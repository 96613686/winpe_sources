# UbpmpExecutionTimeLimitCallback

- ea: `0x180007ec0`
- end: `0x18000842a`
- name: `UbpmpExecutionTimeLimitCallback`
- size: `1386`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180011a90`

## callees

- `0x180003368`
- `0x180005320`
- `0x180007ec0`
- `0x180008430`
- `0x180008720`
- `0x180008920`
- `0x18000a9ac`
- `0x18000fbf0`
- `0x18001af64`
- `0x1800281f8`
- `0x18002d1fc`
- `0x180030d58`
- `0x180035184`
- `0x180036c60`
- `0x180040260`

## import_xrefs

- `ntdll!RtlReleaseSRWLockShared` at `0x180007fd8`
- `ntdll!RtlReleaseSRWLockShared` at `0x180007fd8`
- `ntdll!RtlAcquireSRWLockShared` at `0x180007f5c`
- `ntdll!RtlAcquireSRWLockShared` at `0x180007f5c`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180008110`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x1800081f2`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18000838c`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180008110`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x1800081f2`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18000838c`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180008063`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180008238`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800083c9`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180008063`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180008238`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800083c9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000811c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800081fe`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180008398`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000811c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800081fe`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180008398`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180008047`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180008047`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180008007`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180008007`
- `RPCRT4!UuidEqual` at `0x18000832f`
- `RPCRT4!UuidEqual` at `0x18000832f`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800080eb`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800080eb`

## string_xrefs

