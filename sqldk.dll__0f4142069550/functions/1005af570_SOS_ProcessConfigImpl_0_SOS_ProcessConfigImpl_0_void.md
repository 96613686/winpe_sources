# SOS_ProcessConfigImpl<0>::SOS_ProcessConfigImpl<0>(void)

- ea: `0x1005af570`
- end: `0x1005afbf2`
- name: `??0?$SOS_ProcessConfigImpl@$0A@@@QEAA@XZ`
- size: `1666`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1004416e0`

## callees

- `0x1005af570`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x1005af68c`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x1005afa8d`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x1005afb36`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x1005afb6b`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x1005afbb0`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x1005af68c`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x1005afa8d`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x1005afb36`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x1005afb6b`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x1005afbb0`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x1005af698`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x1005afa99`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x1005afb42`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x1005afb77`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x1005afbbc`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x1005af698`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x1005afa99`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x1005afb42`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x1005afb77`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x1005afbbc`

## string_xrefs

- `0x1005af643`: `MEMORYCLERK_SECURITYAPI`
- `0x1005af738`: `SOS_SYSTHREAD`
- `0x1005af759`: `SOS_ACTIVEDESCRIPTOR`
- `0x1005af74e`: `SOS_TASK`
- `0x1005af764`: `SOS_ACTIVE_DECOMMIT_DESCRIPTOR`
- `0x1005af77a`: `SOS_MINITHREAD`
- `0x1005af7c7`: `SOS_CACHESTORE`
- `0x1005af7dd`: `SOS_ABORT_TASK`
- `0x1005af7d2`: `SOS_BLOCKDESCRIPTORBUCKET`
- `0x1005af80f`: `SOS_CACHESTORE_CLOCK`
- `0x1005af847`: `SOS_SYSTHREAD_DISPATCHER`

## pseudocode

```c
__int64 __fastcall SOS_ProcessConfigImpl<0>::SOS_ProcessConfigImpl<0>(__int64 a1)
{
  __int128 *v2; // rbx
  __int64 v3; // rsi
  __int64 v4; // r14
  __int64 v5; // r15
  __int128 *v6; // rax
  __int64 v7; // rcx
  __int128 v8; // xmm0
  __int128 v9; // xmm1
  __int128 v10; // xmm0
  __int128 v11; // xmm1
  __int128 v12; // xmm0
  __int128 v13; // xmm1
  __int128 v14; // xmm0
  __int128 v15; // xmm1
  __int128 v16; // xmm1
  __int128 v17; // xmm0
  __int128 v18; // xmm1
  __int128 v19; // xmm0
  __int128 v20; // xmm1
  __int128 v22; // [rsp+20h] [rbp-E0h]
  __int128 v23; // [rsp+20h] [rbp-E0h]
  __int128 v24; // [rsp+30h] [rbp-D0h]
  __int128 v25; // [rsp+30h] [rbp-D0h]
  __int128 v26; // [rsp+40h] [rbp-C0h]
  __int128 v27; // [rsp+40h] [rbp-C0h]
  __int128 v28; // [rsp+50h] [rbp-B0h]
  __int128 v29; // [rsp+60h] [rbp-A0h]
  __int128 v30; // [rsp+70h] [rbp-90h]
  __int128 v31; // [rsp+80h] [rbp-80h]
  __int128 v32; // [rsp+90h] [rbp-70h]
  _QWORD v33[60]; // [rsp+B0h] [rbp-50h] BYREF

  *(_DWORD *)a1 = 10;
  *(_DWORD *)(a1 + 4) = 11;
  *(_QWORD *)(a1 + 8) = a1 + 88;
  *(_WORD *)(a1 + 16) = 59;
  v2 = (__int128 *)(a1 + 184);
  *(_QWORD *)(a1 + 24) = a1 + 184;
  *(_WORD *)(a1 + 40) = 4;
  v3 = a1 + 704;
  *(_QWORD *)(a1 + 32) = a1 + 704;
  *(_QWORD *)(a1 + 64) = 0;
  v4 = a1 + 664;
  *(_QWORD *)(a1 + 72) = 0;
  v5 = a1 + 764;
  *(_QWORD *)(a1 + 80) = 0;
  *(_QWORD *)&v22 = L"MEMORYCLERK_XE_BUFFER";
  *((_QWORD *)&v22 + 1) = L"MEMORYCLERK_HOST";
  *(_QWORD *)&v24 = L"MEMORYCLERK_SOSNODE";
  *((_QWORD *)&v24 + 1) = L"MEMORYCLERK_SOSOS";
  *(_QWORD *)&v26 = L"MEMORYCLERK_SOSMEMMANAGER";
  *((_QWORD *)&v26 + 1) = L"MEMORYCLERK_TEST";
  *(_QWORD *)&v28 = L"MEMORYCLERK_XE";
  *((_QWORD *)&v28 + 1) = L"MEMORYCLERK_SECURITYAPI";
  *(_QWORD *)&v29 = L"MEMORYCLERK_RTLHEAP";
  *((_QWORD *)&v29 + 1) = L"MEMORYCLERK_BITMAP";
  *(_QWORD *)&v30 = L"MEMORYCLERK_SQLLAST";
  *((_QWORD *)&v30 + 1) = L"MEMORYCLERK_LAST";
  *(_QWORD *)(a1 + 48) = a1 + 664;
  *(_QWORD *)(a1 + 56) = a1 + 764;
  if ( a1 == -88 )
  {
    *_errno() = 22;
    _invalid_parameter_noinfo();
  }
  else
  {
    *(_OWORD *)(a1 + 88) = v22;
    *(_OWORD *)(a1 + 104) = v24;
    *(_OWORD *)(a1 + 120) = v26;
    *(_OWORD *)(a1 + 136) = v28;
    *(_OWORD *)(a1 + 152) = v29;
    *(_OWORD *)(a1 + 168) = v30;
  }
  v33[0] = "GLOBAL_TRACE_FLAGS";
  v33[1] = "SOS_OBJECT_POOL";
  v33[2] = "MEM_MGR";
  v33[3] = "LOG_RG_GOVERNOR";
  v33[4] = "RG_TIMER";
  v33[5] = "SEQUENCED_OBJECT";
  v33[6] = "BLOCKER_ENUM";
  v33[7] = "SPL_DISPATCHER_QUEUE";
  v33[8] = "SPL_SOS_DISPATCHER";
  v33[9] = "SOS_SYSTHREAD";
  v33[10] = "SOS_SCHEDULER_TIMER";
  v33[11] = "SOS_TASK";
  v33[12] = "SOS_ACTIVEDESCRIPTOR";
  v33[13] = "SOS_ACTIVE_DECOMMIT_DESCRIPTOR";
  v33[14] = "SOS_VM_LOW";
  v33[15] = "SOS_MINITHREAD";
  v33[16] = "GLOBAL_SCHEDULER_LIST";
  v33[17] = "SOS_NODE";
  v33[18] = "SOS_SCHEDULER";
  v33[19] = "SOS_TLIST";
  v33[20] = "SOS_RESOURCE_CLERK_LIST";
  v33[21] = "SOS_SELIST_SIZED_SLOCK";
  v33[22] = "SOS_CACHESTORE";
  v33[23] = "SOS_BLOCKDESCRIPTORBUCKET";
  v33[24] = "SOS_ABORT_TASK";
  v33[25] = "SOS_SUSPEND_QUEUE";
  v33[26] = "SOS_SUSPEND_QUEUE_EXP";
  v33[27] = "SOS_WAITABLE_ADDRESS_HASHBUCKET";
  v33[28] = "SOS_CACHESTORE_CLOCK";
  v33[29] = "SOS_RINGBUFFER_RECORD";
  v33[30] = "SOS_WAIT_STATS";
  v33[31] = "SOS_OOM_CHECK";
  v33[32] = "SOS_SYSTHREAD_DISPATCHER";
  v33[33] = "SOS_CLOCKALG_INTERNODE_SYNC";
  v33[34] = "SOS_OBJECT_STORE";
  v33[35] = "SOS_LARGEPAGE_ALLOCATOR";
  v33[36] = "RESMANAGER";
  v33[37] = "SPL_DISPATCHER_LIST";
  v33[38] = "PARTITIONED_HEAP_FREE_LIST";
  v33[39] = "DELAYED_PARTITIONED_STACK";
  v33[40] = "SPL_XE_BUFFER_MGR";
  v33[41] = "SPL_XE_SESSION_EVENT_MGR";
  v33[42] = "SPL_XE_SESSION_TARGET_MGR";
  v33[43] = "SPL_XE_SESSION_MGR";
  v33[44] = "SPL_XE_NOTIFICATION_CALLBACK_LIST";
  v33[45] = "SPL_XE_DISPATCHER_QUEUE";
  v33[46] = "SOS_DEBUG_HOOK";
  v33[47] = "RESQUEUE";
  v33[48] = "SPL_NONYIELD_ANALYSIS";
  v33[49] = "SOS_BLOCKALLOCPARTIALLIST";
  v33[50] = "SOS_DESCDATABUFFERLIST";
  v33[51] = "DRTL_MODULEINFOLIST";
  v33[52] = "ETW_LOGGER_MANAGER";
  v33[53] = "TESTTEAM";
  v33[54] = "TESTTEAMTASTAS";
  v33[55] = "TESTTEAMEXPONENTIAL";
  v33[56] = "TESTTEAMEXPONENTIALTASTAS";
  v33[57] = "TESTTEAMREPORTINGOPTIONSCHECKUNUSED";
  v33[58] = "TESTTEAMREPORTINGOPTIONSCHECKCLOUDDB";
  v33[59] = "SOS_SYSTEM_SPL_LAST";
  *(_QWORD *)&v31 = "LOCK_RW_TEST";
  *((_QWORD *)&v31 + 1) = "LOCK_RW_AR";
  *(_QWORD *)&v32 = "LOCK_RW_GTL";
  *((_QWORD *)&v32 + 1) = "LOCK_RW_IORG_VOLUME_HT";
  *(_QWORD *)&v23 = 0x202020202020202LL;
  *((_QWORD *)&v23 + 1) = 0x202020202020202LL;
  *(_QWORD *)&v25 = 0x202020202020202LL;
  *((_QWORD *)&v25 + 1) = 0x202020202020202LL;
  *(_QWORD *)&v27 = 0x202020202020202LL;
  *((_QWORD *)&v27 + 1) = 0x202020202020202LL;
  if ( v2 )
  {
    v6 = (__int128 *)v33;
    v7 = 3;
    do
    {
      v2 += 8;
      v8 = *v6;
      v9 = v6[1];
      v6 += 8;
      *(v2 - 8) = v8;
      v10 = *(v6 - 6);
      *(v2 - 7) = v9;
      v11 = *(v6 - 5);
      *(v2 - 6) = v10;
      v12 = *(v6 - 4);
      *(v2 - 5) = v11;
      v13 = *(v6 - 3);
      *(v2 - 4) = v12;
      v14 = *(v6 - 2);
      *(v2 - 3) = v13;
      v15 = *(v6 - 1);
      *(v2 - 2) = v14;
      *(v2 - 1) = v15;
      --v7;
    }
    while ( v7 );
    v16 = v6[1];
    *v2 = *v6;
    v17 = v6[2];
    v2[1] = v16;
    v18 = v6[3];
    v2[2] = v17;
    v19 = v6[4];
    v2[3] = v18;
    v20 = v6[5];
    v2[4] = v19;
    v2[5] = v20;
  }
  else
  {
    *_errno() = 22;
    _invalid_parameter_noinfo();
  }
  if ( v4 )
  {
    *(_OWORD *)v4 = v31;
    *(_OWORD *)(v4 + 16) = v32;
    *(_QWORD *)(v4 + 32) = "SOS_SYSTEM_RW_SPL_LAST";
  }
  else
  {
    *_errno() = 22;
    _invalid_parameter_noinfo();
  }
  if ( v3 )
  {
    *(_OWORD *)v3 = v23;
    *(_OWORD *)(v3 + 16) = v25;
    *(_OWORD *)(v3 + 32) = v27;
    *(_QWORD *)(v3 + 48) = 0x202020202020202LL;
    *(_DWORD *)(v3 + 56) = 33619970;
  }
  else
  {
    *_errno() = 22;
    _invalid_parameter_noinfo();
  }
  if ( v5 )
  {
    *(_DWORD *)v5 = 33686018;
    *(_BYTE *)(v5 + 4) = 2;
  }
  else
  {
    *_errno() = 22;
    _invalid_parameter_noinfo();
  }
  return a1;
}

