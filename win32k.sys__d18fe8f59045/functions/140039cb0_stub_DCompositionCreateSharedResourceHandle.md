# _stub_DCompositionCreateSharedResourceHandle

- ea: `0x140039cb0`
- end: `0x140039d57`
- name: `_stub_DCompositionCreateSharedResourceHandle`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x140039cb0`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140039cf9`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140039cf9`

## string_xrefs

- `0x140039cdf`: `NtDCompositionCreateSharedResourceHandle`

## pseudocode

```c
__int64 stub_DCompositionCreateSharedResourceHandle()
{
  __int64 result; // rax

  if ( !(unsigned __int8)IsWin32KSyscallFiltered() )
    return NtDCompositionCreateSharedResourceHandle();
  NtUserWin32kSysCallFilterStub();
  if ( !(unsigned __int8)PsIsWin32KFilterEnabled() )
    return NtDCompositionCreateSharedResourceHandle();
  result = (unsigned int)*((char *)&W32pServiceTableFilter[35] + 4 * (unsigned int)W32pServiceLimitFilter + 7);
  if ( (int)result > 0 )
    return 3221225500LL;
  return result;
}

```

## disassembly

```asm
0x140039cb0  sub     rsp, 48h
0x140039cb4  mov     [rsp+48h+var_28], rcx
0x140039cb9  mov     [rsp+48h+var_20], rdx
0x140039cbe  mov     [rsp+48h+var_18], r8
0x140039cc3  mov     [rsp+48h+var_10], r9
0x140039cc8  mov     rcx, 11Fh
0x140039ccf  call    cs:__imp_IsWin32KSyscallFiltered
0x140039cd6  nop     dword ptr [rax+rax+00h]
0x140039cdb  test    al, al
0x140039cdd  jz      short loc_140039D33
0x140039cdf  lea     rcx, aNtdcomposition_11; "NtDCompositionCreateSharedResourceHandl"...
0x140039ce6  mov     rdx, 11Fh
0x140039ced  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x140039cf4  nop     dword ptr [rax+rax+00h]
0x140039cf9  call    cs:__imp_PsIsWin32KFilterEnabled
0x140039d00  nop     dword ptr [rax+rax+00h]
0x140039d05  test    al, al
0x140039d07  jz      short loc_140039D33
0x140039d09  lea     rcx, W32pServiceTableFilter
0x140039d10  mov     edx, cs:W32pServiceLimitFilter
0x140039d16  mov     rax, 11Fh
0x140039d1d  lea     rcx, [rcx+rdx*4]
0x140039d21  movsx   eax, byte ptr [rcx+rax]
0x140039d25  or      eax, eax
0x140039d27  jle     short loc_140039D2E
0x140039d29  mov     eax, 0C000001Ch
0x140039d2e  add     rsp, 48h
0x140039d32  retn
0x140039d33  mov     rax, cs:__imp_NtDCompositionCreateSharedResourceHandle
0x140039d3a  mov     rcx, [rsp+48h+var_28]
0x140039d3f  mov     rdx, [rsp+48h+var_20]
0x140039d44  mov     r8, [rsp+48h+var_18]
0x140039d49  mov     r9, [rsp+48h+var_10]
0x140039d4e  add     rsp, 48h
0x140039d52  jmp     rax
```
