# _stub_GdiDdDDIOpenAdapterFromLuid

- ea: `0x140044980`
- end: `0x140044a27`
- name: `_stub_GdiDdDDIOpenAdapterFromLuid`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x140044980`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x1400449c9`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x1400449c9`
- `ext-ms-win-core-win32k-dxgk-l1-1-0!NtGdiDdDDIOpenAdapterFromLuid` at `0x140044a03`

## string_xrefs

- `0x1400449af`: `NtGdiDdDDIOpenAdapterFromLuid`

## pseudocode

```c
__int64 __fastcall stub_GdiDdDDIOpenAdapterFromLuid(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 result; // rax

  if ( !(unsigned __int8)IsWin32KSyscallFiltered() )
    return NtGdiDdDDIOpenAdapterFromLuid(a1, a2, a3, a4);
  NtUserWin32kSysCallFilterStub();
  if ( !(unsigned __int8)PsIsWin32KFilterEnabled() )
    return NtGdiDdDDIOpenAdapterFromLuid(a1, a2, a3, a4);
  result = (unsigned int)*((char *)&W32pServiceTableFilter[67] + 4 * (unsigned int)W32pServiceLimitFilter + 5);
  if ( (int)result > 0 )
    return 3221225500LL;
  return result;
}

```

## disassembly

```asm
0x140044980  sub     rsp, 48h
0x140044984  mov     [rsp+48h+var_28], rcx
0x140044989  mov     [rsp+48h+var_20], rdx
0x14004498e  mov     [rsp+48h+var_18], r8
0x140044993  mov     [rsp+48h+var_10], r9
0x140044998  mov     rcx, 21Dh
0x14004499f  call    cs:__imp_IsWin32KSyscallFiltered
0x1400449a6  nop     dword ptr [rax+rax+00h]
0x1400449ab  test    al, al
0x1400449ad  jz      short loc_140044A03
0x1400449af  lea     rcx, aNtgdiddddiopen_1; "NtGdiDdDDIOpenAdapterFromLuid"
0x1400449b6  mov     rdx, 21Dh
0x1400449bd  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x1400449c4  nop     dword ptr [rax+rax+00h]
0x1400449c9  call    cs:__imp_PsIsWin32KFilterEnabled
0x1400449d0  nop     dword ptr [rax+rax+00h]
0x1400449d5  test    al, al
0x1400449d7  jz      short loc_140044A03
0x1400449d9  lea     rcx, W32pServiceTableFilter
0x1400449e0  mov     edx, cs:W32pServiceLimitFilter
0x1400449e6  mov     rax, 21Dh
0x1400449ed  lea     rcx, [rcx+rdx*4]
0x1400449f1  movsx   eax, byte ptr [rcx+rax]
0x1400449f5  or      eax, eax
0x1400449f7  jle     short loc_1400449FE
0x1400449f9  mov     eax, 0C000001Ch
0x1400449fe  add     rsp, 48h
0x140044a02  retn
0x140044a03  mov     rax, cs:__imp_NtGdiDdDDIOpenAdapterFromLuid
0x140044a0a  mov     rcx, [rsp+48h+var_28]
0x140044a0f  mov     rdx, [rsp+48h+var_20]
0x140044a14  mov     r8, [rsp+48h+var_18]
0x140044a19  mov     r9, [rsp+48h+var_10]
0x140044a1e  add     rsp, 48h
0x140044a22  jmp     rax
```
