# CComRegCatalog::GetClassInfoW(ulong,IUserToken *,_GUID const &,_GUID const &,void * *,void *)

- ea: `0x18003e730`
- end: `0x18003f460`
- name: `?GetClassInfoW@CComRegCatalog@@UEAAJKPEAUIUserToken@@AEBU_GUID@@1PEAPEAXPEAX@Z`
- size: `3376`
- prototype: `__int64 __usercall@<rax>(CComRegCatalog *__hidden this@<rcx>, unsigned int@<edx>, struct IUserToken *@<r8>, const struct _GUID *@<r9>, const struct _GUID *, void **, void *)`
- caller_count: `1`
- callee_count: `28`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800d6610`

## callees

- `0x180003194`
- `0x180008d38`
- `0x18000fb8c`
- `0x1800102cc`
- `0x18001c624`
- `0x1800210f8`
- `0x1800245b4`
- `0x180024660`
- `0x18003deac`
- `0x18003dfc8`
- `0x18003e730`
- `0x18003f468`
- `0x18003f4c4`
- `0x18003f770`
- `0x18003f960`
- `0x18003fad0`
- `0x180040548`
- `0x18004056c`
- `0x180060c1c`
- `0x18006ab6c`
- `0x18007102c`
- `0x180095c0c`
- `0x1800968fc`
- `0x1800a2aec`
- `0x1800b7ac0`
- `0x1800b8428`
- `0x1800d2c88`
- `0x180114010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003e9e0`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003e9e0`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18003e991`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18003e991`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003eca7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003edbd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003ee14`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003f0c0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003eca7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003edbd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003ee14`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003f0c0`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18003e861`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18003e861`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18003e8ad`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18003e8ad`

## string_xrefs

- `0x18003f01c`: `onecore\com\combase\catalog\regcat.cxx`
- `0x18003f086`: `onecore\com\combase\catalog\regcat.cxx`
- `0x18003f11c`: `onecore\com\combase\catalog\regcat.cxx`
- `0x18003f1a5`: `onecore\com\combase\catalog\regcat.cxx`
- `0x18003f1d2`: `onecore\com\combase\catalog\regcat.cxx`
- `0x18003f24c`: `onecore\com\combase\catalog\regcat.cxx`
- `0x18003f342`: `onecore\com\combase\catalog\regcat.cxx`
- `0x18003f375`: `onecore\com\combase\catalog\regcat.cxx`
- `0x18003f390`: `onecore\com\combase\catalog\regcat.cxx`
- `0x18003f3c6`: `onecore\com\combase\catalog\regcat.cxx`
- `0x18003f41c`: `onecore\com\combase\catalog\regcat.cxx`
- `0x18003f44f`: `onecore\com\combase\catalog\regcat.cxx`
- `0x18003f349`: `CLSID:%ls`
- `0x18003f428`: `CLSID:%ls`
- `0x18003ed4d`: `onecore\com\combase\inc\ComGuid.hpp`
- `0x18003f3d7`: `Excessive or cyclic chain of TreatAs values starting from CLSID %ls`
- `0x18003f008`: `HRESULT:%#x, CLSID:%ls`
- `0x18003f001`: `CComRegCatalog::GetClassInfoW`

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
  __int64 v14; // rcx
  unsigned int v15; // ebx
  int v16; // eax
  GUID v17; // xmm0
  unsigned int v18; // r14d
  int v19; // esi
  const char *v20; // r9
  unsigned __int64 v21; // rdx
  __int64 (__fastcall *v22)(CComRegCatalog *, HKEY, WCHAR *, __int64, HKEY *); // rbx
  unsigned int v23; // eax
  __int64 v24; // rdx
  __int64 v25; // r8
  const char *v26; // r9
  LSTATUS ValueW; // eax
  unsigned int v28; // ebx
  int v29; // eax
  LPVOID v30; // rbx
  __int64 v31; // r8
  __int64 v32; // rax
  __int64 v33; // rcx
  struct IGetProcessInfoInternal *v34; // rcx
  __int64 (__fastcall **v35)(_QWORD, GUID *, struct IGetProcessInfoInternal **); // rax
  __int64 (__fastcall *v36)(_QWORD, GUID *, struct IGetProcessInfoInternal **); // rbx
  int v37; // eax
  char v38; // al
  __int64 v39; // rcx
  unsigned __int16 v40; // ax
  __int64 v41; // rcx
  char v42; // al
  __int64 v43; // rcx
  unsigned __int16 v44; // ax
  __int64 v45; // rcx
  char v46; // al
  __int64 v47; // rcx
  char v48; // al
  __int64 v49; // rcx
  char v50; // al
  __int64 v51; // rcx
  char v52; // r13
  char v53; // r15
  struct IGetProcessInfoInternal *v54; // r12
  unsigned int v55; // esi
  int v56; // r14d
  unsigned int v57; // ebx
  HKEY v58; // rdi
  unsigned int v59; // eax
  struct IUnknown *v60; // rsi
  int v61; // eax
  void **v62; // r14
  __int64 v63; // rcx
  struct IGetProcessInfoInternal *v65; // rbx
  __int64 v66; // rcx
  int Interface; // eax
  __int64 v68; // rcx
  int v69; // eax
  unsigned int v70; // eax
  __int64 v71; // rdx
  unsigned __int64 v72; // rdx
  unsigned __int8 v73; // cl
  __int64 v74; // rcx
  ComTrace *v75; // rcx
  __int64 v76; // rcx
  struct IUserToken *v77; // r9
  __int64 (__fastcall **v78)(struct IUserToken *, GUID *, __int64 *); // rax
  __int64 (__fastcall *v79)(struct IUserToken *, GUID *, __int64 *); // rbx
  __int64 v80; // rcx
  __int64 v81; // rcx
  __int64 v82; // rax
  CComRegCatalog *v83; // rcx
  __int64 v84; // rdx
  __int64 v85; // r9
  __int64 v86; // rdx
  __int64 v87; // rdx
  const char *v88; // rax
  OLECHAR *v89; // rax
  __int64 v90; // rdx
  int pdwType; // [rsp+20h] [rbp-110h]
  LPDWORD pdwTypea; // [rsp+20h] [rbp-110h]
  LPDWORD pcbData; // [rsp+30h] [rbp-100h]
  unsigned int v94; // [rsp+48h] [rbp-E8h]
  char v95; // [rsp+B0h] [rbp-80h] BYREF
  unsigned int v96; // [rsp+B4h] [rbp-7Ch] BYREF
  __int64 v97; // [rsp+B8h] [rbp-78h] BYREF
  struct IUserToken *v98; // [rsp+C0h] [rbp-70h] BYREF
  HKEY hkey; // [rsp+C8h] [rbp-68h] BYREF
  char v100; // [rsp+D0h] [rbp-60h] BYREF
  bool v101; // [rsp+D1h] [rbp-5Fh]
  bool v102; // [rsp+D2h] [rbp-5Eh]
  bool v103; // [rsp+D3h] [rbp-5Dh]
  bool v104; // [rsp+D4h] [rbp-5Ch]
  bool v105; // [rsp+D5h] [rbp-5Bh]
  struct IGetProcessInfoInternal *v106; // [rsp+D8h] [rbp-58h] BYREF
  int v107; // [rsp+E0h] [rbp-50h] BYREF
  int v108; // [rsp+E4h] [rbp-4Ch]
  __int16 v109[2]; // [rsp+E8h] [rbp-48h] BYREF
  unsigned __int16 v110; // [rsp+ECh] [rbp-44h]
  unsigned __int16 v111; // [rsp+EEh] [rbp-42h]
  int v112; // [rsp+F0h] [rbp-40h]
  HKEY hKey; // [rsp+F8h] [rbp-38h] BYREF
  unsigned int v114; // [rsp+100h] [rbp-30h]
  DWORD v115; // [rsp+104h] [rbp-2Ch] BYREF
  int v116; // [rsp+108h] [rbp-28h] BYREF
  struct IUnknown *v117; // [rsp+110h] [rbp-20h] BYREF
  CComRegCatalog *v118; // [rsp+118h] [rbp-18h]
  PSID pSid1; // [rsp+120h] [rbp-10h] BYREF
  __int64 (__fastcall ***v120)(_QWORD, GUID *, struct IGetProcessInfoInternal **); // [rsp+128h] [rbp-8h]
  void **v121; // [rsp+130h] [rbp+0h]
  GUID *v122; // [rsp+138h] [rbp+8h]
  GUID rguid; // [rsp+140h] [rbp+10h] BYREF
  OLECHAR v124[4]; // [rsp+150h] [rbp+20h] BYREF
  HKEY *p_hKey; // [rsp+158h] [rbp+28h]
  char *v126; // [rsp+160h] [rbp+30h]
  char *v127; // [rsp+168h] [rbp+38h]
  struct IUserToken **v128; // [rsp+170h] [rbp+40h]
  OLECHAR sz[40]; // [rsp+1A0h] [rbp+70h] BYREF
  WCHAR SubKey[48]; // [rsp+1F0h] [rbp+C0h] BYREF
  unsigned __int16 pvData[104]; // [rsp+250h] [rbp+120h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+378h] [rbp+248h]

  v7 = a7;
  v118 = this;
  v8 = this;
  v122 = a4;
  v10 = a3;
  v114 = a2;
  v98 = a3;
  *a6 = 0;
  v121 = a6;
  v120 = a7;
  if ( (a2 & 0xCE8) != 0 )
  {
    v15 = -2147024809;
    v84 = 178;
LABEL_119:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v84,
      (unsigned int)"onecore\\com\\combase\\catalog\\regcat.cxx",
      (const char *)v15,
      pdwType);
    return v15;
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
    v15 = -2147221164;
    v84 = 179;
    goto LABEL_119;
  }
  v10 = v98;
