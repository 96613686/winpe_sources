# CComRegCatalog::GetClassInfoW(ulong,IUserToken *,_GUID const &,_GUID const &,void * *,void *)

- ea: `0x180037310`
- end: `0x180038000`
- name: `?GetClassInfoW@CComRegCatalog@@UEAAJKPEAUIUserToken@@AEBU_GUID@@1PEAPEAXPEAX@Z`
- size: `3312`
- prototype: `__int64 __fastcall(CComRegCatalog *this, __int64, struct IUserToken *, struct _GUID *, const struct _GUID *, void **, __int64 (__fastcall ***)(_QWORD, GUID *, struct IGetProcessInfoInternal **))`
- caller_count: `1`
- callee_count: `27`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800cfe00`

## callees

- `0x180003064`
- `0x180008378`
- `0x18000b428`
- `0x18000bb40`
- `0x18000e40c`
- `0x18000e460`
- `0x180018344`
- `0x18001ae64`
- `0x18001af6c`
- `0x18002ba28`
- `0x180037310`
- `0x180038008`
- `0x1800382ac`
- `0x1800384a0`
- `0x180038610`
- `0x180039068`
- `0x180039088`
- `0x18005b938`
- `0x180065594`
- `0x18006ca84`
- `0x18008e98c`
- `0x18008f610`
- `0x18009d39c`
- `0x1800b27e0`
- `0x1800b3128`
- `0x1800cca54`
- `0x18010b010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800375df`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800375df`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180037596`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180037596`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800378a0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800379af`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180037a00`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180037c60`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800378a0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800379af`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180037a00`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180037c60`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180037441`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180037441`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18003748a`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18003748a`

## string_xrefs

- `0x180037bbc`: `onecore\com\combase\catalog\regcat.cxx`
- `0x180037c26`: `onecore\com\combase\catalog\regcat.cxx`
- `0x180037cb6`: `onecore\com\combase\catalog\regcat.cxx`
- `0x180037d3f`: `onecore\com\combase\catalog\regcat.cxx`
- `0x180037d6c`: `onecore\com\combase\catalog\regcat.cxx`
- `0x180037de6`: `onecore\com\combase\catalog\regcat.cxx`
- `0x180037edf`: `onecore\com\combase\catalog\regcat.cxx`
- `0x180037f12`: `onecore\com\combase\catalog\regcat.cxx`
- `0x180037f2d`: `onecore\com\combase\catalog\regcat.cxx`
- `0x180037f63`: `onecore\com\combase\catalog\regcat.cxx`
- `0x180037fbc`: `onecore\com\combase\catalog\regcat.cxx`
- `0x180037fef`: `onecore\com\combase\catalog\regcat.cxx`
- `0x180037ee6`: `CLSID:%ls`
- `0x180037fc8`: `CLSID:%ls`
- `0x18003793f`: `onecore\com\combase\inc\ComGuid.hpp`
- `0x180037f74`: `Excessive or cyclic chain of TreatAs values starting from CLSID %ls`
- `0x180037ba1`: `CComRegCatalog::GetClassInfoW`
- `0x180037ba8`: `HRESULT:%#x, CLSID:%ls`

## pseudocode

