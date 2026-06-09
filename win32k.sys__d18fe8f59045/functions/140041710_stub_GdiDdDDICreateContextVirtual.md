# _stub_GdiDdDDICreateContextVirtual

- ea: `0x140041710`
- end: `0x1400417b7`
- name: `_stub_GdiDdDDICreateContextVirtual`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x140041710`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140041759`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140041759`
- `ext-ms-win-core-win32k-dxgk-l1-1-0!NtGdiDdDDICreateContextVirtual` at `0x140041793`

## string_xrefs

- `0x14004173f`: `NtGdiDdDDICreateContextVirtual`

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
  result = (unsigned int)*((char *)&W32pServiceTableFilter[58] + 4 * (unsigned int)W32pServiceLimitFilter + 1);
  if ( (int)result > 0 )
    return 3221225500LL;
  return result;
}

```

## disassembly

```asm
0x140041710  sub     rsp, 48h
0x140041714  mov     [rsp+48h+var_28], rcx
0x140041719  mov     [rsp+48h+var_20], rdx
0x14004171e  mov     [rsp+48h+var_18], r8
0x140041723  mov     [rsp+48h+var_10], r9
0x140041728  mov     rcx, 1D1h
0x14004172f  call    cs:__imp_IsWin32KSyscallFiltered
0x140041736  nop     dword ptr [rax+rax+00h]
0x14004173b  test    al, al
0x14004173d  jz      short loc_140041793
0x14004173f  lea     rcx, aNtgdiddddicrea_2; "NtGdiDdDDICreateContextVirtual"
0x140041746  mov     rdx, 1D1h
0x14004174d  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x140041754  nop     dword ptr [rax+rax+00h]
0x140041759  call    cs:__imp_PsIsWin32KFilterEnabled
0x140041760  nop     dword ptr [rax+rax+00h]
0x140041765  test    al, al
0x140041767  jz      short loc_140041793
0x140041769  lea     rcx, W32pServiceTableFilter
0x140041770  mov     edx, cs:W32pServiceLimitFilter
0x140041776  mov     rax, 1D1h
0x14004177d  lea     rcx, [rcx+rdx*4]
0x140041781  movsx   eax, byte ptr [rcx+rax]
0x140041785  or      eax, eax
0x140041787  jle     short loc_14004178E
0x140041789  mov     eax, 0C000001Ch
0x14004178e  add     rsp, 48h
0x140041792  retn
0x140041793  mov     rax, cs:__imp_NtGdiDdDDICreateContextVirtual
0x14004179a  mov     rcx, [rsp+48h+var_28]
0x14004179f  mov     rdx, [rsp+48h+var_20]
0x1400417a4  mov     r8, [rsp+48h+var_18]
0x1400417a9  mov     r9, [rsp+48h+var_10]
0x1400417ae  add     rsp, 48h
0x1400417b2  jmp     rax
```
