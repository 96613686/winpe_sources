# _stub_OpenCompositionSurfaceDirtyRegion

- ea: `0x140053760`
- end: `0x140053807`
- name: `_stub_OpenCompositionSurfaceDirtyRegion`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x140053760`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x1400537a9`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x1400537a9`
- `ext-ms-win-core-win32k-surfmgr-l1-1-1!NtOpenCompositionSurfaceDirtyRegion` at `0x1400537e3`

## string_xrefs

- `0x14005378f`: `NtOpenCompositionSurfaceDirtyRegion`

## pseudocode

```c
__int64 __fastcall stub_OpenCompositionSurfaceDirtyRegion(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 result; // rax

  if ( !(unsigned __int8)IsWin32KSyscallFiltered() )
    return NtOpenCompositionSurfaceDirtyRegion(a1, a2, a3, a4);
  NtUserWin32kSysCallFilterStub();
  if ( !(unsigned __int8)PsIsWin32KFilterEnabled() )
    return NtOpenCompositionSurfaceDirtyRegion(a1, a2, a3, a4);
  result = (unsigned int)*((char *)&W32pServiceTableFilter[110] + 4 * (unsigned int)W32pServiceLimitFilter + 7);
  if ( (int)result > 0 )
    return 3221225500LL;
  return result;
}

```

## disassembly

```asm
0x140053760  sub     rsp, 48h
0x140053764  mov     [rsp+48h+var_28], rcx
0x140053769  mov     [rsp+48h+var_20], rdx
0x14005376e  mov     [rsp+48h+var_18], r8
0x140053773  mov     [rsp+48h+var_10], r9
0x140053778  mov     rcx, 377h
0x14005377f  call    cs:__imp_IsWin32KSyscallFiltered
0x140053786  nop     dword ptr [rax+rax+00h]
0x14005378b  test    al, al
0x14005378d  jz      short loc_1400537E3
0x14005378f  lea     rcx, aNtopencomposit; "NtOpenCompositionSurfaceDirtyRegion"
0x140053796  mov     rdx, 377h
0x14005379d  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x1400537a4  nop     dword ptr [rax+rax+00h]
0x1400537a9  call    cs:__imp_PsIsWin32KFilterEnabled
0x1400537b0  nop     dword ptr [rax+rax+00h]
0x1400537b5  test    al, al
0x1400537b7  jz      short loc_1400537E3
0x1400537b9  lea     rcx, W32pServiceTableFilter
0x1400537c0  mov     edx, cs:W32pServiceLimitFilter
0x1400537c6  mov     rax, 377h
0x1400537cd  lea     rcx, [rcx+rdx*4]
0x1400537d1  movsx   eax, byte ptr [rcx+rax]
0x1400537d5  or      eax, eax
0x1400537d7  jle     short loc_1400537DE
0x1400537d9  mov     eax, 0C000001Ch
0x1400537de  add     rsp, 48h
0x1400537e2  retn
0x1400537e3  mov     rax, cs:__imp_NtOpenCompositionSurfaceDirtyRegion
0x1400537ea  mov     rcx, [rsp+48h+var_28]
0x1400537ef  mov     rdx, [rsp+48h+var_20]
0x1400537f4  mov     r8, [rsp+48h+var_18]
0x1400537f9  mov     r9, [rsp+48h+var_10]
0x1400537fe  add     rsp, 48h
0x140053802  jmp     rax
```
