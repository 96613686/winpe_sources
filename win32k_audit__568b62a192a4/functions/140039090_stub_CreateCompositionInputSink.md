# _stub_CreateCompositionInputSink

- ea: `0x140039090`
- end: `0x140039137`
- name: `_stub_CreateCompositionInputSink`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x140039090`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x1400390d9`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x1400390d9`

## string_xrefs

- `0x1400390bf`: `NtCreateCompositionInputSink`

## pseudocode

```c
__int64 stub_CreateCompositionInputSink()
{
  __int64 result; // rax

  if ( !(unsigned __int8)IsWin32KSyscallFiltered() )
    return NtCreateCompositionInputSink();
  NtUserWin32kSysCallFilterStub();
  if ( !(unsigned __int8)PsIsWin32KFilterEnabled() )
    return NtCreateCompositionInputSink();
  result = (unsigned int)*((char *)&W32pServiceTableFilter[34] + 4 * (unsigned int)W32pServiceLimitFilter);
  if ( (int)result > 0 )
    return 3221225500LL;
  return result;
}

```

## disassembly

```asm
0x140039090  sub     rsp, 48h
0x140039094  mov     [rsp+48h+var_28], rcx
0x140039099  mov     [rsp+48h+var_20], rdx
0x14003909e  mov     [rsp+48h+var_18], r8
0x1400390a3  mov     [rsp+48h+var_10], r9
0x1400390a8  mov     rcx, 110h
0x1400390af  call    cs:__imp_IsWin32KSyscallFiltered
0x1400390b6  nop     dword ptr [rax+rax+00h]
0x1400390bb  test    al, al
0x1400390bd  jz      short loc_140039113
0x1400390bf  lea     rcx, aNtcreatecompos; "NtCreateCompositionInputSink"
0x1400390c6  mov     rdx, 110h
0x1400390cd  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x1400390d4  nop     dword ptr [rax+rax+00h]
0x1400390d9  call    cs:__imp_PsIsWin32KFilterEnabled
0x1400390e0  nop     dword ptr [rax+rax+00h]
0x1400390e5  test    al, al
0x1400390e7  jz      short loc_140039113
0x1400390e9  lea     rcx, W32pServiceTableFilter
0x1400390f0  mov     edx, cs:W32pServiceLimitFilter
0x1400390f6  mov     rax, 110h
0x1400390fd  lea     rcx, [rcx+rdx*4]
0x140039101  movsx   eax, byte ptr [rcx+rax]
0x140039105  or      eax, eax
0x140039107  jle     short loc_14003910E
0x140039109  mov     eax, 0C000001Ch
0x14003910e  add     rsp, 48h
0x140039112  retn
0x140039113  mov     rax, cs:__imp_NtCreateCompositionInputSink
0x14003911a  mov     rcx, [rsp+48h+var_28]
0x14003911f  mov     rdx, [rsp+48h+var_20]
0x140039124  mov     r8, [rsp+48h+var_18]
0x140039129  mov     r9, [rsp+48h+var_10]
0x14003912e  add     rsp, 48h
0x140039132  jmp     rax
```
