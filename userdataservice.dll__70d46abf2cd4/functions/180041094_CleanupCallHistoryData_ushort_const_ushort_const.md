# CleanupCallHistoryData(ushort const *,ushort const *)

- ea: `0x180041094`
- end: `0x18004198b`
- name: `?CleanupCallHistoryData@@YAJPEBG0@Z`
- size: `2295`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned __int16 *)`
- caller_count: `3`
- callee_count: `26`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18004038c`
- `0x1800adb04`
- `0x1800ae8a0`

## callees

- `0x1800049f0`
- `0x180008ee8`
- `0x180008f0c`
- `0x18000e1f8`
- `0x180030180`
- `0x18003bf04`
- `0x180041094`
- `0x180066860`
- `0x180068698`
- `0x18006a8ac`
- `0x18006b13c`
- `0x180075f98`
- `0x180076664`
- `0x180084a84`
- `0x1800977c4`
- `0x1800a1270`
- `0x1800a1568`
- `0x1800ac3c8`
- `0x1800da920`
- `0x1800db6b0`
- `0x1800db8c8`
- `0x1800dbb50`
- `0x1800e0a08`
- `0x1800e1428`
- `0x18012c76a`
- `0x18012c7b0`

## import_xrefs

- `ESENT!JetOpenTableA` at `0x180041191`
- `ESENT!JetOpenTableA` at `0x180041191`
- `ESENT!JetDelete` at `0x1800416a9`
- `ESENT!JetDelete` at `0x1800416a9`
- `ESENT!JetMakeKey` at `0x1800413c3`
- `ESENT!JetMakeKey` at `0x180041412`
- `ESENT!JetMakeKey` at `0x1800413c3`
- `ESENT!JetMakeKey` at `0x180041412`
- `ESENT!JetSetCurrentIndexA` at `0x18004138e`
- `ESENT!JetSetCurrentIndexA` at `0x18004138e`
- `ESENT!JetRetrieveColumns` at `0x180041620`
- `ESENT!JetRetrieveColumns` at `0x180041620`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180041311`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180041311`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180041130`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180041130`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180041327`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180041327`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18004131a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18004131a`
- `api-ms-win-core-synch-l1-1-0!TryAcquireSRWLockShared` at `0x180041302`
- `api-ms-win-core-synch-l1-1-0!TryAcquireSRWLockShared` at `0x180041302`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800411d1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180041856`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800418f5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800411d1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180041856`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800418f5`

## string_xrefs

