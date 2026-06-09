# _stub_GdiDdDDIOpenBundleObjectNtHandleFromName

- ea: `0x140044a30`
- end: `0x140044ad7`
- name: `_stub_GdiDdDDIOpenBundleObjectNtHandleFromName`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x140044a30`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140044a79`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140044a79`
- `ext-ms-win-core-win32k-dxgk-l1-1-0!NtGdiDdDDIOpenBundleObjectNtHandleFromName` at `0x140044ab3`

## string_xrefs

- `0x140044a5f`: `NtGdiDdDDIOpenBundleObjectNtHandleFromName`

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
  result = (unsigned int)*((char *)&W32pServiceTableFilter[67] + 4 * (unsigned int)W32pServiceLimitFilter + 6);
  if ( (int)result > 0 )
    return 3221225500LL;
  return result;
}

```

## disassembly

```asm
0x140044a30  sub     rsp, 48h
0x140044a34  mov     [rsp+48h+var_28], rcx
0x140044a39  mov     [rsp+48h+var_20], rdx
0x140044a3e  mov     [rsp+48h+var_18], r8
0x140044a43  mov     [rsp+48h+var_10], r9
0x140044a48  mov     rcx, 21Eh
0x140044a4f  call    cs:__imp_IsWin32KSyscallFiltered
0x140044a56  nop     dword ptr [rax+rax+00h]
0x140044a5b  test    al, al
0x140044a5d  jz      short loc_140044AB3
0x140044a5f  lea     rcx, aNtgdiddddiopen_2; "NtGdiDdDDIOpenBundleObjectNtHandleFromN"...
0x140044a66  mov     rdx, 21Eh
0x140044a6d  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x140044a74  nop     dword ptr [rax+rax+00h]
0x140044a79  call    cs:__imp_PsIsWin32KFilterEnabled
0x140044a80  nop     dword ptr [rax+rax+00h]
0x140044a85  test    al, al
0x140044a87  jz      short loc_140044AB3
0x140044a89  lea     rcx, W32pServiceTableFilter
0x140044a90  mov     edx, cs:W32pServiceLimitFilter
0x140044a96  mov     rax, 21Eh
0x140044a9d  lea     rcx, [rcx+rdx*4]
0x140044aa1  movsx   eax, byte ptr [rcx+rax]
0x140044aa5  or      eax, eax
0x140044aa7  jle     short loc_140044AAE
0x140044aa9  mov     eax, 0C000001Ch
0x140044aae  add     rsp, 48h
0x140044ab2  retn
0x140044ab3  mov     rax, cs:__imp_NtGdiDdDDIOpenBundleObjectNtHandleFromName
0x140044aba  mov     rcx, [rsp+48h+var_28]
0x140044abf  mov     rdx, [rsp+48h+var_20]
0x140044ac4  mov     r8, [rsp+48h+var_18]
0x140044ac9  mov     r9, [rsp+48h+var_10]
0x140044ace  add     rsp, 48h
0x140044ad2  jmp     rax
```
