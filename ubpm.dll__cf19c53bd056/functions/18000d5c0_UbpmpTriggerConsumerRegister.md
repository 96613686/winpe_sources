# UbpmpTriggerConsumerRegister

- ea: `0x18000d5c0`
- end: `0x18000e086`
- name: `UbpmpTriggerConsumerRegister`
- size: `2758`
- prototype: `__int64 __fastcall(struct _UBPM_TRIGGER_CONSUMER_PARAMS_1 *, char, struct _UBPM_TRIGGER_CONSUMER_BLOCK **)`
- caller_count: `2`
- callee_count: `24`
- tags: `loader_planting, installer_update`

## callers

- `0x18000b340`
- `0x18000e090`

## callees

- `0x18000ad3c`
- `0x18000ada4`
- `0x18000d5c0`
- `0x18000e090`
- `0x18000f9a0`
- `0x18000f9f0`
- `0x18001311c`
- `0x1800138e0`
- `0x180014b30`
- `0x1800174d0`
- `0x180018ef0`
- `0x180019d90`
- `0x18001ce00`
- `0x18001e9f4`
- `0x18001fbf8`
- `0x180026fd8`
- `0x180027994`
- `0x18002cc50`
- `0x180030cec`
- `0x180032dd8`
- `0x1800347bc`
- `0x180035000`
- `0x1800351ec`
- `0x1800352c0`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18000d667`
- `msvcrt!_wcsicmp` at `0x18000dbb9`
- `msvcrt!_wcsicmp` at `0x18000d667`
- `msvcrt!_wcsicmp` at `0x18000dbb9`
- `ntdll!RtlFreeHeap` at `0x18000d7b1`
- `ntdll!RtlFreeHeap` at `0x18000d903`
- `ntdll!RtlFreeHeap` at `0x18000d7b1`
- `ntdll!RtlFreeHeap` at `0x18000d903`
- `ntdll!RtlReleaseSRWLockShared` at `0x18000d6e6`
- `ntdll!RtlReleaseSRWLockShared` at `0x18000d6e6`
- `ntdll!RtlAcquireSRWLockShared` at `0x18000d636`
- `ntdll!RtlAcquireSRWLockShared` at `0x18000d636`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18000d922`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18000d922`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000d8a6`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000da6f`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000d8a6`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000da6f`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000d609`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000d614`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000d6be`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000d609`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000d614`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000d6be`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000d928`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000d928`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolCleanupGroup` at `0x18000daa3`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolCleanupGroup` at `0x18000daa3`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroup` at `0x18000e046`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroup` at `0x18000e046`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000dc05`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000dca5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ddee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000dc05`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000dca5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ddee`
- `RPCRT4!UuidEqual` at `0x18000d680`
- `RPCRT4!UuidEqual` at `0x18000dbda`
- `RPCRT4!UuidEqual` at `0x18000d680`
- `RPCRT4!UuidEqual` at `0x18000dbda`

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
  __int64 *v9; // rax
  __int64 v10; // r8
  unsigned int v12; // ebp
  struct _UBPM_TRIGGER_CONSUMER_BLOCK *v14; // rsi
  struct _TP_CLEANUP_GROUP *ThreadpoolCleanupGroup; // r13
  __int64 v16; // rbx
  struct _UBPM_TRIGGER_CONSUMER_PARAMS_1 *v17; // rax
  void *v18; // r12
  __int64 v19; // rdx
  unsigned __int16 v20; // bx
  unsigned __int16 v21; // bx
  unsigned int v22; // eax
  _QWORD *v23; // rcx
  signed __int32 v24; // eax
  __int64 v25; // r9
  int v26; // eax
  int v27; // eax
  __int64 v28; // r9
  unsigned int LastError; // eax
  struct _UBPM_TRIGGER_CONSUMER_BLOCK *v30; // rax
  int v31; // eax
  PTP_POOL v32; // rax
  unsigned int v33; // eax
  unsigned int v34; // eax
  _UNKNOWN **j; // rbx
  void *v36; // rax
  _QWORD *v37; // rcx
  __int64 v38; // r9
  int v39; // edx
  __int64 v40; // rcx
  void *v41; // r9
  wchar_t *v42; // rcx
  unsigned int v43; // eax
  _QWORD *v44; // rcx
  __int64 v45; // rdx
  __int64 v46; // r9
  int v47; // r8d
  PVOID *v48; // r10
  wchar_t *v49; // rcx
  int v50; // [rsp+40h] [rbp-78h]
  char v51; // [rsp+50h] [rbp-68h] BYREF
  char v52; // [rsp+51h] [rbp-67h]
  RPC_STATUS Status; // [rsp+54h] [rbp-64h] BYREF
  RPC_STATUS v54; // [rsp+58h] [rbp-60h] BYREF
  __int64 v55; // [rsp+60h] [rbp-58h] BYREF
  void *v56; // [rsp+68h] [rbp-50h]
  char v59; // [rsp+D8h] [rbp+20h] BYREF

  v3 = UbpmpLockTrackerId;
  v4 = 0;
  v59 = 0;
  v51 = 0;
  v55 = 0;
  v54 = 0;
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
    v9 = (__int64 *)TlsGetValue(UbpmpLockTrackerId);
    v10 = *v9;
    if ( (*v9 & 2) == 0 )
      __int2c();
    if ( v9[2]-- == 1 )
      *v9 = v10 & 0xFFFFFFFFFFFFFFFDuLL;
  }
  RtlReleaseSRWLockShared(&g_ConsumerListLock);
  v59 = v4;
  if ( !v4 )
  {
    v14 = 0;
    Status = 0;
    v52 = 0;
    ThreadpoolCleanupGroup = 0;
    v16 = 0;
    v12 = UbpmpCopyRegistrationParams(0, 0, (unsigned int *)&Status, a1);
    if ( v12 == 122 )
    {
      v17 = (struct _UBPM_TRIGGER_CONSUMER_PARAMS_1 *)UbpmAlloc((unsigned int)Status);
      v16 = (__int64)v17;
      if ( !v17 )
      {
        v12 = 14;
LABEL_28:
        v18 = 0;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_Sd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            10,
            (unsigned int)WPP_dd0be36be19438d0c9cf63f3ad92ceae_Traceguids,
            *((_QWORD *)a1 + 1),
            v12);
        goto LABEL_51;
      }
      v12 = UbpmpCopyRegistrationParams(v17, Status, (unsigned int *)&Status, a1);
    }
    if ( v12 )
    {
      if ( v16 )
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, (PVOID)v16);
      goto LABEL_28;
    }
    LastError = UbpmpValidateConsumerParameters(v16, (__int64)&v55, (__int64)&v51, &v59);
    v12 = LastError;
    if ( LastError )
    {
      v37 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_104;
      v38 = *((_QWORD *)a1 + 1);
      v39 = 11;
    }
    else
    {
      ThreadpoolCleanupGroup = CreateThreadpoolCleanupGroup();
      if ( ThreadpoolCleanupGroup )
      {
        v30 = (struct _UBPM_TRIGGER_CONSUMER_BLOCK *)UbpmAlloc(0x168u);
        v14 = v30;
        if ( v30 )
        {
          UbpmpConsumerInitialize(v30);
          v31 = *(_DWORD *)(v16 + 20);
          if ( !v31 || (v36 = UbpmAlloc((unsigned int)(40 * v31)), (*((_QWORD *)v14 + 4) = v36) != 0) )
          {
            *((_QWORD *)v14 + 3) = v16;
            v18 = 0;
            *((_QWORD *)v14 + 41) = v55;
            *(_DWORD *)(v16 + 16) |= 1u;
            *((_QWORD *)v14 + 18) = UbpmUtilsThreadPoolCancelCallback;
            v32 = g_pThreadpool;
            *((_QWORD *)v14 + 17) = ThreadpoolCleanupGroup;
            *((_QWORD *)v14 + 16) = v32;
            v56 = 0;
            v33 = UbpmpExecutionTimeLimitInitialize(v14);
            v12 = v33;
            if ( v33 )
            {
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                WPP_SF_Sd(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  15,
                  (unsigned int)WPP_dd0be36be19438d0c9cf63f3ad92ceae_Traceguids,
                  *(_QWORD *)(*((_QWORD *)v14 + 3) + 8LL),
                  v33);
              goto LABEL_51;
            }
            if ( v55 )
            {
              v40 = *(_QWORD *)(v55 + 8);
              if ( v40 )
                v41 = *(void **)(v40 + 8);
              else
                v41 = 0;
              v42 = *(wchar_t **)(v55 + 64);
              if ( !v42 )
                v42 = *(wchar_t **)(*((_QWORD *)v14 + 3) + 8LL);
              v43 = UbpmHardeningListInsert(
                      v42,
                      *(const WCHAR **)(v55 + 56),
                      *(_DWORD *)(v55 + 72),
                      v41,
                      *(struct _LIST_ENTRY **)(v55 + 40),
                      *(_BYTE *)(v55 + 49),
                      v51);
              v12 = v43;
              if ( v43 )
              {
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                  WPP_SF_Sd(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    16,
                    (unsigned int)WPP_dd0be36be19438d0c9cf63f3ad92ceae_Traceguids,
                    *(_QWORD *)(*((_QWORD *)v14 + 3) + 8LL),
                    v43);
                goto LABEL_51;
              }
              v52 = 1;
            }
            v34 = UbpmpTriggerConsumerSaveRegistrationStats(
                    v14,
                    *((_QWORD *)v14 + 3) + 56LL,
                    *((_QWORD *)v14 + 3) + 60LL,
                    *((_QWORD *)v14 + 3) + 68LL,
                    *((_QWORD *)v14 + 3) + 76LL);
            v12 = v34;
            if ( v34 )
            {
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                WPP_SF_Sd(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  17,
                  (unsigned int)WPP_dd0be36be19438d0c9cf63f3ad92ceae_Traceguids,
                  *(_QWORD *)(*((_QWORD *)v14 + 3) + 8LL),
                  v34);
              goto LABEL_51;
            }
            _InterlockedExchange64(
              (volatile __int64 *)v14 + 8,
              (unsigned int)(*(_DWORD *)(*((_QWORD *)v14 + 3) + 20LL) + 1));
            UbpmpAcquireListLockExclusive();
            if ( g_cTotalConsumers == 10000 )
            {
              UbpmpReleaseListLockExclusive();
              v12 = 84;
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                WPP_SF_Sdd(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  18,
                  (unsigned int)WPP_dd0be36be19438d0c9cf63f3ad92ceae_Traceguids,
                  *(_QWORD *)(*((_QWORD *)v14 + 3) + 8LL),
                  16,
                  84);
              goto LABEL_51;
            }
            for ( j = (_UNKNOWN **)g_leConsumerListHead; ; j = (_UNKNOWN **)*j )
            {
              if ( j == &g_leConsumerListHead )
                goto LABEL_61;
              if ( !_wcsicmp(*((const wchar_t **)j[2] + 1), *(const wchar_t **)(*((_QWORD *)v14 + 3) + 8LL)) )
                break;
              if ( UuidEqual(*(UUID **)j[2], **((UUID ***)v14 + 3), &v54) )
              {
                v59 = 1;
                v44 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                {
                  v45 = 20;
LABEL_137:
                  WPP_SF_S(
                    v44[2],
                    v45,
                    WPP_dd0be36be19438d0c9cf63f3ad92ceae_Traceguids,
                    *(_QWORD *)(*((_QWORD *)v14 + 3) + 8LL));
LABEL_61:
                  if ( !v59 )
                  {
                    RtlAcquireSRWLockExclusive((char *)v14 + 48);
                    *((_DWORD *)v14 + 14) = GetCurrentThreadId();
                    if ( (*((_BYTE *)a1 + 16) & 1) == 0 )
                    {
                      v22 = UbpmConsumerEnable(v14);
                      v12 = v22;
                      if ( v22 )
                      {
                        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                          WPP_SF_Sd(
                            *((_QWORD *)WPP_GLOBAL_Control + 2),
                            21,
                            (unsigned int)WPP_dd0be36be19438d0c9cf63f3ad92ceae_Traceguids,
                            *(_QWORD *)(*((_QWORD *)v14 + 3) + 8LL),
                            v22);
                        *((_DWORD *)v14 + 14) = 0;
                        RtlReleaseSRWLockExclusive((char *)v14 + 48);
                        UbpmpReleaseListLockExclusive();
                        goto LABEL_51;
                      }
                    }
                    *(_DWORD *)(*((_QWORD *)v14 + 3) + 16LL) &= ~0x40u;
                    v23 = off_18004C0E8;
                    if ( *off_18004C0E8 != (_UNKNOWN *)&g_leConsumerListHead )
                      __fastfail(3u);
                    ++g_cTotalConsumers;
                    *((_QWORD *)v14 + 1) = &g_leConsumerListHead;
                    *((_QWORD *)v14 + 2) = v23;
                    *v23 = (char *)v14 + 8;
                    off_18004C0E8 = (_UNKNOWN **)((char *)v14 + 8);
                    *((_QWORD *)v14 + 14) = ThreadpoolCleanupGroup;
                    ThreadpoolCleanupGroup = 0;
                    v24 = _InterlockedExchangeAdd((volatile signed __int32 *)&g_dwConsumerTag, 1u);
                    *((_BYTE *)v14 + 41) |= 1u;
                    v19 = *((_QWORD *)v14 + 3);
                    *((_DWORD *)v14 + 11) = v24 + 1;
                    v48 = (PVOID *)WPP_GLOBAL_Control;
                    if ( *(_DWORD *)(v19 + 20) )
                    {
                      while ( 2 )
                      {
                        v25 = *(_QWORD *)(v19 + 24);
                        v26 = *(_DWORD *)(v25 + 48LL * (unsigned __int16)v18);
                        if ( v26 == 1 )
                        {
                          if ( v48 == &WPP_GLOBAL_Control || (*((_BYTE *)v48 + 28) & 4) == 0 )
                            goto LABEL_33;
                          v46 = *(_QWORD *)(v25 + 48LL * (unsigned __int16)v18 + 8);
                          WPP_SF_SddddL(
                            (unsigned int)v48[2],
                            v19,
                            v47,
                            *(_QWORD *)v46,
                            *(_DWORD *)(v46 + 56),
                            *(_DWORD *)(v46 + 12),
                            *(_DWORD *)(v46 + 16),
                            *(_DWORD *)(v46 + 20),
                            *(_DWORD *)(v46 + 8));
                        }
                        else
                        {
                          v27 = v26 - 2;
                          if ( !v27 )
                          {
                            if ( v48 != &WPP_GLOBAL_Control && (*((_BYTE *)v48 + 28) & 4) != 0 )
                            {
                              v28 = *(_QWORD *)(v25 + 48LL * (unsigned __int16)v18 + 8);
                              WPP_SF_dd(
                                v48[2],
                                23,
                                WPP_dd0be36be19438d0c9cf63f3ad92ceae_Traceguids,
                                *(unsigned int *)(v28 + 12),
                                *(_DWORD *)(v28 + 8));
                              break;
                            }
LABEL_33:
                            v19 = *((_QWORD *)v14 + 3);
                            if ( *(_DWORD *)(*(_QWORD *)(v19 + 24) + 48LL * (unsigned __int16)v18 + 36) )
                            {
                              v20 = 0;
                              do
                              {
                                if ( v48 != &WPP_GLOBAL_Control && (*((_BYTE *)v48 + 28) & 4) != 0 )
                                {
                                  WPP_SF_S(
                                    v48[2],
                                    25,
                                    WPP_dd0be36be19438d0c9cf63f3ad92ceae_Traceguids,
                                    *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v19 + 24) + 48LL * (unsigned __int16)v18 + 40)
                                              + 8LL * v20));
                                  v48 = (PVOID *)WPP_GLOBAL_Control;
                                }
                                v19 = *((_QWORD *)v14 + 3);
                                ++v20;
                              }
                              while ( (unsigned int)v20 < *(_DWORD *)(*(_QWORD *)(v19 + 24)
                                                                    + 48LL * (unsigned __int16)v18
                                                                    + 36) );
                            }
                            LOWORD(v18) = (_WORD)v18 + 1;
                            if ( (unsigned int)(unsigned __int16)v18 >= *(_DWORD *)(v19 + 20) )
                            {
                              v18 = v56;
                              ThreadpoolCleanupGroup = (struct _TP_CLEANUP_GROUP *)v56;
                              goto LABEL_41;
                            }
                            continue;
                          }
                          if ( v27 != 1 || v48 == &WPP_GLOBAL_Control || (*((_BYTE *)v48 + 28) & 4) == 0 )
                            goto LABEL_33;
                          WPP_SF_(v48[2], 24, WPP_dd0be36be19438d0c9cf63f3ad92ceae_Traceguids);
                        }
                        break;
                      }
                      v48 = (PVOID *)WPP_GLOBAL_Control;
                      goto LABEL_33;
                    }
LABEL_41:
                    if ( *(_DWORD *)(v19 + 32) )
                    {
                      v21 = 0;
                      do
                      {
                        if ( v48 != &WPP_GLOBAL_Control && (*((_BYTE *)v48 + 28) & 4) != 0 )
                        {
                          WPP_SF_Sd(
                            (unsigned int)v48[2],
                            26,
                            (unsigned int)WPP_dd0be36be19438d0c9cf63f3ad92ceae_Traceguids,
                            *(_QWORD *)(*(_QWORD *)(v19 + 40) + 40LL * v21),
                            *(_DWORD *)(*(_QWORD *)(v19 + 40) + 40LL * v21 + 16));
                          v48 = (PVOID *)WPP_GLOBAL_Control;
                        }
                        v19 = *((_QWORD *)v14 + 3);
                        ++v21;
                      }
                      while ( (unsigned int)v21 < *(_DWORD *)(v19 + 32) );
                    }
                    if ( v48 != &WPP_GLOBAL_Control && (*((_BYTE *)v48 + 28) & 4) != 0 )
                      WPP_SF_SddiLdq(
                        *((_QWORD *)WPP_GLOBAL_Control + 2),
                        *((_QWORD *)v14 + 8),
                        v47,
                        *(_QWORD *)(*((_QWORD *)v14 + 3) + 8LL),
                        *(_DWORD *)(*((_QWORD *)v14 + 3) + 32LL),
                        *(_DWORD *)(*((_QWORD *)v14 + 3) + 20LL),
                        *((_QWORD *)v14 + 8),
                        *(_DWORD *)(v19 + 16),
                        v50,
                        (char)v14);
                    *((_DWORD *)v14 + 14) = 0;
                    RtlReleaseSRWLockExclusive((char *)v14 + 48);
                    UbpmpReleaseListLockExclusive();
                    *a3 = v14;
                    v14 = 0;
LABEL_51:
                    if ( !a2 )
                      UbpmTelemConsumerRegistered(a1, v12);
                    if ( v12 && v52 == 1 )
                    {
                      v49 = *(wchar_t **)(v55 + 64);
                      if ( !v49 )
                        v49 = *(wchar_t **)(*((_QWORD *)v14 + 3) + 8LL);
                      UbpmHardeningListRemove(v49);
                    }
                    if ( ThreadpoolCleanupGroup )
                      CloseThreadpoolCleanupGroup(ThreadpoolCleanupGroup);
                    if ( v14 )
                    {
                      UbpmConsumerDisable(v14);
                      UbpmUtilsFreeTimerContext((void **)v14 + 36, 1u);
                      UBPM_MIDL_user_free(*((_QWORD *)v14 + 4));
                      UBPM_MIDL_user_free(*((_QWORD *)v14 + 3));
                      UBPM_MIDL_user_free(v14);
                    }
                    if ( v18 )
                      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v18);
                    return v12;
                  }
                }
LABEL_106:
                UbpmpReleaseListLockExclusive();
                v12 = 183;
                goto LABEL_51;
              }
            }
            v59 = 1;
            v44 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              v45 = 19;
              goto LABEL_137;
            }
            goto LABEL_106;
          }
          LastError = GetLastError();
          v12 = LastError;
          v37 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          {
LABEL_104:
            v18 = (void *)v16;
            goto LABEL_51;
          }
          v38 = *(_QWORD *)(v16 + 8);
          v39 = 14;
        }
        else
        {
          LastError = GetLastError();
          v12 = LastError;
          v37 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
            goto LABEL_104;
          v38 = *(_QWORD *)(v16 + 8);
          v39 = 13;
        }
      }
      else
      {
        LastError = GetLastError();
        v12 = LastError;
        v37 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_104;
        v38 = *(_QWORD *)(v16 + 8);
        v39 = 12;
      }
    }
    WPP_SF_Sd(v37[2], v39, (unsigned int)WPP_dd0be36be19438d0c9cf63f3ad92ceae_Traceguids, v38, LastError);
    goto LABEL_104;
  }
  v12 = 183;
  if ( a2 != 1 )
    return UbpmpTriggerConsumerUpdate(a1);
  return v12;
}

