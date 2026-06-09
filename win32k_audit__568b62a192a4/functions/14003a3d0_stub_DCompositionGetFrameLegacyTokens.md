# _stub_DCompositionGetFrameLegacyTokens

- ea: `0x14003a3d0`
- end: `0x14003a477`
- name: `_stub_DCompositionGetFrameLegacyTokens`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x14003a3d0`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x14003a419`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x14003a419`

## string_xrefs

- `0x14003a3ff`: `NtDCompositionGetFrameLegacyTokens`

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
0x14003a3d0  sub     rsp, 48h
0x14003a3d4  mov     [rsp+48h+var_28], rcx
0x14003a3d9  mov     [rsp+48h+var_20], rdx
0x14003a3de  mov     [rsp+48h+var_18], r8
0x14003a3e3  mov     [rsp+48h+var_10], r9
0x14003a3e8  mov     rcx, 12Ch
0x14003a3ef  call    cs:__imp_IsWin32KSyscallFiltered
0x14003a3f6  nop     dword ptr [rax+rax+00h]
0x14003a3fb  test    al, al
0x14003a3fd  jz      short loc_14003A453
0x14003a3ff  lea     rcx, aNtdcomposition_24; "NtDCompositionGetFrameLegacyTokens"
0x14003a406  mov     rdx, 12Ch
0x14003a40d  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x14003a414  nop     dword ptr [rax+rax+00h]
0x14003a419  call    cs:__imp_PsIsWin32KFilterEnabled
0x14003a420  nop     dword ptr [rax+rax+00h]
0x14003a425  test    al, al
0x14003a427  jz      short loc_14003A453
0x14003a429  lea     rcx, W32pServiceTableFilter
0x14003a430  mov     edx, cs:W32pServiceLimitFilter
0x14003a436  mov     rax, 12Ch
0x14003a43d  lea     rcx, [rcx+rdx*4]
0x14003a441  movsx   eax, byte ptr [rcx+rax]
0x14003a445  or      eax, eax
0x14003a447  jle     short loc_14003A44E
0x14003a449  mov     eax, 0C000001Ch
0x14003a44e  add     rsp, 48h
0x14003a452  retn
0x14003a453  mov     rax, cs:__imp_NtDCompositionGetFrameLegacyTokens
0x14003a45a  mov     rcx, [rsp+48h+var_28]
0x14003a45f  mov     rdx, [rsp+48h+var_20]
0x14003a464  mov     r8, [rsp+48h+var_18]
0x14003a469  mov     r9, [rsp+48h+var_10]
0x14003a46e  add     rsp, 48h
0x14003a472  jmp     rax
```
