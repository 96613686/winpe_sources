# _stub_GdiDdDDICreateSwapChain

- ea: `0x140041ea0`
- end: `0x140041f47`
- name: `_stub_GdiDdDDICreateSwapChain`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x140041ea0`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140041ee9`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140041ee9`
- `ext-ms-win-core-win32k-dxgk-l1-1-0!NtGdiDdDDICreateSwapChain` at `0x140041f23`

## string_xrefs

- `0x140041ecf`: `NtGdiDdDDICreateSwapChain`

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
  result = (unsigned int)*((char *)&W32pServiceTableFilter[59] + 4 * (unsigned int)W32pServiceLimitFilter + 4);
  if ( (int)result > 0 )
    return 3221225500LL;
  return result;
}

```

## disassembly

```asm
0x140041ea0  sub     rsp, 48h
0x140041ea4  mov     [rsp+48h+var_28], rcx
0x140041ea9  mov     [rsp+48h+var_20], rdx
0x140041eae  mov     [rsp+48h+var_18], r8
0x140041eb3  mov     [rsp+48h+var_10], r9
0x140041eb8  mov     rcx, 1DCh
0x140041ebf  call    cs:__imp_IsWin32KSyscallFiltered
0x140041ec6  nop     dword ptr [rax+rax+00h]
0x140041ecb  test    al, al
0x140041ecd  jz      short loc_140041F23
0x140041ecf  lea     rcx, aNtgdiddddicrea_13; "NtGdiDdDDICreateSwapChain"
0x140041ed6  mov     rdx, 1DCh
0x140041edd  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x140041ee4  nop     dword ptr [rax+rax+00h]
0x140041ee9  call    cs:__imp_PsIsWin32KFilterEnabled
0x140041ef0  nop     dword ptr [rax+rax+00h]
0x140041ef5  test    al, al
0x140041ef7  jz      short loc_140041F23
0x140041ef9  lea     rcx, W32pServiceTableFilter
0x140041f00  mov     edx, cs:W32pServiceLimitFilter
0x140041f06  mov     rax, 1DCh
0x140041f0d  lea     rcx, [rcx+rdx*4]
0x140041f11  movsx   eax, byte ptr [rcx+rax]
0x140041f15  or      eax, eax
0x140041f17  jle     short loc_140041F1E
0x140041f19  mov     eax, 0C000001Ch
0x140041f1e  add     rsp, 48h
0x140041f22  retn
0x140041f23  mov     rax, cs:__imp_NtGdiDdDDICreateSwapChain
0x140041f2a  mov     rcx, [rsp+48h+var_28]
0x140041f2f  mov     rdx, [rsp+48h+var_20]
0x140041f34  mov     r8, [rsp+48h+var_18]
0x140041f39  mov     r9, [rsp+48h+var_10]
0x140041f3e  add     rsp, 48h
0x140041f42  jmp     rax
```
