# CThemeFile::GetSoundSchemeName(ushort * *)

- ea: `0x180009ea0`
- end: `0x18000a75a`
- name: `?GetSoundSchemeName@CThemeFile@@UEAAJPEAPEAG@Z`
- size: `2234`
- prototype: `__int64 __fastcall(CThemeFile *__hidden this, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `14`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x1800089c0`
- `0x180009ea0`
- `0x18000a9a0`
- `0x18000ab00`
- `0x18000ab10`
- `0x18000d490`
- `0x18000dd60`
- `0x180015190`
- `0x180015660`
- `0x180030f64`
- `0x1800333e8`
- `0x1800358c0`
- `0x18003633c`
- `0x18006d010`

## import_xrefs

- `SHLWAPI!__imp_SHLoadIndirectString` at `0x180009fe6`
- `SHLWAPI!__imp_SHLoadIndirectString` at `0x18000a400`
- `SHLWAPI!__imp_SHLoadIndirectString` at `0x180009fe6`
- `SHLWAPI!__imp_SHLoadIndirectString` at `0x18000a400`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18000a5e7`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18000a5e7`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000a23f`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000a42b`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000a655`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000a23f`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000a42b`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000a655`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000a030`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000a074`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000a317`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000a715`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000a030`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000a074`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000a317`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000a715`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000a208`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000a208`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000a174`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000a174`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18000a1d7`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18000a1d7`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000a3d7`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000a3d7`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18000a387`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18000a387`
- `OLEAUT32!__imp_SysAllocString` at `0x18000a054`
- `OLEAUT32!__imp_SysAllocString` at `0x18000a0b6`
- `OLEAUT32!__imp_SysAllocString` at `0x18000a054`
- `OLEAUT32!__imp_SysAllocString` at `0x18000a0b6`
- `OLEAUT32!__imp_SysFreeString` at `0x18000a0f3`
- `OLEAUT32!__imp_SysFreeString` at `0x18000a0ff`
- `OLEAUT32!__imp_SysFreeString` at `0x18000a0f3`
- `OLEAUT32!__imp_SysFreeString` at `0x18000a0ff`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CThemeFile::GetSoundSchemeName(CThemeFile *this, unsigned __int16 **a2)
{
  CThemeFile *v3; // r14
  const unsigned __int16 **v4; // rsi
  WCHAR *v5; // r13
  OLECHAR *v6; // rdi
  __int64 v7; // rbx
  int v8; // eax
  LPCWCH v9; // r14
  HRESULT v10; // r15d
  unsigned int v11; // edx
  int v12; // r8d
  __int64 v13; // rdx
  __int64 v14; // rcx
  int v15; // esi
  BSTR v16; // rax
  signed int SoundSchemeDisplayName; // esi
  const unsigned __int16 *v18; // r14
  unsigned __int16 *v19; // rax
  LPWSTR v20; // rax
  int v21; // r15d
  unsigned __int16 **v22; // rbx
  LSTATUS v24; // eax
  LSTATUS v25; // eax
  int v26; // esi
  __int64 v27; // rdi
  int j; // esi
  const WCHAR *v29; // rcx
  WCHAR *v30; // rdx
  LPWSTR v31; // rcx
  WCHAR v32; // ax
  unsigned int v33; // r8d
  const WCHAR *v34; // rcx
  WCHAR *v35; // rdx
  WCHAR v36; // ax
  WCHAR *v37; // rax
  WCHAR *v38; // r14
  char v39; // r10
  LSTATUS v40; // eax
  LSTATUS ValueW; // eax
  __int64 v42; // rcx
  WCHAR *v43; // rdx
  __int64 v44; // r8
  WCHAR *v45; // r9
  WCHAR v46; // ax
  WCHAR *v47; // rax
  DWORD i; // r14d
  WCHAR v49; // dx
  const WCHAR *v50; // rax
  __int64 v51; // rcx
  WCHAR *v52; // rax
  CThemeFile *v53; // rax
  unsigned __int16 *v54; // rax
  unsigned int v55; // r8d
  const WCHAR *v56; // rax
  WCHAR *v57; // rdx
  __int64 v58; // rdi
  WCHAR *v59; // rax
  signed int Error; // eax
  WCHAR v61; // r8
  const WCHAR *v62; // rax
  __int64 v63; // rcx
  WCHAR *v64; // rax
  int v65; // eax
  CThemeFile *v66; // rcx
  unsigned __int16 *v67; // rax
  CThemeFile *v68; // rax
  bool v69; // di
  bool v70; // zf
  PCWSTR pszSource; // [rsp+60h] [rbp-A0h] BYREF
  LPWSTR lpBuffer; // [rsp+68h] [rbp-98h]
  CThemeFile *v73; // [rsp+70h] [rbp-90h]
  LPCWCH lpString1; // [rsp+78h] [rbp-88h] BYREF
  DWORD cSubKeys; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int16 **v76; // [rsp+88h] [rbp-78h]
  DWORD pcbData[2]; // [rsp+90h] [rbp-70h] BYREF
  DWORD cchClass; // [rsp+98h] [rbp-68h] BYREF
  DWORD cchName; // [rsp+9Ch] [rbp-64h] BYREF
  BSTR v80[2]; // [rsp+A0h] [rbp-60h] BYREF
  WCHAR pszOutBuf[264]; // [rsp+B0h] [rbp-50h] BYREF
  WCHAR Name[264]; // [rsp+2C0h] [rbp+1C0h] BYREF
  WCHAR String1[264]; // [rsp+4D0h] [rbp+3D0h] BYREF
  WCHAR Class[264]; // [rsp+6E0h] [rbp+5E0h] BYREF

  v76 = a2;
  v3 = this;
  v73 = this;
  lpBuffer = (LPWSTR)((char *)this + 804);
  if ( !*((_WORD *)this + 402) )
  {
    v4 = (const unsigned __int16 **)((char *)this - 16);
    v5 = 0;
    v80[0] = 0;
    v6 = 0;
    *(_QWORD *)pcbData = 0;
    lpString1 = 0;
    v7 = 260;
    if ( (int)CThemeFile::_GetCachedProfile(
                (CThemeFile *)((char *)this - 16),
                1,
                (struct ICachedPrivateProfile **)&lpString1) >= 0 )
    {
      pszSource = 0;
      v8 = StringCchPrintfW(Name, 0x104u, L"%s.MUI", L"SchemeName");
      v9 = lpString1;
      if ( v8 >= 0
        && (*(int (__fastcall **)(LPCWCH, const unsigned __int16 *, WCHAR *, _QWORD, int, PCWSTR *))(*(_QWORD *)lpString1 + 48LL))(
             lpString1,
             L"Sounds",
             Name,
             0,
             1,
             &pszSource) >= 0
        || (v10 = (*(__int64 (__fastcall **)(LPCWCH, const unsigned __int16 *, const unsigned __int16 *, _QWORD, int, PCWSTR *))(*(_QWORD *)v9 + 48LL))(
                    v9,
                    L"Sounds",
                    L"SchemeName",
                    0,
                    1,
                    &pszSource),
            v10 >= 0) )
      {
        memset_0(pszOutBuf, 0, 0x208u);
        v10 = SHLoadIndirectString(pszSource, pszOutBuf, 0x104u, 0);
        if ( v10 >= 0 )
        {
          v10 = ExpandResourceDir(pszOutBuf, v11);
          if ( v10 >= 0 )
          {
            v10 = ExpandThemeTokens(v4[6], pszOutBuf, v12);
            if ( v10 >= 0 )
            {
              v10 = _AllocString<CTCoAllocPolicy>(v14, v13, pszOutBuf, pcbData);
              v6 = *(OLECHAR **)pcbData;
            }
          }
        }
        CoTaskMemFree((LPVOID)pszSource);
      }
      (*(void (__fastcall **)(LPCWCH))(*(_QWORD *)v9 + 16LL))(v9);
      if ( v10 >= 0 )
      {
        v15 = 0;
        v16 = SysAllocString(v6);
        v5 = v16;
        v80[0] = v16;
        if ( v6 && !v16 )
          v15 = -2147024882;
        CoTaskMemFree(v6);
        if ( v15 >= 0 )
        {
          if ( ATL::CComBSTR::Length((ATL::CComBSTR *)v80) )
          {
            if ( !v5
              || (v38 = (WCHAR *)((char *)v73 + 1326),
                  lpString1 = (LPCWCH)((char *)v73 + 1326),
                  v73 == (CThemeFile *)-1326LL) )
            {
              SoundSchemeDisplayName = -2147024809;
            }
            else
            {
              pszSource = 0;
              v24 = RegOpenKeyExW(HKEY_CURRENT_USER, L"AppEvents\\Schemes\\Names", 0, 0x20019u, (PHKEY)&pszSource);
              SoundSchemeDisplayName = v24;
              if ( v24 > 0 )
                SoundSchemeDisplayName = (unsigned __int16)v24 | 0x80070000;
              if ( SoundSchemeDisplayName >= 0 )
              {
                cchClass = 260;
                cSubKeys = 0;
                v25 = RegQueryInfoKeyW((HKEY)pszSource, Class, &cchClass, 0, &cSubKeys, 0, 0, 0, 0, 0, 0, 0);
                v26 = v25;
                if ( v25 > 0 )
                  v26 = (unsigned __int16)v25 | 0x80070000;
                v27 = 2147483646;
                v21 = -2147024774;
                if ( v26 < 0 )
                  goto LABEL_42;
                for ( i = 0; ; ++i )
                {
                  v39 = 0;
                  if ( i >= cSubKeys )
                  {
                    v38 = (WCHAR *)lpString1;
                    goto LABEL_85;
                  }
                  cchName = 260;
                  v40 = RegEnumKeyExW((HKEY)pszSource, i, Name, &cchName, 0, 0, 0, 0);
                  v26 = v40;
                  if ( v40 > 0 )
                    v26 = (unsigned __int16)v40 | 0x80070000;
                  if ( v26 >= 0 )
                  {
                    pcbData[0] = 520;
                    ValueW = RegGetValueW((HKEY)pszSource, Name, 0, 2u, 0, pszOutBuf, pcbData);
                    v26 = ValueW;
                    if ( ValueW )
                    {
                      pszOutBuf[0] = 0;
                      if ( ValueW > 0 )
                        v26 = (unsigned __int16)ValueW | 0x80070000;
                    }
                    if ( v26 >= 0 )
                    {
                      v26 = SHLoadIndirectString(pszOutBuf, String1, 0x104u, 0);
                      if ( v26 >= 0 && CompareStringOrdinal(String1, -1, v5, -1, 1) == 2 )
                        break;
                    }
                  }
                }
                v39 = 1;
                v42 = 2147483646;
                v43 = Name;
                v44 = 260;
                v38 = (WCHAR *)lpString1;
                v45 = (WCHAR *)lpString1;
                do
                {
                  if ( !v42 )
                    break;
                  v46 = *v43;
                  if ( !*v43 )
                    break;
                  ++v43;
                  *v45++ = v46;
                  --v42;
                  --v44;
                }
                while ( v44 );
                v47 = v45 - 1;
                if ( v44 )
                  v47 = v45;
                *v47 = 0;
                v26 = -2147024774;
                if ( v44 )
                  v26 = 0;
LABEL_85:
                if ( v26 < 0 || !v39 )
LABEL_42:
                  *v38 = 0;
                RegCloseKey((HKEY)pszSource);
                if ( *v38 )
                {
                  for ( j = 0; ; ++j )
                  {
                    v29 = (const WCHAR *)(&c_rgszInBoxSoundSchemes)[j];
                    if ( !*v29 )
                      break;
                    if ( CompareStringOrdinal(v29, -1, v38, -1, 1) == 2 )
                    {
                      v30 = v5;
                      v18 = lpBuffer;
                      v31 = lpBuffer;
                      do
                      {
                        if ( !v27 )
                          break;
                        v32 = *v30;
                        if ( !*v30 )
                          break;
                        ++v30;
                        *v31++ = v32;
                        --v27;
                        --v7;
                      }
                      while ( v7 );
                      v20 = v31 - 1;
                      if ( v7 )
                        v20 = v31;
                      *v20 = 0;
                      if ( v7 )
                        v21 = 0;
                      SoundSchemeDisplayName = v21;
                      if ( v7 )
                      {
                        v65 = CompareStringOrdinal(lpString1, -1, L".None", -1, 1);
                        v66 = v73;
                        *((_BYTE *)v73 + 1324) = v65 == 2;
                        *((_BYTE *)v66 + 1846) = 1;
                        v67 = v5;
                        v5 = 0;
                        *v76 = v67;
                        goto LABEL_30;
                      }
                      goto LABEL_29;
                    }
                  }
                }
                pszSource = 0;
                SoundSchemeDisplayName = (*(__int64 (__fastcall **)(CThemeFile *, PCWSTR *))(*(_QWORD *)v73 + 352LL))(
                                           v73,
                                           &pszSource);
                if ( SoundSchemeDisplayName >= 0 )
                {
                  if ( *pszSource )
                  {
                    if ( *v38 )
                      goto LABEL_99;
                    v50 = L"Custom";
                    v51 = 260;
                    do
                    {
                      if ( !v27 )
                        break;
                      v49 = *v50;
                      if ( !*v50 )
                        break;
                      ++v50;
                      *v38++ = v49;
                      --v27;
                      --v51;
                    }
                    while ( v51 );
                    SoundSchemeDisplayName = -2147024774;
                    if ( v51 )
                      SoundSchemeDisplayName = 0;
                    v52 = v38 - 1;
                    if ( v51 )
                      v52 = v38;
                    *v52 = 0;
                    if ( v51 )
                    {
LABEL_99:
                      v18 = lpBuffer;
                      SoundSchemeDisplayName = StringCchCopyW(lpBuffer, 0x104u, v5);
                      if ( SoundSchemeDisplayName >= 0 )
                      {
                        v53 = v73;
                        *((_BYTE *)v73 + 1324) = 0;
                        *((_BYTE *)v53 + 1846) = 0;
                        v54 = v5;
                        v5 = 0;
                        *v76 = v54;
                      }
                      goto LABEL_64;
                    }
                  }
                  else
                  {
                    v34 = L".Default";
                    v35 = v38;
                    do
                    {
                      if ( !v27 )
                        break;
                      v36 = *v34;
                      if ( !*v34 )
                        break;
                      ++v34;
                      *v35++ = v36;
                      --v27;
                      --v7;
                    }
                    while ( v7 );
                    SoundSchemeDisplayName = -2147024774;
                    if ( v7 )
                      SoundSchemeDisplayName = 0;
                    v37 = v35 - 1;
                    if ( v7 )
                      v37 = v35;
                    *v37 = 0;
                    if ( v7 )
                    {
                      v18 = lpBuffer;
                      SoundSchemeDisplayName = GetSoundSchemeDisplayName(lpString1, lpBuffer, v33);
                      if ( SoundSchemeDisplayName >= 0 )
                      {
                        v68 = v73;
                        *((_BYTE *)v73 + 1324) = 0;
                        *((_BYTE *)v68 + 1846) = 1;
                        SoundSchemeDisplayName = HrSysAllocString(v18, v76);
                      }
                      goto LABEL_64;
                    }
                  }
                  v18 = lpBuffer;
LABEL_64:
                  CoTaskMemFree((LPVOID)pszSource);
                  goto LABEL_65;
                }
              }
            }
            v18 = lpBuffer;
LABEL_29:
            *v18 = 0;
            v22 = v76;
            SysFreeString(*v76);
            *v22 = 0;
LABEL_30:
            SysFreeString(v5);
            v3 = v73;
            goto LABEL_31;
          }
        }
      }
      v3 = v73;
    }
    v69 = 1;
    lpString1 = 0;
    if ( (*(int (__fastcall **)(CThemeFile *, LPCWCH *))(*(_QWORD *)v3 + 352LL))(v3, &lpString1) >= 0 )
    {
      v69 = *lpString1 == 0;
      CoTaskMemFree((LPVOID)lpString1);
    }
    v57 = (WCHAR *)((char *)v3 + 1326);
    v70 = !v69;
    v58 = 2147483646;
    if ( v70 )
    {
      *((_BYTE *)v3 + 1846) = 0;
      v62 = L"Custom";
      v63 = 260;
      do
      {
        if ( !v58 )
          break;
        v61 = *v62;
        if ( !*v62 )
          break;
        ++v62;
        *v57++ = v61;
        --v58;
        --v63;
      }
      while ( v63 );
      SoundSchemeDisplayName = -2147024774;
      if ( v63 )
        SoundSchemeDisplayName = 0;
      v64 = v57 - 1;
      if ( v63 )
        v64 = v57;
      *v64 = 0;
      v18 = lpBuffer;
      if ( !v63 )
        goto LABEL_29;
      if ( LoadStringW(g_hinst, 0x809u, lpBuffer, 260) )
        goto LABEL_122;
      Error = ResultFromKnownLastError();
    }
    else
    {
      *((_BYTE *)v3 + 1846) = 1;
      v56 = L".Default";
      do
      {
        if ( !v58 )
          break;
        v55 = *v56;
        if ( !(_WORD)v55 )
          break;
        ++v56;
        *v57++ = v55;
        --v58;
        --v7;
      }
      while ( v7 );
      SoundSchemeDisplayName = -2147024774;
      if ( v7 )
        SoundSchemeDisplayName = 0;
      v59 = v57 - 1;
      if ( v7 )
        v59 = v57;
      *v59 = 0;
      v18 = lpBuffer;
      if ( !v7 )
      {
LABEL_121:
        if ( SoundSchemeDisplayName < 0 )
          goto LABEL_29;
LABEL_122:
        *((_BYTE *)v73 + 1324) = 0;
        SoundSchemeDisplayName = HrSysAllocString(v18, v76);
LABEL_65:
        if ( SoundSchemeDisplayName >= 0 )
          goto LABEL_30;
        goto LABEL_29;
      }
      Error = GetSoundSchemeDisplayName(L".Default", lpBuffer, v55);
    }
    SoundSchemeDisplayName = Error;
    goto LABEL_121;
  }
  SoundSchemeDisplayName = 0;
  if ( a2 )
  {
    v19 = SysAllocString((const OLECHAR *)this + 402);
    *a2 = v19;
    if ( !v19 )
      SoundSchemeDisplayName = -2147024882;
  }
LABEL_31:
  if ( SoundSchemeDisplayName >= 0 && *((_BYTE *)v3 + 1324) )
    return 1;
  return (unsigned int)SoundSchemeDisplayName;
}