- `0x1800080c4`: `NT TASK`
- `0x180008364`: `Removed`
- `0x180008352`: `Not removed`

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
  __int64 v23; // rdx
  __int64 v24; // r8
  __int64 v25; // r9
  __int64 *v26; // rcx
  __int64 **v27; // rax
  UUID *v28; // rax
  UUID **v29; // rcx
  UUID *v30; // r15
  __int64 v31; // rdx
  __int64 v32; // r8
  __int64 v33; // r9
  const wchar_t *v34; // r9
  DWORD v35; // eax
  __int64 v36; // r8
  unsigned __int64 v37; // r12
  unsigned __int64 v38; // rdx
  int v39; // [rsp+30h] [rbp-258h]
  RPC_STATUS Status; // [rsp+34h] [rbp-254h] BYREF
  __int64 v41; // [rsp+38h] [rbp-250h]
  __int64 v42; // [rsp+40h] [rbp-248h]
  unsigned __int16 v43[256]; // [rsp+50h] [rbp-238h] BYREF

  if ( (a2 & 4) == 0 )
  {
    v3 = 0;
    v42 = a1;
    v4 = a1;
    if ( a3 )
      v3 = a3;
    v39 = v3;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_S(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        130,
        WPP_dd0be36be19438d0c9cf63f3ad92ceae_Traceguids,
        *(_QWORD *)(*(_QWORD *)(a1 + 24) + 8LL));
    if ( !(unsigned int)UbpmConsumerIncPendingActions(v4) )
    {
      v5 = -1;
      v41 = -1;
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
      v9 = v43;
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
              v41 = v5;
            }
            else
            {
              UbpmpActionTerminate(v13[3], v13[4], v13 + 5, 0);
              ReportTaskEvent(v19, &STOPPING_ON_TIMEOUT, v43, (const struct _GUID *)((char *)v13 + 52));
              Status = 0;
              v20 = 0;
              *(_OWORD *)(v4 + 272) = 0;
              RtlAcquireSRWLockExclusive(&g_QueuedSerialActionsLock);
              CurrentThreadId = GetCurrentThreadId();
              v22 = (UUID *)g_leQueuedSerialActionsListHead;
              dword_18004FFA0 = CurrentThreadId;
              while ( v22 != (UUID *)&g_leQueuedSerialActionsListHead )
              {
                v30 = *(UUID **)&v22->Data1;
                if ( v13 != (__int64 *)-52LL && UuidEqual((UUID *)((char *)v13 + 52), v22 + 1, &Status) )
                {
                  v28 = *(UUID **)&v22->Data1;
                  if ( *(UUID **)(*(_QWORD *)&v22->Data1 + 8LL) != v22 )
                    goto LABEL_50;
                  v29 = *(UUID ***)v22->Data4;
                  if ( *v29 != v22 )
                    goto LABEL_50;
                  *v29 = v28;
                  *(_QWORD *)v28->Data4 = v29;
                  *(_QWORD *)v22->Data4 = v22;
                  *(_QWORD *)&v22->Data1 = v22;
                  UBPM_MIDL_user_free(v22, v31, v32, v33);
                  v20 = 1;
                }
                v22 = v30;
              }
              dword_18004FFA0 = 0;
              RtlReleaseSRWLockExclusive(&g_QueuedSerialActionsLock);
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
              {
                v34 = L"Removed";
                if ( !v20 )
                  v34 = L"Not removed";
                WPP_SF_Sd(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  95,
                  (unsigned int)WPP_dcdc688f20ff37c56e3e77310b95cc70_Traceguids,
                  (_DWORD)v34,
                  0);
              }
              v4 = v42;
              if ( *(_QWORD *)(*(_QWORD *)(v42 + 24) + 48LL) )
              {
                RtlAcquireSRWLockExclusive(&g_MaintenanceLaunchLock);
                v35 = GetCurrentThreadId();
                LOBYTE(v36) = 2;
                dword_18004FFE8 = v35;
                UbpmpMaintenanceTaskStoppedCallout(v4, v13, v36);
                dword_18004FFE8 = 0;
                RtlReleaseSRWLockExclusive(&g_MaintenanceLaunchLock);
              }
              UbpmQueueConsumerClose((void *)v13[13]);
              v26 = (__int64 *)*v13;
              if ( *(__int64 **)(*v13 + 8) != v13 || (v27 = (__int64 **)v13[1], *v27 != v13) )
LABEL_50:
                __fastfail(3u);
              *v27 = v26;
              v26[1] = (__int64)v27;
              v13[1] = (__int64)v13;
              *v13 = (__int64)v13;
              UBPM_MIDL_user_free(v13, v23, v24, v25);
              v5 = v41;
            }
          }
          v13 = v18;
        }
        while ( v18 != v12 );
        if ( v5 != -1 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
            WPP_SF_ii(*((_QWORD *)WPP_GLOBAL_Control + 2), 131, v15, v5, TickCount64);
          v37 = v5 - TickCount64;
          v38 = 5000;
          if ( v37 > 0x1388 )
            v38 = v37;
          UbpmUtilsSetTimerContext(*(void **)(v4 + 288), v38, 0);
          v3 = v39;
          goto LABEL_22;
        }
        v3 = v39;
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
0x180007ec0  test    dl, 4
0x180007ec3  jnz     locret_1800080C2
0x180007ec9  push    r14
0x180007ecb  push    r15
0x180007ecd  sub     rsp, 278h
0x180007ed4  mov     rax, cs:__security_cookie
0x180007edb  xor     rax, rsp
0x180007ede  mov     [rsp+288h+var_38], rax
0x180007ee6  xor     r14d, r14d
0x180007ee9  mov     [rsp+288h+var_248], rcx
0x180007eee  test    r8, r8
0x180007ef1  mov     [rsp+288h+var_28], r13
0x180007ef9  mov     r15, rcx
0x180007efc  cmovnz  r14d, r8d
0x180007f00  mov     [rsp+288h+var_258], r14d
0x180007f05  mov     rcx, cs:WPP_GLOBAL_Control
0x180007f0c  lea     r13, WPP_GLOBAL_Control
0x180007f13  cmp     rcx, r13
0x180007f16  jnz     loc_180008134
0x180007f1c  mov     rcx, r15
0x180007f1f  call    UbpmConsumerIncPendingActions
0x180007f24  test    eax, eax
0x180007f26  jnz     loc_18000809F
0x180007f2c  mov     [rsp+288h+arg_8], rbx
0x180007f34  lea     rcx, [r15+30h]
0x180007f38  mov     [rsp+288h+arg_18], rsi
0x180007f40  mov     [rsp+288h+var_18], rdi
0x180007f48  mov     [rsp+288h+var_20], r12
0x180007f50  mov     r12, 0FFFFFFFFFFFFFFFFh
0x180007f57  mov     [rsp+288h+var_250], r12
0x180007f5c  call    cs:__imp_RtlAcquireSRWLockShared
0x180007f63  nop     dword ptr [rax+rax+00h]
0x180007f68  mov     rbx, [r15+18h]
0x180007f6c  mov     rbx, [rbx+8]
0x180007f70  test    rbx, rbx
0x180007f73  jz      short loc_180007F93
0x180007f75  mov     rax, r12
0x180007f78  nop     dword ptr [rax+rax+00000000h]
0x180007f80  inc     rax
0x180007f83  cmp     word ptr [rbx+rax*2], 0
0x180007f88  jnz     short loc_180007F80
0x180007f8a  cmp     eax, 8
0x180007f8d  ja      loc_1800080C4
0x180007f93  mov     ecx, 7FFFFFFEh
0x180007f98  lea     rdx, [rsp+288h+var_238]
0x180007f9d  mov     r8d, 100h
0x180007fa3  test    rcx, rcx
0x180007fa6  jz      short loc_180007FC4
0x180007fa8  movzx   eax, word ptr [rbx]
0x180007fab  test    ax, ax
0x180007fae  jz      short loc_180007FC4
0x180007fb0  mov     [rdx], ax
0x180007fb3  add     rbx, 2
0x180007fb7  add     rdx, 2
0x180007fbb  dec     rcx
0x180007fbe  sub     r8, 1
0x180007fc2  jnz     short loc_180007FA3
0x180007fc4  test    r8, r8
0x180007fc7  lea     rcx, [rdx-2]
0x180007fcb  cmovnz  rcx, rdx
0x180007fcf  xor     eax, eax
0x180007fd1  mov     [rcx], ax
0x180007fd4  lea     rcx, [r15+30h]
0x180007fd8  call    cs:__imp_RtlReleaseSRWLockShared
0x180007fdf  nop     dword ptr [rax+rax+00h]
0x180007fe4  test    r14d, r14d
0x180007fe7  jz      loc_180008109
0x180007fed  mov     rcx, r15
0x180007ff0  mov     [rsp+288h+arg_10], rbp
0x180007ff8  call    UbpmpActionContextCleanup
0x180007ffd  lea     rbx, [r15+0E0h]
0x180008004  mov     rdi, [rbx]
0x180008007  call    cs:__imp_GetTickCount64
0x18000800e  nop     dword ptr [rax+rax+00h]
0x180008013  mov     rsi, rax
0x180008016  cmp     rdi, rbx
0x180008019  jnz     loc_180008190
0x18000801f  mov     rcx, cs:WPP_GLOBAL_Control
0x180008026  cmp     rcx, r13
0x180008029  jnz     loc_180008160
0x18000802f  mov     rcx, [r15+120h]
0x180008036  test    rcx, rcx
0x180008039  jz      short loc_180008053
0x18000803b  mov     rcx, [rcx+28h]; pti
0x18000803f  xor     r9d, r9d; msWindowLength
0x180008042  xor     r8d, r8d; msPeriod
0x180008045  xor     edx, edx; pftDueTime
0x180008047  call    cs:__imp_SetThreadpoolTimer
0x18000804e  nop     dword ptr [rax+rax+00h]
0x180008053  test    r14d, r14d
0x180008056  jnz     short loc_18000806F
0x180008058  lea     rcx, [r15+0D0h]
0x18000805f  mov     [rcx+8], r14d
0x180008063  call    cs:__imp_RtlReleaseSRWLockExclusive
0x18000806a  nop     dword ptr [rax+rax+00h]
0x18000806f  mov     rcx, r15
0x180008072  call    UbpmConsumerDecPendingActions
0x180008077  mov     rbp, [rsp+288h+arg_10]
0x18000807f  mov     rdi, [rsp+288h+var_18]
0x180008087  mov     rsi, [rsp+288h+arg_18]
0x18000808f  mov     r12, [rsp+288h+var_20]
0x180008097  mov     rbx, [rsp+288h+arg_8]
0x18000809f  mov     r13, [rsp+288h+var_28]
0x1800080a7  mov     rcx, [rsp+288h+var_38]
0x1800080af  xor     rcx, rsp; StackCookie
0x1800080b2  call    __security_check_cookie
0x1800080b7  add     rsp, 278h
0x1800080be  pop     r15
0x1800080c0  pop     r14
0x1800080c2  retn
0x1800080c4  lea     rax, String2; "NT TASK"
0x1800080cb  mov     [rsp+288h+cchCount2], 7; cchCount2
0x1800080d3  mov     r9d, 7; cchCount1
0x1800080d9  mov     [rsp+288h+lpString2], rax; lpString2
0x1800080de  mov     r8, rbx; lpString1
0x1800080e1  mov     edx, 1; dwCmpFlags
0x1800080e6  mov     ecx, 7Fh; Locale
0x1800080eb  call    cs:__imp_CompareStringW
0x1800080f2  nop     dword ptr [rax+rax+00h]
0x1800080f7  cmp     eax, 2
0x1800080fa  jnz     loc_180007F93
0x180008100  add     rbx, 0Eh
0x180008104  jmp     loc_180007F93
0x180008109  lea     rcx, [r15+0D0h]
0x180008110  call    cs:__imp_RtlAcquireSRWLockExclusive
0x180008117  nop     dword ptr [rax+rax+00h]
0x18000811c  call    cs:__imp_GetCurrentThreadId
0x180008123  nop     dword ptr [rax+rax+00h]
0x180008128  mov     [r15+0D8h], eax
0x18000812f  jmp     loc_180007FED
0x180008134  test    byte ptr [rcx+1Ch], 4
0x180008138  jz      loc_180007F1C
0x18000813e  mov     r9, [r15+18h]
0x180008142  lea     r8, WPP_dd0be36be19438d0c9cf63f3ad92ceae_Traceguids
0x180008149  mov     rcx, [rcx+10h]
0x18000814d  mov     edx, 82h
0x180008152  mov     r9, [r9+8]
0x180008156  call    WPP_SF_S
0x18000815b  jmp     loc_180007F1C
0x180008160  test    byte ptr [rcx+1Ch], 4
0x180008164  jz      loc_18000802F
0x18000816a  mov     rcx, [rcx+10h]
0x18000816e  lea     r8, WPP_dd0be36be19438d0c9cf63f3ad92ceae_Traceguids
0x180008175  mov     edx, 84h
0x18000817a  call    WPP_SF_
0x18000817f  jmp     loc_18000802F
0x180008190  mov     rax, [rdi+48h]
0x180008194  mov     rbp, [rdi]
0x180008197  test    rax, rax
0x18000819a  jz      loc_1800082DE
0x1800081a0  cmp     rax, rsi
0x1800081a3  ja      loc_1800082D2
0x1800081a9  mov     rdx, [rdi+20h]
0x1800081ad  lea     r8, [rdi+28h]
0x1800081b1  mov     rcx, [rdi+18h]
0x1800081b5  xor     r9d, r9d
0x1800081b8  call    UbpmpActionTerminate
0x1800081bd  lea     r12, [rdi+34h]
0x1800081c1  mov     r9, r12; struct _GUID *
0x1800081c4  lea     r8, [rsp+288h+var_238]; unsigned __int16 *
0x1800081c9  lea     rdx, STOPPING_ON_TIMEOUT; struct _EVENT_DESCRIPTOR *
0x1800081d0  call    ?ReportTaskEvent@@YAKPEAXPEBU_EVENT_DESCRIPTOR@@PEBGPEBU_GUID@@@Z; ReportTaskEvent(void *,_EVENT_DESCRIPTOR const *,ushort const *,_GUID const *)
0x1800081d5  xorps   xmm0, xmm0
0x1800081d8  mov     [rsp+288h+Status], 0
0x1800081e0  lea     rcx, g_QueuedSerialActionsLock
0x1800081e7  xor     r13b, r13b
0x1800081ea  movups  xmmword ptr [r15+110h], xmm0
0x1800081f2  call    cs:__imp_RtlAcquireSRWLockExclusive
0x1800081f9  nop     dword ptr [rax+rax+00h]
0x1800081fe  call    cs:__imp_GetCurrentThreadId
0x180008205  nop     dword ptr [rax+rax+00h]
0x18000820a  mov     r14, cs:g_leQueuedSerialActionsListHead
0x180008211  mov     cs:dword_18004FFA0, eax
0x180008217  lea     rax, g_leQueuedSerialActionsListHead
0x18000821e  cmp     r14, rax
0x180008221  jnz     loc_18000831B
0x180008227  lea     rcx, g_QueuedSerialActionsLock
0x18000822e  mov     cs:dword_18004FFA0, 0
0x180008238  call    cs:__imp_RtlReleaseSRWLockExclusive
0x18000823f  nop     dword ptr [rax+rax+00h]
0x180008244  mov     rcx, cs:WPP_GLOBAL_Control
0x18000824b  lea     r14, WPP_GLOBAL_Control
0x180008252  cmp     rcx, r14
0x180008255  jz      short loc_180008261
0x180008257  test    byte ptr [rcx+1Ch], 20h
0x18000825b  jnz     loc_18000834E
0x180008261  mov     r15, [rsp+288h+var_248]
0x180008266  mov     rax, [r15+18h]
0x18000826a  cmp     qword ptr [rax+30h], 0
0x18000826f  jnz     loc_180008385
0x180008275  mov     rcx, [rdi+68h]; void *
0x180008279  call    UbpmQueueConsumerClose
0x18000827e  mov     rcx, [rdi]
0x180008281  cmp     [rcx+8], rdi
0x180008285  jnz     short loc_1800082E7
0x180008287  mov     rax, [rdi+8]
0x18000828b  cmp     [rax], rdi
0x18000828e  jnz     short loc_1800082E7
0x180008290  mov     [rax], rcx
0x180008293  mov     [rcx+8], rax
0x180008297  mov     rcx, rdi
0x18000829a  mov     [rdi+8], rdi
0x18000829e  mov     [rdi], rdi
0x1800082a1  call    UBPM_MIDL_user_free
0x1800082a6  mov     r12, [rsp+288h+var_250]
0x1800082ab  mov     rdi, rbp
0x1800082ae  cmp     rbp, rbx
0x1800082b1  jnz     loc_180008190
0x1800082b7  cmp     r12, 0FFFFFFFFFFFFFFFFh
0x1800082bb  jnz     loc_1800083DA
0x1800082c1  mov     r14d, [rsp+288h+var_258]
0x1800082c6  lea     r13, WPP_GLOBAL_Control
0x1800082cd  jmp     loc_18000801F
0x1800082d2  cmp     r12, rax
0x1800082d5  cmovnb  r12, rax
0x1800082d9  mov     [rsp+288h+var_250], r12
0x1800082de  lea     r14, WPP_GLOBAL_Control
0x1800082e5  jmp     short loc_1800082AB
0x1800082e7  mov     ecx, 3
0x1800082ec  int     29h; Win8: RtlFailFast(ecx)
0x1800082ee  mov     rax, [r14]
0x1800082f1  cmp     [rax+8], r14
0x1800082f5  jnz     short loc_1800082E7
0x1800082f7  mov     rcx, [r14+8]
0x1800082fb  cmp     [rcx], r14
0x1800082fe  jnz     short loc_1800082E7
0x180008300  mov     [rcx], rax
0x180008303  mov     [rax+8], rcx
0x180008307  mov     rcx, r14
0x18000830a  mov     [r14+8], r14
0x18000830e  mov     [r14], r14
0x180008311  call    UBPM_MIDL_user_free
0x180008316  mov     r13b, 1
0x180008319  jmp     short loc_18000833F
0x18000831b  mov     r15, [r14]
0x18000831e  test    r12, r12
0x180008321  jz      short loc_180008346
0x180008323  lea     rdx, [r14+10h]; Uuid2
0x180008327  mov     rcx, r12; Uuid1
0x18000832a  lea     r8, [rsp+288h+Status]; Status
0x18000832f  call    cs:__imp_UuidEqual
0x180008336  nop     dword ptr [rax+rax+00h]
0x18000833b  test    eax, eax
0x18000833d  jnz     short loc_1800082EE
0x18000833f  lea     rax, g_leQueuedSerialActionsListHead
0x180008346  mov     r14, r15
0x180008349  jmp     loc_18000821E
0x18000834e  mov     rcx, [rcx+10h]
0x180008352  lea     rax, aNotRemoved; "Not removed"
0x180008359  test    r13b, r13b
0x18000835c  mov     dword ptr [rsp+288h+lpString2], 0
0x180008364  lea     r9, aRemoved; "Removed"
0x18000836b  mov     edx, 5Fh ; '_'
0x180008370  cmovz   r9, rax
0x180008374  lea     r8, WPP_dcdc688f20ff37c56e3e77310b95cc70_Traceguids
0x18000837b  call    WPP_SF_Sd
0x180008380  jmp     loc_180008261
0x180008385  lea     rcx, g_MaintenanceLaunchLock
0x18000838c  call    cs:__imp_RtlAcquireSRWLockExclusive
0x180008393  nop     dword ptr [rax+rax+00h]
0x180008398  call    cs:__imp_GetCurrentThreadId
0x18000839f  nop     dword ptr [rax+rax+00h]
0x1800083a4  mov     r8b, 2
0x1800083a7  mov     rdx, rdi
0x1800083aa  mov     rcx, r15
0x1800083ad  mov     cs:dword_18004FFE8, eax
0x1800083b3  call    UbpmpMaintenanceTaskStoppedCallout
0x1800083b8  lea     rcx, g_MaintenanceLaunchLock
0x1800083bf  mov     cs:dword_18004FFE8, 0
0x1800083c9  call    cs:__imp_RtlReleaseSRWLockExclusive
0x1800083d0  nop     dword ptr [rax+rax+00h]
0x1800083d5  jmp     loc_180008275
0x1800083da  mov     rcx, cs:WPP_GLOBAL_Control
0x1800083e1  cmp     rcx, r14
0x1800083e4  jz      short loc_180008402
0x1800083e6  test    byte ptr [rcx+1Ch], 4
0x1800083ea  jz      short loc_180008402
0x1800083ec  mov     rcx, [rcx+10h]
0x1800083f0  mov     edx, 83h
0x1800083f5  mov     r9, r12
0x1800083f8  mov     [rsp+288h+lpString2], rsi
0x1800083fd  call    WPP_SF_ii
0x180008402  mov     rcx, [r15+120h]; void *
0x180008409  sub     r12, rsi
0x18000840c  mov     edx, 1388h
0x180008411  cmp     r12, rdx
0x180008414  cmova   rdx, r12; unsigned __int64
0x180008418  xor     r8d, r8d; int
0x18000841b  call    ?UbpmUtilsSetTimerContext@@YAXPEAX_KH@Z; UbpmUtilsSetTimerContext(void *,unsigned __int64,int)
0x180008420  mov     r14d, [rsp+288h+var_258]
0x180008425  jmp     loc_180008053
```
