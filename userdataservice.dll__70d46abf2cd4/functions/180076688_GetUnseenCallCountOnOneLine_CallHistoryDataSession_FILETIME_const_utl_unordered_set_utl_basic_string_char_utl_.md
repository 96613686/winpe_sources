# GetUnseenCallCountOnOneLine(CallHistoryDataSession *,_FILETIME const &,utl::unordered_set<utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>,tlx::istring_hash_ascii,tlx::istring_equal_to_ascii,utl::allocator<utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>>> const *,ushort const *,int,ulong *)

- ea: `0x180076688`
- end: `0x180076fd6`
- name: `?GetUnseenCallCountOnOneLine@@YAJPEAVCallHistoryDataSession@@AEBU_FILETIME@@PEBV?$unordered_set@V?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@Uistring_hash_ascii@tlx@@Uistring_equal_to_ascii@4@V?$allocator@V?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@@2@@utl@@PEBGHPEAK@Z`
- size: `2382`
- prototype: ``
- caller_count: `2`
- callee_count: `26`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1800e0040`
- `0x1800e035c`

## callees

- `0x180008ee8`
- `0x180008f0c`
- `0x180018c20`
- `0x18001b340`
- `0x18003bf04`
- `0x18005d03c`
- `0x18005e048`
- `0x18005e160`
- `0x180066860`
- `0x1800672f8`
- `0x180068458`
- `0x180068698`
- `0x18006a8ac`
- `0x180075f98`
- `0x180076664`
- `0x180076688`
- `0x1800781d8`
- `0x1800a4e74`
- `0x1800da008`
- `0x1800da038`
- `0x1800db6b0`
- `0x1800db8c8`
- `0x1800decf0`
- `0x1800e1428`
- `0x1800e2f58`
- `0x18012c7b0`

## import_xrefs

- `ESENT!JetIndexRecordCount` at `0x180076afa`
- `ESENT!JetIndexRecordCount` at `0x180076afa`
- `ESENT!JetOpenTableA` at `0x180076812`
- `ESENT!JetOpenTableA` at `0x180076812`
- `ESENT!JetMakeKey` at `0x1800768d0`
- `ESENT!JetMakeKey` at `0x180076949`
- `ESENT!JetMakeKey` at `0x180076980`
- `ESENT!JetMakeKey` at `0x1800769a6`
- `ESENT!JetMakeKey` at `0x180076a59`
- `ESENT!JetMakeKey` at `0x1800768d0`
- `ESENT!JetMakeKey` at `0x180076949`
- `ESENT!JetMakeKey` at `0x180076980`
- `ESENT!JetMakeKey` at `0x1800769a6`
- `ESENT!JetMakeKey` at `0x180076a59`
- `ESENT!JetSetCurrentIndexA` at `0x18007689b`
- `ESENT!JetSetCurrentIndexA` at `0x180076a18`
- `ESENT!JetSetCurrentIndexA` at `0x18007689b`
- `ESENT!JetSetCurrentIndexA` at `0x180076a18`
- `ESENT!JetRetrieveColumns` at `0x180076cfa`
- `ESENT!JetRetrieveColumns` at `0x180076cfa`

## string_xrefs

- `0x180076b4c`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\datasession.cpp`
- `0x180076b82`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\datasession.cpp`
- `0x180076bba`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\datasession.cpp`
- `0x180076dfb`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\datasession.cpp`
- `0x180076743`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\callhistory.cpp`
- `0x1800767bc`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\callhistory.cpp`
- `0x18007682d`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\callhistory.cpp`
- `0x180076f6e`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\callhistory.cpp`

## pseudocode

```c
__int64 __fastcall GetUnseenCallCountOnOneLine(
        __int64 a1,
        void *a2,
        __int64 a3,
        _WORD *a4,
        int a5,
        unsigned int *pcrec)
{
  unsigned int v9; // r12d
  unsigned int HresultFromJetError; // ebx
  __int64 v11; // r9
  __int64 v12; // rcx
  __int64 v13; // rdx
  int AppPackageFamilyName; // eax
  __int64 v15; // r9
  int v16; // eax
  JET_SESID v17; // rcx
  JET_DBID v18; // edx
  JET_ERR v19; // eax
  int v20; // eax
  __int64 v21; // r9
  __int64 v22; // rdx
  unsigned int v23; // r15d
  unsigned __int64 v24; // rcx
  JET_ERR v25; // eax
  JET_ERR Key; // eax
  unsigned int v27; // edx
  int v28; // eax
  void *v29; // rbx
  unsigned int v30; // r9d
  JET_ERR v31; // eax
  JET_ERR v32; // eax
  JET_ERR v33; // eax
  int v34; // eax
  JET_ERR v35; // eax
  JET_ERR v36; // eax
  int v37; // eax
  int v38; // eax
  JET_ERR v39; // eax
  DatabaseVolumeSession *v40; // rcx
  __int64 v41; // rcx
  DatabaseVolumeSession *v42; // rcx
  __int64 v43; // rcx
  unsigned int v44; // r13d
  DatabaseVolumeSession *v45; // rcx
  __int64 v46; // rcx
  JET_COLUMNID v47; // esi
  JET_ERR v48; // eax
  __int64 v49; // r9
  bool v50; // zf
  DatabaseVolumeSession *v51; // rcx
  __int64 v52; // rcx
  unsigned int Column; // r15d
  int v54; // eax
  __int64 v55; // rcx
  __int64 v56; // rdi
  __int64 v57; // rax
  __int64 v58; // rcx
  unsigned __int64 v59; // rsi
  __int64 v60; // rax
  _QWORD *v61; // rbx
  _QWORD *v62; // rdi
  int v63; // eax
  __int64 v65; // r9
  __int64 v66; // rcx
  __int64 v67; // rdx
  unsigned int v68; // [rsp+40h] [rbp-C0h] BYREF
  JET_SESID sesid; // [rsp+48h] [rbp-B8h] BYREF
  JET_TABLEID tableid; // [rsp+50h] [rbp-B0h] BYREF
  int v71; // [rsp+58h] [rbp-A8h] BYREF
  int v72; // [rsp+5Ch] [rbp-A4h] BYREF
  _QWORD v73[2]; // [rsp+60h] [rbp-A0h] BYREF
  void *pvData; // [rsp+70h] [rbp-90h] BYREF
  __int64 v75; // [rsp+78h] [rbp-88h] BYREF
  _OWORD v76[3]; // [rsp+80h] [rbp-80h] BYREF
  __int64 v77; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v78; // [rsp+B8h] [rbp-48h]
  JET_RETRIEVECOLUMN pretrievecolumn; // [rsp+D0h] [rbp-30h] BYREF
  int v80; // [rsp+100h] [rbp+0h]
  int v81; // [rsp+104h] [rbp+4h]
  _WORD *v82; // [rsp+108h] [rbp+8h]
  int v83; // [rsp+110h] [rbp+10h]
  __int64 v84; // [rsp+114h] [rbp+14h]
  unsigned int ibLongValue; // [rsp+11Ch] [rbp+1Ch]
  int v86; // [rsp+120h] [rbp+20h]
  int v87; // [rsp+124h] [rbp+24h]
  JET_ERR err; // [rsp+128h] [rbp+28h]
  int v89; // [rsp+12Ch] [rbp+2Ch]
  unsigned int v90; // [rsp+130h] [rbp+30h]
  int v91; // [rsp+134h] [rbp+34h]
  int *v92; // [rsp+138h] [rbp+38h]
  int v93; // [rsp+140h] [rbp+40h]
  __int64 v94; // [rsp+144h] [rbp+44h]
  unsigned int v95; // [rsp+14Ch] [rbp+4Ch]
  int v96; // [rsp+150h] [rbp+50h]
  int v97; // [rsp+154h] [rbp+54h]
  JET_ERR v98; // [rsp+158h] [rbp+58h]
  int v99; // [rsp+15Ch] [rbp+5Ch]
  _BYTE Src[256]; // [rsp+160h] [rbp+60h] BYREF
  _WORD v101[1032]; // [rsp+260h] [rbp+160h] BYREF

  pvData = a2;
  v75 = 0;
  *pcrec = 0;
  ATL::CComPtr<ServiceDataSession>::operator=(&v75, a1);
  v9 = (unsigned int)CallHistoryOperationContext::ValidateCallerSecurity(&v75, 2, 0, 1) >> 31;
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(&v77);
  if ( v9 )
  {
    if ( a3 )
    {
      HresultFromJetError = -2147024809;
      v11 = 1998;
      v12 = 2147942487LL;
      v13 = 0;
LABEL_6:
      Log_HREvent(
        v12,
        v13,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\callhistory.cpp",
        v11);
      goto LABEL_114;
    }
    AppPackageFamilyName = ServiceDataSession::GetAppPackageFamilyName(a1, &v77);
    HresultFromJetError = AppPackageFamilyName;
    if ( AppPackageFamilyName < 0 )
    {
      v11 = 2000;
      v13 = 1;
      v12 = (unsigned int)AppPackageFamilyName;
      goto LABEL_6;
    }
    if ( !a4 )
      goto LABEL_11;
    v15 = -1;
    do
      ++v15;
    while ( a4[v15] );
    v9 = 0;
    if ( (unsigned int)utl::_StringTraits<utl::char_traits<unsigned short>>::compare(v77, (v78 - v77) >> 1, a4, v15) )
LABEL_11:
      v9 = 1;
  }
  v73[0] = *(_QWORD *)(a1 + 2048);
  v73[1] = 0;
  v16 = auto_JET_TRANSACTION::Begin((auto_JET_TRANSACTION *)v73, 1u);
  if ( v16 < 0 )
  {
    HresultFromJetError = MakeHresultFromJetError(v16);
    Log_HREvent(
      HresultFromJetError,
      0,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\callhistory.cpp",
      2007);
    goto LABEL_113;
  }
  v17 = *(_QWORD *)(a1 + 2048);
  v18 = *(_DWORD *)(a1 + 2056);
  v72 = 0;
  sesid = v17;
  tableid = -1;
  v19 = JetOpenTableA(v17, v18, "CallHistory", 0, 0, 4u, &tableid);
  if ( v19 < 0 )
  {
    v20 = MakeHresultFromJetError(v19);
    v21 = 2022;
    goto LABEL_16;
  }
  v68 = 0;
  v23 = 0;
  if ( a4 )
  {
    v24 = -1;
    do
      ++v24;
    while ( a4[v24] );
    v20 = ULongLongToULong(v24, &v68);
    HresultFromJetError = v20;
    if ( v20 < 0 )
    {
      v21 = 2027;
LABEL_23:
      v22 = 1;
      goto LABEL_17;
    }
    v23 = v68;
    if ( v68 )
    {
      v25 = JetSetCurrentIndexA(sesid, tableid, "UnseenByLine");
      if ( v25 < 0 )
      {
        v20 = MakeHresultFromJetError(v25);
        v21 = 2032;
        goto LABEL_16;
      }
      Key = JetMakeKey(sesid, tableid, a4, 2 * v23, 0x101u);
      if ( Key < 0 )
      {
        v20 = MakeHresultFromJetError(Key);
        v21 = 2033;
        goto LABEL_16;
      }
      v68 = 0;
      v28 = auto_JET_TABLEID::MaybeSeek((auto_JET_TABLEID *)&sesid, v27, (enum TableSeekResult *)&v68);
      if ( v28 < 0 )
      {
        v20 = MakeHresultFromJetError(v28);
        v21 = 2036;
        goto LABEL_16;
      }
      if ( v68 - 2 > 1 )
        goto LABEL_52;
      v29 = pvData;
      v30 = 2 * v23;
      if ( *(_QWORD *)pvData )
      {
        v31 = JetMakeKey(sesid, tableid, a4, v30, 1u);
        if ( v31 < 0 )
        {
          v20 = MakeHresultFromJetError(v31);
          v21 = 2042;
          goto LABEL_16;
        }
        v32 = JetMakeKey(sesid, tableid, v29, 8u, 0x200u);
        if ( v32 < 0 )
        {
          v20 = MakeHresultFromJetError(v32);
          v21 = 2043;
          goto LABEL_16;
        }
      }
      else
      {
        v33 = JetMakeKey(sesid, tableid, a4, v30, 0x201u);
        if ( v33 < 0 )
        {
          v20 = MakeHresultFromJetError(v33);
          v21 = 2047;
          goto LABEL_16;
        }
      }
      v34 = auto_JET_TABLEID::MaybeSetRange((auto_JET_TABLEID *)&sesid, 3u, &v72);
      if ( v34 < 0 )
      {
        v20 = MakeHresultFromJetError(v34);
        v21 = 2049;
        goto LABEL_16;
      }
      goto LABEL_51;
    }
    if ( !a5 )
    {
LABEL_52:
      *pcrec = 0;
LABEL_106:
      auto_JET_TABLEID::~auto_JET_TABLEID((auto_JET_TABLEID *)&sesid);
      auto_JET_TRANSACTION::~auto_JET_TRANSACTION((auto_JET_TRANSACTION *)v73);
      utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(&v77);
      ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(&v75);
      return 0;
    }
  }
  v35 = JetSetCurrentIndexA(sesid, tableid, "Unseen");
  if ( v35 < 0 )
  {
    v20 = MakeHresultFromJetError(v35);
    v21 = 2054;
    goto LABEL_16;
  }
  if ( *(_QWORD *)pvData )
  {
    v36 = JetMakeKey(sesid, tableid, pvData, 8u, 1u);
    if ( v36 < 0 )
    {
      v20 = MakeHresultFromJetError(v36);
      v21 = 2058;
      goto LABEL_16;
    }
    v37 = auto_JET_TABLEID::MaybeSetRange((auto_JET_TABLEID *)&sesid, 3u, &v72);
    if ( v37 < 0 )
    {
      v20 = MakeHresultFromJetError(v37);
      v21 = 2059;
      goto LABEL_16;
    }
  }
  else
  {
    v38 = MoveFirst((const struct auto_JET_TABLEID *)&sesid, &v72);
    if ( v38 < 0 )
    {
      v20 = MakeHresultFromJetError(v38);
      v21 = 2063;
      goto LABEL_16;
    }
  }
LABEL_51:
  if ( !v72 )
    goto LABEL_52;
  if ( a3 )
  {
    v51 = *(DatabaseVolumeSession **)(a1 + 2040);
    v71 = 0;
    Column = DatabaseVolumeSession::FindColumnEx(v51, (const struct ColumnDefinition *)&off_180130D80, &v71);
    if ( !v71 )
      Log_AssertionEvent_2(
        v52,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\datasession.cpp",
        203);
    utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::basic_string<char,utl::char_traits<char>,utl::allocator<char>>(v76);
    while ( 1 )
    {
      LODWORD(pvData) = 0;
      v71 = 0;
      v54 = auto_JET_TABLEID::GetColumn((auto_JET_TABLEID *)&sesid, Column, Src, 0x100u, (unsigned int *)&pvData, &v71);
      if ( v54 < 0 )
        break;
      if ( v71 )
      {
        if ( !(unsigned __int8)utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::assign(
                                 v76,
                                 Src,
                                 (unsigned int)pvData) )
        {
          HresultFromJetError = -2147024882;
          v65 = 2177;
          v66 = 2147942414LL;
          v67 = 0;
          goto LABEL_111;
        }
        v56 = *(_QWORD *)(a3 + 16);
        if ( v56 )
        {
          v57 = tlx::string_hash_base<tlx::ascii_toupper_transform>::operator()<utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>,char>(
                  v55,
                  v76);
          LOBYTE(v58) = *(_BYTE *)(a3 + 32);
          v59 = v57;
          v60 = 2 * (v57 & ((8LL << v58) - 1));
          v61 = *(_QWORD **)(v56 + 8 * v60);
          if ( v61 )
          {
            v62 = **(_QWORD ***)(v56 + 8 * v60 + 8);
            while ( 1 )
            {
              if ( v61 == v62 )
                goto LABEL_103;
              if ( v61[2] >= v59 )
              {
                if ( v61[2] > v59 )
                  goto LABEL_103;
                if ( (unsigned __int8)tlx::string_equal_to_base<tlx::ascii_toupper_transform>::operator()<utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>,utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>,char,char,0>(
                                        v58,
                                        v76,
                                        v61 + 3) )
                  break;
              }
              v61 = (_QWORD *)*v61;
            }
            if ( v61 != (_QWORD *)a3 )
              ++*pcrec;
          }
        }
      }
LABEL_103:
      v71 = 0;
      v63 = Move(sesid, tableid, 1, &v71);
      HresultFromJetError = v63;
      if ( v63 < 0 )
      {
        v65 = 2188;
        v67 = 1;
        goto LABEL_110;
      }
      if ( !v71 )
      {
        utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v76);
        goto LABEL_106;
      }
    }
    v63 = MakeHresultFromJetError(v54);
    HresultFromJetError = v63;
    v65 = 2173;
    v67 = 0;
LABEL_110:
    v66 = (unsigned int)v63;
LABEL_111:
    Log_HREvent(
      v66,
      v67,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\callhistory.cpp",
      v65);
    utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v76);
    goto LABEL_112;
  }
  if ( !v9 && (!a4 || v23) )
  {
    v39 = JetIndexRecordCount(sesid, tableid, pcrec, 0);
    if ( v39 < 0 )
    {
      v20 = MakeHresultFromJetError(v39);
      v21 = 2150;
      goto LABEL_16;
    }
    goto LABEL_106;
  }
  v40 = *(DatabaseVolumeSession **)(a1 + 2040);
  v68 = 0;
  LODWORD(pvData) = DatabaseVolumeSession::FindColumnEx(
                      v40,
                      (const struct ColumnDefinition *)&off_180130D60,
                      (int *)&v68);
  if ( !v68 )
    Log_AssertionEvent_2(
      v41,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\datasession.cpp",
      203);
  v42 = *(DatabaseVolumeSession **)(a1 + 2040);
  v68 = 0;
  v44 = DatabaseVolumeSession::FindColumnEx(v42, (const struct ColumnDefinition *)&off_180130EE0, (int *)&v68);
  if ( !v68 )
    Log_AssertionEvent_2(
      v43,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\datasession.cpp",
      203);
  v45 = *(DatabaseVolumeSession **)(a1 + 2040);
  v68 = 0;
  v47 = DatabaseVolumeSession::FindColumnEx(v45, (const struct ColumnDefinition *)&off_180130EC0, (int *)&v68);
  if ( !v68 )
    Log_AssertionEvent_2(
      v46,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\datasession.cpp",
      203);
  while ( 1 )
  {
    v72 = 0;
    v68 = 0;
    *(&pretrievecolumn.columnid + 1) = 0;
    pretrievecolumn.cbData = 4;
    pretrievecolumn.pvData = &v68;
    pretrievecolumn.columnidNextTagged = 0;
    *(&pretrievecolumn.err + 1) = 0;
    v80 = (int)pvData;
    pretrievecolumn.err = _mm_cvtsi128_si32(_mm_srli_si128((__m128i)0LL, 8));
    v93 = 4;
    v81 = 0;
    v82 = v101;
    v87 = 0;
    pretrievecolumn.ibLongValue = _mm_cvtsi128_si32(_mm_srli_si128((__m128i)0LL, 12));
    v89 = 0;
    err = pretrievecolumn.err;
    pretrievecolumn.columnid = v47;
    memset(v76, 0, sizeof(v76));
    v91 = 0;
    *(_QWORD *)&pretrievecolumn.cbActual = 0;
    ibLongValue = pretrievecolumn.ibLongValue;
    v92 = &v72;
    v97 = 0;
    v84 = 0;
    v99 = 0;
    pretrievecolumn.itagSequence = 1;
    v83 = 1025;
    v86 = 1;
    v90 = v44;
    v94 = 0;
    v95 = pretrievecolumn.ibLongValue;
    v96 = 1;
    v98 = pretrievecolumn.err;
    v48 = JetRetrieveColumns(sesid, tableid, &pretrievecolumn, 3u);
    if ( v48 < 0 )
      break;
    if ( v9 )
    {
      if ( pretrievecolumn.err || v68 != 1 )
        goto LABEL_81;
      if ( !err && !v98 && v72 == 1 )
      {
        v49 = -1;
        do
          ++v49;
        while ( v101[v49] );
        v50 = (unsigned int)utl::_StringTraits<utl::char_traits<unsigned short>>::compare(
                              v77,
                              (v78 - v77) >> 1,
                              v101,
                              v49) == 0;
LABEL_80:
        if ( !v50 )
          goto LABEL_82;
LABEL_81:
        ++*pcrec;
      }
    }
    else if ( !v98 && v72 == 1 && a5 && a4 )
    {
      v50 = v23 == 0;
      goto LABEL_80;
    }
LABEL_82:
    v71 = 0;
    v20 = Move(sesid, tableid, 1, &v71);
    HresultFromJetError = v20;
    if ( v20 < 0 )
    {
      v21 = 2140;
      goto LABEL_23;
    }
    if ( !v71 )
      goto LABEL_106;
  }
  v20 = MakeHresultFromJetError(v48);
  v21 = 2097;
