# _stub_CompositorNotifyExitWindows

- ea: `0x140038e80`
- end: `0x140038f27`
- name: `_stub_CompositorNotifyExitWindows`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x140038e80`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140038ec9`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140038ec9`

## string_xrefs

- `0x140038eaf`: `NtCompositorNotifyExitWindows`

## pseudocode

```c
unsigned __int64 stub_CompositorNotifyExitWindows()
{
  unsigned __int64 result; // rax

  if ( !(unsigned __int8)IsWin32KSyscallFiltered() )
    return (unsigned __int64)NtCompositorNotifyExitWindows();
  NtUserWin32kSysCallFilterStub();
  if ( !(unsigned __int8)PsIsWin32KFilterEnabled() )
    return (unsigned __int64)NtCompositorNotifyExitWindows();
  result = (unsigned int)*((char *)&W32pServiceTableFilter[33] + 4 * (unsigned int)W32pServiceLimitFilter + 5);
  if ( (int)result > 0 )
    return 3221225500LL;
  return result;
}

```

## disassembly

```asm
0x140038e80  sub     rsp, 48h
0x140038e84  mov     [rsp+48h+var_28], rcx
0x140038e89  mov     [rsp+48h+var_20], rdx
0x140038e8e  mov     [rsp+48h+var_18], r8
0x140038e93  mov     [rsp+48h+var_10], r9
0x140038e98  mov     rcx, 10Dh
0x140038e9f  call    cs:__imp_IsWin32KSyscallFiltered
0x140038ea6  nop     dword ptr [rax+rax+00h]
0x140038eab  test    al, al
0x140038ead  jz      short loc_140038F03
0x140038eaf  lea     rcx, aNtcompositorno; "NtCompositorNotifyExitWindows"
0x140038eb6  mov     rdx, 10Dh
0x140038ebd  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x140038ec4  nop     dword ptr [rax+rax+00h]
0x140038ec9  call    cs:__imp_PsIsWin32KFilterEnabled
0x140038ed0  nop     dword ptr [rax+rax+00h]
0x140038ed5  test    al, al
0x140038ed7  jz      short loc_140038F03
0x140038ed9  lea     rcx, W32pServiceTableFilter
0x140038ee0  mov     edx, cs:W32pServiceLimitFilter
0x140038ee6  mov     rax, 10Dh
0x140038eed  lea     rcx, [rcx+rdx*4]
0x140038ef1  movsx   eax, byte ptr [rcx+rax]
0x140038ef5  or      eax, eax
0x140038ef7  jle     short loc_140038EFE
0x140038ef9  mov     eax, 0C000001Ch
0x140038efe  add     rsp, 48h
0x140038f02  retn
0x140038f03  mov     rax, cs:__imp_NtCompositorNotifyExitWindows
0x140038f0a  mov     rcx, [rsp+48h+var_28]
0x140038f0f  mov     rdx, [rsp+48h+var_20]
0x140038f14  mov     r8, [rsp+48h+var_18]
0x140038f19  mov     r9, [rsp+48h+var_10]
0x140038f1e  add     rsp, 48h
0x140038f22  jmp     rax
```
