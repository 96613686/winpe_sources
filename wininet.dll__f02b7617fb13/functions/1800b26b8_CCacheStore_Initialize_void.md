# CCacheStore::Initialize(void)

- ea: `0x1800b26b8`
- end: `0x1800b3329`
- name: `?Initialize@CCacheStore@@AEAAJXZ`
- size: `3185`
- prototype: `__int64 __fastcall(CCacheStore *__hidden this)`
- caller_count: `1`
- callee_count: `52`
- tags: `file_ops, authz_impersonation, registry_config, service_task`

## callers

- `0x180043f58`

## callees

- `0x1800201a0`
- `0x180020f74`
- `0x18002101c`
- `0x1800249b8`
- `0x180025514`
- `0x180025910`
- `0x18002a398`
- `0x18002a498`
- `0x18003e350`
- `0x18003fc40`
- `0x180044588`
- `0x18004a830`
- `0x18004aa94`
- `0x1800701d0`
- `0x18007ec9c`
- `0x1800afa98`
- `0x1800b0eec`
- `0x1800b0f30`
- `0x1800b114c`
- `0x1800b11e8`
- `0x1800b12e0`
- `0x1800b13f4`
- `0x1800b1490`
- `0x1800b1600`
- `0x1800b1818`
- `0x1800b18d4`
- `0x1800b19f4`
- `0x1800b26b8`
- `0x1800b382c`
- `0x1800b3860`
- `0x1800b38a4`
- `0x18011da0c`
- `0x180120644`
- `0x1801282dc`
- `0x180128948`
- `0x18012aa70`
- `0x18012ab30`
- `0x1801387a0`
- `0x1801387e4`
- `0x18013d440`
- `0x18013d538`
- `0x180141344`
- `0x1801415a8`
- `0x1801416d0`
- `0x180141878`
- `0x180141b1c`
- `0x18014a7a0`
- `0x18014b3b4`
- `0x1801a8340`
- `0x1801a9d54`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800b2b45`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800b2b96`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800b2bed`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800b2c44`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800b2b45`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800b2b96`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800b2bed`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800b2c44`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800b2a0b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800b2b6c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800b2bc2`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800b2c19`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800b2c70`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800b2dc9`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800b2a0b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800b2b6c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800b2bc2`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800b2c19`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800b2c70`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800b2dc9`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x1800b2ce6`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x1800b2ce6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800b28e3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800b28f3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800b28e3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800b28f3`
- `ESENT!JetGetSystemParameterW` at `0x1800b29e1`
- `ESENT!JetGetSystemParameterW` at `0x1800b29e1`
- `ESENT!JetTerm2` at `0x1800b32b0`
- `ESENT!JetTerm2` at `0x1800b32b0`
- `ESENT!JetEndSession` at `0x1800b3298`
- `ESENT!JetEndSession` at `0x1800b3298`

## pseudocode

