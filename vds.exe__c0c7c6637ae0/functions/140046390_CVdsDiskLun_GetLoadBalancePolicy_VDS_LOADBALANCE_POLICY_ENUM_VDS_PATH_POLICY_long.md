# CVdsDiskLun::GetLoadBalancePolicy(_VDS_LOADBALANCE_POLICY_ENUM *,_VDS_PATH_POLICY * *,long *)

- ea: `0x140046390`
- end: `0x140046a9e`
- name: `?GetLoadBalancePolicy@CVdsDiskLun@@UEAAJPEAW4_VDS_LOADBALANCE_POLICY_ENUM@@PEAPEAU_VDS_PATH_POLICY@@PEAJ@Z`
- size: `1806`
- prototype: `__int64 __fastcall(CVdsDiskLun *__hidden this, enum _VDS_LOADBALANCE_POLICY_ENUM *, struct _VDS_PATH_POLICY **, int *)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callees

- `0x140012c48`
- `0x14001f220`
- `0x14002a08c`
- `0x14003d638`
- `0x140046390`
- `0x140056010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x140046789`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x140046789`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140046988`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140046988`
- `vdsutil!??0CVdsWmiVariantObjectArrayEnum@@QEAA@XZ` at `0x1400463f7`
- `vdsutil!??0CVdsWmiVariantObjectArrayEnum@@QEAA@XZ` at `0x1400463f7`
- `vdsutil!??1CVdsWmiVariantObjectArrayEnum@@QEAA@XZ` at `0x1400464c9`
- `vdsutil!??1CVdsWmiVariantObjectArrayEnum@@QEAA@XZ` at `0x14004699e`
- `vdsutil!??1CVdsWmiVariantObjectArrayEnum@@QEAA@XZ` at `0x1400464c9`
- `vdsutil!??1CVdsWmiVariantObjectArrayEnum@@QEAA@XZ` at `0x14004699e`
- `vdsutil!VdsWmiConnectToNamespace` at `0x1400465ee`
- `vdsutil!VdsWmiConnectToNamespace` at `0x1400465ee`
- `vdsutil!?Attach@CVdsWmiVariantObjectArrayEnum@@QEAAJPEAUtagVARIANT@@@Z` at `0x1400467e2`
- `vdsutil!?Attach@CVdsWmiVariantObjectArrayEnum@@QEAAJPEAUtagVARIANT@@@Z` at `0x1400467e2`
- `vdsutil!?Next@CVdsWmiVariantObjectArrayEnum@@QEAAJPEAPEAUIWbemClassObject@@@Z` at `0x14004680f`
- `vdsutil!?Next@CVdsWmiVariantObjectArrayEnum@@QEAAJPEAPEAUIWbemClassObject@@@Z` at `0x14004680f`
- `vdsutil!VdsWmiGetUlongFromInstance` at `0x14004671c`
- `vdsutil!VdsWmiGetUlongFromInstance` at `0x140046742`
- `vdsutil!VdsWmiGetUlongFromInstance` at `0x140046871`
- `vdsutil!VdsWmiGetUlongFromInstance` at `0x14004688b`
- `vdsutil!VdsWmiGetUlongFromInstance` at `0x14004671c`
- `vdsutil!VdsWmiGetUlongFromInstance` at `0x140046742`
- `vdsutil!VdsWmiGetUlongFromInstance` at `0x140046871`
- `vdsutil!VdsWmiGetUlongFromInstance` at `0x14004688b`
- `vdsutil!VdsWmiGetObjectFromInstance` at `0x1400466f7`
- `vdsutil!VdsWmiGetObjectFromInstance` at `0x1400466f7`
- `vdsutil!?Detach@CVdsWmiVariantObjectArrayEnum@@QEAAJXZ` at `0x140046962`
- `vdsutil!?Detach@CVdsWmiVariantObjectArrayEnum@@QEAAJXZ` at `0x140046962`
- `vdsutil!VdsWmiFindInstanceOfClass` at `0x140046682`
- `vdsutil!VdsWmiFindInstanceOfClass` at `0x1400466d2`
- `vdsutil!VdsWmiFindInstanceOfClass` at `0x140046682`
- `vdsutil!VdsWmiFindInstanceOfClass` at `0x1400466d2`
- `vdsutil!VdsWmiGetUlonglongFromInstance` at `0x1400466a8`
- `vdsutil!VdsWmiGetUlonglongFromInstance` at `0x140046854`
- `vdsutil!VdsWmiGetUlonglongFromInstance` at `0x1400466a8`
- `vdsutil!VdsWmiGetUlonglongFromInstance` at `0x140046854`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x14004644d`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x14004644d`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x1400464be`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x140046993`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x1400464be`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x140046993`
- `vdsutil!VdsTraceW` at `0x1400464b3`
- `vdsutil!VdsTraceW` at `0x140046606`
- `vdsutil!VdsTraceW` at `0x14004676d`
- `vdsutil!VdsTraceW` at `0x1400467a0`
- `vdsutil!VdsTraceW` at `0x140046a3b`
- `vdsutil!VdsTraceW` at `0x140046a5b`
- `vdsutil!VdsTraceW` at `0x1400464b3`
- `vdsutil!VdsTraceW` at `0x140046606`
- `vdsutil!VdsTraceW` at `0x14004676d`
- `vdsutil!VdsTraceW` at `0x1400467a0`
- `vdsutil!VdsTraceW` at `0x140046a3b`
- `vdsutil!VdsTraceW` at `0x140046a5b`
- `OLEAUT32!__imp_SysAllocString` at `0x140046525`
- `OLEAUT32!__imp_SysAllocString` at `0x140046539`
- `OLEAUT32!__imp_SysAllocString` at `0x14004654b`
- `OLEAUT32!__imp_SysAllocString` at `0x14004655d`
- `OLEAUT32!__imp_SysAllocString` at `0x14004656f`
- `OLEAUT32!__imp_SysAllocString` at `0x140046580`
- `OLEAUT32!__imp_SysAllocString` at `0x140046594`
- `OLEAUT32!__imp_SysAllocString` at `0x1400465a5`
- `OLEAUT32!__imp_SysAllocString` at `0x1400465b6`
- `OLEAUT32!__imp_SysAllocString` at `0x1400465c7`
- `OLEAUT32!__imp_SysAllocString` at `0x1400465d8`
- `OLEAUT32!__imp_SysAllocString` at `0x140046525`
- `OLEAUT32!__imp_SysAllocString` at `0x140046539`
- `OLEAUT32!__imp_SysAllocString` at `0x14004654b`
- `OLEAUT32!__imp_SysAllocString` at `0x14004655d`
- `OLEAUT32!__imp_SysAllocString` at `0x14004656f`
- `OLEAUT32!__imp_SysAllocString` at `0x140046580`
- `OLEAUT32!__imp_SysAllocString` at `0x140046594`
- `OLEAUT32!__imp_SysAllocString` at `0x1400465a5`
- `OLEAUT32!__imp_SysAllocString` at `0x1400465b6`
- `OLEAUT32!__imp_SysAllocString` at `0x1400465c7`
- `OLEAUT32!__imp_SysAllocString` at `0x1400465d8`
- `OLEAUT32!__imp_SysFreeString` at `0x1400468f1`
- `OLEAUT32!__imp_SysFreeString` at `0x1400468fc`
- `OLEAUT32!__imp_SysFreeString` at `0x140046907`
- `OLEAUT32!__imp_SysFreeString` at `0x140046912`
- `OLEAUT32!__imp_SysFreeString` at `0x14004691c`
- `OLEAUT32!__imp_SysFreeString` at `0x140046926`
- `OLEAUT32!__imp_SysFreeString` at `0x140046930`
- `OLEAUT32!__imp_SysFreeString` at `0x14004693a`
- `OLEAUT32!__imp_SysFreeString` at `0x140046944`
- `OLEAUT32!__imp_SysFreeString` at `0x14004694e`
- `OLEAUT32!__imp_SysFreeString` at `0x140046958`
- `OLEAUT32!__imp_SysFreeString` at `0x1400468f1`
- `OLEAUT32!__imp_SysFreeString` at `0x1400468fc`
- `OLEAUT32!__imp_SysFreeString` at `0x140046907`
- `OLEAUT32!__imp_SysFreeString` at `0x140046912`
- `OLEAUT32!__imp_SysFreeString` at `0x14004691c`
- `OLEAUT32!__imp_SysFreeString` at `0x140046926`
- `OLEAUT32!__imp_SysFreeString` at `0x140046930`
- `OLEAUT32!__imp_SysFreeString` at `0x14004693a`
- `OLEAUT32!__imp_SysFreeString` at `0x140046944`
- `OLEAUT32!__imp_SysFreeString` at `0x14004694e`
- `OLEAUT32!__imp_SysFreeString` at `0x140046958`
- `OLEAUT32!__imp_VariantInit` at `0x140046458`
- `OLEAUT32!__imp_VariantInit` at `0x140046462`
- `OLEAUT32!__imp_VariantInit` at `0x140046458`
- `OLEAUT32!__imp_VariantInit` at `0x140046462`
- `OLEAUT32!__imp_VariantClear` at `0x140046643`
- `OLEAUT32!__imp_VariantClear` at `0x14004696c`
- `OLEAUT32!__imp_VariantClear` at `0x140046976`
- `OLEAUT32!__imp_VariantClear` at `0x140046643`
- `OLEAUT32!__imp_VariantClear` at `0x14004696c`
- `OLEAUT32!__imp_VariantClear` at `0x140046976`

