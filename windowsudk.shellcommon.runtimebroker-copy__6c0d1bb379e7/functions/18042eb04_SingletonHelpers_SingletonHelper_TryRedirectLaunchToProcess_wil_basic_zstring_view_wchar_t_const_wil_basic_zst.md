# SingletonHelpers::SingletonHelper::TryRedirectLaunchToProcess(wil::basic_zstring_view<wchar_t> const &,wil::basic_zstring_view<wchar_t> const &,ulong,winrt::Windows::Foundation::Collections::ValueSet const &,SingletonHelpers::SingletonHelper::ForegroundOption,bool,StandardMessage,FlowEndpointBase *)

- ea: `0x18042eb04`
- end: `0x18042ec5b`
- name: `?TryRedirectLaunchToProcess@SingletonHelper@SingletonHelpers@@KA?AW4RedirectionResult@details@2@AEBV?$basic_zstring_view@_W@wil@@0KAEBUValueSet@Collections@Foundation@Windows@winrt@@W4ForegroundOption@12@_NW4StandardMessage@@PEAVFlowEndpointBase@@@Z`
- size: `343`
- prototype: `__int64 __fastcall(int, int, int, int, int, HWND hWnd, int, __int64)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18042e98c`

## callees

- `0x18000fea0`
- `0x18042408c`
- `0x180424fe0`
- `0x180429d48`
- `0x18042a00c`
- `0x18042a454`
- `0x18042eb04`
- `0x18042ff94`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18042eb70`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18042eb70`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!IsWindow` at `0x18042ec3a`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!IsWindow` at `0x18042ec3a`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!AllowSetForegroundWindow` at `0x18042ebbb`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!AllowSetForegroundWindow` at `0x18042ebbb`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindowThreadProcessId` at `0x18042eb9b`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindowThreadProcessId` at `0x18042eb9b`

## pseudocode

```c

```