LABEL_3:
  v96 = 0;
  p_hKey = &hKey;
  v126 = &v100;
  v127 = &v95;
  v128 = &v98;
  v12 = 0;
  v97 = 0;
  v95 = 0;
  v100 = 0;
  hKey = 0;
  *(_QWORD *)v124 = v8;
  if ( v10 )
  {
    if ( v11 )
    {
      lambda_6f6522c49679d9fbe761af3c1bc61942_::operator()(v124);
    }
    else
    {
      PathForClsidKey = (*(__int64 (__fastcall **)(CComRegCatalog *, struct IUserToken *, HKEY *))(*(_QWORD *)v8 + 120LL))(
                          v8,
                          v10,
                          &hKey);
      v15 = PathForClsidKey;
      if ( PathForClsidKey < 0 )
      {
        if ( PathForClsidKey != -2147024894 )
        {
          v71 = 263;
          goto LABEL_144;
        }
        if ( !(*(unsigned __int8 (__fastcall **)(CComRegCatalog *))(*(_QWORD *)v8 + 168LL))(v8) )
        {
          if ( ComTrace::IsEnabled(v73, v72) )
          {
            wil::details::static_lazy<ComTrace>::get(
              v74,
              _lambda_f8a79a44bba2ee3470b25df359f31864_::_lambda_invoker_cdecl_);
            ComTrace::LogVerbose_(v75, L"No private hive for package");
          }
          goto LABEL_43;
        }
        lambda_6f6522c49679d9fbe761af3c1bc61942_::operator()(v124);
      }
      else
      {
        v95 = 1;
      }
      if ( !hKey )
      {
        MicrosoftTelemetryAssertTriggeredNoArgs(v14);
        v15 = -2147418113;
        v71 = 266;
        v85 = 2147549183LL;
LABEL_145:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v71,
          (unsigned int)"onecore\\com\\combase\\catalog\\regcat.cxx",
          (const char *)v85,
          pdwType);
        goto LABEL_105;
      }
    }
    pSid1 = 0;
    v109[0] = 0;
    v16 = (*(__int64 (__fastcall **)(struct IUserToken *, PSID *, __int16 *))(*(_QWORD *)v98 + 40LL))(v98, &pSid1, v109);
    v15 = v16;
    if ( v16 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x116,
        (unsigned int)"onecore\\com\\combase\\catalog\\regcat.cxx",
        (const char *)(unsigned int)v16,
        pdwType);
      v81 = v97;
      if ( !v97 )
      {
LABEL_107:
        if ( v95 )
        {
          v82 = *(_QWORD *)v8;
          v83 = v8;
          goto LABEL_109;
        }
        goto LABEL_110;
      }
