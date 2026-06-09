# DatabaseVolumeSession::AttachDatabaseToSession(DatabaseDefinition const *,unsigned __int64,ulong *,int)

- ea: `0x18003c364`
- end: `0x18003cd9c`
- name: `?AttachDatabaseToSession@DatabaseVolumeSession@@QEAAJPEBUDatabaseDefinition@@_KPEAKH@Z`
- size: `2616`
- prototype: `__int64 __fastcall(DatabaseVolumeSession *__hidden this, const struct DatabaseDefinition *, unsigned __int64, unsigned int *, int)`
- caller_count: `2`
- callee_count: `24`
- tags: `file_ops, authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x1800627bc`
- `0x1800e0870`

## callees

- `0x1800049f0`
- `0x1800083d8`
- `0x180008f0c`
- `0x18000e1f8`
- `0x18003b794`
- `0x18003b8c8`
- `0x18003bf04`
- `0x18003bf84`
- `0x18003c364`
- `0x18003e3e4`
- `0x18005e048`
- `0x180066070`
- `0x18006a908`
- `0x18006c5b8`
- `0x180076664`
- `0x180078214`
- `0x18007ecd8`
- `0x18008437c`
- `0x1800977ac`
- `0x18009e374`
- `0x18009e468`
- `0x1800a41b4`
- `0x18012c76a`
- `0x18012c7b0`

## import_xrefs

- `ESENT!JetAddColumnA` at `0x18003ca54`
- `ESENT!JetAddColumnA` at `0x18003ca54`
- `ESENT!JetOpenTableA` at `0x18003c5bd`
- `ESENT!JetOpenTableA` at `0x18003c5bd`
- `ESENT!JetOpenDatabaseW` at `0x18003c4c5`
- `ESENT!JetOpenDatabaseW` at `0x18003c4c5`
- `ESENT!JetGetTableColumnInfoA` at `0x18003c9df`
- `ESENT!JetGetTableColumnInfoA` at `0x18003c9df`
- `ESENT!JetCloseDatabase` at `0x18003c4a2`
- `ESENT!JetCloseDatabase` at `0x18003c4a2`
- `ESENT!JetCreateDatabaseW` at `0x18003c457`
- `ESENT!JetCreateDatabaseW` at `0x18003c457`
- `ESENT!JetCloseTable` at `0x18003c8cf`
- `ESENT!JetCloseTable` at `0x18003c8cf`
- `ESENT!JetCreateTableColumnIndexA` at `0x18003c8b8`
- `ESENT!JetCreateTableColumnIndexA` at `0x18003c8b8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003c3ae`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003c3ae`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003cd31`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003cd6a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003cd31`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003cd6a`

## string_xrefs

- `0x18003c3ea`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\datasession.cpp`
- `0x18003c47d`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\datasession.cpp`
- `0x18003c4fe`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\datasession.cpp`
- `0x18003cd48`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\datasession.cpp`
- `0x18003cc3c`: `onecoreuap\base\AppModel\UserDataAccess\PublishedInternal\Inc\jetinterop.h`

## pseudocode

