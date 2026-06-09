# _stub_GdiDdDDIOpenAdapterFromHdc

- ea: `0x140044cb0`
- end: `0x140044d57`
- name: `_stub_GdiDdDDIOpenAdapterFromHdc`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x140044cb0`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140044cf9`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140044cf9`
- `ext-ms-win-core-win32k-dxgk-l1-1-0!NtGdiDdDDIOpenAdapterFromHdc` at `0x140044d33`

## string_xrefs

- `0x140044cdf`: `NtGdiDdDDIOpenAdapterFromHdc`

## pseudocode

```c
__int64 __fastcall stub_GdiDdDDIOpenAdapterFromHdc(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 result; // rax

  if ( !(unsigned __int8)IsWin32KSyscallFiltered() )
    return NtGdiDdDDIOpenAdapterFromHdc(a1, a2, a3, a4);
  NtUserWin32kSysCallFilterStub();
  if ( !(unsigned __int8)PsIsWin32KFilterEnabled() )
    return NtGdiDdDDIOpenAdapterFromHdc(a1, a2, a3, a4);
  result = (unsigned int)*((char *)&W32pServiceTableFilter[67] + 4 * (unsigned int)W32pServiceLimitFilter + 7);
  if ( (int)result > 0 )
    return 3221225500LL;
  return result;
}

```

## disassembly

```asm
0x140044cb0  sub     rsp, 48h
0x140044cb4  mov     [rsp+48h+var_28], rcx
0x140044cb9  mov     [rsp+48h+var_20], rdx
0x140044cbe  mov     [rsp+48h+var_18], r8
0x140044cc3  mov     [rsp+48h+var_10], r9
0x140044cc8  mov     rcx, 21Fh
0x140044ccf  call    cs:__imp_IsWin32KSyscallFiltered
0x140044cd6  nop     dword ptr [rax+rax+00h]
0x140044cdb  test    al, al
0x140044cdd  jz      short loc_140044D33
0x140044cdf  lea     rcx, aNtgdiddddiopen_0; "NtGdiDdDDIOpenAdapterFromHdc"
0x140044ce6  mov     rdx, 21Fh
0x140044ced  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x140044cf4  nop     dword ptr [rax+rax+00h]
0x140044cf9  call    cs:__imp_PsIsWin32KFilterEnabled
0x140044d00  nop     dword ptr [rax+rax+00h]
0x140044d05  test    al, al
0x140044d07  jz      short loc_140044D33
0x140044d09  lea     rcx, W32pServiceTableFilter
0x140044d10  mov     edx, cs:W32pServiceLimitFilter
0x140044d16  mov     rax, 21Fh
0x140044d1d  lea     rcx, [rcx+rdx*4]
0x140044d21  movsx   eax, byte ptr [rcx+rax]
0x140044d25  or      eax, eax
0x140044d27  jle     short loc_140044D2E
0x140044d29  mov     eax, 0C000001Ch
0x140044d2e  add     rsp, 48h
0x140044d32  retn
0x140044d33  mov     rax, cs:__imp_NtGdiDdDDIOpenAdapterFromHdc
0x140044d3a  mov     rcx, [rsp+48h+var_28]
0x140044d3f  mov     rdx, [rsp+48h+var_20]
0x140044d44  mov     r8, [rsp+48h+var_18]
0x140044d49  mov     r9, [rsp+48h+var_10]
0x140044d4e  add     rsp, 48h
0x140044d52  jmp     rax
```