```c
__int64 __fastcall CCacheStore::Initialize(CCacheStore *this)
{
  CWxWorkItemPool *v1; // r13
  CWxWorker *v2; // r12
  char *v3; // rdi
  char *v4; // rsi
  char *v5; // r14
  char *v6; // r15
  CClientProcess *v7; // rbx
  JET_ERR SystemParameterW; // eax
  CContainerProps *v10; // rax
  int v11; // eax
  char *v12; // rax
  signed int LastError; // eax
  char *v14; // rax
  char *v15; // rax
  char *v16; // rax
  char *v17; // rax
  __int64 v18; // rdx
  __int64 v19; // rcx
  struct _TP_CALLBACK_ENVIRON_V3 *v20; // r8
  CWxWorkItemPool *v21; // rax
  CWxWorkItemPool *v22; // rax
  struct CWxWorkItemPool *v23; // rax
  struct _TP_CALLBACK_ENVIRON_V3 *v24; // r8
  HANDLE v25; // rax
  unsigned __int64 v26; // rax
  CContainerPropsMap *v27; // rcx
  struct _TP_WORK *v28; // rdx
  HANDLE v29; // rax
  CWxWorker *v30; // rcx
  int GlobalCountersName; // [rsp+30h] [rbp-D0h]
  CContainerProps *v33; // [rsp+48h] [rbp-B8h]
  CContainerProps *v34; // [rsp+48h] [rbp-B8h]
  CWxWorkItemPool *v35; // [rsp+50h] [rbp-B0h] BYREF
  CWxWorkItemPool *v36; // [rsp+58h] [rbp-A8h]
  CInFlightPool *v37; // [rsp+60h] [rbp-A0h]
  CClientProcessMap *v38; // [rsp+68h] [rbp-98h] BYREF
  CBloomMap *v39; // [rsp+70h] [rbp-90h] BYREF
  CContainerPropsMap *v40; // [rsp+78h] [rbp-88h] BYREF
  CBloomMapPartition *v41; // [rsp+80h] [rbp-80h] BYREF
  HANDLE hObject; // [rsp+88h] [rbp-78h]
  struct _TP_WORK *v43; // [rsp+90h] [rbp-70h]
  struct _TP_TIMER *v44; // [rsp+98h] [rbp-68h] BYREF
  struct _TP_WORK *v45; // [rsp+A0h] [rbp-60h] BYREF
  JET_INSTANCE instance; // [rsp+A8h] [rbp-58h] BYREF
  JET_SESID sesid; // [rsp+B0h] [rbp-50h] BYREF
  CWxWorkItemPool *v48; // [rsp+B8h] [rbp-48h] BYREF
  CWxWorkItemPool *v49; // [rsp+C0h] [rbp-40h] BYREF
  struct CAppCacheContainerMap *v50; // [rsp+C8h] [rbp-38h] BYREF
  HANDLE v51; // [rsp+D0h] [rbp-30h] BYREF
  CWxWorker *v52; // [rsp+D8h] [rbp-28h] BYREF
  JET_PCWSTR szFilename[2]; // [rsp+E0h] [rbp-20h] BYREF
  LPCWSTR lpName[2]; // [rsp+F0h] [rbp-10h] BYREF
  LPCWSTR lpFileName[2]; // [rsp+100h] [rbp+0h] BYREF
  unsigned __int16 *v56[2]; // [rsp+110h] [rbp+10h] BYREF

  v56[0] = (unsigned __int16 *)&Data;
  szFilename[0] = &Data;
  instance = -1;
  v1 = 0;
  sesid = -1;
  v2 = 0;
  v51 = (HANDLE)-1LL;
  v3 = 0;
  v56[1] = 0;
  v4 = 0;
  szFilename[1] = 0;
  v5 = 0;
  lpFileName[0] = &Data;
  v6 = 0;
  lpFileName[1] = 0;
  v7 = 0;
  lpName[0] = &Data;
  lpName[1] = 0;
  hObject = 0;
  v41 = 0;
  v33 = 0;
  v40 = 0;
  v50 = 0;
  v39 = 0;
  v35 = 0;
  v49 = 0;
  v48 = 0;
  v37 = 0;
  v36 = 0;
  v52 = 0;
  v43 = 0;
  v45 = 0;
  v38 = 0;
  v44 = 0;
  if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
    WPP_SF_q(1036, 18, WPP_d2eb1eb319bd39627e3f05ba48018899_Traceguids, this);
  GlobalCountersName = DetermineCacheDatabasePaths((struct CWxString *)szFilename, v56, lpFileName);
  if ( GlobalCountersName < 0 )
    goto LABEL_4;
  GlobalCountersName = LockDatabase(lpFileName[0], &v51);
  if ( GlobalCountersName < 0 )
    goto LABEL_4;
  GlobalCountersName = ConfigureGlobalJetParameters();
  if ( GlobalCountersName < 0 )
    goto LABEL_4;
  GlobalCountersName = OpenCacheDatabase(v56[0], szFilename[0], &instance, &sesid);
  if ( GlobalCountersName < 0 )
    goto LABEL_4;
  SystemParameterW = JetGetSystemParameterW(instance, 0, 0x18u, (JET_API_PTR *)this + 79, 0, 0);
  GlobalCountersName = HRESULTFromJET_ERR(SystemParameterW, 0);
  if ( GlobalCountersName < 0 )
    goto LABEL_4;
  v10 = (CContainerProps *)HeapAlloc(g_hWxProcessHeap, 0, 0xF0u);
  v34 = v10;
  if ( !v10 || (memset_0(v10, 0, 0xF0u), (v33 = CContainerProps::CContainerProps(v34)) == 0) )
  {
    v33 = 0;
    goto LABEL_66;
  }
  GlobalCountersName = CContainerPropsMap::CreateInstance(&v40);
  if ( GlobalCountersName >= 0 )
  {
    GlobalCountersName = CAppCacheContainerMap::CreateInstance(this, &v50);
    if ( GlobalCountersName >= 0 )
    {
      v11 = CAppCacheDeletionManager::CreateInstance(&v35);
      v1 = v35;
      GlobalCountersName = v11;
      if ( v11 >= 0 )
      {
        *((_QWORD *)v35 + 11) = this;
        GlobalCountersName = CBloomMapPartition::CreateInstance(&v41);
        if ( GlobalCountersName >= 0 )
        {
          GlobalCountersName = CBloomMap::CreateInstance(&v39);
          if ( GlobalCountersName >= 0 )
          {
            v12 = (char *)operator new(0x40u);
            v3 = v12;
            if ( !v12 )
              goto LABEL_66;
            memset_0(v12, 0, 0x40u);
            *(_DWORD *)v3 = 1;
            InitializeCriticalSection((LPCRITICAL_SECTION)(v3 + 24));
            GlobalCountersName = CDependencyStore::Initialize((CDependencyStore *)v3);
            if ( GlobalCountersName >= 0 )
            {
              v14 = (char *)HeapAlloc(g_hWxProcessHeap, 0, 0x40u);
              v4 = v14;
              if ( v14 )
              {
                memset_0(v14, 0, 0x40u);
                *(_DWORD *)v4 = 1;
                InitializeCriticalSection((LPCRITICAL_SECTION)(v4 + 24));
                GlobalCountersName = CHstsStore::Initialize((CHstsStore *)v4, this);
                if ( GlobalCountersName < 0 )
                  goto LABEL_4;
                v15 = (char *)HeapAlloc(g_hWxProcessHeap, 0, 0x40u);
                v5 = v15;
                if ( v15 )
                {
                  memset_0(v15, 0, 0x40u);
                  *(_DWORD *)v5 = 1;
                  InitializeCriticalSection((LPCRITICAL_SECTION)(v5 + 24));
                  GlobalCountersName = CCookieStore::Initialize((CCookieStore *)v5, this);
                  if ( GlobalCountersName < 0 )
                    goto LABEL_4;
                  v16 = (char *)HeapAlloc(g_hWxProcessHeap, 0, 0x40u);
                  v6 = v16;
                  if ( v16 )
                  {
                    memset_0(v16, 0, 0x40u);
                    *(_DWORD *)v6 = 1;
                    InitializeCriticalSection((LPCRITICAL_SECTION)(v6 + 24));
                    GlobalCountersName = CBlobStore::Initialize((CBlobStore *)v6, this);
                    if ( GlobalCountersName < 0 )
                      goto LABEL_4;
                    v17 = (char *)HeapAlloc(g_hWxProcessHeap, 0, 0x30u);
                    v7 = (CClientProcess *)v17;
                    if ( v17 )
                    {
                      *(_QWORD *)v17 = 1;
                      *((_DWORD *)v17 + 11) = 0;
                      *(_OWORD *)(v17 + 8) = 0;
                      *(_OWORD *)(v17 + 24) = 0;
                      *((_DWORD *)v17 + 10) = 0;
                      GlobalCountersName = CClientProcessMap::CreateInstance(&v38);
                      if ( GlobalCountersName >= 0 )
                      {
                        GlobalCountersName = GetGlobalCountersName((struct CWxString *)lpName);
                        if ( GlobalCountersName >= 0 )
                        {
                          hObject = CreateFileMappingW((HANDLE)0xFFFFFFFFFFFFFFFFLL, 0, 4u, 0, 0x80u, lpName[0]);
                          if ( !hObject )
                          {
                            LastError = WxGetLastError(v19, v18);
                            if ( LastError > 0 )
                              LastError = (unsigned __int16)LastError | 0x80070000;
                            if ( LastError >= 0 )
                              LastError = -2147418113;
                            goto LABEL_67;
                          }
                          GlobalCountersName = WxCreateThreadpoolTimer(
                                                 FailFastThreadpoolTimerCallback<&private: static void CCacheStore::ActivityTimerCallback(_TP_CALLBACK_INSTANCE *,void *,_TP_TIMER *)>,
                                                 this,
                                                 v20,
                                                 &v44);
                          if ( GlobalCountersName >= 0 )
                          {
                            GlobalCountersName = CCacheStore::LoadSettings(this);
                            if ( GlobalCountersName >= 0 )
                            {
                              GlobalCountersName = CJetContextList::CreateInstance(this, L"Containers", 1u, &v49);
                              if ( GlobalCountersName >= 0 )
                              {
                                GlobalCountersName = CJetContextList::CreateInstance(this, L"PartitionsEx", 9u, &v48);
                                if ( GlobalCountersName >= 0 )
                                {
                                  v21 = (CWxWorkItemPool *)operator new(0x50u);
                                  v35 = v21;
                                  if ( v21 && (memset_0(v21, 0, 0x50u), (v37 = CInFlightPool::CInFlightPool(v35)) != 0) )
                                  {
                                    v22 = (CWxWorkItemPool *)HeapAlloc(g_hWxProcessHeap, 0, 0x50u);
                                    v35 = v22;
                                    if ( v22
                                      && (memset_0(v22, 0, 0x50u),
                                          v23 = CWxWorkItemPool::CWxWorkItemPool(v35),
                                          (v36 = v23) != 0) )
                                    {
                                      GlobalCountersName = CWxWorker::CreateInstance(this, v23, &v52);
                                      if ( GlobalCountersName >= 0 )
                                      {
                                        v2 = v52;
                                        GlobalCountersName = CWxWorker::Queue(
                                                               v52,
                                                               (int (*)(struct CWxWorker *, struct CWxWorkContext *, unsigned __int64, void *))CCacheStore::DeleteLeakedFilesCallback,
                                                               0,
                                                               0,
                                                               *((_DWORD *)this + 88),
                                                               0xA4CB800u);
                                        if ( GlobalCountersName >= 0 )
                                        {
                                          GlobalCountersName = CWxWorker::Queue(
                                                                 v2,
                                                                 (int (*)(struct CWxWorker *, struct CWxWorkContext *, unsigned __int64, void *))CCacheStore::ScheduledCleanupCallback,
                                                                 0,
                                                                 0,
                                                                 *((_DWORD *)this + 88),
                                                                 0xA4CB800u);
                                          if ( GlobalCountersName >= 0 )
                                          {
                                            GlobalCountersName = CWxWorker::Queue(
                                                                   v2,
                                                                   (int (*)(struct CWxWorker *, struct CWxWorkContext *, unsigned __int64, void *))CCacheStore::InfrequentCleanupCallback,
                                                                   0,
                                                                   0,
                                                                   6 * *((_DWORD *)this + 87),
                                                                   0xA4CB800u);
                                            if ( GlobalCountersName >= 0 )
                                            {
                                              GlobalCountersName = CWxWorker::Queue(
                                                                     v2,
                                                                     (int (*)(struct CWxWorker *, struct CWxWorkContext *, unsigned __int64, void *))CCacheStore::CleanupCallback,
                                                                     0,
                                                                     0,
                                                                     *((_DWORD *)this + 88),
                                                                     0xA4CB800u);
                                              if ( GlobalCountersName >= 0 )
                                              {
                                                GlobalCountersName = WxCreateThreadpoolWork(
                                                                       (void (*)(struct _TP_CALLBACK_INSTANCE *, void *, struct _TP_WORK *))CCacheStore::DeleteCacheFileCallback,
                                                                       this,
                                                                       v24,
                                                                       &v45);
                                                if ( GlobalCountersName < 0 )
                                                {
                                                  v43 = v45;
                                                }
                                                else
                                                {
                                                  v25 = v51;
                                                  v51 = (HANDLE)-1LL;
                                                  *((_QWORD *)this + 5) = v25;
                                                  *((_QWORD *)this + 3) = instance;
                                                  *((_QWORD *)this + 4) = sesid;
                                                  v26 = *((_QWORD *)this + 80);
                                                  instance = -1;
                                                  sesid = -1;
                                                  if ( *((_QWORD *)this + 79) > v26 )
                                                    *((_DWORD *)this + 162) = 1;
                                                  *((_QWORD *)this + 28) = v41;
                                                  v41 = 0;
                                                  CWxString::Transfer(
                                                    (CWxString *)szFilename,
                                                    (CCacheStore *)((char *)this + 8));
                                                  v27 = v40;
                                                  v28 = v45;
                                                  *((_QWORD *)this + 42) = v33;
                                                  *((_QWORD *)this + 56) = v50;
                                                  *((_QWORD *)this + 22) = v39;
                                                  *((_QWORD *)this + 68) = v38;
                                                  *((_QWORD *)this + 76) = v44;
                                                  *((_QWORD *)this + 40) = v49;
                                                  *((_QWORD *)this + 55) = v48;
                                                  *((_QWORD *)this + 31) = v37;
                                                  *((_QWORD *)this + 29) = v36;
                                                  v29 = hObject;
                                                  *((_QWORD *)this + 41) = v27;
                                                  v30 = v2;
                                                  *((_QWORD *)this + 57) = v1;
                                                  v2 = 0;
                                                  *((_QWORD *)this + 58) = v3;
                                                  v1 = 0;
                                                  *((_QWORD *)this + 59) = v4;
                                                  v3 = 0;
                                                  *((_QWORD *)this + 60) = v5;
                                                  v4 = 0;
                                                  *((_QWORD *)this + 61) = v6;
                                                  v5 = 0;
                                                  *((_QWORD *)this + 67) = v7;
                                                  v6 = 0;
                                                  *((_QWORD *)this + 69) = v29;
                                                  v7 = 0;
                                                  v33 = 0;
                                                  v40 = 0;
                                                  v50 = 0;
                                                  v39 = 0;
                                                  v38 = 0;
                                                  v44 = 0;
                                                  v49 = 0;
                                                  v48 = 0;
                                                  v37 = 0;
                                                  v36 = 0;
                                                  *((_QWORD *)this + 30) = v30;
                                                  hObject = 0;
                                                  *((_QWORD *)this + 34) = v28;
                                                  v43 = 0;
                                                  CWxWorker::Run(v30);
                                                }
                                              }
                                            }
                                          }
                                        }
                                      }
                                      else
                                      {
                                        v2 = v52;
                                      }
                                    }
                                    else
                                    {
                                      GlobalCountersName = -2147024882;
                                      v36 = 0;
                                    }
                                  }
                                  else
                                  {
                                    v37 = 0;
                                    GlobalCountersName = -2147024882;
                                  }
                                }
                              }
                            }
                          }
                          if ( v44 )
                            WxCloseThreadpoolTimer(v44);
                        }
                      }
                      goto LABEL_4;
                    }
                    v7 = 0;
                  }
                  else
                  {
                    v6 = 0;
                  }
                }
                else
                {
                  v5 = 0;
                }
              }
              else
              {
                v4 = 0;
              }
LABEL_66:
              LastError = -2147024882;
LABEL_67:
              GlobalCountersName = LastError;
            }
          }
        }
      }
    }
  }
LABEL_4:
  if ( sesid != -1 )
  {
    JetEndSession(sesid, 0);
    sesid = -1;
  }
  if ( instance != -1 )
  {
    JetTerm2(instance, 1u);
    instance = -1;
  }
  if ( v43 )
    WxCloseThreadpoolWork(v43);
  if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
    WPP_SF_d(1036, 19, WPP_d2eb1eb319bd39627e3f05ba48018899_Traceguids, (unsigned int)GlobalCountersName);
  if ( v38 )
    CClientProcessMap::Release(v38);
  if ( v7 )
    CClientProcess::Release(v7);
  if ( v6 )
    CBlobStore::Release((CBlobStore *)v6);
  if ( v5 )
    CCookieStore::Release((CCookieStore *)v5);
  if ( v4 )
    CHstsStore::Release((CHstsStore *)v4);
  if ( v3 )
    CDependencyStore::Release((CDependencyStore *)v3);
  if ( v2 )
    CWxWorker::Release(v2);
  if ( v36 )
    CWxWorkItemPool::Release(v36);
  if ( v37 )
    CInFlightPool::Release(v37);
  if ( v48 )
  {
    CWxWorkItemPool::Release(v48);
    v48 = 0;
  }
  if ( v49 )
  {
    CWxWorkItemPool::Release(v49);
    v49 = 0;
  }
  if ( v1 )
    CAppCacheDeletionManager::Release(v1);
  if ( v39 )
    CBloomMap::Release(v39);
  if ( v50 )
  {
    CAppCacheContainerMap::Release(v50);
    v50 = 0;
  }
  if ( v40 )
    CContainerPropsMap::Release(v40);
  if ( v33 )
    CContainerProps::Release(v33);
  if ( v41 )
    CBloomMapPartition::Release(v41);
  if ( hObject )
    CloseHandle(hObject);
  if ( v51 != (HANDLE)-1LL )
  {
    CloseHandle(v51);
    v51 = (HANDLE)-1LL;
  }
  CWxString::_Release((CWxString *)lpName);
  CWxString::_Release((CWxString *)lpFileName);
  CWxString::_Release((CWxString *)szFilename);
  CWxString::_Release((CWxString *)v56);
  return (unsigned int)GlobalCountersName;
}

```

