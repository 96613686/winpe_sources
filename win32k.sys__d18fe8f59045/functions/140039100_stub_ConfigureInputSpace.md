# _stub_ConfigureInputSpace

- ea: `0x140039100`
- end: `0x1400391a7`
- name: `_stub_ConfigureInputSpace`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, service_task`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x140039100`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140039149`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140039149`

## string_xrefs

- `0x14003912f`: `NtConfigureInputSpace`

## pseudocode

```c
__int64 stub_ConfigureInputSpace()
{
  __int64 result; // rax

  if ( !(unsigned __int8)IsWin32KSyscallFiltered() )
    return NtConfigureInputSpace();
  NtUserWin32kSysCallFilterStub();
  if ( !(unsigned __int8)PsIsWin32KFilterEnabled() )
    return NtConfigureInputSpace();
  result = (unsigned int)*((char *)&W32pServiceTableFilter[33] + 4 * (unsigned int)W32pServiceLimitFilter + 6);
  if ( (int)result > 0 )
    return 3221225500LL;
  return result;
}

```

## disassembly

```asm
0x140039100  sub     rsp, 48h
0x140039104  mov     [rsp+48h+var_28], rcx
0x140039109  mov     [rsp+48h+var_20], rdx
0x14003910e  mov     [rsp+48h+var_18], r8
0x140039113  mov     [rsp+48h+var_10], r9
0x140039118  mov     rcx, 10Eh
0x14003911f  call    cs:__imp_IsWin32KSyscallFiltered
0x140039126  nop     dword ptr [rax+rax+00h]
0x14003912b  test    al, al
0x14003912d  jz      short loc_140039183
0x14003912f  lea     rcx, aNtconfigureinp; "NtConfigureInputSpace"
0x140039136  mov     rdx, 10Eh
0x14003913d  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x140039144  nop     dword ptr [rax+rax+00h]
0x140039149  call    cs:__imp_PsIsWin32KFilterEnabled
0x140039150  nop     dword ptr [rax+rax+00h]
0x140039155  test    al, al
0x140039157  jz      short loc_140039183
0x140039159  lea     rcx, W32pServiceTableFilter
0x140039160  mov     edx, cs:W32pServiceLimitFilter
0x140039166  mov     rax, 10Eh
0x14003916d  lea     rcx, [rcx+rdx*4]
0x140039171  movsx   eax, byte ptr [rcx+rax]
0x140039175  or      eax, eax
0x140039177  jle     short loc_14003917E
0x140039179  mov     eax, 0C000001Ch
0x14003917e  add     rsp, 48h
0x140039182  retn
0x140039183  mov     rax, cs:__imp_NtConfigureInputSpace
0x14003918a  mov     rcx, [rsp+48h+var_28]
0x14003918f  mov     rdx, [rsp+48h+var_20]
0x140039194  mov     r8, [rsp+48h+var_18]
0x140039199  mov     r9, [rsp+48h+var_10]
0x14003919e  add     rsp, 48h
0x1400391a2  jmp     rax
```
