# _stub_DCompositionGetFrameIdFromBatchId

- ea: `0x14003a320`
- end: `0x14003a3c7`
- name: `_stub_DCompositionGetFrameIdFromBatchId`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x14003a320`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x14003a369`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x14003a369`

## string_xrefs

- `0x14003a34f`: `NtDCompositionGetFrameIdFromBatchId`

## pseudocode

```c
__int64 stub_DCompositionGetFrameIdFromBatchId()
{
  __int64 result; // rax

  if ( !(unsigned __int8)IsWin32KSyscallFiltered() )
    return NtDCompositionGetFrameIdFromBatchId();
  NtUserWin32kSysCallFilterStub();
  if ( !(unsigned __int8)PsIsWin32KFilterEnabled() )
    return NtDCompositionGetFrameIdFromBatchId();
  result = (unsigned int)*((char *)&W32pServiceTableFilter[37] + 4 * (unsigned int)W32pServiceLimitFilter + 3);
  if ( (int)result > 0 )
    return 3221225500LL;
  return result;
}

```

## disassembly

```asm
0x14003a320  sub     rsp, 48h
0x14003a324  mov     [rsp+48h+var_28], rcx
0x14003a329  mov     [rsp+48h+var_20], rdx
0x14003a32e  mov     [rsp+48h+var_18], r8
0x14003a333  mov     [rsp+48h+var_10], r9
0x14003a338  mov     rcx, 12Bh
0x14003a33f  call    cs:__imp_IsWin32KSyscallFiltered
0x14003a346  nop     dword ptr [rax+rax+00h]
0x14003a34b  test    al, al
0x14003a34d  jz      short loc_14003A3A3
0x14003a34f  lea     rcx, aNtdcomposition_23; "NtDCompositionGetFrameIdFromBatchId"
0x14003a356  mov     rdx, 12Bh
0x14003a35d  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x14003a364  nop     dword ptr [rax+rax+00h]
0x14003a369  call    cs:__imp_PsIsWin32KFilterEnabled
0x14003a370  nop     dword ptr [rax+rax+00h]
0x14003a375  test    al, al
0x14003a377  jz      short loc_14003A3A3
0x14003a379  lea     rcx, W32pServiceTableFilter
0x14003a380  mov     edx, cs:W32pServiceLimitFilter
0x14003a386  mov     rax, 12Bh
0x14003a38d  lea     rcx, [rcx+rdx*4]
0x14003a391  movsx   eax, byte ptr [rcx+rax]
0x14003a395  or      eax, eax
0x14003a397  jle     short loc_14003A39E
0x14003a399  mov     eax, 0C000001Ch
0x14003a39e  add     rsp, 48h
0x14003a3a2  retn
0x14003a3a3  mov     rax, cs:__imp_NtDCompositionGetFrameIdFromBatchId
0x14003a3aa  mov     rcx, [rsp+48h+var_28]
0x14003a3af  mov     rdx, [rsp+48h+var_20]
0x14003a3b4  mov     r8, [rsp+48h+var_18]
0x14003a3b9  mov     r9, [rsp+48h+var_10]
0x14003a3be  add     rsp, 48h
0x14003a3c2  jmp     rax
```
