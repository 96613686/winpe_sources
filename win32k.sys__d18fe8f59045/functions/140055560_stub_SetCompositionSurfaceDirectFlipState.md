# _stub_SetCompositionSurfaceDirectFlipState

- ea: `0x140055560`
- end: `0x140055607`
- name: `_stub_SetCompositionSurfaceDirectFlipState`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x140055560`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x1400555a9`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x1400555a9`
- `ext-ms-win-core-win32k-surfmgr-l1-1-1!NtSetCompositionSurfaceDirectFlipState` at `0x1400555e3`

## string_xrefs

- `0x14005558f`: `NtSetCompositionSurfaceDirectFlipState`

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
  result = (unsigned int)*((char *)&W32pServiceTableFilter[116] + 4 * (unsigned int)W32pServiceLimitFilter);
  if ( (int)result > 0 )
    return 3221225500LL;
  return result;
}

```

## disassembly

```asm
0x140055560  sub     rsp, 48h
0x140055564  mov     [rsp+48h+var_28], rcx
0x140055569  mov     [rsp+48h+var_20], rdx
0x14005556e  mov     [rsp+48h+var_18], r8
0x140055573  mov     [rsp+48h+var_10], r9
0x140055578  mov     rcx, 3A0h
0x14005557f  call    cs:__imp_IsWin32KSyscallFiltered
0x140055586  nop     dword ptr [rax+rax+00h]
0x14005558b  test    al, al
0x14005558d  jz      short loc_1400555E3
0x14005558f  lea     rcx, aNtsetcompositi_0; "NtSetCompositionSurfaceDirectFlipState"
0x140055596  mov     rdx, 3A0h
0x14005559d  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x1400555a4  nop     dword ptr [rax+rax+00h]
0x1400555a9  call    cs:__imp_PsIsWin32KFilterEnabled
0x1400555b0  nop     dword ptr [rax+rax+00h]
0x1400555b5  test    al, al
0x1400555b7  jz      short loc_1400555E3
0x1400555b9  lea     rcx, W32pServiceTableFilter
0x1400555c0  mov     edx, cs:W32pServiceLimitFilter
0x1400555c6  mov     rax, 3A0h
0x1400555cd  lea     rcx, [rcx+rdx*4]
0x1400555d1  movsx   eax, byte ptr [rcx+rax]
0x1400555d5  or      eax, eax
0x1400555d7  jle     short loc_1400555DE
0x1400555d9  mov     eax, 0C000001Ch
0x1400555de  add     rsp, 48h
0x1400555e2  retn
0x1400555e3  mov     rax, cs:__imp_NtSetCompositionSurfaceDirectFlipState
0x1400555ea  mov     rcx, [rsp+48h+var_28]
0x1400555ef  mov     rdx, [rsp+48h+var_20]
0x1400555f4  mov     r8, [rsp+48h+var_18]
0x1400555f9  mov     r9, [rsp+48h+var_10]
0x1400555fe  add     rsp, 48h
0x140055602  jmp     rax
```
