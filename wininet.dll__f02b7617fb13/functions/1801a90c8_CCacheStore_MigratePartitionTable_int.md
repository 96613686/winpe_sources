# CCacheStore::MigratePartitionTable(int *)

- ea: `0x1801a90c8`
- end: `0x1801a9973`
- name: `?MigratePartitionTable@CCacheStore@@QEAAJPEAH@Z`
- size: `2219`
- prototype: `__int64 __fastcall(CCacheStore *__hidden this, int *)`
- caller_count: `1`
- callee_count: `16`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x180040770`

## callees

- `0x180025910`
- `0x180027ec0`
- `0x180040cf4`
- `0x18007ec9c`
- `0x18007fbc4`
- `0x18010a83c`
- `0x18014a7a0`
- `0x18014b3b4`
- `0x1801a87b8`
- `0x1801a8bac`
- `0x1801a90c8`
- `0x1801afe74`
- `0x1801c9c19`
- `0x1801e1790`
- `0x1801e3c24`
- `0x1801e3c78`

## import_xrefs

- `ESENT!JetCloseTable` at `0x1801a9502`
- `ESENT!JetCloseTable` at `0x1801a952a`
- `ESENT!JetCloseTable` at `0x1801a983a`
- `ESENT!JetCloseTable` at `0x1801a98f9`
- `ESENT!JetCloseTable` at `0x1801a9502`
- `ESENT!JetCloseTable` at `0x1801a952a`
- `ESENT!JetCloseTable` at `0x1801a983a`
- `ESENT!JetCloseTable` at `0x1801a98f9`
- `ESENT!JetCloseDatabase` at `0x1801a9548`
- `ESENT!JetCloseDatabase` at `0x1801a957e`
- `ESENT!JetCloseDatabase` at `0x1801a985a`
- `ESENT!JetCloseDatabase` at `0x1801a9548`
- `ESENT!JetCloseDatabase` at `0x1801a957e`
- `ESENT!JetCloseDatabase` at `0x1801a985a`
- `ESENT!JetSetCurrentIndex2W` at `0x1801a94a0`
- `ESENT!JetSetCurrentIndex2W` at `0x1801a94a0`
- `ESENT!JetOpenTableW` at `0x1801a929c`
- `ESENT!JetOpenTableW` at `0x1801a9371`
- `ESENT!JetOpenTableW` at `0x1801a929c`
- `ESENT!JetOpenTableW` at `0x1801a9371`
- `ESENT!JetCreateTableColumnIndexW` at `0x1801a9423`
- `ESENT!JetCreateTableColumnIndexW` at `0x1801a9423`
- `ESENT!JetDeleteTableW` at `0x1801a98a8`
- `ESENT!JetDeleteTableW` at `0x1801a98a8`
- `ESENT!JetCreateIndex2W` at `0x1801a9479`
- `ESENT!JetCreateIndex2W` at `0x1801a9479`
- `ESENT!JetEndSession` at `0x1801a9560`
- `ESENT!JetEndSession` at `0x1801a9596`
- `ESENT!JetEndSession` at `0x1801a986e`
- `ESENT!JetEndSession` at `0x1801a9560`
- `ESENT!JetEndSession` at `0x1801a9596`
- `ESENT!JetEndSession` at `0x1801a986e`
- `ESENT!JetCommitTransaction` at `0x1801a9928`
- `ESENT!JetCommitTransaction` at `0x1801a9928`
- `ESENT!JetRollback` at `0x1801a94ef`
- `ESENT!JetRollback` at `0x1801a9517`
- `ESENT!JetRollback` at `0x1801a9827`
- `ESENT!JetRollback` at `0x1801a94ef`
- `ESENT!JetRollback` at `0x1801a9517`
- `ESENT!JetRollback` at `0x1801a9827`
- `ESENT!JetBeginTransaction` at `0x1801a93c2`
- `ESENT!JetBeginTransaction` at `0x1801a93df`
- `ESENT!JetBeginTransaction` at `0x1801a93c2`
- `ESENT!JetBeginTransaction` at `0x1801a93df`
- `ESENT!JetMove` at `0x1801a9810`
- `ESENT!JetMove` at `0x1801a9810`

## pseudocode

```c
__int64 __fastcall CCacheStore::MigratePartitionTable(CCacheStore *this, int *a2)
{
  int v4; // r15d
  int ColumnIdsByType; // ebx
  unsigned int v6; // r8d
  unsigned int v7; // eax
  int v8; // ebx
  unsigned int v9; // r8d
  JET_ERR v10; // eax
  JET_ERR v11; // eax
  JET_ERR v12; // eax
  JET_ERR v13; // eax
  JET_ERR v14; // eax
  JET_ERR v15; // eax
  int i; // r8d
  const unsigned __int16 *v18; // rbx
  wchar_t *v19; // rax
  int v20; // ecx
  int v21; // edx
  wchar_t *v22; // rax
  int v23; // ecx
  int v24; // edx
  JET_ERR v25; // eax
  unsigned int v26; // eax
  int v27; // ebx
  JET_ERR v28; // eax
  unsigned int cbParameters; // [rsp+20h] [rbp-E0h]
  unsigned int cbParametersa; // [rsp+20h] [rbp-E0h]
  JET_TABLECREATE_W ptablecreate; // [rsp+80h] [rbp-80h] BYREF
  struct tagJET_TABLECREATE_W v32; // [rsp+D0h] [rbp-30h] BYREF
  JET_SESID v33; // [rsp+120h] [rbp+20h] BYREF
  JET_DBID dbid; // [rsp+128h] [rbp+28h] BYREF
  JET_DBID v35; // [rsp+12Ch] [rbp+2Ch] BYREF
  JET_SESID sesid; // [rsp+130h] [rbp+30h] BYREF
  JET_TABLEID tableid; // [rsp+138h] [rbp+38h] BYREF
  JET_TABLEID ptableid; // [rsp+140h] [rbp+40h] BYREF
  int v39; // [rsp+148h] [rbp+48h] BYREF
  unsigned int v40; // [rsp+14Ch] [rbp+4Ch] BYREF
  unsigned int *v41; // [rsp+150h] [rbp+50h] BYREF
  unsigned int *v42; // [rsp+158h] [rbp+58h] BYREF
  struct _FILETIME v43; // [rsp+160h] [rbp+60h] BYREF
  unsigned __int64 v44; // [rsp+168h] [rbp+68h] BYREF
  _QWORD v45[2]; // [rsp+170h] [rbp+70h] BYREF
  _QWORD v46[2]; // [rsp+180h] [rbp+80h] BYREF
  wchar_t *String1[2]; // [rsp+190h] [rbp+90h] BYREF
  _QWORD v48[2]; // [rsp+1A0h] [rbp+A0h] BYREF
  _QWORD v49[2]; // [rsp+1B0h] [rbp+B0h] BYREF
  JET_INDEXCREATE_W pindexcreate; // [rsp+1C0h] [rbp+C0h] BYREF
  struct tagJET_INDEXCREATE_W v51; // [rsp+210h] [rbp+110h] BYREF
  struct tagJET_INDEXCREATE_W v52; // [rsp+300h] [rbp+200h] BYREF
  struct tag_JET_COLUMNCREATE_W v53; // [rsp+3F0h] [rbp+2F0h] BYREF
  struct tag_JET_COLUMNCREATE_W v54; // [rsp+970h] [rbp+870h] BYREF

  memset_0(&ptablecreate, 0, sizeof(ptablecreate));
  memset_0(&v32, 0, sizeof(v32));
  pindexcreate = c_MigrationPartitionTableIdIndex;
  v4 = 0;
  sesid = -1;
  dbid = -1;
  ptableid = -1;
  v33 = -1;
  v35 = -1;
  tableid = -1;
  v49[0] = &Data;
  v49[1] = 0;
  v48[0] = &Data;
  v48[1] = 0;
  v44 = 0;
  String1[0] = (wchar_t *)&Data;
  String1[1] = 0;
  v46[0] = &Data;
  v46[1] = 0;
  v40 = 0;
  v39 = 0;
  v45[0] = &Data;
  v45[1] = 0;
  v43 = 0;
  v42 = 0;
  v41 = 0;
  if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
    WPP_SF_q(1036, 62, WPP_d2eb1eb319bd39627e3f05ba48018899_Traceguids, this);
  *a2 = 0;
  ColumnIdsByType = CCacheStore::NewLocalSession(this, &sesid, &dbid);
  if ( ColumnIdsByType < 0 )
    goto LABEL_28;
  ColumnIdsByType = InitializeTableDescriptorByType(L"PartitionsEx", 9u, v6, &v53, cbParameters, &v51, &ptablecreate);
  if ( ColumnIdsByType < 0 )
    goto LABEL_28;
  v7 = JetOpenTableW(sesid, dbid, ptablecreate.szTableName, 0, 0, 8u, &ptableid);
  v8 = v7;
  if ( v7 != -1305 )
  {
    if ( (BYTE1(xmmword_180266B50) & 0x10) != 0 )
      WPP_SF_d(524, 63, WPP_d2eb1eb319bd39627e3f05ba48018899_Traceguids, v7);
    ColumnIdsByType = HRESULTFromJET_ERR(v8, 1);
    if ( ColumnIdsByType >= 0 )
    {
      *a2 = 1;
LABEL_10:
      ColumnIdsByType = 0;
      goto LABEL_28;
    }
    goto LABEL_28;
  }
  ColumnIdsByType = CCacheStore::NewLocalSession(this, &v33, &v35);
  if ( ColumnIdsByType >= 0 )
  {
    ColumnIdsByType = InitializeTableDescriptorByType(L"Partitions", 4u, v9, &v54, cbParametersa, &v52, &v32);
    if ( ColumnIdsByType >= 0 )
    {
      v10 = JetOpenTableW(v33, v35, v32.szTableName, 0, 0, 8u, &tableid);
      if ( v10 == -1305 )
      {
        if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
          WPP_SF_(1036, 64, WPP_d2eb1eb319bd39627e3f05ba48018899_Traceguids);
        goto LABEL_10;
      }
      ColumnIdsByType = HRESULTFromJET_ERR(v10, 1);
      if ( ColumnIdsByType >= 0 )
      {
        v11 = JetBeginTransaction(v33);
        ColumnIdsByType = HRESULTFromJET_ERR(v11, 1);
        if ( ColumnIdsByType >= 0 )
        {
          v12 = JetBeginTransaction(sesid);
          ColumnIdsByType = HRESULTFromJET_ERR(v12, 1);
          if ( ColumnIdsByType < 0 )
            goto LABEL_27;
          v4 = 1;
          if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
            WPP_SF_(1036, 65, WPP_d2eb1eb319bd39627e3f05ba48018899_Traceguids);
          v13 = JetCreateTableColumnIndexW(sesid, dbid, &ptablecreate);
          ColumnIdsByType = HRESULTFromJET_ERR(v13, 1);
          if ( ColumnIdsByType < 0 )
            goto LABEL_27;
          ptableid = ptablecreate.tableid;
          ptablecreate.tableid = -1;
          if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
            WPP_SF_(1036, 66, WPP_d2eb1eb319bd39627e3f05ba48018899_Traceguids);
          v14 = JetCreateIndex2W(v33, tableid, &pindexcreate, 1u);
          ColumnIdsByType = HRESULTFromJET_ERR(v14, 1);
          if ( ColumnIdsByType < 0
            || (v15 = JetSetCurrentIndex2W(v33, tableid, L"PartitionTableIndex", 0),
                ColumnIdsByType = HRESULTFromJET_ERR(v15, 1),
                ColumnIdsByType < 0)
            || (ColumnIdsByType = GetColumnIdsByType(v33, v35, L"Partitions", 4u, &v41), ColumnIdsByType < 0)
            || (ColumnIdsByType = GetColumnIdsByType(sesid, dbid, L"PartitionsEx", 9u, &v42), ColumnIdsByType < 0) )
          {
LABEL_27:
            JetRollback(v33, 0);
            goto LABEL_28;
          }
          for ( i = 0x80000000; ; i = 1 )
          {
            v25 = JetMove(v33, tableid, i, 0);
            if ( v25 == -1603 )
              break;
            ColumnIdsByType = HRESULTFromJET_ERR(v25, 1);
            if ( ColumnIdsByType < 0 )
              goto LABEL_27;
            ColumnIdsByType = CCacheStore::GetObsoletePartitionAtCursor(
                                this,
                                v33,
                                tableid,
                                v41,
                                &v44,
                                (struct CWxString *)String1,
                                &v40,
                                (enum PartitionSets *)&v39,
                                (struct CWxString *)v45,
                                &v43);
            if ( ColumnIdsByType < 0 )
              goto LABEL_27;
            v18 = String1[0];
            v19 = String1[0];
            do
            {
              v20 = *(unsigned __int16 *)((char *)v19 + (char *)&c_wszLowIl - (char *)String1[0]);
              v21 = *v19 - v20;
              if ( v21 )
                break;
              ++v19;
            }
            while ( v20 );
            if ( v21 )
            {
              v22 = String1[0];
              do
              {
                v23 = *(unsigned __int16 *)((char *)v22 + "M" - (char *)String1[0]);
                v24 = *v22 - v23;
                if ( v24 )
                  break;
                ++v22;
              }
              while ( v23 );
              if ( v24 && wcsncmp_0(String1[0], L"S-", 2u) )
              {
                if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
                  WPP_SF_(1036, 67, WPP_d2eb1eb319bd39627e3f05ba48018899_Traceguids);
                ColumnIdsByType = WxBase64SIDStringToSIDString(v18, (struct CWxString *)v46);
                if ( ColumnIdsByType < 0 )
                  goto LABEL_27;
                v18 = (const unsigned __int16 *)v46[0];
              }
            }
            ColumnIdsByType = ((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _DWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD))CCacheStore::MigratePartitionEntry)(
                                v42,
                                sesid,
                                ptableid,
                                dbid,
                                v44,
                                v18,
                                v40,
                                v39,
                                v45[0],
                                v43,
                                v42,
                                v49,
                                v48);
            if ( ColumnIdsByType < 0 )
              goto LABEL_27;
          }
          JetRollback(v33, 0);
          if ( tableid != -1 )
          {
            JetCloseTable(v33, tableid);
            tableid = -1;
          }
          if ( v35 != -1 )
          {
            if ( v33 == -1 )
            {
LABEL_78:
              if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
                WPP_SF_(1036, 68, WPP_d2eb1eb319bd39627e3f05ba48018899_Traceguids);
              v26 = JetDeleteTableW(sesid, dbid, L"Partitions");
              v27 = v26;
              if ( v26 == -1305 )
                goto LABEL_84;
              if ( (BYTE1(xmmword_180266B50) & 0x10) != 0 )
                WPP_SF_d(524, 69, WPP_d2eb1eb319bd39627e3f05ba48018899_Traceguids, v26);
              ColumnIdsByType = HRESULTFromJET_ERR(v27, 1);
              if ( ColumnIdsByType >= 0 )
              {
LABEL_84:
                if ( ptableid != -1 )
                {
                  JetCloseTable(sesid, ptableid);
                  ptableid = -1;
                }
                if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
                  WPP_SF_(1036, 70, WPP_d2eb1eb319bd39627e3f05ba48018899_Traceguids);
                v28 = JetCommitTransaction(sesid, 1u);
                ColumnIdsByType = HRESULTFromJET_ERR(v28, 1);
                if ( ColumnIdsByType >= 0 )
                {
                  v4 = 0;
                  *a2 = 1;
                }
              }
              goto LABEL_28;
            }
            JetCloseDatabase(v33, v35, 0);
            v35 = -1;
          }
          if ( v33 != -1 )
          {
            JetEndSession(v33, 0);
            v33 = -1;
          }
          goto LABEL_78;
        }
      }
    }
  }
