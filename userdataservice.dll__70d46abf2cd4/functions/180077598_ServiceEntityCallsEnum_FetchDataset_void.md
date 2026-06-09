# ServiceEntityCallsEnum::FetchDataset(void)

- ea: `0x180077598`
- end: `0x1800781d1`
- name: `?FetchDataset@ServiceEntityCallsEnum@@QEAAJXZ`
- size: `3129`
- prototype: `__int64 __fastcall(ServiceEntityCallsEnum *__hidden this)`
- caller_count: `2`
- callee_count: `26`
- tags: `file_ops, authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1800de2c0`
- `0x1800df140`

## callees

- `0x1800049f0`
- `0x1800054c0`
- `0x1800083d8`
- `0x180008f0c`
- `0x18000e1f8`
- `0x180013000`
- `0x180018c20`
- `0x18003bf04`
- `0x18005e048`
- `0x180066860`
- `0x180068698`
- `0x18006a8ac`
- `0x180075f98`
- `0x180076664`
- `0x180077598`
- `0x1800977ac`
- `0x1800d9fd4`
- `0x1800da7c0`
- `0x1800daae8`
- `0x1800dac90`
- `0x1800db6b0`
- `0x1800db8c8`
- `0x1800dfb00`
- `0x1800e1428`
- `0x18012c75e`
- `0x18012c7b0`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180077ab9`
- `msvcrt!_wcsicmp` at `0x180077ab9`
- `ESENT!JetOpenTableA` at `0x18007771b`
- `ESENT!JetOpenTableA` at `0x18007771b`
- `ESENT!JetMakeKey` at `0x180077933`
- `ESENT!JetMakeKey` at `0x180077982`
- `ESENT!JetMakeKey` at `0x180077933`
- `ESENT!JetMakeKey` at `0x180077982`
- `ESENT!JetSetCurrentIndexA` at `0x1800777a0`
- `ESENT!JetSetCurrentIndexA` at `0x1800777a0`
- `ESENT!JetRetrieveColumns` at `0x180077a5d`
- `ESENT!JetRetrieveColumns` at `0x180077a5d`

## string_xrefs

- `0x180077838`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\datasession.cpp`
- `0x180077603`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\callhistory.cpp`
- `0x18007768f`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\callhistory.cpp`
- `0x180077732`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\callhistory.cpp`
- `0x1800777b7`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\callhistory.cpp`
- `0x180077b3b`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\callhistory.cpp`
- `0x180077bab`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\callhistory.cpp`
- `0x180077c19`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\callhistory.cpp`
- `0x180077c92`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\callhistory.cpp`
- `0x180077d07`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\callhistory.cpp`
- `0x180077d7e`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\callhistory.cpp`
- `0x180077df5`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\callhistory.cpp`
- `0x180077e6c`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\callhistory.cpp`
- `0x180077ee3`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\callhistory.cpp`
- `0x180077f5a`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\callhistory.cpp`
- `0x180077fca`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\callhistory.cpp`

## pseudocode

```c
__int64 __fastcall ServiceEntityCallsEnum::FetchDataset(ServiceEntityCallsEnum *this)
{
  int v2; // eax
  int PhoneHashesFor; // eax
  unsigned int v4; // ebx
  void *v5; // rdi
  _QWORD *v6; // rdx
  char *v7; // rcx
  __int64 v8; // rax
  int v9; // eax
  unsigned int HresultFromJetError; // edi
  void *v11; // rbx
  _QWORD *v12; // rdx
  char *v13; // rcx
  __int64 v14; // rax
  JET_ERR v15; // eax
  void *v16; // rbx
  _QWORD *v17; // rdx
  char *v18; // rcx
  __int64 v19; // rax
  JET_ERR v20; // eax
  void *v21; // rbx
  _QWORD *v22; // rdx
  char *v23; // rcx
  __int64 v24; // rax
  __int64 v25; // rcx
  __int64 v26; // rcx
  __int64 v27; // rcx
  __int64 v28; // rcx
  __int64 v29; // rcx
  __int64 v30; // rcx
  unsigned int v31; // r13d
  __int64 v32; // r9
  void **v33; // rdi
  _DWORD *v34; // rbx
  __int64 v35; // r12
  unsigned __int64 v36; // rcx
  int v37; // eax
  int v38; // esi
  unsigned int v39; // esi
  const void *v40; // r8
  JET_ERR Key; // eax
  unsigned int v42; // edx
  int v43; // eax
  const void *v44; // r8
  JET_ERR v45; // eax
  int v46; // eax
  JET_SESID v47; // rcx
  JET_ERR v48; // eax
  __int64 v49; // r8
  int v50; // eax
  void *v51; // rbx
  _QWORD *v52; // rdx
  char *v53; // rcx
  __int64 v54; // rax
  void *v55; // rbx
  _QWORD *v56; // rdx
  char *v57; // rcx
  __int64 v58; // rax
  void *v59; // rbx
  _QWORD *v60; // rdx
  char *v61; // rcx
  __int64 v62; // rax
  void *v63; // rbx
  _QWORD *v64; // rdx
  char *v65; // rcx
  __int64 v66; // rax
  void *v67; // rbx
  _QWORD *v68; // rdx
  char *v69; // rcx
  __int64 v70; // rax
  void *v71; // rbx
  _QWORD *v72; // rdx
  char *v73; // rcx
  __int64 v74; // rax
  void *v75; // rbx
  _QWORD *v76; // rdx
  char *v77; // rcx
  __int64 v78; // rax
  void *v79; // rbx
  _QWORD *v80; // rdx
  char *v81; // rcx
  __int64 v82; // rax
  void *v83; // rbx
  _QWORD *v84; // rdx
  char *v85; // rcx
  __int64 v86; // rax
  void *v87; // rbx
  _QWORD *v88; // rdx
  char *v89; // rcx
  __int64 v90; // rax
  void *v91; // rbx
  _QWORD *v92; // rdx
  char *v93; // rcx
  __int64 v94; // rax
  _DWORD *v95; // rsi
  __int64 v96; // rcx
  __int64 v97; // r9
  _DWORD *v98; // rdi
  _DWORD *i; // r8
  __int64 v100; // r8
  __int64 v101; // r8
  int v102; // eax
  void *v103; // rbx
  _QWORD *v104; // rdx
  char *v105; // rcx
  __int64 v106; // rax
  int v108; // [rsp+40h] [rbp-C0h] BYREF
  char v109; // [rsp+44h] [rbp-BCh]
  JET_SESID sesid; // [rsp+48h] [rbp-B8h] BYREF
  JET_TABLEID tableid[2]; // [rsp+50h] [rbp-B0h] BYREF
  JET_SESID v112; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v113; // [rsp+68h] [rbp-98h]
  unsigned int cbData; // [rsp+70h] [rbp-90h] BYREF
  void *Block[5]; // [rsp+78h] [rbp-88h] BYREF
  void *v116; // [rsp+A0h] [rbp-60h] BYREF
  void *Src; // [rsp+A8h] [rbp-58h]
  _DWORD *v118; // [rsp+B0h] [rbp-50h]
  JET_COLUMNID Column; // [rsp+B8h] [rbp-48h]
  unsigned int v120; // [rsp+BCh] [rbp-44h]
  _OWORD v121[2]; // [rsp+C0h] [rbp-40h] BYREF
  JET_RETRIEVECOLUMN pretrievecolumn; // [rsp+E0h] [rbp-20h] BYREF
  unsigned int v123; // [rsp+110h] [rbp+10h]
  char *v124; // [rsp+118h] [rbp+18h]
  __int64 v125; // [rsp+120h] [rbp+20h]
  __int64 v126; // [rsp+128h] [rbp+28h]
  int v127; // [rsp+130h] [rbp+30h]
  int v128[2]; // [rsp+134h] [rbp+34h]
  int v129; // [rsp+13Ch] [rbp+3Ch]
  unsigned int v130; // [rsp+140h] [rbp+40h]
  wchar_t *v131; // [rsp+148h] [rbp+48h]
  __int64 v132; // [rsp+150h] [rbp+50h]
  __int64 v133; // [rsp+158h] [rbp+58h]
  int v134; // [rsp+160h] [rbp+60h]
  int v135[2]; // [rsp+164h] [rbp+64h]
  int v136; // [rsp+16Ch] [rbp+6Ch]
  wchar_t String2[1032]; // [rsp+170h] [rbp+70h] BYREF

  utl::unordered_map<enum _SebiEventType,_GUID,utl::hash<enum _SebiEventType>,utl::equal_to<enum _SebiEventType>,utl::allocator<utl::pair<enum _SebiEventType const,_GUID>>>::unordered_map<enum _SebiEventType,_GUID,utl::hash<enum _SebiEventType>,utl::equal_to<enum _SebiEventType>,utl::allocator<utl::pair<enum _SebiEventType const,_GUID>>>(Block);
  v2 = *((_DWORD *)this + 22);
  v112 = *((_QWORD *)this + 10);
  LODWORD(v113) = v2;
  PhoneHashesFor = GetPhoneHashesFor(&v112, Block);
  v4 = PhoneHashesFor;
  if ( PhoneHashesFor < 0 )
  {
    Log_HREvent(
      (unsigned int)PhoneHashesFor,
      1,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\callhistory.cpp",
      3916);
    while ( 1 )
    {
      v5 = Block[0];
      if ( Block[0] == Block )
        break;
      v6 = (_QWORD *)*((_QWORD *)Block[0] + 1);
      v7 = (char *)Block[0] + 24;
      v8 = *(_QWORD *)Block[0];
      *v6 = *(_QWORD *)Block[0];
      *(_QWORD *)(v8 + 8) = v6;
      utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v7);
      operator delete(v5);
    }
    goto LABEL_97;
  }
  v112 = *((_QWORD *)this + 5);
  v113 = 0;
  sesid = v112;
  tableid[0] = -1;
  v9 = auto_JET_TRANSACTION::Begin((auto_JET_TRANSACTION *)&v112, 1u);
  if ( v9 < 0 )
  {
    HresultFromJetError = MakeHresultFromJetError(v9);
    Log_HREvent(
      HresultFromJetError,
      0,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\callhistory.cpp",
      3922);
    auto_JET_TABLEID::~auto_JET_TABLEID((auto_JET_TABLEID *)&sesid);
    auto_JET_TRANSACTION::~auto_JET_TRANSACTION((auto_JET_TRANSACTION *)&v112);
    while ( 1 )
    {
      v11 = Block[0];
      if ( Block[0] == Block )
        break;
      v12 = (_QWORD *)*((_QWORD *)Block[0] + 1);
      v13 = (char *)Block[0] + 24;
      v14 = *(_QWORD *)Block[0];
      *v12 = *(_QWORD *)Block[0];
      *(_QWORD *)(v14 + 8) = v12;
      utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v13);
      operator delete(v11);
    }
