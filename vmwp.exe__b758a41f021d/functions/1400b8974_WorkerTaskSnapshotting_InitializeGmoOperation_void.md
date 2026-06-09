# WorkerTaskSnapshotting::InitializeGmoOperation(void)

- ea: `0x1400b8974`
- end: `0x1400b8dfe`
- name: `?InitializeGmoOperation@WorkerTaskSnapshotting@@AEAAXXZ`
- size: `1162`
- prototype: `void __fastcall(WorkerTaskSnapshotting *__hidden this)`
- caller_count: `1`
- callee_count: `25`
- tags: `service_task, installer_update`

## callers

- `0x14017988c`

## callees

- `0x14003b7c0`
- `0x14005c71c`
- `0x14005c948`
- `0x14005dfbc`
- `0x14005e048`
- `0x14005e6e8`
- `0x140064f4c`
- `0x140078628`
- `0x1400b7900`
- `0x1400b81e0`
- `0x1400b8974`
- `0x1400b8e10`
- `0x1400b99c0`
- `0x1400ba144`
- `0x1400ba47c`
- `0x1400ba6cc`
- `0x1400bc53c`
- `0x14011ea40`
- `0x14011edec`
- `0x14011f6fc`
- `0x14017532c`
- `0x140176108`
- `0x1401861e8`
- `0x1401862c8`
- `0x1402cb010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400b8d0a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400b8d0a`
- `vid!VidCloneTemplateCreate` at `0x1400b8cf6`
- `vid!VidCloneTemplateCreate` at `0x1400b8cf6`

## string_xrefs

