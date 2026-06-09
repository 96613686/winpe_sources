# _stub_GdiDdDDIOpenSyncObjectFromNtHandle2

- ea: `0x140045110`
- end: `0x1400451b7`
- name: `_stub_GdiDdDDIOpenSyncObjectFromNtHandle2`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x140045110`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140045159`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140045159`
- `ext-ms-win-core-win32k-dxgk-l1-1-0!NtGdiDdDDIOpenSyncObjectFromNtHandle2` at `0x140045193`

## string_xrefs

- `0x14004513f`: `NtGdiDdDDIOpenSyncObjectFromNtHandle2`

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
  result = (unsigned int)*((char *)&W32pServiceTableFilter[69] + 4 * (unsigned int)W32pServiceLimitFilter);
  if ( (int)result > 0 )
    return 3221225500LL;
  return result;
}

```

## disassembly

```asm
0x140045110  sub     rsp, 48h
0x140045114  mov     [rsp+48h+var_28], rcx
0x140045119  mov     [rsp+48h+var_20], rdx
0x14004511e  mov     [rsp+48h+var_18], r8
0x140045123  mov     [rsp+48h+var_10], r9
0x140045128  mov     rcx, 228h
0x14004512f  call    cs:__imp_IsWin32KSyscallFiltered
0x140045136  nop     dword ptr [rax+rax+00h]
0x14004513b  test    al, al
0x14004513d  jz      short loc_140045193
0x14004513f  lea     rcx, aNtgdiddddiopen_12; "NtGdiDdDDIOpenSyncObjectFromNtHandle2"
0x140045146  mov     rdx, 228h
0x14004514d  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x140045154  nop     dword ptr [rax+rax+00h]
0x140045159  call    cs:__imp_PsIsWin32KFilterEnabled
0x140045160  nop     dword ptr [rax+rax+00h]
0x140045165  test    al, al
0x140045167  jz      short loc_140045193
0x140045169  lea     rcx, W32pServiceTableFilter
0x140045170  mov     edx, cs:W32pServiceLimitFilter
0x140045176  mov     rax, 228h
0x14004517d  lea     rcx, [rcx+rdx*4]
0x140045181  movsx   eax, byte ptr [rcx+rax]
0x140045185  or      eax, eax
0x140045187  jle     short loc_14004518E
0x140045189  mov     eax, 0C000001Ch
0x14004518e  add     rsp, 48h
0x140045192  retn
0x140045193  mov     rax, cs:__imp_NtGdiDdDDIOpenSyncObjectFromNtHandle2
0x14004519a  mov     rcx, [rsp+48h+var_28]
0x14004519f  mov     rdx, [rsp+48h+var_20]
0x1400451a4  mov     r8, [rsp+48h+var_18]
0x1400451a9  mov     r9, [rsp+48h+var_10]
0x1400451ae  add     rsp, 48h
0x1400451b2  jmp     rax
```
