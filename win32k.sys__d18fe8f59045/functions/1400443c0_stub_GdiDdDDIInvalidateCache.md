# _stub_GdiDdDDIInvalidateCache

- ea: `0x1400443c0`
- end: `0x140044467`
- name: `_stub_GdiDdDDIInvalidateCache`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x1400443c0`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140044409`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140044409`
- `ext-ms-win-core-win32k-dxgk-l1-1-0!NtGdiDdDDIInvalidateCache` at `0x140044443`

## string_xrefs

- `0x1400443ef`: `NtGdiDdDDIInvalidateCache`

## pseudocode

```c
__int64 __fastcall stub_GdiDdDDIInvalidateCache(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 result; // rax

  if ( !(unsigned __int8)IsWin32KSyscallFiltered() )
    return NtGdiDdDDIInvalidateCache(a1, a2, a3, a4);
  NtUserWin32kSysCallFilterStub();
  if ( !(unsigned __int8)PsIsWin32KFilterEnabled() )
    return NtGdiDdDDIInvalidateCache(a1, a2, a3, a4);
  result = (unsigned int)*((char *)&W32pServiceTableFilter[66] + 4 * (unsigned int)W32pServiceLimitFilter + 2);
  if ( (int)result > 0 )
    return 3221225500LL;
  return result;
}

```

## disassembly

```asm
0x1400443c0  sub     rsp, 48h
0x1400443c4  mov     [rsp+48h+var_28], rcx
0x1400443c9  mov     [rsp+48h+var_20], rdx
0x1400443ce  mov     [rsp+48h+var_18], r8
0x1400443d3  mov     [rsp+48h+var_10], r9
0x1400443d8  mov     rcx, 212h
0x1400443df  call    cs:__imp_IsWin32KSyscallFiltered
0x1400443e6  nop     dword ptr [rax+rax+00h]
0x1400443eb  test    al, al
0x1400443ed  jz      short loc_140044443
0x1400443ef  lea     rcx, aNtgdiddddiinva_0; "NtGdiDdDDIInvalidateCache"
0x1400443f6  mov     rdx, 212h
0x1400443fd  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x140044404  nop     dword ptr [rax+rax+00h]
0x140044409  call    cs:__imp_PsIsWin32KFilterEnabled
0x140044410  nop     dword ptr [rax+rax+00h]
0x140044415  test    al, al
0x140044417  jz      short loc_140044443
0x140044419  lea     rcx, W32pServiceTableFilter
0x140044420  mov     edx, cs:W32pServiceLimitFilter
0x140044426  mov     rax, 212h
0x14004442d  lea     rcx, [rcx+rdx*4]
0x140044431  movsx   eax, byte ptr [rcx+rax]
0x140044435  or      eax, eax
0x140044437  jle     short loc_14004443E
0x140044439  mov     eax, 0C000001Ch
0x14004443e  add     rsp, 48h
0x140044442  retn
0x140044443  mov     rax, cs:__imp_NtGdiDdDDIInvalidateCache
0x14004444a  mov     rcx, [rsp+48h+var_28]
0x14004444f  mov     rdx, [rsp+48h+var_20]
0x140044454  mov     r8, [rsp+48h+var_18]
0x140044459  mov     r9, [rsp+48h+var_10]
0x14004445e  add     rsp, 48h
0x140044462  jmp     rax
```