- `0x1400b89d1`: `onecore\vm\worker\wpcore\workertasksnapshotting.cpp`
- `0x1400b89f9`: `onecore\vm\worker\wpcore\workertasksnapshotting.cpp`
- `0x1400b8b52`: `onecore\vm\worker\wpcore\workertasksnapshotting.cpp`
- `0x1400b8c03`: `onecore\vm\worker\wpcore\workertasksnapshotting.cpp`
- `0x1400b8cb2`: `onecore\vm\worker\wpcore\workertasksnapshotting.cpp`
- `0x1400b8d43`: `onecore\vm\worker\wpcore\workertasksnapshotting.cpp`
- `0x1400b8d7d`: `onecore\vm\worker\wpcore\workertasksnapshotting.cpp`
- `0x1400b8da8`: `onecore\vm\worker\wpcore\workertasksnapshotting.cpp`

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
  v2 = qword_1403CC940;
  if ( qword_1403CC940 == 3 )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x38F,
      (unsigned int)"onecore\\vm\\worker\\wpcore\\workertasksnapshotting.cpp",
      (const char *)0x32,
      v24);
  if ( BYTE6(qword_1403CCB4C) )
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
  v25 = qword_1403CC9E0;
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
0x1400b8974  push    rbp
0x1400b8976  push    rbx
0x1400b8977  push    rsi
0x1400b8978  push    rdi
0x1400b8979  push    r12
0x1400b897b  push    r13
0x1400b897d  push    r14
0x1400b897f  push    r15
0x1400b8981  lea     rbp, [rsp-228h]
0x1400b8989  sub     rsp, 328h
0x1400b8990  mov     rax, cs:__security_cookie
0x1400b8997  xor     rax, rsp
0x1400b899a  mov     [rbp+260h+var_50], rax
0x1400b89a1  mov     r14, rcx
0x1400b89a4  xor     r13d, r13d
0x1400b89a7  mov     [rbp+260h+var_70], r13d
0x1400b89ae  xorps   xmm0, xmm0
0x1400b89b1  movdqa  [rbp+260h+var_60], xmm0
0x1400b89b9  mov     r15, cs:qword_1403CC940
0x1400b89c0  cmp     r15, 3
0x1400b89c4  jnz     short loc_1400B89E3
0x1400b89c6  mov     rcx, [rbp+268h]; this
0x1400b89cd  lea     r9d, [r13+32h]; char *
0x1400b89d1  lea     r8, aOnecoreVmWorke_141; "onecore\\vm\\worker\\wpcore\\workertask"...
0x1400b89d8  mov     edx, 38Fh; void *
0x1400b89dd  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x1400b89e3  cmp     byte ptr cs:qword_1403CCB4C+6, r13b
0x1400b89ea  jz      short loc_1400B8A0B
0x1400b89ec  mov     rcx, [rbp+268h]; this
0x1400b89f3  mov     r9d, 32h ; '2'; char *
0x1400b89f9  lea     r8, aOnecoreVmWorke_141; "onecore\\vm\\worker\\wpcore\\workertask"...
0x1400b8a00  mov     edx, 397h; void *
0x1400b8a05  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x1400b8a0b  mov     rax, [rcx+10h]
0x1400b8a0f  mov     rcx, [rax+430h]
0x1400b8a16  mov     rax, [rcx]
0x1400b8a19  lea     rdx, [rbp+260h+var_70]
0x1400b8a20  mov     rax, [rax+70h]
0x1400b8a24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400b8a29  cmp     [rbp+260h+var_70], r13d
0x1400b8a30  setnz   sil
0x1400b8a34  lea     rdx, [rbp+260h+var_1C0]
0x1400b8a3b  mov     rcx, r14
0x1400b8a3e  call    ?GetCurrentActivity@?$WorkerAsyncTask@VSnapshottingTask@VmWorkerTrace@@@@IEAA?AVSnapshottingTask@VmWorkerTrace@@XZ; WorkerAsyncTask<VmWorkerTrace::SnapshottingTask>::GetCurrentActivity(void)
0x1400b8a43  mov     rbx, rax
0x1400b8a46  mov     r12d, 160h
0x1400b8a4c  mov     ecx, r12d; Size
0x1400b8a4f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1400b8a54  mov     rdi, rax
0x1400b8a57  mov     [rbp+260h+var_68], rax
0x1400b8a5e  mov     r8d, r12d; Size
0x1400b8a61  xor     edx, edx; Val
0x1400b8a63  mov     rcx, rax; void *
0x1400b8a66  call    memset_0
0x1400b8a6b  mov     rdx, rbx
0x1400b8a6e  lea     rcx, [rsp+360h+var_310]
0x1400b8a73  call    ??0SnapshottingTask@VmWorkerTrace@@QEAA@$$QEAV01@@Z; VmWorkerTrace::SnapshottingTask::SnapshottingTask(VmWorkerTrace::SnapshottingTask &&)
0x1400b8a78  mov     r9b, sil
0x1400b8a7b  mov     r8, rax
0x1400b8a7e  mov     rdx, [r14+10h]
0x1400b8a82  mov     rcx, rdi
0x1400b8a85  call    ??0CaptureStateUtility@@QEAA@PEAVVirtualMachine@@VSnapshottingTask@VmWorkerTrace@@_N@Z; CaptureStateUtility::CaptureStateUtility(VirtualMachine *,VmWorkerTrace::SnapshottingTask,bool)
0x1400b8a8a  mov     rbx, rax
0x1400b8a8d  mov     [rbp+260h+var_68], rax
0x1400b8a94  lea     rcx, [rbp+260h+var_1C0]; this
0x1400b8a9b  call    ??1SnapshottingTask@VmWorkerTrace@@QEAA@XZ; VmWorkerTrace::SnapshottingTask::~SnapshottingTask(void)
0x1400b8aa0  mov     rdx, [r14+428h]; struct VmRepository *
0x1400b8aa7  mov     rcx, rbx; this
0x1400b8aaa  call    ?SuspendAndSaveEpf@CaptureStateUtility@@QEAAXPEAVVmRepository@@@Z; CaptureStateUtility::SuspendAndSaveEpf(VmRepository *)
0x1400b8aaf  mov     rdx, [r14+428h]; struct VmRepository *
0x1400b8ab6  mov     rcx, rbx; this
0x1400b8ab9  call    ?SuspendAndSaveSchedulerAssist@CaptureStateUtility@@QEAAXPEAVVmRepository@@@Z; CaptureStateUtility::SuspendAndSaveSchedulerAssist(VmRepository *)
0x1400b8abe  mov     rax, [r14+10h]
0x1400b8ac2  mov     rcx, [rax+588h]
0x1400b8ac9  mov     esi, [rcx+178h]
0x1400b8acf  cmp     [rbp+260h+var_70], r13d
0x1400b8ad6  jz      short loc_1400B8B23
0x1400b8ad8  cmp     [rbx+158h], r13b
0x1400b8adf  jz      short loc_1400B8B2B
0x1400b8ae1  mov     rax, [rbx]
0x1400b8ae4  mov     rcx, [rax+430h]
0x1400b8aeb  mov     rax, [rcx]
0x1400b8aee  mov     rax, [rax+0A8h]
0x1400b8af5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400b8afa  mov     rcx, [rbp+268h]; this
0x1400b8b01  test    eax, eax
0x1400b8b03  jns     short loc_1400B8B1A
0x1400b8b05  mov     r9d, eax; char *
0x1400b8b08  lea     r8, aOnecoreVmWorke_121; "onecore\\vm\\worker\\wpcore\\capturesta"...
0x1400b8b0f  mov     edx, 0B3h; void *
0x1400b8b14  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1400b8b1a  mov     byte ptr [rbx+15Bh], 1
0x1400b8b21  jmp     short loc_1400B8B2B
0x1400b8b23  mov     rcx, rbx; this
0x1400b8b26  call    ?InitializeBalloonedPagesBitmap@CaptureStateUtility@@QEAAXXZ; CaptureStateUtility::InitializeBalloonedPagesBitmap(void)
0x1400b8b2b  mov     rcx, [r14+10h]; this
0x1400b8b2f  cmp     [rcx+0B98h], r13b
0x1400b8b36  jz      short loc_1400B8B64
0x1400b8b38  mov     rdx, [r14+428h]; struct VmRepository *
0x1400b8b3f  call    ?SaveIgvmSaveState@VirtualMachine@@UEAAJPEAVVmRepository@@@Z; VirtualMachine::SaveIgvmSaveState(VmRepository *)
0x1400b8b44  mov     rcx, [rbp+268h]; this
0x1400b8b4b  test    eax, eax
0x1400b8b4d  jns     short loc_1400B8B64
0x1400b8b4f  mov     r9d, eax; char *
0x1400b8b52  lea     r8, aOnecoreVmWorke_141; "onecore\\vm\\worker\\wpcore\\workertask"...
0x1400b8b59  mov     edx, 3B9h; void *
0x1400b8b5e  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1400b8b64  mov     [rsp+360h+var_338], r13; unsigned __int64
0x1400b8b69  mov     rax, cs:qword_1403CC9E0
0x1400b8b70  mov     [rsp+360h+var_340], rax; int
0x1400b8b75  mov     r9b, 1
0x1400b8b78  xor     r8d, r8d
0x1400b8b7b  mov     rdx, [r14+428h]
0x1400b8b82  lea     r12, ?m_Instance@MemoryManager@@0V1@A; MemoryManager MemoryManager::m_Instance
0x1400b8b89  mov     rcx, r12
0x1400b8b8c  call    ?SaveRamInformation@MemoryManager@@UEAAXPEAVVmRepository@@W4VmFastSaveType@@_NPEAVGmoBitmap@@PEAT_VM_PERSIST_FLAGS@@@Z; MemoryManager::SaveRamInformation(VmRepository *,VmFastSaveType,bool,GmoBitmap *,_VM_PERSIST_FLAGS *)
0x1400b8b91  mov     rax, [r14+10h]
0x1400b8b95  mov     rcx, [rax+400h]
0x1400b8b9c  mov     rax, [rcx]
0x1400b8b9f  mov     rdx, [r14+428h]
0x1400b8ba6  mov     rax, [rax+100h]
0x1400b8bad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400b8bb2  mov     rdx, [r14+428h]; struct VmRepository *
0x1400b8bb9  mov     rcx, r12; this
0x1400b8bbc  call    ?SaveVtlProtections@MemoryManager@@UEAAXPEAVVmRepository@@@Z; MemoryManager::SaveVtlProtections(VmRepository *)
0x1400b8bc1  mov     rcx, r12; this
0x1400b8bc4  call    ?GetRamSizeInPages@MemoryManager@@UEBA_KXZ; MemoryManager::GetRamSizeInPages(void)
0x1400b8bc9  lea     rdi, [r14+2A0h]
0x1400b8bd0  mov     [rsp+360h+var_320], esi; unsigned int
0x1400b8bd4  mov     [rsp+360h+var_328], r13; unsigned __int64
0x1400b8bd9  mov     [rsp+360h+var_330], rax; unsigned __int64
0x1400b8bde  mov     r9, [r14+18h]; struct IVmSimpleTask *
0x1400b8be2  mov     r8, [r14+10h]; struct VirtualMachine *
0x1400b8be6  mov     rdx, [r14+428h]; void *
0x1400b8bed  mov     rcx, rdi; this
0x1400b8bf0  call    ?Initialize@GmoRamOperationSnapshot@@QEAAJPEAXPEAVVirtualMachine@@PEAUIVmSimpleTask@@_K333I@Z; GmoRamOperationSnapshot::Initialize(void *,VirtualMachine *,IVmSimpleTask *,unsigned __int64,unsigned __int64,unsigned __int64,unsigned __int64,uint)
0x1400b8bf5  mov     rcx, [rbp+268h]; this
0x1400b8bfc  test    eax, eax
0x1400b8bfe  jns     short loc_1400B8C15
0x1400b8c00  mov     r9d, eax; char *
0x1400b8c03  lea     r8, aOnecoreVmWorke_141; "onecore\\vm\\worker\\wpcore\\workertask"...
0x1400b8c0a  mov     edx, 3D8h; void *
0x1400b8c0f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1400b8c15  cmp     [rbp+260h+var_70], r13d
0x1400b8c1c  jz      short loc_1400B8C9C
0x1400b8c1e  cmp     [rbx+158h], r13b
0x1400b8c25  jz      short loc_1400B8C9C
0x1400b8c27  mov     rcx, [rbp+268h]; this
0x1400b8c2e  cmp     [rbx+15Bh], r13b
0x1400b8c35  jnz     short loc_1400B8C49
0x1400b8c37  lea     r8, aOnecoreVmWorke_121; "onecore\\vm\\worker\\wpcore\\capturesta"...
0x1400b8c3e  mov     edx, 0C0h; void *
0x1400b8c43  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x1400b8c49  mov     rax, [rbx]
0x1400b8c4c  mov     rcx, [rax+430h]
0x1400b8c53  mov     rax, [rcx]
0x1400b8c56  mov     r9d, 2
0x1400b8c5c  mov     r8d, 100h
0x1400b8c62  mov     edx, [r14+368h]
0x1400b8c69  mov     rax, [rax+0B8h]
0x1400b8c70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400b8c75  mov     rcx, [rbp+268h]; this
0x1400b8c7c  test    eax, eax
0x1400b8c7e  jns     short loc_1400B8C95
0x1400b8c80  mov     r9d, eax; char *
0x1400b8c83  lea     r8, aOnecoreVmWorke_121; "onecore\\vm\\worker\\wpcore\\capturesta"...
0x1400b8c8a  mov     edx, 0C4h; void *
0x1400b8c8f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1400b8c95  mov     byte ptr [rbx+15Ch], 1
0x1400b8c9c  mov     rcx, rdi; this
0x1400b8c9f  call    ?WorkThreadsStart@GmoRamOperation@@QEAAJXZ; GmoRamOperation::WorkThreadsStart(void)
0x1400b8ca4  mov     rcx, [rbp+268h]; this
0x1400b8cab  test    eax, eax
0x1400b8cad  jns     short loc_1400B8CC4
0x1400b8caf  mov     r9d, eax; char *
0x1400b8cb2  lea     r8, aOnecoreVmWorke_141; "onecore\\vm\\worker\\wpcore\\workertask"...
0x1400b8cb9  mov     edx, 3E2h; void *
0x1400b8cbe  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1400b8cc4  cmp     r15, 2
0x1400b8cc8  jnz     loc_1400B8D55
0x1400b8cce  mov     rax, [r14+10h]
0x1400b8cd2  mov     rcx, [rax+400h]
0x1400b8cd9  add     rcx, 18h
0x1400b8cdd  mov     rax, [rcx]
0x1400b8ce0  mov     rax, [rax]
0x1400b8ce3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400b8ce8  lea     r8, [rbp+260h+var_60]
0x1400b8cef  lea     edx, [r15-1]
0x1400b8cf3  mov     rcx, rax
0x1400b8cf6  call    cs:__imp_VidCloneTemplateCreate
0x1400b8cfd  nop     dword ptr [rax+rax+00h]
0x1400b8d02  test    eax, eax
0x1400b8d04  jnz     loc_1400B8DBA
0x1400b8d0a  call    cs:__imp_GetLastError
0x1400b8d11  nop     dword ptr [rax+rax+00h]
0x1400b8d16  test    eax, 1FFF0000h
0x1400b8d1b  jnz     short loc_1400B8D2B
0x1400b8d1d  test    eax, eax
0x1400b8d1f  jle     short loc_1400B8D39
0x1400b8d21  movzx   eax, ax
0x1400b8d24  or      eax, 80070000h
0x1400b8d29  jmp     short loc_1400B8D39
0x1400b8d2b  test    eax, eax
0x1400b8d2d  jle     short loc_1400B8D39
0x1400b8d2f  and     eax, 0FFFFFFFh
0x1400b8d34  or      eax, 80000000h
0x1400b8d39  mov     rcx, [rbp+268h]; this
0x1400b8d40  mov     r9d, eax; char *
0x1400b8d43  lea     r8, aOnecoreVmWorke_141; "onecore\\vm\\worker\\wpcore\\workertask"...
0x1400b8d4a  mov     edx, 3EEh; void *
0x1400b8d4f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1400b8d55  test    rdi, rdi
0x1400b8d58  lea     rdx, [r14+398h]
0x1400b8d5f  jnz     short loc_1400B8D64
0x1400b8d61  mov     rdx, r13; struct MemoryNotificationListener *
0x1400b8d64  mov     rbx, [rbp+268h]
0x1400b8d6b  mov     rcx, r12; this
0x1400b8d6e  call    ?SetRamNotificationListener@MemoryManager@@UEAAHPEAVMemoryNotificationListener@@@Z; MemoryManager::SetRamNotificationListener(MemoryNotificationListener *)
0x1400b8d73  test    eax, eax
0x1400b8d75  jnz     short loc_1400B8D92
0x1400b8d77  mov     r9d, 80004005h; char *
0x1400b8d7d  lea     r8, aOnecoreVmWorke_141; "onecore\\vm\\worker\\wpcore\\workertask"...
0x1400b8d84  mov     edx, 3FAh; void *
0x1400b8d89  mov     rcx, rbx; this
0x1400b8d8c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1400b8d92  mov     rcx, rdi; this
0x1400b8d95  call    ?SetMemoryIntercepts@GmoRamOperationSnapshot@@QEAAJXZ; GmoRamOperationSnapshot::SetMemoryIntercepts(void)
0x1400b8d9a  mov     rcx, [rbp+268h]; this
0x1400b8da1  test    eax, eax
0x1400b8da3  jns     short loc_1400B8DBA
0x1400b8da5  mov     r9d, eax; char *
0x1400b8da8  lea     r8, aOnecoreVmWorke_141; "onecore\\vm\\worker\\wpcore\\workertask"...
0x1400b8daf  mov     edx, 3FFh; void *
0x1400b8db4  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1400b8dba  lea     rcx, [r14+3B0h]
0x1400b8dc1  lea     rdx, [rbp+260h+var_68]
0x1400b8dc8  call    ??$?4U?$default_delete@VCaptureStateUtility@@@std@@$0A@@?$unique_ptr@VCaptureStateUtility@@U?$default_delete@VCaptureStateUtility@@@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::unique_ptr<CaptureStateUtility>::operator=<std::default_delete<CaptureStateUtility>,0>(std::unique_ptr<CaptureStateUtility> &&)
0x1400b8dcd  nop
0x1400b8dce  lea     rcx, [rbp+260h+var_68]
0x1400b8dd5  call    ??1?$unique_ptr@VCaptureStateUtility@@U?$default_delete@VCaptureStateUtility@@@std@@@std@@QEAA@XZ; std::unique_ptr<CaptureStateUtility>::~unique_ptr<CaptureStateUtility>(void)
0x1400b8dda  mov     rcx, [rbp+260h+var_50]
0x1400b8de1  xor     rcx, rsp; StackCookie
0x1400b8de4  call    __security_check_cookie
0x1400b8de9  add     rsp, 328h
0x1400b8df0  pop     r15
0x1400b8df2  pop     r14
0x1400b8df4  pop     r13
0x1400b8df6  pop     r12
0x1400b8df8  pop     rdi
0x1400b8df9  pop     rsi
0x1400b8dfa  pop     rbx
0x1400b8dfb  pop     rbp
0x1400b8dfc  retn
```
