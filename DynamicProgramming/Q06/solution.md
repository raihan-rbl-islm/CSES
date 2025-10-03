## Implementation

```cpp
#include <bits/stdc++.h>
using namespace std;
#define _raihan ios::sync_with_stdio(false);cin.tie(nullptr);cout.tie(nullptr);
#define int long long

const int M = 1e9 + 7;
const int N = 1009;
int n;

int dp[N][N];
char arr[N][N];

int f(pair <int, int> pr) {
    int x = pr.first, y = pr.second;
    if (dp[x][y] != -1) return dp[x][y];

    int ans = 0;

    if(y + 1 < n && arr[x][y + 1] == '.') {
        ans += f({x, y + 1});
    }

    if(x + 1 < n && arr[x + 1][y] == '.') {
        ans += f({x + 1, y});
    }

    return dp[x][y] = ans % M;

}


int32_t main() { _raihan
    cin >> n;
    for (int i = 0; i < n; i ++) {
        for (int j = 0; j < n; j ++) {
            cin >> arr[i][j];
            dp[i][j] = -1;
        }
    }
    dp[n - 1][n - 1] = 1;
    cout << ((arr[0][0] == '*')? 0: f({0, 0})) << "\n";
}

```
