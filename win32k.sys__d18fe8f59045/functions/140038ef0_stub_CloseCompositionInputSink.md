# _stub_CloseCompositionInputSink

- ea: `0x140038ef0`
- end: `0x140038f97`
- name: `_stub_CloseCompositionInputSink`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x140038ef0`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140038f39`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140038f39`

## string_xrefs

- `0x140038f1f`: `NtCloseCompositionInputSink`

## pseudocode

```c
__int64 stub_CloseCompositionInputSink()
{
  __int64 result; // rax

  if ( !(unsigned __int8)IsWin32KSyscallFiltered() )
    return NtCloseCompositionInputSink();
  NtUserWin32kSysCallFilterStub();
  if ( !(unsigned __int8)PsIsWin32KFilterEnabled() )
    return NtCloseCompositionInputSink();
  result = (unsigned int)*((char *)&W32pServiceTableFilter[33] + 4 * (unsigned int)W32pServiceLimitFilter + 3);
  if ( (int)result > 0 )
    return 3221225500LL;
  return result;
}

```

## disassembly

```asm
0x140038ef0  sub     rsp, 48h
0x140038ef4  mov     [rsp+48h+var_28], rcx
0x140038ef9  mov     [rsp+48h+var_20], rdx
0x140038efe  mov     [rsp+48h+var_18], r8
0x140038f03  mov     [rsp+48h+var_10], r9
0x140038f08  mov     rcx, 10Bh
0x140038f0f  call    cs:__imp_IsWin32KSyscallFiltered
0x140038f16  nop     dword ptr [rax+rax+00h]
0x140038f1b  test    al, al
0x140038f1d  jz      short loc_140038F73
0x140038f1f  lea     rcx, aNtclosecomposi; "NtCloseCompositionInputSink"
0x140038f26  mov     rdx, 10Bh
0x140038f2d  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x140038f34  nop     dword ptr [rax+rax+00h]
0x140038f39  call    cs:__imp_PsIsWin32KFilterEnabled
0x140038f40  nop     dword ptr [rax+rax+00h]
0x140038f45  test    al, al
0x140038f47  jz      short loc_140038F73
0x140038f49  lea     rcx, W32pServiceTableFilter
0x140038f50  mov     edx, cs:W32pServiceLimitFilter
0x140038f56  mov     rax, 10Bh
0x140038f5d  lea     rcx, [rcx+rdx*4]
0x140038f61  movsx   eax, byte ptr [rcx+rax]
0x140038f65  or      eax, eax
0x140038f67  jle     short loc_140038F6E
0x140038f69  mov     eax, 0C000001Ch
0x140038f6e  add     rsp, 48h
0x140038f72  retn
0x140038f73  mov     rax, cs:__imp_NtCloseCompositionInputSink
0x140038f7a  mov     rcx, [rsp+48h+var_28]
0x140038f7f  mov     rdx, [rsp+48h+var_20]
0x140038f84  mov     r8, [rsp+48h+var_18]
0x140038f89  mov     r9, [rsp+48h+var_10]
0x140038f8e  add     rsp, 48h
0x140038f92  jmp     rax
```
