# Wsp::Facade::StorageHealthFacade::EnableMaintenance(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,std::unique_ptr<bool,std::default_delete<bool>> const &,std::unique_ptr<bool,std::default_delete<bool>> const &,std::unique_ptr<uint,std::default_delete<uint>> &,std::unique_ptr<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,std::default_delete<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>>> const &,std::unique_ptr<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,std::default_delete<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>>> const &,std::unique_ptr<ushort,std::default_delete<ushort>> &,mi::MiContext &,std::shared_ptr<Wsp::Facade::IExtendedStatus> &)

- ea: `0x180062e00`
- end: `0x180064bc5`
- name: `?EnableMaintenance@StorageHealthFacade@Facade@Wsp@@QEAA?AW4SM_RETURN_CODE@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV?$unique_ptr@_NU?$default_delete@_N@std@@@6@1AEAV?$unique_ptr@IU?$default_delete@I@std@@@6@AEBV?$unique_ptr@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$default_delete@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@6@3AEAV?$unique_ptr@GU?$default_delete@G@std@@@6@AEAVMiContext@mi@@AEAV?$shared_ptr@UIExtendedStatus@Facade@Wsp@@@6@@Z`
- size: `7621`
- prototype: `__int64 __fastcall(int, int, int, int, __int64, __int64, __int64, __int64, __int64, MI_Uint32)`
- caller_count: `1`
- callee_count: `82`
- tags: `registry_config, installer_update, broker_com_uri`

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
- `0x180052350`
- `0x180052374`
- `0x180053624`
- `0x180053698`
- `0x180057860`
- `0x180057898`
- `0x180057c18`
- `0x1800589e4`
- `0x180059658`
- `0x1800596bc`
- `0x180059720`
- `0x180059784`
- `0x1800597e8`
- `0x18005984c`
- `0x1800598b0`
- `0x180059914`
- `0x180059978`
- `0x1800599dc`
- `0x180059b08`
- `0x180059b64`
- `0x180059bc8`
- `0x180059c2c`
- `0x180059cec`

## string_xrefs

- `0x180064970`: `Completed`
- `0x1800635cf`: `FindWriteCacheDisks`
- `0x1800641cd`: `Waiting for SBL cache state`
- `0x1800640fe`: `Change SBL cache`
- `0x1800643ec`: `Rollback waiting for SBL cache state`
- `0x1800642b4`: `Rollback change SBL cache`
- `0x180063c4b`: `Rollback `
- `0x180063d0e`: `Rollback `
- `0x1800647ac`: `Rollback `
- `0x180064877`: `Rollback `

## pseudocode

