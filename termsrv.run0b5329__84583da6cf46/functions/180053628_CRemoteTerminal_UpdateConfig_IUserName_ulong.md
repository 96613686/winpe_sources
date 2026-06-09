# CRemoteTerminal::UpdateConfig(IUserName *,ulong)

- ea: `0x180053628`
- end: `0x18005a146`
- name: `?UpdateConfig@CRemoteTerminal@@AEAAJPEAUIUserName@@K@Z`
- size: `27422`
- prototype: `__int64 __fastcall(CRemoteTerminal *__hidden this, struct IUserName *, unsigned int)`
- caller_count: `2`
- callee_count: `37`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180047200`
- `0x180052a00`

## callees

- `0x180001284`
- `0x180001688`
- `0x180001a30`
- `0x18000225c`
- `0x180002544`
- `0x180002570`
- `0x1800029c4`
- `0x18000a210`
- `0x180013150`
- `0x180013d00`
- `0x180014440`
- `0x180014bb0`
- `0x180014ea8`
- `0x180015194`
- `0x1800157c0`
- `0x1800159d8`
- `0x180015ab0`
- `0x180017758`
- `0x180024d08`
- `0x1800255f8`
- `0x180025624`
- `0x1800256dc`
- `0x180028070`
- `0x1800287b4`
- `0x1800288a8`
- `0x1800321f0`
- `0x18003269c`
- `0x180032700`
- `0x1800330c4`
- `0x180051be0`
- `0x180053628`
- `0x18006be58`
- `0x1800b14b4`
- `0x1800b8c8c`
- `0x1800c4e00`
- `0x1800c4e0c`
- `0x1800c8010`

## import_xrefs

- `ntdll!EtwEventActivityIdControl` at `0x180053857`
- `ntdll!EtwEventActivityIdControl` at `0x180053857`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x180056472`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x180058bc6`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x180056472`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x180058bc6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800564bb`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180058bfe`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800564bb`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180058bfe`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800544df`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800545a7`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18005484e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180054a29`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180054abc`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800553a5`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800559cb`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180055a35`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180055a88`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180055b29`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180055dd6`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18005629a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180056712`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18005677b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800567dc`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180056840`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180057231`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800577ec`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180057d45`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180058395`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800583cb`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180058420`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800584c7`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180058774`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180058a1d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180058e43`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180058ea5`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180058f0c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180058f71`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18005997b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800544df`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800545a7`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18005484e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180054a29`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180054abc`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800553a5`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800559cb`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180055a35`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180055a88`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180055b29`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180055dd6`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18005629a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180056712`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18005677b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800567dc`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180056840`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180057231`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800577ec`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180057d45`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180058395`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800583cb`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180058420`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800584c7`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180058774`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180058a1d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180058e43`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180058ea5`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180058f0c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180058f71`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18005997b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800544c9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180054599`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005483d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180054981`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800549a6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800549bf`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800549d8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180054a13`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180054aae`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180055394`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005544d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800559b9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180055a20`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180055a74`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180055b16`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180055b74`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180055ba2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180055bd0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180055bf1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180055c40`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180055c6f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180055c9d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180055ccb`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180055cec`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180055dc5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180055e05`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180055e31`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180055e5b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180055e85`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180055ea2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180055ebf`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180055ed8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180055f02`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180055f27`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180055f4c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180055f68`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180055f85`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180056110`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180056289`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180056700`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180056769`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800567ca`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005682f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005688b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800568b9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800568e7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180056908`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005699c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800569cb`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800569fa`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180056a1c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005721f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800577db`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180057816`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180057837`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180057850`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180057869`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180057d34`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180057de7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180058383`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800583ba`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005840c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800584b4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005850e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005853c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005856a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005858b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800585e0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005860f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005863d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005866b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005868c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180058763`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800588d1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180058a0c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180058e31`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180058e93`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180058efa`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180058f5f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180058fb4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180058fe2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180059010`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180059031`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800590c5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800590f4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180059123`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180059145`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180059968`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180059a2a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180059a50`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180059a75`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180059a9a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180059ab6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180059ad3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180059aec`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180059b16`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180059b3b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180059b60`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180059b7c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180059b95`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800544c9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180054599`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005483d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180054981`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800549a6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800549bf`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800549d8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180054a13`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180054aae`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180055394`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005544d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800559b9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180055a20`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180055a74`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180055b16`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180055b74`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180055ba2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180055bd0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180055bf1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180055c40`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180055c6f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180055c9d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180055ccb`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180055cec`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180055dc5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180055e05`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180055e31`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180055e5b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180055e85`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180055ea2`

## string_xrefs

- `0x180056466`: `ntdll.dll`
- `0x180058bba`: `ntdll.dll`
- `0x180053a5c`: `Software\Policies\Microsoft\Windows NT\Terminal Services`
- `0x18005a06b`: `Task completed successfully`
- `0x180053738`: `RemoteTerminal->UpdateConfig()`
- `0x180053717`: `CRemoteTerminal::UpdateConfig`
- `0x1800541fe`: `CRemoteTerminal::UpdateConfig`
- `0x180059fbb`: `CRemoteTerminal::UpdateConfig`
- `0x18005a039`: `CRemoteTerminal::UpdateConfig`
- `0x1800537bf`: `UpdateConfig`
- `0x180053890`: `UpdateConfig`
- `0x1800539b9`: `UpdateConfig`
- `0x180053d19`: `UpdateConfig`
- `0x180053daf`: `UpdateConfig`
- `0x180053ec0`: `UpdateConfig`
- `0x180053fa7`: `UpdateConfig`
- `0x18005403e`: `UpdateConfig`
- `0x180054148`: `UpdateConfig`
- `0x180054234`: `UpdateConfig`
- `0x1800542f8`: `UpdateConfig`
- `0x1800543df`: `UpdateConfig`
- `0x180059d70`: `UpdateConfig`
- `0x180059f4a`: `UpdateConfig`
- `0x1800539ce`: `Terminal->GetConfigData`
- `0x180053a8d`: `Could not open policy reg-key for QueryLocalUserCfg`
- `0x180053ae3`: `fQueryUserConfigFromDC`
- `0x180053c54`: `fQueryUserConfigFromDC`
- `0x180053bfe`: `Could not open Winsta reg-key for QueryLocalUserCfg`
- `0x180053d2e`: `IUserConfig::GetInstanceOfUserConfig`
- `0x180053ed5`: `ptrUserConfig->UpdateConfig`
- `0x180053fbc`: `ptrUserConfig->UpdateConfigFromLocal`
- `0x180054053`: `ptrUserConfig->GetConfig`
- `0x1800540d9`: `UpdateConfig to get TSUserEX info`
- `0x18005415d`: `GetUserSid`
- `0x180054249`: `Impersonate.ImpersonateUser`
- `0x18005430d`: `Impersonate.StopImpersonating`
- `0x180054723`: `TerminalServices-DeviceRedirection-Licenses-TSEasyPrintAllowed`
- `0x180054e3d`: `TerminalServices-DeviceRedirection-Licenses-TSEasyPrintAllowed`
- `0x180054f85`: `TerminalServices-DeviceRedirection-Licenses-TSEasyPrintAllowed`
- `0x180059f5f`: `ptrConnection->SetConfigData`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CRemoteTerminal::UpdateConfig(CRemoteTerminal *this, struct IUserName *a2, char a3)
{
  unsigned __int8 *v5; // r15
  unsigned __int8 *v6; // rbx
  unsigned __int8 *v7; // rdi
  int v8; // r8d
  int v9; // r9d
  int v10; // ecx
  int v11; // r8d
  int v12; // r9d
  signed int ConfigData; // r14d
  int v14; // ecx
  int v15; // r8d
  int v16; // r9d
  unsigned __int8 *v17; // rax
  int v18; // ecx
  int v19; // r8d
  int v20; // r9d
  unsigned __int8 *v21; // r13
  int v22; // ecx
  int v23; // r8d
  int v24; // r9d
  LSTATUS v25; // eax
  int v26; // r8d
  int v27; // r9d
  LSTATUS v28; // ebx
  int v29; // ecx
  int v30; // r8d
  int v31; // r9d
  LSTATUS v32; // eax
  int v33; // r8d
  int v34; // r9d
  int v35; // ecx
  int v36; // r8d
  int v37; // r9d
  int v38; // ecx
  int v39; // r8d
  int v40; // r9d
  int v41; // eax
  int v42; // r8d
  int v43; // r9d
  struct IUserConfig *v44; // rbx
  int v45; // ecx
  int v46; // r8d
  int v47; // r9d
  int v48; // eax
  int v49; // r8d
  int v50; // r9d
  int v51; // ecx
  int v52; // r8d
  int v53; // r9d
  int v54; // ecx
  int v55; // r8d
  int v56; // r9d
  __int64 v57; // rsi
  unsigned __int8 *v58; // rdi
  ULONGLONG v59; // rax
  int v60; // r8d
  int v61; // r9d
  struct IUserName *v62; // rbx
  int v63; // ecx
  int v64; // r8d
  int v65; // r9d
  signed int LastError; // eax
  int v67; // ecx
  int v68; // r8d
  int v69; // r9d
  unsigned __int8 *v70; // r12
  unsigned __int8 *v71; // rbx
  char UserPolicy; // al
  int v73; // ecx
  int v74; // r8d
  int v75; // r9d
  CRemoteTerminal *v76; // r13
  int v77; // ecx
  int v78; // r8d
  int v79; // r9d
  int v80; // esi
  unsigned int v81; // ebx
  HLOCAL v82; // rax
  HANDLE ProcessHeap; // rax
  _OWORD *v84; // rax
  void *v85; // r15
  int v86; // r14d
  void *v87; // r12
  HANDLE v88; // rax
  _QWORD *v89; // rax
  int v90; // eax
  unsigned int v91; // ecx
  unsigned int v92; // r10d
  int v93; // eax
  unsigned int v94; // r10d
  int v95; // eax
  unsigned int v96; // r10d
  int v97; // eax
  size_t v98; // rdx
  int v99; // eax
  unsigned int v100; // r10d
  int v101; // eax
  unsigned int v102; // r10d
  int v103; // eax
  unsigned int v104; // esi
  HANDLE v105; // rax
  _DWORD *v106; // rsi
  int v107; // r9d
  unsigned int v108; // r11d
  unsigned int v109; // esi
  int v110; // r10d
  int v111; // eax
  void *v112; // rsi
  HANDLE v113; // rax
  void *v114; // rsi
  HANDLE v115; // rax
  HANDLE v116; // rax
  HANDLE v117; // rax
  void *v118; // r12
  size_t v119; // r13
  HANDLE v120; // rax
  _OWORD *v121; // rax
  void *v122; // r15
  HANDLE v123; // rax
  _QWORD *v124; // rax
  _QWORD *v125; // r13
  unsigned int *v126; // r9
  __int64 v127; // r9
  unsigned int v128; // r10d
  unsigned int *v129; // r9
  unsigned int v130; // r11d
  int v131; // r10d
  unsigned int *v132; // r9
  __int64 v133; // r9
  unsigned int v134; // r10d
  int v135; // r11d
  unsigned int *v136; // r9
  int v137; // r10d
  unsigned int *v138; // r9
  size_t v139; // rdx
  __int64 v140; // r9
  unsigned int v141; // r10d
  int v142; // r11d
  _DWORD *v143; // r9
  int v144; // r11d
  unsigned int *v145; // r9
  unsigned int v146; // esi
  __int64 v147; // r9
  unsigned int v148; // r11d
  _DWORD *v149; // r9
  __int64 v150; // r10
  int v151; // r10d
  unsigned int *v152; // r9
  __int64 v153; // r9
  unsigned int v154; // r10d
  int v155; // r11d
  _DWORD *v156; // r9
  int v157; // r10d
  unsigned int *v158; // r9
  __int64 v159; // r9
  unsigned int v160; // r10d
  int v161; // r11d
  _DWORD *v162; // r9
  __int64 v163; // rcx
  unsigned int v164; // r9d
  unsigned int v165; // r9d
  int v166; // r14d
  unsigned int v167; // eax
  unsigned int v168; // esi
  HANDLE v169; // rax
  char *v170; // rax
  char *v171; // rsi
  unsigned int v172; // r9d
  unsigned int v173; // r10d
  size_t v174; // rcx
  HANDLE v175; // rax
  unsigned int *v176; // rsi
  unsigned int *v177; // r13
  unsigned __int8 *v178; // r14
  void *v179; // rdx
  unsigned __int8 v180; // al
  unsigned __int64 v181; // rcx
  unsigned __int64 v182; // r8
  unsigned __int8 *v183; // r11
  int v184; // edx
  int v185; // r10d
  unsigned int v186; // r9d
  unsigned int v187; // edi
  int v188; // r8d
  unsigned int v189; // r9d
  unsigned int v190; // r10d
  unsigned int v191; // ecx
  unsigned int v192; // r11d
  _BYTE *v193; // rdi
  char v194; // bl
  int v195; // r10d
  int v196; // r15d
  _BYTE *v197; // rdi
  SIZE_T v198; // r14
  int v199; // r13d
  unsigned int v200; // eax
  unsigned int v201; // r12d
  int v202; // esi
  int v203; // r11d
  int v204; // edx
  int v205; // r10d
  int v206; // r8d
  int v207; // r10d
  int v208; // r9d
  int v209; // r8d
  unsigned int v210; // edx
  int v211; // r9d
  int v212; // ecx
  int v213; // edx
  int v214; // r8d
  int v215; // r9d
  int v216; // edx
  unsigned int v217; // r8d
  unsigned int v218; // r9d
  int v219; // edx
  int v220; // r8d
  int v221; // r9d
  int v222; // edx
  int v223; // r8d
  int v224; // r10d
  int v225; // edx
  int v226; // r9d
  unsigned int v227; // r8d
  int v228; // edx
  HANDLE v229; // rax
  _DWORD *v230; // rax
  int v231; // r14d
  HANDLE v232; // rax
  void *v233; // rcx
  _DWORD *v234; // r14
  HANDLE v235; // rax
  _OWORD *v236; // rax
  HANDLE v237; // rax
  _QWORD *v238; // rax
  _QWORD *v239; // rax
  HANDLE v240; // rax
  HANDLE v241; // rax
  HANDLE v242; // rax
  HANDLE v243; // rax
  HANDLE v244; // rax
  _QWORD *v245; // rax
  HANDLE v246; // rax
  HANDLE v247; // rax
  HANDLE v248; // rax
  HANDLE v249; // rax
  unsigned int v250; // r9d
  int v251; // r14d
  unsigned int v252; // r9d
  unsigned int v253; // esi
  HANDLE v254; // rax
  _DWORD *v255; // rax
  LPVOID v256; // rax
  HANDLE v257; // rax
  HANDLE v258; // rax
  HANDLE v259; // rax
  HANDLE v260; // rax
  HANDLE v261; // rax
  void *v262; // rsi
  HANDLE v263; // rax
  HANDLE v264; // rax
  _QWORD *v265; // rsi
  void *v266; // r13
  HANDLE v267; // rax
  void *v268; // r13
  HANDLE v269; // rax
  void *v270; // r13
  HANDLE v271; // rax
  HANDLE v272; // rax
  void *v273; // rsi
  HANDLE v274; // rax
  void *v275; // rcx
  void *v276; // r9
  unsigned int v277; // r10d
  void *v278; // rcx
  unsigned int *v279; // r9
  void *v280; // rcx
  unsigned int *v281; // r9
  HANDLE v282; // rax
  int v283; // eax
  __int64 v284; // rcx
  void *v285; // r9
  LPVOID v286; // rcx
  unsigned int v287; // r9d
  int v288; // r11d
  LPVOID v289; // rcx
  unsigned int v290; // esi
  HANDLE v291; // rax
  unsigned int *v292; // rax
  unsigned int v293; // r11d
  int v294; // r9d
  unsigned int v295; // r10d
  unsigned int v296; // r11d
  unsigned int v297; // r11d
  unsigned int v298; // r11d
  unsigned int v299; // r9d
  signed int v300; // eax
  FARPROC ProcAddress; // rax
  int v302; // eax
  unsigned int v303; // r9d
  SIZE_T v304; // rsi
  unsigned int v305; // r10d
  int v306; // r14d
  unsigned int *v307; // rcx
  int v308; // r9d
  int v309; // r9d
  __int64 v310; // r10
  unsigned int v311; // r10d
  int v312; // r9d
  SIZE_T v313; // r11
  unsigned int v314; // r11d
  int v315; // r9d
  unsigned int v316; // r10d
  int v317; // r9d
  unsigned int v318; // r10d
  int v319; // r9d
  int v320; // r10d
  int v321; // r11d
  HANDLE v322; // rax
  _DWORD *v323; // rcx
  HANDLE v324; // rax
  void *v325; // rcx
  HANDLE v326; // rax
  void *v327; // rcx
  void *v328; // rax
  unsigned __int64 v329; // rax
  unsigned int v330; // r14d
  HANDLE v331; // rax
  void *v332; // rcx
  _QWORD *v333; // rax
  HANDLE v334; // rax
  HANDLE v335; // rax
  HANDLE v336; // rax
  HANDLE v337; // rax
  unsigned int *v338; // rdx
  HANDLE v339; // rax
  HANDLE v340; // rax
  HANDLE v341; // rax
  HANDLE v342; // rax
  unsigned __int64 v343; // r14
  void *v344; // r11
  unsigned __int8 v345; // al
  unsigned int v346; // r9d
  unsigned int v347; // r10d
  unsigned __int8 *v348; // rbx
  unsigned int v349; // edi
  int v350; // eax
  int v351; // r8d
  unsigned int v352; // r8d
  unsigned int v353; // r10d
  int v354; // ecx
  int v355; // edx
  unsigned int v356; // esi
  _BYTE *v357; // rdi
  char v358; // bl
  int v359; // r10d
  int v360; // r11d
  unsigned int v361; // r9d
  unsigned __int8 *v362; // rbx
  _BYTE *v363; // rax
  SIZE_T v364; // r13
  unsigned int v365; // r12d
  int v366; // r15d
  int v367; // r14d
  int v368; // esi
  int v369; // edx
  int v370; // r8d
  int v371; // r9d
  unsigned int v372; // edx
  int v373; // r8d
  int v374; // r9d
  unsigned int v375; // edx
  int v376; // r8d
  int v377; // r10d
  int v378; // r11d
  unsigned int v379; // r9d
  int v380; // r8d
  unsigned int v381; // r9d
  int v382; // r10d
  int v383; // r11d
  int v384; // edx
  int v385; // r8d
  int v386; // r9d
  int v387; // edx
  int v388; // r10d
  int v389; // r8d
  unsigned int v390; // edx
  int v391; // r10d
  unsigned __int64 i; // rcx
  int v393; // r14d
  void *v394; // r9
  void *v395; // r10
  unsigned int *v396; // r11
  size_t v397; // r8
  void *v398; // rcx
  void *v399; // r11
  void *v400; // r10
  void *v401; // r9
  LPVOID v402; // rax
  void *v403; // r9
  void *v404; // r10
  void *v405; // r11
  LPVOID v406; // rcx
  void *v407; // rcx
  HANDLE v408; // rax
  unsigned int v409; // eax
  size_t v410; // rcx
  _DWORD *v411; // r9
  int v412; // r10d
  int *v413; // r14
  int v414; // esi
  unsigned int v415; // r11d
  int v416; // r10d
  void *v417; // r9
  int v418; // r10d
  LPVOID *v419; // rdx
  size_t v420; // rcx
  unsigned int v421; // r11d
  int v422; // r10d
  void *v423; // r9
  int v424; // r10d
  unsigned int *v425; // rdx
  size_t v426; // rcx
  unsigned int v427; // r11d
  int v428; // r10d
  size_t v429; // r9
  int v430; // r11d
  const void *v431; // rsi
  unsigned int *v432; // rcx
  unsigned int v433; // r13d
  int v434; // r10d
  void *v435; // r9
  int v436; // r10d
  unsigned int *v437; // rdx
  size_t v438; // rcx
  unsigned int v439; // r13d
  unsigned int v440; // r9d
  int v441; // r10d
  int v442; // r9d
  unsigned int v443; // r10d
  size_t v444; // r11
  int *v445; // rax
  size_t v446; // rcx
  unsigned int v447; // r11d
  int v448; // eax
  unsigned int v449; // r11d
  int v450; // r9d
  int v451; // eax
  unsigned int v452; // r11d
  int v453; // r9d
  int v454; // eax
  int v455; // r9d
  unsigned int v456; // esi
  HANDLE v457; // rax
  _DWORD *v458; // rax
  _DWORD *v459; // rsi
  void *v460; // rsi
  HANDLE v461; // rax
  HANDLE v462; // rax
  HANDLE v463; // rax
  HANDLE v464; // rax
  int v465; // r9d
  size_t v466; // r10
  unsigned int v467; // r11d
  unsigned int v468; // esi
  int v469; // r10d
  unsigned int *v470; // r9
  unsigned int v471; // r11d
  unsigned int v472; // r13d
  __int64 v473; // r9
  unsigned int v474; // r10d
  unsigned int *v475; // r9
  unsigned int v476; // r11d
  int v477; // r10d
  unsigned int *v478; // r9
  unsigned int v479; // r11d
  __int64 v480; // r9
  unsigned int v481; // r10d
  int v482; // r11d
  unsigned int *v483; // r9
  int v484; // r10d
  unsigned int *v485; // r9
  unsigned int v486; // r11d
  __int64 v487; // r9
  unsigned int v488; // r10d
  int v489; // r11d
  _DWORD *v490; // r9
  __int64 v491; // rcx
  unsigned int v492; // r9d
  unsigned int v493; // r13d
  int v494; // ecx
  LPVOID v495; // r9
  unsigned int v496; // r10d
  unsigned int v497; // eax
  unsigned int v498; // esi
  HANDLE v499; // rax
  char *v500; // rax
  char *v501; // rsi
  unsigned int v502; // r9d
  size_t v503; // rcx
  HANDLE v504; // rax
  unsigned int *v505; // rsi
  unsigned int *v506; // r13
  int v507; // ecx
  void *v508; // r8
  unsigned __int8 v509; // al
  SIZE_T v510; // rcx
  SIZE_T v511; // r11
  unsigned int v512; // r8d
  unsigned int v513; // r10d
  unsigned __int8 *v514; // rdi
  int v515; // ebx
  int v516; // esi
  int v517; // r9d
  unsigned int v518; // r10d
  unsigned int v519; // r9d
  int v520; // ecx
  int v521; // edx
  _BYTE *v522; // rbx
  char v523; // di
  unsigned int v524; // r9d
  int v525; // r8d
  unsigned __int8 *v526; // rdi
  _BYTE *v527; // r13
  SIZE_T v528; // rax
  int v529; // r12d
  int v530; // r15d
  int v531; // r14d
  int v532; // esi
  int v533; // r11d
  int v534; // edx
  int v535; // r9d
  int v536; // r10d
  int v537; // r8d
  int v538; // r9d
  unsigned int v539; // edx
  int v540; // r8d
  int v541; // ecx
  int v542; // edx
  int v543; // r9d
  int v544; // edx
  unsigned int v545; // r8d
  unsigned int v546; // r9d
  int v547; // edx
  int v548; // r8d
  int v549; // r9d
  int v550; // edx
  int v551; // r8d
  int v552; // r9d
  int v553; // edx
  int v554; // r8d
  unsigned int v555; // r9d
  int v556; // edx
  HANDLE v557; // rax
  _DWORD *v558; // rax
  void *v559; // rbx
  unsigned int v560; // ebx
  HANDLE v561; // rax
  void *v562; // rcx
  HANDLE v563; // rax
  _OWORD *v564; // rcx
  _DWORD *v565; // rax
  HANDLE v566; // rax
  _QWORD *v567; // rax
  _QWORD *v568; // rax
  HANDLE v569; // rax
  HANDLE v570; // rax
  HANDLE v571; // rax
  HANDLE v572; // rax
  void *v573; // rcx
  HANDLE v574; // rax
  _QWORD *v575; // rax
  HANDLE v576; // rax
  HANDLE v577; // rax
  HANDLE v578; // rax
  HANDLE v579; // rax
  unsigned int v580; // r9d
  unsigned int v581; // r9d
  unsigned int v582; // ebx
  HANDLE v583; // rax
  _DWORD *v584; // rax
  void *v585; // rdi
  void *v586; // rcx
  unsigned int v587; // r9d
  LPVOID v588; // rcx
  unsigned int *v589; // r9
  LPVOID v590; // rcx
  unsigned int *v591; // r9
  int v592; // eax
  HANDLE v593; // rax
  int v594; // eax
  int v595; // eax
  int v596; // r9d
  __int64 v597; // rcx
  size_t v598; // rcx
  unsigned int v599; // r11d
  int v600; // r10d
  unsigned int v601; // ebx
  size_t v602; // rcx
  unsigned int v603; // ebx
  HANDLE v604; // rax
  unsigned int *v605; // rax
  unsigned int v606; // r11d
  int v607; // r10d
  int v608; // r9d
  unsigned int v609; // r11d
  unsigned int v610; // r11d
  unsigned int v611; // r11d
  unsigned int v612; // r10d
  bool v613; // sf
  FARPROC v614; // rax
  unsigned int v615; // r9d
  SIZE_T v616; // rbx
  int v617; // ecx
  unsigned int v618; // r10d
  int v619; // r9d
  int v620; // r9d
  __int64 v621; // r10
  unsigned int v622; // r10d
  int v623; // r9d
  size_t v624; // r11
  unsigned int v625; // r11d
  int v626; // r9d
  unsigned int v627; // r10d
  int v628; // r9d
  unsigned int v629; // r10d
  int v630; // r9d
  int v631; // r10d
  int v632; // r11d
  HANDLE v633; // rax
  _QWORD *v634; // rax
  _DWORD *v635; // rcx
  HANDLE v636; // rax
  void *v637; // rcx
  _QWORD *v638; // rax
  HANDLE v639; // rax
  void *v640; // rcx
  SIZE_T v641; // rax
  HANDLE v642; // rax
  void *v643; // rcx
  HANDLE v644; // rax
  HANDLE v645; // rax
  HANDLE v646; // rax
  HANDLE v647; // rax
  unsigned int *v648; // rdx
  unsigned int *v649; // rax
  HANDLE v650; // rax
  HANDLE v651; // rax
  HANDLE v652; // rax
  HANDLE v653; // rax
  void *v654; // r10
  unsigned __int8 v655; // al
  unsigned __int8 *v656; // r9
  size_t v657; // r11
  int v658; // edi
  int v659; // r11d
  unsigned int v660; // eax
  unsigned int v661; // edx
  _BYTE *v662; // rcx
  unsigned int v663; // r8d
  unsigned int v664; // r9d
  int v665; // ebx
  int v666; // edi
  unsigned int v667; // eax
  char v668; // r10
  int v669; // r9d
  SIZE_T v670; // rcx
  int v671; // r14d
  int v672; // r10d
  int v673; // r11d
  unsigned __int8 *v674; // rax
  _BYTE *v675; // r13
  int v676; // r12d
  int v677; // esi
  int v678; // ebx
  int v679; // edx
  unsigned int v680; // r8d
  int v681; // r9d
  unsigned int v682; // edx
  int v683; // r8d
  int v684; // r9d
  unsigned int v685; // edx
  int v686; // r8d
  int v687; // r10d
  int v688; // r11d
  unsigned int v689; // r9d
  int v690; // r8d
  unsigned int v691; // r9d
  int v692; // edx
  int v693; // r8d
  int v694; // r9d
  int v695; // edx
  unsigned int v696; // r8d
  int v697; // r9d
  int v698; // edx
  int v699; // r8d
  unsigned int v700; // r9d
  int v701; // edx
  size_t j; // rcx
  void *v703; // r9
  void *v704; // rdi
  int v705; // ecx
  unsigned int *v706; // r10
  int v707; // r11d
  __int64 v708; // rbx
  int v709; // r11d
  unsigned int v710; // r11d
  __int64 v711; // r8
  unsigned int *v712; // r11
  void *v713; // r10
  unsigned int *v714; // rbx
  LPVOID v715; // rax
  void *v716; // r15
  unsigned int *v717; // r12
  void *v718; // r13
  void *v719; // rcx
  unsigned int v720; // edx
  HANDLE v721; // rax
  int v722; // eax
  HANDLE v723; // rax
  void *v724; // rbx
  HANDLE v725; // rax
  void *v726; // rbx
  HANDLE v727; // rax
  void *v728; // rbx
  HANDLE v729; // rax
  HANDLE v730; // rax
  void *v731; // rbx
  HANDLE v732; // rax
  HANDLE v733; // rax
  _QWORD *v734; // rbx
  void *v735; // rsi
  HANDLE v736; // rax
  void *v737; // rsi
  HANDLE v738; // rax
  void *v739; // rsi
  HANDLE v740; // rax
  HANDLE v741; // rax
  HANDLE v742; // rax
  unsigned int v743; // r9d
  __int64 v744; // r11
  int *v745; // rcx
  size_t v746; // rcx
  unsigned int v747; // r10d
  int v748; // r9d
  int v749; // ebx
  int v750; // ecx
  int v751; // r8d
  int v752; // r9d
  int v753; // ecx
  int v754; // r8d
  int v755; // r9d
  int v756; // edx
  int v757; // eax
  int *v758; // rcx
  _DWORD *v759; // r8
  int v760; // ecx
  int v761; // r8d
  int v762; // r9d
  int v763; // ecx
  int v764; // r8d
  int v765; // r9d
  int v766; // ecx
  int v767; // r8d
  int v768; // r9d
  __int64 v769; // rdx
  _BYTE *v770; // rax
  unsigned int v772; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v773; // [rsp+54h] [rbp-ACh] BYREF
  unsigned int dwBytes; // [rsp+58h] [rbp-A8h] BYREF
  unsigned int dwBytes_4; // [rsp+5Ch] [rbp-A4h] BYREF
  size_t v776; // [rsp+60h] [rbp-A0h] BYREF
  LPVOID v777; // [rsp+68h] [rbp-98h]
  unsigned int v778; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int8 v779; // [rsp+74h] [rbp-8Ch]
  int v780; // [rsp+78h] [rbp-88h] BYREF
  int v781; // [rsp+7Ch] [rbp-84h]
  LPVOID v782; // [rsp+80h] [rbp-80h]
  unsigned int *v783; // [rsp+88h] [rbp-78h]
  SIZE_T v784; // [rsp+90h] [rbp-70h]
  LPVOID v785; // [rsp+98h] [rbp-68h]
  LPVOID v786; // [rsp+A0h] [rbp-60h] BYREF
  LPVOID v787; // [rsp+A8h] [rbp-58h]
  void *v788; // [rsp+B0h] [rbp-50h] BYREF
  LPVOID v789; // [rsp+B8h] [rbp-48h] BYREF
  LPVOID v790; // [rsp+C0h] [rbp-40h]
  _DWORD *v791; // [rsp+C8h] [rbp-38h] BYREF
  LPVOID v792; // [rsp+D0h] [rbp-30h]
  LPVOID v793; // [rsp+D8h] [rbp-28h] BYREF
  SIZE_T v794; // [rsp+E0h] [rbp-20h] BYREF
  unsigned int v795; // [rsp+E8h] [rbp-18h]
  LPVOID lpMem[2]; // [rsp+F0h] [rbp-10h] BYREF
  size_t pcchLength; // [rsp+100h] [rbp+0h] BYREF
  unsigned int v798; // [rsp+108h] [rbp+8h] BYREF
  void *Src; // [rsp+110h] [rbp+10h]
  void *v800; // [rsp+118h] [rbp+18h] BYREF
  size_t v801[2]; // [rsp+120h] [rbp+20h] BYREF
  SIZE_T v802; // [rsp+130h] [rbp+30h] BYREF
  void *v803; // [rsp+138h] [rbp+38h] BYREF
  SIZE_T Size; // [rsp+140h] [rbp+40h]
  __int16 v805; // [rsp+148h] [rbp+48h] BYREF
  void *v806; // [rsp+150h] [rbp+50h]
  SIZE_T v807; // [rsp+158h] [rbp+58h]
  unsigned int v808; // [rsp+160h] [rbp+60h] BYREF
  unsigned int v809; // [rsp+164h] [rbp+64h] BYREF
  unsigned __int8 *v810; // [rsp+168h] [rbp+68h]
  BYTE Data[4]; // [rsp+170h] [rbp+70h] BYREF
  HKEY hKey; // [rsp+178h] [rbp+78h] BYREF
  void *v813; // [rsp+180h] [rbp+80h] BYREF
  unsigned int v814; // [rsp+188h] [rbp+88h] BYREF
  unsigned int v815; // [rsp+18Ch] [rbp+8Ch] BYREF
  unsigned __int8 *v816; // [rsp+190h] [rbp+90h]
  int v817; // [rsp+198h] [rbp+98h] BYREF
  int v818; // [rsp+19Ch] [rbp+9Ch] BYREF
  int v819; // [rsp+1A0h] [rbp+A0h] BYREF
  int v820; // [rsp+1A4h] [rbp+A4h] BYREF
  unsigned int v821; // [rsp+1A8h] [rbp+A8h]
  int v822; // [rsp+1ACh] [rbp+ACh]
  unsigned int v823; // [rsp+1B0h] [rbp+B0h] BYREF
  int v824; // [rsp+1B4h] [rbp+B4h]
  unsigned int v825; // [rsp+1B8h] [rbp+B8h] BYREF
  DWORD Type; // [rsp+1BCh] [rbp+BCh] BYREF
  DWORD cbData; // [rsp+1C0h] [rbp+C0h] BYREF
  unsigned __int8 *v828; // [rsp+1C8h] [rbp+C8h]
  CRemoteTerminal *v829; // [rsp+1D0h] [rbp+D0h]
  struct IUserConfig *v830; // [rsp+1D8h] [rbp+D8h] BYREF
  void *TickCount64; // [rsp+1E0h] [rbp+E0h]
  signed int v832; // [rsp+1E8h] [rbp+E8h] BYREF
  int v833; // [rsp+1ECh] [rbp+ECh] BYREF
  signed int v834; // [rsp+1F0h] [rbp+F0h] BYREF
  signed int v835; // [rsp+1F4h] [rbp+F4h] BYREF
  signed int v836; // [rsp+1F8h] [rbp+F8h] BYREF
  signed int v837; // [rsp+1FCh] [rbp+FCh] BYREF
  signed int v838; // [rsp+200h] [rbp+100h] BYREF
  signed int v839; // [rsp+204h] [rbp+104h] BYREF
  signed int v840; // [rsp+208h] [rbp+108h] BYREF
  int v841; // [rsp+20Ch] [rbp+10Ch] BYREF
  signed int v842; // [rsp+210h] [rbp+110h] BYREF
  int v843; // [rsp+214h] [rbp+114h] BYREF
  signed int v844; // [rsp+218h] [rbp+118h] BYREF
  signed int v845; // [rsp+21Ch] [rbp+11Ch] BYREF
  signed int v846; // [rsp+220h] [rbp+120h] BYREF
  signed int v847; // [rsp+224h] [rbp+124h] BYREF
  signed int v848; // [rsp+228h] [rbp+128h] BYREF
  int *v849; // [rsp+230h] [rbp+130h] BYREF
  struct IUserName *v850; // [rsp+238h] [rbp+138h]
  LPWSTR StringSid; // [rsp+240h] [rbp+140h] BYREF
  PSID Sid; // [rsp+248h] [rbp+148h] BYREF
  LSTATUS v853; // [rsp+250h] [rbp+150h] BYREF
  LSTATUS v854; // [rsp+258h] [rbp+158h] BYREF
  signed int v855; // [rsp+25Ch] [rbp+15Ch] BYREF
  int v856; // [rsp+260h] [rbp+160h] BYREF
  HMODULE phModule; // [rsp+268h] [rbp+168h] BYREF
  HMODULE hModule; // [rsp+278h] [rbp+178h] BYREF
  __int128 v859; // [rsp+280h] [rbp+180h] BYREF
  __int128 v860; // [rsp+290h] [rbp+190h]
  __int128 v861; // [rsp+2A0h] [rbp+1A0h] BYREF
  __int128 v862; // [rsp+2B0h] [rbp+1B0h]
  const char *v863; // [rsp+2C0h] [rbp+1C0h] BYREF
  const char *v864; // [rsp+2C8h] [rbp+1C8h] BYREF
  const char *v865; // [rsp+2D0h] [rbp+1D0h] BYREF
  const char *v866; // [rsp+2D8h] [rbp+1D8h] BYREF
  const char *v867; // [rsp+2E0h] [rbp+1E0h] BYREF
  const char *v868; // [rsp+2E8h] [rbp+1E8h] BYREF
  const char *v869; // [rsp+2F0h] [rbp+1F0h] BYREF
  const char *v870; // [rsp+2F8h] [rbp+1F8h] BYREF
  const char *v871; // [rsp+300h] [rbp+200h] BYREF
  const char *v872; // [rsp+308h] [rbp+208h] BYREF
  const WCHAR *v873; // [rsp+310h] [rbp+210h] BYREF
  const char *v874; // [rsp+318h] [rbp+218h] BYREF
  __int64 v875; // [rsp+320h] [rbp+220h] BYREF
  const WCHAR *v876; // [rsp+328h] [rbp+228h] BYREF
  const char *v877; // [rsp+330h] [rbp+230h] BYREF
  WCHAR *v878; // [rsp+338h] [rbp+238h] BYREF
  const char *v879; // [rsp+340h] [rbp+240h] BYREF
  __int64 v880; // [rsp+348h] [rbp+248h] BYREF
  WCHAR *v881; // [rsp+350h] [rbp+250h] BYREF
  const char *v882; // [rsp+358h] [rbp+258h] BYREF
  const char *v883; // [rsp+360h] [rbp+260h] BYREF
  const char *v884; // [rsp+368h] [rbp+268h] BYREF
  const char *v885; // [rsp+370h] [rbp+270h] BYREF
  const char *v886; // [rsp+378h] [rbp+278h] BYREF
  const char *v887; // [rsp+380h] [rbp+280h] BYREF
  const char *v888; // [rsp+388h] [rbp+288h] BYREF
  const char *v889; // [rsp+390h] [rbp+290h] BYREF
  const char *v890; // [rsp+398h] [rbp+298h] BYREF
  const char *v891; // [rsp+3A0h] [rbp+2A0h] BYREF
  const char *v892; // [rsp+3A8h] [rbp+2A8h] BYREF
  const char *v893; // [rsp+3B0h] [rbp+2B0h] BYREF
  const char *v894; // [rsp+3B8h] [rbp+2B8h] BYREF
  const char *v895; // [rsp+3C0h] [rbp+2C0h] BYREF
  const char *v896; // [rsp+3C8h] [rbp+2C8h] BYREF
  const char *v897; // [rsp+3D0h] [rbp+2D0h] BYREF
  const char *v898; // [rsp+3D8h] [rbp+2D8h] BYREF
  const char *v899; // [rsp+3E0h] [rbp+2E0h] BYREF
  ULONGLONG v900; // [rsp+3E8h] [rbp+2E8h] BYREF
  const char *v901; // [rsp+3F0h] [rbp+2F0h] BYREF
  const char *v902; // [rsp+3F8h] [rbp+2F8h] BYREF
  const char *v903; // [rsp+400h] [rbp+300h] BYREF
  const char *v904; // [rsp+408h] [rbp+308h] BYREF
  const char *v905; // [rsp+410h] [rbp+310h] BYREF
  const char *v906; // [rsp+418h] [rbp+318h] BYREF
  const char *v907; // [rsp+420h] [rbp+320h] BYREF
  const char *v908; // [rsp+428h] [rbp+328h] BYREF
  const char *v909; // [rsp+430h] [rbp+330h] BYREF
  const char *v910; // [rsp+438h] [rbp+338h] BYREF
  const char *v911; // [rsp+440h] [rbp+340h] BYREF
  const char *v912; // [rsp+448h] [rbp+348h] BYREF
  const char *v913; // [rsp+450h] [rbp+350h] BYREF
  const char *v914; // [rsp+460h] [rbp+360h] BYREF
  const char *v915; // [rsp+468h] [rbp+368h] BYREF
  const char *v916; // [rsp+470h] [rbp+370h] BYREF
  const char *v917; // [rsp+478h] [rbp+378h] BYREF
  const char *v918; // [rsp+480h] [rbp+380h] BYREF
  const char *v919; // [rsp+488h] [rbp+388h] BYREF
  const char *v920; // [rsp+490h] [rbp+390h] BYREF
  const char *v921; // [rsp+498h] [rbp+398h] BYREF
  const char *v922; // [rsp+4A0h] [rbp+3A0h] BYREF
  const char *v923; // [rsp+4A8h] [rbp+3A8h] BYREF
  const char *v924; // [rsp+4B0h] [rbp+3B0h] BYREF
  __int64 v925; // [rsp+4C0h] [rbp+3C0h] BYREF
  const char *v926; // [rsp+4C8h] [rbp+3C8h] BYREF
  const char *v927; // [rsp+4D0h] [rbp+3D0h] BYREF
  struct _GUID v928; // [rsp+528h] [rbp+428h] BYREF
  __int128 Buf1; // [rsp+538h] [rbp+438h] BYREF
  struct _GUID v930; // [rsp+548h] [rbp+448h] BYREF
  _BYTE v931[16]; // [rsp+558h] [rbp+458h] BYREF
  int v932; // [rsp+568h] [rbp+468h]
  _BYTE v933[80]; // [rsp+570h] [rbp+470h] BYREF
  WCHAR SubKey[264]; // [rsp+5C0h] [rbp+4C0h] BYREF

  v850 = a2;
  v829 = this;
  v5 = 0;
  v6 = 0;
  v7 = 0;
  v828 = 0;
  StringSid = 0;
  Sid = 0;
  v930 = 0;
  v820 = 1;
  v818 = 0;
  v817 = 0;
  v830 = 0;
  v805 = 0;
  v819 = 0;
  Buf1 = 0;
  hKey = 0;
  Type = 0;
  *(_DWORD *)Data = 0;
  cbData = 4;
  memset_0(SubKey, 0, 0x208u);
  v928 = 0;
  CAutoSetActivityId::CAutoSetActivityId((CAutoSetActivityId *)v931, &v928);
  if ( (unsigned int)dword_180128170 > 4 )
  {
    v925 = *((int *)this + 420);
    v926 = "RemoteTerminal->UpdateConfig()";
    v927 = "CRemoteTerminal::UpdateConfig";
    v863 = "Group Policy";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<8>>(
      (unsigned int)"Group Policy",
      (unsigned int)qword_180108870,
      v8,
      v9,
      (__int64)&v863,
      (__int64)&v927,
      (__int64)&v926,
      (__int64)&v925);
  }
  TickCount64 = (void *)GetTickCount64();
  if ( !*((_QWORD *)this + 200) )
  {
    ConfigData = -2147022646;
    if ( (unsigned int)dword_180128170 > 3 )
    {
      v864 = "UpdateConfig";
      v841 = -2147022646;
      v865 = "check for presence of connection object";
      v866 = "Warning HResult failed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        v10,
        (unsigned int)byte_180108835,
        v11,
        v12,
        (__int64)&v866,
        (__int64)&v865,
        (__int64)&v841,
        (__int64)&v864);
    }
    goto LABEL_991;
  }
  CRemoteTerminal::GetActivityId(this, &v928);
  if ( v932 >= 0 )
    EtwEventActivityIdControl(2, &v928);
  ConfigData = (*(__int64 (__fastcall **)(_QWORD, __int128 *))(**((_QWORD **)this + 200) + 336LL))(
                 *((_QWORD *)this + 200),
                 &Buf1);
  if ( ConfigData < 0 )
  {
    if ( (unsigned int)dword_180128170 > 3 )
    {
      v867 = "UpdateConfig";
      v847 = ConfigData;
      v868 = "ptrConnection->GetConnectionGUID";
      v869 = "Warning HResult failed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        v14,
        (unsigned int)word_1801087FA,
        v15,
        v16,
        (__int64)&v869,
        (__int64)&v868,
        (__int64)&v847,
        (__int64)&v867);
    }
    v7 = 0;
    goto LABEL_991;
  }
  if ( !memcmp_0(&Buf1, &TERMINAL_TYPE_DEBUG, 0x10u) )
  {
    if ( (g_DebugTraceComponent & 4) != 0 )
      _DbgPrintMessage(2, "Connection for session %d is debug", *((_DWORD *)this + 420));
    ConfigData = 0;
    goto LABEL_995;
  }
  v17 = (unsigned __int8 *)operator new[](0x1E40u, (const struct std::nothrow_t *)std::nothrow);
  v7 = v17;
  v816 = v17;
  v6 = v17;
  v810 = v17;
  if ( !v17 )
  {
    ConfigData = -2147024882;
    v7 = v828;
    goto LABEL_991;
  }
  memset_0(v17, 0, 0x1E40u);
  ConfigData = CRemoteTerminal::GetConfigData(this, v7, 0xA68u);
  if ( ConfigData < 0 )
  {
    if ( (unsigned int)dword_180128170 > 3 )
    {
      v870 = "UpdateConfig";
      v848 = ConfigData;
      v871 = "Terminal->GetConfigData";
      v872 = "Warning HResult failed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        v18,
        (unsigned int)&byte_1801087BF,
        v19,
        v20,
        (__int64)&v872,
        (__int64)&v871,
        (__int64)&v848,
        (__int64)&v870);
    }
    goto LABEL_991;
  }
  v21 = v7 + 2672;
  if ( (*(int (__fastcall **)(_QWORD, _BYTE *))(**((_QWORD **)this + 200) + 64LL))(*((_QWORD *)this + 200), v933) >= 0 )
  {
    if ( RegOpenKeyExW(
           HKEY_LOCAL_MACHINE,
           L"Software\\Policies\\Microsoft\\Windows NT\\Terminal Services",
           0,
           0x20019u,
           &hKey) )
    {
      if ( (unsigned int)dword_180128170 > 4 )
      {
        v873 = L"Software\\Policies\\Microsoft\\Windows NT\\Terminal Services";
        v874 = "Could not open policy reg-key for QueryLocalUserCfg";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
          v22,
          (unsigned int)word_18010878A,
          v23,
          v24,
          (__int64)&v874,
          (__int64)&v873);
      }
    }
    else
    {
      v25 = RegQueryValueExW(hKey, L"fQueryUserConfigFromDC", 0, &Type, Data, &cbData);
      v28 = v25;
      if ( (unsigned int)dword_180128170 > 5 )
      {
        v875 = *(unsigned int *)Data;
        v853 = v25;
        v876 = L"Software\\Policies\\Microsoft\\Windows NT\\Terminal Services";
        v877 = "Policy reg-key value for QueryLocalUserCfg";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
          *(_DWORD *)Data,
          (unsigned int)&byte_180108737,
          v26,
          v27,
          (__int64)&v877,
          (__int64)&v876,
          (__int64)&v853,
          (__int64)&v875);
      }
      RegCloseKey(hKey);
      hKey = 0;
      RegCloseKey(0);
      hKey = 0;
      if ( !v28 )
        goto LABEL_34;
    }
  }
  StringCchPrintfW(SubKey, 0x104u, L"%s\\%s", L"System\\CurrentControlSet\\Control\\Terminal Server\\WinStations", v933);
  if ( RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0x20019u, &hKey) )
  {
    if ( (unsigned int)dword_180128170 > 4 )
    {
      v878 = SubKey;
      v879 = "Could not open Winsta reg-key for QueryLocalUserCfg";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
        v29,
        (unsigned int)&byte_180108707,
        v30,
        v31,
        (__int64)&v879,
        (__int64)&v878);
    }
  }
  else
  {
    v32 = RegQueryValueExW(hKey, L"fQueryUserConfigFromDC", 0, &Type, Data, &cbData);
    if ( (unsigned int)dword_180128170 > 5 )
    {
      v880 = *(unsigned int *)Data;
      v854 = v32;
      v881 = SubKey;
      v882 = "Winstation reg-key value for QueryLocalUserCfg";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
        *(_DWORD *)Data,
        (unsigned int)byte_1801086B9,
        v33,
        v34,
        (__int64)&v882,
        (__int64)&v881,
        (__int64)&v854,
        (__int64)&v880);
    }
    RegCloseKey(hKey);
    hKey = 0;
  }
LABEL_34:
  if ( (a3 & 2) != 0 )
  {
    ConfigData = IUserConfig::GetInstanceOfUserConfig(&v830);
    if ( ConfigData < 0 )
    {
      if ( (unsigned int)dword_180128170 > 3 )
      {
        v883 = "UpdateConfig";
        v855 = ConfigData;
        v884 = "IUserConfig::GetInstanceOfUserConfig";
        v885 = "Warning HResult failed";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
          v35,
          (unsigned int)&word_18010867E,
          v36,
          v37,
          (__int64)&v885,
          (__int64)&v884,
          (__int64)&v855,
          (__int64)&v883);
      }
LABEL_38:
      v6 = v7;
      goto LABEL_991;
    }
    ConfigData = CRemoteTerminal::GetLicenseType(this, &v930);
    if ( ConfigData < 0 )
    {
      if ( (unsigned int)dword_180128170 > 3 )
      {
        v886 = "UpdateConfig";
        v840 = ConfigData;
        v887 = "GetLicenseType";
        v888 = "Warning HResult failed";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
          v38,
          (unsigned int)byte_180108643,
          v39,
          v40,
          (__int64)&v888,
          (__int64)&v887,
          (__int64)&v840,
          (__int64)&v886);
      }
      goto LABEL_38;
    }
    if ( *(_DWORD *)Data == 1 )
    {
      v41 = CrimsonHelper::RaiseEvent<unsigned short const *>(
              &CrimsonHelper::s_instance,
              EVENT_TS_DC_QUERY_USER_CONFIG,
              v933);
      if ( v41 < 0 && (unsigned int)dword_180128170 > 2 )
      {
        v856 = v41;
        v889 = "TS_RAISE_EVENT_1 failed with error";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
          dword_180128170,
          (unsigned int)byte_18010861D,
          v42,
          v43,
          (__int64)&v889,
          (__int64)&v856);
      }
      v44 = v830;
      ConfigData = (*(__int64 (__fastcall **)(struct IUserConfig *, struct IUserName *, struct _GUID *))(*(_QWORD *)v830 + 40LL))(
                     v830,
                     v850,
                     &v930);
      if ( ConfigData < 0 )
      {
        if ( (unsigned int)dword_180128170 > 3 )
        {
          v890 = "UpdateConfig";
          v832 = ConfigData;
          v891 = "ptrUserConfig->UpdateConfig";
          v892 = "Warning HResult failed";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
            v45,
            (unsigned int)word_1801085E2,
            v46,
            v47,
            (__int64)&v892,
            (__int64)&v891,
            (__int64)&v832,
            (__int64)&v890);
        }
        goto LABEL_38;
      }
    }
    else
    {
      v48 = CrimsonHelper::RaiseEvent<unsigned short const *>(
              &CrimsonHelper::s_instance,
              EVENT_TS_LM_QUERY_USER_CONFIG,
              v933);
      if ( v48 < 0 && (unsigned int)dword_180128170 > 2 )
      {
        v833 = v48;
        v893 = "TS_RAISE_EVENT_1 failed with error";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
          dword_180128170,
          (unsigned int)&dword_1801085BC,
          v49,
          v50,
          (__int64)&v893,
          (__int64)&v833);
      }
      v44 = v830;
      ConfigData = (*(__int64 (__fastcall **)(struct IUserConfig *))(*(_QWORD *)v830 + 48LL))(v830);
      if ( ConfigData < 0 )
      {
        if ( (unsigned int)dword_180128170 > 3 )
        {
          v894 = "UpdateConfig";
          v834 = ConfigData;
          v895 = "ptrUserConfig->UpdateConfigFromLocal";
          v896 = "Warning HResult failed";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
            v51,
            (unsigned int)byte_180108581,
            v52,
            v53,
            (__int64)&v896,
            (__int64)&v895,
            (__int64)&v834,
            (__int64)&v894);
        }
        goto LABEL_38;
      }
    }
    v5 = v7 + 5208;
    ConfigData = (*(__int64 (__fastcall **)(struct IUserConfig *, unsigned __int8 *))(*(_QWORD *)v44 + 32LL))(
                   v44,
                   v7 + 5208);
    if ( ConfigData < 0 )
    {
      if ( (unsigned int)dword_180128170 > 3 )
      {
        v897 = "UpdateConfig";
        v835 = ConfigData;
        v898 = "ptrUserConfig->GetConfig";
        v899 = "Warning HResult failed";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
          v54,
          (unsigned int)&word_180108546,
          v55,
          v56,
          (__int64)&v899,
          (__int64)&v898,
          (__int64)&v835,
          (__int64)&v897);
      }
      goto LABEL_58;
    }
  }
  v57 = 0;
  v58 = 0;
  v59 = GetTickCount64();
  if ( (unsigned int)dword_180128170 > 4 )
  {
    v900 = v59 - (_QWORD)TickCount64;
    v901 = "UpdateConfig to get TSUserEX info";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(
      dword_180128170,
      (unsigned int)&byte_180108517,
      v60,
      v61,
      (__int64)&v901,
      (__int64)&v900);
  }
  if ( (a3 & 1) != 0 )
  {
    v62 = v850;
    ConfigData = (*(__int64 (__fastcall **)(struct IUserName *, PSID *))(*(_QWORD *)v850 + 72LL))(v850, &Sid);
    if ( ConfigData < 0 )
    {
      if ( (unsigned int)dword_180128170 > 3 )
      {
        v902 = "UpdateConfig";
        v836 = ConfigData;
        v903 = "GetUserSid";
        v904 = "Warning HResult failed";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
          v63,
          (unsigned int)&dword_1801084DC,
          v64,
          v65,
          (__int64)&v904,
          (__int64)&v903,
          (__int64)&v836,
          (__int64)&v902);
      }
LABEL_65:
      v7 = v816;
LABEL_58:
      v6 = v7;
      goto LABEL_991;
    }
    if ( !ConvertSidToStringSidW(Sid, &StringSid) )
    {
      LastError = GetLastError();
      ConfigData = LastError;
      if ( LastError > 0 )
        ConfigData = (unsigned __int16)LastError | 0x80070000;
      v6 = v816;
      if ( ConfigData >= 0 )
        goto LABEL_995;
      v7 = v816;
LABEL_991:
      if ( (unsigned int)dword_180128170 > 3 && (unsigned __int8)tlgKeywordOn(&dword_180128170, 0) )
      {
        v845 = ConfigData;
        v921 = "CRemoteTerminal::UpdateConfig";
        v922 = "Group Policy";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
          v763,
          (unsigned int)byte_180108353,
          v764,
          v765,
          (__int64)&v922,
          (__int64)&v921,
          (__int64)&v845);
      }
      goto LABEL_999;
    }
    ConfigData = CImpersonate::ImpersonateUser((CImpersonate *)&v805, v62);
    if ( ConfigData < 0 )
    {
      if ( (unsigned int)dword_180128170 > 3 )
      {
        v905 = "UpdateConfig";
        v837 = ConfigData;
        v906 = "Impersonate.ImpersonateUser";
        v907 = "Warning HResult failed";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
          v67,
          (unsigned int)byte_1801084A1,
          v68,
          v69,
          (__int64)&v907,
          (__int64)&v906,
          (__int64)&v837,
          (__int64)&v905);
      }
      goto LABEL_65;
    }
    v70 = v816;
    v71 = v816 + 2664;
    UserPolicy = RegGetUserPolicy(StringSid, v816 + 2664, v21);
    *((_BYTE *)v829 + 5368) = UserPolicy;
    if ( UserPolicy )
      v58 = v21;
    v57 = (unsigned __int64)v71 & -(__int64)(UserPolicy != 0);
    ConfigData = CImpersonate::StopImpersonating((CImpersonate *)&v805);
    if ( ConfigData < 0 )
    {
      if ( (unsigned int)dword_180128170 > 3 )
      {
        v908 = "UpdateConfig";
        v838 = ConfigData;
        v909 = "Impersonate.StopImpersonating";
        v910 = "Warning HResult failed";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
          v73,
          (unsigned int)&word_180108466,
          v74,
          v75,
          (__int64)&v910,
          (__int64)&v909,
          (__int64)&v838,
          (__int64)&v908);
      }
      v7 = v70;
      v6 = v70;
      goto LABEL_991;
    }
  }
  else
  {
    v70 = v816;
  }
  v76 = v829;
  ConfigData = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64, unsigned __int8 *, unsigned __int8 *, unsigned __int8 *, int *, int *))(**((_QWORD **)v829 + 200) + 664LL))(
                 *((_QWORD *)v829 + 200),
                 1,
                 v57,
                 v58,
                 v5,
                 v70 + 124,
                 &v818,
                 &v817);
  if ( ConfigData < 0 )
  {
    if ( (unsigned int)dword_180128170 > 3 )
    {
      v911 = "UpdateConfig";
      v839 = ConfigData;
      v912 = "this->ptrConnection->MergeUserSettings";
      v913 = "Warning HResult failed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        v77,
        (unsigned int)byte_18010842B,
        v78,
        v79,
        (__int64)&v913,
        (__int64)&v912,
        (__int64)&v839,
        (__int64)&v911);
    }
    v7 = v70;
LABEL_990:
    v6 = v810;
    goto LABEL_991;
  }
  v7 = v70;
  v828 = v70;
  v80 = 0;
  v822 = 0;
  v849 = 0;
  v81 = 0;
  LODWORD(v782) = 0;
  v813 = 0;
  v82 = LocalAlloc(0x40u, 4u);
  SP<unsigned char,SP_HLOCAL<unsigned char>>::operator=(&v813, v82);
  TickCount64 = v813;
  if ( !v813 )
  {
    v86 = -2147024882;
    goto LABEL_946;
  }
  v821 = 0;
  v824 = 0;
  *(_OWORD *)lpMem = 0;
  v789 = 0;
  ProcessHeap = GetProcessHeap();
  v84 = HeapAlloc(ProcessHeap, 8u, 0xA0u);
  v85 = v84;
  v781 = -805306345;
  v798 = -1;
  v86 = -1073741801;
  if ( !v84 )
  {
    v87 = 0;
    v772 = -1073741801;
    goto LABEL_119;
  }
  *v84 = xmmword_180128590;
  v84[1] = xmmword_1801285A0;
  v84[2] = xmmword_1801285B0;
  v84[3] = xmmword_1801285C0;
  v84[4] = xmmword_1801285D0;
  v84[5] = xmmword_1801285E0;
  v84[6] = xmmword_1801285F0;
  v84[7] = xmmword_180128600;
  v84[8] = xmmword_180128610;
  v84[9] = xmmword_180128620;
  v88 = GetProcessHeap();
  v89 = HeapAlloc(v88, 8u, 8u);
  v87 = v89;
  if ( !v89 )
  {
    v772 = -1073741801;
    goto LABEL_119;
  }
  *v89 = qword_1801284D0;
  v802 = __rdtsc();
  dwBytes = 0;
  v773 = 0;
  v86 = RtlUIntAdd(4, 4, &v773);
  v772 = v86;
  if ( v86 >= 0 )
  {
    v90 = RtlUIntAdd(0, v773, &dwBytes);
    v86 = v90 | 0x10000000;
    v772 = v90 | 0x10000000;
    if ( v90 >= 0 )
    {
      v773 = v91;
      v86 = RtlUIntAdd(v92, 160, &v773);
      v772 = v86;
      if ( v86 >= 0 )
      {
        v93 = RtlUIntAdd(dwBytes, v773, &dwBytes);
        v86 = v93 | 0x10000000;
        v772 = v93 | 0x10000000;
        if ( v93 >= 0 )
        {
          v773 = 0;
          v86 = RtlUIntAdd(v94, 8, &v773);
          v772 = v86;
          if ( v86 >= 0 )
          {
            v95 = RtlUIntAdd(dwBytes, v773, &dwBytes);
            v86 = v95 | 0x10000000;
            v772 = v95 | 0x10000000;
            if ( v95 >= 0 )
            {
              v773 = 0;
              v86 = RtlUIntAdd(v96, 8, &v773);
              v772 = v86;
              if ( v86 >= 0 )
              {
                v97 = RtlUIntAdd(dwBytes, v773, &dwBytes);
                v86 = v97 | 0x10000000;
                v772 = v97 | 0x10000000;
                if ( v97 >= 0 )
                {
                  pcchLength = 0;
                  if ( StringCchLengthW(
                         L"TerminalServices-DeviceRedirection-Licenses-TSEasyPrintAllowed",
                         v98,
                         &pcchLength) < 0 )
                  {
                    v86 = -1073741762;
LABEL_319:
                    v772 = v86;
                    goto LABEL_119;
                  }
                  v773 = 0;
                  v86 = RtlUIntAdd(4, (unsigned int)(2 * (pcchLength + 1)), &v773);
                  v772 = v86;
                  if ( v86 >= 0 )
                  {
                    v99 = RtlUIntAdd(dwBytes, v773, &dwBytes);
                    v86 = v99 | 0x10000000;
                    v772 = v99 | 0x10000000;
                    if ( v99 >= 0 )
                    {
                      v773 = 0;
                      v86 = RtlUIntAdd(v100, v100, &v773);
                      v772 = v86;
                      if ( v86 >= 0 )
                      {
                        v101 = RtlUIntAdd(dwBytes, v773, &dwBytes);
                        v86 = v101 | 0x10000000;
                        v772 = v101 | 0x10000000;
                        if ( v101 >= 0 )
                        {
                          v773 = 0;
                          v86 = RtlUIntAdd(v102, v102, &v773);
                          v772 = v86;
                          if ( v86 >= 0 )
                          {
                            v103 = RtlUIntAdd(dwBytes, v773, &dwBytes);
                            v86 = v103 | 0x10000000;
                            v772 = v103 | 0x10000000;
                            if ( v103 >= 0 )
                            {
                              HIDWORD(lpMem[0]) = dwBytes;
                              v104 = dwBytes;
                              v105 = GetProcessHeap();
                              v106 = HeapAlloc(v105, 8u, v104);
                              if ( !v106 )
                              {
                                v86 = -1073741801;
                                goto LABEL_319;
                              }
                              dwBytes_4 = 0;
                              lpMem[1] = v106;
                              LODWORD(lpMem[0]) = 0;
                              LODWORD(v791) = 0;
                              v790 = 0;
                              v776 = (size_t)v106;
                              v780 = 8;
                              v86 = RtlULongLongAdd(v106, 4, &v791);
                              v772 = v86;
                              if ( v86 >= 0 )
                              {
                                if ( v106 + 2 > (_DWORD *)((char *)lpMem[1] + HIDWORD(lpMem[0])) )
                                {
LABEL_110:
                                  v86 = -1073741789;
LABEL_114:
                                  v772 = v86;
                                  goto LABEL_119;
                                }
                                *v106 = 4;
                                *v791 = v107;
                                v109 = v780;
                                v110 = ++LODWORD(lpMem[0]);
                                LODWORD(v791) = 0;
                                v790 = 0;
                                if ( v85 )
                                {
                                  if ( !v108 )
                                    goto LABEL_113;
                                }
                                else if ( v108 )
                                {
                                  goto LABEL_113;
                                }
                                v126 = (unsigned int *)lpMem[1];
                                if ( lpMem[1] )
                                {
                                  v776 = (size_t)lpMem[1];
                                  v780 = 0;
                                  if ( v110 )
                                  {
                                    do
                                    {
                                      v773 = 0;
                                      v86 = RtlUIntAdd(4, *v126, &v773);
                                      v772 = v86;
                                      if ( v86 < 0 )
                                        goto LABEL_119;
                                      v86 = RtlULongLongAdd(v127, v773, &v776);
                                      v772 = v86;
                                      if ( v86 < 0 )
                                        goto LABEL_119;
                                      ++v780;
                                      v126 = (unsigned int *)v776;
                                    }
                                    while ( v780 < v128 );
                                  }
                                  v86 = RtlULongLongAdd(v126, 4, &v791);
                                  v772 = v86;
                                  if ( v86 < 0 )
                                    goto LABEL_119;
                                  if ( (char *)v129 + v130 + 4 > (char *)lpMem[1] + HIDWORD(lpMem[0]) )
                                    goto LABEL_110;
                                  *v129 = v130;
                                  if ( v85 )
                                    memcpy_0(v791, v85, v130);
                                }
                                else
                                {
                                  v773 = 0;
                                  v86 = RtlUIntAdd(4, v108, &v773);
                                  v772 = v86;
                                  if ( v86 < 0 )
                                    goto LABEL_119;
                                  v86 = RtlUIntAdd(HIDWORD(lpMem[0]), v773, (char *)lpMem + 4);
                                  v772 = v86;
                                  if ( v86 < 0 )
                                    goto LABEL_119;
                                }
                                v131 = ++LODWORD(lpMem[0]);
                                LODWORD(v791) = 0;
                                v790 = 0;
                                if ( v87 )
                                {
                                  if ( !v109 )
                                    goto LABEL_113;
                                }
                                else if ( v109 )
                                {
                                  goto LABEL_113;
                                }
                                v132 = (unsigned int *)lpMem[1];
                                if ( lpMem[1] )
                                {
                                  v776 = (size_t)lpMem[1];
                                  if ( v131 )
                                  {
                                    do
                                    {
                                      v773 = 0;
                                      v86 = RtlUIntAdd(4, *v132, &v773);
                                      v772 = v86;
                                      if ( v86 < 0 )
                                        goto LABEL_119;
                                      v86 = RtlULongLongAdd(v133, v773, &v776);
                                      v772 = v86;
                                      if ( v86 < 0 )
                                        goto LABEL_119;
                                      v132 = (unsigned int *)v776;
                                    }
                                    while ( v135 + 1 < v134 );
                                  }
                                  v86 = RtlULongLongAdd(v132, 4, &v791);
                                  v772 = v86;
                                  if ( v86 < 0 )
                                    goto LABEL_119;
                                  if ( (char *)v136 + v109 + 4 > (char *)lpMem[1] + HIDWORD(lpMem[0]) )
                                    goto LABEL_110;
                                  *v136 = v109;
                                  if ( v87 )
                                    memcpy_0(v791, v87, v109);
                                }
                                else
                                {
                                  v773 = 0;
                                  v86 = RtlUIntAdd(4, v109, &v773);
                                  v772 = v86;
                                  if ( v86 < 0 )
                                    goto LABEL_119;
                                  v86 = RtlUIntAdd(HIDWORD(lpMem[0]), v773, (char *)lpMem + 4);
                                  v772 = v86;
                                  if ( v86 < 0 )
                                    goto LABEL_119;
                                }
                                v137 = ++LODWORD(lpMem[0]);
                                LODWORD(v791) = 0;
                                v790 = 0;
                                v138 = (unsigned int *)lpMem[1];
                                if ( lpMem[1] )
                                {
                                  v776 = (size_t)lpMem[1];
                                  if ( v137 )
                                  {
                                    do
                                    {
                                      v773 = 0;
                                      v86 = RtlUIntAdd(4, *v138, &v773);
                                      v772 = v86;
                                      if ( v86 < 0 )
                                        goto LABEL_119;
                                      v86 = RtlULongLongAdd(v140, v773, &v776);
                                      v772 = v86;
                                      if ( v86 < 0 )
                                        goto LABEL_119;
                                      v138 = (unsigned int *)v776;
                                    }
                                    while ( v142 + 1 < v141 );
                                  }
                                  v86 = RtlULongLongAdd(v138, 4, &v791);
                                  v772 = v86;
                                  if ( v86 < 0 )
                                    goto LABEL_119;
                                  if ( v143 + 3 > (_DWORD *)((char *)lpMem[1] + HIDWORD(lpMem[0])) )
                                    goto LABEL_110;
                                  *v143 = 8;
                                  *(_QWORD *)v791 = v802;
                                }
                                else
                                {
                                  v773 = 0;
                                  v86 = RtlUIntAdd(4, 8, &v773);
                                  v772 = v86;
                                  if ( v86 < 0 )
                                    goto LABEL_119;
                                  v86 = RtlUIntAdd(HIDWORD(lpMem[0]), v773, (char *)lpMem + 4);
                                  v772 = v86;
                                  if ( v86 < 0 )
                                    goto LABEL_119;
                                }
                                ++LODWORD(lpMem[0]);
                                v776 = 0;
                                if ( StringCchLengthW(
                                       L"TerminalServices-DeviceRedirection-Licenses-TSEasyPrintAllowed",
                                       v139,
                                       &v776) < 0 )
                                {
                                  v86 = -1073741762;
                                  goto LABEL_114;
                                }
                                v86 = RtlULongLongAdd(v776, 1, &v776);
                                v772 = v86;
                                if ( v86 >= 0 )
                                {
                                  LODWORD(v791) = 0;
                                  v790 = 0;
                                  if ( !(2 * (_DWORD)v776) )
                                    goto LABEL_113;
                                  v145 = (unsigned int *)lpMem[1];
                                  if ( lpMem[1] )
                                  {
                                    v776 = (size_t)lpMem[1];
                                    v146 = 0;
                                    if ( v144 )
                                    {
                                      do
                                      {
                                        v773 = 0;
                                        v86 = RtlUIntAdd(4, *v145, &v773);
                                        v772 = v86;
                                        if ( v86 < 0 )
                                          goto LABEL_119;
                                        v86 = RtlULongLongAdd(v147, v773, &v776);
                                        v772 = v86;
                                        if ( v86 < 0 )
                                          goto LABEL_119;
                                        ++v146;
                                        v145 = (unsigned int *)v776;
                                      }
                                      while ( v146 < v148 );
                                    }
                                    v86 = RtlULongLongAdd(v145, 4, &v791);
                                    v772 = v86;
                                    if ( v86 < 0 )
                                      goto LABEL_119;
                                    if ( (char *)v149 + v150 + 4 > (char *)lpMem[1] + HIDWORD(lpMem[0]) )
                                      goto LABEL_110;
                                    *v149 = v150;
                                    memcpy_0(
                                      v791,
                                      L"TerminalServices-DeviceRedirection-Licenses-TSEasyPrintAllowed",
                                      (unsigned int)v150);
                                  }
                                  else
                                  {
                                    v773 = 0;
                                    v86 = RtlUIntAdd(4, (unsigned int)(2 * v776), &v773);
                                    v772 = v86;
                                    if ( v86 < 0 )
                                      goto LABEL_119;
                                    v86 = RtlUIntAdd(HIDWORD(lpMem[0]), v773, (char *)lpMem + 4);
                                    v772 = v86;
                                    if ( v86 < 0 )
                                      goto LABEL_119;
                                  }
                                  v151 = ++LODWORD(lpMem[0]);
                                  LODWORD(v791) = 0;
                                  v790 = 0;
                                  v152 = (unsigned int *)lpMem[1];
                                  if ( lpMem[1] )
                                  {
                                    v776 = (size_t)lpMem[1];
                                    if ( v151 )
                                    {
                                      do
                                      {
                                        v773 = 0;
                                        v86 = RtlUIntAdd(4, *v152, &v773);
                                        v772 = v86;
                                        if ( v86 < 0 )
                                          goto LABEL_119;
                                        v86 = RtlULongLongAdd(v153, v773, &v776);
                                        v772 = v86;
                                        if ( v86 < 0 )
                                          goto LABEL_119;
                                        v152 = (unsigned int *)v776;
                                      }
                                      while ( v155 + 1 < v154 );
                                    }
                                    v86 = RtlULongLongAdd(v152, 4, &v791);
                                    v772 = v86;
                                    if ( v86 < 0 )
                                      goto LABEL_119;
                                    if ( v156 + 2 > (_DWORD *)((char *)lpMem[1] + HIDWORD(lpMem[0])) )
                                      goto LABEL_110;
                                    *v156 = 4;
                                    *v791 = 0;
                                  }
                                  else
                                  {
                                    v773 = 0;
                                    v86 = RtlUIntAdd(4, 4, &v773);
                                    v772 = v86;
                                    if ( v86 < 0 )
                                      goto LABEL_119;
                                    v86 = RtlUIntAdd(HIDWORD(lpMem[0]), v773, (char *)lpMem + 4);
                                    v772 = v86;
                                    if ( v86 < 0 )
                                      goto LABEL_119;
                                  }
                                  v157 = ++LODWORD(lpMem[0]);
                                  LODWORD(v791) = 0;
                                  v790 = 0;
                                  v158 = (unsigned int *)lpMem[1];
                                  if ( lpMem[1] )
                                  {
                                    v776 = (size_t)lpMem[1];
                                    if ( v157 )
                                    {
                                      do
                                      {
                                        v773 = 0;
                                        v86 = RtlUIntAdd(4, *v158, &v773);
                                        v772 = v86;
                                        if ( v86 < 0 )
                                          goto LABEL_119;
                                        v86 = RtlULongLongAdd(v159, v773, &v776);
                                        v772 = v86;
                                        if ( v86 < 0 )
                                          goto LABEL_119;
                                        v158 = (unsigned int *)v776;
                                      }
                                      while ( v161 + 1 < v160 );
                                    }
                                    v86 = RtlULongLongAdd(v158, 4, &v791);
                                    v772 = v86;
                                    if ( v86 < 0 )
                                      goto LABEL_119;
                                    if ( v162 + 2 > (_DWORD *)((char *)lpMem[1] + HIDWORD(lpMem[0])) )
                                      goto LABEL_110;
                                    *v162 = 4;
                                    *v791 = 4;
                                  }
                                  else
                                  {
                                    v773 = 0;
                                    v86 = RtlUIntAdd(4, 4, &v773);
                                    v772 = v86;
                                    if ( v86 < 0 )
                                      goto LABEL_119;
                                    v86 = RtlUIntAdd(HIDWORD(lpMem[0]), v773, (char *)lpMem + 4);
                                    v772 = v86;
                                    if ( v86 < 0 )
                                      goto LABEL_119;
                                  }
                                  ++LODWORD(lpMem[0]);
                                  v773 = 0;
                                  v86 = RtlUIntAdd(4, 4, &v773);
                                  v772 = v86;
                                  if ( v86 < 0 )
                                    goto LABEL_119;
                                  v778 = v773;
                                  v773 = 0;
                                  v86 = RtlUIntAdd(v163, 8, &v773);
                                  v772 = v86;
                                  if ( v86 < 0 )
                                    goto LABEL_119;
                                  v86 = RtlUIntAdd(v164, v773, &v778);
                                  v772 = v86;
                                  if ( v86 < 0 )
                                    goto LABEL_119;
                                  v773 = 0;
                                  v86 = RtlUIntAdd(4, 4, &v773);
                                  v772 = v86;
                                  if ( v86 < 0 )
                                    goto LABEL_119;
                                  v86 = RtlUIntAdd(v778, v773, &v778);
                                  v772 = v86;
                                  if ( v86 < 0 )
                                    goto LABEL_119;
                                  v773 = 0;
                                  v86 = RtlUIntAdd(4, 4, &v773);
                                  v772 = v86;
                                  if ( v86 < 0 )
                                    goto LABEL_119;
                                  v86 = RtlUIntAdd(v778, v773, &v778);
                                  v772 = v86;
                                  if ( v86 < 0 )
                                    goto LABEL_119;
                                  v773 = 0;
                                  v86 = RtlUIntAdd(4, 4, &v773);
                                  v772 = v86;
                                  if ( v86 < 0 )
                                    goto LABEL_119;
                                  v86 = RtlUIntAdd(v778, v773, &v778);
                                  v772 = v86;
                                  if ( v86 < 0 )
                                    goto LABEL_119;
                                  v773 = 0;
                                  v86 = RtlUIntAdd(4, 4, &v773);
                                  v772 = v86;
                                  if ( v86 < 0 )
                                    goto LABEL_119;
                                  v86 = RtlUIntAdd(v778, v773, &v778);
                                  v772 = v86;
                                  if ( v86 < 0 )
                                    goto LABEL_119;
                                  v780 = 0;
                                  dwBytes = v778;
                                  v777 = 0;
                                  v794 = __rdtsc();
                                  v773 = 0;
                                  v808 = 8;
                                  v166 = RtlUIntAdd(8, HIDWORD(lpMem[0]), &v808);
                                  if ( v166 < 0 )
                                  {
                                    v786 = v87;
                                    v800 = v85;
                                  }
                                  else
                                  {
                                    v167 = (v808 + 7) & 0xFFFFFFF8;
                                    if ( v167 < v808 )
                                    {
                                      v86 = -805306219;
                                      goto LABEL_319;
                                    }
                                    v808 = (v808 + 7) & 0xFFFFFFF8;
                                    v168 = v167;
                                    v169 = GetProcessHeap();
                                    v170 = (char *)HeapAlloc(v169, 8u, v168);
                                    v171 = v170;
                                    if ( !v170 )
                                    {
                                      v86 = -805306345;
                                      v772 = -805306345;
LABEL_316:
                                      if ( v86 < 0 )
                                        goto LABEL_119;
                                      if ( !v780 )
                                        goto LABEL_318;
                                      if ( !v789 )
                                        goto LABEL_113;
                                      v794 = (SIZE_T)v789;
                                      v86 = RtlULongLongAdd(v789, 4, &v794);
                                      v772 = v86;
                                      v789 = v411;
                                      if ( v86 >= 0 )
                                      {
                                        v413 = (int *)v794;
                                        if ( !*v411 )
                                          v413 = 0;
                                        if ( *v411 != 4 )
                                          goto LABEL_110;
                                        v86 = *v413;
                                        v772 = v86;
                                        if ( v86 == -805306333 )
                                        {
                                          v414 = -2147024774;
                                          dwBytes_4 = -2147024774;
                                        }
                                        else
                                        {
                                          v414 = v86;
                                          dwBytes_4 = v86;
                                          if ( v86 != -2147024774 && v86 < 0 )
                                            goto LABEL_119;
                                        }
                                        v789 = v411;
                                        if ( v412 != 6 )
                                        {
LABEL_318:
                                          v86 = -1073425151;
                                          goto LABEL_319;
                                        }
                                        v776 = v410;
                                        do
                                        {
                                          v86 = RtlULongLongAdd(v410, 4, &v776);
                                          v772 = v86;
                                          if ( v86 < 0 )
                                            goto LABEL_119;
                                          v86 = RtlULongLongAdd(v776, v415, &v776);
                                          v772 = v86;
                                          if ( v86 < 0 )
                                            goto LABEL_119;
                                          v410 = v776;
                                        }
                                        while ( v416 == -1 );
                                        v86 = RtlULongLongAdd(v776, 4, &v776);
                                        v772 = v86;
                                        if ( v86 >= 0 )
                                        {
                                          v419 = (LPVOID *)v776;
                                          if ( !v418 )
                                            v419 = 0;
                                          if ( v418 != 8 )
                                            goto LABEL_110;
                                          dwBytes_4 = v414;
                                          v789 = v417;
                                          if ( !v417 )
                                            goto LABEL_113;
                                          v420 = (size_t)v417;
                                          v776 = (size_t)v417;
                                          v790 = *v419;
                                          do
                                          {
                                            v86 = RtlULongLongAdd(v420, 4, &v776);
                                            v772 = v86;
                                            if ( v86 < 0 )
                                              goto LABEL_119;
                                            v86 = RtlULongLongAdd(v776, v421, &v776);
                                            v772 = v86;
                                            if ( v86 < 0 )
                                              goto LABEL_119;
                                            v420 = v776;
                                          }
                                          while ( (unsigned int)(v422 + 1) < 2 );
                                          v86 = RtlULongLongAdd(v776, 4, &v776);
                                          v772 = v86;
                                          if ( v86 < 0 )
                                            goto LABEL_119;
                                          v425 = (unsigned int *)v776;
                                          if ( !v424 )
                                            v425 = 0;
                                          if ( v424 != 4 )
                                            goto LABEL_110;
                                          dwBytes_4 = v414;
                                          v789 = v423;
                                          if ( !v423 )
                                          {
LABEL_113:
                                            v86 = -1073741811;
                                            goto LABEL_114;
                                          }
                                          v426 = (size_t)v423;
                                          v776 = (size_t)v423;
                                          v795 = *v425;
                                          do
                                          {
                                            v86 = RtlULongLongAdd(v426, 4, &v776);
                                            v772 = v86;
                                            if ( v86 < 0 )
                                              goto LABEL_119;
                                            v86 = RtlULongLongAdd(v776, v427, &v776);
                                            v772 = v86;
                                            if ( v86 < 0 )
                                              goto LABEL_119;
                                            v426 = v776;
                                          }
                                          while ( (unsigned int)(v428 + 1) < 3 );
                                          v86 = RtlULongLongAdd(v776, 4, &v776);
                                          v772 = v86;
                                          if ( v86 >= 0 )
                                          {
                                            v431 = 0;
                                            if ( v430 )
                                              v431 = (const void *)v776;
                                            v432 = (unsigned int *)v429;
                                            v776 = v429;
                                            do
                                            {
                                              v433 = *v432;
                                              v86 = RtlULongLongAdd(v432, 4, &v776);
                                              v772 = v86;
                                              if ( v86 < 0 )
                                                goto LABEL_119;
                                              v86 = RtlULongLongAdd(v776, v433, &v776);
                                              v772 = v86;
                                              if ( v86 < 0 )
                                                goto LABEL_119;
                                              v432 = (unsigned int *)v776;
                                            }
                                            while ( (unsigned int)(v434 + 1) < 4 );
                                            v86 = RtlULongLongAdd(v776, 4, &v776);
                                            v772 = v86;
                                            if ( v86 >= 0 )
                                            {
                                              v437 = (unsigned int *)v776;
                                              if ( !v436 )
                                                v437 = 0;
                                              if ( v436 != 4 )
                                                goto LABEL_110;
                                              v789 = v435;
                                              if ( !v435 )
                                              {
                                                v86 = -1073741811;
                                                goto LABEL_319;
                                              }
                                              v438 = (size_t)v435;
                                              v776 = (size_t)v435;
                                              v439 = *v437;
                                              do
                                              {
                                                v86 = RtlULongLongAdd(v438, 4, &v776);
                                                v772 = v86;
                                                if ( v86 < 0 )
                                                  goto LABEL_119;
                                                v86 = RtlULongLongAdd(v776, v440, &v776);
                                                v772 = v86;
                                                if ( v86 < 0 )
                                                  goto LABEL_119;
                                                v438 = v776;
                                              }
                                              while ( (unsigned int)(v441 + 1) < 5 );
                                              v111 = RtlULongLongAdd(v776, 4, &v776);
                                              v86 = v111;
                                              v772 = v111;
                                              if ( v111 < 0 )
                                              {
LABEL_118:
                                                v772 = v111;
                                                goto LABEL_119;
                                              }
                                              v445 = (int *)v776;
                                              if ( !v442 )
                                                v445 = 0;
                                              if ( v442 != v443 )
                                              {
                                                v86 = -1073741789;
                                                goto LABEL_319;
                                              }
                                              if ( (LPVOID)v802 != v790 )
                                                goto LABEL_318;
                                              v824 = *v445;
                                              v821 = v795;
                                              if ( v439 > v443 || (unsigned int)v444 > v443 )
                                              {
                                                v86 = -2147024774;
                                                goto LABEL_319;
                                              }
                                              memcpy_0(TickCount64, v431, v444);
                                              v111 = dwBytes_4;
                                              if ( dwBytes_4 )
                                              {
                                                v86 = dwBytes_4;
                                                goto LABEL_118;
                                              }
                                            }
                                          }
                                        }
                                      }
                                      goto LABEL_119;
                                    }
                                    v800 = v85;
                                    v786 = v87;
                                    v776 = (size_t)v170;
                                    *(_DWORD *)v170 = lpMem[0];
                                    v166 = RtlULongLongAdd(v170, 4, &v776);
                                    if ( v166 < 0
                                      || (v174 = v776,
                                          *(_DWORD *)v776 = HIDWORD(lpMem[0]),
                                          v166 = RtlULongLongAdd(v174, v173, &v776),
                                          v166 < 0) )
                                    {
                                      v800 = v85;
                                      v786 = v87;
                                      dwBytes = v172;
                                      v175 = GetProcessHeap();
                                      HeapFree(v175, 0, v171);
                                      v165 = v773;
                                    }
                                    else
                                    {
                                      *(_QWORD *)&v171[v808 - 8] = v794;
                                      memcpy_0((void *)v776, lpMem[1], HIDWORD(lpMem[0]));
                                      v777 = v171;
                                      v165 = v808;
                                    }
                                  }
                                  v176 = 0;
                                  pcchLength = 0;
                                  v177 = 0;
                                  v788 = 0;
                                  v785 = 0;
                                  v792 = 0;
                                  v86 = v166 | 0x10000000;
                                  v772 = v86;
                                  if ( v86 < 0 )
                                    goto LABEL_291;
                                  v178 = (unsigned __int8 *)v777;
                                  if ( !v777 )
                                  {
                                    v86 = -805306355;
                                    goto LABEL_319;
                                  }
                                  v806 = (void *)v165;
                                  if ( !v165 || (Size = v165 + 8LL, v179 = MemoryAlloc(Size), (Src = v179) == 0) )
                                  {
                                    v86 = -805306367;
                                    v772 = -805306367;
                                    goto LABEL_293;
                                  }
                                  v793 = 0;
                                  v180 = 0;
                                  v779 = 0;
                                  v181 = 0;
                                  v182 = (unsigned __int64)v806;
                                  if ( v806 )
                                  {
                                    do
                                      v180 ^= v178[v181++];
                                    while ( v181 < (unsigned __int64)v806 );
                                    v779 = v180;
                                  }
                                  v787 = (LPVOID)0xC81ECB17B1B54A58LL;
                                  v183 = v178;
                                  v776 = (size_t)v178;
                                  v807 = (SIZE_T)v179;
                                  v184 = (unsigned __int8)v806 & 7;
                                  if ( ((unsigned __int8)v806 & 7) != 0 )
                                  {
                                    v185 = 0;
                                    LODWORD(v784) = 0;
                                    v778 = 0;
                                    v186 = 0;
                                    v187 = 0;
                                    do
                                    {
                                      v188 = *v183++;
                                      v773 = 8 * v186;
                                      if ( v186 >= 4 )
                                        v185 |= v188 << (56 - v773);
                                      else
                                        v187 |= v188 << (24 - v773);
                                      ++v186;
                                    }
                                    while ( (int)v186 < v184 );
                                    v778 = v187;
                                    LODWORD(v784) = v185;
                                    v776 = (size_t)v183;
                                    v777 = v178;
                                    v786 = v87;
                                    v800 = v85;
                                    v182 = (unsigned __int64)v806;
                                    v189 = v187 ^ 0xB17A307A;
                                    v190 = v185 ^ 0x42F6B18D;
                                    v191 = v187 ^ 0xB17A307A;
                                    v192 = v190;
                                    v773 = 0;
                                    if ( ((unsigned __int8)v806 & 7) != 0 )
                                    {
                                      v193 = (_BYTE *)v807;
                                      do
                                      {
                                        v794 = (SIZE_T)(v193 + 1);
                                        if ( v773 >= 4 )
                                        {
                                          v192 = __ROR4__(v192, 24);
                                          v194 = v192;
                                        }
                                        else
                                        {
                                          v191 = __ROR4__(v191, 24);
                                          v194 = v191;
                                        }
                                        *v193 = v194;
                                        ++v773;
                                        v193 = (_BYTE *)v794;
                                      }
                                      while ( (int)v773 < v184 );
                                      v807 = v794;
                                    }
                                    if ( (unsigned int)v184 <= 4 )
                                    {
                                      v195 = 0;
                                      if ( (unsigned int)v184 < 4 )
                                        v189 = v189 >> (8 * (4 - v184)) << (8 * (4 - v184));
                                    }
                                    else
                                    {
                                      v195 = v190 >> (8 * (8 - v184)) << (8 * (8 - v184));
                                    }
                                    v183 = (unsigned __int8 *)v776;
                                  }
                                  else
                                  {
                                    v189 = 0;
                                    v195 = -1;
                                    v778 = 0;
                                    LODWORD(v784) = 0;
                                  }
                                  if ( v182 >> 3 )
                                  {
                                    v794 = 0;
                                    v773 = 19032;
                                    v772 = WORD1(v787);
                                    v196 = WORD2(v787);
                                    v795 = HIDWORD(v787) ^ 0xB1B54A58;
                                    v197 = (_BYTE *)v807;
                                    v198 = v182 >> 3;
                                    v199 = v784;
                                    v200 = v778;
                                    v201 = HIDWORD(v787) ^ 0xB1B54A58;
                                    do
                                    {
                                      v202 = v183[3] | ((v183[2] | ((v183[1] | (*v183 << 8)) << 8)) << 8);
                                      v203 = *(unsigned __int8 *)(v776 + 7)
                                           | ((*(unsigned __int8 *)(v776 + 6)
                                             | ((*(unsigned __int8 *)(v776 + 5) | (v183[4] << 8)) << 8)) << 8);
                                      v204 = v195 ^ v203;
                                      v776 += 8LL;
                                      v205 = v189 ^ v202 ^ ((v195 ^ v203) - v773);
                                      v206 = HIDWORD(v787) ^ v205;
                                      v207 = v204
                                           ^ (__ROR4__(HIDWORD(v787) ^ v205, 7) + WORD1(v787) * __ROR4__(v205, 15));
                                      v208 = v206 ^ (v196 * __ROR4__(v207 - 1313519016, 9) - __ROR4__(v207, 10));
                                      v209 = v207 ^ (__ROR4__(v208, 27) + HIWORD(v787) * __ROR4__(v196 ^ v208, 28));
                                      v210 = v208 ^ (HIDWORD(v787) - (v209 ^ 0xB1B54A58));
                                      v211 = v209 ^ (WORD1(v787) * (v210 - v773) - (v210 >> 6));
                                      v212 = v210 ^ (v773 * (v196 ^ __ROR4__(v211, 15)));
                                      v213 = v211 ^ (v196 * (HIWORD(v787) + __ROR4__(~v212, 3)));
                                      v214 = v212 ^ (v213 - v773 - HIDWORD(v787));
                                      v215 = v213 ^ (v772 * (v214 ^ HIWORD(v787))) ^ __ROR4__(v214, 10);
                                      v216 = v214 ^ __ROR4__(v215, 3) ^ (v196 * __ROR4__(v215 ^ v773, 26));
                                      v217 = v215 ^ (v773 * (__ROR4__(v216, 15) - HIWORD(v787)));
                                      v218 = v216
                                           ^ (v773 * (v217 ^ HIWORD(v787)))
                                           ^ ((v217 ^ (v217 >> 14)) >> 1)
                                           ^ (v773 * ((8 * (v217 - v196)) | ((unsigned __int64)(v217 - v196) >> 29)));
                                      v219 = v217 ^ (WORD1(v787) * (v218 - v196) - (v218 >> 13));
                                      v220 = v218 ^ __ROR4__(v219, 11) ^ (v196 * __ROR4__(-1313519016 - v219, 9));
                                      v221 = v219 ^ (v220 - HIWORD(v787) + 1313519016);
                                      v222 = v220 ^ (v773 * (v772 ^ v221) - __ROR4__(v221, 7));
                                      v223 = v221
                                           ^ (WORD1(v787) * __ROR4__(HIWORD(v787) ^ v222, 28) - __ROR4__(v222, 16));
                                      v224 = v222 ^ (__ROR4__(v223, 4) + v196 * __ROR4__(-1313519016 - v223, 10));
                                      v225 = v223 ^ __ROR4__(v224, 9) ^ (HIWORD(v787) * __ROR4__(v224 + 1313519016, 4));
                                      v226 = v224 ^ (v773 * __ROR4__(HIDWORD(v787) ^ v225, 24) - __ROR4__(v225, 30));
                                      v227 = v225
                                           ^ (WORD1(v787) * __ROR4__(HIDWORD(v787) - v226, 11) - __ROR4__(v226, 12));
                                      v228 = v226 ^ (v227 >> 8) ^ (v196 * (v227 ^ WORD1(v787)));
                                      v189 = v228 ^ v200;
                                      v195 = v201 ^ v227 ^ v228 ^ v199;
                                      v197[3] = v228 ^ v200;
                                      v197[7] = v201 ^ v227 ^ v228 ^ v199;
                                      v197[2] = __ROR4__(v228 ^ v200, 8);
                                      v197[6] = __ROR4__(v195, 8);
                                      v197[1] = __ROR4__(v228 ^ v200, 16);
                                      v197[5] = __ROR4__(v195, 16);
                                      *v197 = __ROR4__(v228 ^ v200, 24);
                                      v197[4] = __ROR4__(v195, 24);
                                      v200 = v202;
                                      v199 = v203;
                                      v197 += 8;
                                      ++v794;
                                      v183 = (unsigned __int8 *)v776;
                                    }
                                    while ( v794 < v198 );
                                    v180 = v779;
                                    v85 = v800;
                                    v87 = v786;
                                    v177 = (unsigned int *)v788;
                                    v176 = (unsigned int *)v788;
                                    v178 = (unsigned __int8 *)v777;
                                    v182 = (unsigned __int64)v806;
                                  }
                                  *(_QWORD *)((char *)Src + v182) = v180;
                                  v229 = GetProcessHeap();
                                  v230 = HeapAlloc(v229, 8u, 0x30u);
                                  v786 = v230;
                                  if ( v230 )
                                  {
                                    *v230 = Size;
                                    v232 = GetProcessHeap();
                                    v233 = HeapAlloc(v232, 8u, (unsigned int)Size);
                                    if ( !v233 )
                                      goto LABEL_266;
                                    v777 = v178;
                                    v234 = v786;
                                    *((_QWORD *)v786 + 1) = v233;
                                    memcpy_0(v233, Src, (unsigned int)Size);
                                    v234[4] = 160;
                                    v235 = GetProcessHeap();
                                    v236 = HeapAlloc(v235, 8u, 0xA0u);
                                    if ( !v236 )
                                      goto LABEL_266;
                                    *((_QWORD *)v234 + 3) = v236;
                                    *v236 = xmmword_1801284E0;
                                    v236[1] = xmmword_1801284F0;
                                    v236[2] = xmmword_180128500;
                                    v236[3] = xmmword_180128510;
                                    v236[4] = xmmword_180128520;
                                    v236[5] = xmmword_180128530;
                                    v236[6] = xmmword_180128540;
                                    v236[7] = xmmword_180128550;
                                    v236[8] = xmmword_180128560;
                                    v236[9] = xmmword_180128570;
                                    v234[8] = 8;
                                    v237 = GetProcessHeap();
                                    v238 = HeapAlloc(v237, 8u, 8u);
                                    if ( v238 )
                                    {
                                      *((_QWORD *)v234 + 5) = v238;
                                      *v238 = qword_180128580;
                                      v793 = v234;
                                      v231 = 0;
                                      v176 = (unsigned int *)v793;
                                      v793 = 0;
                                    }
                                    else
                                    {
LABEL_266:
                                      v231 = -1073741801;
                                      v239 = v786;
                                      v790 = (LPVOID)*((_QWORD *)v786 + 1);
                                      if ( v790 )
                                      {
                                        v240 = GetProcessHeap();
                                        HeapFree(v240, 0, v790);
                                        v239 = v786;
                                        *((_QWORD *)v786 + 1) = 0;
                                      }
                                      v790 = (LPVOID)v239[3];
                                      if ( v790 )
                                      {
                                        v241 = GetProcessHeap();
                                        HeapFree(v241, 0, v790);
                                        v239 = v786;
                                        *((_QWORD *)v786 + 3) = 0;
                                      }
                                      v790 = (LPVOID)v239[5];
                                      if ( v790 )
                                      {
                                        v242 = GetProcessHeap();
                                        HeapFree(v242, 0, v790);
                                        *((_QWORD *)v786 + 5) = 0;
                                      }
                                      v243 = GetProcessHeap();
                                      HeapFree(v243, 0, v786);
                                    }
                                  }
                                  else
                                  {
                                    v231 = -1073741801;
                                  }
                                  v244 = GetProcessHeap();
                                  HeapFree(v244, 0, Src);
                                  v245 = v793;
                                  if ( v793 )
                                  {
                                    v790 = (LPVOID)*((_QWORD *)v793 + 1);
                                    if ( v790 )
                                    {
                                      v246 = GetProcessHeap();
                                      HeapFree(v246, 0, v790);
                                      v245 = v793;
                                      *((_QWORD *)v793 + 1) = 0;
                                    }
                                    v790 = (LPVOID)v245[3];
                                    if ( v790 )
                                    {
                                      v247 = GetProcessHeap();
                                      HeapFree(v247, 0, v790);
                                      v245 = v793;
                                      *((_QWORD *)v793 + 3) = 0;
                                    }
                                    v790 = (LPVOID)v245[5];
                                    if ( v790 )
                                    {
                                      v248 = GetProcessHeap();
                                      HeapFree(v248, 0, v790);
                                      *((_QWORD *)v793 + 5) = 0;
                                    }
                                    v249 = GetProcessHeap();
                                    HeapFree(v249, 0, v793);
                                  }
                                  v86 = v231 | 0x10000000;
                                  v772 = v86;
                                  if ( v86 < 0 )
                                  {
                                    v256 = v777;
LABEL_292:
                                    if ( !v256 )
                                    {
LABEL_294:
                                      if ( v176 )
                                      {
                                        v790 = (LPVOID)*((_QWORD *)v176 + 1);
                                        if ( v790 )
                                        {
                                          v258 = GetProcessHeap();
                                          HeapFree(v258, 0, v790);
                                          *((_QWORD *)v176 + 1) = 0;
                                        }
                                        v790 = (LPVOID)*((_QWORD *)v176 + 3);
                                        if ( v790 )
                                        {
                                          v259 = GetProcessHeap();
                                          HeapFree(v259, 0, v790);
                                          *((_QWORD *)v176 + 3) = 0;
                                        }
                                        v790 = (LPVOID)*((_QWORD *)v176 + 5);
                                        if ( v790 )
                                        {
                                          v260 = GetProcessHeap();
                                          HeapFree(v260, 0, v790);
                                          *((_QWORD *)v176 + 5) = 0;
                                        }
                                        v261 = GetProcessHeap();
                                        HeapFree(v261, 0, v176);
                                      }
                                      v262 = (void *)pcchLength;
                                      if ( pcchLength )
                                      {
                                        v263 = GetProcessHeap();
                                        HeapFree(v263, 0, v262);
                                      }
                                      if ( v177 )
                                      {
                                        v264 = GetProcessHeap();
                                        HeapFree(v264, 0, v177);
                                      }
                                      v265 = v785;
                                      if ( v785 )
                                      {
                                        v266 = (void *)*((_QWORD *)v785 + 1);
                                        if ( v266 )
                                        {
                                          v267 = GetProcessHeap();
                                          HeapFree(v267, 0, v266);
                                          v265[1] = 0;
                                        }
                                        v268 = (void *)v265[3];
                                        if ( v268 )
                                        {
                                          v269 = GetProcessHeap();
                                          HeapFree(v269, 0, v268);
                                          v265[3] = 0;
                                        }
                                        v270 = (void *)v265[5];
                                        if ( v270 )
                                        {
                                          v271 = GetProcessHeap();
                                          HeapFree(v271, 0, v270);
                                          v265[5] = 0;
                                        }
                                        v272 = GetProcessHeap();
                                        HeapFree(v272, 0, v265);
                                      }
                                      v273 = v792;
                                      if ( v792 )
                                      {
                                        v274 = GetProcessHeap();
                                        HeapFree(v274, 0, v273);
                                      }
                                      goto LABEL_316;
                                    }
LABEL_293:
                                    v257 = GetProcessHeap();
                                    HeapFree(v257, 0, v777);
                                    goto LABEL_294;
                                  }
                                  LODWORD(v784) = 0;
                                  v772 = 4;
                                  v251 = RtlUIntAdd(4, *v176, &v772);
                                  if ( v251 >= 0 )
                                  {
                                    v251 = RtlUIntAdd(v772, v250, &v772);
                                    if ( v251 >= 0 )
                                    {
                                      v794 = (SIZE_T)(v176 + 4);
                                      v251 = RtlUIntAdd(v772, v176[4], &v772);
                                      if ( v251 >= 0 )
                                      {
                                        v251 = RtlUIntAdd(v772, v252, &v772);
                                        if ( v251 >= 0 )
                                        {
                                          Src = v176 + 8;
                                          v251 = RtlUIntAdd(v772, v176[8], &v772);
                                          if ( v251 >= 0 )
                                          {
                                            v783 = v176;
                                            v253 = v772;
                                            v254 = GetProcessHeap();
                                            v255 = HeapAlloc(v254, 8u, v253);
                                            v786 = v255;
                                            v176 = v783;
                                            if ( !v255 )
                                            {
                                              v86 = -805306345;
LABEL_290:
                                              v772 = v86;
LABEL_291:
                                              v256 = v777;
                                              goto LABEL_292;
                                            }
                                            v788 = v255;
                                            *v255 = *v783;
                                            v251 = RtlULongLongAdd(v255, 4, &v788);
                                            if ( v251 < 0 )
                                            {
                                              v777 = v276;
                                              dwBytes = v277;
                                              v786 = v275;
                                            }
                                            else
                                            {
                                              memcpy_0(v788, *((const void **)v176 + 1), *v176);
                                              v251 = RtlULongLongAdd(v788, *v176, &v788);
                                              if ( v251 >= 0 )
                                              {
                                                v278 = v788;
                                                *(_DWORD *)v788 = *(_DWORD *)v794;
                                                v251 = RtlULongLongAdd(v278, 4, &v788);
                                                if ( v251 >= 0 )
                                                {
                                                  memcpy_0(v788, *((const void **)v176 + 3), *v279);
                                                  v251 = RtlULongLongAdd(v788, *(unsigned int *)v794, &v788);
                                                  if ( v251 >= 0 )
                                                  {
                                                    v280 = v788;
                                                    *(_DWORD *)v788 = *(_DWORD *)Src;
                                                    v251 = RtlULongLongAdd(v280, 4, &v788);
                                                    if ( v251 >= 0 )
                                                    {
                                                      memcpy_0(v788, *((const void **)v176 + 5), *v281);
                                                      v251 = RtlULongLongAdd(v788, *(unsigned int *)Src, &v788);
                                                      if ( v251 >= 0 )
                                                      {
                                                        pcchLength = (size_t)v786;
                                                        LODWORD(v784) = v772;
                                                        goto LABEL_331;
                                                      }
                                                    }
                                                  }
                                                }
                                              }
                                            }
                                            v282 = GetProcessHeap();
                                            HeapFree(v282, 0, v786);
                                          }
                                        }
                                      }
                                    }
                                  }
LABEL_331:
                                  v86 = v251 | 0x10000000;
                                  v772 = v86;
                                  if ( v86 < 0 )
                                    goto LABEL_291;
                                  v815 = 8;
                                  v283 = RtlUIntAdd(8, dwBytes, &v815);
                                  v86 = v283 | 0x10000000;
                                  v772 = v283 | 0x10000000;
                                  if ( v283 < 0 )
                                    goto LABEL_291;
                                  v284 = (v815 + 7) & 0xFFFFFFF8;
                                  if ( (unsigned int)v284 < v815 )
                                  {
                                    v86 = -1073741675;
                                    goto LABEL_290;
                                  }
                                  v825 = (v815 + 7) & 0xFFFFFFF8;
                                  v86 = RtlUIntAdd(v284, 8, &v825);
                                  v772 = v86;
                                  if ( v86 < 0 )
                                    goto LABEL_291;
                                  v800 = v85;
                                  v786 = v87;
                                  v777 = v285;
                                  v783 = v176;
                                  v773 = 0;
                                  v286 = lpMem[1];
                                  if ( !lpMem[1] )
                                    goto LABEL_344;
                                  v783 = v176;
                                  v777 = v285;
                                  v786 = v87;
                                  v800 = v85;
                                  if ( LODWORD(lpMem[0]) <= 1 )
                                    goto LABEL_344;
                                  v776 = (size_t)lpMem[1];
                                  do
                                  {
                                    v86 = RtlULongLongAdd(v286, 4, &v776);
                                    v772 = v86;
                                    if ( v86 < 0 )
                                      goto LABEL_291;
                                    v86 = RtlULongLongAdd(v776, v287, &v776);
                                    v772 = v86;
                                    if ( v86 < 0 )
                                      goto LABEL_291;
                                    v286 = (LPVOID)v776;
                                  }
                                  while ( v288 == -1 );
                                  v795 = *(_DWORD *)v776;
                                  v86 = RtlULongLongAdd(v776, 4, &v776);
                                  v772 = v86;
                                  if ( v86 < 0 )
                                    goto LABEL_291;
                                  v289 = lpMem[1];
                                  if ( !lpMem[1] || LODWORD(lpMem[0]) <= 2 )
                                  {
LABEL_344:
                                    v86 = -1073741811;
                                    v772 = -1073741811;
                                    goto LABEL_291;
                                  }
                                  v776 = (size_t)lpMem[1];
                                  do
                                  {
                                    v86 = RtlULongLongAdd(v289, 4, &v776);
                                    v772 = v86;
                                    if ( v86 < 0 )
                                      goto LABEL_291;
                                    v86 = RtlULongLongAdd(v776, v293, &v776);
                                    v772 = v86;
                                    if ( v86 < 0 )
                                      goto LABEL_291;
                                    v289 = (LPVOID)v776;
                                  }
                                  while ( (unsigned int)(v294 + 1) < 2 );
                                  v86 = RtlULongLongAdd(v776, 4, &v776);
                                  v772 = v86;
                                  if ( v86 < 0 )
                                    goto LABEL_291;
                                  v773 = v295;
                                  v778 = v296;
                                  v86 = RtlUIntAdd(v296, v825, &v778);
                                  v772 = v86;
                                  if ( v86 < 0 )
                                    goto LABEL_291;
                                  v86 = RtlUIntAdd(v778, v297, &v778);
                                  v772 = v86;
                                  if ( v86 < 0 )
                                    goto LABEL_291;
                                  v86 = RtlUIntAdd(v778, v795, &v778);
                                  v772 = v86;
                                  if ( v86 < 0 )
                                    goto LABEL_291;
                                  v86 = RtlUIntAdd(v778, v298, &v778);
                                  v772 = v86;
                                  if ( v86 < 0 )
                                    goto LABEL_291;
                                  v86 = RtlUIntAdd(v778, v299, &v778);
                                  v772 = v86;
                                  if ( v86 < 0 )
                                    goto LABEL_291;
                                  v773 = v778;
                                  if ( v778 > 0x400000 )
                                  {
                                    v86 = -2147418113;
                                    goto LABEL_290;
                                  }
                                  v290 = v778;
                                  v291 = GetProcessHeap();
                                  v292 = (unsigned int *)HeapAlloc(v291, 8u, v290);
                                  v177 = v292;
                                  if ( !v292 )
                                  {
                                    v86 = -805306345;
LABEL_348:
                                    v772 = v86;
LABEL_349:
                                    v176 = v783;
                                    goto LABEL_291;
                                  }
                                  v859 = 0;
                                  v860 = 0;
                                  phModule = 0;
                                  if ( !pcchLength )
                                  {
                                    v86 = -2147024809;
                                    goto LABEL_348;
                                  }
                                  *(_QWORD *)&v859 = pcchLength;
                                  LODWORD(v860) = v784;
                                  *((_QWORD *)&v859 + 1) = v292;
                                  *(_QWORD *)((char *)&v860 + 4) = v773;
                                  if ( GetModuleHandleExW(1u, L"ntdll.dll", &phModule)
                                    && (ProcAddress = GetProcAddress(phModule, "NtQuerySystemInformation")) != 0 )
                                  {
                                    v302 = ((__int64 (__fastcall *)(__int64, __int128 *))ProcAddress)(134, &v859);
                                    v86 = v302 | 0x10000000;
                                    v772 = v302 | 0x10000000;
                                    if ( v302 >= 0 )
                                    {
                                      v303 = DWORD1(v860);
                                      goto LABEL_379;
                                    }
                                  }
                                  else
                                  {
                                    v300 = GetLastError();
                                    v772 = v300;
                                    v86 = v300;
                                    if ( v300 > 0 )
                                    {
                                      v86 = (unsigned __int16)v300 | 0x80070000;
                                      v772 = v86;
                                    }
                                    if ( v86 >= 0 )
                                    {
                                      v86 = -2147467259;
                                      goto LABEL_348;
                                    }
                                  }
                                  if ( v86 == -805306333 )
                                  {
                                    v86 = -2147024774;
                                    goto LABEL_348;
                                  }
                                  if ( v86 < 0 )
                                    goto LABEL_349;
                                  v303 = v773;
LABEL_379:
                                  dwBytes = 0;
                                  v788 = v177;
                                  if ( v303 < 4 )
                                  {
LABEL_380:
                                    v86 = -805306306;
                                    goto LABEL_348;
                                  }
                                  v304 = *v177;
                                  v795 = *v177;
                                  v306 = RtlULongLongAdd(v177, 4, &v788);
                                  if ( v306 >= 0 )
                                  {
                                    v306 = RtlUIntAdd(0, v305, &dwBytes);
                                    if ( v306 < 0 )
                                    {
LABEL_433:
                                      v788 = v177;
                                      v176 = v783;
                                      goto LABEL_434;
                                    }
                                    if ( v308 - dwBytes < (unsigned int)v304 )
                                      goto LABEL_380;
                                    Src = v788;
                                    v794 = v304;
                                    v306 = RtlULongLongAdd(v788, (unsigned int)v304, &v788);
                                    if ( v306 >= 0 )
                                    {
                                      v306 = RtlUIntAdd(dwBytes, (unsigned int)v304, &dwBytes);
                                      if ( v306 >= 0 )
                                      {
                                        if ( v309 - dwBytes < (unsigned int)v310 )
                                          goto LABEL_380;
                                        v773 = *(_DWORD *)v788;
                                        v306 = RtlULongLongAdd(v788, v310, &v788);
                                        if ( v306 >= 0 )
                                        {
                                          v306 = RtlUIntAdd(dwBytes, v311, &dwBytes);
                                          if ( v306 >= 0 )
                                          {
                                            if ( v312 - dwBytes < (unsigned int)v313 )
                                              goto LABEL_380;
                                            v806 = v788;
                                            Size = v313;
                                            v306 = RtlULongLongAdd(v788, (unsigned int)v313, &v788);
                                            if ( v306 >= 0 )
                                            {
                                              v306 = RtlUIntAdd(dwBytes, v314, &dwBytes);
                                              if ( v306 >= 0 )
                                              {
                                                if ( v315 - dwBytes < v316 )
                                                  goto LABEL_380;
                                                LODWORD(v784) = *(_DWORD *)v788;
                                                v306 = RtlULongLongAdd(v788, 4, &v788);
                                                if ( v306 >= 0 )
                                                {
                                                  v306 = RtlUIntAdd(dwBytes, 4, &dwBytes);
                                                  if ( v306 >= 0 )
                                                  {
                                                    if ( v317 - dwBytes < v318 )
                                                      goto LABEL_380;
                                                    v306 = RtlUIntAdd(dwBytes, v318, &dwBytes);
                                                    if ( v306 >= 0 )
                                                    {
                                                      if ( v319 != dwBytes
                                                        || (unsigned int)(v320 + v321 + v304) + 12LL != v319 )
                                                      {
                                                        goto LABEL_380;
                                                      }
                                                      v322 = GetProcessHeap();
                                                      v323 = HeapAlloc(v322, 8u, 0x30u);
                                                      v787 = v323;
                                                      v176 = v783;
                                                      v256 = v777;
                                                      if ( !v323 )
                                                      {
                                                        v785 = 0;
                                                        v86 = -805306345;
                                                        v772 = -805306345;
                                                        goto LABEL_292;
                                                      }
                                                      v800 = v85;
                                                      v786 = v87;
                                                      v776 = 0;
                                                      if ( Src )
                                                      {
                                                        *v323 = v795;
                                                        v324 = GetProcessHeap();
                                                        v325 = HeapAlloc(v324, 8u, v794);
                                                        if ( !v325 )
                                                        {
LABEL_412:
                                                          v306 = -1073741801;
                                                          v788 = v177;
                                                          v333 = v787;
                                                          v790 = (LPVOID)*((_QWORD *)v787 + 1);
                                                          if ( v790 )
                                                          {
                                                            v334 = GetProcessHeap();
                                                            HeapFree(v334, 0, v790);
                                                            v333 = v787;
                                                            *((_QWORD *)v787 + 1) = 0;
                                                          }
                                                          v790 = (LPVOID)v333[3];
                                                          if ( v790 )
                                                          {
                                                            v335 = GetProcessHeap();
                                                            HeapFree(v335, 0, v790);
                                                            v333 = v787;
                                                            *((_QWORD *)v787 + 3) = 0;
                                                          }
                                                          v790 = (LPVOID)v333[5];
                                                          if ( v790 )
                                                          {
                                                            v336 = GetProcessHeap();
                                                            HeapFree(v336, 0, v790);
                                                            *((_QWORD *)v787 + 5) = 0;
                                                          }
                                                          v337 = GetProcessHeap();
                                                          HeapFree(v337, 0, v787);
                                                          v338 = (unsigned int *)v776;
                                                          goto LABEL_422;
                                                        }
                                                        *((_QWORD *)v787 + 1) = v325;
                                                        v306 = 0;
                                                        memcpy_0(v325, Src, v794);
                                                        v323 = v787;
                                                      }
                                                      else
                                                      {
                                                        *v323 = 0;
                                                        *((_QWORD *)v323 + 1) = 0;
                                                        v306 = 0;
                                                      }
                                                      if ( v806 )
                                                      {
                                                        v323[4] = v773;
                                                        v326 = GetProcessHeap();
                                                        v327 = HeapAlloc(v326, 8u, Size);
                                                        v328 = v787;
                                                        if ( !v327 )
                                                        {
LABEL_411:
                                                          v787 = v328;
                                                          v800 = v85;
                                                          v786 = v87;
                                                          v783 = v176;
                                                          goto LABEL_412;
                                                        }
                                                        *((_QWORD *)v787 + 3) = v327;
                                                        v306 = 0;
                                                        memcpy_0(v327, v806, Size);
                                                        v323 = v787;
                                                      }
                                                      else
                                                      {
                                                        v323[4] = 0;
                                                        *((_QWORD *)v323 + 3) = 0;
                                                      }
                                                      if ( v788 )
                                                      {
                                                        v329 = (unsigned int)v784;
                                                        v323[8] = v784;
                                                        v330 = v329;
                                                        v790 = (LPVOID)v329;
                                                        v331 = GetProcessHeap();
                                                        v332 = HeapAlloc(v331, 8u, v330);
                                                        v328 = v787;
                                                        if ( !v332 )
                                                          goto LABEL_411;
                                                        *((_QWORD *)v787 + 5) = v332;
                                                        v306 = 0;
                                                        memcpy_0(v332, v788, (size_t)v790);
                                                        v323 = v787;
                                                      }
                                                      else
                                                      {
                                                        v323[8] = 0;
                                                        *((_QWORD *)v323 + 5) = 0;
                                                      }
                                                      v338 = v323;
                                                      v776 = (size_t)v323;
                                                      v788 = v177;
                                                      v783 = v176;
                                                      v786 = v87;
                                                      v800 = v85;
LABEL_422:
                                                      if ( v306 < 0 )
                                                      {
                                                        v307 = 0;
                                                        v785 = 0;
                                                        if ( v338 )
                                                        {
                                                          v790 = (LPVOID)*((_QWORD *)v338 + 1);
                                                          if ( v790 )
                                                          {
                                                            v339 = GetProcessHeap();
                                                            HeapFree(v339, 0, v790);
                                                            v338 = (unsigned int *)v776;
                                                            *(_QWORD *)(v776 + 8) = 0;
                                                          }
                                                          v790 = (LPVOID)*((_QWORD *)v338 + 3);
                                                          if ( v790 )
                                                          {
                                                            v340 = GetProcessHeap();
                                                            HeapFree(v340, 0, v790);
                                                            v338 = (unsigned int *)v776;
                                                            *(_QWORD *)(v776 + 24) = 0;
                                                          }
                                                          v790 = (LPVOID)*((_QWORD *)v338 + 5);
                                                          if ( v790 )
                                                          {
                                                            v341 = GetProcessHeap();
                                                            HeapFree(v341, 0, v790);
                                                            *(_QWORD *)(v776 + 40) = 0;
                                                          }
                                                          v342 = GetProcessHeap();
                                                          HeapFree(v342, 0, (LPVOID)v776);
                                                          v307 = 0;
                                                          v785 = 0;
                                                        }
                                                      }
                                                      else
                                                      {
                                                        v307 = v338;
                                                        v785 = v338;
                                                      }
LABEL_434:
                                                      v86 = v306 | 0x10000000;
                                                      v772 = v86;
                                                      if ( v86 < 0 )
                                                        goto LABEL_291;
                                                      if ( !v307
                                                        || (v806 = (void *)*((_QWORD *)v307 + 1)) == 0
                                                        || !*v307 )
                                                      {
                                                        v86 = -805306355;
                                                        goto LABEL_348;
                                                      }
                                                      v343 = *v307 - 8LL;
                                                      v793 = (LPVOID)v343;
                                                      v344 = MemoryAlloc(v343);
                                                      v792 = v344;
                                                      if ( !v344 )
                                                      {
LABEL_466:
                                                        v792 = 0;
                                                        v86 = -805306367;
                                                        goto LABEL_348;
                                                      }
                                                      v345 = 0;
                                                      v779 = 0;
                                                      v787 = (LPVOID)0x7F1137FAB69605ELL;
                                                      Src = v806;
                                                      v794 = (SIZE_T)v344;
                                                      v346 = v343 & 7;
                                                      if ( (v343 & 7) != 0 )
                                                      {
                                                        v772 = 0;
                                                        LODWORD(v784) = 0;
                                                        v347 = 0;
                                                        v348 = (unsigned __int8 *)Src;
                                                        v349 = 0;
                                                        v350 = 0;
                                                        do
                                                        {
                                                          v351 = *v348++;
                                                          v773 = 8 * v347;
                                                          if ( v347 >= 4 )
                                                            v349 |= v351 << (56 - v773);
                                                          else
                                                            v350 |= v351 << (24 - v773);
                                                          ++v347;
                                                        }
                                                        while ( (int)v347 < (int)v346 );
                                                        LODWORD(v784) = v350;
                                                        v772 = v349;
                                                        Src = v348;
                                                        v788 = v177;
                                                        v783 = v176;
                                                        v786 = v87;
                                                        v800 = v85;
                                                        v345 = v779;
                                                        v352 = v784 ^ 0x92F65A5;
                                                        v353 = v349 ^ 0x699A899C;
                                                        v354 = v784 ^ 0x92F65A5;
                                                        v355 = v349 ^ 0x699A899C;
                                                        v356 = 0;
                                                        if ( (v343 & 7) != 0 )
                                                        {
                                                          v357 = v344;
                                                          do
                                                          {
                                                            v790 = v357 + 1;
                                                            if ( v356 >= 4 )
                                                            {
                                                              v355 = __ROR4__(v355, 24);
                                                              v358 = v355;
                                                            }
                                                            else
                                                            {
                                                              v354 = __ROR4__(v354, 24);
                                                              v358 = v354;
                                                            }
                                                            *v357 = v358;
                                                            ++v356;
                                                            v357 = v790;
                                                          }
                                                          while ( (int)v356 < (int)v346 );
                                                          v794 = (SIZE_T)v790;
                                                        }
                                                        if ( v346 <= 4 )
                                                        {
                                                          v359 = 0;
                                                          if ( v346 < 4 )
                                                            v352 = v352 >> (8 * (4 - v346)) << (8 * (4 - v346));
                                                        }
                                                        else
                                                        {
                                                          v359 = v353 >> (8 * (8 - v346)) << (8 * (8 - v346));
                                                        }
                                                      }
                                                      else
                                                      {
                                                        LODWORD(v784) = 0;
                                                        v772 = -1;
                                                        v359 = 0;
                                                        v352 = 0;
                                                      }
                                                      if ( v343 >> 3 )
                                                      {
                                                        Size = 0;
                                                        v360 = HIDWORD(v787);
                                                        v361 = HIDWORD(v787) ^ 0xAB69605E;
                                                        v773 = HIDWORD(v787) ^ 0xAB69605E;
                                                        v778 = WORD2(v787);
                                                        dwBytes = 24670;
                                                        v362 = (unsigned __int8 *)Src;
                                                        v363 = (_BYTE *)v794;
                                                        v364 = v343 >> 3;
                                                        v365 = v772;
                                                        v366 = v784;
                                                        do
                                                        {
                                                          v367 = v362[3]
                                                               | ((v362[2] | ((v362[1] | (*v362 << 8)) << 8)) << 8);
                                                          v368 = v362[7]
                                                               | ((v362[6] | ((v362[5] | (v362[4] << 8)) << 8)) << 8);
                                                          v362 += 8;
                                                          v369 = v352 ^ v367;
                                                          v370 = v359 ^ v368 ^ v361 ^ v352 ^ v367;
                                                          v371 = v369
                                                               ^ (__ROR4__(v370, 22)
                                                                + v778 * __ROR4__(v370 + 1419157410, 27));
                                                          v372 = v370
                                                               ^ (WORD1(v787) * __ROR4__(v360 + v371, 9)
                                                                - __ROR4__(v371, 30));
                                                          v373 = v371 ^ (dwBytes * (v372 - v778) - (v372 >> 13));
                                                          v374 = v372
                                                               ^ (HIWORD(v787) * __ROR4__(WORD1(v787) ^ v373, 26)
                                                                - __ROR4__(v373, 30));
                                                          v375 = v373 ^ (v360 - (v374 ^ 0xAB69605E));
                                                          v376 = v374
                                                               ^ (WORD1(v787) * (v375 ^ v778))
                                                               ^ __ROR4__(v375, 6);
                                                          v377 = v375
                                                               ^ (__ROR4__(v376, 30)
                                                                + dwBytes * __ROR4__(v360 + v376, 15));
                                                          v378 = v376
                                                               ^ (HIWORD(v787) * __ROR4__(v377 + 1419157410, 14)
                                                                - __ROR4__(v377, 24));
                                                          v379 = v377
                                                               ^ __ROR4__(v378, 10)
                                                               ^ (v778 * __ROR4__(v378 ^ 0xAB69605E, 12));
                                                          v380 = v379
                                                               ^ (HIWORD(v787)
                                                                * (dwBytes
                                                                 + __ROR4__(
                                                                     ~(v378
                                                                     ^ (v379 >> 10)
                                                                     ^ (WORD1(v787) * (v379 ^ HIWORD(v787)))),
                                                                     5)));
                                                          v381 = v378
                                                               ^ (v379 >> 10)
                                                               ^ (WORD1(v787) * (v379 ^ HIWORD(v787)))
                                                               ^ (v380 - HIWORD(v787))
                                                               ^ 0xAB69605E;
                                                          v382 = v380
                                                               ^ ((v381 >> 2) + v778 * __ROR4__(HIWORD(v787) ^ v381, 30));
                                                          v383 = v381
                                                               ^ (__ROR4__(v382, 25)
                                                                + WORD1(v787) * __ROR4__(v382 - HIDWORD(v787), 6));
                                                          v384 = v382 ^ (dwBytes * (v383 ^ v778) + __ROR4__(v383, 9));
                                                          v385 = v383
                                                               ^ (__ROR4__(v384, 25)
                                                                + HIWORD(v787) * __ROR4__(WORD1(v787) ^ v384, 27));
                                                          v386 = v773 ^ v384 ^ v385;
                                                          v387 = v385 ^ (v778 * (__ROR4__(v386, 3) - WORD1(v787)));
                                                          v360 = HIDWORD(v787);
                                                          v388 = v386
                                                               ^ (dwBytes * __ROR4__(v387 - HIDWORD(v787), 1)
                                                                - __ROR4__(v387, 6));
                                                          v389 = v387
                                                               ^ (__ROR4__(v388, 18)
                                                                + HIWORD(v787) * __ROR4__(v388 - 1419157410, 29));
                                                          v390 = v388
                                                               ^ (v778 * __ROR4__(v389 - 1419157410, 17)
                                                                - __ROR4__(v389, 14));
                                                          v391 = v389 ^ (v390 >> 3) ^ (WORD1(v787) * (dwBytes ^ v390));
                                                          v352 = v366
                                                               ^ v390
                                                               ^ __ROR4__(v391, 30)
                                                               ^ (dwBytes * __ROR4__(v391 ^ HIDWORD(v787), 28));
                                                          v359 = v365 ^ v391;
                                                          v363[3] = v352;
                                                          v363[7] = v359;
                                                          v363[2] = __ROR4__(v352, 8);
                                                          v363[6] = __ROR4__(v359, 8);
                                                          v363[1] = __ROR4__(v352, 16);
                                                          v363[5] = __ROR4__(v359, 16);
                                                          *v363 = __ROR4__(v352, 24);
                                                          v363[4] = __ROR4__(v359, 24);
                                                          v366 = v367;
                                                          v365 = v368;
                                                          v363 += 8;
                                                          ++Size;
                                                          v361 = v773;
                                                        }
                                                        while ( Size < v364 );
                                                        v345 = v779;
                                                        v85 = v800;
                                                        v87 = v786;
                                                        v177 = (unsigned int *)v788;
                                                        v344 = v792;
                                                        v343 = (unsigned __int64)v793;
                                                      }
                                                      for ( i = 0; i < v343; ++i )
                                                        v345 ^= *((_BYTE *)v344 + i);
                                                      if ( v345 != *(_QWORD *)((char *)v806 + v343) )
                                                      {
                                                        MemoryFree(v344);
                                                        goto LABEL_466;
                                                      }
                                                      v176 = v783;
                                                      v778 = 0;
                                                      v776 = (size_t)v344;
                                                      if ( (unsigned int)v343 < 4 )
                                                      {
LABEL_468:
                                                        v393 = -1073741762;
LABEL_506:
                                                        v86 = v393 | 0x10000000;
                                                        goto LABEL_290;
                                                      }
                                                      v393 = RtlULongLongAdd(v344, 4, &v776);
                                                      if ( v393 >= 0 )
                                                      {
                                                        v393 = RtlUIntAdd(0, 4, &v778);
                                                        if ( v393 >= 0 )
                                                        {
                                                          if ( (unsigned int)v793 - v778 < 4 )
                                                            goto LABEL_504;
                                                          LODWORD(v784) = *(_DWORD *)v776;
                                                          v393 = RtlULongLongAdd(v776, 4, &v776);
                                                          if ( v393 < 0 )
                                                            goto LABEL_505;
                                                          v393 = RtlUIntAdd(v778, 4, &v778);
                                                          if ( v393 < 0 )
                                                            goto LABEL_505;
                                                          if ( (unsigned int)v793 - v778 < (unsigned int)v784 )
                                                            goto LABEL_504;
                                                          v393 = RtlUIntAdd(v778, (unsigned int)v784, &v778);
                                                          if ( v393 >= 0 )
                                                          {
                                                            v397 = (unsigned int)v784;
                                                            if ( (unsigned __int64)v396 + (unsigned int)v793 >= (unsigned int)v784 + v776
                                                              && (unsigned __int64)v396
                                                               + (unsigned int)v793
                                                               - v776
                                                               - (unsigned int)v784 < 8 )
                                                            {
                                                              v795 = *v396;
                                                              v793 = 0;
                                                              v794 = 0;
                                                              v786 = 0;
                                                              v773 = 0;
                                                              if ( v776 )
                                                              {
                                                                v393 = RtlULongLongAdd(v776, (unsigned int)v784, &v793);
                                                                v792 = v399;
                                                                v785 = v400;
                                                                v777 = v401;
                                                                if ( v393 < 0 )
                                                                {
LABEL_500:
                                                                  v409 = v780;
LABEL_501:
                                                                  if ( v393 < 0 || v795 == v409 )
                                                                    goto LABEL_506;
                                                                  goto LABEL_468;
                                                                }
                                                                v402 = v398;
                                                                Src = v398;
                                                                if ( v398 < v793 )
                                                                {
                                                                  while ( 1 )
                                                                  {
                                                                    v393 = RtlULongLongAdd(v402, 4, &v794);
                                                                    if ( v393 < 0 )
                                                                      goto LABEL_500;
                                                                    if ( v794 > (unsigned __int64)v793 )
                                                                      goto LABEL_488;
                                                                    v778 = 0;
                                                                    v393 = RtlUIntAdd(4, *(unsigned int *)Src, &v778);
                                                                    if ( v393 < 0 )
                                                                      goto LABEL_506;
                                                                    v393 = RtlULongLongAdd(Src, v778, &v786);
                                                                    v792 = v405;
                                                                    v785 = v404;
                                                                    v777 = v403;
                                                                    if ( v393 < 0 )
                                                                      goto LABEL_500;
                                                                    v402 = v786;
                                                                    Src = v786;
                                                                    v406 = v793;
                                                                    v792 = v405;
                                                                    v785 = v404;
                                                                    v777 = v403;
                                                                    if ( v786 > v793 )
                                                                      goto LABEL_488;
                                                                    ++v773;
                                                                    if ( v786 >= v793 )
                                                                    {
                                                                      v792 = v405;
                                                                      v785 = v404;
                                                                      v777 = v403;
                                                                      goto LABEL_490;
                                                                    }
                                                                  }
                                                                }
                                                                v406 = v793;
LABEL_490:
                                                                if ( v402 != v406 )
                                                                {
LABEL_488:
                                                                  v393 = -1073741811;
                                                                  goto LABEL_506;
                                                                }
                                                                v397 = (unsigned int)v784;
                                                              }
                                                              else
                                                              {
                                                                v393 = 0;
                                                                v792 = v396;
                                                                v785 = v395;
                                                                v777 = v394;
                                                              }
                                                              v407 = 0;
                                                              v794 = 0;
                                                              if ( (_DWORD)v397 )
                                                              {
                                                                v408 = GetProcessHeap();
                                                                v407 = HeapAlloc(v408, 8u, (unsigned int)v784);
                                                                v794 = (SIZE_T)v407;
                                                                if ( !v407 )
                                                                {
                                                                  v393 = -1073741801;
                                                                  goto LABEL_506;
                                                                }
                                                                v393 = 0;
                                                                v397 = (unsigned int)v784;
                                                              }
                                                              if ( v776 )
                                                                memcpy_0(v407, (const void *)v776, v397);
                                                              v789 = (LPVOID)v794;
                                                              v409 = v773;
                                                              v780 = v773;
                                                              goto LABEL_501;
                                                            }
LABEL_504:
                                                            v393 = -1073741762;
                                                          }
                                                        }
                                                      }
LABEL_505:
                                                      v792 = v396;
                                                      v777 = v394;
                                                      v785 = v395;
                                                      goto LABEL_506;
                                                    }
                                                  }
                                                }
                                              }
                                            }
                                          }
                                        }
                                      }
                                    }
                                  }
                                  v307 = (unsigned int *)v785;
                                  goto LABEL_433;
                                }
                              }
                            }
                          }
                        }
                      }
                    }
                  }
                }
              }
            }
          }
        }
      }
    }
  }
LABEL_119:
  lpMem[0] = 0;
  v112 = lpMem[1];
  if ( lpMem[1] )
  {
    v113 = GetProcessHeap();
    HeapFree(v113, 0, v112);
    lpMem[1] = 0;
  }
  v114 = v789;
  if ( v789 )
  {
    v115 = GetProcessHeap();
    HeapFree(v115, 0, v114);
  }
  if ( v85 )
  {
    v116 = GetProcessHeap();
    HeapFree(v116, 0, v85);
  }
  if ( v87 )
  {
    v117 = GetProcessHeap();
    HeapFree(v117, 0, v87);
  }
  if ( v86 < 0 )
  {
    v81 = (unsigned int)v782;
    v80 = (int)v782;
    goto LABEL_945;
  }
  if ( v824 )
  {
    v118 = 0;
    *(_OWORD *)v801 = 0;
    v119 = 0;
    v783 = 0;
    v120 = GetProcessHeap();
    v121 = HeapAlloc(v120, 8u, 0xA0u);
    v122 = v121;
    if ( !v121 )
    {
LABEL_579:
      v801[0] = 0;
      v460 = (void *)v801[1];
      if ( v801[1] )
      {
        v461 = GetProcessHeap();
        HeapFree(v461, 0, v460);
        v801[1] = 0;
      }
      if ( v119 )
      {
        v462 = GetProcessHeap();
        HeapFree(v462, 0, (LPVOID)v119);
      }
      if ( v122 )
      {
        v463 = GetProcessHeap();
        HeapFree(v463, 0, v122);
      }
      if ( v118 )
      {
        v464 = GetProcessHeap();
        HeapFree(v464, 0, v118);
      }
      goto LABEL_587;
    }
    *v121 = xmmword_180128590;
    v121[1] = xmmword_1801285A0;
    v121[2] = xmmword_1801285B0;
    v121[3] = xmmword_1801285C0;
    v121[4] = xmmword_1801285D0;
    v121[5] = xmmword_1801285E0;
    v121[6] = xmmword_1801285F0;
    v121[7] = xmmword_180128600;
    v121[8] = xmmword_180128610;
    v121[9] = xmmword_180128620;
    v123 = GetProcessHeap();
    v124 = HeapAlloc(v123, 8u, 8u);
    v125 = v124;
    if ( !v124 )
    {
      v119 = 0;
      goto LABEL_579;
    }
    *v124 = qword_1801284D0;
    v790 = (LPVOID)__rdtsc();
    dwBytes_4 = 0;
    v773 = 0;
    if ( (int)RtlUIntAdd(4, 4, &v773) < 0 )
      goto LABEL_577;
    if ( (int)RtlUIntAdd(0, v773, &dwBytes_4) < 0 )
    {
      v118 = v125;
      v119 = v446;
      goto LABEL_579;
    }
    v773 = v446;
    if ( (int)RtlUIntAdd(v447, 160, &v773) < 0 )
      goto LABEL_577;
    v448 = RtlUIntAdd(dwBytes_4, v773, &dwBytes_4);
    if ( (v450 | v448) < 0 )
      goto LABEL_577;
    v773 = 0;
    if ( (int)RtlUIntAdd(v449, 8, &v773) < 0 )
      goto LABEL_577;
    v451 = RtlUIntAdd(dwBytes_4, v773, &dwBytes_4);
    if ( (v453 | v451) < 0
      || (v773 = 0, (int)RtlUIntAdd(v452, 8, &v773) < 0)
      || (v454 = RtlUIntAdd(dwBytes_4, v773, &dwBytes_4), (v455 | v454) < 0)
      || (HIDWORD(v801[0]) = dwBytes_4,
          v456 = dwBytes_4,
          v457 = GetProcessHeap(),
          v458 = HeapAlloc(v457, 8u, v456),
          (v459 = v458) == 0) )
    {
LABEL_577:
      v118 = v125;
      goto LABEL_578;
    }
    v801[1] = (size_t)v458;
    LODWORD(v801[0]) = 0;
    LODWORD(v803) = 0;
    v802 = 0;
    pcchLength = (size_t)v458;
    v780 = 8;
    v118 = v125;
    if ( (int)RtlULongLongAdd(v458, 4, &v803) < 0 || (unsigned __int64)(v459 + 2) > v801[1] + HIDWORD(v801[0]) )
    {
      v119 = v466;
      goto LABEL_579;
    }
    *v459 = v465;
    *(_DWORD *)v803 = v465;
    v468 = v780;
    v469 = ++LODWORD(v801[0]);
    LODWORD(v803) = 0;
    v802 = 0;
    if ( v122 )
    {
      if ( !v467 )
        goto LABEL_578;
    }
    else if ( v467 )
    {
LABEL_592:
      v119 = 0;
      goto LABEL_579;
    }
    v470 = (unsigned int *)v801[1];
    if ( v801[1] )
    {
      pcchLength = v801[1];
      v472 = 0;
      if ( v469 )
      {
        do
        {
          v773 = 0;
          if ( (int)RtlUIntAdd(4, *v470, &v773) < 0 || (int)RtlULongLongAdd(v473, v773, &pcchLength) < 0 )
            goto LABEL_578;
          ++v472;
          v470 = (unsigned int *)pcchLength;
        }
        while ( v472 < v474 );
      }
      if ( (int)RtlULongLongAdd(v470, 4, &v803) < 0 || (unsigned __int64)v475 + v476 + 4 > v801[1] + HIDWORD(v801[0]) )
        goto LABEL_578;
      *v475 = v476;
      if ( v122 )
        memcpy_0(v803, v122, v476);
      v471 = 4;
    }
    else
    {
      v773 = 0;
      if ( (int)RtlUIntAdd(4, v467, &v773) < 0 || (int)RtlUIntAdd(HIDWORD(v801[0]), v773, (char *)v801 + 4) < 0 )
        goto LABEL_578;
    }
    v477 = ++LODWORD(v801[0]);
    LODWORD(v803) = 0;
    v802 = 0;
    if ( v118 )
    {
      if ( !v468 )
        goto LABEL_578;
    }
    else if ( v468 )
    {
      goto LABEL_592;
    }
    v478 = (unsigned int *)v801[1];
    if ( v801[1] )
    {
      pcchLength = v801[1];
      if ( v477 )
      {
        do
        {
          v773 = 0;
          if ( (int)RtlUIntAdd(4, *v478, &v773) < 0 || (int)RtlULongLongAdd(v480, v773, &pcchLength) < 0 )
            goto LABEL_578;
          v478 = (unsigned int *)pcchLength;
        }
        while ( v482 + 1 < v481 );
      }
      if ( (int)RtlULongLongAdd(v478, 4, &v803) < 0 || (unsigned __int64)v483 + v468 + 4 > v801[1] + HIDWORD(v801[0]) )
        goto LABEL_578;
      *v483 = v468;
      if ( v118 )
      {
        memcpy_0(v803, v118, v468);
        v479 = 4;
      }
    }
    else
    {
      v773 = 0;
      if ( (int)RtlUIntAdd(v471, v468, &v773) < 0 || (int)RtlUIntAdd(HIDWORD(v801[0]), v773, (char *)v801 + 4) < 0 )
        goto LABEL_578;
    }
    v484 = ++LODWORD(v801[0]);
    LODWORD(v803) = 0;
    v802 = 0;
    v485 = (unsigned int *)v801[1];
    if ( !v801[1] )
    {
      v773 = 0;
      if ( (int)RtlUIntAdd(v479, 8, &v773) < 0 || (int)RtlUIntAdd(HIDWORD(v801[0]), v773, (char *)v801 + 4) < 0 )
        goto LABEL_578;
LABEL_634:
      ++LODWORD(v801[0]);
      v773 = 0;
      if ( (int)RtlUIntAdd(v486, v486, &v773) < 0 )
        goto LABEL_578;
      v780 = v773;
      v773 = 0;
      if ( (int)RtlUIntAdd(v491, 8, &v773) < 0 || (int)RtlUIntAdd(v492, v773, &v780) < 0 )
        goto LABEL_578;
      v773 = 0;
      v493 = v780;
      dwBytes = v780;
      v782 = 0;
      v790 = (LPVOID)__rdtsc();
      v809 = 8;
      v494 = RtlUIntAdd(8, HIDWORD(v801[0]), &v809);
      if ( v494 < 0 )
      {
        v786 = v118;
        v789 = v122;
      }
      else
      {
        v497 = (v809 + 7) & 0xFFFFFFF8;
        if ( v497 < v809 )
        {
          v119 = (unsigned int)v495;
          goto LABEL_579;
        }
        v809 = (v809 + 7) & 0xFFFFFFF8;
        v498 = v497;
        v499 = GetProcessHeap();
        v500 = (char *)HeapAlloc(v499, 8u, v498);
        v501 = v500;
        if ( !v500 )
          goto LABEL_927;
        v789 = v122;
        v786 = v118;
        dwBytes = v493;
        v776 = (size_t)v500;
        *(_DWORD *)v500 = v801[0];
        v780 = RtlULongLongAdd(v500, 4, &v776);
        if ( v780 < 0
          || (v503 = v776, *(_DWORD *)v776 = HIDWORD(v801[0]), v780 = RtlULongLongAdd(v503, v502, &v776), v780 < 0) )
        {
          v789 = v122;
          v786 = v118;
          dwBytes = v493;
          v504 = GetProcessHeap();
          HeapFree(v504, 0, v501);
          v495 = v782;
          v494 = v780;
          v496 = (unsigned int)v782;
        }
        else
        {
          *(_QWORD *)&v501[v809 - 8] = v790;
          memcpy_0((void *)v776, (const void *)v801[1], HIDWORD(v801[0]));
          v495 = v501;
          v782 = v501;
          v496 = v809;
          v494 = v780;
        }
      }
      v505 = 0;
      v806 = 0;
      v506 = 0;
      v788 = 0;
      v785 = 0;
      v777 = 0;
      v507 = v494 | 0x10000000;
      if ( v507 < 0 )
      {
        v781 = v507;
        v585 = 0;
        goto LABEL_902;
      }
      if ( !v495 )
        goto LABEL_578;
      v794 = v496;
      if ( !v496 || (v807 = v496 + 8LL, v508 = MemoryAlloc(v807), (Size = (SIZE_T)v508) == 0) )
      {
        v781 = -805306367;
        v559 = v782;
        v585 = 0;
        goto LABEL_904;
      }
      v793 = 0;
      v509 = 0;
      v779 = 0;
      v510 = 0;
      v511 = v794;
      if ( v794 )
      {
        do
          v509 ^= *((_BYTE *)v782 + v510++);
        while ( v510 < v794 );
        v779 = v509;
      }
      v792 = (LPVOID)0xC81ECB17B1B54A58LL;
      pcchLength = (size_t)v782;
      Src = v508;
      v512 = v794 & 7;
      if ( (v794 & 7) != 0 )
      {
        v780 = 0;
        LODWORD(v784) = 0;
        v513 = 0;
        v514 = (unsigned __int8 *)v782;
        v515 = 0;
        v516 = 0;
        do
        {
          v517 = *v514++;
          v780 = 8 * v513;
          if ( v513 >= 4 )
            v515 |= v517 << (56 - v780);
          else
            v516 |= v517 << (24 - v780);
          ++v513;
        }
        while ( (int)v513 < (int)v512 );
        LODWORD(v784) = v516;
        v780 = v515;
        pcchLength = (size_t)v514;
        v786 = v118;
        v789 = v122;
        v505 = 0;
        v518 = v784 ^ 0xB17A307A;
        v519 = v515 ^ 0x42F6B18D;
        v520 = v784 ^ 0xB17A307A;
        v521 = v515 ^ 0x42F6B18D;
        dwBytes_4 = 0;
        if ( (v794 & 7) != 0 )
        {
          v522 = Src;
          do
          {
            v790 = v522 + 1;
            if ( dwBytes_4 >= 4 )
            {
              v521 = __ROR4__(v521, 24);
              v523 = v521;
            }
            else
            {
              v520 = __ROR4__(v520, 24);
              v523 = v520;
            }
            *v522 = v523;
            ++dwBytes_4;
            v522 = v790;
          }
          while ( (int)dwBytes_4 < (int)v512 );
          Src = v790;
        }
        if ( v512 <= 4 )
        {
          v524 = 0;
          if ( v512 < 4 )
            v518 = v518 >> (8 * (4 - v512)) << (8 * (4 - v512));
        }
        else
        {
          v524 = v519 >> (8 * (8 - v512)) << (8 * (8 - v512));
        }
      }
      else
      {
        v518 = 0;
        v524 = -1;
        LODWORD(v784) = 0;
        v780 = 0;
      }
      if ( v511 >> 3 )
      {
        v802 = 0;
        v525 = 19032;
        dwBytes_4 = 19032;
        v781 = WORD1(v792);
        v778 = HIWORD(v792);
        v526 = (unsigned __int8 *)pcchLength;
        v527 = Src;
        v528 = v511 >> 3;
        v529 = v780;
        v530 = v784;
        v531 = WORD2(v792);
        do
        {
          v532 = v526[3] | ((v526[2] | ((v526[1] | (*v526 << 8)) << 8)) << 8);
          v533 = v526[7] | ((v526[6] | ((v526[5] | (v526[4] << 8)) << 8)) << 8);
          v534 = v524 ^ v533;
          v526 += 8;
          v535 = v518 ^ v532 ^ HIDWORD(v792) ^ ((v524 ^ v533) - v525);
          v536 = v534 ^ (__ROR4__(v535, 7) + WORD1(v792) * __ROR4__(HIDWORD(v792) ^ v535, 15));
          v537 = v535 ^ (v531 * __ROR4__(v536 - 1313519016, 9) - __ROR4__(v536, 10));
          v538 = v536 ^ (__ROR4__(v537, 27) + HIWORD(v792) * __ROR4__(v531 ^ v537, 28));
          v539 = v537 ^ (HIDWORD(v792) - (v538 ^ 0xB1B54A58));
          v540 = v538 ^ (WORD1(v792) * (v539 - dwBytes_4) - (v539 >> 6));
          v541 = v539 ^ (dwBytes_4 * (v531 ^ __ROR4__(v540, 15)));
          v542 = v540 ^ (v531 * (v778 + __ROR4__(~v541, 3)));
          v543 = v542
               ^ (v781 * (v778 ^ v541 ^ (v542 - HIDWORD(v792) - dwBytes_4)))
               ^ __ROR4__(v541 ^ (v542 - HIDWORD(v792) - dwBytes_4), 10);
          v544 = v541 ^ (v542 - HIDWORD(v792) - dwBytes_4) ^ __ROR4__(v543, 3) ^ (v531 * __ROR4__(dwBytes_4 ^ v543, 26));
          v545 = v543 ^ (dwBytes_4 * (__ROR4__(v544, 15) - HIWORD(v792)));
          v546 = v544
               ^ (dwBytes_4 * (v778 ^ v545))
               ^ ((v545 ^ (v545 >> 14)) >> 1)
               ^ (dwBytes_4 * ((8 * (v545 - v531)) | ((unsigned __int64)(v545 - v531) >> 29)));
          v547 = v545 ^ (WORD1(v792) * (v546 - v531) - (v546 >> 13));
          v548 = v546 ^ __ROR4__(v547, 11) ^ (v531 * __ROR4__(-1313519016 - v547, 9));
          v549 = v547 ^ (v548 + 1313519016 - HIWORD(v792));
          v550 = v548 ^ (dwBytes_4 * (v781 ^ v549) - __ROR4__(v549, 7));
          v551 = v549 ^ (WORD1(v792) * __ROR4__(HIWORD(v792) ^ v550, 28) - __ROR4__(v550, 16));
          v552 = v550 ^ (__ROR4__(v551, 4) + v531 * __ROR4__(-1313519016 - v551, 10));
          v553 = v551 ^ __ROR4__(v552, 9) ^ (HIWORD(v792) * __ROR4__(v552 + 1313519016, 4));
          v554 = v552 ^ (dwBytes_4 * __ROR4__(HIDWORD(v792) ^ v553, 24) - __ROR4__(v553, 30));
          v555 = v553 ^ (WORD1(v792) * __ROR4__(HIDWORD(v792) - v554, 11) - __ROR4__(v554, 12));
          v556 = v554 ^ (v555 >> 8) ^ (v531 * (WORD1(v792) ^ v555));
          v518 = v556 ^ v530;
          v524 = v556 ^ v529 ^ HIDWORD(v792) ^ v555 ^ 0xB1B54A58;
          v527[3] = v556 ^ v530;
          v527[7] = v524;
          v527[2] = __ROR4__(v556 ^ v530, 8);
          v527[6] = __ROR4__(v524, 8);
          v527[1] = __ROR4__(v556 ^ v530, 16);
          v527[5] = __ROR4__(v524, 16);
          *v527 = __ROR4__(v556 ^ v530, 24);
          v527[4] = __ROR4__(v524, 24);
          v530 = v532;
          v529 = v533;
          v527 += 8;
          ++v802;
          v525 = dwBytes_4;
        }
        while ( v802 < v528 );
        v509 = v779;
        v86 = v772;
        v122 = v789;
        v118 = v786;
        v506 = (unsigned int *)v788;
        v505 = (unsigned int *)v788;
        v511 = v794;
      }
      *(_QWORD *)(Size + v511) = v509;
      v557 = GetProcessHeap();
      v558 = HeapAlloc(v557, 8u, 0x30u);
      v789 = v558;
      if ( !v558 )
      {
        dwBytes_4 = -1073741801;
        v559 = v782;
        goto LABEL_692;
      }
      v560 = v807;
      *v558 = v807;
      v561 = GetProcessHeap();
      v562 = HeapAlloc(v561, 8u, v560);
      v559 = v782;
      if ( v562 )
      {
        *((_QWORD *)v789 + 1) = v562;
        memcpy_0(v562, (const void *)Size, (unsigned int)v807);
        *((_DWORD *)v789 + 4) = 160;
        v563 = GetProcessHeap();
        v564 = HeapAlloc(v563, 8u, 0xA0u);
        v565 = v789;
        if ( v564 )
        {
          *((_QWORD *)v789 + 3) = v564;
          *v564 = xmmword_1801284E0;
          v564[1] = xmmword_1801284F0;
          v564[2] = xmmword_180128500;
          v564[3] = xmmword_180128510;
          v564[4] = xmmword_180128520;
          v564[5] = xmmword_180128530;
          v564[6] = xmmword_180128540;
          v564[7] = xmmword_180128550;
          v564[8] = xmmword_180128560;
          v564[9] = xmmword_180128570;
          v565[8] = 8;
          v566 = GetProcessHeap();
          v567 = HeapAlloc(v566, 8u, 8u);
          if ( v567 )
          {
            v573 = v789;
            *((_QWORD *)v789 + 5) = v567;
            *v567 = qword_180128580;
            v793 = v573;
            dwBytes_4 = 0;
            v782 = v559;
            goto LABEL_691;
          }
          v565 = v789;
        }
        v789 = v565;
      }
      dwBytes_4 = -1073741801;
      v782 = v559;
      v568 = v789;
      v790 = (LPVOID)*((_QWORD *)v789 + 1);
      if ( v790 )
      {
        v569 = GetProcessHeap();
        HeapFree(v569, 0, v790);
        v568 = v789;
        *((_QWORD *)v789 + 1) = 0;
      }
      v790 = (LPVOID)v568[3];
      if ( v790 )
      {
        v570 = GetProcessHeap();
        HeapFree(v570, 0, v790);
        v568 = v789;
        *((_QWORD *)v789 + 3) = 0;
      }
      v790 = (LPVOID)v568[5];
      if ( v790 )
      {
        v571 = GetProcessHeap();
        HeapFree(v571, 0, v790);
        *((_QWORD *)v789 + 5) = 0;
      }
      v572 = GetProcessHeap();
      HeapFree(v572, 0, v789);
      if ( (dwBytes_4 & 0x80000000) != 0 )
      {
LABEL_692:
        v574 = GetProcessHeap();
        HeapFree(v574, 0, (LPVOID)Size);
        v575 = v793;
        if ( v793 )
        {
          v790 = (LPVOID)*((_QWORD *)v793 + 1);
          if ( v790 )
          {
            v576 = GetProcessHeap();
            HeapFree(v576, 0, v790);
            v575 = v793;
            *((_QWORD *)v793 + 1) = 0;
          }
          v790 = (LPVOID)v575[3];
          if ( v790 )
          {
            v577 = GetProcessHeap();
            HeapFree(v577, 0, v790);
            v575 = v793;
            *((_QWORD *)v793 + 3) = 0;
          }
          v790 = (LPVOID)v575[5];
          if ( v790 )
          {
            v578 = GetProcessHeap();
            HeapFree(v578, 0, v790);
            *((_QWORD *)v793 + 5) = 0;
          }
          v579 = GetProcessHeap();
          HeapFree(v579, 0, v793);
        }
        if ( (dwBytes_4 & 0x80000000) != 0 )
        {
          v781 = dwBytes_4 | 0x10000000;
          goto LABEL_708;
        }
        LODWORD(v784) = 0;
        v778 = 4;
        v781 = RtlUIntAdd(4, *v505, &v778);
        if ( v781 < 0
          || (v781 = RtlUIntAdd(v778, v580, &v778), v781 < 0)
          || (v802 = (SIZE_T)(v505 + 4), v781 = RtlUIntAdd(v778, v505[4], &v778), v781 < 0)
          || (v781 = RtlUIntAdd(v778, v581, &v778), v781 < 0)
          || (v794 = (SIZE_T)(v505 + 8), v781 = RtlUIntAdd(v778, v505[8], &v778), v781 < 0) )
        {
          v782 = v559;
        }
        else
        {
          v582 = v778;
          v583 = GetProcessHeap();
          v584 = HeapAlloc(v583, 8u, v582);
          v786 = v584;
          v559 = v782;
          if ( !v584 )
          {
            v781 = -805306345;
LABEL_708:
            v585 = v777;
            goto LABEL_903;
          }
          v789 = v584;
          *v584 = *v505;
          v781 = RtlULongLongAdd(v584, 4, &v789);
          if ( v781 < 0 )
          {
            dwBytes = v587;
            v786 = v586;
          }
          else
          {
            memcpy_0(v789, *((const void **)v505 + 1), *v505);
            v781 = RtlULongLongAdd(v789, *v505, &v789);
            if ( v781 >= 0 )
            {
              v588 = v789;
              *(_DWORD *)v789 = *(_DWORD *)v802;
              v781 = RtlULongLongAdd(v588, 4, &v789);
              if ( v781 >= 0 )
              {
                memcpy_0(v789, *((const void **)v505 + 3), *v589);
                v781 = RtlULongLongAdd(v789, *(unsigned int *)v802, &v789);
                if ( v781 >= 0 )
                {
                  v590 = v789;
                  *(_DWORD *)v789 = *(_DWORD *)v794;
                  v781 = RtlULongLongAdd(v590, 4, &v789);
                  if ( v781 >= 0 )
                  {
                    memcpy_0(v789, *((const void **)v505 + 5), *v591);
                    v592 = RtlULongLongAdd(v789, *(unsigned int *)v794, &v789);
                    v781 = v592;
                    if ( v592 >= 0 )
                    {
                      v806 = v786;
                      LODWORD(v784) = v778;
LABEL_722:
                      v594 = v592 | 0x10000000;
                      if ( v594 < 0 )
                        goto LABEL_726;
                      v814 = 8;
                      v595 = RtlUIntAdd(8, dwBytes, &v814);
                      v594 = v596 | v595;
                      if ( v594 < 0 )
                        goto LABEL_726;
                      v597 = (v814 + 7) & 0xFFFFFFF8;
                      if ( (unsigned int)v597 < v814 )
                      {
                        v594 = -1073741675;
LABEL_726:
                        v781 = v594;
LABEL_764:
                        v585 = v777;
LABEL_902:
                        v559 = v782;
LABEL_903:
                        if ( !v559 )
                        {
LABEL_905:
                          if ( v505 )
                          {
                            v724 = (void *)*((_QWORD *)v505 + 1);
                            if ( v724 )
                            {
                              v725 = GetProcessHeap();
                              HeapFree(v725, 0, v724);
                              *((_QWORD *)v505 + 1) = 0;
                            }
                            v726 = (void *)*((_QWORD *)v505 + 3);
                            if ( v726 )
                            {
                              v727 = GetProcessHeap();
                              HeapFree(v727, 0, v726);
                              *((_QWORD *)v505 + 3) = 0;
                            }
                            v728 = (void *)*((_QWORD *)v505 + 5);
                            if ( v728 )
                            {
                              v729 = GetProcessHeap();
                              HeapFree(v729, 0, v728);
                              *((_QWORD *)v505 + 5) = 0;
                            }
                            v730 = GetProcessHeap();
                            HeapFree(v730, 0, v505);
                          }
                          v731 = v806;
                          if ( v806 )
                          {
                            v732 = GetProcessHeap();
                            HeapFree(v732, 0, v731);
                          }
                          if ( v506 )
                          {
                            v733 = GetProcessHeap();
                            HeapFree(v733, 0, v506);
                          }
                          v734 = v785;
                          if ( v785 )
                          {
                            v735 = (void *)*((_QWORD *)v785 + 1);
                            if ( v735 )
                            {
                              v736 = GetProcessHeap();
                              HeapFree(v736, 0, v735);
                              v734[1] = 0;
                            }
                            v737 = (void *)v734[3];
                            if ( v737 )
                            {
                              v738 = GetProcessHeap();
                              HeapFree(v738, 0, v737);
                              v734[3] = 0;
                            }
                            v739 = (void *)v734[5];
                            if ( v739 )
                            {
                              v740 = GetProcessHeap();
                              HeapFree(v740, 0, v739);
                              v734[5] = 0;
                            }
                            v741 = GetProcessHeap();
                            HeapFree(v741, 0, v734);
                          }
                          if ( v585 )
                          {
                            v742 = GetProcessHeap();
                            HeapFree(v742, 0, v585);
                          }
LABEL_927:
                          if ( v781 >= 0 )
                          {
                            v119 = (size_t)v783;
                            if ( v773 )
                            {
                              if ( v783 )
                              {
                                v802 = (SIZE_T)v783;
                                if ( (int)RtlULongLongAdd(v783, 4, &v802) >= 0 )
                                {
                                  v745 = (int *)v802;
                                  if ( !*(_DWORD *)v119 )
                                    v745 = 0;
                                  if ( *(_DWORD *)v119 == (_DWORD)v744 && *v745 >= 0 && v743 > 1 )
                                  {
                                    v746 = v119;
                                    v776 = v119;
                                    while ( (int)RtlULongLongAdd(v746, v744, &v776) >= 0
                                         && (int)RtlULongLongAdd(v776, v747, &v776) >= 0 )
                                    {
                                      v746 = v776;
                                      if ( v748 != -1 )
                                      {
                                        RtlULongLongAdd(v776, v744, &v776);
                                        goto LABEL_579;
                                      }
                                    }
                                  }
                                }
                              }
                            }
                            goto LABEL_579;
                          }
                          goto LABEL_578;
                        }
LABEL_904:
                        v723 = GetProcessHeap();
                        HeapFree(v723, 0, v559);
                        goto LABEL_905;
                      }
                      v823 = (v814 + 7) & 0xFFFFFFF8;
                      v594 = RtlUIntAdd(v597, 8, &v823);
                      if ( v594 < 0 )
                        goto LABEL_726;
                      v789 = v122;
                      v786 = v118;
                      v782 = v559;
                      v787 = v505;
                      v780 = 0;
                      v598 = v801[1];
                      if ( !v801[1] )
                        goto LABEL_736;
                      v787 = v505;
                      v782 = v559;
                      v786 = v118;
                      v789 = v122;
                      if ( LODWORD(v801[0]) <= 1 )
                        goto LABEL_736;
                      v776 = v801[1];
                      do
                      {
                        v594 = RtlULongLongAdd(v598, 4, &v776);
                        if ( v594 < 0 )
                          goto LABEL_726;
                        v594 = RtlULongLongAdd(v776, v599, &v776);
                        if ( v594 < 0 )
                          goto LABEL_726;
                        v598 = v776;
                      }
                      while ( v600 == -1 );
                      v601 = *(_DWORD *)v776;
                      v594 = RtlULongLongAdd(v776, 4, &v776);
                      if ( v594 < 0 )
                        goto LABEL_726;
                      v602 = v801[1];
                      if ( !v801[1] || LODWORD(v801[0]) <= 2 )
                      {
LABEL_736:
                        v594 = -1073741811;
                        goto LABEL_726;
                      }
                      v776 = v801[1];
                      do
                      {
                        v594 = RtlULongLongAdd(v602, 4, &v776);
                        if ( v594 < 0 )
                          goto LABEL_726;
                        v594 = RtlULongLongAdd(v776, v606, &v776);
                        if ( v594 < 0 )
                          goto LABEL_726;
                        v602 = v776;
                      }
                      while ( (unsigned int)(v607 + 1) < 2 );
                      v594 = RtlULongLongAdd(v776, 4, &v776);
                      if ( v594 < 0 )
                        goto LABEL_726;
                      v780 = v608;
                      dwBytes_4 = v609;
                      v594 = RtlUIntAdd(v609, v823, &dwBytes_4);
                      if ( v594 < 0 )
                        goto LABEL_726;
                      v594 = RtlUIntAdd(dwBytes_4, v610, &dwBytes_4);
                      if ( v594 < 0 )
                        goto LABEL_726;
                      v594 = RtlUIntAdd(dwBytes_4, v601, &dwBytes_4);
                      if ( v594 < 0 )
                        goto LABEL_726;
                      v594 = RtlUIntAdd(dwBytes_4, v611, &dwBytes_4);
                      if ( v594 < 0 )
                        goto LABEL_726;
                      v594 = RtlUIntAdd(dwBytes_4, v612, &dwBytes_4);
                      if ( v594 < 0 )
                        goto LABEL_726;
                      v780 = dwBytes_4;
                      if ( dwBytes_4 > 0x400000 )
                      {
                        v594 = -2147418113;
                        goto LABEL_726;
                      }
                      v603 = dwBytes_4;
                      v604 = GetProcessHeap();
                      v605 = (unsigned int *)HeapAlloc(v604, 8u, v603);
                      v506 = v605;
                      if ( !v605 )
                      {
                        v781 = -805306345;
                        v585 = 0;
                        goto LABEL_902;
                      }
                      v861 = 0;
                      v862 = 0;
                      hModule = 0;
                      if ( !v806 )
                      {
                        v781 = -2147024809;
                        goto LABEL_764;
                      }
                      *(_QWORD *)&v861 = v806;
                      LODWORD(v862) = v784;
                      *((_QWORD *)&v861 + 1) = v605;
                      *(_QWORD *)((char *)&v862 + 4) = (unsigned int)v780;
                      if ( GetModuleHandleExW(1u, L"ntdll.dll", &hModule)
                        && (v614 = GetProcAddress(hModule, "NtQuerySystemInformation")) != 0 )
                      {
                        v594 = ((__int64 (__fastcall *)(__int64, __int128 *))v614)(134, &v861) | 0x10000000;
                        if ( v594 >= 0 )
                        {
                          v615 = DWORD1(v862);
                          goto LABEL_767;
                        }
                      }
                      else
                      {
                        v594 = GetLastError();
                        v613 = v594 < 0;
                        if ( v594 > 0 )
                        {
                          v594 = (unsigned __int16)v594 | 0x80070000;
                          v613 = v594 < 0;
                        }
                        if ( !v613 )
                        {
                          v781 = -2147467259;
                          goto LABEL_764;
                        }
                      }
                      if ( v594 == -805306333 )
                      {
                        v781 = -2147024774;
                        goto LABEL_764;
                      }
                      if ( v594 < 0 )
                        goto LABEL_726;
                      v615 = v780;
LABEL_767:
                      dwBytes = 0;
                      v800 = v506;
                      if ( v615 < 4 )
                      {
LABEL_768:
                        v781 = -805306306;
                        goto LABEL_764;
                      }
                      v616 = *v506;
                      v795 = *v506;
                      v617 = RtlULongLongAdd(v506, 4, &v800);
                      if ( v617 < 0 )
                        goto LABEL_820;
                      v617 = RtlUIntAdd(0, v618, &dwBytes);
                      if ( v617 < 0 )
                        goto LABEL_820;
                      if ( v619 - dwBytes < (unsigned int)v616 )
                        goto LABEL_768;
                      v794 = (SIZE_T)v800;
                      v802 = v616;
                      v617 = RtlULongLongAdd(v800, (unsigned int)v616, &v800);
                      if ( v617 < 0 )
                        goto LABEL_820;
                      v617 = RtlUIntAdd(dwBytes, (unsigned int)v616, &dwBytes);
                      if ( v617 < 0 )
                        goto LABEL_820;
                      if ( v620 - dwBytes < (unsigned int)v621 )
                        goto LABEL_768;
                      v780 = *(_DWORD *)v800;
                      v617 = RtlULongLongAdd(v800, v621, &v800);
                      if ( v617 < 0 )
                        goto LABEL_820;
                      v617 = RtlUIntAdd(dwBytes, v622, &dwBytes);
                      if ( v617 < 0 )
                        goto LABEL_820;
                      if ( v623 - dwBytes < (unsigned int)v624 )
                        goto LABEL_768;
                      Src = v800;
                      pcchLength = v624;
                      v617 = RtlULongLongAdd(v800, (unsigned int)v624, &v800);
                      if ( v617 < 0 )
                        goto LABEL_820;
                      v617 = RtlUIntAdd(dwBytes, v625, &dwBytes);
                      if ( v617 < 0 )
                        goto LABEL_820;
                      if ( v626 - dwBytes < v627 )
                        goto LABEL_768;
                      LODWORD(v784) = *(_DWORD *)v800;
                      v617 = RtlULongLongAdd(v800, 4, &v800);
                      if ( v617 < 0 )
                        goto LABEL_820;
                      v617 = RtlUIntAdd(dwBytes, 4, &dwBytes);
                      if ( v617 < 0 )
                        goto LABEL_820;
                      if ( v628 - dwBytes < v629 )
                        goto LABEL_768;
                      v617 = RtlUIntAdd(dwBytes, v629, &dwBytes);
                      if ( v617 < 0 )
                      {
LABEL_820:
                        v788 = v506;
                        v559 = v782;
                        v649 = (unsigned int *)v785;
                        goto LABEL_821;
                      }
                      if ( v630 != dwBytes || (unsigned int)(v631 + v632 + v616) + 12LL != v630 )
                        goto LABEL_768;
                      v633 = GetProcessHeap();
                      v634 = HeapAlloc(v633, 8u, 0x30u);
                      v635 = v634;
                      v792 = v634;
                      v559 = v782;
                      if ( !v634 )
                      {
                        v785 = 0;
                        v781 = -805306345;
                        v585 = 0;
                        goto LABEL_903;
                      }
                      v789 = v122;
                      v786 = v118;
                      v787 = v505;
                      v776 = 0;
                      if ( v794 )
                      {
                        *(_DWORD *)v634 = v795;
                        v636 = GetProcessHeap();
                        v637 = HeapAlloc(v636, 8u, v802);
                        v638 = v792;
                        if ( !v637 )
                        {
LABEL_800:
                          dwBytes_4 = -1073741801;
                          v788 = v506;
                          v790 = (LPVOID)v638[1];
                          if ( v790 )
                          {
                            v644 = GetProcessHeap();
                            HeapFree(v644, 0, v790);
                            v638 = v792;
                            *((_QWORD *)v792 + 1) = 0;
                          }
                          v790 = (LPVOID)v638[3];
                          if ( v790 )
                          {
                            v645 = GetProcessHeap();
                            HeapFree(v645, 0, v790);
                            v638 = v792;
                            *((_QWORD *)v792 + 3) = 0;
                          }
                          v790 = (LPVOID)v638[5];
                          if ( v790 )
                          {
                            v646 = GetProcessHeap();
                            HeapFree(v646, 0, v790);
                            *((_QWORD *)v792 + 5) = 0;
                          }
                          v647 = GetProcessHeap();
                          HeapFree(v647, 0, v792);
                          v648 = (unsigned int *)v776;
                          goto LABEL_810;
                        }
                        *((_QWORD *)v792 + 1) = v637;
                        dwBytes_4 = 0;
                        memcpy_0(v637, (const void *)v794, v802);
                        v635 = v792;
                      }
                      else
                      {
                        *(_DWORD *)v634 = 0;
                        v634[1] = 0;
                        dwBytes_4 = 0;
                      }
                      if ( Src )
                      {
                        v635[4] = v780;
                        v639 = GetProcessHeap();
                        v640 = HeapAlloc(v639, 8u, pcchLength);
                        v638 = v792;
                        if ( !v640 )
                        {
LABEL_799:
                          v789 = v122;
                          v786 = v118;
                          v782 = v559;
                          v787 = v505;
                          v792 = v638;
                          goto LABEL_800;
                        }
                        *((_QWORD *)v792 + 3) = v640;
                        dwBytes_4 = 0;
                        memcpy_0(v640, Src, pcchLength);
                        v635 = v792;
                      }
                      else
                      {
                        v635[4] = 0;
                        *((_QWORD *)v635 + 3) = 0;
                      }
                      if ( v800 )
                      {
                        v641 = (unsigned int)v784;
                        v635[8] = v784;
                        v802 = v641;
                        v642 = GetProcessHeap();
                        v643 = HeapAlloc(v642, 8u, v802);
                        v638 = v792;
                        if ( !v643 )
                          goto LABEL_799;
                        *((_QWORD *)v792 + 5) = v643;
                        dwBytes_4 = 0;
                        memcpy_0(v643, v800, v802);
                        v635 = v792;
                      }
                      else
                      {
                        v635[8] = 0;
                        *((_QWORD *)v635 + 5) = 0;
                      }
                      v648 = v635;
                      v776 = (size_t)v635;
                      v788 = v506;
                      v787 = v505;
                      v782 = v559;
                      v786 = v118;
                      v789 = v122;
LABEL_810:
                      v617 = dwBytes_4;
                      if ( (dwBytes_4 & 0x80000000) != 0 )
                      {
                        v649 = 0;
                        v785 = 0;
                        if ( v648 )
                        {
                          v790 = (LPVOID)*((_QWORD *)v648 + 1);
                          if ( v790 )
                          {
                            v650 = GetProcessHeap();
                            HeapFree(v650, 0, v790);
                            v648 = (unsigned int *)v776;
                            *(_QWORD *)(v776 + 8) = 0;
                          }
                          v790 = (LPVOID)*((_QWORD *)v648 + 3);
                          if ( v790 )
                          {
                            v651 = GetProcessHeap();
                            HeapFree(v651, 0, v790);
                            v648 = (unsigned int *)v776;
                            *(_QWORD *)(v776 + 24) = 0;
                          }
                          v790 = (LPVOID)*((_QWORD *)v648 + 5);
                          if ( v790 )
                          {
                            v652 = GetProcessHeap();
                            HeapFree(v652, 0, v790);
                            *(_QWORD *)(v776 + 40) = 0;
                          }
                          v653 = GetProcessHeap();
                          HeapFree(v653, 0, (LPVOID)v776);
                          v649 = 0;
                          v785 = 0;
                          v617 = dwBytes_4;
                        }
                      }
                      else
                      {
                        v649 = v648;
                        v785 = v648;
                      }
LABEL_821:
                      v781 = v617 | 0x10000000;
                      if ( v617 < 0 )
                        goto LABEL_764;
                      if ( !v649 || (Size = *((_QWORD *)v649 + 1)) == 0 || !*v649 )
                      {
                        v781 = -805306355;
                        goto LABEL_764;
                      }
                      pcchLength = *v649 - 8LL;
                      v654 = MemoryAlloc(pcchLength);
                      v777 = v654;
                      if ( !v654 )
                      {
LABEL_853:
                        v781 = -805306367;
                        v585 = 0;
                        goto LABEL_902;
                      }
                      v655 = 0;
                      v779 = 0;
                      v793 = (LPVOID)0x7F1137FAB69605ELL;
                      v656 = (unsigned __int8 *)Size;
                      v794 = Size;
                      Src = v654;
                      v657 = pcchLength;
                      v802 = pcchLength & 7;
                      if ( (pcchLength & 7) != 0 )
                      {
                        v798 = 0;
                        v780 = 0;
                        v795 = 0;
                        v658 = 0;
                        v659 = 0;
                        v660 = 0;
                        do
                        {
                          dwBytes_4 = *v656++;
                          v780 = 8 * v658;
                          if ( (unsigned int)v658 >= 4 )
                          {
                            dwBytes_4 <<= 56 - v780;
                            v660 |= dwBytes_4;
                          }
                          else
                          {
                            dwBytes_4 <<= 24 - v780;
                            v659 |= dwBytes_4;
                          }
                          ++v658;
                        }
                        while ( v658 < (int)v802 );
                        v798 = v660;
                        v780 = v659;
                        v794 = (SIZE_T)v656;
                        v788 = v506;
                        v787 = v505;
                        v782 = v559;
                        v786 = v118;
                        v789 = v122;
                        v655 = v779;
                        v657 = pcchLength;
                        v661 = v802;
                        v662 = v654;
                        v663 = v780 ^ 0x92F65A5;
                        v664 = v798 ^ 0x699A899C;
                        v665 = v780 ^ 0x92F65A5;
                        v795 = 0;
                        if ( (_DWORD)v802 )
                        {
                          v666 = v798 ^ 0x699A899C;
                          v667 = v795;
                          do
                          {
                            v790 = v662 + 1;
                            if ( v667 >= 4 )
                            {
                              v666 = __ROR4__(v666, 24);
                              v668 = v666;
                            }
                            else
                            {
                              v665 = __ROR4__(v665, 24);
                              v668 = v665;
                            }
                            *v662 = v668;
                            ++v667;
                            v662 = v790;
                          }
                          while ( (int)v667 < (int)v661 );
                          Src = v790;
                          v655 = v779;
                          v654 = v777;
                        }
                        if ( v661 <= 4 )
                        {
                          v669 = 0;
                          if ( v661 < 4 )
                            v663 = v663 >> (8 * (4 - v661)) << (8 * (4 - v661));
                        }
                        else
                        {
                          v669 = v664 >> (8 * (8 - v661)) << (8 * (8 - v661));
                        }
                      }
                      else
                      {
                        v780 = 0;
                        v669 = 0;
                        v663 = 0;
                      }
                      v670 = v657 >> 3;
                      if ( v657 >> 3 )
                      {
                        v802 = 0;
                        v671 = HIDWORD(v793);
                        v672 = WORD2(v793);
                        LODWORD(v784) = WORD2(v793);
                        v673 = WORD1(v793);
                        dwBytes_4 = 24670;
                        v674 = (unsigned __int8 *)v794;
                        v675 = Src;
                        v676 = v780;
                        do
                        {
                          v677 = v674[3] | ((v674[2] | (((*v674 << 8) | v674[1]) << 8)) << 8);
                          v678 = v674[7] | ((v674[6] | ((v674[5] | (v674[4] << 8)) << 8)) << 8);
                          v674 += 8;
                          v679 = v663 ^ v677;
                          v680 = v671 ^ v663 ^ v677 ^ v669 ^ v678 ^ 0xAB69605E;
                          v681 = v679 ^ (__ROR4__(v680, 22) + v672 * __ROR4__(v680 + 1419157410, 27));
                          v682 = v680 ^ (v673 * __ROR4__(v671 + v681, 9) - __ROR4__(v681, 30));
                          v683 = v681 ^ (dwBytes_4 * (v682 - v672) - (v682 >> 13));
                          v684 = v682 ^ (HIWORD(v793) * __ROR4__(v673 ^ v683, 26) - __ROR4__(v683, 30));
                          v685 = v683 ^ (v671 - (v684 ^ 0xAB69605E));
                          v686 = v684 ^ (v673 * (v672 ^ v685)) ^ __ROR4__(v685, 6);
                          v687 = v685 ^ (__ROR4__(v686, 30) + dwBytes_4 * __ROR4__(v671 + v686, 15));
                          v688 = v686 ^ (HIWORD(v793) * __ROR4__(v687 + 1419157410, 14) - __ROR4__(v687, 24));
                          v689 = v687 ^ __ROR4__(v688, 10) ^ (v784 * __ROR4__(v688 ^ 0xAB69605E, 12));
                          v690 = v689
                               ^ (HIWORD(v793)
                                * (dwBytes_4
                                 + __ROR4__(~(v688 ^ (v689 >> 10) ^ (WORD1(v793) * (HIWORD(v793) ^ v689))), 5)));
                          v691 = v688
                               ^ (v689 >> 10)
                               ^ (WORD1(v793) * (HIWORD(v793) ^ v689))
                               ^ (v690 - HIWORD(v793))
                               ^ 0xAB69605E;
                          v672 = v784;
                          v692 = v690 ^ ((v691 >> 2) + v784 * __ROR4__(HIWORD(v793) ^ v691, 30));
                          v673 = WORD1(v793);
                          v693 = v691 ^ (__ROR4__(v692, 25) + WORD1(v793) * __ROR4__(v692 - v671, 6));
                          v694 = v692 ^ (dwBytes_4 * (v784 ^ v693) + __ROR4__(v693, 9));
                          v695 = v693 ^ (__ROR4__(v694, 25) + HIWORD(v793) * __ROR4__(WORD1(v793) ^ v694, 27));
                          v696 = v694 ^ v695 ^ v671 ^ 0xAB69605E;
                          v697 = v695 ^ (v784 * (__ROR4__(v696, 3) - WORD1(v793)));
                          v698 = v696 ^ (dwBytes_4 * __ROR4__(v697 - v671, 1) - __ROR4__(v697, 6));
                          v699 = v697 ^ (__ROR4__(v698, 18) + HIWORD(v793) * __ROR4__(v698 - 1419157410, 29));
                          v700 = v698 ^ (v784 * __ROR4__(v699 - 1419157410, 17) - __ROR4__(v699, 14));
                          v701 = v699 ^ (v700 >> 3) ^ (WORD1(v793) * (v700 ^ dwBytes_4));
                          v663 = v700 ^ v676 ^ __ROR4__(v701, 30) ^ (dwBytes_4 * __ROR4__(v701 ^ v671, 28));
                          v669 = v701 ^ v798;
                          v675[3] = v663;
                          v675[7] = v669;
                          v675[2] = __ROR4__(v663, 8);
                          v675[6] = __ROR4__(v669, 8);
                          v675[1] = __ROR4__(v663, 16);
                          v675[5] = __ROR4__(v669, 16);
                          *v675 = __ROR4__(v663, 24);
                          v675[4] = __ROR4__(v669, 24);
                          v676 = v677;
                          v798 = v678;
                          v675 += 8;
                          ++v802;
                        }
                        while ( v802 < v670 );
                        v655 = v779;
                        v86 = v772;
                        v122 = v789;
                        v118 = v786;
                        v506 = (unsigned int *)v788;
                        v505 = (unsigned int *)v787;
                        v654 = v777;
                        v657 = pcchLength;
                      }
                      for ( j = 0; j < v657; ++j )
                        v655 ^= *((_BYTE *)v654 + j);
                      if ( v655 != *(_QWORD *)(v657 + Size) )
                      {
                        MemoryFree(v654);
                        goto LABEL_853;
                      }
                      v703 = v782;
                      v704 = v785;
                      v798 = 0;
                      v776 = (size_t)v654;
                      if ( (unsigned int)v657 < 4 )
                      {
                        v705 = -1073741762;
                        v585 = v777;
LABEL_897:
                        v559 = v703;
                        goto LABEL_898;
                      }
                      v705 = RtlULongLongAdd(v654, 4, &v776);
                      if ( v705 >= 0 )
                      {
                        v705 = RtlUIntAdd(0, 4, &v798);
                        if ( v705 >= 0 )
                        {
                          if ( v707 - v798 < 4 )
                            goto LABEL_895;
                          v708 = *(unsigned int *)v776;
                          v780 = *(_DWORD *)v776;
                          v705 = RtlULongLongAdd(v776, 4, &v776);
                          if ( v705 < 0 )
                            goto LABEL_896;
                          v705 = RtlUIntAdd(v798, 4, &v798);
                          if ( v705 < 0 )
                            goto LABEL_896;
                          if ( v709 - v798 < (unsigned int)v708 )
                            goto LABEL_895;
                          v705 = RtlUIntAdd(v798, (unsigned int)v708, &v798);
                          if ( v705 >= 0 )
                          {
                            v711 = v710;
                            v712 = (unsigned int *)v776;
                            if ( (unsigned __int64)v706 + v711 >= v708 + v776
                              && (unsigned __int64)v706 + v711 - v776 - v708 < 8 )
                            {
                              v795 = *v706;
                              v793 = 0;
                              v802 = 0;
                              v794 = 0;
                              LODWORD(v784) = 0;
                              if ( v776 )
                              {
                                v705 = RtlULongLongAdd(v776, (unsigned int)v708, &v793);
                                v781 = v705;
                                v785 = v704;
                                if ( v705 < 0 )
                                {
                                  v559 = v703;
                                  v585 = v713;
LABEL_891:
                                  v722 = v773;
LABEL_892:
                                  if ( v705 >= 0 && v795 != v722 )
                                    v705 = -1073741762;
                                  goto LABEL_898;
                                }
                                v714 = v712;
                                v813 = v712;
                                v715 = v793;
                                if ( v712 < v793 )
                                {
                                  v777 = v713;
                                  v782 = v703;
                                  while ( 1 )
                                  {
                                    v705 = RtlULongLongAdd(v714, 4, &v802);
                                    if ( v705 < 0 )
                                      break;
                                    if ( v802 > (unsigned __int64)v793 )
                                    {
                                      v705 = -1073741811;
LABEL_880:
                                      v559 = v782;
                                      v585 = v777;
                                      goto LABEL_898;
                                    }
                                    v798 = 0;
                                    v705 = RtlUIntAdd(4, *v714, &v798);
                                    if ( v705 < 0 )
                                      goto LABEL_880;
                                    v790 = v122;
                                    v716 = v118;
                                    v717 = v506;
                                    v718 = v704;
                                    Size = (SIZE_T)v704;
                                    v705 = RtlULongLongAdd(v714, v798, &v794);
                                    v781 = v705;
                                    v585 = v713;
                                    v785 = v718;
                                    v506 = v717;
                                    v559 = v703;
                                    v118 = v716;
                                    v122 = v790;
                                    if ( v705 < 0 )
                                      goto LABEL_891;
                                    v714 = (unsigned int *)v794;
                                    v813 = (void *)v794;
                                    v715 = v793;
                                    if ( v794 > (unsigned __int64)v793 )
                                    {
                                      v705 = -1073741811;
                                      v785 = (LPVOID)Size;
                                      goto LABEL_897;
                                    }
                                    LODWORD(v784) = v784 + 1;
                                    v777 = v713;
                                    v704 = (void *)Size;
                                    v785 = (LPVOID)Size;
                                    v782 = v703;
                                    if ( v794 >= (unsigned __int64)v793 )
                                    {
                                      v785 = (LPVOID)Size;
                                      goto LABEL_876;
                                    }
                                  }
                                  v559 = v782;
                                  v585 = v777;
                                  goto LABEL_891;
                                }
LABEL_876:
                                v585 = v713;
                                v559 = v703;
                                if ( v813 != v715 )
                                {
                                  v705 = -1073741811;
LABEL_898:
                                  v781 = v705 | 0x10000000;
                                  goto LABEL_903;
                                }
                              }
                              else
                              {
                                v781 = 0;
                                v785 = v704;
                                v559 = v703;
                                v585 = v706;
                              }
                              v719 = 0;
                              v802 = 0;
                              v720 = v780;
                              if ( v780 )
                              {
                                v721 = GetProcessHeap();
                                v719 = HeapAlloc(v721, 8u, (unsigned int)v780);
                                v802 = (SIZE_T)v719;
                                if ( !v719 )
                                {
                                  v705 = -1073741801;
                                  goto LABEL_898;
                                }
                                v781 = 0;
                                v712 = (unsigned int *)v776;
                                v720 = v780;
                              }
                              if ( v712 )
                                memcpy_0(v719, v712, v720);
                              v783 = (unsigned int *)v802;
                              v722 = v784;
                              v773 = v784;
                              v705 = v781;
                              goto LABEL_892;
                            }
LABEL_895:
                            v705 = -1073741762;
                          }
                        }
                      }
LABEL_896:
                      v785 = v704;
                      v585 = v706;
                      goto LABEL_897;
                    }
                  }
                }
              }
            }
          }
          v782 = v559;
          v593 = GetProcessHeap();
          HeapFree(v593, 0, v786);
        }
        v592 = v781;
        goto LABEL_722;
      }
LABEL_691:
      v505 = (unsigned int *)v793;
      v793 = 0;
      goto LABEL_692;
    }
    pcchLength = v801[1];
    if ( v484 )
    {
      do
      {
        v773 = 0;
        if ( (int)RtlUIntAdd(4, *v485, &v773) < 0 || (int)RtlULongLongAdd(v487, v773, &pcchLength) < 0 )
          goto LABEL_578;
        v485 = (unsigned int *)pcchLength;
      }
      while ( v489 + 1 < v488 );
    }
    if ( (int)RtlULongLongAdd(v485, 4, &v803) >= 0 && (unsigned __int64)(v490 + 3) <= v801[1] + HIDWORD(v801[0]) )
    {
      *v490 = 8;
      *(_QWORD *)v803 = v790;
      goto LABEL_634;
    }
LABEL_578:
    v119 = (size_t)v783;
    goto LABEL_579;
  }
LABEL_587:
  v81 = v821;
  v813 = 0;
  v849 = (int *)TickCount64;
  v80 = v822;
LABEL_945:
  v76 = v829;
  v7 = v828;
  v70 = v816;
LABEL_946:
  SP<unsigned char,SP_HLOCAL<unsigned char>>::Reset(&v813);
  if ( v86 >= 0 )
  {
    if ( v81 != 4 )
    {
LABEL_954:
      v86 = -1073418210;
      goto LABEL_958;
    }
    v86 = 0;
    v80 = *v849;
  }
  else
  {
    switch ( v86 )
    {
      case -805306316:
        v86 = -1073418222;
        break;
      case -805306139:
      case -1073425151:
        v86 = -1073418201;
        break;
      case -805306306:
        v86 = -1073418200;
        break;
      case -2147024774:
        goto LABEL_954;
    }
  }
LABEL_958:
  SP<unsigned char,SP_HLOCAL<unsigned char>>::Reset(&v849);
  v749 = 0;
  if ( v86 >= 0 )
    v749 = v80;
  ConfigData = CSLQuery::IsAppServerAllowed(&v820);
  if ( ConfigData < 0 )
  {
    if ( (unsigned int)dword_180128170 > 3 && (unsigned __int8)tlgKeywordOn(&dword_180128170, 0) )
    {
      v914 = "UpdateConfig";
      v842 = ConfigData;
      v915 = "CSLQuery::IsAppServerAllowed";
      v916 = "Warning HResult failed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        v750,
        (unsigned int)qword_1801083F0,
        v751,
        v752,
        (__int64)&v916,
        (__int64)&v915,
        (__int64)&v842,
        (__int64)&v914);
    }
    goto LABEL_990;
  }
  if ( !v820 && !v749 )
  {
    *((_DWORD *)v70 + 32) &= 0xFFFFAFFF;
    *((_DWORD *)v70 + 32) |= 0x2000u;
  }
  if ( (int)CRemoteTerminal::IsAdminSession(v76, &v819) >= 0 )
  {
    v756 = v819;
  }
  else
  {
    if ( (unsigned int)dword_180128170 > 3 && (unsigned __int8)tlgKeywordOn(&dword_180128170, 0) )
    {
      v843 = v754;
      v917 = "CRemoteTerminal::IsAdminSession failed, assuming admin session";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        v753,
        (unsigned int)word_1801083CA,
        v754,
        v755,
        (__int64)&v917,
        (__int64)&v843);
    }
    v756 = 1;
  }
  if ( v756 )
    *((_DWORD *)v70 + 32) = *((_DWORD *)v70 + 32) & 0xFFFF87FF | 0x2800;
  v757 = *((_DWORD *)v76 + 1276);
  v758 = (int *)((char *)v76 + 5104);
  if ( (v757 & 0x40000000) != 0 )
  {
    v757 = 44;
    *v758 = 44;
  }
  v759 = v70 + 124;
  if ( (*((_DWORD *)v70 + 31) & 0x10000) != 0 )
  {
    v757 |= 1u;
    *v758 = v757;
  }
  if ( (*v759 & 0x2000000) != 0 )
  {
    v757 |= 0x40u;
    *v758 = v757;
  }
  if ( v818 && v817 )
  {
    v757 &= ~0x80u;
    *v758 = v757;
  }
  if ( v756 )
  {
    v757 |= 8u;
    *v758 = v757;
  }
  *v759 ^= (*v759 ^ (v757 << 16)) & 0x10000;
  ConfigData = (*(__int64 (__fastcall **)(_QWORD, struct IUserName *, unsigned __int8 *))(**((_QWORD **)v76 + 200)
                                                                                        + 128LL))(
                 *((_QWORD *)v76 + 200),
                 v850,
                 v70);
  if ( ConfigData < 0 )
  {
    if ( (unsigned int)dword_180128170 > 3 && (unsigned __int8)tlgKeywordOn(&dword_180128170, 0) )
    {
      v918 = "UpdateConfig";
      v844 = ConfigData;
      v919 = "ptrConnection->SetConfigData";
      v920 = "Warning HResult failed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        v760,
        (unsigned int)&byte_18010838F,
        v761,
        v762,
        (__int64)&v920,
        (__int64)&v919,
        (__int64)&v844,
        (__int64)&v918);
    }
    goto LABEL_990;
  }
  v6 = v810;
LABEL_995:
  if ( (unsigned int)dword_180128170 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180128170, 0) )
  {
    v846 = ConfigData;
    v923 = "CRemoteTerminal::UpdateConfig";
    v924 = "Task completed successfully";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      v766,
      (unsigned int)&byte_18010831F,
      v767,
      v768,
      (__int64)&v924,
      (__int64)&v923,
      (__int64)&v846);
  }
  v7 = v6;
LABEL_999:
  if ( v7 )
  {
    v769 = 30;
    v770 = v7 + 210;
    do
    {
      *v770++ = 0;
      --v769;
    }
    while ( v769 );
  }
  operator delete(v6);
  if ( StringSid )
    LocalFree(StringSid);
  if ( Sid )
    CoTaskMemFree(Sid);
  CAutoSetActivityId::~CAutoSetActivityId((CAutoSetActivityId *)v931);
  CImpersonate::StopImpersonating((CImpersonate *)&v805);
  SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(&v830);
  return (unsigned int)ConfigData;
}

```

