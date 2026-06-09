# CRemoteTerminal::UpdateConfig(IUserName *,ulong)

- ea: `0x180055d8c`
- end: `0x18005cde3`
- name: `?UpdateConfig@CRemoteTerminal@@AEAAJPEAUIUserName@@K@Z`
- size: `28759`
- prototype: `__int64 __fastcall(CRemoteTerminal *__hidden this, struct IUserName *, unsigned int)`
- caller_count: `2`
- callee_count: `37`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180049650`
- `0x180055150`

## callees

- `0x180001294`
- `0x1800016a8`
- `0x180001a50`
- `0x180002280`
- `0x18000256c`
- `0x18000259c`
- `0x1800029f0`
- `0x180009940`
- `0x1800139c0`
- `0x1800146c8`
- `0x180014d70`
- `0x1800155f0`
- `0x180015938`
- `0x180015b64`
- `0x180016290`
- `0x18001637c`
- `0x180016558`
- `0x180018394`
- `0x180026068`
- `0x1800269e0`
- `0x180026a10`
- `0x180026ad8`
- `0x180029574`
- `0x180029dc0`
- `0x180029df4`
- `0x180033f60`
- `0x18003440c`
- `0x180034470`
- `0x180034e64`
- `0x180054310`
- `0x180055d8c`
- `0x18006f228`
- `0x1800b77d4`
- `0x1800bf598`
- `0x1800caed0`
- `0x1800caedc`
- `0x1800ce010`

## import_xrefs

- `ntdll!EtwEventActivityIdControl` at `0x180055fc1`
- `ntdll!EtwEventActivityIdControl` at `0x180055fc1`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x180058e02`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18005b718`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x180058e02`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18005b718`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180058e57`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18005b75c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180058e57`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18005b75c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180056ca1`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180056d75`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180057028`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18005723f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800572de`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180057bd3`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180058211`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180058287`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800582e6`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180058393`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800586b8`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180058c24`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800590ba`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18005912f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18005919c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18005920c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180059c69`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18005a230`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18005a7c5`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18005ae2d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18005ae6f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18005aed0`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18005af83`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18005b2a8`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18005b569`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18005b9ad`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18005ba1b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18005ba8e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18005baff`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18005c575`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180056ca1`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180056d75`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180057028`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18005723f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800572de`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180057bd3`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180058211`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180058287`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800582e6`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180058393`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800586b8`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180058c24`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800590ba`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18005912f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18005919c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18005920c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180059c69`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18005a230`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18005a7c5`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18005ae2d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18005ae6f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18005aed0`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18005af83`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18005b2a8`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18005b569`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18005b9ad`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18005ba1b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18005ba8e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18005baff`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18005c575`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180056c85`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180056d61`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180057011`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180057161`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180057192`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800571b7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800571dc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180057223`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800572ca`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180057bbc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180057c81`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800581f9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005826c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800582cc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005837a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800583e4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005841e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180058458`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180058485`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800584e0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005851b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180058555`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005858f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800585bc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800586a1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800586ed`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180058725`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005875b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180058791`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800587ba`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800587e3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180058808`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005883e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005886f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800588a0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800588c8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800588f1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180058a88`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180058c0d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800590a2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180059117`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180059184`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800591f5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005925d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180059297`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800592d1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800592fe`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005939e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800593d9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180059414`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180059442`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180059c51`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005a219`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005a260`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005a28d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005a2b2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005a2d7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005a7ae`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005a86d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005ae15`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005ae58`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005aeb6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005af6a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005afd0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005b00a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005b044`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005b071`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005b0d2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005b10d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005b147`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005b181`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005b1ae`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005b291`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005b40b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005b552`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005b995`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005ba03`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005ba76`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005bae7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005bb48`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005bb82`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005bbbc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005bbe9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005bc89`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005bcc4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005bcff`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005bd2d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005c55c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005c62a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005c65c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005c68d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005c6be`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005c6e6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005c70f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005c734`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005c76a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005c79b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005c7cc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005c7f4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005c819`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180056c85`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180056d61`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180057011`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180057161`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180057192`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800571b7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800571dc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180057223`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800572ca`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180057bbc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180057c81`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800581f9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005826c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800582cc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005837a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800583e4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005841e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180058458`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180058485`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800584e0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005851b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180058555`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005858f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800585bc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800586a1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800586ed`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180058725`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005875b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180058791`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800587ba`

## string_xrefs

- `0x180058df6`: `ntdll.dll`
- `0x18005b70c`: `ntdll.dll`
- `0x1800561cc`: `Software\Policies\Microsoft\Windows NT\Terminal Services`
- `0x18005ccfb`: `Task completed successfully`
- `0x180055e9c`: `RemoteTerminal->UpdateConfig()`
- `0x180055e7b`: `CRemoteTerminal::UpdateConfig`
- `0x1800569aa`: `CRemoteTerminal::UpdateConfig`
- `0x18005cc4b`: `CRemoteTerminal::UpdateConfig`
- `0x18005ccc9`: `CRemoteTerminal::UpdateConfig`
- `0x180055f29`: `UpdateConfig`
- `0x180056000`: `UpdateConfig`
- `0x180056129`: `UpdateConfig`
- `0x1800564b3`: `UpdateConfig`
- `0x180056549`: `UpdateConfig`
- `0x18005665a`: `UpdateConfig`
- `0x180056741`: `UpdateConfig`
- `0x1800567d8`: `UpdateConfig`
- `0x1800568e8`: `UpdateConfig`
- `0x1800569e4`: `UpdateConfig`
- `0x180056aae`: `UpdateConfig`
- `0x180056b95`: `UpdateConfig`
- `0x18005ca00`: `UpdateConfig`
- `0x18005cbda`: `UpdateConfig`
- `0x18005613e`: `Terminal->GetConfigData`
- `0x180056203`: `Could not open policy reg-key for QueryLocalUserCfg`
- `0x180056259`: `fQueryUserConfigFromDC`
- `0x1800563e2`: `fQueryUserConfigFromDC`
- `0x18005638c`: `Could not open Winsta reg-key for QueryLocalUserCfg`
- `0x1800564c8`: `IUserConfig::GetInstanceOfUserConfig`
- `0x18005666f`: `ptrUserConfig->UpdateConfig`
- `0x180056756`: `ptrUserConfig->UpdateConfigFromLocal`
- `0x1800567ed`: `ptrUserConfig->GetConfig`
- `0x180056879`: `UpdateConfig to get TSUserEX info`
- `0x1800568fd`: `GetUserSid`
- `0x1800569f9`: `Impersonate.ImpersonateUser`
- `0x180056ac3`: `Impersonate.StopImpersonating`
- `0x180056ef7`: `TerminalServices-DeviceRedirection-Licenses-TSEasyPrintAllowed`
- `0x180057665`: `TerminalServices-DeviceRedirection-Licenses-TSEasyPrintAllowed`
- `0x1800577ad`: `TerminalServices-DeviceRedirection-Licenses-TSEasyPrintAllowed`
- `0x18005cbef`: `ptrConnection->SetConfigData`

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
  __int64 v11; // r8
  int v12; // r9d
  signed int ConfigData; // r14d
  int v14; // ecx
  int v15; // r9d
  unsigned __int8 *v16; // rax
  int v17; // ecx
  int v18; // r9d
  unsigned __int8 *v19; // r13
  int v20; // ecx
  int v21; // r8d
  int v22; // r9d
  LSTATUS v23; // eax
  int v24; // r8d
  int v25; // r9d
  LSTATUS v26; // ebx
  int v27; // ecx
  int v28; // r8d
  int v29; // r9d
  LSTATUS v30; // eax
  int v31; // r8d
  int v32; // r9d
  int v33; // ecx
  int v34; // r9d
  int v35; // ecx
  int v36; // r9d
  int v37; // eax
  int v38; // r8d
  int v39; // r9d
  struct IUserConfig *v40; // rbx
  int v41; // ecx
  int v42; // r9d
  int v43; // eax
  int v44; // r8d
  int v45; // r9d
  int v46; // ecx
  int v47; // r9d
  int v48; // ecx
  int v49; // r9d
  __int64 v50; // rsi
  unsigned __int8 *v51; // rdi
  ULONGLONG v52; // rax
  int v53; // r8d
  int v54; // r9d
  struct IUserName *v55; // rbx
  int v56; // ecx
  int v57; // r9d
  signed int LastError; // eax
  int v59; // ecx
  int v60; // r9d
  unsigned __int8 *v61; // r12
  unsigned __int8 *v62; // rbx
  char UserPolicy; // al
  int v64; // ecx
  int v65; // r9d
  CRemoteTerminal *v66; // r13
  int v67; // ecx
  int v68; // r9d
  int v69; // esi
  unsigned int v70; // ebx
  HLOCAL v71; // rax
  HANDLE ProcessHeap; // rax
  _OWORD *v73; // rax
  void *v74; // r15
  int v75; // r14d
  void *v76; // r12
  HANDLE v77; // rax
  _QWORD *v78; // rax
  int v79; // eax
  unsigned int v80; // ecx
  unsigned int v81; // r10d
  int v82; // eax
  unsigned int v83; // r10d
  int v84; // eax
  unsigned int v85; // r10d
  int v86; // eax
  size_t v87; // rdx
  int v88; // eax
  unsigned int v89; // r10d
  int v90; // eax
  unsigned int v91; // r10d
  int v92; // eax
  unsigned int v93; // esi
  HANDLE v94; // rax
  _DWORD *v95; // rsi
  int v96; // r9d
  unsigned int v97; // r11d
  unsigned int v98; // esi
  int v99; // r10d
  int v100; // eax
  void *v101; // rsi
  HANDLE v102; // rax
  void *v103; // rsi
  HANDLE v104; // rax
  HANDLE v105; // rax
  HANDLE v106; // rax
  void *v107; // r12
  size_t v108; // r13
  HANDLE v109; // rax
  _OWORD *v110; // rax
  void *v111; // r15
  HANDLE v112; // rax
  _QWORD *v113; // rax
  _QWORD *v114; // r13
  unsigned int *v115; // r9
  __int64 v116; // r9
  unsigned int v117; // r10d
  unsigned int *v118; // r9
  unsigned int v119; // r11d
  int v120; // r10d
  unsigned int *v121; // r9
  __int64 v122; // r9
  unsigned int v123; // r10d
  int v124; // r11d
  unsigned int *v125; // r9
  int v126; // r10d
  unsigned int *v127; // r9
  size_t v128; // rdx
  __int64 v129; // r9
  unsigned int v130; // r10d
  int v131; // r11d
  _DWORD *v132; // r9
  int v133; // r11d
  unsigned int *v134; // r9
  unsigned int v135; // esi
  __int64 v136; // r9
  unsigned int v137; // r11d
  _DWORD *v138; // r9
  __int64 v139; // r10
  int v140; // r10d
  unsigned int *v141; // r9
  __int64 v142; // r9
  unsigned int v143; // r10d
  int v144; // r11d
  _DWORD *v145; // r9
  int v146; // r10d
  unsigned int *v147; // r9
  __int64 v148; // r9
  unsigned int v149; // r10d
  int v150; // r11d
  _DWORD *v151; // r9
  __int64 v152; // rcx
  unsigned int v153; // r9d
  unsigned int v154; // r9d
  int v155; // r14d
  unsigned int v156; // eax
  unsigned int v157; // esi
  HANDLE v158; // rax
  char *v159; // rax
  char *v160; // rsi
  unsigned int v161; // r9d
  unsigned int v162; // r10d
  size_t v163; // rcx
  HANDLE v164; // rax
  unsigned int *v165; // rsi
  unsigned int *v166; // r13
  unsigned __int8 *v167; // r14
  void *v168; // rdx
  unsigned __int8 v169; // al
  unsigned __int64 v170; // rcx
  unsigned __int64 v171; // r8
  unsigned __int8 *v172; // r11
  int v173; // edx
  int v174; // r10d
  unsigned int v175; // r9d
  unsigned int v176; // edi
  int v177; // r8d
  unsigned int v178; // r9d
  unsigned int v179; // r10d
  unsigned int v180; // ecx
  unsigned int v181; // r11d
  _BYTE *v182; // rdi
  char v183; // bl
  int v184; // r10d
  int v185; // r15d
  _BYTE *v186; // rdi
  SIZE_T v187; // r14
  int v188; // r13d
  unsigned int v189; // eax
  unsigned int v190; // r12d
  int v191; // esi
  int v192; // r11d
  int v193; // edx
  int v194; // r10d
  int v195; // r8d
  int v196; // r10d
  int v197; // r9d
  int v198; // r8d
  unsigned int v199; // edx
  int v200; // r9d
  int v201; // ecx
  int v202; // edx
  int v203; // r8d
  int v204; // r9d
  int v205; // edx
  unsigned int v206; // r8d
  unsigned int v207; // r9d
  int v208; // edx
  int v209; // r8d
  int v210; // r9d
  int v211; // edx
  int v212; // r8d
  int v213; // r10d
  int v214; // edx
  int v215; // r9d
  unsigned int v216; // r8d
  int v217; // edx
  HANDLE v218; // rax
  _DWORD *v219; // rax
  int v220; // r14d
  HANDLE v221; // rax
  void *v222; // rcx
  _DWORD *v223; // r14
  HANDLE v224; // rax
  _OWORD *v225; // rax
  HANDLE v226; // rax
  _QWORD *v227; // rax
  _QWORD *v228; // rax
  HANDLE v229; // rax
  HANDLE v230; // rax
  HANDLE v231; // rax
  HANDLE v232; // rax
  HANDLE v233; // rax
  _QWORD *v234; // rax
  HANDLE v235; // rax
  HANDLE v236; // rax
  HANDLE v237; // rax
  HANDLE v238; // rax
  unsigned int v239; // r9d
  int v240; // r14d
  unsigned int v241; // r9d
  unsigned int v242; // esi
  HANDLE v243; // rax
  _DWORD *v244; // rax
  LPVOID v245; // rax
  HANDLE v246; // rax
  HANDLE v247; // rax
  HANDLE v248; // rax
  HANDLE v249; // rax
  HANDLE v250; // rax
  void *v251; // rsi
  HANDLE v252; // rax
  HANDLE v253; // rax
  _QWORD *v254; // rsi
  void *v255; // r13
  HANDLE v256; // rax
  void *v257; // r13
  HANDLE v258; // rax
  void *v259; // r13
  HANDLE v260; // rax
  HANDLE v261; // rax
  void *v262; // rsi
  HANDLE v263; // rax
  void *v264; // rcx
  void *v265; // r9
  unsigned int v266; // r10d
  void *v267; // rcx
  unsigned int *v268; // r9
  void *v269; // rcx
  unsigned int *v270; // r9
  HANDLE v271; // rax
  int v272; // eax
  __int64 v273; // rcx
  void *v274; // r9
  LPVOID v275; // rcx
  unsigned int v276; // r9d
  int v277; // r11d
  LPVOID v278; // rcx
  unsigned int v279; // esi
  HANDLE v280; // rax
  unsigned int *v281; // rax
  unsigned int v282; // r11d
  int v283; // r9d
  unsigned int v284; // r10d
  unsigned int v285; // r11d
  unsigned int v286; // r11d
  unsigned int v287; // r11d
  unsigned int v288; // r9d
  signed int v289; // eax
  FARPROC ProcAddress; // rax
  int v291; // eax
  unsigned int v292; // r9d
  SIZE_T v293; // rsi
  unsigned int v294; // r10d
  int v295; // r14d
  unsigned int *v296; // rcx
  int v297; // r9d
  int v298; // r9d
  __int64 v299; // r10
  unsigned int v300; // r10d
  int v301; // r9d
  SIZE_T v302; // r11
  unsigned int v303; // r11d
  int v304; // r9d
  unsigned int v305; // r10d
  int v306; // r9d
  unsigned int v307; // r10d
  int v308; // r9d
  int v309; // r10d
  int v310; // r11d
  HANDLE v311; // rax
  _DWORD *v312; // rcx
  HANDLE v313; // rax
  void *v314; // rcx
  HANDLE v315; // rax
  void *v316; // rcx
  void *v317; // rax
  unsigned __int64 v318; // rax
  unsigned int v319; // r14d
  HANDLE v320; // rax
  void *v321; // rcx
  _QWORD *v322; // rax
  HANDLE v323; // rax
  HANDLE v324; // rax
  HANDLE v325; // rax
  HANDLE v326; // rax
  unsigned int *v327; // rdx
  HANDLE v328; // rax
  HANDLE v329; // rax
  HANDLE v330; // rax
  HANDLE v331; // rax
  unsigned __int64 v332; // r14
  void *v333; // r11
  unsigned __int8 v334; // al
  unsigned int v335; // r9d
  unsigned int v336; // r10d
  unsigned __int8 *v337; // rbx
  unsigned int v338; // edi
  int v339; // eax
  int v340; // r8d
  unsigned int v341; // r8d
  unsigned int v342; // r10d
  int v343; // ecx
  int v344; // edx
  unsigned int v345; // esi
  _BYTE *v346; // rdi
  char v347; // bl
  int v348; // r10d
  int v349; // r11d
  unsigned int v350; // r9d
  unsigned __int8 *v351; // rbx
  _BYTE *v352; // rax
  SIZE_T v353; // r13
  unsigned int v354; // r12d
  int v355; // r15d
  int v356; // r14d
  int v357; // esi
  int v358; // edx
  int v359; // r8d
  int v360; // r9d
  unsigned int v361; // edx
  int v362; // r8d
  int v363; // r9d
  unsigned int v364; // edx
  int v365; // r8d
  int v366; // r10d
  int v367; // r11d
  unsigned int v368; // r9d
  int v369; // r8d
  unsigned int v370; // r9d
  int v371; // r10d
  int v372; // r11d
  int v373; // edx
  int v374; // r8d
  int v375; // r9d
  int v376; // edx
  int v377; // r10d
  int v378; // r8d
  unsigned int v379; // edx
  int v380; // r10d
  unsigned __int64 i; // rcx
  int v382; // r14d
  void *v383; // r9
  void *v384; // r10
  unsigned int *v385; // r11
  size_t v386; // r8
  void *v387; // rcx
  void *v388; // r11
  void *v389; // r10
  void *v390; // r9
  LPVOID v391; // rax
  void *v392; // r9
  void *v393; // r10
  void *v394; // r11
  LPVOID v395; // rcx
  void *v396; // rcx
  HANDLE v397; // rax
  unsigned int v398; // eax
  size_t v399; // rcx
  _DWORD *v400; // r9
  int v401; // r10d
  int *v402; // r14
  int v403; // esi
  unsigned int v404; // r11d
  int v405; // r10d
  void *v406; // r9
  int v407; // r10d
  LPVOID *v408; // rdx
  size_t v409; // rcx
  unsigned int v410; // r11d
  int v411; // r10d
  void *v412; // r9
  int v413; // r10d
  unsigned int *v414; // rdx
  size_t v415; // rcx
  unsigned int v416; // r11d
  int v417; // r10d
  size_t v418; // r9
  int v419; // r11d
  const void *v420; // rsi
  unsigned int *v421; // rcx
  unsigned int v422; // r13d
  int v423; // r10d
  void *v424; // r9
  int v425; // r10d
  unsigned int *v426; // rdx
  size_t v427; // rcx
  unsigned int v428; // r13d
  unsigned int v429; // r9d
  int v430; // r10d
  int v431; // r9d
  unsigned int v432; // r10d
  size_t v433; // r11
  int *v434; // rax
  size_t v435; // rcx
  unsigned int v436; // r11d
  int v437; // eax
  unsigned int v438; // r11d
  int v439; // r9d
  int v440; // eax
  unsigned int v441; // r11d
  int v442; // r9d
  int v443; // eax
  int v444; // r9d
  unsigned int v445; // esi
  HANDLE v446; // rax
  _DWORD *v447; // rax
  _DWORD *v448; // rsi
  void *v449; // rsi
  HANDLE v450; // rax
  HANDLE v451; // rax
  HANDLE v452; // rax
  HANDLE v453; // rax
  int v454; // r9d
  size_t v455; // r10
  unsigned int v456; // r11d
  unsigned int v457; // esi
  int v458; // r10d
  unsigned int *v459; // r9
  unsigned int v460; // r11d
  unsigned int v461; // r13d
  __int64 v462; // r9
  unsigned int v463; // r10d
  unsigned int *v464; // r9
  unsigned int v465; // r11d
  int v466; // r10d
  unsigned int *v467; // r9
  unsigned int v468; // r11d
  __int64 v469; // r9
  unsigned int v470; // r10d
  int v471; // r11d
  unsigned int *v472; // r9
  int v473; // r10d
  unsigned int *v474; // r9
  unsigned int v475; // r11d
  __int64 v476; // r9
  unsigned int v477; // r10d
  int v478; // r11d
  _DWORD *v479; // r9
  __int64 v480; // rcx
  unsigned int v481; // r9d
  unsigned int v482; // r13d
  int v483; // ecx
  LPVOID v484; // r9
  unsigned int v485; // r10d
  unsigned int v486; // eax
  unsigned int v487; // esi
  HANDLE v488; // rax
  char *v489; // rax
  char *v490; // rsi
  unsigned int v491; // r9d
  size_t v492; // rcx
  HANDLE v493; // rax
  unsigned int *v494; // rsi
  unsigned int *v495; // r13
  int v496; // ecx
  void *v497; // r8
  unsigned __int8 v498; // al
  SIZE_T v499; // rcx
  SIZE_T v500; // r11
  unsigned int v501; // r8d
  unsigned int v502; // r10d
  unsigned __int8 *v503; // rdi
  int v504; // ebx
  int v505; // esi
  int v506; // r9d
  unsigned int v507; // r10d
  unsigned int v508; // r9d
  int v509; // ecx
  int v510; // edx
  _BYTE *v511; // rbx
  char v512; // di
  unsigned int v513; // r9d
  int v514; // r8d
  unsigned __int8 *v515; // rdi
  _BYTE *v516; // r13
  SIZE_T v517; // rax
  int v518; // r12d
  int v519; // r15d
  int v520; // r14d
  int v521; // esi
  int v522; // r11d
  int v523; // edx
  int v524; // r9d
  int v525; // r10d
  int v526; // r8d
  int v527; // r9d
  unsigned int v528; // edx
  int v529; // r8d
  int v530; // ecx
  int v531; // edx
  int v532; // r9d
  int v533; // edx
  unsigned int v534; // r8d
  unsigned int v535; // r9d
  int v536; // edx
  int v537; // r8d
  int v538; // r9d
  int v539; // edx
  int v540; // r8d
  int v541; // r9d
  int v542; // edx
  int v543; // r8d
  unsigned int v544; // r9d
  int v545; // edx
  HANDLE v546; // rax
  _DWORD *v547; // rax
  void *v548; // rbx
  unsigned int v549; // ebx
  HANDLE v550; // rax
  void *v551; // rcx
  HANDLE v552; // rax
  _OWORD *v553; // rcx
  _DWORD *v554; // rax
  HANDLE v555; // rax
  _QWORD *v556; // rax
  _QWORD *v557; // rax
  HANDLE v558; // rax
  HANDLE v559; // rax
  HANDLE v560; // rax
  HANDLE v561; // rax
  void *v562; // rcx
  HANDLE v563; // rax
  _QWORD *v564; // rax
  HANDLE v565; // rax
  HANDLE v566; // rax
  HANDLE v567; // rax
  HANDLE v568; // rax
  unsigned int v569; // r9d
  unsigned int v570; // r9d
  unsigned int v571; // ebx
  HANDLE v572; // rax
  _DWORD *v573; // rax
  void *v574; // rdi
  void *v575; // rcx
  unsigned int v576; // r9d
  LPVOID v577; // rcx
  unsigned int *v578; // r9
  LPVOID v579; // rcx
  unsigned int *v580; // r9
  int v581; // eax
  HANDLE v582; // rax
  int v583; // eax
  int v584; // eax
  int v585; // r9d
  __int64 v586; // rcx
  size_t v587; // rcx
  unsigned int v588; // r11d
  int v589; // r10d
  unsigned int v590; // ebx
  size_t v591; // rcx
  unsigned int v592; // ebx
  HANDLE v593; // rax
  unsigned int *v594; // rax
  unsigned int v595; // r11d
  int v596; // r10d
  int v597; // r9d
  unsigned int v598; // r11d
  unsigned int v599; // r11d
  unsigned int v600; // r11d
  unsigned int v601; // r10d
  bool v602; // sf
  FARPROC v603; // rax
  unsigned int v604; // r9d
  SIZE_T v605; // rbx
  int v606; // ecx
  unsigned int v607; // r10d
  int v608; // r9d
  int v609; // r9d
  __int64 v610; // r10
  unsigned int v611; // r10d
  int v612; // r9d
  size_t v613; // r11
  unsigned int v614; // r11d
  int v615; // r9d
  unsigned int v616; // r10d
  int v617; // r9d
  unsigned int v618; // r10d
  int v619; // r9d
  int v620; // r10d
  int v621; // r11d
  HANDLE v622; // rax
  _QWORD *v623; // rax
  _DWORD *v624; // rcx
  HANDLE v625; // rax
  void *v626; // rcx
  _QWORD *v627; // rax
  HANDLE v628; // rax
  void *v629; // rcx
  SIZE_T v630; // rax
  HANDLE v631; // rax
  void *v632; // rcx
  HANDLE v633; // rax
  HANDLE v634; // rax
  HANDLE v635; // rax
  HANDLE v636; // rax
  unsigned int *v637; // rdx
  unsigned int *v638; // rax
  HANDLE v639; // rax
  HANDLE v640; // rax
  HANDLE v641; // rax
  HANDLE v642; // rax
  void *v643; // r10
  unsigned __int8 v644; // al
  unsigned __int8 *v645; // r9
  size_t v646; // r11
  int v647; // edi
  int v648; // r11d
  unsigned int v649; // eax
  unsigned int v650; // edx
  _BYTE *v651; // rcx
  unsigned int v652; // r8d
  unsigned int v653; // r9d
  int v654; // ebx
  int v655; // edi
  unsigned int v656; // eax
  char v657; // r10
  int v658; // r9d
  SIZE_T v659; // rcx
  int v660; // r14d
  int v661; // r10d
  int v662; // r11d
  unsigned __int8 *v663; // rax
  _BYTE *v664; // r13
  int v665; // r12d
  int v666; // esi
  int v667; // ebx
  int v668; // edx
  unsigned int v669; // r8d
  int v670; // r9d
  unsigned int v671; // edx
  int v672; // r8d
  int v673; // r9d
  unsigned int v674; // edx
  int v675; // r8d
  int v676; // r10d
  int v677; // r11d
  unsigned int v678; // r9d
  int v679; // r8d
  unsigned int v680; // r9d
  int v681; // edx
  int v682; // r8d
  int v683; // r9d
  int v684; // edx
  unsigned int v685; // r8d
  int v686; // r9d
  int v687; // edx
  int v688; // r8d
  unsigned int v689; // r9d
  int v690; // edx
  size_t j; // rcx
  void *v692; // r9
  void *v693; // rdi
  int v694; // ecx
  unsigned int *v695; // r10
  int v696; // r11d
  __int64 v697; // rbx
  int v698; // r11d
  unsigned int v699; // r11d
  __int64 v700; // r8
  unsigned int *v701; // r11
  void *v702; // r10
  unsigned int *v703; // rbx
  LPVOID v704; // rax
  void *v705; // r15
  unsigned int *v706; // r12
  void *v707; // r13
  void *v708; // rcx
  unsigned int v709; // edx
  HANDLE v710; // rax
  int v711; // eax
  HANDLE v712; // rax
  void *v713; // rbx
  HANDLE v714; // rax
  void *v715; // rbx
  HANDLE v716; // rax
  void *v717; // rbx
  HANDLE v718; // rax
  HANDLE v719; // rax
  void *v720; // rbx
  HANDLE v721; // rax
  HANDLE v722; // rax
  _QWORD *v723; // rbx
  void *v724; // rsi
  HANDLE v725; // rax
  void *v726; // rsi
  HANDLE v727; // rax
  void *v728; // rsi
  HANDLE v729; // rax
  HANDLE v730; // rax
  HANDLE v731; // rax
  unsigned int v732; // r9d
  __int64 v733; // r11
  int *v734; // rcx
  size_t v735; // rcx
  unsigned int v736; // r10d
  int v737; // r9d
  int v738; // ebx
  int v739; // ecx
  int v740; // r9d
  int IsAdminSession; // eax
  int v742; // ecx
  int v743; // r8d
  int v744; // r9d
  int v745; // edx
  int v746; // eax
  int *v747; // rcx
  _DWORD *v748; // r8
  int v749; // ecx
  int v750; // r9d
  int v751; // ecx
  int v752; // r8d
  int v753; // r9d
  int v754; // ecx
  int v755; // r8d
  int v756; // r9d
  __int64 v757; // rdx
  _BYTE *v758; // rax
  unsigned int v760; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v761; // [rsp+54h] [rbp-ACh] BYREF
  unsigned int dwBytes; // [rsp+58h] [rbp-A8h] BYREF
  unsigned int dwBytes_4; // [rsp+5Ch] [rbp-A4h] BYREF
  size_t v764; // [rsp+60h] [rbp-A0h] BYREF
  LPVOID v765; // [rsp+68h] [rbp-98h]
  unsigned int v766; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int8 v767; // [rsp+74h] [rbp-8Ch]
  int v768; // [rsp+78h] [rbp-88h] BYREF
  int v769; // [rsp+7Ch] [rbp-84h]
  LPVOID v770; // [rsp+80h] [rbp-80h]
  unsigned int *v771; // [rsp+88h] [rbp-78h]
  SIZE_T v772; // [rsp+90h] [rbp-70h]
  LPVOID v773; // [rsp+98h] [rbp-68h]
  LPVOID v774; // [rsp+A0h] [rbp-60h] BYREF
  LPVOID v775; // [rsp+A8h] [rbp-58h]
  void *v776; // [rsp+B0h] [rbp-50h] BYREF
  LPVOID v777; // [rsp+B8h] [rbp-48h] BYREF
  LPVOID v778; // [rsp+C0h] [rbp-40h]
  _DWORD *v779; // [rsp+C8h] [rbp-38h] BYREF
  LPVOID v780; // [rsp+D0h] [rbp-30h]
  LPVOID v781; // [rsp+D8h] [rbp-28h] BYREF
  SIZE_T v782; // [rsp+E0h] [rbp-20h] BYREF
  unsigned int v783; // [rsp+E8h] [rbp-18h]
  LPVOID lpMem[2]; // [rsp+F0h] [rbp-10h] BYREF
  size_t pcchLength; // [rsp+100h] [rbp+0h] BYREF
  unsigned int v786; // [rsp+108h] [rbp+8h] BYREF
  void *Src; // [rsp+110h] [rbp+10h]
  void *v788; // [rsp+118h] [rbp+18h] BYREF
  size_t v789[2]; // [rsp+120h] [rbp+20h] BYREF
  SIZE_T v790; // [rsp+130h] [rbp+30h] BYREF
  void *v791; // [rsp+138h] [rbp+38h] BYREF
  SIZE_T Size; // [rsp+140h] [rbp+40h]
  __int16 v793; // [rsp+148h] [rbp+48h] BYREF
  void *v794; // [rsp+150h] [rbp+50h]
  SIZE_T v795; // [rsp+158h] [rbp+58h]
  unsigned int v796; // [rsp+160h] [rbp+60h] BYREF
  unsigned int v797; // [rsp+164h] [rbp+64h] BYREF
  unsigned __int8 *v798; // [rsp+168h] [rbp+68h]
  BYTE Data[4]; // [rsp+170h] [rbp+70h] BYREF
  HKEY hKey; // [rsp+178h] [rbp+78h] BYREF
  void *v801; // [rsp+180h] [rbp+80h] BYREF
  unsigned int v802; // [rsp+188h] [rbp+88h] BYREF
  unsigned int v803; // [rsp+18Ch] [rbp+8Ch] BYREF
  unsigned __int8 *v804; // [rsp+190h] [rbp+90h]
  int v805; // [rsp+198h] [rbp+98h] BYREF
  int v806; // [rsp+19Ch] [rbp+9Ch] BYREF
  int v807; // [rsp+1A0h] [rbp+A0h] BYREF
  int v808; // [rsp+1A4h] [rbp+A4h] BYREF
  unsigned int v809; // [rsp+1A8h] [rbp+A8h]
  int v810; // [rsp+1ACh] [rbp+ACh]
  unsigned int v811; // [rsp+1B0h] [rbp+B0h] BYREF
  int v812; // [rsp+1B4h] [rbp+B4h]
  unsigned int v813; // [rsp+1B8h] [rbp+B8h] BYREF
  DWORD Type; // [rsp+1BCh] [rbp+BCh] BYREF
  DWORD cbData; // [rsp+1C0h] [rbp+C0h] BYREF
  unsigned __int8 *v816; // [rsp+1C8h] [rbp+C8h]
  CRemoteTerminal *v817; // [rsp+1D0h] [rbp+D0h]
  struct IUserConfig *v818; // [rsp+1D8h] [rbp+D8h] BYREF
  void *TickCount64; // [rsp+1E0h] [rbp+E0h]
  signed int v820; // [rsp+1E8h] [rbp+E8h] BYREF
  int v821; // [rsp+1ECh] [rbp+ECh] BYREF
  signed int v822; // [rsp+1F0h] [rbp+F0h] BYREF
  signed int v823; // [rsp+1F4h] [rbp+F4h] BYREF
  signed int v824; // [rsp+1F8h] [rbp+F8h] BYREF
  signed int v825; // [rsp+1FCh] [rbp+FCh] BYREF
  signed int v826; // [rsp+200h] [rbp+100h] BYREF
  signed int v827; // [rsp+204h] [rbp+104h] BYREF
  signed int v828; // [rsp+208h] [rbp+108h] BYREF
  int v829; // [rsp+20Ch] [rbp+10Ch] BYREF
  signed int v830; // [rsp+210h] [rbp+110h] BYREF
  int v831; // [rsp+214h] [rbp+114h] BYREF
  signed int v832; // [rsp+218h] [rbp+118h] BYREF
  signed int v833; // [rsp+21Ch] [rbp+11Ch] BYREF
  signed int v834; // [rsp+220h] [rbp+120h] BYREF
  signed int v835; // [rsp+224h] [rbp+124h] BYREF
  signed int v836; // [rsp+228h] [rbp+128h] BYREF
  int *v837; // [rsp+230h] [rbp+130h] BYREF
  struct IUserName *v838; // [rsp+238h] [rbp+138h]
  LPWSTR StringSid; // [rsp+240h] [rbp+140h] BYREF
  PSID Sid; // [rsp+248h] [rbp+148h] BYREF
  LSTATUS v841; // [rsp+250h] [rbp+150h] BYREF
  LSTATUS v842; // [rsp+258h] [rbp+158h] BYREF
  signed int v843; // [rsp+25Ch] [rbp+15Ch] BYREF
  int v844; // [rsp+260h] [rbp+160h] BYREF
  HMODULE phModule; // [rsp+268h] [rbp+168h] BYREF
  HMODULE hModule; // [rsp+278h] [rbp+178h] BYREF
  __int128 v847; // [rsp+280h] [rbp+180h] BYREF
  __int128 v848; // [rsp+290h] [rbp+190h]
  __int128 v849; // [rsp+2A0h] [rbp+1A0h] BYREF
  __int128 v850; // [rsp+2B0h] [rbp+1B0h]
  const char *v851; // [rsp+2C0h] [rbp+1C0h] BYREF
  const char *v852; // [rsp+2C8h] [rbp+1C8h] BYREF
  const char *v853; // [rsp+2D0h] [rbp+1D0h] BYREF
  const char *v854; // [rsp+2D8h] [rbp+1D8h] BYREF
  const char *v855; // [rsp+2E0h] [rbp+1E0h] BYREF
  const char *v856; // [rsp+2E8h] [rbp+1E8h] BYREF
  const char *v857; // [rsp+2F0h] [rbp+1F0h] BYREF
  const char *v858; // [rsp+2F8h] [rbp+1F8h] BYREF
  const char *v859; // [rsp+300h] [rbp+200h] BYREF
  const char *v860; // [rsp+308h] [rbp+208h] BYREF
  const WCHAR *v861; // [rsp+310h] [rbp+210h] BYREF
  const char *v862; // [rsp+318h] [rbp+218h] BYREF
  __int64 v863; // [rsp+320h] [rbp+220h] BYREF
  const WCHAR *v864; // [rsp+328h] [rbp+228h] BYREF
  const char *v865; // [rsp+330h] [rbp+230h] BYREF
  WCHAR *v866; // [rsp+338h] [rbp+238h] BYREF
  const char *v867; // [rsp+340h] [rbp+240h] BYREF
  __int64 v868; // [rsp+348h] [rbp+248h] BYREF
  WCHAR *v869; // [rsp+350h] [rbp+250h] BYREF
  const char *v870; // [rsp+358h] [rbp+258h] BYREF
  const char *v871; // [rsp+360h] [rbp+260h] BYREF
  const char *v872; // [rsp+368h] [rbp+268h] BYREF
  const char *v873; // [rsp+370h] [rbp+270h] BYREF
  const char *v874; // [rsp+378h] [rbp+278h] BYREF
  const char *v875; // [rsp+380h] [rbp+280h] BYREF
  const char *v876; // [rsp+388h] [rbp+288h] BYREF
  const char *v877; // [rsp+390h] [rbp+290h] BYREF
  const char *v878; // [rsp+398h] [rbp+298h] BYREF
  const char *v879; // [rsp+3A0h] [rbp+2A0h] BYREF
  const char *v880; // [rsp+3A8h] [rbp+2A8h] BYREF
  const char *v881; // [rsp+3B0h] [rbp+2B0h] BYREF
  const char *v882; // [rsp+3B8h] [rbp+2B8h] BYREF
  const char *v883; // [rsp+3C0h] [rbp+2C0h] BYREF
  const char *v884; // [rsp+3C8h] [rbp+2C8h] BYREF
  const char *v885; // [rsp+3D0h] [rbp+2D0h] BYREF
  const char *v886; // [rsp+3D8h] [rbp+2D8h] BYREF
  const char *v887; // [rsp+3E0h] [rbp+2E0h] BYREF
  ULONGLONG v888; // [rsp+3E8h] [rbp+2E8h] BYREF
  const char *v889; // [rsp+3F0h] [rbp+2F0h] BYREF
  const char *v890; // [rsp+3F8h] [rbp+2F8h] BYREF
  const char *v891; // [rsp+400h] [rbp+300h] BYREF
  const char *v892; // [rsp+408h] [rbp+308h] BYREF
  const char *v893; // [rsp+410h] [rbp+310h] BYREF
  const char *v894; // [rsp+418h] [rbp+318h] BYREF
  const char *v895; // [rsp+420h] [rbp+320h] BYREF
  const char *v896; // [rsp+428h] [rbp+328h] BYREF
  const char *v897; // [rsp+430h] [rbp+330h] BYREF
  const char *v898; // [rsp+438h] [rbp+338h] BYREF
  const char *v899; // [rsp+440h] [rbp+340h] BYREF
  const char *v900; // [rsp+448h] [rbp+348h] BYREF
  const char *v901; // [rsp+450h] [rbp+350h] BYREF
  const char *v902; // [rsp+460h] [rbp+360h] BYREF
  const char *v903; // [rsp+468h] [rbp+368h] BYREF
  const char *v904; // [rsp+470h] [rbp+370h] BYREF
  const char *v905; // [rsp+478h] [rbp+378h] BYREF
  const char *v906; // [rsp+480h] [rbp+380h] BYREF
  const char *v907; // [rsp+488h] [rbp+388h] BYREF
  const char *v908; // [rsp+490h] [rbp+390h] BYREF
  const char *v909; // [rsp+498h] [rbp+398h] BYREF
  const char *v910; // [rsp+4A0h] [rbp+3A0h] BYREF
  const char *v911; // [rsp+4A8h] [rbp+3A8h] BYREF
  const char *v912; // [rsp+4B0h] [rbp+3B0h] BYREF
  __int64 v913; // [rsp+4C0h] [rbp+3C0h] BYREF
  const char *v914; // [rsp+4C8h] [rbp+3C8h] BYREF
  const char *v915; // [rsp+4D0h] [rbp+3D0h] BYREF
  struct _GUID v916; // [rsp+528h] [rbp+428h] BYREF
  __int128 Buf1; // [rsp+538h] [rbp+438h] BYREF
  struct _GUID v918; // [rsp+548h] [rbp+448h] BYREF
  _BYTE v919[16]; // [rsp+558h] [rbp+458h] BYREF
  int v920; // [rsp+568h] [rbp+468h]
  _BYTE v921[80]; // [rsp+570h] [rbp+470h] BYREF
  WCHAR SubKey[264]; // [rsp+5C0h] [rbp+4C0h] BYREF

  v838 = a2;
  v817 = this;
  v5 = 0;
  v6 = 0;
  v7 = 0;
  v816 = 0;
  StringSid = 0;
  Sid = 0;
  v918 = 0;
  v808 = 1;
  v806 = 0;
  v805 = 0;
  v818 = 0;
  v793 = 0;
  v807 = 0;
  Buf1 = 0;
  hKey = 0;
  Type = 0;
  *(_DWORD *)Data = 0;
  cbData = 4;
  memset_0(SubKey, 0, 0x208u);
  v916 = 0;
  CAutoSetActivityId::CAutoSetActivityId((CAutoSetActivityId *)v919, &v916);
  if ( (unsigned int)dword_18012E170 > 4 )
  {
    v913 = *((int *)this + 420);
    v914 = "RemoteTerminal->UpdateConfig()";
    v915 = "CRemoteTerminal::UpdateConfig";
    v851 = "Group Policy";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<8>>(
      (unsigned int)"Group Policy",
      (unsigned int)qword_18010E8F0,
      v8,
      v9,
      (__int64)&v851,
      (__int64)&v915,
      (__int64)&v914,
      (__int64)&v913);
  }
  TickCount64 = (void *)GetTickCount64();
  if ( !*((_QWORD *)this + 200) )
  {
    ConfigData = -2147022646;
    if ( (unsigned int)dword_18012E170 > 3 )
    {
      v852 = "UpdateConfig";
      v829 = -2147022646;
      v853 = "check for presence of connection object";
      v854 = "Warning HResult failed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        v10,
        (unsigned int)byte_18010E8B5,
        v11,
        v12,
        (__int64)&v854,
        (__int64)&v853,
        (__int64)&v829,
        (__int64)&v852);
    }
    goto LABEL_991;
  }
  CRemoteTerminal::GetActivityId(this, &v916);
  if ( v920 >= 0 )
    EtwEventActivityIdControl(2, &v916);
  ConfigData = (*(__int64 (__fastcall **)(_QWORD, __int128 *))(**((_QWORD **)this + 200) + 336LL))(
                 *((_QWORD *)this + 200),
                 &Buf1);
  if ( ConfigData < 0 )
  {
    if ( (unsigned int)dword_18012E170 > 3 )
    {
      v855 = "UpdateConfig";
      v835 = ConfigData;
      v856 = "ptrConnection->GetConnectionGUID";
      v857 = "Warning HResult failed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        v14,
        (unsigned int)word_18010E87A,
        v11,
        v15,
        (__int64)&v857,
        (__int64)&v856,
        (__int64)&v835,
        (__int64)&v855);
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
  v16 = (unsigned __int8 *)operator new[](0x1E40u, (const struct std::nothrow_t *)std::nothrow);
  v7 = v16;
  v804 = v16;
  v6 = v16;
  v798 = v16;
  if ( !v16 )
  {
    ConfigData = -2147024882;
    v7 = v816;
    goto LABEL_991;
  }
  memset_0(v16, 0, 0x1E40u);
  ConfigData = CRemoteTerminal::GetConfigData(this, v7, 0xA68u);
  if ( ConfigData < 0 )
  {
    if ( (unsigned int)dword_18012E170 > 3 )
    {
      v858 = "UpdateConfig";
      v836 = ConfigData;
      v859 = "Terminal->GetConfigData";
      v860 = "Warning HResult failed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        v17,
        (unsigned int)&byte_18010E83F,
        v11,
        v18,
        (__int64)&v860,
        (__int64)&v859,
        (__int64)&v836,
        (__int64)&v858);
    }
    goto LABEL_991;
  }
  v19 = v7 + 2672;
  if ( (*(int (__fastcall **)(_QWORD, _BYTE *))(**((_QWORD **)this + 200) + 64LL))(*((_QWORD *)this + 200), v921) >= 0 )
  {
    if ( RegOpenKeyExW(
           HKEY_LOCAL_MACHINE,
           L"Software\\Policies\\Microsoft\\Windows NT\\Terminal Services",
           0,
           0x20019u,
           &hKey) )
    {
      if ( (unsigned int)dword_18012E170 > 4 )
      {
        v861 = L"Software\\Policies\\Microsoft\\Windows NT\\Terminal Services";
        v862 = "Could not open policy reg-key for QueryLocalUserCfg";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
          v20,
          (unsigned int)word_18010E80A,
          v21,
          v22,
          (__int64)&v862,
          (__int64)&v861);
      }
    }
    else
    {
      v23 = RegQueryValueExW(hKey, L"fQueryUserConfigFromDC", 0, &Type, Data, &cbData);
      v26 = v23;
      if ( (unsigned int)dword_18012E170 > 5 )
      {
        v863 = *(unsigned int *)Data;
        v841 = v23;
        v864 = L"Software\\Policies\\Microsoft\\Windows NT\\Terminal Services";
        v865 = "Policy reg-key value for QueryLocalUserCfg";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
          *(_DWORD *)Data,
          (unsigned int)&byte_18010E7B7,
          v24,
          v25,
          (__int64)&v865,
          (__int64)&v864,
          (__int64)&v841,
          (__int64)&v863);
      }
      RegCloseKey(hKey);
      hKey = 0;
      RegCloseKey(0);
      hKey = 0;
      if ( !v26 )
        goto LABEL_34;
    }
  }
  StringCchPrintfW(SubKey, 0x104u, L"%s\\%s", L"System\\CurrentControlSet\\Control\\Terminal Server\\WinStations", v921);
  if ( RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0x20019u, &hKey) )
  {
    if ( (unsigned int)dword_18012E170 > 4 )
    {
      v866 = SubKey;
      v867 = "Could not open Winsta reg-key for QueryLocalUserCfg";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
        v27,
        (unsigned int)&byte_18010E787,
        v28,
        v29,
        (__int64)&v867,
        (__int64)&v866);
    }
  }
  else
  {
    v30 = RegQueryValueExW(hKey, L"fQueryUserConfigFromDC", 0, &Type, Data, &cbData);
    if ( (unsigned int)dword_18012E170 > 5 )
    {
      v868 = *(unsigned int *)Data;
      v842 = v30;
      v869 = SubKey;
      v870 = "Winstation reg-key value for QueryLocalUserCfg";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
        *(_DWORD *)Data,
        (unsigned int)byte_18010E739,
        v31,
        v32,
        (__int64)&v870,
        (__int64)&v869,
        (__int64)&v842,
        (__int64)&v868);
    }
    RegCloseKey(hKey);
    hKey = 0;
  }