```

## disassembly

```asm
0x1005af570  mov     [rsp-8+arg_8], rbx
0x1005af575  mov     [rsp-8+arg_10], rsi
0x1005af57a  mov     [rsp-8+arg_18], rdi
0x1005af57f  push    rbp
0x1005af580  push    r14
0x1005af582  push    r15
0x1005af584  lea     rbp, [rsp-190h]
0x1005af58c  sub     rsp, 290h
0x1005af593  mov     rdi, rcx
0x1005af596  mov     dword ptr [rcx], 0Ah
0x1005af59c  lea     rax, [rcx+58h]
0x1005af5a0  mov     dword ptr [rcx+4], 0Bh
0x1005af5a7  mov     [rcx+8], rax
0x1005af5ab  mov     ecx, 3Bh ; ';'
0x1005af5b0  mov     [rdi+10h], cx
0x1005af5b4  lea     rbx, [rdi+0B8h]
0x1005af5bb  mov     ecx, 4
0x1005af5c0  mov     [rdi+18h], rbx
0x1005af5c4  mov     [rdi+28h], cx
0x1005af5c8  lea     rsi, [rdi+2C0h]
0x1005af5cf  xor     ecx, ecx
0x1005af5d1  mov     [rdi+20h], rsi
0x1005af5d5  mov     [rdi+40h], rcx
0x1005af5d9  lea     r14, [rdi+298h]
0x1005af5e0  mov     [rdi+48h], rcx
0x1005af5e4  lea     r15, [rdi+2FCh]
0x1005af5eb  mov     [rdi+50h], rcx
0x1005af5ef  lea     rcx, aMemoryclerkXeB; "MEMORYCLERK_XE_BUFFER"
0x1005af5f6  mov     qword ptr [rsp+2A0h+var_280], rcx
0x1005af5fb  lea     rcx, aMemoryclerkHos; "MEMORYCLERK_HOST"
0x1005af602  mov     qword ptr [rsp+2A0h+var_280+8], rcx
0x1005af607  lea     rcx, aMemoryclerkSos_1; "MEMORYCLERK_SOSNODE"
0x1005af60e  mov     qword ptr [rsp+2A0h+var_270], rcx
0x1005af613  lea     rcx, aMemoryclerkSos; "MEMORYCLERK_SOSOS"
0x1005af61a  mov     qword ptr [rsp+2A0h+var_270+8], rcx
0x1005af61f  lea     rcx, aMemoryclerkSos_0; "MEMORYCLERK_SOSMEMMANAGER"
0x1005af626  mov     qword ptr [rsp+2A0h+var_260], rcx
0x1005af62b  lea     rcx, aMemoryclerkTes; "MEMORYCLERK_TEST"
0x1005af632  mov     qword ptr [rsp+2A0h+var_260+8], rcx
0x1005af637  lea     rcx, aMemoryclerkXe; "MEMORYCLERK_XE"
0x1005af63e  mov     qword ptr [rsp+2A0h+var_250], rcx
0x1005af643  lea     rcx, aMemoryclerkSec; "MEMORYCLERK_SECURITYAPI"
0x1005af64a  mov     qword ptr [rsp+2A0h+var_250+8], rcx
0x1005af64f  lea     rcx, aMemoryclerkRtl; "MEMORYCLERK_RTLHEAP"
0x1005af656  mov     qword ptr [rsp+2A0h+var_240], rcx
0x1005af65b  lea     rcx, aMemoryclerkBit; "MEMORYCLERK_BITMAP"
0x1005af662  mov     qword ptr [rsp+2A0h+var_240+8], rcx
0x1005af667  lea     rcx, aMemoryclerkSql; "MEMORYCLERK_SQLLAST"
0x1005af66e  mov     qword ptr [rsp+2A0h+var_230], rcx
0x1005af673  lea     rcx, aMemoryclerkLas; "MEMORYCLERK_LAST"
0x1005af67a  mov     qword ptr [rsp+2A0h+var_230+8], rcx
0x1005af67f  mov     [rdi+30h], r14
0x1005af683  mov     [rdi+38h], r15
0x1005af687  test    rax, rax
0x1005af68a  jnz     short loc_1005AF6A0
0x1005af68c  call    cs:__imp__errno
0x1005af692  mov     dword ptr [rax], 16h
0x1005af698  call    cs:__imp__invalid_parameter_noinfo
0x1005af69e  jmp     short loc_1005AF6D5
0x1005af6a0  movaps  xmm0, [rsp+2A0h+var_280]
0x1005af6a5  movaps  xmm1, [rsp+2A0h+var_270]
0x1005af6aa  movups  xmmword ptr [rax], xmm0
0x1005af6ad  movaps  xmm0, [rsp+2A0h+var_260]
0x1005af6b2  movups  xmmword ptr [rax+10h], xmm1
0x1005af6b6  movaps  xmm1, [rsp+2A0h+var_250]
0x1005af6bb  movups  xmmword ptr [rax+20h], xmm0
0x1005af6bf  movaps  xmm0, [rsp+2A0h+var_240]
0x1005af6c4  movups  xmmword ptr [rax+30h], xmm1
0x1005af6c8  movaps  xmm1, [rsp+2A0h+var_230]
0x1005af6cd  movups  xmmword ptr [rax+40h], xmm0
0x1005af6d1  movups  xmmword ptr [rax+50h], xmm1
0x1005af6d5  lea     rax, aGlobalTraceFla_0; "GLOBAL_TRACE_FLAGS"
0x1005af6dc  mov     [rbp+1A0h+var_1F0], rax
0x1005af6e0  lea     rax, aSosObjectPool_0; "SOS_OBJECT_POOL"
0x1005af6e7  mov     [rbp+1A0h+var_1E8], rax
0x1005af6eb  lea     rax, aMemMgr_0; "MEM_MGR"
0x1005af6f2  mov     [rbp+1A0h+var_1E0], rax
0x1005af6f6  lea     rax, aLogRgGovernor_0; "LOG_RG_GOVERNOR"
0x1005af6fd  mov     [rbp+1A0h+var_1D8], rax
0x1005af701  lea     rax, aRgTimer; "RG_TIMER"
0x1005af708  mov     [rbp+1A0h+var_1D0], rax
0x1005af70c  lea     rax, aSequencedObjec; "SEQUENCED_OBJECT"
0x1005af713  mov     [rbp+1A0h+var_1C8], rax
0x1005af717  lea     rax, aBlockerEnum; "BLOCKER_ENUM"
0x1005af71e  mov     [rbp+1A0h+var_1C0], rax
0x1005af722  lea     rax, aSplDispatcherQ; "SPL_DISPATCHER_QUEUE"
0x1005af729  mov     [rbp+1A0h+var_1B8], rax
0x1005af72d  lea     rax, aSplSosDispatch; "SPL_SOS_DISPATCHER"
0x1005af734  mov     [rbp+1A0h+var_1B0], rax
0x1005af738  lea     rax, aSosSysthread_0; "SOS_SYSTHREAD"
0x1005af73f  mov     [rbp+1A0h+var_1A8], rax
0x1005af743  lea     rax, aSosSchedulerTi_0; "SOS_SCHEDULER_TIMER"
0x1005af74a  mov     [rbp+1A0h+var_1A0], rax
0x1005af74e  lea     rax, aSosTask; "SOS_TASK"
0x1005af755  mov     [rbp+1A0h+var_198], rax
0x1005af759  lea     rax, aSosActivedescr; "SOS_ACTIVEDESCRIPTOR"
0x1005af760  mov     [rbp+1A0h+var_190], rax
0x1005af764  lea     rax, aSosActiveDecom; "SOS_ACTIVE_DECOMMIT_DESCRIPTOR"
0x1005af76b  mov     [rbp+1A0h+var_188], rax
0x1005af76f  lea     rax, aSosVmLow; "SOS_VM_LOW"
0x1005af776  mov     [rbp+1A0h+var_180], rax
0x1005af77a  lea     rax, aSosMinithread_0; "SOS_MINITHREAD"
0x1005af781  mov     [rbp+1A0h+var_178], rax
0x1005af785  lea     rax, aGlobalSchedule; "GLOBAL_SCHEDULER_LIST"
0x1005af78c  mov     [rbp+1A0h+var_170], rax
0x1005af790  lea     rax, aSosNode; "SOS_NODE"
0x1005af797  mov     [rbp+1A0h+var_168], rax
0x1005af79b  lea     rax, aSosScheduler_0; "SOS_SCHEDULER"
0x1005af7a2  mov     [rbp+1A0h+var_160], rax
0x1005af7a6  lea     rax, aSosTlist_0; "SOS_TLIST"
0x1005af7ad  mov     [rbp+1A0h+var_158], rax
0x1005af7b1  lea     rax, aSosResourceCle; "SOS_RESOURCE_CLERK_LIST"
0x1005af7b8  mov     [rbp+1A0h+var_150], rax
0x1005af7bc  lea     rax, aSosSelistSized_0; "SOS_SELIST_SIZED_SLOCK"
0x1005af7c3  mov     [rbp+1A0h+var_148], rax
0x1005af7c7  lea     rax, aSosCachestore; "SOS_CACHESTORE"
0x1005af7ce  mov     [rbp+1A0h+var_140], rax
0x1005af7d2  lea     rax, aSosBlockdescri; "SOS_BLOCKDESCRIPTORBUCKET"
0x1005af7d9  mov     [rbp+1A0h+var_138], rax
0x1005af7dd  lea     rax, aSosAbortTask; "SOS_ABORT_TASK"
0x1005af7e4  mov     [rbp+1A0h+var_130], rax
0x1005af7e8  lea     rax, aSosSuspendQueu; "SOS_SUSPEND_QUEUE"
0x1005af7ef  mov     [rbp+1A0h+var_128], rax
0x1005af7f3  lea     rax, aSosSuspendQueu_1; "SOS_SUSPEND_QUEUE_EXP"
0x1005af7fa  mov     [rbp+1A0h+var_120], rax
0x1005af801  lea     rax, aSosWaitableAdd; "SOS_WAITABLE_ADDRESS_HASHBUCKET"
0x1005af808  mov     [rbp+1A0h+var_118], rax
0x1005af80f  lea     rax, aSosCachestoreC; "SOS_CACHESTORE_CLOCK"
0x1005af816  mov     [rbp+1A0h+var_110], rax
0x1005af81d  lea     rax, aSosRingbufferR; "SOS_RINGBUFFER_RECORD"
0x1005af824  mov     [rbp+1A0h+var_108], rax
0x1005af82b  lea     rax, aSosWaitStats; "SOS_WAIT_STATS"
0x1005af832  mov     [rbp+1A0h+var_100], rax
0x1005af839  lea     rax, aSosOomCheck; "SOS_OOM_CHECK"
0x1005af840  mov     [rbp+1A0h+var_F8], rax
0x1005af847  lea     rax, aSosSysthreadDi; "SOS_SYSTHREAD_DISPATCHER"
0x1005af84e  mov     [rbp+1A0h+var_F0], rax
0x1005af855  lea     rax, aSosClockalgInt_0; "SOS_CLOCKALG_INTERNODE_SYNC"
0x1005af85c  mov     [rbp+1A0h+var_E8], rax
0x1005af863  lea     rax, aSosObjectStore_0; "SOS_OBJECT_STORE"
0x1005af86a  mov     [rbp+1A0h+var_E0], rax
0x1005af871  lea     rax, aSosLargepageAl; "SOS_LARGEPAGE_ALLOCATOR"
0x1005af878  mov     [rbp+1A0h+var_D8], rax
0x1005af87f  lea     rax, aResmanager_0; "RESMANAGER"
0x1005af886  mov     [rbp+1A0h+var_D0], rax
0x1005af88d  lea     rax, aSplDispatcherL; "SPL_DISPATCHER_LIST"
0x1005af894  mov     [rbp+1A0h+var_C8], rax
0x1005af89b  lea     rax, aPartitionedHea_0; "PARTITIONED_HEAP_FREE_LIST"
0x1005af8a2  mov     [rbp+1A0h+var_C0], rax
0x1005af8a9  lea     rax, aDelayedPartiti; "DELAYED_PARTITIONED_STACK"
0x1005af8b0  mov     [rbp+1A0h+var_B8], rax
0x1005af8b7  lea     rax, aSplXeBufferMgr; "SPL_XE_BUFFER_MGR"
0x1005af8be  mov     [rbp+1A0h+var_B0], rax
0x1005af8c5  lea     rax, aSplXeSessionEv; "SPL_XE_SESSION_EVENT_MGR"
0x1005af8cc  mov     [rbp+1A0h+var_A8], rax
0x1005af8d3  lea     rax, aSplXeSessionTa; "SPL_XE_SESSION_TARGET_MGR"
0x1005af8da  mov     [rbp+1A0h+var_A0], rax
0x1005af8e1  lea     rax, aSplXeSessionMg; "SPL_XE_SESSION_MGR"
0x1005af8e8  mov     [rbp+1A0h+var_98], rax
0x1005af8ef  lea     rax, aSplXeNotificat; "SPL_XE_NOTIFICATION_CALLBACK_LIST"
0x1005af8f6  mov     [rbp+1A0h+var_90], rax
0x1005af8fd  lea     rax, aSplXeDispatche; "SPL_XE_DISPATCHER_QUEUE"
0x1005af904  mov     [rbp+1A0h+var_88], rax
0x1005af90b  lea     rax, aSosDebugHook_0; "SOS_DEBUG_HOOK"
0x1005af912  mov     [rbp+1A0h+var_80], rax
0x1005af919  lea     rax, aResqueue; "RESQUEUE"
0x1005af920  mov     [rbp+1A0h+var_78], rax
0x1005af927  lea     rax, aSplNonyieldAna; "SPL_NONYIELD_ANALYSIS"
0x1005af92e  mov     [rbp+1A0h+var_70], rax
0x1005af935  lea     rax, aSosBlockallocp; "SOS_BLOCKALLOCPARTIALLIST"
0x1005af93c  mov     [rbp+1A0h+var_68], rax
0x1005af943  lea     rax, aSosDescdatabuf; "SOS_DESCDATABUFFERLIST"
0x1005af94a  mov     [rbp+1A0h+var_60], rax
0x1005af951  lea     rax, aDrtlModuleinfo; "DRTL_MODULEINFOLIST"
0x1005af958  mov     [rbp+1A0h+var_58], rax
0x1005af95f  lea     rax, aEtwLoggerManag_0; "ETW_LOGGER_MANAGER"
0x1005af966  mov     [rbp+1A0h+var_50], rax
0x1005af96d  lea     rax, aTestteam_0; "TESTTEAM"
0x1005af974  mov     [rbp+1A0h+var_48], rax
0x1005af97b  lea     rax, aTestteamtastas_0; "TESTTEAMTASTAS"
0x1005af982  mov     [rbp+1A0h+var_40], rax
0x1005af989  lea     rax, aTestteamexpone; "TESTTEAMEXPONENTIAL"
0x1005af990  mov     [rbp+1A0h+var_38], rax
0x1005af997  lea     rax, aTestteamexpone_0; "TESTTEAMEXPONENTIALTASTAS"
0x1005af99e  mov     [rbp+1A0h+var_30], rax
0x1005af9a5  lea     rax, aTestteamreport; "TESTTEAMREPORTINGOPTIONSCHECKUNUSED"
0x1005af9ac  mov     [rbp+1A0h+var_28], rax
0x1005af9b3  lea     rax, aTestteamreport_0; "TESTTEAMREPORTINGOPTIONSCHECKCLOUDDB"
0x1005af9ba  mov     [rbp+1A0h+var_20], rax
0x1005af9c1  lea     rax, aSosSystemSplLa; "SOS_SYSTEM_SPL_LAST"
0x1005af9c8  mov     [rbp+1A0h+var_18], rax
0x1005af9cf  lea     rax, aLockRwTest; "LOCK_RW_TEST"
0x1005af9d6  mov     qword ptr [rbp+1A0h+var_220], rax
0x1005af9da  lea     rax, aLockRwAr; "LOCK_RW_AR"
0x1005af9e1  mov     qword ptr [rbp+1A0h+var_220+8], rax
0x1005af9e5  lea     rax, aLockRwGtl; "LOCK_RW_GTL"
0x1005af9ec  mov     qword ptr [rbp+1A0h+var_210], rax
0x1005af9f0  lea     rax, aLockRwIorgVolu; "LOCK_RW_IORG_VOLUME_HT"
0x1005af9f7  mov     qword ptr [rbp+1A0h+var_210+8], rax
0x1005af9fb  lea     rax, aSosSystemRwSpl; "SOS_SYSTEM_RW_SPL_LAST"
0x1005afa02  mov     [rbp+1A0h+var_200], rax
0x1005afa06  mov     dword ptr [rsp+2A0h+var_280], 2020202h
0x1005afa0e  mov     dword ptr [rsp+2A0h+var_280+4], 2020202h
0x1005afa16  mov     dword ptr [rsp+2A0h+var_280+8], 2020202h
0x1005afa1e  mov     dword ptr [rsp+2A0h+var_280+0Ch], 2020202h
0x1005afa26  mov     dword ptr [rsp+2A0h+var_270], 2020202h
0x1005afa2e  mov     dword ptr [rsp+2A0h+var_270+4], 2020202h
0x1005afa36  mov     dword ptr [rsp+2A0h+var_270+8], 2020202h
0x1005afa3e  mov     dword ptr [rsp+2A0h+var_270+0Ch], 2020202h
0x1005afa46  mov     dword ptr [rsp+2A0h+var_260], 2020202h
0x1005afa4e  mov     dword ptr [rsp+2A0h+var_260+4], 2020202h
0x1005afa56  mov     dword ptr [rsp+2A0h+var_260+8], 2020202h
0x1005afa5e  mov     dword ptr [rsp+2A0h+var_260+0Ch], 2020202h
0x1005afa66  mov     dword ptr [rsp+2A0h+var_250], 2020202h
0x1005afa6e  mov     dword ptr [rsp+2A0h+var_250+4], 2020202h
0x1005afa76  mov     dword ptr [rsp+2A0h+var_250+8], 2010002h
0x1005afa7e  mov     [rbp+1A0h+arg_0], 2020202h
0x1005afa88  test    rbx, rbx
0x1005afa8b  jnz     short loc_1005AFAA4
0x1005afa8d  call    cs:__imp__errno
0x1005afa93  mov     dword ptr [rax], 16h
0x1005afa99  call    cs:__imp__invalid_parameter_noinfo
0x1005afa9f  jmp     loc_1005AFB31
0x1005afaa4  lea     rax, [rbp+1A0h+var_1F0]
0x1005afaa8  mov     ecx, 3
0x1005afaad  nop     dword ptr [rax]
0x1005afab0  lea     rbx, [rbx+80h]
0x1005afab7  movups  xmm0, xmmword ptr [rax]
0x1005afaba  movups  xmm1, xmmword ptr [rax+10h]
0x1005afabe  lea     rax, [rax+80h]
0x1005afac5  movups  xmmword ptr [rbx-80h], xmm0
0x1005afac9  movups  xmm0, xmmword ptr [rax-60h]
0x1005afacd  movups  xmmword ptr [rbx-70h], xmm1
0x1005afad1  movups  xmm1, xmmword ptr [rax-50h]
0x1005afad5  movups  xmmword ptr [rbx-60h], xmm0
0x1005afad9  movups  xmm0, xmmword ptr [rax-40h]
0x1005afadd  movups  xmmword ptr [rbx-50h], xmm1
0x1005afae1  movups  xmm1, xmmword ptr [rax-30h]
0x1005afae5  movups  xmmword ptr [rbx-40h], xmm0
0x1005afae9  movups  xmm0, xmmword ptr [rax-20h]
0x1005afaed  movups  xmmword ptr [rbx-30h], xmm1
0x1005afaf1  movups  xmm1, xmmword ptr [rax-10h]
0x1005afaf5  movups  xmmword ptr [rbx-20h], xmm0
0x1005afaf9  movups  xmmword ptr [rbx-10h], xmm1
0x1005afafd  sub     rcx, 1
0x1005afb01  jnz     short loc_1005AFAB0
0x1005afb03  movups  xmm0, xmmword ptr [rax]
0x1005afb06  movups  xmm1, xmmword ptr [rax+10h]
0x1005afb0a  movups  xmmword ptr [rbx], xmm0
0x1005afb0d  movups  xmm0, xmmword ptr [rax+20h]
0x1005afb11  movups  xmmword ptr [rbx+10h], xmm1
0x1005afb15  movups  xmm1, xmmword ptr [rax+30h]
0x1005afb19  movups  xmmword ptr [rbx+20h], xmm0
0x1005afb1d  movups  xmm0, xmmword ptr [rax+40h]
0x1005afb21  movups  xmmword ptr [rbx+30h], xmm1
0x1005afb25  movups  xmm1, xmmword ptr [rax+50h]
0x1005afb29  movups  xmmword ptr [rbx+40h], xmm0
0x1005afb2d  movups  xmmword ptr [rbx+50h], xmm1
0x1005afb31  test    r14, r14
0x1005afb34  jnz     short loc_1005AFB4A
0x1005afb36  call    cs:__imp__errno
0x1005afb3c  mov     dword ptr [rax], 16h
0x1005afb42  call    cs:__imp__invalid_parameter_noinfo
0x1005afb48  jmp     short loc_1005AFB66
0x1005afb4a  movups  xmm0, [rbp+1A0h+var_220]
0x1005afb4e  movups  xmm1, [rbp+1A0h+var_210]
0x1005afb52  movups  xmmword ptr [r14], xmm0
0x1005afb56  movsd   xmm0, [rbp+1A0h+var_200]
0x1005afb5b  movups  xmmword ptr [r14+10h], xmm1
0x1005afb60  movsd   qword ptr [r14+20h], xmm0
0x1005afb66  test    rsi, rsi
0x1005afb69  jnz     short loc_1005AFB7F
0x1005afb6b  call    cs:__imp__errno
0x1005afb71  mov     dword ptr [rax], 16h
0x1005afb77  call    cs:__imp__invalid_parameter_noinfo
0x1005afb7d  jmp     short loc_1005AFBAB
0x1005afb7f  movups  xmm0, [rsp+2A0h+var_280]
0x1005afb84  mov     eax, dword ptr [rsp+2A0h+var_250+8]
0x1005afb88  movups  xmm1, [rsp+2A0h+var_270]
0x1005afb8d  movups  xmmword ptr [rsi], xmm0
0x1005afb90  movups  xmm0, [rsp+2A0h+var_260]
0x1005afb95  movups  xmmword ptr [rsi+10h], xmm1
0x1005afb99  movsd   xmm1, qword ptr [rsp+2A0h+var_250]
0x1005afb9f  movups  xmmword ptr [rsi+20h], xmm0
0x1005afba3  movsd   qword ptr [rsi+30h], xmm1
0x1005afba8  mov     [rsi+38h], eax
0x1005afbab  test    r15, r15
0x1005afbae  jnz     short loc_1005AFBC4
0x1005afbb0  call    cs:__imp__errno
0x1005afbb6  mov     dword ptr [rax], 16h
0x1005afbbc  call    cs:__imp__invalid_parameter_noinfo
0x1005afbc2  jmp     short loc_1005AFBD2
0x1005afbc4  mov     eax, [rbp+1A0h+arg_0]
0x1005afbca  mov     [r15], eax
0x1005afbcd  mov     byte ptr [r15+4], 2
0x1005afbd2  lea     r11, [rsp+2A0h+var_10]
0x1005afbda  mov     rax, rdi
0x1005afbdd  mov     rbx, [r11+28h]
0x1005afbe1  mov     rsi, [r11+30h]
0x1005afbe5  mov     rdi, [r11+38h]
  ... truncated ...
```
