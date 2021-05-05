# Combination (조합)

n개의 수 중에서 r개를 뽑아 순서를 고려하지 않고 나열한 것.  

- nCr = n! / r! * (n - r)!  

## 직접 구현

```cpp
void combi(vector<int> &nums, int sum, int pos, int depth){
    if (depth == 3){
        if (is_prime[sum]) cnt_prime++;
        return ;
    }

    for (int i=pos; i<nums.size(); ++i){
        combi(nums, sum + nums[i], i + 1, depth+1);
    }
}
```

- __중요한 점__ : 재귀함수를 돌때, 현재지점(pos)를 함수가 알고있어야 한다. pos 지점부터 순회하며 원소를 넣어야, 원소가 중복되지 않고 삽입이 잘 된다.
- __순열__ : 순열을 구현할때에는, 순서가 유효하므로 현재지점(pos)이 필요하지 않다. 중복 수열이 아닌경우에는 visit 배열을 사용하여 이미 존재하는 원소를 판별한다. 

```cpp
void permutation(int sum, int size){
    if (size == N){
        if (sum == answer) cnt_ans++;
        return ;
    }

    for (int i=0; i<N; ++i){
        visited[i] = true; // 중복 수열을 구현하는 경우 제거해주면 됨
        permutation(sum + nums[i], size); // 현재까지 넣은 원소의 개수만 다음 함수가 알고 있으면됨
        visited[i] = false;
    }
}
```

## next_permutation 사용

Container의 시작과 끝 iter를 인자로 받음, 다음 순열이 존재하면 만들어 준 뒤 True를 반환, 존재하지 않으면 false를 반환  

- 오름차순으로 정렬되어있어야 한다.

### 순열을 이용해 조합 만들기

next_permutation은 원소들 중 중복은 제외하고 순열을 만들어 주기 때문에, 이를 이용해 조합을 구할 수 있다.  

```
{0, 0, 1}의 경우 순열은  
- 1,2,3 : {0,0,1}
- 1,3,2 : {0,1,0}
- 2,1,3 : {0,0,1}
- 2,3,1 : {0,1,0}
- 3,1,2 : {1,0,0}
- 3,2,1 : {1,0,0}
으로 중복되는 순열들이 존재하게 되는데, next_permutation은 중복을 제외해주므로  

{0, 0, 1}, {0, 1, 0}, {1, 0, 0} 만 존재하게 된다. 이를 이용해 1을 가진 원소들만 뽑아줌으로써 조합을 구현할 수 있다.
```

```cpp
vector<int> cb(nums.size(), 0);
int sum;
for (int i=nums.size()-3; i<nums.size(); ++i) cb[i] = 1;

do{
    sum = 0;
    for (int i=0; i<nums.size(); ++i){
        if (cb[i]) sum += nums[i];
    }
    if (is_prime[sum]) answer++;

} while(next_permutation(cb.begin(), cb.end()));

return answer;
}
```