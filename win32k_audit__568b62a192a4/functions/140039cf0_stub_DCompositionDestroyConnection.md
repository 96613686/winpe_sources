# _stub_DCompositionDestroyConnection

- ea: `0x140039cf0`
- end: `0x140039d97`
- name: `_stub_DCompositionDestroyConnection`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x140039cf0`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140039d39`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140039d39`

## string_xrefs

- `0x140039d1f`: `NtDCompositionDestroyConnection`

## pseudocode

```c
__int64 stub_DCompositionDestroyConnection()
{
  __int64 result; // rax

  if ( !(unsigned __int8)IsWin32KSyscallFiltered() )
    return NtDCompositionDestroyConnection();
  NtUserWin32kSysCallFilterStub();
  if ( !(unsigned __int8)PsIsWin32KFilterEnabled() )
    return NtDCompositionDestroyConnection();
  result = (unsigned int)*((char *)&W32pServiceTableFilter[36] + 4 * (unsigned int)W32pServiceLimitFilter + 2);
  if ( (int)result > 0 )
    return 3221225500LL;
  return result;
}

```

## disassembly

```asm
0x140039cf0  sub     rsp, 48h
0x140039cf4  mov     [rsp+48h+var_28], rcx
0x140039cf9  mov     [rsp+48h+var_20], rdx
0x140039cfe  mov     [rsp+48h+var_18], r8
0x140039d03  mov     [rsp+48h+var_10], r9
0x140039d08  mov     rcx, 122h
0x140039d0f  call    cs:__imp_IsWin32KSyscallFiltered
0x140039d16  nop     dword ptr [rax+rax+00h]
0x140039d1b  test    al, al
0x140039d1d  jz      short loc_140039D73
0x140039d1f  lea     rcx, aNtdcomposition_14; "NtDCompositionDestroyConnection"
0x140039d26  mov     rdx, 122h
0x140039d2d  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x140039d34  nop     dword ptr [rax+rax+00h]
0x140039d39  call    cs:__imp_PsIsWin32KFilterEnabled
0x140039d40  nop     dword ptr [rax+rax+00h]
0x140039d45  test    al, al
0x140039d47  jz      short loc_140039D73
0x140039d49  lea     rcx, W32pServiceTableFilter
0x140039d50  mov     edx, cs:W32pServiceLimitFilter
0x140039d56  mov     rax, 122h
0x140039d5d  lea     rcx, [rcx+rdx*4]
0x140039d61  movsx   eax, byte ptr [rcx+rax]
0x140039d65  or      eax, eax
0x140039d67  jle     short loc_140039D6E
0x140039d69  mov     eax, 0C000001Ch
0x140039d6e  add     rsp, 48h
0x140039d72  retn
0x140039d73  mov     rax, cs:__imp_NtDCompositionDestroyConnection
0x140039d7a  mov     rcx, [rsp+48h+var_28]
0x140039d7f  mov     rdx, [rsp+48h+var_20]
0x140039d84  mov     r8, [rsp+48h+var_18]
0x140039d89  mov     r9, [rsp+48h+var_10]
0x140039d8e  add     rsp, 48h
0x140039d92  jmp     rax
```
