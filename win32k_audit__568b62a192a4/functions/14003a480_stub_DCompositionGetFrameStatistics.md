# _stub_DCompositionGetFrameStatistics

- ea: `0x14003a480`
- end: `0x14003a527`
- name: `_stub_DCompositionGetFrameStatistics`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x14003a480`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x14003a4c9`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x14003a4c9`

## string_xrefs

- `0x14003a4af`: `NtDCompositionGetFrameStatistics`

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
0x14003a480  sub     rsp, 48h
0x14003a484  mov     [rsp+48h+var_28], rcx
0x14003a489  mov     [rsp+48h+var_20], rdx
0x14003a48e  mov     [rsp+48h+var_18], r8
0x14003a493  mov     [rsp+48h+var_10], r9
0x14003a498  mov     rcx, 12Dh
0x14003a49f  call    cs:__imp_IsWin32KSyscallFiltered
0x14003a4a6  nop     dword ptr [rax+rax+00h]
0x14003a4ab  test    al, al
0x14003a4ad  jz      short loc_14003A503
0x14003a4af  lea     rcx, aNtdcomposition_25; "NtDCompositionGetFrameStatistics"
0x14003a4b6  mov     rdx, 12Dh
0x14003a4bd  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x14003a4c4  nop     dword ptr [rax+rax+00h]
0x14003a4c9  call    cs:__imp_PsIsWin32KFilterEnabled
0x14003a4d0  nop     dword ptr [rax+rax+00h]
0x14003a4d5  test    al, al
0x14003a4d7  jz      short loc_14003A503
0x14003a4d9  lea     rcx, W32pServiceTableFilter
0x14003a4e0  mov     edx, cs:W32pServiceLimitFilter
0x14003a4e6  mov     rax, 12Dh
0x14003a4ed  lea     rcx, [rcx+rdx*4]
0x14003a4f1  movsx   eax, byte ptr [rcx+rax]
0x14003a4f5  or      eax, eax
0x14003a4f7  jle     short loc_14003A4FE
0x14003a4f9  mov     eax, 0C000001Ch
0x14003a4fe  add     rsp, 48h
0x14003a502  retn
0x14003a503  mov     rax, cs:__imp_NtDCompositionGetFrameStatistics
0x14003a50a  mov     rcx, [rsp+48h+var_28]
0x14003a50f  mov     rdx, [rsp+48h+var_20]
0x14003a514  mov     r8, [rsp+48h+var_18]
0x14003a519  mov     r9, [rsp+48h+var_10]
0x14003a51e  add     rsp, 48h
0x14003a522  jmp     rax
```
