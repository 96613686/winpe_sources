# _stub_DCompositionProcessChannelBatchBuffer

- ea: `0x14003aa70`
- end: `0x14003ab17`
- name: `_stub_DCompositionProcessChannelBatchBuffer`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x14003aa70`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x14003aab9`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x14003aab9`

## string_xrefs

- `0x14003aa9f`: `NtDCompositionProcessChannelBatchBuffer`

## pseudocode

```c
__int64 stub_DCompositionProcessChannelBatchBuffer()
{
  __int64 result; // rax

  if ( !(unsigned __int8)IsWin32KSyscallFiltered() )
    return NtDCompositionProcessChannelBatchBuffer();
  NtUserWin32kSysCallFilterStub();
  if ( !(unsigned __int8)PsIsWin32KFilterEnabled() )
    return NtDCompositionProcessChannelBatchBuffer();
  result = (unsigned int)*((char *)&W32pServiceTableFilter[38] + 4 * (unsigned int)W32pServiceLimitFilter + 3);
  if ( (int)result > 0 )
    return 3221225500LL;
  return result;
}

```

## disassembly

```asm
0x14003aa70  sub     rsp, 48h
0x14003aa74  mov     [rsp+48h+var_28], rcx
0x14003aa79  mov     [rsp+48h+var_20], rdx
0x14003aa7e  mov     [rsp+48h+var_18], r8
0x14003aa83  mov     [rsp+48h+var_10], r9
0x14003aa88  mov     rcx, 133h
0x14003aa8f  call    cs:__imp_IsWin32KSyscallFiltered
0x14003aa96  nop     dword ptr [rax+rax+00h]
0x14003aa9b  test    al, al
0x14003aa9d  jz      short loc_14003AAF3
0x14003aa9f  lea     rcx, aNtdcomposition_31; "NtDCompositionProcessChannelBatchBuffer"
0x14003aaa6  mov     rdx, 133h
0x14003aaad  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x14003aab4  nop     dword ptr [rax+rax+00h]
0x14003aab9  call    cs:__imp_PsIsWin32KFilterEnabled
0x14003aac0  nop     dword ptr [rax+rax+00h]
0x14003aac5  test    al, al
0x14003aac7  jz      short loc_14003AAF3
0x14003aac9  lea     rcx, W32pServiceTableFilter
0x14003aad0  mov     edx, cs:W32pServiceLimitFilter
0x14003aad6  mov     rax, 133h
0x14003aadd  lea     rcx, [rcx+rdx*4]
0x14003aae1  movsx   eax, byte ptr [rcx+rax]
0x14003aae5  or      eax, eax
0x14003aae7  jle     short loc_14003AAEE
0x14003aae9  mov     eax, 0C000001Ch
0x14003aaee  add     rsp, 48h
0x14003aaf2  retn
0x14003aaf3  mov     rax, cs:__imp_NtDCompositionProcessChannelBatchBuffer
0x14003aafa  mov     rcx, [rsp+48h+var_28]
0x14003aaff  mov     rdx, [rsp+48h+var_20]
0x14003ab04  mov     r8, [rsp+48h+var_18]
0x14003ab09  mov     r9, [rsp+48h+var_10]
0x14003ab0e  add     rsp, 48h
0x14003ab12  jmp     rax
```
