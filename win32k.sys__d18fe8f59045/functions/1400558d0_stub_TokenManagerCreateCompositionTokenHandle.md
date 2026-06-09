# _stub_TokenManagerCreateCompositionTokenHandle

- ea: `0x1400558d0`
- end: `0x140055977`
- name: `_stub_TokenManagerCreateCompositionTokenHandle`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x1400558d0`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140055919`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140055919`
- `ext-ms-win-core-win32k-tokenmgr-l1-1-0!NtTokenManagerCreateCompositionTokenHandle` at `0x140055953`

## string_xrefs

- `0x1400558ff`: `NtTokenManagerCreateCompositionTokenHandle`

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
  result = (unsigned int)*((char *)&W32pServiceTableFilter[116] + 4 * (unsigned int)W32pServiceLimitFilter + 5);
  if ( (int)result > 0 )
    return 3221225500LL;
  return result;
}

```

## disassembly

```asm
0x1400558d0  sub     rsp, 48h
0x1400558d4  mov     [rsp+48h+var_28], rcx
0x1400558d9  mov     [rsp+48h+var_20], rdx
0x1400558de  mov     [rsp+48h+var_18], r8
0x1400558e3  mov     [rsp+48h+var_10], r9
0x1400558e8  mov     rcx, 3A5h
0x1400558ef  call    cs:__imp_IsWin32KSyscallFiltered
0x1400558f6  nop     dword ptr [rax+rax+00h]
0x1400558fb  test    al, al
0x1400558fd  jz      short loc_140055953
0x1400558ff  lea     rcx, aNttokenmanager; "NtTokenManagerCreateCompositionTokenHan"...
0x140055906  mov     rdx, 3A5h
0x14005590d  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x140055914  nop     dword ptr [rax+rax+00h]
0x140055919  call    cs:__imp_PsIsWin32KFilterEnabled
0x140055920  nop     dword ptr [rax+rax+00h]
0x140055925  test    al, al
0x140055927  jz      short loc_140055953
0x140055929  lea     rcx, W32pServiceTableFilter
0x140055930  mov     edx, cs:W32pServiceLimitFilter
0x140055936  mov     rax, 3A5h
0x14005593d  lea     rcx, [rcx+rdx*4]
0x140055941  movsx   eax, byte ptr [rcx+rax]
0x140055945  or      eax, eax
0x140055947  jle     short loc_14005594E
0x140055949  mov     eax, 0C000001Ch
0x14005594e  add     rsp, 48h
0x140055952  retn
0x140055953  mov     rax, cs:__imp_NtTokenManagerCreateCompositionTokenHandle
0x14005595a  mov     rcx, [rsp+48h+var_28]
0x14005595f  mov     rdx, [rsp+48h+var_20]
0x140055964  mov     r8, [rsp+48h+var_18]
0x140055969  mov     r9, [rsp+48h+var_10]
0x14005596e  add     rsp, 48h
0x140055972  jmp     rax
```
