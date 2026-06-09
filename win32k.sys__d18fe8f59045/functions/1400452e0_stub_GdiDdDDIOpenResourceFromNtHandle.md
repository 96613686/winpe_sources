# _stub_GdiDdDDIOpenResourceFromNtHandle

- ea: `0x1400452e0`
- end: `0x140045387`
- name: `_stub_GdiDdDDIOpenResourceFromNtHandle`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x1400452e0`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140045329`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140045329`
- `ext-ms-win-core-win32k-dxgk-l1-1-0!NtGdiDdDDIOpenResourceFromNtHandle` at `0x140045363`

## string_xrefs

- `0x14004530f`: `NtGdiDdDDIOpenResourceFromNtHandle`

## pseudocode

```c
__int64 __fastcall stub_GdiDdDDIOpenResourceFromNtHandle(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 result; // rax

  if ( !(unsigned __int8)IsWin32KSyscallFiltered() )
    return NtGdiDdDDIOpenResourceFromNtHandle(a1, a2, a3, a4);
  NtUserWin32kSysCallFilterStub();
  if ( !(unsigned __int8)PsIsWin32KFilterEnabled() )
    return NtGdiDdDDIOpenResourceFromNtHandle(a1, a2, a3, a4);
  result = (unsigned int)*((char *)&W32pServiceTableFilter[69] + 4 * (unsigned int)W32pServiceLimitFilter);
  if ( (int)result > 0 )
    return 3221225500LL;
  return result;
}

```

## disassembly

```asm
0x1400452e0  sub     rsp, 48h
0x1400452e4  mov     [rsp+48h+var_28], rcx
0x1400452e9  mov     [rsp+48h+var_20], rdx
0x1400452ee  mov     [rsp+48h+var_18], r8
0x1400452f3  mov     [rsp+48h+var_10], r9
0x1400452f8  mov     rcx, 228h
0x1400452ff  call    cs:__imp_IsWin32KSyscallFiltered
0x140045306  nop     dword ptr [rax+rax+00h]
0x14004530b  test    al, al
0x14004530d  jz      short loc_140045363
0x14004530f  lea     rcx, aNtgdiddddiopen_9; "NtGdiDdDDIOpenResourceFromNtHandle"
0x140045316  mov     rdx, 228h
0x14004531d  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x140045324  nop     dword ptr [rax+rax+00h]
0x140045329  call    cs:__imp_PsIsWin32KFilterEnabled
0x140045330  nop     dword ptr [rax+rax+00h]
0x140045335  test    al, al
0x140045337  jz      short loc_140045363
0x140045339  lea     rcx, W32pServiceTableFilter
0x140045340  mov     edx, cs:W32pServiceLimitFilter
0x140045346  mov     rax, 228h
0x14004534d  lea     rcx, [rcx+rdx*4]
0x140045351  movsx   eax, byte ptr [rcx+rax]
0x140045355  or      eax, eax
0x140045357  jle     short loc_14004535E
0x140045359  mov     eax, 0C000001Ch
0x14004535e  add     rsp, 48h
0x140045362  retn
0x140045363  mov     rax, cs:__imp_NtGdiDdDDIOpenResourceFromNtHandle
0x14004536a  mov     rcx, [rsp+48h+var_28]
0x14004536f  mov     rdx, [rsp+48h+var_20]
0x140045374  mov     r8, [rsp+48h+var_18]
0x140045379  mov     r9, [rsp+48h+var_10]
0x14004537e  add     rsp, 48h
0x140045382  jmp     rax
```