```c
__int64 __fastcall CComRegCatalog::GetClassInfoW(
        CComRegCatalog *this,
        __int64 a2,
        struct IUserToken *a3,
        struct _GUID *a4,
        const struct _GUID *a5,
        void **a6,
        __int64 (__fastcall ***a7)(_QWORD, GUID *, struct IGetProcessInfoInternal **))
{
  __int64 (__fastcall ***v7)(_QWORD, GUID *, struct IGetProcessInfoInternal **); // r15
  CComRegCatalog *v8; // rdi
  struct IUserToken *v10; // r9
  int v11; // ebx
  __int64 v12; // rcx
  int PathForClsidKey; // eax
  unsigned int v14; // ebx
  int v15; // eax
  GUID v16; // xmm0
  unsigned int v17; // r14d
  int v18; // esi
  const char *v19; // r9
  unsigned __int64 v20; // rdx
  unsigned int v21; // eax
  const char *v22; // r9
  unsigned int v23; // eax
  __int64 v24; // rdx
  __int64 v25; // r8
  LSTATUS ValueW; // eax
  unsigned int v27; // ebx
  int v28; // eax
  LPVOID v29; // rbx
  __int64 v30; // r8
  __int64 v31; // rax
  __int64 v32; // rcx
  struct IGetProcessInfoInternal *v33; // rcx
  __int64 (__fastcall **v34)(_QWORD, GUID *, struct IGetProcessInfoInternal **); // rax
  __int64 (__fastcall *v35)(_QWORD, GUID *, struct IGetProcessInfoInternal **); // rbx
  int v36; // eax
  char v37; // al
  __int64 v38; // rcx
  unsigned __int16 v39; // ax
  __int64 v40; // rcx
  char v41; // al
  __int64 v42; // rcx
  unsigned __int16 v43; // ax
  __int64 v44; // rcx
  char v45; // al
  __int64 v46; // rcx
  char v47; // al
  __int64 v48; // rcx
  char v49; // al
  __int64 v50; // rcx
  char v51; // r13
  char v52; // r15
  struct IGetProcessInfoInternal *v53; // r12
  unsigned int v54; // esi
  int v55; // r14d
  unsigned int v56; // ebx
  HKEY v57; // rdi
  unsigned int v58; // eax
  struct IUnknown *v59; // rsi
  int v60; // eax
  void **v61; // r14
  __int64 v62; // rcx
  struct IGetProcessInfoInternal *v64; // rbx
  __int64 v65; // rcx
  int Interface; // eax
  __int64 v67; // rcx
  int v68; // eax
  __int64 v69; // rdx
  unsigned __int64 v70; // rdx
  unsigned __int8 v71; // cl
  __int64 v72; // rcx
  ComTrace *v73; // rcx
  __int64 v74; // rcx
  struct IUserToken *v75; // r9
  __int64 (__fastcall **v76)(struct IUserToken *, GUID *, __int64 *); // rax
  __int64 (__fastcall *v77)(struct IUserToken *, GUID *, __int64 *); // rbx
  __int64 v78; // rcx
  __int64 v79; // rcx
  __int64 v80; // rax
  CComRegCatalog *v81; // rcx
  __int64 v82; // rdx
  __int64 v83; // r9
  __int64 v84; // rdx
  __int64 v85; // rdx
  const char *v86; // rax
  OLECHAR *v87; // rax
  __int64 v88; // rdx
  int pdwType; // [rsp+20h] [rbp-110h]
  const wchar_t *pvData; // [rsp+28h] [rbp-108h]
  int pcbData; // [rsp+30h] [rbp-100h]
  OLECHAR *v92; // [rsp+38h] [rbp-F8h]
  unsigned int v93; // [rsp+48h] [rbp-E8h]
  char v94; // [rsp+B0h] [rbp-80h] BYREF
  unsigned int v95; // [rsp+B4h] [rbp-7Ch] BYREF
  __int64 v96; // [rsp+B8h] [rbp-78h] BYREF
  struct IUserToken *v97; // [rsp+C0h] [rbp-70h] BYREF
  char v98; // [rsp+C8h] [rbp-68h] BYREF
  HKEY hkey; // [rsp+D0h] [rbp-60h] BYREF
  bool v100; // [rsp+D8h] [rbp-58h]
  bool v101; // [rsp+D9h] [rbp-57h]
  bool v102; // [rsp+DAh] [rbp-56h]
  bool v103; // [rsp+DBh] [rbp-55h]
  bool v104; // [rsp+DCh] [rbp-54h]
  struct IGetProcessInfoInternal *v105; // [rsp+E0h] [rbp-50h] BYREF
  int v106; // [rsp+E8h] [rbp-48h] BYREF
  int v107; // [rsp+ECh] [rbp-44h]
  __int16 v108[2]; // [rsp+F0h] [rbp-40h] BYREF
  unsigned __int16 v109; // [rsp+F4h] [rbp-3Ch]
  unsigned __int16 v110; // [rsp+F6h] [rbp-3Ah]
  int v111; // [rsp+F8h] [rbp-38h]
  HKEY hKey; // [rsp+100h] [rbp-30h] BYREF
  unsigned int v113; // [rsp+108h] [rbp-28h]
  DWORD v114; // [rsp+10Ch] [rbp-24h] BYREF
  int v115; // [rsp+110h] [rbp-20h] BYREF
  struct IUnknown *v116; // [rsp+118h] [rbp-18h] BYREF
  CComRegCatalog *v117; // [rsp+120h] [rbp-10h]
  PSID pSid1; // [rsp+128h] [rbp-8h] BYREF
  __int64 (__fastcall ***v119)(_QWORD, GUID *, struct IGetProcessInfoInternal **); // [rsp+130h] [rbp+0h]
  void **v120; // [rsp+138h] [rbp+8h]
  GUID *v121; // [rsp+140h] [rbp+10h]
  GUID rguid; // [rsp+148h] [rbp+18h] BYREF
  OLECHAR v123[4]; // [rsp+160h] [rbp+30h] BYREF
  HKEY *p_hKey; // [rsp+168h] [rbp+38h]
  char *v125; // [rsp+170h] [rbp+40h]
  char *v126; // [rsp+178h] [rbp+48h]
  struct IUserToken **v127; // [rsp+180h] [rbp+50h]
  OLECHAR sz[40]; // [rsp+1B0h] [rbp+80h] BYREF
  WCHAR SubKey[48]; // [rsp+200h] [rbp+D0h] BYREF
  unsigned __int16 v130[104]; // [rsp+260h] [rbp+130h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+388h] [rbp+258h]

  v7 = a7;
  v117 = this;
  v8 = this;
  v121 = a4;
  v10 = a3;
  v113 = a2;
  v97 = a3;
  *a6 = 0;
  v120 = a6;
  v119 = a7;
  if ( (a2 & 0xCE8) != 0 )
  {
    v14 = -2147024809;
    v82 = 178;
LABEL_119:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v82,
      (unsigned int)"onecore\\com\\combase\\catalog\\regcat.cxx",
      (const char *)v14,
      pdwType);
    return v14;
  }
  v11 = a2 & 0x10000;
  if ( (a2 & 0x10000) == 0 )
    goto LABEL_3;
  if ( !(*(unsigned __int8 (__fastcall **)(CComRegCatalog *, __int64, struct IUserToken *, struct IUserToken *))(*(_QWORD *)this + 168LL))(
          this,
          a2,
          a3,
          a3) )
  {
    v14 = -2147221164;
    v82 = 179;
    goto LABEL_119;
  }
  v10 = v97;
LABEL_3:
  v95 = 0;
  p_hKey = &hKey;
  v125 = &v98;
  v126 = &v94;
  v127 = &v97;
  v12 = 0;
  v96 = 0;
  v94 = 0;
  v98 = 0;
  hKey = 0;
  *(_QWORD *)v123 = v8;
  if ( v10 )
  {
    if ( v11 )
    {
      lambda_6f6522c49679d9fbe761af3c1bc61942_::operator()(v123);
    }
    else
    {
      PathForClsidKey = (*(__int64 (__fastcall **)(CComRegCatalog *, struct IUserToken *, HKEY *))(*(_QWORD *)v8 + 120LL))(
                          v8,
                          v10,
                          &hKey);
      v14 = PathForClsidKey;
      if ( PathForClsidKey < 0 )
      {
        if ( PathForClsidKey != -2147024894 )
        {
          v69 = 263;
          goto LABEL_144;
        }
        if ( !(*(unsigned __int8 (__fastcall **)(CComRegCatalog *))(*(_QWORD *)v8 + 168LL))(v8) )
        {
          if ( ComTrace::IsEnabled(v71, v70) )
          {
            wil::details::static_lazy<ComTrace>::get(
              v72,
              _lambda_f8a79a44bba2ee3470b25df359f31864_::_lambda_invoker_cdecl_);
            ComTrace::LogVerbose_(v73, L"No private hive for package");
          }
          goto LABEL_45;
        }
        lambda_6f6522c49679d9fbe761af3c1bc61942_::operator()(v123);
      }
      else
      {
        v94 = 1;
      }
      if ( !hKey )
      {
        MicrosoftTelemetryAssertTriggeredNoArgs();
        v14 = -2147418113;
        v69 = 266;
        v83 = 2147549183LL;
LABEL_145:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v69,
          (unsigned int)"onecore\\com\\combase\\catalog\\regcat.cxx",
          (const char *)v83,
          pdwType);
        goto LABEL_105;
      }
    }
    pSid1 = 0;
    v108[0] = 0;
    v15 = (*(__int64 (__fastcall **)(struct IUserToken *, PSID *, __int16 *))(*(_QWORD *)v97 + 40LL))(v97, &pSid1, v108);
    v14 = v15;
    if ( v15 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x116,
        (unsigned int)"onecore\\com\\combase\\catalog\\regcat.cxx",
        (const char *)(unsigned int)v15,
        pdwType);
      v79 = v96;
      if ( !v96 )
      {
LABEL_107:
        if ( v94 )
        {
          v80 = *(_QWORD *)v8;
          v81 = v8;
          goto LABEL_109;
        }
        goto LABEL_110;
      }
LABEL_106:
      (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v96 + 104LL))(v79, v95);
      goto LABEL_107;
    }
    if ( !EqualSid(pSid1, gSidAnonymous) )
    {
      v74 = v96;
      v75 = v97;
      v76 = *(__int64 (__fastcall ***)(struct IUserToken *, GUID *, __int64 *))v97;
      v96 = 0;
      v77 = *v76;
      if ( v74 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v74 + 16LL))(v74);
        v75 = v97;
      }
      PathForClsidKey = v77(v75, &GUID_000001fc_0000_0000_cfff_123045660046, &v96);
      v14 = PathForClsidKey;
      if ( PathForClsidKey < 0 )
      {
        v69 = 281;
        goto LABEL_144;
      }
    }
    v12 = v96;
  }
  else
  {
    hKey = (HKEY)*((_QWORD *)v8 + 3);
  }
  if ( v12 )
  {
    PathForClsidKey = (*(__int64 (__fastcall **)(__int64, __int64, unsigned int *))(*(_QWORD *)v12 + 96LL))(
                        v12,
                        1,
                        &v95);
    v14 = PathForClsidKey;
    if ( PathForClsidKey < 0 )
    {
      v69 = 296;
LABEL_144:
      v83 = (unsigned int)PathForClsidKey;
      goto LABEL_145;
    }
  }
  v16 = *a4;
  v17 = 0;
  v111 = 0;
  v18 = 0;
  v107 = 0;
  rguid = v16;
  while ( 1 )
  {
    while ( 1 )
    {
      if ( StringFromGUID2(&rguid, sz, 39) != 39 )
        wil::details::in1diag3::_FailFast_Unexpected(
          retaddr,
          (void *)0x19,
          (unsigned int)"onecore\\com\\combase\\inc\\ComGuid.hpp",
          v19);
      memset_0(SubKey, 0, 0x5Au);
      PathForClsidKey = GetPathForClsidKey(&rguid, v20, SubKey);
      v14 = PathForClsidKey;
      if ( PathForClsidKey < 0 )
      {
        v69 = 315;
        goto LABEL_144;
      }
      hkey = 0;
      if ( v17 )
      {
        v23 = (*(__int64 (__fastcall **)(CComRegCatalog *, HKEY, WCHAR *, __int64, HKEY *))(*(_QWORD *)v8 + 152LL))(
                v8,
                hKey,
                SubKey,
                131097,
                &hkey);
        v22 = (const char *)v23;
        if ( v23 != 2 )
          goto LABEL_19;
        if ( gfEnableTracing && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        {
          v92 = sz;
          pcbData = -2147221164;
          pvData = L"HRESULT:%#x, CLSID:%ls";
          pdwType = 3;
          ComTraceMessage(
            2147746132LL,
            "onecore\\com\\combase\\catalog\\regcat.cxx",
            "CComRegCatalog::GetClassInfoW",
            382);
        }
        if ( hkey )
          RegCloseKey(hkey);
LABEL_45:
        v62 = v96;
        if ( v96 )
        {
          (*(void (__fastcall **)(__int64, _QWORD, __int64, const char *, int, const wchar_t *, int, OLECHAR *))(*(_QWORD *)v96 + 104LL))(
            v96,
            v95,
            v25,
            v22,
            pdwType,
            pvData,
            pcbData,
            v92);
          v62 = v96;
        }
        if ( v94 )
        {
          (*(void (__fastcall **)(CComRegCatalog *, struct IUserToken *, __int64, const char *))(*(_QWORD *)v8 + 128LL))(
            v8,
            v97,
            v25,
            v22);
          v62 = v96;
        }
        if ( v62 )
          (*(void (__fastcall **)(__int64, __int64, __int64, const char *))(*(_QWORD *)v62 + 16LL))(v62, v24, v25, v22);
        return 2147746132LL;
      }
      v21 = CComRegCatalog::OpenKeyInViewHelper(hKey, SubKey, 0x20019u, *((_DWORD *)v8 + 4), *((_WORD *)v8 + 10), &hkey);
      v22 = (const char *)v21;
      if ( v21 == 2 )
      {
        v17 = 1;
        v111 = 1;
LABEL_127:
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
        goto LABEL_40;
      }
LABEL_19:
      if ( (_DWORD)v22 )
      {
        v87 = sz;
        v88 = 387;
        goto LABEL_142;
      }
      memset_0(v130, 0, 0xC8u);
      v114 = 200;
      ValueW = RegGetValueW(hkey, L"TreatAs", 0, 0xFFFFu, 0, v130, &v114);
      v27 = ValueW;
      if ( !ValueW )
      {
        if ( (v114 & 0xFFFFFFFE) < 0x4A )
        {
          v84 = 396;
        }
        else
        {
          if ( CurlyStringToGUID(v130, &rguid) )
          {
            v107 = ++v18;
            goto LABEL_127;
          }
          v84 = 397;
        }
        v14 = -2147221165;
        goto LABEL_134;
      }
      if ( ValueW != 2 )
      {
        v87 = (OLECHAR *)GuidString::GuidString(v123, &rguid);
        v22 = (const char *)v27;
        v88 = 405;
LABEL_142:
        v14 = wil::details::in1diag3::Return_Win32Msg(
                retaddr,
                (void *)v88,
                (unsigned int)"onecore\\com\\combase\\catalog\\regcat.cxx",
                v22,
                (unsigned int)"CLSID:%ls",
                (const char *)v87);
        goto LABEL_104;
      }
      v106 = 0;
      if ( v98 )
      {
        v28 = 1;
        v106 = 1;
      }
      else
      {
        v68 = (*(__int64 (__fastcall **)(CComRegCatalog *, HKEY, int *))(*(_QWORD *)v8 + 160LL))(v8, hkey, &v106);
        v14 = v68;
        if ( v68 < 0 )
        {
          v85 = 424;
          goto LABEL_137;
        }
        v28 = v106;
      }
      if ( !g_bInSCM || v28 )
        break;
      v115 = 0;
      v68 = CComRegCatalog::CheckForceHKLMForCLSID(v8, hKey, hkey, &v115);
      v14 = v68;
      if ( v68 < 0 )
      {
        v85 = 430;
LABEL_137:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v85,
          (unsigned int)"onecore\\com\\combase\\catalog\\regcat.cxx",
          (const char *)(unsigned int)v68,
          pdwType);
        goto LABEL_104;
      }
      if ( !v115 )
        break;
      if ( !(*(unsigned __int8 (__fastcall **)(CComRegCatalog *))(*(_QWORD *)v8 + 168LL))(v8) )
      {
        v14 = -2147221161;
        v84 = 442;
LABEL_134:
        wil::details::in1diag3::Return_HrMsg(
          retaddr,
          (void *)v84,
          (unsigned int)"onecore\\com\\combase\\catalog\\regcat.cxx",
          (const char *)v14,
          (int)"CLSID:%ls",
          (const char *)sz);
        goto LABEL_104;
      }
      lambda_6f6522c49679d9fbe761af3c1bc61942_::operator()(v123);
      v107 = 0;
      v18 = 0;
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
    }
    v29 = HeapAlloc(g_hHeap, 0, 0x198u);
    if ( !v29 )
    {
      v116 = 0;
LABEL_102:
      v14 = -2147024882;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1C1,
        (unsigned int)"onecore\\com\\combase\\catalog\\regcat.cxx",
        (const char *)0x8007000ELL,
        pdwType);
LABEL_103:
      wil::com_ptr_t<CComClassInfo,wil::err_returncode_policy>::~com_ptr_t<CComClassInfo,wil::err_returncode_policy>(&v116);
LABEL_104:
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
      goto LABEL_105;
    }
    LOBYTE(v30) = (*(__int64 (__fastcall **)(CComRegCatalog *))(*(_QWORD *)v8 + 360LL))(v8);
    v31 = CComClassInfo::CComClassInfo(v29, *((unsigned int *)v8 + 8), v30);
    v116 = (struct IUnknown *)v31;
    if ( !v31 )
      goto LABEL_102;
    _InterlockedAdd((volatile signed __int32 *)(v31 + 56), 1u);
    v32 = *(_QWORD *)v8;
    v105 = 0;
    if ( (*(unsigned __int8 (__fastcall **)(CComRegCatalog *))(v32 + 344))(v8) )
    {
      v33 = v105;
      v34 = *v7;
      v105 = 0;
      v35 = *v34;
      if ( v33 )
        (*(void (__fastcall **)(struct IGetProcessInfoInternal *))(*(_QWORD *)v33 + 16LL))(v33);
      v36 = v35(v7, &GUID_eb3cae6b_6670_4b52_a0a9_d96c3b30180f, &v105);
      v14 = v36;
      if ( v36 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1C6,
          (unsigned int)"onecore\\com\\combase\\catalog\\regcat.cxx",
          (const char *)(unsigned int)v36,
          pdwType);
        wil::com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>::~com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>(&v105);
        goto LABEL_103;
      }
    }
    else
    {
      v64 = v105;
      v105 = (struct IGetProcessInfoInternal *)(((unsigned __int64)v8 + 8) & -(__int64)(v8 != 0));
      if ( v105 )
      {
        v65 = ((unsigned __int64)v8 + 8) & -(__int64)(v8 != 0);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v65 + 8LL))(v65);
      }
      if ( v64 )
        (*(void (__fastcall **)(struct IGetProcessInfoInternal *))(*(_QWORD *)v64 + 16LL))(v64);
    }
    v37 = (*(__int64 (__fastcall **)(CComRegCatalog *))(*(_QWORD *)v8 + 336LL))(v8);
    v38 = *(_QWORD *)v8;
    v100 = v37;
    v39 = (*(__int64 (__fastcall **)(CComRegCatalog *, _QWORD))(v38 + 144))(v8, v17);
    v40 = *(_QWORD *)v8;
    v109 = v39;
    v41 = (*(__int64 (__fastcall **)(CComRegCatalog *))(v40 + 312))(v8);
    v42 = *(_QWORD *)v8;
    v101 = v41;
    v43 = (*(__int64 (__fastcall **)(CComRegCatalog *))(v42 + 328))(v8);
    v44 = *(_QWORD *)v8;
    v110 = v43;
    v45 = (*(__int64 (__fastcall **)(CComRegCatalog *))(v44 + 304))(v8);
    v46 = *(_QWORD *)v8;
    v102 = v45;
    v47 = (*(__int64 (__fastcall **)(CComRegCatalog *))(v46 + 288))(v8);
    v48 = *(_QWORD *)v8;
    v103 = v47;
    v49 = (*(__int64 (__fastcall **)(CComRegCatalog *))(v48 + 192))(v8);
    v50 = *(_QWORD *)v8;
    v104 = v49;
    v51 = (*(__int64 (__fastcall **)(CComRegCatalog *))(v50 + 184))(v8);
    v52 = (*(__int64 (__fastcall **)(CComRegCatalog *))(*(_QWORD *)v8 + 176LL))(v8);
    v53 = v105;
    v54 = (*(__int64 (__fastcall **)(CComRegCatalog *, _QWORD))(*(_QWORD *)v8 + 136LL))(v8, v17);
    v55 = v106;
    v56 = (*(__int64 (__fastcall **)(CComRegCatalog *))(*(_QWORD *)v8 + 320LL))(v8);
    v57 = (HKEY)*((_QWORD *)v8 + 3);
    v58 = (*(__int64 (__fastcall **)(CComRegCatalog *, _QWORD))(*(_QWORD *)v117 + 136LL))(v117, 0);
    v93 = v54;
    v59 = v116;
    v60 = CComClassInfo::FinalConstruct(
            (CComClassInfo *)v116,
            v97,
            &rguid,
            SubKey,
            hkey,
            v58,
            v57,
            v56,
            v55,
            v93,
            v53,
            (v113 & 0x8000) != 0,
            v52,
            v51,
            v104,
            v103,
            v102,
            v110,
            v101,
            v109,
            v100);
    v14 = v60;
    if ( v60 < 0 )
      break;
    v8 = v117;
    if ( !(*(unsigned __int8 (__fastcall **)(CComRegCatalog *))(*(_QWORD *)v117 + 352LL))(v117)
      || v111
      || ClassRegistrationMatchesRequestedClsctx(v59, v113, 0) )
    {
      v61 = v120;
      Interface = CComClassInfo::QueryInterface((CComClassInfo *)v59, a5, v120);
      v14 = Interface;
      if ( Interface < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1F9,
          (unsigned int)"onecore\\com\\combase\\catalog\\regcat.cxx",
          (const char *)(unsigned int)Interface,
          pdwType);
        if ( v105 )
          (*(void (__fastcall **)(struct IGetProcessInfoInternal *))(*(_QWORD *)v105 + 16LL))(v105);
        CComClassInfo::Release((CComClassInfo *)v59);
        if ( hkey )
          RegCloseKey(hkey);
        v78 = v96;
        if ( v96 )
        {
          (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v96 + 104LL))(v96, v95);
          v78 = v96;
        }
        if ( v94 )
        {
          (*(void (__fastcall **)(CComRegCatalog *, struct IUserToken *))(*(_QWORD *)v8 + 128LL))(v8, v97);
          v78 = v96;
        }
        if ( v78 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v78 + 16LL))(v78);
        return v14;
      }
      if ( v105 )
        (*(void (__fastcall **)(struct IGetProcessInfoInternal *))(*(_QWORD *)v105 + 16LL))(v105);
      CComClassInfo::Release((CComClassInfo *)v59);
      if ( hkey )
        RegCloseKey(hkey);
      goto LABEL_62;
    }
    v111 = 1;
    v17 = 1;
    if ( v105 )
      (*(void (__fastcall **)(struct IGetProcessInfoInternal *))(*(_QWORD *)v105 + 16LL))(v105);
    CComClassInfo::Release((CComClassInfo *)v59);
    if ( hkey )
      RegCloseKey(hkey);
    v7 = v119;
    v18 = v107;
LABEL_40:
    if ( v18 > 50 )
    {
      v61 = v120;
LABEL_62:
      if ( *v61 )
      {
        v67 = v96;
        if ( v96 )
        {
          (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v96 + 104LL))(v96, v95);
          v67 = v96;
        }
        if ( v94 )
        {
          (*(void (__fastcall **)(CComRegCatalog *, struct IUserToken *))(*(_QWORD *)v8 + 128LL))(v8, v97);
          v67 = v96;
        }
        if ( v67 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v67 + 16LL))(v67);
        return 0;
      }
      v86 = (const char *)GuidString::GuidString(v123, v121);
      v14 = -2147221165;
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0x202,
        (unsigned int)"onecore\\com\\combase\\catalog\\regcat.cxx",
        (const char *)0x80040153LL,
        (int)"Excessive or cyclic chain of TreatAs values starting from CLSID %ls",
        v86);
LABEL_105:
      v79 = v96;
      if ( !v96 )
        goto LABEL_107;
      goto LABEL_106;
    }
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x1E1,
    (unsigned int)"onecore\\com\\combase\\catalog\\regcat.cxx",
    (const char *)(unsigned int)v60,
    pdwType);
  wil::com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>::~com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>(&v105);
  wil::com_ptr_t<CComClassInfo,wil::err_returncode_policy>::~com_ptr_t<CComClassInfo,wil::err_returncode_policy>(&v116);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
  if ( v96 )
    (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v96 + 104LL))(v96, v95);
  if ( v94 )
  {
    v81 = v117;
    v80 = *(_QWORD *)v117;
LABEL_109:
    (*(void (__fastcall **)(CComRegCatalog *, struct IUserToken *))(v80 + 128))(v81, v97);
  }
LABEL_110:
  wil::com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>::~com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>(&v96);
  return v14;
}

```

