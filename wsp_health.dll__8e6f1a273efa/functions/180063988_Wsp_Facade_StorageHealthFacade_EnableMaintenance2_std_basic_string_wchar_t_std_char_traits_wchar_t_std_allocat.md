# Wsp::Facade::StorageHealthFacade::EnableMaintenance2(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,std::unique_ptr<bool,std::default_delete<bool>> const &,std::unique_ptr<bool,std::default_delete<bool>> const &,std::unique_ptr<uint,std::default_delete<uint>> &,std::unique_ptr<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,std::default_delete<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>>> const &,std::unique_ptr<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,std::default_delete<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>>> const &,std::unique_ptr<ushort,std::default_delete<ushort>> &,mi::MiContext &,std::shared_ptr<Wsp::Facade::IExtendedStatus> &)

- ea: `0x180063988`
- end: `0x1800645fd`
- name: `?EnableMaintenance2@StorageHealthFacade@Facade@Wsp@@QEAA?AW4SM_RETURN_CODE@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV?$unique_ptr@_NU?$default_delete@_N@std@@@6@1AEAV?$unique_ptr@IU?$default_delete@I@std@@@6@AEBV?$unique_ptr@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$default_delete@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@6@3AEAV?$unique_ptr@GU?$default_delete@G@std@@@6@AEAVMiContext@mi@@AEAV?$shared_ptr@UIExtendedStatus@Facade@Wsp@@@6@@Z`
- size: `3189`
- prototype: ``
- caller_count: `1`
- callee_count: `65`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800564f0`

## callees

- `0x1800010f8`
- `0x1800011a0`
- `0x1800013d0`
- `0x18000163c`
- `0x1800016d0`
- `0x180002b50`
- `0x1800035c0`
- `0x18000bb84`
- `0x18000bc64`
- `0x18000c2f8`
- `0x18000cd54`
- `0x18000cd9c`
- `0x18000d390`
- `0x18000d524`
- `0x18000da34`
- `0x18000daf8`
- `0x18000e4b8`
- `0x18000f34c`
- `0x180011184`
- `0x180016b30`
- `0x180019720`
- `0x180019d40`
- `0x180035104`
- `0x1800354a4`
- `0x180035980`
- `0x180043be8`
- `0x180053d48`
- `0x180053d6c`
- `0x180055020`
- `0x180055098`
- `0x180058f50`
- `0x180058f88`
- `0x18005905c`
- `0x18005a150`
- `0x18005b518`
- `0x18005b6a8`
- `0x18005b704`
- `0x18005b760`
- `0x18005b7bc`
- `0x18005b820`
- `0x18005b884`
- `0x18005ba14`
- `0x18005ee10`
- `0x18005ee48`
- `0x18005f0f4`
- `0x18005f124`
- `0x18005f8b0`
- `0x18005fcbc`
- `0x18005fe14`
- `0x18005fe44`

## string_xrefs

- `0x18006441a`: `Completed`
- `0x180064035`: `SendCommandMaintenanceMode Failed.`

## pseudocode

```c
// Hidden C++ exception states: #wind=15
__int64 __fastcall Wsp::Facade::StorageHealthFacade::EnableMaintenance2(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        _QWORD *a5,
        const char *a6,
        const char *a7,
        _QWORD *a8,
        std::_Ref_count_base *a9,
        __int64 a10)
{
  bool v12; // di
  __int64 v13; // rax
  int v14; // ecx
  int v15; // r8d
  int v16; // r9d
  char *v17; // rbx
  _QWORD *Instance; // rax
  int SubsystemType; // eax
  unsigned int FaultDomainPhysicalDisks; // ebx
  int v21; // ecx
  int v22; // r8d
  int v23; // r9d
  struct cxl::TraceManager *v24; // rax
  int v25; // ecx
  __int64 SmApiSession; // rax
  struct ProtectedPwd **v27; // rax
  int Cluster; // ebx
  int v29; // r8d
  int v30; // r9d
  struct cxl::TraceManager *v31; // rax
  int v32; // ecx
  int v33; // r8d
  int v34; // r9d
  struct cxl::TraceManager *v35; // rax
  int v36; // ecx
  int v37; // r8d
  int v38; // r9d
  __int64 v39; // rax
  std::_Ref_count_base *v40; // rcx
  __int64 v41; // rcx
  __int64 v42; // rcx
  const wchar_t *v43; // rax
  Wsp::Facade::StorageHealthFacade *v44; // rcx
  __int64 v45; // rax
  const wchar_t *v46; // rax
  Wsp::Facade::StorageHealthFacade *v47; // rcx
  __int64 v48; // rax
  int v49; // ecx
  int v50; // r8d
  int v51; // r9d
  struct cxl::TraceManager *v52; // rax
  int v53; // ecx
  int v54; // r8d
  int v55; // r9d
  struct cxl::TraceManager *v56; // rax
  int v57; // ecx
  int v58; // r8d
  int v59; // r9d
  struct cxl::TraceManager *v60; // rax
  int v61; // ecx
  int v62; // r8d
  int v63; // r9d
  struct cxl::TraceManager *v64; // rax
  const MI_Char *v65; // rax
  const MI_Char *v66; // r8
  const MI_Char *v67; // r9
  int v68; // ecx
  int v69; // r8d
  int v70; // r9d
  struct cxl::TraceManager *v71; // rax
  int v72; // ecx
  int v73; // r8d
  int v74; // r9d
  int v75; // ecx
  int v76; // r8d
  int v77; // r9d
  __int64 v79; // rax
  __int64 v80; // rax
  MI_Uint32 secondsRemaining; // [rsp+28h] [rbp-D8h]
  __int64 v82; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v83; // [rsp+68h] [rbp-98h] BYREF
  char v84; // [rsp+70h] [rbp-90h] BYREF
  char v85; // [rsp+71h] [rbp-8Fh] BYREF
  _BYTE v86[6]; // [rsp+72h] [rbp-8Eh] BYREF
  MI_Uint32 v87[2]; // [rsp+78h] [rbp-88h] BYREF
  _BYTE v88[8]; // [rsp+80h] [rbp-80h] BYREF
  _QWORD v89[2]; // [rsp+88h] [rbp-78h] BYREF
  __int16 v90; // [rsp+98h] [rbp-68h] BYREF
  MI_Context **v91; // [rsp+A0h] [rbp-60h] BYREF
  const char *v92; // [rsp+A8h] [rbp-58h] BYREF
  int v93; // [rsp+B0h] [rbp-50h] BYREF
  const char *v94; // [rsp+B8h] [rbp-48h] BYREF
  std::_Ref_count_base *v95[2]; // [rsp+C0h] [rbp-40h] BYREF
  std::_Ref_count_base *v96[2]; // [rsp+D0h] [rbp-30h] BYREF
  _BYTE *v97; // [rsp+E0h] [rbp-20h] BYREF
  std::_Ref_count_base *v98; // [rsp+E8h] [rbp-18h]
  _BYTE v99[32]; // [rsp+100h] [rbp+0h] BYREF
  _OWORD v100[2]; // [rsp+120h] [rbp+20h] BYREF
  _OWORD v101[2]; // [rsp+140h] [rbp+40h] BYREF
  _BYTE v102[32]; // [rsp+160h] [rbp+60h] BYREF
  unsigned int v103; // [rsp+180h] [rbp+80h] BYREF
  int v104; // [rsp+184h] [rbp+84h] BYREF
  _BYTE v105[147]; // [rsp+188h] [rbp+88h] BYREF
  char v106; // [rsp+21Bh] [rbp+11Bh] BYREF
  int v107; // [rsp+21Ch] [rbp+11Ch]
  _BYTE v108[16]; // [rsp+220h] [rbp+120h] BYREF
  _BYTE v109[64]; // [rsp+230h] [rbp+130h] BYREF
  _BYTE v110[48]; // [rsp+270h] [rbp+170h] BYREF
  _BYTE v111[64]; // [rsp+2A0h] [rbp+1A0h] BYREF
  _BYTE pExceptionObject[112]; // [rsp+2E0h] [rbp+1E0h] BYREF

  v82 = a4;
  v83 = a3;
  v92 = a6;
  v94 = a7;
  v91 = (MI_Context **)a9;
  if ( (unsigned int)dword_18014D6A8 > 5 )
  {
    v87[0] = 3230;
    v89[0] = "Wsp::Facade::StorageHealthFacade::EnableMaintenance2";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      (unsigned int)"Wsp::Facade::StorageHealthFacade::EnableMaintenance2",
      (unsigned int)&word_18012B3EE,
      a3,
      a4,
      (__int64)v89,
      (__int64)v87);
  }
  v12 = 1;
  v86[0] = 1;
  v84 = 1;
  v85 = 0;
  v93 = -1;
  v90 = 1;
  v101[0] = 0;
  v101[1] = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v101[0]) = 0;
  Wsp::Facade::MaintenanceModeStruct::MaintenanceModeStruct((Wsp::Facade::MaintenanceModeStruct *)&v103);
  *(_OWORD *)v96 = 0;
  Wsp::Facade::MaintenanceCommandContext::MaintenanceCommandContext((Wsp::Facade::MaintenanceCommandContext *)v110);
  if ( !(unsigned int)Wsp::Facade::StorageHealthFacade::GetSubsystemType(a1) )
  {
    v79 = std::wstring::wstring(v99, L"non highlyavailable subsystems are not supported");
    v80 = cxl::SMResult(&v91, 59001, v79);
    cxl::Error(pExceptionObject, v80);
    throw (cxl::Exception *)pExceptionObject;
  }
  cxl::load_string(v102, qword_1801599A0, 3001);
  v97 = v102;
  v98 = a9;
  std::function_void___cdecl_unsigned_long__::operator___lambda_326242e5b2d8e6ab3091d2d8bf7fa6f6__0_(v111, &v97);
  std::_Func_class<void,unsigned long>::operator()(v111, 1);
  v100[0] = 0;
  v100[1] = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v100[0]) = 0;
  v13 = cxl::StringWriter::StringWriter(v99, v100);
  cxl::TextWriter::Write<55>(v13);
  std::wstring::wstring(&v97, v100);
  if ( (unsigned int)dword_18014D6A8 > 4 && (unsigned __int8)tlgKeywordOn(&dword_18014D6A8, 0x4000) )
  {
    v89[0] = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(&v97);
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>>(
      v14,
      (unsigned int)&dword_18012B41C,
      v15,
      v16,
      (__int64)v89);
  }
  v17 = (char *)cxl::TraceManager::Instance() + 120;
  cxl::CxlTraits<std::wstring>::WriteTo(v17, &v97);
  cxl::TextWriter::operator<<<cxl::ENDL>(v17);
  std::wstring::_Tidy_deallocate(&v97);
  Instance = (_QWORD *)Wsp::MiSpaceAdapter::GetInstance(&v97);
  Wsp::MiSpaceAdapter::UnpackObjectId(*Instance, (unsigned int)v99, a2, (unsigned int)&v104, (__int64)&v103);
  std::wstring::operator=(v101);
  std::wstring::_Tidy_deallocate(v99);
  if ( v98 )
    std::_Ref_count_base::_Decref(v98);
  SubsystemType = Wsp::Facade::StorageHealthFacade::GetSubsystemType(a1);
  if ( SubsystemType != v104 )
  {
    FaultDomainPhysicalDisks = 1;
    std::wstring::wstring(&v97, L"Subsystem not supported");
    if ( (unsigned int)dword_18014D6A8 > 2 )
    {
      v89[0] = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(&v97);
      v87[0] = 1;
      LODWORD(v83) = 3272;
      v82 = (__int64)"Wsp::Facade::StorageHealthFacade::EnableMaintenance2";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>>(
        v21,
        (unsigned int)&dword_18012B43C,
        v22,
        v23,
        (__int64)&v82,
        (__int64)&v83,
        (__int64)v87,
        (__int64)v89);
    }
    v24 = cxl::TraceManager::Instance();
    LODWORD(v83) = 1;
    v87[0] = 3272;
    cxl::TextWriter::WriteLine<wchar_t,char [53],int,int,wchar_t [24]>(
      (struct cxl::TraceManager *)((char *)v24 + 40),
      (__int64)&v83);
LABEL_13:
    std::wstring::_Tidy_deallocate(&v97);
    goto LABEL_67;
  }
  if ( v103 > 0xC || (v25 = 4640, !_bittest(&v25, v103)) )
  {
    FaultDomainPhysicalDisks = 1;
    goto LABEL_67;
  }
  SmApiSession = Wsp::Facade::StorageHealthFacade::GetSmApiSession(4640, &v97);
  std::shared_ptr<mismpstorage::SPACES_VirtualDisk const>::operator=(v105, SmApiSession);
  if ( v98 )
    std::_Ref_count_base::_Decref(v98);
  v27 = (struct ProtectedPwd **)ClusWmi::DataStore::GetInstance(&v97);
  Cluster = ClusWmi::DataStore::GetCluster(*v27);
  if ( v98 )
    std::_Ref_count_base::_Decref(v98);
  if ( Cluster < 0 )
  {
    v87[0] = Cluster;
    if ( (unsigned int)dword_18014D6A8 > 2 )
    {
      LODWORD(v83) = v87[0];
      LODWORD(v82) = 3295;
      v89[0] = "Wsp::Facade::StorageHealthFacade::EnableMaintenance2";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        dword_18014D6A8,
        (unsigned int)&byte_18012B2F7,
        v29,
        v30,
        (__int64)v89,
        (__int64)&v82,
        (__int64)&v83);
    }
    v31 = cxl::TraceManager::Instance();
    LODWORD(v82) = 3295;
    cxl::TextWriter::WriteLine<wchar_t,char [53],int,long>((struct cxl::TraceManager *)((char *)v31 + 40), (__int64)v87);
    FaultDomainPhysicalDisks = Wsp::MiSpaceAdapter::SmRCFromHResult((unsigned int)Cluster);
    std::wstring::wstring(&v97, L"Failed to Get Cluster");
    if ( FaultDomainPhysicalDisks )
    {
      if ( (unsigned int)dword_18014D6A8 > 2 )
      {
        v89[0] = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(&v97);
        LODWORD(v82) = FaultDomainPhysicalDisks;
        LODWORD(v83) = 3296;
        *(_QWORD *)v87 = "Wsp::Facade::StorageHealthFacade::EnableMaintenance2";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>>(
          v32,
          (unsigned int)&byte_18012B32F,
          v33,
          v34,
          (__int64)v87,
          (__int64)&v83,
          (__int64)&v82,
          (__int64)v89);
      }
      v35 = cxl::TraceManager::Instance();
      LODWORD(v82) = FaultDomainPhysicalDisks;
      LODWORD(v83) = 3296;
      cxl::TextWriter::WriteLine<wchar_t,char [53],int,int,wchar_t [22]>(
        (struct cxl::TraceManager *)((char *)v35 + 40),
        (__int64)&v82);
    }
    else if ( (unsigned int)dword_18014D6A8 > 5 )
    {
      v89[0] = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(&v97);
      LODWORD(v82) = 0;
      LODWORD(v83) = 3296;
      *(_QWORD *)v87 = "Wsp::Facade::StorageHealthFacade::EnableMaintenance2";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>>(
        v36,
        (unsigned int)&word_18012B36E,
        v37,
        v38,
        (__int64)v87,
        (__int64)&v83,
        (__int64)&v82,
        (__int64)v89);
    }
    goto LABEL_13;
  }
  v39 = ClusApi::Facade::FacadeFactory::CreateClusterFacade(&v97, v96);
  std::shared_ptr<mismpstorage::SPACES_VirtualDisk const>::operator=(v108, v39);
  v40 = v98;
  if ( v98 )
    std::_Ref_count_base::_Decref(v98);
  Wsp::Facade::StorageHealthFacade::GetLocalNode(v40, &v103);
  Wsp::Facade::StorageHealthFacade::S2DEnabled(v41, &v103);
  v42 = v83;
  if ( *(_QWORD *)v83 )
    v85 = **(_BYTE **)v83;
  if ( !*a5 )
  {
    if ( v106 )
    {
      v43 = (const wchar_t *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(qword_180159A40);
      Wsp::Facade::StorageHealthFacade::GetMaintenanceModeConfiguration(
        v44,
        v43,
        (void (*)(const wchar_t *, const wchar_t *, void *))Wsp::Facade::_MaintenanceModeTimeoutConfigurationCallback,
        &v93);
      v45 = std::make_unique<unsigned int,unsigned int &,0>(v89, &v93);
      std::unique_ptr<unsigned int>::operator=<std::default_delete<unsigned int>,0>(a5, v45);
      std::unique_ptr<unsigned int>::~unique_ptr<unsigned int>(v89);
    }
    else
    {
      std::unique_ptr<unsigned int>::reset(a5, 0);
    }
  }
  if ( !*a8 )
  {
    v46 = (const wchar_t *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(qword_180159A60);
    Wsp::Facade::StorageHealthFacade::GetMaintenanceModeConfiguration(
      v47,
      v46,
      (void (*)(const wchar_t *, const wchar_t *, void *))Wsp::Facade::_MaintenanceModeValidationLevelConfigurationCallback,
      &v90);
    v48 = std::make_unique<unsigned short,unsigned short &,0>(v89, &v90);
    std::unique_ptr<unsigned short>::operator=<std::default_delete<unsigned short>,0>(a8, v48);
    std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(v89);
  }
  if ( *a8 )
  {
    v12 = (*(_BYTE *)*a8 & 1) != 0;
    v84 = v12;
  }
  if ( !v106 || !v107 )
  {
    std::map<std::wstring,mismpstorage::SPACES_PhysicalDisk>::map<std::wstring,mismpstorage::SPACES_PhysicalDisk>(v95);
    std::map<std::wstring,Wsp::Facade::MaintenanceDisk>::map<std::wstring,Wsp::Facade::MaintenanceDisk>(&v97);
    secondsRemaining = a10;
    FaultDomainPhysicalDisks = Wsp::Facade::StorageHealthFacade::GetFaultDomainPhysicalDisks(
                                 a1,
                                 a2,
                                 (unsigned int)&v103,
                                 (unsigned int)&v97,
                                 (__int64)v95);
    if ( FaultDomainPhysicalDisks )
    {
      std::wstring::wstring(v99, L"GetFaultDomainPhysicalDisks");
      if ( (unsigned int)dword_18014D6A8 > 2 )
      {
        v89[0] = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v99);
        LODWORD(v82) = FaultDomainPhysicalDisks;
        LODWORD(v83) = 3369;
        *(_QWORD *)v87 = "Wsp::Facade::StorageHealthFacade::EnableMaintenance2";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>>(
          v53,
          (unsigned int)byte_18012B279,
          v54,
          v55,
          (__int64)v87,
          (__int64)&v83,
          (__int64)&v82,
          (__int64)v89);
      }
      v56 = cxl::TraceManager::Instance();
      LODWORD(v82) = FaultDomainPhysicalDisks;
      LODWORD(v83) = 3369;
      cxl::TextWriter::WriteLine<wchar_t,char [53],int,int,wchar_t [28]>(
        (struct cxl::TraceManager *)((char *)v56 + 40),
        (__int64)&v82,
        (__int64)L"GetFaultDomainPhysicalDisks");
    }
    else
    {
      if ( !v12
        || (FaultDomainPhysicalDisks = Wsp::Facade::StorageHealthFacade::ValidateAllVirtualDiskHealthy(
                                         a1,
                                         (__int64)&v103,
                                         v95,
                                         a10)) == 0 )
      {
        std::shared_ptr<ClusApi::IStorage>::shared_ptr<ClusApi::IStorage>(v89, v105);
        secondsRemaining = v82;
        FaultDomainPhysicalDisks = Wsp::Facade::StorageHealthFacade::CallMaintenanceOnTargetObject(
                                     &v106,
                                     v109,
                                     &v103,
                                     v86,
                                     v83);
        if ( FaultDomainPhysicalDisks )
        {
          std::wstring::wstring(v99, L"CallMaintenanceOnTargetObject Failed.");
          if ( (unsigned int)dword_18014D6A8 > 2 )
          {
            v92 = (const char *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v99);
            LODWORD(v82) = FaultDomainPhysicalDisks;
            LODWORD(v83) = 3398;
            v94 = "Wsp::Facade::StorageHealthFacade::EnableMaintenance2";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>>(
              v61,
              (unsigned int)byte_18012B1FB,
              v62,
              v63,
              (__int64)&v94,
              (__int64)&v83,
              (__int64)&v82,
              (__int64)&v92);
          }
          v64 = cxl::TraceManager::Instance();
          LODWORD(v82) = FaultDomainPhysicalDisks;
          LODWORD(v83) = 3398;
          cxl::TextWriter::WriteLine<wchar_t,char [53],int,int,wchar_t [38]>(
            (struct cxl::TraceManager *)((char *)v64 + 40),
            (__int64)&v82);
          std::wstring::_Tidy_deallocate(v99);
        }
        std::_Tree<std::_Tmap_traits<std::wstring,Wsp::Facade::MaintenanceDisk,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,Wsp::Facade::MaintenanceDisk>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,Wsp::Facade::MaintenanceDisk,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,Wsp::Facade::MaintenanceDisk>>,0>>(&v97);
        std::_Tree<std::_Tmap_traits<std::wstring,mismpstorage::SPACES_VirtualDisk,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,mismpstorage::SPACES_VirtualDisk>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,mismpstorage::SPACES_VirtualDisk,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,mismpstorage::SPACES_VirtualDisk>>,0>>(v95);
        goto LABEL_67;
      }
      std::wstring::wstring(v99, L"ValidateAllVirtualDiskHealthy");
      if ( (unsigned int)dword_18014D6A8 > 2 )
      {
        v89[0] = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v99);
        LODWORD(v82) = FaultDomainPhysicalDisks;
        LODWORD(v83) = 3378;
        *(_QWORD *)v87 = "Wsp::Facade::StorageHealthFacade::EnableMaintenance2";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>>(
          v57,
          (unsigned int)qword_18012B2B8,
          v58,
          v59,
          (__int64)v87,
          (__int64)&v83,
          (__int64)&v82,
          (__int64)v89);
      }
      v60 = cxl::TraceManager::Instance();
      LODWORD(v82) = FaultDomainPhysicalDisks;
      LODWORD(v83) = 3378;
      cxl::TextWriter::WriteLine<wchar_t,char [53],int,int,wchar_t [30]>(
        (struct cxl::TraceManager *)((char *)v60 + 40),
        (__int64)&v82);
    }
    std::wstring::_Tidy_deallocate(v99);
    std::_Tree<std::_Tmap_traits<std::wstring,Wsp::Facade::MaintenanceDisk,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,Wsp::Facade::MaintenanceDisk>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,Wsp::Facade::MaintenanceDisk,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,Wsp::Facade::MaintenanceDisk>>,0>>(&v97);
    std::_Tree<std::_Tmap_traits<std::wstring,mismpstorage::SPACES_VirtualDisk,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,mismpstorage::SPACES_VirtualDisk>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,mismpstorage::SPACES_VirtualDisk,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,mismpstorage::SPACES_VirtualDisk>>,0>>(v95);
    goto LABEL_67;
  }
  if ( *(_QWORD *)v82 )
    LOBYTE(v42) = **(_BYTE **)v82;
  else
    LOBYTE(v42) = 0;
  v88[0] = v42;
  FaultDomainPhysicalDisks = Wsp::Facade::StorageHealthFacade::SendCommandMaintenanceMode(
                               v42,
                               (__int64)v110,
                               a2,
                               &v103,
                               v86,
                               &v85,
                               v88,
                               &v84,
                               a5);
  if ( FaultDomainPhysicalDisks )
  {
    std::wstring::wstring(&v97, L"SendCommandMaintenanceMode Failed.");
    if ( (unsigned int)dword_18014D6A8 > 2 )
    {
      v89[0] = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(&v97);
      LODWORD(v82) = FaultDomainPhysicalDisks;
      LODWORD(v83) = 3358;
      *(_QWORD *)v87 = "Wsp::Facade::StorageHealthFacade::EnableMaintenance2";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>>(
        v49,
        (unsigned int)&byte_18012B3AF,
        v50,
        v51,
        (__int64)v87,
        (__int64)&v83,
        (__int64)&v82,
        (__int64)v89);
    }
    v52 = cxl::TraceManager::Instance();
    LODWORD(v82) = FaultDomainPhysicalDisks;
    LODWORD(v83) = 3358;
    cxl::TextWriter::WriteLine<wchar_t,char [53],int,int,wchar_t [35]>(
      (struct cxl::TraceManager *)((char *)v52 + 40),
      (__int64)&v82);
    goto LABEL_13;
  }
