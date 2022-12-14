# **CS Study**

### 참고 자료

- [velog](https://velog.io/@minsgy/%EB%B0%B1%EC%97%94%EB%93%9C-%EA%B0%9C%EB%B0%9C%EC%9E%90-%EB%A9%B4%EC%A0%91%ED%95%99%EC%8A%B5%EB%82%B4%EC%9A%A9)

## 목차

> - [스프링](#스프링)
> - [자바](#자바)
> - [보안](#보안)
> - [운영체제](#운영체제)
>
>   > - [프로세스와 스레드의 차이는 무엇인가요?](#프로세스와-스레드의-차이는-무엇인가요)
>   > - [교착상태란 무엇이며, 교착상태가 발생하기 위해서는 어떤 조건이 있어야 하나요?](#교착상태란-무엇이며-교착상태가-발생하기-위해서는-어떤-조건이-있어야-하나요)
>   > - [교착상태의 해결법은 무엇인가요?](#교착상태의-해결법은-무엇인가요)
>   > - [뮤텍스와 세마포어에 대해서 설명해 보시오](#뮤텍스와-세마포어에-대해서-설명해-보시오)
>   > - [컨텍스트 스위칭이란 무엇인가요?](#컨텍스트-스위칭이란-무엇인가요)
>   > - [경쟁 상태란 무엇인가요?](#경쟁-상태란-무엇인가요)
>   > - [프로세스 혹은 스레드의 동기화란 무엇인가요?](#프로세스-혹은-스레드의-동기화란-무엇인가요)
>   > - [사용자 수준의 스레드와 커널 수준의 스레드의 차이는 무엇인가요?](#사용자-수준의-스레드와-커널-수준의-스레드의-차이는-무엇인가요)
>   > - [CPU 스케줄링이란 무엇인가요?](#CPU-스케줄링이란-무엇인가요)
>   > - [CPU 스케줄링 방법에는 대표적으로 어떤 것들이 있나요?](#CPU-스케줄링-방법에는-대표적으로-어떤-것들이-있나요)
>   > - [동기와 비동기, 블로킹과 넌블로킹의 차이는 무엇인가요?](#동기와-비동기-블로킹과-넌블로킹의-차이는-무엇인가요)

<br>

---

## 스프링

<br>

## 자바

<br>

## 보안

<br>

## 운영체제

<br>

> ### 프로세스와 스레드의 차이는 무엇인가요
> 
> <br>
> 
> ✨ 정리
> 
> > 프로세스는 프로그램 실행에 필요한 내용이 메모리에 적재되어 운영체제로부터 자원을 할당 받은 작업에 단위이며, 스레드는 프로세스 내에서 실행되는 흐름의 단위입니다. 프로세스 사이에서는 자원을 공유하지않지만, 스레드는 서로 Heap 영역의 자원을 공유합니다.
> 
> <br>
> 
> ❗ 프로그램
> 
> > - 어떤 작업을 하기 위해 처리방법과 순서를 기술한 명령문 집합체
> > - 프로그램을 실행 -> 프로세스 인스턴스 생성!
> 
> <br>
> 
> ❗ 프로세스
> 
> > 프로그램 실행에 필요한 내용이 메모리에 적재되어 운영체제로부터 자원을 할당 받은 작업의 단위
> 
> <br>
> 
> ❗ 스레드
> 
> > - 어떠한 프로세스 내에서 실행되는 흐름의 단위
> > - 스레드들 프로세스 내에서 각각 stack만 따로 할당받고 Code, Data, Heap 영역은 공유!

<br>

[목차로 이동](#목차)

<br>

> ### 교착상태란 무엇이며 교착상태가 발생하기 위해서는 어떤 조건이 있어야 하나요
> 
> <br>
> 
> ✨ 정리
> 
> > 교착상태란 두 개 이상의 프로세스나 스레드가 서로 필요한 자원을 모두 얻지 못해서 무한히 다음 자원을 기다리게 되는 상태입니다. 
> > 
> > 교착상태가 발생하기위한 조건은 상호배제, 점유 대기, 비선점, 순환대기로 총 네개이며 모두 성립되어야합니다. 
> 
> <br>
> 
> ❗ 교착상태 (DeadLock)
> 
> > - 두 개 이상의 프로세스나 스레드가 서로 자원을 얻지 못해서 다음 처리를 하지 못하는 상태
> > - 무한히 다음 자원을 기다리게 되는 상태
> > - 교착상태가 일어나는 경우
> > 
> > ![image](https://user-images.githubusercontent.com/63089631/197149839-04219b2b-fd25-44b1-a322-7130220883e2.png)
> > 
> > > 프로세스1, 2가 자원1, 2를 모두 얻어야 한다고 가정!
> > > 
> > > ​    
> > > 
> > > t1 : 프로세스1이 자원1을 얻음 / 프로세스2가 자원2를 얻음
> > > 
> > > t2 : 프로세스1은 자원2를 기다림 / 프로세스2는 자원1을 기다림
> > > 
> > > ​    
> > > 
> > > 현재 서로 원하는 자원이 상대방에 할당되어 있어서, 두 프로세스는 무한정 wait 상태에 빠짐
> 
> <br>
> 
> ❗ 교착상태 발생 조건
> 
> > - 4가지 모두 성립해야 데드락 발생!
> > 
> > > 하나라도 성립하지않으면 해결 가능!
> > 
> > 1. 상호 배제(Mutual exclusion)
> > 
> > > - 자원은 한번에 한 프로세스만 사용할 수 있음
> > 
> > 2. 점유 대기(Hold and wait)
> > 
> > > - 최소한 하나의 자원을 점유하고 있으면서 다른 프로세스에 할당되어 사용하고 있는 자원을 추가로 점유하기 위해 대기하는 프로세스가 존재해야 함
> > 
> > 3. 비선점(No preemption)
> > 
> > > - 다른 프로세스에 할당된 자원은 사용이 끝날 때까지 강제로 빼앗을 수 없음
> > 
> > 4. 순환 대기(Circular wait)
> > 
> > > - 프로세스의 집합에서 순환 형태로 자원을 대기하고 있어야 함

<br>

[목차로 이동](#목차)

<br>

> ### 교착상태의 해결법은 무엇인가요
> 
> <br>
> 
> > ✨ 정리
> > 
> > > 교착상태의 해결법은 예방, 회피, 발견, 회복이 있습니다. 예방은 교착 상태 발생 조건을 하나 제거하고, 회피는 자원 할당 후 문제 없는지 확인합니다. 발견은 데드락이 발생하면 빠르게 문제 해결하는 것이고 회복은 교착상태에 놓인 프로세스를 종료하거나 할당을 해제하는 것입니다.
> 
> <br>
> 
> ❗ 교착상태의 해결법
> 
> > 1. 예방
> > 
> > > - 교착 상태가 발생하기 전에 미리 조치를 취하는 방식
> > > 
> > > - 교착 상태 발생 조건 중 하나를 제거함으로써 해결
> > > 
> > > - 자원 낭비가 심함
> > > 
> > > > 1. 모든 **자원 공유** 허용
> > > > 2. 모든 자원에 대해 **선점 허용**
> > > > 3. 필요 자원을 **한 번에 모두 할당**하기
> > > > 4. **자원에게 순서 부여**를 통해 프로세스 순서의 증가 방향으로만 자원 요청
> > 
> > 2. 회피
> > 
> > > - 프로세스가 자원을 요구할 때, 시스템은 자원을 할당한 후에도 안정 상태로 남아있는가를 확인하여 교착 상태를 회피
> > > - 오버헤드가 많이 발생
> > > 
> > > > ex) 은행원 알고리즘(Banker's Algorithm)
> > > > 
> > > > > - 안정 상태면 자원 할당, 아니면 다른 프로세스들이 자원 해지까지 대기
> > 
> > 3. 발견
> > 
> > > - 데드락이 발생하면 빠르게 발견하고 문제를 해결하는 것
> > > 
> > > > 자원 할당 그래프(Resource Allocation Graph)를 통해 교착 상태 탐지
> > > > 
> > > > ![image](https://user-images.githubusercontent.com/63089631/197308531-a372a927-ebbb-44c5-82a4-4f820756f305.png)
> > 
> > 4. 회복
> > 
> > > - 교착 상태를 일으킨 프로세스를 종료하거나 할당된 자원을 해제하면서 회복
> > > 
> > > > 1. 프로세스 종료 방법
> > > > 
> > > > > - 교착 상태의 프로세스 모두 중지
> > > > 
> > > > > - 교착 상태가 제거될 때까지 한 프로세스씩 중지
> > > > 
> > > > 2. 자원 선점 방법
> > > > 
> > > > > - 자원을 빼앗긴 프로세스는 강제 종류 이후 재시작
> > > > 
> > > > > - 교착 상태에 빠진 프로세스가 필요로 하는 자원을 강제로 가져옴
> 
> <br>
> 
> <br>
> 
> [출처_velog](https://velog.io/@yanghl98/%EC%9A%B4%EC%98%81%EC%B2%B4%EC%A0%9COS-Deadlock%EB%8D%B0%EB%93%9C%EB%9D%BD-%EC%A0%95%EC%9D%98-%EB%B0%9C%EC%83%9D-%EC%A1%B0%EA%B1%B4-%ED%95%B4%EA%B2%B0-%EB%B0%A9%EB%B2%95)

<br>

[목차로 이동](#목차)

<br>

> ### 뮤텍스와 세마포어에 대해서 설명해 보시오
> 
> ✨ 정리
> 
> > 세마포어와 뮤텍스는 여러 프로세스나 쓰레드가 공유 자원에 접근하는 것을 제어하기 위한 방법입니다. 
> > 
> > 뮤텍스는 공유된 자원에 대해 하나의 프로세스 혹은 스레드만이 접근 가능하며, 세마포어는 세마포어 변수 만큼 여러 프로세스 혹은 스레드가 접근이 가능합니다.
> > 
> > 또, 세마포어는 현재 수행중인 프로세스가 아닌 다른 프로세스가 세마포어를 해제할 수 있지만, 뮤텍스는 락을 획득한 프로세스만이 락 해제가 가능합니다.   
> 
> <br>
> 
> ❗ 들어가기 전
> 
> > 1. **공유된 자원에 여러 개의 프로세스 혹은 스레드가 동시에 접근하면 Critical Section**(여러 프로세스가 데이터를 공유하며 수행될 때, 각 프로세스에서 공유 데이터를 접근하는 프로그램 코드 블록) **문제가 발생**할 수 있다. 
> > 2. 이를 해결하기 위해 **공유 자원을 한 번에 하나의 프로세스 혹은 레드만만 접근할 수 있도록 제한을 두는 동기화 방식**을 취해야 한다.   
> 
> <br>
> 
> ❗ 뮤텍스 (Mutex)
> 
> > - 공유된 자원의 데이터 혹은 임계영역(Critical Section) 등에 **하나의** **Process 혹은 Thread만 접근 가능** (동기화 대상이 하나, 서로 겹치지 않게)
> > - **한 프로세스에 의해 소유될 수 있는 Key를 기반**으로 한 상호배제 기법
> > 
> > > - **Key에 해당하는 객체를 소유한 스레드/프로세스만이** 공유자원에 접근 가능
> > 
> > ![image](https://user-images.githubusercontent.com/63089631/197338098-85f3ea83-f551-426e-97d4-b4d885408ca0.png)
> 
> <br>
> 
> ❗ 세마포어 (Semaphore)
> 
> > - 공유된 자원의 데이터 혹은 임계영역(Critical Section) 등에 세마포어의 변수만큼 **여러 Process 혹은 Thread가 접근가능** (동기화 대상이 하나 이상)
> > 
> > - 자원을 사용하지 않는 상태가 될 때, 대기하던 프로세스가 즉시 자원을 사용하고. 이미 다른 프로세스에 의해 사용중이라는 사실을 알게 되면, 재시도 전에 일정시간 대기해야 함
> > 
> > - 일반적으로 비교적 긴 시간을 확보하는 리소스에 대해 사용
> 
> <br>
> 
> ❗ 차이점
> 
> > - Mutex는 동기화 대상이 오직 **1개일 때** 사용하며, Semaphore는 동기화 대상이 **1개 이상일 때** 사용합니다.
> > - Mutex는 **자원을 소유할 수 있고**, 책임을 가지는 반면 Semaphore는 **자원 소유가 불가**합니다.
> > - Mutex는 상태가 0, 1 뿐이므로 Lock을 가질 수 있고, 소유하고 있는 스레드만이 이 Mutex를 해제할 수 있습니다. 반면 Semaphore는 Semaphore를 소유하지 않는 스레드가 Semaphore를 해제할 수 있습니다.
> > - Semaphore는 시스템 범위에 걸쳐 있고, 파일 시스템 상의 파일로 존재합니다. 반면, Mutex는 프로세스의 범위를 가지며 프로세스 종료될 때 자동으로 Clean up 됩니다.
> 
> <br>
> 
> <br>
> 
> [출처_티스토리](https://delpho.tistory.com/29?category=943516)

<br>

[목차로 이동](#목차)

<br>

> ### 컨텍스트 스위칭이란 무엇인가요?
> 
> > ✨ 정리
> > 
> > > - CPU가 어떤 프로세스를 실행하고 있는 상태에서 OS의 스케쥴러가 인터럽트를 진행하여 더 높은 우선순위를 가진 프로세스가 실행되어야 할 때, 스케쥴러가 레지스터에 저장된 기존 프로세스 값들을 커널 내부에 존재하는 PCB에 저장하고, 새 프로세스의 값을 PCB에서 다시 가져와서 교체하는 작업
> > 
> > <br>
> > 
> > ❗ 컨텍스트 스위칭
> > 
> > > - CPU가 어떤 프로세스를 실행하고 있는 상태에서 OS의 스케쥴러가 인터럽트를 진행하여 더 높은 우선순위를 가진 프로세스가 실행되어야 할 때, 스케쥴러가 레지스터에 저장된 기존 프로세스 값들을 커널 내부에 존재하는 PCB에 저장하고, 새 프로세스의 값을 PCB에서 다시 가져와서 교체하는 작업
> > 
> > <br>
> > 
> > ❗ 콘텍스트 스위칭이 발생하는 상황
> > 
> > > 1. 입/출력을 요청할 때
> > > 2. CPU 사용시간이 만료되었을 때
> > > 3. 자식 프로세스를 만들 때
> > > 4. 인터럽트 처리를 기다릴 때
> > 
> > <br> ❗ 단점
> > 
> > > - 잦게 발생할수록 오버헤드(Overhead) 비용이 발생하여 성능이 떨어짐
> > > 
> > > ![image](https://user-images.githubusercontent.com/63089631/197340570-2247554b-cd9f-418d-a53d-cbbbff0730e2.png)
> > > 
> > > - 위 그림에서, 프로세스 P0가 실행 중인 상태(excuting)에서 유휴 상태(idle)가 될 때 프로세스 P1이 곧바로 excuting이 되지 않고 idle을 좀 더 하다가 excuting이 된다.
> > > 
> > > >  이유 👉👉 프로세스 P0의 상태를 PCB에 저장하고 프로세스 P1 상태를 PCB에서 가져와야 하기 때문
> > > 
> > > >  그런데, 이 과정에서 PCB를 저장하고 가져올 때 CPU는 아무런 일도 하지 못하게 된다.
> 
> [출처_티스토리](https://delpho.tistory.com/25?category=943516)

<br>

[목차로 이동](#목차)

<br>

> ### 경쟁 상태란 무엇인가요
> 
> > ✨ 정리
> > 
> > > 교착상태의 한 종류로, <u>**프로세스가 어떤 순서로 데이터에 접근하느냐에 따라 결과값이 달라질 수 있는 상황**</u>입니다.
> > 
> > <br>
> > 
> > 
> > ❗ 경쟁 상태 (Race Condition)
> > 
> > > - 프로세스가 어떤 순서로 데이터에 접근하느냐에 따라 결과값이 달라질 수 있는 상황
> > > - 둘 이상의 입력이나 조작이 동시에 일어나 의도하지 않은 결과를 가져오는 경우
> > > - 동시 접근 시 자료의 일관성을 해치는 결과가 나타날 수 있음
> > > - 경쟁 상태도 교착상태의 종류 중에 하나
> 
> <br>
> 
> [출처_티스토리](https://delpho.tistory.com/25?category=943516)

<br>

[목차로 이동](#목차)

<br>

> ### 프로세스 혹은 스레드의 동기화란 무엇인가요
>
> > ✨ 정리
> >
> > > 여러 프로세스가 **공유하는 자원의 일관성**을 유지하기 위해 필요한 것으로, 다른 프로세스에게 영향을 주거나 받는 프로세스를 위해 **공유 자원에 접근하는 흐름을 제어하는 것** 입니다.
>
> <br>
>
> > ❗ 프로세스 동기화
> >
> > > 현대 컴퓨터의 메모리에는 여러 프로세스가 존재하는데, 이러한 프로세스들이 하나의 공유 메모리나 또 다른 프로세스에 접근할 때는 매우 신중해야 한다. 이처럼 한 프로세스가 다른 프로세스에게 영향을 받거나 주는 프로세스를 **Cooperating process**라고 한다. 반대로 아무런 영향을 미치지 않는 독립적인 프로세스는 **Independent process**이다.
> > >
> > > 
> > >
> > > 현대 컴퓨터 환경에는 cooperating process가 훨씬 많이 존재하고, 이들은 서로 영향을 미치기 때문에 데이터나 흐름에 대한 **동기화**가 매우 중요하다. 프로세스 사이에 동기화를 하는 것을 **프로세스 동기화(Process Synchronization)** 라고 한다.(현재에는 대부분 쓰레드 기준으로 스위칭을 하므로, **Thread synchronization**으로 많이 불린다.)
> > >
> > > 
> > >
> > > 대표적인 예로 기차표 예매가 있다. 어느 시간에 한 좌석의 기차표는 반드시 하나만 존재해야한다. 그런데 이를 예매하려는 사용자(프로세스)는 여러 명이다. 이 사용자들이 동시에 하나의 좌석 기차표를 구매하려고 하면 어떠한 일이 발생할까? 실제 환경에서는 당연하게도 동기화 문제를 해결한 시스템이므로 한 사람만이 기차표를 예매할 수 있을 것이다. 만약 동기화에 문제가 발생한다면 한 기차표를 여러 사람이 예매하는 불상사가 발생할 수 있다.
> > >
> > > 
> > >
> > > 프로세스 동기화는 여러 프로세스가 **공유하는 자원의 일관성**을 유지하는 것이다. 가령 여러 프로세스가 동시에 하나의 공유된 자원에 접근하려고 할 때 이 프로세스들의 순서를 정하여 데이터의 일관성을 유지시켜주어야 한다.

<br>

[목차로 이동](#목차)

<br>

> ### 사용자 수준의 스레드와 커널 수준의 스레드의 차이는 무엇인가요
>
> > ✨ 정리
> >
> > > - 커널 수준 스레드는 커널 레벨에서 생성되는 스레드로서, 커널이 직접 관리하고 커널 관련 작업을 하는 스레드입니다.
> > >
> > > - 사용자 수준 스레드는 사용자 단에서 스레드를 관리하는 library로 인해 관리되는 스레드입니다.
> > > - 차이점은. <u>**커널 수준 스레드는 컨텍스트 스위칭으로 인해 특정 block되어도 다른 스레드들은 독립적으로 일이 가능합니다. 하지만 사용자 수준 스레드는 컨텍스트 스위칭이 존재하지 않습니다.**</u>
>
> <br>
>
> > ❗ 스레드
> >
> > > - 스레드 👉 <u>**프로세스 내 작업 단위**</u>
> > > - 커널 수준 스레드 / 사용자 수준 스레드로 나뉨
>
> <br>
>
> > ❗ 커널 수준 스레드
> >
> > > - 커널 레벨에서 생성되는 스레드
> > > - 운영체제 시스템 내에서 생성, 동작 👉 커널이 관리
> > > - 커널 수준에서는 프로세스가 주기억 장치에 여러 개가 적재되어 CPU 할당을 기다리며 동작
> > > - 컨텍스트 스위칭으로 인해 특정 스래드가 block 되어도 독립적으로 일 가능
> > >
> > > ![image](https://user-images.githubusercontent.com/63089631/198836201-ccb102d2-8cf6-4728-8a1a-a7511193a664.png)
>
> <br>
>
> > ❗ 사용자 수준 스레드
> >
> > > - 사용자 단에서, 스레드를 관리하는 library로 인해 생성, 관리되는 스레드
> > > - 커널과 관련 없는 기능들만 수행하는 스레드 (ex. 입출력)
> > > - 커널이 이 스레드에 대해서 모름
> > >
> > > > - 물리적으로 밖에 있는게 아니라, 커널 내부에 있지만 <u>**커널의 통제권 밖에 있음**</u>
> > > > - 커널에는 '커널 모드'와 '사용자 모드' 두 가지 있다고 생각.
> > > > - <u>**입출력 인터럽트가 발생하면 커널은 '사용자 모드'가 되어서 사용자 수준 스레드의 응답을 기다린다. 사용자 수준 스레드의 응답이 오면 다시 '커널 모드'로 변환되어 이어서 커널 스레드가 일 처리를 하게 되는 것!!!**</u>
> > >
> > > - 컨텍스트 스위칭 존재 X, 인터럽트 당하면 스레드 전부 Block
> > >
> > > > - ```
> > > >   프로세스 내에서 스레드들끼리는 자원을 공유하여 일 처리를 하기 때문에(스레드 통신 기법), 커널이 관리하는 스레드는 스레드 동기화 기법으로 자원 관리를 할 수 있으므로, 하나의 스레드가 Block이 되어도 다른 스레드들은 커널 관리로 인해 계속해서 동기화가 되어 일 처리가 가능하다.
> > > >       
> > > >   하지만 사용자 수준 스레드는 커널의 관리를 받지 않음으로, Block으로 인해 공유 자원의 무결성에 대한 문제가 발생할 수 있으므로 하나의 스레드가 인터럽트 당하면 모든 스레드가 멈추도록 하는 것 아닐까 추측한다.
> > > >   ```
> > >
> > > ![image](https://user-images.githubusercontent.com/63089631/198836381-fb1afbca-a98c-443a-963c-433ab5b4f24b.png)
> > >
> > > ![image](https://user-images.githubusercontent.com/63089631/198836760-36d9203b-e5dc-4b5e-8c24-e1e184624c87.png)
>
> <br>
>
> [출처_티스토리](https://helloinyong.tistory.com/293)

<br>

[목차로 이동](#목차)

<br>

> ### CPU 스케줄링이란 무엇인가요
>
> > ✨ 정리
> >
> > > > 컴퓨터 자원을 효율적으로 관리하기 위해 **프로세스들 사이에서 CPU의 자원 할당을 받기 위한 우선순위를 관리하는 일**입니다. 
>
> <br>
>
> > ❗ CPU 스케줄링
> >
> > > - 컴퓨터 자원을 효율적으로 관리하기 위해 **프로세스들 사이에서 CPU의 할당을 받기 위한 우선순위를 관리하는 일**
> > > - 점유 방식에 따라 스케줄링 방식이 구분

<br>

목차로 이동

<br>

> ## CPU 스케줄링 방법에는 대표적으로 어떤 것들이 있나요
>
> > ✨ 정리
> >
> > > - 점유 방식에 따라 비선점, 선점 스케줄링 방식이 구분됩니다. 비선점 스케줄링은 이미 할당된 CPU를 다른 프로세스가 **강제로 빼앗아 사용할 수 없는** 스케줄링 기법이며, 선점 스케줄링은 하나의 프로세스가 CPU를 할당받아 실행 하고 있을 때 **우선순위가 높은 프로세스가 CPU를 강제로 빼앗아 사용할 수 있는** 스케줄링 기법입니다.
>
> <br>
>
> > ❗ CPU 스케줄링 방법
> >
> > > - 점유 방식에 따라 비선점, 선점 스케줄링 방식이 구분됩니다.
>
> <br>
>
> > ❗ 비선점 스케줄링
> >
> > > - 이미 할당된 CPU를 다른 프로세스가 **강제로 빼앗아 사용할 수 없는** 스케줄링 기법
> > > - 프로세스가 CPU를 할당받으면 **해당 프로세스가 완료될 때까지 CPU를 사용**
> > > - 프로세스 응답 시간의 예측이 용이하며, 일괄 처리 방식에 적합
> > > - 비선점 스케줄링의 종류에는 FCFS, SJF, 우선순위, HRN, 기한부 등의 알고리즘이 있습니다.
>
> <br>
>
> > ❗ 선점 스케줄링
> >
> > > - 하나의 프로세스가 CPU를 할당받아 실행 하고 있을 때 **우선순위가 높은 프로세스가 CPU를 강제로 빼앗아 사용할 수 있는** 스케줄링 기법
> > > - 선점으로 인한 많은 **오버헤드가 발생**
> > > - **시분할 시스템에 사용**하는 스케줄링이다. (긴급을 요하는 우선순위를 갖는 시분할 처리, 실시간 처리에 유용)
> > >
> > > - 우선순위가 높은 프로세스를 빠르게 처리할 수 있음.
> > > - 선점이 가능하도록 일정 시간 배당에 대한 인터럽트용 타이머 클록이 필요합니다.
> > > - 선점 스케줄링의 종류에는 라운드로빈, SRT, 선점 우선순위, 다단계 큐, 다단계 피드백 큐 등의 알고리즘이 있음
>
> <br>
>
> [출처_https://coding-factory.tistory.com/309](https://coding-factory.tistory.com/309)

<br>

[목차로 이동](#목차)

<br>

> ## 동기와 비동기 블로킹과 넌블로킹의 차이는 무엇인가요
>
> > ✨ 정리
> >
> > > - 
>
> <br>
>
> > ❗ 블로킹(blocking) vs 논블로킹(non-blocking)
> >
> > - 블로킹/논블로킹을 구분짓는 기준 👉 '요청받는 함수가 제어권(함수실행권)을 언제 넘겨주느냐의 차이'
> >
> > > - 블로킹
> > >
> > > > - 요청자(부모함수)는 요청한 작업이 끝날 때까지 다른 작업을 하지 않고 마냥 기다림
> > > > - 다른 함수를 호출할 때, 제어권도 아예 함께 넘겨주고 그 작업이 끝난 후에야 돌려받기 때문
> > > > - (제어권이 없는 상태라 아무것도 못함)
> > > > - 요청 받은 함수는 모든 실행을 마치고 최종 return 값을 돌려줌
> > >
> > > - 논블로킹
> > >
> > > > - 요청자는 요청한 작업이 수행되는 동안 다른 작업을 할 수 있음
> > > > - 다른 함수를 호출할 때, 제어권을 넘겨주기는 하지만 바로 돌려받음
> > > > - **(제어권을 돌려받은 호출자는 다른 작업을 바로 수행 가능)**
>
> <br>
>
> > ❗ 동기(Synchronous) vs 비동기(Asynchronous)
> >
> > - 요청받은 함수가 작업을 완료했는지를 누가 체크하느냐의 차이
> >
> > > - 동기
> > >
> > > 
