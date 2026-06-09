# CHardwareManager::Cleanup(void)

- ea: `0x18005262c`
- end: `0x18005289a`
- name: `?Cleanup@CHardwareManager@@SAXXZ`
- size: `622`
- prototype: `void(void)`
- caller_count: `2`
- callee_count: `18`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800151f0`
- `0x1800515c8`

## callees

- `0x180003f34`
- `0x18000603c`
- `0x18000741c`
- `0x180007690`
- `0x1800119c4`
- `0x180022c14`
- `0x18003461c`
- `0x1800393e8`
- `0x18003f2dc`
- `0x180051654`
- `0x1800516e0`
- `0x180051748`
- `0x18005262c`
- `0x1800530c4`
- `0x180053324`
- `0x180054720`
- `0x180055f74`
- `0x180060964`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180052854`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180052854`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800527e2`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800527e2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800527be`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800527be`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800526cc`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800526cc`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800526d9`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800526d9`
- `api-ms-win-core-io-l1-1-0!PostQueuedCompletionStatus` at `0x1800526f0`
- `api-ms-win-core-io-l1-1-0!PostQueuedCompletionStatus` at `0x1800526f0`

## string_xrefs

- `0x180052647`: `onecore\ds\security\biometrics\service\server\hardwaremanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void CHardwareManager::Cleanup(void)
{
  int v0; // eax
  struct CHardwareManager *v1; // rax
  struct CHardwareManager *v2; // rax
  struct CHardwareManager *v3; // rax
  CHardwareManager *v4; // rax
  struct CHardwareManager *v5; // rax
  CThread *v6; // rcx
  const char *v7; // r9
  struct CHardwareManager *v9; // rax
  unsigned int v10; // edx
  int *v11; // r8
  int v12; // eax
  struct CHardwareManager *v13; // rax
  int v14; // eax
  struct CHardwareManager *v15; // rax
  unsigned int v16; // edx
  int *v17; // r8
  int v18; // eax
  struct CHardwareManager *v19; // rax
  RTL_SRWLOCK *v20; // rsi
  __int128 *v21; // rdx
  struct CHardwareManager *v22; // rax
  _QWORD *v23; // rdi
  _QWORD *v24; // rbx
  __int64 v25; // rcx
  __int64 v26; // rcx
  __int128 v27; // [rsp+20h] [rbp-28h] BYREF
  struct _GUID v28; // [rsp+30h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+20h]

  if ( (unsigned __int64)(*((_QWORD *)CHardwareManager::Instance() + 16) - 1LL) <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    v28 = *(struct _GUID *)&xmmword_1800DF158;
    v0 = StorageManagerExport(&v28);
    if ( v0 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x232,
        (unsigned int)"onecore\\ds\\security\\biometrics\\service\\server\\hardwaremanager.cpp",
        (const char *)(unsigned int)v0,
        v27);
    v1 = CHardwareManager::Instance();
    BioTrustlet::Stop((struct CHardwareManager *)((char *)v1 + 88));
    v2 = CHardwareManager::Instance();
    BioTrustlet::ServerUnbind((struct CHardwareManager *)((char *)v2 + 88));
  }
  v3 = CHardwareManager::Instance();
  handle_thread::Stop((struct CHardwareManager *)((char *)v3 + 56));
  v4 = CHardwareManager::Instance();
  CHardwareManager::UnregisterConnectedStandByExitNotification(v4);
  if ( pti )
  {
    SetThreadpoolTimer(pti, 0, 0, 0);
    CloseThreadpoolTimer(pti);
  }
  v5 = CHardwareManager::Instance();
  PostQueuedCompletionStatus(*((HANDLE *)v5 + 6), 0, 0, 0);
  v6 = (CThread *)*((_QWORD *)CHardwareManager::Instance() + 7);
  if ( v6 && !CThread::WaitForExit(v6, 0x4E20u) )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x24F,
      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\server\\hardwaremanager.cpp",
      v7);
  if ( (unsigned __int64)(*((_QWORD *)CHardwareManager::Instance() + 16) - 1LL) <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    v9 = CHardwareManager::Instance();
    v12 = BioTrustlet::WaitForTrustletStopped((struct CHardwareManager *)((char *)v9 + 88), v10, v11);
    if ( v12 < 0 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x255,
        (unsigned int)"onecore\\ds\\security\\biometrics\\service\\server\\hardwaremanager.cpp",
        (const char *)(unsigned int)v12,
        v27);
      v13 = CHardwareManager::Instance();
      v14 = BioTrustlet::Terminate((struct CHardwareManager *)((char *)v13 + 88));
      if ( v14 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x257,
          (unsigned int)"onecore\\ds\\security\\biometrics\\service\\server\\hardwaremanager.cpp",
          (const char *)(unsigned int)v14,
          v27);
      v15 = CHardwareManager::Instance();
      v18 = BioTrustlet::WaitForTrustletStopped((struct CHardwareManager *)((char *)v15 + 88), v16, v17);
      if ( v18 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x25A,
          (unsigned int)"onecore\\ds\\security\\biometrics\\service\\server\\hardwaremanager.cpp",
          (const char *)(unsigned int)v18,
          v27);
    }
  }
  v19 = CHardwareManager::Instance();
  CloseHandle(*((HANDLE *)v19 + 6));
  v27 = 0;
  std::list<std::shared_ptr<CFingerprintPrivateSensorPool>>::_Alloc_sentinel_and_proxy(&v27);
  v20 = (RTL_SRWLOCK *)((char *)CHardwareManager::Instance() + 8);
  AcquireSRWLockExclusive(v20);
  v21 = (__int128 *)((char *)CHardwareManager::Instance() + 24);
  if ( &v27 != v21 )
    std::list<std::shared_ptr<CBiometricUnit>>::_Assign_unchecked<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::shared_ptr<CBiometricUnit>>>,std::_Iterator_base0>,std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::shared_ptr<CBiometricUnit>>>,std::_Iterator_base0>>(
      &v27,
      **(_QWORD **)v21,
      *(_QWORD *)v21);
  v22 = CHardwareManager::Instance();
  std::list<std::shared_ptr<CBiometricUnit>>::clear((char *)v22 + 24);
  v23 = (_QWORD *)((char *)CHardwareManager::Instance() + 72);
  v24 = (_QWORD *)*v23;
  std::_Tree_val<std::_Tree_simple_types<std::pair<void * const,std::shared_ptr<CHardwareChangeSubscription>>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<void * const,std::shared_ptr<CHardwareChangeSubscription>>,void *>>>(
    v23,
    v23,
    *(_QWORD *)(*v23 + 8LL));
  v24[1] = v24;
  *v24 = v24;
  v24[2] = v24;
  v23[1] = 0;
  if ( v20 )
    ReleaseSRWLockExclusive(v20);
  std::_List_node<std::shared_ptr<CBiometricUnit>,void *>::_Free_non_head<std::allocator<std::_List_node<std::shared_ptr<CBiometricUnit>,void *>>>(
    v25,
    v27);
  *(_QWORD *)v27 = v27;
  *(_QWORD *)(v27 + 8) = v27;
  *((_QWORD *)&v27 + 1) = 0;
  std::_List_node<std::shared_ptr<CBiometricUnit>,void *>::_Free_non_head<std::allocator<std::_List_node<std::shared_ptr<CBiometricUnit>,void *>>>(
    v26,
    v27);
  std::_Deallocate<16>((void *)v27, 0x20u);
}

```

