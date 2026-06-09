# DBSession::_GetExistingIndex(unsigned __int64,ulong *,DBSession::IndexListEntry * *)

- ea: `0x1800115a0`
- end: `0x180011ec4`
- name: `?_GetExistingIndex@DBSession@@AEAAJ_KPEAKPEAPEAUIndexListEntry@1@@Z`
- size: `2340`
- prototype: `int(DBSession *__hidden this, unsigned __int64, unsigned int *, struct DBSession::IndexListEntry **)`
- caller_count: `1`
- callee_count: `22`
- tags: `file_ops, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180014010`

## callees

- `0x180002880`
- `0x1800068f0`
- `0x18000f530`
- `0x1800115a0`
- `0x180011ed0`
- `0x18001203c`
- `0x180012098`
- `0x1800120d0`
- `0x1800131c8`
- `0x180045990`
- `0x18005442c`
- `0x180067c1c`
- `0x18006f180`
- `0x180070790`
- `0x1800737b4`
- `0x180078a40`
- `0x180078a8c`
- `0x18007d4e4`
- `0x18007d540`
- `0x18007d59c`
- `0x1800c50aa`
- `0x1800c50f0`

## import_xrefs

- `msvcrt!strtoul` at `0x1800118cf`
- `msvcrt!strtoul` at `0x180011ae0`
- `msvcrt!strtoul` at `0x180011c82`
- `msvcrt!strtoul` at `0x1800118cf`
- `msvcrt!strtoul` at `0x180011ae0`
- `msvcrt!strtoul` at `0x180011c82`
- `ESENT!JetMove` at `0x180011b1e`
- `ESENT!JetMove` at `0x180011b92`
- `ESENT!JetMove` at `0x180011b1e`
- `ESENT!JetMove` at `0x180011b92`
- `ESENT!JetGetTableIndexInfoA` at `0x1800115f7`
- `ESENT!JetGetTableIndexInfoA` at `0x180011640`
- `ESENT!JetGetTableIndexInfoA` at `0x180011b5a`
- `ESENT!JetGetTableIndexInfoA` at `0x1800115f7`
- `ESENT!JetGetTableIndexInfoA` at `0x180011640`
- `ESENT!JetGetTableIndexInfoA` at `0x180011b5a`
- `ESENT!JetRetrieveColumns` at `0x180011889`
- `ESENT!JetRetrieveColumns` at `0x18001199b`
- `ESENT!JetRetrieveColumns` at `0x180011889`
- `ESENT!JetRetrieveColumns` at `0x18001199b`
- `ESENT!JetGetErrorInfoW` at `0x180011a2f`
- `ESENT!JetGetErrorInfoW` at `0x180011a2f`

## string_xrefs

