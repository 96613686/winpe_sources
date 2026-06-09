# CRegistrarSingleton::Initialize(void)

- ea: `0x180030160`
- end: `0x1800306a0`
- name: `?Initialize@CRegistrarSingleton@@UEAAJXZ`
- size: `1344`
- prototype: `__int64 __fastcall(CRegistrarSingleton *__hidden this)`
- caller_count: `0`
- callee_count: `20`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x1800117bc`
- `0x1800117d0`
- `0x180013180`
- `0x18001347c`
- `0x180030160`
- `0x180031698`
- `0x180034c8c`
- `0x180037ef8`
- `0x18003877c`
- `0x180038ce4`
- `0x1800454d0`
- `0x180046540`
- `0x18004699c`
- `0x180046de8`
- `0x18004af14`
- `0x18004bb6c`
- `0x18004bb9c`
- `0x18004bbcc`
- `0x18004bbfc`
- `0x180055010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800301b2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800301b2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180030652`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180030652`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180030463`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180030476`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800304b3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800304bd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800304c7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800304d1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800304ef`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800305cd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800305d7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800305e1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003060f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180030622`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180030463`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180030476`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800304b3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800304bd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800304c7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800304d1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800304ef`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800305cd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800305d7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800305e1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003060f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180030622`
- `SSDPAPI!SsdpStartup` at `0x1800301f4`
- `SSDPAPI!SsdpStartup` at `0x1800301f4`

## pseudocode

