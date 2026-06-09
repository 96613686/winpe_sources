# _stub_GdiDdDDICreateContext

- ea: `0x140041660`
- end: `0x140041707`
- name: `_stub_GdiDdDDICreateContext`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x140041660`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x1400416a9`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x1400416a9`
- `ext-ms-win-core-win32k-dxgk-l1-1-0!NtGdiDdDDICreateContext` at `0x1400416e3`

## string_xrefs

- `0x14004168f`: `NtGdiDdDDICreateContext`

## pseudocode

```c
__int64 __fastcall stub_GdiDdDDICreateContext(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 result; // rax

  if ( !(unsigned __int8)IsWin32KSyscallFiltered() )
    return NtGdiDdDDICreateContext(a1, a2, a3, a4);
  NtUserWin32kSysCallFilterStub();
  if ( !(unsigned __int8)PsIsWin32KFilterEnabled() )
    return NtGdiDdDDICreateContext(a1, a2, a3, a4);
  result = (unsigned int)*((char *)&W32pServiceTableFilter[58] + 4 * (unsigned int)W32pServiceLimitFilter);
  if ( (int)result > 0 )
    return 3221225500LL;
  return result;
}

```

## disassembly

```asm
0x140041660  sub     rsp, 48h
0x140041664  mov     [rsp+48h+var_28], rcx
0x140041669  mov     [rsp+48h+var_20], rdx
0x14004166e  mov     [rsp+48h+var_18], r8
0x140041673  mov     [rsp+48h+var_10], r9
0x140041678  mov     rcx, 1D0h
0x14004167f  call    cs:__imp_IsWin32KSyscallFiltered
0x140041686  nop     dword ptr [rax+rax+00h]
0x14004168b  test    al, al
0x14004168d  jz      short loc_1400416E3
0x14004168f  lea     rcx, aNtgdiddddicrea_1; "NtGdiDdDDICreateContext"
0x140041696  mov     rdx, 1D0h
0x14004169d  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x1400416a4  nop     dword ptr [rax+rax+00h]
0x1400416a9  call    cs:__imp_PsIsWin32KFilterEnabled
0x1400416b0  nop     dword ptr [rax+rax+00h]
0x1400416b5  test    al, al
0x1400416b7  jz      short loc_1400416E3
0x1400416b9  lea     rcx, W32pServiceTableFilter
0x1400416c0  mov     edx, cs:W32pServiceLimitFilter
0x1400416c6  mov     rax, 1D0h
0x1400416cd  lea     rcx, [rcx+rdx*4]
0x1400416d1  movsx   eax, byte ptr [rcx+rax]
0x1400416d5  or      eax, eax
0x1400416d7  jle     short loc_1400416DE
0x1400416d9  mov     eax, 0C000001Ch
0x1400416de  add     rsp, 48h
0x1400416e2  retn
0x1400416e3  mov     rax, cs:__imp_NtGdiDdDDICreateContext
0x1400416ea  mov     rcx, [rsp+48h+var_28]
0x1400416ef  mov     rdx, [rsp+48h+var_20]
0x1400416f4  mov     r8, [rsp+48h+var_18]
0x1400416f9  mov     r9, [rsp+48h+var_10]
0x1400416fe  add     rsp, 48h
0x140041702  jmp     rax
```
