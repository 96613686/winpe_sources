# CreativeFramework::LockScreenCreativeConfigHelpers::PeekLockScreenRegistryKeys(ushort const *,ushort * *,ushort * *,ushort * *,bool *)

- ea: `0x18000a490`
- end: `0x18000ace9`
- name: `?PeekLockScreenRegistryKeys@LockScreenCreativeConfigHelpers@CreativeFramework@@YAJPEBGPEAPEAG11PEA_N@Z`
- size: `2137`
- prototype: `int(CreativeFramework::LockScreenCreativeConfigHelpers *__hidden this, const unsigned __int16 *, unsigned __int16 **, unsigned __int16 **, unsigned __int16 **, bool *)`
- caller_count: `4`
- callee_count: `13`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180009890`
- `0x18000bdcc`
- `0x180037e20`
- `0x1800422a0`

## callees

- `0x1800092d0`
- `0x1800093f0`
- `0x18000a24c`
- `0x18000a46c`
- `0x18000a490`
- `0x18000acf0`
- `0x18000af00`
- `0x18000b5b8`
- `0x18000c1b8`
- `0x180037140`
- `0x18003729c`
- `0x180054130`
- `0x180054ad4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcstoui64` at `0x18000a760`
- `api-ms-win-crt-private-l1-1-0!_o__wcstoui64` at `0x18000a760`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18000a6db`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18000a6db`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18000a743`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18000a743`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000ac94`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000ac94`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000a61b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000a61b`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000a828`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000a8bf`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000a9e3`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000ab7f`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000a828`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000a8bf`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000a9e3`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000ab7f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000a956`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000aaf6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000a956`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000aaf6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000a67c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000a694`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000ac7f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000a67c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000a694`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000ac7f`

## string_xrefs

