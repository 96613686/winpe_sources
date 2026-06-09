# _stub_SetCompositionSurfaceIndependentFlipInfo

- ea: `0x140055610`
- end: `0x1400556b7`
- name: `_stub_SetCompositionSurfaceIndependentFlipInfo`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x140055610`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140055659`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140055659`
- `ext-ms-win-core-win32k-surfmgr-l1-1-1!NtSetCompositionSurfaceIndependentFlipInfo` at `0x140055693`

## string_xrefs

- `0x14005563f`: `NtSetCompositionSurfaceIndependentFlipInfo`

## pseudocode

```c
__int64 __fastcall stub_SetCompositionSurfaceIndependentFlipInfo(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 result; // rax

  if ( !(unsigned __int8)IsWin32KSyscallFiltered() )
    return NtSetCompositionSurfaceIndependentFlipInfo(a1, a2, a3, a4);
  NtUserWin32kSysCallFilterStub();
  if ( !(unsigned __int8)PsIsWin32KFilterEnabled() )
    return NtSetCompositionSurfaceIndependentFlipInfo(a1, a2, a3, a4);
  result = (unsigned int)*((char *)&W32pServiceTableFilter[116] + 4 * (unsigned int)W32pServiceLimitFilter + 1);
  if ( (int)result > 0 )
    return 3221225500LL;
  return result;
}

```

## disassembly

```asm
0x140055610  sub     rsp, 48h
0x140055614  mov     [rsp+48h+var_28], rcx
0x140055619  mov     [rsp+48h+var_20], rdx
0x14005561e  mov     [rsp+48h+var_18], r8
0x140055623  mov     [rsp+48h+var_10], r9
0x140055628  mov     rcx, 3A1h
0x14005562f  call    cs:__imp_IsWin32KSyscallFiltered
0x140055636  nop     dword ptr [rax+rax+00h]
0x14005563b  test    al, al
0x14005563d  jz      short loc_140055693
0x14005563f  lea     rcx, aNtsetcompositi_1; "NtSetCompositionSurfaceIndependentFlipI"...
0x140055646  mov     rdx, 3A1h
0x14005564d  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x140055654  nop     dword ptr [rax+rax+00h]
0x140055659  call    cs:__imp_PsIsWin32KFilterEnabled
0x140055660  nop     dword ptr [rax+rax+00h]
0x140055665  test    al, al
0x140055667  jz      short loc_140055693
0x140055669  lea     rcx, W32pServiceTableFilter
0x140055670  mov     edx, cs:W32pServiceLimitFilter
0x140055676  mov     rax, 3A1h
0x14005567d  lea     rcx, [rcx+rdx*4]
0x140055681  movsx   eax, byte ptr [rcx+rax]
0x140055685  or      eax, eax
0x140055687  jle     short loc_14005568E
0x140055689  mov     eax, 0C000001Ch
0x14005568e  add     rsp, 48h
0x140055692  retn
0x140055693  mov     rax, cs:__imp_NtSetCompositionSurfaceIndependentFlipInfo
0x14005569a  mov     rcx, [rsp+48h+var_28]
0x14005569f  mov     rdx, [rsp+48h+var_20]
0x1400556a4  mov     r8, [rsp+48h+var_18]
0x1400556a9  mov     r9, [rsp+48h+var_10]
0x1400556ae  add     rsp, 48h
0x1400556b2  jmp     rax
```
