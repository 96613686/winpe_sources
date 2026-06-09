# WorkerTaskStarting::RunCleanStartSteps(void)

- ea: `0x1400c3fa8`
- end: `0x1400c4939`
- name: `?RunCleanStartSteps@WorkerTaskStarting@@AEAAJXZ`
- size: `2449`
- prototype: `__int64 __fastcall(WorkerTaskStarting *__hidden this)`
- caller_count: `2`
- callee_count: `48`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x14016cb2c`
- `0x14016cc50`

## callees

- `0x1400364a0`
- `0x14003cc30`
- `0x140056b38`
- `0x14005c4b8`
- `0x140064f4c`
- `0x140069004`
- `0x1400691b4`
- `0x140069430`
- `0x140075648`
- `0x140083990`
- `0x14008d4e4`
- `0x14008d530`
- `0x14008dbe0`
- `0x1400bc420`
- `0x1400bda50`
- `0x1400c29fc`
- `0x1400c3fa8`
- `0x1400c4940`
- `0x1400c49c8`
- `0x1400c4a80`
- `0x1400c4b40`
- `0x1400c4d90`
- `0x1400c4dc0`
- `0x1400c4e80`
- `0x1400c4eac`
- `0x1400c4fe8`
- `0x1400c5040`
- `0x140102580`
- `0x1401090a8`
- `0x14011ea40`
- `0x14011f6fc`
- `0x14012d20c`
- `0x140138ce8`
- `0x14014f4a8`
- `0x140158c5c`
- `0x14015ea30`
- `0x14016b438`
- `0x14016b464`
- `0x14016b49c`
- `0x14016b54c`
- `0x14016b578`
- `0x14016c970`
- `0x14016d214`
- `0x14016d514`
- `0x14016d754`
- `0x14016d84c`
- `0x14016d938`
- `0x1402cb010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400c4202`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400c4562`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400c4202`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400c4562`
- `vid!VidVsmSetPartitionConfig` at `0x1400c42d2`
- `vid!VidVsmSetPartitionConfig` at `0x1400c42d2`
- `vid!VidTrimPartitionMemory` at `0x1400c46e5`
- `vid!VidTrimPartitionMemory` at `0x1400c46e5`
- `vid!VidChangePartitionLifeState` at `0x1400c41f2`
- `vid!VidChangePartitionLifeState` at `0x1400c4552`
- `vid!VidChangePartitionLifeState` at `0x1400c41f2`
- `vid!VidChangePartitionLifeState` at `0x1400c4552`

## string_xrefs

