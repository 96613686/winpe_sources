# _stub_GdiDdDDIOpenSyncObjectNtHandleFromName

- ea: `0x1400455a0`
- end: `0x140045647`
- name: `_stub_GdiDdDDIOpenSyncObjectNtHandleFromName`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x1400455a0`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x1400455e9`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x1400455e9`
- `ext-ms-win-core-win32k-dxgk-l1-1-0!NtGdiDdDDIOpenSyncObjectNtHandleFromName` at `0x140045623`

## string_xrefs

- `0x1400455cf`: `NtGdiDdDDIOpenSyncObjectNtHandleFromName`

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
  result = (unsigned int)*((char *)&W32pServiceTableFilter[69] + 4 * (unsigned int)W32pServiceLimitFilter + 4);
  if ( (int)result > 0 )
    return 3221225500LL;
  return result;
}

```

## disassembly

```asm
0x1400455a0  sub     rsp, 48h
0x1400455a4  mov     [rsp+48h+var_28], rcx
0x1400455a9  mov     [rsp+48h+var_20], rdx
0x1400455ae  mov     [rsp+48h+var_18], r8
0x1400455b3  mov     [rsp+48h+var_10], r9
0x1400455b8  mov     rcx, 22Ch
0x1400455bf  call    cs:__imp_IsWin32KSyscallFiltered
0x1400455c6  nop     dword ptr [rax+rax+00h]
0x1400455cb  test    al, al
0x1400455cd  jz      short loc_140045623
0x1400455cf  lea     rcx, aNtgdiddddiopen_13; "NtGdiDdDDIOpenSyncObjectNtHandleFromNam"...
0x1400455d6  mov     rdx, 22Ch
0x1400455dd  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x1400455e4  nop     dword ptr [rax+rax+00h]
0x1400455e9  call    cs:__imp_PsIsWin32KFilterEnabled
0x1400455f0  nop     dword ptr [rax+rax+00h]
0x1400455f5  test    al, al
0x1400455f7  jz      short loc_140045623
0x1400455f9  lea     rcx, W32pServiceTableFilter
0x140045600  mov     edx, cs:W32pServiceLimitFilter
0x140045606  mov     rax, 22Ch
0x14004560d  lea     rcx, [rcx+rdx*4]
0x140045611  movsx   eax, byte ptr [rcx+rax]
0x140045615  or      eax, eax
0x140045617  jle     short loc_14004561E
0x140045619  mov     eax, 0C000001Ch
0x14004561e  add     rsp, 48h
0x140045622  retn
0x140045623  mov     rax, cs:__imp_NtGdiDdDDIOpenSyncObjectNtHandleFromName
0x14004562a  mov     rcx, [rsp+48h+var_28]
0x14004562f  mov     rdx, [rsp+48h+var_20]
0x140045634  mov     r8, [rsp+48h+var_18]
0x140045639  mov     r9, [rsp+48h+var_10]
0x14004563e  add     rsp, 48h
0x140045642  jmp     rax
```
