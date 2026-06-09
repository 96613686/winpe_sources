# Wsp::Facade::StorageHealthFacade::DisableMaintenance(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,std::unique_ptr<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,std::default_delete<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>>> const &,std::unique_ptr<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,std::default_delete<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>>> const &,mi::MiContext &,std::shared_ptr<Wsp::Facade::IExtendedStatus> &)

- ea: `0x180060f98`
- end: `0x18006217e`
- name: `?DisableMaintenance@StorageHealthFacade@Facade@Wsp@@QEAA?AW4SM_RETURN_CODE@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV?$unique_ptr@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$default_delete@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@6@1AEAVMiContext@mi@@AEAV?$shared_ptr@UIExtendedStatus@Facade@Wsp@@@6@@Z`
- size: `4582`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `66`
- tags: `broker_com_uri`

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
- `0x18000c4c4`
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
- `0x180052374`
- `0x180052398`
- `0x1800523bc`
- `0x180053624`
- `0x180058a18`
- `0x180059e04`
- `0x180059e68`
- `0x180059ecc`
- `0x180059f30`
- `0x180059f8c`
- `0x180059fe8`
- `0x18005a170`
- `0x18005a1d4`
- `0x18005a238`
- `0x18005a29c`
- `0x18005b944`
- `0x18005d954`
- `0x18005d980`
- `0x18005e500`
- `0x18005e654`
- `0x18005e684`
- `0x18005ea0c`
- `0x18005f0cc`

## string_xrefs

- `0x18006165b`: `FindWriteCacheDisks`
- `0x180061a7a`: `Waiting for SBL cache state`
- `0x1800619a5`: `Change SBL cache`

## pseudocode

