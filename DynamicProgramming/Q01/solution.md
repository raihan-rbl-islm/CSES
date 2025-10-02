# Dice Combinations (CSES 1633)

- **Link:** https://cses.fi/problemset/task/1633
- **Topic:** DP - 1D
- **Difficulty:** Easy
- **Language:** C++

## Complexity
- **Time:** `O(n * 6)` → `O(n)`
- **Space:** `O(n)`

## C++ Code (Iterative, stack-safe)
```cpp
#include <bits/stdc++.h>
using namespace std;
#define _raihan ios::sync_with_stdio(false);cin.tie(nullptr);cout.tie(nullptr);
#define int long long

const int M = 1e9 + 7;
const int N = 1e6 + 9;
int dp[N];

int f(int n) {
    if(dp[n]!= 0) return dp[n];
    for (int i = 1; i <= 6; i ++) {
        if(n - i >= 0) dp[n] += f(n - i);
        dp[n] %= M;
    }
    return dp[n];

}

int32_t main() { _raihan
    dp[0] = 1;
    int n; cin >> n;
    cout << f(n) << "\n";

}
```
