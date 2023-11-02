# Codechef_starters_106_Div3

# First Question
<details>

  <summary>Python CODE</summary>
	BRUTE FORCE

```python
	class Solution:
		def minimumSum(self, nums):
			sum = float('inf')
			for i in range(len(nums) - 2):
				for j in range(i + 1, len(nums) - 1):
					for k in range(j + 1, len(nums)):
						if nums[i] < nums[j] and nums[j] > nums[k]:
							sum = min(sum, nums[i] + nums[j] + nums[k])
			return -1 if sum == float('inf') else sum
```

</details>

<details>
  <summary>C++</summary>
  
  ```cpp
    class Solution {
		public:
			int minimumSum(vector<int>& nums) {
				int sum = INT_MAX;
				for (int i = 0; i < nums.size() - 2; i++) {
					for (int j = i + 1; j < nums.size() - 1; j++) {
						for (int k = j + 1; k < nums.size(); k++) {
							if (nums[i] < nums[j] && nums[j] > nums[k])
								sum = min(sum, nums[i] + nums[j] + nums[k]);
						}
					}
				}
				return sum==INT_MAX?-1:sum;
			}
		};
  ```

</details>


<details>
  <summary>JAVA</summary>
  
  ```java
	class Solution {
		public int minimumSum(int[] nums) {
			int sum = Integer.MAX_VALUE;
			for (int i = 0; i < nums.length - 2; i++) {
				for (int j = i + 1; j < nums.length - 1; j++) {
					for (int k = j + 1; k < nums.length; k++) {
						if (nums[i] < nums[j] && nums[j] > nums[k]) {
							sum = Math.min(sum, nums[i] + nums[j] + nums[k]);
						}
					}
				}
			}
			return (sum == Integer.MAX_VALUE) ? -1 : sum;
		}
	}
  ```
</details>


# Second Question - Minimum Sum of Mountain Triplets II

<details>
    <summary>Python Code</summary>
  
  ```
    class Solution:
        def minimumSum(self, nums):
            m = float('inf')
            n = len(nums)
            l = [0] * n
            r = [0] * n
            l[0] = 0
            
            for i in range(1, n):
                if nums[l[i - 1]] < nums[i]:
                    l[i] = l[i - 1]
                else:
                    l[i] = i
            
            r[n - 1] = n - 1
            for i in range(n - 2, -1, -1):
                if nums[r[i + 1]] < nums[i]:
                    r[i] = r[i + 1]
                else:
                    r[i] = i
            
            for i in range(n):
                if nums[l[i]] < nums[i] and nums[i] > nums[r[i]] and l[i] < i and i < r[i]:
                    m = min(m, nums[i] + nums[l[i]] + nums[r[i]])
            
            if m == float('inf'):
                return -1
            return m

  ```
</details>


<details>
  <summary>C++</summary>
  
  ```
    class Solution {
        public:
            int minimumSum(vector<int>& nums) {
                int m = INT_MAX;
                int n = nums.size();
                vector<int> l(n),r(n);
                l[0]=0;
                for(int i=1;i<n;i++)
                {
                    if(nums[l[i-1]]<nums[i])
                    {
                        l[i]=l[i-1];
                    }
                    else l[i]=i;
                }
                r[n-1]=n-1;
                for(int i=n-2;i>=0;i--)
                {
                    if(nums[r[i+1]]<nums[i])
                    {
                        r[i]=r[i+1];
                    }
                    else r[i]=i;
                }
                for(int i=0;i<n;i++)
                {
                    if(nums[l[i]]<nums[i] && nums[i]>nums[r[i]] && l[i]<i && i<r[i])
                    {
                        m=min(m,nums[i]+nums[l[i]]+nums[r[i]]);
                    }
                }
                if(m==INT_MAX) return -1;
                return m;
            }
        };
  ```
</details>


