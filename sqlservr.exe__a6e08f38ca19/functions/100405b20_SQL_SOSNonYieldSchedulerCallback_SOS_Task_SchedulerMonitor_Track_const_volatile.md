# SQL_SOSNonYieldSchedulerCallback(SOS_Task *,SchedulerMonitor::Track const * volatile)

- ea: `0x100405b20`
- end: `0x1004061a4`
- name: `?SQL_SOSNonYieldSchedulerCallback@@YAXPEAVSOS_Task@@REBVTrack@SchedulerMonitor@@@Z`
- size: `1668`
- prototype: `void __fastcall(struct SOS_Task *this, const struct SchedulerMonitor::Track *volatile)`
- caller_count: `0`
- callee_count: `14`
- tags: `loader_planting, service_task, installer_update`

## callees

- `0x100401010`
- `0x1004010b0`
- `0x100401580`
- `0x100402ec0`
- `0x100403fa0`
- `0x1004043d0`
- `0x1004044e0`
- `0x100405100`
- `0x100405b20`
- `0x100407490`
- `0x100407ea0`
- `0x1004403d0`
- `0x100440860`
- `0x1004534f8`

## import_xrefs

- `sqllang!?stackTrace@@YAXPEAVSOS_Task@@PEAVExecutionContext@@PEB_WKW4StackTraceClass@@PEAVCDStream@@W4WatsonBucketHint@@PEBU_GUID@@PEAVCopiedStackInfo@@@Z` at `0x100406143`
- `sqllang!?stackTrace@@YAXPEAVSOS_Task@@PEAVExecutionContext@@PEB_WKW4StackTraceClass@@PEAVCDStream@@W4WatsonBucketHint@@PEBU_GUID@@PEAVCopiedStackInfo@@@Z` at `0x100406143`
- `sqldk!?SOS_OS_IgnoreNonYieldingScheduler@@3HA` at `0x100405c17`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100405cc4`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100405da3`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100405ded`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100405cc4`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100405da3`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100405ded`
- `sqldk!SystemThread_TlsOffset` at `0x100405cab`
- `sqldk!SystemThread_TlsOffset` at `0x100405d8a`
- `sqldk!SystemThread_TlsOffset` at `0x100405dd2`
- `sqldk!SystemThread_TlsIndex` at `0x100405ca2`
- `sqldk!SystemThread_TlsIndex` at `0x100405d81`
- `sqldk!SystemThread_TlsIndex` at `0x100405dc9`
- `sqldk!?TriggerDump@SOS_OS@@SA_NPEBUSYSTEM_SQLPAL_TRIGGER_DUMP_INFO@@@Z` at `0x100406048`
- `sqldk!?TriggerDump@SOS_OS@@SA_NPEBUSYSTEM_SQLPAL_TRIGGER_DUMP_INFO@@@Z` at `0x100406048`
- `sqldk!?IsXPlatInstance@OsInfo@@QEBA?B_NXZ` at `0x100405ffe`
- `sqldk!?IsXPlatInstance@OsInfo@@QEBA?B_NXZ` at `0x100405ffe`
- `sqldk!?ExceptionPostCatchActions@@YAXPEAVWorker@@@Z` at `0x100405db9`
- `sqldk!?ExceptionPostCatchActions@@YAXPEAVWorker@@@Z` at `0x100405db9`
- `sqldk!?ex_trans_cexcept_nodump@@YAXIPEAU_EXCEPTION_POINTERS@@@Z` at `0x100405cdc`
- `sqldk!?IsWorkerUtilizationHigh@Track@SchedulerMonitor@@QEBAHXZ` at `0x100405f26`
- `sqldk!?IsWorkerUtilizationHigh@Track@SchedulerMonitor@@QEBAHXZ` at `0x100405f26`
- `sqldk!?GetProcessUtilization@ProcessTrack@SchedulerMonitor@@QEBAIXZ` at `0x100405ec4`
- `sqldk!?GetProcessUtilization@ProcessTrack@SchedulerMonitor@@QEBAIXZ` at `0x100405ec4`
- `sqldk!?IsProcessStarved@ProcessTrack@SchedulerMonitor@@QEBAHXZ` at `0x100405f34`
- `sqldk!?IsProcessStarved@ProcessTrack@SchedulerMonitor@@QEBAHXZ` at `0x100405f34`
- `sqldk!?SilentBackoutHandler@@YAHHHHHPEAD@Z` at `0x100405cf5`
- `sqldk!?GetIdlePercentage@CSystemTimes@@QEBAIXZ` at `0x100405eb8`
- `sqldk!?GetIdlePercentage@CSystemTimes@@QEBAIXZ` at `0x100405eb8`
- `sqldk!?g_featureSwitchesDk@@3VCFeatureSwitchesDk@@A` at `0x100405c0a`
- `sqldk!?SOS_OS_OsInfo@@3VOsInfo@@A` at `0x100405ff7`
- `sqldk!?sm_CpuConsumers@SOS_PublicGlobals@@2JC` at `0x100405c38`
- `sqldk!?SOS_Tracing_osTrace@@3KA` at `0x100405fc5`