LABEL_106:
      (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v97 + 104LL))(v81, v96);
      goto LABEL_107;
    }
    if ( !EqualSid(pSid1, gSidAnonymous) )
    {
      v76 = v97;
      v77 = v98;
      v78 = *(__int64 (__fastcall ***)(struct IUserToken *, GUID *, __int64 *))v98;
      v97 = 0;
      v79 = *v78;
      if ( v76 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v76 + 16LL))(v76);
        v77 = v98;
      }
      PathForClsidKey = v79(v77, &GUID_000001fc_0000_0000_cfff_123045660046, &v97);
      v15 = PathForClsidKey;
      if ( PathForClsidKey < 0 )
      {
        v71 = 281;
        goto LABEL_144;
      }
    }
    v12 = v97;
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
                        &v96);
    v15 = PathForClsidKey;
    if ( PathForClsidKey < 0 )
    {
      v71 = 296;
LABEL_144:
      v85 = (unsigned int)PathForClsidKey;
      goto LABEL_145;
    }
  }
  v17 = *a4;
  v18 = 0;
  v112 = 0;
  v19 = 0;
  v108 = 0;
  rguid = v17;
  while ( 1 )
  {
    while ( 1 )
    {
      if ( StringFromGUID2(&rguid, sz, 39) != 39 )
        wil::details::in1diag3::_FailFast_Unexpected(
          retaddr,
          (void *)0x19,
          (unsigned int)"onecore\\com\\combase\\inc\\ComGuid.hpp",
          v20);
      memset_0(SubKey, 0, 0x5Au);
      PathForClsidKey = GetPathForClsidKey(&rguid, v21, SubKey);
      v15 = PathForClsidKey;
      if ( PathForClsidKey < 0 )
      {
        v71 = 315;
        goto LABEL_144;
      }
      hkey = 0;
      if ( v18 )
      {
        v22 = *(__int64 (__fastcall **)(CComRegCatalog *, HKEY, WCHAR *, __int64, HKEY *))(*(_QWORD *)v8 + 152LL);
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
          &hkey,
          0);
        v23 = v22(v8, hKey, SubKey, 131097, &hkey);
        v26 = (const char *)v23;
        if ( v23 != 2 )
          goto LABEL_17;
        if ( gfEnableTracing && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        {
          LODWORD(pcbData) = -2147221164;
          LODWORD(pdwTypea) = 3;
          ComTraceMessage(
            2147746132LL,
            "onecore\\com\\combase\\catalog\\regcat.cxx",
            "CComRegCatalog::GetClassInfoW",
            382,
            pdwTypea,
            L"HRESULT:%#x, CLSID:%ls",
            pcbData,
            sz);
        }
        if ( hkey )
          RegCloseKey(hkey);
LABEL_43:
        v63 = v97;
        if ( v97 )
        {
          (*(void (__fastcall **)(__int64, _QWORD, __int64, const char *))(*(_QWORD *)v97 + 104LL))(v97, v96, v25, v26);
          v63 = v97;
        }
        if ( v95 )
        {
          (*(void (__fastcall **)(CComRegCatalog *, struct IUserToken *, __int64, const char *))(*(_QWORD *)v8 + 128LL))(
            v8,
            v98,
            v25,
            v26);
          v63 = v97;
        }
        if ( v63 )
          (*(void (__fastcall **)(__int64, __int64, __int64, const char *))(*(_QWORD *)v63 + 16LL))(v63, v24, v25, v26);
        return 2147746132LL;
      }
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
        &hkey,
        0);
      v70 = CComRegCatalog::OpenKeyInViewHelper(hKey, SubKey, 0x20019u, *((_DWORD *)v8 + 4), *((_WORD *)v8 + 10), &hkey);
      v26 = (const char *)v70;
      if ( v70 == 2 )
      {
        v18 = 1;
        v112 = 1;
        goto LABEL_127;
      }
LABEL_17:
      if ( (_DWORD)v26 )
      {
        v89 = sz;
        v90 = 387;
        goto LABEL_142;
      }
      memset_0(pvData, 0, 0xC8u);
      v115 = 200;
      ValueW = RegGetValueW(hkey, L"TreatAs", 0, 0xFFFFu, 0, pvData, &v115);
      v28 = ValueW;
      if ( !ValueW )
      {
        if ( (v115 & 0xFFFFFFFE) < 0x4A )
        {
          v86 = 396;
          goto LABEL_132;
        }
        if ( !CurlyStringToGUID(pvData, &rguid) )
        {
          v86 = 397;
LABEL_132:
          v15 = -2147221165;
LABEL_134:
          wil::details::in1diag3::Return_HrMsg(
            retaddr,
            (void *)v86,
            (unsigned int)"onecore\\com\\combase\\catalog\\regcat.cxx",
            (const char *)v15,
            (int)"CLSID:%ls",
            (const char *)sz);
          goto LABEL_104;
        }
        v108 = ++v19;
LABEL_127:
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
        goto LABEL_38;
      }
      if ( ValueW != 2 )
      {
        v89 = (OLECHAR *)GuidString::GuidString(v124, &rguid);
        v26 = (const char *)v28;
        v90 = 405;
LABEL_142:
        v15 = wil::details::in1diag3::Return_Win32Msg(
                retaddr,
                (void *)v90,
                (unsigned int)"onecore\\com\\combase\\catalog\\regcat.cxx",
                v26,
                (unsigned int)"CLSID:%ls",
                (const char *)v89);
        goto LABEL_104;
      }
      v107 = 0;
      if ( v100 )
      {
        v29 = 1;
        v107 = 1;
      }
      else
      {
        v69 = (*(__int64 (__fastcall **)(CComRegCatalog *, HKEY, int *))(*(_QWORD *)v8 + 160LL))(v8, hkey, &v107);
        v15 = v69;
        if ( v69 < 0 )
        {
          v87 = 424;
          goto LABEL_137;
        }
        v29 = v107;
      }
      if ( !g_bInSCM || v29 )
        break;
      v116 = 0;
      v69 = CComRegCatalog::CheckForceHKLMForCLSID(v8, hKey, hkey, &v116);
      v15 = v69;
      if ( v69 < 0 )
      {
        v87 = 430;
LABEL_137:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v87,
          (unsigned int)"onecore\\com\\combase\\catalog\\regcat.cxx",
          (const char *)(unsigned int)v69,
          pdwType);
        goto LABEL_104;
      }
      if ( !v116 )
        break;
      if ( !(*(unsigned __int8 (__fastcall **)(CComRegCatalog *))(*(_QWORD *)v8 + 168LL))(v8) )
      {
        v15 = -2147221161;
        v86 = 442;
        goto LABEL_134;
      }
      lambda_6f6522c49679d9fbe761af3c1bc61942_::operator()(v124);
      v108 = 0;
      v19 = 0;
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
    }
    v30 = HeapAlloc(g_hHeap, 0, 0x198u);
    if ( !v30 )
    {
      v117 = 0;
LABEL_102:
      v15 = -2147024882;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1C1,
        (unsigned int)"onecore\\com\\combase\\catalog\\regcat.cxx",
        (const char *)0x8007000ELL,
        pdwType);
