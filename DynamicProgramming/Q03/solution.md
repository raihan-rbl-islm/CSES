## Implementation
```cpp
#include <bits/stdc++.h>
using namespace std;
#define _raihan ios::sync_with_stdio(false);cin.tie(nullptr);cout.tie(nullptr);
#define int long long

const int M = 1e9 + 7;
const int N = 1e6 + 9;
vector <int> dp(N, -1);
vector <int> vv; 

int f(int x) {
    if (dp[x] != -1) return dp[x];
    int ans = 0;
    for (int i = 0; i < vv.size(); i ++) {
        if (x - vv[i] >= 0) {
            ans += f(x - vv[i]); 
            ans %= M;
        }
        else break;
    }
    return dp[x] = ans;

}

int32_t main() { _raihan
    dp[0] = 1;
    int n, x; cin >> n >> x;
    for (int i = 0; i < n; i ++) {
        int tmp; cin >> tmp;
        vv.push_back(tmp);
    }
    sort(vv.begin(), vv.end());
    cout << f(x) << "\n";
    
}

```
