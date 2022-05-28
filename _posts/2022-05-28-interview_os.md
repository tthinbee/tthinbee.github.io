---
layout: single
title:  "면접준비 - 운영체제"
categories: Interview
tag: [OS, Interview]
toc: true
author_profile: false
sidebar:
    nav: "docs"
#search: false
---

# 면접준비 - 운영체제
    추후 내용 추가 필요

## 운영체제 목차
<ul>
    <li>운영체제란?</li>
    <li>메모리 구조</li>
    <li>프로세스, 스레드</li>
    <li>CPU 스케줄러</li>
    <li>가상 메모리란?</li>
    <li>데드락이란?</li>
</ul>

### 운영체제란?

    시스템의 자원과 동작을 관리하는 소프트웨어
	프로세스, 저장장치, 네트워킹, 사용자, 하드웨어를 관리

### 메모리 구조

	메모리 공간 종류 4가지 : Code, Data, Heap, Stack
	code : 실행할 프로그램의 코드
	data : 전역변수, 정적변수
	heap : 사용자의 동적 할당
		- 런타임에 크기가 결정
	stack : 함수의 호출정보, 지역변수, 매개 변수
		- 컴파일에 크기가 결정
### 프로세스, 스레드

	프로세스 : 실행중인 프로그램
	스레드 : 프로세스 안 실행 단위
	프로세스는 메모리와 cpu를 프로세스마다 할당받아 사용하는데
	스레드는 프로세스 안에서 다른 스레드와 메모리와 cpu를 공유하여 사용
### CPU 스케줄러

	준비큐 있는 프로세스에 대해 cpu 할당하는 방법
	스케줄링 알고리즘
		비선점 알고리즘
		fcfs(First come First Served)
			먼저 cpu를 요청하는 프로세스를 먼저 처리하는 방식
		sjf (Shortest Job First)
			평균 waiting time을 최소화하기 위해 사용
			버스트 시간이 짧은 프로세스부터 cpu를 할당
		선점 알고리즘
		srt(Shorest remaining time)
			최단 잔여시간을 우선으로 하는 스케줄링 
			진행중인 프로세스가 있어도, 최단 잔여 시간인 프로세스를 위해 sleep시키고 짧은 프로세스를 먼저 할당한다.
		RR(Round robin)
			모든 프로세스가 같은 우선순위를 가지고, time slice를 기반으로 스케줄링 한다.
			time slice가 너무 크면 fcfs랑 다를게 없음
			time slice가 너무 작으면 불필요한 Context Switch가 많이 일어남(옮길때 발생되는 비용이 커짐)
		Priority Scheduling (우선 순위 스케줄링)
			우선 순위가 높은 프로세스에 cpu를 우선 할당하는 방식의 스케줄링
### 가상 메모리란?

		사용하는 부분만 메모리에 올리고, 나머지는 디스크에 보관하는 것
### 데드락이란?

		프로세스가 자원을 얻지 못해 다음 작업을 못하는 상태
		발생조건
			1. 상호배제(Mutual exclusion) : 자원은 한번에 한 프로세스만이 사용할 수 있어야 한다.
			2. 점유대기(Hold and wait) : 최소한 하나의 자원을 점유하고 있으면서 다른 프로세스에 할당되어 사용하고 있는 자원을 추가로 점유하기 위해 대기하는 프로세스가 있어야 한다.
			3. 비선점(No preemption) : 다른 프로세스에 할당된 자원은 사용이 끝날때까지 강제로 빼앗을 수 없어야 한다.
			4. 순환 대기(Circular wait) : 프로세스의 집함{P0,P1,..Pn}에서 P0는 P1이 점유한 자원을 대기하고 P1은 P2가 점유한 자원을 대기하고 P2...Pn-1은 Pn이 점유한 자원을 대기하며 Pn은 P0가 점유한 자원을 요구해야 한다.



