# _stub_GdiDdDDICreateHwContext

- ea: `0x140041540`
- end: `0x1400415e7`
- name: `_stub_GdiDdDDICreateHwContext`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x140041540`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140041589`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140041589`
- `ext-ms-win-core-win32k-dxgk-l1-1-0!NtGdiDdDDICreateHwContext` at `0x1400415c3`

## string_xrefs

- `0x14004156f`: `NtGdiDdDDICreateHwContext`

## pseudocode

```c
__int64 __fastcall stub_GdiDdDDICreateHwContext(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 result; // rax

  if ( !(unsigned __int8)IsWin32KSyscallFiltered() )
    return NtGdiDdDDICreateHwContext(a1, a2, a3, a4);
  NtUserWin32kSysCallFilterStub();
  if ( !(unsigned __int8)PsIsWin32KFilterEnabled() )
    return NtGdiDdDDICreateHwContext(a1, a2, a3, a4);
  result = (unsigned int)*((char *)&W32pServiceTableFilter[58] + 4 * (unsigned int)W32pServiceLimitFilter + 1);
  if ( (int)result > 0 )
    return 3221225500LL;
  return result;
}

```

## disassembly

```asm
0x140041540  sub     rsp, 48h
0x140041544  mov     [rsp+48h+var_28], rcx
0x140041549  mov     [rsp+48h+var_20], rdx
0x14004154e  mov     [rsp+48h+var_18], r8
0x140041553  mov     [rsp+48h+var_10], r9
0x140041558  mov     rcx, 1D1h
0x14004155f  call    cs:__imp_IsWin32KSyscallFiltered
0x140041566  nop     dword ptr [rax+rax+00h]
0x14004156b  test    al, al
0x14004156d  jz      short loc_1400415C3
0x14004156f  lea     rcx, aNtgdiddddicrea_5; "NtGdiDdDDICreateHwContext"
0x140041576  mov     rdx, 1D1h
0x14004157d  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x140041584  nop     dword ptr [rax+rax+00h]
0x140041589  call    cs:__imp_PsIsWin32KFilterEnabled
0x140041590  nop     dword ptr [rax+rax+00h]
0x140041595  test    al, al
0x140041597  jz      short loc_1400415C3
0x140041599  lea     rcx, W32pServiceTableFilter
0x1400415a0  mov     edx, cs:W32pServiceLimitFilter
0x1400415a6  mov     rax, 1D1h
0x1400415ad  lea     rcx, [rcx+rdx*4]
0x1400415b1  movsx   eax, byte ptr [rcx+rax]
0x1400415b5  or      eax, eax
0x1400415b7  jle     short loc_1400415BE
0x1400415b9  mov     eax, 0C000001Ch
0x1400415be  add     rsp, 48h
0x1400415c2  retn
0x1400415c3  mov     rax, cs:__imp_NtGdiDdDDICreateHwContext
0x1400415ca  mov     rcx, [rsp+48h+var_28]
0x1400415cf  mov     rdx, [rsp+48h+var_20]
0x1400415d4  mov     r8, [rsp+48h+var_18]
0x1400415d9  mov     r9, [rsp+48h+var_10]
0x1400415de  add     rsp, 48h
0x1400415e2  jmp     rax
```
