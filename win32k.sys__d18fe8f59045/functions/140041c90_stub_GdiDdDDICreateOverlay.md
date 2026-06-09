# _stub_GdiDdDDICreateOverlay

- ea: `0x140041c90`
- end: `0x140041d37`
- name: `_stub_GdiDdDDICreateOverlay`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x140041c90`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140041cd9`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140041cd9`
- `ext-ms-win-core-win32k-dxgk-l1-1-0!NtGdiDdDDICreateOverlay` at `0x140041d13`

## string_xrefs

- `0x140041cbf`: `NtGdiDdDDICreateOverlay`

## pseudocode

```c
__int64 __fastcall stub_GdiDdDDICreateOverlay(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 result; // rax

  if ( !(unsigned __int8)IsWin32KSyscallFiltered() )
    return NtGdiDdDDICreateOverlay(a1, a2, a3, a4);
  NtUserWin32kSysCallFilterStub();
  if ( !(unsigned __int8)PsIsWin32KFilterEnabled() )
    return NtGdiDdDDICreateOverlay(a1, a2, a3, a4);
  result = (unsigned int)*((char *)&W32pServiceTableFilter[59] + 4 * (unsigned int)W32pServiceLimitFilter + 1);
  if ( (int)result > 0 )
    return 3221225500LL;
  return result;
}

```

## disassembly

```asm
0x140041c90  sub     rsp, 48h
0x140041c94  mov     [rsp+48h+var_28], rcx
0x140041c99  mov     [rsp+48h+var_20], rdx
0x140041c9e  mov     [rsp+48h+var_18], r8
0x140041ca3  mov     [rsp+48h+var_10], r9
0x140041ca8  mov     rcx, 1D9h
0x140041caf  call    cs:__imp_IsWin32KSyscallFiltered
0x140041cb6  nop     dword ptr [rax+rax+00h]
0x140041cbb  test    al, al
0x140041cbd  jz      short loc_140041D13
0x140041cbf  lea     rcx, aNtgdiddddicrea_10; "NtGdiDdDDICreateOverlay"
0x140041cc6  mov     rdx, 1D9h
0x140041ccd  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x140041cd4  nop     dword ptr [rax+rax+00h]
0x140041cd9  call    cs:__imp_PsIsWin32KFilterEnabled
0x140041ce0  nop     dword ptr [rax+rax+00h]
0x140041ce5  test    al, al
0x140041ce7  jz      short loc_140041D13
0x140041ce9  lea     rcx, W32pServiceTableFilter
0x140041cf0  mov     edx, cs:W32pServiceLimitFilter
0x140041cf6  mov     rax, 1D9h
0x140041cfd  lea     rcx, [rcx+rdx*4]
0x140041d01  movsx   eax, byte ptr [rcx+rax]
0x140041d05  or      eax, eax
0x140041d07  jle     short loc_140041D0E
0x140041d09  mov     eax, 0C000001Ch
0x140041d0e  add     rsp, 48h
0x140041d12  retn
0x140041d13  mov     rax, cs:__imp_NtGdiDdDDICreateOverlay
0x140041d1a  mov     rcx, [rsp+48h+var_28]
0x140041d1f  mov     rdx, [rsp+48h+var_20]
0x140041d24  mov     r8, [rsp+48h+var_18]
0x140041d29  mov     r9, [rsp+48h+var_10]
0x140041d2e  add     rsp, 48h
0x140041d32  jmp     rax
```
