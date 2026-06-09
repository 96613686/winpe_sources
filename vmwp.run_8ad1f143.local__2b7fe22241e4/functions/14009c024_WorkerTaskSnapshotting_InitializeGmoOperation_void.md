# WorkerTaskSnapshotting::InitializeGmoOperation(void)

- ea: `0x14009c024`
- end: `0x14009c4ae`
- name: `?InitializeGmoOperation@WorkerTaskSnapshotting@@AEAAXXZ`
- size: `1162`
- prototype: `void __fastcall(WorkerTaskSnapshotting *__hidden this)`
- caller_count: `1`
- callee_count: `25`
- tags: `service_task, installer_update`

## callers

- `0x14018c4fc`

## callees

- `0x14002ed90`
- `0x14006af58`
- `0x14009b23c`
- `0x14009b2c8`
- `0x14009b5a8`
- `0x14009b6c4`
- `0x14009b804`
- `0x14009c024`
- `0x14009c4c0`
- `0x14009d070`
- `0x14009d7cc`
- `0x14009d820`
- `0x14009dbc0`
- `0x14009fa0c`
- `0x1400d1318`
- `0x1400d1568`
- `0x1400d15c4`
- `0x140132960`
- `0x140132d0c`
- `0x14013361c`
- `0x140187f9c`
- `0x140188d78`
- `0x140197408`
- `0x1401974e8`
- `0x1402c2010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14009c3ba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14009c3ba`
- `vid!VidCloneTemplateCreate` at `0x14009c3a6`
- `vid!VidCloneTemplateCreate` at `0x14009c3a6`

## string_xrefs

