# _stub_GdiDdDDIOpenSyncObjectFromNtHandle

- ea: `0x140045060`
- end: `0x140045107`
- name: `_stub_GdiDdDDIOpenSyncObjectFromNtHandle`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x140045060`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x1400450a9`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x1400450a9`
- `ext-ms-win-core-win32k-dxgk-l1-1-0!NtGdiDdDDIOpenSyncObjectFromNtHandle` at `0x1400450e3`

## string_xrefs

- `0x14004508f`: `NtGdiDdDDIOpenSyncObjectFromNtHandle`

## pseudocode

```c
__int64 __fastcall stub_GdiDdDDIOpenSyncObjectFromNtHandle(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 result; // rax

  if ( !(unsigned __int8)IsWin32KSyscallFiltered() )
    return NtGdiDdDDIOpenSyncObjectFromNtHandle(a1, a2, a3, a4);
  NtUserWin32kSysCallFilterStub();
  if ( !(unsigned __int8)PsIsWin32KFilterEnabled() )
    return NtGdiDdDDIOpenSyncObjectFromNtHandle(a1, a2, a3, a4);
  result = (unsigned int)*((char *)&W32pServiceTableFilter[68] + 4 * (unsigned int)W32pServiceLimitFilter + 7);
  if ( (int)result > 0 )
    return 3221225500LL;
  return result;
}

```

## disassembly

```asm
0x140045060  sub     rsp, 48h
0x140045064  mov     [rsp+48h+var_28], rcx
0x140045069  mov     [rsp+48h+var_20], rdx
0x14004506e  mov     [rsp+48h+var_18], r8
0x140045073  mov     [rsp+48h+var_10], r9
0x140045078  mov     rcx, 227h
0x14004507f  call    cs:__imp_IsWin32KSyscallFiltered
0x140045086  nop     dword ptr [rax+rax+00h]
0x14004508b  test    al, al
0x14004508d  jz      short loc_1400450E3
0x14004508f  lea     rcx, aNtgdiddddiopen_11; "NtGdiDdDDIOpenSyncObjectFromNtHandle"
0x140045096  mov     rdx, 227h
0x14004509d  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x1400450a4  nop     dword ptr [rax+rax+00h]
0x1400450a9  call    cs:__imp_PsIsWin32KFilterEnabled
0x1400450b0  nop     dword ptr [rax+rax+00h]
0x1400450b5  test    al, al
0x1400450b7  jz      short loc_1400450E3
0x1400450b9  lea     rcx, W32pServiceTableFilter
0x1400450c0  mov     edx, cs:W32pServiceLimitFilter
0x1400450c6  mov     rax, 227h
0x1400450cd  lea     rcx, [rcx+rdx*4]
0x1400450d1  movsx   eax, byte ptr [rcx+rax]
0x1400450d5  or      eax, eax
0x1400450d7  jle     short loc_1400450DE
0x1400450d9  mov     eax, 0C000001Ch
0x1400450de  add     rsp, 48h
0x1400450e2  retn
0x1400450e3  mov     rax, cs:__imp_NtGdiDdDDIOpenSyncObjectFromNtHandle
0x1400450ea  mov     rcx, [rsp+48h+var_28]
0x1400450ef  mov     rdx, [rsp+48h+var_20]
0x1400450f4  mov     r8, [rsp+48h+var_18]
0x1400450f9  mov     r9, [rsp+48h+var_10]
0x1400450fe  add     rsp, 48h
0x140045102  jmp     rax
```
