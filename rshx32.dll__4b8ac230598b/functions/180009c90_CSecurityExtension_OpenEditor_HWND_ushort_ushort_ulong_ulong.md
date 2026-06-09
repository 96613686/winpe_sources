# CSecurityExtension::OpenEditor(HWND__ *,ushort *,ushort *,ulong,ulong)

- ea: `0x180009c90`
- end: `0x180009dd1`
- name: `?OpenEditor@CSecurityExtension@@UEAAJPEAUHWND__@@PEAG1KK@Z`
- size: `321`
- prototype: `__int64 __fastcall(CSecurityExtension *this, HWND, unsigned __int16 *, unsigned __int16 *, unsigned int, SI_PAGE_TYPE uSIPage)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180009c90`
- `0x18000a440`
- `0x18000a66c`
- `0x18001654c`
- `0x18001e010`

## import_xrefs

- `USER32!SetProcessDPIAware` at `0x180009d4a`
- `USER32!SetProcessDPIAware` at `0x180009d4a`
- `ACLUI!__imp_EditSecurity` at `0x180009d67`
- `ACLUI!__imp_EditSecurity` at `0x180009d67`
- `ACLUI!__imp_EditSecurityAdvanced` at `0x180009d99`
- `ACLUI!__imp_EditSecurityAdvanced` at `0x180009d99`

## pseudocode

