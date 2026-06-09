# SQL_SOSNonYieldSchedulerCallback(SOS_Task *,SchedulerMonitor::Track const * volatile)

- ea: `0x100465450`
- end: `0x100465b04`
- name: `?SQL_SOSNonYieldSchedulerCallback@@YAXPEAVSOS_Task@@REBVTrack@SchedulerMonitor@@@Z`
- size: `1716`
- prototype: `void __fastcall(struct SOS_Task *this, const struct SchedulerMonitor::Track *volatile)`
- caller_count: `0`
- callee_count: `15`
- tags: `loader_planting, service_task, installer_update`

## callees

- `0x100418930`
- `0x1004189a0`
- `0x1004191d0`
- `0x100450ce0`
- `0x100455f90`
- `0x10045d370`
- `0x10045d5d0`
- `0x100464e90`
- `0x100465450`
- `0x100466b20`
- `0x1004680b0`
- `0x1004681c0`
- `0x100486af0`
- `0x100487cd6`
- `0x1004880d0`

## import_xrefs

- `sqldk!?StoreRecordInternalWithoutEvent@SOS_RingBuffer@@AEAAXPEAVSOS_RingBufferRecord@@PEAV?$StackFrames@$0BI@@@@Z` at `0x100465a60`
- `sqldk!?StoreRecordInternalWithoutEvent@SOS_RingBuffer@@AEAAXPEAVSOS_RingBufferRecord@@PEAV?$StackFrames@$0BI@@@@Z` at `0x100465a60`
- `sqldk!?ExceptionPostCatchActions@@YAXPEAVWorker@@@Z` at `0x1004656dc`
- `sqldk!?ExceptionPostCatchActions@@YAXPEAVWorker@@@Z` at `0x1004656dc`
- `sqldk!?sm_CpuConsumers@SOS_PublicGlobals@@2JC` at `0x100465547`
- `sqldk!?SOS_Tracing_osTrace@@3KA` at `0x1004658e3`
- `sqldk!?ex_trans_cexcept_nodump@@YAXIPEAU_EXCEPTION_POINTERS@@@Z` at `0x1004655f7`
- `sqldk!?IsWorkerUtilizationHigh@Track@SchedulerMonitor@@QEBAHXZ` at `0x100465844`
- `sqldk!?IsWorkerUtilizationHigh@Track@SchedulerMonitor@@QEBAHXZ` at `0x100465844`
- `sqldk!?GetProcessUtilization@ProcessTrack@SchedulerMonitor@@QEBAIXZ` at `0x1004657e3`
- `sqldk!?GetProcessUtilization@ProcessTrack@SchedulerMonitor@@QEBAIXZ` at `0x1004657e3`
- `sqldk!?IsProcessStarved@ProcessTrack@SchedulerMonitor@@QEBAHXZ` at `0x100465852`
- `sqldk!?IsProcessStarved@ProcessTrack@SchedulerMonitor@@QEBAHXZ` at `0x100465852`
- `sqldk!?SilentBackoutHandler@@YAHHHHHPEAD@Z` at `0x100465610`
- `sqldk!?GetIdlePercentage@CSystemTimes@@QEBAIXZ` at `0x1004657d7`
- `sqldk!?GetIdlePercentage@CSystemTimes@@QEBAIXZ` at `0x1004657d7`
- `sqldk!?TriggerDump@SOS_OS@@SA_NPEBUSYSTEM_SQLPAL_TRIGGER_DUMP_INFO@@@Z` at `0x100465963`
- `sqldk!?TriggerDump@SOS_OS@@SA_NPEBUSYSTEM_SQLPAL_TRIGGER_DUMP_INFO@@@Z` at `0x100465963`
- `sqldk!?g_featureSwitchesDk@@3VCFeatureSwitchesDk@@A` at `0x100465519`
- `sqldk!?IsXPlatInstance@OsInfo@@QEBA?B_NXZ` at `0x10046591a`
- `sqldk!?IsXPlatInstance@OsInfo@@QEBA?B_NXZ` at `0x10046591a`
- `sqldk!?SOS_OS_IgnoreNonYieldingScheduler@@3HA` at `0x100465526`
- `sqldk!?GetUlTraceFlags@CGlobalTraceFlags@@SAPEAEXZ` at `0x100465497`
- `sqldk!?GetUlTraceFlags@CGlobalTraceFlags@@SAPEAEXZ` at `0x1004654a6`
- `sqldk!?GetUlTraceFlags@CGlobalTraceFlags@@SAPEAEXZ` at `0x1004654fd`
- `sqldk!?GetUlTraceFlags@CGlobalTraceFlags@@SAPEAEXZ` at `0x100465831`
- `sqldk!?GetUlTraceFlags@CGlobalTraceFlags@@SAPEAEXZ` at `0x1004658ef`
- `sqldk!?GetUlTraceFlags@CGlobalTraceFlags@@SAPEAEXZ` at `0x100465904`
- `sqldk!?GetUlTraceFlags@CGlobalTraceFlags@@SAPEAEXZ` at `0x100465928`
- `sqldk!?GetUlTraceFlags@CGlobalTraceFlags@@SAPEAEXZ` at `0x100465497`
- `sqldk!?GetUlTraceFlags@CGlobalTraceFlags@@SAPEAEXZ` at `0x1004654a6`
- `sqldk!?GetUlTraceFlags@CGlobalTraceFlags@@SAPEAEXZ` at `0x1004654fd`
- `sqldk!?GetUlTraceFlags@CGlobalTraceFlags@@SAPEAEXZ` at `0x100465831`
- `sqldk!?GetUlTraceFlags@CGlobalTraceFlags@@SAPEAEXZ` at `0x1004658ef`
- `sqldk!?GetUlTraceFlags@CGlobalTraceFlags@@SAPEAEXZ` at `0x100465904`
- `sqldk!?GetUlTraceFlags@CGlobalTraceFlags@@SAPEAEXZ` at `0x100465928`
- `sqldk!SystemThread_TlsIndex` at `0x1004655bd`
- `sqldk!SystemThread_TlsIndex` at `0x1004656a4`
- `sqldk!SystemThread_TlsIndex` at `0x1004656ec`
- `sqldk!SystemThread_TlsOffset` at `0x1004655c6`
- `sqldk!SystemThread_TlsOffset` at `0x1004656ad`
- `sqldk!SystemThread_TlsOffset` at `0x1004656f5`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1004655df`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1004656c6`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100465710`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1004655df`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1004656c6`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100465710`
- `sqldk!?SOS_OS_OsInfo@@3VOsInfo@@A` at `0x100465913`

