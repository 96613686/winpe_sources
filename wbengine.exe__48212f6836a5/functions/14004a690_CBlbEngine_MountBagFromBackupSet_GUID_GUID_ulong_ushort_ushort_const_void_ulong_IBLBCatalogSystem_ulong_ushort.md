# CBlbEngine::MountBagFromBackupSet(_GUID,_GUID,ulong,ushort *,ushort const *,void *,ulong,IBLBCatalogSystem *,ulong *,ushort *,int)

- ea: `0x14004a690`
- end: `0x14004b40f`
- name: `?MountBagFromBackupSet@CBlbEngine@@UEAAJU_GUID@@0KPEAGPEBGPEAXKPEAUIBLBCatalogSystem@@PEAK1H@Z`
- size: `3455`
- prototype: `__int64 __fastcall(struct IBLBCatalogSystem **this, struct _GUID *, struct _GUID *, unsigned int, unsigned __int16 *, OLECHAR *, void *, unsigned int, struct IBLBCatalogSystem *, unsigned int *, unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `36`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x1400549a0`

## callees

- `0x1400063b4`
- `0x140006ca8`
- `0x140007ad3`
- `0x14000ae38`
- `0x14000bb24`
- `0x14000bb4c`
- `0x14000be04`
- `0x140014200`
- `0x140014260`
- `0x1400142d8`
- `0x140014448`
- `0x14003e280`
- `0x14003ee24`
- `0x140043ec4`
- `0x1400472a4`
- `0x14004a690`
- `0x1400507a4`
- `0x14008ca7c`
- `0x14009257c`
- `0x140098c04`
- `0x1400d6ee8`
- `0x1400ef92c`
- `0x1400f007c`
- `0x1400f07dc`
- `0x1400f4400`
- `0x140102128`
- `0x140104148`
- `0x140104e8c`
- `0x140106e60`
- `0x14010a688`
- `0x14011de34`
- `0x14011e5dc`
- `0x14011e818`
- `0x140134cc6`
- `0x140134d20`
- `0x140137010`

## import_xrefs

- `KERNEL32!GetTickCount` at `0x14004ac71`
- `KERNEL32!GetTickCount` at `0x14004ae9d`
- `KERNEL32!GetTickCount` at `0x14004ac71`
- `KERNEL32!GetTickCount` at `0x14004ae9d`
- `KERNEL32!EnterCriticalSection` at `0x14004a895`
- `KERNEL32!EnterCriticalSection` at `0x14004afca`
- `KERNEL32!EnterCriticalSection` at `0x14004a895`
- `KERNEL32!EnterCriticalSection` at `0x14004afca`
- `ole32!CoTaskMemFree` at `0x14004b2b6`
- `ole32!CoTaskMemFree` at `0x14004b2c5`
- `ole32!CoTaskMemFree` at `0x14004b2d4`
- `ole32!CoTaskMemFree` at `0x14004b2e3`
- `ole32!CoTaskMemFree` at `0x14004b2f1`
- `ole32!CoTaskMemFree` at `0x14004b303`
- `ole32!CoTaskMemFree` at `0x14004b321`
- `ole32!CoTaskMemFree` at `0x14004b2b6`
- `ole32!CoTaskMemFree` at `0x14004b2c5`
- `ole32!CoTaskMemFree` at `0x14004b2d4`
- `ole32!CoTaskMemFree` at `0x14004b2e3`
- `ole32!CoTaskMemFree` at `0x14004b2f1`
- `ole32!CoTaskMemFree` at `0x14004b303`
- `ole32!CoTaskMemFree` at `0x14004b321`
- `OLEAUT32!__imp_SysFreeString` at `0x14004aa15`
- `OLEAUT32!__imp_SysFreeString` at `0x14004aa25`
- `OLEAUT32!__imp_SysFreeString` at `0x14004aaab`
- `OLEAUT32!__imp_SysFreeString` at `0x14004aabe`
- `OLEAUT32!__imp_SysFreeString` at `0x14004b154`
- `OLEAUT32!__imp_SysFreeString` at `0x14004b164`
- `OLEAUT32!__imp_SysFreeString` at `0x14004aa15`
- `OLEAUT32!__imp_SysFreeString` at `0x14004aa25`
- `OLEAUT32!__imp_SysFreeString` at `0x14004aaab`
- `OLEAUT32!__imp_SysFreeString` at `0x14004aabe`
- `OLEAUT32!__imp_SysFreeString` at `0x14004b154`
- `OLEAUT32!__imp_SysFreeString` at `0x14004b164`
- `RPCRT4!UuidToStringW` at `0x14004ae7d`
- `RPCRT4!UuidToStringW` at `0x14004ae7d`
- `RPCRT4!RpcStringFreeW` at `0x14004b336`
- `RPCRT4!RpcStringFreeW` at `0x14004b336`

## string_xrefs

- `0x14004aceb`: `base\stor\blb\engine\service\engine.cpp`
- `0x14004afe4`: `base\stor\blb\engine\service\engine.cpp`
- `0x14004acdf`: `wszVhdExtension != NULL`

## pseudocode

