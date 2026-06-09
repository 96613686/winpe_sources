# WorkerTaskStarting::RunCleanStartSteps(void)

- ea: `0x1400931ac`
- end: `0x140093b4b`
- name: `?RunCleanStartSteps@WorkerTaskStarting@@AEAAJXZ`
- size: `2463`
- prototype: `__int64 __fastcall(WorkerTaskStarting *__hidden this)`
- caller_count: `2`
- callee_count: `46`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x14017e4dc`
- `0x14017fa40`

## callees

- `0x1400310b4`
- `0x140042260`
- `0x1400561c8`
- `0x14005b648`
- `0x14005e6a4`
- `0x14005e804`
- `0x14005ecc0`
- `0x140067f6c`
- `0x14007bee0`
- `0x14007c400`
- `0x1400931ac`
- `0x140093b54`
- `0x140093bdc`
- `0x140093c94`
- `0x140093d54`
- `0x140093fa4`
- `0x140093fd4`
- `0x140094094`
- `0x1400940c0`
- `0x1400941fc`
- `0x140094254`
- `0x14009fa0c`
- `0x1400c8410`
- `0x1400cf8c0`
- `0x1400d5db4`
- `0x140111090`
- `0x1401192b8`
- `0x140132960`
- `0x14013361c`
- `0x14014122c`
- `0x14014c9e8`
- `0x140162330`
- `0x14016ac80`
- `0x140170810`
- `0x14017cdf8`
- `0x14017ce24`
- `0x14017ce5c`
- `0x14017cf0c`
- `0x14017cf38`
- `0x14017e320`
- `0x140180004`
- `0x140180304`
- `0x140180544`
- `0x14018063c`
- `0x140180728`
- `0x1402c2010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140093414`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140093774`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140093414`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140093774`
- `vid!VidVsmSetPartitionConfig` at `0x1400934e4`
- `vid!VidVsmSetPartitionConfig` at `0x1400934e4`
- `vid!VidTrimPartitionMemory` at `0x1400938f7`
- `vid!VidTrimPartitionMemory` at `0x1400938f7`
- `vid!VidChangePartitionLifeState` at `0x140093404`
- `vid!VidChangePartitionLifeState` at `0x140093764`
- `vid!VidChangePartitionLifeState` at `0x140093404`
- `vid!VidChangePartitionLifeState` at `0x140093764`

## string_xrefs