- `0x18000a554`: `onecoreuap\internal\shell\inc\LockScreenCreativeConfigHelpers.h`
- `0x18000a5d5`: `onecoreuap\internal\shell\inc\LockScreenCreativeConfigHelpers.h`
- `0x18000a6f0`: `onecoreuap\internal\shell\inc\LockScreenCreativeConfigHelpers.h`
- `0x18000a7c1`: `onecoreuap\internal\shell\inc\LockScreenCreativeConfigHelpers.h`
- `0x18000a8fd`: `onecoreuap\internal\shell\inc\LockScreenCreativeConfigHelpers.h`
- `0x18000ac61`: `onecoreuap\internal\shell\inc\LockScreenCreativeConfigHelpers.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CreativeFramework::LockScreenCreativeConfigHelpers::PeekLockScreenRegistryKeys(
        CreativeFramework::LockScreenCreativeConfigHelpers *this,
        unsigned __int16 *a2,
        DWORD *a3,
        unsigned __int16 **a4,
        unsigned __int16 **a5)
{
  DWORD *v5; // r12
  HKEY v7; // rdi
  unsigned __int64 v8; // r13
  __int64 v9; // r8
  void *v10; // rbx
  unsigned int v11; // esi
  __int64 v12; // r9
  __int64 v13; // rdx
  int CurrentUserSidString; // eax
  int v15; // eax
  WCHAR *v16; // r14
  LSTATUS v17; // eax
  unsigned int v18; // eax
  __int64 v19; // rdx
  unsigned __int64 v20; // rbx
  DWORD i; // esi
  unsigned __int64 v22; // rax
  int v23; // eax
  __int64 v24; // rdx
  unsigned __int64 v25; // r9
  LSTATUS ValueW; // eax
  __int64 v27; // rdx
  __int64 v28; // rcx
  LSTATUS v29; // eax
  unsigned int v30; // ebx
  __int64 v31; // rdx
  unsigned __int64 v32; // r15
  unsigned __int64 v33; // r14
  _WORD *v34; // rax
  _WORD *v35; // rdx
  _QWORD *v36; // r15
  LSTATUS v37; // eax
  __int16 *v38; // rcx
  unsigned __int64 v39; // r8
  __int64 v40; // r10
  __int16 v41; // r9
  __int64 v42; // r9
  _WORD *v43; // rcx
  __int64 v44; // r14
  bool v45; // cf
  unsigned __int64 v46; // r14
  WCHAR *v47; // rdx
  unsigned int v48; // ebx
  _BYTE *v49; // rbx
  LSTATUS v50; // eax
  WCHAR *v51; // r9
  unsigned __int64 v52; // r8
  WCHAR *v53; // rax
  DWORD *v54; // rcx
  WCHAR v55; // r10
  DWORD *v56; // r9
  WCHAR *v57; // rcx
  unsigned __int64 v58; // r14
  int phkResult; // [rsp+20h] [rbp-E0h]
  unsigned int phkResulta; // [rsp+20h] [rbp-E0h]
  int phkResultb; // [rsp+20h] [rbp-E0h]
  LPVOID pv; // [rsp+60h] [rbp-A0h] BYREF
  LPCWSTR lpSubKey; // [rsp+68h] [rbp-98h] BYREF
  __int64 v65; // [rsp+70h] [rbp-90h]
  __int64 v66; // [rsp+78h] [rbp-88h]
  HKEY v67; // [rsp+80h] [rbp-80h] BYREF
  DWORD cSubKeys; // [rsp+88h] [rbp-78h] BYREF
  unsigned __int16 **v69; // [rsp+90h] [rbp-70h] BYREF
  DWORD v70; // [rsp+98h] [rbp-68h] BYREF
  DWORD cchName; // [rsp+A0h] [rbp-60h] BYREF
  DWORD pcbData; // [rsp+A4h] [rbp-5Ch] BYREF
  HKEY v73; // [rsp+A8h] [rbp-58h] BYREF
  unsigned __int16 **v74; // [rsp+B0h] [rbp-50h]
  _WORD v75[264]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR v76[264]; // [rsp+2D0h] [rbp+1D0h] BYREF
  WCHAR Name[256]; // [rsp+4E0h] [rbp+3E0h] BYREF
  WCHAR pvData[264]; // [rsp+6E0h] [rbp+5E0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+948h] [rbp+848h]

  v69 = a4;
  v5 = a3;
  v74 = a5;
  if ( a2 )
    *(_QWORD *)a2 = 0;
  if ( a3 )
    *(_QWORD *)a3 = 0;
  if ( a4 )
    *a4 = 0;
  if ( a5 )
    *(_BYTE *)a5 = 0;
  v7 = 0;
  v73 = 0;
  pv = 0;
  v8 = -1;
  if ( this )
  {
    v9 = -1;
    do
      ++v9;
    while ( *((_WORD *)this + v9) );
    wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
      &v70,
      this);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
      &pv,
      &v70);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v70);
    v10 = pv;
    if ( !pv )
    {
      v11 = -2147024882;
      v12 = 2147942414LL;
      v13 = 412;
LABEL_14:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v13,
        (unsigned int)"onecoreuap\\internal\\shell\\inc\\LockScreenCreativeConfigHelpers.h",
        (const char *)v12,
        phkResult);
LABEL_15:
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&pv);
LABEL_124:
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v73);
      return v11;
    }
  }
  else
  {
    pv = 0;
    CurrentUserSidString = CreativeFramework::LockScreenCreativeConfigHelpers::GetCurrentUserSidString(
                             (CreativeFramework::LockScreenCreativeConfigHelpers *)&pv,
                             a5);
    v11 = CurrentUserSidString;
    if ( CurrentUserSidString < 0 )
    {
      v12 = (unsigned int)CurrentUserSidString;
      v13 = 417;
      goto LABEL_14;
    }
    v10 = pv;
  }
  lpSubKey = 0;
  v65 = 0;
  v66 = 0;
  v15 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::InitializeFormat(
          &lpSubKey,
          L"%s\\%s",
          L"Software\\Microsoft\\Windows\\CurrentVersion\\Authentication\\LogonUI\\Creative",
          v10);
  v11 = v15;
  if ( v15 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1A5,
      (unsigned int)"onecoreuap\\internal\\shell\\inc\\LockScreenCreativeConfigHelpers.h",
      (const char *)(unsigned int)v15,
      phkResult);
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&lpSubKey);
    goto LABEL_15;
  }
  v67 = 0;
  v16 = (WCHAR *)lpSubKey;
  v17 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, lpSubKey, 0, 0x2001Fu, &v67);
  v11 = v17;
  if ( v17 )
  {
    if ( v17 > 0 )
      v11 = (unsigned __int16)v17 | 0x80070000;
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v67);
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&lpSubKey);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&pv);
    if ( (v11 & 0x80000000) != 0 )
      goto LABEL_124;
  }
  else
  {
    v7 = v67;
    v67 = 0;
    v73 = v7;
    if ( v16 )
      CoTaskMemFree(v16);
    if ( v10 )
      CoTaskMemFree(v10);
  }
  cSubKeys = 0;
  v18 = RegQueryInfoKeyW(v7, 0, 0, 0, &cSubKeys, 0, 0, 0, 0, 0, 0, 0);
  if ( v18 )
  {
    v19 = 441;
LABEL_32:
    v11 = wil::details::in1diag3::Return_Win32(
            retaddr,
            (void *)v19,
            (unsigned int)"onecoreuap\\internal\\shell\\inc\\LockScreenCreativeConfigHelpers.h",
            (const char *)v18,
            phkResulta);
    goto LABEL_124;
  }
  v20 = 0;
  for ( i = 0; i < cSubKeys; ++i )
  {
    cchName = 256;
    v18 = RegEnumKeyExW(v7, i, Name, &cchName, 0, 0, 0, 0);
    if ( v18 )
    {
      v19 = 447;
      goto LABEL_32;
    }
    v22 = _o__wcstoui64(Name, 0, 10);
    if ( v22 > v20 )
      v20 = v22;
  }
  if ( !v20 )
  {
    v11 = -2147024894;
    goto LABEL_124;
  }
  lpSubKey = 0;
  v65 = 0;
  v66 = 0;
  v23 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::InitializeFormat(
          &lpSubKey,
          L"%llu",
          v20);
  v11 = v23;
  if ( v23 < 0 )
  {
    v24 = 459;
LABEL_44:
    v25 = (unsigned int)v23;
LABEL_45:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v24,
      (unsigned int)"onecoreuap\\internal\\shell\\inc\\LockScreenCreativeConfigHelpers.h",
      (const char *)v25,
      phkResulta);
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&lpSubKey);
    goto LABEL_124;
  }
  if ( a2 )
  {
    pcbData = 522;
    ValueW = RegGetValueW(v7, lpSubKey, L"contentId", 0x20000002u, 0, pvData, &pcbData);
    v11 = ValueW;
    if ( ValueW > 0 )
      v11 = (unsigned __int16)ValueW | 0x80070000;
    if ( ((v11 + 0x80000000) & 0x80000000) == 0 && v11 != -2147024894 )
    {
      v25 = v11;
      v24 = 465;
      goto LABEL_45;
    }
    v23 = _AllocString<CTCoAllocPolicy>(v28, v27, pvData, a2);
    v11 = v23;
    if ( v23 < 0 )
    {
      v24 = 466;
      goto LABEL_44;
    }
  }
  if ( !v5 )
    goto LABEL_70;
  v70 = 522;
  v29 = RegGetValueW(v7, lpSubKey, L"landscapeImage", 0x20000002u, 0, v75, &v70);
  v30 = v29;
  if ( v29 > 0 )
    v30 = (unsigned __int16)v29 | 0x80070000;
  if ( (int)(v30 + 0x80000000) >= 0 && v30 != -2147024894 )
  {
    v31 = 473;
LABEL_60:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v31,
      (unsigned int)"onecoreuap\\internal\\shell\\inc\\LockScreenCreativeConfigHelpers.h",
      (const char *)v30,
      phkResultb);
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&lpSubKey);
    v11 = v30;
    goto LABEL_124;
  }
  v32 = -1;
  do
    ++v32;
  while ( v75[v32] );
  *(_QWORD *)v5 = 0;
  v33 = v32 + 1;
  if ( v32 + 1 < v32 || (pv = 0, !is_mul_ok(v33, 2u)) )
  {
    v30 = -2147024362;
    goto LABEL_89;
  }
  v34 = CoTaskMemAlloc(2 * v33);
  v35 = v34;
  *(_QWORD *)v5 = v34;
  v30 = v34 == 0 ? 0x8007000E : 0;
  v5 = 0;
  if ( !v34 )
  {
LABEL_89:
    v31 = 474;
    goto LABEL_60;
  }
  if ( v33 > 0x7FFFFFFF )
  {
LABEL_69:
    *v34 = 0;
    goto LABEL_70;
  }
  if ( v32 >= 0x7FFFFFFF )
  {
    if ( v32 == -1 )
      goto LABEL_70;
    goto LABEL_69;
  }
  v38 = v75;
  v39 = v32 + 1;
  v40 = 0;
  do
  {
    if ( !v32 )
      break;
    v41 = *v38;
    if ( !*v38 )
      break;
    ++v38;
    *v34++ = v41;
    --v32;
    ++v40;
    --v39;
  }
  while ( v39 );
  v42 = v40 - 1;
  if ( v39 )
    v42 = v40;
  v43 = v34 - 1;
  if ( v39 )
    v43 = v34;
  *v43 = 0;
  if ( v39 )
  {
    v45 = v33 == v42;
    v44 = v33 - v42;
    if ( !v45 && v44 != 1 && (unsigned __int64)(2 * v44) > 2 )
      memset_0(&v35[v42 + 1], 0, 2 * v44 - 2);
  }
LABEL_70:
  v36 = v69;
  if ( !v69 )
    goto LABEL_98;
  LODWORD(v67) = 522;
  v37 = RegGetValueW(v7, lpSubKey, L"portraitImage", 0x20000002u, v5, v76, (LPDWORD)&v67);
  v30 = v37;
  if ( v37 > 0 )
    v30 = (unsigned __int16)v37 | 0x80070000;
  if ( (int)(v30 + 0x80000000) >= 0 && v30 != -2147024894 )
  {
    v31 = 481;
    goto LABEL_60;
  }
  do
    ++v8;
  while ( v76[v8] != (_WORD)v5 );
  *v36 = v5;
  v46 = v8 + 1;
  if ( v8 + 1 >= v8 && (pv = v5, is_mul_ok(v46, 2u)) )
  {
    v47 = (WCHAR *)CoTaskMemAlloc(2 * v46);
    *v36 = v47;
    v48 = v47 == 0 ? 0x8007000E : 0;
    if ( v47 )
    {
      if ( v46 <= 0x7FFFFFFF )
      {
        if ( v8 < 0x7FFFFFFF )
        {
          v51 = v76;
          v52 = v8 + 1;
          v53 = v47;
          v54 = v5;
          do
          {
            if ( !v8 )
              break;
            v55 = *v51;
            if ( !*v51 )
              break;
            ++v51;
            *v53++ = v55;
            --v8;
            v54 = (DWORD *)((char *)v54 + 1);
            --v52;
          }
          while ( v52 );
          v56 = (DWORD *)((char *)v54 - 1);
          if ( v52 )
            v56 = v54;
          v57 = v53 - 1;
          if ( v52 )
            v57 = v53;
          *v57 = (unsigned __int16)v5;
          if ( v52 )
          {
            v45 = v46 == (_QWORD)v56;
            v58 = v46 - (_QWORD)v56;
            if ( !v45 && v58 != 1 && 2 * v58 > 2 )
              memset_0(&v47[(_QWORD)v56 + 1], 0, 2 * v58 - 2);
          }
LABEL_98:
          v49 = v74;
          if ( v74 )
          {
            LODWORD(v69) = (_DWORD)v5;
            LODWORD(pv) = 4;
            v50 = RegGetValueW(v7, lpSubKey, L"showImageOnSecureLock", 0x20000010u, v5, &v69, (LPDWORD)&pv);
            v11 = v50;
            if ( v50 > 0 )
              v11 = (unsigned __int16)v50 | 0x80070000;
            if ( (int)(v11 + 0x80000000) >= 0 && v11 != -2147024894 )
            {
              v25 = v11;
              v24 = 489;
              goto LABEL_45;
            }
            *v49 = (_DWORD)v69 != (_DWORD)v5;
          }
          Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&lpSubKey);
          v11 = (unsigned int)v5;
          goto LABEL_124;
        }
        if ( v8 == -1 )
          goto LABEL_98;
      }
      *v47 = (unsigned __int16)v5;
      goto LABEL_98;
    }
  }
  else
  {
    v48 = -2147024362;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x1E2,
    (unsigned int)"onecoreuap\\internal\\shell\\inc\\LockScreenCreativeConfigHelpers.h",
    (const char *)v48,
    phkResultb);
  if ( lpSubKey != (LPCWSTR)v5 )
    CoTaskMemFree((LPVOID)lpSubKey);
  if ( v7 )
    RegCloseKey(v7);
  return v48;
}

```