## string_xrefs

- `0x100406029`: `CopyThreadStackForDump: Core dump requested by user. Target Thread Id: 0x%08X`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall SQL_SOSNonYieldSchedulerCallback(struct SOS_Task *this, struct SchedulerMonitor::Track *a2)
{
  struct SOS_Task *v2; // r13
  unsigned int v3; // r14d
  unsigned int v4; // ecx
  unsigned int v5; // ebx
  BOOL v6; // edi
  BOOL v7; // r8d
  __int64 v8; // rbx
  __int64 v9; // rcx
  unsigned __int8 *v10; // rdi
  __int64 v11; // rbx
  __int64 v12; // rcx
  __int64 v13; // rbx
  __int64 v14; // rax
  void *v15; // rsp
  __int64 v16; // r15
  __int64 v17; // r14
  __int64 v18; // rsi
  __int64 v19; // rdi
  unsigned int v20; // edi
  int v21; // ebx
  __int64 v22; // rax
  char v23; // bl
  char v24; // di
  __int64 v25; // [rsp+18h] [rbp-20048h]
  unsigned int ProcessUtilization; // [rsp+30h] [rbp-20030h]
  unsigned int IdlePercentage; // [rsp+38h] [rbp-20028h]
  char v28; // [rsp+50h] [rbp-20010h] BYREF
  struct SchedulerMonitor::Track *v29; // [rsp+20060h] [rbp+0h]
  unsigned int ThreadId; // [rsp+20068h] [rbp+8h]
  unsigned int v31; // [rsp+2006Ch] [rbp+Ch] BYREF
  unsigned int v32; // [rsp+20070h] [rbp+10h] BYREF
  int v33; // [rsp+20074h] [rbp+14h]
  unsigned int v34; // [rsp+20078h] [rbp+18h] BYREF
  unsigned int v35; // [rsp+2007Ch] [rbp+1Ch] BYREF
  unsigned int v36; // [rsp+20080h] [rbp+20h]
  unsigned int v37; // [rsp+20084h] [rbp+24h]
  BOOL v38; // [rsp+20088h] [rbp+28h]
  BOOL v39; // [rsp+2008Ch] [rbp+2Ch]
  __int64 v40; // [rsp+20090h] [rbp+30h]
  unsigned __int8 *v41; // [rsp+20098h] [rbp+38h]
  struct SOS_Task *v42; // [rsp+200A0h] [rbp+40h]
  __int64 v43; // [rsp+200A8h] [rbp+48h]
  unsigned __int8 *v44; // [rsp+200B0h] [rbp+50h]
  _BYTE v45[16]; // [rsp+200B8h] [rbp+58h] BYREF
  _BYTE v46[24]; // [rsp+200C8h] [rbp+68h] BYREF
  _BYTE v47[48]; // [rsp+200E0h] [rbp+80h] BYREF
  int v48; // [rsp+20110h] [rbp+B0h] BYREF
  char Buffer[268]; // [rsp+20114h] [rbp+B4h] BYREF
  _BYTE v50[4]; // [rsp+20220h] [rbp+1C0h] BYREF
  int v51; // [rsp+20224h] [rbp+1C4h]
  int v52; // [rsp+20230h] [rbp+1D0h]
  __int64 v53; // [rsp+20238h] [rbp+1D8h]
  __int64 v54; // [rsp+20240h] [rbp+1E0h]
  _BYTE v55[1232]; // [rsp+20250h] [rbp+1F0h] BYREF
  _BYTE v56[1232]; // [rsp+20720h] [rbp+6C0h] BYREF
  __int64 v57; // [rsp+20BF0h] [rbp+B90h]
  int v58; // [rsp+20BF8h] [rbp+B98h]
  __int64 (*v59[32])(void); // [rsp+20C00h] [rbp+BA0h] BYREF

  v43 = -2;
  v2 = this;
  v42 = this;
  v29 = a2;
  v3 = dword_1004A08D0 / 0x1388u;
  if ( (*(_BYTE *)(qword_10049F340 + 1101) & 4) != 0 || (*(_BYTE *)(qword_10049F340 + 456) & 0x40) != 0 )
  {
    v4 = dword_1004A08D4;
    if ( (unsigned int)dword_1004A08D4 < 0x493E0 )
      v4 = 300000;
  }
  else
  {
    v4 = dword_1004A08D4;
  }
  v37 = v4 / 0x1388;
  v5 = *(_DWORD *)v29 - *((_DWORD *)v29 + 102);
  v36 = v5;
  NonYieldSystemInformation::UpdateNonYieldRingBuffer(
    (NonYieldSystemInformation *)NonYieldSystemInformation::sm_NonYieldSystemInfo,
    v29,
    *(struct SOS_Node **)(*((_QWORD *)v2 + 20) + 5192LL),
    v5,
    v4 / 0x1388);
  v6 = (*(_BYTE *)(qword_10049F340 + 157) & 0x40) != 0;
  v38 = v6;
  v39 = v6;
  v7 = *((_BYTE *)&g_featureSwitchesDk + 81) && SOS_OS_IgnoreNonYieldingScheduler;
  if ( (v6 || SOS_PublicGlobals::sm_CpuConsumers <= 0) && *((_DWORD *)v29 + 102) && !(v5 % v3) && (v5 || v6) && !v7 )
  {
    v32 = 0;
    v35 = 0;
    v33 = -1;
    v40 = 0;
    ThreadId = 0;
    v31 = 0;
    v8 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
    v9 = *(_QWORD *)(v8 + 256);
    if ( !v9 )
    {
      SystemThread::MakeMiniSOSThread(0);
      v9 = *(_QWORD *)(v8 + 256);
    }
    v41 = *(unsigned __int8 **)(v9 + 3208);
    v10 = v41;
    *(_QWORD *)(v9 + 3208) = ex_trans_cexcept_nodump;
    v44 = v10;
    try
    {
      ExcHandler::ExcHandler((ExcHandler *)v47, 0, 0, 0, SilentBackoutHandler, 0);
      v33 = *(_DWORD *)(*((_QWORD *)v2 + 20) + 3688LL);
      v40 = *((_QWORD *)v2 + 19);
      ThreadId = SOS_Task::DwGetThreadId(v2);
      if ( qword_1004D28B8 )
        qword_1004D28B8(v2, &v32, &v35, &v31);
      ExcHandler::~ExcHandler((ExcHandler *)v47);
    }
    catch ( SQLError v46 )
    {
      try
      {
        ExceptionBackout::ExceptionBackout((ExceptionBackout *)v45, (const struct SQLError *)v46);
        ExceptionBackout::~ExceptionBackout((ExceptionBackout *)v45);
      }
      catch ( ShortStackException )
      {
      }
      v2 = v42;
      v38 = v39;
      v10 = v41;
    }
    v11 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
    v12 = *(_QWORD *)(v11 + 256);
    if ( !v12 )
    {
      SystemThread::MakeMiniSOSThread(0);
      v12 = *(_QWORD *)(v11 + 256);
    }
    if ( *(_DWORD *)(v12 + 556) )
      ExceptionPostCatchActions((struct Worker *)v12);
    v13 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
    v14 = *(_QWORD *)(v13 + 256);
    if ( !v14 )
    {
      SystemThread::MakeMiniSOSThread(0);
      v14 = *(_QWORD *)(v13 + 256);
    }
    *(_QWORD *)(v14 + 3208) = v10;
    memset_0(v59, 0, sizeof(v59));
    v15 = alloca(131088);
    v41 = (unsigned __int8 *)&v28;
    v34 = 0;
    v16 = *((_QWORD *)v29 + 21) / 10000LL;
    v17 = *((_QWORD *)v29 + 48) / 10000LL;
    v18 = *((_QWORD *)v29 + 47) / 10000LL;
    v19 = *((_QWORD *)v29 + 43) / 10000LL;
    IdlePercentage = CSystemTimes::GetIdlePercentage((struct SchedulerMonitor::Track *)((char *)v29 + 144));
    ProcessUtilization = SchedulerMonitor::ProcessTrack::GetProcessUtilization(v29);
    v25 = v19;
    v20 = ThreadId;
    scierrlog(0x45DBu, v32, v31, v35, ThreadId, v40, v33, v25, v18, v17, ProcessUtilization, IdlePercentage, v16);
    if ( (*(_BYTE *)(qword_10049F340 + 1003) & 1) != 0 )
    {
      if ( !SchedulerMonitor::Track::IsWorkerUtilizationHigh(v29)
        && SchedulerMonitor::ProcessTrack::IsProcessStarved(v29) )
      {
        v21 = 0;
        v20 = ThreadId;
        goto LABEL_35;
      }
      v20 = ThreadId;
    }
    v21 = 1;
LABEL_35:
    v50[0] = 0;
    v51 = 0;
    v52 = 0;
    v53 = 0;
    v54 = 0;
    v57 = 0;
    v58 = 0;
    memset_0(v55, 0, sizeof(v55));
    memset_0(v56, 0, sizeof(v56));
    if ( !v21 || v36 % v37 || dword_1004A365C && !v38 || (SOS_Tracing_osTrace & 0x40) != 0 )
    {
      v22 = qword_10049F340;
    }
    else
    {
      v22 = qword_10049F340;
      if ( (*(_BYTE *)(qword_10049F340 + 157) & 0x10) == 0 )
      {
        v23 = 1;
        goto LABEL_44;
      }
    }
    v23 = 0;
LABEL_44:
    if ( (*(_BYTE *)(v22 + 317) & 0x10) != 0
      && OsInfo::IsXPlatInstance(SOS_OS_OsInfo)
      && v23
      && (*(_BYTE *)(qword_10049F340 + 319) & 1) == 0 )
    {
      v48 = 753;
      StringCchPrintfA(
        Buffer,
        0x100u,
        "CopyThreadStackForDump: Core dump requested by user. Target Thread Id: 0x%08X",
        v20);
      SOS_OS::TriggerDump((const struct SYSTEM_SQLPAL_TRIGGER_DUMP_INFO *)&v48);
    }
    if ( CopiedStackInfo::CopyThreadStackForDump((CopiedStackInfo *)v50, v41, 0x20000u, v20, v59, 0x20u, &v34) )
    {
      v24 = 1;
      NonYieldSystemInformation::StoreCopiedNonYieldStackRingBuffer(
        NonYieldSystemInformation::sm_NonYieldSystemInfo,
        0,
        v59,
        v34,
        ThreadId,
        v33,
        v2,
        v40,
        v32,
        v31,
        *((_QWORD *)v29 + 47),
        *((_QWORD *)v29 + 48));
    }
    else
    {
      v24 = 0;
    }
    if ( v23 )
    {
      dword_1004A365C = 1;
      v58 = 256;
      stackTrace(v2, 0, L"Non-yielding Scheduler", 1697, 2, 0, 256, 0, v50);
    }
    if ( v24 )
    {
      LogSystemMetadataNotSentToClient(L"Copied stack");
      LogFramesRVA(v59, v34, 0);
    }
    v50[0] = 0;
    v58 = 0;
  }
}