- `0x1400c4002`: `onecore\vm\worker\wpcore\workertaskstarting.cpp`
- `0x1400c40cd`: `onecore\vm\worker\wpcore\workertaskstarting.cpp`
- `0x1400c410f`: `onecore\vm\worker\wpcore\workertaskstarting.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall WorkerTaskStarting::RunCleanStartSteps(WorkerTaskStarting *this)
{
  WorkerAsyncTaskBase *v1; // r15
  VirtualMachine **v2; // r14
  __int64 v3; // rcx
  unsigned int *v4; // r13
  const struct _GUID *v5; // rdi
  int v6; // eax
  __int64 ConfigRepository; // rax
  char v8; // di
  __int64 v9; // rsi
  int v10; // edi
  __int64 v11; // rax
  unsigned int v12; // edi
  __int64 v13; // r8
  unsigned int v14; // esi
  signed int LastError; // eax
  __int64 v16; // rax
  const char *v17; // r9
  __int64 IgvmFileIntoGuest; // rax
  wil *v19; // rcx
  __int64 v20; // rcx
  int v21; // eax
  VirtualMachine *v22; // rdi
  __int64 v23; // rax
  signed int v24; // eax
  int v25; // eax
  int v26; // eax
  int started; // eax
  __int64 v28; // rax
  __int64 v29; // rdx
  VirtualMachine *v30; // rdi
  __int64 v31; // rdx
  __int64 v32; // rcx
  void (*v33)(void); // rax
  __int64 v34; // rdx
  int v36; // [rsp+20h] [rbp-3D8h]
  int v37; // [rsp+20h] [rbp-3D8h]
  int v38; // [rsp+24h] [rbp-3D4h] BYREF
  _QWORD v39[2]; // [rsp+28h] [rbp-3D0h] BYREF
  _BYTE v40[8]; // [rsp+38h] [rbp-3C0h] BYREF
  WorkerAsyncTaskBase *v41; // [rsp+40h] [rbp-3B8h]
  _BYTE v42[336]; // [rsp+50h] [rbp-3A8h] BYREF
  unsigned int v43; // [rsp+1A0h] [rbp-258h] BYREF
  int v44; // [rsp+1A4h] [rbp-254h] BYREF
  __int128 v45; // [rsp+1A8h] [rbp-250h] BYREF
  __int128 v46; // [rsp+1B8h] [rbp-240h]
  __int64 v47; // [rsp+1C8h] [rbp-230h]
  __int128 v48; // [rsp+1D0h] [rbp-228h] BYREF
  __int64 v49; // [rsp+1E0h] [rbp-218h]
  _QWORD v50[3]; // [rsp+1E8h] [rbp-210h] BYREF
  _QWORD v51[42]; // [rsp+200h] [rbp-1F8h] BYREF
  _BYTE v52[8]; // [rsp+350h] [rbp-A8h] BYREF
  __int64 v53; // [rsp+358h] [rbp-A0h]
  __int64 v54; // [rsp+360h] [rbp-98h]
  wil::details::in1diag3 *retaddr; // [rsp+3F8h] [rbp+0h]

  v1 = this;
  v41 = this;
  v2 = (VirtualMachine **)((char *)this + 16);
  v50[0] = (char *)this + 16;
  v3 = *((_QWORD *)this + 2);
  if ( !*(_QWORD *)(*(_QWORD *)(v3 + 1416) + 88LL) )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x1AF,
      (unsigned int)"onecore\\vm\\worker\\wpcore\\workertaskstarting.cpp",
      (const char *)retaddr);
  v38 = 0;
  v48 = 0;
  v49 = 0;
  v4 = (unsigned int *)((char *)v1 + 400);
  v39[0] = (char *)v1 + 400;
  if ( *((_DWORD *)v1 + 100) != 2 )
    goto LABEL_8;
  LODWORD(v5) = VirtualMotherboard::StartReservingResources(*(_QWORD *)(v3 + 984), 0, 0);
  if ( (int)v5 >= 0 )
  {
    memset_0(v51, 0, sizeof(v51));
    WorkerAsyncTask<VmWorkerTrace::StartingTask>::GetCurrentActivity(v1, v42);
    VmPerf::StartRelatedActivity_VmWorkerTrace::ConstructGuestRam_VmWorkerTrace::StartingTask__GUID_const___((VmWorkerTrace::ConstructGuestRam *)v51);
    VmWorkerTrace::StartingTask::~StartingTask((VmWorkerTrace::StartingTask *)v42);
    v6 = VirtualMachine::ConstructGuestRam(
           *v2,
           0,
           *((struct IVmSimpleTask **)v1 + 3),
           (const struct _GUID *)(v51[34] + 8LL));
    LODWORD(v5) = v6;
    if ( v6 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x1C5,
        (unsigned int)"onecore\\vm\\worker\\wpcore\\workertaskstarting.cpp",
        (const char *)(unsigned int)v6,
        v36);
    wil::ActivityBase<VmWorkerTrace,0,16,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v51, (unsigned int)v5);
    VmWorkerTrace::ConstructGuestRam::~ConstructGuestRam((VmWorkerTrace::ConstructGuestRam *)v51);
    if ( (int)v5 >= 0 )
    {
LABEL_8:
      v37 = 0;
      v44 = 0;
      (*(void (__fastcall **)(_QWORD, int *))(**((_QWORD **)*v2 + 134) + 88LL))(*((_QWORD *)*v2 + 134), &v44);
      if ( v44 )
      {
        Config::VmWorkerProcess::IsolationSettings::IsolationSettings((Config::VmWorkerProcess::IsolationSettings *)v52);
        ConfigRepository = VirtualMachine::GetConfigRepository(*v2, v40);
        v8 = *(_BYTE *)Marshal::FromRepository<Vml::VmReferencePtr<VmRepository,Vml::VmUserReferenceTraits> &,Config::VmWorkerProcess::IsolationSettings,>(
                         &v45,
                         ConfigRepository,
                         v52);
        std::vector<std::pair<std::wstring,enum Marshal::UnmarshalError>>::_Tidy((char *)&v45 + 8);
        Vml::VmReferencePtr<VmRepository,Vml::VmUserReferenceTraits>::~VmReferencePtr<VmRepository,Vml::VmUserReferenceTraits>(v40);
        if ( !v8 )
        {
          LODWORD(v5) = -2147024809;
          Config::VmWorkerProcess::IsolationSettings::~IsolationSettings((Config::VmWorkerProcess::IsolationSettings *)v52);
          goto LABEL_84;
        }
        v9 = v53;
        v10 = v54;
        v11 = (**(__int64 (__fastcall ***)(__int64))(*((_QWORD *)*v2 + 128) + 24LL))(*((_QWORD *)*v2 + 128) + 24LL);
        v12 = v10 - v9;
        v13 = v9;
        v14 = 1;
        if ( !(unsigned int)VidChangePartitionLifeState(v11, 1, v13, v12) )
        {
          LastError = GetLastError();
          LODWORD(v5) = LastError;
          if ( LastError > 0 )
            LODWORD(v5) = (unsigned __int16)LastError | 0x80070000;
          if ( (unsigned int)VmlIsDebugTraceEnabled(16416) )
            VmlDebugTraceWithError(16416, &off_1402E3058, (unsigned int)v5);
          Config::VmWorkerProcess::IsolationSettings::~IsolationSettings((Config::VmWorkerProcess::IsolationSettings *)v52);
          goto LABEL_45;
        }
        Config::VmWorkerProcess::IsolationSettings::~IsolationSettings((Config::VmWorkerProcess::IsolationSettings *)v52);
      }
      else
      {
        v14 = 1;
      }
      if ( *((_BYTE *)*v2 + 2664) )
      {
        v16 = (**(__int64 (__fastcall ***)(__int64))(*((_QWORD *)*v2 + 128) + 24LL))(*((_QWORD *)*v2 + 128) + 24LL);
        v45 = 0;
        v46 = 0;
        v47 = 0;
        LODWORD(v45) = 5;
        BYTE8(v46) = 0;
        HIDWORD(v46) = 15;
        if ( !(unsigned int)VidVsmSetPartitionConfig(v16, 40, &v45) )
          wil::details::in1diag3::Throw_GetLastError(
            retaddr,
            (void *)0x57,
            (unsigned int)"onecore\\vm\\worker\\wpcore\\workerhclloader.cpp",
            v17);
      }
      if ( *((_BYTE *)*v2 + 2968) )
      {
        try
        {
          IgvmFileIntoGuest = VirtualMachine::LoadIgvmFileIntoGuest(*v2);
          std::vector<unsigned char>::operator=(&v48, IgvmFileIntoGuest);
          std::vector<_VID_VSM_MBP_PERMISSIONS>::_Tidy(&v45);
        }
        catch ( ... )
        {
          LODWORD(v5) = wil::ResultFromCaughtException(v19);
          v25 = 0;
          v1 = v41;
          v2 = (VirtualMachine **)v50[0];
          v4 = (unsigned int *)v39[0];
          goto LABEL_46;
        }
      }
      LODWORD(v5) = WorkerTaskStarting::PowerOnVirtualMotherboard(v1, 0, 0);
      if ( (int)v5 >= 0 )
      {
        LODWORD(v5) = VirtualMachine::RegisterGuestCrashManager(*v2);
        if ( (int)v5 >= 0 )
        {
          if ( *v4 > 0x33
            || (v20 = 0x8000100008004LL, !_bittest64(&v20, (int)*v4))
            || (LODWORD(v5) = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)*v2 + 133) + 48LL))(*((_QWORD *)*v2 + 133)),
                (int)v5 >= 0) )
          {
            WorkerAsyncTaskBase::UpdateStatusProgress(v1, 0x32u, &v38);
            if ( v38 )
            {
              LODWORD(v5) = -2147023673;
            }
            else
            {
              if ( *v4 != 32 )
                (*(void (__fastcall **)(_QWORD, __int64))(**((_QWORD **)*v2 + 130) + 656LL))(*((_QWORD *)*v2 + 130), 1);
              memset_0(v51, 0, sizeof(v51));
              v5 = (const struct _GUID *)*v2;
              wil::ActivityBase<VmWorkerTrace,2,65536,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<VmWorkerTrace,2,65536,4,0,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v51);
              v51[0] = &VmWorkerTrace::BootStateImporterFlush::`vftable';
              VmWorkerTrace::BootStateImporterFlush::StartActivity(
                (VmWorkerTrace::BootStateImporterFlush *)v51,
                v5 + 71);
              v39[0] = v1;
              v21 = wil::ResultFromException__lambda_1e435c07f28aa931d7536c0492f26ff8___(v39);
              LODWORD(v5) = v21;
              if ( v21 < 0 )
                wil::details::in1diag3::_Log_Hr(
                  retaddr,
                  (void *)0x249,
                  (unsigned int)"onecore\\vm\\worker\\wpcore\\workertaskstarting.cpp",
                  (const char *)(unsigned int)v21,
                  0);
              wil::ActivityBase<VmWorkerTrace,2,65536,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(
                v51,
                (unsigned int)v5);
              if ( (int)v5 >= 0 )
              {
                v37 = 1;
                VmWorkerTrace::BootStateImporterFlush::~BootStateImporterFlush((VmWorkerTrace::BootStateImporterFlush *)v51);
                if ( v44 )
                {
                  memset_0(v51, 0, sizeof(v51));
                  v22 = *v2;
                  wil::ActivityBase<VmWorkerTrace,2,512,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<VmWorkerTrace,2,512,4,0,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v51);
                  v51[0] = &VmWorkerTrace::IsolatedVmBootImport::`vftable';
                  VmWorkerTrace::IsolatedVmBootImport::StartActivity(
                    (VmWorkerTrace::IsolatedVmBootImport *)v51,
                    (const struct _GUID *)v22 + 71);
                  v23 = (**(__int64 (__fastcall ***)(__int64))(*((_QWORD *)*v2 + 128) + 24LL))(*((_QWORD *)*v2 + 128) + 24LL);
                  if ( !(unsigned int)VidChangePartitionLifeState(v23, 2, v48, (unsigned int)(DWORD2(v48) - v48)) )
                  {
                    v24 = GetLastError();
                    LODWORD(v5) = v24;
                    if ( v24 > 0 )
                      LODWORD(v5) = (unsigned __int16)v24 | 0x80070000;
                    if ( (unsigned int)VmlIsDebugTraceEnabled(16416) )
                      VmlDebugTraceWithError(16416, &off_1402E3028, (unsigned int)v5);
                    VmWorkerTrace::IsolatedVmBootImport::~IsolatedVmBootImport((VmWorkerTrace::IsolatedVmBootImport *)v51);
LABEL_45:
                    v25 = v37;
LABEL_46:
                    if ( (int)v5 < 0 )
                      goto LABEL_76;
                    goto LABEL_79;
                  }
                  wil::ActivityBase<VmWorkerTrace,2,512,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v51);
                  VmWorkerTrace::IsolatedVmBootImport::~IsolatedVmBootImport((VmWorkerTrace::IsolatedVmBootImport *)v51);
                }
                switch ( *v4 )
                {
                  case 2u:
                    v43 = 1;
                    break;
                  case 0xFu:
                    v43 = 6;
                    break;
                  case 0x20u:
                    v43 = 17;
                    break;
                  default:
                    v26 = 22;
                    if ( *v4 != 51 )
                      v26 = 0;
                    v43 = v26;
                    break;
                }
                memset_0(v51, 0, sizeof(v51));
                v5 = (const struct _GUID *)*v2;
                wil::ActivityBase<VmWorkerTrace,2,64,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<VmWorkerTrace,2,64,4,0,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v51);
                v51[0] = &VmWorkerTrace::StartVm::`vftable';
                VmWorkerTrace::StartVm::StartActivity((VmWorkerTrace::StartVm *)v51, v5 + 71);
                started = VirtualMachine::StartVm(*v2, 0, v43);
                LODWORD(v5) = started;
                if ( started < 0 )
                  wil::details::in1diag3::_Log_Hr(
                    retaddr,
                    (void *)0x285,
                    (unsigned int)"onecore\\vm\\worker\\wpcore\\workertaskstarting.cpp",
                    (const char *)(unsigned int)started,
                    1);
                wil::ActivityBase<VmWorkerTrace,2,64,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(
                  v51,
                  (unsigned int)v5);
                VmWorkerTrace::StartVm::~StartVm((VmWorkerTrace::StartVm *)v51);
                if ( (int)v5 >= 0 )
                {
                  v28 = (**(__int64 (__fastcall ***)(__int64))(*((_QWORD *)*v2 + 128) + 24LL))(*((_QWORD *)*v2 + 128) + 24LL);
                  VidTrimPartitionMemory(v28);
                  WorkerAsyncTaskBase::UpdateStatusProgress(v1, *((_BYTE *)*v2 + 2664) != 0 ? 95 : 99, &v38);
                  if ( v38 )
                  {
                    LODWORD(v5) = -2147023673;
                  }
                  else
                  {
                    v29 = *((_QWORD *)v1 + 51);
                    *((_QWORD *)v1 + 51) = 0;
                    if ( v29 )
                      std::default_delete<ProcessPriorityBooster>::operator()();
                    v30 = *v2;
                    if ( !*((_BYTE *)*v2 + 2665) )
                      goto LABEL_78;
                    v43 = 60;
                    memset_0(v51, 0, sizeof(v51));
                    wil::ActivityBase<VmWorkerTrace,2,64,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<VmWorkerTrace,2,64,4,0,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v51);
                    v51[0] = &VmWorkerTrace::StartVtl0::`vftable';
                    VmWorkerTrace::StartVtl0::StartActivity(
                      (VmWorkerTrace::StartVtl0 *)v51,
                      (const struct _GUID *)v30 + 71);
                    v39[0] = &v43;
                    v39[1] = v1;
                    *(_QWORD *)&v45 = retaddr;
                    *((_QWORD *)&v45 + 1) = "onecore\\vm\\worker\\wpcore\\workertaskstarting.cpp";
                    *(_QWORD *)&v46 = 0;
                    WORD4(v46) = 683;
                    v50[0] = &off_1402D36B0;
                    v50[1] = v39;
                    v5 = (const struct _GUID *)(unsigned int)wil::details::ResultFromException(&v45, v31, v50);
                    wil::ActivityBase<VmWorkerTrace,2,64,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v51, v5);
                    VmWorkerTrace::StartVtl0::~StartVtl0((VmWorkerTrace::StartVtl0 *)v51);
                    if ( (int)v5 >= 0 )
                    {
LABEL_78:
                      LODWORD(v5) = 0;
LABEL_79:
                      if ( *v4 <= 0x33 && (v32 = 0x8000100008000LL, _bittest64(&v32, (int)*v4)) )
                        v33 = *(void (**)(void))(**((_QWORD **)*v2 + 133) + 72LL);
                      else
                        v33 = *(void (**)(void))(**((_QWORD **)*v2 + 133) + 56LL);
                      v33();
                      WorkerAsyncTaskBase::UpdateStatusProgress(v1, 0x64u, &v38);
                      goto LABEL_84;
                    }
                  }
                  if ( *v4 != 2 )
                  {
                    if ( *v4 == 15 )
                    {
                      v14 = 7;
                    }
                    else if ( *v4 == 32 )
                    {
                      v14 = 24;
                    }
                    else
                    {
                      v14 = 30;
                      if ( *v4 != 51 )
                        v14 = 0;
                    }
                  }
                  VirtualMachine::StopVm(*v2, 0, v14);
                  v25 = v37;
LABEL_76:
                  if ( !v25 )
                    goto LABEL_84;
                }
              }
              else
              {
                VmWorkerTrace::BootStateImporterFlush::~BootStateImporterFlush((VmWorkerTrace::BootStateImporterFlush *)v51);
              }
            }
          }
        }
        else if ( (unsigned int)VmlIsDebugTraceEnabled(16416) )
        {
          VmlDebugTraceWithError(16416, &off_1402E3040, (unsigned int)v5);
        }
        VirtualMotherboard::PowerOff(*((_QWORD *)*v2 + 123), 0);
      }
    }
  }
LABEL_84:
  v34 = *((_QWORD *)v1 + 51);
  *((_QWORD *)v1 + 51) = 0;
  if ( v34 )
    std::default_delete<ProcessPriorityBooster>::operator()();
  std::vector<_VID_VSM_MBP_PERMISSIONS>::_Tidy(&v48);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1400c3fa8  mov     [rsp+arg_8], rbx
0x1400c3fad  mov     [rsp+arg_10], rsi
0x1400c3fb2  push    rdi
0x1400c3fb3  push    r12
0x1400c3fb5  push    r13
0x1400c3fb7  push    r14
0x1400c3fb9  push    r15
0x1400c3fbb  sub     rsp, 3D0h
0x1400c3fc2  mov     rax, cs:__security_cookie
0x1400c3fc9  xor     rax, rsp
0x1400c3fcc  mov     [rsp+3F8h+var_38], rax
0x1400c3fd4  mov     r15, rcx
0x1400c3fd7  mov     [rsp+3F8h+var_3B8], rcx
0x1400c3fdc  lea     r14, [rcx+10h]
0x1400c3fe0  mov     [rsp+3F8h+var_210], r14
0x1400c3fe8  mov     rcx, [r14]
0x1400c3feb  mov     r9, [rsp+3F8h]; char *
0x1400c3ff3  mov     rax, [rcx+588h]
0x1400c3ffa  xor     ebx, ebx
0x1400c3ffc  cmp     [rax+58h], rbx
0x1400c4000  jnz     short loc_1400C4017
0x1400c4002  lea     r8, aOnecoreVmWorke_45; "onecore\\vm\\worker\\wpcore\\workertask"...
0x1400c4009  mov     edx, 1AFh; void *
0x1400c400e  mov     rcx, r9; this
0x1400c4011  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x1400c4017  mov     [rsp+3F8h+var_3D4], ebx
0x1400c401b  xorps   xmm1, xmm1
0x1400c401e  movdqu  [rsp+3F8h+var_228], xmm1
0x1400c4027  mov     [rsp+3F8h+var_218], rbx
0x1400c402f  lea     r13, [r15+190h]
0x1400c4036  mov     [rsp+3F8h+var_3D0], r13
0x1400c403b  cmp     dword ptr [r13+0], 2
0x1400c4040  jnz     loc_1400C410F
0x1400c4046  xor     r8d, r8d
0x1400c4049  xor     edx, edx
0x1400c404b  mov     rcx, [rcx+3D8h]
0x1400c4052  call    ?StartReservingResources@VirtualMotherboard@@QEAAJPEAVVmRepository@@W4VmbReserveResourcesFlags@@@Z; VirtualMotherboard::StartReservingResources(VmRepository *,VmbReserveResourcesFlags)
0x1400c4057  mov     edi, eax
0x1400c4059  test    eax, eax
0x1400c405b  js      loc_1400C48E3
0x1400c4061  xor     edx, edx; Val
0x1400c4063  mov     r8d, 150h; Size
0x1400c4069  lea     rcx, [rsp+3F8h+var_1F8]; void *
0x1400c4071  call    memset_0
0x1400c4076  mov     rdi, [r14]
0x1400c4079  lea     rdx, [rsp+3F8h+var_3A8]
0x1400c407e  mov     rcx, r15
0x1400c4081  call    ?GetCurrentActivity@?$WorkerAsyncTask@VStartingTask@VmWorkerTrace@@@@IEAA?AVStartingTask@VmWorkerTrace@@XZ; WorkerAsyncTask<VmWorkerTrace::StartingTask>::GetCurrentActivity(void)
0x1400c4086  nop
0x1400c4087  lea     r8, [rdi+470h]
0x1400c408e  mov     rdx, rax
0x1400c4091  lea     rcx, [rsp+3F8h+var_1F8]; this
0x1400c4099  call    VmPerf__StartRelatedActivity_VmWorkerTrace__ConstructGuestRam_VmWorkerTrace__StartingTask__GUID_const___
0x1400c409e  nop
0x1400c409f  lea     rcx, [rsp+3F8h+var_3A8]; this
0x1400c40a4  call    ??1StartingTask@VmWorkerTrace@@QEAA@XZ; VmWorkerTrace::StartingTask::~StartingTask(void)
0x1400c40a9  mov     r9, [rsp+3F8h+var_E8]
0x1400c40b1  add     r9, 8; struct _GUID *
0x1400c40b5  mov     r8, [r15+18h]; struct IVmSimpleTask *
0x1400c40b9  xor     edx, edx; struct VmRepository *
0x1400c40bb  mov     rcx, [r14]; this
0x1400c40be  call    ?ConstructGuestRam@VirtualMachine@@QEAAJPEAVVmRepository@@PEAUIVmSimpleTask@@PEBU_GUID@@@Z; VirtualMachine::ConstructGuestRam(VmRepository *,IVmSimpleTask *,_GUID const *)
0x1400c40c3  mov     edi, eax
0x1400c40c5  mov     rcx, [rsp+3F8h]; this
0x1400c40cd  lea     r12, aOnecoreVmWorke_45; "onecore\\vm\\worker\\wpcore\\workertask"...
0x1400c40d4  test    eax, eax
0x1400c40d6  jns     short loc_1400C40E8
0x1400c40d8  mov     r9d, eax; char *
0x1400c40db  mov     r8, r12; unsigned int
0x1400c40de  mov     edx, 1C5h; void *
0x1400c40e3  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1400c40e8  mov     edx, edi
0x1400c40ea  lea     rcx, [rsp+3F8h+var_1F8]
0x1400c40f2  call    ?Stop@?$ActivityBase@VVmWorkerTrace@@$0A@$0BA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<VmWorkerTrace,0,16,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x1400c40f7  nop
0x1400c40f8  lea     rcx, [rsp+3F8h+var_1F8]; this
0x1400c4100  call    ??1ConstructGuestRam@VmWorkerTrace@@QEAA@XZ; VmWorkerTrace::ConstructGuestRam::~ConstructGuestRam(void)
0x1400c4105  test    edi, edi
0x1400c4107  js      loc_1400C48E3
0x1400c410d  jmp     short loc_1400C4116
0x1400c410f  lea     r12, aOnecoreVmWorke_45; "onecore\\vm\\worker\\wpcore\\workertask"...
0x1400c4116  mov     [rsp+3F8h+var_3D8], ebx; int
0x1400c411a  mov     [rsp+3F8h+var_254], ebx
0x1400c4121  mov     rax, [r14]
0x1400c4124  mov     rcx, [rax+430h]
0x1400c412b  mov     rax, [rcx]
0x1400c412e  lea     rdx, [rsp+3F8h+var_254]
0x1400c4136  mov     rax, [rax+58h]
0x1400c413a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400c413f  cmp     [rsp+3F8h+var_254], ebx
0x1400c4146  jz      loc_1400C4260
0x1400c414c  lea     rcx, [rsp+3F8h+var_A8]; this
0x1400c4154  call    ??0IsolationSettings@VmWorkerProcess@Config@@QEAA@XZ; Config::VmWorkerProcess::IsolationSettings::IsolationSettings(void)
0x1400c4159  nop
0x1400c415a  lea     rdx, [rsp+3F8h+var_3C0]
0x1400c415f  mov     rcx, [r14]
0x1400c4162  call    ?GetConfigRepository@VirtualMachine@@UEBA?AV?$VmReferencePtr@VVmRepository@@VVmUserReferenceTraits@Vml@@@Vml@@XZ; VirtualMachine::GetConfigRepository(void)
0x1400c4167  nop
0x1400c4168  lea     r8, [rsp+3F8h+var_A8]
0x1400c4170  mov     rdx, rax
0x1400c4173  lea     rcx, [rsp+3F8h+var_250]
0x1400c417b  call    ??$FromRepository@AEAV?$VmReferencePtr@VVmRepository@@VVmUserReferenceTraits@Vml@@@Vml@@UIsolationSettings@VmWorkerProcess@Config@@$$V@Marshal@@YA?AU?$pair@_NV?$vector@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4UnmarshalError@Marshal@@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4UnmarshalError@Marshal@@@std@@@2@@std@@@std@@AEAV?$VmReferencePtr@VVmRepository@@VVmUserReferenceTraits@Vml@@@Vml@@PEAUIsolationSettings@VmWorkerProcess@Config@@W4UnmarshalFlags@0@@Z; Marshal::FromRepository<Vml::VmReferencePtr<VmRepository,Vml::VmUserReferenceTraits> &,Config::VmWorkerProcess::IsolationSettings,>(Vml::VmReferencePtr<VmRepository,Vml::VmUserReferenceTraits> &,Config::VmWorkerProcess::IsolationSettings *,Marshal::UnmarshalFlags)
0x1400c4180  mov     dil, [rax]
0x1400c4183  lea     rcx, [rsp+3F8h+var_250+8]
0x1400c418b  call    ?_Tidy@?$vector@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4UnmarshalError@Marshal@@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4UnmarshalError@Marshal@@@std@@@2@@std@@AEAAXXZ; std::vector<std::pair<std::wstring,Marshal::UnmarshalError>>::_Tidy(void)
0x1400c4190  nop
0x1400c4191  lea     rcx, [rsp+3F8h+var_3C0]
0x1400c4196  call    ??1?$VmReferencePtr@VVmRepository@@VVmUserReferenceTraits@Vml@@@Vml@@QEAA@XZ; Vml::VmReferencePtr<VmRepository,Vml::VmUserReferenceTraits>::~VmReferencePtr<VmRepository,Vml::VmUserReferenceTraits>(void)
0x1400c419b  test    dil, dil
0x1400c419e  jnz     short loc_1400C41B7
0x1400c41a0  mov     edi, 80070057h
0x1400c41a5  lea     rcx, [rsp+3F8h+var_A8]; this
0x1400c41ad  call    ??1IsolationSettings@VmWorkerProcess@Config@@QEAA@XZ; Config::VmWorkerProcess::IsolationSettings::~IsolationSettings(void)
0x1400c41b2  jmp     loc_1400C48E3
0x1400c41b7  mov     rsi, [rsp+3F8h+var_A0]
0x1400c41bf  mov     rdi, [rsp+3F8h+var_98]
0x1400c41c7  mov     rax, [r14]
0x1400c41ca  mov     rcx, [rax+400h]
0x1400c41d1  add     rcx, 18h
0x1400c41d5  mov     rax, [rcx]
0x1400c41d8  mov     rax, [rax]
0x1400c41db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400c41e0  sub     edi, esi
0x1400c41e2  mov     r9d, edi
0x1400c41e5  mov     r8, rsi
0x1400c41e8  mov     esi, 1
0x1400c41ed  mov     edx, esi
0x1400c41ef  mov     rcx, rax
0x1400c41f2  call    cs:__imp_VidChangePartitionLifeState
0x1400c41f9  nop     dword ptr [rax+rax+00h]
0x1400c41fe  test    eax, eax
0x1400c4200  jnz     short loc_1400C4251
0x1400c4202  call    cs:__imp_GetLastError
0x1400c4209  nop     dword ptr [rax+rax+00h]
0x1400c420e  mov     edi, eax
0x1400c4210  test    eax, eax
0x1400c4212  jle     short loc_1400C421D
0x1400c4214  movzx   edi, ax
0x1400c4217  or      edi, 80070000h
0x1400c421d  mov     esi, 4020h
0x1400c4222  mov     ecx, esi
0x1400c4224  call    VmlIsDebugTraceEnabled
0x1400c4229  test    eax, eax
0x1400c422b  jz      short loc_1400C423F
0x1400c422d  mov     r8d, edi
0x1400c4230  lea     rdx, off_1402E3058; "Unable to begin isolated VM boot import"...
0x1400c4237  mov     ecx, esi
0x1400c4239  call    VmlDebugTraceWithError
0x1400c423e  nop
0x1400c423f  lea     rcx, [rsp+3F8h+var_A8]; this
0x1400c4247  call    ??1IsolationSettings@VmWorkerProcess@Config@@QEAA@XZ; Config::VmWorkerProcess::IsolationSettings::~IsolationSettings(void)
0x1400c424c  jmp     loc_1400C45AC
0x1400c4251  lea     rcx, [rsp+3F8h+var_A8]; this
0x1400c4259  call    ??1IsolationSettings@VmWorkerProcess@Config@@QEAA@XZ; Config::VmWorkerProcess::IsolationSettings::~IsolationSettings(void)
0x1400c425e  jmp     short loc_1400C4265
0x1400c4260  mov     esi, 1
0x1400c4265  mov     rax, [r14]
0x1400c4268  cmp     [rax+0A68h], bl
0x1400c426e  jz      loc_1400C42FA
0x1400c4274  mov     rcx, [rax+400h]
0x1400c427b  add     rcx, 18h
0x1400c427f  mov     rax, [rcx]
0x1400c4282  mov     rax, [rax]
0x1400c4285  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400c428a  xorps   xmm0, xmm0
0x1400c428d  xor     ecx, ecx
0x1400c428f  movups  [rsp+3F8h+var_250], xmm0
0x1400c4297  movups  [rsp+3F8h+var_240], xmm0
0x1400c429f  mov     [rsp+3F8h+var_230], rcx
0x1400c42a7  mov     dword ptr [rsp+3F8h+var_250], 5
0x1400c42b2  mov     byte ptr [rsp+3F8h+var_240+8], bl
0x1400c42b9  mov     dword ptr [rsp+3F8h+var_240+0Ch], 0Fh
0x1400c42c4  lea     r8, [rsp+3F8h+var_250]
0x1400c42cc  lea     edx, [rcx+28h]
0x1400c42cf  mov     rcx, rax
0x1400c42d2  call    cs:__imp_VidVsmSetPartitionConfig
0x1400c42d9  nop     dword ptr [rax+rax+00h]
0x1400c42de  mov     rcx, [rsp+3F8h]; this
0x1400c42e6  test    eax, eax
0x1400c42e8  jnz     short loc_1400C42FA
0x1400c42ea  lea     r8, aOnecoreVmWorke_18; "onecore\\vm\\worker\\wpcore\\workerhcll"...
0x1400c42f1  lea     edx, [rax+57h]; void *
0x1400c42f4  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1400c42fa  mov     rcx, [r14]
0x1400c42fd  cmp     [rcx+0B98h], bl
0x1400c4303  jz      short loc_1400C4330
0x1400c4305  lea     rdx, [rsp+3F8h+var_250]
0x1400c430d  call    ?LoadIgvmFileIntoGuest@VirtualMachine@@UEAA?AV?$vector@EV?$allocator@E@std@@@std@@XZ; VirtualMachine::LoadIgvmFileIntoGuest(void)
0x1400c4312  mov     rdx, rax
0x1400c4315  lea     rcx, [rsp+3F8h+var_228]
0x1400c431d  call    ??4?$vector@EV?$allocator@E@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::vector<uchar>::operator=(std::vector<uchar> &&)
0x1400c4322  lea     rcx, [rsp+3F8h+var_250]
0x1400c432a  call    ?_Tidy@?$vector@T_VID_VSM_MBP_PERMISSIONS@@V?$allocator@T_VID_VSM_MBP_PERMISSIONS@@@std@@@std@@AEAAXXZ; std::vector<_VID_VSM_MBP_PERMISSIONS>::_Tidy(void)
0x1400c432f  nop
0x1400c4330  mov     r8, rbx
0x1400c4333  xor     edx, edx
0x1400c4335  mov     rcx, r15
0x1400c4338  call    ?PowerOnVirtualMotherboard@WorkerTaskStarting@@AEAAJPEAVVmRepository@@T_VM_PERSIST_FLAGS@@@Z; WorkerTaskStarting::PowerOnVirtualMotherboard(VmRepository *,_VM_PERSIST_FLAGS)
0x1400c433d  mov     edi, eax
0x1400c433f  test    eax, eax
0x1400c4341  js      loc_1400C48E3
0x1400c4347  mov     rcx, [r14]; this
0x1400c434a  call    ?RegisterGuestCrashManager@VirtualMachine@@QEAAJXZ; VirtualMachine::RegisterGuestCrashManager(void)
0x1400c434f  mov     edi, eax
0x1400c4351  test    eax, eax
0x1400c4353  jns     short loc_1400C439E
0x1400c4355  mov     esi, 4020h
0x1400c435a  mov     ecx, esi
0x1400c435c  call    VmlIsDebugTraceEnabled
0x1400c4361  test    eax, eax
0x1400c4363  jz      loc_1400C4878
0x1400c4369  mov     r8d, edi
0x1400c436c  lea     rdx, off_1402E3040; "Failed to register the Guest Crash Mana"...
0x1400c4373  mov     ecx, esi
0x1400c4375  call    VmlDebugTraceWithError
0x1400c437a  jmp     loc_1400C4878
0x1400c437f  xor     ebx, ebx
0x1400c4381  mov     edi, [rsp+3F8h+var_3D8]
0x1400c4385  mov     eax, ebx
0x1400c4387  mov     r15, [rsp+3F8h+var_3B8]
0x1400c438c  mov     r14, [rsp+3F8h+var_210]
0x1400c4394  mov     r13, [rsp+3F8h+var_3D0]
0x1400c4399  jmp     loc_1400C45B0
0x1400c439e  cmp     dword ptr [r13+0], 33h ; '3'
0x1400c43a3  ja      short loc_1400C43D9
0x1400c43a5  movsxd  rax, dword ptr [r13+0]
0x1400c43a9  mov     rcx, 8000100008004h
0x1400c43b3  bt      rcx, rax
0x1400c43b7  jnb     short loc_1400C43D9
0x1400c43b9  mov     rax, [r14]
0x1400c43bc  mov     rcx, [rax+428h]
0x1400c43c3  mov     rax, [rcx]
0x1400c43c6  mov     rax, [rax+30h]
0x1400c43ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400c43cf  mov     edi, eax
0x1400c43d1  test    eax, eax
0x1400c43d3  js      loc_1400C4878
0x1400c43d9  lea     r8, [rsp+3F8h+var_3D4]; int *
0x1400c43de  mov     edx, 32h ; '2'; unsigned int
0x1400c43e3  mov     rcx, r15; this
0x1400c43e6  call    ?UpdateStatusProgress@WorkerAsyncTaskBase@@MEAAXIAEAH@Z; WorkerAsyncTaskBase::UpdateStatusProgress(uint,int &)
0x1400c43eb  cmp     [rsp+3F8h+var_3D4], ebx
0x1400c43ef  jz      short loc_1400C43FB
0x1400c43f1  mov     edi, 800704C7h
0x1400c43f6  jmp     loc_1400C4878
0x1400c43fb  cmp     dword ptr [r13+0], 20h ; ' '
0x1400c4400  jz      short loc_1400C441D
0x1400c4402  mov     rax, [r14]
0x1400c4405  mov     rcx, [rax+410h]
0x1400c440c  mov     rax, [rcx]
0x1400c440f  mov     edx, esi
0x1400c4411  mov     rax, [rax+290h]
0x1400c4418  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400c441d  xor     edx, edx; Val
0x1400c441f  mov     r8d, 150h; Size
0x1400c4425  lea     rcx, [rsp+3F8h+var_1F8]; void *
0x1400c442d  call    memset_0
0x1400c4432  mov     rdi, [r14]
0x1400c4435  lea     rcx, [rsp+3F8h+var_1F8]; struct wil::details::IFailureCallback *
0x1400c443d  call    ??0?$ActivityBase@VVmWorkerTrace@@$01$0BAAAA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<VmWorkerTrace,2,65536,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<VmWorkerTrace,2,65536,4,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x1400c4442  lea     rax, ??_7BootStateImporterFlush@VmWorkerTrace@@6B@; const VmWorkerTrace::BootStateImporterFlush::`vftable'
0x1400c4449  mov     [rsp+3F8h+var_1F8], rax
0x1400c4451  lea     rdx, [rdi+470h]; struct _GUID *
0x1400c4458  lea     rcx, [rsp+3F8h+var_1F8]; this
0x1400c4460  call    ?StartActivity@BootStateImporterFlush@VmWorkerTrace@@QEAAXAEBU_GUID@@@Z; VmWorkerTrace::BootStateImporterFlush::StartActivity(_GUID const &)
0x1400c4465  nop
0x1400c4466  mov     [rsp+3F8h+var_3D0], r15
0x1400c446b  lea     rcx, [rsp+3F8h+var_3D0]
0x1400c4470  call    wil__ResultFromException__lambda_1e435c07f28aa931d7536c0492f26ff8___
0x1400c4475  mov     edi, eax
0x1400c4477  mov     rcx, [rsp+3F8h]; this
0x1400c447f  test    eax, eax
0x1400c4481  jns     short loc_1400C4493
0x1400c4483  mov     r9d, eax; char *
0x1400c4486  mov     r8, r12; unsigned int
0x1400c4489  mov     edx, 249h; void *
0x1400c448e  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1400c4493  mov     edx, edi
0x1400c4495  lea     rcx, [rsp+3F8h+var_1F8]
0x1400c449d  call    ?Stop@?$ActivityBase@VVmWorkerTrace@@$01$0BAAAA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<VmWorkerTrace,2,65536,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x1400c44a2  lea     rcx, [rsp+3F8h+var_1F8]; this
0x1400c44aa  test    edi, edi
0x1400c44ac  jns     short loc_1400C44B8
0x1400c44ae  call    ??1BootStateImporterFlush@VmWorkerTrace@@QEAA@XZ; VmWorkerTrace::BootStateImporterFlush::~BootStateImporterFlush(void)
0x1400c44b3  jmp     loc_1400C4878
0x1400c44b8  mov     [rsp+3F8h+var_3D8], esi; int
0x1400c44bc  call    ??1BootStateImporterFlush@VmWorkerTrace@@QEAA@XZ; VmWorkerTrace::BootStateImporterFlush::~BootStateImporterFlush(void)
0x1400c44c1  cmp     [rsp+3F8h+var_254], ebx
0x1400c44c8  jz      loc_1400C45D8
0x1400c44ce  xor     edx, edx; Val
0x1400c44d0  mov     r8d, 150h; Size
0x1400c44d6  lea     rcx, [rsp+3F8h+var_1F8]; void *
0x1400c44de  call    memset_0
0x1400c44e3  mov     rdi, [r14]
0x1400c44e6  lea     rdx, aIsolatedvmboot; "IsolatedVmBootImport"
0x1400c44ed  lea     rcx, [rsp+3F8h+var_1F8]; struct wil::details::IFailureCallback *
0x1400c44f5  call    ??0?$ActivityBase@VVmWorkerTrace@@$01$0CAA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<VmWorkerTrace,2,512,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<VmWorkerTrace,2,512,4,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x1400c44fa  lea     rax, ??_7IsolatedVmBootImport@VmWorkerTrace@@6B@; const VmWorkerTrace::IsolatedVmBootImport::`vftable'
0x1400c4501  mov     [rsp+3F8h+var_1F8], rax
0x1400c4509  lea     rdx, [rdi+470h]; struct _GUID *
  ... truncated ...
```
