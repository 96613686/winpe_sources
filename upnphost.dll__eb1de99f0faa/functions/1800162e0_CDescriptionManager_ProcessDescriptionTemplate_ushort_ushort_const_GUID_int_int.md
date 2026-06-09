# CDescriptionManager::ProcessDescriptionTemplate(ushort *,ushort const *,_GUID *,int,int)

- ea: `0x1800162e0`
- end: `0x180016aed`
- name: `?ProcessDescriptionTemplate@CDescriptionManager@@UEAAJPEAGPEBGPEAU_GUID@@HH@Z`
- size: `2061`
- prototype: `int(CDescriptionManager *__hidden this, unsigned __int16 *, const unsigned __int16 *, struct _GUID *, int, int)`
- caller_count: `0`
- callee_count: `35`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18000f348`
- `0x18000f440`
- `0x1800117bc`
- `0x1800117d0`
- `0x1800117e8`
- `0x180013180`
- `0x180015ab0`
- `0x1800162e0`
- `0x180016c80`
- `0x180017738`
- `0x180018f14`
- `0x18001add0`
- `0x18001bf14`
- `0x18001cb5c`
- `0x18001cc38`
- `0x18002446c`
- `0x1800247c4`
- `0x180025330`
- `0x180028d68`
- `0x180029038`
- `0x18002b52c`
- `0x18002ea70`
- `0x18002f298`
- `0x18002fb24`
- `0x180031484`
- `0x180032ea0`
- `0x180037ef8`
- `0x180038ce4`
- `0x180039a84`
- `0x18003a560`
- `0x18003fea4`
- `0x180049b1c`
- `0x18004a538`
- `0x18004a60c`
- `0x180055010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800164f8`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001653d`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800166d0`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800164f8`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001653d`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800166d0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001677a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800167ce`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180016826`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001677a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800167ce`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180016826`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001655b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800166f9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800167b6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800167ed`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001655b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800166f9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800167b6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800167ed`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001645f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800166c5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001645f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800166c5`
- `OLEAUT32!__imp_SysAllocString` at `0x180016a2e`
- `OLEAUT32!__imp_SysAllocString` at `0x180016a2e`
- `OLEAUT32!__imp_SysFreeString` at `0x180016a57`
- `OLEAUT32!__imp_SysFreeString` at `0x180016a9a`
- `OLEAUT32!__imp_SysFreeString` at `0x180016a57`
- `OLEAUT32!__imp_SysFreeString` at `0x180016a9a`

## pseudocode