```c
__int64 __fastcall CBlbEngine::MountBagFromBackupSet(
        struct IBLBCatalogSystem **this,
        struct _GUID *a2,
        struct _GUID *a3,
        unsigned int a4,
        unsigned __int16 *a5,
        OLECHAR *a6,
        void *a7,
        unsigned int a8,
        struct IBLBCatalogSystem *a9,
        unsigned int *a10,
        unsigned __int16 *a11,
        int a12)
{
  struct IBLBCatalogSystem *v13; // r14
  char v14; // si
  PVOID *v15; // rbx
  int UserExposedVhdContext; // edi
  struct _GUID *v17; // r13
  unsigned __int16 *v18; // r14
  char v19; // r15
  CBlbEngine *v20; // r12
  struct _GUID *v21; // rbx
  struct _GUID v22; // xmm1
  BSTR v23; // r14
  BSTR v24; // r15
  __int64 v25; // rbx
  __int64 v26; // rbx
  _QWORD *v27; // rax
  struct _GUID *v28; // rbx
  __int64 v29; // r9
  __int64 (__fastcall *v30)(struct IBLBCatalogSystem *, struct _GUID *, _BYTE *, __int64); // rax
  unsigned int v31; // edx
  __int64 v32; // r14
  __int64 v33; // rax
  unsigned int v34; // ebx
  unsigned __int16 *v35; // rbx
  __int64 v36; // rdx
  __int64 v37; // r8
  const WCHAR *v38; // rbx
  _QWORD *v39; // rcx
  int v40; // edx
  int v41; // ebx
  char v42; // bl
  struct _GUID v43; // xmm1
  int v44; // eax
  struct _GUID v45; // xmm1
  __int64 v46; // rax
  __int64 v47; // rbx
  _QWORD *v48; // rax
  PVOID *v49; // rcx
  char v51; // [rsp+40h] [rbp-C0h]
  unsigned __int16 *v53; // [rsp+50h] [rbp-B0h] BYREF
  void *Buf1; // [rsp+58h] [rbp-A8h]
  unsigned __int8 v55; // [rsp+60h] [rbp-A0h] BYREF
  char v56; // [rsp+61h] [rbp-9Fh]
  char v57; // [rsp+62h] [rbp-9Eh]
  char v58; // [rsp+63h] [rbp-9Dh]
  unsigned __int8 v59[4]; // [rsp+64h] [rbp-9Ch] BYREF
  DWORD TickCount; // [rsp+68h] [rbp-98h]
  BSTR v61; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int16 *v62; // [rsp+78h] [rbp-88h] BYREF
  int v63; // [rsp+80h] [rbp-80h]
  RPC_WSTR StringUuid; // [rsp+88h] [rbp-78h] BYREF
  BSTR bstrString; // [rsp+90h] [rbp-70h] BYREF
  BSTR v66; // [rsp+98h] [rbp-68h] BYREF
  struct _GUID *v67; // [rsp+A0h] [rbp-60h]
  unsigned __int16 *v68; // [rsp+A8h] [rbp-58h] BYREF
  PCWSTR v69; // [rsp+B0h] [rbp-50h] BYREF
  unsigned __int16 *v70; // [rsp+B8h] [rbp-48h] BYREF
  struct _GUID v71; // [rsp+C0h] [rbp-40h] BYREF
  _QWORD v72[2]; // [rsp+D0h] [rbp-30h] BYREF
  int v73; // [rsp+E0h] [rbp-20h]
  BSTR v74[2]; // [rsp+F0h] [rbp-10h] BYREF
  char v75; // [rsp+100h] [rbp+0h]
  LPVOID pv; // [rsp+110h] [rbp+10h] BYREF
  unsigned __int16 *v77; // [rsp+118h] [rbp+18h] BYREF
  BSTR v78[2]; // [rsp+120h] [rbp+20h] BYREF
  BSTR v79[2]; // [rsp+130h] [rbp+30h] BYREF
  _QWORD v80[2]; // [rsp+140h] [rbp+40h] BYREF
  char v81; // [rsp+150h] [rbp+50h]
  _BYTE v82[64]; // [rsp+160h] [rbp+60h] BYREF
  unsigned int v83; // [rsp+1A0h] [rbp+A0h]
  __int64 v84; // [rsp+1A8h] [rbp+A8h]
  unsigned int v85; // [rsp+220h] [rbp+120h]
  unsigned int v86; // [rsp+224h] [rbp+124h]

  v13 = a9;
  v78[0] = a6;
  v14 = 0;
  LODWORD(v66) = 0;
  Buf1 = a3;
  v67 = a2;
  v79[0] = (BSTR)a10;
  bstrString = a11;
  v15 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 306, &WPP_9870b93072233f1de7a88e8cd32d2237_Traceguids);
    v15 = (PVOID *)WPP_GLOBAL_Control;
  }
  v81 = 0;
  v80[0] = &CBlbLock::`vftable';
  v51 = 0;
  v80[1] = &g_csGlobal;
  memset_0(v82, 0, 0xD0u);
  v72[0] = a7;
  pv = 0;
  v63 = a4 & 2;
  v77 = 0;
  v68 = 0;
  v69 = 0;
  v53 = 0;
  v62 = 0;
  v57 = 0;
  v58 = 0;
  TickCount = 0;
  v72[1] = -1;
  v73 = 0;
  v70 = 0;
  v59[0] = 0;
  v56 = 0;
  v61 = 0;
  v55 = 0;
  StringUuid = 0;
  if ( v15 != &WPP_GLOBAL_Control && (*((_BYTE *)v15 + 28) & 1) != 0 && *((_BYTE *)v15 + 25) >= 4u )
    WPP_SF_d(v15[2], 307, &WPP_9870b93072233f1de7a88e8cd32d2237_Traceguids);
  if ( a4 >= 8 )
  {
    UserExposedVhdContext = -2147024809;
    goto LABEL_11;
  }
  if ( !a11 && a8 || !a10 )
  {
    UserExposedVhdContext = -2147467261;
    goto LABEL_203;
  }
  if ( !memcmp_0(Buf1, &GUID_NULL, 0x10u) )
  {
    UserExposedVhdContext = -2147024809;
    goto LABEL_203;
  }
  if ( a8 < 0x104 )
  {
    *a10 = 0;
    UserExposedVhdContext = -2147024774;
    goto LABEL_203;
  }
  memset_0(a11, 0, 2LL * a8);
  EnterCriticalSection(&g_csGlobal);
  v81 = 1;
  if ( !this[2] )
  {
    v17 = (struct _GUID *)Buf1;
    UserExposedVhdContext = -2139619318;
    v18 = v53;
    v14 = 0;
    v19 = 0;
    v20 = (CBlbEngine *)this;
    goto LABEL_110;
  }
  if ( !a9 )
    v13 = this[2];
  LODWORD(v66) = a4 & 4;
  if ( (a4 & 4) != 0 )
  {
    v21 = v67;
    v22 = *v67;
    *(_OWORD *)v74 = *(_OWORD *)Buf1;
    v71 = v22;
    UserExposedVhdContext = CBlbEngine::GetUserExposedVhdContext(
                              (CBlbEngine *)this,
                              &v71,
                              (struct _GUID *)v74,
                              &v55,
                              &v61);
    if ( UserExposedVhdContext < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 308, &WPP_9870b93072233f1de7a88e8cd32d2237_Traceguids);
      }
      goto LABEL_11;
    }
    if ( v55 )
    {
      v23 = v61;
      v24 = bstrString;
      UserExposedVhdContext = StringCchCopyW(bstrString, a8, v61);
      if ( UserExposedVhdContext < 0 )
        goto LABEL_11;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
      {
        v17 = (struct _GUID *)Buf1;
      }
      else
      {
        v17 = (struct _GUID *)Buf1;
        v25 = *(_QWORD *)ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&v66, v21);
        ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&bstrString, (const struct _GUID *)Buf1);
        WPP_SF_SSS(*((_QWORD *)WPP_GLOBAL_Control + 2), v25, (__int64)v23);
        v14 = 3;
      }
      if ( (v14 & 2) != 0 )
      {
        v14 &= ~2u;
        SysFreeString(bstrString);
      }
      if ( (v14 & 1) != 0 )
        SysFreeString(v66);
      v56 = 1;
