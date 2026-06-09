# wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)

- ea: `0x14000cfac`
- end: `0x14000d011`
- name: `??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?UnregisterWilFeatureConfigurationChange@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ`
- size: `101`
- prototype: `void __fastcall(__int64 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x14000d720`

## callees

- `0x14000cfac`
- `0x1400a8010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x14000cff0`
- `KERNEL32!GetProcAddress` at `0x14000cff0`
- `KERNEL32!GetModuleHandleW` at `0x14000cfd9`
- `KERNEL32!GetModuleHandleW` at `0x14000cfd9`

## string_xrefs

- `0x14000cfd2`: `ntdll.dll`
- `0x14000cfe6`: `RtlUnregisterFeatureConfigurationChangeNotification`

## pseudocode

```c

```
