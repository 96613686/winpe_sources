# _stub_TokenManagerCreateCompositionTokenHandle

- ea: `0x1400554f0`
- end: `0x140055597`
- name: `_stub_TokenManagerCreateCompositionTokenHandle`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x1400554f0`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140055539`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140055539`
- `ext-ms-win-core-win32k-tokenmgr-l1-1-0!NtTokenManagerCreateCompositionTokenHandle` at `0x140055573`

## string_xrefs

- `0x14005551f`: `NtTokenManagerCreateCompositionTokenHandle`

## pseudocode

```c
__int64 __fastcall stub_TokenManagerCreateCompositionTokenHandle(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 result; // rax

  if ( !(unsigned __int8)IsWin32KSyscallFiltered() )
    return NtTokenManagerCreateCompositionTokenHandle(a1, a2, a3, a4);
  NtUserWin32kSysCallFilterStub();
  if ( !(unsigned __int8)PsIsWin32KFilterEnabled() )
    return NtTokenManagerCreateCompositionTokenHandle(a1, a2, a3, a4);
  result = (unsigned int)*((char *)&W32pServiceTableFilter[116] + 4 * (unsigned int)W32pServiceLimitFilter + 2);
  if ( (int)result > 0 )
    return 3221225500LL;
  return result;
}

```

## disassembly

```asm
0x1400554f0  sub     rsp, 48h
0x1400554f4  mov     [rsp+48h+var_28], rcx
0x1400554f9  mov     [rsp+48h+var_20], rdx
0x1400554fe  mov     [rsp+48h+var_18], r8
0x140055503  mov     [rsp+48h+var_10], r9
0x140055508  mov     rcx, 3A2h
0x14005550f  call    cs:__imp_IsWin32KSyscallFiltered
0x140055516  nop     dword ptr [rax+rax+00h]
0x14005551b  test    al, al
0x14005551d  jz      short loc_140055573
0x14005551f  lea     rcx, aNttokenmanager; "NtTokenManagerCreateCompositionTokenHan"...
0x140055526  mov     rdx, 3A2h
0x14005552d  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x140055534  nop     dword ptr [rax+rax+00h]
0x140055539  call    cs:__imp_PsIsWin32KFilterEnabled
0x140055540  nop     dword ptr [rax+rax+00h]
0x140055545  test    al, al
0x140055547  jz      short loc_140055573
0x140055549  lea     rcx, W32pServiceTableFilter
0x140055550  mov     edx, cs:W32pServiceLimitFilter
0x140055556  mov     rax, 3A2h
0x14005555d  lea     rcx, [rcx+rdx*4]
0x140055561  movsx   eax, byte ptr [rcx+rax]
0x140055565  or      eax, eax
0x140055567  jle     short loc_14005556E
0x140055569  mov     eax, 0C000001Ch
0x14005556e  add     rsp, 48h
0x140055572  retn
0x140055573  mov     rax, cs:__imp_NtTokenManagerCreateCompositionTokenHandle
0x14005557a  mov     rcx, [rsp+48h+var_28]
0x14005557f  mov     rdx, [rsp+48h+var_20]
0x140055584  mov     r8, [rsp+48h+var_18]
0x140055589  mov     r9, [rsp+48h+var_10]
0x14005558e  add     rsp, 48h
0x140055592  jmp     rax
```
