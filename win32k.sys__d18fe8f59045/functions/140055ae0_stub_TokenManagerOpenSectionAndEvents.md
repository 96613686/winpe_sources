# _stub_TokenManagerOpenSectionAndEvents

- ea: `0x140055ae0`
- end: `0x140055b87`
- name: `_stub_TokenManagerOpenSectionAndEvents`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x140055ae0`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140055b29`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140055b29`
- `ext-ms-win-core-win32k-tokenmgr-l1-1-0!NtTokenManagerOpenSectionAndEvents` at `0x140055b63`

## string_xrefs

- `0x140055b0f`: `NtTokenManagerOpenSectionAndEvents`

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
  result = (unsigned int)*((char *)&W32pServiceTableFilter[117] + 4 * (unsigned int)W32pServiceLimitFilter);
  if ( (int)result > 0 )
    return 3221225500LL;
  return result;
}

```

## disassembly

```asm
0x140055ae0  sub     rsp, 48h
0x140055ae4  mov     [rsp+48h+var_28], rcx
0x140055ae9  mov     [rsp+48h+var_20], rdx
0x140055aee  mov     [rsp+48h+var_18], r8
0x140055af3  mov     [rsp+48h+var_10], r9
0x140055af8  mov     rcx, 3A8h
0x140055aff  call    cs:__imp_IsWin32KSyscallFiltered
0x140055b06  nop     dword ptr [rax+rax+00h]
0x140055b0b  test    al, al
0x140055b0d  jz      short loc_140055B63
0x140055b0f  lea     rcx, aNttokenmanager_2; "NtTokenManagerOpenSectionAndEvents"
0x140055b16  mov     rdx, 3A8h
0x140055b1d  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x140055b24  nop     dword ptr [rax+rax+00h]
0x140055b29  call    cs:__imp_PsIsWin32KFilterEnabled
0x140055b30  nop     dword ptr [rax+rax+00h]
0x140055b35  test    al, al
0x140055b37  jz      short loc_140055B63
0x140055b39  lea     rcx, W32pServiceTableFilter
0x140055b40  mov     edx, cs:W32pServiceLimitFilter
0x140055b46  mov     rax, 3A8h
0x140055b4d  lea     rcx, [rcx+rdx*4]
0x140055b51  movsx   eax, byte ptr [rcx+rax]
0x140055b55  or      eax, eax
0x140055b57  jle     short loc_140055B5E
0x140055b59  mov     eax, 0C000001Ch
0x140055b5e  add     rsp, 48h
0x140055b62  retn
0x140055b63  mov     rax, cs:__imp_NtTokenManagerOpenSectionAndEvents
0x140055b6a  mov     rcx, [rsp+48h+var_28]
0x140055b6f  mov     rdx, [rsp+48h+var_20]
0x140055b74  mov     r8, [rsp+48h+var_18]
0x140055b79  mov     r9, [rsp+48h+var_10]
0x140055b7e  add     rsp, 48h
0x140055b82  jmp     rax
```
