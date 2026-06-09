# _stub_GdiDdDDIOpenNtHandleFromName

- ea: `0x140044cf0`
- end: `0x140044d97`
- name: `_stub_GdiDdDDIOpenNtHandleFromName`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x140044cf0`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140044d39`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140044d39`
- `ext-ms-win-core-win32k-dxgk-l1-1-0!NtGdiDdDDIOpenNtHandleFromName` at `0x140044d73`

## string_xrefs

- `0x140044d1f`: `NtGdiDdDDIOpenNtHandleFromName`

## pseudocode

```c
__int64 __fastcall stub_GdiDdDDIOpenNtHandleFromName(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 result; // rax

  if ( !(unsigned __int8)IsWin32KSyscallFiltered() )
    return NtGdiDdDDIOpenNtHandleFromName(a1, a2, a3, a4);
  NtUserWin32kSysCallFilterStub();
  if ( !(unsigned __int8)PsIsWin32KFilterEnabled() )
    return NtGdiDdDDIOpenNtHandleFromName(a1, a2, a3, a4);
  result = (unsigned int)*((char *)&W32pServiceTableFilter[68] + 4 * (unsigned int)W32pServiceLimitFilter + 2);
  if ( (int)result > 0 )
    return 3221225500LL;
  return result;
}

```

## disassembly

```asm
0x140044cf0  sub     rsp, 48h
0x140044cf4  mov     [rsp+48h+var_28], rcx
0x140044cf9  mov     [rsp+48h+var_20], rdx
0x140044cfe  mov     [rsp+48h+var_18], r8
0x140044d03  mov     [rsp+48h+var_10], r9
0x140044d08  mov     rcx, 222h
0x140044d0f  call    cs:__imp_IsWin32KSyscallFiltered
0x140044d16  nop     dword ptr [rax+rax+00h]
0x140044d1b  test    al, al
0x140044d1d  jz      short loc_140044D73
0x140044d1f  lea     rcx, aNtgdiddddiopen_6; "NtGdiDdDDIOpenNtHandleFromName"
0x140044d26  mov     rdx, 222h
0x140044d2d  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x140044d34  nop     dword ptr [rax+rax+00h]
0x140044d39  call    cs:__imp_PsIsWin32KFilterEnabled
0x140044d40  nop     dword ptr [rax+rax+00h]
0x140044d45  test    al, al
0x140044d47  jz      short loc_140044D73
0x140044d49  lea     rcx, W32pServiceTableFilter
0x140044d50  mov     edx, cs:W32pServiceLimitFilter
0x140044d56  mov     rax, 222h
0x140044d5d  lea     rcx, [rcx+rdx*4]
0x140044d61  movsx   eax, byte ptr [rcx+rax]
0x140044d65  or      eax, eax
0x140044d67  jle     short loc_140044D6E
0x140044d69  mov     eax, 0C000001Ch
0x140044d6e  add     rsp, 48h
0x140044d72  retn
0x140044d73  mov     rax, cs:__imp_NtGdiDdDDIOpenNtHandleFromName
0x140044d7a  mov     rcx, [rsp+48h+var_28]
0x140044d7f  mov     rdx, [rsp+48h+var_20]
0x140044d84  mov     r8, [rsp+48h+var_18]
0x140044d89  mov     r9, [rsp+48h+var_10]
0x140044d8e  add     rsp, 48h
0x140044d92  jmp     rax
```
