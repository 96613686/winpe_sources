# _stub_DCompositionSetChannelConnectionId

- ea: `0x14003aed0`
- end: `0x14003af77`
- name: `_stub_DCompositionSetChannelConnectionId`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x14003aed0`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x14003af19`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x14003af19`

## string_xrefs

- `0x14003aeff`: `NtDCompositionSetChannelConnectionId`

## pseudocode

```c
__int64 stub_DCompositionSetChannelConnectionId()
{
  __int64 result; // rax

  if ( !(unsigned __int8)IsWin32KSyscallFiltered() )
    return NtDCompositionSetChannelConnectionId();
  NtUserWin32kSysCallFilterStub();
  if ( !(unsigned __int8)PsIsWin32KFilterEnabled() )
    return NtDCompositionSetChannelConnectionId();
  result = (unsigned int)*((char *)&W32pServiceTableFilter[39] + 4 * (unsigned int)W32pServiceLimitFilter + 4);
  if ( (int)result > 0 )
    return 3221225500LL;
  return result;
}

```

## disassembly

```asm
0x14003aed0  sub     rsp, 48h
0x14003aed4  mov     [rsp+48h+var_28], rcx
0x14003aed9  mov     [rsp+48h+var_20], rdx
0x14003aede  mov     [rsp+48h+var_18], r8
0x14003aee3  mov     [rsp+48h+var_10], r9
0x14003aee8  mov     rcx, 13Ch
0x14003aeef  call    cs:__imp_IsWin32KSyscallFiltered
0x14003aef6  nop     dword ptr [rax+rax+00h]
0x14003aefb  test    al, al
0x14003aefd  jz      short loc_14003AF53
0x14003aeff  lea     rcx, aNtdcomposition_40; "NtDCompositionSetChannelConnectionId"
0x14003af06  mov     rdx, 13Ch
0x14003af0d  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x14003af14  nop     dword ptr [rax+rax+00h]
0x14003af19  call    cs:__imp_PsIsWin32KFilterEnabled
0x14003af20  nop     dword ptr [rax+rax+00h]
0x14003af25  test    al, al
0x14003af27  jz      short loc_14003AF53
0x14003af29  lea     rcx, W32pServiceTableFilter
0x14003af30  mov     edx, cs:W32pServiceLimitFilter
0x14003af36  mov     rax, 13Ch
0x14003af3d  lea     rcx, [rcx+rdx*4]
0x14003af41  movsx   eax, byte ptr [rcx+rax]
0x14003af45  or      eax, eax
0x14003af47  jle     short loc_14003AF4E
0x14003af49  mov     eax, 0C000001Ch
0x14003af4e  add     rsp, 48h
0x14003af52  retn
0x14003af53  mov     rax, cs:__imp_NtDCompositionSetChannelConnectionId
0x14003af5a  mov     rcx, [rsp+48h+var_28]
0x14003af5f  mov     rdx, [rsp+48h+var_20]
0x14003af64  mov     r8, [rsp+48h+var_18]
0x14003af69  mov     r9, [rsp+48h+var_10]
0x14003af6e  add     rsp, 48h
0x14003af72  jmp     rax
```
