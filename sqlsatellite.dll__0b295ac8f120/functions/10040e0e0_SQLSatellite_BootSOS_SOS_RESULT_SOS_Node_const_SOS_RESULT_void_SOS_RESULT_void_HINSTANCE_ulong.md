# SQLSatellite_BootSOS(SOS_RESULT (*)(SOS_Node * const),SOS_RESULT (*)(void),SOS_RESULT (*)(void),HINSTANCE__ *,ulong)

- ea: `0x10040e0e0`
- end: `0x10040e51f`
- name: `?SQLSatellite_BootSOS@@YAJP6A?AW4SOS_RESULT@@QEAVSOS_Node@@@ZP6A?AW41@XZ2PEAUHINSTANCE__@@K@Z`
- size: `1087`
- prototype: `__int64 __fastcall(enum SOS_RESULT (__high *)(struct SOS_Node *const), enum SOS_RESULT (__high *)(void), enum SOS_RESULT (__high *)(void), HINSTANCE, char)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x100404a00`

## callees

- `0x10040dc90`
- `0x10040de90`
- `0x10040e0e0`
- `0x100486af0`
- `0x1004880d0`

## import_xrefs

- `KERNEL32!SetConsoleCtrlHandler` at `0x10040e297`
- `KERNEL32!SetConsoleCtrlHandler` at `0x10040e297`
- `KERNEL32!HeapSetInformation` at `0x10040e14a`
- `KERNEL32!HeapSetInformation` at `0x10040e14a`
- `KERNEL32!GetLastError` at `0x10040e2a1`
- `KERNEL32!GetLastError` at `0x10040e2a1`
- `sqldk!?sm_ResourceManager@SOS_PublicGlobals@@2VSOS_ResourceManager@@A` at `0x10040e464`
- `sqldk!?sm_ResourceManager@SOS_PublicGlobals@@2VSOS_ResourceManager@@A` at `0x10040e472`
- `sqldk!?sm_MemUtilizationEffectCallbackList@SOS_PublicGlobals@@2V?$TCallbackList@V?$TCallback@XQEBUMemoryUtilizationInfo@@W4Effects@MemoryUtilizationEffects@@QEBUEffectInfo@3@VNullType@@@@@@A` at `0x10040e401`
- `sqldk!?sm_NonYieldIOCPCallbackList@SOS_PublicGlobals@@2V?$TCallbackList@V?$TCallback@XPEBVTrack@SchedulerMonitor@@VNullType@@V3@V3@@@@@A` at `0x10040e3d6`
- `sqldk!?SOS_OS_StackTraceRoutine@@3P6AXPEAXPEB_WKPEAPEAX@ZEA` at `0x10040e376`
- `sqldk!?Boot@SOS_OS@@SA?AW4SOS_RESULT@@XZ` at `0x10040e4c4`
- `sqldk!?Boot@SOS_OS@@SA?AW4SOS_RESULT@@XZ` at `0x10040e4c4`
- `sqldk!?RegisterProcess@SOS_OS@@SA?AW4SOS_RESULT@@PEAVProcessConfig@@W4SOS_CallerType@@@Z` at `0x10040e179`
- `sqldk!?RegisterProcess@SOS_OS@@SA?AW4SOS_RESULT@@PEAVProcessConfig@@W4SOS_CallerType@@@Z` at `0x10040e179`
- `sqldk!??1AutoMakeMicroSOSThread@@QEAA@XZ` at `0x10040e4dc`
- `sqldk!??1AutoMakeMicroSOSThread@@QEAA@XZ` at `0x10040e4ea`
- `sqldk!??1AutoMakeMicroSOSThread@@QEAA@XZ` at `0x10040e4dc`
- `sqldk!??1AutoMakeMicroSOSThread@@QEAA@XZ` at `0x10040e4ea`
- `sqldk!??0AutoMakeMicroSOSThread@@QEAA@QEAX_JPEAPEAXHPEAVSOS_Scheduler@@PEAVIMemObj@@@Z` at `0x10040e20e`
- `sqldk!??0AutoMakeMicroSOSThread@@QEAA@QEAX_JPEAPEAXHPEAVSOS_Scheduler@@PEAVIMemObj@@@Z` at `0x10040e20e`
- `sqldk!?NotifyTraceOn@SOS_Tracing@@SAXK@Z` at `0x10040e48f`
- `sqldk!?NotifyTraceOn@SOS_Tracing@@SAXK@Z` at `0x10040e49a`
- `sqldk!?NotifyTraceOn@SOS_Tracing@@SAXK@Z` at `0x10040e48f`
- `sqldk!?NotifyTraceOn@SOS_Tracing@@SAXK@Z` at `0x10040e49a`
- `sqldk!?AddStuckDispatcherCallback@SOS_OS@@SAXPEAV?$TCallback@XQEBVSOS_DispatcherBase@@VNullType@@V2@V2@@@@Z` at `0x10040e45e`
- `sqldk!?AddStuckDispatcherCallback@SOS_OS@@SAXPEAV?$TCallback@XQEBVSOS_DispatcherBase@@VNullType@@V2@V2@@@@Z` at `0x10040e45e`
- `sqldk!?SetAbortHandler@SOS_OS@@SAXXZ` at `0x10040e314`
- `sqldk!?SetAbortHandler@SOS_OS@@SAXXZ` at `0x10040e314`
- `sqldk!?SetInvalidParameterHandler@SOS_OS@@SAP6AXPEB_W00I_K@ZXZ` at `0x10040e30e`
- `sqldk!?SetInvalidParameterHandler@SOS_OS@@SAP6AXPEB_W00I_K@ZXZ` at `0x10040e30e`
- `sqldk!?SetUnhandledExceptionFilter@SOS_OS@@SAXXZ` at `0x10040e308`
- `sqldk!?SetUnhandledExceptionFilter@SOS_OS@@SAXXZ` at `0x10040e308`
- `sqldk!?PreInitSOS@@YAXUSQLDK_Callbacks@@H@Z` at `0x10040e1b6`
- `sqldk!?PreInitSOS@@YAXUSQLDK_Callbacks@@H@Z` at `0x10040e1b6`
- `sqldk!?sm_NonYieldSchedulerCallbackList@SOS_PublicGlobals@@2V?$TCallbackList@V?$TCallback@XPEAVSOS_Task@@PEBVTrack@SchedulerMonitor@@VNullType@@V4@@@@@A` at `0x10040e380`
- `sqldk!?SOS_OS_ErrorLogRoutine@@3P6AXKZZEA` at `0x10040e321`
- `sqldk!?sm_DeadlockSchedulerCallbackList@SOS_PublicGlobals@@2V?$TCallbackList@V?$TCallback@XGIPEBVProcessTrack@SchedulerMonitor@@VNullType@@@@@@A` at `0x10040e3ab`
- `sqldk!?sm_SchedLsSize@SOS_PublicGlobals@@2FA` at `0x10040e2dc`
- `sqldk!?sm_BootFinalize@SOS_PublicGlobals@@2P6A?AW4SOS_RESULT@@XZEA` at `0x10040e2fe`
- `sqldk!?SOS_OS_ExceptionPrintRoutine@@3P6AXHHHPEAD@ZEA` at `0x10040e343`
- `sqldk!?SOS_OS_LogUnlocalizedRoutine@@3P6AXPEB_WZZEA` at `0x10040e332`
- `sqldk!?sm_WorkerLsBitmap@SOS_PublicGlobals@@2VSmallBitmap@@A` at `0x10040e1bc`
- `sqldk!?HRESULT_FROM_SOS_RESULT_Uncommon@@YAJW4SOS_RESULT@@@Z` at `0x10040e185`
- `sqldk!?HRESULT_FROM_SOS_RESULT_Uncommon@@YAJW4SOS_RESULT@@@Z` at `0x10040e4d0`
- `sqldk!?HRESULT_FROM_SOS_RESULT_Uncommon@@YAJW4SOS_RESULT@@@Z` at `0x10040e185`
- `sqldk!?HRESULT_FROM_SOS_RESULT_Uncommon@@YAJW4SOS_RESULT@@@Z` at `0x10040e4d0`
- `sqldk!?SOS_OS_UserLogRoutine@@3P6AXHHHKZZEA` at `0x10040e354`
- `sqldk!?sm_NodeLsSize@SOS_PublicGlobals@@2FA` at `0x10040e2d2`
- `sqldk!?sm_NodeInit@SOS_PublicGlobals@@2P6A?AW4SOS_RESULT@@QEAVSOS_Node@@@ZEA` at `0x10040e2ed`
- `sqldk!?sm_DumpExceptionHandlerRoutine@SOS_PublicGlobals@@2P6AHPEAU_EXCEPTION_POINTERS@@@ZEA` at `0x10040e365`
- `sqldk!?sm_NonYieldRMCallbackList@SOS_PublicGlobals@@2V?$TCallbackList@V?$TCallback@X$$CB_JPEBVResourceClerk@@PEBVTrack@SchedulerMonitor@@VNullType@@@@@@A` at `0x10040e42c`
- `sqldk!?CreateMemObject@MemoryObjectFactory@@SAPEAVIMemObj@@W4SOSHOST_MEMOBJ_ID@@KPEAVPageAllocator@@FF@Z` at `0x10040e280`
- `sqldk!?CreateMemObject@MemoryObjectFactory@@SAPEAVIMemObj@@W4SOSHOST_MEMOBJ_ID@@KPEAVPageAllocator@@FF@Z` at `0x10040e280`
- `sqldk!SystemThread_TlsIndex` at `0x10040e21e`
- `sqldk!SystemThread_TlsOffset` at `0x10040e227`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10040e242`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10040e242`
- `sqldk!?MemoryNode_MaxMemoryPagesLimit@@3_JA` at `0x10040e4ba`
- `sqldk!?SOS_OS_sm_osProcessStatus@@3KA` at `0x10040e12e`
- `sqldk!?sm_osStats@SOS_PublicGlobals@@2KA` at `0x10040e480`
- `sqldk!?sm_osMemoryClerk@SOS_PublicGlobals@@2VMemoryClerk@@A` at `0x10040e256`