LABEL_9:
    v4 = HresultFromJetError;
    goto LABEL_97;
  }
  v15 = JetOpenTableA(*((_QWORD *)this + 5), *((_DWORD *)this + 12), "CallHistory", 0, 0, 4u, tableid);
  if ( v15 < 0 )
  {
    HresultFromJetError = MakeHresultFromJetError(v15);
    Log_HREvent(
      HresultFromJetError,
      0,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\callhistory.cpp",
      3931);
    auto_JET_TABLEID::~auto_JET_TABLEID((auto_JET_TABLEID *)&sesid);
    auto_JET_TRANSACTION::~auto_JET_TRANSACTION((auto_JET_TRANSACTION *)&v112);
    while ( 1 )
    {
      v16 = Block[0];
      if ( Block[0] == Block )
        break;
      v17 = (_QWORD *)*((_QWORD *)Block[0] + 1);
      v18 = (char *)Block[0] + 24;
      v19 = *(_QWORD *)Block[0];
      *v17 = *(_QWORD *)Block[0];
      *(_QWORD *)(v19 + 8) = v17;
      utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v18);
      operator delete(v16);
    }
    goto LABEL_9;
  }
  v20 = JetSetCurrentIndexA(sesid, tableid[0], "ByHash");
  if ( v20 < 0 )
  {
    HresultFromJetError = MakeHresultFromJetError(v20);
    Log_HREvent(
      HresultFromJetError,
      0,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\callhistory.cpp",
      3933);
    auto_JET_TABLEID::~auto_JET_TABLEID((auto_JET_TABLEID *)&sesid);
    auto_JET_TRANSACTION::~auto_JET_TRANSACTION((auto_JET_TRANSACTION *)&v112);
    while ( 1 )
    {
      v21 = Block[0];
      if ( Block[0] == Block )
        break;
      v22 = (_QWORD *)*((_QWORD *)Block[0] + 1);
      v23 = (char *)Block[0] + 24;
      v24 = *(_QWORD *)Block[0];
      *v22 = *(_QWORD *)Block[0];
      *(_QWORD *)(v24 + 8) = v22;
      utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v23);
      operator delete(v21);
    }
    goto LABEL_9;
  }
  v25 = *((_QWORD *)this + 4);
  v108 = 0;
  Column = DatabaseVolumeSession::FindColumnEx(
             *(DatabaseVolumeSession **)(v25 + 2040),
             (const struct ColumnDefinition *)&UdmTableCols_CallHistory,
             &v108);
  if ( !v108 )
    Log_AssertionEvent_2(
      v26,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\datasession.cpp",
      203);
  v27 = *((_QWORD *)this + 4);
  v108 = 0;
  v120 = DatabaseVolumeSession::FindColumnEx(
           *(DatabaseVolumeSession **)(v27 + 2040),
           (const struct ColumnDefinition *)&off_180130C60,
           &v108);
  if ( !v108 )
    Log_AssertionEvent_2(
      v28,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\datasession.cpp",
      203);
  v29 = *((_QWORD *)this + 4);
  v108 = 0;
  v31 = DatabaseVolumeSession::FindColumnEx(
          *(DatabaseVolumeSession **)(v29 + 2040),
          (const struct ColumnDefinition *)&off_180130D60,
          &v108);
  if ( !v108 )
    Log_AssertionEvent_2(
      v30,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\datasession.cpp",
      203);
  utl::vector<tlx::auto_xxx<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),0>,utl::allocator<tlx::auto_xxx<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),0>>>::vector<tlx::auto_xxx<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),0>,utl::allocator<tlx::auto_xxx<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),0>>>(&v116);
  v33 = (void **)Block[0];
  v34 = Src;
  v35 = (__int64)(*((_QWORD *)this + 17) - *((_QWORD *)this + 16)) >> 5;
  while ( v33 != Block )
  {
    v36 = (_BYTE *)v33[4] - (_BYTE *)v33[3];
    cbData = 0;
    v37 = ULongLongToULong(v36, &cbData);
    v38 = v37;
    if ( v37 < 0 )
    {
      Log_HREvent(
        (unsigned int)v37,
        1,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\callhistory.cpp",
        3950);
      utl::vector<UdmEmailParticipant,utl::allocator<UdmEmailParticipant>>::_Uninit(&v116);
      auto_JET_TABLEID::~auto_JET_TABLEID((auto_JET_TABLEID *)&sesid);
      auto_JET_TRANSACTION::~auto_JET_TRANSACTION((auto_JET_TRANSACTION *)&v112);
      while ( 1 )
      {
        v91 = Block[0];
        if ( Block[0] == Block )
          break;
        v92 = (_QWORD *)*((_QWORD *)Block[0] + 1);
        v93 = (char *)Block[0] + 24;
        v94 = *(_QWORD *)Block[0];
        *v92 = *(_QWORD *)Block[0];
        *(_QWORD *)(v94 + 8) = v92;
        utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v93);
        operator delete(v91);
      }
LABEL_81:
      v4 = v38;
      goto LABEL_97;
    }
    v39 = 0;
    v40 = v33[3];
    v108 = 0;
    Key = JetMakeKey(sesid, tableid[0], v40, cbData, 0x401u);
    if ( Key < 0 )
    {
      HresultFromJetError = MakeHresultFromJetError(Key);
      Log_HREvent(
        HresultFromJetError,
        0,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\callhistory.cpp",
        3953);
      utl::vector<UdmEmailParticipant,utl::allocator<UdmEmailParticipant>>::_Uninit(&v116);
      auto_JET_TABLEID::~auto_JET_TABLEID((auto_JET_TABLEID *)&sesid);
      auto_JET_TRANSACTION::~auto_JET_TRANSACTION((auto_JET_TRANSACTION *)&v112);
      while ( 1 )
      {
        v87 = Block[0];
        if ( Block[0] == Block )
          break;
        v88 = (_QWORD *)*((_QWORD *)Block[0] + 1);
        v89 = (char *)Block[0] + 24;
        v90 = *(_QWORD *)Block[0];
        *v88 = *(_QWORD *)Block[0];
        *(_QWORD *)(v90 + 8) = v88;
        utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v89);
        operator delete(v87);
      }
      goto LABEL_9;
    }
    v43 = auto_JET_TABLEID::MaybeSeek((auto_JET_TABLEID *)&sesid, v42, (enum TableSeekResult *)&v108);
    if ( v43 < 0 )
    {
      HresultFromJetError = MakeHresultFromJetError(v43);
      Log_HREvent(
        HresultFromJetError,
        0,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\callhistory.cpp",
        3954);
      utl::vector<UdmEmailParticipant,utl::allocator<UdmEmailParticipant>>::_Uninit(&v116);
      auto_JET_TABLEID::~auto_JET_TABLEID((auto_JET_TABLEID *)&sesid);
      auto_JET_TRANSACTION::~auto_JET_TRANSACTION((auto_JET_TRANSACTION *)&v112);
      while ( 1 )
      {
        v83 = Block[0];
        if ( Block[0] == Block )
          break;
        v84 = (_QWORD *)*((_QWORD *)Block[0] + 1);
        v85 = (char *)Block[0] + 24;
        v86 = *(_QWORD *)Block[0];
        *v84 = *(_QWORD *)Block[0];
        *(_QWORD *)(v86 + 8) = v84;
        utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v85);
        operator delete(v83);
      }
      goto LABEL_9;
    }
    if ( v108 != 1 )
    {
      v44 = v33[3];
      v108 = 0;
      v45 = JetMakeKey(sesid, tableid[0], v44, cbData, 0x801u);
      if ( v45 < 0 )
      {
        HresultFromJetError = MakeHresultFromJetError(v45);
        Log_HREvent(
          HresultFromJetError,
          0,
          "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\callhistory.cpp",
          3962);
        utl::vector<UdmEmailParticipant,utl::allocator<UdmEmailParticipant>>::_Uninit(&v116);
        auto_JET_TABLEID::~auto_JET_TABLEID((auto_JET_TABLEID *)&sesid);
        auto_JET_TRANSACTION::~auto_JET_TRANSACTION((auto_JET_TRANSACTION *)&v112);
        while ( 1 )
        {
          v79 = Block[0];
          if ( Block[0] == Block )
            break;
          v80 = (_QWORD *)*((_QWORD *)Block[0] + 1);
          v81 = (char *)Block[0] + 24;
          v82 = *(_QWORD *)Block[0];
          *v80 = *(_QWORD *)Block[0];
          *(_QWORD *)(v82 + 8) = v80;
          utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v81);
          operator delete(v79);
        }
        goto LABEL_9;
      }
      v46 = auto_JET_TABLEID::MaybeSetRange((auto_JET_TABLEID *)&sesid, 3u, &v108);
      if ( v46 < 0 )
      {
        HresultFromJetError = MakeHresultFromJetError(v46);
        Log_HREvent(
          HresultFromJetError,
          0,
          "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\callhistory.cpp",
          3963);
        utl::vector<UdmEmailParticipant,utl::allocator<UdmEmailParticipant>>::_Uninit(&v116);
        auto_JET_TABLEID::~auto_JET_TABLEID((auto_JET_TABLEID *)&sesid);
        auto_JET_TRANSACTION::~auto_JET_TRANSACTION((auto_JET_TRANSACTION *)&v112);
        while ( 1 )
        {
          v75 = Block[0];
          if ( Block[0] == Block )
            break;
          v76 = (_QWORD *)*((_QWORD *)Block[0] + 1);
          v77 = (char *)Block[0] + 24;
          v78 = *(_QWORD *)Block[0];
          *v76 = *(_QWORD *)Block[0];
          *(_QWORD *)(v78 + 8) = v76;
          utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v77);
          operator delete(v75);
        }
        goto LABEL_9;
      }
      while ( v108 )
      {
        v47 = *((_QWORD *)this + 5);
        pretrievecolumn.columnid = Column;
        pretrievecolumn.pvData = (char *)v121 + 8;
        *(_QWORD *)&pretrievecolumn.columnidNextTagged = 0;
        *(&pretrievecolumn.err + 1) = 0;
        v123 = v120;
        v124 = (char *)v121 + 12;
        *(_QWORD *)v128 = 0;
        v129 = 0;
        v131 = String2;
        *(_QWORD *)v135 = 0;
        v136 = 0;
        LODWORD(v121[0]) = 0;
        *(_OWORD *)((char *)v121 + 4) = 1u;
        *(_QWORD *)&pretrievecolumn.cbData = 4;
        *(_QWORD *)&pretrievecolumn.grbit = 0;
        pretrievecolumn.itagSequence = 1;
        v125 = 8;
        v126 = 0;
        v127 = 1;
        v130 = v31;
        v132 = 2050;
        v133 = 0;
        v134 = 1;
        v48 = JetRetrieveColumns(v47, tableid[0], &pretrievecolumn, (v35 != 0) + 2);
        if ( v48 < 0 )
        {
          HresultFromJetError = MakeHresultFromJetError(v48);
          Log_HREvent(
            HresultFromJetError,
            0,
            "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\callhistory.cpp",
            3978);
          utl::vector<UdmEmailParticipant,utl::allocator<UdmEmailParticipant>>::_Uninit(&v116);
          auto_JET_TABLEID::~auto_JET_TABLEID((auto_JET_TABLEID *)&sesid);
          auto_JET_TRANSACTION::~auto_JET_TRANSACTION((auto_JET_TRANSACTION *)&v112);
          while ( 1 )
          {
            v71 = Block[0];
            if ( Block[0] == Block )
              break;
            v72 = (_QWORD *)*((_QWORD *)Block[0] + 1);
            v73 = (char *)Block[0] + 24;
            v74 = *(_QWORD *)Block[0];
            *v72 = *(_QWORD *)Block[0];
            *(_QWORD *)(v74 + 8) = v72;
            utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v73);
            operator delete(v71);
          }
          goto LABEL_9;
        }
        if ( pretrievecolumn.err < 0 )
        {
          HresultFromJetError = MakeHresultFromJetError(pretrievecolumn.err);
          Log_HREvent(
            HresultFromJetError,
            0,
            "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\callhistory.cpp",
            3979);
          utl::vector<UdmEmailParticipant,utl::allocator<UdmEmailParticipant>>::_Uninit(&v116);
          auto_JET_TABLEID::~auto_JET_TABLEID((auto_JET_TABLEID *)&sesid);
          auto_JET_TRANSACTION::~auto_JET_TRANSACTION((auto_JET_TRANSACTION *)&v112);
          while ( 1 )
          {
            v67 = Block[0];
            if ( Block[0] == Block )
              break;
            v68 = (_QWORD *)*((_QWORD *)Block[0] + 1);
            v69 = (char *)Block[0] + 24;
            v70 = *(_QWORD *)Block[0];
            *v68 = *(_QWORD *)Block[0];
            *(_QWORD *)(v70 + 8) = v68;
            utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v69);
            operator delete(v67);
          }
          goto LABEL_9;
        }
        if ( v128[1] < 0 )
        {
          HresultFromJetError = MakeHresultFromJetError(v128[1]);
          Log_HREvent(
            HresultFromJetError,
            0,
            "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\callhistory.cpp",
            3980);
          utl::vector<UdmEmailParticipant,utl::allocator<UdmEmailParticipant>>::_Uninit(&v116);
          auto_JET_TABLEID::~auto_JET_TABLEID((auto_JET_TABLEID *)&sesid);
          auto_JET_TRANSACTION::~auto_JET_TRANSACTION((auto_JET_TRANSACTION *)&v112);
          while ( 1 )
          {
            v63 = Block[0];
            if ( Block[0] == Block )
              break;
            v64 = (_QWORD *)*((_QWORD *)Block[0] + 1);
            v65 = (char *)Block[0] + 24;
            v66 = *(_QWORD *)Block[0];
            *v64 = *(_QWORD *)Block[0];
            *(_QWORD *)(v66 + 8) = v64;
            utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v65);
            operator delete(v63);
          }
          goto LABEL_9;
        }
        if ( v35 )
        {
          if ( v135[1] < 0 )
          {
            HresultFromJetError = MakeHresultFromJetError(v135[1]);
            Log_HREvent(
              HresultFromJetError,
              0,
              "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\callhistory.cpp",
              3985);
            utl::vector<UdmEmailParticipant,utl::allocator<UdmEmailParticipant>>::_Uninit(&v116);
            auto_JET_TABLEID::~auto_JET_TABLEID((auto_JET_TABLEID *)&sesid);
            auto_JET_TRANSACTION::~auto_JET_TRANSACTION((auto_JET_TRANSACTION *)&v112);
            while ( 1 )
            {
              v51 = Block[0];
              if ( Block[0] == Block )
                break;
              v52 = (_QWORD *)*((_QWORD *)Block[0] + 1);
              v53 = (char *)Block[0] + 24;
              v54 = *(_QWORD *)Block[0];
              *v52 = *(_QWORD *)Block[0];
              *(_QWORD *)(v54 + 8) = v52;
              utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v53);
              operator delete(v51);
            }
            goto LABEL_9;
          }
          while ( 1 )
          {
            v49 = *((_QWORD *)this + 16);
            if ( v39 >= (unsigned __int64)((*((_QWORD *)this + 17) - v49) >> 5) )
              break;
            if ( !_wcsicmp(*(const wchar_t **)(32LL * v39 + v49), String2) )
              goto LABEL_41;
            ++v39;
          }
        }
        else
        {
LABEL_41:
          if ( v34 == v118 )
          {
            if ( !utl::vector<ServiceEntityCallsEnum::CallItem,utl::allocator<ServiceEntityCallsEnum::CallItem>>::_PushBackOne2<ServiceEntityCallsEnum::CallItem const &>(
                    (__int64 *)&v116,
                    (__int64)v121) )
            {
              HresultFromJetError = -2147024882;
              Log_HREvent(
                2147942414LL,
                0,
                "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\callhistory.cpp",
                4003);
              utl::vector<UdmEmailParticipant,utl::allocator<UdmEmailParticipant>>::_Uninit(&v116);
              auto_JET_TABLEID::~auto_JET_TABLEID((auto_JET_TABLEID *)&sesid);
              auto_JET_TRANSACTION::~auto_JET_TRANSACTION((auto_JET_TRANSACTION *)&v112);
              while ( 1 )
              {
                v59 = Block[0];
                if ( Block[0] == Block )
                  break;
                v60 = (_QWORD *)*((_QWORD *)Block[0] + 1);
                v61 = (char *)Block[0] + 24;
                v62 = *(_QWORD *)Block[0];
                *v60 = *(_QWORD *)Block[0];
                *(_QWORD *)(v62 + 8) = v60;
                utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v61);
                operator delete(v59);
              }
              goto LABEL_9;
            }
            v34 = Src;
          }
          else
          {
            *(_OWORD *)v34 = v121[0];
            v34[4] = v121[1];
            v34 += 5;
            Src = v34;
          }
        }
        v50 = Move(sesid, tableid[0], 1, &v108);
        v38 = v50;
        if ( v50 < 0 )
        {
          Log_HREvent(
            (unsigned int)v50,
            1,
            "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\callhistory.cpp",
            4007);
          utl::vector<UdmEmailParticipant,utl::allocator<UdmEmailParticipant>>::_Uninit(&v116);
          auto_JET_TABLEID::~auto_JET_TABLEID((auto_JET_TABLEID *)&sesid);
          auto_JET_TRANSACTION::~auto_JET_TRANSACTION((auto_JET_TRANSACTION *)&v112);
          while ( 1 )
          {
            v55 = Block[0];
            if ( Block[0] == Block )
              break;
            v56 = (_QWORD *)*((_QWORD *)Block[0] + 1);
            v57 = (char *)Block[0] + 24;
            v58 = *(_QWORD *)Block[0];
            *v56 = *(_QWORD *)Block[0];
            *(_QWORD *)(v58 + 8) = v56;
            utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v57);
            operator delete(v55);
          }
          goto LABEL_81;
        }
        v39 = 0;
      }
    }
    v33 = (void **)*v33;
  }
  v95 = v116;
  LOBYTE(v32) = v109;
  utl::_SortImp<utl::_ArrayIt<ServiceEntityCallsEnum::CallItem>,__int64,ServiceEntityCallsEnum::CompareCallIds>(
    (__int64)v116,
    (__int64)v34,
    0xCCCCCCCCCCCCCCCDuLL * (((char *)v34 - (_BYTE *)v116) >> 2),
    v32);
  v98 = v95;
  if ( v95 == v34 )
  {
LABEL_91:
    if ( v98 != v34 )
    {
      memmove_0(
        v98,
        v34,
        20
      * (((unsigned __int64)((unsigned __int128)(0 * (__int128)0x6666666666666667LL) >> 64) >> 63)
       + ((__int64)((unsigned __int128)(0 * (__int128)0x6666666666666667LL) >> 64) >> 3)));
      v34 -= v34 - v98;
      Src = v34;
    }
  }
  else
  {
    for ( i = v95; ; v98 = i )
    {
      v100 = (__int64)(i + 5);
      if ( (_DWORD *)v100 == v34 )
        break;
      if ( utl::equal_to<void>::operator()<ServiceEntityCallsEnum::CallItem &,ServiceEntityCallsEnum::CallItem &>(
             v96,
             (__int64)v98,
             v100) )
      {
        while ( 1 )
        {
          v101 = (__int64)(i + 5);
          if ( (_DWORD *)v101 == v34 )
            break;
          if ( !utl::equal_to<void>::operator()<ServiceEntityCallsEnum::CallItem &,ServiceEntityCallsEnum::CallItem &>(
                  v96,
                  (__int64)v98,
                  v101) )
          {
            v102 = i[4];
            v98 += 5;
            *(_OWORD *)v98 = *(_OWORD *)i;
            v98[4] = v102;
          }
        }
        v98 += 5;
        goto LABEL_91;
      }
    }
  }
  LOBYTE(v97) = v109;
  utl::_SortImp<utl::_ArrayIt<ServiceEntityCallsEnum::CallItem>,__int64,ServiceEntityCallsEnum::CompareCallTimes>(
    (__int64)v95,
    (__int64)v34,
    0xCCCCCCCCCCCCCCCDuLL * (v34 - v95),
    v97);
  utl::vector<ServiceEntityCallsEnum::CallItem,utl::allocator<ServiceEntityCallsEnum::CallItem>>::swap(
    &v116,
    (char *)this + 96);
  *((_DWORD *)this + 30) = 1;
  utl::vector<UdmEmailParticipant,utl::allocator<UdmEmailParticipant>>::_Uninit(&v116);
  auto_JET_TABLEID::~auto_JET_TABLEID((auto_JET_TABLEID *)&sesid);
  auto_JET_TRANSACTION::~auto_JET_TRANSACTION((auto_JET_TRANSACTION *)&v112);
  while ( 1 )
  {
    v103 = Block[0];
    if ( Block[0] == Block )
      break;
    v104 = (_QWORD *)*((_QWORD *)Block[0] + 1);
    v105 = (char *)Block[0] + 24;
    v106 = *(_QWORD *)Block[0];
    *v104 = *(_QWORD *)Block[0];
    *(_QWORD *)(v106 + 8) = v104;
    utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v105);
    operator delete(v103);
  }
  v4 = 0;