- `0x14009c081`: `onecore\vm\worker\wpcore\workertasksnapshotting.cpp`
- `0x14009c0a9`: `onecore\vm\worker\wpcore\workertasksnapshotting.cpp`
- `0x14009c202`: `onecore\vm\worker\wpcore\workertasksnapshotting.cpp`
- `0x14009c2b3`: `onecore\vm\worker\wpcore\workertasksnapshotting.cpp`
- `0x14009c362`: `onecore\vm\worker\wpcore\workertasksnapshotting.cpp`
- `0x14009c3f3`: `onecore\vm\worker\wpcore\workertasksnapshotting.cpp`
- `0x14009c42d`: `onecore\vm\worker\wpcore\workertasksnapshotting.cpp`
- `0x14009c458`: `onecore\vm\worker\wpcore\workertasksnapshotting.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall WorkerTaskSnapshotting::InitializeGmoOperation(WorkerTaskSnapshotting *this)
{
  __int64 v2; // r15
  bool v3; // si
  __int64 CurrentActivity; // rbx
  CaptureStateUtility *v5; // rdi
  __int64 v6; // rax
  __int64 v7; // r9
  CaptureStateUtility *v8; // rbx
  __int64 v9; // r9
  unsigned int v10; // esi
  int v11; // eax
  VirtualMachine *v12; // rcx
  int v13; // eax
  unsigned __int64 RamSizeInPages; // rax
  int v15; // eax
  const char *v16; // r9
  int v17; // eax
  int v18; // eax
  __int64 (__fastcall ***v19)(_QWORD); // rcx
  __int64 v20; // rax
  signed int LastError; // eax
  struct MemoryNotificationListener *v22; // rdx
  int v23; // eax
  unsigned int v24; // [rsp+20h] [rbp-E0h]
  unsigned __int64 v25; // [rsp+20h] [rbp-E0h]
  int v26; // [rsp+20h] [rbp-E0h]
  char v27[336]; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v28[336]; // [rsp+1A0h] [rbp+A0h] BYREF
  int v29; // [rsp+2F0h] [rbp+1F0h] BYREF
  CaptureStateUtility *v30; // [rsp+2F8h] [rbp+1F8h] BYREF
  __int128 v31; // [rsp+300h] [rbp+200h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+368h] [rbp+268h]

  v29 = 0;
  v31 = 0;
  v2 = qword_1403C03B0;
  if ( qword_1403C03B0 == 3 )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x38F,
      (unsigned int)"onecore\\vm\\worker\\wpcore\\workertasksnapshotting.cpp",
      (const char *)0x32,
      v24);
  if ( BYTE6(qword_1403C05BC) )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x397,
      (unsigned int)"onecore\\vm\\worker\\wpcore\\workertasksnapshotting.cpp",
      (const char *)0x32,
      v24);
  (*(void (__fastcall **)(_QWORD, int *))(**(_QWORD **)(*((_QWORD *)this + 2) + 1072LL) + 112LL))(
    *(_QWORD *)(*((_QWORD *)this + 2) + 1072LL),
    &v29);
  v3 = v29 != 0;
  CurrentActivity = WorkerAsyncTask<VmWorkerTrace::SnapshottingTask>::GetCurrentActivity(this, v28);
  v5 = (CaptureStateUtility *)operator new(0x160u);
  v30 = v5;
  memset_0(v5, 0, 0x160u);
  v6 = VmWorkerTrace::SnapshottingTask::SnapshottingTask(v27, CurrentActivity);
  LOBYTE(v7) = v3;
  v8 = (CaptureStateUtility *)CaptureStateUtility::CaptureStateUtility(v5, *((_QWORD *)this + 2), v6, v7);
  v30 = v8;
  VmWorkerTrace::SnapshottingTask::~SnapshottingTask((VmWorkerTrace::SnapshottingTask *)v28);
  CaptureStateUtility::SuspendAndSaveEpf(v8, *((struct VmRepository **)this + 133));
  CaptureStateUtility::SuspendAndSaveSchedulerAssist(v8, *((struct VmRepository **)this + 133));
  v10 = *(_DWORD *)(*(_QWORD *)(*((_QWORD *)this + 2) + 1416LL) + 376LL);
  if ( v29 )
  {
    if ( *((_BYTE *)v8 + 344) )
    {
      v11 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(*(_QWORD *)v8 + 1072LL) + 168LL))(*(_QWORD *)(*(_QWORD *)v8 + 1072LL));
      if ( v11 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xB3,
          (unsigned int)"onecore\\vm\\worker\\wpcore\\capturestateutility.cpp",
          (const char *)(unsigned int)v11,
          v24);
      *((_BYTE *)v8 + 347) = 1;
    }
  }
  else
  {
    CaptureStateUtility::InitializeBalloonedPagesBitmap(v8);
  }
  v12 = (VirtualMachine *)*((_QWORD *)this + 2);
  if ( *((_BYTE *)v12 + 2968) )
  {
    v13 = VirtualMachine::SaveIgvmSaveState(v12, *((struct VmRepository **)this + 133));
    if ( v13 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x3B9,
        (unsigned int)"onecore\\vm\\worker\\wpcore\\workertasksnapshotting.cpp",
        (const char *)(unsigned int)v13,
        v24);
  }
  v25 = qword_1403C0450;
  LOBYTE(v9) = 1;
  MemoryManager::SaveRamInformation(&MemoryManager::m_Instance, *((_QWORD *)this + 133), 0, v9);
  (*(void (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)(*((_QWORD *)this + 2) + 1024LL) + 256LL))(
    *(_QWORD *)(*((_QWORD *)this + 2) + 1024LL),
    *((_QWORD *)this + 133));
  MemoryManager::SaveVtlProtections((MemoryManager *)&MemoryManager::m_Instance, *((struct VmRepository **)this + 133));
  RamSizeInPages = MemoryManager::GetRamSizeInPages((MemoryManager *)&MemoryManager::m_Instance);
  v15 = GmoRamOperationSnapshot::Initialize(
          (WorkerTaskSnapshotting *)((char *)this + 672),
          *((void **)this + 133),
          *((struct VirtualMachine **)this + 2),
          *((struct IVmSimpleTask **)this + 3),
          v25,
          0,
          RamSizeInPages,
          0,
          v10);
  if ( v15 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x3D8,
      (unsigned int)"onecore\\vm\\worker\\wpcore\\workertasksnapshotting.cpp",
      (const char *)(unsigned int)v15,
      v26);
  if ( v29 && *((_BYTE *)v8 + 344) )
  {
    if ( !*((_BYTE *)v8 + 347) )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0xC0,
        (unsigned int)"onecore\\vm\\worker\\wpcore\\capturestateutility.cpp",
        v16);
    v17 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64, __int64))(**(_QWORD **)(*(_QWORD *)v8 + 1072LL) + 184LL))(
            *(_QWORD *)(*(_QWORD *)v8 + 1072LL),
            *((unsigned int *)this + 218),
            256,
            2);
    if ( v17 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xC4,
        (unsigned int)"onecore\\vm\\worker\\wpcore\\capturestateutility.cpp",
        (const char *)(unsigned int)v17,
        v26);
    *((_BYTE *)v8 + 348) = 1;
  }
  v18 = GmoRamOperation::WorkThreadsStart((WorkerTaskSnapshotting *)((char *)this + 672));
  if ( v18 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x3E2,
      (unsigned int)"onecore\\vm\\worker\\wpcore\\workertasksnapshotting.cpp",
      (const char *)(unsigned int)v18,
      v26);
  if ( v2 == 2 )
  {
    v19 = (__int64 (__fastcall ***)(_QWORD))(*(_QWORD *)(*((_QWORD *)this + 2) + 1024LL) + 24LL);
    v20 = (**v19)(v19);
    if ( !(unsigned int)VidCloneTemplateCreate(v20, 1, &v31) )
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
        (void *)0x3EE,
        (unsigned int)"onecore\\vm\\worker\\wpcore\\workertasksnapshotting.cpp",
        (const char *)(unsigned int)LastError,
        v26);
    }
  }
  else
  {
    v22 = (WorkerTaskSnapshotting *)((char *)this + 920);
    if ( this == (WorkerTaskSnapshotting *)-672LL )
      v22 = 0;
    if ( !(unsigned int)MemoryManager::SetRamNotificationListener((MemoryManager *)&MemoryManager::m_Instance, v22) )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x3FA,
        (unsigned int)"onecore\\vm\\worker\\wpcore\\workertasksnapshotting.cpp",
        (const char *)0x80004005LL,
        v26);
    v23 = GmoRamOperationSnapshot::SetMemoryIntercepts((WorkerTaskSnapshotting *)((char *)this + 672));
    if ( v23 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x3FF,
        (unsigned int)"onecore\\vm\\worker\\wpcore\\workertasksnapshotting.cpp",
        (const char *)(unsigned int)v23,
        v26);
  }
  std::unique_ptr<CaptureStateUtility>::operator=<std::default_delete<CaptureStateUtility>,0>((char *)this + 944, &v30);
  std::unique_ptr<CaptureStateUtility>::~unique_ptr<CaptureStateUtility>(&v30);
}

```