<details>
  <summary>JAVA</summary>
  
  ```
        class Solution {
              public int minimumSum(int[] nums) {
                  int m = Integer.MAX_VALUE;
                  int n = nums.length;
                  int[] l = new int[n];
                  int[] r = new int[n];
                  l[0] = 0;
                  
                  for (int i = 1; i < n; i++) {
                      if (nums[l[i - 1]] < nums[i]) {
                          l[i] = l[i - 1];
                      } else {
                          l[i] = i;
                      }
                  }
                  
                  r[n - 1] = n - 1;
                  for (int i = n - 2; i >= 0; i--) {
                      if (nums[r[i + 1]] < nums[i]) {
                          r[i] = r[i + 1];
                      } else {
                          r[i] = i;
                      }
                  }
                  
                  for (int i = 0; i < n; i++) {
                      if (nums[l[i]] < nums[i] && nums[i] > nums[r[i]] && l[i] < i && i < r[i]) {
                          m = Math.min(m, nums[i] + nums[l[i]] + nums[r[i]]);
                      }
                  }
                  
                  if (m == Integer.MAX_VALUE) {
                      return -1;
                  }
                  return m;
              }
          }
  ```
</details>

# Third Question
<details>

  <summary>Python CODE</summary>
	BRUTE FORCE

```python
	class Solution:
		def minimumSum(self, nums):
			sum = float('inf')
			for i in range(len(nums) - 2):
				for j in range(i + 1, len(nums) - 1):
					for k in range(j + 1, len(nums)):
						if nums[i] < nums[j] and nums[j] > nums[k]:
							sum = min(sum, nums[i] + nums[j] + nums[k])
			return -1 if sum == float('inf') else sum
```

</details>

<details>
  <summary>C++</summary>
  
  ```cpp
    class Solution {
		public:
			int minimumSum(vector<int>& nums) {
				int sum = INT_MAX;
				for (int i = 0; i < nums.size() - 2; i++) {
					for (int j = i + 1; j < nums.size() - 1; j++) {
						for (int k = j + 1; k < nums.size(); k++) {
							if (nums[i] < nums[j] && nums[j] > nums[k])
								sum = min(sum, nums[i] + nums[j] + nums[k]);
						}
					}
				}
				return sum==INT_MAX?-1:sum;
			}
		};
  ```

</details>


<details>
  <summary>JAVA</summary>
  
  ```java
	class Solution {
		public int minimumSum(int[] nums) {
			int sum = Integer.MAX_VALUE;
			for (int i = 0; i < nums.length - 2; i++) {
				for (int j = i + 1; j < nums.length - 1; j++) {
					for (int k = j + 1; k < nums.length; k++) {
						if (nums[i] < nums[j] && nums[j] > nums[k]) {
							sum = Math.min(sum, nums[i] + nums[j] + nums[k]);
						}
					}
				}
			}
			return (sum == Integer.MAX_VALUE) ? -1 : sum;
		}
	}
  ```
</details>


# Save People

<details>
    <summary>Python Code</summary>

```
        def solve():
        n, m, x, y = map(int, input().split())
        mul = n * m
        print(max(mul - x * m, mul - (n - x + 1) * m, mul - y * n, mul - (m - y + 1) * n))
    
        t = int(input())
        for _ in range(t):
            solve()


```
</details>


<details>
  	<summary>C++</summary>
  
```
        #include <iostream>
        #include <algorithm>
        #include <vector>
        #include <math.h>
        #include <set>
        #define rep(i,a,b) for(int i=a; i<b; i++)
        
        using namespace std;
        
        typedef long long ll;
        
        void solve(){
            ll n,m,x,y; cin>>n>>m>>x>>y;
            ll mul=n*m;
            cout<<max({mul-x*m,mul-m*(n-x+1),mul-y*n,mul-n*(m-y+1)});
            cout<<"\n";
        }
        
        int main(){
           ios_base::sync_with_stdio(false);
           cin.tie(NULL); cout.tie(NULL);
           int t; cin>>t; while(t--)solve();
           return 0;
        }
```
</details>


<details>
	<summary>JAVA</summary>
  
```

      import java.util.Scanner;

      public class Main {
          public static void main(String[] args) {
              Scanner sc = new Scanner(System.in);
              int t = sc.nextInt();
      
              while (t-- > 0) {
                  long n = sc.nextLong();
                  long m = sc.nextLong();
                  long x = sc.nextLong();
                  long y = sc.nextLong();
      
                  long mul = n * m;
                  long result = Math.max(Math.max(mul - x * m, mul - (n - x + 1) * m), Math.max(mul - y * n, mul - (m - y + 1) * n));
      
                  System.out.println(result);
              }
          }
      }


```
</details>



# Counting Possibilites

