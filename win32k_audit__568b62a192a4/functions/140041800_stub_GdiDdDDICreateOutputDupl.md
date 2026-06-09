# _stub_GdiDdDDICreateOutputDupl

- ea: `0x140041800`
- end: `0x1400418a7`
- name: `_stub_GdiDdDDICreateOutputDupl`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x140041800`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140041849`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140041849`
- `ext-ms-win-core-win32k-dxgk-l1-1-0!NtGdiDdDDICreateOutputDupl` at `0x140041883`

## string_xrefs

- `0x14004182f`: `NtGdiDdDDICreateOutputDupl`

## pseudocode

```c
__int64 __fastcall stub_GdiDdDDICreateOutputDupl(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 result; // rax

  if ( !(unsigned __int8)IsWin32KSyscallFiltered() )
    return NtGdiDdDDICreateOutputDupl(a1, a2, a3, a4);
  NtUserWin32kSysCallFilterStub();
  if ( !(unsigned __int8)PsIsWin32KFilterEnabled() )
    return NtGdiDdDDICreateOutputDupl(a1, a2, a3, a4);
  result = (unsigned int)*((char *)&W32pServiceTableFilter[58] + 4 * (unsigned int)W32pServiceLimitFilter + 5);
  if ( (int)result > 0 )
    return 3221225500LL;
  return result;
}

```

## disassembly

```asm
0x140041800  sub     rsp, 48h
0x140041804  mov     [rsp+48h+var_28], rcx
0x140041809  mov     [rsp+48h+var_20], rdx
0x14004180e  mov     [rsp+48h+var_18], r8
0x140041813  mov     [rsp+48h+var_10], r9
0x140041818  mov     rcx, 1D5h
0x14004181f  call    cs:__imp_IsWin32KSyscallFiltered
0x140041826  nop     dword ptr [rax+rax+00h]
0x14004182b  test    al, al
0x14004182d  jz      short loc_140041883
0x14004182f  lea     rcx, aNtgdiddddicrea_9; "NtGdiDdDDICreateOutputDupl"
0x140041836  mov     rdx, 1D5h
0x14004183d  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x140041844  nop     dword ptr [rax+rax+00h]
0x140041849  call    cs:__imp_PsIsWin32KFilterEnabled
0x140041850  nop     dword ptr [rax+rax+00h]
0x140041855  test    al, al
0x140041857  jz      short loc_140041883
0x140041859  lea     rcx, W32pServiceTableFilter
0x140041860  mov     edx, cs:W32pServiceLimitFilter
0x140041866  mov     rax, 1D5h
0x14004186d  lea     rcx, [rcx+rdx*4]
0x140041871  movsx   eax, byte ptr [rcx+rax]
0x140041875  or      eax, eax
0x140041877  jle     short loc_14004187E
0x140041879  mov     eax, 0C000001Ch
0x14004187e  add     rsp, 48h
0x140041882  retn
0x140041883  mov     rax, cs:__imp_NtGdiDdDDICreateOutputDupl
0x14004188a  mov     rcx, [rsp+48h+var_28]
0x14004188f  mov     rdx, [rsp+48h+var_20]
0x140041894  mov     r8, [rsp+48h+var_18]
0x140041899  mov     r9, [rsp+48h+var_10]
0x14004189e  add     rsp, 48h
0x1400418a2  jmp     rax
```
