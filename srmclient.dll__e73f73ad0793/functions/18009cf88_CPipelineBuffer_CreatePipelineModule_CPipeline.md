# CPipelineBuffer::CreatePipelineModule(CPipeline &)

- ea: `0x18009cf88`
- end: `0x18009dff9`
- name: `?CreatePipelineModule@CPipelineBuffer@@IEAAXAEAVCPipeline@@@Z`
- size: `4209`
- prototype: `void __fastcall(CPipelineBuffer *__hidden this, struct CPipeline *)`
- caller_count: `2`
- callee_count: `24`
- tags: `file_ops, authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x18009ed10`
- `0x18009f134`

## callees

- `0x180001350`
- `0x1800020ba`
- `0x180006a1c`
- `0x180007bd4`
- `0x1800095f4`
- `0x180010bc4`
- `0x1800161d0`
- `0x18001df94`
- `0x1800285e8`
- `0x18005dc7c`
- `0x18006febc`
- `0x1800700b8`
- `0x180070648`
- `0x1800718cc`
- `0x180072598`
- `0x180073a80`
- `0x18009c7b8`
- `0x18009c8e0`
- `0x18009ca34`
- `0x18009cf88`
- `0x18009fc68`
- `0x1800b078a`
- `0x1800b07d0`
- `0x1800d5010`

## import_xrefs

- `ole32!CoCreateInstance` at `0x18009d612`
- `ole32!CoCreateInstance` at `0x18009d612`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x18009d852`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x18009d852`
- `OLEAUT32!__imp_SysFreeString` at `0x18009d83a`
- `OLEAUT32!__imp_SysFreeString` at `0x18009d924`
- `OLEAUT32!__imp_SysFreeString` at `0x18009d930`
- `OLEAUT32!__imp_SysFreeString` at `0x18009d93f`
- `OLEAUT32!__imp_SysFreeString` at `0x18009d94e`
- `OLEAUT32!__imp_SysFreeString` at `0x18009d95d`
- `OLEAUT32!__imp_SysFreeString` at `0x18009d83a`
- `OLEAUT32!__imp_SysFreeString` at `0x18009d924`
- `OLEAUT32!__imp_SysFreeString` at `0x18009d930`
- `OLEAUT32!__imp_SysFreeString` at `0x18009d93f`
- `OLEAUT32!__imp_SysFreeString` at `0x18009d94e`
- `OLEAUT32!__imp_SysFreeString` at `0x18009d95d`
- `OLEAUT32!__imp_SysStringLen` at `0x18009d845`
- `OLEAUT32!__imp_SysStringLen` at `0x18009d845`

## string_xrefs

- `0x18009d35d`: `NetworkService`
- `0x18009d354`: `LocalService`
- `0x18009cfc2`: `base\fs\fsrm\service\pipeline\plbuffer.cpp`
- `0x18009cfd0`: `CPipelineBuffer::CreatePipelineModule`

## pseudocode

