# WdmlibInit

- ea: `0x140017f98`
- end: `0x14001801d`
- name: `WdmlibInit`
- size: `133`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140018024`

## callees

- `0x140017f98`

## import_xrefs

- `ntoskrnl!MmGetSystemRoutineAddress` at `0x140017fc1`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x140018004`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x140017fc1`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x140018004`
- `ntoskrnl!RtlInitUnicodeString` at `0x140017fb0`
- `ntoskrnl!RtlInitUnicodeString` at `0x140017ff3`
- `ntoskrnl!RtlInitUnicodeString` at `0x140017fb0`
- `ntoskrnl!RtlInitUnicodeString` at `0x140017ff3`

## string_xrefs

- `0x140017f9f`: `IoCreateDeviceSecure`
- `0x140017fe7`: `IoValidateDeviceIoControlAccess`

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
0x140017f98  sub     rsp, 38h
0x140017f9c  xorps   xmm0, xmm0
0x140017f9f  lea     rdx, SourceString; "IoCreateDeviceSecure"
0x140017fa6  lea     rcx, [rsp+38h+DestinationString]; DestinationString
0x140017fab  movups  xmmword ptr [rsp+38h+DestinationString.Length], xmm0
0x140017fb0  call    cs:__imp_RtlInitUnicodeString
0x140017fb7  nop     dword ptr [rax+rax+00h]
0x140017fbc  lea     rcx, [rsp+38h+DestinationString]; SystemRoutineName
0x140017fc1  call    cs:__imp_MmGetSystemRoutineAddress
0x140017fc8  nop     dword ptr [rax+rax+00h]
0x140017fcd  mov     cs:PfnIoCreateDeviceSecure, rax
0x140017fd4  test    rax, rax
0x140017fd7  jnz     short loc_140017FE7
0x140017fd9  lea     rax, IoDevObjCreateDeviceSecure
0x140017fe0  mov     cs:PfnIoCreateDeviceSecure, rax
0x140017fe7  lea     rdx, aIovalidatedevi; "IoValidateDeviceIoControlAccess"
0x140017fee  lea     rcx, [rsp+38h+DestinationString]; DestinationString
0x140017ff3  call    cs:__imp_RtlInitUnicodeString
0x140017ffa  nop     dword ptr [rax+rax+00h]
0x140017fff  lea     rcx, [rsp+38h+DestinationString]; SystemRoutineName
0x140018004  call    cs:__imp_MmGetSystemRoutineAddress
0x14001800b  nop     dword ptr [rax+rax+00h]
0x140018010  mov     cs:WdmlibInitialized, 1
0x140018017  add     rsp, 38h
0x14001801b  retn
```