```

## disassembly

```asm
0x180009ea0  mov     [rsp-8+arg_10], rbx
0x180009ea5  push    rbp
0x180009ea6  push    rsi
0x180009ea7  push    rdi
0x180009ea8  push    r12
0x180009eaa  push    r13
0x180009eac  push    r14
0x180009eae  push    r15
0x180009eb0  lea     rbp, [rsp-800h]
0x180009eb8  sub     rsp, 900h
0x180009ebf  mov     rax, cs:__security_cookie
0x180009ec6  xor     rax, rsp
0x180009ec9  mov     [rbp+830h+var_40], rax
0x180009ed0  mov     rbx, rdx
0x180009ed3  mov     [rbp+830h+var_8A8], rdx
0x180009ed7  mov     r14, rcx
0x180009eda  mov     [rsp+930h+var_8C0], rcx
0x180009edf  lea     rax, [rcx+324h]
0x180009ee6  mov     [rsp+930h+lpBuffer], rax
0x180009eeb  mov     r15d, 1
0x180009ef1  cmp     word ptr [rax], 0
0x180009ef5  jnz     loc_18000A0A8
0x180009efb  lea     rsi, [rcx-10h]
0x180009eff  xor     r12d, r12d
0x180009f02  mov     r13d, r12d
0x180009f05  mov     [rbp+830h+var_890], r12
0x180009f09  mov     edi, r12d
0x180009f0c  mov     qword ptr [rbp+830h+pcbData], r12
0x180009f10  mov     [rsp+930h+lpString1], r12
0x180009f15  lea     r8, [rsp+930h+lpString1]; struct ICachedPrivateProfile **
0x180009f1a  movzx   edx, r15b; bool
0x180009f1e  mov     rcx, rsi; this
0x180009f21  call    ?_GetCachedProfile@CThemeFile@@AEAAJ_NPEAPEAUICachedPrivateProfile@@@Z; CThemeFile::_GetCachedProfile(bool,ICachedPrivateProfile * *)
0x180009f26  mov     ebx, 104h
0x180009f2b  test    eax, eax
0x180009f2d  js      loc_18000A6E5
0x180009f33  mov     [rsp+930h+pszSource], r12
0x180009f38  lea     r9, aSchemename; "SchemeName"
0x180009f3f  lea     r8, aSMui; "%s.MUI"
0x180009f46  mov     edx, ebx; unsigned __int64
0x180009f48  lea     rcx, [rbp+830h+Name]; unsigned __int16 *
0x180009f4f  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180009f54  mov     r14, [rsp+930h+lpString1]
0x180009f59  test    eax, eax
0x180009f5b  js      short loc_180009F90
0x180009f5d  mov     rax, [r14]
0x180009f60  lea     rcx, [rsp+930h+pszSource]
0x180009f65  mov     [rsp+930h+lpcbMaxSubKeyLen], rcx
0x180009f6a  mov     dword ptr [rsp+930h+phkResult], r15d
0x180009f6f  xor     r9d, r9d
0x180009f72  lea     r8, [rbp+830h+Name]
0x180009f79  lea     rdx, aSounds; "Sounds"
0x180009f80  mov     rcx, r14
0x180009f83  mov     rax, [rax+30h]
0x180009f87  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009f8c  test    eax, eax
0x180009f8e  jns     short loc_180009FC6
0x180009f90  mov     rax, [r14]
0x180009f93  lea     rcx, [rsp+930h+pszSource]
0x180009f98  mov     [rsp+930h+lpcbMaxSubKeyLen], rcx
0x180009f9d  mov     dword ptr [rsp+930h+phkResult], r15d
0x180009fa2  xor     r9d, r9d
0x180009fa5  lea     r8, aSchemename; "SchemeName"
0x180009fac  lea     rdx, aSounds; "Sounds"
0x180009fb3  mov     rcx, r14
0x180009fb6  mov     rax, [rax+30h]
0x180009fba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009fbf  mov     r15d, eax
0x180009fc2  test    eax, eax
0x180009fc4  js      short loc_18000A036
0x180009fc6  xor     edx, edx; Val
0x180009fc8  mov     r8d, 208h; Size
0x180009fce  lea     rcx, [rbp+830h+pszOutBuf]; void *
0x180009fd2  call    memset_0
0x180009fd7  xor     r9d, r9d; ppvReserved
0x180009fda  mov     r8d, ebx; cchOutBuf
0x180009fdd  lea     rdx, [rbp+830h+pszOutBuf]; pszOutBuf
0x180009fe1  mov     rcx, [rsp+930h+pszSource]; pszSource
0x180009fe6  call    cs:__imp_SHLoadIndirectString
0x180009fec  mov     r15d, eax
0x180009fef  test    eax, eax
0x180009ff1  js      short loc_18000A02B
0x180009ff3  lea     rcx, [rbp+830h+pszOutBuf]; unsigned __int16 *
0x180009ff7  call    ?ExpandResourceDir@@YAJPEAGK@Z; ExpandResourceDir(ushort *,ulong)
0x180009ffc  mov     r15d, eax
0x180009fff  test    eax, eax
0x18000a001  js      short loc_18000A02B
0x18000a003  lea     rdx, [rbp+830h+pszOutBuf]; unsigned __int16 *
0x18000a007  mov     rcx, [rsi+30h]; unsigned __int16 *
0x18000a00b  call    ?ExpandThemeTokens@@YAJPEBGPEAGH@Z; ExpandThemeTokens(ushort const *,ushort *,int)
0x18000a010  mov     r15d, eax
0x18000a013  test    eax, eax
0x18000a015  js      short loc_18000A02B
0x18000a017  lea     r9, [rbp+830h+pcbData]
0x18000a01b  lea     r8, [rbp+830h+pszOutBuf]
0x18000a01f  call    ??$_AllocString@VCTCoAllocPolicy@@@@YAJPEAXKPEBGPEAPEAG@Z; _AllocString<CTCoAllocPolicy>(void *,ulong,ushort const *,ushort * *)
0x18000a024  mov     r15d, eax
0x18000a027  mov     rdi, qword ptr [rbp+830h+pcbData]
0x18000a02b  mov     rcx, [rsp+930h+pszSource]; pv
0x18000a030  call    cs:__imp_CoTaskMemFree
0x18000a036  mov     rax, [r14]
0x18000a039  mov     rcx, r14
0x18000a03c  mov     rax, [rax+10h]
0x18000a040  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a045  test    r15d, r15d
0x18000a048  js      loc_18000A6E0
0x18000a04e  mov     esi, r12d
0x18000a051  mov     rcx, rdi; psz
0x18000a054  call    cs:__imp_SysAllocString
0x18000a05a  mov     r13, rax
0x18000a05d  mov     [rbp+830h+var_890], rax
0x18000a061  test    rdi, rdi
0x18000a064  jz      short loc_18000A071
0x18000a066  mov     ecx, 8007000Eh
0x18000a06b  test    rax, rax
0x18000a06e  cmovz   esi, ecx
0x18000a071  mov     rcx, rdi; pv
0x18000a074  call    cs:__imp_CoTaskMemFree
0x18000a07a  test    esi, esi
0x18000a07c  js      loc_18000A6E0
0x18000a082  lea     rcx, [rbp+830h+var_890]; this
0x18000a086  call    ?Length@CComBSTR@ATL@@QEBAIXZ; ATL::CComBSTR::Length(void)
0x18000a08b  test    eax, eax
0x18000a08d  jz      loc_18000A6E0
0x18000a093  test    r13, r13
0x18000a096  jnz     loc_18000A32A
0x18000a09c  mov     esi, 80070057h
0x18000a0a1  mov     r14, [rsp+930h+lpBuffer]
0x18000a0a6  jmp     short loc_18000A0E8
0x18000a0a8  xor     r12d, r12d
0x18000a0ab  mov     esi, r12d
0x18000a0ae  test    rbx, rbx
0x18000a0b1  jz      short loc_18000A110
0x18000a0b3  mov     rcx, rax; psz
0x18000a0b6  call    cs:__imp_SysAllocString
0x18000a0bc  mov     [rbx], rax
0x18000a0bf  mov     ecx, 8007000Eh
0x18000a0c4  test    rax, rax
0x18000a0c7  cmovz   esi, ecx
0x18000a0ca  jmp     short loc_18000A110
0x18000a0cc  lea     rax, [rcx-2]
0x18000a0d0  test    rbx, rbx
0x18000a0d3  cmovnz  rax, rcx
0x18000a0d7  mov     [rax], r12w
0x18000a0db  cmovnz  r15d, r12d
0x18000a0df  mov     esi, r15d
0x18000a0e2  jnz     loc_18000A638
0x18000a0e8  mov     [r14], r12w
0x18000a0ec  mov     rbx, [rbp+830h+var_8A8]
0x18000a0f0  mov     rcx, [rbx]; bstrString
0x18000a0f3  call    cs:__imp_SysFreeString
0x18000a0f9  mov     [rbx], r12
0x18000a0fc  mov     rcx, r13; bstrString
0x18000a0ff  call    cs:__imp_SysFreeString
0x18000a105  mov     r14, [rsp+930h+var_8C0]
0x18000a10a  mov     r15d, 1
0x18000a110  test    esi, esi
0x18000a112  jns     short loc_18000A140
0x18000a114  mov     eax, esi
0x18000a116  mov     rcx, [rbp+830h+var_40]
0x18000a11d  xor     rcx, rsp; StackCookie
0x18000a120  call    __security_check_cookie
0x18000a125  mov     rbx, [rsp+930h+arg_10]
0x18000a12d  add     rsp, 900h
0x18000a134  pop     r15
0x18000a136  pop     r14
0x18000a138  pop     r13
0x18000a13a  pop     r12
0x18000a13c  pop     rdi
0x18000a13d  pop     rsi
0x18000a13e  pop     rbp
0x18000a13f  retn
0x18000a140  cmp     byte ptr [r14+52Ch], 0
0x18000a148  cmovnz  esi, r15d
0x18000a14c  jmp     short loc_18000A114
0x18000a14e  mov     [rsp+930h+pszSource], r12
0x18000a153  lea     rax, [rsp+930h+pszSource]
0x18000a158  mov     [rsp+930h+phkResult], rax; phkResult
0x18000a15d  mov     r9d, 20019h; samDesired
0x18000a163  xor     r8d, r8d; ulOptions
0x18000a166  lea     rdx, aAppeventsSchem_14; "AppEvents\\Schemes\\Names"
0x18000a16d  mov     rcx, 0FFFFFFFF80000001h; hKey
0x18000a174  call    cs:__imp_RegOpenKeyExW
0x18000a17a  mov     esi, eax
0x18000a17c  test    eax, eax
0x18000a17e  jle     short loc_18000A189
0x18000a180  movzx   esi, ax
0x18000a183  or      esi, 80070000h
0x18000a189  test    esi, esi
0x18000a18b  js      loc_18000A0A1
0x18000a191  mov     [rbp+830h+cchClass], ebx
0x18000a194  mov     [rbp+830h+cSubKeys], r12d
0x18000a198  mov     [rsp+930h+lpftLastWriteTime], r12; lpftLastWriteTime
0x18000a19d  mov     [rsp+930h+lpcbSecurityDescriptor], r12; lpcbSecurityDescriptor
0x18000a1a2  mov     [rsp+930h+lpcbMaxValueLen], r12; lpcbMaxValueLen
0x18000a1a7  mov     [rsp+930h+lpcbMaxValueNameLen], r12; lpcbMaxValueNameLen
0x18000a1ac  mov     [rsp+930h+lpcValues], r12; lpcValues
0x18000a1b1  mov     [rsp+930h+lpcbMaxClassLen], r12; lpcbMaxClassLen
0x18000a1b6  mov     [rsp+930h+lpcbMaxSubKeyLen], r12; lpcbMaxSubKeyLen
0x18000a1bb  lea     rax, [rbp+830h+cSubKeys]
0x18000a1bf  mov     [rsp+930h+phkResult], rax; lpcSubKeys
0x18000a1c4  xor     r9d, r9d; lpReserved
0x18000a1c7  lea     r8, [rbp+830h+cchClass]; lpcchClass
0x18000a1cb  lea     rdx, [rbp+830h+Class]; lpClass
0x18000a1d2  mov     rcx, [rsp+930h+pszSource]; hKey
0x18000a1d7  call    cs:__imp_RegQueryInfoKeyW
0x18000a1dd  mov     esi, eax
0x18000a1df  test    eax, eax
0x18000a1e1  jle     short loc_18000A1EC
0x18000a1e3  movzx   esi, ax
0x18000a1e6  or      esi, 80070000h
0x18000a1ec  mov     edi, 7FFFFFFEh
0x18000a1f1  mov     r15d, 8007007Ah
0x18000a1f7  test    esi, esi
0x18000a1f9  jns     loc_18000A61F
0x18000a1ff  mov     [r14], r12w
0x18000a203  mov     rcx, [rsp+930h+pszSource]; hKey
0x18000a208  call    cs:__imp_RegCloseKey
0x18000a20e  cmp     [r14], r12w
0x18000a212  jz      short loc_18000A28E
0x18000a214  mov     esi, r12d
0x18000a217  lea     rcx, ?c_rgszInBoxSoundSchemes@@3QBQEBGB; ushort const * const near * const c_rgszInBoxSoundSchemes
0x18000a21e  movsxd  rax, esi
0x18000a221  mov     rcx, [rcx+rax*8]; lpString1
0x18000a225  cmp     [rcx], r12w
0x18000a229  jz      short loc_18000A28E
0x18000a22b  mov     dword ptr [rsp+930h+phkResult], 1; bIgnoreCase
0x18000a233  mov     r9d, 0FFFFFFFFh; cchCount2
0x18000a239  mov     r8, r14; lpString2
0x18000a23c  mov     edx, r9d; cchCount1
0x18000a23f  call    cs:__imp_CompareStringOrdinal
0x18000a245  cmp     eax, 2
0x18000a248  jnz     loc_18000A631
0x18000a24e  mov     rdx, r13
0x18000a251  mov     r14, [rsp+930h+lpBuffer]
0x18000a256  mov     rcx, r14
0x18000a259  nop     dword ptr [rax+00000000h]
0x18000a260  test    rdi, rdi
0x18000a263  jz      loc_18000A0CC
0x18000a269  movzx   eax, word ptr [rdx]
0x18000a26c  test    ax, ax
0x18000a26f  jz      loc_18000A0CC
0x18000a275  add     rdx, 2
0x18000a279  mov     [rcx], ax
0x18000a27c  add     rcx, 2
0x18000a280  dec     rdi
0x18000a283  sub     rbx, 1
0x18000a287  jnz     short loc_18000A260
0x18000a289  jmp     loc_18000A0CC
0x18000a28e  mov     [rsp+930h+pszSource], r12
0x18000a293  mov     rcx, [rsp+930h+var_8C0]
0x18000a298  mov     rax, [rcx]
0x18000a29b  lea     rdx, [rsp+930h+pszSource]
0x18000a2a0  mov     rax, [rax+160h]
0x18000a2a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a2ac  mov     esi, eax
0x18000a2ae  test    eax, eax
0x18000a2b0  js      loc_18000A0A1
0x18000a2b6  mov     rax, [rsp+930h+pszSource]
0x18000a2bb  cmp     [rax], r12w
0x18000a2bf  jnz     loc_18000A685
0x18000a2c5  lea     rcx, aDefault; ".Default"
0x18000a2cc  mov     rdx, r14
0x18000a2cf  nop
0x18000a2d0  test    rdi, rdi
0x18000a2d3  jz      short loc_18000A2F1
0x18000a2d5  movzx   eax, word ptr [rcx]
0x18000a2d8  test    ax, ax
0x18000a2db  jz      short loc_18000A2F1
0x18000a2dd  add     rcx, 2
0x18000a2e1  mov     [rdx], ax
0x18000a2e4  add     rdx, 2
0x18000a2e8  dec     rdi
0x18000a2eb  sub     rbx, 1
0x18000a2ef  jnz     short loc_18000A2D0
0x18000a2f1  mov     esi, r15d
0x18000a2f4  test    rbx, rbx
0x18000a2f7  cmovnz  esi, r12d
0x18000a2fb  lea     rax, [rdx-2]
0x18000a2ff  cmovnz  rax, rdx
0x18000a303  mov     [rax], r12w
0x18000a307  jnz     loc_18000A69E
0x18000a30d  mov     r14, [rsp+930h+lpBuffer]
0x18000a312  mov     rcx, [rsp+930h+pszSource]; pv
0x18000a317  call    cs:__imp_CoTaskMemFree
0x18000a31d  test    esi, esi
0x18000a31f  jns     loc_18000A0FC
0x18000a325  jmp     loc_18000A0E8
0x18000a32a  mov     r14, [rsp+930h+var_8C0]
0x18000a32f  add     r14, 52Eh
0x18000a336  mov     [rsp+930h+lpString1], r14
0x18000a33b  jz      loc_18000A09C
0x18000a341  jmp     loc_18000A14E
0x18000a350  xor     r10b, r10b
0x18000a353  cmp     r14d, [rbp+830h+cSubKeys]
0x18000a357  jnb     loc_18000A627
0x18000a35d  mov     [rbp+830h+cchName], ebx
0x18000a360  mov     [rsp+930h+lpcValues], r12; lpftLastWriteTime
0x18000a365  mov     [rsp+930h+lpcbMaxClassLen], r12; lpcchClass
0x18000a36a  mov     [rsp+930h+lpcbMaxSubKeyLen], r12; lpClass
  ... truncated ...
```
