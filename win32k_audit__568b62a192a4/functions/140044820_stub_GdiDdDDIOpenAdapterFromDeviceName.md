# _stub_GdiDdDDIOpenAdapterFromDeviceName

- ea: `0x140044820`
- end: `0x1400448c7`
- name: `_stub_GdiDdDDIOpenAdapterFromDeviceName`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x140044820`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140044869`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140044869`
- `ext-ms-win-core-win32k-dxgk-l1-1-0!NtGdiDdDDIOpenAdapterFromDeviceName` at `0x1400448a3`

## string_xrefs

- `0x14004484f`: `NtGdiDdDDIOpenAdapterFromDeviceName`

## pseudocode

```c
__int64 __fastcall stub_GdiDdDDIOpenAdapterFromDeviceName(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 result; // rax

  if ( !(unsigned __int8)IsWin32KSyscallFiltered() )
    return NtGdiDdDDIOpenAdapterFromDeviceName(a1, a2, a3, a4);
  NtUserWin32kSysCallFilterStub();
  if ( !(unsigned __int8)PsIsWin32KFilterEnabled() )
    return NtGdiDdDDIOpenAdapterFromDeviceName(a1, a2, a3, a4);
  result = (unsigned int)*((char *)&W32pServiceTableFilter[67] + 4 * (unsigned int)W32pServiceLimitFilter + 3);
  if ( (int)result > 0 )
    return 3221225500LL;
  return result;
}

```

## disassembly

```asm
0x140044820  sub     rsp, 48h
0x140044824  mov     [rsp+48h+var_28], rcx
0x140044829  mov     [rsp+48h+var_20], rdx
0x14004482e  mov     [rsp+48h+var_18], r8
0x140044833  mov     [rsp+48h+var_10], r9
0x140044838  mov     rcx, 21Bh
0x14004483f  call    cs:__imp_IsWin32KSyscallFiltered
0x140044846  nop     dword ptr [rax+rax+00h]
0x14004484b  test    al, al
0x14004484d  jz      short loc_1400448A3
0x14004484f  lea     rcx, aNtgdiddddiopen; "NtGdiDdDDIOpenAdapterFromDeviceName"
0x140044856  mov     rdx, 21Bh
0x14004485d  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x140044864  nop     dword ptr [rax+rax+00h]
0x140044869  call    cs:__imp_PsIsWin32KFilterEnabled
0x140044870  nop     dword ptr [rax+rax+00h]
0x140044875  test    al, al
0x140044877  jz      short loc_1400448A3
0x140044879  lea     rcx, W32pServiceTableFilter
0x140044880  mov     edx, cs:W32pServiceLimitFilter
0x140044886  mov     rax, 21Bh
0x14004488d  lea     rcx, [rcx+rdx*4]
0x140044891  movsx   eax, byte ptr [rcx+rax]
0x140044895  or      eax, eax
0x140044897  jle     short loc_14004489E
0x140044899  mov     eax, 0C000001Ch
0x14004489e  add     rsp, 48h
0x1400448a2  retn
0x1400448a3  mov     rax, cs:__imp_NtGdiDdDDIOpenAdapterFromDeviceName
0x1400448aa  mov     rcx, [rsp+48h+var_28]
0x1400448af  mov     rdx, [rsp+48h+var_20]
0x1400448b4  mov     r8, [rsp+48h+var_18]
0x1400448b9  mov     r9, [rsp+48h+var_10]
0x1400448be  add     rsp, 48h
0x1400448c2  jmp     rax
```