<details>
    <summary>Python Code</summary>

            from collections import deque

            def dfs(node, adj, child):
                curr = 0
                for nbr in adj[node]:
                    curr += dfs(nbr, adj, child)
                child[node] = curr
                return curr + 1
            
            def extension(node, adj, child, ext, e):
                ext[node] = e
                for nbr in adj[node]:
                    extension(nbr, adj, child, ext, e + child[node] - (child[nbr] + 1))
            
            def solve():
                n = int(input())
                adj = [[] for _ in range(n + 1)]
                par = [0] * (n + 1)
                
                for i in range(n - 1):
                    u, v = map(int, input().split())
                    adj[u].append(v)
                    par[v] = u
            
                root = 0
                for i in range(1, n + 1):
                    if par[i] == 0:
                        root = i
                        break
            
                minpos = [n] * (n + 1)
                q = deque()
                q.append(root)
                p = 1
                
                while q:
                    sz = len(q)
                    for i in range(sz):
                        curr = q.popleft()
                        minpos[curr] = p
                        for nbr in adj[curr]:
                            q.append(nbr)
                    p += 1
            
                child = [0] * (n + 1)
                dfs(root, adj, child)
                ext = [0] * (n + 1)
                extension(root, adj, child, ext, 0)
                
                ans = [0] * (n + 2)
                
                for i in range(1, n + 1):
                    ans[minpos[i]] += 1
                    if ext[i] >= 0 and (minpos[i] + ext[i] <= n):
                        ans[minpos[i] + ext[i] + 1] -= 1
                
                for i in range(1, n + 1):
                    ans[i] += ans[i - 1]
                    print(ans[i], end=" ")
                print()
            
            t = int(input())
            for _ in range(t):
                solve()



  
</details>


<details>
  <summary>C++</summary>

                  #include<bits/stdc++.h>
                  #include <ext/pb_ds/assoc_container.hpp>
                  #include <ext/pb_ds/tree_policy.hpp>
                  using namespace std;
                  using namespace __gnu_pbds;
                  
                  typedef tree<int, null_type, less<int>, rb_tree_tag, tree_order_statistics_node_update> pbds; 
                  
                  //member functions :
                  //1. order_of_key(k) : number of elements strictly lesser than k
                  //2. find_by_order(k) : k-th element in the set
                  
                  //=======================================================================
                  #define ll long long
                  #define int long long
                  #define vi vector<int>
                  #define vvi vector<vector<int>>
                  #define pii pair<int,int> 
                  #define vpi vector<pair<int,int>> 
                  #define all(x) (x).begin(),(x).end()
                  #define countbits(x) __builtin_popcount(x)
                  #define yes cout<<"YES"<<endl
                  #define no cout<<"NO"<<endl
                  #define pb push_back
                  #define ff first
                  #define ss second
                  #define endl '\n'
                  
                  int mod = 1e9+7;
                  //int mod = 998244353;
                  
                  int max(int a,int b){return a>b ? a : b ;}
                  
                  int min(int a,int b){return a<b ? a : b ;}
                  
                  int hcf(int a,int b){
                      return (b==0 ? a : hcf(b,a%b));
                  }
                  
                  int lcm(int x,int y){
                      return (x*y)/hcf(x,y);
                  }
                  
                  int pow(int x, int y, int p = 1e9 + 7)
                  {
                    int res = 1;
                  
                    while (y > 0)
                    {
                      if (y % 2 == 1)
                      {
                        res = (res * x)%p;
                      }
                      y = y >> 1;
                      x = (x * x)%p;
                    }
                    return res % p;
                  }
                  
                  int sqrt(int a)
                  {
                    int l = 0;
                    int r = 1e9;
                    int ans = 0;
                    while (l <= r)
                    {
                      int mid = l + ((r - l) / 2);
                      if (mid * mid <= a)
                      {
                        ans = mid;
                        l = mid + 1;
                      }
                      else
                      {
                        r = mid - 1;
                      }
                    }
                    return ans;
                  }
                  
                  
                  void printarray(vector<int> &a){
                      for(int i=0 ; i<(int)a.size() ; i++){
                          cout<<a[i]<<" ";
                      }
                      cout<<endl;
                  }
                  
                  int acc(vi &a){
                      int sum=0;for(auto e : a){sum+=e;}
                      return sum;
                  }
                  
                  int dfs(int node,vvi &adj,vi &child){
                      int curr=0;
                      for(auto nbr : adj[node]){
                          curr+=dfs(nbr,adj,child);
                      }
                      child[node]=curr;
                      return curr+1;
                  }
                  
                  void extension(int node,vvi &adj,vi &child,vi &ext,int e){
                      ext[node]=e;
                      for(auto nbr : adj[node]){
                          extension(nbr,adj,child,ext,e+child[node]-(child[nbr]+1));
                      }
                      return;
                  }
                  
                  void solve(){
                      int n;
                      cin>>n;
                      vector<vector<int>> adj(n+1);
                      vector<int> par(n+1,0);
                      for(int i=0 ; i<n-1 ; i++){
                          int u,v;
                          cin>>u>>v;
                          adj[u].pb(v);
                          par[v]=u;
                      }
                      int root=0;
                      for(int i=1 ; i<=n ; i++){
                          if(par[i]==0){
                              root=i;
                              break;
                          }
                      }
                      vi minpos(n+1,n);
                      queue<int> q;
                      q.push(root);
                      int p=1;
                      while(!q.empty()){
                          int sz=q.size();
                          for(int i=0 ; i<sz ; i++){
                              int curr=q.front();
                              q.pop();
                              minpos[curr]=p;
                              for(auto nbr : adj[curr]){
                                  q.push(nbr);
                              }
                          }
                          p++;
                      }
                      vi child(n+1,0);
                      dfs(root,adj,child);
                      vi ext(n+1,0);
                      extension(root,adj,child,ext,0);
                      vi ans(n+2,0);
                      // printarray(ext);
                      for(int i=1 ; i<=n ; i++){
                          ans[minpos[i]]++;
                          if(ext[i]>=0  && (minpos[i]+ext[i]<=n)) {
                              ans[minpos[i]+ext[i]+1]--;
                          }
                      }
                      for(int i=1; i<=n ; i++){
                          ans[i]+=ans[i-1];
                          cout<<ans[i]<<" ";
                      }
                      cout<<endl;
                    
                  }
                  
                  int32_t main(){
                      ios_base::sync_with_stdio(false);
                      cin.tie(NULL);
                      int t;
                      cin>>t;
                      while(t--){
                          solve();
                      }
                      //for(int i=1 ; i<=t ; i++){
                      //    cout<<"Case #"<<i<<": ";
                      //    solve();
                      //} 
                  
                      return 0;
                  }

          