LABEL_97:
  Block[3] = 0;
  utl::_HashTable<enum _SebiEventType,utl::pair<enum _SebiEventType const,_GUID>,utl::hash<enum _SebiEventType>,utl::equal_to<enum _SebiEventType>,utl::allocator<utl::pair<enum _SebiEventType const,_GUID>>,0>::_FreeBuckets(Block);
  return v4;
}

```

## disassembly

```asm
0x180077598  push    rbp
0x18007759a  push    rbx
0x18007759b  push    rsi
0x18007759c  push    rdi
0x18007759d  push    r12
0x18007759f  push    r13
0x1800775a1  push    r14
0x1800775a3  push    r15
0x1800775a5  lea     rbp, [rsp-898h]
0x1800775ad  sub     rsp, 998h
0x1800775b4  mov     rax, cs:__security_cookie
0x1800775bb  xor     rax, rsp
0x1800775be  mov     [rbp+8D0h+var_50], rax
0x1800775c5  mov     r14, rcx
0x1800775c8  lea     rcx, [rsp+9D0h+Block]
0x1800775cd  call    ??0?$unordered_map@W4_SebiEventType@@U_GUID@@U?$hash@W4_SebiEventType@@@utl@@U?$equal_to@W4_SebiEventType@@@4@V?$allocator@U?$pair@$$CBW4_SebiEventType@@U_GUID@@@utl@@@4@@utl@@QEAA@XZ; utl::unordered_map<_SebiEventType,_GUID,utl::hash<_SebiEventType>,utl::equal_to<_SebiEventType>,utl::allocator<utl::pair<_SebiEventType const,_GUID>>>::unordered_map<_SebiEventType,_GUID,utl::hash<_SebiEventType>,utl::equal_to<_SebiEventType>,utl::allocator<utl::pair<_SebiEventType const,_GUID>>>(void)
0x1800775d2  movsd   xmm0, qword ptr [r14+50h]
0x1800775d8  lea     rdx, [rsp+9D0h+Block]
0x1800775dd  mov     eax, [r14+58h]
0x1800775e1  lea     rcx, [rsp+9D0h+var_970]
0x1800775e6  movsd   [rsp+9D0h+var_970], xmm0
0x1800775ec  mov     dword ptr [rsp+9D0h+var_968], eax
0x1800775f0  call    ?GetPhoneHashesFor@@YAJUOLITEMID@@AEAV?$unordered_set@V?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@Uistring_hash_ascii@tlx@@Uistring_equal_to_ascii@4@V?$allocator@V?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@@2@@utl@@@Z; GetPhoneHashesFor(OLITEMID,utl::unordered_set<utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>,tlx::istring_hash_ascii,tlx::istring_equal_to_ascii,utl::allocator<utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>>> &)
0x1800775f5  xor     esi, esi
0x1800775f7  mov     ebx, eax
0x1800775f9  test    eax, eax
0x1800775fb  jns     short loc_18007764F
0x1800775fd  mov     r9d, 0F4Ch
0x180077603  lea     r8, aOnecoreuapBase_43; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18007760a  lea     edx, [rsi+1]
0x18007760d  mov     ecx, eax
0x18007760f  call    Log_HREvent
0x180077614  mov     rdi, [rsp+9D0h+Block]
0x180077619  lea     rax, [rsp+9D0h+Block]
0x18007761e  cmp     rdi, rax
0x180077621  jz      loc_18007819E
0x180077627  mov     rdx, [rdi+8]
0x18007762b  lea     rcx, [rdi+18h]; void *
0x18007762f  mov     rax, [rdi]
0x180077632  mov     [rdx], rax
0x180077635  mov     [rax+8], rdx
0x180077639  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x18007763e  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x180077645  mov     rcx, rdi; Block
0x180077648  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18007764d  jmp     short loc_180077614
0x18007764f  mov     rax, [r14+28h]
0x180077653  lea     rcx, [rsp+9D0h+var_970]; this
0x180077658  mov     r15d, 1
0x18007765e  mov     [rsp+9D0h+var_970], rax
0x180077663  mov     edx, r15d; unsigned int
0x180077666  mov     [rsp+9D0h+var_968], rsi
0x18007766b  mov     [rsp+9D0h+sesid], rax
0x180077670  mov     [rsp+9D0h+tableid], 0FFFFFFFFFFFFFFFFh
0x180077679  call    ?Begin@auto_JET_TRANSACTION@@QEAAJK@Z; auto_JET_TRANSACTION::Begin(ulong)
0x18007767e  test    eax, eax
0x180077680  jns     short loc_1800776F3
0x180077682  mov     ecx, eax; int
0x180077684  call    ?MakeHresultFromJetError@@YAJJ@Z; MakeHresultFromJetError(long)
0x180077689  mov     r9d, 0F52h
0x18007768f  lea     r8, aOnecoreuapBase_43; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180077696  xor     edx, edx
0x180077698  mov     ecx, eax
0x18007769a  mov     edi, eax
0x18007769c  call    Log_HREvent
0x1800776a1  lea     rcx, [rsp+9D0h+sesid]; this
0x1800776a6  call    ??1auto_JET_TABLEID@@QEAA@XZ; auto_JET_TABLEID::~auto_JET_TABLEID(void)
0x1800776ab  lea     rcx, [rsp+9D0h+var_970]; this
0x1800776b0  call    ??1auto_JET_TRANSACTION@@QEAA@XZ; auto_JET_TRANSACTION::~auto_JET_TRANSACTION(void)
0x1800776b5  mov     rbx, [rsp+9D0h+Block]
0x1800776ba  lea     rax, [rsp+9D0h+Block]
0x1800776bf  cmp     rbx, rax
0x1800776c2  jz      short loc_1800776EC
0x1800776c4  mov     rdx, [rbx+8]
0x1800776c8  lea     rcx, [rbx+18h]; void *
0x1800776cc  mov     rax, [rbx]
0x1800776cf  mov     [rdx], rax
0x1800776d2  mov     [rax+8], rdx
0x1800776d6  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x1800776db  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x1800776e2  mov     rcx, rbx; Block
0x1800776e5  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800776ea  jmp     short loc_1800776B5
0x1800776ec  mov     ebx, edi
0x1800776ee  jmp     loc_18007819E
0x1800776f3  mov     edx, [r14+30h]; dbid
0x1800776f7  lea     rax, [rsp+9D0h+tableid]
0x1800776fc  mov     rcx, [r14+28h]; sesid
0x180077700  lea     r8, ?UdmTableName_CallHistory@@3QBDB; "CallHistory"
0x180077707  mov     [rsp+9D0h+ptableid], rax; ptableid
0x18007770c  xor     r9d, r9d; pvParameters
0x18007770f  mov     [rsp+9D0h+grbit], 4; grbit
0x180077717  mov     [rsp+9D0h+cbParameters], esi; cbParameters
0x18007771b  call    cs:__imp_JetOpenTableA
0x180077721  test    eax, eax
0x180077723  jns     short loc_18007778F
0x180077725  mov     ecx, eax; int
0x180077727  call    ?MakeHresultFromJetError@@YAJJ@Z; MakeHresultFromJetError(long)
0x18007772c  mov     r9d, 0F5Bh
0x180077732  lea     r8, aOnecoreuapBase_43; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180077739  xor     edx, edx
0x18007773b  mov     ecx, eax
0x18007773d  mov     edi, eax
0x18007773f  call    Log_HREvent
0x180077744  lea     rcx, [rsp+9D0h+sesid]; this
0x180077749  call    ??1auto_JET_TABLEID@@QEAA@XZ; auto_JET_TABLEID::~auto_JET_TABLEID(void)
0x18007774e  lea     rcx, [rsp+9D0h+var_970]; this
0x180077753  call    ??1auto_JET_TRANSACTION@@QEAA@XZ; auto_JET_TRANSACTION::~auto_JET_TRANSACTION(void)
0x180077758  mov     rbx, [rsp+9D0h+Block]
0x18007775d  lea     rax, [rsp+9D0h+Block]
0x180077762  cmp     rbx, rax
0x180077765  jz      short loc_1800776EC
0x180077767  mov     rdx, [rbx+8]
0x18007776b  lea     rcx, [rbx+18h]; void *
0x18007776f  mov     rax, [rbx]
0x180077772  mov     [rdx], rax
0x180077775  mov     [rax+8], rdx
0x180077779  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x18007777e  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x180077785  mov     rcx, rbx; Block
0x180077788  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18007778d  jmp     short loc_180077758
0x18007778f  mov     rdx, [rsp+9D0h+tableid]; tableid
0x180077794  lea     r8, ?UdmIdxName_CallHistory_ByHash@@3QBDB; "ByHash"
0x18007779b  mov     rcx, [rsp+9D0h+sesid]; sesid
0x1800777a0  call    cs:__imp_JetSetCurrentIndexA
0x1800777a6  test    eax, eax
0x1800777a8  jns     short loc_180077818
0x1800777aa  mov     ecx, eax; int
0x1800777ac  call    ?MakeHresultFromJetError@@YAJJ@Z; MakeHresultFromJetError(long)
0x1800777b1  mov     r9d, 0F5Dh
0x1800777b7  lea     r8, aOnecoreuapBase_43; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800777be  xor     edx, edx
0x1800777c0  mov     ecx, eax
0x1800777c2  mov     edi, eax
0x1800777c4  call    Log_HREvent
0x1800777c9  lea     rcx, [rsp+9D0h+sesid]; this
0x1800777ce  call    ??1auto_JET_TABLEID@@QEAA@XZ; auto_JET_TABLEID::~auto_JET_TABLEID(void)
0x1800777d3  lea     rcx, [rsp+9D0h+var_970]; this
0x1800777d8  call    ??1auto_JET_TRANSACTION@@QEAA@XZ; auto_JET_TRANSACTION::~auto_JET_TRANSACTION(void)
0x1800777dd  mov     rbx, [rsp+9D0h+Block]
0x1800777e2  lea     rax, [rsp+9D0h+Block]
0x1800777e7  cmp     rbx, rax
0x1800777ea  jz      loc_1800776EC
0x1800777f0  mov     rdx, [rbx+8]
0x1800777f4  lea     rcx, [rbx+18h]; void *
0x1800777f8  mov     rax, [rbx]
0x1800777fb  mov     [rdx], rax
0x1800777fe  mov     [rax+8], rdx
0x180077802  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x180077807  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x18007780e  mov     rcx, rbx; Block
0x180077811  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180077816  jmp     short loc_1800777DD
0x180077818  mov     rcx, [r14+20h]
0x18007781c  lea     r8, [rsp+9D0h+var_990]; int *
0x180077821  lea     rdx, ?UdmTableCols_CallHistory@@3QBUColumnDefinition@@B; struct ColumnDefinition *
0x180077828  mov     [rsp+9D0h+var_990], esi
0x18007782c  mov     rcx, [rcx+7F8h]; this
0x180077833  call    ?FindColumnEx@DatabaseVolumeSession@@QEBAKPEBUColumnDefinition@@PEAH@Z; DatabaseVolumeSession::FindColumnEx(ColumnDefinition const *,int *)
0x180077838  lea     rdi, aOnecoreuapBase_62; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18007783f  mov     [rbp+8D0h+var_918], eax
0x180077842  mov     ebx, 0CBh
0x180077847  cmp     [rsp+9D0h+var_990], esi
0x18007784b  jnz     short loc_180077858
0x18007784d  mov     r8d, ebx
0x180077850  mov     rdx, rdi
0x180077853  call    Log_AssertionEvent_2
0x180077858  mov     rcx, [r14+20h]
0x18007785c  lea     r8, [rsp+9D0h+var_990]; int *
0x180077861  lea     rdx, off_180130C60; struct ColumnDefinition *
0x180077868  mov     [rsp+9D0h+var_990], esi
0x18007786c  mov     rcx, [rcx+7F8h]; this
0x180077873  call    ?FindColumnEx@DatabaseVolumeSession@@QEBAKPEBUColumnDefinition@@PEAH@Z; DatabaseVolumeSession::FindColumnEx(ColumnDefinition const *,int *)
0x180077878  mov     [rbp+8D0h+var_914], eax
0x18007787b  cmp     [rsp+9D0h+var_990], esi
0x18007787f  jnz     short loc_18007788C
0x180077881  mov     r8d, ebx
0x180077884  mov     rdx, rdi
0x180077887  call    Log_AssertionEvent_2
0x18007788c  mov     rcx, [r14+20h]
0x180077890  lea     r8, [rsp+9D0h+var_990]; int *
0x180077895  lea     rdx, off_180130D60; struct ColumnDefinition *
0x18007789c  mov     [rsp+9D0h+var_990], esi
0x1800778a0  mov     rcx, [rcx+7F8h]; this
0x1800778a7  call    ?FindColumnEx@DatabaseVolumeSession@@QEBAKPEBUColumnDefinition@@PEAH@Z; DatabaseVolumeSession::FindColumnEx(ColumnDefinition const *,int *)
0x1800778ac  mov     r13d, eax
0x1800778af  cmp     [rsp+9D0h+var_990], esi
0x1800778b3  jnz     short loc_1800778C0
0x1800778b5  mov     r8d, ebx
0x1800778b8  mov     rdx, rdi
0x1800778bb  call    Log_AssertionEvent_2
0x1800778c0  lea     rcx, [rbp+8D0h+var_930]
0x1800778c4  call    ??0?$vector@V?$auto_xxx@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@Z$0A@@tlx@@V?$allocator@V?$auto_xxx@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@Z$0A@@tlx@@@utl@@@utl@@QEAA@XZ; utl::vector<tlx::auto_xxx<ushort *,void (*)(ushort *),&SysFreeString(ushort *),0>,utl::allocator<tlx::auto_xxx<ushort *,void (*)(ushort *),&SysFreeString(ushort *),0>>>::vector<tlx::auto_xxx<ushort *,void (*)(ushort *),&SysFreeString(ushort *),0>,utl::allocator<tlx::auto_xxx<ushort *,void (*)(ushort *),&SysFreeString(ushort *),0>>>(void)
0x1800778c9  mov     r12, [r14+88h]
0x1800778d0  sub     r12, [r14+80h]
0x1800778d7  mov     rdi, [rsp+9D0h+Block]
0x1800778dc  mov     rbx, [rbp+8D0h+Src]
0x1800778e0  sar     r12, 5
0x1800778e4  lea     rax, [rsp+9D0h+Block]
0x1800778e9  cmp     rdi, rax
0x1800778ec  jz      loc_180078038
0x1800778f2  mov     rcx, [rdi+20h]
0x1800778f6  lea     rdx, [rsp+9D0h+cbData]; unsigned int *
0x1800778fb  sub     rcx, [rdi+18h]; unsigned __int64
0x1800778ff  mov     [rsp+9D0h+cbData], esi
0x180077903  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x180077908  mov     esi, eax
0x18007790a  test    eax, eax
0x18007790c  js      loc_180077FC4
0x180077912  mov     r9d, [rsp+9D0h+cbData]; cbData
0x180077917  xor     esi, esi
0x180077919  mov     r8, [rdi+18h]; pvData
0x18007791d  mov     rdx, [rsp+9D0h+tableid]; tableid
0x180077922  mov     rcx, [rsp+9D0h+sesid]; sesid
0x180077927  mov     [rsp+9D0h+var_990], esi
0x18007792b  mov     [rsp+9D0h+cbParameters], 401h; grbit
0x180077933  call    cs:__imp_JetMakeKey
0x180077939  test    eax, eax
0x18007793b  js      loc_180077F4D
0x180077941  lea     r8, [rsp+9D0h+var_990]; enum TableSeekResult *
0x180077946  lea     rcx, [rsp+9D0h+sesid]; this
0x18007794b  call    ?MaybeSeek@auto_JET_TABLEID@@QEAAJKPEAW4TableSeekResult@@@Z; auto_JET_TABLEID::MaybeSeek(ulong,TableSeekResult *)
0x180077950  test    eax, eax
0x180077952  js      loc_180077ED6
0x180077958  cmp     [rsp+9D0h+var_990], r15d
0x18007795d  jz      loc_180077B28
0x180077963  mov     r9d, [rsp+9D0h+cbData]; cbData
0x180077968  mov     r8, [rdi+18h]; pvData
0x18007796c  mov     rdx, [rsp+9D0h+tableid]; tableid
0x180077971  mov     rcx, [rsp+9D0h+sesid]; sesid
0x180077976  mov     [rsp+9D0h+var_990], esi
0x18007797a  mov     [rsp+9D0h+cbParameters], 801h; grbit
0x180077982  call    cs:__imp_JetMakeKey
0x180077988  test    eax, eax
0x18007798a  js      loc_180077E5F
0x180077990  lea     r8, [rsp+9D0h+var_990]; int *
0x180077995  lea     edx, [rsi+3]; unsigned int
0x180077998  lea     rcx, [rsp+9D0h+sesid]; this
0x18007799d  call    ?MaybeSetRange@auto_JET_TABLEID@@QEAAJKPEAH@Z; auto_JET_TABLEID::MaybeSetRange(ulong,int *)
0x1800779a2  test    eax, eax
0x1800779a4  js      loc_180077DE8
0x1800779aa  cmp     [rsp+9D0h+var_990], esi
0x1800779ae  jz      loc_180077B28
0x1800779b4  mov     rdx, [rsp+9D0h+tableid]; tableid
0x1800779b9  lea     r8, [rbp+8D0h+pretrievecolumn]; pretrievecolumn
0x1800779bd  mov     rcx, [r14+28h]; sesid
0x1800779c1  xor     eax, eax
0x1800779c3  mov     qword ptr [rbp+8D0h+var_910+0Ch], rax
0x1800779c7  mov     eax, [rbp+8D0h+var_918]
0x1800779ca  mov     [rbp+8D0h+pretrievecolumn.columnid], eax
0x1800779cd  lea     rax, [rbp+8D0h+var_910+8]
0x1800779d1  mov     [rbp+8D0h+pretrievecolumn.pvData], rax
0x1800779d5  xor     eax, eax
0x1800779d7  mov     qword ptr [rbp+8D0h+pretrievecolumn.columnidNextTagged], rax
0x1800779db  mov     dword ptr [rbp+8D0h+pretrievecolumn+2Ch], eax
0x1800779de  mov     eax, [rbp+8D0h+var_914]
0x1800779e1  mov     [rbp+8D0h+var_8C0], eax
0x1800779e4  lea     rax, [rbp+8D0h+var_910+0Ch]
0x1800779e8  mov     [rbp+8D0h+var_8B8], rax
0x1800779ec  xor     eax, eax
0x1800779ee  mov     qword ptr [rbp+8D0h+var_89C], rax
0x1800779f2  mov     [rbp+8D0h+var_894], eax
0x1800779f5  lea     rax, [rbp+8D0h+String2]
0x1800779f9  mov     [rbp+8D0h+var_888], rax
0x1800779fd  xor     eax, eax
0x1800779ff  mov     qword ptr [rbp+8D0h+var_86C], rax
0x180077a03  mov     [rbp+8D0h+var_864], eax
0x180077a06  mov     rax, r12
0x180077a09  neg     rax
0x180077a0c  mov     dword ptr [rbp+8D0h+var_910], esi
0x180077a0f  mov     [rbp-3Ch], r15
0x180077a13  sbb     r9d, r9d
0x180077a16  mov     qword ptr [rbp+8D0h+pretrievecolumn.cbData], 4
0x180077a1e  neg     r9d
0x180077a21  mov     qword ptr [rbp+8D0h+pretrievecolumn.grbit], 0
0x180077a29  add     r9d, 2; cretrievecolumn
0x180077a2d  mov     [rbp+8D0h+pretrievecolumn.itagSequence], r15d
0x180077a31  mov     [rbp+8D0h+var_8B0], 8
0x180077a39  mov     [rbp+8D0h+var_8A8], 0
0x180077a41  mov     [rbp+8D0h+var_8A0], r15d
0x180077a45  mov     [rbp+8D0h+var_890], r13d
0x180077a49  mov     [rbp+8D0h+var_880], 802h
0x180077a51  mov     [rbp+8D0h+var_878], 0
0x180077a59  mov     [rbp+8D0h+var_870], r15d
0x180077a5d  call    cs:__imp_JetRetrieveColumns
0x180077a63  test    eax, eax
0x180077a65  js      loc_180077D71
0x180077a6b  mov     ecx, [rbp+8D0h+pretrievecolumn.err]; int
0x180077a6e  test    ecx, ecx
0x180077a70  js      loc_180077CFC
0x180077a76  mov     ecx, [rbp+8D0h+var_89C+4]; int
0x180077a79  test    ecx, ecx
0x180077a7b  js      loc_180077C87
0x180077a81  test    r12, r12
0x180077a84  jz      short loc_180077ACA
0x180077a86  mov     ecx, [rbp+8D0h+var_86C+4]; int
0x180077a89  test    ecx, ecx
0x180077a8b  js      loc_180077B30
0x180077a91  mov     r8, [r14+80h]
  ... truncated ...
```