## pseudocode

```c
// write access to const memory has been detected, the output may be wrong!
// Hidden C++ exception states: #wind=1
__int64 __fastcall SQLSatellite_BootSOS(
        enum SOS_RESULT (__high *a1)(struct SOS_Node *const),
        __int64 (*a2)(void),
        enum SOS_RESULT (__high *a3)(void),
        HINSTANCE a4,
        char a5)
{
  __int64 result; // rax
  unsigned int v10; // eax
  __int64 v11; // r8
  unsigned __int64 v12; // rcx
  unsigned __int64 v13; // rcx
  void *v14; // rsp
  void *v15; // rsp
  __int64 v16; // rdi
  __int64 v17; // rbx
  char *v18; // r8
  signed int LastError; // eax
  unsigned int v20; // ebx
  unsigned int v21; // eax
  unsigned int ConfiguredMemoryMB; // eax
  int v23; // [rsp+20h] [rbp-20h]
  void *v24[6]; // [rsp+40h] [rbp+0h] BYREF
  _BYTE v25[6048]; // [rsp+70h] [rbp+30h] BYREF

  v24[4] = (void *)-2LL;
  if ( (SOS_OS_sm_osProcessStatus & 1) == 0 )
  {
    HeapSetInformation(0, HeapEnableTerminationOnCorruption, 0, 0);
    if ( (a5 & 1) != 0 )
    {
      result = InitializeSqlDumper(a4);
      if ( (int)result < 0 )
      {
        _mm_lfence();
        return result;
      }
    }
    v10 = SOS_OS::RegisterProcess(clientProcessConfig, 1);
    if ( v10 )
      return HRESULT_FROM_SOS_RESULT_Uncommon(v10);
    v24[0] = utassert_fail_imp;
    v24[1] = 0;
    v24[2] = &off_1004EDE50;
    PreInitSOS(v24, 21);
    v11 = SOS_PublicGlobals::sm_WorkerLsBitmap[1];
    v12 = 8 * v11 + 15;
    if ( v12 <= 8 * v11 )
      v12 = 0xFFFFFFFFFFFFFF0LL;
    v13 = v12 & 0xFFFFFFFFFFFFFFF0uLL;
    v14 = alloca(v13);
    v15 = alloca(v13);
    AutoMakeMicroSOSThread::AutoMakeMicroSOSThread((AutoMakeMicroSOSThread *)v25, 0, v11, v24, 1, 0, 0);
    v16 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
    v17 = *(_QWORD *)(v16 + 256);
    if ( !v17 )
    {
      SystemThread::MakeMiniSOSThread(0);
      v17 = *(_QWORD *)(v16 + 256);
    }
    *(_DWORD *)(v17 + 616) |= 0x20u;
    v18 = (char *)&SOS_PublicGlobals::sm_osMemoryClerk + 64;
    if ( !SOS_PublicGlobals::sm_osMemoryClerk )
      v18 = 0;
    LOWORD(v23) = 128;
    *(_QWORD *)(v17 + 1000) = MemoryObjectFactory::CreateMemObject(1, 4, v18, 8, v23);
    if ( !SetConsoleCtrlHandler(ControlHandler, 1) )
    {
      LastError = GetLastError();
      v20 = LastError;
      if ( LastError > 0 )
        v20 = (unsigned __int16)LastError | 0x80070000;
      goto LABEL_22;
    }
    qword_100556CA8 = (__int64)a1;
    qword_100556D28 = (__int64)a3;
    SOS_PublicGlobals::sm_NodeLsSize = 12;
    SOS_PublicGlobals::sm_SchedLsSize = 8;
    SOS_PublicGlobals::sm_NodeInit = (enum SOS_RESULT (__high *)(struct SOS_Node *const))SQLSatellite_SOSNodeInitRoutine;
    SOS_PublicGlobals::sm_BootFinalize = (enum SOS_RESULT (__high *)(void))SQLSatellite_SOSBootFinalizeRoutine;
    SOS_OS::SetUnhandledExceptionFilter();
    SOS_OS::SetInvalidParameterHandler();
    SOS_OS::SetAbortHandler();
    SOS_OS_ErrorLogRoutine = scierrlog;
    SOS_OS_LogUnlocalizedRoutine = SOSLogToErrorLog;
    SOS_OS_ExceptionPrintRoutine = (void (*)(int, int, int, char *))ex_vcallprint_no_dump_no_retval;
    SOS_OS_UserLogRoutine = user_log;
    SOS_PublicGlobals::sm_DumpExceptionHandlerRoutine = (int (*)(struct _EXCEPTION_POINTERS *))SqlDumpExceptionHandler;
    SOS_OS_StackTraceRoutine = (void (*)(void *, const wchar_t *, unsigned int, void **))stackTraceCallBack;
    qword_1004EDE60 = *((_QWORD *)&SOS_PublicGlobals::sm_NonYieldSchedulerCallbackList + 1);
    **((_QWORD **)&SOS_PublicGlobals::sm_NonYieldSchedulerCallbackList + 1) = &qword_1004EDE58;
    *((_QWORD *)&SOS_PublicGlobals::sm_NonYieldSchedulerCallbackList + 1) = &qword_1004EDE58;
    qword_1004EDE58 = SOS_PublicGlobals::sm_NonYieldSchedulerCallbackList;
    qword_1004EE820 = *((_QWORD *)&SOS_PublicGlobals::sm_DeadlockSchedulerCallbackList + 1);
    **((_QWORD **)&SOS_PublicGlobals::sm_DeadlockSchedulerCallbackList + 1) = &qword_1004EE818;
    *((_QWORD *)&SOS_PublicGlobals::sm_DeadlockSchedulerCallbackList + 1) = &qword_1004EE818;
    qword_1004EE818 = SOS_PublicGlobals::sm_DeadlockSchedulerCallbackList;
    qword_1004EE838 = *((_QWORD *)&SOS_PublicGlobals::sm_NonYieldIOCPCallbackList + 1);
    **((_QWORD **)&SOS_PublicGlobals::sm_NonYieldIOCPCallbackList + 1) = &qword_1004EE830;
    *((_QWORD *)&SOS_PublicGlobals::sm_NonYieldIOCPCallbackList + 1) = &qword_1004EE830;
    qword_1004EE830 = SOS_PublicGlobals::sm_NonYieldIOCPCallbackList;
    qword_1004EE880 = *((_QWORD *)&SOS_PublicGlobals::sm_MemUtilizationEffectCallbackList + 1);
    **((_QWORD **)&SOS_PublicGlobals::sm_MemUtilizationEffectCallbackList + 1) = &qword_1004EE878;
    *((_QWORD *)&SOS_PublicGlobals::sm_MemUtilizationEffectCallbackList + 1) = &qword_1004EE878;
    qword_1004EE878 = SOS_PublicGlobals::sm_MemUtilizationEffectCallbackList;
    qword_1004EE850 = *((_QWORD *)&SOS_PublicGlobals::sm_NonYieldRMCallbackList + 1);
    **((_QWORD **)&SOS_PublicGlobals::sm_NonYieldRMCallbackList + 1) = &qword_1004EE848;
    *((_QWORD *)&SOS_PublicGlobals::sm_NonYieldRMCallbackList + 1) = &qword_1004EE848;
    qword_1004EE848 = SOS_PublicGlobals::sm_NonYieldRMCallbackList;
    SOS_OS::AddStuckDispatcherCallback(&qword_1004EE860);
    SOS_PublicGlobals::sm_ResourceManager[3] = 4;
    SOS_PublicGlobals::sm_ResourceManager[4] = 2;
    SOS_PublicGlobals::sm_osStats |= 0x4Fu;
    SOS_Tracing::NotifyTraceOn(0x1F4Fu);
    SOS_Tracing::NotifyTraceOn(0x14Au);
    if ( a2 )
    {
      v21 = a2();
      if ( v21 )
        goto LABEL_21;
    }
    ConfiguredMemoryMB = GetConfiguredMemoryMB();
    if ( ConfiguredMemoryMB )
      MemoryNode_MaxMemoryPagesLimit = (unsigned __int64)ConfiguredMemoryMB << 7;
    v21 = SOS_OS::Boot();
    if ( v21 )
    {
LABEL_21:
      v20 = HRESULT_FROM_SOS_RESULT_Uncommon(v21);
LABEL_22:
      AutoMakeMicroSOSThread::~AutoMakeMicroSOSThread((AutoMakeMicroSOSThread *)v25);
      return v20;
    }
    AutoMakeMicroSOSThread::~AutoMakeMicroSOSThread((AutoMakeMicroSOSThread *)v25);
  }
  return 0;
}

```

