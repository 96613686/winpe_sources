# _stub_DCompositionSetChildRootVisual

- ea: `0x14003b150`
- end: `0x14003b1f7`
- name: `_stub_DCompositionSetChildRootVisual`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x14003b150`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x14003b199`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x14003b199`

## string_xrefs

- `0x14003b17f`: `NtDCompositionSetChildRootVisual`

## pseudocode

```c
__int64 stub_DCompositionSetChildRootVisual()
{
  __int64 result; // rax

  if ( !(unsigned __int8)IsWin32KSyscallFiltered() )
    return NtDCompositionSetChildRootVisual();
  NtUserWin32kSysCallFilterStub();
  if ( !(unsigned __int8)PsIsWin32KFilterEnabled() )
    return NtDCompositionSetChildRootVisual();
  result = (unsigned int)*((char *)&W32pServiceTableFilter[39] + 4 * (unsigned int)W32pServiceLimitFilter + 5);
  if ( (int)result > 0 )
    return 3221225500LL;
  return result;
}

```

## disassembly

```asm
0x14003b150  sub     rsp, 48h
0x14003b154  mov     [rsp+48h+var_28], rcx
0x14003b159  mov     [rsp+48h+var_20], rdx
0x14003b15e  mov     [rsp+48h+var_18], r8
0x14003b163  mov     [rsp+48h+var_10], r9
0x14003b168  mov     rcx, 13Dh
0x14003b16f  call    cs:__imp_IsWin32KSyscallFiltered
0x14003b176  nop     dword ptr [rax+rax+00h]
0x14003b17b  test    al, al
0x14003b17d  jz      short loc_14003B1D3
0x14003b17f  lea     rcx, aNtdcomposition_41; "NtDCompositionSetChildRootVisual"
0x14003b186  mov     rdx, 13Dh
0x14003b18d  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x14003b194  nop     dword ptr [rax+rax+00h]
0x14003b199  call    cs:__imp_PsIsWin32KFilterEnabled
0x14003b1a0  nop     dword ptr [rax+rax+00h]
0x14003b1a5  test    al, al
0x14003b1a7  jz      short loc_14003B1D3
0x14003b1a9  lea     rcx, W32pServiceTableFilter
0x14003b1b0  mov     edx, cs:W32pServiceLimitFilter
0x14003b1b6  mov     rax, 13Dh
0x14003b1bd  lea     rcx, [rcx+rdx*4]
0x14003b1c1  movsx   eax, byte ptr [rcx+rax]
0x14003b1c5  or      eax, eax
0x14003b1c7  jle     short loc_14003B1CE
0x14003b1c9  mov     eax, 0C000001Ch
0x14003b1ce  add     rsp, 48h
0x14003b1d2  retn
0x14003b1d3  mov     rax, cs:__imp_NtDCompositionSetChildRootVisual
0x14003b1da  mov     rcx, [rsp+48h+var_28]
0x14003b1df  mov     rdx, [rsp+48h+var_20]
0x14003b1e4  mov     r8, [rsp+48h+var_18]
0x14003b1e9  mov     r9, [rsp+48h+var_10]
0x14003b1ee  add     rsp, 48h
0x14003b1f2  jmp     rax
```