## disassembly

```asm
0x1800b26b8  push    rbp
0x1800b26ba  push    rbx
0x1800b26bb  push    rsi
0x1800b26bc  push    rdi
0x1800b26bd  push    r12
0x1800b26bf  push    r13
0x1800b26c1  push    r14
0x1800b26c3  push    r15
0x1800b26c5  lea     rbp, [rsp-38h]
0x1800b26ca  sub     rsp, 138h
0x1800b26d1  mov     rax, cs:__security_cookie
0x1800b26d8  xor     rax, rsp
0x1800b26db  mov     [rbp+70h+var_50], rax
0x1800b26df  lea     rax, Data
0x1800b26e6  mov     [rsp+170h+var_130], rcx
0x1800b26eb  mov     r8, rcx
0x1800b26ee  mov     [rbp+70h+var_60], rax
0x1800b26f2  xor     ecx, ecx
0x1800b26f4  mov     [rbp+70h+szFilename], rax
0x1800b26f8  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1800b26fc  mov     [rsp+170h+var_134], ecx
0x1800b2700  mov     [rbp+70h+instance], rdx
0x1800b2704  mov     r13d, ecx
0x1800b2707  mov     [rbp+70h+sesid], rdx
0x1800b270b  mov     r12d, ecx
0x1800b270e  mov     [rbp+70h+var_A0], rdx
0x1800b2712  mov     edi, ecx
0x1800b2714  mov     [rbp+70h+var_58], rcx
0x1800b2718  mov     esi, ecx
0x1800b271a  mov     [rbp+70h+var_88], rcx
0x1800b271e  mov     r14d, ecx
0x1800b2721  mov     [rbp+70h+lpFileName], rax
0x1800b2725  mov     r15d, ecx
0x1800b2728  mov     [rbp+70h+var_68], rcx
0x1800b272c  mov     ebx, ecx
0x1800b272e  mov     [rbp+70h+lpName], rax
0x1800b2732  mov     [rbp+70h+var_78], rcx
0x1800b2736  mov     [rbp+70h+hObject], rcx
0x1800b273a  mov     [rbp+70h+var_F0], rcx
0x1800b273e  mov     [rsp+170h+var_128], rcx
0x1800b2743  mov     [rsp+170h+var_F8], rcx
0x1800b2748  mov     [rbp+70h+var_A8], rcx
0x1800b274c  mov     [rsp+170h+var_100], rcx
0x1800b2751  mov     [rsp+170h+var_120], rcx
0x1800b2756  mov     [rbp+70h+var_B0], rcx
0x1800b275a  mov     [rbp+70h+var_B8], rcx
0x1800b275e  mov     [rsp+170h+var_110], rcx
0x1800b2763  mov     [rsp+170h+var_118], rcx
0x1800b2768  mov     [rbp+70h+var_98], rcx
0x1800b276c  mov     [rbp+70h+var_E0], rcx
0x1800b2770  mov     [rbp+70h+var_D0], rcx
0x1800b2774  mov     [rsp+170h+var_108], rcx
0x1800b2779  mov     [rbp+70h+var_D8], rcx
0x1800b277d  test    byte ptr cs:xmmword_180266B60+1, 10h
0x1800b2784  jz      short loc_1800B279D
0x1800b2786  lea     edx, [rcx+12h]
0x1800b2789  mov     r9, r8
0x1800b278c  mov     ecx, 40Ch
0x1800b2791  lea     r8, WPP_d2eb1eb319bd39627e3f05ba48018899_Traceguids
0x1800b2798  call    WPP_SF_q
0x1800b279d  lea     r8, [rbp+70h+lpFileName]; struct CWxString *
0x1800b27a1  lea     rdx, [rbp+70h+var_60]; struct CWxString *
0x1800b27a5  lea     rcx, [rbp+70h+szFilename]; this
0x1800b27a9  call    ?DetermineCacheDatabasePaths@@YAJPEAVCWxString@@00@Z; DetermineCacheDatabasePaths(CWxString *,CWxString *,CWxString *)
0x1800b27ae  mov     [rsp+170h+var_140], eax
0x1800b27b2  test    eax, eax
0x1800b27b4  jns     loc_1800B2977
0x1800b27ba  mov     [rsp+170h+var_134], 34Fh
0x1800b27c2  mov     rcx, [rbp+70h+sesid]; sesid
0x1800b27c6  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1800b27ca  jnz     loc_1800B3296
0x1800b27d0  mov     rcx, [rbp+70h+instance]; instance
0x1800b27d4  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1800b27d8  jnz     loc_1800B32AB
0x1800b27de  mov     rax, [rbp+70h+var_E0]
0x1800b27e2  test    rax, rax
0x1800b27e5  jnz     loc_1800B32C3
0x1800b27eb  test    byte ptr cs:xmmword_180266B60+1, 10h
0x1800b27f2  jnz     loc_1800B2957
0x1800b27f8  mov     rcx, [rsp+170h+var_108]; this
0x1800b27fd  test    rcx, rcx
0x1800b2800  jnz     loc_1800B32D0
0x1800b2806  test    rbx, rbx
0x1800b2809  jz      short loc_1800B2813
0x1800b280b  mov     rcx, rbx; this
0x1800b280e  call    ?Release@CClientProcess@@QEAAKXZ; CClientProcess::Release(void)
0x1800b2813  xor     ebx, ebx
0x1800b2815  test    r15, r15
0x1800b2818  jnz     loc_1800B32DA
0x1800b281e  test    r14, r14
0x1800b2821  jnz     loc_1800B32E7
0x1800b2827  test    rsi, rsi
0x1800b282a  jz      short loc_1800B2834
0x1800b282c  mov     rcx, rsi; this
0x1800b282f  call    ?Release@CHstsStore@@QEAAKXZ; CHstsStore::Release(void)
0x1800b2834  test    rdi, rdi
0x1800b2837  jnz     loc_1800B2B0C
0x1800b283d  test    r12, r12
0x1800b2840  jnz     loc_1800B32F4
0x1800b2846  mov     rax, [rsp+170h+var_118]
0x1800b284b  test    rax, rax
0x1800b284e  jnz     loc_1800B3301
0x1800b2854  mov     rax, [rsp+170h+var_110]
0x1800b2859  test    rax, rax
0x1800b285c  jz      short loc_1800B2866
0x1800b285e  mov     rcx, rax; this
0x1800b2861  call    ?Release@CInFlightPool@@QEAAKXZ; CInFlightPool::Release(void)
0x1800b2866  mov     rcx, [rbp+70h+var_B8]; this
0x1800b286a  test    rcx, rcx
0x1800b286d  jz      short loc_1800B2878
0x1800b286f  call    ?Release@CWxWorkItemPool@@QEAAKXZ; CWxWorkItemPool::Release(void)
0x1800b2874  mov     [rbp+70h+var_B8], rbx
0x1800b2878  mov     rcx, [rbp+70h+var_B0]; this
0x1800b287c  test    rcx, rcx
0x1800b287f  jnz     loc_1800B2949
0x1800b2885  test    r13, r13
0x1800b2888  jnz     loc_1800B330E
0x1800b288e  mov     rcx, [rsp+170h+var_100]; this
0x1800b2893  test    rcx, rcx
0x1800b2896  jnz     loc_1800B2B19
0x1800b289c  mov     rcx, [rbp+70h+var_A8]; this
0x1800b28a0  test    rcx, rcx
0x1800b28a3  jnz     loc_1800B331B
0x1800b28a9  mov     rcx, [rsp+170h+var_F8]; this
0x1800b28ae  test    rcx, rcx
0x1800b28b1  jnz     loc_1800B2B23
0x1800b28b7  mov     rax, [rsp+170h+var_128]
0x1800b28bc  test    rax, rax
0x1800b28bf  jz      short loc_1800B28C9
0x1800b28c1  mov     rcx, rax; this
0x1800b28c4  call    ?Release@CContainerProps@@QEAAKXZ; CContainerProps::Release(void)
0x1800b28c9  mov     rcx, [rbp+70h+var_F0]; this
0x1800b28cd  test    rcx, rcx
0x1800b28d0  jz      short loc_1800B28D7
0x1800b28d2  call    ?Release@CBloomMapPartition@@QEAAKXZ; CBloomMapPartition::Release(void)
0x1800b28d7  mov     rax, [rbp+70h+hObject]
0x1800b28db  test    rax, rax
0x1800b28de  jz      short loc_1800B28E9
0x1800b28e0  mov     rcx, rax; hObject
0x1800b28e3  call    cs:__imp_CloseHandle
0x1800b28e9  mov     rcx, [rbp+70h+var_A0]; hObject
0x1800b28ed  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1800b28f1  jz      short loc_1800B2901
0x1800b28f3  call    cs:__imp_CloseHandle
0x1800b28f9  mov     [rbp+70h+var_A0], 0FFFFFFFFFFFFFFFFh
0x1800b2901  lea     rcx, [rbp+70h+lpName]; this
0x1800b2905  call    ?_Release@CWxString@@AEAAXXZ; CWxString::_Release(void)
0x1800b290a  lea     rcx, [rbp+70h+lpFileName]; this
0x1800b290e  call    ?_Release@CWxString@@AEAAXXZ; CWxString::_Release(void)
0x1800b2913  lea     rcx, [rbp+70h+szFilename]; this
0x1800b2917  call    ?_Release@CWxString@@AEAAXXZ; CWxString::_Release(void)
0x1800b291c  lea     rcx, [rbp+70h+var_60]; this
0x1800b2920  call    ?_Release@CWxString@@AEAAXXZ; CWxString::_Release(void)
0x1800b2925  mov     eax, [rsp+170h+var_140]
0x1800b2929  mov     rcx, [rbp+70h+var_50]
0x1800b292d  xor     rcx, rsp; StackCookie
0x1800b2930  call    __security_check_cookie
0x1800b2935  add     rsp, 138h
0x1800b293c  pop     r15
0x1800b293e  pop     r14
0x1800b2940  pop     r13
0x1800b2942  pop     r12
0x1800b2944  pop     rdi
0x1800b2945  pop     rsi
0x1800b2946  pop     rbx
0x1800b2947  pop     rbp
0x1800b2948  retn
0x1800b2949  call    ?Release@CWxWorkItemPool@@QEAAKXZ; CWxWorkItemPool::Release(void)
0x1800b294e  mov     [rbp+70h+var_B0], rbx
0x1800b2952  jmp     loc_1800B2885
0x1800b2957  mov     r9d, [rsp+170h+var_140]
0x1800b295c  lea     r8, WPP_d2eb1eb319bd39627e3f05ba48018899_Traceguids
0x1800b2963  mov     edx, 13h
0x1800b2968  mov     ecx, 40Ch
0x1800b296d  call    WPP_SF_d
0x1800b2972  jmp     loc_1800B27F8
0x1800b2977  mov     rcx, [rbp+70h+lpFileName]; lpFileName
0x1800b297b  lea     rdx, [rbp+70h+var_A0]; void **
0x1800b297f  call    ?LockDatabase@@YAJPEBGPEAPEAX@Z; LockDatabase(ushort const *,void * *)
0x1800b2984  mov     [rsp+170h+var_140], eax
0x1800b2988  test    eax, eax
0x1800b298a  js      loc_1800B3137
0x1800b2990  call    ?ConfigureGlobalJetParameters@@YAJXZ; ConfigureGlobalJetParameters(void)
0x1800b2995  mov     [rsp+170h+var_140], eax
0x1800b2999  test    eax, eax
0x1800b299b  js      loc_1800B3144
0x1800b29a1  mov     rdx, [rbp+70h+szFilename]; szFilename
0x1800b29a5  lea     r9, [rbp+70h+sesid]; unsigned __int64 *
0x1800b29a9  mov     rcx, [rbp+70h+var_60]; unsigned __int16 *
0x1800b29ad  lea     r8, [rbp+70h+instance]; unsigned __int64 *
0x1800b29b1  call    ?OpenCacheDatabase@@YAJPEBG0PEA_K1@Z; OpenCacheDatabase(ushort const *,ushort const *,unsigned __int64 *,unsigned __int64 *)
0x1800b29b6  mov     [rsp+170h+var_140], eax
0x1800b29ba  test    eax, eax
0x1800b29bc  js      loc_1800B3151
0x1800b29c2  mov     r9, [rsp+170h+var_130]
0x1800b29c7  xor     edx, edx; sesid
0x1800b29c9  mov     rcx, [rbp+70h+instance]; instance
0x1800b29cd  add     r9, 278h; plParam
0x1800b29d4  mov     [rsp+170h+cbMax], ebx; cbMax
0x1800b29d8  mov     [rsp+170h+szParam], rbx; szParam
0x1800b29dd  lea     r8d, [rdx+18h]; paramid
0x1800b29e1  call    cs:__imp_JetGetSystemParameterW
0x1800b29e7  mov     ecx, eax; int
0x1800b29e9  xor     edx, edx; int
0x1800b29eb  call    ?HRESULTFromJET_ERR@@YAJJH@Z; HRESULTFromJET_ERR(long,int)
0x1800b29f0  mov     [rsp+170h+var_140], eax
0x1800b29f4  test    eax, eax
0x1800b29f6  js      loc_1800B27C2
0x1800b29fc  mov     rcx, cs:g_hWxProcessHeap; hHeap
0x1800b2a03  xor     edx, edx; dwFlags
0x1800b2a05  mov     r8d, 0F0h; dwBytes
0x1800b2a0b  call    cs:__imp_HeapAlloc
0x1800b2a11  mov     [rsp+170h+var_128], rax
0x1800b2a16  test    rax, rax
0x1800b2a19  jz      loc_1800B2AE2
0x1800b2a1f  xor     edx, edx; Val
0x1800b2a21  mov     r8d, 0F0h; Size
0x1800b2a27  mov     rcx, rax; void *
0x1800b2a2a  call    memset_0
0x1800b2a2f  mov     rcx, [rsp+170h+var_128]; this
0x1800b2a34  call    ??0CContainerProps@@AEAA@XZ; CContainerProps::CContainerProps(void)
0x1800b2a39  mov     [rsp+170h+var_128], rax
0x1800b2a3e  test    rax, rax
0x1800b2a41  jz      loc_1800B2AE2
0x1800b2a47  lea     rcx, [rsp+170h+var_F8]; struct CContainerPropsMap **
0x1800b2a4c  call    ?CreateInstance@CContainerPropsMap@@SAJPEAPEAV1@@Z; CContainerPropsMap::CreateInstance(CContainerPropsMap * *)
0x1800b2a51  mov     [rsp+170h+var_140], eax
0x1800b2a55  test    eax, eax
0x1800b2a57  js      loc_1800B315E
0x1800b2a5d  mov     rcx, [rsp+170h+var_130]; struct CCacheStore *
0x1800b2a62  lea     rdx, [rbp+70h+var_A8]; struct CAppCacheContainerMap **
0x1800b2a66  call    ?CreateInstance@CAppCacheContainerMap@@SAJPEAVCCacheStore@@PEAPEAV1@@Z; CAppCacheContainerMap::CreateInstance(CCacheStore *,CAppCacheContainerMap * *)
0x1800b2a6b  mov     [rsp+170h+var_140], eax
0x1800b2a6f  test    eax, eax
0x1800b2a71  js      loc_1800B316B
0x1800b2a77  lea     rcx, [rsp+170h+var_120]; struct CAppCacheDeletionManager **
0x1800b2a7c  call    ?CreateInstance@CAppCacheDeletionManager@@SAJPEAPEAV1@@Z; CAppCacheDeletionManager::CreateInstance(CAppCacheDeletionManager * *)
0x1800b2a81  mov     r13, [rsp+170h+var_120]
0x1800b2a86  mov     [rsp+170h+var_140], eax
0x1800b2a8a  test    eax, eax
0x1800b2a8c  js      loc_1800B3178
0x1800b2a92  mov     rax, [rsp+170h+var_130]
0x1800b2a97  lea     rcx, [rbp+70h+var_F0]; struct CBloomMapPartition **
0x1800b2a9b  mov     [r13+58h], rax
0x1800b2a9f  call    ?CreateInstance@CBloomMapPartition@@SAJPEAPEAV1@@Z; CBloomMapPartition::CreateInstance(CBloomMapPartition * *)
0x1800b2aa4  mov     [rsp+170h+var_140], eax
0x1800b2aa8  test    eax, eax
0x1800b2aaa  js      loc_1800B3185
0x1800b2ab0  lea     rcx, [rsp+170h+var_100]; struct CBloomMap **
0x1800b2ab5  call    ?CreateInstance@CBloomMap@@SAJPEAPEAV1@@Z; CBloomMap::CreateInstance(CBloomMap * *)
0x1800b2aba  mov     [rsp+170h+var_140], eax
0x1800b2abe  test    eax, eax
0x1800b2ac0  js      loc_1800B3192
0x1800b2ac6  mov     ecx, 40h ; '@'; unsigned __int64
0x1800b2acb  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800b2ad0  mov     rdi, rax
0x1800b2ad3  test    rax, rax
0x1800b2ad6  jnz     short loc_1800B2B2D
0x1800b2ad8  mov     [rsp+170h+var_134], 377h
0x1800b2ae0  jmp     short loc_1800B2AFE
0x1800b2ae2  xor     eax, eax
0x1800b2ae4  mov     [rsp+170h+var_134], 36Ah
0x1800b2aec  mov     [rsp+170h+var_128], rax
0x1800b2af1  jmp     short loc_1800B2AFE
0x1800b2af3  xor     r15d, r15d
0x1800b2af6  mov     [rsp+170h+var_134], 380h
0x1800b2afe  mov     eax, 8007000Eh
0x1800b2b03  mov     [rsp+170h+var_140], eax
0x1800b2b07  jmp     loc_1800B27C2
0x1800b2b0c  mov     rcx, rdi; this
0x1800b2b0f  call    ?Release@CDependencyStore@@QEAAKXZ; CDependencyStore::Release(void)
0x1800b2b14  jmp     loc_1800B283D
0x1800b2b19  call    ?Release@CBloomMap@@QEAAKXZ; CBloomMap::Release(void)
0x1800b2b1e  jmp     loc_1800B289C
0x1800b2b23  call    ?Release@CContainerPropsMap@@QEAAKXZ; CContainerPropsMap::Release(void)
0x1800b2b28  jmp     loc_1800B28B7
0x1800b2b2d  xor     edx, edx; Val
0x1800b2b2f  mov     rcx, rdi; void *
0x1800b2b32  lea     r8d, [rdx+40h]; Size
0x1800b2b36  call    memset_0
0x1800b2b3b  lea     rcx, [rdi+18h]; lpCriticalSection
0x1800b2b3f  mov     dword ptr [rdi], 1
0x1800b2b45  call    cs:__imp_InitializeCriticalSection
0x1800b2b4b  mov     rcx, rdi; this
0x1800b2b4e  call    ?Initialize@CDependencyStore@@QEAAJXZ; CDependencyStore::Initialize(void)
0x1800b2b53  mov     [rsp+170h+var_140], eax
0x1800b2b57  test    eax, eax
0x1800b2b59  js      loc_1800B319F
0x1800b2b5f  mov     rcx, cs:g_hWxProcessHeap; hHeap
0x1800b2b66  xor     edx, edx; dwFlags
0x1800b2b68  lea     r8d, [rdx+40h]; dwBytes
0x1800b2b6c  call    cs:__imp_HeapAlloc
0x1800b2b72  mov     rsi, rax
0x1800b2b75  test    rax, rax
0x1800b2b78  jz      loc_1800B2E43
0x1800b2b7e  xor     edx, edx; Val
0x1800b2b80  mov     rcx, rax; void *
0x1800b2b83  lea     r8d, [rdx+40h]; Size
0x1800b2b87  call    memset_0
0x1800b2b8c  lea     rcx, [rsi+18h]; lpCriticalSection
  ... truncated ...
```
