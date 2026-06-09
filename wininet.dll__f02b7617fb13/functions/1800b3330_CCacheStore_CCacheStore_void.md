# CCacheStore::~CCacheStore(void)

- ea: `0x1800b3330`
- end: `0x1800b3823`
- name: `??1CCacheStore@@AEAA@XZ`
- size: `1267`
- prototype: `void __fastcall(CCacheStore *__hidden this)`
- caller_count: `1`
- callee_count: `28`
- tags: `authz_impersonation`

## callers

- `0x180042c58`

## callees

- `0x1800201a0`
- `0x180020f74`
- `0x180025910`
- `0x18002a498`
- `0x18003e6b4`
- `0x180041814`
- `0x180044588`
- `0x18004aa94`
- `0x180086aa4`
- `0x18008749c`
- `0x180087f04`
- `0x1800afa98`
- `0x1800b0eec`
- `0x1800b3330`
- `0x1800b382c`
- `0x1800b3860`
- `0x1800b38a4`
- `0x1801282dc`
- `0x18012ec20`
- `0x180134444`
- `0x1801387a0`
- `0x1801387e4`
- `0x180141344`
- `0x180141878`
- `0x180141b1c`
- `0x180147a48`
- `0x1801a9d54`
- `0x1801b0f68`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800b3421`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800b3466`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800b34eb`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800b3530`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800b3585`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800b35a2`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800b35bc`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800b35c6`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800b3421`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800b3466`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800b34eb`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800b3530`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800b3585`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800b35a2`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800b35bc`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800b35c6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800b3410`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800b35d5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800b3608`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800b3789`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800b3410`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800b35d5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800b3608`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800b3789`
- `ESENT!JetTerm2` at `0x1800b3678`
- `ESENT!JetTerm2` at `0x1800b3678`
- `ESENT!JetEndSession` at `0x1800b377a`
- `ESENT!JetEndSession` at `0x1800b377a`

## pseudocode

```c
void __fastcall CCacheStore::~CCacheStore(CCacheStore *this)
{
  struct _TP_WORK *v2; // rcx
  CWxWorker *v3; // rcx
  CWxWorkItemPool *v4; // rcx
  CAppCacheDeletionManager *v5; // rcx
  CJetContext *v6; // rcx
  CWxWorkItemPool *v7; // rcx
  CWxWorkItemPool *v8; // rcx
  JET_SESID v9; // rcx
  JET_INSTANCE v10; // rcx
  void *v11; // rcx
  void *v12; // rcx
  void *v13; // rcx
  CClientProcessMap *v14; // rcx
  CClientProcess *v15; // rcx
  CBlobStore *v16; // rcx
  CCookieStore *v17; // rcx
  CHstsStore *v18; // rcx
  CDependencyStore *v19; // rcx
  CAppCacheDeletionManager *v20; // rcx
  CAppCacheContainerMap *v21; // rcx
  CWxWorkItemPool *v22; // rcx
  CContainerProps *v23; // rcx
  CContainerPropsMap *v24; // rcx
  CWxWorkItemPool *v25; // rcx
  CInFlightPool *v26; // rcx
  CWxWorker *v27; // rcx
  CWxWorkItemPool *v28; // rcx
  CBloomMapPartition *v29; // rcx
  CBloomMap *v30; // rcx
  CJetContext *v31; // rcx
  void *v32; // rcx
  CContainerPropsMap *v33; // rcx
  CWxWorker *v34; // rcx
  int v35; // edx

  v2 = (struct _TP_WORK *)*((_QWORD *)this + 34);
  if ( v2 )
  {
    WxWaitForThreadpoolWorkCallbacks(v2, 0);
    WxCloseThreadpoolWork(*((struct _TP_WORK **)this + 34));
    *((_QWORD *)this + 34) = 0;
  }
  v3 = (CWxWorker *)*((_QWORD *)this + 30);
  if ( v3 )
  {
    CWxWorker::Terminate(v3);
    v34 = (CWxWorker *)*((_QWORD *)this + 30);
    if ( v34 )
    {
      CWxWorker::Release(v34);
      *((_QWORD *)this + 30) = 0;
    }
  }
  v4 = (CWxWorkItemPool *)*((_QWORD *)this + 29);
  if ( v4 )
  {
    CWxWorkItemPool::Release(v4);
    *((_QWORD *)this + 29) = 0;
  }
  if ( *((_QWORD *)this + 76) )
  {
    if ( *((_DWORD *)this + 150) )
      WxFatalWin32Error((unsigned int)v4);
    CCacheStore::StartActivity(this);
    WxSetThreadpoolTimer(*((struct _TP_TIMER **)this + 76), 0, 0, 0);
    WxWaitForThreadpoolTimerCallbacks(*((struct _TP_TIMER **)this + 76), v35);
    WxCloseThreadpoolTimer(*((struct _TP_TIMER **)this + 76));
    *((_QWORD *)this + 76) = 0;
  }
  if ( *((_QWORD *)this + 41) )
  {
    CWxRefMap<CContainerPropsMap,CContainerProps>::Dispose();
    v33 = (CContainerPropsMap *)*((_QWORD *)this + 41);
    if ( v33 )
    {
      CContainerPropsMap::Release(v33);
      *((_QWORD *)this + 41) = 0;
    }
  }
  v5 = (CAppCacheDeletionManager *)*((_QWORD *)this + 57);
  if ( v5 )
    CAppCacheDeletionManager::Shutdown(v5);
  v6 = (CJetContext *)*((_QWORD *)this + 16);
  if ( v6 )
  {
    CJetContext::Release(v6);
    *((_QWORD *)this + 16) = 0;
  }
  v7 = (CWxWorkItemPool *)*((_QWORD *)this + 55);
  if ( v7 )
  {
    CWxWorkItemPool::Release(v7);
    *((_QWORD *)this + 55) = 0;
  }
  v8 = (CWxWorkItemPool *)*((_QWORD *)this + 40);
  if ( v8 )
  {
    CWxWorkItemPool::Release(v8);
    *((_QWORD *)this + 40) = 0;
  }
  v9 = *((_QWORD *)this + 4);
  if ( v9 != -1 )
  {
    JetEndSession(v9, 0);
    *((_QWORD *)this + 4) = -1;
  }
  v10 = *((_QWORD *)this + 3);
  if ( v10 != -1 )
  {
    JetTerm2(v10, 1u);
    *((_QWORD *)this + 3) = -1;
  }
  v11 = (void *)*((_QWORD *)this + 69);
  if ( v11 )
  {
    CloseHandle(v11);
    *((_QWORD *)this + 69) = 0;
  }
  v12 = (void *)*((_QWORD *)this + 5);
  if ( v12 != (void *)-1LL )
  {
    CloseHandle(v12);
    *((_QWORD *)this + 5) = -1;
  }
  DeleteCriticalSection((LPCRITICAL_SECTION)this + 14);
  v13 = (void *)*((_QWORD *)this + 69);
  if ( v13 )
  {
    CloseHandle(v13);
    *((_QWORD *)this + 69) = 0;
  }
  v14 = (CClientProcessMap *)*((_QWORD *)this + 68);
  if ( v14 )
  {
    CClientProcessMap::Release(v14);
    *((_QWORD *)this + 68) = 0;
  }
  v15 = (CClientProcess *)*((_QWORD *)this + 67);
  if ( v15 )
  {
    CClientProcess::Release(v15);
    *((_QWORD *)this + 67) = 0;
  }
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 496));
  v16 = (CBlobStore *)*((_QWORD *)this + 61);
  if ( v16 )
  {
    CBlobStore::Release(v16);
    *((_QWORD *)this + 61) = 0;
  }
  v17 = (CCookieStore *)*((_QWORD *)this + 60);
  if ( v17 )
  {
    CCookieStore::Release(v17);
    *((_QWORD *)this + 60) = 0;
  }
  v18 = (CHstsStore *)*((_QWORD *)this + 59);
  if ( v18 )
  {
    CHstsStore::Release(v18);
    *((_QWORD *)this + 59) = 0;
  }
  v19 = (CDependencyStore *)*((_QWORD *)this + 58);
  if ( v19 )
  {
    CDependencyStore::Release(v19);
    *((_QWORD *)this + 58) = 0;
  }
  v20 = (CAppCacheDeletionManager *)*((_QWORD *)this + 57);
  if ( v20 )
  {
    CAppCacheDeletionManager::Release(v20);
    *((_QWORD *)this + 57) = 0;
  }
  v21 = (CAppCacheContainerMap *)*((_QWORD *)this + 56);
  if ( v21 )
  {
    CAppCacheContainerMap::Release(v21);
    *((_QWORD *)this + 56) = 0;
  }
  v22 = (CWxWorkItemPool *)*((_QWORD *)this + 55);
  if ( v22 )
  {
    CWxWorkItemPool::Release(v22);
    *((_QWORD *)this + 55) = 0;
  }
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 368));
  v23 = (CContainerProps *)*((_QWORD *)this + 42);
  if ( v23 )
  {
    CContainerProps::Release(v23);
    *((_QWORD *)this + 42) = 0;
  }
  v24 = (CContainerPropsMap *)*((_QWORD *)this + 41);
  if ( v24 )
  {
    CContainerPropsMap::Release(v24);
    *((_QWORD *)this + 41) = 0;
  }
  v25 = (CWxWorkItemPool *)*((_QWORD *)this + 40);
  if ( v25 )
  {
    CWxWorkItemPool::Release(v25);
    *((_QWORD *)this + 40) = 0;
  }
  DeleteCriticalSection((LPCRITICAL_SECTION)this + 7);
  v26 = (CInFlightPool *)*((_QWORD *)this + 31);
  if ( v26 )
  {
    CInFlightPool::Release(v26);
    *((_QWORD *)this + 31) = 0;
  }
  v27 = (CWxWorker *)*((_QWORD *)this + 30);
  if ( v27 )
  {
    CWxWorker::Release(v27);
    *((_QWORD *)this + 30) = 0;
  }
  v28 = (CWxWorkItemPool *)*((_QWORD *)this + 29);
  if ( v28 )
  {
    CWxWorkItemPool::Release(v28);
    *((_QWORD *)this + 29) = 0;
  }
  v29 = (CBloomMapPartition *)*((_QWORD *)this + 28);
  if ( v29 )
  {
    CBloomMapPartition::Release(v29);
    *((_QWORD *)this + 28) = 0;
  }
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 184));
  v30 = (CBloomMap *)*((_QWORD *)this + 22);
  if ( v30 )
  {
    CBloomMap::Release(v30);
    *((_QWORD *)this + 22) = 0;
  }
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 136));
  v31 = (CJetContext *)*((_QWORD *)this + 16);
  if ( v31 )
  {
    CJetContext::Release(v31);
    *((_QWORD *)this + 16) = 0;
  }
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 88));
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
  v32 = (void *)*((_QWORD *)this + 5);
  if ( v32 != (void *)-1LL )
  {
    CloseHandle(v32);
    *((_QWORD *)this + 5) = -1;
  }
  CWxString::_Release((CCacheStore *)((char *)this + 8));
}

