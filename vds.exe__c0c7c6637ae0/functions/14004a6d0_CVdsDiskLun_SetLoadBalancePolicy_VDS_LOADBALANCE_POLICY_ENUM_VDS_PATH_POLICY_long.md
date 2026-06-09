# CVdsDiskLun::SetLoadBalancePolicy(_VDS_LOADBALANCE_POLICY_ENUM,_VDS_PATH_POLICY *,long)

- ea: `0x14004a6d0`
- end: `0x14004aecc`
- name: `?SetLoadBalancePolicy@CVdsDiskLun@@UEAAJW4_VDS_LOADBALANCE_POLICY_ENUM@@PEAU_VDS_PATH_POLICY@@J@Z`
- size: `2044`
- prototype: `__int64 __fastcall(CVdsDiskLun *__hidden this, enum _VDS_LOADBALANCE_POLICY_ENUM, struct _VDS_PATH_POLICY *, int)`
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callees

- `0x140012c48`
- `0x14001f220`
- `0x14002a08c`
- `0x14003d638`
- `0x14004a6d0`
- `0x14004b0d8`
- `0x140056010`

## import_xrefs

- `vdsutil!VdsWmiConnectToNamespace` at `0x14004a902`
- `vdsutil!VdsWmiConnectToNamespace` at `0x14004a902`
- `vdsutil!VdsWmiGetUlongFromInstance` at `0x14004acbd`
- `vdsutil!VdsWmiGetUlongFromInstance` at `0x14004acbd`
- `vdsutil!VdsWmiFindInstanceOfClass` at `0x14004a9be`
- `vdsutil!VdsWmiFindInstanceOfClass` at `0x14004a9be`
- `vdsutil!VdsWmiCreateClassInstance` at `0x14004a9e4`
- `vdsutil!VdsWmiCreateClassInstance` at `0x14004aaf1`
- `vdsutil!VdsWmiCreateClassInstance` at `0x14004a9e4`
- `vdsutil!VdsWmiCreateClassInstance` at `0x14004aaf1`
- `vdsutil!VdsWmiSetUlongInInstance` at `0x14004aa0b`
- `vdsutil!VdsWmiSetUlongInInstance` at `0x14004aa2e`
- `vdsutil!VdsWmiSetUlongInInstance` at `0x14004aa56`
- `vdsutil!VdsWmiSetUlongInInstance` at `0x14004aa92`
- `vdsutil!VdsWmiSetUlongInInstance` at `0x14004ab5a`
- `vdsutil!VdsWmiSetUlongInInstance` at `0x14004ab84`
- `vdsutil!VdsWmiSetUlongInInstance` at `0x14004aa0b`
- `vdsutil!VdsWmiSetUlongInInstance` at `0x14004aa2e`
- `vdsutil!VdsWmiSetUlongInInstance` at `0x14004aa56`
- `vdsutil!VdsWmiSetUlongInInstance` at `0x14004aa92`
- `vdsutil!VdsWmiSetUlongInInstance` at `0x14004ab5a`
- `vdsutil!VdsWmiSetUlongInInstance` at `0x14004ab84`
- `vdsutil!VdsWmiCreateVariantArray` at `0x14004aab2`
- `vdsutil!VdsWmiCreateVariantArray` at `0x14004aab2`
- `vdsutil!VdsWmiSetUlonglongInInstance` at `0x14004ab18`
- `vdsutil!VdsWmiSetUlonglongInInstance` at `0x14004ab33`
- `vdsutil!VdsWmiSetUlonglongInInstance` at `0x14004ab18`
- `vdsutil!VdsWmiSetUlonglongInInstance` at `0x14004ab33`
- `vdsutil!VdsWmiGetMethodArgumentObject` at `0x14004ac37`
- `vdsutil!VdsWmiGetMethodArgumentObject` at `0x14004ac37`
- `vdsutil!VdsWmiSetObjectInInstance` at `0x14004ac67`
- `vdsutil!VdsWmiSetObjectInInstance` at `0x14004ac67`
- `vdsutil!VdsWmiCallMethod` at `0x14004ac97`
- `vdsutil!VdsWmiCallMethod` at `0x14004ac97`
- `vdsutil!VdsTraceEx` at `0x14004a970`
- `vdsutil!VdsTraceEx` at `0x14004a970`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x14004a74d`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x14004a74d`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x14004a797`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x14004ae59`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x14004a797`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x14004ae59`
- `vdsutil!VdsTraceW` at `0x14004a78c`
- `vdsutil!VdsTraceW` at `0x14004a91a`
- `vdsutil!VdsTraceW` at `0x14004aa6e`
- `vdsutil!VdsTraceW` at `0x14004ac17`
- `vdsutil!VdsTraceW` at `0x14004ac4f`
- `vdsutil!VdsTraceW` at `0x14004acd5`
- `vdsutil!VdsTraceW` at `0x14004acf7`
- `vdsutil!VdsTraceW` at `0x14004ad1f`
- `vdsutil!VdsTraceW` at `0x14004ad8e`
- `vdsutil!VdsTraceW` at `0x14004a78c`
- `vdsutil!VdsTraceW` at `0x14004a91a`
- `vdsutil!VdsTraceW` at `0x14004aa6e`
- `vdsutil!VdsTraceW` at `0x14004ac17`
- `vdsutil!VdsTraceW` at `0x14004ac4f`
- `vdsutil!VdsTraceW` at `0x14004acd5`
- `vdsutil!VdsTraceW` at `0x14004acf7`
- `vdsutil!VdsTraceW` at `0x14004ad1f`
- `vdsutil!VdsTraceW` at `0x14004ad8e`
- `OLEAUT32!__imp_SysAllocString` at `0x14004a7fa`
- `OLEAUT32!__imp_SysAllocString` at `0x14004a80e`
- `OLEAUT32!__imp_SysAllocString` at `0x14004a81f`
- `OLEAUT32!__imp_SysAllocString` at `0x14004a830`
- `OLEAUT32!__imp_SysAllocString` at `0x14004a841`
- `OLEAUT32!__imp_SysAllocString` at `0x14004a852`
- `OLEAUT32!__imp_SysAllocString` at `0x14004a862`
- `OLEAUT32!__imp_SysAllocString` at `0x14004a874`
- `OLEAUT32!__imp_SysAllocString` at `0x14004a884`
- `OLEAUT32!__imp_SysAllocString` at `0x14004a896`
- `OLEAUT32!__imp_SysAllocString` at `0x14004a8a7`
- `OLEAUT32!__imp_SysAllocString` at `0x14004a8b8`
- `OLEAUT32!__imp_SysAllocString` at `0x14004a8c9`
- `OLEAUT32!__imp_SysAllocString` at `0x14004a8da`
- `OLEAUT32!__imp_SysAllocString` at `0x14004a8ec`
- `OLEAUT32!__imp_SysAllocString` at `0x14004a7fa`
- `OLEAUT32!__imp_SysAllocString` at `0x14004a80e`
- `OLEAUT32!__imp_SysAllocString` at `0x14004a81f`
- `OLEAUT32!__imp_SysAllocString` at `0x14004a830`
- `OLEAUT32!__imp_SysAllocString` at `0x14004a841`
- `OLEAUT32!__imp_SysAllocString` at `0x14004a852`
- `OLEAUT32!__imp_SysAllocString` at `0x14004a862`
- `OLEAUT32!__imp_SysAllocString` at `0x14004a874`
- `OLEAUT32!__imp_SysAllocString` at `0x14004a884`
- `OLEAUT32!__imp_SysAllocString` at `0x14004a896`
- `OLEAUT32!__imp_SysAllocString` at `0x14004a8a7`
- `OLEAUT32!__imp_SysAllocString` at `0x14004a8b8`
- `OLEAUT32!__imp_SysAllocString` at `0x14004a8c9`
- `OLEAUT32!__imp_SysAllocString` at `0x14004a8da`
- `OLEAUT32!__imp_SysAllocString` at `0x14004a8ec`
- `OLEAUT32!__imp_SysFreeString` at `0x14004adb4`
- `OLEAUT32!__imp_SysFreeString` at `0x14004adbe`
- `OLEAUT32!__imp_SysFreeString` at `0x14004adc8`
- `OLEAUT32!__imp_SysFreeString` at `0x14004add2`
- `OLEAUT32!__imp_SysFreeString` at `0x14004addc`
- `OLEAUT32!__imp_SysFreeString` at `0x14004ade5`
- `OLEAUT32!__imp_SysFreeString` at `0x14004adee`
- `OLEAUT32!__imp_SysFreeString` at `0x14004adf7`
- `OLEAUT32!__imp_SysFreeString` at `0x14004ae00`
- `OLEAUT32!__imp_SysFreeString` at `0x14004ae0a`
- `OLEAUT32!__imp_SysFreeString` at `0x14004ae14`
- `OLEAUT32!__imp_SysFreeString` at `0x14004ae1e`
- `OLEAUT32!__imp_SysFreeString` at `0x14004ae28`
- `OLEAUT32!__imp_SysFreeString` at `0x14004ae31`
- `OLEAUT32!__imp_SysFreeString` at `0x14004ae3a`
- `OLEAUT32!__imp_SysFreeString` at `0x14004adb4`
- `OLEAUT32!__imp_SysFreeString` at `0x14004adbe`
- `OLEAUT32!__imp_SysFreeString` at `0x14004adc8`
- `OLEAUT32!__imp_SysFreeString` at `0x14004add2`
- `OLEAUT32!__imp_SysFreeString` at `0x14004addc`
- `OLEAUT32!__imp_SysFreeString` at `0x14004ade5`
- `OLEAUT32!__imp_SysFreeString` at `0x14004adee`
- `OLEAUT32!__imp_SysFreeString` at `0x14004adf7`
- `OLEAUT32!__imp_SysFreeString` at `0x14004ae00`
- `OLEAUT32!__imp_SysFreeString` at `0x14004ae0a`
- `OLEAUT32!__imp_SysFreeString` at `0x14004ae14`
- `OLEAUT32!__imp_SysFreeString` at `0x14004ae1e`
- `OLEAUT32!__imp_SysFreeString` at `0x14004ae28`
- `OLEAUT32!__imp_SysFreeString` at `0x14004ae31`
- `OLEAUT32!__imp_SysFreeString` at `0x14004ae3a`
- `OLEAUT32!__imp_VariantInit` at `0x14004a758`
- `OLEAUT32!__imp_VariantInit` at `0x14004a762`
- `OLEAUT32!__imp_VariantInit` at `0x14004a758`
- `OLEAUT32!__imp_VariantInit` at `0x14004a762`
- `OLEAUT32!__imp_VariantClear` at `0x14004a97c`
- `OLEAUT32!__imp_VariantClear` at `0x14004ae44`
- `OLEAUT32!__imp_VariantClear` at `0x14004ae4e`
- `OLEAUT32!__imp_VariantClear` at `0x14004a97c`
- `OLEAUT32!__imp_VariantClear` at `0x14004ae44`
- `OLEAUT32!__imp_VariantClear` at `0x14004ae4e`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x14004ab9e`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x14004ab9e`