## string_xrefs

- `0x100465944`: `CopyThreadStackForDump: Core dump requested by user. Target Thread Id: 0x%08X`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall SQL_SOSNonYieldSchedulerCallback(struct SOS_Task *this, struct SchedulerMonitor::Track *a2)
{
  __int64 UlTraceFlags; // rax
  unsigned int v4; // edx
  unsigned int v5; // r13d
  BOOL v6; // edi
  BOOL v7; // r8d
  __int64 v8; // rdi
  __int64 v9; // rcx
  unsigned __int8 *v10; // rdi
  __int64 v11; // rbx
  __int64 v12; // rcx
  __int64 v13; // rbx
  __int64 v14; // rax
  void *v15; // rsp
  unsigned int v16; // edi
  int v17; // ebx
  bool v18; // bl
  __int64 v19; // rdx
  __int64 v20; // rcx
  char v21; // si
  __int64 v22; // rdi
  __int64 (**v23)(void); // [rsp+0h] [rbp-20060h]
  unsigned int v24; // [rsp+8h] [rbp-20058h]
  unsigned int *v25; // [rsp+10h] [rbp-20050h]
  char v26; // [rsp+50h] [rbp-20010h] BYREF
  struct SchedulerMonitor::Track *v27; // [rsp+20060h] [rbp+0h]
  __int64 (**v28)(void); // [rsp+20068h] [rbp+8h]
  unsigned int v29; // [rsp+20070h] [rbp+10h] BYREF
  unsigned int v30; // [rsp+20074h] [rbp+14h] BYREF
  unsigned int v31; // [rsp+20078h] [rbp+18h] BYREF
  unsigned int v32; // [rsp+2007Ch] [rbp+1Ch]
  BOOL v33; // [rsp+20080h] [rbp+20h]
  unsigned int v34; // [rsp+20084h] [rbp+24h]
  BOOL v35; // [rsp+20088h] [rbp+28h]
  unsigned int v36[2]; // [rsp+20090h] [rbp+30h]
  unsigned __int8 *v37; // [rsp+20098h] [rbp+38h]
  struct SOS_Task *v38; // [rsp+200A0h] [rbp+40h]
  struct SOS_Task *v39; // [rsp+200A8h] [rbp+48h]
  __int64 v40; // [rsp+200B0h] [rbp+50h]
  unsigned __int8 *v41; // [rsp+200B8h] [rbp+58h]
  _BYTE v42[16]; // [rsp+200C0h] [rbp+60h] BYREF
  _BYTE v43[24]; // [rsp+200D0h] [rbp+70h] BYREF
  _BYTE v44[40]; // [rsp+200E8h] [rbp+88h] BYREF
  __int128 v45; // [rsp+20110h] [rbp+B0h] BYREF
  __int64 v46; // [rsp+20120h] [rbp+C0h]
  __int64 v47; // [rsp+20128h] [rbp+C8h]
  __int64 (**v48)(void); // [rsp+20130h] [rbp+D0h]
  struct SOS_Task *v49; // [rsp+20138h] [rbp+D8h]
  __int64 v50; // [rsp+20140h] [rbp+E0h]
  unsigned int v51; // [rsp+20148h] [rbp+E8h]
  unsigned int v52; // [rsp+2014Ch] [rbp+ECh]
  __int64 v53; // [rsp+20150h] [rbp+F0h]
  __int64 v54; // [rsp+20158h] [rbp+F8h]
  _BYTE v55[256]; // [rsp+20160h] [rbp+100h] BYREF
  _BYTE v56[216]; // [rsp+20260h] [rbp+200h] BYREF
  int v57; // [rsp+20338h] [rbp+2D8h]
  __int64 v58; // [rsp+20340h] [rbp+2E0h]
  int v59; // [rsp+20350h] [rbp+2F0h] BYREF
  char Buffer[268]; // [rsp+20354h] [rbp+2F4h] BYREF
  _BYTE v61[4]; // [rsp+20460h] [rbp+400h] BYREF
  int v62; // [rsp+20464h] [rbp+404h]
  int v63; // [rsp+20470h] [rbp+410h]
  __int64 v64; // [rsp+20478h] [rbp+418h]
  __int64 v65; // [rsp+20480h] [rbp+420h]
  _BYTE v66[1232]; // [rsp+20490h] [rbp+430h] BYREF
  _BYTE v67[1232]; // [rsp+20960h] [rbp+900h] BYREF
  __int64 v68; // [rsp+20E30h] [rbp+DD0h]
  int v69; // [rsp+20E38h] [rbp+DD8h]
  __int64 (*v70[32])(void); // [rsp+20E40h] [rbp+DE0h] BYREF

  v40 = -2;
  v38 = this;
  v39 = this;
  v27 = a2;
  if ( (*(_BYTE *)(CGlobalTraceFlags::GetUlTraceFlags() + 1101) & 4) != 0
    || (UlTraceFlags = CGlobalTraceFlags::GetUlTraceFlags(), v4 = 12, (*(_BYTE *)(UlTraceFlags + 456) & 0x40) != 0) )
  {
    v4 = 60;
  }
  v32 = v4;
  v5 = *(_DWORD *)v27 - *((_DWORD *)v27 + 102);
  v34 = v5;
  NonYieldSystemInformation::UpdateNonYieldRingBuffer(
    (NonYieldSystemInformation *)NonYieldSystemInformation::sm_NonYieldSystemInfo,
    v27,
    *(LARGE_INTEGER **)(*((_QWORD *)this + 20) + 5192LL),
    v5,
    v4);
  v6 = (*(_BYTE *)(CGlobalTraceFlags::GetUlTraceFlags() + 157) & 0x40) != 0;
  v33 = v6;
  v35 = v6;
  v7 = g_featureSwitchesDk[81] && SOS_OS_IgnoreNonYieldingScheduler;
  if ( (v6 || SOS_PublicGlobals::sm_CpuConsumers <= 0)
    && *((_DWORD *)v27 + 102)
    && v5 == 12 * (v5 / 0xC)
    && (v5 || v6)
    && !v7 )
  {
    v29 = 0;
    v31 = 0;
    *(_QWORD *)v36 = 0;
    v28 = (__int64 (**)(void))0xFFFFFFFF00000000LL;
    v30 = 0;
    v8 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
    v9 = *(_QWORD *)(v8 + 256);
    if ( !v9 )
    {
      SystemThread::MakeMiniSOSThread(0);
      v9 = *(_QWORD *)(v8 + 256);
    }
    v37 = *(unsigned __int8 **)(v9 + 3208);
    v10 = v37;
    *(_QWORD *)(v9 + 3208) = ex_trans_cexcept_nodump;
    v41 = v10;
    try
    {
      ExcHandler::ExcHandler((ExcHandler *)v44, 0, 0, 0, SilentBackoutHandler, 0);
      HIDWORD(v28) = *(_DWORD *)(*((_QWORD *)this + 20) + 3688LL);
      *(_QWORD *)v36 = *((_QWORD *)this + 19);
      LODWORD(v28) = SOS_Task::DwGetThreadId(this);
      if ( qword_1005572F8 )
        qword_1005572F8(this, &v29, &v31, &v30);
      ExcHandler::~ExcHandler((ExcHandler *)v44);
    }
    catch ( SQLError v43 )
    {
      try
      {
        ExceptionBackout::ExceptionBackout((ExceptionBackout *)v42, (const struct SQLError *)v43);
        ExceptionBackout::~ExceptionBackout((ExceptionBackout *)v42);
      }
      catch ( ShortStackException )
      {
      }
      v5 = v34;
      v38 = v39;
      v33 = v35;
      v10 = v37;
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
    memset_0(v70, 0, sizeof(v70));
    v15 = alloca(131088);
    v37 = (unsigned __int8 *)&v26;
    CSystemTimes::GetIdlePercentage((struct SchedulerMonitor::Track *)((char *)v27 + 144));
    SchedulerMonitor::ProcessTrack::GetProcessUtilization(v27);
    LODWORD(v25) = HIDWORD(v28);
    v24 = v36[0];
    v16 = (unsigned int)v28;
    LODWORD(v23) = (_DWORD)v28;
    scierrlog(0x45DBu, v29, v30, v31);
    if ( (*(_BYTE *)(CGlobalTraceFlags::GetUlTraceFlags() + 1003) & 1) != 0 )
    {
      if ( !SchedulerMonitor::Track::IsWorkerUtilizationHigh(v27)
        && SchedulerMonitor::ProcessTrack::IsProcessStarved(v27) )
      {
        v17 = 0;
        v16 = (unsigned int)v28;
LABEL_33:
        v61[0] = 0;
        v62 = 0;
        v63 = 0;
        v64 = 0;
        v65 = 0;
        v68 = 0;
        v69 = 0;
        memset_0(v66, 0, sizeof(v66));
        memset_0(v67, 0, sizeof(v67));
        v18 = v17
           && !(v5 % v32)
           && (!dword_1005589BC || v33)
           && (SOS_Tracing_osTrace & 0x40) == 0
           && (*(_BYTE *)(CGlobalTraceFlags::GetUlTraceFlags() + 157) & 0x10) == 0;
        if ( (*(_BYTE *)(CGlobalTraceFlags::GetUlTraceFlags() + 317) & 0x10) != 0
          && OsInfo::IsXPlatInstance(SOS_OS_OsInfo)
          && v18
          && (*(_BYTE *)(CGlobalTraceFlags::GetUlTraceFlags() + 319) & 1) == 0 )
        {
          v59 = 753;
          StringCchPrintfA(
            Buffer,
            0x100u,
            "CopyThreadStackForDump: Core dump requested by user. Target Thread Id: 0x%08X",
            v16);
          SOS_OS::TriggerDump((const struct SYSTEM_SQLPAL_TRIGGER_DUMP_INFO *)&v59);
        }
        if ( CopiedStackInfo::CopyThreadStackForDump((CopiedStackInfo *)v61, v37, 0x20000u, v16, v23, v24, v25) )
        {
          v21 = 1;
          v20 = *((_QWORD *)v27 + 48);
          v19 = *((_QWORD *)v27 + 47);
          v22 = qword_10052F130;
          if ( qword_10052F130 )
          {
            v45 = 0;
            v46 = 0;
            v47 = 0;
            v48 = v28;
            v49 = v38;
            v50 = *(_QWORD *)v36;
            v51 = v29;
            v52 = v30;
            v53 = v19;
            v54 = v20;
            memset_0(v55, 0, sizeof(v55));
            v57 = 0;
            v58 = 0;
            if ( *(_QWORD *)(v22 + 64) )
              StackFrames<24>::CaptureCurrent(v56, 1);
            SOS_RingBuffer::StoreRecordInternalWithoutEvent(v22, &v45, v56);
          }
        }
        else
        {
          v21 = 0;
        }
        if ( v18 )
        {
          dword_1005589BC = 1;
          v69 = 256;
          stackTrace(v20, v19, L"Non-yielding Scheduler", 1697, 2);
        }
        if ( v21 )
        {
          LogSystemMetadataNotSentToClient(L"Copied stack", v19);
          LogFramesRVA(v70, 0, 0);
        }
        v61[0] = 0;
        v69 = 0;
        return;
      }
      v16 = (unsigned int)v28;
    }
    v17 = 1;
    goto LABEL_33;
  }
}

```

## disassembly

```asm
0x100465450  push    rbp
0x100465452  push    rsi
0x100465453  push    rdi
0x100465454  push    r12
0x100465456  push    r13
0x100465458  push    r14
0x10046545a  push    r15
0x10046545c  sub     rsp, 0F60h
0x100465463  lea     rbp, [rsp+70h]
0x100465468  mov     [rbp+0F20h+var_ED0], 0FFFFFFFFFFFFFFFEh
0x100465470  mov     [rbp+0F20h+arg_10], rbx
0x100465477  mov     rax, cs:__security_cookie
0x10046547e  xor     rax, rbp
0x100465481  mov     [rbp+0F20h+var_40], rax
0x100465488  mov     rbx, rcx
0x10046548b  mov     [rbp+0F20h+var_EE0], rcx
0x10046548f  mov     [rbp+0F20h+var_ED8], rcx
0x100465493  mov     [rbp+0F20h+var_F20], rdx
0x100465497  call    cs:__imp_?GetUlTraceFlags@CGlobalTraceFlags@@SAPEAEXZ; CGlobalTraceFlags::GetUlTraceFlags(void)
0x10046549d  test    byte ptr [rax+44Dh], 4
0x1004654a4  jnz     short loc_1004654BA
0x1004654a6  call    cs:__imp_?GetUlTraceFlags@CGlobalTraceFlags@@SAPEAEXZ; CGlobalTraceFlags::GetUlTraceFlags(void)
0x1004654ac  test    byte ptr [rax+1C8h], 40h
0x1004654b3  mov     edx, 0Ch
0x1004654b8  jz      short loc_1004654BF
0x1004654ba  mov     edx, 3Ch ; '<'
0x1004654bf  mov     [rbp+0F20h+var_F04], edx
0x1004654c2  mov     rcx, [rbp+0F20h+var_F20]
0x1004654c6  mov     rax, [rbp+0F20h+var_F20]
0x1004654ca  mov     r13d, [rax]
0x1004654cd  sub     r13d, [rcx+198h]
0x1004654d4  mov     [rbp+0F20h+var_EFC], r13d
0x1004654d8  mov     r8, [rbx+0A0h]
0x1004654df  mov     dword ptr [rsp+0F90h+var_F70], edx; unsigned int
0x1004654e3  mov     r9d, r13d; unsigned int
0x1004654e6  mov     r8, [r8+1448h]; struct SOS_Node *
0x1004654ed  mov     rdx, [rbp+0F20h+var_F20]; struct SchedulerMonitor::Track *
0x1004654f1  lea     rcx, ?sm_NonYieldSystemInfo@NonYieldSystemInformation@@0V1@A; this
0x1004654f8  call    ?UpdateNonYieldRingBuffer@NonYieldSystemInformation@@QEAAXPEBVTrack@SchedulerMonitor@@PEAVSOS_Node@@IK@Z; NonYieldSystemInformation::UpdateNonYieldRingBuffer(SchedulerMonitor::Track const *,SOS_Node *,uint,ulong)
0x1004654fd  call    cs:__imp_?GetUlTraceFlags@CGlobalTraceFlags@@SAPEAEXZ; CGlobalTraceFlags::GetUlTraceFlags(void)
0x100465503  movzx   ecx, byte ptr [rax+9Dh]
0x10046550a  shr     cl, 6
0x10046550d  movzx   edi, cl
0x100465510  and     edi, 1
0x100465513  mov     [rbp+0F20h+var_F00], edi
0x100465516  mov     [rbp+0F20h+var_EF8], edi
0x100465519  mov     rax, cs:__imp_?g_featureSwitchesDk@@3VCFeatureSwitchesDk@@A; CFeatureSwitchesDk g_featureSwitchesDk
0x100465520  cmp     byte ptr [rax+51h], 0
0x100465524  jz      short loc_10046553D
0x100465526  mov     rax, cs:__imp_?SOS_OS_IgnoreNonYieldingScheduler@@3HA; int SOS_OS_IgnoreNonYieldingScheduler
0x10046552d  cmp     dword ptr [rax], 0
0x100465530  jz      short loc_10046553D
0x100465532  mov     r8d, 1
0x100465538  xor     r12d, r12d
0x10046553b  jmp     short loc_100465543
0x10046553d  xor     r12d, r12d
0x100465540  mov     r8d, r12d
0x100465543  test    edi, edi
0x100465545  jnz     short loc_100465558
0x100465547  mov     rax, cs:__imp_?sm_CpuConsumers@SOS_PublicGlobals@@2JC; long volatile SOS_PublicGlobals::sm_CpuConsumers
0x10046554e  mov     ecx, [rax]
0x100465550  test    ecx, ecx
0x100465552  jg      loc_100465ADB
0x100465558  mov     rax, [rbp+0F20h+var_F20]
0x10046555c  cmp     dword ptr [rax+198h], 0
0x100465563  jz      loc_100465ADB
0x100465569  mov     eax, 0AAAAAAABh
0x10046556e  mul     r13d
0x100465571  shr     edx, 3
0x100465574  lea     ecx, [rdx+rdx*2]
0x100465577  shl     ecx, 2
0x10046557a  cmp     r13d, ecx
0x10046557d  jnz     loc_100465ADB
0x100465583  test    r13d, r13d
0x100465586  jnz     short loc_100465590
0x100465588  test    edi, edi
0x10046558a  jz      loc_100465ADB
0x100465590  test    r8d, r8d
0x100465593  jnz     loc_100465ADB
0x100465599  mov     [rbp+0F20h+var_F10], r12d
0x10046559d  mov     [rbp+0F20h+var_F08], r12d
0x1004655a1  mov     dword ptr [rbp+0F20h+var_F18+4], 0FFFFFFFFh
0x1004655a8  mov     qword ptr [rbp+0F20h+var_EF0], r12
0x1004655ac  mov     dword ptr [rbp+0F20h+var_F18], r12d
0x1004655b0  mov     [rbp+0F20h+var_F0C], r12d
0x1004655b4  mov     rdx, gs:58h
0x1004655bd  mov     rax, cs:__imp_SystemThread_TlsIndex
0x1004655c4  mov     ecx, [rax]
0x1004655c6  mov     rax, cs:__imp_SystemThread_TlsOffset
0x1004655cd  mov     edi, [rax]
0x1004655cf  add     rdi, [rdx+rcx*8]
0x1004655d3  mov     rcx, [rdi+100h]
0x1004655da  test    rcx, rcx
0x1004655dd  jnz     short loc_1004655EC
0x1004655df  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x1004655e5  mov     rcx, [rdi+100h]
0x1004655ec  mov     rdi, [rcx+0C88h]
0x1004655f3  mov     [rbp+0F20h+var_EE8], rdi
0x1004655f7  mov     rax, cs:__imp_?ex_trans_cexcept_nodump@@YAXIPEAU_EXCEPTION_POINTERS@@@Z; ex_trans_cexcept_nodump(uint,_EXCEPTION_POINTERS *)
0x1004655fe  mov     [rcx+0C88h], rax
0x100465605  mov     [rbp+0F20h+var_EC8], rdi
0x100465609  xor     edx, edx; unsigned __int16
0x10046560b  mov     [rsp+0F90h+var_F68], r12; struct Worker *
0x100465610  mov     rax, cs:__imp_?SilentBackoutHandler@@YAHHHHHPEAD@Z; SilentBackoutHandler(int,int,int,int,char *)
0x100465617  mov     [rsp+0F90h+var_F70], rax; int (*)(int, int, int, int, char *)
0x10046561c  xor     r9d, r9d; unsigned __int8
0x10046561f  xor     r8d, r8d; unsigned __int8
0x100465622  lea     rcx, [rbp+0F20h+var_E98]; this
0x100465629  call    ??0ExcHandler@@QEAA@GEEP6AHHHHHPEAD@ZPEAVWorker@@@Z; ExcHandler::ExcHandler(ushort,uchar,uchar,int (*)(int,int,int,int,char *),Worker *)
0x10046562e  nop
0x10046562f  mov     rax, [rbx+0A0h]
0x100465636  mov     ecx, [rax+0E68h]
0x10046563c  mov     dword ptr [rbp+0F20h+var_F18+4], ecx
0x10046563f  mov     rax, [rbx+98h]
0x100465646  mov     qword ptr [rbp+0F20h+var_EF0], rax
0x10046564a  mov     rcx, rbx; this
0x10046564d  call    ?DwGetThreadId@SOS_Task@@QEAAKXZ; SOS_Task::DwGetThreadId(void)
0x100465652  mov     dword ptr [rbp+0F20h+var_F18], eax
0x100465655  mov     rax, cs:qword_1005572F8
0x10046565c  test    rax, rax
0x10046565f  jz      short loc_100465673
0x100465661  lea     r9, [rbp+0F20h+var_F0C]
0x100465665  lea     r8, [rbp+0F20h+var_F08]
0x100465669  lea     rdx, [rbp+0F20h+var_F10]
0x10046566d  mov     rcx, rbx
0x100465670  call    rax ; qword_1005572F8
0x100465672  nop
0x100465673  lea     rcx, [rbp+0F20h+var_E98]; this
0x10046567a  call    ??1ExcHandler@@QEAA@XZ; ExcHandler::~ExcHandler(void)
0x10046567f  nop
0x100465680  jmp     short loc_10046569B
0x100465682  xor     r12d, r12d
0x100465685  mov     r13d, [rbp+0F20h+var_EFC]
0x100465689  mov     rax, [rbp+0F20h+var_ED8]
0x10046568d  mov     [rbp+0F20h+var_EE0], rax
0x100465691  mov     eax, [rbp+0F20h+var_EF8]
0x100465694  mov     [rbp+0F20h+var_F00], eax
0x100465697  mov     rdi, [rbp+0F20h+var_EE8]
0x10046569b  mov     rdx, gs:58h
0x1004656a4  mov     rax, cs:__imp_SystemThread_TlsIndex
0x1004656ab  mov     ecx, [rax]
0x1004656ad  mov     rax, cs:__imp_SystemThread_TlsOffset
0x1004656b4  mov     ebx, [rax]
0x1004656b6  add     rbx, [rdx+rcx*8]
0x1004656ba  mov     rcx, [rbx+100h]
0x1004656c1  test    rcx, rcx
0x1004656c4  jnz     short loc_1004656D3
0x1004656c6  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x1004656cc  mov     rcx, [rbx+100h]
0x1004656d3  cmp     dword ptr [rcx+22Ch], 0
0x1004656da  jz      short loc_1004656E3
0x1004656dc  call    cs:__imp_?ExceptionPostCatchActions@@YAXPEAVWorker@@@Z; ExceptionPostCatchActions(Worker *)
0x1004656e2  nop
0x1004656e3  mov     rdx, gs:58h
0x1004656ec  mov     rax, cs:__imp_SystemThread_TlsIndex
0x1004656f3  mov     ecx, [rax]
0x1004656f5  mov     rax, cs:__imp_SystemThread_TlsOffset
0x1004656fc  mov     ebx, [rax]
0x1004656fe  add     rbx, [rdx+rcx*8]
0x100465702  mov     rax, [rbx+100h]
0x100465709  test    rax, rax
0x10046570c  jnz     short loc_10046571D
0x10046570e  xor     ecx, ecx
0x100465710  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x100465716  mov     rax, [rbx+100h]
0x10046571d  mov     [rax+0C88h], rdi
0x100465724  xor     edx, edx; Val
0x100465726  mov     r8d, 100h; Size
0x10046572c  lea     rcx, [rbp+0F20h+var_140]; void *
0x100465733  call    memset_0
0x100465738  mov     eax, 20010h
0x10046573d  call    _alloca_probe
0x100465742  sub     rsp, rax
0x100465745  lea     rax, [rsp+20FA0h+var_20F30]
0x10046574a  mov     [rbp+0F20h+var_EE8], rax
0x10046574e  mov     rcx, [rbp+0F20h+var_F20]
0x100465752  mov     r9, [rbp+0F20h+var_F20]
0x100465756  mov     r10, 346DC5D63886594Bh
0x100465760  mov     rax, r10
0x100465763  imul    qword ptr [r9+0A8h]
0x10046576a  mov     r15, rdx
0x10046576d  sar     r15, 0Bh
0x100465771  mov     rax, r15
0x100465774  shr     rax, 3Fh
0x100465778  add     r15, rax
0x10046577b  mov     rax, r10
0x10046577e  imul    qword ptr [rcx+180h]
0x100465785  mov     r14, rdx
0x100465788  sar     r14, 0Bh
0x10046578c  mov     rax, r14
0x10046578f  shr     rax, 3Fh
0x100465793  add     r14, rax
0x100465796  mov     rax, r10
0x100465799  imul    qword ptr [rcx+178h]
0x1004657a0  mov     rsi, rdx
0x1004657a3  sar     rsi, 0Bh
0x1004657a7  mov     rcx, rsi
0x1004657aa  shr     rcx, 3Fh
0x1004657ae  add     rsi, rcx
0x1004657b1  mov     r8, [rbp+0F20h+var_F20]
0x1004657b5  mov     rax, r10
0x1004657b8  imul    qword ptr [r8+158h]
0x1004657bf  mov     rdi, rdx
0x1004657c2  sar     rdi, 0Bh
0x1004657c6  mov     rax, rdi
0x1004657c9  shr     rax, 3Fh
0x1004657cd  add     rdi, rax
0x1004657d0  lea     rcx, [r9+90h]
0x1004657d7  call    cs:__imp_?GetIdlePercentage@CSystemTimes@@QEBAIXZ; CSystemTimes::GetIdlePercentage(void)
0x1004657dd  mov     ebx, eax
0x1004657df  mov     rcx, [rbp+0F20h+var_F20]
0x1004657e3  call    cs:__imp_?GetProcessUtilization@ProcessTrack@SchedulerMonitor@@QEBAIXZ; SchedulerMonitor::ProcessTrack::GetProcessUtilization(void)
0x1004657e9  mov     [rsp+20FA0h+var_20F40], r15
0x1004657ee  mov     [rsp+20FA0h+var_20F48], ebx
0x1004657f2  mov     [rsp+20FA0h+var_20F50], eax
0x1004657f6  mov     [rsp+20FA0h+var_20F58], r14
0x1004657fb  mov     [rsp+20FA0h+var_20F60], rsi
0x100465800  mov     [rsp+20FA0h+var_20F68], rdi
0x100465805  mov     eax, dword ptr [rbp+0F20h+var_F18+4]
0x100465808  mov     dword ptr [rsp+20FA0h+var_20F70], eax; unsigned int *
0x10046580c  mov     rax, qword ptr [rbp+0F20h+var_EF0]
0x100465810  mov     qword ptr [rsp+20FA0h+var_20F78], rax; unsigned int
0x100465815  mov     edi, dword ptr [rbp+0F20h+var_F18]
0x100465818  mov     dword ptr [rsp+20FA0h+var_20F80], edi; __int64 (**)(void)
0x10046581c  mov     r9d, [rbp+0F20h+var_F08]
0x100465820  mov     r8d, [rbp+0F20h+var_F0C]
0x100465824  mov     edx, [rbp+0F20h+var_F10]
0x100465827  mov     ecx, 45DBh; unsigned int
0x10046582c  call    ?scierrlog@@YAXKZZ; scierrlog(ulong,...)
0x100465831  call    cs:__imp_?GetUlTraceFlags@CGlobalTraceFlags@@SAPEAEXZ; CGlobalTraceFlags::GetUlTraceFlags(void)
0x100465837  test    byte ptr [rax+3EBh], 1
0x10046583e  jz      short loc_100465867
0x100465840  mov     rcx, [rbp+0F20h+var_F20]
0x100465844  call    cs:__imp_?IsWorkerUtilizationHigh@Track@SchedulerMonitor@@QEBAHXZ; SchedulerMonitor::Track::IsWorkerUtilizationHigh(void)
0x10046584a  test    eax, eax
0x10046584c  jnz     short loc_100465864
0x10046584e  mov     rcx, [rbp+0F20h+var_F20]
0x100465852  call    cs:__imp_?IsProcessStarved@ProcessTrack@SchedulerMonitor@@QEBAHXZ; SchedulerMonitor::ProcessTrack::IsProcessStarved(void)
0x100465858  test    eax, eax
0x10046585a  jz      short loc_100465864
0x10046585c  mov     ebx, r12d
0x10046585f  mov     edi, dword ptr [rbp+0F20h+var_F18]
0x100465862  jmp     short loc_10046586C
0x100465864  mov     edi, dword ptr [rbp+0F20h+var_F18]
0x100465867  mov     ebx, 1
0x10046586c  mov     [rbp+0F20h+var_B20], 0
0x100465873  mov     [rbp+0F20h+var_B1C], r12d
0x10046587a  mov     [rbp+0F20h+var_B10], r12d
0x100465881  mov     [rbp+0F20h+var_B08], r12
0x100465888  mov     [rbp+0F20h+var_B00], r12
0x10046588f  mov     [rbp+0F20h+var_150], r12
0x100465896  mov     [rbp+0F20h+var_148], r12d
0x10046589d  xor     edx, edx; Val
0x10046589f  mov     r8d, 4D0h; Size
0x1004658a5  lea     rcx, [rbp+0F20h+var_AF0]; void *
0x1004658ac  call    memset_0
0x1004658b1  xor     edx, edx; Val
0x1004658b3  mov     r8d, 4D0h; Size
0x1004658b9  lea     rcx, [rbp+0F20h+var_620]; void *
0x1004658c0  call    memset_0
0x1004658c5  nop
0x1004658c6  test    ebx, ebx
0x1004658c8  jz      short loc_100465902
0x1004658ca  xor     edx, edx
0x1004658cc  mov     eax, r13d
0x1004658cf  div     [rbp+0F20h+var_F04]
0x1004658d2  test    edx, edx
0x1004658d4  jnz     short loc_100465902
0x1004658d6  cmp     cs:dword_1005589BC, edx
0x1004658dc  jz      short loc_1004658E3
0x1004658de  cmp     [rbp+0F20h+var_F00], edx
0x1004658e1  jz      short loc_100465902
0x1004658e3  mov     rax, cs:__imp_?SOS_Tracing_osTrace@@3KA; ulong SOS_Tracing_osTrace
0x1004658ea  test    byte ptr [rax], 40h
0x1004658ed  jnz     short loc_100465902
0x1004658ef  call    cs:__imp_?GetUlTraceFlags@CGlobalTraceFlags@@SAPEAEXZ; CGlobalTraceFlags::GetUlTraceFlags(void)
0x1004658f5  test    byte ptr [rax+9Dh], 10h
0x1004658fc  jnz     short loc_100465902
0x1004658fe  mov     bl, 1
0x100465900  jmp     short loc_100465904
0x100465902  xor     bl, bl
0x100465904  call    cs:__imp_?GetUlTraceFlags@CGlobalTraceFlags@@SAPEAEXZ; CGlobalTraceFlags::GetUlTraceFlags(void)
0x10046590a  test    byte ptr [rax+13Dh], 10h
0x100465911  jz      short loc_100465969
0x100465913  mov     rcx, cs:__imp_?SOS_OS_OsInfo@@3VOsInfo@@A; OsInfo SOS_OS_OsInfo
0x10046591a  call    cs:__imp_?IsXPlatInstance@OsInfo@@QEBA?B_NXZ; OsInfo::IsXPlatInstance(void)
0x100465920  test    al, al
0x100465922  jz      short loc_100465969
0x100465924  test    bl, bl
0x100465926  jz      short loc_100465969
0x100465928  call    cs:__imp_?GetUlTraceFlags@CGlobalTraceFlags@@SAPEAEXZ; CGlobalTraceFlags::GetUlTraceFlags(void)
0x10046592e  test    byte ptr [rax+13Fh], 1
0x100465935  jnz     short loc_100465969
0x100465937  mov     [rbp+0F20h+var_C30], 2F1h
0x100465941  mov     r9d, edi
0x100465944  lea     r8, aCopythreadstac; "CopyThreadStackForDump: Core dump reque"...
0x10046594b  mov     edx, 100h; unsigned __int64
0x100465950  lea     rcx, [rbp+0F20h+Buffer]; Buffer
0x100465957  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x10046595c  lea     rcx, [rbp+0F20h+var_C30]
  ... truncated ...
```