- `0x18004121d`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\datasession.cpp`
- `0x180041253`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\datasession.cpp`
- `0x180041289`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\datasession.cpp`
- `0x1800412bf`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\datasession.cpp`
- `0x1800412ec`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\datasession.cpp`
- `0x18004110b`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\callhistory.cpp`
- `0x1800411a8`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\callhistory.cpp`
- `0x1800412d4`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\callhistory.cpp`
- `0x180041950`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\callhistory.cpp`

## pseudocode

```c
__int64 __fastcall CleanupCallHistoryData(const unsigned __int16 *a1, unsigned __int16 *a2)
{
  AppInstanceCache *v2; // rax
  AppInstanceCache *v3; // rsi
  int v4; // eax
  unsigned int HresultFromJetError; // edi
  __int64 v6; // rdi
  struct _RTL_CRITICAL_SECTION *v7; // rbx
  RTL_SRWLOCK *v8; // r12
  RTL_SRWLOCK *v9; // r12
  JET_DBID v10; // edx
  int v11; // r13d
  JET_SESID v12; // rcx
  JET_ERR v13; // eax
  DatabaseVolumeSession *v14; // rcx
  __int64 v15; // rcx
  DatabaseVolumeSession *v16; // rcx
  __int64 v17; // rcx
  DatabaseVolumeSession *v18; // rcx
  __int64 v19; // rcx
  DatabaseVolumeSession *v20; // rcx
  __int64 v21; // rcx
  __int64 v22; // rcx
  int v23; // r12d
  int v24; // eax
  JET_ERR v25; // eax
  JET_ERR Key; // eax
  unsigned int v27; // edx
  int v28; // eax
  JET_ERR v29; // eax
  int v30; // eax
  __int64 v31; // r13
  JET_ERR v32; // eax
  int v33; // eax
  JET_ERR v34; // eax
  __int64 v35; // rax
  __int64 v36; // r12
  int v37; // eax
  unsigned int v38; // r12d
  unsigned int v39; // eax
  __int64 v40; // r9
  __int64 v41; // rcx
  unsigned __int64 v42; // r12
  unsigned __int64 i; // r14
  int v45; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v46; // [rsp+48h] [rbp-B8h] BYREF
  RTL_SRWLOCK *v47; // [rsp+50h] [rbp-B0h]
  JET_SESID sesid; // [rsp+58h] [rbp-A8h] BYREF
  JET_TABLEID tableid; // [rsp+60h] [rbp-A0h] BYREF
  int v50; // [rsp+68h] [rbp-98h] BYREF
  _QWORD v51[2]; // [rsp+70h] [rbp-90h] BYREF
  __int64 v52; // [rsp+80h] [rbp-80h] BYREF
  int pvData; // [rsp+88h] [rbp-78h] BYREF
  int v54; // [rsp+8Ch] [rbp-74h] BYREF
  int v55; // [rsp+90h] [rbp-70h]
  __int64 v56; // [rsp+98h] [rbp-68h] BYREF
  __int64 v57; // [rsp+A0h] [rbp-60h]
  JET_COLUMNID Column; // [rsp+B0h] [rbp-50h]
  unsigned int v59; // [rsp+B4h] [rbp-4Ch]
  unsigned int v60; // [rsp+B8h] [rbp-48h]
  unsigned int v61; // [rsp+BCh] [rbp-44h]
  struct _FILETIME v62; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v63; // [rsp+C8h] [rbp-38h] BYREF
  unsigned __int16 *v64; // [rsp+D0h] [rbp-30h]
  __int64 v65; // [rsp+D8h] [rbp-28h]
  __int128 v66; // [rsp+F0h] [rbp-10h] BYREF
  __int128 v67; // [rsp+100h] [rbp+0h]
  __int128 v68; // [rsp+110h] [rbp+10h]
  JET_RETRIEVECOLUMN pretrievecolumn; // [rsp+140h] [rbp+40h] BYREF
  unsigned int v70; // [rsp+170h] [rbp+70h]
  int v71; // [rsp+174h] [rbp+74h]
  __int64 *v72; // [rsp+178h] [rbp+78h]
  int v73; // [rsp+180h] [rbp+80h]
  __int64 v74; // [rsp+184h] [rbp+84h]
  unsigned int v75; // [rsp+18Ch] [rbp+8Ch]
  int v76; // [rsp+190h] [rbp+90h]
  __int64 v77; // [rsp+194h] [rbp+94h]
  unsigned int ibLongValue; // [rsp+19Ch] [rbp+9Ch]
  unsigned int v79; // [rsp+1A0h] [rbp+A0h]
  int v80; // [rsp+1A4h] [rbp+A4h]
  unsigned __int16 *v81; // [rsp+1A8h] [rbp+A8h]
  int v82; // [rsp+1B0h] [rbp+B0h]
  __int64 v83; // [rsp+1B4h] [rbp+B4h]
  unsigned int v84; // [rsp+1BCh] [rbp+BCh]
  int v85; // [rsp+1C0h] [rbp+C0h]
  int v86; // [rsp+1C4h] [rbp+C4h]
  JET_ERR err; // [rsp+1C8h] [rbp+C8h]
  int v88; // [rsp+1CCh] [rbp+CCh]
  unsigned int v89; // [rsp+1D0h] [rbp+D0h]
  int v90; // [rsp+1D4h] [rbp+D4h]
  struct _FILETIME *v91; // [rsp+1D8h] [rbp+D8h]
  int v92; // [rsp+1E0h] [rbp+E0h]
  __int64 v93; // [rsp+1E4h] [rbp+E4h]
  unsigned int v94; // [rsp+1ECh] [rbp+ECh]
  int v95; // [rsp+1F0h] [rbp+F0h]
  int v96; // [rsp+1F4h] [rbp+F4h]
  JET_ERR v97; // [rsp+1F8h] [rbp+F8h]
  int v98; // [rsp+1FCh] [rbp+FCh]
  unsigned __int16 v99[1032]; // [rsp+200h] [rbp+100h] BYREF

  v64 = a2;
  v2 = (AppInstanceCache *)operator new(0x28u);
  if ( !v2 || (v3 = AppInstanceCache::AppInstanceCache(v2)) == 0 )
  {
    HresultFromJetError = -2147024882;
    Log_HREvent(
      2147942414LL,
      0,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\callhistory.cpp",
      5142);
    return HresultFromJetError;
  }
  v52 = 0;
  v4 = CreateCallHistorySession(0, &v52);
  HresultFromJetError = v4;
  if ( v4 < 0 )
  {
    Log_HREvent(
      (unsigned int)v4,
      1,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\callhistory.cpp",
      5148);
LABEL_8:
    ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(&v52);
    tlx::_delete<AppInstanceCache>(v3);
    return HresultFromJetError;
  }
  v6 = v52;
  v7 = (struct _RTL_CRITICAL_SECTION *)(v52 + 2064);
  EnterCriticalSection((LPCRITICAL_SECTION)(v52 + 2064));
  v8 = *(RTL_SRWLOCK **)(v6 + 2040);
  sesid = *(_QWORD *)(v6 + 2048);
  v9 = v8 + 15;
  tableid = -1;
  v10 = *(_DWORD *)(v6 + 2056);
  v11 = 0;
  v12 = *(_QWORD *)(v6 + 2048);
  v46 = 0;
  v47 = v9;
  v13 = JetOpenTableA(v12, v10, "CallHistory", 0, 0, 8u, &tableid);
  if ( v13 < 0 )
  {
    HresultFromJetError = MakeHresultFromJetError(v13);
    Log_HREvent(
      HresultFromJetError,
      0,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\callhistory.cpp",
      5162);
LABEL_7:
    auto_JET_TABLEID::~auto_JET_TABLEID((auto_JET_TABLEID *)&sesid);
    BackoffContext::Unlock((BackoffContext *)&v46);
    LeaveCriticalSection(v7);
    goto LABEL_8;
  }
  v14 = *(DatabaseVolumeSession **)(v6 + 2040);
  v45 = 0;
  Column = DatabaseVolumeSession::FindColumnEx(v14, (const struct ColumnDefinition *)&UdmTableCols_CallHistory, &v45);
  if ( !v45 )
    Log_AssertionEvent_2(
      v15,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\datasession.cpp",
      203);
  v16 = *(DatabaseVolumeSession **)(v6 + 2040);
  v45 = 0;
  v60 = DatabaseVolumeSession::FindColumnEx(v16, (const struct ColumnDefinition *)&off_180130D60, &v45);
  if ( !v45 )
    Log_AssertionEvent_2(
      v17,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\datasession.cpp",
      203);
  v18 = *(DatabaseVolumeSession **)(v6 + 2040);
  v45 = 0;
  v61 = DatabaseVolumeSession::FindColumnEx(v18, (const struct ColumnDefinition *)&off_180130EA0, &v45);
  if ( !v45 )
    Log_AssertionEvent_2(
      v19,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\datasession.cpp",
      203);
  v20 = *(DatabaseVolumeSession **)(v6 + 2040);
  v45 = 0;
  v59 = DatabaseVolumeSession::FindColumnEx(v20, (const struct ColumnDefinition *)&off_180130C60, &v45);
  if ( !v45 )
    Log_AssertionEvent_2(
      v21,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\datasession.cpp",
      203);
  utl::vector<tlx::auto_xxx<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),0>,utl::allocator<tlx::auto_xxx<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),0>>>::vector<tlx::auto_xxx<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),0>,utl::allocator<tlx::auto_xxx<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),0>>>(&v56);
  while ( 2 )
  {
    if ( v11 )
      Log_AssertionEvent_2(
        v22,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\datasession.cpp",
        2208);
    if ( HIDWORD(v46) >= 2 )
    {
      AcquireSRWLockExclusive(v9);
      LODWORD(v46) = 2;
    }
    else
    {
      if ( !TryAcquireSRWLockShared(v9) )
      {
        Sleep(0x64u);
        AcquireSRWLockShared(v9);
      }
      LODWORD(v46) = 1;
    }
    v23 = 0;
    v51[0] = *(_QWORD *)(v6 + 2048);
    v51[1] = 0;
    v24 = auto_JET_TRANSACTION::Begin((auto_JET_TRANSACTION *)v51, 0);
    if ( v24 < 0 )
    {
      v39 = MakeHresultFromJetError(v24);
      v40 = 5181;
      goto LABEL_60;
    }
    v54 = 0;
    memset_0(v99, 0, 0x802u);
    v62 = 0;
    v63 = 0;
    v25 = JetSetCurrentIndexA(sesid, tableid, "ByLineKind");
    if ( v25 < 0 )
    {
      v39 = MakeHresultFromJetError(v25);
      v40 = 5188;
      goto LABEL_60;
    }
    pvData = 1;
    v50 = 0;
    Key = JetMakeKey(sesid, tableid, &pvData, 4u, 0x101u);
    if ( Key < 0 )
    {
      v39 = MakeHresultFromJetError(Key);
      v40 = 5192;
      goto LABEL_60;
    }
    v28 = auto_JET_TABLEID::MaybeSeek((auto_JET_TABLEID *)&sesid, v27, (enum TableSeekResult *)&v50);
    if ( v28 < 0 )
    {
      v39 = MakeHresultFromJetError(v28);
      v40 = 5193;
      goto LABEL_60;
    }
    v45 = 0;
    if ( (unsigned int)(v50 - 2) <= 1 )
    {
      v29 = JetMakeKey(sesid, tableid, &pvData, 4u, 0x201u);
      if ( v29 < 0 )
      {
        v39 = MakeHresultFromJetError(v29);
        v40 = 5198;
      }
      else
      {
        v30 = auto_JET_TABLEID::MaybeSetRange((auto_JET_TABLEID *)&sesid, 3u, &v45);
        if ( v30 >= 0 )
          goto LABEL_32;
        v39 = MakeHresultFromJetError(v30);
        v40 = 5199;
      }
LABEL_60:
      v41 = v39;
      HresultFromJetError = v39;
LABEL_61:
      Log_HREvent(
        v41,
        0,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\callhistory.cpp",
        v40);
LABEL_67:
      auto_JET_TRANSACTION::~auto_JET_TRANSACTION((auto_JET_TRANSACTION *)v51);
      BackoffContext::Unlock((BackoffContext *)&v46);
      utl::vector<UdmEmailParticipant,utl::allocator<UdmEmailParticipant>>::_Uninit(&v56);
      goto LABEL_7;
    }
LABEL_32:
    v55 = 0;
    while ( 1 )
    {
      v31 = v56;
      if ( !v45 )
        break;
      if ( v23 < 0 )
        goto LABEL_68;
      pretrievecolumn.columnid = Column;
      pretrievecolumn.itagSequence = 1;
      *(&pretrievecolumn.columnid + 1) = 0;
      pretrievecolumn.pvData = &v54;
      pretrievecolumn.columnidNextTagged = 0;
      *(&pretrievecolumn.err + 1) = 0;
      v70 = v59;
      pretrievecolumn.cbData = 4;
      pretrievecolumn.err = _mm_cvtsi128_si32(_mm_srli_si128((__m128i)0LL, 8));
      v71 = 0;
      v72 = &v63;
      v79 = v60;
      v73 = 8;
      v76 = 1;
      *(_QWORD *)&pretrievecolumn.cbActual = 0;
      pretrievecolumn.ibLongValue = _mm_cvtsi128_si32(_mm_srli_si128((__m128i)0LL, 12));
      ibLongValue = pretrievecolumn.ibLongValue;
      v80 = 0;
      v81 = v99;
      v82 = 2050;
      v74 = 0;
      v86 = 0;
      v88 = 0;
      v89 = v61;
      v75 = pretrievecolumn.ibLongValue;
      v77 = 0;
      err = pretrievecolumn.err;
      v66 = 0;
      v90 = 0;
      v83 = 0;
      v67 = 0;
      v91 = &v62;
      v84 = pretrievecolumn.ibLongValue;
      v85 = 1;
      v68 = 0;
      v92 = 8;
      v96 = 0;
      v94 = pretrievecolumn.ibLongValue;
      v93 = 0;
      v95 = 1;
      v97 = pretrievecolumn.err;
      v98 = 0;
      v32 = JetRetrieveColumns(sesid, tableid, &pretrievecolumn, 4u);
      if ( v32 != -1017 )
      {
        if ( v32 < 0 )
        {
          v39 = MakeHresultFromJetError(v32);
          v40 = 5220;
          goto LABEL_60;
        }
        if ( !pretrievecolumn.err )
        {
          v50 = 1;
          if ( err || v97 )
            goto LABEL_43;
          v33 = IsCallEntryStale(v3, v64, v99, v62, &v50);
          if ( v33 < 0 )
          {
            Log_HREvent(
              (unsigned int)v33,
              0,
              "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\callhistory.cpp",
              5244);
            goto LABEL_48;
          }
          if ( v50 )
          {
LABEL_43:
            v34 = JetDelete(*(_QWORD *)(v6 + 2048), tableid);
            if ( v34 == -1102 )
            {
              BackoffContext::NeedsBackoff((BackoffContext *)&v46);
              v36 = v31;
              v57 = v31;
              v55 = 1;
              goto LABEL_53;
            }
            if ( v34 < 0 )
            {
              v39 = MakeHresultFromJetError(v34);
              v40 = 5263;
              goto LABEL_60;
            }
            memset_0(&v66, 0, 0x48u);
            LODWORD(v66) = 1;
            v65 = 0;
            HIDWORD(v66) = 0;
            DWORD1(v67) = v54;
            v35 = *((_QWORD *)&v67 + 1);
            if ( !err )
              v35 = v63;
            *((_QWORD *)&v67 + 1) = v35;
            DWORD2(v66) = 1;
            LODWORD(v67) = 1;
            if ( !(unsigned __int8)utl::vector<UdmNotifyStructure,utl::allocator<UdmNotifyStructure>>::_PushBackOne<UdmNotifyStructure const &>(
                                     &v56,
                                     &v66) )
            {
              HresultFromJetError = -2147024882;
              v40 = 5281;
              v41 = 2147942414LL;
              goto LABEL_61;
            }
          }
        }
      }
LABEL_48:
      v23 = Move(sesid, tableid, 1, &v45);
    }
    if ( v23 < 0 )
    {
LABEL_68:
      Log_HREvent(
        (unsigned int)v23,
        1,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\callhistory.cpp",
        5284);
      auto_JET_TRANSACTION::~auto_JET_TRANSACTION((auto_JET_TRANSACTION *)v51);
      BackoffContext::Unlock((BackoffContext *)&v46);
      utl::vector<UdmEmailParticipant,utl::allocator<UdmEmailParticipant>>::_Uninit(&v56);
      auto_JET_TABLEID::~auto_JET_TABLEID((auto_JET_TABLEID *)&sesid);
      BackoffContext::Unlock((BackoffContext *)&v46);
      LeaveCriticalSection(v7);
      HresultFromJetError = v23;
      goto LABEL_8;
    }
    v37 = auto_JET_TRANSACTION::Commit((auto_JET_TRANSACTION *)v51, 1u);
    v38 = v37;
    if ( v37 < 0 )
    {
      Log_HREvent(
        (unsigned int)v37,
        1,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\callhistory.cpp",
        5295);
      HresultFromJetError = v38;
      goto LABEL_67;
    }
    v36 = v57;
LABEL_53:
    auto_JET_TRANSACTION::~auto_JET_TRANSACTION((auto_JET_TRANSACTION *)v51);
    BackoffContext::Unlock((BackoffContext *)&v46);
    if ( v55 )
    {
      v9 = v47;
      v11 = v46;
      continue;
    }
    break;
  }
  v42 = 0x8E38E38E38E38E39uLL * ((v36 - v31) >> 3);
  if ( v42 )
  {
    for ( i = 0; i < v42; ++i )
      DatabaseVolumeSession::PushNotify(
        *(DatabaseVolumeSession **)(v6 + 2040),
        (const struct UdmNotifyStructure *)(v31 + 72 * i));
  }
  utl::vector<UdmEmailParticipant,utl::allocator<UdmEmailParticipant>>::_Uninit(&v56);
  auto_JET_TABLEID::~auto_JET_TABLEID((auto_JET_TABLEID *)&sesid);
  BackoffContext::Unlock((BackoffContext *)&v46);
  LeaveCriticalSection(v7);
  ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(&v52);
  tlx::_delete<AppInstanceCache>(v3);
  return 0;
}

