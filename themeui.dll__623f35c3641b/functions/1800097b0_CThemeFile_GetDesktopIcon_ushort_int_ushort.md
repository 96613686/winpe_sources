# CThemeFile::GetDesktopIcon(ushort *,int,ushort * *)

- ea: `0x1800097b0`
- end: `0x180009bc4`
- name: `?GetDesktopIcon@CThemeFile@@UEAAJPEAGHPEAPEAG@Z`
- size: `1044`
- prototype: `__int64 __fastcall(CThemeFile *__hidden this, unsigned __int16 *, int, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `14`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x1800089c0`
- `0x1800097b0`
- `0x18000a9a0`
- `0x18000ab90`
- `0x18000d490`
- `0x18000dd60`
- `0x18000e780`
- `0x180015660`
- `0x1800358c0`
- `0x18003633c`
- `0x180052974`
- `0x180060fac`
- `0x18006ad80`
- `0x18006d010`

## import_xrefs

- `SHLWAPI!StrChrW` at `0x180009898`
- `SHLWAPI!StrChrW` at `0x180009898`
- `SHLWAPI!PathIsRelativeW` at `0x180009b4e`
- `SHLWAPI!PathIsRelativeW` at `0x180009b4e`
- `SHLWAPI!__imp_SHLoadIndirectString` at `0x180009b08`
- `SHLWAPI!__imp_SHLoadIndirectString` at `0x180009b08`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180009a36`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180009b9e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180009a36`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180009b9e`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800098ad`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800098ad`
- `OLEAUT32!__imp_SysAllocString` at `0x180009a19`
- `OLEAUT32!__imp_SysAllocString` at `0x180009a19`

## pseudocode

```c
__int64 __fastcall CThemeFile::GetDesktopIcon(CThemeFile *this, unsigned __int16 *a2, int a3, unsigned __int16 **a4)
{
  char v4; // r13
  __int64 v5; // rsi
  WCHAR *v8; // r9
  unsigned __int16 *v9; // r15
  __int64 v10; // rcx
  __int64 v11; // r8
  WCHAR *v12; // rcx
  int CachedProfile; // ebx
  unsigned int v14; // edx
  __int64 result; // rax
  const WCHAR *v16; // rax
  const WCHAR *v17; // rdi
  LPWSTR v18; // rax
  __int64 v19; // rdx
  unsigned __int16 *v20; // r8
  unsigned __int16 *v21; // rcx
  OLECHAR *v22; // rdi
  const unsigned __int16 **v23; // rsi
  const OLECHAR *v24; // rcx
  unsigned __int16 *v25; // r8
  unsigned __int16 *v26; // rcx
  unsigned __int16 *v27; // rax
  int v28; // eax
  struct ICachedPrivateProfile *v29; // r14
  HRESULT v30; // ebx
  unsigned int v31; // edx
  struct IUnknown *v32; // rdx
  __int64 v33; // rcx
  __int64 v34; // r8
  HRESULT v35; // eax
  struct ICachedPrivateProfile *v36; // [rsp+40h] [rbp-C0h] BYREF
  PCWSTR pszSource; // [rsp+48h] [rbp-B8h] BYREF
  OLECHAR *v38; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int16 *v39; // [rsp+58h] [rbp-A8h]
  CThemeFile *v40; // [rsp+60h] [rbp-A0h]
  WCHAR pszOutBuf[264]; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int16 v42[264]; // [rsp+280h] [rbp+180h] BYREF
  WCHAR pszStart[2088]; // [rsp+490h] [rbp+390h] BYREF
  unsigned __int16 v44[2088]; // [rsp+14E0h] [rbp+13E0h] BYREF

  v40 = this;
  *a4 = 0;
  v4 = 3;
  v39 = a2;
  v5 = 2147483646;
  v8 = pszStart;
  if ( !a3 )
    v4 = 1;
  v9 = a2;
  v10 = 2147483646;
  v11 = 2084;
  do
  {
    if ( !v10 )
      break;
    if ( !*a2 )
      break;
    *v8++ = *a2++;
    --v10;
    --v11;
  }
  while ( v11 );
  v12 = v8 - 1;
  CachedProfile = -2147024774;
  v14 = -2147024774;
  if ( v11 )
  {
    v12 = v8;
    v14 = 0;
  }
  *v12 = 0;
  if ( !v11 )
    return v14;
  v16 = StrChrW(pszStart, 0x3Au);
  v17 = v16;
  if ( v16 )
  {
    v18 = CharNextW(v16);
    v19 = 260;
    v20 = v42;
    do
    {
      if ( !v5 )
        break;
      if ( !*v18 )
        break;
      *v20++ = *v18++;
      --v5;
      --v19;
    }
    while ( v19 );
    v21 = v20 - 1;
    if ( v19 )
      v21 = v20;
    *v21 = 0;
    *v17 = 0;
  }
  else
  {
    v24 = L"DefaultValue";
    v19 = 260;
    v25 = v42;
    do
    {
      if ( !v5 )
        break;
      if ( !*v24 )
        break;
      *v25++ = *v24++;
      --v5;
      --v19;
    }
    while ( v19 );
    v26 = v25 - 1;
    if ( v19 )
      v26 = v25;
    *v26 = 0;
  }
  if ( v19 )
    CachedProfile = 0;
  if ( CachedProfile < 0 )
    return (unsigned int)CachedProfile;
  v22 = 0;
  *a4 = 0;
  v23 = (const unsigned __int16 **)((char *)this - 16);
  v38 = 0;
  v36 = 0;
  CachedProfile = CThemeFile::_GetCachedProfile((CThemeFile *)((char *)this - 16), 1, &v36);
  if ( CachedProfile < 0 )
    goto LABEL_23;
  pszSource = 0;
  v28 = StringCchPrintfW(v44, 0x104u, L"%s.MUI", v42);
  v29 = v36;
  if ( v28 >= 0
    && (*(int (__fastcall **)(struct ICachedPrivateProfile *, WCHAR *, unsigned __int16 *, _QWORD, int, PCWSTR *))(*(_QWORD *)v36 + 48LL))(
         v36,
         pszStart,
         v44,
         0,
         1,
         &pszSource) >= 0
    || (v30 = (*(__int64 (__fastcall **)(struct ICachedPrivateProfile *, WCHAR *, unsigned __int16 *, _QWORD, int, PCWSTR *))(*(_QWORD *)v29 + 48LL))(
                v29,
                pszStart,
                v42,
                0,
                1,
                &pszSource),
        v30 >= 0) )
  {
    memset_0(pszOutBuf, 0, 0x208u);
    v30 = SHLoadIndirectString(pszSource, pszOutBuf, 0x104u, 0);
    if ( v30 < 0 )
      goto LABEL_55;
    v30 = ExpandResourceDir(pszOutBuf, v31);
    if ( v30 < 0 )
      goto LABEL_55;
    v30 = ExpandThemeTokens(v23[6], pszOutBuf);
    if ( v30 < 0 )
      goto LABEL_55;
    if ( (v4 & 2) != 0 && !PathIsRelativeW(pszOutBuf) )
    {
      LODWORD(v36) = 0;
      SHMapUrlToZoneEx(pszOutBuf, v32, v34, (unsigned int *)&v36);
      if ( pszOutBuf[0] && (_DWORD)v36 && !CFileSource::s_IsUncPathAllowedForThumbnailImage() )
      {
        pszOutBuf[0] = 0;
      }
      else if ( (unsigned int)ConfirmFile(pszOutBuf) == 3 )
      {
        v30 = -2147024894;
        goto LABEL_55;
      }
    }
    v35 = _AllocString<CTCoAllocPolicy>(v33, v32, pszOutBuf, &v38);
    v22 = v38;
    v30 = v35;
LABEL_55:
    CoTaskMemFree((LPVOID)pszSource);
    v9 = v39;
  }
  (*(void (__fastcall **)(struct ICachedPrivateProfile *))(*(_QWORD *)v29 + 16LL))(v29);
  if ( v30 < 0 )
    goto LABEL_33;
  CachedProfile = 0;
  v27 = SysAllocString(v22);
  *a4 = v27;
  if ( v22 && !v27 )
    CachedProfile = -2147024882;
  CoTaskMemFree(v22);
LABEL_23:
  if ( CachedProfile >= 0 )
    return (unsigned int)CachedProfile;
LABEL_33:
  result = StringCchPrintfW(v44, 0x824u, L"Software\\Classes\\%s", pszStart);
  if ( (int)result >= 0 )
  {
    result = CThemeFile::_getThemeSettingBSTR((CThemeFile *)v23, v44, v42, v4, a4);
    if ( (int)result < 0 )
      return (*(__int64 (__fastcall **)(CThemeFile *, unsigned __int16 *, unsigned __int16 **))(*(_QWORD *)v40 + 368LL))(
               v40,
               v9,
               a4);
  }
  return result;
}

