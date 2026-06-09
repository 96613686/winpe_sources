# Wsp::Facade::StorageHealthFacade::EnableMaintenance2(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,std::unique_ptr<bool,std::default_delete<bool>> const &,std::unique_ptr<bool,std::default_delete<bool>> const &,std::unique_ptr<uint,std::default_delete<uint>> &,std::unique_ptr<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,std::default_delete<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>>> const &,std::unique_ptr<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,std::default_delete<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>>> const &,std::unique_ptr<ushort,std::default_delete<ushort>> &,mi::MiContext &,std::shared_ptr<Wsp::Facade::IExtendedStatus> &)

- ea: `0x180062184`
- end: `0x180062df8`
- name: `?EnableMaintenance2@StorageHealthFacade@Facade@Wsp@@QEAA?AW4SM_RETURN_CODE@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV?$unique_ptr@_NU?$default_delete@_N@std@@@6@1AEAV?$unique_ptr@IU?$default_delete@I@std@@@6@AEBV?$unique_ptr@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$default_delete@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@6@3AEAV?$unique_ptr@GU?$default_delete@G@std@@@6@AEAVMiContext@mi@@AEAV?$shared_ptr@UIExtendedStatus@Facade@Wsp@@@6@@Z`
- size: `3188`
- prototype: ``
- caller_count: `1`
- callee_count: `65`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180054ac8`

## callees

- `0x1800010f4`
- `0x18000119c`
- `0x1800013bc`
- `0x180001620`
- `0x1800016b0`
- `0x180002ae0`
- `0x180003520`
- `0x18000b800`
- `0x18000b8e4`
- `0x18000bf68`
- `0x18000c9a8`
- `0x18000c9f0`
- `0x18000cfb4`
- `0x18000d140`
- `0x18000d618`
- `0x18000d6dc`
- `0x18000e044`
- `0x18000eebc`
- `0x180010ca4`
- `0x180016218`
- `0x180018d50`
- `0x180019340`
- `0x180033fd4`
- `0x180034360`
- `0x180034808`
- `0x1800424d8`
- `0x180052350`
- `0x180052374`
- `0x180053624`
- `0x180053698`
- `0x180057860`
- `0x180057898`
- `0x180057968`
- `0x1800589e4`
- `0x180059da0`
- `0x180059f30`
- `0x180059f8c`
- `0x180059fe8`
- `0x18005a044`
- `0x18005a0a8`
- `0x18005a10c`
- `0x18005a29c`
- `0x18005d680`
- `0x18005d6b8`
- `0x18005d954`
- `0x18005d980`
- `0x18005e104`
- `0x18005e500`
- `0x18005e654`
- `0x18005e684`

## string_xrefs

- `0x180062c16`: `Completed`
- `0x180062831`: `SendCommandMaintenanceMode Failed.`

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
        void **a8,
        std::_Ref_count_base *a9,
        __int64 a10)
{
  bool v12; // di
  __int64 v13; // rax
  __int64 v14; // rcx
  __int64 v15; // r8
  __int64 v16; // r9
  char *v17; // rbx
  _QWORD *Instance; // rax
  __int64 v19; // rax
  int SubsystemType; // eax
  unsigned int FaultDomainPhysicalDisks; // ebx
  __int64 v22; // rcx
  __int64 v23; // r8
  __int64 v24; // r9
  struct cxl::TraceManager *v25; // rax
  int v26; // ecx
  __int64 SmApiSession; // rax
  struct ProtectedPwd **v28; // rax
  int Cluster; // ebx
  __int64 v30; // r8
  __int64 v31; // r9
  struct cxl::TraceManager *v32; // rax
  __int64 v33; // rcx
  __int64 v34; // r8
  __int64 v35; // r9
  struct cxl::TraceManager *v36; // rax
  __int64 v37; // rcx
  __int64 v38; // r8
  __int64 v39; // r9
  __int64 v40; // rax
  std::_Ref_count_base *v41; // rcx
  __int64 v42; // rcx
  __int64 v43; // rcx
  const wchar_t *v44; // rax
  Wsp::Facade::StorageHealthFacade *v45; // rcx
  __int64 *v46; // rax
  const wchar_t *v47; // rax
  Wsp::Facade::StorageHealthFacade *v48; // rcx
  void **v49; // rax
  __int64 v50; // rcx
  __int64 v51; // r8
  __int64 v52; // r9
  struct cxl::TraceManager *v53; // rax
  __int64 v54; // rcx
  __int64 v55; // r8
  __int64 v56; // r9
  struct cxl::TraceManager *v57; // rax
  __int64 v58; // rcx
  __int64 v59; // r8
  __int64 v60; // r9
  struct cxl::TraceManager *v61; // rax
  __int64 v62; // rcx
  __int64 v63; // r8
  __int64 v64; // r9
  struct cxl::TraceManager *v65; // rax
  const MI_Char *v66; // rax
  const MI_Char *v67; // r8
  const MI_Char *v68; // r9
  __int64 v69; // rcx
  __int64 v70; // r8
  __int64 v71; // r9
  struct cxl::TraceManager *v72; // rax
  __int64 v73; // rcx
  __int64 v74; // r8
  __int64 v75; // r9
  __int64 v76; // rcx
  __int64 v77; // r8
  __int64 v78; // r9
  __int64 v80; // rax
  __int64 v81; // rax
  void *secondsRemaining; // [rsp+28h] [rbp-D8h]
  __int64 v83; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v84; // [rsp+68h] [rbp-98h] BYREF
  char v85; // [rsp+70h] [rbp-90h] BYREF
  char v86; // [rsp+71h] [rbp-8Fh] BYREF
  _BYTE v87[6]; // [rsp+72h] [rbp-8Eh] BYREF
  MI_Uint32 v88[2]; // [rsp+78h] [rbp-88h] BYREF
  _BYTE v89[8]; // [rsp+80h] [rbp-80h] BYREF
  _QWORD v90[2]; // [rsp+88h] [rbp-78h] BYREF
  __int16 v91; // [rsp+98h] [rbp-68h] BYREF
  MI_Context **v92; // [rsp+A0h] [rbp-60h] BYREF
  const char *v93; // [rsp+A8h] [rbp-58h] BYREF
  int v94; // [rsp+B0h] [rbp-50h] BYREF
  const char *v95; // [rsp+B8h] [rbp-48h] BYREF
  _BYTE v96[16]; // [rsp+C0h] [rbp-40h] BYREF
  std::_Ref_count_base *v97[2]; // [rsp+D0h] [rbp-30h] BYREF
  _BYTE *v98; // [rsp+E0h] [rbp-20h] BYREF
  std::_Ref_count_base *v99; // [rsp+E8h] [rbp-18h]
  _BYTE v100[32]; // [rsp+100h] [rbp+0h] BYREF
  _OWORD v101[2]; // [rsp+120h] [rbp+20h] BYREF
  _OWORD v102[2]; // [rsp+140h] [rbp+40h] BYREF
  _BYTE v103[32]; // [rsp+160h] [rbp+60h] BYREF
  unsigned int v104; // [rsp+180h] [rbp+80h] BYREF
  int v105; // [rsp+184h] [rbp+84h] BYREF
  _QWORD v106[18]; // [rsp+188h] [rbp+88h] BYREF
  char v107; // [rsp+21Bh] [rbp+11Bh] BYREF
  int v108; // [rsp+21Ch] [rbp+11Ch]
  _BYTE v109[16]; // [rsp+220h] [rbp+120h] BYREF
  _BYTE v110[64]; // [rsp+230h] [rbp+130h] BYREF
  _BYTE v111[48]; // [rsp+270h] [rbp+170h] BYREF
  _BYTE v112[64]; // [rsp+2A0h] [rbp+1A0h] BYREF
  _BYTE pExceptionObject[112]; // [rsp+2E0h] [rbp+1E0h] BYREF

  v83 = a4;
  v84 = a3;
  v93 = a6;
  v95 = a7;
  v92 = (MI_Context **)a9;
  if ( (unsigned int)dword_18014B6A8 > 5 )
  {
    v88[0] = 3230;
    v90[0] = "Wsp::Facade::StorageHealthFacade::EnableMaintenance2";
    secondsRemaining = v88;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      (__int64)"Wsp::Facade::StorageHealthFacade::EnableMaintenance2",
      (__int64)&word_1801293E6,
      a3,
      a4,
      v90);
  }
  v12 = 1;
  v87[0] = 1;
  v85 = 1;
  v86 = 0;
  v94 = -1;
  v91 = 1;
  v102[0] = 0;
  v102[1] = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v102[0]) = 0;
  Wsp::Facade::MaintenanceModeStruct::MaintenanceModeStruct((Wsp::Facade::MaintenanceModeStruct *)&v104);
  *(_OWORD *)v97 = 0;
  Wsp::Facade::MaintenanceCommandContext::MaintenanceCommandContext((Wsp::Facade::MaintenanceCommandContext *)v111);
  if ( !(unsigned int)Wsp::Facade::StorageHealthFacade::GetSubsystemType(a1) )
  {
    v80 = std::wstring::wstring(v100, L"non highlyavailable subsystems are not supported");
    v81 = cxl::SMResult(&v92, 59001, v80);
    cxl::Error(pExceptionObject, v81);
    throw (cxl::Exception *)pExceptionObject;
  }
  cxl::load_string(v103, qword_1801578A0, 3001);
  v98 = v103;
  v99 = a9;
  std::function_void___cdecl_unsigned_long__::operator___lambda_326242e5b2d8e6ab3091d2d8bf7fa6f6__0_(v112, &v98);
  std::_Func_class<void,unsigned long>::operator()(v112, 1);
  v101[0] = 0;
  v101[1] = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v101[0]) = 0;
  v13 = cxl::StringWriter::StringWriter(v100, v101);
  cxl::TextWriter::Write<55>(v13);
  std::wstring::wstring(&v98, v101);
  if ( (unsigned int)dword_18014B6A8 > 4 && (unsigned __int8)tlgKeywordOn(&dword_18014B6A8, 0x4000) )
  {
    v90[0] = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(&v98);
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>>(
      v14,
      (__int64)&dword_180129414,
      v15,
      v16,
      v90);
  }
  v17 = (char *)cxl::TraceManager::Instance() + 120;
  cxl::CxlTraits<std::wstring>::WriteTo(v17, &v98);
  cxl::TextWriter::operator<<<cxl::ENDL>((__int64)v17);
  std::wstring::_Tidy_deallocate(&v98);
  Instance = (_QWORD *)Wsp::MiSpaceAdapter::GetInstance(&v98);
  v19 = Wsp::MiSpaceAdapter::UnpackObjectId(*Instance, (unsigned int)v100, a2, (unsigned int)&v105, (__int64)&v104);
  std::wstring::operator=(v102, v19);
  std::wstring::_Tidy_deallocate(v100);
  if ( v99 )
    std::_Ref_count_base::_Decref(v99);
  SubsystemType = Wsp::Facade::StorageHealthFacade::GetSubsystemType(a1);
  if ( SubsystemType != v105 )
  {
    FaultDomainPhysicalDisks = 1;
    std::wstring::wstring(&v98, L"Subsystem not supported");
    if ( (unsigned int)dword_18014B6A8 > 2 )
    {
      v90[0] = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(&v98);
      v88[0] = 1;
      LODWORD(v84) = 3272;
      v83 = (__int64)"Wsp::Facade::StorageHealthFacade::EnableMaintenance2";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>>(
        v22,
        (__int64)&dword_180129434,
        v23,
        v24,
        &v83,
        (__int64)&v84,
        (__int64)v88,
        v90);
    }
    v25 = cxl::TraceManager::Instance();
    LODWORD(v84) = 1;
    v88[0] = 3272;
    cxl::TextWriter::WriteLine<wchar_t,char [53],int,int,wchar_t [24]>(
      (struct cxl::TraceManager *)((char *)v25 + 40),
      (__int64)&v84);
LABEL_13:
    std::wstring::_Tidy_deallocate(&v98);
    goto LABEL_67;
  }
  if ( v104 > 0xC || (v26 = 4640, !_bittest(&v26, v104)) )
  {
    FaultDomainPhysicalDisks = 1;
    goto LABEL_67;
  }
  SmApiSession = Wsp::Facade::StorageHealthFacade::GetSmApiSession(4640, &v98);
  std::shared_ptr<mismpstorage::SPACES_VirtualDisk const>::operator=(v106, SmApiSession);
  if ( v99 )
    std::_Ref_count_base::_Decref(v99);
  v28 = (struct ProtectedPwd **)ClusWmi::DataStore::GetInstance(&v98);
  Cluster = ClusWmi::DataStore::GetCluster(*v28);
  if ( v99 )
    std::_Ref_count_base::_Decref(v99);
  if ( Cluster < 0 )
  {
    v88[0] = Cluster;
    if ( (unsigned int)dword_18014B6A8 > 2 )
    {
      LODWORD(v84) = v88[0];
      LODWORD(v83) = 3295;
      v90[0] = "Wsp::Facade::StorageHealthFacade::EnableMaintenance2";
      secondsRemaining = &v83;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        (unsigned int)dword_18014B6A8,
        (__int64)&byte_1801292EF,
        v30,
        v31,
        v90);
    }
    v32 = cxl::TraceManager::Instance();
    LODWORD(v83) = 3295;
    cxl::TextWriter::WriteLine<wchar_t,char [53],int,long>((struct cxl::TraceManager *)((char *)v32 + 40), (__int64)v88);
    FaultDomainPhysicalDisks = Wsp::MiSpaceAdapter::SmRCFromHResult((unsigned int)Cluster);
    std::wstring::wstring(&v98, L"Failed to Get Cluster");
    if ( FaultDomainPhysicalDisks )
    {
      if ( (unsigned int)dword_18014B6A8 > 2 )
      {
        v90[0] = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(&v98);
        LODWORD(v83) = FaultDomainPhysicalDisks;
        LODWORD(v84) = 3296;
        *(_QWORD *)v88 = "Wsp::Facade::StorageHealthFacade::EnableMaintenance2";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>>(
          v33,
          (__int64)&byte_180129327,
          v34,
          v35,
          v88,
          (__int64)&v84,
          (__int64)&v83,
          v90);
      }
      v36 = cxl::TraceManager::Instance();
      LODWORD(v83) = FaultDomainPhysicalDisks;
      LODWORD(v84) = 3296;
      cxl::TextWriter::WriteLine<wchar_t,char [53],int,int,wchar_t [22]>(
        (struct cxl::TraceManager *)((char *)v36 + 40),
        (__int64)&v83);
    }
    else if ( (unsigned int)dword_18014B6A8 > 5 )
    {
      v90[0] = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(&v98);
      LODWORD(v83) = 0;
      LODWORD(v84) = 3296;
      *(_QWORD *)v88 = "Wsp::Facade::StorageHealthFacade::EnableMaintenance2";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>>(
        v37,
        (__int64)&word_180129366,
        v38,
        v39,
        v88,
        (__int64)&v84,
        (__int64)&v83,
        v90);
    }
    goto LABEL_13;
  }
  v40 = ClusApi::Facade::FacadeFactory::CreateClusterFacade(&v98, v97);
  std::shared_ptr<mismpstorage::SPACES_VirtualDisk const>::operator=(v109, v40);
  v41 = v99;
  if ( v99 )
    std::_Ref_count_base::_Decref(v99);
  Wsp::Facade::StorageHealthFacade::GetLocalNode(v41, &v104);
  Wsp::Facade::StorageHealthFacade::S2DEnabled(v42, &v104);
  v43 = v84;
  if ( *(_QWORD *)v84 )
    v86 = **(_BYTE **)v84;
  if ( !*a5 )
  {
    if ( v107 )
    {
      v44 = (const wchar_t *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(qword_180157940);
      Wsp::Facade::StorageHealthFacade::GetMaintenanceModeConfiguration(
        v45,
        v44,
        (void (*)(const wchar_t *, const wchar_t *, void *))Wsp::Facade::_MaintenanceModeTimeoutConfigurationCallback,
        &v94);
      v46 = std::make_unique<unsigned int,unsigned int &,0>(v90, &v94);
      std::unique_ptr<unsigned int>::operator=<std::default_delete<unsigned int>,0>((__int64)a5, v46);
      std::unique_ptr<unsigned int>::~unique_ptr<unsigned int>(v90);
    }
    else
    {
      std::unique_ptr<unsigned int>::reset(a5, 0);
    }
  }
  if ( !*a8 )
  {
    v47 = (const wchar_t *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(qword_180157960);
    Wsp::Facade::StorageHealthFacade::GetMaintenanceModeConfiguration(
      v48,
      v47,
      (void (*)(const wchar_t *, const wchar_t *, void *))Wsp::Facade::_MaintenanceModeValidationLevelConfigurationCallback,
      &v91);
    v49 = (void **)std::make_unique<unsigned short,unsigned short &,0>(v90, &v91);
    std::unique_ptr<unsigned short>::operator=<std::default_delete<unsigned short>,0>(a8, v49);
    std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(v90);
  }
  if ( *a8 )
  {
    v12 = (*(_BYTE *)*a8 & 1) != 0;
    v85 = v12;
  }
  if ( !v107 || !v108 )
  {
    std::map<std::wstring,mismpstorage::SPACES_PhysicalDisk>::map<std::wstring,mismpstorage::SPACES_PhysicalDisk>(v96);
    std::map<std::wstring,Wsp::Facade::MaintenanceDisk>::map<std::wstring,Wsp::Facade::MaintenanceDisk>(&v98);
    LODWORD(secondsRemaining) = a10;
    FaultDomainPhysicalDisks = Wsp::Facade::StorageHealthFacade::GetFaultDomainPhysicalDisks(
                                 a1,
                                 a2,
                                 (unsigned int)&v104,
                                 (unsigned int)&v98,
                                 (__int64)v96);
    if ( FaultDomainPhysicalDisks )
    {
      std::wstring::wstring(v100, L"GetFaultDomainPhysicalDisks");
      if ( (unsigned int)dword_18014B6A8 > 2 )
      {
        v90[0] = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v100);
        LODWORD(v83) = FaultDomainPhysicalDisks;
        LODWORD(v84) = 3369;
        *(_QWORD *)v88 = "Wsp::Facade::StorageHealthFacade::EnableMaintenance2";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>>(
          v54,
          (__int64)byte_180129271,
          v55,
          v56,
          v88,
          (__int64)&v84,
          (__int64)&v83,
          v90);
      }
      v57 = cxl::TraceManager::Instance();
      LODWORD(v83) = FaultDomainPhysicalDisks;
      LODWORD(v84) = 3369;
      cxl::TextWriter::WriteLine<wchar_t,char [53],int,int,wchar_t [28]>(
        (struct cxl::TraceManager *)((char *)v57 + 40),
        (__int64)&v83,
        (__int64)L"GetFaultDomainPhysicalDisks");
    }
    else
    {
      if ( !v12
        || (FaultDomainPhysicalDisks = Wsp::Facade::StorageHealthFacade::ValidateAllVirtualDiskHealthy(
                                         a1,
                                         &v104,
                                         v96,
                                         a10)) == 0 )
      {
        std::shared_ptr<ClusApi::IStorage>::shared_ptr<ClusApi::IStorage>(v90, v106);
        LODWORD(secondsRemaining) = v83;
        FaultDomainPhysicalDisks = Wsp::Facade::StorageHealthFacade::CallMaintenanceOnTargetObject(
                                     &v107,
                                     v110,
                                     &v104,
                                     v87,
                                     v84);
        if ( FaultDomainPhysicalDisks )
        {
          std::wstring::wstring(v100, L"CallMaintenanceOnTargetObject Failed.");
          if ( (unsigned int)dword_18014B6A8 > 2 )
          {
            v93 = (const char *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v100);
            LODWORD(v83) = FaultDomainPhysicalDisks;
            LODWORD(v84) = 3398;
            v95 = "Wsp::Facade::StorageHealthFacade::EnableMaintenance2";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>>(
              v62,
              (__int64)byte_1801291F3,
              v63,
              v64,
              &v95,
              (__int64)&v84,
              (__int64)&v83,
              &v93);
          }
          v65 = cxl::TraceManager::Instance();
          LODWORD(v83) = FaultDomainPhysicalDisks;
          LODWORD(v84) = 3398;
          cxl::TextWriter::WriteLine<wchar_t,char [53],int,int,wchar_t [38]>(
            (struct cxl::TraceManager *)((char *)v65 + 40),
            (__int64)&v83);
          std::wstring::_Tidy_deallocate(v100);
        }
        std::_Tree<std::_Tmap_traits<std::wstring,Wsp::Facade::MaintenanceDisk,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,Wsp::Facade::MaintenanceDisk>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,Wsp::Facade::MaintenanceDisk,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,Wsp::Facade::MaintenanceDisk>>,0>>(&v98);
        std::_Tree<std::_Tmap_traits<std::wstring,mismpstorage::SPACES_VirtualDisk,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,mismpstorage::SPACES_VirtualDisk>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,mismpstorage::SPACES_VirtualDisk,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,mismpstorage::SPACES_VirtualDisk>>,0>>(v96);
        goto LABEL_67;
      }
      std::wstring::wstring(v100, L"ValidateAllVirtualDiskHealthy");
      if ( (unsigned int)dword_18014B6A8 > 2 )
      {
        v90[0] = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v100);
        LODWORD(v83) = FaultDomainPhysicalDisks;
        LODWORD(v84) = 3378;
        *(_QWORD *)v88 = "Wsp::Facade::StorageHealthFacade::EnableMaintenance2";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>>(
          v58,
          (__int64)qword_1801292B0,
          v59,
          v60,
          v88,
          (__int64)&v84,
          (__int64)&v83,
          v90);
      }
      v61 = cxl::TraceManager::Instance();
      LODWORD(v83) = FaultDomainPhysicalDisks;
      LODWORD(v84) = 3378;
      cxl::TextWriter::WriteLine<wchar_t,char [53],int,int,wchar_t [30]>(
        (struct cxl::TraceManager *)((char *)v61 + 40),
        (__int64)&v83);
    }
    std::wstring::_Tidy_deallocate(v100);
    std::_Tree<std::_Tmap_traits<std::wstring,Wsp::Facade::MaintenanceDisk,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,Wsp::Facade::MaintenanceDisk>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,Wsp::Facade::MaintenanceDisk,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,Wsp::Facade::MaintenanceDisk>>,0>>(&v98);
    std::_Tree<std::_Tmap_traits<std::wstring,mismpstorage::SPACES_VirtualDisk,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,mismpstorage::SPACES_VirtualDisk>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,mismpstorage::SPACES_VirtualDisk,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,mismpstorage::SPACES_VirtualDisk>>,0>>(v96);
    goto LABEL_67;
  }
  if ( *(_QWORD *)v83 )
    LOBYTE(v43) = **(_BYTE **)v83;
  else
    LOBYTE(v43) = 0;
  v89[0] = v43;
  FaultDomainPhysicalDisks = Wsp::Facade::StorageHealthFacade::SendCommandMaintenanceMode(
                               v43,
                               (__int64)v111,
                               a2,
                               &v104,
                               v87,
                               &v86,
                               v89,
                               &v85,
                               a5);
  if ( FaultDomainPhysicalDisks )
  {
    std::wstring::wstring(&v98, L"SendCommandMaintenanceMode Failed.");
    if ( (unsigned int)dword_18014B6A8 > 2 )
    {
      v90[0] = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(&v98);
      LODWORD(v83) = FaultDomainPhysicalDisks;
      LODWORD(v84) = 3358;
      *(_QWORD *)v88 = "Wsp::Facade::StorageHealthFacade::EnableMaintenance2";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>>(
        v50,
        (__int64)&byte_1801293A7,
        v51,
        v52,
        v88,
        (__int64)&v84,
        (__int64)&v83,
        v90);
    }
    v53 = cxl::TraceManager::Instance();
    LODWORD(v83) = FaultDomainPhysicalDisks;
    LODWORD(v84) = 3358;
    cxl::TextWriter::WriteLine<wchar_t,char [53],int,int,wchar_t [35]>(
      (struct cxl::TraceManager *)((char *)v53 + 40),
      (__int64)&v83);
    goto LABEL_13;
  }
LABEL_67:
  v66 = (const MI_Char *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v103);
  MI_Context_WriteProgress(*v92, v66, v67, v68, 0x64u, (MI_Uint32)secondsRemaining);
  std::wstring::wstring(&v98, L"Completed");
  if ( FaultDomainPhysicalDisks )
  {
    if ( (unsigned int)dword_18014B6A8 > 2 )
    {
      v92 = (MI_Context **)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(&v98);
      LODWORD(v83) = FaultDomainPhysicalDisks;
      LODWORD(v84) = 3418;
      v93 = "Wsp::Facade::StorageHealthFacade::EnableMaintenance2";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>>(
        v69,
        (__int64)word_180129232,
        v70,
        v71,
        &v93,
        (__int64)&v84,
        (__int64)&v83,
        &v92);
    }
    v72 = cxl::TraceManager::Instance();
    LODWORD(v83) = FaultDomainPhysicalDisks;
    LODWORD(v84) = 3418;
    cxl::TextWriter::WriteLine<wchar_t,char [53],int,int,wchar_t [10]>(
      (struct cxl::TraceManager *)((char *)v72 + 40),
      (__int64)&v83);
  }
  else if ( (unsigned int)dword_18014B6A8 > 5 )
  {
    v92 = (MI_Context **)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(&v98);
    LODWORD(v83) = 0;
    LODWORD(v84) = 3418;
    v93 = "Wsp::Facade::StorageHealthFacade::EnableMaintenance2";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>>(
      v73,
      (__int64)&byte_180129137,
      v74,
      v75,
      &v93,
      (__int64)&v84,
      (__int64)&v83,
      &v92);
  }
  std::wstring::_Tidy_deallocate(&v98);
  if ( (unsigned int)dword_18014B6A8 > 5 )
  {
    LODWORD(v83) = 3420;
    v92 = (MI_Context **)"Wsp::Facade::StorageHealthFacade::EnableMaintenance2";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      v76,
      (__int64)qword_180129178,
      v77,
      v78,
      &v92);
  }
  std::wstring::_Tidy_deallocate(v101);
  std::wstring::_Tidy_deallocate(v103);
  Wsp::Facade::MaintenanceCommandContext::~MaintenanceCommandContext((Wsp::Facade::MaintenanceCommandContext *)v111);
  if ( v97[1] )
    std::_Ref_count_base::_Decref(v97[1]);
  Wsp::Facade::MaintenanceModeStruct::~MaintenanceModeStruct((Wsp::Facade::MaintenanceModeStruct *)&v104);
  std::wstring::_Tidy_deallocate(v102);
  return FaultDomainPhysicalDisks;
}

```