LABEL_67:
  v65 = (const MI_Char *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v102);
  MI_Context_WriteProgress(*v91, v65, v66, v67, 0x64u, secondsRemaining);
  std::wstring::wstring(&v97, L"Completed");
  if ( FaultDomainPhysicalDisks )
  {
    if ( (unsigned int)dword_18014D6A8 > 2 )
    {
      v91 = (MI_Context **)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(&v97);
      LODWORD(v82) = FaultDomainPhysicalDisks;
      LODWORD(v83) = 3418;
      v92 = "Wsp::Facade::StorageHealthFacade::EnableMaintenance2";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>>(
        v68,
        (unsigned int)word_18012B23A,
        v69,
        v70,
        (__int64)&v92,
        (__int64)&v83,
        (__int64)&v82,
        (__int64)&v91);
    }
    v71 = cxl::TraceManager::Instance();
    LODWORD(v82) = FaultDomainPhysicalDisks;
    LODWORD(v83) = 3418;
    cxl::TextWriter::WriteLine<wchar_t,char [53],int,int,wchar_t [10]>(
      (struct cxl::TraceManager *)((char *)v71 + 40),
      (__int64)&v82);
  }
  else if ( (unsigned int)dword_18014D6A8 > 5 )
  {
    v91 = (MI_Context **)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(&v97);
    LODWORD(v82) = 0;
    LODWORD(v83) = 3418;
    v92 = "Wsp::Facade::StorageHealthFacade::EnableMaintenance2";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>>(
      v72,
      (unsigned int)&byte_18012B13F,
      v73,
      v74,
      (__int64)&v92,
      (__int64)&v83,
      (__int64)&v82,
      (__int64)&v91);
  }
  std::wstring::_Tidy_deallocate(&v97);
  if ( (unsigned int)dword_18014D6A8 > 5 )
  {
    LODWORD(v82) = 3420;
    v91 = (MI_Context **)"Wsp::Facade::StorageHealthFacade::EnableMaintenance2";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      v75,
      (unsigned int)qword_18012B180,
      v76,
      v77,
      (__int64)&v91,
      (__int64)&v82);
  }
  std::wstring::_Tidy_deallocate(v100);
  std::wstring::_Tidy_deallocate(v102);
  Wsp::Facade::MaintenanceCommandContext::~MaintenanceCommandContext((Wsp::Facade::MaintenanceCommandContext *)v110);
  if ( v96[1] )
    std::_Ref_count_base::_Decref(v96[1]);
  Wsp::Facade::MaintenanceModeStruct::~MaintenanceModeStruct((Wsp::Facade::MaintenanceModeStruct *)&v103);
  std::wstring::_Tidy_deallocate(v101);
  return FaultDomainPhysicalDisks;
}