## disassembly

```asm
0x18000a490  push    rbp
0x18000a492  push    rbx
0x18000a493  push    rsi
0x18000a494  push    rdi
0x18000a495  push    r12
0x18000a497  push    r13
0x18000a499  push    r14
0x18000a49b  push    r15
0x18000a49d  lea     rbp, [rsp-808h]
0x18000a4a5  sub     rsp, 908h
0x18000a4ac  mov     rax, cs:__security_cookie
0x18000a4b3  xor     rax, rsp
0x18000a4b6  mov     [rbp+840h+var_50], rax
0x18000a4bd  mov     rax, r9
0x18000a4c0  mov     [rbp+840h+var_8B0], rax
0x18000a4c4  mov     r12, r8
0x18000a4c7  mov     r15, rdx
0x18000a4ca  mov     rdx, [rbp+840h+arg_20]; unsigned __int16 **
0x18000a4d1  mov     [rbp+840h+var_890], rdx
0x18000a4d5  xor     r14d, r14d
0x18000a4d8  test    r15, r15
0x18000a4db  jz      short loc_18000A4E0
0x18000a4dd  mov     [r15], r14
0x18000a4e0  test    r12, r12
0x18000a4e3  jz      short loc_18000A4E8
0x18000a4e5  mov     [r8], r14
0x18000a4e8  test    rax, rax
0x18000a4eb  jz      short loc_18000A4F0
0x18000a4ed  mov     [r9], r14
0x18000a4f0  test    rdx, rdx
0x18000a4f3  jz      short loc_18000A4F8
0x18000a4f5  mov     [rdx], r14b
0x18000a4f8  mov     rdi, r14
0x18000a4fb  mov     [rbp+840h+var_898], r14
0x18000a4ff  mov     [rsp+940h+pv], r14
0x18000a504  or      r13, 0FFFFFFFFFFFFFFFFh
0x18000a508  test    rcx, rcx
0x18000a50b  jz      short loc_18000A577
0x18000a50d  mov     r8, r13
0x18000a510  inc     r8
0x18000a513  cmp     [rcx+r8*2], r14w
0x18000a518  jnz     short loc_18000A510
0x18000a51a  mov     rdx, rcx
0x18000a51d  lea     rcx, [rbp+840h+var_8A8]
0x18000a521  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x18000a526  lea     rdx, [rbp+840h+var_8A8]
0x18000a52a  lea     rcx, [rsp+940h+pv]
0x18000a52f  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x18000a534  lea     rcx, [rbp+840h+var_8A8]
0x18000a538  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x18000a53d  mov     rbx, [rsp+940h+pv]
0x18000a542  test    rbx, rbx
0x18000a545  jnz     short loc_18000A59B
0x18000a547  mov     esi, 8007000Eh
0x18000a54c  mov     r9d, esi; char *
0x18000a54f  mov     edx, 19Ch; void *
0x18000a554  lea     r8, aOnecoreuapInte_1; "onecoreuap\\internal\\shell\\inc\\LockS"...
0x18000a55b  mov     rcx, [rbp+848h]; this
0x18000a562  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a567  nop
0x18000a568  lea     rcx, [rsp+940h+pv]
0x18000a56d  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x18000a572  jmp     loc_18000ACBA
0x18000a577  mov     [rsp+940h+pv], r14
0x18000a57c  lea     rcx, [rsp+940h+pv]; this
0x18000a581  call    ?GetCurrentUserSidString@LockScreenCreativeConfigHelpers@CreativeFramework@@YAJPEAPEAG@Z; CreativeFramework::LockScreenCreativeConfigHelpers::GetCurrentUserSidString(ushort * *)
0x18000a586  mov     esi, eax
0x18000a588  test    eax, eax
0x18000a58a  jns     short loc_18000A596
0x18000a58c  mov     r9d, eax
0x18000a58f  mov     edx, 1A1h
0x18000a594  jmp     short loc_18000A554
0x18000a596  mov     rbx, [rsp+940h+pv]
0x18000a59b  mov     [rsp+940h+lpSubKey], r14
0x18000a5a0  mov     [rsp+940h+var_8D0], r14
0x18000a5a5  mov     [rsp+940h+var_8C8], r14
0x18000a5aa  mov     r9, rbx
0x18000a5ad  lea     r8, ?c_logonUICreativeKeyPath@LockScreenCreativeConfigHelpers@CreativeFramework@@3QBGB; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18000a5b4  lea     rdx, aSS_1; "%s\\%s"
0x18000a5bb  lea     rcx, [rsp+940h+lpSubKey]
0x18000a5c0  call    ?InitializeFormat@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::InitializeFormat(ushort const *,...)
0x18000a5c5  mov     esi, eax
0x18000a5c7  test    eax, eax
0x18000a5c9  jns     short loc_18000A5F6
0x18000a5cb  mov     rcx, [rbp+848h]; this
0x18000a5d2  mov     r9d, eax; char *
0x18000a5d5  lea     r8, aOnecoreuapInte_1; "onecoreuap\\internal\\shell\\inc\\LockS"...
0x18000a5dc  mov     edx, 1A5h; void *
0x18000a5e1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a5e6  nop
0x18000a5e7  lea     rcx, [rsp+940h+lpSubKey]
0x18000a5ec  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18000a5f1  jmp     loc_18000A568
0x18000a5f6  mov     [rbp+840h+var_8C0], r14
0x18000a5fa  lea     rax, [rbp+840h+var_8C0]
0x18000a5fe  mov     [rsp+940h+phkResult], rax; phkResult
0x18000a603  mov     r9d, 2001Fh; samDesired
0x18000a609  xor     r8d, r8d; ulOptions
0x18000a60c  mov     r14, [rsp+940h+lpSubKey]
0x18000a611  mov     rdx, r14; lpSubKey
0x18000a614  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000a61b  call    cs:__imp_RegOpenKeyExW
0x18000a622  nop     dword ptr [rax+rax+00h]
0x18000a627  mov     esi, eax
0x18000a629  xor     ecx, ecx
0x18000a62b  test    eax, eax
0x18000a62d  jz      short loc_18000A668
0x18000a62f  xor     r14d, r14d
0x18000a632  test    eax, eax
0x18000a634  jle     short loc_18000A63F
0x18000a636  movzx   esi, ax
0x18000a639  or      esi, 80070000h
0x18000a63f  lea     rcx, [rbp+840h+var_8C0]
0x18000a643  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18000a648  nop
0x18000a649  lea     rcx, [rsp+940h+lpSubKey]
0x18000a64e  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18000a653  nop
0x18000a654  lea     rcx, [rsp+940h+pv]
0x18000a659  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x18000a65e  test    esi, esi
0x18000a660  js      loc_18000ACBA
0x18000a666  jmp     short loc_18000A6A0
0x18000a668  mov     rdi, [rbp+840h+var_8C0]
0x18000a66c  mov     [rbp+840h+var_8C0], rcx
0x18000a670  mov     [rbp+840h+var_898], rdi
0x18000a674  test    r14, r14
0x18000a677  jz      short loc_18000A689
0x18000a679  mov     rcx, r14; pv
0x18000a67c  call    cs:__imp_CoTaskMemFree
0x18000a683  nop     dword ptr [rax+rax+00h]
0x18000a688  nop
0x18000a689  xor     r14d, r14d
0x18000a68c  test    rbx, rbx
0x18000a68f  jz      short loc_18000A6A0
0x18000a691  mov     rcx, rbx; pv
0x18000a694  call    cs:__imp_CoTaskMemFree
0x18000a69b  nop     dword ptr [rax+rax+00h]
0x18000a6a0  mov     [rbp+840h+cSubKeys], r14d
0x18000a6a4  mov     [rsp+940h+lpftLastWriteTime], r14; lpftLastWriteTime
0x18000a6a9  mov     [rsp+940h+lpcbSecurityDescriptor], r14; lpcbSecurityDescriptor
0x18000a6ae  mov     [rsp+940h+lpcbMaxValueLen], r14; lpcbMaxValueLen
0x18000a6b3  mov     [rsp+940h+lpcbMaxValueNameLen], r14; lpcbMaxValueNameLen
0x18000a6b8  mov     [rsp+940h+lpcValues], r14; lpcValues
0x18000a6bd  mov     [rsp+940h+lpcbMaxClassLen], r14; lpcbMaxClassLen
0x18000a6c2  mov     [rsp+940h+lpcbMaxSubKeyLen], r14; lpcbMaxSubKeyLen
0x18000a6c7  lea     rax, [rbp+840h+cSubKeys]
0x18000a6cb  mov     [rsp+940h+phkResult], rax; int
0x18000a6d0  xor     r9d, r9d; lpReserved
0x18000a6d3  xor     r8d, r8d; lpcchClass
0x18000a6d6  xor     edx, edx; lpClass
0x18000a6d8  mov     rcx, rdi; hKey
0x18000a6db  call    cs:__imp_RegQueryInfoKeyW
0x18000a6e2  nop     dword ptr [rax+rax+00h]
0x18000a6e7  test    eax, eax
0x18000a6e9  jz      short loc_18000A70D
0x18000a6eb  mov     edx, 1B9h; void *
0x18000a6f0  lea     r8, aOnecoreuapInte_1; "onecoreuap\\internal\\shell\\inc\\LockS"...
0x18000a6f7  mov     r9d, eax; char *
0x18000a6fa  mov     rcx, [rbp+848h]; this
0x18000a701  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18000a706  mov     esi, eax
0x18000a708  jmp     loc_18000ACBA
0x18000a70d  mov     rbx, r14
0x18000a710  mov     esi, r14d
0x18000a713  cmp     esi, [rbp+840h+cSubKeys]
0x18000a716  jnb     short loc_18000A781
0x18000a718  mov     [rbp+840h+cchName], 100h
0x18000a71f  mov     [rsp+940h+lpcValues], r14; lpftLastWriteTime
0x18000a724  mov     [rsp+940h+lpcbMaxClassLen], r14; lpcchClass
0x18000a729  mov     [rsp+940h+lpcbMaxSubKeyLen], r14; lpClass
0x18000a72e  mov     [rsp+940h+phkResult], r14; lpReserved
0x18000a733  lea     r9, [rbp+840h+cchName]; lpcchName
0x18000a737  lea     r8, [rbp+840h+Name]; lpName
0x18000a73e  mov     edx, esi; dwIndex
0x18000a740  mov     rcx, rdi; hKey
0x18000a743  call    cs:__imp_RegEnumKeyExW
0x18000a74a  nop     dword ptr [rax+rax+00h]
0x18000a74f  test    eax, eax
0x18000a751  jnz     short loc_18000A777
0x18000a753  xor     edx, edx
0x18000a755  lea     r8d, [rax+0Ah]
0x18000a759  lea     rcx, [rbp+840h+Name]
0x18000a760  call    cs:__imp__o__wcstoui64
0x18000a767  nop     dword ptr [rax+rax+00h]
0x18000a76c  cmp     rax, rbx
0x18000a76f  cmova   rbx, rax
0x18000a773  inc     esi
0x18000a775  jmp     short loc_18000A713
0x18000a777  mov     edx, 1BFh
0x18000a77c  jmp     loc_18000A6F0
0x18000a781  test    rbx, rbx
0x18000a784  jnz     short loc_18000A790
0x18000a786  mov     esi, 80070002h
0x18000a78b  jmp     loc_18000ACBA
0x18000a790  mov     [rsp+940h+lpSubKey], r14
0x18000a795  mov     [rsp+940h+var_8D0], r14
0x18000a79a  mov     [rsp+940h+var_8C8], r14
0x18000a79f  mov     r8, rbx
0x18000a7a2  lea     rdx, aLlu; "%llu"
0x18000a7a9  lea     rcx, [rsp+940h+lpSubKey]
0x18000a7ae  call    ?InitializeFormat@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::InitializeFormat(ushort const *,...)
0x18000a7b3  mov     esi, eax
0x18000a7b5  test    eax, eax
0x18000a7b7  jns     short loc_18000A7E4
0x18000a7b9  mov     edx, 1CBh; void *
0x18000a7be  mov     r9d, eax; char *
0x18000a7c1  lea     r8, aOnecoreuapInte_1; "onecoreuap\\internal\\shell\\inc\\LockS"...
0x18000a7c8  mov     rcx, [rbp+848h]; this
0x18000a7cf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a7d4  nop
0x18000a7d5  lea     rcx, [rsp+940h+lpSubKey]
0x18000a7da  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18000a7df  jmp     loc_18000ACBA
0x18000a7e4  mov     ebx, 80000000h
0x18000a7e9  test    r15, r15
0x18000a7ec  jz      loc_18000A87E
0x18000a7f2  mov     [rbp+840h+pcbData], 20Ah
0x18000a7f9  lea     rax, [rbp+840h+pcbData]
0x18000a7fd  mov     [rsp+940h+lpcbMaxClassLen], rax; pcbData
0x18000a802  lea     rax, [rbp+840h+pvData]
0x18000a809  mov     [rsp+940h+lpcbMaxSubKeyLen], rax; pvData
0x18000a80e  mov     [rsp+940h+phkResult], r14; pdwType
0x18000a813  mov     r9d, 20000002h; dwFlags
0x18000a819  lea     r8, ?c_contentIdRegKey@LockScreenCreativeConfigHelpers@CreativeFramework@@3QBGB; "contentId"
0x18000a820  mov     rdx, [rsp+940h+lpSubKey]; lpSubKey
0x18000a825  mov     rcx, rdi; hkey
0x18000a828  call    cs:__imp_RegGetValueW
0x18000a82f  nop     dword ptr [rax+rax+00h]
0x18000a834  mov     esi, eax
0x18000a836  test    eax, eax
0x18000a838  jle     short loc_18000A843
0x18000a83a  movzx   esi, ax
0x18000a83d  or      esi, 80070000h
0x18000a843  lea     eax, [rsi+rbx]
0x18000a846  test    ebx, eax
0x18000a848  jnz     short loc_18000A85F
0x18000a84a  cmp     esi, 80070002h
0x18000a850  jz      short loc_18000A85F
0x18000a852  mov     r9d, esi
0x18000a855  mov     edx, 1D1h
0x18000a85a  jmp     loc_18000A7C1
0x18000a85f  mov     r9, r15
0x18000a862  lea     r8, [rbp+840h+pvData]
0x18000a869  call    ??$_AllocString@VCTCoAllocPolicy@@@@YAJPEAXKPEBGPEAPEAG@Z; _AllocString<CTCoAllocPolicy>(void *,ulong,ushort const *,ushort * *)
0x18000a86e  mov     esi, eax
0x18000a870  test    eax, eax
0x18000a872  jns     short loc_18000A87E
0x18000a874  mov     edx, 1D2h
0x18000a879  jmp     loc_18000A7BE
0x18000a87e  mov     esi, 8007000Eh
0x18000a883  test    r12, r12
0x18000a886  jz      loc_18000A9A0
0x18000a88c  mov     [rbp+840h+var_8A8], 20Ah
0x18000a893  lea     rax, [rbp+840h+var_8A8]
0x18000a897  mov     [rsp+940h+lpcbMaxClassLen], rax; pcbData
0x18000a89c  lea     rax, [rbp+840h+var_880]
0x18000a8a0  mov     [rsp+940h+lpcbMaxSubKeyLen], rax; pvData
0x18000a8a5  mov     [rsp+940h+phkResult], r14; int
0x18000a8aa  mov     r9d, 20000002h; dwFlags
0x18000a8b0  lea     r8, ?c_landscapeRegKey@LockScreenCreativeConfigHelpers@CreativeFramework@@3QBGB; "landscapeImage"
0x18000a8b7  mov     rdx, [rsp+940h+lpSubKey]; lpSubKey
0x18000a8bc  mov     rcx, rdi; hkey
0x18000a8bf  call    cs:__imp_RegGetValueW
0x18000a8c6  nop     dword ptr [rax+rax+00h]
0x18000a8cb  mov     ebx, eax
0x18000a8cd  test    eax, eax
0x18000a8cf  jle     short loc_18000A8DA
0x18000a8d1  movzx   ebx, ax
0x18000a8d4  or      ebx, 80070000h
0x18000a8da  mov     ecx, 80000000h
0x18000a8df  lea     eax, [rbx+rcx]
0x18000a8e2  test    ecx, eax
0x18000a8e4  jnz     short loc_18000A91B
0x18000a8e6  cmp     ebx, 80070002h
0x18000a8ec  jz      short loc_18000A91B
0x18000a8ee  mov     edx, 1D9h; void *
0x18000a8f3  mov     rcx, [rbp+848h]; this
0x18000a8fa  mov     r9d, ebx; char *
0x18000a8fd  lea     r8, aOnecoreuapInte_1; "onecoreuap\\internal\\shell\\inc\\LockS"...
0x18000a904  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a909  nop
0x18000a90a  lea     rcx, [rsp+940h+lpSubKey]
0x18000a90f  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18000a914  mov     esi, ebx
0x18000a916  jmp     loc_18000ACBA
0x18000a91b  lea     rax, [rbp+840h+var_880]
0x18000a91f  mov     r15, r13
0x18000a922  inc     r15
0x18000a925  cmp     [rax+r15*2], r14w
0x18000a92a  jnz     short loc_18000A922
0x18000a92c  mov     [r12], r14
0x18000a930  lea     r14, [r15+1]
0x18000a934  cmp     r14, r15
0x18000a937  jb      loc_18000AAAD
0x18000a93d  xor     ecx, ecx
0x18000a93f  mov     [rsp+940h+pv], rcx
0x18000a944  lea     eax, [rcx+2]
0x18000a947  mul     r14
0x18000a94a  test    rdx, rdx
  ... truncated ...
```
