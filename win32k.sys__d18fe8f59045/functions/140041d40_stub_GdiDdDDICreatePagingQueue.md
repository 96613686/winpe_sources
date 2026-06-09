# _stub_GdiDdDDICreatePagingQueue

- ea: `0x140041d40`
- end: `0x140041de7`
- name: `_stub_GdiDdDDICreatePagingQueue`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x140041d40`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140041d89`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140041d89`
- `ext-ms-win-core-win32k-dxgk-l1-1-0!NtGdiDdDDICreatePagingQueue` at `0x140041dc3`

## string_xrefs

- `0x140041d6f`: `NtGdiDdDDICreatePagingQueue`

## pseudocode

```c
__int64 __fastcall stub_GdiDdDDICreatePagingQueue(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 result; // rax

  if ( !(unsigned __int8)IsWin32KSyscallFiltered() )
    return NtGdiDdDDICreatePagingQueue(a1, a2, a3, a4);
  NtUserWin32kSysCallFilterStub();
  if ( !(unsigned __int8)PsIsWin32KFilterEnabled() )
    return NtGdiDdDDICreatePagingQueue(a1, a2, a3, a4);
  result = (unsigned int)*((char *)&W32pServiceTableFilter[59] + 4 * (unsigned int)W32pServiceLimitFilter + 2);
  if ( (int)result > 0 )
    return 3221225500LL;
  return result;
}

```

## disassembly

```asm
0x140041d40  sub     rsp, 48h
0x140041d44  mov     [rsp+48h+var_28], rcx
0x140041d49  mov     [rsp+48h+var_20], rdx
0x140041d4e  mov     [rsp+48h+var_18], r8
0x140041d53  mov     [rsp+48h+var_10], r9
0x140041d58  mov     rcx, 1DAh
0x140041d5f  call    cs:__imp_IsWin32KSyscallFiltered
0x140041d66  nop     dword ptr [rax+rax+00h]
0x140041d6b  test    al, al
0x140041d6d  jz      short loc_140041DC3
0x140041d6f  lea     rcx, aNtgdiddddicrea_11; "NtGdiDdDDICreatePagingQueue"
0x140041d76  mov     rdx, 1DAh
0x140041d7d  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x140041d84  nop     dword ptr [rax+rax+00h]
0x140041d89  call    cs:__imp_PsIsWin32KFilterEnabled
0x140041d90  nop     dword ptr [rax+rax+00h]
0x140041d95  test    al, al
0x140041d97  jz      short loc_140041DC3
0x140041d99  lea     rcx, W32pServiceTableFilter
0x140041da0  mov     edx, cs:W32pServiceLimitFilter
0x140041da6  mov     rax, 1DAh
0x140041dad  lea     rcx, [rcx+rdx*4]
0x140041db1  movsx   eax, byte ptr [rcx+rax]
0x140041db5  or      eax, eax
0x140041db7  jle     short loc_140041DBE
0x140041db9  mov     eax, 0C000001Ch
0x140041dbe  add     rsp, 48h
0x140041dc2  retn
0x140041dc3  mov     rax, cs:__imp_NtGdiDdDDICreatePagingQueue
0x140041dca  mov     rcx, [rsp+48h+var_28]
0x140041dcf  mov     rdx, [rsp+48h+var_20]
0x140041dd4  mov     r8, [rsp+48h+var_18]
0x140041dd9  mov     r9, [rsp+48h+var_10]
0x140041dde  add     rsp, 48h
0x140041de2  jmp     rax
```
