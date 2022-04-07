# 💿  CloneDeep
## Vanilla JS로 모든 객체에 대응 가능한 DeepClone Method 구현하기
<!-- ## Use Vanilla JS to implement Deep Clone Method capable of all Object -->
<br/><h2 align='center'>Q : JavaScript의 Object는 깊은복사일까?<br/><br/>A</h2>


```css
JS는 데이터를 저장하기 위한 별도의 메모리 공간을 확보하여 저장하고, 그 주소를 변수영역에 저장합니다.  
즉, 데이터의 성질에 따라 변수와 데이터 저장공간을 구분한다고 볼 수 있다. 

변수영역과 데이터 영역을 따로 구분하게 된다면 데이터 변환을 자유롭게 할 수 있고,   
메모리를 효율적으로 관리할 수 있는 등의 이점이 있기 떄문에 변수 영역에 값을 직접 대입하지 않고 한 단계를 더 거쳐 주소값을 복사하는 이유이다.

데이터 영역의 메모리는 모두 불변값이다. 그러나 변수에는 다른 값을 얼마든지 대입할 수 있다.  
이 부분부터 깊은복사가 이루어지지 않는 것에 대한 의문과 혼란이 생기기 시작되는 시점인 것 같다.

모든 데이터타입은 참조형이기는 하지만 기본형은 주소를 복사하는 과정이 한번만 이루어지는 것이고,   
참조형은 객체안에 (예: 여러개의 프로퍼티로 이뤄진 데이터 그룹) 변수 영역이 존재하기 때문에 한단계 더 거치는 것이다.

객체의 데이터 영역의 주소 자체를 변경하고자 한다면 새로운 주소에 값을 만든 후, 다시 연결함으로써 다시 값을 할당할 수 있고,   
내부 프로퍼티를 변경하는 경우에는 객체의 데이터 영역은 변경되지 않고 객체의 변수 영역이 변경되는 것이다.  
즉, 새로운 객체가 만들어진 것이 아니라 기존의 객체 내부의 값만 바뀐 것이다.  
그러므로 여전히 처음 객체의 데이터영역의 주소는 변경되지 않고 있기 때문에 깊은복사가 이루어지지 않는다.  

이러한 문제를 해결하기 위해 구글링하다보면 Lodash, JSON 등등 몇가지 방법이 제시되고 있는데 JSON 같은 경우는   
완벽한 깊은복사에 대응하지 못한다.  
Lodash같은 라이브러리를 사용하더라도 deep clone의 과정을 이해하지 못하면 Object를 자유롭게 다루지 못할 것 같아 직접 구현해보기로 했다.
```
<br/>

## ⚙️ Environment

> TypeScript Version v4.6.3 (Mac)
>
> Node Version v17.7.1
>
> Npm Version v8.5.2
>
> MacOS Monterey Version 12.3
<br/>

## 🛠 Usage

```javascript
$ cd src
$ ts-node index.ts
```

**Test Code 실행** 

```javascript
$ npm run test
```
