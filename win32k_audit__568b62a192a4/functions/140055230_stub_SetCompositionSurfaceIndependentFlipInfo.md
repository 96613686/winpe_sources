# _stub_SetCompositionSurfaceIndependentFlipInfo

- ea: `0x140055230`
- end: `0x1400552d7`
- name: `_stub_SetCompositionSurfaceIndependentFlipInfo`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x140055230`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140055279`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140055279`
- `ext-ms-win-core-win32k-surfmgr-l1-1-1!NtSetCompositionSurfaceIndependentFlipInfo` at `0x1400552b3`

## string_xrefs

- `0x14005525f`: `NtSetCompositionSurfaceIndependentFlipInfo`

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
  result = (unsigned int)*((char *)&W32pServiceTableFilter[115] + 4 * (unsigned int)W32pServiceLimitFilter + 6);
  if ( (int)result > 0 )
    return 3221225500LL;
  return result;
}

```

## disassembly

```asm
0x140055230  sub     rsp, 48h
0x140055234  mov     [rsp+48h+var_28], rcx
0x140055239  mov     [rsp+48h+var_20], rdx
0x14005523e  mov     [rsp+48h+var_18], r8
0x140055243  mov     [rsp+48h+var_10], r9
0x140055248  mov     rcx, 39Eh
0x14005524f  call    cs:__imp_IsWin32KSyscallFiltered
0x140055256  nop     dword ptr [rax+rax+00h]
0x14005525b  test    al, al
0x14005525d  jz      short loc_1400552B3
0x14005525f  lea     rcx, aNtsetcompositi_1; "NtSetCompositionSurfaceIndependentFlipI"...
0x140055266  mov     rdx, 39Eh
0x14005526d  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x140055274  nop     dword ptr [rax+rax+00h]
0x140055279  call    cs:__imp_PsIsWin32KFilterEnabled
0x140055280  nop     dword ptr [rax+rax+00h]
0x140055285  test    al, al
0x140055287  jz      short loc_1400552B3
0x140055289  lea     rcx, W32pServiceTableFilter
0x140055290  mov     edx, cs:W32pServiceLimitFilter
0x140055296  mov     rax, 39Eh
0x14005529d  lea     rcx, [rcx+rdx*4]
0x1400552a1  movsx   eax, byte ptr [rcx+rax]
0x1400552a5  or      eax, eax
0x1400552a7  jle     short loc_1400552AE
0x1400552a9  mov     eax, 0C000001Ch
0x1400552ae  add     rsp, 48h
0x1400552b2  retn
0x1400552b3  mov     rax, cs:__imp_NtSetCompositionSurfaceIndependentFlipInfo
0x1400552ba  mov     rcx, [rsp+48h+var_28]
0x1400552bf  mov     rdx, [rsp+48h+var_20]
0x1400552c4  mov     r8, [rsp+48h+var_18]
0x1400552c9  mov     r9, [rsp+48h+var_10]
0x1400552ce  add     rsp, 48h
0x1400552d2  jmp     rax
```