## string_xrefs

- `0x14004658d`: `DSMPathCount`
- `0x14004659e`: `DSM_Paths`
- `0x1400465af`: `DSMPathId`
- `0x1400465c0`: `PathWeight`
- `0x1400465d1`: `PrimaryPath`
- `0x140046a16`: `CVdsDiskLun::GetLoadBalancePolicy: FindMpioGetDescriptor NOT SUPPORTED`
- `0x140046a2f`: `CVdsDiskLun::GetLoadBalancePolicy: FindMpioGetDescriptor failed, 1: %lX`
- `0x140046a46`: `CVdsDiskLun::GetLoadBalancePolicy: FindMpioGetDescriptor failed, 2: %lX`
- `0x14004674e`: `CVdsDiskLun::GetLoadBalancePolicy: VdsWmiGetUlongFromInstance DSMPathCount failed: %X`
- `0x140046764`: `CVdsDiskLun::GetLoadBalancePolicy: Too many paths returned.`
- `0x140046797`: `CVdsDiskLun::GetLoadBalancePolicy: pPaths Alloc: Out of memory.`
- `0x1400467ce`: `CVdsDiskLun::GetLoadBalancePolicy: VdsWmiGetVariantObjectArrayFromInstance DSM_Paths failed: %X`
- `0x1400467ee`: `CVdsDiskLun::GetLoadBalancePolicy: vdsDsmPathsEnum.Attach failed: %X`
- `0x1400468d0`: `CVdsDiskLun::GetLoadBalancePolicy: vdsDsmPathsEnum.Next failed: %X`
- `0x1400468c4`: `CVdsDiskLun::GetLoadBalancePolicy: VdsWmiGetUlonglongFromInstance DSMPathId failed: %X`
- `0x1400468b8`: `CVdsDiskLun::GetLoadBalancePolicy: VdsWmiGetUlongFromInstance PathWeight failed: %X`
- `0x1400468ac`: `CVdsDiskLun::GetLoadBalancePolicy: VdsWmiGetUlongFromInstance PrimaryPath failed: %X`

## pseudocode

