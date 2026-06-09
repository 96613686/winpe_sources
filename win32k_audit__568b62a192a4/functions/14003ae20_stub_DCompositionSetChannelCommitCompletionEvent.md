# _stub_DCompositionSetChannelCommitCompletionEvent

- ea: `0x14003ae20`
- end: `0x14003aec7`
- name: `_stub_DCompositionSetChannelCommitCompletionEvent`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x14003ae20`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x14003ae69`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x14003ae69`

## string_xrefs

- `0x14003ae4f`: `NtDCompositionSetChannelCommitCompletionEvent`

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
0x14003ae20  sub     rsp, 48h
0x14003ae24  mov     [rsp+48h+var_28], rcx
0x14003ae29  mov     [rsp+48h+var_20], rdx
0x14003ae2e  mov     [rsp+48h+var_18], r8
0x14003ae33  mov     [rsp+48h+var_10], r9
0x14003ae38  mov     rcx, 13Bh
0x14003ae3f  call    cs:__imp_IsWin32KSyscallFiltered
0x14003ae46  nop     dword ptr [rax+rax+00h]
0x14003ae4b  test    al, al
0x14003ae4d  jz      short loc_14003AEA3
0x14003ae4f  lea     rcx, aNtdcomposition_39; "NtDCompositionSetChannelCommitCompletio"...
0x14003ae56  mov     rdx, 13Bh
0x14003ae5d  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x14003ae64  nop     dword ptr [rax+rax+00h]
0x14003ae69  call    cs:__imp_PsIsWin32KFilterEnabled
0x14003ae70  nop     dword ptr [rax+rax+00h]
0x14003ae75  test    al, al
0x14003ae77  jz      short loc_14003AEA3
0x14003ae79  lea     rcx, W32pServiceTableFilter
0x14003ae80  mov     edx, cs:W32pServiceLimitFilter
0x14003ae86  mov     rax, 13Bh
0x14003ae8d  lea     rcx, [rcx+rdx*4]
0x14003ae91  movsx   eax, byte ptr [rcx+rax]
0x14003ae95  or      eax, eax
0x14003ae97  jle     short loc_14003AE9E
0x14003ae99  mov     eax, 0C000001Ch
0x14003ae9e  add     rsp, 48h
0x14003aea2  retn
0x14003aea3  mov     rax, cs:__imp_NtDCompositionSetChannelCommitCompletionEvent
0x14003aeaa  mov     rcx, [rsp+48h+var_28]
0x14003aeaf  mov     rdx, [rsp+48h+var_20]
0x14003aeb4  mov     r8, [rsp+48h+var_18]
0x14003aeb9  mov     r9, [rsp+48h+var_10]
0x14003aebe  add     rsp, 48h
0x14003aec2  jmp     rax
```
