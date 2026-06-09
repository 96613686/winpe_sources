# _stub_DCompositionSetDebugCounter

- ea: `0x14003b200`
- end: `0x14003b2a7`
- name: `_stub_DCompositionSetDebugCounter`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x14003b200`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x14003b249`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x14003b249`

## string_xrefs

- `0x14003b22f`: `NtDCompositionSetDebugCounter`

## pseudocode

```c
__int64 stub_DCompositionSetDebugCounter()
{
  __int64 result; // rax

  if ( !(unsigned __int8)IsWin32KSyscallFiltered() )
    return NtDCompositionSetDebugCounter();
  NtUserWin32kSysCallFilterStub();
  if ( !(unsigned __int8)PsIsWin32KFilterEnabled() )
    return NtDCompositionSetDebugCounter();
  result = (unsigned int)*((char *)&W32pServiceTableFilter[39] + 4 * (unsigned int)W32pServiceLimitFilter + 6);
  if ( (int)result > 0 )
    return 3221225500LL;
  return result;
}

```

## disassembly

```asm
0x14003b200  sub     rsp, 48h
0x14003b204  mov     [rsp+48h+var_28], rcx
0x14003b209  mov     [rsp+48h+var_20], rdx
0x14003b20e  mov     [rsp+48h+var_18], r8
0x14003b213  mov     [rsp+48h+var_10], r9
0x14003b218  mov     rcx, 13Eh
0x14003b21f  call    cs:__imp_IsWin32KSyscallFiltered
0x14003b226  nop     dword ptr [rax+rax+00h]
0x14003b22b  test    al, al
0x14003b22d  jz      short loc_14003B283
0x14003b22f  lea     rcx, aNtdcomposition_42; "NtDCompositionSetDebugCounter"
0x14003b236  mov     rdx, 13Eh
0x14003b23d  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x14003b244  nop     dword ptr [rax+rax+00h]
0x14003b249  call    cs:__imp_PsIsWin32KFilterEnabled
0x14003b250  nop     dword ptr [rax+rax+00h]
0x14003b255  test    al, al
0x14003b257  jz      short loc_14003B283
0x14003b259  lea     rcx, W32pServiceTableFilter
0x14003b260  mov     edx, cs:W32pServiceLimitFilter
0x14003b266  mov     rax, 13Eh
0x14003b26d  lea     rcx, [rcx+rdx*4]
0x14003b271  movsx   eax, byte ptr [rcx+rax]
0x14003b275  or      eax, eax
0x14003b277  jle     short loc_14003B27E
0x14003b279  mov     eax, 0C000001Ch
0x14003b27e  add     rsp, 48h
0x14003b282  retn
0x14003b283  mov     rax, cs:__imp_NtDCompositionSetDebugCounter
0x14003b28a  mov     rcx, [rsp+48h+var_28]
0x14003b28f  mov     rdx, [rsp+48h+var_20]
0x14003b294  mov     r8, [rsp+48h+var_18]
0x14003b299  mov     r9, [rsp+48h+var_10]
0x14003b29e  add     rsp, 48h
0x14003b2a2  jmp     rax
```
