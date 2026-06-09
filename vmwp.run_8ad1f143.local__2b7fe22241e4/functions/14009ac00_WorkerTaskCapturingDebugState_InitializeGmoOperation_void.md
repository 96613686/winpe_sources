# WorkerTaskCapturingDebugState::InitializeGmoOperation(void)

- ea: `0x14009ac00`
- end: `0x14009b15a`
- name: `?InitializeGmoOperation@WorkerTaskCapturingDebugState@@AEAAXXZ`
- size: `1370`
- prototype: `void __fastcall(WorkerTaskCapturingDebugState *__hidden this)`
- caller_count: `1`
- callee_count: `38`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x140189bcc`

## callees

- `0x14002ed90`
- `0x14006af58`
- `0x14008f858`
- `0x140095d40`
- `0x14009ac00`
- `0x14009b170`
- `0x14009b1a0`
- `0x14009b23c`
- `0x14009b25c`
- `0x14009b2c8`
- `0x14009b2fc`
- `0x14009b584`
- `0x14009b5a8`
- `0x14009b6a0`
- `0x14009b6c4`
- `0x14009b804`
- `0x14009ba30`
- `0x14009bbe4`
- `0x14009c4c0`
- `0x14009d070`
- `0x14009d7cc`
- `0x14009dbc0`
- `0x1400d1318`
- `0x1400d1568`
- `0x1400d15c4`
- `0x140132960`
- `0x140132d0c`
- `0x14013361c`
- `0x140166a30`
- `0x1401847b4`
- `0x140184b20`
- `0x140187f9c`
- `0x140188560`
- `0x140188d78`
- `0x140197408`
- `0x1401974e8`
- `0x140207b20`
- `0x1402c2010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14009afb2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14009afb2`
- `vid!VidCloneTemplateCreate` at `0x14009af9e`
- `vid!VidCloneTemplateCreate` at `0x14009af9e`

## string_xrefs

- `0x14009ac56`: `onecore\vm\worker\wpcore\workertaskcapturingdebugstate.cpp`
- `0x14009ae65`: `onecore\vm\worker\wpcore\workertaskcapturingdebugstate.cpp`
- `0x14009af2c`: `onecore\vm\worker\wpcore\workertaskcapturingdebugstate.cpp`
- `0x14009af5c`: `onecore\vm\worker\wpcore\workertaskcapturingdebugstate.cpp`
- `0x14009afeb`: `onecore\vm\worker\wpcore\workertaskcapturingdebugstate.cpp`
- `0x14009b04f`: `onecore\vm\worker\wpcore\workertaskcapturingdebugstate.cpp`
- `0x14009b0c9`: `onecore\vm\worker\wpcore\workertaskcapturingdebugstate.cpp`
- `0x14009b0f8`: `onecore\vm\worker\wpcore\workertaskcapturingdebugstate.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
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
  v2 = qword_1403C03B0;
  if ( qword_1403C03B0 == 3 )
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
  v32 = qword_1403C0450;
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
0x14009ac00  push    rbp
0x14009ac02  push    rbx
0x14009ac03  push    rsi
0x14009ac04  push    rdi
0x14009ac05  push    r12
0x14009ac07  push    r13
0x14009ac09  push    r14
0x14009ac0b  push    r15
0x14009ac0d  lea     rbp, [rsp-248h]
0x14009ac15  sub     rsp, 348h
0x14009ac1c  mov     rax, cs:__security_cookie
0x14009ac23  xor     rax, rsp
0x14009ac26  mov     [rbp+280h+var_50], rax
0x14009ac2d  mov     rsi, rcx
0x14009ac30  xor     r15d, r15d
0x14009ac33  xorps   xmm0, xmm0
0x14009ac36  movdqa  [rbp+280h+var_60], xmm0
0x14009ac3e  mov     r12, cs:qword_1403C03B0
0x14009ac45  cmp     r12, 3
0x14009ac49  jnz     short loc_14009AC68
0x14009ac4b  mov     rcx, [rbp+288h]; this
0x14009ac52  lea     r9d, [r15+32h]; char *
0x14009ac56  lea     r8, aOnecoreVmWorke_124; "onecore\\vm\\worker\\wpcore\\workertask"...
0x14009ac5d  mov     edx, 2CAh; void *
0x14009ac62  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x14009ac68  lea     rdx, [rbp+280h+var_1D0]
0x14009ac6f  call    ?GetCurrentActivity@?$WorkerAsyncTask@VSnapshottingTask@VmWorkerTrace@@@@IEAA?AVSnapshottingTask@VmWorkerTrace@@XZ; WorkerAsyncTask<VmWorkerTrace::SnapshottingTask>::GetCurrentActivity(void)
0x14009ac74  mov     rbx, rax
0x14009ac77  mov     r14d, 160h
0x14009ac7d  mov     ecx, r14d; Size
0x14009ac80  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14009ac85  mov     rdi, rax
0x14009ac88  mov     [rbp+280h+var_80], rax
0x14009ac8f  mov     r8d, r14d; Size
0x14009ac92  xor     edx, edx; Val
0x14009ac94  mov     rcx, rax; void *
0x14009ac97  call    memset_0
0x14009ac9c  mov     rdx, rbx
0x14009ac9f  lea     rcx, [rsp+380h+var_320]
0x14009aca4  call    ??0SnapshottingTask@VmWorkerTrace@@QEAA@$$QEAV01@@Z; VmWorkerTrace::SnapshottingTask::SnapshottingTask(VmWorkerTrace::SnapshottingTask &&)
0x14009aca9  xor     r9d, r9d
0x14009acac  mov     r8, rax
0x14009acaf  mov     rdx, [rsi+10h]
0x14009acb3  mov     rcx, rdi
0x14009acb6  call    ??0CaptureStateUtility@@QEAA@PEAVVirtualMachine@@VSnapshottingTask@VmWorkerTrace@@_N@Z; CaptureStateUtility::CaptureStateUtility(VirtualMachine *,VmWorkerTrace::SnapshottingTask,bool)
0x14009acbb  mov     rbx, rax
0x14009acbe  mov     [rbp+280h+var_80], rax
0x14009acc5  lea     rcx, [rbp+280h+var_1D0]; this
0x14009accc  call    ??1SnapshottingTask@VmWorkerTrace@@QEAA@XZ; VmWorkerTrace::SnapshottingTask::~SnapshottingTask(void)
0x14009acd1  mov     rdx, [rsi+1F8h]; struct VmRepository *
0x14009acd8  mov     rcx, rbx; this
0x14009acdb  call    ?SuspendAndSaveEpf@CaptureStateUtility@@QEAAXPEAVVmRepository@@@Z; CaptureStateUtility::SuspendAndSaveEpf(VmRepository *)
0x14009ace0  mov     rdx, [rsi+1F8h]; struct VmRepository *
0x14009ace7  mov     rcx, rbx; this
0x14009acea  call    ?SuspendAndSaveSchedulerAssist@CaptureStateUtility@@QEAAXPEAVVmRepository@@@Z; CaptureStateUtility::SuspendAndSaveSchedulerAssist(VmRepository *)
0x14009acef  mov     rax, [rsi+10h]
0x14009acf3  mov     rcx, [rax+588h]
0x14009acfa  mov     r13d, [rcx+178h]
0x14009ad01  mov     rcx, rbx; this
0x14009ad04  call    ?InitializeBalloonedPagesBitmap@CaptureStateUtility@@QEAAXXZ; CaptureStateUtility::InitializeBalloonedPagesBitmap(void)
0x14009ad09  mov     [rsp+380h+var_358], r15; unsigned __int64
0x14009ad0e  mov     rax, cs:qword_1403C0450
0x14009ad15  mov     [rsp+380h+var_360], rax; int
0x14009ad1a  mov     ebx, 1
0x14009ad1f  mov     r9b, bl
0x14009ad22  xor     r8d, r8d
0x14009ad25  mov     rdx, [rsi+1F8h]
0x14009ad2c  lea     rdi, ?m_Instance@MemoryManager@@0V1@A; MemoryManager MemoryManager::m_Instance
0x14009ad33  mov     rcx, rdi
0x14009ad36  call    ?SaveRamInformation@MemoryManager@@UEAAXPEAVVmRepository@@W4VmFastSaveType@@_NPEAVGmoBitmap@@PEAT_VM_PERSIST_FLAGS@@@Z; MemoryManager::SaveRamInformation(VmRepository *,VmFastSaveType,bool,GmoBitmap *,_VM_PERSIST_FLAGS *)
0x14009ad3b  mov     rax, [rsi+10h]
0x14009ad3f  mov     rcx, [rax+400h]
0x14009ad46  mov     rax, [rcx]
0x14009ad49  mov     rdx, [rsi+1F8h]
0x14009ad50  mov     rax, [rax+100h]
0x14009ad57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14009ad5c  mov     rdx, [rsi+1F8h]; struct VmRepository *
0x14009ad63  mov     rcx, rdi; this
0x14009ad66  call    ?SaveVtlProtections@MemoryManager@@UEAAXPEAVVmRepository@@@Z; MemoryManager::SaveVtlProtections(VmRepository *)
0x14009ad6b  mov     [rsp+380h+var_330], r15
0x14009ad70  mov     eax, [rsi+1D0h]
0x14009ad76  sub     eax, ebx
0x14009ad78  test    eax, 0FFFFFFFDh
0x14009ad7d  jnz     short loc_14009ADB7
0x14009ad7f  mov     rcx, [rsi+10h]; this
0x14009ad83  cmp     [rcx+0A68h], r15b
0x14009ad8a  jz      short loc_14009ADB7
0x14009ad8c  mov     [rsp+380h+var_328], r15
0x14009ad91  lea     r8, [rsp+380h+var_330]; unsigned __int64 *
0x14009ad96  lea     rdx, [rsp+380h+var_328]; unsigned __int64 *
0x14009ad9b  call    ?GetVtl2PrivateRamRange@VirtualMachine@@UEBAXPEA_K0@Z; VirtualMachine::GetVtl2PrivateRamRange(unsigned __int64 *,unsigned __int64 *)
0x14009ada0  mov     rdx, [rsp+380h+var_328]; unsigned __int64
0x14009ada5  mov     rcx, rdi; this
0x14009ada8  call    ?GpaIndexToRamIndex@MemoryManager@@UEAA_K_K@Z; MemoryManager::GpaIndexToRamIndex(unsigned __int64)
0x14009adad  mov     r14, rax
0x14009adb0  mov     r15, [rsp+380h+var_330]
0x14009adb5  jmp     short loc_14009ADC5
0x14009adb7  mov     r14, r15
0x14009adba  mov     rcx, rdi; this
0x14009adbd  call    ?GetRamSizeInPages@MemoryManager@@UEBA_KXZ; MemoryManager::GetRamSizeInPages(void)
0x14009adc2  mov     r15, rax
0x14009adc5  cmp     dword ptr [rsi+1D0h], 2
0x14009adcc  jz      loc_14009AE77
0x14009add2  mov     ecx, 110h; Size
0x14009add7  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14009addc  mov     rdi, rax
0x14009addf  mov     [rsp+380h+var_330], rax
0x14009ade4  xor     edx, edx; Val
0x14009ade6  mov     r8d, 110h; Size
0x14009adec  mov     rcx, rax; void *
0x14009adef  call    memset_0
0x14009adf4  mov     rcx, rdi; this
0x14009adf7  call    ??0GmoRamOperationSnapshot@@QEAA@XZ; GmoRamOperationSnapshot::GmoRamOperationSnapshot(void)
0x14009adfc  mov     [rsp+380h+var_330], 0
0x14009ae05  mov     rcx, [rsi+1A8h]; this
0x14009ae0c  mov     [rsi+1A8h], rax
0x14009ae13  test    rcx, rcx
0x14009ae16  jz      short loc_14009AE1F
0x14009ae18  mov     edx, ebx; unsigned int
0x14009ae1a  call    ??_EGmoRamOperationSnapshot@@UEAAPEAXI@Z; GmoRamOperationSnapshot::`vector deleting destructor'(uint)
0x14009ae1f  lea     rcx, [rsp+380h+var_330]
0x14009ae24  call    ??1?$unique_ptr@VGmoRamOperationSnapshot@@U?$default_delete@VGmoRamOperationSnapshot@@@std@@@std@@QEAA@XZ; std::unique_ptr<GmoRamOperationSnapshot>::~unique_ptr<GmoRamOperationSnapshot>(void)
0x14009ae29  mov     [rsp+380h+var_340], r13d; unsigned int
0x14009ae2e  mov     [rsp+380h+var_348], r14; unsigned __int64
0x14009ae33  mov     [rsp+380h+var_350], r15; unsigned __int64
0x14009ae38  mov     r9, [rsi+18h]; struct IVmSimpleTask *
0x14009ae3c  mov     r8, [rsi+10h]; struct VirtualMachine *
0x14009ae40  mov     rdx, [rsi+1F8h]; void *
0x14009ae47  mov     rcx, [rsi+1A8h]; this
0x14009ae4e  call    ?Initialize@GmoRamOperationSnapshot@@QEAAJPEAXPEAVVirtualMachine@@PEAUIVmSimpleTask@@_K333I@Z; GmoRamOperationSnapshot::Initialize(void *,VirtualMachine *,IVmSimpleTask *,unsigned __int64,unsigned __int64,unsigned __int64,unsigned __int64,uint)
0x14009ae53  mov     rcx, [rbp+288h]; this
0x14009ae5a  test    eax, eax
0x14009ae5c  jns     loc_14009AF3E
0x14009ae62  mov     r9d, eax; char *
0x14009ae65  lea     r8, aOnecoreVmWorke_124; "onecore\\vm\\worker\\wpcore\\workertask"...
0x14009ae6c  mov     edx, 30Ah; void *
0x14009ae71  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14009ae77  mov     ecx, 0F8h; Size
0x14009ae7c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14009ae81  mov     rdi, rax
0x14009ae84  mov     [rsp+380h+var_330], rax
0x14009ae89  xor     edx, edx; Val
0x14009ae8b  mov     r8d, 0F8h; Size
0x14009ae91  mov     rcx, rax; void *
0x14009ae94  call    memset_0
0x14009ae99  xor     edx, edx; Val
0x14009ae9b  mov     r8d, 0F8h; Size
0x14009aea1  mov     rcx, rdi; void *
0x14009aea4  call    memset_0
0x14009aea9  mov     rcx, rdi; this
0x14009aeac  call    ??0GmoRamOperationSave@@QEAA@XZ; GmoRamOperationSave::GmoRamOperationSave(void)
0x14009aeb1  mov     [rsp+380h+var_330], 0
0x14009aeba  mov     rcx, [rsi+1B0h]; this
0x14009aec1  mov     [rsi+1B0h], rax
0x14009aec8  test    rcx, rcx
0x14009aecb  jz      short loc_14009AED4
0x14009aecd  mov     edx, ebx; unsigned int
0x14009aecf  call    ??_GGmoRamOperationSave@@UEAAPEAXI@Z; GmoRamOperationSave::`scalar deleting destructor'(uint)
0x14009aed4  lea     rcx, [rsp+380h+var_330]
0x14009aed9  call    ??1?$unique_ptr@VGmoRamOperationSave@@U?$default_delete@VGmoRamOperationSave@@@std@@@std@@QEAA@XZ; std::unique_ptr<GmoRamOperationSave>::~unique_ptr<GmoRamOperationSave>(void)
0x14009aede  mov     [rsp+380h+var_338], ebx
0x14009aee2  mov     [rsp+380h+var_340], r13d
0x14009aee7  mov     [rsp+380h+var_348], r14
0x14009aeec  mov     [rsp+380h+var_350], r15
0x14009aef1  mov     [rsp+380h+var_358], 5
0x14009aefa  mov     [rsp+380h+var_360], 63h ; 'c'; int
0x14009af03  mov     r9, [rsi+18h]
0x14009af07  mov     r8, [rsi+10h]
0x14009af0b  mov     rdx, [rsi+1F8h]
0x14009af12  mov     rcx, [rsi+1B0h]
0x14009af19  call    ?Initialize@GmoRamOperationSource@@QEAAJPEAXPEAVVirtualMachine@@PEAUIVmSimpleTask@@_K333IW4Flags@1@@Z; GmoRamOperationSource::Initialize(void *,VirtualMachine *,IVmSimpleTask *,unsigned __int64,unsigned __int64,unsigned __int64,unsigned __int64,uint,GmoRamOperationSource::Flags)
0x14009af1e  mov     rcx, [rbp+288h]; this
0x14009af25  test    eax, eax
0x14009af27  jns     short loc_14009AF3E
0x14009af29  mov     r9d, eax; char *
0x14009af2c  lea     r8, aOnecoreVmWorke_124; "onecore\\vm\\worker\\wpcore\\workertask"...
0x14009af33  mov     edx, 318h; void *
0x14009af38  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14009af3e  mov     rcx, rsi; this
0x14009af41  call    ?GetGmoRamOperation@WorkerTaskCapturingDebugState@@AEAAPEAVGmoRamOperationSource@@XZ; WorkerTaskCapturingDebugState::GetGmoRamOperation(void)
0x14009af46  mov     rcx, rax; this
0x14009af49  call    ?WorkThreadsStart@GmoRamOperation@@QEAAJXZ; GmoRamOperation::WorkThreadsStart(void)
0x14009af4e  mov     rcx, [rbp+288h]; this
0x14009af55  test    eax, eax
0x14009af57  jns     short loc_14009AF6E
0x14009af59  mov     r9d, eax; char *
0x14009af5c  lea     r8, aOnecoreVmWorke_124; "onecore\\vm\\worker\\wpcore\\workertask"...
0x14009af63  mov     edx, 31Fh; void *
0x14009af68  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14009af6e  cmp     r12, 2
0x14009af72  jnz     loc_14009AFFD
0x14009af78  mov     rax, [rsi+10h]
0x14009af7c  mov     rcx, [rax+400h]
0x14009af83  add     rcx, 18h
0x14009af87  mov     rax, [rcx]
0x14009af8a  mov     rax, [rax]
0x14009af8d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14009af92  lea     r8, [rbp+280h+var_60]
0x14009af99  mov     edx, ebx
0x14009af9b  mov     rcx, rax
0x14009af9e  call    cs:__imp_VidCloneTemplateCreate
0x14009afa5  nop     dword ptr [rax+rax+00h]
0x14009afaa  test    eax, eax
0x14009afac  jnz     loc_14009B116
0x14009afb2  call    cs:__imp_GetLastError
0x14009afb9  nop     dword ptr [rax+rax+00h]
0x14009afbe  test    eax, 1FFF0000h
0x14009afc3  jnz     short loc_14009AFD3
0x14009afc5  test    eax, eax
0x14009afc7  jle     short loc_14009AFE1
0x14009afc9  movzx   eax, ax
0x14009afcc  or      eax, 80070000h
0x14009afd1  jmp     short loc_14009AFE1
0x14009afd3  test    eax, eax
0x14009afd5  jle     short loc_14009AFE1
0x14009afd7  and     eax, 0FFFFFFFh
0x14009afdc  or      eax, 80000000h
0x14009afe1  mov     rcx, [rbp+288h]; this
0x14009afe8  mov     r9d, eax; char *
0x14009afeb  lea     r8, aOnecoreVmWorke_124; "onecore\\vm\\worker\\wpcore\\workertask"...
0x14009aff2  mov     edx, 32Bh; void *
0x14009aff7  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14009affd  cmp     dword ptr [rsi+1D0h], 2
0x14009b004  jz      loc_14009B116
0x14009b00a  mov     rax, [rsi+1A8h]
0x14009b011  lea     r8, [rax+0F8h]
0x14009b018  neg     rax
0x14009b01b  sbb     rdx, rdx
0x14009b01e  and     rdx, r8; struct MemoryNotificationListener *
0x14009b021  lea     rcx, ?m_Instance@MemoryManager@@0V1@A; this
0x14009b028  call    ?SetRamNotificationListener@MemoryManager@@UEAAHPEAVMemoryNotificationListener@@@Z; MemoryManager::SetRamNotificationListener(MemoryNotificationListener *)
0x14009b02d  test    eax, eax
0x14009b02f  jz      short loc_14009B061
0x14009b031  mov     rcx, [rsi+1A8h]; this
0x14009b038  call    ?SetMemoryIntercepts@GmoRamOperationSnapshot@@QEAAJXZ; GmoRamOperationSnapshot::SetMemoryIntercepts(void)
0x14009b03d  mov     rcx, [rbp+288h]; this
0x14009b044  test    eax, eax
0x14009b046  jns     loc_14009B116
0x14009b04c  mov     r9d, eax; char *
0x14009b04f  lea     r8, aOnecoreVmWorke_124; "onecore\\vm\\worker\\wpcore\\workertask"...
0x14009b056  mov     edx, 344h; void *
0x14009b05b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14009b061  xorps   xmm0, xmm0
0x14009b064  movups  [rbp+280h+var_78], xmm0
0x14009b06b  lea     rcx, [rsp+380h+var_328]
0x14009b070  call    ??$make_unique@VVmMachineLocalSettingsStore@Vml@@$$V$0A@@std@@YA?AV?$unique_ptr@VVmMachineLocalSettingsStore@Vml@@U?$default_delete@VVmMachineLocalSettingsStore@Vml@@@std@@@0@XZ; std::make_unique<Vml::VmMachineLocalSettingsStore,,0>(void)
0x14009b075  nop
0x14009b076  mov     rcx, [rax]
0x14009b079  mov     qword ptr [rax], 0
0x14009b080  mov     [rsp+380h+var_330], rcx
0x14009b085  lea     r9, [rsp+380h+var_330]
0x14009b08a  lea     rcx, [rbp+280h+var_78]
0x14009b091  call    ??0VirtualizationSettings@@QEAA@_NPEBG$$QEAV?$unique_ptr@VISettingsStore@@U?$default_delete@VISettingsStore@@@std@@@std@@@Z; VirtualizationSettings::VirtualizationSettings(bool,ushort const *,std::unique_ptr<ISettingsStore> &&)
0x14009b096  nop
0x14009b097  lea     rcx, [rsp+380h+var_330]
0x14009b09c  call    ??1?$unique_ptr@V?$VmDispatchContextWithParams@XPEAUIVmSimpleTask@@I$$QEAUMigrationTargetInit@Worker@Parameters@Migration@@@Vml@@U?$default_delete@V?$VmDispatchContextWithParams@XPEAUIVmSimpleTask@@I$$QEAUMigrationTargetInit@Worker@Parameters@Migration@@@Vml@@@std@@@std@@QEAA@XZ; std::unique_ptr<Vml::VmDispatchContextWithParams<void,IVmSimpleTask *,uint,Migration::Parameters::Worker::MigrationTargetInit &&>>::~unique_ptr<Vml::VmDispatchContextWithParams<void,IVmSimpleTask *,uint,Migration::Parameters::Worker::MigrationTargetInit &&>>(void)
0x14009b0a1  nop
0x14009b0a2  lea     rcx, [rsp+380h+var_328]
0x14009b0a7  call    ??1?$unique_ptr@V?$VmDispatchContextWithParams@XPEAUIVmSimpleTask@@I$$QEAUMigrationTargetInit@Worker@Parameters@Migration@@@Vml@@U?$default_delete@V?$VmDispatchContextWithParams@XPEAUIVmSimpleTask@@I$$QEAUMigrationTargetInit@Worker@Parameters@Migration@@@Vml@@@std@@@std@@QEAA@XZ; std::unique_ptr<Vml::VmDispatchContextWithParams<void,IVmSimpleTask *,uint,Migration::Parameters::Worker::MigrationTargetInit &&>>::~unique_ptr<Vml::VmDispatchContextWithParams<void,IVmSimpleTask *,uint,Migration::Parameters::Worker::MigrationTargetInit &&>>(void)
0x14009b0ac  mov     rbx, [rbp+288h]
0x14009b0b3  lea     rcx, [rbp+280h+var_78]; this
0x14009b0ba  call    ?GetAzureFeatureSetEnabled@VirtualizationSettings@@UEBA_NXZ; VirtualizationSettings::GetAzureFeatureSetEnabled(void)
0x14009b0bf  test    al, al
0x14009b0c1  jnz     short loc_14009B0DE
0x14009b0c3  mov     r9d, 80070032h; char *
0x14009b0c9  lea     r8, aOnecoreVmWorke_124; "onecore\\vm\\worker\\wpcore\\workertask"...
0x14009b0d0  mov     edx, 34Dh; void *
0x14009b0d5  mov     rcx, rbx; this
0x14009b0d8  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14009b0de  mov     rcx, [rsi+1A8h]; this
0x14009b0e5  call    ?SaveAllMemory@GmoRamOperationSnapshot@@QEAAJXZ; GmoRamOperationSnapshot::SaveAllMemory(void)
0x14009b0ea  mov     rcx, [rbp+288h]; this
0x14009b0f1  test    eax, eax
0x14009b0f3  jns     short loc_14009B10A
0x14009b0f5  mov     r9d, eax; char *
0x14009b0f8  lea     r8, aOnecoreVmWorke_124; "onecore\\vm\\worker\\wpcore\\workertask"...
0x14009b0ff  mov     edx, 34Eh; void *
0x14009b104  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14009b10a  lea     rcx, [rbp+280h+var_78+8]
0x14009b111  call    ??1?$unique_ptr@V?$VmDispatchContextWithParams@XPEAUIVmSimpleTask@@I$$QEAUMigrationTargetInit@Worker@Parameters@Migration@@@Vml@@U?$default_delete@V?$VmDispatchContextWithParams@XPEAUIVmSimpleTask@@I$$QEAUMigrationTargetInit@Worker@Parameters@Migration@@@Vml@@@std@@@std@@QEAA@XZ; std::unique_ptr<Vml::VmDispatchContextWithParams<void,IVmSimpleTask *,uint,Migration::Parameters::Worker::MigrationTargetInit &&>>::~unique_ptr<Vml::VmDispatchContextWithParams<void,IVmSimpleTask *,uint,Migration::Parameters::Worker::MigrationTargetInit &&>>(void)
0x14009b116  lea     rcx, [rsi+1B8h]
0x14009b11d  lea     rdx, [rbp+280h+var_80]
0x14009b124  call    ??$?4U?$default_delete@VCaptureStateUtility@@@std@@$0A@@?$unique_ptr@VCaptureStateUtility@@U?$default_delete@VCaptureStateUtility@@@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::unique_ptr<CaptureStateUtility>::operator=<std::default_delete<CaptureStateUtility>,0>(std::unique_ptr<CaptureStateUtility> &&)
0x14009b129  nop
0x14009b12a  lea     rcx, [rbp+280h+var_80]
0x14009b131  call    ??1?$unique_ptr@VCaptureStateUtility@@U?$default_delete@VCaptureStateUtility@@@std@@@std@@QEAA@XZ; std::unique_ptr<CaptureStateUtility>::~unique_ptr<CaptureStateUtility>(void)
0x14009b136  mov     rcx, [rbp+280h+var_50]
0x14009b13d  xor     rcx, rsp; StackCookie
0x14009b140  call    __security_check_cookie
0x14009b145  add     rsp, 348h
0x14009b14c  pop     r15
0x14009b14e  pop     r14
0x14009b150  pop     r13
0x14009b152  pop     r12
0x14009b154  pop     rdi
0x14009b155  pop     rsi
0x14009b156  pop     rbx
0x14009b157  pop     rbp
0x14009b158  retn
```