```c
// Hidden C++ exception states: #wind=16
__int64 __fastcall CVdsDiskLun::GetLoadBalancePolicy(
        CVdsDiskLun *this,
        enum _VDS_LOADBALANCE_POLICY_ENUM *a2,
        struct _VDS_PATH_POLICY **a3,
        int *a4)
{
  struct _VDS_PATH_POLICY *v8; // rsi
  CVdsDiskLun *v9; // rdi
  unsigned int v10; // edi
  OLECHAR *v11; // r14
  int v12; // eax
  int v13; // ebx
  int Descriptor; // eax
  struct IWbemClassObject *v15; // rbx
  int VariantFromInstance; // eax
  int InstanceOfClass; // eax
  int UlonglongFromInstance; // eax
  int v19; // eax
  int ObjectFromInstance; // eax
  int UlongFromInstance; // eax
  int v22; // eax
  int v23; // eax
  int v24; // eax
  signed int i; // edi
  int v26; // eax
  int v27; // ecx
  int v28; // eax
  int v29; // eax
  int v30; // eax
  int v32; // eax
  unsigned int v33; // [rsp+30h] [rbp-D0h] BYREF
  struct IWbemClassObject *v34; // [rsp+38h] [rbp-C8h] BYREF
  struct IWbemClassObject *v35; // [rsp+40h] [rbp-C0h] BYREF
  struct IWbemServices *v36; // [rsp+48h] [rbp-B8h] BYREF
  int v37; // [rsp+50h] [rbp-B0h] BYREF
  enum _VDS_LOADBALANCE_POLICY_ENUM v38; // [rsp+54h] [rbp-ACh] BYREF
  __int64 v39; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v40; // [rsp+60h] [rbp-A0h] BYREF
  BSTR v41; // [rsp+68h] [rbp-98h]
  BSTR v42; // [rsp+70h] [rbp-90h]
  BSTR v43; // [rsp+78h] [rbp-88h]
  BSTR v44; // [rsp+80h] [rbp-80h]
  BSTR v45; // [rsp+88h] [rbp-78h]
  BSTR v46; // [rsp+90h] [rbp-70h]
  BSTR v47; // [rsp+98h] [rbp-68h]
  BSTR v48; // [rsp+A0h] [rbp-60h]
  BSTR v49; // [rsp+A8h] [rbp-58h]
  ULONGLONG v50; // [rsp+B0h] [rbp-50h] BYREF
  BSTR bstrString; // [rsp+B8h] [rbp-48h]
  BSTR v52; // [rsp+C0h] [rbp-40h]
  __int64 v53; // [rsp+C8h] [rbp-38h] BYREF
  VARIANTARG pvarg; // [rsp+D0h] [rbp-30h] BYREF
  VARIANTARG v55; // [rsp+E8h] [rbp-18h] BYREF
  _BYTE v56[24]; // [rsp+100h] [rbp+0h] BYREF
  _BYTE v57[88]; // [rsp+118h] [rbp+18h] BYREF
  struct IWbemClassObject *v58; // [rsp+180h] [rbp+80h] BYREF

  v53 = 0;
  v36 = 0;
  v58 = 0;
  v40 = 0;
  v39 = 0;
  v35 = 0;
  v34 = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  memset(&v55, 0, sizeof(v55));
  CVdsWmiVariantObjectArrayEnum::CVdsWmiVariantObjectArrayEnum((CVdsWmiVariantObjectArrayEnum *)v56);
  bstrString = 0;
  v41 = 0;
  v42 = 0;
  v43 = 0;
  v44 = 0;
  v52 = 0;
  v45 = 0;
  v46 = 0;
  v47 = 0;
  v48 = 0;
  v49 = 0;
  v50 = 0;
  v38 = VDS_LBP_UNKNOWN;
  v33 = 0;
  v8 = 0;
  v37 = 0;
  CVdsCallTracer::CVdsCallTracer((CVdsCallTracer *)v57, 0x5Eu, "CVdsDiskLun::GetLoadBalancePolicy()");
  VariantInit(&pvarg);
  VariantInit(&v55);
  v9 = (CVdsDiskLun *)((char *)this - 112);
  if ( *((_DWORD *)this + 60) != 3 )
  {
    v32 = (*(__int64 (__fastcall **)(_QWORD, enum _VDS_LOADBALANCE_POLICY_ENUM *, struct _VDS_PATH_POLICY **, int *))(**((_QWORD **)this + 26) + 32LL))(
            *((_QWORD *)this + 26),
            a2,
            a3,
            a4);
    v13 = v32;
    if ( v32 < 0 )
    {
      VdsTraceW(0, L"CVdsDiskLun::GetLoadBalancePolicy: m_pLunMpio->GetLoadBalancePolicy failed: %X", (unsigned int)v32);
      goto LABEL_48;
    }
LABEL_47:
    v13 = 0;
    goto LABEL_48;
  }
  if ( !a2 || !a3 || !a4 )
  {
    VdsTraceW(0, L"CVdsDiskLun::GetLoadBalancePolicy: NULL input arguments");
    v13 = -2147024809;
    goto LABEL_48;
  }
  *a2 = VDS_LBP_UNKNOWN;
  *a4 = 0;
  *a3 = 0;
  if ( !CVdsService::m_hIscsidscModule )
  {
    VdsTraceW(0, L"CVdsDiskLun::GetLoadBalancePolicy: Could not load iSCSI library.");
    CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v57);
    CVdsWmiVariantObjectArrayEnum::~CVdsWmiVariantObjectArrayEnum((CVdsWmiVariantObjectArrayEnum *)v56);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v34);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v35);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v39);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v40);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v58);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v36);
    v10 = -2147212288;
    goto LABEL_52;
  }
  bstrString = SysAllocString(L"root\\wmi");
  v41 = SysAllocString(L"InstanceName");
  v42 = SysAllocString(L"DSM_QueryUniqueId");
  v43 = SysAllocString(L"DsmUniqueId");
  v44 = SysAllocString(L"DSM_QueryLBPolicy");
  v11 = SysAllocString(L"LoadBalancePolicy");
  v52 = v11;
  v45 = SysAllocString(L"DSMPathCount");
  v46 = SysAllocString(L"DSM_Paths");
  v47 = SysAllocString(L"DSMPathId");
  v48 = SysAllocString(L"PathWeight");
  v49 = SysAllocString(L"PrimaryPath");
  v12 = VdsWmiConnectToNamespace(bstrString, &v53, &v36);
  v13 = v12;
  if ( v12 >= 0 )
  {
    Descriptor = CVdsDiskLun::FindMpioGetDescriptor(v9, v36, &v58);
    v13 = Descriptor;
    if ( Descriptor < 0 )
    {
      if ( Descriptor == -2147212288 )
      {
        VdsTraceW(2, L"CVdsDiskLun::GetLoadBalancePolicy: FindMpioGetDescriptor NOT SUPPORTED", 2147755008LL);
      }
      else if ( Descriptor == -2147212277 )
      {
        VdsTraceW(1, L"CVdsDiskLun::GetLoadBalancePolicy: FindMpioGetDescriptor failed, 1: %lX", 2147755019LL);
      }
      else
      {
        VdsTraceW(
          0,
          L"CVdsDiskLun::GetLoadBalancePolicy: FindMpioGetDescriptor failed, 2: %lX",
          (unsigned int)Descriptor);
      }
      goto LABEL_48;
    }
    v15 = v58;
    if ( v58 )
    {
      VariantClear(&pvarg);
      VariantFromInstance = VdsWmiGetVariantFromInstance(v15, v41, 8u, &pvarg);
      v13 = VariantFromInstance;
      if ( VariantFromInstance < 0 )
      {
        VdsTraceW(
          0,
          L"CVdsDiskLun::GetLoadBalancePolicy: VdsWmiGetVariantStringFromInstance InstanceName failed: %X",
          (unsigned int)VariantFromInstance);
        goto LABEL_48;
      }
      InstanceOfClass = VdsWmiFindInstanceOfClass(v36, v42, pvarg.llVal, &v40);
      v13 = InstanceOfClass;
      if ( InstanceOfClass < 0 )
      {
        VdsTraceW(
          0,
          L"CVdsDiskLun::GetLoadBalancePolicy: VdsWmiFindInstanceOfClass DSM_QueryUniqueId failed: %X",
          (unsigned int)InstanceOfClass);
        goto LABEL_48;
      }
      UlonglongFromInstance = VdsWmiGetUlonglongFromInstance(v40, v43, &v50);
      v13 = UlonglongFromInstance;
      if ( UlonglongFromInstance < 0 )
      {
        VdsTraceW(
          0,
          L"CVdsDiskLun::GetLoadBalancePolicy: VdsWmiGetUlonglongFromInstance DsmUniqueId failed: %X",
          (unsigned int)UlonglongFromInstance);
        goto LABEL_48;
      }
      v19 = VdsWmiFindInstanceOfClass(v36, v44, pvarg.llVal, &v39);
      v13 = v19;
      if ( v19 < 0 )
      {
        VdsTraceW(
          0,
          L"CVdsDiskLun::GetLoadBalancePolicy: VdsWmiFindInstanceOfClass DSM_QueryLBPolicy failed: %X",
          (unsigned int)v19);
        goto LABEL_48;
      }
      ObjectFromInstance = VdsWmiGetObjectFromInstance(v39, v11, &v35);
      v13 = ObjectFromInstance;
      if ( ObjectFromInstance < 0 )
      {
        VdsTraceW(
          0,
          L"CVdsDiskLun::GetLoadBalancePolicy: VdsWmiGetObjectFromInstance LoadBalancePolicy failed: %X",
          (unsigned int)ObjectFromInstance);
        goto LABEL_48;
      }
      UlongFromInstance = VdsWmiGetUlongFromInstance(v35, v11, &v38);
      v13 = UlongFromInstance;
      if ( UlongFromInstance < 0 )
      {
        VdsTraceW(
          0,
          L"CVdsDiskLun::GetLoadBalancePolicy: VdsWmiGetUlongFromInstance LoadBalancePolicy failed: %X",
          (unsigned int)UlongFromInstance);
        goto LABEL_48;
      }
      v22 = VdsWmiGetUlongFromInstance(v35, v45, &v33);
      v13 = v22;
      if ( v22 < 0 )
      {
        VdsTraceW(
          0,
          L"CVdsDiskLun::GetLoadBalancePolicy: VdsWmiGetUlongFromInstance DSMPathCount failed: %X",
          (unsigned int)v22);
        goto LABEL_48;
      }
      if ( v33 > 0x7FFFFFFF )
      {
        VdsTraceW(0, L"CVdsDiskLun::GetLoadBalancePolicy: Too many paths returned.");
        v13 = -2147024362;
        goto LABEL_48;
      }
      v8 = (struct _VDS_PATH_POLICY *)CoTaskMemAlloc(24LL * v33);
      if ( !v8 )
      {
        VdsTraceW(0, L"CVdsDiskLun::GetLoadBalancePolicy: pPaths Alloc: Out of memory.");
        v13 = -2147024882;
        goto LABEL_48;
      }
      v23 = VdsWmiGetVariantFromInstance(v35, v46, 0x200Du, &v55);
      v13 = v23;
      if ( v23 < 0 )
      {
        VdsTraceW(
          0,
          L"CVdsDiskLun::GetLoadBalancePolicy: VdsWmiGetVariantObjectArrayFromInstance DSM_Paths failed: %X",
          (unsigned int)v23);
        goto LABEL_48;
      }
      v24 = CVdsWmiVariantObjectArrayEnum::Attach((CVdsWmiVariantObjectArrayEnum *)v56, &v55);
      v13 = v24;
      if ( v24 < 0 )
      {
        VdsTraceW(0, L"CVdsDiskLun::GetLoadBalancePolicy: vdsDsmPathsEnum.Attach failed: %X", (unsigned int)v24);
        goto LABEL_48;
      }
      for ( i = 0; ; ++i )
      {
        ATL::CComPtrBase<IVdsIscsiPortal>::Release(&v34);
        v26 = CVdsWmiVariantObjectArrayEnum::Next((CVdsWmiVariantObjectArrayEnum *)v56, &v34);
        v13 = v26;
        v27 = v33;
        if ( v26 == 1 )
          break;
        if ( v26 < 0 )
        {
          VdsTraceW(0, L"CVdsDiskLun::GetLoadBalancePolicy: vdsDsmPathsEnum.Next failed: %X", (unsigned int)v26);
          goto LABEL_48;
        }
        if ( i >= (int)v33 )
          break;
        v8[i].pathId.ullSourceId = v50;
        v28 = VdsWmiGetUlonglongFromInstance(v34, v47, &v8[i].pathId.ullPathId);
        v13 = v28;
        if ( v28 < 0 )
        {
          VdsTraceW(
            0,
            L"CVdsDiskLun::GetLoadBalancePolicy: VdsWmiGetUlonglongFromInstance DSMPathId failed: %X",
            (unsigned int)v28);
          goto LABEL_48;
        }
        v29 = VdsWmiGetUlongFromInstance(v34, v48, &v8[i].ulWeight);
        v13 = v29;
        if ( v29 < 0 )
        {
          VdsTraceW(
            0,
            L"CVdsDiskLun::GetLoadBalancePolicy: VdsWmiGetUlongFromInstance PathWeight failed: %X",
            (unsigned int)v29);
          goto LABEL_48;
        }
        v30 = VdsWmiGetUlongFromInstance(v34, v49, &v37);
        v13 = v30;
        if ( v30 < 0 )
        {
          VdsTraceW(
            0,
            L"CVdsDiskLun::GetLoadBalancePolicy: VdsWmiGetUlongFromInstance PrimaryPath failed: %X",
            (unsigned int)v30);
          goto LABEL_48;
        }
        v8[i].bPrimaryPath = v37 != 0;
      }
      *a2 = v38;
      *a3 = v8;
      *a4 = v27;
    }
    goto LABEL_47;
  }
  VdsTraceW(0, L"CVdsDiskLun::GetLoadBalancePolicy: VdsWmiConnectToNamespace failed: %X", (unsigned int)v12);
LABEL_48:
  SysFreeString(bstrString);
  SysFreeString(v41);
  SysFreeString(v42);
  SysFreeString(v43);
  SysFreeString(v44);
  SysFreeString(v52);
  SysFreeString(v45);
  SysFreeString(v46);
  SysFreeString(v47);
  SysFreeString(v48);
  SysFreeString(v49);
  CVdsWmiVariantObjectArrayEnum::Detach((CVdsWmiVariantObjectArrayEnum *)v56);
  VariantClear(&pvarg);
  VariantClear(&v55);
  if ( v13 < 0 && v8 )
    CoTaskMemFree(v8);
  CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v57);
  CVdsWmiVariantObjectArrayEnum::~CVdsWmiVariantObjectArrayEnum((CVdsWmiVariantObjectArrayEnum *)v56);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v34);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v35);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v39);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v40);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v58);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v36);
  v10 = v13;
LABEL_52:
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v53);
  return v10;
}

```