LABEL_103:
      wil::com_ptr_t<CComClassInfo,wil::err_returncode_policy>::~com_ptr_t<CComClassInfo,wil::err_returncode_policy>(&v117);
LABEL_104:
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
      goto LABEL_105;
    }
    LOBYTE(v31) = (*(__int64 (__fastcall **)(CComRegCatalog *))(*(_QWORD *)v8 + 360LL))(v8);
    v32 = CComClassInfo::CComClassInfo(v30, *((unsigned int *)v8 + 8), v31);
    v117 = (struct IUnknown *)v32;
    if ( !v32 )
      goto LABEL_102;
    _InterlockedAdd((volatile signed __int32 *)(v32 + 56), 1u);
    v33 = *(_QWORD *)v8;
    v106 = 0;
    if ( (*(unsigned __int8 (__fastcall **)(CComRegCatalog *))(v33 + 344))(v8) )
    {
      v34 = v106;
      v35 = *v7;
      v106 = 0;
      v36 = *v35;
      if ( v34 )
        (*(void (__fastcall **)(struct IGetProcessInfoInternal *))(*(_QWORD *)v34 + 16LL))(v34);
      v37 = v36(v7, &GUID_eb3cae6b_6670_4b52_a0a9_d96c3b30180f, &v106);
      v15 = v37;
      if ( v37 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1C6,
          (unsigned int)"onecore\\com\\combase\\catalog\\regcat.cxx",
          (const char *)(unsigned int)v37,
          pdwType);
        wil::com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>::~com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>(&v106);
        goto LABEL_103;
      }
    }
    else
    {
      v65 = v106;
      v106 = (struct IGetProcessInfoInternal *)(((unsigned __int64)v8 + 8) & -(__int64)(v8 != 0));
      if ( v106 )
      {
        v66 = ((unsigned __int64)v8 + 8) & -(__int64)(v8 != 0);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v66 + 8LL))(v66);
      }
      if ( v65 )
        (*(void (__fastcall **)(struct IGetProcessInfoInternal *))(*(_QWORD *)v65 + 16LL))(v65);
    }
    v38 = (*(__int64 (__fastcall **)(CComRegCatalog *))(*(_QWORD *)v8 + 336LL))(v8);
    v39 = *(_QWORD *)v8;
    v101 = v38;
    v40 = (*(__int64 (__fastcall **)(CComRegCatalog *, _QWORD))(v39 + 144))(v8, v18);
    v41 = *(_QWORD *)v8;
    v110 = v40;
    v42 = (*(__int64 (__fastcall **)(CComRegCatalog *))(v41 + 312))(v8);
    v43 = *(_QWORD *)v8;
    v102 = v42;
    v44 = (*(__int64 (__fastcall **)(CComRegCatalog *))(v43 + 328))(v8);
    v45 = *(_QWORD *)v8;
    v111 = v44;
    v46 = (*(__int64 (__fastcall **)(CComRegCatalog *))(v45 + 304))(v8);
    v47 = *(_QWORD *)v8;
    v103 = v46;
    v48 = (*(__int64 (__fastcall **)(CComRegCatalog *))(v47 + 288))(v8);
    v49 = *(_QWORD *)v8;
    v104 = v48;
    v50 = (*(__int64 (__fastcall **)(CComRegCatalog *))(v49 + 192))(v8);
    v51 = *(_QWORD *)v8;
    v105 = v50;
    v52 = (*(__int64 (__fastcall **)(CComRegCatalog *))(v51 + 184))(v8);
    v53 = (*(__int64 (__fastcall **)(CComRegCatalog *))(*(_QWORD *)v8 + 176LL))(v8);
    v54 = v106;
    v55 = (*(__int64 (__fastcall **)(CComRegCatalog *, _QWORD))(*(_QWORD *)v8 + 136LL))(v8, v18);
    v56 = v107;
    v57 = (*(__int64 (__fastcall **)(CComRegCatalog *))(*(_QWORD *)v8 + 320LL))(v8);
    v58 = (HKEY)*((_QWORD *)v8 + 3);
    v59 = (*(__int64 (__fastcall **)(CComRegCatalog *, _QWORD))(*(_QWORD *)v118 + 136LL))(v118, 0);
    v94 = v55;
    v60 = v117;
    v61 = CComClassInfo::FinalConstruct(
            (CComClassInfo *)v117,
            v98,
            &rguid,
            SubKey,
            hkey,
            v59,
            v58,
            v57,
            v56,
            v94,
            v54,
            (v114 & 0x8000) != 0,
            v53,
            v52,
            v105,
            v104,
            v103,
            v111,
            v102,
            v110,
            v101);
    v15 = v61;
    if ( v61 < 0 )
      break;
    v8 = v118;
    if ( !(*(unsigned __int8 (__fastcall **)(CComRegCatalog *))(*(_QWORD *)v118 + 352LL))(v118)
      || v112
      || ClassRegistrationMatchesRequestedClsctx(v60, v114, 0) )
    {
      v62 = v121;
      Interface = CComClassInfo::QueryInterface((CComClassInfo *)v60, a5, v121);
      v15 = Interface;
      if ( Interface < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1F9,
          (unsigned int)"onecore\\com\\combase\\catalog\\regcat.cxx",
          (const char *)(unsigned int)Interface,
          pdwType);
        if ( v106 )
          (*(void (__fastcall **)(struct IGetProcessInfoInternal *))(*(_QWORD *)v106 + 16LL))(v106);
        CComClassInfo::Release((CComClassInfo *)v60);
        if ( hkey )
          RegCloseKey(hkey);
        v80 = v97;
        if ( v97 )
        {
          (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v97 + 104LL))(v97, v96);
          v80 = v97;
        }
        if ( v95 )
        {
          (*(void (__fastcall **)(CComRegCatalog *, struct IUserToken *))(*(_QWORD *)v8 + 128LL))(v8, v98);
          v80 = v97;
        }
        if ( v80 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v80 + 16LL))(v80);
        return v15;
      }
      if ( v106 )
        (*(void (__fastcall **)(struct IGetProcessInfoInternal *))(*(_QWORD *)v106 + 16LL))(v106);
      CComClassInfo::Release((CComClassInfo *)v60);
      if ( hkey )
        RegCloseKey(hkey);
      goto LABEL_60;
    }
    v112 = 1;
    v18 = 1;
    if ( v106 )
      (*(void (__fastcall **)(struct IGetProcessInfoInternal *))(*(_QWORD *)v106 + 16LL))(v106);
    CComClassInfo::Release((CComClassInfo *)v60);
    if ( hkey )
      RegCloseKey(hkey);
    v7 = v120;
    v19 = v108;
