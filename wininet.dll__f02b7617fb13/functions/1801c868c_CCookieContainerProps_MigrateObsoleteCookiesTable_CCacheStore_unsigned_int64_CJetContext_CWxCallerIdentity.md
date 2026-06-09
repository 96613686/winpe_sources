# CCookieContainerProps::MigrateObsoleteCookiesTable(CCacheStore *,unsigned __int64,CJetContext *,CWxCallerIdentity *)

- ea: `0x1801c868c`
- end: `0x1801c8a99`
- name: `?MigrateObsoleteCookiesTable@CCookieContainerProps@@AEAAJPEAVCCacheStore@@_KPEAVCJetContext@@PEAVCWxCallerIdentity@@@Z`
- size: `1037`
- prototype: `__int64 __fastcall(CCookieContainerProps *__hidden this, struct CCacheStore *, unsigned __int64, struct CJetContext *, struct CWxCallerIdentity *)`
- caller_count: `1`
- callee_count: `19`
- tags: `authz_impersonation, installer_update`

## callers

- `0x1800b049c`

## callees

- `0x18001f3a4`
- `0x180020fc4`
- `0x180021360`
- `0x180021cd0`
- `0x180025910`
- `0x180027ec0`
- `0x180040cf4`
- `0x18007ec9c`
- `0x18007fbc4`
- `0x1800ad380`
- `0x1800dc5f0`
- `0x1800e2220`
- `0x1800e8bf0`
- `0x18010a83c`
- `0x18014a7a0`
- `0x18014b3b4`
- `0x1801c8268`
- `0x1801c868c`
- `0x1801e3c78`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1801c88fa`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1801c88fa`
- `ESENT!JetCloseTable` at `0x1801c8a0b`
- `ESENT!JetCloseTable` at `0x1801c8a0b`
- `ESENT!JetCloseDatabase` at `0x1801c8a2b`
- `ESENT!JetCloseDatabase` at `0x1801c8a2b`
- `ESENT!JetSetCurrentIndex2W` at `0x1801c8845`
- `ESENT!JetSetCurrentIndex2W` at `0x1801c8845`
- `ESENT!JetOpenTableW` at `0x1801c87e8`
- `ESENT!JetOpenTableW` at `0x1801c87e8`
- `ESENT!JetEndSession` at `0x1801c8a3f`
- `ESENT!JetEndSession` at `0x1801c8a3f`
- `ESENT!JetRollback` at `0x1801c89f8`
- `ESENT!JetRollback` at `0x1801c89f8`
- `ESENT!JetBeginTransaction` at `0x1801c8862`
- `ESENT!JetBeginTransaction` at `0x1801c8862`
- `ESENT!JetMove` at `0x1801c8935`
- `ESENT!JetMove` at `0x1801c89e3`
- `ESENT!JetMove` at `0x1801c8935`
- `ESENT!JetMove` at `0x1801c89e3`

## pseudocode