LABEL_34:
  if ( (a3 & 2) != 0 )
  {
    ConfigData = IUserConfig::GetInstanceOfUserConfig(&v818);
    if ( ConfigData < 0 )
    {
      if ( (unsigned int)dword_18012E170 > 3 )
      {
        v871 = "UpdateConfig";
        v843 = ConfigData;
        v872 = "IUserConfig::GetInstanceOfUserConfig";
        v873 = "Warning HResult failed";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
          v33,
          (unsigned int)&word_18010E6FE,
          v11,
          v34,
          (__int64)&v873,
          (__int64)&v872,
          (__int64)&v843,
          (__int64)&v871);
      }
LABEL_38:
      v6 = v7;
      goto LABEL_991;
    }
    ConfigData = CRemoteTerminal::GetLicenseType(this, &v918);
    if ( ConfigData < 0 )
    {
      if ( (unsigned int)dword_18012E170 > 3 )
      {
        v874 = "UpdateConfig";
        v828 = ConfigData;
        v875 = "GetLicenseType";
        v876 = "Warning HResult failed";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
          v35,
          (unsigned int)byte_18010E6C3,
          v11,
          v36,
          (__int64)&v876,
          (__int64)&v875,
          (__int64)&v828,
          (__int64)&v874);
      }
      goto LABEL_38;
    }
    if ( *(_DWORD *)Data == 1 )
    {
      v37 = CrimsonHelper::RaiseEvent<unsigned short const *>(
              &CrimsonHelper::s_instance,
              EVENT_TS_DC_QUERY_USER_CONFIG,
              v921);
      if ( v37 < 0 && (unsigned int)dword_18012E170 > 2 )
      {
        v844 = v37;
        v877 = "TS_RAISE_EVENT_1 failed with error";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
          dword_18012E170,
          (unsigned int)byte_18010E69D,
          v38,
          v39,
          (__int64)&v877,
          (__int64)&v844);
      }
      v40 = v818;
      ConfigData = (*(__int64 (__fastcall **)(struct IUserConfig *, struct IUserName *, struct _GUID *))(*(_QWORD *)v818 + 40LL))(
                     v818,
                     v838,
                     &v918);
      if ( ConfigData < 0 )
      {
        if ( (unsigned int)dword_18012E170 > 3 )
        {
          v878 = "UpdateConfig";
          v820 = ConfigData;
          v879 = "ptrUserConfig->UpdateConfig";
          v880 = "Warning HResult failed";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
            v41,
            (unsigned int)word_18010E662,
            v11,
            v42,
            (__int64)&v880,
            (__int64)&v879,
            (__int64)&v820,
            (__int64)&v878);
        }
        goto LABEL_38;
      }
    }
    else
    {
      v43 = CrimsonHelper::RaiseEvent<unsigned short const *>(
              &CrimsonHelper::s_instance,
              EVENT_TS_LM_QUERY_USER_CONFIG,
              v921);
      if ( v43 < 0 && (unsigned int)dword_18012E170 > 2 )
      {
        v821 = v43;
        v881 = "TS_RAISE_EVENT_1 failed with error";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
          dword_18012E170,
          (unsigned int)&dword_18010E63C,
          v44,
          v45,
          (__int64)&v881,
          (__int64)&v821);
      }
      v40 = v818;
      ConfigData = (*(__int64 (__fastcall **)(struct IUserConfig *))(*(_QWORD *)v818 + 48LL))(v818);
      if ( ConfigData < 0 )
      {
        if ( (unsigned int)dword_18012E170 > 3 )
        {
          v882 = "UpdateConfig";
          v822 = ConfigData;
          v883 = "ptrUserConfig->UpdateConfigFromLocal";
          v884 = "Warning HResult failed";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
            v46,
            (unsigned int)byte_18010E601,
            v11,
            v47,
            (__int64)&v884,
            (__int64)&v883,
            (__int64)&v822,
            (__int64)&v882);
        }
        goto LABEL_38;
      }
    }
    v5 = v7 + 5208;
    ConfigData = (*(__int64 (__fastcall **)(struct IUserConfig *, unsigned __int8 *))(*(_QWORD *)v40 + 32LL))(
                   v40,
                   v7 + 5208);
    if ( ConfigData < 0 )
    {
      if ( (unsigned int)dword_18012E170 > 3 )
      {
        v885 = "UpdateConfig";
        v823 = ConfigData;
        v886 = "ptrUserConfig->GetConfig";
        v887 = "Warning HResult failed";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
          v48,
          (unsigned int)&word_18010E5C6,
          v11,
          v49,
          (__int64)&v887,
          (__int64)&v886,
          (__int64)&v823,
          (__int64)&v885);
      }
      goto LABEL_58;
    }
  }
  v50 = 0;
  v51 = 0;
  v52 = GetTickCount64();
  if ( (unsigned int)dword_18012E170 > 4 )
  {
    v888 = v52 - (_QWORD)TickCount64;
    v889 = "UpdateConfig to get TSUserEX info";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(
      dword_18012E170,
      (unsigned int)&byte_18010E597,
      v53,
      v54,
      (__int64)&v889,
      (__int64)&v888);
  }
  if ( (a3 & 1) != 0 )
  {
    v55 = v838;
    ConfigData = (*(__int64 (__fastcall **)(struct IUserName *, PSID *))(*(_QWORD *)v838 + 72LL))(v838, &Sid);
    if ( ConfigData < 0 )
    {
      if ( (unsigned int)dword_18012E170 > 3 )
      {
        v890 = "UpdateConfig";
        v824 = ConfigData;
        v891 = "GetUserSid";
        v892 = "Warning HResult failed";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
          v56,
          (unsigned int)&dword_18010E55C,
          v11,
          v57,
          (__int64)&v892,
          (__int64)&v891,
          (__int64)&v824,
          (__int64)&v890);
      }
LABEL_65:
      v7 = v804;
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
      v6 = v804;
      if ( ConfigData >= 0 )
        goto LABEL_995;
      v7 = v804;
LABEL_991:
      if ( (unsigned int)dword_18012E170 > 3 && (unsigned __int8)tlgKeywordOn(&dword_18012E170, 0, v11) )
      {
        v833 = ConfigData;
        v909 = "CRemoteTerminal::UpdateConfig";
        v910 = "Group Policy";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
          v751,
          (unsigned int)byte_18010E3D3,
          v752,
          v753,
          (__int64)&v910,
          (__int64)&v909,
          (__int64)&v833);
      }
      goto LABEL_999;
    }
    ConfigData = CImpersonate::ImpersonateUser((CImpersonate *)&v793, v55);
    if ( ConfigData < 0 )
    {
      if ( (unsigned int)dword_18012E170 > 3 )
      {
        v893 = "UpdateConfig";
        v825 = ConfigData;
        v894 = "Impersonate.ImpersonateUser";
        v895 = "Warning HResult failed";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
          v59,
          (unsigned int)byte_18010E521,
          v11,
          v60,
          (__int64)&v895,
          (__int64)&v894,
          (__int64)&v825,
          (__int64)&v893);
      }
      goto LABEL_65;
    }
    v61 = v804;
    v62 = v804 + 2664;
    UserPolicy = RegGetUserPolicy(StringSid, v804 + 2664, v19);
    *((_BYTE *)v817 + 5368) = UserPolicy;
    if ( UserPolicy )
      v51 = v19;
    v50 = (unsigned __int64)v62 & -(__int64)(UserPolicy != 0);
    ConfigData = CImpersonate::StopImpersonating((CImpersonate *)&v793);
    if ( ConfigData < 0 )
    {
      if ( (unsigned int)dword_18012E170 > 3 )
      {
        v896 = "UpdateConfig";
        v826 = ConfigData;
        v897 = "Impersonate.StopImpersonating";
        v898 = "Warning HResult failed";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
          v64,
          (unsigned int)&word_18010E4E6,
          v11,
          v65,
          (__int64)&v898,
          (__int64)&v897,
          (__int64)&v826,
          (__int64)&v896);
      }
      v7 = v61;
      v6 = v61;
      goto LABEL_991;
    }
  }
  else
  {
    v61 = v804;
  }
  v66 = v817;
  ConfigData = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64, unsigned __int8 *, unsigned __int8 *, unsigned __int8 *, int *, int *))(**((_QWORD **)v817 + 200) + 664LL))(
                 *((_QWORD *)v817 + 200),
                 1,
                 v50,
                 v51,
                 v5,
                 v61 + 124,
                 &v806,
                 &v805);
  if ( ConfigData < 0 )
  {
    if ( (unsigned int)dword_18012E170 > 3 )
    {
      v899 = "UpdateConfig";
      v827 = ConfigData;
      v900 = "this->ptrConnection->MergeUserSettings";
      v901 = "Warning HResult failed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        v67,
        (unsigned int)byte_18010E4AB,
        v11,
        v68,
        (__int64)&v901,
        (__int64)&v900,
        (__int64)&v827,
        (__int64)&v899);
    }
    v7 = v61;
