# CDescriptionManager::PublishDescription(_GUID const &,long)

- ea: `0x18000f750`
- end: `0x18000fdee`
- name: `?PublishDescription@CDescriptionManager@@UEAAJAEBU_GUID@@J@Z`
- size: `1694`
- prototype: `__int64 __fastcall(CDescriptionManager *__hidden this, const struct _GUID *, int)`
- caller_count: `0`
- callee_count: `33`
- tags: `file_ops, service_task, broker_com_uri`

## callees

- `0x18000f1bc`
- `0x18000f21c`
- `0x18000f348`
- `0x18000f4d8`
- `0x18000f51c`
- `0x18000f750`
- `0x18000fdf4`
- `0x180010660`
- `0x18001169c`
- `0x1800117bc`
- `0x1800117d0`
- `0x180013180`
- `0x1800144e4`
- `0x180015ab0`
- `0x180015d90`
- `0x180016af4`
- `0x180016d5c`
- `0x180018b40`
- `0x18001b960`
- `0x18001cb5c`
- `0x18001da24`
- `0x180030c30`
- `0x180037ef8`
- `0x180038ce4`
- `0x180038f50`
- `0x180039a84`
- `0x18003a560`
- `0x18003a584`
- `0x18003ae80`
- `0x18003fea4`
- `0x180046540`
- `0x18004a81c`
- `0x180055010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000f962`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000f9a0`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000f9ab`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000f962`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000f9a0`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000f9ab`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18000fa8d`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18000fa8d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000fb28`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000fb28`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000f9b5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000fbc5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000f9b5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000fbc5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000fc3a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000fc3a`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18000fb07`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18000fb07`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18000fc30`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18000fc30`
- `OLEAUT32!__imp_SysAllocString` at `0x18000f832`
- `OLEAUT32!__imp_SysAllocString` at `0x18000f832`
- `OLEAUT32!__imp_SysFreeString` at `0x18000f885`
- `OLEAUT32!__imp_SysFreeString` at `0x18000f885`

## pseudocode

```c
__int64 __fastcall CDescriptionManager::PublishDescription(CDescriptionManager *this, struct _GUID *a2, int a3)
{
  CDescriptionManager *v3; // r14
  _QWORD *v6; // rsi
  int v7; // r13d
  int IsAllowedCOMCallLocality; // edi
  CDescriptionManager *v9; // rcx
  OLECHAR *v10; // rbx
  __int64 Key; // rax
  CDescriptionManager *v12; // rcx
  CDescriptionManager *v13; // rcx
  __int64 v14; // r8
  _QWORD *v16; // rax
  struct _GUID v17; // xmm0
  struct _TP_WORK *v18; // r13
  struct _RTL_CRITICAL_SECTION *v19; // rbx
  char *v20; // r14
  int i; // edx
  char *v22; // r12
  struct _TP_WORK **v23; // rax
  __int64 v24; // rdx
  _QWORD *v25; // rcx
  __int64 v26; // rax
  __int64 v27; // rdx
  __int64 v28; // r11
  __int64 v29; // rax
  signed int LastError; // eax
  STRSAFE_PCNZWCH v31; // rcx
  __int64 v32; // [rsp+30h] [rbp-D0h] BYREF
  void *Block; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v34; // [rsp+40h] [rbp-C0h] BYREF
  void *v35; // [rsp+48h] [rbp-B8h] BYREF
  int v36; // [rsp+50h] [rbp-B0h] BYREF
  CDescriptionManager *v37; // [rsp+58h] [rbp-A8h]
  __int64 v38; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 *v39; // [rsp+68h] [rbp-98h] BYREF
  _QWORD v40[5]; // [rsp+70h] [rbp-90h] BYREF
  int v41; // [rsp+9Ch] [rbp-64h]
  const char *v42; // [rsp+B8h] [rbp-48h]
  char v43[256]; // [rsp+F0h] [rbp-10h] BYREF
  char v44[256]; // [rsp+1F0h] [rbp+F0h] BYREF

  v3 = this;
  v37 = this;
  v36 = a3;
  ATL::CComSafeDeleteCriticalSection::Lock((CDescriptionManager *)((char *)this + 24));
  memset_0(v40, 0, 0x78u);
  v6 = 0;
  v7 = 0;
  IsAllowedCOMCallLocality = HrIsAllowedCOMCallLocality(1);
  if ( IsAllowedCOMCallLocality >= 0 )
  {
    v16 = malloc(0x50u);
    v6 = v16;
    if ( v16 )
    {
      v16[1] = v16;
      *v16 = v16;
      v16[2] = 0;
      v16[3] = 0;
      v16[5] = 0;
      v16[4] = 0;
    }
    else
    {
      IsAllowedCOMCallLocality = -2147024882;
    }
  }
  v41 = a3;
  v35 = 0;
  v39 = 0;
  if ( IsAllowedCOMCallLocality >= 0 )
  {
    IsAllowedCOMCallLocality = HrGetContentURL(a2, (struct CUString *)&v39);
    if ( IsAllowedCOMCallLocality >= 0 )
    {
      IsAllowedCOMCallLocality = HrGetURLBase((struct CUString *)&v35);
      if ( IsAllowedCOMCallLocality >= 0 )
      {
        IsAllowedCOMCallLocality = CUString::HrAppend((CUString *)&v35, v39);
        if ( IsAllowedCOMCallLocality >= 0 )
        {
          IsAllowedCOMCallLocality = StringCbPrintfA(v43, 0x100u, "%S", (const wchar_t *)v35);
          v40[1] = v43;
        }
      }
    }
  }
  v42 = "0bd2834d-d10e-46e9-84ba-34e538bea2d3";
  SmartComPtr<IUPnPDescriptionManager>::SmartComPtr<IUPnPDescriptionManager>(&v34);
  SmartComPtr<IUPnPDescriptionManager>::SmartComPtr<IUPnPDescriptionManager>(&v38);
  if ( IsAllowedCOMCallLocality < 0 )
    goto LABEL_18;
  SmartComPtr<IUPnPDescriptionManager>::SmartComPtr<IUPnPDescriptionManager>(&v32);
  IsAllowedCOMCallLocality = CDescriptionManager::HrLoadDocumentAndRootNode(v3, a2, &v32);
  if ( IsAllowedCOMCallLocality >= 0 )
  {
    v10 = SysAllocString(L"//ddd:device");
    if ( v10 )
    {
      ATL::CComPtrBase<IUPnPDynamicContentSource>::Release(&v34);
      Key = LKRhash::CTypedHashTable<CNoRefHashTable,URL_HASH_ENTRY,char const *,LKRhash::CLKRHashTable>::_ExtractKey((__int64)&v32);
      IsAllowedCOMCallLocality = (*(__int64 (__fastcall **)(__int64, OLECHAR *, __int64 *))(*(_QWORD *)Key + 288LL))(
                                   Key,
                                   v10,
                                   &v34);
      if ( IsAllowedCOMCallLocality == 1 )
        IsAllowedCOMCallLocality = -2147467259;
      SysFreeString(v10);
      if ( !IsAllowedCOMCallLocality )
        goto LABEL_9;
      v31 = WPP_GLOBAL_Control;
    }
    else
    {
      v31 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control )
      {
        if ( (WPP_GLOBAL_Control[14] & 1) != 0 )
        {
          WPP_SF_Sd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            14,
            (unsigned int)WPP_cfeffffca17e32bb09beafeef3f68c4e_Traceguids,
            (unsigned int)L"//ddd:device",
            14);
          v31 = WPP_GLOBAL_Control;
        }
        if ( v31 != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (v31[14] & 1) != 0 )
        {
          WPP_SF_d(*((_QWORD *)v31 + 2), 15, WPP_cfeffffca17e32bb09beafeef3f68c4e_Traceguids, 2147942414LL);
          v31 = WPP_GLOBAL_Control;
        }
      }
      IsAllowedCOMCallLocality = -2147024882;
    }
    if ( v31 != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (v31[14] & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)v31 + 2),
        16,
        WPP_0f728bc4424332fd22a71fc2ba056f71_Traceguids,
        (unsigned int)IsAllowedCOMCallLocality);
    if ( IsAllowedCOMCallLocality >= 0 )
    {
LABEL_9:
      IsAllowedCOMCallLocality = HrSelectNode(L"/ddd:root/ddd:device", &v32, &v38);
      if ( IsAllowedCOMCallLocality >= 0 )
        IsAllowedCOMCallLocality = CDescriptionManager::Hr_DoStartUrlListening(v12, a2);
    }
  }
  ATL::CComPtr<IUPnPDescriptionManager>::~CComPtr<IUPnPDescriptionManager>((__int64)&v32);
  if ( IsAllowedCOMCallLocality >= 0 )
  {
    v7 = 1;
    LODWORD(v32) = 1;
    if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 0x40) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 62, WPP_d1632e28abac3523b7923f2ce652edb2_Traceguids);
    Block = 0;
    IsAllowedCOMCallLocality = HrSelectNodeText((OLECHAR *)L"ddd:UDN");
    if ( IsAllowedCOMCallLocality >= 0 )
    {
      IsAllowedCOMCallLocality = StringCbPrintfA(v44, 0x100u, "%S::upnp:rootdevice", (const wchar_t *)Block);
      if ( IsAllowedCOMCallLocality >= 0 )
      {
        v40[3] = v44;
        v40[0] = "upnp:rootdevice";
        IsAllowedCOMCallLocality = CDescriptionManager::AddRegistrationParams(
                                     v13,
                                     (struct _SSDP_MESSAGE_EX *)v40,
                                     v14,
                                     (struct SSDP_SERVICE_REGISTRATION_PARAMS *)v6);
      }
    }
    if ( IsAllowedCOMCallLocality
      && WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control
      && (WPP_GLOBAL_Control[14] & 1) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        63,
        WPP_d1632e28abac3523b7923f2ce652edb2_Traceguids,
        (unsigned int)IsAllowedCOMCallLocality);
    }
    free(Block);
    if ( IsAllowedCOMCallLocality >= 0 )
    {
      IsAllowedCOMCallLocality = CDescriptionManager::HrPD_DoDevicePublication(
                                   (int)v3,
                                   (int)a2,
                                   (struct SSDP_SERVICE_REGISTRATION_PARAMS *)v6);
      if ( IsAllowedCOMCallLocality >= 0 )
      {
        v17 = *a2;
        *((_DWORD *)v6 + 12) = a3;
        v6[9] = v3;
        *(struct _GUID *)((char *)v6 + 52) = v17;
        Block = CreateThreadpoolWork(
                  CDescriptionManager::BeginRegistration,
                  v6,
                  (PTP_CALLBACK_ENVIRON)((char *)v3 + 392));
        v18 = (struct _TP_WORK *)Block;
        if ( !Block )
        {
          LastError = GetLastError();
          IsAllowedCOMCallLocality = LastError;
          if ( LastError > 0 )
            IsAllowedCOMCallLocality = (unsigned __int16)LastError | 0x80070000;
          v9 = (CDescriptionManager *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 0x40) != 0 )
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              78,
              WPP_d1632e28abac3523b7923f2ce652edb2_Traceguids,
              (unsigned int)IsAllowedCOMCallLocality);
          if ( IsAllowedCOMCallLocality < 0 )
          {
LABEL_50:
            v7 = v32;
            goto LABEL_18;
          }
        }
        v19 = (struct _RTL_CRITICAL_SECTION *)((char *)v3 + 488);
        EnterCriticalSection((LPCRITICAL_SECTION)((char *)v3 + 488));
        v20 = (char *)v3 + 320;
        for ( i = 0; ; ++i )
        {
          if ( i >= *((_DWORD *)v20 + 2) )
          {
            v22 = v20 + 16;
            goto LABEL_37;
          }
          v25 = (_QWORD *)(*(_QWORD *)v20 + 16LL * i);
          v26 = *(_QWORD *)&a2->Data1 - *v25;
          if ( *(_QWORD *)&a2->Data1 == *v25 )
            v26 = *(_QWORD *)a2->Data4 - v25[1];
          if ( !v26 )
            break;
        }
        v22 = v20 + 16;
        if ( *((_QWORD *)v20 + 2) + 8LL * i )
        {
          IsAllowedCOMCallLocality = -2147024809;
          goto LABEL_48;
        }
