# 2019-2 객체지향 프로그래밍 프로젝트 - **{Do-Meh-Vin}**
구성원: 3-1 김도현  | 3-3 이혜원  | 3-4 진혜빈

## 1. 주제
{리듬을 타자♪♬ - 노래가사와 함께하는 타자게임}

## 2. 동기
{많은 사람들이 타자연습을 위해 타자연습프로그램을 사용하며, 타자연습은 컴퓨터를 사용하기 위해 거쳐야 하는 필수코스로 자리잡았다. 
 이러한 프로그램은 자리연습부터 시작해서 낱말 연습, 짧은 글 연습, 긴 글 연습 등의 기능을 제공하며, 컴퓨터 키보드를 자유자재로 사용하고 각종 문서 작업의 효율을 높이기 위해선 타자의 정확도와 속도를 높이는 반복적인 훈련이 필요하다. 
하지만 기존의 타자연습프로그램은 내장되어있는 단어와 문장들이 한정적이기 때문에 흥미가 쉽게 저하된다. 또한 흥미유발을 위해 존재하는 다양한 타자게임 역시 시각적 효과만 높였을 뿐, 실질적인 존재 의미를 충족시키지 못한다.
이러한 문제점들을 보완하기 위해 노래방게임과 타자연습게임을 병합하는 아이디어를 고안하게 되었다.
}

## 3. 프로그램 사용 대상
{타자치는 것을 막 익히기 시작하는 유아 / 초등학생 또는 기존의 타자연습 프로그램에 싫증을 느낀 사람}

## 4. 목적
{기존의 타자연습에서 새로운 기능을 추가하여 색다른 재미와 다양한 난이도를 추가하는 것이 궁극적 목표이다. 
 재미요소의 추가는 노래를 이용한다. 해당 노래의 박자에 맞추어 타자를 치는 것이다. 게임의 타입은 두 가지로 한다. 
첫 번째의 주 기능은 싱크가사를 통해 노래 박자에 맞추어 타이핑을 하는 것이다. 이를 통해 타자게임을 시작하는 사람들의 관심을 끌고, 기존 유저들의 유지율을 높여 많은 사람들의 타자실력 향상에 도움을 주는 것이 목표이다. ( 아래사진과 같이 노래방 처럼 박자에 맞추어 가사가 등장하고 해당 가사가 모두 흘러나오기전에 타이핑 해야함 )

 +부수적인 두번째 기능으로 기존의 타자게임에서 무작위적인 단어 대신 노래가사가 떨어지는 방식의 타입도 제작
}

## 5. 주요기능
  
* 싱크가사 데이터
현재 자유롭게 활용가능한 오픈된 싱크가사 데이터는 없는 것으로 확인되었다. 단, LRC파일( 가사 한줄의 싱크 타이밍 값이 저장되어있는 파일)을 참고하여 사용자가 직접 사용하고자 하는 데이터를 해당폴더에 저장하여 사용할 수 있도록 하되, 약 10곡정도의 기본예제들은 직접 데이터셋을 구축하여 프로그램에 내장되도록 한다.

[1] 노래 싱크 가사 타이핑 게임 

노래 가사를 노래 박자에 맞추어 제한시간안에 입력해야하는 방식

게임 진행
1) 프로그램에 내장된 싱크가사 데이터 중에 원하는 노래의 데이터를 선택
2) 노래가 시작됨과 동시에 화면에는 노래 가사가 단어 단위로 끊겨 무작위 배치된다
( 가사는 해당가사가 노래로 흘러나오기 시작함과 동시에 화면에 등장한다. 싱크가사의 타이밍에 맞춰 등장 )

3) 흘러나오는 노래를 힌트로 무작위 배치된 단어들을 조합하여 가사 문장을 타이핑한다. 
( 완벽하게 타이핑하면 해당 단어들은 화면에서 모두 삭제되고 점수 누적 )
4) 노래가 진행됨에 따라 흘러나오는 가사의 단어들은 화면에 계속 누적되며, 최종적으로 화면에 일정개수 이상의 단어가 쌓이게 되면 game over
5) 노래가 종료되면 game over
6) 게임종료시 현재까지의 점수가 산출된다.


