# Wsp::Facade::StorageHealthFacade::EnableMaintenance(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,std::unique_ptr<bool,std::default_delete<bool>> const &,std::unique_ptr<bool,std::default_delete<bool>> const &,std::unique_ptr<uint,std::default_delete<uint>> &,std::unique_ptr<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,std::default_delete<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>>> const &,std::unique_ptr<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,std::default_delete<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>>> const &,std::unique_ptr<ushort,std::default_delete<ushort>> &,mi::MiContext &,std::shared_ptr<Wsp::Facade::IExtendedStatus> &)

- ea: `0x180064604`
- end: `0x1800663ca`
- name: `?EnableMaintenance@StorageHealthFacade@Facade@Wsp@@QEAA?AW4SM_RETURN_CODE@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV?$unique_ptr@_NU?$default_delete@_N@std@@@6@1AEAV?$unique_ptr@IU?$default_delete@I@std@@@6@AEBV?$unique_ptr@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$default_delete@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@6@3AEAV?$unique_ptr@GU?$default_delete@G@std@@@6@AEAVMiContext@mi@@AEAV?$shared_ptr@UIExtendedStatus@Facade@Wsp@@@6@@Z`
- size: `7622`
- prototype: `__int64 __fastcall(int, int, int, int, __int64, __int64, __int64, __int64, __int64, MI_Uint32)`
- caller_count: `1`
- callee_count: `82`
- tags: `registry_config, installer_update, broker_com_uri`

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
- `0x180053d48`
- `0x180053d6c`
- `0x180055020`
- `0x180055098`
- `0x180058f50`
- `0x180058f88`
- `0x180059368`
- `0x18005a150`
- `0x18005add0`
- `0x18005ae34`
- `0x18005ae98`
- `0x18005aefc`
- `0x18005af60`
- `0x18005afc4`
- `0x18005b028`
- `0x18005b08c`
- `0x18005b0f0`
- `0x18005b154`
- `0x18005b280`
- `0x18005b2dc`
- `0x18005b340`
- `0x18005b3a4`
- `0x18005b464`

## string_xrefs

- `0x180066174`: `Completed`
- `0x180064dd3`: `FindWriteCacheDisks`
- `0x1800659d1`: `Waiting for SBL cache state`
- `0x180065902`: `Change SBL cache`
- `0x180065bf0`: `Rollback waiting for SBL cache state`
- `0x180065ab8`: `Rollback change SBL cache`
- `0x18006544f`: `Rollback `
- `0x180065512`: `Rollback `
- `0x180065fb0`: `Rollback `
- `0x18006607b`: `Rollback `

## pseudocode

