# WorkerTaskCapturingDebugState::InitializeGmoOperation(void)

- ea: `0x14005d988`
- end: `0x14005dee2`
- name: `?InitializeGmoOperation@WorkerTaskCapturingDebugState@@AEAAXXZ`
- size: `1370`
- prototype: `void __fastcall(WorkerTaskCapturingDebugState *__hidden this)`
- caller_count: `1`
- callee_count: `38`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x140176f5c`

## callees

- `0x14003b7c0`
- `0x14005c4dc`
- `0x14005c568`
- `0x14005c71c`
- `0x14005c948`
- `0x14005ca88`
- `0x14005d988`
- `0x14005def8`
- `0x14005df20`
- `0x14005dfbc`
- `0x14005dfdc`
- `0x14005e048`
- `0x14005e07c`
- `0x14005e6c4`
- `0x14005e6e8`
- `0x14005eb48`
- `0x140078628`
- `0x140082b4c`
- `0x1400b7900`
- `0x1400b8e10`
- `0x1400b99c0`
- `0x1400ba144`
- `0x1400ba47c`
- `0x1400ba6cc`
- `0x1400bc53c`
- `0x14011ea40`
- `0x14011edec`
- `0x14011f6fc`
- `0x140153e40`
- `0x1401719c4`
- `0x140171d30`
- `0x14017532c`
- `0x1401758f0`
- `0x140176108`
- `0x1401861e8`
- `0x1401862c8`
- `0x1401f84e0`
- `0x1402cb010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14005dd3a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14005dd3a`
- `vid!VidCloneTemplateCreate` at `0x14005dd26`
- `vid!VidCloneTemplateCreate` at `0x14005dd26`

## string_xrefs

- `0x14005d9de`: `onecore\vm\worker\wpcore\workertaskcapturingdebugstate.cpp`
- `0x14005dbed`: `onecore\vm\worker\wpcore\workertaskcapturingdebugstate.cpp`
- `0x14005dcb4`: `onecore\vm\worker\wpcore\workertaskcapturingdebugstate.cpp`
- `0x14005dce4`: `onecore\vm\worker\wpcore\workertaskcapturingdebugstate.cpp`
- `0x14005dd73`: `onecore\vm\worker\wpcore\workertaskcapturingdebugstate.cpp`
- `0x14005ddd7`: `onecore\vm\worker\wpcore\workertaskcapturingdebugstate.cpp`
- `0x14005de51`: `onecore\vm\worker\wpcore\workertaskcapturingdebugstate.cpp`
- `0x14005de80`: `onecore\vm\worker\wpcore\workertaskcapturingdebugstate.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=6 #try_helpers=1
void __fastcall WorkerTaskCapturingDebugState::InitializeGmoOperation(WorkerTaskCapturingDebugState *this)
{
  __int64 v2; // r12
  __int64 CurrentActivity; // rbx
  CaptureStateUtility *v4; // rdi
  __int64 v5; // rax
  CaptureStateUtility *v6; // rbx
  unsigned int v7; // r13d
  __int64 v8; // r9
  VirtualMachine *v9; // rcx
  unsigned __int64 v10; // r14
  unsigned __int64 RamSizeInPages; // r15
  void *v12; // rdi
  GmoRamOperationSnapshot *v13; // rax
  GmoRamOperationSnapshot *v14; // rcx
  int v15; // eax
  void *v16; // rdi
  GmoRamOperationSave *v17; // rax
  GmoRamOperationSave *v18; // rcx
  int v19; // eax
  GmoRamOperation *GmoRamOperation; // rax
  int v21; // eax
  __int64 (__fastcall ***v22)(_QWORD); // rcx
  __int64 v23; // rax
  signed int LastError; // eax
  int v25; // eax
  unsigned __int64 *v26; // rax
  unsigned __int64 v27; // rcx
  __int64 v28; // rdx
  __int64 v29; // r8
  int v30; // eax
  unsigned int v31; // [rsp+20h] [rbp-E0h]
  unsigned __int64 v32; // [rsp+20h] [rbp-E0h]
  int v33; // [rsp+20h] [rbp-E0h]
  unsigned __int64 v34; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int64 v35; // [rsp+58h] [rbp-A8h] BYREF
  char v36[336]; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v37[336]; // [rsp+1B0h] [rbp+B0h] BYREF
  CaptureStateUtility *v38; // [rsp+300h] [rbp+200h] BYREF
  __int128 v39; // [rsp+308h] [rbp+208h] BYREF
  __int128 v40; // [rsp+320h] [rbp+220h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+388h] [rbp+288h]

  v40 = 0;
  v2 = qword_1403CC940;
  if ( qword_1403CC940 == 3 )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x2CA,
      (unsigned int)"onecore\\vm\\worker\\wpcore\\workertaskcapturingdebugstate.cpp",
      (const char *)0x32,
      v31);
  CurrentActivity = WorkerAsyncTask<VmWorkerTrace::SnapshottingTask>::GetCurrentActivity(this, v37);
  v4 = (CaptureStateUtility *)operator new(0x160u);
  v38 = v4;
  memset_0(v4, 0, 0x160u);
  v5 = VmWorkerTrace::SnapshottingTask::SnapshottingTask(v36, CurrentActivity);
  v6 = (CaptureStateUtility *)CaptureStateUtility::CaptureStateUtility(v4, *((_QWORD *)this + 2), v5, 0);
  v38 = v6;
  VmWorkerTrace::SnapshottingTask::~SnapshottingTask((VmWorkerTrace::SnapshottingTask *)v37);
  CaptureStateUtility::SuspendAndSaveEpf(v6, *((struct VmRepository **)this + 63));
  CaptureStateUtility::SuspendAndSaveSchedulerAssist(v6, *((struct VmRepository **)this + 63));
  v7 = *(_DWORD *)(*(_QWORD *)(*((_QWORD *)this + 2) + 1416LL) + 376LL);
  CaptureStateUtility::InitializeBalloonedPagesBitmap(v6);
  v32 = qword_1403CC9E0;
  LOBYTE(v8) = 1;
  MemoryManager::SaveRamInformation(&MemoryManager::m_Instance, *((_QWORD *)this + 63), 0, v8);
  (*(void (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)(*((_QWORD *)this + 2) + 1024LL) + 256LL))(
    *(_QWORD *)(*((_QWORD *)this + 2) + 1024LL),
    *((_QWORD *)this + 63));
  MemoryManager::SaveVtlProtections((MemoryManager *)&MemoryManager::m_Instance, *((struct VmRepository **)this + 63));
  v34 = 0;
  if ( ((*((_DWORD *)this + 116) - 1) & 0xFFFFFFFD) != 0
    || (v9 = (VirtualMachine *)*((_QWORD *)this + 2), !*((_BYTE *)v9 + 2664)) )
  {
    v10 = 0;
    RamSizeInPages = MemoryManager::GetRamSizeInPages((MemoryManager *)&MemoryManager::m_Instance);
  }
  else
  {
    v35 = 0;
    VirtualMachine::GetVtl2PrivateRamRange(v9, &v35, &v34);
    v10 = MemoryManager::GpaIndexToRamIndex((MemoryManager *)&MemoryManager::m_Instance, v35);
    RamSizeInPages = v34;
  }
  if ( *((_DWORD *)this + 116) == 2 )
  {
    v16 = operator new(0xF8u);
    v34 = (unsigned __int64)v16;
    memset_0(v16, 0, 0xF8u);
    memset_0(v16, 0, 0xF8u);
    v17 = GmoRamOperationSave::GmoRamOperationSave((GmoRamOperationSave *)v16);
    v34 = 0;
    v18 = (GmoRamOperationSave *)*((_QWORD *)this + 54);
    *((_QWORD *)this + 54) = v17;
    if ( v18 )
      GmoRamOperationSave::`scalar deleting destructor'(v18, 1u);
    std::unique_ptr<GmoRamOperationSave>::~unique_ptr<GmoRamOperationSave>(&v34);
    v33 = 99;
    v19 = GmoRamOperationSource::Initialize(
            *((_QWORD *)this + 54),
            *((_QWORD *)this + 63),
            *((_QWORD *)this + 2),
            *((_QWORD *)this + 3));
    if ( v19 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x318,
        (unsigned int)"onecore\\vm\\worker\\wpcore\\workertaskcapturingdebugstate.cpp",
        (const char *)(unsigned int)v19,
        99);
  }
  else
  {
    v12 = operator new(0x110u);
    v34 = (unsigned __int64)v12;
    memset_0(v12, 0, 0x110u);
    v13 = GmoRamOperationSnapshot::GmoRamOperationSnapshot((GmoRamOperationSnapshot *)v12);
    v34 = 0;
    v14 = (GmoRamOperationSnapshot *)*((_QWORD *)this + 53);
    *((_QWORD *)this + 53) = v13;
    if ( v14 )
      GmoRamOperationSnapshot::`vector deleting destructor'(v14, 1u);
    std::unique_ptr<GmoRamOperationSnapshot>::~unique_ptr<GmoRamOperationSnapshot>(&v34);
    v15 = GmoRamOperationSnapshot::Initialize(
            *((GmoRamOperationSnapshot **)this + 53),
            *((void **)this + 63),
            *((struct VirtualMachine **)this + 2),
            *((struct IVmSimpleTask **)this + 3),
            v32,
            0,
            RamSizeInPages,
            v10,
            v7);
    if ( v15 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x30A,
        (unsigned int)"onecore\\vm\\worker\\wpcore\\workertaskcapturingdebugstate.cpp",
        (const char *)(unsigned int)v15,
        v33);
  }
  GmoRamOperation = WorkerTaskCapturingDebugState::GetGmoRamOperation(this);
  v21 = GmoRamOperation::WorkThreadsStart(GmoRamOperation);
  if ( v21 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x31F,
      (unsigned int)"onecore\\vm\\worker\\wpcore\\workertaskcapturingdebugstate.cpp",
      (const char *)(unsigned int)v21,
      v33);
  if ( v2 == 2 )
  {
    v22 = (__int64 (__fastcall ***)(_QWORD))(*(_QWORD *)(*((_QWORD *)this + 2) + 1024LL) + 24LL);
    v23 = (**v22)(v22);
    if ( !(unsigned int)VidCloneTemplateCreate(v23, 1, &v40) )
    {
      LastError = GetLastError();
      if ( (LastError & 0x1FFF0000) != 0 )
      {
        if ( LastError > 0 )
          LastError = LastError & 0xFFFFFFF | 0x80000000;
      }
      else if ( LastError > 0 )
      {
        LastError = (unsigned __int16)LastError | 0x80070000;
      }
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x32B,
        (unsigned int)"onecore\\vm\\worker\\wpcore\\workertaskcapturingdebugstate.cpp",
        (const char *)(unsigned int)LastError,
        v33);
    }
  }
  else if ( *((_DWORD *)this + 116) != 2 )
  {
    if ( (unsigned int)MemoryManager::SetRamNotificationListener(
                         (MemoryManager *)&MemoryManager::m_Instance,
                         (struct MemoryNotificationListener *)((*((_QWORD *)this + 53) + 248LL)
                                                             & ((unsigned __int128)-(__int128)*((unsigned __int64 *)this
                                                                                              + 53) >> 64))) )
    {
      v25 = GmoRamOperationSnapshot::SetMemoryIntercepts(*((GmoRamOperationSnapshot **)this + 53));
      if ( v25 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x344,
          (unsigned int)"onecore\\vm\\worker\\wpcore\\workertaskcapturingdebugstate.cpp",
          (const char *)(unsigned int)v25,
          v33);
    }
    else
    {
      v39 = 0;
      v26 = (unsigned __int64 *)std::make_unique<Vml::VmMachineLocalSettingsStore,,0>(&v35);
      v27 = *v26;
      *v26 = 0;
      v34 = v27;
      VirtualizationSettings::VirtualizationSettings(&v39, v28, v29, &v34);
      std::unique_ptr<Vml::VmDispatchContextWithParams<void,IVmSimpleTask *,unsigned int,Migration::Parameters::Worker::MigrationTargetInit &&>>::~unique_ptr<Vml::VmDispatchContextWithParams<void,IVmSimpleTask *,unsigned int,Migration::Parameters::Worker::MigrationTargetInit &&>>(&v34);
      std::unique_ptr<Vml::VmDispatchContextWithParams<void,IVmSimpleTask *,unsigned int,Migration::Parameters::Worker::MigrationTargetInit &&>>::~unique_ptr<Vml::VmDispatchContextWithParams<void,IVmSimpleTask *,unsigned int,Migration::Parameters::Worker::MigrationTargetInit &&>>(&v35);
      if ( !VirtualizationSettings::GetAzureFeatureSetEnabled((VirtualizationSettings *)&v39) )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x34D,
          (unsigned int)"onecore\\vm\\worker\\wpcore\\workertaskcapturingdebugstate.cpp",
          (const char *)0x80070032LL,
          v33);
      v30 = GmoRamOperationSnapshot::SaveAllMemory(*((GmoRamOperationSnapshot **)this + 53));
      if ( v30 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x34E,
          (unsigned int)"onecore\\vm\\worker\\wpcore\\workertaskcapturingdebugstate.cpp",
          (const char *)(unsigned int)v30,
          v33);
      std::unique_ptr<Vml::VmDispatchContextWithParams<void,IVmSimpleTask *,unsigned int,Migration::Parameters::Worker::MigrationTargetInit &&>>::~unique_ptr<Vml::VmDispatchContextWithParams<void,IVmSimpleTask *,unsigned int,Migration::Parameters::Worker::MigrationTargetInit &&>>((char *)&v39 + 8);
    }
  }
  std::unique_ptr<CaptureStateUtility>::operator=<std::default_delete<CaptureStateUtility>,0>((char *)this + 440, &v38);
  std::unique_ptr<CaptureStateUtility>::~unique_ptr<CaptureStateUtility>(&v38);
}

