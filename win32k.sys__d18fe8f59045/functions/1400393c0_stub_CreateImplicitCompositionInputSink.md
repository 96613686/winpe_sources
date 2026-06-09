# _stub_CreateImplicitCompositionInputSink

- ea: `0x1400393c0`
- end: `0x140039467`
- name: `_stub_CreateImplicitCompositionInputSink`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x1400393c0`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140039409`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140039409`

## string_xrefs

- `0x1400393ef`: `NtCreateImplicitCompositionInputSink`

## pseudocode

```c
__int64 stub_CreateImplicitCompositionInputSink()
{
  __int64 result; // rax

  if ( !(unsigned __int8)IsWin32KSyscallFiltered() )
    return NtCreateImplicitCompositionInputSink();
  NtUserWin32kSysCallFilterStub();
  if ( !(unsigned __int8)PsIsWin32KFilterEnabled() )
    return NtCreateImplicitCompositionInputSink();
  result = (unsigned int)*((char *)&W32pServiceTableFilter[34] + 4 * (unsigned int)W32pServiceLimitFilter + 2);
  if ( (int)result > 0 )
    return 3221225500LL;
  return result;
}

```

## disassembly

```asm
0x1400393c0  sub     rsp, 48h
0x1400393c4  mov     [rsp+48h+var_28], rcx
0x1400393c9  mov     [rsp+48h+var_20], rdx
0x1400393ce  mov     [rsp+48h+var_18], r8
0x1400393d3  mov     [rsp+48h+var_10], r9
0x1400393d8  mov     rcx, 112h
0x1400393df  call    cs:__imp_IsWin32KSyscallFiltered
0x1400393e6  nop     dword ptr [rax+rax+00h]
0x1400393eb  test    al, al
0x1400393ed  jz      short loc_140039443
0x1400393ef  lea     rcx, aNtcreateimplic; "NtCreateImplicitCompositionInputSink"
0x1400393f6  mov     rdx, 112h
0x1400393fd  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x140039404  nop     dword ptr [rax+rax+00h]
0x140039409  call    cs:__imp_PsIsWin32KFilterEnabled
0x140039410  nop     dword ptr [rax+rax+00h]
0x140039415  test    al, al
0x140039417  jz      short loc_140039443
0x140039419  lea     rcx, W32pServiceTableFilter
0x140039420  mov     edx, cs:W32pServiceLimitFilter
0x140039426  mov     rax, 112h
0x14003942d  lea     rcx, [rcx+rdx*4]
0x140039431  movsx   eax, byte ptr [rcx+rax]
0x140039435  or      eax, eax
0x140039437  jle     short loc_14003943E
0x140039439  mov     eax, 0C000001Ch
0x14003943e  add     rsp, 48h
0x140039442  retn
0x140039443  mov     rax, cs:__imp_NtCreateImplicitCompositionInputSink
0x14003944a  mov     rcx, [rsp+48h+var_28]
0x14003944f  mov     rdx, [rsp+48h+var_20]
0x140039454  mov     r8, [rsp+48h+var_18]
0x140039459  mov     r9, [rsp+48h+var_10]
0x14003945e  add     rsp, 48h
0x140039462  jmp     rax
```
