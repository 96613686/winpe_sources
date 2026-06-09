# CCookieContainerProps::MigrateCookieContainer(CCacheStore *,CJetContext *,CWxCallerIdentity *)

- ea: `0x180130918`
- end: `0x180130fbf`
- name: `?MigrateCookieContainer@CCookieContainerProps@@AEAAJPEAVCCacheStore@@PEAVCJetContext@@PEAVCWxCallerIdentity@@@Z`
- size: `1703`
- prototype: `int(CCookieContainerProps *__hidden this, struct CCacheStore *, struct CJetContext *, struct CWxCallerIdentity *)`
- caller_count: `1`
- callee_count: `27`
- tags: `authz_impersonation, installer_update`

## callers

- `0x1800b049c`

## callees

- `0x18001f3a4`
- `0x1800204f8`
- `0x180021360`
- `0x18002153c`
- `0x180021cd0`
- `0x180025910`
- `0x180027ec0`
- `0x180040cf4`
- `0x180046a1c`
- `0x18007ec9c`
- `0x18007ed10`
- `0x18007fbc4`
- `0x180083dc4`
- `0x180086300`
- `0x1800acab8`
- `0x1800dc5f0`
- `0x1800e2220`
- `0x1800e8bf0`
- `0x18010a83c`
- `0x180130918`
- `0x18014a7a0`
- `0x18014b3b4`
- `0x1801c7ea0`
- `0x1801c8268`
- `0x1801e1790`
- `0x1801e3c78`
- `0x1801e49ec`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180130d91`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180130d91`
- `ESENT!JetCloseTable` at `0x180130ec1`
- `ESENT!JetCloseTable` at `0x180130ec1`
- `ESENT!JetCloseDatabase` at `0x180130ee3`
- `ESENT!JetCloseDatabase` at `0x180130ee3`
- `ESENT!JetSetCurrentIndex2W` at `0x180130c98`
- `ESENT!JetSetCurrentIndex2W` at `0x180130c98`
- `ESENT!JetOpenTableW` at `0x180130c4f`
- `ESENT!JetOpenTableW` at `0x180130c4f`
- `ESENT!JetEndSession` at `0x180130ef8`
- `ESENT!JetEndSession` at `0x180130ef8`
- `ESENT!JetRollback` at `0x180130b9e`
- `ESENT!JetRollback` at `0x180130eaa`
- `ESENT!JetRollback` at `0x180130f1f`
- `ESENT!JetRollback` at `0x180130b9e`
- `ESENT!JetRollback` at `0x180130eaa`
- `ESENT!JetRollback` at `0x180130f1f`
- `ESENT!JetBeginTransaction` at `0x180130a56`
- `ESENT!JetBeginTransaction` at `0x180130cb5`
- `ESENT!JetBeginTransaction` at `0x180130a56`
- `ESENT!JetBeginTransaction` at `0x180130cb5`
- `ESENT!JetMove` at `0x180130dcc`
- `ESENT!JetMove` at `0x180130dcc`

## pseudocode

