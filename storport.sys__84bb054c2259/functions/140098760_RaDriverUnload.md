# RaDriverUnload

- ea: `0x140098760`
- end: `0x14009893d`
- name: `RaDriverUnload`
- size: `477`
- prototype: `__int64 __fastcall(PDRIVER_OBJECT DriverObject)`
- caller_count: `0`
- callee_count: `4`
- tags: `reparse_path, loader_planting`

## callees

- `0x140070754`
- `0x140098760`
- `0x140187cac`
- `0x140190ad0`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x1400987f2`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400987f2`
- `ntoskrnl!IoDeleteDevice` at `0x140098816`
- `ntoskrnl!IoDeleteDevice` at `0x140098816`
- `ntoskrnl!PcwUnregister` at `0x140098848`
- `ntoskrnl!PcwUnregister` at `0x140098867`
- `ntoskrnl!PcwUnregister` at `0x140098886`
- `ntoskrnl!PcwUnregister` at `0x1400988a5`
- `ntoskrnl!PcwUnregister` at `0x1400988c4`
- `ntoskrnl!PcwUnregister` at `0x1400988e3`
- `ntoskrnl!PcwUnregister` at `0x140098902`
- `ntoskrnl!PcwUnregister` at `0x140098921`
- `ntoskrnl!PcwUnregister` at `0x140098848`
- `ntoskrnl!PcwUnregister` at `0x140098867`
- `ntoskrnl!PcwUnregister` at `0x140098886`
- `ntoskrnl!PcwUnregister` at `0x1400988a5`
- `ntoskrnl!PcwUnregister` at `0x1400988c4`
- `ntoskrnl!PcwUnregister` at `0x1400988e3`
- `ntoskrnl!PcwUnregister` at `0x140098902`
- `ntoskrnl!PcwUnregister` at `0x140098921`
- `ntoskrnl!IoGetDriverObjectExtension` at `0x1400987b3`
- `ntoskrnl!IoGetDriverObjectExtension` at `0x1400987b3`
- `ntoskrnl!IoDeleteSymbolicLink` at `0x140098803`
- `ntoskrnl!IoDeleteSymbolicLink` at `0x140098803`

## pseudocode

