# _stub_DCompositionGetDeletedResources

- ea: `0x14003a390`
- end: `0x14003a437`
- name: `_stub_DCompositionGetDeletedResources`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x14003a390`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x14003a3d9`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x14003a3d9`

## string_xrefs

- `0x14003a3bf`: `NtDCompositionGetDeletedResources`

## pseudocode

```c
__int64 stub_DCompositionGetDeletedResources()
{
  __int64 result; // rax

  if ( !(unsigned __int8)IsWin32KSyscallFiltered() )
    return NtDCompositionGetDeletedResources();
  NtUserWin32kSysCallFilterStub();
  if ( !(unsigned __int8)PsIsWin32KFilterEnabled() )
    return NtDCompositionGetDeletedResources();
  result = (unsigned int)*((char *)&W32pServiceTableFilter[37] + 4 * (unsigned int)W32pServiceLimitFilter + 1);
  if ( (int)result > 0 )
    return 3221225500LL;
  return result;
}

```

## disassembly

```asm
0x14003a390  sub     rsp, 48h
0x14003a394  mov     [rsp+48h+var_28], rcx
0x14003a399  mov     [rsp+48h+var_20], rdx
0x14003a39e  mov     [rsp+48h+var_18], r8
0x14003a3a3  mov     [rsp+48h+var_10], r9
0x14003a3a8  mov     rcx, 129h
0x14003a3af  call    cs:__imp_IsWin32KSyscallFiltered
0x14003a3b6  nop     dword ptr [rax+rax+00h]
0x14003a3bb  test    al, al
0x14003a3bd  jz      short loc_14003A413
0x14003a3bf  lea     rcx, aNtdcomposition_21; "NtDCompositionGetDeletedResources"
0x14003a3c6  mov     rdx, 129h
0x14003a3cd  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x14003a3d4  nop     dword ptr [rax+rax+00h]
0x14003a3d9  call    cs:__imp_PsIsWin32KFilterEnabled
0x14003a3e0  nop     dword ptr [rax+rax+00h]
0x14003a3e5  test    al, al
0x14003a3e7  jz      short loc_14003A413
0x14003a3e9  lea     rcx, W32pServiceTableFilter
0x14003a3f0  mov     edx, cs:W32pServiceLimitFilter
0x14003a3f6  mov     rax, 129h
0x14003a3fd  lea     rcx, [rcx+rdx*4]
0x14003a401  movsx   eax, byte ptr [rcx+rax]
0x14003a405  or      eax, eax
0x14003a407  jle     short loc_14003A40E
0x14003a409  mov     eax, 0C000001Ch
0x14003a40e  add     rsp, 48h
0x14003a412  retn
0x14003a413  mov     rax, cs:__imp_NtDCompositionGetDeletedResources
0x14003a41a  mov     rcx, [rsp+48h+var_28]
0x14003a41f  mov     rdx, [rsp+48h+var_20]
0x14003a424  mov     r8, [rsp+48h+var_18]
0x14003a429  mov     r9, [rsp+48h+var_10]
0x14003a42e  add     rsp, 48h
0x14003a432  jmp     rax
```
