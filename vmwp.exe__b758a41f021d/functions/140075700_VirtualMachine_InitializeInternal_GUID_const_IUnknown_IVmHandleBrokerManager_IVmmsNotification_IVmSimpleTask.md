# VirtualMachine::InitializeInternal(_GUID const &,IUnknown *,IVmHandleBrokerManager *,IVmmsNotification *,IVmSimpleTask *)

- ea: `0x140075700`
- end: `0x140077c11`
- name: `?InitializeInternal@VirtualMachine@@AEAAJAEBU_GUID@@PEAUIUnknown@@PEAUIVmHandleBrokerManager@@PEAVIVmmsNotification@@PEAUIVmSimpleTask@@@Z`
- size: `9489`
- prototype: `__int64 __usercall@<rax>(VirtualMachine *__hidden this@<rcx>, const struct _GUID *@<rdx>, struct IUnknown *@<r8>, struct IVmHandleBrokerManager *@<r9>, struct IVmmsNotification *, struct IVmSimpleTask *)`
- caller_count: `0`
- callee_count: `138`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x140022888`
- `0x14002a850`
- `0x140031480`
- `0x140032620`
- `0x1400364a0`
- `0x14003a9c0`
- `0x14003b720`
- `0x14003b844`
- `0x14003c680`
- `0x14003d828`
- `0x14004517c`
- `0x1400464d0`
- `0x1400484f4`
- `0x14004f6dc`
- `0x140053de8`
- `0x140053f10`
- `0x140053f60`
- `0x1400545bc`
- `0x140054fc0`
- `0x140055a9c`
- `0x140055e18`
- `0x14005a448`
- `0x14005b4b4`
- `0x14005bef0`
- `0x14005c1d0`
- `0x14005c4b8`
- `0x14005e524`
- `0x140064f4c`
- `0x140066eec`
- `0x1400670f8`
- `0x140068c10`
- `0x140069004`
- `0x1400691b4`
- `0x140069338`
- `0x140069470`
- `0x14006bf00`
- `0x14006da84`
- `0x14006dae8`
- `0x1400703b0`
- `0x1400706b8`
- `0x140070ecc`
- `0x140071638`
- `0x140071aa4`
- `0x140073fa8`
- `0x140074ff0`
- `0x14007519c`
- `0x140075648`
- `0x140075700`
- `0x140078628`
- `0x1400834e4`

## import_xrefs

- `vmprox!GetVmErrInfo` at `0x140077930`
- `vmprox!GetVmErrInfo` at `0x140077930`
- `OLEAUT32!__imp_VariantInit` at `0x140077896`
- `OLEAUT32!__imp_VariantInit` at `0x140077896`
- `OLEAUT32!__imp_VariantClear` at `0x140077b11`
- `OLEAUT32!__imp_VariantClear` at `0x140077b11`
- `vid!VidGetPartitionProperty` at `0x140076ff8`
- `vid!VidGetPartitionProperty` at `0x140076ff8`

## string_xrefs

- `0x140077aea`: `Completed VirtualMachine::InitializeInternal`

## pseudocode

```c

```
