# _stub_DCompositionProcessChannelBatchBuffer

- ea: `0x14003a8a0`
- end: `0x14003a947`
- name: `_stub_DCompositionProcessChannelBatchBuffer`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x14003a8a0`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x14003a8e9`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x14003a8e9`

## string_xrefs

- `0x14003a8cf`: `NtDCompositionProcessChannelBatchBuffer`

## pseudocode

```c
__int64 __fastcall stub_DCompositionProcessChannelBatchBuffer(unsigned int a1, unsigned int a2, __int64 a3, __int64 a4)
{
  __int64 result; // rax

  if ( !(unsigned __int8)IsWin32KSyscallFiltered() )
    return NtDCompositionProcessChannelBatchBuffer(a1, a2, a3, a4);
  NtUserWin32kSysCallFilterStub();
  if ( !(unsigned __int8)PsIsWin32KFilterEnabled() )
    return NtDCompositionProcessChannelBatchBuffer(a1, a2, a3, a4);
  result = (unsigned int)*((char *)&W32pServiceTableFilter[38] + 4 * (unsigned int)W32pServiceLimitFilter + 3);
  if ( (int)result > 0 )
    return 3221225500LL;
  return result;
}

```

## disassembly

```asm
0x14003a8a0  sub     rsp, 48h
0x14003a8a4  mov     [rsp+48h+var_28], rcx
0x14003a8a9  mov     [rsp+48h+var_20], rdx
0x14003a8ae  mov     [rsp+48h+var_18], r8
0x14003a8b3  mov     [rsp+48h+var_10], r9
0x14003a8b8  mov     rcx, 133h
0x14003a8bf  call    cs:__imp_IsWin32KSyscallFiltered
0x14003a8c6  nop     dword ptr [rax+rax+00h]
0x14003a8cb  test    al, al
0x14003a8cd  jz      short loc_14003A923
0x14003a8cf  lea     rcx, aNtdcomposition_31; "NtDCompositionProcessChannelBatchBuffer"
0x14003a8d6  mov     rdx, 133h
0x14003a8dd  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x14003a8e4  nop     dword ptr [rax+rax+00h]
0x14003a8e9  call    cs:__imp_PsIsWin32KFilterEnabled
0x14003a8f0  nop     dword ptr [rax+rax+00h]
0x14003a8f5  test    al, al
0x14003a8f7  jz      short loc_14003A923
0x14003a8f9  lea     rcx, W32pServiceTableFilter
0x14003a900  mov     edx, cs:W32pServiceLimitFilter
0x14003a906  mov     rax, 133h
0x14003a90d  lea     rcx, [rcx+rdx*4]
0x14003a911  movsx   eax, byte ptr [rcx+rax]
0x14003a915  or      eax, eax
0x14003a917  jle     short loc_14003A91E
0x14003a919  mov     eax, 0C000001Ch
0x14003a91e  add     rsp, 48h
0x14003a922  retn
0x14003a923  mov     rax, cs:__imp_NtDCompositionProcessChannelBatchBuffer
0x14003a92a  mov     rcx, [rsp+48h+var_28]
0x14003a92f  mov     rdx, [rsp+48h+var_20]
0x14003a934  mov     r8, [rsp+48h+var_18]
0x14003a939  mov     r9, [rsp+48h+var_10]
0x14003a93e  add     rsp, 48h
0x14003a942  jmp     rax
```
