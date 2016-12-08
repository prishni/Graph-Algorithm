#include <cmath>
#include <cstdio>
#include <vector>
#include <iostream>
#include <algorithm>
#include <deque>
using namespace std;
class Graph{
    
    // adjacency list 
    vector< vector<int> > adj;
    //no. of vertices
    int v; 
    public:
    //constructor
    Graph(int v){
        this->v = v;
        adj.resize(v);
    }
    
    void addEdge(int v,int u){
        adj[v].push_back(u);
        adj[u].push_back(v);
    }
    
    void BFS(int s,int n){
        int start = s;
        deque<int> queue;
        vector<int> visited(n);
        vector<int> pathlength(n);
       
        for(int i=0;i<this->v;i++){
            visited[i]=0;
            pathlength[i]=-1;
            }
        visited[s]=1;
        pathlength[s]=0;
        queue.push_back(s);
       
        while(!queue.empty()){
            s = queue.front();
            visited[s]=1;
            queue.pop_front();
            
            for(int i = 0;i<adj[s].size();i++){
                
                if(visited[adj[s][i]]==0) {
                    queue.push_back(adj[s][i]);
                    visited[adj[s][i]]=1;
                    pathlength[adj[s][i]] =pathlength[s] + 6;
                }
            }
        }
        for(int i=0;i<this->v;i++){
            if(i==start)continue;
            cout<<pathlength[i]<<" ";
        }
    }
};

int main() {
    int q;
    cin>>q;
     
    for(int k=0;k<q;k++){
        int n,e,v,u,s;
        cin>>n>>e;
        Graph g(n);
        for(int E=0;E<e;E++){
            cin>>v>>u; 
            g.addEdge(v-1,u-1);
        }
        cin>>s; 
        g.BFS(s-1,n);
        cout<<endl;
    }
    return 0;
}
