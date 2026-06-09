# VbsStrComp(VAR *,int,VAR *)

- ea: `0x18001e210`
- end: `0x18001e798`
- name: `?VbsStrComp@@YAJPEAVVAR@@H0@Z`
- size: `1416`
- prototype: `__int64 __fastcall(struct VAR *, int, struct VAR *)`
- caller_count: `0`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180003850`
- `0x1800040d4`
- `0x18001bf24`
- `0x18001c950`
- `0x18001e210`
- `0x18001e7a0`
- `0x180040cc4`
- `0x180042360`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x18001e78d`
- `OLEAUT32!__imp_SysFreeString` at `0x18001e78d`
- `OLEAUT32!__imp_SysStringByteLen` at `0x18001e4e6`
- `OLEAUT32!__imp_SysStringByteLen` at `0x18001e4e6`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x18001e4fb`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x18001e4fb`
- `KERNEL32!CompareStringA` at `0x18001e756`
- `KERNEL32!CompareStringA` at `0x18001e756`
- `KERNEL32!CompareStringW` at `0x18001e445`
- `KERNEL32!CompareStringW` at `0x18001e445`
- `KERNEL32!WideCharToMultiByte` at `0x18001e702`
- `KERNEL32!WideCharToMultiByte` at `0x18001e728`
- `KERNEL32!WideCharToMultiByte` at `0x18001e702`
- `KERNEL32!WideCharToMultiByte` at `0x18001e728`
- `KERNEL32!IsValidLocale` at `0x18001e61f`
- `KERNEL32!IsValidLocale` at `0x18001e61f`
- `KERNEL32!TlsGetValue` at `0x18001e268`
- `KERNEL32!TlsGetValue` at `0x18001e268`
- `KERNEL32!SetLastError` at `0x18001e76b`
- `KERNEL32!SetLastError` at `0x18001e76b`

## pseudocode

