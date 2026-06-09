# UbpmpExecutionTimeLimitCallback

- ea: `0x180007480`
- end: `0x180007980`
- name: `UbpmpExecutionTimeLimitCallback`
- size: `1280`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18000c650`

## callees

- `0x180002f84`
- `0x1800049b4`
- `0x180007480`
- `0x180007990`
- `0x180007c50`
- `0x180007e30`
- `0x18000a03c`
- `0x180019d90`
- `0x18001e9f4`
- `0x18002659c`
- `0x18002b258`
- `0x18002eb98`
- `0x180032dd8`
- `0x1800347bc`
- `0x18003d810`

## import_xrefs

- `ntdll!RtlReleaseSRWLockShared` at `0x18000758a`
- `ntdll!RtlReleaseSRWLockShared` at `0x18000758a`
- `ntdll!RtlAcquireSRWLockShared` at `0x18000751c`
- `ntdll!RtlAcquireSRWLockShared` at `0x18000751c`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x1800076a3`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180007772`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x1800078f4`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x1800076a3`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180007772`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x1800078f4`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180007603`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800077ac`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180007925`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180007603`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800077ac`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180007925`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800076a9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007778`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800078fa`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800076a9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007778`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800078fa`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800075ed`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800075ed`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800075b3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800075b3`
- `RPCRT4!UuidEqual` at `0x18000789d`
- `RPCRT4!UuidEqual` at `0x18000789d`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180007684`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180007684`

## string_xrefs

- `0x18000765d`: `NT TASK`
- `0x1800078cc`: `Removed`
- `0x1800078ba`: `Not removed`

## pseudocode

