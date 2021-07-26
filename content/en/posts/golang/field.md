---
title: "golang dev"
date: 2021-07-19
description: "Guide to emoji usage in Hugo"
featured: true
tags: ["golang", "syntax", "package"]
categories: ["golang"]
---

![gologo](/images/GO.png)


![Overview](https://github.com/matcornic/hugo-theme-learn/raw/master/images/tn.png)

{{< alert "info" info >}}

{{< alert "warning" warning >}}

{{< alert "success" success >}}

{{< alert "danger" danger >}}

 


## GO 언어 소개🤼
* 구글이 만든 언어
* 2009년에 나와서 10년 넘었다.

## Golang 소개 urls
* https://www.samsungsds.com/kr/insights/golang.html

## Field References
* Twitch
  * https://blog.twitch.tv/en/2019/04/10/go-memory-ballast-how-i-learnt-to-stop-worrying-and-love-the-heap-26c2462549a2/


* Docker, Kubernetes, GRPC에서 사용하고 있다. (신뢰 가득?)
* Python 을 사용하는 대기업들 지금은 어떻게 됐을까?
* Dropbox
  * Dropbox 는 빠른 Python 구현인 Pyston 을 개발하다가, 이미 구현된 빠른 Python 인 PyPy 를 만지작거리다가.. 결국 Go 언어로 갈아탔다. 
* Uber
  * 성능 크리티클한 부분을 Go 로 만들었다. (Node.js 를 고려하다가 Go 를 선택했다고 함.)
* Pinterest
  * Gevent 로 Python 을 빠르게 하다가, Elixir 로 갈아탔다.
  * 참고로 Pinterest 는 MAU (Monthly Active Users) 가 1 억에 달한다고 한다.
  * Alexa 에 의하면 Pinterest 는 Netflix.com 보다 트래픽이 많다고 한다.


구글, 드랍박스, 우버 등등 실리콘벨리의 많은 회사들이 GO 언어로 넘어왔다.
로켓펀치 GO 데브시스터즈 게임서버로 GO선택
9M Interactive, 트리노드, 원더피플, 블루홀스콜, 컴투스 등등 Go언어를 사용한다.
구인하는데 유명한 언어 써있으면 쓸 수 있고 안 쓸 수 있는데, 덜 유명한 언어가 써 있으면 쓴다는 뜻.
Go언어를 모바일에서 쓸 수 있는데 실험 단계이다. (18년 7월 기준)


go 의 현재 버전이 1.16.x 인데요
현재 status로  어떤 분야의 개발이 가능한가요?

## 웹서비스
###. frameworks
  * gin
  * echo
1. frameworks
  * gin
  * echo

## GO 가 잘하는 것
* 메모리 자동관리
* 네트워크 프로그래밍
* 병렬 프로그래밍
* Go routine

## 주 용도
* 서비스용 백엔드나 시스템 데몬 같은 용도로 적합
* 고성능 네트워크 서버
  * gRPC
  * go routine
  * 

## GUI
* Fyne, Wails, Walk가 많이 발전 했지만 electron, QT등과 비교 할 수준은 안 됨.

## Mobile 
* https://github.com/golang/go/wiki/Mobile
  * go-mobile이 버려진 자식인 줄 알았는데, 조금씩 개선되고 있나보네요 이것도 플러터에 비하면 뭐 ^^;

## 웹 Frontend
- GopherJS 
- 대세가 아니니 vuejs, react, 요즘 들어서는 굳이? 싶습니다. 

 

- ebiten 이라는 2D 게임엔진이 있는데, 웹 + 안드 + iOS + 각종 OS로 빌드가 가능 합니다.
최근엔 닌텐도 스위치에 빌드 하도록 업데이트 중이라고 하더군요.

 

- 효율을 생각 해보자면 .. GUI 필요한게 아닌 대부분의 일들은 타언어 수준은 가능합니다.

 

- 게임서버 프로그래머인데 제 지인분이 다니는 국내 게임회사 중에 go 언어로 게임서버 구현된 곳도 한군데 있습니다. 게임업계에서는 go 언어를 도입하는 것에 관심 많은 분들이 종종 있습니다. 메인으로 쓰지않더라도 보조적인 용도로 쓰거나 간단한 프로그램을 만들 때 쓰는거죠. :-)

 