```c
__int64 __fastcall VbsStrComp(struct VAR *a1, int a2, struct VAR *a3)
{
  struct VAR *v3; // rdi
  LCID Val; // eax
  LCID DefaultLocale; // esi
  int v6; // r14d
  _QWORD *Value; // rax
  __int64 v8; // rsi
  __int16 v9; // ax
  struct IDispatch **v10; // rcx
  VARTYPE v11; // r9
  __int16 v12; // r12
  __int64 v13; // r15
  struct IDispatch **v14; // rbx
  char v15; // r13
  unsigned __int16 v16; // ax
  DWORD v17; // r10d
  __int64 v18; // r11
  unsigned int v19; // r8d
  unsigned int v20; // r13d
  unsigned int v21; // ebx
  _WORD *v22; // rcx
  unsigned int v23; // eax
  _WORD *v24; // rdx
  bool v25; // cf
  int v26; // r8d
  int cchCount2; // r13d
  int v28; // eax
  const unsigned __int16 *v29; // r8
  int v30; // r9d
  int v31; // eax
  bool v32; // zf
  unsigned __int16 v34; // ax
  UINT v35; // edx
  const unsigned __int16 *v36; // r8
  int v37; // r9d
  BSTR v38; // rax
  struct VAR *v39; // rax
  struct VAR *v40; // rax
  int Default; // eax
  const unsigned __int16 *v42; // r8
  int v43; // r9d
  int v44; // eax
  const unsigned __int16 *v45; // r8
  int v46; // r9d
  __int64 v47; // rcx
  unsigned __int8 v48; // al
  int v49; // edi
  CHAR *v50; // rax
  const CHAR *v51; // rbx
  DWORD v52; // ecx
  const CHAR *v53; // rbp
  int v54; // eax
  int v55; // edi
  int v56; // eax
  CHAR *lpString2; // [rsp+20h] [rbp-78h]
  __int64 lpWideCharStr; // [rsp+40h] [rbp-58h]
  char v60; // [rsp+A8h] [rbp+10h]
  struct IDispatch **cchWideChar; // [rsp+B0h] [rbp+18h] BYREF
  DWORD dwCmpFlags; // [rsp+B8h] [rbp+20h]

  v3 = a3;
  if ( (unsigned int)(a2 - 2) > 1 )
    return 2148139458LL;
  if ( a2 != 3 )
  {
    DefaultLocale = 0;
    goto LABEL_4;
  }
  Val = VAR::UlGetVal(a3);
  v3 = (struct VAR *)((char *)v3 + 24);
  DefaultLocale = Val;
  if ( Val < 2 )
  {
LABEL_4:
    v6 = DefaultLocale;
    Value = TlsGetValue(g_luTls);
    if ( Value && (v8 = Value[3]) != 0 )
      DefaultLocale = *(_DWORD *)(v8 + 188);
    else
      DefaultLocale = GetDefaultLocale();
    goto LABEL_7;
  }
  v6 = 1;
  if ( !IsValidLocale(Val, 1u) )
    return 2148139013LL;
LABEL_7:
  v9 = *(_WORD *)v3;
  if ( *(_WORD *)v3 == 16396 || v9 == 74 )
  {
    v10 = (struct IDispatch **)*((_QWORD *)v3 + 1);
    v9 = *(_WORD *)v10;
  }
  else
  {
    v10 = (struct IDispatch **)v3;
  }
  cchWideChar = v10;
  if ( v9 == 9 )
  {
    Default = VAR::ObjGetDefault(v10[1], (struct VAR **)&cchWideChar);
    if ( Default < 0 )
      RaiseErrorHr(Default, 0, v42, v43);
    v10 = cchWideChar;
  }
  v11 = 8;
  v12 = -1;
  if ( *(_WORD *)v10 == 8 )
  {
    v13 = (__int64)v10[1];
  }
  else
  {
    if ( *(_WORD *)v10 == 1 )
    {
      v13 = -1;
      v14 = (struct IDispatch **)((char *)v3 + 24);
LABEL_16:
      v15 = 0;
      goto LABEL_17;
    }
    v39 = VAR::PvarConvert((VAR *)v10, 8u);
    v11 = 8;
    v13 = *((_QWORD *)v39 + 1);
  }
  v14 = (struct IDispatch **)((char *)v3 + 24);
  if ( !v13 || v13 == -1 || v3 == (struct VAR *)-24LL )
    goto LABEL_16;
  v34 = *(_WORD *)v14;
  if ( *(_WORD *)v14 == 16396 || v34 == 74 )
    v34 = **((_WORD **)v3 + 4);
  if ( v34 == 8 || (v34 & 0x4000) == 0 && (unsigned int)VAR::IsSimpleType(v34) )
    goto LABEL_16;
  v35 = SysStringByteLen((BSTR)v13);
  v38 = 0;
  if ( v35 < 0x7FFFFFFD )
    v38 = SysAllocStringByteLen((LPCSTR)v13, v35);
  if ( !v38 )
    RaiseErrorHr(-2146828281, 0, v36, v37);
  v13 = (__int64)v38;
  v15 = 1;
  v11 = 8;
LABEL_17:
  v16 = *(_WORD *)v14;
  v60 = v15;
  if ( *(_WORD *)v14 == 16396 || v16 == 74 )
  {
    v14 = (struct IDispatch **)*((_QWORD *)v3 + 4);
    v16 = *(_WORD *)v14;
  }
  cchWideChar = v14;
  if ( v16 == 9 )
  {
    v44 = VAR::ObjGetDefault(v14[1], (struct VAR **)&cchWideChar);
    if ( v44 < 0 )
      RaiseErrorHr(v44, 0, v45, v46);
    v14 = cchWideChar;
    v11 = 8;
  }
  v17 = 1;
  if ( v11 == *(_WORD *)v14 )
  {
    v18 = (__int64)v14[1];
  }
  else
  {
    if ( *(_WORD *)v14 == 1 )
    {
      v18 = -1;
      lpWideCharStr = -1;
      goto LABEL_23;
    }
    v40 = VAR::PvarConvert((VAR *)v14, v11);
    v17 = 1;
    v18 = *((_QWORD *)v40 + 1);
  }
  lpWideCharStr = v18;
LABEL_23:
  if ( v13 == -1 || v18 == -1 )
  {
    v32 = v15 == 0;
    *(_WORD *)a1 = 1;
    goto LABEL_51;
  }
  if ( v18 )
    v19 = *(_DWORD *)(v18 - 4);
  else
    v19 = 0;
  LODWORD(cchWideChar) = v19;
  if ( v13 )
    v20 = *(_DWORD *)(v13 - 4);
  else
    v20 = 0;
  v21 = v19;
  if ( v19 >= v20 )
    v21 = v20;
  if ( !v21 )
  {
LABEL_39:
    if ( v19 >= v20 )
    {
      if ( v19 <= v20 )
      {
        v12 = 2;
        if ( v19 == v20 )
          v12 = 0;
      }
      else
      {
        v12 = 1;
      }
    }
    goto LABEL_50;
  }
  if ( !v6 )
  {
    v22 = (_WORD *)v13;
    v23 = v21 >> 1;
    v24 = (_WORD *)v18;
    while ( v23 )
    {
      v25 = *v24 < *v22;
      if ( *v24 != *v22 )
        goto LABEL_91;
      --v23;
      ++v24;
      ++v22;
    }
    if ( (v21 & 1) == 0
      || (v47 = v21 - 1, v48 = *(_BYTE *)(v47 + v18), v25 = v48 < *(_BYTE *)(v47 + v13), v48 == *(_BYTE *)(v47 + v13)) )
    {
      v19 = (unsigned int)cchWideChar;
      goto LABEL_39;
    }
LABEL_91:
    if ( !v25 )
      v12 = 1;
    goto LABEL_50;
  }
  if ( g_fFarEast )
    v17 = 131073;
  dwCmpFlags = v17;
  if ( g_fJapan )
  {
    v17 |= 0x10000u;
    dwCmpFlags = v17;
  }
  v26 = v19 >> 1;
  cchCount2 = v20 >> 1;
  LODWORD(cchWideChar) = v26;
  if ( !g_fAnsiOs )
  {
    v28 = CompareStringW(DefaultLocale, v17, (PCNZWCH)v18, v26, (PCNZWCH)v13, cchCount2);
    goto LABEL_48;
  }
  if ( !v26 || !cchCount2 )
  {
    v52 = 87;
    goto LABEL_102;
  }
  v49 = 2 * v26;
  v50 = (CHAR *)MemAlloc(2 * cchCount2 + 2 * v26);
  v51 = v50;
  if ( !v50 )
  {
    v52 = 14;
LABEL_102:
    SetLastError(v52);
    goto LABEL_77;
  }
  v53 = &v50[v49];
  v54 = WideCharToMultiByte(0, 0, (LPCWCH)lpWideCharStr, (int)cchWideChar, v50, v49, 0, 0);
  lpString2 = (CHAR *)&v51[v49];
  v55 = v54;
  v56 = WideCharToMultiByte(0, 0, (LPCWCH)v13, cchCount2, lpString2, 2 * cchCount2, 0, 0);
  if ( !v55 || !v56 )
LABEL_77:
    RaiseErrorHr(-2146828283, 0, v29, v30);
  v28 = CompareStringA(DefaultLocale, dwCmpFlags, v51, v55, v53, v56);
LABEL_48:
  v31 = v28 - 2;
  if ( v31 == -2 )
    goto LABEL_77;
  v12 = v31;
LABEL_50:
  v32 = v60 == 0;
  *((_WORD *)a1 + 4) = v12;
  *(_WORD *)a1 = 2;
LABEL_51:
  if ( !v32 )
    SysFreeString((BSTR)v13);
  return 0;
}

```