LABEL_28:
  if ( ptableid != -1 )
  {
    JetCloseTable(sesid, ptableid);
    ptableid = -1;
  }
  if ( v4 )
    JetRollback(sesid, 0);
  if ( tableid != -1 )
  {
    JetCloseTable(v33, tableid);
    tableid = -1;
  }
  if ( v35 != -1 )
  {
    if ( v33 == -1 )
      goto LABEL_39;
    JetCloseDatabase(v33, v35, 0);
    v35 = -1;
  }
  if ( v33 != -1 )
  {
    JetEndSession(v33, 0);
    v33 = -1;
  }
LABEL_39:
  if ( dbid != -1 )
  {
    if ( sesid == -1 )
      goto LABEL_44;
    JetCloseDatabase(sesid, dbid, 0);
    dbid = -1;
  }
  if ( sesid != -1 )
  {
    JetEndSession(sesid, 0);
    sesid = -1;
  }
LABEL_44:
  if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
    WPP_SF_d(1036, 71, WPP_d2eb1eb319bd39627e3f05ba48018899_Traceguids, (unsigned int)ColumnIdsByType);
  if ( v41 )
    WxFreeHeapEx(&v41);
  if ( v42 )
    WxFreeHeapEx(&v42);
  CWxString::_Release((CWxString *)v45);
  CWxString::_Release((CWxString *)v46);
  CWxString::_Release((CWxString *)String1);
  CWxString::_Release((CWxString *)v48);
  CWxString::_Release((CWxString *)v49);
  return (unsigned int)ColumnIdsByType;
}

