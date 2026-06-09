# _stub_GdiDdDDIUpdateAllocationProperty

- ea: `0x1400481e0`
- end: `0x140048287`
- name: `_stub_GdiDdDDIUpdateAllocationProperty`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, installer_update`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x1400481e0`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140048229`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140048229`
- `ext-ms-win-core-win32k-dxgk-l1-1-0!NtGdiDdDDIUpdateAllocationProperty` at `0x140048263`

## string_xrefs

- `0x14004820f`: `NtGdiDdDDIUpdateAllocationProperty`

## pseudocode

```c
__int64 __fastcall stub_GdiDdDDIUpdateAllocationProperty(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 result; // rax

  if ( !(unsigned __int8)IsWin32KSyscallFiltered() )
    return NtGdiDdDDIUpdateAllocationProperty(a1, a2, a3, a4);
  NtUserWin32kSysCallFilterStub();
  if ( !(unsigned __int8)PsIsWin32KFilterEnabled() )
    return NtGdiDdDDIUpdateAllocationProperty(a1, a2, a3, a4);
  result = (unsigned int)*((char *)&W32pServiceTableFilter[77] + 4 * (unsigned int)W32pServiceLimitFilter + 7);
  if ( (int)result > 0 )
    return 3221225500LL;
  return result;
}

```

## disassembly

```asm
0x1400481e0  sub     rsp, 48h
0x1400481e4  mov     [rsp+48h+var_28], rcx
0x1400481e9  mov     [rsp+48h+var_20], rdx
0x1400481ee  mov     [rsp+48h+var_18], r8
0x1400481f3  mov     [rsp+48h+var_10], r9
0x1400481f8  mov     rcx, 26Fh
0x1400481ff  call    cs:__imp_IsWin32KSyscallFiltered
0x140048206  nop     dword ptr [rax+rax+00h]
0x14004820b  test    al, al
0x14004820d  jz      short loc_140048263
0x14004820f  lea     rcx, aNtgdiddddiupda; "NtGdiDdDDIUpdateAllocationProperty"
0x140048216  mov     rdx, 26Fh
0x14004821d  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x140048224  nop     dword ptr [rax+rax+00h]
0x140048229  call    cs:__imp_PsIsWin32KFilterEnabled
0x140048230  nop     dword ptr [rax+rax+00h]
0x140048235  test    al, al
0x140048237  jz      short loc_140048263
0x140048239  lea     rcx, W32pServiceTableFilter
0x140048240  mov     edx, cs:W32pServiceLimitFilter
0x140048246  mov     rax, 26Fh
0x14004824d  lea     rcx, [rcx+rdx*4]
0x140048251  movsx   eax, byte ptr [rcx+rax]
0x140048255  or      eax, eax
0x140048257  jle     short loc_14004825E
0x140048259  mov     eax, 0C000001Ch
0x14004825e  add     rsp, 48h
0x140048262  retn
0x140048263  mov     rax, cs:__imp_NtGdiDdDDIUpdateAllocationProperty
0x14004826a  mov     rcx, [rsp+48h+var_28]
0x14004826f  mov     rdx, [rsp+48h+var_20]
0x140048274  mov     r8, [rsp+48h+var_18]
0x140048279  mov     r9, [rsp+48h+var_10]
0x14004827e  add     rsp, 48h
0x140048282  jmp     rax
```