```c
__int64 __fastcall CCookieContainerProps::MigrateCookieContainer(
        CCookieContainerProps *this,
        CJetContextList **a2,
        struct CJetContext *a3,
        const unsigned __int16 **a4)
{
  int v8; // r12d
  int v9; // eax
  unsigned int v10; // r9d
  JET_SESID *v11; // rsi
  int BasicColumn; // ebx
  JET_ERR v13; // eax
  int v14; // eax
  __int64 v15; // rdx
  unsigned int v16; // r8d
  JET_ERR v17; // eax
  JET_ERR v18; // eax
  JET_ERR v19; // eax
  unsigned int v20; // r9d
  int i; // r8d
  JET_ERR v22; // eax
  unsigned int cbParameters; // [rsp+20h] [rbp-E0h]
  const unsigned __int16 *cbParametersa; // [rsp+20h] [rbp-E0h]
  const unsigned __int16 *grbit; // [rsp+28h] [rbp-D8h]
  JET_TABLEID *ptableid; // [rsp+30h] [rbp-D0h]
  const unsigned __int16 *v28; // [rsp+38h] [rbp-C8h]
  const unsigned __int16 *v29; // [rsp+40h] [rbp-C0h]
  const unsigned __int16 *v30; // [rsp+48h] [rbp-B8h]
  const unsigned __int16 *v31; // [rsp+50h] [rbp-B0h]
  unsigned int v32; // [rsp+60h] [rbp-A0h] BYREF
  int v33; // [rsp+64h] [rbp-9Ch]
  unsigned int v34; // [rsp+68h] [rbp-98h] BYREF
  unsigned __int8 *v35; // [rsp+70h] [rbp-90h] BYREF
  struct CJetContext *v36; // [rsp+78h] [rbp-88h] BYREF
  LPCWSTR lpFileName[2]; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int16 *v38[2]; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int16 *v39[2]; // [rsp+A0h] [rbp-60h] BYREF
  struct tagJET_TABLECREATE_W v40; // [rsp+B0h] [rbp-50h] BYREF
  JET_SESID sesid; // [rsp+100h] [rbp+0h] BYREF
  JET_DBID dbid; // [rsp+108h] [rbp+8h] BYREF
  JET_TABLEID tableid; // [rsp+110h] [rbp+10h] BYREF
  unsigned int v44; // [rsp+118h] [rbp+18h] BYREF
  unsigned int *v45; // [rsp+120h] [rbp+20h] BYREF
  unsigned __int16 *v46[2]; // [rsp+128h] [rbp+28h] BYREF
  __int64 v47; // [rsp+138h] [rbp+38h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+140h] [rbp+40h] BYREF
  unsigned __int16 *v49[2]; // [rsp+148h] [rbp+48h] BYREF
  unsigned __int16 *v50[3]; // [rsp+158h] [rbp+58h] BYREF
  struct tagJET_INDEXCREATE_W v51; // [rsp+170h] [rbp+70h] BYREF
  struct tag_JET_COLUMNCREATE_W v52; // [rsp+260h] [rbp+160h] BYREF

  v33 = 0;
  v39[0] = (unsigned __int16 *)&Data;
  v39[1] = 0;
  v36 = 0;
  v47 = 0;
  v38[0] = (unsigned __int16 *)&Data;
  v38[1] = 0;
  v8 = 0;
  v46[0] = (unsigned __int16 *)&Data;
  v46[1] = 0;
  v49[0] = (unsigned __int16 *)&Data;
  v49[1] = 0;
  v50[0] = (unsigned __int16 *)&Data;
  v50[1] = 0;
  lpFileName[0] = &Data;
  lpFileName[1] = 0;
  memset_0(&v40, 0, sizeof(v40));
  dbid = -1;
  sesid = -1;
  tableid = -1;
  v45 = 0;
  v35 = 0;
  v34 = 0;
  SystemTimeAsFileTime = 0;
  v44 = 0;
  if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
    WPP_SF_qqqq(
      1036,
      56,
      (unsigned int)WPP_f58dbc53e8bb3f1c4b5de2c920940777_Traceguids,
      (_DWORD)this,
      (__int64)a2,
      (__int64)a3,
      (__int64)a4);
  v9 = CJetContextList::AcquireContext(a2[40], &v36, 0);
  v11 = (JET_SESID *)v36;
  BasicColumn = v9;
  if ( v9 < 0 )
  {
    v33 = 2248;
    goto LABEL_62;
  }
  BasicColumn = CJetContext::SetCurrentIndex(v36, 1u, L"PartitionIdIndex", v10);
  if ( BasicColumn < 0 )
  {
    v33 = 2249;
    goto LABEL_62;
  }
  v13 = JetBeginTransaction(v11[2]);
  BasicColumn = HRESULTFromJET_ERR(v13, 1);
  if ( BasicColumn >= 0 )
  {
    v8 = 1;
    BasicColumn = CWxString::Set((CWxString *)v39, a4[1]);
    if ( BasicColumn < 0 )
    {
      v33 = 2254;
      goto LABEL_62;
    }
    v14 = SeekToContainer((struct CJetContext *)v11, v39[0], L"Cookies");
    BasicColumn = v14;
    if ( v14 == 1 )
    {
      if ( (BYTE1(xmmword_180266B60) & 0x10) == 0 )
      {
LABEL_14:
        BasicColumn = 0;
        goto LABEL_62;
      }
      v15 = 57;
LABEL_13:
      WPP_SF_(1036, v15, WPP_f58dbc53e8bb3f1c4b5de2c920940777_Traceguids);
      goto LABEL_14;
    }
    if ( v14 >= 0 )
    {
      BasicColumn = CJetContext::GetBasicColumn((CJetContext *)v11, 0, &v47, 8u);
      if ( BasicColumn >= 0 )
      {
        BasicColumn = CJetContext::GetBasicColumn((CJetContext *)v11, 4u, &v44, 4u);
        if ( BasicColumn >= 0 )
        {
          if ( (v44 & 1) != 0 )
          {
            if ( (BYTE1(xmmword_180266B50) & 0x10) != 0 )
              WPP_SF_d(524, 58, WPP_f58dbc53e8bb3f1c4b5de2c920940777_Traceguids, v44);
            BasicColumn = -2147467259;
            v33 = 2274;
          }
          else
          {
            BasicColumn = CJetContext::GetStringColumn((CJetContext *)v11, 7u, (struct CWxString *)v50);
            if ( BasicColumn >= 0 )
            {
              JetRollback(v11[2], 0);
              v8 = 0;
              BasicColumn = CWxString::Format((CWxString *)v38, L"Container_%I64u", v47);
              if ( BasicColumn >= 0 )
              {
                BasicColumn = CCacheStore::NewLocalSession((CCacheStore *)a2, &sesid, &dbid);
                if ( BasicColumn >= 0 )
                {
                  BasicColumn = InitializeTableDescriptorByType(v38[0], 2u, v16, &v52, cbParameters, &v51, &v40);
                  if ( BasicColumn >= 0 )
                  {
                    v17 = JetOpenTableW(sesid, dbid, v40.szTableName, 0, 0, 8u, &tableid);
                    if ( v17 == -1305 )
                    {
                      if ( (BYTE1(xmmword_180266B60) & 0x10) == 0 )
                        goto LABEL_14;
                      v15 = 59;
                      goto LABEL_13;
                    }
                    BasicColumn = HRESULTFromJET_ERR(v17, 1);
                    if ( BasicColumn >= 0 )
                    {
                      v18 = JetSetCurrentIndex2W(sesid, tableid, L"HashEntryIdIndex", 0);
                      BasicColumn = HRESULTFromJET_ERR(v18, 1);
                      if ( BasicColumn >= 0 )
                      {
                        v19 = JetBeginTransaction(sesid);
                        BasicColumn = HRESULTFromJET_ERR(v19, 1);
                        if ( BasicColumn >= 0 )
                        {
                          BasicColumn = GetColumnIdsByType(sesid, dbid, v38[0], 2u, &v45);
                          if ( BasicColumn >= 0 )
                          {
                            BasicColumn = CWxString::ExtendBuffer((CWxString *)v46, 0x200u);
                            if ( BasicColumn >= 0 )
                            {
                              BasicColumn = CWxString::ExtendBuffer((CWxString *)v49, 0x200u);
                              if ( BasicColumn >= 0 )
                              {
                                BasicColumn = CWxString::ExtendBuffer((CWxString *)lpFileName, 0x200u);
                                if ( BasicColumn >= 0 )
                                {
                                  BasicColumn = WxAlloc<unsigned char,WxHeapAllocator>(0x8000u);
                                  if ( BasicColumn >= 0 )
                                  {
                                    v32 = 0x8000;
                                    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
                                    BasicColumn = CJetContext::SetCurrentIndex(
                                                    a3,
                                                    1u,
                                                    L"MinimizedRDomainHashCookieHashIndex",
                                                    v20);
                                    if ( BasicColumn >= 0 )
                                    {
                                      for ( i = 0x80000000; ; i = 1 )
                                      {
                                        v22 = JetMove(sesid, tableid, i, 0);
                                        if ( v22 == -1603 )
                                          break;
                                        BasicColumn = HRESULTFromJET_ERR(v22, 1);
                                        if ( BasicColumn < 0 )
                                          break;
                                        if ( (int)GetStringColumn(sesid, tableid, v45[4], (struct CWxString *)v46) >= 0
                                          && (int)GetStringColumn(sesid, tableid, v45[5], (struct CWxString *)v49) >= 0 )
                                        {
                                          BasicColumn = CWxString::SetPath(
                                                          (CWxString *)lpFileName,
                                                          v50[0],
                                                          v49[0],
                                                          0,
                                                          cbParametersa,
                                                          grbit,
                                                          (const unsigned __int16 *)ptableid,
                                                          v28,
                                                          v29,
                                                          v30,
                                                          v31);
                                          if ( BasicColumn < 0 )
                                          {
                                            v33 = 2350;
                                            break;
                                          }
                                          if ( (int)GetCookieFileData(lpFileName[0], &v35, &v32, &v34) >= 0 )
                                          {
                                            CCookieContainerProps::MigrateCookieBuffer(
                                              this,
                                              a3,
                                              (union FILETIMEEX *)&SystemTimeAsFileTime,
                                              v46[0],
                                              v35,
                                              v34);
                                            CWxString::BoundUpdateLength((CWxString *)v46, 0);
                                          }
                                        }
                                      }
                                    }
                                    else
                                    {
                                      v33 = 2329;
                                    }
                                  }
                                  else
                                  {
                                    v33 = 2324;
                                  }
                                }
                                else
                                {
                                  v33 = 2323;
                                }
                              }
                              else
                              {
                                v33 = 2322;
                              }
                            }
                            else
                            {
                              v33 = 2321;
                            }
                          }
                          else
                          {
                            v33 = 2315;
                          }
                          JetRollback(sesid, 0);
                        }
                      }
                    }
                  }
                  else
                  {
                    v33 = 2292;
                  }
                }
                else
                {
                  v33 = 2284;
                }
              }
              else
              {
                v33 = 2282;
              }
            }
            else
            {
              v33 = 2277;
            }
          }
        }
        else
        {
          v33 = 2267;
        }
      }
      else
      {
        v33 = 2266;
      }
    }
    else
    {
      v33 = 2264;
    }
  }
LABEL_62:
  if ( tableid != -1 )
  {
    JetCloseTable(sesid, tableid);
    tableid = -1;
  }
  if ( dbid != -1 )
  {
    if ( sesid == -1 )
      goto LABEL_69;
    JetCloseDatabase(sesid, dbid, 0);
    dbid = -1;
  }
  if ( sesid != -1 )
  {
    JetEndSession(sesid, 0);
    sesid = -1;
  }
LABEL_69:
  if ( v35 )
    WxFreeHeapEx(&v35);
  if ( v8 )
    JetRollback(v11[2], 0);
  CCacheStore::ReleaseContainerContext((CCacheStore *)a2, &v36);
  if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
    WPP_SF_d(1036, 60, WPP_f58dbc53e8bb3f1c4b5de2c920940777_Traceguids, (unsigned int)BasicColumn);
  if ( v45 )
    WxFreeHeapEx(&v45);
  CWxString::_Release((CWxString *)lpFileName);
  CWxString::_Release((CWxString *)v50);
  CWxString::_Release((CWxString *)v49);
  CWxString::_Release((CWxString *)v46);
  CWxString::_Release((CWxString *)v38);
  CWxString::_Release((CWxString *)v39);
  return (unsigned int)BasicColumn;
}

```