```c
void __fastcall UbpmpExecutionTimeLimitCallback(__int64 a1, char a2, __int64 a3)
{
  int v3; // r14d
  __int64 v4; // r15
  unsigned __int64 v5; // r12
  const WCHAR *v6; // rbx
  __int64 v7; // rax
  __int64 v8; // rcx
  unsigned __int16 *v9; // rdx
  __int64 v10; // r8
  unsigned __int16 *v11; // rcx
  __int64 *v12; // rbx
  __int64 *v13; // rdi
  ULONGLONG TickCount64; // rsi
  __int64 v15; // r8
  __int64 v16; // rcx
  ULONGLONG v17; // rax
  __int64 *v18; // rbp
  void *v19; // rcx
  char v20; // r13
  DWORD CurrentThreadId; // eax
  UUID *v22; // r14
  __int64 *v23; // rcx
  __int64 **v24; // rax
  UUID *v25; // rax
  UUID **v26; // rcx
  UUID *v27; // r15
  const wchar_t *v28; // r9
  DWORD v29; // eax
  __int64 v30; // r8
  unsigned __int64 v31; // r12
  unsigned __int64 v32; // rdx
  int v33; // [rsp+30h] [rbp-258h]
  RPC_STATUS Status; // [rsp+34h] [rbp-254h] BYREF
  __int64 v35; // [rsp+38h] [rbp-250h]
  __int64 v36; // [rsp+40h] [rbp-248h]
  unsigned __int16 v37[256]; // [rsp+50h] [rbp-238h] BYREF

  if ( (a2 & 4) == 0 )
  {
    v3 = 0;
    v36 = a1;
    v4 = a1;
    if ( a3 )
      v3 = a3;
    v33 = v3;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_S(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        130,
        WPP_dd0be36be19438d0c9cf63f3ad92ceae_Traceguids,
        *(_QWORD *)(*(_QWORD *)(a1 + 24) + 8LL));
    if ( !(unsigned int)UbpmConsumerIncPendingActions(v4) )
    {
      v5 = -1;
      v35 = -1;
      RtlAcquireSRWLockShared(v4 + 48);
      v6 = *(const WCHAR **)(*(_QWORD *)(v4 + 24) + 8LL);
      if ( v6 )
      {
        v7 = -1;
        do
          ++v7;
        while ( v6[v7] );
        if ( (unsigned int)v7 > 8 && CompareStringW(0x7Fu, 1u, v6, 7, L"NT TASK", 7) == 2 )
          v6 += 7;
      }
      v8 = 2147483646;
      v9 = v37;
      v10 = 256;
      do
      {
        if ( !v8 )
          break;
        if ( !*v6 )
          break;
        *v9++ = *v6++;
        --v8;
        --v10;
      }
      while ( v10 );
      v11 = v9 - 1;
      if ( v10 )
        v11 = v9;
      *v11 = 0;
      RtlReleaseSRWLockShared(v4 + 48);
      if ( !v3 )
      {
        RtlAcquireSRWLockExclusive(v4 + 208);
        *(_DWORD *)(v4 + 216) = GetCurrentThreadId();
      }
      UbpmpActionContextCleanup(v4);
      v12 = (__int64 *)(v4 + 224);
      v13 = *(__int64 **)(v4 + 224);
      TickCount64 = GetTickCount64();
      if ( v13 != (__int64 *)(v4 + 224) )
      {
        do
        {
          v17 = v13[9];
          v18 = (__int64 *)*v13;
          if ( v17 )
          {
            if ( v17 > TickCount64 )
            {
              if ( v5 >= v17 )
                v5 = v13[9];
              v35 = v5;
            }
            else
            {
              UbpmpActionTerminate(v13[3], v13[4], v13 + 5, 0);
              ReportTaskEvent(v19, &STOPPING_ON_TIMEOUT, v37, (const struct _GUID *)((char *)v13 + 52));
              Status = 0;
              v20 = 0;
              *(_OWORD *)(v4 + 272) = 0;
              RtlAcquireSRWLockExclusive(&g_QueuedSerialActionsLock);
              CurrentThreadId = GetCurrentThreadId();
              v22 = (UUID *)g_leQueuedSerialActionsListHead;
              dword_18004CEA0 = CurrentThreadId;
              while ( v22 != (UUID *)&g_leQueuedSerialActionsListHead )
              {
                v27 = *(UUID **)&v22->Data1;
                if ( v13 != (__int64 *)-52LL && UuidEqual((UUID *)((char *)v13 + 52), v22 + 1, &Status) )
                {
                  v25 = *(UUID **)&v22->Data1;
                  if ( *(UUID **)(*(_QWORD *)&v22->Data1 + 8LL) != v22 )
                    goto LABEL_50;
                  v26 = *(UUID ***)v22->Data4;
                  if ( *v26 != v22 )
                    goto LABEL_50;
                  *v26 = v25;
                  *(_QWORD *)v25->Data4 = v26;
                  *(_QWORD *)v22->Data4 = v22;
                  *(_QWORD *)&v22->Data1 = v22;
                  UBPM_MIDL_user_free(v22);
                  v20 = 1;
                }
                v22 = v27;
              }
              dword_18004CEA0 = 0;
              RtlReleaseSRWLockExclusive(&g_QueuedSerialActionsLock);
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
              {
                v28 = L"Removed";
                if ( !v20 )
                  v28 = L"Not removed";
                WPP_SF_Sd(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  95,
                  (unsigned int)WPP_dcdc688f20ff37c56e3e77310b95cc70_Traceguids,
                  (_DWORD)v28,
                  0);
              }
              v4 = v36;
              if ( *(_QWORD *)(*(_QWORD *)(v36 + 24) + 48LL) )
              {
                RtlAcquireSRWLockExclusive(&g_MaintenanceLaunchLock);
                v29 = GetCurrentThreadId();
                LOBYTE(v30) = 2;
                dword_18004CEE8 = v29;
                UbpmpMaintenanceTaskStoppedCallout(v4, v13, v30);
                dword_18004CEE8 = 0;
                RtlReleaseSRWLockExclusive(&g_MaintenanceLaunchLock);
              }
              UbpmQueueConsumerClose((void *)v13[13]);
              v23 = (__int64 *)*v13;
              if ( *(__int64 **)(*v13 + 8) != v13 || (v24 = (__int64 **)v13[1], *v24 != v13) )
LABEL_50:
                __fastfail(3u);
              *v24 = v23;
              v23[1] = (__int64)v24;
              v13[1] = (__int64)v13;
              *v13 = (__int64)v13;
              UBPM_MIDL_user_free(v13);
              v5 = v35;
            }
          }
          v13 = v18;
        }
        while ( v18 != v12 );
        if ( v5 != -1 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
            WPP_SF_ii(*((_QWORD *)WPP_GLOBAL_Control + 2), 131, v15, v5, TickCount64);
          v31 = v5 - TickCount64;
          v32 = 5000;
          if ( v31 > 0x1388 )
            v32 = v31;
          UbpmUtilsSetTimerContext(*(void **)(v4 + 288), v32, 0);
          v3 = v33;
          goto LABEL_22;
        }
        v3 = v33;
      }
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 132, WPP_dd0be36be19438d0c9cf63f3ad92ceae_Traceguids);
      v16 = *(_QWORD *)(v4 + 288);
      if ( v16 )
        SetThreadpoolTimer(*(PTP_TIMER *)(v16 + 40), 0, 0, 0);
LABEL_22:
      if ( !v3 )
      {
        *(_DWORD *)(v4 + 216) = 0;
        RtlReleaseSRWLockExclusive(v4 + 208);
      }
      UbpmConsumerDecPendingActions(v4);
    }
  }
}

```

