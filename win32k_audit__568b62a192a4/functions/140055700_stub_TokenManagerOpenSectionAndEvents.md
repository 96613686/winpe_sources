# _stub_TokenManagerOpenSectionAndEvents

- ea: `0x140055700`
- end: `0x1400557a7`
- name: `_stub_TokenManagerOpenSectionAndEvents`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x140055700`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140055749`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140055749`
- `ext-ms-win-core-win32k-tokenmgr-l1-1-0!NtTokenManagerOpenSectionAndEvents` at `0x140055783`

## string_xrefs

- `0x14005572f`: `NtTokenManagerOpenSectionAndEvents`

## pseudocode

```c
__int64 __fastcall stub_TokenManagerOpenSectionAndEvents(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 result; // rax

  if ( !(unsigned __int8)IsWin32KSyscallFiltered() )
    return NtTokenManagerOpenSectionAndEvents(a1, a2, a3, a4);
  NtUserWin32kSysCallFilterStub();
  if ( !(unsigned __int8)PsIsWin32KFilterEnabled() )
    return NtTokenManagerOpenSectionAndEvents(a1, a2, a3, a4);
  result = (unsigned int)*((char *)&W32pServiceTableFilter[116] + 4 * (unsigned int)W32pServiceLimitFilter + 5);
  if ( (int)result > 0 )
    return 3221225500LL;
  return result;
}

```

## disassembly

```asm
0x140055700  sub     rsp, 48h
0x140055704  mov     [rsp+48h+var_28], rcx
0x140055709  mov     [rsp+48h+var_20], rdx
0x14005570e  mov     [rsp+48h+var_18], r8
0x140055713  mov     [rsp+48h+var_10], r9
0x140055718  mov     rcx, 3A5h
0x14005571f  call    cs:__imp_IsWin32KSyscallFiltered
0x140055726  nop     dword ptr [rax+rax+00h]
0x14005572b  test    al, al
0x14005572d  jz      short loc_140055783
0x14005572f  lea     rcx, aNttokenmanager_2; "NtTokenManagerOpenSectionAndEvents"
0x140055736  mov     rdx, 3A5h
0x14005573d  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x140055744  nop     dword ptr [rax+rax+00h]
0x140055749  call    cs:__imp_PsIsWin32KFilterEnabled
0x140055750  nop     dword ptr [rax+rax+00h]
0x140055755  test    al, al
0x140055757  jz      short loc_140055783
0x140055759  lea     rcx, W32pServiceTableFilter
0x140055760  mov     edx, cs:W32pServiceLimitFilter
0x140055766  mov     rax, 3A5h
0x14005576d  lea     rcx, [rcx+rdx*4]
0x140055771  movsx   eax, byte ptr [rcx+rax]
0x140055775  or      eax, eax
0x140055777  jle     short loc_14005577E
0x140055779  mov     eax, 0C000001Ch
0x14005577e  add     rsp, 48h
0x140055782  retn
0x140055783  mov     rax, cs:__imp_NtTokenManagerOpenSectionAndEvents
0x14005578a  mov     rcx, [rsp+48h+var_28]
0x14005578f  mov     rdx, [rsp+48h+var_20]
0x140055794  mov     r8, [rsp+48h+var_18]
0x140055799  mov     r9, [rsp+48h+var_10]
0x14005579e  add     rsp, 48h
0x1400557a2  jmp     rax
```