```c
// Hidden C++ exception states: #wind=36
__int64 __fastcall Wsp::Facade::StorageHealthFacade::EnableMaintenance(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        _QWORD *a5,
        __int64 *a6,
        const char *a7,
        void **a8,
        MI_Context **a9,
        __int64 a10)
{
  MI_Context **v12; // r12
  const MI_Char *v13; // rax
  const MI_Char *v14; // r8
  const MI_Char *v15; // r9
  __int64 v16; // rax
  __int64 v17; // rcx
  __int64 v18; // r8
  __int64 v19; // r9
  char *v20; // rbx
  __int64 v21; // rdx
  __int64 v22; // rdx
  _QWORD *Instance; // rax
  __int64 v24; // rax
  int SubsystemType; // eax
  MI_Uint32 FaultDomainPhysicalDisks; // edi
  __int64 v27; // rcx
  __int64 v28; // r8
  __int64 v29; // r9
  struct cxl::TraceManager *v30; // rax
  __int64 v31; // rdx
  __int64 v32; // r8
  int v33; // ecx
  __int64 SmApiSession; // rax
  struct ProtectedPwd **v35; // rax
  signed int Cluster; // ebx
  __int64 v37; // r8
  __int64 v38; // r9
  struct cxl::TraceManager *v39; // rax
  __int64 v40; // rcx
  __int64 v41; // r8
  __int64 v42; // r9
  struct cxl::TraceManager *v43; // rax
  __int64 v44; // rdx
  __int64 v45; // r8
  __int64 v46; // rcx
  __int64 v47; // r8
  __int64 v48; // r9
  _BYTE *v49; // rcx
  __int64 v50; // rax
  std::_Ref_count_base *v51; // rcx
  __int64 v52; // rcx
  __int64 v53; // rbx
  const wchar_t *v54; // rax
  Wsp::Facade::StorageHealthFacade *v55; // rcx
  __int64 *v56; // rax
  const wchar_t *v57; // rax
  Wsp::Facade::StorageHealthFacade *v58; // rcx
  void **v59; // rax
  const MI_Char *v60; // rax
  const MI_Char *v61; // r8
  const MI_Char *v62; // r9
  __int64 v63; // rcx
  __int64 v64; // r8
  __int64 v65; // r9
  struct cxl::TraceManager *v66; // rax
  __int64 v67; // rdx
  __int64 v68; // r8
  const MI_Char *v69; // rax
  const MI_Char *v70; // r8
  const MI_Char *v71; // r9
  int v72; // ecx
  int v73; // r9d
  __int64 v74; // rcx
  __int64 v75; // r8
  __int64 v76; // r9
  struct cxl::TraceManager *v77; // rax
  __int64 v78; // rdx
  __int64 v79; // r8
  const MI_Char *v80; // rax
  const MI_Char *v81; // r8
  const MI_Char *v82; // r9
  __int64 v83; // rcx
  __int64 v84; // rcx
  __int64 v85; // r8
  __int64 v86; // r9
  struct cxl::TraceManager *v87; // rax
  __int64 v88; // rdx
  __int64 v89; // r8
  const MI_Char *v90; // rax
  const MI_Char *v91; // r8
  const MI_Char *v92; // r9
  __int64 v93; // rcx
  __int64 v94; // r8
  __int64 v95; // r9
  struct cxl::TraceManager *v96; // rax
  const MI_Char *v97; // rax
  const MI_Char *v98; // r8
  const MI_Char *v99; // r9
  __int64 v100; // rcx
  __int64 v101; // rcx
  __int64 v102; // r8
  __int64 v103; // r9
  struct cxl::TraceManager *v104; // rax
  __int64 v105; // rdx
  __int64 v106; // r8
  const MI_Char *v107; // rax
  const MI_Char *v108; // r8
  const MI_Char *v109; // r9
  const MI_Char *v110; // rax
  const MI_Char *v111; // r8
  const MI_Char *v112; // r9
  __int64 v113; // rcx
  __int64 v114; // r8
  __int64 v115; // r9
  struct cxl::TextWriter *v116; // rbx
  __int64 v117; // rax
  __int64 v118; // rcx
  __int64 v119; // r8
  __int64 v120; // r9
  __int64 v121; // rcx
  _QWORD *v122; // rbx
  __int64 v123; // rsi
  __int64 v124; // r14
  int v125; // r15d
  __int64 v126; // rax
  __int64 v127; // rax
  __int64 v128; // rcx
  __int64 v129; // r8
  __int64 v130; // r9
  struct cxl::TextWriter *v131; // rbx
  __int64 v132; // rax
  __int64 v133; // rax
  __int64 v134; // rax
  __int64 i; // rsi
  __int64 v136; // r14
  __int64 v137; // rax
  __int64 v138; // rcx
  __int64 v139; // r8
  __int64 v140; // r9
  struct cxl::TextWriter *v141; // rbx
  __int64 v142; // rax
  __int64 value; // rax
  int v144; // edx
  __int64 v145; // rcx
  __int64 v146; // r8
  __int64 v147; // r9
  __int64 v148; // rax
  const MI_Char *v149; // rax
  const MI_Char *v150; // r8
  const MI_Char *v151; // r9
  int v152; // ecx
  __int64 v153; // rcx
  __int64 v154; // r8
  __int64 v155; // r9
  struct cxl::TraceManager *v156; // rax
  __int64 v157; // rcx
  __int64 v158; // r8
  __int64 v159; // r9
  struct cxl::TraceManager *v160; // rax
  __int64 v161; // rdx
  __int64 v162; // r8
  __int64 v163; // rcx
  __int64 v164; // rcx
  __int64 v165; // r8
  __int64 v166; // r9
  struct cxl::TraceManager *v167; // rax
  __int64 v168; // rdx
  __int64 v169; // r8
  int v170; // ecx
  int v171; // ebx
  __int64 v172; // rcx
  __int64 v173; // r8
  __int64 v174; // r9
  struct cxl::TraceManager *v175; // rax
  __int64 v176; // rdx
  __int64 v177; // r8
  __int64 v178; // rcx
  __int64 v179; // r8
  __int64 v180; // r9
  bool v181; // si
  int v182; // r9d
  int DiskCacheState; // ebx
  __int64 v184; // rcx
  __int64 v185; // r8
  __int64 v186; // r9
  struct cxl::TraceManager *v187; // rax
  __int64 v188; // rcx
  __int64 v189; // r8
  __int64 v190; // r9
  _BOOL8 v191; // rcx
  int v192; // ebx
  __int64 v193; // rcx
  __int64 v194; // r8
  __int64 v195; // r9
  struct cxl::TraceManager *v196; // rax
  __int64 v197; // rcx
  __int64 v198; // r8
  __int64 v199; // r9
  struct cxl::TraceManager *v200; // rax
  int v201; // edx
  __int64 v202; // rcx
  __int64 v203; // r8
  __int64 v204; // r9
  int v205; // esi
  __int64 v206; // rax
  __int64 v207; // rax
  __int64 v208; // rcx
  __int64 v209; // r8
  __int64 v210; // r9
  struct cxl::TextWriter *v211; // rbx
  __int64 v212; // rax
  __int64 v213; // rax
  __int64 v214; // rax
  int v215; // edx
  __int64 v216; // rcx
  __int64 v217; // r8
  __int64 v218; // r9
  const MI_Char *v219; // rax
  const MI_Char *v220; // r8
  const MI_Char *v221; // r9
  __int64 v222; // rcx
  __int64 v223; // r8
  __int64 v224; // r9
  struct cxl::TraceManager *v225; // rax
  __int64 v226; // rdx
  __int64 v227; // r8
  __int64 v228; // rcx
  __int64 v229; // r8
  __int64 v230; // r9
  __int64 v231; // rcx
  __int64 v232; // r8
  __int64 v233; // r9
  __int64 v235; // rax
  __int64 v236; // rax
  MI_Uint32 *secondsRemaining; // [rsp+28h] [rbp-D8h]
  _DWORD *secondsRemaininga; // [rsp+28h] [rbp-D8h]
  MI_Uint32 secondsRemainingb; // [rsp+28h] [rbp-D8h]
  MI_Uint32 v240; // [rsp+60h] [rbp-A0h] BYREF
  _DWORD v241[3]; // [rsp+64h] [rbp-9Ch] BYREF
  __int64 v242; // [rsp+70h] [rbp-90h] BYREF
  char v243; // [rsp+78h] [rbp-88h] BYREF
  _BYTE v244[3]; // [rsp+79h] [rbp-87h] BYREF
  MI_Uint32 v245; // [rsp+7Ch] [rbp-84h] BYREF
  const char *v246; // [rsp+80h] [rbp-80h] BYREF
  MI_Uint32 v247[2]; // [rsp+88h] [rbp-78h] BYREF
  const char *v248; // [rsp+90h] [rbp-70h] BYREF
  const char *v249; // [rsp+98h] [rbp-68h] BYREF
  __int16 v250; // [rsp+A0h] [rbp-60h] BYREF
  _QWORD *v251; // [rsp+A8h] [rbp-58h]
  const char **v252[2]; // [rsp+B0h] [rbp-50h] BYREF
  int v253; // [rsp+C0h] [rbp-40h] BYREF
  __int64 *v254; // [rsp+C8h] [rbp-38h]
  _QWORD *v255; // [rsp+D0h] [rbp-30h]
  __int128 v256; // [rsp+D8h] [rbp-28h] BYREF
  __int64 v257; // [rsp+E8h] [rbp-18h]
  __int128 v258; // [rsp+F0h] [rbp-10h] BYREF
  __int64 v259; // [rsp+100h] [rbp+0h]
  std::_Ref_count_base *v260[2]; // [rsp+108h] [rbp+8h] BYREF
  _BYTE v261[16]; // [rsp+118h] [rbp+18h] BYREF
  _BYTE v262[32]; // [rsp+128h] [rbp+28h] BYREF
  const char *v263; // [rsp+148h] [rbp+48h] BYREF
  std::_Ref_count_base *v264; // [rsp+150h] [rbp+50h]
  _QWORD v265[4]; // [rsp+168h] [rbp+68h] BYREF
  _BYTE v266[40]; // [rsp+188h] [rbp+88h] BYREF
  unsigned int v267; // [rsp+1B0h] [rbp+B0h] BYREF
  int v268; // [rsp+1B4h] [rbp+B4h] BYREF
  _QWORD v269[10]; // [rsp+1B8h] [rbp+B8h] BYREF
  _BYTE v270[32]; // [rsp+208h] [rbp+108h] BYREF
  _BYTE v271[35]; // [rsp+228h] [rbp+128h] BYREF
  char v272; // [rsp+24Bh] [rbp+14Bh] BYREF
  int v273; // [rsp+24Ch] [rbp+14Ch]
  _BYTE v274[16]; // [rsp+250h] [rbp+150h] BYREF
  _BYTE v275[64]; // [rsp+260h] [rbp+160h] BYREF
  _BYTE v276[8]; // [rsp+2A0h] [rbp+1A0h] BYREF
  _BYTE v277[32]; // [rsp+2A8h] [rbp+1A8h] BYREF
  _OWORD v278[2]; // [rsp+2C8h] [rbp+1C8h] BYREF
  _OWORD v279[2]; // [rsp+2E8h] [rbp+1E8h] BYREF
  _BYTE v280[8]; // [rsp+308h] [rbp+208h] BYREF
  _BYTE v281[32]; // [rsp+310h] [rbp+210h] BYREF
  _BYTE v282[8]; // [rsp+330h] [rbp+230h] BYREF
  _BYTE v283[40]; // [rsp+338h] [rbp+238h] BYREF
  void **pExceptionObject; // [rsp+360h] [rbp+260h] BYREF
  _BYTE v285[104]; // [rsp+368h] [rbp+268h] BYREF

  *(_QWORD *)v247 = a4;
  v251 = (_QWORD *)a3;
  v255 = a5;
  v248 = a7;
  v254 = a6;
  v12 = a9;
  v249 = (const char *)a9;
  if ( (unsigned int)dword_18014B6A8 > 5 )
  {
    v245 = 326;
    *(_QWORD *)&v241[1] = "Wsp::Facade::StorageHealthFacade::EnableMaintenance";
    secondsRemaining = &v245;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      (__int64)"Wsp::Facade::StorageHealthFacade::EnableMaintenance",
      (__int64)word_18012B972,
      a3,
      a4,
      &v241[1]);
  }
  v279[0] = 0;
  v279[1] = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v279[0]) = 0;
  v258 = 0;
  v259 = 0;
  v256 = 0;
  v257 = 0;
  v253 = -1;
  v250 = 1;
  std::map<std::wstring,mismpstorage::SPACES_PhysicalDisk>::map<std::wstring,mismpstorage::SPACES_PhysicalDisk>(v261);
  std::map<std::wstring,Wsp::Facade::MaintenanceDisk>::map<std::wstring,Wsp::Facade::MaintenanceDisk>(v252);
  Wsp::Facade::MaintenanceModeStruct::MaintenanceModeStruct((Wsp::Facade::MaintenanceModeStruct *)&v267);
  *(_OWORD *)v260 = 0;
  v244[0] = 0;
  v243 = 1;
  if ( !(unsigned int)Wsp::Facade::StorageHealthFacade::GetSubsystemType(a1) )
  {
    v235 = std::wstring::wstring(v276, L"non highlyavailable subsystems are not supported");
    v236 = cxl::SMResult(&v249, 59001, v235);
    cxl::Error(&pExceptionObject, v236);
    throw (cxl::Exception *)&pExceptionObject;
  }
  cxl::load_string(v266, qword_1801578A0, 3001);
  v13 = (const MI_Char *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v266);
  MI_Context_WriteProgress(*a9, v13, v14, v15, 1u, (MI_Uint32)secondsRemaining);
  v278[0] = 0;
  v278[1] = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v278[0]) = 0;
  v16 = cxl::StringWriter::StringWriter(v276, v278);
  cxl::TextWriter::Write<55>(v16);
  std::wstring::wstring(v265, v278);
  if ( (unsigned int)dword_18014B6A8 > 4 && (unsigned __int8)tlgKeywordOn(&dword_18014B6A8, 0x4000) )
  {
    *(_QWORD *)&v241[1] = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v265);
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>>(
      v17,
      (__int64)byte_18012B913,
      v18,
      v19,
      &v241[1]);
  }
  v20 = (char *)cxl::TraceManager::Instance() + 120;
  cxl::CxlTraits<std::wstring>::WriteTo(v20, v265);
  cxl::TextWriter::operator<<<cxl::ENDL>((__int64)v20);
  std::wstring::_Tidy_deallocate(v265);
  v21 = *v254;
  if ( *v254 )
  {
    v271[33] = 1;
    std::wstring::operator=(v271, v21);
  }
  v22 = *(_QWORD *)a7;
  if ( *(_QWORD *)a7 )
  {
    v271[32] = 1;
    std::wstring::operator=(v270, v22);
  }
  Instance = (_QWORD *)Wsp::MiSpaceAdapter::GetInstance(&v263);
  v24 = Wsp::MiSpaceAdapter::UnpackObjectId(*Instance, (unsigned int)v262, a2, (unsigned int)&v268, (__int64)&v267);
  std::wstring::operator=(v279, v24);
  std::wstring::_Tidy_deallocate(v262);
  if ( v264 )
    std::_Ref_count_base::_Decref(v264);
  SubsystemType = Wsp::Facade::StorageHealthFacade::GetSubsystemType(a1);
  if ( SubsystemType != v268 )
  {
    FaultDomainPhysicalDisks = 1;
    std::wstring::wstring(v262, L"Subsystem not supported");
    if ( (unsigned int)dword_18014B6A8 > 2 )
    {
      *(_QWORD *)v247 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v262);
      v245 = 1;
      v240 = 381;
      v248 = "Wsp::Facade::StorageHealthFacade::EnableMaintenance";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>>(
        v27,
        (__int64)byte_18012B933,
        v28,
        v29,
        &v248,
        (__int64)&v240,
        (__int64)&v245,
        v247);
    }
    v30 = cxl::TraceManager::Instance();
    v240 = 1;
    v245 = 381;
    cxl::TextWriter::WriteLine<wchar_t,char [52],int,int,wchar_t [24]>(
      (struct cxl::TraceManager *)((char *)v30 + 40),
      v31,
      v32,
      (__int64)&v245,
      (__int64)&v240);
    std::wstring::_Tidy_deallocate(v262);
    goto LABEL_152;
  }
  if ( v267 > 0xC || (v33 = 4640, !_bittest(&v33, v267)) )
  {
    FaultDomainPhysicalDisks = 1;
    goto LABEL_152;
  }
  SmApiSession = Wsp::Facade::StorageHealthFacade::GetSmApiSession(4640, &v263);
  std::shared_ptr<mismpstorage::SPACES_VirtualDisk const>::operator=(v269, SmApiSession);
  if ( v264 )
    std::_Ref_count_base::_Decref(v264);
  v35 = (struct ProtectedPwd **)ClusWmi::DataStore::GetInstance(&v263);
  Cluster = ClusWmi::DataStore::GetCluster(*v35);
  if ( v264 )
    std::_Ref_count_base::_Decref(v264);
  if ( Cluster < 0 )
  {
    v245 = Cluster;
    if ( (unsigned int)dword_18014B6A8 > 2 )
    {
      v240 = v245;
      v241[0] = 404;
      *(_QWORD *)v247 = "Wsp::Facade::StorageHealthFacade::EnableMaintenance";
      secondsRemaininga = v241;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        (unsigned int)dword_18014B6A8,
        (__int64)byte_18012B85B,
        v37,
        v38,
        v247);
    }
    v39 = cxl::TraceManager::Instance();
    v241[0] = 404;
    cxl::TextWriter::WriteLine<wchar_t,char [52],int,long>(
      (struct cxl::TraceManager *)((char *)v39 + 40),
      (__int64)&v245);
    FaultDomainPhysicalDisks = Wsp::MiSpaceAdapter::SmRCFromHResult((unsigned int)Cluster);
    std::wstring::wstring(v265, L"Failed to Get Cluster");
    if ( FaultDomainPhysicalDisks )
    {
      if ( (unsigned int)dword_18014B6A8 > 2 )
      {
        *(_QWORD *)v247 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v265);
        v241[0] = FaultDomainPhysicalDisks;
        v240 = 405;
        v248 = "Wsp::Facade::StorageHealthFacade::EnableMaintenance";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>>(
          v40,
          (__int64)byte_18012B893,
          v41,
          v42,
          &v248,
          (__int64)&v240,
          (__int64)v241,
          v247);
      }
      v43 = cxl::TraceManager::Instance();
      v241[0] = FaultDomainPhysicalDisks;
      v240 = 405;
      cxl::TextWriter::WriteLine<wchar_t,char [52],int,int,wchar_t [22]>(
        (struct cxl::TraceManager *)((char *)v43 + 40),
        v44,
        v45,
        (__int64)&v240,
        (__int64)v241);
    }
    else if ( (unsigned int)dword_18014B6A8 > 5 )
    {
      *(_QWORD *)v247 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v265);
      v241[0] = 0;
      v240 = 405;
      v248 = "Wsp::Facade::StorageHealthFacade::EnableMaintenance";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>>(
        v46,
        (__int64)word_18012B8D2,
        v47,
        v48,
        &v248,
        (__int64)&v240,
        (__int64)v241,
        v247);
    }
    v49 = v265;
    goto LABEL_33;
  }
  v50 = ClusApi::Facade::FacadeFactory::CreateClusterFacade(&v263, v260);
  std::shared_ptr<mismpstorage::SPACES_VirtualDisk const>::operator=(v274, v50);
  v51 = v264;
  if ( v264 )
    std::_Ref_count_base::_Decref(v264);
  Wsp::Facade::StorageHealthFacade::GetLocalNode(v51, &v267);
  Wsp::Facade::StorageHealthFacade::S2DEnabled(v52, &v267);
  v53 = (__int64)v255;
  if ( !*v255 )
  {
    if ( v272 )
    {
      v54 = (const wchar_t *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(qword_180157940);
      Wsp::Facade::StorageHealthFacade::GetMaintenanceModeConfiguration(
        v55,
        v54,
        (void (*)(const wchar_t *, const wchar_t *, void *))Wsp::Facade::_MaintenanceModeTimeoutConfigurationCallback,
        &v253);
      v56 = std::make_unique<unsigned int,unsigned int &,0>(&v241[1], &v253);
      std::unique_ptr<unsigned int>::operator=<std::default_delete<unsigned int>,0>(v53, v56);
      std::unique_ptr<unsigned int>::~unique_ptr<unsigned int>(&v241[1]);
    }
    else
    {
      std::unique_ptr<unsigned int>::reset(v255, 0);
    }
  }
  if ( !*a8 )
  {
    v57 = (const wchar_t *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(qword_180157960);
    Wsp::Facade::StorageHealthFacade::GetMaintenanceModeConfiguration(
      v58,
      v57,
      (void (*)(const wchar_t *, const wchar_t *, void *))Wsp::Facade::_MaintenanceModeValidationLevelConfigurationCallback,
      &v250);
    v59 = (void **)std::make_unique<unsigned short,unsigned short &,0>(&v241[1], &v250);
    std::unique_ptr<unsigned short>::operator=<std::default_delete<unsigned short>,0>(a8, v59);
    std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&v241[1]);
  }
  v60 = (const MI_Char *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v266);
  MI_Context_WriteProgress(*a9, v60, v61, v62, 2u, (MI_Uint32)secondsRemaininga);
  LODWORD(secondsRemaininga) = a10;
  FaultDomainPhysicalDisks = Wsp::Facade::StorageHealthFacade::GetFaultDomainPhysicalDisks(
                               a1,
                               a2,
                               (unsigned int)&v267,
                               (unsigned int)v252,
                               (__int64)v261);
  if ( FaultDomainPhysicalDisks )
  {
    std::wstring::wstring(v262, L"GetFaultDomainPhysicalDisks");
    if ( (unsigned int)dword_18014B6A8 > 2 )
    {
      *(_QWORD *)v247 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v262);
      v241[0] = FaultDomainPhysicalDisks;
      v240 = 452;
      v248 = "Wsp::Facade::StorageHealthFacade::EnableMaintenance";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>>(
        v63,
        (__int64)byte_18012B7DD,
        v64,
        v65,
        &v248,
        (__int64)&v240,
        (__int64)v241,
        v247);
    }
    v66 = cxl::TraceManager::Instance();
    v241[0] = FaultDomainPhysicalDisks;
    v240 = 452;
    cxl::TextWriter::WriteLine<wchar_t,char [52],int,int,wchar_t [28]>(
      (struct cxl::TraceManager *)((char *)v66 + 40),
      v67,
      v68,
      (__int64)&v240,
      (__int64)v241,
      (__int64)L"GetFaultDomainPhysicalDisks");
LABEL_46:
    std::wstring::_Tidy_deallocate(v262);
    goto LABEL_152;
  }
  if ( v272 && v273 )
  {
    v69 = (const MI_Char *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v266);
    MI_Context_WriteProgress(*a9, v69, v70, v71, 3u, a10);
    FaultDomainPhysicalDisks = Wsp::Facade::StorageHealthFacade::FindWriteCacheDisks(v72, (__int64)&v267, v252, v73);
    if ( FaultDomainPhysicalDisks )
    {
      std::wstring::wstring(v262, L"FindWriteCacheDisks");
      if ( (unsigned int)dword_18014B6A8 > 2 )
      {
        *(_QWORD *)v247 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v262);
        v241[0] = FaultDomainPhysicalDisks;
        v240 = 470;
        v248 = "Wsp::Facade::StorageHealthFacade::EnableMaintenance";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>>(
          v74,
          (__int64)&dword_18012B81C,
          v75,
          v76,
          &v248,
          (__int64)&v240,
          (__int64)v241,
          v247);
      }
      v77 = cxl::TraceManager::Instance();
      v241[0] = FaultDomainPhysicalDisks;
      v240 = 470;
      cxl::TextWriter::WriteLine<wchar_t,char [52],int,int,wchar_t [20]>(
        (struct cxl::TraceManager *)((char *)v77 + 40),
        v78,
        v79,
        (__int64)&v240,
        (__int64)v241);
      goto LABEL_46;
    }
    v80 = (const MI_Char *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v266);
    MI_Context_WriteProgress(*a9, v80, v81, v82, 4u, (MI_Uint32)secondsRemaininga);
    FaultDomainPhysicalDisks = Wsp::Facade::StorageHealthFacade::ValidateFiltering(v83, &v267, v252);
    if ( FaultDomainPhysicalDisks )
    {
      std::wstring::wstring(v262, L"ValidateFiltering");
      if ( (unsigned int)dword_18014B6A8 > 2 )
      {
        *(_QWORD *)v247 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v262);
        v241[0] = FaultDomainPhysicalDisks;
        v240 = 487;
        v248 = "Wsp::Facade::StorageHealthFacade::EnableMaintenance";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>>(
          v84,
          (__int64)&byte_18012B75F,
          v85,
          v86,
          &v248,
          (__int64)&v240,
          (__int64)v241,
          v247);
      }
      v87 = cxl::TraceManager::Instance();
      v241[0] = FaultDomainPhysicalDisks;
      v240 = 487;
      cxl::TextWriter::WriteLine<wchar_t,char [52],int,int,wchar_t [18]>(
        (struct cxl::TraceManager *)((char *)v87 + 40),
        v88,
        v89,
        (__int64)&v240,
        (__int64)v241,
        (__int64)L"ValidateFiltering");
      goto LABEL_46;
    }
  }
  if ( *(_WORD *)*a8 )
  {
    if ( (*(_BYTE *)*a8 & 1) != 0 )
    {
      v90 = (const MI_Char *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v266);
      MI_Context_WriteProgress(*a9, v90, v91, v92, 5u, (MI_Uint32)secondsRemaininga);
      FaultDomainPhysicalDisks = Wsp::Facade::StorageHealthFacade::ValidateAllVirtualDiskHealthy(a1, &v267, v261, a10);
      if ( FaultDomainPhysicalDisks )
      {
        std::wstring::wstring(v262, L"ValidateAllVirtualDiskHealthy");
        if ( (unsigned int)dword_18014B6A8 > 2 )
        {
          *(_QWORD *)v247 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v262);
          v241[0] = FaultDomainPhysicalDisks;
          v240 = 509;
          v248 = "Wsp::Facade::StorageHealthFacade::EnableMaintenance";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>>(
            v93,
            (__int64)&word_18012B79E,
            v94,
            v95,
            &v248,
            (__int64)&v240,
            (__int64)v241,
            v247);
        }
        v96 = cxl::TraceManager::Instance();
        v241[0] = FaultDomainPhysicalDisks;
        v240 = 509;
        cxl::TextWriter::WriteLine<wchar_t,char [52],int,int,wchar_t [30]>(
          (struct cxl::TraceManager *)((char *)v96 + 40),
          (__int64)v241);
LABEL_63:
        v49 = v262;
LABEL_33:
        std::wstring::_Tidy_deallocate(v49);
        goto LABEL_152;
      }
    }
  }
  if ( v272 )
  {
    if ( v273 )
    {
      v97 = (const MI_Char *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v266);
      MI_Context_WriteProgress(*a9, v97, v98, v99, 6u, (MI_Uint32)secondsRemaininga);
      FaultDomainPhysicalDisks = Wsp::Facade::StorageHealthFacade::QueryBoundDevices(v100, &v267, v252, &v258);
      if ( FaultDomainPhysicalDisks )
      {
        std::wstring::wstring(v262, L"QueryBoundDevices");
        if ( (unsigned int)dword_18014B6A8 > 2 )
        {
          *(_QWORD *)v247 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v262);
          v241[0] = FaultDomainPhysicalDisks;
          v240 = 532;
          v248 = "Wsp::Facade::StorageHealthFacade::EnableMaintenance";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>>(
            v101,
            (__int64)byte_18012B6E1,
            v102,
            v103,
            &v248,
            (__int64)&v240,
            (__int64)v241,
            v247);
        }
        v104 = cxl::TraceManager::Instance();
        v241[0] = FaultDomainPhysicalDisks;
        v240 = 532;
        cxl::TextWriter::WriteLine<wchar_t,char [52],int,int,wchar_t [18]>(
          (struct cxl::TraceManager *)((char *)v104 + 40),
          v105,
          v106,
          (__int64)&v240,
          (__int64)v241,
          (__int64)L"QueryBoundDevices");
        goto LABEL_63;
      }
    }
  }
  v107 = (const MI_Char *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v266);
  MI_Context_WriteProgress(*a9, v107, v108, v109, 7u, (MI_Uint32)secondsRemaininga);
  std::shared_ptr<ClusApi::IStorage>::shared_ptr<ClusApi::IStorage>(&v263, v269);
  secondsRemainingb = v247[0];
  FaultDomainPhysicalDisks = Wsp::Facade::StorageHealthFacade::CallMaintenanceOnTargetObject(
                               &v272,
                               v275,
                               &v267,
                               &v243,
                               v251);
  v245 = FaultDomainPhysicalDisks;
  v110 = (const MI_Char *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v266);
  MI_Context_WriteProgress(*a9, v110, v111, v112, 8u, secondsRemainingb);
  std::operator+<wchar_t>(v265, L"Target ObjectID:", a2);
  if ( FaultDomainPhysicalDisks )
  {
    if ( (unsigned int)dword_18014B6A8 > 2 )
    {
      *(_QWORD *)&v241[1] = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v265);
      v241[0] = FaultDomainPhysicalDisks;
      v240 = 568;
      v242 = (__int64)"Wsp::Facade::StorageHealthFacade::EnableMaintenance";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>>(
        v113,
        (__int64)qword_18012B720,
        v114,
        v115,
        &v242,
        (__int64)&v240,
        (__int64)v241,
        &v241[1]);
    }
    v116 = (struct cxl::TraceManager *)((char *)cxl::TraceManager::Instance() + 40);
    v117 = std::operator+<wchar_t>(v262, L"Target ObjectID:", a2);
    v241[0] = FaultDomainPhysicalDisks;
    v240 = 568;
    cxl::TextWriter::WriteLine<wchar_t,char [52],int,int,std::wstring>(v116, (__int64)v241, v117);
    std::wstring::_Tidy_deallocate(v262);
  }
  else if ( (unsigned int)dword_18014B6A8 > 5 )
  {
    *(_QWORD *)&v241[1] = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v265);
    v241[0] = 0;
    v240 = 568;
    v242 = (__int64)"Wsp::Facade::StorageHealthFacade::EnableMaintenance";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>>(
      v118,
      (__int64)qword_18012B6A0,
      v119,
      v120,
      &v242,
      (__int64)&v240,
      (__int64)v241,
      &v241[1]);
  }
  std::wstring::_Tidy_deallocate(v265);
  if ( v272 )
  {
    if ( FaultDomainPhysicalDisks )
    {
      if ( !v273 )
        goto LABEL_152;
LABEL_79:
      v122 = v251;
      goto LABEL_80;
    }
    if ( !v273 )
      goto LABEL_152;
    v136 = *((_QWORD *)&v258 + 1);
    for ( i = v258; i != v136; i += 64 )
    {
      std::shared_ptr<ClusApi::IStorage>::shared_ptr<ClusApi::IStorage>(v265, v269);
      v241[0] = 5;
      LODWORD(secondsRemaininga) = v247[0];
      FaultDomainPhysicalDisks = Wsp::Facade::StorageHealthFacade::CallMaintenanceOnTargetObject(
                                   &v272,
                                   i,
                                   v241,
                                   &v243,
                                   v251);
      v245 = FaultDomainPhysicalDisks;
      v137 = mismpstorage::SPACES_StoragePool::ObjectId(i, v276);
      mismpstorage::read_property<std::wstring>::get_value(v137);
      std::wstring::_Tidy_deallocate(v277);
      if ( FaultDomainPhysicalDisks )
      {
        if ( (unsigned int)dword_18014B6A8 > 2 )
        {
          v246 = (const char *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v262);
          v241[0] = FaultDomainPhysicalDisks;
          v240 = 607;
          v263 = "Wsp::Facade::StorageHealthFacade::EnableMaintenance";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>>(
            v138,
            (__int64)byte_18012B661,
            v139,
            v140,
            &v263,
            (__int64)&v240,
            (__int64)v241,
            &v246);
        }
        v141 = (struct cxl::TraceManager *)((char *)cxl::TraceManager::Instance() + 40);
        v142 = mismpstorage::SPACES_StoragePool::ObjectId(i, v280);
        value = mismpstorage::read_property<std::wstring>::get_value(v142);
        LODWORD(v242) = FaultDomainPhysicalDisks;
        v241[1] = 607;
        cxl::TextWriter::WriteLine<wchar_t,char [52],int,int,std::wstring>(v141, (__int64)&v242, value);
        std::wstring::_Tidy_deallocate(&v263);
        std::wstring::_Tidy_deallocate(v281);
      }
      else if ( (unsigned int)dword_18014B6A8 > 5 )
      {
        v263 = (const char *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v262);
        v241[0] = v144;
        v240 = 607;
        v246 = "Wsp::Facade::StorageHealthFacade::EnableMaintenance";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>>(
          v145,
          (__int64)qword_18012B620,
          v146,
          v147,
          &v246,
          (__int64)&v240,
          (__int64)v241,
          &v263);
      }
      std::wstring::_Tidy_deallocate(v262);
      if ( FaultDomainPhysicalDisks )
        goto LABEL_79;
      v148 = mismpstorage::SPACES_PhysicalDisk::Clone(i, &pExceptionObject);
      std::vector<mismpstorage::SPACES_PhysicalDisk>::emplace_back<mismpstorage::SPACES_PhysicalDisk>(&v256, v148);
      pExceptionObject = &mismpstorage::mi_base::`vftable';
      mi::MiInstance::~MiInstance((mi::MiInstance *)v285);
    }
    v122 = v251;
    if ( *v251 && *(_BYTE *)*v251 )
    {
      v149 = (const MI_Char *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v266);
      MI_Context_WriteProgress(*a9, v149, v150, v151, 0x64u, (MI_Uint32)secondsRemaininga);
      goto LABEL_152;
    }
    v241[1] = 4;
    FaultDomainPhysicalDisks = Wsp::Facade::StorageHealthFacade::SetMaintenanceModeIntent(v121, v252, &v241[1]);
    v245 = FaultDomainPhysicalDisks;
    if ( FaultDomainPhysicalDisks )
    {
      std::wstring::wstring(v262, L"Set Starting Maintenance Mode Intent on Physical Disks");
      if ( (unsigned int)dword_18014B6A8 > 2 )
      {
        v263 = (const char *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v262);
        v241[1] = FaultDomainPhysicalDisks;
        LODWORD(v242) = 637;
        v246 = "Wsp::Facade::StorageHealthFacade::EnableMaintenance";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>>(
          v153,
          (__int64)word_18012B5A2,
          v154,
          v155,
          &v246,
          (__int64)&v242,
          (__int64)&v241[1],
          &v263);
      }
      v156 = cxl::TraceManager::Instance();
      v241[1] = FaultDomainPhysicalDisks;
      LODWORD(v242) = 637;
      cxl::TextWriter::WriteLine<wchar_t,char [52],int,int,wchar_t [55]>(
        (struct cxl::TraceManager *)((char *)v156 + 40),
        (__int64)&v241[1],
        (__int64)L"Set Starting Maintenance Mode Intent on Physical Disks");
LABEL_106:
      std::wstring::_Tidy_deallocate(v262);
LABEL_80:
      v243 = 0;
      if ( v272 )
      {
        if ( v273 )
        {
          v124 = *((_QWORD *)&v256 + 1);
          v123 = v256;
          if ( (_QWORD)v256 != *((_QWORD *)&v256 + 1) )
          {
            do
            {
              std::shared_ptr<ClusApi::IStorage>::shared_ptr<ClusApi::IStorage>(v265, v269);
              v241[1] = 5;
              v125 = Wsp::Facade::StorageHealthFacade::CallMaintenanceOnTargetObject(&v272, v123, &v241[1], &v243, v122);
              v126 = mismpstorage::SPACES_StoragePool::ObjectId(v123, v282);
              v127 = mismpstorage::read_property<std::wstring>::get_value(v126);
              std::operator+<wchar_t>(v262, L"Rollback ", v127);
              std::wstring::_Tidy_deallocate(v280);
              std::wstring::_Tidy_deallocate(v283);
              if ( v125 )
              {
                if ( (unsigned int)dword_18014B6A8 > 2 )
                {
                  v263 = (const char *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v262);
                  v241[1] = v125;
                  LODWORD(v242) = 736;
                  v246 = "Wsp::Facade::StorageHealthFacade::EnableMaintenance";
                  _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>>(
                    v128,
                    (__int64)&word_18012B426,
                    v129,
                    v130,
                    &v246,
                    (__int64)&v242,
                    (__int64)&v241[1],
                    &v263);
                }
                v131 = (struct cxl::TraceManager *)((char *)cxl::TraceManager::Instance() + 40);
                v132 = mismpstorage::SPACES_StoragePool::ObjectId(v123, &pExceptionObject);
                v133 = mismpstorage::read_property<std::wstring>::get_value(v132);
                v134 = std::operator+<wchar_t>(&v263, L"Rollback ", v133);
                v241[0] = v125;
                v240 = 736;
                cxl::TextWriter::WriteLine<wchar_t,char [52],int,int,std::wstring>(v131, (__int64)v241, v134);
                std::wstring::_Tidy_deallocate(&v263);
                std::wstring::_Tidy_deallocate(v276);
                std::wstring::_Tidy_deallocate(v285);
                v122 = v251;
              }
              else if ( (unsigned int)dword_18014B6A8 > 5 )
              {
                v263 = (const char *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v262);
                v241[1] = v201;
                LODWORD(v242) = 736;
                v246 = "Wsp::Facade::StorageHealthFacade::EnableMaintenance";
                _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>>(
                  v202,
                  (__int64)&word_18012B2A6,
                  v203,
                  v204,
                  &v246,
                  (__int64)&v242,
                  (__int64)&v241[1],
                  &v263);
              }
              std::wstring::_Tidy_deallocate(v262);
              v123 += 64;
            }
            while ( v123 != v124 );
            FaultDomainPhysicalDisks = v245;
            v12 = (MI_Context **)v249;
          }
        }
      }
      std::shared_ptr<ClusApi::IStorage>::shared_ptr<ClusApi::IStorage>(v265, v269);
      LODWORD(secondsRemaininga) = v247[0];
      v205 = Wsp::Facade::StorageHealthFacade::CallMaintenanceOnTargetObject(&v272, v275, &v267, &v243, v122);
      v206 = mismpstorage::SPACES_StoragePool::ObjectId(v275, &pExceptionObject);
      v207 = mismpstorage::read_property<std::wstring>::get_value(v206);
      std::operator+<wchar_t>(v262, L"Rollback ", v207);
      std::wstring::_Tidy_deallocate(v276);
      std::wstring::_Tidy_deallocate(v285);
      if ( v205 )
      {
        if ( (unsigned int)dword_18014B6A8 > 2 )
        {
          v249 = (const char *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v262);
          v241[1] = v205;
          LODWORD(v242) = 752;
          v263 = "Wsp::Facade::StorageHealthFacade::EnableMaintenance";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>>(
            v208,
            (__int64)&byte_18012B2E7,
            v209,
            v210,
            &v263,
            (__int64)&v242,
            (__int64)&v241[1],
            &v249);
        }
        v211 = (struct cxl::TraceManager *)((char *)cxl::TraceManager::Instance() + 40);
        v212 = mismpstorage::SPACES_StoragePool::ObjectId(v275, v282);
        v213 = mismpstorage::read_property<std::wstring>::get_value(v212);
        v214 = std::operator+<wchar_t>(v280, L"Rollback ", v213);
        v241[1] = v205;
        LODWORD(v242) = 752;
        cxl::TextWriter::WriteLine<wchar_t,char [52],int,int,std::wstring>(v211, (__int64)&v241[1], v214);
        std::wstring::_Tidy_deallocate(v280);
        std::wstring::_Tidy_deallocate(v265);
        std::wstring::_Tidy_deallocate(v283);
      }
      else if ( (unsigned int)dword_18014B6A8 > 5 )
      {
        v249 = (const char *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v262);
        v241[1] = v215;
        LODWORD(v242) = 752;
        v263 = "Wsp::Facade::StorageHealthFacade::EnableMaintenance";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>>(
          v216,
          (__int64)&word_18012B326,
          v217,
          v218,
          &v263,
          (__int64)&v242,
          (__int64)&v241[1],
          &v249);
      }
      goto LABEL_46;
    }
    FaultDomainPhysicalDisks = Wsp::Facade::StorageHealthFacade::ChangeWriteCache(
                                 v152,
                                 (unsigned int)v244,
                                 (unsigned int)&v267,
                                 (unsigned int)v252,
                                 a10);
    v245 = FaultDomainPhysicalDisks;
    if ( FaultDomainPhysicalDisks )
    {
      std::wstring::wstring(v262, L"Change SBL cache");
      if ( (unsigned int)dword_18014B6A8 > 2 )
      {
        v263 = (const char *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v262);
        v241[1] = FaultDomainPhysicalDisks;
        LODWORD(v242) = 648;
        v246 = "Wsp::Facade::StorageHealthFacade::EnableMaintenance";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>>(
          v157,
          (__int64)byte_18012B5E1,
          v158,
          v159,
          &v246,
          (__int64)&v242,
          (__int64)&v241[1],
          &v263);
      }
      v160 = cxl::TraceManager::Instance();
      v241[1] = FaultDomainPhysicalDisks;
      LODWORD(v242) = 648;
      cxl::TextWriter::WriteLine<wchar_t,char [52],int,int,wchar_t [17]>(
        (struct cxl::TraceManager *)((char *)v160 + 40),
        v161,
        v162,
        (__int64)&v242,
        (__int64)&v241[1]);
    }
    else
    {
      FaultDomainPhysicalDisks = Wsp::Facade::StorageHealthFacade::GetDiskCacheState(
                                   a1,
                                   (unsigned int)&v267,
                                   (unsigned int)v252,
                                   0,
                                   (__int64)a9,
                                   a10);
      v245 = FaultDomainPhysicalDisks;
      if ( !FaultDomainPhysicalDisks )
      {
        v241[1] = 4;
        FaultDomainPhysicalDisks = Wsp::Facade::StorageHealthFacade::ClearMaintenanceModeIntent(v163, v252, &v241[1]);
        v245 = FaultDomainPhysicalDisks;
        if ( !FaultDomainPhysicalDisks )
          goto LABEL_152;
        std::wstring::wstring(v262, L"Clear Starting Maintenance Mode Intent on Physical Disks");
        if ( (unsigned int)dword_18014B6A8 > 2 )
        {
          v263 = (const char *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v262);
          v241[1] = FaultDomainPhysicalDisks;
          LODWORD(v242) = 668;
          v246 = "Wsp::Facade::StorageHealthFacade::EnableMaintenance";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>>(
            v197,
            (__int64)byte_18012B563,
            v198,
            v199,
            &v246,
            (__int64)&v242,
            (__int64)&v241[1],
            &v263);
        }
        v200 = cxl::TraceManager::Instance();
        v241[1] = FaultDomainPhysicalDisks;
        LODWORD(v242) = 668;
        cxl::TextWriter::WriteLine<wchar_t,char [52],int,int,wchar_t [57]>(
          (struct cxl::TraceManager *)((char *)v200 + 40),
          (__int64)&v241[1]);
        goto LABEL_106;
      }
      std::wstring::wstring(v262, L"Waiting for SBL cache state");
      if ( (unsigned int)dword_18014B6A8 > 2 )
      {
        v263 = (const char *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v262);
        v241[1] = FaultDomainPhysicalDisks;
        LODWORD(v242) = 661;
        v246 = "Wsp::Facade::StorageHealthFacade::EnableMaintenance";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>>(
          v164,
          (__int64)&dword_18012B524,
          v165,
          v166,
          &v246,
          (__int64)&v242,
          (__int64)&v241[1],
          &v263);
      }
      v167 = cxl::TraceManager::Instance();
      v241[1] = FaultDomainPhysicalDisks;
      LODWORD(v242) = 661;
      cxl::TextWriter::WriteLine<wchar_t,char [52],int,int,wchar_t [28]>(
        (struct cxl::TraceManager *)((char *)v167 + 40),
        v168,
        v169,
        (__int64)&v242,
        (__int64)&v241[1],
        (__int64)L"Waiting for SBL cache state");
    }
    std::wstring::_Tidy_deallocate(v262);
    if ( !v272 || !v273 )
      goto LABEL_80;
    v244[0] = 1;
    v171 = Wsp::Facade::StorageHealthFacade::ChangeWriteCache(
             v170,
             (unsigned int)v244,
             (unsigned int)&v267,
             (unsigned int)v252,
             a10);
    std::wstring::wstring(v262, L"Rollback change SBL cache");
    if ( v171 )
    {
      if ( (unsigned int)dword_18014B6A8 > 2 )
      {
        v263 = (const char *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v262);
        v241[1] = v171;
        LODWORD(v242) = 687;
        v246 = "Wsp::Facade::StorageHealthFacade::EnableMaintenance";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>>(
          v172,
          (__int64)byte_18012B465,
          v173,
          v174,
          &v246,
          (__int64)&v242,
          (__int64)&v241[1],
          &v263);
      }
      v175 = cxl::TraceManager::Instance();
      v241[1] = v171;
      LODWORD(v242) = 687;
      cxl::TextWriter::WriteLine<wchar_t,char [52],int,int,wchar_t [26]>(
        (struct cxl::TraceManager *)((char *)v175 + 40),
        v176,
        v177,
        (__int64)&v242,
        (__int64)&v241[1]);
    }
    else if ( (unsigned int)dword_18014B6A8 > 5 )
    {
      v263 = (const char *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v262);
      v241[1] = 0;
      LODWORD(v242) = 687;
      v246 = "Wsp::Facade::StorageHealthFacade::EnableMaintenance";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>>(
        v178,
        (__int64)&dword_18012B4A4,
        v179,
        v180,
        &v246,
        (__int64)&v242,
        (__int64)&v241[1],
        &v263);
    }
    std::wstring::_Tidy_deallocate(v262);
    v181 = v171 == 0;
    LOBYTE(v182) = 1;
    DiskCacheState = Wsp::Facade::StorageHealthFacade::GetDiskCacheState(
                       a1,
                       (unsigned int)&v267,
                       (unsigned int)v252,
                       v182,
                       (__int64)a9,
                       a10);
    std::wstring::wstring(v262, L"Rollback waiting for SBL cache state");
    if ( DiskCacheState )
    {
      if ( (unsigned int)dword_18014B6A8 > 2 )
      {
        v263 = (const char *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v262);
        v241[1] = DiskCacheState;
        LODWORD(v242) = 700;
        v246 = "Wsp::Facade::StorageHealthFacade::EnableMaintenance";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>>(
          v184,
          (__int64)byte_18012B4E5,
          v185,
          v186,
          &v246,
          (__int64)&v242,
          (__int64)&v241[1],
          &v263);
      }
      v187 = cxl::TraceManager::Instance();
      v241[1] = DiskCacheState;
      LODWORD(v242) = 700;
      cxl::TextWriter::WriteLine<wchar_t,char [52],int,int,wchar_t [37]>(
        (struct cxl::TraceManager *)((char *)v187 + 40),
        (__int64)&v241[1]);
    }
    else if ( (unsigned int)dword_18014B6A8 > 5 )
    {
      v263 = (const char *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v262);
      v241[1] = 0;
      LODWORD(v242) = 700;
      v246 = "Wsp::Facade::StorageHealthFacade::EnableMaintenance";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>>(
        v188,
        (__int64)&word_18012B3A6,
        v189,
        v190,
        &v246,
        (__int64)&v242,
        (__int64)&v241[1],
        &v263);
    }
    std::wstring::_Tidy_deallocate(v262);
    v191 = 0;
    if ( !DiskCacheState )
      v191 = v181;
    if ( v191 )
    {
      v241[1] = 4;
      v192 = Wsp::Facade::StorageHealthFacade::ClearMaintenanceModeIntent(v191, v252, &v241[1]);
      if ( v192 )
      {
        std::wstring::wstring(v262, L"Clear Starting Maintenance Mode Intent on Physical Disks ");
        if ( (unsigned int)dword_18014B6A8 > 2 )
        {
          v263 = (const char *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v262);
          v241[1] = v192;
          LODWORD(v242) = 711;
          v246 = "Wsp::Facade::StorageHealthFacade::EnableMaintenance";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>>(
            v193,
            (__int64)&byte_18012B3E7,
            v194,
            v195,
            &v246,
            (__int64)&v242,
            (__int64)&v241[1],
            &v263);
        }
        v196 = cxl::TraceManager::Instance();
        v241[1] = v192;
        LODWORD(v242) = 711;
        cxl::TextWriter::WriteLine<wchar_t,char [52],int,int,wchar_t [58]>(
          (struct cxl::TraceManager *)((char *)v196 + 40),
          (__int64)&v241[1]);
        std::wstring::_Tidy_deallocate(v262);
      }
    }
    goto LABEL_79;
  }
