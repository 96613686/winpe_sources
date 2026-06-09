# TdxShutdownModule

- ea: `0x1400145a0`
- end: `0x14001468e`
- name: `TdxShutdownModule`
- size: `238`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `reparse_path, authz_impersonation`

## callers

- `0x140017440`

## callees

- `0x140012b34`
- `0x140015038`
- `0x140015658`
- `0x1400156d4`
- `0x140017494`
- `0x140018064`
- `0x140023008`

## import_xrefs

- `ntoskrnl!IoDeleteSymbolicLink` at `0x1400145e9`
- `ntoskrnl!IoDeleteSymbolicLink` at `0x1400145fa`
- `ntoskrnl!IoDeleteSymbolicLink` at `0x1400145e9`
- `ntoskrnl!IoDeleteSymbolicLink` at `0x1400145fa`
- `ntoskrnl!IoDeleteDevice` at `0x140014649`
- `ntoskrnl!IoDeleteDevice` at `0x140014649`
- `ntoskrnl!ExFreePoolWithTag` at `0x140014677`
- `ntoskrnl!ExFreePoolWithTag` at `0x140014677`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400145c0`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400145d8`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400145c0`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400145d8`
- `TDI!TdiDeregisterProvider` at `0x140014612`
- `TDI!TdiDeregisterProvider` at `0x140014612`

## pseudocode

```c
__int64 TdxShutdownModule()
{
  struct _UNICODE_STRING DestinationString; // [rsp+20h] [rbp-28h] BYREF
  struct _UNICODE_STRING SymbolicLinkName; // [rsp+30h] [rbp-18h] BYREF

  DestinationString = 0;
  SymbolicLinkName = 0;
  RtlInitUnicodeString(&DestinationString, L"\\Device\\Ip6");
  RtlInitUnicodeString(&SymbolicLinkName, L"\\Device\\Ip");
  IoDeleteSymbolicLink(&DestinationString);
  IoDeleteSymbolicLink(&SymbolicLinkName);
  TdxShutdownTlClientModule();
  TdiDeregisterProvider(TdxTdiProviderHandle);
  TdxTdiProviderHandle = 0;
  TdxShutdownPnpEventClientModule();
  TdxShutdownNsiProviderModule();
  TdxShutdownTransportAddressModule();
  TdxShutdownTransportModule();
  TdxShutdownNaClientModule();
  IoDeleteDevice(TdxDeviceObject);
  TdxDeviceObject = 0;
  TdxDriverObject = 0;
  ExFreePoolWithTag(TdxEntityArray, 0x20786454u);
  return wil_UninitializeFeatureStaging();
}

```

## disassembly

```asm
0x1400145a0  sub     rsp, 48h
0x1400145a4  xorps   xmm0, xmm0
0x1400145a7  lea     rdx, TdxIpv6DeviceName; "\\Device\\Ip6"
0x1400145ae  xorps   xmm1, xmm1
0x1400145b1  lea     rcx, [rsp+48h+DestinationString]; DestinationString
0x1400145b6  movups  xmmword ptr [rsp+48h+DestinationString.Length], xmm0
0x1400145bb  movups  xmmword ptr [rsp+48h+SymbolicLinkName.Length], xmm1
0x1400145c0  call    cs:__imp_RtlInitUnicodeString
0x1400145c7  nop     dword ptr [rax+rax+00h]
0x1400145cc  lea     rdx, TdxIpDeviceName; "\\Device\\Ip"
0x1400145d3  lea     rcx, [rsp+48h+SymbolicLinkName]; DestinationString
0x1400145d8  call    cs:__imp_RtlInitUnicodeString
0x1400145df  nop     dword ptr [rax+rax+00h]
0x1400145e4  lea     rcx, [rsp+48h+DestinationString]; SymbolicLinkName
0x1400145e9  call    cs:__imp_IoDeleteSymbolicLink
0x1400145f0  nop     dword ptr [rax+rax+00h]
0x1400145f5  lea     rcx, [rsp+48h+SymbolicLinkName]; SymbolicLinkName
0x1400145fa  call    cs:__imp_IoDeleteSymbolicLink
0x140014601  nop     dword ptr [rax+rax+00h]
0x140014606  call    TdxShutdownTlClientModule
0x14001460b  mov     rcx, cs:TdxTdiProviderHandle; ProviderHandle
0x140014612  call    cs:__imp_TdiDeregisterProvider
0x140014619  nop     dword ptr [rax+rax+00h]
0x14001461e  mov     cs:TdxTdiProviderHandle, 0
0x140014629  call    TdxShutdownPnpEventClientModule
0x14001462e  call    TdxShutdownNsiProviderModule
0x140014633  call    TdxShutdownTransportAddressModule
0x140014638  call    TdxShutdownTransportModule
0x14001463d  call    TdxShutdownNaClientModule
0x140014642  mov     rcx, cs:TdxDeviceObject; DeviceObject
0x140014649  call    cs:__imp_IoDeleteDevice
0x140014650  nop     dword ptr [rax+rax+00h]
0x140014655  mov     rcx, cs:TdxEntityArray; P
0x14001465c  mov     edx, 20786454h; Tag
0x140014661  mov     cs:TdxDeviceObject, 0
0x14001466c  mov     cs:TdxDriverObject, 0
0x140014677  call    cs:__imp_ExFreePoolWithTag
0x14001467e  nop     dword ptr [rax+rax+00h]
0x140014683  call    wil_UninitializeFeatureStaging
0x140014688  add     rsp, 48h
0x14001468c  retn
```
