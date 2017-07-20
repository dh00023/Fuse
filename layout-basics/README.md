# Fuse

### 앱 생성
```
$ fuse create app <projectname> [optional path]
```

fuse는 `one .ux` file이 포함되어있어야한다. `MainView.ux`가 디폴트 값이다.

### Running App

```
$ fuse preview
```

USB를 연결해서 핸드폰이나 테블릿에서 실행할 수 있다.
```
$ fuse preview -tios
$ fuse preview -tandroid
```
처음 연결할 때, preview app을 설치해야한다. 처음 설치한 후에는 다시 설치하지 않아도 된다.


### 기본시작

SublimeText와 Atom에서 fuse plugin을 제공해준다.

```ux
<!-- MainView.ux -->
<App>
</App>
```

`MainView.ux`는 이와 같이 `<App>`태그가 있어야한다.

### Rectangle

```
<App>
	<Rectangle Fill="Black" Width="100" Height="100" Alignment="Default"/>/>
</App>
```
#### Width & Height
실행창을 확인해보면 화면이 검정색으로 바뀐걸 확인할 수 있다. `Width`와 `Height`로 높이와 너비를 지정할 수 있다.
- 숫자만 적용하면 각각 devise의 pixel과 상관없이 같은 크기로 나타나는 것을 확인할 수 있다.
- `px`를 뒤에 붙여주면 화면 크기에 따라 크기가 변경된다.
- `%`는 화면의 비율에 맞게 적용된다.

#### Alignment
위치를 지정해준다. Default값은 Center이다.
- [Alignment 속성](https://www.fusetools.com/docs/fuse/elements/element/alignment)

```
<Rectangle Fill="Black" Margin="10"></Rectangle>
```
#### Margin
margin을 설정해준다. 순서대로 왼쪽,위,오른쪽,아래로 각각 지정할 수 있다.

### StackPanel
Fuse에는 여러가지 layout이 있다. StackPanel은 children을 수직이나 수평으로 쌓는 것을 의미한다.

```
<StackPanel Orientation="Horizontal">
	<Text>Some text</Text>
	<Button Text="the button"></Button>
	<Slider></Slider>
	<Switch></Switch>
</StackPanel>
```

#### Orientation
- Vertical : 세로
- Horizontal : 가로

### Text
텍스트는 항상 왼쪽위에서 시작한다.
```
<Text Alignment="Center">Some text</Text>
```
`Alignment`속성을 통해서 텍스트의 위치를 수정할 수 있다.
- [Text](https://www.fusetools.com/docs/fuse/controls/text)

```
<Text TextAlignment="Center" Margin="10">Some text</Text>
```
`TextAlignment`는 block형태이다.

### DockPanel
```
<DockPanel Padding="10">
	<Text Dock="Right">Some text</Text>
	<Button Text="the button" Dock="Top" Margin="10"></Button>
	<Slider Dock="Left"></Slider>
	<Switch></Switch>
</DockPanel>
```
Children을 `Dock`속성을 통해 Left, Right, Top, Bottom 각각의 다른 방향으로 docking(결합)하는 것이다.