```c
// Hidden C++ exception states: #wind=17
void __fastcall CPipelineBuffer::CreatePipelineModule(CPipelineBuffer *this, struct CPipeline *a2)
{
  CPipelineBuffer *v2; // rdi
  int v3; // eax
  int v4; // eax
  int v5; // eax
  int v6; // eax
  int v7; // eax
  int v8; // eax
  int v9; // eax
  int v10; // eax
  const wchar_t *v11; // rsi
  const wchar_t *v12; // rax
  const wchar_t *v13; // rax
  int v14; // eax
  void (__fastcall ***v15)(_QWORD, GUID *, struct IFsrmPipelineModuleImplementation **); // rcx
  int v16; // eax
  int v17; // eax
  HRESULT v18; // eax
  int v19; // eax
  int v20; // eax
  int v21; // eax
  int v22; // eax
  int v23; // eax
  __int64 v24; // r8
  OLECHAR *v25; // rcx
  UINT v26; // eax
  BSTR v27; // rax
  __int64 v28; // rsi
  __int64 v29; // rcx
  __int64 v30; // rsi
  __int64 v31; // rcx
  char v32; // al
  int Hr; // eax
  char v34; // al
  int v35; // eax
  char v36; // al
  int v37; // eax
  char v38; // al
  int v39; // eax
  char v40; // al
  int v41; // eax
  char v42; // al
  int v43; // eax
  char v44; // al
  int v45; // eax
  char v46; // al
  int v47; // eax
  char v48; // al
  int v49; // eax
  char v50; // al
  int v51; // eax
  char v52; // al
  int v53; // eax
  char v54; // al
  char v55; // al
  char v56; // al
  int v57; // eax
  char v58; // al
  int v59; // eax
  char v60; // al
  int v61; // eax
  char v62; // al
  int v63; // eax
  char v64; // al
  int v65; // eax
  char v66; // al
  int v67; // eax
  char v68; // al
  const unsigned __int16 *ErrorText; // rax
  __int64 v70; // r9
  int v71; // eax
  char v72; // al
  __int64 v73; // [rsp+40h] [rbp-298h] BYREF
  BSTR AsBSTR; // [rsp+48h] [rbp-290h] BYREF
  _WORD v75[2]; // [rsp+50h] [rbp-288h] BYREF
  __int16 v76; // [rsp+54h] [rbp-284h] BYREF
  _FsrmAccountType v77; // [rsp+58h] [rbp-280h] BYREF
  struct IFsrmPipelineModuleImplementation *ppv; // [rsp+60h] [rbp-278h] BYREF
  BSTR pbstr; // [rsp+68h] [rbp-270h] BYREF
  unsigned int v80; // [rsp+70h] [rbp-268h] BYREF
  int v81; // [rsp+74h] [rbp-264h] BYREF
  __int64 v82; // [rsp+78h] [rbp-260h] BYREF
  CPipelineBuffer *v83; // [rsp+80h] [rbp-258h]
  BSTR v84; // [rsp+88h] [rbp-250h] BYREF
  __int64 v85; // [rsp+90h] [rbp-248h] BYREF
  int pExceptionObject; // [rsp+98h] [rbp-240h] BYREF
  __int64 v87; // [rsp+A0h] [rbp-238h] BYREF
  BSTR bstrString; // [rsp+A8h] [rbp-230h] BYREF
  BSTR v89; // [rsp+B0h] [rbp-228h] BYREF
  void (__fastcall ***v90)(_QWORD, GUID *, struct IFsrmPipelineModuleImplementation **); // [rsp+B8h] [rbp-220h] BYREF
  BSTR v91; // [rsp+C0h] [rbp-218h]
  void (__fastcall ***v92)(_QWORD, GUID *, struct IFsrmPipelineModuleImplementation **); // [rsp+C8h] [rbp-210h] BYREF
  int v93; // [rsp+D0h] [rbp-208h] BYREF
  __int64 v94; // [rsp+D8h] [rbp-200h] BYREF
  __int64 v95; // [rsp+E0h] [rbp-1F8h] BYREF
  __int64 v96; // [rsp+E8h] [rbp-1F0h] BYREF
  __int64 v97; // [rsp+F0h] [rbp-1E8h] BYREF
  __int64 v98; // [rsp+F8h] [rbp-1E0h] BYREF
  struct _GUID v99; // [rsp+100h] [rbp-1D8h] BYREF
  const unsigned __int16 *v100; // [rsp+110h] [rbp-1C8h] BYREF
  const unsigned __int16 *v101; // [rsp+118h] [rbp-1C0h]
  __int128 v102; // [rsp+120h] [rbp-1B8h]
  _OWORD v103[6]; // [rsp+130h] [rbp-1A8h] BYREF
  int v104; // [rsp+198h] [rbp-140h]
  _com_error *v105; // [rsp+1A0h] [rbp-138h] BYREF
  const exception *v106; // [rsp+1A8h] [rbp-130h] BYREF
  void **v107; // [rsp+1B0h] [rbp-128h] BYREF
  int v108; // [rsp+1B8h] [rbp-120h]
  unsigned int v109; // [rsp+1DCh] [rbp-FCh]
  IID rclsid; // [rsp+260h] [rbp-78h] BYREF
  GUID pguid; // [rsp+270h] [rbp-68h] BYREF
  void *Block[3]; // [rsp+280h] [rbp-58h] BYREF
  unsigned __int64 v113; // [rsp+298h] [rbp-40h]

  v2 = this;
  v83 = this;
  *(_QWORD *)&v99.Data1 = &v100;
  v100 = L"base\\fs\\fsrm\\service\\pipeline\\plbuffer.cpp";
  v101 = L"CPipelineBuffer::CreatePipelineModule";
  *(_QWORD *)&v102 = L"PLBUFFRC";
  *((_QWORD *)&v102 + 1) = 0x1600000082LL;
  LODWORD(v103[0]) = 255;
  v104 = 0x1000000;
  memset_0((char *)v103 + 8, 0, 0x60u);
  CSrmFunctionTracer::CSrmFunctionTracer((__int64)&v107, (const struct CSrmDebugInfo *)&v100, 0);
  ppv = 0;
  v85 = 0;
  v82 = 0;
  v84 = 0;
  v89 = 0;
  bstrString = 0;
  pbstr = 0;
  v91 = 0;
  rclsid = GUID_NULL;
  v77 = FsrmAccountType_Unknown;
  v81 = 0;
  v75[0] = 0;
  v76 = 0;
  v3 = (*(__int64 (__fastcall **)(_QWORD, BSTR *))(**((_QWORD **)v2 + 4) + 112LL))(*((_QWORD *)v2 + 4), &v84);
  v108 = v3;
  if ( v3 < 0 )
  {
    Hr = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v107);
    CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v107, Hr);
    v34 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v107);
    CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v107, 0x95u, v34, 0);
  }
  v108 = v3;
  v4 = (*(__int64 (__fastcall **)(_QWORD, int *))(**((_QWORD **)v2 + 4) + 160LL))(*((_QWORD *)v2 + 4), &v81);
  v108 = v4;
  if ( v4 < 0 )
  {
    v35 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v107);
    CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v107, v35);
    v36 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v107);
    CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v107, 0x96u, v36, 0);
  }
  v108 = v4;
  v5 = (*(__int64 (__fastcall **)(_QWORD, BSTR *))(**((_QWORD **)v2 + 4) + 96LL))(*((_QWORD *)v2 + 4), &pbstr);
  v108 = v5;
  if ( v5 < 0 )
  {
    v37 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v107);
    CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v107, v37);
    v38 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v107);
    CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v107, 0x97u, v38, 0);
  }
  v108 = v5;
  v6 = (*(__int64 (__fastcall **)(_QWORD, _WORD *))(**((_QWORD **)v2 + 4) + 168LL))(*((_QWORD *)v2 + 4), v75);
  v108 = v6;
  if ( v6 < 0 )
  {
    v39 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v107);
    CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v107, v39);
    v40 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v107);
    CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v107, 0x98u, v40, 0);
  }
  v108 = v6;
  v7 = (*(__int64 (__fastcall **)(_QWORD, __int16 *))(**((_QWORD **)v2 + 4) + 184LL))(*((_QWORD *)v2 + 4), &v76);
  v108 = v7;
  if ( v7 < 0 )
  {
    v41 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v107);
    CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v107, v41);
    v42 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v107);
    CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v107, 0x99u, v42, 0);
  }
  v108 = v7;
  v8 = (*(__int64 (__fastcall **)(_QWORD, _FsrmAccountType *))(**((_QWORD **)v2 + 4) + 200LL))(
         *((_QWORD *)v2 + 4),
         &v77);
  v108 = v8;
  if ( v8 < 0 )
  {
    v43 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v107);
    CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v107, v43);
    v44 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v107);
    CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v107, 0x9Au, v44, 0);
  }
  v108 = v8;
  v9 = (*(__int64 (__fastcall **)(_QWORD, BSTR *))(**((_QWORD **)v2 + 4) + 128LL))(*((_QWORD *)v2 + 4), &v89);
  v108 = v9;
  if ( v9 < 0 )
  {
    v45 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v107);
    CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v107, v45);
    v46 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v107);
    CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v107, 0x9Bu, v46, 0);
  }
  v108 = v9;
  v10 = (*(__int64 (__fastcall **)(_QWORD, BSTR *))(**((_QWORD **)v2 + 4) + 144LL))(*((_QWORD *)v2 + 4), &bstrString);
  v108 = v10;
  if ( v10 < 0 )
  {
    v47 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v107);
    CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v107, v47);
    v48 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v107);
    CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v107, 0x9Cu, v48, 0);
  }
  v108 = v10;
  CSrmID::Initialize(&rclsid, (struct CSrmFunctionTracer *)&v107, pbstr, -2147418113);
  if ( v75[0] != 0xFFFF )
  {
    CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v107, -2147200202);
    v32 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v107);
    CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v107, 0x9Fu, v32, 0);
  }
  v108 = 0;
  AsBSTR = v84;
  v73 = 1551;
  CSrmFunctionTracerBase::AddContext(&v107, 1, &v73, &AsBSTR);
  v11 = L"<Uknown>";
  if ( v81 == 1 )
  {
    v12 = L"Storage";
  }
  else if ( v81 == 2 )
  {
    v12 = L"Classifier";
  }
  else
  {
    v12 = L"<Uknown>";
  }
  AsBSTR = (BSTR)v12;
  v73 = 1552;
  CSrmFunctionTracerBase::AddContext(&v107, 1, &v73, &AsBSTR);
  AsBSTR = pbstr;
  v73 = 1553;
  CSrmFunctionTracerBase::AddContext(&v107, 1, &v73, &AsBSTR);
  switch ( v77 )
  {
    case FsrmAccountType_NetworkService:
      v11 = L"NetworkService";
      break;
    case FsrmAccountType_LocalService:
      v11 = L"LocalService";
      break;
    case FsrmAccountType_LocalSystem:
      v11 = L"LocalSystem";
      break;
    case FsrmAccountType_InProc:
      v11 = L"InProc";
      break;
    case FsrmAccountType_External:
      v11 = L"External";
      break;
    case FsrmAccountType_Automatic:
      v11 = L"Automatic";
      break;
  }
  AsBSTR = (BSTR)v11;
  v73 = 1554;
  CSrmFunctionTracerBase::AddContext(&v107, 1, &v73, &AsBSTR);
  v13 = L"TRUE";
  if ( !v75[0] )
    v13 = L"FALSE";
  AsBSTR = (BSTR)v13;
  v73 = 1550;
  CSrmFunctionTracerBase::AddContext(&v107, 1, &v73, &AsBSTR);
  AsBSTR = v89;
  v73 = 1555;
  CSrmFunctionTracerBase::AddContext(&v107, 1, &v73, &AsBSTR);
  AsBSTR = bstrString;
  v73 = 1556;
  CSrmFunctionTracerBase::AddContext(&v107, 1, &v73, &AsBSTR);
  pguid = GUID_NULL;
  CSrmID::CreateNew(&pguid, &v99);
  AsBSTR = CSrmID::GetAsBSTR((CSrmID *)&pguid);
  v91 = AsBSTR;
  try
  {
    v94 = 1950;
    v95 = 0;
    CSrmFunctionTracerBase::AddContext(&v107, 0, &v95, &v94);
    if ( *(_QWORD *)&rclsid.Data1 == *(_QWORD *)&CLSID_FsrmAdsCacheModule.Data1
      && *(_QWORD *)rclsid.Data4 == *(_QWORD *)CLSID_FsrmAdsCacheModule.Data4 )
    {
      v92 = 0;
      v14 = ATL::CComObject<CAdsCache>::CreateInstance(&v92);
      v108 = v14;
      if ( v14 < 0 )
      {
        v49 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v107);
        CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v107, v49);
        v50 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v107);
        CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v107, 0x5Au, v50, 0);
      }
      v108 = v14;
      v15 = v92;
    }
    else if ( *(_QWORD *)&rclsid.Data1 == *(_QWORD *)&CLSID_FsrmFolderClassifierModule.Data1
           && *(_QWORD *)rclsid.Data4 == *(_QWORD *)CLSID_FsrmFolderClassifierModule.Data4 )
    {
      v90 = 0;
      v16 = ATL::CComObject<CFolderClassifier>::CreateInstance(&v90);
      v108 = v16;
      if ( v16 < 0 )
      {
        v51 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v107);
        CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v107, v51);
        v52 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v107);
        CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v107, 0x5Au, v52, 0);
      }
      v108 = v16;
      v15 = v90;
    }
    else
    {
      if ( *(_QWORD *)&rclsid.Data1 != *(_QWORD *)&CLSID_FsrmSecureModule.Data1
        || *(_QWORD *)rclsid.Data4 != *(_QWORD *)CLSID_FsrmSecureModule.Data4 )
      {
        if ( v77 == FsrmAccountType_InProc )
        {
          CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v107, -2147024891);
          v55 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v107);
          CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v107, 0xC1u, v55, 0);
        }
        v108 = 0;
        if ( v77 != FsrmAccountType_External && (unsigned int)(v77 - 1) > 2 && v77 != FsrmAccountType_Automatic )
        {
          CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v107, -2147200234);
          v56 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v107);
          CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v107, 0xC9u, v56, 0);
        }
        v108 = 0;
        if ( v77 == FsrmAccountType_External )
        {
          v18 = CoCreateInstance(&rclsid, 0, 4u, &GUID_b7907906_2b02_4cb5_84a9_fdf54613d6cd, (LPVOID *)&ppv);
          v108 = v18;
          if ( v18 < 0 )
          {
            v57 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v107);
            CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v107, v57);
            v58 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v107);
            CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v107, 0xD3u, v58, 0);
          }
          v108 = v18;
        }
        else
        {
          PlbufferCreateModuleInstance(*(struct CPipeline **)&rclsid.Data1, &rclsid, v77, &ppv);
        }
        goto LABEL_51;
      }
      v73 = 0;
      v17 = ATL::CComObject<CSecureModule>::CreateInstance(&v73);
      v108 = v17;
      if ( v17 < 0 )
      {
        v53 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v107);
        CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v107, v53);
        v54 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v107);
        CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v107, 0x5Au, v54, 0);
      }
      v108 = v17;
      v15 = (void (__fastcall ***)(_QWORD, GUID *, struct IFsrmPipelineModuleImplementation **))v73;
    }
    (**v15)(v15, &GUID_b7907906_2b02_4cb5_84a9_fdf54613d6cd, &ppv);
LABEL_51:
    v96 = 1951;
    v97 = 0;
    CSrmFunctionTracerBase::AddContext(&v107, 0, &v97, &v96);
    v19 = ((__int64 (__fastcall *)(struct IFsrmPipelineModuleImplementation *, _QWORD, __int64 *))ppv->lpVtbl->OnLoad)(
            ppv,
            *((_QWORD *)v2 + 4),
            &v82);
    v108 = v19;
    if ( v19 < 0 )
    {
      v59 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v107);
      CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v107, v59);
      v60 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v107);
      CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v107, 0xE0u, v60, 0);
    }
    v108 = v19;
    if ( ppv )
    {
      ((void (__fastcall *)(struct IFsrmPipelineModuleImplementation *))ppv->lpVtbl->Release)(ppv);
      ppv = 0;
    }
    v98 = 1950;
    *(_QWORD *)&v99.Data1 = 0;
    CSrmFunctionTracerBase::AddContext(&v107, 0, &v99, &v98);
    v20 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v82 + 56LL))(v82, &v85);
    v108 = v20;
    if ( v20 < 0 )
    {
      v61 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v107);
      CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v107, v61);
      v62 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v107);
      CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v107, 0xEAu, v62, 0);
    }
    v108 = v20;
    v87 = 0;
    v21 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v85)(
            v85,
            &GUID_1951d547_e731_4fa8_865f_75449f0cee65,
            &v87);
    v108 = v21;
    if ( v21 < 0 )
    {
      v63 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v107);
      CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v107, v63);
      v64 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v107);
      CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v107, 0xEFu, v64, 0);
    }
    v108 = v21;
    v22 = (*(__int64 (__fastcall **)(__int64, BSTR))(*(_QWORD *)v87 + 80LL))(v87, AsBSTR);
    v108 = v22;
    if ( v22 < 0 )
    {
      v65 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v107);
      CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v107, v65);
      v66 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v107);
      CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v107, 0xF3u, v66, 0);
    }
    v108 = v22;
    if ( v87 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v87 + 16LL))(v87);
  }
  catch ( long v93 )
  {
    CSrmFunctionTracer::HandleHresultException(
      (CSrmFunctionTracer *)&v107,
      v93,
      L"base\\fs\\fsrm\\service\\pipeline\\plbuffer.cpp",
      L"PLBUFFRC",
      L"CPipelineBuffer::CreatePipelineModule",
      0xF5u,
      v109);
    v2 = v83;
  }
  catch ( _com_error *v105 )
  {
    CSrmFunctionTracer::HandleComException(
      (CSrmFunctionTracer *)&v107,
      v105,
      L"base\\fs\\fsrm\\service\\pipeline\\plbuffer.cpp",
      L"PLBUFFRC",
      L"CPipelineBuffer::CreatePipelineModule",
      0xF5u,
      v109);
  }
  catch ( std::bad_alloc )
  {
    CSrmFunctionTracer::HandleStdBadAllocException(
      (CSrmFunctionTracer *)&v107,
      L"base\\fs\\fsrm\\service\\pipeline\\plbuffer.cpp",
      L"PLBUFFRC",
      L"CPipelineBuffer::CreatePipelineModule",
      0xF5u,
      v109);
    v2 = v83;
  }
  catch ( const exception *v106 )
  {
    CSrmFunctionTracer::HandleStdGenericException(
      (CSrmFunctionTracer *)&v107,
      v106,
      L"base\\fs\\fsrm\\service\\pipeline\\plbuffer.cpp",
      L"PLBUFFRC",
      L"CPipelineBuffer::CreatePipelineModule",
      0xF5u,
      v109);
  }
  if ( v108 < 0 )
  {
    ErrorText = (const unsigned __int16 *)CSrmFunctionTracerBase::GetErrorText(&v107, Block);
    if ( *((_QWORD *)ErrorText + 3) >= 8u )
      ErrorText = *(const unsigned __int16 **)ErrorText;
    LODWORD(v100) = -2147205097;
    v101 = ErrorText;
    v102 = 0;
    memset(v103, 0, 48);
    CSrmFunctionTracer::LogEvent(
      (CSrmFunctionTracer *)&v107,
      251,
      1u,
      v70,
      (const struct EventLogMessageContent *)&v100);
    if ( v113 >= 8 )
      operator delete(Block[0]);
    v113 = 7;
    Block[2] = 0;
    LOWORD(Block[0]) = 0;
    v108 = -2147200150;
    v71 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v107);
    CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v107, v71);
    v72 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v107);
    CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v107, 0xFDu, v72, 0);
  }
  v80 = 0;
  v23 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v82 + 80LL))(v82, &v80);
  v108 = v23;
  if ( v23 < 0 )
  {
    v67 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v107);
    CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v107, v67);
    v68 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v107);
    CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v107, 0x101u, v68, 0);
  }
  v108 = v23;
  CFsrmTargetProcessHandle::InitializeFromPID((CPipelineBuffer *)((char *)v2 + 96), v80);
  v24 = -1;
  do
    ++v24;
  while ( v84[v24] );
  std::wstring::assign((char *)v2 + 40, v84);
  v25 = pbstr;
  if ( *((BSTR *)v2 + 10) != pbstr )
  {
    if ( *((_QWORD *)v2 + 10) )
    {
      SysFreeString(*((BSTR *)v2 + 10));
      v25 = pbstr;
    }
    v26 = SysStringLen(v25);
    v27 = SysAllocStringLen(pbstr, v26);
    if ( !v27 && pbstr )
    {
      pExceptionObject = -2147024882;
      throw (long *)&pExceptionObject;
    }
    *((_QWORD *)v2 + 10) = v27;
  }
  *((_DWORD *)v2 + 4) = v77;
  *((_DWORD *)v2 + 36) = v80;
  *((_BYTE *)v2 + 9) = v76 == -1;
  v28 = v85;
  if ( *((_QWORD *)v2 + 11) != v85 )
  {
    if ( v85 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v85 + 8LL))(v85);
    v29 = *((_QWORD *)v2 + 11);
    if ( v29 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
    *((_QWORD *)v2 + 11) = v28;
  }
  v30 = v82;
  if ( *((_QWORD *)v2 + 16) != v82 )
  {
    if ( v82 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v82 + 8LL))(v82);
    v31 = *((_QWORD *)v2 + 16);
    if ( v31 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
    *((_QWORD *)v2 + 16) = v30;
  }
  v91 = 0;
  *((_QWORD *)v2 + 17) = AsBSTR;
  CPipelineBuffer::InitializeSupportedExtensions(v2);
  SysFreeString(0);
  SysFreeString(pbstr);
  SysFreeString(bstrString);
  SysFreeString(v89);
  SysFreeString(v84);
  if ( v82 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v82 + 16LL))(v82);
  if ( v85 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v85 + 16LL))(v85);
  if ( ppv )
    ((void (__fastcall *)(struct IFsrmPipelineModuleImplementation *))ppv->lpVtbl->Release)(ppv);
  v107 = &CSrmFunctionTracer::`vftable';
  CSrmFunctionTracerBase::~CSrmFunctionTracerBase((CSrmFunctionTracerBase *)&v107);
}

