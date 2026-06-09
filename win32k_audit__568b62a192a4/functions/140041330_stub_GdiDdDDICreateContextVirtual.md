# _stub_GdiDdDDICreateContextVirtual

- ea: `0x140041330`
- end: `0x1400413d7`
- name: `_stub_GdiDdDDICreateContextVirtual`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x140041330`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140041379`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140041379`
- `ext-ms-win-core-win32k-dxgk-l1-1-0!NtGdiDdDDICreateContextVirtual` at `0x1400413b3`

## string_xrefs

- `0x14004135f`: `NtGdiDdDDICreateContextVirtual`

## pseudocode

```c
__int64 __fastcall stub_GdiDdDDICreateContextVirtual(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 result; // rax

  if ( !(unsigned __int8)IsWin32KSyscallFiltered() )
    return NtGdiDdDDICreateContextVirtual(a1, a2, a3, a4);
  NtUserWin32kSysCallFilterStub();
  if ( !(unsigned __int8)PsIsWin32KFilterEnabled() )
    return NtGdiDdDDICreateContextVirtual(a1, a2, a3, a4);
  result = (unsigned int)*((char *)&W32pServiceTableFilter[57] + 4 * (unsigned int)W32pServiceLimitFilter + 6);
  if ( (int)result > 0 )
    return 3221225500LL;
  return result;
}

```

## disassembly

```asm
0x140041330  sub     rsp, 48h
0x140041334  mov     [rsp+48h+var_28], rcx
0x140041339  mov     [rsp+48h+var_20], rdx
0x14004133e  mov     [rsp+48h+var_18], r8
0x140041343  mov     [rsp+48h+var_10], r9
0x140041348  mov     rcx, 1CEh
0x14004134f  call    cs:__imp_IsWin32KSyscallFiltered
0x140041356  nop     dword ptr [rax+rax+00h]
0x14004135b  test    al, al
0x14004135d  jz      short loc_1400413B3
0x14004135f  lea     rcx, aNtgdiddddicrea_2; "NtGdiDdDDICreateContextVirtual"
0x140041366  mov     rdx, 1CEh
0x14004136d  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x140041374  nop     dword ptr [rax+rax+00h]
0x140041379  call    cs:__imp_PsIsWin32KFilterEnabled
0x140041380  nop     dword ptr [rax+rax+00h]
0x140041385  test    al, al
0x140041387  jz      short loc_1400413B3
0x140041389  lea     rcx, W32pServiceTableFilter
0x140041390  mov     edx, cs:W32pServiceLimitFilter
0x140041396  mov     rax, 1CEh
0x14004139d  lea     rcx, [rcx+rdx*4]
0x1400413a1  movsx   eax, byte ptr [rcx+rax]
0x1400413a5  or      eax, eax
0x1400413a7  jle     short loc_1400413AE
0x1400413a9  mov     eax, 0C000001Ch
0x1400413ae  add     rsp, 48h
0x1400413b2  retn
0x1400413b3  mov     rax, cs:__imp_NtGdiDdDDICreateContextVirtual
0x1400413ba  mov     rcx, [rsp+48h+var_28]
0x1400413bf  mov     rdx, [rsp+48h+var_20]
0x1400413c4  mov     r8, [rsp+48h+var_18]
0x1400413c9  mov     r9, [rsp+48h+var_10]
0x1400413ce  add     rsp, 48h
0x1400413d2  jmp     rax
```
