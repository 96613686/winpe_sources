# NotificationServiceImpl::SendEventAndUpdateRegistryDeviceValues(ushort const *,unsigned __int64)

- ea: `0x180074998`
- end: `0x1800749f6`
- name: `?SendEventAndUpdateRegistryDeviceValues@NotificationServiceImpl@@AEAAXPEBG_K@Z`
- size: `94`
- prototype: `void __fastcall(NotificationServiceImpl *__hidden this, const unsigned __int16 *, unsigned __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, service_task, installer_update`

## callers

- `0x18006e2b0`

## callees

- `0x18000fe0c`
- `0x180074998`
- `0x1800853b0`
- `0x18008548c`

## import_xrefs

- `ntdll!RtlPublishWnfStateData` at `0x1800749c9`
- `ntdll!RtlPublishWnfStateData` at `0x1800749c9`

## string_xrefs

- `0x1800749db`: `onecoreuap\base\diagnosis\platform\notifications\prov\wnp\notificationserviceimpl.cpp`

## pseudocode

```c

```
