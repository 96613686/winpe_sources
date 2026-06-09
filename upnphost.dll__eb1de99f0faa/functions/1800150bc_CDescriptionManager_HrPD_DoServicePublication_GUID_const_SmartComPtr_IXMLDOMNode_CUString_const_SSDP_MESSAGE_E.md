# CDescriptionManager::HrPD_DoServicePublication(_GUID const &,SmartComPtr<IXMLDOMNode> &,CUString const &,_SSDP_MESSAGE_EX *,SSDP_SERVICE_REGISTRATION_PARAMS *)

- ea: `0x1800150bc`
- end: `0x180015aa4`
- name: `?HrPD_DoServicePublication@CDescriptionManager@@AEAAJAEBU_GUID@@AEAV?$SmartComPtr@UIXMLDOMNode@@@@AEBVCUString@@PEAU_SSDP_MESSAGE_EX@@PEAUSSDP_SERVICE_REGISTRATION_PARAMS@@@Z`
- size: `2536`
- prototype: `__int64 __fastcall(int, int, int, int, struct _SSDP_MESSAGE_EX *, __int64)`
- caller_count: `1`
- callee_count: `22`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x1800144e4`

## callees

- `0x18000f260`
- `0x18000fdf4`
- `0x1800117bc`
- `0x1800117d0`
- `0x180013cb4`
- `0x1800150bc`
- `0x180015d90`
- `0x180016af4`
- `0x180018738`
- `0x180025330`
- `0x180030c30`
- `0x180037ef8`
- `0x180038324`
- `0x180038ce4`
- `0x180039a84`
- `0x18003a560`
- `0x180043124`
- `0x1800454d0`
- `0x180046540`
- `0x180049ed4`
- `0x18004aa5c`
- `0x180055010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800152aa`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180015343`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800154d1`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001552c`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800156fa`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001571d`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001578f`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800152aa`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180015343`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800154d1`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001552c`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800156fa`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001571d`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001578f`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18001526d`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180015300`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800158f1`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18001597b`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18001526d`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180015300`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800158f1`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18001597b`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x180015932`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x180015932`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180015468`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180015468`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180015484`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180015484`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800155e9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800155e9`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18001596e`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1800159c2`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18001596e`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1800159c2`
- `OLEAUT32!__imp_SysAllocString` at `0x1800151c4`
- `OLEAUT32!__imp_SysAllocString` at `0x180015390`
- `OLEAUT32!__imp_SysAllocString` at `0x1800151c4`
- `OLEAUT32!__imp_SysAllocString` at `0x180015390`
- `OLEAUT32!__imp_SysFreeString` at `0x180015214`
- `OLEAUT32!__imp_SysFreeString` at `0x1800152cc`
- `OLEAUT32!__imp_SysFreeString` at `0x1800153df`
- `OLEAUT32!__imp_SysFreeString` at `0x18001540c`
- `OLEAUT32!__imp_SysFreeString` at `0x180015214`
- `OLEAUT32!__imp_SysFreeString` at `0x1800152cc`
- `OLEAUT32!__imp_SysFreeString` at `0x1800153df`
- `OLEAUT32!__imp_SysFreeString` at `0x18001540c`

## string_xrefs

- `0x1800151bd`: `ddd:serviceType`
- `0x180015650`: `ddd:serviceType`
- `0x1800156d0`: `ddd:serviceType`
- `0x18001575d`: `ddd:serviceType`
- `0x180015328`: `ddd:serviceList/ddd:service[./ddd:serviceType = '`
- `0x18001515e`: `ddd:serviceList/ddd:service`

## pseudocode

```c
__int64 __fastcall CDescriptionManager::HrPD_DoServicePublication(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const wchar_t **a4,
        struct _SSDP_MESSAGE_EX *a5,
        struct SSDP_SERVICE_REGISTRATION_PARAMS *a6)
{
  struct _SSDP_MESSAGE_EX *v6; // r15
  const wchar_t **v8; // r12
  unsigned int v9; // r13d
  _QWORD *v10; // rsi
  int AdditionalSsdpHeadersAndCount; // edi
  __int64 Key; // rax
  unsigned __int16 *v13; // rbx
  OLECHAR *v14; // rsi
  __int64 v15; // rax
  const wchar_t *v16; // rsi
  __int64 v17; // r15
  size_t v18; // r15
  const wchar_t *v19; // rcx
  size_t v20; // r8
  wchar_t *v21; // r14
  HRESULT v22; // eax
  size_t v23; // rdx
  size_t *v24; // r8
  HRESULT v25; // esi
  _WORD *v26; // rsi
  size_t v27; // r8
  size_t v28; // rdx
  size_t *v29; // r8
  int v30; // r14d
  OLECHAR *v31; // rsi
  __int64 v32; // rax
  __int64 v34; // rsi
  __int64 v35; // rax
  struct _RTL_CRITICAL_SECTION *v36; // rcx
  struct IUPnPDeviceControlSsdpHeaders **v37; // rsi
  CDescriptionManager *v38; // rcx
  __int64 v39; // r8
  signed int LastError; // eax
  STRSAFE_PCNZWCH v41; // rcx
  STRSAFE_PCNZWCH v42; // rcx
  CDescriptionManager *v43; // rcx
  unsigned __int64 v44; // r12
  _QWORD *v45; // rax
  const wchar_t *v46; // r14
  _QWORD *v47; // r12
  wchar_t *v48; // rax
  wchar_t *v49; // rsi
  __int64 v50; // r15
  int v51; // r13d
  unsigned int i; // ebx
  void *v53; // rcx
  LPSTR lpMultiByteStr; // [rsp+20h] [rbp-E0h]
  _QWORD *v55; // [rsp+40h] [rbp-C0h]
  unsigned int v56; // [rsp+48h] [rbp-B8h]
  int v57; // [rsp+4Ch] [rbp-B4h] BYREF
  __int64 v58; // [rsp+50h] [rbp-B0h] BYREF
  OLECHAR *psz; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v60; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v61; // [rsp+68h] [rbp-98h] BYREF
  STRSAFE_PCNZWCH pszSrc; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int16 *v63; // [rsp+78h] [rbp-88h]
  struct _SSDP_MESSAGE_EX *v64; // [rsp+80h] [rbp-80h]
  BSTR bstrString; // [rsp+88h] [rbp-78h] BYREF
  __int64 v66; // [rsp+90h] [rbp-70h] BYREF
  const wchar_t **v67; // [rsp+98h] [rbp-68h]
  __int64 v68; // [rsp+A0h] [rbp-60h]
  __int64 v69; // [rsp+A8h] [rbp-58h]
  __int64 v70; // [rsp+B0h] [rbp-50h]
  struct SSDP_SERVICE_REGISTRATION_PARAMS *v71; // [rsp+B8h] [rbp-48h]
  char v72[256]; // [rsp+C0h] [rbp-40h] BYREF
  char v73[256]; // [rsp+1C0h] [rbp+C0h] BYREF

  v6 = a5;
  v8 = a4;
  v68 = a3;
  v64 = a5;
  v71 = a6;
  v67 = a4;
  v70 = a2;
  v69 = a1;
  if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 0x40) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 66, WPP_d1632e28abac3523b7923f2ce652edb2_Traceguids);
  v9 = 0;
  v56 = 0;
  bstrString = 0;
  v10 = 0;
  v57 = 0;
  v55 = 0;
  SmartComPtr<IUPnPDescriptionManager>::SmartComPtr<IUPnPDescriptionManager>(&v66);
  AdditionalSsdpHeadersAndCount = HrSelectNodes(L"ddd:serviceList/ddd:service", a3, &v66);
  if ( AdditionalSsdpHeadersAndCount >= 0 )
  {
    while ( 1 )
    {
      if ( AdditionalSsdpHeadersAndCount < 0 )
      {
LABEL_36:
        if ( v10 )
        {
          for ( i = 0; i < v9; ++i )
          {
            v53 = (void *)v10[i];
            if ( v53 )
              operator delete(v53);
          }
          operator delete(v10);
        }
        break;
      }
      SmartComPtr<IUPnPDescriptionManager>::SmartComPtr<IUPnPDescriptionManager>(&v58);
      Key = LKRhash::CTypedHashTable<CNoRefHashTable,URL_HASH_ENTRY,char const *,LKRhash::CLKRHashTable>::_ExtractKey((__int64)&v66);
      if ( (*(unsigned int (__fastcall **)(__int64, __int64 *))(*(_QWORD *)Key + 72LL))(Key, &v58) )
      {
        ATL::CComPtr<IUPnPDescriptionManager>::~CComPtr<IUPnPDescriptionManager>((__int64)&v58);
        goto LABEL_36;
      }
      v13 = 0;
      v63 = 0;
      SmartComPtr<IUPnPDescriptionManager>::SmartComPtr<IUPnPDescriptionManager>(&v60);
      v14 = SysAllocString(L"ddd:serviceType");
      if ( v14 )
      {
        ATL::CComPtrBase<IUPnPDynamicContentSource>::Release(&v60);
        v15 = LKRhash::CTypedHashTable<CNoRefHashTable,URL_HASH_ENTRY,char const *,LKRhash::CLKRHashTable>::_ExtractKey((__int64)&v58);
        AdditionalSsdpHeadersAndCount = (*(__int64 (__fastcall **)(__int64, OLECHAR *, __int64 *))(*(_QWORD *)v15 + 296LL))(
                                          v15,
                                          v14,
                                          &v60);
        if ( AdditionalSsdpHeadersAndCount == 1 )
          AdditionalSsdpHeadersAndCount = -2147467259;
        SysFreeString(v14);
        if ( !AdditionalSsdpHeadersAndCount )
          goto LABEL_11;
        v41 = WPP_GLOBAL_Control;
      }
      else
      {
        v41 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control )
        {
          if ( (WPP_GLOBAL_Control[14] & 1) != 0 )
          {
            WPP_SF_Sd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              14,
              (unsigned int)WPP_cfeffffca17e32bb09beafeef3f68c4e_Traceguids,
              (unsigned int)L"ddd:serviceType",
              14);
            v41 = WPP_GLOBAL_Control;
          }
          if ( v41 != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (v41[14] & 1) != 0 )
          {
            WPP_SF_d(*((_QWORD *)v41 + 2), 15, WPP_cfeffffca17e32bb09beafeef3f68c4e_Traceguids, 2147942414LL);
            v41 = WPP_GLOBAL_Control;
          }
        }
        AdditionalSsdpHeadersAndCount = -2147024882;
      }
      if ( v41 != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (v41[14] & 1) != 0 )
      {
        WPP_SF_Sd(
          *((_QWORD *)v41 + 2),
          17,
          (unsigned int)WPP_0f728bc4424332fd22a71fc2ba056f71_Traceguids,
          (unsigned int)L"ddd:serviceType",
          AdditionalSsdpHeadersAndCount);
        v41 = WPP_GLOBAL_Control;
      }
      if ( AdditionalSsdpHeadersAndCount < 0 )
        goto LABEL_80;
LABEL_11:
      pszSrc = 0;
      AdditionalSsdpHeadersAndCount = (*(__int64 (__fastcall **)(__int64, STRSAFE_PCNZWCH *))(*(_QWORD *)v60 + 208LL))(
                                        v60,
                                        &pszSrc);
      if ( AdditionalSsdpHeadersAndCount >= 0 )
      {
        v16 = pszSrc;
        if ( pszSrc )
        {
          v17 = -1;
          do
            ++v17;
          while ( pszSrc[v17] );
          v18 = v17 + 1;
          v21 = (wchar_t *)malloc(2 * v18);
          if ( !v21 )
          {
            AdditionalSsdpHeadersAndCount = -2147024882;
            goto LABEL_56;
          }
          v22 = StringValidateDestW(v19, v18, v20);
          AdditionalSsdpHeadersAndCount = v22;
          if ( v22 >= 0 )
          {
            v25 = StringCopyWorkerW(v21, v23, v24, v16, (size_t)lpMultiByteStr);
            goto LABEL_18;
          }
          v25 = v22;
          if ( v18 )
          {
            *v21 = 0;
LABEL_76:
            free(v21);
            goto LABEL_56;
          }
LABEL_18:
          AdditionalSsdpHeadersAndCount = v25;
          if ( v25 < 0 )
            goto LABEL_76;
          free(0);
          v13 = v21;
          v63 = v21;
          if ( v25 )
          {
LABEL_56:
            if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                10,
                WPP_bbadc92b44a9335df55a63a23abb1016_Traceguids,
                (unsigned int)AdditionalSsdpHeadersAndCount);
          }
          v6 = v64;
        }
        else
        {
          free(0);
          v63 = 0;
          AdditionalSsdpHeadersAndCount = 0;
        }
        SysFreeString((BSTR)pszSrc);
      }
      if ( !AdditionalSsdpHeadersAndCount )
        goto LABEL_23;
      v41 = WPP_GLOBAL_Control;
LABEL_80:
      if ( v41 != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (v41[14] & 1) != 0 )
        WPP_SF_Sd(
          *((_QWORD *)v41 + 2),
          18,
          (unsigned int)WPP_0f728bc4424332fd22a71fc2ba056f71_Traceguids,
          (unsigned int)L"ddd:serviceType",
          AdditionalSsdpHeadersAndCount);
LABEL_23:
      ATL::CComPtr<IUPnPDescriptionManager>::~CComPtr<IUPnPDescriptionManager>((__int64)&v60);
      SmartComPtr<IUPnPDescriptionManager>::SmartComPtr<IUPnPDescriptionManager>(&v61);
      if ( AdditionalSsdpHeadersAndCount < 0 )
        goto LABEL_43;
      psz = 0;
      v26 = malloc(0x64u);
      if ( !v26 )
      {
        AdditionalSsdpHeadersAndCount = -2147024882;
        goto LABEL_45;
      }
      AdditionalSsdpHeadersAndCount = StringValidateDestW((STRSAFE_PCNZWCH)0x32, 0x32u, v27);
      if ( AdditionalSsdpHeadersAndCount < 0 )
      {
        *v26 = 0;
LABEL_85:
        free(v26);
LABEL_45:
        if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            10,
            WPP_bbadc92b44a9335df55a63a23abb1016_Traceguids,
            (unsigned int)AdditionalSsdpHeadersAndCount);
        if ( AdditionalSsdpHeadersAndCount < 0 )
          goto LABEL_49;
        goto LABEL_28;
      }
      AdditionalSsdpHeadersAndCount = StringCopyWorkerW(
                                        v26,
                                        v28,
                                        v29,
                                        L"ddd:serviceList/ddd:service[./ddd:serviceType = '",
                                        (size_t)lpMultiByteStr);
      if ( AdditionalSsdpHeadersAndCount < 0 )
        goto LABEL_85;
      free(0);
      psz = v26;
      if ( AdditionalSsdpHeadersAndCount )
        goto LABEL_45;
LABEL_28:
      AdditionalSsdpHeadersAndCount = CUString::HrAppend((CUString *)&psz, v13);
      if ( AdditionalSsdpHeadersAndCount < 0 )
        goto LABEL_49;
      AdditionalSsdpHeadersAndCount = CUString::HrAppend((CUString *)&psz, L"']");
      if ( AdditionalSsdpHeadersAndCount < 0 )
        goto LABEL_49;
      v30 = (int)psz;
      v31 = SysAllocString(psz);
      if ( !v31 )
      {
        v42 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control )
        {
          if ( (WPP_GLOBAL_Control[14] & 1) != 0 )
          {
            WPP_SF_Sd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              14,
              (unsigned int)WPP_cfeffffca17e32bb09beafeef3f68c4e_Traceguids,
              v30,
              14);
            v42 = WPP_GLOBAL_Control;
          }
          if ( v42 != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (v42[14] & 1) != 0 )
          {
            WPP_SF_d(*((_QWORD *)v42 + 2), 15, WPP_cfeffffca17e32bb09beafeef3f68c4e_Traceguids, 2147942414LL);
            v42 = WPP_GLOBAL_Control;
          }
        }
        AdditionalSsdpHeadersAndCount = -2147024882;
        goto LABEL_94;
      }
      ATL::CComPtrBase<IUPnPDynamicContentSource>::Release(&v61);
      v32 = LKRhash::CTypedHashTable<CNoRefHashTable,URL_HASH_ENTRY,char const *,LKRhash::CLKRHashTable>::_ExtractKey(v68);
      AdditionalSsdpHeadersAndCount = (*(__int64 (__fastcall **)(__int64, OLECHAR *, __int64 *))(*(_QWORD *)v32 + 296LL))(
                                        v32,
                                        v31,
                                        &v61);
      if ( AdditionalSsdpHeadersAndCount == 1 )
        AdditionalSsdpHeadersAndCount = -2147467259;
      SysFreeString(v31);
      if ( AdditionalSsdpHeadersAndCount )
      {
        v42 = WPP_GLOBAL_Control;
LABEL_94:
        if ( v42 != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (v42[14] & 1) != 0 )
          WPP_SF_Sd(
            *((_QWORD *)v42 + 2),
            17,
            (unsigned int)WPP_0f728bc4424332fd22a71fc2ba056f71_Traceguids,
            v30,
            AdditionalSsdpHeadersAndCount);
      }
LABEL_49:
      free(psz);
      if ( AdditionalSsdpHeadersAndCount < 0 )
        goto LABEL_43;
      if ( !(unsigned __int8)ATL::CComPtrBase<IXMLDOMNode>::IsEqualObject(&v61, v58) )
        goto LABEL_42;
      AdditionalSsdpHeadersAndCount = StringCbPrintfA(v73, 0x100u, "%S", v13);
      if ( AdditionalSsdpHeadersAndCount < 0 )
        goto LABEL_43;
      AdditionalSsdpHeadersAndCount = StringCbPrintfA(v72, 0x100u, "%S::%S", *v8, v13);
      if ( AdditionalSsdpHeadersAndCount < 0 )
        goto LABEL_43;
      v34 = v69;
      *((_QWORD *)v6 + 3) = v72;
      *(_QWORD *)v6 = v73;
      EnterCriticalSection((LPCRITICAL_SECTION)(v34 + 568));
      v35 = CTable<_GUID,IUPnPDeviceControlSsdpHeaders *>::Lookup(v34 + 136, v70);
      v36 = (struct _RTL_CRITICAL_SECTION *)(v34 + 568);
      v37 = (struct IUPnPDeviceControlSsdpHeaders **)v35;
      LeaveCriticalSection(v36);
      if ( !v37 || !*v37 )
      {
        v10 = v55;
LABEL_41:
        AdditionalSsdpHeadersAndCount = CDescriptionManager::AddRegistrationParams(v38, v6, v39, v71);
        if ( AdditionalSsdpHeadersAndCount < 0 )
          goto LABEL_44;
LABEL_42:
        AdditionalSsdpHeadersAndCount = HrRegisterServiceWithEventing(&v58, v8, 1);
LABEL_43:
        v10 = v55;
        goto LABEL_44;
      }
      v43 = (CDescriptionManager *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 0x40) != 0 )
        WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 67, WPP_d1632e28abac3523b7923f2ce652edb2_Traceguids, v37);
      AdditionalSsdpHeadersAndCount = CDescriptionManager::HrGetAdditionalSsdpHeadersAndCount(
                                        v43,
                                        *v37,
                                        &bstrString,
                                        &v57);
      if ( AdditionalSsdpHeadersAndCount < 0 )
        goto LABEL_43;
      v44 = v57;
      if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 0x40) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          68,
          WPP_d1632e28abac3523b7923f2ce652edb2_Traceguids,
          (unsigned int)v57);
      v45 = malloc(saturated_mul(v44, 8u));
      v55 = v45;
      v10 = v45;
      if ( v45 )
      {
        if ( AdditionalSsdpHeadersAndCount || (int)v44 <= 0 )
          goto LABEL_121;
        v46 = bstrString;
        v47 = v45;
        do
        {
          v48 = wcsstr(v46, L"\r\n");
          v49 = v48;
          if ( v48 )
          {
            v50 = v48 - v46;
            v51 = WideCharToMultiByte(0xFDE9u, 0, v46, v50 + 1, 0, 0, 0, 0);
            v38 = (CDescriptionManager *)malloc(v51 + 1LL);
            v47[v56] = v38;
            if ( v38 )
            {
              if ( WideCharToMultiByte(0xFDE9u, 0, v46, v50 + 1, (LPSTR)v38, v51 + 1, 0, 0) )
                goto LABEL_114;
              LastError = GetLastError();
              AdditionalSsdpHeadersAndCount = LastError;
              if ( LastError > 0 )
                AdditionalSsdpHeadersAndCount = (unsigned __int16)LastError | 0x80070000;
              if ( AdditionalSsdpHeadersAndCount >= 0 )
              {
LABEL_114:
                v9 = ++v56;
              }
              else
              {
                v9 = v56;
                operator delete((void *)v47[v56]);
              }
            }
            else
            {
              v9 = v56;
              AdditionalSsdpHeadersAndCount = -2147024882;
            }
            v49 += 2;
          }
          if ( !v49 )
            break;
          if ( !*v49 )
            break;
          v46 = v49;
        }
        while ( AdditionalSsdpHeadersAndCount >= 0 );
        v13 = v63;
        LODWORD(v44) = v57;
        v10 = v55;
        if ( AdditionalSsdpHeadersAndCount >= 0 )
        {
          v6 = v64;
LABEL_121:
          *((_QWORD *)v6 + 14) = v10;
          v10 = 0;
          *((_DWORD *)v6 + 26) = v44;
          v8 = v67;
          v55 = 0;
          goto LABEL_41;
        }
      }
      else
      {
        AdditionalSsdpHeadersAndCount = -2147024882;
      }
LABEL_44:
      ATL::CComPtr<IUPnPDescriptionManager>::~CComPtr<IUPnPDescriptionManager>((__int64)&v61);
      free(v13);
      ATL::CComPtr<IUPnPDescriptionManager>::~CComPtr<IUPnPDescriptionManager>((__int64)&v58);
      v6 = v64;
      v8 = v67;
    }
  }
  SysFreeString(bstrString);
  if ( AdditionalSsdpHeadersAndCount
    && WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control
    && (WPP_GLOBAL_Control[14] & 1) != 0 )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      69,
      WPP_d1632e28abac3523b7923f2ce652edb2_Traceguids,
      (unsigned int)AdditionalSsdpHeadersAndCount);
  }
  ATL::CComPtr<IUPnPDescriptionManager>::~CComPtr<IUPnPDescriptionManager>((__int64)&v66);
  return (unsigned int)AdditionalSsdpHeadersAndCount;
}

```

## disassembly

```asm
0x1800150bc  push    rbp
0x1800150be  push    rbx
0x1800150bf  push    rsi
0x1800150c0  push    rdi
0x1800150c1  push    r12
0x1800150c3  push    r13
0x1800150c5  push    r14
0x1800150c7  push    r15
0x1800150c9  lea     rbp, [rsp-1D8h]
0x1800150d1  sub     rsp, 2D8h
0x1800150d8  mov     rax, cs:__security_cookie
0x1800150df  xor     rax, rsp
0x1800150e2  mov     [rbp+210h+var_50], rax
0x1800150e9  mov     r15, [rbp+210h+arg_20]
0x1800150f0  mov     rbx, r8
0x1800150f3  mov     rax, [rbp+210h+arg_28]
0x1800150fa  mov     r12, r9
0x1800150fd  mov     [rbp+210h+var_270], rbx
0x180015101  mov     [rbp+210h+var_290], r15
0x180015105  mov     [rbp+210h+var_258], rax
0x180015109  mov     [rbp+210h+var_278], r9
0x18001510d  mov     [rbp+210h+var_260], rdx
0x180015111  mov     [rbp+210h+var_268], rcx
0x180015115  mov     rcx, cs:WPP_GLOBAL_Control
0x18001511c  lea     rax, WPP_GLOBAL_Control
0x180015123  cmp     rcx, rax
0x180015126  jz      short loc_180015132
0x180015128  test    byte ptr [rcx+1Ch], 40h
0x18001512c  jnz     loc_180015619
0x180015132  xor     r14d, r14d
0x180015135  lea     rcx, [rbp+210h+var_280]; void *
0x180015139  mov     r13d, r14d
0x18001513c  mov     [rsp+310h+var_2C8], r14d
0x180015141  mov     [rbp+210h+bstrString], r14
0x180015145  mov     esi, r14d
0x180015148  mov     [rsp+310h+var_2C4], r14d
0x18001514d  mov     [rsp+310h+var_2D0], r14
0x180015152  call    ??0?$SmartComPtr@UIUPnPDescriptionManager@@@@QEAA@XZ; SmartComPtr<IUPnPDescriptionManager>::SmartComPtr<IUPnPDescriptionManager>(void)
0x180015157  lea     r8, [rbp+210h+var_280]
0x18001515b  mov     rdx, rbx
0x18001515e  lea     rcx, aDddServicelist_0; "ddd:serviceList/ddd:service"
0x180015165  call    ?HrSelectNodes@@YAJPEBGAEAV?$SmartComPtr@UIXMLDOMNode@@@@AEAV?$SmartComPtr@UIXMLDOMNodeList@@@@@Z; HrSelectNodes(ushort const *,SmartComPtr<IXMLDOMNode> &,SmartComPtr<IXMLDOMNodeList> &)
0x18001516a  mov     edi, eax
0x18001516c  test    eax, eax
0x18001516e  js      loc_180015408
0x180015174  test    edi, edi
0x180015176  js      loc_1800153FF
0x18001517c  lea     rcx, [rsp+310h+var_2C0]; void *
0x180015181  call    ??0?$SmartComPtr@UIUPnPDescriptionManager@@@@QEAA@XZ; SmartComPtr<IUPnPDescriptionManager>::SmartComPtr<IUPnPDescriptionManager>(void)
0x180015186  lea     rcx, [rbp+210h+var_280]
0x18001518a  call    ?_ExtractKey@?$CTypedHashTable@VCNoRefHashTable@@VURL_HASH_ENTRY@@PEBDVCLKRHashTable@LKRhash@@@LKRhash@@CA?B_KPEBX@Z; LKRhash::CTypedHashTable<CNoRefHashTable,URL_HASH_ENTRY,char const *,LKRhash::CLKRHashTable>::_ExtractKey(void const *)
0x18001518f  mov     rcx, rax
0x180015192  lea     rdx, [rsp+310h+var_2C0]
0x180015197  mov     rax, [rax]
0x18001519a  mov     rax, [rax+48h]
0x18001519e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800151a3  test    eax, eax
0x1800151a5  jnz     loc_1800153F5
0x1800151ab  mov     rbx, r14
0x1800151ae  lea     rcx, [rsp+310h+var_2B0]; void *
0x1800151b3  mov     [rsp+310h+var_298], rbx
0x1800151b8  call    ??0?$SmartComPtr@UIUPnPDescriptionManager@@@@QEAA@XZ; SmartComPtr<IUPnPDescriptionManager>::SmartComPtr<IUPnPDescriptionManager>(void)
0x1800151bd  lea     rcx, aDddServicetype; "ddd:serviceType"
0x1800151c4  call    cs:__imp_SysAllocString
0x1800151ca  mov     rsi, rax
0x1800151cd  test    rax, rax
0x1800151d0  jz      loc_180015633
0x1800151d6  lea     rcx, [rsp+310h+var_2B0]
0x1800151db  call    ?Release@?$CComPtrBase@UIUPnPDynamicContentSource@@@ATL@@QEAAXXZ; ATL::CComPtrBase<IUPnPDynamicContentSource>::Release(void)
0x1800151e0  lea     rcx, [rsp+310h+var_2C0]
0x1800151e5  call    ?_ExtractKey@?$CTypedHashTable@VCNoRefHashTable@@VURL_HASH_ENTRY@@PEBDVCLKRHashTable@LKRhash@@@LKRhash@@CA?B_KPEBX@Z; LKRhash::CTypedHashTable<CNoRefHashTable,URL_HASH_ENTRY,char const *,LKRhash::CLKRHashTable>::_ExtractKey(void const *)
0x1800151ea  mov     rcx, rax
0x1800151ed  lea     r8, [rsp+310h+var_2B0]
0x1800151f2  mov     rdx, rsi
0x1800151f5  mov     rax, [rax]
0x1800151f8  mov     rax, [rax+128h]
0x1800151ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015204  mov     edi, eax
0x180015206  cmp     eax, 1
0x180015209  mov     eax, 80004005h
0x18001520e  mov     rcx, rsi; bstrString
0x180015211  cmovz   edi, eax
0x180015214  call    cs:__imp_SysFreeString
0x18001521a  test    edi, edi
0x18001521c  jnz     loc_1800156AB
0x180015222  mov     rcx, [rsp+310h+var_2B0]
0x180015227  lea     rdx, [rsp+310h+pszSrc]
0x18001522c  mov     [rsp+310h+pszSrc], r14
0x180015231  mov     rax, [rcx]
0x180015234  mov     rax, [rax+0D0h]
0x18001523b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015240  mov     edi, eax
0x180015242  test    eax, eax
0x180015244  js      loc_1800152D2
0x18001524a  mov     rsi, [rsp+310h+pszSrc]
0x18001524f  test    rsi, rsi
0x180015252  jz      loc_1800156F8
0x180015258  or      r15, 0FFFFFFFFFFFFFFFFh
0x18001525c  inc     r15
0x18001525f  cmp     [rsi+r15*2], r14w
0x180015264  jnz     short loc_18001525C
0x180015266  inc     r15
0x180015269  lea     rcx, [r15+r15]; Size
0x18001526d  call    cs:__imp_malloc
0x180015273  mov     r14, rax
0x180015276  test    rax, rax
0x180015279  jz      loc_18001570D
0x18001527f  mov     rdx, r15; cchDest
0x180015282  call    StringValidateDestW
0x180015287  mov     edi, eax
0x180015289  test    eax, eax
0x18001528b  js      loc_18001572B
0x180015291  mov     r9, rsi; pszSrc
0x180015294  mov     rcx, r14; pszDest
0x180015297  call    StringCopyWorkerW
0x18001529c  mov     esi, eax
0x18001529e  mov     edi, esi
0x1800152a0  test    esi, esi
0x1800152a2  js      loc_18001571A
0x1800152a8  xor     ecx, ecx; Block
0x1800152aa  call    cs:__imp_free
0x1800152b0  mov     rbx, r14
0x1800152b3  xor     r14d, r14d
0x1800152b6  mov     [rsp+310h+var_298], rbx
0x1800152bb  test    esi, esi
0x1800152bd  jnz     loc_1800155AB
0x1800152c3  mov     r15, [rbp+210h+var_290]
0x1800152c7  mov     rcx, [rsp+310h+pszSrc]; bstrString
0x1800152cc  call    cs:__imp_SysFreeString
0x1800152d2  test    edi, edi
0x1800152d4  jnz     loc_180015738
0x1800152da  lea     rcx, [rsp+310h+var_2B0]
0x1800152df  call    ??1?$CComPtr@UIUPnPDescriptionManager@@@ATL@@QEAA@XZ; ATL::CComPtr<IUPnPDescriptionManager>::~CComPtr<IUPnPDescriptionManager>(void)
0x1800152e4  lea     rcx, [rsp+310h+var_2A8]; void *
0x1800152e9  call    ??0?$SmartComPtr@UIUPnPDescriptionManager@@@@QEAA@XZ; SmartComPtr<IUPnPDescriptionManager>::SmartComPtr<IUPnPDescriptionManager>(void)
0x1800152ee  test    edi, edi
0x1800152f0  js      loc_1800154BF
0x1800152f6  mov     ecx, 64h ; 'd'; Size
0x1800152fb  mov     [rsp+310h+psz], r14
0x180015300  call    cs:__imp_malloc
0x180015306  mov     rsi, rax
0x180015309  test    rax, rax
0x18001530c  jz      loc_18001577E
0x180015312  mov     ecx, 32h ; '2'; pszDest
0x180015317  mov     edx, ecx; cchDest
0x180015319  call    StringValidateDestW
0x18001531e  mov     edi, eax
0x180015320  test    eax, eax
0x180015322  js      loc_180015788
0x180015328  lea     r9, aDddServicelist; "ddd:serviceList/ddd:service[./ddd:servi"...
0x18001532f  mov     rcx, rsi; pszDest
0x180015332  call    StringCopyWorkerW
0x180015337  mov     edi, eax
0x180015339  test    eax, eax
0x18001533b  js      loc_18001578C
0x180015341  xor     ecx, ecx; Block
0x180015343  call    cs:__imp_free
0x180015349  mov     [rsp+310h+psz], rsi
0x18001534e  test    edi, edi
0x180015350  jnz     loc_1800154EE
0x180015356  mov     rdx, rbx; unsigned __int16 *
0x180015359  lea     rcx, [rsp+310h+psz]; this
0x18001535e  call    ?HrAppend@CUString@@QEAAJPEBG@Z; CUString::HrAppend(ushort const *)
0x180015363  mov     edi, eax
0x180015365  test    eax, eax
0x180015367  js      loc_180015527
0x18001536d  lea     rdx, asc_1800601A8; "']"
0x180015374  lea     rcx, [rsp+310h+psz]; this
0x180015379  call    ?HrAppend@CUString@@QEAAJPEBG@Z; CUString::HrAppend(ushort const *)
0x18001537e  mov     edi, eax
0x180015380  test    eax, eax
0x180015382  js      loc_180015527
0x180015388  mov     r14, [rsp+310h+psz]
0x18001538d  mov     rcx, r14; psz
0x180015390  call    cs:__imp_SysAllocString
0x180015396  mov     rsi, rax
0x180015399  test    rax, rax
0x18001539c  jz      loc_18001579A
0x1800153a2  lea     rcx, [rsp+310h+var_2A8]
0x1800153a7  call    ?Release@?$CComPtrBase@UIUPnPDynamicContentSource@@@ATL@@QEAAXXZ; ATL::CComPtrBase<IUPnPDynamicContentSource>::Release(void)
0x1800153ac  mov     rcx, [rbp+210h+var_270]
0x1800153b0  call    ?_ExtractKey@?$CTypedHashTable@VCNoRefHashTable@@VURL_HASH_ENTRY@@PEBDVCLKRHashTable@LKRhash@@@LKRhash@@CA?B_KPEBX@Z; LKRhash::CTypedHashTable<CNoRefHashTable,URL_HASH_ENTRY,char const *,LKRhash::CLKRHashTable>::_ExtractKey(void const *)
0x1800153b5  mov     rcx, rax
0x1800153b8  lea     r8, [rsp+310h+var_2A8]
0x1800153bd  mov     rdx, rsi
0x1800153c0  mov     rax, [rax]
0x1800153c3  mov     rax, [rax+128h]
0x1800153ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800153cf  mov     edi, eax
0x1800153d1  cmp     eax, 1
0x1800153d4  mov     eax, 80004005h
0x1800153d9  mov     rcx, rsi; bstrString
0x1800153dc  cmovz   edi, eax
0x1800153df  call    cs:__imp_SysFreeString
0x1800153e5  test    edi, edi
0x1800153e7  jnz     loc_18001580E
0x1800153ed  xor     r14d, r14d
0x1800153f0  jmp     loc_180015527
0x1800153f5  lea     rcx, [rsp+310h+var_2C0]
0x1800153fa  call    ??1?$CComPtr@UIUPnPDescriptionManager@@@ATL@@QEAA@XZ; ATL::CComPtr<IUPnPDescriptionManager>::~CComPtr<IUPnPDescriptionManager>(void)
0x1800153ff  test    rsi, rsi
0x180015402  jnz     loc_180015A3A
0x180015408  mov     rcx, [rbp+210h+bstrString]; bstrString
0x18001540c  call    cs:__imp_SysFreeString
0x180015412  test    edi, edi
0x180015414  jnz     loc_180015A66
0x18001541a  lea     rcx, [rbp+210h+var_280]
0x18001541e  call    ??1?$CComPtr@UIUPnPDescriptionManager@@@ATL@@QEAA@XZ; ATL::CComPtr<IUPnPDescriptionManager>::~CComPtr<IUPnPDescriptionManager>(void)
0x180015423  mov     eax, edi
0x180015425  mov     rcx, [rbp+210h+var_50]
0x18001542c  xor     rcx, rsp; StackCookie
0x18001542f  call    __security_check_cookie
0x180015434  add     rsp, 2D8h
0x18001543b  pop     r15
0x18001543d  pop     r14
0x18001543f  pop     r13
0x180015441  pop     r12
0x180015443  pop     rdi
0x180015444  pop     rsi
0x180015445  pop     rbx
0x180015446  pop     rbp
0x180015447  retn
0x180015448  mov     rsi, [rbp+210h+var_268]
0x18001544c  lea     rax, [rbp+210h+var_250]
0x180015450  mov     [r15+18h], rax
0x180015454  lea     rax, [rbp+210h+var_150]
0x18001545b  mov     [r15], rax
0x18001545e  lea     rdi, [rsi+238h]
0x180015465  mov     rcx, rdi; lpCriticalSection
0x180015468  call    cs:__imp_EnterCriticalSection
0x18001546e  mov     rdx, [rbp+210h+var_260]
0x180015472  lea     rcx, [rsi+88h]
0x180015479  call    ?Lookup@?$CTable@U_GUID@@PEAUIUPnPDeviceControlSsdpHeaders@@@@QEAAPEAPEAUIUPnPDeviceControlSsdpHeaders@@AEBU_GUID@@@Z; CTable<_GUID,IUPnPDeviceControlSsdpHeaders *>::Lookup(_GUID const &)
0x18001547e  mov     rcx, rdi; lpCriticalSection
0x180015481  mov     rsi, rax
0x180015484  call    cs:__imp_LeaveCriticalSection
0x18001548a  test    rsi, rsi
0x18001548d  jnz     loc_180015850
0x180015493  mov     rsi, [rsp+310h+var_2D0]
0x180015498  mov     r9, [rbp+210h+var_258]; struct SSDP_SERVICE_REGISTRATION_PARAMS *
0x18001549c  mov     rdx, r15; struct _SSDP_MESSAGE_EX *
0x18001549f  call    ?AddRegistrationParams@CDescriptionManager@@AEAAJPEAU_SSDP_MESSAGE_EX@@KPEAUSSDP_SERVICE_REGISTRATION_PARAMS@@@Z; CDescriptionManager::AddRegistrationParams(_SSDP_MESSAGE_EX *,ulong,SSDP_SERVICE_REGISTRATION_PARAMS *)
0x1800154a4  mov     edi, eax
0x1800154a6  test    eax, eax
0x1800154a8  js      short loc_1800154C4
0x1800154aa  mov     r8d, 1
0x1800154b0  lea     rcx, [rsp+310h+var_2C0]
0x1800154b5  mov     rdx, r12
0x1800154b8  call    ?HrRegisterServiceWithEventing@@YAJAEAV?$SmartComPtr@UIXMLDOMNode@@@@AEBVCUString@@H@Z; HrRegisterServiceWithEventing(SmartComPtr<IXMLDOMNode> &,CUString const &,int)
0x1800154bd  mov     edi, eax
0x1800154bf  mov     rsi, [rsp+310h+var_2D0]
0x1800154c4  lea     rcx, [rsp+310h+var_2A8]
0x1800154c9  call    ??1?$CComPtr@UIUPnPDescriptionManager@@@ATL@@QEAA@XZ; ATL::CComPtr<IUPnPDescriptionManager>::~CComPtr<IUPnPDescriptionManager>(void)
0x1800154ce  mov     rcx, rbx; Block
0x1800154d1  call    cs:__imp_free
0x1800154d7  lea     rcx, [rsp+310h+var_2C0]
0x1800154dc  call    ??1?$CComPtr@UIUPnPDescriptionManager@@@ATL@@QEAA@XZ; ATL::CComPtr<IUPnPDescriptionManager>::~CComPtr<IUPnPDescriptionManager>(void)
0x1800154e1  mov     r15, [rbp+210h+var_290]
0x1800154e5  mov     r12, [rbp+210h+var_278]
0x1800154e9  jmp     loc_180015174
0x1800154ee  mov     rcx, cs:WPP_GLOBAL_Control
0x1800154f5  lea     rax, WPP_GLOBAL_Control
0x1800154fc  cmp     rcx, rax
0x1800154ff  jz      short loc_18001551F
0x180015501  test    byte ptr [rcx+1Ch], 1
0x180015505  jz      short loc_18001551F
0x180015507  mov     rcx, [rcx+10h]
0x18001550b  lea     r8, WPP_bbadc92b44a9335df55a63a23abb1016_Traceguids
0x180015512  mov     edx, 0Ah
0x180015517  mov     r9d, edi
0x18001551a  call    WPP_SF_d
0x18001551f  test    edi, edi
0x180015521  jns     loc_180015356
0x180015527  mov     rcx, [rsp+310h+psz]; Block
0x18001552c  call    cs:__imp_free
0x180015532  test    edi, edi
0x180015534  js      short loc_1800154BF
0x180015536  mov     rdx, [rsp+310h+var_2C0]
0x18001553b  lea     rcx, [rsp+310h+var_2A8]
0x180015540  call    ?IsEqualObject@?$CComPtrBase@UIXMLDOMNode@@@ATL@@QEAA_NPEAUIUnknown@@@Z; ATL::CComPtrBase<IXMLDOMNode>::IsEqualObject(IUnknown *)
0x180015545  test    al, al
0x180015547  jz      loc_1800154AA
0x18001554d  mov     esi, 100h
0x180015552  lea     r8, aS_0; "%S"
0x180015559  mov     edx, esi; unsigned __int64
0x18001555b  lea     rcx, [rbp+210h+var_150]; char *
0x180015562  mov     r9, rbx
0x180015565  call    ?StringCbPrintfA@@YAJPEAD_KPEBDZZ; StringCbPrintfA(char *,unsigned __int64,char const *,...)
0x18001556a  mov     edi, eax
0x18001556c  test    eax, eax
0x18001556e  js      loc_1800154BF
0x180015574  mov     r9, [r12]
0x180015578  lea     r8, aSS; "%S::%S"
0x18001557f  mov     edx, esi; unsigned __int64
0x180015581  mov     [rsp+310h+lpMultiByteStr], rbx
0x180015586  lea     rcx, [rbp+210h+var_250]; char *
0x18001558a  call    ?StringCbPrintfA@@YAJPEAD_KPEBDZZ; StringCbPrintfA(char *,unsigned __int64,char const *,...)
0x18001558f  mov     edi, eax
0x180015591  test    eax, eax
0x180015593  js      loc_1800154BF
  ... truncated ...
```