```

## disassembly

```asm
0x180041094  push    rbp
0x180041096  push    rbx
0x180041097  push    rsi
0x180041098  push    rdi
0x180041099  push    r12
0x18004109b  push    r13
0x18004109d  push    r14
0x18004109f  push    r15
0x1800410a1  lea     rbp, [rsp-928h]
0x1800410a9  sub     rsp, 0A28h
0x1800410b0  mov     rax, cs:__security_cookie
0x1800410b7  xor     rax, rsp
0x1800410ba  mov     [rbp+960h+var_50], rax
0x1800410c1  mov     ecx, 28h ; '('; Size
0x1800410c6  mov     [rbp+960h+var_990], rdx
0x1800410ca  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800410cf  xor     r14d, r14d
0x1800410d2  test    rax, rax
0x1800410d5  jz      loc_18004194B
0x1800410db  mov     rcx, rax; this
0x1800410de  call    ??0AppInstanceCache@@QEAA@XZ; AppInstanceCache::AppInstanceCache(void)
0x1800410e3  mov     rsi, rax
0x1800410e6  test    rax, rax
0x1800410e9  jz      loc_18004194B
0x1800410ef  mov     ecx, r14d
0x1800410f2  mov     [rbp+960h+var_9E0], r14
0x1800410f6  lea     rdx, [rbp+960h+var_9E0]
0x1800410fa  call    ?CreateCallHistorySession@@YAJUUdmCreateDataSessionControls@@PEAPEAVCallHistoryDataSession@@@Z; CreateCallHistorySession(UdmCreateDataSessionControls,CallHistoryDataSession * *)
0x1800410ff  mov     edi, eax
0x180041101  test    eax, eax
0x180041103  jns     short loc_180041122
0x180041105  mov     r9d, 141Ch
0x18004110b  lea     r8, aOnecoreuapBase_43; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180041112  lea     edx, [r14+1]
0x180041116  mov     ecx, eax
0x180041118  call    Log_HREvent
0x18004111d  jmp     loc_1800411D7
0x180041122  mov     rdi, [rbp+960h+var_9E0]
0x180041126  lea     rbx, [rdi+810h]
0x18004112d  mov     rcx, rbx; lpCriticalSection
0x180041130  call    cs:__imp_EnterCriticalSection
0x180041136  mov     rax, [rdi+800h]
0x18004113d  lea     r8, ?UdmTableName_CallHistory@@3QBDB; "CallHistory"
0x180041144  mov     r12, [rdi+7F8h]
0x18004114b  xor     r9d, r9d; pvParameters
0x18004114e  mov     [rsp+0A60h+sesid], rax
0x180041153  add     r12, 78h ; 'x'
0x180041157  mov     [rsp+0A60h+tableid], 0FFFFFFFFFFFFFFFFh
0x180041160  lea     rax, [rsp+0A60h+tableid]
0x180041165  mov     edx, [rdi+808h]; dbid
0x18004116b  mov     r13d, r14d
0x18004116e  mov     rcx, [rdi+800h]; sesid
0x180041175  mov     [rsp+0A60h+ptableid], rax; ptableid
0x18004117a  mov     [rsp+0A60h+grbit], 8; grbit
0x180041182  mov     [rsp+0A60h+cbParameters], r14d; cbParameters
0x180041187  mov     [rsp+0A60h+var_A18], r14
0x18004118c  mov     [rsp+0A60h+var_A10], r12
0x180041191  call    cs:__imp_JetOpenTableA
0x180041197  test    eax, eax
0x180041199  jns     short loc_1800411ED
0x18004119b  mov     ecx, eax; int
0x18004119d  call    ?MakeHresultFromJetError@@YAJJ@Z; MakeHresultFromJetError(long)
0x1800411a2  mov     r9d, 142Ah
0x1800411a8  lea     r8, aOnecoreuapBase_43; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800411af  xor     edx, edx
0x1800411b1  mov     ecx, eax
0x1800411b3  mov     edi, eax
0x1800411b5  call    Log_HREvent
0x1800411ba  lea     rcx, [rsp+0A60h+sesid]; this
0x1800411bf  call    ??1auto_JET_TABLEID@@QEAA@XZ; auto_JET_TABLEID::~auto_JET_TABLEID(void)
0x1800411c4  lea     rcx, [rsp+0A60h+var_A18]; this
0x1800411c9  call    ?Unlock@BackoffContext@@QEAAXXZ; BackoffContext::Unlock(void)
0x1800411ce  mov     rcx, rbx; lpCriticalSection
0x1800411d1  call    cs:__imp_LeaveCriticalSection
0x1800411d7  lea     rcx, [rbp+960h+var_9E0]
0x1800411db  call    ??1?$CComPtrBase@UISODACompletionCallback@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(void)
0x1800411e0  mov     rcx, rsi; Block
0x1800411e3  call    ??$_delete@VAppInstanceCache@@@tlx@@YAXPEAVAppInstanceCache@@@Z; tlx::_delete<AppInstanceCache>(AppInstanceCache *)
0x1800411e8  jmp     loc_180041966
0x1800411ed  mov     rcx, [rdi+7F8h]; this
0x1800411f4  lea     r8, [rsp+0A60h+var_A20]; int *
0x1800411f9  lea     rdx, ?UdmTableCols_CallHistory@@3QBUColumnDefinition@@B; struct ColumnDefinition *
0x180041200  mov     [rsp+0A60h+var_A20], r14d
0x180041205  call    ?FindColumnEx@DatabaseVolumeSession@@QEBAKPEBUColumnDefinition@@PEAH@Z; DatabaseVolumeSession::FindColumnEx(ColumnDefinition const *,int *)
0x18004120a  mov     r15d, 0CBh
0x180041210  mov     [rbp+960h+var_9B0], eax
0x180041213  cmp     [rsp+0A60h+var_A20], r14d
0x180041218  jnz     short loc_180041229
0x18004121a  mov     r8d, r15d
0x18004121d  lea     rdx, aOnecoreuapBase_62; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180041224  call    Log_AssertionEvent_2
0x180041229  mov     rcx, [rdi+7F8h]; this
0x180041230  lea     r8, [rsp+0A60h+var_A20]; int *
0x180041235  lea     rdx, off_180130D60; struct ColumnDefinition *
0x18004123c  mov     [rsp+0A60h+var_A20], r14d
0x180041241  call    ?FindColumnEx@DatabaseVolumeSession@@QEBAKPEBUColumnDefinition@@PEAH@Z; DatabaseVolumeSession::FindColumnEx(ColumnDefinition const *,int *)
0x180041246  mov     [rbp+960h+var_9A8], eax
0x180041249  cmp     [rsp+0A60h+var_A20], r14d
0x18004124e  jnz     short loc_18004125F
0x180041250  mov     r8d, r15d
0x180041253  lea     rdx, aOnecoreuapBase_62; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18004125a  call    Log_AssertionEvent_2
0x18004125f  mov     rcx, [rdi+7F8h]; this
0x180041266  lea     r8, [rsp+0A60h+var_A20]; int *
0x18004126b  lea     rdx, off_180130EA0; struct ColumnDefinition *
0x180041272  mov     [rsp+0A60h+var_A20], r14d
0x180041277  call    ?FindColumnEx@DatabaseVolumeSession@@QEBAKPEBUColumnDefinition@@PEAH@Z; DatabaseVolumeSession::FindColumnEx(ColumnDefinition const *,int *)
0x18004127c  mov     [rbp+960h+var_9A4], eax
0x18004127f  cmp     [rsp+0A60h+var_A20], r14d
0x180041284  jnz     short loc_180041295
0x180041286  mov     r8d, r15d
0x180041289  lea     rdx, aOnecoreuapBase_62; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180041290  call    Log_AssertionEvent_2
0x180041295  mov     rcx, [rdi+7F8h]; this
0x18004129c  lea     r8, [rsp+0A60h+var_A20]; int *
0x1800412a1  lea     rdx, off_180130C60; struct ColumnDefinition *
0x1800412a8  mov     [rsp+0A60h+var_A20], r14d
0x1800412ad  call    ?FindColumnEx@DatabaseVolumeSession@@QEBAKPEBUColumnDefinition@@PEAH@Z; DatabaseVolumeSession::FindColumnEx(ColumnDefinition const *,int *)
0x1800412b2  mov     [rbp+960h+var_9AC], eax
0x1800412b5  cmp     [rsp+0A60h+var_A20], r14d
0x1800412ba  jnz     short loc_1800412CB
0x1800412bc  mov     r8d, r15d
0x1800412bf  lea     rdx, aOnecoreuapBase_62; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800412c6  call    Log_AssertionEvent_2
0x1800412cb  lea     rcx, [rbp+960h+var_9C8]
0x1800412cf  call    ??0?$vector@V?$auto_xxx@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@Z$0A@@tlx@@V?$allocator@V?$auto_xxx@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@Z$0A@@tlx@@@utl@@@utl@@QEAA@XZ; utl::vector<tlx::auto_xxx<ushort *,void (*)(ushort *),&SysFreeString(ushort *),0>,utl::allocator<tlx::auto_xxx<ushort *,void (*)(ushort *),&SysFreeString(ushort *),0>>>::vector<tlx::auto_xxx<ushort *,void (*)(ushort *),&SysFreeString(ushort *),0>,utl::allocator<tlx::auto_xxx<ushort *,void (*)(ushort *),&SysFreeString(ushort *),0>>>(void)
0x1800412d4  lea     r14, aOnecoreuapBase_43; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800412db  mov     r15d, 1
0x1800412e1  test    r13d, r13d
0x1800412e4  jz      short loc_1800412F8
0x1800412e6  mov     r8d, 8A0h
0x1800412ec  lea     rdx, aOnecoreuapBase_62; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800412f3  call    Log_AssertionEvent_2
0x1800412f8  cmp     dword ptr [rsp+0A60h+var_A18+4], 2
0x1800412fd  mov     rcx, r12; SRWLock
0x180041300  jnb     short loc_180041327
0x180041302  call    cs:__imp_TryAcquireSRWLockShared
0x180041308  test    al, al
0x18004130a  jnz     short loc_180041320
0x18004130c  mov     ecx, 64h ; 'd'; dwMilliseconds
0x180041311  call    cs:__imp_Sleep
0x180041317  mov     rcx, r12; SRWLock
0x18004131a  call    cs:__imp_AcquireSRWLockShared
0x180041320  mov     dword ptr [rsp+0A60h+var_A18], r15d
0x180041325  jmp     short loc_180041335
0x180041327  call    cs:__imp_AcquireSRWLockExclusive
0x18004132d  mov     dword ptr [rsp+0A60h+var_A18], 2
0x180041335  mov     rax, [rdi+800h]
0x18004133c  lea     rcx, [rsp+0A60h+var_9F0]; this
0x180041341  xor     r12d, r12d
0x180041344  mov     [rsp+0A60h+var_9F0], rax
0x180041349  xor     edx, edx; unsigned int
0x18004134b  mov     [rsp+0A60h+var_9E8], r12
0x180041350  call    ?Begin@auto_JET_TRANSACTION@@QEAAJK@Z; auto_JET_TRANSACTION::Begin(ulong)
0x180041355  test    eax, eax
0x180041357  js      loc_180041939
0x18004135d  xor     edx, edx; Val
0x18004135f  mov     [rbp+960h+var_9D4], r12d
0x180041363  mov     r8d, 802h; Size
0x180041369  lea     rcx, [rbp+960h+var_860]; void *
0x180041370  call    memset_0
0x180041375  mov     rdx, [rsp+0A60h+tableid]; tableid
0x18004137a  lea     r8, ?UdmIdxName_CallHistory_ByLineKind@@3QBDB; "ByLineKind"
0x180041381  mov     rcx, [rsp+0A60h+sesid]; sesid
0x180041386  mov     qword ptr [rbp+960h+var_9A0.dwLowDateTime], r12
0x18004138a  mov     [rbp+960h+var_998], r12
0x18004138e  call    cs:__imp_JetSetCurrentIndexA
0x180041394  test    eax, eax
0x180041396  js      loc_180041927
0x18004139c  mov     rdx, [rsp+0A60h+tableid]; tableid
0x1800413a1  lea     r13d, [r12+4]
0x1800413a6  mov     rcx, [rsp+0A60h+sesid]; sesid
0x1800413ab  lea     r8, [rbp+960h+pvData]; pvData
0x1800413af  mov     r9d, r13d; cbData
0x1800413b2  mov     [rbp+960h+pvData], r15d
0x1800413b6  mov     [rsp+0A60h+var_9F8], r12d
0x1800413bb  mov     [rsp+0A60h+cbParameters], 101h; grbit
0x1800413c3  call    cs:__imp_JetMakeKey
0x1800413c9  test    eax, eax
0x1800413cb  js      loc_180041915
0x1800413d1  lea     r8, [rsp+0A60h+var_9F8]; enum TableSeekResult *
0x1800413d6  lea     rcx, [rsp+0A60h+sesid]; this
0x1800413db  call    ?MaybeSeek@auto_JET_TABLEID@@QEAAJKPEAW4TableSeekResult@@@Z; auto_JET_TABLEID::MaybeSeek(ulong,TableSeekResult *)
0x1800413e0  test    eax, eax
0x1800413e2  js      loc_180041903
0x1800413e8  mov     eax, [rsp+0A60h+var_9F8]
0x1800413ec  add     eax, 0FFFFFFFEh
0x1800413ef  mov     [rsp+0A60h+var_A20], r12d
0x1800413f4  cmp     eax, r15d
0x1800413f7  ja      short loc_18004143C
0x1800413f9  mov     rdx, [rsp+0A60h+tableid]; tableid
0x1800413fe  lea     r8, [rbp+960h+pvData]; pvData
0x180041402  mov     rcx, [rsp+0A60h+sesid]; sesid
0x180041407  mov     r9d, r13d; cbData
0x18004140a  mov     [rsp+0A60h+cbParameters], 201h; grbit
0x180041412  call    cs:__imp_JetMakeKey
0x180041418  test    eax, eax
0x18004141a  js      loc_1800417A4
0x180041420  lea     r8, [rsp+0A60h+var_A20]; int *
0x180041425  lea     edx, [r12+3]; unsigned int
0x18004142a  lea     rcx, [rsp+0A60h+sesid]; this
0x18004142f  call    ?MaybeSetRange@auto_JET_TABLEID@@QEAAJKPEAH@Z; auto_JET_TABLEID::MaybeSetRange(ulong,int *)
0x180041434  test    eax, eax
0x180041436  js      loc_180041795
0x18004143c  mov     [rbp+960h+var_9D0], r12d
0x180041440  cmp     [rsp+0A60h+var_A20], 0
0x180041445  mov     r13, [rbp+960h+var_9C8]
0x180041449  jz      loc_180041747
0x18004144f  test    r12d, r12d
0x180041452  js      loc_1800418AD
0x180041458  mov     eax, [rbp+960h+var_9B0]
0x18004145b  xorps   xmm2, xmm2
0x18004145e  mov     [rbp+960h+pretrievecolumn.columnid], eax
0x180041461  xorps   xmm1, xmm1
0x180041464  movups  [rbp+960h+var_950], xmm2
0x180041468  mov     ecx, 4
0x18004146d  mov     [rbp+960h+pretrievecolumn.itagSequence], r15d
0x180041471  movups  [rbp+960h+var_970], xmm2
0x180041475  mov     eax, dword ptr [rbp+960h+var_970+4]
0x180041478  mov     dword ptr [rbp+960h+pretrievecolumn+4], eax
0x18004147b  lea     rax, [rbp+960h+var_9D4]
0x18004147f  mov     [rbp+960h+pretrievecolumn.pvData], rax
0x180041483  lea     edx, [rcx+4]
0x180041486  mov     eax, dword ptr [rbp+960h+var_950+4]
0x180041489  mov     [rbp+960h+pretrievecolumn.columnidNextTagged], eax
0x18004148c  mov     eax, dword ptr [rbp+960h+var_950+0Ch]
0x18004148f  mov     dword ptr [rbp+960h+pretrievecolumn+2Ch], eax
0x180041492  mov     eax, [rbp+960h+var_9AC]
0x180041495  mov     [rbp+960h+var_8F0], eax
0x180041498  movups  [rbp+960h+var_960], xmm2
0x18004149c  mov     [rbp+960h+pretrievecolumn.cbData], ecx
0x18004149f  movsd   xmm0, qword ptr [rbp+960h+var_960+4]
0x1800414a4  psrldq  xmm2, 8
0x1800414a9  movd    [rbp+960h+pretrievecolumn.err], xmm2
0x1800414ae  xorps   xmm2, xmm2
0x1800414b1  movups  [rbp+960h+var_970], xmm2
0x1800414b5  mov     eax, dword ptr [rbp+960h+var_970+4]
0x1800414b8  mov     [rbp+960h+var_8EC], eax
0x1800414bb  lea     rax, [rbp+960h+var_998]
0x1800414bf  mov     [rbp+960h+var_8E8], rax
0x1800414c3  mov     eax, [rbp+960h+var_9A8]
0x1800414c6  mov     [rbp+960h+var_8C0], eax
0x1800414cc  movups  [rbp+960h+var_960], xmm2
0x1800414d0  mov     [rbp+960h+var_8E0], edx
0x1800414d6  movups  [rbp+960h+var_950], xmm2
0x1800414da  mov     [rbp+960h+var_8D0], r15d
0x1800414e1  psrldq  xmm1, 0Ch
0x1800414e6  psrldq  xmm2, 0Ch
0x1800414eb  movsd   qword ptr [rbp+960h+pretrievecolumn.cbActual], xmm0
0x1800414f0  movsd   xmm0, qword ptr [rbp+960h+var_960+4]
0x1800414f5  movd    [rbp+960h+pretrievecolumn.ibLongValue], xmm1
0x1800414fa  xorps   xmm1, xmm1
0x1800414fd  movd    [rbp+960h+var_8C4], xmm2
0x180041505  xorps   xmm2, xmm2
0x180041508  movups  [rbp+960h+var_970], xmm2
0x18004150c  mov     eax, dword ptr [rbp+960h+var_970+4]
0x18004150f  mov     [rbp+960h+var_8BC], eax
0x180041515  lea     rax, [rbp+960h+var_860]
0x18004151c  mov     [rbp+960h+var_8B8], rax
0x180041523  movups  [rbp+960h+var_960], xmm2
0x180041527  mov     [rbp+960h+var_8B0], 802h
0x180041531  movsd   [rbp+960h+var_8DC], xmm0
0x180041539  movsd   xmm0, qword ptr [rbp+960h+var_950+4]
0x18004153e  movups  [rbp+960h+var_950], xmm2
0x180041542  mov     eax, dword ptr [rbp+960h+var_950+4]
0x180041545  mov     [rbp+960h+var_89C], eax
0x18004154b  mov     eax, dword ptr [rbp+960h+var_950+0Ch]
0x18004154e  mov     [rbp+960h+var_894], eax
0x180041554  mov     eax, [rbp+960h+var_9A4]
0x180041557  psrldq  xmm1, 0Ch
0x18004155c  psrldq  xmm2, 8
0x180041561  mov     [rbp+960h+var_890], eax
0x180041567  movd    [rbp+960h+var_8D4], xmm1
0x18004156f  xorps   xmm1, xmm1
0x180041572  movsd   [rbp+960h+var_8CC], xmm0
0x18004157a  movsd   xmm0, qword ptr [rbp+960h+var_960+4]
0x18004157f  movd    [rbp+960h+var_898], xmm2
0x180041587  xorps   xmm2, xmm2
0x18004158a  movups  [rbp+960h+var_970], xmm2
0x18004158e  mov     eax, dword ptr [rbp+960h+var_970+4]
0x180041591  mov     [rbp+960h+var_88C], eax
0x180041597  lea     rax, [rbp+960h+var_9A0]
0x18004159b  psrldq  xmm1, 0Ch
0x1800415a0  movsd   [rbp+960h+var_8AC], xmm0
0x1800415a8  movups  [rbp+960h+var_960], xmm2
0x1800415ac  mov     [rbp+960h+var_888], rax
0x1800415b3  movsd   xmm0, qword ptr [rbp+960h+var_960+4]
0x1800415b8  movd    [rbp+960h+var_8A4], xmm1
0x1800415c0  mov     [rbp+960h+var_8A0], r15d
0x1800415c7  movups  [rbp+960h+var_950], xmm2
0x1800415cb  mov     [rbp+960h+var_880], edx
0x1800415d1  mov     eax, dword ptr [rbp+960h+var_950+4]
0x1800415d4  lea     r8, [rbp+960h+pretrievecolumn]; pretrievecolumn
0x1800415d8  mov     rdx, [rsp+0A60h+tableid]; tableid
0x1800415dd  xorps   xmm1, xmm1
0x1800415e0  psrldq  xmm1, 0Ch
0x1800415e5  mov     r9d, ecx; cretrievecolumn
0x1800415e8  mov     rcx, [rsp+0A60h+sesid]; sesid
0x1800415ed  mov     [rbp+960h+var_86C], eax
0x1800415f3  mov     eax, dword ptr [rbp+960h+var_950+0Ch]
  ... truncated ...
```
