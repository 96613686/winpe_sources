# GetContextSwitchCount(ulong *)

- ea: `0x180002d54`
- end: `0x180002dd6`
- name: `?GetContextSwitchCount@@YAHPEAK@Z`
- size: `130`
- prototype: `__int64 __fastcall(unsigned int *)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180001160`
- `0x1800035c0`

## callees

- `0x180002d54`
- `0x1800041a6`
- `0x1800041d0`

## import_xrefs

- `ntdll!NtQuerySystemInformation` at `0x180002da1`
- `ntdll!NtQuerySystemInformation` at `0x180002da1`

## pseudocode

```c
__int64 __fastcall GetContextSwitchCount(unsigned int *a1)
{
  ULONG ReturnLength[4]; // [rsp+20h] [rbp-1A8h] BYREF
  _BYTE SystemInformation[296]; // [rsp+30h] [rbp-198h] BYREF
  unsigned int v5; // [rsp+158h] [rbp-70h]

  memset_0(SystemInformation, 0, 0x178u);
  ReturnLength[0] = 0;
  if ( NtQuerySystemInformation(SystemPerformanceInformation, SystemInformation, 0x178u, ReturnLength) < 0 )
    return 0;
  *a1 = v5;
  return 1;
}

```

## disassembly

```asm
0x180002d54  push    rbx
0x180002d56  sub     rsp, 1C0h
0x180002d5d  mov     rax, cs:__security_cookie
0x180002d64  xor     rax, rsp
0x180002d67  mov     [rsp+1C8h+var_18], rax
0x180002d6f  mov     rbx, rcx
0x180002d72  xor     edx, edx; Val
0x180002d74  lea     rcx, [rsp+1C8h+SystemInformation]; void *
0x180002d79  mov     r8d, 178h; Size
0x180002d7f  call    memset_0
0x180002d84  lea     r9, [rsp+1C8h+ReturnLength]; ReturnLength
0x180002d89  mov     [rsp+1C8h+ReturnLength], 0
0x180002d91  mov     r8d, 178h; SystemInformationLength
0x180002d97  lea     rdx, [rsp+1C8h+SystemInformation]; SystemInformation
0x180002d9c  mov     ecx, 2; SystemInformationClass
0x180002da1  call    cs:__imp_NtQuerySystemInformation
0x180002da7  test    eax, eax
0x180002da9  jns     short loc_180002DAF
0x180002dab  xor     eax, eax
0x180002dad  jmp     short loc_180002DBD
0x180002daf  mov     eax, [rsp+1C8h+var_70]
0x180002db6  mov     [rbx], eax
0x180002db8  mov     eax, 1
0x180002dbd  mov     rcx, [rsp+1C8h+var_18]
0x180002dc5  xor     rcx, rsp; StackCookie
0x180002dc8  call    __security_check_cookie
0x180002dcd  add     rsp, 1C0h
0x180002dd4  pop     rbx
0x180002dd5  retn
```
