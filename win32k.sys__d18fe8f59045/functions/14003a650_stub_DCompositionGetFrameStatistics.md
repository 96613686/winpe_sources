# _stub_DCompositionGetFrameStatistics

- ea: `0x14003a650`
- end: `0x14003a6f7`
- name: `_stub_DCompositionGetFrameStatistics`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x14003a650`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x14003a699`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x14003a699`

## string_xrefs

- `0x14003a67f`: `NtDCompositionGetFrameStatistics`

## pseudocode

```c
__int64 stub_DCompositionGetFrameStatistics()
{
  __int64 result; // rax

  if ( !(unsigned __int8)IsWin32KSyscallFiltered() )
    return NtDCompositionGetFrameStatistics();
  NtUserWin32kSysCallFilterStub();
  if ( !(unsigned __int8)PsIsWin32KFilterEnabled() )
    return NtDCompositionGetFrameStatistics();
  result = (unsigned int)*((char *)&W32pServiceTableFilter[37] + 4 * (unsigned int)W32pServiceLimitFilter + 5);
  if ( (int)result > 0 )
    return 3221225500LL;
  return result;
}

```

## disassembly

```asm
0x14003a650  sub     rsp, 48h
0x14003a654  mov     [rsp+48h+var_28], rcx
0x14003a659  mov     [rsp+48h+var_20], rdx
0x14003a65e  mov     [rsp+48h+var_18], r8
0x14003a663  mov     [rsp+48h+var_10], r9
0x14003a668  mov     rcx, 12Dh
0x14003a66f  call    cs:__imp_IsWin32KSyscallFiltered
0x14003a676  nop     dword ptr [rax+rax+00h]
0x14003a67b  test    al, al
0x14003a67d  jz      short loc_14003A6D3
0x14003a67f  lea     rcx, aNtdcomposition_25; "NtDCompositionGetFrameStatistics"
0x14003a686  mov     rdx, 12Dh
0x14003a68d  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x14003a694  nop     dword ptr [rax+rax+00h]
0x14003a699  call    cs:__imp_PsIsWin32KFilterEnabled
0x14003a6a0  nop     dword ptr [rax+rax+00h]
0x14003a6a5  test    al, al
0x14003a6a7  jz      short loc_14003A6D3
0x14003a6a9  lea     rcx, W32pServiceTableFilter
0x14003a6b0  mov     edx, cs:W32pServiceLimitFilter
0x14003a6b6  mov     rax, 12Dh
0x14003a6bd  lea     rcx, [rcx+rdx*4]
0x14003a6c1  movsx   eax, byte ptr [rcx+rax]
0x14003a6c5  or      eax, eax
0x14003a6c7  jle     short loc_14003A6CE
0x14003a6c9  mov     eax, 0C000001Ch
0x14003a6ce  add     rsp, 48h
0x14003a6d2  retn
0x14003a6d3  mov     rax, cs:__imp_NtDCompositionGetFrameStatistics
0x14003a6da  mov     rcx, [rsp+48h+var_28]
0x14003a6df  mov     rdx, [rsp+48h+var_20]
0x14003a6e4  mov     r8, [rsp+48h+var_18]
0x14003a6e9  mov     r9, [rsp+48h+var_10]
0x14003a6ee  add     rsp, 48h
0x14003a6f2  jmp     rax
```
