---
title:  "Process와 Thread"
excerpt: "Process와 Thread"

header:
  overlay_image: https://images.unsplash.com/photo-1444807121485-ff36df2de82c?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=crop&w=1500&q=80

categories:
  - dev
  - CS
---

**프로세스(Process)**는 프로그램을 구동하여 프로그램 자체와 프로그램의 상태가 메모리 상에서 실행되는 작업 단위이다. - 실행중인 프로그램  
프로세스는 Ready, Running, Blocked 상태를 가진다.
프로세스는 독립적으로 메모리 영역(Code, Data, Heap, Stack)을 다른 프로세스와 공유를 하지 않는다.
프로세스에 포함된 스레드들은 병렬로 실행된다.  

#### Thread  
프로세스 내에서 실행되는 실행 단위

**쓰레드와 프로세스의 차이점**
프로세스는 독립적이기 때문에 메모리영역을 다른 프로세스와 공유를 하지 않지만 쓸레드는 해당 쓰레드를 위한 스택을 생성할 뿐 그외의 메모리 영역은 공유한다.


**Context**란 CPU 가 다루는 Task(Procee / Thread) 에 대한 정보로 어떤 객체를 핸들링 하기 위한 접근 수단이다. Context의 대부분의 정보는 Register에 저장되며 PCB(Process Control Block)로 관리된다.  

**ContextSwitch**란 Cpu를 현재 프로세스에서 다른 프로세스로 넘겨주는 과정이다. PCB는 OS에 의해 스케쥴링 되는 Process Control Block이고, Thread의 경우는 Process내의 TCB(Task Control Block)의 내부 구조를 통해 관리된다. ContextSwitching이 발생하면 Cache초기화, MemoryMapping초기화가 발생하며 많은 비용이 발생한다. Thread는 Stack영역을 제외한 모든 메모리를 공유하기 때문에 ContextSwitching 발생시 Stack영역만 변경을 진행한다. 그래서 컨텍스트 스위칭이 프로세스에 비해 빠르다.

멀티스레드는 프로그램 하나를 여러실행 단위로 쪼개어 실행한다는 측면에서 다중 프로세싱과 의미가 비슷하지만 동일 프로세스에서의 스레드는 메모리영역을 공유하므로 자원생성, 중복성 최소화 등이 가능하므로 효과적이다.

