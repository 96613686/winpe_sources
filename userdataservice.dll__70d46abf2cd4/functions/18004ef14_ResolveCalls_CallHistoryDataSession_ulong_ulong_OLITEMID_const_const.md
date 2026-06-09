# ResolveCalls(CallHistoryDataSession *,ulong,ulong,OLITEMID const * const)

- ea: `0x18004ef14`
- end: `0x18004fba4`
- name: `?ResolveCalls@@YAJPEAVCallHistoryDataSession@@KKQEBUOLITEMID@@@Z`
- size: `3216`
- prototype: `__int64 __fastcall(struct CallHistoryDataSession *this, unsigned int, unsigned int, const struct OLITEMID *const)`
- caller_count: `2`
- callee_count: `24`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x18004edf4`
- `0x1800e1f34`

## callees

- `0x180008ee8`
- `0x180008f0c`
- `0x18001e940`
- `0x18003bf04`
- `0x18004ef14`
- `0x180066860`
- `0x1800672f8`
- `0x180068698`
- `0x18006b13c`
- `0x180075f98`
- `0x180076604`
- `0x180076664`
- `0x1800a0174`
- `0x1800a1270`
- `0x1800a1568`
- `0x1800c0f04`
- `0x1800db71c`
- `0x1800dbb0c`
- `0x1800dbc30`
- `0x1800e1b5c`
- `0x1800e2758`
- `0x1800e98c4`
- `0x18012c76a`
- `0x18012c7b0`

## import_xrefs

- `ESENT!JetOpenTableA` at `0x18004f1c4`
- `ESENT!JetOpenTableA` at `0x18004f1c4`
- `ESENT!JetSetCurrentIndexA` at `0x18004f1e3`
- `ESENT!JetSetCurrentIndexA` at `0x18004f1e3`
- `ESENT!JetPrepareUpdate` at `0x18004f8e6`
- `ESENT!JetPrepareUpdate` at `0x18004f8e6`
- `ESENT!JetRetrieveColumns` at `0x18004f615`
- `ESENT!JetRetrieveColumns` at `0x18004f615`
- `ESENT!JetSetColumns` at `0x18004f98b`
- `ESENT!JetSetColumns` at `0x18004f98b`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18004f267`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18004f267`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18004f27e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18004f27e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18004f272`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18004f272`
- `api-ms-win-core-synch-l1-1-0!TryAcquireSRWLockShared` at `0x18004f258`
- `api-ms-win-core-synch-l1-1-0!TryAcquireSRWLockShared` at `0x18004f258`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18004ef89`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18004ef89`

## string_xrefs

- `0x18004efcf`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\datasession.cpp`
- `0x18004f146`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\datasession.cpp`
- `0x18004f17c`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\datasession.cpp`
- `0x18004f240`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\datasession.cpp`
- `0x18004ef9b`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\callhistory.cpp`
- `0x18004fa1c`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\callhistory.cpp`
- `0x18004fa41`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\callhistory.cpp`
- `0x18004fb0d`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\callhistory.cpp`
- `0x18004fb49`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\callhistory.cpp`
- `0x18004f8cc`: `onecoreuap\base\AppModel\UserDataAccess\PublishedInternal\Inc\jetinterop.h`

## pseudocode

