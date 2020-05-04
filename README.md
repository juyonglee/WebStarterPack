# 5.단위, 배경, 박스모델
## 5.1. boxmodel
![Boxmodel Image](https://github.com/juyonglee/WebStarterPack/blob/master/Images/Boxmodel.png)

HTML의 모든 요소는 **사각형의 박스 형태**로 만들어집니다. 박스는 총 4가지의 세분된 영역으로 구성되어있으며 영역마다 다양한 스타일을 적용할 수 있습니다.

1. Content 영역
    
    요소의 실제 내용을 포함하는 영역입니다. 따라서 크기는 내용의 너비 및 높이를 나타냅니다.

2. Border 영역

    content 영역을 감싸는 테두리 선을 border라고 합니다.

3. Padding 영역
    
    - content 영역과 테두리 사이의 여백을 padding이라고 합니다.
    - padding을 content의 연장으로 볼 수도 있습니다.

3. Margin 영역

    - border 바깥쪽의 영역을 margin이라고 합니다. 
    - border 영역을 다른 요소와 구별하기 위해 쓰이는 빈 영역입니다.
    - 즉, 주변 요소와의 여백(간격)을 margin을 이용해 지정할 수 있습니다.

<hr>

## 5.2. border
border 속성은 요소의 **`테두리`** 에 관련된 속성을 지정할 때 사용합니다. 테두리의 굵기, 모양, 색상을 지정할 수 있는 속성들이 있습니다.

### border 관련 속성
1. border-width: 선의 굵기를 지정하는 속성
    - Default Value: `medium`
    - border-top-width
    - border-bottom-width
    - border-right-width
    - border-left-width
    ```css
    border-width: [top] [right] [bottom] [left];
    ```

2. border-style: 선의 모양을 지정하는 속성
    - Default Value: `none`
    - border-top-style
    - border-bottom-style
    - border-right-style
    - border-left-style
    ```css
    border-style: [top] [right] [bottom] [left];
    ```

3. border-color
    - Default Value: `currentColor`
        - CSS3에서 도입된 개념으로 currentColor가 설정되면, color가 상속됩니다.
    - border-top-color
    - border-bottom-color
    - border-right-color
    - border-left-color
    ```css
    border-color: [top] [right] [bottom] [left];
    ```
### border 축약
```css
border: [-width] [-style] [-color];
```
`공백`으로 구분해 축약하여 사용할 수 있고, 정의되지 않은 속성값에 대해서는 기본값이 적용됩니다.
 
### border 예제
![Border Style Example](https://github.com/juyonglee/WebStarterPack/blob/master/Images/BorderStyle.png)

<hr>

## 5.3. Padding
padding 영역은 border와 content 사이의 여백입니다. 속성의 순서는 고정되어있으며, 위쪽을 기준으로 `시계방향`으로 돌아간다고 생각하면 쉽습니다. 또한 padding의 기본 값은 `0`입니다.
1. padding-top
2. padding-right
3. padding-bottom
4. padding-left 

```css
padding: [-top] [-right] [-bottom] [-left];
            /* [Case1] 상, 우, 하, 좌 다른 경우 */
            0      10px     20px      30px
            /* [Case2] 좌, 우 같은 경우 */
            0      10px     20px
            /* [Case3] 상, 하 & 좌, 우 같은 경우 */
            0      10px
            /* [Case4] 상, 우, 하, 좌 모두 같은 경우 */
            0                                
```

<hr>

## 5.4. Margin
margin은 border 영역을 다른 요소와 구별하기 위해 쓰이는 빈 영역입니다..
즉, 이 말은 다른 요소와의 **`간격`** 을 만들 수 있다는 것입니다. 

### margin 속성
- Value
    - length
    - percentage
    - `auto` 
        - block 너비의 %를 사용합니다. 
        - 이를 활용하여 `수평 중앙 정렬`을 할 수 있습니다.
- margin-top border
- margin-right border
- margin-bottom border
- margin-left border

### syntax
```css
margin: [-top] [-right] [-bottom] [-left];
        /* [Case1] 상, 우, 하, 좌 다른 경우 */
        0      10px     20px      30px
        /* [Case2] 좌, 우 같은 경우 */
        0      10px     20px
        /* [Case3] 상, 하 & 좌, 우 같은 경우 */
        0      10px
        /* [Case4] 상, 우, 하, 좌 모두 같은 경우 */
        0
```

### 주의점!!
좌우의 margin이 모두 auto로 적용 되었다면, 브라우저는 요소가 가질수 있는 `가로 영역`에서 자신의 width를 제외한 `나머지 여백에 크기에 대해 균등 분할` 하여 적용합니다. 이에 따라 요소는 수평 중앙 정렬이 됩니다. 상하의 경우 수직 중앙 정렬이 되지 않으며, 기본적인 플로우를 벗어나는 상황에 대해서 적용이됩니다.

### margin collapse
마진 병합은 인접한 두 개 이상의 `수직 방향 박스`의 마진이 하나로 합쳐지는 것을 의미합니다. 마진 병합이 다음 세가지의 경우에 일어납니다.

1. 두 요소가 상하로 인접한 경우: 위 요소의 하단 마진과 아래 요소의 상단 마진의 병합이 일어납니다.
2. 부모 요소와 첫 번째 자식 요소 또는 마지막 자식 요소
    - 부모 요소의 상단 마진과 첫 번째 자식 요소의 상단 마진 병합이 일어납니다.
    - 부모 요소의 하단 마진과 마지막 자식 요소의 하단 마진 병합이 일어납니다.
3. 내용이 없는 빈 요소의 경우: 해당 요소의 `상단 마진`과 `하단 마진`의 병합이 일어납니다.

*`마진 병합은 수직 방향으로만 이루어지며, 좌우에 대해서는 일어나지 않습니다.`*
마진 병합은 마진이 반드시 맞닿아야 발생하기 때문에 2,3번째의 경우 padding 및 border가 없어야 합니다.