( 참고. 아래 화면처럼 싱크가사의 시간정보에 맞추어 노래가사가 단어 단위로 끊겨 등장)

필요한 기능
1) 싱크가사데이터파일을 통해 가사가 등장해야하는 시점을 확인하는 기능
2) 등장해야하는 가사를 띄어쓰기 단위로 끊어 화면에 무작위적으로 배치하는 기능
3) 화면에 띄워진 가사단어들의 개수를 카운팅하여 일정 개수가 넘어가면 게임이 종료되는 기능
4) 가사를 완벽하게 입력하면 점수가 누적되고 화면에 보여지는 해당가사의 단어들이 모두 삭제되는 기능
5) 노래 속도를 조절하여 게임의 난이도를 조절할 수 있는 기능( ex. 0.5배속/1배속/2배속 )


[2] 노래가사 타이핑 게임

기존의 타자연습게임에서 parsing으로 불러온 노래가사를 타이핑하는 방식 

게임 진행
1) 프로그램에 내장된 가사 데이터 중에 원하는 노래의 데이터를 선택
2) 사용자가 처음 단어를 치는 순간에 게임이 시작되고, 기존의 오리지널한 타자연습과 같이 모든 가사를 내리 타이핑하게 한다.
3) 가사는 문장별로 끊어놓고, 다음 문장으로 넘어가는 것은 엔터 / 스페이스바로 한다.
4) 모든 가사를 입력한 순간 게임이 종료되고 점수가 산출된다.

( 참고. 기존의 한컴타자의 긴글연습과 비슷한 UI를 지닐 것이다.)              

필요한 기능
1) 선택한 곡의 모든 가사가 문장단위로 구분되고 각 문장마다 타이핑하는 칸이 주어지는 기능
2) 다음 입력칸으로 넘어갈 때 엔터 / 스페이스바로 넘어가는 기능
3) 화면에 띄운 가사를 모두 입력하였을 때 엔터 / 스페이스바를 누르면 자동으로 다음화면으로 넘어감과 동시에 다음칸으로 넘어가는 기능
4) 오타에 반응하여 알려주는 기능
5) 모두 완벽히 입력하였을 때 성공으로 인식하고 다음 창을 열어주는 기능
6) 오타수에 따라 정확도와 모두 입력한 시간을 점수표로 출력하는 기능

## 6. 프로젝트 핵심
{
위의 주요 기능들을 구현하기 위해 가장 핵심적인 포인트는 다음과 같다. 

[1] 노래 싱크 가사 타이핑 게임
- 노래가 흘러나옴에 따라 적절한 시간에 해당가사가 단어로 분할되어 화면에 랜덤으로 띄워지는 기능

[2] 노래 가사 타이핑 게임
- 정확도와 속도를 측정하고 이에 따라 다르게 점수를 매기는 기능
}

## 7. 구현에 필요한 라이브러리나 기술
{pygame을 바탕으로 기본적인 UI를 생성}

## 8. **분업 계획**


## 9. 기타

<hr>

#### readme 작성관련 참고하기 [바로가기](https://heropy.blog/2017/09/30/markdown/)

#### 예시 계획서 [[예시 1]](https://docs.google.com/document/d/1hcuGhTtmiTUxuBtr3O6ffrSMahKNhEj33woE02V-84U/edit?usp=sharing) | [[예시 2]](https://docs.google.com/document/d/1FmxTZvmrroOW4uZ34Xfyyk9ejrQNx6gtsB6k7zOvHYE/edit?usp=sharing) | [[예시 3]](https://github.com/goldmango328/2018-OOP-Python-Light) | [[예시4]](https://github.com/ssy05468/2018-OOP-Python-lightbulb) | [[모두보기]](https://github.com/kadragon/oop_project_ex/network/members)
