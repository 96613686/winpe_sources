# WdmlibIoCreateDeviceSecure

- ea: `0x1400201b0`
- end: `0x140020298`
- name: `WdmlibIoCreateDeviceSecure`
- size: `232`
- prototype: `NTSTATUS __stdcall(PDRIVER_OBJECT DriverObject, ULONG DeviceExtensionSize, PUNICODE_STRING DeviceName, ULONG DeviceType, ULONG DeviceCharacteristics, BOOLEAN Exclusive, PCUNICODE_STRING DefaultSDDLString, LPCGUID DeviceClassGuid, PDEVICE_OBJECT *DeviceObject)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x140022078`

## callees

- `0x14000f9e0`
- `0x1400201b0`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x1400201dd`
- `ntoskrnl!RtlInitUnicodeString` at `0x140020220`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400201dd`
- `ntoskrnl!RtlInitUnicodeString` at `0x140020220`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x1400201ee`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x140020231`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x1400201ee`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x140020231`

## string_xrefs

- `0x1400201cc`: `IoCreateDeviceSecure`
- `0x140020214`: `IoValidateDeviceIoControlAccess`

## pseudocode

```c
NTSTATUS __stdcall WdmlibIoCreateDeviceSecure(
        PDRIVER_OBJECT DriverObject,
        ULONG DeviceExtensionSize,
        PUNICODE_STRING DeviceName,
        ULONG DeviceType,
        ULONG DeviceCharacteristics,
        BOOLEAN Exclusive,
        PCUNICODE_STRING DefaultSDDLString,
        LPCGUID DeviceClassGuid,
        PDEVICE_OBJECT *DeviceObject)
{
  struct _UNICODE_STRING DestinationString; // [rsp+50h] [rbp-18h] BYREF

  if ( !WdmlibInitialized )
  {
    DestinationString = 0;
    RtlInitUnicodeString(&DestinationString, L"IoCreateDeviceSecure");
    PfnIoCreateDeviceSecure = (__int64)MmGetSystemRoutineAddress(&DestinationString);
    if ( !PfnIoCreateDeviceSecure )
      PfnIoCreateDeviceSecure = (__int64)IoDevObjCreateDeviceSecure;
    RtlInitUnicodeString(&DestinationString, L"IoValidateDeviceIoControlAccess");
    MmGetSystemRoutineAddress(&DestinationString);
    WdmlibInitialized = 1;
  }
  return ((__int64 (__fastcall *)(PDRIVER_OBJECT, _QWORD, PUNICODE_STRING, __int64, int, _BYTE, const UNICODE_STRING *, _QWORD, PDEVICE_OBJECT *))PfnIoCreateDeviceSecure)(
           DriverObject,
           0,
           DeviceName,
           34,
           256,
           0,
           &SDDL_DEVOBJ_SYS_ALL_ADM_ALL,
           0,
           &::DeviceObject);
}

```

## disassembly

```asm
0x1400201b0  mov     [rsp+arg_0], rbx
0x1400201b5  push    rdi
0x1400201b6  sub     rsp, 60h
0x1400201ba  cmp     cs:WdmlibInitialized, 0
0x1400201c1  mov     rbx, r8
0x1400201c4  mov     rdi, rcx
0x1400201c7  jnz     short loc_140020244
0x1400201c9  xorps   xmm0, xmm0
0x1400201cc  lea     rdx, aIocreatedevice; "IoCreateDeviceSecure"
0x1400201d3  lea     rcx, [rsp+68h+DestinationString]; DestinationString
0x1400201d8  movups  xmmword ptr [rsp+68h+DestinationString.Length], xmm0
0x1400201dd  call    cs:__imp_RtlInitUnicodeString
0x1400201e4  nop     dword ptr [rax+rax+00h]
0x1400201e9  lea     rcx, [rsp+68h+DestinationString]; SystemRoutineName
0x1400201ee  call    cs:__imp_MmGetSystemRoutineAddress
0x1400201f5  nop     dword ptr [rax+rax+00h]
0x1400201fa  mov     cs:PfnIoCreateDeviceSecure, rax
0x140020201  test    rax, rax
0x140020204  jnz     short loc_140020214
0x140020206  lea     rax, IoDevObjCreateDeviceSecure
0x14002020d  mov     cs:PfnIoCreateDeviceSecure, rax
0x140020214  lea     rdx, aIovalidatedevi; "IoValidateDeviceIoControlAccess"
0x14002021b  lea     rcx, [rsp+68h+DestinationString]; DestinationString
0x140020220  call    cs:__imp_RtlInitUnicodeString
0x140020227  nop     dword ptr [rax+rax+00h]
0x14002022c  lea     rcx, [rsp+68h+DestinationString]; SystemRoutineName
0x140020231  call    cs:__imp_MmGetSystemRoutineAddress
0x140020238  nop     dword ptr [rax+rax+00h]
0x14002023d  mov     cs:WdmlibInitialized, 1
0x140020244  mov     rax, cs:PfnIoCreateDeviceSecure
0x14002024b  lea     rcx, DeviceObject
0x140020252  mov     [rsp+68h+var_28], rcx
0x140020257  mov     r9d, 22h ; '"'
0x14002025d  mov     [rsp+68h+var_30], 0
0x140020266  lea     rcx, SDDL_DEVOBJ_SYS_ALL_ADM_ALL
0x14002026d  mov     [rsp+68h+var_38], rcx
0x140020272  mov     r8, rbx
0x140020275  mov     [rsp+68h+var_40], 0
0x14002027a  mov     rcx, rdi
0x14002027d  xor     edx, edx
0x14002027f  mov     [rsp+68h+var_48], 100h
0x140020287  call    _guard_dispatch_icall
0x14002028c  mov     rbx, [rsp+68h+arg_0]
0x140020291  add     rsp, 60h
0x140020295  pop     rdi
0x140020296  retn
```
