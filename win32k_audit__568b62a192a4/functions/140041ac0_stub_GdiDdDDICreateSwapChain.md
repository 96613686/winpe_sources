# _stub_GdiDdDDICreateSwapChain

- ea: `0x140041ac0`
- end: `0x140041b67`
- name: `_stub_GdiDdDDICreateSwapChain`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x140041ac0`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140041b09`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140041b09`
- `ext-ms-win-core-win32k-dxgk-l1-1-0!NtGdiDdDDICreateSwapChain` at `0x140041b43`

## string_xrefs

- `0x140041aef`: `NtGdiDdDDICreateSwapChain`

## pseudocode

```c
__int64 __fastcall stub_GdiDdDDICreateSwapChain(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 result; // rax

  if ( !(unsigned __int8)IsWin32KSyscallFiltered() )
    return NtGdiDdDDICreateSwapChain(a1, a2, a3, a4);
  NtUserWin32kSysCallFilterStub();
  if ( !(unsigned __int8)PsIsWin32KFilterEnabled() )
    return NtGdiDdDDICreateSwapChain(a1, a2, a3, a4);
  result = (unsigned int)*((char *)&W32pServiceTableFilter[59] + 4 * (unsigned int)W32pServiceLimitFilter + 1);
  if ( (int)result > 0 )
    return 3221225500LL;
  return result;
}

```

## disassembly

```asm
0x140041ac0  sub     rsp, 48h
0x140041ac4  mov     [rsp+48h+var_28], rcx
0x140041ac9  mov     [rsp+48h+var_20], rdx
0x140041ace  mov     [rsp+48h+var_18], r8
0x140041ad3  mov     [rsp+48h+var_10], r9
0x140041ad8  mov     rcx, 1D9h
0x140041adf  call    cs:__imp_IsWin32KSyscallFiltered
0x140041ae6  nop     dword ptr [rax+rax+00h]
0x140041aeb  test    al, al
0x140041aed  jz      short loc_140041B43
0x140041aef  lea     rcx, aNtgdiddddicrea_13; "NtGdiDdDDICreateSwapChain"
0x140041af6  mov     rdx, 1D9h
0x140041afd  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x140041b04  nop     dword ptr [rax+rax+00h]
0x140041b09  call    cs:__imp_PsIsWin32KFilterEnabled
0x140041b10  nop     dword ptr [rax+rax+00h]
0x140041b15  test    al, al
0x140041b17  jz      short loc_140041B43
0x140041b19  lea     rcx, W32pServiceTableFilter
0x140041b20  mov     edx, cs:W32pServiceLimitFilter
0x140041b26  mov     rax, 1D9h
0x140041b2d  lea     rcx, [rcx+rdx*4]
0x140041b31  movsx   eax, byte ptr [rcx+rax]
0x140041b35  or      eax, eax
0x140041b37  jle     short loc_140041B3E
0x140041b39  mov     eax, 0C000001Ch
0x140041b3e  add     rsp, 48h
0x140041b42  retn
0x140041b43  mov     rax, cs:__imp_NtGdiDdDDICreateSwapChain
0x140041b4a  mov     rcx, [rsp+48h+var_28]
0x140041b4f  mov     rdx, [rsp+48h+var_20]
0x140041b54  mov     r8, [rsp+48h+var_18]
0x140041b59  mov     r9, [rsp+48h+var_10]
0x140041b5e  add     rsp, 48h
0x140041b62  jmp     rax
```
