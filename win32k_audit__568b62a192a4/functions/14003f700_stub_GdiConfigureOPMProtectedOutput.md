# _stub_GdiConfigureOPMProtectedOutput

- ea: `0x14003f700`
- end: `0x14003f7a7`
- name: `_stub_GdiConfigureOPMProtectedOutput`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, service_task`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x14003f700`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x14003f749`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x14003f749`

## string_xrefs

- `0x14003f72f`: `NtGdiConfigureOPMProtectedOutput`

## pseudocode

```c
__int64 stub_GdiConfigureOPMProtectedOutput()
{
  __int64 result; // rax

  if ( !(unsigned __int8)IsWin32KSyscallFiltered() )
    return NtGdiConfigureOPMProtectedOutput();
  NtUserWin32kSysCallFilterStub();
  if ( !(unsigned __int8)PsIsWin32KFilterEnabled() )
    return NtGdiConfigureOPMProtectedOutput();
  result = (unsigned int)*((char *)&W32pServiceTableFilter[52] + 4 * (unsigned int)W32pServiceLimitFilter + 5);
  if ( (int)result > 0 )
    return 3221225500LL;
  return result;
}

```

## disassembly

```asm
0x14003f700  sub     rsp, 48h
0x14003f704  mov     [rsp+48h+var_28], rcx
0x14003f709  mov     [rsp+48h+var_20], rdx
0x14003f70e  mov     [rsp+48h+var_18], r8
0x14003f713  mov     [rsp+48h+var_10], r9
0x14003f718  mov     rcx, 1A5h
0x14003f71f  call    cs:__imp_IsWin32KSyscallFiltered
0x14003f726  nop     dword ptr [rax+rax+00h]
0x14003f72b  test    al, al
0x14003f72d  jz      short loc_14003F783
0x14003f72f  lea     rcx, aNtgdiconfigure; "NtGdiConfigureOPMProtectedOutput"
0x14003f736  mov     rdx, 1A5h
0x14003f73d  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x14003f744  nop     dword ptr [rax+rax+00h]
0x14003f749  call    cs:__imp_PsIsWin32KFilterEnabled
0x14003f750  nop     dword ptr [rax+rax+00h]
0x14003f755  test    al, al
0x14003f757  jz      short loc_14003F783
0x14003f759  lea     rcx, W32pServiceTableFilter
0x14003f760  mov     edx, cs:W32pServiceLimitFilter
0x14003f766  mov     rax, 1A5h
0x14003f76d  lea     rcx, [rcx+rdx*4]
0x14003f771  movsx   eax, byte ptr [rcx+rax]
0x14003f775  or      eax, eax
0x14003f777  jle     short loc_14003F77E
0x14003f779  mov     eax, 0C000001Ch
0x14003f77e  add     rsp, 48h
0x14003f782  retn
0x14003f783  mov     rax, cs:__imp_NtGdiConfigureOPMProtectedOutput
0x14003f78a  mov     rcx, [rsp+48h+var_28]
0x14003f78f  mov     rdx, [rsp+48h+var_20]
0x14003f794  mov     r8, [rsp+48h+var_18]
0x14003f799  mov     r9, [rsp+48h+var_10]
0x14003f79e  add     rsp, 48h
0x14003f7a2  jmp     rax
```