LABEL_131:
      v46 = -1;
      do
        ++v46;
      while ( v24[v46] );
      *(_DWORD *)v79[0] = v46 + 1;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 319, &WPP_9870b93072233f1de7a88e8cd32d2237_Traceguids, v24);
      }
      v19 = v51;
      v18 = v53;
      v14 = v51;
      goto LABEL_109;
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      v26 = *(_QWORD *)ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)v74, v21);
      v27 = (_QWORD *)ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&v61, (const struct _GUID *)Buf1);
      WPP_SF_SS(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        310,
        (unsigned int)&WPP_9870b93072233f1de7a88e8cd32d2237_Traceguids,
        *v27,
        v26);
      v14 = 12;
    }
    if ( (v14 & 8) != 0 )
    {
      v14 &= ~8u;
      SysFreeString(v61);
    }
    if ( (v14 & 4) != 0 )
    {
      v14 &= ~4u;
      SysFreeString(v74[0]);
    }
  }
  CBlbLock::ReleaseLock((CBlbLock *)v80);
  memset_0(v82, 0, 0xD0u);
  v28 = v67;
  LOBYTE(v29) = 1;
  v30 = *(__int64 (__fastcall **)(struct IBLBCatalogSystem *, struct _GUID *, _BYTE *, __int64))(*(_QWORD *)v13 + 88LL);
  v71 = *v67;
  UserExposedVhdContext = v30(v13, &v71, v82, v29);
  if ( UserExposedVhdContext < 0 )
  {
    v14 = 0;
    goto LABEL_11;
  }
  v31 = 0;
  v51 = 1;
  while ( 1 )
  {
    if ( v31 >= v83 )
      goto LABEL_138;
    v32 = v84 + 120LL * v31;
    v33 = *(_QWORD *)v32 - *(_QWORD *)Buf1;
    if ( *(_QWORD *)v32 == *(_QWORD *)Buf1 )
      v33 = *(_QWORD *)(v32 + 8) - *((_QWORD *)Buf1 + 1);
    if ( !v33 )
      break;
    ++v31;
  }
  if ( !v32 )
  {
LABEL_138:
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      v17 = (struct _GUID *)Buf1;
    }
    else
    {
      v17 = (struct _GUID *)Buf1;
      v14 |= 0x30u;
      v47 = *(_QWORD *)ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)v78, v28);
      v48 = (_QWORD *)ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)v79, (const struct _GUID *)Buf1);
      WPP_SF_SS(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        311,
        (unsigned int)&WPP_9870b93072233f1de7a88e8cd32d2237_Traceguids,
        *v48,
        v47);
    }
    if ( (v14 & 0x20) != 0 )
    {
      v14 &= ~0x20u;
      SysFreeString(v79[0]);
    }
    if ( (v14 & 0x10) != 0 )
      SysFreeString(v78[0]);
    v14 = 0;
    UserExposedVhdContext = -2139619263;
    goto LABEL_12;
  }
  v14 = 0;
  if ( a12 )
  {
    UserExposedVhdContext = CBlbImpersonationHelper::CacheClientTokenIfNeeded((CBlbImpersonationHelper *)v72);
    if ( UserExposedVhdContext < 0 )
      goto LABEL_11;
  }
  LODWORD(v61) = 0;
  UserExposedVhdContext = BlbQueryTargetMediaType(
                            a5,
                            (struct CBlbImpersonationHelper *)v72,
                            (enum _BLB_MEDIA_TYPE *)&v61);
  if ( UserExposedVhdContext < 0 )
    goto LABEL_11;
  v34 = (unsigned int)v61;
  if ( !(_DWORD)v61 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 312, &WPP_9870b93072233f1de7a88e8cd32d2237_Traceguids);
    }
    UserExposedVhdContext = -2139619316;
    goto LABEL_11;
  }
  if ( (_DWORD)v61 != 4 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 313, &WPP_9870b93072233f1de7a88e8cd32d2237_Traceguids);
    }
    CBlbImpersonationHelper::DiscardCachedCOMClientToken((CBlbImpersonationHelper *)v72);
  }
  if ( (BlbutilGetBackupFeatures(v34) & 0x40) == 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 314, &WPP_9870b93072233f1de7a88e8cd32d2237_Traceguids);
    }
    UserExposedVhdContext = -2139619250;
    goto LABEL_11;
  }
  TickCount = GetTickCount();
  UserExposedVhdContext = BlbGetTargetPathForBackupSet(
                            a5,
                            1u,
                            (struct _BLBCAT_BACKUP_SET_INFO *)v82,
                            (struct CBlbImpersonationHelper *)v72,
                            (unsigned __int16 **)&pv,
                            &v77,
                            &v68);
  if ( UserExposedVhdContext < 0
    || (UserExposedVhdContext = BlbGetAppropriateVhdExtension(v85, v86, &v70, v59), UserExposedVhdContext < 0) )
  {
LABEL_11:
    v17 = (struct _GUID *)Buf1;
LABEL_12:
    v18 = v53;
    v19 = v51;
LABEL_109:
    v20 = (CBlbEngine *)this;
    goto LABEL_110;
  }
  v35 = v70;
  if ( !v70 )
    BlbAssert("base\\stor\\blb\\engine\\service\\engine.cpp", 0x1941u, "wszVhdExtension != NULL");
  v17 = (struct _GUID *)Buf1;
  UserExposedVhdContext = BlbAppendBagFile(v68, (UUID *)Buf1, 0, v35, (unsigned __int16 **)&v69);
  if ( UserExposedVhdContext < 0 )
    goto LABEL_12;
  UserExposedVhdContext = CBlbImpersonationHelper::ImpersonateCaller((CBlbImpersonationHelper *)v72, 0);
  if ( UserExposedVhdContext < 0 )
    goto LABEL_12;
  v38 = v69;
  LOBYTE(v37) = 1;
  UserExposedVhdContext = BlbVerifyFileNotCompressedOrEncrypted(v69, v36, v37);
  if ( UserExposedVhdContext < 0 )
  {
    v39 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_12;
    }
    v40 = 315;