## disassembly

```asm
0x14009c024  push    rbp
0x14009c026  push    rbx
0x14009c027  push    rsi
0x14009c028  push    rdi
0x14009c029  push    r12
0x14009c02b  push    r13
0x14009c02d  push    r14
0x14009c02f  push    r15
0x14009c031  lea     rbp, [rsp-228h]
0x14009c039  sub     rsp, 328h
0x14009c040  mov     rax, cs:__security_cookie
0x14009c047  xor     rax, rsp
0x14009c04a  mov     [rbp+260h+var_50], rax
0x14009c051  mov     r14, rcx
0x14009c054  xor     r13d, r13d
0x14009c057  mov     [rbp+260h+var_70], r13d
0x14009c05e  xorps   xmm0, xmm0
0x14009c061  movdqa  [rbp+260h+var_60], xmm0
0x14009c069  mov     r15, cs:qword_1403C03B0
0x14009c070  cmp     r15, 3
0x14009c074  jnz     short loc_14009C093
0x14009c076  mov     rcx, [rbp+268h]; this
0x14009c07d  lea     r9d, [r13+32h]; char *
0x14009c081  lea     r8, aOnecoreVmWorke_140; "onecore\\vm\\worker\\wpcore\\workertask"...
0x14009c088  mov     edx, 38Fh; void *
0x14009c08d  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x14009c093  cmp     byte ptr cs:qword_1403C05BC+6, r13b
0x14009c09a  jz      short loc_14009C0BB
0x14009c09c  mov     rcx, [rbp+268h]; this
0x14009c0a3  mov     r9d, 32h ; '2'; char *
0x14009c0a9  lea     r8, aOnecoreVmWorke_140; "onecore\\vm\\worker\\wpcore\\workertask"...
0x14009c0b0  mov     edx, 397h; void *
0x14009c0b5  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x14009c0bb  mov     rax, [rcx+10h]
0x14009c0bf  mov     rcx, [rax+430h]
0x14009c0c6  mov     rax, [rcx]
0x14009c0c9  lea     rdx, [rbp+260h+var_70]
0x14009c0d0  mov     rax, [rax+70h]
0x14009c0d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14009c0d9  cmp     [rbp+260h+var_70], r13d
0x14009c0e0  setnz   sil
0x14009c0e4  lea     rdx, [rbp+260h+var_1C0]
0x14009c0eb  mov     rcx, r14
0x14009c0ee  call    ?GetCurrentActivity@?$WorkerAsyncTask@VSnapshottingTask@VmWorkerTrace@@@@IEAA?AVSnapshottingTask@VmWorkerTrace@@XZ; WorkerAsyncTask<VmWorkerTrace::SnapshottingTask>::GetCurrentActivity(void)
0x14009c0f3  mov     rbx, rax
0x14009c0f6  mov     r12d, 160h
0x14009c0fc  mov     ecx, r12d; Size
0x14009c0ff  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14009c104  mov     rdi, rax
0x14009c107  mov     [rbp+260h+var_68], rax
0x14009c10e  mov     r8d, r12d; Size
0x14009c111  xor     edx, edx; Val
0x14009c113  mov     rcx, rax; void *
0x14009c116  call    memset_0
0x14009c11b  mov     rdx, rbx
0x14009c11e  lea     rcx, [rsp+360h+var_310]
0x14009c123  call    ??0SnapshottingTask@VmWorkerTrace@@QEAA@$$QEAV01@@Z; VmWorkerTrace::SnapshottingTask::SnapshottingTask(VmWorkerTrace::SnapshottingTask &&)
0x14009c128  mov     r9b, sil
0x14009c12b  mov     r8, rax
0x14009c12e  mov     rdx, [r14+10h]
0x14009c132  mov     rcx, rdi
0x14009c135  call    ??0CaptureStateUtility@@QEAA@PEAVVirtualMachine@@VSnapshottingTask@VmWorkerTrace@@_N@Z; CaptureStateUtility::CaptureStateUtility(VirtualMachine *,VmWorkerTrace::SnapshottingTask,bool)
0x14009c13a  mov     rbx, rax
0x14009c13d  mov     [rbp+260h+var_68], rax
0x14009c144  lea     rcx, [rbp+260h+var_1C0]; this
0x14009c14b  call    ??1SnapshottingTask@VmWorkerTrace@@QEAA@XZ; VmWorkerTrace::SnapshottingTask::~SnapshottingTask(void)
0x14009c150  mov     rdx, [r14+428h]; struct VmRepository *
0x14009c157  mov     rcx, rbx; this
0x14009c15a  call    ?SuspendAndSaveEpf@CaptureStateUtility@@QEAAXPEAVVmRepository@@@Z; CaptureStateUtility::SuspendAndSaveEpf(VmRepository *)
0x14009c15f  mov     rdx, [r14+428h]; struct VmRepository *
0x14009c166  mov     rcx, rbx; this
0x14009c169  call    ?SuspendAndSaveSchedulerAssist@CaptureStateUtility@@QEAAXPEAVVmRepository@@@Z; CaptureStateUtility::SuspendAndSaveSchedulerAssist(VmRepository *)
0x14009c16e  mov     rax, [r14+10h]
0x14009c172  mov     rcx, [rax+588h]
0x14009c179  mov     esi, [rcx+178h]
0x14009c17f  cmp     [rbp+260h+var_70], r13d
0x14009c186  jz      short loc_14009C1D3
0x14009c188  cmp     [rbx+158h], r13b
0x14009c18f  jz      short loc_14009C1DB
0x14009c191  mov     rax, [rbx]
0x14009c194  mov     rcx, [rax+430h]
0x14009c19b  mov     rax, [rcx]
0x14009c19e  mov     rax, [rax+0A8h]
0x14009c1a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14009c1aa  mov     rcx, [rbp+268h]; this
0x14009c1b1  test    eax, eax
0x14009c1b3  jns     short loc_14009C1CA
0x14009c1b5  mov     r9d, eax; char *
0x14009c1b8  lea     r8, aOnecoreVmWorke_120; "onecore\\vm\\worker\\wpcore\\capturesta"...
0x14009c1bf  mov     edx, 0B3h; void *
0x14009c1c4  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14009c1ca  mov     byte ptr [rbx+15Bh], 1
0x14009c1d1  jmp     short loc_14009C1DB
0x14009c1d3  mov     rcx, rbx; this
0x14009c1d6  call    ?InitializeBalloonedPagesBitmap@CaptureStateUtility@@QEAAXXZ; CaptureStateUtility::InitializeBalloonedPagesBitmap(void)
0x14009c1db  mov     rcx, [r14+10h]; this
0x14009c1df  cmp     [rcx+0B98h], r13b
0x14009c1e6  jz      short loc_14009C214
0x14009c1e8  mov     rdx, [r14+428h]; struct VmRepository *
0x14009c1ef  call    ?SaveIgvmSaveState@VirtualMachine@@UEAAJPEAVVmRepository@@@Z; VirtualMachine::SaveIgvmSaveState(VmRepository *)
0x14009c1f4  mov     rcx, [rbp+268h]; this
0x14009c1fb  test    eax, eax
0x14009c1fd  jns     short loc_14009C214
0x14009c1ff  mov     r9d, eax; char *
0x14009c202  lea     r8, aOnecoreVmWorke_140; "onecore\\vm\\worker\\wpcore\\workertask"...
0x14009c209  mov     edx, 3B9h; void *
0x14009c20e  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14009c214  mov     [rsp+360h+var_338], r13; unsigned __int64
0x14009c219  mov     rax, cs:qword_1403C0450
0x14009c220  mov     [rsp+360h+var_340], rax; int
0x14009c225  mov     r9b, 1
0x14009c228  xor     r8d, r8d
0x14009c22b  mov     rdx, [r14+428h]
0x14009c232  lea     r12, ?m_Instance@MemoryManager@@0V1@A; MemoryManager MemoryManager::m_Instance
0x14009c239  mov     rcx, r12
0x14009c23c  call    ?SaveRamInformation@MemoryManager@@UEAAXPEAVVmRepository@@W4VmFastSaveType@@_NPEAVGmoBitmap@@PEAT_VM_PERSIST_FLAGS@@@Z; MemoryManager::SaveRamInformation(VmRepository *,VmFastSaveType,bool,GmoBitmap *,_VM_PERSIST_FLAGS *)
0x14009c241  mov     rax, [r14+10h]
0x14009c245  mov     rcx, [rax+400h]
0x14009c24c  mov     rax, [rcx]
0x14009c24f  mov     rdx, [r14+428h]
0x14009c256  mov     rax, [rax+100h]
0x14009c25d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14009c262  mov     rdx, [r14+428h]; struct VmRepository *
0x14009c269  mov     rcx, r12; this
0x14009c26c  call    ?SaveVtlProtections@MemoryManager@@UEAAXPEAVVmRepository@@@Z; MemoryManager::SaveVtlProtections(VmRepository *)
0x14009c271  mov     rcx, r12; this
0x14009c274  call    ?GetRamSizeInPages@MemoryManager@@UEBA_KXZ; MemoryManager::GetRamSizeInPages(void)
0x14009c279  lea     rdi, [r14+2A0h]
0x14009c280  mov     [rsp+360h+var_320], esi; unsigned int
0x14009c284  mov     [rsp+360h+var_328], r13; unsigned __int64
0x14009c289  mov     [rsp+360h+var_330], rax; unsigned __int64
0x14009c28e  mov     r9, [r14+18h]; struct IVmSimpleTask *
0x14009c292  mov     r8, [r14+10h]; struct VirtualMachine *
0x14009c296  mov     rdx, [r14+428h]; void *
0x14009c29d  mov     rcx, rdi; this
0x14009c2a0  call    ?Initialize@GmoRamOperationSnapshot@@QEAAJPEAXPEAVVirtualMachine@@PEAUIVmSimpleTask@@_K333I@Z; GmoRamOperationSnapshot::Initialize(void *,VirtualMachine *,IVmSimpleTask *,unsigned __int64,unsigned __int64,unsigned __int64,unsigned __int64,uint)
0x14009c2a5  mov     rcx, [rbp+268h]; this
0x14009c2ac  test    eax, eax
0x14009c2ae  jns     short loc_14009C2C5
0x14009c2b0  mov     r9d, eax; char *
0x14009c2b3  lea     r8, aOnecoreVmWorke_140; "onecore\\vm\\worker\\wpcore\\workertask"...
0x14009c2ba  mov     edx, 3D8h; void *
0x14009c2bf  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14009c2c5  cmp     [rbp+260h+var_70], r13d
0x14009c2cc  jz      short loc_14009C34C
0x14009c2ce  cmp     [rbx+158h], r13b
0x14009c2d5  jz      short loc_14009C34C
0x14009c2d7  mov     rcx, [rbp+268h]; this
0x14009c2de  cmp     [rbx+15Bh], r13b
0x14009c2e5  jnz     short loc_14009C2F9
0x14009c2e7  lea     r8, aOnecoreVmWorke_120; "onecore\\vm\\worker\\wpcore\\capturesta"...
0x14009c2ee  mov     edx, 0C0h; void *
0x14009c2f3  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x14009c2f9  mov     rax, [rbx]
0x14009c2fc  mov     rcx, [rax+430h]
0x14009c303  mov     rax, [rcx]
0x14009c306  mov     r9d, 2
0x14009c30c  mov     r8d, 100h
0x14009c312  mov     edx, [r14+368h]
0x14009c319  mov     rax, [rax+0B8h]
0x14009c320  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14009c325  mov     rcx, [rbp+268h]; this
0x14009c32c  test    eax, eax
0x14009c32e  jns     short loc_14009C345
0x14009c330  mov     r9d, eax; char *
0x14009c333  lea     r8, aOnecoreVmWorke_120; "onecore\\vm\\worker\\wpcore\\capturesta"...
0x14009c33a  mov     edx, 0C4h; void *
0x14009c33f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14009c345  mov     byte ptr [rbx+15Ch], 1
0x14009c34c  mov     rcx, rdi; this
0x14009c34f  call    ?WorkThreadsStart@GmoRamOperation@@QEAAJXZ; GmoRamOperation::WorkThreadsStart(void)
0x14009c354  mov     rcx, [rbp+268h]; this
0x14009c35b  test    eax, eax
0x14009c35d  jns     short loc_14009C374
0x14009c35f  mov     r9d, eax; char *
0x14009c362  lea     r8, aOnecoreVmWorke_140; "onecore\\vm\\worker\\wpcore\\workertask"...
0x14009c369  mov     edx, 3E2h; void *
0x14009c36e  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14009c374  cmp     r15, 2
0x14009c378  jnz     loc_14009C405
0x14009c37e  mov     rax, [r14+10h]
0x14009c382  mov     rcx, [rax+400h]
0x14009c389  add     rcx, 18h
0x14009c38d  mov     rax, [rcx]
0x14009c390  mov     rax, [rax]
0x14009c393  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14009c398  lea     r8, [rbp+260h+var_60]
0x14009c39f  lea     edx, [r15-1]
0x14009c3a3  mov     rcx, rax
0x14009c3a6  call    cs:__imp_VidCloneTemplateCreate
0x14009c3ad  nop     dword ptr [rax+rax+00h]
0x14009c3b2  test    eax, eax
0x14009c3b4  jnz     loc_14009C46A
0x14009c3ba  call    cs:__imp_GetLastError
0x14009c3c1  nop     dword ptr [rax+rax+00h]
0x14009c3c6  test    eax, 1FFF0000h
0x14009c3cb  jnz     short loc_14009C3DB
0x14009c3cd  test    eax, eax
0x14009c3cf  jle     short loc_14009C3E9
0x14009c3d1  movzx   eax, ax
0x14009c3d4  or      eax, 80070000h
0x14009c3d9  jmp     short loc_14009C3E9
0x14009c3db  test    eax, eax
0x14009c3dd  jle     short loc_14009C3E9
0x14009c3df  and     eax, 0FFFFFFFh
0x14009c3e4  or      eax, 80000000h
0x14009c3e9  mov     rcx, [rbp+268h]; this
0x14009c3f0  mov     r9d, eax; char *
0x14009c3f3  lea     r8, aOnecoreVmWorke_140; "onecore\\vm\\worker\\wpcore\\workertask"...
0x14009c3fa  mov     edx, 3EEh; void *
0x14009c3ff  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14009c405  test    rdi, rdi
0x14009c408  lea     rdx, [r14+398h]
0x14009c40f  jnz     short loc_14009C414
0x14009c411  mov     rdx, r13; struct MemoryNotificationListener *
0x14009c414  mov     rbx, [rbp+268h]
0x14009c41b  mov     rcx, r12; this
0x14009c41e  call    ?SetRamNotificationListener@MemoryManager@@UEAAHPEAVMemoryNotificationListener@@@Z; MemoryManager::SetRamNotificationListener(MemoryNotificationListener *)
0x14009c423  test    eax, eax
0x14009c425  jnz     short loc_14009C442
0x14009c427  mov     r9d, 80004005h; char *
0x14009c42d  lea     r8, aOnecoreVmWorke_140; "onecore\\vm\\worker\\wpcore\\workertask"...
0x14009c434  mov     edx, 3FAh; void *
0x14009c439  mov     rcx, rbx; this
0x14009c43c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14009c442  mov     rcx, rdi; this
0x14009c445  call    ?SetMemoryIntercepts@GmoRamOperationSnapshot@@QEAAJXZ; GmoRamOperationSnapshot::SetMemoryIntercepts(void)
0x14009c44a  mov     rcx, [rbp+268h]; this
0x14009c451  test    eax, eax
0x14009c453  jns     short loc_14009C46A
0x14009c455  mov     r9d, eax; char *
0x14009c458  lea     r8, aOnecoreVmWorke_140; "onecore\\vm\\worker\\wpcore\\workertask"...
0x14009c45f  mov     edx, 3FFh; void *
0x14009c464  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14009c46a  lea     rcx, [r14+3B0h]
0x14009c471  lea     rdx, [rbp+260h+var_68]
0x14009c478  call    ??$?4U?$default_delete@VCaptureStateUtility@@@std@@$0A@@?$unique_ptr@VCaptureStateUtility@@U?$default_delete@VCaptureStateUtility@@@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::unique_ptr<CaptureStateUtility>::operator=<std::default_delete<CaptureStateUtility>,0>(std::unique_ptr<CaptureStateUtility> &&)
0x14009c47d  nop
0x14009c47e  lea     rcx, [rbp+260h+var_68]
0x14009c485  call    ??1?$unique_ptr@VCaptureStateUtility@@U?$default_delete@VCaptureStateUtility@@@std@@@std@@QEAA@XZ; std::unique_ptr<CaptureStateUtility>::~unique_ptr<CaptureStateUtility>(void)
0x14009c48a  mov     rcx, [rbp+260h+var_50]
0x14009c491  xor     rcx, rsp; StackCookie
0x14009c494  call    __security_check_cookie
0x14009c499  add     rsp, 328h
0x14009c4a0  pop     r15
0x14009c4a2  pop     r14
0x14009c4a4  pop     r13
0x14009c4a6  pop     r12
0x14009c4a8  pop     rdi
0x14009c4a9  pop     rsi
0x14009c4aa  pop     rbx
0x14009c4ab  pop     rbp
0x14009c4ac  retn
```