```c
__int64 __fastcall ResolveCalls(
        struct CallHistoryDataSession *this,
        int a2,
        unsigned int a3,
        const struct OLITEMID *a4)
{
  __int64 v4; // rbx
  HRESULT Instance; // eax
  unsigned int v8; // edi
  DatabaseVolumeSession *v9; // rcx
  __int64 v10; // rcx
  DatabaseVolumeSession *v11; // rcx
  __int64 v12; // rcx
  DatabaseVolumeSession *v13; // rcx
  __int64 v14; // rcx
  DatabaseVolumeSession *v15; // rcx
  __int64 v16; // rcx
  DatabaseVolumeSession *v17; // rcx
  __int64 v18; // rcx
  DatabaseVolumeSession *v19; // rcx
  __int64 v20; // rcx
  DatabaseVolumeSession *v21; // rcx
  __int64 v22; // rcx
  JET_COLUMNID v23; // r13d
  DatabaseVolumeSession *v24; // rcx
  __int64 v25; // rcx
  unsigned int v26; // r12d
  DatabaseVolumeSession *v27; // rcx
  __int64 v28; // rcx
  JET_DBID v29; // edx
  JET_ERR v30; // eax
  JET_ERR v31; // eax
  int HresultFromJetError; // eax
  __int64 v33; // r9
  __int64 v34; // rdx
  __int64 v35; // rcx
  JET_ERR v36; // eax
  int inited; // eax
  __int64 v38; // r9
  __int64 v39; // rdx
  _OWORD *v40; // rcx
  __int64 *v41; // rax
  __int128 v42; // xmm1
  __int128 v43; // xmm0
  __int128 v44; // xmm1
  __int128 v45; // xmm0
  __int128 v46; // xmm1
  __int128 v47; // xmm0
  __int128 v48; // xmm1
  __int128 v49; // xmm0
  __int128 v50; // xmm1
  int v51; // eax
  __int64 v52; // r11
  int v53; // eax
  __int64 v54; // rcx
  JET_ERR v55; // eax
  __int64 v56; // r9
  JET_ERR v57; // eax
  DatabaseVolumeSession *v58; // rcx
  __int64 v59; // rdx
  __int64 v60; // rdx
  unsigned int v62; // ebx
  int v63; // [rsp+40h] [rbp-C0h] BYREF
  JET_SESID sesid; // [rsp+48h] [rbp-B8h] BYREF
  JET_TABLEID tableid; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v66; // [rsp+58h] [rbp-A8h] BYREF
  PSRWLOCK SRWLock; // [rsp+60h] [rbp-A0h]
  __int128 v68; // [rsp+68h] [rbp-98h]
  __int128 v69; // [rsp+78h] [rbp-88h]
  __int128 v70; // [rsp+88h] [rbp-78h]
  int v71; // [rsp+98h] [rbp-68h] BYREF
  int v72; // [rsp+9Ch] [rbp-64h] BYREF
  struct IPOutlookApp3 *ppv; // [rsp+A0h] [rbp-60h] BYREF
  JET_COLUMNID v74; // [rsp+A8h] [rbp-58h]
  unsigned int Column; // [rsp+ACh] [rbp-54h]
  unsigned int v76; // [rsp+B0h] [rbp-50h]
  unsigned int v77; // [rsp+B4h] [rbp-4Ch]
  unsigned int v78; // [rsp+B8h] [rbp-48h]
  int v79; // [rsp+BCh] [rbp-44h]
  unsigned int v80; // [rsp+C0h] [rbp-40h]
  unsigned int v81; // [rsp+C4h] [rbp-3Ch]
  _QWORD v82[4]; // [rsp+C8h] [rbp-38h] BYREF
  JET_SESID v83; // [rsp+E8h] [rbp-18h]
  JET_TABLEID v84; // [rsp+F0h] [rbp-10h]
  int v85; // [rsp+F8h] [rbp-8h]
  __int64 v86; // [rsp+100h] [rbp+0h] BYREF
  __int64 v87; // [rsp+108h] [rbp+8h] BYREF
  int v88; // [rsp+110h] [rbp+10h]
  int v89; // [rsp+120h] [rbp+20h] BYREF
  __int64 v90; // [rsp+128h] [rbp+28h]
  int v91; // [rsp+130h] [rbp+30h]
  int v92; // [rsp+134h] [rbp+34h]
  __int64 v93; // [rsp+138h] [rbp+38h]
  __int64 v94; // [rsp+170h] [rbp+70h] BYREF
  int v95; // [rsp+178h] [rbp+78h]
  _BYTE v96[4]; // [rsp+17Ch] [rbp+7Ch] BYREF
  char v97; // [rsp+180h] [rbp+80h] BYREF
  char v98; // [rsp+24Ah] [rbp+14Ah] BYREF
  _BYTE v99[12]; // [rsp+320h] [rbp+220h] BYREF
  char v100; // [rsp+32Ch] [rbp+22Ch] BYREF
  unsigned __int16 v101[101]; // [rsp+330h] [rbp+230h] BYREF
  unsigned __int16 v102[107]; // [rsp+3FAh] [rbp+2FAh] BYREF
  JET_RETRIEVECOLUMN pretrievecolumn; // [rsp+4D0h] [rbp+3D0h] BYREF
  JET_COLUMNID v104; // [rsp+500h] [rbp+400h]
  int v105; // [rsp+504h] [rbp+404h]
  __int64 *v106; // [rsp+508h] [rbp+408h]
  int v107; // [rsp+510h] [rbp+410h]
  __int64 v108; // [rsp+514h] [rbp+414h]
  int v109; // [rsp+51Ch] [rbp+41Ch]
  int v110; // [rsp+520h] [rbp+420h]
  int v111; // [rsp+524h] [rbp+424h]
  int v112; // [rsp+528h] [rbp+428h]
  int v113; // [rsp+52Ch] [rbp+42Ch]
  unsigned int v114; // [rsp+530h] [rbp+430h]
  int v115; // [rsp+534h] [rbp+434h]
  _BYTE *v116; // [rsp+538h] [rbp+438h]
  int v117; // [rsp+540h] [rbp+440h]
  __int64 v118; // [rsp+544h] [rbp+444h]
  int v119; // [rsp+54Ch] [rbp+44Ch]
  int v120; // [rsp+550h] [rbp+450h]
  __int64 v121; // [rsp+554h] [rbp+454h]
  int v122; // [rsp+55Ch] [rbp+45Ch]
  unsigned int v123; // [rsp+560h] [rbp+460h]
  int v124; // [rsp+564h] [rbp+464h]
  __int64 *v125; // [rsp+568h] [rbp+468h]
  int v126; // [rsp+570h] [rbp+470h]
  __int64 v127; // [rsp+574h] [rbp+474h]
  int v128; // [rsp+57Ch] [rbp+47Ch]
  int v129; // [rsp+580h] [rbp+480h]
  __int64 v130; // [rsp+584h] [rbp+484h]
  int v131; // [rsp+58Ch] [rbp+48Ch]
  unsigned int v132; // [rsp+590h] [rbp+490h]
  int v133; // [rsp+594h] [rbp+494h]
  char *v134; // [rsp+598h] [rbp+498h]
  int v135; // [rsp+5A0h] [rbp+4A0h]
  __int64 v136; // [rsp+5A4h] [rbp+4A4h]
  int v137; // [rsp+5ACh] [rbp+4ACh]
  int v138; // [rsp+5B0h] [rbp+4B0h]
  __int64 v139; // [rsp+5B4h] [rbp+4B4h]
  int v140; // [rsp+5BCh] [rbp+4BCh]
  unsigned int v141; // [rsp+5C0h] [rbp+4C0h]
  int v142; // [rsp+5C4h] [rbp+4C4h]
  char *v143; // [rsp+5C8h] [rbp+4C8h]
  int v144; // [rsp+5D0h] [rbp+4D0h]
  __int64 v145; // [rsp+5D4h] [rbp+4D4h]
  int v146; // [rsp+5DCh] [rbp+4DCh]
  int v147; // [rsp+5E0h] [rbp+4E0h]
  __int64 v148; // [rsp+5E4h] [rbp+4E4h]
  int v149; // [rsp+5ECh] [rbp+4ECh]
  unsigned int v150; // [rsp+5F0h] [rbp+4F0h]
  int v151; // [rsp+5F4h] [rbp+4F4h]
  int *v152; // [rsp+5F8h] [rbp+4F8h]
  int v153; // [rsp+600h] [rbp+500h]
  __int64 v154; // [rsp+604h] [rbp+504h]
  int v155; // [rsp+60Ch] [rbp+50Ch]
  int v156; // [rsp+610h] [rbp+510h]
  int v157; // [rsp+614h] [rbp+514h]
  int v158; // [rsp+618h] [rbp+518h]
  int v159; // [rsp+61Ch] [rbp+51Ch]
  JET_SETCOLUMN psetcolumn; // [rsp+620h] [rbp+520h] BYREF
  unsigned int v161; // [rsp+648h] [rbp+548h] BYREF
  char *v162; // [rsp+650h] [rbp+550h]
  int v163; // [rsp+658h] [rbp+558h]
  int v164; // [rsp+664h] [rbp+564h]
  struct JET_SETCOLUMN v165; // [rsp+670h] [rbp+570h] BYREF
  struct JET_SETCOLUMN v166; // [rsp+698h] [rbp+598h] BYREF

  v4 = a3;
  SRWLock = (PSRWLOCK)(*((_QWORD *)this + 255) + 120LL);
  v79 = a2;
  v66 = 0;
  ppv = 0;
  Instance = CoCreateInstance(&CLSID_Application, 0, 0x17u, &GUID_a65ccaeb_6558_4656_ad3d_eccc00d00f0d, (LPVOID *)&ppv);
  v8 = Instance;
  if ( Instance < 0 )
  {
    Log_HREvent(
      (unsigned int)Instance,
      1,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\callhistory.cpp",
      2598);
LABEL_95:
    ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(&ppv);
    BackoffContext::Unlock((BackoffContext *)&v66);
    return v8;
  }
  v9 = (DatabaseVolumeSession *)*((_QWORD *)this + 255);
  v63 = 0;
  Column = DatabaseVolumeSession::FindColumnEx(v9, (const struct ColumnDefinition *)&off_180130C60, &v63);
  if ( !v63 )
    Log_AssertionEvent_2(
      v10,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\datasession.cpp",
      203);
  v11 = (DatabaseVolumeSession *)*((_QWORD *)this + 255);
  v63 = 0;
  v76 = DatabaseVolumeSession::FindColumnEx(v11, (const struct ColumnDefinition *)&off_180130CA0, &v63);
  if ( !v63 )
    Log_AssertionEvent_2(
      v12,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\datasession.cpp",
      203);
  v13 = (DatabaseVolumeSession *)*((_QWORD *)this + 255);
  v63 = 0;
  v77 = DatabaseVolumeSession::FindColumnEx(v13, (const struct ColumnDefinition *)&off_180130CC0, &v63);
  if ( !v63 )
    Log_AssertionEvent_2(
      v14,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\datasession.cpp",
      203);
  v15 = (DatabaseVolumeSession *)*((_QWORD *)this + 255);
  v63 = 0;
  v74 = DatabaseVolumeSession::FindColumnEx(v15, (const struct ColumnDefinition *)&UdmTableCols_CallHistory, &v63);
  if ( !v63 )
    Log_AssertionEvent_2(
      v16,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\datasession.cpp",
      203);
  v17 = (DatabaseVolumeSession *)*((_QWORD *)this + 255);
  v63 = 0;
  v80 = DatabaseVolumeSession::FindColumnEx(v17, (const struct ColumnDefinition *)&off_180130CE0, &v63);
  if ( !v63 )
    Log_AssertionEvent_2(
      v18,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\datasession.cpp",
      203);
  v19 = (DatabaseVolumeSession *)*((_QWORD *)this + 255);
  v63 = 0;
  v81 = DatabaseVolumeSession::FindColumnEx(v19, (const struct ColumnDefinition *)&off_180130D00, &v63);
  if ( !v63 )
    Log_AssertionEvent_2(
      v20,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\datasession.cpp",
      203);
  v21 = (DatabaseVolumeSession *)*((_QWORD *)this + 255);
  v63 = 0;
  v23 = DatabaseVolumeSession::FindColumnEx(v21, (const struct ColumnDefinition *)&off_180130D40, &v63);
  if ( !v63 )
    Log_AssertionEvent_2(
      v22,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\datasession.cpp",
      203);
  v24 = (DatabaseVolumeSession *)*((_QWORD *)this + 255);
  v63 = 0;
  v26 = DatabaseVolumeSession::FindColumnEx(v24, (const struct ColumnDefinition *)&off_180130D20, &v63);
  if ( !v63 )
    Log_AssertionEvent_2(
      v25,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\datasession.cpp",
      203);
  v27 = (DatabaseVolumeSession *)*((_QWORD *)this + 255);
  v63 = 0;
  v78 = DatabaseVolumeSession::FindColumnEx(v27, (const struct ColumnDefinition *)&off_180130EE0, &v63);
  if ( !v63 )
    Log_AssertionEvent_2(
      v28,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\datasession.cpp",
      203);
  v29 = *((_DWORD *)this + 514);
  sesid = *((_QWORD *)this + 256);
  tableid = -1;
  v30 = JetOpenTableA(sesid, v29, "CallHistory", 0, 0, 8u, &tableid);
  if ( v30 >= 0 )
  {
    v31 = JetSetCurrentIndexA(sesid, tableid, "ById");
    if ( v31 < 0 )
    {
      HresultFromJetError = MakeHresultFromJetError(v31);
      v8 = HresultFromJetError;
      v33 = 2625;
      v34 = 0;
LABEL_93:
      Log_HREvent(
        (unsigned int)HresultFromJetError,
        v34,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\callhistory.cpp",
        v33);
LABEL_94:
      auto_JET_TABLEID::~auto_JET_TABLEID((auto_JET_TABLEID *)&sesid);
      goto LABEL_95;
    }
    v63 = 0;
    HresultFromJetError = MoveFirst((const struct auto_JET_TABLEID *)&sesid, &v63);
    v8 = HresultFromJetError;
    if ( HresultFromJetError < 0 )
    {
      v33 = 2630;
      v34 = 1;
      goto LABEL_93;
    }
    v35 = 3 * v4;
    while ( 1 )
    {
      if ( !v63 )
      {
        CallHistoryDataSession::FlushUpdates(this);
        auto_JET_TABLEID::~auto_JET_TABLEID((auto_JET_TABLEID *)&sesid);
        ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(&ppv);
        BackoffContext::Unlock((BackoffContext *)&v66);
        return 0;
      }
      if ( (_DWORD)v66 )
        Log_AssertionEvent_2(
          v35,
          "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\datasession.cpp",
          2208);
      if ( HIDWORD(v66) >= 2 )
      {
        AcquireSRWLockExclusive(SRWLock);
        LODWORD(v66) = 2;
      }
      else
      {
        if ( !TryAcquireSRWLockShared(SRWLock) )
        {
          Sleep(0x64u);
          AcquireSRWLockShared(SRWLock);
        }
        LODWORD(v66) = 1;
      }
      v94 = g_ZeroOlItemId;
      v95 = 0;
      memset_0(v96, 0, 0x198u);
      pretrievecolumn.columnid = v74;
      *(&pretrievecolumn.columnid + 1) = 0;
      pretrievecolumn.pvData = &v72;
      *(&pretrievecolumn.err + 1) = _mm_cvtsi128_si32(_mm_srli_si128((__m128i)0LL, 12));
      v105 = 0;
      v106 = &v94;
      *(_QWORD *)&pretrievecolumn.cbActual = 0;
      pretrievecolumn.ibLongValue = *(&pretrievecolumn.err + 1);
      v111 = 0;
      v112 = _mm_cvtsi128_si32(_mm_srli_si128((__m128i)0LL, 8));
      v113 = 0;
      v115 = 0;
      *(_QWORD *)&pretrievecolumn.columnidNextTagged = 0;
      v116 = v96;
      v108 = 0;
      v109 = *(&pretrievecolumn.err + 1);
      v118 = 0;
      v122 = *(&pretrievecolumn.err + 1);
      v123 = Column;
      v72 = 0;
      v86 = 0;
      v71 = 0;
      pretrievecolumn.cbData = 4;
      pretrievecolumn.itagSequence = 1;
      v104 = v23;
      v107 = 12;
      v110 = 1;
      v114 = v26;
      v117 = 4;
      v119 = *(&pretrievecolumn.err + 1);
      v120 = 1;
      v121 = 0;
      v124 = 0;
      v125 = &v86;
      v132 = v76;
      v131 = *(&pretrievecolumn.err + 1);
      v133 = 0;
      v134 = &v97;
      v141 = v77;
      v127 = 0;
      v126 = 8;
      v128 = *(&pretrievecolumn.err + 1);
      v130 = 0;
      v140 = *(&pretrievecolumn.err + 1);
      v142 = 0;
      v143 = &v98;
      v136 = 0;
      v150 = v78;
      v137 = *(&pretrievecolumn.err + 1);
      v139 = 0;
      v149 = *(&pretrievecolumn.err + 1);
      v68 = 0;
      v151 = 0;
      v145 = 0;
      v70 = 0;
      v152 = &v71;
      v146 = *(&pretrievecolumn.err + 1);
      v69 = 0;
      v157 = 0;
      v148 = 0;
      v159 = 0;
      v129 = 1;
      v135 = 202;
      v138 = 1;
      v144 = 202;
      v147 = 1;
      v153 = 4;
      v154 = 0;
      v155 = *(&pretrievecolumn.err + 1);
      v156 = 1;
      v158 = v112;
      v36 = JetRetrieveColumns(sesid, tableid, &pretrievecolumn, 7u);
      if ( v36 == -1017 )
      {
        inited = Move(sesid, tableid, 1, &v63);
        v8 = inited;
        if ( inited < 0 )
        {
          v38 = 2658;
          goto LABEL_74;
        }
      }
      else
      {
        if ( v36 < 0 )
        {
          inited = MakeHresultFromJetError(v36);
          v8 = inited;
          v38 = 2663;
          v59 = 0;
          goto LABEL_75;
        }
        if ( v158 || v71 != 1 )
        {
          if ( v112
            || (v79 & 1) != 0
            || (const struct OLITEMID *)utl::find<OLITEMID const * const,OLITEMID>(a4, (char *)a4 + 12 * v4, &v94) != (const struct OLITEMID *)((char *)a4 + 12 * v4)
            || (v87 = g_ZeroOlItemId, v88 = 0, (unsigned __int8)operator==(&v94, &v87)) )
          {
            v39 = 3;
            v40 = v99;
            v41 = &v94;
            do
            {
              v42 = *((_OWORD *)v41 + 1);
              *v40 = *(_OWORD *)v41;
              v43 = *((_OWORD *)v41 + 2);
              v40[1] = v42;
              v44 = *((_OWORD *)v41 + 3);
              v40[2] = v43;
              v45 = *((_OWORD *)v41 + 4);
              v40[3] = v44;
              v46 = *((_OWORD *)v41 + 5);
              v40[4] = v45;
              v47 = *((_OWORD *)v41 + 6);
              v40[5] = v46;
              v48 = *((_OWORD *)v41 + 7);
              v41 += 16;
              v40[6] = v47;
              v40[7] = v48;
              v40 += 8;
              --v39;
            }
            while ( v39 );
            v49 = *(_OWORD *)v41;
            v50 = *((_OWORD *)v41 + 1);
            v51 = *((_DWORD *)v41 + 8);
            *v40 = v49;
            v40[1] = v50;
            *((_DWORD *)v40 + 8) = v51;
            inited = RebindCallInfo(ppv, (const struct CallResolutionState *)&v94, (struct CallResolutionState *)v99);
            v8 = inited;
            if ( inited < 0 )
            {
              v38 = 2695;
LABEL_74:
              v59 = 1;
LABEL_75:
              Log_HREvent(
                (unsigned int)inited,
                v59,
                "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\callhistory.cpp",
                v38);
              goto LABEL_76;
            }
            if ( !(unsigned int)CallResolutionState::operator==(v99, &v94) )
            {
              *(&psetcolumn.columnid + 1) = v52;
              *(_QWORD *)&psetcolumn.grbit = v52;
              *(_QWORD *)&psetcolumn.err = v52;
              memset_0(&v161, 0, 0x78u);
              psetcolumn.pvData = v99;
              psetcolumn.columnid = v23;
              v162 = &v100;
              psetcolumn.cbData = 12;
              psetcolumn.itagSequence = 1;
              v161 = v26;
              v163 = 4;
              v164 = 1;
              inited = InitSetColumn(&v165, v80, v102);
              v8 = inited;
              if ( inited < 0 )
              {
                v38 = 2718;
                goto LABEL_74;
              }
              inited = InitSetColumn(&v166, v81, v101);
              v8 = inited;
              if ( inited < 0 )
              {
                v38 = 2719;
                goto LABEL_74;
              }
              v82[0] = sesid;
              v82[2] = sesid;
              v83 = sesid;
              v82[1] = tableid;
              v82[3] = 0;
              v84 = tableid;
              v85 = 0;
              v53 = UpdateContext::Start((UpdateContext *)v82, 0);
              v8 = v53;
              if ( v53 < 0 )
              {
                v56 = 2728;
LABEL_78:
                v60 = 1;
LABEL_79:
                Log_HREvent(
                  (unsigned int)v53,
                  v60,
                  "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\callhistory.cpp",
                  v56);
                UpdateContext::~UpdateContext((UpdateContext *)v82);
LABEL_76:
                BackoffContext::Unlock((BackoffContext *)&v66);
                goto LABEL_94;
              }
              if ( v85 )
                Log_AssertionEvent_2(
                  v54,
                  "onecoreuap\\base\\AppModel\\UserDataAccess\\PublishedInternal\\Inc\\jetinterop.h",
                  522);
              v55 = JetPrepareUpdate(v83, v84, 2u);
              switch ( v55 )
              {
                case 0:
                  v85 = 1;
                  goto LABEL_69;
                case -1102:
                  v53 = UpdateContext::Commit((UpdateContext *)v82, 1u);
                  v8 = v53;
                  if ( v53 < 0 )
                  {
                    v56 = 2734;
                    goto LABEL_78;
                  }
                  BackoffContext::NeedsBackoff((BackoffContext *)&v66);
                  v63 = 1;
                  break;
                case -1017:
                  v53 = UpdateContext::Commit((UpdateContext *)v82, 1u);
                  v8 = v53;
                  if ( v53 < 0 )
                  {
                    v56 = 2741;
                    goto LABEL_78;
                  }
                  v53 = Move(sesid, tableid, 1, &v63);
                  v8 = v53;
                  if ( v53 < 0 )
                  {
                    v56 = 2742;
                    goto LABEL_78;
                  }
                  break;
                default:
                  if ( v55 < 0 )
                  {
                    v53 = MakeHresultFromJetError(v55);
                    v56 = 2747;
                    goto LABEL_84;
                  }
LABEL_69:
                  v57 = JetSetColumns(sesid, tableid, &psetcolumn, 4u);
                  if ( v57 < 0 )
                  {
                    v53 = MakeHresultFromJetError(v57);
                    v56 = 2751;
LABEL_84:
                    v8 = v53;
                    v60 = 0;
                    goto LABEL_79;
                  }
                  v53 = UpdateContext::CommitUpdate((UpdateContext *)v82, 1u);
                  v8 = v53;
                  if ( v53 < 0 )
                  {
                    v56 = 2752;
                    goto LABEL_78;
                  }
                  memset_0(&v89, 0, 0x48u);
                  v58 = (DatabaseVolumeSession *)*((_QWORD *)this + 255);
                  v92 = v72;
                  v93 = v86;
                  v89 = 1;
                  v90 = 2;
                  v91 = 1;
                  DatabaseVolumeSession::PushNotify(v58, (const struct UdmNotifyStructure *)&v89);
                  v53 = Move(sesid, tableid, 1, &v63);
                  v8 = v53;
                  if ( v53 < 0 )
                  {
                    v56 = 2763;
                    goto LABEL_78;
                  }
                  break;
              }
              UpdateContext::~UpdateContext((UpdateContext *)v82);
              goto LABEL_36;
            }
            inited = Move(sesid, tableid, 1, &v63);
            v8 = inited;
            if ( inited < 0 )
            {
              v38 = 2700;
              goto LABEL_74;
            }
          }
          else
          {
            inited = Move(sesid, tableid, 1, &v63);
            v8 = inited;
            if ( inited < 0 )
            {
              v38 = 2689;
              goto LABEL_74;
            }
          }
        }
        else
        {
          inited = Move(sesid, tableid, 1, &v63);
          v8 = inited;
          if ( inited < 0 )
          {
            v38 = 2669;
            goto LABEL_74;
          }
        }
      }
LABEL_36:
      BackoffContext::Unlock((BackoffContext *)&v66);
    }
  }
  v62 = MakeHresultFromJetError(v30);
  Log_HREvent(
    v62,
    0,
    "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\callhistory.cpp",
    2623);
  auto_JET_TABLEID::~auto_JET_TABLEID((auto_JET_TABLEID *)&sesid);
  ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(&ppv);
  BackoffContext::Unlock((BackoffContext *)&v66);
  return v62;
}

```