```

## disassembly

```asm
0x18000d5c0  mov     rax, rsp
0x18000d5c3  mov     [rax+18h], r8
0x18000d5c7  mov     [rax+10h], dl
0x18000d5ca  push    rbx
0x18000d5cb  push    rbp
0x18000d5cc  push    rsi
0x18000d5cd  push    rdi
0x18000d5ce  push    r12
0x18000d5d0  push    r13
0x18000d5d2  push    r15
0x18000d5d4  sub     rsp, 80h
0x18000d5db  mov     esi, cs:UbpmpLockTrackerId
0x18000d5e1  xor     ebp, ebp
0x18000d5e3  xor     r15b, r15b
0x18000d5e6  mov     byte ptr [rax+20h], 0
0x18000d5ea  mov     byte ptr [rax-68h], 0
0x18000d5ee  mov     r12, r8
0x18000d5f1  mov     [rax-58h], rbp
0x18000d5f5  movzx   r13d, dl
0x18000d5f9  mov     [rax-60h], ebp
0x18000d5fc  mov     rdi, rcx
0x18000d5ff  mov     [rax-64h], ebp
0x18000d602  cmp     esi, 0FFFFFFFFh
0x18000d605  jz      short loc_18000D62F
0x18000d607  mov     ecx, esi; dwTlsIndex
0x18000d609  call    cs:__imp_TlsGetValue
0x18000d60f  mov     ecx, esi; dwTlsIndex
0x18000d611  mov     rbx, rax
0x18000d614  call    cs:__imp_TlsGetValue
0x18000d61a  test    qword ptr [rax], 0FFFFFFFFFFFFFFFEh
0x18000d621  jnz     loc_18000D7FD
0x18000d627  or      qword ptr [rbx], 2
0x18000d62b  inc     qword ptr [rbx+10h]
0x18000d62f  lea     rcx, ?g_ConsumerListLock@@3U_CEM_LOCK@@A; _CEM_LOCK g_ConsumerListLock
0x18000d636  call    cs:__imp_RtlAcquireSRWLockShared
0x18000d63c  mov     rbx, cs:g_leConsumerListHead
0x18000d643  mov     [rsp+0B8h+arg_0], r14
0x18000d64b  lea     rax, g_leConsumerListHead
0x18000d652  cmp     rbx, rax
0x18000d655  jz      loc_18000D731
0x18000d65b  mov     rcx, [rbx+10h]
0x18000d65f  mov     rdx, [rdi+8]; String2
0x18000d663  mov     rcx, [rcx+8]; String1
0x18000d667  call    cs:__imp__wcsicmp
0x18000d66d  test    eax, eax
0x18000d66f  jz      short loc_18000D693
0x18000d671  mov     rcx, [rbx+10h]
0x18000d675  lea     r8, [rsp+0B8h+Status]; Status
0x18000d67a  mov     rdx, [rdi]; Uuid2
0x18000d67d  mov     rcx, [rcx]; Uuid1
0x18000d680  call    cs:__imp_UuidEqual
0x18000d686  test    eax, eax
0x18000d688  jnz     loc_18000DD6C
0x18000d68e  mov     rbx, [rbx]
0x18000d691  jmp     short loc_18000D64B
0x18000d693  mov     r15b, 1
0x18000d696  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d69d  lea     r14, WPP_GLOBAL_Control
0x18000d6a4  cmp     rcx, r14
0x18000d6a7  jz      short loc_18000D6B3
0x18000d6a9  test    byte ptr [rcx+1Ch], 2
0x18000d6ad  jnz     loc_18000DDAE
0x18000d6b3  mov     ecx, cs:UbpmpLockTrackerId; dwTlsIndex
0x18000d6b9  cmp     ecx, 0FFFFFFFFh
0x18000d6bc  jz      short loc_18000D6DF
0x18000d6be  call    cs:__imp_TlsGetValue
0x18000d6c4  mov     r8, [rax]
0x18000d6c7  test    r8b, 2
0x18000d6cb  jz      loc_18000D7F6
0x18000d6d1  sub     qword ptr [rax+10h], 1
0x18000d6d6  jnz     short loc_18000D6DF
0x18000d6d8  and     r8, 0FFFFFFFFFFFFFFFDh
0x18000d6dc  mov     [rax], r8
0x18000d6df  lea     rcx, ?g_ConsumerListLock@@3U_CEM_LOCK@@A; _CEM_LOCK g_ConsumerListLock
0x18000d6e6  call    cs:__imp_RtlReleaseSRWLockShared
0x18000d6ec  mov     [rsp+0B8h+arg_18], r15b
0x18000d6f4  test    r15b, r15b
0x18000d6f7  jz      short loc_18000D73D
0x18000d6f9  mov     ebp, 0B7h
0x18000d6fe  cmp     r13b, 1
0x18000d702  jz      loc_18000D909
0x18000d708  mov     r9, r12
0x18000d70b  movzx   edx, r15b
0x18000d70f  mov     rcx, rdi; struct _UBPM_TRIGGER_CONSUMER_PARAMS_1 *
0x18000d712  call    UbpmpTriggerConsumerUpdate
0x18000d717  mov     r14, [rsp+0B8h+arg_0]
0x18000d71f  add     rsp, 80h
0x18000d726  pop     r15
0x18000d728  pop     r13
0x18000d72a  pop     r12
0x18000d72c  pop     rdi
0x18000d72d  pop     rsi
0x18000d72e  pop     rbp
0x18000d72f  pop     rbx
0x18000d730  retn
0x18000d731  lea     r14, WPP_GLOBAL_Control
0x18000d738  jmp     loc_18000D6B3
0x18000d73d  mov     rsi, rbp
0x18000d740  mov     [rsp+0B8h+Status], ebp
0x18000d744  mov     r9, rdi; struct _UBPM_TRIGGER_CONSUMER_PARAMS_1 *
0x18000d747  mov     [rsp+0B8h+var_67], sil
0x18000d74c  lea     r8, [rsp+0B8h+Status]; unsigned int *
0x18000d751  xor     edx, edx; unsigned int
0x18000d753  xor     ecx, ecx; struct _UBPM_TRIGGER_CONSUMER_PARAMS_1 *
0x18000d755  mov     r13, rbp
0x18000d758  mov     rbx, rbp
0x18000d75b  call    ?UbpmpCopyRegistrationParams@@YAKPEAU_UBPM_TRIGGER_CONSUMER_PARAMS_1@@KPEAK0@Z; UbpmpCopyRegistrationParams(_UBPM_TRIGGER_CONSUMER_PARAMS_1 *,ulong,ulong *,_UBPM_TRIGGER_CONSUMER_PARAMS_1 *)
0x18000d760  mov     ebp, eax
0x18000d762  cmp     eax, 7Ah ; 'z'
0x18000d765  jnz     short loc_18000D792
0x18000d767  mov     ecx, [rsp+0B8h+Status]; Size
0x18000d76b  call    ?UbpmAlloc@@YAPEAXK@Z; UbpmAlloc(ulong)
0x18000d770  mov     rbx, rax
0x18000d773  test    rax, rax
0x18000d776  jz      loc_18000DDCC
0x18000d77c  mov     edx, [rsp+0B8h+Status]; unsigned int
0x18000d780  lea     r8, [rsp+0B8h+Status]; unsigned int *
0x18000d785  mov     r9, rdi; struct _UBPM_TRIGGER_CONSUMER_PARAMS_1 *
0x18000d788  mov     rcx, rax; struct _UBPM_TRIGGER_CONSUMER_PARAMS_1 *
0x18000d78b  call    ?UbpmpCopyRegistrationParams@@YAKPEAU_UBPM_TRIGGER_CONSUMER_PARAMS_1@@KPEAK0@Z; UbpmpCopyRegistrationParams(_UBPM_TRIGGER_CONSUMER_PARAMS_1 *,ulong,ulong *,_UBPM_TRIGGER_CONSUMER_PARAMS_1 *)
0x18000d790  mov     ebp, eax
0x18000d792  test    ebp, ebp
0x18000d794  jz      loc_18000DA7F
0x18000d79a  test    rbx, rbx
0x18000d79d  jz      short loc_18000D7B7
0x18000d79f  mov     rcx, gs:60h
0x18000d7a8  mov     r8, rbx; P
0x18000d7ab  xor     edx, edx; Flags
0x18000d7ad  mov     rcx, [rcx+30h]; HeapHandle
0x18000d7b1  call    cs:__imp_RtlFreeHeap
0x18000d7b7  xor     r12d, r12d
0x18000d7ba  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d7c1  cmp     rcx, r14
0x18000d7c4  jz      loc_18000D8BE
0x18000d7ca  test    byte ptr [rcx+1Ch], 1
0x18000d7ce  jz      loc_18000D8BE
0x18000d7d4  mov     r9, [rdi+8]
0x18000d7d8  mov     edx, 0Ah
0x18000d7dd  mov     dword ptr [rsp+0B8h+var_98], ebp
0x18000d7e1  mov     rcx, [rcx+10h]
0x18000d7e5  lea     r8, WPP_dd0be36be19438d0c9cf63f3ad92ceae_Traceguids
0x18000d7ec  call    WPP_SF_Sd
0x18000d7f1  jmp     loc_18000D8BE
0x18000d7f6  int     2Ch; Windows NT - assertion failure
0x18000d7f8  jmp     loc_18000D6D1
0x18000d7fd  int     2Ch; Windows NT - assertion failure
0x18000d7ff  jmp     loc_18000D627
0x18000d804  cmp     r10, r14
0x18000d807  jz      short loc_18000D814
0x18000d809  test    byte ptr [r10+1Ch], 4
0x18000d80e  jnz     loc_18000DF2C
0x18000d814  mov     rdx, [rsi+18h]
0x18000d818  mov     rax, [rdx+18h]
0x18000d81c  cmp     dword ptr [rax+r13*8+24h], 0
0x18000d822  jbe     short loc_18000D84B
0x18000d824  xor     ebx, ebx
0x18000d826  cmp     r10, r14
0x18000d829  jz      short loc_18000D836
0x18000d82b  test    byte ptr [r10+1Ch], 4
0x18000d830  jnz     loc_18000DF6A
0x18000d836  mov     rdx, [rsi+18h]
0x18000d83a  inc     bx
0x18000d83d  movzx   eax, bx
0x18000d840  mov     rcx, [rdx+18h]
0x18000d844  cmp     eax, [rcx+r13*8+24h]
0x18000d849  jb      short loc_18000D826
0x18000d84b  inc     r12w
0x18000d84f  movzx   eax, r12w
0x18000d853  cmp     eax, [rdx+14h]
0x18000d856  jb      loc_18000D9B5
0x18000d85c  mov     r12, [rsp+0B8h+var_50]
0x18000d861  mov     r13, r12
0x18000d864  cmp     dword ptr [rdx+20h], 0
0x18000d868  jbe     short loc_18000D88B
0x18000d86a  xor     ebx, ebx
0x18000d86c  cmp     r10, r14
0x18000d86f  jz      short loc_18000D87C
0x18000d871  test    byte ptr [r10+1Ch], 4
0x18000d876  jnz     loc_18000DF9B
0x18000d87c  mov     rdx, [rsi+18h]
0x18000d880  inc     bx
0x18000d883  movzx   eax, bx
0x18000d886  cmp     eax, [rdx+20h]
0x18000d889  jb      short loc_18000D86C
0x18000d88b  cmp     r10, r14
0x18000d88e  jz      short loc_18000D89B
0x18000d890  test    byte ptr [r10+1Ch], 4
0x18000d895  jnz     loc_18000DFD6
0x18000d89b  lea     rcx, [rsi+30h]
0x18000d89f  mov     dword ptr [rsi+38h], 0
0x18000d8a6  call    cs:__imp_RtlReleaseSRWLockExclusive
0x18000d8ac  call    UbpmpReleaseListLockExclusive
0x18000d8b1  mov     rax, [rsp+0B8h+arg_10]
0x18000d8b9  mov     [rax], rsi
0x18000d8bc  xor     esi, esi
0x18000d8be  cmp     [rsp+0B8h+arg_8], 0
0x18000d8c6  jnz     short loc_18000D8D2
0x18000d8c8  mov     edx, ebp
0x18000d8ca  mov     rcx, rdi
0x18000d8cd  call    UbpmTelemConsumerRegistered
0x18000d8d2  test    ebp, ebp
0x18000d8d4  jnz     loc_18000E018
0x18000d8da  test    r13, r13
0x18000d8dd  jnz     loc_18000E043
0x18000d8e3  test    rsi, rsi
0x18000d8e6  jnz     loc_18000E051
0x18000d8ec  test    r12, r12
0x18000d8ef  jz      short loc_18000D909
0x18000d8f1  mov     rcx, gs:60h
0x18000d8fa  mov     r8, r12; P
0x18000d8fd  xor     edx, edx; Flags
0x18000d8ff  mov     rcx, [rcx+30h]; HeapHandle
0x18000d903  call    cs:__imp_RtlFreeHeap
0x18000d909  mov     eax, ebp
0x18000d90b  jmp     loc_18000D717
0x18000d910  cmp     [rsp+0B8h+arg_18], r12b
0x18000d918  jnz     loc_18000DCDD
0x18000d91e  lea     rcx, [rsi+30h]
0x18000d922  call    cs:__imp_RtlAcquireSRWLockExclusive
0x18000d928  call    cs:__imp_GetCurrentThreadId
0x18000d92e  mov     [rsi+38h], eax
0x18000d931  test    byte ptr [rdi+10h], 1
0x18000d935  jnz     short loc_18000D949
0x18000d937  mov     rcx, rsi; struct _UBPM_TRIGGER_CONSUMER_BLOCK *
0x18000d93a  call    UbpmConsumerEnable
0x18000d93f  mov     ebp, eax
0x18000d941  test    eax, eax
0x18000d943  jnz     loc_18000DA57
0x18000d949  mov     rax, [rsi+18h]
0x18000d94d  lea     rdx, g_leConsumerListHead
0x18000d954  and     dword ptr [rax+10h], 0FFFFFFBFh
0x18000d958  mov     rcx, cs:off_18004C0E8
0x18000d95f  cmp     [rcx], rdx
0x18000d962  jnz     loc_18000DA50
0x18000d968  inc     cs:g_cTotalConsumers
0x18000d96e  lea     rax, [rsi+8]
0x18000d972  mov     [rax], rdx
0x18000d975  mov     [rax+8], rcx
0x18000d979  mov     [rcx], rax
0x18000d97c  mov     cs:off_18004C0E8, rax
0x18000d983  mov     eax, 1
0x18000d988  mov     [rsi+70h], r13
0x18000d98c  xor     r13d, r13d
0x18000d98f  lock xadd cs:?g_dwConsumerTag@@3KC, eax; ulong volatile g_dwConsumerTag
0x18000d997  or      byte ptr [rsi+29h], 1
0x18000d99b  inc     eax
0x18000d99d  mov     rdx, [rsi+18h]
0x18000d9a1  mov     [rsi+2Ch], eax
0x18000d9a4  mov     r10, cs:WPP_GLOBAL_Control
0x18000d9ab  cmp     [rdx+14h], r12d
0x18000d9af  jbe     loc_18000D864
0x18000d9b5  mov     r9, [rdx+18h]
0x18000d9b9  movzx   eax, r12w
0x18000d9bd  lea     r13, [rax+rax*2]
0x18000d9c1  add     r13, r13
0x18000d9c4  mov     eax, [r9+r13*8]
0x18000d9c8  cmp     eax, 1
0x18000d9cb  jz      loc_18000D804
0x18000d9d1  sub     eax, 2
0x18000d9d4  jnz     short loc_18000DA1C
0x18000d9d6  cmp     r10, r14
0x18000d9d9  jz      loc_18000D814
0x18000d9df  test    byte ptr [r10+1Ch], 4
0x18000d9e4  jz      loc_18000D814
0x18000d9ea  mov     r9, [r9+r13*8+8]
0x18000d9ef  lea     r8, WPP_dd0be36be19438d0c9cf63f3ad92ceae_Traceguids
0x18000d9f6  mov     rcx, [r10+10h]
0x18000d9fa  mov     edx, 17h
0x18000d9ff  mov     eax, [r9+8]
0x18000da03  mov     r9d, [r9+0Ch]
0x18000da07  mov     dword ptr [rsp+0B8h+var_98], eax
0x18000da0b  call    WPP_SF_dd
0x18000da10  mov     r10, cs:WPP_GLOBAL_Control
0x18000da17  jmp     loc_18000D814
0x18000da1c  cmp     eax, 1
0x18000da1f  jnz     loc_18000D814
0x18000da25  cmp     r10, r14
0x18000da28  jz      loc_18000D814
0x18000da2e  test    byte ptr [r10+1Ch], 4
0x18000da33  jz      loc_18000D814
0x18000da39  mov     rcx, [r10+10h]
0x18000da3d  lea     r8, WPP_dd0be36be19438d0c9cf63f3ad92ceae_Traceguids
0x18000da44  mov     edx, 18h
0x18000da49  call    WPP_SF_
0x18000da4e  jmp     short loc_18000DA10
0x18000da50  mov     ecx, 3
0x18000da55  int     29h; Win8: RtlFailFast(ecx)
0x18000da57  mov     rcx, cs:WPP_GLOBAL_Control
0x18000da5e  cmp     rcx, r14
0x18000da61  jnz     loc_18000DEFC
0x18000da67  lea     rcx, [rsi+30h]
0x18000da6b  mov     [rsi+38h], r12d
0x18000da6f  call    cs:__imp_RtlReleaseSRWLockExclusive
0x18000da75  call    UbpmpReleaseListLockExclusive
0x18000da7a  jmp     loc_18000D8BE
0x18000da7f  lea     r9, [rsp+0B8h+arg_18]
0x18000da87  mov     rcx, rbx
0x18000da8a  lea     r8, [rsp+0B8h+var_68]
0x18000da8f  lea     rdx, [rsp+0B8h+var_58]
0x18000da94  call    UbpmpValidateConsumerParameters
  ... truncated ...
```
