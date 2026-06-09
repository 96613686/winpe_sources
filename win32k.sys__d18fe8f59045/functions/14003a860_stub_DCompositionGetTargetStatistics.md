# _stub_DCompositionGetTargetStatistics

- ea: `0x14003a860`
- end: `0x14003a907`
- name: `_stub_DCompositionGetTargetStatistics`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x14003a860`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x14003a8a9`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x14003a8a9`

## string_xrefs

- `0x14003a88f`: `NtDCompositionGetTargetStatistics`

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
0x14003a860  sub     rsp, 48h
0x14003a864  mov     [rsp+48h+var_28], rcx
0x14003a869  mov     [rsp+48h+var_20], rdx
0x14003a86e  mov     [rsp+48h+var_18], r8
0x14003a873  mov     [rsp+48h+var_10], r9
0x14003a878  mov     rcx, 130h
0x14003a87f  call    cs:__imp_IsWin32KSyscallFiltered
0x14003a886  nop     dword ptr [rax+rax+00h]
0x14003a88b  test    al, al
0x14003a88d  jz      short loc_14003A8E3
0x14003a88f  lea     rcx, aNtdcomposition_28; "NtDCompositionGetTargetStatistics"
0x14003a896  mov     rdx, 130h
0x14003a89d  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x14003a8a4  nop     dword ptr [rax+rax+00h]
0x14003a8a9  call    cs:__imp_PsIsWin32KFilterEnabled
0x14003a8b0  nop     dword ptr [rax+rax+00h]
0x14003a8b5  test    al, al
0x14003a8b7  jz      short loc_14003A8E3
0x14003a8b9  lea     rcx, W32pServiceTableFilter
0x14003a8c0  mov     edx, cs:W32pServiceLimitFilter
0x14003a8c6  mov     rax, 130h
0x14003a8cd  lea     rcx, [rcx+rdx*4]
0x14003a8d1  movsx   eax, byte ptr [rcx+rax]
0x14003a8d5  or      eax, eax
0x14003a8d7  jle     short loc_14003A8DE
0x14003a8d9  mov     eax, 0C000001Ch
0x14003a8de  add     rsp, 48h
0x14003a8e2  retn
0x14003a8e3  mov     rax, cs:__imp_NtDCompositionGetTargetStatistics
0x14003a8ea  mov     rcx, [rsp+48h+var_28]
0x14003a8ef  mov     rdx, [rsp+48h+var_20]
0x14003a8f4  mov     r8, [rsp+48h+var_18]
0x14003a8f9  mov     r9, [rsp+48h+var_10]
0x14003a8fe  add     rsp, 48h
0x14003a902  jmp     rax
```