```c
__int64 __fastcall RaDriverUnload(PDRIVER_OBJECT DriverObject)
{
  PVOID DriverObjectExtension; // rax
  __int64 v3; // rdx
  __int64 v4; // rcx
  struct _UNICODE_STRING DestinationString; // [rsp+20h] [rbp-18h] BYREF

  DestinationString = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 10, WPP_61bd6e0e791f31e2ffa75bd9431aea96_Traceguids, DriverObject);
  }
  DriverObjectExtension = IoGetDriverObjectExtension(DriverObject, DriverEntry);
  RaDeleteDriver(DriverObjectExtension);
  if ( _InterlockedExchangeAdd(&InitializeCount, 0xFFFFFFFF) == 1 )
  {
    if ( StorpControl )
    {
      RtlInitUnicodeString(&DestinationString, L"\\DosDevices\\StorportControl");
      IoDeleteSymbolicLink(&DestinationString);
      IoDeleteDevice(StorpControl);
      StorpControl = 0;
    }
    if ( IsWppInitialized )
    {
      WppCleanupKm(v4, v3);
      IsWppInitialized = 0;
    }
    if ( SpPerfUnitReadCounterSet )
    {
      PcwUnregister(SpPerfUnitReadCounterSet);
      SpPerfUnitReadCounterSet = 0;
    }
    if ( SpPerfUnitWriteCounterSet )
    {
      PcwUnregister(SpPerfUnitWriteCounterSet);
      SpPerfUnitWriteCounterSet = 0;
    }
    if ( SpPerfUnitTransferCounterSet )
    {
      PcwUnregister(SpPerfUnitTransferCounterSet);
      SpPerfUnitTransferCounterSet = 0;
    }
    if ( SpPerfUnitQueueCounterSet )
    {
      PcwUnregister(SpPerfUnitQueueCounterSet);
      SpPerfUnitQueueCounterSet = 0;
    }
    if ( SpPerfNamespaceReadCounterSet )
    {
      PcwUnregister(SpPerfNamespaceReadCounterSet);
      SpPerfNamespaceReadCounterSet = 0;
    }
    if ( SpPerfNamespaceWriteCounterSet )
    {
      PcwUnregister(SpPerfNamespaceWriteCounterSet);
      SpPerfNamespaceWriteCounterSet = 0;
    }
    if ( SpPerfNamespaceTransferCounterSet )
    {
      PcwUnregister(SpPerfNamespaceTransferCounterSet);
      SpPerfNamespaceTransferCounterSet = 0;
    }
    if ( SpPerfNamespaceQueueCounterSet )
    {
      PcwUnregister(SpPerfNamespaceQueueCounterSet);
      SpPerfNamespaceQueueCounterSet = 0;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x140098760  push    rbx
0x140098762  sub     rsp, 30h
0x140098766  xorps   xmm0, xmm0
0x140098769  mov     rbx, rcx
0x14009876c  movups  xmmword ptr [rsp+38h+DestinationString.Length], xmm0
0x140098771  mov     rcx, cs:WPP_GLOBAL_Control
0x140098778  lea     rax, WPP_GLOBAL_Control
0x14009877f  cmp     rcx, rax
0x140098782  jz      short loc_1400987A9
0x140098784  mov     eax, [rcx+2Ch]
0x140098787  test    al, 2
0x140098789  jz      short loc_1400987A9
0x14009878b  cmp     byte ptr [rcx+29h], 4
0x14009878f  jb      short loc_1400987A9
0x140098791  mov     rcx, [rcx+18h]
0x140098795  lea     r8, WPP_61bd6e0e791f31e2ffa75bd9431aea96_Traceguids
0x14009879c  mov     edx, 0Ah
0x1400987a1  mov     r9, rbx
0x1400987a4  call    WPP_SF_q
0x1400987a9  lea     rdx, DriverEntry; ClientIdentificationAddress
0x1400987b0  mov     rcx, rbx; DriverObject
0x1400987b3  call    cs:__imp_IoGetDriverObjectExtension
0x1400987ba  nop     dword ptr [rax+rax+00h]
0x1400987bf  mov     rcx, rax
0x1400987c2  call    RaDeleteDriver
0x1400987c7  or      eax, 0FFFFFFFFh
0x1400987ca  lock xadd cs:InitializeCount, eax
0x1400987d2  cmp     eax, 1
0x1400987d5  jnz     loc_140098934
0x1400987db  xor     ebx, ebx
0x1400987dd  cmp     cs:StorpControl, rbx
0x1400987e4  jz      short loc_140098829
0x1400987e6  lea     rdx, aDosdevicesStor; "\\DosDevices\\StorportControl"
0x1400987ed  lea     rcx, [rsp+38h+DestinationString]; DestinationString
0x1400987f2  call    cs:__imp_RtlInitUnicodeString
0x1400987f9  nop     dword ptr [rax+rax+00h]
0x1400987fe  lea     rcx, [rsp+38h+DestinationString]; SymbolicLinkName
0x140098803  call    cs:__imp_IoDeleteSymbolicLink
0x14009880a  nop     dword ptr [rax+rax+00h]
0x14009880f  mov     rcx, cs:StorpControl; DeviceObject
0x140098816  call    cs:__imp_IoDeleteDevice
0x14009881d  nop     dword ptr [rax+rax+00h]
0x140098822  mov     cs:StorpControl, rbx
0x140098829  cmp     cs:IsWppInitialized, bl
0x14009882f  jz      short loc_14009883C
0x140098831  call    WppCleanupKm
0x140098836  mov     cs:IsWppInitialized, bl
0x14009883c  mov     rcx, cs:SpPerfUnitReadCounterSet; Registration
0x140098843  test    rcx, rcx
0x140098846  jz      short loc_14009885B
0x140098848  call    cs:__imp_PcwUnregister
0x14009884f  nop     dword ptr [rax+rax+00h]
0x140098854  mov     cs:SpPerfUnitReadCounterSet, rbx
0x14009885b  mov     rcx, cs:SpPerfUnitWriteCounterSet; Registration
0x140098862  test    rcx, rcx
0x140098865  jz      short loc_14009887A
0x140098867  call    cs:__imp_PcwUnregister
0x14009886e  nop     dword ptr [rax+rax+00h]
0x140098873  mov     cs:SpPerfUnitWriteCounterSet, rbx
0x14009887a  mov     rcx, cs:SpPerfUnitTransferCounterSet; Registration
0x140098881  test    rcx, rcx
0x140098884  jz      short loc_140098899
0x140098886  call    cs:__imp_PcwUnregister
0x14009888d  nop     dword ptr [rax+rax+00h]
0x140098892  mov     cs:SpPerfUnitTransferCounterSet, rbx
0x140098899  mov     rcx, cs:SpPerfUnitQueueCounterSet; Registration
0x1400988a0  test    rcx, rcx
0x1400988a3  jz      short loc_1400988B8
0x1400988a5  call    cs:__imp_PcwUnregister
0x1400988ac  nop     dword ptr [rax+rax+00h]
0x1400988b1  mov     cs:SpPerfUnitQueueCounterSet, rbx
0x1400988b8  mov     rcx, cs:SpPerfNamespaceReadCounterSet; Registration
0x1400988bf  test    rcx, rcx
0x1400988c2  jz      short loc_1400988D7
0x1400988c4  call    cs:__imp_PcwUnregister
0x1400988cb  nop     dword ptr [rax+rax+00h]
0x1400988d0  mov     cs:SpPerfNamespaceReadCounterSet, rbx
0x1400988d7  mov     rcx, cs:SpPerfNamespaceWriteCounterSet; Registration
0x1400988de  test    rcx, rcx
0x1400988e1  jz      short loc_1400988F6
0x1400988e3  call    cs:__imp_PcwUnregister
0x1400988ea  nop     dword ptr [rax+rax+00h]
0x1400988ef  mov     cs:SpPerfNamespaceWriteCounterSet, rbx
0x1400988f6  mov     rcx, cs:SpPerfNamespaceTransferCounterSet; Registration
0x1400988fd  test    rcx, rcx
0x140098900  jz      short loc_140098915
0x140098902  call    cs:__imp_PcwUnregister
0x140098909  nop     dword ptr [rax+rax+00h]
0x14009890e  mov     cs:SpPerfNamespaceTransferCounterSet, rbx
0x140098915  mov     rcx, cs:SpPerfNamespaceQueueCounterSet; Registration
0x14009891c  test    rcx, rcx
0x14009891f  jz      short loc_140098934
0x140098921  call    cs:__imp_PcwUnregister
0x140098928  nop     dword ptr [rax+rax+00h]
0x14009892d  mov     cs:SpPerfNamespaceQueueCounterSet, rbx
0x140098934  xor     eax, eax
0x140098936  add     rsp, 30h
0x14009893a  pop     rbx
0x14009893b  retn
```
