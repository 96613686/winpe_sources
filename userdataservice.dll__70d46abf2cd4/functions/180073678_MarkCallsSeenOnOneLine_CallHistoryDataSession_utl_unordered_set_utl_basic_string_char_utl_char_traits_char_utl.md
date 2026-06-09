# MarkCallsSeenOnOneLine(CallHistoryDataSession *,utl::unordered_set<utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>,tlx::istring_hash_ascii,tlx::istring_equal_to_ascii,utl::allocator<utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>>> const *,UdmIdSet const *,_FILETIME const &,ushort const *,int)

- ea: `0x180073678`
- end: `0x180074dae`
- name: `?MarkCallsSeenOnOneLine@@YAJPEAVCallHistoryDataSession@@PEBV?$unordered_set@V?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@Uistring_hash_ascii@tlx@@Uistring_equal_to_ascii@4@V?$allocator@V?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@@2@@utl@@PEBUUdmIdSet@@AEBU_FILETIME@@PEBGH@Z`
- size: `5942`
- prototype: `__int64 __fastcall(int, int, int, int, void *pvData, int)`
- caller_count: `3`
- callee_count: `33`
- tags: `file_ops, authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x1800e0e3c`
- `0x1800e110c`
- `0x1800e1200`

## callees

- `0x1800054c0`
- `0x180008ee8`
- `0x180008f0c`
- `0x180013000`
- `0x180018c20`
- `0x18001b340`
- `0x18003bf04`
- `0x18005b080`
- `0x18005d03c`
- `0x18005e048`
- `0x18005e160`
- `0x180066860`
- `0x180068458`
- `0x180068698`
- `0x18006a8ac`
- `0x18006b13c`
- `0x180073610`
- `0x180073678`
- `0x180075f98`
- `0x180076604`
- `0x180076664`
- `0x1800977ac`
- `0x1800a1270`
- `0x1800a1568`
- `0x1800dbb0c`
- `0x1800e1380`
- `0x1800e1428`
- `0x1800e2758`
- `0x1800e2874`
- `0x1800e2f58`
- `0x18012c76a`
- `0x18012c7b0`
- `0x18012c840`

## import_xrefs

- `msvcrt!_strnicmp` at `0x1800741a9`
- `msvcrt!_strnicmp` at `0x1800741a9`
- `ESENT!JetOpenTableA` at `0x180073895`
- `ESENT!JetOpenTableA` at `0x180073895`
- `ESENT!JetMakeKey` at `0x180073cbd`
- `ESENT!JetMakeKey` at `0x180073d0e`
- `ESENT!JetMakeKey` at `0x180073d36`
- `ESENT!JetMakeKey` at `0x180073dae`
- `ESENT!JetMakeKey` at `0x180073cbd`
- `ESENT!JetMakeKey` at `0x180073d0e`
- `ESENT!JetMakeKey` at `0x180073d36`
- `ESENT!JetMakeKey` at `0x180073dae`
- `ESENT!JetSetCurrentIndexA` at `0x180073c93`
- `ESENT!JetSetCurrentIndexA` at `0x180073d88`
- `ESENT!JetSetCurrentIndexA` at `0x180073c93`
- `ESENT!JetSetCurrentIndexA` at `0x180073d88`
- `ESENT!JetRetrieveColumns` at `0x180074136`
- `ESENT!JetRetrieveColumns` at `0x180074136`
- `ESENT!JetSetColumn` at `0x1800742ce`
- `ESENT!JetSetColumn` at `0x1800742ff`
- `ESENT!JetSetColumn` at `0x1800742ce`
- `ESENT!JetSetColumn` at `0x1800742ff`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180073bf2`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180073bf2`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180073c0c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180073c0c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180073bfb`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180073bfb`
- `api-ms-win-core-synch-l1-1-0!TryAcquireSRWLockShared` at `0x180073be3`
- `api-ms-win-core-synch-l1-1-0!TryAcquireSRWLockShared` at `0x180073be3`

## string_xrefs

- `0x18007397d`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\datasession.cpp`
- `0x1800739b6`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\datasession.cpp`
- `0x1800739ef`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\datasession.cpp`
- `0x180073a28`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\datasession.cpp`
- `0x180073a61`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\datasession.cpp`
- `0x180073a9a`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\datasession.cpp`
- `0x180073ad3`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\datasession.cpp`
- `0x180073b0c`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\datasession.cpp`
- `0x180073bcf`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\datasession.cpp`
- `0x180073718`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\callhistory.cpp`
- `0x1800737b8`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\callhistory.cpp`
- `0x1800738b0`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\callhistory.cpp`
- `0x180073b52`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\callhistory.cpp`
- `0x18007444d`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\callhistory.cpp`
- `0x1800744d5`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\callhistory.cpp`
- `0x18007455d`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\callhistory.cpp`
- `0x1800745e5`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\callhistory.cpp`
- `0x18007466d`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\callhistory.cpp`
- `0x1800746f5`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\callhistory.cpp`
- `0x180074776`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\callhistory.cpp`
- `0x1800747ff`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\callhistory.cpp`
- `0x180074887`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\callhistory.cpp`
- `0x180074908`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\callhistory.cpp`
- `0x18007498a`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\callhistory.cpp`
- `0x180074a0c`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\callhistory.cpp`
- `0x180074a95`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\callhistory.cpp`
- `0x180074b9b`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\callhistory.cpp`
- `0x180074c23`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\callhistory.cpp`
- `0x180074cab`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\callhistory.cpp`
- `0x180074d33`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\callhistory.cpp`

## pseudocode

