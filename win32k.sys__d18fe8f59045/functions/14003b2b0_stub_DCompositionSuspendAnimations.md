# _stub_DCompositionSuspendAnimations

- ea: `0x14003b2b0`
- end: `0x14003b357`
- name: `_stub_DCompositionSuspendAnimations`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x14003b2b0`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x14003b2f9`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x14003b2f9`

## string_xrefs

- `0x14003b2df`: `NtDCompositionSuspendAnimations`

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
0x14003b2b0  sub     rsp, 48h
0x14003b2b4  mov     [rsp+48h+var_28], rcx
0x14003b2b9  mov     [rsp+48h+var_20], rdx
0x14003b2be  mov     [rsp+48h+var_18], r8
0x14003b2c3  mov     [rsp+48h+var_10], r9
0x14003b2c8  mov     rcx, 13Fh
0x14003b2cf  call    cs:__imp_IsWin32KSyscallFiltered
0x14003b2d6  nop     dword ptr [rax+rax+00h]
0x14003b2db  test    al, al
0x14003b2dd  jz      short loc_14003B333
0x14003b2df  lea     rcx, aNtdcomposition_43; "NtDCompositionSuspendAnimations"
0x14003b2e6  mov     rdx, 13Fh
0x14003b2ed  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x14003b2f4  nop     dword ptr [rax+rax+00h]
0x14003b2f9  call    cs:__imp_PsIsWin32KFilterEnabled
0x14003b300  nop     dword ptr [rax+rax+00h]
0x14003b305  test    al, al
0x14003b307  jz      short loc_14003B333
0x14003b309  lea     rcx, W32pServiceTableFilter
0x14003b310  mov     edx, cs:W32pServiceLimitFilter
0x14003b316  mov     rax, 13Fh
0x14003b31d  lea     rcx, [rcx+rdx*4]
0x14003b321  movsx   eax, byte ptr [rcx+rax]
0x14003b325  or      eax, eax
0x14003b327  jle     short loc_14003B32E
0x14003b329  mov     eax, 0C000001Ch
0x14003b32e  add     rsp, 48h
0x14003b332  retn
0x14003b333  mov     rax, cs:__imp_NtDCompositionSuspendAnimations
0x14003b33a  mov     rcx, [rsp+48h+var_28]
0x14003b33f  mov     rdx, [rsp+48h+var_20]
0x14003b344  mov     r8, [rsp+48h+var_18]
0x14003b349  mov     r9, [rsp+48h+var_10]
0x14003b34e  add     rsp, 48h
0x14003b352  jmp     rax
```