```c
__int64 __fastcall CDescriptionManager::ProcessDescriptionTemplate(
        CDescriptionManager *this,
        unsigned __int16 *a2,
        const unsigned __int16 *a3,
        struct _GUID *a4,
        int a5,
        int a6)
{
  STRSAFE_PCNZWCH v10; // rcx
  int IsAllowedCOMCallLocality; // esi
  __int64 v12; // r8
  struct _GUID v13; // xmm0
  STRSAFE_PCNZWCH v14; // rcx
  __int64 v15; // rcx
  __int64 v16; // rcx
  __int64 v17; // rcx
  __int64 v18; // rcx
  __int64 v19; // rcx
  __int64 (__fastcall ***v21)(LPVOID, GUID *, __int64 *); // rbx
  char *v22; // rdi
  HKEY *v23; // rcx
  int v24; // edx
  int v25; // r14d
  int v26; // edi
  int i; // ecx
  _QWORD *v28; // rdx
  __int64 v29; // rax
  _OWORD *v30; // r15
  int v31; // eax
  __int64 v32; // rcx
  __int64 v33; // rcx
  unsigned __int16 *v34; // rax
  OLECHAR *v35; // rbx
  HKEY phkResult; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v37; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v38; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v39; // [rsp+48h] [rbp-B8h] BYREF
  __int64 (__fastcall ***v40)(LPVOID, GUID *, __int64 *); // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int16 *v41; // [rsp+58h] [rbp-A8h] BYREF
  HKEY hKey; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v43; // [rsp+68h] [rbp-98h] BYREF
  __int64 v44; // [rsp+70h] [rbp-90h] BYREF
  void *v45; // [rsp+78h] [rbp-88h] BYREF
  void *Block; // [rsp+80h] [rbp-80h] BYREF
  __int64 v47; // [rsp+88h] [rbp-78h]
  _QWORD v48[2]; // [rsp+90h] [rbp-70h] BYREF
  __int64 v49[2]; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v50[2]; // [rsp+B0h] [rbp-50h] BYREF
  struct _GUID *v51; // [rsp+C0h] [rbp-40h]
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+C8h] [rbp-38h]
  struct _GUID v53; // [rsp+D0h] [rbp-30h] BYREF
  __int128 v54; // [rsp+E0h] [rbp-20h]
  struct _GUID v55; // [rsp+F0h] [rbp-10h] BYREF

  v51 = a4;
  if ( !a2 || !a3 || !a4 )
    return 2147500035LL;
  lpCriticalSection = (LPCRITICAL_SECTION)((char *)this + 24);
  ATL::CComSafeDeleteCriticalSection::Lock((CDescriptionManager *)((char *)this + 24));
  SmartComPtr<IUPnPDescriptionManager>::SmartComPtr<IUPnPDescriptionManager>(&v40);
  SmartComPtr<IUPnPDescriptionManager>::SmartComPtr<IUPnPDescriptionManager>(&v37);
  v45 = 0;
  SmartComPtr<IUPnPDescriptionManager>::SmartComPtr<IUPnPDescriptionManager>(&v38);
  SmartComPtr<IUPnPDescriptionManager>::SmartComPtr<IUPnPDescriptionManager>(&v39);
  SmartComPtr<IUPnPDescriptionManager>::SmartComPtr<IUPnPDescriptionManager>(&v44);
  SmartComPtr<IUPnPDescriptionManager>::SmartComPtr<IUPnPDescriptionManager>(&v43);
  IsAllowedCOMCallLocality = HrIsAllowedCOMCallLocality(1);
  if ( IsAllowedCOMCallLocality >= 0 )
  {
    if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 0x40) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, WPP_d1632e28abac3523b7923f2ce652edb2_Traceguids);
    IsAllowedCOMCallLocality = HrLoadDocument((__int64)a2, (LPVOID *)&v40, v12);
    if ( IsAllowedCOMCallLocality >= 0 )
    {
      v21 = v40;
      ATL::CComPtrBase<IUPnPDynamicContentSource>::Release(&v37);
      IsAllowedCOMCallLocality = -2147467261;
      if ( !v21
        || (IsAllowedCOMCallLocality = (**v21)(v21, &GUID_2933bf80_7b36_11d2_b20e_00c04f983e60, &v37),
            IsAllowedCOMCallLocality < 0) )
      {
LABEL_77:
        v10 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            26,
            WPP_d1632e28abac3523b7923f2ce652edb2_Traceguids,
            (unsigned int)IsAllowedCOMCallLocality);
        goto LABEL_10;
      }
      if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 0x40) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, WPP_d1632e28abac3523b7923f2ce652edb2_Traceguids);
      IsAllowedCOMCallLocality = HrSelectNodeText((OLECHAR *)L"/ddd:root/ddd:device/ddd:UDN");
      if ( IsAllowedCOMCallLocality >= 0 )
      {
        if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 0x40) != 0 )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, WPP_d1632e28abac3523b7923f2ce652edb2_Traceguids);
        IsAllowedCOMCallLocality = HrSelectNodes(L"//ddd:device", &v37, &v38);
        if ( IsAllowedCOMCallLocality >= 0 )
        {
          IsAllowedCOMCallLocality = HrSelectNodes(L"//ddd:UDN", &v37, &v39);
          if ( IsAllowedCOMCallLocality >= 0 )
          {
            IsAllowedCOMCallLocality = HrSelectNodes(L"//ddd:SCPDURL", &v37, &v44);
            if ( IsAllowedCOMCallLocality >= 0 )
              IsAllowedCOMCallLocality = HrSelectNodes(L"//ddd:icon", &v37, &v43);
          }
        }
      }
    }
    if ( !IsAllowedCOMCallLocality )
      goto LABEL_10;
    goto LABEL_77;
  }
LABEL_10:
  v49[0] = 0;
  v49[1] = 0;
  v50[0] = 0;
  v50[1] = 0;
  Block = 0;
  v47 = 0;
  v48[0] = 0;
  v48[1] = 0;
  v55 = 0;
  if ( IsAllowedCOMCallLocality >= 0 )
  {
    if ( a6 )
    {
      v13 = *a4;
      hKey = 0;
      phkResult = 0;
      v55 = v13;
      IsAllowedCOMCallLocality = HrCreateOrOpenDescriptionKey(&phkResult);
      if ( IsAllowedCOMCallLocality >= 0 )
      {
        v41 = 0;
        IsAllowedCOMCallLocality = CUString::HrInitFromGUID((CUString *)&v41, &v55);
        if ( IsAllowedCOMCallLocality >= 0 )
          IsAllowedCOMCallLocality = HrRegOpenKeyEx(phkResult, v41, 0x2001Fu, &hKey);
        RegCloseKey(phkResult);
        free(v41);
      }
      if ( IsAllowedCOMCallLocality )
      {
        v14 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            122,
            WPP_d1632e28abac3523b7923f2ce652edb2_Traceguids,
            (unsigned int)IsAllowedCOMCallLocality);
        if ( IsAllowedCOMCallLocality < 0 )
        {
          if ( IsAllowedCOMCallLocality == -2147024894 )
            IsAllowedCOMCallLocality = -2147180494;
          goto LABEL_22;
        }
      }
      IsAllowedCOMCallLocality = CDescriptionManager::HrLD_ReadUDNMappings((__int64)v14, hKey, (__int64)v49);
      if ( IsAllowedCOMCallLocality >= 0 )
        IsAllowedCOMCallLocality = CDescriptionManager::HrPDT_ReregisterUDNsInDescriptionDocument(v15, v49, &v39);
      RegCloseKey(hKey);
    }
    else
    {
      IsAllowedCOMCallLocality = CDescriptionManager::HrPDT_DoUDNToUDNMapping(v10, &v39, v49);
      if ( IsAllowedCOMCallLocality < 0 )
        goto LABEL_22;
      IsAllowedCOMCallLocality = CDescriptionManager::HrPDT_FetchPhysicalIdentifier(v32, v49, &v45, &v55);
    }
    if ( IsAllowedCOMCallLocality < 0 )
      goto LABEL_22;
    IsAllowedCOMCallLocality = CDescriptionManager::HrPDT_ReplaceSCPDURLs(v16, (__int64)&v44, a3, (__int64)&Block);
    if ( IsAllowedCOMCallLocality < 0 )
      goto LABEL_22;
    IsAllowedCOMCallLocality = CDescriptionManager::HrPDT_ReplaceIcons(v17, (__int64)&v43, a3, (__int64)&Block);
    if ( IsAllowedCOMCallLocality < 0 )
      goto LABEL_22;
    IsAllowedCOMCallLocality = CDescriptionManager::HrPDT_ReplaceControlAndEventURLs(v18, &v38);
    if ( IsAllowedCOMCallLocality < 0 )
      goto LABEL_22;
    LODWORD(phkResult) = 0;
    IsAllowedCOMCallLocality = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v38 + 80LL))(v38);
    if ( IsAllowedCOMCallLocality < 0 )
      goto LABEL_22;
    IsAllowedCOMCallLocality = CDescriptionManager::HrPDT_ProcessPresentationURLs(v19, &v55, &v38, &phkResult);
    if ( IsAllowedCOMCallLocality < 0 )
      goto LABEL_22;
    if ( (_DWORD)phkResult )
    {
      v34 = SysAllocString(a3);
      v35 = v34;
      if ( !v34 )
      {
        IsAllowedCOMCallLocality = -2147024882;
        goto LABEL_22;
      }
      IsAllowedCOMCallLocality = HrCreatePresentationVirtualDir(&v55, v34);
      SysFreeString(v35);
      if ( IsAllowedCOMCallLocality < 0 )
        goto LABEL_22;
    }
    if ( !a5
      || (IsAllowedCOMCallLocality = CDescriptionManager::HrPDT_PersistDescriptionDocument(v33, &v55, &v40),
          IsAllowedCOMCallLocality >= 0) )
    {
      IsAllowedCOMCallLocality = CDescriptionManager::HrPersistDeviceSettingsToRegistry(
                                   v33,
                                   &v55,
                                   v49,
                                   (__int64)&Block,
                                   a5);
      if ( IsAllowedCOMCallLocality >= 0 )
      {
        EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 568));
        v25 = v47;
        v26 = 0;
        v54 = 0;
        v53 = v55;
        if ( (int)v47 > 0 )
        {
          v30 = Block;
          while ( IsAllowedCOMCallLocality >= 0 )
          {
            v54 = v30[v26];
            v31 = CUArray<CDescriptionManager::CleanupItem>::HrPushBack((char *)this + 200, &v53);
            ++v26;
            IsAllowedCOMCallLocality = v31;
            if ( v26 >= v25 )
            {
              if ( v31 < 0 )
                break;
              goto LABEL_56;
            }
          }
        }
        else
        {
LABEL_56:
          IsAllowedCOMCallLocality = CTable<_GUID,FileInfo>::HrAppendTableTransfer((char *)this + 168, &Block);
        }
        LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 568));
        if ( IsAllowedCOMCallLocality >= 0 )
        {
          EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 216));
          IsAllowedCOMCallLocality = CTable<_GUID,CTable<CUString,CUString>>::HrInsertTransfer(
                                       (char *)this + 256,
                                       &v55,
                                       v49);
          LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 216));
          if ( IsAllowedCOMCallLocality >= 0 )
          {
            phkResult = 0;
            IsAllowedCOMCallLocality = (*(__int64 (__fastcall **)(__int64, HKEY *))(*(_QWORD *)v37 + 272LL))(
                                         v37,
                                         &phkResult);
            if ( IsAllowedCOMCallLocality >= 0 )
            {
              EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 568));
              for ( i = 0; ; ++i )
              {
                if ( i >= *((_DWORD *)this + 20) )
                {
                  v22 = (char *)this + 88;
                  goto LABEL_50;
                }
                v28 = (_QWORD *)(*((_QWORD *)this + 9) + 16LL * i);
                v29 = *(_QWORD *)&v55.Data1 - *v28;
                if ( *(_QWORD *)&v55.Data1 == *v28 )
                  v29 = *(_QWORD *)v55.Data4 - v28[1];
                if ( !v29 )
                  break;
              }
              v22 = (char *)this + 88;
              v23 = (HKEY *)(*((_QWORD *)this + 11) + 8LL * i);
              if ( v23 )
              {
                *v23 = phkResult;
LABEL_45:
                IsAllowedCOMCallLocality = 0;
                goto LABEL_46;
              }
LABEL_50:
              IsAllowedCOMCallLocality = CUArray<_GUID>::HrPushBack((char *)this + 72, &v55);
              if ( IsAllowedCOMCallLocality >= 0 )
              {
                v24 = *((_DWORD *)v22 + 3);
                if ( *((_DWORD *)v22 + 2) != v24
                  || (IsAllowedCOMCallLocality = CUArray<unsigned short *>::HrSetReserve(v22, (unsigned int)(v24 + 50)),
                      IsAllowedCOMCallLocality >= 0) )
                {
                  *(_QWORD *)(*(_QWORD *)v22 + 8LL * (int)(*((_DWORD *)v22 + 2))++) = phkResult;
                  goto LABEL_45;
                }
                CUArray<_GUID>::HrPopBack((char *)this + 72);
              }
LABEL_46:
              LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 568));
              if ( IsAllowedCOMCallLocality >= 0 )
              {
                if ( !a6 )
                  *v51 = v55;
                goto LABEL_23;
              }
              SysFreeString((BSTR)phkResult);
            }
          }
        }
      }
    }
  }
LABEL_22:
  (*(void (__fastcall **)(CDescriptionManager *, struct _GUID *, _QWORD))(*(_QWORD *)this + 48LL))(this, &v55, 0);
LABEL_23:
  if ( IsAllowedCOMCallLocality
    && WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control
    && (WPP_GLOBAL_Control[14] & 1) != 0 )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      47,
      WPP_d1632e28abac3523b7923f2ce652edb2_Traceguids,
      (unsigned int)IsAllowedCOMCallLocality);
  }
  CUArray<FileInfo>::Clear(v48);
  if ( Block )
    free(Block);
  CUArray<CUString>::Clear(v50);
  CUArray<CUString>::Clear(v49);
  ATL::CComPtr<IUPnPDescriptionManager>::~CComPtr<IUPnPDescriptionManager>((__int64)&v43);
  ATL::CComPtr<IUPnPDescriptionManager>::~CComPtr<IUPnPDescriptionManager>((__int64)&v44);
  ATL::CComPtr<IUPnPDescriptionManager>::~CComPtr<IUPnPDescriptionManager>((__int64)&v39);
  ATL::CComPtr<IUPnPDescriptionManager>::~CComPtr<IUPnPDescriptionManager>((__int64)&v38);
  free(v45);
  ATL::CComPtr<IUPnPDescriptionManager>::~CComPtr<IUPnPDescriptionManager>((__int64)&v37);
  ATL::CComPtr<IUPnPDescriptionManager>::~CComPtr<IUPnPDescriptionManager>((__int64)&v40);
  LeaveCriticalSection(lpCriticalSection);
  return (unsigned int)IsAllowedCOMCallLocality;
}

```

