# Algorithm

<details>
    <summary style="font-size : 20px;"><strong> Q) 거품정렬에 대해 설명해주세요</strong></summary></br>

서로 인접한 두 원소의 대소를 비교하고 조건에 맞지 않다면 자리를 교환하며 정렬하는 알고리즘이다.   

정렬 여부에 상관없이 매번 두 원소를 비교하므로 최선, 최악, 평균 시간복잡도가 O(N^2)으로 동일하다. 

</div></details></br>

<details>
<summary>선택정렬에 대해 설명해주세요</summary>

루프를 돌면서 해당 위치에 넣을 원소를 선택하며 정렬하는 알고리즘이다. 매번 마지막 원소까지 모두 비교를 하기 때문에 최선, 최악, 평균 시간복잡도가 O(N^2)이다.  

</details></br>
# 삽입 정렬이란?

2번째 원소부터 시작해 이전의 원소들과 비교해 자신이 삽입되어야 할 위치를 찾아나가며 정렬하는 알고리즘이다. 최선의 경우(이미 정렬 되어있는 경우) 한번씩만 비교하기때문에 O(N)의 시간복잡도가 걸리고, 최악과 평균은 O(N^2)의 시간복잡도를 갖는다.

# 셀 정렬이란?

삽입 정렬의 최선 시간복잡도가 빠른것에 착안, 삽입되어야할 위치가 상당히 먼 경우를 최적화 시킨 정렬이다. 일정한 기준에 따라 부분 리스트를 만든 후 부분 리스트의 개수를 줄여가며 삽입정렬을 하는 방식의 정렬 알고리즘이다. 최선 O(N^2), 평균 O(N^1.5), 최악 O(N^2)이다.  

# 퀵 정렬이란?

분할 정복 알고리즘의 하나입니다. 배열의 원소 중 하나를 피벗으로 설정한 뒤 피벗을 기준으로 피벗보다 작은 요소들은 왼쪽, 큰 요소들은 오른쪽으로 나누어 리스트를 분할합니다. 피벗을 제외한 각각의 리스트에서 또 피벗을 설정한 후 정렬하는 과정을 재귀적으로 호출합니다.  

최선의 경우, 또 평균적으로 매 재귀 단계마다 N번의 비교가 일어나고, 재귀 호출은 총 lgN번 일어나기때문에 시간복잡도는 O(NlgN)이 됩니다. 하지만 최악의 경우 즉, 피벗을 잘못잡아 리스트가 계속 불균등하게 나누어지는 경우 시간복잡도는 O(N^2)이 됩니다.  

퀵 소트는 추가적인 메모리 공간을 필요로 하지 않을 뿐더러 평균 시간복잡도가 O(NlgN)인 다른 정렬 알고리즘들과 비교헀을때 더욱 빠릅니다. 이에 대한 이유는 locality라는 개념으로 설명드릴 수 있을것 같습니다. locality 란 일부 메모리 영역을 집중적으로 access하는 경향을 말하는데, 자주 사용되는 페이지는 물리 메모리 뿐만 아니라 캐시에도 두기 때문에 더 빠른 접근과 처리가 가능하게 됩니다. 이러한 부분에서 퀵 소트는 피봇을 기준으로 정렬시 피봇을 기준으로 나누어 가기 때문에 데이터 탐색 위치가 크게 변하지 않고, locality를 활용할 수 있습니다. 이런 이유로 퀵 소트는 페이지 캐시 히트가 높고, 비슷한 시간 복잡도를 가진 다른 정렬 알고리즘과 비교했을때 빠른 성능을 보입니다.  

# 합병 정렬이란?

분할 정복 알고리즘의 하나입니다. 리스트를 균등한 크기로 분할하는 과정을 재귀적으로 호출하여 더이상 쪼갤수 없을때까지 진행한 후, 분할된 부분 리스트를 다시 합병하는 과정을 재귀적으로 호출하여 정렬하는 알고리즘 입니다.  

최선, 최악, 평균의 경우 모두 같은데, 먼저 이동연산의 경우 임시 배열에 복사했다가 다시 가져와야하기 때문에 각 재귀 단계마다 2N번의 이동이 발생하고, 재귀 호출은 총 lgN번 일어나기 때문에 총 2NlgN번의 이동 연산이 발생한다. 합병 연산의 경우 매 재귀호출 단계마다 N번의 연산과 재귀호출은 lgN번 일어나기때문에 총 NlgN번의 합병연산이 일어난다. 즉, 비교연산과 합병연산을 합쳐 3NlgN, O(NlgN)의 시간복잡도를 가진다.  

# 힙 정렬이란?

힙 정렬이란 완전 이진 트리를 기본으로하는 힙 자료구조를 기반으로 한 정렬 알고리즘이다.  

