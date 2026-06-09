# _stub_DCompositionGetTargetStatistics

- ea: `0x14003a690`
- end: `0x14003a737`
- name: `_stub_DCompositionGetTargetStatistics`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x14003a690`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x14003a6d9`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x14003a6d9`

## string_xrefs

- `0x14003a6bf`: `NtDCompositionGetTargetStatistics`

## pseudocode

```c
__int64 stub_DCompositionGetTargetStatistics()
{
  __int64 result; // rax

  if ( !(unsigned __int8)IsWin32KSyscallFiltered() )
    return NtDCompositionGetTargetStatistics();
  NtUserWin32kSysCallFilterStub();
  if ( !(unsigned __int8)PsIsWin32KFilterEnabled() )
    return NtDCompositionGetTargetStatistics();
  result = (unsigned int)*((char *)&W32pServiceTableFilter[38] + 4 * (unsigned int)W32pServiceLimitFilter);
  if ( (int)result > 0 )
    return 3221225500LL;
  return result;
}

```

## disassembly

```asm
0x14003a690  sub     rsp, 48h
0x14003a694  mov     [rsp+48h+var_28], rcx
0x14003a699  mov     [rsp+48h+var_20], rdx
0x14003a69e  mov     [rsp+48h+var_18], r8
0x14003a6a3  mov     [rsp+48h+var_10], r9
0x14003a6a8  mov     rcx, 130h
0x14003a6af  call    cs:__imp_IsWin32KSyscallFiltered
0x14003a6b6  nop     dword ptr [rax+rax+00h]
0x14003a6bb  test    al, al
0x14003a6bd  jz      short loc_14003A713
0x14003a6bf  lea     rcx, aNtdcomposition_28; "NtDCompositionGetTargetStatistics"
0x14003a6c6  mov     rdx, 130h
0x14003a6cd  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x14003a6d4  nop     dword ptr [rax+rax+00h]
0x14003a6d9  call    cs:__imp_PsIsWin32KFilterEnabled
0x14003a6e0  nop     dword ptr [rax+rax+00h]
0x14003a6e5  test    al, al
0x14003a6e7  jz      short loc_14003A713
0x14003a6e9  lea     rcx, W32pServiceTableFilter
0x14003a6f0  mov     edx, cs:W32pServiceLimitFilter
0x14003a6f6  mov     rax, 130h
0x14003a6fd  lea     rcx, [rcx+rdx*4]
0x14003a701  movsx   eax, byte ptr [rcx+rax]
0x14003a705  or      eax, eax
0x14003a707  jle     short loc_14003A70E
0x14003a709  mov     eax, 0C000001Ch
0x14003a70e  add     rsp, 48h
0x14003a712  retn
0x14003a713  mov     rax, cs:__imp_NtDCompositionGetTargetStatistics
0x14003a71a  mov     rcx, [rsp+48h+var_28]
0x14003a71f  mov     rdx, [rsp+48h+var_20]
0x14003a724  mov     r8, [rsp+48h+var_18]
0x14003a729  mov     r9, [rsp+48h+var_10]
0x14003a72e  add     rsp, 48h
0x14003a732  jmp     rax
```