```c
__int64 __fastcall CSecurityExtension::OpenEditor(
        CSecurityExtension *this,
        HWND a2,
        unsigned __int16 *a3,
        unsigned __int16 *a4,
        unsigned int a5,
        SI_PAGE_TYPE uSIPage)
{
  ISecurityInformation *v6; // rdi
  int v10; // ebx
  int v11; // eax
  unsigned int v12; // esi
  int v13; // eax
  ISecurityInformation *v14; // rdx
  HWND v15; // rcx
  SI_PAGE_TYPE v16; // r8d
  LPSECURITYINFO psi; // [rsp+60h] [rbp+18h] BYREF

  v6 = 0;
  psi = 0;
  if ( a3 && a4 )
  {
    v10 = *((_DWORD *)this + 6);
    if ( v10 == -1 )
    {
      v10 = LocalAllocString((unsigned __int16 **)this + 6, a3);
      if ( v10 < 0 )
        return (unsigned int)v10;
      v10 = LocalAllocString((unsigned __int16 **)this + 5, a4);
      if ( v10 < 0 )
        return (unsigned int)v10;
      v10 = CSecurityExtension::_CheckForSecurity((CSecurityExtension *)((char *)this - 16), a5);
      *((_DWORD *)this + 6) = v10;
    }
    if ( v10 < 0 )
      return (unsigned int)v10;
    v11 = CSecurityExtension::_CreateSI((CSecurityExtension *)((char *)this - 16), &psi);
    v6 = psi;
    v10 = v11;
    if ( v11 >= 0 )
    {
      v12 = uSIPage;
      ((void (__fastcall *)(LPSECURITYINFO, HWND, __int64, _QWORD))psi->lpVtbl->PropertySheetPageCallback)(
        psi,
        a2,
        1025,
        (unsigned int)uSIPage);
      SetProcessDPIAware();
      v13 = *((_DWORD *)this + 16);
      if ( v12 )
      {
        if ( v13 && (_WORD)v12 != 3 && (v12 & 0xFFFF0000) == 0 )
          v12 = 5;
        v16 = v12;
        v14 = v6;
        v15 = a2;
      }
      else
      {
        v14 = v6;
        v15 = a2;
        if ( !v13 )
        {
          if ( !EditSecurity(a2, v6) )
            v10 = -2147467259;
          goto LABEL_21;
        }
        v16 = SI_PAGE_TAKEOWNERSHIP;
      }
      v10 = EditSecurityAdvanced(v15, v14, v16);
    }
  }
  else
  {
    v10 = -2147467261;
  }
LABEL_21:
  if ( v6 )
    ((void (__fastcall *)(ISecurityInformation *))v6->lpVtbl->Release)(v6);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180009c90  mov     [rsp+arg_0], rbx
0x180009c95  mov     [rsp+arg_8], rbp
0x180009c9a  push    rsi
0x180009c9b  push    rdi
0x180009c9c  push    r14
0x180009c9e  sub     rsp, 30h
0x180009ca2  xor     edi, edi
0x180009ca4  mov     rsi, r9
0x180009ca7  mov     [rsp+48h+psi], rdi
0x180009cac  mov     r14, rdx
0x180009caf  mov     rbp, rcx
0x180009cb2  test    r8, r8
0x180009cb5  jz      loc_180009DA3
0x180009cbb  test    r9, r9
0x180009cbe  jz      loc_180009DA3
0x180009cc4  mov     ebx, [rcx+18h]
0x180009cc7  cmp     ebx, 0FFFFFFFFh
0x180009cca  jnz     short loc_180009D0A
0x180009ccc  add     rcx, 30h ; '0'; unsigned __int16 **
0x180009cd0  mov     rdx, r8; unsigned __int16 *
0x180009cd3  call    ?LocalAllocString@@YAJPEAPEAGPEBG@Z; LocalAllocString(ushort * *,ushort const *)
0x180009cd8  mov     ebx, eax
0x180009cda  test    eax, eax
0x180009cdc  js      loc_180009DBC
0x180009ce2  lea     rcx, [rbp+28h]; unsigned __int16 **
0x180009ce6  mov     rdx, rsi; unsigned __int16 *
0x180009ce9  call    ?LocalAllocString@@YAJPEAPEAGPEBG@Z; LocalAllocString(ushort * *,ushort const *)
0x180009cee  mov     ebx, eax
0x180009cf0  test    eax, eax
0x180009cf2  js      loc_180009DBC
0x180009cf8  mov     edx, [rsp+48h+arg_20]; unsigned int
0x180009cfc  lea     rcx, [rbp-10h]; this
0x180009d00  call    ?_CheckForSecurity@CSecurityExtension@@AEAAJK@Z; CSecurityExtension::_CheckForSecurity(ulong)
0x180009d05  mov     ebx, eax
0x180009d07  mov     [rbp+18h], eax
0x180009d0a  test    ebx, ebx
0x180009d0c  js      loc_180009DBC
0x180009d12  lea     rdx, [rsp+48h+psi]; struct ISecurityInformation **
0x180009d17  lea     rcx, [rbp-10h]; this
0x180009d1b  call    ?_CreateSI@CSecurityExtension@@AEAAJPEAPEAUISecurityInformation@@@Z; CSecurityExtension::_CreateSI(ISecurityInformation * *)
0x180009d20  mov     rdi, [rsp+48h+psi]
0x180009d25  mov     ebx, eax
0x180009d27  test    eax, eax
0x180009d29  js      short loc_180009DA8
0x180009d2b  mov     rax, [rdi]
0x180009d2e  mov     r8d, 401h
0x180009d34  mov     esi, [rsp+48h+uSIPage]
0x180009d38  mov     rdx, r14
0x180009d3b  mov     r9d, esi
0x180009d3e  mov     rcx, rdi
0x180009d41  mov     rax, [rax+48h]
0x180009d45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009d4a  call    cs:__imp_SetProcessDPIAware
0x180009d50  mov     eax, [rbp+40h]
0x180009d53  test    esi, esi
0x180009d55  jnz     short loc_180009D78
0x180009d57  mov     rdx, rdi; psi
0x180009d5a  mov     rcx, r14; hwndOwner
0x180009d5d  test    eax, eax
0x180009d5f  jz      short loc_180009D67
0x180009d61  lea     r8d, [rsi+5]
0x180009d65  jmp     short loc_180009D99
0x180009d67  call    cs:__imp_EditSecurity
0x180009d6d  test    eax, eax
0x180009d6f  jnz     short loc_180009DA8
0x180009d71  mov     ebx, 80004005h
0x180009d76  jmp     short loc_180009DA8
0x180009d78  test    eax, eax
0x180009d7a  jz      short loc_180009D90
0x180009d7c  cmp     si, 3
0x180009d80  jz      short loc_180009D90
0x180009d82  test    esi, 0FFFF0000h
0x180009d88  mov     eax, 5
0x180009d8d  cmovz   esi, eax
0x180009d90  mov     r8d, esi; uSIPage
0x180009d93  mov     rdx, rdi; psi
0x180009d96  mov     rcx, r14; hwndOwner
0x180009d99  call    cs:__imp_EditSecurityAdvanced
0x180009d9f  mov     ebx, eax
0x180009da1  jmp     short loc_180009DA8
0x180009da3  mov     ebx, 80004003h
0x180009da8  test    rdi, rdi
0x180009dab  jz      short loc_180009DBC
0x180009dad  mov     rax, [rdi]
0x180009db0  mov     rcx, rdi
0x180009db3  mov     rax, [rax+10h]
0x180009db7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009dbc  mov     rbp, [rsp+48h+arg_8]
0x180009dc1  mov     eax, ebx
0x180009dc3  mov     rbx, [rsp+48h+arg_0]
0x180009dc8  add     rsp, 30h
0x180009dcc  pop     r14
0x180009dce  pop     rdi
0x180009dcf  pop     rsi
0x180009dd0  retn
```
