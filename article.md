This article provides a detailed explanation and analysis of developing a PLAY button inspired by the game "League of Legends" using pure WPF technology.
This article provides a detailed explanation and analysis of developing a PLAY button inspired by the game "League of Legends" using pure WPF technology. It emphasizes the process of leveraging WPF features to create a versatile user interface component and offers a new perspective on open-source development. The article also explores advanced WPF features like animations and triggers to enhance the user interaction experience.
This is a new version of the currently published article.
Abstract:
Image 1

This article provides a detailed explanation and analysis of developing a PLAY button inspired by the game "League of Legends" using pure WPF technology. It emphasizes the process of leveraging WPF features to create a versatile user interface component and offers a new perspective on open-source development. The article also explores advanced WPF features like animations and triggers to enhance the user interaction experience.

Image 2

We have turned the content of this article into an instructional video and posted it on YouTube, where everyone can practice along with the video.

Youtube：League of Legends PlayButton- WPF Project 
GitHub：League of Legends PLAY Button - WPF Project
GitHub：League of Legends Full Project-WPF


Introduction:
User interface components are crucial for enhancing the user experience. In games, a responsive and visually appealing PLAY button serves as the gateway to the world of entertainment. This article showcases the process of creating a PLAY button using WPF, which provides a powerful framework for building rich desktop applications.

Project Background:
The project discussed in this article aims to demonstrate the capabilities of WPF technology as comprehensively as possible. We released this project a few years ago and received a tremendous positive response, which has continued to motivate us to contribute to open-source development. While .NET technologies evolve, we are continually updating and refining the code previously shared on GitHub. Given the extensive content covered by this overall project, we decided to break it down and provide a detailed analysis of each part's composition and technical focus, hoping to assist more WPF enthusiasts in their learning journey.

Button Composition:
Image 3

By using an analyzer , we can see that this PLAY button inherits properties from WPFToggleButton. On the left side, there's a logo from the "League of Legends" game, while the right side comprises multiple elements such as Borders, images, and text with different designs. Additionally, interactive mouseover and checked trigger effects are added.

Key Content Analysis:
1. Creating Irregular Shapes:

Image 4

The first two graphics can be easily encoded using Border controls. However, the third graphic, which includes a pointed end and an arc, cannot be encoded using a simple Border. Therefore, our initial thought might be to use a Polygon and coordinates for drawing. Still, the Polygon property cannot provide functionality for drawing arcs. Hence, we should use the Path control for encoding.

Detailed Analysis:

XAML
<Style TargetType="{x:Type Path}" x:Key="Arrow">
    <Setter Property="Fill" Value="#1E2328"/>
    <Setter Property="Stroke" Value="{StaticResource ArrowStroke}"/>
    <Setter Property="StrokeThickness" Value="2"/>
    <Setter Property="Data" Value="M 0,0 L 103,0 L 118,14 L 103,28 L 0,28 C 10,14 0,0 0,0 Z"/>
    <Setter Property="Margin" Value="40 5 4 -5"/>
    <Setter Property="Effect">
        <Setter.Value>
            <DropShadowEffect BlurRadius="5" ShadowDepth="2"/>
        </Setter.Value>
    </Setter>
</Style>

In WPF, the Path control is a powerful tool for drawing various shapes and outlines. The Path control uses path data to define shapes, and path data consists of a series of commands and coordinates that specify how to draw the shape.

       Its fundamental properties include:

Data Property: The Data property is a crucial attribute of the Path control, used to specify path data, which consists of a series of commands and coordinates to describe the outline of a shape. The format of path data includes various commands such as MoveTo (M), LineTo (L), CurveTo (C), ClosePath (Z), etc., combined with coordinates to define shapes. By providing path data in the Data property, we can create various shapes, including line segments, curves, polygons, and more.

Fill Property: The Fill property is used to specify the fill color inside a shape. It allows us to use colors, gradients, patterns, or transparency to fill the interior of a shape.

Stroke Property: The Stroke property is used to specify the color of the outline of a shape. It allows you to define the color of the outline lines using various colors.

