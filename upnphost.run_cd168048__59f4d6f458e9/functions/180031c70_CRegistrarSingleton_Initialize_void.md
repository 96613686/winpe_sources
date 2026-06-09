# CRegistrarSingleton::Initialize(void)

- ea: `0x180031c70`
- end: `0x180032213`
- name: `?Initialize@CRegistrarSingleton@@UEAAJXZ`
- size: `1443`
- prototype: `__int64 __fastcall(LPVOID *this)`
- caller_count: `0`
- callee_count: `20`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x1800056d8`
- `0x1800056f0`
- `0x1800071c0`
- `0x1800074dc`
- `0x180031c70`
- `0x180033370`
- `0x180036cdc`
- `0x18003a30c`
- `0x18003ac54`
- `0x18003b1cc`
- `0x1800480c0`
- `0x180049258`
- `0x1800496f4`
- `0x180049b64`
- `0x18004e1a4`
- `0x18004ee6c`
- `0x18004eea4`
- `0x18004eedc`
- `0x18004ef14`
- `0x180059010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180031cc2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180031cc2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800321be`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800321be`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180031f83`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180031f9c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180031fdf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180031fef`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180031fff`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003200f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180032033`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003211b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003212b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003213b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003216f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180032188`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180031f83`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180031f9c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180031fdf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180031fef`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180031fff`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003200f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180032033`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003211b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003212b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003213b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003216f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180032188`
- `SSDPAPI!SsdpStartup` at `0x180031d0a`
- `SSDPAPI!SsdpStartup` at `0x180031d0a`

## pseudocode

