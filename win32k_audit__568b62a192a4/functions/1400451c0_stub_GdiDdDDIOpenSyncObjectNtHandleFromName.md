# _stub_GdiDdDDIOpenSyncObjectNtHandleFromName

- ea: `0x1400451c0`
- end: `0x140045267`
- name: `_stub_GdiDdDDIOpenSyncObjectNtHandleFromName`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x1400451c0`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140045209`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140045209`
- `ext-ms-win-core-win32k-dxgk-l1-1-0!NtGdiDdDDIOpenSyncObjectNtHandleFromName` at `0x140045243`

## string_xrefs

- `0x1400451ef`: `NtGdiDdDDIOpenSyncObjectNtHandleFromName`

## pseudocode

```c
__int64 __fastcall stub_GdiDdDDIOpenSyncObjectNtHandleFromName(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 result; // rax

  if ( !(unsigned __int8)IsWin32KSyscallFiltered() )
    return NtGdiDdDDIOpenSyncObjectNtHandleFromName(a1, a2, a3, a4);
  NtUserWin32kSysCallFilterStub();
  if ( !(unsigned __int8)PsIsWin32KFilterEnabled() )
    return NtGdiDdDDIOpenSyncObjectNtHandleFromName(a1, a2, a3, a4);
  result = (unsigned int)*((char *)&W32pServiceTableFilter[69] + 4 * (unsigned int)W32pServiceLimitFilter + 1);
  if ( (int)result > 0 )
    return 3221225500LL;
  return result;
}

```

## disassembly

```asm
0x1400451c0  sub     rsp, 48h
0x1400451c4  mov     [rsp+48h+var_28], rcx
0x1400451c9  mov     [rsp+48h+var_20], rdx
0x1400451ce  mov     [rsp+48h+var_18], r8
0x1400451d3  mov     [rsp+48h+var_10], r9
0x1400451d8  mov     rcx, 229h
0x1400451df  call    cs:__imp_IsWin32KSyscallFiltered
0x1400451e6  nop     dword ptr [rax+rax+00h]
0x1400451eb  test    al, al
0x1400451ed  jz      short loc_140045243
0x1400451ef  lea     rcx, aNtgdiddddiopen_13; "NtGdiDdDDIOpenSyncObjectNtHandleFromNam"...
0x1400451f6  mov     rdx, 229h
0x1400451fd  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x140045204  nop     dword ptr [rax+rax+00h]
0x140045209  call    cs:__imp_PsIsWin32KFilterEnabled
0x140045210  nop     dword ptr [rax+rax+00h]
0x140045215  test    al, al
0x140045217  jz      short loc_140045243
0x140045219  lea     rcx, W32pServiceTableFilter
0x140045220  mov     edx, cs:W32pServiceLimitFilter
0x140045226  mov     rax, 229h
0x14004522d  lea     rcx, [rcx+rdx*4]
0x140045231  movsx   eax, byte ptr [rcx+rax]
0x140045235  or      eax, eax
0x140045237  jle     short loc_14004523E
0x140045239  mov     eax, 0C000001Ch
0x14004523e  add     rsp, 48h
0x140045242  retn
0x140045243  mov     rax, cs:__imp_NtGdiDdDDIOpenSyncObjectNtHandleFromName
0x14004524a  mov     rcx, [rsp+48h+var_28]
0x14004524f  mov     rdx, [rsp+48h+var_20]
0x140045254  mov     r8, [rsp+48h+var_18]
0x140045259  mov     r9, [rsp+48h+var_10]
0x14004525e  add     rsp, 48h
0x140045262  jmp     rax
```
