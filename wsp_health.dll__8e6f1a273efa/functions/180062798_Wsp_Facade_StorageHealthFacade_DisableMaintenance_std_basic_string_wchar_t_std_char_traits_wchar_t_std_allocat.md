# Wsp::Facade::StorageHealthFacade::DisableMaintenance(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,std::unique_ptr<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,std::default_delete<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>>> const &,std::unique_ptr<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,std::default_delete<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>>> const &,mi::MiContext &,std::shared_ptr<Wsp::Facade::IExtendedStatus> &)

- ea: `0x180062798`
- end: `0x18006397f`
- name: `?DisableMaintenance@StorageHealthFacade@Facade@Wsp@@QEAA?AW4SM_RETURN_CODE@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV?$unique_ptr@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$default_delete@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@6@1AEAVMiContext@mi@@AEAV?$shared_ptr@UIExtendedStatus@Facade@Wsp@@@6@@Z`
- size: `4583`
- prototype: ``
- caller_count: `1`
- callee_count: `66`
- tags: `broker_com_uri`

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
- `0x18000c85c`
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
- `0x180053d6c`
- `0x180053d90`
- `0x180053db4`
- `0x180055020`
- `0x18005a184`
- `0x18005b57c`
- `0x18005b5e0`
- `0x18005b644`
- `0x18005b6a8`
- `0x18005b704`
- `0x18005b760`
- `0x18005b8e8`
- `0x18005b94c`
- `0x18005b9b0`
- `0x18005ba14`
- `0x18005d0cc`
- `0x18005f0f4`
- `0x18005f124`
- `0x18005fcbc`
- `0x18005fe14`
- `0x18005fe44`
- `0x1800601d0`
- `0x18006089c`

## string_xrefs

