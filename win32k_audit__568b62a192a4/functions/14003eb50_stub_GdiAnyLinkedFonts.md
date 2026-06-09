# _stub_GdiAnyLinkedFonts

- ea: `0x14003eb50`
- end: `0x14003ebf7`
- name: `_stub_GdiAnyLinkedFonts`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x14003eb50`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x14003eb99`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x14003eb99`

## string_xrefs

- `0x14003eb7f`: `NtGdiAnyLinkedFonts`

## pseudocode

```c
__int64 stub_GdiAnyLinkedFonts()
{
  __int64 result; // rax

  if ( !(unsigned __int8)IsWin32KSyscallFiltered() )
    return NtGdiAnyLinkedFonts();
  NtUserWin32kSysCallFilterStub();
  if ( !(unsigned __int8)PsIsWin32KFilterEnabled() )
    return NtGdiAnyLinkedFonts();
  result = (unsigned int)*((char *)&W32pServiceTableFilter[50] + 4 * (unsigned int)W32pServiceLimitFilter + 4);
  if ( (int)result > 0 )
    return 3221225500LL;
  return result;
}

```

## disassembly

```asm
0x14003eb50  sub     rsp, 48h
0x14003eb54  mov     [rsp+48h+var_28], rcx
0x14003eb59  mov     [rsp+48h+var_20], rdx
0x14003eb5e  mov     [rsp+48h+var_18], r8
0x14003eb63  mov     [rsp+48h+var_10], r9
0x14003eb68  mov     rcx, 194h
0x14003eb6f  call    cs:__imp_IsWin32KSyscallFiltered
0x14003eb76  nop     dword ptr [rax+rax+00h]
0x14003eb7b  test    al, al
0x14003eb7d  jz      short loc_14003EBD3
0x14003eb7f  lea     rcx, aNtgdianylinked; "NtGdiAnyLinkedFonts"
0x14003eb86  mov     rdx, 194h
0x14003eb8d  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x14003eb94  nop     dword ptr [rax+rax+00h]
0x14003eb99  call    cs:__imp_PsIsWin32KFilterEnabled
0x14003eba0  nop     dword ptr [rax+rax+00h]
0x14003eba5  test    al, al
0x14003eba7  jz      short loc_14003EBD3
0x14003eba9  lea     rcx, W32pServiceTableFilter
0x14003ebb0  mov     edx, cs:W32pServiceLimitFilter
0x14003ebb6  mov     rax, 194h
0x14003ebbd  lea     rcx, [rcx+rdx*4]
0x14003ebc1  movsx   eax, byte ptr [rcx+rax]
0x14003ebc5  or      eax, eax
0x14003ebc7  jle     short loc_14003EBCE
0x14003ebc9  mov     eax, 0C000001Ch
0x14003ebce  add     rsp, 48h
0x14003ebd2  retn
0x14003ebd3  mov     rax, cs:__imp_NtGdiAnyLinkedFonts
0x14003ebda  mov     rcx, [rsp+48h+var_28]
0x14003ebdf  mov     rdx, [rsp+48h+var_20]
0x14003ebe4  mov     r8, [rsp+48h+var_18]
0x14003ebe9  mov     r9, [rsp+48h+var_10]
0x14003ebee  add     rsp, 48h
0x14003ebf2  jmp     rax
```