## disassembly

```asm
0x180130918  push    rbp
0x18013091a  push    rbx
0x18013091b  push    rsi
0x18013091c  push    rdi
0x18013091d  push    r12
0x18013091f  push    r13
0x180130921  push    r14
0x180130923  push    r15
0x180130925  lea     rbp, [rsp-6F8h]
0x18013092d  sub     rsp, 7F8h
0x180130934  mov     rax, cs:__security_cookie
0x18013093b  xor     rax, rsp
0x18013093e  mov     [rbp+730h+var_50], rax
0x180130945  xor     ebx, ebx
0x180130947  lea     rax, Data
0x18013094e  mov     r14, r8
0x180130951  mov     [rsp+830h+var_7CC], ebx
0x180130955  mov     r13, rdx
0x180130958  mov     [rbp+730h+var_790], rax
0x18013095c  mov     r15, rcx
0x18013095f  mov     [rbp+730h+var_788], rbx
0x180130963  lea     r8d, [rbx+50h]; Size
0x180130967  mov     [rsp+830h+var_7B8], rbx
0x18013096c  xor     edx, edx; Val
0x18013096e  mov     [rbp+730h+var_6F8], rbx
0x180130972  lea     rcx, [rbp+730h+var_780]; void *
0x180130976  mov     [rbp+730h+var_7A0], rax
0x18013097a  mov     rdi, r9
0x18013097d  mov     [rbp+730h+var_798], rbx
0x180130981  mov     r12d, ebx
0x180130984  mov     [rbp+730h+var_708], rax
0x180130988  mov     [rbp+730h+var_700], rbx
0x18013098c  mov     [rbp+730h+var_6E8], rax
0x180130990  mov     [rbp+730h+var_6E0], rbx
0x180130994  mov     [rbp+730h+var_6D8], rax
0x180130998  mov     [rbp+730h+var_6D0], rbx
0x18013099c  mov     [rbp+730h+lpFileName], rax
0x1801309a0  mov     [rbp+730h+var_7A8], rbx
0x1801309a4  call    memset_0
0x1801309a9  or      rax, 0FFFFFFFFFFFFFFFFh
0x1801309ad  mov     [rbp+730h+dbid], 0FFFFFFFFh
0x1801309b4  mov     [rbp+730h+sesid], rax
0x1801309b8  mov     [rbp+730h+tableid], rax
0x1801309bc  mov     [rbp+730h+var_710], rbx
0x1801309c0  mov     [rsp+830h+var_7C0], rbx
0x1801309c5  mov     [rsp+830h+var_7C8], ebx
0x1801309c9  mov     qword ptr [rbp+730h+SystemTimeAsFileTime.dwLowDateTime], rbx
0x1801309cd  mov     [rbp+730h+var_718], ebx
0x1801309d0  test    byte ptr cs:xmmword_180266B60+1, 10h
0x1801309d7  jz      short loc_1801309FF
0x1801309d9  mov     [rsp+830h+ptableid], rdi
0x1801309de  lea     edx, [rbx+38h]
0x1801309e1  mov     qword ptr [rsp+830h+grbit], r14
0x1801309e6  lea     r8, WPP_f58dbc53e8bb3f1c4b5de2c920940777_Traceguids
0x1801309ed  mov     ecx, 40Ch
0x1801309f2  mov     qword ptr [rsp+830h+cbParameters], r13; unsigned int
0x1801309f7  mov     r9, r15
0x1801309fa  call    WPP_SF_qqqq
0x1801309ff  mov     rcx, [r13+140h]; this
0x180130a06  lea     rdx, [rsp+830h+var_7B8]; struct CJetContext **
0x180130a0b  xor     r8d, r8d; int *
0x180130a0e  call    ?AcquireContext@CJetContextList@@QEAAJPEAPEAVCJetContext@@PEAH@Z; CJetContextList::AcquireContext(CJetContext * *,int *)
0x180130a13  mov     rsi, [rsp+830h+var_7B8]
0x180130a18  mov     ebx, eax
0x180130a1a  test    eax, eax
0x180130a1c  jns     short loc_180130A2B
0x180130a1e  mov     [rsp+830h+var_7CC], 8C8h
0x180130a26  jmp     loc_180130EB0
0x180130a2b  lea     r8, aPartitionidind; "PartitionIdIndex"
0x180130a32  mov     edx, 1; unsigned int
0x180130a37  mov     rcx, rsi; this
0x180130a3a  call    ?SetCurrentIndex@CJetContext@@QEAAJKPEBGK@Z; CJetContext::SetCurrentIndex(ulong,ushort const *,ulong)
0x180130a3f  mov     ebx, eax
0x180130a41  test    eax, eax
0x180130a43  jns     short loc_180130A52
0x180130a45  mov     [rsp+830h+var_7CC], 8C9h
0x180130a4d  jmp     loc_180130EB0
0x180130a52  mov     rcx, [rsi+10h]; sesid
0x180130a56  call    cs:__imp_JetBeginTransaction
0x180130a5c  mov     ecx, eax; int
0x180130a5e  mov     edx, 1; int
0x180130a63  call    ?HRESULTFromJET_ERR@@YAJJH@Z; HRESULTFromJET_ERR(long,int)
0x180130a68  mov     ebx, eax
0x180130a6a  test    eax, eax
0x180130a6c  js      loc_180130EB0
0x180130a72  mov     rdx, [rdi+8]; unsigned __int16 *
0x180130a76  lea     rcx, [rbp+730h+var_790]; this
0x180130a7a  mov     r12d, 1
0x180130a80  call    ?Set@CWxString@@QEAAJPEBG@Z; CWxString::Set(ushort const *)
0x180130a85  mov     ebx, eax
0x180130a87  test    eax, eax
0x180130a89  jns     short loc_180130A98
0x180130a8b  mov     [rsp+830h+var_7CC], 8CEh
0x180130a93  jmp     loc_180130EB0
0x180130a98  mov     rdx, [rbp+730h+var_790]; unsigned __int16 *
0x180130a9c  lea     r8, aCookies; "Cookies"
0x180130aa3  mov     rcx, rsi; struct CJetContext *
0x180130aa6  call    ?SeekToContainer@@YAJPEAVCJetContext@@PEBG1@Z; SeekToContainer(CJetContext *,ushort const *,ushort const *)
0x180130aab  mov     ebx, eax
0x180130aad  mov     edi, r12d
0x180130ab0  cmp     eax, r12d
0x180130ab3  jnz     short loc_180130ADB
0x180130ab5  test    byte ptr cs:xmmword_180266B60+1, 10h
0x180130abc  jz      short loc_180130AD4
0x180130abe  mov     edx, 39h ; '9'
0x180130ac3  mov     ecx, 40Ch
0x180130ac8  lea     r8, WPP_f58dbc53e8bb3f1c4b5de2c920940777_Traceguids
0x180130acf  call    WPP_SF_
0x180130ad4  xor     ebx, ebx
0x180130ad6  jmp     loc_180130EB0
0x180130adb  test    eax, eax
0x180130add  jns     short loc_180130AEC
0x180130adf  mov     [rsp+830h+var_7CC], 8D8h
0x180130ae7  jmp     loc_180130EB0
0x180130aec  mov     r9d, 8; unsigned int
0x180130af2  lea     r8, [rbp+730h+var_6F8]; void *
0x180130af6  xor     edx, edx; unsigned int
0x180130af8  mov     rcx, rsi; this
0x180130afb  call    ?GetBasicColumn@CJetContext@@QEAAJKPEAXK@Z; CJetContext::GetBasicColumn(ulong,void *,ulong)
0x180130b00  mov     ebx, eax
0x180130b02  test    eax, eax
0x180130b04  jns     short loc_180130B13
0x180130b06  mov     [rsp+830h+var_7CC], 8DAh
0x180130b0e  jmp     loc_180130EB0
0x180130b13  mov     edx, 4; unsigned int
0x180130b18  lea     r8, [rbp+730h+var_718]; void *
0x180130b1c  mov     r9d, edx; unsigned int
0x180130b1f  mov     rcx, rsi; this
0x180130b22  call    ?GetBasicColumn@CJetContext@@QEAAJKPEAXK@Z; CJetContext::GetBasicColumn(ulong,void *,ulong)
0x180130b27  mov     ebx, eax
0x180130b29  test    eax, eax
0x180130b2b  jns     short loc_180130B3A
0x180130b2d  mov     [rsp+830h+var_7CC], 8DBh
0x180130b35  jmp     loc_180130EB0
0x180130b3a  mov     r9d, [rbp+730h+var_718]
0x180130b3e  test    dil, r9b
0x180130b41  jz      short loc_180130B74
0x180130b43  test    byte ptr cs:xmmword_180266B50+1, 10h
0x180130b4a  jz      short loc_180130B62
0x180130b4c  mov     edx, 3Ah ; ':'
0x180130b51  lea     r8, WPP_f58dbc53e8bb3f1c4b5de2c920940777_Traceguids
0x180130b58  mov     ecx, 20Ch
0x180130b5d  call    WPP_SF_d
0x180130b62  mov     ebx, 80004005h
0x180130b67  mov     [rsp+830h+var_7CC], 8E2h
0x180130b6f  jmp     loc_180130EB0
0x180130b74  lea     r8, [rbp+730h+var_6D8]; struct CWxString *
0x180130b78  mov     edx, 7; unsigned int
0x180130b7d  mov     rcx, rsi; this
0x180130b80  call    ?GetStringColumn@CJetContext@@QEAAJKPEAVCWxString@@@Z; CJetContext::GetStringColumn(ulong,CWxString *)
0x180130b85  mov     ebx, eax
0x180130b87  test    eax, eax
0x180130b89  jns     short loc_180130B98
0x180130b8b  mov     [rsp+830h+var_7CC], 8E5h
0x180130b93  jmp     loc_180130EB0
0x180130b98  mov     rcx, [rsi+10h]; sesid
0x180130b9c  xor     edx, edx; grbit
0x180130b9e  call    cs:__imp_JetRollback
0x180130ba4  mov     r8, [rbp+730h+var_6F8]
0x180130ba8  lea     rdx, ?c_wszEntryTable@@3QBGB; "Container_%I64u"
0x180130baf  lea     rcx, [rbp+730h+var_7A0]; this
0x180130bb3  xor     r12d, r12d
0x180130bb6  call    ?Format@CWxString@@QEAAJPEBGZZ; CWxString::Format(ushort const *,...)
0x180130bbb  mov     ebx, eax
0x180130bbd  test    eax, eax
0x180130bbf  jns     short loc_180130BCE
0x180130bc1  mov     [rsp+830h+var_7CC], 8EAh
0x180130bc9  jmp     loc_180130EB0
0x180130bce  lea     r8, [rbp+730h+dbid]; unsigned int *
0x180130bd2  mov     rcx, r13; this
0x180130bd5  lea     rdx, [rbp+730h+sesid]; unsigned __int64 *
0x180130bd9  call    ?NewLocalSession@CCacheStore@@QEAAJPEA_KPEAK@Z; CCacheStore::NewLocalSession(unsigned __int64 *,ulong *)
0x180130bde  mov     ebx, eax
0x180130be0  test    eax, eax
0x180130be2  jns     short loc_180130BF1
0x180130be4  mov     [rsp+830h+var_7CC], 8ECh
0x180130bec  jmp     loc_180130EB0
0x180130bf1  mov     rcx, [rbp+730h+var_7A0]; unsigned __int16 *
0x180130bf5  lea     rax, [rbp+730h+var_780]
0x180130bf9  mov     [rsp+830h+ptableid], rax; struct tagJET_TABLECREATE_W *
0x180130bfe  lea     r9, [rbp+730h+var_5D0]; struct tag_JET_COLUMNCREATE_W *
0x180130c05  lea     rax, [rbp+730h+var_6C0]
0x180130c09  mov     edx, 2; unsigned int
0x180130c0e  mov     qword ptr [rsp+830h+grbit], rax; struct tagJET_INDEXCREATE_W *
0x180130c13  call    ?InitializeTableDescriptorByType@@YAJPEBGKKPEAUtag_JET_COLUMNCREATE_W@@KPEAUtagJET_INDEXCREATE_W@@PEAUtagJET_TABLECREATE_W@@@Z; InitializeTableDescriptorByType(ushort const *,ulong,ulong,tag_JET_COLUMNCREATE_W *,ulong,tagJET_INDEXCREATE_W *,tagJET_TABLECREATE_W *)
0x180130c18  mov     ebx, eax
0x180130c1a  test    eax, eax
0x180130c1c  jns     short loc_180130C2B
0x180130c1e  mov     [rsp+830h+var_7CC], 8F4h
0x180130c26  jmp     loc_180130EB0
0x180130c2b  mov     r8, [rbp+730h+var_780.szTableName]; szTableName
0x180130c2f  lea     rax, [rbp+730h+tableid]
0x180130c33  mov     edx, [rbp+730h+dbid]; dbid
0x180130c36  xor     r9d, r9d; pvParameters
0x180130c39  mov     rcx, [rbp+730h+sesid]; sesid
0x180130c3d  mov     [rsp+830h+ptableid], rax; unsigned __int16 *
0x180130c42  mov     [rsp+830h+grbit], 8; unsigned __int16 *
0x180130c4a  mov     [rsp+830h+cbParameters], r12d; cbParameters
0x180130c4f  call    cs:__imp_JetOpenTableW
0x180130c55  cmp     eax, 0FFFFFAE7h
0x180130c5a  jnz     short loc_180130C73
0x180130c5c  test    byte ptr cs:xmmword_180266B60+1, 10h
0x180130c63  jz      loc_180130AD4
0x180130c69  mov     edx, 3Bh ; ';'
0x180130c6e  jmp     loc_180130AC3
0x180130c73  mov     edx, edi; int
0x180130c75  mov     ecx, eax; int
0x180130c77  call    ?HRESULTFromJET_ERR@@YAJJH@Z; HRESULTFromJET_ERR(long,int)
0x180130c7c  mov     ebx, eax
0x180130c7e  test    eax, eax
0x180130c80  js      loc_180130EB0
0x180130c86  mov     rdx, [rbp+730h+tableid]; tableid
0x180130c8a  lea     r8, aHashentryidind; "HashEntryIdIndex"
0x180130c91  mov     rcx, [rbp+730h+sesid]; sesid
0x180130c95  xor     r9d, r9d; grbit
0x180130c98  call    cs:__imp_JetSetCurrentIndex2W
0x180130c9e  mov     ecx, eax; int
0x180130ca0  mov     edx, edi; int
0x180130ca2  call    ?HRESULTFromJET_ERR@@YAJJH@Z; HRESULTFromJET_ERR(long,int)
0x180130ca7  mov     ebx, eax
0x180130ca9  test    eax, eax
0x180130cab  js      loc_180130EB0
0x180130cb1  mov     rcx, [rbp+730h+sesid]; sesid
0x180130cb5  call    cs:__imp_JetBeginTransaction
0x180130cbb  mov     ecx, eax; int
0x180130cbd  mov     edx, edi; int
0x180130cbf  call    ?HRESULTFromJET_ERR@@YAJJH@Z; HRESULTFromJET_ERR(long,int)
0x180130cc4  mov     ebx, eax
0x180130cc6  test    eax, eax
0x180130cc8  js      loc_180130EB0
0x180130cce  mov     r8, [rbp+730h+var_7A0]; unsigned __int16 *
0x180130cd2  lea     rax, [rbp+730h+var_710]
0x180130cd6  mov     edx, [rbp+730h+dbid]; dbid
0x180130cd9  mov     r9d, 2; unsigned int
0x180130cdf  mov     rcx, [rbp+730h+sesid]; sesid
0x180130ce3  mov     qword ptr [rsp+830h+cbParameters], rax; unsigned __int16 *
0x180130ce8  call    ?GetColumnIdsByType@@YAJ_KKPEBGKPEAPEAK@Z; GetColumnIdsByType(unsigned __int64,ulong,ushort const *,ulong,ulong * *)
0x180130ced  mov     ebx, eax
0x180130cef  test    eax, eax
0x180130cf1  jns     short loc_180130D00
0x180130cf3  mov     [rsp+830h+var_7CC], 90Bh
0x180130cfb  jmp     loc_180130EA4
0x180130d00  mov     edx, 200h; unsigned int
0x180130d05  lea     rcx, [rbp+730h+var_708]; this
0x180130d09  call    ?ExtendBuffer@CWxString@@QEAAJK@Z; CWxString::ExtendBuffer(ulong)
0x180130d0e  mov     ebx, eax
0x180130d10  test    eax, eax
0x180130d12  jns     short loc_180130D21
0x180130d14  mov     [rsp+830h+var_7CC], 911h
0x180130d1c  jmp     loc_180130EA4
0x180130d21  mov     edx, 200h; unsigned int
0x180130d26  lea     rcx, [rbp+730h+var_6E8]; this
0x180130d2a  call    ?ExtendBuffer@CWxString@@QEAAJK@Z; CWxString::ExtendBuffer(ulong)
0x180130d2f  mov     ebx, eax
0x180130d31  test    eax, eax
0x180130d33  jns     short loc_180130D42
0x180130d35  mov     [rsp+830h+var_7CC], 912h
0x180130d3d  jmp     loc_180130EA4
0x180130d42  mov     edx, 200h; unsigned int
0x180130d47  lea     rcx, [rbp+730h+lpFileName]; this
0x180130d4b  call    ?ExtendBuffer@CWxString@@QEAAJK@Z; CWxString::ExtendBuffer(ulong)
0x180130d50  mov     ebx, eax
0x180130d52  test    eax, eax
0x180130d54  jns     short loc_180130D63
0x180130d56  mov     [rsp+830h+var_7CC], 913h
0x180130d5e  jmp     loc_180130EA4
0x180130d63  lea     rdx, [rsp+830h+var_7C0]
0x180130d68  mov     ecx, 8000h; dwBytes
0x180130d6d  call    ??$WxAlloc@EVWxHeapAllocator@@@@YAJKPEAPEAE@Z; WxAlloc<uchar,WxHeapAllocator>(ulong,uchar * *)
0x180130d72  mov     ebx, eax
0x180130d74  test    eax, eax
0x180130d76  jns     short loc_180130D85
0x180130d78  mov     [rsp+830h+var_7CC], 914h
0x180130d80  jmp     loc_180130EA4
0x180130d85  lea     rcx, [rbp+730h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180130d89  mov     [rsp+830h+var_7D0], 8000h
0x180130d91  call    cs:__imp_GetSystemTimeAsFileTime
0x180130d97  lea     r8, aMinimizedrdoma_2; "MinimizedRDomainHashCookieHashIndex"
0x180130d9e  mov     edx, edi; unsigned int
0x180130da0  mov     rcx, r14; this
0x180130da3  call    ?SetCurrentIndex@CJetContext@@QEAAJKPEBGK@Z; CJetContext::SetCurrentIndex(ulong,ushort const *,ulong)
0x180130da8  mov     ebx, eax
0x180130daa  test    eax, eax
0x180130dac  jns     short loc_180130DBB
0x180130dae  mov     [rsp+830h+var_7CC], 919h
0x180130db6  jmp     loc_180130EA4
0x180130dbb  mov     r8d, 80000000h; cRow
0x180130dc1  mov     rdx, [rbp+730h+tableid]; tableid
0x180130dc5  xor     r9d, r9d; grbit
0x180130dc8  mov     rcx, [rbp+730h+sesid]; sesid
0x180130dcc  call    cs:__imp_JetMove
0x180130dd2  cmp     eax, 0FFFFF9BDh
0x180130dd7  jz      loc_180130EA4
0x180130ddd  mov     edx, edi; int
0x180130ddf  mov     ecx, eax; int
0x180130de1  call    ?HRESULTFromJET_ERR@@YAJJH@Z; HRESULTFromJET_ERR(long,int)
0x180130de6  mov     ebx, eax
0x180130de8  test    eax, eax
0x180130dea  js      loc_180130EA4
0x180130df0  mov     r8, [rbp+730h+var_710]
  ... truncated ...
```
