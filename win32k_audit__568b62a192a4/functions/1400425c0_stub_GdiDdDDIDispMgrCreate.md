# _stub_GdiDdDDIDispMgrCreate

- ea: `0x1400425c0`
- end: `0x140042667`
- name: `_stub_GdiDdDDIDispMgrCreate`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x1400425c0`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140042609`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140042609`
- `ext-ms-win-core-win32k-dxgk-l1-1-0!NtGdiDdDDIDispMgrCreate` at `0x140042643`

## string_xrefs

- `0x1400425ef`: `NtGdiDdDDIDispMgrCreate`

## pseudocode

```c
__int64 __fastcall stub_GdiDdDDIDispMgrCreate(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 result; // rax

  if ( !(unsigned __int8)IsWin32KSyscallFiltered() )
    return NtGdiDdDDIDispMgrCreate(a1, a2, a3, a4);
  NtUserWin32kSysCallFilterStub();
  if ( !(unsigned __int8)PsIsWin32KFilterEnabled() )
    return NtGdiDdDDIDispMgrCreate(a1, a2, a3, a4);
  result = (unsigned int)*((char *)&W32pServiceTableFilter[61] + 4 * (unsigned int)W32pServiceLimitFilter + 1);
  if ( (int)result > 0 )
    return 3221225500LL;
  return result;
}

```

## disassembly

```asm
0x1400425c0  sub     rsp, 48h
0x1400425c4  mov     [rsp+48h+var_28], rcx
0x1400425c9  mov     [rsp+48h+var_20], rdx
0x1400425ce  mov     [rsp+48h+var_18], r8
0x1400425d3  mov     [rsp+48h+var_10], r9
0x1400425d8  mov     rcx, 1E9h
0x1400425df  call    cs:__imp_IsWin32KSyscallFiltered
0x1400425e6  nop     dword ptr [rax+rax+00h]
0x1400425eb  test    al, al
0x1400425ed  jz      short loc_140042643
0x1400425ef  lea     rcx, aNtgdiddddidisp; "NtGdiDdDDIDispMgrCreate"
0x1400425f6  mov     rdx, 1E9h
0x1400425fd  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x140042604  nop     dword ptr [rax+rax+00h]
0x140042609  call    cs:__imp_PsIsWin32KFilterEnabled
0x140042610  nop     dword ptr [rax+rax+00h]
0x140042615  test    al, al
0x140042617  jz      short loc_140042643
0x140042619  lea     rcx, W32pServiceTableFilter
0x140042620  mov     edx, cs:W32pServiceLimitFilter
0x140042626  mov     rax, 1E9h
0x14004262d  lea     rcx, [rcx+rdx*4]
0x140042631  movsx   eax, byte ptr [rcx+rax]
0x140042635  or      eax, eax
0x140042637  jle     short loc_14004263E
0x140042639  mov     eax, 0C000001Ch
0x14004263e  add     rsp, 48h
0x140042642  retn
0x140042643  mov     rax, cs:__imp_NtGdiDdDDIDispMgrCreate
0x14004264a  mov     rcx, [rsp+48h+var_28]
0x14004264f  mov     rdx, [rsp+48h+var_20]
0x140042654  mov     r8, [rsp+48h+var_18]
0x140042659  mov     r9, [rsp+48h+var_10]
0x14004265e  add     rsp, 48h
0x140042662  jmp     rax
```