```

## disassembly

```asm
0x1801a90c8  mov     [rsp-8+arg_10], rbx
0x1801a90cd  push    rbp
0x1801a90ce  push    rsi
0x1801a90cf  push    rdi
0x1801a90d0  push    r12
0x1801a90d2  push    r13
0x1801a90d4  push    r14
0x1801a90d6  push    r15
0x1801a90d8  lea     rbp, [rsp-0E00h]
0x1801a90e0  sub     rsp, 0F00h
0x1801a90e7  mov     rax, cs:__security_cookie
0x1801a90ee  xor     rax, rsp
0x1801a90f1  mov     [rbp+0E30h+var_40], rax
0x1801a90f8  xor     r12d, r12d
0x1801a90fb  mov     r14, rdx
0x1801a90fe  mov     rsi, rcx
0x1801a9101  mov     [rsp+0F30h+var_EBC], r12d
0x1801a9106  xor     edx, edx; Val
0x1801a9108  lea     rcx, [rbp+0E30h+ptablecreate]; void *
0x1801a910c  lea     ebx, [r12+50h]
0x1801a9111  mov     r8d, ebx; Size
0x1801a9114  call    memset_0
0x1801a9119  mov     r8d, ebx; Size
0x1801a911c  lea     rcx, [rbp+0E30h+var_E60]; void *
0x1801a9120  xor     edx, edx; Val
0x1801a9122  call    memset_0
0x1801a9127  movaps  xmm0, xmmword ptr cs:?c_MigrationPartitionTableIdIndex@@3UtagJET_INDEXCREATE_W@@B; tagJET_INDEXCREATE_W const c_MigrationPartitionTableIdIndex
0x1801a912e  lea     rax, Data
0x1801a9135  movaps  xmm1, xmmword ptr cs:?c_MigrationPartitionTableIdIndex@@3UtagJET_INDEXCREATE_W@@B+10h; tagJET_INDEXCREATE_W const c_MigrationPartitionTableIdIndex
0x1801a913c  or      r13, 0FFFFFFFFFFFFFFFFh
0x1801a9140  movaps  xmmword ptr [rbp+0E30h+pindexcreate.cbStruct], xmm0
0x1801a9147  mov     r15d, r12d
0x1801a914a  movaps  xmm0, xmmword ptr cs:?c_MigrationPartitionTableIdIndex@@3UtagJET_INDEXCREATE_W@@B+20h; tagJET_INDEXCREATE_W const c_MigrationPartitionTableIdIndex
0x1801a9151  movaps  xmmword ptr [rbp+0E30h+pindexcreate.ulDensity], xmm0
0x1801a9158  movaps  xmm0, xmmword ptr cs:?c_MigrationPartitionTableIdIndex@@3UtagJET_INDEXCREATE_W@@B+40h; tagJET_INDEXCREATE_W const c_MigrationPartitionTableIdIndex
0x1801a915f  movaps  xmmword ptr [rbp+0E30h+pindexcreate.szKey], xmm1
0x1801a9166  movaps  xmm1, xmmword ptr cs:?c_MigrationPartitionTableIdIndex@@3UtagJET_INDEXCREATE_W@@B+30h; tagJET_INDEXCREATE_W const c_MigrationPartitionTableIdIndex
0x1801a916d  movaps  xmmword ptr [rbp+0E30h+pindexcreate.cConditionalColumn], xmm0
0x1801a9174  mov     [rbp+0E30h+sesid], r13
0x1801a9178  mov     [rbp+0E30h+dbid], 0FFFFFFFFh
0x1801a917f  mov     [rbp+0E30h+var_DF0], r13
0x1801a9183  mov     [rbp+0E30h+var_E10], r13
0x1801a9187  mov     [rbp+0E30h+var_E04], 0FFFFFFFFh
0x1801a918e  mov     [rbp+0E30h+tableid], r13
0x1801a9192  mov     [rbp+0E30h+var_D80], rax
0x1801a9199  mov     [rbp+0E30h+var_D78], r12
0x1801a91a0  mov     [rbp+0E30h+var_D90], rax
0x1801a91a7  mov     [rbp+0E30h+var_D88], r12
0x1801a91ae  mov     [rbp+0E30h+var_DC8], r12
0x1801a91b2  mov     [rbp+0E30h+String1], rax
0x1801a91b9  mov     [rbp+0E30h+var_D98], r12
0x1801a91c0  mov     [rbp+0E30h+var_DB0], rax
0x1801a91c7  mov     [rbp+0E30h+var_DA8], r12
0x1801a91ce  mov     [rbp+0E30h+var_DE4], r12d
0x1801a91d2  mov     [rbp+0E30h+var_DE8], r12d
0x1801a91d6  mov     [rbp+0E30h+var_DC0], rax
0x1801a91da  mov     [rbp+0E30h+var_DB8], r12
0x1801a91de  mov     qword ptr [rbp+0E30h+var_DD0.dwLowDateTime], r12
0x1801a91e2  mov     [rbp+0E30h+var_DD8], r12
0x1801a91e6  mov     [rbp+0E30h+var_DE0], r12
0x1801a91ea  movaps  xmmword ptr [rbp+0E30h+pindexcreate.30h], xmm1
0x1801a91f1  test    byte ptr cs:xmmword_180266B60+1, 10h
0x1801a91f8  jz      short loc_1801A9211
0x1801a91fa  lea     edx, [rbx-12h]
0x1801a91fd  mov     ecx, 40Ch
0x1801a9202  mov     r9, rsi
0x1801a9205  lea     r8, WPP_d2eb1eb319bd39627e3f05ba48018899_Traceguids
0x1801a920c  call    WPP_SF_q
0x1801a9211  lea     r8, [rbp+0E30h+dbid]; unsigned int *
0x1801a9215  mov     [r14], r12d
0x1801a9218  lea     rdx, [rbp+0E30h+sesid]; unsigned __int64 *
0x1801a921c  mov     rcx, rsi; this
0x1801a921f  call    ?NewLocalSession@CCacheStore@@QEAAJPEA_KPEAK@Z; CCacheStore::NewLocalSession(unsigned __int64 *,ulong *)
0x1801a9224  mov     ebx, eax
0x1801a9226  test    eax, eax
0x1801a9228  jns     short loc_1801A9237
0x1801a922a  mov     [rsp+0F30h+var_EBC], 0D8Ch
0x1801a9232  jmp     loc_1801A94F5
0x1801a9237  lea     rax, [rbp+0E30h+ptablecreate]
0x1801a923b  mov     edx, 9; unsigned int
0x1801a9240  mov     [rsp+0F30h+ptableid], rax; struct tagJET_TABLECREATE_W *
0x1801a9245  lea     r9, [rbp+0E30h+var_B40]; struct tag_JET_COLUMNCREATE_W *
0x1801a924c  lea     rax, [rbp+0E30h+var_D20]
0x1801a9253  lea     rcx, ?c_wszPartitionTable@@3QBGB; "PartitionsEx"
0x1801a925a  mov     qword ptr [rsp+0F30h+grbit], rax; struct tagJET_INDEXCREATE_W *
0x1801a925f  call    ?InitializeTableDescriptorByType@@YAJPEBGKKPEAUtag_JET_COLUMNCREATE_W@@KPEAUtagJET_INDEXCREATE_W@@PEAUtagJET_TABLECREATE_W@@@Z; InitializeTableDescriptorByType(ushort const *,ulong,ulong,tag_JET_COLUMNCREATE_W *,ulong,tagJET_INDEXCREATE_W *,tagJET_TABLECREATE_W *)
0x1801a9264  mov     ebx, eax
0x1801a9266  test    eax, eax
0x1801a9268  jns     short loc_1801A9277
0x1801a926a  mov     [rsp+0F30h+var_EBC], 0D93h
0x1801a9272  jmp     loc_1801A94F5
0x1801a9277  mov     r8, [rbp+0E30h+ptablecreate.szTableName]; szTableName
0x1801a927b  lea     rax, [rbp+0E30h+var_DF0]
0x1801a927f  mov     edx, [rbp+0E30h+dbid]; dbid
0x1801a9282  mov     edi, 8
0x1801a9287  mov     rcx, [rbp+0E30h+sesid]; sesid
0x1801a928b  xor     r9d, r9d; pvParameters
0x1801a928e  mov     [rsp+0F30h+ptableid], rax; ptableid
0x1801a9293  mov     [rsp+0F30h+grbit], edi; grbit
0x1801a9297  mov     [rsp+0F30h+cbParameters], r12d; unsigned int
0x1801a929c  call    cs:__imp_JetOpenTableW
0x1801a92a2  mov     ebx, eax
0x1801a92a4  cmp     eax, 0FFFFFAE7h
0x1801a92a9  jz      short loc_1801A92EE
0x1801a92ab  test    byte ptr cs:xmmword_180266B50+1, 10h
0x1801a92b2  jz      short loc_1801A92CB
0x1801a92b4  lea     edx, [rdi+37h]
0x1801a92b7  mov     ecx, 20Ch
0x1801a92bc  mov     r9d, eax
0x1801a92bf  lea     r8, WPP_d2eb1eb319bd39627e3f05ba48018899_Traceguids
0x1801a92c6  call    WPP_SF_d
0x1801a92cb  mov     edi, 1
0x1801a92d0  mov     ecx, ebx; int
0x1801a92d2  mov     edx, edi; int
0x1801a92d4  call    ?HRESULTFromJET_ERR@@YAJJH@Z; HRESULTFromJET_ERR(long,int)
0x1801a92d9  mov     ebx, eax
0x1801a92db  test    eax, eax
0x1801a92dd  js      loc_1801A94F5
0x1801a92e3  mov     [r14], edi
0x1801a92e6  mov     ebx, r12d
0x1801a92e9  jmp     loc_1801A94F5
0x1801a92ee  lea     r8, [rbp+0E30h+var_E04]; unsigned int *
0x1801a92f2  mov     rcx, rsi; this
0x1801a92f5  lea     rdx, [rbp+0E30h+var_E10]; unsigned __int64 *
0x1801a92f9  call    ?NewLocalSession@CCacheStore@@QEAAJPEA_KPEAK@Z; CCacheStore::NewLocalSession(unsigned __int64 *,ulong *)
0x1801a92fe  mov     ebx, eax
0x1801a9300  test    eax, eax
0x1801a9302  jns     short loc_1801A9311
0x1801a9304  mov     [rsp+0F30h+var_EBC], 0DACh
0x1801a930c  jmp     loc_1801A94F5
0x1801a9311  lea     rax, [rbp+0E30h+var_E60]
0x1801a9315  mov     edx, 4; unsigned int
0x1801a931a  mov     [rsp+0F30h+ptableid], rax; struct tagJET_TABLECREATE_W *
0x1801a931f  lea     r9, [rbp+0E30h+var_5C0]; struct tag_JET_COLUMNCREATE_W *
0x1801a9326  lea     rax, [rbp+0E30h+var_C30]
0x1801a932d  lea     rcx, ?c_wszPartitionTableObs@@3QBGB; "Partitions"
0x1801a9334  mov     qword ptr [rsp+0F30h+grbit], rax; struct tagJET_INDEXCREATE_W *
0x1801a9339  call    ?InitializeTableDescriptorByType@@YAJPEBGKKPEAUtag_JET_COLUMNCREATE_W@@KPEAUtagJET_INDEXCREATE_W@@PEAUtagJET_TABLECREATE_W@@@Z; InitializeTableDescriptorByType(ushort const *,ulong,ulong,tag_JET_COLUMNCREATE_W *,ulong,tagJET_INDEXCREATE_W *,tagJET_TABLECREATE_W *)
0x1801a933e  mov     ebx, eax
0x1801a9340  test    eax, eax
0x1801a9342  jns     short loc_1801A9351
0x1801a9344  mov     [rsp+0F30h+var_EBC], 0DB4h
0x1801a934c  jmp     loc_1801A94F5
0x1801a9351  mov     r8, [rbp+0E30h+var_E60.szTableName]; szTableName
0x1801a9355  lea     rax, [rbp+0E30h+tableid]
0x1801a9359  mov     edx, [rbp+0E30h+var_E04]; dbid
0x1801a935c  xor     r9d, r9d; pvParameters
0x1801a935f  mov     rcx, [rbp+0E30h+var_E10]; sesid
0x1801a9363  mov     [rsp+0F30h+ptableid], rax; ptableid
0x1801a9368  mov     [rsp+0F30h+grbit], edi; grbit
0x1801a936c  mov     [rsp+0F30h+cbParameters], r12d; cbParameters
0x1801a9371  call    cs:__imp_JetOpenTableW
0x1801a9377  cmp     eax, 0FFFFFAE7h
0x1801a937c  jnz     short loc_1801A93A6
0x1801a937e  test    byte ptr cs:xmmword_180266B60+1, 10h
0x1801a9385  jz      loc_1801A92E6
0x1801a938b  mov     edx, 40h ; '@'
0x1801a9390  lea     r8, WPP_d2eb1eb319bd39627e3f05ba48018899_Traceguids
0x1801a9397  mov     ecx, 40Ch
0x1801a939c  call    WPP_SF_
0x1801a93a1  jmp     loc_1801A92E6
0x1801a93a6  mov     edi, 1
0x1801a93ab  mov     ecx, eax; int
0x1801a93ad  mov     edx, edi; int
0x1801a93af  call    ?HRESULTFromJET_ERR@@YAJJH@Z; HRESULTFromJET_ERR(long,int)
0x1801a93b4  mov     ebx, eax
0x1801a93b6  test    eax, eax
0x1801a93b8  js      loc_1801A94F5
0x1801a93be  mov     rcx, [rbp+0E30h+var_E10]; sesid
0x1801a93c2  call    cs:__imp_JetBeginTransaction
0x1801a93c8  mov     ecx, eax; int
0x1801a93ca  mov     edx, edi; int
0x1801a93cc  call    ?HRESULTFromJET_ERR@@YAJJH@Z; HRESULTFromJET_ERR(long,int)
0x1801a93d1  mov     ebx, eax
0x1801a93d3  test    eax, eax
0x1801a93d5  js      loc_1801A94F5
0x1801a93db  mov     rcx, [rbp+0E30h+sesid]; sesid
0x1801a93df  call    cs:__imp_JetBeginTransaction
0x1801a93e5  mov     ecx, eax; int
0x1801a93e7  mov     edx, edi; int
0x1801a93e9  call    ?HRESULTFromJET_ERR@@YAJJH@Z; HRESULTFromJET_ERR(long,int)
0x1801a93ee  mov     ebx, eax
0x1801a93f0  test    eax, eax
0x1801a93f2  js      loc_1801A94E9
0x1801a93f8  mov     r15d, edi
0x1801a93fb  test    byte ptr cs:xmmword_180266B60+1, 10h
0x1801a9402  jz      short loc_1801A9418
0x1801a9404  lea     edx, [rdi+40h]
0x1801a9407  mov     ecx, 40Ch
0x1801a940c  lea     r8, WPP_d2eb1eb319bd39627e3f05ba48018899_Traceguids
0x1801a9413  call    WPP_SF_
0x1801a9418  mov     edx, [rbp+0E30h+dbid]; dbid
0x1801a941b  lea     r8, [rbp+0E30h+ptablecreate]; ptablecreate
0x1801a941f  mov     rcx, [rbp+0E30h+sesid]; sesid
0x1801a9423  call    cs:__imp_JetCreateTableColumnIndexW
0x1801a9429  mov     ecx, eax; int
0x1801a942b  mov     edx, edi; int
0x1801a942d  call    ?HRESULTFromJET_ERR@@YAJJH@Z; HRESULTFromJET_ERR(long,int)
0x1801a9432  mov     ebx, eax
0x1801a9434  test    eax, eax
0x1801a9436  js      loc_1801A94E9
0x1801a943c  mov     rax, [rbp+0E30h+ptablecreate.tableid]
0x1801a9440  mov     [rbp+0E30h+var_DF0], rax
0x1801a9444  mov     [rbp+0E30h+ptablecreate.tableid], r13
0x1801a9448  test    byte ptr cs:xmmword_180266B60+1, 10h
0x1801a944f  jz      short loc_1801A9467
0x1801a9451  mov     edx, 42h ; 'B'
0x1801a9456  lea     r8, WPP_d2eb1eb319bd39627e3f05ba48018899_Traceguids
0x1801a945d  mov     ecx, 40Ch
0x1801a9462  call    WPP_SF_
0x1801a9467  mov     rdx, [rbp+0E30h+tableid]; tableid
0x1801a946b  lea     r8, [rbp+0E30h+pindexcreate]; pindexcreate
0x1801a9472  mov     rcx, [rbp+0E30h+var_E10]; sesid
0x1801a9476  mov     r9d, edi; cIndexCreate
0x1801a9479  call    cs:__imp_JetCreateIndex2W
0x1801a947f  mov     ecx, eax; int
0x1801a9481  mov     edx, edi; int
0x1801a9483  call    ?HRESULTFromJET_ERR@@YAJJH@Z; HRESULTFromJET_ERR(long,int)
0x1801a9488  mov     ebx, eax
0x1801a948a  test    eax, eax
0x1801a948c  js      short loc_1801A94E9
0x1801a948e  mov     rdx, [rbp+0E30h+tableid]; tableid
0x1801a9492  lea     r8, aPartitiontable; "PartitionTableIndex"
0x1801a9499  mov     rcx, [rbp+0E30h+var_E10]; sesid
0x1801a949d  xor     r9d, r9d; grbit
0x1801a94a0  call    cs:__imp_JetSetCurrentIndex2W
0x1801a94a6  mov     ecx, eax; int
0x1801a94a8  mov     edx, edi; int
0x1801a94aa  call    ?HRESULTFromJET_ERR@@YAJJH@Z; HRESULTFromJET_ERR(long,int)
0x1801a94af  mov     ebx, eax
0x1801a94b1  test    eax, eax
0x1801a94b3  js      short loc_1801A94E9
0x1801a94b5  mov     edx, [rbp+0E30h+var_E04]; dbid
0x1801a94b8  lea     rax, [rbp+0E30h+var_DE0]
0x1801a94bc  mov     rcx, [rbp+0E30h+var_E10]; sesid
0x1801a94c0  lea     r8, ?c_wszPartitionTableObs@@3QBGB; "Partitions"
0x1801a94c7  mov     r9d, 4; unsigned int
0x1801a94cd  mov     qword ptr [rsp+0F30h+cbParameters], rax; unsigned int **
0x1801a94d2  call    ?GetColumnIdsByType@@YAJ_KKPEBGKPEAPEAK@Z; GetColumnIdsByType(unsigned __int64,ulong,ushort const *,ulong,ulong * *)
0x1801a94d7  mov     ebx, eax
0x1801a94d9  test    eax, eax
0x1801a94db  jns     loc_1801A9645
0x1801a94e1  mov     [rsp+0F30h+var_EBC], 0DF7h
0x1801a94e9  mov     rcx, [rbp+0E30h+var_E10]; sesid
0x1801a94ed  xor     edx, edx; grbit
0x1801a94ef  call    cs:__imp_JetRollback
0x1801a94f5  mov     rdx, [rbp+0E30h+var_DF0]; tableid
0x1801a94f9  cmp     rdx, r13
0x1801a94fc  jz      short loc_1801A950C
0x1801a94fe  mov     rcx, [rbp+0E30h+sesid]; sesid
0x1801a9502  call    cs:__imp_JetCloseTable
0x1801a9508  mov     [rbp+0E30h+var_DF0], r13
0x1801a950c  test    r15d, r15d
0x1801a950f  jz      short loc_1801A951D
0x1801a9511  mov     rcx, [rbp+0E30h+sesid]; sesid
0x1801a9515  xor     edx, edx; grbit
0x1801a9517  call    cs:__imp_JetRollback
0x1801a951d  mov     rdx, [rbp+0E30h+tableid]; tableid
0x1801a9521  cmp     rdx, r13
0x1801a9524  jz      short loc_1801A9534
0x1801a9526  mov     rcx, [rbp+0E30h+var_E10]; sesid
0x1801a952a  call    cs:__imp_JetCloseTable
0x1801a9530  mov     [rbp+0E30h+tableid], r13
0x1801a9534  mov     edx, [rbp+0E30h+var_E04]; dbid
0x1801a9537  cmp     edx, 0FFFFFFFFh
0x1801a953a  jz      short loc_1801A9555
0x1801a953c  mov     rcx, [rbp+0E30h+var_E10]; sesid
0x1801a9540  cmp     rcx, r13
0x1801a9543  jz      short loc_1801A956A
0x1801a9545  xor     r8d, r8d; grbit
0x1801a9548  call    cs:__imp_JetCloseDatabase
0x1801a954e  mov     [rbp+0E30h+var_E04], 0FFFFFFFFh
0x1801a9555  mov     rcx, [rbp+0E30h+var_E10]; sesid
0x1801a9559  cmp     rcx, r13
0x1801a955c  jz      short loc_1801A956A
0x1801a955e  xor     edx, edx; grbit
0x1801a9560  call    cs:__imp_JetEndSession
0x1801a9566  mov     [rbp+0E30h+var_E10], r13
0x1801a956a  mov     edx, [rbp+0E30h+dbid]; dbid
0x1801a956d  cmp     edx, 0FFFFFFFFh
0x1801a9570  jz      short loc_1801A958B
0x1801a9572  mov     rcx, [rbp+0E30h+sesid]; sesid
0x1801a9576  cmp     rcx, r13
0x1801a9579  jz      short loc_1801A95A0
0x1801a957b  xor     r8d, r8d; grbit
0x1801a957e  call    cs:__imp_JetCloseDatabase
0x1801a9584  mov     [rbp+0E30h+dbid], 0FFFFFFFFh
0x1801a958b  mov     rcx, [rbp+0E30h+sesid]; sesid
0x1801a958f  cmp     rcx, r13
0x1801a9592  jz      short loc_1801A95A0
0x1801a9594  xor     edx, edx; grbit
0x1801a9596  call    cs:__imp_JetEndSession
0x1801a959c  mov     [rbp+0E30h+sesid], r13
0x1801a95a0  test    byte ptr cs:xmmword_180266B60+1, 10h
0x1801a95a7  jz      short loc_1801A95C2
0x1801a95a9  mov     edx, 47h ; 'G'
0x1801a95ae  lea     r8, WPP_d2eb1eb319bd39627e3f05ba48018899_Traceguids
0x1801a95b5  mov     ecx, 40Ch
0x1801a95ba  mov     r9d, ebx
0x1801a95bd  call    WPP_SF_d
  ... truncated ...
```
