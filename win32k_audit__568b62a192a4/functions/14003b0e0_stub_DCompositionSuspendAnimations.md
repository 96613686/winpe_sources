# _stub_DCompositionSuspendAnimations

- ea: `0x14003b0e0`
- end: `0x14003b187`
- name: `_stub_DCompositionSuspendAnimations`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x14003b0e0`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x14003b129`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x14003b129`

## string_xrefs

- `0x14003b10f`: `NtDCompositionSuspendAnimations`

## pseudocode

```c
__int64 stub_DCompositionSuspendAnimations()
{
  __int64 result; // rax

  if ( !(unsigned __int8)IsWin32KSyscallFiltered() )
    return NtDCompositionSuspendAnimations();
  NtUserWin32kSysCallFilterStub();
  if ( !(unsigned __int8)PsIsWin32KFilterEnabled() )
    return NtDCompositionSuspendAnimations();
  result = (unsigned int)*((char *)&W32pServiceTableFilter[39] + 4 * (unsigned int)W32pServiceLimitFilter + 7);
  if ( (int)result > 0 )
    return 3221225500LL;
  return result;
}

```

## disassembly

```asm
0x14003b0e0  sub     rsp, 48h
0x14003b0e4  mov     [rsp+48h+var_28], rcx
0x14003b0e9  mov     [rsp+48h+var_20], rdx
0x14003b0ee  mov     [rsp+48h+var_18], r8
0x14003b0f3  mov     [rsp+48h+var_10], r9
0x14003b0f8  mov     rcx, 13Fh
0x14003b0ff  call    cs:__imp_IsWin32KSyscallFiltered
0x14003b106  nop     dword ptr [rax+rax+00h]
0x14003b10b  test    al, al
0x14003b10d  jz      short loc_14003B163
0x14003b10f  lea     rcx, aNtdcomposition_43; "NtDCompositionSuspendAnimations"
0x14003b116  mov     rdx, 13Fh
0x14003b11d  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x14003b124  nop     dword ptr [rax+rax+00h]
0x14003b129  call    cs:__imp_PsIsWin32KFilterEnabled
0x14003b130  nop     dword ptr [rax+rax+00h]
0x14003b135  test    al, al
0x14003b137  jz      short loc_14003B163
0x14003b139  lea     rcx, W32pServiceTableFilter
0x14003b140  mov     edx, cs:W32pServiceLimitFilter
0x14003b146  mov     rax, 13Fh
0x14003b14d  lea     rcx, [rcx+rdx*4]
0x14003b151  movsx   eax, byte ptr [rcx+rax]
0x14003b155  or      eax, eax
0x14003b157  jle     short loc_14003B15E
0x14003b159  mov     eax, 0C000001Ch
0x14003b15e  add     rsp, 48h
0x14003b162  retn
0x14003b163  mov     rax, cs:__imp_NtDCompositionSuspendAnimations
0x14003b16a  mov     rcx, [rsp+48h+var_28]
0x14003b16f  mov     rdx, [rsp+48h+var_20]
0x14003b174  mov     r8, [rsp+48h+var_18]
0x14003b179  mov     r9, [rsp+48h+var_10]
0x14003b17e  add     rsp, 48h
0x14003b182  jmp     rax
```
