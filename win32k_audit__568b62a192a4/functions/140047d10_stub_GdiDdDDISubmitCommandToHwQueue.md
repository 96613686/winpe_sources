# _stub_GdiDdDDISubmitCommandToHwQueue

- ea: `0x140047d10`
- end: `0x140047db7`
- name: `_stub_GdiDdDDISubmitCommandToHwQueue`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x140047d10`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140047d59`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140047d59`
- `ext-ms-win-core-win32k-dxgk-l1-1-0!NtGdiDdDDISubmitCommandToHwQueue` at `0x140047d93`

## string_xrefs

- `0x140047d3f`: `NtGdiDdDDISubmitCommandToHwQueue`

## pseudocode

```c
__int64 __fastcall stub_GdiDdDDISubmitCommandToHwQueue(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 result; // rax

  if ( !(unsigned __int8)IsWin32KSyscallFiltered() )
    return NtGdiDdDDISubmitCommandToHwQueue(a1, a2, a3, a4);
  NtUserWin32kSysCallFilterStub();
  if ( !(unsigned __int8)PsIsWin32KFilterEnabled() )
    return NtGdiDdDDISubmitCommandToHwQueue(a1, a2, a3, a4);
  result = (unsigned int)*((char *)&W32pServiceTableFilter[77] + 4 * (unsigned int)W32pServiceLimitFilter);
  if ( (int)result > 0 )
    return 3221225500LL;
  return result;
}

```

## disassembly

```asm
0x140047d10  sub     rsp, 48h
0x140047d14  mov     [rsp+48h+var_28], rcx
0x140047d19  mov     [rsp+48h+var_20], rdx
0x140047d1e  mov     [rsp+48h+var_18], r8
0x140047d23  mov     [rsp+48h+var_10], r9
0x140047d28  mov     rcx, 268h
0x140047d2f  call    cs:__imp_IsWin32KSyscallFiltered
0x140047d36  nop     dword ptr [rax+rax+00h]
0x140047d3b  test    al, al
0x140047d3d  jz      short loc_140047D93
0x140047d3f  lea     rcx, aNtgdiddddisubm_0; "NtGdiDdDDISubmitCommandToHwQueue"
0x140047d46  mov     rdx, 268h
0x140047d4d  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x140047d54  nop     dword ptr [rax+rax+00h]
0x140047d59  call    cs:__imp_PsIsWin32KFilterEnabled
0x140047d60  nop     dword ptr [rax+rax+00h]
0x140047d65  test    al, al
0x140047d67  jz      short loc_140047D93
0x140047d69  lea     rcx, W32pServiceTableFilter
0x140047d70  mov     edx, cs:W32pServiceLimitFilter
0x140047d76  mov     rax, 268h
0x140047d7d  lea     rcx, [rcx+rdx*4]
0x140047d81  movsx   eax, byte ptr [rcx+rax]
0x140047d85  or      eax, eax
0x140047d87  jle     short loc_140047D8E
0x140047d89  mov     eax, 0C000001Ch
0x140047d8e  add     rsp, 48h
0x140047d92  retn
0x140047d93  mov     rax, cs:__imp_NtGdiDdDDISubmitCommandToHwQueue
0x140047d9a  mov     rcx, [rsp+48h+var_28]
0x140047d9f  mov     rdx, [rsp+48h+var_20]
0x140047da4  mov     r8, [rsp+48h+var_18]
0x140047da9  mov     r9, [rsp+48h+var_10]
0x140047dae  add     rsp, 48h
0x140047db2  jmp     rax
```
