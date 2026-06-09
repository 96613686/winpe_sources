# _stub_TokenManagerThread

- ea: `0x140055b90`
- end: `0x140055c37`
- name: `_stub_TokenManagerThread`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x140055b90`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140055bd9`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140055bd9`
- `ext-ms-win-core-win32k-tokenmgr-l1-1-0!NtTokenManagerThread` at `0x140055c13`

## string_xrefs

- `0x140055bbf`: `NtTokenManagerThread`

## pseudocode

```c
__int64 __fastcall stub_TokenManagerThread(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 result; // rax

  if ( !(unsigned __int8)IsWin32KSyscallFiltered() )
    return NtTokenManagerThread(a1, a2, a3, a4);
  NtUserWin32kSysCallFilterStub();
  if ( !(unsigned __int8)PsIsWin32KFilterEnabled() )
    return NtTokenManagerThread(a1, a2, a3, a4);
  result = (unsigned int)*((char *)&W32pServiceTableFilter[117] + 4 * (unsigned int)W32pServiceLimitFilter + 1);
  if ( (int)result > 0 )
    return 3221225500LL;
  return result;
}

```

## disassembly

```asm
0x140055b90  sub     rsp, 48h
0x140055b94  mov     [rsp+48h+var_28], rcx
0x140055b99  mov     [rsp+48h+var_20], rdx
0x140055b9e  mov     [rsp+48h+var_18], r8
0x140055ba3  mov     [rsp+48h+var_10], r9
0x140055ba8  mov     rcx, 3A9h
0x140055baf  call    cs:__imp_IsWin32KSyscallFiltered
0x140055bb6  nop     dword ptr [rax+rax+00h]
0x140055bbb  test    al, al
0x140055bbd  jz      short loc_140055C13
0x140055bbf  lea     rcx, aNttokenmanager_3; "NtTokenManagerThread"
0x140055bc6  mov     rdx, 3A9h
0x140055bcd  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x140055bd4  nop     dword ptr [rax+rax+00h]
0x140055bd9  call    cs:__imp_PsIsWin32KFilterEnabled
0x140055be0  nop     dword ptr [rax+rax+00h]
0x140055be5  test    al, al
0x140055be7  jz      short loc_140055C13
0x140055be9  lea     rcx, W32pServiceTableFilter
0x140055bf0  mov     edx, cs:W32pServiceLimitFilter
0x140055bf6  mov     rax, 3A9h
0x140055bfd  lea     rcx, [rcx+rdx*4]
0x140055c01  movsx   eax, byte ptr [rcx+rax]
0x140055c05  or      eax, eax
0x140055c07  jle     short loc_140055C0E
0x140055c09  mov     eax, 0C000001Ch
0x140055c0e  add     rsp, 48h
0x140055c12  retn
0x140055c13  mov     rax, cs:__imp_NtTokenManagerThread
0x140055c1a  mov     rcx, [rsp+48h+var_28]
0x140055c1f  mov     rdx, [rsp+48h+var_20]
0x140055c24  mov     r8, [rsp+48h+var_18]
0x140055c29  mov     r9, [rsp+48h+var_10]
0x140055c2e  add     rsp, 48h
0x140055c32  jmp     rax
```