StrokeThickness Property: The StrokeThickness property is used to specify the thickness of the outline lines. It determines the width of the outline.

Commands and Coordinates: Path data consists of a series of commands and coordinates, where these commands instruct WPF on how to draw shapes from one point to another. Common path commands include:

M (MoveTo): It moves the drawing point to the specified coordinates.
L (LineTo): It draws a straight line to the specified coordinates.
C (CurveTo): It draws a Bézier curve, using control points to define the curve's shape.
Z (ClosePath): It closes the path, connecting the current point to the starting point, forming a closed shape.
The Data property is a critical attribute of the Path control, used to specify path data that includes commands and coordinates for defining the shape's outline. Path data employs a series of commands to describe the contour of a path. Here is a detailed explanation of the commands and coordinates in the path data for the project:

Image 5

We can simply interpret this as X/Y coordinate axes. We set the length of this shape to be 118, and the width to be 28:

M 0,0: This is a "MoveTo" command, which moves the drawing point to the coordinates (0, 0), representing the starting point.

L 103,0: This is a "LineTo" command, which draws a straight line from the current point (0, 0) to the coordinates (103, 0). Subsequently, it continues to draw lines to (118, 14), (103, 28), and (0, 28).

Since this is a symmetrical shape, the Y-coordinate of the second line is half the total height of the shape: 14.

Next is the part for drawing curves: C 10,14 0,0 0,0 z: This is a "Bezier Curve" command, defining a Bézier curve where the preceding points are control points, and the subsequent point is the endpoint. This command defines a Bézier curve with control point (10, 14) and endpoint (0, 0), and it uses the 'z' command to close the path by connecting it to the starting point (0, 0).

2. Creating Gradient Colors:

XAML
 <LinearGradientBrush x:Key="ArrowStroke" StartPoint="0.5,0" EndPoint="0.5,1" >
      <GradientStop Color="#CC3FE7EE" Offset="0"/>
      <GradientStop Color="#CC006D7D" Offset="0.5"/>
      <GradientStop Color="#CC0493A7" Offset="1"/>
 </LinearGradientBrush>

 <LinearGradientBrush x:Key="ArrowStrokeOver" StartPoint="0.5,0" EndPoint="0.5,1" >
      <GradientStop Color="#FFAFF5FF" Offset="0"/>
      <GradientStop Color="#FF46E6FF" Offset="0.5"/>
      <GradientStop Color="#FF00ADD4" Offset="1"/>
 </LinearGradientBrush>

 <LinearGradientBrush x:Key="ArrowFillOver" StartPoint="0.5,0" EndPoint="0.5,1" >
      <GradientStop Color="#FF1D3B4A" Offset="0"/>
      <GradientStop Color="#FF082734" Offset="1"/>
 </LinearGradientBrush>
In this section of the game, the stroke part is not a simple solid color but a gradient color composed of multiple hues. To achieve this effect, we can utilize LinearGradientBrush for customizing colors.

   Key Properties and Usage of LinearGradientBrush:

Image 6

StartPoint and EndPoint:
StartPoint specifies the gradient's starting point, typically represented using relative coordinates, where (0, 0) is the top-left corner, and (1, 1) is the bottom-right corner. EndPoint specifies the gradient's ending point, also using relative coordinates.
GradientStops:
GradientStops is a collection of GradientStop objects, each defining a color and a relative position (Offset). The Color property of GradientStop defines the color at the specified position, and the Offset property defines the color's position in the gradient, typically ranging from 0 to 1.
Gradient Direction:
The gradient's direction is determined by StartPoint and EndPoint. For example, if StartPoint is (0, 0) and EndPoint is (1, 1), the gradient will transition from the top-left corner to the bottom-right corner.
Gradient Type:LinearGradientBrush defaults to linear gradient, where colors transition along a straight line. By adjusting StartPoint and EndPoint, you can change the gradient's direction and starting point to create various gradient effects.
In this project, we aim to create a vertical gradient starting from the center of the shape and moving downwards. Therefore, we set StartPoint to (0.5, 0), indicating that the gradient's starting point is at the top center (horizontal midpoint). EndPoint is set to (0.5, 1), indicating that the gradient's ending point is at the bottom center (horizontal midpoint).

