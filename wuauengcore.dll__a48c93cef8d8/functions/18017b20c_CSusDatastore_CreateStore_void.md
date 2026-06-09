# CSusDatastore::CreateStore(void)

- ea: `0x18017b20c`
- end: `0x18017ba4d`
- name: `?CreateStore@CSusDatastore@@AEAAJXZ`
- size: `2113`
- prototype: `__int64 __fastcall(CSusDatastore *__hidden this)`
- caller_count: `1`
- callee_count: `26`
- tags: `file_ops, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18017a430`

## callees

- `0x180114b08`
- `0x18012b618`
- `0x18012e67c`
- `0x18013193c`
- `0x180131a30`
- `0x180179ce4`
- `0x180179e9c`
- `0x18017a144`
- `0x18017af48`
- `0x18017b20c`
- `0x180182610`
- `0x1801826f4`
- `0x180182c4c`
- `0x1801844a0`
- `0x1801844ec`
- `0x18018457c`
- `0x180184f04`
- `0x1801853f0`
- `0x180185430`
- `0x180189f7c`
- `0x18018f57c`
- `0x180190bc0`
- `0x1801f732c`
- `0x180238960`
- `0x180240cc0`
- `0x180240d40`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18017b278`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18017b278`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18017ba18`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18017ba18`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18017b416`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18017b416`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18017b709`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18017b709`
- `ESENT!JetOpenDatabaseA` at `0x18017b4bd`
- `ESENT!JetOpenDatabaseA` at `0x18017b4bd`
- `ESENT!JetCreateDatabaseA` at `0x18017b591`
- `ESENT!JetCreateDatabaseA` at `0x18017b591`
- `ESENT!JetAttachDatabaseA` at `0x18017b3f2`
- `ESENT!JetAttachDatabaseA` at `0x18017b3f2`
- `ESENT!JetCloseDatabase` at `0x18017b79f`
- `ESENT!JetCloseDatabase` at `0x18017b79f`
- `ESENT!JetDetachDatabaseA` at `0x18017b91f`
- `ESENT!JetDetachDatabaseA` at `0x18017b91f`

## string_xrefs

- `0x18017b334`: `DS: Could not delete log file directory %hs`
- `0x18017b5b0`: `JetCreateDatabase`
- `0x18017b5f3`: `Database created. Attempting to add tables`
- `0x18017b4ea`: `JetOpenDatabase`
- `0x18017b47e`: `DS: 0x%08x: JetAttachDatabase failed. sesid: %Ix.  Assuming store is invalid.`
- `0x18017b760`: `DS: CreateStore cleanup, dsStatus: %d`
- `0x18017b6bc`: `Data store successfully created`
- `0x18017b9ad`: `DS: DSRemoveDb called`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CSusDatastore::CreateStore(CSusDatastore *this)
{
  unsigned int v2; // r13d
  struct CSusEseSession *v3; // r15
  unsigned int v4; // edi
  int v5; // r12d
  char *v6; // rbx
  __int64 v7; // rsi
  int v8; // eax
  int inited; // eax
  int v10; // r9d
  JET_ERR v11; // eax
  bool v12; // cc
  __int64 v13; // rax
  JET_ERR v14; // eax
  JET_ERR v15; // eax
  int v16; // r8d
  int v17; // r9d
  int v18; // edi
  __int64 v19; // rdx
  __int64 v20; // r8
  __int64 RegKeyPath; // rax
  __int64 v22; // rcx
  __int64 v23; // rdx
  __int64 v24; // r8
  const WCHAR *v25; // rax
  __int64 v26; // rcx
  JET_ERR v27; // eax
  unsigned int v28; // eax
  int v29; // eax
  int v30; // eax
  JET_ERR v31; // eax
  unsigned int v32; // eax
  __int64 v33; // rdx
  int grbit; // [rsp+28h] [rbp-49h]
  int v36; // [rsp+30h] [rbp-41h]
  unsigned int v37[2]; // [rsp+38h] [rbp-39h]
  void *v38; // [rsp+40h] [rbp-31h]
  __int64 v39; // [rsp+48h] [rbp-29h]
  int v40; // [rsp+68h] [rbp-9h]
  int v41; // [rsp+6Ch] [rbp-5h]
  JET_DBID pdbid; // [rsp+78h] [rbp+7h] BYREF
  unsigned int v43[4]; // [rsp+80h] [rbp+Fh] BYREF
  struct CSusEseSession *v44; // [rsp+90h] [rbp+1Fh] BYREF

  v2 = 0;
  v3 = 0;
  v44 = 0;
  v41 = *((_DWORD *)this + 212);
  pdbid = -1;
  v4 = 0;
  v5 = 0;
  v40 = 0;
  v6 = (char *)this + 640;
  if ( this != (CSusDatastore *)-640LL )
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 648));
  *(_QWORD *)v43 = -1;
  LODWORD(v7) = 0;
  if ( *((int *)this + 212) >= 2 )
  {
LABEL_14:
    if ( (int)v7 < 0 )
      goto LABEL_45;
    goto LABEL_15;
  }
  memset(&g_rgClientStoreColumnIds, -1, 0x4A4u);
  v8 = ConfigureSharedGlobalJetSysParams(lambda_63d41ac565cd9c1054815aec83348440_::_lambda_invoker_cdecl_);
  if ( v8 )
  {
    LODWORD(v7) = JETErrToHRESULTAndAttemptRecovery(v8);
    v37[0] = v7;
    WUTrace(0, 0, 0x2000, 2, 0, L"0x%08x: Error setting global ESE parameters");
  }
  if ( (int)v7 < 0 )
    goto LABEL_45;
  inited = CSusDatastore::ConfigAndInitInstance(this, (unsigned __int64 *)v43);
  LODWORD(v7) = inited;
  if ( inited == -939523577 || inited == -939523548 )
  {
    LODWORD(v7) = SusDeleteDirectoryA(*((LPCCH *)this + 109), 0, 0, v10, grbit, v36, v37[0], v38, v39);
    if ( (int)v7 < 0 )
    {
      WUTrace(0, 0, 0x2000, 1, v7, L"DS: Could not delete log file directory %hs", *((_QWORD *)this + 109));
      goto LABEL_45;
    }
    LODWORD(v7) = CSusDatastore::ConfigAndInitInstance(this, (unsigned __int64 *)v43);
  }
  if ( (_DWORD)v7 != 1207959552 )
  {
    DSAttemptRecovery(v7);
    WUTrace(0, 0, 0x2000, 1, v7, L"DS: InitializeEse failed");
    goto LABEL_14;
  }
  *((_QWORD *)this + 105) = *(_QWORD *)v43;
