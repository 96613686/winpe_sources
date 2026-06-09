# _stub_DCompositionWaitForCompositorClock

- ea: `0x14003b6d0`
- end: `0x14003b777`
- name: `_stub_DCompositionWaitForCompositorClock`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x14003b6d0`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x14003b719`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x14003b719`

## string_xrefs

- `0x14003b6ff`: `NtDCompositionWaitForCompositorClock`

## pseudocode

```c
__int64 stub_DCompositionWaitForCompositorClock()
{
  __int64 result; // rax

  if ( !(unsigned __int8)IsWin32KSyscallFiltered() )
    return NtDCompositionWaitForCompositorClock();
  NtUserWin32kSysCallFilterStub();
  if ( !(unsigned __int8)PsIsWin32KFilterEnabled() )
    return NtDCompositionWaitForCompositorClock();
  result = (unsigned int)*((char *)&W32pServiceTableFilter[40] + 4 * (unsigned int)W32pServiceLimitFilter + 5);
  if ( (int)result > 0 )
    return 3221225500LL;
  return result;
}

```

## disassembly

```asm
0x14003b6d0  sub     rsp, 48h
0x14003b6d4  mov     [rsp+48h+var_28], rcx
0x14003b6d9  mov     [rsp+48h+var_20], rdx
0x14003b6de  mov     [rsp+48h+var_18], r8
0x14003b6e3  mov     [rsp+48h+var_10], r9
0x14003b6e8  mov     rcx, 145h
0x14003b6ef  call    cs:__imp_IsWin32KSyscallFiltered
0x14003b6f6  nop     dword ptr [rax+rax+00h]
0x14003b6fb  test    al, al
0x14003b6fd  jz      short loc_14003B753
0x14003b6ff  lea     rcx, aNtdcomposition_49; "NtDCompositionWaitForCompositorClock"
0x14003b706  mov     rdx, 145h
0x14003b70d  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x14003b714  nop     dword ptr [rax+rax+00h]
0x14003b719  call    cs:__imp_PsIsWin32KFilterEnabled
0x14003b720  nop     dword ptr [rax+rax+00h]
0x14003b725  test    al, al
0x14003b727  jz      short loc_14003B753
0x14003b729  lea     rcx, W32pServiceTableFilter
0x14003b730  mov     edx, cs:W32pServiceLimitFilter
0x14003b736  mov     rax, 145h
0x14003b73d  lea     rcx, [rcx+rdx*4]
0x14003b741  movsx   eax, byte ptr [rcx+rax]
0x14003b745  or      eax, eax
0x14003b747  jle     short loc_14003B74E
0x14003b749  mov     eax, 0C000001Ch
0x14003b74e  add     rsp, 48h
0x14003b752  retn
0x14003b753  mov     rax, cs:__imp_NtDCompositionWaitForCompositorClock
0x14003b75a  mov     rcx, [rsp+48h+var_28]
0x14003b75f  mov     rdx, [rsp+48h+var_20]
0x14003b764  mov     r8, [rsp+48h+var_18]
0x14003b769  mov     r9, [rsp+48h+var_10]
0x14003b76e  add     rsp, 48h
0x14003b772  jmp     rax
```
