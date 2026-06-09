# CDescriptionManager::ProcessDescriptionTemplate(ushort *,ushort const *,_GUID *,int,int)

- ea: `0x18000a5f0`
- end: `0x18000ae58`
- name: `?ProcessDescriptionTemplate@CDescriptionManager@@UEAAJPEAGPEBGPEAU_GUID@@HH@Z`
- size: `2152`
- prototype: `int(CDescriptionManager *__hidden this, unsigned __int16 *, const unsigned __int16 *, struct _GUID *, int, int)`
- caller_count: `0`
- callee_count: `35`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180003e08`
- `0x1800056d8`
- `0x1800056f0`
- `0x180005708`
- `0x1800071c0`
- `0x180009d50`
- `0x18000a5f0`
- `0x18000aff0`
- `0x18000bb00`
- `0x18000c904`
- `0x18000de40`
- `0x18000fb0c`
- `0x180010d88`
- `0x180011a48`
- `0x1800127ec`
- `0x180024cb0`
- `0x180025034`
- `0x18002a1e0`
- `0x18002c534`
- `0x18002c638`
- `0x18002cd00`
- `0x180030340`
- `0x180030ba4`
- `0x180031534`
- `0x180033180`
- `0x180034d54`
- `0x18003a30c`
- `0x18003b1cc`
- `0x18003c018`
- `0x18003cb60`
- `0x180042774`
- `0x18004cc70`
- `0x18004d758`
- `0x18004d82c`
- `0x180059010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000a80e`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000a859`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000a9ff`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000a80e`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000a859`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000a9ff`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000aab5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000ab15`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000ab79`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000aab5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000ab15`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000ab79`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000a87d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000aa2e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000aaf7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000ab3a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000a87d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000aa2e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000aaf7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000ab3a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000a76f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000a9ee`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000a76f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000a9ee`
- `OLEAUT32!__imp_SysAllocString` at `0x18000ad87`
- `OLEAUT32!__imp_SysAllocString` at `0x18000ad87`
- `OLEAUT32!__imp_SysFreeString` at `0x18000adb6`
- `OLEAUT32!__imp_SysFreeString` at `0x18000adff`
- `OLEAUT32!__imp_SysFreeString` at `0x18000adb6`
- `OLEAUT32!__imp_SysFreeString` at `0x18000adff`

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
  char v39[8]; // [rsp+48h] [rbp-B8h] BYREF
  __int64 (__fastcall ***v40)(LPVOID, GUID *, __int64 *); // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int16 *v41; // [rsp+58h] [rbp-A8h] BYREF
  HKEY hKey; // [rsp+60h] [rbp-A0h] BYREF
  char v43[8]; // [rsp+68h] [rbp-98h] BYREF
  char v44[8]; // [rsp+70h] [rbp-90h] BYREF
  void *v45; // [rsp+78h] [rbp-88h] BYREF
  void *Block; // [rsp+80h] [rbp-80h] BYREF
  __int64 v47; // [rsp+88h] [rbp-78h]
  _QWORD v48[2]; // [rsp+90h] [rbp-70h] BYREF
  __int64 v49[2]; // [rsp+A0h] [rbp-60h] BYREF
  _QWORD v50[2]; // [rsp+B0h] [rbp-50h] BYREF
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
  SmartComPtr<IUPnPDescriptionManager>::SmartComPtr<IUPnPDescriptionManager>(v39);
  SmartComPtr<IUPnPDescriptionManager>::SmartComPtr<IUPnPDescriptionManager>(v44);
  SmartComPtr<IUPnPDescriptionManager>::SmartComPtr<IUPnPDescriptionManager>(v43);
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
          IsAllowedCOMCallLocality = HrSelectNodes(L"//ddd:UDN", &v37, v39);
          if ( IsAllowedCOMCallLocality >= 0 )
          {
            IsAllowedCOMCallLocality = HrSelectNodes(L"//ddd:SCPDURL", &v37, v44);
            if ( IsAllowedCOMCallLocality >= 0 )
              IsAllowedCOMCallLocality = HrSelectNodes(L"//ddd:icon", &v37, v43);
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
        IsAllowedCOMCallLocality = CDescriptionManager::HrPDT_ReregisterUDNsInDescriptionDocument(v15, v49, v39);
      RegCloseKey(hKey);
    }
    else
    {
      IsAllowedCOMCallLocality = CDescriptionManager::HrPDT_DoUDNToUDNMapping(v10, v39, v49);
      if ( IsAllowedCOMCallLocality < 0 )
        goto LABEL_22;
      IsAllowedCOMCallLocality = CDescriptionManager::HrPDT_FetchPhysicalIdentifier(v32, v49, &v45, &v55);
    }
    if ( IsAllowedCOMCallLocality < 0 )
      goto LABEL_22;
    IsAllowedCOMCallLocality = CDescriptionManager::HrPDT_ReplaceSCPDURLs(v16, (__int64)v44, a3, (__int64)&Block);
    if ( IsAllowedCOMCallLocality < 0 )
      goto LABEL_22;
    IsAllowedCOMCallLocality = CDescriptionManager::HrPDT_ReplaceIcons(v17, (__int64)v43, a3, (__int64)&Block);
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
              IsAllowedCOMCallLocality = CUArray<_GUID>::HrPushBack((char *)this + 72);
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
  ATL::CComPtr<IUPnPDescriptionManager>::~CComPtr<IUPnPDescriptionManager>(v43);
  ATL::CComPtr<IUPnPDescriptionManager>::~CComPtr<IUPnPDescriptionManager>(v44);
  ATL::CComPtr<IUPnPDescriptionManager>::~CComPtr<IUPnPDescriptionManager>(v39);
  ATL::CComPtr<IUPnPDescriptionManager>::~CComPtr<IUPnPDescriptionManager>(&v38);
  free(v45);
  ATL::CComPtr<IUPnPDescriptionManager>::~CComPtr<IUPnPDescriptionManager>(&v37);
  ATL::CComPtr<IUPnPDescriptionManager>::~CComPtr<IUPnPDescriptionManager>(&v40);
  LeaveCriticalSection(lpCriticalSection);
  return (unsigned int)IsAllowedCOMCallLocality;
}

