# _stub_DCompositionGetFrameLegacyTokens

- ea: `0x14003a5a0`
- end: `0x14003a647`
- name: `_stub_DCompositionGetFrameLegacyTokens`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x14003a5a0`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x14003a5e9`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x14003a5e9`

## string_xrefs

- `0x14003a5cf`: `NtDCompositionGetFrameLegacyTokens`

## pseudocode

```c
__int64 stub_DCompositionGetFrameLegacyTokens()
{
  __int64 result; // rax

  if ( !(unsigned __int8)IsWin32KSyscallFiltered() )
    return NtDCompositionGetFrameLegacyTokens();
  NtUserWin32kSysCallFilterStub();
  if ( !(unsigned __int8)PsIsWin32KFilterEnabled() )
    return NtDCompositionGetFrameLegacyTokens();
  result = (unsigned int)*((char *)&W32pServiceTableFilter[37] + 4 * (unsigned int)W32pServiceLimitFilter + 4);
  if ( (int)result > 0 )
    return 3221225500LL;
  return result;
}

```

## disassembly

```asm
0x14003a5a0  sub     rsp, 48h
0x14003a5a4  mov     [rsp+48h+var_28], rcx
0x14003a5a9  mov     [rsp+48h+var_20], rdx
0x14003a5ae  mov     [rsp+48h+var_18], r8
0x14003a5b3  mov     [rsp+48h+var_10], r9
0x14003a5b8  mov     rcx, 12Ch
0x14003a5bf  call    cs:__imp_IsWin32KSyscallFiltered
0x14003a5c6  nop     dword ptr [rax+rax+00h]
0x14003a5cb  test    al, al
0x14003a5cd  jz      short loc_14003A623
0x14003a5cf  lea     rcx, aNtdcomposition_24; "NtDCompositionGetFrameLegacyTokens"
0x14003a5d6  mov     rdx, 12Ch
0x14003a5dd  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x14003a5e4  nop     dword ptr [rax+rax+00h]
0x14003a5e9  call    cs:__imp_PsIsWin32KFilterEnabled
0x14003a5f0  nop     dword ptr [rax+rax+00h]
0x14003a5f5  test    al, al
0x14003a5f7  jz      short loc_14003A623
0x14003a5f9  lea     rcx, W32pServiceTableFilter
0x14003a600  mov     edx, cs:W32pServiceLimitFilter
0x14003a606  mov     rax, 12Ch
0x14003a60d  lea     rcx, [rcx+rdx*4]
0x14003a611  movsx   eax, byte ptr [rcx+rax]
0x14003a615  or      eax, eax
0x14003a617  jle     short loc_14003A61E
0x14003a619  mov     eax, 0C000001Ch
0x14003a61e  add     rsp, 48h
0x14003a622  retn
0x14003a623  mov     rax, cs:__imp_NtDCompositionGetFrameLegacyTokens
0x14003a62a  mov     rcx, [rsp+48h+var_28]
0x14003a62f  mov     rdx, [rsp+48h+var_20]
0x14003a634  mov     r8, [rsp+48h+var_18]
0x14003a639  mov     r9, [rsp+48h+var_10]
0x14003a63e  add     rsp, 48h
0x14003a642  jmp     rax
```