## disassembly

```asm
0x10040e0e0  push    rbp
0x10040e0e2  push    rdi
0x10040e0e3  push    r12
0x10040e0e5  push    r14
0x10040e0e7  push    r15
0x10040e0e9  mov     eax, 1820h
0x10040e0ee  call    _alloca_probe
0x10040e0f3  sub     rsp, rax
0x10040e0f6  lea     rbp, [rsp+40h]
0x10040e0fb  mov     [rbp+1800h+var_17E0], 0FFFFFFFFFFFFFFFEh
0x10040e103  mov     [rbp+1800h+arg_0], rbx
0x10040e10a  mov     [rbp+1800h+arg_10], rsi
0x10040e111  mov     rax, cs:__security_cookie
0x10040e118  xor     rax, rbp
0x10040e11b  mov     [rbp+1800h+var_30], rax
0x10040e122  mov     rbx, r9
0x10040e125  mov     r14, r8
0x10040e128  mov     rsi, rdx
0x10040e12b  mov     r15, rcx
0x10040e12e  mov     rax, cs:__imp_?SOS_OS_sm_osProcessStatus@@3KA; ulong SOS_OS_sm_osProcessStatus
0x10040e135  test    byte ptr [rax], 1
0x10040e138  jnz     loc_10040E4F0
0x10040e13e  xor     r9d, r9d; HeapInformationLength
0x10040e141  xor     r8d, r8d; HeapInformation
0x10040e144  lea     edx, [r9+1]; HeapInformationClass
0x10040e148  xor     ecx, ecx; HeapHandle
0x10040e14a  call    cs:__imp_HeapSetInformation
0x10040e150  test    [rbp+1800h+arg_20], 1
0x10040e157  jz      short loc_10040E16D
0x10040e159  mov     rcx, rbx; hModule
0x10040e15c  call    ?InitializeSqlDumper@@YAJPEAUHINSTANCE__@@@Z; InitializeSqlDumper(HINSTANCE__ *)
0x10040e161  test    eax, eax
0x10040e163  jns     short loc_10040E16D
0x10040e165  lfence
0x10040e168  jmp     loc_10040E4F2
0x10040e16d  mov     edx, 1
0x10040e172  lea     rcx, ?clientProcessConfig@@3V?$SOS_ProcessConfigImpl@$00@@A; SOS_ProcessConfigImpl<1> clientProcessConfig
0x10040e179  call    cs:__imp_?RegisterProcess@SOS_OS@@SA?AW4SOS_RESULT@@PEAVProcessConfig@@W4SOS_CallerType@@@Z; SOS_OS::RegisterProcess(ProcessConfig *,SOS_CallerType)
0x10040e17f  test    eax, eax
0x10040e181  jz      short loc_10040E190
0x10040e183  mov     ecx, eax
0x10040e185  call    cs:__imp_?HRESULT_FROM_SOS_RESULT_Uncommon@@YAJW4SOS_RESULT@@@Z; HRESULT_FROM_SOS_RESULT_Uncommon(SOS_RESULT)
0x10040e18b  jmp     loc_10040E4F2
0x10040e190  lea     rax, utassert_fail_imp
0x10040e197  mov     [rbp+1800h+var_1800], rax
0x10040e19b  xor     r12d, r12d
0x10040e19e  mov     [rbp+1800h+var_17F8], r12
0x10040e1a2  lea     rax, off_1004EDE50
0x10040e1a9  mov     [rbp+1800h+var_17F0], rax
0x10040e1ad  lea     edx, [r12+15h]
0x10040e1b2  lea     rcx, [rbp+1800h+var_1800]
0x10040e1b6  call    cs:__imp_?PreInitSOS@@YAXUSQLDK_Callbacks@@H@Z; PreInitSOS(SQLDK_Callbacks,int)
0x10040e1bc  mov     rax, cs:__imp_?sm_WorkerLsBitmap@SOS_PublicGlobals@@2VSmallBitmap@@A; SmallBitmap SOS_PublicGlobals::sm_WorkerLsBitmap
0x10040e1c3  mov     r8, [rax+8]
0x10040e1c7  lea     rax, ds:0[r8*8]
0x10040e1cf  lea     rcx, [rax+0Fh]
0x10040e1d3  cmp     rcx, rax
0x10040e1d6  ja      short loc_10040E1E2
0x10040e1d8  mov     rcx, 0FFFFFFFFFFFFFF0h
0x10040e1e2  and     rcx, 0FFFFFFFFFFFFFFF0h
0x10040e1e6  mov     rax, rcx
0x10040e1e9  call    _alloca_probe
0x10040e1ee  sub     rsp, rcx
0x10040e1f1  lea     r9, [rsp+1840h+var_1800]
0x10040e1f6  mov     [rsp+1840h+var_1810], r12
0x10040e1fb  mov     [rsp+1840h+var_1818], r12
0x10040e200  mov     [rsp+1840h+var_1820], 1
0x10040e208  xor     edx, edx
0x10040e20a  lea     rcx, [rbp+1800h+var_17D0]
0x10040e20e  call    cs:__imp_??0AutoMakeMicroSOSThread@@QEAA@QEAX_JPEAPEAXHPEAVSOS_Scheduler@@PEAVIMemObj@@@Z; AutoMakeMicroSOSThread::AutoMakeMicroSOSThread(void * const,__int64,void * *,int,SOS_Scheduler *,IMemObj *)
0x10040e214  nop
0x10040e215  mov     rdx, gs:58h
0x10040e21e  mov     rax, cs:__imp_SystemThread_TlsIndex
0x10040e225  mov     ecx, [rax]
0x10040e227  mov     rax, cs:__imp_SystemThread_TlsOffset
0x10040e22e  mov     edi, [rax]
0x10040e230  add     rdi, [rdx+rcx*8]
0x10040e234  mov     rbx, [rdi+100h]
0x10040e23b  test    rbx, rbx
0x10040e23e  jnz     short loc_10040E24F
0x10040e240  xor     ecx, ecx
0x10040e242  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x10040e248  mov     rbx, [rdi+100h]
0x10040e24f  or      dword ptr [rbx+268h], 20h
0x10040e256  mov     rax, cs:__imp_?sm_osMemoryClerk@SOS_PublicGlobals@@2VMemoryClerk@@A; MemoryClerk SOS_PublicGlobals::sm_osMemoryClerk
0x10040e25d  mov     ecx, 80h
0x10040e262  mov     edi, 8
0x10040e267  mov     r9d, edi
0x10040e26a  lea     r8, [rax+40h]
0x10040e26e  test    rax, rax
0x10040e271  cmovz   r8, r12
0x10040e275  mov     word ptr [rsp+1840h+var_1820], cx
0x10040e27a  lea     edx, [rcx-7Ch]
0x10040e27d  lea     ecx, [rdi-7]
0x10040e280  call    cs:__imp_?CreateMemObject@MemoryObjectFactory@@SAPEAVIMemObj@@W4SOSHOST_MEMOBJ_ID@@KPEAVPageAllocator@@FF@Z; MemoryObjectFactory::CreateMemObject(SOSHOST_MEMOBJ_ID,ulong,PageAllocator *,short,short)
0x10040e286  mov     [rbx+3E8h], rax
0x10040e28d  lea     edx, [rdi-7]; Add
0x10040e290  lea     rcx, ControlHandler; HandlerRoutine
0x10040e297  call    cs:__imp_SetConsoleCtrlHandler
0x10040e29d  test    eax, eax
0x10040e29f  jnz     short loc_10040E2BF
0x10040e2a1  call    cs:__imp_GetLastError
0x10040e2a7  mov     ebx, eax
0x10040e2a9  test    eax, eax
0x10040e2ab  jle     loc_10040E4D8
0x10040e2b1  movzx   ebx, ax
0x10040e2b4  or      ebx, 80070000h
0x10040e2ba  jmp     loc_10040E4D8
0x10040e2bf  mov     cs:qword_100556CA8, r15
0x10040e2c6  mov     cs:qword_100556D28, r14
0x10040e2cd  mov     ecx, 0Ch
0x10040e2d2  mov     rax, cs:__imp_?sm_NodeLsSize@SOS_PublicGlobals@@2FA; short SOS_PublicGlobals::sm_NodeLsSize
0x10040e2d9  mov     [rax], cx
0x10040e2dc  mov     rax, cs:__imp_?sm_SchedLsSize@SOS_PublicGlobals@@2FA; short SOS_PublicGlobals::sm_SchedLsSize
0x10040e2e3  mov     [rax], di
0x10040e2e6  lea     rcx, SQLSatellite_SOSNodeInitRoutine
0x10040e2ed  mov     rax, cs:__imp_?sm_NodeInit@SOS_PublicGlobals@@2P6A?AW4SOS_RESULT@@QEAVSOS_Node@@@ZEA; SOS_RESULT (*SOS_PublicGlobals::sm_NodeInit)(SOS_Node * const)
0x10040e2f4  mov     [rax], rcx
0x10040e2f7  lea     rcx, SQLSatellite_SOSBootFinalizeRoutine
0x10040e2fe  mov     rax, cs:__imp_?sm_BootFinalize@SOS_PublicGlobals@@2P6A?AW4SOS_RESULT@@XZEA; SOS_RESULT (*SOS_PublicGlobals::sm_BootFinalize)(void)
0x10040e305  mov     [rax], rcx
0x10040e308  call    cs:__imp_?SetUnhandledExceptionFilter@SOS_OS@@SAXXZ; SOS_OS::SetUnhandledExceptionFilter(void)
0x10040e30e  call    cs:__imp_?SetInvalidParameterHandler@SOS_OS@@SAP6AXPEB_W00I_K@ZXZ; SOS_OS::SetInvalidParameterHandler(void)
0x10040e314  call    cs:__imp_?SetAbortHandler@SOS_OS@@SAXXZ; SOS_OS::SetAbortHandler(void)
0x10040e31a  lea     rcx, ?scierrlog@@YAXKZZ; scierrlog(ulong,...)
0x10040e321  mov     rax, cs:__imp_?SOS_OS_ErrorLogRoutine@@3P6AXKZZEA; void (*SOS_OS_ErrorLogRoutine)(ulong,...)
0x10040e328  mov     [rax], rcx
0x10040e32b  lea     rcx, ?SOSLogToErrorLog@@YAXPEB_WZZ; SOSLogToErrorLog(wchar_t const *,...)
0x10040e332  mov     rax, cs:__imp_?SOS_OS_LogUnlocalizedRoutine@@3P6AXPEB_WZZEA; void (*SOS_OS_LogUnlocalizedRoutine)(wchar_t const *,...)
0x10040e339  mov     [rax], rcx
0x10040e33c  lea     rcx, ?ex_vcallprint_no_dump_no_retval@@YAXHHHPEAD@Z; ex_vcallprint_no_dump_no_retval(int,int,int,char *)
0x10040e343  mov     rax, cs:__imp_?SOS_OS_ExceptionPrintRoutine@@3P6AXHHHPEAD@ZEA; void (*SOS_OS_ExceptionPrintRoutine)(int,int,int,char *)
0x10040e34a  mov     [rax], rcx
0x10040e34d  lea     rcx, ?user_log@@YAXHHHKZZ; user_log(int,int,int,ulong,...)
0x10040e354  mov     rax, cs:__imp_?SOS_OS_UserLogRoutine@@3P6AXHHHKZZEA; void (*SOS_OS_UserLogRoutine)(int,int,int,ulong,...)
0x10040e35b  mov     [rax], rcx
0x10040e35e  lea     rcx, ?SqlDumpExceptionHandler@@YAHPEAU_EXCEPTION_POINTERS@@@Z; SqlDumpExceptionHandler(_EXCEPTION_POINTERS *)
0x10040e365  mov     rax, cs:__imp_?sm_DumpExceptionHandlerRoutine@SOS_PublicGlobals@@2P6AHPEAU_EXCEPTION_POINTERS@@@ZEA; int (*SOS_PublicGlobals::sm_DumpExceptionHandlerRoutine)(_EXCEPTION_POINTERS *)
0x10040e36c  mov     [rax], rcx
0x10040e36f  lea     rcx, ?stackTraceCallBack@@YAXPEAXPEB_WKPEAVCDStream@@@Z; stackTraceCallBack(void *,wchar_t const *,ulong,CDStream *)
0x10040e376  mov     rax, cs:__imp_?SOS_OS_StackTraceRoutine@@3P6AXPEAXPEB_WKPEAPEAX@ZEA; void (*SOS_OS_StackTraceRoutine)(void *,wchar_t const *,ulong,void * *)
0x10040e37d  mov     [rax], rcx
0x10040e380  mov     rcx, cs:__imp_?sm_NonYieldSchedulerCallbackList@SOS_PublicGlobals@@2V?$TCallbackList@V?$TCallback@XPEAVSOS_Task@@PEBVTrack@SchedulerMonitor@@VNullType@@V4@@@@@A; TCallbackList<TCallback<void,SOS_Task *,SchedulerMonitor::Track const *,NullType,NullType>> SOS_PublicGlobals::sm_NonYieldSchedulerCallbackList
0x10040e387  mov     rax, [rcx+8]
0x10040e38b  mov     cs:qword_1004EDE60, rax
0x10040e392  mov     rax, [rcx+8]
0x10040e396  lea     rdx, qword_1004EDE58
0x10040e39d  mov     [rax], rdx
0x10040e3a0  mov     [rcx+8], rdx
0x10040e3a4  mov     cs:qword_1004EDE58, rcx
0x10040e3ab  mov     rcx, cs:__imp_?sm_DeadlockSchedulerCallbackList@SOS_PublicGlobals@@2V?$TCallbackList@V?$TCallback@XGIPEBVProcessTrack@SchedulerMonitor@@VNullType@@@@@@A; TCallbackList<TCallback<void,ushort,uint,SchedulerMonitor::ProcessTrack const *,NullType>> SOS_PublicGlobals::sm_DeadlockSchedulerCallbackList
0x10040e3b2  mov     rax, [rcx+8]
0x10040e3b6  mov     cs:qword_1004EE820, rax
0x10040e3bd  mov     rax, [rcx+8]
0x10040e3c1  lea     rdx, qword_1004EE818
0x10040e3c8  mov     [rax], rdx
0x10040e3cb  mov     [rcx+8], rdx
0x10040e3cf  mov     cs:qword_1004EE818, rcx
0x10040e3d6  mov     rcx, cs:__imp_?sm_NonYieldIOCPCallbackList@SOS_PublicGlobals@@2V?$TCallbackList@V?$TCallback@XPEBVTrack@SchedulerMonitor@@VNullType@@V3@V3@@@@@A; TCallbackList<TCallback<void,SchedulerMonitor::Track const *,NullType,NullType,NullType>> SOS_PublicGlobals::sm_NonYieldIOCPCallbackList
0x10040e3dd  mov     rax, [rcx+8]
0x10040e3e1  mov     cs:qword_1004EE838, rax
0x10040e3e8  mov     rax, [rcx+8]
0x10040e3ec  lea     rdx, qword_1004EE830
0x10040e3f3  mov     [rax], rdx
0x10040e3f6  mov     [rcx+8], rdx
0x10040e3fa  mov     cs:qword_1004EE830, rcx
0x10040e401  mov     rcx, cs:__imp_?sm_MemUtilizationEffectCallbackList@SOS_PublicGlobals@@2V?$TCallbackList@V?$TCallback@XQEBUMemoryUtilizationInfo@@W4Effects@MemoryUtilizationEffects@@QEBUEffectInfo@3@VNullType@@@@@@A; TCallbackList<TCallback<void,MemoryUtilizationInfo const * const,MemoryUtilizationEffects::Effects,MemoryUtilizationEffects::EffectInfo const * const,NullType>> SOS_PublicGlobals::sm_MemUtilizationEffectCallbackList
0x10040e408  mov     rax, [rcx+8]
0x10040e40c  mov     cs:qword_1004EE880, rax
0x10040e413  mov     rax, [rcx+8]
0x10040e417  lea     rdx, qword_1004EE878
0x10040e41e  mov     [rax], rdx
0x10040e421  mov     [rcx+8], rdx
0x10040e425  mov     cs:qword_1004EE878, rcx
0x10040e42c  mov     rcx, cs:__imp_?sm_NonYieldRMCallbackList@SOS_PublicGlobals@@2V?$TCallbackList@V?$TCallback@X$$CB_JPEBVResourceClerk@@PEBVTrack@SchedulerMonitor@@VNullType@@@@@@A; TCallbackList<TCallback<void,__int64 const,ResourceClerk const *,SchedulerMonitor::Track const *,NullType>> SOS_PublicGlobals::sm_NonYieldRMCallbackList
0x10040e433  mov     rax, [rcx+8]
0x10040e437  mov     cs:qword_1004EE850, rax
0x10040e43e  mov     rax, [rcx+8]
0x10040e442  lea     rdx, qword_1004EE848
0x10040e449  mov     [rax], rdx
0x10040e44c  mov     [rcx+8], rdx
0x10040e450  mov     cs:qword_1004EE848, rcx
0x10040e457  lea     rcx, qword_1004EE860
0x10040e45e  call    cs:__imp_?AddStuckDispatcherCallback@SOS_OS@@SAXPEAV?$TCallback@XQEBVSOS_DispatcherBase@@VNullType@@V2@V2@@@@Z; SOS_OS::AddStuckDispatcherCallback(TCallback<void,SOS_DispatcherBase const * const,NullType,NullType,NullType> *)
0x10040e464  mov     rax, cs:__imp_?sm_ResourceManager@SOS_PublicGlobals@@2VSOS_ResourceManager@@A; SOS_ResourceManager SOS_PublicGlobals::sm_ResourceManager
0x10040e46b  mov     dword ptr [rax+0Ch], 4
0x10040e472  mov     rax, cs:__imp_?sm_ResourceManager@SOS_PublicGlobals@@2VSOS_ResourceManager@@A; SOS_ResourceManager SOS_PublicGlobals::sm_ResourceManager
0x10040e479  mov     dword ptr [rax+10h], 2
0x10040e480  mov     rax, cs:__imp_?sm_osStats@SOS_PublicGlobals@@2KA; ulong SOS_PublicGlobals::sm_osStats
0x10040e487  or      dword ptr [rax], 4Fh
0x10040e48a  mov     ecx, 1F4Fh
0x10040e48f  call    cs:__imp_?NotifyTraceOn@SOS_Tracing@@SAXK@Z; SOS_Tracing::NotifyTraceOn(ulong)
0x10040e495  mov     ecx, 14Ah
0x10040e49a  call    cs:__imp_?NotifyTraceOn@SOS_Tracing@@SAXK@Z; SOS_Tracing::NotifyTraceOn(ulong)
0x10040e4a0  test    rsi, rsi
0x10040e4a3  jz      short loc_10040E4AB
0x10040e4a5  call    rsi
0x10040e4a7  test    eax, eax
0x10040e4a9  jnz     short loc_10040E4CE
0x10040e4ab  call    ?GetConfiguredMemoryMB@@YAKXZ; GetConfiguredMemoryMB(void)
0x10040e4b0  test    eax, eax
0x10040e4b2  jz      short loc_10040E4C4
0x10040e4b4  mov     ecx, eax
0x10040e4b6  shl     rcx, 7
0x10040e4ba  mov     rax, cs:__imp_?MemoryNode_MaxMemoryPagesLimit@@3_JA; __int64 MemoryNode_MaxMemoryPagesLimit
0x10040e4c1  mov     [rax], rcx
0x10040e4c4  call    cs:__imp_?Boot@SOS_OS@@SA?AW4SOS_RESULT@@XZ; SOS_OS::Boot(void)
0x10040e4ca  test    eax, eax
0x10040e4cc  jz      short loc_10040E4E6
0x10040e4ce  mov     ecx, eax
0x10040e4d0  call    cs:__imp_?HRESULT_FROM_SOS_RESULT_Uncommon@@YAJW4SOS_RESULT@@@Z; HRESULT_FROM_SOS_RESULT_Uncommon(SOS_RESULT)
0x10040e4d6  mov     ebx, eax
0x10040e4d8  lea     rcx, [rbp+1800h+var_17D0]
0x10040e4dc  call    cs:__imp_??1AutoMakeMicroSOSThread@@QEAA@XZ; AutoMakeMicroSOSThread::~AutoMakeMicroSOSThread(void)
0x10040e4e2  mov     eax, ebx
0x10040e4e4  jmp     short loc_10040E4F2
0x10040e4e6  lea     rcx, [rbp+1800h+var_17D0]
0x10040e4ea  call    cs:__imp_??1AutoMakeMicroSOSThread@@QEAA@XZ; AutoMakeMicroSOSThread::~AutoMakeMicroSOSThread(void)
0x10040e4f0  xor     eax, eax
0x10040e4f2  mov     rcx, [rbp+1800h+var_30]
0x10040e4f9  xor     rcx, rbp; StackCookie
0x10040e4fc  call    __security_check_cookie
0x10040e501  mov     rbx, [rbp+1800h+arg_0]
0x10040e508  mov     rsi, [rbp+1800h+arg_10]
0x10040e50f  lea     rsp, [rbp+17E0h]
0x10040e516  pop     r15
0x10040e518  pop     r14
0x10040e51a  pop     r12
0x10040e51c  pop     rdi
0x10040e51d  pop     rbp
0x10040e51e  retn
```
