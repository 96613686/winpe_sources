# Win32kCreateDriver

- ea: `0x14001afdc`
- end: `0x14001b01e`
- name: `Win32kCreateDriver`
- size: `66`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x1400ba080`

## import_xrefs

- `ntoskrnl!IoCreateDriver` at `0x14001b00c`
- `ntoskrnl!IoCreateDriver` at `0x14001b00c`
- `ntoskrnl!RtlInitUnicodeString` at `0x14001aff4`
- `ntoskrnl!RtlInitUnicodeString` at `0x14001aff4`

## pseudocode

```c
__int64 Win32kCreateDriver()
{
  struct _UNICODE_STRING DestinationString; // [rsp+20h] [rbp-18h] BYREF

  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, L"\\Driver\\Win32k");
  return IoCreateDriver(&DestinationString, W32GetDebugState);
}

```

## disassembly

```asm
0x14001afdc  sub     rsp, 38h
0x14001afe0  xorps   xmm0, xmm0
0x14001afe3  lea     rdx, aDriverWin32k; "\\Driver\\Win32k"
0x14001afea  lea     rcx, [rsp+38h+DestinationString]; DestinationString
0x14001afef  movups  xmmword ptr [rsp+38h+DestinationString.Length], xmm0
0x14001aff4  call    cs:__imp_RtlInitUnicodeString
0x14001affb  nop     dword ptr [rax+rax+00h]
0x14001b000  lea     rdx, W32GetDebugState
0x14001b007  lea     rcx, [rsp+38h+DestinationString]
0x14001b00c  call    cs:__imp_IoCreateDriver
0x14001b013  nop     dword ptr [rax+rax+00h]
0x14001b018  add     rsp, 38h
0x14001b01c  retn
```