```c
__int64 __fastcall CRegistrarSingleton::Initialize(LPVOID *this)
{
  struct _RTL_CRITICAL_SECTION *v2; // rbx
  int IsAllowedCOMCallLocality; // edi
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
    ATL::CComPtr<IUPnPDescriptionManager>::~CComPtr<IUPnPDescriptionManager>(&v23);
  }
  ATL::CComPtr<IUPnPDescriptionManager>::~CComPtr<IUPnPDescriptionManager>(&ppv);
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
0x180031c70  push    rbp
0x180031c72  push    rbx
0x180031c73  push    rsi
0x180031c74  push    rdi
0x180031c75  push    r12
0x180031c77  push    r13
0x180031c79  push    r14
0x180031c7b  push    r15
0x180031c7d  mov     rbp, rsp
0x180031c80  sub     rsp, 78h
0x180031c84  mov     rsi, rcx
0x180031c87  mov     rcx, cs:WPP_GLOBAL_Control
0x180031c8e  lea     rax, WPP_GLOBAL_Control
0x180031c95  cmp     rcx, rax
0x180031c98  jz      short loc_180031CB8
0x180031c9a  test    byte ptr [rcx+1Ch], 40h
0x180031c9e  jz      short loc_180031CB8
0x180031ca0  mov     rcx, [rcx+10h]
0x180031ca4  lea     r8, WPP_0f8e6464007c3e0bdd6d585d5cfe4b6e_Traceguids
0x180031cab  mov     edx, 1Bh
0x180031cb0  mov     r9, rsi
0x180031cb3  call    WPP_SF_q
0x180031cb8  lea     rbx, [rsi+0A0h]
0x180031cbf  mov     rcx, rbx; lpCriticalSection
0x180031cc2  call    cs:__imp_EnterCriticalSection
0x180031cc9  nop     dword ptr [rax+rax+00h]
0x180031cce  mov     ecx, 1
0x180031cd3  call    ?HrIsAllowedCOMCallLocality@@YAJW4CALL_LOCALITY@@@Z; HrIsAllowedCOMCallLocality(CALL_LOCALITY)
0x180031cd8  xor     r13d, r13d
0x180031cdb  mov     edi, eax
0x180031cdd  test    eax, eax
0x180031cdf  js      loc_1800321B1
0x180031ce5  lea     rcx, ?s_instance@CUPnPInterfaceList@@0V1@A; lpCriticalSection
0x180031cec  call    ?HrInitialize@CUPnPInterfaceList@@QEAAJXZ; CUPnPInterfaceList::HrInitialize(void)
0x180031cf1  mov     edi, eax
0x180031cf3  test    eax, eax
0x180031cf5  js      loc_1800321B1
0x180031cfb  call    ?HrInitEventApi@@YAJXZ; HrInitEventApi(void)
0x180031d00  mov     edi, eax
0x180031d02  test    eax, eax
0x180031d04  js      loc_1800321B1
0x180031d0a  call    cs:__imp_SsdpStartup
0x180031d11  nop     dword ptr [rax+rax+00h]
0x180031d16  test    eax, eax
0x180031d18  jz      loc_1800321A0
0x180031d1e  lea     rcx, [rsi+68h]; ppv
0x180031d22  call    ?CoCreateInstance@?$CComPtrBase@UIUPnPDescriptionManager@@@ATL@@QEAAJAEBU_GUID@@PEAUIUnknown@@K@Z; ATL::CComPtrBase<IUPnPDescriptionManager>::CoCreateInstance(_GUID const &,IUnknown *,ulong)
0x180031d27  mov     edi, eax
0x180031d29  test    eax, eax
0x180031d2b  js      loc_1800321B1
0x180031d31  lea     r12, [rsi+70h]
0x180031d35  mov     rcx, r12; ppv
0x180031d38  call    ?CoCreateInstance@?$CComPtrBase@UIUPnPDevicePersistenceManager@@@ATL@@QEAAJAEBU_GUID@@PEAUIUnknown@@K@Z; ATL::CComPtrBase<IUPnPDevicePersistenceManager>::CoCreateInstance(_GUID const &,IUnknown *,ulong)
0x180031d3d  mov     edi, eax
0x180031d3f  test    eax, eax
0x180031d41  js      loc_1800321B1
0x180031d47  lea     rcx, [rbp+ppv]; void *
0x180031d4b  call    ??0?$SmartComPtr@UIUPnPDescriptionManager@@@@QEAA@XZ; SmartComPtr<IUPnPDescriptionManager>::SmartComPtr<IUPnPDescriptionManager>(void)
0x180031d50  lea     rcx, [rbp+ppv]; ppv
0x180031d54  call    ?CoCreateInstance@?$CComPtrBase@UIUPnPDynamicContentSource@@@ATL@@QEAAJAEBU_GUID@@PEAUIUnknown@@K@Z; ATL::CComPtrBase<IUPnPDynamicContentSource>::CoCreateInstance(_GUID const &,IUnknown *,ulong)
0x180031d59  mov     edi, eax
0x180031d5b  test    eax, eax
0x180031d5d  js      short loc_180031DCC
0x180031d5f  lea     rcx, [rbp+arg_0]; void *
0x180031d63  call    ??0?$SmartComPtr@UIUPnPDescriptionManager@@@@QEAA@XZ; SmartComPtr<IUPnPDescriptionManager>::SmartComPtr<IUPnPDescriptionManager>(void)
0x180031d68  mov     r14, [rsi+68h]
0x180031d6c  lea     rcx, [rbp+arg_0]
0x180031d70  call    ?Release@?$CComPtrBase@UIUPnPDynamicContentSource@@@ATL@@QEAAXXZ; ATL::CComPtrBase<IUPnPDynamicContentSource>::Release(void)
0x180031d75  mov     edi, 80004003h
0x180031d7a  test    r14, r14
0x180031d7d  jz      short loc_180031DC3
0x180031d7f  mov     rax, [r14]
0x180031d82  lea     r8, [rbp+arg_0]
0x180031d86  lea     rdx, _GUID_6d8ff8d5_730d_11d4_bf42_00b0d0118b56
0x180031d8d  mov     rcx, r14
0x180031d90  mov     rax, [rax]
0x180031d93  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031d98  mov     edi, eax
0x180031d9a  test    eax, eax
0x180031d9c  js      short loc_180031DC3
0x180031d9e  mov     rcx, [rbp+ppv]
0x180031da2  mov     rdx, [rbp+arg_0]
0x180031da6  mov     rax, [rcx]
0x180031da9  mov     rax, [rax+20h]
0x180031dad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031db2  mov     edi, eax
0x180031db4  test    eax, eax
0x180031db6  js      short loc_180031DC3
0x180031db8  lea     rcx, [rsi+78h]; ppv
0x180031dbc  call    ?CoCreateInstance@?$CComPtrBase@UIUPnPValidationManager@@@ATL@@QEAAJAEBU_GUID@@PEAUIUnknown@@K@Z; ATL::CComPtrBase<IUPnPValidationManager>::CoCreateInstance(_GUID const &,IUnknown *,ulong)
0x180031dc1  mov     edi, eax
0x180031dc3  lea     rcx, [rbp+arg_0]
0x180031dc7  call    ??1?$CComPtr@UIUPnPDescriptionManager@@@ATL@@QEAA@XZ; ATL::CComPtr<IUPnPDescriptionManager>::~CComPtr<IUPnPDescriptionManager>(void)
0x180031dcc  lea     rcx, [rbp+ppv]
0x180031dd0  call    ??1?$CComPtr@UIUPnPDescriptionManager@@@ATL@@QEAA@XZ; ATL::CComPtr<IUPnPDescriptionManager>::~CComPtr<IUPnPDescriptionManager>(void)
0x180031dd5  test    edi, edi
0x180031dd7  js      loc_1800321B1
0x180031ddd  lea     rcx, [rsi+80h]; ppv
0x180031de4  lea     rdx, CLSID_UPnPContainerManager; rclsid
0x180031deb  call    ?CoCreateInstance@?$CComPtrBase@UIUPnPContainerManager@@@ATL@@QEAAJAEBU_GUID@@PEAUIUnknown@@K@Z; ATL::CComPtrBase<IUPnPContainerManager>::CoCreateInstance(_GUID const &,IUnknown *,ulong)
0x180031df0  mov     edi, eax
0x180031df2  test    eax, eax
0x180031df4  js      loc_1800321B1
0x180031dfa  lea     rcx, [rsi+90h]; ppv
0x180031e01  call    ?CoCreateInstance@?$CComPtrBase@UIUPnPDynamicContentSource@@@ATL@@QEAAJAEBU_GUID@@PEAUIUnknown@@K@Z; ATL::CComPtrBase<IUPnPDynamicContentSource>::CoCreateInstance(_GUID const &,IUnknown *,ulong)
0x180031e06  mov     edi, eax
0x180031e08  test    eax, eax
0x180031e0a  js      loc_1800321B1
0x180031e10  lea     rcx, [rsi+88h]; ppv
0x180031e17  lea     rdx, CLSID_UPnPContainerManager64; rclsid
0x180031e1e  call    ?CoCreateInstance@?$CComPtrBase@UIUPnPContainerManager@@@ATL@@QEAAJAEBU_GUID@@PEAUIUnknown@@K@Z; ATL::CComPtrBase<IUPnPContainerManager>::CoCreateInstance(_GUID const &,IUnknown *,ulong)
0x180031e23  mov     edi, eax
0x180031e25  test    eax, eax
0x180031e27  js      loc_1800321B1
0x180031e2d  mov     rcx, [r12]
0x180031e31  lea     r8, [rbp+arg_18]
0x180031e35  mov     dword ptr [rbp+ppv], r13d
0x180031e39  lea     rdx, [rbp+ppv]
0x180031e3d  mov     [rbp+arg_18], r13
0x180031e41  mov     rax, [rcx]
0x180031e44  mov     rax, [rax+30h]
0x180031e48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031e4d  mov     edi, eax
0x180031e4f  test    eax, eax
0x180031e51  js      loc_1800321B1
0x180031e57  mov     r15d, r13d
0x180031e5a  cmp     dword ptr [rbp+ppv], r13d
0x180031e5e  jle     loc_18003202F
0x180031e64  lea     rbx, WPP_GLOBAL_Control
0x180031e6b  mov     rcx, [r12]
0x180031e6f  lea     r9, [rbp+var_28]
0x180031e73  mov     rdx, [rbp+arg_18]
0x180031e77  mov     [rbp+var_30], r13
0x180031e7b  mov     [rbp+var_28], r13
0x180031e7f  mov     [rbp+var_20], r13
0x180031e83  mov     [rbp+var_18], r13
0x180031e87  mov     dword ptr [rbp+arg_10], r13d
0x180031e8b  mov     r8, [rcx]
0x180031e8e  movsxd  r14, r15d
0x180031e91  shl     r14, 4
0x180031e95  add     rdx, r14
0x180031e98  mov     rax, [r8+20h]
0x180031e9c  lea     r8, [rbp+arg_10]
0x180031ea0  mov     [rsp+78h+var_48], r8
0x180031ea5  lea     r8, [rbp+var_18]
0x180031ea9  mov     qword ptr [rsp+78h+var_50], r8
0x180031eae  lea     r8, [rbp+var_20]
0x180031eb2  mov     [rsp+78h+var_58], r8
0x180031eb7  lea     r8, [rbp+var_30]
0x180031ebb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031ec0  test    eax, eax
0x180031ec2  js      loc_18003201B
0x180031ec8  mov     rcx, [rsi+68h]
0x180031ecc  mov     rdx, [rbp+arg_18]
0x180031ed0  add     rdx, r14
0x180031ed3  mov     r8, [rcx]
0x180031ed6  mov     rax, [r8+28h]
0x180031eda  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031edf  test    eax, eax
0x180031ee1  js      loc_180031FA8
0x180031ee7  mov     rcx, [rsi+68h]
0x180031eeb  lea     r9, [rbp+pv]
0x180031eef  mov     rdx, [rbp+arg_18]
0x180031ef3  mov     [rbp+pv], r13
0x180031ef7  add     rdx, r14
0x180031efa  mov     dword ptr [rbp+arg_0], r13d
0x180031efe  mov     r8, [rcx]
0x180031f01  mov     rax, [r8+40h]
0x180031f05  lea     r8, [rbp+arg_0]
0x180031f09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031f0e  test    eax, eax
0x180031f10  js      loc_180031FA8
0x180031f16  mov     r8, [rbp+pv]
0x180031f1a  test    r8, r8
0x180031f1d  jz      loc_180031FA8
0x180031f23  mov     eax, dword ptr [rbp+arg_0]
0x180031f26  lea     rcx, [rsi+8]; this
0x180031f2a  mov     rdx, [rbp+arg_18]
0x180031f2e  mov     r9, [rbp+var_28]; unsigned __int16 *
0x180031f32  add     rdx, r14; struct _GUID *
0x180031f35  mov     [rsp+78h+var_48], r8; unsigned __int16 **
0x180031f3a  mov     r8, [rbp+var_30]; unsigned __int16 *
0x180031f3e  mov     [rsp+78h+var_50], eax; int
0x180031f42  mov     rax, [rbp+var_20]
0x180031f46  mov     [rsp+78h+var_58], rax; unsigned __int16 *
0x180031f4b  call    ?HrAddDevice@CDeviceManager@@QEAAJAEBU_GUID@@PEBG11JPEAPEAG@Z; CDeviceManager::HrAddDevice(_GUID const &,ushort const *,ushort const *,ushort const *,long,ushort * *)
0x180031f50  test    eax, eax
0x180031f52  js      short loc_180031F6F
0x180031f54  mov     rcx, [rsi+68h]
0x180031f58  mov     rdx, [rbp+arg_18]
0x180031f5c  add     rdx, r14
0x180031f5f  mov     r8, [rcx]
0x180031f62  mov     rax, [r8+20h]
0x180031f66  mov     r8d, dword ptr [rbp+arg_10]
0x180031f6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031f6f  mov     r14d, r13d
0x180031f72  cmp     dword ptr [rbp+arg_0], r13d
0x180031f76  jle     short loc_180031F98
0x180031f78  mov     rcx, [rbp+pv]
0x180031f7c  movsxd  rax, r14d
0x180031f7f  mov     rcx, [rcx+rax*8]; pv
0x180031f83  call    cs:__imp_CoTaskMemFree
0x180031f8a  nop     dword ptr [rax+rax+00h]
0x180031f8f  inc     r14d
0x180031f92  cmp     r14d, dword ptr [rbp+arg_0]
0x180031f96  jl      short loc_180031F78
0x180031f98  mov     rcx, [rbp+pv]; pv
0x180031f9c  call    cs:__imp_CoTaskMemFree
0x180031fa3  nop     dword ptr [rax+rax+00h]
0x180031fa8  test    edi, edi
0x180031faa  jz      short loc_180031FDB
0x180031fac  mov     rcx, cs:WPP_GLOBAL_Control
0x180031fb3  cmp     rcx, rbx
0x180031fb6  jz      short loc_180031FDB
0x180031fb8  test    byte ptr [rcx+1Ch], 1
0x180031fbc  jz      short loc_180031FDB
0x180031fbe  mov     r9, [rbp+var_30]
0x180031fc2  lea     r8, WPP_0f8e6464007c3e0bdd6d585d5cfe4b6e_Traceguids
0x180031fc9  mov     rcx, [rcx+10h]
0x180031fcd  mov     edx, 1Ch
0x180031fd2  mov     dword ptr [rsp+78h+var_58], edi
0x180031fd6  call    WPP_SF_Sd
0x180031fdb  mov     rcx, [rbp+var_30]; pv
0x180031fdf  call    cs:__imp_CoTaskMemFree
0x180031fe6  nop     dword ptr [rax+rax+00h]
0x180031feb  mov     rcx, [rbp+var_28]; pv
0x180031fef  call    cs:__imp_CoTaskMemFree
0x180031ff6  nop     dword ptr [rax+rax+00h]
0x180031ffb  mov     rcx, [rbp+var_20]; pv
0x180031fff  call    cs:__imp_CoTaskMemFree
0x180032006  nop     dword ptr [rax+rax+00h]
0x18003200b  mov     rcx, [rbp+var_18]; pv
0x18003200f  call    cs:__imp_CoTaskMemFree
0x180032016  nop     dword ptr [rax+rax+00h]
0x18003201b  inc     r15d
0x18003201e  cmp     r15d, dword ptr [rbp+ppv]
0x180032022  jl      loc_180031E6B
0x180032028  lea     rbx, [rsi+0A0h]
0x18003202f  mov     rcx, [rbp+arg_18]; pv
0x180032033  call    cs:__imp_CoTaskMemFree
0x18003203a  nop     dword ptr [rax+rax+00h]
0x18003203f  mov     rcx, [r12]
0x180032043  lea     r8, [rbp+ppv]
0x180032047  mov     dword ptr [rbp+arg_0], r13d
0x18003204b  lea     rdx, [rbp+arg_0]
0x18003204f  mov     [rbp+ppv], r13
0x180032053  mov     rax, [rcx]
0x180032056  mov     rax, [rax+50h]
0x18003205a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003205f  mov     edi, eax
0x180032061  test    eax, eax
0x180032063  js      loc_1800321B1
0x180032069  mov     eax, dword ptr [rbp+arg_0]
0x18003206c  mov     r14d, r13d
0x18003206f  test    eax, eax
0x180032071  jle     loc_18003215D
0x180032077  lea     rbx, WPP_GLOBAL_Control
0x18003207e  mov     rcx, [r12]
0x180032082  lea     rdx, [rbp+var_20]
0x180032086  mov     [rbp+arg_10], r13
0x18003208a  lea     r9, [rbp+arg_18]
0x18003208e  mov     [rbp+arg_18], r13
0x180032092  lea     r8, [rbp+arg_10]
0x180032096  mov     [rbp+var_20], r13
0x18003209a  mov     rax, [rcx]
0x18003209d  mov     [rsp+78h+var_58], rdx
0x1800320a2  mov     rdx, [rbp+ppv]
0x1800320a6  movsxd  r15, r14d
0x1800320a9  mov     rax, [rax+40h]
0x1800320ad  mov     rdx, [rdx+r15*8]
0x1800320b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800320b6  test    eax, eax
0x1800320b8  js      loc_180032147
0x1800320be  mov     rdx, [rbp+ppv]
0x1800320c2  lea     rcx, [rsi+48h]; this
0x1800320c6  mov     rax, [rbp+var_20]
0x1800320ca  mov     r9, [rbp+arg_18]; unsigned __int16 *
0x1800320ce  mov     r8, [rbp+arg_10]; unsigned __int16 *
0x1800320d2  mov     rdx, [rdx+r15*8]; unsigned __int16 *
0x1800320d6  mov     [rsp+78h+var_58], rax; unsigned __int16 *
0x1800320db  call    ?HrRegisterProvider@CProviderManager@@QEAAJPEBG000@Z; CProviderManager::HrRegisterProvider(ushort const *,ushort const *,ushort const *,ushort const *)
0x1800320e0  test    edi, edi
0x1800320e2  jz      short loc_180032117
0x1800320e4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800320eb  cmp     rcx, rbx
0x1800320ee  jz      short loc_180032117
0x1800320f0  test    byte ptr [rcx+1Ch], 1
0x1800320f4  jz      short loc_180032117
0x1800320f6  mov     r9, [rbp+ppv]
0x1800320fa  lea     r8, WPP_0f8e6464007c3e0bdd6d585d5cfe4b6e_Traceguids
0x180032101  mov     rcx, [rcx+10h]
0x180032105  mov     edx, 1Dh
0x18003210a  mov     dword ptr [rsp+78h+var_58], edi
0x18003210e  mov     r9, [r9+r15*8]
0x180032112  call    WPP_SF_Sd
0x180032117  mov     rcx, [rbp+arg_10]; pv
0x18003211b  call    cs:__imp_CoTaskMemFree
0x180032122  nop     dword ptr [rax+rax+00h]
0x180032127  mov     rcx, [rbp+arg_18]; pv
0x18003212b  call    cs:__imp_CoTaskMemFree
  ... truncated ...
```
