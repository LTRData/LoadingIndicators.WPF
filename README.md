# LoadingIndicators.WPF

A collection of **nine animated loading indicators for WPF**: `Wave`, `Arc`, `Arcs`, `ArcsRing`, `DoubleBounce`, `FlipPlane`, `Pulse`, `Ring` and `ThreeDots`.

![Demo](https://raw.githubusercontent.com/LTRData/LoadingIndicators.WPF/master/demo.gif)

## About this LTRData fork

This is the LTRData fork of [LoadingIndicators.WPF](https://github.com/punker76/LoadingIndicators.WPF), originally published under `zeluisping`. The August 2023 LTRData changes adjust the framework targets and NuGet packaging and remove the projects' Paket restore integration. The checked-in package version is `2.0.1`.

The library and demo target **.NET Framework 4.5** and **.NET 6 for Windows** (`net45;net6.0-windows`). This is a Windows desktop control library using WPF.

## Install

Add the LTRData package to a compatible WPF application:

```sh
dotnet add package LTRData.LoadingIndicators.WPF
```

The assembly and CLR namespace remain `LoadingIndicators.WPF`. The original XAML namespace is still exported by the assembly and should be used as shown below; its URL is an identifier, not a package download location.

## Usage

Add the namespace to your window or user control:

```xml
<Window ...
        xmlns:li="http://github.com/zeluisping/loadingIndicators/xaml/controls">
```

Then add an indicator:

```xml
<li:LoadingIndicator Mode="Arcs"
                     IsActive="True"
                     SpeedRatio="1"
                     Foreground="DodgerBlue" />
```

The properties are dependency properties, so they can also be bound to a view model:

```xml
<li:LoadingIndicator Mode="Ring"
                     IsActive="{Binding IsBusy}"
                     SpeedRatio="{Binding AnimationSpeed}" />
```

| Property | Default | Behavior |
|---|---|---|
| `Mode` | `Wave` | Selects one of the nine animations listed above. |
| `IsActive` | `true` | Activates the animation; setting it to `false` switches to the inactive state and collapses the indicator's internal visual. |
| `SpeedRatio` | `1.0` | Controls animation speed; for example, `2.0` runs at twice the normal rate. |
| `Foreground` | Style uses `AccentColorBrush` | Sets the indicator color. A local value, as above, overrides the style's resource-based value. |

The styles use the `AccentColorBrush` resource convention associated with [MahApps.Metro](https://github.com/MahApps/MahApps.Metro). A default brush is included in [Colors.xaml](https://github.com/LTRData/LoadingIndicators.WPF/blob/master/src/LoadingIndicators.WPF/Colors.xaml), and the library has no MahApps.Metro package dependency. Set `Foreground` explicitly or supply the matching brush resource when integrating application themes.

## Source and demo

| Project | Purpose |
|---|---|
| [LoadingIndicators.WPF](https://github.com/LTRData/LoadingIndicators.WPF/tree/master/src/LoadingIndicators.WPF) | Control, animation styles and default resources. |
| [LoadingIndicators.WPF.Demo](https://github.com/LTRData/LoadingIndicators.WPF/tree/master/src/LoadingIndicators.WPF.Samples/LoadingIndicators.WPF.Demo) | WPF application displaying all nine modes, with activation controls and a speed slider. |

Both projects are in [src/LoadingIndicators.WPF.sln](https://github.com/LTRData/LoadingIndicators.WPF/blob/master/src/LoadingIndicators.WPF.sln). Building the Windows desktop projects requires appropriate .NET/WPF tooling and reference assemblies for the selected target. The .NET 6 demo requires the .NET 6 Windows Desktop runtime.

## License

See [LICENSE](https://github.com/LTRData/LoadingIndicators.WPF/blob/master/LICENSE) for the original Unlicense/public-domain dedication and warranty disclaimer.
