# leetcoding


<ul>

<li> <!-- template -->
    <code>2. Add Two Numbers</code>
    <br>
    <code>Explanation: </code> 
    <br>
    <details>
        <summary>code</summary>
        ```cpp
            class Solution {
public:
    vector<vector<int>> combinationSum(vector<int>& candidates, int target) {

        vector< vector<int> > ans;
        // index, vector<int> 
        
        function< void(int, vector<int>, int) > solve = [&]
            (int i, vector<int> v, int sum){
            
            if( sum > target ) return ;
            
            if( sum == target ) {
                ans.push_back(v);
                return ;
            }
            
            if(i >= candidates.size()) return ;
            
            { // taking same number 
                v.push_back( candidates[i] );
                solve( i, v, sum + candidates[i] );
                v.pop_back();
            }
            
            { // taking another number 
                v.push_back( candidates[i] );
                solve( i+1, v, sum + candidates[i] );
                v.pop_back();
                
            }
            
            {
                // skiping number 
                solve(i+1, v, sum);
            }
            
            
            
        };
        
        solve(0, {}, 0);
        
        
        
        return ans;
        
    }
};
        ```
    </details>
</li>





</ul>

<details>
<summary>How do I dropdown?</summary>
<hr>

```cpp
int main() {
  int y = SOME_MACRO_REFERENCE;
  int x = 5 + 6;
  cout << "Hello World! " << x << std::endl();
}
```

This is how you drop.
</details>

