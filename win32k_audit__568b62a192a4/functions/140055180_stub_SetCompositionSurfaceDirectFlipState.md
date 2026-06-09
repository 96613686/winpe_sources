# _stub_SetCompositionSurfaceDirectFlipState

- ea: `0x140055180`
- end: `0x140055227`
- name: `_stub_SetCompositionSurfaceDirectFlipState`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x140055180`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x1400551c9`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x1400551c9`
- `ext-ms-win-core-win32k-surfmgr-l1-1-1!NtSetCompositionSurfaceDirectFlipState` at `0x140055203`

## string_xrefs

- `0x1400551af`: `NtSetCompositionSurfaceDirectFlipState`

## pseudocode

```c
__int64 __fastcall stub_SetCompositionSurfaceDirectFlipState(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 result; // rax

  if ( !(unsigned __int8)IsWin32KSyscallFiltered() )
    return NtSetCompositionSurfaceDirectFlipState(a1, a2, a3, a4);
  NtUserWin32kSysCallFilterStub();
  if ( !(unsigned __int8)PsIsWin32KFilterEnabled() )
    return NtSetCompositionSurfaceDirectFlipState(a1, a2, a3, a4);
  result = (unsigned int)*((char *)&W32pServiceTableFilter[115] + 4 * (unsigned int)W32pServiceLimitFilter + 5);
  if ( (int)result > 0 )
    return 3221225500LL;
  return result;
}

```

## disassembly

```asm
0x140055180  sub     rsp, 48h
0x140055184  mov     [rsp+48h+var_28], rcx
0x140055189  mov     [rsp+48h+var_20], rdx
0x14005518e  mov     [rsp+48h+var_18], r8
0x140055193  mov     [rsp+48h+var_10], r9
0x140055198  mov     rcx, 39Dh
0x14005519f  call    cs:__imp_IsWin32KSyscallFiltered
0x1400551a6  nop     dword ptr [rax+rax+00h]
0x1400551ab  test    al, al
0x1400551ad  jz      short loc_140055203
0x1400551af  lea     rcx, aNtsetcompositi_0; "NtSetCompositionSurfaceDirectFlipState"
0x1400551b6  mov     rdx, 39Dh
0x1400551bd  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x1400551c4  nop     dword ptr [rax+rax+00h]
0x1400551c9  call    cs:__imp_PsIsWin32KFilterEnabled
0x1400551d0  nop     dword ptr [rax+rax+00h]
0x1400551d5  test    al, al
0x1400551d7  jz      short loc_140055203
0x1400551d9  lea     rcx, W32pServiceTableFilter
0x1400551e0  mov     edx, cs:W32pServiceLimitFilter
0x1400551e6  mov     rax, 39Dh
0x1400551ed  lea     rcx, [rcx+rdx*4]
0x1400551f1  movsx   eax, byte ptr [rcx+rax]
0x1400551f5  or      eax, eax
0x1400551f7  jle     short loc_1400551FE
0x1400551f9  mov     eax, 0C000001Ch
0x1400551fe  add     rsp, 48h
0x140055202  retn
0x140055203  mov     rax, cs:__imp_NtSetCompositionSurfaceDirectFlipState
0x14005520a  mov     rcx, [rsp+48h+var_28]
0x14005520f  mov     rdx, [rsp+48h+var_20]
0x140055214  mov     r8, [rsp+48h+var_18]
0x140055219  mov     r9, [rsp+48h+var_10]
0x14005521e  add     rsp, 48h
0x140055222  jmp     rax
```
