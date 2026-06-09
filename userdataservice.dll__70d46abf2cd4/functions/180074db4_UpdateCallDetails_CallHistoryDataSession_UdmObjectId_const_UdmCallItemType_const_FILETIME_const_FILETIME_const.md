# UpdateCallDetails(CallHistoryDataSession *,UdmObjectId const &,UdmCallItemType const *,_FILETIME const *,_FILETIME const *,int const *,ushort const *,ushort const * const,ulong const *,ushort const * const,ushort const * const,_FILETIME const *,int const *)

- ea: `0x180074db4`
- end: `0x180075f8f`
- name: `?UpdateCallDetails@@YAJPEAVCallHistoryDataSession@@AEBUUdmObjectId@@PEBW4UdmCallItemType@@PEBU_FILETIME@@3PEBHPEBGQEBGPEBK6634@Z`
- size: `4571`
- prototype: `__int64 __usercall@<rax>(struct CallHistoryDataSession *this@<rcx>, const struct UdmObjectId *@<rdx>, const enum UdmCallItemType *@<r8>, const struct _FILETIME *@<r9>, const struct _FILETIME *, const int *, const unsigned __int16 *, const unsigned __int16 *const, const unsigned int *, const unsigned __int16 *const, const unsigned __int16 *const, const struct _FILETIME *, const int *)`
- caller_count: `1`
- callee_count: `19`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x1800e28ec`

## callees

- `0x180008f0c`
- `0x18003bf04`
- `0x180066860`
- `0x18006b13c`
- `0x180074db4`
- `0x180075f98`
- `0x180076604`
- `0x180076664`
- `0x1800a0174`
- `0x1800a1270`
- `0x1800a1568`
- `0x1800a55ac`
- `0x1800da0d0`
- `0x1800dbc30`
- `0x1800e1380`
- `0x1800e2758`
- `0x1800e98c4`
- `0x18012c76a`
- `0x18012c7b0`

## import_xrefs

- `ESENT!JetOpenTableA` at `0x180074e8f`
- `ESENT!JetOpenTableA` at `0x180074e8f`
- `ESENT!JetRetrieveColumns` at `0x1800757ce`
- `ESENT!JetRetrieveColumns` at `0x1800757ce`
- `ESENT!JetSetColumns` at `0x180075ddc`
- `ESENT!JetSetColumns` at `0x180075ddc`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800751a0`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800751a0`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800751b8`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800751b8`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800751a9`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800751a9`
- `api-ms-win-core-synch-l1-1-0!TryAcquireSRWLockShared` at `0x18007518f`
- `api-ms-win-core-synch-l1-1-0!TryAcquireSRWLockShared` at `0x18007518f`

## string_xrefs

- `0x180074eea`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\datasession.cpp`
- `0x180074f23`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\datasession.cpp`
- `0x180074f5c`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\datasession.cpp`
- `0x180074f95`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\datasession.cpp`
- `0x180074fce`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\datasession.cpp`
- `0x180075007`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\datasession.cpp`
- `0x180075040`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\datasession.cpp`
- `0x180075079`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\datasession.cpp`
- `0x1800750b2`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\datasession.cpp`
- `0x1800750eb`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\datasession.cpp`
- `0x180075124`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\datasession.cpp`
- `0x18007515d`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\datasession.cpp`
- `0x18007517a`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\datasession.cpp`
- `0x180074ea6`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\callhistory.cpp`
- `0x180075d84`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\callhistory.cpp`
- `0x180075e5b`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\callhistory.cpp`
- `0x180075f33`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\callhistory.cpp`

## pseudocode