```

## disassembly

```asm
0x18009cf88  mov     r11, rsp
0x18009cf8b  push    rbx
0x18009cf8c  push    rsi
0x18009cf8d  push    rdi
0x18009cf8e  push    r14
0x18009cf90  sub     rsp, 2B8h
0x18009cf97  mov     rax, cs:__security_cookie
0x18009cf9e  xor     rax, rsp
0x18009cfa1  mov     [rsp+2D8h+var_30], rax
0x18009cfa9  mov     rdi, rcx
0x18009cfac  mov     [rsp+2D8h+var_258], rcx
0x18009cfb4  lea     rax, [r11-1C8h]
0x18009cfbb  mov     [r11-1D8h], rax
0x18009cfc2  lea     rax, aBaseFsFsrmServ_11; "base\\fs\\fsrm\\service\\pipeline\\plbu"...
0x18009cfc9  mov     [r11-1C8h], rax
0x18009cfd0  lea     rax, aCpipelinebuffe_0; "CPipelineBuffer::CreatePipelineModule"
0x18009cfd7  mov     [r11-1C0h], rax
0x18009cfde  lea     rax, aPlbuffrc; "PLBUFFRC"
0x18009cfe5  mov     [r11-1B8h], rax
0x18009cfec  mov     [rsp+2D8h+var_1B0], 82h
0x18009cff7  mov     [rsp+2D8h+var_1AC], 16h
0x18009d002  mov     dword ptr [rsp+2D8h+var_1A8], 0FFh
0x18009d00d  xor     ebx, ebx
0x18009d00f  mov     [rsp+2D8h+var_140], 1000000h
0x18009d01a  xor     edx, edx; Val
0x18009d01c  lea     r8d, [rbx+60h]; Size
0x18009d020  lea     rcx, [r11-1A0h]; void *
0x18009d027  call    memset_0
0x18009d02c  nop
0x18009d02d  xor     r8d, r8d
0x18009d030  lea     rdx, [rsp+2D8h+var_1C8]
0x18009d038  lea     rcx, [rsp+2D8h+var_128]
0x18009d040  call    ??0CSrmFunctionTracer@@QEAA@UCSrmDebugInfo@@PEBG@Z; CSrmFunctionTracer::CSrmFunctionTracer(CSrmDebugInfo,ushort const *)
0x18009d045  nop
0x18009d046  mov     [rsp+2D8h+var_278], rbx
0x18009d04b  mov     [rsp+2D8h+var_248], rbx
0x18009d053  mov     [rsp+2D8h+var_260], rbx
0x18009d058  mov     [rsp+2D8h+var_250], rbx
0x18009d060  mov     [rsp+2D8h+var_228], rbx
0x18009d068  mov     [rsp+2D8h+bstrString], rbx
0x18009d070  mov     [rsp+2D8h+pbstr], rbx
0x18009d075  mov     [rsp+2D8h+var_218], rbx
0x18009d07d  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18009d084  movdqu  xmmword ptr [rsp+2D8h+rclsid.Data1], xmm0
0x18009d08d  mov     [rsp+2D8h+var_280], ebx
0x18009d091  mov     [rsp+2D8h+var_264], ebx
0x18009d095  mov     [rsp+2D8h+var_288], bx
0x18009d09a  mov     [rsp+2D8h+var_284], bx
0x18009d09f  mov     rcx, [rdi+20h]
0x18009d0a3  mov     rax, [rcx]
0x18009d0a6  lea     rdx, [rsp+2D8h+var_250]
0x18009d0ae  mov     rax, [rax+70h]
0x18009d0b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009d0b7  mov     [rsp+2D8h+var_120], eax
0x18009d0be  test    eax, eax
0x18009d0c0  js      loc_18009DA15
0x18009d0c6  mov     [rsp+2D8h+var_120], eax
0x18009d0cd  mov     rcx, [rdi+20h]
0x18009d0d1  mov     rax, [rcx]
0x18009d0d4  lea     rdx, [rsp+2D8h+var_264]
0x18009d0d9  mov     rax, [rax+0A0h]
0x18009d0e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009d0e5  mov     [rsp+2D8h+var_120], eax
0x18009d0ec  test    eax, eax
0x18009d0ee  js      loc_18009DA57
0x18009d0f4  mov     [rsp+2D8h+var_120], eax
0x18009d0fb  mov     rcx, [rdi+20h]
0x18009d0ff  mov     rax, [rcx]
0x18009d102  lea     rdx, [rsp+2D8h+pbstr]
0x18009d107  mov     rax, [rax+60h]
0x18009d10b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009d110  mov     [rsp+2D8h+var_120], eax
0x18009d117  test    eax, eax
0x18009d119  js      loc_18009DA99
0x18009d11f  mov     [rsp+2D8h+var_120], eax
0x18009d126  mov     rcx, [rdi+20h]
0x18009d12a  mov     rax, [rcx]
0x18009d12d  lea     rdx, [rsp+2D8h+var_288]
0x18009d132  mov     rax, [rax+0A8h]
0x18009d139  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009d13e  mov     [rsp+2D8h+var_120], eax
0x18009d145  test    eax, eax
0x18009d147  js      loc_18009DADB
0x18009d14d  mov     [rsp+2D8h+var_120], eax
0x18009d154  mov     rcx, [rdi+20h]
0x18009d158  mov     rax, [rcx]
0x18009d15b  lea     rdx, [rsp+2D8h+var_284]
0x18009d160  mov     rax, [rax+0B8h]
0x18009d167  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009d16c  mov     [rsp+2D8h+var_120], eax
0x18009d173  test    eax, eax
0x18009d175  js      loc_18009DB1D
0x18009d17b  mov     [rsp+2D8h+var_120], eax
0x18009d182  mov     rcx, [rdi+20h]
0x18009d186  mov     rax, [rcx]
0x18009d189  lea     rdx, [rsp+2D8h+var_280]
0x18009d18e  mov     rax, [rax+0C8h]
0x18009d195  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009d19a  mov     [rsp+2D8h+var_120], eax
0x18009d1a1  test    eax, eax
0x18009d1a3  js      loc_18009DB5F
0x18009d1a9  mov     [rsp+2D8h+var_120], eax
0x18009d1b0  mov     rcx, [rdi+20h]
0x18009d1b4  mov     rax, [rcx]
0x18009d1b7  lea     rdx, [rsp+2D8h+var_228]
0x18009d1bf  mov     rax, [rax+80h]
0x18009d1c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009d1cb  mov     [rsp+2D8h+var_120], eax
0x18009d1d2  test    eax, eax
0x18009d1d4  js      loc_18009DBA1
0x18009d1da  mov     [rsp+2D8h+var_120], eax
0x18009d1e1  mov     rcx, [rdi+20h]
0x18009d1e5  mov     rax, [rcx]
0x18009d1e8  lea     rdx, [rsp+2D8h+bstrString]
0x18009d1f0  mov     rax, [rax+90h]
0x18009d1f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009d1fc  mov     [rsp+2D8h+var_120], eax
0x18009d203  test    eax, eax
0x18009d205  js      loc_18009DBE3
0x18009d20b  mov     [rsp+2D8h+var_120], eax
0x18009d212  mov     r9d, 8000FFFFh; int
0x18009d218  mov     r8, [rsp+2D8h+pbstr]; lpsz
0x18009d21d  lea     rdx, [rsp+2D8h+var_128]; this
0x18009d225  lea     rcx, [rsp+2D8h+rclsid]; pclsid
0x18009d22d  call    ?Initialize@CSrmID@@QEAAXAEAVCSrmFunctionTracer@@PEBGJ@Z; CSrmID::Initialize(CSrmFunctionTracer &,ushort const *,long)
0x18009d232  mov     eax, [rsp+2D8h+var_120]
0x18009d239  mov     [rsp+2D8h+var_120], eax
0x18009d240  or      r14, 0FFFFFFFFFFFFFFFFh
0x18009d244  lea     rcx, [rsp+2D8h+var_128]; this
0x18009d24c  cmp     [rsp+2D8h+var_288], r14w
0x18009d252  jnz     loc_18009D9E5
0x18009d258  mov     [rsp+2D8h+var_120], ebx
0x18009d25f  mov     rax, [rsp+2D8h+var_250]
0x18009d267  mov     [rsp+2D8h+var_290], rax
0x18009d26c  mov     [rsp+2D8h+var_298], 60Fh
0x18009d275  lea     r9, [rsp+2D8h+var_290]
0x18009d27a  lea     r8, [rsp+2D8h+var_298]
0x18009d27f  lea     edx, [r14+2]
0x18009d283  call    ?AddContext@CSrmFunctionTracerBase@@QEAAXW4_SrmContextType@@AEBUResIdOrStringParam@@1@Z; CSrmFunctionTracerBase::AddContext(_SrmContextType,ResIdOrStringParam const &,ResIdOrStringParam const &)
0x18009d288  mov     ecx, [rsp+2D8h+var_264]
0x18009d28c  sub     ecx, 1
0x18009d28f  lea     rsi, aUknown; "<Uknown>"
0x18009d296  jz      short loc_18009D2AB
0x18009d298  cmp     ecx, 1
0x18009d29b  jz      short loc_18009D2A2
0x18009d29d  mov     rax, rsi
0x18009d2a0  jmp     short loc_18009D2B2
0x18009d2a2  lea     rax, aClassifier; "Classifier"
0x18009d2a9  jmp     short loc_18009D2B2
0x18009d2ab  lea     rax, aStorage; "Storage"
0x18009d2b2  mov     [rsp+2D8h+var_290], rax
0x18009d2b7  mov     [rsp+2D8h+var_298], 610h
0x18009d2c0  lea     r9, [rsp+2D8h+var_290]
0x18009d2c5  lea     r8, [rsp+2D8h+var_298]
0x18009d2ca  mov     edx, 1
0x18009d2cf  lea     rcx, [rsp+2D8h+var_128]
0x18009d2d7  call    ?AddContext@CSrmFunctionTracerBase@@QEAAXW4_SrmContextType@@AEBUResIdOrStringParam@@1@Z; CSrmFunctionTracerBase::AddContext(_SrmContextType,ResIdOrStringParam const &,ResIdOrStringParam const &)
0x18009d2dc  mov     rax, [rsp+2D8h+pbstr]
0x18009d2e1  mov     [rsp+2D8h+var_290], rax
0x18009d2e6  mov     [rsp+2D8h+var_298], 611h
0x18009d2ef  lea     r9, [rsp+2D8h+var_290]
0x18009d2f4  lea     r8, [rsp+2D8h+var_298]
0x18009d2f9  mov     edx, 1
0x18009d2fe  lea     rcx, [rsp+2D8h+var_128]
0x18009d306  call    ?AddContext@CSrmFunctionTracerBase@@QEAAXW4_SrmContextType@@AEBUResIdOrStringParam@@1@Z; CSrmFunctionTracerBase::AddContext(_SrmContextType,ResIdOrStringParam const &,ResIdOrStringParam const &)
0x18009d30b  mov     ecx, [rsp+2D8h+var_280]
0x18009d30f  sub     ecx, 1
0x18009d312  jz      short loc_18009D35D
0x18009d314  sub     ecx, 1
0x18009d317  jz      short loc_18009D354
0x18009d319  sub     ecx, 1
0x18009d31c  jz      short loc_18009D34B
0x18009d31e  sub     ecx, 1
0x18009d321  jz      short loc_18009D342
0x18009d323  sub     ecx, 1
0x18009d326  jz      short loc_18009D339
0x18009d328  cmp     ecx, 1EFh
0x18009d32e  jnz     short loc_18009D364
0x18009d330  lea     rsi, aAutomatic; "Automatic"
0x18009d337  jmp     short loc_18009D364
0x18009d339  lea     rsi, aExternal; "External"
0x18009d340  jmp     short loc_18009D364
0x18009d342  lea     rsi, aInproc; "InProc"
0x18009d349  jmp     short loc_18009D364
0x18009d34b  lea     rsi, aLocalsystem; "LocalSystem"
0x18009d352  jmp     short loc_18009D364
0x18009d354  lea     rsi, aLocalservice; "LocalService"
0x18009d35b  jmp     short loc_18009D364
0x18009d35d  lea     rsi, aNetworkservice; "NetworkService"
0x18009d364  mov     [rsp+2D8h+var_290], rsi
0x18009d369  mov     [rsp+2D8h+var_298], 612h
0x18009d372  lea     r9, [rsp+2D8h+var_290]
0x18009d377  lea     r8, [rsp+2D8h+var_298]
0x18009d37c  mov     edx, 1
0x18009d381  lea     rcx, [rsp+2D8h+var_128]
0x18009d389  call    ?AddContext@CSrmFunctionTracerBase@@QEAAXW4_SrmContextType@@AEBUResIdOrStringParam@@1@Z; CSrmFunctionTracerBase::AddContext(_SrmContextType,ResIdOrStringParam const &,ResIdOrStringParam const &)
0x18009d38e  lea     rax, aTrue_0; "TRUE"
0x18009d395  lea     rcx, aFalse; "FALSE"
0x18009d39c  cmp     [rsp+2D8h+var_288], bx
0x18009d3a1  cmovz   rax, rcx
0x18009d3a5  mov     [rsp+2D8h+var_290], rax
0x18009d3aa  mov     [rsp+2D8h+var_298], 60Eh
0x18009d3b3  lea     r9, [rsp+2D8h+var_290]
0x18009d3b8  lea     r8, [rsp+2D8h+var_298]
0x18009d3bd  mov     edx, 1
0x18009d3c2  lea     rcx, [rsp+2D8h+var_128]
0x18009d3ca  call    ?AddContext@CSrmFunctionTracerBase@@QEAAXW4_SrmContextType@@AEBUResIdOrStringParam@@1@Z; CSrmFunctionTracerBase::AddContext(_SrmContextType,ResIdOrStringParam const &,ResIdOrStringParam const &)
0x18009d3cf  mov     rax, [rsp+2D8h+var_228]
0x18009d3d7  mov     [rsp+2D8h+var_290], rax
0x18009d3dc  mov     [rsp+2D8h+var_298], 613h
0x18009d3e5  lea     r9, [rsp+2D8h+var_290]
0x18009d3ea  lea     r8, [rsp+2D8h+var_298]
0x18009d3ef  mov     edx, 1
0x18009d3f4  lea     rcx, [rsp+2D8h+var_128]
0x18009d3fc  call    ?AddContext@CSrmFunctionTracerBase@@QEAAXW4_SrmContextType@@AEBUResIdOrStringParam@@1@Z; CSrmFunctionTracerBase::AddContext(_SrmContextType,ResIdOrStringParam const &,ResIdOrStringParam const &)
0x18009d401  mov     rax, [rsp+2D8h+bstrString]
0x18009d409  mov     [rsp+2D8h+var_290], rax
0x18009d40e  mov     [rsp+2D8h+var_298], 614h
0x18009d417  lea     r9, [rsp+2D8h+var_290]
0x18009d41c  lea     r8, [rsp+2D8h+var_298]
0x18009d421  mov     edx, 1
0x18009d426  lea     rcx, [rsp+2D8h+var_128]
0x18009d42e  call    ?AddContext@CSrmFunctionTracerBase@@QEAAXW4_SrmContextType@@AEBUResIdOrStringParam@@1@Z; CSrmFunctionTracerBase::AddContext(_SrmContextType,ResIdOrStringParam const &,ResIdOrStringParam const &)
0x18009d433  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18009d43a  movdqu  xmmword ptr [rsp+2D8h+pguid.Data1], xmm0
0x18009d443  lea     rdx, [rsp+2D8h+var_1D8]; retstr
0x18009d44b  lea     rcx, [rsp+2D8h+pguid]; pguid
0x18009d453  call    ?CreateNew@CSrmID@@QEAA?AU_GUID@@XZ; CSrmID::CreateNew(void)
0x18009d458  lea     rcx, [rsp+2D8h+pguid]; this
0x18009d460  call    ?GetAsBSTR@CSrmID@@QEAAPEAGXZ; CSrmID::GetAsBSTR(void)
0x18009d465  mov     [rsp+2D8h+var_290], rax
0x18009d46a  mov     [rsp+2D8h+var_218], rax
0x18009d472  mov     esi, 79Eh
0x18009d477  mov     [rsp+2D8h+var_200], rsi
0x18009d47f  mov     [rsp+2D8h+var_1F8], rbx
0x18009d487  lea     r9, [rsp+2D8h+var_200]
0x18009d48f  lea     r8, [rsp+2D8h+var_1F8]
0x18009d497  xor     edx, edx
0x18009d499  lea     rcx, [rsp+2D8h+var_128]
0x18009d4a1  call    ?AddContext@CSrmFunctionTracerBase@@QEAAXW4_SrmContextType@@AEBUResIdOrStringParam@@1@Z; CSrmFunctionTracerBase::AddContext(_SrmContextType,ResIdOrStringParam const &,ResIdOrStringParam const &)
0x18009d4a6  mov     rcx, qword ptr [rsp+2D8h+rclsid.Data1]; struct CPipeline *
0x18009d4ae  mov     rax, qword ptr [rsp+2D8h+rclsid.Data4]
0x18009d4b6  cmp     rcx, qword ptr cs:CLSID_FsrmAdsCacheModule.Data1
0x18009d4bd  jnz     short loc_18009D517
0x18009d4bf  cmp     rax, qword ptr cs:CLSID_FsrmAdsCacheModule.Data4
0x18009d4c6  jnz     short loc_18009D517
0x18009d4c8  mov     [rsp+2D8h+var_210], rbx
0x18009d4d0  lea     rcx, [rsp+2D8h+var_210]
0x18009d4d8  call    ?CreateInstance@?$CComObject@VCAdsCache@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<CAdsCache>::CreateInstance(ATL::CComObject<CAdsCache> * *)
0x18009d4dd  mov     [rsp+2D8h+var_120], eax
0x18009d4e4  test    eax, eax
0x18009d4e6  js      loc_18009DC25
0x18009d4ec  mov     [rsp+2D8h+var_120], eax
0x18009d4f3  mov     rcx, [rsp+2D8h+var_210]
0x18009d4fb  mov     rax, [rcx]
0x18009d4fe  lea     r8, [rsp+2D8h+var_278]
0x18009d503  lea     rdx, _GUID_b7907906_2b02_4cb5_84a9_fdf54613d6cd
0x18009d50a  mov     rax, [rax]
0x18009d50d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009d512  jmp     loc_18009D642
0x18009d517  cmp     rcx, qword ptr cs:CLSID_FsrmFolderClassifierModule.Data1
0x18009d51e  jnz     short loc_18009D55E
0x18009d520  cmp     rax, qword ptr cs:CLSID_FsrmFolderClassifierModule.Data4
0x18009d527  jnz     short loc_18009D55E
0x18009d529  mov     [rsp+2D8h+var_220], rbx
0x18009d531  lea     rcx, [rsp+2D8h+var_220]
0x18009d539  call    ?CreateInstance@?$CComObject@VCFolderClassifier@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<CFolderClassifier>::CreateInstance(ATL::CComObject<CFolderClassifier> * *)
0x18009d53e  mov     [rsp+2D8h+var_120], eax
0x18009d545  test    eax, eax
0x18009d547  js      loc_18009DC65
0x18009d54d  mov     [rsp+2D8h+var_120], eax
0x18009d554  mov     rcx, [rsp+2D8h+var_220]
0x18009d55c  jmp     short loc_18009D4FB
0x18009d55e  cmp     rcx, qword ptr cs:CLSID_FsrmSecureModule.Data1
0x18009d565  jnz     short loc_18009D59F
0x18009d567  cmp     rax, qword ptr cs:CLSID_FsrmSecureModule.Data4
0x18009d56e  jnz     short loc_18009D59F
0x18009d570  mov     [rsp+2D8h+var_298], rbx
0x18009d575  lea     rcx, [rsp+2D8h+var_298]
0x18009d57a  call    ?CreateInstance@?$CComObject@VCSecureModule@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<CSecureModule>::CreateInstance(ATL::CComObject<CSecureModule> * *)
0x18009d57f  mov     [rsp+2D8h+var_120], eax
0x18009d586  test    eax, eax
0x18009d588  js      loc_18009DCA5
0x18009d58e  mov     [rsp+2D8h+var_120], eax
0x18009d595  mov     rcx, [rsp+2D8h+var_298]
0x18009d59a  jmp     loc_18009D4FB
0x18009d59f  mov     eax, [rsp+2D8h+var_120]
0x18009d5a6  mov     [rsp+2D8h+var_120], eax
0x18009d5ad  mov     r8d, [rsp+2D8h+var_280]; enum _FsrmAccountType
0x18009d5b2  cmp     r8d, 4
0x18009d5b6  jz      loc_18009DCE5
0x18009d5bc  mov     [rsp+2D8h+var_120], ebx
0x18009d5c3  mov     [rsp+2D8h+var_120], ebx
0x18009d5ca  cmp     r8d, 5
0x18009d5ce  jz      short loc_18009D5E6
0x18009d5d0  lea     eax, [r8-1]
0x18009d5d4  cmp     eax, 2
0x18009d5d7  jbe     short loc_18009D5E6
0x18009d5d9  cmp     r8d, 1F4h
0x18009d5e0  jnz     loc_18009DD1C
  ... truncated ...
```
