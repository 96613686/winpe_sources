# _stub_DCompositionGetFrameIdFromBatchId

- ea: `0x14003a4f0`
- end: `0x14003a597`
- name: `_stub_DCompositionGetFrameIdFromBatchId`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x14003a4f0`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x14003a539`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x14003a539`

## string_xrefs

- `0x14003a51f`: `NtDCompositionGetFrameIdFromBatchId`

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
0x14003a4f0  sub     rsp, 48h
0x14003a4f4  mov     [rsp+48h+var_28], rcx
0x14003a4f9  mov     [rsp+48h+var_20], rdx
0x14003a4fe  mov     [rsp+48h+var_18], r8
0x14003a503  mov     [rsp+48h+var_10], r9
0x14003a508  mov     rcx, 12Bh
0x14003a50f  call    cs:__imp_IsWin32KSyscallFiltered
0x14003a516  nop     dword ptr [rax+rax+00h]
0x14003a51b  test    al, al
0x14003a51d  jz      short loc_14003A573
0x14003a51f  lea     rcx, aNtdcomposition_23; "NtDCompositionGetFrameIdFromBatchId"
0x14003a526  mov     rdx, 12Bh
0x14003a52d  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x14003a534  nop     dword ptr [rax+rax+00h]
0x14003a539  call    cs:__imp_PsIsWin32KFilterEnabled
0x14003a540  nop     dword ptr [rax+rax+00h]
0x14003a545  test    al, al
0x14003a547  jz      short loc_14003A573
0x14003a549  lea     rcx, W32pServiceTableFilter
0x14003a550  mov     edx, cs:W32pServiceLimitFilter
0x14003a556  mov     rax, 12Bh
0x14003a55d  lea     rcx, [rcx+rdx*4]
0x14003a561  movsx   eax, byte ptr [rcx+rax]
0x14003a565  or      eax, eax
0x14003a567  jle     short loc_14003A56E
0x14003a569  mov     eax, 0C000001Ch
0x14003a56e  add     rsp, 48h
0x14003a572  retn
0x14003a573  mov     rax, cs:__imp_NtDCompositionGetFrameIdFromBatchId
0x14003a57a  mov     rcx, [rsp+48h+var_28]
0x14003a57f  mov     rdx, [rsp+48h+var_20]
0x14003a584  mov     r8, [rsp+48h+var_18]
0x14003a589  mov     r9, [rsp+48h+var_10]
0x14003a58e  add     rsp, 48h
0x14003a592  jmp     rax
```
