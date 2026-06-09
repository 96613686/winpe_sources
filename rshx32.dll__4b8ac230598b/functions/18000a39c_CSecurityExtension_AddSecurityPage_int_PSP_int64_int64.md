# CSecurityExtension::_AddSecurityPage(int (*)(_PSP *,__int64),__int64)

- ea: `0x18000a39c`
- end: `0x18000a438`
- name: `?_AddSecurityPage@CSecurityExtension@@AEAAJP6AHPEAU_PSP@@_J@Z1@Z`
- size: `156`
- prototype: `__int64 __fastcall(CSecurityExtension *this, unsigned int (__fastcall *)(HPROPSHEETPAGE, __int64), __int64)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180008d90`
- `0x18000a0e4`

## callees

- `0x18000a39c`
- `0x18000a66c`
- `0x18001e010`

## import_xrefs

- `COMCTL32!DestroyPropertySheetPage` at `0x18000a3f7`
- `COMCTL32!DestroyPropertySheetPage` at `0x18000a3f7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a3ff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a3ff`
- `ACLUI!__imp_CreateSecurityPage` at `0x18000a3d4`
- `ACLUI!__imp_CreateSecurityPage` at `0x18000a3d4`

## pseudocode

```c
__int64 __fastcall CSecurityExtension::_AddSecurityPage(
        CSecurityExtension *this,
        unsigned int (__fastcall *a2)(HPROPSHEETPAGE, __int64),
        __int64 a3)
{
  signed int v5; // ebx
  LPSECURITYINFO v6; // rsi
  HPROPSHEETPAGE SecurityPage; // rax
  struct _PSP *v8; // rdi
  signed int LastError; // eax
  LPSECURITYINFO psi; // [rsp+58h] [rbp+20h] BYREF

  psi = 0;
  v5 = CSecurityExtension::_CreateSI(this, &psi);
  if ( v5 >= 0 )
  {
    v6 = psi;
    SecurityPage = CreateSecurityPage(psi);
    v8 = SecurityPage;
    if ( SecurityPage )
    {
      if ( !a2(SecurityPage, a3) )
        DestroyPropertySheetPage(v8);
    }
    else
    {
      LastError = GetLastError();
      v5 = LastError;
      if ( LastError > 0 )
        v5 = (unsigned __int16)LastError | 0x80070000;
    }
    ((void (__fastcall *)(LPSECURITYINFO))v6->lpVtbl->Release)(v6);
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18000a39c  mov     rax, rsp
0x18000a39f  mov     [rax+8], rbx
0x18000a3a3  mov     [rax+10h], rbp
0x18000a3a7  push    rsi
0x18000a3a8  push    rdi
0x18000a3a9  push    r14
0x18000a3ab  sub     rsp, 20h
0x18000a3af  mov     r14, rdx
0x18000a3b2  mov     qword ptr [rax+20h], 0
0x18000a3ba  lea     rdx, [rax+20h]; struct ISecurityInformation **
0x18000a3be  mov     rbp, r8
0x18000a3c1  call    ?_CreateSI@CSecurityExtension@@AEAAJPEAPEAUISecurityInformation@@@Z; CSecurityExtension::_CreateSI(ISecurityInformation * *)
0x18000a3c6  mov     ebx, eax
0x18000a3c8  test    eax, eax
0x18000a3ca  js      short loc_18000A423
0x18000a3cc  mov     rsi, [rsp+38h+psi]
0x18000a3d1  mov     rcx, rsi; psi
0x18000a3d4  call    cs:__imp_CreateSecurityPage
0x18000a3da  mov     rdi, rax
0x18000a3dd  test    rax, rax
0x18000a3e0  jz      short loc_18000A3FF
0x18000a3e2  mov     rcx, rax
0x18000a3e5  mov     rdx, rbp
0x18000a3e8  mov     rax, r14
0x18000a3eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a3f0  test    eax, eax
0x18000a3f2  jnz     short loc_18000A414
0x18000a3f4  mov     rcx, rdi; HPROPSHEETPAGE
0x18000a3f7  call    cs:__imp_DestroyPropertySheetPage
0x18000a3fd  jmp     short loc_18000A414
0x18000a3ff  call    cs:__imp_GetLastError
0x18000a405  mov     ebx, eax
0x18000a407  test    eax, eax
0x18000a409  jle     short loc_18000A414
0x18000a40b  movzx   ebx, ax
0x18000a40e  or      ebx, 80070000h
0x18000a414  mov     rax, [rsi]
0x18000a417  mov     rcx, rsi
0x18000a41a  mov     rax, [rax+10h]
0x18000a41e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a423  mov     rbp, [rsp+38h+arg_8]
0x18000a428  mov     eax, ebx
0x18000a42a  mov     rbx, [rsp+38h+arg_0]
0x18000a42f  add     rsp, 20h
0x18000a433  pop     r14
0x18000a435  pop     rdi
0x18000a436  pop     rsi
0x18000a437  retn
```