LABEL_152:
  v219 = (const MI_Char *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v266);
  MI_Context_WriteProgress(*v12, v219, v220, v221, 0x64u, (MI_Uint32)secondsRemaininga);
  std::wstring::wstring(v262, L"Completed");
  if ( FaultDomainPhysicalDisks )
  {
    if ( (unsigned int)dword_18014B6A8 > 2 )
    {
      v249 = (const char *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v262);
      v241[1] = FaultDomainPhysicalDisks;
      LODWORD(v242) = 768;
      v263 = "Wsp::Facade::StorageHealthFacade::EnableMaintenance";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>>(
        v222,
        (__int64)&byte_18012B367,
        v223,
        v224,
        &v263,
        (__int64)&v242,
        (__int64)&v241[1],
        &v249);
    }
    v225 = cxl::TraceManager::Instance();
    v241[1] = FaultDomainPhysicalDisks;
    LODWORD(v242) = 768;
    cxl::TextWriter::WriteLine<wchar_t,char [52],int,int,wchar_t [10]>(
      (struct cxl::TraceManager *)((char *)v225 + 40),
      v226,
      v227,
      (__int64)&v242,
      (__int64)&v241[1]);
  }
  else if ( (unsigned int)dword_18014B6A8 > 5 )
  {
    v249 = (const char *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v262);
    v241[1] = 0;
    LODWORD(v242) = 768;
    v263 = "Wsp::Facade::StorageHealthFacade::EnableMaintenance";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>>(
      v228,
      (__int64)word_18012B20A,
      v229,
      v230,
      &v263,
      (__int64)&v242,
      (__int64)&v241[1],
      &v249);
  }
  std::wstring::_Tidy_deallocate(v262);
  if ( (unsigned int)dword_18014B6A8 > 5 )
  {
    v241[1] = 770;
    v249 = "Wsp::Facade::StorageHealthFacade::EnableMaintenance";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      v231,
      (__int64)byte_18012B24B,
      v232,
      v233,
      &v249);
  }
  std::wstring::_Tidy_deallocate(v278);
  std::wstring::_Tidy_deallocate(v266);
  if ( v260[1] )
    std::_Ref_count_base::_Decref(v260[1]);
  Wsp::Facade::MaintenanceModeStruct::~MaintenanceModeStruct((Wsp::Facade::MaintenanceModeStruct *)&v267);
  std::_Tree<std::_Tmap_traits<std::wstring,Wsp::Facade::MaintenanceDisk,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,Wsp::Facade::MaintenanceDisk>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,Wsp::Facade::MaintenanceDisk,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,Wsp::Facade::MaintenanceDisk>>,0>>(v252);
  std::_Tree<std::_Tmap_traits<std::wstring,mismpstorage::SPACES_VirtualDisk,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,mismpstorage::SPACES_VirtualDisk>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,mismpstorage::SPACES_VirtualDisk,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,mismpstorage::SPACES_VirtualDisk>>,0>>(v261);
  if ( (_QWORD)v256 )
  {
    std::_Destroy_range<std::allocator<mismpstorage::SPACES_PhysicalDisk>>(v256, *((_QWORD *)&v256 + 1));
    std::_Deallocate<16>((void *)v256, (v257 - v256) & 0xFFFFFFFFFFFFFFC0uLL);
    v256 = 0;
    v257 = 0;
  }
  if ( (_QWORD)v258 )
  {
    std::_Destroy_range<std::allocator<mismpstorage::SPACES_PhysicalDisk>>(v258, *((_QWORD *)&v258 + 1));
    std::_Deallocate<16>((void *)v258, (v259 - v258) & 0xFFFFFFFFFFFFFFC0uLL);
    v258 = 0;
    v259 = 0;
  }
  std::wstring::_Tidy_deallocate(v279);
  return FaultDomainPhysicalDisks;
}

