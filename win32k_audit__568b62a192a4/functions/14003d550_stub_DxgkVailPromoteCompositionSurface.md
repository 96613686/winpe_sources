# _stub_DxgkVailPromoteCompositionSurface

- ea: `0x14003d550`
- end: `0x14003d5f7`
- name: `_stub_DxgkVailPromoteCompositionSurface`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x14003d550`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x14003d599`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x14003d599`
- `ext-ms-win-core-win32k-dxgk-l1-1-0!NtDxgkVailPromoteCompositionSurface` at `0x14003d5d3`

## string_xrefs

- `0x14003d57f`: `NtDxgkVailPromoteCompositionSurface`

## pseudocode

```c
__int64 __fastcall stub_DxgkVailPromoteCompositionSurface(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 result; // rax

  if ( !(unsigned __int8)IsWin32KSyscallFiltered() )
    return NtDxgkVailPromoteCompositionSurface(a1, a2, a3, a4);
  NtUserWin32kSysCallFilterStub();
  if ( !(unsigned __int8)PsIsWin32KFilterEnabled() )
    return NtDxgkVailPromoteCompositionSurface(a1, a2, a3, a4);
  result = (unsigned int)*((char *)&W32pServiceTableFilter[46] + 4 * (unsigned int)W32pServiceLimitFilter + 4);
  if ( (int)result > 0 )
    return 3221225500LL;
  return result;
}

```

## disassembly

```asm
0x14003d550  sub     rsp, 48h
0x14003d554  mov     [rsp+48h+var_28], rcx
0x14003d559  mov     [rsp+48h+var_20], rdx
0x14003d55e  mov     [rsp+48h+var_18], r8
0x14003d563  mov     [rsp+48h+var_10], r9
0x14003d568  mov     rcx, 174h
0x14003d56f  call    cs:__imp_IsWin32KSyscallFiltered
0x14003d576  nop     dword ptr [rax+rax+00h]
0x14003d57b  test    al, al
0x14003d57d  jz      short loc_14003D5D3
0x14003d57f  lea     rcx, aNtdxgkvailprom; "NtDxgkVailPromoteCompositionSurface"
0x14003d586  mov     rdx, 174h
0x14003d58d  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x14003d594  nop     dword ptr [rax+rax+00h]
0x14003d599  call    cs:__imp_PsIsWin32KFilterEnabled
0x14003d5a0  nop     dword ptr [rax+rax+00h]
0x14003d5a5  test    al, al
0x14003d5a7  jz      short loc_14003D5D3
0x14003d5a9  lea     rcx, W32pServiceTableFilter
0x14003d5b0  mov     edx, cs:W32pServiceLimitFilter
0x14003d5b6  mov     rax, 174h
0x14003d5bd  lea     rcx, [rcx+rdx*4]
0x14003d5c1  movsx   eax, byte ptr [rcx+rax]
0x14003d5c5  or      eax, eax
0x14003d5c7  jle     short loc_14003D5CE
0x14003d5c9  mov     eax, 0C000001Ch
0x14003d5ce  add     rsp, 48h
0x14003d5d2  retn
0x14003d5d3  mov     rax, cs:__imp_NtDxgkVailPromoteCompositionSurface
0x14003d5da  mov     rcx, [rsp+48h+var_28]
0x14003d5df  mov     rdx, [rsp+48h+var_20]
0x14003d5e4  mov     r8, [rsp+48h+var_18]
0x14003d5e9  mov     r9, [rsp+48h+var_10]
0x14003d5ee  add     rsp, 48h
0x14003d5f2  jmp     rax
```