- `0x180011d5b`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\dbmanager.cpp`
- `0x180011d93`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\dbmanager.cpp`
- `0x1800116c2`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\dbsession.cpp`
- `0x180011dd6`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\dbsession.cpp`
- `0x180011e35`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\dbsession.cpp`
- `0x180011c4c`: `onecoreuap\base\AppModel\UserDataAccess\PublishedInternal\Inc\jetinterop.h`
- `0x180011e16`: `onecoreuap\base\AppModel\UserDataAccess\PublishedInternal\Inc\jetinterop.h`
- `0x180011e6d`: `onecoreuap\base\AppModel\UserDataAccess\PublishedInternal\Inc\jetinterop.h`

## pseudocode

```c
__int64 __fastcall DBSession::_GetExistingIndex(
        DBSession *this,
        JET_TABLEID a2,
        unsigned int *a3,
        struct DBSession::IndexListEntry **a4)
{
  JET_ERR TableIndexInfoA; // ebx
  JET_ERR v8; // ebx
  unsigned __int64 v9; // rbx
  __int64 v10; // rax
  bool v11; // cf
  unsigned __int64 v12; // rax
  unsigned __int64 *v13; // rax
  __int64 v14; // rsi
  DBSession::IndexListEntry *i; // rdi
  int v16; // eax
  void *v18; // rdi
  unsigned int v19; // r9d
  unsigned __int64 v20; // rcx
  __int64 v21; // r14
  JET_ERR v22; // ebx
  int v23; // eax
  __int64 v24; // r14
  JET_SESID v25; // rcx
  JET_ERR v26; // r15d
  unsigned int v27; // eax
  _QWORD *v28; // rdx
  _QWORD *v29; // rcx
  __int64 v30; // r12
  __int64 *v31; // r15
  __int64 v32; // rax
  __int64 v33; // r14
  unsigned __int64 v34; // r12
  _QWORD *v35; // r12
  __int64 v36; // r14
  unsigned int v37; // eax
  __int64 v38; // r8
  __int64 v39; // r9
  JET_SESID v40; // rcx
  JET_ERR Columns; // eax
  int v42; // ebx
  unsigned int v43; // ebx
  int *v44; // rbx
  __int64 j; // r15
  unsigned int v46; // r14d
  JET_ERR v47; // r14d
  unsigned int v48; // eax
  __int64 v49; // r8
  __int64 v50; // r9
  int v51; // eax
  unsigned int v52; // eax
  __int64 v53; // rax
  __int64 v54; // r8
  int v55; // eax
  __int64 v56; // rcx
  unsigned int v57; // eax
  unsigned int v58; // eax
  __int64 v59; // rbx
  __int64 v60; // r8
  __int64 HresultFromJetError; // rbx
  __int64 v62; // r8
  JET_ERR v63; // [rsp+30h] [rbp-D0h] BYREF
  JET_ERR v64; // [rsp+38h] [rbp-C8h] BYREF
  unsigned int v65; // [rsp+3Ch] [rbp-C4h] BYREF
  _QWORD v66[2]; // [rsp+40h] [rbp-C0h] BYREF
  int v67; // [rsp+50h] [rbp-B0h] BYREF
  _QWORD *v68; // [rsp+58h] [rbp-A8h]
  JET_TABLEID v69; // [rsp+60h] [rbp-A0h]
  struct DBSession::IndexListEntry **v70; // [rsp+68h] [rbp-98h]
  _BYTE v71[56]; // [rsp+70h] [rbp-90h] BYREF
  int *v72; // [rsp+A8h] [rbp-58h]
  __int64 v73; // [rsp+B0h] [rbp-50h]
  __int128 v74; // [rsp+B8h] [rbp-48h]
  int v75[2]; // [rsp+C8h] [rbp-38h]
  char pvResult[8]; // [rsp+D0h] [rbp-30h] BYREF
  JET_TABLEID tableid; // [rsp+D8h] [rbp-28h]
  JET_COLUMNID v78; // [rsp+E4h] [rbp-1Ch]
  int v79; // [rsp+E8h] [rbp-18h]
  int v80; // [rsp+F8h] [rbp-8h]
  int v81; // [rsp+10Ch] [rbp+Ch]
  int v82; // [rsp+118h] [rbp+18h]
  int v83; // [rsp+11Ch] [rbp+1Ch]
  int v84; // [rsp+120h] [rbp+20h]
  int v85; // [rsp+130h] [rbp+30h] BYREF
  __int128 v86; // [rsp+134h] [rbp+34h]
  __int128 v87; // [rsp+144h] [rbp+44h]
  __int128 v88; // [rsp+154h] [rbp+54h]
  __int128 v89; // [rsp+164h] [rbp+64h]
  __int128 v90; // [rsp+174h] [rbp+74h]
  __int128 v91; // [rsp+184h] [rbp+84h]
  __int128 v92; // [rsp+194h] [rbp+94h]
  __int128 v93; // [rsp+1A4h] [rbp+A4h]
  __int128 v94; // [rsp+1B4h] [rbp+B4h]
  int v95; // [rsp+1C4h] [rbp+C4h]
  JET_RETRIEVECOLUMN pretrievecolumn; // [rsp+1D0h] [rbp+D0h] BYREF
  int v97; // [rsp+200h] [rbp+100h]
  __int64 v98; // [rsp+208h] [rbp+108h]
  int v99; // [rsp+210h] [rbp+110h]
  int v100; // [rsp+220h] [rbp+120h]
  int v101; // [rsp+230h] [rbp+130h]
  __int64 v102; // [rsp+238h] [rbp+138h]
  int v103; // [rsp+240h] [rbp+140h]
  int v104; // [rsp+250h] [rbp+150h]
  int v105; // [rsp+260h] [rbp+160h]
  __int64 v106; // [rsp+268h] [rbp+168h]
  int v107; // [rsp+270h] [rbp+170h]
  int v108; // [rsp+280h] [rbp+180h]
  int v109; // [rsp+290h] [rbp+190h]
  unsigned int *v110; // [rsp+298h] [rbp+198h]
  int v111; // [rsp+2A0h] [rbp+1A0h]
  int v112; // [rsp+2B0h] [rbp+1B0h]
  int v113; // [rsp+2B8h] [rbp+1B8h]
  char String[16]; // [rsp+2C0h] [rbp+1C0h] BYREF
  char v115[16]; // [rsp+2D0h] [rbp+1D0h] BYREF