LABEL_15:
  v2 = 1;
  *((_DWORD *)this + 212) = 3;
  LODWORD(v7) = CSusDatastore::GetSessionAsClass(this, &v44);
  v3 = v44;
  if ( (int)v7 < 0 )
    goto LABEL_45;
  *((_DWORD *)this + 212) = 2;
  while ( 1 )
  {
    v11 = JetAttachDatabaseA(*((_QWORD *)v3 + 16), *((JET_PCSTR *)this + 108), 0);
    if ( v11 != -1907 )
    {
      if ( v11 == -1811 )
      {
        v5 = 1;
        v40 = 1;
        v4 = 0;
        WUTrace(0, 0, 0x2000, 1, 0, L"DS: JetAttachDatabase failed. Database file was not found.");
        goto LABEL_32;
      }
      if ( v11 != -1202 )
        break;
    }
    Sleep(0x1F4u);
    if ( ++v4 >= 0x3C )
    {
      LODWORD(v7) = -2145091569;
      v4 = 0;
      goto LABEL_45;
    }
  }
  v4 = 0;
  if ( v11 && v11 != 1007 )
  {
    v7 = (unsigned int)JETErrToHRESULTAndAttemptRecovery(v11);
    v12 = (int)HRESULTToErrorType(v7) <= 3;
    v13 = *((_QWORD *)v3 + 16);
    if ( !v12 )
    {
      v37[0] = v7;
      WUTrace(
        0,
        0,
        0x2000,
        1,
        0,
        L"DS: 0x%08x: JetAttachDatabase failed. sesid: %Ix.  Assuming store is invalid.",
        *(_QWORD *)v37,
        *((_QWORD *)v3 + 16));
      LODWORD(v7) = -2145091582;
      goto LABEL_45;
    }
    goto LABEL_29;
  }
  v2 = 2;
  v14 = JetOpenDatabaseA(*((_QWORD *)v3 + 16), *((JET_PCSTR *)this + 108), 0, &pdbid, 0);
  if ( v14 )
  {
    LODWORD(v7) = JETErrToHRESULTAndAttemptRecovery(v14);
    v13 = *((_QWORD *)v3 + 16);
LABEL_29:
    v37[0] = v7;
    WUTrace(0, 0, 0x2000, 1, 0, L"DS: 0x%08x: %hs failed. instanceid: %Ix", *(_QWORD *)v37, "JetOpenDatabase", v13);
    goto LABEL_45;
  }
  v2 = 3;
  *((_DWORD *)v3 + 34) = pdbid;
  pdbid = -1;
