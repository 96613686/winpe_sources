# _stub_DCompositionGetBatchId

- ea: `0x140039fb0`
- end: `0x14003a057`
- name: `_stub_DCompositionGetBatchId`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x140039fb0`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140039ff9`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140039ff9`

## string_xrefs

- `0x140039fdf`: `NtDCompositionGetBatchId`

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
0x140039fb0  sub     rsp, 48h
0x140039fb4  mov     [rsp+48h+var_28], rcx
0x140039fb9  mov     [rsp+48h+var_20], rdx
0x140039fbe  mov     [rsp+48h+var_18], r8
0x140039fc3  mov     [rsp+48h+var_10], r9
0x140039fc8  mov     rcx, 126h
0x140039fcf  call    cs:__imp_IsWin32KSyscallFiltered
0x140039fd6  nop     dword ptr [rax+rax+00h]
0x140039fdb  test    al, al
0x140039fdd  jz      short loc_14003A033
0x140039fdf  lea     rcx, aNtdcomposition_18; "NtDCompositionGetBatchId"
0x140039fe6  mov     rdx, 126h
0x140039fed  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x140039ff4  nop     dword ptr [rax+rax+00h]
0x140039ff9  call    cs:__imp_PsIsWin32KFilterEnabled
0x14003a000  nop     dword ptr [rax+rax+00h]
0x14003a005  test    al, al
0x14003a007  jz      short loc_14003A033
0x14003a009  lea     rcx, W32pServiceTableFilter
0x14003a010  mov     edx, cs:W32pServiceLimitFilter
0x14003a016  mov     rax, 126h
0x14003a01d  lea     rcx, [rcx+rdx*4]
0x14003a021  movsx   eax, byte ptr [rcx+rax]
0x14003a025  or      eax, eax
0x14003a027  jle     short loc_14003A02E
0x14003a029  mov     eax, 0C000001Ch
0x14003a02e  add     rsp, 48h
0x14003a032  retn
0x14003a033  mov     rax, cs:__imp_NtDCompositionGetBatchId
0x14003a03a  mov     rcx, [rsp+48h+var_28]
0x14003a03f  mov     rdx, [rsp+48h+var_20]
0x14003a044  mov     r8, [rsp+48h+var_18]
0x14003a049  mov     r9, [rsp+48h+var_10]
0x14003a04e  add     rsp, 48h
0x14003a052  jmp     rax
```
