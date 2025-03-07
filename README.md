# 两款软件均来自于国内外大佬的开发，在他们的开发下才有我们学习的机会，来源我会放在最下面，感谢大佬  :smiling_face_with_three_hearts:
- **仅对使用者来说二者均可，有一点点计算机命令基础的用户即可使用greenluma，否则使用steamtools更为简便**

# GreenLuma与SteamTools的个人解析（代表目前我的学习进度）  
## **GreenLuma**  
**1. 核心功能与技术原理**  
GreenLuma是一款针对Steam平台设计的**内存补丁工具**，其主要功能是通过修改Steam客户端的内存数据与系统模块，绕过游戏数字版权管理（DRM）和授权验证机制。其技术实现主要依赖以下核心方法：  
- **内存篡改（Memory Patching）**：通过动态扫描并修改Steam进程内存中的关键标志位（如游戏ID、DLC激活状态），将未授权的游戏伪装为合法拥有。例如，拦截并篡改`SteamAPI_IsDlcInstalled`函数的返回值，使系统误判用户已购买特定DLC。  
- **DLL劫持（DLL Hijacking）**：替换Steam核心模块（如`steamclient.dll`、`vstdlib_s.dll`）为自定义版本，覆盖原始函数逻辑。例如，在加载DLL时注入代码，劫持游戏列表生成流程，添加未购买的游戏条目。  
- **私服联机支持**：通过重定向Steam的服务器通信接口（如`ISteamGameServer`相关API），将联机请求引导至用户自建的私有服务器，绕过官方服务器的认证流程。

**2. 使用条件与限制**  
- **客户端版本依赖**：仅支持特定版本的Steam Beta客户端，需手动禁用自动更新功能（修改`steam.cfg`文件中的`AutoUpdateBehavior`为`0`），否则补丁会因版本不兼容失效。  
- **反作弊规避**：无法绕过部分游戏的独立反作弊系统（如EasyAntiCheat、BattlEye），若强行使用可能导致VAC（Valve Anti-Cheat）封禁。  
- **操作环境隔离**：建议在虚拟机或沙盒环境中运行，避免污染主系统或触发安全软件警报。  

**3. 典型应用场景**  
- **DLC解锁**：免费激活付费扩展内容（如《文明6》的领袖包）。  
- **游戏共享**：通过私服实现非官方多人联机（如《求生之路2》社区服务器）。  
- **开发者调试**：本地测试游戏功能无需购买正版授权（需遵守DMCA安全研究豁免条款）。  

---

## **SteamTools**  
**1. 核心功能与技术原理**  
SteamTools是一款多功能的Steam辅助工具，其核心功能聚焦于**游戏共享**与**账号管理优化**：  
- **家庭库共享绕过**：通过模拟家庭共享组（Family Sharing Group）的授权流程，允许多账号同时访问同一游戏库，突破Steam官方限制的5设备上限。  
- **区域限制规避**：修改客户端区域标识（如`SteamCountry`注册表项），解锁地理锁定的游戏内容。  
- **多账号快速切换**：利用内存注入技术保存多个账号的登录凭证，实现一键切换，避免重复输入密码。  

**2. 使用条件与限制**  
- **版本兼容性**：依赖Steam客户端的特定版本（如Steam Beta 2023.12.01），需定期更新工具以适配官方接口变更。  
- **反作弊冲突**：开启工具后无法运行受VAC保护的游戏（如《CS:GO》《Dota2》），否则可能触发永久封禁。  
- **隐私风险**：若使用第三方修改版工具，存在账号凭证泄露或恶意代码注入风险。  

**3. 典型应用场景**  
- **游戏测试**：开发者快速切换测试账号验证多用户场景。  
- **跨区体验**：访问区域独占内容（如日本区视觉小说）。  
- **家庭共享优化**：多人共享游戏库时减少设备授权冲突。  
