# _stub_UnBindCompositionSurface

- ea: `0x140055c40`
- end: `0x140055ce7`
- name: `_stub_UnBindCompositionSurface`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x140055c40`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140055c89`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140055c89`
- `ext-ms-win-core-win32k-surfmgr-l1-1-1!NtUnBindCompositionSurface` at `0x140055cc3`

## string_xrefs

- `0x140055c6f`: `NtUnBindCompositionSurface`

## pseudocode

```c
__int64 __fastcall stub_UnBindCompositionSurface(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 result; // rax

  if ( !(unsigned __int8)IsWin32KSyscallFiltered() )
    return NtUnBindCompositionSurface(a1, a2, a3, a4);
  NtUserWin32kSysCallFilterStub();
  if ( !(unsigned __int8)PsIsWin32KFilterEnabled() )
    return NtUnBindCompositionSurface(a1, a2, a3, a4);
  result = (unsigned int)*((char *)&W32pServiceTableFilter[117] + 4 * (unsigned int)W32pServiceLimitFilter + 2);
  if ( (int)result > 0 )
    return 3221225500LL;
  return result;
}

```

## disassembly

```asm
0x140055c40  sub     rsp, 48h
0x140055c44  mov     [rsp+48h+var_28], rcx
0x140055c49  mov     [rsp+48h+var_20], rdx
0x140055c4e  mov     [rsp+48h+var_18], r8
0x140055c53  mov     [rsp+48h+var_10], r9
0x140055c58  mov     rcx, 3AAh
0x140055c5f  call    cs:__imp_IsWin32KSyscallFiltered
0x140055c66  nop     dword ptr [rax+rax+00h]
0x140055c6b  test    al, al
0x140055c6d  jz      short loc_140055CC3
0x140055c6f  lea     rcx, aNtunbindcompos; "NtUnBindCompositionSurface"
0x140055c76  mov     rdx, 3AAh
0x140055c7d  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x140055c84  nop     dword ptr [rax+rax+00h]
0x140055c89  call    cs:__imp_PsIsWin32KFilterEnabled
0x140055c90  nop     dword ptr [rax+rax+00h]
0x140055c95  test    al, al
0x140055c97  jz      short loc_140055CC3
0x140055c99  lea     rcx, W32pServiceTableFilter
0x140055ca0  mov     edx, cs:W32pServiceLimitFilter
0x140055ca6  mov     rax, 3AAh
0x140055cad  lea     rcx, [rcx+rdx*4]
0x140055cb1  movsx   eax, byte ptr [rcx+rax]
0x140055cb5  or      eax, eax
0x140055cb7  jle     short loc_140055CBE
0x140055cb9  mov     eax, 0C000001Ch
0x140055cbe  add     rsp, 48h
0x140055cc2  retn
0x140055cc3  mov     rax, cs:__imp_NtUnBindCompositionSurface
0x140055cca  mov     rcx, [rsp+48h+var_28]
0x140055ccf  mov     rdx, [rsp+48h+var_20]
0x140055cd4  mov     r8, [rsp+48h+var_18]
0x140055cd9  mov     r9, [rsp+48h+var_10]
0x140055cde  add     rsp, 48h
0x140055ce2  jmp     rax
```