</details>


<details>
  <summary>JAVA</summary>


            import java.util.*;

      public class Main {
          static void dfs(int node, List<List<Integer>> adj, int[] child) {
              int curr = 0;
              for (int nbr : adj.get(node)) {
                  curr += dfs(nbr, adj, child);
              }
              child[node] = curr;
          }

    static void extension(int node, List<List<Integer>> adj, int[] child, int[] ext, int e) {
        ext[node] = e;
        for (int nbr : adj.get(node)) {
            extension(nbr, adj, child, ext, e + child[node] - (child[nbr] + 1));
        }
    }

    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int t = sc.nextInt();

        while (t-- > 0) {
            int n = sc.nextInt();
            List<List<Integer>> adj = new ArrayList<>();
            for (int i = 0; i <= n; i++) {
                adj.add(new ArrayList<>());
            }

            int[] par = new int[n + 1];

            for (int i = 0; i < n - 1; i++) {
                int u = sc.nextInt();
                int v = sc.nextInt();
                adj.get(u).add(v);
                par[v] = u;
            }

            int root = 0;
            for (int i = 1; i <= n; i++) {
                if (par[i] == 0) {
                    root = i;
                    break;
                }
            }

            int[] minpos = new int[n + 1];
            Queue<Integer> q = new LinkedList<>();
            q.add(root);
            int p = 1;

            while (!q.isEmpty()) {
                int sz = q.size();
                for (int i = 0; i < sz; i++) {
                    int curr = q.poll();
                    minpos[curr] = p;
                    for (int nbr : adj.get(curr)) {
                        q.add(nbr);
                    }
                }
                p++;
            }

            int[] child = new int[n + 1];
            dfs(root, adj, child);

            int[] ext = new int[n + 1];
            extension(root, adj, child, ext, 0);

            int[] ans = new int[n + 2];

            for (int i = 1; i <= n; i++) {
                ans[minpos[i]]++;
                if (ext[i] >= 0 && (minpos[i] + ext[i] <= n)) {
                    ans[minpos[i] + ext[i] + 1]--;
                }
            }

            for (int i = 1; i <= n; i++) {
                ans[i] += ans[i - 1];
                System.out.print(ans[i] + " ");
            }

            System.out.println();
        }


</details>