Image 7

Next, the GradientStops collection includes three GradientStop objects, each defining different colors and relative positions：

The third GradientStop:
Color is set to #CC3FE7EE, representing a color value.
Offset is set to 0, indicating that this color is located at the starting point of the gradient.
The second GradientStop:
Color is set to #CC006D7D.
Offset is set to 0.5, indicating that this color is located at the midpoint of the gradient.
The third GradientStop:
Color is set to #CC0493A7.
Offset is set to 1, indicating that this color is located at the ending point of the gradient.

3. Handling Path and Border for Thickness:

Image 8

In the Border control:

The borderlines of a Border control are contained within the Border itself. The thickness of the borderlines is controlled by the BorderThickness property, specifying the width of the borderlines in device-independent pixels (DIPs).
In the Path control:

The borderlines of a Path control are drawn based on the StrokeThickness property's center position. StrokeThickness controls the thickness of the borderlines, representing the distance by which the borderlines extend from the center.
   

In this fixed-size graphic, both Border and Path have their thickness set to 2, and Margin is set to 4 4 4 4. However, this setup reveals that the upper border of the Path extends beyond the Border.

Therefore, adjustments are needed in the Margin of the Path considering StrokeThickness. The left Margin is already set to 40, which can cover the GreenLine, so there's no issue. The top Margin should be increased by 1 pixel, set to 5 pixels, while the right and bottom Margins need no change. Since the Path has a fixed size of 118x28, only the left and top Margins need adjustment.

 Additionally, since the top Margin increases by 5 pixels, the bottom may appear cut off, as in this situation. To prevent this, you can set the bottom Margin to -5 pixels. This balances the layout by removing the 5 pixels added at the top. Another approach is to keep the bottom Margin at 0 pixels. Both methods prevent the bottom from being cut off due to the added top Margin.

4. Creating Animations Using Jamesnet.WPF Nuget:
 

XAML
Shrink ▲   
<Application x:Class="VickyPlayButton.App"
             xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
             xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
             xmlns:james="https://jamesnet.dev/xaml/presentation"
             StartupUri="MainWindow.xaml">

    <Application.Resources>
        <Style TargetType="{x:Type ToggleButton}">
            <Setter Property="Height" Value="38"/>
            <Setter Property="Width" Value="165"/>
            <Setter Property="Foreground" Value="#FFFFFF"/>
            <Setter Property="Background" Value="Transparent"/>
            <Setter Property="Template">
                <Setter.Value>
                    <ControlTemplate TargetType="{x:Type ToggleButton}">
                        <ControlTemplate.Resources>
                            <Storyboard x:Key="Checked">
                                <james:ThickItem Mode="CubicEaseInOut" TargetName="play" Property="Margin" Duration="0:0:0:0.5" To="30 100 0 0"/>
                                <james:ThickItem Mode="CubicEaseInOut" TargetName="stop" Property="Margin" Duration="0:0:0:0.5" To="30 0 0 0"/>
                            </Storyboard>
                            <Storyboard x:Key="UnChecked">
                                <james:ThickItem Mode="CubicEaseInOut" TargetName="play" Property="Margin" Duration="0:0:0:0.5" To="30 0 0 0"/>
                                <james:ThickItem Mode="CubicEaseInOut" TargetName="stop" Property="Margin" Duration="0:0:0:0.5" To="30 0 0 100"/>
                            </Storyboard>
                        </ControlTemplate.Resources>
                        <Grid Background="{TemplateBinding Background}">
                            <Border Style="{StaticResource GoldLine}"/>
                            <Image Style="{StaticResource Emblem}"/>
                            <Border Style="{StaticResource GreenLine}"/>
                            <Path x:Name="path" Style="{StaticResource Arrow}"/>
                            <Grid>
                                <Grid.Clip>
                                    <RectangleGeometry Rect="0,5,165,28"/>
                                </Grid.Clip>
                                <TextBlock x:Name="play" Style="{StaticResource Play}"/>
                                <TextBlock x:Name="stop" Style="{StaticResource Stop}"/>
                            </Grid>
                        </Grid>
                        <ControlTemplate.Triggers>
                            <Trigger Property="IsMouseOver" Value="True">
                                <Setter TargetName="path" Property="Fill" Value="{StaticResource ArrowFillOver}"/>
                                <Setter TargetName="path" Property="Stroke" Value="{StaticResource ArrowStrokeOver}"/>
                                <Setter Property="Foreground" Value="#FFFCF1DC"/>
                                <Setter Property="Cursor" Value="Hand"/>
                            </Trigger>
                            <Trigger Property="IsChecked" Value="True">
                                <Setter TargetName="path" Property="Fill" Value="#1E2328"/>
                                <Setter TargetName="path" Property="Stroke" Value="#5C5B57"/>
                                <Setter Property="Foreground" Value="#3C3C41"/>
                                <Trigger.EnterActions>
                                    <BeginStoryboard Storyboard="{StaticResource Checked}"/>
                                </Trigger.EnterActions>
                                <Trigger.ExitActions>
                                    <BeginStoryboard Storyboard="{StaticResource UnChecked}"/>
                                </Trigger.ExitActions>
                            </Trigger>
                        </ControlTemplate.Triggers>
                    </ControlTemplate>
                </Setter.Value>
            </Setter>
        </Style>
    </Application.Resources>
