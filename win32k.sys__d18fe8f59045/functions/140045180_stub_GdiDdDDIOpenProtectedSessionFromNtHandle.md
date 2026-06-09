# _stub_GdiDdDDIOpenProtectedSessionFromNtHandle

- ea: `0x140045180`
- end: `0x140045227`
- name: `_stub_GdiDdDDIOpenProtectedSessionFromNtHandle`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x140045180`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x1400451c9`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x1400451c9`
- `ext-ms-win-core-win32k-dxgk-l1-1-0!NtGdiDdDDIOpenProtectedSessionFromNtHandle` at `0x140045203`

## string_xrefs

- `0x1400451af`: `NtGdiDdDDIOpenProtectedSessionFromNtHandle`

## pseudocode

```c
__int64 __fastcall stub_GdiDdDDIOpenProtectedSessionFromNtHandle(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 result; // rax

  if ( !(unsigned __int8)IsWin32KSyscallFiltered() )
    return NtGdiDdDDIOpenProtectedSessionFromNtHandle(a1, a2, a3, a4);
  NtUserWin32kSysCallFilterStub();
  if ( !(unsigned __int8)PsIsWin32KFilterEnabled() )
    return NtGdiDdDDIOpenProtectedSessionFromNtHandle(a1, a2, a3, a4);
  result = (unsigned int)*((char *)&W32pServiceTableFilter[68] + 4 * (unsigned int)W32pServiceLimitFilter + 6);
  if ( (int)result > 0 )
    return 3221225500LL;
  return result;
}

```

## disassembly

```asm
0x140045180  sub     rsp, 48h
0x140045184  mov     [rsp+48h+var_28], rcx
0x140045189  mov     [rsp+48h+var_20], rdx
0x14004518e  mov     [rsp+48h+var_18], r8
0x140045193  mov     [rsp+48h+var_10], r9
0x140045198  mov     rcx, 226h
0x14004519f  call    cs:__imp_IsWin32KSyscallFiltered
0x1400451a6  nop     dword ptr [rax+rax+00h]
0x1400451ab  test    al, al
0x1400451ad  jz      short loc_140045203
0x1400451af  lea     rcx, aNtgdiddddiopen_7; "NtGdiDdDDIOpenProtectedSessionFromNtHan"...
0x1400451b6  mov     rdx, 226h
0x1400451bd  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x1400451c4  nop     dword ptr [rax+rax+00h]
0x1400451c9  call    cs:__imp_PsIsWin32KFilterEnabled
0x1400451d0  nop     dword ptr [rax+rax+00h]
0x1400451d5  test    al, al
0x1400451d7  jz      short loc_140045203
0x1400451d9  lea     rcx, W32pServiceTableFilter
0x1400451e0  mov     edx, cs:W32pServiceLimitFilter
0x1400451e6  mov     rax, 226h
0x1400451ed  lea     rcx, [rcx+rdx*4]
0x1400451f1  movsx   eax, byte ptr [rcx+rax]
0x1400451f5  or      eax, eax
0x1400451f7  jle     short loc_1400451FE
0x1400451f9  mov     eax, 0C000001Ch
0x1400451fe  add     rsp, 48h
0x140045202  retn
0x140045203  mov     rax, cs:__imp_NtGdiDdDDIOpenProtectedSessionFromNtHandle
0x14004520a  mov     rcx, [rsp+48h+var_28]
0x14004520f  mov     rdx, [rsp+48h+var_20]
0x140045214  mov     r8, [rsp+48h+var_18]
0x140045219  mov     r9, [rsp+48h+var_10]
0x14004521e  add     rsp, 48h
0x140045222  jmp     rax
```