- `0x180062e5b`: `FindWriteCacheDisks`
- `0x18006327a`: `Waiting for SBL cache state`
- `0x1800631a5`: `Change SBL cache`

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
  int v15; // ecx
  int v16; // r8d
  int v17; // r9d
  char *v18; // rbx
  _QWORD *Instance; // rax
  int SubsystemType; // eax
  __int64 v21; // rcx
  MI_Uint32 FaultDomainPhysicalDisks; // edi
  int v23; // ecx
  int v24; // r8d
  int v25; // r9d
  struct cxl::TraceManager *v26; // rax
  _BYTE *v27; // rcx
  __int64 SmApiSession; // rax
  struct ProtectedPwd **v29; // rax
  signed int Cluster; // ebx
  int v31; // r8d
  int v32; // r9d
  struct cxl::TraceManager *v33; // rax
  int v34; // ecx
  int v35; // r8d
  int v36; // r9d
  struct cxl::TraceManager *v37; // rax
  int v38; // ecx
  int v39; // r8d
  int v40; // r9d
  __int64 v41; // rax
  std::_Ref_count_base *v42; // rcx
  __int64 v43; // rcx
  const MI_Char *v44; // rax
  const MI_Char *v45; // r8
  const MI_Char *v46; // r9
  int v47; // ecx
  int v48; // r8d
  int v49; // r9d
  struct cxl::TraceManager *v50; // rax
  const MI_Char *v51; // rax
  const MI_Char *v52; // r8
  const MI_Char *v53; // r9
  int v54; // ecx
  int v55; // r9d
  __int64 v56; // rcx
  int v57; // ecx
  int v58; // r8d
  int v59; // r9d
  struct cxl::TraceManager *v60; // rax
  __int64 v61; // rcx
  int v62; // ecx
  int v63; // r8d
  int v64; // r9d
  struct cxl::TraceManager *v65; // rax
  __int64 v66; // rcx
  int v67; // ecx
  int v68; // r8d
  int v69; // r9d
  struct cxl::TraceManager *v70; // rax
  int v71; // ecx
  int v72; // r8d
  int v73; // r9d
  struct cxl::TraceManager *v74; // rax
  const MI_Char *v75; // rax
  const MI_Char *v76; // r8
  const MI_Char *v77; // r9
  int v78; // ecx
  int v79; // ecx
  int v80; // r8d
  int v81; // r9d
  struct cxl::TraceManager *v82; // rax
  __int64 v83; // rcx
  int v84; // ecx
  int v85; // r8d
  int v86; // r9d
  struct cxl::TraceManager *v87; // rax
  int v88; // ecx
  int v89; // r8d
  int v90; // r9d
  struct cxl::TraceManager *v91; // rax
  const MI_Char *v92; // rax
  const MI_Char *v93; // r8
  const MI_Char *v94; // r9
  int v95; // ecx
  int v96; // r8d
  int v97; // r9d
  struct cxl::TraceManager *v98; // rax
  int v99; // ecx
  int v100; // r8d
  int v101; // r9d
  const MI_Char *v102; // rax
  const MI_Char *v103; // r8
  const MI_Char *v104; // r9
  __int64 v105; // r14
  __int64 v106; // r15
  __int64 v107; // rax
  int v108; // ecx
  int v109; // r8d
  int v110; // r9d
  struct cxl::TextWriter *v111; // rbx
  __int64 v112; // rax
  __int64 value; // rax
  int v114; // ecx
  int v115; // r8d
  int v116; // r9d
  const MI_Char *v117; // rax
  const MI_Char *v118; // r8
  const MI_Char *v119; // r9
  int v120; // ecx
  int v121; // r8d
  int v122; // r9d
  __int64 v124; // rax
  __int64 v125; // rax
  MI_Uint32 secondsRemaining; // [rsp+28h] [rbp-D8h]
  __int64 *secondsRemaininga; // [rsp+28h] [rbp-D8h]
  __int64 v128; // [rsp+60h] [rbp-A0h] BYREF
  MI_Uint32 v129[2]; // [rsp+68h] [rbp-98h] BYREF
  const char *v130; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v131[4]; // [rsp+78h] [rbp-88h] BYREF
  MI_Uint32 v132; // [rsp+7Ch] [rbp-84h] BYREF
  char v133; // [rsp+80h] [rbp-80h] BYREF
  __int64 v134; // [rsp+88h] [rbp-78h] BYREF
  _QWORD *v135; // [rsp+90h] [rbp-70h] BYREF
  const char *v136; // [rsp+98h] [rbp-68h] BYREF
  const char **v137[2]; // [rsp+A0h] [rbp-60h] BYREF
  __int128 v138; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v139; // [rsp+C0h] [rbp-40h]
  __int64 v140; // [rsp+C8h] [rbp-38h] BYREF
  std::_Ref_count_base *v141[2]; // [rsp+D0h] [rbp-30h] BYREF
  _BYTE v142[16]; // [rsp+E0h] [rbp-20h] BYREF
  const char *v143; // [rsp+F0h] [rbp-10h] BYREF
  std::_Ref_count_base *v144; // [rsp+F8h] [rbp-8h]
  _BYTE v145[32]; // [rsp+110h] [rbp+10h] BYREF
  _BYTE v146[32]; // [rsp+130h] [rbp+30h] BYREF
  _BYTE v147[32]; // [rsp+150h] [rbp+50h] BYREF
  _OWORD v148[2]; // [rsp+170h] [rbp+70h] BYREF
  _OWORD v149[2]; // [rsp+190h] [rbp+90h] BYREF
  _BYTE v150[4]; // [rsp+1B0h] [rbp+B0h] BYREF
  int v151; // [rsp+1B4h] [rbp+B4h] BYREF
  _BYTE v152[80]; // [rsp+1B8h] [rbp+B8h] BYREF
  _BYTE v153[32]; // [rsp+208h] [rbp+108h] BYREF
  _BYTE v154[35]; // [rsp+228h] [rbp+128h] BYREF
  char v155; // [rsp+24Bh] [rbp+14Bh] BYREF
  int v156; // [rsp+24Ch] [rbp+14Ch]
  _BYTE v157[16]; // [rsp+250h] [rbp+150h] BYREF
  _BYTE v158[64]; // [rsp+260h] [rbp+160h] BYREF
  _BYTE v159[8]; // [rsp+2A0h] [rbp+1A0h] BYREF
  _BYTE v160[32]; // [rsp+2A8h] [rbp+1A8h] BYREF
  _BYTE v161[8]; // [rsp+2C8h] [rbp+1C8h] BYREF
  _BYTE v162[32]; // [rsp+2D0h] [rbp+1D0h] BYREF
  _BYTE pExceptionObject[112]; // [rsp+2F0h] [rbp+1F0h] BYREF

  v130 = a4;
  v135 = a3;
  v10 = a5;
  v136 = (const char *)a5;
  if ( (unsigned int)dword_18014D6A8 > 5 )
  {
    v132 = 782;
    v143 = "Wsp::Facade::StorageHealthFacade::DisableMaintenance";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      (unsigned int)"Wsp::Facade::StorageHealthFacade::DisableMaintenance",
      (unsigned int)&byte_18012D2BF,
      (_DWORD)a3,
      (_DWORD)a4,
      (__int64)&v143,
      (__int64)&v132);
  }
  v149[0] = 0;
  v149[1] = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v149[0]) = 0;
  v138 = 0;
  v139 = 0;
  std::map<std::wstring,mismpstorage::SPACES_PhysicalDisk>::map<std::wstring,mismpstorage::SPACES_PhysicalDisk>(v142);
  std::map<std::wstring,Wsp::Facade::MaintenanceDisk>::map<std::wstring,Wsp::Facade::MaintenanceDisk>(v137);
  Wsp::Facade::MaintenanceModeStruct::MaintenanceModeStruct((Wsp::Facade::MaintenanceModeStruct *)v150);
  *(_OWORD *)v141 = 0;
  v133 = 1;
  v131[0] = 0;
  cxl::load_string(v147, qword_1801599A0, 3002);
  if ( !(unsigned int)Wsp::Facade::StorageHealthFacade::GetSubsystemType(a1) )
  {
    v124 = std::wstring::wstring(v145, L"non highlyavailable subsystems are not supported");
    v125 = cxl::SMResult(&v136, 59001, v124);
    cxl::Error(pExceptionObject, v125);
    throw (cxl::Exception *)pExceptionObject;
  }
  v11 = (const MI_Char *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v147);
  MI_Context_WriteProgress(*a5, v11, v12, v13, 1u, secondsRemaining);
  v148[0] = 0;
  v148[1] = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v148[0]) = 0;
  v14 = cxl::StringWriter::StringWriter(v145, v148);
  cxl::TextWriter::Write<56>(v14);
  std::wstring::wstring(v146, v148);
  if ( (unsigned int)dword_18014D6A8 > 4 && (unsigned __int8)tlgKeywordOn(&dword_18014D6A8, 0x4000) )
  {
    v143 = (const char *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v146);
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>>(
      v15,
      (unsigned int)byte_18012D17B,
      v16,
      v17,
      (__int64)&v143);
  }
  v18 = (char *)cxl::TraceManager::Instance() + 120;
  cxl::CxlTraits<std::wstring>::WriteTo(v18, v146);
  cxl::TextWriter::operator<<<cxl::ENDL>(v18);
  std::wstring::_Tidy_deallocate(v146);
  if ( *a3 )
  {
    v154[33] = 1;
    std::wstring::operator=(v154);
  }
  if ( *(_QWORD *)a4 )
  {
    v154[32] = 1;
    std::wstring::operator=(v153);
  }
  Instance = (_QWORD *)Wsp::MiSpaceAdapter::GetInstance(&v143);
  Wsp::MiSpaceAdapter::UnpackObjectId(*Instance, (unsigned int)v145, a2, (unsigned int)&v151, (__int64)v150);
  std::wstring::operator=(v149);
  std::wstring::_Tidy_deallocate(v145);
  if ( v144 )
    std::_Ref_count_base::_Decref(v144);
  SubsystemType = Wsp::Facade::StorageHealthFacade::GetSubsystemType(a1);
  if ( SubsystemType != v151 )
  {
    FaultDomainPhysicalDisks = 1;
    std::wstring::wstring(v145, L"Subsystem not supported");
    if ( (unsigned int)dword_18014D6A8 > 2 )
    {
      v143 = (const char *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v145);
      v132 = 1;
      v129[0] = 831;
      v130 = "Wsp::Facade::StorageHealthFacade::DisableMaintenance";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>>(
        v23,
        (unsigned int)byte_18012D19B,
        v24,
        v25,
        (__int64)&v130,
        (__int64)v129,
        (__int64)&v132,
        (__int64)&v143);
    }
    v26 = cxl::TraceManager::Instance();
    v129[0] = 1;
    v132 = 831;
    cxl::TextWriter::WriteLine<wchar_t,char [53],int,int,wchar_t [24]>(
      (struct cxl::TraceManager *)((char *)v26 + 40),
      (__int64)v129);
LABEL_17:
    v27 = v145;
LABEL_18:
    std::wstring::_Tidy_deallocate(v27);
    goto LABEL_88;
  }
  SmApiSession = Wsp::Facade::StorageHealthFacade::GetSmApiSession(v21, &v143);
  std::shared_ptr<mismpstorage::SPACES_VirtualDisk const>::operator=(v152, SmApiSession);
  if ( v144 )
    std::_Ref_count_base::_Decref(v144);
  v29 = (struct ProtectedPwd **)ClusWmi::DataStore::GetInstance(&v143);
  Cluster = ClusWmi::DataStore::GetCluster(*v29);
  if ( v144 )
    std::_Ref_count_base::_Decref(v144);
  if ( Cluster < 0 )
  {
    v132 = Cluster;
    if ( (unsigned int)dword_18014D6A8 > 2 )
    {
      v129[0] = v132;
      LODWORD(v128) = 840;
      v143 = "Wsp::Facade::StorageHealthFacade::DisableMaintenance";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        dword_18014D6A8,
        (unsigned int)word_18012D1DA,
        v31,
        v32,
        (__int64)&v143,
        (__int64)&v128,
        (__int64)v129);
    }
    v33 = cxl::TraceManager::Instance();
    LODWORD(v128) = 840;
    cxl::TextWriter::WriteLine<wchar_t,char [53],int,long>(
      (struct cxl::TraceManager *)((char *)v33 + 40),
      (__int64)&v132);
    FaultDomainPhysicalDisks = Wsp::MiSpaceAdapter::SmRCFromHResult((unsigned int)Cluster);
    std::wstring::wstring(v146, L"Failed to Get Cluster");
    if ( FaultDomainPhysicalDisks )
    {
      if ( (unsigned int)dword_18014D6A8 > 2 )
      {
        v143 = (const char *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v146);
        LODWORD(v128) = FaultDomainPhysicalDisks;
        v129[0] = 841;
        v130 = "Wsp::Facade::StorageHealthFacade::DisableMaintenance";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>>(
          v34,
          (unsigned int)&dword_18012D0BC,
          v35,
          v36,
          (__int64)&v130,
          (__int64)v129,
          (__int64)&v128,
          (__int64)&v143);
      }
      v37 = cxl::TraceManager::Instance();
      LODWORD(v128) = FaultDomainPhysicalDisks;
      v129[0] = 841;
      cxl::TextWriter::WriteLine<wchar_t,char [53],int,int,wchar_t [22]>(
        (struct cxl::TraceManager *)((char *)v37 + 40),
        (__int64)&v128);
    }
    else if ( (unsigned int)dword_18014D6A8 > 5 )
    {
      v143 = (const char *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v146);
      LODWORD(v128) = 0;
      v129[0] = 841;
      v130 = "Wsp::Facade::StorageHealthFacade::DisableMaintenance";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>>(
        v38,
        (unsigned int)byte_18012D0FB,
        v39,
        v40,
        (__int64)&v130,
        (__int64)v129,
        (__int64)&v128,
        (__int64)&v143);
    }
    v27 = v146;
    goto LABEL_18;
  }
  v41 = ClusApi::Facade::FacadeFactory::CreateClusterFacade(&v143, v141);
  std::shared_ptr<mismpstorage::SPACES_VirtualDisk const>::operator=(v157, v41);
  v42 = v144;
  if ( v144 )
    std::_Ref_count_base::_Decref(v144);
  Wsp::Facade::StorageHealthFacade::GetLocalNode(v42, v150);
  Wsp::Facade::StorageHealthFacade::S2DEnabled(v43, v150);
  v44 = (const MI_Char *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v147);
  MI_Context_WriteProgress(*a5, v44, v45, v46, 2u, (MI_Uint32)secondsRemaininga);
  LODWORD(secondsRemaininga) = a6;
  FaultDomainPhysicalDisks = Wsp::Facade::StorageHealthFacade::GetFaultDomainPhysicalDisks(
                               a1,
                               a2,
                               (unsigned int)v150,
                               (unsigned int)v137,
                               (__int64)v142);
  if ( FaultDomainPhysicalDisks )
  {
    std::wstring::wstring(v145, L"GetFaultDomainPhysicalDisks");
    if ( (unsigned int)dword_18014D6A8 > 2 )
    {
      v143 = (const char *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v145);
      LODWORD(v128) = FaultDomainPhysicalDisks;
      v129[0] = 864;
      v130 = "Wsp::Facade::StorageHealthFacade::DisableMaintenance";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>>(
        v47,
        (unsigned int)&dword_18012D13C,
        v48,
        v49,
        (__int64)&v130,
        (__int64)v129,
        (__int64)&v128,
        (__int64)&v143);
    }
    v50 = cxl::TraceManager::Instance();
    LODWORD(v128) = FaultDomainPhysicalDisks;
    v129[0] = 864;
    cxl::TextWriter::WriteLine<wchar_t,char [53],int,int,wchar_t [28]>(
      (struct cxl::TraceManager *)((char *)v50 + 40),
      (__int64)&v128,
      (__int64)L"GetFaultDomainPhysicalDisks");
    goto LABEL_17;
  }
  if ( v155 && v156 )
  {
    v51 = (const MI_Char *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v147);
    MI_Context_WriteProgress(*a5, v51, v52, v53, 3u, a6);
    FaultDomainPhysicalDisks = Wsp::Facade::StorageHealthFacade::FindWriteCacheDisks(v54, (__int64)v150, v137, v55);
    if ( FaultDomainPhysicalDisks )
    {
      std::wstring::wstring(v145, L"FindWriteCacheDisks");
      if ( (unsigned int)dword_18014D6A8 > 2 )
      {
        v143 = (const char *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v145);
        LODWORD(v128) = FaultDomainPhysicalDisks;
        v129[0] = 882;
        v130 = "Wsp::Facade::StorageHealthFacade::DisableMaintenance";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>>(
          v57,
          (unsigned int)&word_18012D03E,
          v58,
          v59,
          (__int64)&v130,
          (__int64)v129,
          (__int64)&v128,
          (__int64)&v143);
      }
      v60 = cxl::TraceManager::Instance();
      LODWORD(v128) = FaultDomainPhysicalDisks;
      v129[0] = 882;
      cxl::TextWriter::WriteLine<wchar_t,char [53],int,int,wchar_t [20]>(
        (struct cxl::TraceManager *)((char *)v60 + 40),
        (__int64)&v128);
      goto LABEL_17;
    }
    FaultDomainPhysicalDisks = Wsp::Facade::StorageHealthFacade::QueryBoundDevices(v56, v150, v137, &v138);
    if ( FaultDomainPhysicalDisks )
    {
      std::wstring::wstring(v145, L"QueryBoundDevices");
      if ( (unsigned int)dword_18014D6A8 > 2 )
      {
        v143 = (const char *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v145);
        LODWORD(v128) = FaultDomainPhysicalDisks;
        v129[0] = 892;
        v130 = "Wsp::Facade::StorageHealthFacade::DisableMaintenance";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>>(
          v62,
          (unsigned int)byte_18012D07D,
          v63,
          v64,
          (__int64)&v130,
          (__int64)v129,
          (__int64)&v128,
          (__int64)&v143);
      }
      v65 = cxl::TraceManager::Instance();
      LODWORD(v128) = FaultDomainPhysicalDisks;
      v129[0] = 892;
      cxl::TextWriter::WriteLine<wchar_t,char [53],int,int,wchar_t [18]>(
        (struct cxl::TraceManager *)((char *)v65 + 40),
        (__int64)&v128);
      goto LABEL_17;
    }
    LODWORD(v128) = 5;
    FaultDomainPhysicalDisks = Wsp::Facade::StorageHealthFacade::SetMaintenanceModeIntent(v61, v137, &v128);
    if ( FaultDomainPhysicalDisks )
    {
      std::wstring::wstring(v145, L"Set stopping maintenance mode intent on physical disks");
      if ( (unsigned int)dword_18014D6A8 > 2 )
      {
        v143 = (const char *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v145);
        LODWORD(v128) = FaultDomainPhysicalDisks;
        v129[0] = 900;
        v130 = "Wsp::Facade::StorageHealthFacade::DisableMaintenance";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>>(
          v67,
          (unsigned int)qword_18012CFC0,
          v68,
          v69,
          (__int64)&v130,
          (__int64)v129,
          (__int64)&v128,
          (__int64)&v143);
      }
      v70 = cxl::TraceManager::Instance();
      LODWORD(v128) = FaultDomainPhysicalDisks;
      v129[0] = 900;
      cxl::TextWriter::WriteLine<wchar_t,char [53],int,int,wchar_t [55]>(
        (struct cxl::TraceManager *)((char *)v70 + 40),
        (__int64)&v128);
      goto LABEL_17;
    }
    LODWORD(v128) = 4;
    FaultDomainPhysicalDisks = Wsp::Facade::StorageHealthFacade::ClearMaintenanceModeIntent(v66, v137, &v128);
    if ( FaultDomainPhysicalDisks )
    {
      std::wstring::wstring(v145, L"Clear starting maintenance mode intent on physical disks");
      if ( (unsigned int)dword_18014D6A8 > 2 )
      {
        v143 = (const char *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v145);
        LODWORD(v128) = FaultDomainPhysicalDisks;
        v129[0] = 907;
        v130 = "Wsp::Facade::StorageHealthFacade::DisableMaintenance";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>>(
          v71,
          (unsigned int)&byte_18012CFFF,
          v72,
          v73,
          (__int64)&v130,
          (__int64)v129,
          (__int64)&v128,
          (__int64)&v143);
      }
      v74 = cxl::TraceManager::Instance();
      LODWORD(v128) = FaultDomainPhysicalDisks;
      v129[0] = 907;
      cxl::TextWriter::WriteLine<wchar_t,char [53],int,int,wchar_t [57]>(
        (struct cxl::TraceManager *)((char *)v74 + 40),
        (__int64)&v128);
      goto LABEL_17;
    }
    v75 = (const MI_Char *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v147);
    MI_Context_WriteProgress(*a5, v75, v76, v77, 4u, (MI_Uint32)secondsRemaininga);
    FaultDomainPhysicalDisks = Wsp::Facade::StorageHealthFacade::ChangeWriteCache(
                                 v78,
                                 (unsigned int)&v133,
                                 (unsigned int)v150,
                                 (unsigned int)v137,
                                 a6);
    if ( FaultDomainPhysicalDisks )
    {
      std::wstring::wstring(v145, L"Change SBL cache");
      if ( (unsigned int)dword_18014D6A8 > 2 )
      {
        v143 = (const char *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v145);
        LODWORD(v128) = FaultDomainPhysicalDisks;
        v129[0] = 927;
        v130 = "Wsp::Facade::StorageHealthFacade::DisableMaintenance";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>>(
          v79,
          (unsigned int)word_18012CF42,
          v80,
          v81,
          (__int64)&v130,
          (__int64)v129,
          (__int64)&v128,
          (__int64)&v143);
      }
      v82 = cxl::TraceManager::Instance();
      LODWORD(v128) = FaultDomainPhysicalDisks;
      v129[0] = 927;
      cxl::TextWriter::WriteLine<wchar_t,char [53],int,int,wchar_t [17]>(
        (struct cxl::TraceManager *)((char *)v82 + 40),
        (__int64)&v128);
      goto LABEL_17;
    }
    FaultDomainPhysicalDisks = Wsp::Facade::StorageHealthFacade::GetDiskCacheState(
                                 a1,
                                 (__int64)v150,
                                 (__int64)v137,
                                 1,
                                 (__int64)a5,
                                 a6);
    if ( FaultDomainPhysicalDisks )
    {
      std::wstring::wstring(v145, L"Waiting for SBL cache state");
      if ( (unsigned int)dword_18014D6A8 > 2 )
      {
        v143 = (const char *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v145);
        LODWORD(v128) = FaultDomainPhysicalDisks;
        v129[0] = 940;
        v130 = "Wsp::Facade::StorageHealthFacade::DisableMaintenance";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>>(
          v84,
          (unsigned int)byte_18012CF81,
          v85,
          v86,
          (__int64)&v130,
          (__int64)v129,
          (__int64)&v128,
          (__int64)&v143);
      }
      v87 = cxl::TraceManager::Instance();
      LODWORD(v128) = FaultDomainPhysicalDisks;
      v129[0] = 940;
      cxl::TextWriter::WriteLine<wchar_t,char [53],int,int,wchar_t [28]>(
        (struct cxl::TraceManager *)((char *)v87 + 40),
        (__int64)&v128,
        (__int64)L"Waiting for SBL cache state");
      goto LABEL_17;
    }
    LODWORD(v128) = 5;
    FaultDomainPhysicalDisks = Wsp::Facade::StorageHealthFacade::ClearMaintenanceModeIntent(v83, v137, &v128);
    if ( FaultDomainPhysicalDisks )
    {
      std::wstring::wstring(v145, L"Set stopping maintenance mode intent on physical disks");
      if ( (unsigned int)dword_18014D6A8 > 2 )
      {
        v143 = (const char *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v145);
        LODWORD(v128) = FaultDomainPhysicalDisks;
        v129[0] = 947;
        v130 = "Wsp::Facade::StorageHealthFacade::DisableMaintenance";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>>(
          v88,
          (unsigned int)byte_18012CE83,
          v89,
          v90,
          (__int64)&v130,
          (__int64)v129,
          (__int64)&v128,
          (__int64)&v143);
      }
      v91 = cxl::TraceManager::Instance();
      LODWORD(v128) = FaultDomainPhysicalDisks;
      v129[0] = 947;
      cxl::TextWriter::WriteLine<wchar_t,char [53],int,int,wchar_t [55]>(
        (struct cxl::TraceManager *)((char *)v91 + 40),
        (__int64)&v128);
      goto LABEL_17;
    }
  }
  v92 = (const MI_Char *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v147);
  MI_Context_WriteProgress(*a5, v92, v93, v94, 0x5Bu, (MI_Uint32)secondsRemaininga);
  std::shared_ptr<ClusApi::IStorage>::shared_ptr<ClusApi::IStorage>(&v143, v152);
  *(_QWORD *)v129 = 0;
  v128 = 0;
  v134 = 0;
  secondsRemaininga = &v128;
  FaultDomainPhysicalDisks = Wsp::Facade::StorageHealthFacade::CallMaintenanceOnTargetObject(
                               &v155,
                               v158,
                               v150,
                               v131,
                               &v134);
  std::unique_ptr<bool>::~unique_ptr<bool>(&v134);
  std::unique_ptr<bool>::~unique_ptr<bool>(&v128);
  std::unique_ptr<unsigned int>::~unique_ptr<unsigned int>(v129);
  std::wstring::wstring(v146, a2);
  if ( FaultDomainPhysicalDisks )
  {
    if ( (unsigned int)dword_18014D6A8 > 2 )
    {
      v143 = (const char *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v146);
      LODWORD(v128) = FaultDomainPhysicalDisks;
      v129[0] = 974;
      v130 = "Wsp::Facade::StorageHealthFacade::DisableMaintenance";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>>(
        v95,
        (unsigned int)word_18012CEC2,
        v96,
        v97,
        (__int64)&v130,
        (__int64)v129,
        (__int64)&v128,
        (__int64)&v143);
    }
    v98 = cxl::TraceManager::Instance();
    LODWORD(v128) = FaultDomainPhysicalDisks;
    v129[0] = 974;
    cxl::TextWriter::WriteLine<wchar_t,char [53],int,int,std::wstring>(
      (struct cxl::TraceManager *)((char *)v98 + 40),
      (__int64)&v128,
      a2);
  }
  else if ( (unsigned int)dword_18014D6A8 > 5 )
  {
    v143 = (const char *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v146);
    LODWORD(v128) = 0;
    v129[0] = 974;
    v130 = "Wsp::Facade::StorageHealthFacade::DisableMaintenance";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>>(
      v99,
      (unsigned int)byte_18012CF01,
      v100,
      v101,
      (__int64)&v130,
      (__int64)v129,
      (__int64)&v128,
      (__int64)&v143);
  }
  std::wstring::_Tidy_deallocate(v146);
  if ( !FaultDomainPhysicalDisks )
  {
    v102 = (const MI_Char *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v147);
    MI_Context_WriteProgress(*a5, v102, v103, v104, 0x5Cu, (MI_Uint32)secondsRemaininga);
    if ( v155 )
    {
      if ( v156 )
      {
        v106 = *((_QWORD *)&v138 + 1);
        v105 = v138;
        if ( (_QWORD)v138 != *((_QWORD *)&v138 + 1) )
        {
          do
          {
            std::shared_ptr<ClusApi::IStorage>::shared_ptr<ClusApi::IStorage>(v146, v152);
            v143 = 0;
            v130 = 0;
            v135 = 0;
            v140 = 0;
            *(_QWORD *)v129 = 0;
            LODWORD(v128) = 5;
            secondsRemaininga = &v140;
            FaultDomainPhysicalDisks = Wsp::Facade::StorageHealthFacade::CallMaintenanceOnTargetObject(
                                         &v155,
                                         v105,
                                         &v128,
                                         v131,
                                         v129);
            std::unique_ptr<bool>::~unique_ptr<bool>(v129);
            std::unique_ptr<bool>::~unique_ptr<bool>(&v140);
            std::unique_ptr<unsigned int>::~unique_ptr<unsigned int>(&v135);
            std::unique_ptr<std::wstring>::~unique_ptr<std::wstring>(&v130);
            std::unique_ptr<std::wstring>::~unique_ptr<std::wstring>(&v143);
            v107 = mismpstorage::SPACES_StoragePool::ObjectId(v105, v159);
            mismpstorage::read_property<std::wstring>::get_value(v107, v145);
            std::wstring::_Tidy_deallocate(v160);
            if ( FaultDomainPhysicalDisks )
            {
              if ( (unsigned int)dword_18014D6A8 > 2 )
              {
                v143 = (const char *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v145);
                LODWORD(v128) = FaultDomainPhysicalDisks;
                v129[0] = 1014;
                v130 = "Wsp::Facade::StorageHealthFacade::DisableMaintenance";
                _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>>(
                  v108,
                  (unsigned int)qword_18012CDA8,
                  v109,
                  v110,
                  (__int64)&v130,
                  (__int64)v129,
                  (__int64)&v128,
                  (__int64)&v143);
              }
              v111 = (struct cxl::TraceManager *)((char *)cxl::TraceManager::Instance() + 40);
              v112 = mismpstorage::SPACES_StoragePool::ObjectId(v105, v161);
              value = mismpstorage::read_property<std::wstring>::get_value(v112, &v143);
              v132 = FaultDomainPhysicalDisks;
              LODWORD(v134) = 1014;
              cxl::TextWriter::WriteLine<wchar_t,char [53],int,int,std::wstring>(v111, (__int64)&v132, value);
              std::wstring::_Tidy_deallocate(&v143);
              std::wstring::_Tidy_deallocate(v162);
            }
            else if ( (unsigned int)dword_18014D6A8 > 5 )
            {
              v143 = (const char *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v145);
              LODWORD(v128) = 0;
              v129[0] = 1014;
              v130 = "Wsp::Facade::StorageHealthFacade::DisableMaintenance";
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>>(
                v114,
                (unsigned int)&byte_18012CDE7,
                v115,
                v116,
                (__int64)&v130,
                (__int64)v129,
                (__int64)&v128,
                (__int64)&v143);
            }
            std::wstring::_Tidy_deallocate(v145);
            if ( FaultDomainPhysicalDisks )
              break;
            v105 += 64;
          }
          while ( v105 != v106 );
          v10 = (MI_Context **)v136;
        }
      }
    }
  }