LABEL_37:
        v23 = (struct _TP_WORK **)CTable<_GUID,_TP_WORK *>::Lookup(v20, a2);
        if ( v23 )
        {
          *v23 = v18;
        }
        else
        {
          if ( (int)CUArray<_GUID>::HrPushBack(v20, v24) < 0 )
          {
LABEL_41:
            IsAllowedCOMCallLocality = -2147467259;
LABEL_48:
            v3 = v37;
            goto LABEL_49;
          }
          if ( (int)CUArray<IUPnPDeviceControlSsdpHeaders *>::HrPushBack(v22, &Block) < 0 )
          {
            CUArray<_GUID>::HrPopBack(v20);
            goto LABEL_41;
          }
          v18 = (struct _TP_WORK *)Block;
        }
        v3 = v37;
        if ( !CTable<_GUID,long>::Lookup((char *)v37 + 352, a2) )
          CTable<_GUID,long>::HrInsert(v28, v27, &v36);
        v29 = *((_QWORD *)v3 + 76);
        v6[1] = (char *)v3 + 608;
        *v6 = v29;
        *(_QWORD *)(v29 + 8) = v6;
        *((_QWORD *)v3 + 76) = v6;
        SubmitThreadpoolWork(v18);
        v6 = 0;
LABEL_49:
        LeaveCriticalSection(v19);
        goto LABEL_50;
      }
    }
  }