</Application>
WPF에서는 다양한 동적 애니메이션을 만들어 사용자 인터페이스를 더욱 매력적으로 만들 수 있습니다. 이 프로젝트에서 Thickness 애니메이션은 TextBlock의 텍스트 부분에 흥미로운 애니메이션을 추가하는 데 사용됩니다.

애니메이션은 ControlTemplate.Resources를 사용하여 정의할 수 있으며, 이를 통해 "Checked" 및 "UnChecked"라는 두 개의 애니메이션 리소스를 정의할 수 있습니다. 체크하면 "재생" 텍스트가 제거되고 "중지" 텍스트가 안으로 이동하고, "확인되지 않음" 상태에서는 "중지" 텍스트가 제거되고 "재생" 텍스트가 안으로 이동합니다. 이렇게 하면 뒤집기 효과와 유사한 애니메이션이 만들어집니다.

애니메이션을 쉽게 만들고 사용할 수 있도록 WPF의 다양한 애니메이션을 Jamesnet.WPF Nuget 패키지로 컴파일하고 구성했습니다. 이 패키지를 추가하기만 하면 애니메이션을 쉽게 사용하고 작성할 수 있습니다.

5. 클립 속성 사용:
 

XAML
  <Grid Background="{TemplateBinding Background}">
         <Border Style="{StaticResource GoldLine}"/>
         <Image Style="{StaticResource Emblem}"/>
         <Border Style="{StaticResource GreenLine}"/>
         <Path x:Name="path" Style="{StaticResource Arrow}"/>
      <Grid>
         <Grid.Clip>
             <RectangleGeometry Rect="0,5,165,28"/>
         </Grid.Clip>
             <TextBlock x:Name="play" Style="{StaticResource Play}"/>
             <TextBlock x:Name="stop" Style="{StaticResource Stop}"/>
      </Grid> 
  </Grid>

Grid 내의 요소는 서로 겹치기 때문에 위아래로 스크롤하는 텍스트에 대한 애니메이션을 만들 때 텍스트가 테두리를 넘어 확장되는 것처럼 보이는 시각적 문제가 발생할 수 있습니다. 이 문제를 해결하기 위해 <Grid.Clip> 속성이 사용됩니다.

<Grid.Clip>은 자식 요소의 표시 영역을 제한하는 클리핑 영역을 정의하는 데 사용되는 XAML 요소입니다. 클리핑 영역은 일반적으로 사각형과 같은 모양이며, 클리핑 영역 내의 내용만 표시되고 바깥쪽의 내용은 숨겨집니다.

이 프로젝트에서 <Grid.Clip> 영역은 Path: Rect="0,5,165,28"의 크기 내에서 설정됩니다. 이렇게 하면 텍스트가 이 영역 내에만 나타나므로 패스 내에서 위아래로 스크롤 효과가 발생합니다.