## string_xrefs

- `0x14004a85b`: `DSMPathCount`
- `0x14004a87d`: `DSM_Paths`
- `0x14004a8a0`: `DSMPathId`
- `0x14004a8b1`: `PathWeight`
- `0x14004a8c2`: `PrimaryPath`
- `0x14004a88f`: `MPIO_DSM_Path`
- `0x14004ad13`: `CVdsDiskLun::SetLoadBalancePolicy: FindMpioGetDescriptor NOT SUPPORTED`
- `0x14004ad2a`: `CVdsDiskLun::SetLoadBalancePolicy: FindMpioGetDescriptor failed: %lX`
- `0x14004a9f0`: `CVdsDiskLun::SetLoadBalancePolicy: VdsWmiCreateClassInstance DSM_Load_Balance_Policy failed: %X`
- `0x14004aa62`: `CVdsDiskLun::SetLoadBalancePolicy: VdsWmiSetUlongInInstance DSMPathCount failed: %X`
- `0x14004aabe`: `CVdsDiskLun::SetLoadBalancePolicy: VdsWmiCreateVariantArray failed: %X`
- `0x14004abe3`: `CVdsDiskLun::SetLoadBalancePolicy: VdsWmiCreateClassInstance MPIO_DSM_Path failed: %X`
- `0x14004abd7`: `CVdsDiskLun::SetLoadBalancePolicy: VdsWmiSetUlonglongInInstance DSMPathId failed: %X`
- `0x14004abbf`: `CVdsDiskLun::SetLoadBalancePolicy: VdsWmiSetUlongInInstance PathWeight failed: %X`
- `0x14004abb3`: `CVdsDiskLun::SetLoadBalancePolicy: VdsWmiSetUlongInInstance PrimaryPath failed: %X`
- `0x14004ac0e`: `CVdsDiskLun::SetLoadBalancePolicy: VdsWmiSetVariantInInstance DSM_Paths failed: %X`