LABEL_18:
  if ( v6 )
  {
    CDescriptionManager::PurgeRegistrationParams(v9, (struct SSDP_SERVICE_REGISTRATION_PARAMS *)v6);
    operator delete(v6);
  }
  if ( IsAllowedCOMCallLocality < 0 )
  {
    if ( v7 )
      CDescriptionManager::Hr_DoStopUrlListening(v9, a2);
    CDescriptionManager::HrRD_RemoveFromEventing(v3, a2);
  }
  else if ( !IsAllowedCOMCallLocality )
  {
    goto LABEL_22;
  }
  if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      79,
      WPP_d1632e28abac3523b7923f2ce652edb2_Traceguids,
      (unsigned int)IsAllowedCOMCallLocality);
LABEL_22:
  ATL::CComPtr<IUPnPDescriptionManager>::~CComPtr<IUPnPDescriptionManager>((__int64)&v38);
  ATL::CComPtr<IUPnPDescriptionManager>::~CComPtr<IUPnPDescriptionManager>((__int64)&v34);
  free(v39);
  free(v35);
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)v3 + 24));
  return (unsigned int)IsAllowedCOMCallLocality;
}

```

## disassembly

```asm
0x18000f750  mov     [rsp-8+arg_18], rbx
0x18000f755  push    rbp
0x18000f756  push    rsi
0x18000f757  push    rdi
0x18000f758  push    r12
0x18000f75a  push    r13
0x18000f75c  push    r14
0x18000f75e  push    r15
0x18000f760  lea     rbp, [rsp-200h]
0x18000f768  sub     rsp, 300h
0x18000f76f  mov     rax, cs:__security_cookie
0x18000f776  xor     rax, rsp
0x18000f779  mov     [rbp+230h+var_40], rax
0x18000f780  mov     r14, rcx
0x18000f783  mov     [rsp+330h+var_2D8], rcx
0x18000f788  add     rcx, 18h; this
0x18000f78c  mov     [rsp+330h+var_2E0], r8d
0x18000f791  mov     r12d, r8d
0x18000f794  mov     r15, rdx
0x18000f797  call    ?Lock@CComSafeDeleteCriticalSection@ATL@@QEAAJXZ; ATL::CComSafeDeleteCriticalSection::Lock(void)
0x18000f79c  xor     edx, edx; Val
0x18000f79e  lea     rcx, [rsp+330h+var_2C0]; void *
0x18000f7a3  lea     r8d, [rdx+78h]; Size
0x18000f7a7  call    memset_0
0x18000f7ac  xor     esi, esi
0x18000f7ae  xor     r13d, r13d
0x18000f7b1  lea     ecx, [rsi+1]
0x18000f7b4  call    ?HrIsAllowedCOMCallLocality@@YAJW4CALL_LOCALITY@@@Z; HrIsAllowedCOMCallLocality(CALL_LOCALITY)
0x18000f7b9  mov     edi, eax
0x18000f7bb  test    eax, eax
0x18000f7bd  jns     loc_18000FA88
0x18000f7c3  mov     [rbp+230h+var_294], r12d
0x18000f7c7  mov     [rsp+330h+var_2E8], r13
0x18000f7cc  mov     [rsp+330h+var_2C8], r13
0x18000f7d1  test    edi, edi
0x18000f7d3  jns     loc_18000FA1A
0x18000f7d9  lea     rax, a0bd2834dD10e46; "0bd2834d-d10e-46e9-84ba-34e538bea2d3"
0x18000f7e0  lea     rcx, [rsp+330h+var_2F0]; void *
0x18000f7e5  mov     [rbp+230h+var_278], rax
0x18000f7e9  call    ??0?$SmartComPtr@UIUPnPDescriptionManager@@@@QEAA@XZ; SmartComPtr<IUPnPDescriptionManager>::SmartComPtr<IUPnPDescriptionManager>(void)
0x18000f7ee  lea     rcx, [rsp+330h+var_2D0]; void *
0x18000f7f3  call    ??0?$SmartComPtr@UIUPnPDescriptionManager@@@@QEAA@XZ; SmartComPtr<IUPnPDescriptionManager>::SmartComPtr<IUPnPDescriptionManager>(void)
0x18000f7f8  lea     rbx, WPP_GLOBAL_Control
0x18000f7ff  test    edi, edi
0x18000f801  js      loc_18000F970
0x18000f807  lea     rcx, [rsp+330h+var_300]; void *
0x18000f80c  call    ??0?$SmartComPtr@UIUPnPDescriptionManager@@@@QEAA@XZ; SmartComPtr<IUPnPDescriptionManager>::SmartComPtr<IUPnPDescriptionManager>(void)
0x18000f811  lea     r8, [rsp+330h+var_300]
0x18000f816  mov     rdx, r15
0x18000f819  mov     rcx, r14
0x18000f81c  call    ?HrLoadDocumentAndRootNode@CDescriptionManager@@AEAAJAEBU_GUID@@AEAV?$SmartComPtr@UIXMLDOMNode@@@@@Z; CDescriptionManager::HrLoadDocumentAndRootNode(_GUID const &,SmartComPtr<IXMLDOMNode> &)
0x18000f821  mov     edi, eax
0x18000f823  test    eax, eax
0x18000f825  js      loc_18000F8BA
0x18000f82b  lea     rcx, aDddDevice; "//ddd:device"
0x18000f832  call    cs:__imp_SysAllocString
0x18000f838  mov     rbx, rax
0x18000f83b  test    rax, rax
0x18000f83e  jz      loc_18000FC7E
0x18000f844  lea     rcx, [rsp+330h+var_2F0]
0x18000f849  call    ?Release@?$CComPtrBase@UIUPnPDynamicContentSource@@@ATL@@QEAAXXZ; ATL::CComPtrBase<IUPnPDynamicContentSource>::Release(void)
0x18000f84e  lea     rcx, [rsp+330h+var_300]
0x18000f853  call    ?_ExtractKey@?$CTypedHashTable@VCNoRefHashTable@@VURL_HASH_ENTRY@@PEBDVCLKRHashTable@LKRhash@@@LKRhash@@CA?B_KPEBX@Z; LKRhash::CTypedHashTable<CNoRefHashTable,URL_HASH_ENTRY,char const *,LKRhash::CLKRHashTable>::_ExtractKey(void const *)
0x18000f858  mov     r9, rax
0x18000f85b  lea     r8, [rsp+330h+var_2F0]
0x18000f860  mov     rdx, rbx
0x18000f863  mov     rcx, [rax]
0x18000f866  mov     rax, [rcx+120h]
0x18000f86d  mov     rcx, r9
0x18000f870  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f875  mov     edi, eax
0x18000f877  cmp     eax, 1
0x18000f87a  mov     eax, 80004005h
0x18000f87f  mov     rcx, rbx; bstrString
0x18000f882  cmovz   edi, eax
0x18000f885  call    cs:__imp_SysFreeString
0x18000f88b  lea     rbx, WPP_GLOBAL_Control
0x18000f892  test    edi, edi
0x18000f894  jnz     loc_18000FCF6
0x18000f89a  lea     r8, [rsp+330h+var_2D0]
0x18000f89f  lea     rdx, [rsp+330h+var_300]
0x18000f8a4  lea     rcx, aDddRootDddDevi_0; "/ddd:root/ddd:device"
0x18000f8ab  call    ?HrSelectNode@@YAJPEBGAEAV?$SmartComPtr@UIXMLDOMNode@@@@1@Z; HrSelectNode(ushort const *,SmartComPtr<IXMLDOMNode> &,SmartComPtr<IXMLDOMNode> &)
0x18000f8b0  mov     edi, eax
0x18000f8b2  test    eax, eax
0x18000f8b4  jns     loc_18000FA0B
0x18000f8ba  lea     rcx, [rsp+330h+var_300]
0x18000f8bf  call    ??1?$CComPtr@UIUPnPDescriptionManager@@@ATL@@QEAA@XZ; ATL::CComPtr<IUPnPDescriptionManager>::~CComPtr<IUPnPDescriptionManager>(void)
0x18000f8c4  test    edi, edi
0x18000f8c6  js      loc_18000F970
0x18000f8cc  mov     r13d, 1
0x18000f8d2  mov     dword ptr [rsp+330h+var_300], r13d
0x18000f8d7  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f8de  cmp     rcx, rbx
0x18000f8e1  jnz     loc_18000F9E7
0x18000f8e7  lea     r8, [rsp+330h+Block]
0x18000f8ec  mov     [rsp+330h+Block], 0
0x18000f8f5  lea     rdx, [rsp+330h+var_2D0]
0x18000f8fa  lea     rcx, aDddUdn_0; "ddd:UDN"
0x18000f901  call    ?HrSelectNodeText@@YAJPEBGAEAV?$SmartComPtr@UIXMLDOMNode@@@@AEAVCUString@@@Z; HrSelectNodeText(ushort const *,SmartComPtr<IXMLDOMNode> &,CUString &)
0x18000f906  mov     edi, eax
0x18000f908  test    eax, eax
0x18000f90a  js      short loc_18000F955
0x18000f90c  mov     r9, [rsp+330h+Block]
0x18000f911  lea     r8, aSUpnpRootdevic; "%S::upnp:rootdevice"
0x18000f918  mov     edx, 100h; unsigned __int64
0x18000f91d  lea     rcx, [rbp+230h+var_140]; char *
0x18000f924  call    ?StringCbPrintfA@@YAJPEAD_KPEBDZZ; StringCbPrintfA(char *,unsigned __int64,char const *,...)
0x18000f929  mov     edi, eax
0x18000f92b  test    eax, eax
0x18000f92d  js      short loc_18000F955
0x18000f92f  lea     rax, [rbp+230h+var_140]
0x18000f936  mov     r9, rsi; struct SSDP_SERVICE_REGISTRATION_PARAMS *
0x18000f939  mov     [rbp+230h+var_2A8], rax
0x18000f93d  lea     rdx, [rsp+330h+var_2C0]; struct _SSDP_MESSAGE_EX *
0x18000f942  lea     rax, aUpnpRootdevice; "upnp:rootdevice"
0x18000f949  mov     [rsp+330h+var_2C0], rax
0x18000f94e  call    ?AddRegistrationParams@CDescriptionManager@@AEAAJPEAU_SSDP_MESSAGE_EX@@KPEAUSSDP_SERVICE_REGISTRATION_PARAMS@@@Z; CDescriptionManager::AddRegistrationParams(_SSDP_MESSAGE_EX *,ulong,SSDP_SERVICE_REGISTRATION_PARAMS *)
0x18000f953  mov     edi, eax
0x18000f955  test    edi, edi
0x18000f957  jnz     loc_18000FD2D
0x18000f95d  mov     rcx, [rsp+330h+Block]; Block
0x18000f962  call    cs:__imp_free
0x18000f968  test    edi, edi
0x18000f96a  jns     loc_18000FAC1
0x18000f970  test    rsi, rsi
0x18000f973  jnz     loc_18000FD7E
0x18000f979  test    edi, edi
0x18000f97b  js      loc_18000FD98
0x18000f981  jnz     loc_18000FDB0
0x18000f987  lea     rcx, [rsp+330h+var_2D0]
0x18000f98c  call    ??1?$CComPtr@UIUPnPDescriptionManager@@@ATL@@QEAA@XZ; ATL::CComPtr<IUPnPDescriptionManager>::~CComPtr<IUPnPDescriptionManager>(void)
0x18000f991  lea     rcx, [rsp+330h+var_2F0]
0x18000f996  call    ??1?$CComPtr@UIUPnPDescriptionManager@@@ATL@@QEAA@XZ; ATL::CComPtr<IUPnPDescriptionManager>::~CComPtr<IUPnPDescriptionManager>(void)
0x18000f99b  mov     rcx, [rsp+330h+var_2C8]; Block
0x18000f9a0  call    cs:__imp_free
0x18000f9a6  mov     rcx, [rsp+330h+var_2E8]; Block
0x18000f9ab  call    cs:__imp_free
0x18000f9b1  lea     rcx, [r14+18h]; lpCriticalSection
0x18000f9b5  call    cs:__imp_LeaveCriticalSection
0x18000f9bb  mov     eax, edi
0x18000f9bd  mov     rcx, [rbp+230h+var_40]
0x18000f9c4  xor     rcx, rsp; StackCookie
0x18000f9c7  call    __security_check_cookie
0x18000f9cc  mov     rbx, [rsp+330h+arg_18]
0x18000f9d4  add     rsp, 300h
0x18000f9db  pop     r15
0x18000f9dd  pop     r14
0x18000f9df  pop     r13
0x18000f9e1  pop     r12
0x18000f9e3  pop     rdi
0x18000f9e4  pop     rsi
0x18000f9e5  pop     rbp
0x18000f9e6  retn
0x18000f9e7  test    byte ptr [rcx+1Ch], 40h
0x18000f9eb  jz      loc_18000F8E7
0x18000f9f1  mov     rcx, [rcx+10h]
0x18000f9f5  lea     r8, WPP_d1632e28abac3523b7923f2ce652edb2_Traceguids
0x18000f9fc  mov     edx, 3Eh ; '>'
0x18000fa01  call    WPP_SF_
0x18000fa06  jmp     loc_18000F8E7
0x18000fa0b  mov     rdx, r15; struct _GUID *
0x18000fa0e  call    ?Hr_DoStartUrlListening@CDescriptionManager@@AEAAJAEBU_GUID@@@Z; CDescriptionManager::Hr_DoStartUrlListening(_GUID const &)
0x18000fa13  mov     edi, eax
0x18000fa15  jmp     loc_18000F8BA
0x18000fa1a  lea     rdx, [rsp+330h+var_2C8]; this
0x18000fa1f  mov     rcx, r15; Uuid
0x18000fa22  call    ?HrGetContentURL@@YAJAEBU_GUID@@AEAVCUString@@@Z; HrGetContentURL(_GUID const &,CUString &)
0x18000fa27  mov     edi, eax
0x18000fa29  test    eax, eax
0x18000fa2b  js      loc_18000F7D9
0x18000fa31  lea     rcx, [rsp+330h+var_2E8]; this
0x18000fa36  call    ?HrGetURLBase@@YAJAEAVCUString@@@Z; HrGetURLBase(CUString &)
0x18000fa3b  mov     edi, eax
0x18000fa3d  test    eax, eax
0x18000fa3f  js      loc_18000F7D9
0x18000fa45  mov     rdx, [rsp+330h+var_2C8]; unsigned __int16 *
0x18000fa4a  lea     rcx, [rsp+330h+var_2E8]; this
0x18000fa4f  call    ?HrAppend@CUString@@QEAAJPEBG@Z; CUString::HrAppend(ushort const *)
0x18000fa54  mov     edi, eax
0x18000fa56  test    eax, eax
0x18000fa58  js      loc_18000F7D9
0x18000fa5e  mov     r9, [rsp+330h+var_2E8]
0x18000fa63  lea     r8, aS_0; "%S"
0x18000fa6a  mov     edx, 100h; unsigned __int64
0x18000fa6f  lea     rcx, [rbp+230h+var_240]; char *
0x18000fa73  call    ?StringCbPrintfA@@YAJPEAD_KPEBDZZ; StringCbPrintfA(char *,unsigned __int64,char const *,...)
0x18000fa78  mov     edi, eax
0x18000fa7a  lea     rax, [rbp+230h+var_240]
0x18000fa7e  mov     [rsp+330h+var_2B8], rax
0x18000fa83  jmp     loc_18000F7D9
0x18000fa88  mov     ecx, 50h ; 'P'; Size
0x18000fa8d  call    cs:__imp_malloc
0x18000fa93  mov     rsi, rax
0x18000fa96  test    rax, rax
0x18000fa99  jnz     short loc_18000FAA5
0x18000fa9b  mov     edi, 8007000Eh
0x18000faa0  jmp     loc_18000F7C3
0x18000faa5  mov     [rax+8], rax
0x18000faa9  mov     [rax], rax
0x18000faac  mov     [rax+10h], r13
0x18000fab0  mov     [rax+18h], r13
0x18000fab4  mov     [rax+28h], r13
0x18000fab8  mov     [rax+20h], r13
0x18000fabc  jmp     loc_18000F7C3
0x18000fac1  lea     r9, [rsp+330h+var_2C0]
0x18000fac6  mov     [rsp+330h+var_310], rsi; struct SSDP_SERVICE_REGISTRATION_PARAMS *
0x18000facb  lea     r8, [rsp+330h+var_2F0]
0x18000fad0  mov     rdx, r15; int
0x18000fad3  mov     rcx, r14; int
0x18000fad6  call    ?HrPD_DoDevicePublication@CDescriptionManager@@AEAAJAEBU_GUID@@AEAV?$SmartComPtr@UIXMLDOMNodeList@@@@PEAU_SSDP_MESSAGE_EX@@PEAUSSDP_SERVICE_REGISTRATION_PARAMS@@@Z; CDescriptionManager::HrPD_DoDevicePublication(_GUID const &,SmartComPtr<IXMLDOMNodeList> &,_SSDP_MESSAGE_EX *,SSDP_SERVICE_REGISTRATION_PARAMS *)
0x18000fadb  mov     edi, eax
0x18000fadd  test    eax, eax
0x18000fadf  js      loc_18000F970
0x18000fae5  movups  xmm0, xmmword ptr [r15]
0x18000fae9  lea     r8, [r14+188h]; pcbe
0x18000faf0  mov     [rsi+30h], r12d
0x18000faf4  mov     rdx, rsi; pv
0x18000faf7  mov     [rsi+48h], r14
0x18000fafb  lea     rcx, ?BeginRegistration@CDescriptionManager@@SAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x18000fb02  movdqu  xmmword ptr [rsi+34h], xmm0
0x18000fb07  call    cs:__imp_CreateThreadpoolWork
0x18000fb0d  mov     [rsp+330h+Block], rax
0x18000fb12  mov     r13, rax
0x18000fb15  test    rax, rax
0x18000fb18  jz      loc_18000FC3A
0x18000fb1e  lea     rbx, [r14+1E8h]
0x18000fb25  mov     rcx, rbx; lpCriticalSection
0x18000fb28  call    cs:__imp_EnterCriticalSection
0x18000fb2e  add     r14, 140h
0x18000fb35  xor     edx, edx
0x18000fb37  cmp     edx, [r14+8]
0x18000fb3b  jl      short loc_18000FB81
0x18000fb3d  lea     r12, [r14+10h]
0x18000fb41  mov     rdx, r15
0x18000fb44  mov     rcx, r14
0x18000fb47  call    ?Lookup@?$CTable@U_GUID@@PEAU_TP_WORK@@@@QEAAPEAPEAU_TP_WORK@@AEBU_GUID@@@Z; CTable<_GUID,_TP_WORK *>::Lookup(_GUID const &)
0x18000fb4c  test    rax, rax
0x18000fb4f  jnz     loc_18000FD64
0x18000fb55  mov     rcx, r14
0x18000fb58  call    ?HrPushBack@?$CUArray@U_GUID@@@@QEAAJAEBU_GUID@@@Z; CUArray<_GUID>::HrPushBack(_GUID const &)
0x18000fb5d  test    eax, eax
0x18000fb5f  js      short loc_18000FB7A
0x18000fb61  lea     rdx, [rsp+330h+Block]
0x18000fb66  mov     rcx, r12
0x18000fb69  call    ?HrPushBack@?$CUArray@PEAUIUPnPDeviceControlSsdpHeaders@@@@QEAAJAEBQEAUIUPnPDeviceControlSsdpHeaders@@@Z; CUArray<IUPnPDeviceControlSsdpHeaders *>::HrPushBack(IUPnPDeviceControlSsdpHeaders * const &)
0x18000fb6e  test    eax, eax
0x18000fb70  jns     short loc_18000FBEC
0x18000fb72  mov     rcx, r14
0x18000fb75  call    ?HrPopBack@?$CUArray@U_GUID@@@@QEAAJXZ; CUArray<_GUID>::HrPopBack(void)
0x18000fb7a  mov     edi, 80004005h
0x18000fb7f  jmp     short loc_18000FBBD
0x18000fb81  mov     rax, [r15]
0x18000fb84  movsxd  r8, edx
0x18000fb87  mov     rcx, r8
0x18000fb8a  shl     rcx, 4
0x18000fb8e  add     rcx, [r14]
0x18000fb91  sub     rax, [rcx]
0x18000fb94  jnz     short loc_18000FB9E
0x18000fb96  mov     rax, [r15+8]
0x18000fb9a  sub     rax, [rcx+8]
0x18000fb9e  test    rax, rax
0x18000fba1  jz      short loc_18000FBA7
0x18000fba3  inc     edx
0x18000fba5  jmp     short loc_18000FB37
0x18000fba7  lea     r12, [r14+10h]
0x18000fbab  mov     rax, [r12]
0x18000fbaf  lea     rcx, [rax+r8*8]
0x18000fbb3  test    rcx, rcx
0x18000fbb6  jz      short loc_18000FB41
0x18000fbb8  mov     edi, 80070057h
0x18000fbbd  mov     r14, [rsp+330h+var_2D8]
0x18000fbc2  mov     rcx, rbx; lpCriticalSection
0x18000fbc5  call    cs:__imp_LeaveCriticalSection
0x18000fbcb  mov     r13d, dword ptr [rsp+330h+var_300]
0x18000fbd0  jmp     loc_18000F970
0x18000fbd5  test    edi, edi
0x18000fbd7  jns     loc_18000F89A
0x18000fbdd  jmp     loc_18000F8BA
0x18000fbe2  test    edi, edi
0x18000fbe4  jns     loc_18000FB1E
0x18000fbea  jmp     short loc_18000FBCB
0x18000fbec  mov     r13, [rsp+330h+Block]
0x18000fbf1  test    eax, eax
0x18000fbf3  js      short loc_18000FB7A
0x18000fbf5  mov     r14, [rsp+330h+var_2D8]
0x18000fbfa  mov     rdx, r15
0x18000fbfd  lea     r11, [r14+160h]
0x18000fc04  mov     rcx, r11
0x18000fc07  call    ?Lookup@?$CTable@U_GUID@@J@@QEAAPEAJAEBU_GUID@@@Z; CTable<_GUID,long>::Lookup(_GUID const &)
0x18000fc0c  test    rax, rax
0x18000fc0f  jz      loc_18000FD6C
0x18000fc15  lea     rcx, [r14+260h]
0x18000fc1c  mov     rax, [rcx]
0x18000fc1f  mov     [rsi+8], rcx
0x18000fc23  mov     [rsi], rax
0x18000fc26  mov     [rax+8], rsi
0x18000fc2a  mov     [rcx], rsi
0x18000fc2d  mov     rcx, r13; pwk
0x18000fc30  call    cs:__imp_SubmitThreadpoolWork
  ... truncated ...
```