## disassembly

```asm
0x18004ef14  mov     [rsp-8+arg_8], rbx
0x18004ef19  push    rbp
0x18004ef1a  push    rsi
0x18004ef1b  push    rdi
0x18004ef1c  push    r12
0x18004ef1e  push    r13
0x18004ef20  push    r14
0x18004ef22  push    r15
0x18004ef24  lea     rbp, [rsp-5D0h]
0x18004ef2c  sub     rsp, 6D0h
0x18004ef33  mov     rax, cs:__security_cookie
0x18004ef3a  xor     rax, rsp
0x18004ef3d  mov     [rbp+600h+var_40], rax
0x18004ef44  mov     rax, [rcx+7F8h]
0x18004ef4b  xor     r14d, r14d
0x18004ef4e  add     rax, 78h ; 'x'
0x18004ef52  mov     ebx, r8d
0x18004ef55  mov     [rsp+700h+SRWLock], rax
0x18004ef5a  mov     r15, r9
0x18004ef5d  lea     rax, [rbp+600h+var_660]
0x18004ef61  mov     [rbp+600h+var_644], edx
0x18004ef64  mov     rsi, rcx
0x18004ef67  mov     [rsp+700h+ppv], rax; ppv
0x18004ef6c  lea     r9, _GUID_a65ccaeb_6558_4656_ad3d_eccc00d00f0d; riid
0x18004ef73  mov     [rsp+700h+var_6A8], r14
0x18004ef78  xor     edx, edx; pUnkOuter
0x18004ef7a  mov     [rbp+600h+var_660], r14
0x18004ef7e  lea     r8d, [r14+17h]; dwClsContext
0x18004ef82  lea     rcx, CLSID_Application; rclsid
0x18004ef89  call    cs:__imp_CoCreateInstance
0x18004ef8f  mov     edi, eax
0x18004ef91  test    eax, eax
0x18004ef93  jns     short loc_18004EFB2
0x18004ef95  mov     r9d, 0A26h
0x18004ef9b  lea     r8, aOnecoreuapBase_43; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18004efa2  lea     edx, [r14+1]
0x18004efa6  mov     ecx, eax
0x18004efa8  call    Log_HREvent
0x18004efad  jmp     loc_18004FB25
0x18004efb2  mov     rcx, [rsi+7F8h]; this
0x18004efb9  lea     r8, [rsp+700h+var_6C0]; int *
0x18004efbe  lea     rdx, off_180130C60; struct ColumnDefinition *
0x18004efc5  mov     [rsp+700h+var_6C0], r14d
0x18004efca  call    ?FindColumnEx@DatabaseVolumeSession@@QEBAKPEBUColumnDefinition@@PEAH@Z; DatabaseVolumeSession::FindColumnEx(ColumnDefinition const *,int *)
0x18004efcf  lea     r12, aOnecoreuapBase_62; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18004efd6  mov     [rbp+600h+var_654], eax
0x18004efd9  mov     edi, 0CBh
0x18004efde  cmp     [rsp+700h+var_6C0], r14d
0x18004efe3  jnz     short loc_18004EFF0
0x18004efe5  mov     r8d, edi
0x18004efe8  mov     rdx, r12
0x18004efeb  call    Log_AssertionEvent_2
0x18004eff0  mov     rcx, [rsi+7F8h]; this
0x18004eff7  lea     r8, [rsp+700h+var_6C0]; int *
0x18004effc  lea     rdx, off_180130CA0; struct ColumnDefinition *
0x18004f003  mov     [rsp+700h+var_6C0], r14d
0x18004f008  call    ?FindColumnEx@DatabaseVolumeSession@@QEBAKPEBUColumnDefinition@@PEAH@Z; DatabaseVolumeSession::FindColumnEx(ColumnDefinition const *,int *)
0x18004f00d  mov     [rbp+600h+var_650], eax
0x18004f010  cmp     [rsp+700h+var_6C0], r14d
0x18004f015  jnz     short loc_18004F022
0x18004f017  mov     r8d, edi
0x18004f01a  mov     rdx, r12
0x18004f01d  call    Log_AssertionEvent_2
0x18004f022  mov     rcx, [rsi+7F8h]; this
0x18004f029  lea     r8, [rsp+700h+var_6C0]; int *
0x18004f02e  lea     rdx, off_180130CC0; struct ColumnDefinition *
0x18004f035  mov     [rsp+700h+var_6C0], r14d
0x18004f03a  call    ?FindColumnEx@DatabaseVolumeSession@@QEBAKPEBUColumnDefinition@@PEAH@Z; DatabaseVolumeSession::FindColumnEx(ColumnDefinition const *,int *)
0x18004f03f  mov     [rbp+600h+var_64C], eax
0x18004f042  cmp     [rsp+700h+var_6C0], r14d
0x18004f047  jnz     short loc_18004F054
0x18004f049  mov     r8d, edi
0x18004f04c  mov     rdx, r12
0x18004f04f  call    Log_AssertionEvent_2
0x18004f054  mov     rcx, [rsi+7F8h]; this
0x18004f05b  lea     r8, [rsp+700h+var_6C0]; int *
0x18004f060  lea     rdx, ?UdmTableCols_CallHistory@@3QBUColumnDefinition@@B; struct ColumnDefinition *
0x18004f067  mov     [rsp+700h+var_6C0], r14d
0x18004f06c  call    ?FindColumnEx@DatabaseVolumeSession@@QEBAKPEBUColumnDefinition@@PEAH@Z; DatabaseVolumeSession::FindColumnEx(ColumnDefinition const *,int *)
0x18004f071  mov     [rbp+600h+var_658], eax
0x18004f074  cmp     [rsp+700h+var_6C0], r14d
0x18004f079  jnz     short loc_18004F086
0x18004f07b  mov     r8d, edi
0x18004f07e  mov     rdx, r12
0x18004f081  call    Log_AssertionEvent_2
0x18004f086  mov     rcx, [rsi+7F8h]; this
0x18004f08d  lea     r8, [rsp+700h+var_6C0]; int *
0x18004f092  lea     rdx, off_180130CE0; struct ColumnDefinition *
0x18004f099  mov     [rsp+700h+var_6C0], r14d
0x18004f09e  call    ?FindColumnEx@DatabaseVolumeSession@@QEBAKPEBUColumnDefinition@@PEAH@Z; DatabaseVolumeSession::FindColumnEx(ColumnDefinition const *,int *)
0x18004f0a3  mov     [rbp+600h+var_640], eax
0x18004f0a6  cmp     [rsp+700h+var_6C0], r14d
0x18004f0ab  jnz     short loc_18004F0B8
0x18004f0ad  mov     r8d, edi
0x18004f0b0  mov     rdx, r12
0x18004f0b3  call    Log_AssertionEvent_2
0x18004f0b8  mov     rcx, [rsi+7F8h]; this
0x18004f0bf  lea     r8, [rsp+700h+var_6C0]; int *
0x18004f0c4  lea     rdx, off_180130D00; struct ColumnDefinition *
0x18004f0cb  mov     [rsp+700h+var_6C0], r14d
0x18004f0d0  call    ?FindColumnEx@DatabaseVolumeSession@@QEBAKPEBUColumnDefinition@@PEAH@Z; DatabaseVolumeSession::FindColumnEx(ColumnDefinition const *,int *)
0x18004f0d5  mov     [rbp+600h+var_63C], eax
0x18004f0d8  cmp     [rsp+700h+var_6C0], r14d
0x18004f0dd  jnz     short loc_18004F0EA
0x18004f0df  mov     r8d, edi
0x18004f0e2  mov     rdx, r12
0x18004f0e5  call    Log_AssertionEvent_2
0x18004f0ea  mov     rcx, [rsi+7F8h]; this
0x18004f0f1  lea     r8, [rsp+700h+var_6C0]; int *
0x18004f0f6  lea     rdx, off_180130D40; struct ColumnDefinition *
0x18004f0fd  mov     [rsp+700h+var_6C0], r14d
0x18004f102  call    ?FindColumnEx@DatabaseVolumeSession@@QEBAKPEBUColumnDefinition@@PEAH@Z; DatabaseVolumeSession::FindColumnEx(ColumnDefinition const *,int *)
0x18004f107  mov     r13d, eax
0x18004f10a  cmp     [rsp+700h+var_6C0], r14d
0x18004f10f  jnz     short loc_18004F11C
0x18004f111  mov     r8d, edi
0x18004f114  mov     rdx, r12
0x18004f117  call    Log_AssertionEvent_2
0x18004f11c  mov     rcx, [rsi+7F8h]; this
0x18004f123  lea     r8, [rsp+700h+var_6C0]; int *
0x18004f128  lea     rdx, off_180130D20; struct ColumnDefinition *
0x18004f12f  mov     [rsp+700h+var_6C0], r14d
0x18004f134  call    ?FindColumnEx@DatabaseVolumeSession@@QEBAKPEBUColumnDefinition@@PEAH@Z; DatabaseVolumeSession::FindColumnEx(ColumnDefinition const *,int *)
0x18004f139  mov     r12d, eax
0x18004f13c  cmp     [rsp+700h+var_6C0], r14d
0x18004f141  jnz     short loc_18004F152
0x18004f143  mov     r8d, edi
0x18004f146  lea     rdx, aOnecoreuapBase_62; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18004f14d  call    Log_AssertionEvent_2
0x18004f152  mov     rcx, [rsi+7F8h]; this
0x18004f159  lea     r8, [rsp+700h+var_6C0]; int *
0x18004f15e  lea     rdx, off_180130EE0; struct ColumnDefinition *
0x18004f165  mov     [rsp+700h+var_6C0], r14d
0x18004f16a  call    ?FindColumnEx@DatabaseVolumeSession@@QEBAKPEBUColumnDefinition@@PEAH@Z; DatabaseVolumeSession::FindColumnEx(ColumnDefinition const *,int *)
0x18004f16f  mov     [rbp+600h+var_648], eax
0x18004f172  cmp     [rsp+700h+var_6C0], r14d
0x18004f177  jnz     short loc_18004F188
0x18004f179  mov     r8d, edi
0x18004f17c  lea     rdx, aOnecoreuapBase_62; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18004f183  call    Log_AssertionEvent_2
0x18004f188  mov     rcx, [rsi+800h]; sesid
0x18004f18f  lea     rax, [rsp+700h+tableid]
0x18004f194  mov     edx, [rsi+808h]; dbid
0x18004f19a  lea     r8, ?UdmTableName_CallHistory@@3QBDB; "CallHistory"
0x18004f1a1  mov     [rsp+700h+ptableid], rax; ptableid
0x18004f1a6  xor     r9d, r9d; pvParameters
0x18004f1a9  mov     [rsp+700h+grbit], 8; grbit
0x18004f1b1  mov     dword ptr [rsp+700h+ppv], r14d; cbParameters
0x18004f1b6  mov     [rsp+700h+sesid], rcx
0x18004f1bb  mov     [rsp+700h+tableid], 0FFFFFFFFFFFFFFFFh
0x18004f1c4  call    cs:__imp_JetOpenTableA
0x18004f1ca  test    eax, eax
0x18004f1cc  js      loc_18004FB3C
0x18004f1d2  mov     rdx, [rsp+700h+tableid]; tableid
0x18004f1d7  lea     r8, ?UdmIdxName_CallHistory_ById@@3QBDB; "ById"
0x18004f1de  mov     rcx, [rsp+700h+sesid]; sesid
0x18004f1e3  call    cs:__imp_JetSetCurrentIndexA
0x18004f1e9  test    eax, eax
0x18004f1eb  js      loc_18004FAFC
0x18004f1f1  lea     rdx, [rsp+700h+var_6C0]; int *
0x18004f1f6  mov     [rsp+700h+var_6C0], r14d
0x18004f1fb  lea     rcx, [rsp+700h+sesid]; struct auto_JET_TABLEID *
0x18004f200  call    ?MoveFirst@@YAJAEBVauto_JET_TABLEID@@PEAH@Z; MoveFirst(auto_JET_TABLEID const &,int *)
0x18004f205  mov     edi, eax
0x18004f207  test    eax, eax
0x18004f209  jns     short loc_18004F21B
0x18004f20b  mov     r9d, 0A46h
0x18004f211  mov     edx, 1
0x18004f216  jmp     loc_18004FB0D
0x18004f21b  lea     rcx, [rbx+rbx*2]
0x18004f21f  mov     ebx, 1
0x18004f224  lea     r14, [r15+rcx*4]
0x18004f228  xor     edi, edi
0x18004f22a  cmp     [rsp+700h+var_6C0], edi
0x18004f22e  jz      loc_18004FAD3
0x18004f234  cmp     dword ptr [rsp+700h+var_6A8], edi
0x18004f238  jz      short loc_18004F24C
0x18004f23a  mov     r8d, 8A0h
0x18004f240  lea     rdx, aOnecoreuapBase_62; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18004f247  call    Log_AssertionEvent_2
0x18004f24c  cmp     dword ptr [rsp+700h+var_6A8+4], 2
0x18004f251  mov     rcx, [rsp+700h+SRWLock]; SRWLock
0x18004f256  jnb     short loc_18004F27E
0x18004f258  call    cs:__imp_TryAcquireSRWLockShared
0x18004f25e  test    al, al
0x18004f260  jnz     short loc_18004F278
0x18004f262  mov     ecx, 64h ; 'd'; dwMilliseconds
0x18004f267  call    cs:__imp_Sleep
0x18004f26d  mov     rcx, [rsp+700h+SRWLock]; SRWLock
0x18004f272  call    cs:__imp_AcquireSRWLockShared
0x18004f278  mov     dword ptr [rsp+700h+var_6A8], ebx
0x18004f27c  jmp     short loc_18004F28C
0x18004f27e  call    cs:__imp_AcquireSRWLockExclusive
0x18004f284  mov     dword ptr [rsp+700h+var_6A8], 2
0x18004f28c  movsd   xmm0, cs:?g_ZeroOlItemId@@3UOLITEMID@@B; OLITEMID const g_ZeroOlItemId
0x18004f294  lea     rcx, [rbp+600h+var_584]; void *
0x18004f298  mov     eax, cs:dword_18013A438
0x18004f29e  xor     edx, edx; Val
0x18004f2a0  mov     r8d, 198h; Size
0x18004f2a6  movsd   [rbp+600h+var_590], xmm0
0x18004f2ab  mov     [rbp+600h+var_588], eax
0x18004f2ae  call    memset_0
0x18004f2b3  mov     eax, [rbp+600h+var_658]
0x18004f2b6  xorps   xmm2, xmm2
0x18004f2b9  mov     [rbp+600h+pretrievecolumn.columnid], eax
0x18004f2bf  xorps   xmm1, xmm1
0x18004f2c2  movups  [rsp+700h+var_698], xmm2
0x18004f2c7  mov     eax, dword ptr [rsp+700h+var_698+4]
0x18004f2cb  mov     ecx, 4
0x18004f2d0  movups  [rsp+700h+var_688], xmm2
0x18004f2d5  mov     dword ptr [rbp+600h+pretrievecolumn+4], eax
0x18004f2db  lea     rax, [rbp+600h+var_664]
0x18004f2df  movsd   xmm0, qword ptr [rsp+700h+var_688+4]
0x18004f2e5  movups  [rbp+600h+var_678], xmm2
0x18004f2e9  mov     [rbp+600h+pretrievecolumn.pvData], rax
0x18004f2f0  psrldq  xmm2, 0Ch
0x18004f2f5  movd    dword ptr [rbp+600h+pretrievecolumn+2Ch], xmm2
0x18004f2fd  xorps   xmm2, xmm2
0x18004f300  movups  [rsp+700h+var_698], xmm2
0x18004f305  mov     eax, dword ptr [rsp+700h+var_698+4]
0x18004f309  mov     [rbp+600h+var_1FC], eax
0x18004f30f  lea     rax, [rbp+600h+var_590]
0x18004f313  movups  [rsp+700h+var_688], xmm2
0x18004f318  mov     [rbp+600h+var_1F8], rax
0x18004f31f  psrldq  xmm1, 0Ch
0x18004f324  movsd   qword ptr [rbp+600h+pretrievecolumn.cbActual], xmm0
0x18004f32c  movsd   xmm0, qword ptr [rbp+600h+var_678+4]
0x18004f331  movups  [rbp+600h+var_678], xmm2
0x18004f335  mov     eax, dword ptr [rbp+600h+var_678+4]
0x18004f338  psrldq  xmm2, 8
0x18004f33d  movd    [rbp+600h+pretrievecolumn.ibLongValue], xmm1
0x18004f345  xorps   xmm1, xmm1
0x18004f348  mov     [rbp+600h+var_1DC], eax
0x18004f34e  mov     eax, dword ptr [rbp+600h+var_678+0Ch]
0x18004f351  movd    [rbp+600h+var_1D8], xmm2
0x18004f359  xorps   xmm2, xmm2
0x18004f35c  movups  [rsp+700h+var_698], xmm2
0x18004f361  mov     [rbp+600h+var_1D4], eax
0x18004f367  mov     eax, dword ptr [rsp+700h+var_698+4]
0x18004f36b  movups  [rbp+600h+var_678], xmm2
0x18004f36f  mov     [rbp+600h+var_1CC], eax
0x18004f375  lea     rax, [rbp+600h+var_584]
0x18004f379  movsd   qword ptr [rbp+600h+pretrievecolumn.columnidNextTagged], xmm0
0x18004f381  movsd   xmm0, qword ptr [rsp+700h+var_688+4]
0x18004f387  movups  [rsp+700h+var_688], xmm2
0x18004f38c  mov     [rbp+600h+var_1C8], rax
0x18004f393  mov     eax, [rbp+600h+var_654]
0x18004f396  psrldq  xmm1, 0Ch
0x18004f39b  movsd   [rbp+600h+var_1EC], xmm0
0x18004f3a3  movsd   xmm0, qword ptr [rsp+700h+var_688+4]
0x18004f3a9  movd    [rbp+600h+var_1E4], xmm1
0x18004f3b1  xorps   xmm1, xmm1
0x18004f3b4  psrldq  xmm2, 0Ch
0x18004f3b9  movsd   [rbp+600h+var_1BC], xmm0
0x18004f3c1  movsd   xmm0, qword ptr [rbp+600h+var_678+4]
0x18004f3c6  movd    [rbp+600h+var_1A4], xmm2
0x18004f3ce  xorps   xmm2, xmm2
0x18004f3d1  psrldq  xmm1, 0Ch
0x18004f3d6  mov     [rbp+600h+var_1A0], eax
0x18004f3dc  mov     [rbp+600h+var_664], edi
0x18004f3df  mov     [rbp+600h+var_600], rdi
0x18004f3e3  mov     [rbp+600h+var_668], edi
0x18004f3e6  mov     [rbp+600h+pretrievecolumn.cbData], ecx
0x18004f3ec  mov     [rbp+600h+pretrievecolumn.itagSequence], ebx
0x18004f3f2  mov     [rbp+600h+var_200], r13d
0x18004f3f9  mov     [rbp+600h+var_1F0], 0Ch
0x18004f403  mov     [rbp+600h+var_1E0], ebx
0x18004f409  mov     [rbp+600h+var_1D0], r12d
0x18004f410  mov     [rbp+600h+var_1C0], ecx
0x18004f416  movd    [rbp+600h+var_1B4], xmm1
0x18004f41e  mov     [rbp+600h+var_1B0], ebx
0x18004f424  movsd   [rbp+600h+var_1AC], xmm0
0x18004f42c  movups  [rsp+700h+var_698], xmm2
0x18004f431  movups  [rsp+700h+var_688], xmm2
0x18004f436  movups  [rbp+600h+var_678], xmm2
0x18004f43a  mov     eax, dword ptr [rsp+700h+var_698+4]
0x18004f43e  xorps   xmm1, xmm1
0x18004f441  movsd   xmm0, qword ptr [rsp+700h+var_688+4]
0x18004f447  mov     edx, 0CAh
0x18004f44c  mov     [rbp+600h+var_19C], eax
0x18004f452  lea     rax, [rbp+600h+var_600]
0x18004f456  mov     [rbp+600h+var_198], rax
0x18004f45d  mov     eax, [rbp+600h+var_650]
0x18004f460  mov     [rbp+600h+var_170], eax
0x18004f466  psrldq  xmm2, 0Ch
0x18004f46b  psrldq  xmm1, 0Ch
0x18004f470  movd    [rbp+600h+var_174], xmm2
0x18004f478  xorps   xmm2, xmm2
0x18004f47b  movups  [rsp+700h+var_698], xmm2
0x18004f480  mov     eax, dword ptr [rsp+700h+var_698+4]
0x18004f484  mov     [rbp+600h+var_16C], eax
0x18004f48a  lea     rax, [rbp+600h+var_580]
0x18004f491  mov     [rbp+600h+var_168], rax
0x18004f498  mov     eax, [rbp+600h+var_64C]
0x18004f49b  movups  [rsp+700h+var_688], xmm2
0x18004f4a0  mov     [rbp+600h+var_140], eax
0x18004f4a6  movsd   [rbp+600h+var_18C], xmm0
0x18004f4ae  movsd   xmm0, qword ptr [rbp+600h+var_678+4]
0x18004f4b3  movups  [rbp+600h+var_678], xmm2
0x18004f4b7  mov     [rbp+600h+var_190], 8
  ... truncated ...
```
