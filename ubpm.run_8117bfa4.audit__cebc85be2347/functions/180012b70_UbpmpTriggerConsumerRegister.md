# UbpmpTriggerConsumerRegister

- ea: `0x180012b70`
- end: `0x1800136aa`
- name: `UbpmpTriggerConsumerRegister`
- size: `2874`
- prototype: `__int64 __fastcall(struct _UBPM_TRIGGER_CONSUMER_PARAMS_1 *)`
- caller_count: `2`
- callee_count: `24`
- tags: `loader_planting, installer_update`

## callers

- `0x1800136b0`
- `0x1800158e0`

## callees

- `0x1800017a4`
- `0x180001824`
- `0x18000eb68`
- `0x18000ec90`
- `0x18000fbf0`
- `0x180012b70`
- `0x1800136b0`
- `0x1800150c0`
- `0x180015b90`
- `0x180016e70`
- `0x1800192f0`
- `0x18001af64`
- `0x18001c2e8`
- `0x180020a80`
- `0x18002702c`
- `0x180028ed4`
- `0x18002c05c`
- `0x18002ecf8`
- `0x180032f78`
- `0x180035184`
- `0x180036c60`
- `0x180037508`
- `0x180037708`
- `0x1800377e4`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180012c29`
- `msvcrt!_wcsicmp` at `0x1800131b9`
- `msvcrt!_wcsicmp` at `0x180012c29`
- `msvcrt!_wcsicmp` at `0x1800131b9`
- `ntdll!RtlFreeHeap` at `0x180012d8c`
- `ntdll!RtlFreeHeap` at `0x180012eea`
- `ntdll!RtlFreeHeap` at `0x180012d8c`
- `ntdll!RtlFreeHeap` at `0x180012eea`
- `ntdll!RtlReleaseSRWLockShared` at `0x180012cba`
- `ntdll!RtlReleaseSRWLockShared` at `0x180012cba`
- `ntdll!RtlAcquireSRWLockShared` at `0x180012bf2`
- `ntdll!RtlAcquireSRWLockShared` at `0x180012bf2`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180012f0f`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180012f0f`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180012e87`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180013068`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180012e87`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180013068`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180012bb9`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180012bca`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180012c8c`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180012bb9`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180012bca`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180012c8c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180012f1b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180012f1b`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolCleanupGroup` at `0x1800130a2`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolCleanupGroup` at `0x1800130a2`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroup` at `0x180013664`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroup` at `0x180013664`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013211`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800132b7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013406`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013211`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800132b7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013406`
- `RPCRT4!UuidEqual` at `0x180012c48`
- `RPCRT4!UuidEqual` at `0x1800131e0`
- `RPCRT4!UuidEqual` at `0x180012c48`
- `RPCRT4!UuidEqual` at `0x1800131e0`

## pseudocode

```c
__int64 __fastcall UbpmpTriggerConsumerRegister(
        struct _UBPM_TRIGGER_CONSUMER_PARAMS_1 *a1,
        char a2,
        struct _UBPM_TRIGGER_CONSUMER_BLOCK **a3)
{
  DWORD v3; // esi
  char v4; // r15
  _QWORD *Value; // rbx
  _UNKNOWN **i; // rbx
  __int64 *v10; // rax
  __int64 v11; // r8
  __int64 v13; // r8
  unsigned int v14; // ebp
  struct _UBPM_TRIGGER_CONSUMER_BLOCK *v16; // rsi
  struct _TP_CLEANUP_GROUP *ThreadpoolCleanupGroup; // r13
  struct _UBPM_TRIGGER_CONSUMER_PARAMS_1 *v18; // rbx
  struct _UBPM_TRIGGER_CONSUMER_PARAMS_1 *v19; // rax
  struct _UBPM_TRIGGER_CONSUMER_PARAMS_1 *v20; // r12
  __int64 v21; // rdx
  unsigned __int16 v22; // bx
  unsigned __int16 v23; // bx
  __int64 v24; // rcx
  unsigned int v25; // eax
  _QWORD *v26; // rcx
  signed __int32 v27; // eax
  __int64 v28; // r9
  int v29; // eax
  int v30; // eax
  DWORD LastError; // eax
  struct _UBPM_TRIGGER_CONSUMER_BLOCK *v32; // rax
  int v33; // eax
  PTP_POOL v34; // rax
  unsigned int v35; // eax
  unsigned int v36; // eax
  _UNKNOWN **j; // rbx
  void *v38; // rax
  _QWORD *v39; // rcx
  __int64 v40; // r9
  int v41; // edx
  __int64 v42; // rcx
  void *v43; // r9
  wchar_t *v44; // rcx
  unsigned int v45; // eax
  _QWORD *v46; // rcx
  __int64 v47; // rdx
  __int64 v48; // r9
  int v49; // r8d
  PVOID *v50; // r10
  wchar_t *v51; // rcx
  __int64 v52; // rdx
  __int64 v53; // r8
  __int64 v54; // r9
  __int64 v55; // rdx
  __int64 v56; // r8
  __int64 v57; // r9
  __int64 v58; // rdx
  __int64 v59; // r8
  __int64 v60; // r9
  int v61; // [rsp+40h] [rbp-78h]
  char v62; // [rsp+50h] [rbp-68h] BYREF
  char v63; // [rsp+51h] [rbp-67h]
  RPC_STATUS Status; // [rsp+54h] [rbp-64h] BYREF
  RPC_STATUS v65; // [rsp+58h] [rbp-60h] BYREF
  __int64 v66; // [rsp+60h] [rbp-58h] BYREF
  struct _UBPM_TRIGGER_CONSUMER_PARAMS_1 *v67; // [rsp+68h] [rbp-50h]
  char v70; // [rsp+D8h] [rbp+20h] BYREF

