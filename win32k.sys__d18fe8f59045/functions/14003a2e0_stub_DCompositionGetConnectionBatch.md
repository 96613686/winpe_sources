# _stub_DCompositionGetConnectionBatch

- ea: `0x14003a2e0`
- end: `0x14003a387`
- name: `_stub_DCompositionGetConnectionBatch`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x14003a2e0`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x14003a329`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x14003a329`

## string_xrefs

- `0x14003a30f`: `NtDCompositionGetConnectionBatch`

## pseudocode

```c
__int64 stub_DCompositionGetConnectionBatch()
{
  __int64 result; // rax

  if ( !(unsigned __int8)IsWin32KSyscallFiltered() )
    return NtDCompositionGetConnectionBatch();
  NtUserWin32kSysCallFilterStub();
  if ( !(unsigned __int8)PsIsWin32KFilterEnabled() )
    return NtDCompositionGetConnectionBatch();
  result = (unsigned int)*((char *)&W32pServiceTableFilter[37] + 4 * (unsigned int)W32pServiceLimitFilter);
  if ( (int)result > 0 )
    return 3221225500LL;
  return result;
}

```

## disassembly

```asm
0x14003a2e0  sub     rsp, 48h
0x14003a2e4  mov     [rsp+48h+var_28], rcx
0x14003a2e9  mov     [rsp+48h+var_20], rdx
0x14003a2ee  mov     [rsp+48h+var_18], r8
0x14003a2f3  mov     [rsp+48h+var_10], r9
0x14003a2f8  mov     rcx, 128h
0x14003a2ff  call    cs:__imp_IsWin32KSyscallFiltered
0x14003a306  nop     dword ptr [rax+rax+00h]
0x14003a30b  test    al, al
0x14003a30d  jz      short loc_14003A363
0x14003a30f  lea     rcx, aNtdcomposition_20; "NtDCompositionGetConnectionBatch"
0x14003a316  mov     rdx, 128h
0x14003a31d  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x14003a324  nop     dword ptr [rax+rax+00h]
0x14003a329  call    cs:__imp_PsIsWin32KFilterEnabled
0x14003a330  nop     dword ptr [rax+rax+00h]
0x14003a335  test    al, al
0x14003a337  jz      short loc_14003A363
0x14003a339  lea     rcx, W32pServiceTableFilter
0x14003a340  mov     edx, cs:W32pServiceLimitFilter
0x14003a346  mov     rax, 128h
0x14003a34d  lea     rcx, [rcx+rdx*4]
0x14003a351  movsx   eax, byte ptr [rcx+rax]
0x14003a355  or      eax, eax
0x14003a357  jle     short loc_14003A35E
0x14003a359  mov     eax, 0C000001Ch
0x14003a35e  add     rsp, 48h
0x14003a362  retn
0x14003a363  mov     rax, cs:__imp_NtDCompositionGetConnectionBatch
0x14003a36a  mov     rcx, [rsp+48h+var_28]
0x14003a36f  mov     rdx, [rsp+48h+var_20]
0x14003a374  mov     r8, [rsp+48h+var_18]
0x14003a379  mov     r9, [rsp+48h+var_10]
0x14003a37e  add     rsp, 48h
0x14003a382  jmp     rax
```