LABEL_38:
    if ( v19 > 50 )
    {
      v62 = v121;
LABEL_60:
      if ( *v62 )
      {
        v68 = v97;
        if ( v97 )
        {
          (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v97 + 104LL))(v97, v96);
          v68 = v97;
        }
        if ( v95 )
        {
          (*(void (__fastcall **)(CComRegCatalog *, struct IUserToken *))(*(_QWORD *)v8 + 128LL))(v8, v98);
          v68 = v97;
        }
        if ( v68 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v68 + 16LL))(v68);
        return 0;
      }
      v88 = (const char *)GuidString::GuidString(v124, v122);
      v15 = -2147221165;
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0x202,
        (unsigned int)"onecore\\com\\combase\\catalog\\regcat.cxx",
        (const char *)0x80040153LL,
        (int)"Excessive or cyclic chain of TreatAs values starting from CLSID %ls",
        v88);
LABEL_105:
      v81 = v97;
      if ( !v97 )
        goto LABEL_107;
      goto LABEL_106;
    }
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x1E1,
    (unsigned int)"onecore\\com\\combase\\catalog\\regcat.cxx",
    (const char *)(unsigned int)v61,
    pdwType);
  wil::com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>::~com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>(&v106);
  wil::com_ptr_t<CComClassInfo,wil::err_returncode_policy>::~com_ptr_t<CComClassInfo,wil::err_returncode_policy>(&v117);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
  if ( v97 )
    (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v97 + 104LL))(v97, v96);
  if ( v95 )
  {
    v83 = v118;
    v82 = *(_QWORD *)v118;
LABEL_109:
    (*(void (__fastcall **)(CComRegCatalog *, struct IUserToken *))(v82 + 128))(v83, v98);
  }
LABEL_110:
  wil::com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>::~com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>(&v97);
  return v15;
}