## pseudocode

```c
// Hidden C++ exception states: #wind=17
__int64 __fastcall CVdsDiskLun::SetLoadBalancePolicy(
        CVdsDiskLun *this,
        unsigned int a2,
        struct _VDS_PATH_POLICY *a3,
        unsigned int a4)
{
  OLECHAR *v8; // r13
  CVdsDiskLun *v9; // r14
  unsigned int v10; // edi
  OLECHAR *v11; // r12
  int v12; // eax
  int v13; // ebx
  OLECHAR *v14; // rdi
  OLECHAR *v15; // rsi
  OLECHAR *v16; // r14
  OLECHAR *v17; // r15
  int Descriptor; // eax
  struct IWbemClassObject *v19; // rbx
  int VariantFromInstance; // eax
  BSTR v21; // r14
  int InstanceOfClass; // eax
  int v23; // eax
  int v24; // eax
  int v25; // eax
  int v26; // eax
  int v27; // eax
  int v28; // eax
  LONG i; // eax
  int v30; // eax
  int v31; // eax
  int v32; // eax
  int v33; // eax
  int v34; // eax
  int v35; // eax
  int MethodArgumentObject; // eax
  int v37; // eax
  int v38; // eax
  int UlongFromInstance; // eax
  int v40; // eax
  BSTR v42; // [rsp+30h] [rbp-D0h]
  unsigned __int16 *v43; // [rsp+38h] [rbp-C8h]
  LONG rgIndices; // [rsp+40h] [rbp-C0h] BYREF
  BSTR v45; // [rsp+48h] [rbp-B8h]
  void *pv; // [rsp+50h] [rbp-B0h] BYREF
  struct IWbemClassObject *v47; // [rsp+58h] [rbp-A8h] BYREF
  struct IWbemServices *v48; // [rsp+60h] [rbp-A0h] BYREF
  int v49; // [rsp+68h] [rbp-98h] BYREF
  __int64 v50; // [rsp+70h] [rbp-90h] BYREF
  __int64 v51; // [rsp+78h] [rbp-88h] BYREF
  __int64 v52; // [rsp+80h] [rbp-80h] BYREF
  struct IWbemClassObject *v53; // [rsp+88h] [rbp-78h] BYREF
  BSTR v54; // [rsp+90h] [rbp-70h]
  BSTR v55; // [rsp+98h] [rbp-68h]
  BSTR v56; // [rsp+A0h] [rbp-60h]
  BSTR v57; // [rsp+A8h] [rbp-58h]
  BSTR v58; // [rsp+B0h] [rbp-50h]
  BSTR v59; // [rsp+B8h] [rbp-48h]
  BSTR v60; // [rsp+C0h] [rbp-40h]
  BSTR v61; // [rsp+C8h] [rbp-38h]
  BSTR bstrString; // [rsp+D0h] [rbp-30h]
  __int64 v63; // [rsp+D8h] [rbp-28h] BYREF
  VARIANTARG pvarg; // [rsp+E0h] [rbp-20h] BYREF
  VARIANTARG v65; // [rsp+F8h] [rbp-8h] BYREF
  _BYTE v66[80]; // [rsp+110h] [rbp+10h] BYREF
  BSTR v67; // [rsp+170h] [rbp+70h]

  v8 = 0;
  v63 = 0;
  v48 = 0;
  v53 = 0;
  v52 = 0;
  v47 = 0;
  pv = 0;
  v50 = 0;
  v51 = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  memset(&v65, 0, sizeof(v65));
  v49 = 0;
  rgIndices = 0;
  CVdsCallTracer::CVdsCallTracer((CVdsCallTracer *)v66, 0x5Eu, "CVdsDiskLun::SetLoadBalancePolicy()");
  VariantInit(&pvarg);
  VariantInit(&v65);
  v9 = (CVdsDiskLun *)((char *)this - 112);
  if ( *((_DWORD *)this + 60) != 3 )
  {
    bstrString = 0;
    v54 = 0;
    v55 = 0;
    v56 = 0;
    v57 = 0;
    v11 = 0;
    v58 = 0;
    v59 = 0;
    v60 = 0;
    v61 = 0;
    v40 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, struct _VDS_PATH_POLICY *, _QWORD))(**((_QWORD **)this + 26) + 40LL))(
            *((_QWORD *)this + 26),
            a2,
            a3,
            a4);
    v13 = v40;
    if ( v40 < 0 )
    {
      VdsTraceW(0, L"CVdsDiskLun::SetLoadBalancePolicy: m_pLunMpio->SetLoadBalancePolicy failed: %X", (unsigned int)v40);
      v14 = 0;
      v15 = 0;
      v16 = 0;
      v17 = 0;
      goto LABEL_62;
    }
    v14 = 0;
    v15 = 0;
    v16 = 0;
    v17 = 0;
    goto LABEL_61;
  }
  if ( CVdsService::m_hIscsidscModule )
  {
    bstrString = SysAllocString(L"root\\wmi");
    v54 = SysAllocString(L"InstanceName");
    v55 = SysAllocString(L"DSM_LB_Operations");
    v56 = SysAllocString(L"DSM_Load_Balance_Policy");
    v57 = SysAllocString(L"Version");
    v11 = SysAllocString(L"LoadBalancePolicy");
    v45 = SysAllocString(L"DSMPathCount");
    v8 = SysAllocString(L"Reserved");
    v43 = SysAllocString(L"DSM_Paths");
    v58 = SysAllocString(L"MPIO_DSM_Path");
    v59 = SysAllocString(L"DSMPathId");
    v60 = SysAllocString(L"PathWeight");
    v61 = SysAllocString(L"PrimaryPath");
    v42 = SysAllocString(L"DsmSetLoadBalancePolicy");
    v67 = SysAllocString(L"Status");
    v12 = VdsWmiConnectToNamespace(bstrString, &v63, &v48);
    v13 = v12;
    if ( v12 < 0 )
    {
      VdsTraceW(0, L"CVdsDiskLun::SetLoadBalancePolicy: VdsWmiConnectToNamespace failed: %X", (unsigned int)v12);
LABEL_6:
      v14 = v42;
      v15 = v43;
      v16 = v67;
      v17 = v45;
LABEL_62:
      SysFreeString(bstrString);
      SysFreeString(v54);
      SysFreeString(v55);
      SysFreeString(v56);
      SysFreeString(v57);
      SysFreeString(v11);
      SysFreeString(v17);
      SysFreeString(v8);
      SysFreeString(v15);
      SysFreeString(v58);
      SysFreeString(v59);
      SysFreeString(v60);
      SysFreeString(v61);
      SysFreeString(v14);
      SysFreeString(v16);
      VariantClear(&pvarg);
      VariantClear(&v65);
      CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v66);
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v51);
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v50);
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&pv);
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v47);
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v52);
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v53);
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v48);
      v10 = v13;
      goto LABEL_63;
    }
    Descriptor = CVdsDiskLun::FindMpioGetDescriptor(v9, v48, &v53);
    v13 = Descriptor;
    if ( Descriptor < 0 )
    {
      if ( Descriptor == -2147212288 )
        VdsTraceW(2, L"CVdsDiskLun::SetLoadBalancePolicy: FindMpioGetDescriptor NOT SUPPORTED", 2147755008LL);
      else
        VdsTraceW(0, L"CVdsDiskLun::SetLoadBalancePolicy: FindMpioGetDescriptor failed: %lX", (unsigned int)Descriptor);
      goto LABEL_6;
    }
    v19 = v53;
    if ( !v53 )
    {
      v13 = -2147024809;
      VdsTraceEx(94, 0, "CVdsDiskLun::SetLoadBalancePolicy, 1, hr=%lX", -2147024809);
      goto LABEL_6;
    }
    VariantClear(&pvarg);
    VariantFromInstance = VdsWmiGetVariantFromInstance(v19, v54, 8u, &pvarg);
    v13 = VariantFromInstance;
    if ( VariantFromInstance < 0 )
    {
      VdsTraceW(
        0,
        L"CVdsDiskLun::SetLoadBalancePolicy: VdsWmiGetVariantStringFromInstance InstanceName failed: %X",
        (unsigned int)VariantFromInstance);
      goto LABEL_6;
    }
    v21 = v55;
    InstanceOfClass = VdsWmiFindInstanceOfClass(v48, v55, pvarg.llVal, &v52);
    v13 = InstanceOfClass;
    if ( InstanceOfClass < 0 )
    {
      VdsTraceW(
        0,
        L"CVdsDiskLun::SetLoadBalancePolicy: VdsWmiFindInstanceOfClass DSM_LB_Operations failed: %X",
        (unsigned int)InstanceOfClass);
      goto LABEL_6;
    }
    v23 = VdsWmiCreateClassInstance(v48, v56, &v47);
    v13 = v23;
    if ( v23 < 0 )
    {
      VdsTraceW(
        0,
        L"CVdsDiskLun::SetLoadBalancePolicy: VdsWmiCreateClassInstance DSM_Load_Balance_Policy failed: %X",
        (unsigned int)v23);
      goto LABEL_6;
    }
    v24 = VdsWmiSetUlongInInstance(v47, v57, 1);
    v13 = v24;
    if ( v24 < 0 )
    {
      VdsTraceW(0, L"CVdsDiskLun::SetLoadBalancePolicy: VdsWmiSetUlongInInstance Version failed: %X", (unsigned int)v24);
      goto LABEL_6;
    }
    v25 = VdsWmiSetUlongInInstance(v47, v11, a2);
    v13 = v25;
    if ( v25 < 0 )
    {
      VdsTraceW(
        0,
        L"CVdsDiskLun::SetLoadBalancePolicy: VdsWmiSetUlongInInstance LoadBalancePolicy failed: %X",
        (unsigned int)v25);
      goto LABEL_6;
    }
    v17 = v45;
    v26 = VdsWmiSetUlongInInstance(v47, v45, a4);
    v13 = v26;
    if ( v26 < 0 )
    {
      VdsTraceW(
        0,
        L"CVdsDiskLun::SetLoadBalancePolicy: VdsWmiSetUlongInInstance DSMPathCount failed: %X",
        (unsigned int)v26);
LABEL_22:
      v15 = v43;
LABEL_23:
      v14 = v42;
LABEL_24:
      v16 = v67;
      goto LABEL_62;
    }
    v27 = VdsWmiSetUlongInInstance(v47, v8, 0);
    v13 = v27;
    if ( v27 < 0 )
    {
      VdsTraceW(
        0,
        L"CVdsDiskLun::SetLoadBalancePolicy: VdsWmiSetUlongInInstance Reserved failed: %X",
        (unsigned int)v27);
      goto LABEL_22;
    }
    v28 = VdsWmiCreateVariantArray(13, a4, &v65);
    v13 = v28;
    if ( v28 < 0 )
    {
      VdsTraceW(0, L"CVdsDiskLun::SetLoadBalancePolicy: VdsWmiCreateVariantArray failed: %X", (unsigned int)v28);
      goto LABEL_22;
    }
    rgIndices = 0;
    for ( i = 0; i < (int)a4; i = ++rgIndices )
    {
      ATL::CComPtrBase<IVdsIscsiPortal>::Release(&pv);
      v30 = VdsWmiCreateClassInstance(v48, v58, &pv);
      v13 = v30;
      if ( v30 < 0 )
      {
        VdsTraceW(
          0,
          L"CVdsDiskLun::SetLoadBalancePolicy: VdsWmiCreateClassInstance MPIO_DSM_Path failed: %X",
          (unsigned int)v30);
        goto LABEL_22;
      }
      v31 = VdsWmiSetUlonglongInInstance(pv, v59, a3[rgIndices].pathId.ullPathId);
      v13 = v31;
      if ( v31 < 0 )
      {
        VdsTraceW(
          0,
          L"CVdsDiskLun::SetLoadBalancePolicy: VdsWmiSetUlonglongInInstance DSMPathId failed: %X",
          (unsigned int)v31);
        goto LABEL_22;
      }
      v32 = VdsWmiSetUlonglongInInstance(pv, v8, 0);
      v13 = v32;
      if ( v32 < 0 )
      {
        VdsTraceW(
          0,
          L"CVdsDiskLun::SetLoadBalancePolicy: VdsWmiSetUlonglongInInstance Reserved failed: %X",
          (unsigned int)v32);
        goto LABEL_22;
      }
      v33 = VdsWmiSetUlongInInstance(pv, v60, a3[rgIndices].ulWeight);
      v13 = v33;
      if ( v33 < 0 )
      {
        VdsTraceW(
          0,
          L"CVdsDiskLun::SetLoadBalancePolicy: VdsWmiSetUlongInInstance PathWeight failed: %X",
          (unsigned int)v33);
        goto LABEL_22;
      }
      v34 = VdsWmiSetUlongInInstance(pv, v61, a3[rgIndices].bPrimaryPath);
      v13 = v34;
      if ( v34 < 0 )
      {
        VdsTraceW(
          0,
          L"CVdsDiskLun::SetLoadBalancePolicy: VdsWmiSetUlongInInstance PrimaryPath failed: %X",
          (unsigned int)v34);
        goto LABEL_22;
      }
      SafeArrayPutElement(v65.parray, &rgIndices, pv);
    }
    v15 = v43;
    v35 = VdsWmiSetVariantInInstance(v47, v43, &v65);
    v13 = v35;
    if ( v35 < 0 )
    {
      VdsTraceW(
        0,
        L"CVdsDiskLun::SetLoadBalancePolicy: VdsWmiSetVariantInInstance DSM_Paths failed: %X",
        (unsigned int)v35);
      goto LABEL_23;
    }
    v14 = v42;
    MethodArgumentObject = VdsWmiGetMethodArgumentObject(v48, v21, v42, &v50);
    v13 = MethodArgumentObject;
    if ( MethodArgumentObject < 0 )
    {
      VdsTraceW(
        0,
        L"CVdsDiskLun::SetLoadBalancePolicy: VdsWmiGetMethodArgumentObject DsmSetLoadBalancePolicy failed: %X",
        (unsigned int)MethodArgumentObject);
      goto LABEL_24;
    }
    v37 = VdsWmiSetObjectInInstance(v50, v11, v47);
    v13 = v37;
    if ( v37 < 0 )
    {
      VdsTraceW(
        0,
        L"CVdsDiskLun::SetLoadBalancePolicy: VdsWmiSetObjectInInstance LoadBalancePolicy failed: %X",
        (unsigned int)v37);
      goto LABEL_24;
    }
    v38 = VdsWmiCallMethod(v48, v52, v42, v50, &v51);
    v13 = v38;
    if ( v38 < 0 )
    {
      VdsTraceW(
        0,
        L"CVdsDiskLun::SetLoadBalancePolicy: VdsWmiCallMethod DsmSetLoadBalancePolicy failed: %X",
        (unsigned int)v38);
      goto LABEL_24;
    }
    v16 = v67;
    UlongFromInstance = VdsWmiGetUlongFromInstance(v51, v67, &v49);
    v13 = UlongFromInstance;
    if ( UlongFromInstance < 0 )
    {
      VdsTraceW(
        0,
        L"CVdsDiskLun::SetLoadBalancePolicy: VdsWmiGetUlongFromInstance Status failed: %X",
        (unsigned int)UlongFromInstance);
      goto LABEL_62;
    }
    if ( v49 )
    {
      VdsTraceW(0, L"CVdsDiskLun::SetLoadBalancePolicy: DsmSetLoadBalancePolicy failed: %X");
      v13 = -2147467259;
      goto LABEL_62;
    }
LABEL_61:
    v13 = 0;
    goto LABEL_62;
  }
  VdsTraceW(0, L"CVdsDiskLun::SetLoadBalancePolicy: Could not load iSCSI library.");
  CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v66);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v51);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v50);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&pv);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v47);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v52);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v53);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v48);
  v10 = -2147212288;
LABEL_63:
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v63);
  return v10;
}

```