```

## disassembly

```asm
0x180062e00  push    rbp
0x180062e02  push    rbx
0x180062e03  push    rsi
0x180062e04  push    rdi
0x180062e05  push    r12
0x180062e07  push    r13
0x180062e09  push    r14
0x180062e0b  push    r15
0x180062e0d  lea     rbp, [rsp-2E8h]
0x180062e15  sub     rsp, 3E8h
0x180062e1c  mov     rax, cs:__security_cookie
0x180062e23  xor     rax, rsp
0x180062e26  mov     [rbp+320h+var_50], rax
0x180062e2d  mov     qword ptr [rbp+320h+var_398], r9
0x180062e31  mov     [rbp+320h+var_378], r8
0x180062e35  mov     r14, rdx
0x180062e38  mov     r15, rcx
0x180062e3b  mov     rsi, [rbp+320h+arg_38]
0x180062e42  mov     rax, [rbp+320h+arg_20]
0x180062e49  mov     [rbp+320h+var_350], rax
0x180062e4d  mov     rdi, [rbp+320h+arg_30]
0x180062e54  mov     [rbp+320h+var_390], rdi
0x180062e58  mov     rax, [rbp+320h+arg_28]
0x180062e5f  mov     [rbp+320h+var_358], rax
0x180062e63  mov     r12, [rbp+320h+arg_40]
0x180062e6a  mov     [rbp+320h+var_388], r12
0x180062e6e  mov     r13, qword ptr [rbp+320h+arg_48]
0x180062e75  mov     eax, cs:dword_18014B6A8
0x180062e7b  lea     rcx, aWspFacadeStora_24; "Wsp::Facade::StorageHealthFacade::Enabl"...
0x180062e82  cmp     eax, 5
0x180062e85  jbe     short loc_180062EB4
0x180062e87  mov     [rsp+420h+var_3A4], 146h
0x180062e8f  mov     qword ptr [rsp+420h+var_3BC+4], rcx
0x180062e94  lea     rax, [rsp+420h+var_3A4]
0x180062e99  mov     qword ptr [rsp+420h+secondsRemaining], rax; secondsRemaining
0x180062e9e  lea     rax, [rsp+420h+var_3BC+4]
0x180062ea3  mov     qword ptr [rsp+420h+percentComplete], rax
0x180062ea8  lea     rdx, word_18012B972
0x180062eaf  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x180062eb4  xorps   xmm0, xmm0
0x180062eb7  movups  [rbp+320h+var_138], xmm0
0x180062ebe  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x180062ec6  movdqu  [rbp+320h+var_128], xmm1
0x180062ece  xor     ebx, ebx
0x180062ed0  mov     word ptr [rbp+320h+var_138], bx
0x180062ed7  movdqu  [rbp+320h+var_330], xmm0
0x180062edc  mov     [rbp+320h+var_320], rbx
0x180062ee0  movdqu  [rbp+320h+var_348], xmm0
0x180062ee5  mov     [rbp+320h+var_338], rbx
0x180062ee9  mov     [rbp+320h+var_360], 0FFFFFFFFh
0x180062ef0  lea     eax, [rbx+1]
0x180062ef3  mov     [rbp+320h+var_380], ax
0x180062ef7  lea     rcx, [rbp+320h+var_308]
0x180062efb  call    ??0?$map@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@VSPACES_PhysicalDisk@mismpstorage@@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@VSPACES_PhysicalDisk@mismpstorage@@@std@@@2@@std@@QEAA@XZ; std::map<std::wstring,mismpstorage::SPACES_PhysicalDisk>::map<std::wstring,mismpstorage::SPACES_PhysicalDisk>(void)
0x180062f00  nop
0x180062f01  lea     rcx, [rbp+320h+var_370]
0x180062f05  call    ??0?$map@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UMaintenanceDisk@Facade@Wsp@@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UMaintenanceDisk@Facade@Wsp@@@std@@@2@@std@@QEAA@XZ; std::map<std::wstring,Wsp::Facade::MaintenanceDisk>::map<std::wstring,Wsp::Facade::MaintenanceDisk>(void)
0x180062f0a  nop
0x180062f0b  lea     rcx, [rbp+320h+var_270]; this
0x180062f12  call    ??0MaintenanceModeStruct@Facade@Wsp@@QEAA@XZ; Wsp::Facade::MaintenanceModeStruct::MaintenanceModeStruct(void)
0x180062f17  nop
0x180062f18  xorps   xmm1, xmm1
0x180062f1b  movdqu  xmmword ptr [rbp+320h+var_318], xmm1
0x180062f20  mov     [rsp+420h+var_3A7], bl
0x180062f24  mov     [rsp+420h+var_3A8], 1
0x180062f29  mov     rcx, r15
0x180062f2c  call    ?GetSubsystemType@StorageHealthFacade@Facade@Wsp@@QEBA?BW4WSP_SUBSYSTEM_TYPE@@XZ; Wsp::Facade::StorageHealthFacade::GetSubsystemType(void)
0x180062f31  test    eax, eax
0x180062f33  jz      loc_180064B7E
0x180062f39  mov     r8d, 0BB9h
0x180062f3f  mov     rdx, cs:qword_1801578A0
0x180062f46  lea     rcx, [rbp+320h+var_298]
0x180062f4d  call    ?load_string@cxl@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEAUHINSTANCE__@@I@Z; cxl::load_string(HINSTANCE__ *,uint)
0x180062f52  nop
0x180062f53  lea     rcx, [rbp+320h+var_298]
0x180062f5a  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180062f5f  mov     rdx, rax; activity
0x180062f62  mov     [rsp+420h+percentComplete], 1; percentComplete
0x180062f6a  mov     rcx, [r12]; context
0x180062f6e  call    MI_Context_WriteProgress
0x180062f73  xorps   xmm0, xmm0
0x180062f76  movups  [rbp+320h+var_158], xmm0
0x180062f7d  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x180062f85  movdqu  [rbp+320h+var_148], xmm1
0x180062f8d  mov     word ptr [rbp+320h+var_158], bx
0x180062f94  lea     rdx, [rbp+320h+var_158]
0x180062f9b  lea     rcx, [rbp+320h+var_180]
0x180062fa2  call    ??0StringWriter@cxl@@QEAA@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::StringWriter::StringWriter(std::wstring &)
0x180062fa7  nop
0x180062fa8  mov     rcx, rax
0x180062fab  call    ??$Write@$0DH@@TextWriter@cxl@@QEAAAEAV01@AEAY0DH@$$CB_W@Z; cxl::TextWriter::Write<55>(wchar_t const (&)[55])
0x180062fb0  nop
0x180062fb1  lea     rdx, [rbp+320h+var_158]
0x180062fb8  lea     rcx, [rbp+320h+var_2B8]
0x180062fbc  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180062fc1  nop
0x180062fc2  mov     eax, cs:dword_18014B6A8
0x180062fc8  cmp     eax, 4
0x180062fcb  jbe     short loc_180063006
0x180062fcd  mov     edx, 4000h
0x180062fd2  lea     rcx, dword_18014B6A8
0x180062fd9  call    _tlgKeywordOn
0x180062fde  test    al, al
0x180062fe0  jz      short loc_180063006
0x180062fe2  lea     rcx, [rbp+320h+var_2B8]
0x180062fe6  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180062feb  mov     qword ptr [rsp+420h+var_3BC+4], rax
0x180062ff0  lea     rax, [rsp+420h+var_3BC+4]
0x180062ff5  mov     qword ptr [rsp+420h+percentComplete], rax
0x180062ffa  lea     rdx, byte_18012B913
0x180063001  call    ??$Write@U?$_tlgWrapSz@_W@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@_W@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<wchar_t> const &)
0x180063006  call    ?Instance@TraceManager@cxl@@SAAEAV12@XZ; cxl::TraceManager::Instance(void)
0x18006300b  lea     rbx, [rax+78h]
0x18006300f  lea     rdx, [rbp+320h+var_2B8]
0x180063013  mov     rcx, rbx
0x180063016  call    ?WriteTo@?$CxlTraits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@cxl@@SAXAEAVTextWriter@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBUFormat@2@@Z; cxl::CxlTraits<std::wstring>::WriteTo(cxl::TextWriter &,std::wstring const &,cxl::Format const &)
0x18006301b  mov     rcx, rbx
0x18006301e  call    ??$?6UENDL@cxl@@@TextWriter@cxl@@QEAAAEAV01@AEBUENDL@1@@Z; cxl::TextWriter::operator<<<cxl::ENDL>(cxl::ENDL const &)
0x180063023  nop
0x180063024  lea     rcx, [rbp+320h+var_2B8]
0x180063028  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18006302d  mov     rax, [rbp+320h+var_358]
0x180063031  mov     rdx, [rax]
0x180063034  mov     ebx, 1
0x180063039  test    rdx, rdx
0x18006303c  jz      short loc_180063050
0x18006303e  mov     [rbp+320h+var_1D7], bl
0x180063044  lea     rcx, [rbp+320h+var_1F8]
0x18006304b  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x180063050  mov     rdx, [rdi]
0x180063053  xor     edi, edi
0x180063055  test    rdx, rdx
0x180063058  jz      short loc_18006306C
0x18006305a  mov     [rbp+320h+var_1D8], bl
0x180063060  lea     rcx, [rbp+320h+var_218]
0x180063067  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18006306c  lea     rcx, [rbp+320h+var_2D8]
0x180063070  call    ?GetInstance@MiSpaceAdapter@Wsp@@SA?AV?$shared_ptr@VMiSpaceAdapter@Wsp@@@std@@XZ; Wsp::MiSpaceAdapter::GetInstance(void)
0x180063075  nop
0x180063076  lea     rcx, [rbp+320h+var_270]
0x18006307d  mov     qword ptr [rsp+420h+percentComplete], rcx
0x180063082  lea     r9, [rbp+320h+var_26C]
0x180063089  mov     r8, r14
0x18006308c  lea     rdx, [rbp+320h+var_2F8]
0x180063090  mov     rcx, [rax]
0x180063093  call    ?UnpackObjectId@MiSpaceAdapter@Wsp@@QEBA?BV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV34@PEAW4WSP_SUBSYSTEM_TYPE@@PEAW4WSP_OBJECT_TYPE@@@Z; Wsp::MiSpaceAdapter::UnpackObjectId(std::wstring const &,WSP_SUBSYSTEM_TYPE *,WSP_OBJECT_TYPE *)
0x180063098  nop
0x180063099  mov     rdx, rax
0x18006309c  lea     rcx, [rbp+320h+var_138]
0x1800630a3  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x1800630a8  nop
0x1800630a9  lea     rcx, [rbp+320h+var_2F8]
0x1800630ad  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800630b2  nop
0x1800630b3  mov     rcx, [rbp+320h+var_2D0]; this
0x1800630b7  test    rcx, rcx
0x1800630ba  jz      short loc_1800630C1
0x1800630bc  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800630c1  mov     rcx, r15
0x1800630c4  call    ?GetSubsystemType@StorageHealthFacade@Facade@Wsp@@QEBA?BW4WSP_SUBSYSTEM_TYPE@@XZ; Wsp::Facade::StorageHealthFacade::GetSubsystemType(void)
0x1800630c9  cmp     eax, [rbp+320h+var_26C]
0x1800630cf  jz      loc_180063186
0x1800630d5  mov     edi, ebx
0x1800630d7  lea     rdx, aSubsystemNotSu; "Subsystem not supported"
0x1800630de  lea     rcx, [rbp+320h+var_2F8]
0x1800630e2  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x1800630e7  nop
0x1800630e8  mov     eax, cs:dword_18014B6A8
0x1800630ee  mov     ebx, 17Dh
0x1800630f3  cmp     eax, 2
0x1800630f6  jbe     short loc_18006314E
0x1800630f8  lea     rcx, [rbp+320h+var_2F8]
0x1800630fc  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180063101  mov     qword ptr [rbp+320h+var_398], rax
0x180063105  mov     [rsp+420h+var_3A4], 1
0x18006310d  mov     [rsp+420h+var_3C0], ebx
0x180063111  lea     rax, aWspFacadeStora_24; "Wsp::Facade::StorageHealthFacade::Enabl"...
0x180063118  mov     [rbp+320h+var_390], rax
0x18006311c  lea     rax, [rbp+320h+var_398]
0x180063120  mov     [rsp+420h+var_3E8], rax
0x180063125  lea     rax, [rsp+420h+var_3A4]
0x18006312a  mov     [rsp+420h+var_3F0], rax
0x18006312f  lea     rax, [rsp+420h+var_3C0]
0x180063134  mov     qword ptr [rsp+420h+secondsRemaining], rax
0x180063139  lea     rax, [rbp+320h+var_390]
0x18006313d  mov     qword ptr [rsp+420h+percentComplete], rax
0x180063142  lea     rdx, byte_18012B933
0x180063149  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@U?$_tlgWrapSz@_W@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4AEBU?$_tlgWrapSz@_W@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<wchar_t> const &)
0x18006314e  call    ?Instance@TraceManager@cxl@@SAAEAV12@XZ; cxl::TraceManager::Instance(void)
0x180063153  lea     rcx, [rax+28h]; struct cxl::TextWriter *
0x180063157  mov     [rsp+420h+var_3C0], 1
0x18006315f  mov     [rsp+420h+var_3A4], ebx
0x180063163  lea     rax, [rsp+420h+var_3C0]
0x180063168  mov     qword ptr [rsp+420h+percentComplete], rax; __int64
0x18006316d  lea     r9, [rsp+420h+var_3A4]
0x180063172  call    ??$WriteLine@_W$$BY0DE@DHH$$BY0BI@_W@TextWriter@cxl@@QEAAXPEB_WAEAY0DE@$$CBDAEBH2AEAY0BI@$$CB_W@Z; cxl::TextWriter::WriteLine<wchar_t,char [52],int,int,wchar_t [24]>(wchar_t const *,char const (&)[52],int const &,int const &,wchar_t const (&)[24])
0x180063177  nop
0x180063178  lea     rcx, [rbp+320h+var_2F8]
0x18006317c  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180063181  jmp     loc_180064947
0x180063186  mov     eax, [rbp+320h+var_270]
0x18006318c  cmp     eax, 0Ch
0x18006318f  ja      loc_180064945
0x180063195  mov     ecx, 1220h
0x18006319a  bt      ecx, eax
0x18006319d  jnb     loc_180064945
0x1800631a3  lea     rdx, [rbp+320h+var_2D8]
0x1800631a7  call    ?GetSmApiSession@StorageHealthFacade@Facade@Wsp@@AEAA?AV?$shared_ptr@VMiSession@mi@@@std@@XZ; Wsp::Facade::StorageHealthFacade::GetSmApiSession(void)
0x1800631ac  mov     rdx, rax
0x1800631af  lea     rcx, [rbp+320h+var_268]
0x1800631b6  call    ??4?$shared_ptr@$$CBVSPACES_VirtualDisk@mismpstorage@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<mismpstorage::SPACES_VirtualDisk const>::operator=(std::shared_ptr<mismpstorage::SPACES_VirtualDisk const> &&)
0x1800631bb  mov     rcx, [rbp+320h+var_2D0]; this
0x1800631bf  test    rcx, rcx
0x1800631c2  jz      short loc_1800631C9
0x1800631c4  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800631c9  lea     rcx, [rbp+320h+var_2D8]
0x1800631cd  call    ?GetInstance@DataStore@ClusWmi@@SA?AV?$shared_ptr@VDataStore@ClusWmi@@@std@@XZ; ClusWmi::DataStore::GetInstance(void)
0x1800631d2  nop
0x1800631d3  lea     rdx, [rbp+320h+var_318]
0x1800631d7  mov     rcx, [rax]; struct ProtectedPwd *
0x1800631da  call    ?GetCluster@DataStore@ClusWmi@@QEAAJPEAV?$shared_ptr@UICluster@ClusApi@@@std@@@Z; ClusWmi::DataStore::GetCluster(std::shared_ptr<ClusApi::ICluster> *)
0x1800631df  mov     ebx, eax
0x1800631e1  mov     rcx, [rbp+320h+var_2D0]; this
0x1800631e5  test    rcx, rcx
0x1800631e8  jz      short loc_1800631EF
0x1800631ea  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800631ef  test    ebx, ebx
0x1800631f1  jns     loc_18006338A
0x1800631f7  mov     [rsp+420h+var_3A4], ebx
0x1800631fb  mov     ecx, cs:dword_18014B6A8
0x180063201  mov     edi, 194h
0x180063206  cmp     ecx, 2
0x180063209  jbe     short loc_18006324D
0x18006320b  mov     eax, [rsp+420h+var_3A4]
0x18006320f  mov     [rsp+420h+var_3C0], eax
0x180063213  mov     dword ptr [rsp+420h+var_3BC], edi
0x180063217  lea     r14, aWspFacadeStora_24; "Wsp::Facade::StorageHealthFacade::Enabl"...
0x18006321e  mov     qword ptr [rbp+320h+var_398], r14
0x180063222  lea     rax, [rsp+420h+var_3C0]
0x180063227  mov     [rsp+420h+var_3F0], rax
0x18006322c  lea     rax, [rsp+420h+var_3BC]
0x180063231  mov     qword ptr [rsp+420h+secondsRemaining], rax
0x180063236  lea     rax, [rbp+320h+var_398]
0x18006323a  mov     qword ptr [rsp+420h+percentComplete], rax
0x18006323f  lea     rdx, byte_18012B85B
0x180063246  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18006324b  jmp     short loc_180063254
0x18006324d  lea     r14, aWspFacadeStora_24; "Wsp::Facade::StorageHealthFacade::Enabl"...
0x180063254  call    ?Instance@TraceManager@cxl@@SAAEAV12@XZ; cxl::TraceManager::Instance(void)
0x180063259  lea     rcx, [rax+28h]; struct cxl::TextWriter *
0x18006325d  mov     dword ptr [rsp+420h+var_3BC], edi
0x180063261  lea     rax, [rsp+420h+var_3A4]
0x180063266  mov     qword ptr [rsp+420h+percentComplete], rax; __int64
0x18006326b  lea     r9, [rsp+420h+var_3BC]
0x180063270  mov     r8, r14
0x180063273  call    ??$WriteLine@_W$$BY0DE@DHJ@TextWriter@cxl@@QEAAXPEB_WAEAY0DE@$$CBDAEBHAEBJ@Z; cxl::TextWriter::WriteLine<wchar_t,char [52],int,long>(wchar_t const *,char const (&)[52],int const &,long const &)
0x180063278  mov     ecx, ebx
0x18006327a  call    ?SmRCFromHResult@MiSpaceAdapter@Wsp@@SA?AW4SM_RETURN_CODE@@J@Z; Wsp::MiSpaceAdapter::SmRCFromHResult(long)
0x18006327f  mov     edi, eax
0x180063281  lea     rdx, aFailedToGetClu; "Failed to Get Cluster"
0x180063288  lea     rcx, [rbp+320h+var_2B8]
0x18006328c  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x180063291  nop
0x180063292  xor     esi, esi
0x180063294  test    edi, edi
0x180063296  jz      loc_180063321
0x18006329c  mov     ecx, cs:dword_18014B6A8
0x1800632a2  cmp     ecx, 2
0x1800632a5  jbe     short loc_1800632F6
0x1800632a7  lea     rcx, [rbp+320h+var_2B8]
0x1800632ab  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x1800632b0  mov     qword ptr [rbp+320h+var_398], rax
0x1800632b4  mov     dword ptr [rsp+420h+var_3BC], edi
0x1800632b8  mov     [rsp+420h+var_3C0], 195h
0x1800632c0  mov     [rbp+320h+var_390], r14
0x1800632c4  lea     rax, [rbp+320h+var_398]
0x1800632c8  mov     [rsp+420h+var_3E8], rax
0x1800632cd  lea     rax, [rsp+420h+var_3BC]
0x1800632d2  mov     [rsp+420h+var_3F0], rax
0x1800632d7  lea     rax, [rsp+420h+var_3C0]
0x1800632dc  mov     qword ptr [rsp+420h+secondsRemaining], rax
0x1800632e1  lea     rax, [rbp+320h+var_390]
0x1800632e5  mov     qword ptr [rsp+420h+percentComplete], rax
0x1800632ea  lea     rdx, byte_18012B893
0x1800632f1  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@U?$_tlgWrapSz@_W@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4AEBU?$_tlgWrapSz@_W@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<wchar_t> const &)
0x1800632f6  call    ?Instance@TraceManager@cxl@@SAAEAV12@XZ; cxl::TraceManager::Instance(void)
0x1800632fb  lea     rcx, [rax+28h]; struct cxl::TextWriter *
0x1800632ff  mov     dword ptr [rsp+420h+var_3BC], edi
0x180063303  mov     [rsp+420h+var_3C0], 195h
0x18006330b  lea     rax, [rsp+420h+var_3BC]
0x180063310  mov     qword ptr [rsp+420h+percentComplete], rax; __int64
0x180063315  lea     r9, [rsp+420h+var_3C0]
0x18006331a  call    ??$WriteLine@_W$$BY0DE@DHH$$BY0BG@_W@TextWriter@cxl@@QEAAXPEB_WAEAY0DE@$$CBDAEBH2AEAY0BG@$$CB_W@Z; cxl::TextWriter::WriteLine<wchar_t,char [52],int,int,wchar_t [22]>(wchar_t const *,char const (&)[52],int const &,int const &,wchar_t const (&)[22])
0x18006331f  jmp     short loc_18006337C
0x180063321  mov     eax, cs:dword_18014B6A8
0x180063327  cmp     eax, 5
0x18006332a  jbe     short loc_18006337C
0x18006332c  lea     rcx, [rbp+320h+var_2B8]
0x180063330  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180063335  mov     qword ptr [rbp+320h+var_398], rax
  ... truncated ...
```
