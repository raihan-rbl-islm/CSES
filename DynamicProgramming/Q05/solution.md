## Implementation

```cpp
#include <bits/stdc++.h>
using namespace std;
#define _raihan ios::sync_with_stdio(false);cin.tie(nullptr);cout.tie(nullptr);
#define int long long

const int N = 1e6 + 9;
vector <int> dp(N, -1);

void getDigits(int n, vector <int> &digits) {
    while (n) {
        int tmp = n % 10;
        if (tmp != 0) digits.push_back(n % 10);
        n /= 10;
    }
}

int f(int n) {
    if (dp[n] != -1) return dp[n];
    vector <int> digits; getDigits(n, digits);
    int ans = INT_MAX;
    for (int i = 0; i < digits.size(); i ++) {
        ans = min(ans, f(n - digits[i]));
    }
    return dp[n] = ans + 1;
    
}


int32_t main() { _raihan
    dp[0] = 0;
    int n; cin >> n;
    cout << f(n) << "\n";
    
}

```