  v3 = UbpmpLockTrackerId;
  v4 = 0;
  v70 = 0;
  v62 = 0;
  v66 = 0;
  v65 = 0;
  Status = 0;
  if ( UbpmpLockTrackerId != -1 )
  {
    Value = TlsGetValue(UbpmpLockTrackerId);
    if ( (*(_QWORD *)TlsGetValue(v3) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
      __int2c();
    *Value |= 2uLL;
    ++Value[2];
  }
  RtlAcquireSRWLockShared(&g_ConsumerListLock);
  for ( i = (_UNKNOWN **)g_leConsumerListHead; i != &g_leConsumerListHead; i = (_UNKNOWN **)*i )
  {
    if ( !_wcsicmp(*((const wchar_t **)i[2] + 1), *((const wchar_t **)a1 + 1)) )
    {
      v4 = 1;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_S(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          10,
          WPP_d9ec29665f893a54f0af621b09fac3ba_Traceguids,
          *((_QWORD *)a1 + 1));
      break;
    }
    if ( UuidEqual(*(UUID **)i[2], *(UUID **)a1, &Status) )
    {
      v4 = 1;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_S(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          11,
          WPP_d9ec29665f893a54f0af621b09fac3ba_Traceguids,
          *((_QWORD *)a1 + 1));
      break;
    }
  }
  if ( UbpmpLockTrackerId != -1 )
  {
    v10 = (__int64 *)TlsGetValue(UbpmpLockTrackerId);
    v11 = *v10;
    if ( (*v10 & 2) == 0 )
      __int2c();
    if ( v10[2]-- == 1 )
      *v10 = v11 & 0xFFFFFFFFFFFFFFFDuLL;
  }
  RtlReleaseSRWLockShared(&g_ConsumerListLock);
  v70 = v4;
  if ( !v4 )
  {
    v16 = 0;
    Status = 0;
    v63 = 0;
    ThreadpoolCleanupGroup = 0;
    v18 = 0;
    v14 = UbpmpCopyRegistrationParams(0, 0, (unsigned int *)&Status, a1);
    if ( v14 == 122 )
    {
      v19 = (struct _UBPM_TRIGGER_CONSUMER_PARAMS_1 *)UbpmAlloc((unsigned int)Status);
      v18 = v19;
      if ( !v19 )
      {
        v14 = 14;
LABEL_28:
        v20 = 0;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_Sd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            10,
            (unsigned int)WPP_dd0be36be19438d0c9cf63f3ad92ceae_Traceguids,
            *((_QWORD *)a1 + 1),
            v14);
        goto LABEL_51;
      }
      v14 = UbpmpCopyRegistrationParams(v19, Status, (unsigned int *)&Status, a1);
    }
    if ( v14 )
    {
      if ( v18 )
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v18);
      goto LABEL_28;
    }
    LastError = UbpmpValidateConsumerParameters(v18, &v66, &v62, &v70);
    v14 = LastError;
    if ( LastError )
    {
      v39 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_104;
      v40 = *((_QWORD *)a1 + 1);
      v41 = 11;
    }
    else
    {
      ThreadpoolCleanupGroup = CreateThreadpoolCleanupGroup();
      if ( ThreadpoolCleanupGroup )
      {
        v32 = (struct _UBPM_TRIGGER_CONSUMER_BLOCK *)UbpmAlloc(0x168u);
        v16 = v32;
        if ( v32 )
        {
          UbpmpConsumerInitialize(v32);
          v33 = *((_DWORD *)v18 + 5);
          if ( !v33 || (v38 = UbpmAlloc((unsigned int)(40 * v33)), (*((_QWORD *)v16 + 4) = v38) != 0) )
          {
            *((_QWORD *)v16 + 3) = v18;
            v20 = 0;
            *((_QWORD *)v16 + 41) = v66;
            *((_DWORD *)v18 + 4) |= 1u;
            *((_QWORD *)v16 + 18) = UbpmUtilsThreadPoolCancelCallback;
            v34 = g_pThreadpool;
            *((_QWORD *)v16 + 17) = ThreadpoolCleanupGroup;
            *((_QWORD *)v16 + 16) = v34;
            v67 = 0;
            v35 = UbpmpExecutionTimeLimitInitialize(v16);
            v14 = v35;
            if ( v35 )
            {
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                WPP_SF_Sd(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  15,
                  (unsigned int)WPP_dd0be36be19438d0c9cf63f3ad92ceae_Traceguids,
                  *(_QWORD *)(*((_QWORD *)v16 + 3) + 8LL),
                  v35);
              goto LABEL_51;
            }
            if ( v66 )
            {
              v42 = *(_QWORD *)(v66 + 8);
              if ( v42 )
                v43 = *(void **)(v42 + 8);
              else
                v43 = 0;
              v44 = *(wchar_t **)(v66 + 64);
              if ( !v44 )
                v44 = *(wchar_t **)(*((_QWORD *)v16 + 3) + 8LL);
              v45 = UbpmHardeningListInsert(
                      v44,
                      *(const WCHAR **)(v66 + 56),
                      *(unsigned int *)(v66 + 72),
                      v43,
                      *(struct _LIST_ENTRY **)(v66 + 40),
                      *(_BYTE *)(v66 + 49),
                      v62);
              v14 = v45;
              if ( v45 )
              {
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                  WPP_SF_Sd(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    16,
                    (unsigned int)WPP_dd0be36be19438d0c9cf63f3ad92ceae_Traceguids,
                    *(_QWORD *)(*((_QWORD *)v16 + 3) + 8LL),
                    v45);
                goto LABEL_51;
              }
              v63 = 1;
            }
            v36 = UbpmpTriggerConsumerSaveRegistrationStats(
                    v16,
                    *((_QWORD *)v16 + 3) + 56LL,
                    *((_QWORD *)v16 + 3) + 60LL,
                    *((_QWORD *)v16 + 3) + 68LL,
                    *((_QWORD *)v16 + 3) + 76LL);
            v14 = v36;
            if ( v36 )
            {
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                WPP_SF_Sd(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  17,
                  (unsigned int)WPP_dd0be36be19438d0c9cf63f3ad92ceae_Traceguids,
                  *(_QWORD *)(*((_QWORD *)v16 + 3) + 8LL),
                  v36);
              goto LABEL_51;
            }
            _InterlockedExchange64(
              (volatile __int64 *)v16 + 8,
              (unsigned int)(*(_DWORD *)(*((_QWORD *)v16 + 3) + 20LL) + 1));
            UbpmpAcquireListLockExclusive();
            if ( g_cTotalConsumers == 10000 )
            {
              ((void (*)(void))UbpmpReleaseListLockExclusive)();
              v14 = 84;
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                WPP_SF_Sdd(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  18,
                  (unsigned int)WPP_dd0be36be19438d0c9cf63f3ad92ceae_Traceguids,
                  *(_QWORD *)(*((_QWORD *)v16 + 3) + 8LL),
                  16,
                  84);
              goto LABEL_51;
            }
            for ( j = (_UNKNOWN **)g_leConsumerListHead; ; j = (_UNKNOWN **)*j )
            {
              if ( j == &g_leConsumerListHead )
                goto LABEL_61;
              if ( !_wcsicmp(*((const wchar_t **)j[2] + 1), *(const wchar_t **)(*((_QWORD *)v16 + 3) + 8LL)) )
                break;
              if ( UuidEqual(*(UUID **)j[2], **((UUID ***)v16 + 3), &v65) )
              {
                v70 = 1;
                v46 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                {
                  v47 = 20;
LABEL_137:
                  WPP_SF_S(
                    v46[2],
                    v47,
                    WPP_dd0be36be19438d0c9cf63f3ad92ceae_Traceguids,
                    *(_QWORD *)(*((_QWORD *)v16 + 3) + 8LL));
LABEL_61:
                  if ( !v70 )
                  {
                    RtlAcquireSRWLockExclusive((char *)v16 + 48);
                    *((_DWORD *)v16 + 14) = GetCurrentThreadId();
                    if ( (*((_BYTE *)a1 + 16) & 1) == 0 )
                    {
                      v25 = UbpmConsumerEnable(v16);
                      v14 = v25;
                      if ( v25 )
                      {
                        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                          WPP_SF_Sd(
                            *((_QWORD *)WPP_GLOBAL_Control + 2),
                            21,
                            (unsigned int)WPP_dd0be36be19438d0c9cf63f3ad92ceae_Traceguids,
                            *(_QWORD *)(*((_QWORD *)v16 + 3) + 8LL),
                            v25);
                        *((_DWORD *)v16 + 14) = 0;
                        RtlReleaseSRWLockExclusive((char *)v16 + 48);
                        ((void (*)(void))UbpmpReleaseListLockExclusive)();
                        goto LABEL_51;
                      }
                    }
                    *(_DWORD *)(*((_QWORD *)v16 + 3) + 16LL) &= ~0x40u;
                    v26 = off_18004F0E8;
                    if ( *off_18004F0E8 != (_UNKNOWN *)&g_leConsumerListHead )
                      __fastfail(3u);
                    ++g_cTotalConsumers;
                    *((_QWORD *)v16 + 1) = &g_leConsumerListHead;
                    *((_QWORD *)v16 + 2) = v26;
                    *v26 = (char *)v16 + 8;
                    off_18004F0E8 = (_UNKNOWN **)((char *)v16 + 8);
                    *((_QWORD *)v16 + 14) = ThreadpoolCleanupGroup;
                    ThreadpoolCleanupGroup = 0;
                    v27 = _InterlockedExchangeAdd((volatile signed __int32 *)&g_dwConsumerTag, 1u);
                    *((_BYTE *)v16 + 41) |= 1u;
                    v21 = *((_QWORD *)v16 + 3);
                    *((_DWORD *)v16 + 11) = v27 + 1;
                    v50 = (PVOID *)WPP_GLOBAL_Control;
                    if ( *(_DWORD *)(v21 + 20) )
                    {
                      while ( 2 )
                      {
                        v28 = *(_QWORD *)(v21 + 24);
                        v29 = *(_DWORD *)(v28 + 48LL * (unsigned __int16)v20);
                        if ( v29 == 1 )
                        {
                          if ( v50 == &WPP_GLOBAL_Control || (*((_BYTE *)v50 + 28) & 4) == 0 )
                            goto LABEL_33;
                          v48 = *(_QWORD *)(v28 + 48LL * (unsigned __int16)v20 + 8);
                          WPP_SF_SddddL(
                            (unsigned int)v50[2],
                            v21,
                            v49,
                            *(_QWORD *)v48,
                            *(_DWORD *)(v48 + 56),
                            *(_DWORD *)(v48 + 12),
                            *(_DWORD *)(v48 + 16),
                            *(_DWORD *)(v48 + 20),
                            *(_DWORD *)(v48 + 8));
                        }
                        else
                        {
                          v30 = v29 - 2;
                          if ( !v30 )
                          {
                            if ( v50 != &WPP_GLOBAL_Control && (*((_BYTE *)v50 + 28) & 4) != 0 )
                            {
                              WPP_SF_dd(
                                v50[2],
                                23,
                                WPP_dd0be36be19438d0c9cf63f3ad92ceae_Traceguids,
                                *(unsigned int *)(*(_QWORD *)(v28 + 48LL * (unsigned __int16)v20 + 8) + 12LL));
                              break;
                            }
LABEL_33:
                            v21 = *((_QWORD *)v16 + 3);
                            if ( *(_DWORD *)(*(_QWORD *)(v21 + 24) + 48LL * (unsigned __int16)v20 + 36) )
                            {
                              v22 = 0;
                              do
                              {
                                if ( v50 != &WPP_GLOBAL_Control && (*((_BYTE *)v50 + 28) & 4) != 0 )
                                {
                                  WPP_SF_S(
                                    v50[2],
                                    25,
                                    WPP_dd0be36be19438d0c9cf63f3ad92ceae_Traceguids,
                                    *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v21 + 24) + 48LL * (unsigned __int16)v20 + 40)
                                              + 8LL * v22));
                                  v50 = (PVOID *)WPP_GLOBAL_Control;
                                }
                                v21 = *((_QWORD *)v16 + 3);
                                ++v22;
                              }
                              while ( (unsigned int)v22 < *(_DWORD *)(*(_QWORD *)(v21 + 24)
                                                                    + 48LL * (unsigned __int16)v20
                                                                    + 36) );
                            }
                            LOWORD(v20) = (_WORD)v20 + 1;
                            if ( (unsigned int)(unsigned __int16)v20 >= *(_DWORD *)(v21 + 20) )
                            {
                              v20 = v67;
                              ThreadpoolCleanupGroup = v67;
                              goto LABEL_41;
                            }
                            continue;
                          }
                          if ( v30 != 1 || v50 == &WPP_GLOBAL_Control || (*((_BYTE *)v50 + 28) & 4) == 0 )
                            goto LABEL_33;
                          WPP_SF_(v50[2], 24, WPP_dd0be36be19438d0c9cf63f3ad92ceae_Traceguids);
                        }
                        break;
                      }
                      v50 = (PVOID *)WPP_GLOBAL_Control;
                      goto LABEL_33;
                    }
LABEL_41:
                    if ( *(_DWORD *)(v21 + 32) )
                    {
                      v23 = 0;
                      do
                      {
                        if ( v50 != &WPP_GLOBAL_Control && (*((_BYTE *)v50 + 28) & 4) != 0 )
                        {
                          WPP_SF_Sd(
                            (unsigned int)v50[2],
                            26,
                            (unsigned int)WPP_dd0be36be19438d0c9cf63f3ad92ceae_Traceguids,
                            *(_QWORD *)(*(_QWORD *)(v21 + 40) + 40LL * v23),
                            *(_DWORD *)(*(_QWORD *)(v21 + 40) + 40LL * v23 + 16));
                          v50 = (PVOID *)WPP_GLOBAL_Control;
                        }
                        v21 = *((_QWORD *)v16 + 3);
                        ++v23;
                      }
                      while ( (unsigned int)v23 < *(_DWORD *)(v21 + 32) );
                    }
                    if ( v50 != &WPP_GLOBAL_Control && (*((_BYTE *)v50 + 28) & 4) != 0 )
                      WPP_SF_SddiLdq(
                        *((_QWORD *)WPP_GLOBAL_Control + 2),
                        *((_QWORD *)v16 + 8),
                        v49,
                        *(_QWORD *)(*((_QWORD *)v16 + 3) + 8LL),
                        *(_DWORD *)(*((_QWORD *)v16 + 3) + 32LL),
                        *(_DWORD *)(*((_QWORD *)v16 + 3) + 20LL),
                        *((_QWORD *)v16 + 8),
                        *(_DWORD *)(v21 + 16),
                        v61,
                        (char)v16);
                    *((_DWORD *)v16 + 14) = 0;
                    RtlReleaseSRWLockExclusive((char *)v16 + 48);
                    UbpmpReleaseListLockExclusive(v24);
                    *a3 = v16;
                    v16 = 0;
LABEL_51:
                    if ( !a2 )
                      UbpmTelemConsumerRegistered(a1, v14);
                    if ( v14 && v63 == 1 )
                    {
                      v51 = *(wchar_t **)(v66 + 64);
                      if ( !v51 )
                        v51 = *(wchar_t **)(*((_QWORD *)v16 + 3) + 8LL);
                      UbpmHardeningListRemove(v51);
                    }
                    if ( ThreadpoolCleanupGroup )
                      CloseThreadpoolCleanupGroup(ThreadpoolCleanupGroup);
                    if ( v16 )
                    {
                      UbpmConsumerDisable(v16);
                      UbpmUtilsFreeTimerContext((void **)v16 + 36, 1u);
                      UBPM_MIDL_user_free(*((_QWORD *)v16 + 4), v52, v53, v54);
                      UBPM_MIDL_user_free(*((_QWORD *)v16 + 3), v55, v56, v57);
                      UBPM_MIDL_user_free(v16, v58, v59, v60);
                    }
                    if ( v20 )
                      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v20);
                    return v14;
                  }
                }
LABEL_106:
                ((void (*)(void))UbpmpReleaseListLockExclusive)();
                v14 = 183;
                goto LABEL_51;
              }
            }
            v70 = 1;
            v46 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              v47 = 19;
              goto LABEL_137;
            }
            goto LABEL_106;
          }
          LastError = GetLastError();
          v14 = LastError;
          v39 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          {
LABEL_104:
            v20 = v18;
            goto LABEL_51;
          }
          v40 = *((_QWORD *)v18 + 1);
          v41 = 14;
        }
        else
        {
          LastError = GetLastError();
          v14 = LastError;
          v39 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
            goto LABEL_104;
          v40 = *((_QWORD *)v18 + 1);
          v41 = 13;
        }
      }
      else
      {
        LastError = GetLastError();
        v14 = LastError;
        v39 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_104;
        v40 = *((_QWORD *)v18 + 1);
        v41 = 12;
      }
    }
    WPP_SF_Sd(v39[2], v41, (unsigned int)WPP_dd0be36be19438d0c9cf63f3ad92ceae_Traceguids, v40, LastError);
    goto LABEL_104;
  }
  v14 = 183;
  if ( a2 != 1 )
    return UbpmpTriggerConsumerUpdate(a1, v4, v13, a3);
  return v14;
}

