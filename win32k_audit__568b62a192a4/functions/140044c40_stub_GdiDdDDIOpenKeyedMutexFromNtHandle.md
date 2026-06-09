# _stub_GdiDdDDIOpenKeyedMutexFromNtHandle

- ea: `0x140044c40`
- end: `0x140044ce7`
- name: `_stub_GdiDdDDIOpenKeyedMutexFromNtHandle`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x140044c40`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140044c89`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140044c89`
- `ext-ms-win-core-win32k-dxgk-l1-1-0!NtGdiDdDDIOpenKeyedMutexFromNtHandle` at `0x140044cc3`

## string_xrefs

- `0x140044c6f`: `NtGdiDdDDIOpenKeyedMutexFromNtHandle`

## pseudocode

```c
__int64 __fastcall stub_GdiDdDDIOpenKeyedMutexFromNtHandle(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 result; // rax

  if ( !(unsigned __int8)IsWin32KSyscallFiltered() )
    return NtGdiDdDDIOpenKeyedMutexFromNtHandle(a1, a2, a3, a4);
  NtUserWin32kSysCallFilterStub();
  if ( !(unsigned __int8)PsIsWin32KFilterEnabled() )
    return NtGdiDdDDIOpenKeyedMutexFromNtHandle(a1, a2, a3, a4);
  result = (unsigned int)*((char *)&W32pServiceTableFilter[68] + 4 * (unsigned int)W32pServiceLimitFilter + 1);
  if ( (int)result > 0 )
    return 3221225500LL;
  return result;
}

```

## disassembly

```asm
0x140044c40  sub     rsp, 48h
0x140044c44  mov     [rsp+48h+var_28], rcx
0x140044c49  mov     [rsp+48h+var_20], rdx
0x140044c4e  mov     [rsp+48h+var_18], r8
0x140044c53  mov     [rsp+48h+var_10], r9
0x140044c58  mov     rcx, 221h
0x140044c5f  call    cs:__imp_IsWin32KSyscallFiltered
0x140044c66  nop     dword ptr [rax+rax+00h]
0x140044c6b  test    al, al
0x140044c6d  jz      short loc_140044CC3
0x140044c6f  lea     rcx, aNtgdiddddiopen_5; "NtGdiDdDDIOpenKeyedMutexFromNtHandle"
0x140044c76  mov     rdx, 221h
0x140044c7d  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x140044c84  nop     dword ptr [rax+rax+00h]
0x140044c89  call    cs:__imp_PsIsWin32KFilterEnabled
0x140044c90  nop     dword ptr [rax+rax+00h]
0x140044c95  test    al, al
0x140044c97  jz      short loc_140044CC3
0x140044c99  lea     rcx, W32pServiceTableFilter
0x140044ca0  mov     edx, cs:W32pServiceLimitFilter
0x140044ca6  mov     rax, 221h
0x140044cad  lea     rcx, [rcx+rdx*4]
0x140044cb1  movsx   eax, byte ptr [rcx+rax]
0x140044cb5  or      eax, eax
0x140044cb7  jle     short loc_140044CBE
0x140044cb9  mov     eax, 0C000001Ch
0x140044cbe  add     rsp, 48h
0x140044cc2  retn
0x140044cc3  mov     rax, cs:__imp_NtGdiDdDDIOpenKeyedMutexFromNtHandle
0x140044cca  mov     rcx, [rsp+48h+var_28]
0x140044ccf  mov     rdx, [rsp+48h+var_20]
0x140044cd4  mov     r8, [rsp+48h+var_18]
0x140044cd9  mov     r9, [rsp+48h+var_10]
0x140044cde  add     rsp, 48h
0x140044ce2  jmp     rax
```