## disassembly

```asm
0x14004a6d0  push    rbp
0x14004a6d2  push    rbx
0x14004a6d3  push    rsi
0x14004a6d4  push    rdi
0x14004a6d5  push    r12
0x14004a6d7  push    r13
0x14004a6d9  push    r14
0x14004a6db  push    r15
0x14004a6dd  lea     rbp, [rsp-28h]
0x14004a6e2  sub     rsp, 128h
0x14004a6e9  mov     edi, r9d
0x14004a6ec  mov     rsi, r8
0x14004a6ef  mov     r15d, edx
0x14004a6f2  mov     rbx, rcx
0x14004a6f5  xor     r13d, r13d
0x14004a6f8  mov     [rbp+60h+var_88], r13
0x14004a6fc  mov     [rsp+160h+var_100], r13
0x14004a701  mov     [rbp+60h+var_D8], r13
0x14004a705  mov     [rbp+60h+var_E0], r13
0x14004a709  mov     [rsp+160h+var_108], r13
0x14004a70e  mov     [rsp+160h+pv], r13
0x14004a713  mov     [rsp+160h+var_F0], r13
0x14004a718  mov     [rsp+160h+var_E8], r13
0x14004a71d  xorps   xmm0, xmm0
0x14004a720  xor     eax, eax
0x14004a722  movups  xmmword ptr [rbp+60h+pvarg], xmm0
0x14004a726  mov     qword ptr [rbp+60h+pvarg+10h], rax
0x14004a72a  xorps   xmm1, xmm1
0x14004a72d  movups  xmmword ptr [rbp+60h+var_68], xmm1
0x14004a731  mov     qword ptr [rbp+60h+var_68+10h], rax
0x14004a735  mov     [rsp+160h+var_F8], r13d
0x14004a73a  mov     [rsp+160h+rgIndices], r13d
0x14004a73f  lea     r8, aCvdsdisklunSet_24; "CVdsDiskLun::SetLoadBalancePolicy()"
0x14004a746  lea     edx, [rax+5Eh]
0x14004a749  lea     rcx, [rbp+60h+var_50]
0x14004a74d  call    cs:__imp_??0CVdsCallTracer@@QEAA@KPEBD@Z; CVdsCallTracer::CVdsCallTracer(ulong,char const *)
0x14004a753  nop
0x14004a754  lea     rcx, [rbp+60h+pvarg]; pvarg
0x14004a758  call    cs:__imp_VariantInit
0x14004a75e  lea     rcx, [rbp+60h+var_68]; pvarg
0x14004a762  call    cs:__imp_VariantInit
0x14004a768  lea     r14, [rbx-70h]
0x14004a76c  cmp     dword ptr [r14+160h], 3
0x14004a774  jnz     loc_14004AD36
0x14004a77a  cmp     cs:?m_hIscsidscModule@CVdsService@@2PEAUHINSTANCE__@@EA, r13; HINSTANCE__ * CVdsService::m_hIscsidscModule
0x14004a781  jnz     short loc_14004A7F3
0x14004a783  lea     rdx, aCvdsdisklunSet_41; "CVdsDiskLun::SetLoadBalancePolicy: Coul"...
0x14004a78a  xor     ecx, ecx
0x14004a78c  call    cs:__imp_VdsTraceW
0x14004a792  nop
0x14004a793  lea     rcx, [rbp+60h+var_50]
0x14004a797  call    cs:__imp_??1CVdsCallTracer@@QEAA@XZ; CVdsCallTracer::~CVdsCallTracer(void)
0x14004a79d  nop
0x14004a79e  lea     rcx, [rsp+160h+var_E8]
0x14004a7a3  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x14004a7a8  nop
0x14004a7a9  lea     rcx, [rsp+160h+var_F0]
0x14004a7ae  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x14004a7b3  nop
0x14004a7b4  lea     rcx, [rsp+160h+pv]
0x14004a7b9  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x14004a7be  nop
0x14004a7bf  lea     rcx, [rsp+160h+var_108]
0x14004a7c4  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x14004a7c9  nop
0x14004a7ca  lea     rcx, [rbp+60h+var_E0]
0x14004a7ce  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x14004a7d3  nop
0x14004a7d4  lea     rcx, [rbp+60h+var_D8]
0x14004a7d8  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x14004a7dd  nop
0x14004a7de  lea     rcx, [rsp+160h+var_100]
0x14004a7e3  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x14004a7e8  nop
0x14004a7e9  mov     edi, 80042400h
0x14004a7ee  jmp     loc_14004AEAD
0x14004a7f3  lea     rcx, Source; "root\\wmi"
0x14004a7fa  call    cs:__imp_SysAllocString
0x14004a800  mov     rbx, rax
0x14004a803  mov     [rbp+60h+bstrString], rax
0x14004a807  lea     rcx, aInstancename; "InstanceName"
0x14004a80e  call    cs:__imp_SysAllocString
0x14004a814  mov     [rbp+60h+var_D0], rax
0x14004a818  lea     rcx, aDsmLbOperation; "DSM_LB_Operations"
0x14004a81f  call    cs:__imp_SysAllocString
0x14004a825  mov     [rbp+60h+var_C8], rax
0x14004a829  lea     rcx, aDsmLoadBalance; "DSM_Load_Balance_Policy"
0x14004a830  call    cs:__imp_SysAllocString
0x14004a836  mov     [rbp+60h+var_C0], rax
0x14004a83a  lea     rcx, aVersion; "Version"
0x14004a841  call    cs:__imp_SysAllocString
0x14004a847  mov     [rbp+60h+var_B8], rax
0x14004a84b  lea     rcx, aLoadbalancepol; "LoadBalancePolicy"
0x14004a852  call    cs:__imp_SysAllocString
0x14004a858  mov     r12, rax
0x14004a85b  lea     rcx, aDsmpathcount; "DSMPathCount"
0x14004a862  call    cs:__imp_SysAllocString
0x14004a868  mov     [rsp+160h+var_118], rax
0x14004a86d  lea     rcx, aReserved; "Reserved"
0x14004a874  call    cs:__imp_SysAllocString
0x14004a87a  mov     r13, rax
0x14004a87d  lea     rcx, aDsmPaths; "DSM_Paths"
0x14004a884  call    cs:__imp_SysAllocString
0x14004a88a  mov     [rsp+160h+var_128], rax
0x14004a88f  lea     rcx, aMpioDsmPath; "MPIO_DSM_Path"
0x14004a896  call    cs:__imp_SysAllocString
0x14004a89c  mov     [rbp+60h+var_B0], rax
0x14004a8a0  lea     rcx, aDsmpathid; "DSMPathId"
0x14004a8a7  call    cs:__imp_SysAllocString
0x14004a8ad  mov     [rbp+60h+var_A8], rax
0x14004a8b1  lea     rcx, aPathweight; "PathWeight"
0x14004a8b8  call    cs:__imp_SysAllocString
0x14004a8be  mov     [rbp+60h+var_A0], rax
0x14004a8c2  lea     rcx, aPrimarypath; "PrimaryPath"
0x14004a8c9  call    cs:__imp_SysAllocString
0x14004a8cf  mov     [rbp+60h+var_98], rax
0x14004a8d3  lea     rcx, aDsmsetloadbala; "DsmSetLoadBalancePolicy"
0x14004a8da  call    cs:__imp_SysAllocString
0x14004a8e0  mov     [rsp+160h+var_130], rax
0x14004a8e5  lea     rcx, aStatus; "Status"
0x14004a8ec  call    cs:__imp_SysAllocString
0x14004a8f2  mov     [rbp+60h+arg_0], rax
0x14004a8f6  lea     r8, [rsp+160h+var_100]
0x14004a8fb  lea     rdx, [rbp+60h+var_88]
0x14004a8ff  mov     rcx, rbx
0x14004a902  call    cs:__imp_VdsWmiConnectToNamespace
0x14004a908  mov     ebx, eax
0x14004a90a  test    eax, eax
0x14004a90c  jns     short loc_14004A938
0x14004a90e  lea     rdx, aCvdsdisklunSet_2; "CVdsDiskLun::SetLoadBalancePolicy: VdsW"...
0x14004a915  mov     r8d, eax
0x14004a918  xor     ecx, ecx
0x14004a91a  call    cs:__imp_VdsTraceW
0x14004a920  mov     rdi, [rsp+160h+var_130]
0x14004a925  mov     rsi, [rsp+160h+var_128]
0x14004a92a  mov     r14, [rbp+60h+arg_0]
0x14004a92e  mov     r15, [rsp+160h+var_118]
0x14004a933  jmp     loc_14004ADB0
0x14004a938  lea     r8, [rbp+60h+var_D8]; struct IWbemClassObject **
0x14004a93c  mov     rdx, [rsp+160h+var_100]; struct IWbemServices *
0x14004a941  mov     rcx, r14; this
0x14004a944  call    ?FindMpioGetDescriptor@CVdsDiskLun@@AEAAJPEAUIWbemServices@@PEAPEAUIWbemClassObject@@@Z; CVdsDiskLun::FindMpioGetDescriptor(IWbemServices *,IWbemClassObject * *)
0x14004a949  mov     ebx, eax
0x14004a94b  test    eax, eax
0x14004a94d  js      loc_14004AD07
0x14004a953  mov     rbx, [rbp+60h+var_D8]
0x14004a957  test    rbx, rbx
0x14004a95a  jnz     short loc_14004A978
0x14004a95c  mov     ebx, 80070057h
0x14004a961  mov     r9d, ebx
0x14004a964  lea     r8, aCvdsdisklunSet_4; "CVdsDiskLun::SetLoadBalancePolicy, 1, h"...
0x14004a96b  xor     edx, edx
0x14004a96d  lea     ecx, [rdx+5Eh]
0x14004a970  call    cs:__imp_VdsTraceEx
0x14004a976  jmp     short loc_14004A920
0x14004a978  lea     rcx, [rbp+60h+pvarg]; pvarg
0x14004a97c  call    cs:__imp_VariantClear
0x14004a982  mov     r8d, 8; unsigned __int16
0x14004a988  lea     r9, [rbp+60h+pvarg]; struct tagVARIANT *
0x14004a98c  mov     rdx, [rbp+60h+var_D0]; unsigned __int16 *
0x14004a990  mov     rcx, rbx; struct IWbemClassObject *
0x14004a993  call    ?VdsWmiGetVariantFromInstance@@YAJPEAUIWbemClassObject@@PEAGGPEAUtagVARIANT@@@Z; VdsWmiGetVariantFromInstance(IWbemClassObject *,ushort *,ushort,tagVARIANT *)
0x14004a998  mov     ebx, eax
0x14004a99a  test    eax, eax
0x14004a99c  jns     short loc_14004A9AA
0x14004a99e  lea     rdx, aCvdsdisklunSet_3; "CVdsDiskLun::SetLoadBalancePolicy: VdsW"...
0x14004a9a5  jmp     loc_14004A915
0x14004a9aa  lea     r9, [rbp+60h+var_E0]
0x14004a9ae  mov     r8, qword ptr [rbp+60h+pvarg+8]
0x14004a9b2  mov     r14, [rbp+60h+var_C8]
0x14004a9b6  mov     rdx, r14
0x14004a9b9  mov     rcx, [rsp+160h+var_100]
0x14004a9be  call    cs:__imp_VdsWmiFindInstanceOfClass
0x14004a9c4  mov     ebx, eax
0x14004a9c6  test    eax, eax
0x14004a9c8  jns     short loc_14004A9D6
0x14004a9ca  lea     rdx, aCvdsdisklunSet_43; "CVdsDiskLun::SetLoadBalancePolicy: VdsW"...
0x14004a9d1  jmp     loc_14004A915
0x14004a9d6  lea     r8, [rsp+160h+var_108]
0x14004a9db  mov     rdx, [rbp+60h+var_C0]
0x14004a9df  mov     rcx, [rsp+160h+var_100]
0x14004a9e4  call    cs:__imp_VdsWmiCreateClassInstance
0x14004a9ea  mov     ebx, eax
0x14004a9ec  test    eax, eax
0x14004a9ee  jns     short loc_14004A9FC
0x14004a9f0  lea     rdx, aCvdsdisklunSet_13; "CVdsDiskLun::SetLoadBalancePolicy: VdsW"...
0x14004a9f7  jmp     loc_14004A915
0x14004a9fc  mov     r8d, 1
0x14004aa02  mov     rdx, [rbp+60h+var_B8]
0x14004aa06  mov     rcx, [rsp+160h+var_108]
0x14004aa0b  call    cs:__imp_VdsWmiSetUlongInInstance
0x14004aa11  mov     ebx, eax
0x14004aa13  test    eax, eax
0x14004aa15  jns     short loc_14004AA23
0x14004aa17  lea     rdx, aCvdsdisklunSet_44; "CVdsDiskLun::SetLoadBalancePolicy: VdsW"...
0x14004aa1e  jmp     loc_14004A915
0x14004aa23  mov     r8d, r15d
0x14004aa26  mov     rdx, r12
0x14004aa29  mov     rcx, [rsp+160h+var_108]
0x14004aa2e  call    cs:__imp_VdsWmiSetUlongInInstance
0x14004aa34  mov     ebx, eax
0x14004aa36  test    eax, eax
0x14004aa38  jns     short loc_14004AA46
0x14004aa3a  lea     rdx, aCvdsdisklunSet_11; "CVdsDiskLun::SetLoadBalancePolicy: VdsW"...
0x14004aa41  jmp     loc_14004A915
0x14004aa46  mov     r8d, edi
0x14004aa49  mov     r15, [rsp+160h+var_118]
0x14004aa4e  mov     rdx, r15
0x14004aa51  mov     rcx, [rsp+160h+var_108]
0x14004aa56  call    cs:__imp_VdsWmiSetUlongInInstance
0x14004aa5c  mov     ebx, eax
0x14004aa5e  test    eax, eax
0x14004aa60  jns     short loc_14004AA87
0x14004aa62  lea     rdx, aCvdsdisklunSet_8; "CVdsDiskLun::SetLoadBalancePolicy: VdsW"...
0x14004aa69  mov     r8d, eax
0x14004aa6c  xor     ecx, ecx
0x14004aa6e  call    cs:__imp_VdsTraceW
0x14004aa74  mov     rsi, [rsp+160h+var_128]
0x14004aa79  mov     rdi, [rsp+160h+var_130]
0x14004aa7e  mov     r14, [rbp+60h+arg_0]
0x14004aa82  jmp     loc_14004ADB0
0x14004aa87  xor     r8d, r8d
0x14004aa8a  mov     rdx, r13
0x14004aa8d  mov     rcx, [rsp+160h+var_108]
0x14004aa92  call    cs:__imp_VdsWmiSetUlongInInstance
0x14004aa98  mov     ebx, eax
0x14004aa9a  test    eax, eax
0x14004aa9c  jns     short loc_14004AAA7
0x14004aa9e  lea     rdx, aCvdsdisklunSet_22; "CVdsDiskLun::SetLoadBalancePolicy: VdsW"...
0x14004aaa5  jmp     short loc_14004AA69
0x14004aaa7  mov     ecx, 0Dh
0x14004aaac  lea     r8, [rbp+60h+var_68]
0x14004aab0  mov     edx, edi
0x14004aab2  call    cs:__imp_VdsWmiCreateVariantArray
0x14004aab8  mov     ebx, eax
0x14004aaba  test    eax, eax
0x14004aabc  jns     short loc_14004AAC7
0x14004aabe  lea     rdx, aCvdsdisklunSet_25; "CVdsDiskLun::SetLoadBalancePolicy: VdsW"...
0x14004aac5  jmp     short loc_14004AA69
0x14004aac7  mov     [rsp+160h+rgIndices], 0
0x14004aacf  xor     eax, eax
0x14004aad1  cmp     eax, edi
0x14004aad3  jge     loc_14004ABEF
0x14004aad9  lea     rcx, [rsp+160h+pv]
0x14004aade  call    ?Release@?$CComPtrBase@UIVdsIscsiPortal@@@ATL@@QEAAXXZ; ATL::CComPtrBase<IVdsIscsiPortal>::Release(void)
0x14004aae3  lea     r8, [rsp+160h+pv]
0x14004aae8  mov     rdx, [rbp+60h+var_B0]
0x14004aaec  mov     rcx, [rsp+160h+var_100]
0x14004aaf1  call    cs:__imp_VdsWmiCreateClassInstance
0x14004aaf7  mov     ebx, eax
0x14004aaf9  test    eax, eax
0x14004aafb  js      loc_14004ABE3
0x14004ab01  movsxd  rax, [rsp+160h+rgIndices]
0x14004ab06  lea     r8, [rax+rax*2]
0x14004ab0a  mov     r8, [rsi+r8*8+8]
0x14004ab0f  mov     rdx, [rbp+60h+var_A8]
0x14004ab13  mov     rcx, [rsp+160h+pv]
0x14004ab18  call    cs:__imp_VdsWmiSetUlonglongInInstance
0x14004ab1e  mov     ebx, eax
0x14004ab20  test    eax, eax
0x14004ab22  js      loc_14004ABD7
0x14004ab28  xor     r8d, r8d
0x14004ab2b  mov     rdx, r13
0x14004ab2e  mov     rcx, [rsp+160h+pv]
0x14004ab33  call    cs:__imp_VdsWmiSetUlonglongInInstance
0x14004ab39  mov     ebx, eax
0x14004ab3b  test    eax, eax
0x14004ab3d  js      loc_14004ABCB
0x14004ab43  movsxd  rax, [rsp+160h+rgIndices]
0x14004ab48  lea     r8, [rax+rax*2]
0x14004ab4c  mov     r8d, [rsi+r8*8+14h]
0x14004ab51  mov     rdx, [rbp+60h+var_A0]
0x14004ab55  mov     rcx, [rsp+160h+pv]
0x14004ab5a  call    cs:__imp_VdsWmiSetUlongInInstance
0x14004ab60  mov     ebx, eax
0x14004ab62  test    eax, eax
0x14004ab64  js      short loc_14004ABBF
0x14004ab66  movsxd  rax, [rsp+160h+rgIndices]
0x14004ab6b  lea     rcx, [rax+rax*2]
0x14004ab6f  xor     r8d, r8d
0x14004ab72  cmp     [rsi+rcx*8+10h], r8d
0x14004ab77  setnz   r8b
0x14004ab7b  mov     rdx, [rbp+60h+var_98]
0x14004ab7f  mov     rcx, [rsp+160h+pv]
0x14004ab84  call    cs:__imp_VdsWmiSetUlongInInstance
0x14004ab8a  mov     ebx, eax
0x14004ab8c  test    eax, eax
0x14004ab8e  js      short loc_14004ABB3
0x14004ab90  mov     r8, [rsp+160h+pv]; pv
0x14004ab95  lea     rdx, [rsp+160h+rgIndices]; rgIndices
0x14004ab9a  mov     rcx, qword ptr [rbp+60h+var_68+8]; psa
0x14004ab9e  call    cs:__imp_SafeArrayPutElement
0x14004aba4  mov     eax, [rsp+160h+rgIndices]
0x14004aba8  inc     eax
0x14004abaa  mov     [rsp+160h+rgIndices], eax
0x14004abae  jmp     loc_14004AAD1
0x14004abb3  lea     rdx, aCvdsdisklunSet_38; "CVdsDiskLun::SetLoadBalancePolicy: VdsW"...
0x14004abba  jmp     loc_14004AA69
0x14004abbf  lea     rdx, aCvdsdisklunSet_33; "CVdsDiskLun::SetLoadBalancePolicy: VdsW"...
0x14004abc6  jmp     loc_14004AA69
  ... truncated ...
```