LABEL_88:
  v117 = (const MI_Char *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v147);
  MI_Context_WriteProgress(*v10, v117, v118, v119, 0x64u, (MI_Uint32)secondsRemaininga);
  if ( (unsigned int)dword_18014D6A8 > 5 )
  {
    LODWORD(v134) = 1034;
    v136 = "Wsp::Facade::StorageHealthFacade::DisableMaintenance";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      v120,
      (unsigned int)qword_18012CE28,
      v121,
      v122,
      (__int64)&v136,
      (__int64)&v134);
  }
  std::wstring::_Tidy_deallocate(v148);
  std::wstring::_Tidy_deallocate(v147);
  if ( v141[1] )
    std::_Ref_count_base::_Decref(v141[1]);
  Wsp::Facade::MaintenanceModeStruct::~MaintenanceModeStruct((Wsp::Facade::MaintenanceModeStruct *)v150);
  std::_Tree<std::_Tmap_traits<std::wstring,Wsp::Facade::MaintenanceDisk,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,Wsp::Facade::MaintenanceDisk>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,Wsp::Facade::MaintenanceDisk,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,Wsp::Facade::MaintenanceDisk>>,0>>(v137);
  std::_Tree<std::_Tmap_traits<std::wstring,mismpstorage::SPACES_VirtualDisk,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,mismpstorage::SPACES_VirtualDisk>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,mismpstorage::SPACES_VirtualDisk,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,mismpstorage::SPACES_VirtualDisk>>,0>>(v142);
  if ( (_QWORD)v138 )
  {
    std::_Destroy_range<std::allocator<mismpstorage::SPACES_PhysicalDisk>>(v138, *((_QWORD *)&v138 + 1));
    std::_Deallocate<16>(v138, (v139 - v138) & 0xFFFFFFFFFFFFFFC0uLL);
    v138 = 0;
    v139 = 0;
  }
  std::wstring::_Tidy_deallocate(v149);
  return FaultDomainPhysicalDisks;
}