## disassembly

```asm
0x140046390  push    rbp
0x140046392  push    rbx
0x140046393  push    rsi
0x140046394  push    rdi
0x140046395  push    r12
0x140046397  push    r13
0x140046399  push    r14
0x14004639b  push    r15
0x14004639d  lea     rbp, [rsp-38h]
0x1400463a2  sub     rsp, 138h
0x1400463a9  mov     r15, r9
0x1400463ac  mov     r12, r8
0x1400463af  mov     r13, rdx
0x1400463b2  mov     rbx, rcx
0x1400463b5  xor     edi, edi
0x1400463b7  mov     [rbp+70h+var_A8], rdi
0x1400463bb  mov     [rsp+170h+var_128], rdi
0x1400463c0  mov     [rbp+70h+arg_0], rdi
0x1400463c7  mov     [rsp+170h+var_110], rdi
0x1400463cc  mov     [rsp+170h+var_118], rdi
0x1400463d1  mov     [rsp+170h+var_130], rdi
0x1400463d6  mov     [rsp+170h+var_138], rdi
0x1400463db  xorps   xmm0, xmm0
0x1400463de  xor     eax, eax
0x1400463e0  movups  xmmword ptr [rbp+70h+pvarg], xmm0
0x1400463e4  mov     qword ptr [rbp+70h+pvarg+10h], rax
0x1400463e8  xorps   xmm1, xmm1
0x1400463eb  movups  xmmword ptr [rbp+70h+var_88], xmm1
0x1400463ef  mov     qword ptr [rbp+70h+var_88+10h], rax
0x1400463f3  lea     rcx, [rbp+70h+var_70]
0x1400463f7  call    cs:__imp_??0CVdsWmiVariantObjectArrayEnum@@QEAA@XZ; CVdsWmiVariantObjectArrayEnum::CVdsWmiVariantObjectArrayEnum(void)
0x1400463fd  nop
0x1400463fe  mov     [rbp+70h+bstrString], rdi
0x140046402  mov     [rsp+170h+var_108], rdi
0x140046407  mov     [rsp+170h+var_100], rdi
0x14004640c  mov     [rsp+170h+var_F8], rdi
0x140046411  mov     [rbp+70h+var_F0], rdi
0x140046415  mov     [rbp+70h+var_B0], rdi
0x140046419  mov     [rbp+70h+var_E8], rdi
0x14004641d  mov     [rbp+70h+var_E0], rdi
0x140046421  mov     [rbp+70h+var_D8], rdi
0x140046425  mov     [rbp+70h+var_D0], rdi
0x140046429  mov     [rbp+70h+var_C8], rdi
0x14004642d  mov     [rbp+70h+var_C0], rdi
0x140046431  mov     [rsp+170h+var_11C], edi
0x140046435  mov     [rsp+170h+var_140], edi
0x140046439  mov     esi, edi
0x14004643b  mov     [rsp+170h+var_120], edi
0x14004643f  lea     r8, aCvdsdisklunGet_107; "CVdsDiskLun::GetLoadBalancePolicy()"
0x140046446  lea     edx, [rdi+5Eh]
0x140046449  lea     rcx, [rbp+70h+var_58]
0x14004644d  call    cs:__imp_??0CVdsCallTracer@@QEAA@KPEBD@Z; CVdsCallTracer::CVdsCallTracer(ulong,char const *)
0x140046453  nop
0x140046454  lea     rcx, [rbp+70h+pvarg]; pvarg
0x140046458  call    cs:__imp_VariantInit
0x14004645e  lea     rcx, [rbp+70h+var_88]; pvarg
0x140046462  call    cs:__imp_VariantInit
0x140046468  lea     rdi, [rbx-70h]
0x14004646c  cmp     dword ptr [rdi+160h], 3
0x140046473  jnz     loc_140046A6B
0x140046479  xor     eax, eax
0x14004647b  test    r13, r13
0x14004647e  jz      loc_140046A52
0x140046484  test    r12, r12
0x140046487  jz      loc_140046A52
0x14004648d  test    r15, r15
0x140046490  jz      loc_140046A52
0x140046496  mov     [r13+0], eax
0x14004649a  mov     [r15], eax
0x14004649d  mov     [r12], rax
0x1400464a1  cmp     cs:?m_hIscsidscModule@CVdsService@@2PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * CVdsService::m_hIscsidscModule
0x1400464a8  jnz     short loc_14004651E
0x1400464aa  lea     rdx, aCvdsdisklunGet_86; "CVdsDiskLun::GetLoadBalancePolicy: Coul"...
0x1400464b1  xor     ecx, ecx
0x1400464b3  call    cs:__imp_VdsTraceW
0x1400464b9  nop
0x1400464ba  lea     rcx, [rbp+70h+var_58]
0x1400464be  call    cs:__imp_??1CVdsCallTracer@@QEAA@XZ; CVdsCallTracer::~CVdsCallTracer(void)
0x1400464c4  nop
0x1400464c5  lea     rcx, [rbp+70h+var_70]
0x1400464c9  call    cs:__imp_??1CVdsWmiVariantObjectArrayEnum@@QEAA@XZ; CVdsWmiVariantObjectArrayEnum::~CVdsWmiVariantObjectArrayEnum(void)
0x1400464cf  nop
0x1400464d0  lea     rcx, [rsp+170h+var_138]
0x1400464d5  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1400464da  nop
0x1400464db  lea     rcx, [rsp+170h+var_130]
0x1400464e0  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1400464e5  nop
0x1400464e6  lea     rcx, [rsp+170h+var_118]
0x1400464eb  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1400464f0  nop
0x1400464f1  lea     rcx, [rsp+170h+var_110]
0x1400464f6  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1400464fb  nop
0x1400464fc  lea     rcx, [rbp+70h+arg_0]
0x140046503  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x140046508  nop
0x140046509  lea     rcx, [rsp+170h+var_128]
0x14004650e  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x140046513  nop
0x140046514  mov     edi, 80042400h
0x140046519  jmp     loc_1400469EB
0x14004651e  lea     rcx, Source; "root\\wmi"
0x140046525  call    cs:__imp_SysAllocString
0x14004652b  mov     rbx, rax
0x14004652e  mov     [rbp+70h+bstrString], rax
0x140046532  lea     rcx, aInstancename; "InstanceName"
0x140046539  call    cs:__imp_SysAllocString
0x14004653f  mov     [rsp+170h+var_108], rax
0x140046544  lea     rcx, aDsmQueryunique; "DSM_QueryUniqueId"
0x14004654b  call    cs:__imp_SysAllocString
0x140046551  mov     [rsp+170h+var_100], rax
0x140046556  lea     rcx, aDsmuniqueid; "DsmUniqueId"
0x14004655d  call    cs:__imp_SysAllocString
0x140046563  mov     [rsp+170h+var_F8], rax
0x140046568  lea     rcx, aDsmQuerylbpoli; "DSM_QueryLBPolicy"
0x14004656f  call    cs:__imp_SysAllocString
0x140046575  mov     [rbp+70h+var_F0], rax
0x140046579  lea     rcx, aLoadbalancepol; "LoadBalancePolicy"
0x140046580  call    cs:__imp_SysAllocString
0x140046586  mov     r14, rax
0x140046589  mov     [rbp+70h+var_B0], rax
0x14004658d  lea     rcx, aDsmpathcount; "DSMPathCount"
0x140046594  call    cs:__imp_SysAllocString
0x14004659a  mov     [rbp+70h+var_E8], rax
0x14004659e  lea     rcx, aDsmPaths; "DSM_Paths"
0x1400465a5  call    cs:__imp_SysAllocString
0x1400465ab  mov     [rbp+70h+var_E0], rax
0x1400465af  lea     rcx, aDsmpathid; "DSMPathId"
0x1400465b6  call    cs:__imp_SysAllocString
0x1400465bc  mov     [rbp+70h+var_D8], rax
0x1400465c0  lea     rcx, aPathweight; "PathWeight"
0x1400465c7  call    cs:__imp_SysAllocString
0x1400465cd  mov     [rbp+70h+var_D0], rax
0x1400465d1  lea     rcx, aPrimarypath; "PrimaryPath"
0x1400465d8  call    cs:__imp_SysAllocString
0x1400465de  mov     [rbp+70h+var_C8], rax
0x1400465e2  lea     r8, [rsp+170h+var_128]
0x1400465e7  lea     rdx, [rbp+70h+var_A8]
0x1400465eb  mov     rcx, rbx
0x1400465ee  call    cs:__imp_VdsWmiConnectToNamespace
0x1400465f4  mov     ebx, eax
0x1400465f6  test    eax, eax
0x1400465f8  jns     short loc_140046611
0x1400465fa  lea     rdx, aCvdsdisklunGet_116; "CVdsDiskLun::GetLoadBalancePolicy: VdsW"...
0x140046601  mov     r8d, eax
0x140046604  xor     ecx, ecx
0x140046606  call    cs:__imp_VdsTraceW
0x14004660c  jmp     loc_1400468ED
0x140046611  lea     r8, [rbp+70h+arg_0]; struct IWbemClassObject **
0x140046618  mov     rdx, [rsp+170h+var_128]; struct IWbemServices *
0x14004661d  mov     rcx, rdi; this
0x140046620  call    ?FindMpioGetDescriptor@CVdsDiskLun@@AEAAJPEAUIWbemServices@@PEAPEAUIWbemClassObject@@@Z; CVdsDiskLun::FindMpioGetDescriptor(IWbemServices *,IWbemClassObject * *)
0x140046625  mov     ebx, eax
0x140046627  test    eax, eax
0x140046629  js      loc_140046A0A
0x14004662f  mov     rbx, [rbp+70h+arg_0]
0x140046636  test    rbx, rbx
0x140046639  jz      loc_1400468EB
0x14004663f  lea     rcx, [rbp+70h+pvarg]; pvarg
0x140046643  call    cs:__imp_VariantClear
0x140046649  mov     r8d, 8; unsigned __int16
0x14004664f  lea     r9, [rbp+70h+pvarg]; struct tagVARIANT *
0x140046653  mov     rdx, [rsp+170h+var_108]; unsigned __int16 *
0x140046658  mov     rcx, rbx; struct IWbemClassObject *
0x14004665b  call    ?VdsWmiGetVariantFromInstance@@YAJPEAUIWbemClassObject@@PEAGGPEAUtagVARIANT@@@Z; VdsWmiGetVariantFromInstance(IWbemClassObject *,ushort *,ushort,tagVARIANT *)
0x140046660  mov     ebx, eax
0x140046662  test    eax, eax
0x140046664  jns     short loc_14004666F
0x140046666  lea     rdx, aCvdsdisklunGet_14; "CVdsDiskLun::GetLoadBalancePolicy: VdsW"...
0x14004666d  jmp     short loc_140046601
0x14004666f  lea     r9, [rsp+170h+var_110]
0x140046674  mov     r8, qword ptr [rbp+70h+pvarg+8]
0x140046678  mov     rdx, [rsp+170h+var_100]
0x14004667d  mov     rcx, [rsp+170h+var_128]
0x140046682  call    cs:__imp_VdsWmiFindInstanceOfClass
0x140046688  mov     ebx, eax
0x14004668a  test    eax, eax
0x14004668c  jns     short loc_14004669A
0x14004668e  lea     rdx, aCvdsdisklunGet_35; "CVdsDiskLun::GetLoadBalancePolicy: VdsW"...
0x140046695  jmp     loc_140046601
0x14004669a  lea     r8, [rbp+70h+var_C0]
0x14004669e  mov     rdx, [rsp+170h+var_F8]
0x1400466a3  mov     rcx, [rsp+170h+var_110]
0x1400466a8  call    cs:__imp_VdsWmiGetUlonglongFromInstance
0x1400466ae  mov     ebx, eax
0x1400466b0  test    eax, eax
0x1400466b2  jns     short loc_1400466C0
0x1400466b4  lea     rdx, aCvdsdisklunGet_21; "CVdsDiskLun::GetLoadBalancePolicy: VdsW"...
0x1400466bb  jmp     loc_140046601
0x1400466c0  lea     r9, [rsp+170h+var_118]
0x1400466c5  mov     r8, qword ptr [rbp+70h+pvarg+8]
0x1400466c9  mov     rdx, [rbp+70h+var_F0]
0x1400466cd  mov     rcx, [rsp+170h+var_128]
0x1400466d2  call    cs:__imp_VdsWmiFindInstanceOfClass
0x1400466d8  mov     ebx, eax
0x1400466da  test    eax, eax
0x1400466dc  jns     short loc_1400466EA
0x1400466de  lea     rdx, aCvdsdisklunGet_25; "CVdsDiskLun::GetLoadBalancePolicy: VdsW"...
0x1400466e5  jmp     loc_140046601
0x1400466ea  lea     r8, [rsp+170h+var_130]
0x1400466ef  mov     rdx, r14
0x1400466f2  mov     rcx, [rsp+170h+var_118]
0x1400466f7  call    cs:__imp_VdsWmiGetObjectFromInstance
0x1400466fd  mov     ebx, eax
0x1400466ff  test    eax, eax
0x140046701  jns     short loc_14004670F
0x140046703  lea     rdx, aCvdsdisklunGet_134; "CVdsDiskLun::GetLoadBalancePolicy: VdsW"...
0x14004670a  jmp     loc_140046601
0x14004670f  lea     r8, [rsp+170h+var_11C]
0x140046714  mov     rdx, r14
0x140046717  mov     rcx, [rsp+170h+var_130]
0x14004671c  call    cs:__imp_VdsWmiGetUlongFromInstance
0x140046722  mov     ebx, eax
0x140046724  test    eax, eax
0x140046726  jns     short loc_140046734
0x140046728  lea     rdx, aCvdsdisklunGet_50; "CVdsDiskLun::GetLoadBalancePolicy: VdsW"...
0x14004672f  jmp     loc_140046601
0x140046734  lea     r8, [rsp+170h+var_140]
0x140046739  mov     rdx, [rbp+70h+var_E8]
0x14004673d  mov     rcx, [rsp+170h+var_130]
0x140046742  call    cs:__imp_VdsWmiGetUlongFromInstance
0x140046748  mov     ebx, eax
0x14004674a  test    eax, eax
0x14004674c  jns     short loc_14004675A
0x14004674e  lea     rdx, aCvdsdisklunGet_9; "CVdsDiskLun::GetLoadBalancePolicy: VdsW"...
0x140046755  jmp     loc_140046601
0x14004675a  cmp     [rsp+170h+var_140], 7FFFFFFFh
0x140046762  jbe     short loc_14004677D
0x140046764  lea     rdx, aCvdsdisklunGet_133; "CVdsDiskLun::GetLoadBalancePolicy: Too "...
0x14004676b  xor     ecx, ecx
0x14004676d  call    cs:__imp_VdsTraceW
0x140046773  mov     ebx, 80070216h
0x140046778  jmp     loc_1400468ED
0x14004677d  mov     eax, [rsp+170h+var_140]
0x140046781  lea     rcx, [rax+rax*2]
0x140046785  shl     rcx, 3; cb
0x140046789  call    cs:__imp_CoTaskMemAlloc
0x14004678f  mov     rsi, rax
0x140046792  test    rax, rax
0x140046795  jnz     short loc_1400467B0
0x140046797  lea     rdx, aCvdsdisklunGet_124; "CVdsDiskLun::GetLoadBalancePolicy: pPat"...
0x14004679e  xor     ecx, ecx
0x1400467a0  call    cs:__imp_VdsTraceW
0x1400467a6  mov     ebx, 8007000Eh
0x1400467ab  jmp     loc_1400468ED
0x1400467b0  mov     r8d, 200Dh; unsigned __int16
0x1400467b6  lea     r9, [rbp+70h+var_88]; struct tagVARIANT *
0x1400467ba  mov     rdx, [rbp+70h+var_E0]; unsigned __int16 *
0x1400467be  mov     rcx, [rsp+170h+var_130]; struct IWbemClassObject *
0x1400467c3  call    ?VdsWmiGetVariantFromInstance@@YAJPEAUIWbemClassObject@@PEAGGPEAUtagVARIANT@@@Z; VdsWmiGetVariantFromInstance(IWbemClassObject *,ushort *,ushort,tagVARIANT *)
0x1400467c8  mov     ebx, eax
0x1400467ca  test    eax, eax
0x1400467cc  jns     short loc_1400467DA
0x1400467ce  lea     rdx, aCvdsdisklunGet_81; "CVdsDiskLun::GetLoadBalancePolicy: VdsW"...
0x1400467d5  jmp     loc_140046601
0x1400467da  lea     rdx, [rbp+70h+var_88]
0x1400467de  lea     rcx, [rbp+70h+var_70]
0x1400467e2  call    cs:__imp_?Attach@CVdsWmiVariantObjectArrayEnum@@QEAAJPEAUtagVARIANT@@@Z; CVdsWmiVariantObjectArrayEnum::Attach(tagVARIANT *)
0x1400467e8  mov     ebx, eax
0x1400467ea  test    eax, eax
0x1400467ec  jns     short loc_1400467FA
0x1400467ee  lea     rdx, aCvdsdisklunGet_115; "CVdsDiskLun::GetLoadBalancePolicy: vdsD"...
0x1400467f5  jmp     loc_140046601
0x1400467fa  xor     edi, edi
0x1400467fc  lea     rcx, [rsp+170h+var_138]
0x140046801  call    ?Release@?$CComPtrBase@UIVdsIscsiPortal@@@ATL@@QEAAXXZ; ATL::CComPtrBase<IVdsIscsiPortal>::Release(void)
0x140046806  lea     rdx, [rsp+170h+var_138]
0x14004680b  lea     rcx, [rbp+70h+var_70]
0x14004680f  call    cs:__imp_?Next@CVdsWmiVariantObjectArrayEnum@@QEAAJPEAPEAUIWbemClassObject@@@Z; CVdsWmiVariantObjectArrayEnum::Next(IWbemClassObject * *)
0x140046815  mov     ebx, eax
0x140046817  mov     ecx, [rsp+170h+var_140]
0x14004681b  cmp     eax, 1
0x14004681e  jz      loc_1400468DC
0x140046824  test    eax, eax
0x140046826  js      loc_1400468D0
0x14004682c  cmp     edi, ecx
0x14004682e  jge     loc_1400468DC
0x140046834  movsxd  rax, edi
0x140046837  lea     r14, [rax+rax*2]
0x14004683b  mov     rax, [rbp+70h+var_C0]
0x14004683f  mov     [rsi+r14*8], rax
0x140046843  lea     r8, [rsi+8]
0x140046847  lea     r8, [r8+r14*8]
0x14004684b  mov     rdx, [rbp+70h+var_D8]
0x14004684f  mov     rcx, [rsp+170h+var_138]
0x140046854  call    cs:__imp_VdsWmiGetUlonglongFromInstance
0x14004685a  mov     ebx, eax
0x14004685c  test    eax, eax
0x14004685e  js      short loc_1400468C4
0x140046860  lea     r8, [rsi+14h]
0x140046864  lea     r8, [r8+r14*8]
0x140046868  mov     rdx, [rbp+70h+var_D0]
0x14004686c  mov     rcx, [rsp+170h+var_138]
0x140046871  call    cs:__imp_VdsWmiGetUlongFromInstance
0x140046877  mov     ebx, eax
0x140046879  test    eax, eax
0x14004687b  js      short loc_1400468B8
0x14004687d  lea     r8, [rsp+170h+var_120]
0x140046882  mov     rdx, [rbp+70h+var_C8]
  ... truncated ...
```
