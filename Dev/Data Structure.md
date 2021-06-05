# 그래프에 대해서 설명해주세요

그래프란 노드와 노드를 연결하는 간선을 하나로 모아놓은 자료구조이다. 방향 그래프, 무방향 그래프 모두 존재합니다. 그래프의 구현은 인접 행렬이나 인접 리스트로 구현할 수 있는데, 구현 방법에 따라 그래프의 탐색에 대한 시간복잡도가 달라집니다. 그래프 탐색 알고리즘은 대표적으로 모든 노드에대해 탐색하는 DFS와 BFS가 있고 특정 노드에서 다른 모든 노드들에 대한 최단경로를 구하는 다익스트라, 벨만포드, 플로이드 워셜 알고리즘이 있습니다.

# 트리에 대해서 설명해주세요

트리는 그래프의 한 종류로 방향성이 있고, 사이클이 없는 비순환 그래프입니다. 노드들이 부모-자식의 관계로 존재하고 있습니다. 이진 트리, 이진 탐색 트리, 최대힙 최소힙 등의 예시가 있습니다

# 힙에 대해서 설명해주세요

완전 이진 트리의 일종으로 우선순위 큐를 위해 만들어진 자료구조입니다. 최대힙 또는 최소힙에 따라 최댓값, 최솟값을 빠르게 찾아낼 수 있도록 구현되었습니다. 힙의 삽입 삭제는 O(logN)에 이루어 집니다.  

# 해시 테이블에 대해서 설명해주세요

해시 테이블이란 키, 밸류 쌍의 데이터를 저장하는 자료구조로 데이터를 빠르게 검색할 수 있는 자료구조입니다. 각각의 키값에 대해 해시함수를 적용하여 고유한 Index값을 생성하고, 이 Index값을 활용해 값을 저장하거나 검색하게 됩니다. 이러한 구조로 데이터를 저장하게 되면 key값을 기반으로 데이터를 찾을때 해시 함수를 한번만 수행하면 되기 떄문에 상수 시간복잡도로 빠르게 저장, 삭제, 조회 할 수 있습니다.  

해시 함수에는 키 값을 테이블의 크기로 나누어 인덱스를 구하는 방식과, 키의 문자열을 아스키코드로 바꾸고 값을 합한 것을 인덱스로 사용하는 방식 등이 있습니다.  

해시 값이 충돌하는 경우 크게 체이닝하는 방법과 오픈 어드레싱 방법이 있습니다. 먼저 체이닝 하는 방법은 동일한 인덱스를 가진 데이터에 대해 추가 메모리를 사용하여 연결리스트 방식으로 저장하는 방식입니다. 이러한 체이닝 방식은 해시 테이블의 확장이 필요없고 구현이 간단하다는 장점이 있습니다. 하지만 데이터가 많아지면 그만큼 해시의 효율성이 감소한다는 단점이 있습니다. 그 다음 오픈 어드레싱이란 추가적인 메모리를 사용하는 체이닝 방식과 다르게 비어있는 해시 테이블의 공간을 활용하는 방법입니다. 비어있는 인덱스를 탐색하는 방법으로는 바로 그 다음 인덱스를 확인하는 선형탐사 방법이 있는데 이는 특정 부분에 데이터가 밀집되는 현상이 발생한다는 문제점이 있습니다. 여기서 조금 더 개선한 방법이 제곱식으로 그 다음 인덱스를 정해 밀집 현상을 줄이는 제곱 탐사 방법이 있습니다. 또는 증가 폭을 또다른 해시 함수를 통해 구하는 이중 해싱 방법도 있습니다.  

해시 충돌을 최소화 하기 위한 방법으로는 해시함수를 잘 설계하는 것과 버킷의 사이즈를 충분히 크게하는 방법 등이 있습니다.  

# 맵과 해쉬맵의 차이를 설명해주세요

# 리스트와 배열의 차이를 설명해주세요

배열의 경우 메모리가 연속적으로 할당되어 있기 때문에 인덱스를 사용하여 상수시간에 원소에 접근할 수 있습니다. 하지만 연결리스트의 경우 메모리가 연속적으로 할당되어 있지 않기 때문에 특정 원소에 접근하기 위해선 모든 노드를 순회해야 하고, O(N)의 시간복잡도를 가지게 됩니다.  

하지만 삽입과 삭제에 있어선 연결리스트가 더 빠른시간에 해결할 수 있는데요, 원소와 원소사이 포인터만 바꿔줌으로써 상수시간에 삽입과 삭제를 수행할 수 있는 반면 배열의 경우 기존 원소들의 위치를 조정해줘야 되고, 최악의 경우에는 삽입과 삭제에 선형시간이 걸리게 됩니다.

# 스택과 큐의 차이를 설명해주세요

스택은 LIFO 방식으로, 가장 나중에 들어간 데이터가 가장 먼저 나오는 방식으로 이루어진 자료구조이고, 큐는 FIFO 방식으로 가장 먼저 들어간 데이터가 가장 먼저 나오는 방식으로 이루어진 자료구조입니다.