```c
// Hidden C++ exception states: #wind=36
__int64 __fastcall Wsp::Facade::StorageHealthFacade::EnableMaintenance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3,
        __int64 a4,
        _QWORD *a5,
        _QWORD *a6,
        const char *a7,
        _QWORD *a8,
        MI_Context **a9,
        __int64 a10)
{
  MI_Context **v12; // r12
  const MI_Char *v13; // rax
  const MI_Char *v14; // r8
  const MI_Char *v15; // r9
  __int64 v16; // rax
  int v17; // ecx
  int v18; // r8d
  int v19; // r9d
  char *v20; // rbx
  _QWORD *Instance; // rax
  int SubsystemType; // eax
  MI_Uint32 FaultDomainPhysicalDisks; // edi
  int v24; // ecx
  int v25; // r8d
  int v26; // r9d
  struct cxl::TraceManager *v27; // rax
  int v28; // ecx
  __int64 SmApiSession; // rax
  struct ProtectedPwd **v30; // rax
  signed int Cluster; // ebx
  int v32; // r8d
  int v33; // r9d
  struct cxl::TraceManager *v34; // rax
  int v35; // ecx
  int v36; // r8d
  int v37; // r9d
  struct cxl::TraceManager *v38; // rax
  int v39; // ecx
  int v40; // r8d
  int v41; // r9d
  _BYTE *v42; // rcx
  __int64 v43; // rax
  std::_Ref_count_base *v44; // rcx
  __int64 v45; // rcx
  _QWORD *v46; // rbx
  const wchar_t *v47; // rax
  Wsp::Facade::StorageHealthFacade *v48; // rcx
  __int64 v49; // rax
  const wchar_t *v50; // rax
  Wsp::Facade::StorageHealthFacade *v51; // rcx
  __int64 v52; // rax
  const MI_Char *v53; // rax
  const MI_Char *v54; // r8
  const MI_Char *v55; // r9
  int v56; // ecx
  int v57; // r8d
  int v58; // r9d
  struct cxl::TraceManager *v59; // rax
  const MI_Char *v60; // rax
  const MI_Char *v61; // r8
  const MI_Char *v62; // r9
  int v63; // ecx
  int v64; // r9d
  int v65; // ecx
  int v66; // r8d
  int v67; // r9d
  struct cxl::TraceManager *v68; // rax
  const MI_Char *v69; // rax
  const MI_Char *v70; // r8
  const MI_Char *v71; // r9
  __int64 v72; // rcx
  int v73; // ecx
  int v74; // r8d
  int v75; // r9d
  struct cxl::TraceManager *v76; // rax
  const MI_Char *v77; // rax
  const MI_Char *v78; // r8
  const MI_Char *v79; // r9
  int v80; // ecx
  int v81; // r8d
  int v82; // r9d
  struct cxl::TraceManager *v83; // rax
  const MI_Char *v84; // rax
  const MI_Char *v85; // r8
  const MI_Char *v86; // r9
  __int64 v87; // rcx
  int v88; // ecx
  int v89; // r8d
  int v90; // r9d
  struct cxl::TraceManager *v91; // rax
  const MI_Char *v92; // rax
  const MI_Char *v93; // r8
  const MI_Char *v94; // r9
  const MI_Char *v95; // rax
  const MI_Char *v96; // r8
  const MI_Char *v97; // r9
  int v98; // ecx
  int v99; // r8d
  int v100; // r9d
  struct cxl::TextWriter *v101; // rbx
  __int64 v102; // rax
  int v103; // ecx
  int v104; // r8d
  int v105; // r9d
  __int64 v106; // rcx
  _QWORD *v107; // rbx
  __int64 v108; // rsi
  __int64 v109; // r14
  int v110; // r15d
  __int64 v111; // rax
  __int64 v112; // rax
  int v113; // ecx
  int v114; // r8d
  int v115; // r9d
  struct cxl::TextWriter *v116; // rbx
  __int64 v117; // rax
  __int64 v118; // rax
  __int64 v119; // rax
  __int64 i; // rsi
  __int64 v121; // r14
  __int64 v122; // rax
  int v123; // ecx
  int v124; // r8d
  int v125; // r9d
  struct cxl::TextWriter *v126; // rbx
  __int64 v127; // rax
  __int64 value; // rax
  int v129; // edx
  int v130; // ecx
  int v131; // r8d
  int v132; // r9d
  __int64 v133; // rax
  const MI_Char *v134; // rax
  const MI_Char *v135; // r8
  const MI_Char *v136; // r9
  int v137; // ecx
  int v138; // ecx
  int v139; // r8d
  int v140; // r9d
  struct cxl::TraceManager *v141; // rax
  int v142; // ecx
  int v143; // r8d
  int v144; // r9d
  struct cxl::TraceManager *v145; // rax
  __int64 v146; // rcx
  int v147; // ecx
  int v148; // r8d
  int v149; // r9d
  struct cxl::TraceManager *v150; // rax
  int v151; // ecx
  int v152; // ebx
  int v153; // ecx
  int v154; // r8d
  int v155; // r9d
  struct cxl::TraceManager *v156; // rax
  int v157; // ecx
  int v158; // r8d
  int v159; // r9d
  bool v160; // si
  int v161; // r9d
  int DiskCacheState; // ebx
  int v163; // ecx
  int v164; // r8d
  int v165; // r9d
  struct cxl::TraceManager *v166; // rax
  int v167; // ecx
  int v168; // r8d
  int v169; // r9d
  _BOOL8 v170; // rcx
  int v171; // ebx
  int v172; // ecx
  int v173; // r8d
  int v174; // r9d
  struct cxl::TraceManager *v175; // rax
  int v176; // ecx
  int v177; // r8d
  int v178; // r9d
  struct cxl::TraceManager *v179; // rax
  int v180; // edx
  int v181; // ecx
  int v182; // r8d
  int v183; // r9d
  int v184; // esi
  __int64 v185; // rax
  __int64 v186; // rax
  int v187; // ecx
  int v188; // r8d
  int v189; // r9d
  struct cxl::TextWriter *v190; // rbx
  __int64 v191; // rax
  __int64 v192; // rax
  __int64 v193; // rax
  int v194; // edx
  int v195; // ecx
  int v196; // r8d
  int v197; // r9d
  const MI_Char *v198; // rax
  const MI_Char *v199; // r8
  const MI_Char *v200; // r9
  int v201; // ecx
  int v202; // r8d
  int v203; // r9d
  struct cxl::TraceManager *v204; // rax
  int v205; // ecx
  int v206; // r8d
  int v207; // r9d
  int v208; // ecx
  int v209; // r8d
  int v210; // r9d
  __int64 v212; // rax
  __int64 v213; // rax
  MI_Uint32 secondsRemaining; // [rsp+28h] [rbp-D8h]
  MI_Uint32 secondsRemaininga; // [rsp+28h] [rbp-D8h]
  MI_Uint32 secondsRemainingb; // [rsp+28h] [rbp-D8h]
  MI_Uint32 v217; // [rsp+60h] [rbp-A0h] BYREF
  _DWORD v218[3]; // [rsp+64h] [rbp-9Ch] BYREF
  __int64 v219; // [rsp+70h] [rbp-90h] BYREF
  char v220; // [rsp+78h] [rbp-88h] BYREF
  _BYTE v221[3]; // [rsp+79h] [rbp-87h] BYREF
  MI_Uint32 v222; // [rsp+7Ch] [rbp-84h] BYREF
  const char *v223; // [rsp+80h] [rbp-80h] BYREF
  MI_Uint32 v224[2]; // [rsp+88h] [rbp-78h] BYREF
  const char *v225; // [rsp+90h] [rbp-70h] BYREF
  const char *v226; // [rsp+98h] [rbp-68h] BYREF
  __int16 v227; // [rsp+A0h] [rbp-60h] BYREF
  _QWORD *v228; // [rsp+A8h] [rbp-58h]
  const char **v229[2]; // [rsp+B0h] [rbp-50h] BYREF
  int v230; // [rsp+C0h] [rbp-40h] BYREF
  _QWORD *v231; // [rsp+C8h] [rbp-38h]
  _QWORD *v232; // [rsp+D0h] [rbp-30h]
  __int128 v233; // [rsp+D8h] [rbp-28h] BYREF
  __int64 v234; // [rsp+E8h] [rbp-18h]
  __int128 v235; // [rsp+F0h] [rbp-10h] BYREF
  __int64 v236; // [rsp+100h] [rbp+0h]
  std::_Ref_count_base *v237[2]; // [rsp+108h] [rbp+8h] BYREF
  _QWORD v238[2]; // [rsp+118h] [rbp+18h] BYREF
  _BYTE v239[32]; // [rsp+128h] [rbp+28h] BYREF
  const char *v240; // [rsp+148h] [rbp+48h] BYREF
  std::_Ref_count_base *v241; // [rsp+150h] [rbp+50h]
  _BYTE v242[32]; // [rsp+168h] [rbp+68h] BYREF
  _BYTE v243[40]; // [rsp+188h] [rbp+88h] BYREF
  unsigned int v244; // [rsp+1B0h] [rbp+B0h] BYREF
  int v245; // [rsp+1B4h] [rbp+B4h] BYREF
  _BYTE v246[80]; // [rsp+1B8h] [rbp+B8h] BYREF
  _BYTE v247[32]; // [rsp+208h] [rbp+108h] BYREF
  _BYTE v248[35]; // [rsp+228h] [rbp+128h] BYREF
  char v249; // [rsp+24Bh] [rbp+14Bh] BYREF
  int v250; // [rsp+24Ch] [rbp+14Ch]
  _BYTE v251[16]; // [rsp+250h] [rbp+150h] BYREF
  _BYTE v252[64]; // [rsp+260h] [rbp+160h] BYREF
  _BYTE v253[8]; // [rsp+2A0h] [rbp+1A0h] BYREF
  _BYTE v254[32]; // [rsp+2A8h] [rbp+1A8h] BYREF
  _OWORD v255[2]; // [rsp+2C8h] [rbp+1C8h] BYREF
  _OWORD v256[2]; // [rsp+2E8h] [rbp+1E8h] BYREF
  _BYTE v257[8]; // [rsp+308h] [rbp+208h] BYREF
  _BYTE v258[32]; // [rsp+310h] [rbp+210h] BYREF
  _BYTE v259[8]; // [rsp+330h] [rbp+230h] BYREF
  _BYTE v260[40]; // [rsp+338h] [rbp+238h] BYREF
  void **pExceptionObject; // [rsp+360h] [rbp+260h] BYREF
  _BYTE v262[104]; // [rsp+368h] [rbp+268h] BYREF

  *(_QWORD *)v224 = a4;
  v228 = a3;
  v232 = a5;
  v225 = a7;
  v231 = a6;
  v12 = a9;
  v226 = (const char *)a9;
  if ( (unsigned int)dword_18014D6A8 > 5 )
  {
    v222 = 326;
    *(_QWORD *)&v218[1] = "Wsp::Facade::StorageHealthFacade::EnableMaintenance";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      (unsigned int)"Wsp::Facade::StorageHealthFacade::EnableMaintenance",
      (unsigned int)word_18012D97A,
      (_DWORD)a3,
      a4,
      (__int64)&v218[1],
      (__int64)&v222);
  }
  v256[0] = 0;
  v256[1] = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v256[0]) = 0;
  v235 = 0;
  v236 = 0;
  v233 = 0;
  v234 = 0;
  v230 = -1;
  v227 = 1;
  std::map<std::wstring,mismpstorage::SPACES_PhysicalDisk>::map<std::wstring,mismpstorage::SPACES_PhysicalDisk>(v238);
  std::map<std::wstring,Wsp::Facade::MaintenanceDisk>::map<std::wstring,Wsp::Facade::MaintenanceDisk>(v229);
  Wsp::Facade::MaintenanceModeStruct::MaintenanceModeStruct((Wsp::Facade::MaintenanceModeStruct *)&v244);
  *(_OWORD *)v237 = 0;
  v221[0] = 0;
  v220 = 1;
  if ( !(unsigned int)Wsp::Facade::StorageHealthFacade::GetSubsystemType(a1) )
  {
    v212 = std::wstring::wstring(v253, L"non highlyavailable subsystems are not supported");
    v213 = cxl::SMResult(&v226, 59001, v212);
    cxl::Error(&pExceptionObject, v213);
    throw (cxl::Exception *)&pExceptionObject;
  }
  cxl::load_string(v243, qword_1801599A0, 3001);
  v13 = (const MI_Char *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v243);
  MI_Context_WriteProgress(*a9, v13, v14, v15, 1u, secondsRemaining);
  v255[0] = 0;
  v255[1] = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v255[0]) = 0;
  v16 = cxl::StringWriter::StringWriter(v253, v255);
  cxl::TextWriter::Write<55>(v16);
  std::wstring::wstring(v242, v255);
  if ( (unsigned int)dword_18014D6A8 > 4 && (unsigned __int8)tlgKeywordOn(&dword_18014D6A8, 0x4000) )
  {
    *(_QWORD *)&v218[1] = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v242);
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>>(
      v17,
      (unsigned int)word_18012D95A,
      v18,
      v19,
      (__int64)&v218[1]);
  }
  v20 = (char *)cxl::TraceManager::Instance() + 120;
  cxl::CxlTraits<std::wstring>::WriteTo(v20, v242);
  cxl::TextWriter::operator<<<cxl::ENDL>(v20);
  std::wstring::_Tidy_deallocate(v242);
  if ( *v231 )
  {
    v248[33] = 1;
    std::wstring::operator=(v248);
  }
  if ( *(_QWORD *)a7 )
  {
    v248[32] = 1;
    std::wstring::operator=(v247);
  }
  Instance = (_QWORD *)Wsp::MiSpaceAdapter::GetInstance(&v240);
  Wsp::MiSpaceAdapter::UnpackObjectId(*Instance, (unsigned int)v239, a2, (unsigned int)&v245, (__int64)&v244);
  std::wstring::operator=(v256);
  std::wstring::_Tidy_deallocate(v239);
  if ( v241 )
    std::_Ref_count_base::_Decref(v241);
  SubsystemType = Wsp::Facade::StorageHealthFacade::GetSubsystemType(a1);
  if ( SubsystemType != v245 )
  {
    FaultDomainPhysicalDisks = 1;
    std::wstring::wstring(v239, L"Subsystem not supported");
    if ( (unsigned int)dword_18014D6A8 > 2 )
    {
      *(_QWORD *)v224 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v239);
      v222 = 1;
      v217 = 381;
      v225 = "Wsp::Facade::StorageHealthFacade::EnableMaintenance";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>>(
        v24,
        (unsigned int)&dword_18012D8A4,
        v25,
        v26,
        (__int64)&v225,
        (__int64)&v217,
        (__int64)&v222,
        (__int64)v224);
    }
    v27 = cxl::TraceManager::Instance();
    v217 = 1;
    v222 = 381;
    cxl::TextWriter::WriteLine<wchar_t,char [52],int,int,wchar_t [24]>(
      (struct cxl::TraceManager *)((char *)v27 + 40),
      (__int64)&v217);
    std::wstring::_Tidy_deallocate(v239);
    goto LABEL_152;
  }
  if ( v244 > 0xC || (v28 = 4640, !_bittest(&v28, v244)) )
  {
    FaultDomainPhysicalDisks = 1;
    goto LABEL_152;
  }
  SmApiSession = Wsp::Facade::StorageHealthFacade::GetSmApiSession(4640, &v240);
  std::shared_ptr<mismpstorage::SPACES_VirtualDisk const>::operator=(v246, SmApiSession);
  if ( v241 )
    std::_Ref_count_base::_Decref(v241);
  v30 = (struct ProtectedPwd **)ClusWmi::DataStore::GetInstance(&v240);
  Cluster = ClusWmi::DataStore::GetCluster(*v30);
  if ( v241 )
    std::_Ref_count_base::_Decref(v241);
  if ( Cluster < 0 )
  {
    v222 = Cluster;
    if ( (unsigned int)dword_18014D6A8 > 2 )
    {
      v217 = v222;
      v218[0] = 404;
      *(_QWORD *)v224 = "Wsp::Facade::StorageHealthFacade::EnableMaintenance";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        dword_18014D6A8,
        (unsigned int)byte_18012D8E3,
        v32,
        v33,
        (__int64)v224,
        (__int64)v218,
        (__int64)&v217);
    }
    v34 = cxl::TraceManager::Instance();
    v218[0] = 404;
    cxl::TextWriter::WriteLine<wchar_t,char [52],int,long>(
      (struct cxl::TraceManager *)((char *)v34 + 40),
      (__int64)&v222);
    FaultDomainPhysicalDisks = Wsp::MiSpaceAdapter::SmRCFromHResult((unsigned int)Cluster);
    std::wstring::wstring(v242, L"Failed to Get Cluster");
    if ( FaultDomainPhysicalDisks )
    {
      if ( (unsigned int)dword_18014D6A8 > 2 )
      {
        *(_QWORD *)v224 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v242);
        v218[0] = FaultDomainPhysicalDisks;
        v217 = 405;
        v225 = "Wsp::Facade::StorageHealthFacade::EnableMaintenance";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>>(
          v35,
          (unsigned int)byte_18012D91B,
          v36,
          v37,
          (__int64)&v225,
          (__int64)&v217,
          (__int64)v218,
          (__int64)v224);
      }
      v38 = cxl::TraceManager::Instance();
      v218[0] = FaultDomainPhysicalDisks;
      v217 = 405;
      cxl::TextWriter::WriteLine<wchar_t,char [52],int,int,wchar_t [22]>(
        (struct cxl::TraceManager *)((char *)v38 + 40),
        (__int64)v218);
    }
    else if ( (unsigned int)dword_18014D6A8 > 5 )
    {
      *(_QWORD *)v224 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v242);
      v218[0] = 0;
      v217 = 405;
      v225 = "Wsp::Facade::StorageHealthFacade::EnableMaintenance";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>>(
        v39,
        (unsigned int)byte_18012D7E5,
        v40,
        v41,
        (__int64)&v225,
        (__int64)&v217,
        (__int64)v218,
        (__int64)v224);
    }
    v42 = v242;
    goto LABEL_33;
  }
  v43 = ClusApi::Facade::FacadeFactory::CreateClusterFacade(&v240, v237);
  std::shared_ptr<mismpstorage::SPACES_VirtualDisk const>::operator=(v251, v43);
  v44 = v241;
  if ( v241 )
    std::_Ref_count_base::_Decref(v241);
  Wsp::Facade::StorageHealthFacade::GetLocalNode(v44, &v244);
  Wsp::Facade::StorageHealthFacade::S2DEnabled(v45, &v244);
  v46 = v232;
  if ( !*v232 )
  {
    if ( v249 )
    {
      v47 = (const wchar_t *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(qword_180159A40);
      Wsp::Facade::StorageHealthFacade::GetMaintenanceModeConfiguration(
        v48,
        v47,
        (void (*)(const wchar_t *, const wchar_t *, void *))Wsp::Facade::_MaintenanceModeTimeoutConfigurationCallback,
        &v230);
      v49 = std::make_unique<unsigned int,unsigned int &,0>(&v218[1], &v230);
      std::unique_ptr<unsigned int>::operator=<std::default_delete<unsigned int>,0>(v46, v49);
      std::unique_ptr<unsigned int>::~unique_ptr<unsigned int>(&v218[1]);
    }
    else
    {
      std::unique_ptr<unsigned int>::reset(v232, 0);
    }
  }
  if ( !*a8 )
  {
    v50 = (const wchar_t *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(qword_180159A60);
    Wsp::Facade::StorageHealthFacade::GetMaintenanceModeConfiguration(
      v51,
      v50,
      (void (*)(const wchar_t *, const wchar_t *, void *))Wsp::Facade::_MaintenanceModeValidationLevelConfigurationCallback,
      &v227);
    v52 = std::make_unique<unsigned short,unsigned short &,0>(&v218[1], &v227);
    std::unique_ptr<unsigned short>::operator=<std::default_delete<unsigned short>,0>(a8, v52);
    std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&v218[1]);
  }
  v53 = (const MI_Char *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v243);
  MI_Context_WriteProgress(*a9, v53, v54, v55, 2u, secondsRemaininga);
  secondsRemaininga = a10;
  FaultDomainPhysicalDisks = Wsp::Facade::StorageHealthFacade::GetFaultDomainPhysicalDisks(
                               a1,
                               a2,
                               (unsigned int)&v244,
                               (unsigned int)v229,
                               (__int64)v238);
  if ( FaultDomainPhysicalDisks )
  {
    std::wstring::wstring(v239, L"GetFaultDomainPhysicalDisks");
    if ( (unsigned int)dword_18014D6A8 > 2 )
    {
      *(_QWORD *)v224 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v239);
      v218[0] = FaultDomainPhysicalDisks;
      v217 = 452;
      v225 = "Wsp::Facade::StorageHealthFacade::EnableMaintenance";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>>(
        v56,
        (unsigned int)&word_18012D826,
        v57,
        v58,
        (__int64)&v225,
        (__int64)&v217,
        (__int64)v218,
        (__int64)v224);
    }
    v59 = cxl::TraceManager::Instance();
    v218[0] = FaultDomainPhysicalDisks;
    v217 = 452;
    cxl::TextWriter::WriteLine<wchar_t,char [52],int,int,wchar_t [28]>(
      (struct cxl::TraceManager *)((char *)v59 + 40),
      (__int64)v218,
      (__int64)L"GetFaultDomainPhysicalDisks");
LABEL_46:
    std::wstring::_Tidy_deallocate(v239);
    goto LABEL_152;
  }
  if ( v249 && v250 )
  {
    v60 = (const MI_Char *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v243);
    MI_Context_WriteProgress(*a9, v60, v61, v62, 3u, a10);
    FaultDomainPhysicalDisks = Wsp::Facade::StorageHealthFacade::FindWriteCacheDisks(v63, (__int64)&v244, v229, v64);
    if ( FaultDomainPhysicalDisks )
    {
      std::wstring::wstring(v239, L"FindWriteCacheDisks");
      if ( (unsigned int)dword_18014D6A8 > 2 )
      {
        *(_QWORD *)v224 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v239);
        v218[0] = FaultDomainPhysicalDisks;
        v217 = 470;
        v225 = "Wsp::Facade::StorageHealthFacade::EnableMaintenance";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>>(
          v65,
          (unsigned int)byte_18012D865,
          v66,
          v67,
          (__int64)&v225,
          (__int64)&v217,
          (__int64)v218,
          (__int64)v224);
      }
      v68 = cxl::TraceManager::Instance();
      v218[0] = FaultDomainPhysicalDisks;
      v217 = 470;
      cxl::TextWriter::WriteLine<wchar_t,char [52],int,int,wchar_t [20]>(
        (struct cxl::TraceManager *)((char *)v68 + 40),
        (__int64)v218);
      goto LABEL_46;
    }
    v69 = (const MI_Char *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v243);
    MI_Context_WriteProgress(*a9, v69, v70, v71, 4u, secondsRemaininga);
    FaultDomainPhysicalDisks = Wsp::Facade::StorageHealthFacade::ValidateFiltering(v72, &v244, v229);
    if ( FaultDomainPhysicalDisks )
    {
      std::wstring::wstring(v239, L"ValidateFiltering");
      if ( (unsigned int)dword_18014D6A8 > 2 )
      {
        *(_QWORD *)v224 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v239);
        v218[0] = FaultDomainPhysicalDisks;
        v217 = 487;
        v225 = "Wsp::Facade::StorageHealthFacade::EnableMaintenance";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>>(
          v73,
          (unsigned int)&byte_18012D767,
          v74,
          v75,
          (__int64)&v225,
          (__int64)&v217,
          (__int64)v218,
          (__int64)v224);
      }
      v76 = cxl::TraceManager::Instance();
      v218[0] = FaultDomainPhysicalDisks;
      v217 = 487;
      cxl::TextWriter::WriteLine<wchar_t,char [52],int,int,wchar_t [18]>(
        (struct cxl::TraceManager *)((char *)v76 + 40),
        (__int64)v218,
        (__int64)L"ValidateFiltering");
      goto LABEL_46;
    }
  }
  if ( *(_WORD *)*a8 )
  {
    if ( (*(_BYTE *)*a8 & 1) != 0 )
    {
      v77 = (const MI_Char *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v243);
      MI_Context_WriteProgress(*a9, v77, v78, v79, 5u, secondsRemaininga);
      FaultDomainPhysicalDisks = Wsp::Facade::StorageHealthFacade::ValidateAllVirtualDiskHealthy(
                                   a1,
                                   (__int64)&v244,
                                   v238,
                                   a10);
      if ( FaultDomainPhysicalDisks )
      {
        std::wstring::wstring(v239, L"ValidateAllVirtualDiskHealthy");
        if ( (unsigned int)dword_18014D6A8 > 2 )
        {
          *(_QWORD *)v224 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v239);
          v218[0] = FaultDomainPhysicalDisks;
          v217 = 509;
          v225 = "Wsp::Facade::StorageHealthFacade::EnableMaintenance";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>>(
            v80,
            (unsigned int)&word_18012D7A6,
            v81,
            v82,
            (__int64)&v225,
            (__int64)&v217,
            (__int64)v218,
            (__int64)v224);
        }
        v83 = cxl::TraceManager::Instance();
        v218[0] = FaultDomainPhysicalDisks;
        v217 = 509;
        cxl::TextWriter::WriteLine<wchar_t,char [52],int,int,wchar_t [30]>(
          (struct cxl::TraceManager *)((char *)v83 + 40),
          (__int64)v218);
LABEL_63:
        v42 = v239;
LABEL_33:
        std::wstring::_Tidy_deallocate(v42);
        goto LABEL_152;
      }
    }
  }
  if ( v249 )
  {
    if ( v250 )
    {
      v84 = (const MI_Char *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v243);
      MI_Context_WriteProgress(*a9, v84, v85, v86, 6u, secondsRemaininga);
      FaultDomainPhysicalDisks = Wsp::Facade::StorageHealthFacade::QueryBoundDevices(v87, &v244, v229, &v235);
      if ( FaultDomainPhysicalDisks )
      {
        std::wstring::wstring(v239, L"QueryBoundDevices");
        if ( (unsigned int)dword_18014D6A8 > 2 )
        {
          *(_QWORD *)v224 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v239);
          v218[0] = FaultDomainPhysicalDisks;
          v217 = 532;
          v225 = "Wsp::Facade::StorageHealthFacade::EnableMaintenance";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>>(
            v88,
            (unsigned int)byte_18012D6E9,
            v89,
            v90,
            (__int64)&v225,
            (__int64)&v217,
            (__int64)v218,
            (__int64)v224);
        }
        v91 = cxl::TraceManager::Instance();
        v218[0] = FaultDomainPhysicalDisks;
        v217 = 532;
        cxl::TextWriter::WriteLine<wchar_t,char [52],int,int,wchar_t [18]>(
          (struct cxl::TraceManager *)((char *)v91 + 40),
          (__int64)v218,
          (__int64)L"QueryBoundDevices");
        goto LABEL_63;
      }
    }
  }
  v92 = (const MI_Char *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v243);
  MI_Context_WriteProgress(*a9, v92, v93, v94, 7u, secondsRemaininga);
  std::shared_ptr<ClusApi::IStorage>::shared_ptr<ClusApi::IStorage>(&v240, v246);
  secondsRemainingb = v224[0];
  FaultDomainPhysicalDisks = Wsp::Facade::StorageHealthFacade::CallMaintenanceOnTargetObject(
                               &v249,
                               v252,
                               &v244,
                               &v220,
                               v228);
  v222 = FaultDomainPhysicalDisks;
  v95 = (const MI_Char *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v243);
  MI_Context_WriteProgress(*a9, v95, v96, v97, 8u, secondsRemainingb);
  std::operator+<wchar_t>(v242, L"Target ObjectID:", a2);
  if ( FaultDomainPhysicalDisks )
  {
    if ( (unsigned int)dword_18014D6A8 > 2 )
    {
      *(_QWORD *)&v218[1] = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v242);
      v218[0] = FaultDomainPhysicalDisks;
      v217 = 568;
      v219 = (__int64)"Wsp::Facade::StorageHealthFacade::EnableMaintenance";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>>(
        v98,
        (unsigned int)qword_18012D728,
        v99,
        v100,
        (__int64)&v219,
        (__int64)&v217,
        (__int64)v218,
        (__int64)&v218[1]);
    }
    v101 = (struct cxl::TraceManager *)((char *)cxl::TraceManager::Instance() + 40);
    v102 = std::operator+<wchar_t>(v239, L"Target ObjectID:", a2);
    v218[0] = FaultDomainPhysicalDisks;
    v217 = 568;
    cxl::TextWriter::WriteLine<wchar_t,char [52],int,int,std::wstring>(v101, (__int64)v218, v102);
    std::wstring::_Tidy_deallocate(v239);
  }
  else if ( (unsigned int)dword_18014D6A8 > 5 )
  {
    *(_QWORD *)&v218[1] = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v242);
    v218[0] = 0;
    v217 = 568;
    v219 = (__int64)"Wsp::Facade::StorageHealthFacade::EnableMaintenance";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>>(
      v103,
      (unsigned int)qword_18012D6A8,
      v104,
      v105,
      (__int64)&v219,
      (__int64)&v217,
      (__int64)v218,
      (__int64)&v218[1]);
  }
  std::wstring::_Tidy_deallocate(v242);
  if ( v249 )
  {
    if ( FaultDomainPhysicalDisks )
    {
      if ( !v250 )
        goto LABEL_152;
LABEL_79:
      v107 = v228;
      goto LABEL_80;
    }
    if ( !v250 )
      goto LABEL_152;
    v121 = *((_QWORD *)&v235 + 1);
    for ( i = v235; i != v121; i += 64 )
    {
      std::shared_ptr<ClusApi::IStorage>::shared_ptr<ClusApi::IStorage>(v242, v246);
      v218[0] = 5;
      secondsRemaininga = v224[0];
      FaultDomainPhysicalDisks = Wsp::Facade::StorageHealthFacade::CallMaintenanceOnTargetObject(
                                   &v249,
                                   i,
                                   v218,
                                   &v220,
                                   v228);
      v222 = FaultDomainPhysicalDisks;
      v122 = mismpstorage::SPACES_StoragePool::ObjectId(i, v253);
      mismpstorage::read_property<std::wstring>::get_value(v122, v239);
      std::wstring::_Tidy_deallocate(v254);
      if ( FaultDomainPhysicalDisks )
      {
        if ( (unsigned int)dword_18014D6A8 > 2 )
        {
          v223 = (const char *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v239);
          v218[0] = FaultDomainPhysicalDisks;
          v217 = 607;
          v240 = "Wsp::Facade::StorageHealthFacade::EnableMaintenance";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>>(
            v123,
            (unsigned int)byte_18012D669,
            v124,
            v125,
            (__int64)&v240,
            (__int64)&v217,
            (__int64)v218,
            (__int64)&v223);
        }
        v126 = (struct cxl::TraceManager *)((char *)cxl::TraceManager::Instance() + 40);
        v127 = mismpstorage::SPACES_StoragePool::ObjectId(i, v257);
        value = mismpstorage::read_property<std::wstring>::get_value(v127, &v240);
        LODWORD(v219) = FaultDomainPhysicalDisks;
        v218[1] = 607;
        cxl::TextWriter::WriteLine<wchar_t,char [52],int,int,std::wstring>(v126, (__int64)&v219, value);
        std::wstring::_Tidy_deallocate(&v240);
        std::wstring::_Tidy_deallocate(v258);
      }
      else if ( (unsigned int)dword_18014D6A8 > 5 )
      {
        v240 = (const char *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v239);
        v218[0] = v129;
        v217 = 607;
        v223 = "Wsp::Facade::StorageHealthFacade::EnableMaintenance";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>>(
          v130,
          (unsigned int)qword_18012D628,
          v131,
          v132,
          (__int64)&v223,
          (__int64)&v217,
          (__int64)v218,
          (__int64)&v240);
      }
      std::wstring::_Tidy_deallocate(v239);
      if ( FaultDomainPhysicalDisks )
        goto LABEL_79;
      v133 = mismpstorage::SPACES_PhysicalDisk::Clone(i, &pExceptionObject);
      std::vector<mismpstorage::SPACES_PhysicalDisk>::emplace_back<mismpstorage::SPACES_PhysicalDisk>(&v233, v133);
      pExceptionObject = &mismpstorage::mi_base::`vftable';
      mi::MiInstance::~MiInstance((mi::MiInstance *)v262);
    }
    v107 = v228;
    if ( *v228 && *(_BYTE *)*v228 )
    {
      v134 = (const MI_Char *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v243);
      MI_Context_WriteProgress(*a9, v134, v135, v136, 0x64u, secondsRemaininga);
      goto LABEL_152;
    }
    v218[1] = 4;
    FaultDomainPhysicalDisks = Wsp::Facade::StorageHealthFacade::SetMaintenanceModeIntent(v106, v229, &v218[1]);
    v222 = FaultDomainPhysicalDisks;
    if ( FaultDomainPhysicalDisks )
    {
      std::wstring::wstring(v239, L"Set Starting Maintenance Mode Intent on Physical Disks");
      if ( (unsigned int)dword_18014D6A8 > 2 )
      {
        v240 = (const char *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v239);
        v218[1] = FaultDomainPhysicalDisks;
        LODWORD(v219) = 637;
        v223 = "Wsp::Facade::StorageHealthFacade::EnableMaintenance";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>>(
          v138,
          (unsigned int)word_18012D5AA,
          v139,
          v140,
          (__int64)&v223,
          (__int64)&v219,
          (__int64)&v218[1],
          (__int64)&v240);
      }
      v141 = cxl::TraceManager::Instance();
      v218[1] = FaultDomainPhysicalDisks;
      LODWORD(v219) = 637;
      cxl::TextWriter::WriteLine<wchar_t,char [52],int,int,wchar_t [55]>(
        (struct cxl::TraceManager *)((char *)v141 + 40),
        (__int64)&v218[1],
        (__int64)L"Set Starting Maintenance Mode Intent on Physical Disks");
LABEL_106:
      std::wstring::_Tidy_deallocate(v239);
LABEL_80:
      v220 = 0;
      if ( v249 )
      {
        if ( v250 )
        {
          v109 = *((_QWORD *)&v233 + 1);
          v108 = v233;
          if ( (_QWORD)v233 != *((_QWORD *)&v233 + 1) )
          {
            do
            {
              std::shared_ptr<ClusApi::IStorage>::shared_ptr<ClusApi::IStorage>(v242, v246);
              v218[1] = 5;
              v110 = Wsp::Facade::StorageHealthFacade::CallMaintenanceOnTargetObject(&v249, v108, &v218[1], &v220, v107);
              v111 = mismpstorage::SPACES_StoragePool::ObjectId(v108, v259);
              v112 = mismpstorage::read_property<std::wstring>::get_value(v111, v257);
              std::operator+<wchar_t>(v239, L"Rollback ", v112);
              std::wstring::_Tidy_deallocate(v257);
              std::wstring::_Tidy_deallocate(v260);
              if ( v110 )
              {
                if ( (unsigned int)dword_18014D6A8 > 2 )
                {
                  v240 = (const char *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v239);
                  v218[1] = v110;
                  LODWORD(v219) = 736;
                  v223 = "Wsp::Facade::StorageHealthFacade::EnableMaintenance";
                  _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>>(
                    v113,
                    (unsigned int)&word_18012D42E,
                    v114,
                    v115,
                    (__int64)&v223,
                    (__int64)&v219,
                    (__int64)&v218[1],
                    (__int64)&v240);
                }
                v116 = (struct cxl::TraceManager *)((char *)cxl::TraceManager::Instance() + 40);
                v117 = mismpstorage::SPACES_StoragePool::ObjectId(v108, &pExceptionObject);
                v118 = mismpstorage::read_property<std::wstring>::get_value(v117, v253);
                v119 = std::operator+<wchar_t>(&v240, L"Rollback ", v118);
                v218[0] = v110;
                v217 = 736;
                cxl::TextWriter::WriteLine<wchar_t,char [52],int,int,std::wstring>(v116, (__int64)v218, v119);
                std::wstring::_Tidy_deallocate(&v240);
                std::wstring::_Tidy_deallocate(v253);
                std::wstring::_Tidy_deallocate(v262);
                v107 = v228;
              }
              else if ( (unsigned int)dword_18014D6A8 > 5 )
              {
                v240 = (const char *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v239);
                v218[1] = v180;
                LODWORD(v219) = 736;
                v223 = "Wsp::Facade::StorageHealthFacade::EnableMaintenance";
                _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>>(
                  v181,
                  (unsigned int)byte_18012D2ED,
                  v182,
                  v183,
                  (__int64)&v223,
                  (__int64)&v219,
                  (__int64)&v218[1],
                  (__int64)&v240);
              }
              std::wstring::_Tidy_deallocate(v239);
              v108 += 64;
            }
            while ( v108 != v109 );
            FaultDomainPhysicalDisks = v222;
            v12 = (MI_Context **)v226;
          }
        }
      }
      std::shared_ptr<ClusApi::IStorage>::shared_ptr<ClusApi::IStorage>(v242, v246);
      secondsRemaininga = v224[0];
      v184 = Wsp::Facade::StorageHealthFacade::CallMaintenanceOnTargetObject(&v249, v252, &v244, &v220, v107);
      v185 = mismpstorage::SPACES_StoragePool::ObjectId(v252, &pExceptionObject);
      v186 = mismpstorage::read_property<std::wstring>::get_value(v185, v253);
      std::operator+<wchar_t>(v239, L"Rollback ", v186);
      std::wstring::_Tidy_deallocate(v253);
      std::wstring::_Tidy_deallocate(v262);
      if ( v184 )
      {
        if ( (unsigned int)dword_18014D6A8 > 2 )
        {
          v226 = (const char *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v239);
          v218[1] = v184;
          LODWORD(v219) = 752;
          v240 = "Wsp::Facade::StorageHealthFacade::EnableMaintenance";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>>(
            v187,
            (unsigned int)&word_18012D32E,
            v188,
            v189,
            (__int64)&v240,
            (__int64)&v219,
            (__int64)&v218[1],
            (__int64)&v226);
        }
        v190 = (struct cxl::TraceManager *)((char *)cxl::TraceManager::Instance() + 40);
        v191 = mismpstorage::SPACES_StoragePool::ObjectId(v252, v259);
        v192 = mismpstorage::read_property<std::wstring>::get_value(v191, v242);
        v193 = std::operator+<wchar_t>(v257, L"Rollback ", v192);
        v218[1] = v184;
        LODWORD(v219) = 752;
        cxl::TextWriter::WriteLine<wchar_t,char [52],int,int,std::wstring>(v190, (__int64)&v218[1], v193);
        std::wstring::_Tidy_deallocate(v257);
        std::wstring::_Tidy_deallocate(v242);
        std::wstring::_Tidy_deallocate(v260);
      }
      else if ( (unsigned int)dword_18014D6A8 > 5 )
      {
        v226 = (const char *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v239);
        v218[1] = v194;
        LODWORD(v219) = 752;
        v240 = "Wsp::Facade::StorageHealthFacade::EnableMaintenance";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>>(
          v195,
          (unsigned int)byte_18012D36D,
          v196,
          v197,
          (__int64)&v240,
          (__int64)&v219,
          (__int64)&v218[1],
          (__int64)&v226);
      }
      goto LABEL_46;
    }
    FaultDomainPhysicalDisks = Wsp::Facade::StorageHealthFacade::ChangeWriteCache(
                                 v137,
                                 (unsigned int)v221,
                                 (unsigned int)&v244,
                                 (unsigned int)v229,
                                 a10);
    v222 = FaultDomainPhysicalDisks;
    if ( FaultDomainPhysicalDisks )
    {
      std::wstring::wstring(v239, L"Change SBL cache");
      if ( (unsigned int)dword_18014D6A8 > 2 )
      {
        v240 = (const char *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v239);
        v218[1] = FaultDomainPhysicalDisks;
        LODWORD(v219) = 648;
        v223 = "Wsp::Facade::StorageHealthFacade::EnableMaintenance";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>>(
          v142,
          (unsigned int)byte_18012D5E9,
          v143,
          v144,
          (__int64)&v223,
          (__int64)&v219,
          (__int64)&v218[1],
          (__int64)&v240);
      }
      v145 = cxl::TraceManager::Instance();
      v218[1] = FaultDomainPhysicalDisks;
      LODWORD(v219) = 648;
      cxl::TextWriter::WriteLine<wchar_t,char [52],int,int,wchar_t [17]>(
        (struct cxl::TraceManager *)((char *)v145 + 40),
        (__int64)&v218[1]);
    }
    else
    {
      FaultDomainPhysicalDisks = Wsp::Facade::StorageHealthFacade::GetDiskCacheState(
                                   a1,
                                   (unsigned int)&v244,
                                   (unsigned int)v229,
                                   0,
                                   (__int64)a9,
                                   a10);
      v222 = FaultDomainPhysicalDisks;
      if ( !FaultDomainPhysicalDisks )
      {
        v218[1] = 4;
        FaultDomainPhysicalDisks = Wsp::Facade::StorageHealthFacade::ClearMaintenanceModeIntent(v146, v229, &v218[1]);
        v222 = FaultDomainPhysicalDisks;
        if ( !FaultDomainPhysicalDisks )
          goto LABEL_152;
        std::wstring::wstring(v239, L"Clear Starting Maintenance Mode Intent on Physical Disks");
        if ( (unsigned int)dword_18014D6A8 > 2 )
        {
          v240 = (const char *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v239);
          v218[1] = FaultDomainPhysicalDisks;
          LODWORD(v219) = 668;
          v223 = "Wsp::Facade::StorageHealthFacade::EnableMaintenance";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>>(
            v176,
            (unsigned int)byte_18012D56B,
            v177,
            v178,
            (__int64)&v223,
            (__int64)&v219,
            (__int64)&v218[1],
            (__int64)&v240);
        }
        v179 = cxl::TraceManager::Instance();
        v218[1] = FaultDomainPhysicalDisks;
        LODWORD(v219) = 668;
        cxl::TextWriter::WriteLine<wchar_t,char [52],int,int,wchar_t [57]>(
          (struct cxl::TraceManager *)((char *)v179 + 40),
          (__int64)&v218[1]);
        goto LABEL_106;
      }
      std::wstring::wstring(v239, L"Waiting for SBL cache state");
      if ( (unsigned int)dword_18014D6A8 > 2 )
      {
        v240 = (const char *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v239);
        v218[1] = FaultDomainPhysicalDisks;
        LODWORD(v219) = 661;
        v223 = "Wsp::Facade::StorageHealthFacade::EnableMaintenance";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>>(
          v147,
          (unsigned int)&dword_18012D52C,
          v148,
          v149,
          (__int64)&v223,
          (__int64)&v219,
          (__int64)&v218[1],
          (__int64)&v240);
      }
      v150 = cxl::TraceManager::Instance();
      v218[1] = FaultDomainPhysicalDisks;
      LODWORD(v219) = 661;
      cxl::TextWriter::WriteLine<wchar_t,char [52],int,int,wchar_t [28]>(
        (struct cxl::TraceManager *)((char *)v150 + 40),
        (__int64)&v218[1],
        (__int64)L"Waiting for SBL cache state");
    }
    std::wstring::_Tidy_deallocate(v239);
    if ( !v249 || !v250 )
      goto LABEL_80;
    v221[0] = 1;
    v152 = Wsp::Facade::StorageHealthFacade::ChangeWriteCache(
             v151,
             (unsigned int)v221,
             (unsigned int)&v244,
             (unsigned int)v229,
             a10);
    std::wstring::wstring(v239, L"Rollback change SBL cache");
    if ( v152 )
    {
      if ( (unsigned int)dword_18014D6A8 > 2 )
      {
        v240 = (const char *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v239);
        v218[1] = v152;
        LODWORD(v219) = 687;
        v223 = "Wsp::Facade::StorageHealthFacade::EnableMaintenance";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>>(
          v153,
          (unsigned int)byte_18012D46D,
          v154,
          v155,
          (__int64)&v223,
          (__int64)&v219,
          (__int64)&v218[1],
          (__int64)&v240);
      }
      v156 = cxl::TraceManager::Instance();
      v218[1] = v152;
      LODWORD(v219) = 687;
      cxl::TextWriter::WriteLine<wchar_t,char [52],int,int,wchar_t [26]>(
        (struct cxl::TraceManager *)((char *)v156 + 40),
        (__int64)&v218[1]);
    }
    else if ( (unsigned int)dword_18014D6A8 > 5 )
    {
      v240 = (const char *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v239);
      v218[1] = 0;
      LODWORD(v219) = 687;
      v223 = "Wsp::Facade::StorageHealthFacade::EnableMaintenance";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>>(
        v157,
        (unsigned int)&dword_18012D4AC,
        v158,
        v159,
        (__int64)&v223,
        (__int64)&v219,
        (__int64)&v218[1],
        (__int64)&v240);
    }
    std::wstring::_Tidy_deallocate(v239);
    v160 = v152 == 0;
    LOBYTE(v161) = 1;
    DiskCacheState = Wsp::Facade::StorageHealthFacade::GetDiskCacheState(
                       a1,
                       (unsigned int)&v244,
                       (unsigned int)v229,
                       v161,
                       (__int64)a9,
                       a10);
    std::wstring::wstring(v239, L"Rollback waiting for SBL cache state");
    if ( DiskCacheState )
    {
      if ( (unsigned int)dword_18014D6A8 > 2 )
      {
        v240 = (const char *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v239);
        v218[1] = DiskCacheState;
        LODWORD(v219) = 700;
        v223 = "Wsp::Facade::StorageHealthFacade::EnableMaintenance";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>>(
          v163,
          (unsigned int)byte_18012D4ED,
          v164,
          v165,
          (__int64)&v223,
          (__int64)&v219,
          (__int64)&v218[1],
          (__int64)&v240);
      }
      v166 = cxl::TraceManager::Instance();
      v218[1] = DiskCacheState;
      LODWORD(v219) = 700;
      cxl::TextWriter::WriteLine<wchar_t,char [52],int,int,wchar_t [37]>(
        (struct cxl::TraceManager *)((char *)v166 + 40),
        (__int64)&v218[1]);
    }
    else if ( (unsigned int)dword_18014D6A8 > 5 )
    {
      v240 = (const char *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v239);
      v218[1] = 0;
      LODWORD(v219) = 700;
      v223 = "Wsp::Facade::StorageHealthFacade::EnableMaintenance";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>>(
        v167,
        (unsigned int)&word_18012D3AE,
        v168,
        v169,
        (__int64)&v223,
        (__int64)&v219,
        (__int64)&v218[1],
        (__int64)&v240);
    }
    std::wstring::_Tidy_deallocate(v239);
    v170 = 0;
    if ( !DiskCacheState )
      v170 = v160;
    if ( v170 )
    {
      v218[1] = 4;
      v171 = Wsp::Facade::StorageHealthFacade::ClearMaintenanceModeIntent(v170, v229, &v218[1]);
      if ( v171 )
      {
        std::wstring::wstring(v239, L"Clear Starting Maintenance Mode Intent on Physical Disks ");
        if ( (unsigned int)dword_18014D6A8 > 2 )
        {
          v240 = (const char *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v239);
          v218[1] = v171;
          LODWORD(v219) = 711;
          v223 = "Wsp::Facade::StorageHealthFacade::EnableMaintenance";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>>(
            v172,
            (unsigned int)&byte_18012D3EF,
            v173,
            v174,
            (__int64)&v223,
            (__int64)&v219,
            (__int64)&v218[1],
            (__int64)&v240);
        }
        v175 = cxl::TraceManager::Instance();
        v218[1] = v171;
        LODWORD(v219) = 711;
        cxl::TextWriter::WriteLine<wchar_t,char [52],int,int,wchar_t [58]>(
          (struct cxl::TraceManager *)((char *)v175 + 40),
          (__int64)&v218[1]);
        std::wstring::_Tidy_deallocate(v239);
      }
    }
    goto LABEL_79;
  }
