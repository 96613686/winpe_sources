# _stub_DCompositionSendDwmLpcMessage

- ea: `0x14003ae90`
- end: `0x14003af37`
- name: `_stub_DCompositionSendDwmLpcMessage`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x14003ae90`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x14003aed9`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x14003aed9`

## string_xrefs

- `0x14003aebf`: `NtDCompositionSendDwmLpcMessage`

## pseudocode

```c
__int64 stub_DCompositionSendDwmLpcMessage()
{
  __int64 result; // rax

  if ( !(unsigned __int8)IsWin32KSyscallFiltered() )
    return NtDCompositionSendDwmLpcMessage();
  NtUserWin32kSysCallFilterStub();
  if ( !(unsigned __int8)PsIsWin32KFilterEnabled() )
    return NtDCompositionSendDwmLpcMessage();
  result = (unsigned int)*((char *)&W32pServiceTableFilter[39] + 4 * (unsigned int)W32pServiceLimitFilter + 1);
  if ( (int)result > 0 )
    return 3221225500LL;
  return result;
}

```

## disassembly

```asm
0x14003ae90  sub     rsp, 48h
0x14003ae94  mov     [rsp+48h+var_28], rcx
0x14003ae99  mov     [rsp+48h+var_20], rdx
0x14003ae9e  mov     [rsp+48h+var_18], r8
0x14003aea3  mov     [rsp+48h+var_10], r9
0x14003aea8  mov     rcx, 139h
0x14003aeaf  call    cs:__imp_IsWin32KSyscallFiltered
0x14003aeb6  nop     dword ptr [rax+rax+00h]
0x14003aebb  test    al, al
0x14003aebd  jz      short loc_14003AF13
0x14003aebf  lea     rcx, aNtdcomposition_37; "NtDCompositionSendDwmLpcMessage"
0x14003aec6  mov     rdx, 139h
0x14003aecd  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x14003aed4  nop     dword ptr [rax+rax+00h]
0x14003aed9  call    cs:__imp_PsIsWin32KFilterEnabled
0x14003aee0  nop     dword ptr [rax+rax+00h]
0x14003aee5  test    al, al
0x14003aee7  jz      short loc_14003AF13
0x14003aee9  lea     rcx, W32pServiceTableFilter
0x14003aef0  mov     edx, cs:W32pServiceLimitFilter
0x14003aef6  mov     rax, 139h
0x14003aefd  lea     rcx, [rcx+rdx*4]
0x14003af01  movsx   eax, byte ptr [rcx+rax]
0x14003af05  or      eax, eax
0x14003af07  jle     short loc_14003AF0E
0x14003af09  mov     eax, 0C000001Ch
0x14003af0e  add     rsp, 48h
0x14003af12  retn
0x14003af13  mov     rax, cs:__imp_NtDCompositionSendDwmLpcMessage
0x14003af1a  mov     rcx, [rsp+48h+var_28]
0x14003af1f  mov     rdx, [rsp+48h+var_20]
0x14003af24  mov     r8, [rsp+48h+var_18]
0x14003af29  mov     r9, [rsp+48h+var_10]
0x14003af2e  add     rsp, 48h
0x14003af32  jmp     rax
```