- Ace Framework 대안으로 게임쪽도 go 도입이 확실히 많습니다.

 

- 데탑 쪽 그니까 gui 쪽은 이리저리 해보았지만. 별로 입니다.
메크로, 크롤링 , 서비스 정도는 쓸만하고요,
모바일 쪽은 flutter , react-native 등 이 너무 잘나와서 솔직히 구지 golang 으로 안할꺼 같습니다.

 

(추가)

- 하기 내용 출처: https://namu.wiki/w/Go(%ED%94%84%EB%A1%9C%EA%B7%B8%EB%9E%98%EB%B0%8D%20%EC%96%B8%EC%96%B4)#s-5

 

   나온 지 5년 동안은 구글에 취직이라도 하지 않는 이상[14] 배워봤자 딱히 쓸 데가 없다는 이유로 새로운 언어에 관심이 많은 얼리 어답터 개발자들 사이에서나 알음알음 쓰이던 정도였지만, 다름아닌 구글이 만든 것이기도 하고, 언어 자체가 가진 매력도 있어서 사용자 층이 점차 늘어나는 추세다. 특히 Go 언어를 이용해서 안드로이드와 iOS 앱을 제작할 수 있게 적용 중이다.[15] 또한 Python이 그렇듯 웹 개발에도 쓰이고 있고, Revel, Beego 등의 풀 스택 프레임워크나 Gin 등의 마이크로 프레임워크들이 인기를 끌고 있다. Martini는 한국어 문서도 있다. 특히 서버 사이드 언어로서 좋은 평가를 받고 있는데, 대형 서비스가 아닌 간단한 웹사이트의 경우 Go가 자체적으로 지원하는 라이브러리와 Gorilla 같은 툴킷만으로도 쉽게 웹사이트를 만들어낼 수 있다. 최근에는 Gin이나 echo 등의 웹 프레임워크도 활발히 사용되는 중이다.

컨테이너 기반 가상화 도구인 Docker, Kubernetes를 작성하는 데 사용된 언어로 유명하다.

그리고 전부를 Go로 만든 것은 아니지만, 당연히 구글을 비롯해 드롭박스나 클라우드플레어[16], 사운드클라우드, 넷플릭스 등에서도 기존의 기능들 중 상당수를 새롭게 Go를 이용해 바꿨다고 한다. 트위치도 많은 부분이 Go로 작성되었다고 하며, 언론사인 뉴욕 타임즈에서도 Gizmo라는 API 백엔드 서비스를 Go를 이용해 만들어 그 소스를 GitHub에 공개한 바 있고, SpaceX에서도 원격 측정 프로그램에서 Go를 사용한다고 한다. 또한 이더리움의 메인 클라이언트인 Geth 역시 Go로 작성되었고, Discord 또한 2020년 기준 최근 Rust로 교체 전까지는 서버와 클라이언트단 언어에 Golang을 채택하고 있었다. 즉 Go는 이미 시장에서 인정받은, 안정성이 검증된 언어라고 할 수 있다.

pkg.go.dev[17]이라는 Go 패키지 호스팅 사이트도 존재한다.

 

(추가2)

- 하기 내용 출처: 

  https://namu.wiki/w/Go(%ED%94%84%EB%A1%9C%EA%B7%B8%EB%9E%98%EB%B0%8D%20%EC%96%B8%EC%96%B4)#s-5

 

   Go 언어의 설계 지향점은 시스템 프로그래밍 언어였지만, 가비지 컬렉션의 지원이나 제네릭의 부재로 인해 박싱/언박싱이 불필요하게 많이 일어나는 등 C/C++을 대체할 수 있는 언어는 아니라는 것에 합의가 이루어지고 있는 상황이다. 실제로 고성능 연산에 사용하기에는 C/C++에 비해 느리며, 저수준 시스템 개발에서는 가비지 컬렉션과 고루틴을 지원하기 위한 무거운 런타임 등으로 인해 사용이 불가능에 가깝다. 그런 이유로 대체로 개발 속도와 실행 속도, 병행성 사이의 적정 지점이 필요한 서버 애플리케이션 개발에 많이 사용되는 편.

 

