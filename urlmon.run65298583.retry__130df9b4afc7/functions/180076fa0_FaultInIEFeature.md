# FaultInIEFeature

- ea: `0x180076fa0`
- end: `0x1800771e9`
- name: `FaultInIEFeature`
- size: `585`
- prototype: `HRESULT __stdcall(HWND hWnd, uCLSSPEC *pClassSpec, QUERYCONTEXT *pQuery, DWORD dwFlags)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180075de0`
- `0x1800ebc30`

## callees

- `0x1800215c0`
- `0x180030880`
- `0x180076fa0`
- `0x1800771f0`
- `0x1800b6d50`
- `0x18011ba26`
- `0x18011baa0`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180077001`
- `msvcrt!memcpy_s` at `0x1800770cb`
- `msvcrt!memcpy_s` at `0x180077001`
- `msvcrt!memcpy_s` at `0x1800770cb`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18007716c`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18007717b`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18007716c`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18007717b`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180077158`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180077158`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegGetUSValueA` at `0x180077113`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegGetUSValueA` at `0x180077113`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetParent` at `0x180077190`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetParent` at `0x180077190`
- `ext-ms-win-ntuser-dialogbox-l1-1-1!DialogBoxParamW` at `0x1800771c3`
- `ext-ms-win-ntuser-dialogbox-l1-1-1!DialogBoxParamW` at `0x1800771c3`
- `ext-ms-win-ntuser-window-l1-1-3!GetLastActivePopup` at `0x18007719e`
- `ext-ms-win-ntuser-window-l1-1-3!GetLastActivePopup` at `0x18007719e`

## string_xrefs

- `0x1800770f5`: `Software\Microsoft\Active Setup\Declined Install On Demand IEv5`

## pseudocode

```c

```