LABEL_91:
    WPP_SF_Sd(
      v39[2],
      v40,
      (unsigned int)&WPP_9870b93072233f1de7a88e8cd32d2237_Traceguids,
      (_DWORD)v38,
      UserExposedVhdContext);
    goto LABEL_12;
  }
  CBlbImpersonationHelper::Revert((CBlbImpersonationHelper *)v72);
  UserExposedVhdContext = CBlbVhdHelper::MountVolume(
                            (struct CBlbImpersonationHelper *)v72,
                            v38,
                            (2 * (a4 & 1)) | 4,
                            v78[0],
                            *(_DWORD *)(v32 + 64),
                            &v62);
  if ( UserExposedVhdContext < 0 )
  {
    v39 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_12;
    }
    v40 = 316;
    goto LABEL_91;
  }
  v14 = 1;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_SS(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      317,
      (unsigned int)&WPP_9870b93072233f1de7a88e8cd32d2237_Traceguids,
      (_DWORD)v38,
      (__int64)v62);
  }
  v41 = v63;
  if ( v63 )
  {
    if ( !*((_DWORD *)this + 9) )
    {
      UserExposedVhdContext = BlbEnableNetworkShare();
      if ( UserExposedVhdContext < 0 )
      {
LABEL_107:
        v18 = v53;
LABEL_108:
        v19 = 1;
        goto LABEL_109;
      }
      v57 = 1;
    }
    if ( UuidToStringW((const UUID *)Buf1, &StringUuid) )
    {
      UserExposedVhdContext = -2147024882;
      goto LABEL_107;
    }
    v44 = BlbCreateReparsePointUnderNetworkShare(v62, StringUuid, &v53);
    v18 = v53;
    UserExposedVhdContext = v44;
    if ( v44 < 0 )
      goto LABEL_108;
    v24 = bstrString;
    v58 = 1;
    UserExposedVhdContext = StringCchCopyW(bstrString, a8, v53);
    if ( UserExposedVhdContext < 0 )
      goto LABEL_108;
    v20 = (CBlbEngine *)this;
    ++*((_DWORD *)this + 9);
  }
  else
  {
    v24 = bstrString;
    v18 = v53;
    UserExposedVhdContext = StringCchCopyW(bstrString, a8, v62);
    v20 = (CBlbEngine *)this;
    if ( UserExposedVhdContext < 0 )
      goto LABEL_129;
  }
  if ( !(_DWORD)v66 )
    goto LABEL_131;
  v74[0] = (BSTR)&CBlbLock::`vftable';
  v74[1] = (BSTR)&g_csGlobal;
  EnterCriticalSection(&g_csGlobal);
  v75 = 1;
  if ( !v41 )
    BlbAssert("base\\stor\\blb\\engine\\service\\engine.cpp", 0x19A6u, "bNeedNetworkShare");
  v45 = *v67;
  v71 = *v17;
  *(struct _GUID *)v78 = v45;
  UserExposedVhdContext = CBlbEngine::AddUserExposedVhdContext(v20, (struct _GUID *)v78, &v71, v18);
  if ( UserExposedVhdContext >= 0 )
  {
    CBlbLock::ReleaseLock((CBlbLock *)v74);
    CBlbLock::~CBlbLock((CBlbLock *)v74);
    goto LABEL_131;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 318, &WPP_9870b93072233f1de7a88e8cd32d2237_Traceguids);
  }
  CBlbLock::~CBlbLock((CBlbLock *)v74);
LABEL_129:
  v19 = 1;
LABEL_110:
  v42 = GetTickCount();
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 320, &WPP_9870b93072233f1de7a88e8cd32d2237_Traceguids);
  }
  if ( !v56 )
  {
    v43 = *v67;
    v71 = *v17;
    *(struct _GUID *)v79 = v43;
    PublishMountedBagEvent((struct _GUID *)v79, &v71, v63 != 0, UserExposedVhdContext, v42 - TickCount);
  }
  if ( UserExposedVhdContext < 0 )
  {
    if ( v57
      && (int)BlbDisableNetworkShare() < 0
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 321, &WPP_9870b93072233f1de7a88e8cd32d2237_Traceguids);
    }
    if ( v58
      && (int)BlbutilDeleteFile(v18, 0, 0) < 0
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 322, &WPP_9870b93072233f1de7a88e8cd32d2237_Traceguids);
    }
    if ( v14 )
    {
      if ( (*(int (__fastcall **)(CBlbEngine *, unsigned __int16 *))(*(_QWORD *)v20 + 360LL))(v20, v62) >= 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 324, &WPP_9870b93072233f1de7a88e8cd32d2237_Traceguids);
        }
      }
      else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
             && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
             && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 323, &WPP_9870b93072233f1de7a88e8cd32d2237_Traceguids);
      }
    }
  }
  CBlbImpersonationHelper::Revert((CBlbImpersonationHelper *)v72);
  if ( pv )
    CoTaskMemFree(pv);
  if ( v77 )
    CoTaskMemFree(v77);
  if ( v68 )
    CoTaskMemFree(v68);
  if ( v69 )
    CoTaskMemFree((LPVOID)v69);
  if ( v18 )
    CoTaskMemFree(v18);
  if ( v70 )
    CoTaskMemFree(v70);
  if ( v19 )
    FreeBackupSetContents((struct _BLBCAT_BACKUP_SET_INFO *)v82);
  if ( v62 )
  {
    CoTaskMemFree(v62);
    v62 = 0;
  }
  if ( StringUuid )
  {
    RpcStringFreeW(&StringUuid);
    StringUuid = 0;
  }
  v49 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 325, &WPP_9870b93072233f1de7a88e8cd32d2237_Traceguids);
      v49 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v49 != &WPP_GLOBAL_Control && (*((_BYTE *)v49 + 28) & 1) != 0 && *((_BYTE *)v49 + 25) >= 4u )
    {
      WPP_SF_(v49[2], 326, &WPP_9870b93072233f1de7a88e8cd32d2237_Traceguids);
      v49 = (PVOID *)WPP_GLOBAL_Control;
    }
  }
  if ( UserExposedVhdContext < 0
    && v49 != &WPP_GLOBAL_Control
    && (*((_BYTE *)v49 + 28) & 1) != 0
    && *((_BYTE *)v49 + 25) >= 2u )
  {
    WPP_SF_d(v49[2], 327, &WPP_9870b93072233f1de7a88e8cd32d2237_Traceguids);
  }
LABEL_203:
  CBlbImpersonationHelper::~CBlbImpersonationHelper((CBlbImpersonationHelper *)v72);
  CBlbLock::~CBlbLock((CBlbLock *)v80);
  return (unsigned int)UserExposedVhdContext;
}

```

