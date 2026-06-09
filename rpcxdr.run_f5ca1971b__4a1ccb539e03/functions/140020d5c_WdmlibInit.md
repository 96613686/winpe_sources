# WdmlibInit

- ea: `0x140020d5c`
- end: `0x140020de1`
- name: `WdmlibInit`
- size: `133`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140020de8`

## callees

- `0x140020d5c`

## import_xrefs

- `ntoskrnl!MmGetSystemRoutineAddress` at `0x140020d85`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x140020dc8`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x140020d85`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x140020dc8`
- `ntoskrnl!RtlInitUnicodeString` at `0x140020d74`
- `ntoskrnl!RtlInitUnicodeString` at `0x140020db7`
- `ntoskrnl!RtlInitUnicodeString` at `0x140020d74`
- `ntoskrnl!RtlInitUnicodeString` at `0x140020db7`

## string_xrefs

- `0x140020d63`: `IoCreateDeviceSecure`
- `0x140020dab`: `IoValidateDeviceIoControlAccess`

## pseudocode

```c
PVOID WdmlibInit()
{
  PVOID result; // rax
  struct _UNICODE_STRING DestinationString; // [rsp+20h] [rbp-18h] BYREF

  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, L"IoCreateDeviceSecure");
  PfnIoCreateDeviceSecure = (__int64)MmGetSystemRoutineAddress(&DestinationString);
  if ( !PfnIoCreateDeviceSecure )
    PfnIoCreateDeviceSecure = (__int64)IoDevObjCreateDeviceSecure;
  RtlInitUnicodeString(&DestinationString, L"IoValidateDeviceIoControlAccess");
  result = MmGetSystemRoutineAddress(&DestinationString);
  WdmlibInitialized = 1;
  return result;
}

```

## disassembly

```asm
0x140020d5c  sub     rsp, 38h
0x140020d60  xorps   xmm0, xmm0
0x140020d63  lea     rdx, aIocreatedevice; "IoCreateDeviceSecure"
0x140020d6a  lea     rcx, [rsp+38h+DestinationString]; DestinationString
0x140020d6f  movups  xmmword ptr [rsp+38h+DestinationString.Length], xmm0
0x140020d74  call    cs:__imp_RtlInitUnicodeString
0x140020d7b  nop     dword ptr [rax+rax+00h]
0x140020d80  lea     rcx, [rsp+38h+DestinationString]; SystemRoutineName
0x140020d85  call    cs:__imp_MmGetSystemRoutineAddress
0x140020d8c  nop     dword ptr [rax+rax+00h]
0x140020d91  mov     cs:PfnIoCreateDeviceSecure, rax
0x140020d98  test    rax, rax
0x140020d9b  jnz     short loc_140020DAB
0x140020d9d  lea     rax, IoDevObjCreateDeviceSecure
0x140020da4  mov     cs:PfnIoCreateDeviceSecure, rax
0x140020dab  lea     rdx, aIovalidatedevi; "IoValidateDeviceIoControlAccess"
0x140020db2  lea     rcx, [rsp+38h+DestinationString]; DestinationString
0x140020db7  call    cs:__imp_RtlInitUnicodeString
0x140020dbe  nop     dword ptr [rax+rax+00h]
0x140020dc3  lea     rcx, [rsp+38h+DestinationString]; SystemRoutineName
0x140020dc8  call    cs:__imp_MmGetSystemRoutineAddress
0x140020dcf  nop     dword ptr [rax+rax+00h]
0x140020dd4  mov     cs:WdmlibInitialized, 1
0x140020ddb  add     rsp, 38h
0x140020ddf  retn
```
