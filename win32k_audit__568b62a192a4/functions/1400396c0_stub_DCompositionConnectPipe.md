# _stub_DCompositionConnectPipe

- ea: `0x1400396c0`
- end: `0x140039767`
- name: `_stub_DCompositionConnectPipe`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x1400396c0`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140039709`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140039709`

## string_xrefs

- `0x1400396ef`: `NtDCompositionConnectPipe`

## pseudocode

```c
__int64 stub_DCompositionConnectPipe()
{
  __int64 result; // rax

  if ( !(unsigned __int8)IsWin32KSyscallFiltered() )
    return NtDCompositionConnectPipe();
  NtUserWin32kSysCallFilterStub();
  if ( !(unsigned __int8)PsIsWin32KFilterEnabled() )
    return NtDCompositionConnectPipe();
  result = (unsigned int)*((char *)&W32pServiceTableFilter[35] + 4 * (unsigned int)W32pServiceLimitFilter + 1);
  if ( (int)result > 0 )
    return 3221225500LL;
  return result;
}

```

## disassembly

```asm
0x1400396c0  sub     rsp, 48h
0x1400396c4  mov     [rsp+48h+var_28], rcx
0x1400396c9  mov     [rsp+48h+var_20], rdx
0x1400396ce  mov     [rsp+48h+var_18], r8
0x1400396d3  mov     [rsp+48h+var_10], r9
0x1400396d8  mov     rcx, 119h
0x1400396df  call    cs:__imp_IsWin32KSyscallFiltered
0x1400396e6  nop     dword ptr [rax+rax+00h]
0x1400396eb  test    al, al
0x1400396ed  jz      short loc_140039743
0x1400396ef  lea     rcx, aNtdcomposition_5; "NtDCompositionConnectPipe"
0x1400396f6  mov     rdx, 119h
0x1400396fd  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x140039704  nop     dword ptr [rax+rax+00h]
0x140039709  call    cs:__imp_PsIsWin32KFilterEnabled
0x140039710  nop     dword ptr [rax+rax+00h]
0x140039715  test    al, al
0x140039717  jz      short loc_140039743
0x140039719  lea     rcx, W32pServiceTableFilter
0x140039720  mov     edx, cs:W32pServiceLimitFilter
0x140039726  mov     rax, 119h
0x14003972d  lea     rcx, [rcx+rdx*4]
0x140039731  movsx   eax, byte ptr [rcx+rax]
0x140039735  or      eax, eax
0x140039737  jle     short loc_14003973E
0x140039739  mov     eax, 0C000001Ch
0x14003973e  add     rsp, 48h
0x140039742  retn
0x140039743  mov     rax, cs:__imp_NtDCompositionConnectPipe
0x14003974a  mov     rcx, [rsp+48h+var_28]
0x14003974f  mov     rdx, [rsp+48h+var_20]
0x140039754  mov     r8, [rsp+48h+var_18]
0x140039759  mov     r9, [rsp+48h+var_10]
0x14003975e  add     rsp, 48h
0x140039762  jmp     rax
```
