# _stub_GdiDdDDICreateProtectedSession

- ea: `0x140041a10`
- end: `0x140041ab7`
- name: `_stub_GdiDdDDICreateProtectedSession`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x140041a10`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140041a59`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140041a59`
- `ext-ms-win-core-win32k-dxgk-l1-1-0!NtGdiDdDDICreateProtectedSession` at `0x140041a93`

## string_xrefs

- `0x140041a3f`: `NtGdiDdDDICreateProtectedSession`

## pseudocode

```c
__int64 __fastcall stub_GdiDdDDICreateProtectedSession(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 result; // rax

  if ( !(unsigned __int8)IsWin32KSyscallFiltered() )
    return NtGdiDdDDICreateProtectedSession(a1, a2, a3, a4);
  NtUserWin32kSysCallFilterStub();
  if ( !(unsigned __int8)PsIsWin32KFilterEnabled() )
    return NtGdiDdDDICreateProtectedSession(a1, a2, a3, a4);
  result = (unsigned int)*((char *)&W32pServiceTableFilter[59] + 4 * (unsigned int)W32pServiceLimitFilter);
  if ( (int)result > 0 )
    return 3221225500LL;
  return result;
}

```

## disassembly

```asm
0x140041a10  sub     rsp, 48h
0x140041a14  mov     [rsp+48h+var_28], rcx
0x140041a19  mov     [rsp+48h+var_20], rdx
0x140041a1e  mov     [rsp+48h+var_18], r8
0x140041a23  mov     [rsp+48h+var_10], r9
0x140041a28  mov     rcx, 1D8h
0x140041a2f  call    cs:__imp_IsWin32KSyscallFiltered
0x140041a36  nop     dword ptr [rax+rax+00h]
0x140041a3b  test    al, al
0x140041a3d  jz      short loc_140041A93
0x140041a3f  lea     rcx, aNtgdiddddicrea_12; "NtGdiDdDDICreateProtectedSession"
0x140041a46  mov     rdx, 1D8h
0x140041a4d  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x140041a54  nop     dword ptr [rax+rax+00h]
0x140041a59  call    cs:__imp_PsIsWin32KFilterEnabled
0x140041a60  nop     dword ptr [rax+rax+00h]
0x140041a65  test    al, al
0x140041a67  jz      short loc_140041A93
0x140041a69  lea     rcx, W32pServiceTableFilter
0x140041a70  mov     edx, cs:W32pServiceLimitFilter
0x140041a76  mov     rax, 1D8h
0x140041a7d  lea     rcx, [rcx+rdx*4]
0x140041a81  movsx   eax, byte ptr [rcx+rax]
0x140041a85  or      eax, eax
0x140041a87  jle     short loc_140041A8E
0x140041a89  mov     eax, 0C000001Ch
0x140041a8e  add     rsp, 48h
0x140041a92  retn
0x140041a93  mov     rax, cs:__imp_NtGdiDdDDICreateProtectedSession
0x140041a9a  mov     rcx, [rsp+48h+var_28]
0x140041a9f  mov     rdx, [rsp+48h+var_20]
0x140041aa4  mov     r8, [rsp+48h+var_18]
0x140041aa9  mov     r9, [rsp+48h+var_10]
0x140041aae  add     rsp, 48h
0x140041ab2  jmp     rax
```