```c
__int64 __fastcall MarkCallsSeenOnOneLine(__int64 a1, __int64 **a2, __int64 a3, void *a4, _WORD *pvData, int a6)
{
  __int64 v7; // r8
  unsigned int i; // ebx
  unsigned int HresultFromJetError; // ebx
  void *v10; // rcx
  _QWORD *v11; // rdx
  __int64 v12; // rax
  unsigned int v13; // r13d
  int AppPackageFamilyName; // eax
  void *v15; // rcx
  _QWORD *v16; // rdx
  __int64 v17; // rax
  __int64 v18; // r9
  JET_SESID v19; // rcx
  JET_DBID v20; // edx
  unsigned int v21; // ebx
  int v22; // r15d
  RTL_SRWLOCK *v23; // rdi
  RTL_SRWLOCK *v24; // rdi
  unsigned int v25; // r12d
  JET_ERR v26; // eax
  void *v27; // rcx
  _QWORD *v28; // rdx
  __int64 v29; // rax
  DatabaseVolumeSession *v31; // rcx
  __int64 v32; // rcx
  DatabaseVolumeSession *v33; // rcx
  __int64 v34; // rcx
  DatabaseVolumeSession *v35; // rcx
  __int64 v36; // rcx
  DatabaseVolumeSession *v37; // rcx
  __int64 v38; // rcx
  DatabaseVolumeSession *v39; // rcx
  __int64 v40; // rcx
  DatabaseVolumeSession *v41; // rcx
  __int64 v42; // rcx
  DatabaseVolumeSession *v43; // rcx
  __int64 v44; // rcx
  DatabaseVolumeSession *v45; // rcx
  __int64 v46; // rcx
  unsigned __int64 v47; // rcx
  int v48; // eax
  void *v49; // rcx
  _QWORD *v50; // rdx
  __int64 v51; // rax
  unsigned int v52; // edx
  int v53; // edi
  __int64 v54; // rax
  int v55; // eax
  JET_ERR v56; // eax
  JET_ERR v57; // eax
  unsigned int v58; // edx
  int v59; // eax
  JET_ERR v60; // eax
  JET_ERR v61; // eax
  int v62; // eax
  JET_ERR v63; // eax
  JET_ERR Key; // eax
  int v65; // eax
  unsigned int v66; // r15d
  JET_ERR v67; // eax
  int v68; // eax
  bool v69; // zf
  __int64 **v70; // rcx
  size_t v71; // rdi
  __int64 **v72; // rbx
  __int64 v73; // r9
  int v74; // eax
  JET_ERR v75; // eax
  JET_ERR v76; // eax
  int v77; // eax
  __int64 v78; // rdi
  __int64 v79; // rax
  int v80; // eax
  unsigned int j; // ebx
  void *v82; // rcx
  _QWORD *v83; // rdx
  __int64 v84; // rax
  void *v85; // rcx
  _QWORD *v86; // rdx
  __int64 v87; // rax
  void *v88; // rcx
  _QWORD *v89; // rdx
  __int64 v90; // rax
  void *v91; // rcx
  _QWORD *v92; // rdx
  __int64 v93; // rax
  void *v94; // rcx
  _QWORD *v95; // rdx
  __int64 v96; // rax
  void *v97; // rcx
  _QWORD *v98; // rdx
  __int64 v99; // rax
  void *v100; // rcx
  _QWORD *v101; // rdx
  __int64 v102; // rax
  void *v103; // rcx
  _QWORD *v104; // rdx
  __int64 v105; // rax
  void *v106; // rcx
  _QWORD *v107; // rdx
  __int64 v108; // rax
  void *v109; // rcx
  _QWORD *v110; // rdx
  __int64 v111; // rax
  void *v112; // rcx
  _QWORD *v113; // rdx
  __int64 v114; // rax
  void *v115; // rcx
  _QWORD *v116; // rdx
  __int64 v117; // rax
  void *v118; // rcx
  _QWORD *v119; // rdx
  __int64 v120; // rax
  void *v121; // rcx
  _QWORD *v122; // rdx
  __int64 v123; // rax
  void *v124; // rcx
  _QWORD *v125; // rdx
  __int64 v126; // rax
  void *v127; // rcx
  _QWORD *v128; // rdx
  __int64 v129; // rax
  void *v130; // rcx
  _QWORD *v131; // rdx
  __int64 v132; // rax
  void *v133; // rcx
  _QWORD *v134; // rdx
  __int64 v135; // rax
  unsigned int v136; // [rsp+40h] [rbp-C0h] BYREF
  int v137; // [rsp+48h] [rbp-B8h] BYREF
  unsigned int v138; // [rsp+4Ch] [rbp-B4h]
  RTL_SRWLOCK *v139; // [rsp+50h] [rbp-B0h]
  __int64 v140; // [rsp+58h] [rbp-A8h] BYREF
  JET_SESID sesid; // [rsp+60h] [rbp-A0h] BYREF
  JET_TABLEID tableid; // [rsp+68h] [rbp-98h] BYREF
  int v143; // [rsp+70h] [rbp-90h] BYREF
  char v144[4]; // [rsp+74h] [rbp-8Ch] BYREF
  void *Block[3]; // [rsp+78h] [rbp-88h] BYREF
  __int64 v146; // [rsp+90h] [rbp-70h]
  int v147; // [rsp+A0h] [rbp-60h] BYREF
  int v148; // [rsp+A4h] [rbp-5Ch] BYREF
  int v149; // [rsp+A8h] [rbp-58h] BYREF
  __int128 v150; // [rsp+B0h] [rbp-50h]
  __int128 v151; // [rsp+C0h] [rbp-40h]
  __int128 v152; // [rsp+D0h] [rbp-30h]
  __int64 v153; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v154; // [rsp+E8h] [rbp-18h]
  int v155; // [rsp+100h] [rbp+0h] BYREF
  JET_COLUMNID v156; // [rsp+104h] [rbp+4h]
  int v157; // [rsp+108h] [rbp+8h]
  _QWORD v158[6]; // [rsp+110h] [rbp+10h] BYREF
  int v159; // [rsp+140h] [rbp+40h]
  JET_COLUMNID Column; // [rsp+148h] [rbp+48h]
  unsigned int v161; // [rsp+14Ch] [rbp+4Ch]
  unsigned int v162; // [rsp+150h] [rbp+50h]
  unsigned int v163; // [rsp+154h] [rbp+54h]
  unsigned int v164; // [rsp+158h] [rbp+58h]
  unsigned int v165; // [rsp+15Ch] [rbp+5Ch]
  JET_COLUMNID columnid; // [rsp+160h] [rbp+60h]
  void *v167; // [rsp+168h] [rbp+68h]
  __int64 v168; // [rsp+170h] [rbp+70h]
  __int64 **v169; // [rsp+178h] [rbp+78h]
  __int64 v170; // [rsp+180h] [rbp+80h] BYREF
  _BYTE v171[8]; // [rsp+188h] [rbp+88h] BYREF
  JET_RETRIEVECOLUMN pretrievecolumn; // [rsp+190h] [rbp+90h] BYREF
  unsigned int v173; // [rsp+1C0h] [rbp+C0h]
  int v174; // [rsp+1C4h] [rbp+C4h]
  __int64 *v175; // [rsp+1C8h] [rbp+C8h]
  int v176; // [rsp+1D0h] [rbp+D0h]
  __int64 v177; // [rsp+1D4h] [rbp+D4h]
  unsigned int ibLongValue; // [rsp+1DCh] [rbp+DCh]
  int v179; // [rsp+1E0h] [rbp+E0h]
  __int64 v180; // [rsp+1E4h] [rbp+E4h]
  unsigned int v181; // [rsp+1ECh] [rbp+ECh]
  unsigned int v182; // [rsp+1F0h] [rbp+F0h]
  int v183; // [rsp+1F4h] [rbp+F4h]
  char *v184; // [rsp+1F8h] [rbp+F8h]
  int v185; // [rsp+200h] [rbp+100h]
  _DWORD MaxCount[5]; // [rsp+204h] [rbp+104h]
  JET_ERR err; // [rsp+218h] [rbp+118h]
  int v188; // [rsp+21Ch] [rbp+11Ch]
  JET_COLUMNID v189; // [rsp+220h] [rbp+120h]
  int v190; // [rsp+224h] [rbp+124h]
  int *v191; // [rsp+228h] [rbp+128h]
  int v192; // [rsp+230h] [rbp+130h]
  __int64 v193; // [rsp+234h] [rbp+134h]
  unsigned int v194; // [rsp+23Ch] [rbp+13Ch]
  int v195; // [rsp+240h] [rbp+140h]
  __int64 v196; // [rsp+244h] [rbp+144h]
  unsigned int v197; // [rsp+24Ch] [rbp+14Ch]
  unsigned int v198; // [rsp+250h] [rbp+150h]
  int v199; // [rsp+254h] [rbp+154h]
  _WORD *v200; // [rsp+258h] [rbp+158h]
  int v201; // [rsp+260h] [rbp+160h]
  __int64 v202; // [rsp+264h] [rbp+164h]
  unsigned int v203; // [rsp+26Ch] [rbp+16Ch]
  int v204; // [rsp+270h] [rbp+170h]
  int v205; // [rsp+274h] [rbp+174h]
  JET_ERR v206; // [rsp+278h] [rbp+178h]
  int v207; // [rsp+27Ch] [rbp+17Ch]
  unsigned int v208; // [rsp+280h] [rbp+180h]
  int v209; // [rsp+284h] [rbp+184h]
  int *v210; // [rsp+288h] [rbp+188h]
  int v211; // [rsp+290h] [rbp+190h]
  __int64 v212; // [rsp+294h] [rbp+194h]
  unsigned int v213; // [rsp+29Ch] [rbp+19Ch]
  int v214; // [rsp+2A0h] [rbp+1A0h]
  int v215; // [rsp+2A4h] [rbp+1A4h]
  JET_ERR v216; // [rsp+2A8h] [rbp+1A8h]
  int v217; // [rsp+2ACh] [rbp+1ACh]
  unsigned int v218; // [rsp+2B0h] [rbp+1B0h]
  int v219; // [rsp+2B4h] [rbp+1B4h]
  int *v220; // [rsp+2B8h] [rbp+1B8h]
  int v221; // [rsp+2C0h] [rbp+1C0h]
  __int64 v222; // [rsp+2C4h] [rbp+1C4h]
  unsigned int v223; // [rsp+2CCh] [rbp+1CCh]
  int v224; // [rsp+2D0h] [rbp+1D0h]
  int v225; // [rsp+2D4h] [rbp+1D4h]
  JET_ERR v226; // [rsp+2D8h] [rbp+1D8h]
  int v227; // [rsp+2DCh] [rbp+1DCh]
  char v228[3600]; // [rsp+2E0h] [rbp+1E0h] BYREF
  char String2[112]; // [rsp+10F0h] [rbp+FF0h] BYREF
  _WORD v230[1032]; // [rsp+1160h] [rbp+1060h] BYREF

  v167 = a4;
  v168 = a3;
  v169 = a2;
  utl::unordered_map<enum _SebiEventType,_GUID,utl::hash<enum _SebiEventType>,utl::equal_to<enum _SebiEventType>,utl::allocator<utl::pair<enum _SebiEventType const,_GUID>>>::unordered_map<enum _SebiEventType,_GUID,utl::hash<enum _SebiEventType>,utl::equal_to<enum _SebiEventType>,utl::allocator<utl::pair<enum _SebiEventType const,_GUID>>>(Block);
  if ( v7 )
  {
    for ( i = 0; ; ++i )
    {
      if ( i >= *(_DWORD *)v7 )
        goto LABEL_9;
      if ( !*(_QWORD *)utl::_HashTable<unsigned long,unsigned long,utl::hash<unsigned long>,utl::equal_to<unsigned long>,utl::allocator<unsigned long>,0>::emplace<unsigned long const &,0>(
                         Block,
                         &v137,
                         *(_QWORD *)(v7 + 8) + 4 * (3LL * i + 2)) )
        break;
      v7 = v168;
    }
    HresultFromJetError = -2147024882;
    Log_HREvent(
      2147942414LL,
      0,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\callhistory.cpp",
      1125);
    while ( 1 )
    {
      v10 = Block[0];
      if ( Block[0] == Block )
        break;
      v11 = (_QWORD *)*((_QWORD *)Block[0] + 1);
      v12 = *(_QWORD *)Block[0];
      *v11 = *(_QWORD *)Block[0];
      *(_QWORD *)(v12 + 8) = v11;
      operator delete(v10);
    }
LABEL_23:
    v146 = 0;
    utl::_HashTable<enum _SebiEventType,utl::pair<enum _SebiEventType const,_GUID>,utl::hash<enum _SebiEventType>,utl::equal_to<enum _SebiEventType>,utl::allocator<utl::pair<enum _SebiEventType const,_GUID>>,0>::_FreeBuckets(Block);
    return HresultFromJetError;
  }
LABEL_9:
  v140 = 0;
  ATL::CComPtr<ServiceDataSession>::operator=(&v140, a1);
  v13 = (unsigned int)CallHistoryOperationContext::ValidateCallerSecurity(&v140, 2, 0, 1) >> 31;
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(&v153);
  if ( v13 )
  {
    AppPackageFamilyName = ServiceDataSession::GetAppPackageFamilyName(a1, &v153);
    HresultFromJetError = AppPackageFamilyName;
    if ( AppPackageFamilyName < 0 )
    {
      Log_HREvent(
        (unsigned int)AppPackageFamilyName,
        1,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\callhistory.cpp",
        1135);
      utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(&v153);
      ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(&v140);
      while ( 1 )
      {
        v15 = Block[0];
        if ( Block[0] == Block )
          break;
        v16 = (_QWORD *)*((_QWORD *)Block[0] + 1);
        v17 = *(_QWORD *)Block[0];
        *v16 = *(_QWORD *)Block[0];
        *(_QWORD *)(v17 + 8) = v16;
        operator delete(v15);
      }
      goto LABEL_23;
    }
    if ( !pvData )
      goto LABEL_18;
    v18 = -1;
    do
      ++v18;
    while ( pvData[v18] );
    v13 = 0;
    if ( (unsigned int)utl::_StringTraits<utl::char_traits<unsigned short>>::compare(
                         v153,
                         (v154 - v153) >> 1,
                         pvData,
                         v18) )
LABEL_18:
      v13 = 1;
  }
  v19 = *(_QWORD *)(a1 + 2048);
  v20 = *(_DWORD *)(a1 + 2056);
  v21 = 0;
  v22 = 0;
  v137 = 0;
  v23 = *(RTL_SRWLOCK **)(a1 + 2040);
  tableid = -1;
  v24 = v23 + 15;
  v25 = 0;
  v139 = v24;
  v138 = 0;
  sesid = v19;
  v26 = JetOpenTableA(v19, v20, "CallHistory", 0, 0, 8u, &tableid);
  if ( v26 < 0 )
  {
    HresultFromJetError = MakeHresultFromJetError(v26);
    Log_HREvent(
      HresultFromJetError,
      0,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\callhistory.cpp",
      1151);
    auto_JET_TABLEID::~auto_JET_TABLEID((auto_JET_TABLEID *)&sesid);
    BackoffContext::Unlock((BackoffContext *)&v137);
    utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(&v153);
    ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(&v140);
    while ( 1 )
    {
      v27 = Block[0];
      if ( Block[0] == Block )
        break;
      v28 = (_QWORD *)*((_QWORD *)Block[0] + 1);
      v29 = *(_QWORD *)Block[0];
      *v28 = *(_QWORD *)Block[0];
      *(_QWORD *)(v29 + 8) = v28;
      operator delete(v27);
    }
    goto LABEL_23;
  }
  v31 = *(DatabaseVolumeSession **)(a1 + 2040);
  v136 = 0;
  Column = DatabaseVolumeSession::FindColumnEx(
             v31,
             (const struct ColumnDefinition *)&UdmTableCols_CallHistory,
             (int *)&v136);
  if ( !v136 )
    Log_AssertionEvent_2(
      v32,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\datasession.cpp",
      203);
  v33 = *(DatabaseVolumeSession **)(a1 + 2040);
  v136 = 0;
  v161 = DatabaseVolumeSession::FindColumnEx(v33, (const struct ColumnDefinition *)&off_180130C60, (int *)&v136);
  if ( !v136 )
    Log_AssertionEvent_2(
      v34,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\datasession.cpp",
      203);
  v35 = *(DatabaseVolumeSession **)(a1 + 2040);
  v136 = 0;
  v162 = DatabaseVolumeSession::FindColumnEx(v35, (const struct ColumnDefinition *)&off_180130D80, (int *)&v136);
  if ( !v136 )
    Log_AssertionEvent_2(
      v36,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\datasession.cpp",
      203);
  v37 = *(DatabaseVolumeSession **)(a1 + 2040);
  v136 = 0;
  columnid = DatabaseVolumeSession::FindColumnEx(v37, (const struct ColumnDefinition *)&off_180130C20, (int *)&v136);
  if ( !v136 )
    Log_AssertionEvent_2(
      v38,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\datasession.cpp",
      203);
  v39 = *(DatabaseVolumeSession **)(a1 + 2040);
  v136 = 0;
  v156 = DatabaseVolumeSession::FindColumnEx(v39, (const struct ColumnDefinition *)&off_180130C40, (int *)&v136);
  if ( !v136 )
    Log_AssertionEvent_2(
      v40,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\datasession.cpp",
      203);
  v41 = *(DatabaseVolumeSession **)(a1 + 2040);
  v136 = 0;
  v163 = DatabaseVolumeSession::FindColumnEx(v41, (const struct ColumnDefinition *)&off_180130D60, (int *)&v136);
  if ( !v136 )
    Log_AssertionEvent_2(
      v42,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\datasession.cpp",
      203);
  v43 = *(DatabaseVolumeSession **)(a1 + 2040);
  v136 = 0;
  v164 = DatabaseVolumeSession::FindColumnEx(v43, (const struct ColumnDefinition *)&off_180130EE0, (int *)&v136);
  if ( !v136 )
    Log_AssertionEvent_2(
      v44,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\datasession.cpp",
      203);
  v45 = *(DatabaseVolumeSession **)(a1 + 2040);
  v136 = 0;
  v165 = DatabaseVolumeSession::FindColumnEx(v45, (const struct ColumnDefinition *)&off_180130EC0, (int *)&v136);
  if ( !v136 )
    Log_AssertionEvent_2(
      v46,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\datasession.cpp",
      203);
  v144[0] = 1;
  v136 = 0;
  if ( pvData )
  {
    v47 = -1;
    do
      ++v47;
    while ( pvData[v47] );
    v48 = ULongLongToULong(v47, &v136);
    HresultFromJetError = v48;
    if ( v48 < 0 )
    {
      Log_HREvent(
        (unsigned int)v48,
        1,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\callhistory.cpp",
        1166);
      auto_JET_TABLEID::~auto_JET_TABLEID((auto_JET_TABLEID *)&sesid);
      BackoffContext::Unlock((BackoffContext *)&v137);
      utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(&v153);
      ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(&v140);
      while ( 1 )
      {
        v49 = Block[0];
        if ( Block[0] == Block )
          break;
        v50 = (_QWORD *)*((_QWORD *)Block[0] + 1);
        v51 = *(_QWORD *)Block[0];
        *v50 = *(_QWORD *)Block[0];
        *(_QWORD *)(v51 + 8) = v50;
        operator delete(v49);
      }
      goto LABEL_23;
    }
    v25 = v136;
LABEL_48:
    v21 = v138;
  }
  if ( v22 )
    Log_AssertionEvent_2(
      v46,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\datasession.cpp",
      2208);
  if ( v21 >= 2 )
  {
    AcquireSRWLockExclusive(v24);
    v137 = 2;
  }
  else
  {
    if ( !TryAcquireSRWLockShared(v24) )
    {
      Sleep(0x64u);
      AcquireSRWLockShared(v24);
    }
    v137 = 1;
  }
  v53 = 0;
  v54 = *(_QWORD *)(a1 + 2048);
  v158[1] = tableid;
  v158[5] = tableid;
  v170 = 0;
  v136 = 0;
  v147 = 0;
  v149 = 0;
  v155 = 0;
  v158[0] = v54;
  v158[2] = v54;
  v158[3] = 0;
  v158[4] = v54;
  v159 = 0;
  v55 = UpdateContext::Start((UpdateContext *)v158, v52);
  if ( v55 < 0 )
  {
    HresultFromJetError = MakeHresultFromJetError(v55);
    Log_HREvent(
      HresultFromJetError,
      0,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\callhistory.cpp",
      1191);
    UpdateContext::~UpdateContext((UpdateContext *)v158);
    BackoffContext::Unlock((BackoffContext *)&v137);
    auto_JET_TABLEID::~auto_JET_TABLEID((auto_JET_TABLEID *)&sesid);
    BackoffContext::Unlock((BackoffContext *)&v137);
    utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(&v153);
    ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(&v140);
    while ( 1 )
    {
      v133 = Block[0];
      if ( Block[0] == Block )
        break;
      v134 = (_QWORD *)*((_QWORD *)Block[0] + 1);
      v135 = *(_QWORD *)Block[0];
      *v134 = *(_QWORD *)Block[0];
      *(_QWORD *)(v135 + 8) = v134;
      operator delete(v133);
    }
    goto LABEL_23;
  }
  v148 = 0;
  if ( !pvData )
    goto LABEL_68;
  if ( !v25 )
  {
    if ( !a6 )
      goto LABEL_160;
LABEL_68:
    v63 = JetSetCurrentIndexA(sesid, tableid, "Unseen");
    if ( v63 < 0 )
    {
      HresultFromJetError = MakeHresultFromJetError(v63);
      Log_HREvent(
        HresultFromJetError,
        0,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\callhistory.cpp",
        1218);
      UpdateContext::~UpdateContext((UpdateContext *)v158);
      BackoffContext::Unlock((BackoffContext *)&v137);
      auto_JET_TABLEID::~auto_JET_TABLEID((auto_JET_TABLEID *)&sesid);
      BackoffContext::Unlock((BackoffContext *)&v137);
      utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(&v153);
      ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(&v140);
      while ( 1 )
      {
        v130 = Block[0];
        if ( Block[0] == Block )
          break;
        v131 = (_QWORD *)*((_QWORD *)Block[0] + 1);
        v132 = *(_QWORD *)Block[0];
        *v131 = *(_QWORD *)Block[0];
        *(_QWORD *)(v132 + 8) = v131;
        operator delete(v130);
      }
      goto LABEL_23;
    }
    Key = JetMakeKey(sesid, tableid, v167, 8u, 1u);
    if ( Key < 0 )
    {
      HresultFromJetError = MakeHresultFromJetError(Key);
      Log_HREvent(
        HresultFromJetError,
        0,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\callhistory.cpp",
        1219);
      UpdateContext::~UpdateContext((UpdateContext *)v158);
      BackoffContext::Unlock((BackoffContext *)&v137);
      auto_JET_TABLEID::~auto_JET_TABLEID((auto_JET_TABLEID *)&sesid);
      BackoffContext::Unlock((BackoffContext *)&v137);
      utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(&v153);
      ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(&v140);
      while ( 1 )
      {
        v127 = Block[0];
        if ( Block[0] == Block )
          break;
        v128 = (_QWORD *)*((_QWORD *)Block[0] + 1);
        v129 = *(_QWORD *)Block[0];
        *v128 = *(_QWORD *)Block[0];
        *(_QWORD *)(v129 + 8) = v128;
        operator delete(v127);
      }
      goto LABEL_23;
    }
    v65 = auto_JET_TABLEID::MaybeSetRange((auto_JET_TABLEID *)&sesid, 3u, &v148);
    if ( v65 < 0 )
    {
      HresultFromJetError = MakeHresultFromJetError(v65);
      Log_HREvent(
        HresultFromJetError,
        0,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\callhistory.cpp",
        1220);
      UpdateContext::~UpdateContext((UpdateContext *)v158);
      BackoffContext::Unlock((BackoffContext *)&v137);
      auto_JET_TABLEID::~auto_JET_TABLEID((auto_JET_TABLEID *)&sesid);
      BackoffContext::Unlock((BackoffContext *)&v137);
      utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(&v153);
      ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(&v140);
      while ( 1 )
      {
        v124 = Block[0];
        if ( Block[0] == Block )
          break;
        v125 = (_QWORD *)*((_QWORD *)Block[0] + 1);
        v126 = *(_QWORD *)Block[0];
        *v125 = *(_QWORD *)Block[0];
        *(_QWORD *)(v126 + 8) = v125;
        operator delete(v124);
      }
      goto LABEL_23;
    }
    goto LABEL_71;
  }
  v56 = JetSetCurrentIndexA(sesid, tableid, "UnseenByLine");
  if ( v56 < 0 )
  {
    HresultFromJetError = MakeHresultFromJetError(v56);
    Log_HREvent(
      HresultFromJetError,
      0,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\callhistory.cpp",
      1202);
    UpdateContext::~UpdateContext((UpdateContext *)v158);
    BackoffContext::Unlock((BackoffContext *)&v137);
    auto_JET_TABLEID::~auto_JET_TABLEID((auto_JET_TABLEID *)&sesid);
    BackoffContext::Unlock((BackoffContext *)&v137);
    utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(&v153);
    ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(&v140);
    while ( 1 )
    {
      v97 = Block[0];
      if ( Block[0] == Block )
        break;
      v98 = (_QWORD *)*((_QWORD *)Block[0] + 1);
      v99 = *(_QWORD *)Block[0];
      *v98 = *(_QWORD *)Block[0];
      *(_QWORD *)(v99 + 8) = v98;
      operator delete(v97);
    }
    goto LABEL_23;
  }
  v57 = JetMakeKey(sesid, tableid, pvData, 2 * v25, 0x101u);
  if ( v57 < 0 )
  {
    HresultFromJetError = MakeHresultFromJetError(v57);
    Log_HREvent(
      HresultFromJetError,
      0,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\callhistory.cpp",
      1203);
    UpdateContext::~UpdateContext((UpdateContext *)v158);
    BackoffContext::Unlock((BackoffContext *)&v137);
    auto_JET_TABLEID::~auto_JET_TABLEID((auto_JET_TABLEID *)&sesid);
    BackoffContext::Unlock((BackoffContext *)&v137);
    utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(&v153);
    ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(&v140);
    while ( 1 )
    {
      v94 = Block[0];
      if ( Block[0] == Block )
        break;
      v95 = (_QWORD *)*((_QWORD *)Block[0] + 1);
      v96 = *(_QWORD *)Block[0];
      *v95 = *(_QWORD *)Block[0];
      *(_QWORD *)(v96 + 8) = v95;
      operator delete(v94);
    }
    goto LABEL_23;
  }
  v143 = 0;
  v59 = auto_JET_TABLEID::MaybeSeek((auto_JET_TABLEID *)&sesid, v58, (enum TableSeekResult *)&v143);
  if ( v59 < 0 )
  {
    HresultFromJetError = MakeHresultFromJetError(v59);
    Log_HREvent(
      HresultFromJetError,
      0,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\callhistory.cpp",
      1206);
    UpdateContext::~UpdateContext((UpdateContext *)v158);
    BackoffContext::Unlock((BackoffContext *)&v137);
    auto_JET_TABLEID::~auto_JET_TABLEID((auto_JET_TABLEID *)&sesid);
    BackoffContext::Unlock((BackoffContext *)&v137);
    utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(&v153);
    ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(&v140);
    while ( 1 )
    {
      v91 = Block[0];
      if ( Block[0] == Block )
        break;
      v92 = (_QWORD *)*((_QWORD *)Block[0] + 1);
      v93 = *(_QWORD *)Block[0];
      *v92 = *(_QWORD *)Block[0];
      *(_QWORD *)(v93 + 8) = v92;
      operator delete(v91);
    }
    goto LABEL_23;
  }
  if ( (unsigned int)(v143 - 2) > 1 )
  {
LABEL_160:
    UpdateContext::~UpdateContext((UpdateContext *)v158);
    BackoffContext::Unlock((BackoffContext *)&v137);
    goto LABEL_161;
  }
  v60 = JetMakeKey(sesid, tableid, pvData, 2 * v25, 1u);
  if ( v60 < 0 )
  {
    HresultFromJetError = MakeHresultFromJetError(v60);
    Log_HREvent(
      HresultFromJetError,
      0,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\callhistory.cpp",
      1210);
    UpdateContext::~UpdateContext((UpdateContext *)v158);
    BackoffContext::Unlock((BackoffContext *)&v137);
    auto_JET_TABLEID::~auto_JET_TABLEID((auto_JET_TABLEID *)&sesid);
    BackoffContext::Unlock((BackoffContext *)&v137);
    utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(&v153);
    ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(&v140);
    while ( 1 )
    {
      v88 = Block[0];
      if ( Block[0] == Block )
        break;
      v89 = (_QWORD *)*((_QWORD *)Block[0] + 1);
      v90 = *(_QWORD *)Block[0];
      *v89 = *(_QWORD *)Block[0];
      *(_QWORD *)(v90 + 8) = v89;
      operator delete(v88);
    }
    goto LABEL_23;
  }
  v61 = JetMakeKey(sesid, tableid, v167, 8u, 0x200u);
  if ( v61 < 0 )
  {
    HresultFromJetError = MakeHresultFromJetError(v61);
    Log_HREvent(
      HresultFromJetError,
      0,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\callhistory.cpp",
      1211);
    UpdateContext::~UpdateContext((UpdateContext *)v158);
    BackoffContext::Unlock((BackoffContext *)&v137);
    auto_JET_TABLEID::~auto_JET_TABLEID((auto_JET_TABLEID *)&sesid);
    BackoffContext::Unlock((BackoffContext *)&v137);
    utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(&v153);
    ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(&v140);
    while ( 1 )
    {
      v85 = Block[0];
      if ( Block[0] == Block )
        break;
      v86 = (_QWORD *)*((_QWORD *)Block[0] + 1);
      v87 = *(_QWORD *)Block[0];
      *v86 = *(_QWORD *)Block[0];
      *(_QWORD *)(v87 + 8) = v86;
      operator delete(v85);
    }
    goto LABEL_23;
  }
  v62 = auto_JET_TABLEID::MaybeSetRange((auto_JET_TABLEID *)&sesid, 3u, &v148);
  if ( v62 < 0 )
  {
    HresultFromJetError = MakeHresultFromJetError(v62);
    Log_HREvent(
      HresultFromJetError,
      0,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\callhistory.cpp",
      1212);
    UpdateContext::~UpdateContext((UpdateContext *)v158);
    BackoffContext::Unlock((BackoffContext *)&v137);
    auto_JET_TABLEID::~auto_JET_TABLEID((auto_JET_TABLEID *)&sesid);
    BackoffContext::Unlock((BackoffContext *)&v137);
    utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(&v153);
    ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(&v140);
    while ( 1 )
    {
      v82 = Block[0];
      if ( Block[0] == Block )
        break;
      v83 = (_QWORD *)*((_QWORD *)Block[0] + 1);
      v84 = *(_QWORD *)Block[0];
      *v83 = *(_QWORD *)Block[0];
      *(_QWORD *)(v84 + 8) = v83;
      operator delete(v82);
    }
    goto LABEL_23;
  }
LABEL_71:
  v66 = 0;
  v157 = 0;
  if ( !v148 )
    goto LABEL_160;
  do
  {
    pretrievecolumn.columnid = Column;
    pretrievecolumn.itagSequence = 1;
    *(&pretrievecolumn.columnid + 1) = 0;
    pretrievecolumn.pvData = &v136;
    pretrievecolumn.columnidNextTagged = 0;
    *(&pretrievecolumn.err + 1) = 0;
    v173 = v161;
    pretrievecolumn.cbData = 4;
    *(_QWORD *)&pretrievecolumn.cbActual = 0;
    pretrievecolumn.ibLongValue = _mm_cvtsi128_si32(_mm_srli_si128((__m128i)0LL, 12));
    pretrievecolumn.err = _mm_cvtsi128_si32(_mm_srli_si128((__m128i)0LL, 8));
    v174 = 0;
    v175 = &v170;
    v182 = v162;
    v176 = 8;
    v179 = 1;
    v177 = 0;
    v180 = 0;
    ibLongValue = pretrievecolumn.ibLongValue;
    v185 = 100;
    v183 = 0;
    v184 = String2;
    *(_QWORD *)&MaxCount[1] = 0;
    MaxCount[4] = 0;
    v188 = 0;
    v189 = v156;
    v181 = pretrievecolumn.ibLongValue;
    v190 = 0;
    MaxCount[0] = _mm_cvtsi128_si32(_mm_srli_si128((__m128i)0LL, 4));
    v191 = &v147;
    MaxCount[3] = 1;
    err = pretrievecolumn.err;
    v192 = 4;
    v193 = 0;
    v198 = v163;
    v197 = pretrievecolumn.ibLongValue;
    v211 = 4;
    v199 = 0;
    v200 = v230;
    v205 = 0;
    v207 = 0;
    v208 = v164;
    v221 = 4;
    v194 = pretrievecolumn.ibLongValue;
    v206 = pretrievecolumn.err;
    v195 = 1;
    v209 = 0;
    v210 = &v149;
    v215 = 0;
    v217 = 0;
    v203 = pretrievecolumn.ibLongValue;
    v218 = v165;
    v196 = 0;
    v201 = 1025;
    v216 = pretrievecolumn.err;
    v152 = 0;
    v204 = 1;
    v150 = 0;
    v219 = 0;
    v202 = 0;
    v213 = pretrievecolumn.ibLongValue;
    v220 = &v155;
    v151 = 0;
    v225 = 0;
    v212 = 0;
    v227 = 0;
    v214 = 1;
    v222 = 0;
    v223 = pretrievecolumn.ibLongValue;
    v224 = 1;
    v226 = pretrievecolumn.err;
    v67 = JetRetrieveColumns(sesid, tableid, &pretrievecolumn, 7u);
    if ( v67 < 0 )
    {
      HresultFromJetError = MakeHresultFromJetError(v67);
      Log_HREvent(
        HresultFromJetError,
        0,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\callhistory.cpp",
        1245);
      UpdateContext::~UpdateContext((UpdateContext *)v158);
      BackoffContext::Unlock((BackoffContext *)&v137);
      auto_JET_TABLEID::~auto_JET_TABLEID((auto_JET_TABLEID *)&sesid);
      BackoffContext::Unlock((BackoffContext *)&v137);
      utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(&v153);
      ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(&v140);
      while ( 1 )
      {
        v118 = Block[0];
        if ( Block[0] == Block )
          break;
        v119 = (_QWORD *)*((_QWORD *)Block[0] + 1);
        v120 = *(_QWORD *)Block[0];
        *v119 = *(_QWORD *)Block[0];
        *(_QWORD *)(v120 + 8) = v119;
        operator delete(v118);
      }
      goto LABEL_23;
    }
    v68 = 1;
    if ( v168 )
    {
      if ( pretrievecolumn.err
        || (v69 = Block == *(void ***)utl::_HashTable<unsigned long,utl::pair<unsigned long const,bool>,utl::hash<unsigned long>,utl::equal_to<unsigned long>,utl::allocator<utl::pair<unsigned long const,bool>>,0>::find<void>(
                                        Block,
                                        v171,
                                        &v136),
            v68 = 1,
            v69) )
      {
        v68 = 0;
      }
    }
    v70 = v169;
    if ( v169 && v68 )
    {
      if ( !err )
      {
        v71 = MaxCount[0];
        v72 = (__int64 **)*v169;
        while ( v72 != v70 )
        {
          if ( !_strnicmp((const char *)v72[3], String2, v71) )
          {
            v53 = 0;
            v68 = 1;
            goto LABEL_87;
          }
          v72 = (__int64 **)*v72;
          v70 = v169;
        }
        v53 = 0;
      }
      v68 = 0;
    }
LABEL_87:
    if ( a6 && pvData && !v25 )
    {
      if ( v216 || v149 != 1 )
        goto LABEL_110;
    }
    else if ( !v68 )
    {
      goto LABEL_110;
    }
    if ( !v13 )
      goto LABEL_103;
    if ( v226 )
      goto LABEL_103;
    if ( v155 != 1 )
      goto LABEL_103;
    if ( !v206 && !v216 && v149 == 1 )
    {
      v73 = -1;
      do
        ++v73;
      while ( v230[v73] );
      if ( !(unsigned int)utl::_StringTraits<utl::char_traits<unsigned short>>::compare(
                            v153,
                            (v154 - v153) >> 1,
                            v230,
                            v73) )
      {
LABEL_103:
        v143 = 0;
        v74 = UpdateContext::MaybePrepare((UpdateContext *)v158, 2u, &v143);
        HresultFromJetError = v74;
        if ( v74 < 0 )
        {
          Log_HREvent(
            (unsigned int)v74,
            1,
            "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\callhistory.cpp",
            1295);
          UpdateContext::~UpdateContext((UpdateContext *)v158);
          BackoffContext::Unlock((BackoffContext *)&v137);
          auto_JET_TABLEID::~auto_JET_TABLEID((auto_JET_TABLEID *)&sesid);
          BackoffContext::Unlock((BackoffContext *)&v137);
          utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(&v153);
          ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(&v140);
          while ( 1 )
          {
            v109 = Block[0];
            if ( Block[0] == Block )
              break;
            v110 = (_QWORD *)*((_QWORD *)Block[0] + 1);
            v111 = *(_QWORD *)Block[0];
            *v110 = *(_QWORD *)Block[0];
            *(_QWORD *)(v111 + 8) = v110;
            operator delete(v109);
          }
          goto LABEL_23;
        }
        if ( v143 )
        {
          v157 = 1;
        }
        else
        {
          v147 |= 1u;
          v75 = JetSetColumn(sesid, tableid, columnid, v144, 1u, 0, 0);
          if ( v75 < 0 )
          {
            HresultFromJetError = MakeHresultFromJetError(v75);
            Log_HREvent(
              HresultFromJetError,
              0,
              "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\callhistory.cpp",
              1307);
            UpdateContext::~UpdateContext((UpdateContext *)v158);
            BackoffContext::Unlock((BackoffContext *)&v137);
            auto_JET_TABLEID::~auto_JET_TABLEID((auto_JET_TABLEID *)&sesid);
            BackoffContext::Unlock((BackoffContext *)&v137);
            utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(&v153);
            ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(&v140);
            while ( 1 )
            {
              v106 = Block[0];
              if ( Block[0] == Block )
                break;
              v107 = (_QWORD *)*((_QWORD *)Block[0] + 1);
              v108 = *(_QWORD *)Block[0];
              *v107 = *(_QWORD *)Block[0];
              *(_QWORD *)(v108 + 8) = v107;
              operator delete(v106);
            }
            goto LABEL_23;
          }
          v76 = JetSetColumn(sesid, tableid, v156, &v147, 4u, 0, 0);
          if ( v76 < 0 )
          {
            HresultFromJetError = MakeHresultFromJetError(v76);
            Log_HREvent(
              HresultFromJetError,
              0,
              "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\callhistory.cpp",
              1308);
            UpdateContext::~UpdateContext((UpdateContext *)v158);
            BackoffContext::Unlock((BackoffContext *)&v137);
            auto_JET_TABLEID::~auto_JET_TABLEID((auto_JET_TABLEID *)&sesid);
            BackoffContext::Unlock((BackoffContext *)&v137);
            utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(&v153);
            ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(&v140);
            while ( 1 )
            {
              v103 = Block[0];
              if ( Block[0] == Block )
                break;
              v104 = (_QWORD *)*((_QWORD *)Block[0] + 1);
              v105 = *(_QWORD *)Block[0];
              *v104 = *(_QWORD *)Block[0];
              *(_QWORD *)(v105 + 8) = v104;
              operator delete(v103);
            }
            goto LABEL_23;
          }
          v77 = UpdateContext::Update((UpdateContext *)v158);
          HresultFromJetError = v77;
          if ( v77 < 0 )
          {
            Log_HREvent(
              (unsigned int)v77,
              1,
              "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\callhistory.cpp",
              1310);
            UpdateContext::~UpdateContext((UpdateContext *)v158);
            BackoffContext::Unlock((BackoffContext *)&v137);
            auto_JET_TABLEID::~auto_JET_TABLEID((auto_JET_TABLEID *)&sesid);
            BackoffContext::Unlock((BackoffContext *)&v137);
            utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(&v153);
            ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(&v140);
            while ( 1 )
            {
              v100 = Block[0];
              if ( Block[0] == Block )
                break;
              v101 = (_QWORD *)*((_QWORD *)Block[0] + 1);
              v102 = *(_QWORD *)Block[0];
              *v101 = *(_QWORD *)Block[0];
              *(_QWORD *)(v102 + 8) = v101;
              operator delete(v100);
            }
            goto LABEL_23;
          }
          v78 = 9LL * v66;
          memset_0(&v228[72 * v66], 0, 0x48u);
          *(_DWORD *)&v228[72 * v66 + 20] = v136;
          v79 = v170;
          *(_DWORD *)&v228[72 * v66++] = 1;
          *(_QWORD *)&v228[8 * v78 + 24] = v79;
          *(_QWORD *)&v228[8 * v78 + 8] = 2;
          *(_DWORD *)&v228[8 * v78 + 16] = 1;
          v53 = 0;
        }
      }
    }
LABEL_110:
    if ( v66 == 50 )
      goto LABEL_114;
    v53 = 0;
    v143 = 0;
    v80 = Move(sesid, tableid, 1, &v143);
    HresultFromJetError = v80;
    if ( v80 < 0 )
    {
      Log_HREvent(
        (unsigned int)v80,
        1,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\callhistory.cpp",
        1329);
      UpdateContext::~UpdateContext((UpdateContext *)v158);
      BackoffContext::Unlock((BackoffContext *)&v137);
      auto_JET_TABLEID::~auto_JET_TABLEID((auto_JET_TABLEID *)&sesid);
      BackoffContext::Unlock((BackoffContext *)&v137);
      utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(&v153);
      ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(&v140);
      while ( 1 )
      {
        v112 = Block[0];
        if ( Block[0] == Block )
          break;
        v113 = (_QWORD *)*((_QWORD *)Block[0] + 1);
        v114 = *(_QWORD *)Block[0];
        *v113 = *(_QWORD *)Block[0];
        *(_QWORD *)(v114 + 8) = v113;
        operator delete(v112);
      }
      goto LABEL_23;
    }
  }
  while ( v143 );
  v53 = 1;
  if ( !v66 )
    goto LABEL_117;
LABEL_114:
  HresultFromJetError = UpdateContext::Commit((UpdateContext *)v158, 1u);
  if ( (HresultFromJetError & 0x80000000) != 0 )
  {
    Log_HREvent(
      HresultFromJetError,
      1,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\callhistory.cpp",
      1341);
    UpdateContext::~UpdateContext((UpdateContext *)v158);
    BackoffContext::Unlock((BackoffContext *)&v137);
    auto_JET_TABLEID::~auto_JET_TABLEID((auto_JET_TABLEID *)&sesid);
    BackoffContext::Unlock((BackoffContext *)&v137);
    utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(&v153);
    ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(&v140);
    while ( 1 )
    {
      v115 = Block[0];
      if ( Block[0] == Block )
        break;
      v116 = (_QWORD *)*((_QWORD *)Block[0] + 1);
      v117 = *(_QWORD *)Block[0];
      *v116 = *(_QWORD *)Block[0];
      *(_QWORD *)(v117 + 8) = v116;
      operator delete(v115);
    }
    goto LABEL_23;
  }
  for ( j = 0; j < v66; ++j )
    DatabaseVolumeSession::PushNotify(
      *(DatabaseVolumeSession **)(a1 + 2040),
      (const struct UdmNotifyStructure *)&v228[72 * j]);
LABEL_117:
  if ( v157 )
  {
    BackoffContext::NeedsBackoff((BackoffContext *)&v137);
    v53 = 0;
  }
  UpdateContext::~UpdateContext((UpdateContext *)v158);
  BackoffContext::Unlock((BackoffContext *)&v137);
  if ( !v53 )
  {
    v24 = v139;
    v22 = v137;
    goto LABEL_48;
  }
LABEL_161:
  auto_JET_TABLEID::~auto_JET_TABLEID((auto_JET_TABLEID *)&sesid);
  BackoffContext::Unlock((BackoffContext *)&v137);
  utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(&v153);
  ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(&v140);
  while ( 1 )
  {
    v121 = Block[0];
    if ( Block[0] == Block )
      break;
    v122 = (_QWORD *)*((_QWORD *)Block[0] + 1);
    v123 = *(_QWORD *)Block[0];
    *v122 = *(_QWORD *)Block[0];
    *(_QWORD *)(v123 + 8) = v122;
    operator delete(v121);
  }
  v146 = 0;
  utl::_HashTable<enum _SebiEventType,utl::pair<enum _SebiEventType const,_GUID>,utl::hash<enum _SebiEventType>,utl::equal_to<enum _SebiEventType>,utl::allocator<utl::pair<enum _SebiEventType const,_GUID>>,0>::_FreeBuckets(Block);
  return 0;
}

```