```c
__int64 __fastcall CRegistrarSingleton::Initialize(LPVOID *this)
{
  struct _RTL_CRITICAL_SECTION *v2; // rbx
  HRESULT IsAllowedCOMCallLocality; // edi
  __int64 *v4; // r12
  __int64 (__fastcall ***v5)(_QWORD, GUID *, __int64 *); // r14
  __int64 v6; // rcx
  int v7; // r15d
  __int64 v8; // rcx
  __int64 v9; // r14
  LPVOID v10; // rcx
  int i; // r14d
  __int64 v12; // rcx
  int v13; // eax
  int v14; // r14d
  __int64 v15; // rcx
  int v16; // r14d
  LPVOID pv; // [rsp+40h] [rbp-38h] BYREF
  unsigned __int16 *v19; // [rsp+48h] [rbp-30h] BYREF
  unsigned __int16 *v20; // [rsp+50h] [rbp-28h] BYREF
  unsigned __int16 *v21; // [rsp+58h] [rbp-20h] BYREF
  LPVOID v22[3]; // [rsp+60h] [rbp-18h] BYREF
  __int64 v23; // [rsp+C0h] [rbp+48h] BYREF
  LPVOID ppv; // [rsp+C8h] [rbp+50h] BYREF
  unsigned __int16 *v25; // [rsp+D0h] [rbp+58h] BYREF
  unsigned __int16 *v26; // [rsp+D8h] [rbp+60h] BYREF

  if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 0x40) != 0 )
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, WPP_0f8e6464007c3e0bdd6d585d5cfe4b6e_Traceguids, this);
  v2 = (struct _RTL_CRITICAL_SECTION *)(this + 20);
  EnterCriticalSection((LPCRITICAL_SECTION)this + 4);
  IsAllowedCOMCallLocality = HrIsAllowedCOMCallLocality(1);
  if ( IsAllowedCOMCallLocality < 0 )
    goto LABEL_53;
  IsAllowedCOMCallLocality = CUPnPInterfaceList::HrInitialize(&CUPnPInterfaceList::s_instance);
  if ( IsAllowedCOMCallLocality < 0 )
    goto LABEL_53;
  IsAllowedCOMCallLocality = HrInitEventApi();
  if ( IsAllowedCOMCallLocality < 0 )
    goto LABEL_53;
  if ( !(unsigned int)SsdpStartup() )
  {
    IsAllowedCOMCallLocality = HrFromLastWin32Error();
    if ( IsAllowedCOMCallLocality >= 0 )
      IsAllowedCOMCallLocality = -2147467259;
    goto LABEL_53;
  }
  IsAllowedCOMCallLocality = ATL::CComPtrBase<IUPnPDescriptionManager>::CoCreateInstance(this + 13);
  if ( IsAllowedCOMCallLocality < 0 )
    goto LABEL_53;
  v4 = (__int64 *)(this + 14);
  IsAllowedCOMCallLocality = ATL::CComPtrBase<IUPnPDevicePersistenceManager>::CoCreateInstance(this + 14);
  if ( IsAllowedCOMCallLocality < 0 )
    goto LABEL_53;
  SmartComPtr<IUPnPDescriptionManager>::SmartComPtr<IUPnPDescriptionManager>(&ppv);
  IsAllowedCOMCallLocality = ATL::CComPtrBase<IUPnPDynamicContentSource>::CoCreateInstance(&ppv);
  if ( IsAllowedCOMCallLocality >= 0 )
  {
    SmartComPtr<IUPnPDescriptionManager>::SmartComPtr<IUPnPDescriptionManager>(&v23);
    v5 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))this[13];
    ATL::CComPtrBase<IUPnPDynamicContentSource>::Release(&v23);
    IsAllowedCOMCallLocality = -2147467261;
    if ( v5 )
    {
      IsAllowedCOMCallLocality = (**v5)(v5, &GUID_6d8ff8d5_730d_11d4_bf42_00b0d0118b56, &v23);
      if ( IsAllowedCOMCallLocality >= 0 )
      {
        IsAllowedCOMCallLocality = (*(__int64 (__fastcall **)(LPVOID, __int64))(*(_QWORD *)ppv + 32LL))(ppv, v23);
        if ( IsAllowedCOMCallLocality >= 0 )
          IsAllowedCOMCallLocality = ATL::CComPtrBase<IUPnPValidationManager>::CoCreateInstance(this + 15);
      }
    }
    ATL::CComPtr<IUPnPDescriptionManager>::~CComPtr<IUPnPDescriptionManager>((__int64)&v23);
  }
  ATL::CComPtr<IUPnPDescriptionManager>::~CComPtr<IUPnPDescriptionManager>((__int64)&ppv);
  if ( IsAllowedCOMCallLocality < 0 )
    goto LABEL_53;
  IsAllowedCOMCallLocality = ATL::CComPtrBase<IUPnPContainerManager>::CoCreateInstance(
                               this + 16,
                               &CLSID_UPnPContainerManager);
  if ( IsAllowedCOMCallLocality < 0 )
    goto LABEL_53;
  IsAllowedCOMCallLocality = ATL::CComPtrBase<IUPnPDynamicContentSource>::CoCreateInstance(this + 18);
  if ( IsAllowedCOMCallLocality < 0 )
    goto LABEL_53;
  IsAllowedCOMCallLocality = ATL::CComPtrBase<IUPnPContainerManager>::CoCreateInstance(
                               this + 17,
                               &CLSID_UPnPContainerManager64);
  if ( IsAllowedCOMCallLocality < 0 )
    goto LABEL_53;
  v6 = *v4;
  LODWORD(ppv) = 0;
  v26 = 0;
  IsAllowedCOMCallLocality = (*(__int64 (__fastcall **)(__int64, LPVOID *, unsigned __int16 **))(*(_QWORD *)v6 + 48LL))(
                               v6,
                               &ppv,
                               &v26);
  if ( IsAllowedCOMCallLocality < 0 )
    goto LABEL_53;
  v7 = 0;
  if ( (int)ppv > 0 )
  {
    do
    {
      v8 = *v4;
      v19 = 0;
      v20 = 0;
      v21 = 0;
      v22[0] = 0;
      LODWORD(v25) = 0;
      v9 = 8LL * v7;
      if ( (*(int (__fastcall **)(__int64, unsigned __int16 *, unsigned __int16 **, unsigned __int16 **, unsigned __int16 **, LPVOID *, unsigned __int16 **))(*(_QWORD *)v8 + 32LL))(
             v8,
             &v26[v9],
             &v19,
             &v20,
             &v21,
             v22,
             &v25) >= 0 )
      {
        if ( (*(int (__fastcall **)(LPVOID, unsigned __int16 *))(*(_QWORD *)this[13] + 40LL))(this[13], &v26[v9]) >= 0 )
        {
          v10 = this[13];
          pv = 0;
          LODWORD(v23) = 0;
          if ( (*(int (__fastcall **)(LPVOID, unsigned __int16 *, __int64 *, LPVOID *))(*(_QWORD *)v10 + 64LL))(
                 v10,
                 &v26[v9],
                 &v23,
                 &pv) >= 0 )
          {
            if ( pv )
            {
              if ( CDeviceManager::HrAddDevice(
                     (CDeviceManager *)(this + 1),
                     (const struct _GUID *)&v26[v9],
                     v19,
                     v20,
                     v21,
                     v23,
                     (unsigned __int16 **)pv) >= 0 )
                (*(void (__fastcall **)(LPVOID, unsigned __int16 *, _QWORD))(*(_QWORD *)this[13] + 32LL))(
                  this[13],
                  &v26[v9],
                  (unsigned int)v25);
              for ( i = 0; i < (int)v23; ++i )
                CoTaskMemFree(*((LPVOID *)pv + i));
              CoTaskMemFree(pv);
            }
          }
        }
        if ( IsAllowedCOMCallLocality
          && WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control
          && (WPP_GLOBAL_Control[14] & 1) != 0 )
        {
          WPP_SF_Sd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            28,
            (unsigned int)WPP_0f8e6464007c3e0bdd6d585d5cfe4b6e_Traceguids,
            (_DWORD)v19,
            IsAllowedCOMCallLocality);
        }
        CoTaskMemFree(v19);
        CoTaskMemFree(v20);
        CoTaskMemFree(v21);
        CoTaskMemFree(v22[0]);
      }
      ++v7;
    }
    while ( v7 < (int)ppv );
    v2 = (struct _RTL_CRITICAL_SECTION *)(this + 20);
  }
  CoTaskMemFree(v26);
  v12 = *v4;
  LODWORD(v23) = 0;
  ppv = 0;
  IsAllowedCOMCallLocality = (*(__int64 (__fastcall **)(__int64, __int64 *, LPVOID *))(*(_QWORD *)v12 + 80LL))(
                               v12,
                               &v23,
                               &ppv);
  if ( IsAllowedCOMCallLocality < 0 )
  {
LABEL_53:
    CRegistrarSingleton::ShutdownInternal((CRegistrarSingleton *)this, 0);
    goto LABEL_54;
  }
  v13 = v23;
  v14 = 0;
  if ( (int)v23 > 0 )
  {
    do
    {
      v15 = *v4;
      v25 = 0;
      v26 = 0;
      v21 = 0;
      if ( (*(int (__fastcall **)(__int64, _QWORD, unsigned __int16 **, unsigned __int16 **, unsigned __int16 **))(*(_QWORD *)v15 + 64LL))(
             v15,
             *((_QWORD *)ppv + v14),
             &v25,
             &v26,
             &v21) >= 0 )
      {
        CProviderManager::HrRegisterProvider(
          (CProviderManager *)(this + 9),
          *((const unsigned __int16 **)ppv + v14),
          v25,
          v26,
          v21);
        if ( IsAllowedCOMCallLocality
          && WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control
          && (WPP_GLOBAL_Control[14] & 1) != 0 )
        {
          WPP_SF_Sd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            29,
            (unsigned int)WPP_0f8e6464007c3e0bdd6d585d5cfe4b6e_Traceguids,
            *((_QWORD *)ppv + v14),
            IsAllowedCOMCallLocality);
        }
        CoTaskMemFree(v25);
        CoTaskMemFree(v26);
        CoTaskMemFree(v21);
      }
      v13 = v23;
      ++v14;
    }
    while ( v14 < (int)v23 );
    v2 = (struct _RTL_CRITICAL_SECTION *)(this + 20);
  }
  v16 = 0;
  if ( v13 > 0 )
  {
    do
      CoTaskMemFree(*((LPVOID *)ppv + v16++));
    while ( v16 < (int)v23 );
  }
  CoTaskMemFree(ppv);
  *((_DWORD *)this + 38) = 1;
LABEL_54:
  LeaveCriticalSection(v2);
  if ( IsAllowedCOMCallLocality
    && WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control
    && (WPP_GLOBAL_Control[14] & 1) != 0 )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      30,
      WPP_0f8e6464007c3e0bdd6d585d5cfe4b6e_Traceguids,
      (unsigned int)IsAllowedCOMCallLocality);
  }
  return (unsigned int)IsAllowedCOMCallLocality;
}

```

