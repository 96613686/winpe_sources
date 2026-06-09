# _stub_GdiDdDDIInvalidateCache

- ea: `0x140043fe0`
- end: `0x140044087`
- name: `_stub_GdiDdDDIInvalidateCache`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x140043fe0`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140044029`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140044029`
- `ext-ms-win-core-win32k-dxgk-l1-1-0!NtGdiDdDDIInvalidateCache` at `0x140044063`

## string_xrefs

- `0x14004400f`: `NtGdiDdDDIInvalidateCache`

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
  result = (unsigned int)*((char *)&W32pServiceTableFilter[65] + 4 * (unsigned int)W32pServiceLimitFilter + 7);
  if ( (int)result > 0 )
    return 3221225500LL;
  return result;
}

```

## disassembly

```asm
0x140043fe0  sub     rsp, 48h
0x140043fe4  mov     [rsp+48h+var_28], rcx
0x140043fe9  mov     [rsp+48h+var_20], rdx
0x140043fee  mov     [rsp+48h+var_18], r8
0x140043ff3  mov     [rsp+48h+var_10], r9
0x140043ff8  mov     rcx, 20Fh
0x140043fff  call    cs:__imp_IsWin32KSyscallFiltered
0x140044006  nop     dword ptr [rax+rax+00h]
0x14004400b  test    al, al
0x14004400d  jz      short loc_140044063
0x14004400f  lea     rcx, aNtgdiddddiinva_0; "NtGdiDdDDIInvalidateCache"
0x140044016  mov     rdx, 20Fh
0x14004401d  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x140044024  nop     dword ptr [rax+rax+00h]
0x140044029  call    cs:__imp_PsIsWin32KFilterEnabled
0x140044030  nop     dword ptr [rax+rax+00h]
0x140044035  test    al, al
0x140044037  jz      short loc_140044063
0x140044039  lea     rcx, W32pServiceTableFilter
0x140044040  mov     edx, cs:W32pServiceLimitFilter
0x140044046  mov     rax, 20Fh
0x14004404d  lea     rcx, [rcx+rdx*4]
0x140044051  movsx   eax, byte ptr [rcx+rax]
0x140044055  or      eax, eax
0x140044057  jle     short loc_14004405E
0x140044059  mov     eax, 0C000001Ch
0x14004405e  add     rsp, 48h
0x140044062  retn
0x140044063  mov     rax, cs:__imp_NtGdiDdDDIInvalidateCache
0x14004406a  mov     rcx, [rsp+48h+var_28]
0x14004406f  mov     rdx, [rsp+48h+var_20]
0x140044074  mov     r8, [rsp+48h+var_18]
0x140044079  mov     r9, [rsp+48h+var_10]
0x14004407e  add     rsp, 48h
0x140044082  jmp     rax
```