## disassembly

```asm
0x18001e210  mov     r11, rsp
0x18001e213  mov     [r11+8], rcx
0x18001e217  push    rdi
0x18001e218  sub     rsp, 90h
0x18001e21f  lea     eax, [rdx-2]
0x18001e222  mov     rdi, r8
0x18001e225  cmp     eax, 1
0x18001e228  ja      loc_18001E58E
0x18001e22e  mov     [r11-10h], rbx
0x18001e232  mov     ebx, 1
0x18001e237  mov     [r11-20h], rsi
0x18001e23b  mov     [r11-38h], r14
0x18001e23f  cmp     edx, 3
0x18001e242  jnz     loc_18001E533
0x18001e248  mov     rcx, r8; this
0x18001e24b  call    ?UlGetVal@VAR@@QEAAKXZ; VAR::UlGetVal(void)
0x18001e250  add     rdi, 18h
0x18001e254  mov     esi, eax
0x18001e256  cmp     eax, 2
0x18001e259  jnb     loc_18001E618
0x18001e25f  mov     ecx, cs:?g_luTls@@3KA; dwTlsIndex
0x18001e265  mov     r14d, esi
0x18001e268  call    cs:__imp_TlsGetValue
0x18001e26e  test    rax, rax
0x18001e271  jz      loc_18001E517
0x18001e277  mov     rsi, [rax+18h]
0x18001e27b  test    rsi, rsi
0x18001e27e  jz      loc_18001E517
0x18001e284  mov     esi, [rsi+0BCh]
0x18001e28a  movzx   eax, word ptr [rdi]
0x18001e28d  mov     [rsp+98h+var_18], rbp
0x18001e295  mov     ebp, 400Ch
0x18001e29a  cmp     ax, bp
0x18001e29d  jz      loc_18001E53A
0x18001e2a3  cmp     ax, 4Ah ; 'J'
0x18001e2a7  jz      loc_18001E53A
0x18001e2ad  mov     rcx, rdi; this
0x18001e2b0  mov     edx, 9
0x18001e2b5  mov     [rsp+98h+cchWideChar], rcx
0x18001e2bd  cmp     dx, ax
0x18001e2c0  jz      loc_18001E5CE
0x18001e2c6  movzx   eax, word ptr [rcx]
0x18001e2c9  mov     r9d, 8
0x18001e2cf  mov     [rsp+98h+var_28], r12
0x18001e2d4  mov     r12, 0FFFFFFFFFFFFFFFFh
0x18001e2db  mov     [rsp+98h+var_30], r13
0x18001e2e0  mov     [rsp+98h+var_40], r15
0x18001e2e5  cmp     r9w, ax
0x18001e2e9  jnz     loc_18001E552
0x18001e2ef  mov     r15, [rcx+8]
0x18001e2f3  lea     rbx, [rdi+18h]
0x18001e2f7  test    r15, r15
0x18001e2fa  jz      short loc_18001E30A
0x18001e2fc  cmp     r15, r12
0x18001e2ff  jz      short loc_18001E30A
0x18001e301  test    rbx, rbx
0x18001e304  jnz     loc_18001E4AC
0x18001e30a  xor     r13b, r13b
0x18001e30d  movzx   eax, word ptr [rbx]
0x18001e310  mov     [rsp+98h+arg_8], r13b
0x18001e318  cmp     ax, bp
0x18001e31b  jz      loc_18001E546
0x18001e321  cmp     ax, 4Ah ; 'J'
0x18001e325  jz      loc_18001E546
0x18001e32b  mov     ecx, 9
0x18001e330  mov     [rsp+98h+cchWideChar], rbx
0x18001e338  cmp     cx, ax
0x18001e33b  jz      loc_18001E5F0
0x18001e341  movzx   eax, word ptr [rbx]
0x18001e344  mov     r10d, 1
0x18001e34a  cmp     r9w, ax
0x18001e34e  jnz     loc_18001E56E
0x18001e354  mov     r11, [rbx+8]
0x18001e358  mov     [rsp+98h+lpWideCharStr], r11
0x18001e35d  cmp     r15, r12
0x18001e360  jz      loc_18001E776
0x18001e366  cmp     r11, r12
0x18001e369  jz      loc_18001E776
0x18001e36f  test    r11, r11
0x18001e372  jz      loc_18001E523
0x18001e378  mov     r8d, [r11-4]
0x18001e37c  mov     dword ptr [rsp+98h+cchWideChar], r8d
0x18001e384  test    r15, r15
0x18001e387  jz      loc_18001E52B
0x18001e38d  mov     r13d, [r15-4]
0x18001e391  cmp     r8d, r13d
0x18001e394  mov     ebx, r8d
0x18001e397  mov     edi, 2
0x18001e39c  cmovnb  ebx, r13d
0x18001e3a0  test    ebx, ebx
0x18001e3a2  jz      short loc_18001E3E0
0x18001e3a4  test    r14d, r14d
0x18001e3a7  jnz     short loc_18001E3F0
0x18001e3a9  mov     eax, ebx
0x18001e3ab  mov     rcx, r15
0x18001e3ae  shr     eax, 1
0x18001e3b0  mov     rdx, r11
0x18001e3b3  test    eax, eax
0x18001e3b5  jz      short loc_18001E3CF
0x18001e3b7  movzx   r8d, word ptr [rdx]
0x18001e3bb  cmp     r8w, [rcx]
0x18001e3bf  jnz     loc_18001E681
0x18001e3c5  dec     eax
0x18001e3c7  add     rdx, rdi
0x18001e3ca  add     rcx, rdi
0x18001e3cd  jmp     short loc_18001E3B3
0x18001e3cf  test    bl, 1
0x18001e3d2  jnz     loc_18001E66D
0x18001e3d8  mov     r8d, dword ptr [rsp+98h+cchWideChar]
0x18001e3e0  cmp     r8d, r13d
0x18001e3e3  jb      short loc_18001E45A
0x18001e3e5  jbe     loc_18001E65C
0x18001e3eb  mov     r12d, r10d
0x18001e3ee  jmp     short loc_18001E45A
0x18001e3f0  cmp     cs:?g_fFarEast@@3HA, 0; int g_fFarEast
0x18001e3f7  mov     eax, 20001h
0x18001e3fc  cmovnz  r10d, eax
0x18001e400  cmp     cs:?g_fJapan@@3HA, 0; int g_fJapan
0x18001e407  mov     [rsp+98h+dwCmpFlags], r10d
0x18001e40f  jnz     loc_18001E68A
0x18001e415  shr     r8d, 1
0x18001e418  shr     r13d, 1
0x18001e41b  cmp     cs:?g_fAnsiOs@@3HA, 0; int g_fAnsiOs
0x18001e422  mov     dword ptr [rsp+98h+cchWideChar], r8d
0x18001e42a  jnz     loc_18001E69C
0x18001e430  mov     r9d, r8d; cchCount1
0x18001e433  mov     [rsp+98h+cchCount2], r13d; cchCount2
0x18001e438  mov     r8, r11; lpString1
0x18001e43b  mov     [rsp+98h+lpString2], r15; lpString2
0x18001e440  mov     edx, r10d; dwCmpFlags
0x18001e443  mov     ecx, esi; Locale
0x18001e445  call    cs:__imp_CompareStringW
0x18001e44b  add     eax, 0FFFFFFFEh
0x18001e44e  cmp     eax, 0FFFFFFFEh
0x18001e451  jz      loc_18001E5C1
0x18001e457  mov     r12d, eax
0x18001e45a  mov     rax, [rsp+98h+arg_0]
0x18001e462  cmp     [rsp+98h+arg_8], 0
0x18001e46a  mov     [rax+8], r12w
0x18001e46f  mov     [rax], di
0x18001e472  jnz     loc_18001E78A
0x18001e478  mov     r12, [rsp+98h+var_28]
0x18001e47d  xor     eax, eax
0x18001e47f  mov     r13, [rsp+98h+var_30]
0x18001e484  mov     r15, [rsp+98h+var_40]
0x18001e489  mov     rbp, [rsp+98h+var_18]
0x18001e491  mov     rsi, [rsp+98h+var_20]
0x18001e496  mov     r14, [rsp+98h+var_38]
0x18001e49b  mov     rbx, [rsp+98h+var_10]
0x18001e4a3  add     rsp, 90h
0x18001e4aa  pop     rdi
0x18001e4ab  retn
0x18001e4ac  movzx   eax, word ptr [rbx]
0x18001e4af  cmp     ax, bp
0x18001e4b2  jz      loc_18001E59C
0x18001e4b8  cmp     ax, 4Ah ; 'J'
0x18001e4bc  jz      loc_18001E59C
0x18001e4c2  cmp     ax, 8
0x18001e4c6  jz      loc_18001E30A
0x18001e4cc  bt      ax, 0Eh
0x18001e4d1  jb      short loc_18001E4E3
0x18001e4d3  movzx   ecx, ax; int
0x18001e4d6  call    ?IsSimpleType@VAR@@SAHH@Z; VAR::IsSimpleType(int)
0x18001e4db  test    eax, eax
0x18001e4dd  jnz     loc_18001E30A
0x18001e4e3  mov     rcx, r15; bstr
0x18001e4e6  call    cs:__imp_SysStringByteLen
0x18001e4ec  mov     edx, eax; len
0x18001e4ee  xor     eax, eax
0x18001e4f0  cmp     edx, 7FFFFFFDh
0x18001e4f6  jnb     short loc_18001E501
0x18001e4f8  mov     rcx, r15; psz
0x18001e4fb  call    cs:__imp_SysAllocStringByteLen
0x18001e501  test    rax, rax
0x18001e504  jnz     loc_18001E641
0x18001e50a  xor     edx, edx; struct VAR *
0x18001e50c  mov     ecx, 800A0007h; int
0x18001e511  call    ?RaiseErrorHr@@YAXJPEAVVAR@@PEBGJ@Z; RaiseErrorHr(long,VAR *,ushort const *,long)
0x18001e517  call    ?GetDefaultLocale@@YAKXZ; GetDefaultLocale(void)
0x18001e51c  mov     esi, eax
0x18001e51e  jmp     loc_18001E28A
0x18001e523  xor     r8d, r8d
0x18001e526  jmp     loc_18001E37C
0x18001e52b  xor     r13d, r13d
0x18001e52e  jmp     loc_18001E391
0x18001e533  xor     esi, esi
0x18001e535  jmp     loc_18001E25F
0x18001e53a  mov     rcx, [rdi+8]
0x18001e53e  movzx   eax, word ptr [rcx]
0x18001e541  jmp     loc_18001E2B0
0x18001e546  mov     rbx, [rdi+20h]
0x18001e54a  movzx   eax, word ptr [rbx]
0x18001e54d  jmp     loc_18001E32B
0x18001e552  cmp     bx, ax
0x18001e555  jz      short loc_18001E5A8
0x18001e557  mov     edx, r9d; vt
0x18001e55a  call    ?PvarConvert@VAR@@QEAAPEAV1@H@Z; VAR::PvarConvert(int)
0x18001e55f  mov     r9d, 8
0x18001e565  mov     r15, [rax+8]
0x18001e569  jmp     loc_18001E2F3
0x18001e56e  cmp     r10w, ax
0x18001e572  jz      short loc_18001E5B4
0x18001e574  mov     edx, r9d; vt
0x18001e577  mov     rcx, rbx; this
0x18001e57a  call    ?PvarConvert@VAR@@QEAAPEAV1@H@Z; VAR::PvarConvert(int)
0x18001e57f  mov     r10d, 1
0x18001e585  mov     r11, [rax+8]
0x18001e589  jmp     loc_18001E358
0x18001e58e  mov     eax, 800A01C2h
0x18001e593  add     rsp, 90h
0x18001e59a  pop     rdi
0x18001e59b  retn
0x18001e59c  mov     rax, [rdi+20h]
0x18001e5a0  movzx   eax, word ptr [rax]
0x18001e5a3  jmp     loc_18001E4C2
0x18001e5a8  mov     r15, r12
0x18001e5ab  lea     rbx, [rdi+18h]
0x18001e5af  jmp     loc_18001E30A
0x18001e5b4  mov     r11, r12
0x18001e5b7  mov     [rsp+98h+lpWideCharStr], r12
0x18001e5bc  jmp     loc_18001E35D
0x18001e5c1  xor     edx, edx; struct VAR *
0x18001e5c3  mov     ecx, 800A0005h; int
0x18001e5c8  call    ?RaiseErrorHr@@YAXJPEAVVAR@@PEBGJ@Z; RaiseErrorHr(long,VAR *,ushort const *,long)
0x18001e5ce  mov     rcx, [rcx+8]; struct IDispatch *
0x18001e5d2  lea     rdx, [rsp+98h+cchWideChar]; struct VAR **
0x18001e5da  call    ?ObjGetDefault@VAR@@SAJPEAUIDispatch@@PEAPEAV1@@Z; VAR::ObjGetDefault(IDispatch *,VAR * *)
0x18001e5df  test    eax, eax
0x18001e5e1  js      short loc_18001E637
0x18001e5e3  mov     rcx, [rsp+98h+cchWideChar]
0x18001e5eb  jmp     loc_18001E2C6
0x18001e5f0  mov     rcx, [rbx+8]; struct IDispatch *
0x18001e5f4  lea     rdx, [rsp+98h+cchWideChar]; struct VAR **
0x18001e5fc  call    ?ObjGetDefault@VAR@@SAJPEAUIDispatch@@PEAPEAV1@@Z; VAR::ObjGetDefault(IDispatch *,VAR * *)
0x18001e601  test    eax, eax
0x18001e603  js      short loc_18001E652
0x18001e605  mov     rbx, [rsp+98h+cchWideChar]
0x18001e60d  mov     r9d, 8
0x18001e613  jmp     loc_18001E341
0x18001e618  mov     edx, ebx; dwFlags
0x18001e61a  mov     ecx, eax; Locale
0x18001e61c  mov     r14d, ebx
0x18001e61f  call    cs:__imp_IsValidLocale
0x18001e625  test    eax, eax
0x18001e627  jnz     loc_18001E28A
0x18001e62d  mov     eax, 800A0005h
0x18001e632  jmp     loc_18001E491
0x18001e637  xor     edx, edx; struct VAR *
0x18001e639  mov     ecx, eax; int
0x18001e63b  call    ?RaiseErrorHr@@YAXJPEAVVAR@@PEBGJ@Z; RaiseErrorHr(long,VAR *,ushort const *,long)
0x18001e641  mov     r15, rax
0x18001e644  mov     r13b, 1
0x18001e647  mov     r9d, 8
0x18001e64d  jmp     loc_18001E30D
0x18001e652  xor     edx, edx; struct VAR *
0x18001e654  mov     ecx, eax; int
0x18001e656  call    ?RaiseErrorHr@@YAXJPEAVVAR@@PEBGJ@Z; RaiseErrorHr(long,VAR *,ushort const *,long)
0x18001e65c  xor     eax, eax
0x18001e65e  mov     r12d, edi
0x18001e661  cmp     r8d, r13d
0x18001e664  cmovz   r12d, eax
0x18001e668  jmp     loc_18001E45A
0x18001e66d  lea     eax, [rbx-1]
0x18001e670  mov     ecx, eax
0x18001e672  movzx   eax, byte ptr [rax+r11]
0x18001e677  cmp     al, [rcx+r15]
0x18001e67b  jz      loc_18001E3D8
0x18001e681  cmovnb  r12d, r10d
0x18001e685  jmp     loc_18001E45A
0x18001e68a  bts     r10d, 10h
0x18001e68f  mov     [rsp+98h+dwCmpFlags], r10d
0x18001e697  jmp     loc_18001E415
0x18001e69c  test    r8d, r8d
0x18001e69f  jz      loc_18001E766
0x18001e6a5  test    r13d, r13d
0x18001e6a8  jz      loc_18001E766
0x18001e6ae  lea     edi, [r8+r8]
0x18001e6b2  lea     r14d, ds:0[r13*2]
0x18001e6ba  lea     ecx, [r14+rdi]; unsigned int
0x18001e6be  call    ?MemAlloc@@YAPEAXI@Z; MemAlloc(uint)
0x18001e6c3  mov     rbx, rax
0x18001e6c6  test    rax, rax
0x18001e6c9  jnz     short loc_18001E6D5
0x18001e6cb  mov     ecx, 0Eh
0x18001e6d0  jmp     loc_18001E76B
0x18001e6d5  mov     r9d, dword ptr [rsp+98h+cchWideChar]; cchWideChar
0x18001e6dd  xor     r12d, r12d
0x18001e6e0  mov     r8, [rsp+98h+lpWideCharStr]; lpWideCharStr
0x18001e6e5  xor     edx, edx; dwFlags
0x18001e6e7  mov     [rsp+98h+lpUsedDefaultChar], r12; lpUsedDefaultChar
0x18001e6ec  xor     ecx, ecx; CodePage
0x18001e6ee  mov     [rsp+98h+lpDefaultChar], r12; lpDefaultChar
0x18001e6f3  movsxd  rbp, edi
0x18001e6f6  mov     [rsp+98h+cchCount2], edi; cbMultiByte
0x18001e6fa  add     rbp, rbx
0x18001e6fd  mov     [rsp+98h+lpString2], rbx; lpMultiByteStr
0x18001e702  call    cs:__imp_WideCharToMultiByte
0x18001e708  mov     [rsp+98h+lpUsedDefaultChar], r12; lpUsedDefaultChar
0x18001e70d  mov     r9d, r13d; cchWideChar
0x18001e710  mov     [rsp+98h+lpDefaultChar], r12; lpDefaultChar
  ... truncated ...
```
