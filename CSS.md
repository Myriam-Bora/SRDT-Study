# 미디어쿼리 Media query

- 화면 해상도, 기기(화면크기)등의 조건에 따라 스타일을 전환할수 있는 속성
- 사용자가 보이는 화면 즉, ***<u>뷰포트에 따라 결정된다</u>***



## 기본 문법 

```html
@media [only 또는 not][미디어 유형][and 또는 ,](조건문){실행문}
```

- only : 미디어쿼리를 지원하는 브라우저에서만 미디어 쿼리를 해석하게 해주는 키워드
- not :  not 다음에 따라오는 조건을 부정하는 키워드. 예) not tv : tv를 제외한 모든 미디어 유형에 적용

- 미디어 유형은 생략이 가능하여 생략 시 all 키워드로 작동

|   기기명   |                           설명                           |
| :--------: | :------------------------------------------------------: |
|    all     |                        모든 장치                         |
|   print    |                        인쇄 장치                         |
|   screen   |         컴퓨터 화면 장치 또는 스마트 기기의 화면         |
|     tv     |            영상과 음성이 동시에 출력되는 장치            |
| projection |                      프로젝터 장치                       |
|  handheld  |                손에 들고 다니는 소형 장치                |
|   speech   |                      음성 출력 장치                      |
|   aural    |   음성 합성 장치 (화면을 읽어 소시로 출력해 주는 장치)   |
|  embossed  | 점자 인쇄 장치 (화면을 읽어 종이에 점자를 찍어내는 장치) |
|    tty     |              디스플레이 기능이 제한된 장치               |
|  braille   |                      점자 표시 장치                      |

- and : 앞뒤 조건이 모두 true 일 때 따라오는 것을 해석 (생략 가능)
- , 콤마 : 앞뒤 조건 중 하나만 true 인 경우 해석 (생략 가능)
- 조건문 (생략 가능)
  - min : 최소, 즉 이상
  - max : 최대, 즉 이하

|       조건문        |              설명               |                            조건값                            | min/max 사용 여부 |
| :-----------------: | :-----------------------------: | :----------------------------------------------------------: | :---------------: |
|        width        |     웹 페이지의 가로 너빗값     |              width에서 사용가능 한 모든 속성 값              |       사용        |
|       height        |     웹 페이지의 세로 높잇값     |              width에서 사용가능 한 모든 속성 값              |       사용        |
|    device-width     |       기기의 가로 너빗값        |              width에서 사용가능 한 모든 속성 값              |       사용        |
|    device-height    |       기기의 세로 너빗값        |              width에서 사용가능 한 모든 속성 값              |       사용        |
|     orientation     |        기기의 화면 방향         |             portrait(세로)<br />landscape(가로)              |         X         |
|    aspect-ratio     |            화면 비율            | 브라우저 화면 비율(1), <br />브라우저 종황비(16/9), <br />브라우저 해상도(1280/720) |       사용        |
| device-aspect-ratio |       단말기의 화면 비율        | 기기 화면 비율(1), <br />기기 종황비(16/9), <br />기기 해상도(1280/720) |       사용        |
|        color        |         기기의 비트 수          |                         8(bit 단위)                          |       사용        |
|     color-index     |         기기의 색상 수          |                      128(색상 수 단위)                       |       사용        |
|     monochrome      | 기기가 흑백일 때 픽셀당 비트 수 |                         1(bit 단위)                          |       사용        |
|     resolution      |          기기의 해상력          |                         300dpi/dpcm                          |       사용        |
|        scan         |         TV의 스캔 방식          |                    progressive/interlace                     |         X         |
|        grid         |      기기의 그리드/비트맵       |                0(비트맵 방식)/1(그리드 방식)                 |         X         |



------

## 미디어 쿼리 사용 시 주의 사항

### 띄어쓰기에 주의

- 예) @media all and (min-width:320px){ }  : and과 (min-width:320px) 사이에 띄어쓰기!

### min/max 작성 순서

- min : 크기가 작은 순서대로 작성
- max : 크기가 큰 순서대로 작성

```html
<style>
    //화면의 크기가 500픽셀일 때
    @media (width:500px){
        body{
            background-color:blue;
        }
    }
    //화면의 크기가 500픽셀 이하 일 때
    @media (max-width:500px){
        body{
            background-color:blue;
        }
    }
    //화면의 크기가 500픽셀 이상 일 때
    @media (min-width:500px){
        body{
            background-color:blue;
        }
    }
    
    //~500px: red , 501~600px:green , 601px~:blue 일 떄
     @media (max-width:600px){  //1)순서 주의!
        body{
            background-color:blue;
        }
    }
     @media (max-width:500px){ //2)순서 주의! :2)번 코드가 더 나중에 실행되기 때문
        body{
            background-color:blue;
        }
    }
     @media (min-width:601px){
        body{
            background-color:blue;
        }
    }
  
</style>
```

------

# 뷰포트

- 화면에서 실제 내용이 표시되는 영역
  - 데스크톱 : 해상도
- 반응형 웹을 제작할 때 사용하는 뷰포트의 기본 메타 태그

```html
<meta name="viewport" content="width=device-width, initial-scale=1, minimum-scale=1, maximum-scale=1, user-scalable=no">
```

- 뷰포트 속성

|    속성명     |       속성값        |                          속성 설명                           |
| :-----------: | :-----------------: | :----------------------------------------------------------: |
|     width     | device-width , 양수 |                     뷰포트의 너비를 지정                     |
|    height     | device-height, 양수 |                     뷰포트의 너비를 지정                     |
| initial-scale |        양수         | 뷰포트의 초기 배율을 지정한다<br />기본값1. 1보다 작은 값을 사용하면 축소된 페이지를 표시<br />1보다 큰 값을 사용하면 확대된 페이지를 표시 |
| user-scalable |       yes, no       | 뷰포트의 확대/축소 여부를 지정<br />기본값은 yes<br />no를 설정하면 사용자가 페이지를 확대할 수 없다 |
| minimum-scale |        양수         |       뷰포트의 최소 축소 비율을 지정<br />기본값 0.25        |
| maximum-scale |        양수         |        뷰포트의 최대 확대 비율을 지정<br />기본값 5.0        |



------

# 가변 그리드 %

- 가변 크기의 & 값 = ( 가변으로 만들 박스의 가로 / 박스를 감싸고 있는 박스의 가로 ) * 100
- 가변 크기로 변환하여 값을 적용한 소스코드에는 사용한 공식을 주석으로 작성한다

## 

# 가변 폰트

- em 단위 : 대문의 M의 너비를 1em으로 표현한 것
  - 16px = 1em
- 최신 브라우저는 픽셀 단위를 사용해도 축소,확대가 가능하다
- 가변 폰트 값 = 가변폰트를 적용할 글자 크깃값 / 적용할 요소를 감싸고 있는 요소의 글자 크깃값
