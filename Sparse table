#include<bits/stdc++.h>
using namespace std;
 
#define ll long long
#define ld long double
#define endl "\n"
#define yes cout<<"YES"<<endl
#define no  cout<<"NO"<<endl
const int N=2e5+10;
const int LOG=22;
ll bin_log[N][LOG];
void query(ll L,ll R)
{
     ll len=R-L+1;
     ll e=0;
     while((1<<(e+1)<=len))
     e++;
     
     cout<<min(bin_log[L][e],bin_log[R-(1<<e)+1][e])<<endl;
}
void solve()
{
     //TIME COMPLEXITY O(N(logN)+Q(logN));
     
     ll n,q;
     cin>>n>>q;
     ll a[n];
     for(auto &p:a)
     cin>>p;
     
     // Initialization
     for(int i=0;i<n;i++)
     bin_log[i][0]=a[i];
     
     // Pre processing
     for(int i=1;i<LOG;i++)
     {
          for(int j=0;(j+(1<<i)-1)<n;j++)
          bin_log[j][i]=min(bin_log[j][i-1],bin_log[j+(1<<(i-1))][i-1]);
     }
     
     // answering queries;
     while(q--)
     {
          ll L,R;
          cin>>L>>R;
          L--,R--;
          query(L,R);
     }
}
int main()
{
	solve();
}