LABEL_152:
  v198 = (const MI_Char *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v243);
  MI_Context_WriteProgress(*v12, v198, v199, v200, 0x64u, secondsRemaininga);
  std::wstring::wstring(v239, L"Completed");
  if ( FaultDomainPhysicalDisks )
  {
    if ( (unsigned int)dword_18014D6A8 > 2 )
    {
      v226 = (const char *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v239);
      v218[1] = FaultDomainPhysicalDisks;
      LODWORD(v219) = 768;
      v240 = "Wsp::Facade::StorageHealthFacade::EnableMaintenance";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>>(
        v201,
        (unsigned int)word_18012D212,
        v202,
        v203,
        (__int64)&v240,
        (__int64)&v219,
        (__int64)&v218[1],
        (__int64)&v226);
    }
    v204 = cxl::TraceManager::Instance();
    v218[1] = FaultDomainPhysicalDisks;
    LODWORD(v219) = 768;
    cxl::TextWriter::WriteLine<wchar_t,char [52],int,int,wchar_t [10]>(
      (struct cxl::TraceManager *)((char *)v204 + 40),
      (__int64)&v218[1]);
  }
  else if ( (unsigned int)dword_18014D6A8 > 5 )
  {
    v226 = (const char *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v239);
    v218[1] = 0;
    LODWORD(v219) = 768;
    v240 = "Wsp::Facade::StorageHealthFacade::EnableMaintenance";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>>(
      v205,
      (unsigned int)byte_18012D251,
      v206,
      v207,
      (__int64)&v240,
      (__int64)&v219,
      (__int64)&v218[1],
      (__int64)&v226);
  }
  std::wstring::_Tidy_deallocate(v239);
  if ( (unsigned int)dword_18014D6A8 > 5 )
  {
    v218[1] = 770;
    v226 = "Wsp::Facade::StorageHealthFacade::EnableMaintenance";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      v208,
      (unsigned int)word_18012D292,
      v209,
      v210,
      (__int64)&v226,
      (__int64)&v218[1]);
  }
  std::wstring::_Tidy_deallocate(v255);
  std::wstring::_Tidy_deallocate(v243);
  if ( v237[1] )
    std::_Ref_count_base::_Decref(v237[1]);
  Wsp::Facade::MaintenanceModeStruct::~MaintenanceModeStruct((Wsp::Facade::MaintenanceModeStruct *)&v244);
  std::_Tree<std::_Tmap_traits<std::wstring,Wsp::Facade::MaintenanceDisk,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,Wsp::Facade::MaintenanceDisk>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,Wsp::Facade::MaintenanceDisk,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,Wsp::Facade::MaintenanceDisk>>,0>>(v229);
  std::_Tree<std::_Tmap_traits<std::wstring,mismpstorage::SPACES_VirtualDisk,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,mismpstorage::SPACES_VirtualDisk>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,mismpstorage::SPACES_VirtualDisk,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,mismpstorage::SPACES_VirtualDisk>>,0>>(v238);
  if ( (_QWORD)v233 )
  {
    std::_Destroy_range<std::allocator<mismpstorage::SPACES_PhysicalDisk>>(v233, *((_QWORD *)&v233 + 1));
    std::_Deallocate<16>(v233, (v234 - v233) & 0xFFFFFFFFFFFFFFC0uLL);
    v233 = 0;
    v234 = 0;
  }
  if ( (_QWORD)v235 )
  {
    std::_Destroy_range<std::allocator<mismpstorage::SPACES_PhysicalDisk>>(v235, *((_QWORD *)&v235 + 1));
    std::_Deallocate<16>(v235, (v236 - v235) & 0xFFFFFFFFFFFFFFC0uLL);
    v235 = 0;
    v236 = 0;
  }
  std::wstring::_Tidy_deallocate(v256);
  return FaultDomainPhysicalDisks;
}