```c
// Hidden C++ exception states: #wind=27
__int64 __fastcall Wsp::Facade::StorageHealthFacade::DisableMaintenance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3,
        const char *a4,
        MI_Context **a5,
        __int64 a6)
{
  MI_Context **v10; // r12
  const MI_Char *v11; // rax
  const MI_Char *v12; // r8
  const MI_Char *v13; // r9
  __int64 v14; // rax
  __int64 v15; // rcx
  __int64 v16; // r8
  __int64 v17; // r9
  char *v18; // rbx
  __int64 v19; // rdx
  __int64 v20; // rdx
  _QWORD *Instance; // rax
  __int64 v22; // rax
  int SubsystemType; // eax
  __int64 v24; // rcx
  MI_Uint32 FaultDomainPhysicalDisks; // edi
  __int64 v26; // rcx
  __int64 v27; // r8
  __int64 v28; // r9
  struct cxl::TraceManager *v29; // rax
  _BYTE *v30; // rcx
  __int64 SmApiSession; // rax
  struct ProtectedPwd **v32; // rax
  signed int Cluster; // ebx
  __int64 v34; // r8
  __int64 v35; // r9
  struct cxl::TraceManager *v36; // rax
  __int64 v37; // rcx
  __int64 v38; // r8
  __int64 v39; // r9
  struct cxl::TraceManager *v40; // rax
  __int64 v41; // rcx
  __int64 v42; // r8
  __int64 v43; // r9
  __int64 v44; // rax
  std::_Ref_count_base *v45; // rcx
  __int64 v46; // rcx
  const MI_Char *v47; // rax
  const MI_Char *v48; // r8
  const MI_Char *v49; // r9
  __int64 v50; // rcx
  __int64 v51; // r8
  __int64 v52; // r9
  struct cxl::TraceManager *v53; // rax
  const MI_Char *v54; // rax
  const MI_Char *v55; // r8
  const MI_Char *v56; // r9
  int v57; // ecx
  int v58; // r9d
  __int64 v59; // rcx
  __int64 v60; // rcx
  __int64 v61; // r8
  __int64 v62; // r9
  struct cxl::TraceManager *v63; // rax
  __int64 v64; // rcx
  __int64 v65; // rcx
  __int64 v66; // r8
  __int64 v67; // r9
  struct cxl::TraceManager *v68; // rax
  __int64 v69; // rcx
  __int64 v70; // rcx
  __int64 v71; // r8
  __int64 v72; // r9
  struct cxl::TraceManager *v73; // rax
  __int64 v74; // rcx
  __int64 v75; // r8
  __int64 v76; // r9
  struct cxl::TraceManager *v77; // rax
  const MI_Char *v78; // rax
  const MI_Char *v79; // r8
  const MI_Char *v80; // r9
  int v81; // ecx
  __int64 v82; // rcx
  __int64 v83; // r8
  __int64 v84; // r9
  struct cxl::TraceManager *v85; // rax
  __int64 v86; // rcx
  __int64 v87; // rcx
  __int64 v88; // r8
  __int64 v89; // r9
  struct cxl::TraceManager *v90; // rax
  __int64 v91; // rcx
  __int64 v92; // r8
  __int64 v93; // r9
  struct cxl::TraceManager *v94; // rax
  const MI_Char *v95; // rax
  const MI_Char *v96; // r8
  const MI_Char *v97; // r9
  __int64 v98; // rcx
  __int64 v99; // r8
  __int64 v100; // r9
  struct cxl::TraceManager *v101; // rax
  __int64 v102; // rcx
  __int64 v103; // r8
  __int64 v104; // r9
  const MI_Char *v105; // rax
  const MI_Char *v106; // r8
  const MI_Char *v107; // r9
  __int64 v108; // r14
  __int64 v109; // r15
  __int64 v110; // rax
  __int64 v111; // rcx
  __int64 v112; // r8
  __int64 v113; // r9
  struct cxl::TextWriter *v114; // rbx
  __int64 v115; // rax
  __int64 value; // rax
  __int64 v117; // rcx
  __int64 v118; // r8
  __int64 v119; // r9
  const MI_Char *v120; // rax
  const MI_Char *v121; // r8
  const MI_Char *v122; // r9
  __int64 v123; // rcx
  __int64 v124; // r8
  __int64 v125; // r9
  __int64 v127; // rax
  __int64 v128; // rax
  MI_Uint32 *secondsRemaining; // [rsp+28h] [rbp-D8h]
  __int64 *secondsRemaininga; // [rsp+28h] [rbp-D8h]
  __int64 v131; // [rsp+60h] [rbp-A0h] BYREF
  MI_Uint32 v132[2]; // [rsp+68h] [rbp-98h] BYREF
  const char *v133; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v134[4]; // [rsp+78h] [rbp-88h] BYREF
  MI_Uint32 v135; // [rsp+7Ch] [rbp-84h] BYREF
  char v136; // [rsp+80h] [rbp-80h] BYREF
  __int64 v137; // [rsp+88h] [rbp-78h] BYREF
  _QWORD *v138; // [rsp+90h] [rbp-70h] BYREF
  const char *v139; // [rsp+98h] [rbp-68h] BYREF
  const char **v140[2]; // [rsp+A0h] [rbp-60h] BYREF
  __int128 v141; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v142; // [rsp+C0h] [rbp-40h]
  __int64 v143; // [rsp+C8h] [rbp-38h] BYREF
  std::_Ref_count_base *v144[2]; // [rsp+D0h] [rbp-30h] BYREF
  _BYTE v145[16]; // [rsp+E0h] [rbp-20h] BYREF
  const char *v146; // [rsp+F0h] [rbp-10h] BYREF
  std::_Ref_count_base *v147; // [rsp+F8h] [rbp-8h]
  _BYTE v148[32]; // [rsp+110h] [rbp+10h] BYREF
  _QWORD v149[4]; // [rsp+130h] [rbp+30h] BYREF
  _BYTE v150[32]; // [rsp+150h] [rbp+50h] BYREF
  _OWORD v151[2]; // [rsp+170h] [rbp+70h] BYREF
  _OWORD v152[2]; // [rsp+190h] [rbp+90h] BYREF
  _BYTE v153[4]; // [rsp+1B0h] [rbp+B0h] BYREF
  int v154; // [rsp+1B4h] [rbp+B4h] BYREF
  _QWORD v155[10]; // [rsp+1B8h] [rbp+B8h] BYREF
  _BYTE v156[32]; // [rsp+208h] [rbp+108h] BYREF
  _BYTE v157[35]; // [rsp+228h] [rbp+128h] BYREF
  char v158; // [rsp+24Bh] [rbp+14Bh] BYREF
  int v159; // [rsp+24Ch] [rbp+14Ch]
  _BYTE v160[16]; // [rsp+250h] [rbp+150h] BYREF
  _BYTE v161[64]; // [rsp+260h] [rbp+160h] BYREF
  _BYTE v162[8]; // [rsp+2A0h] [rbp+1A0h] BYREF
  _BYTE v163[32]; // [rsp+2A8h] [rbp+1A8h] BYREF
  _BYTE v164[8]; // [rsp+2C8h] [rbp+1C8h] BYREF
  _BYTE v165[32]; // [rsp+2D0h] [rbp+1D0h] BYREF
  _BYTE pExceptionObject[112]; // [rsp+2F0h] [rbp+1F0h] BYREF

  v133 = a4;
  v138 = a3;
  v10 = a5;
  v139 = (const char *)a5;
  if ( (unsigned int)dword_18014B6A8 > 5 )
  {
    v135 = 782;
    v146 = "Wsp::Facade::StorageHealthFacade::DisableMaintenance";
    secondsRemaining = &v135;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      (__int64)"Wsp::Facade::StorageHealthFacade::DisableMaintenance",
      (__int64)qword_18012B278,
      (__int64)a3,
      (__int64)a4,
      &v146);
  }
  v152[0] = 0;
  v152[1] = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v152[0]) = 0;
  v141 = 0;
  v142 = 0;
  std::map<std::wstring,mismpstorage::SPACES_PhysicalDisk>::map<std::wstring,mismpstorage::SPACES_PhysicalDisk>(v145);
  std::map<std::wstring,Wsp::Facade::MaintenanceDisk>::map<std::wstring,Wsp::Facade::MaintenanceDisk>(v140);
  Wsp::Facade::MaintenanceModeStruct::MaintenanceModeStruct((Wsp::Facade::MaintenanceModeStruct *)v153);
  *(_OWORD *)v144 = 0;
  v136 = 1;
  v134[0] = 0;
  cxl::load_string(v150, qword_1801578A0, 3002);
  if ( !(unsigned int)Wsp::Facade::StorageHealthFacade::GetSubsystemType(a1) )
  {
    v127 = std::wstring::wstring(v148, L"non highlyavailable subsystems are not supported");
    v128 = cxl::SMResult(&v139, 59001, v127);
    cxl::Error(pExceptionObject, v128);
    throw (cxl::Exception *)pExceptionObject;
  }
  v11 = (const MI_Char *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v150);
  MI_Context_WriteProgress(*a5, v11, v12, v13, 1u, (MI_Uint32)secondsRemaining);
  v151[0] = 0;
  v151[1] = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v151[0]) = 0;
  v14 = cxl::StringWriter::StringWriter(v148, v151);
  cxl::TextWriter::Write<56>(v14);
  std::wstring::wstring(v149, v151);
  if ( (unsigned int)dword_18014B6A8 > 4 && (unsigned __int8)tlgKeywordOn(&dword_18014B6A8, 0x4000) )
  {
    v146 = (const char *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v149);
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>>(
      v15,
      (__int64)byte_18012B173,
      v16,
      v17,
      &v146);
  }
  v18 = (char *)cxl::TraceManager::Instance() + 120;
  cxl::CxlTraits<std::wstring>::WriteTo(v18, v149);
  cxl::TextWriter::operator<<<cxl::ENDL>((__int64)v18);
  std::wstring::_Tidy_deallocate(v149);
  v19 = *a3;
  if ( *a3 )
  {
    v157[33] = 1;
    std::wstring::operator=(v157, v19);
  }
  v20 = *(_QWORD *)a4;
  if ( *(_QWORD *)a4 )
  {
    v157[32] = 1;
    std::wstring::operator=(v156, v20);
  }
  Instance = (_QWORD *)Wsp::MiSpaceAdapter::GetInstance(&v146);
  v22 = Wsp::MiSpaceAdapter::UnpackObjectId(*Instance, (unsigned int)v148, a2, (unsigned int)&v154, (__int64)v153);
  std::wstring::operator=(v152, v22);
  std::wstring::_Tidy_deallocate(v148);
  if ( v147 )
    std::_Ref_count_base::_Decref(v147);
  SubsystemType = Wsp::Facade::StorageHealthFacade::GetSubsystemType(a1);
  if ( SubsystemType != v154 )
  {
    FaultDomainPhysicalDisks = 1;
    std::wstring::wstring(v148, L"Subsystem not supported");
    if ( (unsigned int)dword_18014B6A8 > 2 )
    {
      v146 = (const char *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v148);
      v135 = 1;
      v132[0] = 831;
      v133 = "Wsp::Facade::StorageHealthFacade::DisableMaintenance";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>>(
        v26,
        (__int64)byte_18012B193,
        v27,
        v28,
        &v133,
        (__int64)v132,
        (__int64)&v135,
        &v146);
    }
    v29 = cxl::TraceManager::Instance();
    v132[0] = 1;
    v135 = 831;
    cxl::TextWriter::WriteLine<wchar_t,char [53],int,int,wchar_t [24]>(
      (struct cxl::TraceManager *)((char *)v29 + 40),
      (__int64)v132);
LABEL_17:
    v30 = v148;
LABEL_18:
    std::wstring::_Tidy_deallocate(v30);
    goto LABEL_88;
  }
  SmApiSession = Wsp::Facade::StorageHealthFacade::GetSmApiSession(v24, &v146);
  std::shared_ptr<mismpstorage::SPACES_VirtualDisk const>::operator=(v155, SmApiSession);
  if ( v147 )
    std::_Ref_count_base::_Decref(v147);
  v32 = (struct ProtectedPwd **)ClusWmi::DataStore::GetInstance(&v146);
  Cluster = ClusWmi::DataStore::GetCluster(*v32);
  if ( v147 )
    std::_Ref_count_base::_Decref(v147);
  if ( Cluster < 0 )
  {
    v135 = Cluster;
    if ( (unsigned int)dword_18014B6A8 > 2 )
    {
      v132[0] = v135;
      LODWORD(v131) = 840;
      v146 = "Wsp::Facade::StorageHealthFacade::DisableMaintenance";
      secondsRemaininga = &v131;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        (unsigned int)dword_18014B6A8,
        (__int64)word_18012B1D2,
        v34,
        v35,
        &v146);
    }
    v36 = cxl::TraceManager::Instance();
    LODWORD(v131) = 840;
    cxl::TextWriter::WriteLine<wchar_t,char [53],int,long>(
      (struct cxl::TraceManager *)((char *)v36 + 40),
      (__int64)&v135);
    FaultDomainPhysicalDisks = Wsp::MiSpaceAdapter::SmRCFromHResult((unsigned int)Cluster);
    std::wstring::wstring(v149, L"Failed to Get Cluster");
    if ( FaultDomainPhysicalDisks )
    {
      if ( (unsigned int)dword_18014B6A8 > 2 )
      {
        v146 = (const char *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v149);
        LODWORD(v131) = FaultDomainPhysicalDisks;
        v132[0] = 841;
        v133 = "Wsp::Facade::StorageHealthFacade::DisableMaintenance";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>>(
          v37,
          (__int64)&dword_18012B0B4,
          v38,
          v39,
          &v133,
          (__int64)v132,
          (__int64)&v131,
          &v146);
      }
      v40 = cxl::TraceManager::Instance();
      LODWORD(v131) = FaultDomainPhysicalDisks;
      v132[0] = 841;
      cxl::TextWriter::WriteLine<wchar_t,char [53],int,int,wchar_t [22]>(
        (struct cxl::TraceManager *)((char *)v40 + 40),
        (__int64)&v131);
    }
    else if ( (unsigned int)dword_18014B6A8 > 5 )
    {
      v146 = (const char *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v149);
      LODWORD(v131) = 0;
      v132[0] = 841;
      v133 = "Wsp::Facade::StorageHealthFacade::DisableMaintenance";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>>(
        v41,
        (__int64)byte_18012B0F3,
        v42,
        v43,
        &v133,
        (__int64)v132,
        (__int64)&v131,
        &v146);
    }
    v30 = v149;
    goto LABEL_18;
  }
  v44 = ClusApi::Facade::FacadeFactory::CreateClusterFacade(&v146, v144);
  std::shared_ptr<mismpstorage::SPACES_VirtualDisk const>::operator=(v160, v44);
  v45 = v147;
  if ( v147 )
    std::_Ref_count_base::_Decref(v147);
  Wsp::Facade::StorageHealthFacade::GetLocalNode(v45, v153);
  Wsp::Facade::StorageHealthFacade::S2DEnabled(v46, v153);
  v47 = (const MI_Char *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v150);
  MI_Context_WriteProgress(*a5, v47, v48, v49, 2u, (MI_Uint32)secondsRemaininga);
  LODWORD(secondsRemaininga) = a6;
  FaultDomainPhysicalDisks = Wsp::Facade::StorageHealthFacade::GetFaultDomainPhysicalDisks(
                               a1,
                               a2,
                               (unsigned int)v153,
                               (unsigned int)v140,
                               (__int64)v145);
  if ( FaultDomainPhysicalDisks )
  {
    std::wstring::wstring(v148, L"GetFaultDomainPhysicalDisks");
    if ( (unsigned int)dword_18014B6A8 > 2 )
    {
      v146 = (const char *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v148);
      LODWORD(v131) = FaultDomainPhysicalDisks;
      v132[0] = 864;
      v133 = "Wsp::Facade::StorageHealthFacade::DisableMaintenance";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>>(
        v50,
        (__int64)&dword_18012B134,
        v51,
        v52,
        &v133,
        (__int64)v132,
        (__int64)&v131,
        &v146);
    }
    v53 = cxl::TraceManager::Instance();
    LODWORD(v131) = FaultDomainPhysicalDisks;
    v132[0] = 864;
    cxl::TextWriter::WriteLine<wchar_t,char [53],int,int,wchar_t [28]>(
      (struct cxl::TraceManager *)((char *)v53 + 40),
      (__int64)&v131,
      (__int64)L"GetFaultDomainPhysicalDisks");
    goto LABEL_17;
  }
  if ( v158 && v159 )
  {
    v54 = (const MI_Char *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v150);
    MI_Context_WriteProgress(*a5, v54, v55, v56, 3u, a6);
    FaultDomainPhysicalDisks = Wsp::Facade::StorageHealthFacade::FindWriteCacheDisks(v57, (__int64)v153, v140, v58);
    if ( FaultDomainPhysicalDisks )
    {
      std::wstring::wstring(v148, L"FindWriteCacheDisks");
      if ( (unsigned int)dword_18014B6A8 > 2 )
      {
        v146 = (const char *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v148);
        LODWORD(v131) = FaultDomainPhysicalDisks;
        v132[0] = 882;
        v133 = "Wsp::Facade::StorageHealthFacade::DisableMaintenance";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>>(
          v60,
          (__int64)&word_18012B036,
          v61,
          v62,
          &v133,
          (__int64)v132,
          (__int64)&v131,
          &v146);
      }
      v63 = cxl::TraceManager::Instance();
      LODWORD(v131) = FaultDomainPhysicalDisks;
      v132[0] = 882;
      cxl::TextWriter::WriteLine<wchar_t,char [53],int,int,wchar_t [20]>(
        (struct cxl::TraceManager *)((char *)v63 + 40),
        (__int64)&v131);
      goto LABEL_17;
    }
    FaultDomainPhysicalDisks = Wsp::Facade::StorageHealthFacade::QueryBoundDevices(v59, v153, v140, &v141);
    if ( FaultDomainPhysicalDisks )
    {
      std::wstring::wstring(v148, L"QueryBoundDevices");
      if ( (unsigned int)dword_18014B6A8 > 2 )
      {
        v146 = (const char *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v148);
        LODWORD(v131) = FaultDomainPhysicalDisks;
        v132[0] = 892;
        v133 = "Wsp::Facade::StorageHealthFacade::DisableMaintenance";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>>(
          v65,
          (__int64)byte_18012B075,
          v66,
          v67,
          &v133,
          (__int64)v132,
          (__int64)&v131,
          &v146);
      }
      v68 = cxl::TraceManager::Instance();
      LODWORD(v131) = FaultDomainPhysicalDisks;
      v132[0] = 892;
      cxl::TextWriter::WriteLine<wchar_t,char [53],int,int,wchar_t [18]>(
        (struct cxl::TraceManager *)((char *)v68 + 40),
        (__int64)&v131);
      goto LABEL_17;
    }
    LODWORD(v131) = 5;
    FaultDomainPhysicalDisks = Wsp::Facade::StorageHealthFacade::SetMaintenanceModeIntent(v64, v140, &v131);
    if ( FaultDomainPhysicalDisks )
    {
      std::wstring::wstring(v148, L"Set stopping maintenance mode intent on physical disks");
      if ( (unsigned int)dword_18014B6A8 > 2 )
      {
        v146 = (const char *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v148);
        LODWORD(v131) = FaultDomainPhysicalDisks;
        v132[0] = 900;
        v133 = "Wsp::Facade::StorageHealthFacade::DisableMaintenance";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>>(
          v70,
          (__int64)qword_18012AFB8,
          v71,
          v72,
          &v133,
          (__int64)v132,
          (__int64)&v131,
          &v146);
      }
      v73 = cxl::TraceManager::Instance();
      LODWORD(v131) = FaultDomainPhysicalDisks;
      v132[0] = 900;
      cxl::TextWriter::WriteLine<wchar_t,char [53],int,int,wchar_t [55]>(
        (struct cxl::TraceManager *)((char *)v73 + 40),
        (__int64)&v131);
      goto LABEL_17;
    }
    LODWORD(v131) = 4;
    FaultDomainPhysicalDisks = Wsp::Facade::StorageHealthFacade::ClearMaintenanceModeIntent(v69, v140, &v131);
    if ( FaultDomainPhysicalDisks )
    {
      std::wstring::wstring(v148, L"Clear starting maintenance mode intent on physical disks");
      if ( (unsigned int)dword_18014B6A8 > 2 )
      {
        v146 = (const char *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v148);
        LODWORD(v131) = FaultDomainPhysicalDisks;
        v132[0] = 907;
        v133 = "Wsp::Facade::StorageHealthFacade::DisableMaintenance";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>>(
          v74,
          (__int64)&byte_18012AFF7,
          v75,
          v76,
          &v133,
          (__int64)v132,
          (__int64)&v131,
          &v146);
      }
      v77 = cxl::TraceManager::Instance();
      LODWORD(v131) = FaultDomainPhysicalDisks;
      v132[0] = 907;
      cxl::TextWriter::WriteLine<wchar_t,char [53],int,int,wchar_t [57]>(
        (struct cxl::TraceManager *)((char *)v77 + 40),
        (__int64)&v131);
      goto LABEL_17;
    }
    v78 = (const MI_Char *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v150);
    MI_Context_WriteProgress(*a5, v78, v79, v80, 4u, (MI_Uint32)secondsRemaininga);
    FaultDomainPhysicalDisks = Wsp::Facade::StorageHealthFacade::ChangeWriteCache(
                                 v81,
                                 (unsigned int)&v136,
                                 (unsigned int)v153,
                                 (unsigned int)v140,
                                 a6);
    if ( FaultDomainPhysicalDisks )
    {
      std::wstring::wstring(v148, L"Change SBL cache");
      if ( (unsigned int)dword_18014B6A8 > 2 )
      {
        v146 = (const char *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v148);
        LODWORD(v131) = FaultDomainPhysicalDisks;
        v132[0] = 927;
        v133 = "Wsp::Facade::StorageHealthFacade::DisableMaintenance";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>>(
          v82,
          (__int64)word_18012AF3A,
          v83,
          v84,
          &v133,
          (__int64)v132,
          (__int64)&v131,
          &v146);
      }
      v85 = cxl::TraceManager::Instance();
      LODWORD(v131) = FaultDomainPhysicalDisks;
      v132[0] = 927;
      cxl::TextWriter::WriteLine<wchar_t,char [53],int,int,wchar_t [17]>(
        (struct cxl::TraceManager *)((char *)v85 + 40),
        (__int64)&v131);
      goto LABEL_17;
    }
    FaultDomainPhysicalDisks = Wsp::Facade::StorageHealthFacade::GetDiskCacheState(
                                 a1,
                                 (__int64)v153,
                                 (__int64)v140,
                                 1,
                                 (__int64)a5,
                                 a6);
    if ( FaultDomainPhysicalDisks )
    {
      std::wstring::wstring(v148, L"Waiting for SBL cache state");
      if ( (unsigned int)dword_18014B6A8 > 2 )
      {
        v146 = (const char *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v148);
        LODWORD(v131) = FaultDomainPhysicalDisks;
        v132[0] = 940;
        v133 = "Wsp::Facade::StorageHealthFacade::DisableMaintenance";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>>(
          v87,
          (__int64)byte_18012AF79,
          v88,
          v89,
          &v133,
          (__int64)v132,
          (__int64)&v131,
          &v146);
      }
      v90 = cxl::TraceManager::Instance();
      LODWORD(v131) = FaultDomainPhysicalDisks;
      v132[0] = 940;
      cxl::TextWriter::WriteLine<wchar_t,char [53],int,int,wchar_t [28]>(
        (struct cxl::TraceManager *)((char *)v90 + 40),
        (__int64)&v131,
        (__int64)L"Waiting for SBL cache state");
      goto LABEL_17;
    }
    LODWORD(v131) = 5;
    FaultDomainPhysicalDisks = Wsp::Facade::StorageHealthFacade::ClearMaintenanceModeIntent(v86, v140, &v131);
    if ( FaultDomainPhysicalDisks )
    {
      std::wstring::wstring(v148, L"Set stopping maintenance mode intent on physical disks");
      if ( (unsigned int)dword_18014B6A8 > 2 )
      {
        v146 = (const char *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v148);
        LODWORD(v131) = FaultDomainPhysicalDisks;
        v132[0] = 947;
        v133 = "Wsp::Facade::StorageHealthFacade::DisableMaintenance";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>>(
          v91,
          (__int64)byte_18012AE7B,
          v92,
          v93,
          &v133,
          (__int64)v132,
          (__int64)&v131,
          &v146);
      }
      v94 = cxl::TraceManager::Instance();
      LODWORD(v131) = FaultDomainPhysicalDisks;
      v132[0] = 947;
      cxl::TextWriter::WriteLine<wchar_t,char [53],int,int,wchar_t [55]>(
        (struct cxl::TraceManager *)((char *)v94 + 40),
        (__int64)&v131);
      goto LABEL_17;
    }
  }
  v95 = (const MI_Char *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v150);
  MI_Context_WriteProgress(*a5, v95, v96, v97, 0x5Bu, (MI_Uint32)secondsRemaininga);
  std::shared_ptr<ClusApi::IStorage>::shared_ptr<ClusApi::IStorage>(&v146, v155);
  *(_QWORD *)v132 = 0;
  v131 = 0;
  v137 = 0;
  secondsRemaininga = &v131;
  FaultDomainPhysicalDisks = Wsp::Facade::StorageHealthFacade::CallMaintenanceOnTargetObject(
                               &v158,
                               v161,
                               v153,
                               v134,
                               &v137);
  std::unique_ptr<bool>::~unique_ptr<bool>(&v137);
  std::unique_ptr<bool>::~unique_ptr<bool>(&v131);
  std::unique_ptr<unsigned int>::~unique_ptr<unsigned int>(v132);
  std::wstring::wstring(v149, a2);
  if ( FaultDomainPhysicalDisks )
  {
    if ( (unsigned int)dword_18014B6A8 > 2 )
    {
      v146 = (const char *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v149);
      LODWORD(v131) = FaultDomainPhysicalDisks;
      v132[0] = 974;
      v133 = "Wsp::Facade::StorageHealthFacade::DisableMaintenance";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>>(
        v98,
        (__int64)word_18012AEBA,
        v99,
        v100,
        &v133,
        (__int64)v132,
        (__int64)&v131,
        &v146);
    }
    v101 = cxl::TraceManager::Instance();
    LODWORD(v131) = FaultDomainPhysicalDisks;
    v132[0] = 974;
    cxl::TextWriter::WriteLine<wchar_t,char [53],int,int,std::wstring>(
      (struct cxl::TraceManager *)((char *)v101 + 40),
      (__int64)&v131,
      a2);
  }
  else if ( (unsigned int)dword_18014B6A8 > 5 )
  {
    v146 = (const char *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v149);
    LODWORD(v131) = 0;
    v132[0] = 974;
    v133 = "Wsp::Facade::StorageHealthFacade::DisableMaintenance";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>>(
      v102,
      (__int64)byte_18012AEF9,
      v103,
      v104,
      &v133,
      (__int64)v132,
      (__int64)&v131,
      &v146);
  }
  std::wstring::_Tidy_deallocate(v149);
  if ( !FaultDomainPhysicalDisks )
  {
    v105 = (const MI_Char *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v150);
    MI_Context_WriteProgress(*a5, v105, v106, v107, 0x5Cu, (MI_Uint32)secondsRemaininga);
    if ( v158 )
    {
      if ( v159 )
      {
        v109 = *((_QWORD *)&v141 + 1);
        v108 = v141;
        if ( (_QWORD)v141 != *((_QWORD *)&v141 + 1) )
        {
          do
          {
            std::shared_ptr<ClusApi::IStorage>::shared_ptr<ClusApi::IStorage>(v149, v155);
            v146 = 0;
            v133 = 0;
            v138 = 0;
            v143 = 0;
            *(_QWORD *)v132 = 0;
            LODWORD(v131) = 5;
            secondsRemaininga = &v143;
            FaultDomainPhysicalDisks = Wsp::Facade::StorageHealthFacade::CallMaintenanceOnTargetObject(
                                         &v158,
                                         v108,
                                         &v131,
                                         v134,
                                         v132);
            std::unique_ptr<bool>::~unique_ptr<bool>(v132);
            std::unique_ptr<bool>::~unique_ptr<bool>(&v143);
            std::unique_ptr<unsigned int>::~unique_ptr<unsigned int>(&v138);
            std::unique_ptr<std::wstring>::~unique_ptr<std::wstring>(&v133);
            std::unique_ptr<std::wstring>::~unique_ptr<std::wstring>(&v146);
            v110 = mismpstorage::SPACES_StoragePool::ObjectId(v108, v162);
            mismpstorage::read_property<std::wstring>::get_value(v110);
            std::wstring::_Tidy_deallocate(v163);
            if ( FaultDomainPhysicalDisks )
            {
              if ( (unsigned int)dword_18014B6A8 > 2 )
              {
                v146 = (const char *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v148);
                LODWORD(v131) = FaultDomainPhysicalDisks;
                v132[0] = 1014;
                v133 = "Wsp::Facade::StorageHealthFacade::DisableMaintenance";
                _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>>(
                  v111,
                  (__int64)qword_18012ADA0,
                  v112,
                  v113,
                  &v133,
                  (__int64)v132,
                  (__int64)&v131,
                  &v146);
              }
              v114 = (struct cxl::TraceManager *)((char *)cxl::TraceManager::Instance() + 40);
              v115 = mismpstorage::SPACES_StoragePool::ObjectId(v108, v164);
              value = mismpstorage::read_property<std::wstring>::get_value(v115);
              v135 = FaultDomainPhysicalDisks;
              LODWORD(v137) = 1014;
              cxl::TextWriter::WriteLine<wchar_t,char [53],int,int,std::wstring>(v114, (__int64)&v135, value);
              std::wstring::_Tidy_deallocate(&v146);
              std::wstring::_Tidy_deallocate(v165);
            }
            else if ( (unsigned int)dword_18014B6A8 > 5 )
            {
              v146 = (const char *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v148);
              LODWORD(v131) = 0;
              v132[0] = 1014;
              v133 = "Wsp::Facade::StorageHealthFacade::DisableMaintenance";
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>>(
                v117,
                (__int64)&byte_18012ADDF,
                v118,
                v119,
                &v133,
                (__int64)v132,
                (__int64)&v131,
                &v146);
            }
            std::wstring::_Tidy_deallocate(v148);
            if ( FaultDomainPhysicalDisks )
              break;
            v108 += 64;
          }
          while ( v108 != v109 );
          v10 = (MI_Context **)v139;
        }
      }
    }
  }
LABEL_88:
  v120 = (const MI_Char *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v150);
  MI_Context_WriteProgress(*v10, v120, v121, v122, 0x64u, (MI_Uint32)secondsRemaininga);
  if ( (unsigned int)dword_18014B6A8 > 5 )
  {
    LODWORD(v137) = 1034;
    v139 = "Wsp::Facade::StorageHealthFacade::DisableMaintenance";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      v123,
      (__int64)qword_18012AE20,
      v124,
      v125,
      &v139);
  }
  std::wstring::_Tidy_deallocate(v151);
  std::wstring::_Tidy_deallocate(v150);
  if ( v144[1] )
    std::_Ref_count_base::_Decref(v144[1]);
  Wsp::Facade::MaintenanceModeStruct::~MaintenanceModeStruct((Wsp::Facade::MaintenanceModeStruct *)v153);
  std::_Tree<std::_Tmap_traits<std::wstring,Wsp::Facade::MaintenanceDisk,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,Wsp::Facade::MaintenanceDisk>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,Wsp::Facade::MaintenanceDisk,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,Wsp::Facade::MaintenanceDisk>>,0>>(v140);
  std::_Tree<std::_Tmap_traits<std::wstring,mismpstorage::SPACES_VirtualDisk,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,mismpstorage::SPACES_VirtualDisk>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,mismpstorage::SPACES_VirtualDisk,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,mismpstorage::SPACES_VirtualDisk>>,0>>(v145);
  if ( (_QWORD)v141 )
  {
    std::_Destroy_range<std::allocator<mismpstorage::SPACES_PhysicalDisk>>(v141, *((_QWORD *)&v141 + 1));
    std::_Deallocate<16>((void *)v141, (v142 - v141) & 0xFFFFFFFFFFFFFFC0uLL);
    v141 = 0;
    v142 = 0;
  }
  std::wstring::_Tidy_deallocate(v152);
  return FaultDomainPhysicalDisks;
}

```