## disassembly

```asm
0x1800162e0  push    rbp
0x1800162e2  push    rbx
0x1800162e3  push    rsi
0x1800162e4  push    rdi
0x1800162e5  push    r13
0x1800162e7  push    r14
0x1800162e9  push    r15
0x1800162eb  lea     rbp, [rsp-10h]
0x1800162f0  sub     rsp, 110h
0x1800162f7  mov     rax, cs:__security_cookie
0x1800162fe  xor     rax, rsp
0x180016301  mov     [rbp+40h+var_40], rax
0x180016305  xor     r15d, r15d
0x180016308  mov     [rbp+40h+var_80], r9
0x18001630c  mov     r14, r9
0x18001630f  mov     rdi, r8
0x180016312  mov     rbx, rdx
0x180016315  mov     r13, rcx
0x180016318  test    rdx, rdx
0x18001631b  jz      loc_180016AE3
0x180016321  test    r8, r8
0x180016324  jz      loc_180016AE3
0x18001632a  test    r9, r9
0x18001632d  jz      loc_180016AE3
0x180016333  lea     rax, [rcx+18h]
0x180016337  mov     rcx, rax; this
0x18001633a  mov     [rbp+40h+lpCriticalSection], rax
0x18001633e  call    ?Lock@CComSafeDeleteCriticalSection@ATL@@QEAAJXZ; ATL::CComSafeDeleteCriticalSection::Lock(void)
0x180016343  lea     rcx, [rsp+140h+var_F0]; void *
0x180016348  call    ??0?$SmartComPtr@UIUPnPDescriptionManager@@@@QEAA@XZ; SmartComPtr<IUPnPDescriptionManager>::SmartComPtr<IUPnPDescriptionManager>(void)
0x18001634d  lea     rcx, [rsp+140h+var_108]; void *
0x180016352  call    ??0?$SmartComPtr@UIUPnPDescriptionManager@@@@QEAA@XZ; SmartComPtr<IUPnPDescriptionManager>::SmartComPtr<IUPnPDescriptionManager>(void)
0x180016357  lea     rcx, [rsp+140h+var_100]; void *
0x18001635c  mov     [rsp+140h+var_C8], r15
0x180016361  call    ??0?$SmartComPtr@UIUPnPDescriptionManager@@@@QEAA@XZ; SmartComPtr<IUPnPDescriptionManager>::SmartComPtr<IUPnPDescriptionManager>(void)
0x180016366  lea     rcx, [rsp+140h+var_F8]; void *
0x18001636b  call    ??0?$SmartComPtr@UIUPnPDescriptionManager@@@@QEAA@XZ; SmartComPtr<IUPnPDescriptionManager>::SmartComPtr<IUPnPDescriptionManager>(void)
0x180016370  lea     rcx, [rsp+140h+var_D0]; void *
0x180016375  call    ??0?$SmartComPtr@UIUPnPDescriptionManager@@@@QEAA@XZ; SmartComPtr<IUPnPDescriptionManager>::SmartComPtr<IUPnPDescriptionManager>(void)
0x18001637a  lea     rcx, [rsp+140h+var_D8]; void *
0x18001637f  call    ??0?$SmartComPtr@UIUPnPDescriptionManager@@@@QEAA@XZ; SmartComPtr<IUPnPDescriptionManager>::SmartComPtr<IUPnPDescriptionManager>(void)
0x180016384  lea     ecx, [r15+1]
0x180016388  call    ?HrIsAllowedCOMCallLocality@@YAJW4CALL_LOCALITY@@@Z; HrIsAllowedCOMCallLocality(CALL_LOCALITY)
0x18001638d  mov     esi, eax
0x18001638f  lea     rax, WPP_GLOBAL_Control
0x180016396  test    esi, esi
0x180016398  js      loc_18001695D
0x18001639e  mov     rcx, cs:WPP_GLOBAL_Control
0x1800163a5  cmp     rcx, rax
0x1800163a8  jz      short loc_1800163B4
0x1800163aa  test    byte ptr [rcx+1Ch], 40h
0x1800163ae  jnz     loc_1800168EB
0x1800163b4  lea     rdx, [rsp+140h+var_F0]
0x1800163b9  mov     rcx, rbx
0x1800163bc  call    ?HrLoadDocument@@YAJPEAGAEAV?$SmartComPtr@UIXMLDOMDocument@@@@PEBG@Z; HrLoadDocument(ushort *,SmartComPtr<IXMLDOMDocument> &,ushort const *)
0x1800163c1  mov     esi, eax
0x1800163c3  test    eax, eax
0x1800163c5  jns     loc_180016581
0x1800163cb  lea     rbx, WPP_GLOBAL_Control
0x1800163d2  test    esi, esi
0x1800163d4  jnz     loc_180016926
0x1800163da  mov     [rbp+40h+var_A0], r15
0x1800163de  xorps   xmm0, xmm0
0x1800163e1  mov     [rbp+40h+var_98], r15
0x1800163e5  mov     [rbp+40h+var_90], r15
0x1800163e9  mov     [rbp+40h+var_88], r15
0x1800163ed  mov     [rbp+40h+Block], r15
0x1800163f1  mov     [rbp+40h+var_B8], r15
0x1800163f5  mov     [rbp+40h+var_B0], r15
0x1800163f9  mov     [rbp+40h+var_A8], r15
0x1800163fd  movups  xmmword ptr [rbp+40h+var_50.Data1], xmm0
0x180016401  test    esi, esi
0x180016403  js      loc_1800164C7
0x180016409  cmp     [rbp+40h+arg_28], r15d
0x18001640d  jz      loc_180016969
0x180016413  movups  xmm0, xmmword ptr [r14]
0x180016417  lea     rcx, [rsp+140h+phkResult]; phkResult
0x18001641c  mov     [rsp+140h+hKey], r15
0x180016421  mov     [rsp+140h+phkResult], r15
0x180016426  movdqu  xmmword ptr [rbp+40h+var_50.Data1], xmm0
0x18001642b  call    ?HrCreateOrOpenDescriptionKey@@YAJPEAPEAUHKEY__@@@Z; HrCreateOrOpenDescriptionKey(HKEY__ * *)
0x180016430  mov     esi, eax
0x180016432  test    eax, eax
0x180016434  jns     loc_1800166A3
0x18001643a  test    esi, esi
0x18001643c  jnz     loc_1800169BB
0x180016442  mov     rdx, [rsp+140h+hKey]
0x180016447  lea     r8, [rbp+40h+var_A0]
0x18001644b  call    ?HrLD_ReadUDNMappings@CDescriptionManager@@AEAAJPEAUHKEY__@@AEAV?$CTable@VCUString@@V1@@@@Z; CDescriptionManager::HrLD_ReadUDNMappings(HKEY__ *,CTable<CUString,CUString> &)
0x180016450  mov     esi, eax
0x180016452  test    eax, eax
0x180016454  jns     loc_1800169F2
0x18001645a  mov     rcx, [rsp+140h+hKey]; hKey
0x18001645f  call    cs:__imp_RegCloseKey
0x180016465  test    esi, esi
0x180016467  js      short loc_1800164C7
0x180016469  lea     r9, [rbp+40h+Block]
0x18001646d  mov     r8, rdi
0x180016470  lea     rdx, [rsp+140h+var_D0]
0x180016475  call    ?HrPDT_ReplaceSCPDURLs@CDescriptionManager@@AEAAJAEAV?$SmartComPtr@UIXMLDOMNodeList@@@@PEBGAEAV?$CTable@U_GUID@@UFileInfo@@@@@Z; CDescriptionManager::HrPDT_ReplaceSCPDURLs(SmartComPtr<IXMLDOMNodeList> &,ushort const *,CTable<_GUID,FileInfo> &)
0x18001647a  mov     esi, eax
0x18001647c  test    eax, eax
0x18001647e  js      short loc_1800164C7
0x180016480  lea     r9, [rbp+40h+Block]
0x180016484  mov     r8, rdi
0x180016487  lea     rdx, [rsp+140h+var_D8]
0x18001648c  call    ?HrPDT_ReplaceIcons@CDescriptionManager@@AEAAJAEAV?$SmartComPtr@UIXMLDOMNodeList@@@@PEBGAEAV?$CTable@U_GUID@@UFileInfo@@@@@Z; CDescriptionManager::HrPDT_ReplaceIcons(SmartComPtr<IXMLDOMNodeList> &,ushort const *,CTable<_GUID,FileInfo> &)
0x180016491  mov     esi, eax
0x180016493  test    eax, eax
0x180016495  js      short loc_1800164C7
0x180016497  lea     rdx, [rsp+140h+var_100]
0x18001649c  call    ?HrPDT_ReplaceControlAndEventURLs@CDescriptionManager@@AEAAJAEAV?$SmartComPtr@UIXMLDOMNodeList@@@@@Z; CDescriptionManager::HrPDT_ReplaceControlAndEventURLs(SmartComPtr<IXMLDOMNodeList> &)
0x1800164a1  mov     esi, eax
0x1800164a3  test    eax, eax
0x1800164a5  js      short loc_1800164C7
0x1800164a7  mov     rcx, [rsp+140h+var_100]
0x1800164ac  mov     dword ptr [rsp+140h+phkResult], r15d
0x1800164b1  mov     rax, [rcx]
0x1800164b4  mov     rax, [rax+50h]
0x1800164b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800164bd  mov     esi, eax
0x1800164bf  test    eax, eax
0x1800164c1  jns     loc_180016A07
0x1800164c7  mov     rax, [r13+0]
0x1800164cb  lea     rdx, [rbp+40h+var_50]
0x1800164cf  xor     r8d, r8d
0x1800164d2  mov     rcx, r13
0x1800164d5  mov     rax, [rax+30h]
0x1800164d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800164de  test    esi, esi
0x1800164e0  jnz     loc_180016AA5
0x1800164e6  lea     rcx, [rbp+40h+var_B0]
0x1800164ea  call    ?Clear@?$CUArray@UFileInfo@@@@QEAAXXZ; CUArray<FileInfo>::Clear(void)
0x1800164ef  mov     rcx, [rbp+40h+Block]; Block
0x1800164f3  test    rcx, rcx
0x1800164f6  jz      short loc_1800164FE
0x1800164f8  call    cs:__imp_free
0x1800164fe  lea     rcx, [rbp+40h+var_90]
0x180016502  call    ?Clear@?$CUArray@VCUString@@@@QEAAXXZ; CUArray<CUString>::Clear(void)
0x180016507  lea     rcx, [rbp+40h+var_A0]
0x18001650b  call    ?Clear@?$CUArray@VCUString@@@@QEAAXXZ; CUArray<CUString>::Clear(void)
0x180016510  lea     rcx, [rsp+140h+var_D8]
0x180016515  call    ??1?$CComPtr@UIUPnPDescriptionManager@@@ATL@@QEAA@XZ; ATL::CComPtr<IUPnPDescriptionManager>::~CComPtr<IUPnPDescriptionManager>(void)
0x18001651a  lea     rcx, [rsp+140h+var_D0]
0x18001651f  call    ??1?$CComPtr@UIUPnPDescriptionManager@@@ATL@@QEAA@XZ; ATL::CComPtr<IUPnPDescriptionManager>::~CComPtr<IUPnPDescriptionManager>(void)
0x180016524  lea     rcx, [rsp+140h+var_F8]
0x180016529  call    ??1?$CComPtr@UIUPnPDescriptionManager@@@ATL@@QEAA@XZ; ATL::CComPtr<IUPnPDescriptionManager>::~CComPtr<IUPnPDescriptionManager>(void)
0x18001652e  lea     rcx, [rsp+140h+var_100]
0x180016533  call    ??1?$CComPtr@UIUPnPDescriptionManager@@@ATL@@QEAA@XZ; ATL::CComPtr<IUPnPDescriptionManager>::~CComPtr<IUPnPDescriptionManager>(void)
0x180016538  mov     rcx, [rsp+140h+var_C8]; Block
0x18001653d  call    cs:__imp_free
0x180016543  lea     rcx, [rsp+140h+var_108]
0x180016548  call    ??1?$CComPtr@UIUPnPDescriptionManager@@@ATL@@QEAA@XZ; ATL::CComPtr<IUPnPDescriptionManager>::~CComPtr<IUPnPDescriptionManager>(void)
0x18001654d  lea     rcx, [rsp+140h+var_F0]
0x180016552  call    ??1?$CComPtr@UIUPnPDescriptionManager@@@ATL@@QEAA@XZ; ATL::CComPtr<IUPnPDescriptionManager>::~CComPtr<IUPnPDescriptionManager>(void)
0x180016557  mov     rcx, [rbp+40h+lpCriticalSection]; lpCriticalSection
0x18001655b  call    cs:__imp_LeaveCriticalSection
0x180016561  mov     eax, esi
0x180016563  mov     rcx, [rbp+40h+var_40]
0x180016567  xor     rcx, rsp; StackCookie
0x18001656a  call    __security_check_cookie
0x18001656f  add     rsp, 110h
0x180016576  pop     r15
0x180016578  pop     r14
0x18001657a  pop     r13
0x18001657c  pop     rdi
0x18001657d  pop     rsi
0x18001657e  pop     rbx
0x18001657f  pop     rbp
0x180016580  retn
0x180016581  mov     rbx, [rsp+140h+var_F0]
0x180016586  lea     rcx, [rsp+140h+var_108]
0x18001658b  call    ?Release@?$CComPtrBase@UIUPnPDynamicContentSource@@@ATL@@QEAAXXZ; ATL::CComPtrBase<IUPnPDynamicContentSource>::Release(void)
0x180016590  mov     esi, 80004003h
0x180016595  test    rbx, rbx
0x180016598  jz      loc_18001691F
0x18001659e  mov     rax, [rbx]
0x1800165a1  lea     r8, [rsp+140h+var_108]
0x1800165a6  lea     rdx, _GUID_2933bf80_7b36_11d2_b20e_00c04f983e60
0x1800165ad  mov     rcx, rbx
0x1800165b0  mov     rax, [rax]
0x1800165b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800165b8  mov     esi, eax
0x1800165ba  test    eax, eax
0x1800165bc  js      loc_18001691F
0x1800165c2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800165c9  lea     rbx, WPP_GLOBAL_Control
0x1800165d0  cmp     rcx, rbx
0x1800165d3  jz      short loc_1800165DF
0x1800165d5  test    byte ptr [rcx+1Ch], 40h
0x1800165d9  jnz     loc_180016905
0x1800165df  lea     r8, [rsp+140h+var_C8]
0x1800165e4  lea     rdx, [rsp+140h+var_108]
0x1800165e9  lea     rcx, aDddRootDddDevi; "/ddd:root/ddd:device/ddd:UDN"
0x1800165f0  call    ?HrSelectNodeText@@YAJPEBGAEAV?$SmartComPtr@UIXMLDOMNode@@@@AEAVCUString@@@Z; HrSelectNodeText(ushort const *,SmartComPtr<IXMLDOMNode> &,CUString &)
0x1800165f5  mov     esi, eax
0x1800165f7  test    eax, eax
0x1800165f9  js      loc_1800163D2
0x1800165ff  mov     rcx, cs:WPP_GLOBAL_Control
0x180016606  cmp     rcx, rbx
0x180016609  jz      short loc_180016626
0x18001660b  test    byte ptr [rcx+1Ch], 40h
0x18001660f  jz      short loc_180016626
0x180016611  mov     rcx, [rcx+10h]
0x180016615  lea     r8, WPP_d1632e28abac3523b7923f2ce652edb2_Traceguids
0x18001661c  mov     edx, 19h
0x180016621  call    WPP_SF_
0x180016626  lea     r8, [rsp+140h+var_100]
0x18001662b  lea     rdx, [rsp+140h+var_108]
0x180016630  lea     rcx, aDddDevice; "//ddd:device"
0x180016637  call    ?HrSelectNodes@@YAJPEBGAEAV?$SmartComPtr@UIXMLDOMNode@@@@AEAV?$SmartComPtr@UIXMLDOMNodeList@@@@@Z; HrSelectNodes(ushort const *,SmartComPtr<IXMLDOMNode> &,SmartComPtr<IXMLDOMNodeList> &)
0x18001663c  mov     esi, eax
0x18001663e  test    eax, eax
0x180016640  js      loc_1800163D2
0x180016646  lea     r8, [rsp+140h+var_F8]
0x18001664b  lea     rdx, [rsp+140h+var_108]
0x180016650  lea     rcx, aDddUdn; "//ddd:UDN"
0x180016657  call    ?HrSelectNodes@@YAJPEBGAEAV?$SmartComPtr@UIXMLDOMNode@@@@AEAV?$SmartComPtr@UIXMLDOMNodeList@@@@@Z; HrSelectNodes(ushort const *,SmartComPtr<IXMLDOMNode> &,SmartComPtr<IXMLDOMNodeList> &)
0x18001665c  mov     esi, eax
0x18001665e  test    eax, eax
0x180016660  js      loc_1800163D2
0x180016666  lea     r8, [rsp+140h+var_D0]
0x18001666b  lea     rdx, [rsp+140h+var_108]
0x180016670  lea     rcx, aDddScpdurl_0; "//ddd:SCPDURL"
0x180016677  call    ?HrSelectNodes@@YAJPEBGAEAV?$SmartComPtr@UIXMLDOMNode@@@@AEAV?$SmartComPtr@UIXMLDOMNodeList@@@@@Z; HrSelectNodes(ushort const *,SmartComPtr<IXMLDOMNode> &,SmartComPtr<IXMLDOMNodeList> &)
0x18001667c  mov     esi, eax
0x18001667e  test    eax, eax
0x180016680  js      loc_1800163D2
0x180016686  lea     r8, [rsp+140h+var_D8]
0x18001668b  lea     rdx, [rsp+140h+var_108]
0x180016690  lea     rcx, aDddIcon; "//ddd:icon"
0x180016697  call    ?HrSelectNodes@@YAJPEBGAEAV?$SmartComPtr@UIXMLDOMNode@@@@AEAV?$SmartComPtr@UIXMLDOMNodeList@@@@@Z; HrSelectNodes(ushort const *,SmartComPtr<IXMLDOMNode> &,SmartComPtr<IXMLDOMNodeList> &)
0x18001669c  mov     esi, eax
0x18001669e  jmp     loc_1800163D2
0x1800166a3  lea     rdx, [rbp+40h+var_50]; struct _GUID *
0x1800166a7  mov     [rsp+140h+var_E8], r15
0x1800166ac  lea     rcx, [rsp+140h+var_E8]; this
0x1800166b1  call    ?HrInitFromGUID@CUString@@QEAAJAEBU_GUID@@@Z; CUString::HrInitFromGUID(_GUID const &)
0x1800166b6  mov     esi, eax
0x1800166b8  test    eax, eax
0x1800166ba  jns     loc_18001699A
0x1800166c0  mov     rcx, [rsp+140h+phkResult]; hKey
0x1800166c5  call    cs:__imp_RegCloseKey
0x1800166cb  mov     rcx, [rsp+140h+var_E8]; Block
0x1800166d0  call    cs:__imp_free
0x1800166d6  jmp     loc_18001643A
0x1800166db  lea     rdi, [r14+10h]
0x1800166df  mov     rax, [rdi]
0x1800166e2  lea     rcx, [rax+r8*8]
0x1800166e6  test    rcx, rcx
0x1800166e9  jz      short loc_180016726
0x1800166eb  mov     rax, [rsp+140h+phkResult]
0x1800166f0  mov     [rcx], rax
0x1800166f3  mov     esi, r15d
0x1800166f6  mov     rcx, rbx; lpCriticalSection
0x1800166f9  call    cs:__imp_LeaveCriticalSection
0x1800166ff  test    esi, esi
0x180016701  js      loc_180016A95
0x180016707  cmp     [rbp+40h+arg_28], r15d
0x18001670b  jnz     loc_1800164DE
0x180016711  mov     rax, [rbp+40h+var_80]
0x180016715  movups  xmm0, xmmword ptr [rbp+40h+var_50.Data1]
0x180016719  movdqu  xmmword ptr [rax], xmm0
0x18001671d  jmp     loc_1800164DE
0x180016722  lea     rdi, [r14+10h]
0x180016726  lea     rdx, [rbp+40h+var_50]
0x18001672a  mov     rcx, r14
0x18001672d  call    ?HrPushBack@?$CUArray@U_GUID@@@@QEAAJAEBU_GUID@@@Z; CUArray<_GUID>::HrPushBack(_GUID const &)
0x180016732  mov     esi, eax
0x180016734  test    eax, eax
0x180016736  js      short loc_1800166F6
0x180016738  mov     edx, [rdi+0Ch]
0x18001673b  cmp     [rdi+8], edx
0x18001673e  jz      short loc_180016755
0x180016740  movsxd  rdx, dword ptr [rdi+8]
0x180016744  mov     rcx, [rdi]
0x180016747  mov     rax, [rsp+140h+phkResult]
0x18001674c  mov     [rcx+rdx*8], rax
0x180016750  inc     dword ptr [rdi+8]
0x180016753  jmp     short loc_1800166F3
0x180016755  add     edx, 32h ; '2'
0x180016758  mov     rcx, rdi
0x18001675b  call    ?HrSetReserve@?$CUArray@PEAG@@QEAAJJ@Z; CUArray<ushort *>::HrSetReserve(long)
0x180016760  mov     esi, eax
0x180016762  test    eax, eax
0x180016764  jns     short loc_180016740
0x180016766  mov     rcx, r14
0x180016769  call    ?HrPopBack@?$CUArray@U_GUID@@@@QEAAJXZ; CUArray<_GUID>::HrPopBack(void)
0x18001676e  jmp     short loc_1800166F6
0x180016770  lea     rbx, [r13+238h]
0x180016777  mov     rcx, rbx; lpCriticalSection
0x18001677a  call    cs:__imp_EnterCriticalSection
0x180016780  mov     r14d, dword ptr [rbp+40h+var_B8]
0x180016784  xorps   xmm0, xmm0
0x180016787  mov     edi, r15d
0x18001678a  movdqu  [rbp+40h+var_60], xmm0
0x18001678f  movups  xmm0, xmmword ptr [rbp+40h+var_50.Data1]
0x180016793  movdqu  [rbp+40h+var_70], xmm0
0x180016798  test    r14d, r14d
0x18001679b  jg      loc_180016868
  ... truncated ...
```
