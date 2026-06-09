# _stub_DCompositionSetChannelConnectionId

- ea: `0x14003b0a0`
- end: `0x14003b147`
- name: `_stub_DCompositionSetChannelConnectionId`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x14003b0a0`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x14003b0e9`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x14003b0e9`

## string_xrefs

- `0x14003b0cf`: `NtDCompositionSetChannelConnectionId`

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
0x14003b0a0  sub     rsp, 48h
0x14003b0a4  mov     [rsp+48h+var_28], rcx
0x14003b0a9  mov     [rsp+48h+var_20], rdx
0x14003b0ae  mov     [rsp+48h+var_18], r8
0x14003b0b3  mov     [rsp+48h+var_10], r9
0x14003b0b8  mov     rcx, 13Ch
0x14003b0bf  call    cs:__imp_IsWin32KSyscallFiltered
0x14003b0c6  nop     dword ptr [rax+rax+00h]
0x14003b0cb  test    al, al
0x14003b0cd  jz      short loc_14003B123
0x14003b0cf  lea     rcx, aNtdcomposition_40; "NtDCompositionSetChannelConnectionId"
0x14003b0d6  mov     rdx, 13Ch
0x14003b0dd  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x14003b0e4  nop     dword ptr [rax+rax+00h]
0x14003b0e9  call    cs:__imp_PsIsWin32KFilterEnabled
0x14003b0f0  nop     dword ptr [rax+rax+00h]
0x14003b0f5  test    al, al
0x14003b0f7  jz      short loc_14003B123
0x14003b0f9  lea     rcx, W32pServiceTableFilter
0x14003b100  mov     edx, cs:W32pServiceLimitFilter
0x14003b106  mov     rax, 13Ch
0x14003b10d  lea     rcx, [rcx+rdx*4]
0x14003b111  movsx   eax, byte ptr [rcx+rax]
0x14003b115  or      eax, eax
0x14003b117  jle     short loc_14003B11E
0x14003b119  mov     eax, 0C000001Ch
0x14003b11e  add     rsp, 48h
0x14003b122  retn
0x14003b123  mov     rax, cs:__imp_NtDCompositionSetChannelConnectionId
0x14003b12a  mov     rcx, [rsp+48h+var_28]
0x14003b12f  mov     rdx, [rsp+48h+var_20]
0x14003b134  mov     r8, [rsp+48h+var_18]
0x14003b139  mov     r9, [rsp+48h+var_10]
0x14003b13e  add     rsp, 48h
0x14003b142  jmp     rax
```