## disassembly

```asm
0x180037310  push    rbp
0x180037312  push    rbx
0x180037313  push    rsi
0x180037314  push    rdi
0x180037315  push    r12
0x180037317  push    r13
0x180037319  push    r14
0x18003731b  push    r15
0x18003731d  lea     rbp, [rsp-218h]
0x180037325  sub     rsp, 348h
0x18003732c  mov     rax, cs:__security_cookie
0x180037333  xor     rax, rsp
0x180037336  mov     [rbp+250h+var_50], rax
0x18003733d  mov     r15, [rbp+250h+arg_30]
0x180037344  xor     r12d, r12d
0x180037347  mov     [rbp+250h+var_260], rcx
0x18003734b  mov     rdi, rcx
0x18003734e  mov     rcx, [rbp+250h+arg_28]
0x180037355  mov     rsi, r9
0x180037358  mov     [rbp+250h+var_240], r9
0x18003735c  mov     r9, r8
0x18003735f  mov     [rbp+250h+var_278], edx
0x180037362  mov     [rbp+250h+var_2C0], r8
0x180037366  mov     [rcx], r12
0x180037369  mov     [rbp+250h+var_248], rcx
0x18003736d  mov     [rbp+250h+var_250], r15
0x180037371  test    edx, 0CE8h
0x180037377  jnz     loc_180037DC9
0x18003737d  mov     ebx, edx
0x18003737f  and     ebx, 10000h
0x180037385  jnz     loc_180037DFA
0x18003738b  mov     [rbp+250h+var_2CC], r12d
0x18003738f  lea     rax, [rbp+250h+hKey]
0x180037393  mov     [rbp+250h+var_218], rax
0x180037397  lea     rax, [rbp+250h+var_2B8]
0x18003739b  mov     [rbp+250h+var_210], rax
0x18003739f  lea     rax, [rbp+250h+var_2D0]
0x1800373a3  mov     [rbp+250h+var_208], rax
0x1800373a7  lea     rax, [rbp+250h+var_2C0]
0x1800373ab  mov     [rbp+250h+var_200], rax
0x1800373af  mov     rcx, r12
0x1800373b2  mov     [rbp+250h+var_2C8], rcx
0x1800373b6  mov     r13d, 1
0x1800373bc  mov     [rbp+250h+var_2D0], r12b
0x1800373c0  mov     [rbp+250h+var_2B8], r12b
0x1800373c4  mov     [rbp+250h+hKey], r12
0x1800373c8  mov     qword ptr [rbp+250h+var_220], rdi
0x1800373cc  test    r9, r9
0x1800373cf  jz      loc_180037AFB
0x1800373d5  test    ebx, ebx
0x1800373d7  jnz     loc_180037E19
0x1800373dd  mov     rax, [rdi]
0x1800373e0  lea     r8, [rbp+250h+hKey]
0x1800373e4  mov     rdx, r9
0x1800373e7  mov     rcx, rdi
0x1800373ea  mov     rax, [rax+78h]
0x1800373ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800373f3  mov     ebx, eax
0x1800373f5  test    eax, eax
0x1800373f7  js      loc_180037B2F
0x1800373fd  mov     [rbp+250h+var_2D0], r13b
0x180037401  cmp     [rbp+250h+hKey], r12
0x180037405  jz      loc_180037E35
0x18003740b  mov     rcx, [rbp+250h+var_2C0]
0x18003740f  lea     r8, [rbp+250h+var_290]
0x180037413  mov     [rbp+250h+pSid1], r12
0x180037417  lea     rdx, [rbp+250h+pSid1]
0x18003741b  mov     [rbp+250h+var_290], r12w
0x180037420  mov     rax, [rcx]
0x180037423  mov     rax, [rax+28h]
0x180037427  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003742c  mov     ebx, eax
0x18003742e  test    eax, eax
0x180037430  js      loc_180037D38
0x180037436  mov     rdx, cs:?gSidAnonymous@@3PEAXEA; pSid2
0x18003743d  mov     rcx, [rbp+250h+pSid1]; pSid1
0x180037441  call    cs:__imp_EqualSid
0x180037447  test    eax, eax
0x180037449  jz      loc_180037BDA
0x18003744f  mov     rcx, [rbp+250h+var_2C8]
0x180037453  test    rcx, rcx
0x180037456  jnz     loc_180037B08
0x18003745c  movups  xmm0, xmmword ptr [rsi]
0x18003745f  mov     r14d, r12d
0x180037462  mov     [rbp+250h+var_288], r12d
0x180037466  mov     esi, r12d
0x180037469  mov     [rbp+250h+var_294], r12d
0x18003746d  movdqu  xmmword ptr [rbp+250h+rguid.Data1], xmm0
0x180037472  mov     rbx, [rbp+258h]
0x180037479  lea     rdx, [rbp+250h+sz]; lpsz
0x180037480  mov     r8d, 27h ; '''; cchMax
0x180037486  lea     rcx, [rbp+250h+rguid]; rguid
0x18003748a  call    cs:__imp_StringFromGUID2
0x180037490  cmp     eax, 27h ; '''
0x180037493  jnz     loc_18003793F
0x180037499  xor     edx, edx; Val
0x18003749b  lea     r8d, [rax+33h]; Size
0x18003749f  lea     rcx, [rbp+250h+SubKey]; void *
0x1800374a6  call    memset_0
0x1800374ab  lea     r8, [rbp+250h+SubKey]; unsigned __int16 *
0x1800374b2  lea     rcx, [rbp+250h+rguid]; struct _GUID *
0x1800374b6  call    ?GetPathForClsidKey@@YAJAEBU_GUID@@_KPEAG@Z; GetPathForClsidKey(_GUID const &,unsigned __int64,ushort *)
0x1800374bb  mov     ebx, eax
0x1800374bd  test    eax, eax
0x1800374bf  js      loc_180037FE0
0x1800374c5  mov     [rbp+250h+hkey], r12
0x1800374c9  test    r14d, r14d
0x1800374cc  jnz     short loc_18003750E
0x1800374ce  mov     r9d, [rdi+10h]; unsigned int
0x1800374d2  lea     rax, [rbp+250h+hkey]
0x1800374d6  mov     rcx, [rbp+250h+hKey]; hKey
0x1800374da  lea     rdx, [rbp+250h+SubKey]; lpSubKey
0x1800374e1  mov     [rsp+380h+pvData], rax; HKEY *
0x1800374e6  mov     r8d, 20019h; unsigned int
0x1800374ec  movzx   eax, word ptr [rdi+14h]
0x1800374f0  mov     word ptr [rsp+380h+pdwType], ax; unsigned __int16
0x1800374f5  call    ?OpenKeyInViewHelper@CComRegCatalog@@KAJPEAUHKEY__@@PEBGKKGPEAPEAU2@@Z; CComRegCatalog::OpenKeyInViewHelper(HKEY__ *,ushort const *,ulong,ulong,ushort,HKEY__ * *)
0x1800374fa  mov     r9d, eax
0x1800374fd  cmp     eax, 2
0x180037500  jnz     short loc_180037546
0x180037502  mov     r14d, r13d
0x180037505  mov     [rbp+250h+var_288], r13d
0x180037509  jmp     loc_180037E71
0x18003750e  mov     rax, [rdi]
0x180037511  lea     rcx, [rbp+250h+hkey]
0x180037515  mov     rdx, [rbp+250h+hKey]
0x180037519  lea     r8, [rbp+250h+SubKey]
0x180037520  mov     [rsp+380h+pdwType], rcx
0x180037525  mov     r9d, 20019h
0x18003752b  mov     rcx, rdi
0x18003752e  mov     rax, [rax+98h]
0x180037535  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003753a  mov     r9d, eax; char *
0x18003753d  cmp     eax, 2
0x180037540  jz      loc_1800378BF
0x180037546  test    r9d, r9d
0x180037549  jnz     loc_180037FA9
0x18003754f  mov     ebx, 0C8h
0x180037554  lea     rcx, [rbp+250h+var_120]; void *
0x18003755b  mov     r8d, ebx; Size
0x18003755e  xor     edx, edx; Val
0x180037560  call    memset_0
0x180037565  mov     rcx, [rbp+250h+hkey]; hkey
0x180037569  lea     rax, [rbp+250h+var_274]
0x18003756d  mov     [rsp+380h+pcbData], rax; pcbData
0x180037572  lea     rdx, ?TreatAs@Constants@Catalog@Com@@3QBGB; "TreatAs"
0x180037579  lea     rax, [rbp+250h+var_120]
0x180037580  mov     [rbp+250h+var_274], ebx
0x180037583  mov     [rsp+380h+pvData], rax; pvData
0x180037588  mov     r9d, 0FFFFh; dwFlags
0x18003758e  xor     r8d, r8d; lpValue
0x180037591  mov     [rsp+380h+pdwType], r12; int
0x180037596  call    cs:__imp_RegGetValueW
0x18003759c  mov     ebx, eax
0x18003759e  test    eax, eax
0x1800375a0  jz      loc_180037E7F
0x1800375a6  cmp     eax, 2
0x1800375a9  jnz     loc_180037F92
0x1800375af  mov     [rbp+250h+var_298], r12d
0x1800375b3  cmp     [rbp+250h+var_2B8], r12b
0x1800375b7  jz      loc_180037A63
0x1800375bd  mov     eax, r13d
0x1800375c0  mov     [rbp+250h+var_298], eax
0x1800375c3  cmp     cs:?g_bInSCM@@3JA, r12d; long g_bInSCM
0x1800375ca  jnz     loc_180037A8F
0x1800375d0  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x1800375d7  xor     edx, edx; dwFlags
0x1800375d9  mov     r8d, 198h; dwBytes
0x1800375df  call    cs:__imp_HeapAlloc
0x1800375e5  mov     rbx, rax
0x1800375e8  test    rax, rax
0x1800375eb  jz      loc_180037CAB
0x1800375f1  mov     rcx, [rdi]
0x1800375f4  mov     rax, [rcx+168h]
0x1800375fb  mov     rcx, rdi
0x1800375fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037603  mov     edx, [rdi+20h]
0x180037606  mov     r8b, al
0x180037609  mov     rcx, rbx
0x18003760c  call    ??0CComClassInfo@@QEAA@W4RegistrationSource@@_N@Z; CComClassInfo::CComClassInfo(RegistrationSource,bool)
0x180037611  mov     [rbp+250h+var_268], rax
0x180037615  test    rax, rax
0x180037618  jz      loc_180037CAF
0x18003761e  lock add [rax+38h], r13d
0x180037623  mov     rcx, [rdi]
0x180037626  mov     [rbp+250h+var_2A0], r12
0x18003762a  mov     rax, [rcx+158h]
0x180037631  mov     rcx, rdi
0x180037634  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037639  test    al, al
0x18003763b  jz      loc_180037954
0x180037641  mov     rcx, [rbp+250h+var_2A0]
0x180037645  mov     rax, [r15]
0x180037648  mov     [rbp+250h+var_2A0], r12
0x18003764c  mov     rbx, [rax]
0x18003764f  test    rcx, rcx
0x180037652  jnz     loc_180037EA5
0x180037658  lea     r8, [rbp+250h+var_2A0]
0x18003765c  mov     rcx, r15
0x18003765f  lea     rdx, _GUID_eb3cae6b_6670_4b52_a0a9_d96c3b30180f
0x180037666  mov     rax, rbx
0x180037669  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003766e  mov     ebx, eax
0x180037670  test    eax, eax
0x180037672  js      loc_180037F26
0x180037678  mov     rax, [rdi]
0x18003767b  mov     rcx, rdi
0x18003767e  mov     rax, [rax+150h]
0x180037685  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003768a  mov     rcx, [rdi]
0x18003768d  mov     edx, r14d
0x180037690  mov     [rbp+250h+var_2A8], al
0x180037693  mov     rax, [rcx+90h]
0x18003769a  mov     rcx, rdi
0x18003769d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800376a2  mov     rcx, [rdi]
0x1800376a5  mov     [rbp+250h+var_28C], ax
0x1800376a9  mov     rax, [rcx+138h]
0x1800376b0  mov     rcx, rdi
0x1800376b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800376b8  mov     rcx, [rdi]
0x1800376bb  mov     [rbp+250h+var_2A7], al
0x1800376be  mov     rax, [rcx+148h]
0x1800376c5  mov     rcx, rdi
0x1800376c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800376cd  mov     rcx, [rdi]
0x1800376d0  mov     [rbp+250h+var_28A], ax
0x1800376d4  mov     rax, [rcx+130h]
0x1800376db  mov     rcx, rdi
0x1800376de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800376e3  mov     rcx, [rdi]
0x1800376e6  mov     [rbp+250h+var_2A6], al
0x1800376e9  mov     rax, [rcx+120h]
0x1800376f0  mov     rcx, rdi
0x1800376f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800376f8  mov     rcx, [rdi]
0x1800376fb  mov     [rbp+250h+var_2A5], al
0x1800376fe  mov     rax, [rcx+0C0h]
0x180037705  mov     rcx, rdi
0x180037708  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003770d  mov     rcx, [rdi]
0x180037710  mov     [rbp+250h+var_2A4], al
0x180037713  mov     rax, [rcx+0B8h]
0x18003771a  mov     rcx, rdi
0x18003771d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037722  mov     rcx, [rdi]
0x180037725  mov     r13b, al
0x180037728  mov     rax, [rcx+0B0h]
0x18003772f  mov     rcx, rdi
0x180037732  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037737  mov     rcx, [rdi]
0x18003773a  mov     r15b, al
0x18003773d  mov     r12, [rbp+250h+var_2A0]
0x180037741  mov     edx, r14d
0x180037744  mov     rax, [rcx+88h]
0x18003774b  mov     rcx, rdi
0x18003774e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037753  mov     rcx, [rdi]
0x180037756  mov     esi, eax
0x180037758  mov     r14d, [rbp+250h+var_298]
0x18003775c  mov     rax, [rcx+140h]
0x180037763  mov     rcx, rdi
0x180037766  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003776b  mov     r8, [rbp+250h+var_260]
0x18003776f  mov     ebx, eax
0x180037771  mov     rdi, [rdi+18h]
0x180037775  xor     edx, edx
0x180037777  mov     rcx, [r8]
0x18003777a  mov     rax, [rcx+88h]
0x180037781  mov     rcx, r8
0x180037784  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037789  mov     dl, [rbp+250h+var_2A8]
0x18003778c  mov     ecx, [rbp+250h+var_278]
0x18003778f  mov     r8, [rbp+250h+hkey]
0x180037793  mov     [rsp+380h+var_2E0], dl; bool
0x18003779a  movzx   edx, [rbp+250h+var_28C]
0x18003779e  mov     [rsp+380h+var_2E8], dx; unsigned __int16
0x1800377a6  mov     dl, [rbp+250h+var_2A7]
0x1800377a9  mov     [rsp+380h+var_2F0], dl; bool
0x1800377b0  movzx   edx, [rbp+250h+var_28A]
0x1800377b4  mov     [rsp+380h+var_2F8], dx; unsigned __int16
0x1800377bc  mov     dl, [rbp+250h+var_2A6]
0x1800377bf  shr     ecx, 0Fh
0x1800377c2  mov     [rsp+380h+var_300], dl; bool
0x1800377c9  and     cl, 1
0x1800377cc  mov     dl, [rbp+250h+var_2A5]
0x1800377cf  mov     [rsp+380h+var_308], dl; bool
0x1800377d3  lea     r9, [rbp+250h+SubKey]; unsigned __int16 *
0x1800377da  mov     dl, [rbp+250h+var_2A4]
0x1800377dd  mov     [rsp+380h+var_310], dl; bool
0x1800377e1  mov     rdx, [rbp+250h+var_2C0]; struct IUserToken *
0x1800377e5  mov     [rsp+380h+var_318], r13b; bool
0x1800377ea  mov     [rsp+380h+var_320], r15b; bool
0x1800377ef  mov     [rsp+380h+var_328], cl; bool
0x1800377f3  mov     [rsp+380h+var_330], r12; struct IGetProcessInfoInternal *
0x1800377f8  mov     [rsp+380h+var_338], esi; unsigned int
0x1800377fc  mov     rsi, [rbp+250h+var_268]
0x180037800  mov     [rsp+380h+var_340], r14d; int
0x180037805  mov     rcx, rsi; this
0x180037808  mov     [rsp+380h+var_348], ebx; unsigned int
  ... truncated ...
```