## disassembly

```asm
0x180007480  test    dl, 4
0x180007483  jnz     locret_18000765C
0x180007489  push    r14
0x18000748b  push    r15
0x18000748d  sub     rsp, 278h
0x180007494  mov     rax, cs:__security_cookie
0x18000749b  xor     rax, rsp
0x18000749e  mov     [rsp+288h+var_38], rax
0x1800074a6  xor     r14d, r14d
0x1800074a9  mov     [rsp+288h+var_248], rcx
0x1800074ae  test    r8, r8
0x1800074b1  mov     [rsp+288h+var_28], r13
0x1800074b9  mov     r15, rcx
0x1800074bc  cmovnz  r14d, r8d
0x1800074c0  mov     [rsp+288h+var_258], r14d
0x1800074c5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800074cc  lea     r13, WPP_GLOBAL_Control
0x1800074d3  cmp     rcx, r13
0x1800074d6  jnz     loc_1800076BB
0x1800074dc  mov     rcx, r15
0x1800074df  call    UbpmConsumerIncPendingActions
0x1800074e4  test    eax, eax
0x1800074e6  jnz     loc_180007639
0x1800074ec  mov     [rsp+288h+arg_8], rbx
0x1800074f4  lea     rcx, [r15+30h]
0x1800074f8  mov     [rsp+288h+arg_18], rsi
0x180007500  mov     [rsp+288h+var_18], rdi
0x180007508  mov     [rsp+288h+var_20], r12
0x180007510  mov     r12, 0FFFFFFFFFFFFFFFFh
0x180007517  mov     [rsp+288h+var_250], r12
0x18000751c  call    cs:__imp_RtlAcquireSRWLockShared
0x180007522  mov     rbx, [r15+18h]
0x180007526  mov     rbx, [rbx+8]
0x18000752a  test    rbx, rbx
0x18000752d  jz      short loc_180007545
0x18000752f  mov     rax, r12
0x180007532  inc     rax
0x180007535  cmp     word ptr [rbx+rax*2], 0
0x18000753a  jnz     short loc_180007532
0x18000753c  cmp     eax, 8
0x18000753f  ja      loc_18000765D
0x180007545  mov     ecx, 7FFFFFFEh
0x18000754a  lea     rdx, [rsp+288h+var_238]
0x18000754f  mov     r8d, 100h
0x180007555  test    rcx, rcx
0x180007558  jz      short loc_180007576
0x18000755a  movzx   eax, word ptr [rbx]
0x18000755d  test    ax, ax
0x180007560  jz      short loc_180007576
0x180007562  mov     [rdx], ax
0x180007565  add     rbx, 2
0x180007569  add     rdx, 2
0x18000756d  dec     rcx
0x180007570  sub     r8, 1
0x180007574  jnz     short loc_180007555
0x180007576  test    r8, r8
0x180007579  lea     rcx, [rdx-2]
0x18000757d  cmovnz  rcx, rdx
0x180007581  xor     eax, eax
0x180007583  mov     [rcx], ax
0x180007586  lea     rcx, [r15+30h]
0x18000758a  call    cs:__imp_RtlReleaseSRWLockShared
0x180007590  test    r14d, r14d
0x180007593  jz      loc_18000769C
0x180007599  mov     rcx, r15
0x18000759c  mov     [rsp+288h+arg_10], rbp
0x1800075a4  call    UbpmpActionContextCleanup
0x1800075a9  lea     rbx, [r15+0E0h]
0x1800075b0  mov     rdi, [rbx]
0x1800075b3  call    cs:__imp_GetTickCount64
0x1800075b9  mov     rsi, rax
0x1800075bc  cmp     rdi, rbx
0x1800075bf  jnz     loc_180007710
0x1800075c5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800075cc  cmp     rcx, r13
0x1800075cf  jnz     loc_1800076E7
0x1800075d5  mov     rcx, [r15+120h]
0x1800075dc  test    rcx, rcx
0x1800075df  jz      short loc_1800075F3
0x1800075e1  mov     rcx, [rcx+28h]; pti
0x1800075e5  xor     r9d, r9d; msWindowLength
0x1800075e8  xor     r8d, r8d; msPeriod
0x1800075eb  xor     edx, edx; pftDueTime
0x1800075ed  call    cs:__imp_SetThreadpoolTimer
0x1800075f3  test    r14d, r14d
0x1800075f6  jnz     short loc_180007609
0x1800075f8  lea     rcx, [r15+0D0h]
0x1800075ff  mov     [rcx+8], r14d
0x180007603  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180007609  mov     rcx, r15
0x18000760c  call    UbpmConsumerDecPendingActions
0x180007611  mov     rbp, [rsp+288h+arg_10]
0x180007619  mov     rdi, [rsp+288h+var_18]
0x180007621  mov     rsi, [rsp+288h+arg_18]
0x180007629  mov     r12, [rsp+288h+var_20]
0x180007631  mov     rbx, [rsp+288h+arg_8]
0x180007639  mov     r13, [rsp+288h+var_28]
0x180007641  mov     rcx, [rsp+288h+var_38]
0x180007649  xor     rcx, rsp; StackCookie
0x18000764c  call    __security_check_cookie
0x180007651  add     rsp, 278h
0x180007658  pop     r15
0x18000765a  pop     r14
0x18000765c  retn
0x18000765d  lea     rax, String2; "NT TASK"
0x180007664  mov     [rsp+288h+cchCount2], 7; cchCount2
0x18000766c  mov     r9d, 7; cchCount1
0x180007672  mov     [rsp+288h+lpString2], rax; lpString2
0x180007677  mov     r8, rbx; lpString1
0x18000767a  mov     edx, 1; dwCmpFlags
0x18000767f  mov     ecx, 7Fh; Locale
0x180007684  call    cs:__imp_CompareStringW
0x18000768a  cmp     eax, 2
0x18000768d  jnz     loc_180007545
0x180007693  add     rbx, 0Eh
0x180007697  jmp     loc_180007545
0x18000769c  lea     rcx, [r15+0D0h]
0x1800076a3  call    cs:__imp_RtlAcquireSRWLockExclusive
0x1800076a9  call    cs:__imp_GetCurrentThreadId
0x1800076af  mov     [r15+0D8h], eax
0x1800076b6  jmp     loc_180007599
0x1800076bb  test    byte ptr [rcx+1Ch], 4
0x1800076bf  jz      loc_1800074DC
0x1800076c5  mov     r9, [r15+18h]
0x1800076c9  lea     r8, WPP_dd0be36be19438d0c9cf63f3ad92ceae_Traceguids
0x1800076d0  mov     rcx, [rcx+10h]
0x1800076d4  mov     edx, 82h
0x1800076d9  mov     r9, [r9+8]
0x1800076dd  call    WPP_SF_S
0x1800076e2  jmp     loc_1800074DC
0x1800076e7  test    byte ptr [rcx+1Ch], 4
0x1800076eb  jz      loc_1800075D5
0x1800076f1  mov     rcx, [rcx+10h]
0x1800076f5  lea     r8, WPP_dd0be36be19438d0c9cf63f3ad92ceae_Traceguids
0x1800076fc  mov     edx, 84h
0x180007701  call    WPP_SF_
0x180007706  jmp     loc_1800075D5
0x180007710  mov     rax, [rdi+48h]
0x180007714  mov     rbp, [rdi]
0x180007717  test    rax, rax
0x18000771a  jz      loc_18000784C
0x180007720  cmp     rax, rsi
0x180007723  ja      loc_180007840
0x180007729  mov     rdx, [rdi+20h]
0x18000772d  lea     r8, [rdi+28h]
0x180007731  mov     rcx, [rdi+18h]
0x180007735  xor     r9d, r9d
0x180007738  call    UbpmpActionTerminate
0x18000773d  lea     r12, [rdi+34h]
0x180007741  mov     r9, r12; struct _GUID *
0x180007744  lea     r8, [rsp+288h+var_238]; unsigned __int16 *
0x180007749  lea     rdx, STOPPING_ON_TIMEOUT; struct _EVENT_DESCRIPTOR *
0x180007750  call    ?ReportTaskEvent@@YAKPEAXPEBU_EVENT_DESCRIPTOR@@PEBGPEBU_GUID@@@Z; ReportTaskEvent(void *,_EVENT_DESCRIPTOR const *,ushort const *,_GUID const *)
0x180007755  xorps   xmm0, xmm0
0x180007758  mov     [rsp+288h+Status], 0
0x180007760  lea     rcx, g_QueuedSerialActionsLock
0x180007767  xor     r13b, r13b
0x18000776a  movups  xmmword ptr [r15+110h], xmm0
0x180007772  call    cs:__imp_RtlAcquireSRWLockExclusive
0x180007778  call    cs:__imp_GetCurrentThreadId
0x18000777e  mov     r14, cs:g_leQueuedSerialActionsListHead
0x180007785  mov     cs:dword_18004CEA0, eax
0x18000778b  lea     rax, g_leQueuedSerialActionsListHead
0x180007792  cmp     r14, rax
0x180007795  jnz     loc_180007889
0x18000779b  lea     rcx, g_QueuedSerialActionsLock
0x1800077a2  mov     cs:dword_18004CEA0, 0
0x1800077ac  call    cs:__imp_RtlReleaseSRWLockExclusive
0x1800077b2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800077b9  lea     r14, WPP_GLOBAL_Control
0x1800077c0  cmp     rcx, r14
0x1800077c3  jz      short loc_1800077CF
0x1800077c5  test    byte ptr [rcx+1Ch], 20h
0x1800077c9  jnz     loc_1800078B6
0x1800077cf  mov     r15, [rsp+288h+var_248]
0x1800077d4  mov     rax, [r15+18h]
0x1800077d8  cmp     qword ptr [rax+30h], 0
0x1800077dd  jnz     loc_1800078ED
0x1800077e3  mov     rcx, [rdi+68h]; void *
0x1800077e7  call    UbpmQueueConsumerClose
0x1800077ec  mov     rcx, [rdi]
0x1800077ef  cmp     [rcx+8], rdi
0x1800077f3  jnz     short loc_180007855
0x1800077f5  mov     rax, [rdi+8]
0x1800077f9  cmp     [rax], rdi
0x1800077fc  jnz     short loc_180007855
0x1800077fe  mov     [rax], rcx
0x180007801  mov     [rcx+8], rax
0x180007805  mov     rcx, rdi
0x180007808  mov     [rdi+8], rdi
0x18000780c  mov     [rdi], rdi
0x18000780f  call    UBPM_MIDL_user_free
0x180007814  mov     r12, [rsp+288h+var_250]
0x180007819  mov     rdi, rbp
0x18000781c  cmp     rbp, rbx
0x18000781f  jnz     loc_180007710
0x180007825  cmp     r12, 0FFFFFFFFFFFFFFFFh
0x180007829  jnz     loc_180007930
0x18000782f  mov     r14d, [rsp+288h+var_258]
0x180007834  lea     r13, WPP_GLOBAL_Control
0x18000783b  jmp     loc_1800075C5
0x180007840  cmp     r12, rax
0x180007843  cmovnb  r12, rax
0x180007847  mov     [rsp+288h+var_250], r12
0x18000784c  lea     r14, WPP_GLOBAL_Control
0x180007853  jmp     short loc_180007819
0x180007855  mov     ecx, 3
0x18000785a  int     29h; Win8: RtlFailFast(ecx)
0x18000785c  mov     rax, [r14]
0x18000785f  cmp     [rax+8], r14
0x180007863  jnz     short loc_180007855
0x180007865  mov     rcx, [r14+8]
0x180007869  cmp     [rcx], r14
0x18000786c  jnz     short loc_180007855
0x18000786e  mov     [rcx], rax
0x180007871  mov     [rax+8], rcx
0x180007875  mov     rcx, r14
0x180007878  mov     [r14+8], r14
0x18000787c  mov     [r14], r14
0x18000787f  call    UBPM_MIDL_user_free
0x180007884  mov     r13b, 1
0x180007887  jmp     short loc_1800078A7
0x180007889  mov     r15, [r14]
0x18000788c  test    r12, r12
0x18000788f  jz      short loc_1800078AE
0x180007891  lea     rdx, [r14+10h]; Uuid2
0x180007895  mov     rcx, r12; Uuid1
0x180007898  lea     r8, [rsp+288h+Status]; Status
0x18000789d  call    cs:__imp_UuidEqual
0x1800078a3  test    eax, eax
0x1800078a5  jnz     short loc_18000785C
0x1800078a7  lea     rax, g_leQueuedSerialActionsListHead
0x1800078ae  mov     r14, r15
0x1800078b1  jmp     loc_180007792
0x1800078b6  mov     rcx, [rcx+10h]
0x1800078ba  lea     rax, aNotRemoved; "Not removed"
0x1800078c1  test    r13b, r13b
0x1800078c4  mov     dword ptr [rsp+288h+lpString2], 0
0x1800078cc  lea     r9, aRemoved; "Removed"
0x1800078d3  mov     edx, 5Fh ; '_'
0x1800078d8  cmovz   r9, rax
0x1800078dc  lea     r8, WPP_dcdc688f20ff37c56e3e77310b95cc70_Traceguids
0x1800078e3  call    WPP_SF_Sd
0x1800078e8  jmp     loc_1800077CF
0x1800078ed  lea     rcx, g_MaintenanceLaunchLock
0x1800078f4  call    cs:__imp_RtlAcquireSRWLockExclusive
0x1800078fa  call    cs:__imp_GetCurrentThreadId
0x180007900  mov     r8b, 2
0x180007903  mov     rdx, rdi
0x180007906  mov     rcx, r15
0x180007909  mov     cs:dword_18004CEE8, eax
0x18000790f  call    UbpmpMaintenanceTaskStoppedCallout
0x180007914  lea     rcx, g_MaintenanceLaunchLock
0x18000791b  mov     cs:dword_18004CEE8, 0
0x180007925  call    cs:__imp_RtlReleaseSRWLockExclusive
0x18000792b  jmp     loc_1800077E3
0x180007930  mov     rcx, cs:WPP_GLOBAL_Control
0x180007937  cmp     rcx, r14
0x18000793a  jz      short loc_180007958
0x18000793c  test    byte ptr [rcx+1Ch], 4
0x180007940  jz      short loc_180007958
0x180007942  mov     rcx, [rcx+10h]
0x180007946  mov     edx, 83h
0x18000794b  mov     r9, r12
0x18000794e  mov     [rsp+288h+lpString2], rsi
0x180007953  call    WPP_SF_ii
0x180007958  mov     rcx, [r15+120h]; void *
0x18000795f  sub     r12, rsi
0x180007962  mov     edx, 1388h
0x180007967  cmp     r12, rdx
0x18000796a  cmova   rdx, r12; unsigned __int64
0x18000796e  xor     r8d, r8d; int
0x180007971  call    ?UbpmUtilsSetTimerContext@@YAXPEAX_KH@Z; UbpmUtilsSetTimerContext(void *,unsigned __int64,int)
0x180007976  mov     r14d, [rsp+288h+var_258]
0x18000797b  jmp     loc_1800075F3
```