본 게시물은,

   계속 업데이트 할 예정입니다.


## go 에서 사용되는 환경변수
|변수명|설명|예시|
|:---|:---|:---|
|GOROOT|go SDK가 설치된 경로|C:\go|
|GOPATH|go 프로젝트 의존성 경로|C:\Users\{Username}\go|
|GOBIN|go 프로젝트 의존성 바이너리 경로|C:\Users\{Username}\go\bin|

## GOBIN 오류
go install cannot install cross-compiled binaries when gobin is set 과 같은 오류 발생시 GOBIN 환경변수를 제거해주면 해결됩니다.

## GO 25 kewyorrds

* var
* const
* struct
* type
* continue
* break
* goto
* for
* range
* if
* else
* switch
* case
* return
* import
* package
* default
* func
* interface
* select
* defer
* go
* map
* chan
* fallthrough





## go언어 설치
  * sudo apt install golang-go

## 함수 도움말 보기 (go doc usage example)
```bash
yhseok@yhseok-n:~/go/src/tcp-exams/client$ go doc net/http ListenAndServe
package http // import "net/http"

func ListenAndServe(addr string, handler Handler) error
    ListenAndServe listens on the TCP network address addr and then calls Serve
    with handler to handle requests on incoming connections. Accepted
    connections are configured to enable TCP keep-alives.

    The handler is typically nil, in which case the DefaultServeMux is used.

    ListenAndServe always returns a non-nil error.

yhseok@yhseok-n:~/go/src/tcp-exams/client$
```

```go
package main
 
//필요 패키지 임포트
import (
    "fmt"
    "log"
    "net/http"
    "strings"
)
 
func defaultHandler(w http.ResponseWriter, r *http.Request) {
    r.ParseForm()
    //Get 파라미터 및 정보 출력
    fmt.Println("default : ", r.Form)
    fmt.Println("path", r.URL.Path)
    fmt.Println("param : ", r.Form["test_param"])
    //Parameter 전체 출력
    for k, v := range r.Form {
        fmt.Println("key:", k)
        fmt.Println("val:", strings.Join(v, ""))
    }
    //기본 출력
    fmt.Fprintf(w, "Golang WebServer Working!")
}
 
func main() {
    //기본 Url 핸들러 메소드 지정
    http.HandleFunc("/", defaultHandler)
    //서버 시작
    err := http.ListenAndServe(":9090", nil)
    //예외 처리
    if err != nil {
        log.Fatal("ListenAndServe: ", err)
    } else {
        fmt.Println("ListenAndServe Started! -> Port(9090)")
    }
}
```



* godoc 을 사용하려면 다음을 설치한다.
  * sudo apt install golang-golang-x-tools

## PlantUML
* PlantUML theme
  * https://plantuml.com/ko/theme

* PlantUML theme from the internet can be included like this
  1. toy theme
     ```
     !include https://raw.githubusercontent.com/future-architect/puml-themes/master/themes/puml-theme-toy.puml
     
     ```
      ```plantuml
      @startuml
      !include https://raw.githubusercontent.com/future-architect/puml-themes/master/themes/puml-theme-toy.puml
      Alice -> Bob: Authentication Request

      alt successful case

          Bob -> Alice: Authentication Accepted

      else some kind of failure

          Bob -> Alice: Authentication Failure
          group My own label
          Alice -> Log : Log attack start
              loop 1000 times
                  Alice -> Bob: DNS Attack
              end
          Alice -> Log : Log attack end
          end

      else Another type of failure

        Bob -> Alice: Please repeat

      end
      @enduml
      ```     
