# 7. Layout
## 7.1. Display
모든 요소는 자기가 기본적으로 가지고 있는 `display 값`이 있습니다. 그리고 그 값에 따라 블록 레벨, 인라인 레벨 등 렌더링 박스의 유형이 결정됩니다.
display 속성으로 해당 요소의 렌더링 박스의 유형을 변경할 수 있으며 심지어 렌더링 여부도 결정할 수 있습니다.
display 속성을 잘 알아야 요소가 화면에 표현되는 방식을 이해하기 쉽습니다.
### display 속성
요소의 rendering box 유형을 결정하는 속성입니다. CSS를 활용하여 inline 요소를 block 요소처럼 또는 block 요소를 inline 요소처럼 나타낼 수 있다.
```css
display: value;
```

`기본 값` : - (요소마다 다름)

속성 값: 

- none: 요소가 렌더링 되지 않는다. 즉, 브라우저가 `Render Tree`를 만들지 않는다! 
- inline: inline level 요소처럼 렌더링
- block: block level 요소처럼 렌더링
- `inline-block`: inline level 요소처럼 렌더링(배치)되지만 block level의 성질을 가짐 `(height나 width 등과 같은 박스모델 속성을 적용할 수 있다.)`
 
inline level 요소 사이의 공백과 개행 처리 inline 요소의 경우 공백과 개행에 대해서 하나의 여백으로 받아들입니다. 따라서 inline와 inline-block의 경우 태그 사이의 공백이나 개행이 있을 경우 약 4px의 여백을 가지게 됩니다.
 
| display       | width | height | margin | padding | border |
| ------------- |:-----:| :----: | :----: | :-----: | :----: |
| block         |   O   |    O   |    O   |    O    |    O   |
| inline        |   x   |    x   |  좌/우  |    O    |    O   |
| inline-block  |   O   |    O   |    O   |    O    |    O   |

 ## 7.2. Visibility
CSS에서 요소를 숨기는 방법에는 몇 가지가 있습니다. display 속성에서 배웠듯이 아예 렌더링이 되지 않게끔 할 수도 있고, 다른 위치 관련 속성들을 이용해서 안 보이게 숨기는 방법도 있습니다. 하지만 요소를 숨긴다는 의미로만 해석하면 가장 명시적인 방법은 visibility 속성을 이용하는 것입니다.

### visibility 속성
요소의 화면 표시 여부를 지정하는 속성입니다. 
- `기본 값` : visible 
```csss
visibility: visible | hidden | collapse | initial | inherit;
```
**속성 값**
- visible: 화면에 표시
- hidden: 화면에 표시되지 않음 `(공간은 차지함)`. 즉, 자신의 박스 영역은 유지(margin까지 모두 포함)
- collapse: 셀 간의 경계를 무시하고 숨김 `(테이블 관련 요소에만 적용 가능)`. 즉, 박스영역 없으며 `테이블의 행과 열 요소`에만 지정 가능, 그 외 요소 지정은 hidden과 같음.

### display: none과 차이점
- `display: none`: 요소가 `렌더링 되지 않음` (DOM에 존재하지 않음)
- `visibility: hidden`: 요소가 보이지는 않지만 렌더링 되며 화면에 `공간을 가지고 있음 (DOM에 존재함)`

<hr>

## 7.3. float
모든 요소는 기본적으로 보통의 흐름에 따라 `위에서 아래`로, 그리고 `좌측에서 우측`으로 배치됩니다.
요소 박스의 경계대로 차례대로 배치되며 float 속성은 요소를 보통의 흐름에서 벗어나 `독자적인 공간 위에 배치되게 됩니다`.

`Layout을 좌, 우로 분할할때 사용한다.`

### float 속성
요소를 float `(요소를 보통의 흐름에서 벗어나게 함)` 시킬지 지정하는 속성입니다.
- `기본 값` : none
```css
float: none | left | right | initial | inherit;
```
**속성 값**
- none: float 시키지 않음(기본값)
- left: 좌측으로 float 시킴
- right: 우측으로 float 시킴

요소를 보통의 흐름에서 벗어나 띄어지게 함
주변 텍스트나 인라인 요소가 주위를 감싸는 특징이 있음
대부분 요소의 display 값을 block으로 변경함