```

## disassembly

```asm
0x180064604  push    rbp
0x180064606  push    rbx
0x180064607  push    rsi
0x180064608  push    rdi
0x180064609  push    r12
0x18006460b  push    r13
0x18006460d  push    r14
0x18006460f  push    r15
0x180064611  lea     rbp, [rsp-2E8h]
0x180064619  sub     rsp, 3E8h
0x180064620  mov     rax, cs:__security_cookie
0x180064627  xor     rax, rsp
0x18006462a  mov     [rbp+320h+var_50], rax
0x180064631  mov     qword ptr [rbp+320h+var_398], r9
0x180064635  mov     [rbp+320h+var_378], r8
0x180064639  mov     r14, rdx
0x18006463c  mov     r15, rcx
0x18006463f  mov     rsi, [rbp+320h+arg_38]
0x180064646  mov     rax, [rbp+320h+arg_20]
0x18006464d  mov     [rbp+320h+var_350], rax
0x180064651  mov     rdi, [rbp+320h+arg_30]
0x180064658  mov     [rbp+320h+var_390], rdi
0x18006465c  mov     rax, [rbp+320h+arg_28]
0x180064663  mov     [rbp+320h+var_358], rax
0x180064667  mov     r12, [rbp+320h+arg_40]
0x18006466e  mov     [rbp+320h+var_388], r12
0x180064672  mov     r13, qword ptr [rbp+320h+arg_48]
0x180064679  mov     eax, cs:dword_18014D6A8
0x18006467f  lea     rcx, aWspFacadeStora_24; "Wsp::Facade::StorageHealthFacade::Enabl"...
0x180064686  cmp     eax, 5
0x180064689  jbe     short loc_1800646B8
0x18006468b  mov     [rsp+420h+var_3A4], 146h
0x180064693  mov     qword ptr [rsp+420h+var_3BC+4], rcx
0x180064698  lea     rax, [rsp+420h+var_3A4]
0x18006469d  mov     qword ptr [rsp+420h+secondsRemaining], rax; secondsRemaining
0x1800646a2  lea     rax, [rsp+420h+var_3BC+4]
0x1800646a7  mov     qword ptr [rsp+420h+percentComplete], rax
0x1800646ac  lea     rdx, word_18012D97A
0x1800646b3  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x1800646b8  xorps   xmm0, xmm0
0x1800646bb  movups  [rbp+320h+var_138], xmm0
0x1800646c2  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x1800646ca  movdqu  [rbp+320h+var_128], xmm1
0x1800646d2  xor     ebx, ebx
0x1800646d4  mov     word ptr [rbp+320h+var_138], bx
0x1800646db  movdqu  [rbp+320h+var_330], xmm0
0x1800646e0  mov     [rbp+320h+var_320], rbx
0x1800646e4  movdqu  [rbp+320h+var_348], xmm0
0x1800646e9  mov     [rbp+320h+var_338], rbx
0x1800646ed  mov     [rbp+320h+var_360], 0FFFFFFFFh
0x1800646f4  lea     eax, [rbx+1]
0x1800646f7  mov     [rbp+320h+var_380], ax
0x1800646fb  lea     rcx, [rbp+320h+var_308]
0x1800646ff  call    ??0?$map@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@VSPACES_PhysicalDisk@mismpstorage@@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@VSPACES_PhysicalDisk@mismpstorage@@@std@@@2@@std@@QEAA@XZ; std::map<std::wstring,mismpstorage::SPACES_PhysicalDisk>::map<std::wstring,mismpstorage::SPACES_PhysicalDisk>(void)
0x180064704  nop
0x180064705  lea     rcx, [rbp+320h+var_370]
0x180064709  call    ??0?$map@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UMaintenanceDisk@Facade@Wsp@@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UMaintenanceDisk@Facade@Wsp@@@std@@@2@@std@@QEAA@XZ; std::map<std::wstring,Wsp::Facade::MaintenanceDisk>::map<std::wstring,Wsp::Facade::MaintenanceDisk>(void)
0x18006470e  nop
0x18006470f  lea     rcx, [rbp+320h+var_270]; this
0x180064716  call    ??0MaintenanceModeStruct@Facade@Wsp@@QEAA@XZ; Wsp::Facade::MaintenanceModeStruct::MaintenanceModeStruct(void)
0x18006471b  nop
0x18006471c  xorps   xmm1, xmm1
0x18006471f  movdqu  xmmword ptr [rbp+320h+var_318], xmm1
0x180064724  mov     [rsp+420h+var_3A7], bl
0x180064728  mov     [rsp+420h+var_3A8], 1
0x18006472d  mov     rcx, r15
0x180064730  call    ?GetSubsystemType@StorageHealthFacade@Facade@Wsp@@QEBA?BW4WSP_SUBSYSTEM_TYPE@@XZ; Wsp::Facade::StorageHealthFacade::GetSubsystemType(void)
0x180064735  test    eax, eax
0x180064737  jz      loc_180066383
0x18006473d  mov     r8d, 0BB9h
0x180064743  mov     rdx, cs:qword_1801599A0
0x18006474a  lea     rcx, [rbp+320h+var_298]
0x180064751  call    ?load_string@cxl@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEAUHINSTANCE__@@I@Z; cxl::load_string(HINSTANCE__ *,uint)
0x180064756  nop
0x180064757  lea     rcx, [rbp+320h+var_298]
0x18006475e  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180064763  mov     rdx, rax; activity
0x180064766  mov     [rsp+420h+percentComplete], 1; percentComplete
0x18006476e  mov     rcx, [r12]; context
0x180064772  call    MI_Context_WriteProgress
0x180064777  xorps   xmm0, xmm0
0x18006477a  movups  [rbp+320h+var_158], xmm0
0x180064781  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x180064789  movdqu  [rbp+320h+var_148], xmm1
0x180064791  mov     word ptr [rbp+320h+var_158], bx
0x180064798  lea     rdx, [rbp+320h+var_158]
0x18006479f  lea     rcx, [rbp+320h+var_180]
0x1800647a6  call    ??0StringWriter@cxl@@QEAA@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::StringWriter::StringWriter(std::wstring &)
0x1800647ab  nop
0x1800647ac  mov     rcx, rax
0x1800647af  call    ??$Write@$0DH@@TextWriter@cxl@@QEAAAEAV01@AEAY0DH@$$CB_W@Z; cxl::TextWriter::Write<55>(wchar_t const (&)[55])
0x1800647b4  nop
0x1800647b5  lea     rdx, [rbp+320h+var_158]
0x1800647bc  lea     rcx, [rbp+320h+var_2B8]
0x1800647c0  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800647c5  nop
0x1800647c6  mov     eax, cs:dword_18014D6A8
0x1800647cc  cmp     eax, 4
0x1800647cf  jbe     short loc_18006480A
0x1800647d1  mov     edx, 4000h
0x1800647d6  lea     rcx, dword_18014D6A8
0x1800647dd  call    _tlgKeywordOn
0x1800647e2  test    al, al
0x1800647e4  jz      short loc_18006480A
0x1800647e6  lea     rcx, [rbp+320h+var_2B8]
0x1800647ea  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x1800647ef  mov     qword ptr [rsp+420h+var_3BC+4], rax
0x1800647f4  lea     rax, [rsp+420h+var_3BC+4]
0x1800647f9  mov     qword ptr [rsp+420h+percentComplete], rax
0x1800647fe  lea     rdx, word_18012D95A
0x180064805  call    ??$Write@U?$_tlgWrapSz@_W@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@_W@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<wchar_t> const &)
0x18006480a  call    ?Instance@TraceManager@cxl@@SAAEAV12@XZ; cxl::TraceManager::Instance(void)
0x18006480f  lea     rbx, [rax+78h]
0x180064813  lea     rdx, [rbp+320h+var_2B8]
0x180064817  mov     rcx, rbx
0x18006481a  call    ?WriteTo@?$CxlTraits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@cxl@@SAXAEAVTextWriter@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBUFormat@2@@Z; cxl::CxlTraits<std::wstring>::WriteTo(cxl::TextWriter &,std::wstring const &,cxl::Format const &)
0x18006481f  mov     rcx, rbx
0x180064822  call    ??$?6UENDL@cxl@@@TextWriter@cxl@@QEAAAEAV01@AEBUENDL@1@@Z; cxl::TextWriter::operator<<<cxl::ENDL>(cxl::ENDL const &)
0x180064827  nop
0x180064828  lea     rcx, [rbp+320h+var_2B8]
0x18006482c  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180064831  mov     rax, [rbp+320h+var_358]
0x180064835  mov     rdx, [rax]
0x180064838  mov     ebx, 1
0x18006483d  test    rdx, rdx
0x180064840  jz      short loc_180064854
0x180064842  mov     [rbp+320h+var_1D7], bl
0x180064848  lea     rcx, [rbp+320h+var_1F8]
0x18006484f  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x180064854  mov     rdx, [rdi]
0x180064857  xor     edi, edi
0x180064859  test    rdx, rdx
0x18006485c  jz      short loc_180064870
0x18006485e  mov     [rbp+320h+var_1D8], bl
0x180064864  lea     rcx, [rbp+320h+var_218]
0x18006486b  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x180064870  lea     rcx, [rbp+320h+var_2D8]
0x180064874  call    ?GetInstance@MiSpaceAdapter@Wsp@@SA?AV?$shared_ptr@VMiSpaceAdapter@Wsp@@@std@@XZ; Wsp::MiSpaceAdapter::GetInstance(void)
0x180064879  nop
0x18006487a  lea     rcx, [rbp+320h+var_270]
0x180064881  mov     qword ptr [rsp+420h+percentComplete], rcx
0x180064886  lea     r9, [rbp+320h+var_26C]
0x18006488d  mov     r8, r14
0x180064890  lea     rdx, [rbp+320h+var_2F8]
0x180064894  mov     rcx, [rax]
0x180064897  call    ?UnpackObjectId@MiSpaceAdapter@Wsp@@QEBA?BV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV34@PEAW4WSP_SUBSYSTEM_TYPE@@PEAW4WSP_OBJECT_TYPE@@@Z; Wsp::MiSpaceAdapter::UnpackObjectId(std::wstring const &,WSP_SUBSYSTEM_TYPE *,WSP_OBJECT_TYPE *)
0x18006489c  nop
0x18006489d  mov     rdx, rax
0x1800648a0  lea     rcx, [rbp+320h+var_138]
0x1800648a7  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x1800648ac  nop
0x1800648ad  lea     rcx, [rbp+320h+var_2F8]
0x1800648b1  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800648b6  nop
0x1800648b7  mov     rcx, [rbp+320h+var_2D0]; this
0x1800648bb  test    rcx, rcx
0x1800648be  jz      short loc_1800648C5
0x1800648c0  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800648c5  mov     rcx, r15
0x1800648c8  call    ?GetSubsystemType@StorageHealthFacade@Facade@Wsp@@QEBA?BW4WSP_SUBSYSTEM_TYPE@@XZ; Wsp::Facade::StorageHealthFacade::GetSubsystemType(void)
0x1800648cd  cmp     eax, [rbp+320h+var_26C]
0x1800648d3  jz      loc_18006498A
0x1800648d9  mov     edi, ebx
0x1800648db  lea     rdx, aSubsystemNotSu; "Subsystem not supported"
0x1800648e2  lea     rcx, [rbp+320h+var_2F8]
0x1800648e6  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x1800648eb  nop
0x1800648ec  mov     eax, cs:dword_18014D6A8
0x1800648f2  mov     ebx, 17Dh
0x1800648f7  cmp     eax, 2
0x1800648fa  jbe     short loc_180064952
0x1800648fc  lea     rcx, [rbp+320h+var_2F8]
0x180064900  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180064905  mov     qword ptr [rbp+320h+var_398], rax
0x180064909  mov     [rsp+420h+var_3A4], 1
0x180064911  mov     [rsp+420h+var_3C0], ebx
0x180064915  lea     rax, aWspFacadeStora_24; "Wsp::Facade::StorageHealthFacade::Enabl"...
0x18006491c  mov     [rbp+320h+var_390], rax
0x180064920  lea     rax, [rbp+320h+var_398]
0x180064924  mov     [rsp+420h+var_3E8], rax
0x180064929  lea     rax, [rsp+420h+var_3A4]
0x18006492e  mov     [rsp+420h+var_3F0], rax
0x180064933  lea     rax, [rsp+420h+var_3C0]
0x180064938  mov     qword ptr [rsp+420h+secondsRemaining], rax
0x18006493d  lea     rax, [rbp+320h+var_390]
0x180064941  mov     qword ptr [rsp+420h+percentComplete], rax
0x180064946  lea     rdx, dword_18012D8A4
0x18006494d  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@U?$_tlgWrapSz@_W@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4AEBU?$_tlgWrapSz@_W@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<wchar_t> const &)
0x180064952  call    ?Instance@TraceManager@cxl@@SAAEAV12@XZ; cxl::TraceManager::Instance(void)
0x180064957  lea     rcx, [rax+28h]; struct cxl::TextWriter *
0x18006495b  mov     [rsp+420h+var_3C0], 1
0x180064963  mov     [rsp+420h+var_3A4], ebx
0x180064967  lea     rax, [rsp+420h+var_3C0]
0x18006496c  mov     qword ptr [rsp+420h+percentComplete], rax; __int64
0x180064971  lea     r9, [rsp+420h+var_3A4]
0x180064976  call    ??$WriteLine@_W$$BY0DE@DHH$$BY0BI@_W@TextWriter@cxl@@QEAAXPEB_WAEAY0DE@$$CBDAEBH2AEAY0BI@$$CB_W@Z; cxl::TextWriter::WriteLine<wchar_t,char [52],int,int,wchar_t [24]>(wchar_t const *,char const (&)[52],int const &,int const &,wchar_t const (&)[24])
0x18006497b  nop
0x18006497c  lea     rcx, [rbp+320h+var_2F8]
0x180064980  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180064985  jmp     loc_18006614B
0x18006498a  mov     eax, [rbp+320h+var_270]
0x180064990  cmp     eax, 0Ch
0x180064993  ja      loc_180066149
0x180064999  mov     ecx, 1220h
0x18006499e  bt      ecx, eax
0x1800649a1  jnb     loc_180066149
0x1800649a7  lea     rdx, [rbp+320h+var_2D8]
0x1800649ab  call    ?GetSmApiSession@StorageHealthFacade@Facade@Wsp@@AEAA?AV?$shared_ptr@VMiSession@mi@@@std@@XZ; Wsp::Facade::StorageHealthFacade::GetSmApiSession(void)
0x1800649b0  mov     rdx, rax
0x1800649b3  lea     rcx, [rbp+320h+var_268]
0x1800649ba  call    ??4?$shared_ptr@$$CBVSPACES_VirtualDisk@mismpstorage@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<mismpstorage::SPACES_VirtualDisk const>::operator=(std::shared_ptr<mismpstorage::SPACES_VirtualDisk const> &&)
0x1800649bf  mov     rcx, [rbp+320h+var_2D0]; this
0x1800649c3  test    rcx, rcx
0x1800649c6  jz      short loc_1800649CD
0x1800649c8  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800649cd  lea     rcx, [rbp+320h+var_2D8]
0x1800649d1  call    ?GetInstance@DataStore@ClusWmi@@SA?AV?$shared_ptr@VDataStore@ClusWmi@@@std@@XZ; ClusWmi::DataStore::GetInstance(void)
0x1800649d6  nop
0x1800649d7  lea     rdx, [rbp+320h+var_318]
0x1800649db  mov     rcx, [rax]; struct ProtectedPwd *
0x1800649de  call    ?GetCluster@DataStore@ClusWmi@@QEAAJPEAV?$shared_ptr@UICluster@ClusApi@@@std@@@Z; ClusWmi::DataStore::GetCluster(std::shared_ptr<ClusApi::ICluster> *)
0x1800649e3  mov     ebx, eax
0x1800649e5  mov     rcx, [rbp+320h+var_2D0]; this
0x1800649e9  test    rcx, rcx
0x1800649ec  jz      short loc_1800649F3
0x1800649ee  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800649f3  test    ebx, ebx
0x1800649f5  jns     loc_180064B8E
0x1800649fb  mov     [rsp+420h+var_3A4], ebx
0x1800649ff  mov     ecx, cs:dword_18014D6A8
0x180064a05  mov     edi, 194h
0x180064a0a  cmp     ecx, 2
0x180064a0d  jbe     short loc_180064A51
0x180064a0f  mov     eax, [rsp+420h+var_3A4]
0x180064a13  mov     [rsp+420h+var_3C0], eax
0x180064a17  mov     dword ptr [rsp+420h+var_3BC], edi
0x180064a1b  lea     r14, aWspFacadeStora_24; "Wsp::Facade::StorageHealthFacade::Enabl"...
0x180064a22  mov     qword ptr [rbp+320h+var_398], r14
0x180064a26  lea     rax, [rsp+420h+var_3C0]
0x180064a2b  mov     [rsp+420h+var_3F0], rax
0x180064a30  lea     rax, [rsp+420h+var_3BC]
0x180064a35  mov     qword ptr [rsp+420h+secondsRemaining], rax
0x180064a3a  lea     rax, [rbp+320h+var_398]
0x180064a3e  mov     qword ptr [rsp+420h+percentComplete], rax
0x180064a43  lea     rdx, byte_18012D8E3
0x180064a4a  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180064a4f  jmp     short loc_180064A58
0x180064a51  lea     r14, aWspFacadeStora_24; "Wsp::Facade::StorageHealthFacade::Enabl"...
0x180064a58  call    ?Instance@TraceManager@cxl@@SAAEAV12@XZ; cxl::TraceManager::Instance(void)
0x180064a5d  lea     rcx, [rax+28h]; struct cxl::TextWriter *
0x180064a61  mov     dword ptr [rsp+420h+var_3BC], edi
0x180064a65  lea     rax, [rsp+420h+var_3A4]
0x180064a6a  mov     qword ptr [rsp+420h+percentComplete], rax; __int64
0x180064a6f  lea     r9, [rsp+420h+var_3BC]
0x180064a74  mov     r8, r14
0x180064a77  call    ??$WriteLine@_W$$BY0DE@DHJ@TextWriter@cxl@@QEAAXPEB_WAEAY0DE@$$CBDAEBHAEBJ@Z; cxl::TextWriter::WriteLine<wchar_t,char [52],int,long>(wchar_t const *,char const (&)[52],int const &,long const &)
0x180064a7c  mov     ecx, ebx
0x180064a7e  call    ?SmRCFromHResult@MiSpaceAdapter@Wsp@@SA?AW4SM_RETURN_CODE@@J@Z; Wsp::MiSpaceAdapter::SmRCFromHResult(long)
0x180064a83  mov     edi, eax
0x180064a85  lea     rdx, aFailedToGetClu; "Failed to Get Cluster"
0x180064a8c  lea     rcx, [rbp+320h+var_2B8]
0x180064a90  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x180064a95  nop
0x180064a96  xor     esi, esi
0x180064a98  test    edi, edi
0x180064a9a  jz      loc_180064B25
0x180064aa0  mov     ecx, cs:dword_18014D6A8
0x180064aa6  cmp     ecx, 2
0x180064aa9  jbe     short loc_180064AFA
0x180064aab  lea     rcx, [rbp+320h+var_2B8]
0x180064aaf  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180064ab4  mov     qword ptr [rbp+320h+var_398], rax
0x180064ab8  mov     dword ptr [rsp+420h+var_3BC], edi
0x180064abc  mov     [rsp+420h+var_3C0], 195h
0x180064ac4  mov     [rbp+320h+var_390], r14
0x180064ac8  lea     rax, [rbp+320h+var_398]
0x180064acc  mov     [rsp+420h+var_3E8], rax
0x180064ad1  lea     rax, [rsp+420h+var_3BC]
0x180064ad6  mov     [rsp+420h+var_3F0], rax
0x180064adb  lea     rax, [rsp+420h+var_3C0]
0x180064ae0  mov     qword ptr [rsp+420h+secondsRemaining], rax
0x180064ae5  lea     rax, [rbp+320h+var_390]
0x180064ae9  mov     qword ptr [rsp+420h+percentComplete], rax
0x180064aee  lea     rdx, byte_18012D91B
0x180064af5  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@U?$_tlgWrapSz@_W@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4AEBU?$_tlgWrapSz@_W@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<wchar_t> const &)
0x180064afa  call    ?Instance@TraceManager@cxl@@SAAEAV12@XZ; cxl::TraceManager::Instance(void)
0x180064aff  lea     rcx, [rax+28h]; struct cxl::TextWriter *
0x180064b03  mov     dword ptr [rsp+420h+var_3BC], edi
0x180064b07  mov     [rsp+420h+var_3C0], 195h
0x180064b0f  lea     rax, [rsp+420h+var_3BC]
0x180064b14  mov     qword ptr [rsp+420h+percentComplete], rax; __int64
0x180064b19  lea     r9, [rsp+420h+var_3C0]
0x180064b1e  call    ??$WriteLine@_W$$BY0DE@DHH$$BY0BG@_W@TextWriter@cxl@@QEAAXPEB_WAEAY0DE@$$CBDAEBH2AEAY0BG@$$CB_W@Z; cxl::TextWriter::WriteLine<wchar_t,char [52],int,int,wchar_t [22]>(wchar_t const *,char const (&)[52],int const &,int const &,wchar_t const (&)[22])
0x180064b23  jmp     short loc_180064B80
0x180064b25  mov     eax, cs:dword_18014D6A8
0x180064b2b  cmp     eax, 5
0x180064b2e  jbe     short loc_180064B80
0x180064b30  lea     rcx, [rbp+320h+var_2B8]
0x180064b34  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180064b39  mov     qword ptr [rbp+320h+var_398], rax
  ... truncated ...
```
