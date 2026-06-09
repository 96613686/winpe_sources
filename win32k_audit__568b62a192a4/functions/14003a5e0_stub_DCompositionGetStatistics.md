# _stub_DCompositionGetStatistics

- ea: `0x14003a5e0`
- end: `0x14003a687`
- name: `_stub_DCompositionGetStatistics`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x14003a5e0`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x14003a629`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x14003a629`

## string_xrefs

- `0x14003a60f`: `NtDCompositionGetStatistics`

## pseudocode

```c
__int64 __fastcall stub_DCompositionGetStatistics(int a1, int a2, int a3, int a4, __int64 a5)
{
  __int64 result; // rax

  if ( !(unsigned __int8)IsWin32KSyscallFiltered() )
    return NtDCompositionGetStatistics(a1, a2, a3, a4, a5);
  NtUserWin32kSysCallFilterStub();
  if ( !(unsigned __int8)PsIsWin32KFilterEnabled() )
    return NtDCompositionGetStatistics(a1, a2, a3, a4, a5);
  result = (unsigned int)*((char *)&W32pServiceTableFilter[37] + 4 * (unsigned int)W32pServiceLimitFilter + 7);
  if ( (int)result > 0 )
    return 3221225500LL;
  return result;
}

```

## disassembly

```asm
0x14003a5e0  sub     rsp, 48h
0x14003a5e4  mov     [rsp+48h+var_28], rcx
0x14003a5e9  mov     [rsp+48h+var_20], rdx
0x14003a5ee  mov     [rsp+48h+var_18], r8
0x14003a5f3  mov     [rsp+48h+var_10], r9
0x14003a5f8  mov     rcx, 12Fh
0x14003a5ff  call    cs:__imp_IsWin32KSyscallFiltered
0x14003a606  nop     dword ptr [rax+rax+00h]
0x14003a60b  test    al, al
0x14003a60d  jz      short loc_14003A663
0x14003a60f  lea     rcx, aNtdcomposition_27; "NtDCompositionGetStatistics"
0x14003a616  mov     rdx, 12Fh
0x14003a61d  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x14003a624  nop     dword ptr [rax+rax+00h]
0x14003a629  call    cs:__imp_PsIsWin32KFilterEnabled
0x14003a630  nop     dword ptr [rax+rax+00h]
0x14003a635  test    al, al
0x14003a637  jz      short loc_14003A663
0x14003a639  lea     rcx, W32pServiceTableFilter
0x14003a640  mov     edx, cs:W32pServiceLimitFilter
0x14003a646  mov     rax, 12Fh
0x14003a64d  lea     rcx, [rcx+rdx*4]
0x14003a651  movsx   eax, byte ptr [rcx+rax]
0x14003a655  or      eax, eax
0x14003a657  jle     short loc_14003A65E
0x14003a659  mov     eax, 0C000001Ch
0x14003a65e  add     rsp, 48h
0x14003a662  retn
0x14003a663  mov     rax, cs:__imp_NtDCompositionGetStatistics
0x14003a66a  mov     rcx, [rsp+48h+var_28]
0x14003a66f  mov     rdx, [rsp+48h+var_20]
0x14003a674  mov     r8, [rsp+48h+var_18]
0x14003a679  mov     r9, [rsp+48h+var_10]
0x14003a67e  add     rsp, 48h
0x14003a682  jmp     rax
```
