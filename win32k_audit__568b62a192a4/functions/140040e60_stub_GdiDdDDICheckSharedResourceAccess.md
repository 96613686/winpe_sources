# _stub_GdiDdDDICheckSharedResourceAccess

- ea: `0x140040e60`
- end: `0x140040f07`
- name: `_stub_GdiDdDDICheckSharedResourceAccess`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x140040e60`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140040ea9`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140040ea9`
- `ext-ms-win-core-win32k-dxgk-l1-1-0!NtGdiDdDDICheckSharedResourceAccess` at `0x140040ee3`

## string_xrefs

- `0x140040e8f`: `NtGdiDdDDICheckSharedResourceAccess`

## pseudocode

```c
__int64 __fastcall stub_GdiDdDDICheckSharedResourceAccess(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 result; // rax

  if ( !(unsigned __int8)IsWin32KSyscallFiltered() )
    return NtGdiDdDDICheckSharedResourceAccess(a1, a2, a3, a4);
  NtUserWin32kSysCallFilterStub();
  if ( !(unsigned __int8)PsIsWin32KFilterEnabled() )
    return NtGdiDdDDICheckSharedResourceAccess(a1, a2, a3, a4);
  result = (unsigned int)*((char *)&W32pServiceTableFilter[56] + 4 * (unsigned int)W32pServiceLimitFilter + 7);
  if ( (int)result > 0 )
    return 3221225500LL;
  return result;
}

```

## disassembly

```asm
0x140040e60  sub     rsp, 48h
0x140040e64  mov     [rsp+48h+var_28], rcx
0x140040e69  mov     [rsp+48h+var_20], rdx
0x140040e6e  mov     [rsp+48h+var_18], r8
0x140040e73  mov     [rsp+48h+var_10], r9
0x140040e78  mov     rcx, 1C7h
0x140040e7f  call    cs:__imp_IsWin32KSyscallFiltered
0x140040e86  nop     dword ptr [rax+rax+00h]
0x140040e8b  test    al, al
0x140040e8d  jz      short loc_140040EE3
0x140040e8f  lea     rcx, aNtgdiddddichec_5; "NtGdiDdDDICheckSharedResourceAccess"
0x140040e96  mov     rdx, 1C7h
0x140040e9d  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x140040ea4  nop     dword ptr [rax+rax+00h]
0x140040ea9  call    cs:__imp_PsIsWin32KFilterEnabled
0x140040eb0  nop     dword ptr [rax+rax+00h]
0x140040eb5  test    al, al
0x140040eb7  jz      short loc_140040EE3
0x140040eb9  lea     rcx, W32pServiceTableFilter
0x140040ec0  mov     edx, cs:W32pServiceLimitFilter
0x140040ec6  mov     rax, 1C7h
0x140040ecd  lea     rcx, [rcx+rdx*4]
0x140040ed1  movsx   eax, byte ptr [rcx+rax]
0x140040ed5  or      eax, eax
0x140040ed7  jle     short loc_140040EDE
0x140040ed9  mov     eax, 0C000001Ch
0x140040ede  add     rsp, 48h
0x140040ee2  retn
0x140040ee3  mov     rax, cs:__imp_NtGdiDdDDICheckSharedResourceAccess
0x140040eea  mov     rcx, [rsp+48h+var_28]
0x140040eef  mov     rdx, [rsp+48h+var_20]
0x140040ef4  mov     r8, [rsp+48h+var_18]
0x140040ef9  mov     r9, [rsp+48h+var_10]
0x140040efe  add     rsp, 48h
0x140040f02  jmp     rax
```