내림차순 정렬을 기준으로 설명하면, 먼저 최대 힙을 구성 한 뒤, 가장 큰 값을 가진 루트 노드를 차례대로 꺼내서 배열의 앞부터 저장하면 된다. 시간복잡도는 힙 구조 생성 알고리즘의 시간복잡도 O(NlgN)과 루트 노드를 하나씩 꺼내며 정렬된 배열을 만드는 시간복잡도 O(NlgN)을 합해 O(NlgN)이다.  

# 이분 탐색이란?

탐색 범위를 두 부분으로 분할하며 찾는 방식이다. 이분 탐색의 가장 큰 특징은 이미 정렬 된 상태에서 진행이 되어야 한다는 것이다. 정렬된 리스트에서 중간값, mid값을 구한 뒤 이에대한 대소 비교를 기준으로 부분을 나누며 탐색값을 찾는 알고리즘 이다.  

시간 복잡도는 매번 두 부분씩 나누며 찾으므로 O(lgN)이 된다.  

# DFS와 BFS에 대해 설명해주세요

먼저 DFS란 루트 노드, 시작 노드에서 시작해서 다음 분기로 넘어가기 전에 해당 분기를 먼저 모두 탐색하는 방법이다.  

주로 재귀호출을 통해 구현하며 구현방법이 BFS에 비해 간단하다. 주로 모든 노드를 방문하고자 할 때 DFS를 사용한다. 시간복잡도는 그래프가 인접 행렬으로 표현됐을때 O(N^2), 인접 리스트, 벡터로 표현됐을때 O(간선 + 정점) 이다.

BFS란 루트 노드, 시작 노드에서 시작해서 인접한 노드들 부터 먼저 탐색하는 방법이다.  

Queue를 사용하여 구현하며 DFS에 비해 비교적 구현방법이 간단하며 두 노드 사이의 최단경로를 찾을때 BFS를 주로 사용한다. 시간복잡도는 DFS와 같다.

# 최단경로 찾기 알고리즘에 대해 설명해주세요

다익스트라 알고리즘 - 하나의 정점에서 모든 정점까지의 최단 경로를 구하는 방법으로, 첫 정점을 기준으로 연결되어 있는 정점들 중 비용이 가장 적은 간선을 통해 정점을 방문하며 최단거리를 갱신해 나가는 알고리즘이다.  

배열을 사용해 구현하는 방법과 우선순위 큐를 사용해 구현하는 방법이 있다. 배열을 사용할시 모든 간선에 대해 검사하며 최소비용을 가진 간선을 찾아야 하지만 우선순위 큐로 구현할 시 log의 시간에 구할 수 있게되어 시간복잡도를 줄일 수 있다.  

벨만 포드 알고리즘 - 한 노드에서 다른 노드들 까지의 최단거리를 구하는 알고리즘입니다. 다익스트라 알고리즘이 음수 간선이 존재할 떄 답을 구할 수 없는것에 비해, 벨만 포드 알고리즘은 모든 간선에 대해 정점의 개수만큼 진행을 함으로써 답을 구할 수 있습니다. 그러므로 시간복잡도는 당연히 다익스트라 알고리즘보다 느립니다. (음의 사이클은 정점의 개수만큼 모든 간선을 진행할때 마지막 진행 단계에서 값이 달라진다면 음의 사이클이 있다고 판단 할 수 있다)

플로이드 워셜 알고리즘 - 모든 정점에서 모든 정점으로의 최단 경로를 구하는 방법이다. 플로이드 워셜의 경우 배열을 사용해 최단거리를 초기화 한 다음 거쳐가는 정점을 기준으로 배열의 값들을 업데이트 하며 모든 노드들에 대한 최단거리를 구할 수 있다.

# Spanning Tree란

# 백트래킹 알고리즘에 대해 설명해주세요

백트래킹이란 DFS 알고리즘을 기반으로, 굳이 검사해도 되지 않아도 되는 부분에 대해서는 가지치기를 통해 나머지만 탐색하는 알고리즘이다. 대표적인 예제로 N-Queen 문제가 있다. N-Queen 문제의 경우 각 Queen을 둘때 마다 그다음에 둘 Queen의 자리가 제한되있으므로, 모든 자리에대해서 탐색하지 않아도 되기에 가지치기를 통한 백트래킹 알고리즘을 사용할 수 있다.

# 완전탐색 알고리즘에 대해 설명해주세요

완전탐색 알고리즘이란 모든 가능한 경우의 수에 대해 확인을 하여 조건에 맞는 답을 찾는 알고리즘 입니다.  

# 투포인터 알고리즘에 대해 설명해주세요

# 다이나믹 프로그래밍에 대해 설명해주세요

# 그리디 알고리즘에 대해 설명해주세요