- `0x140093206`: `onecore\vm\worker\wpcore\workertaskstarting.cpp`
- `0x1400932d1`: `onecore\vm\worker\wpcore\workertaskstarting.cpp`
- `0x140093313`: `onecore\vm\worker\wpcore\workertaskstarting.cpp`

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
  int v9; // edi
  __int64 v10; // rsi
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
  int v36; // [rsp+20h] [rbp-388h]
  int v37; // [rsp+20h] [rbp-388h]
  int v38; // [rsp+24h] [rbp-384h] BYREF
  _QWORD v39[2]; // [rsp+28h] [rbp-380h] BYREF
  _BYTE v40[8]; // [rsp+38h] [rbp-370h] BYREF
  WorkerAsyncTaskBase *v41; // [rsp+40h] [rbp-368h]
  _BYTE v42[336]; // [rsp+50h] [rbp-358h] BYREF
  unsigned int v43; // [rsp+1A0h] [rbp-208h] BYREF
  int v44; // [rsp+1A4h] [rbp-204h] BYREF
  wil::details::in1diag3 *v45; // [rsp+1A8h] [rbp-200h] BYREF
  __int128 v46; // [rsp+1B0h] [rbp-1F8h] BYREF
  __int64 v47; // [rsp+1C0h] [rbp-1E8h]
  __int128 v48; // [rsp+1C8h] [rbp-1E0h] BYREF
  __int64 v49; // [rsp+1D8h] [rbp-1D0h]
  _QWORD v50[2]; // [rsp+1E0h] [rbp-1C8h] BYREF
  __int128 v51; // [rsp+1F0h] [rbp-1B8h] BYREF
  __int128 v52; // [rsp+200h] [rbp-1A8h]
  __int64 v53; // [rsp+210h] [rbp-198h]
  _QWORD v54[42]; // [rsp+220h] [rbp-188h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+3A8h] [rbp+0h]

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
    memset_0(v54, 0, sizeof(v54));
    WorkerAsyncTask<VmWorkerTrace::StartingTask>::GetCurrentActivity(v1, v42);
    VmPerf::StartRelatedActivity_VmWorkerTrace::ConstructGuestRam_VmWorkerTrace::StartingTask__GUID_const___((VmWorkerTrace::ConstructGuestRam *)v54);
    VmWorkerTrace::StartingTask::~StartingTask((VmWorkerTrace::StartingTask *)v42);
    v6 = VirtualMachine::ConstructGuestRam(
           *v2,
           0,
           *((struct IVmSimpleTask **)v1 + 3),
           (const struct _GUID *)(v54[34] + 8LL));
    LODWORD(v5) = v6;
    if ( v6 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x1C5,
        (unsigned int)"onecore\\vm\\worker\\wpcore\\workertaskstarting.cpp",
        (const char *)(unsigned int)v6,
        v36);
    wil::ActivityBase<VmWorkerTrace,0,16,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v54, (unsigned int)v5);
    VmWorkerTrace::ConstructGuestRam::~ConstructGuestRam((VmWorkerTrace::ConstructGuestRam *)v54);
    if ( (int)v5 >= 0 )
    {
LABEL_8:
      v37 = 0;
      v44 = 0;
      (*(void (__fastcall **)(_QWORD, int *))(**((_QWORD **)*v2 + 134) + 88LL))(*((_QWORD *)*v2 + 134), &v44);
      if ( v44 )
      {
        v45 = 0;
        v46 = 0;
        v47 = 0;
        ConfigRepository = VirtualMachine::GetConfigRepository(*v2, v40);
        v8 = *(_BYTE *)Marshal::FromRepository<Vml::VmReferencePtr<VmRepository,Vml::VmUserReferenceTraits> &,Config::VmWorkerProcess::IsolationSettings,>(
                         &v51,
                         ConfigRepository,
                         &v45);
        std::vector<std::pair<std::wstring,enum Marshal::UnmarshalError>>::_Tidy((char *)&v51 + 8);
        Vml::VmReferencePtr<VmRepository,Vml::VmUserReferenceTraits>::~VmReferencePtr<VmRepository,Vml::VmUserReferenceTraits>(v40);
        if ( !v8 )
        {
          LODWORD(v5) = -2147024809;
          std::vector<_VID_VSM_MBP_PERMISSIONS>::_Tidy(&v46);
          goto LABEL_84;
        }
        v9 = DWORD2(v46);
        v10 = v46;
        v11 = (**(__int64 (__fastcall ***)(__int64))(*((_QWORD *)*v2 + 128) + 24LL))(*((_QWORD *)*v2 + 128) + 24LL);
        v12 = v9 - v10;
        v13 = v10;
        v14 = 1;
        if ( !(unsigned int)VidChangePartitionLifeState(v11, 1, v13, v12) )
        {
          LastError = GetLastError();
          LODWORD(v5) = LastError;
          if ( LastError > 0 )
            LODWORD(v5) = (unsigned __int16)LastError | 0x80070000;
          if ( (unsigned int)VmlIsDebugTraceEnabled(16416) )
            VmlDebugTraceWithError(16416, &off_1402D9C28, (unsigned int)v5);
          std::vector<_VID_VSM_MBP_PERMISSIONS>::_Tidy(&v46);
          goto LABEL_45;
        }
        std::vector<_VID_VSM_MBP_PERMISSIONS>::_Tidy(&v46);
      }
      else
      {
        v14 = 1;
      }
      if ( *((_BYTE *)*v2 + 2664) )
      {
        v16 = (**(__int64 (__fastcall ***)(__int64))(*((_QWORD *)*v2 + 128) + 24LL))(*((_QWORD *)*v2 + 128) + 24LL);
        v51 = 0;
        v52 = 0;
        v53 = 0;
        LODWORD(v51) = 5;
        BYTE8(v52) = 0;
        HIDWORD(v52) = 15;
        if ( !(unsigned int)VidVsmSetPartitionConfig(v16, 40, &v51) )
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
              memset_0(v54, 0, sizeof(v54));
              v5 = (const struct _GUID *)*v2;
              wil::ActivityBase<VmWorkerTrace,2,65536,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<VmWorkerTrace,2,65536,4,0,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v54);
              v54[0] = &VmWorkerTrace::BootStateImporterFlush::`vftable';
              VmWorkerTrace::BootStateImporterFlush::StartActivity(
                (VmWorkerTrace::BootStateImporterFlush *)v54,
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
                v54,
                (unsigned int)v5);
              if ( (int)v5 >= 0 )
              {
                v37 = 1;
                VmWorkerTrace::BootStateImporterFlush::~BootStateImporterFlush((VmWorkerTrace::BootStateImporterFlush *)v54);
                if ( v44 )
                {
                  memset_0(v54, 0, sizeof(v54));
                  v22 = *v2;
                  wil::ActivityBase<VmWorkerTrace,2,512,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<VmWorkerTrace,2,512,4,0,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v54);
                  v54[0] = &VmWorkerTrace::IsolatedVmBootImport::`vftable';
                  VmWorkerTrace::IsolatedVmBootImport::StartActivity(
                    (VmWorkerTrace::IsolatedVmBootImport *)v54,
                    (const struct _GUID *)v22 + 71);
                  v23 = (**(__int64 (__fastcall ***)(__int64))(*((_QWORD *)*v2 + 128) + 24LL))(*((_QWORD *)*v2 + 128) + 24LL);
                  if ( !(unsigned int)VidChangePartitionLifeState(v23, 2, v48, (unsigned int)(DWORD2(v48) - v48)) )
                  {
                    v24 = GetLastError();
                    LODWORD(v5) = v24;
                    if ( v24 > 0 )
                      LODWORD(v5) = (unsigned __int16)v24 | 0x80070000;
                    if ( (unsigned int)VmlIsDebugTraceEnabled(16416) )
                      VmlDebugTraceWithError(16416, &off_1402D9C10, (unsigned int)v5);
                    VmWorkerTrace::IsolatedVmBootImport::~IsolatedVmBootImport((VmWorkerTrace::IsolatedVmBootImport *)v54);
LABEL_45:
                    v25 = v37;
LABEL_46:
                    if ( (int)v5 < 0 )
                      goto LABEL_76;
                    goto LABEL_79;
                  }
                  wil::ActivityBase<VmWorkerTrace,2,512,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v54);
                  VmWorkerTrace::IsolatedVmBootImport::~IsolatedVmBootImport((VmWorkerTrace::IsolatedVmBootImport *)v54);
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
                memset_0(v54, 0, sizeof(v54));
                v5 = (const struct _GUID *)*v2;
                wil::ActivityBase<VmWorkerTrace,2,64,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<VmWorkerTrace,2,64,4,0,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v54);
                v54[0] = &VmWorkerTrace::StartVm::`vftable';
                VmWorkerTrace::StartVm::StartActivity((VmWorkerTrace::StartVm *)v54, v5 + 71);
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
                  v54,
                  (unsigned int)v5);
                VmWorkerTrace::StartVm::~StartVm((VmWorkerTrace::StartVm *)v54);
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
                    memset_0(v54, 0, sizeof(v54));
                    wil::ActivityBase<VmWorkerTrace,2,64,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<VmWorkerTrace,2,64,4,0,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v54);
                    v54[0] = &VmWorkerTrace::StartVtl0::`vftable';
                    VmWorkerTrace::StartVtl0::StartActivity(
                      (VmWorkerTrace::StartVtl0 *)v54,
                      (const struct _GUID *)v30 + 71);
                    v39[0] = &v43;
                    v39[1] = v1;
                    v45 = retaddr;
                    *(_QWORD *)&v46 = "onecore\\vm\\worker\\wpcore\\workertaskstarting.cpp";
                    *((_QWORD *)&v46 + 1) = 0;
                    LOWORD(v47) = 683;
                    v50[0] = &off_1402CA978;
                    v50[1] = v39;
                    v5 = (const struct _GUID *)(unsigned int)wil::details::ResultFromException(&v45, v31, v50);
                    wil::ActivityBase<VmWorkerTrace,2,64,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v54, v5);
                    VmWorkerTrace::StartVtl0::~StartVtl0((VmWorkerTrace::StartVtl0 *)v54);
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
                VmWorkerTrace::BootStateImporterFlush::~BootStateImporterFlush((VmWorkerTrace::BootStateImporterFlush *)v54);
              }
            }
          }
        }
        else if ( (unsigned int)VmlIsDebugTraceEnabled(16416) )
        {
          VmlDebugTraceWithError(16416, &off_1402D9C40, (unsigned int)v5);
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
0x1400931ac  mov     [rsp+arg_8], rbx
0x1400931b1  mov     [rsp+arg_10], rsi
0x1400931b6  push    rdi
0x1400931b7  push    r12
0x1400931b9  push    r13
0x1400931bb  push    r14
0x1400931bd  push    r15
0x1400931bf  sub     rsp, 380h
0x1400931c6  mov     rax, cs:__security_cookie
0x1400931cd  xor     rax, rsp
0x1400931d0  mov     [rsp+3A8h+var_38], rax
0x1400931d8  mov     r15, rcx
0x1400931db  mov     [rsp+3A8h+var_368], rcx
0x1400931e0  lea     r14, [rcx+10h]
0x1400931e4  mov     [rsp+3A8h+var_1C8], r14
0x1400931ec  mov     rcx, [r14]
0x1400931ef  mov     r9, [rsp+3A8h]; char *
0x1400931f7  mov     rax, [rcx+588h]
0x1400931fe  xor     ebx, ebx
0x140093200  cmp     [rax+58h], rbx
0x140093204  jnz     short loc_14009321B
0x140093206  lea     r8, aOnecoreVmWorke_44; "onecore\\vm\\worker\\wpcore\\workertask"...
0x14009320d  mov     edx, 1AFh; void *
0x140093212  mov     rcx, r9; this
0x140093215  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x14009321b  mov     [rsp+3A8h+var_384], ebx
0x14009321f  xorps   xmm1, xmm1
0x140093222  movdqu  [rsp+3A8h+var_1E0], xmm1
0x14009322b  mov     [rsp+3A8h+var_1D0], rbx
0x140093233  lea     r13, [r15+190h]
0x14009323a  mov     [rsp+3A8h+var_380], r13
0x14009323f  cmp     dword ptr [r13+0], 2
0x140093244  jnz     loc_140093313
0x14009324a  xor     r8d, r8d
0x14009324d  xor     edx, edx
0x14009324f  mov     rcx, [rcx+3D8h]
0x140093256  call    ?StartReservingResources@VirtualMotherboard@@QEAAJPEAVVmRepository@@W4VmbReserveResourcesFlags@@@Z; VirtualMotherboard::StartReservingResources(VmRepository *,VmbReserveResourcesFlags)
0x14009325b  mov     edi, eax
0x14009325d  test    eax, eax
0x14009325f  js      loc_140093AF5
0x140093265  xor     edx, edx; Val
0x140093267  mov     r8d, 150h; Size
0x14009326d  lea     rcx, [rsp+3A8h+var_188]; void *
0x140093275  call    memset_0
0x14009327a  mov     rdi, [r14]
0x14009327d  lea     rdx, [rsp+3A8h+var_358]
0x140093282  mov     rcx, r15
0x140093285  call    ?GetCurrentActivity@?$WorkerAsyncTask@VStartingTask@VmWorkerTrace@@@@IEAA?AVStartingTask@VmWorkerTrace@@XZ; WorkerAsyncTask<VmWorkerTrace::StartingTask>::GetCurrentActivity(void)
0x14009328a  nop
0x14009328b  lea     r8, [rdi+470h]
0x140093292  mov     rdx, rax
0x140093295  lea     rcx, [rsp+3A8h+var_188]; this
0x14009329d  call    VmPerf__StartRelatedActivity_VmWorkerTrace__ConstructGuestRam_VmWorkerTrace__StartingTask__GUID_const___
0x1400932a2  nop
0x1400932a3  lea     rcx, [rsp+3A8h+var_358]; this
0x1400932a8  call    ??1StartingTask@VmWorkerTrace@@QEAA@XZ; VmWorkerTrace::StartingTask::~StartingTask(void)
0x1400932ad  mov     r9, [rsp+3A8h+var_78]
0x1400932b5  add     r9, 8; struct _GUID *
0x1400932b9  mov     r8, [r15+18h]; struct IVmSimpleTask *
0x1400932bd  xor     edx, edx; struct VmRepository *
0x1400932bf  mov     rcx, [r14]; this
0x1400932c2  call    ?ConstructGuestRam@VirtualMachine@@QEAAJPEAVVmRepository@@PEAUIVmSimpleTask@@PEBU_GUID@@@Z; VirtualMachine::ConstructGuestRam(VmRepository *,IVmSimpleTask *,_GUID const *)
0x1400932c7  mov     edi, eax
0x1400932c9  mov     rcx, [rsp+3A8h]; this
0x1400932d1  lea     r12, aOnecoreVmWorke_44; "onecore\\vm\\worker\\wpcore\\workertask"...
0x1400932d8  test    eax, eax
0x1400932da  jns     short loc_1400932EC
0x1400932dc  mov     r9d, eax; char *
0x1400932df  mov     r8, r12; unsigned int
0x1400932e2  mov     edx, 1C5h; void *
0x1400932e7  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1400932ec  mov     edx, edi
0x1400932ee  lea     rcx, [rsp+3A8h+var_188]
0x1400932f6  call    ?Stop@?$ActivityBase@VVmWorkerTrace@@$0A@$0BA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<VmWorkerTrace,0,16,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x1400932fb  nop
0x1400932fc  lea     rcx, [rsp+3A8h+var_188]; this
0x140093304  call    ??1ConstructGuestRam@VmWorkerTrace@@QEAA@XZ; VmWorkerTrace::ConstructGuestRam::~ConstructGuestRam(void)
0x140093309  test    edi, edi
0x14009330b  js      loc_140093AF5
0x140093311  jmp     short loc_14009331A
0x140093313  lea     r12, aOnecoreVmWorke_44; "onecore\\vm\\worker\\wpcore\\workertask"...
0x14009331a  mov     [rsp+3A8h+var_388], ebx; int
0x14009331e  mov     [rsp+3A8h+var_204], ebx
0x140093325  mov     rax, [r14]
0x140093328  mov     rcx, [rax+430h]
0x14009332f  mov     rax, [rcx]
0x140093332  lea     rdx, [rsp+3A8h+var_204]
0x14009333a  mov     rax, [rax+58h]
0x14009333e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140093343  cmp     [rsp+3A8h+var_204], ebx
0x14009334a  jz      loc_140093472
0x140093350  mov     [rsp+3A8h+var_200], rbx
0x140093358  xorps   xmm0, xmm0
0x14009335b  movdqu  [rsp+3A8h+var_1F8], xmm0
0x140093364  mov     [rsp+3A8h+var_1E8], rbx
0x14009336c  lea     rdx, [rsp+3A8h+var_370]
0x140093371  mov     rcx, [r14]
0x140093374  call    ?GetConfigRepository@VirtualMachine@@UEBA?AV?$VmReferencePtr@VVmRepository@@VVmUserReferenceTraits@Vml@@@Vml@@XZ; VirtualMachine::GetConfigRepository(void)
0x140093379  nop
0x14009337a  lea     r8, [rsp+3A8h+var_200]
0x140093382  mov     rdx, rax
0x140093385  lea     rcx, [rsp+3A8h+var_1B8]
0x14009338d  call    ??$FromRepository@AEAV?$VmReferencePtr@VVmRepository@@VVmUserReferenceTraits@Vml@@@Vml@@UIsolationSettings@VmWorkerProcess@Config@@$$V@Marshal@@YA?AU?$pair@_NV?$vector@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4UnmarshalError@Marshal@@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4UnmarshalError@Marshal@@@std@@@2@@std@@@std@@AEAV?$VmReferencePtr@VVmRepository@@VVmUserReferenceTraits@Vml@@@Vml@@PEAUIsolationSettings@VmWorkerProcess@Config@@W4UnmarshalFlags@0@@Z; Marshal::FromRepository<Vml::VmReferencePtr<VmRepository,Vml::VmUserReferenceTraits> &,Config::VmWorkerProcess::IsolationSettings,>(Vml::VmReferencePtr<VmRepository,Vml::VmUserReferenceTraits> &,Config::VmWorkerProcess::IsolationSettings *,Marshal::UnmarshalFlags)
0x140093392  mov     dil, [rax]
0x140093395  lea     rcx, [rsp+3A8h+var_1B8+8]
0x14009339d  call    ?_Tidy@?$vector@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4UnmarshalError@Marshal@@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4UnmarshalError@Marshal@@@std@@@2@@std@@AEAAXXZ; std::vector<std::pair<std::wstring,Marshal::UnmarshalError>>::_Tidy(void)
0x1400933a2  nop
0x1400933a3  lea     rcx, [rsp+3A8h+var_370]
0x1400933a8  call    ??1?$VmReferencePtr@VVmRepository@@VVmUserReferenceTraits@Vml@@@Vml@@QEAA@XZ; Vml::VmReferencePtr<VmRepository,Vml::VmUserReferenceTraits>::~VmReferencePtr<VmRepository,Vml::VmUserReferenceTraits>(void)
0x1400933ad  test    dil, dil
0x1400933b0  jnz     short loc_1400933C9
0x1400933b2  mov     edi, 80070057h
0x1400933b7  lea     rcx, [rsp+3A8h+var_1F8]
0x1400933bf  call    ?_Tidy@?$vector@T_VID_VSM_MBP_PERMISSIONS@@V?$allocator@T_VID_VSM_MBP_PERMISSIONS@@@std@@@std@@AEAAXXZ; std::vector<_VID_VSM_MBP_PERMISSIONS>::_Tidy(void)
0x1400933c4  jmp     loc_140093AF5
0x1400933c9  mov     rsi, qword ptr [rsp+3A8h+var_1F8]
0x1400933d1  mov     rdi, qword ptr [rsp+3A8h+var_1F8+8]
0x1400933d9  mov     rax, [r14]
0x1400933dc  mov     rcx, [rax+400h]
0x1400933e3  add     rcx, 18h
0x1400933e7  mov     rax, [rcx]
0x1400933ea  mov     rax, [rax]
0x1400933ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400933f2  sub     edi, esi
0x1400933f4  mov     r9d, edi
0x1400933f7  mov     r8, rsi
0x1400933fa  mov     esi, 1
0x1400933ff  mov     edx, esi
0x140093401  mov     rcx, rax
0x140093404  call    cs:__imp_VidChangePartitionLifeState
0x14009340b  nop     dword ptr [rax+rax+00h]
0x140093410  test    eax, eax
0x140093412  jnz     short loc_140093463
0x140093414  call    cs:__imp_GetLastError
0x14009341b  nop     dword ptr [rax+rax+00h]
0x140093420  mov     edi, eax
0x140093422  test    eax, eax
0x140093424  jle     short loc_14009342F
0x140093426  movzx   edi, ax
0x140093429  or      edi, 80070000h
0x14009342f  mov     esi, 4020h
0x140093434  mov     ecx, esi
0x140093436  call    VmlIsDebugTraceEnabled
0x14009343b  test    eax, eax
0x14009343d  jz      short loc_140093451
0x14009343f  mov     r8d, edi
0x140093442  lea     rdx, off_1402D9C28; "Unable to begin isolated VM boot import"...
0x140093449  mov     ecx, esi
0x14009344b  call    VmlDebugTraceWithError
0x140093450  nop
0x140093451  lea     rcx, [rsp+3A8h+var_1F8]
0x140093459  call    ?_Tidy@?$vector@T_VID_VSM_MBP_PERMISSIONS@@V?$allocator@T_VID_VSM_MBP_PERMISSIONS@@@std@@@std@@AEAAXXZ; std::vector<_VID_VSM_MBP_PERMISSIONS>::_Tidy(void)
0x14009345e  jmp     loc_1400937BE
0x140093463  lea     rcx, [rsp+3A8h+var_1F8]
0x14009346b  call    ?_Tidy@?$vector@T_VID_VSM_MBP_PERMISSIONS@@V?$allocator@T_VID_VSM_MBP_PERMISSIONS@@@std@@@std@@AEAAXXZ; std::vector<_VID_VSM_MBP_PERMISSIONS>::_Tidy(void)
0x140093470  jmp     short loc_140093477
0x140093472  mov     esi, 1
0x140093477  mov     rax, [r14]
0x14009347a  cmp     [rax+0A68h], bl
0x140093480  jz      loc_14009350C
0x140093486  mov     rcx, [rax+400h]
0x14009348d  add     rcx, 18h
0x140093491  mov     rax, [rcx]
0x140093494  mov     rax, [rax]
0x140093497  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14009349c  xorps   xmm0, xmm0
0x14009349f  xor     ecx, ecx
0x1400934a1  movups  [rsp+3A8h+var_1B8], xmm0
0x1400934a9  movups  [rsp+3A8h+var_1A8], xmm0
0x1400934b1  mov     [rsp+3A8h+var_198], rcx
0x1400934b9  mov     dword ptr [rsp+3A8h+var_1B8], 5
0x1400934c4  mov     byte ptr [rsp+3A8h+var_1A8+8], bl
0x1400934cb  mov     dword ptr [rsp+3A8h+var_1A8+0Ch], 0Fh
0x1400934d6  lea     r8, [rsp+3A8h+var_1B8]
0x1400934de  lea     edx, [rcx+28h]
0x1400934e1  mov     rcx, rax
0x1400934e4  call    cs:__imp_VidVsmSetPartitionConfig
0x1400934eb  nop     dword ptr [rax+rax+00h]
0x1400934f0  mov     rcx, [rsp+3A8h]; this
0x1400934f8  test    eax, eax
0x1400934fa  jnz     short loc_14009350C
0x1400934fc  lea     r8, aOnecoreVmWorke_17; "onecore\\vm\\worker\\wpcore\\workerhcll"...
0x140093503  lea     edx, [rax+57h]; void *
0x140093506  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x14009350c  mov     rcx, [r14]
0x14009350f  cmp     [rcx+0B98h], bl
0x140093515  jz      short loc_140093542
0x140093517  lea     rdx, [rsp+3A8h+var_200]
0x14009351f  call    ?LoadIgvmFileIntoGuest@VirtualMachine@@UEAA?AV?$vector@EV?$allocator@E@std@@@std@@XZ; VirtualMachine::LoadIgvmFileIntoGuest(void)
0x140093524  mov     rdx, rax
0x140093527  lea     rcx, [rsp+3A8h+var_1E0]
0x14009352f  call    ??4?$vector@EV?$allocator@E@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::vector<uchar>::operator=(std::vector<uchar> &&)
0x140093534  lea     rcx, [rsp+3A8h+var_200]
0x14009353c  call    ?_Tidy@?$vector@T_VID_VSM_MBP_PERMISSIONS@@V?$allocator@T_VID_VSM_MBP_PERMISSIONS@@@std@@@std@@AEAAXXZ; std::vector<_VID_VSM_MBP_PERMISSIONS>::_Tidy(void)
0x140093541  nop
0x140093542  mov     r8, rbx
0x140093545  xor     edx, edx
0x140093547  mov     rcx, r15
0x14009354a  call    ?PowerOnVirtualMotherboard@WorkerTaskStarting@@AEAAJPEAVVmRepository@@T_VM_PERSIST_FLAGS@@@Z; WorkerTaskStarting::PowerOnVirtualMotherboard(VmRepository *,_VM_PERSIST_FLAGS)
0x14009354f  mov     edi, eax
0x140093551  test    eax, eax
0x140093553  js      loc_140093AF5
0x140093559  mov     rcx, [r14]; this
0x14009355c  call    ?RegisterGuestCrashManager@VirtualMachine@@QEAAJXZ; VirtualMachine::RegisterGuestCrashManager(void)
0x140093561  mov     edi, eax
0x140093563  test    eax, eax
0x140093565  jns     short loc_1400935B0
0x140093567  mov     esi, 4020h
0x14009356c  mov     ecx, esi
0x14009356e  call    VmlIsDebugTraceEnabled
0x140093573  test    eax, eax
0x140093575  jz      loc_140093A8A
0x14009357b  mov     r8d, edi
0x14009357e  lea     rdx, off_1402D9C40; "Failed to register the Guest Crash Mana"...
0x140093585  mov     ecx, esi
0x140093587  call    VmlDebugTraceWithError
0x14009358c  jmp     loc_140093A8A
0x140093591  xor     ebx, ebx
0x140093593  mov     edi, [rsp+3A8h+var_388]
0x140093597  mov     eax, ebx
0x140093599  mov     r15, [rsp+3A8h+var_368]
0x14009359e  mov     r14, [rsp+3A8h+var_1C8]
0x1400935a6  mov     r13, [rsp+3A8h+var_380]
0x1400935ab  jmp     loc_1400937C2
0x1400935b0  cmp     dword ptr [r13+0], 33h ; '3'
0x1400935b5  ja      short loc_1400935EB
0x1400935b7  movsxd  rax, dword ptr [r13+0]
0x1400935bb  mov     rcx, 8000100008004h
0x1400935c5  bt      rcx, rax
0x1400935c9  jnb     short loc_1400935EB
0x1400935cb  mov     rax, [r14]
0x1400935ce  mov     rcx, [rax+428h]
0x1400935d5  mov     rax, [rcx]
0x1400935d8  mov     rax, [rax+30h]
0x1400935dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400935e1  mov     edi, eax
0x1400935e3  test    eax, eax
0x1400935e5  js      loc_140093A8A
0x1400935eb  lea     r8, [rsp+3A8h+var_384]; int *
0x1400935f0  mov     edx, 32h ; '2'; unsigned int
0x1400935f5  mov     rcx, r15; this
0x1400935f8  call    ?UpdateStatusProgress@WorkerAsyncTaskBase@@MEAAXIAEAH@Z; WorkerAsyncTaskBase::UpdateStatusProgress(uint,int &)
0x1400935fd  cmp     [rsp+3A8h+var_384], ebx
0x140093601  jz      short loc_14009360D
0x140093603  mov     edi, 800704C7h
0x140093608  jmp     loc_140093A8A
0x14009360d  cmp     dword ptr [r13+0], 20h ; ' '
0x140093612  jz      short loc_14009362F
0x140093614  mov     rax, [r14]
0x140093617  mov     rcx, [rax+410h]
0x14009361e  mov     rax, [rcx]
0x140093621  mov     edx, esi
0x140093623  mov     rax, [rax+290h]
0x14009362a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14009362f  xor     edx, edx; Val
0x140093631  mov     r8d, 150h; Size
0x140093637  lea     rcx, [rsp+3A8h+var_188]; void *
0x14009363f  call    memset_0
0x140093644  mov     rdi, [r14]
0x140093647  lea     rcx, [rsp+3A8h+var_188]; struct wil::details::IFailureCallback *
0x14009364f  call    ??0?$ActivityBase@VVmWorkerTrace@@$01$0BAAAA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<VmWorkerTrace,2,65536,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<VmWorkerTrace,2,65536,4,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x140093654  lea     rax, ??_7BootStateImporterFlush@VmWorkerTrace@@6B@; const VmWorkerTrace::BootStateImporterFlush::`vftable'
0x14009365b  mov     [rsp+3A8h+var_188], rax
0x140093663  lea     rdx, [rdi+470h]; struct _GUID *
0x14009366a  lea     rcx, [rsp+3A8h+var_188]; this
0x140093672  call    ?StartActivity@BootStateImporterFlush@VmWorkerTrace@@QEAAXAEBU_GUID@@@Z; VmWorkerTrace::BootStateImporterFlush::StartActivity(_GUID const &)
0x140093677  nop
0x140093678  mov     [rsp+3A8h+var_380], r15
0x14009367d  lea     rcx, [rsp+3A8h+var_380]
0x140093682  call    wil__ResultFromException__lambda_1e435c07f28aa931d7536c0492f26ff8___
0x140093687  mov     edi, eax
0x140093689  mov     rcx, [rsp+3A8h]; this
0x140093691  test    eax, eax
0x140093693  jns     short loc_1400936A5
0x140093695  mov     r9d, eax; char *
0x140093698  mov     r8, r12; unsigned int
0x14009369b  mov     edx, 249h; void *
0x1400936a0  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1400936a5  mov     edx, edi
0x1400936a7  lea     rcx, [rsp+3A8h+var_188]
0x1400936af  call    ?Stop@?$ActivityBase@VVmWorkerTrace@@$01$0BAAAA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<VmWorkerTrace,2,65536,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x1400936b4  lea     rcx, [rsp+3A8h+var_188]; this
0x1400936bc  test    edi, edi
0x1400936be  jns     short loc_1400936CA
0x1400936c0  call    ??1BootStateImporterFlush@VmWorkerTrace@@QEAA@XZ; VmWorkerTrace::BootStateImporterFlush::~BootStateImporterFlush(void)
0x1400936c5  jmp     loc_140093A8A
0x1400936ca  mov     [rsp+3A8h+var_388], esi; int
0x1400936ce  call    ??1BootStateImporterFlush@VmWorkerTrace@@QEAA@XZ; VmWorkerTrace::BootStateImporterFlush::~BootStateImporterFlush(void)
0x1400936d3  cmp     [rsp+3A8h+var_204], ebx
0x1400936da  jz      loc_1400937EA
0x1400936e0  xor     edx, edx; Val
0x1400936e2  mov     r8d, 150h; Size
0x1400936e8  lea     rcx, [rsp+3A8h+var_188]; void *
0x1400936f0  call    memset_0
0x1400936f5  mov     rdi, [r14]
0x1400936f8  lea     rdx, aIsolatedvmboot; "IsolatedVmBootImport"
0x1400936ff  lea     rcx, [rsp+3A8h+var_188]; struct wil::details::IFailureCallback *
0x140093707  call    ??0?$ActivityBase@VVmWorkerTrace@@$01$0CAA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<VmWorkerTrace,2,512,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<VmWorkerTrace,2,512,4,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x14009370c  lea     rax, ??_7IsolatedVmBootImport@VmWorkerTrace@@6B@; const VmWorkerTrace::IsolatedVmBootImport::`vftable'
0x140093713  mov     [rsp+3A8h+var_188], rax
  ... truncated ...
```
