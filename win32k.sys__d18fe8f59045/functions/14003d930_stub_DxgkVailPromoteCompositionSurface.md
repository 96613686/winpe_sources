# _stub_DxgkVailPromoteCompositionSurface

- ea: `0x14003d930`
- end: `0x14003d9d7`
- name: `_stub_DxgkVailPromoteCompositionSurface`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x14003d930`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x14003d979`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x14003d979`
- `ext-ms-win-core-win32k-dxgk-l1-1-0!NtDxgkVailPromoteCompositionSurface` at `0x14003d9b3`

## string_xrefs

- `0x14003d95f`: `NtDxgkVailPromoteCompositionSurface`

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
  result = (unsigned int)*((char *)&W32pServiceTableFilter[46] + 4 * (unsigned int)W32pServiceLimitFilter + 7);
  if ( (int)result > 0 )
    return 3221225500LL;
  return result;
}

```

## disassembly

```asm
0x14003d930  sub     rsp, 48h
0x14003d934  mov     [rsp+48h+var_28], rcx
0x14003d939  mov     [rsp+48h+var_20], rdx
0x14003d93e  mov     [rsp+48h+var_18], r8
0x14003d943  mov     [rsp+48h+var_10], r9
0x14003d948  mov     rcx, 177h
0x14003d94f  call    cs:__imp_IsWin32KSyscallFiltered
0x14003d956  nop     dword ptr [rax+rax+00h]
0x14003d95b  test    al, al
0x14003d95d  jz      short loc_14003D9B3
0x14003d95f  lea     rcx, aNtdxgkvailprom; "NtDxgkVailPromoteCompositionSurface"
0x14003d966  mov     rdx, 177h
0x14003d96d  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x14003d974  nop     dword ptr [rax+rax+00h]
0x14003d979  call    cs:__imp_PsIsWin32KFilterEnabled
0x14003d980  nop     dword ptr [rax+rax+00h]
0x14003d985  test    al, al
0x14003d987  jz      short loc_14003D9B3
0x14003d989  lea     rcx, W32pServiceTableFilter
0x14003d990  mov     edx, cs:W32pServiceLimitFilter
0x14003d996  mov     rax, 177h
0x14003d99d  lea     rcx, [rcx+rdx*4]
0x14003d9a1  movsx   eax, byte ptr [rcx+rax]
0x14003d9a5  or      eax, eax
0x14003d9a7  jle     short loc_14003D9AE
0x14003d9a9  mov     eax, 0C000001Ch
0x14003d9ae  add     rsp, 48h
0x14003d9b2  retn
0x14003d9b3  mov     rax, cs:__imp_NtDxgkVailPromoteCompositionSurface
0x14003d9ba  mov     rcx, [rsp+48h+var_28]
0x14003d9bf  mov     rdx, [rsp+48h+var_20]
0x14003d9c4  mov     r8, [rsp+48h+var_18]
0x14003d9c9  mov     r9, [rsp+48h+var_10]
0x14003d9ce  add     rsp, 48h
0x14003d9d2  jmp     rax
```
