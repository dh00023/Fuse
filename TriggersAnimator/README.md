# Trigger and Animator

Triggers는 상호작용에 있어서 main tool이다.( transitions and animation)
Triggers는 objects이다.
- detect events, gestures, other user input or changes of state in your app
- performs animations and actions in response


```
<App>
	<DockPanel>
		<StatusBarBackground DockPanel.Dock="Top" />

		<Rectangle TransformOrigin="TopLeft" Width="100" Height="100" Fill="#000" CornerRadius="10">
			<WhilePressed>
				<Scale Factor="1.5" Duration=".4" DurationBack="1.0" Easing="BounceOut" EasingBack="BounceIn"/>
				<Rotate Degrees="45" />
				<Move X="50" Y="20" />
			</WhilePressed>
		</Rectangle>
	</DockPanel>
</App>
```
- `WhilePressed`는 누르고 있는동안 적용된다.
- `WhileHovering`은 마우스가 그 위에 있으면 적용된다.


- `Scale`은 크기를 변경시켜준다.
	- `Factor`는 크기를 지정한다.
	- `Duration`은 그 효과가 실행되는 시간을 정할 수 있다.
	- `Easing` 은 자연스럽고 표현력있는 효과를 보여줄 때 사용한다. [[속성](https://www.fusetools.com/docs/fuse/animations/easing)]
- `Rotate`는 회전을 시킨다. `Degrees`속성은 얼마나 회전할지 각도를 정해줄 수 있다.
- `Move`는 X와 Y만큼 각각 가로 세로 방향으로 움직일 수 있다.

- `Rectangle`의 [`TransformOrgin`속성](https://www.fusetools.com/docs/fuse/elements/element/transformorigin)은 구체적으로 어떻게 바꿀지 정할 수 있다.


```
<App>
	<DockPanel>
		<StatusBarBackground DockPanel.Dock="Top" />

		<StackPanel>
			<Button />
			<Rectangle Width="100" Height="100" Fill="#000" CornerRadius="10">
				<WhilePressed>
					<Scale Factor="1.5"></Scale>
				</WhilePressed>
			</Rectangle>
			<Button />
		</StackPanel>
	</DockPanel>
</App>
```
결과를 확인해보면 주위의 elements나 layout에는 영향을 미치지 않는 것을 볼 수 있다. 하지만 `Rectangle`의 `width`나 `Height`는 layout에 영향을 미치는 것을 확인할 수 있다.


```
<App>
	<DockPanel>
		<StatusBarBackground DockPanel.Dock="Top" />
		<StackPanel Orientation="Horizontal" Alignment="Center">
			<Rectangle Width="100" Height="100" Fill="#000" CornerRadius="10">
				<WhileHovering>
					<Scale Target="GreyRectangle" Factor="1.5" Duration=".4" DurationBack="1.0" Easing="BounceOut" EasingBack="BounceIn"/>
					<!-- <Rotate Degrees="45" />
					<Move X="50" Y="20" />-->
				</WhileHovering>
			</Rectangle>
			<Rectangle ux:Name="GreyRectangle" Width="100" Height="100" Fill="#ccc" CornerRadius="10" Margin="10,0,0,0"/>
		</StackPanel>
	</DockPanel>
</App>
```
- `ux:Name`으로 이름을 지정할 수 있다.
- `Target`으로 애니메이션 효과를 한 대상에 지정할 수 있다.