```

## disassembly

```asm
0x14005d988  push    rbp
0x14005d98a  push    rbx
0x14005d98b  push    rsi
0x14005d98c  push    rdi
0x14005d98d  push    r12
0x14005d98f  push    r13
0x14005d991  push    r14
0x14005d993  push    r15
0x14005d995  lea     rbp, [rsp-248h]
0x14005d99d  sub     rsp, 348h
0x14005d9a4  mov     rax, cs:__security_cookie
0x14005d9ab  xor     rax, rsp
0x14005d9ae  mov     [rbp+280h+var_50], rax
0x14005d9b5  mov     rsi, rcx
0x14005d9b8  xor     r15d, r15d
0x14005d9bb  xorps   xmm0, xmm0
0x14005d9be  movdqa  [rbp+280h+var_60], xmm0
0x14005d9c6  mov     r12, cs:qword_1403CC940
0x14005d9cd  cmp     r12, 3
0x14005d9d1  jnz     short loc_14005D9F0
0x14005d9d3  mov     rcx, [rbp+288h]; this
0x14005d9da  lea     r9d, [r15+32h]; char *
0x14005d9de  lea     r8, aOnecoreVmWorke_125; "onecore\\vm\\worker\\wpcore\\workertask"...
0x14005d9e5  mov     edx, 2CAh; void *
0x14005d9ea  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x14005d9f0  lea     rdx, [rbp+280h+var_1D0]
0x14005d9f7  call    ?GetCurrentActivity@?$WorkerAsyncTask@VSnapshottingTask@VmWorkerTrace@@@@IEAA?AVSnapshottingTask@VmWorkerTrace@@XZ; WorkerAsyncTask<VmWorkerTrace::SnapshottingTask>::GetCurrentActivity(void)
0x14005d9fc  mov     rbx, rax
0x14005d9ff  mov     r14d, 160h
0x14005da05  mov     ecx, r14d; Size
0x14005da08  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14005da0d  mov     rdi, rax
0x14005da10  mov     [rbp+280h+var_80], rax
0x14005da17  mov     r8d, r14d; Size
0x14005da1a  xor     edx, edx; Val
0x14005da1c  mov     rcx, rax; void *
0x14005da1f  call    memset_0
0x14005da24  mov     rdx, rbx
0x14005da27  lea     rcx, [rsp+380h+var_320]
0x14005da2c  call    ??0SnapshottingTask@VmWorkerTrace@@QEAA@$$QEAV01@@Z; VmWorkerTrace::SnapshottingTask::SnapshottingTask(VmWorkerTrace::SnapshottingTask &&)
0x14005da31  xor     r9d, r9d
0x14005da34  mov     r8, rax
0x14005da37  mov     rdx, [rsi+10h]
0x14005da3b  mov     rcx, rdi
0x14005da3e  call    ??0CaptureStateUtility@@QEAA@PEAVVirtualMachine@@VSnapshottingTask@VmWorkerTrace@@_N@Z; CaptureStateUtility::CaptureStateUtility(VirtualMachine *,VmWorkerTrace::SnapshottingTask,bool)
0x14005da43  mov     rbx, rax
0x14005da46  mov     [rbp+280h+var_80], rax
0x14005da4d  lea     rcx, [rbp+280h+var_1D0]; this
0x14005da54  call    ??1SnapshottingTask@VmWorkerTrace@@QEAA@XZ; VmWorkerTrace::SnapshottingTask::~SnapshottingTask(void)
0x14005da59  mov     rdx, [rsi+1F8h]; struct VmRepository *
0x14005da60  mov     rcx, rbx; this
0x14005da63  call    ?SuspendAndSaveEpf@CaptureStateUtility@@QEAAXPEAVVmRepository@@@Z; CaptureStateUtility::SuspendAndSaveEpf(VmRepository *)
0x14005da68  mov     rdx, [rsi+1F8h]; struct VmRepository *
0x14005da6f  mov     rcx, rbx; this
0x14005da72  call    ?SuspendAndSaveSchedulerAssist@CaptureStateUtility@@QEAAXPEAVVmRepository@@@Z; CaptureStateUtility::SuspendAndSaveSchedulerAssist(VmRepository *)
0x14005da77  mov     rax, [rsi+10h]
0x14005da7b  mov     rcx, [rax+588h]
0x14005da82  mov     r13d, [rcx+178h]
0x14005da89  mov     rcx, rbx; this
0x14005da8c  call    ?InitializeBalloonedPagesBitmap@CaptureStateUtility@@QEAAXXZ; CaptureStateUtility::InitializeBalloonedPagesBitmap(void)
0x14005da91  mov     [rsp+380h+var_358], r15; unsigned __int64
0x14005da96  mov     rax, cs:qword_1403CC9E0
0x14005da9d  mov     [rsp+380h+var_360], rax; int
0x14005daa2  mov     ebx, 1
0x14005daa7  mov     r9b, bl
0x14005daaa  xor     r8d, r8d
0x14005daad  mov     rdx, [rsi+1F8h]
0x14005dab4  lea     rdi, ?m_Instance@MemoryManager@@0V1@A; MemoryManager MemoryManager::m_Instance
0x14005dabb  mov     rcx, rdi
0x14005dabe  call    ?SaveRamInformation@MemoryManager@@UEAAXPEAVVmRepository@@W4VmFastSaveType@@_NPEAVGmoBitmap@@PEAT_VM_PERSIST_FLAGS@@@Z; MemoryManager::SaveRamInformation(VmRepository *,VmFastSaveType,bool,GmoBitmap *,_VM_PERSIST_FLAGS *)
0x14005dac3  mov     rax, [rsi+10h]
0x14005dac7  mov     rcx, [rax+400h]
0x14005dace  mov     rax, [rcx]
0x14005dad1  mov     rdx, [rsi+1F8h]
0x14005dad8  mov     rax, [rax+100h]
0x14005dadf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005dae4  mov     rdx, [rsi+1F8h]; struct VmRepository *
0x14005daeb  mov     rcx, rdi; this
0x14005daee  call    ?SaveVtlProtections@MemoryManager@@UEAAXPEAVVmRepository@@@Z; MemoryManager::SaveVtlProtections(VmRepository *)
0x14005daf3  mov     [rsp+380h+var_330], r15
0x14005daf8  mov     eax, [rsi+1D0h]
0x14005dafe  sub     eax, ebx
0x14005db00  test    eax, 0FFFFFFFDh
0x14005db05  jnz     short loc_14005DB3F
0x14005db07  mov     rcx, [rsi+10h]; this
0x14005db0b  cmp     [rcx+0A68h], r15b
0x14005db12  jz      short loc_14005DB3F
0x14005db14  mov     [rsp+380h+var_328], r15
0x14005db19  lea     r8, [rsp+380h+var_330]; unsigned __int64 *
0x14005db1e  lea     rdx, [rsp+380h+var_328]; unsigned __int64 *
0x14005db23  call    ?GetVtl2PrivateRamRange@VirtualMachine@@UEBAXPEA_K0@Z; VirtualMachine::GetVtl2PrivateRamRange(unsigned __int64 *,unsigned __int64 *)
0x14005db28  mov     rdx, [rsp+380h+var_328]; unsigned __int64
0x14005db2d  mov     rcx, rdi; this
0x14005db30  call    ?GpaIndexToRamIndex@MemoryManager@@UEAA_K_K@Z; MemoryManager::GpaIndexToRamIndex(unsigned __int64)
0x14005db35  mov     r14, rax
0x14005db38  mov     r15, [rsp+380h+var_330]
0x14005db3d  jmp     short loc_14005DB4D
0x14005db3f  mov     r14, r15
0x14005db42  mov     rcx, rdi; this
0x14005db45  call    ?GetRamSizeInPages@MemoryManager@@UEBA_KXZ; MemoryManager::GetRamSizeInPages(void)
0x14005db4a  mov     r15, rax
0x14005db4d  cmp     dword ptr [rsi+1D0h], 2
0x14005db54  jz      loc_14005DBFF
0x14005db5a  mov     ecx, 110h; Size
0x14005db5f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14005db64  mov     rdi, rax
0x14005db67  mov     [rsp+380h+var_330], rax
0x14005db6c  xor     edx, edx; Val
0x14005db6e  mov     r8d, 110h; Size
0x14005db74  mov     rcx, rax; void *
0x14005db77  call    memset_0
0x14005db7c  mov     rcx, rdi; this
0x14005db7f  call    ??0GmoRamOperationSnapshot@@QEAA@XZ; GmoRamOperationSnapshot::GmoRamOperationSnapshot(void)
0x14005db84  mov     [rsp+380h+var_330], 0
0x14005db8d  mov     rcx, [rsi+1A8h]; this
0x14005db94  mov     [rsi+1A8h], rax
0x14005db9b  test    rcx, rcx
0x14005db9e  jz      short loc_14005DBA7
0x14005dba0  mov     edx, ebx; unsigned int
0x14005dba2  call    ??_EGmoRamOperationSnapshot@@UEAAPEAXI@Z; GmoRamOperationSnapshot::`vector deleting destructor'(uint)
0x14005dba7  lea     rcx, [rsp+380h+var_330]
0x14005dbac  call    ??1?$unique_ptr@VGmoRamOperationSnapshot@@U?$default_delete@VGmoRamOperationSnapshot@@@std@@@std@@QEAA@XZ; std::unique_ptr<GmoRamOperationSnapshot>::~unique_ptr<GmoRamOperationSnapshot>(void)
0x14005dbb1  mov     [rsp+380h+var_340], r13d; unsigned int
0x14005dbb6  mov     [rsp+380h+var_348], r14; unsigned __int64
0x14005dbbb  mov     [rsp+380h+var_350], r15; unsigned __int64
0x14005dbc0  mov     r9, [rsi+18h]; struct IVmSimpleTask *
0x14005dbc4  mov     r8, [rsi+10h]; struct VirtualMachine *
0x14005dbc8  mov     rdx, [rsi+1F8h]; void *
0x14005dbcf  mov     rcx, [rsi+1A8h]; this
0x14005dbd6  call    ?Initialize@GmoRamOperationSnapshot@@QEAAJPEAXPEAVVirtualMachine@@PEAUIVmSimpleTask@@_K333I@Z; GmoRamOperationSnapshot::Initialize(void *,VirtualMachine *,IVmSimpleTask *,unsigned __int64,unsigned __int64,unsigned __int64,unsigned __int64,uint)
0x14005dbdb  mov     rcx, [rbp+288h]; this
0x14005dbe2  test    eax, eax
0x14005dbe4  jns     loc_14005DCC6
0x14005dbea  mov     r9d, eax; char *
0x14005dbed  lea     r8, aOnecoreVmWorke_125; "onecore\\vm\\worker\\wpcore\\workertask"...
0x14005dbf4  mov     edx, 30Ah; void *
0x14005dbf9  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14005dbff  mov     ecx, 0F8h; Size
0x14005dc04  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14005dc09  mov     rdi, rax
0x14005dc0c  mov     [rsp+380h+var_330], rax
0x14005dc11  xor     edx, edx; Val
0x14005dc13  mov     r8d, 0F8h; Size
0x14005dc19  mov     rcx, rax; void *
0x14005dc1c  call    memset_0
0x14005dc21  xor     edx, edx; Val
0x14005dc23  mov     r8d, 0F8h; Size
0x14005dc29  mov     rcx, rdi; void *
0x14005dc2c  call    memset_0
0x14005dc31  mov     rcx, rdi; this
0x14005dc34  call    ??0GmoRamOperationSave@@QEAA@XZ; GmoRamOperationSave::GmoRamOperationSave(void)
0x14005dc39  mov     [rsp+380h+var_330], 0
0x14005dc42  mov     rcx, [rsi+1B0h]; this
0x14005dc49  mov     [rsi+1B0h], rax
0x14005dc50  test    rcx, rcx
0x14005dc53  jz      short loc_14005DC5C
0x14005dc55  mov     edx, ebx; unsigned int
0x14005dc57  call    ??_GGmoRamOperationSave@@UEAAPEAXI@Z; GmoRamOperationSave::`scalar deleting destructor'(uint)
0x14005dc5c  lea     rcx, [rsp+380h+var_330]
0x14005dc61  call    ??1?$unique_ptr@VGmoRamOperationSave@@U?$default_delete@VGmoRamOperationSave@@@std@@@std@@QEAA@XZ; std::unique_ptr<GmoRamOperationSave>::~unique_ptr<GmoRamOperationSave>(void)
0x14005dc66  mov     [rsp+380h+var_338], ebx
0x14005dc6a  mov     [rsp+380h+var_340], r13d
0x14005dc6f  mov     [rsp+380h+var_348], r14
0x14005dc74  mov     [rsp+380h+var_350], r15
0x14005dc79  mov     [rsp+380h+var_358], 5
0x14005dc82  mov     [rsp+380h+var_360], 63h ; 'c'; int
0x14005dc8b  mov     r9, [rsi+18h]
0x14005dc8f  mov     r8, [rsi+10h]
0x14005dc93  mov     rdx, [rsi+1F8h]
0x14005dc9a  mov     rcx, [rsi+1B0h]
0x14005dca1  call    ?Initialize@GmoRamOperationSource@@QEAAJPEAXPEAVVirtualMachine@@PEAUIVmSimpleTask@@_K333IW4Flags@1@@Z; GmoRamOperationSource::Initialize(void *,VirtualMachine *,IVmSimpleTask *,unsigned __int64,unsigned __int64,unsigned __int64,unsigned __int64,uint,GmoRamOperationSource::Flags)
0x14005dca6  mov     rcx, [rbp+288h]; this
0x14005dcad  test    eax, eax
0x14005dcaf  jns     short loc_14005DCC6
0x14005dcb1  mov     r9d, eax; char *
0x14005dcb4  lea     r8, aOnecoreVmWorke_125; "onecore\\vm\\worker\\wpcore\\workertask"...
0x14005dcbb  mov     edx, 318h; void *
0x14005dcc0  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14005dcc6  mov     rcx, rsi; this
0x14005dcc9  call    ?GetGmoRamOperation@WorkerTaskCapturingDebugState@@AEAAPEAVGmoRamOperationSource@@XZ; WorkerTaskCapturingDebugState::GetGmoRamOperation(void)
0x14005dcce  mov     rcx, rax; this
0x14005dcd1  call    ?WorkThreadsStart@GmoRamOperation@@QEAAJXZ; GmoRamOperation::WorkThreadsStart(void)
0x14005dcd6  mov     rcx, [rbp+288h]; this
0x14005dcdd  test    eax, eax
0x14005dcdf  jns     short loc_14005DCF6
0x14005dce1  mov     r9d, eax; char *
0x14005dce4  lea     r8, aOnecoreVmWorke_125; "onecore\\vm\\worker\\wpcore\\workertask"...
0x14005dceb  mov     edx, 31Fh; void *
0x14005dcf0  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14005dcf6  cmp     r12, 2
0x14005dcfa  jnz     loc_14005DD85
0x14005dd00  mov     rax, [rsi+10h]
0x14005dd04  mov     rcx, [rax+400h]
0x14005dd0b  add     rcx, 18h
0x14005dd0f  mov     rax, [rcx]
0x14005dd12  mov     rax, [rax]
0x14005dd15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005dd1a  lea     r8, [rbp+280h+var_60]
0x14005dd21  mov     edx, ebx
0x14005dd23  mov     rcx, rax
0x14005dd26  call    cs:__imp_VidCloneTemplateCreate
0x14005dd2d  nop     dword ptr [rax+rax+00h]
0x14005dd32  test    eax, eax
0x14005dd34  jnz     loc_14005DE9E
0x14005dd3a  call    cs:__imp_GetLastError
0x14005dd41  nop     dword ptr [rax+rax+00h]
0x14005dd46  test    eax, 1FFF0000h
0x14005dd4b  jnz     short loc_14005DD5B
0x14005dd4d  test    eax, eax
0x14005dd4f  jle     short loc_14005DD69
0x14005dd51  movzx   eax, ax
0x14005dd54  or      eax, 80070000h
0x14005dd59  jmp     short loc_14005DD69
0x14005dd5b  test    eax, eax
0x14005dd5d  jle     short loc_14005DD69
0x14005dd5f  and     eax, 0FFFFFFFh
0x14005dd64  or      eax, 80000000h
0x14005dd69  mov     rcx, [rbp+288h]; this
0x14005dd70  mov     r9d, eax; char *
0x14005dd73  lea     r8, aOnecoreVmWorke_125; "onecore\\vm\\worker\\wpcore\\workertask"...
0x14005dd7a  mov     edx, 32Bh; void *
0x14005dd7f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14005dd85  cmp     dword ptr [rsi+1D0h], 2
0x14005dd8c  jz      loc_14005DE9E
0x14005dd92  mov     rax, [rsi+1A8h]
0x14005dd99  lea     r8, [rax+0F8h]
0x14005dda0  neg     rax
0x14005dda3  sbb     rdx, rdx
0x14005dda6  and     rdx, r8; struct MemoryNotificationListener *
0x14005dda9  lea     rcx, ?m_Instance@MemoryManager@@0V1@A; this
0x14005ddb0  call    ?SetRamNotificationListener@MemoryManager@@UEAAHPEAVMemoryNotificationListener@@@Z; MemoryManager::SetRamNotificationListener(MemoryNotificationListener *)
0x14005ddb5  test    eax, eax
0x14005ddb7  jz      short loc_14005DDE9
0x14005ddb9  mov     rcx, [rsi+1A8h]; this
0x14005ddc0  call    ?SetMemoryIntercepts@GmoRamOperationSnapshot@@QEAAJXZ; GmoRamOperationSnapshot::SetMemoryIntercepts(void)
0x14005ddc5  mov     rcx, [rbp+288h]; this
0x14005ddcc  test    eax, eax
0x14005ddce  jns     loc_14005DE9E
0x14005ddd4  mov     r9d, eax; char *
0x14005ddd7  lea     r8, aOnecoreVmWorke_125; "onecore\\vm\\worker\\wpcore\\workertask"...
0x14005ddde  mov     edx, 344h; void *
0x14005dde3  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14005dde9  xorps   xmm0, xmm0
0x14005ddec  movups  [rbp+280h+var_78], xmm0
0x14005ddf3  lea     rcx, [rsp+380h+var_328]
0x14005ddf8  call    ??$make_unique@VVmMachineLocalSettingsStore@Vml@@$$V$0A@@std@@YA?AV?$unique_ptr@VVmMachineLocalSettingsStore@Vml@@U?$default_delete@VVmMachineLocalSettingsStore@Vml@@@std@@@0@XZ; std::make_unique<Vml::VmMachineLocalSettingsStore,,0>(void)
0x14005ddfd  nop
0x14005ddfe  mov     rcx, [rax]
0x14005de01  mov     qword ptr [rax], 0
0x14005de08  mov     [rsp+380h+var_330], rcx
0x14005de0d  lea     r9, [rsp+380h+var_330]
0x14005de12  lea     rcx, [rbp+280h+var_78]
0x14005de19  call    ??0VirtualizationSettings@@QEAA@_NPEBG$$QEAV?$unique_ptr@VISettingsStore@@U?$default_delete@VISettingsStore@@@std@@@std@@@Z; VirtualizationSettings::VirtualizationSettings(bool,ushort const *,std::unique_ptr<ISettingsStore> &&)
0x14005de1e  nop
0x14005de1f  lea     rcx, [rsp+380h+var_330]
0x14005de24  call    ??1?$unique_ptr@V?$VmDispatchContextWithParams@XPEAUIVmSimpleTask@@I$$QEAUMigrationTargetInit@Worker@Parameters@Migration@@@Vml@@U?$default_delete@V?$VmDispatchContextWithParams@XPEAUIVmSimpleTask@@I$$QEAUMigrationTargetInit@Worker@Parameters@Migration@@@Vml@@@std@@@std@@QEAA@XZ; std::unique_ptr<Vml::VmDispatchContextWithParams<void,IVmSimpleTask *,uint,Migration::Parameters::Worker::MigrationTargetInit &&>>::~unique_ptr<Vml::VmDispatchContextWithParams<void,IVmSimpleTask *,uint,Migration::Parameters::Worker::MigrationTargetInit &&>>(void)
0x14005de29  nop
0x14005de2a  lea     rcx, [rsp+380h+var_328]
0x14005de2f  call    ??1?$unique_ptr@V?$VmDispatchContextWithParams@XPEAUIVmSimpleTask@@I$$QEAUMigrationTargetInit@Worker@Parameters@Migration@@@Vml@@U?$default_delete@V?$VmDispatchContextWithParams@XPEAUIVmSimpleTask@@I$$QEAUMigrationTargetInit@Worker@Parameters@Migration@@@Vml@@@std@@@std@@QEAA@XZ; std::unique_ptr<Vml::VmDispatchContextWithParams<void,IVmSimpleTask *,uint,Migration::Parameters::Worker::MigrationTargetInit &&>>::~unique_ptr<Vml::VmDispatchContextWithParams<void,IVmSimpleTask *,uint,Migration::Parameters::Worker::MigrationTargetInit &&>>(void)
0x14005de34  mov     rbx, [rbp+288h]
0x14005de3b  lea     rcx, [rbp+280h+var_78]; this
0x14005de42  call    ?GetAzureFeatureSetEnabled@VirtualizationSettings@@UEBA_NXZ; VirtualizationSettings::GetAzureFeatureSetEnabled(void)
0x14005de47  test    al, al
0x14005de49  jnz     short loc_14005DE66
0x14005de4b  mov     r9d, 80070032h; char *
0x14005de51  lea     r8, aOnecoreVmWorke_125; "onecore\\vm\\worker\\wpcore\\workertask"...
0x14005de58  mov     edx, 34Dh; void *
0x14005de5d  mov     rcx, rbx; this
0x14005de60  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14005de66  mov     rcx, [rsi+1A8h]; this
0x14005de6d  call    ?SaveAllMemory@GmoRamOperationSnapshot@@QEAAJXZ; GmoRamOperationSnapshot::SaveAllMemory(void)
0x14005de72  mov     rcx, [rbp+288h]; this
0x14005de79  test    eax, eax
0x14005de7b  jns     short loc_14005DE92
0x14005de7d  mov     r9d, eax; char *
0x14005de80  lea     r8, aOnecoreVmWorke_125; "onecore\\vm\\worker\\wpcore\\workertask"...
0x14005de87  mov     edx, 34Eh; void *
0x14005de8c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14005de92  lea     rcx, [rbp+280h+var_78+8]
0x14005de99  call    ??1?$unique_ptr@V?$VmDispatchContextWithParams@XPEAUIVmSimpleTask@@I$$QEAUMigrationTargetInit@Worker@Parameters@Migration@@@Vml@@U?$default_delete@V?$VmDispatchContextWithParams@XPEAUIVmSimpleTask@@I$$QEAUMigrationTargetInit@Worker@Parameters@Migration@@@Vml@@@std@@@std@@QEAA@XZ; std::unique_ptr<Vml::VmDispatchContextWithParams<void,IVmSimpleTask *,uint,Migration::Parameters::Worker::MigrationTargetInit &&>>::~unique_ptr<Vml::VmDispatchContextWithParams<void,IVmSimpleTask *,uint,Migration::Parameters::Worker::MigrationTargetInit &&>>(void)
0x14005de9e  lea     rcx, [rsi+1B8h]
0x14005dea5  lea     rdx, [rbp+280h+var_80]
0x14005deac  call    ??$?4U?$default_delete@VCaptureStateUtility@@@std@@$0A@@?$unique_ptr@VCaptureStateUtility@@U?$default_delete@VCaptureStateUtility@@@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::unique_ptr<CaptureStateUtility>::operator=<std::default_delete<CaptureStateUtility>,0>(std::unique_ptr<CaptureStateUtility> &&)
0x14005deb1  nop
0x14005deb2  lea     rcx, [rbp+280h+var_80]
0x14005deb9  call    ??1?$unique_ptr@VCaptureStateUtility@@U?$default_delete@VCaptureStateUtility@@@std@@@std@@QEAA@XZ; std::unique_ptr<CaptureStateUtility>::~unique_ptr<CaptureStateUtility>(void)
0x14005debe  mov     rcx, [rbp+280h+var_50]
0x14005dec5  xor     rcx, rsp; StackCookie
0x14005dec8  call    __security_check_cookie
0x14005decd  add     rsp, 348h
0x14005ded4  pop     r15
0x14005ded6  pop     r14
0x14005ded8  pop     r13
0x14005deda  pop     r12
0x14005dedc  pop     rdi
0x14005dedd  pop     rsi
0x14005dede  pop     rbx
0x14005dedf  pop     rbp
0x14005dee0  retn
```
