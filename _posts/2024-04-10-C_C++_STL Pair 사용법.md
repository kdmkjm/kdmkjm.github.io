---
title: C++ pair 사용법
date: 2024-04-10 21:54:00 +09:00
categories: [Coding_test, C/C++]
tags:
  [
    Coding_test,
    C,
    C++,
    utility,
    pair,
    algorithm,
  ]
---

> C++의 표준 라이브러리 중 utility에 포함된 pair의 기본 사용법을 기술

---

## 1. Pair의 설명 및 기본 사용법

> 두 종류의 데이터 타입을 하나의 객체로 취급할 수 있게 말그대로 쌍(pair)를 지어준다. "utility" 헤더를 상속 받아 사용할 수 있다. 

```cpp
#include <iostream>
#include <utility>
using namespace std;

int main()
{
	pair<int, string> p1 = { 1,"apple"};
	pair<int, string> p2;

	p2 = make_pair(2, "banana");

	cout << "first : " << p1.first << " second : " << p1.second << '\n';
	cout << "first : " << p2.first << " second : " << p2.second << '\n';
}
```

## 2. vector, queue와 응용

```cpp
#include <iostream>
#include <utility>
#include <vector>
#include <queue>
#include <algorithm>
using namespace std;

int main()
{
	// int, string형의 페어를 가진 벡터 v를 생성
	vector<pair<int, string>> v;

	// v에 인자 추가
	v.push_back(make_pair(1, "one"));
	v.push_back(make_pair(5, "five"));
	v.push_back(make_pair(4, "four"));
	v.push_back(make_pair(2, "two"));
	v.push_back(make_pair(3, "three"));

	for (int i = 0; i < v.size(); i++)
	{
		cout << "첫번째 인자 : " << v[i].first << " 두번째 인자 : " << v[i].second << '\n';
	}

	sort(v.begin(), v.end());

	for (int i = 0; i < v.size(); i++)
	{
		cout << "첫번째 인자 : " << v[i].first << " 두번째 인자 : " << v[i].second << '\n';
	}

	// string, int형의 페어를 가진 큐 q를 생성
	queue<pair<string, int>> q;

	// q에 인자 추가
	q.push({ "eleven", 11 });

	cout << "첫번째 인자 : " << q.front().first << " 두번째 인자 : " << q.front().second << '\n';
}
```

## 마무리
---
알고리즘 문제를 풀다보면 보통 벡터 등과 결합한 문제가 자주 출제된다. 익숙해지도록 하자.