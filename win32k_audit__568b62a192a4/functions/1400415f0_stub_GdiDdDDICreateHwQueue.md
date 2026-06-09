# _stub_GdiDdDDICreateHwQueue

- ea: `0x1400415f0`
- end: `0x140041697`
- name: `_stub_GdiDdDDICreateHwQueue`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x1400415f0`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140041639`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140041639`
- `ext-ms-win-core-win32k-dxgk-l1-1-0!NtGdiDdDDICreateHwQueue` at `0x140041673`

## string_xrefs

- `0x14004161f`: `NtGdiDdDDICreateHwQueue`

## pseudocode

```c
__int64 __fastcall stub_GdiDdDDICreateHwQueue(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 result; // rax

  if ( !(unsigned __int8)IsWin32KSyscallFiltered() )
    return NtGdiDdDDICreateHwQueue(a1, a2, a3, a4);
  NtUserWin32kSysCallFilterStub();
  if ( !(unsigned __int8)PsIsWin32KFilterEnabled() )
    return NtGdiDdDDICreateHwQueue(a1, a2, a3, a4);
  result = (unsigned int)*((char *)&W32pServiceTableFilter[58] + 4 * (unsigned int)W32pServiceLimitFilter + 2);
  if ( (int)result > 0 )
    return 3221225500LL;
  return result;
}

```

## disassembly

```asm
0x1400415f0  sub     rsp, 48h
0x1400415f4  mov     [rsp+48h+var_28], rcx
0x1400415f9  mov     [rsp+48h+var_20], rdx
0x1400415fe  mov     [rsp+48h+var_18], r8
0x140041603  mov     [rsp+48h+var_10], r9
0x140041608  mov     rcx, 1D2h
0x14004160f  call    cs:__imp_IsWin32KSyscallFiltered
0x140041616  nop     dword ptr [rax+rax+00h]
0x14004161b  test    al, al
0x14004161d  jz      short loc_140041673
0x14004161f  lea     rcx, aNtgdiddddicrea_6; "NtGdiDdDDICreateHwQueue"
0x140041626  mov     rdx, 1D2h
0x14004162d  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x140041634  nop     dword ptr [rax+rax+00h]
0x140041639  call    cs:__imp_PsIsWin32KFilterEnabled
0x140041640  nop     dword ptr [rax+rax+00h]
0x140041645  test    al, al
0x140041647  jz      short loc_140041673
0x140041649  lea     rcx, W32pServiceTableFilter
0x140041650  mov     edx, cs:W32pServiceLimitFilter
0x140041656  mov     rax, 1D2h
0x14004165d  lea     rcx, [rcx+rdx*4]
0x140041661  movsx   eax, byte ptr [rcx+rax]
0x140041665  or      eax, eax
0x140041667  jle     short loc_14004166E
0x140041669  mov     eax, 0C000001Ch
0x14004166e  add     rsp, 48h
0x140041672  retn
0x140041673  mov     rax, cs:__imp_NtGdiDdDDICreateHwQueue
0x14004167a  mov     rcx, [rsp+48h+var_28]
0x14004167f  mov     rdx, [rsp+48h+var_20]
0x140041684  mov     r8, [rsp+48h+var_18]
0x140041689  mov     r9, [rsp+48h+var_10]
0x14004168e  add     rsp, 48h
0x140041692  jmp     rax
```
