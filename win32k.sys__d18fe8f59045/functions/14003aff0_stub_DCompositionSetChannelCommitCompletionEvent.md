# _stub_DCompositionSetChannelCommitCompletionEvent

- ea: `0x14003aff0`
- end: `0x14003b097`
- name: `_stub_DCompositionSetChannelCommitCompletionEvent`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x14003aff0`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x14003b039`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x14003b039`

## string_xrefs

- `0x14003b01f`: `NtDCompositionSetChannelCommitCompletionEvent`

## pseudocode

```c
__int64 stub_DCompositionSetChannelCommitCompletionEvent()
{
  __int64 result; // rax

  if ( !(unsigned __int8)IsWin32KSyscallFiltered() )
    return NtDCompositionSetChannelCommitCompletionEvent();
  NtUserWin32kSysCallFilterStub();
  if ( !(unsigned __int8)PsIsWin32KFilterEnabled() )
    return NtDCompositionSetChannelCommitCompletionEvent();
  result = (unsigned int)*((char *)&W32pServiceTableFilter[39] + 4 * (unsigned int)W32pServiceLimitFilter + 3);
  if ( (int)result > 0 )
    return 3221225500LL;
  return result;
}

```

## disassembly

```asm
0x14003aff0  sub     rsp, 48h
0x14003aff4  mov     [rsp+48h+var_28], rcx
0x14003aff9  mov     [rsp+48h+var_20], rdx
0x14003affe  mov     [rsp+48h+var_18], r8
0x14003b003  mov     [rsp+48h+var_10], r9
0x14003b008  mov     rcx, 13Bh
0x14003b00f  call    cs:__imp_IsWin32KSyscallFiltered
0x14003b016  nop     dword ptr [rax+rax+00h]
0x14003b01b  test    al, al
0x14003b01d  jz      short loc_14003B073
0x14003b01f  lea     rcx, aNtdcomposition_39; "NtDCompositionSetChannelCommitCompletio"...
0x14003b026  mov     rdx, 13Bh
0x14003b02d  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x14003b034  nop     dword ptr [rax+rax+00h]
0x14003b039  call    cs:__imp_PsIsWin32KFilterEnabled
0x14003b040  nop     dword ptr [rax+rax+00h]
0x14003b045  test    al, al
0x14003b047  jz      short loc_14003B073
0x14003b049  lea     rcx, W32pServiceTableFilter
0x14003b050  mov     edx, cs:W32pServiceLimitFilter
0x14003b056  mov     rax, 13Bh
0x14003b05d  lea     rcx, [rcx+rdx*4]
0x14003b061  movsx   eax, byte ptr [rcx+rax]
0x14003b065  or      eax, eax
0x14003b067  jle     short loc_14003B06E
0x14003b069  mov     eax, 0C000001Ch
0x14003b06e  add     rsp, 48h
0x14003b072  retn
0x14003b073  mov     rax, cs:__imp_NtDCompositionSetChannelCommitCompletionEvent
0x14003b07a  mov     rcx, [rsp+48h+var_28]
0x14003b07f  mov     rdx, [rsp+48h+var_20]
0x14003b084  mov     r8, [rsp+48h+var_18]
0x14003b089  mov     r9, [rsp+48h+var_10]
0x14003b08e  add     rsp, 48h
0x14003b092  jmp     rax
```
