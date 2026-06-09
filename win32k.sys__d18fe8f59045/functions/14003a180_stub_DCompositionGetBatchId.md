# _stub_DCompositionGetBatchId

- ea: `0x14003a180`
- end: `0x14003a227`
- name: `_stub_DCompositionGetBatchId`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x14003a180`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x14003a1c9`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x14003a1c9`

## string_xrefs

- `0x14003a1af`: `NtDCompositionGetBatchId`

## pseudocode

```c
__int64 stub_DCompositionGetBatchId()
{
  __int64 result; // rax

  if ( !(unsigned __int8)IsWin32KSyscallFiltered() )
    return NtDCompositionGetBatchId();
  NtUserWin32kSysCallFilterStub();
  if ( !(unsigned __int8)PsIsWin32KFilterEnabled() )
    return NtDCompositionGetBatchId();
  result = (unsigned int)*((char *)&W32pServiceTableFilter[36] + 4 * (unsigned int)W32pServiceLimitFilter + 6);
  if ( (int)result > 0 )
    return 3221225500LL;
  return result;
}

```

## disassembly

```asm
0x14003a180  sub     rsp, 48h
0x14003a184  mov     [rsp+48h+var_28], rcx
0x14003a189  mov     [rsp+48h+var_20], rdx
0x14003a18e  mov     [rsp+48h+var_18], r8
0x14003a193  mov     [rsp+48h+var_10], r9
0x14003a198  mov     rcx, 126h
0x14003a19f  call    cs:__imp_IsWin32KSyscallFiltered
0x14003a1a6  nop     dword ptr [rax+rax+00h]
0x14003a1ab  test    al, al
0x14003a1ad  jz      short loc_14003A203
0x14003a1af  lea     rcx, aNtdcomposition_18; "NtDCompositionGetBatchId"
0x14003a1b6  mov     rdx, 126h
0x14003a1bd  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x14003a1c4  nop     dword ptr [rax+rax+00h]
0x14003a1c9  call    cs:__imp_PsIsWin32KFilterEnabled
0x14003a1d0  nop     dword ptr [rax+rax+00h]
0x14003a1d5  test    al, al
0x14003a1d7  jz      short loc_14003A203
0x14003a1d9  lea     rcx, W32pServiceTableFilter
0x14003a1e0  mov     edx, cs:W32pServiceLimitFilter
0x14003a1e6  mov     rax, 126h
0x14003a1ed  lea     rcx, [rcx+rdx*4]
0x14003a1f1  movsx   eax, byte ptr [rcx+rax]
0x14003a1f5  or      eax, eax
0x14003a1f7  jle     short loc_14003A1FE
0x14003a1f9  mov     eax, 0C000001Ch
0x14003a1fe  add     rsp, 48h
0x14003a202  retn
0x14003a203  mov     rax, cs:__imp_NtDCompositionGetBatchId
0x14003a20a  mov     rcx, [rsp+48h+var_28]
0x14003a20f  mov     rdx, [rsp+48h+var_20]
0x14003a214  mov     r8, [rsp+48h+var_18]
0x14003a219  mov     r9, [rsp+48h+var_10]
0x14003a21e  add     rsp, 48h
0x14003a222  jmp     rax
```
