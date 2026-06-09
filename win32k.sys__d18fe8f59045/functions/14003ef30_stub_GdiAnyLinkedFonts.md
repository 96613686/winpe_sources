# _stub_GdiAnyLinkedFonts

- ea: `0x14003ef30`
- end: `0x14003efd7`
- name: `_stub_GdiAnyLinkedFonts`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x14003ef30`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x14003ef79`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x14003ef79`

## string_xrefs

- `0x14003ef5f`: `NtGdiAnyLinkedFonts`

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
  result = (unsigned int)*((char *)&W32pServiceTableFilter[50] + 4 * (unsigned int)W32pServiceLimitFilter + 7);
  if ( (int)result > 0 )
    return 3221225500LL;
  return result;
}

```

## disassembly

```asm
0x14003ef30  sub     rsp, 48h
0x14003ef34  mov     [rsp+48h+var_28], rcx
0x14003ef39  mov     [rsp+48h+var_20], rdx
0x14003ef3e  mov     [rsp+48h+var_18], r8
0x14003ef43  mov     [rsp+48h+var_10], r9
0x14003ef48  mov     rcx, 197h
0x14003ef4f  call    cs:__imp_IsWin32KSyscallFiltered
0x14003ef56  nop     dword ptr [rax+rax+00h]
0x14003ef5b  test    al, al
0x14003ef5d  jz      short loc_14003EFB3
0x14003ef5f  lea     rcx, aNtgdianylinked; "NtGdiAnyLinkedFonts"
0x14003ef66  mov     rdx, 197h
0x14003ef6d  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x14003ef74  nop     dword ptr [rax+rax+00h]
0x14003ef79  call    cs:__imp_PsIsWin32KFilterEnabled
0x14003ef80  nop     dword ptr [rax+rax+00h]
0x14003ef85  test    al, al
0x14003ef87  jz      short loc_14003EFB3
0x14003ef89  lea     rcx, W32pServiceTableFilter
0x14003ef90  mov     edx, cs:W32pServiceLimitFilter
0x14003ef96  mov     rax, 197h
0x14003ef9d  lea     rcx, [rcx+rdx*4]
0x14003efa1  movsx   eax, byte ptr [rcx+rax]
0x14003efa5  or      eax, eax
0x14003efa7  jle     short loc_14003EFAE
0x14003efa9  mov     eax, 0C000001Ch
0x14003efae  add     rsp, 48h
0x14003efb2  retn
0x14003efb3  mov     rax, cs:__imp_NtGdiAnyLinkedFonts
0x14003efba  mov     rcx, [rsp+48h+var_28]
0x14003efbf  mov     rdx, [rsp+48h+var_20]
0x14003efc4  mov     r8, [rsp+48h+var_18]
0x14003efc9  mov     r9, [rsp+48h+var_10]
0x14003efce  add     rsp, 48h
0x14003efd2  jmp     rax
```