```c
__int64 __fastcall CCookieContainerProps::MigrateObsoleteCookiesTable(
        CCookieContainerProps *this,
        struct CCacheStore *a2,
        __int64 a3,
        struct CJetContext *a4)
{
  int ColumnIdsByType; // ebx
  unsigned int v9; // r8d
  JET_ERR v10; // eax
  JET_ERR v11; // eax
  JET_ERR v12; // eax
  unsigned int v13; // r9d
  JET_ERR i; // eax
  unsigned int cbParameters; // [rsp+20h] [rbp-E0h]
  unsigned __int16 *v17[2]; // [rsp+48h] [rbp-B8h] BYREF
  unsigned __int8 *v18; // [rsp+58h] [rbp-A8h] BYREF
  struct tagJET_TABLECREATE_W v19; // [rsp+60h] [rbp-A0h] BYREF
  JET_SESID sesid; // [rsp+B0h] [rbp-50h] BYREF
  JET_DBID dbid; // [rsp+B8h] [rbp-48h] BYREF
  JET_TABLEID tableid; // [rsp+C0h] [rbp-40h] BYREF
  unsigned int v23; // [rsp+C8h] [rbp-38h] BYREF
  unsigned int v24; // [rsp+CCh] [rbp-34h] BYREF
  unsigned int *v25; // [rsp+D0h] [rbp-30h] BYREF
  unsigned __int16 *v26[2]; // [rsp+D8h] [rbp-28h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+E8h] [rbp-18h] BYREF
  struct tagJET_INDEXCREATE_W v28; // [rsp+F0h] [rbp-10h] BYREF
  struct tag_JET_COLUMNCREATE_W v29; // [rsp+1E0h] [rbp+E0h] BYREF

  v17[1] = 0;
  v17[0] = (unsigned __int16 *)&Data;
  memset_0(&v19, 0, sizeof(v19));
  dbid = -1;
  sesid = -1;
  tableid = -1;
  v25 = 0;
  v26[0] = (unsigned __int16 *)&Data;
  v26[1] = 0;
  v18 = 0;
  v24 = 0;
  v23 = 0;
  SystemTimeAsFileTime = 0;
  ColumnIdsByType = CWxString::Format((CWxString *)v17, L"CookieEntry_%I64u", a3);
  if ( ColumnIdsByType >= 0 )
  {
    ColumnIdsByType = CCacheStore::NewLocalSession(a2, &sesid, &dbid);
    if ( ColumnIdsByType >= 0 )
    {
      ColumnIdsByType = InitializeTableDescriptorByType(v17[0], 0xAu, v9, &v29, cbParameters, &v28, &v19);
      if ( ColumnIdsByType >= 0 )
      {
        v10 = JetOpenTableW(sesid, dbid, v19.szTableName, 0, 0, 8u, &tableid);
        if ( v10 == -1305 )
        {
          if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
            WPP_SF_(1036, 52, WPP_f58dbc53e8bb3f1c4b5de2c920940777_Traceguids);
          ColumnIdsByType = 0;
        }
        else
        {
          ColumnIdsByType = HRESULTFromJET_ERR(v10, 1);
          if ( ColumnIdsByType >= 0 )
          {
            v11 = JetSetCurrentIndex2W(sesid, tableid, L"HashEntryIdIndex", 0);
            ColumnIdsByType = HRESULTFromJET_ERR(v11, 1);
            if ( ColumnIdsByType >= 0 )
            {
              v12 = JetBeginTransaction(sesid);
              ColumnIdsByType = HRESULTFromJET_ERR(v12, 1);
              if ( ColumnIdsByType >= 0 )
              {
                ColumnIdsByType = GetColumnIdsByType(sesid, dbid, v17[0], 0xAu, &v25);
                if ( ColumnIdsByType >= 0 )
                {
                  ColumnIdsByType = CWxString::ExtendBuffer((CWxString *)v26, 0x200u);
                  if ( ColumnIdsByType >= 0 )
                  {
                    ColumnIdsByType = WxAlloc<unsigned char,WxHeapAllocator>(0x8000u);
                    if ( ColumnIdsByType >= 0 )
                    {
                      v23 = 0x8000;
                      GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
                      ColumnIdsByType = CJetContext::SetCurrentIndex(
                                          a4,
                                          1u,
                                          L"MinimizedRDomainHashCookieHashIndex",
                                          v13);
                      if ( ColumnIdsByType >= 0 )
                      {
                        for ( i = JetMove(sesid, tableid, 0x80000000, 0); i != -1603; i = JetMove(sesid, tableid, 1, 0) )
                        {
                          ColumnIdsByType = HRESULTFromJET_ERR(i, 1);
                          if ( ColumnIdsByType < 0 )
                            break;
                          if ( (int)GetStringColumn(sesid, tableid, v25[2], (struct CWxString *)v26) >= 0
                            && (int)GetBinaryColumnWithBuffer(sesid, tableid, v25[4], &v18, &v23, &v24) >= 0 )
                          {
                            CCookieContainerProps::MigrateCookieBuffer(
                              this,
                              a4,
                              (union FILETIMEEX *)&SystemTimeAsFileTime,
                              v26[0],
                              v18,
                              v24);
                            CWxString::BoundUpdateLength((CWxString *)v26, 0);
                          }
                        }
                      }
                    }
                  }
                }
                JetRollback(sesid, 0);
              }
            }
          }
        }
      }
    }
  }
  if ( tableid != -1 )
  {
    JetCloseTable(sesid, tableid);
    tableid = -1;
  }
  if ( dbid != -1 )
  {
    if ( sesid == -1 )
      goto LABEL_30;
    JetCloseDatabase(sesid, dbid, 0);
    dbid = -1;
  }
  if ( sesid != -1 )
  {
    JetEndSession(sesid, 0);
    sesid = -1;
  }
LABEL_30:
  WxHeapFree<_WX_AVL_TABLE>(&v18);
  CWxString::_Release((CWxString *)v26);
  if ( v25 )
    WxFreeHeapEx(&v25);
  CWxString::_Release((CWxString *)v17);
  return (unsigned int)ColumnIdsByType;
}

```

