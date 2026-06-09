# CRegFolder::_GetDisplayName(IDLREGITEM const *,ulong,ushort * *)

- ea: `0x180091620`
- end: `0x18009258a`
- name: `?_GetDisplayName@CRegFolder@@AEAAJPEFBUIDLREGITEM@@KPEAPEAG@Z`
- size: `3946`
- prototype: `int(CRegFolder *__hidden this, const struct IDLREGITEM *, unsigned int, unsigned __int16 **)`
- caller_count: `9`
- callee_count: `41`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180063a50`
- `0x18008b7b0`
- `0x18008fb60`
- `0x180092730`
- `0x1800b57c0`
- `0x1800c2920`
- `0x1805426c8`
- `0x180544240`
- `0x1805453a0`

## callees

- `0x180009fc0`
- `0x180012d30`
- `0x1800625e0`
- `0x180063050`
- `0x180064ad0`
- `0x18007bf50`
- `0x18007dcf0`
- `0x1800899a4`
- `0x1800899e0`
- `0x180089b40`
- `0x18008c740`
- `0x18008e7a0`
- `0x18008ec90`
- `0x18008ecb0`
- `0x18008fb60`
- `0x180091244`
- `0x180091620`
- `0x180092590`
- `0x180092970`
- `0x180092a70`
- `0x180095130`
- `0x1800c6e20`
- `0x1800c8920`
- `0x1800d1d80`
- `0x1800dd900`
- `0x1800fa0f8`
- `0x1801356e4`
- `0x1801357b0`
- `0x18020f710`
- `0x18028ec20`
- `0x1802952c8`
- `0x1802d03bc`
- `0x1803554b0`
- `0x1803b1f60`
- `0x1803b29ea`
- `0x1803b2ac0`
- `0x1803b69b9`
- `0x1803b69c5`
- `0x1803e187c`
- `0x18054298c`
- `0x18067d010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180092510`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180092510`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180091891`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18009235c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180091891`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18009235c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800923a4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800923a4`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18009178e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18009178e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180092381`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180092381`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180091a24`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180091a24`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180091afb`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180091c5d`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180091afb`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180091c5d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180091cef`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180091cef`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180091a48`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180091b52`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180091c23`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180091db9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180091e45`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180092261`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180092278`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180092293`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009233a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180091a48`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180091b52`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180091c23`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180091db9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180091e45`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180092261`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180092278`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180092293`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009233a`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800921c6`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800921c6`
- `SHCORE!__imp_SHRegGetCLSIDKey` at `0x1800919e7`
- `SHCORE!__imp_SHRegGetCLSIDKey` at `0x1800919e7`
- `SHCORE!__imp_StrRetToStrW` at `0x180091bc0`
- `SHCORE!__imp_StrRetToStrW` at `0x180091ebb`
- `SHCORE!__imp_StrRetToStrW` at `0x180091bc0`
- `SHCORE!__imp_StrRetToStrW` at `0x180091ebb`
- `SHCORE!__imp_IsAppCompatModeEnabled` at `0x180092181`
- `SHCORE!__imp_IsAppCompatModeEnabled` at `0x180092181`

## string_xrefs

- `0x180092313`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall CRegFolder::_GetDisplayName(
        struct IShellItem2 *this,
        const struct IDLREGITEM *a2,
        unsigned int a3,
        unsigned __int16 **a4)
{
  unsigned int v4; // r15d
  const struct IDLREGITEM *v5; // rdi
  struct IShellItem2 *v6; // r14
  int v7; // ebx
  unsigned __int64 v8; // rax
  __int64 v9; // rdx
  unsigned __int64 v10; // rax
  __int64 v11; // rdx
  const struct IDLREGITEM *v12; // rax
  __m128i v13; // xmm0
  int v14; // esi
  CCLSIDInfoCache *v15; // rcx
  HRESULT CachedRegFolder; // r12d
  unsigned __int64 v17; // rax
  __int64 v18; // r8
  const struct IDLREGITEM *v19; // rax
  struct _GUID *v20; // rax
  CCLSIDInfoCache *v21; // rcx
  HDSA v22; // rsi
  int v23; // r15d
  int v24; // r14d
  int v25; // r15d
  int v26; // eax
  int v27; // ebx
  const struct CLSID_CACHE_ENTRY *v28; // rdx
  int v29; // eax
  const struct CLSID_CACHE_ENTRY *v30; // rdx
  int v31; // eax
  __int64 v32; // rax
  const struct IDLREGITEM *v33; // rbx
  const struct IDLREGITEM *v34; // rsi
  _WORD *v35; // rcx
  int v36; // eax
  struct IShellItem2 *v37; // r14
  __int64 v38; // rcx
  unsigned __int64 v39; // rbx
  LPWSTR v40; // rax
  __int64 v41; // rdx
  __int64 v42; // r9
  struct IShellItem2 *v43; // r8
  WCHAR v44; // cx
  struct IShellItem2 *v45; // rcx
  unsigned __int16 v46; // ax
  const ITEMIDLIST *v47; // rbx
  IShellFolder *v48; // rcx
  LPWSTR v49; // rax
  int lpVtbl; // ebx
  const char *v52; // r9
  struct IShellItem2 *v53; // r15
  __int64 v54; // rcx
  char *v55; // rax
  size_t v56; // rbx
  size_t v57; // r14
  WCHAR *v58; // rax
  WCHAR *v59; // rsi
  struct IShellItem2 *v60; // rcx
  HKEY v61; // rbx
  __int64 v62; // rax
  int v63; // eax
  struct IShellItem2 *v64; // rax
  int v65; // eax
  int v66; // eax
  wil::details::in1diag3 *v67; // rcx
  __int64 v68; // rdx
  struct IShellItem2 *v69; // rcx
  IShellFolder *v70; // rbx
  ITEMIDLIST *v71; // rsi
  _WORD *v72; // rcx
  int v73; // eax
  int v74; // eax
  LPWSTR *cotaskmem_string_nothrow; // rdi
  WCHAR *v76; // rsi
  CCLSIDInfoCache *v77; // rcx
  CCLSIDInfoCache *v78; // rcx
  void **v79; // rax
  int v80; // r9d
  int v81; // eax
  CCLSIDInfoCache *v82; // rcx
  int v83; // r10d
  const ITEMIDLIST *FolderIDList; // rax
  int v85; // eax
  __int64 v86; // rcx
  void **ppv; // [rsp+20h] [rbp-E0h]
  unsigned int *v88; // [rsp+28h] [rbp-D8h]
  unsigned __int16 *v89; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v90; // [rsp+38h] [rbp-C8h]
  __int64 v91; // [rsp+40h] [rbp-C0h]
  unsigned __int16 **v92; // [rsp+48h] [rbp-B8h]
  struct IShellItem2 *v93; // [rsp+50h] [rbp-B0h] BYREF
  LPVOID pv; // [rsp+58h] [rbp-A8h] BYREF
  LPWSTR ppsz; // [rsp+60h] [rbp-A0h] BYREF
  IShellFolder *psf; // [rsp+68h] [rbp-98h] BYREF
  HKEY hKey; // [rsp+70h] [rbp-90h] BYREF
  struct _GUID v98; // [rsp+78h] [rbp-88h] BYREF
  __int64 v99; // [rsp+88h] [rbp-78h]
  __m128i Buf1; // [rsp+90h] [rbp-70h] BYREF
  struct _GUID pitem; // [rsp+A0h] [rbp-60h] BYREF
  __int128 v102; // [rsp+B0h] [rbp-50h]
  __int64 v103; // [rsp+C0h] [rbp-40h]
  struct _GUID v104; // [rsp+C8h] [rbp-38h] BYREF
  __int128 v105; // [rsp+D8h] [rbp-28h]
  __int64 v106; // [rsp+E8h] [rbp-18h]
  STRRET pstr; // [rsp+F0h] [rbp-10h] BYREF
  int v108; // [rsp+200h] [rbp+100h] BYREF
  OLECHAR sz[46]; // [rsp+204h] [rbp+104h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2B8h] [rbp+1B8h]

  v92 = a4;
  v4 = a3;
  LODWORD(hKey) = a3;
  v5 = a2;
  v6 = this;
  v93 = this;
  v7 = 0;
  LODWORD(psf) = 0;
  *a4 = 0;
  ppsz = 0;
  if ( !a2 )
    goto LABEL_6;
  v8 = *(unsigned __int16 *)a2;
  if ( (unsigned int)v8 <= 7
    || (v9 = *((unsigned __int16 *)a2 + 2), v8 < v9 + 38)
    || (Buf1 = *(__m128i *)((char *)v5 + v9 + 6), memcmp_0(&Buf1, qword_1807187A0, 0x10u)) )
  {
    v10 = *(unsigned __int16 *)v5;
    if ( (unsigned int)v10 > 7 )
    {
      v11 = *((unsigned __int16 *)v5 + 2);
      if ( v10 >= v11 + 38 )
      {
        Buf1 = *(__m128i *)((char *)v5 + v11 + 6);
        if ( !memcmp_0(&Buf1, qword_1807187A0, 0x10u) )
        {
          v13 = *(__m128i *)((char *)v5 + *((unsigned __int16 *)v5 + 2) + 22);
          goto LABEL_9;
        }
      }
    }
LABEL_6:
    if ( *((_BYTE *)v5 + 2) == LOBYTE(v6[45].lpVtbl) )
      v12 = v5;
    else
      v12 = (const struct IDLREGITEM *)((char *)v5 + HIDWORD(v6[44].lpVtbl));
    v13 = *(__m128i *)((char *)v12 + 4);
LABEL_9:
    Buf1 = v13;
    v14 = 0;
    ppsz = 0;
    if ( _mm_cvtsi128_si32(v13) != HIDWORD(v6[46].lpVtbl) )
      goto LABEL_10;
    lpVtbl = (int)v6[46].lpVtbl;
    if ( GetTickCount() - lpVtbl < 0x1F4 )
    {
      if ( !_InterlockedIncrement((volatile signed __int32 *)&v6[45].lpVtbl + 1)
        && !memcmp_0(&Buf1, (char *)&v6[46].lpVtbl + 4, 0x10u)
        && HIDWORD(v6[48].lpVtbl) == v4 )
      {
        v53 = v6 + 49;
        if ( v6 == (struct IShellItem2 *)-392LL )
          wil::details::in1diag3::_FailFast_Unexpected(
            retaddr,
            (void *)0xF89,
            (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
            v52);
        v54 = 0x7FFFFFFF;
        v55 = (char *)&v6[49];
        do
        {
          if ( !*(_WORD *)v55 )
            break;
          v55 += 2;
          --v54;
        }
        while ( v54 );
        v56 = 2 * ((v55 - (char *)v53) >> 1);
        v57 = v56 + 2;
        v58 = (WCHAR *)CoTaskMemAlloc(v56 + 2);
        v59 = v58;
        if ( v58 )
        {
          if ( v56 )
          {
            if ( v57 < v56 )
            {
              memset_0(v58, 0, v57);
              *(_DWORD *)_o__errno(v86) = 34;
              invalid_parameter_noinfo();
            }
            else
            {
              memcpy_0(v58, v53, v56);
            }
          }
          v59[v56 / 2] = 0;
        }
        v6 = v93;
        _InterlockedDecrement((volatile signed __int32 *)&v93[45].lpVtbl + 1);
        ppsz = v59;
        v14 = 1;
        v4 = (unsigned int)hKey;
        v7 = 0;
LABEL_10:
        if ( v14 )
        {
          CachedRegFolder = 0;
LABEL_95:
          v49 = ppsz;
          ppsz = 0;
          *v92 = v49;
          goto LABEL_96;
        }
        v15 = (CCLSIDInfoCache *)ppsz;
        if ( ppsz )
          wil::details::close_invoke_helper<1,void (*)(void *),&void CoTaskMemFree(void *),unsigned short *>::close_reset(ppsz);
        ppsz = 0;
        psf = 0;
        CachedRegFolder = 1;
        if ( v5
          && (v17 = *(unsigned __int16 *)v5, (unsigned int)v17 > 7)
          && (v18 = *((unsigned __int16 *)v5 + 2), v15 = (CCLSIDInfoCache *)(v18 + 38), v17 >= v18 + 38)
          && (v98 = *(struct _GUID *)((char *)v5 + v18 + 6), !memcmp_0(&v98, qword_1807187A0, 0x10u)) )
        {
          v20 = (struct _GUID *)((char *)v5 + *((unsigned __int16 *)v5 + 2) + 22);
        }
        else
        {
          if ( *((_BYTE *)v5 + 2) == LOBYTE(v6[45].lpVtbl) )
            v19 = v5;
          else
            v19 = (const struct IDLREGITEM *)((char *)v5 + HIDWORD(v6[44].lpVtbl));
          v20 = (struct _GUID *)((char *)v19 + 4);
        }
        v98 = *v20;
        if ( (v4 & 0xC001) == 0x8000 )
        {
          pitem = 0;
          v102 = 0;
          v103 = 0;
          if ( (unsigned int)CCLSIDInfoCache::_EnsureCacheIsValid(v15, 0) )
          {
            AcquireSRWLockShared(&g_clsidInfoCache);
            v105 = 0;
            v106 = 0;
            v104 = v98;
            v22 = hdsa;
            if ( hdsa )
              v23 = *(_DWORD *)hdsa;
            else
              v23 = 0;
            v24 = 0;
            v25 = v23 - 1;
            while ( v24 <= v25 )
            {
              v26 = (v25 + v24) / 2;
              v27 = v26;
              v28 = 0;
              if ( v22 && v26 >= 0 && v26 < *(_DWORD *)v22 )
                v28 = (const struct CLSID_CACHE_ENTRY *)(*((_QWORD *)v22 + 1)
                                                       + (unsigned int)(*((_DWORD *)v22 + 5) * v26));
              v29 = CCLSIDInfoCache::s_CompareEntries((const struct CLSID_CACHE_ENTRY *)&v104, v28, 0);
              if ( v29 < 0 )
              {
                v25 = v27 - 1;
              }
              else
              {
                if ( v29 <= 0 )
                {
                  for ( ; v27 > 0; --v27 )
                  {
                    v30 = 0;
                    if ( v22 )
                    {
                      v31 = v27 - 1;
                      if ( v27 - 1 >= 0 && v31 < *(_DWORD *)v22 )
                        v30 = (const struct CLSID_CACHE_ENTRY *)(*((_QWORD *)v22 + 1)
                                                               + (unsigned int)(*((_DWORD *)v22 + 5) * v31));
                    }
                    if ( (unsigned int)CCLSIDInfoCache::s_CompareEntries(
                                         (const struct CLSID_CACHE_ENTRY *)&v104,
                                         v30,
                                         0) )
                      break;
                  }
                  if ( v27 != -1 )
                  {
                    v32 = 0;
                    if ( v22 && v27 >= 0 && v27 < *(_DWORD *)v22 )
                      v32 = *((_QWORD *)v22 + 1) + (unsigned int)(*((_DWORD *)v22 + 5) * v27);
                    pitem = *(struct _GUID *)v32;
                    v102 = *(_OWORD *)(v32 + 16);
                    v103 = *(_QWORD *)(v32 + 32);
                    ReleaseSRWLockShared(&g_clsidInfoCache);
                    v4 = (unsigned int)hKey;
                    goto LABEL_45;
                  }
                  break;
                }
                v24 = v27 + 1;
              }
            }
            ReleaseSRWLockShared(&g_clsidInfoCache);
            pitem = v98;
            CCLSIDInfoCache::_LoadValuesFromRegistry(v77, (struct CLSID_CACHE_ENTRY *)&pitem);
            AcquireSRWLockExclusive(&g_clsidInfoCache);
            if ( (unsigned int)CCLSIDInfoCache::_EnsureCacheIsValid(v78, 1) )
            {
              v81 = CDSA_Base<CLSID_CACHE_ENTRY>::Search(&hdsa, &pitem);
              if ( !(unsigned int)CCLSIDInfoCache::_IsEntry(v82, &v98, v81) )
                DSA_InsertItem(hdsa, v83, &pitem);
            }
            ReleaseSRWLockExclusive(&g_clsidInfoCache);
            v4 = (unsigned int)hKey;
          }
          else
          {
            pitem = v98;
            CCLSIDInfoCache::_LoadValuesFromRegistry(v21, (struct CLSID_CACHE_ENTRY *)&pitem);
          }
LABEL_45:
          v7 = (HIDWORD(v103) >> 3) & 1;
        }
        else
        {
          if ( (v4 & 0x8000) != 0 && (v4 & 0x4000) == 0 )
          {
            v37 = v93;
            goto LABEL_70;
          }
          hKey = 0;
          if ( (int)SHRegGetCLSIDKey(&v98, 0, 1, 0, 1, &hKey) >= 0 )
          {
            v79 = (void **)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::put(&psf);
            if ( SHRegAllocData(hKey, 0, 0, v80, v79, v88) < 0 )
              wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
                &psf,
                0);
          }
          if ( !psf && (unsigned int)CCLSIDInfoCache::GetFolderValue(v38, &v98, 1) )
            v7 = 1;
          if ( hKey )
            RegCloseKey(hKey);
        }
        if ( !v7 )
          goto LABEL_67;
        v33 = v5;
        hKey = 0;
        v34 = 0;
        v35 = (_WORD *)((char *)v5 + *(unsigned __int16 *)v5);
        if ( v35 && *v35 )
        {
          v33 = (const struct IDLREGITEM *)ILCloneFirst((LPCITEMIDLIST)v5);
          v36 = 0;
          if ( !v33 )
            v36 = -2147024882;
          CachedRegFolder = v36;
          if ( !v33 )
            goto LABEL_67;
          v34 = v33;
        }
        if ( (!(unsigned int)IsDelegateRegId(v33) || !v33)
          && (!memcmp_0(&GUID_000214e6_0000_0000_c000_000000000046, &IID_IIdentityName, 0x10u)
           || !memcmp_0(&GUID_000214e6_0000_0000_c000_000000000046, &IID_IDelegateItem, 0x10u)) )
        {
          pv = 0;
          v37 = v93;
          CachedRegFolder = CRegFolder::_CreateCachedRegFolder(
                              (CRegFolder *)v93,
                              v33,
                              0,
                              &GUID_000214e6_0000_0000_c000_000000000046,
                              &pv);
          if ( CachedRegFolder >= 0 )
          {
            CachedRegFolder = (*(__int64 (__fastcall **)(LPVOID, _QWORD, GUID *, HKEY *))(*(_QWORD *)pv + 64LL))(
                                pv,
                                0,
                                &GUID_000214e6_0000_0000_c000_000000000046,
                                &hKey);
            (*(void (__fastcall **)(LPVOID))(*(_QWORD *)pv + 16LL))(pv);
          }
          goto LABEL_123;
        }
        if ( memcmp_0(&GUID_000214e6_0000_0000_c000_000000000046, &IID_ICapabilities, 0x10u) )
        {
          v37 = v93;
          CachedRegFolder = CRegFolder::_CreateCachedRegFolder(
                              (CRegFolder *)v93,
                              v33,
                              0,
                              &GUID_000214e6_0000_0000_c000_000000000046,
                              (void **)&hKey);
          if ( CachedRegFolder != -2147467262 )
          {
LABEL_123:
            CoTaskMemFree(v34);
            if ( CachedRegFolder >= 0 )
            {
              if ( psf )
                wil::details::close_invoke_helper<1,void (*)(void *),&void CoTaskMemFree(void *),unsigned short *>::close_reset(psf);
              v61 = hKey;
              psf = 0;
              memset_0(&pstr, 0, sizeof(pstr));
              CachedRegFolder = (*(__int64 (__fastcall **)(HKEY, const ITEMIDLIST *, _QWORD, STRRET *))(*(_QWORD *)v61 + 88LL))(
                                  v61,
                                  &c_idlDesktop,
                                  v4,
                                  &pstr);
              if ( CachedRegFolder )
              {
                if ( CachedRegFolder == -2147467263 )
                  CachedRegFolder = 1;
              }
              else
              {
                CachedRegFolder = StrRetToStrW(&pstr, &c_idlDesktop, (LPWSTR *)&psf);
              }
              (*(void (__fastcall **)(HKEY))(*(_QWORD *)hKey + 16LL))(hKey);
            }
            goto LABEL_68;
          }
          if ( !memcmp_0(&GUID_000214e6_0000_0000_c000_000000000046, &IID_IPropertyStoreFactory, 0x10u) )
          {
            v93 = 0;
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v93);
            CachedRegFolder = CRegFolder::_GetTargetFileSystemItem((CRegFolder *)v37, v33, &v93);
            if ( CachedRegFolder >= 0 )
            {
              ppv = (void **)&hKey;
              CachedRegFolder = ((__int64 (__fastcall *)(struct IShellItem2 *, _QWORD, const GUID *, GUID *))v93->lpVtbl->BindToHandler)(
                                  v93,
                                  0,
                                  &BHID_SFObject,
                                  &GUID_000214e6_0000_0000_c000_000000000046);
            }
            v60 = v93;
            if ( v93 )
            {
              v93 = 0;
              ((void (__fastcall *)(struct IShellItem2 *))v60->lpVtbl->Release)(v60);
            }
            goto LABEL_123;
          }
          CoTaskMemFree(v34);
LABEL_68:
          if ( psf )
            ppsz = (LPWSTR)psf;
LABEL_70:
          v39 = -1;
          if ( CachedRegFolder != 1 )
          {
LABEL_71:
            if ( CachedRegFolder < 0 )
              goto LABEL_96;
            v40 = ppsz;
            do
              ++v39;
            while ( ppsz[v39] );
            if ( v39 < 0x40 )
            {
              if ( !_InterlockedIncrement((volatile signed __int32 *)&v37[45].lpVtbl + 1) )
              {
                v41 = 2147483646;
                v42 = 64;
                v43 = v37 + 49;
                do
                {
                  if ( !v41 )
                    break;
                  v44 = *v40;
                  if ( !*v40 )
                    break;
                  ++v40;
                  LOWORD(v43->lpVtbl) = v44;
                  v43 = (struct IShellItem2 *)((char *)v43 + 2);
                  --v41;
                  --v42;
                }
                while ( v42 );
                v45 = (struct IShellItem2 *)((char *)v43 - 2);
                if ( v42 )
                  v45 = v43;
                LOWORD(v45->lpVtbl) = 0;
                HIDWORD(v37[48].lpVtbl) = v4;
                *(__m128i *)((char *)&v37[46].lpVtbl + 4) = Buf1;
                LODWORD(v37[46].lpVtbl) = GetTickCount();
              }
              _InterlockedDecrement((volatile signed __int32 *)&v37[45].lpVtbl + 1);
            }
            goto LABEL_95;
          }
          v89 = 0;
          v90 = 0;
          v91 = 0;
          *(_QWORD *)&v98.Data1 = 0;
          *(_QWORD *)v98.Data4 = 0;
          v99 = 0;
          if ( (v4 & 0x8000) != 0 )
          {
            if ( (v4 & 1) == 0 && !(unsigned int)CRegFolder::_IsDesktop((CRegFolder *)v37) )
            {
              v90 = -1;
              v91 = -1;
              FolderIDList = (const ITEMIDLIST *)CRegFolder::_GetFolderIDList((CRegFolder *)v37);
              v85 = SHGetNameAndFlagsAlloc(FolderIDList, v4);
              if ( v85 < 0 )
                wil::details::in1diag3::_Log_Hr(
                  retaddr,
                  (void *)0x6D7,
                  (unsigned int)"onecoreuap\\shell\\windows.storage\\regfldr.cpp",
                  (const char *)(unsigned int)v85,
                  (int)ppv);
              else
                Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::Concat(&v89, L"\\");
            }
            if ( (unsigned int)IsAppCompatModeEnabled(5) )
              v4 &= ~0x8000u;
            if ( (v4 & 0x8000) != 0 && (v4 & 0x4000) == 0 )
            {
              v108 = 3801146;
              StringFromGUID2((const GUID *const)&Buf1, sz, 39);
              v73 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::Concat(
                      &v98,
                      &v108);
              CachedRegFolder = v73;
              if ( v73 < 0 )
                wil::details::in1diag3::_Log_Hr(
                  retaddr,
                  (void *)0x6F2,
                  (unsigned int)"onecoreuap\\shell\\windows.storage\\regfldr.cpp",
                  (const char *)(unsigned int)v73,
                  (int)ppv);
              goto LABEL_163;
            }
          }
          pv = v5;
          v93 = 0;
          LODWORD(psf) = 1;
          v62 = _lambda_b461f0d585b4e5be4448ff82c363a670_::_lambda_b461f0d585b4e5be4448ff82c363a670_(
                  &pitem,
                  v37,
                  &pv,
                  &v93);
          v63 = lambda_b354619901b1de20493e1a841af0ba1e_::operator()(v62);
          if ( v63 < 0 )
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x659,
              (unsigned int)"onecoreuap\\shell\\windows.storage\\regfldr.cpp",
              (const char *)(unsigned int)v63,
              (int)ppv);
          v64 = v93;
          v99 = -1;
          *(_QWORD *)v98.Data4 = -1;
          if ( v93 )
          {
            v69 = 0;
            v93 = 0;
            *(_QWORD *)&v98.Data1 = v64;
LABEL_181:
            if ( v69 )
              CoTaskMemFree(v69);
LABEL_163:
            if ( CachedRegFolder >= 0 )
            {
              v74 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::Concat(
                      &v89,
                      &v98);
              CachedRegFolder = v74;
              if ( v74 < 0 )
              {
                wil::details::in1diag3::_Log_Hr(
                  retaddr,
                  (void *)0x715,
                  (unsigned int)"onecoreuap\\shell\\windows.storage\\regfldr.cpp",
                  (const char *)(unsigned int)v74,
                  (int)ppv);
              }
              else
              {
                cotaskmem_string_nothrow = (LPWSTR *)wil::make_cotaskmem_string_nothrow(
                                                       (wil *)&pv,
                                                       v89,
                                                       0xFFFFFFFFFFFFFFFFuLL);
                if ( &ppsz != cotaskmem_string_nothrow )
                {
                  v76 = *cotaskmem_string_nothrow;
                  if ( ppsz )
                    wil::details::close_invoke_helper<1,void (*)(void *),&void CoTaskMemFree(void *),unsigned short *>::close_reset(ppsz);
                  ppsz = v76;
                  *cotaskmem_string_nothrow = 0;
                }
                if ( pv )
                  CoTaskMemFree(pv);
              }
            }
            if ( *(_QWORD *)&v98.Data1 )
              CoTaskMemFree(*(LPVOID *)&v98.Data1);
            if ( v89 )
              CoTaskMemFree(v89);
            goto LABEL_71;
          }
          CachedRegFolder = CRegFolder::_GetRegistryDisplayName((CRegFolder *)v37, v5, (unsigned __int16 **)&v98);
          if ( CachedRegFolder < 0 || !v37[21].lpVtbl || (v4 & 0x8001) != 0 )
          {
LABEL_143:
            v69 = v93;
            goto LABEL_181;
          }
          pitem = (struct _GUID)0LL;
          *(_QWORD *)&v102 = 0;
          v65 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::Initialize(
                  &pitem,
                  g_hinst,
                  4257);
          if ( v65 < 0 )
          {
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x705,
              (unsigned int)"onecoreuap\\shell\\windows.storage\\regfldr.cpp",
              (const char *)(unsigned int)v65,
              (int)ppv);
            goto LABEL_142;
          }
          v104 = (struct _GUID)0LL;
          *(_QWORD *)&v105 = 0;
          v66 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::InitializeMessage(
                  &v104,
                  *(_QWORD *)&pitem.Data1,
                  v37[21].lpVtbl,
                  *(_QWORD *)&v98.Data1);
          v67 = retaddr;
          if ( v66 < 0 )
          {
            v68 = 1800;
          }
          else
          {
            v66 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::Initialize(
                    &v98,
                    &v104);
            CachedRegFolder = v66;
            v67 = retaddr;
            if ( v66 >= 0 )
            {
LABEL_141:
              Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v104);
LABEL_142:
              Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&pitem);
              goto LABEL_143;
            }
            v68 = 1802;
          }
          wil::details::in1diag3::_Log_Hr(
            v67,
            (void *)v68,
            (unsigned int)"onecoreuap\\shell\\windows.storage\\regfldr.cpp",
            (const char *)(unsigned int)v66,
            (int)ppv);
          goto LABEL_141;
        }
        CachedRegFolder = -2147467259;
        CoTaskMemFree(v34);
LABEL_67:
        v37 = v93;
        goto LABEL_68;
      }
      _InterlockedDecrement((volatile signed __int32 *)&v6[45].lpVtbl + 1);
    }
    v7 = 0;
    goto LABEL_10;
  }
  psf = 0;
  Buf1 = *(__m128i *)((char *)v5 + *((unsigned __int16 *)v5 + 2) + 22);
  CachedRegFolder = CRegFolder::_CreateCachedDelegateFolder((CRegFolder *)v6, (const struct _GUID *)&Buf1, &psf, 0);
  if ( CachedRegFolder < 0 )
    goto LABEL_92;
  ppsz = 0;
  v93 = 0;
  v70 = psf;
  if ( !psf || *(_WORD *)v5 && (v72 = (_WORD *)((char *)v5 + *(unsigned __int16 *)v5)) != 0 && *v72 )
  {
    v71 = (ITEMIDLIST *)ILCloneParent(v5);
    if ( !v71 )
    {
      CachedRegFolder = -2147024882;
      goto LABEL_92;
    }
    CachedRegFolder = SHBindToObject(v70, v71, 0, &GUID_000214e6_0000_0000_c000_000000000046, (void **)&v93);
    CoTaskMemFree(v71);
  }
  else
  {
    CachedRegFolder = ((__int64 (__fastcall *)(IShellFolder *, GUID *, struct IShellItem2 **))psf->lpVtbl->QueryInterface)(
                        psf,
                        &GUID_000214e6_0000_0000_c000_000000000046,
                        &v93);
  }
  if ( CachedRegFolder >= 0 )
  {
    v46 = *(_WORD *)v5;
    if ( *(_WORD *)v5 )
    {
      do
      {
        v47 = (const ITEMIDLIST *)v5;
        v5 = (const struct IDLREGITEM *)((char *)v5 + v46);
        v46 = *(_WORD *)v5;
      }
      while ( *(_WORD *)v5 );
    }
    else
    {
      v47 = (const ITEMIDLIST *)v5;
    }
    memset_0(&pstr, 0, sizeof(pstr));
    CachedRegFolder = ((__int64 (__fastcall *)(struct IShellItem2 *, const ITEMIDLIST *, _QWORD, STRRET *))v93->lpVtbl->GetPropertyDescriptionList)(
                        v93,
                        v47,
                        v4,
                        &pstr);
    if ( CachedRegFolder >= 0 )
      CachedRegFolder = StrRetToStrW(&pstr, v47, &ppsz);
    ((void (__fastcall *)(struct IShellItem2 *))v93->lpVtbl->Release)(v93);
  }
LABEL_92:
  v48 = psf;
  if ( psf )
  {
    psf = 0;
    ((void (__fastcall *)(IShellFolder *))v48->lpVtbl->Release)(v48);
  }
  if ( CachedRegFolder >= 0 )
    goto LABEL_95;
LABEL_96:
  if ( ppsz )
    CoTaskMemFree(ppsz);
  return (unsigned int)CachedRegFolder;
}

```

