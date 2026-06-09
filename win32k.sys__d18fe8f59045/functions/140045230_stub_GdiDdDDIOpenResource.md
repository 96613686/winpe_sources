# _stub_GdiDdDDIOpenResource

- ea: `0x140045230`
- end: `0x1400452d7`
- name: `_stub_GdiDdDDIOpenResource`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x140045230`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140045279`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140045279`
- `ext-ms-win-core-win32k-dxgk-l1-1-0!NtGdiDdDDIOpenResource` at `0x1400452b3`

## string_xrefs

- `0x14004525f`: `NtGdiDdDDIOpenResource`

## pseudocode

```c
__int64 __fastcall stub_GdiDdDDIOpenResource(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 result; // rax

  if ( !(unsigned __int8)IsWin32KSyscallFiltered() )
    return NtGdiDdDDIOpenResource(a1, a2, a3, a4);
  NtUserWin32kSysCallFilterStub();
  if ( !(unsigned __int8)PsIsWin32KFilterEnabled() )
    return NtGdiDdDDIOpenResource(a1, a2, a3, a4);
  result = (unsigned int)*((char *)&W32pServiceTableFilter[68] + 4 * (unsigned int)W32pServiceLimitFilter + 7);
  if ( (int)result > 0 )
    return 3221225500LL;
  return result;
}

```

## disassembly

```asm
0x140045230  sub     rsp, 48h
0x140045234  mov     [rsp+48h+var_28], rcx
0x140045239  mov     [rsp+48h+var_20], rdx
0x14004523e  mov     [rsp+48h+var_18], r8
0x140045243  mov     [rsp+48h+var_10], r9
0x140045248  mov     rcx, 227h
0x14004524f  call    cs:__imp_IsWin32KSyscallFiltered
0x140045256  nop     dword ptr [rax+rax+00h]
0x14004525b  test    al, al
0x14004525d  jz      short loc_1400452B3
0x14004525f  lea     rcx, aNtgdiddddiopen_8; "NtGdiDdDDIOpenResource"
0x140045266  mov     rdx, 227h
0x14004526d  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x140045274  nop     dword ptr [rax+rax+00h]
0x140045279  call    cs:__imp_PsIsWin32KFilterEnabled
0x140045280  nop     dword ptr [rax+rax+00h]
0x140045285  test    al, al
0x140045287  jz      short loc_1400452B3
0x140045289  lea     rcx, W32pServiceTableFilter
0x140045290  mov     edx, cs:W32pServiceLimitFilter
0x140045296  mov     rax, 227h
0x14004529d  lea     rcx, [rcx+rdx*4]
0x1400452a1  movsx   eax, byte ptr [rcx+rax]
0x1400452a5  or      eax, eax
0x1400452a7  jle     short loc_1400452AE
0x1400452a9  mov     eax, 0C000001Ch
0x1400452ae  add     rsp, 48h
0x1400452b2  retn
0x1400452b3  mov     rax, cs:__imp_NtGdiDdDDIOpenResource
0x1400452ba  mov     rcx, [rsp+48h+var_28]
0x1400452bf  mov     rdx, [rsp+48h+var_20]
0x1400452c4  mov     r8, [rsp+48h+var_18]
0x1400452c9  mov     r9, [rsp+48h+var_10]
0x1400452ce  add     rsp, 48h
0x1400452d2  jmp     rax
```