## disassembly

```asm
0x1801c868c  push    rbp
0x1801c868e  push    rbx
0x1801c868f  push    rsi
0x1801c8690  push    rdi
0x1801c8691  push    r13
0x1801c8693  push    r14
0x1801c8695  push    r15
0x1801c8697  lea     rbp, [rsp-670h]
0x1801c869f  sub     rsp, 770h
0x1801c86a6  mov     rax, cs:__security_cookie
0x1801c86ad  xor     rax, rsp
0x1801c86b0  mov     [rbp+6A0h+var_40], rax
0x1801c86b7  mov     rdi, rdx
0x1801c86ba  mov     [rsp+7A0h+var_75C], 0
0x1801c86c2  xor     edx, edx; Val
0x1801c86c4  mov     [rsp+7A0h+var_750], 0
0x1801c86cd  mov     rbx, r8
0x1801c86d0  lea     r15, Data
0x1801c86d7  mov     r14, rcx
0x1801c86da  mov     [rsp+7A0h+var_758], r15
0x1801c86df  lea     rcx, [rsp+7A0h+var_740]; void *
0x1801c86e4  mov     rsi, r9
0x1801c86e7  lea     r8d, [rdx+50h]; Size
0x1801c86eb  call    memset_0
0x1801c86f0  or      r13, 0FFFFFFFFFFFFFFFFh
0x1801c86f4  mov     [rbp+6A0h+dbid], 0FFFFFFFFh
0x1801c86fb  mov     r8, rbx
0x1801c86fe  mov     [rbp+6A0h+sesid], r13
0x1801c8702  lea     rdx, ?c_wszCookieEntryTableObs@@3QBGB; "CookieEntry_%I64u"
0x1801c8709  mov     [rbp+6A0h+tableid], r13
0x1801c870d  lea     rcx, [rsp+7A0h+var_758]; this
0x1801c8712  mov     [rbp+6A0h+var_6D0], 0
0x1801c871a  mov     [rbp+6A0h+var_6C8], r15
0x1801c871e  mov     [rbp+6A0h+var_6C0], 0
0x1801c8726  mov     [rsp+7A0h+var_748], 0
0x1801c872f  mov     [rbp+6A0h+var_6D4], 0
0x1801c8736  mov     [rbp+6A0h+var_6D8], 0
0x1801c873d  mov     qword ptr [rbp+6A0h+SystemTimeAsFileTime.dwLowDateTime], 0
0x1801c8745  call    ?Format@CWxString@@QEAAJPEBGZZ; CWxString::Format(ushort const *,...)
0x1801c874a  mov     ebx, eax
0x1801c874c  test    eax, eax
0x1801c874e  jns     short loc_1801C875D
0x1801c8750  mov     [rsp+7A0h+var_75C], 7E0h
0x1801c8758  jmp     loc_1801C89FE
0x1801c875d  lea     r8, [rbp+6A0h+dbid]; unsigned int *
0x1801c8761  mov     rcx, rdi; this
0x1801c8764  lea     rdx, [rbp+6A0h+sesid]; unsigned __int64 *
0x1801c8768  call    ?NewLocalSession@CCacheStore@@QEAAJPEA_KPEAK@Z; CCacheStore::NewLocalSession(unsigned __int64 *,ulong *)
0x1801c876d  mov     ebx, eax
0x1801c876f  test    eax, eax
0x1801c8771  jns     short loc_1801C8780
0x1801c8773  mov     [rsp+7A0h+var_75C], 7E2h
0x1801c877b  jmp     loc_1801C89FE
0x1801c8780  mov     rcx, [rsp+7A0h+var_758]; unsigned __int16 *
0x1801c8785  lea     rax, [rsp+7A0h+var_740]
0x1801c878a  mov     [rsp+7A0h+ptableid], rax; struct tagJET_TABLECREATE_W *
0x1801c878f  lea     r9, [rbp+6A0h+var_5C0]; struct tag_JET_COLUMNCREATE_W *
0x1801c8796  lea     rax, [rbp+6A0h+var_6B0]
0x1801c879a  mov     r15d, 0Ah
0x1801c87a0  mov     edx, r15d; unsigned int
0x1801c87a3  mov     qword ptr [rsp+7A0h+grbit], rax; struct tagJET_INDEXCREATE_W *
0x1801c87a8  call    ?InitializeTableDescriptorByType@@YAJPEBGKKPEAUtag_JET_COLUMNCREATE_W@@KPEAUtagJET_INDEXCREATE_W@@PEAUtagJET_TABLECREATE_W@@@Z; InitializeTableDescriptorByType(ushort const *,ulong,ulong,tag_JET_COLUMNCREATE_W *,ulong,tagJET_INDEXCREATE_W *,tagJET_TABLECREATE_W *)
0x1801c87ad  mov     ebx, eax
0x1801c87af  test    eax, eax
0x1801c87b1  jns     short loc_1801C87C0
0x1801c87b3  mov     [rsp+7A0h+var_75C], 7EAh
0x1801c87bb  jmp     loc_1801C89FE
0x1801c87c0  mov     r8, [rsp+7A0h+var_740.szTableName]; szTableName
0x1801c87c5  lea     rax, [rbp+6A0h+tableid]
0x1801c87c9  mov     edx, [rbp+6A0h+dbid]; dbid
0x1801c87cc  xor     r9d, r9d; pvParameters
0x1801c87cf  mov     rcx, [rbp+6A0h+sesid]; sesid
0x1801c87d3  mov     [rsp+7A0h+ptableid], rax; ptableid
0x1801c87d8  mov     [rsp+7A0h+grbit], 8; grbit
0x1801c87e0  mov     [rsp+7A0h+cbParameters], 0; cbParameters
0x1801c87e8  call    cs:__imp_JetOpenTableW
0x1801c87ee  cmp     eax, 0FFFFFAE7h
0x1801c87f3  jnz     short loc_1801C881B
0x1801c87f5  test    byte ptr cs:xmmword_180266B60+1, 10h
0x1801c87fc  jz      short loc_1801C8814
0x1801c87fe  mov     edx, 34h ; '4'
0x1801c8803  lea     r8, WPP_f58dbc53e8bb3f1c4b5de2c920940777_Traceguids
0x1801c880a  mov     ecx, 40Ch
0x1801c880f  call    WPP_SF_
0x1801c8814  xor     ebx, ebx
0x1801c8816  jmp     loc_1801C89FE
0x1801c881b  mov     edi, 1
0x1801c8820  mov     ecx, eax; int
0x1801c8822  mov     edx, edi; int
0x1801c8824  call    ?HRESULTFromJET_ERR@@YAJJH@Z; HRESULTFromJET_ERR(long,int)
0x1801c8829  mov     ebx, eax
0x1801c882b  test    eax, eax
0x1801c882d  js      loc_1801C89FE
0x1801c8833  mov     rdx, [rbp+6A0h+tableid]; tableid
0x1801c8837  lea     r8, aHashentryidind; "HashEntryIdIndex"
0x1801c883e  mov     rcx, [rbp+6A0h+sesid]; sesid
0x1801c8842  xor     r9d, r9d; grbit
0x1801c8845  call    cs:__imp_JetSetCurrentIndex2W
0x1801c884b  mov     ecx, eax; int
0x1801c884d  mov     edx, edi; int
0x1801c884f  call    ?HRESULTFromJET_ERR@@YAJJH@Z; HRESULTFromJET_ERR(long,int)
0x1801c8854  mov     ebx, eax
0x1801c8856  test    eax, eax
0x1801c8858  js      loc_1801C89FE
0x1801c885e  mov     rcx, [rbp+6A0h+sesid]; sesid
0x1801c8862  call    cs:__imp_JetBeginTransaction
0x1801c8868  mov     ecx, eax; int
0x1801c886a  mov     edx, edi; int
0x1801c886c  call    ?HRESULTFromJET_ERR@@YAJJH@Z; HRESULTFromJET_ERR(long,int)
0x1801c8871  mov     ebx, eax
0x1801c8873  test    eax, eax
0x1801c8875  js      loc_1801C89FE
0x1801c887b  mov     r8, [rsp+7A0h+var_758]; unsigned __int16 *
0x1801c8880  lea     rax, [rbp+6A0h+var_6D0]
0x1801c8884  mov     edx, [rbp+6A0h+dbid]; dbid
0x1801c8887  mov     r9d, r15d; unsigned int
0x1801c888a  mov     rcx, [rbp+6A0h+sesid]; sesid
0x1801c888e  mov     qword ptr [rsp+7A0h+cbParameters], rax; unsigned int **
0x1801c8893  call    ?GetColumnIdsByType@@YAJ_KKPEBGKPEAPEAK@Z; GetColumnIdsByType(unsigned __int64,ulong,ushort const *,ulong,ulong * *)
0x1801c8898  mov     ebx, eax
0x1801c889a  test    eax, eax
0x1801c889c  jns     short loc_1801C88AB
0x1801c889e  mov     [rsp+7A0h+var_75C], 801h
0x1801c88a6  jmp     loc_1801C89F2
0x1801c88ab  mov     edx, 200h; unsigned int
0x1801c88b0  lea     rcx, [rbp+6A0h+var_6C8]; this
0x1801c88b4  call    ?ExtendBuffer@CWxString@@QEAAJK@Z; CWxString::ExtendBuffer(ulong)
0x1801c88b9  mov     ebx, eax
0x1801c88bb  test    eax, eax
0x1801c88bd  jns     short loc_1801C88CC
0x1801c88bf  mov     [rsp+7A0h+var_75C], 803h
0x1801c88c7  jmp     loc_1801C89F2
0x1801c88cc  mov     r15d, 8000h
0x1801c88d2  lea     rdx, [rsp+7A0h+var_748]
0x1801c88d7  mov     ecx, r15d; dwBytes
0x1801c88da  call    ??$WxAlloc@EVWxHeapAllocator@@@@YAJKPEAPEAE@Z; WxAlloc<uchar,WxHeapAllocator>(ulong,uchar * *)
0x1801c88df  mov     ebx, eax
0x1801c88e1  test    eax, eax
0x1801c88e3  jns     short loc_1801C88F2
0x1801c88e5  mov     [rsp+7A0h+var_75C], 804h
0x1801c88ed  jmp     loc_1801C89F2
0x1801c88f2  lea     rcx, [rbp+6A0h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1801c88f6  mov     [rbp+6A0h+var_6D8], r15d
0x1801c88fa  call    cs:__imp_GetSystemTimeAsFileTime
0x1801c8900  lea     r8, aMinimizedrdoma_2; "MinimizedRDomainHashCookieHashIndex"
0x1801c8907  mov     edx, edi; unsigned int
0x1801c8909  mov     rcx, rsi; this
0x1801c890c  call    ?SetCurrentIndex@CJetContext@@QEAAJKPEBGK@Z; CJetContext::SetCurrentIndex(ulong,ushort const *,ulong)
0x1801c8911  mov     ebx, eax
0x1801c8913  test    eax, eax
0x1801c8915  jns     short loc_1801C8924
0x1801c8917  mov     [rsp+7A0h+var_75C], 809h
0x1801c891f  jmp     loc_1801C89F2
0x1801c8924  mov     rdx, [rbp+6A0h+tableid]; tableid
0x1801c8928  xor     r9d, r9d; grbit
0x1801c892b  mov     rcx, [rbp+6A0h+sesid]; sesid
0x1801c892f  mov     r8d, 80000000h; cRow
0x1801c8935  call    cs:__imp_JetMove
0x1801c893b  mov     r15d, 0FFFFF9BDh
0x1801c8941  jmp     loc_1801C89E9
0x1801c8946  mov     edx, edi; int
0x1801c8948  mov     ecx, eax; int
0x1801c894a  call    ?HRESULTFromJET_ERR@@YAJJH@Z; HRESULTFromJET_ERR(long,int)
0x1801c894f  mov     ebx, eax
0x1801c8951  test    eax, eax
0x1801c8953  js      loc_1801C89F2
0x1801c8959  mov     r8, [rbp+6A0h+var_6D0]
0x1801c895d  lea     r9, [rbp+6A0h+var_6C8]; struct CWxString *
0x1801c8961  mov     rdx, [rbp+6A0h+tableid]; tableid
0x1801c8965  mov     rcx, [rbp+6A0h+sesid]; sesid
0x1801c8969  mov     r8d, [r8+8]; columnid
0x1801c896d  call    ?GetStringColumn@@YAJ_K0KPEAVCWxString@@@Z; GetStringColumn(unsigned __int64,unsigned __int64,ulong,CWxString *)
0x1801c8972  test    eax, eax
0x1801c8974  js      short loc_1801C89D5
0x1801c8976  mov     r8, [rbp+6A0h+var_6D0]
0x1801c897a  lea     rax, [rbp+6A0h+var_6D4]
0x1801c897e  mov     rdx, [rbp+6A0h+tableid]; unsigned __int64
0x1801c8982  lea     r9, [rsp+7A0h+var_748]; unsigned __int8 **
0x1801c8987  mov     rcx, [rbp+6A0h+sesid]; sesid
0x1801c898b  mov     qword ptr [rsp+7A0h+grbit], rax; unsigned int *
0x1801c8990  lea     rax, [rbp+6A0h+var_6D8]
0x1801c8994  mov     r8d, [r8+10h]; unsigned int
0x1801c8998  mov     qword ptr [rsp+7A0h+cbParameters], rax; unsigned int *
0x1801c899d  call    ?GetBinaryColumnWithBuffer@@YAJ_K0KPEAPEAEPEAK2@Z; GetBinaryColumnWithBuffer(unsigned __int64,unsigned __int64,ulong,uchar * *,ulong *,ulong *)
0x1801c89a2  test    eax, eax
0x1801c89a4  js      short loc_1801C89D5
0x1801c89a6  mov     eax, [rbp+6A0h+var_6D4]
0x1801c89a9  lea     r8, [rbp+6A0h+SystemTimeAsFileTime]; union FILETIMEEX *
0x1801c89ad  mov     r9, [rbp+6A0h+var_6C8]; unsigned __int16 *
0x1801c89b1  mov     rdx, rsi; struct CJetContext *
0x1801c89b4  mov     [rsp+7A0h+grbit], eax; unsigned int
0x1801c89b8  mov     rcx, r14; this
0x1801c89bb  mov     rax, [rsp+7A0h+var_748]
0x1801c89c0  mov     qword ptr [rsp+7A0h+cbParameters], rax; unsigned __int8 *
0x1801c89c5  call    ?MigrateCookieBuffer@CCookieContainerProps@@AEAAJPEAVCJetContext@@PEATFILETIMEEX@@PEAGPEAEK@Z; CCookieContainerProps::MigrateCookieBuffer(CJetContext *,FILETIMEEX *,ushort *,uchar *,ulong)
0x1801c89ca  xor     edx, edx; unsigned int
0x1801c89cc  lea     rcx, [rbp+6A0h+var_6C8]; this
0x1801c89d0  call    ?BoundUpdateLength@CWxString@@QEAAXK@Z; CWxString::BoundUpdateLength(ulong)
0x1801c89d5  mov     rdx, [rbp+6A0h+tableid]; tableid
0x1801c89d9  xor     r9d, r9d; grbit
0x1801c89dc  mov     rcx, [rbp+6A0h+sesid]; sesid
0x1801c89e0  mov     r8d, edi; cRow
0x1801c89e3  call    cs:__imp_JetMove
0x1801c89e9  cmp     eax, r15d
0x1801c89ec  jnz     loc_1801C8946
0x1801c89f2  mov     rcx, [rbp+6A0h+sesid]; sesid
0x1801c89f6  xor     edx, edx; grbit
0x1801c89f8  call    cs:__imp_JetRollback
0x1801c89fe  mov     rdx, [rbp+6A0h+tableid]; tableid
0x1801c8a02  cmp     rdx, r13
0x1801c8a05  jz      short loc_1801C8A15
0x1801c8a07  mov     rcx, [rbp+6A0h+sesid]; sesid
0x1801c8a0b  call    cs:__imp_JetCloseTable
0x1801c8a11  mov     [rbp+6A0h+tableid], r13
0x1801c8a15  mov     edx, [rbp+6A0h+dbid]; dbid
0x1801c8a18  or      edi, 0FFFFFFFFh
0x1801c8a1b  cmp     edx, edi
0x1801c8a1d  jz      short loc_1801C8A34
0x1801c8a1f  mov     rcx, [rbp+6A0h+sesid]; sesid
0x1801c8a23  cmp     rcx, r13
0x1801c8a26  jz      short loc_1801C8A49
0x1801c8a28  xor     r8d, r8d; grbit
0x1801c8a2b  call    cs:__imp_JetCloseDatabase
0x1801c8a31  mov     [rbp+6A0h+dbid], edi
0x1801c8a34  mov     rcx, [rbp+6A0h+sesid]; sesid
0x1801c8a38  cmp     rcx, r13
0x1801c8a3b  jz      short loc_1801C8A49
0x1801c8a3d  xor     edx, edx; grbit
0x1801c8a3f  call    cs:__imp_JetEndSession
0x1801c8a45  mov     [rbp+6A0h+sesid], r13
0x1801c8a49  lea     rcx, [rsp+7A0h+var_748]
0x1801c8a4e  call    ??$WxHeapFree@U_WX_AVL_TABLE@@@@YAXPEAPEAU_WX_AVL_TABLE@@@Z; WxHeapFree<_WX_AVL_TABLE>(_WX_AVL_TABLE * *)
0x1801c8a53  lea     rcx, [rbp+6A0h+var_6C8]; this
0x1801c8a57  call    ?_Release@CWxString@@AEAAXXZ; CWxString::_Release(void)
0x1801c8a5c  cmp     [rbp+6A0h+var_6D0], 0
0x1801c8a61  jz      short loc_1801C8A6C
0x1801c8a63  lea     rcx, [rbp+6A0h+var_6D0]
0x1801c8a67  call    WxFreeHeapEx
0x1801c8a6c  lea     rcx, [rsp+7A0h+var_758]; this
0x1801c8a71  call    ?_Release@CWxString@@AEAAXXZ; CWxString::_Release(void)
0x1801c8a76  mov     eax, ebx
0x1801c8a78  mov     rcx, [rbp+6A0h+var_40]
0x1801c8a7f  xor     rcx, rsp; StackCookie
0x1801c8a82  call    __security_check_cookie
0x1801c8a87  add     rsp, 770h
0x1801c8a8e  pop     r15
0x1801c8a90  pop     r14
0x1801c8a92  pop     r13
0x1801c8a94  pop     rdi
0x1801c8a95  pop     rsi
0x1801c8a96  pop     rbx
0x1801c8a97  pop     rbp
0x1801c8a98  retn
```