## disassembly

```asm
0x180091620  push    rbp
0x180091622  push    rbx
0x180091623  push    rsi
0x180091624  push    rdi
0x180091625  push    r12
0x180091627  push    r13
0x180091629  push    r14
0x18009162b  push    r15
0x18009162d  lea     rbp, [rsp-178h]
0x180091635  sub     rsp, 278h
0x18009163c  mov     rax, cs:__security_cookie
0x180091643  xor     rax, rsp
0x180091646  mov     [rbp+1B0h+var_50], rax
0x18009164d  mov     [rsp+2B0h+var_268], r9
0x180091652  mov     r15d, r8d
0x180091655  mov     dword ptr [rsp+2B0h+hKey], r8d
0x18009165a  mov     rdi, rdx
0x18009165d  mov     r14, rcx
0x180091660  mov     [rsp+2B0h+var_260], rcx
0x180091665  xor     ebx, ebx
0x180091667  mov     dword ptr [rsp+2B0h+psf], ebx
0x18009166b  mov     [r9], rbx
0x18009166e  mov     [rsp+2B0h+ppsz], rbx
0x180091673  test    rdx, rdx
0x180091676  jz      short loc_1800916AA
0x180091678  movzx   eax, word ptr [rdx]
0x18009167b  cmp     eax, 7
0x18009167e  jbe     short loc_180091691
0x180091680  movzx   edx, word ptr [rdx+4]
0x180091684  lea     rcx, [rdx+26h]
0x180091688  cmp     rax, rcx
0x18009168b  jnb     loc_180092093
0x180091691  movzx   eax, word ptr [rdi]
0x180091694  cmp     eax, 7
0x180091697  jbe     short loc_1800916AA
0x180091699  movzx   edx, word ptr [rdi+4]
0x18009169d  lea     rcx, [rdx+26h]
0x1800916a1  cmp     rax, rcx
0x1800916a4  jnb     loc_1800922A4
0x1800916aa  movzx   eax, byte ptr [r14+168h]
0x1800916b2  cmp     [rdi+2], al
0x1800916b5  jz      loc_1800924DF
0x1800916bb  mov     eax, [r14+164h]
0x1800916c2  add     rax, rdi
0x1800916c5  movups  xmm0, xmmword ptr [rax+4]
0x1800916c9  movups  [rbp+1B0h+Buf1], xmm0
0x1800916cd  mov     esi, ebx
0x1800916cf  mov     [rsp+2B0h+ppsz], rbx
0x1800916d4  mov     r13d, 1
0x1800916da  movd    eax, xmm0
0x1800916de  cmp     eax, [r14+174h]
0x1800916e5  jz      loc_180091C56
0x1800916eb  test    esi, esi
0x1800916ed  jnz     loc_180091B25
0x1800916f3  mov     rcx, [rsp+2B0h+ppsz]; pv
0x1800916f8  test    rcx, rcx
0x1800916fb  jnz     loc_180091A35
0x180091701  mov     [rsp+2B0h+ppsz], rbx
0x180091706  mov     [rsp+2B0h+psf], rbx
0x18009170b  mov     r12d, r13d
0x18009170e  test    rdi, rdi
0x180091711  jz      short loc_18009172D
0x180091713  movzx   eax, word ptr [rdi]
0x180091716  cmp     eax, 7
0x180091719  jbe     short loc_18009172D
0x18009171b  movzx   r8d, word ptr [rdi+4]
0x180091720  lea     rcx, [r8+26h]; this
0x180091724  cmp     rax, rcx
0x180091727  jnb     loc_1800922D9
0x18009172d  movzx   eax, byte ptr [r14+168h]
0x180091735  cmp     [rdi+2], al
0x180091738  jz      loc_1800924E7
0x18009173e  mov     eax, [r14+164h]
0x180091745  add     rax, rdi
0x180091748  add     rax, 4
0x18009174c  movups  xmm0, xmmword ptr [rax]
0x18009174f  movups  xmmword ptr [rsp+2B0h+var_238.Data1], xmm0
0x180091754  mov     eax, r15d
0x180091757  and     eax, 0C001h
0x18009175c  cmp     eax, 8000h
0x180091761  jnz     loc_1800919B7
0x180091767  xorps   xmm0, xmm0
0x18009176a  xor     eax, eax
0x18009176c  movups  [rbp+1B0h+pitem], xmm0
0x180091770  movups  [rbp+1B0h+var_200], xmm0
0x180091774  mov     [rbp+1B0h+var_1F0], rax
0x180091778  xor     edx, edx; int
0x18009177a  call    ?_EnsureCacheIsValid@CCLSIDInfoCache@@AEAAHH@Z; CCLSIDInfoCache::_EnsureCacheIsValid(int)
0x18009177f  test    eax, eax
0x180091781  jz      loc_18009252C
0x180091787  lea     rcx, ?g_clsidInfoCache@@3VCCLSIDInfoCache@@A; SRWLock
0x18009178e  call    cs:__imp_AcquireSRWLockShared
0x180091795  nop     dword ptr [rax+rax+00h]
0x18009179a  xorps   xmm0, xmm0
0x18009179d  movdqu  [rbp+1B0h+var_1D8], xmm0
0x1800917a2  mov     [rbp+1B0h+var_1C8], rbx
0x1800917a6  movups  xmm0, xmmword ptr [rsp+2B0h+var_238.Data1]
0x1800917ab  movups  [rbp+1B0h+var_1E8], xmm0
0x1800917af  mov     rsi, cs:hdsa
0x1800917b6  test    rsi, rsi
0x1800917b9  jz      loc_1800924EF
0x1800917bf  mov     r15d, [rsi]
0x1800917c2  mov     r14d, ebx
0x1800917c5  dec     r15d
0x1800917c8  nop     dword ptr [rax+rax+00000000h]
0x1800917d0  cmp     r14d, r15d
0x1800917d3  jg      loc_180092355
0x1800917d9  lea     eax, [r15+r14]
0x1800917dd  cdq
0x1800917de  sub     eax, edx
0x1800917e0  sar     eax, 1
0x1800917e2  mov     ebx, eax
0x1800917e4  xor     edx, edx
0x1800917e6  test    rsi, rsi
0x1800917e9  jz      short loc_1800917FD
0x1800917eb  test    eax, eax
0x1800917ed  js      short loc_1800917FD
0x1800917ef  cmp     eax, [rsi]
0x1800917f1  jge     short loc_1800917FD
0x1800917f3  mov     edx, eax
0x1800917f5  imul    edx, [rsi+14h]
0x1800917f9  add     rdx, [rsi+8]; struct CLSID_CACHE_ENTRY *
0x1800917fd  xor     r8d, r8d; __int64
0x180091800  lea     rcx, [rbp+1B0h+var_1E8]; struct CLSID_CACHE_ENTRY *
0x180091804  call    ?s_CompareEntries@CCLSIDInfoCache@@CAHPEBUCLSID_CACHE_ENTRY@@0_J@Z; CCLSIDInfoCache::s_CompareEntries(CLSID_CACHE_ENTRY const *,CLSID_CACHE_ENTRY const *,__int64)
0x180091809  test    eax, eax
0x18009180b  js      short loc_180091815
0x18009180d  jle     short loc_18009181B
0x18009180f  lea     r14d, [rbx+1]
0x180091813  jmp     short loc_1800917D0
0x180091815  lea     r15d, [rbx-1]
0x180091819  jmp     short loc_1800917D0
0x18009181b  test    ebx, ebx
0x18009181d  jle     short loc_18009184F
0x18009181f  xor     edx, edx
0x180091821  test    rsi, rsi
0x180091824  jz      short loc_18009183B
0x180091826  lea     eax, [rbx-1]
0x180091829  test    eax, eax
0x18009182b  js      short loc_18009183B
0x18009182d  cmp     eax, [rsi]
0x18009182f  jge     short loc_18009183B
0x180091831  imul    eax, [rsi+14h]
0x180091835  mov     edx, eax
0x180091837  add     rdx, [rsi+8]; struct CLSID_CACHE_ENTRY *
0x18009183b  xor     r8d, r8d; __int64
0x18009183e  lea     rcx, [rbp+1B0h+var_1E8]; struct CLSID_CACHE_ENTRY *
0x180091842  call    ?s_CompareEntries@CCLSIDInfoCache@@CAHPEBUCLSID_CACHE_ENTRY@@0_J@Z; CCLSIDInfoCache::s_CompareEntries(CLSID_CACHE_ENTRY const *,CLSID_CACHE_ENTRY const *,__int64)
0x180091847  test    eax, eax
0x180091849  jz      loc_1800924F7
0x18009184f  cmp     ebx, 0FFFFFFFFh
0x180091852  jz      loc_180092355
0x180091858  xor     eax, eax
0x18009185a  test    rsi, rsi
0x18009185d  jz      short loc_180091871
0x18009185f  test    ebx, ebx
0x180091861  js      short loc_180091871
0x180091863  cmp     ebx, [rsi]
0x180091865  jge     short loc_180091871
0x180091867  imul    ebx, [rsi+14h]
0x18009186b  mov     eax, ebx
0x18009186d  add     rax, [rsi+8]
0x180091871  movups  xmm0, xmmword ptr [rax]
0x180091874  movups  [rbp+1B0h+pitem], xmm0
0x180091878  movups  xmm1, xmmword ptr [rax+10h]
0x18009187c  movups  [rbp+1B0h+var_200], xmm1
0x180091880  movsd   xmm0, qword ptr [rax+20h]
0x180091885  movsd   [rbp+1B0h+var_1F0], xmm0
0x18009188a  lea     rcx, ?g_clsidInfoCache@@3VCCLSIDInfoCache@@A; SRWLock
0x180091891  call    cs:__imp_ReleaseSRWLockShared
0x180091898  nop     dword ptr [rax+rax+00h]
0x18009189d  mov     r15d, dword ptr [rsp+2B0h+hKey]
0x1800918a2  mov     ebx, dword ptr [rbp+1B0h+var_1F0+4]
0x1800918a5  shr     ebx, 3
0x1800918a8  and     ebx, r13d
0x1800918ab  test    ebx, ebx
0x1800918ad  jz      loc_180091A54
0x1800918b3  mov     rbx, rdi
0x1800918b6  mov     [rsp+2B0h+hKey], 0
0x1800918bf  xor     esi, esi
0x1800918c1  movzx   ecx, word ptr [rdi]
0x1800918c4  add     rcx, rdi
0x1800918c7  jz      short loc_1800918F4
0x1800918c9  cmp     [rcx], si
0x1800918cc  jz      short loc_1800918F4
0x1800918ce  mov     rcx, rdi; pidl
0x1800918d1  call    ILCloneFirst
0x1800918d6  mov     rbx, rax
0x1800918d9  xor     eax, eax
0x1800918db  mov     r12d, 8007000Eh
0x1800918e1  test    rbx, rbx
0x1800918e4  cmovz   eax, r12d
0x1800918e8  mov     r12d, eax
0x1800918eb  jz      loc_180091A54
0x1800918f1  mov     rsi, rbx
0x1800918f4  mov     rcx, rbx
0x1800918f7  call    IsDelegateRegId
0x1800918fc  test    eax, eax
0x1800918fe  jz      short loc_180091909
0x180091900  test    rbx, rbx
0x180091903  jnz     loc_180091D46
0x180091909  mov     r8d, 10h; Size
0x18009190f  lea     rdx, IID_IIdentityName; Buf2
0x180091916  lea     rcx, _GUID_000214e6_0000_0000_c000_000000000046; Buf1
0x18009191d  call    memcmp_0
0x180091922  test    eax, eax
0x180091924  jz      short loc_180091947
0x180091926  mov     r8d, 10h; Size
0x18009192c  lea     rdx, IID_IDelegateItem; Buf2
0x180091933  lea     rcx, _GUID_000214e6_0000_0000_c000_000000000046; Buf1
0x18009193a  call    memcmp_0
0x18009193f  test    eax, eax
0x180091941  jnz     loc_180091D46
0x180091947  mov     [rsp+2B0h+pv], 0
0x180091950  lea     rax, [rsp+2B0h+pv]
0x180091955  mov     [rsp+2B0h+ppv], rax; void **
0x18009195a  lea     r9, _GUID_000214e6_0000_0000_c000_000000000046; struct _GUID *
0x180091961  xor     r8d, r8d; pbc
0x180091964  mov     rdx, rbx; struct IDLREGITEM *
0x180091967  mov     r14, [rsp+2B0h+var_260]
0x18009196c  mov     rcx, r14; this
0x18009196f  call    ?_CreateCachedRegFolder@CRegFolder@@AEAAJPEFBUIDLREGITEM@@PEAUIBindCtx@@AEBU_GUID@@PEAPEAX@Z; CRegFolder::_CreateCachedRegFolder(IDLREGITEM const *,IBindCtx *,_GUID const &,void * *)
0x180091974  mov     r12d, eax
0x180091977  test    eax, eax
0x180091979  js      loc_180091E42
0x18009197f  mov     rcx, [rsp+2B0h+pv]
0x180091984  mov     rax, [rcx]
0x180091987  lea     r9, [rsp+2B0h+hKey]
0x18009198c  lea     r8, _GUID_000214e6_0000_0000_c000_000000000046
0x180091993  xor     edx, edx
0x180091995  mov     rax, [rax+40h]
0x180091999  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009199e  mov     r12d, eax
0x1800919a1  mov     rcx, [rsp+2B0h+pv]
0x1800919a6  mov     rax, [rcx]
0x1800919a9  mov     rax, [rax+10h]
0x1800919ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800919b2  jmp     loc_180091E42
0x1800919b7  bt      r15d, 0Fh
0x1800919bc  jb      loc_18009207E
0x1800919c2  mov     [rsp+2B0h+hKey], 0
0x1800919cb  lea     rax, [rsp+2B0h+hKey]
0x1800919d0  mov     [rsp+2B0h+var_288], rax; unsigned int *
0x1800919d5  mov     dword ptr [rsp+2B0h+ppv], r13d
0x1800919da  xor     r9d, r9d
0x1800919dd  mov     r8d, r13d
0x1800919e0  xor     edx, edx
0x1800919e2  lea     rcx, [rsp+2B0h+var_238]
0x1800919e7  call    cs:__imp_SHRegGetCLSIDKey
0x1800919ee  nop     dword ptr [rax+rax+00h]
0x1800919f3  test    eax, eax
0x1800919f5  jns     loc_18009240D
0x1800919fb  cmp     [rsp+2B0h+psf], 0
0x180091a01  jnz     short loc_180091A16
0x180091a03  mov     r8d, r13d
0x180091a06  lea     rdx, [rsp+2B0h+var_238]
0x180091a0b  call    ?GetFolderValue@CCLSIDInfoCache@@QEAAHAEBU_GUID@@W4CLSID_FOLDER_VALUE_FLAGS@@@Z; CCLSIDInfoCache::GetFolderValue(_GUID const &,CLSID_FOLDER_VALUE_FLAGS)
0x180091a10  test    eax, eax
0x180091a12  cmovnz  ebx, r13d
0x180091a16  mov     rcx, [rsp+2B0h+hKey]; hKey
0x180091a1b  test    rcx, rcx
0x180091a1e  jz      loc_1800918AB
0x180091a24  call    cs:__imp_RegCloseKey
0x180091a2b  nop     dword ptr [rax+rax+00h]
0x180091a30  jmp     loc_1800918AB
0x180091a35  call    ?close_reset@?$close_invoke_helper@$00P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZPEAG@details@wil@@SAXPEAG@Z; wil::details::close_invoke_helper<1,void (*)(void *),&CoTaskMemFree(void *),ushort *>::close_reset(ushort *)
0x180091a3a  jmp     loc_180091701
0x180091a3f  mov     r12d, 80004005h
0x180091a45  mov     rcx, rsi; pv
0x180091a48  call    cs:__imp_CoTaskMemFree
0x180091a4f  nop     dword ptr [rax+rax+00h]
0x180091a54  mov     r14, [rsp+2B0h+var_260]
0x180091a59  mov     rax, [rsp+2B0h+psf]
0x180091a5e  test    rax, rax
0x180091a61  jnz     loc_180091B1B
0x180091a67  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x180091a6e  cmp     r12d, 1
0x180091a72  jz      loc_180091EEA
0x180091a78  test    r12d, r12d
0x180091a7b  js      loc_180091C19
0x180091a81  mov     rax, [rsp+2B0h+ppsz]
0x180091a86  inc     rbx
0x180091a89  cmp     word ptr [rax+rbx*2], 0
0x180091a8e  jnz     short loc_180091A86
0x180091a90  cmp     rbx, 40h ; '@'
0x180091a94  jnb     loc_180091C03
0x180091a9a  lock inc dword ptr [r14+16Ch]
0x180091aa2  jnz     short loc_180091B0E
0x180091aa4  mov     edx, 7FFFFFFEh
0x180091aa9  mov     r9d, 40h ; '@'
0x180091aaf  lea     r8, [r14+188h]
0x180091ab6  test    rdx, rdx
0x180091ab9  jz      short loc_180091AD8
0x180091abb  movzx   ecx, word ptr [rax]
0x180091abe  test    cx, cx
0x180091ac1  jz      short loc_180091AD8
0x180091ac3  add     rax, 2
0x180091ac7  mov     [r8], cx
0x180091acb  add     r8, 2
0x180091acf  dec     rdx
  ... truncated ...
```