```

## disassembly

```asm
0x100405b20  push    rbp
0x100405b22  push    rsi
0x100405b23  push    rdi
0x100405b24  push    r12
0x100405b26  push    r13
0x100405b28  push    r14
0x100405b2a  push    r15
0x100405b2c  sub     rsp, 0D20h
0x100405b33  lea     rbp, [rsp+70h]
0x100405b38  mov     [rbp+0CE0h+var_C98], 0FFFFFFFFFFFFFFFEh
0x100405b40  mov     [rbp+0CE0h+arg_10], rbx
0x100405b47  mov     rax, cs:__security_cookie
0x100405b4e  xor     rax, rbp
0x100405b51  mov     [rbp+0CE0h+var_40], rax
0x100405b58  mov     r13, rcx
0x100405b5b  mov     [rbp+0CE0h+var_CA0], rcx
0x100405b5f  mov     [rbp+0CE0h+var_CE0], rdx
0x100405b63  mov     eax, 0D1B71759h
0x100405b68  mul     cs:dword_1004A08D0
0x100405b6e  mov     r14d, edx
0x100405b71  shr     r14d, 0Ch
0x100405b75  mov     rax, cs:qword_10049F340
0x100405b7c  test    byte ptr [rax+44Dh], 4
0x100405b83  jnz     short loc_100405B96
0x100405b85  test    byte ptr [rax+1C8h], 40h
0x100405b8c  jnz     short loc_100405B96
0x100405b8e  mov     ecx, cs:dword_1004A08D4
0x100405b94  jmp     short loc_100405BA6
0x100405b96  mov     ecx, cs:dword_1004A08D4
0x100405b9c  mov     edx, 493E0h
0x100405ba1  cmp     ecx, edx
0x100405ba3  cmovb   ecx, edx
0x100405ba6  mov     eax, 0D1B71759h
0x100405bab  mul     ecx
0x100405bad  mov     esi, edx
0x100405baf  shr     esi, 0Ch
0x100405bb2  mov     [rbp+0CE0h+var_CBC], esi
0x100405bb5  mov     rcx, [rbp+0CE0h+var_CE0]
0x100405bb9  mov     rax, [rbp+0CE0h+var_CE0]
0x100405bbd  mov     ebx, [rax]
0x100405bbf  sub     ebx, [rcx+198h]
0x100405bc5  mov     [rbp+0CE0h+var_CC0], ebx
0x100405bc8  mov     r8, [r13+0A0h]
0x100405bcf  mov     dword ptr [rsp+0D50h+var_D30], esi; unsigned int
0x100405bd3  mov     r9d, ebx; unsigned int
0x100405bd6  mov     r8, [r8+1448h]; struct SOS_Node *
0x100405bdd  mov     rdx, [rbp+0CE0h+var_CE0]; struct SchedulerMonitor::Track *
0x100405be1  lea     rcx, ?sm_NonYieldSystemInfo@NonYieldSystemInformation@@0V1@A; this
0x100405be8  call    ?UpdateNonYieldRingBuffer@NonYieldSystemInformation@@QEAAXPEBVTrack@SchedulerMonitor@@PEAVSOS_Node@@IK@Z; NonYieldSystemInformation::UpdateNonYieldRingBuffer(SchedulerMonitor::Track const *,SOS_Node *,uint,ulong)
0x100405bed  mov     rax, cs:qword_10049F340
0x100405bf4  movzx   ecx, byte ptr [rax+9Dh]
0x100405bfb  shr     cl, 6
0x100405bfe  movzx   edi, cl
0x100405c01  and     edi, 1
0x100405c04  mov     [rbp+0CE0h+var_CB8], edi
0x100405c07  mov     [rbp+0CE0h+var_CB4], edi
0x100405c0a  mov     rax, cs:__imp_?g_featureSwitchesDk@@3VCFeatureSwitchesDk@@A; CFeatureSwitchesDk g_featureSwitchesDk
0x100405c11  cmp     byte ptr [rax+51h], 0
0x100405c15  jz      short loc_100405C2E
0x100405c17  mov     rax, cs:__imp_?SOS_OS_IgnoreNonYieldingScheduler@@3HA; int SOS_OS_IgnoreNonYieldingScheduler
0x100405c1e  cmp     dword ptr [rax], 0
0x100405c21  jz      short loc_100405C2E
0x100405c23  mov     r8d, 1
0x100405c29  xor     r12d, r12d
0x100405c2c  jmp     short loc_100405C34
0x100405c2e  xor     r12d, r12d
0x100405c31  mov     r8d, r12d
0x100405c34  test    edi, edi
0x100405c36  jnz     short loc_100405C49
0x100405c38  mov     rax, cs:__imp_?sm_CpuConsumers@SOS_PublicGlobals@@2JC; long volatile SOS_PublicGlobals::sm_CpuConsumers
0x100405c3f  mov     ecx, [rax]
0x100405c41  test    ecx, ecx
0x100405c43  jg      loc_10040617B
0x100405c49  mov     rax, [rbp+0CE0h+var_CE0]
0x100405c4d  cmp     dword ptr [rax+198h], 0
0x100405c54  jz      loc_10040617B
0x100405c5a  xor     edx, edx
0x100405c5c  mov     eax, ebx
0x100405c5e  div     r14d
0x100405c61  test    edx, edx
0x100405c63  jnz     loc_10040617B
0x100405c69  test    ebx, ebx
0x100405c6b  jnz     short loc_100405C75
0x100405c6d  test    edi, edi
0x100405c6f  jz      loc_10040617B
0x100405c75  test    r8d, r8d
0x100405c78  jnz     loc_10040617B
0x100405c7e  mov     [rbp+0CE0h+var_CD0], r12d
0x100405c82  mov     [rbp+0CE0h+var_CC4], r12d
0x100405c86  mov     [rbp+0CE0h+var_CCC], 0FFFFFFFFh
0x100405c8d  mov     [rbp+0CE0h+var_CB0], r12
0x100405c91  mov     [rbp+0CE0h+var_CD8], r12d
0x100405c95  mov     [rbp+0CE0h+var_CD4], r12d
0x100405c99  mov     rdx, gs:58h
0x100405ca2  mov     rax, cs:__imp_SystemThread_TlsIndex
0x100405ca9  mov     ecx, [rax]
0x100405cab  mov     rax, cs:__imp_SystemThread_TlsOffset
0x100405cb2  mov     ebx, [rax]
0x100405cb4  add     rbx, [rdx+rcx*8]
0x100405cb8  mov     rcx, [rbx+100h]
0x100405cbf  test    rcx, rcx
0x100405cc2  jnz     short loc_100405CD1
0x100405cc4  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x100405cca  mov     rcx, [rbx+100h]
0x100405cd1  mov     rdi, [rcx+0C88h]
0x100405cd8  mov     [rbp+0CE0h+var_CA8], rdi
0x100405cdc  mov     rax, cs:__imp_?ex_trans_cexcept_nodump@@YAXIPEAU_EXCEPTION_POINTERS@@@Z; ex_trans_cexcept_nodump(uint,_EXCEPTION_POINTERS *)
0x100405ce3  mov     [rcx+0C88h], rax
0x100405cea  mov     [rbp+0CE0h+var_C90], rdi
0x100405cee  xor     edx, edx; unsigned __int16
0x100405cf0  mov     [rsp+0D50h+var_D28], r12; struct Worker *
0x100405cf5  mov     rax, cs:__imp_?SilentBackoutHandler@@YAHHHHHPEAD@Z; SilentBackoutHandler(int,int,int,int,char *)
0x100405cfc  mov     [rsp+0D50h+var_D30], rax; int (*)(int, int, int, int, char *)
0x100405d01  xor     r9d, r9d; unsigned __int8
0x100405d04  xor     r8d, r8d; unsigned __int8
0x100405d07  lea     rcx, [rbp+0CE0h+var_C60]; this
0x100405d0e  call    ??0ExcHandler@@QEAA@GEEP6AHHHHHPEAD@ZPEAVWorker@@@Z; ExcHandler::ExcHandler(ushort,uchar,uchar,int (*)(int,int,int,int,char *),Worker *)
0x100405d13  nop
0x100405d14  mov     rax, [r13+0A0h]
0x100405d1b  mov     ecx, [rax+0E68h]
0x100405d21  mov     [rbp+0CE0h+var_CCC], ecx
0x100405d24  mov     rax, [r13+98h]
0x100405d2b  mov     [rbp+0CE0h+var_CB0], rax
0x100405d2f  mov     rcx, r13; this
0x100405d32  call    ?DwGetThreadId@SOS_Task@@QEAAKXZ; SOS_Task::DwGetThreadId(void)
0x100405d37  mov     [rbp+0CE0h+var_CD8], eax
0x100405d3a  mov     rax, cs:qword_1004D28B8
0x100405d41  test    rax, rax
0x100405d44  jz      short loc_100405D58
0x100405d46  lea     r9, [rbp+0CE0h+var_CD4]
0x100405d4a  lea     r8, [rbp+0CE0h+var_CC4]
0x100405d4e  lea     rdx, [rbp+0CE0h+var_CD0]
0x100405d52  mov     rcx, r13
0x100405d55  call    rax ; qword_1004D28B8
0x100405d57  nop
0x100405d58  lea     rcx, [rbp+0CE0h+var_C60]; this
0x100405d5f  call    ??1ExcHandler@@QEAA@XZ; ExcHandler::~ExcHandler(void)
0x100405d64  nop
0x100405d65  jmp     short loc_100405D78
0x100405d67  xor     r12d, r12d
0x100405d6a  mov     r13, [rbp+0CE0h+var_CA0]
0x100405d6e  mov     eax, [rbp+0CE0h+var_CB4]
0x100405d71  mov     [rbp+0CE0h+var_CB8], eax
0x100405d74  mov     rdi, [rbp+0CE0h+var_CA8]
0x100405d78  mov     rdx, gs:58h
0x100405d81  mov     rax, cs:__imp_SystemThread_TlsIndex
0x100405d88  mov     ecx, [rax]
0x100405d8a  mov     rax, cs:__imp_SystemThread_TlsOffset
0x100405d91  mov     ebx, [rax]
0x100405d93  add     rbx, [rdx+rcx*8]
0x100405d97  mov     rcx, [rbx+100h]
0x100405d9e  test    rcx, rcx
0x100405da1  jnz     short loc_100405DB0
0x100405da3  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x100405da9  mov     rcx, [rbx+100h]
0x100405db0  cmp     dword ptr [rcx+22Ch], 0
0x100405db7  jz      short loc_100405DC0
0x100405db9  call    cs:__imp_?ExceptionPostCatchActions@@YAXPEAVWorker@@@Z; ExceptionPostCatchActions(Worker *)
0x100405dbf  nop
0x100405dc0  mov     rdx, gs:58h
0x100405dc9  mov     rax, cs:__imp_SystemThread_TlsIndex
0x100405dd0  mov     ecx, [rax]
0x100405dd2  mov     rax, cs:__imp_SystemThread_TlsOffset
0x100405dd9  mov     ebx, [rax]
0x100405ddb  add     rbx, [rdx+rcx*8]
0x100405ddf  mov     rax, [rbx+100h]
0x100405de6  test    rax, rax
0x100405de9  jnz     short loc_100405DFA
0x100405deb  xor     ecx, ecx
0x100405ded  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x100405df3  mov     rax, [rbx+100h]
0x100405dfa  mov     [rax+0C88h], rdi
0x100405e01  xor     edx, edx; Val
0x100405e03  mov     r8d, 100h; Size
0x100405e09  lea     rcx, [rbp+0CE0h+var_140]; void *
0x100405e10  call    memset_0
0x100405e15  mov     eax, 20010h
0x100405e1a  call    _alloca_probe
0x100405e1f  sub     rsp, rax
0x100405e22  lea     rax, [rsp+20D60h+var_20CF0]
0x100405e27  mov     [rbp+0CE0h+var_CA8], rax
0x100405e2b  mov     [rbp+0CE0h+var_CC8], r12d
0x100405e2f  mov     rcx, [rbp+0CE0h+var_CE0]
0x100405e33  mov     r8, [rbp+0CE0h+var_CE0]
0x100405e37  mov     r9, 346DC5D63886594Bh
0x100405e41  mov     rax, r9
0x100405e44  imul    qword ptr [r8+0A8h]
0x100405e4b  mov     r15, rdx
0x100405e4e  sar     r15, 0Bh
0x100405e52  mov     rax, r15
0x100405e55  shr     rax, 3Fh
0x100405e59  add     r15, rax
0x100405e5c  mov     rax, r9
0x100405e5f  imul    qword ptr [rcx+180h]
0x100405e66  mov     r14, rdx
0x100405e69  sar     r14, 0Bh
0x100405e6d  mov     rax, r14
0x100405e70  shr     rax, 3Fh
0x100405e74  add     r14, rax
0x100405e77  mov     rax, r9
0x100405e7a  imul    qword ptr [rcx+178h]
0x100405e81  mov     rsi, rdx
0x100405e84  sar     rsi, 0Bh
0x100405e88  mov     rcx, rsi
0x100405e8b  shr     rcx, 3Fh
0x100405e8f  add     rsi, rcx
0x100405e92  mov     rcx, [rbp+0CE0h+var_CE0]
0x100405e96  mov     rax, r9
0x100405e99  imul    qword ptr [rcx+158h]
0x100405ea0  mov     rdi, rdx
0x100405ea3  sar     rdi, 0Bh
0x100405ea7  mov     rax, rdi
0x100405eaa  shr     rax, 3Fh
0x100405eae  add     rdi, rax
0x100405eb1  lea     rcx, [r8+90h]
0x100405eb8  call    cs:__imp_?GetIdlePercentage@CSystemTimes@@QEBAIXZ; CSystemTimes::GetIdlePercentage(void)
0x100405ebe  mov     ebx, eax
0x100405ec0  mov     rcx, [rbp+0CE0h+var_CE0]
0x100405ec4  call    cs:__imp_?GetProcessUtilization@ProcessTrack@SchedulerMonitor@@QEBAIXZ; SchedulerMonitor::ProcessTrack::GetProcessUtilization(void)
0x100405eca  mov     [rsp+20D60h+var_20D00], r15
0x100405ecf  mov     dword ptr [rsp+20D60h+var_20D08], ebx
0x100405ed3  mov     dword ptr [rsp+20D60h+var_20D10], eax
0x100405ed7  mov     [rsp+20D60h+var_20D18], r14
0x100405edc  mov     [rsp+20D60h+var_20D20], rsi
0x100405ee1  mov     [rsp+20D60h+var_20D28], rdi
0x100405ee6  mov     eax, [rbp+0CE0h+var_CCC]
0x100405ee9  mov     dword ptr [rsp+20D60h+var_20D30], eax
0x100405eed  mov     rax, [rbp+0CE0h+var_CB0]
0x100405ef1  mov     qword ptr [rsp+20D60h+var_20D38], rax
0x100405ef6  mov     edi, [rbp+0CE0h+var_CD8]
0x100405ef9  mov     dword ptr [rsp+20D60h+var_20D40], edi
0x100405efd  mov     r9d, [rbp+0CE0h+var_CC4]
0x100405f01  mov     r8d, [rbp+0CE0h+var_CD4]
0x100405f05  mov     edx, [rbp+0CE0h+var_CD0]
0x100405f08  mov     ecx, 45DBh; unsigned int
0x100405f0d  call    ?scierrlog@@YAXKZZ; scierrlog(ulong,...)
0x100405f12  mov     rax, cs:qword_10049F340
0x100405f19  test    byte ptr [rax+3EBh], 1
0x100405f20  jz      short loc_100405F49
0x100405f22  mov     rcx, [rbp+0CE0h+var_CE0]
0x100405f26  call    cs:__imp_?IsWorkerUtilizationHigh@Track@SchedulerMonitor@@QEBAHXZ; SchedulerMonitor::Track::IsWorkerUtilizationHigh(void)
0x100405f2c  test    eax, eax
0x100405f2e  jnz     short loc_100405F46
0x100405f30  mov     rcx, [rbp+0CE0h+var_CE0]
0x100405f34  call    cs:__imp_?IsProcessStarved@ProcessTrack@SchedulerMonitor@@QEBAHXZ; SchedulerMonitor::ProcessTrack::IsProcessStarved(void)
0x100405f3a  test    eax, eax
0x100405f3c  jz      short loc_100405F46
0x100405f3e  mov     ebx, r12d
0x100405f41  mov     edi, [rbp+0CE0h+var_CD8]
0x100405f44  jmp     short loc_100405F4E
0x100405f46  mov     edi, [rbp+0CE0h+var_CD8]
0x100405f49  mov     ebx, 1
0x100405f4e  mov     [rbp+0CE0h+var_B20], 0
0x100405f55  mov     [rbp+0CE0h+var_B1C], r12d
0x100405f5c  mov     [rbp+0CE0h+var_B10], r12d
0x100405f63  mov     [rbp+0CE0h+var_B08], r12
0x100405f6a  mov     [rbp+0CE0h+var_B00], r12
0x100405f71  mov     [rbp+0CE0h+var_150], r12
0x100405f78  mov     [rbp+0CE0h+var_148], r12d
0x100405f7f  xor     edx, edx; Val
0x100405f81  mov     r8d, 4D0h; Size
0x100405f87  lea     rcx, [rbp+0CE0h+var_AF0]; void *
0x100405f8e  call    memset_0
0x100405f93  xor     edx, edx; Val
0x100405f95  mov     r8d, 4D0h; Size
0x100405f9b  lea     rcx, [rbp+0CE0h+var_620]; void *
0x100405fa2  call    memset_0
0x100405fa7  nop
0x100405fa8  test    ebx, ebx
0x100405faa  jz      short loc_100405FE5
0x100405fac  xor     edx, edx
0x100405fae  mov     eax, [rbp+0CE0h+var_CC0]
0x100405fb1  div     [rbp+0CE0h+var_CBC]
0x100405fb4  test    edx, edx
0x100405fb6  jnz     short loc_100405FE5
0x100405fb8  cmp     cs:dword_1004A365C, edx
0x100405fbe  jz      short loc_100405FC5
0x100405fc0  cmp     [rbp+0CE0h+var_CB8], edx
0x100405fc3  jz      short loc_100405FE5
0x100405fc5  mov     rax, cs:__imp_?SOS_Tracing_osTrace@@3KA; ulong SOS_Tracing_osTrace
0x100405fcc  test    byte ptr [rax], 40h
0x100405fcf  jnz     short loc_100405FE5
0x100405fd1  mov     rax, cs:qword_10049F340
0x100405fd8  test    byte ptr [rax+9Dh], 10h
0x100405fdf  jnz     short loc_100405FEC
0x100405fe1  mov     bl, 1
0x100405fe3  jmp     short loc_100405FEE
0x100405fe5  mov     rax, cs:qword_10049F340
0x100405fec  xor     bl, bl
0x100405fee  test    byte ptr [rax+13Dh], 10h
0x100405ff5  jz      short loc_10040604E
0x100405ff7  mov     rcx, cs:__imp_?SOS_OS_OsInfo@@3VOsInfo@@A; OsInfo SOS_OS_OsInfo
0x100405ffe  call    cs:__imp_?IsXPlatInstance@OsInfo@@QEBA?B_NXZ; OsInfo::IsXPlatInstance(void)
0x100406004  test    al, al
0x100406006  jz      short loc_10040604E
0x100406008  test    bl, bl
0x10040600a  jz      short loc_10040604E
0x10040600c  mov     rax, cs:qword_10049F340
0x100406013  test    byte ptr [rax+13Fh], 1
0x10040601a  jnz     short loc_10040604E
  ... truncated ...
```