## disassembly

```asm
0x180060f98  push    rbp
0x180060f9a  push    rbx
0x180060f9b  push    rsi
0x180060f9c  push    rdi
0x180060f9d  push    r12
0x180060f9f  push    r13
0x180060fa1  push    r14
0x180060fa3  push    r15
0x180060fa5  lea     rbp, [rsp-278h]
0x180060fad  sub     rsp, 378h
0x180060fb4  mov     rax, cs:__security_cookie
0x180060fbb  xor     rax, rsp
0x180060fbe  mov     [rbp+2B0h+var_50], rax
0x180060fc5  mov     rdi, r9
0x180060fc8  mov     [rsp+3B0h+var_340], r9
0x180060fcd  mov     rsi, r8
0x180060fd0  mov     [rbp+2B0h+var_320], r8
0x180060fd4  mov     r15, rdx
0x180060fd7  mov     r14, rcx
0x180060fda  mov     r12, [rbp+2B0h+arg_20]
0x180060fe1  mov     [rbp+2B0h+var_318], r12
0x180060fe5  mov     r13, qword ptr [rbp+2B0h+arg_28]
0x180060fec  mov     eax, cs:dword_18014B6A8
0x180060ff2  lea     rcx, aWspFacadeStora_26; "Wsp::Facade::StorageHealthFacade::Disab"...
0x180060ff9  cmp     eax, 5
0x180060ffc  jbe     short loc_180061029
0x180060ffe  mov     [rsp+3B0h+var_334], 30Eh
0x180061006  mov     [rbp+2B0h+var_2C0], rcx
0x18006100a  lea     rax, [rsp+3B0h+var_334]
0x18006100f  mov     qword ptr [rsp+3B0h+secondsRemaining], rax; secondsRemaining
0x180061014  lea     rax, [rbp+2B0h+var_2C0]
0x180061018  mov     qword ptr [rsp+3B0h+percentComplete], rax
0x18006101d  lea     rdx, qword_18012B278
0x180061024  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x180061029  xorps   xmm0, xmm0
0x18006102c  movups  [rbp+2B0h+var_220], xmm0
0x180061033  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x18006103b  movdqu  [rbp+2B0h+var_210], xmm1
0x180061043  xor     eax, eax
0x180061045  mov     word ptr [rbp+2B0h+var_220], ax
0x18006104c  movdqu  [rbp+2B0h+var_300], xmm0
0x180061051  mov     [rbp+2B0h+var_2F0], rax
0x180061055  lea     rcx, [rbp+2B0h+var_2D0]
0x180061059  call    ??0?$map@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@VSPACES_PhysicalDisk@mismpstorage@@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@VSPACES_PhysicalDisk@mismpstorage@@@std@@@2@@std@@QEAA@XZ; std::map<std::wstring,mismpstorage::SPACES_PhysicalDisk>::map<std::wstring,mismpstorage::SPACES_PhysicalDisk>(void)
0x18006105e  nop
0x18006105f  lea     rcx, [rbp+2B0h+var_310]
0x180061063  call    ??0?$map@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UMaintenanceDisk@Facade@Wsp@@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UMaintenanceDisk@Facade@Wsp@@@std@@@2@@std@@QEAA@XZ; std::map<std::wstring,Wsp::Facade::MaintenanceDisk>::map<std::wstring,Wsp::Facade::MaintenanceDisk>(void)
0x180061068  nop
0x180061069  lea     rcx, [rbp+2B0h+var_200]; this
0x180061070  call    ??0MaintenanceModeStruct@Facade@Wsp@@QEAA@XZ; Wsp::Facade::MaintenanceModeStruct::MaintenanceModeStruct(void)
0x180061075  nop
0x180061076  xorps   xmm1, xmm1
0x180061079  movdqu  xmmword ptr [rbp+2B0h+var_2E0], xmm1
0x18006107e  mov     [rbp+2B0h+var_330], 1
0x180061082  mov     [rsp+3B0h+var_338], 0
0x180061087  mov     r8d, 0BBAh
0x18006108d  mov     rdx, cs:qword_1801578A0
0x180061094  lea     rcx, [rbp+2B0h+var_260]
0x180061098  call    ?load_string@cxl@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEAUHINSTANCE__@@I@Z; cxl::load_string(HINSTANCE__ *,uint)
0x18006109d  nop
0x18006109e  mov     rcx, r14
0x1800610a1  call    ?GetSubsystemType@StorageHealthFacade@Facade@Wsp@@QEBA?BW4WSP_SUBSYSTEM_TYPE@@XZ; Wsp::Facade::StorageHealthFacade::GetSubsystemType(void)
0x1800610a6  test    eax, eax
0x1800610a8  jz      loc_18006213A
0x1800610ae  lea     rcx, [rbp+2B0h+var_260]
0x1800610b2  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x1800610b7  mov     rdx, rax; activity
0x1800610ba  mov     [rsp+3B0h+percentComplete], 1; percentComplete
0x1800610c2  mov     rcx, [r12]; context
0x1800610c6  call    MI_Context_WriteProgress
0x1800610cb  xorps   xmm0, xmm0
0x1800610ce  movups  [rbp+2B0h+var_240], xmm0
0x1800610d2  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x1800610da  movdqu  [rbp+2B0h+var_230], xmm1
0x1800610e2  xor     eax, eax
0x1800610e4  mov     word ptr [rbp+2B0h+var_240], ax
0x1800610e8  lea     rdx, [rbp+2B0h+var_240]
0x1800610ec  lea     rcx, [rbp+2B0h+var_2A0]
0x1800610f0  call    ??0StringWriter@cxl@@QEAA@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::StringWriter::StringWriter(std::wstring &)
0x1800610f5  nop
0x1800610f6  mov     rcx, rax
0x1800610f9  call    ??$Write@$0DI@@TextWriter@cxl@@QEAAAEAV01@AEAY0DI@$$CB_W@Z; cxl::TextWriter::Write<56>(wchar_t const (&)[56])
0x1800610fe  nop
0x1800610ff  lea     rdx, [rbp+2B0h+var_240]
0x180061103  lea     rcx, [rbp+2B0h+var_280]
0x180061107  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18006110c  nop
0x18006110d  mov     eax, cs:dword_18014B6A8
0x180061113  cmp     eax, 4
0x180061116  jbe     short loc_18006114F
0x180061118  mov     edx, 4000h
0x18006111d  lea     rcx, dword_18014B6A8
0x180061124  call    _tlgKeywordOn
0x180061129  test    al, al
0x18006112b  jz      short loc_18006114F
0x18006112d  lea     rcx, [rbp+2B0h+var_280]
0x180061131  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180061136  mov     [rbp+2B0h+var_2C0], rax
0x18006113a  lea     rax, [rbp+2B0h+var_2C0]
0x18006113e  mov     qword ptr [rsp+3B0h+percentComplete], rax
0x180061143  lea     rdx, byte_18012B173
0x18006114a  call    ??$Write@U?$_tlgWrapSz@_W@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@_W@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<wchar_t> const &)
0x18006114f  call    ?Instance@TraceManager@cxl@@SAAEAV12@XZ; cxl::TraceManager::Instance(void)
0x180061154  lea     rbx, [rax+78h]
0x180061158  lea     rdx, [rbp+2B0h+var_280]
0x18006115c  mov     rcx, rbx
0x18006115f  call    ?WriteTo@?$CxlTraits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@cxl@@SAXAEAVTextWriter@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBUFormat@2@@Z; cxl::CxlTraits<std::wstring>::WriteTo(cxl::TextWriter &,std::wstring const &,cxl::Format const &)
0x180061164  mov     rcx, rbx
0x180061167  call    ??$?6UENDL@cxl@@@TextWriter@cxl@@QEAAAEAV01@AEBUENDL@1@@Z; cxl::TextWriter::operator<<<cxl::ENDL>(cxl::ENDL const &)
0x18006116c  nop
0x18006116d  lea     rcx, [rbp+2B0h+var_280]
0x180061171  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180061176  mov     rdx, [rsi]
0x180061179  xor     ebx, ebx
0x18006117b  test    rdx, rdx
0x18006117e  jz      short loc_180061193
0x180061180  mov     [rbp+2B0h+var_167], 1
0x180061187  lea     rcx, [rbp+2B0h+var_188]
0x18006118e  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x180061193  mov     rdx, [rdi]
0x180061196  test    rdx, rdx
0x180061199  jz      short loc_1800611AE
0x18006119b  mov     [rbp+2B0h+var_168], 1
0x1800611a2  lea     rcx, [rbp+2B0h+var_1A8]
0x1800611a9  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x1800611ae  lea     rcx, [rbp+2B0h+var_2C0]
0x1800611b2  call    ?GetInstance@MiSpaceAdapter@Wsp@@SA?AV?$shared_ptr@VMiSpaceAdapter@Wsp@@@std@@XZ; Wsp::MiSpaceAdapter::GetInstance(void)
0x1800611b7  nop
0x1800611b8  lea     rcx, [rbp+2B0h+var_200]
0x1800611bf  mov     qword ptr [rsp+3B0h+percentComplete], rcx
0x1800611c4  lea     r9, [rbp+2B0h+var_1FC]
0x1800611cb  mov     r8, r15
0x1800611ce  lea     rdx, [rbp+2B0h+var_2A0]
0x1800611d2  mov     rcx, [rax]
0x1800611d5  call    ?UnpackObjectId@MiSpaceAdapter@Wsp@@QEBA?BV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV34@PEAW4WSP_SUBSYSTEM_TYPE@@PEAW4WSP_OBJECT_TYPE@@@Z; Wsp::MiSpaceAdapter::UnpackObjectId(std::wstring const &,WSP_SUBSYSTEM_TYPE *,WSP_OBJECT_TYPE *)
0x1800611da  nop
0x1800611db  mov     rdx, rax
0x1800611de  lea     rcx, [rbp+2B0h+var_220]
0x1800611e5  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x1800611ea  nop
0x1800611eb  lea     rcx, [rbp+2B0h+var_2A0]
0x1800611ef  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800611f4  nop
0x1800611f5  mov     rcx, [rbp+2B0h+var_2B8]; this
0x1800611f9  test    rcx, rcx
0x1800611fc  jz      short loc_180061203
0x1800611fe  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180061203  mov     rcx, r14
0x180061206  call    ?GetSubsystemType@StorageHealthFacade@Facade@Wsp@@QEBA?BW4WSP_SUBSYSTEM_TYPE@@XZ; Wsp::Facade::StorageHealthFacade::GetSubsystemType(void)
0x18006120b  cmp     eax, [rbp+2B0h+var_1FC]
0x180061211  jz      loc_1800612DA
0x180061217  mov     edi, 1
0x18006121c  lea     rdx, aSubsystemNotSu; "Subsystem not supported"
0x180061223  lea     rcx, [rbp+2B0h+var_2A0]
0x180061227  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18006122c  nop
0x18006122d  mov     eax, cs:dword_18014B6A8
0x180061233  lea     esi, [rdi+1]
0x180061236  mov     r15d, 33Fh
0x18006123c  cmp     eax, esi
0x18006123e  jbe     short loc_180061297
0x180061240  lea     rcx, [rbp+2B0h+var_2A0]
0x180061244  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180061249  mov     [rbp+2B0h+var_2C0], rax
0x18006124d  mov     [rsp+3B0h+var_334], edi
0x180061251  mov     [rsp+3B0h+var_348], r15d
0x180061256  lea     r14, aWspFacadeStora_26; "Wsp::Facade::StorageHealthFacade::Disab"...
0x18006125d  mov     [rsp+3B0h+var_340], r14
0x180061262  lea     rax, [rbp+2B0h+var_2C0]
0x180061266  mov     [rsp+3B0h+var_378], rax
0x18006126b  lea     rax, [rsp+3B0h+var_334]
0x180061270  mov     [rsp+3B0h+var_380], rax
0x180061275  lea     rax, [rsp+3B0h+var_348]
0x18006127a  mov     qword ptr [rsp+3B0h+secondsRemaining], rax
0x18006127f  lea     rax, [rsp+3B0h+var_340]
0x180061284  mov     qword ptr [rsp+3B0h+percentComplete], rax
0x180061289  lea     rdx, byte_18012B193
0x180061290  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@U?$_tlgWrapSz@_W@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4AEBU?$_tlgWrapSz@_W@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<wchar_t> const &)
0x180061295  jmp     short loc_18006129E
0x180061297  lea     r14, aWspFacadeStora_26; "Wsp::Facade::StorageHealthFacade::Disab"...
0x18006129e  call    ?Instance@TraceManager@cxl@@SAAEAV12@XZ; cxl::TraceManager::Instance(void)
0x1800612a3  lea     rcx, [rax+28h]; struct cxl::TextWriter *
0x1800612a7  mov     [rsp+3B0h+var_348], 1
0x1800612af  mov     [rsp+3B0h+var_334], r15d
0x1800612b4  lea     rax, [rsp+3B0h+var_348]
0x1800612b9  mov     qword ptr [rsp+3B0h+percentComplete], rax; __int64
0x1800612be  lea     r9, [rsp+3B0h+var_334]
0x1800612c3  mov     r8, r14
0x1800612c6  call    ??$WriteLine@_W$$BY0DF@DHH$$BY0BI@_W@TextWriter@cxl@@QEAAXPEB_WAEAY0DF@$$CBDAEBH2AEAY0BI@$$CB_W@Z; cxl::TextWriter::WriteLine<wchar_t,char [53],int,int,wchar_t [24]>(wchar_t const *,char const (&)[53],int const &,int const &,wchar_t const (&)[24])
0x1800612cb  nop
0x1800612cc  lea     rcx, [rbp+2B0h+var_2A0]
0x1800612d0  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800612d5  jmp     loc_180062041
0x1800612da  lea     rdx, [rbp+2B0h+var_2C0]
0x1800612de  call    ?GetSmApiSession@StorageHealthFacade@Facade@Wsp@@AEAA?AV?$shared_ptr@VMiSession@mi@@@std@@XZ; Wsp::Facade::StorageHealthFacade::GetSmApiSession(void)
0x1800612e3  mov     rdx, rax
0x1800612e6  lea     rcx, [rbp+2B0h+var_1F8]
0x1800612ed  call    ??4?$shared_ptr@$$CBVSPACES_VirtualDisk@mismpstorage@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<mismpstorage::SPACES_VirtualDisk const>::operator=(std::shared_ptr<mismpstorage::SPACES_VirtualDisk const> &&)
0x1800612f2  mov     rcx, [rbp+2B0h+var_2B8]; this
0x1800612f6  test    rcx, rcx
0x1800612f9  jz      short loc_180061300
0x1800612fb  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180061300  lea     rcx, [rbp+2B0h+var_2C0]
0x180061304  call    ?GetInstance@DataStore@ClusWmi@@SA?AV?$shared_ptr@VDataStore@ClusWmi@@@std@@XZ; ClusWmi::DataStore::GetInstance(void)
0x180061309  nop
0x18006130a  lea     rdx, [rbp+2B0h+var_2E0]
0x18006130e  mov     rcx, [rax]; struct ProtectedPwd *
0x180061311  call    ?GetCluster@DataStore@ClusWmi@@QEAAJPEAV?$shared_ptr@UICluster@ClusApi@@@std@@@Z; ClusWmi::DataStore::GetCluster(std::shared_ptr<ClusApi::ICluster> *)
0x180061316  mov     ebx, eax
0x180061318  mov     rcx, [rbp+2B0h+var_2B8]; this
0x18006131c  test    rcx, rcx
0x18006131f  jz      short loc_180061326
0x180061321  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180061326  test    ebx, ebx
0x180061328  jns     loc_1800614C6
0x18006132e  mov     [rsp+3B0h+var_334], ebx
0x180061332  mov     ecx, cs:dword_18014B6A8
0x180061338  mov     edi, 348h
0x18006133d  mov     esi, 2
0x180061342  cmp     ecx, esi
0x180061344  jbe     short loc_180061388
0x180061346  mov     eax, [rsp+3B0h+var_334]
0x18006134a  mov     [rsp+3B0h+var_348], eax
0x18006134e  mov     dword ptr [rsp+3B0h+var_350], edi
0x180061352  lea     r14, aWspFacadeStora_26; "Wsp::Facade::StorageHealthFacade::Disab"...
0x180061359  mov     [rbp+2B0h+var_2C0], r14
0x18006135d  lea     rax, [rsp+3B0h+var_348]
0x180061362  mov     [rsp+3B0h+var_380], rax
0x180061367  lea     rax, [rsp+3B0h+var_350]
0x18006136c  mov     qword ptr [rsp+3B0h+secondsRemaining], rax
0x180061371  lea     rax, [rbp+2B0h+var_2C0]
0x180061375  mov     qword ptr [rsp+3B0h+percentComplete], rax
0x18006137a  lea     rdx, word_18012B1D2
0x180061381  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180061386  jmp     short loc_18006138F
0x180061388  lea     r14, aWspFacadeStora_26; "Wsp::Facade::StorageHealthFacade::Disab"...
0x18006138f  call    ?Instance@TraceManager@cxl@@SAAEAV12@XZ; cxl::TraceManager::Instance(void)
0x180061394  lea     rcx, [rax+28h]; struct cxl::TextWriter *
0x180061398  mov     dword ptr [rsp+3B0h+var_350], edi
0x18006139c  lea     rax, [rsp+3B0h+var_334]
0x1800613a1  mov     qword ptr [rsp+3B0h+percentComplete], rax; __int64
0x1800613a6  lea     r9, [rsp+3B0h+var_350]
0x1800613ab  mov     r8, r14
0x1800613ae  call    ??$WriteLine@_W$$BY0DF@DHJ@TextWriter@cxl@@QEAAXPEB_WAEAY0DF@$$CBDAEBHAEBJ@Z; cxl::TextWriter::WriteLine<wchar_t,char [53],int,long>(wchar_t const *,char const (&)[53],int const &,long const &)
0x1800613b3  mov     ecx, ebx
0x1800613b5  call    ?SmRCFromHResult@MiSpaceAdapter@Wsp@@SA?AW4SM_RETURN_CODE@@J@Z; Wsp::MiSpaceAdapter::SmRCFromHResult(long)
0x1800613ba  mov     edi, eax
0x1800613bc  lea     rdx, aFailedToGetClu; "Failed to Get Cluster"
0x1800613c3  lea     rcx, [rbp+2B0h+var_280]
0x1800613c7  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x1800613cc  nop
0x1800613cd  xor     ebx, ebx
0x1800613cf  test    edi, edi
0x1800613d1  jz      loc_180061460
0x1800613d7  mov     ecx, cs:dword_18014B6A8
0x1800613dd  cmp     ecx, esi
0x1800613df  jbe     short loc_180061432
0x1800613e1  lea     rcx, [rbp+2B0h+var_280]
0x1800613e5  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x1800613ea  mov     [rbp+2B0h+var_2C0], rax
0x1800613ee  mov     dword ptr [rsp+3B0h+var_350], edi
0x1800613f2  mov     [rsp+3B0h+var_348], 349h
0x1800613fa  mov     [rsp+3B0h+var_340], r14
0x1800613ff  lea     rax, [rbp+2B0h+var_2C0]
0x180061403  mov     [rsp+3B0h+var_378], rax
0x180061408  lea     rax, [rsp+3B0h+var_350]
0x18006140d  mov     [rsp+3B0h+var_380], rax
0x180061412  lea     rax, [rsp+3B0h+var_348]
0x180061417  mov     qword ptr [rsp+3B0h+secondsRemaining], rax
0x18006141c  lea     rax, [rsp+3B0h+var_340]
0x180061421  mov     qword ptr [rsp+3B0h+percentComplete], rax
0x180061426  lea     rdx, dword_18012B0B4
0x18006142d  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@U?$_tlgWrapSz@_W@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4AEBU?$_tlgWrapSz@_W@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<wchar_t> const &)
0x180061432  call    ?Instance@TraceManager@cxl@@SAAEAV12@XZ; cxl::TraceManager::Instance(void)
0x180061437  lea     rcx, [rax+28h]; struct cxl::TextWriter *
0x18006143b  mov     dword ptr [rsp+3B0h+var_350], edi
0x18006143f  mov     [rsp+3B0h+var_348], 349h
0x180061447  lea     rax, [rsp+3B0h+var_350]
0x18006144c  mov     qword ptr [rsp+3B0h+percentComplete], rax; __int64
0x180061451  lea     r9, [rsp+3B0h+var_348]
0x180061456  mov     r8, r14
0x180061459  call    ??$WriteLine@_W$$BY0DF@DHH$$BY0BG@_W@TextWriter@cxl@@QEAAXPEB_WAEAY0DF@$$CBDAEBH2AEAY0BG@$$CB_W@Z; cxl::TextWriter::WriteLine<wchar_t,char [53],int,int,wchar_t [22]>(wchar_t const *,char const (&)[53],int const &,int const &,wchar_t const (&)[22])
0x18006145e  jmp     short loc_1800614BD
0x180061460  mov     eax, cs:dword_18014B6A8
0x180061466  cmp     eax, 5
0x180061469  jbe     short loc_1800614BD
0x18006146b  lea     rcx, [rbp+2B0h+var_280]
0x18006146f  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180061474  mov     [rbp+2B0h+var_2C0], rax
0x180061478  mov     dword ptr [rsp+3B0h+var_350], ebx
0x18006147c  mov     [rsp+3B0h+var_348], 349h
0x180061484  mov     [rsp+3B0h+var_340], r14
0x180061489  lea     rax, [rbp+2B0h+var_2C0]
0x18006148d  mov     [rsp+3B0h+var_378], rax
0x180061492  lea     rax, [rsp+3B0h+var_350]
0x180061497  mov     [rsp+3B0h+var_380], rax
0x18006149c  lea     rax, [rsp+3B0h+var_348]
0x1800614a1  mov     qword ptr [rsp+3B0h+secondsRemaining], rax
0x1800614a6  lea     rax, [rsp+3B0h+var_340]
0x1800614ab  mov     qword ptr [rsp+3B0h+percentComplete], rax
  ... truncated ...
```
