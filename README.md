# FluentLauncher.Infra.Settings
Fluent Launcher 设置部分模块基础代码，源代码由 [@gaviny82](https://github.com/gaviny82) 编写

## 使用示例

以下代码取自 [FluentLauncher.Extension.ConnectX](https://github.com/Xcube-Studio/FluentLauncher.Extension.ConnectX) 仓库
``` CSharp
using FluentLauncher.Infra.Settings;
using FluentLauncher.Infra.Settings.Converters;

namespace FluentLauncher.Extension.ConnectX;

public partial class ClientSettingProvider(ISettingsStorage storage) 
    : SettingsContainer(storage), IClientSettingProvider
{
    [SettingItem(Default = "", Converter = typeof(JsonStringConverter<string>))]
    public partial string UserServerAddress { get; set; }

    [SettingItem(Default = 0, Converter = typeof(JsonStringConverter<int>))]
    public partial int ServerNodeSelection { get; set; }
}
```
