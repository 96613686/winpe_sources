# _stub_GdiDdDDITrimProcessCommitment

- ea: `0x140048300`
- end: `0x1400483a7`
- name: `_stub_GdiDdDDITrimProcessCommitment`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x140048300`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140048349`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140048349`
- `ext-ms-win-core-win32k-dxgk-l1-1-0!NtGdiDdDDITrimProcessCommitment` at `0x140048383`

## string_xrefs

- `0x14004832f`: `NtGdiDdDDITrimProcessCommitment`

## pseudocode

```c
__int64 __fastcall stub_GdiDdDDITrimProcessCommitment(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 result; // rax

  if ( !(unsigned __int8)IsWin32KSyscallFiltered() )
    return NtGdiDdDDITrimProcessCommitment(a1, a2, a3, a4);
  NtUserWin32kSysCallFilterStub();
  if ( !(unsigned __int8)PsIsWin32KFilterEnabled() )
    return NtGdiDdDDITrimProcessCommitment(a1, a2, a3, a4);
  result = (unsigned int)*((char *)&W32pServiceTableFilter[77] + 4 * (unsigned int)W32pServiceLimitFilter + 6);
  if ( (int)result > 0 )
    return 3221225500LL;
  return result;
}

```

## disassembly

```asm
0x140048300  sub     rsp, 48h
0x140048304  mov     [rsp+48h+var_28], rcx
0x140048309  mov     [rsp+48h+var_20], rdx
0x14004830e  mov     [rsp+48h+var_18], r8
0x140048313  mov     [rsp+48h+var_10], r9
0x140048318  mov     rcx, 26Eh
0x14004831f  call    cs:__imp_IsWin32KSyscallFiltered
0x140048326  nop     dword ptr [rax+rax+00h]
0x14004832b  test    al, al
0x14004832d  jz      short loc_140048383
0x14004832f  lea     rcx, aNtgdidddditrim; "NtGdiDdDDITrimProcessCommitment"
0x140048336  mov     rdx, 26Eh
0x14004833d  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x140048344  nop     dword ptr [rax+rax+00h]
0x140048349  call    cs:__imp_PsIsWin32KFilterEnabled
0x140048350  nop     dword ptr [rax+rax+00h]
0x140048355  test    al, al
0x140048357  jz      short loc_140048383
0x140048359  lea     rcx, W32pServiceTableFilter
0x140048360  mov     edx, cs:W32pServiceLimitFilter
0x140048366  mov     rax, 26Eh
0x14004836d  lea     rcx, [rcx+rdx*4]
0x140048371  movsx   eax, byte ptr [rcx+rax]
0x140048375  or      eax, eax
0x140048377  jle     short loc_14004837E
0x140048379  mov     eax, 0C000001Ch
0x14004837e  add     rsp, 48h
0x140048382  retn
0x140048383  mov     rax, cs:__imp_NtGdiDdDDITrimProcessCommitment
0x14004838a  mov     rcx, [rsp+48h+var_28]
0x14004838f  mov     rdx, [rsp+48h+var_20]
0x140048394  mov     r8, [rsp+48h+var_18]
0x140048399  mov     r9, [rsp+48h+var_10]
0x14004839e  add     rsp, 48h
0x1400483a2  jmp     rax
```
