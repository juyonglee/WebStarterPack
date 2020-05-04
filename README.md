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
 