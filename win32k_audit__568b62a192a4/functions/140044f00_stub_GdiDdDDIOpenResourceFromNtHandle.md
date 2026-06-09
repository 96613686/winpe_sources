# _stub_GdiDdDDIOpenResourceFromNtHandle

- ea: `0x140044f00`
- end: `0x140044fa7`
- name: `_stub_GdiDdDDIOpenResourceFromNtHandle`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x140044f00`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140044f49`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140044f49`
- `ext-ms-win-core-win32k-dxgk-l1-1-0!NtGdiDdDDIOpenResourceFromNtHandle` at `0x140044f83`

## string_xrefs

- `0x140044f2f`: `NtGdiDdDDIOpenResourceFromNtHandle`

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
  result = (unsigned int)*((char *)&W32pServiceTableFilter[68] + 4 * (unsigned int)W32pServiceLimitFilter + 5);
  if ( (int)result > 0 )
    return 3221225500LL;
  return result;
}

```

## disassembly

```asm
0x140044f00  sub     rsp, 48h
0x140044f04  mov     [rsp+48h+var_28], rcx
0x140044f09  mov     [rsp+48h+var_20], rdx
0x140044f0e  mov     [rsp+48h+var_18], r8
0x140044f13  mov     [rsp+48h+var_10], r9
0x140044f18  mov     rcx, 225h
0x140044f1f  call    cs:__imp_IsWin32KSyscallFiltered
0x140044f26  nop     dword ptr [rax+rax+00h]
0x140044f2b  test    al, al
0x140044f2d  jz      short loc_140044F83
0x140044f2f  lea     rcx, aNtgdiddddiopen_9; "NtGdiDdDDIOpenResourceFromNtHandle"
0x140044f36  mov     rdx, 225h
0x140044f3d  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x140044f44  nop     dword ptr [rax+rax+00h]
0x140044f49  call    cs:__imp_PsIsWin32KFilterEnabled
0x140044f50  nop     dword ptr [rax+rax+00h]
0x140044f55  test    al, al
0x140044f57  jz      short loc_140044F83
0x140044f59  lea     rcx, W32pServiceTableFilter
0x140044f60  mov     edx, cs:W32pServiceLimitFilter
0x140044f66  mov     rax, 225h
0x140044f6d  lea     rcx, [rcx+rdx*4]
0x140044f71  movsx   eax, byte ptr [rcx+rax]
0x140044f75  or      eax, eax
0x140044f77  jle     short loc_140044F7E
0x140044f79  mov     eax, 0C000001Ch
0x140044f7e  add     rsp, 48h
0x140044f82  retn
0x140044f83  mov     rax, cs:__imp_NtGdiDdDDIOpenResourceFromNtHandle
0x140044f8a  mov     rcx, [rsp+48h+var_28]
0x140044f8f  mov     rdx, [rsp+48h+var_20]
0x140044f94  mov     r8, [rsp+48h+var_18]
0x140044f99  mov     r9, [rsp+48h+var_10]
0x140044f9e  add     rsp, 48h
0x140044fa2  jmp     rax
```
