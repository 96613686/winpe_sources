# _stub_DCompositionRegisterVirtualDesktopVisual

- ea: `0x14003aa00`
- end: `0x14003aaa7`
- name: `_stub_DCompositionRegisterVirtualDesktopVisual`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x14003aa00`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x14003aa49`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x14003aa49`

## string_xrefs

- `0x14003aa2f`: `NtDCompositionRegisterVirtualDesktopVisual`

## pseudocode

```c
__int64 stub_DCompositionRegisterVirtualDesktopVisual()
{
  __int64 result; // rax

  if ( !(unsigned __int8)IsWin32KSyscallFiltered() )
    return NtDCompositionRegisterVirtualDesktopVisual();
  NtUserWin32kSysCallFilterStub();
  if ( !(unsigned __int8)PsIsWin32KFilterEnabled() )
    return NtDCompositionRegisterVirtualDesktopVisual();
  result = (unsigned int)*((char *)&W32pServiceTableFilter[38] + 4 * (unsigned int)W32pServiceLimitFilter + 5);
  if ( (int)result > 0 )
    return 3221225500LL;
  return result;
}

```

## disassembly

```asm
0x14003aa00  sub     rsp, 48h
0x14003aa04  mov     [rsp+48h+var_28], rcx
0x14003aa09  mov     [rsp+48h+var_20], rdx
0x14003aa0e  mov     [rsp+48h+var_18], r8
0x14003aa13  mov     [rsp+48h+var_10], r9
0x14003aa18  mov     rcx, 135h
0x14003aa1f  call    cs:__imp_IsWin32KSyscallFiltered
0x14003aa26  nop     dword ptr [rax+rax+00h]
0x14003aa2b  test    al, al
0x14003aa2d  jz      short loc_14003AA83
0x14003aa2f  lea     rcx, aNtdcomposition_33; "NtDCompositionRegisterVirtualDesktopVis"...
0x14003aa36  mov     rdx, 135h
0x14003aa3d  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x14003aa44  nop     dword ptr [rax+rax+00h]
0x14003aa49  call    cs:__imp_PsIsWin32KFilterEnabled
0x14003aa50  nop     dword ptr [rax+rax+00h]
0x14003aa55  test    al, al
0x14003aa57  jz      short loc_14003AA83
0x14003aa59  lea     rcx, W32pServiceTableFilter
0x14003aa60  mov     edx, cs:W32pServiceLimitFilter
0x14003aa66  mov     rax, 135h
0x14003aa6d  lea     rcx, [rcx+rdx*4]
0x14003aa71  movsx   eax, byte ptr [rcx+rax]
0x14003aa75  or      eax, eax
0x14003aa77  jle     short loc_14003AA7E
0x14003aa79  mov     eax, 0C000001Ch
0x14003aa7e  add     rsp, 48h
0x14003aa82  retn
0x14003aa83  mov     rax, cs:__imp_NtDCompositionRegisterVirtualDesktopVisual
0x14003aa8a  mov     rcx, [rsp+48h+var_28]
0x14003aa8f  mov     rdx, [rsp+48h+var_20]
0x14003aa94  mov     r8, [rsp+48h+var_18]
0x14003aa99  mov     r9, [rsp+48h+var_10]
0x14003aa9e  add     rsp, 48h
0x14003aaa2  jmp     rax
```