```

## disassembly

```asm
0x1800b3330  mov     [rsp+arg_0], rbx
0x1800b3335  mov     [rsp+arg_8], rsi
0x1800b333a  push    rdi
0x1800b333b  sub     rsp, 20h
0x1800b333f  mov     rbx, rcx
0x1800b3342  xor     edi, edi
0x1800b3344  mov     rcx, [rcx+110h]; struct _TP_WORK *
0x1800b334b  test    rcx, rcx
0x1800b334e  jnz     loc_1800B36E0
0x1800b3354  mov     rcx, [rbx+0F0h]; this
0x1800b335b  test    rcx, rcx
0x1800b335e  jnz     loc_1800B36BA
0x1800b3364  mov     rcx, [rbx+0E8h]; unsigned int
0x1800b336b  test    rcx, rcx
0x1800b336e  jnz     loc_1800B36FF
0x1800b3374  cmp     [rbx+260h], rdi
0x1800b337b  jnz     loc_1800B3710
0x1800b3381  mov     rcx, [rbx+148h]
0x1800b3388  test    rcx, rcx
0x1800b338b  jnz     loc_1800B364D
0x1800b3391  mov     rcx, [rbx+1C8h]; this
0x1800b3398  test    rcx, rcx
0x1800b339b  jnz     loc_1800B375D
0x1800b33a1  mov     rcx, [rbx+80h]; this
0x1800b33a8  test    rcx, rcx
0x1800b33ab  jnz     loc_1800B3767
0x1800b33b1  mov     rcx, [rbx+1B8h]; this
0x1800b33b8  test    rcx, rcx
0x1800b33bb  jz      short loc_1800B33C9
0x1800b33bd  call    ?Release@CWxWorkItemPool@@QEAAKXZ; CWxWorkItemPool::Release(void)
0x1800b33c2  mov     [rbx+1B8h], rdi
0x1800b33c9  mov     rcx, [rbx+140h]; this
0x1800b33d0  test    rcx, rcx
0x1800b33d3  jnz     loc_1800B35F7
0x1800b33d9  mov     rcx, [rbx+20h]; sesid
0x1800b33dd  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800b33e1  cmp     rcx, rsi
0x1800b33e4  jnz     loc_1800B3778
0x1800b33ea  mov     rcx, [rbx+18h]; instance
0x1800b33ee  cmp     rcx, rsi
0x1800b33f1  jnz     loc_1800B3673
0x1800b33f7  mov     rcx, [rbx+228h]; hObject
0x1800b33fe  test    rcx, rcx
0x1800b3401  jnz     loc_1800B3789
0x1800b3407  mov     rcx, [rbx+28h]; hObject
0x1800b340b  cmp     rcx, rsi
0x1800b340e  jz      short loc_1800B341A
0x1800b3410  call    cs:__imp_CloseHandle
0x1800b3416  mov     [rbx+28h], rsi
0x1800b341a  lea     rcx, [rbx+230h]; lpCriticalSection
0x1800b3421  call    cs:__imp_DeleteCriticalSection
0x1800b3427  mov     rcx, [rbx+228h]; hObject
0x1800b342e  test    rcx, rcx
0x1800b3431  jnz     loc_1800B3608
0x1800b3437  mov     rcx, [rbx+220h]; this
0x1800b343e  test    rcx, rcx
0x1800b3441  jnz     loc_1800B379B
0x1800b3447  mov     rcx, [rbx+218h]; this
0x1800b344e  test    rcx, rcx
0x1800b3451  jz      short loc_1800B345F
0x1800b3453  call    ?Release@CClientProcess@@QEAAKXZ; CClientProcess::Release(void)
0x1800b3458  mov     [rbx+218h], rdi
0x1800b345f  lea     rcx, [rbx+1F0h]; lpCriticalSection
0x1800b3466  call    cs:__imp_DeleteCriticalSection
0x1800b346c  mov     rcx, [rbx+1E8h]; this
0x1800b3473  test    rcx, rcx
0x1800b3476  jnz     loc_1800B37AC
0x1800b347c  mov     rcx, [rbx+1E0h]; this
0x1800b3483  test    rcx, rcx
0x1800b3486  jnz     loc_1800B37BD
0x1800b348c  mov     rcx, [rbx+1D8h]; this
0x1800b3493  test    rcx, rcx
0x1800b3496  jnz     loc_1800B363C
0x1800b349c  mov     rcx, [rbx+1D0h]; this
0x1800b34a3  test    rcx, rcx
0x1800b34a6  jnz     loc_1800B3687
0x1800b34ac  mov     rcx, [rbx+1C8h]; this
0x1800b34b3  test    rcx, rcx
0x1800b34b6  jnz     loc_1800B37CE
0x1800b34bc  mov     rcx, [rbx+1C0h]; this
0x1800b34c3  test    rcx, rcx
0x1800b34c6  jnz     loc_1800B37DF
0x1800b34cc  mov     rcx, [rbx+1B8h]; this
0x1800b34d3  test    rcx, rcx
0x1800b34d6  jz      short loc_1800B34E4
0x1800b34d8  call    ?Release@CWxWorkItemPool@@QEAAKXZ; CWxWorkItemPool::Release(void)
0x1800b34dd  mov     [rbx+1B8h], rdi
0x1800b34e4  lea     rcx, [rbx+170h]; lpCriticalSection
0x1800b34eb  call    cs:__imp_DeleteCriticalSection
0x1800b34f1  mov     rcx, [rbx+150h]; this
0x1800b34f8  test    rcx, rcx
0x1800b34fb  jnz     loc_1800B361A
0x1800b3501  mov     rcx, [rbx+148h]; this
0x1800b3508  test    rcx, rcx
0x1800b350b  jnz     loc_1800B36A9
0x1800b3511  mov     rcx, [rbx+140h]; this
0x1800b3518  test    rcx, rcx
0x1800b351b  jz      short loc_1800B3529
0x1800b351d  call    ?Release@CWxWorkItemPool@@QEAAKXZ; CWxWorkItemPool::Release(void)
0x1800b3522  mov     [rbx+140h], rdi
0x1800b3529  lea     rcx, [rbx+118h]; lpCriticalSection
0x1800b3530  call    cs:__imp_DeleteCriticalSection
0x1800b3536  mov     rcx, [rbx+0F8h]; this
0x1800b353d  test    rcx, rcx
0x1800b3540  jz      short loc_1800B354E
0x1800b3542  call    ?Release@CInFlightPool@@QEAAKXZ; CInFlightPool::Release(void)
0x1800b3547  mov     [rbx+0F8h], rdi
0x1800b354e  mov     rcx, [rbx+0F0h]; this
0x1800b3555  test    rcx, rcx
0x1800b3558  jnz     loc_1800B37F0
0x1800b355e  mov     rcx, [rbx+0E8h]; this
0x1800b3565  test    rcx, rcx
0x1800b3568  jnz     loc_1800B3801
0x1800b356e  mov     rcx, [rbx+0E0h]; this
0x1800b3575  test    rcx, rcx
0x1800b3578  jnz     loc_1800B362B
0x1800b357e  lea     rcx, [rbx+0B8h]; lpCriticalSection
0x1800b3585  call    cs:__imp_DeleteCriticalSection
0x1800b358b  mov     rcx, [rbx+0B0h]; this
0x1800b3592  test    rcx, rcx
0x1800b3595  jnz     loc_1800B3698
0x1800b359b  lea     rcx, [rbx+88h]; lpCriticalSection
0x1800b35a2  call    cs:__imp_DeleteCriticalSection
0x1800b35a8  mov     rcx, [rbx+80h]; this
0x1800b35af  test    rcx, rcx
0x1800b35b2  jnz     loc_1800B3812
0x1800b35b8  lea     rcx, [rbx+58h]; lpCriticalSection
0x1800b35bc  call    cs:__imp_DeleteCriticalSection
0x1800b35c2  lea     rcx, [rbx+30h]; lpCriticalSection
0x1800b35c6  call    cs:__imp_DeleteCriticalSection
0x1800b35cc  mov     rcx, [rbx+28h]; hObject
0x1800b35d0  cmp     rcx, rsi
0x1800b35d3  jz      short loc_1800B35DF
0x1800b35d5  call    cs:__imp_CloseHandle
0x1800b35db  mov     [rbx+28h], rsi
0x1800b35df  lea     rcx, [rbx+8]; this
0x1800b35e3  mov     rbx, [rsp+28h+arg_0]
0x1800b35e8  mov     rsi, [rsp+28h+arg_8]
0x1800b35ed  add     rsp, 20h
0x1800b35f1  pop     rdi
0x1800b35f2  jmp     ?_Release@CWxString@@AEAAXXZ; CWxString::_Release(void)
0x1800b35f7  call    ?Release@CWxWorkItemPool@@QEAAKXZ; CWxWorkItemPool::Release(void)
0x1800b35fc  mov     [rbx+140h], rdi
0x1800b3603  jmp     loc_1800B33D9
0x1800b3608  call    cs:__imp_CloseHandle
0x1800b360e  mov     [rbx+228h], rdi
0x1800b3615  jmp     loc_1800B3437
0x1800b361a  call    ?Release@CContainerProps@@QEAAKXZ; CContainerProps::Release(void)
0x1800b361f  mov     [rbx+150h], rdi
0x1800b3626  jmp     loc_1800B3501
0x1800b362b  call    ?Release@CBloomMapPartition@@QEAAKXZ; CBloomMapPartition::Release(void)
0x1800b3630  mov     [rbx+0E0h], rdi
0x1800b3637  jmp     loc_1800B357E
0x1800b363c  call    ?Release@CHstsStore@@QEAAKXZ; CHstsStore::Release(void)
0x1800b3641  mov     [rbx+1D8h], rdi
0x1800b3648  jmp     loc_1800B349C
0x1800b364d  call    ?Dispose@?$CWxRefMap@VCContainerPropsMap@@VCContainerProps@@@@QEAAXXZ; CWxRefMap<CContainerPropsMap,CContainerProps>::Dispose(void)
0x1800b3652  mov     rcx, [rbx+148h]; this
0x1800b3659  test    rcx, rcx
0x1800b365c  jz      loc_1800B3391
0x1800b3662  call    ?Release@CContainerPropsMap@@QEAAKXZ; CContainerPropsMap::Release(void)
0x1800b3667  mov     [rbx+148h], rdi
0x1800b366e  jmp     loc_1800B3391
0x1800b3673  mov     edx, 1; grbit
0x1800b3678  call    cs:__imp_JetTerm2
0x1800b367e  mov     [rbx+18h], rsi
0x1800b3682  jmp     loc_1800B33F7
0x1800b3687  call    ?Release@CDependencyStore@@QEAAKXZ; CDependencyStore::Release(void)
0x1800b368c  mov     [rbx+1D0h], rdi
0x1800b3693  jmp     loc_1800B34AC
0x1800b3698  call    ?Release@CBloomMap@@QEAAKXZ; CBloomMap::Release(void)
0x1800b369d  mov     [rbx+0B0h], rdi
0x1800b36a4  jmp     loc_1800B359B
0x1800b36a9  call    ?Release@CContainerPropsMap@@QEAAKXZ; CContainerPropsMap::Release(void)
0x1800b36ae  mov     [rbx+148h], rdi
0x1800b36b5  jmp     loc_1800B3511
0x1800b36ba  call    ?Terminate@CWxWorker@@QEAAXXZ; CWxWorker::Terminate(void)
0x1800b36bf  mov     rcx, [rbx+0F0h]; this
0x1800b36c6  test    rcx, rcx
0x1800b36c9  jz      loc_1800B3364
0x1800b36cf  call    ?Release@CWxWorker@@QEAAKXZ; CWxWorker::Release(void)
0x1800b36d4  mov     [rbx+0F0h], rdi
0x1800b36db  jmp     loc_1800B3364
0x1800b36e0  xor     edx, edx; int
0x1800b36e2  call    ?WxWaitForThreadpoolWorkCallbacks@@YAXPEAU_TP_WORK@@H@Z; WxWaitForThreadpoolWorkCallbacks(_TP_WORK *,int)
0x1800b36e7  mov     rcx, [rbx+110h]; struct _TP_WORK *
0x1800b36ee  call    ?WxCloseThreadpoolWork@@YAXPEAU_TP_WORK@@@Z; WxCloseThreadpoolWork(_TP_WORK *)
0x1800b36f3  mov     [rbx+110h], rdi
0x1800b36fa  jmp     loc_1800B3354
0x1800b36ff  call    ?Release@CWxWorkItemPool@@QEAAKXZ; CWxWorkItemPool::Release(void)
0x1800b3704  mov     [rbx+0E8h], rdi
0x1800b370b  jmp     loc_1800B3374
0x1800b3710  cmp     [rbx+258h], edi
0x1800b3716  jz      short loc_1800B371D
0x1800b3718  call    ?WxFatalWin32Error@@YAXK@Z; WxFatalWin32Error(ulong)
0x1800b371d  mov     rcx, rbx; this
0x1800b3720  call    ?StartActivity@CCacheStore@@QEAAXXZ; CCacheStore::StartActivity(void)
0x1800b3725  mov     rcx, [rbx+260h]; struct _TP_TIMER *
0x1800b372c  xor     r9d, r9d; unsigned int
0x1800b372f  xor     r8d, r8d; unsigned int
0x1800b3732  xor     edx, edx; struct _FILETIME *
0x1800b3734  call    ?WxSetThreadpoolTimer@@YAXPEAU_TP_TIMER@@PEAU_FILETIME@@KK@Z; WxSetThreadpoolTimer(_TP_TIMER *,_FILETIME *,ulong,ulong)
0x1800b3739  mov     rcx, [rbx+260h]; struct _TP_TIMER *
0x1800b3740  call    ?WxWaitForThreadpoolTimerCallbacks@@YAXPEAU_TP_TIMER@@H@Z; WxWaitForThreadpoolTimerCallbacks(_TP_TIMER *,int)
0x1800b3745  mov     rcx, [rbx+260h]; struct _TP_TIMER *
0x1800b374c  call    ?WxCloseThreadpoolTimer@@YAXPEAU_TP_TIMER@@@Z; WxCloseThreadpoolTimer(_TP_TIMER *)
0x1800b3751  mov     [rbx+260h], rdi
0x1800b3758  jmp     loc_1800B3381
0x1800b375d  call    ?Shutdown@CAppCacheDeletionManager@@QEAAXXZ; CAppCacheDeletionManager::Shutdown(void)
0x1800b3762  jmp     loc_1800B33A1
0x1800b3767  call    ?Release@CJetContext@@QEAAKXZ; CJetContext::Release(void)
0x1800b376c  mov     [rbx+80h], rdi
0x1800b3773  jmp     loc_1800B33B1
0x1800b3778  xor     edx, edx; grbit
0x1800b377a  call    cs:__imp_JetEndSession
0x1800b3780  mov     [rbx+20h], rsi
0x1800b3784  jmp     loc_1800B33EA
0x1800b3789  call    cs:__imp_CloseHandle
0x1800b378f  mov     [rbx+228h], rdi
0x1800b3796  jmp     loc_1800B3407
0x1800b379b  call    ?Release@CClientProcessMap@@QEAAKXZ; CClientProcessMap::Release(void)
0x1800b37a0  mov     [rbx+220h], rdi
0x1800b37a7  jmp     loc_1800B3447
0x1800b37ac  call    ?Release@CBlobStore@@QEAAKXZ; CBlobStore::Release(void)
0x1800b37b1  mov     [rbx+1E8h], rdi
0x1800b37b8  jmp     loc_1800B347C
0x1800b37bd  call    ?Release@CCookieStore@@QEAAKXZ; CCookieStore::Release(void)
0x1800b37c2  mov     [rbx+1E0h], rdi
0x1800b37c9  jmp     loc_1800B348C
0x1800b37ce  call    ?Release@CAppCacheDeletionManager@@QEAAKXZ; CAppCacheDeletionManager::Release(void)
0x1800b37d3  mov     [rbx+1C8h], rdi
0x1800b37da  jmp     loc_1800B34BC
0x1800b37df  call    ?Release@CAppCacheContainerMap@@QEAAKXZ; CAppCacheContainerMap::Release(void)
0x1800b37e4  mov     [rbx+1C0h], rdi
0x1800b37eb  jmp     loc_1800B34CC
0x1800b37f0  call    ?Release@CWxWorker@@QEAAKXZ; CWxWorker::Release(void)
0x1800b37f5  mov     [rbx+0F0h], rdi
0x1800b37fc  jmp     loc_1800B355E
0x1800b3801  call    ?Release@CWxWorkItemPool@@QEAAKXZ; CWxWorkItemPool::Release(void)
0x1800b3806  mov     [rbx+0E8h], rdi
0x1800b380d  jmp     loc_1800B356E
0x1800b3812  call    ?Release@CJetContext@@QEAAKXZ; CJetContext::Release(void)
0x1800b3817  mov     [rbx+80h], rdi
0x1800b381e  jmp     loc_1800B35B8
```