```c
__int64 __fastcall UpdateCallDetails(
        struct CallHistoryDataSession *this,
        const struct UdmObjectId *a2,
        const enum UdmCallItemType *a3,
        const struct _FILETIME *a4,
        const struct _FILETIME *a5,
        const int *a6,
        unsigned __int16 *a7,
        unsigned __int16 *a8,
        const unsigned int *a9,
        unsigned __int16 *a10,
        unsigned __int16 *a11,
        const struct _FILETIME *a12,
        const int *a13)
{
  int v16; // edi
  unsigned int v17; // r14d
  JET_DBID v18; // edx
  RTL_SRWLOCK *v19; // rbx
  JET_SESID v20; // rcx
  JET_ERR v21; // eax
  unsigned int HresultFromJetError; // ebx
  DatabaseVolumeSession *v23; // rcx
  __int64 v24; // rcx
  DatabaseVolumeSession *v25; // rcx
  __int64 v26; // rcx
  DatabaseVolumeSession *v27; // rcx
  __int64 v28; // rcx
  DatabaseVolumeSession *v29; // rcx
  __int64 v30; // rcx
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
  unsigned int v47; // edx
  __int64 v48; // rax
  int v49; // r8d
  __int64 v50; // rcx
  int v51; // eax
  int v52; // ecx
  unsigned int v53; // r14d
  JET_ERR v54; // eax
  __int64 v55; // rbx
  unsigned int v56; // r8d
  unsigned int v57; // edi
  int v58; // eax
  __int64 v59; // rax
  __int64 v60; // rcx
  __int64 v61; // rax
  __int64 v62; // rcx
  __int64 v63; // rax
  __int64 v64; // rdi
  __int64 v65; // rcx
  unsigned int v66; // r8d
  __int128 v67; // xmm1
  __int128 v68; // xmm0
  unsigned int v69; // eax
  __int64 v70; // rcx
  unsigned __int16 *v71; // rax
  int v72; // ecx
  int v73; // edx
  int inited; // r14d
  unsigned __int16 *v75; // rax
  int v76; // ecx
  int v77; // edx
  __int64 v78; // rax
  __int64 v79; // rcx
  unsigned __int16 *v80; // rax
  int v81; // ecx
  int v82; // edx
  unsigned __int16 *v83; // rax
  int v84; // ecx
  int v85; // edx
  __int64 v86; // rax
  __int64 v87; // rcx
  __int64 v88; // rax
  __int128 v89; // xmm1
  __int64 v90; // rcx
  __int64 v91; // r9
  JET_ERR v92; // eax
  int v93; // eax
  unsigned int v94; // edi
  int v95; // eax
  DatabaseVolumeSession *v96; // rcx
  __int64 v97; // r9
  __int64 v98; // rdx
  __int64 v100; // rcx
  int v101; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v102; // [rsp+48h] [rbp-B8h]
  __int128 v103; // [rsp+58h] [rbp-A8h]
  __int128 v104; // [rsp+68h] [rbp-98h]
  unsigned __int8 v105; // [rsp+78h] [rbp-88h] BYREF
  char v106; // [rsp+79h] [rbp-87h] BYREF
  __int64 v107; // [rsp+80h] [rbp-80h] BYREF
  RTL_SRWLOCK *v108; // [rsp+88h] [rbp-78h]
  char v109; // [rsp+90h] [rbp-70h] BYREF
  JET_COLUMNID Column; // [rsp+94h] [rbp-6Ch]
  int v111; // [rsp+98h] [rbp-68h] BYREF
  unsigned int v112; // [rsp+9Ch] [rbp-64h]
  unsigned int v113; // [rsp+A0h] [rbp-60h]
  unsigned int v114; // [rsp+A4h] [rbp-5Ch]
  unsigned int v115; // [rsp+A8h] [rbp-58h] BYREF
  unsigned int v116; // [rsp+ACh] [rbp-54h]
  unsigned int v117; // [rsp+B0h] [rbp-50h]
  unsigned int v118; // [rsp+B4h] [rbp-4Ch]
  int v119; // [rsp+B8h] [rbp-48h] BYREF
  unsigned int v120; // [rsp+BCh] [rbp-44h]
  unsigned int v121; // [rsp+C0h] [rbp-40h]
  unsigned int v122; // [rsp+C4h] [rbp-3Ch]
  unsigned int v123; // [rsp+C8h] [rbp-38h]
  unsigned int v124; // [rsp+CCh] [rbp-34h]
  unsigned int v125; // [rsp+D0h] [rbp-30h] BYREF
  JET_SESID sesid; // [rsp+D8h] [rbp-28h] BYREF
  JET_TABLEID tableid; // [rsp+E0h] [rbp-20h] BYREF
  int v128; // [rsp+E8h] [rbp-18h] BYREF
  __int64 v129; // [rsp+F0h] [rbp-10h] BYREF
  __int128 v130; // [rsp+F8h] [rbp-8h]
  __int64 v131; // [rsp+108h] [rbp+8h]
  __int64 v132; // [rsp+110h] [rbp+10h]
  JET_TABLEID v133; // [rsp+118h] [rbp+18h]
  int v134; // [rsp+120h] [rbp+20h]
  __int64 v135; // [rsp+140h] [rbp+40h] BYREF
  __int64 v136; // [rsp+148h] [rbp+48h] BYREF
  __int64 v137; // [rsp+150h] [rbp+50h] BYREF
  const enum UdmCallItemType *v138; // [rsp+158h] [rbp+58h]
  unsigned __int16 *v139; // [rsp+160h] [rbp+60h]
  unsigned __int16 *v140; // [rsp+168h] [rbp+68h]
  unsigned __int16 *v141; // [rsp+170h] [rbp+70h]
  unsigned __int16 *v142; // [rsp+178h] [rbp+78h]
  JET_RETRIEVECOLUMN pretrievecolumn; // [rsp+180h] [rbp+80h] BYREF
  unsigned int v144; // [rsp+1B0h] [rbp+B0h]
  int v145; // [rsp+1B4h] [rbp+B4h]
  __int64 *v146; // [rsp+1B8h] [rbp+B8h]
  int v147; // [rsp+1C0h] [rbp+C0h]
  __int64 v148; // [rsp+1C4h] [rbp+C4h]
  unsigned int ibLongValue; // [rsp+1CCh] [rbp+CCh]
  int v150; // [rsp+1D0h] [rbp+D0h]
  int v151; // [rsp+1D4h] [rbp+D4h]
  JET_ERR err; // [rsp+1D8h] [rbp+D8h]
  int v153; // [rsp+1DCh] [rbp+DCh]
  unsigned int v154; // [rsp+1E0h] [rbp+E0h]
  int v155; // [rsp+1E4h] [rbp+E4h]
  __int64 *v156; // [rsp+1E8h] [rbp+E8h]
  int v157; // [rsp+1F0h] [rbp+F0h]
  __int64 v158; // [rsp+1F4h] [rbp+F4h]
  unsigned int v159; // [rsp+1FCh] [rbp+FCh]
  int v160; // [rsp+200h] [rbp+100h]
  int v161; // [rsp+204h] [rbp+104h]
  JET_ERR v162; // [rsp+208h] [rbp+108h]
  int v163; // [rsp+20Ch] [rbp+10Ch]
  unsigned int v164; // [rsp+210h] [rbp+110h]
  int v165; // [rsp+214h] [rbp+114h]
  unsigned int *v166; // [rsp+218h] [rbp+118h]
  int v167; // [rsp+220h] [rbp+120h]
  __int64 v168; // [rsp+224h] [rbp+124h]
  unsigned int v169; // [rsp+22Ch] [rbp+12Ch]
  int v170; // [rsp+230h] [rbp+130h]
  int v171; // [rsp+234h] [rbp+134h]
  JET_ERR v172; // [rsp+238h] [rbp+138h]
  int v173; // [rsp+23Ch] [rbp+13Ch]
  unsigned int v174; // [rsp+240h] [rbp+140h]
  int v175; // [rsp+244h] [rbp+144h]
  _BYTE *v176; // [rsp+248h] [rbp+148h]
  int v177; // [rsp+250h] [rbp+150h]
  __int64 v178; // [rsp+254h] [rbp+154h]
  unsigned int v179; // [rsp+25Ch] [rbp+15Ch]
  int v180; // [rsp+260h] [rbp+160h]
  int v181; // [rsp+264h] [rbp+164h]
  JET_ERR v182; // [rsp+268h] [rbp+168h]
  int v183; // [rsp+26Ch] [rbp+16Ch]
  unsigned int v184; // [rsp+270h] [rbp+170h]
  int v185; // [rsp+274h] [rbp+174h]
  _BYTE *v186; // [rsp+278h] [rbp+178h]
  int v187; // [rsp+280h] [rbp+180h]
  __int64 v188; // [rsp+284h] [rbp+184h]
  unsigned int v189; // [rsp+28Ch] [rbp+18Ch]
  int v190; // [rsp+290h] [rbp+190h]
  int v191; // [rsp+294h] [rbp+194h]
  JET_ERR v192; // [rsp+298h] [rbp+198h]
  int v193; // [rsp+29Ch] [rbp+19Ch]
  unsigned int v194; // [rsp+2A0h] [rbp+1A0h]
  int v195; // [rsp+2A4h] [rbp+1A4h]
  int *v196; // [rsp+2A8h] [rbp+1A8h]
  int v197; // [rsp+2B0h] [rbp+1B0h]
  __int64 v198; // [rsp+2B4h] [rbp+1B4h]
  unsigned int v199; // [rsp+2BCh] [rbp+1BCh]
  int v200; // [rsp+2C0h] [rbp+1C0h]
  int v201; // [rsp+2C4h] [rbp+1C4h]
  JET_ERR v202; // [rsp+2C8h] [rbp+1C8h]
  int v203; // [rsp+2CCh] [rbp+1CCh]
  unsigned int v204; // [rsp+2D0h] [rbp+1D0h]
  int v205; // [rsp+2D4h] [rbp+1D4h]
  _BYTE *v206; // [rsp+2D8h] [rbp+1D8h]
  int v207; // [rsp+2E0h] [rbp+1E0h]
  __int64 v208; // [rsp+2E4h] [rbp+1E4h]
  unsigned int v209; // [rsp+2ECh] [rbp+1ECh]
  int v210; // [rsp+2F0h] [rbp+1F0h]
  int v211; // [rsp+2F4h] [rbp+1F4h]
  JET_ERR v212; // [rsp+2F8h] [rbp+1F8h]
  int v213; // [rsp+2FCh] [rbp+1FCh]
  unsigned int v214; // [rsp+300h] [rbp+200h]
  int v215; // [rsp+304h] [rbp+204h]
  _BYTE *v216; // [rsp+308h] [rbp+208h]
  int v217; // [rsp+310h] [rbp+210h]
  __int64 v218; // [rsp+314h] [rbp+214h]
  unsigned int v219; // [rsp+31Ch] [rbp+21Ch]
  int v220; // [rsp+320h] [rbp+220h]
  int v221; // [rsp+324h] [rbp+224h]
  JET_ERR v222; // [rsp+328h] [rbp+228h]
  int v223; // [rsp+32Ch] [rbp+22Ch]
  unsigned int v224; // [rsp+330h] [rbp+230h]
  int v225; // [rsp+334h] [rbp+234h]
  __int64 *v226; // [rsp+338h] [rbp+238h]
  int v227; // [rsp+340h] [rbp+240h]
  __int64 v228; // [rsp+344h] [rbp+244h]
  unsigned int v229; // [rsp+34Ch] [rbp+24Ch]
  int v230; // [rsp+350h] [rbp+250h]
  int v231; // [rsp+354h] [rbp+254h]
  JET_ERR v232; // [rsp+358h] [rbp+258h]
  int v233; // [rsp+35Ch] [rbp+25Ch]
  unsigned int v234; // [rsp+360h] [rbp+260h]
  int v235; // [rsp+364h] [rbp+264h]
  unsigned __int8 *v236; // [rsp+368h] [rbp+268h]
  int v237; // [rsp+370h] [rbp+270h]
  __int64 v238; // [rsp+374h] [rbp+274h]
  unsigned int v239; // [rsp+37Ch] [rbp+27Ch]
  int v240; // [rsp+380h] [rbp+280h]
  int v241; // [rsp+384h] [rbp+284h]
  JET_ERR v242; // [rsp+388h] [rbp+288h]
  int v243; // [rsp+38Ch] [rbp+28Ch]
  JET_SETCOLUMN psetcolumn[11]; // [rsp+390h] [rbp+290h] BYREF
  _BYTE v245[176]; // [rsp+550h] [rbp+450h] BYREF
  _BYTE v246[208]; // [rsp+600h] [rbp+500h] BYREF
  _BYTE v247[208]; // [rsp+6D0h] [rbp+5D0h] BYREF
  _BYTE v248[272]; // [rsp+7A0h] [rbp+6A0h] BYREF

  v139 = a7;
  v140 = a8;
  v16 = 0;
  v17 = 0;
  v18 = *((_DWORD *)this + 514);
  v19 = (RTL_SRWLOCK *)(*((_QWORD *)this + 255) + 120LL);
  v141 = a10;
  v142 = a11;
  v20 = *((_QWORD *)this + 256);
  v138 = a3;
  v135 = 0;
  v136 = 0;
  v128 = 0;
  v125 = 0;
  v119 = 0;
  v137 = 0;
  v105 = 0;
  v107 = 0;
  v108 = v19;
  sesid = v20;
  tableid = -1;
  v21 = JetOpenTableA(v20, v18, "CallHistory", 0, 0, 8u, &tableid);
  if ( v21 < 0 )
  {
    HresultFromJetError = MakeHresultFromJetError(v21);
    Log_HREvent(
      HresultFromJetError,
      0,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\callhistory.cpp",
      2299);
LABEL_128:
    auto_JET_TABLEID::~auto_JET_TABLEID((auto_JET_TABLEID *)&sesid);
    BackoffContext::Unlock((BackoffContext *)&v107);
    return HresultFromJetError;
  }
  v23 = (DatabaseVolumeSession *)*((_QWORD *)this + 255);
  v101 = 0;
  Column = DatabaseVolumeSession::FindColumnEx(v23, (const struct ColumnDefinition *)&off_180130C00, &v101);
  if ( !v101 )
    Log_AssertionEvent_2(
      v24,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\datasession.cpp",
      203);
  v25 = (DatabaseVolumeSession *)*((_QWORD *)this + 255);
  v101 = 0;
  v112 = DatabaseVolumeSession::FindColumnEx(v25, (const struct ColumnDefinition *)&off_180130C80, &v101);
  if ( !v101 )
    Log_AssertionEvent_2(
      v26,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\datasession.cpp",
      203);
  v27 = (DatabaseVolumeSession *)*((_QWORD *)this + 255);
  v101 = 0;
  v113 = DatabaseVolumeSession::FindColumnEx(v27, (const struct ColumnDefinition *)&off_180130C60, &v101);
  if ( !v101 )
    Log_AssertionEvent_2(
      v28,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\datasession.cpp",
      203);
  v29 = (DatabaseVolumeSession *)*((_QWORD *)this + 255);
  v101 = 0;
  v114 = DatabaseVolumeSession::FindColumnEx(v29, (const struct ColumnDefinition *)&off_180130C20, &v101);
  if ( !v101 )
    Log_AssertionEvent_2(
      v30,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\datasession.cpp",
      203);
  v31 = (DatabaseVolumeSession *)*((_QWORD *)this + 255);
  v101 = 0;
  v116 = DatabaseVolumeSession::FindColumnEx(v31, (const struct ColumnDefinition *)&off_180130C40, &v101);
  if ( !v101 )
    Log_AssertionEvent_2(
      v32,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\datasession.cpp",
      203);
  v33 = (DatabaseVolumeSession *)*((_QWORD *)this + 255);
  v101 = 0;
  v117 = DatabaseVolumeSession::FindColumnEx(v33, (const struct ColumnDefinition *)&off_180130DA0, &v101);
  if ( !v101 )
    Log_AssertionEvent_2(
      v34,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\datasession.cpp",
      203);
  v35 = (DatabaseVolumeSession *)*((_QWORD *)this + 255);
  v101 = 0;
  v118 = DatabaseVolumeSession::FindColumnEx(v35, (const struct ColumnDefinition *)&off_180130DC0, &v101);
  if ( !v101 )
    Log_AssertionEvent_2(
      v36,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\datasession.cpp",
      203);
  v37 = (DatabaseVolumeSession *)*((_QWORD *)this + 255);
  v101 = 0;
  v120 = DatabaseVolumeSession::FindColumnEx(v37, (const struct ColumnDefinition *)&off_180130DE0, &v101);
  if ( !v101 )
    Log_AssertionEvent_2(
      v38,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\datasession.cpp",
      203);
  v39 = (DatabaseVolumeSession *)*((_QWORD *)this + 255);
  v101 = 0;
  v121 = DatabaseVolumeSession::FindColumnEx(v39, (const struct ColumnDefinition *)&off_180130E40, &v101);
  if ( !v101 )
    Log_AssertionEvent_2(
      v40,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\datasession.cpp",
      203);
  v41 = (DatabaseVolumeSession *)*((_QWORD *)this + 255);
  v101 = 0;
  v122 = DatabaseVolumeSession::FindColumnEx(v41, (const struct ColumnDefinition *)&off_180130E60, &v101);
  if ( !v101 )
    Log_AssertionEvent_2(
      v42,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\datasession.cpp",
      203);
  v43 = (DatabaseVolumeSession *)*((_QWORD *)this + 255);
  v101 = 0;
  v123 = DatabaseVolumeSession::FindColumnEx(v43, (const struct ColumnDefinition *)&off_180130E80, &v101);
  if ( !v101 )
    Log_AssertionEvent_2(
      v44,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\datasession.cpp",
      203);
  v45 = (DatabaseVolumeSession *)*((_QWORD *)this + 255);
  v101 = 0;
  v124 = DatabaseVolumeSession::FindColumnEx(v45, (const struct ColumnDefinition *)&off_180130F60, &v101);
  if ( !v101 )
    Log_AssertionEvent_2(
      v46,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\datasession.cpp",
      203);
  while ( 1 )
  {
    if ( v16 )
      Log_AssertionEvent_2(
        v46,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\datasession.cpp",
        2208);
    if ( v17 >= 2 )
    {
      AcquireSRWLockExclusive(v19);
      LODWORD(v107) = 2;
    }
    else
    {
      if ( !TryAcquireSRWLockShared(v19) )
      {
        Sleep(0x64u);
        AcquireSRWLockShared(v19);
      }
      LODWORD(v107) = 1;
    }
    v48 = *((_QWORD *)this + 256);
    *(_QWORD *)&v130 = tableid;
    v133 = tableid;
    v129 = v48;
    *((_QWORD *)&v130 + 1) = v48;
    v131 = 0;
    v132 = v48;
    v134 = 0;
    HresultFromJetError = UpdateContext::Start((UpdateContext *)&v129, v47);
    if ( (HresultFromJetError & 0x80000000) != 0 )
    {
      v97 = 2319;
      v98 = 1;
LABEL_126:
      v100 = HresultFromJetError;
      goto LABEL_127;
    }
    v50 = *((_QWORD *)this + 256);
    v101 = 0;
    v51 = SeekIndexToKey<unsigned long>(v50, tableid, v49, (int)a2 + 8, (__int64)&v101, 0);
    HresultFromJetError = v51;
    if ( v51 < 0 )
    {
      v97 = 2327;
      v98 = 1;
      goto LABEL_124;
    }
    if ( !v101 )
    {
      if ( (Microsoft_Windows_UserDataAccess_UserDataServiceEnableBits & 0x10) != 0 )
        McTemplateU0pqq_EventWriteTransfer(
          v52,
          (unsigned int)UpdateCallNotFound,
          (_DWORD)this,
          *((_DWORD *)a2 + 1),
          *((_DWORD *)a2 + 2));
      v97 = 2332;
      v98 = 0;
      HresultFromJetError = -2147023728;
      goto LABEL_126;
    }
    pretrievecolumn.columnid = Column;
    *(&pretrievecolumn.columnid + 1) = 0;
    pretrievecolumn.pvData = &v128;
    pretrievecolumn.columnidNextTagged = 0;
    *(&pretrievecolumn.err + 1) = 0;
    v144 = v112;
    pretrievecolumn.cbData = 4;
    pretrievecolumn.err = _mm_cvtsi128_si32(_mm_srli_si128((__m128i)0LL, 8));
    pretrievecolumn.itagSequence = 1;
    v145 = 0;
    v146 = &v136;
    v151 = 0;
    v153 = 0;
    v154 = v113;
    v147 = 8;
    pretrievecolumn.ibLongValue = _mm_cvtsi128_si32(_mm_srli_si128((__m128i)0LL, 12));
    err = pretrievecolumn.err;
    v150 = 1;
    v155 = 0;
    v156 = &v135;
    v161 = 0;
    v163 = 0;
    *(_QWORD *)&pretrievecolumn.cbActual = 0;
    v164 = v116;
    ibLongValue = pretrievecolumn.ibLongValue;
    v162 = pretrievecolumn.err;
    v148 = 0;
    v165 = 0;
    v157 = 8;
    v158 = 0;
    v159 = pretrievecolumn.ibLongValue;
    v160 = 1;
    v53 = v118;
    v166 = &v125;
    v171 = 0;
    v173 = 0;
    v174 = v117;
    v172 = pretrievecolumn.err;
    v167 = 4;
    v175 = 0;
    v176 = v246;
    v181 = 0;
    v183 = 0;
    v170 = 1;
    v169 = pretrievecolumn.ibLongValue;
    v182 = pretrievecolumn.err;
    v177 = 202;
    v185 = 0;
    v186 = v247;
    v191 = 0;
    v179 = pretrievecolumn.ibLongValue;
    v193 = 0;
    v168 = 0;
    v194 = v120;
    v192 = pretrievecolumn.err;
    v178 = 0;
    v195 = 0;
    v189 = pretrievecolumn.ibLongValue;
    v196 = &v119;
    v188 = 0;
    v201 = 0;
    v180 = 1;
    v184 = v118;
    v187 = 202;
    v190 = 1;
    v197 = 4;
    v198 = 0;
    v199 = pretrievecolumn.ibLongValue;
    v200 = 1;
    v203 = 0;
    v204 = v121;
    v202 = pretrievecolumn.err;
    v207 = 162;
    v205 = 0;
    v206 = v245;
    v211 = 0;
    v213 = 0;
    v214 = v122;
    v210 = 1;
    v212 = pretrievecolumn.err;
    v217 = 258;
    v215 = 0;
    v216 = v248;
    v221 = 0;
    v223 = 0;
    v224 = v123;
    v220 = 1;
    v209 = pretrievecolumn.ibLongValue;
    v222 = pretrievecolumn.err;
    v227 = 8;
    v225 = 0;
    v226 = &v137;
    v231 = 0;
    v233 = 0;
    v208 = 0;
    v234 = v124;
    v219 = pretrievecolumn.ibLongValue;
    v232 = pretrievecolumn.err;
    v218 = 0;
    v102 = 0;
    v235 = 0;
    v228 = 0;
    v229 = pretrievecolumn.ibLongValue;
    v230 = 1;
    v103 = 0;
    v104 = 0;
    v236 = &v105;
    v241 = 0;
    v237 = 1;
    v240 = 1;
    v239 = pretrievecolumn.ibLongValue;
    v243 = 0;
    v238 = 0;
    v242 = pretrievecolumn.err;
    v54 = JetRetrieveColumns(sesid, tableid, &pretrievecolumn, 0xBu);
    if ( v54 < 0 )
    {
      v51 = MakeHresultFromJetError(v54);
      v97 = 2352;
LABEL_115:
      HresultFromJetError = v51;
      v98 = 0;
LABEL_124:
      v100 = (unsigned int)v51;
LABEL_127:
      Log_HREvent(
        v100,
        v98,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\callhistory.cpp",
        v97);
      UpdateContext::~UpdateContext((UpdateContext *)&v129);
      BackoffContext::Unlock((BackoffContext *)&v107);
      goto LABEL_128;
    }
    v55 = v135;
    psetcolumn[0].columnid = 0;
    memset_0(&psetcolumn[0].pvData, 0, 0x1B0u);
    v56 = v125;
    v57 = 0;
    v115 = v125;
    v111 = 0;
    v106 = 1;
    if ( v138 && (pretrievecolumn.err || *(_DWORD *)v138 != v128) )
    {
      v58 = *(_DWORD *)v138;
      v57 = 1;
      psetcolumn[0].columnid = Column;
      v102 = 0;
      *(&psetcolumn[0].columnid + 1) = 0;
      psetcolumn[0].pvData = &v111;
      v111 = v58;
      v103 = 0;
      *(_QWORD *)&psetcolumn[0].grbit = 0;
      psetcolumn[0].cbData = 4;
      psetcolumn[0].itagSequence = 1;
      *(_QWORD *)&psetcolumn[0].err = 0;
    }
    if ( a5 && (err || *a5 != v136) )
    {
      *(_QWORD *)&v102 = v112;
      v59 = v57++;
      *((_QWORD *)&v102 + 1) = a5;
      v60 = v59;
      *(_QWORD *)((char *)&v103 + 4) = 0;
      LODWORD(v103) = 8;
      *(_OWORD *)&psetcolumn[v60].columnid = v102;
      HIDWORD(v103) = 1;
      *(_OWORD *)&psetcolumn[v60].cbData = v103;
      *(_QWORD *)&psetcolumn[v60].err = 0;
    }
    if ( a4 && (v162 || *a4 != v55) )
    {
      v55 = (__int64)*a4;
      *(_QWORD *)&v102 = v113;
      v61 = v57++;
      *((_QWORD *)&v102 + 1) = a4;
      v62 = v61;
      *(_QWORD *)((char *)&v103 + 4) = 0;
      LODWORD(v103) = 8;
      *(_OWORD *)&psetcolumn[v62].columnid = v102;
      HIDWORD(v103) = 1;
      *(_OWORD *)&psetcolumn[v62].cbData = v103;
      *(_QWORD *)&psetcolumn[v62].err = 0;
    }
    if ( a6 && (v172 || *a6 != (v56 & 1)) )
    {
      v63 = v57;
      v64 = v57 + 1;
      DWORD1(v102) = 0;
      *(_QWORD *)((char *)&v103 + 4) = 0;
      HIDWORD(v103) = 1;
      v65 = v63;
      if ( *a6 )
      {
        LODWORD(v103) = 1;
        *((_QWORD *)&v102 + 1) = &v106;
        v66 = v56 | 1;
      }
      else
      {
        *((_QWORD *)&v102 + 1) = 0;
        v66 = v56 & 0xFFFFFFFE;
        LODWORD(v103) = 0;
      }
      v67 = v103;
      LODWORD(v102) = v114;
      v68 = v102;
      *((_QWORD *)&v102 + 1) = &v115;
      v69 = v116;
      *(_OWORD *)&psetcolumn[v65].columnid = v68;
      DWORD1(v102) = 0;
      *(_OWORD *)&psetcolumn[v65].cbData = v67;
      *(_QWORD *)&psetcolumn[v65].err = 0;
      v70 = v64;
      LODWORD(v102) = v69;
      v57 = v64 + 1;
      *(_QWORD *)((char *)&v103 + 4) = 0;
      LODWORD(v103) = 4;
      *(_OWORD *)&psetcolumn[v70].columnid = v102;
      HIDWORD(v103) = 1;
      v115 = v66;
      *(_OWORD *)&psetcolumn[v70].cbData = v103;
      *(_QWORD *)&psetcolumn[v70].err = 0;
    }
    if ( v139 )
    {
      if ( v182 )
        goto LABEL_63;
      v71 = v139;
      do
      {
        v72 = *(unsigned __int16 *)((char *)v71 + v246 - (_BYTE *)v139);
        v73 = *v71 - v72;
        if ( v73 )
          break;
        ++v71;
      }
      while ( v72 );
      if ( v73 )
      {
LABEL_63:
        inited = InitSetColumn(&psetcolumn[v57], v117, v139);
        if ( inited < 0 )
        {
          v91 = 2407;
          goto LABEL_106;
        }
        v53 = v118;
        ++v57;
      }
    }
    if ( v140 )
    {
      if ( v192 )
        goto LABEL_71;
      v75 = v140;
      do
      {
        v76 = *(unsigned __int16 *)((char *)v75 + v247 - (_BYTE *)v140);
        v77 = *v75 - v76;
        if ( v77 )
          break;
        ++v75;
      }
      while ( v76 );
      if ( v77 )
      {
LABEL_71:
        inited = InitSetColumn(&psetcolumn[v57], v53, v140);
        if ( inited < 0 )
        {
          v91 = 2417;
          goto LABEL_106;
        }
        ++v57;
      }
    }
    if ( a9 && (v202 || *a9 != v119) )
    {
      *(_QWORD *)&v102 = v120;
      v78 = v57++;
      *((_QWORD *)&v102 + 1) = a9;
      v79 = v78;
      *(_QWORD *)((char *)&v103 + 4) = 0;
      LODWORD(v103) = 4;
      *(_OWORD *)&psetcolumn[v79].columnid = v102;
      HIDWORD(v103) = 1;
      *(_OWORD *)&psetcolumn[v79].cbData = v103;
      *(_QWORD *)&psetcolumn[v79].err = 0;
    }
    if ( v141 )
    {
      if ( v212 )
        goto LABEL_83;
      v80 = v141;
      do
      {
        v81 = *(unsigned __int16 *)((char *)v80 + v245 - (_BYTE *)v141);
        v82 = *v80 - v81;
        if ( v82 )
          break;
        ++v80;
      }
      while ( v81 );
      if ( v82 )
      {
LABEL_83:
        inited = InitSetColumn(&psetcolumn[v57], v121, v141);
        if ( inited < 0 )
        {
          v91 = 2436;
          goto LABEL_106;
        }
        ++v57;
      }
    }
    if ( v142 )
    {
      if ( v222 )
        goto LABEL_91;
      v83 = v142;
      do
      {
        v84 = *(unsigned __int16 *)((char *)v83 + v248 - (_BYTE *)v142);
        v85 = *v83 - v84;
        if ( v85 )
          break;
        ++v83;
      }
      while ( v84 );
      if ( v85 )
      {
LABEL_91:
        inited = InitSetColumn(&psetcolumn[v57], v122, v142);
        if ( inited >= 0 )
        {
          ++v57;
          goto LABEL_93;
        }
        v91 = 2446;
LABEL_106:
        Log_HREvent(
          (unsigned int)inited,
          1,
          "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\callhistory.cpp",
          v91);
        UpdateContext::~UpdateContext((UpdateContext *)&v129);
        BackoffContext::Unlock((BackoffContext *)&v107);
        HresultFromJetError = inited;
        goto LABEL_128;
      }
    }
LABEL_93:
    if ( a12 && (v232 || *a12 != v137) )
    {
      *(_QWORD *)&v102 = v123;
      v86 = v57++;
      *((_QWORD *)&v102 + 1) = a12;
      v87 = v86;
      *(_QWORD *)((char *)&v103 + 4) = 0;
      LODWORD(v103) = 8;
      *(_OWORD *)&psetcolumn[v87].columnid = v102;
      HIDWORD(v103) = 1;
      *(_OWORD *)&psetcolumn[v87].cbData = v103;
      *(_QWORD *)&psetcolumn[v87].err = 0;
    }
    if ( a13 && (v242 || *a13 != v105) )
    {
      *((_QWORD *)&v102 + 1) = &v109;
      *(_QWORD *)&v102 = v124;
      v88 = v57++;
      *(_QWORD *)((char *)&v103 + 4) = 0;
      LODWORD(v103) = 1;
      HIDWORD(v103) = 1;
      v89 = v103;
      v90 = v88;
      *(_OWORD *)&psetcolumn[v90].columnid = v102;
      *(_OWORD *)&psetcolumn[v90].cbData = v89;
      *(_QWORD *)&psetcolumn[v90].err = 0;
    }
    if ( !v57 )
      break;
    v101 = 0;
    inited = UpdateContext::MaybePrepare((UpdateContext *)&v129, 2u, &v101);
    if ( inited < 0 )
    {
      v91 = 2479;
      goto LABEL_106;
    }
    if ( !v101 )
    {
      v92 = JetSetColumns(sesid, tableid, psetcolumn, v57);
      if ( v92 >= 0 )
      {
        v93 = UpdateContext::CommitUpdate((UpdateContext *)&v129, 1u);
        v94 = v93;
        if ( v93 >= 0 )
        {
          UpdateContext::~UpdateContext((UpdateContext *)&v129);
          BackoffContext::Unlock((BackoffContext *)&v107);
          memset_0(&v129, 0, 0x48u);
          v95 = *((_DWORD *)a2 + 2);
          v96 = (DatabaseVolumeSession *)*((_QWORD *)this + 255);
          *(_QWORD *)((char *)&v130 + 4) = *(_QWORD *)a2;
          LODWORD(v129) = 1;
          LODWORD(v130) = 2;
          HIDWORD(v130) = v95;
          v131 = v55;
          DatabaseVolumeSession::PushNotify(v96, (const struct UdmNotifyStructure *)&v129);
          goto LABEL_118;
        }
        Log_HREvent(
          (unsigned int)v93,
          1,
          "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\callhistory.cpp",
          2489);
        UpdateContext::~UpdateContext((UpdateContext *)&v129);
        BackoffContext::Unlock((BackoffContext *)&v107);
        HresultFromJetError = v94;
        goto LABEL_128;
      }
      v51 = MakeHresultFromJetError(v92);
      v97 = 2487;
      goto LABEL_115;
    }
    BackoffContext::NeedsBackoff((BackoffContext *)&v107);
    UpdateContext::~UpdateContext((UpdateContext *)&v129);
    BackoffContext::Unlock((BackoffContext *)&v107);
    v19 = v108;
    v17 = HIDWORD(v107);
    v16 = v107;
  }
  UpdateContext::~UpdateContext((UpdateContext *)&v129);
  BackoffContext::Unlock((BackoffContext *)&v107);
LABEL_118:
  CallHistoryDataSession::FlushUpdates(this);
  auto_JET_TABLEID::~auto_JET_TABLEID((auto_JET_TABLEID *)&sesid);
  BackoffContext::Unlock((BackoffContext *)&v107);
  return 0;
}

```

