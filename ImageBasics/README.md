## Image Basics

- [fuse Image](https://www.fusetools.com/docs/fuse/controls/image)

```ux
<App>
	<DockPanel>
		<StatusBarBackground Dock="Top"/>
		<BottomBarBackground Dock="Bottom" />

		<Image File="Assets/logo.png" />
		<Image Url="https://s-media-cache-ak0.pinimg.com/736x/da/af/73/daaf73960eb5a21d6bca748195f12052--lion-photography-lion-kings.jpg" />
	</DockPanel>
</App>
```

`Url`과 `File`경로를 이용해서 이미지를 올릴 수 있다.

### StretchMode
이미지 크기를 결정하는 것이다.

```ux
<Image File="Assets/logo.png" StretchMode="Uniform" />
```
- [Fuse](https://www.fusetools.com/docs/fuse/controls/image/stretchmode)

### StretchDirection
이미지를 공간에 맞게 더 크게 혹은 더 작게 채우는 기능이다.

```ux
<Image File="Assets/logo.png" StretchMode="Uniform" StretchDirection="Both" />
```

### ContetnAlignmetn
위치를 지정한다.
```ux
<Image File="Assets/logo.png" ContentAlignment="Right" StretchMode="Uniform" />
```

### 이미지를 넣는 다양한 방법
```ux
<FileImageSource File="Assets/logo.png" ux:Global="testpattern" />
<Image Source="testpattern" />
```
```ux
<Image>
  <FileImageSource File="Assets/logo.png"/>
</Image>
```

### 여러개의 이미지 넣기
```ux
<FileImageSource File="Assets/logo.png" ux:Global="testpattern" />
<StackPanel>
  <Image Source="testpattern" />
  <Image Source="testpattern" />
</StackPanel>
```

### Displaying a multi-density image from files
```ux
<Image Width="256" Height="128">
  <MultiDensityImageSource>
    <FileImageSource File="Assets/logo.png" Density="1" />
    <FileImageSource File="Assets/logo@2x.png" Density="2" />
  </MultiDensityImageSource>
</Image>
```