## disassembly

```asm
0x14004a690  push    rbp
0x14004a692  push    rbx
0x14004a693  push    rsi
0x14004a694  push    rdi
0x14004a695  push    r12
0x14004a697  push    r13
0x14004a699  push    r14
0x14004a69b  push    r15
0x14004a69d  lea     rbp, [rsp-148h]
0x14004a6a5  sub     rsp, 248h
0x14004a6ac  mov     rax, cs:__security_cookie
0x14004a6b3  xor     rax, rsp
0x14004a6b6  mov     [rbp+180h+var_50], rax
0x14004a6bd  mov     rax, [rbp+180h+arg_28]
0x14004a6c4  mov     r15d, r9d
0x14004a6c7  mov     r12, [rbp+180h+arg_48]
0x14004a6ce  mov     rdi, [rbp+180h+arg_50]
0x14004a6d5  mov     r13, [rbp+180h+arg_20]
0x14004a6dc  mov     r14, [rbp+180h+arg_40]
0x14004a6e3  mov     [rbp+180h+var_160], rax
0x14004a6e7  xor     eax, eax
0x14004a6e9  mov     esi, eax
0x14004a6eb  mov     dword ptr [rbp+180h+var_1E8], eax
0x14004a6ee  mov     [rsp+280h+Buf1], r8
0x14004a6f3  mov     [rbp+180h+var_1E0], rdx
0x14004a6f7  mov     [rsp+280h+var_238], rcx
0x14004a6fc  mov     [rbp+180h+var_150], r12
0x14004a700  mov     [rbp+180h+bstrString], rdi
0x14004a704  mov     rbx, cs:WPP_GLOBAL_Control
0x14004a70b  lea     rcx, WPP_GLOBAL_Control
0x14004a712  cmp     rbx, rcx
0x14004a715  jz      short loc_14004A741
0x14004a717  test    byte ptr [rbx+1Ch], 1
0x14004a71b  jz      short loc_14004A741
0x14004a71d  cmp     byte ptr [rbx+19h], 4
0x14004a721  jb      short loc_14004A741
0x14004a723  mov     rcx, [rbx+10h]
0x14004a727  lea     r8, WPP_9870b93072233f1de7a88e8cd32d2237_Traceguids
0x14004a72e  mov     edx, 132h
0x14004a733  call    WPP_SF_
0x14004a738  mov     rbx, cs:WPP_GLOBAL_Control
0x14004a73f  xor     eax, eax
0x14004a741  lea     rcx, ??_7CBlbLock@@6B@; const CBlbLock::`vftable'
0x14004a748  mov     [rbp+180h+var_130], al
0x14004a74b  mov     [rbp+180h+var_140], rcx
0x14004a74f  xor     edx, edx; Val
0x14004a751  lea     rcx, ?g_csGlobal@@3U_RTL_CRITICAL_SECTION@@A; _RTL_CRITICAL_SECTION g_csGlobal
0x14004a758  mov     [rsp+280h+var_240], al
0x14004a75c  mov     [rbp+180h+var_138], rcx
0x14004a760  mov     r8d, 0D0h; Size
0x14004a766  lea     rcx, [rbp+180h+var_120]; void *
0x14004a76a  call    memset_0
0x14004a76f  mov     rax, [rbp+180h+arg_30]
0x14004a776  xor     ecx, ecx
0x14004a778  mov     [rbp+180h+var_1B0], rax
0x14004a77c  mov     eax, r15d
0x14004a77f  and     eax, 2
0x14004a782  mov     [rbp+180h+pv], rcx
0x14004a786  mov     [rbp+180h+var_200], eax
0x14004a789  mov     [rbp+180h+var_168], rcx
0x14004a78d  mov     [rbp+180h+var_1D8], rcx
0x14004a791  mov     [rbp+180h+var_1D0], rcx
0x14004a795  mov     [rsp+280h+var_230], rcx
0x14004a79a  mov     [rsp+280h+var_208], rcx
0x14004a79f  mov     [rsp+280h+var_21E], cl
0x14004a7a3  mov     [rsp+280h+var_23F], cl
0x14004a7a7  mov     [rsp+280h+var_21D], cl
0x14004a7ab  mov     [rsp+280h+var_218], ecx
0x14004a7af  mov     [rbp+180h+var_1A8], 0FFFFFFFFFFFFFFFFh
0x14004a7b7  mov     [rbp+180h+var_1A0], ecx
0x14004a7ba  mov     [rbp+180h+var_1C8], rcx
0x14004a7be  mov     [rsp+280h+var_21C], cl
0x14004a7c2  mov     [rsp+280h+var_21F], cl
0x14004a7c6  mov     [rsp+280h+var_210], rcx
0x14004a7cb  mov     [rsp+280h+var_220], cl
0x14004a7cf  mov     [rbp+180h+StringUuid], rcx
0x14004a7d3  lea     rax, WPP_GLOBAL_Control
0x14004a7da  cmp     rbx, rax
0x14004a7dd  jz      short loc_14004A803
0x14004a7df  test    byte ptr [rbx+1Ch], 1
0x14004a7e3  jz      short loc_14004A803
0x14004a7e5  cmp     byte ptr [rbx+19h], 4
0x14004a7e9  jb      short loc_14004A803
0x14004a7eb  mov     rcx, [rbx+10h]
0x14004a7ef  lea     r8, WPP_9870b93072233f1de7a88e8cd32d2237_Traceguids
0x14004a7f6  mov     edx, 133h
0x14004a7fb  mov     r9d, r15d
0x14004a7fe  call    WPP_SF_d
0x14004a803  cmp     r15d, 8
0x14004a807  jb      short loc_14004A822
0x14004a809  mov     edi, 80070057h
0x14004a80e  mov     r13, [rsp+280h+Buf1]
0x14004a813  mov     r14, [rsp+280h+var_230]
0x14004a818  mov     r15b, [rsp+280h+var_240]
0x14004a81d  jmp     loc_14004AE98
0x14004a822  mov     ebx, [rbp+180h+arg_38]
0x14004a828  test    rdi, rdi
0x14004a82b  jnz     short loc_14004A831
0x14004a82d  test    ebx, ebx
0x14004a82f  jnz     short loc_14004A836
0x14004a831  test    r12, r12
0x14004a834  jnz     short loc_14004A840
0x14004a836  mov     edi, 80004003h
0x14004a83b  jmp     loc_14004B3D8
0x14004a840  mov     rcx, [rsp+280h+Buf1]; Buf1
0x14004a845  lea     rdx, GUID_NULL; Buf2
0x14004a84c  mov     r8d, 10h; Size
0x14004a852  call    memcmp_0
0x14004a857  xor     ecx, ecx
0x14004a859  test    eax, eax
0x14004a85b  jnz     short loc_14004A867
0x14004a85d  mov     edi, 80070057h
0x14004a862  jmp     loc_14004B3D8
0x14004a867  cmp     ebx, 104h
0x14004a86d  jnb     short loc_14004A87D
0x14004a86f  mov     [r12], ecx
0x14004a873  mov     edi, 8007007Ah
0x14004a878  jmp     loc_14004B3D8
0x14004a87d  lea     r8, [rbx+rbx]; Size
0x14004a881  xor     edx, edx; Val
0x14004a883  mov     rcx, rdi; void *
0x14004a886  mov     r12, rbx
0x14004a889  call    memset_0
0x14004a88e  lea     rcx, ?g_csGlobal@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x14004a895  call    cs:__imp_EnterCriticalSection
0x14004a89b  mov     rcx, [rsp+280h+var_238]; this
0x14004a8a0  xor     eax, eax
0x14004a8a2  mov     [rbp+180h+var_130], 1
0x14004a8a6  cmp     [rcx+10h], rax
0x14004a8aa  jnz     short loc_14004A8CB
0x14004a8ac  mov     r13, [rsp+280h+Buf1]
0x14004a8b1  mov     edi, 8078000Ah
0x14004a8b6  mov     r14, [rsp+280h+var_230]
0x14004a8bb  mov     sil, al
0x14004a8be  mov     r15b, [rsp+280h+var_240]
0x14004a8c3  mov     r12, rcx
0x14004a8c6  jmp     loc_14004AE9D
0x14004a8cb  test    r14, r14
0x14004a8ce  mov     eax, r15d
0x14004a8d1  cmovz   r14, [rcx+10h]
0x14004a8d6  and     eax, 4
0x14004a8d9  mov     dword ptr [rbp+180h+var_1E8], eax
0x14004a8dc  jz      loc_14004AAC4
0x14004a8e2  mov     rax, [rsp+280h+Buf1]
0x14004a8e7  lea     r9, [rsp+280h+var_220]; unsigned __int8 *
0x14004a8ec  mov     rbx, [rbp+180h+var_1E0]
0x14004a8f0  lea     r8, [rbp+180h+var_190]; struct _GUID
0x14004a8f4  lea     rdx, [rbp+180h+var_1C0]; struct _GUID
0x14004a8f8  movups  xmm0, xmmword ptr [rax]
0x14004a8fb  lea     rax, [rsp+280h+var_210]
0x14004a900  movups  xmm1, xmmword ptr [rbx]
0x14004a903  mov     [rsp+280h+var_260], rax; unsigned __int16 **
0x14004a908  movdqu  xmmword ptr [rbp+180h+var_190], xmm0
0x14004a90d  movdqu  xmmword ptr [rbp+180h+var_1C0.Data1], xmm1
0x14004a912  call    ?GetUserExposedVhdContext@CBlbEngine@@QEAAJU_GUID@@0PEAEPEAPEAG@Z; CBlbEngine::GetUserExposedVhdContext(_GUID,_GUID,uchar *,ushort * *)
0x14004a917  xor     r11d, r11d
0x14004a91a  mov     edi, eax
0x14004a91c  test    eax, eax
0x14004a91e  jns     short loc_14004A968
0x14004a920  mov     rcx, cs:WPP_GLOBAL_Control
0x14004a927  lea     rax, WPP_GLOBAL_Control
0x14004a92e  cmp     rcx, rax
0x14004a931  jz      loc_14004A80E
0x14004a937  test    byte ptr [rcx+1Ch], 1
0x14004a93b  jz      loc_14004A80E
0x14004a941  cmp     byte ptr [rcx+19h], 2
0x14004a945  jb      loc_14004A80E
0x14004a94b  mov     rcx, [rcx+10h]
0x14004a94f  lea     r8, WPP_9870b93072233f1de7a88e8cd32d2237_Traceguids
0x14004a956  mov     edx, 134h
0x14004a95b  mov     r9d, edi
0x14004a95e  call    WPP_SF_d
0x14004a963  jmp     loc_14004A80E
0x14004a968  cmp     [rsp+280h+var_220], r11b
0x14004a96d  jz      loc_14004AA37
0x14004a973  mov     r14, [rsp+280h+var_210]
0x14004a978  mov     rdx, r12; unsigned __int64
0x14004a97b  mov     r15, [rbp+180h+bstrString]
0x14004a97f  mov     r8, r14; unsigned __int16 *
0x14004a982  mov     rcx, r15; unsigned __int16 *
0x14004a985  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x14004a98a  mov     edi, eax
0x14004a98c  test    eax, eax
0x14004a98e  js      loc_14004A80E
0x14004a994  mov     rax, cs:WPP_GLOBAL_Control
0x14004a99b  lea     r12, WPP_GLOBAL_Control
0x14004a9a2  cmp     rax, r12
0x14004a9a5  jz      short loc_14004AA03
0x14004a9a7  test    byte ptr [rax+1Ch], 1
0x14004a9ab  jz      short loc_14004AA03
0x14004a9ad  cmp     byte ptr [rax+19h], 4
0x14004a9b1  jb      short loc_14004AA03
0x14004a9b3  mov     rdx, rbx; struct _GUID *
0x14004a9b6  lea     rcx, [rbp+180h+var_1E8]; this
0x14004a9ba  call    ??0CComBSTR@ATL@@QEAA@AEBU_GUID@@@Z; ATL::CComBSTR::CComBSTR(_GUID const &)
0x14004a9bf  mov     r13, [rsp+280h+Buf1]
0x14004a9c4  lea     rcx, [rbp+180h+bstrString]; this
0x14004a9c8  mov     rdx, r13; struct _GUID *
0x14004a9cb  mov     rbx, [rax]
0x14004a9ce  call    ??0CComBSTR@ATL@@QEAA@AEBU_GUID@@@Z; ATL::CComBSTR::CComBSTR(_GUID const &)
0x14004a9d3  mov     rcx, cs:WPP_GLOBAL_Control
0x14004a9da  lea     r8, WPP_9870b93072233f1de7a88e8cd32d2237_Traceguids
0x14004a9e1  mov     edx, 135h
0x14004a9e6  mov     [rsp+280h+var_258], r14; __int64
0x14004a9eb  mov     [rsp+280h+var_260], rbx; __int64
0x14004a9f0  mov     r9, [rax]
0x14004a9f3  mov     rcx, [rcx+10h]; LoggerHandle
0x14004a9f7  call    WPP_SF_SSS
0x14004a9fc  mov     esi, 3
0x14004aa01  jmp     short loc_14004AA08
0x14004aa03  mov     r13, [rsp+280h+Buf1]
0x14004aa08  test    sil, 2
0x14004aa0c  jz      short loc_14004AA1B
0x14004aa0e  mov     rcx, [rbp+180h+bstrString]; bstrString
0x14004aa12  and     esi, 0FFFFFFFDh
0x14004aa15  call    cs:__imp_SysFreeString
0x14004aa1b  test    sil, 1
0x14004aa1f  jz      short loc_14004AA2B
0x14004aa21  mov     rcx, [rbp+180h+var_1E8]; bstrString
0x14004aa25  call    cs:__imp_SysFreeString
0x14004aa2b  mov     [rsp+280h+var_21F], 1
0x14004aa30  xor     ecx, ecx
0x14004aa32  jmp     loc_14004B082
0x14004aa37  mov     rax, cs:WPP_GLOBAL_Control
0x14004aa3e  lea     rcx, WPP_GLOBAL_Control
0x14004aa45  cmp     rax, rcx
0x14004aa48  jz      short loc_14004AA9D
0x14004aa4a  test    byte ptr [rax+1Ch], 1
0x14004aa4e  jz      short loc_14004AA9D
0x14004aa50  cmp     byte ptr [rax+19h], 4
0x14004aa54  jb      short loc_14004AA9D
0x14004aa56  mov     rdx, rbx; struct _GUID *
0x14004aa59  lea     rcx, [rbp+180h+var_190]; this
0x14004aa5d  call    ??0CComBSTR@ATL@@QEAA@AEBU_GUID@@@Z; ATL::CComBSTR::CComBSTR(_GUID const &)
0x14004aa62  mov     rdx, [rsp+280h+Buf1]; struct _GUID *
0x14004aa67  lea     rcx, [rsp+280h+var_210]; this
0x14004aa6c  mov     rbx, [rax]
0x14004aa6f  call    ??0CComBSTR@ATL@@QEAA@AEBU_GUID@@@Z; ATL::CComBSTR::CComBSTR(_GUID const &)
0x14004aa74  mov     rcx, cs:WPP_GLOBAL_Control
0x14004aa7b  lea     r8, WPP_9870b93072233f1de7a88e8cd32d2237_Traceguids
0x14004aa82  mov     edx, 136h
0x14004aa87  mov     [rsp+280h+var_260], rbx
0x14004aa8c  mov     r9, [rax]
0x14004aa8f  mov     rcx, [rcx+10h]
0x14004aa93  call    WPP_SF_SS
0x14004aa98  mov     esi, 0Ch
0x14004aa9d  test    sil, 8
0x14004aaa1  jz      short loc_14004AAB1
0x14004aaa3  mov     rcx, [rsp+280h+var_210]; bstrString
0x14004aaa8  and     esi, 0FFFFFFF7h
0x14004aaab  call    cs:__imp_SysFreeString
0x14004aab1  test    sil, 4
0x14004aab5  jz      short loc_14004AAC4
0x14004aab7  mov     rcx, [rbp+180h+var_190]; bstrString
0x14004aabb  and     esi, 0FFFFFFFBh
0x14004aabe  call    cs:__imp_SysFreeString
0x14004aac4  lea     rcx, [rbp+180h+var_140]; this
0x14004aac8  call    ?ReleaseLock@CBlbLock@@QEAAXXZ; CBlbLock::ReleaseLock(void)
0x14004aacd  xor     edx, edx; Val
0x14004aacf  lea     rcx, [rbp+180h+var_120]; void *
0x14004aad3  mov     r8d, 0D0h; Size
0x14004aad9  call    memset_0
0x14004aade  mov     rax, [r14]
0x14004aae1  lea     r8, [rbp+180h+var_120]
0x14004aae5  mov     rbx, [rbp+180h+var_1E0]
0x14004aae9  lea     rdx, [rbp+180h+var_1C0]
0x14004aaed  mov     r9b, 1
0x14004aaf0  mov     rcx, r14
0x14004aaf3  mov     rax, [rax+58h]
0x14004aaf7  movups  xmm0, xmmword ptr [rbx]
0x14004aafa  movdqu  xmmword ptr [rbp+180h+var_1C0.Data1], xmm0
0x14004aaff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004ab04  xor     r9d, r9d
0x14004ab07  mov     edi, eax
0x14004ab09  test    eax, eax
0x14004ab0b  js      loc_14004B179
0x14004ab11  mov     r8, [rbp+180h+var_D8]
0x14004ab18  mov     edx, r9d
0x14004ab1b  mov     [rsp+280h+var_240], 1
0x14004ab20  cmp     edx, [rbp+180h+var_E0]
0x14004ab26  jnb     loc_14004B0DA
0x14004ab2c  mov     rcx, [rsp+280h+Buf1]
0x14004ab31  mov     eax, edx
0x14004ab33  imul    r14, rax, 78h ; 'x'
0x14004ab37  add     r14, r8
0x14004ab3a  mov     rax, [r14]
0x14004ab3d  sub     rax, [rcx]
0x14004ab40  jnz     short loc_14004AB4A
0x14004ab42  mov     rax, [r14+8]
0x14004ab46  sub     rax, [rcx+8]
0x14004ab4a  test    rax, rax
0x14004ab4d  jz      short loc_14004AB53
0x14004ab4f  inc     edx
0x14004ab51  jmp     short loc_14004AB20
0x14004ab53  test    r14, r14
0x14004ab56  jz      loc_14004B0DA
0x14004ab5c  xor     esi, esi
0x14004ab5e  cmp     [rbp+180h+arg_58], esi
0x14004ab64  jz      short loc_14004AB79
0x14004ab66  lea     rcx, [rbp+180h+var_1B0]; this
  ... truncated ...
```
