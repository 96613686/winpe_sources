# _stub_GdiDdDDIOpenSyncObjectFromNtHandle

- ea: `0x140045440`
- end: `0x1400454e7`
- name: `_stub_GdiDdDDIOpenSyncObjectFromNtHandle`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x140045440`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140045489`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140045489`
- `ext-ms-win-core-win32k-dxgk-l1-1-0!NtGdiDdDDIOpenSyncObjectFromNtHandle` at `0x1400454c3`

## string_xrefs

- `0x14004546f`: `NtGdiDdDDIOpenSyncObjectFromNtHandle`

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
  result = (unsigned int)*((char *)&W32pServiceTableFilter[69] + 4 * (unsigned int)W32pServiceLimitFilter + 2);
  if ( (int)result > 0 )
    return 3221225500LL;
  return result;
}

```

## disassembly

```asm
0x140045440  sub     rsp, 48h
0x140045444  mov     [rsp+48h+var_28], rcx
0x140045449  mov     [rsp+48h+var_20], rdx
0x14004544e  mov     [rsp+48h+var_18], r8
0x140045453  mov     [rsp+48h+var_10], r9
0x140045458  mov     rcx, 22Ah
0x14004545f  call    cs:__imp_IsWin32KSyscallFiltered
0x140045466  nop     dword ptr [rax+rax+00h]
0x14004546b  test    al, al
0x14004546d  jz      short loc_1400454C3
0x14004546f  lea     rcx, aNtgdiddddiopen_11; "NtGdiDdDDIOpenSyncObjectFromNtHandle"
0x140045476  mov     rdx, 22Ah
0x14004547d  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x140045484  nop     dword ptr [rax+rax+00h]
0x140045489  call    cs:__imp_PsIsWin32KFilterEnabled
0x140045490  nop     dword ptr [rax+rax+00h]
0x140045495  test    al, al
0x140045497  jz      short loc_1400454C3
0x140045499  lea     rcx, W32pServiceTableFilter
0x1400454a0  mov     edx, cs:W32pServiceLimitFilter
0x1400454a6  mov     rax, 22Ah
0x1400454ad  lea     rcx, [rcx+rdx*4]
0x1400454b1  movsx   eax, byte ptr [rcx+rax]
0x1400454b5  or      eax, eax
0x1400454b7  jle     short loc_1400454BE
0x1400454b9  mov     eax, 0C000001Ch
0x1400454be  add     rsp, 48h
0x1400454c2  retn
0x1400454c3  mov     rax, cs:__imp_NtGdiDdDDIOpenSyncObjectFromNtHandle
0x1400454ca  mov     rcx, [rsp+48h+var_28]
0x1400454cf  mov     rdx, [rsp+48h+var_20]
0x1400454d4  mov     r8, [rsp+48h+var_18]
0x1400454d9  mov     r9, [rsp+48h+var_10]
0x1400454de  add     rsp, 48h
0x1400454e2  jmp     rax
```
