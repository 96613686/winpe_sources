# CThemeFile::SetCursor(ushort *,ushort *)

- ea: `0x180018b20`
- end: `0x180018d65`
- name: `?SetCursor@CThemeFile@@UEAAJPEAG0@Z`
- size: `581`
- prototype: `__int64 __fastcall(CThemeFile *__hidden this, unsigned __int16 *, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1800089c0`
- `0x180018b20`
- `0x1800358c0`
- `0x18006d010`

## import_xrefs

- `SHLWAPI!StrStrW` at `0x180018c5e`
- `SHLWAPI!StrStrW` at `0x180018c5e`
- `SHLWAPI!PathIsRelativeW` at `0x180018c72`
- `SHLWAPI!PathIsRelativeW` at `0x180018c72`
- `SHLWAPI!__imp_PathUnExpandEnvStringsForUserW` at `0x180018d2a`
- `SHLWAPI!__imp_PathUnExpandEnvStringsForUserW` at `0x180018d2a`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180018b92`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180018b92`

## pseudocode

```c
__int64 __fastcall CThemeFile::SetCursor(CThemeFile *this, unsigned __int16 *a2, unsigned __int16 *a3)
{
  __int64 *v6; // rbx
  HRESULT v7; // edi
  __int64 v8; // rdx
  unsigned __int16 *v9; // r8
  __int64 v10; // rcx
  __int64 v11; // rcx
  WCHAR *v12; // rax
  WCHAR *v13; // rcx
  PWSTR v14; // rax
  __int64 v15; // rax
  LPVOID v16; // rcx
  int v18; // eax
  unsigned __int16 *v19; // rcx
  LPVOID ppv; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR pszFirst[264]; // [rsp+40h] [rbp-C0h] BYREF

  if ( !*((_QWORD *)this + 4) )
    return (unsigned int)-2147467259;
  v6 = (__int64 *)*((_QWORD *)this + 5);
  if ( v6 )
  {
    (*(void (__fastcall **)(_QWORD))(*v6 + 8))(*((_QWORD *)this + 5));
    v7 = 0;
    goto LABEL_9;
  }
  ppv = 0;
  v7 = CoCreateInstance(&CLSID_PrivateProfile, 0, 1u, &GUID_b57046bc_32e5_428a_9887_19f712b907bf, &ppv);
  if ( v7 >= 0 )
  {
    v7 = (*(__int64 (__fastcall **)(LPVOID, _QWORD, __int64))(*(_QWORD *)ppv + 24LL))(
           ppv,
           *((_QWORD *)this + 4),
           0x400000);
    if ( v7 < 0 )
    {
      v16 = ppv;
      v15 = *(_QWORD *)ppv;
LABEL_25:
      (*(void (__fastcall **)(LPVOID, __int64, unsigned __int16 *))(v15 + 16))(v16, v8, v9);
      return (unsigned int)v7;
    }
    v10 = *((_QWORD *)this + 5);
    if ( v10 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
    v6 = (__int64 *)ppv;
    *((_QWORD *)this + 5) = ppv;
    (*(void (__fastcall **)(__int64 *))(*v6 + 8))(v6);
LABEL_9:
    *((_BYTE *)this + 48) = 1;
    if ( a3 )
    {
      v11 = 2147483646;
      v12 = pszFirst;
      v9 = a3;
      v8 = 260;
      do
      {
        if ( !v11 )
          break;
        if ( !*v9 )
          break;
        *v12++ = *v9++;
        --v11;
        --v8;
      }
      while ( v8 );
      v13 = v12 - 1;
      if ( v8 )
        v13 = v12;
      *v13 = 0;
      if ( !v8 )
        goto LABEL_21;
      v14 = StrStrW(pszFirst, L",");
      if ( v14 )
        *v14 = 0;
      if ( !PathIsRelativeW(pszFirst) )
      {
        v18 = PathUnExpandEnvStringsForUserW(0, a3, pszFirst, 260);
        v19 = pszFirst;
        if ( !v18 )
          v19 = a3;
        a3 = v19;
      }
    }
    v7 = (*(__int64 (__fastcall **)(__int64 *, const WCHAR *, unsigned __int16 *, __int64, unsigned __int16 *))(*v6 + 80))(
           v6,
           L"Control Panel\\Cursors",
           a2,
           1,
           a3);
LABEL_21:
    if ( v7 >= 0 && (int)StringCchPrintfW(pszFirst, 0x104u, L"%s.MUI", a2) >= 0 )
      (*(void (__fastcall **)(__int64 *, const WCHAR *, WCHAR *, __int64, _QWORD))(*v6 + 80))(
        v6,
        L"Control Panel\\Cursors",
        pszFirst,
        1,
        0);
    v15 = *v6;
    v16 = v6;
    goto LABEL_25;
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180018b20  push    rbp
0x180018b22  push    rbx
0x180018b23  push    rsi
0x180018b24  push    rdi
0x180018b25  push    r12
0x180018b27  push    r14
0x180018b29  push    r15
0x180018b2b  lea     rbp, [rsp-160h]
0x180018b33  sub     rsp, 260h
0x180018b3a  mov     rax, cs:__security_cookie
0x180018b41  xor     rax, rsp
0x180018b44  mov     [rbp+190h+var_40], rax
0x180018b4b  xor     r12d, r12d
0x180018b4e  mov     r14, r8
0x180018b51  mov     r15, rdx
0x180018b54  mov     rsi, rcx
0x180018b57  cmp     [rcx+20h], r12
0x180018b5b  jz      loc_180018D5E
0x180018b61  mov     rbx, [rcx+28h]
0x180018b65  test    rbx, rbx
0x180018b68  jnz     loc_180018BEE
0x180018b6e  lea     rax, [rsp+290h+var_260]
0x180018b73  mov     [rsp+290h+var_260], r12
0x180018b78  lea     r9, _GUID_b57046bc_32e5_428a_9887_19f712b907bf; riid
0x180018b7f  mov     [rsp+290h+ppv], rax; ppv
0x180018b84  xor     edx, edx; pUnkOuter
0x180018b86  lea     r8d, [r12+1]; dwClsContext
0x180018b8b  lea     rcx, CLSID_PrivateProfile; rclsid
0x180018b92  call    cs:__imp_CoCreateInstance
0x180018b98  mov     edi, eax
0x180018b9a  test    eax, eax
0x180018b9c  js      loc_180018CFA
0x180018ba2  mov     rcx, [rsp+290h+var_260]
0x180018ba7  mov     r8d, 400000h
0x180018bad  mov     rdx, [rsi+20h]
0x180018bb1  mov     rax, [rcx]
0x180018bb4  mov     rax, [rax+18h]
0x180018bb8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018bbd  mov     edi, eax
0x180018bbf  test    eax, eax
0x180018bc1  js      loc_180018D43
0x180018bc7  mov     rcx, [rsi+28h]
0x180018bcb  test    rcx, rcx
0x180018bce  jnz     loc_180018D4D
0x180018bd4  mov     rbx, [rsp+290h+var_260]
0x180018bd9  mov     [rsi+28h], rbx
0x180018bdd  mov     rcx, rbx
0x180018be0  mov     rax, [rbx]
0x180018be3  mov     rax, [rax+8]
0x180018be7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018bec  jmp     short loc_180018C00
0x180018bee  mov     rax, [rbx]
0x180018bf1  mov     rcx, rbx
0x180018bf4  mov     rax, [rax+8]
0x180018bf8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018bfd  mov     edi, r12d
0x180018c00  mov     byte ptr [rsi+30h], 1
0x180018c04  mov     esi, 104h
0x180018c09  test    r14, r14
0x180018c0c  jz      short loc_180018C80
0x180018c0e  mov     ecx, 7FFFFFFEh
0x180018c13  lea     rax, [rsp+290h+pszFirst]
0x180018c18  mov     r8, r14
0x180018c1b  mov     edx, esi
0x180018c1d  test    rcx, rcx
0x180018c20  jz      short loc_180018C41
0x180018c22  movzx   r9d, word ptr [r8]
0x180018c26  test    r9w, r9w
0x180018c2a  jz      short loc_180018C41
0x180018c2c  mov     [rax], r9w
0x180018c30  add     r8, 2
0x180018c34  add     rax, 2
0x180018c38  dec     rcx
0x180018c3b  sub     rdx, 1
0x180018c3f  jnz     short loc_180018C1D
0x180018c41  test    rdx, rdx
0x180018c44  lea     rcx, [rax-2]
0x180018c48  cmovnz  rcx, rax
0x180018c4c  mov     [rcx], r12w
0x180018c50  jz      short loc_180018CA6
0x180018c52  lea     rdx, pszSrch; ","
0x180018c59  lea     rcx, [rsp+290h+pszFirst]; pszFirst
0x180018c5e  call    cs:__imp_StrStrW
0x180018c64  test    rax, rax
0x180018c67  jz      short loc_180018C6D
0x180018c69  mov     [rax], r12w
0x180018c6d  lea     rcx, [rsp+290h+pszFirst]; pszPath
0x180018c72  call    cs:__imp_PathIsRelativeW
0x180018c78  test    eax, eax
0x180018c7a  jz      loc_180018D1D
0x180018c80  mov     rax, [rbx]
0x180018c83  lea     rdx, pcszSubKey; "Control Panel\\Cursors"
0x180018c8a  mov     r9d, 1
0x180018c90  mov     [rsp+290h+ppv], r14
0x180018c95  mov     r8, r15
0x180018c98  mov     rcx, rbx
0x180018c9b  mov     rax, [rax+50h]
0x180018c9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018ca4  mov     edi, eax
0x180018ca6  test    edi, edi
0x180018ca8  js      short loc_180018CEB
0x180018caa  mov     r9, r15
0x180018cad  lea     r8, aSMui; "%s.MUI"
0x180018cb4  mov     rdx, rsi; unsigned __int64
0x180018cb7  lea     rcx, [rsp+290h+pszFirst]; unsigned __int16 *
0x180018cbc  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180018cc1  test    eax, eax
0x180018cc3  js      short loc_180018CEB
0x180018cc5  mov     rax, [rbx]
0x180018cc8  lea     r8, [rsp+290h+pszFirst]
0x180018ccd  mov     r9d, 1
0x180018cd3  mov     [rsp+290h+ppv], r12
0x180018cd8  lea     rdx, pcszSubKey; "Control Panel\\Cursors"
0x180018cdf  mov     rcx, rbx
0x180018ce2  mov     rax, [rax+50h]
0x180018ce6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018ceb  mov     rax, [rbx]
0x180018cee  mov     rcx, rbx
0x180018cf1  mov     rax, [rax+10h]
0x180018cf5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018cfa  mov     eax, edi
0x180018cfc  mov     rcx, [rbp+190h+var_40]
0x180018d03  xor     rcx, rsp; StackCookie
0x180018d06  call    __security_check_cookie
0x180018d0b  add     rsp, 260h
0x180018d12  pop     r15
0x180018d14  pop     r14
0x180018d16  pop     r12
0x180018d18  pop     rdi
0x180018d19  pop     rsi
0x180018d1a  pop     rbx
0x180018d1b  pop     rbp
0x180018d1c  retn
0x180018d1d  mov     r9d, esi
0x180018d20  lea     r8, [rsp+290h+pszFirst]
0x180018d25  mov     rdx, r14
0x180018d28  xor     ecx, ecx
0x180018d2a  call    cs:__imp_PathUnExpandEnvStringsForUserW
0x180018d30  test    eax, eax
0x180018d32  lea     rcx, [rsp+290h+pszFirst]
0x180018d37  cmovz   rcx, r14
0x180018d3b  mov     r14, rcx
0x180018d3e  jmp     loc_180018C80
0x180018d43  mov     rcx, [rsp+290h+var_260]
0x180018d48  mov     rax, [rcx]
0x180018d4b  jmp     short loc_180018CF1
0x180018d4d  mov     rax, [rcx]
0x180018d50  mov     rax, [rax+10h]
0x180018d54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018d59  jmp     loc_180018BD4
0x180018d5e  mov     edi, 80004005h
0x180018d63  jmp     short loc_180018CFA
```
