# _stub_GdiDdDDIMakeResident

- ea: `0x1400441f0`
- end: `0x140044297`
- name: `_stub_GdiDdDDIMakeResident`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, service_task`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x1400441f0`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140044239`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140044239`
- `ext-ms-win-core-win32k-dxgk-l1-1-0!NtGdiDdDDIMakeResident` at `0x140044273`

## string_xrefs

- `0x14004421f`: `NtGdiDdDDIMakeResident`

## pseudocode

```c
__int64 __fastcall stub_GdiDdDDIMakeResident(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 result; // rax

  if ( !(unsigned __int8)IsWin32KSyscallFiltered() )
    return NtGdiDdDDIMakeResident(a1, a2, a3, a4);
  NtUserWin32kSysCallFilterStub();
  if ( !(unsigned __int8)PsIsWin32KFilterEnabled() )
    return NtGdiDdDDIMakeResident(a1, a2, a3, a4);
  result = (unsigned int)*((char *)&W32pServiceTableFilter[66] + 4 * (unsigned int)W32pServiceLimitFilter + 2);
  if ( (int)result > 0 )
    return 3221225500LL;
  return result;
}

```

## disassembly

```asm
0x1400441f0  sub     rsp, 48h
0x1400441f4  mov     [rsp+48h+var_28], rcx
0x1400441f9  mov     [rsp+48h+var_20], rdx
0x1400441fe  mov     [rsp+48h+var_18], r8
0x140044203  mov     [rsp+48h+var_10], r9
0x140044208  mov     rcx, 212h
0x14004420f  call    cs:__imp_IsWin32KSyscallFiltered
0x140044216  nop     dword ptr [rax+rax+00h]
0x14004421b  test    al, al
0x14004421d  jz      short loc_140044273
0x14004421f  lea     rcx, aNtgdiddddimake; "NtGdiDdDDIMakeResident"
0x140044226  mov     rdx, 212h
0x14004422d  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x140044234  nop     dword ptr [rax+rax+00h]
0x140044239  call    cs:__imp_PsIsWin32KFilterEnabled
0x140044240  nop     dword ptr [rax+rax+00h]
0x140044245  test    al, al
0x140044247  jz      short loc_140044273
0x140044249  lea     rcx, W32pServiceTableFilter
0x140044250  mov     edx, cs:W32pServiceLimitFilter
0x140044256  mov     rax, 212h
0x14004425d  lea     rcx, [rcx+rdx*4]
0x140044261  movsx   eax, byte ptr [rcx+rax]
0x140044265  or      eax, eax
0x140044267  jle     short loc_14004426E
0x140044269  mov     eax, 0C000001Ch
0x14004426e  add     rsp, 48h
0x140044272  retn
0x140044273  mov     rax, cs:__imp_NtGdiDdDDIMakeResident
0x14004427a  mov     rcx, [rsp+48h+var_28]
0x14004427f  mov     rdx, [rsp+48h+var_20]
0x140044284  mov     r8, [rsp+48h+var_18]
0x140044289  mov     r9, [rsp+48h+var_10]
0x14004428e  add     rsp, 48h
0x140044292  jmp     rax
```
