---
title: C++ Array, List, Map 사용법
date: 2024-04-29 21:15:00 +09:00
categories: [Coding_test, C/C++]
tags:
  [
    Coding_test,
    C,
    C++,
    Array,
    List,
    Map,
    algorithm,
  ]
---

> C++에서 주료  사용되는 데이터  구조인 Array, List, Map의  특징 및 사용법을 기술

---

## 1. Array(배열)의 설명 및 기본 사용법

> 배열(Array)은 같은 자료형의 여러 변수에 접근할 수 있게 해주는 집계 데이터 유형이다.
> 고정 크기의 연속적인 메모리 할당이 가능하며 인덱스를 통한 접근이 가능하다.
> 선언 후 크기 변경이 불가하며, 빠른 엑세스가 장점이다.

```cpp
#include <iostream>
#include <array>
using namespace std;

int main()
{
	array< int, 3 > arr1 = { 1, 5, 7 };
	array< int, 0 > arr2;
	array< int, 1 > arr3;
	array< int, 2 > arr4;

	cout << arr1.empty() << '\n';
	cout << arr2.empty() << '\n';

	cout << arr2.max_size() << '\n';
	cout << arr4.max_size() << '\n';

	cout << sizeof(arr1) << '\n';
	cout << sizeof(arr2) << '\n';
}
```

## 2. List(리스트)의 설명 및 기본 사용법

> List는 앞 뒤로 이동이 가능한 이중 연결 리스트로 구성되어 있다.
> 연결 리스트는 동적으로 크기를 변경할 수 있으며 데이터의 삽입, 삭제가 쉬운 특징을 가지고 있다.

```cpp
#include <iostream>
#include <list>
using namespace std;

int main()
{
	// 리스트 생성
	list<int> l1;

	l1.push_back(1);
	l1.push_back(2);
	l1.push_front(3);
	l1.push_back(4);
	l1.push_back(5);

	// 이터레이터 생성
	list<int>::iterator pos_start = l1.begin();
	list<int>::iterator pos_end = l1.end();

	for (pos_start = l1.begin(); pos_start != pos_end; pos_start++)
	{
		cout << *pos_start << " ";
	}
	cout << '\n';

	l1.pop_front();
	l1.pop_back();

	for (pos_start = l1.begin(); pos_start != pos_end; pos_start++)
	{
		cout << *pos_start << " ";
	}
	cout << '\n';

	cout << l1.size() << '\n';
	cout << l1.empty() << '\n';
	cout << l1.front() << '\n';
	cout << l1.back() << '\n';

	pos_start = l1.begin();
	pos_start++;
	l1.insert(pos_start, 9);

	for (pos_start = l1.begin(); pos_start != pos_end; pos_start++)
	{
		cout << *pos_start << " ";
	}
	cout << '\n';
}
```

## 3. Map(맵)의 설명 및 기본 사용법

> 맵(Map)을 Key-value 쌍으로 데이터를 저장하는 연관 컨테이너이다. 트리형식으로 구현되어 있다.
> map은 key-value 쌍으로 구성되어있다.
> key단위로 정렬되어 저장되며 key는 유일한 특성을 갖는다.
> 고로 키는 통한 접근이 매우 빠르다.

```cpp
#include <iostream>
#include <map>
using namespace std;

int main()
{
	map<int, string> map1;

	map1.insert(make_pair(1, "국어"));
	map1.insert(make_pair(2, "영어"));
	map1.insert(make_pair(3, "수학"));

	map1[4] = "과학";

	map<int, string>::iterator pos_start = map1.begin();
	map<int, string>::iterator pos_end = map1.end();

	for (pos_start = map1.begin(); pos_start != map1.end(); pos_start++)
	{
		cout << "key: " << pos_start->first << " value: " << pos_start->second << '\n';
	}

	cout << map1.find(4)->second << '\n';

	map1.erase(2);

	for (pos_start = map1.begin(); pos_start != map1.end(); pos_start++)
	{
		cout << "key: " << pos_start->first << " value: " << pos_start->second << '\n';
	}
}
```

## 마무리
---
각 집계 데이터의 특징에 따라 적합한 유형을 사용하는 것이 관건이다.