```

## disassembly

```asm
0x18000a5f0  push    rbp
0x18000a5f2  push    rbx
0x18000a5f3  push    rsi
0x18000a5f4  push    rdi
0x18000a5f5  push    r13
0x18000a5f7  push    r14
0x18000a5f9  push    r15
0x18000a5fb  lea     rbp, [rsp-10h]
0x18000a600  sub     rsp, 110h
0x18000a607  mov     rax, cs:__security_cookie
0x18000a60e  xor     rax, rsp
0x18000a611  mov     [rbp+40h+var_40], rax
0x18000a615  xor     r15d, r15d
0x18000a618  mov     [rbp+40h+var_80], r9
0x18000a61c  mov     r14, r9
0x18000a61f  mov     rdi, r8
0x18000a622  mov     rbx, rdx
0x18000a625  mov     r13, rcx
0x18000a628  test    rdx, rdx
0x18000a62b  jz      loc_18000AE4E
0x18000a631  test    r8, r8
0x18000a634  jz      loc_18000AE4E
0x18000a63a  test    r9, r9
0x18000a63d  jz      loc_18000AE4E
0x18000a643  lea     rax, [rcx+18h]
0x18000a647  mov     rcx, rax; this
0x18000a64a  mov     [rbp+40h+lpCriticalSection], rax
0x18000a64e  call    ?Lock@CComSafeDeleteCriticalSection@ATL@@QEAAJXZ; ATL::CComSafeDeleteCriticalSection::Lock(void)
0x18000a653  lea     rcx, [rsp+140h+var_F0]; void *
0x18000a658  call    ??0?$SmartComPtr@UIUPnPDescriptionManager@@@@QEAA@XZ; SmartComPtr<IUPnPDescriptionManager>::SmartComPtr<IUPnPDescriptionManager>(void)
0x18000a65d  lea     rcx, [rsp+140h+var_108]; void *
0x18000a662  call    ??0?$SmartComPtr@UIUPnPDescriptionManager@@@@QEAA@XZ; SmartComPtr<IUPnPDescriptionManager>::SmartComPtr<IUPnPDescriptionManager>(void)
0x18000a667  lea     rcx, [rsp+140h+var_100]; void *
0x18000a66c  mov     [rsp+140h+var_C8], r15
0x18000a671  call    ??0?$SmartComPtr@UIUPnPDescriptionManager@@@@QEAA@XZ; SmartComPtr<IUPnPDescriptionManager>::SmartComPtr<IUPnPDescriptionManager>(void)
0x18000a676  lea     rcx, [rsp+140h+var_F8]; void *
0x18000a67b  call    ??0?$SmartComPtr@UIUPnPDescriptionManager@@@@QEAA@XZ; SmartComPtr<IUPnPDescriptionManager>::SmartComPtr<IUPnPDescriptionManager>(void)
0x18000a680  lea     rcx, [rsp+140h+var_D0]; void *
0x18000a685  call    ??0?$SmartComPtr@UIUPnPDescriptionManager@@@@QEAA@XZ; SmartComPtr<IUPnPDescriptionManager>::SmartComPtr<IUPnPDescriptionManager>(void)
0x18000a68a  lea     rcx, [rsp+140h+var_D8]; void *
0x18000a68f  call    ??0?$SmartComPtr@UIUPnPDescriptionManager@@@@QEAA@XZ; SmartComPtr<IUPnPDescriptionManager>::SmartComPtr<IUPnPDescriptionManager>(void)
0x18000a694  lea     ecx, [r15+1]
0x18000a698  call    ?HrIsAllowedCOMCallLocality@@YAJW4CALL_LOCALITY@@@Z; HrIsAllowedCOMCallLocality(CALL_LOCALITY)
0x18000a69d  mov     esi, eax
0x18000a69f  lea     rax, WPP_GLOBAL_Control
0x18000a6a6  test    esi, esi
0x18000a6a8  js      loc_18000ACB6
0x18000a6ae  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a6b5  cmp     rcx, rax
0x18000a6b8  jz      short loc_18000A6C4
0x18000a6ba  test    byte ptr [rcx+1Ch], 40h
0x18000a6be  jnz     loc_18000AC44
0x18000a6c4  lea     rdx, [rsp+140h+var_F0]
0x18000a6c9  mov     rcx, rbx
0x18000a6cc  call    ?HrLoadDocument@@YAJPEAGAEAV?$SmartComPtr@UIXMLDOMDocument@@@@PEBG@Z; HrLoadDocument(ushort *,SmartComPtr<IXMLDOMDocument> &,ushort const *)
0x18000a6d1  mov     esi, eax
0x18000a6d3  test    eax, eax
0x18000a6d5  jns     loc_18000A8AA
0x18000a6db  lea     rbx, WPP_GLOBAL_Control
0x18000a6e2  test    esi, esi
0x18000a6e4  jnz     loc_18000AC7F
0x18000a6ea  mov     [rbp+40h+var_A0], r15
0x18000a6ee  xorps   xmm0, xmm0
0x18000a6f1  mov     [rbp+40h+var_98], r15
0x18000a6f5  mov     [rbp+40h+var_90], r15
0x18000a6f9  mov     [rbp+40h+var_88], r15
0x18000a6fd  mov     [rbp+40h+Block], r15
0x18000a701  mov     [rbp+40h+var_B8], r15
0x18000a705  mov     [rbp+40h+var_B0], r15
0x18000a709  mov     [rbp+40h+var_A8], r15
0x18000a70d  movups  xmmword ptr [rbp+40h+var_50.Data1], xmm0
0x18000a711  test    esi, esi
0x18000a713  js      loc_18000A7DD
0x18000a719  cmp     [rbp+40h+arg_28], r15d
0x18000a71d  jz      loc_18000ACC2
0x18000a723  movups  xmm0, xmmword ptr [r14]
0x18000a727  lea     rcx, [rsp+140h+phkResult]; phkResult
0x18000a72c  mov     [rsp+140h+hKey], r15
0x18000a731  mov     [rsp+140h+phkResult], r15
0x18000a736  movdqu  xmmword ptr [rbp+40h+var_50.Data1], xmm0
0x18000a73b  call    ?HrCreateOrOpenDescriptionKey@@YAJPEAPEAUHKEY__@@@Z; HrCreateOrOpenDescriptionKey(HKEY__ * *)
0x18000a740  mov     esi, eax
0x18000a742  test    eax, eax
0x18000a744  jns     loc_18000A9CC
0x18000a74a  test    esi, esi
0x18000a74c  jnz     loc_18000AD14
0x18000a752  mov     rdx, [rsp+140h+hKey]
0x18000a757  lea     r8, [rbp+40h+var_A0]
0x18000a75b  call    ?HrLD_ReadUDNMappings@CDescriptionManager@@AEAAJPEAUHKEY__@@AEAV?$CTable@VCUString@@V1@@@@Z; CDescriptionManager::HrLD_ReadUDNMappings(HKEY__ *,CTable<CUString,CUString> &)
0x18000a760  mov     esi, eax
0x18000a762  test    eax, eax
0x18000a764  jns     loc_18000AD4B
0x18000a76a  mov     rcx, [rsp+140h+hKey]; hKey
0x18000a76f  call    cs:__imp_RegCloseKey
0x18000a776  nop     dword ptr [rax+rax+00h]
0x18000a77b  test    esi, esi
0x18000a77d  js      short loc_18000A7DD
0x18000a77f  lea     r9, [rbp+40h+Block]
0x18000a783  mov     r8, rdi
0x18000a786  lea     rdx, [rsp+140h+var_D0]
0x18000a78b  call    ?HrPDT_ReplaceSCPDURLs@CDescriptionManager@@AEAAJAEAV?$SmartComPtr@UIXMLDOMNodeList@@@@PEBGAEAV?$CTable@U_GUID@@UFileInfo@@@@@Z; CDescriptionManager::HrPDT_ReplaceSCPDURLs(SmartComPtr<IXMLDOMNodeList> &,ushort const *,CTable<_GUID,FileInfo> &)
0x18000a790  mov     esi, eax
0x18000a792  test    eax, eax
0x18000a794  js      short loc_18000A7DD
0x18000a796  lea     r9, [rbp+40h+Block]
0x18000a79a  mov     r8, rdi
0x18000a79d  lea     rdx, [rsp+140h+var_D8]
0x18000a7a2  call    ?HrPDT_ReplaceIcons@CDescriptionManager@@AEAAJAEAV?$SmartComPtr@UIXMLDOMNodeList@@@@PEBGAEAV?$CTable@U_GUID@@UFileInfo@@@@@Z; CDescriptionManager::HrPDT_ReplaceIcons(SmartComPtr<IXMLDOMNodeList> &,ushort const *,CTable<_GUID,FileInfo> &)
0x18000a7a7  mov     esi, eax
0x18000a7a9  test    eax, eax
0x18000a7ab  js      short loc_18000A7DD
0x18000a7ad  lea     rdx, [rsp+140h+var_100]
0x18000a7b2  call    ?HrPDT_ReplaceControlAndEventURLs@CDescriptionManager@@AEAAJAEAV?$SmartComPtr@UIXMLDOMNodeList@@@@@Z; CDescriptionManager::HrPDT_ReplaceControlAndEventURLs(SmartComPtr<IXMLDOMNodeList> &)
0x18000a7b7  mov     esi, eax
0x18000a7b9  test    eax, eax
0x18000a7bb  js      short loc_18000A7DD
0x18000a7bd  mov     rcx, [rsp+140h+var_100]
0x18000a7c2  mov     dword ptr [rsp+140h+phkResult], r15d
0x18000a7c7  mov     rax, [rcx]
0x18000a7ca  mov     rax, [rax+50h]
0x18000a7ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a7d3  mov     esi, eax
0x18000a7d5  test    eax, eax
0x18000a7d7  jns     loc_18000AD60
0x18000a7dd  mov     rax, [r13+0]
0x18000a7e1  lea     rdx, [rbp+40h+var_50]
0x18000a7e5  xor     r8d, r8d
0x18000a7e8  mov     rcx, r13
0x18000a7eb  mov     rax, [rax+30h]
0x18000a7ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a7f4  test    esi, esi
0x18000a7f6  jnz     loc_18000AE10
0x18000a7fc  lea     rcx, [rbp+40h+var_B0]
0x18000a800  call    ?Clear@?$CUArray@UFileInfo@@@@QEAAXXZ; CUArray<FileInfo>::Clear(void)
0x18000a805  mov     rcx, [rbp+40h+Block]; Block
0x18000a809  test    rcx, rcx
0x18000a80c  jz      short loc_18000A81A
0x18000a80e  call    cs:__imp_free
0x18000a815  nop     dword ptr [rax+rax+00h]
0x18000a81a  lea     rcx, [rbp+40h+var_90]
0x18000a81e  call    ?Clear@?$CUArray@VCUString@@@@QEAAXXZ; CUArray<CUString>::Clear(void)
0x18000a823  lea     rcx, [rbp+40h+var_A0]
0x18000a827  call    ?Clear@?$CUArray@VCUString@@@@QEAAXXZ; CUArray<CUString>::Clear(void)
0x18000a82c  lea     rcx, [rsp+140h+var_D8]
0x18000a831  call    ??1?$CComPtr@UIUPnPDescriptionManager@@@ATL@@QEAA@XZ; ATL::CComPtr<IUPnPDescriptionManager>::~CComPtr<IUPnPDescriptionManager>(void)
0x18000a836  lea     rcx, [rsp+140h+var_D0]
0x18000a83b  call    ??1?$CComPtr@UIUPnPDescriptionManager@@@ATL@@QEAA@XZ; ATL::CComPtr<IUPnPDescriptionManager>::~CComPtr<IUPnPDescriptionManager>(void)
0x18000a840  lea     rcx, [rsp+140h+var_F8]
0x18000a845  call    ??1?$CComPtr@UIUPnPDescriptionManager@@@ATL@@QEAA@XZ; ATL::CComPtr<IUPnPDescriptionManager>::~CComPtr<IUPnPDescriptionManager>(void)
0x18000a84a  lea     rcx, [rsp+140h+var_100]
0x18000a84f  call    ??1?$CComPtr@UIUPnPDescriptionManager@@@ATL@@QEAA@XZ; ATL::CComPtr<IUPnPDescriptionManager>::~CComPtr<IUPnPDescriptionManager>(void)
0x18000a854  mov     rcx, [rsp+140h+var_C8]; Block
0x18000a859  call    cs:__imp_free
0x18000a860  nop     dword ptr [rax+rax+00h]
0x18000a865  lea     rcx, [rsp+140h+var_108]
0x18000a86a  call    ??1?$CComPtr@UIUPnPDescriptionManager@@@ATL@@QEAA@XZ; ATL::CComPtr<IUPnPDescriptionManager>::~CComPtr<IUPnPDescriptionManager>(void)
0x18000a86f  lea     rcx, [rsp+140h+var_F0]
0x18000a874  call    ??1?$CComPtr@UIUPnPDescriptionManager@@@ATL@@QEAA@XZ; ATL::CComPtr<IUPnPDescriptionManager>::~CComPtr<IUPnPDescriptionManager>(void)
0x18000a879  mov     rcx, [rbp+40h+lpCriticalSection]; lpCriticalSection
0x18000a87d  call    cs:__imp_LeaveCriticalSection
0x18000a884  nop     dword ptr [rax+rax+00h]
0x18000a889  mov     eax, esi
0x18000a88b  mov     rcx, [rbp+40h+var_40]
0x18000a88f  xor     rcx, rsp; StackCookie
0x18000a892  call    __security_check_cookie
0x18000a897  add     rsp, 110h
0x18000a89e  pop     r15
0x18000a8a0  pop     r14
0x18000a8a2  pop     r13
0x18000a8a4  pop     rdi
0x18000a8a5  pop     rsi
0x18000a8a6  pop     rbx
0x18000a8a7  pop     rbp
0x18000a8a8  retn
0x18000a8aa  mov     rbx, [rsp+140h+var_F0]
0x18000a8af  lea     rcx, [rsp+140h+var_108]
0x18000a8b4  call    ?Release@?$CComPtrBase@UIUPnPDynamicContentSource@@@ATL@@QEAAXXZ; ATL::CComPtrBase<IUPnPDynamicContentSource>::Release(void)
0x18000a8b9  mov     esi, 80004003h
0x18000a8be  test    rbx, rbx
0x18000a8c1  jz      loc_18000AC78
0x18000a8c7  mov     rax, [rbx]
0x18000a8ca  lea     r8, [rsp+140h+var_108]
0x18000a8cf  lea     rdx, _GUID_2933bf80_7b36_11d2_b20e_00c04f983e60
0x18000a8d6  mov     rcx, rbx
0x18000a8d9  mov     rax, [rax]
0x18000a8dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a8e1  mov     esi, eax
0x18000a8e3  test    eax, eax
0x18000a8e5  js      loc_18000AC78
0x18000a8eb  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a8f2  lea     rbx, WPP_GLOBAL_Control
0x18000a8f9  cmp     rcx, rbx
0x18000a8fc  jz      short loc_18000A908
0x18000a8fe  test    byte ptr [rcx+1Ch], 40h
0x18000a902  jnz     loc_18000AC5E
0x18000a908  lea     r8, [rsp+140h+var_C8]
0x18000a90d  lea     rdx, [rsp+140h+var_108]
0x18000a912  lea     rcx, aDddRootDddDevi; "/ddd:root/ddd:device/ddd:UDN"
0x18000a919  call    ?HrSelectNodeText@@YAJPEBGAEAV?$SmartComPtr@UIXMLDOMNode@@@@AEAVCUString@@@Z; HrSelectNodeText(ushort const *,SmartComPtr<IXMLDOMNode> &,CUString &)
0x18000a91e  mov     esi, eax
0x18000a920  test    eax, eax
0x18000a922  js      loc_18000A6E2
0x18000a928  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a92f  cmp     rcx, rbx
0x18000a932  jz      short loc_18000A94F
0x18000a934  test    byte ptr [rcx+1Ch], 40h
0x18000a938  jz      short loc_18000A94F
0x18000a93a  mov     rcx, [rcx+10h]
0x18000a93e  lea     r8, WPP_d1632e28abac3523b7923f2ce652edb2_Traceguids
0x18000a945  mov     edx, 19h
0x18000a94a  call    WPP_SF_
0x18000a94f  lea     r8, [rsp+140h+var_100]
0x18000a954  lea     rdx, [rsp+140h+var_108]
0x18000a959  lea     rcx, aDddDevice; "//ddd:device"
0x18000a960  call    ?HrSelectNodes@@YAJPEBGAEAV?$SmartComPtr@UIXMLDOMNode@@@@AEAV?$SmartComPtr@UIXMLDOMNodeList@@@@@Z; HrSelectNodes(ushort const *,SmartComPtr<IXMLDOMNode> &,SmartComPtr<IXMLDOMNodeList> &)
0x18000a965  mov     esi, eax
0x18000a967  test    eax, eax
0x18000a969  js      loc_18000A6E2
0x18000a96f  lea     r8, [rsp+140h+var_F8]
0x18000a974  lea     rdx, [rsp+140h+var_108]
0x18000a979  lea     rcx, aDddUdn; "//ddd:UDN"
0x18000a980  call    ?HrSelectNodes@@YAJPEBGAEAV?$SmartComPtr@UIXMLDOMNode@@@@AEAV?$SmartComPtr@UIXMLDOMNodeList@@@@@Z; HrSelectNodes(ushort const *,SmartComPtr<IXMLDOMNode> &,SmartComPtr<IXMLDOMNodeList> &)
0x18000a985  mov     esi, eax
0x18000a987  test    eax, eax
0x18000a989  js      loc_18000A6E2
0x18000a98f  lea     r8, [rsp+140h+var_D0]
0x18000a994  lea     rdx, [rsp+140h+var_108]
0x18000a999  lea     rcx, aDddScpdurl_0; "//ddd:SCPDURL"
0x18000a9a0  call    ?HrSelectNodes@@YAJPEBGAEAV?$SmartComPtr@UIXMLDOMNode@@@@AEAV?$SmartComPtr@UIXMLDOMNodeList@@@@@Z; HrSelectNodes(ushort const *,SmartComPtr<IXMLDOMNode> &,SmartComPtr<IXMLDOMNodeList> &)
0x18000a9a5  mov     esi, eax
0x18000a9a7  test    eax, eax
0x18000a9a9  js      loc_18000A6E2
0x18000a9af  lea     r8, [rsp+140h+var_D8]
0x18000a9b4  lea     rdx, [rsp+140h+var_108]
0x18000a9b9  lea     rcx, aDddIcon; "//ddd:icon"
0x18000a9c0  call    ?HrSelectNodes@@YAJPEBGAEAV?$SmartComPtr@UIXMLDOMNode@@@@AEAV?$SmartComPtr@UIXMLDOMNodeList@@@@@Z; HrSelectNodes(ushort const *,SmartComPtr<IXMLDOMNode> &,SmartComPtr<IXMLDOMNodeList> &)
0x18000a9c5  mov     esi, eax
0x18000a9c7  jmp     loc_18000A6E2
0x18000a9cc  lea     rdx, [rbp+40h+var_50]; struct _GUID *
0x18000a9d0  mov     [rsp+140h+var_E8], r15
0x18000a9d5  lea     rcx, [rsp+140h+var_E8]; this
0x18000a9da  call    ?HrInitFromGUID@CUString@@QEAAJAEBU_GUID@@@Z; CUString::HrInitFromGUID(_GUID const &)
0x18000a9df  mov     esi, eax
0x18000a9e1  test    eax, eax
0x18000a9e3  jns     loc_18000ACF3
0x18000a9e9  mov     rcx, [rsp+140h+phkResult]; hKey
0x18000a9ee  call    cs:__imp_RegCloseKey
0x18000a9f5  nop     dword ptr [rax+rax+00h]
0x18000a9fa  mov     rcx, [rsp+140h+var_E8]; Block
0x18000a9ff  call    cs:__imp_free
0x18000aa06  nop     dword ptr [rax+rax+00h]
0x18000aa0b  jmp     loc_18000A74A
0x18000aa10  lea     rdi, [r14+10h]
0x18000aa14  mov     rax, [rdi]
0x18000aa17  lea     rcx, [rax+r8*8]
0x18000aa1b  test    rcx, rcx
0x18000aa1e  jz      short loc_18000AA61
0x18000aa20  mov     rax, [rsp+140h+phkResult]
0x18000aa25  mov     [rcx], rax
0x18000aa28  mov     esi, r15d
0x18000aa2b  mov     rcx, rbx; lpCriticalSection
0x18000aa2e  call    cs:__imp_LeaveCriticalSection
0x18000aa35  nop     dword ptr [rax+rax+00h]
0x18000aa3a  test    esi, esi
0x18000aa3c  js      loc_18000ADFA
0x18000aa42  cmp     [rbp+40h+arg_28], r15d
0x18000aa46  jnz     loc_18000A7F4
0x18000aa4c  mov     rax, [rbp+40h+var_80]
0x18000aa50  movups  xmm0, xmmword ptr [rbp+40h+var_50.Data1]
0x18000aa54  movdqu  xmmword ptr [rax], xmm0
0x18000aa58  jmp     loc_18000A7F4
0x18000aa5d  lea     rdi, [r14+10h]
0x18000aa61  lea     rdx, [rbp+40h+var_50]
0x18000aa65  mov     rcx, r14
0x18000aa68  call    ?HrPushBack@?$CUArray@U_GUID@@@@QEAAJAEBU_GUID@@@Z; CUArray<_GUID>::HrPushBack(_GUID const &)
0x18000aa6d  mov     esi, eax
0x18000aa6f  test    eax, eax
0x18000aa71  js      short loc_18000AA2B
0x18000aa73  mov     edx, [rdi+0Ch]
0x18000aa76  cmp     [rdi+8], edx
0x18000aa79  jz      short loc_18000AA90
0x18000aa7b  movsxd  rdx, dword ptr [rdi+8]
0x18000aa7f  mov     rcx, [rdi]
0x18000aa82  mov     rax, [rsp+140h+phkResult]
0x18000aa87  mov     [rcx+rdx*8], rax
0x18000aa8b  inc     dword ptr [rdi+8]
0x18000aa8e  jmp     short loc_18000AA28
0x18000aa90  add     edx, 32h ; '2'
0x18000aa93  mov     rcx, rdi
0x18000aa96  call    ?HrSetReserve@?$CUArray@PEAG@@QEAAJJ@Z; CUArray<ushort *>::HrSetReserve(long)
0x18000aa9b  mov     esi, eax
0x18000aa9d  test    eax, eax
0x18000aa9f  jns     short loc_18000AA7B
0x18000aaa1  mov     rcx, r14
0x18000aaa4  call    ?HrPopBack@?$CUArray@U_GUID@@@@QEAAJXZ; CUArray<_GUID>::HrPopBack(void)
0x18000aaa9  jmp     short loc_18000AA2B
0x18000aaab  lea     rbx, [r13+238h]
0x18000aab2  mov     rcx, rbx; lpCriticalSection
0x18000aab5  call    cs:__imp_EnterCriticalSection
0x18000aabc  nop     dword ptr [rax+rax+00h]
  ... truncated ...
```