```

## disassembly

```asm
0x180012b70  mov     rax, rsp
0x180012b73  mov     [rax+18h], r8
0x180012b77  mov     [rax+10h], dl
0x180012b7a  push    rbx
0x180012b7b  push    rbp
0x180012b7c  push    rsi
0x180012b7d  push    rdi
0x180012b7e  push    r12
0x180012b80  push    r13
0x180012b82  push    r15
0x180012b84  sub     rsp, 80h
0x180012b8b  mov     esi, cs:UbpmpLockTrackerId
0x180012b91  xor     ebp, ebp
0x180012b93  xor     r15b, r15b
0x180012b96  mov     byte ptr [rax+20h], 0
0x180012b9a  mov     byte ptr [rax-68h], 0
0x180012b9e  mov     r12, r8
0x180012ba1  mov     [rax-58h], rbp
0x180012ba5  movzx   r13d, dl
0x180012ba9  mov     [rax-60h], ebp
0x180012bac  mov     rdi, rcx
0x180012baf  mov     [rax-64h], ebp
0x180012bb2  cmp     esi, 0FFFFFFFFh
0x180012bb5  jz      short loc_180012BEB
0x180012bb7  mov     ecx, esi; dwTlsIndex
0x180012bb9  call    cs:__imp_TlsGetValue
0x180012bc0  nop     dword ptr [rax+rax+00h]
0x180012bc5  mov     ecx, esi; dwTlsIndex
0x180012bc7  mov     rbx, rax
0x180012bca  call    cs:__imp_TlsGetValue
0x180012bd1  nop     dword ptr [rax+rax+00h]
0x180012bd6  test    qword ptr [rax], 0FFFFFFFFFFFFFFFEh
0x180012bdd  jnz     loc_180012DDE
0x180012be3  or      qword ptr [rbx], 2
0x180012be7  inc     qword ptr [rbx+10h]
0x180012beb  lea     rcx, ?g_ConsumerListLock@@3U_CEM_LOCK@@A; _CEM_LOCK g_ConsumerListLock
0x180012bf2  call    cs:__imp_RtlAcquireSRWLockShared
0x180012bf9  nop     dword ptr [rax+rax+00h]
0x180012bfe  mov     rbx, cs:g_leConsumerListHead
0x180012c05  mov     [rsp+0B8h+arg_0], r14
0x180012c0d  lea     rax, g_leConsumerListHead
0x180012c14  cmp     rbx, rax
0x180012c17  jz      loc_180012D0C
0x180012c1d  mov     rcx, [rbx+10h]
0x180012c21  mov     rdx, [rdi+8]; String2
0x180012c25  mov     rcx, [rcx+8]; String1
0x180012c29  call    cs:__imp__wcsicmp
0x180012c30  nop     dword ptr [rax+rax+00h]
0x180012c35  test    eax, eax
0x180012c37  jz      short loc_180012C61
0x180012c39  mov     rcx, [rbx+10h]
0x180012c3d  lea     r8, [rsp+0B8h+Status]; Status
0x180012c42  mov     rdx, [rdi]; Uuid2
0x180012c45  mov     rcx, [rcx]; Uuid1
0x180012c48  call    cs:__imp_UuidEqual
0x180012c4f  nop     dword ptr [rax+rax+00h]
0x180012c54  test    eax, eax
0x180012c56  jnz     loc_180013384
0x180012c5c  mov     rbx, [rbx]
0x180012c5f  jmp     short loc_180012C0D
0x180012c61  mov     r15b, 1
0x180012c64  mov     rcx, cs:WPP_GLOBAL_Control
0x180012c6b  lea     r14, WPP_GLOBAL_Control
0x180012c72  cmp     rcx, r14
0x180012c75  jz      short loc_180012C81
0x180012c77  test    byte ptr [rcx+1Ch], 2
0x180012c7b  jnz     loc_1800133C6
0x180012c81  mov     ecx, cs:UbpmpLockTrackerId; dwTlsIndex
0x180012c87  cmp     ecx, 0FFFFFFFFh
0x180012c8a  jz      short loc_180012CB3
0x180012c8c  call    cs:__imp_TlsGetValue
0x180012c93  nop     dword ptr [rax+rax+00h]
0x180012c98  mov     r8, [rax]
0x180012c9b  test    r8b, 2
0x180012c9f  jz      loc_180012DD7
0x180012ca5  sub     qword ptr [rax+10h], 1
0x180012caa  jnz     short loc_180012CB3
0x180012cac  and     r8, 0FFFFFFFFFFFFFFFDh
0x180012cb0  mov     [rax], r8
0x180012cb3  lea     rcx, ?g_ConsumerListLock@@3U_CEM_LOCK@@A; _CEM_LOCK g_ConsumerListLock
0x180012cba  call    cs:__imp_RtlReleaseSRWLockShared
0x180012cc1  nop     dword ptr [rax+rax+00h]
0x180012cc6  mov     [rsp+0B8h+arg_18], r15b
0x180012cce  test    r15b, r15b
0x180012cd1  jz      short loc_180012D18
0x180012cd3  mov     ebp, 0B7h
0x180012cd8  cmp     r13b, 1
0x180012cdc  jz      loc_180012EF6
0x180012ce2  mov     r9, r12
0x180012ce5  movzx   edx, r15b
0x180012ce9  mov     rcx, rdi; struct _UBPM_TRIGGER_CONSUMER_PARAMS_1 *
0x180012cec  call    UbpmpTriggerConsumerUpdate
0x180012cf1  mov     r14, [rsp+0B8h+arg_0]
0x180012cf9  add     rsp, 80h
0x180012d00  pop     r15
0x180012d02  pop     r13
0x180012d04  pop     r12
0x180012d06  pop     rdi
0x180012d07  pop     rsi
0x180012d08  pop     rbp
0x180012d09  pop     rbx
0x180012d0a  retn
0x180012d0c  lea     r14, WPP_GLOBAL_Control
0x180012d13  jmp     loc_180012C81
0x180012d18  mov     rsi, rbp
0x180012d1b  mov     [rsp+0B8h+Status], ebp
0x180012d1f  mov     r9, rdi; struct _UBPM_TRIGGER_CONSUMER_PARAMS_1 *
0x180012d22  mov     [rsp+0B8h+var_67], sil
0x180012d27  lea     r8, [rsp+0B8h+Status]; unsigned int *
0x180012d2c  xor     edx, edx; unsigned int
0x180012d2e  xor     ecx, ecx; struct _UBPM_TRIGGER_CONSUMER_PARAMS_1 *
0x180012d30  mov     r13, rbp
0x180012d33  mov     rbx, rbp
0x180012d36  call    ?UbpmpCopyRegistrationParams@@YAKPEAU_UBPM_TRIGGER_CONSUMER_PARAMS_1@@KPEAK0@Z; UbpmpCopyRegistrationParams(_UBPM_TRIGGER_CONSUMER_PARAMS_1 *,ulong,ulong *,_UBPM_TRIGGER_CONSUMER_PARAMS_1 *)
0x180012d3b  mov     ebp, eax
0x180012d3d  cmp     eax, 7Ah ; 'z'
0x180012d40  jnz     short loc_180012D6D
0x180012d42  mov     ecx, [rsp+0B8h+Status]; Size
0x180012d46  call    ?UbpmAlloc@@YAPEAXK@Z; UbpmAlloc(ulong)
0x180012d4b  mov     rbx, rax
0x180012d4e  test    rax, rax
0x180012d51  jz      loc_1800133E4
0x180012d57  mov     edx, [rsp+0B8h+Status]; unsigned int
0x180012d5b  lea     r8, [rsp+0B8h+Status]; unsigned int *
0x180012d60  mov     r9, rdi; struct _UBPM_TRIGGER_CONSUMER_PARAMS_1 *
0x180012d63  mov     rcx, rax; struct _UBPM_TRIGGER_CONSUMER_PARAMS_1 *
0x180012d66  call    ?UbpmpCopyRegistrationParams@@YAKPEAU_UBPM_TRIGGER_CONSUMER_PARAMS_1@@KPEAK0@Z; UbpmpCopyRegistrationParams(_UBPM_TRIGGER_CONSUMER_PARAMS_1 *,ulong,ulong *,_UBPM_TRIGGER_CONSUMER_PARAMS_1 *)
0x180012d6b  mov     ebp, eax
0x180012d6d  test    ebp, ebp
0x180012d6f  jz      loc_18001307E
0x180012d75  test    rbx, rbx
0x180012d78  jz      short loc_180012D98
0x180012d7a  mov     rcx, gs:60h
0x180012d83  mov     r8, rbx; P
0x180012d86  xor     edx, edx; Flags
0x180012d88  mov     rcx, [rcx+30h]; HeapHandle
0x180012d8c  call    cs:__imp_RtlFreeHeap
0x180012d93  nop     dword ptr [rax+rax+00h]
0x180012d98  xor     r12d, r12d
0x180012d9b  mov     rcx, cs:WPP_GLOBAL_Control
0x180012da2  cmp     rcx, r14
0x180012da5  jz      loc_180012EA5
0x180012dab  test    byte ptr [rcx+1Ch], 1
0x180012daf  jz      loc_180012EA5
0x180012db5  mov     r9, [rdi+8]
0x180012db9  mov     edx, 0Ah
0x180012dbe  mov     dword ptr [rsp+0B8h+var_98], ebp
0x180012dc2  mov     rcx, [rcx+10h]
0x180012dc6  lea     r8, WPP_dd0be36be19438d0c9cf63f3ad92ceae_Traceguids
0x180012dcd  call    WPP_SF_Sd
0x180012dd2  jmp     loc_180012EA5
0x180012dd7  int     2Ch; Windows NT - assertion failure
0x180012dd9  jmp     loc_180012CA5
0x180012dde  int     2Ch; Windows NT - assertion failure
0x180012de0  jmp     loc_180012BE3
0x180012de5  cmp     r10, r14
0x180012de8  jz      short loc_180012DF5
0x180012dea  test    byte ptr [r10+1Ch], 4
0x180012def  jnz     loc_18001354A
0x180012df5  mov     rdx, [rsi+18h]
0x180012df9  mov     rax, [rdx+18h]
0x180012dfd  cmp     dword ptr [rax+r13*8+24h], 0
0x180012e03  jbe     short loc_180012E2C
0x180012e05  xor     ebx, ebx
0x180012e07  cmp     r10, r14
0x180012e0a  jz      short loc_180012E17
0x180012e0c  test    byte ptr [r10+1Ch], 4
0x180012e11  jnz     loc_180013588
0x180012e17  mov     rdx, [rsi+18h]
0x180012e1b  inc     bx
0x180012e1e  movzx   eax, bx
0x180012e21  mov     rcx, [rdx+18h]
0x180012e25  cmp     eax, [rcx+r13*8+24h]
0x180012e2a  jb      short loc_180012E07
0x180012e2c  inc     r12w
0x180012e30  movzx   eax, r12w
0x180012e34  cmp     eax, [rdx+14h]
0x180012e37  jb      loc_180012FAE
0x180012e3d  mov     r12, [rsp+0B8h+var_50]
0x180012e42  mov     r13, r12
0x180012e45  cmp     dword ptr [rdx+20h], 0
0x180012e49  jbe     short loc_180012E6C
0x180012e4b  xor     ebx, ebx
0x180012e4d  cmp     r10, r14
0x180012e50  jz      short loc_180012E5D
0x180012e52  test    byte ptr [r10+1Ch], 4
0x180012e57  jnz     loc_1800135B9
0x180012e5d  mov     rdx, [rsi+18h]
0x180012e61  inc     bx
0x180012e64  movzx   eax, bx
0x180012e67  cmp     eax, [rdx+20h]
0x180012e6a  jb      short loc_180012E4D
0x180012e6c  cmp     r10, r14
0x180012e6f  jz      short loc_180012E7C
0x180012e71  test    byte ptr [r10+1Ch], 4
0x180012e76  jnz     loc_1800135F4
0x180012e7c  lea     rcx, [rsi+30h]
0x180012e80  mov     dword ptr [rsi+38h], 0
0x180012e87  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180012e8e  nop     dword ptr [rax+rax+00h]
0x180012e93  call    UbpmpReleaseListLockExclusive
0x180012e98  mov     rax, [rsp+0B8h+arg_10]
0x180012ea0  mov     [rax], rsi
0x180012ea3  xor     esi, esi
0x180012ea5  cmp     [rsp+0B8h+arg_8], 0
0x180012ead  jnz     short loc_180012EB9
0x180012eaf  mov     edx, ebp
0x180012eb1  mov     rcx, rdi
0x180012eb4  call    UbpmTelemConsumerRegistered
0x180012eb9  test    ebp, ebp
0x180012ebb  jnz     loc_180013636
0x180012ec1  test    r13, r13
0x180012ec4  jnz     loc_180013661
0x180012eca  test    rsi, rsi
0x180012ecd  jnz     loc_180013675
0x180012ed3  test    r12, r12
0x180012ed6  jz      short loc_180012EF6
0x180012ed8  mov     rcx, gs:60h
0x180012ee1  mov     r8, r12; P
0x180012ee4  xor     edx, edx; Flags
0x180012ee6  mov     rcx, [rcx+30h]; HeapHandle
0x180012eea  call    cs:__imp_RtlFreeHeap
0x180012ef1  nop     dword ptr [rax+rax+00h]
0x180012ef6  mov     eax, ebp
0x180012ef8  jmp     loc_180012CF1
0x180012efd  cmp     [rsp+0B8h+arg_18], r12b
0x180012f05  jnz     loc_1800132F5
0x180012f0b  lea     rcx, [rsi+30h]
0x180012f0f  call    cs:__imp_RtlAcquireSRWLockExclusive
0x180012f16  nop     dword ptr [rax+rax+00h]
0x180012f1b  call    cs:__imp_GetCurrentThreadId
0x180012f22  nop     dword ptr [rax+rax+00h]
0x180012f27  mov     [rsi+38h], eax
0x180012f2a  test    byte ptr [rdi+10h], 1
0x180012f2e  jnz     short loc_180012F42
0x180012f30  mov     rcx, rsi; struct _UBPM_TRIGGER_CONSUMER_BLOCK *
0x180012f33  call    UbpmConsumerEnable
0x180012f38  mov     ebp, eax
0x180012f3a  test    eax, eax
0x180012f3c  jnz     loc_180013050
0x180012f42  mov     rax, [rsi+18h]
0x180012f46  lea     rdx, g_leConsumerListHead
0x180012f4d  and     dword ptr [rax+10h], 0FFFFFFBFh
0x180012f51  mov     rcx, cs:off_18004F0E8
0x180012f58  cmp     [rcx], rdx
0x180012f5b  jnz     loc_180013049
0x180012f61  inc     cs:g_cTotalConsumers
0x180012f67  lea     rax, [rsi+8]
0x180012f6b  mov     [rax], rdx
0x180012f6e  mov     [rax+8], rcx
0x180012f72  mov     [rcx], rax
0x180012f75  mov     cs:off_18004F0E8, rax
0x180012f7c  mov     eax, 1
0x180012f81  mov     [rsi+70h], r13
0x180012f85  xor     r13d, r13d
0x180012f88  lock xadd cs:?g_dwConsumerTag@@3KC, eax; ulong volatile g_dwConsumerTag
0x180012f90  or      byte ptr [rsi+29h], 1
0x180012f94  inc     eax
0x180012f96  mov     rdx, [rsi+18h]
0x180012f9a  mov     [rsi+2Ch], eax
0x180012f9d  mov     r10, cs:WPP_GLOBAL_Control
0x180012fa4  cmp     [rdx+14h], r12d
0x180012fa8  jbe     loc_180012E45
0x180012fae  mov     r9, [rdx+18h]
0x180012fb2  movzx   eax, r12w
0x180012fb6  lea     r13, [rax+rax*2]
0x180012fba  add     r13, r13
0x180012fbd  mov     eax, [r9+r13*8]
0x180012fc1  cmp     eax, 1
0x180012fc4  jz      loc_180012DE5
0x180012fca  sub     eax, 2
0x180012fcd  jnz     short loc_180013015
0x180012fcf  cmp     r10, r14
0x180012fd2  jz      loc_180012DF5
0x180012fd8  test    byte ptr [r10+1Ch], 4
0x180012fdd  jz      loc_180012DF5
0x180012fe3  mov     r9, [r9+r13*8+8]
0x180012fe8  lea     r8, WPP_dd0be36be19438d0c9cf63f3ad92ceae_Traceguids
0x180012fef  mov     rcx, [r10+10h]
0x180012ff3  mov     edx, 17h
0x180012ff8  mov     eax, [r9+8]
0x180012ffc  mov     r9d, [r9+0Ch]
0x180013000  mov     dword ptr [rsp+0B8h+var_98], eax
0x180013004  call    WPP_SF_dd
0x180013009  mov     r10, cs:WPP_GLOBAL_Control
0x180013010  jmp     loc_180012DF5
0x180013015  cmp     eax, 1
0x180013018  jnz     loc_180012DF5
0x18001301e  cmp     r10, r14
0x180013021  jz      loc_180012DF5
0x180013027  test    byte ptr [r10+1Ch], 4
0x18001302c  jz      loc_180012DF5
0x180013032  mov     rcx, [r10+10h]
0x180013036  lea     r8, WPP_dd0be36be19438d0c9cf63f3ad92ceae_Traceguids
0x18001303d  mov     edx, 18h
0x180013042  call    WPP_SF_
0x180013047  jmp     short loc_180013009
0x180013049  mov     ecx, 3
0x18001304e  int     29h; Win8: RtlFailFast(ecx)
0x180013050  mov     rcx, cs:WPP_GLOBAL_Control
  ... truncated ...
```
