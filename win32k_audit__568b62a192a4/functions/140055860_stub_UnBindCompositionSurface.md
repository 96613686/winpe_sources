# _stub_UnBindCompositionSurface

- ea: `0x140055860`
- end: `0x140055907`
- name: `_stub_UnBindCompositionSurface`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x140055860`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x1400558a9`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x1400558a9`
- `ext-ms-win-core-win32k-surfmgr-l1-1-1!NtUnBindCompositionSurface` at `0x1400558e3`

## string_xrefs

- `0x14005588f`: `NtUnBindCompositionSurface`

## pseudocode

```c
__int64 __fastcall stub_UnBindCompositionSurface(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 result; // rax

  if ( !(unsigned __int8)IsWin32KSyscallFiltered() )
    return NtUnBindCompositionSurface(a1, a2, a3, a4);
  NtUserWin32kSysCallFilterStub();
  if ( !(unsigned __int8)PsIsWin32KFilterEnabled() )
    return NtUnBindCompositionSurface(a1, a2, a3, a4);
  result = (unsigned int)*((char *)&W32pServiceTableFilter[116] + 4 * (unsigned int)W32pServiceLimitFilter + 7);
  if ( (int)result > 0 )
    return 3221225500LL;
  return result;
}

```

## disassembly

```asm
0x140055860  sub     rsp, 48h
0x140055864  mov     [rsp+48h+var_28], rcx
0x140055869  mov     [rsp+48h+var_20], rdx
0x14005586e  mov     [rsp+48h+var_18], r8
0x140055873  mov     [rsp+48h+var_10], r9
0x140055878  mov     rcx, 3A7h
0x14005587f  call    cs:__imp_IsWin32KSyscallFiltered
0x140055886  nop     dword ptr [rax+rax+00h]
0x14005588b  test    al, al
0x14005588d  jz      short loc_1400558E3
0x14005588f  lea     rcx, aNtunbindcompos; "NtUnBindCompositionSurface"
0x140055896  mov     rdx, 3A7h
0x14005589d  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x1400558a4  nop     dword ptr [rax+rax+00h]
0x1400558a9  call    cs:__imp_PsIsWin32KFilterEnabled
0x1400558b0  nop     dword ptr [rax+rax+00h]
0x1400558b5  test    al, al
0x1400558b7  jz      short loc_1400558E3
0x1400558b9  lea     rcx, W32pServiceTableFilter
0x1400558c0  mov     edx, cs:W32pServiceLimitFilter
0x1400558c6  mov     rax, 3A7h
0x1400558cd  lea     rcx, [rcx+rdx*4]
0x1400558d1  movsx   eax, byte ptr [rcx+rax]
0x1400558d5  or      eax, eax
0x1400558d7  jle     short loc_1400558DE
0x1400558d9  mov     eax, 0C000001Ch
0x1400558de  add     rsp, 48h
0x1400558e2  retn
0x1400558e3  mov     rax, cs:__imp_NtUnBindCompositionSurface
0x1400558ea  mov     rcx, [rsp+48h+var_28]
0x1400558ef  mov     rdx, [rsp+48h+var_20]
0x1400558f4  mov     r8, [rsp+48h+var_18]
0x1400558f9  mov     r9, [rsp+48h+var_10]
0x1400558fe  add     rsp, 48h
0x140055902  jmp     rax
```