```

## disassembly

```asm
0x180062798  push    rbp
0x18006279a  push    rbx
0x18006279b  push    rsi
0x18006279c  push    rdi
0x18006279d  push    r12
0x18006279f  push    r13
0x1800627a1  push    r14
0x1800627a3  push    r15
0x1800627a5  lea     rbp, [rsp-278h]
0x1800627ad  sub     rsp, 378h
0x1800627b4  mov     rax, cs:__security_cookie
0x1800627bb  xor     rax, rsp
0x1800627be  mov     [rbp+2B0h+var_50], rax
0x1800627c5  mov     rdi, r9
0x1800627c8  mov     [rsp+3B0h+var_340], r9
0x1800627cd  mov     rsi, r8
0x1800627d0  mov     [rbp+2B0h+var_320], r8
0x1800627d4  mov     r15, rdx
0x1800627d7  mov     r14, rcx
0x1800627da  mov     r12, [rbp+2B0h+arg_20]
0x1800627e1  mov     [rbp+2B0h+var_318], r12
0x1800627e5  mov     r13, qword ptr [rbp+2B0h+arg_28]
0x1800627ec  mov     eax, cs:dword_18014D6A8
0x1800627f2  lea     rcx, aWspFacadeStora_26; "Wsp::Facade::StorageHealthFacade::Disab"...
0x1800627f9  cmp     eax, 5
0x1800627fc  jbe     short loc_180062829
0x1800627fe  mov     [rsp+3B0h+var_334], 30Eh
0x180062806  mov     [rbp+2B0h+var_2C0], rcx
0x18006280a  lea     rax, [rsp+3B0h+var_334]
0x18006280f  mov     qword ptr [rsp+3B0h+secondsRemaining], rax; secondsRemaining
0x180062814  lea     rax, [rbp+2B0h+var_2C0]
0x180062818  mov     qword ptr [rsp+3B0h+percentComplete], rax
0x18006281d  lea     rdx, byte_18012D2BF
0x180062824  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x180062829  xorps   xmm0, xmm0
0x18006282c  movups  [rbp+2B0h+var_220], xmm0
0x180062833  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x18006283b  movdqu  [rbp+2B0h+var_210], xmm1
0x180062843  xor     eax, eax
0x180062845  mov     word ptr [rbp+2B0h+var_220], ax
0x18006284c  movdqu  [rbp+2B0h+var_300], xmm0
0x180062851  mov     [rbp+2B0h+var_2F0], rax
0x180062855  lea     rcx, [rbp+2B0h+var_2D0]
0x180062859  call    ??0?$map@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@VSPACES_PhysicalDisk@mismpstorage@@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@VSPACES_PhysicalDisk@mismpstorage@@@std@@@2@@std@@QEAA@XZ; std::map<std::wstring,mismpstorage::SPACES_PhysicalDisk>::map<std::wstring,mismpstorage::SPACES_PhysicalDisk>(void)
0x18006285e  nop
0x18006285f  lea     rcx, [rbp+2B0h+var_310]
0x180062863  call    ??0?$map@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UMaintenanceDisk@Facade@Wsp@@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UMaintenanceDisk@Facade@Wsp@@@std@@@2@@std@@QEAA@XZ; std::map<std::wstring,Wsp::Facade::MaintenanceDisk>::map<std::wstring,Wsp::Facade::MaintenanceDisk>(void)
0x180062868  nop
0x180062869  lea     rcx, [rbp+2B0h+var_200]; this
0x180062870  call    ??0MaintenanceModeStruct@Facade@Wsp@@QEAA@XZ; Wsp::Facade::MaintenanceModeStruct::MaintenanceModeStruct(void)
0x180062875  nop
0x180062876  xorps   xmm1, xmm1
0x180062879  movdqu  xmmword ptr [rbp+2B0h+var_2E0], xmm1
0x18006287e  mov     [rbp+2B0h+var_330], 1
0x180062882  mov     [rsp+3B0h+var_338], 0
0x180062887  mov     r8d, 0BBAh
0x18006288d  mov     rdx, cs:qword_1801599A0
0x180062894  lea     rcx, [rbp+2B0h+var_260]
0x180062898  call    ?load_string@cxl@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEAUHINSTANCE__@@I@Z; cxl::load_string(HINSTANCE__ *,uint)
0x18006289d  nop
0x18006289e  mov     rcx, r14
0x1800628a1  call    ?GetSubsystemType@StorageHealthFacade@Facade@Wsp@@QEBA?BW4WSP_SUBSYSTEM_TYPE@@XZ; Wsp::Facade::StorageHealthFacade::GetSubsystemType(void)
0x1800628a6  test    eax, eax
0x1800628a8  jz      loc_18006393B
0x1800628ae  lea     rcx, [rbp+2B0h+var_260]
0x1800628b2  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x1800628b7  mov     rdx, rax; activity
0x1800628ba  mov     [rsp+3B0h+percentComplete], 1; percentComplete
0x1800628c2  mov     rcx, [r12]; context
0x1800628c6  call    MI_Context_WriteProgress
0x1800628cb  xorps   xmm0, xmm0
0x1800628ce  movups  [rbp+2B0h+var_240], xmm0
0x1800628d2  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x1800628da  movdqu  [rbp+2B0h+var_230], xmm1
0x1800628e2  xor     eax, eax
0x1800628e4  mov     word ptr [rbp+2B0h+var_240], ax
0x1800628e8  lea     rdx, [rbp+2B0h+var_240]
0x1800628ec  lea     rcx, [rbp+2B0h+var_2A0]
0x1800628f0  call    ??0StringWriter@cxl@@QEAA@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::StringWriter::StringWriter(std::wstring &)
0x1800628f5  nop
0x1800628f6  mov     rcx, rax
0x1800628f9  call    ??$Write@$0DI@@TextWriter@cxl@@QEAAAEAV01@AEAY0DI@$$CB_W@Z; cxl::TextWriter::Write<56>(wchar_t const (&)[56])
0x1800628fe  nop
0x1800628ff  lea     rdx, [rbp+2B0h+var_240]
0x180062903  lea     rcx, [rbp+2B0h+var_280]
0x180062907  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18006290c  nop
0x18006290d  mov     eax, cs:dword_18014D6A8
0x180062913  cmp     eax, 4
0x180062916  jbe     short loc_18006294F
0x180062918  mov     edx, 4000h
0x18006291d  lea     rcx, dword_18014D6A8
0x180062924  call    _tlgKeywordOn
0x180062929  test    al, al
0x18006292b  jz      short loc_18006294F
0x18006292d  lea     rcx, [rbp+2B0h+var_280]
0x180062931  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180062936  mov     [rbp+2B0h+var_2C0], rax
0x18006293a  lea     rax, [rbp+2B0h+var_2C0]
0x18006293e  mov     qword ptr [rsp+3B0h+percentComplete], rax
0x180062943  lea     rdx, byte_18012D17B
0x18006294a  call    ??$Write@U?$_tlgWrapSz@_W@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@_W@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<wchar_t> const &)
0x18006294f  call    ?Instance@TraceManager@cxl@@SAAEAV12@XZ; cxl::TraceManager::Instance(void)
0x180062954  lea     rbx, [rax+78h]
0x180062958  lea     rdx, [rbp+2B0h+var_280]
0x18006295c  mov     rcx, rbx
0x18006295f  call    ?WriteTo@?$CxlTraits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@cxl@@SAXAEAVTextWriter@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBUFormat@2@@Z; cxl::CxlTraits<std::wstring>::WriteTo(cxl::TextWriter &,std::wstring const &,cxl::Format const &)
0x180062964  mov     rcx, rbx
0x180062967  call    ??$?6UENDL@cxl@@@TextWriter@cxl@@QEAAAEAV01@AEBUENDL@1@@Z; cxl::TextWriter::operator<<<cxl::ENDL>(cxl::ENDL const &)
0x18006296c  nop
0x18006296d  lea     rcx, [rbp+2B0h+var_280]
0x180062971  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180062976  mov     rdx, [rsi]
0x180062979  xor     ebx, ebx
0x18006297b  test    rdx, rdx
0x18006297e  jz      short loc_180062993
0x180062980  mov     [rbp+2B0h+var_167], 1
0x180062987  lea     rcx, [rbp+2B0h+var_188]
0x18006298e  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x180062993  mov     rdx, [rdi]
0x180062996  test    rdx, rdx
0x180062999  jz      short loc_1800629AE
0x18006299b  mov     [rbp+2B0h+var_168], 1
0x1800629a2  lea     rcx, [rbp+2B0h+var_1A8]
0x1800629a9  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x1800629ae  lea     rcx, [rbp+2B0h+var_2C0]
0x1800629b2  call    ?GetInstance@MiSpaceAdapter@Wsp@@SA?AV?$shared_ptr@VMiSpaceAdapter@Wsp@@@std@@XZ; Wsp::MiSpaceAdapter::GetInstance(void)
0x1800629b7  nop
0x1800629b8  lea     rcx, [rbp+2B0h+var_200]
0x1800629bf  mov     qword ptr [rsp+3B0h+percentComplete], rcx
0x1800629c4  lea     r9, [rbp+2B0h+var_1FC]
0x1800629cb  mov     r8, r15
0x1800629ce  lea     rdx, [rbp+2B0h+var_2A0]
0x1800629d2  mov     rcx, [rax]
0x1800629d5  call    ?UnpackObjectId@MiSpaceAdapter@Wsp@@QEBA?BV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV34@PEAW4WSP_SUBSYSTEM_TYPE@@PEAW4WSP_OBJECT_TYPE@@@Z; Wsp::MiSpaceAdapter::UnpackObjectId(std::wstring const &,WSP_SUBSYSTEM_TYPE *,WSP_OBJECT_TYPE *)
0x1800629da  nop
0x1800629db  mov     rdx, rax
0x1800629de  lea     rcx, [rbp+2B0h+var_220]
0x1800629e5  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x1800629ea  nop
0x1800629eb  lea     rcx, [rbp+2B0h+var_2A0]
0x1800629ef  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800629f4  nop
0x1800629f5  mov     rcx, [rbp+2B0h+var_2B8]; this
0x1800629f9  test    rcx, rcx
0x1800629fc  jz      short loc_180062A03
0x1800629fe  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180062a03  mov     rcx, r14
0x180062a06  call    ?GetSubsystemType@StorageHealthFacade@Facade@Wsp@@QEBA?BW4WSP_SUBSYSTEM_TYPE@@XZ; Wsp::Facade::StorageHealthFacade::GetSubsystemType(void)
0x180062a0b  cmp     eax, [rbp+2B0h+var_1FC]
0x180062a11  jz      loc_180062ADA
0x180062a17  mov     edi, 1
0x180062a1c  lea     rdx, aSubsystemNotSu; "Subsystem not supported"
0x180062a23  lea     rcx, [rbp+2B0h+var_2A0]
0x180062a27  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x180062a2c  nop
0x180062a2d  mov     eax, cs:dword_18014D6A8
0x180062a33  lea     esi, [rdi+1]
0x180062a36  mov     r15d, 33Fh
0x180062a3c  cmp     eax, esi
0x180062a3e  jbe     short loc_180062A97
0x180062a40  lea     rcx, [rbp+2B0h+var_2A0]
0x180062a44  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180062a49  mov     [rbp+2B0h+var_2C0], rax
0x180062a4d  mov     [rsp+3B0h+var_334], edi
0x180062a51  mov     [rsp+3B0h+var_348], r15d
0x180062a56  lea     r14, aWspFacadeStora_26; "Wsp::Facade::StorageHealthFacade::Disab"...
0x180062a5d  mov     [rsp+3B0h+var_340], r14
0x180062a62  lea     rax, [rbp+2B0h+var_2C0]
0x180062a66  mov     [rsp+3B0h+var_378], rax
0x180062a6b  lea     rax, [rsp+3B0h+var_334]
0x180062a70  mov     [rsp+3B0h+var_380], rax
0x180062a75  lea     rax, [rsp+3B0h+var_348]
0x180062a7a  mov     qword ptr [rsp+3B0h+secondsRemaining], rax
0x180062a7f  lea     rax, [rsp+3B0h+var_340]
0x180062a84  mov     qword ptr [rsp+3B0h+percentComplete], rax
0x180062a89  lea     rdx, byte_18012D19B
0x180062a90  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@U?$_tlgWrapSz@_W@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4AEBU?$_tlgWrapSz@_W@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<wchar_t> const &)
0x180062a95  jmp     short loc_180062A9E
0x180062a97  lea     r14, aWspFacadeStora_26; "Wsp::Facade::StorageHealthFacade::Disab"...
0x180062a9e  call    ?Instance@TraceManager@cxl@@SAAEAV12@XZ; cxl::TraceManager::Instance(void)
0x180062aa3  lea     rcx, [rax+28h]; struct cxl::TextWriter *
0x180062aa7  mov     [rsp+3B0h+var_348], 1
0x180062aaf  mov     [rsp+3B0h+var_334], r15d
0x180062ab4  lea     rax, [rsp+3B0h+var_348]
0x180062ab9  mov     qword ptr [rsp+3B0h+percentComplete], rax; __int64
0x180062abe  lea     r9, [rsp+3B0h+var_334]
0x180062ac3  mov     r8, r14
0x180062ac6  call    ??$WriteLine@_W$$BY0DF@DHH$$BY0BI@_W@TextWriter@cxl@@QEAAXPEB_WAEAY0DF@$$CBDAEBH2AEAY0BI@$$CB_W@Z; cxl::TextWriter::WriteLine<wchar_t,char [53],int,int,wchar_t [24]>(wchar_t const *,char const (&)[53],int const &,int const &,wchar_t const (&)[24])
0x180062acb  nop
0x180062acc  lea     rcx, [rbp+2B0h+var_2A0]
0x180062ad0  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180062ad5  jmp     loc_180063841
0x180062ada  lea     rdx, [rbp+2B0h+var_2C0]
0x180062ade  call    ?GetSmApiSession@StorageHealthFacade@Facade@Wsp@@AEAA?AV?$shared_ptr@VMiSession@mi@@@std@@XZ; Wsp::Facade::StorageHealthFacade::GetSmApiSession(void)
0x180062ae3  mov     rdx, rax
0x180062ae6  lea     rcx, [rbp+2B0h+var_1F8]
0x180062aed  call    ??4?$shared_ptr@$$CBVSPACES_VirtualDisk@mismpstorage@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<mismpstorage::SPACES_VirtualDisk const>::operator=(std::shared_ptr<mismpstorage::SPACES_VirtualDisk const> &&)
0x180062af2  mov     rcx, [rbp+2B0h+var_2B8]; this
0x180062af6  test    rcx, rcx
0x180062af9  jz      short loc_180062B00
0x180062afb  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180062b00  lea     rcx, [rbp+2B0h+var_2C0]
0x180062b04  call    ?GetInstance@DataStore@ClusWmi@@SA?AV?$shared_ptr@VDataStore@ClusWmi@@@std@@XZ; ClusWmi::DataStore::GetInstance(void)
0x180062b09  nop
0x180062b0a  lea     rdx, [rbp+2B0h+var_2E0]
0x180062b0e  mov     rcx, [rax]; struct ProtectedPwd *
0x180062b11  call    ?GetCluster@DataStore@ClusWmi@@QEAAJPEAV?$shared_ptr@UICluster@ClusApi@@@std@@@Z; ClusWmi::DataStore::GetCluster(std::shared_ptr<ClusApi::ICluster> *)
0x180062b16  mov     ebx, eax
0x180062b18  mov     rcx, [rbp+2B0h+var_2B8]; this
0x180062b1c  test    rcx, rcx
0x180062b1f  jz      short loc_180062B26
0x180062b21  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180062b26  test    ebx, ebx
0x180062b28  jns     loc_180062CC6
0x180062b2e  mov     [rsp+3B0h+var_334], ebx
0x180062b32  mov     ecx, cs:dword_18014D6A8
0x180062b38  mov     edi, 348h
0x180062b3d  mov     esi, 2
0x180062b42  cmp     ecx, esi
0x180062b44  jbe     short loc_180062B88
0x180062b46  mov     eax, [rsp+3B0h+var_334]
0x180062b4a  mov     [rsp+3B0h+var_348], eax
0x180062b4e  mov     dword ptr [rsp+3B0h+var_350], edi
0x180062b52  lea     r14, aWspFacadeStora_26; "Wsp::Facade::StorageHealthFacade::Disab"...
0x180062b59  mov     [rbp+2B0h+var_2C0], r14
0x180062b5d  lea     rax, [rsp+3B0h+var_348]
0x180062b62  mov     [rsp+3B0h+var_380], rax
0x180062b67  lea     rax, [rsp+3B0h+var_350]
0x180062b6c  mov     qword ptr [rsp+3B0h+secondsRemaining], rax
0x180062b71  lea     rax, [rbp+2B0h+var_2C0]
0x180062b75  mov     qword ptr [rsp+3B0h+percentComplete], rax
0x180062b7a  lea     rdx, word_18012D1DA
0x180062b81  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180062b86  jmp     short loc_180062B8F
0x180062b88  lea     r14, aWspFacadeStora_26; "Wsp::Facade::StorageHealthFacade::Disab"...
0x180062b8f  call    ?Instance@TraceManager@cxl@@SAAEAV12@XZ; cxl::TraceManager::Instance(void)
0x180062b94  lea     rcx, [rax+28h]; struct cxl::TextWriter *
0x180062b98  mov     dword ptr [rsp+3B0h+var_350], edi
0x180062b9c  lea     rax, [rsp+3B0h+var_334]
0x180062ba1  mov     qword ptr [rsp+3B0h+percentComplete], rax; __int64
0x180062ba6  lea     r9, [rsp+3B0h+var_350]
0x180062bab  mov     r8, r14
0x180062bae  call    ??$WriteLine@_W$$BY0DF@DHJ@TextWriter@cxl@@QEAAXPEB_WAEAY0DF@$$CBDAEBHAEBJ@Z; cxl::TextWriter::WriteLine<wchar_t,char [53],int,long>(wchar_t const *,char const (&)[53],int const &,long const &)
0x180062bb3  mov     ecx, ebx
0x180062bb5  call    ?SmRCFromHResult@MiSpaceAdapter@Wsp@@SA?AW4SM_RETURN_CODE@@J@Z; Wsp::MiSpaceAdapter::SmRCFromHResult(long)
0x180062bba  mov     edi, eax
0x180062bbc  lea     rdx, aFailedToGetClu; "Failed to Get Cluster"
0x180062bc3  lea     rcx, [rbp+2B0h+var_280]
0x180062bc7  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x180062bcc  nop
0x180062bcd  xor     ebx, ebx
0x180062bcf  test    edi, edi
0x180062bd1  jz      loc_180062C60
0x180062bd7  mov     ecx, cs:dword_18014D6A8
0x180062bdd  cmp     ecx, esi
0x180062bdf  jbe     short loc_180062C32
0x180062be1  lea     rcx, [rbp+2B0h+var_280]
0x180062be5  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180062bea  mov     [rbp+2B0h+var_2C0], rax
0x180062bee  mov     dword ptr [rsp+3B0h+var_350], edi
0x180062bf2  mov     [rsp+3B0h+var_348], 349h
0x180062bfa  mov     [rsp+3B0h+var_340], r14
0x180062bff  lea     rax, [rbp+2B0h+var_2C0]
0x180062c03  mov     [rsp+3B0h+var_378], rax
0x180062c08  lea     rax, [rsp+3B0h+var_350]
0x180062c0d  mov     [rsp+3B0h+var_380], rax
0x180062c12  lea     rax, [rsp+3B0h+var_348]
0x180062c17  mov     qword ptr [rsp+3B0h+secondsRemaining], rax
0x180062c1c  lea     rax, [rsp+3B0h+var_340]
0x180062c21  mov     qword ptr [rsp+3B0h+percentComplete], rax
0x180062c26  lea     rdx, dword_18012D0BC
0x180062c2d  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@U?$_tlgWrapSz@_W@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4AEBU?$_tlgWrapSz@_W@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<wchar_t> const &)
0x180062c32  call    ?Instance@TraceManager@cxl@@SAAEAV12@XZ; cxl::TraceManager::Instance(void)
0x180062c37  lea     rcx, [rax+28h]; struct cxl::TextWriter *
0x180062c3b  mov     dword ptr [rsp+3B0h+var_350], edi
0x180062c3f  mov     [rsp+3B0h+var_348], 349h
0x180062c47  lea     rax, [rsp+3B0h+var_350]
0x180062c4c  mov     qword ptr [rsp+3B0h+percentComplete], rax; __int64
0x180062c51  lea     r9, [rsp+3B0h+var_348]
0x180062c56  mov     r8, r14
0x180062c59  call    ??$WriteLine@_W$$BY0DF@DHH$$BY0BG@_W@TextWriter@cxl@@QEAAXPEB_WAEAY0DF@$$CBDAEBH2AEAY0BG@$$CB_W@Z; cxl::TextWriter::WriteLine<wchar_t,char [53],int,int,wchar_t [22]>(wchar_t const *,char const (&)[53],int const &,int const &,wchar_t const (&)[22])
0x180062c5e  jmp     short loc_180062CBD
0x180062c60  mov     eax, cs:dword_18014D6A8
0x180062c66  cmp     eax, 5
0x180062c69  jbe     short loc_180062CBD
0x180062c6b  lea     rcx, [rbp+2B0h+var_280]
0x180062c6f  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180062c74  mov     [rbp+2B0h+var_2C0], rax
0x180062c78  mov     dword ptr [rsp+3B0h+var_350], ebx
0x180062c7c  mov     [rsp+3B0h+var_348], 349h
0x180062c84  mov     [rsp+3B0h+var_340], r14
0x180062c89  lea     rax, [rbp+2B0h+var_2C0]
0x180062c8d  mov     [rsp+3B0h+var_378], rax
0x180062c92  lea     rax, [rsp+3B0h+var_350]
0x180062c97  mov     [rsp+3B0h+var_380], rax
0x180062c9c  lea     rax, [rsp+3B0h+var_348]
0x180062ca1  mov     qword ptr [rsp+3B0h+secondsRemaining], rax
0x180062ca6  lea     rax, [rsp+3B0h+var_340]
0x180062cab  mov     qword ptr [rsp+3B0h+percentComplete], rax
  ... truncated ...
```