  v70 = a4;
  v69 = a2;
  TableIndexInfoA = JetGetTableIndexInfoA(*((_QWORD *)this + 27), a2, 0, a3, 4u, 7u);
  CheckCorruption(TableIndexInfoA);
  if ( TableIndexInfoA < 0 )
  {
    HresultFromJetError = (unsigned int)MakeHresultFromJetError(TableIndexInfoA);
    Log_HREventPersist(HresultFromJetError, 0, v62, 423);
    return (unsigned int)HresultFromJetError;
  }
  memset_0(pvResult, 0, 0x58u);
  v8 = JetGetTableIndexInfoA(*((_QWORD *)this + 27), a2, 0, pvResult, 0x58u, 1u);
  CheckCorruption(v8);
  if ( v8 < 0 )
  {
    v59 = (unsigned int)MakeHresultFromJetError(v8);
    Log_HREventPersist(v59, 0, v60, 432);
    return (unsigned int)v59;
  }
  v9 = *a3;
  v66[0] = *((_QWORD *)this + 27);
  v66[1] = tableid;
  v10 = 48 * v9;
  if ( !is_mul_ok(v9, 0x30u) )
    v10 = -1;
  v11 = __CFADD__(v10, 8);
  v12 = v10 + 8;
  if ( v11 )
    v12 = -1;
  v13 = (unsigned __int64 *)operator new[](v12);
  if ( !v13 )
    goto LABEL_11;
  *v13 = v9;
  v14 = (__int64)(v13 + 1);
  for ( i = (DBSession::IndexListEntry *)(v13 + 1); v9; --v9 )
  {
    DBSession::IndexListEntry::IndexListEntry(i);
    i = (DBSession::IndexListEntry *)((char *)i + 48);
  }
  if ( !v14 )
  {
LABEL_11:
    Log_UnistoreHREvent_0(
      2147942414LL,
      0,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\dbsession.cpp",
      437);
    v16 = auto_JET_TABLEID::close((auto_JET_TABLEID *)v66);
    if ( v16 < 0 )
    {
      v58 = MakeHresultFromJetError(v16);
      Log_UnistoreHREvent_0(
        v58,
        0,
        "onecoreuap\\base\\AppModel\\UserDataAccess\\PublishedInternal\\Inc\\jetinterop.h",
        261);
    }
    return 2147942414LL;
  }
  v18 = operator new[](0xA5Eu);
  if ( !v18 )
  {
    Log_UnistoreHREvent_0(
      2147942414LL,
      0,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\dbsession.cpp",
      450);
    tlx::_delete_array<DBSession::IndexListEntry>(v14);
    auto_JET_TABLEID::~auto_JET_TABLEID((auto_JET_TABLEID *)v66);
    return 2147942414LL;
  }
  v20 = *((_QWORD *)this + 27);
  v21 = 0;
  v64 = 0;
  v22 = CommsESE_JetMove(v20, tableid, 0x80000000, v19);
LABEL_16:
  if ( !v22 )
  {
    v24 = v14 + 48 * v21;
    *(_OWORD *)v24 = 0;
    *(_OWORD *)(v24 + 16) = 0;
    *(_OWORD *)(v24 + 32) = 0;
    memset_0(&pretrievecolumn.pvData, 0, 0xE8u);
    v25 = *((_QWORD *)this + 27);
    pretrievecolumn.columnid = v78;
    pretrievecolumn.pvData = String;
    v97 = v81;
    v98 = v24 + 8;
    v101 = v79;
    v102 = v24 + 12;
    v105 = v84;
    v106 = v24 + 16;
    v109 = v80;
    v110 = &v65;
    pretrievecolumn.cbData = 9;
    pretrievecolumn.itagSequence = 1;
    v99 = 4;
    v100 = 1;
    v103 = 4;
    v104 = 1;
    v107 = 4;
    v108 = 1;
    v65 = 0;
    v111 = 4;
    v112 = 1;
    v26 = JetRetrieveColumns(v25, tableid, &pretrievecolumn, 5u);
    CheckCorruption(v26);
    if ( v26 < 0 )
    {
      v48 = MakeHresultFromJetError(v26);
      v50 = 510;
    }
    else
    {
      if ( pretrievecolumn.err )
      {
        v37 = MakeHresultFromJetError(pretrievecolumn.err);
        v39 = 514;
        goto LABEL_32;
      }
      if ( !v113 )
      {
        String[8] = 0;
        v27 = strtoul(String, 0, 16);
        v29 = (_QWORD *)(v24 + 24);
        *(_DWORD *)(v24 + 4) = v27;
        v30 = *(_QWORD *)(v24 + 32);
        v31 = (__int64 *)(v24 + 32);
        v32 = *(_QWORD *)(v24 + 24);
        v33 = v65;
        v34 = (v30 - v32) >> 4;
        v68 = v29;
        if ( v65 > v34 )
        {
          if ( !(unsigned __int8)utl::vector<DBSession::IndexColumnInfo,utl::allocator<DBSession::IndexColumnInfo>>::reserve(
                                   v29,
                                   v65) )
          {
            Log_UnistoreHREvent_0(
              2147942414LL,
              0,
              "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\dbsession.cpp",
              523);
            operator delete(v18);
            tlx::_delete_array<DBSession::IndexListEntry>(v14);
            auto_JET_TABLEID::~auto_JET_TABLEID((auto_JET_TABLEID *)v66);
            return 2147942414LL;
          }
          v54 = *v31;
          v29 = 0;
          v28 = (_QWORD *)(v33 - v34);
          while ( v29 != v28 )
          {
            v53 = 2LL * (_QWORD)v29;
            v29 = (_QWORD *)((char *)v29 + 1);
            *(_QWORD *)(v54 + 8 * v53) = 1;
            *(_QWORD *)(v54 + 8 * v53 + 8) = 0;
          }
          v35 = v68;
          v36 = *v68 + 16 * v33;
        }
        else
        {
          v35 = v29;
          v36 = v32 + 16LL * v65;
        }
        *v31 = v36;
        if ( !v65 )
          Log_AssertionEvent_3(v29, v28, 525);
        v47 = JetGetTableIndexInfoA(*((_QWORD *)this + 27), v69, String, v18, 0xA5Eu, 0xBu);
        CheckCorruption(v47);
        if ( v47 >= 0 )
        {
          v46 = 0;
          while ( 1 )
          {
            if ( v22 )
            {
LABEL_44:
              v22 = JetMove(*((_QWORD *)this + 27), tableid, 1, 0);
              CheckCorruption(v22);
              v21 = (unsigned int)++v64;
              goto LABEL_16;
            }
            v40 = *((_QWORD *)this + 27);
            *(_QWORD *)v75 = 0;
            *(_DWORD *)v71 = v83;
            memset(&v71[20], 0, 36);
            *(_QWORD *)&v71[8] = v115;
            *(_DWORD *)&v71[16] = 9;
            *(_DWORD *)&v71[48] = v82;
            v72 = &v67;
            v74 = 0;
            *(_DWORD *)&v71[32] = 1;
            v67 = 0;
            v73 = 4;
            DWORD2(v74) = 1;
            Columns = JetRetrieveColumns(v40, tableid, (JET_RETRIEVECOLUMN *)v71, 2u);
            v42 = Columns;
            if ( g_fInProc && !dword_18010D924 )
            {
              if ( Columns != -1414 )
              {
                v63 = Columns;
                if ( Columns >= 0 )
                  goto LABEL_35;
                v85 = 152;
                v95 = 0;
                v86 = 0;
                v87 = 0;
                v88 = 0;
                v89 = 0;
                v90 = 0;
                v91 = 0;
                v92 = 0;
                v93 = 0;
                v94 = 0;
                if ( (int)JetGetErrorInfoW(&v63, &v85, 152, 1, 0) < 0 )
                  goto LABEL_31;
                if ( DWORD1(v86) != 10 )
                {
                  if ( DWORD1(v86) == 11 )
                  {
                    v64 = v63;
                    UnistoreTelemetry::JetInconsistentError<unsigned long>(&v64);
                  }
                  else if ( DWORD1(v86) == 12 )
                  {
                    v64 = v63;
                    UnistoreTelemetry::JetFragmentationError<unsigned long>(&v64);
                  }
LABEL_31:
                  v37 = MakeHresultFromJetError(v42);
                  v39 = 566;
                  goto LABEL_32;
                }
                if ( v63 == -1414 )
                  goto LABEL_31;
              }
              v55 = RegistrySetDWORD(HKEY_CURRENT_USER, L"Software\\Microsoft\\Unified Store", L"CorruptReason", v42);
              if ( v55 >= 0 )
              {
                v63 = v42;
                UnistoreTelemetry::MarkStoreCorruption<unsigned long>(&v63);
                if ( (unsigned int)IsJetCorruptionError(v42) )
                {
                  Log_AssertionEvent(
                    v56,
                    "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\dbmanager.cpp",
                    109);
                  __int2c();
                }
              }
              else
              {
                Log_UnistoreHREvent_0(
                  (unsigned int)v55,
                  0,
                  "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\dbmanager.cpp",
                  102);
              }
            }
            if ( v42 < 0 )
              goto LABEL_31;
LABEL_35:
            if ( *(_DWORD *)&v71[40] )
            {
              v37 = MakeHresultFromJetError(*(int *)&v71[40]);
              v39 = 570;
              goto LABEL_32;
            }
            if ( v75[0] )
            {
              v37 = MakeHresultFromJetError(v75[0]);
              v39 = 574;
              goto LABEL_32;
            }
            v115[8] = 0;
            v44 = (int *)(*v35 + 16LL * v46);
            v44[1] = strtoul(v115, 0, 16);
            *v44 = v67 & 1;
            for ( j = 0; (unsigned int)j < *((_DWORD *)v18 + 16); j = (unsigned int)(j + 1) )
            {
              if ( strtoul(*(const char **)(24 * j + *((_QWORD *)v18 + 7) + 8), 0, 16) == v44[1] )
              {
                v44[2] = 1;
                v44[3] = *(_DWORD *)(24 * j + *((_QWORD *)v18 + 7) + 16);
                break;
              }
            }
            if ( ++v46 == v65 )
              goto LABEL_44;
            v22 = JetMove(*((_QWORD *)this + 27), tableid, 1, 0);
            CheckCorruption(v22);
            v35 = v68;
          }
        }
        v37 = MakeHresultFromJetError(v47);
        v39 = 535;
LABEL_32:
        v43 = v37;
        Log_HREventPersist(v37, 0, v38, v39);
        operator delete(v18);
        tlx::_delete_array<DBSession::IndexListEntry>(v14);
        auto_JET_TABLEID::~auto_JET_TABLEID((auto_JET_TABLEID *)v66);
        return v43;
      }
      v48 = MakeHresultFromJetError(v113);
      v50 = 518;
    }
    v43 = v48;
    Log_HREventPersist(v48, 0, v49, v50);
    operator delete(v18);
    tlx::_delete_array<DBSession::IndexListEntry>(v14);
    v51 = auto_JET_TABLEID::close((auto_JET_TABLEID *)v66);
    if ( v51 < 0 )
    {
      v52 = MakeHresultFromJetError(v51);
      Log_UnistoreHREvent_0(
        v52,
        0,
        "onecoreuap\\base\\AppModel\\UserDataAccess\\PublishedInternal\\Inc\\jetinterop.h",
        261);
    }
    return v43;
  }
  *v70 = (struct DBSession::IndexListEntry *)v14;
  operator delete(v18);
  v23 = auto_JET_TABLEID::close((auto_JET_TABLEID *)v66);
  if ( v23 < 0 )
  {
    v57 = MakeHresultFromJetError(v23);
    Log_UnistoreHREvent_0(
      v57,
      0,
      "onecoreuap\\base\\AppModel\\UserDataAccess\\PublishedInternal\\Inc\\jetinterop.h",
      261);
  }
  return 0;
}