```

## disassembly

```asm
0x18003e730  push    rbp
0x18003e732  push    rbx
0x18003e733  push    rsi
0x18003e734  push    rdi
0x18003e735  push    r12
0x18003e737  push    r13
0x18003e739  push    r14
0x18003e73b  push    r15
0x18003e73d  lea     rbp, [rsp-208h]
0x18003e745  sub     rsp, 338h
0x18003e74c  mov     rax, cs:__security_cookie
0x18003e753  xor     rax, rsp
0x18003e756  mov     [rbp+240h+var_50], rax
0x18003e75d  mov     r15, [rbp+240h+arg_30]
0x18003e764  xor     r12d, r12d
0x18003e767  mov     [rbp+240h+var_258], rcx
0x18003e76b  mov     rdi, rcx
0x18003e76e  mov     rcx, [rbp+240h+arg_28]
0x18003e775  mov     rsi, r9
0x18003e778  mov     [rbp+240h+var_238], r9
0x18003e77c  mov     r9, r8
0x18003e77f  mov     [rbp+240h+var_270], edx
0x18003e782  mov     [rbp+240h+var_2B0], r8
0x18003e786  mov     [rcx], r12
0x18003e789  mov     [rbp+240h+var_240], rcx
0x18003e78d  mov     [rbp+240h+var_248], r15
0x18003e791  test    edx, 0CE8h
0x18003e797  jnz     loc_18003F22F
0x18003e79d  mov     ebx, edx
0x18003e79f  and     ebx, 10000h
0x18003e7a5  jnz     loc_18003F260
0x18003e7ab  mov     [rbp+240h+var_2BC], r12d
0x18003e7af  lea     rax, [rbp+240h+hKey]
0x18003e7b3  mov     [rbp+240h+var_218], rax
0x18003e7b7  lea     rax, [rbp+240h+var_2A0]
0x18003e7bb  mov     [rbp+240h+var_210], rax
0x18003e7bf  lea     rax, [rbp+240h+var_2C0]
0x18003e7c3  mov     [rbp+240h+var_208], rax
0x18003e7c7  lea     rax, [rbp+240h+var_2B0]
0x18003e7cb  mov     [rbp+240h+var_200], rax
0x18003e7cf  mov     rcx, r12
0x18003e7d2  mov     [rbp+240h+var_2B8], rcx
0x18003e7d6  mov     r13d, 1
0x18003e7dc  mov     [rbp+240h+var_2C0], r12b
0x18003e7e0  mov     [rbp+240h+var_2A0], r12b
0x18003e7e4  mov     [rbp+240h+hKey], r12
0x18003e7e8  mov     qword ptr [rbp+240h+var_220], rdi
0x18003e7ec  test    r9, r9
0x18003e7ef  jz      loc_18003EF5E
0x18003e7f5  test    ebx, ebx
0x18003e7f7  jnz     loc_18003F27F
0x18003e7fd  mov     rax, [rdi]
0x18003e800  lea     r8, [rbp+240h+hKey]
0x18003e804  mov     rdx, r9
0x18003e807  mov     rcx, rdi
0x18003e80a  mov     rax, [rax+78h]
0x18003e80e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e813  mov     ebx, eax
0x18003e815  test    eax, eax
0x18003e817  js      loc_18003EF92
0x18003e81d  mov     [rbp+240h+var_2C0], r13b
0x18003e821  cmp     [rbp+240h+hKey], r12
0x18003e825  jz      loc_18003F29B
0x18003e82b  mov     rcx, [rbp+240h+var_2B0]
0x18003e82f  lea     r8, [rbp+240h+var_288]
0x18003e833  mov     [rbp+240h+pSid1], r12
0x18003e837  lea     rdx, [rbp+240h+pSid1]
0x18003e83b  mov     [rbp+240h+var_288], r12w
0x18003e840  mov     rax, [rcx]
0x18003e843  mov     rax, [rax+28h]
0x18003e847  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e84c  mov     ebx, eax
0x18003e84e  test    eax, eax
0x18003e850  js      loc_18003F19E
0x18003e856  mov     rdx, cs:?gSidAnonymous@@3PEAXEA; pSid2
0x18003e85d  mov     rcx, [rbp+240h+pSid1]; pSid1
0x18003e861  call    cs:__imp_EqualSid
0x18003e868  nop     dword ptr [rax+rax+00h]
0x18003e86d  test    eax, eax
0x18003e86f  jz      loc_18003F03A
0x18003e875  mov     rcx, [rbp+240h+var_2B8]
0x18003e879  test    rcx, rcx
0x18003e87c  jnz     loc_18003EF6B
0x18003e882  movups  xmm0, xmmword ptr [rsi]
0x18003e885  mov     r14d, r12d
0x18003e888  mov     [rbp+240h+var_280], r12d
0x18003e88c  mov     esi, r12d
0x18003e88f  mov     [rbp+240h+var_28C], r12d
0x18003e893  movdqu  xmmword ptr [rbp+240h+rguid.Data1], xmm0
0x18003e898  mov     rbx, [rbp+248h]
0x18003e89f  lea     rdx, [rbp+240h+sz]; lpsz
0x18003e8a3  mov     r8d, 27h ; '''; cchMax
0x18003e8a9  lea     rcx, [rbp+240h+rguid]; rguid
0x18003e8ad  call    cs:__imp_StringFromGUID2
0x18003e8b4  nop     dword ptr [rax+rax+00h]
0x18003e8b9  cmp     eax, 27h ; '''
0x18003e8bc  jnz     loc_18003ED4D
0x18003e8c2  xor     edx, edx; Val
0x18003e8c4  lea     r8d, [rax+33h]; Size
0x18003e8c8  lea     rcx, [rbp+240h+SubKey]; void *
0x18003e8cf  call    memset_0
0x18003e8d4  lea     r8, [rbp+240h+SubKey]; unsigned __int16 *
0x18003e8db  lea     rcx, [rbp+240h+rguid]; struct _GUID *
0x18003e8df  call    ?GetPathForClsidKey@@YAJAEBU_GUID@@_KPEAG@Z; GetPathForClsidKey(_GUID const &,unsigned __int64,ushort *)
0x18003e8e4  mov     ebx, eax
0x18003e8e6  test    eax, eax
0x18003e8e8  js      loc_18003F440
0x18003e8ee  xor     edx, edx
0x18003e8f0  mov     [rbp+240h+hkey], r12
0x18003e8f4  lea     rcx, [rbp+240h+hkey]
0x18003e8f8  test    r14d, r14d
0x18003e8fb  jz      loc_18003EEA9
0x18003e901  mov     rax, [rdi]
0x18003e904  mov     rbx, [rax+98h]
0x18003e90b  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18003e910  mov     rdx, [rbp+240h+hKey]
0x18003e914  lea     rax, [rbp+240h+hkey]
0x18003e918  mov     [rsp+370h+pdwType], rax
0x18003e91d  lea     r8, [rbp+240h+SubKey]
0x18003e924  mov     rax, rbx
0x18003e927  mov     r9d, 20019h
0x18003e92d  mov     rcx, rdi
0x18003e930  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e935  mov     r9d, eax; char *
0x18003e938  cmp     eax, 2
0x18003e93b  jz      loc_18003ECCC
0x18003e941  test    r9d, r9d
0x18003e944  jnz     loc_18003F40C
0x18003e94a  mov     ebx, 0C8h
0x18003e94f  lea     rcx, [rbp+240h+var_120]; void *
0x18003e956  mov     r8d, ebx; Size
0x18003e959  xor     edx, edx; Val
0x18003e95b  call    memset_0
0x18003e960  mov     rcx, [rbp+240h+hkey]; hkey
0x18003e964  lea     rax, [rbp+240h+var_26C]
0x18003e968  mov     [rsp+370h+pcbData], rax; pcbData
0x18003e96d  lea     rdx, ?TreatAs@Constants@Catalog@Com@@3QBGB; "TreatAs"
0x18003e974  lea     rax, [rbp+240h+var_120]
0x18003e97b  mov     [rbp+240h+var_26C], ebx
0x18003e97e  mov     [rsp+370h+pvData], rax; pvData
0x18003e983  mov     r9d, 0FFFFh; dwFlags
0x18003e989  xor     r8d, r8d; lpValue
0x18003e98c  mov     [rsp+370h+pdwType], r12; int
0x18003e991  call    cs:__imp_RegGetValueW
0x18003e998  nop     dword ptr [rax+rax+00h]
0x18003e99d  mov     ebx, eax
0x18003e99f  test    eax, eax
0x18003e9a1  jz      loc_18003F2E5
0x18003e9a7  cmp     eax, 2
0x18003e9aa  jnz     loc_18003F3F5
0x18003e9b0  mov     [rbp+240h+var_290], r12d
0x18003e9b4  cmp     [rbp+240h+var_2A0], r12b
0x18003e9b8  jz      loc_18003EE7D
0x18003e9be  mov     eax, r13d
0x18003e9c1  mov     [rbp+240h+var_290], eax
0x18003e9c4  cmp     cs:?g_bInSCM@@3JA, r12d; long g_bInSCM
0x18003e9cb  jnz     loc_18003EEF2
0x18003e9d1  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x18003e9d8  xor     edx, edx; dwFlags
0x18003e9da  mov     r8d, 198h; dwBytes
0x18003e9e0  call    cs:__imp_HeapAlloc
0x18003e9e7  nop     dword ptr [rax+rax+00h]
0x18003e9ec  mov     rbx, rax
0x18003e9ef  test    rax, rax
0x18003e9f2  jz      loc_18003F111
0x18003e9f8  mov     rcx, [rdi]
0x18003e9fb  mov     rax, [rcx+168h]
0x18003ea02  mov     rcx, rdi
0x18003ea05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ea0a  mov     edx, [rdi+20h]
0x18003ea0d  mov     r8b, al
0x18003ea10  mov     rcx, rbx
0x18003ea13  call    ??0CComClassInfo@@QEAA@W4RegistrationSource@@_N@Z; CComClassInfo::CComClassInfo(RegistrationSource,bool)
0x18003ea18  mov     [rbp+240h+var_260], rax
0x18003ea1c  test    rax, rax
0x18003ea1f  jz      loc_18003F115
0x18003ea25  lock add [rax+38h], r13d
0x18003ea2a  mov     rcx, [rdi]
0x18003ea2d  mov     [rbp+240h+var_298], r12
0x18003ea31  mov     rax, [rcx+158h]
0x18003ea38  mov     rcx, rdi
0x18003ea3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ea40  test    al, al
0x18003ea42  jz      loc_18003ED62
0x18003ea48  mov     rcx, [rbp+240h+var_298]
0x18003ea4c  mov     rax, [r15]
0x18003ea4f  mov     [rbp+240h+var_298], r12
0x18003ea53  mov     rbx, [rax]
0x18003ea56  test    rcx, rcx
0x18003ea59  jnz     loc_18003F30B
0x18003ea5f  lea     r8, [rbp+240h+var_298]
0x18003ea63  mov     rcx, r15
0x18003ea66  lea     rdx, _GUID_eb3cae6b_6670_4b52_a0a9_d96c3b30180f
0x18003ea6d  mov     rax, rbx
0x18003ea70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ea75  mov     ebx, eax
0x18003ea77  test    eax, eax
0x18003ea79  js      loc_18003F389
0x18003ea7f  mov     rax, [rdi]
0x18003ea82  mov     rcx, rdi
0x18003ea85  mov     rax, [rax+150h]
0x18003ea8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ea91  mov     rcx, [rdi]
0x18003ea94  mov     edx, r14d
0x18003ea97  mov     [rbp+240h+var_29F], al
0x18003ea9a  mov     rax, [rcx+90h]
0x18003eaa1  mov     rcx, rdi
0x18003eaa4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003eaa9  mov     rcx, [rdi]
0x18003eaac  mov     [rbp+240h+var_284], ax
0x18003eab0  mov     rax, [rcx+138h]
0x18003eab7  mov     rcx, rdi
0x18003eaba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003eabf  mov     rcx, [rdi]
0x18003eac2  mov     [rbp+240h+var_29E], al
0x18003eac5  mov     rax, [rcx+148h]
0x18003eacc  mov     rcx, rdi
0x18003eacf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ead4  mov     rcx, [rdi]
0x18003ead7  mov     [rbp+240h+var_282], ax
0x18003eadb  mov     rax, [rcx+130h]
0x18003eae2  mov     rcx, rdi
0x18003eae5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003eaea  mov     rcx, [rdi]
0x18003eaed  mov     [rbp+240h+var_29D], al
0x18003eaf0  mov     rax, [rcx+120h]
0x18003eaf7  mov     rcx, rdi
0x18003eafa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003eaff  mov     rcx, [rdi]
0x18003eb02  mov     [rbp+240h+var_29C], al
0x18003eb05  mov     rax, [rcx+0C0h]
0x18003eb0c  mov     rcx, rdi
0x18003eb0f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003eb14  mov     rcx, [rdi]
0x18003eb17  mov     [rbp+240h+var_29B], al
0x18003eb1a  mov     rax, [rcx+0B8h]
0x18003eb21  mov     rcx, rdi
0x18003eb24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003eb29  mov     rcx, [rdi]
0x18003eb2c  mov     r13b, al
0x18003eb2f  mov     rax, [rcx+0B0h]
0x18003eb36  mov     rcx, rdi
0x18003eb39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003eb3e  mov     rcx, [rdi]
0x18003eb41  mov     r15b, al
0x18003eb44  mov     r12, [rbp+240h+var_298]
0x18003eb48  mov     edx, r14d
0x18003eb4b  mov     rax, [rcx+88h]
0x18003eb52  mov     rcx, rdi
0x18003eb55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003eb5a  mov     rcx, [rdi]
0x18003eb5d  mov     esi, eax
0x18003eb5f  mov     r14d, [rbp+240h+var_290]
0x18003eb63  mov     rax, [rcx+140h]
0x18003eb6a  mov     rcx, rdi
0x18003eb6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003eb72  mov     r8, [rbp+240h+var_258]
0x18003eb76  mov     ebx, eax
0x18003eb78  mov     rdi, [rdi+18h]
0x18003eb7c  xor     edx, edx
0x18003eb7e  mov     rcx, [r8]
0x18003eb81  mov     rax, [rcx+88h]
0x18003eb88  mov     rcx, r8
0x18003eb8b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003eb90  mov     dl, [rbp+240h+var_29F]
0x18003eb93  mov     ecx, [rbp+240h+var_270]
0x18003eb96  mov     r8, [rbp+240h+hkey]
0x18003eb9a  mov     [rsp+370h+var_2D0], dl; bool
0x18003eba1  movzx   edx, [rbp+240h+var_284]
0x18003eba5  mov     [rsp+370h+var_2D8], dx; unsigned __int16
0x18003ebad  mov     dl, [rbp+240h+var_29E]
0x18003ebb0  mov     [rsp+370h+var_2E0], dl; bool
0x18003ebb7  movzx   edx, [rbp+240h+var_282]
0x18003ebbb  mov     [rsp+370h+var_2E8], dx; unsigned __int16
0x18003ebc3  mov     dl, [rbp+240h+var_29D]
0x18003ebc6  shr     ecx, 0Fh
0x18003ebc9  mov     [rsp+370h+var_2F0], dl; bool
0x18003ebd0  and     cl, 1
0x18003ebd3  mov     dl, [rbp+240h+var_29C]
0x18003ebd6  mov     [rsp+370h+var_2F8], dl; bool
0x18003ebda  lea     r9, [rbp+240h+SubKey]; unsigned __int16 *
0x18003ebe1  mov     dl, [rbp+240h+var_29B]
0x18003ebe4  mov     [rsp+370h+var_300], dl; bool
0x18003ebe8  mov     rdx, [rbp+240h+var_2B0]; struct IUserToken *
0x18003ebec  mov     [rsp+370h+var_308], r13b; bool
0x18003ebf1  mov     [rsp+370h+var_310], r15b; bool
0x18003ebf6  mov     [rsp+370h+var_318], cl; bool
0x18003ebfa  mov     [rsp+370h+var_320], r12; struct IGetProcessInfoInternal *
0x18003ebff  mov     [rsp+370h+var_328], esi; unsigned int
0x18003ec03  mov     rsi, [rbp+240h+var_260]
0x18003ec07  mov     [rsp+370h+var_330], r14d; int
0x18003ec0c  mov     rcx, rsi; this
0x18003ec0f  mov     [rsp+370h+var_338], ebx; unsigned int
0x18003ec13  mov     [rsp+370h+pcbData], rdi; HKEY
0x18003ec18  mov     dword ptr [rsp+370h+pvData], eax; unsigned int
0x18003ec1c  mov     [rsp+370h+pdwType], r8; int
0x18003ec21  lea     r8, [rbp+240h+rguid]; struct _GUID *
0x18003ec25  call    ?FinalConstruct@CComClassInfo@@QEAAJPEAUIUserToken@@PEBU_GUID@@PEAGPEAUHKEY__@@K3KHKPEAUIGetProcessInfoInternal@@_N55555G5G5@Z; CComClassInfo::FinalConstruct(IUserToken *,_GUID const *,ushort *,HKEY__ *,ulong,HKEY__ *,ulong,int,ulong,IGetProcessInfoInternal *,bool,bool,bool,bool,bool,bool,ushort,bool,ushort,bool)
0x18003ec2a  xor     r12d, r12d
0x18003ec2d  mov     ebx, eax
  ... truncated ...
```