## disassembly

```asm
0x180073678  mov     [rsp-8+arg_8], rbx
0x18007367d  push    rbp
0x18007367e  push    rsi
0x18007367f  push    rdi
0x180073680  push    r12
0x180073682  push    r13
0x180073684  push    r14
0x180073686  push    r15
0x180073688  lea     rbp, [rsp-1880h]
0x180073690  mov     eax, 1980h
0x180073695  call    _alloca_probe
0x18007369a  sub     rsp, rax
0x18007369d  mov     rax, cs:__security_cookie
0x1800736a4  xor     rax, rsp
0x1800736a7  mov     [rbp+18B0h+var_40], rax
0x1800736ae  mov     r14, [rbp+18B0h+pvData]
0x1800736b5  mov     rsi, rcx
0x1800736b8  lea     rcx, [rsp+19B0h+Block]
0x1800736bd  mov     [rbp+18B0h+var_1848], r9
0x1800736c1  mov     [rbp+18B0h+var_1840], r8
0x1800736c5  mov     [rbp+18B0h+var_1838], rdx
0x1800736c9  call    ??0?$unordered_map@W4_SebiEventType@@U_GUID@@U?$hash@W4_SebiEventType@@@utl@@U?$equal_to@W4_SebiEventType@@@4@V?$allocator@U?$pair@$$CBW4_SebiEventType@@U_GUID@@@utl@@@4@@utl@@QEAA@XZ; utl::unordered_map<_SebiEventType,_GUID,utl::hash<_SebiEventType>,utl::equal_to<_SebiEventType>,utl::allocator<utl::pair<_SebiEventType const,_GUID>>>::unordered_map<_SebiEventType,_GUID,utl::hash<_SebiEventType>,utl::equal_to<_SebiEventType>,utl::allocator<utl::pair<_SebiEventType const,_GUID>>>(void)
0x1800736ce  xor     edi, edi
0x1800736d0  lea     r15d, [rdi+1]
0x1800736d4  test    r8, r8
0x1800736d7  jz      loc_18007375D
0x1800736dd  mov     ebx, edi
0x1800736df  cmp     ebx, [r8]
0x1800736e2  jnb     short loc_18007375D
0x1800736e4  mov     eax, ebx
0x1800736e6  lea     rdx, [rsp+19B0h+var_1968]
0x1800736eb  lea     rcx, [rax+rax*2]
0x1800736ef  mov     rax, [r8+8]
0x1800736f3  lea     rcx, [rcx+2]
0x1800736f7  lea     r8, [rax+rcx*4]
0x1800736fb  lea     rcx, [rsp+19B0h+Block]
0x180073700  call    ??$emplace@AEBK$0A@@?$_HashTable@KKU?$hash@K@utl@@U?$equal_to@K@2@V?$allocator@K@2@$0A@@utl@@QEAA?AU?$pair@V?$_DlistConstIt@U?$_HashNode@K@utl@@K@utl@@_N@1@AEBK@Z; utl::_HashTable<ulong,ulong,utl::hash<ulong>,utl::equal_to<ulong>,utl::allocator<ulong>,0>::emplace<ulong const &,0>(ulong const &)
0x180073705  cmp     [rax], rdi
0x180073708  jz      short loc_180073713
0x18007370a  mov     r8, [rbp+18B0h+var_1840]
0x18007370e  add     ebx, r15d
0x180073711  jmp     short loc_1800736DF
0x180073713  mov     ebx, 8007000Eh
0x180073718  lea     r8, aOnecoreuapBase_43; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18007371f  mov     ecx, ebx
0x180073721  mov     r9d, 465h
0x180073727  xor     edx, edx
0x180073729  call    Log_HREvent
0x18007372e  mov     rcx, [rsp+19B0h+Block]; Block
0x180073733  lea     rax, [rsp+19B0h+Block]
0x180073738  cmp     rcx, rax
0x18007373b  jz      loc_180073916
0x180073741  mov     rdx, [rcx+8]
0x180073745  mov     rax, [rcx]
0x180073748  mov     [rdx], rax
0x18007374b  mov     [rax+8], rdx
0x18007374f  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x180073756  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18007375b  jmp     short loc_18007372E
0x18007375d  mov     rdx, rsi
0x180073760  mov     [rsp+19B0h+var_1958], rdi
0x180073765  lea     rcx, [rsp+19B0h+var_1958]
0x18007376a  call    ??4?$CComPtr@VServiceDataSession@@@ATL@@QEAAPEAVServiceDataSession@@PEAV2@@Z; ATL::CComPtr<ServiceDataSession>::operator=(ServiceDataSession *)
0x18007376f  xor     r8d, r8d
0x180073772  lea     rcx, [rsp+19B0h+var_1958]
0x180073777  mov     r9d, r15d
0x18007377a  lea     edx, [r8+2]
0x18007377e  call    ?ValidateCallerSecurity@CallHistoryOperationContext@@QEAAJW4UdmAccessLevel@@KH@Z; CallHistoryOperationContext::ValidateCallerSecurity(UdmAccessLevel,ulong,int)
0x180073783  mov     r13d, eax
0x180073786  lea     rcx, [rbp+18B0h+var_18D0]; void *
0x18007378a  shr     r13d, 1Fh
0x18007378e  call    ??0?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@XZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(void)
0x180073793  or      r12, 0FFFFFFFFFFFFFFFFh
0x180073797  test    r13d, r13d
0x18007379a  jz      loc_18007383D
0x1800737a0  lea     rdx, [rbp+18B0h+var_18D0]
0x1800737a4  mov     rcx, rsi
0x1800737a7  call    ?GetAppPackageFamilyName@ServiceDataSession@@QEAAJPEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@Z; ServiceDataSession::GetAppPackageFamilyName(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> *)
0x1800737ac  mov     ebx, eax
0x1800737ae  test    eax, eax
0x1800737b0  jns     short loc_18007380B
0x1800737b2  mov     r9d, 46Fh
0x1800737b8  lea     r8, aOnecoreuapBase_43; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800737bf  mov     edx, r15d
0x1800737c2  mov     ecx, eax
0x1800737c4  call    Log_HREvent
0x1800737c9  lea     rcx, [rbp+18B0h+var_18D0]; void *
0x1800737cd  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x1800737d2  lea     rcx, [rsp+19B0h+var_1958]
0x1800737d7  call    ??1?$CComPtrBase@UISODACompletionCallback@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(void)
0x1800737dc  mov     rcx, [rsp+19B0h+Block]; Block
0x1800737e1  lea     rax, [rsp+19B0h+Block]
0x1800737e6  cmp     rcx, rax
0x1800737e9  jz      loc_180073916
0x1800737ef  mov     rdx, [rcx+8]
0x1800737f3  mov     rax, [rcx]
0x1800737f6  mov     [rdx], rax
0x1800737f9  mov     [rax+8], rdx
0x1800737fd  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x180073804  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180073809  jmp     short loc_1800737DC
0x18007380b  test    r14, r14
0x18007380e  jz      short loc_18007383A
0x180073810  mov     r9, r12
0x180073813  inc     r9
0x180073816  cmp     [r14+r9*2], di
0x18007381b  jnz     short loc_180073813
0x18007381d  mov     rcx, [rbp+18B0h+var_18D0]
0x180073821  mov     r8, r14
0x180073824  mov     rdx, [rbp+18B0h+var_18C8]
0x180073828  sub     rdx, rcx
0x18007382b  sar     rdx, 1
0x18007382e  call    ?compare@?$_StringTraits@U?$char_traits@G@utl@@@utl@@SAHPEBG_K01@Z; utl::_StringTraits<utl::char_traits<ushort>>::compare(ushort const *,unsigned __int64,ushort const *,unsigned __int64)
0x180073833  mov     r13d, edi
0x180073836  test    eax, eax
0x180073838  jz      short loc_18007383D
0x18007383a  mov     r13d, r15d
0x18007383d  mov     rcx, [rsi+800h]; sesid
0x180073844  lea     rax, [rsp+19B0h+tableid]
0x180073849  mov     edx, [rsi+808h]; dbid
0x18007384f  lea     r8, ?UdmTableName_CallHistory@@3QBDB; "CallHistory"
0x180073856  mov     ebx, edi
0x180073858  mov     [rsp+19B0h+ptableid], rax; ptableid
0x18007385d  mov     r15d, edi
0x180073860  mov     [rsp+19B0h+var_1968], edi
0x180073864  mov     rdi, [rsi+7F8h]
0x18007386b  xor     r9d, r9d; pvParameters
0x18007386e  mov     [rsp+19B0h+tableid], r12
0x180073873  add     rdi, 78h ; 'x'
0x180073877  xor     r12d, r12d
0x18007387a  mov     [rsp+19B0h+grbit], 8; grbit
0x180073882  mov     [rsp+19B0h+var_1960], rdi
0x180073887  mov     [rsp+19B0h+var_1964], ebx
0x18007388b  mov     [rsp+19B0h+sesid], rcx
0x180073890  mov     [rsp+19B0h+cbParameters], r12d; cbParameters
0x180073895  call    cs:__imp_JetOpenTableA
0x18007389b  test    eax, eax
0x18007389d  jns     loc_180073950
0x1800738a3  mov     ecx, eax; int
0x1800738a5  call    ?MakeHresultFromJetError@@YAJJ@Z; MakeHresultFromJetError(long)
0x1800738aa  mov     r9d, 47Fh
0x1800738b0  lea     r8, aOnecoreuapBase_43; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800738b7  xor     edx, edx
0x1800738b9  mov     ecx, eax
0x1800738bb  mov     ebx, eax
0x1800738bd  call    Log_HREvent
0x1800738c2  lea     rcx, [rsp+19B0h+sesid]; this
0x1800738c7  call    ??1auto_JET_TABLEID@@QEAA@XZ; auto_JET_TABLEID::~auto_JET_TABLEID(void)
0x1800738cc  lea     rcx, [rsp+19B0h+var_1968]; this
0x1800738d1  call    ?Unlock@BackoffContext@@QEAAXXZ; BackoffContext::Unlock(void)
0x1800738d6  lea     rcx, [rbp+18B0h+var_18D0]; void *
0x1800738da  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x1800738df  lea     rcx, [rsp+19B0h+var_1958]
0x1800738e4  call    ??1?$CComPtrBase@UISODACompletionCallback@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(void)
0x1800738e9  mov     rcx, [rsp+19B0h+Block]; Block
0x1800738ee  lea     rax, [rsp+19B0h+Block]
0x1800738f3  cmp     rcx, rax
0x1800738f6  jz      short loc_180073914
0x1800738f8  mov     rdx, [rcx+8]
0x1800738fc  mov     rax, [rcx]
0x1800738ff  mov     [rdx], rax
0x180073902  mov     [rax+8], rdx
0x180073906  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x18007390d  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180073912  jmp     short loc_1800738E9
0x180073914  xor     edi, edi
0x180073916  lea     rcx, [rsp+19B0h+Block]
0x18007391b  mov     [rbp+18B0h+var_1920], rdi
0x18007391f  call    ?_FreeBuckets@?$_HashTable@W4_SebiEventType@@U?$pair@$$CBW4_SebiEventType@@U_GUID@@@utl@@U?$hash@W4_SebiEventType@@@3@U?$equal_to@W4_SebiEventType@@@3@V?$allocator@U?$pair@$$CBW4_SebiEventType@@U_GUID@@@utl@@@3@$0A@@utl@@AEAAXXZ; utl::_HashTable<_SebiEventType,utl::pair<_SebiEventType const,_GUID>,utl::hash<_SebiEventType>,utl::equal_to<_SebiEventType>,utl::allocator<utl::pair<_SebiEventType const,_GUID>>,0>::_FreeBuckets(void)
0x180073924  mov     eax, ebx
0x180073926  mov     rcx, [rbp+18B0h+var_40]
0x18007392d  xor     rcx, rsp; StackCookie
0x180073930  call    __security_check_cookie
0x180073935  mov     rbx, [rsp+19B0h+arg_8]
0x18007393d  add     rsp, 1980h
0x180073944  pop     r15
0x180073946  pop     r14
0x180073948  pop     r13
0x18007394a  pop     r12
0x18007394c  pop     rdi
0x18007394d  pop     rsi
0x18007394e  pop     rbp
0x18007394f  retn
0x180073950  mov     rcx, [rsi+7F8h]; this
0x180073957  lea     r8, [rsp+19B0h+var_1970]; int *
0x18007395c  lea     rdx, ?UdmTableCols_CallHistory@@3QBUColumnDefinition@@B; struct ColumnDefinition *
0x180073963  mov     [rsp+19B0h+var_1970], r12d
0x180073968  call    ?FindColumnEx@DatabaseVolumeSession@@QEBAKPEBUColumnDefinition@@PEAH@Z; DatabaseVolumeSession::FindColumnEx(ColumnDefinition const *,int *)
0x18007396d  mov     [rbp+18B0h+var_1868], eax
0x180073970  cmp     [rsp+19B0h+var_1970], r12d
0x180073975  jnz     short loc_180073989
0x180073977  mov     r8d, 0CBh
0x18007397d  lea     rdx, aOnecoreuapBase_62; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180073984  call    Log_AssertionEvent_2
0x180073989  mov     rcx, [rsi+7F8h]; this
0x180073990  lea     r8, [rsp+19B0h+var_1970]; int *
0x180073995  lea     rdx, off_180130C60; struct ColumnDefinition *
0x18007399c  mov     [rsp+19B0h+var_1970], r12d
0x1800739a1  call    ?FindColumnEx@DatabaseVolumeSession@@QEBAKPEBUColumnDefinition@@PEAH@Z; DatabaseVolumeSession::FindColumnEx(ColumnDefinition const *,int *)
0x1800739a6  mov     [rbp+18B0h+var_1864], eax
0x1800739a9  cmp     [rsp+19B0h+var_1970], r12d
0x1800739ae  jnz     short loc_1800739C2
0x1800739b0  mov     r8d, 0CBh
0x1800739b6  lea     rdx, aOnecoreuapBase_62; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800739bd  call    Log_AssertionEvent_2
0x1800739c2  mov     rcx, [rsi+7F8h]; this
0x1800739c9  lea     r8, [rsp+19B0h+var_1970]; int *
0x1800739ce  lea     rdx, off_180130D80; struct ColumnDefinition *
0x1800739d5  mov     [rsp+19B0h+var_1970], r12d
0x1800739da  call    ?FindColumnEx@DatabaseVolumeSession@@QEBAKPEBUColumnDefinition@@PEAH@Z; DatabaseVolumeSession::FindColumnEx(ColumnDefinition const *,int *)
0x1800739df  mov     [rbp+18B0h+var_1860], eax
0x1800739e2  cmp     [rsp+19B0h+var_1970], r12d
0x1800739e7  jnz     short loc_1800739FB
0x1800739e9  mov     r8d, 0CBh
0x1800739ef  lea     rdx, aOnecoreuapBase_62; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800739f6  call    Log_AssertionEvent_2
0x1800739fb  mov     rcx, [rsi+7F8h]; this
0x180073a02  lea     r8, [rsp+19B0h+var_1970]; int *
0x180073a07  lea     rdx, off_180130C20; struct ColumnDefinition *
0x180073a0e  mov     [rsp+19B0h+var_1970], r12d
0x180073a13  call    ?FindColumnEx@DatabaseVolumeSession@@QEBAKPEBUColumnDefinition@@PEAH@Z; DatabaseVolumeSession::FindColumnEx(ColumnDefinition const *,int *)
0x180073a18  mov     [rbp+18B0h+columnid], eax
0x180073a1b  cmp     [rsp+19B0h+var_1970], r12d
0x180073a20  jnz     short loc_180073A34
0x180073a22  mov     r8d, 0CBh
0x180073a28  lea     rdx, aOnecoreuapBase_62; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180073a2f  call    Log_AssertionEvent_2
0x180073a34  mov     rcx, [rsi+7F8h]; this
0x180073a3b  lea     r8, [rsp+19B0h+var_1970]; int *
0x180073a40  lea     rdx, off_180130C40; struct ColumnDefinition *
0x180073a47  mov     [rsp+19B0h+var_1970], r12d
0x180073a4c  call    ?FindColumnEx@DatabaseVolumeSession@@QEBAKPEBUColumnDefinition@@PEAH@Z; DatabaseVolumeSession::FindColumnEx(ColumnDefinition const *,int *)
0x180073a51  mov     [rbp+18B0h+var_18AC], eax
0x180073a54  cmp     [rsp+19B0h+var_1970], r12d
0x180073a59  jnz     short loc_180073A6D
0x180073a5b  mov     r8d, 0CBh
0x180073a61  lea     rdx, aOnecoreuapBase_62; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180073a68  call    Log_AssertionEvent_2
0x180073a6d  mov     rcx, [rsi+7F8h]; this
0x180073a74  lea     r8, [rsp+19B0h+var_1970]; int *
0x180073a79  lea     rdx, off_180130D60; struct ColumnDefinition *
0x180073a80  mov     [rsp+19B0h+var_1970], r12d
0x180073a85  call    ?FindColumnEx@DatabaseVolumeSession@@QEBAKPEBUColumnDefinition@@PEAH@Z; DatabaseVolumeSession::FindColumnEx(ColumnDefinition const *,int *)
0x180073a8a  mov     [rbp+18B0h+var_185C], eax
0x180073a8d  cmp     [rsp+19B0h+var_1970], r12d
0x180073a92  jnz     short loc_180073AA6
0x180073a94  mov     r8d, 0CBh
0x180073a9a  lea     rdx, aOnecoreuapBase_62; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180073aa1  call    Log_AssertionEvent_2
0x180073aa6  mov     rcx, [rsi+7F8h]; this
0x180073aad  lea     r8, [rsp+19B0h+var_1970]; int *
0x180073ab2  lea     rdx, off_180130EE0; struct ColumnDefinition *
0x180073ab9  mov     [rsp+19B0h+var_1970], r12d
0x180073abe  call    ?FindColumnEx@DatabaseVolumeSession@@QEBAKPEBUColumnDefinition@@PEAH@Z; DatabaseVolumeSession::FindColumnEx(ColumnDefinition const *,int *)
0x180073ac3  mov     [rbp+18B0h+var_1858], eax
0x180073ac6  cmp     [rsp+19B0h+var_1970], r12d
0x180073acb  jnz     short loc_180073ADF
0x180073acd  mov     r8d, 0CBh
0x180073ad3  lea     rdx, aOnecoreuapBase_62; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180073ada  call    Log_AssertionEvent_2
0x180073adf  mov     rcx, [rsi+7F8h]; this
0x180073ae6  lea     r8, [rsp+19B0h+var_1970]; int *
0x180073aeb  lea     rdx, off_180130EC0; struct ColumnDefinition *
0x180073af2  mov     [rsp+19B0h+var_1970], r12d
0x180073af7  call    ?FindColumnEx@DatabaseVolumeSession@@QEBAKPEBUColumnDefinition@@PEAH@Z; DatabaseVolumeSession::FindColumnEx(ColumnDefinition const *,int *)
0x180073afc  mov     [rbp+18B0h+var_1854], eax
0x180073aff  cmp     [rsp+19B0h+var_1970], r12d
0x180073b04  jnz     short loc_180073B18
0x180073b06  mov     r8d, 0CBh
0x180073b0c  lea     rdx, aOnecoreuapBase_62; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180073b13  call    Log_AssertionEvent_2
0x180073b18  xor     r9d, r9d
0x180073b1b  mov     [rsp+19B0h+var_193C], 1
0x180073b20  mov     [rsp+19B0h+var_1970], r12d
0x180073b25  test    r14, r14
0x180073b28  jz      loc_180073BC4
0x180073b2e  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180073b32  inc     rcx; unsigned __int64
0x180073b35  cmp     [r14+rcx*2], r9w
0x180073b3a  jnz     short loc_180073B32
0x180073b3c  lea     rdx, [rsp+19B0h+var_1970]; unsigned int *
0x180073b41  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x180073b46  mov     ebx, eax
0x180073b48  test    eax, eax
0x180073b4a  jns     short loc_180073BBB
0x180073b4c  mov     r9d, 48Eh
0x180073b52  lea     r8, aOnecoreuapBase_43; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180073b59  mov     edx, 1
0x180073b5e  mov     ecx, eax
0x180073b60  call    Log_HREvent
0x180073b65  lea     rcx, [rsp+19B0h+sesid]; this
0x180073b6a  call    ??1auto_JET_TABLEID@@QEAA@XZ; auto_JET_TABLEID::~auto_JET_TABLEID(void)
0x180073b6f  lea     rcx, [rsp+19B0h+var_1968]; this
0x180073b74  call    ?Unlock@BackoffContext@@QEAAXXZ; BackoffContext::Unlock(void)
0x180073b79  lea     rcx, [rbp+18B0h+var_18D0]; void *
0x180073b7d  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x180073b82  lea     rcx, [rsp+19B0h+var_1958]
0x180073b87  call    ??1?$CComPtrBase@UISODACompletionCallback@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(void)
0x180073b8c  mov     rcx, [rsp+19B0h+Block]; Block
0x180073b91  lea     rax, [rsp+19B0h+Block]
  ... truncated ...
```