LABEL_32:
  if ( v5 )
  {
    *(_QWORD *)v43 = &CSusEseTransaction::`vftable';
    *(_QWORD *)&v43[2] = 0;
    v15 = JetCreateDatabaseA(*((_QWORD *)v3 + 16), *((JET_PCSTR *)this + 108), 0, &pdbid, 0);
    if ( v15 )
    {
      LODWORD(v7) = JETErrToHRESULTAndAttemptRecovery(v15);
      v37[0] = v7;
      WUTrace(
        0,
        0,
        0x2000,
        1,
        0,
        L"DS: 0x%08x: %hs failed. instanceid: %Ix",
        *(_QWORD *)v37,
        "JetCreateDatabase",
        *((_QWORD *)v3 + 16));
LABEL_35:
      CSusEseTransaction::~CSusEseTransaction((CSusEseTransaction *)v43);
      goto LABEL_45;
    }
    WUTrace(0, 0, 0x2000, 5, 0, L"Database created. Attempting to add tables");
    v2 = 3;
    *((_DWORD *)v3 + 34) = pdbid;
    pdbid = -1;
    LODWORD(v7) = CSusEseTransaction::Begin((CSusEseTransaction *)v43, (struct CSusEseSession *)((char *)v3 + 8));
    if ( (int)v7 < 0 )
      goto LABEL_35;
    do
    {
      LODWORD(v7) = DSCreateTable(
                      *((_QWORD *)v3 + 16),
                      *((_DWORD *)v3 + 34),
                      (const struct tagSusTableCreate *)(&g_rgClientStoreTables + 6 * v4),
                      &g_rgClientStoreColumnIds);
      if ( (int)v7 < 0 )
      {
        v4 = 0;
        goto LABEL_43;
      }
      ++v4;
    }
    while ( v4 < 0x16 );
    v18 = *((_DWORD *)this + 212);
    *((_DWORD *)this + 212) = 4;
    LODWORD(v7) = CSusEseSession::InitializeStore(v3, 0, v16, v17);
    *((_DWORD *)this + 212) = v18;
    v4 = 0;
    if ( (int)v7 >= 0 )
    {
      LODWORD(v7) = CSusEseTransaction::Commit((CSusEseTransaction *)v43);
      if ( (int)v7 >= 0 )
      {
        WUTrace(0, 0, 0x2000, 4, 0, L"Data store successfully created");
        LODWORD(v7) = 0;
        RegKeyPath = GetRegKeyPath(0, v19, v20);
        RegDelValue(v22, RegKeyPath, L"ResetDataStoreReason");
        v25 = (const WCHAR *)GetRegKeyPath(9, v23, v24);
        RegDeleteTreeW(HKEY_LOCAL_MACHINE, v25);
        RegSetLastDownloadsPurgeTime();
        CSusEseTransaction::~CSusEseTransaction((CSusEseTransaction *)v43);
        goto LABEL_58;
      }
    }
LABEL_43:
    v37[0] = v7;
    WUTrace(0, 0, 0x2000, 1, 0, L"DS: %#08x: Data store creation failed.", *(_QWORD *)v37);
    CSusEseTransaction::~CSusEseTransaction((CSusEseTransaction *)v43);
    goto LABEL_44;
  }
  v43[0] = 0;
  LODWORD(v44) = 0;
  v29 = (*(__int64 (__fastcall **)(__int64, unsigned int *, struct CSusEseSession **))(*((_QWORD *)v3 + 1) + 160LL))(
          (__int64)v3 + 8,
          v43,
          &v44);
  if ( v29 < 0
    || v43[0] == 14 && (_DWORD)v44 == 3
    || (v29 = CSusEseSession::MigrateStore(v3, v43[0], (unsigned int)v44), LODWORD(v7) = v29, v29 != -2145091578) )
  {
    LODWORD(v7) = v29;
    if ( v29 >= 0 )
    {
      do
      {
        v30 = DSValidateTableAndSetColumnids(
                *((_QWORD *)v3 + 16),
                *((_DWORD *)v3 + 34),
                (const struct tagSusTableCreate *)(&g_rgClientStoreTables + 6 * v4),
                &g_rgClientStoreColumnIds);
        LODWORD(v7) = v30;
        if ( v30 < 0 )
          break;
        ++v4;
      }
      while ( v4 < 0x16 );
      v4 = 0;
      v6 = (char *)this + 640;
      if ( v30 >= 0 )
      {
        LODWORD(v7) = CServiceCache::PopulateFromStore((CSusDatastore *)((char *)this + 736), this, v3);
        if ( (int)v7 >= 0 )
        {
LABEL_58:
          v2 = 0;
          v41 = 5;
        }
      }
LABEL_44:
      v5 = v40;
    }
  }
  else
  {
    LODWORD(v39) = 14;
    LODWORD(v38) = 3;
    v37[0] = 12;
    WUTrace(
      0,
      0,
      0x2000,
      1,
      0,
      L"Datastore version is incorrect. Expected %lu.%lu-%lu.%lu, but got %lu.%lu.",
      *(_QWORD *)v37,
      v38,
      v39,
      3,
      v43[0],
      (_DWORD)v44);
  }
LABEL_45:
  v37[0] = v2;
  WUTrace(0, 0, 0x2000, 4, 0, L"DS: CreateStore cleanup, dsStatus: %d", *(_QWORD *)v37);
  if ( v2 < 3 )
  {
    if ( v2 < 2 )
      goto LABEL_66;
  }
  else
  {
    v27 = JetCloseDatabase(*((_QWORD *)v3 + 16), *((_DWORD *)v3 + 34), 0);
    if ( v27 >= 0 )
      v28 = v27 | 0x48000000;
    else
      v28 = -v27 | 0xC8000000;
    WUTrace(0, 0, 0x2000, 4, v28, L"DS: JetCloseDatabase called");
    *((_DWORD *)v3 + 34) = -1;
  }
  v31 = JetDetachDatabaseA(*((_QWORD *)v3 + 16), *((JET_PCSTR *)this + 108));
  if ( v31 >= 0 )
    v32 = v31 | 0x48000000;
  else
    v32 = -v31 | 0xC8000000;
  WUTrace(0, 0, 0x2000, 4, v32, L"DS: JetDetachDatabase called");
LABEL_66:
  if ( v2 )
  {
    v4 = CSusDatastore::TerminateEse(this);
    WUTrace(0, 0, 0x2000, 4, v4, L"DS: TerminateEse called");
  }
  if ( v5 && v2 >= 3 )
  {
    v4 = DSRemoveDb(*((const char **)this + 108), *((const char **)this + 109));
    WUTrace(0, 0, 0x2000, 4, v4, L"DS: DSRemoveDb called");
  }
  if ( (int)v7 < 0 || (v4 & 0x80000000) != 0 )
  {
    v33 = *((_QWORD *)this + 105);
    if ( v33 != -1 )
      CSusDatastore::JetTerm2WithRetry(v26, v33, 2);
  }
  if ( v3 )
    (*(void (__fastcall **)(__int64))(*((_QWORD *)v3 + 1) + 16LL))((__int64)v3 + 8);
  *((_DWORD *)this + 212) = v41;
  if ( v6 )
    LeaveCriticalSection((LPCRITICAL_SECTION)(v6 + 8));
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18017b20c  mov     rax, rsp
0x18017b20f  mov     [rax+10h], rbx
0x18017b213  mov     [rax+18h], rsi
0x18017b217  mov     [rax+20h], rdi
0x18017b21b  push    rbp
0x18017b21c  push    r12
0x18017b21e  push    r13
0x18017b220  push    r14
0x18017b222  push    r15
0x18017b224  lea     rbp, [rax-5Fh]
0x18017b228  sub     rsp, 0A0h
0x18017b22f  mov     rax, cs:__security_cookie
0x18017b236  xor     rax, rsp
0x18017b239  mov     [rbp+57h+var_30], rax
0x18017b23d  mov     r14, rcx
0x18017b240  xor     eax, eax
0x18017b242  mov     r13d, eax
0x18017b245  mov     r15d, eax
0x18017b248  mov     [rbp+57h+var_38], rax
0x18017b24c  mov     edi, [rcx+350h]
0x18017b252  mov     [rbp+57h+var_5C], edi
0x18017b255  mov     [rbp+57h+pdbid], 0FFFFFFFFh
0x18017b25c  xor     edi, edi
0x18017b25e  mov     r12d, edi
0x18017b261  mov     [rbp+57h+var_60], edi
0x18017b264  lea     rbx, [rcx+280h]
0x18017b26b  mov     [rbp+57h+var_58], rbx
0x18017b26f  test    rbx, rbx
0x18017b272  jz      short loc_18017B27F
0x18017b274  lea     rcx, [rbx+8]; lpCriticalSection
0x18017b278  call    cs:__imp_EnterCriticalSection
0x18017b27e  nop
0x18017b27f  mov     qword ptr [rbp+57h+var_48], 0FFFFFFFFFFFFFFFFh
0x18017b287  mov     esi, edi
0x18017b289  cmp     dword ptr [r14+350h], 2
0x18017b291  jge     loc_18017B3A0
0x18017b297  mov     r8d, 4A4h; Size
0x18017b29d  or      edx, 0FFFFFFFFh; Val
0x18017b2a0  lea     rcx, ?g_rgClientStoreColumnIds@@3PAKA; void *
0x18017b2a7  call    memset
0x18017b2ac  lea     rcx, _lambda_63d41ac565cd9c1054815aec83348440____lambda_invoker_cdecl_; void (*)(const enum DsEseConfigLogLevel *, const wchar_t *)
0x18017b2b3  call    ?ConfigureSharedGlobalJetSysParams@@YAJQ6AXAEBW4DsEseConfigLogLevel@@PEB_W@Z@Z; ConfigureSharedGlobalJetSysParams(void (*const)(DsEseConfigLogLevel const &,wchar_t const *))
0x18017b2b8  test    eax, eax
0x18017b2ba  jz      short loc_18017B2ED
0x18017b2bc  mov     ecx, eax; int
0x18017b2be  call    ?JETErrToHRESULTAndAttemptRecovery@@YAJJ@Z; JETErrToHRESULTAndAttemptRecovery(long)
0x18017b2c3  mov     esi, eax
0x18017b2c5  mov     [rsp+0C0h+var_90], eax; unsigned int
0x18017b2c9  lea     rax, a0x08xErrorSett; "0x%08x: Error setting global ESE parame"...
0x18017b2d0  mov     qword ptr [rsp+0C0h+var_98], rax; int
0x18017b2d5  mov     qword ptr [rsp+0C0h+grbit], rdi; int
0x18017b2da  xor     edx, edx
0x18017b2dc  xor     ecx, ecx
0x18017b2de  lea     r9d, [rdx+2]
0x18017b2e2  mov     r8d, 2000h
0x18017b2e8  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x18017b2ed  test    esi, esi
0x18017b2ef  js      loc_18017B75B
0x18017b2f5  lea     rdx, [rbp+57h+var_48]; unsigned __int64 *
0x18017b2f9  mov     rcx, r14; this
0x18017b2fc  call    ?ConfigAndInitInstance@CSusDatastore@@AEAAJPEA_K@Z; CSusDatastore::ConfigAndInitInstance(unsigned __int64 *)
0x18017b301  mov     esi, eax
0x18017b303  cmp     eax, 0C8000207h
0x18017b308  jz      short loc_18017B311
0x18017b30a  cmp     eax, 0C8000224h
0x18017b30f  jnz     short loc_18017B36A
0x18017b311  xor     r8d, r8d; int
0x18017b314  xor     edx, edx; int
0x18017b316  mov     rcx, [r14+368h]; lpMultiByteStr
0x18017b31d  call    ?SusDeleteDirectoryA@@YAJPEBDHHHHHKPEAXH@Z; SusDeleteDirectoryA(char const *,int,int,int,int,int,ulong,void *,int)
0x18017b322  mov     esi, eax
0x18017b324  test    eax, eax
0x18017b326  jns     short loc_18017B35C
0x18017b328  mov     rax, [r14+368h]
0x18017b32f  mov     qword ptr [rsp+0C0h+var_90], rax
0x18017b334  lea     rax, aDsCouldNotDele; "DS: Could not delete log file directory"...
0x18017b33b  mov     qword ptr [rsp+0C0h+var_98], rax
0x18017b340  mov     [rsp+0C0h+grbit], esi
0x18017b344  xor     edx, edx
0x18017b346  xor     ecx, ecx
0x18017b348  lea     r9d, [rdx+1]
0x18017b34c  mov     r8d, 2000h
0x18017b352  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x18017b357  jmp     loc_18017B75B
0x18017b35c  lea     rdx, [rbp+57h+var_48]; unsigned __int64 *
0x18017b360  mov     rcx, r14; this
0x18017b363  call    ?ConfigAndInitInstance@CSusDatastore@@AEAAJPEA_K@Z; CSusDatastore::ConfigAndInitInstance(unsigned __int64 *)
0x18017b368  mov     esi, eax
0x18017b36a  cmp     esi, 48000000h
0x18017b370  jz      loc_18017B42F
0x18017b376  mov     ecx, esi; int
0x18017b378  call    ?DSAttemptRecovery@@YAXJ@Z; DSAttemptRecovery(long)
0x18017b37d  lea     rax, aDsInitializees; "DS: InitializeEse failed"
0x18017b384  mov     qword ptr [rsp+0C0h+var_98], rax
0x18017b389  mov     [rsp+0C0h+grbit], esi
0x18017b38d  xor     edx, edx
0x18017b38f  xor     ecx, ecx
0x18017b391  lea     r9d, [rdx+1]
0x18017b395  mov     r8d, 2000h
0x18017b39b  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x18017b3a0  test    esi, esi
0x18017b3a2  js      loc_18017B75B
0x18017b3a8  mov     r13d, 1
0x18017b3ae  mov     dword ptr [r14+350h], 3
0x18017b3b9  lea     rdx, [rbp+57h+var_38]; struct CSusEseSession **
0x18017b3bd  mov     rcx, r14; this
0x18017b3c0  call    ?GetSessionAsClass@CSusDatastore@@QEAAJPEAPEAVCSusEseSession@@@Z; CSusDatastore::GetSessionAsClass(CSusEseSession * *)
0x18017b3c5  mov     esi, eax
0x18017b3c7  mov     r15, [rbp+57h+var_38]
0x18017b3cb  test    eax, eax
0x18017b3cd  js      loc_18017B75B
0x18017b3d3  mov     dword ptr [r14+350h], 2
0x18017b3de  mov     esi, r13d
0x18017b3e1  xor     r8d, r8d; grbit
0x18017b3e4  mov     rdx, [r14+360h]; szFilename
0x18017b3eb  mov     rcx, [r15+80h]; sesid
0x18017b3f2  call    cs:__imp_JetAttachDatabaseA
0x18017b3f8  cmp     eax, 0FFFFF88Dh
0x18017b3fd  jz      short loc_18017B411
0x18017b3ff  cmp     eax, 0FFFFF8EDh
0x18017b404  jz      loc_18017B52E
0x18017b40a  cmp     eax, 0FFFFFB4Eh
0x18017b40f  jnz     short loc_18017B43F
0x18017b411  mov     ecx, 1F4h; dwMilliseconds
0x18017b416  call    cs:__imp_Sleep
0x18017b41c  add     edi, esi
0x18017b41e  cmp     edi, 3Ch ; '<'
0x18017b421  jb      short loc_18017B3E1
0x18017b423  mov     esi, 8024800Fh
0x18017b428  xor     edi, edi
0x18017b42a  jmp     loc_18017B75B
0x18017b42f  mov     rax, qword ptr [rbp+57h+var_48]
0x18017b433  mov     [r14+348h], rax
0x18017b43a  jmp     loc_18017B3A8
0x18017b43f  xor     edi, edi
0x18017b441  test    eax, eax
0x18017b443  jz      short loc_18017B49E
0x18017b445  cmp     eax, 3EFh
0x18017b44a  jz      short loc_18017B49E
0x18017b44c  mov     ecx, eax; int
0x18017b44e  call    ?JETErrToHRESULTAndAttemptRecovery@@YAJJ@Z; JETErrToHRESULTAndAttemptRecovery(long)
0x18017b453  mov     esi, eax
0x18017b455  mov     ecx, eax
0x18017b457  call    ?HRESULTToErrorType@@YA?AW4tagDSErrorType@@J@Z; HRESULTToErrorType(long)
0x18017b45c  xor     edx, edx
0x18017b45e  xor     ecx, ecx
0x18017b460  mov     r9d, r13d
0x18017b463  mov     r8d, 2000h
0x18017b469  cmp     eax, 3
0x18017b46c  mov     rax, [r15+80h]
0x18017b473  jle     short loc_18017B4E5
0x18017b475  mov     [rsp+0C0h+var_88], rax
0x18017b47a  mov     [rsp+0C0h+var_90], esi
0x18017b47e  lea     rax, aDs0x08xJetatta; "DS: 0x%08x: JetAttachDatabase failed. s"...
0x18017b485  mov     qword ptr [rsp+0C0h+var_98], rax
0x18017b48a  mov     qword ptr [rsp+0C0h+grbit], rdi
0x18017b48f  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x18017b494  mov     esi, 80248002h
0x18017b499  jmp     loc_18017B75B
0x18017b49e  mov     r13d, 2
0x18017b4a4  mov     [rsp+0C0h+grbit], edi; grbit
0x18017b4a8  lea     r9, [rbp+57h+pdbid]; pdbid
0x18017b4ac  xor     r8d, r8d; szConnect
0x18017b4af  mov     rdx, [r14+360h]; szFilename
0x18017b4b6  mov     rcx, [r15+80h]; sesid
0x18017b4bd  call    cs:__imp_JetOpenDatabaseA
0x18017b4c3  test    eax, eax
0x18017b4c5  jz      short loc_18017B515
0x18017b4c7  mov     ecx, eax; int
0x18017b4c9  call    ?JETErrToHRESULTAndAttemptRecovery@@YAJJ@Z; JETErrToHRESULTAndAttemptRecovery(long)
0x18017b4ce  mov     esi, eax
0x18017b4d0  mov     rax, [r15+80h]
0x18017b4d7  xor     edx, edx
0x18017b4d9  xor     ecx, ecx
0x18017b4db  lea     r9d, [r13-1]
0x18017b4df  mov     r8d, 2000h
0x18017b4e5  mov     [rsp+0C0h+var_80], rax
0x18017b4ea  lea     rax, aJetopendatabas_0; "JetOpenDatabase"
0x18017b4f1  mov     [rsp+0C0h+var_88], rax
0x18017b4f6  mov     [rsp+0C0h+var_90], esi
0x18017b4fa  lea     rax, aDs0x08xHsFaile; "DS: 0x%08x: %hs failed. instanceid: %Ix"
0x18017b501  mov     qword ptr [rsp+0C0h+var_98], rax
0x18017b506  mov     qword ptr [rsp+0C0h+grbit], rdi
0x18017b50b  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x18017b510  jmp     loc_18017B75B
0x18017b515  mov     r13d, 3
0x18017b51b  mov     eax, [rbp+57h+pdbid]
0x18017b51e  mov     [r15+88h], eax
0x18017b525  mov     [rbp+57h+pdbid], 0FFFFFFFFh
0x18017b52c  jmp     short loc_18017B559
0x18017b52e  mov     r12d, esi
0x18017b531  mov     [rbp+57h+var_60], esi
0x18017b534  lea     rax, aDsJetattachdat; "DS: JetAttachDatabase failed. Database "...
0x18017b53b  mov     qword ptr [rsp+0C0h+var_98], rax
0x18017b540  xor     edi, edi
0x18017b542  mov     qword ptr [rsp+0C0h+grbit], rdi
0x18017b547  mov     r9d, esi
0x18017b54a  xor     edx, edx
0x18017b54c  xor     ecx, ecx
0x18017b54e  mov     r8d, 2000h
0x18017b554  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x18017b559  test    r12d, r12d
0x18017b55c  jz      loc_18017B7B9
0x18017b562  xorps   xmm0, xmm0
0x18017b565  movups  xmmword ptr [rbp+57h+var_48], xmm0
0x18017b569  lea     rax, ??_7CSusEseTransaction@@6B@; const CSusEseTransaction::`vftable'
0x18017b570  mov     qword ptr [rbp+57h+var_48], rax
0x18017b574  mov     qword ptr [rbp+57h+var_48+8], rdi
0x18017b578  mov     [rsp+0C0h+grbit], edi; grbit
0x18017b57c  lea     r9, [rbp+57h+pdbid]; pdbid
0x18017b580  xor     r8d, r8d; szConnect
0x18017b583  mov     rdx, [r14+360h]; szFilename
0x18017b58a  mov     rcx, [r15+80h]; sesid
0x18017b591  call    cs:__imp_JetCreateDatabaseA
0x18017b597  test    eax, eax
0x18017b599  jz      short loc_18017B5F3
0x18017b59b  mov     ecx, eax; int
0x18017b59d  call    ?JETErrToHRESULTAndAttemptRecovery@@YAJJ@Z; JETErrToHRESULTAndAttemptRecovery(long)
0x18017b5a2  mov     esi, eax
0x18017b5a4  mov     rax, [r15+80h]
0x18017b5ab  mov     [rsp+0C0h+var_80], rax
0x18017b5b0  lea     rax, aJetcreatedatab_0; "JetCreateDatabase"
0x18017b5b7  mov     [rsp+0C0h+var_88], rax
0x18017b5bc  mov     [rsp+0C0h+var_90], esi
0x18017b5c0  lea     rax, aDs0x08xHsFaile; "DS: 0x%08x: %hs failed. instanceid: %Ix"
0x18017b5c7  mov     qword ptr [rsp+0C0h+var_98], rax
0x18017b5cc  mov     qword ptr [rsp+0C0h+grbit], rdi
0x18017b5d1  xor     edx, edx
0x18017b5d3  xor     ecx, ecx
0x18017b5d5  lea     r9d, [rdx+1]
0x18017b5d9  mov     r8d, 2000h
0x18017b5df  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x18017b5e4  nop
0x18017b5e5  lea     rcx, [rbp+57h+var_48]; this
0x18017b5e9  call    ??1CSusEseTransaction@@UEAA@XZ; CSusEseTransaction::~CSusEseTransaction(void)
0x18017b5ee  jmp     loc_18017B75B
0x18017b5f3  lea     rax, aDatabaseCreate; "Database created. Attempting to add tab"...
0x18017b5fa  mov     qword ptr [rsp+0C0h+var_98], rax
0x18017b5ff  mov     qword ptr [rsp+0C0h+grbit], rdi
0x18017b604  xor     edx, edx
0x18017b606  xor     ecx, ecx
0x18017b608  lea     r9d, [rdx+5]
0x18017b60c  mov     r8d, 2000h
0x18017b612  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x18017b617  mov     r13d, 3
0x18017b61d  mov     eax, [rbp+57h+pdbid]
0x18017b620  mov     [r15+88h], eax
0x18017b627  mov     [rbp+57h+pdbid], 0FFFFFFFFh
0x18017b62e  lea     rdx, [r15+8]; struct ISusEseSession *
0x18017b632  lea     rcx, [rbp+57h+var_48]; this
0x18017b636  call    ?Begin@CSusEseTransaction@@QEAAJPEAUISusEseSession@@@Z; CSusEseTransaction::Begin(ISusEseSession *)
0x18017b63b  mov     esi, eax
0x18017b63d  test    eax, eax
0x18017b63f  js      short loc_18017B5E5
0x18017b641  lea     r12, ?g_rgClientStoreTables@@3PAUtagSusTableCreate@@A; tagSusTableCreate near * g_rgClientStoreTables
0x18017b648  mov     eax, edi
0x18017b64a  lea     r8, [rax+rax*2]
0x18017b64e  shl     r8, 4
0x18017b652  add     r8, r12; struct tagSusTableCreate *
0x18017b655  lea     r9, ?g_rgClientStoreColumnIds@@3PAKA; unsigned int *
0x18017b65c  mov     edx, [r15+88h]; dbid
0x18017b663  mov     rcx, [r15+80h]; unsigned __int64
0x18017b66a  call    ?DSCreateTable@@YAJ_KKPEBUtagSusTableCreate@@PEAK@Z; DSCreateTable(unsigned __int64,ulong,tagSusTableCreate const *,ulong *)
0x18017b66f  mov     esi, eax
0x18017b671  test    eax, eax
0x18017b673  js      loc_18017B723
0x18017b679  inc     edi
0x18017b67b  cmp     edi, 16h
0x18017b67e  jb      short loc_18017B648
0x18017b680  mov     edi, [r14+350h]
0x18017b687  mov     r12d, 4
0x18017b68d  mov     [r14+350h], r12d
0x18017b694  xor     edx, edx; int
0x18017b696  mov     rcx, r15; this
0x18017b699  call    ?InitializeStore@CSusEseSession@@QEAAJHHH@Z; CSusEseSession::InitializeStore(int,int,int)
0x18017b69e  mov     esi, eax
0x18017b6a0  mov     [r14+350h], edi
0x18017b6a7  xor     edi, edi
0x18017b6a9  test    eax, eax
0x18017b6ab  js      short loc_18017B725
0x18017b6ad  lea     rcx, [rbp+57h+var_48]; this
0x18017b6b1  call    ?Commit@CSusEseTransaction@@QEAAJXZ; CSusEseTransaction::Commit(void)
0x18017b6b6  mov     esi, eax
0x18017b6b8  test    eax, eax
0x18017b6ba  js      short loc_18017B725
0x18017b6bc  lea     rax, aDataStoreSucce; "Data store successfully created"
0x18017b6c3  mov     qword ptr [rsp+0C0h+var_98], rax
0x18017b6c8  mov     qword ptr [rsp+0C0h+grbit], rdi
0x18017b6cd  mov     r9d, r12d
0x18017b6d0  xor     edx, edx
0x18017b6d2  xor     ecx, ecx
0x18017b6d4  mov     r8d, 2000h
0x18017b6da  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x18017b6df  mov     esi, edi
0x18017b6e1  xor     ecx, ecx
0x18017b6e3  call    ?GetRegKeyPath@@YAPEB_WW4WURegKey@RegUtil@@@Z; GetRegKeyPath(RegUtil::WURegKey)
0x18017b6e8  mov     rdx, rax
0x18017b6eb  lea     r8, aResetdatastore; "ResetDataStoreReason"
0x18017b6f2  call    ?RegDelValue@@YAJPEAUHKEY__@@PEB_W1W4RegistryHiveType@@@Z; RegDelValue(HKEY__ *,wchar_t const *,wchar_t const *,RegistryHiveType)
0x18017b6f7  lea     ecx, [rdi+9]
  ... truncated ...
```