LABEL_16:
  HresultFromJetError = v20;
  v22 = 0;
LABEL_17:
  Log_HREvent(
    (unsigned int)v20,
    v22,
    "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\callhistory.cpp",
    v21);
LABEL_112:
  auto_JET_TABLEID::~auto_JET_TABLEID((auto_JET_TABLEID *)&sesid);
LABEL_113:
  auto_JET_TRANSACTION::~auto_JET_TRANSACTION((auto_JET_TRANSACTION *)v73);
LABEL_114:
  utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(&v77);
  ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(&v75);
  return HresultFromJetError;
}

```

## disassembly

```asm
0x180076688  mov     [rsp-8+arg_10], rbx
0x18007668d  push    rbp
0x18007668e  push    rsi
0x18007668f  push    rdi
0x180076690  push    r12
0x180076692  push    r13
0x180076694  push    r14
0x180076696  push    r15
0x180076698  lea     rbp, [rsp-980h]
0x1800766a0  sub     rsp, 0A80h
0x1800766a7  mov     rax, cs:__security_cookie
0x1800766ae  xor     rax, rsp
0x1800766b1  mov     [rbp+9B0h+var_40], rax
0x1800766b8  mov     r14, [rbp+9B0h+pcrec]
0x1800766bf  mov     rsi, rcx
0x1800766c2  mov     [rsp+0AB0h+pvData], rdx
0x1800766c7  xor     ebx, ebx
0x1800766c9  mov     rdx, rcx
0x1800766cc  mov     [rsp+0AB0h+var_A38], rbx
0x1800766d1  lea     rcx, [rsp+0AB0h+var_A38]
0x1800766d6  mov     rdi, r9
0x1800766d9  mov     [r14], ebx
0x1800766dc  mov     r13, r8
0x1800766df  call    ??4?$CComPtr@VServiceDataSession@@@ATL@@QEAAPEAVServiceDataSession@@PEAV2@@Z; ATL::CComPtr<ServiceDataSession>::operator=(ServiceDataSession *)
0x1800766e4  lea     r15d, [rbx+1]
0x1800766e8  xor     r8d, r8d
0x1800766eb  mov     r9d, r15d
0x1800766ee  lea     edx, [rbx+2]
0x1800766f1  lea     rcx, [rsp+0AB0h+var_A38]
0x1800766f6  call    ?ValidateCallerSecurity@CallHistoryOperationContext@@QEAAJW4UdmAccessLevel@@KH@Z; CallHistoryOperationContext::ValidateCallerSecurity(UdmAccessLevel,ulong,int)
0x1800766fb  mov     r12d, eax
0x1800766fe  lea     rcx, [rbp+9B0h+var_A00]; void *
0x180076702  shr     r12d, 1Fh
0x180076706  call    ??0?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@XZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(void)
0x18007670b  test    r12d, r12d
0x18007670e  jz      short loc_180076789
0x180076710  test    r13, r13
0x180076713  jz      short loc_180076726
0x180076715  mov     ebx, 80070057h
0x18007671a  mov     r9d, 7CEh
0x180076720  mov     ecx, ebx
0x180076722  xor     edx, edx
0x180076724  jmp     short loc_180076743
0x180076726  lea     rdx, [rbp+9B0h+var_A00]
0x18007672a  mov     rcx, rsi
0x18007672d  call    ?GetAppPackageFamilyName@ServiceDataSession@@QEAAJPEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@Z; ServiceDataSession::GetAppPackageFamilyName(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> *)
0x180076732  mov     ebx, eax
0x180076734  test    eax, eax
0x180076736  jns     short loc_180076754
0x180076738  mov     r9d, 7D0h
0x18007673e  mov     edx, r15d
0x180076741  mov     ecx, eax
0x180076743  lea     r8, aOnecoreuapBase_43; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18007674a  call    Log_HREvent
0x18007674f  jmp     loc_180076F97
0x180076754  xor     ebx, ebx
0x180076756  test    rdi, rdi
0x180076759  jz      short loc_180076786
0x18007675b  or      r9, 0FFFFFFFFFFFFFFFFh
0x18007675f  inc     r9
0x180076762  cmp     [rdi+r9*2], bx
0x180076767  jnz     short loc_18007675F
0x180076769  mov     rcx, [rbp+9B0h+var_A00]
0x18007676d  mov     r8, rdi
0x180076770  mov     rdx, [rbp+9B0h+var_9F8]
0x180076774  sub     rdx, rcx
0x180076777  sar     rdx, 1
0x18007677a  call    ?compare@?$_StringTraits@U?$char_traits@G@utl@@@utl@@SAHPEBG_K01@Z; utl::_StringTraits<utl::char_traits<ushort>>::compare(ushort const *,unsigned __int64,ushort const *,unsigned __int64)
0x18007677f  mov     r12d, ebx
0x180076782  test    eax, eax
0x180076784  jz      short loc_180076789
0x180076786  mov     r12d, r15d
0x180076789  mov     rax, [rsi+800h]
0x180076790  lea     rcx, [rsp+0AB0h+var_A50]; this
0x180076795  mov     edx, r15d; unsigned int
0x180076798  mov     [rsp+0AB0h+var_A50], rax
0x18007679d  mov     [rsp+0AB0h+var_A48], 0
0x1800767a6  call    ?Begin@auto_JET_TRANSACTION@@QEAAJK@Z; auto_JET_TRANSACTION::Begin(ulong)
0x1800767ab  test    eax, eax
0x1800767ad  jns     short loc_1800767D3
0x1800767af  mov     ecx, eax; int
0x1800767b1  call    ?MakeHresultFromJetError@@YAJJ@Z; MakeHresultFromJetError(long)
0x1800767b6  mov     r9d, 7D7h
0x1800767bc  lea     r8, aOnecoreuapBase_43; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800767c3  xor     edx, edx
0x1800767c5  mov     ecx, eax
0x1800767c7  mov     ebx, eax
0x1800767c9  call    Log_HREvent
0x1800767ce  jmp     loc_180076F8D
0x1800767d3  mov     rcx, [rsi+800h]; sesid
0x1800767da  lea     rax, [rsp+0AB0h+tableid]
0x1800767df  mov     edx, [rsi+808h]; dbid
0x1800767e5  lea     r8, ?UdmTableName_CallHistory@@3QBDB; "CallHistory"
0x1800767ec  mov     [rsp+0AB0h+ptableid], rax; ptableid
0x1800767f1  xor     r9d, r9d; pvParameters
0x1800767f4  mov     [rsp+0AB0h+grbit], 4; grbit
0x1800767fc  mov     [rsp+0AB0h+cbParameters], ebx; cbParameters
0x180076800  mov     [rsp+0AB0h+var_A54], ebx
0x180076804  mov     [rsp+0AB0h+sesid], rcx
0x180076809  mov     [rsp+0AB0h+tableid], 0FFFFFFFFFFFFFFFFh
0x180076812  call    cs:__imp_JetOpenTableA
0x180076818  test    eax, eax
0x18007681a  jns     short loc_180076840
0x18007681c  mov     ecx, eax; int
0x18007681e  call    ?MakeHresultFromJetError@@YAJJ@Z; MakeHresultFromJetError(long)
0x180076823  mov     r9d, 7E6h
0x180076829  mov     ebx, eax
0x18007682b  xor     edx, edx
0x18007682d  lea     r8, aOnecoreuapBase_43; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180076834  mov     ecx, eax
0x180076836  call    Log_HREvent
0x18007683b  jmp     loc_180076F83
0x180076840  mov     [rsp+0AB0h+var_A70], ebx
0x180076844  mov     r15d, ebx
0x180076847  test    rdi, rdi
0x18007684a  jz      loc_180076A07
0x180076850  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180076854  inc     rcx; unsigned __int64
0x180076857  cmp     [rdi+rcx*2], bx
0x18007685b  jnz     short loc_180076854
0x18007685d  lea     rdx, [rsp+0AB0h+var_A70]; unsigned int *
0x180076862  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x180076867  mov     ebx, eax
0x180076869  test    eax, eax
0x18007686b  jns     short loc_18007687A
0x18007686d  mov     r9d, 7EBh
0x180076873  mov     edx, 1
0x180076878  jmp     short loc_18007682D
0x18007687a  mov     r15d, [rsp+0AB0h+var_A70]
0x18007687f  xor     ebx, ebx
0x180076881  test    r15d, r15d
0x180076884  jz      loc_1800769F2
0x18007688a  mov     rdx, [rsp+0AB0h+tableid]; tableid
0x18007688f  lea     r8, ?UdmIdxName_CallHistory_UnseenByLine@@3QBDB; "UnseenByLine"
0x180076896  mov     rcx, [rsp+0AB0h+sesid]; sesid
0x18007689b  call    cs:__imp_JetSetCurrentIndexA
0x1800768a1  test    eax, eax
0x1800768a3  jns     short loc_1800768B7
0x1800768a5  mov     ecx, eax; int
0x1800768a7  call    ?MakeHresultFromJetError@@YAJJ@Z; MakeHresultFromJetError(long)
0x1800768ac  mov     r9d, 7F0h
0x1800768b2  jmp     loc_180076829
0x1800768b7  mov     rdx, [rsp+0AB0h+tableid]; tableid
0x1800768bc  lea     r9d, [r15+r15]; cbData
0x1800768c0  mov     rcx, [rsp+0AB0h+sesid]; sesid
0x1800768c5  mov     r8, rdi; pvData
0x1800768c8  mov     [rsp+0AB0h+cbParameters], 101h; grbit
0x1800768d0  call    cs:__imp_JetMakeKey
0x1800768d6  test    eax, eax
0x1800768d8  jns     short loc_1800768EC
0x1800768da  mov     ecx, eax; int
0x1800768dc  call    ?MakeHresultFromJetError@@YAJJ@Z; MakeHresultFromJetError(long)
0x1800768e1  mov     r9d, 7F1h
0x1800768e7  jmp     loc_180076829
0x1800768ec  lea     r8, [rsp+0AB0h+var_A70]; enum TableSeekResult *
0x1800768f1  mov     [rsp+0AB0h+var_A70], ebx
0x1800768f5  lea     rcx, [rsp+0AB0h+sesid]; this
0x1800768fa  call    ?MaybeSeek@auto_JET_TABLEID@@QEAAJKPEAW4TableSeekResult@@@Z; auto_JET_TABLEID::MaybeSeek(ulong,TableSeekResult *)
0x1800768ff  test    eax, eax
0x180076901  jns     short loc_180076915
0x180076903  mov     ecx, eax; int
0x180076905  call    ?MakeHresultFromJetError@@YAJJ@Z; MakeHresultFromJetError(long)
0x18007690a  mov     r9d, 7F4h
0x180076910  jmp     loc_180076829
0x180076915  mov     eax, [rsp+0AB0h+var_A70]
0x180076919  add     eax, 0FFFFFFFEh
0x18007691c  cmp     eax, 1
0x18007691f  ja      loc_180076ACA
0x180076925  mov     rbx, [rsp+0AB0h+pvData]
0x18007692a  lea     r9d, [r15+r15]; cbData
0x18007692e  mov     rdx, [rsp+0AB0h+tableid]; tableid
0x180076933  mov     r8, rdi; pvData
0x180076936  mov     rcx, [rsp+0AB0h+sesid]; sesid
0x18007693b  cmp     qword ptr [rbx], 0
0x18007693f  jz      short loc_18007699E
0x180076941  mov     [rsp+0AB0h+cbParameters], 1; grbit
0x180076949  call    cs:__imp_JetMakeKey
0x18007694f  test    eax, eax
0x180076951  jns     short loc_180076965
0x180076953  mov     ecx, eax; int
0x180076955  call    ?MakeHresultFromJetError@@YAJJ@Z; MakeHresultFromJetError(long)
0x18007695a  mov     r9d, 7FAh
0x180076960  jmp     loc_180076829
0x180076965  mov     rdx, [rsp+0AB0h+tableid]; tableid
0x18007696a  mov     r9d, 8; cbData
0x180076970  mov     rcx, [rsp+0AB0h+sesid]; sesid
0x180076975  mov     r8, rbx; pvData
0x180076978  mov     [rsp+0AB0h+cbParameters], 200h; grbit
0x180076980  call    cs:__imp_JetMakeKey
0x180076986  xor     ebx, ebx
0x180076988  test    eax, eax
0x18007698a  jns     short loc_1800769C4
0x18007698c  mov     ecx, eax; int
0x18007698e  call    ?MakeHresultFromJetError@@YAJJ@Z; MakeHresultFromJetError(long)
0x180076993  mov     r9d, 7FBh
0x180076999  jmp     loc_180076829
0x18007699e  mov     [rsp+0AB0h+cbParameters], 201h; grbit
0x1800769a6  call    cs:__imp_JetMakeKey
0x1800769ac  xor     ebx, ebx
0x1800769ae  test    eax, eax
0x1800769b0  jns     short loc_1800769C4
0x1800769b2  mov     ecx, eax; int
0x1800769b4  call    ?MakeHresultFromJetError@@YAJJ@Z; MakeHresultFromJetError(long)
0x1800769b9  mov     r9d, 7FFh
0x1800769bf  jmp     loc_180076829
0x1800769c4  lea     r8, [rsp+0AB0h+var_A54]; int *
0x1800769c9  mov     edx, 3; unsigned int
0x1800769ce  lea     rcx, [rsp+0AB0h+sesid]; this
0x1800769d3  call    ?MaybeSetRange@auto_JET_TABLEID@@QEAAJKPEAH@Z; auto_JET_TABLEID::MaybeSetRange(ulong,int *)
0x1800769d8  test    eax, eax
0x1800769da  jns     loc_180076AC4
0x1800769e0  mov     ecx, eax; int
0x1800769e2  call    ?MakeHresultFromJetError@@YAJJ@Z; MakeHresultFromJetError(long)
0x1800769e7  mov     r9d, 801h
0x1800769ed  jmp     loc_180076829
0x1800769f2  cmp     [rbp+9B0h+arg_20], ebx
0x1800769f8  jz      loc_180076ACA
0x1800769fe  test    r15d, r15d
0x180076a01  jnz     loc_180076ACA
0x180076a07  mov     rdx, [rsp+0AB0h+tableid]; tableid
0x180076a0c  lea     r8, ?UdmIdxName_CallHistory_Unseen@@3QBDB; "Unseen"
0x180076a13  mov     rcx, [rsp+0AB0h+sesid]; sesid
0x180076a18  call    cs:__imp_JetSetCurrentIndexA
0x180076a1e  test    eax, eax
0x180076a20  jns     short loc_180076A34
0x180076a22  mov     ecx, eax; int
0x180076a24  call    ?MakeHresultFromJetError@@YAJJ@Z; MakeHresultFromJetError(long)
0x180076a29  mov     r9d, 806h
0x180076a2f  jmp     loc_180076829
0x180076a34  mov     rax, [rsp+0AB0h+pvData]
0x180076a39  cmp     [rax], rbx
0x180076a3c  jz      short loc_180076A9F
0x180076a3e  mov     rdx, [rsp+0AB0h+tableid]; tableid
0x180076a43  mov     r9d, 8; cbData
0x180076a49  mov     rcx, [rsp+0AB0h+sesid]; sesid
0x180076a4e  mov     r8, rax; pvData
0x180076a51  mov     [rsp+0AB0h+cbParameters], 1; grbit
0x180076a59  call    cs:__imp_JetMakeKey
0x180076a5f  test    eax, eax
0x180076a61  jns     short loc_180076A75
0x180076a63  mov     ecx, eax; int
0x180076a65  call    ?MakeHresultFromJetError@@YAJJ@Z; MakeHresultFromJetError(long)
0x180076a6a  mov     r9d, 80Ah
0x180076a70  jmp     loc_180076829
0x180076a75  lea     r8, [rsp+0AB0h+var_A54]; int *
0x180076a7a  mov     edx, 3; unsigned int
0x180076a7f  lea     rcx, [rsp+0AB0h+sesid]; this
0x180076a84  call    ?MaybeSetRange@auto_JET_TABLEID@@QEAAJKPEAH@Z; auto_JET_TABLEID::MaybeSetRange(ulong,int *)
0x180076a89  test    eax, eax
0x180076a8b  jns     short loc_180076AC4
0x180076a8d  mov     ecx, eax; int
0x180076a8f  call    ?MakeHresultFromJetError@@YAJJ@Z; MakeHresultFromJetError(long)
0x180076a94  mov     r9d, 80Bh
0x180076a9a  jmp     loc_180076829
0x180076a9f  lea     rdx, [rsp+0AB0h+var_A54]; int *
0x180076aa4  lea     rcx, [rsp+0AB0h+sesid]; struct auto_JET_TABLEID *
0x180076aa9  call    ?MoveFirst@@YAJAEBVauto_JET_TABLEID@@PEAH@Z; MoveFirst(auto_JET_TABLEID const &,int *)
0x180076aae  test    eax, eax
0x180076ab0  jns     short loc_180076AC4
0x180076ab2  mov     ecx, eax; int
0x180076ab4  call    ?MakeHresultFromJetError@@YAJJ@Z; MakeHresultFromJetError(long)
0x180076ab9  mov     r9d, 80Fh
0x180076abf  jmp     loc_180076829
0x180076ac4  cmp     [rsp+0AB0h+var_A54], ebx
0x180076ac8  jnz     short loc_180076AD2
0x180076aca  mov     [r14], ebx
0x180076acd  jmp     loc_180076F12
0x180076ad2  test    r13, r13
0x180076ad5  jnz     loc_180076DD0
0x180076adb  test    r12d, r12d
0x180076ade  jnz     short loc_180076B1A
0x180076ae0  test    rdi, rdi
0x180076ae3  jz      short loc_180076AEA
0x180076ae5  test    r15d, r15d
0x180076ae8  jz      short loc_180076B1A
0x180076aea  mov     rdx, [rsp+0AB0h+tableid]; tableid
0x180076aef  xor     r9d, r9d; crecMax
0x180076af2  mov     rcx, [rsp+0AB0h+sesid]; sesid
0x180076af7  mov     r8, r14; pcrec
0x180076afa  call    cs:__imp_JetIndexRecordCount
0x180076b00  test    eax, eax
0x180076b02  jns     loc_180076F12
0x180076b08  mov     ecx, eax; int
0x180076b0a  call    ?MakeHresultFromJetError@@YAJJ@Z; MakeHresultFromJetError(long)
0x180076b0f  mov     r9d, 866h
0x180076b15  jmp     loc_180076829
0x180076b1a  mov     rcx, [rsi+7F8h]; this
0x180076b21  lea     r8, [rsp+0AB0h+var_A70]; int *
0x180076b26  lea     rdx, off_180130D60; struct ColumnDefinition *
0x180076b2d  mov     [rsp+0AB0h+var_A70], ebx
0x180076b31  call    ?FindColumnEx@DatabaseVolumeSession@@QEBAKPEBUColumnDefinition@@PEAH@Z; DatabaseVolumeSession::FindColumnEx(ColumnDefinition const *,int *)
0x180076b36  xor     r13d, r13d
0x180076b39  mov     dword ptr [rsp+0AB0h+pvData], eax
0x180076b3d  mov     ebx, 0CBh
0x180076b42  cmp     [rsp+0AB0h+var_A70], r13d
0x180076b47  jnz     short loc_180076B58
0x180076b49  mov     r8d, ebx
0x180076b4c  lea     rdx, aOnecoreuapBase_62; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180076b53  call    Log_AssertionEvent_2
0x180076b58  mov     rcx, [rsi+7F8h]; this
  ... truncated ...
```
