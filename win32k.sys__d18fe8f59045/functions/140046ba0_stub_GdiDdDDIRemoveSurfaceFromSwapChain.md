# _stub_GdiDdDDIRemoveSurfaceFromSwapChain

- ea: `0x140046ba0`
- end: `0x140046c47`
- name: `_stub_GdiDdDDIRemoveSurfaceFromSwapChain`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x140046ba0`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140046be9`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140046be9`
- `ext-ms-win-core-win32k-dxgk-l1-1-0!NtGdiDdDDIRemoveSurfaceFromSwapChain` at `0x140046c23`

## string_xrefs

- `0x140046bcf`: `NtGdiDdDDIRemoveSurfaceFromSwapChain`

## pseudocode

```c
__int64 __fastcall stub_GdiDdDDIRemoveSurfaceFromSwapChain(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 result; // rax

  if ( !(unsigned __int8)IsWin32KSyscallFiltered() )
    return NtGdiDdDDIRemoveSurfaceFromSwapChain(a1, a2, a3, a4);
  NtUserWin32kSysCallFilterStub();
  if ( !(unsigned __int8)PsIsWin32KFilterEnabled() )
    return NtGdiDdDDIRemoveSurfaceFromSwapChain(a1, a2, a3, a4);
  result = (unsigned int)*((char *)&W32pServiceTableFilter[73] + 4 * (unsigned int)W32pServiceLimitFilter + 4);
  if ( (int)result > 0 )
    return 3221225500LL;
  return result;
}

```

## disassembly

```asm
0x140046ba0  sub     rsp, 48h
0x140046ba4  mov     [rsp+48h+var_28], rcx
0x140046ba9  mov     [rsp+48h+var_20], rdx
0x140046bae  mov     [rsp+48h+var_18], r8
0x140046bb3  mov     [rsp+48h+var_10], r9
0x140046bb8  mov     rcx, 24Ch
0x140046bbf  call    cs:__imp_IsWin32KSyscallFiltered
0x140046bc6  nop     dword ptr [rax+rax+00h]
0x140046bcb  test    al, al
0x140046bcd  jz      short loc_140046C23
0x140046bcf  lea     rcx, aNtgdiddddiremo; "NtGdiDdDDIRemoveSurfaceFromSwapChain"
0x140046bd6  mov     rdx, 24Ch
0x140046bdd  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x140046be4  nop     dword ptr [rax+rax+00h]
0x140046be9  call    cs:__imp_PsIsWin32KFilterEnabled
0x140046bf0  nop     dword ptr [rax+rax+00h]
0x140046bf5  test    al, al
0x140046bf7  jz      short loc_140046C23
0x140046bf9  lea     rcx, W32pServiceTableFilter
0x140046c00  mov     edx, cs:W32pServiceLimitFilter
0x140046c06  mov     rax, 24Ch
0x140046c0d  lea     rcx, [rcx+rdx*4]
0x140046c11  movsx   eax, byte ptr [rcx+rax]
0x140046c15  or      eax, eax
0x140046c17  jle     short loc_140046C1E
0x140046c19  mov     eax, 0C000001Ch
0x140046c1e  add     rsp, 48h
0x140046c22  retn
0x140046c23  mov     rax, cs:__imp_NtGdiDdDDIRemoveSurfaceFromSwapChain
0x140046c2a  mov     rcx, [rsp+48h+var_28]
0x140046c2f  mov     rdx, [rsp+48h+var_20]
0x140046c34  mov     r8, [rsp+48h+var_18]
0x140046c39  mov     r9, [rsp+48h+var_10]
0x140046c3e  add     rsp, 48h
0x140046c42  jmp     rax
```
