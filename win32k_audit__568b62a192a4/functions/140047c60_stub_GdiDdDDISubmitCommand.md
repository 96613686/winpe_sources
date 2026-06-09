# _stub_GdiDdDDISubmitCommand

- ea: `0x140047c60`
- end: `0x140047d07`
- name: `_stub_GdiDdDDISubmitCommand`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x140047c60`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140047ca9`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140047ca9`
- `ext-ms-win-core-win32k-dxgk-l1-1-0!NtGdiDdDDISubmitCommand` at `0x140047ce3`

## string_xrefs

- `0x140047c8f`: `NtGdiDdDDISubmitCommand`

## pseudocode

```c
__int64 __fastcall stub_GdiDdDDISubmitCommand(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 result; // rax

  if ( !(unsigned __int8)IsWin32KSyscallFiltered() )
    return NtGdiDdDDISubmitCommand(a1, a2, a3, a4);
  NtUserWin32kSysCallFilterStub();
  if ( !(unsigned __int8)PsIsWin32KFilterEnabled() )
    return NtGdiDdDDISubmitCommand(a1, a2, a3, a4);
  result = (unsigned int)*((char *)&W32pServiceTableFilter[76] + 4 * (unsigned int)W32pServiceLimitFilter + 7);
  if ( (int)result > 0 )
    return 3221225500LL;
  return result;
}

```

## disassembly

```asm
0x140047c60  sub     rsp, 48h
0x140047c64  mov     [rsp+48h+var_28], rcx
0x140047c69  mov     [rsp+48h+var_20], rdx
0x140047c6e  mov     [rsp+48h+var_18], r8
0x140047c73  mov     [rsp+48h+var_10], r9
0x140047c78  mov     rcx, 267h
0x140047c7f  call    cs:__imp_IsWin32KSyscallFiltered
0x140047c86  nop     dword ptr [rax+rax+00h]
0x140047c8b  test    al, al
0x140047c8d  jz      short loc_140047CE3
0x140047c8f  lea     rcx, aNtgdiddddisubm; "NtGdiDdDDISubmitCommand"
0x140047c96  mov     rdx, 267h
0x140047c9d  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x140047ca4  nop     dword ptr [rax+rax+00h]
0x140047ca9  call    cs:__imp_PsIsWin32KFilterEnabled
0x140047cb0  nop     dword ptr [rax+rax+00h]
0x140047cb5  test    al, al
0x140047cb7  jz      short loc_140047CE3
0x140047cb9  lea     rcx, W32pServiceTableFilter
0x140047cc0  mov     edx, cs:W32pServiceLimitFilter
0x140047cc6  mov     rax, 267h
0x140047ccd  lea     rcx, [rcx+rdx*4]
0x140047cd1  movsx   eax, byte ptr [rcx+rax]
0x140047cd5  or      eax, eax
0x140047cd7  jle     short loc_140047CDE
0x140047cd9  mov     eax, 0C000001Ch
0x140047cde  add     rsp, 48h
0x140047ce2  retn
0x140047ce3  mov     rax, cs:__imp_NtGdiDdDDISubmitCommand
0x140047cea  mov     rcx, [rsp+48h+var_28]
0x140047cef  mov     rdx, [rsp+48h+var_20]
0x140047cf4  mov     r8, [rsp+48h+var_18]
0x140047cf9  mov     r9, [rsp+48h+var_10]
0x140047cfe  add     rsp, 48h
0x140047d02  jmp     rax
```