## disassembly

```asm
0x180030160  push    rbp
0x180030162  push    rbx
0x180030163  push    rsi
0x180030164  push    rdi
0x180030165  push    r12
0x180030167  push    r13
0x180030169  push    r14
0x18003016b  push    r15
0x18003016d  mov     rbp, rsp
0x180030170  sub     rsp, 78h
0x180030174  mov     rsi, rcx
0x180030177  mov     rcx, cs:WPP_GLOBAL_Control
0x18003017e  lea     rax, WPP_GLOBAL_Control
0x180030185  cmp     rcx, rax
0x180030188  jz      short loc_1800301A8
0x18003018a  test    byte ptr [rcx+1Ch], 40h
0x18003018e  jz      short loc_1800301A8
0x180030190  mov     rcx, [rcx+10h]
0x180030194  lea     r8, WPP_0f8e6464007c3e0bdd6d585d5cfe4b6e_Traceguids
0x18003019b  mov     edx, 1Bh
0x1800301a0  mov     r9, rsi
0x1800301a3  call    WPP_SF_q
0x1800301a8  lea     rbx, [rsi+0A0h]
0x1800301af  mov     rcx, rbx; lpCriticalSection
0x1800301b2  call    cs:__imp_EnterCriticalSection
0x1800301b8  mov     ecx, 1
0x1800301bd  call    ?HrIsAllowedCOMCallLocality@@YAJW4CALL_LOCALITY@@@Z; HrIsAllowedCOMCallLocality(CALL_LOCALITY)
0x1800301c2  xor     r13d, r13d
0x1800301c5  mov     edi, eax
0x1800301c7  test    eax, eax
0x1800301c9  js      loc_180030645
0x1800301cf  lea     rcx, ?s_instance@CUPnPInterfaceList@@0V1@A; lpCriticalSection
0x1800301d6  call    ?HrInitialize@CUPnPInterfaceList@@QEAAJXZ; CUPnPInterfaceList::HrInitialize(void)
0x1800301db  mov     edi, eax
0x1800301dd  test    eax, eax
0x1800301df  js      loc_180030645
0x1800301e5  call    ?HrInitEventApi@@YAJXZ; HrInitEventApi(void)
0x1800301ea  mov     edi, eax
0x1800301ec  test    eax, eax
0x1800301ee  js      loc_180030645
0x1800301f4  call    cs:__imp_SsdpStartup
0x1800301fa  test    eax, eax
0x1800301fc  jz      loc_180030634
0x180030202  lea     rcx, [rsi+68h]; ppv
0x180030206  call    ?CoCreateInstance@?$CComPtrBase@UIUPnPDescriptionManager@@@ATL@@QEAAJAEBU_GUID@@PEAUIUnknown@@K@Z; ATL::CComPtrBase<IUPnPDescriptionManager>::CoCreateInstance(_GUID const &,IUnknown *,ulong)
0x18003020b  mov     edi, eax
0x18003020d  test    eax, eax
0x18003020f  js      loc_180030645
0x180030215  lea     r12, [rsi+70h]
0x180030219  mov     rcx, r12; ppv
0x18003021c  call    ?CoCreateInstance@?$CComPtrBase@UIUPnPDevicePersistenceManager@@@ATL@@QEAAJAEBU_GUID@@PEAUIUnknown@@K@Z; ATL::CComPtrBase<IUPnPDevicePersistenceManager>::CoCreateInstance(_GUID const &,IUnknown *,ulong)
0x180030221  mov     edi, eax
0x180030223  test    eax, eax
0x180030225  js      loc_180030645
0x18003022b  lea     rcx, [rbp+ppv]; void *
0x18003022f  call    ??0?$SmartComPtr@UIUPnPDescriptionManager@@@@QEAA@XZ; SmartComPtr<IUPnPDescriptionManager>::SmartComPtr<IUPnPDescriptionManager>(void)
0x180030234  lea     rcx, [rbp+ppv]; ppv
0x180030238  call    ?CoCreateInstance@?$CComPtrBase@UIUPnPDynamicContentSource@@@ATL@@QEAAJAEBU_GUID@@PEAUIUnknown@@K@Z; ATL::CComPtrBase<IUPnPDynamicContentSource>::CoCreateInstance(_GUID const &,IUnknown *,ulong)
0x18003023d  mov     edi, eax
0x18003023f  test    eax, eax
0x180030241  js      short loc_1800302B0
0x180030243  lea     rcx, [rbp+arg_0]; void *
0x180030247  call    ??0?$SmartComPtr@UIUPnPDescriptionManager@@@@QEAA@XZ; SmartComPtr<IUPnPDescriptionManager>::SmartComPtr<IUPnPDescriptionManager>(void)
0x18003024c  mov     r14, [rsi+68h]
0x180030250  lea     rcx, [rbp+arg_0]
0x180030254  call    ?Release@?$CComPtrBase@UIUPnPDynamicContentSource@@@ATL@@QEAAXXZ; ATL::CComPtrBase<IUPnPDynamicContentSource>::Release(void)
0x180030259  mov     edi, 80004003h
0x18003025e  test    r14, r14
0x180030261  jz      short loc_1800302A7
0x180030263  mov     rax, [r14]
0x180030266  lea     r8, [rbp+arg_0]
0x18003026a  lea     rdx, _GUID_6d8ff8d5_730d_11d4_bf42_00b0d0118b56
0x180030271  mov     rcx, r14
0x180030274  mov     rax, [rax]
0x180030277  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003027c  mov     edi, eax
0x18003027e  test    eax, eax
0x180030280  js      short loc_1800302A7
0x180030282  mov     rcx, [rbp+ppv]
0x180030286  mov     rdx, [rbp+arg_0]
0x18003028a  mov     rax, [rcx]
0x18003028d  mov     rax, [rax+20h]
0x180030291  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030296  mov     edi, eax
0x180030298  test    eax, eax
0x18003029a  js      short loc_1800302A7
0x18003029c  lea     rcx, [rsi+78h]; ppv
0x1800302a0  call    ?CoCreateInstance@?$CComPtrBase@UIUPnPValidationManager@@@ATL@@QEAAJAEBU_GUID@@PEAUIUnknown@@K@Z; ATL::CComPtrBase<IUPnPValidationManager>::CoCreateInstance(_GUID const &,IUnknown *,ulong)
0x1800302a5  mov     edi, eax
0x1800302a7  lea     rcx, [rbp+arg_0]
0x1800302ab  call    ??1?$CComPtr@UIUPnPDescriptionManager@@@ATL@@QEAA@XZ; ATL::CComPtr<IUPnPDescriptionManager>::~CComPtr<IUPnPDescriptionManager>(void)
0x1800302b0  lea     rcx, [rbp+ppv]
0x1800302b4  call    ??1?$CComPtr@UIUPnPDescriptionManager@@@ATL@@QEAA@XZ; ATL::CComPtr<IUPnPDescriptionManager>::~CComPtr<IUPnPDescriptionManager>(void)
0x1800302b9  test    edi, edi
0x1800302bb  js      loc_180030645
0x1800302c1  lea     rcx, [rsi+80h]; ppv
0x1800302c8  lea     rdx, CLSID_UPnPContainerManager; rclsid
0x1800302cf  call    ?CoCreateInstance@?$CComPtrBase@UIUPnPContainerManager@@@ATL@@QEAAJAEBU_GUID@@PEAUIUnknown@@K@Z; ATL::CComPtrBase<IUPnPContainerManager>::CoCreateInstance(_GUID const &,IUnknown *,ulong)
0x1800302d4  mov     edi, eax
0x1800302d6  test    eax, eax
0x1800302d8  js      loc_180030645
0x1800302de  lea     rcx, [rsi+90h]; ppv
0x1800302e5  call    ?CoCreateInstance@?$CComPtrBase@UIUPnPDynamicContentSource@@@ATL@@QEAAJAEBU_GUID@@PEAUIUnknown@@K@Z; ATL::CComPtrBase<IUPnPDynamicContentSource>::CoCreateInstance(_GUID const &,IUnknown *,ulong)
0x1800302ea  mov     edi, eax
0x1800302ec  test    eax, eax
0x1800302ee  js      loc_180030645
0x1800302f4  lea     rcx, [rsi+88h]; ppv
0x1800302fb  lea     rdx, CLSID_UPnPContainerManager64; rclsid
0x180030302  call    ?CoCreateInstance@?$CComPtrBase@UIUPnPContainerManager@@@ATL@@QEAAJAEBU_GUID@@PEAUIUnknown@@K@Z; ATL::CComPtrBase<IUPnPContainerManager>::CoCreateInstance(_GUID const &,IUnknown *,ulong)
0x180030307  mov     edi, eax
0x180030309  test    eax, eax
0x18003030b  js      loc_180030645
0x180030311  mov     rcx, [r12]
0x180030315  lea     r8, [rbp+arg_18]
0x180030319  mov     dword ptr [rbp+ppv], r13d
0x18003031d  lea     rdx, [rbp+ppv]
0x180030321  mov     [rbp+arg_18], r13
0x180030325  mov     rax, [rcx]
0x180030328  mov     rax, [rax+30h]
0x18003032c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030331  mov     edi, eax
0x180030333  test    eax, eax
0x180030335  js      loc_180030645
0x18003033b  mov     r15d, r13d
0x18003033e  cmp     dword ptr [rbp+ppv], r13d
0x180030342  jle     loc_1800304EB
0x180030348  lea     rbx, WPP_GLOBAL_Control
0x18003034f  mov     rcx, [r12]
0x180030353  lea     r9, [rbp+var_28]
0x180030357  mov     rdx, [rbp+arg_18]
0x18003035b  mov     [rbp+var_30], r13
0x18003035f  mov     [rbp+var_28], r13
0x180030363  mov     [rbp+var_20], r13
0x180030367  mov     [rbp+var_18], r13
0x18003036b  mov     dword ptr [rbp+arg_10], r13d
0x18003036f  mov     r8, [rcx]
0x180030372  movsxd  r14, r15d
0x180030375  shl     r14, 4
0x180030379  add     rdx, r14
0x18003037c  mov     rax, [r8+20h]
0x180030380  lea     r8, [rbp+arg_10]
0x180030384  mov     [rsp+78h+var_48], r8
0x180030389  lea     r8, [rbp+var_18]
0x18003038d  mov     qword ptr [rsp+78h+var_50], r8
0x180030392  lea     r8, [rbp+var_20]
0x180030396  mov     [rsp+78h+var_58], r8
0x18003039b  lea     r8, [rbp+var_30]
0x18003039f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800303a4  test    eax, eax
0x1800303a6  js      loc_1800304D7
0x1800303ac  mov     rcx, [rsi+68h]
0x1800303b0  mov     rdx, [rbp+arg_18]
0x1800303b4  add     rdx, r14
0x1800303b7  mov     r8, [rcx]
0x1800303ba  mov     rax, [r8+28h]
0x1800303be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800303c3  test    eax, eax
0x1800303c5  js      loc_18003047C
0x1800303cb  mov     rcx, [rsi+68h]
0x1800303cf  lea     r9, [rbp+pv]
0x1800303d3  mov     rdx, [rbp+arg_18]
0x1800303d7  mov     [rbp+pv], r13
0x1800303db  add     rdx, r14
0x1800303de  mov     dword ptr [rbp+arg_0], r13d
0x1800303e2  mov     r8, [rcx]
0x1800303e5  mov     rax, [r8+40h]
0x1800303e9  lea     r8, [rbp+arg_0]
0x1800303ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800303f2  test    eax, eax
0x1800303f4  js      loc_18003047C
0x1800303fa  mov     r8, [rbp+pv]
0x1800303fe  test    r8, r8
0x180030401  jz      short loc_18003047C
0x180030403  mov     eax, dword ptr [rbp+arg_0]
0x180030406  lea     rcx, [rsi+8]; this
0x18003040a  mov     rdx, [rbp+arg_18]
0x18003040e  mov     r9, [rbp+var_28]; unsigned __int16 *
0x180030412  add     rdx, r14; struct _GUID *
0x180030415  mov     [rsp+78h+var_48], r8; unsigned __int16 **
0x18003041a  mov     r8, [rbp+var_30]; unsigned __int16 *
0x18003041e  mov     [rsp+78h+var_50], eax; int
0x180030422  mov     rax, [rbp+var_20]
0x180030426  mov     [rsp+78h+var_58], rax; unsigned __int16 *
0x18003042b  call    ?HrAddDevice@CDeviceManager@@QEAAJAEBU_GUID@@PEBG11JPEAPEAG@Z; CDeviceManager::HrAddDevice(_GUID const &,ushort const *,ushort const *,ushort const *,long,ushort * *)
0x180030430  test    eax, eax
0x180030432  js      short loc_18003044F
0x180030434  mov     rcx, [rsi+68h]
0x180030438  mov     rdx, [rbp+arg_18]
0x18003043c  add     rdx, r14
0x18003043f  mov     r8, [rcx]
0x180030442  mov     rax, [r8+20h]
0x180030446  mov     r8d, dword ptr [rbp+arg_10]
0x18003044a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003044f  mov     r14d, r13d
0x180030452  cmp     dword ptr [rbp+arg_0], r13d
0x180030456  jle     short loc_180030472
0x180030458  mov     rcx, [rbp+pv]
0x18003045c  movsxd  rax, r14d
0x18003045f  mov     rcx, [rcx+rax*8]; pv
0x180030463  call    cs:__imp_CoTaskMemFree
0x180030469  inc     r14d
0x18003046c  cmp     r14d, dword ptr [rbp+arg_0]
0x180030470  jl      short loc_180030458
0x180030472  mov     rcx, [rbp+pv]; pv
0x180030476  call    cs:__imp_CoTaskMemFree
0x18003047c  test    edi, edi
0x18003047e  jz      short loc_1800304AF
0x180030480  mov     rcx, cs:WPP_GLOBAL_Control
0x180030487  cmp     rcx, rbx
0x18003048a  jz      short loc_1800304AF
0x18003048c  test    byte ptr [rcx+1Ch], 1
0x180030490  jz      short loc_1800304AF
0x180030492  mov     r9, [rbp+var_30]
0x180030496  lea     r8, WPP_0f8e6464007c3e0bdd6d585d5cfe4b6e_Traceguids
0x18003049d  mov     rcx, [rcx+10h]
0x1800304a1  mov     edx, 1Ch
0x1800304a6  mov     dword ptr [rsp+78h+var_58], edi
0x1800304aa  call    WPP_SF_Sd
0x1800304af  mov     rcx, [rbp+var_30]; pv
0x1800304b3  call    cs:__imp_CoTaskMemFree
0x1800304b9  mov     rcx, [rbp+var_28]; pv
0x1800304bd  call    cs:__imp_CoTaskMemFree
0x1800304c3  mov     rcx, [rbp+var_20]; pv
0x1800304c7  call    cs:__imp_CoTaskMemFree
0x1800304cd  mov     rcx, [rbp+var_18]; pv
0x1800304d1  call    cs:__imp_CoTaskMemFree
0x1800304d7  inc     r15d
0x1800304da  cmp     r15d, dword ptr [rbp+ppv]
0x1800304de  jl      loc_18003034F
0x1800304e4  lea     rbx, [rsi+0A0h]
0x1800304eb  mov     rcx, [rbp+arg_18]; pv
0x1800304ef  call    cs:__imp_CoTaskMemFree
0x1800304f5  mov     rcx, [r12]
0x1800304f9  lea     r8, [rbp+ppv]
0x1800304fd  mov     dword ptr [rbp+arg_0], r13d
0x180030501  lea     rdx, [rbp+arg_0]
0x180030505  mov     [rbp+ppv], r13
0x180030509  mov     rax, [rcx]
0x18003050c  mov     rax, [rax+50h]
0x180030510  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030515  mov     edi, eax
0x180030517  test    eax, eax
0x180030519  js      loc_180030645
0x18003051f  mov     eax, dword ptr [rbp+arg_0]
0x180030522  mov     r14d, r13d
0x180030525  test    eax, eax
0x180030527  jle     loc_1800305FD
0x18003052d  lea     rbx, WPP_GLOBAL_Control
0x180030534  mov     rcx, [r12]
0x180030538  lea     rdx, [rbp+var_20]
0x18003053c  mov     [rbp+arg_10], r13
0x180030540  lea     r9, [rbp+arg_18]
0x180030544  mov     [rbp+arg_18], r13
0x180030548  lea     r8, [rbp+arg_10]
0x18003054c  mov     [rbp+var_20], r13
0x180030550  mov     rax, [rcx]
0x180030553  mov     [rsp+78h+var_58], rdx
0x180030558  mov     rdx, [rbp+ppv]
0x18003055c  movsxd  r15, r14d
0x18003055f  mov     rax, [rax+40h]
0x180030563  mov     rdx, [rdx+r15*8]
0x180030567  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003056c  test    eax, eax
0x18003056e  js      short loc_1800305E7
0x180030570  mov     rdx, [rbp+ppv]
0x180030574  lea     rcx, [rsi+48h]; this
0x180030578  mov     rax, [rbp+var_20]
0x18003057c  mov     r9, [rbp+arg_18]; unsigned __int16 *
0x180030580  mov     r8, [rbp+arg_10]; unsigned __int16 *
0x180030584  mov     rdx, [rdx+r15*8]; unsigned __int16 *
0x180030588  mov     [rsp+78h+var_58], rax; unsigned __int16 *
0x18003058d  call    ?HrRegisterProvider@CProviderManager@@QEAAJPEBG000@Z; CProviderManager::HrRegisterProvider(ushort const *,ushort const *,ushort const *,ushort const *)
0x180030592  test    edi, edi
0x180030594  jz      short loc_1800305C9
0x180030596  mov     rcx, cs:WPP_GLOBAL_Control
0x18003059d  cmp     rcx, rbx
0x1800305a0  jz      short loc_1800305C9
0x1800305a2  test    byte ptr [rcx+1Ch], 1
0x1800305a6  jz      short loc_1800305C9
0x1800305a8  mov     r9, [rbp+ppv]
0x1800305ac  lea     r8, WPP_0f8e6464007c3e0bdd6d585d5cfe4b6e_Traceguids
0x1800305b3  mov     rcx, [rcx+10h]
0x1800305b7  mov     edx, 1Dh
0x1800305bc  mov     dword ptr [rsp+78h+var_58], edi
0x1800305c0  mov     r9, [r9+r15*8]
0x1800305c4  call    WPP_SF_Sd
0x1800305c9  mov     rcx, [rbp+arg_10]; pv
0x1800305cd  call    cs:__imp_CoTaskMemFree
0x1800305d3  mov     rcx, [rbp+arg_18]; pv
0x1800305d7  call    cs:__imp_CoTaskMemFree
0x1800305dd  mov     rcx, [rbp+var_20]; pv
0x1800305e1  call    cs:__imp_CoTaskMemFree
0x1800305e7  mov     eax, dword ptr [rbp+arg_0]
0x1800305ea  inc     r14d
0x1800305ed  cmp     r14d, eax
0x1800305f0  jl      loc_180030534
0x1800305f6  lea     rbx, [rsi+0A0h]
0x1800305fd  mov     r14d, r13d
0x180030600  test    eax, eax
0x180030602  jle     short loc_18003061E
  ... truncated ...
```