## disassembly

```asm
0x18005262c  push    rbp
0x18005262e  push    rbx
0x18005262f  push    rsi
0x180052630  push    rdi
0x180052631  mov     rbp, rsp
0x180052634  sub     rsp, 48h
0x180052638  call    ?Instance@CHardwareManager@@SAAEAV1@XZ; CHardwareManager::Instance(void)
0x18005263d  mov     rcx, [rax+80h]
0x180052644  dec     rcx
0x180052647  lea     rbx, aOnecoreDsSecur_25; "onecore\\ds\\security\\biometrics\\serv"...
0x18005264e  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x180052652  ja      short loc_18005269D
0x180052654  movups  xmm0, cs:xmmword_1800DF158
0x18005265b  movdqu  xmmword ptr [rbp+var_18.Data1], xmm0
0x180052660  lea     rcx, [rbp+var_18]; struct _GUID
0x180052664  call    ?StorageManagerExport@@YAJU_GUID@@@Z; StorageManagerExport(_GUID)
0x180052669  mov     rcx, [rbp+20h]; this
0x18005266d  test    eax, eax
0x18005266f  jns     short loc_180052681
0x180052671  mov     r9d, eax; char *
0x180052674  mov     r8, rbx; unsigned int
0x180052677  mov     edx, 232h; void *
0x18005267c  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180052681  call    ?Instance@CHardwareManager@@SAAEAV1@XZ; CHardwareManager::Instance(void)
0x180052686  lea     rcx, [rax+58h]; this
0x18005268a  call    ?Stop@BioTrustlet@@QEAAJXZ; BioTrustlet::Stop(void)
0x18005268f  call    ?Instance@CHardwareManager@@SAAEAV1@XZ; CHardwareManager::Instance(void)
0x180052694  lea     rcx, [rax+58h]; this
0x180052698  call    ?ServerUnbind@BioTrustlet@@QEAAJXZ; BioTrustlet::ServerUnbind(void)
0x18005269d  call    ?Instance@CHardwareManager@@SAAEAV1@XZ; CHardwareManager::Instance(void)
0x1800526a2  lea     rcx, [rax+38h]; this
0x1800526a6  call    ?Stop@handle_thread@@QEAAXXZ; handle_thread::Stop(void)
0x1800526ab  call    ?Instance@CHardwareManager@@SAAEAV1@XZ; CHardwareManager::Instance(void)
0x1800526b0  mov     rcx, rax; this
0x1800526b3  call    ?UnregisterConnectedStandByExitNotification@CHardwareManager@@AEAAXXZ; CHardwareManager::UnregisterConnectedStandByExitNotification(void)
0x1800526b8  mov     rcx, cs:pti; pti
0x1800526bf  test    rcx, rcx
0x1800526c2  jz      short loc_1800526DF
0x1800526c4  xor     r9d, r9d; msWindowLength
0x1800526c7  xor     r8d, r8d; msPeriod
0x1800526ca  xor     edx, edx; pftDueTime
0x1800526cc  call    cs:__imp_SetThreadpoolTimer
0x1800526d2  mov     rcx, cs:pti; pti
0x1800526d9  call    cs:__imp_CloseThreadpoolTimer
0x1800526df  call    ?Instance@CHardwareManager@@SAAEAV1@XZ; CHardwareManager::Instance(void)
0x1800526e4  xor     r9d, r9d; lpOverlapped
0x1800526e7  xor     r8d, r8d; dwCompletionKey
0x1800526ea  xor     edx, edx; dwNumberOfBytesTransferred
0x1800526ec  mov     rcx, [rax+30h]; CompletionPort
0x1800526f0  call    cs:__imp_PostQueuedCompletionStatus
0x1800526f6  call    ?Instance@CHardwareManager@@SAAEAV1@XZ; CHardwareManager::Instance(void)
0x1800526fb  mov     rcx, [rax+38h]; this
0x1800526ff  test    rcx, rcx
0x180052702  jz      short loc_180052716
0x180052704  mov     edx, 4E20h; unsigned int
0x180052709  call    ?WaitForExit@CThread@@AEBAEK@Z; CThread::WaitForExit(ulong)
0x18005270e  test    al, al
0x180052710  jnz     short loc_180052716
0x180052712  mov     al, 1
0x180052714  jmp     short loc_180052718
0x180052716  xor     al, al
0x180052718  mov     rcx, [rbp+20h]; this
0x18005271c  test    al, al
0x18005271e  jz      short loc_18005272E
0x180052720  mov     r8, rbx; unsigned int
0x180052723  mov     edx, 24Fh; void *
0x180052728  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18005272e  call    ?Instance@CHardwareManager@@SAAEAV1@XZ; CHardwareManager::Instance(void)
0x180052733  mov     rcx, [rax+80h]
0x18005273a  dec     rcx
0x18005273d  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x180052741  ja      short loc_1800527B5
0x180052743  call    ?Instance@CHardwareManager@@SAAEAV1@XZ; CHardwareManager::Instance(void)
0x180052748  lea     rcx, [rax+58h]; this
0x18005274c  call    ?WaitForTrustletStopped@BioTrustlet@@QEAAJKPEAJ@Z; BioTrustlet::WaitForTrustletStopped(ulong,long *)
0x180052751  mov     rcx, [rbp+20h]; this
0x180052755  test    eax, eax
0x180052757  jns     short loc_1800527B5
0x180052759  mov     r9d, eax; char *
0x18005275c  mov     r8, rbx; unsigned int
0x18005275f  mov     edx, 255h; void *
0x180052764  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180052769  call    ?Instance@CHardwareManager@@SAAEAV1@XZ; CHardwareManager::Instance(void)
0x18005276e  lea     rcx, [rax+58h]; this
0x180052772  call    ?Terminate@BioTrustlet@@QEAAJXZ; BioTrustlet::Terminate(void)
0x180052777  mov     rcx, [rbp+20h]; this
0x18005277b  test    eax, eax
0x18005277d  jns     short loc_18005278F
0x18005277f  mov     r9d, eax; char *
0x180052782  mov     r8, rbx; unsigned int
0x180052785  mov     edx, 257h; void *
0x18005278a  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18005278f  call    ?Instance@CHardwareManager@@SAAEAV1@XZ; CHardwareManager::Instance(void)
0x180052794  lea     rcx, [rax+58h]; this
0x180052798  call    ?WaitForTrustletStopped@BioTrustlet@@QEAAJKPEAJ@Z; BioTrustlet::WaitForTrustletStopped(ulong,long *)
0x18005279d  mov     rcx, [rbp+20h]; this
0x1800527a1  test    eax, eax
0x1800527a3  jns     short loc_1800527B5
0x1800527a5  mov     r9d, eax; char *
0x1800527a8  mov     r8, rbx; unsigned int
0x1800527ab  mov     edx, 25Ah; void *
0x1800527b0  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800527b5  call    ?Instance@CHardwareManager@@SAAEAV1@XZ; CHardwareManager::Instance(void)
0x1800527ba  mov     rcx, [rax+30h]; hObject
0x1800527be  call    cs:__imp_CloseHandle
0x1800527c4  xorps   xmm0, xmm0
0x1800527c7  movdqu  [rbp+var_28], xmm0
0x1800527cc  lea     rcx, [rbp+var_28]
0x1800527d0  call    ?_Alloc_sentinel_and_proxy@?$list@V?$shared_ptr@VCFingerprintPrivateSensorPool@@@std@@V?$allocator@V?$shared_ptr@VCFingerprintPrivateSensorPool@@@std@@@2@@std@@AEAAXXZ; std::list<std::shared_ptr<CFingerprintPrivateSensorPool>>::_Alloc_sentinel_and_proxy(void)
0x1800527d5  nop
0x1800527d6  call    ?Instance@CHardwareManager@@SAAEAV1@XZ; CHardwareManager::Instance(void)
0x1800527db  lea     rsi, [rax+8]
0x1800527df  mov     rcx, rsi; SRWLock
0x1800527e2  call    cs:__imp_AcquireSRWLockExclusive
0x1800527e8  mov     [rbp+arg_0], rsi
0x1800527ec  call    ?Instance@CHardwareManager@@SAAEAV1@XZ; CHardwareManager::Instance(void)
0x1800527f1  lea     rdx, [rax+18h]
0x1800527f5  lea     rax, [rbp+var_28]
0x1800527f9  cmp     rax, rdx
0x1800527fc  jz      short loc_180052810
0x1800527fe  mov     rdx, [rdx]
0x180052801  mov     r8, rdx
0x180052804  mov     rdx, [rdx]
0x180052807  lea     rcx, [rbp+var_28]
0x18005280b  call    ??$_Assign_unchecked@V?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@V?$shared_ptr@VCBiometricUnit@@@std@@@std@@@std@@U_Iterator_base0@2@@std@@V12@@?$list@V?$shared_ptr@VCBiometricUnit@@@std@@V?$allocator@V?$shared_ptr@VCBiometricUnit@@@std@@@2@@std@@AEAAXV?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@V?$shared_ptr@VCBiometricUnit@@@std@@@std@@@std@@U_Iterator_base0@2@@1@V21@@Z; std::list<std::shared_ptr<CBiometricUnit>>::_Assign_unchecked<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::shared_ptr<CBiometricUnit>>>,std::_Iterator_base0>,std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::shared_ptr<CBiometricUnit>>>,std::_Iterator_base0>>(std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::shared_ptr<CBiometricUnit>>>,std::_Iterator_base0>,std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::shared_ptr<CBiometricUnit>>>,std::_Iterator_base0>)
0x180052810  call    ?Instance@CHardwareManager@@SAAEAV1@XZ; CHardwareManager::Instance(void)
0x180052815  lea     rcx, [rax+18h]
0x180052819  call    ?clear@?$list@V?$shared_ptr@VCBiometricUnit@@@std@@V?$allocator@V?$shared_ptr@VCBiometricUnit@@@std@@@2@@std@@QEAAXXZ; std::list<std::shared_ptr<CBiometricUnit>>::clear(void)
0x18005281e  call    ?Instance@CHardwareManager@@SAAEAV1@XZ; CHardwareManager::Instance(void)
0x180052823  lea     rdi, [rax+48h]
0x180052827  mov     rbx, [rdi]
0x18005282a  mov     r8, [rbx+8]
0x18005282e  mov     rdx, rdi
0x180052831  mov     rcx, rdi
0x180052834  call    ??$_Erase_tree@V?$allocator@U?$_Tree_node@U?$pair@QEAXV?$shared_ptr@VCHardwareChangeSubscription@@@std@@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@QEAXV?$shared_ptr@VCHardwareChangeSubscription@@@std@@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@QEAXV?$shared_ptr@VCHardwareChangeSubscription@@@std@@@std@@PEAX@std@@@1@PEAU?$_Tree_node@U?$pair@QEAXV?$shared_ptr@VCHardwareChangeSubscription@@@std@@@std@@PEAX@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<void * const,std::shared_ptr<CHardwareChangeSubscription>>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<void * const,std::shared_ptr<CHardwareChangeSubscription>>,void *>>>(std::allocator<std::_Tree_node<std::pair<void * const,std::shared_ptr<CHardwareChangeSubscription>>,void *>> &,std::_Tree_node<std::pair<void * const,std::shared_ptr<CHardwareChangeSubscription>>,void *> *)
0x180052839  mov     [rbx+8], rbx
0x18005283d  mov     [rbx], rbx
0x180052840  mov     [rbx+10h], rbx
0x180052844  mov     qword ptr [rdi+8], 0
0x18005284c  test    rsi, rsi
0x18005284f  jz      short loc_18005285A
0x180052851  mov     rcx, rsi; SRWLock
0x180052854  call    cs:__imp_ReleaseSRWLockExclusive
0x18005285a  mov     rdx, qword ptr [rbp+var_28]
0x18005285e  call    ??$_Free_non_head@V?$allocator@U?$_List_node@V?$shared_ptr@VCBiometricUnit@@@std@@PEAX@std@@@std@@@?$_List_node@V?$shared_ptr@VCBiometricUnit@@@std@@PEAX@std@@SAXAEAV?$allocator@U?$_List_node@V?$shared_ptr@VCBiometricUnit@@@std@@PEAX@std@@@1@PEAU01@@Z; std::_List_node<std::shared_ptr<CBiometricUnit>,void *>::_Free_non_head<std::allocator<std::_List_node<std::shared_ptr<CBiometricUnit>,void *>>>(std::allocator<std::_List_node<std::shared_ptr<CBiometricUnit>,void *>> &,std::_List_node<std::shared_ptr<CBiometricUnit>,void *> *)
0x180052863  mov     rax, qword ptr [rbp+var_28]
0x180052867  mov     [rax], rax
0x18005286a  mov     rax, qword ptr [rbp+var_28]
0x18005286e  mov     [rax+8], rax
0x180052872  mov     qword ptr [rbp+var_28+8], 0
0x18005287a  mov     rdx, qword ptr [rbp+var_28]
0x18005287e  call    ??$_Free_non_head@V?$allocator@U?$_List_node@V?$shared_ptr@VCBiometricUnit@@@std@@PEAX@std@@@std@@@?$_List_node@V?$shared_ptr@VCBiometricUnit@@@std@@PEAX@std@@SAXAEAV?$allocator@U?$_List_node@V?$shared_ptr@VCBiometricUnit@@@std@@PEAX@std@@@1@PEAU01@@Z; std::_List_node<std::shared_ptr<CBiometricUnit>,void *>::_Free_non_head<std::allocator<std::_List_node<std::shared_ptr<CBiometricUnit>,void *>>>(std::allocator<std::_List_node<std::shared_ptr<CBiometricUnit>,void *>> &,std::_List_node<std::shared_ptr<CBiometricUnit>,void *> *)
0x180052883  mov     edx, 20h ; ' '
0x180052888  mov     rcx, qword ptr [rbp+var_28]
0x18005288c  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180052891  add     rsp, 48h
0x180052895  pop     rdi
0x180052896  pop     rsi
0x180052897  pop     rbx
0x180052898  pop     rbp
0x180052899  retn
```