```

## disassembly

```asm
0x1800115a0  push    rbp
0x1800115a2  push    rbx
0x1800115a3  push    rsi
0x1800115a4  push    rdi
0x1800115a5  push    r13
0x1800115a7  lea     rbp, [rsp-210h]
0x1800115af  sub     rsp, 310h
0x1800115b6  mov     rax, cs:__security_cookie
0x1800115bd  xor     rax, rsp
0x1800115c0  mov     [rbp+230h+var_50], rax
0x1800115c7  mov     [rsp+330h+var_2C8], r9
0x1800115cc  mov     rdi, r8
0x1800115cf  mov     r9, r8; pvResult
0x1800115d2  mov     [rsp+330h+InfoLevel], 7; InfoLevel
0x1800115da  mov     r13, rcx
0x1800115dd  mov     [rsp+330h+var_2D0], rdx
0x1800115e2  mov     rcx, [rcx+0D8h]; sesid
0x1800115e9  xor     r8d, r8d; szIndexName
0x1800115ec  mov     rsi, rdx
0x1800115ef  mov     [rsp+330h+cbResult], 4; cbResult
0x1800115f7  call    cs:__imp_JetGetTableIndexInfoA
0x1800115fd  mov     ecx, eax; int
0x1800115ff  mov     ebx, eax
0x180011601  call    ?CheckCorruption@@YAXJ@Z; CheckCorruption(long)
0x180011606  test    ebx, ebx
0x180011608  js      loc_180011EA5
0x18001160e  xor     edx, edx; Val
0x180011610  lea     rcx, [rbp+230h+pvResult]; void *
0x180011614  mov     r8d, 58h ; 'X'; Size
0x18001161a  call    memset_0
0x18001161f  mov     rcx, [r13+0D8h]; sesid
0x180011626  lea     r9, [rbp+230h+pvResult]; pvResult
0x18001162a  xor     r8d, r8d; szIndexName
0x18001162d  mov     [rsp+330h+InfoLevel], 1; InfoLevel
0x180011635  mov     rdx, rsi; tableid
0x180011638  mov     [rsp+330h+cbResult], 58h ; 'X'; cbResult
0x180011640  call    cs:__imp_JetGetTableIndexInfoA
0x180011646  mov     ecx, eax; int
0x180011648  mov     ebx, eax
0x18001164a  call    ?CheckCorruption@@YAXJ@Z; CheckCorruption(long)
0x18001164f  test    ebx, ebx
0x180011651  js      loc_180011E86
0x180011657  mov     rax, [r13+0D8h]
0x18001165e  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180011665  mov     ebx, [rdi]
0x180011667  mov     [rsp+330h+var_2F0], rax
0x18001166c  mov     rax, [rbp+230h+tableid]
0x180011670  mov     [rsp+330h+var_2E8], rax
0x180011675  mov     eax, 30h ; '0'
0x18001167a  mul     rbx
0x18001167d  cmovb   rax, rcx
0x180011681  add     rax, 8
0x180011685  cmovb   rax, rcx
0x180011689  mov     rcx, rax; unsigned __int64
0x18001168c  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180011691  test    rax, rax
0x180011694  jz      short loc_1800116BC
0x180011696  mov     [rax], rbx
0x180011699  lea     rsi, [rax+8]
0x18001169d  mov     rdi, rsi
0x1800116a0  test    rbx, rbx
0x1800116a3  jz      short loc_1800116B7
0x1800116a5  mov     rcx, rdi; this
0x1800116a8  call    ??0IndexListEntry@DBSession@@QEAA@XZ; DBSession::IndexListEntry::IndexListEntry(void)
0x1800116ad  add     rdi, 30h ; '0'
0x1800116b1  sub     rbx, 1
0x1800116b5  jnz     short loc_1800116A5
0x1800116b7  test    rsi, rsi
0x1800116ba  jnz     short loc_1800116F1
0x1800116bc  mov     r9d, 1B5h
0x1800116c2  lea     r8, aOnecoreuapBase_29; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800116c9  xor     edx, edx
0x1800116cb  mov     ecx, 8007000Eh
0x1800116d0  call    Log_UnistoreHREvent_0
0x1800116d5  lea     rcx, [rsp+330h+var_2F0]; this
0x1800116da  call    ?close@auto_JET_TABLEID@@QEAAJXZ; auto_JET_TABLEID::close(void)
0x1800116df  test    eax, eax
0x1800116e1  js      loc_180011E64
0x1800116e7  mov     eax, 8007000Eh
0x1800116ec  jmp     loc_180011A89
0x1800116f1  mov     ecx, 0A5Eh; unsigned __int64
0x1800116f6  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800116fb  mov     rdi, rax
0x1800116fe  test    rax, rax
0x180011701  jz      loc_180011E2F
0x180011707  mov     rdx, [rbp+230h+tableid]; unsigned __int64
0x18001170b  mov     r8d, 80000000h; int
0x180011711  mov     rcx, [r13+0D8h]; unsigned __int64
0x180011718  mov     [rsp+330h+var_28], r12
0x180011720  mov     [rsp+330h+var_30], r14
0x180011728  xor     r14d, r14d
0x18001172b  mov     [rsp+330h+var_2F8], r14d
0x180011730  mov     [rsp+330h+var_38], r15
0x180011738  call    ?CommsESE_JetMove@@YAJ_K0JK@Z; CommsESE_JetMove(unsigned __int64,unsigned __int64,long,ulong)
0x18001173d  mov     ebx, eax
0x18001173f  nop
0x180011740  test    ebx, ebx
0x180011742  jz      short loc_18001176D
0x180011744  mov     rax, [rsp+330h+var_2C8]
0x180011749  mov     rcx, rdi; Block
0x18001174c  mov     [rax], rsi
0x18001174f  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180011754  lea     rcx, [rsp+330h+var_2F0]; this
0x180011759  call    ?close@auto_JET_TABLEID@@QEAAJXZ; auto_JET_TABLEID::close(void)
0x18001175e  test    eax, eax
0x180011760  js      loc_180011E0D
0x180011766  xor     eax, eax
0x180011768  jmp     loc_180011A71
0x18001176d  xorps   xmm0, xmm0
0x180011770  lea     r14, [r14+r14*2]
0x180011774  shl     r14, 4
0x180011778  lea     rcx, [rbp+230h+pretrievecolumn.pvData]; void *
0x18001177f  add     r14, rsi
0x180011782  xor     edx, edx; Val
0x180011784  mov     r8d, 0E8h; Size
0x18001178a  movups  xmmword ptr [r14], xmm0
0x18001178e  movups  xmmword ptr [r14+10h], xmm0
0x180011793  movups  xmmword ptr [r14+20h], xmm0
0x180011798  call    memset_0
0x18001179d  mov     eax, [rbp+230h+var_24C]
0x1800117a0  lea     r8, [rbp+230h+pretrievecolumn]; pretrievecolumn
0x1800117a7  mov     rdx, [rbp+230h+tableid]; tableid
0x1800117ab  mov     r9d, 5; cretrievecolumn
0x1800117b1  mov     rcx, [r13+0D8h]; sesid
0x1800117b8  mov     [rbp+230h+pretrievecolumn.columnid], eax
0x1800117be  lea     rax, [rbp+230h+String]
0x1800117c5  mov     [rbp+230h+pretrievecolumn.pvData], rax
0x1800117cc  mov     eax, [rbp+230h+var_224]
0x1800117cf  mov     [rbp+230h+var_130], eax
0x1800117d5  lea     rax, [r14+8]
0x1800117d9  mov     [rbp+230h+var_128], rax
0x1800117e0  mov     eax, [rbp+230h+var_248]
0x1800117e3  mov     [rbp+230h+var_100], eax
0x1800117e9  lea     rax, [r14+0Ch]
0x1800117ed  mov     [rbp+230h+var_F8], rax
0x1800117f4  mov     eax, [rbp+230h+var_210]
0x1800117f7  mov     [rbp+230h+var_D0], eax
0x1800117fd  lea     rax, [r14+10h]
0x180011801  mov     [rbp+230h+var_C8], rax
0x180011808  mov     eax, [rbp+230h+var_238]
0x18001180b  mov     [rbp+230h+var_A0], eax
0x180011811  lea     rax, [rsp+330h+var_2F4]
0x180011816  mov     [rbp+230h+var_98], rax
0x18001181d  mov     [rbp+230h+pretrievecolumn.cbData], 9
0x180011827  mov     [rbp+230h+pretrievecolumn.itagSequence], 1
0x180011831  mov     [rbp+230h+var_120], 4
0x18001183b  mov     [rbp+230h+var_110], 1
0x180011845  mov     [rbp+230h+var_F0], 4
0x18001184f  mov     [rbp+230h+var_E0], 1
0x180011859  mov     [rbp+230h+var_C0], 4
0x180011863  mov     [rbp+230h+var_B0], 1
0x18001186d  mov     [rsp+330h+var_2F4], 0
0x180011875  mov     [rbp+230h+var_90], 4
0x18001187f  mov     [rbp+230h+var_80], 1
0x180011889  call    cs:__imp_JetRetrieveColumns
0x18001188f  mov     ecx, eax; int
0x180011891  mov     r15d, eax
0x180011894  call    ?CheckCorruption@@YAXJ@Z; CheckCorruption(long)
0x180011899  test    r15d, r15d
0x18001189c  js      loc_180011C08
0x1800118a2  mov     ecx, [rbp+230h+pretrievecolumn.err]; int
0x1800118a8  test    ecx, ecx
0x1800118aa  jnz     short loc_180011911
0x1800118ac  mov     ecx, [rbp+230h+var_78]; int
0x1800118b2  test    ecx, ecx
0x1800118b4  jnz     loc_180011CAD
0x1800118ba  mov     [rbp+230h+var_68], cl
0x1800118c0  xor     edx, edx; EndPtr
0x1800118c2  lea     rcx, [rbp+230h+String]; String
0x1800118c9  mov     r8d, 10h; Radix
0x1800118cf  call    cs:__imp_strtoul
0x1800118d5  lea     rcx, [r14+18h]
0x1800118d9  mov     [r14+4], eax
0x1800118dd  mov     r12, [rcx+8]
0x1800118e1  lea     r15, [rcx+8]
0x1800118e5  mov     rax, [rcx]
0x1800118e8  mov     r14d, [rsp+330h+var_2F4]
0x1800118ed  sub     r12, rax
0x1800118f0  sar     r12, 4
0x1800118f4  mov     [rsp+330h+var_2D8], rcx
0x1800118f9  cmp     r14, r12
0x1800118fc  ja      loc_180011D09
0x180011902  shl     r14, 4
0x180011906  mov     r12, rcx
0x180011909  add     r14, rax
0x18001190c  jmp     loc_180011CCA
0x180011911  call    ?MakeHresultFromJetError@@YAJJ@Z; MakeHresultFromJetError(long)
0x180011916  mov     r9d, 202h
0x18001191c  jmp     loc_180011A4A
0x180011921  mov     rdx, [rbp+230h+tableid]; tableid
0x180011925  lea     r8, [rsp+330h+var_2C0]; pretrievecolumn
0x18001192a  mov     rcx, [r13+0D8h]; sesid
0x180011931  xor     eax, eax
0x180011933  xorps   xmm0, xmm0
0x180011936  mov     qword ptr [rbp+230h+var_268], rax
0x18001193a  mov     eax, [rbp+230h+var_214]
0x18001193d  mov     r9d, 2; cretrievecolumn
0x180011943  mov     dword ptr [rsp+330h+var_2C0], eax
0x180011947  lea     rax, [rbp+230h+var_60]
0x18001194e  movups  xmmword ptr [rsp+330h+var_2C0+8], xmm0
0x180011953  mov     qword ptr [rsp+330h+var_2C0+8], rax
0x180011958  mov     eax, [rbp+230h+var_218]
0x18001195b  movups  [rbp+230h+var_288], xmm0
0x18001195f  mov     dword ptr [rbp+230h+var_2C0+10h], 9
0x180011966  movups  xmmword ptr [rbp+230h+var_2C0+28h], xmm0
0x18001196a  mov     dword ptr [rbp+230h+var_2C0+30h], eax
0x18001196d  lea     rax, [rsp+330h+var_2E0]
0x180011972  movups  xmmword ptr [rbp+230h+var_2C0+18h], xmm0
0x180011976  mov     qword ptr [rbp+230h+var_288], rax
0x18001197a  movups  [rbp+230h+var_278], xmm0
0x18001197e  mov     dword ptr [rbp+230h+var_2C0+20h], 1
0x180011985  mov     [rsp+330h+var_2E0], 0
0x18001198d  mov     dword ptr [rbp+230h+var_288+8], 4
0x180011994  mov     dword ptr [rbp+230h+var_278+8], 1
0x18001199b  call    cs:__imp_JetRetrieveColumns
0x1800119a1  cmp     cs:?g_fInProc@@3HA, 0; int g_fInProc
0x1800119a8  mov     ebx, eax
0x1800119aa  jz      loc_180011AA6
0x1800119b0  cmp     cs:dword_18010D924, 0
0x1800119b7  jnz     loc_180011AA6
0x1800119bd  cmp     eax, 0FFFFFA7Ah
0x1800119c2  jz      loc_180011D34
0x1800119c8  mov     [rsp+330h+var_300], eax
0x1800119cc  test    eax, eax
0x1800119ce  jns     loc_180011AAA
0x1800119d4  xorps   xmm0, xmm0
0x1800119d7  mov     [rbp+230h+var_200], 98h
0x1800119de  xor     eax, eax
0x1800119e0  lea     rdx, [rbp+230h+var_200]
0x1800119e4  mov     r9d, 1
0x1800119ea  mov     [rbp+230h+var_16C], eax
0x1800119f0  mov     r8d, 98h
0x1800119f6  mov     [rsp+330h+cbResult], eax
0x1800119fa  lea     rcx, [rsp+330h+var_300]
0x1800119ff  movups  [rbp+230h+var_1FC], xmm0
0x180011a03  movups  [rbp+230h+var_1EC], xmm0
0x180011a07  movups  [rbp+230h+var_1DC], xmm0
0x180011a0b  movups  [rbp+230h+var_1CC], xmm0
0x180011a0f  movups  [rbp+230h+var_1BC], xmm0
0x180011a13  movups  [rbp+230h+var_1AC], xmm0
0x180011a1a  movups  [rbp+230h+var_19C], xmm0
0x180011a21  movups  [rbp+230h+var_18C], xmm0
0x180011a28  movups  [rbp+230h+var_17C], xmm0
0x180011a2f  call    cs:__imp_JetGetErrorInfoW
0x180011a35  test    eax, eax
0x180011a37  jns     loc_180011BD3
0x180011a3d  mov     ecx, ebx; int
0x180011a3f  call    ?MakeHresultFromJetError@@YAJJ@Z; MakeHresultFromJetError(long)
0x180011a44  mov     r9d, 236h
0x180011a4a  xor     edx, edx
0x180011a4c  mov     ecx, eax
0x180011a4e  mov     ebx, eax
0x180011a50  call    Log_HREventPersist
0x180011a55  mov     rcx, rdi; Block
0x180011a58  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180011a5d  mov     rcx, rsi
0x180011a60  call    ??$_delete_array@UIndexListEntry@DBSession@@@tlx@@YAXPEAUIndexListEntry@DBSession@@@Z; tlx::_delete_array<DBSession::IndexListEntry>(DBSession::IndexListEntry *)
0x180011a65  lea     rcx, [rsp+330h+var_2F0]; this
0x180011a6a  call    ??1auto_JET_TABLEID@@QEAA@XZ; auto_JET_TABLEID::~auto_JET_TABLEID(void)
0x180011a6f  mov     eax, ebx
0x180011a71  mov     r14, [rsp+330h+var_30]
0x180011a79  mov     r12, [rsp+330h+var_28]
0x180011a81  mov     r15, [rsp+330h+var_38]
0x180011a89  mov     rcx, [rbp+230h+var_50]
0x180011a90  xor     rcx, rsp; StackCookie
0x180011a93  call    __security_check_cookie
0x180011a98  add     rsp, 310h
0x180011a9f  pop     r13
0x180011aa1  pop     rdi
0x180011aa2  pop     rsi
0x180011aa3  pop     rbx
0x180011aa4  pop     rbp
0x180011aa5  retn
0x180011aa6  test    ebx, ebx
0x180011aa8  js      short loc_180011A3D
0x180011aaa  mov     ecx, dword ptr [rbp+230h+var_2C0+28h]; int
0x180011aad  test    ecx, ecx
0x180011aaf  jnz     loc_180011BC3
0x180011ab5  mov     ecx, [rbp+230h+var_268]; int
0x180011ab8  test    ecx, ecx
0x180011aba  jnz     loc_180011BB3
0x180011ac0  mov     [rbp+230h+var_58], cl
0x180011ac6  xor     edx, edx; EndPtr
0x180011ac8  mov     ebx, r14d
0x180011acb  lea     rcx, [rbp+230h+var_60]; String
0x180011ad2  shl     rbx, 4
0x180011ad6  mov     r8d, 10h; Radix
0x180011adc  add     rbx, [r12]
0x180011ae0  call    cs:__imp_strtoul
0x180011ae6  mov     [rbx+4], eax
0x180011ae9  movzx   eax, byte ptr [rsp+330h+var_2E0]
0x180011aee  and     eax, 1
0x180011af1  mov     [rbx], eax
0x180011af3  xor     r15d, r15d
0x180011af6  cmp     r15d, [rdi+40h]
0x180011afa  jb      loc_180011C65
0x180011b00  inc     r14d
0x180011b03  cmp     r14d, [rsp+330h+var_2F4]
0x180011b08  jz      short loc_180011B7E
0x180011b0a  mov     rdx, [rbp+230h+tableid]; tableid
  ... truncated ...
```