```

## disassembly

```asm
0x1800097b0  push    rbp
0x1800097b2  push    rbx
0x1800097b3  push    rsi
0x1800097b4  push    r12
0x1800097b6  push    r13
0x1800097b8  push    r14
0x1800097ba  push    r15
0x1800097bc  lea     rbp, [rsp-2440h]
0x1800097c4  mov     eax, 2540h
0x1800097c9  call    _alloca_probe
0x1800097ce  sub     rsp, rax
0x1800097d1  mov     rax, cs:__security_cookie
0x1800097d8  xor     rax, rsp
0x1800097db  mov     [rbp+2470h+var_40], rax
0x1800097e2  test    r8d, r8d
0x1800097e5  mov     [rsp+2570h+var_2510], rcx
0x1800097ea  mov     eax, 1
0x1800097ef  mov     qword ptr [r9], 0
0x1800097f6  mov     r13d, 3
0x1800097fc  mov     [rsp+2570h+var_2518], rdx
0x180009801  mov     esi, 7FFFFFFEh
0x180009806  mov     r12, r9
0x180009809  mov     r14, rcx
0x18000980c  lea     r9, [rbp+2470h+pszStart]
0x180009813  cmovz   r13d, eax
0x180009817  mov     r15, rdx
0x18000981a  mov     ecx, esi
0x18000981c  mov     r8d, 824h
0x180009822  test    rcx, rcx
0x180009825  jz      short loc_180009844
0x180009827  movzx   eax, word ptr [rdx]
0x18000982a  test    ax, ax
0x18000982d  jz      short loc_180009844
0x18000982f  mov     [r9], ax
0x180009833  add     rdx, 2
0x180009837  add     r9, 2
0x18000983b  dec     rcx
0x18000983e  sub     r8, 1
0x180009842  jnz     short loc_180009822
0x180009844  xor     eax, eax
0x180009846  lea     rcx, [r9-2]
0x18000984a  test    r8, r8
0x18000984d  mov     ebx, 8007007Ah
0x180009852  mov     edx, ebx
0x180009854  cmovnz  rcx, r9
0x180009858  cmovnz  edx, eax
0x18000985b  mov     [rcx], ax
0x18000985e  jnz     short loc_180009884
0x180009860  mov     eax, edx
0x180009862  mov     rcx, [rbp+2470h+var_40]
0x180009869  xor     rcx, rsp; StackCookie
0x18000986c  call    __security_check_cookie
0x180009871  add     rsp, 2540h
0x180009878  pop     r15
0x18000987a  pop     r14
0x18000987c  pop     r13
0x18000987e  pop     r12
0x180009880  pop     rsi
0x180009881  pop     rbx
0x180009882  pop     rbp
0x180009883  retn
0x180009884  mov     edx, 3Ah ; ':'; wMatch
0x180009889  mov     [rsp+2570h+arg_10], rdi
0x180009891  lea     rcx, [rbp+2470h+pszStart]; pszStart
0x180009898  call    cs:__imp_StrChrW
0x18000989e  mov     rdi, rax
0x1800098a1  test    rax, rax
0x1800098a4  jz      loc_180009943
0x1800098aa  mov     rcx, rax; lpsz
0x1800098ad  call    cs:__imp_CharNextW
0x1800098b3  mov     edx, 104h
0x1800098b8  lea     r8, [rbp+2470h+var_22F0]
0x1800098bf  nop
0x1800098c0  test    rsi, rsi
0x1800098c3  jz      short loc_1800098E2
0x1800098c5  movzx   ecx, word ptr [rax]
0x1800098c8  test    cx, cx
0x1800098cb  jz      short loc_1800098E2
0x1800098cd  mov     [r8], cx
0x1800098d1  add     rax, 2
0x1800098d5  add     r8, 2
0x1800098d9  dec     rsi
0x1800098dc  sub     rdx, 1
0x1800098e0  jnz     short loc_1800098C0
0x1800098e2  test    rdx, rdx
0x1800098e5  lea     rcx, [r8-2]
0x1800098e9  cmovnz  rcx, r8
0x1800098ed  xor     eax, eax
0x1800098ef  mov     [rcx], ax
0x1800098f2  mov     [rdi], ax
0x1800098f5  test    rdx, rdx
0x1800098f8  cmovnz  ebx, eax
0x1800098fb  test    ebx, ebx
0x1800098fd  js      short loc_180009934
0x1800098ff  xor     edi, edi
0x180009901  mov     qword ptr [r12], 0
0x180009909  lea     rsi, [r14-10h]
0x18000990d  mov     [rsp+2570h+var_2520], rdi
0x180009912  mov     rcx, rsi; this
0x180009915  mov     [rsp+2570h+var_2530], rdi
0x18000991a  lea     r8, [rsp+2570h+var_2530]; struct ICachedPrivateProfile **
0x18000991f  mov     dl, 1; bool
0x180009921  call    ?_GetCachedProfile@CThemeFile@@AEAAJ_NPEAPEAUICachedPrivateProfile@@@Z; CThemeFile::_GetCachedProfile(bool,ICachedPrivateProfile * *)
0x180009926  mov     ebx, eax
0x180009928  test    eax, eax
0x18000992a  jns     loc_180009A41
0x180009930  test    ebx, ebx
0x180009932  js      short loc_18000998D
0x180009934  mov     eax, ebx
0x180009936  mov     rdi, [rsp+2570h+arg_10]
0x18000993e  jmp     loc_180009862
0x180009943  lea     rcx, aDefaultvalue; "DefaultValue"
0x18000994a  mov     edx, 104h
0x18000994f  lea     r8, [rbp+2470h+var_22F0]
0x180009956  test    rsi, rsi
0x180009959  jz      short loc_180009978
0x18000995b  movzx   eax, word ptr [rcx]
0x18000995e  test    ax, ax
0x180009961  jz      short loc_180009978
0x180009963  mov     [r8], ax
0x180009967  add     rcx, 2
0x18000996b  add     r8, 2
0x18000996f  dec     rsi
0x180009972  sub     rdx, 1
0x180009976  jnz     short loc_180009956
0x180009978  test    rdx, rdx
0x18000997b  lea     rcx, [r8-2]
0x18000997f  cmovnz  rcx, r8
0x180009983  xor     eax, eax
0x180009985  mov     [rcx], ax
0x180009988  jmp     loc_1800098F5
0x18000998d  lea     r9, [rbp+2470h+pszStart]
0x180009994  mov     edx, 824h; unsigned __int64
0x180009999  lea     r8, aSoftwareClasse; "Software\\Classes\\%s"
0x1800099a0  lea     rcx, [rbp+2470h+var_1090]; unsigned __int16 *
0x1800099a7  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800099ac  test    eax, eax
0x1800099ae  js      short loc_180009936
0x1800099b0  mov     r9d, r13d; unsigned int
0x1800099b3  mov     [rsp+2570h+var_2550], r12; unsigned __int16 **
0x1800099b8  lea     r8, [rbp+2470h+var_22F0]; unsigned __int16 *
0x1800099bf  mov     rcx, rsi; this
0x1800099c2  lea     rdx, [rbp+2470h+var_1090]; unsigned __int16 *
0x1800099c9  call    ?_getThemeSettingBSTR@CThemeFile@@AEAAJPEBG0KPEAPEAG@Z; CThemeFile::_getThemeSettingBSTR(ushort const *,ushort const *,ulong,ushort * *)
0x1800099ce  test    eax, eax
0x1800099d0  jns     loc_180009936
0x1800099d6  mov     rcx, [rsp+2570h+var_2510]
0x1800099db  mov     r8, r12
0x1800099de  mov     rdx, r15
0x1800099e1  mov     rax, [rcx]
0x1800099e4  mov     rax, [rax+170h]
0x1800099eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800099f0  mov     rdi, [rsp+2570h+arg_10]
0x1800099f8  jmp     loc_180009862
0x1800099fd  mov     rax, [r14]
0x180009a00  mov     rcx, r14
0x180009a03  mov     rax, [rax+10h]
0x180009a07  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009a0c  test    ebx, ebx
0x180009a0e  js      loc_18000998D
0x180009a14  mov     rcx, rdi; psz
0x180009a17  xor     ebx, ebx
0x180009a19  call    cs:__imp_SysAllocString
0x180009a1f  mov     [r12], rax
0x180009a23  test    rdi, rdi
0x180009a26  jz      short loc_180009A33
0x180009a28  test    rax, rax
0x180009a2b  mov     ecx, 8007000Eh
0x180009a30  cmovz   ebx, ecx
0x180009a33  mov     rcx, rdi; pv
0x180009a36  call    cs:__imp_CoTaskMemFree
0x180009a3c  jmp     loc_180009930
0x180009a41  lea     r9, [rbp+2470h+var_22F0]
0x180009a48  mov     [rsp+2570h+pszSource], rdi
0x180009a4d  lea     r8, aSMui; "%s.MUI"
0x180009a54  mov     edx, 104h; unsigned __int64
0x180009a59  lea     rcx, [rbp+2470h+var_1090]; unsigned __int16 *
0x180009a60  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180009a65  mov     r14, [rsp+2570h+var_2530]
0x180009a6a  test    eax, eax
0x180009a6c  js      short loc_180009AA4
0x180009a6e  mov     rax, [r14]
0x180009a71  lea     rcx, [rsp+2570h+pszSource]
0x180009a76  mov     [rsp+2570h+var_2548], rcx
0x180009a7b  lea     r8, [rbp+2470h+var_1090]
0x180009a82  xor     r9d, r9d
0x180009a85  mov     dword ptr [rsp+2570h+var_2550], 1
0x180009a8d  lea     rdx, [rbp+2470h+pszStart]
0x180009a94  mov     rcx, r14
0x180009a97  mov     rax, [rax+30h]
0x180009a9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009aa0  test    eax, eax
0x180009aa2  jns     short loc_180009AE0
0x180009aa4  mov     rax, [r14]
0x180009aa7  lea     rcx, [rsp+2570h+pszSource]
0x180009aac  mov     [rsp+2570h+var_2548], rcx
0x180009ab1  lea     r8, [rbp+2470h+var_22F0]
0x180009ab8  xor     r9d, r9d
0x180009abb  mov     dword ptr [rsp+2570h+var_2550], 1
0x180009ac3  lea     rdx, [rbp+2470h+pszStart]
0x180009aca  mov     rcx, r14
0x180009acd  mov     rax, [rax+30h]
0x180009ad1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009ad6  mov     ebx, eax
0x180009ad8  test    eax, eax
0x180009ada  js      loc_1800099FD
0x180009ae0  xor     edx, edx; Val
0x180009ae2  lea     rcx, [rsp+2570h+pszOutBuf]; void *
0x180009ae7  mov     r8d, 208h; Size
0x180009aed  call    memset_0
0x180009af2  mov     rcx, [rsp+2570h+pszSource]; pszSource
0x180009af7  lea     rdx, [rsp+2570h+pszOutBuf]; pszOutBuf
0x180009afc  xor     r9d, r9d; ppvReserved
0x180009aff  mov     r8d, 104h; cchOutBuf
0x180009b05  xor     r15d, r15d
0x180009b08  call    cs:__imp_SHLoadIndirectString
0x180009b0e  mov     ebx, eax
0x180009b10  test    eax, eax
0x180009b12  js      short loc_180009B3F
0x180009b14  lea     rcx, [rsp+2570h+pszOutBuf]; unsigned __int16 *
0x180009b19  call    ?ExpandResourceDir@@YAJPEAGK@Z; ExpandResourceDir(ushort *,ulong)
0x180009b1e  mov     ebx, eax
0x180009b20  test    eax, eax
0x180009b22  js      short loc_180009B3F
0x180009b24  mov     rcx, [rsi+30h]; unsigned __int16 *
0x180009b28  lea     rdx, [rsp+2570h+pszOutBuf]; unsigned __int16 *
0x180009b2d  call    ?ExpandThemeTokens@@YAJPEBGPEAGH@Z; ExpandThemeTokens(ushort const *,ushort *,int)
0x180009b32  mov     ebx, eax
0x180009b34  test    eax, eax
0x180009b36  js      short loc_180009B3F
0x180009b38  lea     r15, [rsp+2570h+pszOutBuf]
0x180009b3d  jmp     short loc_180009B43
0x180009b3f  test    ebx, ebx
0x180009b41  js      short loc_180009B99
0x180009b43  test    r13b, 2
0x180009b47  jz      short loc_180009B85
0x180009b49  lea     rcx, [rsp+2570h+pszOutBuf]; pszPath
0x180009b4e  call    cs:__imp_PathIsRelativeW
0x180009b54  test    eax, eax
0x180009b56  jnz     short loc_180009B85
0x180009b58  lea     r9, [rsp+2570h+var_2530]; unsigned int *
0x180009b5d  mov     dword ptr [rsp+2570h+var_2530], edi
0x180009b61  lea     rcx, [rsp+2570h+pszOutBuf]; unsigned __int16 *
0x180009b66  call    ?SHMapUrlToZoneEx@@YAJPEBGPEAUIUnknown@@KPEAK@Z; SHMapUrlToZoneEx(ushort const *,IUnknown *,ulong,ulong *)
0x180009b6b  cmp     [rsp+2570h+pszOutBuf], di
0x180009b70  jz      short loc_180009BAE
0x180009b72  cmp     dword ptr [rsp+2570h+var_2530], edi
0x180009b76  jz      short loc_180009BAE
0x180009b78  call    ?s_IsUncPathAllowedForThumbnailImage@CFileSource@@SAHXZ; CFileSource::s_IsUncPathAllowedForThumbnailImage(void)
0x180009b7d  test    eax, eax
0x180009b7f  jnz     short loc_180009BAE
0x180009b81  mov     [r15], ax
0x180009b85  lea     r9, [rsp+2570h+var_2520]
0x180009b8a  mov     r8, r15
0x180009b8d  call    ??$_AllocString@VCTCoAllocPolicy@@@@YAJPEAXKPEBGPEAPEAG@Z; _AllocString<CTCoAllocPolicy>(void *,ulong,ushort const *,ushort * *)
0x180009b92  mov     rdi, [rsp+2570h+var_2520]
0x180009b97  mov     ebx, eax
0x180009b99  mov     rcx, [rsp+2570h+pszSource]; pv
0x180009b9e  call    cs:__imp_CoTaskMemFree
0x180009ba4  mov     r15, [rsp+2570h+var_2518]
0x180009ba9  jmp     loc_1800099FD
0x180009bae  lea     rcx, [rsp+2570h+pszOutBuf]; unsigned __int16 *
0x180009bb3  call    ?ConfirmFile@@YAHPEAGH@Z; ConfirmFile(ushort *,int)
0x180009bb8  cmp     eax, 3
0x180009bbb  jnz     short loc_180009B85
0x180009bbd  mov     ebx, 80070002h
0x180009bc2  jmp     short loc_180009B99
```
