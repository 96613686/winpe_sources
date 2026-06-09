# _stub_DCompositionGetDeletedResources

- ea: `0x14003a1c0`
- end: `0x14003a267`
- name: `_stub_DCompositionGetDeletedResources`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x14003a1c0`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x14003a209`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x14003a209`

## string_xrefs

- `0x14003a1ef`: `NtDCompositionGetDeletedResources`

## pseudocode

```c
__int64 stub_DCompositionGetDeletedResources()
{
  __int64 result; // rax

  if ( !(unsigned __int8)IsWin32KSyscallFiltered() )
    return NtDCompositionGetDeletedResources();
  NtUserWin32kSysCallFilterStub();
  if ( !(unsigned __int8)PsIsWin32KFilterEnabled() )
    return NtDCompositionGetDeletedResources();
  result = (unsigned int)*((char *)&W32pServiceTableFilter[37] + 4 * (unsigned int)W32pServiceLimitFilter + 1);
  if ( (int)result > 0 )
    return 3221225500LL;
  return result;
}

```

## disassembly

```asm
0x14003a1c0  sub     rsp, 48h
0x14003a1c4  mov     [rsp+48h+var_28], rcx
0x14003a1c9  mov     [rsp+48h+var_20], rdx
0x14003a1ce  mov     [rsp+48h+var_18], r8
0x14003a1d3  mov     [rsp+48h+var_10], r9
0x14003a1d8  mov     rcx, 129h
0x14003a1df  call    cs:__imp_IsWin32KSyscallFiltered
0x14003a1e6  nop     dword ptr [rax+rax+00h]
0x14003a1eb  test    al, al
0x14003a1ed  jz      short loc_14003A243
0x14003a1ef  lea     rcx, aNtdcomposition_21; "NtDCompositionGetDeletedResources"
0x14003a1f6  mov     rdx, 129h
0x14003a1fd  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x14003a204  nop     dword ptr [rax+rax+00h]
0x14003a209  call    cs:__imp_PsIsWin32KFilterEnabled
0x14003a210  nop     dword ptr [rax+rax+00h]
0x14003a215  test    al, al
0x14003a217  jz      short loc_14003A243
0x14003a219  lea     rcx, W32pServiceTableFilter
0x14003a220  mov     edx, cs:W32pServiceLimitFilter
0x14003a226  mov     rax, 129h
0x14003a22d  lea     rcx, [rcx+rdx*4]
0x14003a231  movsx   eax, byte ptr [rcx+rax]
0x14003a235  or      eax, eax
0x14003a237  jle     short loc_14003A23E
0x14003a239  mov     eax, 0C000001Ch
0x14003a23e  add     rsp, 48h
0x14003a242  retn
0x14003a243  mov     rax, cs:__imp_NtDCompositionGetDeletedResources
0x14003a24a  mov     rcx, [rsp+48h+var_28]
0x14003a24f  mov     rdx, [rsp+48h+var_20]
0x14003a254  mov     r8, [rsp+48h+var_18]
0x14003a259  mov     r9, [rsp+48h+var_10]
0x14003a25e  add     rsp, 48h
0x14003a262  jmp     rax
```
