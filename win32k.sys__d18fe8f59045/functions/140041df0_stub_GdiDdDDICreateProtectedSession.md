# _stub_GdiDdDDICreateProtectedSession

- ea: `0x140041df0`
- end: `0x140041e97`
- name: `_stub_GdiDdDDICreateProtectedSession`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x140041df0`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140041e39`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140041e39`
- `ext-ms-win-core-win32k-dxgk-l1-1-0!NtGdiDdDDICreateProtectedSession` at `0x140041e73`

## string_xrefs

- `0x140041e1f`: `NtGdiDdDDICreateProtectedSession`

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
  result = (unsigned int)*((char *)&W32pServiceTableFilter[59] + 4 * (unsigned int)W32pServiceLimitFilter + 3);
  if ( (int)result > 0 )
    return 3221225500LL;
  return result;
}

```

## disassembly

```asm
0x140041df0  sub     rsp, 48h
0x140041df4  mov     [rsp+48h+var_28], rcx
0x140041df9  mov     [rsp+48h+var_20], rdx
0x140041dfe  mov     [rsp+48h+var_18], r8
0x140041e03  mov     [rsp+48h+var_10], r9
0x140041e08  mov     rcx, 1DBh
0x140041e0f  call    cs:__imp_IsWin32KSyscallFiltered
0x140041e16  nop     dword ptr [rax+rax+00h]
0x140041e1b  test    al, al
0x140041e1d  jz      short loc_140041E73
0x140041e1f  lea     rcx, aNtgdiddddicrea_12; "NtGdiDdDDICreateProtectedSession"
0x140041e26  mov     rdx, 1DBh
0x140041e2d  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x140041e34  nop     dword ptr [rax+rax+00h]
0x140041e39  call    cs:__imp_PsIsWin32KFilterEnabled
0x140041e40  nop     dword ptr [rax+rax+00h]
0x140041e45  test    al, al
0x140041e47  jz      short loc_140041E73
0x140041e49  lea     rcx, W32pServiceTableFilter
0x140041e50  mov     edx, cs:W32pServiceLimitFilter
0x140041e56  mov     rax, 1DBh
0x140041e5d  lea     rcx, [rcx+rdx*4]
0x140041e61  movsx   eax, byte ptr [rcx+rax]
0x140041e65  or      eax, eax
0x140041e67  jle     short loc_140041E6E
0x140041e69  mov     eax, 0C000001Ch
0x140041e6e  add     rsp, 48h
0x140041e72  retn
0x140041e73  mov     rax, cs:__imp_NtGdiDdDDICreateProtectedSession
0x140041e7a  mov     rcx, [rsp+48h+var_28]
0x140041e7f  mov     rdx, [rsp+48h+var_20]
0x140041e84  mov     r8, [rsp+48h+var_18]
0x140041e89  mov     r9, [rsp+48h+var_10]
0x140041e8e  add     rsp, 48h
0x140041e92  jmp     rax
```
