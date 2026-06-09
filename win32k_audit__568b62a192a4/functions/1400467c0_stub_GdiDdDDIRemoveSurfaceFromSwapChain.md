# _stub_GdiDdDDIRemoveSurfaceFromSwapChain

- ea: `0x1400467c0`
- end: `0x140046867`
- name: `_stub_GdiDdDDIRemoveSurfaceFromSwapChain`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x1400467c0`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140046809`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140046809`
- `ext-ms-win-core-win32k-dxgk-l1-1-0!NtGdiDdDDIRemoveSurfaceFromSwapChain` at `0x140046843`

## string_xrefs

- `0x1400467ef`: `NtGdiDdDDIRemoveSurfaceFromSwapChain`

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
  result = (unsigned int)*((char *)&W32pServiceTableFilter[73] + 4 * (unsigned int)W32pServiceLimitFilter + 1);
  if ( (int)result > 0 )
    return 3221225500LL;
  return result;
}

```

## disassembly

```asm
0x1400467c0  sub     rsp, 48h
0x1400467c4  mov     [rsp+48h+var_28], rcx
0x1400467c9  mov     [rsp+48h+var_20], rdx
0x1400467ce  mov     [rsp+48h+var_18], r8
0x1400467d3  mov     [rsp+48h+var_10], r9
0x1400467d8  mov     rcx, 249h
0x1400467df  call    cs:__imp_IsWin32KSyscallFiltered
0x1400467e6  nop     dword ptr [rax+rax+00h]
0x1400467eb  test    al, al
0x1400467ed  jz      short loc_140046843
0x1400467ef  lea     rcx, aNtgdiddddiremo; "NtGdiDdDDIRemoveSurfaceFromSwapChain"
0x1400467f6  mov     rdx, 249h
0x1400467fd  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x140046804  nop     dword ptr [rax+rax+00h]
0x140046809  call    cs:__imp_PsIsWin32KFilterEnabled
0x140046810  nop     dword ptr [rax+rax+00h]
0x140046815  test    al, al
0x140046817  jz      short loc_140046843
0x140046819  lea     rcx, W32pServiceTableFilter
0x140046820  mov     edx, cs:W32pServiceLimitFilter
0x140046826  mov     rax, 249h
0x14004682d  lea     rcx, [rcx+rdx*4]
0x140046831  movsx   eax, byte ptr [rcx+rax]
0x140046835  or      eax, eax
0x140046837  jle     short loc_14004683E
0x140046839  mov     eax, 0C000001Ch
0x14004683e  add     rsp, 48h
0x140046842  retn
0x140046843  mov     rax, cs:__imp_NtGdiDdDDIRemoveSurfaceFromSwapChain
0x14004684a  mov     rcx, [rsp+48h+var_28]
0x14004684f  mov     rdx, [rsp+48h+var_20]
0x140046854  mov     r8, [rsp+48h+var_18]
0x140046859  mov     r9, [rsp+48h+var_10]
0x14004685e  add     rsp, 48h
0x140046862  jmp     rax
```
