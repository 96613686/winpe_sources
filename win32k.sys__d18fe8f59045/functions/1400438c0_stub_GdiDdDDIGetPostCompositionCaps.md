# _stub_GdiDdDDIGetPostCompositionCaps

- ea: `0x1400438c0`
- end: `0x140043967`
- name: `_stub_GdiDdDDIGetPostCompositionCaps`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x1400438c0`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140043909`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140043909`
- `ext-ms-win-core-win32k-dxgk-l1-1-0!NtGdiDdDDIGetPostCompositionCaps` at `0x140043943`

## string_xrefs

- `0x1400438ef`: `NtGdiDdDDIGetPostCompositionCaps`

## pseudocode

```c
__int64 __fastcall stub_GdiDdDDIGetPostCompositionCaps(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 result; // rax

  if ( !(unsigned __int8)IsWin32KSyscallFiltered() )
    return NtGdiDdDDIGetPostCompositionCaps(a1, a2, a3, a4);
  NtUserWin32kSysCallFilterStub();
  if ( !(unsigned __int8)PsIsWin32KFilterEnabled() )
    return NtGdiDdDDIGetPostCompositionCaps(a1, a2, a3, a4);
  result = (unsigned int)*((char *)&W32pServiceTableFilter[64] + 4 * (unsigned int)W32pServiceLimitFilter + 2);
  if ( (int)result > 0 )
    return 3221225500LL;
  return result;
}

```

## disassembly

```asm
0x1400438c0  sub     rsp, 48h
0x1400438c4  mov     [rsp+48h+var_28], rcx
0x1400438c9  mov     [rsp+48h+var_20], rdx
0x1400438ce  mov     [rsp+48h+var_18], r8
0x1400438d3  mov     [rsp+48h+var_10], r9
0x1400438d8  mov     rcx, 202h
0x1400438df  call    cs:__imp_IsWin32KSyscallFiltered
0x1400438e6  nop     dword ptr [rax+rax+00h]
0x1400438eb  test    al, al
0x1400438ed  jz      short loc_140043943
0x1400438ef  lea     rcx, aNtgdiddddigetp; "NtGdiDdDDIGetPostCompositionCaps"
0x1400438f6  mov     rdx, 202h
0x1400438fd  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x140043904  nop     dword ptr [rax+rax+00h]
0x140043909  call    cs:__imp_PsIsWin32KFilterEnabled
0x140043910  nop     dword ptr [rax+rax+00h]
0x140043915  test    al, al
0x140043917  jz      short loc_140043943
0x140043919  lea     rcx, W32pServiceTableFilter
0x140043920  mov     edx, cs:W32pServiceLimitFilter
0x140043926  mov     rax, 202h
0x14004392d  lea     rcx, [rcx+rdx*4]
0x140043931  movsx   eax, byte ptr [rcx+rax]
0x140043935  or      eax, eax
0x140043937  jle     short loc_14004393E
0x140043939  mov     eax, 0C000001Ch
0x14004393e  add     rsp, 48h
0x140043942  retn
0x140043943  mov     rax, cs:__imp_NtGdiDdDDIGetPostCompositionCaps
0x14004394a  mov     rcx, [rsp+48h+var_28]
0x14004394f  mov     rdx, [rsp+48h+var_20]
0x140043954  mov     r8, [rsp+48h+var_18]
0x140043959  mov     r9, [rsp+48h+var_10]
0x14004395e  add     rsp, 48h
0x140043962  jmp     rax
```