## disassembly

```asm
0x180074db4  mov     [rsp-8+arg_10], rbx
0x180074db9  push    rbp
0x180074dba  push    rsi
0x180074dbb  push    rdi
0x180074dbc  push    r12
0x180074dbe  push    r13
0x180074dc0  push    r14
0x180074dc2  push    r15
0x180074dc4  lea     rbp, [rsp-7C0h]
0x180074dcc  sub     rsp, 8C0h
0x180074dd3  mov     rax, cs:__security_cookie
0x180074dda  xor     rax, rsp
0x180074ddd  mov     [rbp+7F0h+var_40], rax
0x180074de4  mov     rax, [rbp+7F0h+arg_30]
0x180074deb  xor     r13d, r13d
0x180074dee  mov     rsi, rcx
0x180074df1  mov     [rbp+7F0h+var_790], rax
0x180074df5  mov     rcx, [rbp+7F0h+arg_38]
0x180074dfc  mov     r12, r9
0x180074dff  mov     rax, [rbp+7F0h+arg_48]
0x180074e06  mov     r15, rdx
0x180074e09  mov     [rbp+7F0h+var_788], rcx
0x180074e0d  xor     r9d, r9d; pvParameters
0x180074e10  mov     rcx, [rbp+7F0h+arg_50]
0x180074e17  mov     edi, r13d
0x180074e1a  mov     rbx, [rsi+7F8h]
0x180074e21  mov     r14d, r13d
0x180074e24  mov     edx, [rsi+808h]; dbid
0x180074e2a  add     rbx, 78h ; 'x'
0x180074e2e  mov     [rbp+7F0h+var_780], rax
0x180074e32  lea     rax, [rbp+7F0h+tableid]
0x180074e36  mov     [rsp+8F0h+ptableid], rax; ptableid
0x180074e3b  mov     [rbp+7F0h+var_778], rcx
0x180074e3f  mov     rcx, [rsi+800h]; sesid
0x180074e46  mov     [rbp+7F0h+var_798], r8
0x180074e4a  lea     r8, ?UdmTableName_CallHistory@@3QBDB; "CallHistory"
0x180074e51  mov     [rsp+8F0h+grbit], 8; grbit
0x180074e59  mov     [rsp+8F0h+cbParameters], r13d; cbParameters
0x180074e5e  mov     [rbp+7F0h+var_7B0], r13
0x180074e62  mov     [rbp+7F0h+var_7A8], r13
0x180074e66  mov     [rbp+7F0h+var_808], r13d
0x180074e6a  mov     [rbp+7F0h+var_820], r13d
0x180074e6e  mov     [rbp+7F0h+var_838], r13d
0x180074e72  mov     [rbp+7F0h+var_7A0], r13
0x180074e76  mov     [rsp+8F0h+var_878], r13b
0x180074e7b  mov     [rbp+7F0h+var_870], r13
0x180074e7f  mov     [rbp+7F0h+var_868], rbx
0x180074e83  mov     [rbp+7F0h+sesid], rcx
0x180074e87  mov     [rbp+7F0h+tableid], 0FFFFFFFFFFFFFFFFh
0x180074e8f  call    cs:__imp_JetOpenTableA
0x180074e95  test    eax, eax
0x180074e97  jns     short loc_180074EBD
0x180074e99  mov     ecx, eax; int
0x180074e9b  call    ?MakeHresultFromJetError@@YAJJ@Z; MakeHresultFromJetError(long)
0x180074ea0  mov     r9d, 8FBh
0x180074ea6  lea     r8, aOnecoreuapBase_43; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180074ead  xor     edx, edx
0x180074eaf  mov     ecx, eax
0x180074eb1  mov     ebx, eax
0x180074eb3  call    Log_HREvent
0x180074eb8  jmp     loc_180075F51
0x180074ebd  mov     rcx, [rsi+7F8h]; this
0x180074ec4  lea     r8, [rsp+8F0h+var_8B0]; int *
0x180074ec9  lea     rdx, off_180130C00; struct ColumnDefinition *
0x180074ed0  mov     [rsp+8F0h+var_8B0], r13d
0x180074ed5  call    ?FindColumnEx@DatabaseVolumeSession@@QEBAKPEBUColumnDefinition@@PEAH@Z; DatabaseVolumeSession::FindColumnEx(ColumnDefinition const *,int *)
0x180074eda  mov     [rbp+7F0h+var_85C], eax
0x180074edd  cmp     [rsp+8F0h+var_8B0], r13d
0x180074ee2  jnz     short loc_180074EF6
0x180074ee4  mov     r8d, 0CBh
0x180074eea  lea     rdx, aOnecoreuapBase_62; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180074ef1  call    Log_AssertionEvent_2
0x180074ef6  mov     rcx, [rsi+7F8h]; this
0x180074efd  lea     r8, [rsp+8F0h+var_8B0]; int *
0x180074f02  lea     rdx, off_180130C80; struct ColumnDefinition *
0x180074f09  mov     [rsp+8F0h+var_8B0], r13d
0x180074f0e  call    ?FindColumnEx@DatabaseVolumeSession@@QEBAKPEBUColumnDefinition@@PEAH@Z; DatabaseVolumeSession::FindColumnEx(ColumnDefinition const *,int *)
0x180074f13  mov     [rbp+7F0h+var_854], eax
0x180074f16  cmp     [rsp+8F0h+var_8B0], r13d
0x180074f1b  jnz     short loc_180074F2F
0x180074f1d  mov     r8d, 0CBh
0x180074f23  lea     rdx, aOnecoreuapBase_62; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180074f2a  call    Log_AssertionEvent_2
0x180074f2f  mov     rcx, [rsi+7F8h]; this
0x180074f36  lea     r8, [rsp+8F0h+var_8B0]; int *
0x180074f3b  lea     rdx, off_180130C60; struct ColumnDefinition *
0x180074f42  mov     [rsp+8F0h+var_8B0], r13d
0x180074f47  call    ?FindColumnEx@DatabaseVolumeSession@@QEBAKPEBUColumnDefinition@@PEAH@Z; DatabaseVolumeSession::FindColumnEx(ColumnDefinition const *,int *)
0x180074f4c  mov     [rbp+7F0h+var_850], eax
0x180074f4f  cmp     [rsp+8F0h+var_8B0], r13d
0x180074f54  jnz     short loc_180074F68
0x180074f56  mov     r8d, 0CBh
0x180074f5c  lea     rdx, aOnecoreuapBase_62; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180074f63  call    Log_AssertionEvent_2
0x180074f68  mov     rcx, [rsi+7F8h]; this
0x180074f6f  lea     r8, [rsp+8F0h+var_8B0]; int *
0x180074f74  lea     rdx, off_180130C20; struct ColumnDefinition *
0x180074f7b  mov     [rsp+8F0h+var_8B0], r13d
0x180074f80  call    ?FindColumnEx@DatabaseVolumeSession@@QEBAKPEBUColumnDefinition@@PEAH@Z; DatabaseVolumeSession::FindColumnEx(ColumnDefinition const *,int *)
0x180074f85  mov     [rbp+7F0h+var_84C], eax
0x180074f88  cmp     [rsp+8F0h+var_8B0], r13d
0x180074f8d  jnz     short loc_180074FA1
0x180074f8f  mov     r8d, 0CBh
0x180074f95  lea     rdx, aOnecoreuapBase_62; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180074f9c  call    Log_AssertionEvent_2
0x180074fa1  mov     rcx, [rsi+7F8h]; this
0x180074fa8  lea     r8, [rsp+8F0h+var_8B0]; int *
0x180074fad  lea     rdx, off_180130C40; struct ColumnDefinition *
0x180074fb4  mov     [rsp+8F0h+var_8B0], r13d
0x180074fb9  call    ?FindColumnEx@DatabaseVolumeSession@@QEBAKPEBUColumnDefinition@@PEAH@Z; DatabaseVolumeSession::FindColumnEx(ColumnDefinition const *,int *)
0x180074fbe  mov     [rbp+7F0h+var_844], eax
0x180074fc1  cmp     [rsp+8F0h+var_8B0], r13d
0x180074fc6  jnz     short loc_180074FDA
0x180074fc8  mov     r8d, 0CBh
0x180074fce  lea     rdx, aOnecoreuapBase_62; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180074fd5  call    Log_AssertionEvent_2
0x180074fda  mov     rcx, [rsi+7F8h]; this
0x180074fe1  lea     r8, [rsp+8F0h+var_8B0]; int *
0x180074fe6  lea     rdx, off_180130DA0; struct ColumnDefinition *
0x180074fed  mov     [rsp+8F0h+var_8B0], r13d
0x180074ff2  call    ?FindColumnEx@DatabaseVolumeSession@@QEBAKPEBUColumnDefinition@@PEAH@Z; DatabaseVolumeSession::FindColumnEx(ColumnDefinition const *,int *)
0x180074ff7  mov     [rbp+7F0h+var_840], eax
0x180074ffa  cmp     [rsp+8F0h+var_8B0], r13d
0x180074fff  jnz     short loc_180075013
0x180075001  mov     r8d, 0CBh
0x180075007  lea     rdx, aOnecoreuapBase_62; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18007500e  call    Log_AssertionEvent_2
0x180075013  mov     rcx, [rsi+7F8h]; this
0x18007501a  lea     r8, [rsp+8F0h+var_8B0]; int *
0x18007501f  lea     rdx, off_180130DC0; struct ColumnDefinition *
0x180075026  mov     [rsp+8F0h+var_8B0], r13d
0x18007502b  call    ?FindColumnEx@DatabaseVolumeSession@@QEBAKPEBUColumnDefinition@@PEAH@Z; DatabaseVolumeSession::FindColumnEx(ColumnDefinition const *,int *)
0x180075030  mov     [rbp+7F0h+var_83C], eax
0x180075033  cmp     [rsp+8F0h+var_8B0], r13d
0x180075038  jnz     short loc_18007504C
0x18007503a  mov     r8d, 0CBh
0x180075040  lea     rdx, aOnecoreuapBase_62; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180075047  call    Log_AssertionEvent_2
0x18007504c  mov     rcx, [rsi+7F8h]; this
0x180075053  lea     r8, [rsp+8F0h+var_8B0]; int *
0x180075058  lea     rdx, off_180130DE0; struct ColumnDefinition *
0x18007505f  mov     [rsp+8F0h+var_8B0], r13d
0x180075064  call    ?FindColumnEx@DatabaseVolumeSession@@QEBAKPEBUColumnDefinition@@PEAH@Z; DatabaseVolumeSession::FindColumnEx(ColumnDefinition const *,int *)
0x180075069  mov     [rbp+7F0h+var_834], eax
0x18007506c  cmp     [rsp+8F0h+var_8B0], r13d
0x180075071  jnz     short loc_180075085
0x180075073  mov     r8d, 0CBh
0x180075079  lea     rdx, aOnecoreuapBase_62; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180075080  call    Log_AssertionEvent_2
0x180075085  mov     rcx, [rsi+7F8h]; this
0x18007508c  lea     r8, [rsp+8F0h+var_8B0]; int *
0x180075091  lea     rdx, off_180130E40; struct ColumnDefinition *
0x180075098  mov     [rsp+8F0h+var_8B0], r13d
0x18007509d  call    ?FindColumnEx@DatabaseVolumeSession@@QEBAKPEBUColumnDefinition@@PEAH@Z; DatabaseVolumeSession::FindColumnEx(ColumnDefinition const *,int *)
0x1800750a2  mov     [rbp+7F0h+var_830], eax
0x1800750a5  cmp     [rsp+8F0h+var_8B0], r13d
0x1800750aa  jnz     short loc_1800750BE
0x1800750ac  mov     r8d, 0CBh
0x1800750b2  lea     rdx, aOnecoreuapBase_62; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800750b9  call    Log_AssertionEvent_2
0x1800750be  mov     rcx, [rsi+7F8h]; this
0x1800750c5  lea     r8, [rsp+8F0h+var_8B0]; int *
0x1800750ca  lea     rdx, off_180130E60; struct ColumnDefinition *
0x1800750d1  mov     [rsp+8F0h+var_8B0], r13d
0x1800750d6  call    ?FindColumnEx@DatabaseVolumeSession@@QEBAKPEBUColumnDefinition@@PEAH@Z; DatabaseVolumeSession::FindColumnEx(ColumnDefinition const *,int *)
0x1800750db  mov     [rbp+7F0h+var_82C], eax
0x1800750de  cmp     [rsp+8F0h+var_8B0], r13d
0x1800750e3  jnz     short loc_1800750F7
0x1800750e5  mov     r8d, 0CBh
0x1800750eb  lea     rdx, aOnecoreuapBase_62; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800750f2  call    Log_AssertionEvent_2
0x1800750f7  mov     rcx, [rsi+7F8h]; this
0x1800750fe  lea     r8, [rsp+8F0h+var_8B0]; int *
0x180075103  lea     rdx, off_180130E80; struct ColumnDefinition *
0x18007510a  mov     [rsp+8F0h+var_8B0], r13d
0x18007510f  call    ?FindColumnEx@DatabaseVolumeSession@@QEBAKPEBUColumnDefinition@@PEAH@Z; DatabaseVolumeSession::FindColumnEx(ColumnDefinition const *,int *)
0x180075114  mov     [rbp+7F0h+var_828], eax
0x180075117  cmp     [rsp+8F0h+var_8B0], r13d
0x18007511c  jnz     short loc_180075130
0x18007511e  mov     r8d, 0CBh
0x180075124  lea     rdx, aOnecoreuapBase_62; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18007512b  call    Log_AssertionEvent_2
0x180075130  mov     rcx, [rsi+7F8h]; this
0x180075137  lea     r8, [rsp+8F0h+var_8B0]; int *
0x18007513c  lea     rdx, off_180130F60; struct ColumnDefinition *
0x180075143  mov     [rsp+8F0h+var_8B0], r13d
0x180075148  call    ?FindColumnEx@DatabaseVolumeSession@@QEBAKPEBUColumnDefinition@@PEAH@Z; DatabaseVolumeSession::FindColumnEx(ColumnDefinition const *,int *)
0x18007514d  mov     [rbp+7F0h+var_824], eax
0x180075150  cmp     [rsp+8F0h+var_8B0], r13d
0x180075155  jnz     short loc_180075169
0x180075157  mov     r8d, 0CBh
0x18007515d  lea     rdx, aOnecoreuapBase_62; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180075164  call    Log_AssertionEvent_2
0x180075169  mov     r13, [rbp+7F0h+arg_28]
0x180075170  test    edi, edi
0x180075172  jz      short loc_180075186
0x180075174  mov     r8d, 8A0h
0x18007517a  lea     rdx, aOnecoreuapBase_62; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180075181  call    Log_AssertionEvent_2
0x180075186  mov     rcx, rbx; SRWLock
0x180075189  cmp     r14d, 2
0x18007518d  jnb     short loc_1800751B8
0x18007518f  call    cs:__imp_TryAcquireSRWLockShared
0x180075195  xor     r14d, r14d
0x180075198  test    al, al
0x18007519a  jnz     short loc_1800751AF
0x18007519c  lea     ecx, [r14+64h]; dwMilliseconds
0x1800751a0  call    cs:__imp_Sleep
0x1800751a6  mov     rcx, rbx; SRWLock
0x1800751a9  call    cs:__imp_AcquireSRWLockShared
0x1800751af  mov     dword ptr [rbp+7F0h+var_870], 1
0x1800751b6  jmp     short loc_1800751C8
0x1800751b8  call    cs:__imp_AcquireSRWLockExclusive
0x1800751be  xor     r14d, r14d
0x1800751c1  mov     dword ptr [rbp+7F0h+var_870], 2
0x1800751c8  mov     rcx, [rbp+7F0h+tableid]
0x1800751cc  mov     rax, [rsi+800h]
0x1800751d3  mov     [rbp+7F0h+var_7F8], rcx
0x1800751d7  mov     [rbp+7F0h+var_7D8], rcx
0x1800751db  lea     rcx, [rbp+7F0h+var_800]; this
0x1800751df  mov     [rbp+7F0h+var_800], rax
0x1800751e3  mov     [rbp+7F0h+var_7F0], rax
0x1800751e7  mov     [rbp+7F0h+var_7E8], 0
0x1800751ef  mov     [rbp+7F0h+var_7E0], rax
0x1800751f3  mov     [rbp+7F0h+var_7D0], r14d
0x1800751f7  call    ?Start@UpdateContext@@QEAAJK@Z; UpdateContext::Start(ulong)
0x1800751fc  mov     ebx, eax
0x1800751fe  test    eax, eax
0x180075200  js      loc_180075F26
0x180075206  mov     rdx, [rbp+7F0h+tableid]
0x18007520a  lea     rax, [rsp+8F0h+var_8B0]
0x18007520f  mov     rcx, [rsi+800h]
0x180075216  lea     r9, [r15+8]
0x18007521a  mov     [rsp+8F0h+grbit], r14d
0x18007521f  mov     qword ptr [rsp+8F0h+cbParameters], rax
0x180075224  mov     [rsp+8F0h+var_8B0], r14d
0x180075229  call    ??$SeekIndexToKey@K@@YAJ_K0PEBUIndexDefinition@@AEBKPEAHK@Z; SeekIndexToKey<ulong>(unsigned __int64,unsigned __int64,IndexDefinition const *,ulong const &,int *,ulong)
0x18007522e  mov     ebx, eax
0x180075230  test    eax, eax
0x180075232  js      loc_180075F17
0x180075238  cmp     [rsp+8F0h+var_8B0], r14d
0x18007523d  jz      loc_180075EE4
0x180075243  mov     eax, [rbp+7F0h+var_85C]
0x180075246  xorps   xmm2, xmm2
0x180075249  mov     [rbp+7F0h+pretrievecolumn.columnid], eax
0x18007524f  xorps   xmm1, xmm1
0x180075252  movups  [rsp+8F0h+var_888], xmm2
0x180075257  mov     r8d, 4
0x18007525d  movups  [rsp+8F0h+var_8A8], xmm2
0x180075262  mov     eax, dword ptr [rsp+8F0h+var_8A8+4]
0x180075266  mov     dword ptr [rbp+7F0h+pretrievecolumn+4], eax
0x18007526c  lea     rax, [rbp+7F0h+var_808]
0x180075270  mov     [rbp+7F0h+pretrievecolumn.pvData], rax
0x180075277  lea     ecx, [r8-3]
0x18007527b  mov     eax, dword ptr [rsp+8F0h+var_888+4]
0x18007527f  lea     edx, [rcx+7]
0x180075282  mov     [rbp+7F0h+pretrievecolumn.columnidNextTagged], eax
0x180075288  mov     eax, dword ptr [rsp+8F0h+var_888+0Ch]
0x18007528c  mov     dword ptr [rbp+7F0h+pretrievecolumn+2Ch], eax
0x180075292  mov     eax, [rbp+7F0h+var_854]
0x180075295  mov     [rbp+7F0h+var_740], eax
0x18007529b  movups  [rsp+8F0h+var_898], xmm2
0x1800752a0  mov     [rbp+7F0h+pretrievecolumn.cbData], r8d
0x1800752a7  movsd   xmm0, qword ptr [rsp+8F0h+var_898+4]
0x1800752ad  psrldq  xmm2, 8
0x1800752b2  movd    [rbp+7F0h+pretrievecolumn.err], xmm2
0x1800752ba  xorps   xmm2, xmm2
0x1800752bd  movups  [rsp+8F0h+var_888], xmm2
0x1800752c2  mov     [rbp+7F0h+pretrievecolumn.itagSequence], ecx
0x1800752c8  movups  [rsp+8F0h+var_8A8], xmm2
0x1800752cd  mov     eax, dword ptr [rsp+8F0h+var_8A8+4]
0x1800752d1  mov     [rbp+7F0h+var_73C], eax
0x1800752d7  lea     rax, [rbp+7F0h+var_7A8]
0x1800752db  mov     [rbp+7F0h+var_738], rax
0x1800752e2  mov     eax, dword ptr [rsp+8F0h+var_888+4]
0x1800752e6  mov     [rbp+7F0h+var_71C], eax
0x1800752ec  mov     eax, dword ptr [rsp+8F0h+var_888+0Ch]
0x1800752f0  mov     [rbp+7F0h+var_714], eax
0x1800752f6  mov     eax, [rbp+7F0h+var_850]
0x1800752f9  mov     [rbp+7F0h+var_710], eax
0x1800752ff  movups  [rsp+8F0h+var_898], xmm2
0x180075304  mov     [rbp+7F0h+var_730], edx
0x18007530a  psrldq  xmm1, 0Ch
0x18007530f  psrldq  xmm2, 8
0x180075314  movd    [rbp+7F0h+pretrievecolumn.ibLongValue], xmm1
0x18007531c  xorps   xmm1, xmm1
0x18007531f  movd    [rbp+7F0h+var_718], xmm2
0x180075327  xorps   xmm2, xmm2
0x18007532a  movups  [rsp+8F0h+var_888], xmm2
0x18007532f  mov     [rbp+7F0h+var_720], ecx
0x180075335  movups  [rsp+8F0h+var_8A8], xmm2
0x18007533a  mov     eax, dword ptr [rsp+8F0h+var_8A8+4]
0x18007533e  mov     [rbp+7F0h+var_70C], eax
0x180075344  lea     rax, [rbp+7F0h+var_7B0]
0x180075348  mov     [rbp+7F0h+var_708], rax
0x18007534f  mov     eax, dword ptr [rsp+8F0h+var_888+4]
0x180075353  mov     [rbp+7F0h+var_6EC], eax
0x180075359  mov     eax, dword ptr [rsp+8F0h+var_888+0Ch]
0x18007535d  psrldq  xmm1, 0Ch
0x180075362  mov     [rbp+7F0h+var_6E4], eax
  ... truncated ...
```