## disassembly

```asm
0x180062184  push    rbp
0x180062186  push    rbx
0x180062187  push    rsi
0x180062188  push    rdi
0x180062189  push    r12
0x18006218b  push    r13
0x18006218d  push    r14
0x18006218f  push    r15
0x180062191  lea     rbp, [rsp-268h]
0x180062199  sub     rsp, 368h
0x1800621a0  mov     rax, cs:__security_cookie
0x1800621a7  xor     rax, rsp
0x1800621aa  mov     [rbp+2A0h+var_50], rax
0x1800621b1  mov     [rsp+3A0h+var_340], r9
0x1800621b6  mov     [rsp+3A0h+var_338], r8
0x1800621bb  mov     r13, rdx
0x1800621be  mov     r14, rcx
0x1800621c1  mov     r15, [rbp+2A0h+arg_38]
0x1800621c8  mov     rsi, [rbp+2A0h+arg_20]
0x1800621cf  mov     rax, [rbp+2A0h+arg_28]
0x1800621d6  mov     [rbp+2A0h+var_2F8], rax
0x1800621da  mov     rax, [rbp+2A0h+arg_30]
0x1800621e1  mov     [rbp+2A0h+var_2E8], rax
0x1800621e5  mov     rbx, [rbp+2A0h+arg_40]
0x1800621ec  mov     [rbp+2A0h+var_300], rbx
0x1800621f0  mov     r12, [rbp+2A0h+arg_48]
0x1800621f7  mov     eax, cs:dword_18014B6A8
0x1800621fd  lea     rcx, aWspFacadeStora_1; "Wsp::Facade::StorageHealthFacade::Enabl"...
0x180062204  cmp     eax, 5
0x180062207  jbe     short loc_180062234
0x180062209  mov     [rsp+3A0h+var_328], 0C9Eh
0x180062211  mov     [rbp+2A0h+var_318], rcx
0x180062215  lea     rax, [rsp+3A0h+var_328]
0x18006221a  mov     qword ptr [rsp+3A0h+secondsRemaining], rax; secondsRemaining
0x18006221f  lea     rax, [rbp+2A0h+var_318]
0x180062223  mov     qword ptr [rsp+3A0h+percentComplete], rax
0x180062228  lea     rdx, word_1801293E6
0x18006222f  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x180062234  mov     edi, 1
0x180062239  mov     [rsp+3A0h+var_32E], dil
0x18006223e  mov     [rsp+3A0h+var_330], dil
0x180062243  mov     [rsp+3A0h+var_32F], 0
0x180062248  mov     [rbp+2A0h+var_2F0], 0FFFFFFFFh
0x18006224f  mov     [rbp+2A0h+var_308], di
0x180062253  xorps   xmm0, xmm0
0x180062256  movups  [rbp+2A0h+var_260], xmm0
0x18006225a  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x180062262  movdqu  [rbp+2A0h+var_250], xmm1
0x180062267  xor     eax, eax
0x180062269  mov     word ptr [rbp+2A0h+var_260], ax
0x18006226d  lea     rcx, [rbp+2A0h+var_220]; this
0x180062274  call    ??0MaintenanceModeStruct@Facade@Wsp@@QEAA@XZ; Wsp::Facade::MaintenanceModeStruct::MaintenanceModeStruct(void)
0x180062279  nop
0x18006227a  xorps   xmm1, xmm1
0x18006227d  movdqu  xmmword ptr [rbp+2A0h+var_2D0], xmm1
0x180062282  lea     rcx, [rbp+2A0h+var_130]; this
0x180062289  call    ??0MaintenanceCommandContext@Facade@Wsp@@QEAA@XZ; Wsp::Facade::MaintenanceCommandContext::MaintenanceCommandContext(void)
0x18006228e  nop
0x18006228f  mov     rcx, r14
0x180062292  call    ?GetSubsystemType@StorageHealthFacade@Facade@Wsp@@QEBA?BW4WSP_SUBSYSTEM_TYPE@@XZ; Wsp::Facade::StorageHealthFacade::GetSubsystemType(void)
0x180062297  test    eax, eax
0x180062299  jz      loc_180062DB4
0x18006229f  mov     r8d, 0BB9h
0x1800622a5  mov     rdx, cs:qword_1801578A0
0x1800622ac  lea     rcx, [rbp+2A0h+var_240]
0x1800622b0  call    ?load_string@cxl@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEAUHINSTANCE__@@I@Z; cxl::load_string(HINSTANCE__ *,uint)
0x1800622b5  nop
0x1800622b6  lea     rax, [rbp+2A0h+var_240]
0x1800622ba  mov     [rbp+2A0h+var_2C0], rax
0x1800622be  mov     [rbp+2A0h+var_2B8], rbx
0x1800622c2  lea     rdx, [rbp+2A0h+var_2C0]
0x1800622c6  lea     rcx, [rbp+2A0h+var_100]
0x1800622cd  call    std__function_void___cdecl_unsigned_long____operator___lambda_326242e5b2d8e6ab3091d2d8bf7fa6f6__0_
0x1800622d2  mov     edx, edi
0x1800622d4  lea     rcx, [rbp+2A0h+var_100]
0x1800622db  call    ??R?$_Func_class@XK@std@@QEBAXK@Z; std::_Func_class<void,ulong>::operator()(ulong)
0x1800622e0  xorps   xmm0, xmm0
0x1800622e3  movups  [rbp+2A0h+var_280], xmm0
0x1800622e7  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x1800622ef  movdqu  [rbp+2A0h+var_270], xmm1
0x1800622f4  xor     eax, eax
0x1800622f6  mov     word ptr [rbp+2A0h+var_280], ax
0x1800622fa  lea     rdx, [rbp+2A0h+var_280]
0x1800622fe  lea     rcx, [rbp+2A0h+var_2A0]
0x180062302  call    ??0StringWriter@cxl@@QEAA@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::StringWriter::StringWriter(std::wstring &)
0x180062307  nop
0x180062308  mov     rcx, rax
0x18006230b  call    ??$Write@$0DH@@TextWriter@cxl@@QEAAAEAV01@AEAY0DH@$$CB_W@Z; cxl::TextWriter::Write<55>(wchar_t const (&)[55])
0x180062310  nop
0x180062311  lea     rdx, [rbp+2A0h+var_280]
0x180062315  lea     rcx, [rbp+2A0h+var_2C0]
0x180062319  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18006231e  nop
0x18006231f  mov     eax, cs:dword_18014B6A8
0x180062325  cmp     eax, 4
0x180062328  jbe     short loc_180062361
0x18006232a  mov     edx, 4000h
0x18006232f  lea     rcx, dword_18014B6A8
0x180062336  call    _tlgKeywordOn
0x18006233b  test    al, al
0x18006233d  jz      short loc_180062361
0x18006233f  lea     rcx, [rbp+2A0h+var_2C0]
0x180062343  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180062348  mov     [rbp+2A0h+var_318], rax
0x18006234c  lea     rax, [rbp+2A0h+var_318]
0x180062350  mov     qword ptr [rsp+3A0h+percentComplete], rax
0x180062355  lea     rdx, dword_180129414
0x18006235c  call    ??$Write@U?$_tlgWrapSz@_W@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@_W@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<wchar_t> const &)
0x180062361  call    ?Instance@TraceManager@cxl@@SAAEAV12@XZ; cxl::TraceManager::Instance(void)
0x180062366  lea     rbx, [rax+78h]
0x18006236a  lea     rdx, [rbp+2A0h+var_2C0]
0x18006236e  mov     rcx, rbx
0x180062371  call    ?WriteTo@?$CxlTraits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@cxl@@SAXAEAVTextWriter@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBUFormat@2@@Z; cxl::CxlTraits<std::wstring>::WriteTo(cxl::TextWriter &,std::wstring const &,cxl::Format const &)
0x180062376  mov     rcx, rbx
0x180062379  call    ??$?6UENDL@cxl@@@TextWriter@cxl@@QEAAAEAV01@AEBUENDL@1@@Z; cxl::TextWriter::operator<<<cxl::ENDL>(cxl::ENDL const &)
0x18006237e  nop
0x18006237f  lea     rcx, [rbp+2A0h+var_2C0]
0x180062383  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180062388  lea     rcx, [rbp+2A0h+var_2C0]
0x18006238c  call    ?GetInstance@MiSpaceAdapter@Wsp@@SA?AV?$shared_ptr@VMiSpaceAdapter@Wsp@@@std@@XZ; Wsp::MiSpaceAdapter::GetInstance(void)
0x180062391  nop
0x180062392  lea     rcx, [rbp+2A0h+var_220]
0x180062399  mov     qword ptr [rsp+3A0h+percentComplete], rcx
0x18006239e  lea     r9, [rbp+2A0h+var_21C]
0x1800623a5  mov     r8, r13
0x1800623a8  lea     rdx, [rbp+2A0h+var_2A0]
0x1800623ac  mov     rcx, [rax]
0x1800623af  call    ?UnpackObjectId@MiSpaceAdapter@Wsp@@QEBA?BV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV34@PEAW4WSP_SUBSYSTEM_TYPE@@PEAW4WSP_OBJECT_TYPE@@@Z; Wsp::MiSpaceAdapter::UnpackObjectId(std::wstring const &,WSP_SUBSYSTEM_TYPE *,WSP_OBJECT_TYPE *)
0x1800623b4  nop
0x1800623b5  mov     rdx, rax
0x1800623b8  lea     rcx, [rbp+2A0h+var_260]
0x1800623bc  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x1800623c1  nop
0x1800623c2  lea     rcx, [rbp+2A0h+var_2A0]
0x1800623c6  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800623cb  nop
0x1800623cc  mov     rcx, [rbp+2A0h+var_2B8]; this
0x1800623d0  test    rcx, rcx
0x1800623d3  jz      short loc_1800623DA
0x1800623d5  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800623da  mov     rcx, r14
0x1800623dd  call    ?GetSubsystemType@StorageHealthFacade@Facade@Wsp@@QEBA?BW4WSP_SUBSYSTEM_TYPE@@XZ; Wsp::Facade::StorageHealthFacade::GetSubsystemType(void)
0x1800623e2  cmp     eax, [rbp+2A0h+var_21C]
0x1800623e8  jz      loc_1800624A3
0x1800623ee  mov     ebx, edi
0x1800623f0  lea     rdx, aSubsystemNotSu; "Subsystem not supported"
0x1800623f7  lea     rcx, [rbp+2A0h+var_2C0]
0x1800623fb  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x180062400  nop
0x180062401  mov     eax, cs:dword_18014B6A8
0x180062407  mov     esi, 0CC8h
0x18006240c  cmp     eax, 2
0x18006240f  jbe     short loc_180062465
0x180062411  lea     rcx, [rbp+2A0h+var_2C0]
0x180062415  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18006241a  mov     [rbp+2A0h+var_318], rax
0x18006241e  mov     [rsp+3A0h+var_328], edi
0x180062422  mov     dword ptr [rsp+3A0h+var_338], esi
0x180062426  lea     rax, aWspFacadeStora_1; "Wsp::Facade::StorageHealthFacade::Enabl"...
0x18006242d  mov     [rsp+3A0h+var_340], rax
0x180062432  lea     rax, [rbp+2A0h+var_318]
0x180062436  mov     [rsp+3A0h+var_368], rax
0x18006243b  lea     rax, [rsp+3A0h+var_328]
0x180062440  mov     [rsp+3A0h+var_370], rax
0x180062445  lea     rax, [rsp+3A0h+var_338]
0x18006244a  mov     qword ptr [rsp+3A0h+secondsRemaining], rax
0x18006244f  lea     rax, [rsp+3A0h+var_340]
0x180062454  mov     qword ptr [rsp+3A0h+percentComplete], rax
0x180062459  lea     rdx, dword_180129434
0x180062460  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@U?$_tlgWrapSz@_W@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4AEBU?$_tlgWrapSz@_W@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<wchar_t> const &)
0x180062465  call    ?Instance@TraceManager@cxl@@SAAEAV12@XZ; cxl::TraceManager::Instance(void)
0x18006246a  lea     rcx, [rax+28h]; struct cxl::TextWriter *
0x18006246e  mov     dword ptr [rsp+3A0h+var_338], edi
0x180062472  mov     [rsp+3A0h+var_328], esi
0x180062476  lea     rax, [rsp+3A0h+var_338]
0x18006247b  mov     qword ptr [rsp+3A0h+percentComplete], rax; __int64
0x180062480  lea     r9, [rsp+3A0h+var_328]
0x180062485  lea     rdi, aWspFacadeStora_1; "Wsp::Facade::StorageHealthFacade::Enabl"...
0x18006248c  mov     r8, rdi
0x18006248f  call    ??$WriteLine@_W$$BY0DF@DHH$$BY0BI@_W@TextWriter@cxl@@QEAAXPEB_WAEAY0DF@$$CBDAEBH2AEAY0BI@$$CB_W@Z; cxl::TextWriter::WriteLine<wchar_t,char [53],int,int,wchar_t [24]>(wchar_t const *,char const (&)[53],int const &,int const &,wchar_t const (&)[24])
0x180062494  nop
0x180062495  lea     rcx, [rbp+2A0h+var_2C0]
0x180062499  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18006249e  jmp     loc_180062BF6
0x1800624a3  mov     eax, [rbp+2A0h+var_220]
0x1800624a9  cmp     eax, 0Ch
0x1800624ac  ja      loc_180062BED
0x1800624b2  mov     ecx, 1220h
0x1800624b7  bt      ecx, eax
0x1800624ba  jnb     loc_180062BED
0x1800624c0  lea     rdx, [rbp+2A0h+var_2C0]
0x1800624c4  call    ?GetSmApiSession@StorageHealthFacade@Facade@Wsp@@AEAA?AV?$shared_ptr@VMiSession@mi@@@std@@XZ; Wsp::Facade::StorageHealthFacade::GetSmApiSession(void)
0x1800624c9  mov     rdx, rax
0x1800624cc  lea     rcx, [rbp+2A0h+var_218]
0x1800624d3  call    ??4?$shared_ptr@$$CBVSPACES_VirtualDisk@mismpstorage@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<mismpstorage::SPACES_VirtualDisk const>::operator=(std::shared_ptr<mismpstorage::SPACES_VirtualDisk const> &&)
0x1800624d8  mov     rcx, [rbp+2A0h+var_2B8]; this
0x1800624dc  test    rcx, rcx
0x1800624df  jz      short loc_1800624E6
0x1800624e1  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800624e6  lea     rcx, [rbp+2A0h+var_2C0]
0x1800624ea  call    ?GetInstance@DataStore@ClusWmi@@SA?AV?$shared_ptr@VDataStore@ClusWmi@@@std@@XZ; ClusWmi::DataStore::GetInstance(void)
0x1800624ef  nop
0x1800624f0  lea     rdx, [rbp+2A0h+var_2D0]
0x1800624f4  mov     rcx, [rax]; struct ProtectedPwd *
0x1800624f7  call    ?GetCluster@DataStore@ClusWmi@@QEAAJPEAV?$shared_ptr@UICluster@ClusApi@@@std@@@Z; ClusWmi::DataStore::GetCluster(std::shared_ptr<ClusApi::ICluster> *)
0x1800624fc  mov     ebx, eax
0x1800624fe  mov     rcx, [rbp+2A0h+var_2B8]; this
0x180062502  test    rcx, rcx
0x180062505  jz      short loc_18006250C
0x180062507  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18006250c  test    ebx, ebx
0x18006250e  jns     loc_1800626A7
0x180062514  mov     [rsp+3A0h+var_328], ebx
0x180062518  mov     ecx, cs:dword_18014B6A8
0x18006251e  mov     esi, 0CDFh
0x180062523  cmp     ecx, 2
0x180062526  jbe     short loc_18006256A
0x180062528  mov     eax, [rsp+3A0h+var_328]
0x18006252c  mov     dword ptr [rsp+3A0h+var_338], eax
0x180062530  mov     dword ptr [rsp+3A0h+var_340], esi
0x180062534  lea     rdi, aWspFacadeStora_1; "Wsp::Facade::StorageHealthFacade::Enabl"...
0x18006253b  mov     [rbp+2A0h+var_318], rdi
0x18006253f  lea     rax, [rsp+3A0h+var_338]
0x180062544  mov     [rsp+3A0h+var_370], rax
0x180062549  lea     rax, [rsp+3A0h+var_340]
0x18006254e  mov     qword ptr [rsp+3A0h+secondsRemaining], rax
0x180062553  lea     rax, [rbp+2A0h+var_318]
0x180062557  mov     qword ptr [rsp+3A0h+percentComplete], rax
0x18006255c  lea     rdx, byte_1801292EF
0x180062563  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180062568  jmp     short loc_180062571
0x18006256a  lea     rdi, aWspFacadeStora_1; "Wsp::Facade::StorageHealthFacade::Enabl"...
0x180062571  call    ?Instance@TraceManager@cxl@@SAAEAV12@XZ; cxl::TraceManager::Instance(void)
0x180062576  lea     rcx, [rax+28h]; struct cxl::TextWriter *
0x18006257a  mov     dword ptr [rsp+3A0h+var_340], esi
0x18006257e  lea     rax, [rsp+3A0h+var_328]
0x180062583  mov     qword ptr [rsp+3A0h+percentComplete], rax; __int64
0x180062588  lea     r9, [rsp+3A0h+var_340]
0x18006258d  mov     r8, rdi
0x180062590  call    ??$WriteLine@_W$$BY0DF@DHJ@TextWriter@cxl@@QEAAXPEB_WAEAY0DF@$$CBDAEBHAEBJ@Z; cxl::TextWriter::WriteLine<wchar_t,char [53],int,long>(wchar_t const *,char const (&)[53],int const &,long const &)
0x180062595  mov     ecx, ebx
0x180062597  call    ?SmRCFromHResult@MiSpaceAdapter@Wsp@@SA?AW4SM_RETURN_CODE@@J@Z; Wsp::MiSpaceAdapter::SmRCFromHResult(long)
0x18006259c  mov     ebx, eax
0x18006259e  lea     rdx, aFailedToGetClu; "Failed to Get Cluster"
0x1800625a5  lea     rcx, [rbp+2A0h+var_2C0]
0x1800625a9  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x1800625ae  nop
0x1800625af  test    ebx, ebx
0x1800625b1  jz      loc_180062641
0x1800625b7  mov     ecx, cs:dword_18014B6A8
0x1800625bd  cmp     ecx, 2
0x1800625c0  jbe     short loc_180062613
0x1800625c2  lea     rcx, [rbp+2A0h+var_2C0]
0x1800625c6  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x1800625cb  mov     [rbp+2A0h+var_318], rax
0x1800625cf  mov     dword ptr [rsp+3A0h+var_340], ebx
0x1800625d3  mov     dword ptr [rsp+3A0h+var_338], 0CE0h
0x1800625db  mov     qword ptr [rsp+3A0h+var_328], rdi
0x1800625e0  lea     rax, [rbp+2A0h+var_318]
0x1800625e4  mov     [rsp+3A0h+var_368], rax
0x1800625e9  lea     rax, [rsp+3A0h+var_340]
0x1800625ee  mov     [rsp+3A0h+var_370], rax
0x1800625f3  lea     rax, [rsp+3A0h+var_338]
0x1800625f8  mov     qword ptr [rsp+3A0h+secondsRemaining], rax
0x1800625fd  lea     rax, [rsp+3A0h+var_328]
0x180062602  mov     qword ptr [rsp+3A0h+percentComplete], rax
0x180062607  lea     rdx, byte_180129327
0x18006260e  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@U?$_tlgWrapSz@_W@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4AEBU?$_tlgWrapSz@_W@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<wchar_t> const &)
0x180062613  call    ?Instance@TraceManager@cxl@@SAAEAV12@XZ; cxl::TraceManager::Instance(void)
0x180062618  lea     rcx, [rax+28h]; struct cxl::TextWriter *
0x18006261c  mov     dword ptr [rsp+3A0h+var_340], ebx
0x180062620  mov     dword ptr [rsp+3A0h+var_338], 0CE0h
0x180062628  lea     rax, [rsp+3A0h+var_340]
0x18006262d  mov     qword ptr [rsp+3A0h+percentComplete], rax; __int64
0x180062632  lea     r9, [rsp+3A0h+var_338]
0x180062637  mov     r8, rdi
0x18006263a  call    ??$WriteLine@_W$$BY0DF@DHH$$BY0BG@_W@TextWriter@cxl@@QEAAXPEB_WAEAY0DF@$$CBDAEBH2AEAY0BG@$$CB_W@Z; cxl::TextWriter::WriteLine<wchar_t,char [53],int,int,wchar_t [22]>(wchar_t const *,char const (&)[53],int const &,int const &,wchar_t const (&)[22])
0x18006263f  jmp     short loc_1800626A2
0x180062641  mov     eax, cs:dword_18014B6A8
0x180062647  cmp     eax, 5
0x18006264a  jbe     short loc_1800626A2
0x18006264c  lea     rcx, [rbp+2A0h+var_2C0]
0x180062650  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180062655  mov     [rbp+2A0h+var_318], rax
0x180062659  mov     dword ptr [rsp+3A0h+var_340], 0
0x180062661  mov     dword ptr [rsp+3A0h+var_338], 0CE0h
0x180062669  mov     qword ptr [rsp+3A0h+var_328], rdi
0x18006266e  lea     rax, [rbp+2A0h+var_318]
0x180062672  mov     [rsp+3A0h+var_368], rax
0x180062677  lea     rax, [rsp+3A0h+var_340]
0x18006267c  mov     [rsp+3A0h+var_370], rax
0x180062681  lea     rax, [rsp+3A0h+var_338]
0x180062686  mov     qword ptr [rsp+3A0h+secondsRemaining], rax
0x18006268b  lea     rax, [rsp+3A0h+var_328]
0x180062690  mov     qword ptr [rsp+3A0h+percentComplete], rax
0x180062695  lea     rdx, word_180129366
0x18006269c  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@U?$_tlgWrapSz@_W@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4AEBU?$_tlgWrapSz@_W@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<wchar_t> const &)
0x1800626a1  nop
0x1800626a2  jmp     loc_180062495
0x1800626a7  lea     rdx, [rbp+2A0h+var_2D0]
  ... truncated ...
```