LABEL_990:
    v6 = v798;
    goto LABEL_991;
  }
  v7 = v61;
  v816 = v61;
  v69 = 0;
  v810 = 0;
  v837 = 0;
  v70 = 0;
  LODWORD(v770) = 0;
  v801 = 0;
  v71 = LocalAlloc(0x40u, 4u);
  SP<unsigned char,SP_HLOCAL<unsigned char>>::operator=(&v801, v71);
  TickCount64 = v801;
  if ( !v801 )
  {
    v75 = -2147024882;
    goto LABEL_946;
  }
  v809 = 0;
  v812 = 0;
  *(_OWORD *)lpMem = 0;
  v777 = 0;
  ProcessHeap = GetProcessHeap();
  v73 = HeapAlloc(ProcessHeap, 8u, 0xA0u);
  v74 = v73;
  v769 = -805306345;
  v786 = -1;
  v75 = -1073741801;
  if ( !v73 )
  {
    v76 = 0;
    v760 = -1073741801;
    goto LABEL_119;
  }
  *v73 = `WarbirdUmGetDecryptionCipher'::`2'::DecryptionCipher;
  v73[1] = xmmword_18012E5A0;
  v73[2] = xmmword_18012E5B0;
  v73[3] = xmmword_18012E5C0;
  v73[4] = xmmword_18012E5D0;
  v73[5] = xmmword_18012E5E0;
  v73[6] = xmmword_18012E5F0;
  v73[7] = xmmword_18012E600;
  v73[8] = xmmword_18012E610;
  v73[9] = xmmword_18012E620;
  v77 = GetProcessHeap();
  v78 = HeapAlloc(v77, 8u, 8u);
  v76 = v78;
  if ( !v78 )
  {
    v760 = -1073741801;
    goto LABEL_119;
  }
  *v78 = `WarbirdUmGetDecryptionKey'::`2'::nDecryptionKey;
  v790 = __rdtsc();
  dwBytes = 0;
  v761 = 0;
  v75 = RtlUIntAdd(4, 4, &v761);
  v760 = v75;
  if ( v75 >= 0 )
  {
    v79 = RtlUIntAdd(0, v761, &dwBytes);
    v75 = v79 | 0x10000000;
    v760 = v79 | 0x10000000;
    if ( v79 >= 0 )
    {
      v761 = v80;
      v75 = RtlUIntAdd(v81, 160, &v761);
      v760 = v75;
      if ( v75 >= 0 )
      {
        v82 = RtlUIntAdd(dwBytes, v761, &dwBytes);
        v75 = v82 | 0x10000000;
        v760 = v82 | 0x10000000;
        if ( v82 >= 0 )
        {
          v761 = 0;
          v75 = RtlUIntAdd(v83, 8, &v761);
          v760 = v75;
          if ( v75 >= 0 )
          {
            v84 = RtlUIntAdd(dwBytes, v761, &dwBytes);
            v75 = v84 | 0x10000000;
            v760 = v84 | 0x10000000;
            if ( v84 >= 0 )
            {
              v761 = 0;
              v75 = RtlUIntAdd(v85, 8, &v761);
              v760 = v75;
              if ( v75 >= 0 )
              {
                v86 = RtlUIntAdd(dwBytes, v761, &dwBytes);
                v75 = v86 | 0x10000000;
                v760 = v86 | 0x10000000;
                if ( v86 >= 0 )
                {
                  pcchLength = 0;
                  if ( StringCchLengthW(
                         L"TerminalServices-DeviceRedirection-Licenses-TSEasyPrintAllowed",
                         v87,
                         &pcchLength) < 0 )
                  {
                    v75 = -1073741762;
LABEL_319:
                    v760 = v75;
                    goto LABEL_119;
                  }
                  v761 = 0;
                  v75 = RtlUIntAdd(4, (unsigned int)(2 * (pcchLength + 1)), &v761);
                  v760 = v75;
                  if ( v75 >= 0 )
                  {
                    v88 = RtlUIntAdd(dwBytes, v761, &dwBytes);
                    v75 = v88 | 0x10000000;
                    v760 = v88 | 0x10000000;
                    if ( v88 >= 0 )
                    {
                      v761 = 0;
                      v75 = RtlUIntAdd(v89, v89, &v761);
                      v760 = v75;
                      if ( v75 >= 0 )
                      {
                        v90 = RtlUIntAdd(dwBytes, v761, &dwBytes);
                        v75 = v90 | 0x10000000;
                        v760 = v90 | 0x10000000;
                        if ( v90 >= 0 )
                        {
                          v761 = 0;
                          v75 = RtlUIntAdd(v91, v91, &v761);
                          v760 = v75;
                          if ( v75 >= 0 )
                          {
                            v92 = RtlUIntAdd(dwBytes, v761, &dwBytes);
                            v75 = v92 | 0x10000000;
                            v760 = v92 | 0x10000000;
                            if ( v92 >= 0 )
                            {
                              HIDWORD(lpMem[0]) = dwBytes;
                              v93 = dwBytes;
                              v94 = GetProcessHeap();
                              v95 = HeapAlloc(v94, 8u, v93);
                              if ( !v95 )
                              {
                                v75 = -1073741801;
                                goto LABEL_319;
                              }
                              dwBytes_4 = 0;
                              lpMem[1] = v95;
                              LODWORD(lpMem[0]) = 0;
                              LODWORD(v779) = 0;
                              v778 = 0;
                              v764 = (size_t)v95;
                              v768 = 8;
                              v75 = RtlULongLongAdd(v95, 4, &v779);
                              v760 = v75;
                              if ( v75 >= 0 )
                              {
                                if ( v95 + 2 > (_DWORD *)((char *)lpMem[1] + HIDWORD(lpMem[0])) )
                                {
LABEL_110:
                                  v75 = -1073741789;
LABEL_114:
                                  v760 = v75;
                                  goto LABEL_119;
                                }
                                *v95 = 4;
                                *v779 = v96;
                                v98 = v768;
                                v99 = ++LODWORD(lpMem[0]);
                                LODWORD(v779) = 0;
                                v778 = 0;
                                if ( v74 )
                                {
                                  if ( !v97 )
                                    goto LABEL_113;
                                }
                                else if ( v97 )
                                {
                                  goto LABEL_113;
                                }
                                v115 = (unsigned int *)lpMem[1];
                                if ( lpMem[1] )
                                {
                                  v764 = (size_t)lpMem[1];
                                  v768 = 0;
                                  if ( v99 )
                                  {
                                    do
                                    {
                                      v761 = 0;
                                      v75 = RtlUIntAdd(4, *v115, &v761);
                                      v760 = v75;
                                      if ( v75 < 0 )
                                        goto LABEL_119;
                                      v75 = RtlULongLongAdd(v116, v761, &v764);
                                      v760 = v75;
                                      if ( v75 < 0 )
                                        goto LABEL_119;
                                      ++v768;
                                      v115 = (unsigned int *)v764;
                                    }
                                    while ( v768 < v117 );
                                  }
                                  v75 = RtlULongLongAdd(v115, 4, &v779);
                                  v760 = v75;
                                  if ( v75 < 0 )
                                    goto LABEL_119;
                                  if ( (char *)v118 + v119 + 4 > (char *)lpMem[1] + HIDWORD(lpMem[0]) )
                                    goto LABEL_110;
                                  *v118 = v119;
                                  if ( v74 )
                                    memcpy_0(v779, v74, v119);
                                }
                                else
                                {
                                  v761 = 0;
                                  v75 = RtlUIntAdd(4, v97, &v761);
                                  v760 = v75;
                                  if ( v75 < 0 )
                                    goto LABEL_119;
                                  v75 = RtlUIntAdd(HIDWORD(lpMem[0]), v761, (char *)lpMem + 4);
                                  v760 = v75;
                                  if ( v75 < 0 )
                                    goto LABEL_119;
                                }
                                v120 = ++LODWORD(lpMem[0]);
                                LODWORD(v779) = 0;
                                v778 = 0;
                                if ( v76 )
                                {
                                  if ( !v98 )
                                    goto LABEL_113;
                                }
                                else if ( v98 )
                                {
                                  goto LABEL_113;
                                }
                                v121 = (unsigned int *)lpMem[1];
                                if ( lpMem[1] )
                                {
                                  v764 = (size_t)lpMem[1];
                                  if ( v120 )
                                  {
                                    do
                                    {
                                      v761 = 0;
                                      v75 = RtlUIntAdd(4, *v121, &v761);
                                      v760 = v75;
                                      if ( v75 < 0 )
                                        goto LABEL_119;
                                      v75 = RtlULongLongAdd(v122, v761, &v764);
                                      v760 = v75;
                                      if ( v75 < 0 )
                                        goto LABEL_119;
                                      v121 = (unsigned int *)v764;
                                    }
                                    while ( v124 + 1 < v123 );
                                  }
                                  v75 = RtlULongLongAdd(v121, 4, &v779);
                                  v760 = v75;
                                  if ( v75 < 0 )
                                    goto LABEL_119;
                                  if ( (char *)v125 + v98 + 4 > (char *)lpMem[1] + HIDWORD(lpMem[0]) )
                                    goto LABEL_110;
                                  *v125 = v98;
                                  if ( v76 )
                                    memcpy_0(v779, v76, v98);
                                }
                                else
                                {
                                  v761 = 0;
                                  v75 = RtlUIntAdd(4, v98, &v761);
                                  v760 = v75;
                                  if ( v75 < 0 )
                                    goto LABEL_119;
                                  v75 = RtlUIntAdd(HIDWORD(lpMem[0]), v761, (char *)lpMem + 4);
                                  v760 = v75;
                                  if ( v75 < 0 )
                                    goto LABEL_119;
                                }
                                v126 = ++LODWORD(lpMem[0]);
                                LODWORD(v779) = 0;
                                v778 = 0;
                                v127 = (unsigned int *)lpMem[1];
                                if ( lpMem[1] )
                                {
                                  v764 = (size_t)lpMem[1];
                                  if ( v126 )
                                  {
                                    do
                                    {
                                      v761 = 0;
                                      v75 = RtlUIntAdd(4, *v127, &v761);
                                      v760 = v75;
                                      if ( v75 < 0 )
                                        goto LABEL_119;
                                      v75 = RtlULongLongAdd(v129, v761, &v764);
                                      v760 = v75;
                                      if ( v75 < 0 )
                                        goto LABEL_119;
                                      v127 = (unsigned int *)v764;
                                    }
                                    while ( v131 + 1 < v130 );
                                  }
                                  v75 = RtlULongLongAdd(v127, 4, &v779);
                                  v760 = v75;
                                  if ( v75 < 0 )
                                    goto LABEL_119;
                                  if ( v132 + 3 > (_DWORD *)((char *)lpMem[1] + HIDWORD(lpMem[0])) )
                                    goto LABEL_110;
                                  *v132 = 8;
                                  *(_QWORD *)v779 = v790;
                                }
                                else
                                {
                                  v761 = 0;
                                  v75 = RtlUIntAdd(4, 8, &v761);
                                  v760 = v75;
                                  if ( v75 < 0 )
                                    goto LABEL_119;
                                  v75 = RtlUIntAdd(HIDWORD(lpMem[0]), v761, (char *)lpMem + 4);
                                  v760 = v75;
                                  if ( v75 < 0 )
                                    goto LABEL_119;
                                }
                                ++LODWORD(lpMem[0]);
                                v764 = 0;
                                if ( StringCchLengthW(
                                       L"TerminalServices-DeviceRedirection-Licenses-TSEasyPrintAllowed",
                                       v128,
                                       &v764) < 0 )
                                {
                                  v75 = -1073741762;
                                  goto LABEL_114;
                                }
                                v75 = RtlULongLongAdd(v764, 1, &v764);
                                v760 = v75;
                                if ( v75 >= 0 )
                                {
                                  LODWORD(v779) = 0;
                                  v778 = 0;
                                  if ( !(2 * (_DWORD)v764) )
                                    goto LABEL_113;
                                  v134 = (unsigned int *)lpMem[1];
                                  if ( lpMem[1] )
                                  {
                                    v764 = (size_t)lpMem[1];
                                    v135 = 0;
                                    if ( v133 )
                                    {
                                      do
                                      {
                                        v761 = 0;
                                        v75 = RtlUIntAdd(4, *v134, &v761);
                                        v760 = v75;
                                        if ( v75 < 0 )
                                          goto LABEL_119;
                                        v75 = RtlULongLongAdd(v136, v761, &v764);
                                        v760 = v75;
                                        if ( v75 < 0 )
                                          goto LABEL_119;
                                        ++v135;
                                        v134 = (unsigned int *)v764;
                                      }
                                      while ( v135 < v137 );
                                    }
                                    v75 = RtlULongLongAdd(v134, 4, &v779);
                                    v760 = v75;
                                    if ( v75 < 0 )
                                      goto LABEL_119;
                                    if ( (char *)v138 + v139 + 4 > (char *)lpMem[1] + HIDWORD(lpMem[0]) )
                                      goto LABEL_110;
                                    *v138 = v139;
                                    memcpy_0(
                                      v779,
                                      L"TerminalServices-DeviceRedirection-Licenses-TSEasyPrintAllowed",
                                      (unsigned int)v139);
                                  }
                                  else
                                  {
                                    v761 = 0;
                                    v75 = RtlUIntAdd(4, (unsigned int)(2 * v764), &v761);
                                    v760 = v75;
                                    if ( v75 < 0 )
                                      goto LABEL_119;
                                    v75 = RtlUIntAdd(HIDWORD(lpMem[0]), v761, (char *)lpMem + 4);
                                    v760 = v75;
                                    if ( v75 < 0 )
                                      goto LABEL_119;
                                  }
                                  v140 = ++LODWORD(lpMem[0]);
                                  LODWORD(v779) = 0;
                                  v778 = 0;
                                  v141 = (unsigned int *)lpMem[1];
                                  if ( lpMem[1] )
                                  {
                                    v764 = (size_t)lpMem[1];
                                    if ( v140 )
                                    {
                                      do
                                      {
                                        v761 = 0;
                                        v75 = RtlUIntAdd(4, *v141, &v761);
                                        v760 = v75;
                                        if ( v75 < 0 )
                                          goto LABEL_119;
                                        v75 = RtlULongLongAdd(v142, v761, &v764);
                                        v760 = v75;
                                        if ( v75 < 0 )
                                          goto LABEL_119;
                                        v141 = (unsigned int *)v764;
                                      }
                                      while ( v144 + 1 < v143 );
                                    }
                                    v75 = RtlULongLongAdd(v141, 4, &v779);
                                    v760 = v75;
                                    if ( v75 < 0 )
                                      goto LABEL_119;
                                    if ( v145 + 2 > (_DWORD *)((char *)lpMem[1] + HIDWORD(lpMem[0])) )
                                      goto LABEL_110;
                                    *v145 = 4;
                                    *v779 = 0;
                                  }
                                  else
                                  {
                                    v761 = 0;
                                    v75 = RtlUIntAdd(4, 4, &v761);
                                    v760 = v75;
                                    if ( v75 < 0 )
                                      goto LABEL_119;
                                    v75 = RtlUIntAdd(HIDWORD(lpMem[0]), v761, (char *)lpMem + 4);
                                    v760 = v75;
                                    if ( v75 < 0 )
                                      goto LABEL_119;
                                  }
                                  v146 = ++LODWORD(lpMem[0]);
                                  LODWORD(v779) = 0;
                                  v778 = 0;
                                  v147 = (unsigned int *)lpMem[1];
                                  if ( lpMem[1] )
                                  {
                                    v764 = (size_t)lpMem[1];
                                    if ( v146 )
                                    {
                                      do
                                      {
                                        v761 = 0;
                                        v75 = RtlUIntAdd(4, *v147, &v761);
                                        v760 = v75;
                                        if ( v75 < 0 )
                                          goto LABEL_119;
                                        v75 = RtlULongLongAdd(v148, v761, &v764);
                                        v760 = v75;
                                        if ( v75 < 0 )
                                          goto LABEL_119;
                                        v147 = (unsigned int *)v764;
                                      }
                                      while ( v150 + 1 < v149 );
                                    }
                                    v75 = RtlULongLongAdd(v147, 4, &v779);
                                    v760 = v75;
                                    if ( v75 < 0 )
                                      goto LABEL_119;
                                    if ( v151 + 2 > (_DWORD *)((char *)lpMem[1] + HIDWORD(lpMem[0])) )
                                      goto LABEL_110;
                                    *v151 = 4;
                                    *v779 = 4;
                                  }
                                  else
                                  {
                                    v761 = 0;
                                    v75 = RtlUIntAdd(4, 4, &v761);
                                    v760 = v75;
                                    if ( v75 < 0 )
                                      goto LABEL_119;
                                    v75 = RtlUIntAdd(HIDWORD(lpMem[0]), v761, (char *)lpMem + 4);
                                    v760 = v75;
                                    if ( v75 < 0 )
                                      goto LABEL_119;
                                  }
                                  ++LODWORD(lpMem[0]);
                                  v761 = 0;
                                  v75 = RtlUIntAdd(4, 4, &v761);
                                  v760 = v75;
                                  if ( v75 < 0 )
                                    goto LABEL_119;
                                  v766 = v761;
                                  v761 = 0;
                                  v75 = RtlUIntAdd(v152, 8, &v761);
                                  v760 = v75;
                                  if ( v75 < 0 )
                                    goto LABEL_119;
                                  v75 = RtlUIntAdd(v153, v761, &v766);
                                  v760 = v75;
                                  if ( v75 < 0 )
                                    goto LABEL_119;
                                  v761 = 0;
                                  v75 = RtlUIntAdd(4, 4, &v761);
                                  v760 = v75;
                                  if ( v75 < 0 )
                                    goto LABEL_119;
                                  v75 = RtlUIntAdd(v766, v761, &v766);
                                  v760 = v75;
                                  if ( v75 < 0 )
                                    goto LABEL_119;
                                  v761 = 0;
                                  v75 = RtlUIntAdd(4, 4, &v761);
                                  v760 = v75;
                                  if ( v75 < 0 )
                                    goto LABEL_119;
                                  v75 = RtlUIntAdd(v766, v761, &v766);
                                  v760 = v75;
                                  if ( v75 < 0 )
                                    goto LABEL_119;
                                  v761 = 0;
                                  v75 = RtlUIntAdd(4, 4, &v761);
                                  v760 = v75;
                                  if ( v75 < 0 )
                                    goto LABEL_119;
                                  v75 = RtlUIntAdd(v766, v761, &v766);
                                  v760 = v75;
                                  if ( v75 < 0 )
                                    goto LABEL_119;
                                  v761 = 0;
                                  v75 = RtlUIntAdd(4, 4, &v761);
                                  v760 = v75;
                                  if ( v75 < 0 )
                                    goto LABEL_119;
                                  v75 = RtlUIntAdd(v766, v761, &v766);
                                  v760 = v75;
                                  if ( v75 < 0 )
                                    goto LABEL_119;
                                  v768 = 0;
                                  dwBytes = v766;
                                  v765 = 0;
                                  v782 = __rdtsc();
                                  v761 = 0;
                                  v796 = 8;
                                  v155 = RtlUIntAdd(8, HIDWORD(lpMem[0]), &v796);
                                  if ( v155 < 0 )
                                  {
                                    v774 = v76;
                                    v788 = v74;
                                  }
                                  else
                                  {
                                    v156 = (v796 + 7) & 0xFFFFFFF8;
                                    if ( v156 < v796 )
                                    {
                                      v75 = -805306219;
                                      goto LABEL_319;
                                    }
                                    v796 = (v796 + 7) & 0xFFFFFFF8;
                                    v157 = v156;
                                    v158 = GetProcessHeap();
                                    v159 = (char *)HeapAlloc(v158, 8u, v157);
                                    v160 = v159;
                                    if ( !v159 )
                                    {
                                      v75 = -805306345;
                                      v760 = -805306345;
LABEL_316:
                                      if ( v75 < 0 )
                                        goto LABEL_119;
                                      if ( !v768 )
                                        goto LABEL_318;
                                      if ( !v777 )
                                        goto LABEL_113;
                                      v782 = (SIZE_T)v777;
                                      v75 = RtlULongLongAdd(v777, 4, &v782);
                                      v760 = v75;
                                      v777 = v400;
                                      if ( v75 >= 0 )
                                      {
                                        v402 = (int *)v782;
                                        if ( !*v400 )
                                          v402 = 0;
                                        if ( *v400 != 4 )
                                          goto LABEL_110;
                                        v75 = *v402;
                                        v760 = v75;
                                        if ( v75 == -805306333 )
                                        {
                                          v403 = -2147024774;
                                          dwBytes_4 = -2147024774;
                                        }
                                        else
                                        {
                                          v403 = v75;
                                          dwBytes_4 = v75;
                                          if ( v75 != -2147024774 && v75 < 0 )
                                            goto LABEL_119;
                                        }
                                        v777 = v400;
                                        if ( v401 != 6 )
                                        {
LABEL_318:
                                          v75 = -1073425151;
                                          goto LABEL_319;
                                        }
                                        v764 = v399;
                                        do
                                        {
                                          v75 = RtlULongLongAdd(v399, 4, &v764);
                                          v760 = v75;
                                          if ( v75 < 0 )
                                            goto LABEL_119;
                                          v75 = RtlULongLongAdd(v764, v404, &v764);
                                          v760 = v75;
                                          if ( v75 < 0 )
                                            goto LABEL_119;
                                          v399 = v764;
                                        }
                                        while ( v405 == -1 );
                                        v75 = RtlULongLongAdd(v764, 4, &v764);
                                        v760 = v75;
                                        if ( v75 >= 0 )
                                        {
                                          v408 = (LPVOID *)v764;
                                          if ( !v407 )
                                            v408 = 0;
                                          if ( v407 != 8 )
                                            goto LABEL_110;
                                          dwBytes_4 = v403;
                                          v777 = v406;
                                          if ( !v406 )
                                            goto LABEL_113;
                                          v409 = (size_t)v406;
                                          v764 = (size_t)v406;
                                          v778 = *v408;
                                          do
                                          {
                                            v75 = RtlULongLongAdd(v409, 4, &v764);
                                            v760 = v75;
                                            if ( v75 < 0 )
                                              goto LABEL_119;
                                            v75 = RtlULongLongAdd(v764, v410, &v764);
                                            v760 = v75;
                                            if ( v75 < 0 )
                                              goto LABEL_119;
                                            v409 = v764;
                                          }
                                          while ( (unsigned int)(v411 + 1) < 2 );
                                          v75 = RtlULongLongAdd(v764, 4, &v764);
                                          v760 = v75;
                                          if ( v75 < 0 )
                                            goto LABEL_119;
                                          v414 = (unsigned int *)v764;
                                          if ( !v413 )
                                            v414 = 0;
                                          if ( v413 != 4 )
                                            goto LABEL_110;
                                          dwBytes_4 = v403;
                                          v777 = v412;
                                          if ( !v412 )
                                          {
LABEL_113:
                                            v75 = -1073741811;
                                            goto LABEL_114;
                                          }
                                          v415 = (size_t)v412;
                                          v764 = (size_t)v412;
                                          v783 = *v414;
                                          do
                                          {
                                            v75 = RtlULongLongAdd(v415, 4, &v764);
                                            v760 = v75;
                                            if ( v75 < 0 )
                                              goto LABEL_119;
                                            v75 = RtlULongLongAdd(v764, v416, &v764);
                                            v760 = v75;
                                            if ( v75 < 0 )
                                              goto LABEL_119;
                                            v415 = v764;
                                          }
                                          while ( (unsigned int)(v417 + 1) < 3 );
                                          v75 = RtlULongLongAdd(v764, 4, &v764);
                                          v760 = v75;
                                          if ( v75 >= 0 )
                                          {
                                            v420 = 0;
                                            if ( v419 )
                                              v420 = (const void *)v764;
                                            v421 = (unsigned int *)v418;
                                            v764 = v418;
                                            do
                                            {
                                              v422 = *v421;
                                              v75 = RtlULongLongAdd(v421, 4, &v764);
                                              v760 = v75;
                                              if ( v75 < 0 )
                                                goto LABEL_119;
                                              v75 = RtlULongLongAdd(v764, v422, &v764);
                                              v760 = v75;
                                              if ( v75 < 0 )
                                                goto LABEL_119;
                                              v421 = (unsigned int *)v764;
                                            }
                                            while ( (unsigned int)(v423 + 1) < 4 );
                                            v75 = RtlULongLongAdd(v764, 4, &v764);
                                            v760 = v75;
                                            if ( v75 >= 0 )
                                            {
                                              v426 = (unsigned int *)v764;
                                              if ( !v425 )
                                                v426 = 0;
                                              if ( v425 != 4 )
                                                goto LABEL_110;
                                              v777 = v424;
                                              if ( !v424 )
                                              {
                                                v75 = -1073741811;
                                                goto LABEL_319;
                                              }
                                              v427 = (size_t)v424;
                                              v764 = (size_t)v424;
                                              v428 = *v426;
                                              do
                                              {
                                                v75 = RtlULongLongAdd(v427, 4, &v764);
                                                v760 = v75;
                                                if ( v75 < 0 )
                                                  goto LABEL_119;
                                                v75 = RtlULongLongAdd(v764, v429, &v764);
                                                v760 = v75;
                                                if ( v75 < 0 )
                                                  goto LABEL_119;
                                                v427 = v764;
                                              }
                                              while ( (unsigned int)(v430 + 1) < 5 );
                                              v100 = RtlULongLongAdd(v764, 4, &v764);
                                              v75 = v100;
                                              v760 = v100;
                                              if ( v100 < 0 )
                                              {
LABEL_118:
                                                v760 = v100;
                                                goto LABEL_119;
                                              }
                                              v434 = (int *)v764;
                                              if ( !v431 )
                                                v434 = 0;
                                              if ( v431 != v432 )
                                              {
                                                v75 = -1073741789;
                                                goto LABEL_319;
                                              }
                                              if ( (LPVOID)v790 != v778 )
                                                goto LABEL_318;
                                              v812 = *v434;
                                              v809 = v783;
                                              if ( v428 > v432 || (unsigned int)v433 > v432 )
                                              {
                                                v75 = -2147024774;
                                                goto LABEL_319;
                                              }
                                              memcpy_0(TickCount64, v420, v433);
                                              v100 = dwBytes_4;
                                              if ( dwBytes_4 )
                                              {
                                                v75 = dwBytes_4;
                                                goto LABEL_118;
                                              }
                                            }
                                          }
                                        }
                                      }
                                      goto LABEL_119;
                                    }
                                    v788 = v74;
                                    v774 = v76;
                                    v764 = (size_t)v159;
                                    *(_DWORD *)v159 = lpMem[0];
                                    v155 = RtlULongLongAdd(v159, 4, &v764);
                                    if ( v155 < 0
                                      || (v163 = v764,
                                          *(_DWORD *)v764 = HIDWORD(lpMem[0]),
                                          v155 = RtlULongLongAdd(v163, v162, &v764),
                                          v155 < 0) )
                                    {
                                      v788 = v74;
                                      v774 = v76;
                                      dwBytes = v161;
                                      v164 = GetProcessHeap();
                                      HeapFree(v164, 0, v160);
                                      v154 = v761;
                                    }
                                    else
                                    {
                                      *(_QWORD *)&v160[v796 - 8] = v782;
                                      memcpy_0((void *)v764, lpMem[1], HIDWORD(lpMem[0]));
                                      v765 = v160;
                                      v154 = v796;
                                    }
                                  }
                                  v165 = 0;
                                  pcchLength = 0;
                                  v166 = 0;
                                  v776 = 0;
                                  v773 = 0;
                                  v780 = 0;
                                  v75 = v155 | 0x10000000;
                                  v760 = v75;
                                  if ( v75 < 0 )
                                    goto LABEL_291;
                                  v167 = (unsigned __int8 *)v765;
                                  if ( !v765 )
                                  {
                                    v75 = -805306355;
                                    goto LABEL_319;
                                  }
                                  v794 = (void *)v154;
                                  if ( !v154 || (Size = v154 + 8LL, v168 = MemoryAlloc(Size), (Src = v168) == 0) )
                                  {
                                    v75 = -805306367;
                                    v760 = -805306367;
                                    goto LABEL_293;
                                  }
                                  v781 = 0;
                                  v169 = 0;
                                  v767 = 0;
                                  v170 = 0;
                                  v171 = (unsigned __int64)v794;
                                  if ( v794 )
                                  {
                                    do
                                      v169 ^= v167[v170++];
                                    while ( v170 < (unsigned __int64)v794 );
                                    v767 = v169;
                                  }
                                  v775 = (LPVOID)0xC81ECB17B1B54A58LL;
                                  v172 = v167;
                                  v764 = (size_t)v167;
                                  v795 = (SIZE_T)v168;
                                  v173 = (unsigned __int8)v794 & 7;
                                  if ( ((unsigned __int8)v794 & 7) != 0 )
                                  {
                                    v174 = 0;
                                    LODWORD(v772) = 0;
                                    v766 = 0;
                                    v175 = 0;
                                    v176 = 0;
                                    do
                                    {
                                      v177 = *v172++;
                                      v761 = 8 * v175;
                                      if ( v175 >= 4 )
                                        v174 |= v177 << (56 - v761);
                                      else
                                        v176 |= v177 << (24 - v761);
                                      ++v175;
                                    }
                                    while ( (int)v175 < v173 );
                                    v766 = v176;
                                    LODWORD(v772) = v174;
                                    v764 = (size_t)v172;
                                    v765 = v167;
                                    v774 = v76;
                                    v788 = v74;
                                    v171 = (unsigned __int64)v794;
                                    v178 = v176 ^ 0xB17A307A;
                                    v179 = v174 ^ 0x42F6B18D;
                                    v180 = v176 ^ 0xB17A307A;
                                    v181 = v179;
                                    v761 = 0;
                                    if ( ((unsigned __int8)v794 & 7) != 0 )
                                    {
                                      v182 = (_BYTE *)v795;
                                      do
                                      {
                                        v782 = (SIZE_T)(v182 + 1);
                                        if ( v761 >= 4 )
                                        {
                                          v181 = __ROR4__(v181, 24);
                                          v183 = v181;
                                        }
                                        else
                                        {
                                          v180 = __ROR4__(v180, 24);
                                          v183 = v180;
                                        }
                                        *v182 = v183;
                                        ++v761;
                                        v182 = (_BYTE *)v782;
                                      }
                                      while ( (int)v761 < v173 );
                                      v795 = v782;
                                    }
                                    if ( (unsigned int)v173 <= 4 )
                                    {
                                      v184 = 0;
                                      if ( (unsigned int)v173 < 4 )
                                        v178 = v178 >> (8 * (4 - v173)) << (8 * (4 - v173));
                                    }
                                    else
                                    {
                                      v184 = v179 >> (8 * (8 - v173)) << (8 * (8 - v173));
                                    }
                                    v172 = (unsigned __int8 *)v764;
                                  }
                                  else
                                  {
                                    v178 = 0;
                                    v184 = -1;
                                    v766 = 0;
                                    LODWORD(v772) = 0;
                                  }
                                  if ( v171 >> 3 )
                                  {
                                    v782 = 0;
                                    v761 = 19032;
                                    v760 = WORD1(v775);
                                    v185 = WORD2(v775);
                                    v783 = HIDWORD(v775) ^ 0xB1B54A58;
                                    v186 = (_BYTE *)v795;
                                    v187 = v171 >> 3;
                                    v188 = v772;
                                    v189 = v766;
                                    v190 = HIDWORD(v775) ^ 0xB1B54A58;
                                    do
                                    {
                                      v191 = v172[3] | ((v172[2] | ((v172[1] | (*v172 << 8)) << 8)) << 8);
                                      v192 = *(unsigned __int8 *)(v764 + 7)
                                           | ((*(unsigned __int8 *)(v764 + 6)
                                             | ((*(unsigned __int8 *)(v764 + 5) | (v172[4] << 8)) << 8)) << 8);
                                      v193 = v184 ^ v192;
                                      v764 += 8LL;
                                      v194 = v178 ^ v191 ^ ((v184 ^ v192) - v761);
                                      v195 = HIDWORD(v775) ^ v194;
                                      v196 = v193
                                           ^ (__ROR4__(HIDWORD(v775) ^ v194, 7) + WORD1(v775) * __ROR4__(v194, 15));
                                      v197 = v195 ^ (v185 * __ROR4__(v196 - 1313519016, 9) - __ROR4__(v196, 10));
                                      v198 = v196 ^ (__ROR4__(v197, 27) + HIWORD(v775) * __ROR4__(v185 ^ v197, 28));
                                      v199 = v197 ^ (HIDWORD(v775) - (v198 ^ 0xB1B54A58));
                                      v200 = v198 ^ (WORD1(v775) * (v199 - v761) - (v199 >> 6));
                                      v201 = v199 ^ (v761 * (v185 ^ __ROR4__(v200, 15)));
                                      v202 = v200 ^ (v185 * (HIWORD(v775) + __ROR4__(~v201, 3)));
                                      v203 = v201 ^ (v202 - v761 - HIDWORD(v775));
                                      v204 = v202 ^ (v760 * (v203 ^ HIWORD(v775))) ^ __ROR4__(v203, 10);
                                      v205 = v203 ^ __ROR4__(v204, 3) ^ (v185 * __ROR4__(v204 ^ v761, 26));
                                      v206 = v204 ^ (v761 * (__ROR4__(v205, 15) - HIWORD(v775)));
                                      v207 = v205
                                           ^ (v761 * (v206 ^ HIWORD(v775)))
                                           ^ ((v206 ^ (v206 >> 14)) >> 1)
                                           ^ (v761 * ((8 * (v206 - v185)) | ((unsigned __int64)(v206 - v185) >> 29)));
                                      v208 = v206 ^ (WORD1(v775) * (v207 - v185) - (v207 >> 13));
                                      v209 = v207 ^ __ROR4__(v208, 11) ^ (v185 * __ROR4__(-1313519016 - v208, 9));
                                      v210 = v208 ^ (v209 - HIWORD(v775) + 1313519016);
                                      v211 = v209 ^ (v761 * (v760 ^ v210) - __ROR4__(v210, 7));
                                      v212 = v210
                                           ^ (WORD1(v775) * __ROR4__(HIWORD(v775) ^ v211, 28) - __ROR4__(v211, 16));
                                      v213 = v211 ^ (__ROR4__(v212, 4) + v185 * __ROR4__(-1313519016 - v212, 10));
                                      v214 = v212 ^ __ROR4__(v213, 9) ^ (HIWORD(v775) * __ROR4__(v213 + 1313519016, 4));
                                      v215 = v213 ^ (v761 * __ROR4__(HIDWORD(v775) ^ v214, 24) - __ROR4__(v214, 30));
                                      v216 = v214
                                           ^ (WORD1(v775) * __ROR4__(HIDWORD(v775) - v215, 11) - __ROR4__(v215, 12));
                                      v217 = v215 ^ (v216 >> 8) ^ (v185 * (v216 ^ WORD1(v775)));
                                      v178 = v217 ^ v189;
                                      v184 = v190 ^ v216 ^ v217 ^ v188;
                                      v186[3] = v217 ^ v189;
                                      v186[7] = v190 ^ v216 ^ v217 ^ v188;
                                      v186[2] = __ROR4__(v217 ^ v189, 8);
                                      v186[6] = __ROR4__(v184, 8);
                                      v186[1] = __ROR4__(v217 ^ v189, 16);
                                      v186[5] = __ROR4__(v184, 16);
                                      *v186 = __ROR4__(v217 ^ v189, 24);
                                      v186[4] = __ROR4__(v184, 24);
                                      v189 = v191;
                                      v188 = v192;
                                      v186 += 8;
                                      ++v782;
                                      v172 = (unsigned __int8 *)v764;
                                    }
                                    while ( v782 < v187 );
                                    v169 = v767;
                                    v74 = v788;
                                    v76 = v774;
                                    v166 = (unsigned int *)v776;
                                    v165 = (unsigned int *)v776;
                                    v167 = (unsigned __int8 *)v765;
                                    v171 = (unsigned __int64)v794;
                                  }
                                  *(_QWORD *)((char *)Src + v171) = v169;
                                  v218 = GetProcessHeap();
                                  v219 = HeapAlloc(v218, 8u, 0x30u);
                                  v774 = v219;
                                  if ( v219 )
                                  {
                                    *v219 = Size;
                                    v221 = GetProcessHeap();
                                    v222 = HeapAlloc(v221, 8u, (unsigned int)Size);
                                    if ( !v222 )
                                      goto LABEL_266;
                                    v765 = v167;
                                    v223 = v774;
                                    *((_QWORD *)v774 + 1) = v222;
                                    memcpy_0(v222, Src, (unsigned int)Size);
                                    v223[4] = 160;
                                    v224 = GetProcessHeap();
                                    v225 = HeapAlloc(v224, 8u, 0xA0u);
                                    if ( !v225 )
                                      goto LABEL_266;
                                    *((_QWORD *)v223 + 3) = v225;
                                    *v225 = `WarbirdUmGetEncryptionCipher'::`2'::EncryptionCipher;
                                    v225[1] = xmmword_18012E4F0;
                                    v225[2] = xmmword_18012E500;
                                    v225[3] = xmmword_18012E510;
                                    v225[4] = xmmword_18012E520;
                                    v225[5] = xmmword_18012E530;
                                    v225[6] = xmmword_18012E540;
                                    v225[7] = xmmword_18012E550;
                                    v225[8] = xmmword_18012E560;
                                    v225[9] = xmmword_18012E570;
                                    v223[8] = 8;
                                    v226 = GetProcessHeap();
                                    v227 = HeapAlloc(v226, 8u, 8u);
                                    if ( v227 )
                                    {
                                      *((_QWORD *)v223 + 5) = v227;
                                      *v227 = `WarbirdUmGetEncryptionKey'::`2'::nEncryptionKey;
                                      v781 = v223;
                                      v220 = 0;
                                      v165 = (unsigned int *)v781;
                                      v781 = 0;
                                    }
                                    else
                                    {
LABEL_266:
                                      v220 = -1073741801;
                                      v228 = v774;
                                      v778 = (LPVOID)*((_QWORD *)v774 + 1);
                                      if ( v778 )
                                      {
                                        v229 = GetProcessHeap();
                                        HeapFree(v229, 0, v778);
                                        v228 = v774;
                                        *((_QWORD *)v774 + 1) = 0;
                                      }
                                      v778 = (LPVOID)v228[3];
                                      if ( v778 )
                                      {
                                        v230 = GetProcessHeap();
                                        HeapFree(v230, 0, v778);
                                        v228 = v774;
                                        *((_QWORD *)v774 + 3) = 0;
                                      }
                                      v778 = (LPVOID)v228[5];
                                      if ( v778 )
                                      {
                                        v231 = GetProcessHeap();
                                        HeapFree(v231, 0, v778);
                                        *((_QWORD *)v774 + 5) = 0;
                                      }
                                      v232 = GetProcessHeap();
                                      HeapFree(v232, 0, v774);
                                    }
                                  }
                                  else
                                  {
                                    v220 = -1073741801;
                                  }
                                  v233 = GetProcessHeap();
                                  HeapFree(v233, 0, Src);
                                  v234 = v781;
                                  if ( v781 )
                                  {
                                    v778 = (LPVOID)*((_QWORD *)v781 + 1);
                                    if ( v778 )
                                    {
                                      v235 = GetProcessHeap();
                                      HeapFree(v235, 0, v778);
                                      v234 = v781;
                                      *((_QWORD *)v781 + 1) = 0;
                                    }
                                    v778 = (LPVOID)v234[3];
                                    if ( v778 )
                                    {
                                      v236 = GetProcessHeap();
                                      HeapFree(v236, 0, v778);
                                      v234 = v781;
                                      *((_QWORD *)v781 + 3) = 0;
                                    }
                                    v778 = (LPVOID)v234[5];
                                    if ( v778 )
                                    {
                                      v237 = GetProcessHeap();
                                      HeapFree(v237, 0, v778);
                                      *((_QWORD *)v781 + 5) = 0;
                                    }
                                    v238 = GetProcessHeap();
                                    HeapFree(v238, 0, v781);
                                  }
                                  v75 = v220 | 0x10000000;
                                  v760 = v75;
                                  if ( v75 < 0 )
                                  {
                                    v245 = v765;
LABEL_292:
                                    if ( !v245 )
                                    {
LABEL_294:
                                      if ( v165 )
                                      {
                                        v778 = (LPVOID)*((_QWORD *)v165 + 1);
                                        if ( v778 )
                                        {
                                          v247 = GetProcessHeap();
                                          HeapFree(v247, 0, v778);
                                          *((_QWORD *)v165 + 1) = 0;
                                        }
                                        v778 = (LPVOID)*((_QWORD *)v165 + 3);
                                        if ( v778 )
                                        {
                                          v248 = GetProcessHeap();
                                          HeapFree(v248, 0, v778);
                                          *((_QWORD *)v165 + 3) = 0;
                                        }
                                        v778 = (LPVOID)*((_QWORD *)v165 + 5);
                                        if ( v778 )
                                        {
                                          v249 = GetProcessHeap();
                                          HeapFree(v249, 0, v778);
                                          *((_QWORD *)v165 + 5) = 0;
                                        }
                                        v250 = GetProcessHeap();
                                        HeapFree(v250, 0, v165);
                                      }
                                      v251 = (void *)pcchLength;
                                      if ( pcchLength )
                                      {
                                        v252 = GetProcessHeap();
                                        HeapFree(v252, 0, v251);
                                      }
                                      if ( v166 )
                                      {
                                        v253 = GetProcessHeap();
                                        HeapFree(v253, 0, v166);
                                      }
                                      v254 = v773;
                                      if ( v773 )
                                      {
                                        v255 = (void *)*((_QWORD *)v773 + 1);
                                        if ( v255 )
                                        {
                                          v256 = GetProcessHeap();
                                          HeapFree(v256, 0, v255);
                                          v254[1] = 0;
                                        }
                                        v257 = (void *)v254[3];
                                        if ( v257 )
                                        {
                                          v258 = GetProcessHeap();
                                          HeapFree(v258, 0, v257);
                                          v254[3] = 0;
                                        }
                                        v259 = (void *)v254[5];
                                        if ( v259 )
                                        {
                                          v260 = GetProcessHeap();
                                          HeapFree(v260, 0, v259);
                                          v254[5] = 0;
                                        }
                                        v261 = GetProcessHeap();
                                        HeapFree(v261, 0, v254);
                                      }
                                      v262 = v780;
                                      if ( v780 )
                                      {
                                        v263 = GetProcessHeap();
                                        HeapFree(v263, 0, v262);
                                      }
                                      goto LABEL_316;
                                    }
LABEL_293:
                                    v246 = GetProcessHeap();
                                    HeapFree(v246, 0, v765);
                                    goto LABEL_294;
                                  }
                                  LODWORD(v772) = 0;
                                  v760 = 4;
                                  v240 = RtlUIntAdd(4, *v165, &v760);
                                  if ( v240 >= 0 )
                                  {
                                    v240 = RtlUIntAdd(v760, v239, &v760);
                                    if ( v240 >= 0 )
                                    {
                                      v782 = (SIZE_T)(v165 + 4);
                                      v240 = RtlUIntAdd(v760, v165[4], &v760);
                                      if ( v240 >= 0 )
                                      {
                                        v240 = RtlUIntAdd(v760, v241, &v760);
                                        if ( v240 >= 0 )
                                        {
                                          Src = v165 + 8;
                                          v240 = RtlUIntAdd(v760, v165[8], &v760);
                                          if ( v240 >= 0 )
                                          {
                                            v771 = v165;
                                            v242 = v760;
                                            v243 = GetProcessHeap();
                                            v244 = HeapAlloc(v243, 8u, v242);
                                            v774 = v244;
                                            v165 = v771;
                                            if ( !v244 )
                                            {
                                              v75 = -805306345;
LABEL_290:
                                              v760 = v75;
LABEL_291:
                                              v245 = v765;
                                              goto LABEL_292;
                                            }
                                            v776 = v244;
                                            *v244 = *v771;
                                            v240 = RtlULongLongAdd(v244, 4, &v776);
                                            if ( v240 < 0 )
                                            {
                                              v765 = v265;
                                              dwBytes = v266;
                                              v774 = v264;
                                            }
                                            else
                                            {
                                              memcpy_0(v776, *((const void **)v165 + 1), *v165);
                                              v240 = RtlULongLongAdd(v776, *v165, &v776);
                                              if ( v240 >= 0 )
                                              {
                                                v267 = v776;
                                                *(_DWORD *)v776 = *(_DWORD *)v782;
                                                v240 = RtlULongLongAdd(v267, 4, &v776);
                                                if ( v240 >= 0 )
                                                {
                                                  memcpy_0(v776, *((const void **)v165 + 3), *v268);
                                                  v240 = RtlULongLongAdd(v776, *(unsigned int *)v782, &v776);
                                                  if ( v240 >= 0 )
                                                  {
                                                    v269 = v776;
                                                    *(_DWORD *)v776 = *(_DWORD *)Src;
                                                    v240 = RtlULongLongAdd(v269, 4, &v776);
                                                    if ( v240 >= 0 )
                                                    {
                                                      memcpy_0(v776, *((const void **)v165 + 5), *v270);
                                                      v240 = RtlULongLongAdd(v776, *(unsigned int *)Src, &v776);
                                                      if ( v240 >= 0 )
                                                      {
                                                        pcchLength = (size_t)v774;
                                                        LODWORD(v772) = v760;
                                                        goto LABEL_331;
                                                      }
                                                    }
                                                  }
                                                }
                                              }
                                            }
                                            v271 = GetProcessHeap();
                                            HeapFree(v271, 0, v774);
                                          }
                                        }
                                      }
                                    }
                                  }
LABEL_331:
                                  v75 = v240 | 0x10000000;
                                  v760 = v75;
                                  if ( v75 < 0 )
                                    goto LABEL_291;
                                  v803 = 8;
                                  v272 = RtlUIntAdd(8, dwBytes, &v803);
                                  v75 = v272 | 0x10000000;
                                  v760 = v272 | 0x10000000;
                                  if ( v272 < 0 )
                                    goto LABEL_291;
                                  v273 = (v803 + 7) & 0xFFFFFFF8;
                                  if ( (unsigned int)v273 < v803 )
                                  {
                                    v75 = -1073741675;
                                    goto LABEL_290;
                                  }
                                  v813 = (v803 + 7) & 0xFFFFFFF8;
                                  v75 = RtlUIntAdd(v273, 8, &v813);
                                  v760 = v75;
                                  if ( v75 < 0 )
                                    goto LABEL_291;
                                  v788 = v74;
                                  v774 = v76;
                                  v765 = v274;
                                  v771 = v165;
                                  v761 = 0;
                                  v275 = lpMem[1];
                                  if ( !lpMem[1] )
                                    goto LABEL_344;
                                  v771 = v165;
                                  v765 = v274;
                                  v774 = v76;
                                  v788 = v74;
                                  if ( LODWORD(lpMem[0]) <= 1 )
                                    goto LABEL_344;
                                  v764 = (size_t)lpMem[1];
                                  do
                                  {
                                    v75 = RtlULongLongAdd(v275, 4, &v764);
                                    v760 = v75;
                                    if ( v75 < 0 )
                                      goto LABEL_291;
                                    v75 = RtlULongLongAdd(v764, v276, &v764);
                                    v760 = v75;
                                    if ( v75 < 0 )
                                      goto LABEL_291;
                                    v275 = (LPVOID)v764;
                                  }
                                  while ( v277 == -1 );
                                  v783 = *(_DWORD *)v764;
                                  v75 = RtlULongLongAdd(v764, 4, &v764);
                                  v760 = v75;
                                  if ( v75 < 0 )
                                    goto LABEL_291;
                                  v278 = lpMem[1];
                                  if ( !lpMem[1] || LODWORD(lpMem[0]) <= 2 )
                                  {
LABEL_344:
                                    v75 = -1073741811;
                                    v760 = -1073741811;
                                    goto LABEL_291;
                                  }
                                  v764 = (size_t)lpMem[1];
                                  do
                                  {
                                    v75 = RtlULongLongAdd(v278, 4, &v764);
                                    v760 = v75;
                                    if ( v75 < 0 )
                                      goto LABEL_291;
                                    v75 = RtlULongLongAdd(v764, v282, &v764);
                                    v760 = v75;
                                    if ( v75 < 0 )
                                      goto LABEL_291;
                                    v278 = (LPVOID)v764;
                                  }
                                  while ( (unsigned int)(v283 + 1) < 2 );
                                  v75 = RtlULongLongAdd(v764, 4, &v764);
                                  v760 = v75;
                                  if ( v75 < 0 )
                                    goto LABEL_291;
                                  v761 = v284;
                                  v766 = v285;
                                  v75 = RtlUIntAdd(v285, v813, &v766);
                                  v760 = v75;
                                  if ( v75 < 0 )
                                    goto LABEL_291;
                                  v75 = RtlUIntAdd(v766, v286, &v766);
                                  v760 = v75;
                                  if ( v75 < 0 )
                                    goto LABEL_291;
                                  v75 = RtlUIntAdd(v766, v783, &v766);
                                  v760 = v75;
                                  if ( v75 < 0 )
                                    goto LABEL_291;
                                  v75 = RtlUIntAdd(v766, v287, &v766);
                                  v760 = v75;
                                  if ( v75 < 0 )
                                    goto LABEL_291;
                                  v75 = RtlUIntAdd(v766, v288, &v766);
                                  v760 = v75;
                                  if ( v75 < 0 )
                                    goto LABEL_291;
                                  v761 = v766;
                                  if ( v766 > 0x400000 )
                                  {
                                    v75 = -2147418113;
                                    goto LABEL_290;
                                  }
                                  v279 = v766;
                                  v280 = GetProcessHeap();
                                  v281 = (unsigned int *)HeapAlloc(v280, 8u, v279);
                                  v166 = v281;
                                  if ( !v281 )
                                  {
                                    v75 = -805306345;
LABEL_348:
                                    v760 = v75;
LABEL_349:
                                    v165 = v771;
                                    goto LABEL_291;
                                  }
                                  v847 = 0;
                                  v848 = 0;
                                  phModule = 0;
                                  if ( !pcchLength )
                                  {
                                    v75 = -2147024809;
                                    goto LABEL_348;
                                  }
                                  *(_QWORD *)&v847 = pcchLength;
                                  LODWORD(v848) = v772;
                                  *((_QWORD *)&v847 + 1) = v281;
                                  *(_QWORD *)((char *)&v848 + 4) = v761;
                                  if ( GetModuleHandleExW(1u, L"ntdll.dll", &phModule)
                                    && (ProcAddress = GetProcAddress(phModule, "NtQuerySystemInformation")) != 0 )
                                  {
                                    v291 = ((__int64 (__fastcall *)(__int64, __int128 *))ProcAddress)(134, &v847);
                                    v75 = v291 | 0x10000000;
                                    v760 = v291 | 0x10000000;
                                    if ( v291 >= 0 )
                                    {
                                      v292 = DWORD1(v848);
                                      goto LABEL_379;
                                    }
                                  }
                                  else
                                  {
                                    v289 = GetLastError();
                                    v760 = v289;
                                    v75 = v289;
                                    if ( v289 > 0 )
                                    {
                                      v75 = (unsigned __int16)v289 | 0x80070000;
                                      v760 = v75;
                                    }
                                    if ( v75 >= 0 )
                                    {
                                      v75 = -2147467259;
                                      goto LABEL_348;
                                    }
                                  }
                                  if ( v75 == -805306333 )
                                  {
                                    v75 = -2147024774;
                                    goto LABEL_348;
                                  }
                                  if ( v75 < 0 )
                                    goto LABEL_349;
                                  v292 = v761;
LABEL_379:
                                  dwBytes = 0;
                                  v776 = v166;
                                  if ( v292 < 4 )
                                  {
LABEL_380:
                                    v75 = -805306306;
                                    goto LABEL_348;
                                  }
                                  v293 = *v166;
                                  v783 = *v166;
                                  v295 = RtlULongLongAdd(v166, 4, &v776);
                                  if ( v295 >= 0 )
                                  {
                                    v295 = RtlUIntAdd(0, v294, &dwBytes);
                                    if ( v295 < 0 )
                                    {
LABEL_433:
                                      v776 = v166;
                                      v165 = v771;
                                      goto LABEL_434;
                                    }
                                    if ( v297 - dwBytes < (unsigned int)v293 )
                                      goto LABEL_380;
                                    Src = v776;
                                    v782 = v293;
                                    v295 = RtlULongLongAdd(v776, (unsigned int)v293, &v776);
                                    if ( v295 >= 0 )
                                    {
                                      v295 = RtlUIntAdd(dwBytes, (unsigned int)v293, &dwBytes);
                                      if ( v295 >= 0 )
                                      {
                                        if ( v298 - dwBytes < (unsigned int)v299 )
                                          goto LABEL_380;
                                        v761 = *(_DWORD *)v776;
                                        v295 = RtlULongLongAdd(v776, v299, &v776);
                                        if ( v295 >= 0 )
                                        {
                                          v295 = RtlUIntAdd(dwBytes, v300, &dwBytes);
                                          if ( v295 >= 0 )
                                          {
                                            if ( v301 - dwBytes < (unsigned int)v302 )
                                              goto LABEL_380;
                                            v794 = v776;
                                            Size = v302;
                                            v295 = RtlULongLongAdd(v776, (unsigned int)v302, &v776);
                                            if ( v295 >= 0 )
                                            {
                                              v295 = RtlUIntAdd(dwBytes, v303, &dwBytes);
                                              if ( v295 >= 0 )
                                              {
                                                if ( v304 - dwBytes < v305 )
                                                  goto LABEL_380;
                                                LODWORD(v772) = *(_DWORD *)v776;
                                                v295 = RtlULongLongAdd(v776, 4, &v776);
                                                if ( v295 >= 0 )
                                                {
                                                  v295 = RtlUIntAdd(dwBytes, 4, &dwBytes);
                                                  if ( v295 >= 0 )
                                                  {
                                                    if ( v306 - dwBytes < v307 )
                                                      goto LABEL_380;
                                                    v295 = RtlUIntAdd(dwBytes, v307, &dwBytes);
                                                    if ( v295 >= 0 )
                                                    {
                                                      if ( v308 != dwBytes
                                                        || (unsigned int)(v309 + v310 + v293) + 12LL != v308 )
                                                      {
                                                        goto LABEL_380;
                                                      }
                                                      v311 = GetProcessHeap();
                                                      v312 = HeapAlloc(v311, 8u, 0x30u);
                                                      v775 = v312;
                                                      v165 = v771;
                                                      v245 = v765;
                                                      if ( !v312 )
                                                      {
                                                        v773 = 0;
                                                        v75 = -805306345;
                                                        v760 = -805306345;
                                                        goto LABEL_292;
                                                      }
                                                      v788 = v74;
                                                      v774 = v76;
                                                      v764 = 0;
                                                      if ( Src )
                                                      {
                                                        *v312 = v783;
                                                        v313 = GetProcessHeap();
                                                        v314 = HeapAlloc(v313, 8u, v782);
                                                        if ( !v314 )
                                                        {
LABEL_412:
                                                          v295 = -1073741801;
                                                          v776 = v166;
                                                          v322 = v775;
                                                          v778 = (LPVOID)*((_QWORD *)v775 + 1);
                                                          if ( v778 )
                                                          {
                                                            v323 = GetProcessHeap();
                                                            HeapFree(v323, 0, v778);
                                                            v322 = v775;
                                                            *((_QWORD *)v775 + 1) = 0;
                                                          }
                                                          v778 = (LPVOID)v322[3];
                                                          if ( v778 )
                                                          {
                                                            v324 = GetProcessHeap();
                                                            HeapFree(v324, 0, v778);
                                                            v322 = v775;
                                                            *((_QWORD *)v775 + 3) = 0;
                                                          }
                                                          v778 = (LPVOID)v322[5];
                                                          if ( v778 )
                                                          {
                                                            v325 = GetProcessHeap();
                                                            HeapFree(v325, 0, v778);
                                                            *((_QWORD *)v775 + 5) = 0;
                                                          }
                                                          v326 = GetProcessHeap();
                                                          HeapFree(v326, 0, v775);
                                                          v327 = (unsigned int *)v764;
                                                          goto LABEL_422;
                                                        }
                                                        *((_QWORD *)v775 + 1) = v314;
                                                        v295 = 0;
                                                        memcpy_0(v314, Src, v782);
                                                        v312 = v775;
                                                      }
                                                      else
                                                      {
                                                        *v312 = 0;
                                                        *((_QWORD *)v312 + 1) = 0;
                                                        v295 = 0;
                                                      }
                                                      if ( v794 )
                                                      {
                                                        v312[4] = v761;
                                                        v315 = GetProcessHeap();
                                                        v316 = HeapAlloc(v315, 8u, Size);
                                                        v317 = v775;
                                                        if ( !v316 )
                                                        {
LABEL_411:
                                                          v775 = v317;
                                                          v788 = v74;
                                                          v774 = v76;
                                                          v771 = v165;
                                                          goto LABEL_412;
                                                        }
                                                        *((_QWORD *)v775 + 3) = v316;
                                                        v295 = 0;
                                                        memcpy_0(v316, v794, Size);
                                                        v312 = v775;
                                                      }
                                                      else
                                                      {
                                                        v312[4] = 0;
                                                        *((_QWORD *)v312 + 3) = 0;
                                                      }
                                                      if ( v776 )
                                                      {
                                                        v318 = (unsigned int)v772;
                                                        v312[8] = v772;
                                                        v319 = v318;
                                                        v778 = (LPVOID)v318;
                                                        v320 = GetProcessHeap();
                                                        v321 = HeapAlloc(v320, 8u, v319);
                                                        v317 = v775;
                                                        if ( !v321 )
                                                          goto LABEL_411;
                                                        *((_QWORD *)v775 + 5) = v321;
                                                        v295 = 0;
                                                        memcpy_0(v321, v776, (size_t)v778);
                                                        v312 = v775;
                                                      }
                                                      else
                                                      {
                                                        v312[8] = 0;
                                                        *((_QWORD *)v312 + 5) = 0;
                                                      }
                                                      v327 = v312;
                                                      v764 = (size_t)v312;
                                                      v776 = v166;
                                                      v771 = v165;
                                                      v774 = v76;
                                                      v788 = v74;
LABEL_422:
                                                      if ( v295 < 0 )
                                                      {
                                                        v296 = 0;
                                                        v773 = 0;
                                                        if ( v327 )
                                                        {
                                                          v778 = (LPVOID)*((_QWORD *)v327 + 1);
                                                          if ( v778 )
                                                          {
                                                            v328 = GetProcessHeap();
                                                            HeapFree(v328, 0, v778);
                                                            v327 = (unsigned int *)v764;
                                                            *(_QWORD *)(v764 + 8) = 0;
                                                          }
                                                          v778 = (LPVOID)*((_QWORD *)v327 + 3);
                                                          if ( v778 )
                                                          {
                                                            v329 = GetProcessHeap();
                                                            HeapFree(v329, 0, v778);
                                                            v327 = (unsigned int *)v764;
                                                            *(_QWORD *)(v764 + 24) = 0;
                                                          }
                                                          v778 = (LPVOID)*((_QWORD *)v327 + 5);
                                                          if ( v778 )
                                                          {
                                                            v330 = GetProcessHeap();
                                                            HeapFree(v330, 0, v778);
                                                            *(_QWORD *)(v764 + 40) = 0;
                                                          }
                                                          v331 = GetProcessHeap();
                                                          HeapFree(v331, 0, (LPVOID)v764);
                                                          v296 = 0;
                                                          v773 = 0;
                                                        }
                                                      }
                                                      else
                                                      {
                                                        v296 = v327;
                                                        v773 = v327;
                                                      }
LABEL_434:
                                                      v75 = v295 | 0x10000000;
                                                      v760 = v75;
                                                      if ( v75 < 0 )
                                                        goto LABEL_291;
                                                      if ( !v296
                                                        || (v794 = (void *)*((_QWORD *)v296 + 1)) == 0
                                                        || !*v296 )
                                                      {
                                                        v75 = -805306355;
                                                        goto LABEL_348;
                                                      }
                                                      v332 = *v296 - 8LL;
                                                      v781 = (LPVOID)v332;
                                                      v333 = MemoryAlloc(v332);
                                                      v780 = v333;
                                                      if ( !v333 )
                                                      {
LABEL_466:
                                                        v780 = 0;
                                                        v75 = -805306367;
                                                        goto LABEL_348;
                                                      }
                                                      v334 = 0;
                                                      v767 = 0;
                                                      v775 = (LPVOID)0x7F1137FAB69605ELL;
                                                      Src = v794;
                                                      v782 = (SIZE_T)v333;
                                                      v335 = v332 & 7;
                                                      if ( (v332 & 7) != 0 )
                                                      {
                                                        v760 = 0;
                                                        LODWORD(v772) = 0;
                                                        v336 = 0;
                                                        v337 = (unsigned __int8 *)Src;
                                                        v338 = 0;
                                                        v339 = 0;
                                                        do
                                                        {
                                                          v340 = *v337++;
                                                          v761 = 8 * v336;
                                                          if ( v336 >= 4 )
                                                            v338 |= v340 << (56 - v761);
                                                          else
                                                            v339 |= v340 << (24 - v761);
                                                          ++v336;
                                                        }
                                                        while ( (int)v336 < (int)v335 );
                                                        LODWORD(v772) = v339;
                                                        v760 = v338;
                                                        Src = v337;
                                                        v776 = v166;
                                                        v771 = v165;
                                                        v774 = v76;
                                                        v788 = v74;
                                                        v334 = v767;
                                                        v341 = v772 ^ 0x92F65A5;
                                                        v342 = v338 ^ 0x699A899C;
                                                        v343 = v772 ^ 0x92F65A5;
                                                        v344 = v338 ^ 0x699A899C;
                                                        v345 = 0;
                                                        if ( (v332 & 7) != 0 )
                                                        {
                                                          v346 = v333;
                                                          do
                                                          {
                                                            v778 = v346 + 1;
                                                            if ( v345 >= 4 )
                                                            {
                                                              v344 = __ROR4__(v344, 24);
                                                              v347 = v344;
                                                            }
                                                            else
                                                            {
                                                              v343 = __ROR4__(v343, 24);
                                                              v347 = v343;
                                                            }
                                                            *v346 = v347;
                                                            ++v345;
                                                            v346 = v778;
                                                          }
                                                          while ( (int)v345 < (int)v335 );
                                                          v782 = (SIZE_T)v778;
                                                        }
                                                        if ( v335 <= 4 )
                                                        {
                                                          v348 = 0;
                                                          if ( v335 < 4 )
                                                            v341 = v341 >> (8 * (4 - v335)) << (8 * (4 - v335));
                                                        }
                                                        else
                                                        {
                                                          v348 = v342 >> (8 * (8 - v335)) << (8 * (8 - v335));
                                                        }
                                                      }
                                                      else
                                                      {
                                                        LODWORD(v772) = 0;
                                                        v760 = -1;
                                                        v348 = 0;
                                                        v341 = 0;
                                                      }
                                                      if ( v332 >> 3 )
                                                      {
                                                        Size = 0;
                                                        v349 = HIDWORD(v775);
                                                        v350 = HIDWORD(v775) ^ 0xAB69605E;
                                                        v761 = HIDWORD(v775) ^ 0xAB69605E;
                                                        v766 = WORD2(v775);
                                                        dwBytes = 24670;
                                                        v351 = (unsigned __int8 *)Src;
                                                        v352 = (_BYTE *)v782;
                                                        v353 = v332 >> 3;
                                                        v354 = v760;
                                                        v355 = v772;
                                                        do
                                                        {
                                                          v356 = v351[3]
                                                               | ((v351[2] | ((v351[1] | (*v351 << 8)) << 8)) << 8);
                                                          v357 = v351[7]
                                                               | ((v351[6] | ((v351[5] | (v351[4] << 8)) << 8)) << 8);
                                                          v351 += 8;
                                                          v358 = v341 ^ v356;
                                                          v359 = v348 ^ v357 ^ v350 ^ v341 ^ v356;
                                                          v360 = v358
                                                               ^ (__ROR4__(v359, 22)
                                                                + v766 * __ROR4__(v359 + 1419157410, 27));
                                                          v361 = v359
                                                               ^ (WORD1(v775) * __ROR4__(v349 + v360, 9)
                                                                - __ROR4__(v360, 30));
                                                          v362 = v360 ^ (dwBytes * (v361 - v766) - (v361 >> 13));
                                                          v363 = v361
                                                               ^ (HIWORD(v775) * __ROR4__(WORD1(v775) ^ v362, 26)
                                                                - __ROR4__(v362, 30));
                                                          v364 = v362 ^ (v349 - (v363 ^ 0xAB69605E));
                                                          v365 = v363
                                                               ^ (WORD1(v775) * (v364 ^ v766))
                                                               ^ __ROR4__(v364, 6);
                                                          v366 = v364
                                                               ^ (__ROR4__(v365, 30)
                                                                + dwBytes * __ROR4__(v349 + v365, 15));
                                                          v367 = v365
                                                               ^ (HIWORD(v775) * __ROR4__(v366 + 1419157410, 14)
                                                                - __ROR4__(v366, 24));
                                                          v368 = v366
                                                               ^ __ROR4__(v367, 10)
                                                               ^ (v766 * __ROR4__(v367 ^ 0xAB69605E, 12));
                                                          v369 = v368
                                                               ^ (HIWORD(v775)
                                                                * (dwBytes
                                                                 + __ROR4__(
                                                                     ~(v367
                                                                     ^ (v368 >> 10)
                                                                     ^ (WORD1(v775) * (v368 ^ HIWORD(v775)))),
                                                                     5)));
                                                          v370 = v367
                                                               ^ (v368 >> 10)
                                                               ^ (WORD1(v775) * (v368 ^ HIWORD(v775)))
                                                               ^ (v369 - HIWORD(v775))
                                                               ^ 0xAB69605E;
                                                          v371 = v369
                                                               ^ ((v370 >> 2) + v766 * __ROR4__(HIWORD(v775) ^ v370, 30));
                                                          v372 = v370
                                                               ^ (__ROR4__(v371, 25)
                                                                + WORD1(v775) * __ROR4__(v371 - HIDWORD(v775), 6));
                                                          v373 = v371 ^ (dwBytes * (v372 ^ v766) + __ROR4__(v372, 9));
                                                          v374 = v372
                                                               ^ (__ROR4__(v373, 25)
                                                                + HIWORD(v775) * __ROR4__(WORD1(v775) ^ v373, 27));
                                                          v375 = v761 ^ v373 ^ v374;
                                                          v376 = v374 ^ (v766 * (__ROR4__(v375, 3) - WORD1(v775)));
                                                          v349 = HIDWORD(v775);
                                                          v377 = v375
                                                               ^ (dwBytes * __ROR4__(v376 - HIDWORD(v775), 1)
                                                                - __ROR4__(v376, 6));
                                                          v378 = v376
                                                               ^ (__ROR4__(v377, 18)
                                                                + HIWORD(v775) * __ROR4__(v377 - 1419157410, 29));
                                                          v379 = v377
                                                               ^ (v766 * __ROR4__(v378 - 1419157410, 17)
                                                                - __ROR4__(v378, 14));
                                                          v380 = v378 ^ (v379 >> 3) ^ (WORD1(v775) * (dwBytes ^ v379));
                                                          v341 = v355
                                                               ^ v379
                                                               ^ __ROR4__(v380, 30)
                                                               ^ (dwBytes * __ROR4__(v380 ^ HIDWORD(v775), 28));
                                                          v348 = v354 ^ v380;
                                                          v352[3] = v341;
                                                          v352[7] = v348;
                                                          v352[2] = __ROR4__(v341, 8);
                                                          v352[6] = __ROR4__(v348, 8);
                                                          v352[1] = __ROR4__(v341, 16);
                                                          v352[5] = __ROR4__(v348, 16);
                                                          *v352 = __ROR4__(v341, 24);
                                                          v352[4] = __ROR4__(v348, 24);
                                                          v355 = v356;
                                                          v354 = v357;
                                                          v352 += 8;
                                                          ++Size;
                                                          v350 = v761;
                                                        }
                                                        while ( Size < v353 );
                                                        v334 = v767;
                                                        v74 = v788;
                                                        v76 = v774;
                                                        v166 = (unsigned int *)v776;
                                                        v333 = v780;
                                                        v332 = (unsigned __int64)v781;
                                                      }
                                                      for ( i = 0; i < v332; ++i )
                                                        v334 ^= *((_BYTE *)v333 + i);
                                                      if ( v334 != *(_QWORD *)((char *)v794 + v332) )
                                                      {
                                                        MemoryFree(v333);
                                                        goto LABEL_466;
                                                      }
                                                      v165 = v771;
                                                      v766 = 0;
                                                      v764 = (size_t)v333;
                                                      if ( (unsigned int)v332 < 4 )
                                                      {
LABEL_468:
                                                        v382 = -1073741762;
LABEL_506:
                                                        v75 = v382 | 0x10000000;
                                                        goto LABEL_290;
                                                      }
                                                      v382 = RtlULongLongAdd(v333, 4, &v764);
                                                      if ( v382 >= 0 )
                                                      {
                                                        v382 = RtlUIntAdd(0, 4, &v766);
                                                        if ( v382 >= 0 )
                                                        {
                                                          if ( (unsigned int)v781 - v766 < 4 )
                                                            goto LABEL_504;
                                                          LODWORD(v772) = *(_DWORD *)v764;
                                                          v382 = RtlULongLongAdd(v764, 4, &v764);
                                                          if ( v382 < 0 )
                                                            goto LABEL_505;
                                                          v382 = RtlUIntAdd(v766, 4, &v766);
                                                          if ( v382 < 0 )
                                                            goto LABEL_505;
                                                          if ( (unsigned int)v781 - v766 < (unsigned int)v772 )
                                                            goto LABEL_504;
                                                          v382 = RtlUIntAdd(v766, (unsigned int)v772, &v766);
                                                          if ( v382 >= 0 )
                                                          {
                                                            v386 = (unsigned int)v772;
                                                            if ( (unsigned __int64)v385 + (unsigned int)v781 >= (unsigned int)v772 + v764
                                                              && (unsigned __int64)v385
                                                               + (unsigned int)v781
                                                               - v764
                                                               - (unsigned int)v772 < 8 )
                                                            {
                                                              v783 = *v385;
                                                              v781 = 0;
                                                              v782 = 0;
                                                              v774 = 0;
                                                              v761 = 0;
                                                              if ( v764 )
                                                              {
                                                                v382 = RtlULongLongAdd(v764, (unsigned int)v772, &v781);
                                                                v780 = v388;
                                                                v773 = v389;
                                                                v765 = v390;
                                                                if ( v382 < 0 )
                                                                {
LABEL_500:
                                                                  v398 = v768;
LABEL_501:
                                                                  if ( v382 < 0 || v783 == v398 )
                                                                    goto LABEL_506;
                                                                  goto LABEL_468;
                                                                }
                                                                v391 = v387;
                                                                Src = v387;
                                                                if ( v387 < v781 )
                                                                {
                                                                  while ( 1 )
                                                                  {
                                                                    v382 = RtlULongLongAdd(v391, 4, &v782);
                                                                    if ( v382 < 0 )
                                                                      goto LABEL_500;
                                                                    if ( v782 > (unsigned __int64)v781 )
                                                                      goto LABEL_488;
                                                                    v766 = 0;
                                                                    v382 = RtlUIntAdd(4, *(unsigned int *)Src, &v766);
                                                                    if ( v382 < 0 )
                                                                      goto LABEL_506;
                                                                    v382 = RtlULongLongAdd(Src, v766, &v774);
                                                                    v780 = v394;
                                                                    v773 = v393;
                                                                    v765 = v392;
                                                                    if ( v382 < 0 )
                                                                      goto LABEL_500;
                                                                    v391 = v774;
                                                                    Src = v774;
                                                                    v395 = v781;
                                                                    v780 = v394;
                                                                    v773 = v393;
                                                                    v765 = v392;
                                                                    if ( v774 > v781 )
                                                                      goto LABEL_488;
                                                                    ++v761;
                                                                    if ( v774 >= v781 )
                                                                    {
                                                                      v780 = v394;
                                                                      v773 = v393;
                                                                      v765 = v392;
                                                                      goto LABEL_490;
                                                                    }
                                                                  }
                                                                }
                                                                v395 = v781;
LABEL_490:
                                                                if ( v391 != v395 )
                                                                {
LABEL_488:
                                                                  v382 = -1073741811;
                                                                  goto LABEL_506;
                                                                }
                                                                v386 = (unsigned int)v772;
                                                              }
                                                              else
                                                              {
                                                                v382 = 0;
                                                                v780 = v385;
                                                                v773 = v384;
                                                                v765 = v383;
                                                              }
                                                              v396 = 0;
                                                              v782 = 0;
                                                              if ( (_DWORD)v386 )
                                                              {
                                                                v397 = GetProcessHeap();
                                                                v396 = HeapAlloc(v397, 8u, (unsigned int)v772);
                                                                v782 = (SIZE_T)v396;
                                                                if ( !v396 )
                                                                {
                                                                  v382 = -1073741801;
                                                                  goto LABEL_506;
                                                                }
                                                                v382 = 0;
                                                                v386 = (unsigned int)v772;
                                                              }
                                                              if ( v764 )
                                                                memcpy_0(v396, (const void *)v764, v386);
                                                              v777 = (LPVOID)v782;
                                                              v398 = v761;
                                                              v768 = v761;
                                                              goto LABEL_501;
                                                            }
LABEL_504:
                                                            v382 = -1073741762;
                                                          }
                                                        }
                                                      }
LABEL_505:
                                                      v780 = v385;
                                                      v765 = v383;
                                                      v773 = v384;
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
                                  v296 = (unsigned int *)v773;
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
  v101 = lpMem[1];
  if ( lpMem[1] )
  {
    v102 = GetProcessHeap();
    HeapFree(v102, 0, v101);
    lpMem[1] = 0;
  }
  v103 = v777;
  if ( v777 )
  {
    v104 = GetProcessHeap();
    HeapFree(v104, 0, v103);
  }
  if ( v74 )
  {
    v105 = GetProcessHeap();
    HeapFree(v105, 0, v74);
  }
  if ( v76 )
  {
    v106 = GetProcessHeap();
    HeapFree(v106, 0, v76);
  }
  if ( v75 < 0 )
  {
    v70 = (unsigned int)v770;
    v69 = (int)v770;
    goto LABEL_945;
  }
  if ( v812 )
  {
    v107 = 0;
    *(_OWORD *)v789 = 0;
    v108 = 0;
    v771 = 0;
    v109 = GetProcessHeap();
    v110 = HeapAlloc(v109, 8u, 0xA0u);
    v111 = v110;
    if ( !v110 )
    {
LABEL_579:
      v789[0] = 0;
      v449 = (void *)v789[1];
      if ( v789[1] )
      {
        v450 = GetProcessHeap();
        HeapFree(v450, 0, v449);
        v789[1] = 0;
      }
      if ( v108 )
      {
        v451 = GetProcessHeap();
        HeapFree(v451, 0, (LPVOID)v108);
      }
      if ( v111 )
      {
        v452 = GetProcessHeap();
        HeapFree(v452, 0, v111);
      }
      if ( v107 )
      {
        v453 = GetProcessHeap();
        HeapFree(v453, 0, v107);
      }
      goto LABEL_587;
    }
    *v110 = `WarbirdUmGetDecryptionCipher'::`2'::DecryptionCipher;
    v110[1] = xmmword_18012E5A0;
    v110[2] = xmmword_18012E5B0;
    v110[3] = xmmword_18012E5C0;
    v110[4] = xmmword_18012E5D0;
    v110[5] = xmmword_18012E5E0;
    v110[6] = xmmword_18012E5F0;
    v110[7] = xmmword_18012E600;
    v110[8] = xmmword_18012E610;
    v110[9] = xmmword_18012E620;
    v112 = GetProcessHeap();
    v113 = HeapAlloc(v112, 8u, 8u);
    v114 = v113;
    if ( !v113 )
    {
      v108 = 0;
      goto LABEL_579;
    }
    *v113 = `WarbirdUmGetDecryptionKey'::`2'::nDecryptionKey;
    v778 = (LPVOID)__rdtsc();
    dwBytes_4 = 0;
    v761 = 0;
    if ( (int)RtlUIntAdd(4, 4, &v761) < 0 )
      goto LABEL_577;
    if ( (int)RtlUIntAdd(0, v761, &dwBytes_4) < 0 )
    {
      v107 = v114;
      v108 = v435;
      goto LABEL_579;
    }
    v761 = v435;
    if ( (int)RtlUIntAdd(v436, 160, &v761) < 0 )
      goto LABEL_577;
    v437 = RtlUIntAdd(dwBytes_4, v761, &dwBytes_4);
    if ( (v439 | v437) < 0 )
      goto LABEL_577;
    v761 = 0;
    if ( (int)RtlUIntAdd(v438, 8, &v761) < 0 )
      goto LABEL_577;
    v440 = RtlUIntAdd(dwBytes_4, v761, &dwBytes_4);
    if ( (v442 | v440) < 0
      || (v761 = 0, (int)RtlUIntAdd(v441, 8, &v761) < 0)
      || (v443 = RtlUIntAdd(dwBytes_4, v761, &dwBytes_4), (v444 | v443) < 0)
      || (HIDWORD(v789[0]) = dwBytes_4,
          v445 = dwBytes_4,
          v446 = GetProcessHeap(),
          v447 = HeapAlloc(v446, 8u, v445),
          (v448 = v447) == 0) )
    {
LABEL_577:
      v107 = v114;
      goto LABEL_578;
    }
    v789[1] = (size_t)v447;
    LODWORD(v789[0]) = 0;
    LODWORD(v791) = 0;
    v790 = 0;
    pcchLength = (size_t)v447;
    v768 = 8;
    v107 = v114;
    if ( (int)RtlULongLongAdd(v447, 4, &v791) < 0 || (unsigned __int64)(v448 + 2) > v789[1] + HIDWORD(v789[0]) )
    {
      v108 = v455;
      goto LABEL_579;
    }
    *v448 = v454;
    *(_DWORD *)v791 = v454;
    v457 = v768;
    v458 = ++LODWORD(v789[0]);
    LODWORD(v791) = 0;
    v790 = 0;
    if ( v111 )
    {
      if ( !v456 )
        goto LABEL_578;
    }
    else if ( v456 )
    {
LABEL_592:
      v108 = 0;
      goto LABEL_579;
    }
    v459 = (unsigned int *)v789[1];
    if ( v789[1] )
    {
      pcchLength = v789[1];
      v461 = 0;
      if ( v458 )
      {
        do
        {
          v761 = 0;
          if ( (int)RtlUIntAdd(4, *v459, &v761) < 0 || (int)RtlULongLongAdd(v462, v761, &pcchLength) < 0 )
            goto LABEL_578;
          ++v461;
          v459 = (unsigned int *)pcchLength;
        }
        while ( v461 < v463 );
      }
      if ( (int)RtlULongLongAdd(v459, 4, &v791) < 0 || (unsigned __int64)v464 + v465 + 4 > v789[1] + HIDWORD(v789[0]) )
        goto LABEL_578;
      *v464 = v465;
      if ( v111 )
        memcpy_0(v791, v111, v465);
      v460 = 4;
    }
    else
    {
      v761 = 0;
      if ( (int)RtlUIntAdd(4, v456, &v761) < 0 || (int)RtlUIntAdd(HIDWORD(v789[0]), v761, (char *)v789 + 4) < 0 )
        goto LABEL_578;
    }
    v466 = ++LODWORD(v789[0]);
    LODWORD(v791) = 0;
    v790 = 0;
    if ( v107 )
    {
      if ( !v457 )
        goto LABEL_578;
    }
    else if ( v457 )
    {
      goto LABEL_592;
    }
    v467 = (unsigned int *)v789[1];
    if ( v789[1] )
    {
      pcchLength = v789[1];
      if ( v466 )
      {
        do
        {
          v761 = 0;
          if ( (int)RtlUIntAdd(4, *v467, &v761) < 0 || (int)RtlULongLongAdd(v469, v761, &pcchLength) < 0 )
            goto LABEL_578;
          v467 = (unsigned int *)pcchLength;
        }
        while ( v471 + 1 < v470 );
      }
      if ( (int)RtlULongLongAdd(v467, 4, &v791) < 0 || (unsigned __int64)v472 + v457 + 4 > v789[1] + HIDWORD(v789[0]) )
        goto LABEL_578;
      *v472 = v457;
      if ( v107 )
      {
        memcpy_0(v791, v107, v457);
        v468 = 4;
      }
    }
    else
    {
      v761 = 0;
      if ( (int)RtlUIntAdd(v460, v457, &v761) < 0 || (int)RtlUIntAdd(HIDWORD(v789[0]), v761, (char *)v789 + 4) < 0 )
        goto LABEL_578;
    }
    v473 = ++LODWORD(v789[0]);
    LODWORD(v791) = 0;
    v790 = 0;
    v474 = (unsigned int *)v789[1];
    if ( !v789[1] )
    {
      v761 = 0;
      if ( (int)RtlUIntAdd(v468, 8, &v761) < 0 || (int)RtlUIntAdd(HIDWORD(v789[0]), v761, (char *)v789 + 4) < 0 )
        goto LABEL_578;
LABEL_634:
      ++LODWORD(v789[0]);
      v761 = 0;
      if ( (int)RtlUIntAdd(v475, v475, &v761) < 0 )
        goto LABEL_578;
      v768 = v761;
      v761 = 0;
      if ( (int)RtlUIntAdd(v480, 8, &v761) < 0 || (int)RtlUIntAdd(v481, v761, &v768) < 0 )
        goto LABEL_578;
      v761 = 0;
      v482 = v768;
      dwBytes = v768;
      v770 = 0;
      v778 = (LPVOID)__rdtsc();
      v797 = 8;
      v483 = RtlUIntAdd(8, HIDWORD(v789[0]), &v797);
      if ( v483 < 0 )
      {
        v774 = v107;
        v777 = v111;
      }
      else
      {
        v486 = (v797 + 7) & 0xFFFFFFF8;
        if ( v486 < v797 )
        {
          v108 = (unsigned int)v484;
          goto LABEL_579;
        }
        v797 = (v797 + 7) & 0xFFFFFFF8;
        v487 = v486;
        v488 = GetProcessHeap();
        v489 = (char *)HeapAlloc(v488, 8u, v487);
        v490 = v489;
        if ( !v489 )
          goto LABEL_927;
        v777 = v111;
        v774 = v107;
        dwBytes = v482;
        v764 = (size_t)v489;
        *(_DWORD *)v489 = v789[0];
        v768 = RtlULongLongAdd(v489, 4, &v764);
        if ( v768 < 0
          || (v492 = v764, *(_DWORD *)v764 = HIDWORD(v789[0]), v768 = RtlULongLongAdd(v492, v491, &v764), v768 < 0) )
        {
          v777 = v111;
          v774 = v107;
          dwBytes = v482;
          v493 = GetProcessHeap();
          HeapFree(v493, 0, v490);
          v484 = v770;
          v483 = v768;
          v485 = (unsigned int)v770;
        }
        else
        {
          *(_QWORD *)&v490[v797 - 8] = v778;
          memcpy_0((void *)v764, (const void *)v789[1], HIDWORD(v789[0]));
          v484 = v490;
          v770 = v490;
          v485 = v797;
          v483 = v768;
        }
      }
      v494 = 0;
      v794 = 0;
      v495 = 0;
      v776 = 0;
      v773 = 0;
      v765 = 0;
      v496 = v483 | 0x10000000;
      if ( v496 < 0 )
      {
        v769 = v496;
        v574 = 0;
        goto LABEL_902;
      }
      if ( !v484 )
        goto LABEL_578;
      v782 = v485;
      if ( !v485 || (v795 = v485 + 8LL, v497 = MemoryAlloc(v795), (Size = (SIZE_T)v497) == 0) )
      {
        v769 = -805306367;
        v548 = v770;
        v574 = 0;
        goto LABEL_904;
      }
      v781 = 0;
      v498 = 0;
      v767 = 0;
      v499 = 0;
      v500 = v782;
      if ( v782 )
      {
        do
          v498 ^= *((_BYTE *)v770 + v499++);
        while ( v499 < v782 );
        v767 = v498;
      }
      v780 = (LPVOID)0xC81ECB17B1B54A58LL;
      pcchLength = (size_t)v770;
      Src = v497;
      v501 = v782 & 7;
      if ( (v782 & 7) != 0 )
      {
        v768 = 0;
        LODWORD(v772) = 0;
        v502 = 0;
        v503 = (unsigned __int8 *)v770;
        v504 = 0;
        v505 = 0;
        do
        {
          v506 = *v503++;
          v768 = 8 * v502;
          if ( v502 >= 4 )
            v504 |= v506 << (56 - v768);
          else
            v505 |= v506 << (24 - v768);
          ++v502;
        }
        while ( (int)v502 < (int)v501 );
        LODWORD(v772) = v505;
        v768 = v504;
        pcchLength = (size_t)v503;
        v774 = v107;
        v777 = v111;
        v494 = 0;
        v507 = v772 ^ 0xB17A307A;
        v508 = v504 ^ 0x42F6B18D;
        v509 = v772 ^ 0xB17A307A;
        v510 = v504 ^ 0x42F6B18D;
        dwBytes_4 = 0;
        if ( (v782 & 7) != 0 )
        {
          v511 = Src;
          do
          {
            v778 = v511 + 1;
            if ( dwBytes_4 >= 4 )
            {
              v510 = __ROR4__(v510, 24);
              v512 = v510;
            }
            else
            {
              v509 = __ROR4__(v509, 24);
              v512 = v509;
            }
            *v511 = v512;
            ++dwBytes_4;
            v511 = v778;
          }
          while ( (int)dwBytes_4 < (int)v501 );
          Src = v778;
        }
        if ( v501 <= 4 )
        {
          v513 = 0;
          if ( v501 < 4 )
            v507 = v507 >> (8 * (4 - v501)) << (8 * (4 - v501));
        }
        else
        {
          v513 = v508 >> (8 * (8 - v501)) << (8 * (8 - v501));
        }
      }
      else
      {
        v507 = 0;
        v513 = -1;
        LODWORD(v772) = 0;
        v768 = 0;
      }
      if ( v500 >> 3 )
      {
        v790 = 0;
        v514 = 19032;
        dwBytes_4 = 19032;
        v769 = WORD1(v780);
        v766 = HIWORD(v780);
        v515 = (unsigned __int8 *)pcchLength;
        v516 = Src;
        v517 = v500 >> 3;
        v518 = v768;
        v519 = v772;
        v520 = WORD2(v780);
        do
        {
          v521 = v515[3] | ((v515[2] | ((v515[1] | (*v515 << 8)) << 8)) << 8);
          v522 = v515[7] | ((v515[6] | ((v515[5] | (v515[4] << 8)) << 8)) << 8);
          v523 = v513 ^ v522;
          v515 += 8;
          v524 = v507 ^ v521 ^ HIDWORD(v780) ^ ((v513 ^ v522) - v514);
          v525 = v523 ^ (__ROR4__(v524, 7) + WORD1(v780) * __ROR4__(HIDWORD(v780) ^ v524, 15));
          v526 = v524 ^ (v520 * __ROR4__(v525 - 1313519016, 9) - __ROR4__(v525, 10));
          v527 = v525 ^ (__ROR4__(v526, 27) + HIWORD(v780) * __ROR4__(v520 ^ v526, 28));
          v528 = v526 ^ (HIDWORD(v780) - (v527 ^ 0xB1B54A58));
          v529 = v527 ^ (WORD1(v780) * (v528 - dwBytes_4) - (v528 >> 6));
          v530 = v528 ^ (dwBytes_4 * (v520 ^ __ROR4__(v529, 15)));
          v531 = v529 ^ (v520 * (v766 + __ROR4__(~v530, 3)));
          v532 = v531
               ^ (v769 * (v766 ^ v530 ^ (v531 - HIDWORD(v780) - dwBytes_4)))
               ^ __ROR4__(v530 ^ (v531 - HIDWORD(v780) - dwBytes_4), 10);
          v533 = v530 ^ (v531 - HIDWORD(v780) - dwBytes_4) ^ __ROR4__(v532, 3) ^ (v520 * __ROR4__(dwBytes_4 ^ v532, 26));
          v534 = v532 ^ (dwBytes_4 * (__ROR4__(v533, 15) - HIWORD(v780)));
          v535 = v533
               ^ (dwBytes_4 * (v766 ^ v534))
               ^ ((v534 ^ (v534 >> 14)) >> 1)
               ^ (dwBytes_4 * ((8 * (v534 - v520)) | ((unsigned __int64)(v534 - v520) >> 29)));
          v536 = v534 ^ (WORD1(v780) * (v535 - v520) - (v535 >> 13));
          v537 = v535 ^ __ROR4__(v536, 11) ^ (v520 * __ROR4__(-1313519016 - v536, 9));
          v538 = v536 ^ (v537 + 1313519016 - HIWORD(v780));
          v539 = v537 ^ (dwBytes_4 * (v769 ^ v538) - __ROR4__(v538, 7));
          v540 = v538 ^ (WORD1(v780) * __ROR4__(HIWORD(v780) ^ v539, 28) - __ROR4__(v539, 16));
          v541 = v539 ^ (__ROR4__(v540, 4) + v520 * __ROR4__(-1313519016 - v540, 10));
          v542 = v540 ^ __ROR4__(v541, 9) ^ (HIWORD(v780) * __ROR4__(v541 + 1313519016, 4));
          v543 = v541 ^ (dwBytes_4 * __ROR4__(HIDWORD(v780) ^ v542, 24) - __ROR4__(v542, 30));
          v544 = v542 ^ (WORD1(v780) * __ROR4__(HIDWORD(v780) - v543, 11) - __ROR4__(v543, 12));
          v545 = v543 ^ (v544 >> 8) ^ (v520 * (WORD1(v780) ^ v544));
          v507 = v545 ^ v519;
          v513 = v545 ^ v518 ^ HIDWORD(v780) ^ v544 ^ 0xB1B54A58;
          v516[3] = v545 ^ v519;
          v516[7] = v513;
          v516[2] = __ROR4__(v545 ^ v519, 8);
          v516[6] = __ROR4__(v513, 8);
          v516[1] = __ROR4__(v545 ^ v519, 16);
          v516[5] = __ROR4__(v513, 16);
          *v516 = __ROR4__(v545 ^ v519, 24);
          v516[4] = __ROR4__(v513, 24);
          v519 = v521;
          v518 = v522;
          v516 += 8;
          ++v790;
          v514 = dwBytes_4;
        }
        while ( v790 < v517 );
        v498 = v767;
        v75 = v760;
        v111 = v777;
        v107 = v774;
        v495 = (unsigned int *)v776;
        v494 = (unsigned int *)v776;
        v500 = v782;
      }
      *(_QWORD *)(Size + v500) = v498;
      v546 = GetProcessHeap();
      v547 = HeapAlloc(v546, 8u, 0x30u);
      v777 = v547;
      if ( !v547 )
      {
        dwBytes_4 = -1073741801;
        v548 = v770;
        goto LABEL_692;
      }
      v549 = v795;
      *v547 = v795;
      v550 = GetProcessHeap();
      v551 = HeapAlloc(v550, 8u, v549);
      v548 = v770;
      if ( v551 )
      {
        *((_QWORD *)v777 + 1) = v551;
        memcpy_0(v551, (const void *)Size, (unsigned int)v795);
        *((_DWORD *)v777 + 4) = 160;
        v552 = GetProcessHeap();
        v553 = HeapAlloc(v552, 8u, 0xA0u);
        v554 = v777;
        if ( v553 )
        {
          *((_QWORD *)v777 + 3) = v553;
          *v553 = `WarbirdUmGetEncryptionCipher'::`2'::EncryptionCipher;
          v553[1] = xmmword_18012E4F0;
          v553[2] = xmmword_18012E500;
          v553[3] = xmmword_18012E510;
          v553[4] = xmmword_18012E520;
          v553[5] = xmmword_18012E530;
          v553[6] = xmmword_18012E540;
          v553[7] = xmmword_18012E550;
          v553[8] = xmmword_18012E560;
          v553[9] = xmmword_18012E570;
          v554[8] = 8;
          v555 = GetProcessHeap();
          v556 = HeapAlloc(v555, 8u, 8u);
          if ( v556 )
          {
            v562 = v777;
            *((_QWORD *)v777 + 5) = v556;
            *v556 = `WarbirdUmGetEncryptionKey'::`2'::nEncryptionKey;
            v781 = v562;
            dwBytes_4 = 0;
            v770 = v548;
            goto LABEL_691;
          }
          v554 = v777;
        }
        v777 = v554;
      }
      dwBytes_4 = -1073741801;
      v770 = v548;
      v557 = v777;
      v778 = (LPVOID)*((_QWORD *)v777 + 1);
      if ( v778 )
      {
        v558 = GetProcessHeap();
        HeapFree(v558, 0, v778);
        v557 = v777;
        *((_QWORD *)v777 + 1) = 0;
      }
      v778 = (LPVOID)v557[3];
      if ( v778 )
      {
        v559 = GetProcessHeap();
        HeapFree(v559, 0, v778);
        v557 = v777;
        *((_QWORD *)v777 + 3) = 0;
      }
      v778 = (LPVOID)v557[5];
      if ( v778 )
      {
        v560 = GetProcessHeap();
        HeapFree(v560, 0, v778);
        *((_QWORD *)v777 + 5) = 0;
      }
      v561 = GetProcessHeap();
      HeapFree(v561, 0, v777);
      if ( (dwBytes_4 & 0x80000000) != 0 )
      {
LABEL_692:
        v563 = GetProcessHeap();
        HeapFree(v563, 0, (LPVOID)Size);
        v564 = v781;
        if ( v781 )
        {
          v778 = (LPVOID)*((_QWORD *)v781 + 1);
          if ( v778 )
          {
            v565 = GetProcessHeap();
            HeapFree(v565, 0, v778);
            v564 = v781;
            *((_QWORD *)v781 + 1) = 0;
          }
          v778 = (LPVOID)v564[3];
          if ( v778 )
          {
            v566 = GetProcessHeap();
            HeapFree(v566, 0, v778);
            v564 = v781;
            *((_QWORD *)v781 + 3) = 0;
          }
          v778 = (LPVOID)v564[5];
          if ( v778 )
          {
            v567 = GetProcessHeap();
            HeapFree(v567, 0, v778);
            *((_QWORD *)v781 + 5) = 0;
          }
          v568 = GetProcessHeap();
          HeapFree(v568, 0, v781);
        }
        if ( (dwBytes_4 & 0x80000000) != 0 )
        {
          v769 = dwBytes_4 | 0x10000000;
          goto LABEL_708;
        }
        LODWORD(v772) = 0;
        v766 = 4;
        v769 = RtlUIntAdd(4, *v494, &v766);
        if ( v769 < 0
          || (v769 = RtlUIntAdd(v766, v569, &v766), v769 < 0)
          || (v790 = (SIZE_T)(v494 + 4), v769 = RtlUIntAdd(v766, v494[4], &v766), v769 < 0)
          || (v769 = RtlUIntAdd(v766, v570, &v766), v769 < 0)
          || (v782 = (SIZE_T)(v494 + 8), v769 = RtlUIntAdd(v766, v494[8], &v766), v769 < 0) )
        {
          v770 = v548;
        }
        else
        {
          v571 = v766;
          v572 = GetProcessHeap();
          v573 = HeapAlloc(v572, 8u, v571);
          v774 = v573;
          v548 = v770;
          if ( !v573 )
          {
            v769 = -805306345;
LABEL_708:
            v574 = v765;
            goto LABEL_903;
          }
          v777 = v573;
          *v573 = *v494;
          v769 = RtlULongLongAdd(v573, 4, &v777);
          if ( v769 < 0 )
          {
            dwBytes = v576;
            v774 = v575;
          }
          else
          {
            memcpy_0(v777, *((const void **)v494 + 1), *v494);
            v769 = RtlULongLongAdd(v777, *v494, &v777);
            if ( v769 >= 0 )
            {
              v577 = v777;
              *(_DWORD *)v777 = *(_DWORD *)v790;
              v769 = RtlULongLongAdd(v577, 4, &v777);
              if ( v769 >= 0 )
              {
                memcpy_0(v777, *((const void **)v494 + 3), *v578);
                v769 = RtlULongLongAdd(v777, *(unsigned int *)v790, &v777);
                if ( v769 >= 0 )
                {
                  v579 = v777;
                  *(_DWORD *)v777 = *(_DWORD *)v782;
                  v769 = RtlULongLongAdd(v579, 4, &v777);
                  if ( v769 >= 0 )
                  {
                    memcpy_0(v777, *((const void **)v494 + 5), *v580);
                    v581 = RtlULongLongAdd(v777, *(unsigned int *)v782, &v777);
                    v769 = v581;
                    if ( v581 >= 0 )
                    {
                      v794 = v774;
                      LODWORD(v772) = v766;
LABEL_722:
                      v583 = v581 | 0x10000000;
                      if ( v583 < 0 )
                        goto LABEL_726;
                      v802 = 8;
                      v584 = RtlUIntAdd(8, dwBytes, &v802);
                      v583 = v585 | v584;
                      if ( v583 < 0 )
                        goto LABEL_726;
                      v586 = (v802 + 7) & 0xFFFFFFF8;
                      if ( (unsigned int)v586 < v802 )
                      {
                        v583 = -1073741675;
LABEL_726:
                        v769 = v583;
LABEL_764:
                        v574 = v765;
LABEL_902:
                        v548 = v770;
LABEL_903:
                        if ( !v548 )
                        {
LABEL_905:
                          if ( v494 )
                          {
                            v713 = (void *)*((_QWORD *)v494 + 1);
                            if ( v713 )
                            {
                              v714 = GetProcessHeap();
                              HeapFree(v714, 0, v713);
                              *((_QWORD *)v494 + 1) = 0;
                            }
                            v715 = (void *)*((_QWORD *)v494 + 3);
                            if ( v715 )
                            {
                              v716 = GetProcessHeap();
                              HeapFree(v716, 0, v715);
                              *((_QWORD *)v494 + 3) = 0;
                            }
                            v717 = (void *)*((_QWORD *)v494 + 5);
                            if ( v717 )
                            {
                              v718 = GetProcessHeap();
                              HeapFree(v718, 0, v717);
                              *((_QWORD *)v494 + 5) = 0;
                            }
                            v719 = GetProcessHeap();
                            HeapFree(v719, 0, v494);
                          }
                          v720 = v794;
                          if ( v794 )
                          {
                            v721 = GetProcessHeap();
                            HeapFree(v721, 0, v720);
                          }
                          if ( v495 )
                          {
                            v722 = GetProcessHeap();
                            HeapFree(v722, 0, v495);
                          }
                          v723 = v773;
                          if ( v773 )
                          {
                            v724 = (void *)*((_QWORD *)v773 + 1);
                            if ( v724 )
                            {
                              v725 = GetProcessHeap();
                              HeapFree(v725, 0, v724);
                              v723[1] = 0;
                            }
                            v726 = (void *)v723[3];
                            if ( v726 )
                            {
                              v727 = GetProcessHeap();
                              HeapFree(v727, 0, v726);
                              v723[3] = 0;
                            }
                            v728 = (void *)v723[5];
                            if ( v728 )
                            {
                              v729 = GetProcessHeap();
                              HeapFree(v729, 0, v728);
                              v723[5] = 0;
                            }
                            v730 = GetProcessHeap();
                            HeapFree(v730, 0, v723);
                          }
                          if ( v574 )
                          {
                            v731 = GetProcessHeap();
                            HeapFree(v731, 0, v574);
                          }
LABEL_927:
                          if ( v769 >= 0 )
                          {
                            v108 = (size_t)v771;
                            if ( v761 )
                            {
                              if ( v771 )
                              {
                                v790 = (SIZE_T)v771;
                                if ( (int)RtlULongLongAdd(v771, 4, &v790) >= 0 )
                                {
                                  v734 = (int *)v790;
                                  if ( !*(_DWORD *)v108 )
                                    v734 = 0;
                                  if ( *(_DWORD *)v108 == (_DWORD)v733 && *v734 >= 0 && v732 > 1 )
                                  {
                                    v735 = v108;
                                    v764 = v108;
                                    while ( (int)RtlULongLongAdd(v735, v733, &v764) >= 0
                                         && (int)RtlULongLongAdd(v764, v736, &v764) >= 0 )
                                    {
                                      v735 = v764;
                                      if ( v737 != -1 )
                                      {
                                        RtlULongLongAdd(v764, v733, &v764);
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
                        v712 = GetProcessHeap();
                        HeapFree(v712, 0, v548);
                        goto LABEL_905;
                      }
                      v811 = (v802 + 7) & 0xFFFFFFF8;
                      v583 = RtlUIntAdd(v586, 8, &v811);
                      if ( v583 < 0 )
                        goto LABEL_726;
                      v777 = v111;
                      v774 = v107;
                      v770 = v548;
                      v775 = v494;
                      v768 = 0;
                      v587 = v789[1];
                      if ( !v789[1] )
                        goto LABEL_736;
                      v775 = v494;
                      v770 = v548;
                      v774 = v107;
                      v777 = v111;
                      if ( LODWORD(v789[0]) <= 1 )
                        goto LABEL_736;
                      v764 = v789[1];
                      do
                      {
                        v583 = RtlULongLongAdd(v587, 4, &v764);
                        if ( v583 < 0 )
                          goto LABEL_726;
                        v583 = RtlULongLongAdd(v764, v588, &v764);
                        if ( v583 < 0 )
                          goto LABEL_726;
                        v587 = v764;
                      }
                      while ( v589 == -1 );
                      v590 = *(_DWORD *)v764;
                      v583 = RtlULongLongAdd(v764, 4, &v764);
                      if ( v583 < 0 )
                        goto LABEL_726;
                      v591 = v789[1];
                      if ( !v789[1] || LODWORD(v789[0]) <= 2 )
                      {
LABEL_736:
                        v583 = -1073741811;
                        goto LABEL_726;
                      }
                      v764 = v789[1];
                      do
                      {
                        v583 = RtlULongLongAdd(v591, 4, &v764);
                        if ( v583 < 0 )
                          goto LABEL_726;
                        v583 = RtlULongLongAdd(v764, v595, &v764);
                        if ( v583 < 0 )
                          goto LABEL_726;
                        v591 = v764;
                      }
                      while ( (unsigned int)(v596 + 1) < 2 );
                      v583 = RtlULongLongAdd(v764, 4, &v764);
                      if ( v583 < 0 )
                        goto LABEL_726;
                      v768 = v597;
                      dwBytes_4 = v598;
                      v583 = RtlUIntAdd(v598, v811, &dwBytes_4);
                      if ( v583 < 0 )
                        goto LABEL_726;
                      v583 = RtlUIntAdd(dwBytes_4, v599, &dwBytes_4);
                      if ( v583 < 0 )
                        goto LABEL_726;
                      v583 = RtlUIntAdd(dwBytes_4, v590, &dwBytes_4);
                      if ( v583 < 0 )
                        goto LABEL_726;
                      v583 = RtlUIntAdd(dwBytes_4, v600, &dwBytes_4);
                      if ( v583 < 0 )
                        goto LABEL_726;
                      v583 = RtlUIntAdd(dwBytes_4, v601, &dwBytes_4);
                      if ( v583 < 0 )
                        goto LABEL_726;
                      v768 = dwBytes_4;
                      if ( dwBytes_4 > 0x400000 )
                      {
                        v583 = -2147418113;
                        goto LABEL_726;
                      }
                      v592 = dwBytes_4;
                      v593 = GetProcessHeap();
                      v594 = (unsigned int *)HeapAlloc(v593, 8u, v592);
                      v495 = v594;
                      if ( !v594 )
                      {
                        v769 = -805306345;
                        v574 = 0;
                        goto LABEL_902;
                      }
                      v849 = 0;
                      v850 = 0;
                      hModule = 0;
                      if ( !v794 )
                      {
                        v769 = -2147024809;
                        goto LABEL_764;
                      }
                      *(_QWORD *)&v849 = v794;
                      LODWORD(v850) = v772;
                      *((_QWORD *)&v849 + 1) = v594;
                      *(_QWORD *)((char *)&v850 + 4) = (unsigned int)v768;
                      if ( GetModuleHandleExW(1u, L"ntdll.dll", &hModule)
                        && (v603 = GetProcAddress(hModule, "NtQuerySystemInformation")) != 0 )
                      {
                        v583 = ((__int64 (__fastcall *)(__int64, __int128 *))v603)(134, &v849) | 0x10000000;
                        if ( v583 >= 0 )
                        {
                          v604 = DWORD1(v850);
                          goto LABEL_767;
                        }
                      }
                      else
                      {
                        v583 = GetLastError();
                        v602 = v583 < 0;
                        if ( v583 > 0 )
                        {
                          v583 = (unsigned __int16)v583 | 0x80070000;
                          v602 = v583 < 0;
                        }
                        if ( !v602 )
                        {
                          v769 = -2147467259;
                          goto LABEL_764;
                        }
                      }
                      if ( v583 == -805306333 )
                      {
                        v769 = -2147024774;
                        goto LABEL_764;
                      }
                      if ( v583 < 0 )
                        goto LABEL_726;
                      v604 = v768;
LABEL_767:
                      dwBytes = 0;
                      v788 = v495;
                      if ( v604 < 4 )
                      {
LABEL_768:
                        v769 = -805306306;
                        goto LABEL_764;
                      }
                      v605 = *v495;
                      v783 = *v495;
                      v606 = RtlULongLongAdd(v495, 4, &v788);
                      if ( v606 < 0 )
                        goto LABEL_820;
                      v606 = RtlUIntAdd(0, v607, &dwBytes);
                      if ( v606 < 0 )
                        goto LABEL_820;
                      if ( v608 - dwBytes < (unsigned int)v605 )
                        goto LABEL_768;
                      v782 = (SIZE_T)v788;
                      v790 = v605;
                      v606 = RtlULongLongAdd(v788, (unsigned int)v605, &v788);
                      if ( v606 < 0 )
                        goto LABEL_820;
                      v606 = RtlUIntAdd(dwBytes, (unsigned int)v605, &dwBytes);
                      if ( v606 < 0 )
                        goto LABEL_820;
                      if ( v609 - dwBytes < (unsigned int)v610 )
                        goto LABEL_768;
                      v768 = *(_DWORD *)v788;
                      v606 = RtlULongLongAdd(v788, v610, &v788);
                      if ( v606 < 0 )
                        goto LABEL_820;
                      v606 = RtlUIntAdd(dwBytes, v611, &dwBytes);
                      if ( v606 < 0 )
                        goto LABEL_820;
                      if ( v612 - dwBytes < (unsigned int)v613 )
                        goto LABEL_768;
                      Src = v788;
                      pcchLength = v613;
                      v606 = RtlULongLongAdd(v788, (unsigned int)v613, &v788);
                      if ( v606 < 0 )
                        goto LABEL_820;
                      v606 = RtlUIntAdd(dwBytes, v614, &dwBytes);
                      if ( v606 < 0 )
                        goto LABEL_820;
                      if ( v615 - dwBytes < v616 )
                        goto LABEL_768;
                      LODWORD(v772) = *(_DWORD *)v788;
                      v606 = RtlULongLongAdd(v788, 4, &v788);
                      if ( v606 < 0 )
                        goto LABEL_820;
                      v606 = RtlUIntAdd(dwBytes, 4, &dwBytes);
                      if ( v606 < 0 )
                        goto LABEL_820;
                      if ( v617 - dwBytes < v618 )
                        goto LABEL_768;
                      v606 = RtlUIntAdd(dwBytes, v618, &dwBytes);
                      if ( v606 < 0 )
                      {
LABEL_820:
                        v776 = v495;
                        v548 = v770;
                        v638 = (unsigned int *)v773;
                        goto LABEL_821;
                      }
                      if ( v619 != dwBytes || (unsigned int)(v620 + v621 + v605) + 12LL != v619 )
                        goto LABEL_768;
                      v622 = GetProcessHeap();
                      v623 = HeapAlloc(v622, 8u, 0x30u);
                      v624 = v623;
                      v780 = v623;
                      v548 = v770;
                      if ( !v623 )
                      {
                        v773 = 0;
                        v769 = -805306345;
                        v574 = 0;
                        goto LABEL_903;
                      }
                      v777 = v111;
                      v774 = v107;
                      v775 = v494;
                      v764 = 0;
                      if ( v782 )
                      {
                        *(_DWORD *)v623 = v783;
                        v625 = GetProcessHeap();
                        v626 = HeapAlloc(v625, 8u, v790);
                        v627 = v780;
                        if ( !v626 )
                        {
LABEL_800:
                          dwBytes_4 = -1073741801;
                          v776 = v495;
                          v778 = (LPVOID)v627[1];
                          if ( v778 )
                          {
                            v633 = GetProcessHeap();
                            HeapFree(v633, 0, v778);
                            v627 = v780;
                            *((_QWORD *)v780 + 1) = 0;
                          }
                          v778 = (LPVOID)v627[3];
                          if ( v778 )
                          {
                            v634 = GetProcessHeap();
                            HeapFree(v634, 0, v778);
                            v627 = v780;
                            *((_QWORD *)v780 + 3) = 0;
                          }
                          v778 = (LPVOID)v627[5];
                          if ( v778 )
                          {
                            v635 = GetProcessHeap();
                            HeapFree(v635, 0, v778);
                            *((_QWORD *)v780 + 5) = 0;
                          }
                          v636 = GetProcessHeap();
                          HeapFree(v636, 0, v780);
                          v637 = (unsigned int *)v764;
                          goto LABEL_810;
                        }
                        *((_QWORD *)v780 + 1) = v626;
                        dwBytes_4 = 0;
                        memcpy_0(v626, (const void *)v782, v790);
                        v624 = v780;
                      }
                      else
                      {
                        *(_DWORD *)v623 = 0;
                        v623[1] = 0;
                        dwBytes_4 = 0;
                      }
                      if ( Src )
                      {
                        v624[4] = v768;
                        v628 = GetProcessHeap();
                        v629 = HeapAlloc(v628, 8u, pcchLength);
                        v627 = v780;
                        if ( !v629 )
                        {
LABEL_799:
                          v777 = v111;
                          v774 = v107;
                          v770 = v548;
                          v775 = v494;
                          v780 = v627;
                          goto LABEL_800;
                        }
                        *((_QWORD *)v780 + 3) = v629;
                        dwBytes_4 = 0;
                        memcpy_0(v629, Src, pcchLength);
                        v624 = v780;
                      }
                      else
                      {
                        v624[4] = 0;
                        *((_QWORD *)v624 + 3) = 0;
                      }
                      if ( v788 )
                      {
                        v630 = (unsigned int)v772;
                        v624[8] = v772;
                        v790 = v630;
                        v631 = GetProcessHeap();
                        v632 = HeapAlloc(v631, 8u, v790);
                        v627 = v780;
                        if ( !v632 )
                          goto LABEL_799;
                        *((_QWORD *)v780 + 5) = v632;
                        dwBytes_4 = 0;
                        memcpy_0(v632, v788, v790);
                        v624 = v780;
                      }
                      else
                      {
                        v624[8] = 0;
                        *((_QWORD *)v624 + 5) = 0;
                      }
                      v637 = v624;
                      v764 = (size_t)v624;
                      v776 = v495;
                      v775 = v494;
                      v770 = v548;
                      v774 = v107;
                      v777 = v111;
LABEL_810:
                      v606 = dwBytes_4;
                      if ( (dwBytes_4 & 0x80000000) != 0 )
                      {
                        v638 = 0;
                        v773 = 0;
                        if ( v637 )
                        {
                          v778 = (LPVOID)*((_QWORD *)v637 + 1);
                          if ( v778 )
                          {
                            v639 = GetProcessHeap();
                            HeapFree(v639, 0, v778);
                            v637 = (unsigned int *)v764;
                            *(_QWORD *)(v764 + 8) = 0;
                          }
                          v778 = (LPVOID)*((_QWORD *)v637 + 3);
                          if ( v778 )
                          {
                            v640 = GetProcessHeap();
                            HeapFree(v640, 0, v778);
                            v637 = (unsigned int *)v764;
                            *(_QWORD *)(v764 + 24) = 0;
                          }
                          v778 = (LPVOID)*((_QWORD *)v637 + 5);
                          if ( v778 )
                          {
                            v641 = GetProcessHeap();
                            HeapFree(v641, 0, v778);
                            *(_QWORD *)(v764 + 40) = 0;
                          }
                          v642 = GetProcessHeap();
                          HeapFree(v642, 0, (LPVOID)v764);
                          v638 = 0;
                          v773 = 0;
                          v606 = dwBytes_4;
                        }
                      }
                      else
                      {
                        v638 = v637;
                        v773 = v637;
                      }
LABEL_821:
                      v769 = v606 | 0x10000000;
                      if ( v606 < 0 )
                        goto LABEL_764;
                      if ( !v638 || (Size = *((_QWORD *)v638 + 1)) == 0 || !*v638 )
                      {
                        v769 = -805306355;
                        goto LABEL_764;
                      }
                      pcchLength = *v638 - 8LL;
                      v643 = MemoryAlloc(pcchLength);
                      v765 = v643;
                      if ( !v643 )
                      {
LABEL_853:
                        v769 = -805306367;
                        v574 = 0;
                        goto LABEL_902;
                      }
                      v644 = 0;
                      v767 = 0;
                      v781 = (LPVOID)0x7F1137FAB69605ELL;
                      v645 = (unsigned __int8 *)Size;
                      v782 = Size;
                      Src = v643;
                      v646 = pcchLength;
                      v790 = pcchLength & 7;
                      if ( (pcchLength & 7) != 0 )
                      {
                        v786 = 0;
                        v768 = 0;
                        v783 = 0;
                        v647 = 0;
                        v648 = 0;
                        v649 = 0;
                        do
                        {
                          dwBytes_4 = *v645++;
                          v768 = 8 * v647;
                          if ( (unsigned int)v647 >= 4 )
                          {
                            dwBytes_4 <<= 56 - v768;
                            v649 |= dwBytes_4;
                          }
                          else
                          {
                            dwBytes_4 <<= 24 - v768;
                            v648 |= dwBytes_4;
                          }
                          ++v647;
                        }
                        while ( v647 < (int)v790 );
                        v786 = v649;
                        v768 = v648;
                        v782 = (SIZE_T)v645;
                        v776 = v495;
                        v775 = v494;
                        v770 = v548;
                        v774 = v107;
                        v777 = v111;
                        v644 = v767;
                        v646 = pcchLength;
                        v650 = v790;
                        v651 = v643;
                        v652 = v768 ^ 0x92F65A5;
                        v653 = v786 ^ 0x699A899C;
                        v654 = v768 ^ 0x92F65A5;
                        v783 = 0;
                        if ( (_DWORD)v790 )
                        {
                          v655 = v786 ^ 0x699A899C;
                          v656 = v783;
                          do
                          {
                            v778 = v651 + 1;
                            if ( v656 >= 4 )
                            {
                              v655 = __ROR4__(v655, 24);
                              v657 = v655;
                            }
                            else
                            {
                              v654 = __ROR4__(v654, 24);
                              v657 = v654;
                            }
                            *v651 = v657;
                            ++v656;
                            v651 = v778;
                          }
                          while ( (int)v656 < (int)v650 );
                          Src = v778;
                          v644 = v767;
                          v643 = v765;
                        }
                        if ( v650 <= 4 )
                        {
                          v658 = 0;
                          if ( v650 < 4 )
                            v652 = v652 >> (8 * (4 - v650)) << (8 * (4 - v650));
                        }
                        else
                        {
                          v658 = v653 >> (8 * (8 - v650)) << (8 * (8 - v650));
                        }
                      }
                      else
                      {
                        v768 = 0;
                        v658 = 0;
                        v652 = 0;
                      }
                      v659 = v646 >> 3;
                      if ( v646 >> 3 )
                      {
                        v790 = 0;
                        v660 = HIDWORD(v781);
                        v661 = WORD2(v781);
                        LODWORD(v772) = WORD2(v781);
                        v662 = WORD1(v781);
                        dwBytes_4 = 24670;
                        v663 = (unsigned __int8 *)v782;
                        v664 = Src;
                        v665 = v768;
                        do
                        {
                          v666 = v663[3] | ((v663[2] | (((*v663 << 8) | v663[1]) << 8)) << 8);
                          v667 = v663[7] | ((v663[6] | ((v663[5] | (v663[4] << 8)) << 8)) << 8);
                          v663 += 8;
                          v668 = v652 ^ v666;
                          v669 = v660 ^ v652 ^ v666 ^ v658 ^ v667 ^ 0xAB69605E;
                          v670 = v668 ^ (__ROR4__(v669, 22) + v661 * __ROR4__(v669 + 1419157410, 27));
                          v671 = v669 ^ (v662 * __ROR4__(v660 + v670, 9) - __ROR4__(v670, 30));
                          v672 = v670 ^ (dwBytes_4 * (v671 - v661) - (v671 >> 13));
                          v673 = v671 ^ (HIWORD(v781) * __ROR4__(v662 ^ v672, 26) - __ROR4__(v672, 30));
                          v674 = v672 ^ (v660 - (v673 ^ 0xAB69605E));
                          v675 = v673 ^ (v662 * (v661 ^ v674)) ^ __ROR4__(v674, 6);
                          v676 = v674 ^ (__ROR4__(v675, 30) + dwBytes_4 * __ROR4__(v660 + v675, 15));
                          v677 = v675 ^ (HIWORD(v781) * __ROR4__(v676 + 1419157410, 14) - __ROR4__(v676, 24));
                          v678 = v676 ^ __ROR4__(v677, 10) ^ (v772 * __ROR4__(v677 ^ 0xAB69605E, 12));
                          v679 = v678
                               ^ (HIWORD(v781)
                                * (dwBytes_4
                                 + __ROR4__(~(v677 ^ (v678 >> 10) ^ (WORD1(v781) * (HIWORD(v781) ^ v678))), 5)));
                          v680 = v677
                               ^ (v678 >> 10)
                               ^ (WORD1(v781) * (HIWORD(v781) ^ v678))
                               ^ (v679 - HIWORD(v781))
                               ^ 0xAB69605E;
                          v661 = v772;
                          v681 = v679 ^ ((v680 >> 2) + v772 * __ROR4__(HIWORD(v781) ^ v680, 30));
                          v662 = WORD1(v781);
                          v682 = v680 ^ (__ROR4__(v681, 25) + WORD1(v781) * __ROR4__(v681 - v660, 6));
                          v683 = v681 ^ (dwBytes_4 * (v772 ^ v682) + __ROR4__(v682, 9));
                          v684 = v682 ^ (__ROR4__(v683, 25) + HIWORD(v781) * __ROR4__(WORD1(v781) ^ v683, 27));
                          v685 = v683 ^ v684 ^ v660 ^ 0xAB69605E;
                          v686 = v684 ^ (v772 * (__ROR4__(v685, 3) - WORD1(v781)));
                          v687 = v685 ^ (dwBytes_4 * __ROR4__(v686 - v660, 1) - __ROR4__(v686, 6));
                          v688 = v686 ^ (__ROR4__(v687, 18) + HIWORD(v781) * __ROR4__(v687 - 1419157410, 29));
                          v689 = v687 ^ (v772 * __ROR4__(v688 - 1419157410, 17) - __ROR4__(v688, 14));
                          v690 = v688 ^ (v689 >> 3) ^ (WORD1(v781) * (v689 ^ dwBytes_4));
                          v652 = v689 ^ v665 ^ __ROR4__(v690, 30) ^ (dwBytes_4 * __ROR4__(v690 ^ v660, 28));
                          v658 = v690 ^ v786;
                          v664[3] = v652;
                          v664[7] = v658;
                          v664[2] = __ROR4__(v652, 8);
                          v664[6] = __ROR4__(v658, 8);
                          v664[1] = __ROR4__(v652, 16);
                          v664[5] = __ROR4__(v658, 16);
                          *v664 = __ROR4__(v652, 24);
                          v664[4] = __ROR4__(v658, 24);
                          v665 = v666;
                          v786 = v667;
                          v664 += 8;
                          ++v790;
                        }
                        while ( v790 < v659 );
                        v644 = v767;
                        v75 = v760;
                        v111 = v777;
                        v107 = v774;
                        v495 = (unsigned int *)v776;
                        v494 = (unsigned int *)v775;
                        v643 = v765;
                        v646 = pcchLength;
                      }
                      for ( j = 0; j < v646; ++j )
                        v644 ^= *((_BYTE *)v643 + j);
                      if ( v644 != *(_QWORD *)(v646 + Size) )
                      {
                        MemoryFree(v643);
                        goto LABEL_853;
                      }
                      v692 = v770;
                      v693 = v773;
                      v786 = 0;
                      v764 = (size_t)v643;
                      if ( (unsigned int)v646 < 4 )
                      {
                        v694 = -1073741762;
                        v574 = v765;
LABEL_897:
                        v548 = v692;
                        goto LABEL_898;
                      }
                      v694 = RtlULongLongAdd(v643, 4, &v764);
                      if ( v694 >= 0 )
                      {
                        v694 = RtlUIntAdd(0, 4, &v786);
                        if ( v694 >= 0 )
                        {
                          if ( v696 - v786 < 4 )
                            goto LABEL_895;
                          v697 = *(unsigned int *)v764;
                          v768 = *(_DWORD *)v764;
                          v694 = RtlULongLongAdd(v764, 4, &v764);
                          if ( v694 < 0 )
                            goto LABEL_896;
                          v694 = RtlUIntAdd(v786, 4, &v786);
                          if ( v694 < 0 )
                            goto LABEL_896;
                          if ( v698 - v786 < (unsigned int)v697 )
                            goto LABEL_895;
                          v694 = RtlUIntAdd(v786, (unsigned int)v697, &v786);
                          if ( v694 >= 0 )
                          {
                            v700 = v699;
                            v701 = (unsigned int *)v764;
                            if ( (unsigned __int64)v695 + v700 >= v697 + v764
                              && (unsigned __int64)v695 + v700 - v764 - v697 < 8 )
                            {
                              v783 = *v695;
                              v781 = 0;
                              v790 = 0;
                              v782 = 0;
                              LODWORD(v772) = 0;
                              if ( v764 )
                              {
                                v694 = RtlULongLongAdd(v764, (unsigned int)v697, &v781);
                                v769 = v694;
                                v773 = v693;
                                if ( v694 < 0 )
                                {
                                  v548 = v692;
                                  v574 = v702;
LABEL_891:
                                  v711 = v761;
LABEL_892:
                                  if ( v694 >= 0 && v783 != v711 )
                                    v694 = -1073741762;
                                  goto LABEL_898;
                                }
                                v703 = v701;
                                v801 = v701;
                                v704 = v781;
                                if ( v701 < v781 )
                                {
                                  v765 = v702;
                                  v770 = v692;
                                  while ( 1 )
                                  {
                                    v694 = RtlULongLongAdd(v703, 4, &v790);
                                    if ( v694 < 0 )
                                      break;
                                    if ( v790 > (unsigned __int64)v781 )
                                    {
                                      v694 = -1073741811;
LABEL_880:
                                      v548 = v770;
                                      v574 = v765;
                                      goto LABEL_898;
                                    }
                                    v786 = 0;
                                    v694 = RtlUIntAdd(4, *v703, &v786);
                                    if ( v694 < 0 )
                                      goto LABEL_880;
                                    v778 = v111;
                                    v705 = v107;
                                    v706 = v495;
                                    v707 = v693;
                                    Size = (SIZE_T)v693;
                                    v694 = RtlULongLongAdd(v703, v786, &v782);
                                    v769 = v694;
                                    v574 = v702;
                                    v773 = v707;
                                    v495 = v706;
                                    v548 = v692;
                                    v107 = v705;
                                    v111 = v778;
                                    if ( v694 < 0 )
                                      goto LABEL_891;
                                    v703 = (unsigned int *)v782;
                                    v801 = (void *)v782;
                                    v704 = v781;
                                    if ( v782 > (unsigned __int64)v781 )
                                    {
                                      v694 = -1073741811;
                                      v773 = (LPVOID)Size;
                                      goto LABEL_897;
                                    }
                                    LODWORD(v772) = v772 + 1;
                                    v765 = v702;
                                    v693 = (void *)Size;
                                    v773 = (LPVOID)Size;
                                    v770 = v692;
                                    if ( v782 >= (unsigned __int64)v781 )
                                    {
                                      v773 = (LPVOID)Size;
                                      goto LABEL_876;
                                    }
                                  }
                                  v548 = v770;
                                  v574 = v765;
                                  goto LABEL_891;
                                }
LABEL_876:
                                v574 = v702;
                                v548 = v692;
                                if ( v801 != v704 )
                                {
                                  v694 = -1073741811;
LABEL_898:
                                  v769 = v694 | 0x10000000;
                                  goto LABEL_903;
                                }
                              }
                              else
                              {
                                v769 = 0;
                                v773 = v693;
                                v548 = v692;
                                v574 = v695;
                              }
                              v708 = 0;
                              v790 = 0;
                              v709 = v768;
                              if ( v768 )
                              {
                                v710 = GetProcessHeap();
                                v708 = HeapAlloc(v710, 8u, (unsigned int)v768);
                                v790 = (SIZE_T)v708;
                                if ( !v708 )
                                {
                                  v694 = -1073741801;
                                  goto LABEL_898;
                                }
                                v769 = 0;
                                v701 = (unsigned int *)v764;
                                v709 = v768;
                              }
                              if ( v701 )
                                memcpy_0(v708, v701, v709);
                              v771 = (unsigned int *)v790;
                              v711 = v772;
                              v761 = v772;
                              v694 = v769;
                              goto LABEL_892;
                            }
LABEL_895:
                            v694 = -1073741762;
                          }
                        }
                      }
LABEL_896:
                      v773 = v693;
                      v574 = v695;
                      goto LABEL_897;
                    }
                  }
                }
              }
            }
          }
          v770 = v548;
          v582 = GetProcessHeap();
          HeapFree(v582, 0, v774);
        }
        v581 = v769;
        goto LABEL_722;
      }
LABEL_691:
      v494 = (unsigned int *)v781;
      v781 = 0;
      goto LABEL_692;
    }
    pcchLength = v789[1];
    if ( v473 )
    {
      do
      {
        v761 = 0;
        if ( (int)RtlUIntAdd(4, *v474, &v761) < 0 || (int)RtlULongLongAdd(v476, v761, &pcchLength) < 0 )
          goto LABEL_578;
        v474 = (unsigned int *)pcchLength;
      }
      while ( v478 + 1 < v477 );
    }
    if ( (int)RtlULongLongAdd(v474, 4, &v791) >= 0 && (unsigned __int64)(v479 + 3) <= v789[1] + HIDWORD(v789[0]) )
    {
      *v479 = 8;
      *(_QWORD *)v791 = v778;
      goto LABEL_634;
    }
LABEL_578:
    v108 = (size_t)v771;
    goto LABEL_579;
  }
LABEL_587:
  v70 = v809;
  v801 = 0;
  v837 = (int *)TickCount64;
  v69 = v810;
LABEL_945:
  v66 = v817;
  v7 = v816;
  v61 = v804;
LABEL_946:
  SP<unsigned char,SP_HLOCAL<unsigned char>>::Reset(&v801);
  if ( v75 >= 0 )
  {
    if ( v70 != 4 )
    {
LABEL_954:
      v75 = -1073418210;
      goto LABEL_958;
    }
    v75 = 0;
    v69 = *v837;
  }
  else
  {
    switch ( v75 )
    {
      case -805306316:
        v75 = -1073418222;
        break;
      case -805306139:
      case -1073425151:
        v75 = -1073418201;
        break;
      case -805306306:
        v75 = -1073418200;
        break;
      case -2147024774:
        goto LABEL_954;
    }
  }
LABEL_958:
  SP<unsigned char,SP_HLOCAL<unsigned char>>::Reset(&v837);
  v738 = 0;
  if ( v75 >= 0 )
    v738 = v69;
  ConfigData = CSLQuery::IsAppServerAllowed(&v808);
  if ( ConfigData < 0 )
  {
    if ( (unsigned int)dword_18012E170 > 3 && (unsigned __int8)tlgKeywordOn(&dword_18012E170, 0, v11) )
    {
      v902 = "UpdateConfig";
      v830 = ConfigData;
      v903 = "CSLQuery::IsAppServerAllowed";
      v904 = "Warning HResult failed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        v739,
        (unsigned int)qword_18010E470,
        v11,
        v740,
        (__int64)&v904,
        (__int64)&v903,
        (__int64)&v830,
        (__int64)&v902);
    }
    goto LABEL_990;
  }
  if ( !v808 && !v738 )
  {
    *((_DWORD *)v61 + 32) &= 0xFFFFAFFF;
    *((_DWORD *)v61 + 32) |= 0x2000u;
  }
  IsAdminSession = CRemoteTerminal::IsAdminSession(v66, &v807);
  if ( IsAdminSession >= 0 )
  {
    v745 = v807;
  }
  else
  {
    if ( (unsigned int)dword_18012E170 > 3
      && (unsigned __int8)tlgKeywordOn(&dword_18012E170, 0, (unsigned int)IsAdminSession) )
    {
      v831 = v743;
      v905 = "CRemoteTerminal::IsAdminSession failed, assuming admin session";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        v742,
        (unsigned int)word_18010E44A,
        v743,
        v744,
        (__int64)&v905,
        (__int64)&v831);
    }
    v745 = 1;
  }
  if ( v745 )
    *((_DWORD *)v61 + 32) = *((_DWORD *)v61 + 32) & 0xFFFF87FF | 0x2800;
  v746 = *((_DWORD *)v66 + 1276);
  v747 = (int *)((char *)v66 + 5104);
  if ( (v746 & 0x40000000) != 0 )
  {
    v746 = 44;
    *v747 = 44;
  }
  v748 = v61 + 124;
  if ( (*((_DWORD *)v61 + 31) & 0x10000) != 0 )
  {
    v746 |= 1u;
    *v747 = v746;
  }
  if ( (*v748 & 0x2000000) != 0 )
  {
    v746 |= 0x40u;
    *v747 = v746;
  }
  if ( v806 && v805 )
  {
    v746 &= ~0x80u;
    *v747 = v746;
  }
  if ( v745 )
  {
    v746 |= 8u;
    *v747 = v746;
  }
  *v748 ^= (*v748 ^ (v746 << 16)) & 0x10000;
  ConfigData = (*(__int64 (__fastcall **)(_QWORD, struct IUserName *, unsigned __int8 *))(**((_QWORD **)v66 + 200)
                                                                                        + 128LL))(
                 *((_QWORD *)v66 + 200),
                 v838,
                 v61);
  if ( ConfigData < 0 )
  {
    if ( (unsigned int)dword_18012E170 > 3 && (unsigned __int8)tlgKeywordOn(&dword_18012E170, 0, v11) )
    {
      v906 = "UpdateConfig";
      v832 = ConfigData;
      v907 = "ptrConnection->SetConfigData";
      v908 = "Warning HResult failed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        v749,
        (unsigned int)&byte_18010E40F,
        v11,
        v750,
        (__int64)&v908,
        (__int64)&v907,
        (__int64)&v832,
        (__int64)&v906);
    }
    goto LABEL_990;
  }
  v6 = v798;
LABEL_995:
  if ( (unsigned int)dword_18012E170 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18012E170, 0, v11) )
  {
    v834 = ConfigData;
    v911 = "CRemoteTerminal::UpdateConfig";
    v912 = "Task completed successfully";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      v754,
      (unsigned int)&byte_18010E39F,
      v755,
      v756,
      (__int64)&v912,
      (__int64)&v911,
      (__int64)&v834);
  }
  v7 = v6;
LABEL_999:
  if ( v7 )
  {
    v757 = 30;
    v758 = v7 + 210;
    do
    {
      *v758++ = 0;
      --v757;
    }
    while ( v757 );
  }
  operator delete(v6);
  if ( StringSid )
    LocalFree(StringSid);
  if ( Sid )
    CoTaskMemFree(Sid);
  CAutoSetActivityId::~CAutoSetActivityId((CAutoSetActivityId *)v919);
  CImpersonate::StopImpersonating((CImpersonate *)&v793);
  SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(&v818);
  return (unsigned int)ConfigData;
}

```

## disassembly

```asm
0x180055d8c  mov     [rsp-8+arg_10], rbx
0x180055d91  push    rbp
0x180055d92  push    rsi
0x180055d93  push    rdi
0x180055d94  push    r12
0x180055d96  push    r13
0x180055d98  push    r14
0x180055d9a  push    r15
0x180055d9c  lea     rbp, [rsp-6E0h]
0x180055da4  sub     rsp, 7E0h
0x180055dab  mov     rax, cs:__security_cookie
0x180055db2  xor     rax, rsp
0x180055db5  mov     [rbp+710h+var_40], rax
0x180055dbc  mov     r12d, r8d
0x180055dbf  mov     [rbp+710h+var_5D8], rdx
0x180055dc6  mov     rsi, rcx
0x180055dc9  mov     [rbp+710h+var_640], rcx
0x180055dd0  xor     r15d, r15d
0x180055dd3  mov     ebx, r15d
0x180055dd6  mov     edi, r15d
0x180055dd9  mov     [rbp+710h+var_648], r15
0x180055de0  mov     [rbp+710h+StringSid], r15
0x180055de7  mov     [rbp+710h+Sid], r15
0x180055dee  xorps   xmm0, xmm0
0x180055df1  movups  xmmword ptr [rbp+710h+var_2C8.Data1], xmm0
0x180055df8  mov     [rbp+710h+var_66C], 1
0x180055e02  mov     [rbp+710h+var_674], r15d
0x180055e09  mov     [rbp+710h+var_678], r15d
0x180055e10  mov     [rbp+710h+var_638], r15
0x180055e17  mov     [rbp+710h+var_6C8], r15w
0x180055e1c  mov     [rbp+710h+var_670], r15d
0x180055e23  movups  [rbp+710h+Buf1], xmm0
0x180055e2a  mov     [rbp+710h+hKey], r15
0x180055e2e  mov     [rbp+710h+Type], r15d
0x180055e35  mov     dword ptr [rbp+710h+Data], r15d
0x180055e39  mov     [rbp+710h+cbData], 4
0x180055e43  xor     edx, edx; Val
0x180055e45  mov     r8d, 208h; Size
0x180055e4b  lea     rcx, [rbp+710h+SubKey]; void *
0x180055e52  call    memset_0
0x180055e57  xorps   xmm0, xmm0
0x180055e5a  movups  xmmword ptr [rbp+710h+var_2E8.Data1], xmm0
0x180055e61  lea     rdx, [rbp+710h+var_2E8]; struct _GUID *
0x180055e68  lea     rcx, [rbp+710h+var_2B8]; this
0x180055e6f  call    ??0CAutoSetActivityId@@QEAA@PEAU_GUID@@@Z; CAutoSetActivityId::CAutoSetActivityId(_GUID *)
0x180055e74  nop
0x180055e75  mov     eax, cs:dword_18012E170
0x180055e7b  lea     r13, aCremotetermina_32; "CRemoteTerminal::UpdateConfig"
0x180055e82  lea     rcx, aGroupPolicy; "Group Policy"
0x180055e89  cmp     eax, 4
0x180055e8c  jbe     short loc_180055EF4
0x180055e8e  movsxd  rax, dword ptr [rsi+690h]
0x180055e95  mov     [rbp+710h+var_350], rax
0x180055e9c  lea     rax, aRemoteterminal_4; "RemoteTerminal->UpdateConfig()"
0x180055ea3  mov     [rbp+710h+var_348], rax
0x180055eaa  mov     [rbp+710h+var_340], r13
0x180055eb1  mov     [rbp+710h+var_550], rcx
0x180055eb8  lea     rax, [rbp+710h+var_350]
0x180055ebf  mov     [rsp+810h+var_7D8], rax
0x180055ec4  lea     rax, [rbp+710h+var_348]
0x180055ecb  mov     [rsp+810h+var_7E0], rax
0x180055ed0  lea     rax, [rbp+710h+var_340]
0x180055ed7  mov     [rsp+810h+lpcbData], rax
0x180055edc  lea     rax, [rbp+710h+var_550]
0x180055ee3  mov     [rsp+810h+phkResult], rax
0x180055ee8  lea     rdx, qword_18010E8F0
0x180055eef  call    ??$Write@U?$_tlgWrapSz@D@@U1@U1@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@33AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &)
0x180055ef4  call    cs:__imp_GetTickCount64
0x180055efb  nop     dword ptr [rax+rax+00h]
0x180055f00  mov     [rbp+710h+var_630], rax
0x180055f07  cmp     [rsi+640h], r15
0x180055f0e  jnz     loc_180055F9B
0x180055f14  mov     r14d, 800708CAh
0x180055f1a  mov     eax, cs:dword_18012E170
0x180055f20  cmp     eax, 3
0x180055f23  jbe     loc_18005CC52
0x180055f29  lea     rax, aUpdateconfig; "UpdateConfig"
0x180055f30  mov     [rbp+710h+var_548], rax
0x180055f37  mov     [rbp+710h+var_604], r14d
0x180055f3e  lea     rax, aCheckForPresen; "check for presence of connection object"
0x180055f45  mov     [rbp+710h+var_540], rax
0x180055f4c  lea     rax, aWarningHresult; "Warning HResult failed"
0x180055f53  mov     [rbp+710h+var_538], rax
0x180055f5a  lea     rax, [rbp+710h+var_548]
0x180055f61  mov     [rsp+810h+var_7D8], rax
0x180055f66  lea     rax, [rbp+710h+var_604]
0x180055f6d  mov     [rsp+810h+var_7E0], rax
0x180055f72  lea     rax, [rbp+710h+var_540]
0x180055f79  mov     [rsp+810h+lpcbData], rax
0x180055f7e  lea     rax, [rbp+710h+var_538]
0x180055f85  lea     rdx, byte_18010E8B5
0x180055f8c  mov     [rsp+810h+phkResult], rax
0x180055f91  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x180055f96  jmp     loc_18005CC52
0x180055f9b  lea     rdx, [rbp+710h+var_2E8]; struct _GUID *
0x180055fa2  mov     rcx, rsi; this
0x180055fa5  call    ?GetActivityId@CRemoteTerminal@@UEAAJPEAU_GUID@@@Z; CRemoteTerminal::GetActivityId(_GUID *)
0x180055faa  mov     edi, 2
0x180055faf  cmp     [rbp+710h+var_2A8], r15d
0x180055fb6  jl      short loc_180055FCD
0x180055fb8  lea     rdx, [rbp+710h+var_2E8]
0x180055fbf  mov     ecx, edi
0x180055fc1  call    cs:__imp_EtwEventActivityIdControl
0x180055fc8  nop     dword ptr [rax+rax+00h]
0x180055fcd  mov     rcx, [rsi+640h]
0x180055fd4  mov     rax, [rcx]
0x180055fd7  lea     rdx, [rbp+710h+Buf1]
0x180055fde  mov     rax, [rax+150h]
0x180055fe5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055fea  mov     r14d, eax
0x180055fed  test    eax, eax
0x180055fef  jns     loc_180056075
0x180055ff5  mov     eax, cs:dword_18012E170
0x180055ffb  cmp     eax, 3
0x180055ffe  jbe     short loc_18005606D
0x180056000  lea     rax, aUpdateconfig; "UpdateConfig"
0x180056007  mov     [rbp+710h+var_530], rax
0x18005600e  mov     [rbp+710h+var_5EC], r14d
0x180056015  lea     rax, aPtrconnectionG_1; "ptrConnection->GetConnectionGUID"
0x18005601c  mov     [rbp+710h+var_528], rax
0x180056023  lea     rax, aWarningHresult; "Warning HResult failed"
0x18005602a  mov     [rbp+710h+var_520], rax
0x180056031  lea     rax, [rbp+710h+var_530]
0x180056038  mov     [rsp+810h+var_7D8], rax
0x18005603d  lea     rax, [rbp+710h+var_5EC]
0x180056044  mov     [rsp+810h+var_7E0], rax
0x180056049  lea     rax, [rbp+710h+var_528]
0x180056050  mov     [rsp+810h+lpcbData], rax
0x180056055  lea     rax, [rbp+710h+var_520]
0x18005605c  mov     [rsp+810h+phkResult], rax
0x180056061  lea     rdx, word_18010E87A
0x180056068  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18005606d  mov     rdi, r15
0x180056070  jmp     loc_18005CC52
0x180056075  mov     r8d, 10h; Size
0x18005607b  lea     rdx, TERMINAL_TYPE_DEBUG; Buf2
0x180056082  lea     rcx, [rbp+710h+Buf1]; Buf1
0x180056089  call    memcmp_0
0x18005608e  test    eax, eax
0x180056090  jnz     short loc_1800560B8
0x180056092  test    byte ptr cs:?g_DebugTraceComponent@@3KA, 4; ulong g_DebugTraceComponent
0x180056099  jz      short loc_1800560B0
0x18005609b  mov     r8d, [rsi+690h]
0x1800560a2  lea     rdx, aConnectionForS; "Connection for session %d is debug"
0x1800560a9  mov     ecx, edi; int
0x1800560ab  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800560b0  mov     r14d, r15d
0x1800560b3  jmp     loc_18005CCD0
0x1800560b8  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800560bf  mov     r14d, 1E40h
0x1800560c5  mov     ecx, r14d; unsigned __int64
0x1800560c8  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800560cd  mov     rdi, rax
0x1800560d0  mov     [rbp+710h+var_680], rax
0x1800560d7  mov     rbx, rax
0x1800560da  mov     [rbp+710h+var_6A8], rax
0x1800560de  test    rax, rax
0x1800560e1  jnz     short loc_1800560F5
0x1800560e3  mov     r14d, 8007000Eh
0x1800560e9  mov     rdi, [rbp+710h+var_648]
0x1800560f0  jmp     loc_18005CC52
0x1800560f5  mov     r8, r14; Size
0x1800560f8  xor     edx, edx; Val
0x1800560fa  mov     rcx, rdi; void *
0x1800560fd  call    memset_0
0x180056102  mov     r8d, 0A68h; unsigned int
0x180056108  mov     rdx, rdi; unsigned __int8 *
0x18005610b  mov     rcx, rsi; this
0x18005610e  call    ?GetConfigData@CRemoteTerminal@@UEAAJPEAEK@Z; CRemoteTerminal::GetConfigData(uchar *,ulong)
0x180056113  mov     r14d, eax
0x180056116  test    eax, eax
0x180056118  jns     short loc_180056191
0x18005611a  mov     eax, cs:dword_18012E170
0x180056120  cmp     eax, 3
0x180056123  jbe     loc_18005CC52
0x180056129  lea     rax, aUpdateconfig; "UpdateConfig"
0x180056130  mov     [rbp+710h+var_518], rax
0x180056137  mov     [rbp+710h+var_5E8], r14d
0x18005613e  lea     rax, aTerminalGetcon; "Terminal->GetConfigData"
0x180056145  mov     [rbp+710h+var_510], rax
0x18005614c  lea     rax, aWarningHresult; "Warning HResult failed"
0x180056153  mov     [rbp+710h+var_508], rax
0x18005615a  lea     rax, [rbp+710h+var_518]
0x180056161  mov     [rsp+810h+var_7D8], rax
0x180056166  lea     rax, [rbp+710h+var_5E8]
0x18005616d  mov     [rsp+810h+var_7E0], rax
0x180056172  lea     rax, [rbp+710h+var_510]
0x180056179  mov     [rsp+810h+lpcbData], rax
0x18005617e  lea     rax, [rbp+710h+var_508]
0x180056185  lea     rdx, byte_18010E83F
0x18005618c  jmp     loc_180055F8C
0x180056191  lea     r13, [rdi+0A70h]
0x180056198  mov     rcx, [rsi+640h]
0x18005619f  mov     rax, [rcx]
0x1800561a2  lea     rdx, [rbp+710h+var_2A0]
0x1800561a9  mov     rax, [rax+40h]
0x1800561ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800561b2  test    eax, eax
0x1800561b4  js      loc_180056314
0x1800561ba  lea     rax, [rbp+710h+hKey]
0x1800561be  mov     [rsp+810h+phkResult], rax; phkResult
0x1800561c3  mov     r9d, 20019h; samDesired
0x1800561c9  xor     r8d, r8d; ulOptions
0x1800561cc  lea     r14, aSoftwarePolici; "Software\\Policies\\Microsoft\\Windows "...
0x1800561d3  mov     rdx, r14; lpSubKey
0x1800561d6  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800561dd  call    cs:__imp_RegOpenKeyExW
0x1800561e4  nop     dword ptr [rax+rax+00h]
0x1800561e9  test    eax, eax
0x1800561eb  jz      short loc_18005623A
0x1800561ed  mov     eax, cs:dword_18012E170
0x1800561f3  cmp     eax, 4
0x1800561f6  jbe     loc_180056314
0x1800561fc  mov     [rbp+710h+var_500], r14
0x180056203  lea     rax, aCouldNotOpenPo; "Could not open policy reg-key for Query"...
0x18005620a  mov     [rbp+710h+var_4F8], rax
0x180056211  lea     rax, [rbp+710h+var_500]
0x180056218  mov     [rsp+810h+lpcbData], rax
0x18005621d  lea     rax, [rbp+710h+var_4F8]
0x180056224  mov     [rsp+810h+phkResult], rax
0x180056229  lea     rdx, word_18010E80A
0x180056230  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x180056235  jmp     loc_180056314
0x18005623a  lea     rax, [rbp+710h+cbData]
0x180056241  mov     [rsp+810h+lpcbData], rax; lpcbData
0x180056246  lea     rax, [rbp+710h+Data]
0x18005624a  mov     [rsp+810h+phkResult], rax; lpData
0x18005624f  lea     r9, [rbp+710h+Type]; lpType
0x180056256  xor     r8d, r8d; lpReserved
0x180056259  lea     rdx, aFqueryuserconf; "fQueryUserConfigFromDC"
0x180056260  mov     rcx, [rbp+710h+hKey]; hKey
0x180056264  call    cs:__imp_RegQueryValueExW
0x18005626b  nop     dword ptr [rax+rax+00h]
0x180056270  mov     ebx, eax
0x180056272  mov     ecx, cs:dword_18012E170
0x180056278  cmp     ecx, 5
0x18005627b  jbe     short loc_1800562DE
0x18005627d  mov     ecx, dword ptr [rbp+710h+Data]
0x180056280  mov     [rbp+710h+var_4F0], rcx
0x180056287  mov     [rbp+710h+var_5C0], eax
0x18005628d  mov     [rbp+710h+var_4E8], r14
0x180056294  lea     rax, aPolicyRegKeyVa; "Policy reg-key value for QueryLocalUser"...
0x18005629b  mov     [rbp+710h+var_4E0], rax
0x1800562a2  lea     rax, [rbp+710h+var_4F0]
0x1800562a9  mov     [rsp+810h+var_7D8], rax
0x1800562ae  lea     rax, [rbp+710h+var_5C0]
0x1800562b5  mov     [rsp+810h+var_7E0], rax
0x1800562ba  lea     rax, [rbp+710h+var_4E8]
0x1800562c1  mov     [rsp+810h+lpcbData], rax
0x1800562c6  lea     rax, [rbp+710h+var_4E0]
0x1800562cd  mov     [rsp+810h+phkResult], rax
0x1800562d2  lea     rdx, byte_18010E7B7
0x1800562d9  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x1800562de  mov     rcx, [rbp+710h+hKey]; hKey
0x1800562e2  call    cs:__imp_RegCloseKey
0x1800562e9  nop     dword ptr [rax+rax+00h]
0x1800562ee  mov     [rbp+710h+hKey], 0
0x1800562f6  xor     ecx, ecx; hKey
0x1800562f8  call    cs:__imp_RegCloseKey
0x1800562ff  nop     dword ptr [rax+rax+00h]
0x180056304  mov     [rbp+710h+hKey], 0
0x18005630c  test    ebx, ebx
0x18005630e  jz      loc_180056484
0x180056314  lea     rax, [rbp+710h+var_2A0]
0x18005631b  mov     [rsp+810h+phkResult], rax
0x180056320  lea     r9, SubKey; "System\\CurrentControlSet\\Control\\Ter"...
0x180056327  lea     r8, aSS_0; "%s\\%s"
0x18005632e  mov     edx, 104h; unsigned __int64
0x180056333  lea     rcx, [rbp+710h+SubKey]; unsigned __int16 *
0x18005633a  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18005633f  lea     rax, [rbp+710h+hKey]
0x180056343  mov     [rsp+810h+phkResult], rax; phkResult
0x180056348  mov     r9d, 20019h; samDesired
0x18005634e  xor     r8d, r8d; ulOptions
0x180056351  lea     rdx, [rbp+710h+SubKey]; lpSubKey
0x180056358  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18005635f  call    cs:__imp_RegOpenKeyExW
0x180056366  nop     dword ptr [rax+rax+00h]
0x18005636b  test    eax, eax
0x18005636d  jz      short loc_1800563C3
0x18005636f  mov     eax, cs:dword_18012E170
0x180056375  cmp     eax, 4
0x180056378  jbe     loc_180056484
0x18005637e  lea     rax, [rbp+710h+SubKey]
0x180056385  mov     [rbp+710h+var_4D8], rax
0x18005638c  lea     rax, aCouldNotOpenWi; "Could not open Winsta reg-key for Query"...
0x180056393  mov     [rbp+710h+var_4D0], rax
0x18005639a  lea     rax, [rbp+710h+var_4D8]
0x1800563a1  mov     [rsp+810h+lpcbData], rax
0x1800563a6  lea     rax, [rbp+710h+var_4D0]
0x1800563ad  mov     [rsp+810h+phkResult], rax
0x1800563b2  lea     rdx, byte_18010E787
0x1800563b9  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x1800563be  jmp     loc_180056484
0x1800563c3  lea     rax, [rbp+710h+cbData]
0x1800563ca  mov     [rsp+810h+lpcbData], rax; lpcbData
0x1800563cf  lea     rax, [rbp+710h+Data]
0x1800563d3  mov     [rsp+810h+phkResult], rax; lpData
0x1800563d8  lea     r9, [rbp+710h+Type]; lpType
0x1800563df  xor     r8d, r8d; lpReserved
  ... truncated ...
```
