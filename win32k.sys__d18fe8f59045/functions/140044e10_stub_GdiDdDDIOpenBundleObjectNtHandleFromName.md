# _stub_GdiDdDDIOpenBundleObjectNtHandleFromName

- ea: `0x140044e10`
- end: `0x140044eb7`
- name: `_stub_GdiDdDDIOpenBundleObjectNtHandleFromName`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x140044e10`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140044e59`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140044e59`
- `ext-ms-win-core-win32k-dxgk-l1-1-0!NtGdiDdDDIOpenBundleObjectNtHandleFromName` at `0x140044e93`

## string_xrefs

- `0x140044e3f`: `NtGdiDdDDIOpenBundleObjectNtHandleFromName`

## pseudocode

```c
__int64 __fastcall stub_GdiDdDDIOpenBundleObjectNtHandleFromName(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 result; // rax

  if ( !(unsigned __int8)IsWin32KSyscallFiltered() )
    return NtGdiDdDDIOpenBundleObjectNtHandleFromName(a1, a2, a3, a4);
  NtUserWin32kSysCallFilterStub();
  if ( !(unsigned __int8)PsIsWin32KFilterEnabled() )
    return NtGdiDdDDIOpenBundleObjectNtHandleFromName(a1, a2, a3, a4);
  result = (unsigned int)*((char *)&W32pServiceTableFilter[68] + 4 * (unsigned int)W32pServiceLimitFilter + 1);
  if ( (int)result > 0 )
    return 3221225500LL;
  return result;
}

```

## disassembly

```asm
0x140044e10  sub     rsp, 48h
0x140044e14  mov     [rsp+48h+var_28], rcx
0x140044e19  mov     [rsp+48h+var_20], rdx
0x140044e1e  mov     [rsp+48h+var_18], r8
0x140044e23  mov     [rsp+48h+var_10], r9
0x140044e28  mov     rcx, 221h
0x140044e2f  call    cs:__imp_IsWin32KSyscallFiltered
0x140044e36  nop     dword ptr [rax+rax+00h]
0x140044e3b  test    al, al
0x140044e3d  jz      short loc_140044E93
0x140044e3f  lea     rcx, aNtgdiddddiopen_2; "NtGdiDdDDIOpenBundleObjectNtHandleFromN"...
0x140044e46  mov     rdx, 221h
0x140044e4d  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x140044e54  nop     dword ptr [rax+rax+00h]
0x140044e59  call    cs:__imp_PsIsWin32KFilterEnabled
0x140044e60  nop     dword ptr [rax+rax+00h]
0x140044e65  test    al, al
0x140044e67  jz      short loc_140044E93
0x140044e69  lea     rcx, W32pServiceTableFilter
0x140044e70  mov     edx, cs:W32pServiceLimitFilter
0x140044e76  mov     rax, 221h
0x140044e7d  lea     rcx, [rcx+rdx*4]
0x140044e81  movsx   eax, byte ptr [rcx+rax]
0x140044e85  or      eax, eax
0x140044e87  jle     short loc_140044E8E
0x140044e89  mov     eax, 0C000001Ch
0x140044e8e  add     rsp, 48h
0x140044e92  retn
0x140044e93  mov     rax, cs:__imp_NtGdiDdDDIOpenBundleObjectNtHandleFromName
0x140044e9a  mov     rcx, [rsp+48h+var_28]
0x140044e9f  mov     rdx, [rsp+48h+var_20]
0x140044ea4  mov     r8, [rsp+48h+var_18]
0x140044ea9  mov     r9, [rsp+48h+var_10]
0x140044eae  add     rsp, 48h
0x140044eb2  jmp     rax
```