## disassembly

```asm
0x180053628  mov     [rsp-8+arg_10], rbx
0x18005362d  push    rbp
0x18005362e  push    rsi
0x18005362f  push    rdi
0x180053630  push    r12
0x180053632  push    r13
0x180053634  push    r14
0x180053636  push    r15
0x180053638  lea     rbp, [rsp-6E0h]
0x180053640  sub     rsp, 7E0h
0x180053647  mov     rax, cs:__security_cookie
0x18005364e  xor     rax, rsp
0x180053651  mov     [rbp+710h+var_40], rax
0x180053658  mov     r12d, r8d
0x18005365b  mov     [rbp+710h+var_5D8], rdx
0x180053662  mov     rsi, rcx
0x180053665  mov     [rbp+710h+var_640], rcx
0x18005366c  xor     r15d, r15d
0x18005366f  mov     ebx, r15d
0x180053672  mov     edi, r15d
0x180053675  mov     [rbp+710h+var_648], r15
0x18005367c  mov     [rbp+710h+StringSid], r15
0x180053683  mov     [rbp+710h+Sid], r15
0x18005368a  xorps   xmm0, xmm0
0x18005368d  movups  xmmword ptr [rbp+710h+var_2C8.Data1], xmm0
0x180053694  mov     [rbp+710h+var_66C], 1
0x18005369e  mov     [rbp+710h+var_674], r15d
0x1800536a5  mov     [rbp+710h+var_678], r15d
0x1800536ac  mov     [rbp+710h+var_638], r15
0x1800536b3  mov     [rbp+710h+var_6C8], r15w
0x1800536b8  mov     [rbp+710h+var_670], r15d
0x1800536bf  movups  [rbp+710h+Buf1], xmm0
0x1800536c6  mov     [rbp+710h+hKey], r15
0x1800536ca  mov     [rbp+710h+Type], r15d
0x1800536d1  mov     dword ptr [rbp+710h+Data], r15d
0x1800536d5  mov     [rbp+710h+cbData], 4
0x1800536df  xor     edx, edx; Val
0x1800536e1  mov     r8d, 208h; Size
0x1800536e7  lea     rcx, [rbp+710h+SubKey]; void *
0x1800536ee  call    memset_0
0x1800536f3  xorps   xmm0, xmm0
0x1800536f6  movups  xmmword ptr [rbp+710h+var_2E8.Data1], xmm0
0x1800536fd  lea     rdx, [rbp+710h+var_2E8]; struct _GUID *
0x180053704  lea     rcx, [rbp+710h+var_2B8]; this
0x18005370b  call    ??0CAutoSetActivityId@@QEAA@PEAU_GUID@@@Z; CAutoSetActivityId::CAutoSetActivityId(_GUID *)
0x180053710  nop
0x180053711  mov     eax, cs:dword_180128170
0x180053717  lea     r13, aCremotetermina_32; "CRemoteTerminal::UpdateConfig"
0x18005371e  lea     rcx, aGroupPolicy; "Group Policy"
0x180053725  cmp     eax, 4
0x180053728  jbe     short loc_180053790
0x18005372a  movsxd  rax, dword ptr [rsi+690h]
0x180053731  mov     [rbp+710h+var_350], rax
0x180053738  lea     rax, aRemoteterminal_4; "RemoteTerminal->UpdateConfig()"
0x18005373f  mov     [rbp+710h+var_348], rax
0x180053746  mov     [rbp+710h+var_340], r13
0x18005374d  mov     [rbp+710h+var_550], rcx
0x180053754  lea     rax, [rbp+710h+var_350]
0x18005375b  mov     [rsp+810h+var_7D8], rax
0x180053760  lea     rax, [rbp+710h+var_348]
0x180053767  mov     [rsp+810h+var_7E0], rax
0x18005376c  lea     rax, [rbp+710h+var_340]
0x180053773  mov     [rsp+810h+lpcbData], rax
0x180053778  lea     rax, [rbp+710h+var_550]
0x18005377f  mov     [rsp+810h+phkResult], rax
0x180053784  lea     rdx, qword_180108870
0x18005378b  call    ??$Write@U?$_tlgWrapSz@D@@U1@U1@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@33AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &)
0x180053790  call    cs:__imp_GetTickCount64
0x180053796  mov     [rbp+710h+var_630], rax
0x18005379d  cmp     [rsi+640h], r15
0x1800537a4  jnz     loc_180053831
0x1800537aa  mov     r14d, 800708CAh
0x1800537b0  mov     eax, cs:dword_180128170
0x1800537b6  cmp     eax, 3
0x1800537b9  jbe     loc_180059FC2
0x1800537bf  lea     rax, aUpdateconfig; "UpdateConfig"
0x1800537c6  mov     [rbp+710h+var_548], rax
0x1800537cd  mov     [rbp+710h+var_604], r14d
0x1800537d4  lea     rax, aCheckForPresen; "check for presence of connection object"
0x1800537db  mov     [rbp+710h+var_540], rax
0x1800537e2  lea     rax, aWarningHresult; "Warning HResult failed"
0x1800537e9  mov     [rbp+710h+var_538], rax
0x1800537f0  lea     rax, [rbp+710h+var_548]
0x1800537f7  mov     [rsp+810h+var_7D8], rax
0x1800537fc  lea     rax, [rbp+710h+var_604]
0x180053803  mov     [rsp+810h+var_7E0], rax
0x180053808  lea     rax, [rbp+710h+var_540]
0x18005380f  mov     [rsp+810h+lpcbData], rax
0x180053814  lea     rax, [rbp+710h+var_538]
0x18005381b  lea     rdx, byte_180108835
0x180053822  mov     [rsp+810h+phkResult], rax
0x180053827  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18005382c  jmp     loc_180059FC2
0x180053831  lea     rdx, [rbp+710h+var_2E8]; struct _GUID *
0x180053838  mov     rcx, rsi; this
0x18005383b  call    ?GetActivityId@CRemoteTerminal@@UEAAJPEAU_GUID@@@Z; CRemoteTerminal::GetActivityId(_GUID *)
0x180053840  mov     edi, 2
0x180053845  cmp     [rbp+710h+var_2A8], r15d
0x18005384c  jl      short loc_18005385D
0x18005384e  lea     rdx, [rbp+710h+var_2E8]
0x180053855  mov     ecx, edi
0x180053857  call    cs:__imp_EtwEventActivityIdControl
0x18005385d  mov     rcx, [rsi+640h]
0x180053864  mov     rax, [rcx]
0x180053867  lea     rdx, [rbp+710h+Buf1]
0x18005386e  mov     rax, [rax+150h]
0x180053875  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005387a  mov     r14d, eax
0x18005387d  test    eax, eax
0x18005387f  jns     loc_180053905
0x180053885  mov     eax, cs:dword_180128170
0x18005388b  cmp     eax, 3
0x18005388e  jbe     short loc_1800538FD
0x180053890  lea     rax, aUpdateconfig; "UpdateConfig"
0x180053897  mov     [rbp+710h+var_530], rax
0x18005389e  mov     [rbp+710h+var_5EC], r14d
0x1800538a5  lea     rax, aPtrconnectionG_1; "ptrConnection->GetConnectionGUID"
0x1800538ac  mov     [rbp+710h+var_528], rax
0x1800538b3  lea     rax, aWarningHresult; "Warning HResult failed"
0x1800538ba  mov     [rbp+710h+var_520], rax
0x1800538c1  lea     rax, [rbp+710h+var_530]
0x1800538c8  mov     [rsp+810h+var_7D8], rax
0x1800538cd  lea     rax, [rbp+710h+var_5EC]
0x1800538d4  mov     [rsp+810h+var_7E0], rax
0x1800538d9  lea     rax, [rbp+710h+var_528]
0x1800538e0  mov     [rsp+810h+lpcbData], rax
0x1800538e5  lea     rax, [rbp+710h+var_520]
0x1800538ec  mov     [rsp+810h+phkResult], rax
0x1800538f1  lea     rdx, word_1801087FA
0x1800538f8  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x1800538fd  mov     rdi, r15
0x180053900  jmp     loc_180059FC2
0x180053905  mov     r8d, 10h; Size
0x18005390b  lea     rdx, TERMINAL_TYPE_DEBUG; Buf2
0x180053912  lea     rcx, [rbp+710h+Buf1]; Buf1
0x180053919  call    memcmp_0
0x18005391e  test    eax, eax
0x180053920  jnz     short loc_180053948
0x180053922  test    byte ptr cs:?g_DebugTraceComponent@@3KA, 4; ulong g_DebugTraceComponent
0x180053929  jz      short loc_180053940
0x18005392b  mov     r8d, [rsi+690h]
0x180053932  lea     rdx, aConnectionForS; "Connection for session %d is debug"
0x180053939  mov     ecx, edi; int
0x18005393b  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180053940  mov     r14d, r15d
0x180053943  jmp     loc_18005A040
0x180053948  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18005394f  mov     r14d, 1E40h
0x180053955  mov     ecx, r14d; unsigned __int64
0x180053958  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18005395d  mov     rdi, rax
0x180053960  mov     [rbp+710h+var_680], rax
0x180053967  mov     rbx, rax
0x18005396a  mov     [rbp+710h+var_6A8], rax
0x18005396e  test    rax, rax
0x180053971  jnz     short loc_180053985
0x180053973  mov     r14d, 8007000Eh
0x180053979  mov     rdi, [rbp+710h+var_648]
0x180053980  jmp     loc_180059FC2
0x180053985  mov     r8, r14; Size
0x180053988  xor     edx, edx; Val
0x18005398a  mov     rcx, rdi; void *
0x18005398d  call    memset_0
0x180053992  mov     r8d, 0A68h; unsigned int
0x180053998  mov     rdx, rdi; unsigned __int8 *
0x18005399b  mov     rcx, rsi; this
0x18005399e  call    ?GetConfigData@CRemoteTerminal@@UEAAJPEAEK@Z; CRemoteTerminal::GetConfigData(uchar *,ulong)
0x1800539a3  mov     r14d, eax
0x1800539a6  test    eax, eax
0x1800539a8  jns     short loc_180053A21
0x1800539aa  mov     eax, cs:dword_180128170
0x1800539b0  cmp     eax, 3
0x1800539b3  jbe     loc_180059FC2
0x1800539b9  lea     rax, aUpdateconfig; "UpdateConfig"
0x1800539c0  mov     [rbp+710h+var_518], rax
0x1800539c7  mov     [rbp+710h+var_5E8], r14d
0x1800539ce  lea     rax, aTerminalGetcon; "Terminal->GetConfigData"
0x1800539d5  mov     [rbp+710h+var_510], rax
0x1800539dc  lea     rax, aWarningHresult; "Warning HResult failed"
0x1800539e3  mov     [rbp+710h+var_508], rax
0x1800539ea  lea     rax, [rbp+710h+var_518]
0x1800539f1  mov     [rsp+810h+var_7D8], rax
0x1800539f6  lea     rax, [rbp+710h+var_5E8]
0x1800539fd  mov     [rsp+810h+var_7E0], rax
0x180053a02  lea     rax, [rbp+710h+var_510]
0x180053a09  mov     [rsp+810h+lpcbData], rax
0x180053a0e  lea     rax, [rbp+710h+var_508]
0x180053a15  lea     rdx, byte_1801087BF
0x180053a1c  jmp     loc_180053822
0x180053a21  lea     r13, [rdi+0A70h]
0x180053a28  mov     rcx, [rsi+640h]
0x180053a2f  mov     rax, [rcx]
0x180053a32  lea     rdx, [rbp+710h+var_2A0]
0x180053a39  mov     rax, [rax+40h]
0x180053a3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053a42  test    eax, eax
0x180053a44  js      loc_180053B8C
0x180053a4a  lea     rax, [rbp+710h+hKey]
0x180053a4e  mov     [rsp+810h+phkResult], rax; phkResult
0x180053a53  mov     r9d, 20019h; samDesired
0x180053a59  xor     r8d, r8d; ulOptions
0x180053a5c  lea     r14, aSoftwarePolici; "Software\\Policies\\Microsoft\\Windows "...
0x180053a63  mov     rdx, r14; lpSubKey
0x180053a66  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180053a6d  call    cs:__imp_RegOpenKeyExW
0x180053a73  test    eax, eax
0x180053a75  jz      short loc_180053AC4
0x180053a77  mov     eax, cs:dword_180128170
0x180053a7d  cmp     eax, 4
0x180053a80  jbe     loc_180053B8C
0x180053a86  mov     [rbp+710h+var_500], r14
0x180053a8d  lea     rax, aCouldNotOpenPo; "Could not open policy reg-key for Query"...
0x180053a94  mov     [rbp+710h+var_4F8], rax
0x180053a9b  lea     rax, [rbp+710h+var_500]
0x180053aa2  mov     [rsp+810h+lpcbData], rax
0x180053aa7  lea     rax, [rbp+710h+var_4F8]
0x180053aae  mov     [rsp+810h+phkResult], rax
0x180053ab3  lea     rdx, word_18010878A
0x180053aba  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x180053abf  jmp     loc_180053B8C
0x180053ac4  lea     rax, [rbp+710h+cbData]
0x180053acb  mov     [rsp+810h+lpcbData], rax; lpcbData
0x180053ad0  lea     rax, [rbp+710h+Data]
0x180053ad4  mov     [rsp+810h+phkResult], rax; lpData
0x180053ad9  lea     r9, [rbp+710h+Type]; lpType
0x180053ae0  xor     r8d, r8d; lpReserved
0x180053ae3  lea     rdx, aFqueryuserconf; "fQueryUserConfigFromDC"
0x180053aea  mov     rcx, [rbp+710h+hKey]; hKey
0x180053aee  call    cs:__imp_RegQueryValueExW
0x180053af4  mov     ebx, eax
0x180053af6  mov     ecx, cs:dword_180128170
0x180053afc  cmp     ecx, 5
0x180053aff  jbe     short loc_180053B62
0x180053b01  mov     ecx, dword ptr [rbp+710h+Data]
0x180053b04  mov     [rbp+710h+var_4F0], rcx
0x180053b0b  mov     [rbp+710h+var_5C0], eax
0x180053b11  mov     [rbp+710h+var_4E8], r14
0x180053b18  lea     rax, aPolicyRegKeyVa; "Policy reg-key value for QueryLocalUser"...
0x180053b1f  mov     [rbp+710h+var_4E0], rax
0x180053b26  lea     rax, [rbp+710h+var_4F0]
0x180053b2d  mov     [rsp+810h+var_7D8], rax
0x180053b32  lea     rax, [rbp+710h+var_5C0]
0x180053b39  mov     [rsp+810h+var_7E0], rax
0x180053b3e  lea     rax, [rbp+710h+var_4E8]
0x180053b45  mov     [rsp+810h+lpcbData], rax
0x180053b4a  lea     rax, [rbp+710h+var_4E0]
0x180053b51  mov     [rsp+810h+phkResult], rax
0x180053b56  lea     rdx, byte_180108737
0x180053b5d  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x180053b62  mov     rcx, [rbp+710h+hKey]; hKey
0x180053b66  call    cs:__imp_RegCloseKey
0x180053b6c  mov     [rbp+710h+hKey], 0
0x180053b74  xor     ecx, ecx; hKey
0x180053b76  call    cs:__imp_RegCloseKey
0x180053b7c  mov     [rbp+710h+hKey], 0
0x180053b84  test    ebx, ebx
0x180053b86  jz      loc_180053CEA
0x180053b8c  lea     rax, [rbp+710h+var_2A0]
0x180053b93  mov     [rsp+810h+phkResult], rax
0x180053b98  lea     r9, aSystemCurrentc_10; "System\\CurrentControlSet\\Control\\Ter"...
0x180053b9f  lea     r8, aSS_0; "%s\\%s"
0x180053ba6  mov     edx, 104h; unsigned __int64
0x180053bab  lea     rcx, [rbp+710h+SubKey]; unsigned __int16 *
0x180053bb2  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180053bb7  lea     rax, [rbp+710h+hKey]
0x180053bbb  mov     [rsp+810h+phkResult], rax; phkResult
0x180053bc0  mov     r9d, 20019h; samDesired
0x180053bc6  xor     r8d, r8d; ulOptions
0x180053bc9  lea     rdx, [rbp+710h+SubKey]; lpSubKey
0x180053bd0  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180053bd7  call    cs:__imp_RegOpenKeyExW
0x180053bdd  test    eax, eax
0x180053bdf  jz      short loc_180053C35
0x180053be1  mov     eax, cs:dword_180128170
0x180053be7  cmp     eax, 4
0x180053bea  jbe     loc_180053CEA
0x180053bf0  lea     rax, [rbp+710h+SubKey]
0x180053bf7  mov     [rbp+710h+var_4D8], rax
0x180053bfe  lea     rax, aCouldNotOpenWi; "Could not open Winsta reg-key for Query"...
0x180053c05  mov     [rbp+710h+var_4D0], rax
0x180053c0c  lea     rax, [rbp+710h+var_4D8]
0x180053c13  mov     [rsp+810h+lpcbData], rax
0x180053c18  lea     rax, [rbp+710h+var_4D0]
0x180053c1f  mov     [rsp+810h+phkResult], rax
0x180053c24  lea     rdx, byte_180108707
0x180053c2b  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x180053c30  jmp     loc_180053CEA
0x180053c35  lea     rax, [rbp+710h+cbData]
0x180053c3c  mov     [rsp+810h+lpcbData], rax; lpcbData
0x180053c41  lea     rax, [rbp+710h+Data]
0x180053c45  mov     [rsp+810h+phkResult], rax; lpData
0x180053c4a  lea     r9, [rbp+710h+Type]; lpType
0x180053c51  xor     r8d, r8d; lpReserved
0x180053c54  lea     rdx, aFqueryuserconf; "fQueryUserConfigFromDC"
0x180053c5b  mov     rcx, [rbp+710h+hKey]; hKey
0x180053c5f  call    cs:__imp_RegQueryValueExW
0x180053c65  mov     ecx, cs:dword_180128170
0x180053c6b  cmp     ecx, 5
0x180053c6e  jbe     short loc_180053CD8
0x180053c70  mov     ecx, dword ptr [rbp+710h+Data]
  ... truncated ...
```
