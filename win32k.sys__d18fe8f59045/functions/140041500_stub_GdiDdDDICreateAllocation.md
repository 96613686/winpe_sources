# _stub_GdiDdDDICreateAllocation

- ea: `0x140041500`
- end: `0x1400415a7`
- name: `_stub_GdiDdDDICreateAllocation`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x140041500`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140041549`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140041549`
- `ext-ms-win-core-win32k-dxgk-l1-1-0!NtGdiDdDDICreateAllocation` at `0x140041583`

## string_xrefs

- `0x14004152f`: `NtGdiDdDDICreateAllocation`

## pseudocode

```c
__int64 __fastcall stub_GdiDdDDICreateAllocation(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 result; // rax

  if ( !(unsigned __int8)IsWin32KSyscallFiltered() )
    return NtGdiDdDDICreateAllocation(a1, a2, a3, a4);
  NtUserWin32kSysCallFilterStub();
  if ( !(unsigned __int8)PsIsWin32KFilterEnabled() )
    return NtGdiDdDDICreateAllocation(a1, a2, a3, a4);
  result = (unsigned int)*((char *)&W32pServiceTableFilter[57] + 4 * (unsigned int)W32pServiceLimitFilter + 6);
  if ( (int)result > 0 )
    return 3221225500LL;
  return result;
}

```

## disassembly

```asm
0x140041500  sub     rsp, 48h
0x140041504  mov     [rsp+48h+var_28], rcx
0x140041509  mov     [rsp+48h+var_20], rdx
0x14004150e  mov     [rsp+48h+var_18], r8
0x140041513  mov     [rsp+48h+var_10], r9
0x140041518  mov     rcx, 1CEh
0x14004151f  call    cs:__imp_IsWin32KSyscallFiltered
0x140041526  nop     dword ptr [rax+rax+00h]
0x14004152b  test    al, al
0x14004152d  jz      short loc_140041583
0x14004152f  lea     rcx, aNtgdiddddicrea; "NtGdiDdDDICreateAllocation"
0x140041536  mov     rdx, 1CEh
0x14004153d  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x140041544  nop     dword ptr [rax+rax+00h]
0x140041549  call    cs:__imp_PsIsWin32KFilterEnabled
0x140041550  nop     dword ptr [rax+rax+00h]
0x140041555  test    al, al
0x140041557  jz      short loc_140041583
0x140041559  lea     rcx, W32pServiceTableFilter
0x140041560  mov     edx, cs:W32pServiceLimitFilter
0x140041566  mov     rax, 1CEh
0x14004156d  lea     rcx, [rcx+rdx*4]
0x140041571  movsx   eax, byte ptr [rcx+rax]
0x140041575  or      eax, eax
0x140041577  jle     short loc_14004157E
0x140041579  mov     eax, 0C000001Ch
0x14004157e  add     rsp, 48h
0x140041582  retn
0x140041583  mov     rax, cs:__imp_NtGdiDdDDICreateAllocation
0x14004158a  mov     rcx, [rsp+48h+var_28]
0x14004158f  mov     rdx, [rsp+48h+var_20]
0x140041594  mov     r8, [rsp+48h+var_18]
0x140041599  mov     r9, [rsp+48h+var_10]
0x14004159e  add     rsp, 48h
0x1400415a2  jmp     rax
```