```c
__int64 __fastcall DatabaseVolumeSession::AttachDatabaseToSession(
        DatabaseVolumeSession *this,
        const struct DatabaseDefinition *a2,
        JET_SESID a3,
        unsigned int *a4)
{
  DatabaseVolumeSession *v4; // r15
  unsigned int *v5; // r12
  int v6; // eax
  unsigned int v7; // r8d
  struct DatabaseTableDefinition *v8; // rbx
  JET_ERR v9; // eax
  unsigned int HresultFromJetError; // eax
  __int64 v11; // r9
  JET_DBID v12; // edx
  bool v13; // zf
  JET_ERR v14; // eax
  JET_COLUMNCREATE_A *v15; // r14
  _QWORD *v16; // r13
  int i; // eax
  __int64 v18; // rax
  __int64 v19; // rbx
  _QWORD *v20; // r15
  const char *v21; // r8
  JET_ERR v22; // eax
  unsigned int j; // r9d
  __int64 v24; // rcx
  __int64 v25; // r8
  __int64 v26; // rdx
  __int64 v27; // r10
  __int64 v28; // rcx
  __int64 v29; // r12
  _QWORD *v30; // rax
  unsigned __int64 v31; // r15
  unsigned __int64 v32; // rdx
  __int64 v33; // r9
  __int64 *v34; // r10
  __int64 v35; // r11
  __int64 v36; // r8
  __int64 v37; // rcx
  _BYTE *v38; // rax
  unsigned int *v39; // r15
  __int64 v40; // r9
  __int64 v41; // r10
  __int64 v42; // r9
  __int64 v43; // r10
  int v44; // r12d
  unsigned int v45; // eax
  __int64 v46; // r10
  __int64 v47; // r9
  int v48; // r10d
  unsigned __int64 v49; // r12
  int v50; // r15d
  JET_INDEXCREATE_A *v51; // r9
  JET_ERR v52; // eax
  JET_ERR v53; // eax
  unsigned int v54; // eax
  __int64 v55; // rdx
  _QWORD *v56; // rbx
  __int64 k; // r8
  _DWORD *v58; // r15
  __int64 m; // r12
  __int64 v60; // r8
  JET_ERR TableColumnInfoA; // eax
  __int64 v62; // r8
  int updated; // eax
  __int64 v64; // r9
  __int64 v65; // r9
  unsigned int v66; // eax
  __int64 v67; // rcx
  __int64 v68; // r9
  void *v69; // rcx
  int v70; // eax
  unsigned int v71; // eax
  JET_DBID pdbid; // [rsp+40h] [rbp-C0h] BYREF
  JET_SESID sesid; // [rsp+48h] [rbp-B8h] BYREF
  JET_SESID v75; // [rsp+50h] [rbp-B0h] BYREF
  JET_TABLEID tableid; // [rsp+58h] [rbp-A8h] BYREF
  void *v77[3]; // [rsp+60h] [rbp-A0h] BYREF
  void *v78[3]; // [rsp+78h] [rbp-88h] BYREF
  void *v79[3]; // [rsp+90h] [rbp-70h] BYREF
  struct DatabaseTableDefinition *v80; // [rsp+A8h] [rbp-58h] BYREF
  int v81; // [rsp+B0h] [rbp-50h]
  _QWORD v82[2]; // [rsp+B8h] [rbp-48h] BYREF
  char v83; // [rsp+C8h] [rbp-38h]
  DatabaseVolumeSession *v84; // [rsp+D0h] [rbp-30h]
  __int64 v85; // [rsp+D8h] [rbp-28h]
  __int64 v86; // [rsp+E0h] [rbp-20h]
  __int64 v87; // [rsp+E8h] [rbp-18h]
  _QWORD *v88; // [rsp+F0h] [rbp-10h]
  void *v89[3]; // [rsp+F8h] [rbp-8h] BYREF
  unsigned int *v90; // [rsp+110h] [rbp+10h]
  JET_TABLECREATE_A ptablecreate; // [rsp+120h] [rbp+20h] BYREF
  void *Block[3]; // [rsp+170h] [rbp+70h] BYREF
  char v93[16]; // [rsp+188h] [rbp+88h] BYREF
  JET_COLUMNDEF pvResult; // [rsp+198h] [rbp+98h] BYREF
  WCHAR szFilename[264]; // [rsp+1C0h] [rbp+C0h] BYREF

  v4 = this;
  v84 = this;
  v90 = a4;
  v5 = a4;
  sesid = a3;
  EnterCriticalSection(&g_sessionLock);
  v6 = StringCchPrintfW(szFilename, 0x104u, L"%s%S", *((_QWORD *)v4 + 1), UdmDatabase_Phone);
  LODWORD(v8) = v6;
  if ( v6 < 0 )
  {
    Log_HREvent(
      (unsigned int)v6,
      1,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\datasession.cpp",
      257);
    goto LABEL_97;
  }
  pdbid = -1;
  LODWORD(v8) = CommsESE_JetAttachDatabaseW(sesid, szFilename, v7);
  v83 = 1;
  v82[0] = &pdbid;
  v82[1] = &sesid;
  if ( (_DWORD)v8 == -2147024894 )
  {
    v9 = JetCreateDatabaseW(sesid, szFilename, 0, &pdbid, 0);
    if ( v9 < 0 )
    {
      HresultFromJetError = MakeHresultFromJetError(v9);
      v11 = 272;
LABEL_95:
      LODWORD(v8) = HresultFromJetError;
      Log_HREvent(
        HresultFromJetError,
        0,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\datasession.cpp",
        v11);
      goto LABEL_96;
    }
  }
  else
  {
    if ( (int)v8 < 0 )
    {
      Log_HREvent(
        (unsigned int)v8,
        1,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\datasession.cpp",
        281);
      v12 = pdbid;
      v13 = pdbid == -1;
LABEL_8:
      if ( !v13 )
        JetCloseDatabase(sesid, v12, 0);
      goto LABEL_97;
    }
    v14 = JetOpenDatabaseW(sesid, szFilename, 0, &pdbid, 0);
    if ( v14 < 0 )
    {
      HresultFromJetError = MakeHresultFromJetError(v14);
      v11 = 282;
      goto LABEL_95;
    }
  }
  if ( *((_DWORD *)v4 + 14) )
  {
LABEL_93:
    *v5 = pdbid;
    *((_DWORD *)v4 + 14) = 1;
    LeaveCriticalSection(&g_sessionLock);
    return 0;
  }
  utl::vector<tlx::auto_xxx<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),0>,utl::allocator<tlx::auto_xxx<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),0>>>::vector<tlx::auto_xxx<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),0>,utl::allocator<tlx::auto_xxx<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),0>>>(v79);
  utl::vector<tlx::auto_xxx<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),0>,utl::allocator<tlx::auto_xxx<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),0>>>::vector<tlx::auto_xxx<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),0>,utl::allocator<tlx::auto_xxx<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),0>>>(v78);
  utl::vector<tlx::auto_xxx<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),0>,utl::allocator<tlx::auto_xxx<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),0>>>::vector<tlx::auto_xxx<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),0>,utl::allocator<tlx::auto_xxx<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),0>>>(v77);
  v15 = (JET_COLUMNCREATE_A *)v79[0];
  v16 = v77[0];
  for ( i = 0; ; i = v81 + 1 )
  {
    v81 = i;
    if ( i )
    {
      utl::vector<utl::vector<tagJET_CONDITIONALCOLUMN_A,utl::allocator<tagJET_CONDITIONALCOLUMN_A>>,utl::allocator<utl::vector<tagJET_CONDITIONALCOLUMN_A,utl::allocator<tagJET_CONDITIONALCOLUMN_A>>>>::_Uninit(v77);
      utl::vector<UdmEmailParticipant,utl::allocator<UdmEmailParticipant>>::_Uninit(v78);
      utl::vector<UdmEmailParticipant,utl::allocator<UdmEmailParticipant>>::_Uninit(v79);
      v5 = v90;
      goto LABEL_93;
    }
    v80 = (struct DatabaseTableDefinition *)&UdmTableDef_CallHistory;
    v75 = sesid;
    tableid = -1;
    v18 = utl::vector<tlx::auto_xxx<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),0>,utl::allocator<tlx::auto_xxx<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),0>>>::vector<tlx::auto_xxx<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),0>,utl::allocator<tlx::auto_xxx<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),0>>>(Block);
    v19 = *(_QWORD *)utl::_HashTable<DatabaseTableDefinition const *,utl::pair<DatabaseTableDefinition const * const,utl::vector<unsigned long,utl::allocator<unsigned long>>>,utl::hash<DatabaseTableDefinition const *>,utl::equal_to<DatabaseTableDefinition const *>,utl::allocator<utl::pair<DatabaseTableDefinition const * const,utl::vector<unsigned long,utl::allocator<unsigned long>>>>,0>::emplace<DatabaseTableDefinition const * &,utl::vector<unsigned long,utl::allocator<unsigned long>>,0>(
                       (char *)v4 + 64,
                       v93,
                       &v80,
                       v18);
    if ( Block[0] != (void *)-1LL )
    {
      Block[1] = Block[0];
      operator delete(Block[0]);
    }
    if ( !v19 )
    {
      v64 = 300;
      goto LABEL_89;
    }
    v20 = (_QWORD *)(v19 + 32);
    v8 = v80;
    v21 = (const char *)*((_QWORD *)v80 + 1);
    v88 = v20;
    v22 = JetOpenTableA(sesid, pdbid, v21, 0, 0, 0xAu, &tableid);
    if ( v22 == -1305 )
    {
      if ( utl::vector<USLongDeletedRevisionItem,utl::allocator<USLongDeletedRevisionItem>>::_Resize<,0>(
             v79,
             *((unsigned int *)v8 + 6)) )
      {
        v15 = (JET_COLUMNCREATE_A *)v79[0];
        for ( j = 0; j < *((_DWORD *)v8 + 6); v15[v25].cp = 1200 )
        {
          v24 = *((_QWORD *)v8 + 2);
          v25 = j;
          v26 = 32LL * j++;
          *(_OWORD *)&v15[v25].cbStruct = 0;
          *(_OWORD *)&v15[v25].coltyp = 0;
          *(_OWORD *)&v15[v25].pvDefault = 0;
          *(_QWORD *)&v15[v25].columnid = 0;
          v15[v25].cbStruct = 56;
          v15[v25].szColumnName = *(char **)(v26 + v24 + 8);
          v15[v25].coltyp = *(_DWORD *)(v26 + v24 + 16);
          v15[v25].cbMax = *(_DWORD *)(v26 + v24 + 20);
          v15[v25].grbit = *(_DWORD *)(v26 + v24 + 24);
        }
        if ( !utl::vector<tagJET_INDEXCREATE_A,utl::allocator<tagJET_INDEXCREATE_A>>::_Resize<,0>(
                v78,
                *((unsigned int *)v8 + 10)) )
        {
          v64 = 329;
          goto LABEL_89;
        }
        if ( !(unsigned __int8)utl::vector<utl::vector<tagJET_CONDITIONALCOLUMN_A,utl::allocator<tagJET_CONDITIONALCOLUMN_A>>,utl::allocator<utl::vector<tagJET_CONDITIONALCOLUMN_A,utl::allocator<tagJET_CONDITIONALCOLUMN_A>>>>::_Resize<,0>(
                                 v77,
                                 *((unsigned int *)v8 + 10)) )
        {
          v64 = 330;
          goto LABEL_89;
        }
        v16 = v77[0];
        v27 = 0;
        while ( 1 )
        {
          LODWORD(v80) = v27;
          if ( (unsigned int)v27 >= *((_DWORD *)v8 + 10) )
            break;
          v28 = *((_QWORD *)v8 + 4);
          v86 = 48 * v27;
          v29 = (unsigned int)v27;
          v87 = v28;
          v30 = *(_QWORD **)(48 * v27 + v28 + 40);
          if ( v30 )
          {
            v31 = 0;
            if ( *v30 )
            {
              do
                ++v31;
              while ( v30[v31] );
            }
            v85 = (__int64)&v16[3 * v27];
            if ( !(unsigned __int8)utl::vector<tagJET_CONDITIONALCOLUMN_A,utl::allocator<tagJET_CONDITIONALCOLUMN_A>>::_Resize<,0>(
                                     v85,
                                     v31) )
            {
              v64 = 347;
              goto LABEL_89;
            }
            v32 = 0;
            if ( v31 )
            {
              v33 = v86;
              v34 = (__int64 *)v85;
              v35 = v87;
              do
              {
                v36 = 3 * v32;
                *(_DWORD *)(*v34 + 8 * v36) = 24;
                *(_QWORD *)(*v34 + 8 * v36 + 8) = *(_QWORD *)(*(_QWORD *)(v33 + v35 + 40) + 8 * v32);
                v37 = *v34;
                v38 = *(_BYTE **)(*v34 + 24 * v32 + 8);
                if ( *v38 == 33 )
                {
                  *(_QWORD *)(v37 + 24 * v32 + 8) = v38 + 1;
                  *(_DWORD *)(*v34 + 24 * v32 + 16) = 1;
                }
                else
                {
                  *(_DWORD *)(v37 + 24 * v32 + 16) = 2;
                }
                ++v32;
              }
              while ( v32 < v31 );
            }
          }
          v39 = (unsigned int *)((char *)v78[0] + 80 * v29);
          memset_0(v39, 0, 0x50u);
          v40 = v86;
          v41 = v87;
          *v39 = 80;
          *((_QWORD *)v39 + 1) = *(_QWORD *)(v40 + v41 + 8);
          *((_QWORD *)v39 + 2) = *(_QWORD *)(v40 + v41 + 16);
          v44 = ULongLongToULong(*(_QWORD *)(v40 + v41 + 32), v39 + 6);
          if ( v44 < 0 )
          {
            v65 = 370;
            goto LABEL_63;
          }
          v45 = *(_DWORD *)(v42 + v43 + 24);
          v46 = (unsigned int)v80;
          v39[7] = v45;
          v39[8] = 80;
          v39[10] = 1033;
          v44 = ULongLongToULong(0xAAAAAAAAAAAAAAABuLL * ((__int64)(v16[3 * v46 + 1] - v16[3 * v46]) >> 3), v39 + 16);
          if ( v44 < 0 )
          {
            v65 = 374;
LABEL_63:
            Log_HREvent(
              (unsigned int)v44,
              1,
              "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\datasession.cpp",
              v65);
            auto_JET_TABLEID::~auto_JET_TABLEID((auto_JET_TABLEID *)&v75);
            utl::vector<utl::vector<tagJET_CONDITIONALCOLUMN_A,utl::allocator<tagJET_CONDITIONALCOLUMN_A>>,utl::allocator<utl::vector<tagJET_CONDITIONALCOLUMN_A,utl::allocator<tagJET_CONDITIONALCOLUMN_A>>>>::_Uninit(v77);
            utl::vector<UdmEmailParticipant,utl::allocator<UdmEmailParticipant>>::_Uninit(v78);
            utl::vector<UdmEmailParticipant,utl::allocator<UdmEmailParticipant>>::_Uninit(v79);
            tlx::_UndoSolo__lambda_90a2604abc0f2846ab0b425d86ffc7b9___::__UndoSolo__lambda_90a2604abc0f2846ab0b425d86ffc7b9___(v82);
            LODWORD(v8) = v44;
            goto LABEL_97;
          }
          v27 = (unsigned int)(v48 + 1);
          *((_QWORD *)v39 + 7) = v16[v47];
        }
        *(_QWORD *)&ptablecreate.cbStruct = 80;
        memset_0(&ptablecreate.szTableName, 0, 0x48u);
        ptablecreate.szTableName = (char *)*((_QWORD *)v8 + 1);
        ptablecreate.ulPages = 10;
        ptablecreate.ulDensity = 80;
        ptablecreate.grbit = *((_DWORD *)v8 + 11);
        v49 = 0x6DB6DB6DB6DB6DB7LL * (((char *)v79[1] - (char *)v15) >> 3);
        v50 = ULongLongToULong(v49, &ptablecreate.cColumns);
        if ( v50 < 0 )
        {
          v68 = 384;
          goto LABEL_69;
        }
        ptablecreate.rgcolumncreate = v15;
        v50 = ULongLongToULong(0xCCCCCCCCCCCCCCCDuLL * (((char *)v78[1] - (char *)v78[0]) >> 4), &ptablecreate.cIndexes);
        if ( v50 < 0 )
        {
          v68 = 386;
LABEL_69:
          Log_HREvent(
            (unsigned int)v50,
            1,
            "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\datasession.cpp",
            v68);
          auto_JET_TABLEID::~auto_JET_TABLEID((auto_JET_TABLEID *)&v75);
          utl::vector<utl::vector<tagJET_CONDITIONALCOLUMN_A,utl::allocator<tagJET_CONDITIONALCOLUMN_A>>,utl::allocator<utl::vector<tagJET_CONDITIONALCOLUMN_A,utl::allocator<tagJET_CONDITIONALCOLUMN_A>>>>::_Uninit(v77);
          utl::vector<UdmEmailParticipant,utl::allocator<UdmEmailParticipant>>::_Uninit(v78);
          utl::vector<UdmEmailParticipant,utl::allocator<UdmEmailParticipant>>::_Uninit(v79);
          tlx::_UndoSolo__lambda_90a2604abc0f2846ab0b425d86ffc7b9___::__UndoSolo__lambda_90a2604abc0f2846ab0b425d86ffc7b9___(v82);
          LODWORD(v8) = v50;
          goto LABEL_97;
        }
        ptablecreate.rgindexcreate = v51;
        ptablecreate.grbit = *((_DWORD *)v8 + 11);
        v52 = JetCreateTableColumnIndexA(sesid, pdbid, &ptablecreate);
        if ( v52 < 0 )
        {
          v66 = MakeHresultFromJetError(v52);
          v64 = 393;
          goto LABEL_66;
        }
        v53 = JetCloseTable(sesid, ptablecreate.tableid);
        if ( v53 < 0 )
        {
          v54 = MakeHresultFromJetError(v53);
          Log_HREvent(
            v54,
            0,
            "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\datasession.cpp",
            394);
        }
        v55 = *((unsigned int *)v8 + 6);
        v56 = v88;
        if ( !(unsigned __int8)utl::vector<unsigned long,utl::allocator<unsigned long>>::_Resize<,0>(v88, v55) )
        {
          v64 = 397;
          goto LABEL_89;
        }
        for ( k = 0; (unsigned int)k < v49; k = (unsigned int)(k + 1) )
          *(_DWORD *)(*v56 + 4 * k) = v15[(unsigned int)k].columnid;
        v4 = v84;
        goto LABEL_47;
      }
      v64 = 312;
LABEL_89:
      LODWORD(v8) = -2147024882;
      v67 = 2147942414LL;
      goto LABEL_90;
    }
    if ( v22 < 0 )
      break;
    if ( *v20 == v20[1] )
    {
      utl::vector<tlx::auto_xxx<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),0>,utl::allocator<tlx::auto_xxx<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),0>>>::vector<tlx::auto_xxx<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),0>,utl::allocator<tlx::auto_xxx<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),0>>>(v89);
      if ( (unsigned __int8)utl::vector<unsigned long,utl::allocator<unsigned long>>::_Resize<,0>(
                              v89,
                              *((unsigned int *)v8 + 6)) )
      {
        v58 = v89[0];
        for ( m = 0; ; m = (unsigned int)(m + 1) )
        {
          if ( (unsigned int)m >= *((_DWORD *)v8 + 6) )
          {
            v4 = v84;
            updated = DatabaseVolumeSession::_UpdateTableIndexes(v84, sesid, tableid, v8);
            LODWORD(v8) = updated;
            if ( updated >= 0 )
            {
              utl::vector<ServiceEntityCallsEnum::CallItem,utl::allocator<ServiceEntityCallsEnum::CallItem>>::swap(
                v89,
                v88);
              utl::vector<UdmEmailParticipant,utl::allocator<UdmEmailParticipant>>::_Uninit(v89);
              goto LABEL_47;
            }
            Log_HREvent(
              (unsigned int)updated,
              1,
              "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\datasession.cpp",
              449);
            utl::vector<UdmEmailParticipant,utl::allocator<UdmEmailParticipant>>::_Uninit(v89);
            goto LABEL_91;
          }
          pvResult.cbStruct = 28;
          memset(&pvResult.columnid, 0, 24);
          v60 = *((_QWORD *)v8 + 2);
          v85 = 32LL * (unsigned int)m;
          TableColumnInfoA = JetGetTableColumnInfoA(sesid, tableid, *(JET_PCSTR *)(v60 + v85 + 8), &pvResult, 0x1Cu, 0);
          if ( TableColumnInfoA == -1507 )
          {
            v62 = *((_QWORD *)v8 + 2);
            pvResult.coltyp = *(_DWORD *)(v62 + v85 + 16);
            pvResult.cp = 1200;
            *(_QWORD *)&pvResult.cbMax = *(_QWORD *)(v62 + v85 + 20);
            TableColumnInfoA = JetAddColumnA(
                                 sesid,
                                 tableid,
                                 *(JET_PCSTR *)(v62 + v85 + 8),
                                 &pvResult,
                                 0,
                                 0,
                                 &pvResult.columnid);
          }
          if ( TableColumnInfoA < 0 )
            break;
          v58[m] = pvResult.columnid;
        }
        v8 = (struct DatabaseTableDefinition *)(unsigned int)MakeHresultFromJetError(TableColumnInfoA);
        Log_HREvent(
          v8,
          0,
          "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\datasession.cpp",
          444);
        if ( v58 == (_DWORD *)-1LL )
          goto LABEL_78;
        v69 = v58;
LABEL_77:
        operator delete(v69);
      }
      else
      {
        LODWORD(v8) = -2147024882;
        Log_HREvent(
          2147942414LL,
          0,
          "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\datasession.cpp",
          413);
        v69 = v89[0];
        if ( v89[0] != (void *)-1LL )
          goto LABEL_77;
      }
LABEL_78:
      v70 = auto_JET_TABLEID::close((auto_JET_TABLEID *)&v75);
      if ( v70 < 0 )
      {
        v71 = MakeHresultFromJetError(v70);
        Log_HREvent(v71, 0, "onecoreuap\\base\\AppModel\\UserDataAccess\\PublishedInternal\\Inc\\jetinterop.h", 261);
      }
      if ( v16 != (_QWORD *)-1LL )
      {
        utl::vector<utl::vector<tagJET_CONDITIONALCOLUMN_A,utl::allocator<tagJET_CONDITIONALCOLUMN_A>>,utl::allocator<utl::vector<tagJET_CONDITIONALCOLUMN_A,utl::allocator<tagJET_CONDITIONALCOLUMN_A>>>>::_EraseTail(
          v77,
          v16);
        operator delete(v77[0]);
      }
      if ( v78[0] != (void *)-1LL )
        operator delete(v78[0]);
      if ( v15 != (JET_COLUMNCREATE_A *)-1LL )
        operator delete(v15);
      v12 = pdbid;
      v13 = pdbid == -1;
      goto LABEL_8;
    }
    v4 = v84;
LABEL_47:
    auto_JET_TABLEID::~auto_JET_TABLEID((auto_JET_TABLEID *)&v75);
  }
  v66 = MakeHresultFromJetError(v22);
  v64 = 408;
LABEL_66:
  LODWORD(v8) = v66;
  v67 = v66;
LABEL_90:
  Log_HREvent(
    v67,
    0,
    "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\datasession.cpp",
    v64);
LABEL_91:
  auto_JET_TABLEID::~auto_JET_TABLEID((auto_JET_TABLEID *)&v75);
  utl::vector<utl::vector<tagJET_CONDITIONALCOLUMN_A,utl::allocator<tagJET_CONDITIONALCOLUMN_A>>,utl::allocator<utl::vector<tagJET_CONDITIONALCOLUMN_A,utl::allocator<tagJET_CONDITIONALCOLUMN_A>>>>::_Uninit(v77);
  utl::vector<UdmEmailParticipant,utl::allocator<UdmEmailParticipant>>::_Uninit(v78);
  utl::vector<UdmEmailParticipant,utl::allocator<UdmEmailParticipant>>::_Uninit(v79);
LABEL_96:
  tlx::_UndoSolo__lambda_90a2604abc0f2846ab0b425d86ffc7b9___::__UndoSolo__lambda_90a2604abc0f2846ab0b425d86ffc7b9___(v82);
LABEL_97:
  LeaveCriticalSection(&g_sessionLock);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18003c364  mov     [rsp-8+arg_8], rbx
0x18003c369  push    rbp
0x18003c36a  push    rsi
0x18003c36b  push    rdi
0x18003c36c  push    r12
0x18003c36e  push    r13
0x18003c370  push    r14
0x18003c372  push    r15
0x18003c374  lea     rbp, [rsp-2E0h]
0x18003c37c  sub     rsp, 3E0h
0x18003c383  mov     rax, cs:__security_cookie
0x18003c38a  xor     rax, rsp
0x18003c38d  mov     [rbp+310h+var_40], rax
0x18003c394  mov     r15, rcx
0x18003c397  mov     [rbp+310h+var_340], rcx
0x18003c39b  lea     rcx, ?g_sessionLock@@3Vrecursive_mutex@utl@@A; lpCriticalSection
0x18003c3a2  mov     [rbp+310h+var_300], r9
0x18003c3a6  mov     r12, r9
0x18003c3a9  mov     [rsp+410h+sesid], r8
0x18003c3ae  call    cs:__imp_EnterCriticalSection
0x18003c3b4  mov     rax, cs:?UdmDatabase_Phone@@3UDatabaseDefinition@@B; DatabaseDefinition const UdmDatabase_Phone
0x18003c3bb  lea     r8, aSS; "%s%S"
0x18003c3c2  mov     r9, [r15+8]
0x18003c3c6  lea     rcx, [rbp+310h+szFilename]; unsigned __int16 *
0x18003c3cd  mov     edx, 104h; unsigned __int64
0x18003c3d2  mov     qword ptr [rsp+410h+grbit], rax
0x18003c3d7  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18003c3dc  xor     edi, edi
0x18003c3de  mov     ebx, eax
0x18003c3e0  test    eax, eax
0x18003c3e2  jns     short loc_18003C400
0x18003c3e4  mov     r9d, 101h
0x18003c3ea  lea     r8, aOnecoreuapBase_62; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18003c3f1  lea     edx, [rdi+1]
0x18003c3f4  mov     ecx, eax
0x18003c3f6  call    Log_HREvent
0x18003c3fb  jmp     loc_18003CD63
0x18003c400  mov     rcx, [rsp+410h+sesid]; unsigned __int64
0x18003c405  lea     rdx, [rbp+310h+szFilename]; unsigned __int16 *
0x18003c40c  or      r14d, 0FFFFFFFFh
0x18003c410  mov     [rsp+410h+pdbid], r14d
0x18003c415  call    ?CommsESE_JetAttachDatabaseW@@YAJ_KPEBGK@Z; CommsESE_JetAttachDatabaseW(unsigned __int64,ushort const *,ulong)
0x18003c41a  mov     ebx, eax
0x18003c41c  mov     esi, 1
0x18003c421  mov     [rbp+310h+var_348], sil
0x18003c425  lea     rax, [rsp+410h+pdbid]
0x18003c42a  mov     [rbp+310h+var_358], rax
0x18003c42e  lea     rax, [rsp+410h+sesid]
0x18003c433  mov     [rbp+310h+var_350], rax
0x18003c437  cmp     ebx, 80070002h
0x18003c43d  jnz     short loc_18003C473
0x18003c43f  mov     rcx, [rsp+410h+sesid]; sesid
0x18003c444  lea     r9, [rsp+410h+pdbid]; pdbid
0x18003c449  xor     r8d, r8d; szConnect
0x18003c44c  mov     [rsp+410h+grbit], edi; grbit
0x18003c450  lea     rdx, [rbp+310h+szFilename]; szFilename
0x18003c457  call    cs:__imp_JetCreateDatabaseW
0x18003c45d  test    eax, eax
0x18003c45f  jns     short loc_18003C4D3
0x18003c461  mov     ecx, eax; int
0x18003c463  call    ?MakeHresultFromJetError@@YAJJ@Z; MakeHresultFromJetError(long)
0x18003c468  mov     r9d, 110h
0x18003c46e  jmp     loc_18003CD48
0x18003c473  test    ebx, ebx
0x18003c475  jns     short loc_18003C4AD
0x18003c477  mov     r9d, 119h
0x18003c47d  lea     r8, aOnecoreuapBase_62; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18003c484  mov     edx, esi
0x18003c486  mov     ecx, ebx
0x18003c488  call    Log_HREvent
0x18003c48d  mov     edx, [rsp+410h+pdbid]; dbid
0x18003c491  cmp     edx, r14d
0x18003c494  jz      loc_18003CD63
0x18003c49a  mov     rcx, [rsp+410h+sesid]; sesid
0x18003c49f  xor     r8d, r8d; grbit
0x18003c4a2  call    cs:__imp_JetCloseDatabase
0x18003c4a8  jmp     loc_18003CD63
0x18003c4ad  mov     rcx, [rsp+410h+sesid]; sesid
0x18003c4b2  lea     r9, [rsp+410h+pdbid]; pdbid
0x18003c4b7  xor     r8d, r8d; szConnect
0x18003c4ba  mov     [rsp+410h+grbit], edi; grbit
0x18003c4be  lea     rdx, [rbp+310h+szFilename]; szFilename
0x18003c4c5  call    cs:__imp_JetOpenDatabaseW
0x18003c4cb  test    eax, eax
0x18003c4cd  js      loc_18003CD3B
0x18003c4d3  cmp     [r15+38h], edi
0x18003c4d7  jnz     loc_18003CD1E
0x18003c4dd  lea     rcx, [rbp+310h+var_380]
0x18003c4e1  call    ??0?$vector@V?$auto_xxx@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@Z$0A@@tlx@@V?$allocator@V?$auto_xxx@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@Z$0A@@tlx@@@utl@@@utl@@QEAA@XZ; utl::vector<tlx::auto_xxx<ushort *,void (*)(ushort *),&SysFreeString(ushort *),0>,utl::allocator<tlx::auto_xxx<ushort *,void (*)(ushort *),&SysFreeString(ushort *),0>>>::vector<tlx::auto_xxx<ushort *,void (*)(ushort *),&SysFreeString(ushort *),0>,utl::allocator<tlx::auto_xxx<ushort *,void (*)(ushort *),&SysFreeString(ushort *),0>>>(void)
0x18003c4e6  lea     rcx, [rsp+410h+var_398]
0x18003c4eb  call    ??0?$vector@V?$auto_xxx@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@Z$0A@@tlx@@V?$allocator@V?$auto_xxx@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@Z$0A@@tlx@@@utl@@@utl@@QEAA@XZ; utl::vector<tlx::auto_xxx<ushort *,void (*)(ushort *),&SysFreeString(ushort *),0>,utl::allocator<tlx::auto_xxx<ushort *,void (*)(ushort *),&SysFreeString(ushort *),0>>>::vector<tlx::auto_xxx<ushort *,void (*)(ushort *),&SysFreeString(ushort *),0>,utl::allocator<tlx::auto_xxx<ushort *,void (*)(ushort *),&SysFreeString(ushort *),0>>>(void)
0x18003c4f0  lea     rcx, [rsp+410h+var_3B0]
0x18003c4f5  call    ??0?$vector@V?$auto_xxx@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@Z$0A@@tlx@@V?$allocator@V?$auto_xxx@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@Z$0A@@tlx@@@utl@@@utl@@QEAA@XZ; utl::vector<tlx::auto_xxx<ushort *,void (*)(ushort *),&SysFreeString(ushort *),0>,utl::allocator<tlx::auto_xxx<ushort *,void (*)(ushort *),&SysFreeString(ushort *),0>>>::vector<tlx::auto_xxx<ushort *,void (*)(ushort *),&SysFreeString(ushort *),0>,utl::allocator<tlx::auto_xxx<ushort *,void (*)(ushort *),&SysFreeString(ushort *),0>>>(void)
0x18003c4fa  mov     r14, [rbp+310h+var_380]
0x18003c4fe  lea     rdi, aOnecoreuapBase_62; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18003c505  mov     r13, [rsp+410h+var_3B0]
0x18003c50a  xor     eax, eax
0x18003c50c  mov     r12d, 4B0h
0x18003c512  mov     [rbp+310h+var_360], eax
0x18003c515  cmp     eax, esi
0x18003c517  jnb     loc_18003CCFD
0x18003c51d  mov     ecx, eax
0x18003c51f  mov     rax, cs:off_18012FE48
0x18003c526  mov     rcx, [rax+rcx*8]
0x18003c52a  mov     rax, [rsp+410h+sesid]
0x18003c52f  mov     [rbp+310h+var_368], rcx
0x18003c533  lea     rcx, [rbp+310h+Block]
0x18003c537  mov     [rsp+410h+var_3C0], rax
0x18003c53c  mov     [rsp+410h+tableid], 0FFFFFFFFFFFFFFFFh
0x18003c545  call    ??0?$vector@V?$auto_xxx@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@Z$0A@@tlx@@V?$allocator@V?$auto_xxx@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@Z$0A@@tlx@@@utl@@@utl@@QEAA@XZ; utl::vector<tlx::auto_xxx<ushort *,void (*)(ushort *),&SysFreeString(ushort *),0>,utl::allocator<tlx::auto_xxx<ushort *,void (*)(ushort *),&SysFreeString(ushort *),0>>>::vector<tlx::auto_xxx<ushort *,void (*)(ushort *),&SysFreeString(ushort *),0>,utl::allocator<tlx::auto_xxx<ushort *,void (*)(ushort *),&SysFreeString(ushort *),0>>>(void)
0x18003c54a  mov     r9, rax
0x18003c54d  lea     rcx, [r15+40h]
0x18003c551  lea     r8, [rbp+310h+var_368]
0x18003c555  lea     rdx, [rbp+310h+var_288]
0x18003c55c  call    ??$emplace@AEAPEBUDatabaseTableDefinition@@V?$vector@KV?$allocator@K@utl@@@utl@@$0A@@?$_HashTable@PEBUDatabaseTableDefinition@@U?$pair@QEBUDatabaseTableDefinition@@V?$vector@KV?$allocator@K@utl@@@utl@@@utl@@U?$hash@PEBUDatabaseTableDefinition@@@3@U?$equal_to@PEBUDatabaseTableDefinition@@@3@V?$allocator@U?$pair@QEBUDatabaseTableDefinition@@V?$vector@KV?$allocator@K@utl@@@utl@@@utl@@@3@$0A@@utl@@QEAA?AU?$pair@V?$_DlistIt@U?$_HashNode@U?$pair@QEBUDatabaseTableDefinition@@V?$vector@KV?$allocator@K@utl@@@utl@@@utl@@@utl@@U?$pair@QEBUDatabaseTableDefinition@@V?$vector@KV?$allocator@K@utl@@@utl@@@2@@utl@@_N@1@AEAPEBUDatabaseTableDefinition@@$$QEAV?$vector@KV?$allocator@K@utl@@@1@@Z; utl::_HashTable<DatabaseTableDefinition const *,utl::pair<DatabaseTableDefinition const * const,utl::vector<ulong,utl::allocator<ulong>>>,utl::hash<DatabaseTableDefinition const *>,utl::equal_to<DatabaseTableDefinition const *>,utl::allocator<utl::pair<DatabaseTableDefinition const * const,utl::vector<ulong,utl::allocator<ulong>>>>,0>::emplace<DatabaseTableDefinition const * &,utl::vector<ulong,utl::allocator<ulong>>,0>(DatabaseTableDefinition const * &,utl::vector<ulong,utl::allocator<ulong>> &&)
0x18003c561  mov     rcx, [rbp+310h+Block]; Block
0x18003c565  mov     rbx, [rax]
0x18003c568  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18003c56c  jz      short loc_18003C57E
0x18003c56e  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x18003c575  mov     [rbp+310h+var_298], rcx
0x18003c579  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18003c57e  test    rbx, rbx
0x18003c581  jz      loc_18003CCBD
0x18003c587  mov     edx, [rsp+410h+pdbid]; dbid
0x18003c58b  lea     r15, [rbx+20h]
0x18003c58f  mov     rbx, [rbp+310h+var_368]
0x18003c593  lea     rax, [rsp+410h+tableid]
0x18003c598  mov     rcx, [rsp+410h+sesid]; sesid
0x18003c59d  xor     r9d, r9d; pvParameters
0x18003c5a0  mov     [rsp+410h+ptableid], rax; ptableid
0x18003c5a5  mov     [rsp+410h+InfoLevel], 0Ah; grbit
0x18003c5ad  mov     r8, [rbx+8]; szTableName
0x18003c5b1  mov     [rbp+310h+var_320], r15
0x18003c5b5  mov     [rsp+410h+grbit], 0; cbParameters
0x18003c5bd  call    cs:__imp_JetOpenTableA
0x18003c5c3  cmp     eax, 0FFFFFAE7h
0x18003c5c8  jnz     loc_18003C94D
0x18003c5ce  mov     edx, [rbx+18h]
0x18003c5d1  lea     rcx, [rbp+310h+var_380]
0x18003c5d5  call    ??$_Resize@$$V$0A@@?$vector@UUSLongDeletedRevisionItem@@V?$allocator@UUSLongDeletedRevisionItem@@@utl@@@utl@@AEAA_N_K@Z; utl::vector<USLongDeletedRevisionItem,utl::allocator<USLongDeletedRevisionItem>>::_Resize<,0>(unsigned __int64)
0x18003c5da  test    al, al
0x18003c5dc  jz      loc_18003CBA3
0x18003c5e2  mov     r14, [rbp+310h+var_380]
0x18003c5e6  xor     r9d, r9d
0x18003c5e9  cmp     [rbx+18h], r9d
0x18003c5ed  jbe     short loc_18003C654
0x18003c5ef  mov     rcx, [rbx+10h]
0x18003c5f3  xor     eax, eax
0x18003c5f5  mov     edx, r9d
0x18003c5f8  xorps   xmm0, xmm0
0x18003c5fb  imul    r8, rdx, 38h ; '8'
0x18003c5ff  shl     rdx, 5
0x18003c603  add     r9d, esi
0x18003c606  movups  xmmword ptr [r8+r14], xmm0
0x18003c60b  movups  xmmword ptr [r8+r14+10h], xmm0
0x18003c611  movups  xmmword ptr [r8+r14+20h], xmm0
0x18003c617  mov     [r8+r14+30h], rax
0x18003c61c  mov     dword ptr [r8+r14], 38h ; '8'
0x18003c624  mov     rax, [rdx+rcx+8]
0x18003c629  mov     [r8+r14+8], rax
0x18003c62e  mov     eax, [rdx+rcx+10h]
0x18003c632  mov     [r8+r14+10h], eax
0x18003c637  mov     eax, [rdx+rcx+14h]
0x18003c63b  mov     [r8+r14+14h], eax
0x18003c640  mov     eax, [rdx+rcx+18h]
0x18003c644  mov     [r8+r14+18h], eax
0x18003c649  mov     [r8+r14+2Ch], r12d
0x18003c64e  cmp     r9d, [rbx+18h]
0x18003c652  jb      short loc_18003C5EF
0x18003c654  mov     edx, [rbx+28h]
0x18003c657  lea     rcx, [rsp+410h+var_398]
0x18003c65c  call    ??$_Resize@$$V$0A@@?$vector@UtagJET_INDEXCREATE_A@@V?$allocator@UtagJET_INDEXCREATE_A@@@utl@@@utl@@AEAA_N_K@Z; utl::vector<tagJET_INDEXCREATE_A,utl::allocator<tagJET_INDEXCREATE_A>>::_Resize<,0>(unsigned __int64)
0x18003c661  test    al, al
0x18003c663  jz      loc_18003CB98
0x18003c669  mov     edx, [rbx+28h]
0x18003c66c  lea     rcx, [rsp+410h+var_3B0]
0x18003c671  call    ??$_Resize@$$V$0A@@?$vector@V?$vector@UtagJET_CONDITIONALCOLUMN_A@@V?$allocator@UtagJET_CONDITIONALCOLUMN_A@@@utl@@@utl@@V?$allocator@V?$vector@UtagJET_CONDITIONALCOLUMN_A@@V?$allocator@UtagJET_CONDITIONALCOLUMN_A@@@utl@@@utl@@@2@@utl@@AEAA_N_K@Z; utl::vector<utl::vector<tagJET_CONDITIONALCOLUMN_A,utl::allocator<tagJET_CONDITIONALCOLUMN_A>>,utl::allocator<utl::vector<tagJET_CONDITIONALCOLUMN_A,utl::allocator<tagJET_CONDITIONALCOLUMN_A>>>>::_Resize<,0>(unsigned __int64)
0x18003c676  test    al, al
0x18003c678  jz      loc_18003CB8D
0x18003c67e  mov     r13, [rsp+410h+var_3B0]
0x18003c683  xor     r10d, r10d
0x18003c686  mov     dword ptr [rbp+310h+var_368], r10d
0x18003c68a  cmp     r10d, [rbx+28h]
0x18003c68e  jnb     loc_18003C808
0x18003c694  mov     rcx, [rbx+20h]
0x18003c698  lea     rax, [r10+r10*2]
0x18003c69c  shl     rax, 4
0x18003c6a0  mov     [rbp+310h+var_330], rax
0x18003c6a4  mov     r12d, r10d
0x18003c6a7  mov     [rbp+310h+var_328], rcx
0x18003c6ab  mov     rax, [rax+rcx+28h]
0x18003c6b0  test    rax, rax
0x18003c6b3  jz      loc_18003C751
0x18003c6b9  xor     r15d, r15d
0x18003c6bc  cmp     [rax], r15
0x18003c6bf  jz      short loc_18003C6CB
0x18003c6c1  add     r15, rsi
0x18003c6c4  cmp     qword ptr [rax+r15*8], 0
0x18003c6c9  jnz     short loc_18003C6C1
0x18003c6cb  lea     rax, [r10+r10*2]
0x18003c6cf  mov     rdx, r15
0x18003c6d2  lea     rcx, ds:0[rax*8]
0x18003c6da  add     rcx, r13
0x18003c6dd  mov     [rbp+310h+var_338], rcx
0x18003c6e1  call    ??$_Resize@$$V$0A@@?$vector@UtagJET_CONDITIONALCOLUMN_A@@V?$allocator@UtagJET_CONDITIONALCOLUMN_A@@@utl@@@utl@@AEAA_N_K@Z; utl::vector<tagJET_CONDITIONALCOLUMN_A,utl::allocator<tagJET_CONDITIONALCOLUMN_A>>::_Resize<,0>(unsigned __int64)
0x18003c6e6  test    al, al
0x18003c6e8  jz      loc_18003CABB
0x18003c6ee  xor     edx, edx
0x18003c6f0  test    r15, r15
0x18003c6f3  jz      short loc_18003C751
0x18003c6f5  mov     r9, [rbp+310h+var_330]
0x18003c6f9  mov     r10, [rbp+310h+var_338]
0x18003c6fd  mov     r11, [rbp+310h+var_328]
0x18003c701  mov     rax, [r10]
0x18003c704  lea     r8, [rdx+rdx*2]
0x18003c708  mov     dword ptr [rax+r8*8], 18h
0x18003c710  mov     rax, [r9+r11+28h]
0x18003c715  mov     rcx, [r10]
0x18003c718  mov     rax, [rax+rdx*8]
0x18003c71c  mov     [rcx+r8*8+8], rax
0x18003c721  mov     rcx, [r10]
0x18003c724  mov     rax, [rcx+r8*8+8]
0x18003c729  cmp     byte ptr [rax], 21h ; '!'
0x18003c72c  jnz     short loc_18003C740
0x18003c72e  inc     rax
0x18003c731  mov     [rcx+r8*8+8], rax
0x18003c736  mov     rax, [r10]
0x18003c739  mov     [rax+r8*8+10h], esi
0x18003c73e  jmp     short loc_18003C749
0x18003c740  mov     dword ptr [rcx+r8*8+10h], 2
0x18003c749  add     rdx, rsi
0x18003c74c  cmp     rdx, r15
0x18003c74f  jb      short loc_18003C701
0x18003c751  xor     edx, edx; Val
0x18003c753  lea     r15, [r12+r12*4]
0x18003c757  shl     r15, 4
0x18003c75b  add     r15, [rsp+410h+var_398]
0x18003c760  mov     rcx, r15; void *
0x18003c763  lea     r8d, [rdx+50h]; Size
0x18003c767  call    memset_0
0x18003c76c  mov     r9, [rbp+310h+var_330]
0x18003c770  lea     rdx, [r15+18h]; unsigned int *
0x18003c774  mov     r10, [rbp+310h+var_328]
0x18003c778  mov     dword ptr [r15], 50h ; 'P'
0x18003c77f  mov     rax, [r9+r10+8]
0x18003c784  mov     [r15+8], rax
0x18003c788  mov     rax, [r9+r10+10h]
0x18003c78d  mov     [r15+10h], rax
0x18003c791  mov     rcx, [r9+r10+20h]; unsigned __int64
0x18003c796  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x18003c79b  mov     r12d, eax
0x18003c79e  test    eax, eax
0x18003c7a0  js      loc_18003CACE
0x18003c7a6  mov     eax, [r9+r10+18h]
0x18003c7ab  lea     rdx, [r15+40h]; unsigned int *
0x18003c7af  mov     r10d, dword ptr [rbp+310h+var_368]
0x18003c7b3  mov     [r15+1Ch], eax
0x18003c7b7  mov     rax, 0AAAAAAAAAAAAAAABh
0x18003c7c1  mov     dword ptr [r15+20h], 50h ; 'P'
0x18003c7c9  mov     dword ptr [r15+28h], 409h
0x18003c7d1  lea     r9, [r10+r10*2]
0x18003c7d5  mov     rcx, [r13+r9*8+8]
0x18003c7da  sub     rcx, [r13+r9*8+0]
0x18003c7df  sar     rcx, 3
0x18003c7e3  imul    rcx, rax; unsigned __int64
0x18003c7e7  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x18003c7ec  mov     r12d, eax
0x18003c7ef  test    eax, eax
0x18003c7f1  js      loc_18003CAC6
0x18003c7f7  mov     rax, [r13+r9*8+0]
0x18003c7fc  add     r10d, esi
0x18003c7ff  mov     [r15+38h], rax
0x18003c803  jmp     loc_18003C686
0x18003c808  xor     edx, edx; Val
0x18003c80a  mov     qword ptr [rbp+310h+ptablecreate.cbStruct], 50h ; 'P'
0x18003c812  lea     rcx, [rbp+310h+ptablecreate.szTableName]; void *
0x18003c816  lea     r8d, [rdx+48h]; Size
0x18003c81a  call    memset_0
0x18003c81f  mov     rax, [rbx+8]
0x18003c823  lea     rdx, [rbp+310h+ptablecreate.cColumns]; unsigned int *
0x18003c827  mov     r12, [rbp+310h+var_378]
0x18003c82b  mov     [rbp+310h+ptablecreate.szTableName], rax
0x18003c82f  sub     r12, r14
0x18003c832  mov     [rbp+310h+ptablecreate.ulPages], 0Ah
0x18003c839  mov     [rbp+310h+ptablecreate.ulDensity], 50h ; 'P'
0x18003c840  mov     eax, [rbx+2Ch]
0x18003c843  mov     [rbp+310h+ptablecreate.grbit], eax
0x18003c846  mov     rax, 6DB6DB6DB6DB6DB7h
0x18003c850  sar     r12, 3
0x18003c854  imul    r12, rax
0x18003c858  mov     rcx, r12; unsigned __int64
0x18003c85b  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x18003c860  mov     r15d, eax
0x18003c863  test    eax, eax
0x18003c865  js      loc_18003CB42
0x18003c86b  mov     rcx, [rbp+310h+var_390]
0x18003c86f  lea     rdx, [rbp+310h+ptablecreate.cIndexes]; unsigned int *
0x18003c873  mov     r9, [rsp+410h+var_398]
0x18003c878  mov     rax, 0CCCCCCCCCCCCCCCDh
  ... truncated ...
```
