# _stub_GdiDdDDIOpenSyncObjectFromNtHandle2

- ea: `0x1400454f0`
- end: `0x140045597`
- name: `_stub_GdiDdDDIOpenSyncObjectFromNtHandle2`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x1400454f0`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140045539`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140045539`
- `ext-ms-win-core-win32k-dxgk-l1-1-0!NtGdiDdDDIOpenSyncObjectFromNtHandle2` at `0x140045573`

## string_xrefs

- `0x14004551f`: `NtGdiDdDDIOpenSyncObjectFromNtHandle2`

## pseudocode

```c
__int64 __fastcall stub_GdiDdDDIOpenSyncObjectFromNtHandle2(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 result; // rax

  if ( !(unsigned __int8)IsWin32KSyscallFiltered() )
    return NtGdiDdDDIOpenSyncObjectFromNtHandle2(a1, a2, a3, a4);
  NtUserWin32kSysCallFilterStub();
  if ( !(unsigned __int8)PsIsWin32KFilterEnabled() )
    return NtGdiDdDDIOpenSyncObjectFromNtHandle2(a1, a2, a3, a4);
  result = (unsigned int)*((char *)&W32pServiceTableFilter[69] + 4 * (unsigned int)W32pServiceLimitFilter + 3);
  if ( (int)result > 0 )
    return 3221225500LL;
  return result;
}

```

## disassembly

```asm
0x1400454f0  sub     rsp, 48h
0x1400454f4  mov     [rsp+48h+var_28], rcx
0x1400454f9  mov     [rsp+48h+var_20], rdx
0x1400454fe  mov     [rsp+48h+var_18], r8
0x140045503  mov     [rsp+48h+var_10], r9
0x140045508  mov     rcx, 22Bh
0x14004550f  call    cs:__imp_IsWin32KSyscallFiltered
0x140045516  nop     dword ptr [rax+rax+00h]
0x14004551b  test    al, al
0x14004551d  jz      short loc_140045573
0x14004551f  lea     rcx, aNtgdiddddiopen_12; "NtGdiDdDDIOpenSyncObjectFromNtHandle2"
0x140045526  mov     rdx, 22Bh
0x14004552d  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x140045534  nop     dword ptr [rax+rax+00h]
0x140045539  call    cs:__imp_PsIsWin32KFilterEnabled
0x140045540  nop     dword ptr [rax+rax+00h]
0x140045545  test    al, al
0x140045547  jz      short loc_140045573
0x140045549  lea     rcx, W32pServiceTableFilter
0x140045550  mov     edx, cs:W32pServiceLimitFilter
0x140045556  mov     rax, 22Bh
0x14004555d  lea     rcx, [rcx+rdx*4]
0x140045561  movsx   eax, byte ptr [rcx+rax]
0x140045565  or      eax, eax
0x140045567  jle     short loc_14004556E
0x140045569  mov     eax, 0C000001Ch
0x14004556e  add     rsp, 48h
0x140045572  retn
0x140045573  mov     rax, cs:__imp_NtGdiDdDDIOpenSyncObjectFromNtHandle2
0x14004557a  mov     rcx, [rsp+48h+var_28]
0x14004557f  mov     rdx, [rsp+48h+var_20]
0x140045584  mov     r8, [rsp+48h+var_18]
0x140045589  mov     r9, [rsp+48h+var_10]
0x14004558e  add     rsp, 48h
0x140045592  jmp     rax
```
