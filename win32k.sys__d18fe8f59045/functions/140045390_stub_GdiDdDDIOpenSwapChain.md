# _stub_GdiDdDDIOpenSwapChain

- ea: `0x140045390`
- end: `0x140045437`
- name: `_stub_GdiDdDDIOpenSwapChain`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x140045390`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x1400453d9`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x1400453d9`
- `ext-ms-win-core-win32k-dxgk-l1-1-0!NtGdiDdDDIOpenSwapChain` at `0x140045413`

## string_xrefs

- `0x1400453bf`: `NtGdiDdDDIOpenSwapChain`

## pseudocode

```c
__int64 __fastcall stub_GdiDdDDIOpenSwapChain(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 result; // rax

  if ( !(unsigned __int8)IsWin32KSyscallFiltered() )
    return NtGdiDdDDIOpenSwapChain(a1, a2, a3, a4);
  NtUserWin32kSysCallFilterStub();
  if ( !(unsigned __int8)PsIsWin32KFilterEnabled() )
    return NtGdiDdDDIOpenSwapChain(a1, a2, a3, a4);
  result = (unsigned int)*((char *)&W32pServiceTableFilter[69] + 4 * (unsigned int)W32pServiceLimitFilter + 1);
  if ( (int)result > 0 )
    return 3221225500LL;
  return result;
}

```

## disassembly

```asm
0x140045390  sub     rsp, 48h
0x140045394  mov     [rsp+48h+var_28], rcx
0x140045399  mov     [rsp+48h+var_20], rdx
0x14004539e  mov     [rsp+48h+var_18], r8
0x1400453a3  mov     [rsp+48h+var_10], r9
0x1400453a8  mov     rcx, 229h
0x1400453af  call    cs:__imp_IsWin32KSyscallFiltered
0x1400453b6  nop     dword ptr [rax+rax+00h]
0x1400453bb  test    al, al
0x1400453bd  jz      short loc_140045413
0x1400453bf  lea     rcx, aNtgdiddddiopen_10; "NtGdiDdDDIOpenSwapChain"
0x1400453c6  mov     rdx, 229h
0x1400453cd  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x1400453d4  nop     dword ptr [rax+rax+00h]
0x1400453d9  call    cs:__imp_PsIsWin32KFilterEnabled
0x1400453e0  nop     dword ptr [rax+rax+00h]
0x1400453e5  test    al, al
0x1400453e7  jz      short loc_140045413
0x1400453e9  lea     rcx, W32pServiceTableFilter
0x1400453f0  mov     edx, cs:W32pServiceLimitFilter
0x1400453f6  mov     rax, 229h
0x1400453fd  lea     rcx, [rcx+rdx*4]
0x140045401  movsx   eax, byte ptr [rcx+rax]
0x140045405  or      eax, eax
0x140045407  jle     short loc_14004540E
0x140045409  mov     eax, 0C000001Ch
0x14004540e  add     rsp, 48h
0x140045412  retn
0x140045413  mov     rax, cs:__imp_NtGdiDdDDIOpenSwapChain
0x14004541a  mov     rcx, [rsp+48h+var_28]
0x14004541f  mov     rdx, [rsp+48h+var_20]
0x140045424  mov     r8, [rsp+48h+var_18]
0x140045429  mov     r9, [rsp+48h+var_10]
0x14004542e  add     rsp, 48h
0x140045432  jmp     rax
```
