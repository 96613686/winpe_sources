# _stub_ConfigureInputSpace

- ea: `0x140038f30`
- end: `0x140038fd7`
- name: `_stub_ConfigureInputSpace`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, service_task`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x140038f30`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140038f79`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140038f79`

## string_xrefs

- `0x140038f5f`: `NtConfigureInputSpace`

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
0x140038f30  sub     rsp, 48h
0x140038f34  mov     [rsp+48h+var_28], rcx
0x140038f39  mov     [rsp+48h+var_20], rdx
0x140038f3e  mov     [rsp+48h+var_18], r8
0x140038f43  mov     [rsp+48h+var_10], r9
0x140038f48  mov     rcx, 10Eh
0x140038f4f  call    cs:__imp_IsWin32KSyscallFiltered
0x140038f56  nop     dword ptr [rax+rax+00h]
0x140038f5b  test    al, al
0x140038f5d  jz      short loc_140038FB3
0x140038f5f  lea     rcx, aNtconfigureinp; "NtConfigureInputSpace"
0x140038f66  mov     rdx, 10Eh
0x140038f6d  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x140038f74  nop     dword ptr [rax+rax+00h]
0x140038f79  call    cs:__imp_PsIsWin32KFilterEnabled
0x140038f80  nop     dword ptr [rax+rax+00h]
0x140038f85  test    al, al
0x140038f87  jz      short loc_140038FB3
0x140038f89  lea     rcx, W32pServiceTableFilter
0x140038f90  mov     edx, cs:W32pServiceLimitFilter
0x140038f96  mov     rax, 10Eh
0x140038f9d  lea     rcx, [rcx+rdx*4]
0x140038fa1  movsx   eax, byte ptr [rcx+rax]
0x140038fa5  or      eax, eax
0x140038fa7  jle     short loc_140038FAE
0x140038fa9  mov     eax, 0C000001Ch
0x140038fae  add     rsp, 48h
0x140038fb2  retn
0x140038fb3  mov     rax, cs:__imp_NtConfigureInputSpace
0x140038fba  mov     rcx, [rsp+48h+var_28]
0x140038fbf  mov     rdx, [rsp+48h+var_20]
0x140038fc4  mov     r8, [rsp+48h+var_18]
0x140038fc9  mov     r9, [rsp+48h+var_10]
0x140038fce  add     rsp, 48h
0x140038fd2  jmp     rax
```
