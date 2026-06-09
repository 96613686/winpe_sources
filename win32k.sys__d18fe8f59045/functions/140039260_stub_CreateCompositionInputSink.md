# _stub_CreateCompositionInputSink

- ea: `0x140039260`
- end: `0x140039307`
- name: `_stub_CreateCompositionInputSink`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x140039260`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x1400392a9`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x1400392a9`

## string_xrefs

- `0x14003928f`: `NtCreateCompositionInputSink`

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
0x140039260  sub     rsp, 48h
0x140039264  mov     [rsp+48h+var_28], rcx
0x140039269  mov     [rsp+48h+var_20], rdx
0x14003926e  mov     [rsp+48h+var_18], r8
0x140039273  mov     [rsp+48h+var_10], r9
0x140039278  mov     rcx, 110h
0x14003927f  call    cs:__imp_IsWin32KSyscallFiltered
0x140039286  nop     dword ptr [rax+rax+00h]
0x14003928b  test    al, al
0x14003928d  jz      short loc_1400392E3
0x14003928f  lea     rcx, aNtcreatecompos; "NtCreateCompositionInputSink"
0x140039296  mov     rdx, 110h
0x14003929d  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x1400392a4  nop     dword ptr [rax+rax+00h]
0x1400392a9  call    cs:__imp_PsIsWin32KFilterEnabled
0x1400392b0  nop     dword ptr [rax+rax+00h]
0x1400392b5  test    al, al
0x1400392b7  jz      short loc_1400392E3
0x1400392b9  lea     rcx, W32pServiceTableFilter
0x1400392c0  mov     edx, cs:W32pServiceLimitFilter
0x1400392c6  mov     rax, 110h
0x1400392cd  lea     rcx, [rcx+rdx*4]
0x1400392d1  movsx   eax, byte ptr [rcx+rax]
0x1400392d5  or      eax, eax
0x1400392d7  jle     short loc_1400392DE
0x1400392d9  mov     eax, 0C000001Ch
0x1400392de  add     rsp, 48h
0x1400392e2  retn
0x1400392e3  mov     rax, cs:__imp_NtCreateCompositionInputSink
0x1400392ea  mov     rcx, [rsp+48h+var_28]
0x1400392ef  mov     rdx, [rsp+48h+var_20]
0x1400392f4  mov     r8, [rsp+48h+var_18]
0x1400392f9  mov     r9, [rsp+48h+var_10]
0x1400392fe  add     rsp, 48h
0x140039302  jmp     rax
```
