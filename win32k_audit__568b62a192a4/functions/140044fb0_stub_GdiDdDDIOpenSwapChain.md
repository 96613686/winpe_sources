# _stub_GdiDdDDIOpenSwapChain

- ea: `0x140044fb0`
- end: `0x140045057`
- name: `_stub_GdiDdDDIOpenSwapChain`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x140044fb0`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140044ff9`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140044ff9`
- `ext-ms-win-core-win32k-dxgk-l1-1-0!NtGdiDdDDIOpenSwapChain` at `0x140045033`

## string_xrefs

- `0x140044fdf`: `NtGdiDdDDIOpenSwapChain`

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
  result = (unsigned int)*((char *)&W32pServiceTableFilter[68] + 4 * (unsigned int)W32pServiceLimitFilter + 6);
  if ( (int)result > 0 )
    return 3221225500LL;
  return result;
}

```

## disassembly

```asm
0x140044fb0  sub     rsp, 48h
0x140044fb4  mov     [rsp+48h+var_28], rcx
0x140044fb9  mov     [rsp+48h+var_20], rdx
0x140044fbe  mov     [rsp+48h+var_18], r8
0x140044fc3  mov     [rsp+48h+var_10], r9
0x140044fc8  mov     rcx, 226h
0x140044fcf  call    cs:__imp_IsWin32KSyscallFiltered
0x140044fd6  nop     dword ptr [rax+rax+00h]
0x140044fdb  test    al, al
0x140044fdd  jz      short loc_140045033
0x140044fdf  lea     rcx, aNtgdiddddiopen_10; "NtGdiDdDDIOpenSwapChain"
0x140044fe6  mov     rdx, 226h
0x140044fed  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x140044ff4  nop     dword ptr [rax+rax+00h]
0x140044ff9  call    cs:__imp_PsIsWin32KFilterEnabled
0x140045000  nop     dword ptr [rax+rax+00h]
0x140045005  test    al, al
0x140045007  jz      short loc_140045033
0x140045009  lea     rcx, W32pServiceTableFilter
0x140045010  mov     edx, cs:W32pServiceLimitFilter
0x140045016  mov     rax, 226h
0x14004501d  lea     rcx, [rcx+rdx*4]
0x140045021  movsx   eax, byte ptr [rcx+rax]
0x140045025  or      eax, eax
0x140045027  jle     short loc_14004502E
0x140045029  mov     eax, 0C000001Ch
0x14004502e  add     rsp, 48h
0x140045032  retn
0x140045033  mov     rax, cs:__imp_NtGdiDdDDIOpenSwapChain
0x14004503a  mov     rcx, [rsp+48h+var_28]
0x14004503f  mov     rdx, [rsp+48h+var_20]
0x140045044  mov     r8, [rsp+48h+var_18]
0x140045049  mov     r9, [rsp+48h+var_10]
0x14004504e  add     rsp, 48h
0x140045052  jmp     rax
```