```

## disassembly

```asm
0x180063988  push    rbp
0x18006398a  push    rbx
0x18006398b  push    rsi
0x18006398c  push    rdi
0x18006398d  push    r12
0x18006398f  push    r13
0x180063991  push    r14
0x180063993  push    r15
0x180063995  lea     rbp, [rsp-268h]
0x18006399d  sub     rsp, 368h
0x1800639a4  mov     rax, cs:__security_cookie
0x1800639ab  xor     rax, rsp
0x1800639ae  mov     [rbp+2A0h+var_50], rax
0x1800639b5  mov     [rsp+3A0h+var_340], r9
0x1800639ba  mov     [rsp+3A0h+var_338], r8
0x1800639bf  mov     r13, rdx
0x1800639c2  mov     r14, rcx
0x1800639c5  mov     r15, [rbp+2A0h+arg_38]
0x1800639cc  mov     rsi, [rbp+2A0h+arg_20]
0x1800639d3  mov     rax, [rbp+2A0h+arg_28]
0x1800639da  mov     [rbp+2A0h+var_2F8], rax
0x1800639de  mov     rax, [rbp+2A0h+arg_30]
0x1800639e5  mov     [rbp+2A0h+var_2E8], rax
0x1800639e9  mov     rbx, [rbp+2A0h+arg_40]
0x1800639f0  mov     [rbp+2A0h+var_300], rbx
0x1800639f4  mov     r12, [rbp+2A0h+arg_48]
0x1800639fb  mov     eax, cs:dword_18014D6A8
0x180063a01  lea     rcx, aWspFacadeStora_1; "Wsp::Facade::StorageHealthFacade::Enabl"...
0x180063a08  cmp     eax, 5
0x180063a0b  jbe     short loc_180063A38
0x180063a0d  mov     [rsp+3A0h+var_328], 0C9Eh
0x180063a15  mov     [rbp+2A0h+var_318], rcx
0x180063a19  lea     rax, [rsp+3A0h+var_328]
0x180063a1e  mov     qword ptr [rsp+3A0h+secondsRemaining], rax; secondsRemaining
0x180063a23  lea     rax, [rbp+2A0h+var_318]
0x180063a27  mov     qword ptr [rsp+3A0h+percentComplete], rax
0x180063a2c  lea     rdx, word_18012B3EE
0x180063a33  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x180063a38  mov     edi, 1
0x180063a3d  mov     [rsp+3A0h+var_32E], dil
0x180063a42  mov     [rsp+3A0h+var_330], dil
0x180063a47  mov     [rsp+3A0h+var_32F], 0
0x180063a4c  mov     [rbp+2A0h+var_2F0], 0FFFFFFFFh
0x180063a53  mov     [rbp+2A0h+var_308], di
0x180063a57  xorps   xmm0, xmm0
0x180063a5a  movups  [rbp+2A0h+var_260], xmm0
0x180063a5e  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x180063a66  movdqu  [rbp+2A0h+var_250], xmm1
0x180063a6b  xor     eax, eax
0x180063a6d  mov     word ptr [rbp+2A0h+var_260], ax
0x180063a71  lea     rcx, [rbp+2A0h+var_220]; this
0x180063a78  call    ??0MaintenanceModeStruct@Facade@Wsp@@QEAA@XZ; Wsp::Facade::MaintenanceModeStruct::MaintenanceModeStruct(void)
0x180063a7d  nop
0x180063a7e  xorps   xmm1, xmm1
0x180063a81  movdqu  xmmword ptr [rbp+2A0h+var_2D0], xmm1
0x180063a86  lea     rcx, [rbp+2A0h+var_130]; this
0x180063a8d  call    ??0MaintenanceCommandContext@Facade@Wsp@@QEAA@XZ; Wsp::Facade::MaintenanceCommandContext::MaintenanceCommandContext(void)
0x180063a92  nop
0x180063a93  mov     rcx, r14
0x180063a96  call    ?GetSubsystemType@StorageHealthFacade@Facade@Wsp@@QEBA?BW4WSP_SUBSYSTEM_TYPE@@XZ; Wsp::Facade::StorageHealthFacade::GetSubsystemType(void)
0x180063a9b  test    eax, eax
0x180063a9d  jz      loc_1800645B9
0x180063aa3  mov     r8d, 0BB9h
0x180063aa9  mov     rdx, cs:qword_1801599A0
0x180063ab0  lea     rcx, [rbp+2A0h+var_240]
0x180063ab4  call    ?load_string@cxl@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEAUHINSTANCE__@@I@Z; cxl::load_string(HINSTANCE__ *,uint)
0x180063ab9  nop
0x180063aba  lea     rax, [rbp+2A0h+var_240]
0x180063abe  mov     [rbp+2A0h+var_2C0], rax
0x180063ac2  mov     [rbp+2A0h+var_2B8], rbx
0x180063ac6  lea     rdx, [rbp+2A0h+var_2C0]
0x180063aca  lea     rcx, [rbp+2A0h+var_100]
0x180063ad1  call    std__function_void___cdecl_unsigned_long____operator___lambda_326242e5b2d8e6ab3091d2d8bf7fa6f6__0_
0x180063ad6  mov     edx, edi
0x180063ad8  lea     rcx, [rbp+2A0h+var_100]
0x180063adf  call    ??R?$_Func_class@XK@std@@QEBAXK@Z; std::_Func_class<void,ulong>::operator()(ulong)
0x180063ae4  xorps   xmm0, xmm0
0x180063ae7  movups  [rbp+2A0h+var_280], xmm0
0x180063aeb  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x180063af3  movdqu  [rbp+2A0h+var_270], xmm1
0x180063af8  xor     eax, eax
0x180063afa  mov     word ptr [rbp+2A0h+var_280], ax
0x180063afe  lea     rdx, [rbp+2A0h+var_280]
0x180063b02  lea     rcx, [rbp+2A0h+var_2A0]
0x180063b06  call    ??0StringWriter@cxl@@QEAA@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::StringWriter::StringWriter(std::wstring &)
0x180063b0b  nop
0x180063b0c  mov     rcx, rax
0x180063b0f  call    ??$Write@$0DH@@TextWriter@cxl@@QEAAAEAV01@AEAY0DH@$$CB_W@Z; cxl::TextWriter::Write<55>(wchar_t const (&)[55])
0x180063b14  nop
0x180063b15  lea     rdx, [rbp+2A0h+var_280]
0x180063b19  lea     rcx, [rbp+2A0h+var_2C0]
0x180063b1d  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180063b22  nop
0x180063b23  mov     eax, cs:dword_18014D6A8
0x180063b29  cmp     eax, 4
0x180063b2c  jbe     short loc_180063B65
0x180063b2e  mov     edx, 4000h
0x180063b33  lea     rcx, dword_18014D6A8
0x180063b3a  call    _tlgKeywordOn
0x180063b3f  test    al, al
0x180063b41  jz      short loc_180063B65
0x180063b43  lea     rcx, [rbp+2A0h+var_2C0]
0x180063b47  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180063b4c  mov     [rbp+2A0h+var_318], rax
0x180063b50  lea     rax, [rbp+2A0h+var_318]
0x180063b54  mov     qword ptr [rsp+3A0h+percentComplete], rax
0x180063b59  lea     rdx, dword_18012B41C
0x180063b60  call    ??$Write@U?$_tlgWrapSz@_W@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@_W@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<wchar_t> const &)
0x180063b65  call    ?Instance@TraceManager@cxl@@SAAEAV12@XZ; cxl::TraceManager::Instance(void)
0x180063b6a  lea     rbx, [rax+78h]
0x180063b6e  lea     rdx, [rbp+2A0h+var_2C0]
0x180063b72  mov     rcx, rbx
0x180063b75  call    ?WriteTo@?$CxlTraits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@cxl@@SAXAEAVTextWriter@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBUFormat@2@@Z; cxl::CxlTraits<std::wstring>::WriteTo(cxl::TextWriter &,std::wstring const &,cxl::Format const &)
0x180063b7a  mov     rcx, rbx
0x180063b7d  call    ??$?6UENDL@cxl@@@TextWriter@cxl@@QEAAAEAV01@AEBUENDL@1@@Z; cxl::TextWriter::operator<<<cxl::ENDL>(cxl::ENDL const &)
0x180063b82  nop
0x180063b83  lea     rcx, [rbp+2A0h+var_2C0]
0x180063b87  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180063b8c  lea     rcx, [rbp+2A0h+var_2C0]
0x180063b90  call    ?GetInstance@MiSpaceAdapter@Wsp@@SA?AV?$shared_ptr@VMiSpaceAdapter@Wsp@@@std@@XZ; Wsp::MiSpaceAdapter::GetInstance(void)
0x180063b95  nop
0x180063b96  lea     rcx, [rbp+2A0h+var_220]
0x180063b9d  mov     qword ptr [rsp+3A0h+percentComplete], rcx
0x180063ba2  lea     r9, [rbp+2A0h+var_21C]
0x180063ba9  mov     r8, r13
0x180063bac  lea     rdx, [rbp+2A0h+var_2A0]
0x180063bb0  mov     rcx, [rax]
0x180063bb3  call    ?UnpackObjectId@MiSpaceAdapter@Wsp@@QEBA?BV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV34@PEAW4WSP_SUBSYSTEM_TYPE@@PEAW4WSP_OBJECT_TYPE@@@Z; Wsp::MiSpaceAdapter::UnpackObjectId(std::wstring const &,WSP_SUBSYSTEM_TYPE *,WSP_OBJECT_TYPE *)
0x180063bb8  nop
0x180063bb9  mov     rdx, rax
0x180063bbc  lea     rcx, [rbp+2A0h+var_260]
0x180063bc0  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x180063bc5  nop
0x180063bc6  lea     rcx, [rbp+2A0h+var_2A0]
0x180063bca  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180063bcf  nop
0x180063bd0  mov     rcx, [rbp+2A0h+var_2B8]; this
0x180063bd4  test    rcx, rcx
0x180063bd7  jz      short loc_180063BDE
0x180063bd9  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180063bde  mov     rcx, r14
0x180063be1  call    ?GetSubsystemType@StorageHealthFacade@Facade@Wsp@@QEBA?BW4WSP_SUBSYSTEM_TYPE@@XZ; Wsp::Facade::StorageHealthFacade::GetSubsystemType(void)
0x180063be6  cmp     eax, [rbp+2A0h+var_21C]
0x180063bec  jz      loc_180063CA7
0x180063bf2  mov     ebx, edi
0x180063bf4  lea     rdx, aSubsystemNotSu; "Subsystem not supported"
0x180063bfb  lea     rcx, [rbp+2A0h+var_2C0]
0x180063bff  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x180063c04  nop
0x180063c05  mov     eax, cs:dword_18014D6A8
0x180063c0b  mov     esi, 0CC8h
0x180063c10  cmp     eax, 2
0x180063c13  jbe     short loc_180063C69
0x180063c15  lea     rcx, [rbp+2A0h+var_2C0]
0x180063c19  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180063c1e  mov     [rbp+2A0h+var_318], rax
0x180063c22  mov     [rsp+3A0h+var_328], edi
0x180063c26  mov     dword ptr [rsp+3A0h+var_338], esi
0x180063c2a  lea     rax, aWspFacadeStora_1; "Wsp::Facade::StorageHealthFacade::Enabl"...
0x180063c31  mov     [rsp+3A0h+var_340], rax
0x180063c36  lea     rax, [rbp+2A0h+var_318]
0x180063c3a  mov     [rsp+3A0h+var_368], rax
0x180063c3f  lea     rax, [rsp+3A0h+var_328]
0x180063c44  mov     [rsp+3A0h+var_370], rax
0x180063c49  lea     rax, [rsp+3A0h+var_338]
0x180063c4e  mov     qword ptr [rsp+3A0h+secondsRemaining], rax
0x180063c53  lea     rax, [rsp+3A0h+var_340]
0x180063c58  mov     qword ptr [rsp+3A0h+percentComplete], rax
0x180063c5d  lea     rdx, dword_18012B43C
0x180063c64  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@U?$_tlgWrapSz@_W@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4AEBU?$_tlgWrapSz@_W@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<wchar_t> const &)
0x180063c69  call    ?Instance@TraceManager@cxl@@SAAEAV12@XZ; cxl::TraceManager::Instance(void)
0x180063c6e  lea     rcx, [rax+28h]; struct cxl::TextWriter *
0x180063c72  mov     dword ptr [rsp+3A0h+var_338], edi
0x180063c76  mov     [rsp+3A0h+var_328], esi
0x180063c7a  lea     rax, [rsp+3A0h+var_338]
0x180063c7f  mov     qword ptr [rsp+3A0h+percentComplete], rax; __int64
0x180063c84  lea     r9, [rsp+3A0h+var_328]
0x180063c89  lea     rdi, aWspFacadeStora_1; "Wsp::Facade::StorageHealthFacade::Enabl"...
0x180063c90  mov     r8, rdi
0x180063c93  call    ??$WriteLine@_W$$BY0DF@DHH$$BY0BI@_W@TextWriter@cxl@@QEAAXPEB_WAEAY0DF@$$CBDAEBH2AEAY0BI@$$CB_W@Z; cxl::TextWriter::WriteLine<wchar_t,char [53],int,int,wchar_t [24]>(wchar_t const *,char const (&)[53],int const &,int const &,wchar_t const (&)[24])
0x180063c98  nop
0x180063c99  lea     rcx, [rbp+2A0h+var_2C0]
0x180063c9d  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180063ca2  jmp     loc_1800643FA
0x180063ca7  mov     eax, [rbp+2A0h+var_220]
0x180063cad  cmp     eax, 0Ch
0x180063cb0  ja      loc_1800643F1
0x180063cb6  mov     ecx, 1220h
0x180063cbb  bt      ecx, eax
0x180063cbe  jnb     loc_1800643F1
0x180063cc4  lea     rdx, [rbp+2A0h+var_2C0]
0x180063cc8  call    ?GetSmApiSession@StorageHealthFacade@Facade@Wsp@@AEAA?AV?$shared_ptr@VMiSession@mi@@@std@@XZ; Wsp::Facade::StorageHealthFacade::GetSmApiSession(void)
0x180063ccd  mov     rdx, rax
0x180063cd0  lea     rcx, [rbp+2A0h+var_218]
0x180063cd7  call    ??4?$shared_ptr@$$CBVSPACES_VirtualDisk@mismpstorage@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<mismpstorage::SPACES_VirtualDisk const>::operator=(std::shared_ptr<mismpstorage::SPACES_VirtualDisk const> &&)
0x180063cdc  mov     rcx, [rbp+2A0h+var_2B8]; this
0x180063ce0  test    rcx, rcx
0x180063ce3  jz      short loc_180063CEA
0x180063ce5  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180063cea  lea     rcx, [rbp+2A0h+var_2C0]
0x180063cee  call    ?GetInstance@DataStore@ClusWmi@@SA?AV?$shared_ptr@VDataStore@ClusWmi@@@std@@XZ; ClusWmi::DataStore::GetInstance(void)
0x180063cf3  nop
0x180063cf4  lea     rdx, [rbp+2A0h+var_2D0]
0x180063cf8  mov     rcx, [rax]; struct ProtectedPwd *
0x180063cfb  call    ?GetCluster@DataStore@ClusWmi@@QEAAJPEAV?$shared_ptr@UICluster@ClusApi@@@std@@@Z; ClusWmi::DataStore::GetCluster(std::shared_ptr<ClusApi::ICluster> *)
0x180063d00  mov     ebx, eax
0x180063d02  mov     rcx, [rbp+2A0h+var_2B8]; this
0x180063d06  test    rcx, rcx
0x180063d09  jz      short loc_180063D10
0x180063d0b  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180063d10  test    ebx, ebx
0x180063d12  jns     loc_180063EAB
0x180063d18  mov     [rsp+3A0h+var_328], ebx
0x180063d1c  mov     ecx, cs:dword_18014D6A8
0x180063d22  mov     esi, 0CDFh
0x180063d27  cmp     ecx, 2
0x180063d2a  jbe     short loc_180063D6E
0x180063d2c  mov     eax, [rsp+3A0h+var_328]
0x180063d30  mov     dword ptr [rsp+3A0h+var_338], eax
0x180063d34  mov     dword ptr [rsp+3A0h+var_340], esi
0x180063d38  lea     rdi, aWspFacadeStora_1; "Wsp::Facade::StorageHealthFacade::Enabl"...
0x180063d3f  mov     [rbp+2A0h+var_318], rdi
0x180063d43  lea     rax, [rsp+3A0h+var_338]
0x180063d48  mov     [rsp+3A0h+var_370], rax
0x180063d4d  lea     rax, [rsp+3A0h+var_340]
0x180063d52  mov     qword ptr [rsp+3A0h+secondsRemaining], rax
0x180063d57  lea     rax, [rbp+2A0h+var_318]
0x180063d5b  mov     qword ptr [rsp+3A0h+percentComplete], rax
0x180063d60  lea     rdx, byte_18012B2F7
0x180063d67  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180063d6c  jmp     short loc_180063D75
0x180063d6e  lea     rdi, aWspFacadeStora_1; "Wsp::Facade::StorageHealthFacade::Enabl"...
0x180063d75  call    ?Instance@TraceManager@cxl@@SAAEAV12@XZ; cxl::TraceManager::Instance(void)
0x180063d7a  lea     rcx, [rax+28h]; struct cxl::TextWriter *
0x180063d7e  mov     dword ptr [rsp+3A0h+var_340], esi
0x180063d82  lea     rax, [rsp+3A0h+var_328]
0x180063d87  mov     qword ptr [rsp+3A0h+percentComplete], rax; __int64
0x180063d8c  lea     r9, [rsp+3A0h+var_340]
0x180063d91  mov     r8, rdi
0x180063d94  call    ??$WriteLine@_W$$BY0DF@DHJ@TextWriter@cxl@@QEAAXPEB_WAEAY0DF@$$CBDAEBHAEBJ@Z; cxl::TextWriter::WriteLine<wchar_t,char [53],int,long>(wchar_t const *,char const (&)[53],int const &,long const &)
0x180063d99  mov     ecx, ebx
0x180063d9b  call    ?SmRCFromHResult@MiSpaceAdapter@Wsp@@SA?AW4SM_RETURN_CODE@@J@Z; Wsp::MiSpaceAdapter::SmRCFromHResult(long)
0x180063da0  mov     ebx, eax
0x180063da2  lea     rdx, aFailedToGetClu; "Failed to Get Cluster"
0x180063da9  lea     rcx, [rbp+2A0h+var_2C0]
0x180063dad  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x180063db2  nop
0x180063db3  test    ebx, ebx
0x180063db5  jz      loc_180063E45
0x180063dbb  mov     ecx, cs:dword_18014D6A8
0x180063dc1  cmp     ecx, 2
0x180063dc4  jbe     short loc_180063E17
0x180063dc6  lea     rcx, [rbp+2A0h+var_2C0]
0x180063dca  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180063dcf  mov     [rbp+2A0h+var_318], rax
0x180063dd3  mov     dword ptr [rsp+3A0h+var_340], ebx
0x180063dd7  mov     dword ptr [rsp+3A0h+var_338], 0CE0h
0x180063ddf  mov     qword ptr [rsp+3A0h+var_328], rdi
0x180063de4  lea     rax, [rbp+2A0h+var_318]
0x180063de8  mov     [rsp+3A0h+var_368], rax
0x180063ded  lea     rax, [rsp+3A0h+var_340]
0x180063df2  mov     [rsp+3A0h+var_370], rax
0x180063df7  lea     rax, [rsp+3A0h+var_338]
0x180063dfc  mov     qword ptr [rsp+3A0h+secondsRemaining], rax
0x180063e01  lea     rax, [rsp+3A0h+var_328]
0x180063e06  mov     qword ptr [rsp+3A0h+percentComplete], rax
0x180063e0b  lea     rdx, byte_18012B32F
0x180063e12  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@U?$_tlgWrapSz@_W@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4AEBU?$_tlgWrapSz@_W@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<wchar_t> const &)
0x180063e17  call    ?Instance@TraceManager@cxl@@SAAEAV12@XZ; cxl::TraceManager::Instance(void)
0x180063e1c  lea     rcx, [rax+28h]; struct cxl::TextWriter *
0x180063e20  mov     dword ptr [rsp+3A0h+var_340], ebx
0x180063e24  mov     dword ptr [rsp+3A0h+var_338], 0CE0h
0x180063e2c  lea     rax, [rsp+3A0h+var_340]
0x180063e31  mov     qword ptr [rsp+3A0h+percentComplete], rax; __int64
0x180063e36  lea     r9, [rsp+3A0h+var_338]
0x180063e3b  mov     r8, rdi
0x180063e3e  call    ??$WriteLine@_W$$BY0DF@DHH$$BY0BG@_W@TextWriter@cxl@@QEAAXPEB_WAEAY0DF@$$CBDAEBH2AEAY0BG@$$CB_W@Z; cxl::TextWriter::WriteLine<wchar_t,char [53],int,int,wchar_t [22]>(wchar_t const *,char const (&)[53],int const &,int const &,wchar_t const (&)[22])
0x180063e43  jmp     short loc_180063EA6
0x180063e45  mov     eax, cs:dword_18014D6A8
0x180063e4b  cmp     eax, 5
0x180063e4e  jbe     short loc_180063EA6
0x180063e50  lea     rcx, [rbp+2A0h+var_2C0]
0x180063e54  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180063e59  mov     [rbp+2A0h+var_318], rax
0x180063e5d  mov     dword ptr [rsp+3A0h+var_340], 0
0x180063e65  mov     dword ptr [rsp+3A0h+var_338], 0CE0h
0x180063e6d  mov     qword ptr [rsp+3A0h+var_328], rdi
0x180063e72  lea     rax, [rbp+2A0h+var_318]
0x180063e76  mov     [rsp+3A0h+var_368], rax
0x180063e7b  lea     rax, [rsp+3A0h+var_340]
0x180063e80  mov     [rsp+3A0h+var_370], rax
0x180063e85  lea     rax, [rsp+3A0h+var_338]
0x180063e8a  mov     qword ptr [rsp+3A0h+secondsRemaining], rax
0x180063e8f  lea     rax, [rsp+3A0h+var_328]
0x180063e94  mov     qword ptr [rsp+3A0h+percentComplete], rax
0x180063e99  lea     rdx, word_18012B36E
0x180063ea0  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@U?$_tlgWrapSz@_W@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4AEBU?$_tlgWrapSz@_W@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<wchar_t> const &)
0x180063ea5  nop
0x180063ea6  jmp     loc_180063C99
0x180063eab  lea     rdx, [rbp+2A0h+var_2D0]
  ... truncated ...
```
