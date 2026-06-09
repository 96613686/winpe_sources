# WorkerTaskMigrationTarget::DoTdxVpStateImport(void)

- ea: `0x140218848`
- end: `0x140218f8e`
- name: `?DoTdxVpStateImport@WorkerTaskMigrationTarget@@AEAAJXZ`
- size: `1862`
- prototype: `__int64 __fastcall(WorkerTaskMigrationTarget *__hidden this)`
- caller_count: `1`
- callee_count: `34`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x14005ecc0`

## callees

- `0x14003b720`
- `0x14003d828`
- `0x140052d9c`
- `0x1400691b4`
- `0x140069690`
- `0x14006b204`
- `0x14006b2c4`
- `0x14006b8b8`
- `0x14006b908`
- `0x14006be48`
- `0x140078628`
- `0x14007a6cc`
- `0x140083990`
- `0x14008bdbc`
- `0x1400927e8`
- `0x14009e678`
- `0x1400a1a58`
- `0x1400a1b2c`
- `0x1400b4028`
- `0x1400b4058`
- `0x1400d937c`
- `0x1400da008`
- `0x1400da040`
- `0x14011ea40`
- `0x14011f6fc`
- `0x140121a35`
- `0x1401cca04`
- `0x1401cce98`
- `0x14020d358`
- `0x140212b8c`
- `0x140213900`
- `0x140218848`
- `0x1402204d0`
- `0x1402cb010`

## import_xrefs

- `vid!VidTdxImportVpState` at `0x140218d45`
- `vid!VidTdxImportVpState` at `0x140218d45`

## string_xrefs

- `0x140218e75`: `onecore\vm\worker\migration\workertaskmigrationtarget.cpp`
- `0x140218e89`: `onecore\vm\worker\migration\workertaskmigrationtarget.cpp`
- `0x140218e9d`: `onecore\vm\worker\migration\workertaskmigrationtarget.cpp`
- `0x140218ec2`: `onecore\vm\worker\migration\workertaskmigrationtarget.cpp`
- `0x140218ed7`: `onecore\vm\worker\migration\workertaskmigrationtarget.cpp`
- `0x140218eeb`: `onecore\vm\worker\migration\workertaskmigrationtarget.cpp`
- `0x140218f10`: `onecore\vm\worker\migration\workertaskmigrationtarget.cpp`
- `0x140218f27`: `onecore\vm\worker\migration\workertaskmigrationtarget.cpp`
- `0x140218f3e`: `onecore\vm\worker\migration\workertaskmigrationtarget.cpp`
- `0x140218f55`: `onecore\vm\worker\migration\workertaskmigrationtarget.cpp`
- `0x140218f66`: `onecore\vm\worker\migration\workertaskmigrationtarget.cpp`
- `0x140218f7b`: `onecore\vm\worker\migration\workertaskmigrationtarget.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=6 #try_helpers=1
__int64 __fastcall WorkerTaskMigrationTarget::DoTdxVpStateImport(WorkerTaskMigrationTarget *this)
{
  unsigned __int64 v2; // r14
  char *v3; // r15
  const struct _GUID *v4; // rsi
  const unsigned __int16 *v5; // rdi
  __int64 v6; // rbx
  unsigned __int64 v7; // r12
  VmMigrationConnection **v8; // rdi
  int v9; // eax
  int v10; // eax
  VmMigrationConnection *v11; // rax
  __int64 v12; // rcx
  unsigned int v13; // eax
  char v14; // dl
  char *v15; // rbx
  int v16; // eax
  VmMigrationConnection *v17; // rax
  __int64 v18; // rcx
  unsigned int v19; // eax
  char v20; // dl
  __int64 v21; // rsi
  _QWORD *v22; // rbx
  char v23; // al
  __int64 v24; // r9
  __int64 v25; // r13
  const unsigned __int16 *v26; // rax
  __int64 v27; // rcx
  __int64 v28; // r13
  __int64 v29; // rax
  const char *v30; // r9
  int v31; // eax
  unsigned int v32; // r13d
  const struct _GUID *v33; // rdi
  const unsigned __int16 *v34; // rbx
  unsigned int v36; // eax
  unsigned int v37; // eax
  int v38; // [rsp+20h] [rbp-428h]
  int v39; // [rsp+20h] [rbp-428h]
  int v40; // [rsp+30h] [rbp-418h] BYREF
  unsigned int v41; // [rsp+34h] [rbp-414h]
  unsigned __int64 VmName; // [rsp+38h] [rbp-410h] BYREF
  __int64 v43; // [rsp+40h] [rbp-408h] BYREF
  WorkerTaskMigrationTarget *v44; // [rsp+48h] [rbp-400h]
  unsigned __int64 v45; // [rsp+50h] [rbp-3F8h]
  struct _GUID v46; // [rsp+60h] [rbp-3E8h] BYREF
  _QWORD v47[2]; // [rsp+70h] [rbp-3D8h] BYREF
  _QWORD v48[2]; // [rsp+80h] [rbp-3C8h] BYREF
  _BYTE v49[16]; // [rsp+90h] [rbp-3B8h] BYREF
  _BYTE v50[336]; // [rsp+A0h] [rbp-3A8h] BYREF
  void *Src[2]; // [rsp+1F0h] [rbp-258h] BYREF
  _BYTE v52[5]; // [rsp+200h] [rbp-248h] BYREF
  __int16 v53; // [rsp+205h] [rbp-243h]
  char v54; // [rsp+207h] [rbp-241h]
  __int64 v55; // [rsp+208h] [rbp-240h]
  __int64 v56; // [rsp+210h] [rbp-238h]
  char v57; // [rsp+218h] [rbp-230h]
  int v58; // [rsp+219h] [rbp-22Fh]
  __int16 v59; // [rsp+21Dh] [rbp-22Bh]
  char v60; // [rsp+21Fh] [rbp-229h]
  __int128 v61; // [rsp+220h] [rbp-228h] BYREF
  unsigned __int8 *v62[2]; // [rsp+230h] [rbp-218h] BYREF
  __int64 v63; // [rsp+240h] [rbp-208h]
  _BYTE v64[40]; // [rsp+250h] [rbp-1F8h] BYREF
  _BYTE v65[72]; // [rsp+278h] [rbp-1D0h] BYREF
  _QWORD v66[42]; // [rsp+2C0h] [rbp-188h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+448h] [rbp+0h]

  v44 = this;
  v40 = 0;
  v2 = 0;
  v45 = 0;
  v46 = 0;
  v3 = (char *)this + 16;
  v43 = (__int64)this + 16;
  Vml::VmPerfTraceOperation::VmPerfTraceOperation(
    (Vml::VmPerfTraceOperation *)v64,
    (struct Vml::VmPerfTraceComponent *)&g_MigrationPerfTrace,
    (const struct _GUID *)(*((_QWORD *)this + 2) + 1136LL),
    &v46);
  VmName = (unsigned __int64)VirtualMachine::GetVmName((VirtualMachine *)(*(_QWORD *)v3 + 16LL));
  Vml::VmPerfTraceOperation::BeginOperation<unsigned short const *>(
    (Vml::VmPerfTraceOperation *)v64,
    &VMWP_PERF_MIGRATION_TARGET_TDX_START_IMPORT_VP_STATES);
  memset_0(v66, 0, sizeof(v66));
  v4 = *(const struct _GUID **)v3;
  v5 = VirtualMachine::GetVmName((VirtualMachine *)(*(_QWORD *)v3 + 16LL));
  v6 = *(_QWORD *)(WorkerAsyncTask<VmWorkerTrace::TargetMigrationTask>::GetCurrentActivity(this, v50) + 272);
  memset_0(v66, 0, sizeof(v66));
  wil::ActivityBase<VmWorkerTrace,0,262144,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<VmWorkerTrace,0,262144,4,0,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v66);
  v66[0] = &VmWorkerTrace::MigrationTransferTdxVpState::`vftable';
  v40 = 2;
  wil::ActivityBase<VmWorkerTrace,2,512,4,0,_TlgReflectorTag_Param0IsProviderType>::SetRelatedActivityId(v66, v6 + 8);
  VmWorkerTrace::MigrationTransferTdxVpState::StartActivity(
    (VmWorkerTrace::MigrationTransferTdxVpState *)v66,
    v4 + 71,
    v5);
  VmWorkerTrace::TargetMigrationTask::~TargetMigrationTask((VmWorkerTrace::TargetMigrationTask *)v50);
  v7 = 0;
  v41 = 0;
  v8 = (VmMigrationConnection **)((char *)this + 440);
  v9 = VmMigrationConnection::BeginMessageSequence(*((_QWORD *)this + 55), 53);
  if ( v9 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xDB5,
      (unsigned int)"onecore\\vm\\worker\\migration\\workertaskmigrationtarget.cpp",
      (const char *)(unsigned int)v9,
      v38);
  v40 = 0;
  do
  {
    Src[0] = 0;
    VmName = 0;
    v52[0] = -1;
    *(_DWORD *)&v52[1] = 0;
    v53 = 0;
    v54 = 0;
    v55 = 0;
    v56 = 0;
    v57 = 0;
    v58 = 0;
    v59 = 0;
    v60 = 0;
    v10 = VmMigrationConnection::ReceiveMessage(
            *v8,
            (unsigned __int64 *)Src,
            &VmName,
            &v40,
            (struct _SECURE_MIGRATION_CONTROL_DATA *)v52);
    if ( v10 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xDC1,
        (unsigned int)"onecore\\vm\\worker\\migration\\workertaskmigrationtarget.cpp",
        (const char *)(unsigned int)v10,
        v39);
    if ( v10 == 294977 )
    {
      v40 = 0;
      v11 = (VmMigrationConnection *)Vml::VmReferencePtr<IVirtualMachine,Vml::VmWeakReferenceTraits>::operator->(v8);
      LOBYTE(v12) = (unsigned int)VmMigrationConnection::GetAsyncSendError(v11, &v40) == 0;
      wil::verify_bool<bool,0>(v12);
      v13 = wil::verify_hresult<long>(2147943759LL);
      if ( v14 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xDC2,
          (unsigned int)"onecore\\vm\\worker\\migration\\workertaskmigrationtarget.cpp",
          (const char *)v13,
          v39);
      v36 = wil::verify_hresult<long>((unsigned int)v40);
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xDC2,
        (unsigned int)"onecore\\vm\\worker\\migration\\workertaskmigrationtarget.cpp",
        (const char *)v36,
        v39);
    }
    *(_OWORD *)v62 = 0;
    v63 = 0;
    v15 = (char *)Src[0];
    std::vector<enum gsl::byte>::vector<enum gsl::byte>(v62, Src[0]);
    v16 = VmMigrationConnection::ReceiveMessageData(
            *v8,
            v62[0],
            (unsigned __int64)v15,
            (struct _SECURE_MIGRATION_CONTROL_DATA *)v52);
    if ( v16 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xDC8,
        (unsigned int)"onecore\\vm\\worker\\migration\\workertaskmigrationtarget.cpp",
        (const char *)(unsigned int)v16,
        v39);
    if ( v16 == 294977 )
    {
      v40 = 0;
      v17 = (VmMigrationConnection *)Vml::VmReferencePtr<IVirtualMachine,Vml::VmWeakReferenceTraits>::operator->(v8);
      LOBYTE(v18) = (unsigned int)VmMigrationConnection::GetAsyncSendError(v17, &v40) == 0;
      wil::verify_bool<bool,0>(v18);
      v19 = wil::verify_hresult<long>(2147943759LL);
      if ( v20 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xDC9,
          (unsigned int)"onecore\\vm\\worker\\migration\\workertaskmigrationtarget.cpp",
          (const char *)v19,
          v39);
      v37 = wil::verify_hresult<long>((unsigned int)v40);
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xDC9,
        (unsigned int)"onecore\\vm\\worker\\migration\\workertaskmigrationtarget.cpp",
        (const char *)v37,
        v39);
    }
    v61 = 0;
    gsl::span<unsigned char,-1>::span<unsigned char,-1>(v49, v62);
    gsl::span<enum gsl::byte const,-1>::subspan(v49, &v61, v56, &v15[-v56]);
    v21 = 0;
    while ( v7 < VmName )
    {
      if ( v21 + 16 > (unsigned __int64)v61 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xDD2,
          (unsigned int)"onecore\\vm\\worker\\migration\\workertaskmigrationtarget.cpp",
          (const char *)0x8007000DLL,
          v39);
      *(_OWORD *)Src = 0;
      gsl::span<enum gsl::byte const,-1>::subspan(&v61, Src, v21, 16);
      v22 = Src[1];
      v47[0] = Src[0];
      v47[1] = Src[1];
      if ( (unsigned __int64)gsl::span<unsigned char,-1>::size_bytes(v47) < 0x10 )
      {
        v22 = 0;
      }
      else
      {
        gsl::span<unsigned char,-1>::size_bytes(v47);
        if ( v22 )
        {
          v23 = 0;
          goto LABEL_19;
        }
      }
      v23 = 1;
LABEL_19:
      if ( v23 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xDD6,
          (unsigned int)"onecore\\vm\\worker\\migration\\workertaskmigrationtarget.cpp",
          (const char *)0x8000FFFFLL,
          v39);
      v24 = v22[1];
      if ( v21 + v24 + 16 > (unsigned __int64)v61 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xDD8,
          (unsigned int)"onecore\\vm\\worker\\migration\\workertaskmigrationtarget.cpp",
          (const char *)0x8007000DLL,
          v39);
      *(_OWORD *)Src = 0;
      gsl::span<enum gsl::byte const,-1>::subspan(&v61, Src, v21 + 16, v24);
      memcpy_0(*(void **)(*((_QWORD *)v44 + 108) + 8LL), Src[1], v22[1]);
      v25 = *(_QWORD *)v3;
      v26 = VirtualMachine::GetVmName((VirtualMachine *)(*(_QWORD *)v3 + 16LL));
      v27 = -1;
      do
        ++v27;
      while ( v26[v27] );
      v48[0] = v26;
      v48[1] = v27;
      *(_QWORD *)&v46.Data1 = "ImportVpState";
      *(_QWORD *)v46.Data4 = 13;
      VmWorkerTrace::CvmLmProtocolEvent(&v46, v25 + 1136, v48);
      v28 = v22[1];
      Src[0] = *(void **)(*((_QWORD *)v44 + 108) + 24LL);
      v29 = (**(__int64 (__fastcall ***)(__int64))(*(_QWORD *)(*(_QWORD *)v3 + 1024LL) + 24LL))(*(_QWORD *)(*(_QWORD *)v3 + 1024LL) + 24LL);
      if ( !(unsigned int)VidTdxImportVpState(v29, Src[0], 0, v28) )
        wil::details::in1diag3::Throw_GetLastError(
          retaddr,
          (void *)0xDEB,
          (unsigned int)"onecore\\vm\\worker\\migration\\workertaskmigrationtarget.cpp",
          v30);
      v21 += v22[1] + 16LL;
      v45 = ++v2;
      ++v7;
    }
    std::vector<_VID_VSM_MBP_PERMISSIONS>::_Tidy(v62);
    v7 = 0;
  }
  while ( !v40 );
  v31 = VmMigrationConnection::AcknowledgeMessageSequence(*v8, 0, 0);
  if ( v31 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xDF3,
      (unsigned int)"onecore\\vm\\worker\\migration\\workertaskmigrationtarget.cpp",
      (const char *)(unsigned int)v31,
      v39);
  v32 = v41;
  v33 = *(const struct _GUID **)v3;
  v34 = VirtualMachine::GetVmName((VirtualMachine *)(*(_QWORD *)v3 + 16LL));
  wil::ActivityBase<VmWorkerTrace,0,262144,5,0,_TlgReflectorTag_Param0IsProviderType>::SetStopResult(v66, v32);
  VmWorkerTrace::MigrationTransferTdxVpState::Stop((VmWorkerTrace::MigrationTransferTdxVpState *)v66, v33 + 71, v34, v2);
  v43 = (__int64)VirtualMachine::GetVmName((VirtualMachine *)(*(_QWORD *)v3 + 16LL));
  Vml::VmPerfTraceOperation::EndOperation<unsigned short const *>(
    (Vml::VmPerfTraceOperation *)v64,
    &VMWP_PERF_MIGRATION_TARGET_TDX_STOP_IMPORT_VP_STATES,
    (__int64)&v43);
  VmWorkerTrace::MigrationTransferTdxVpState::~MigrationTransferTdxVpState((VmWorkerTrace::MigrationTransferTdxVpState *)v66);
  std::wstring::_Tidy_deallocate(v65);
  return v32;
}

```

## disassembly

```asm
0x140218848  mov     [rsp+arg_8], rbx
0x14021884d  mov     [rsp+arg_10], rsi
0x140218852  push    rdi
0x140218853  push    r12
0x140218855  push    r13
0x140218857  push    r14
0x140218859  push    r15
0x14021885b  sub     rsp, 420h
0x140218862  mov     rax, cs:__security_cookie
0x140218869  xor     rax, rsp
0x14021886c  mov     [rsp+448h+var_38], rax
0x140218874  mov     r13, rcx
0x140218877  mov     [rsp+448h+var_400], rcx
0x14021887c  xor     eax, eax
0x14021887e  mov     [rsp+448h+var_418], eax
0x140218882  mov     r14d, eax
0x140218885  mov     [rsp+448h+var_3F8], rax
0x14021888a  xorps   xmm0, xmm0
0x14021888d  movups  xmmword ptr [rsp+448h+var_3E8.Data1], xmm0
0x140218892  lea     r15, [rcx+10h]
0x140218896  mov     [rsp+448h+var_408], r15
0x14021889b  mov     r8, [r15]
0x14021889e  add     r8, 470h; struct _GUID *
0x1402188a5  lea     r9, [rsp+448h+var_3E8]; struct _GUID *
0x1402188aa  lea     rdx, ?g_MigrationPerfTrace@@3VVmPerfTraceComponent@Vml@@A; struct Vml::VmPerfTraceComponent *
0x1402188b1  lea     rcx, [rsp+448h+var_1F8]; this
0x1402188b9  call    ??0VmPerfTraceOperation@Vml@@QEAA@AEAVVmPerfTraceComponent@1@AEBU_GUID@@1@Z; Vml::VmPerfTraceOperation::VmPerfTraceOperation(Vml::VmPerfTraceComponent &,_GUID const &,_GUID const &)
0x1402188be  nop
0x1402188bf  mov     rcx, [r15]
0x1402188c2  add     rcx, 10h; this
0x1402188c6  call    ?GetVmName@VirtualMachine@@UEBAPEBGXZ; VirtualMachine::GetVmName(void)
0x1402188cb  mov     [rsp+448h+var_410], rax
0x1402188d0  lea     r8, [rsp+448h+var_410]
0x1402188d5  lea     rdx, VMWP_PERF_MIGRATION_TARGET_TDX_START_IMPORT_VP_STATES; EventDescriptor
0x1402188dc  lea     rcx, [rsp+448h+var_1F8]; this
0x1402188e4  call    ??$BeginOperation@PEBG@VmPerfTraceOperation@Vml@@QEAAXAEBU_EVENT_DESCRIPTOR@@$$QEAPEBG@Z; Vml::VmPerfTraceOperation::BeginOperation<ushort const *>(_EVENT_DESCRIPTOR const &,ushort const * &&)
0x1402188e9  mov     r12d, 150h
0x1402188ef  mov     r8d, r12d; Size
0x1402188f2  xor     edx, edx; Val
0x1402188f4  lea     rcx, [rsp+448h+var_188]; void *
0x1402188fc  call    memset_0
0x140218901  mov     rsi, [r15]
0x140218904  lea     rcx, [rsi+10h]; this
0x140218908  call    ?GetVmName@VirtualMachine@@UEBAPEBGXZ; VirtualMachine::GetVmName(void)
0x14021890d  mov     rdi, rax
0x140218910  lea     rdx, [rsp+448h+var_3A8]
0x140218918  mov     rcx, r13
0x14021891b  call    ?GetCurrentActivity@?$WorkerAsyncTask@VTargetMigrationTask@VmWorkerTrace@@@@IEAA?AVTargetMigrationTask@VmWorkerTrace@@XZ; WorkerAsyncTask<VmWorkerTrace::TargetMigrationTask>::GetCurrentActivity(void)
0x140218920  nop
0x140218921  mov     rbx, [rax+110h]
0x140218928  mov     r8d, r12d; Size
0x14021892b  xor     edx, edx; Val
0x14021892d  lea     rcx, [rsp+448h+var_188]; void *
0x140218935  call    memset_0
0x14021893a  lea     rdx, aMigrationtrans_6; "MigrationTransferTdxVpState"
0x140218941  lea     rcx, [rsp+448h+var_188]; struct wil::details::IFailureCallback *
0x140218949  call    ??0?$ActivityBase@VVmWorkerTrace@@$0A@$0EAAAA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<VmWorkerTrace,0,262144,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<VmWorkerTrace,0,262144,4,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x14021894e  lea     rax, ??_7MigrationTransferTdxVpState@VmWorkerTrace@@6B@; const VmWorkerTrace::MigrationTransferTdxVpState::`vftable'
0x140218955  mov     [rsp+448h+var_188], rax
0x14021895d  mov     [rsp+448h+var_418], 2
0x140218965  lea     rdx, [rbx+8]
0x140218969  lea     rcx, [rsp+448h+var_188]
0x140218971  call    ?SetRelatedActivityId@?$ActivityBase@VVmWorkerTrace@@$01$0CAA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXAEBU_GUID@@@Z; wil::ActivityBase<VmWorkerTrace,2,512,4,0,_TlgReflectorTag_Param0IsProviderType>::SetRelatedActivityId(_GUID const &)
0x140218976  lea     rdx, [rsi+470h]; struct _GUID *
0x14021897d  mov     r8, rdi; unsigned __int16 *
0x140218980  lea     rcx, [rsp+448h+var_188]; this
0x140218988  call    ?StartActivity@MigrationTransferTdxVpState@VmWorkerTrace@@QEAAXAEBU_GUID@@PEBG@Z; VmWorkerTrace::MigrationTransferTdxVpState::StartActivity(_GUID const &,ushort const *)
0x14021898d  nop
0x14021898e  lea     rcx, [rsp+448h+var_3A8]; this
0x140218996  call    ??1TargetMigrationTask@VmWorkerTrace@@QEAA@XZ; VmWorkerTrace::TargetMigrationTask::~TargetMigrationTask(void)
0x14021899b  xor     r12d, r12d
0x14021899e  mov     [rsp+448h+var_414], r12d
0x1402189a3  lea     rdi, [r13+1B8h]
0x1402189aa  lea     edx, [r14+35h]
0x1402189ae  mov     rcx, [rdi]
0x1402189b1  call    ?BeginMessageSequence@VmMigrationConnection@@QEAAJW4MESSAGE_SEQUENCE_TYPE@1@@Z; VmMigrationConnection::BeginMessageSequence(VmMigrationConnection::MESSAGE_SEQUENCE_TYPE)
0x1402189b6  mov     rcx, [rsp+448h]; this
0x1402189be  test    eax, eax
0x1402189c0  js      loc_140218E72
0x1402189c6  mov     [rsp+448h+var_418], r12d
0x1402189cb  mov     [rsp+448h+Src], r12
0x1402189d3  mov     [rsp+448h+var_410], r12
0x1402189d8  mov     [rsp+448h+var_248], 0FFh
0x1402189e0  xor     eax, eax
0x1402189e2  mov     dword ptr [rsp+448h+var_248+1], eax
0x1402189e9  mov     [rsp+448h+var_243], ax
0x1402189f1  mov     [rsp+448h+var_241], al
0x1402189f8  mov     [rsp+448h+var_240], r12
0x140218a00  mov     [rsp+448h+var_238], r12
0x140218a08  mov     [rsp+448h+var_230], r12b
0x140218a10  mov     [rsp+448h+var_22F], eax
0x140218a17  mov     [rsp+448h+var_22B], ax
0x140218a1f  mov     [rsp+448h+var_229], al
0x140218a26  lea     rax, [rsp+448h+var_248]
0x140218a2e  mov     qword ptr [rsp+448h+var_428], rax; int
0x140218a33  lea     r9, [rsp+448h+var_418]; int *
0x140218a38  lea     r8, [rsp+448h+var_410]; unsigned __int64 *
0x140218a3d  lea     rdx, [rsp+448h+Src]; unsigned __int64 *
0x140218a45  mov     rcx, [rdi]; this
0x140218a48  call    ?ReceiveMessage@VmMigrationConnection@@QEAAJAEA_K0AEAHAEAU_SECURE_MIGRATION_CONTROL_DATA@@@Z; VmMigrationConnection::ReceiveMessage(unsigned __int64 &,unsigned __int64 &,int &,_SECURE_MIGRATION_CONTROL_DATA &)
0x140218a4d  mov     rcx, [rsp+448h]; this
0x140218a55  test    eax, eax
0x140218a57  js      loc_140218E86
0x140218a5d  cmp     eax, 48041h
0x140218a62  jnz     short loc_140218AA9
0x140218a64  mov     [rsp+448h+var_418], r12d
0x140218a69  mov     rcx, rdi
0x140218a6c  call    ??C?$VmReferencePtr@UIVirtualMachine@@VVmWeakReferenceTraits@Vml@@@Vml@@QEBAPEAUIVirtualMachine@@XZ; Vml::VmReferencePtr<IVirtualMachine,Vml::VmWeakReferenceTraits>::operator->(void)
0x140218a71  lea     rdx, [rsp+448h+var_418]; int *
0x140218a76  mov     rcx, rax; this
0x140218a79  call    ?GetAsyncSendError@VmMigrationConnection@@QEAAHAEAJ@Z; VmMigrationConnection::GetAsyncSendError(long &)
0x140218a7e  test    eax, eax
0x140218a80  setz    cl
0x140218a83  call    ??$verify_bool@_N$0A@@wil@@YA_N_N@Z; wil::verify_bool<bool,0>(bool)
0x140218a88  mov     dl, al
0x140218a8a  mov     ecx, 8007054Fh
0x140218a8f  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x140218a94  mov     rcx, [rsp+448h]; this
0x140218a9c  test    dl, dl
0x140218a9e  jz      loc_140218EAE
0x140218aa4  jmp     loc_140218E9A
0x140218aa9  xorps   xmm0, xmm0
0x140218aac  xor     eax, eax
0x140218aae  movups  xmmword ptr [rsp+448h+var_218], xmm0
0x140218ab6  mov     [rsp+448h+var_208], rax
0x140218abe  mov     rbx, [rsp+448h+Src]
0x140218ac6  mov     rdx, rbx
0x140218ac9  lea     rcx, [rsp+448h+var_218]
0x140218ad1  call    ??0?$vector@W4byte@gsl@@V?$allocator@W4byte@gsl@@@std@@@std@@QEAA@_KAEBV?$allocator@W4byte@gsl@@@1@@Z; std::vector<gsl::byte>::vector<gsl::byte>(unsigned __int64,std::allocator<gsl::byte> const &)
0x140218ad6  nop
0x140218ad7  lea     r9, [rsp+448h+var_248]; struct _SECURE_MIGRATION_CONTROL_DATA *
0x140218adf  mov     r8, rbx; unsigned __int64
0x140218ae2  mov     rdx, [rsp+448h+var_218]; unsigned __int8 *
0x140218aea  mov     rcx, [rdi]; this
0x140218aed  call    ?ReceiveMessageData@VmMigrationConnection@@QEAAJPEAE_KAEAU_SECURE_MIGRATION_CONTROL_DATA@@@Z; VmMigrationConnection::ReceiveMessageData(uchar *,unsigned __int64,_SECURE_MIGRATION_CONTROL_DATA &)
0x140218af2  mov     rcx, [rsp+448h]; this
0x140218afa  test    eax, eax
0x140218afc  js      loc_140218ED4
0x140218b02  cmp     eax, 48041h
0x140218b07  jnz     short loc_140218B4E
0x140218b09  mov     [rsp+448h+var_418], r12d
0x140218b0e  mov     rcx, rdi
0x140218b11  call    ??C?$VmReferencePtr@UIVirtualMachine@@VVmWeakReferenceTraits@Vml@@@Vml@@QEBAPEAUIVirtualMachine@@XZ; Vml::VmReferencePtr<IVirtualMachine,Vml::VmWeakReferenceTraits>::operator->(void)
0x140218b16  lea     rdx, [rsp+448h+var_418]; int *
0x140218b1b  mov     rcx, rax; this
0x140218b1e  call    ?GetAsyncSendError@VmMigrationConnection@@QEAAHAEAJ@Z; VmMigrationConnection::GetAsyncSendError(long &)
0x140218b23  test    eax, eax
0x140218b25  setz    cl
0x140218b28  call    ??$verify_bool@_N$0A@@wil@@YA_N_N@Z; wil::verify_bool<bool,0>(bool)
0x140218b2d  mov     dl, al
0x140218b2f  mov     ecx, 8007054Fh
0x140218b34  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x140218b39  mov     rcx, [rsp+448h]; this
0x140218b41  test    dl, dl
0x140218b43  jz      loc_140218EFC
0x140218b49  jmp     loc_140218EE8
0x140218b4e  xorps   xmm0, xmm0
0x140218b51  movups  [rsp+448h+var_228], xmm0
0x140218b59  lea     rdx, [rsp+448h+var_218]
0x140218b61  lea     rcx, [rsp+448h+var_3B8]
0x140218b69  call    ??$?0$0?0V?$vector@EV?$allocator@E@std@@@std@@$0A@@?$span@E$0?0@gsl@@QEAA@AEAV?$vector@EV?$allocator@E@std@@@std@@@Z; gsl::span<uchar,-1>::span<uchar,-1>(std::vector<uchar> &)
0x140218b6e  mov     r8, [rsp+448h+var_238]
0x140218b76  sub     rbx, r8
0x140218b79  mov     r9, rbx
0x140218b7c  lea     rdx, [rsp+448h+var_228]
0x140218b84  lea     rcx, [rsp+448h+var_3B8]
0x140218b8c  call    ?subspan@?$span@$$CBW4byte@gsl@@$0?0@gsl@@QEBA?AV12@_K0@Z; gsl::span<gsl::byte const,-1>::subspan(unsigned __int64,unsigned __int64)
0x140218b91  mov     rsi, r12
0x140218b94  cmp     r12, [rsp+448h+var_410]
0x140218b99  jnb     loc_140218D79
0x140218b9f  lea     r13, [rsi+10h]
0x140218ba3  cmp     r13, qword ptr [rsp+448h+var_228]
0x140218bab  setnbe  al
0x140218bae  mov     rcx, [rsp+448h]; this
0x140218bb6  test    al, al
0x140218bb8  jnz     loc_140218F21
0x140218bbe  xorps   xmm0, xmm0
0x140218bc1  movups  xmmword ptr [rsp+448h+Src], xmm0
0x140218bc9  mov     r9d, 10h
0x140218bcf  mov     r8, rsi
0x140218bd2  lea     rdx, [rsp+448h+Src]
0x140218bda  lea     rcx, [rsp+448h+var_228]
0x140218be2  call    ?subspan@?$span@$$CBW4byte@gsl@@$0?0@gsl@@QEBA?AV12@_K0@Z; gsl::span<gsl::byte const,-1>::subspan(unsigned __int64,unsigned __int64)
0x140218be7  mov     rbx, [rsp+448h+Src+8]
0x140218bef  mov     rax, [rsp+448h+Src]
0x140218bf7  mov     [rsp+448h+var_3D8], rax
0x140218bfc  mov     [rsp+448h+var_3D0], rbx
0x140218c01  lea     rcx, [rsp+448h+var_3D8]
0x140218c06  call    ?size_bytes@?$span@E$0?0@gsl@@QEBA_KXZ; gsl::span<uchar,-1>::size_bytes(void)
0x140218c0b  cmp     rax, 10h
0x140218c0f  jb      short loc_140218C26
0x140218c11  lea     rcx, [rsp+448h+var_3D8]
0x140218c16  call    ?size_bytes@?$span@E$0?0@gsl@@QEBA_KXZ; gsl::span<uchar,-1>::size_bytes(void)
0x140218c1b  xor     edx, edx
0x140218c1d  test    rbx, rbx
0x140218c20  jz      short loc_140218C2A
0x140218c22  mov     al, dl
0x140218c24  jmp     short loc_140218C2C
0x140218c26  xor     edx, edx
0x140218c28  mov     ebx, edx
0x140218c2a  mov     al, 1
0x140218c2c  mov     rcx, [rsp+448h]; this
0x140218c34  test    al, al
0x140218c36  jnz     loc_140218F38
0x140218c3c  mov     r9, [rbx+8]
0x140218c40  lea     rax, [r9+10h]
0x140218c44  add     rax, rsi
0x140218c47  cmp     rax, qword ptr [rsp+448h+var_228]
0x140218c4f  setnbe  al
0x140218c52  mov     rcx, [rsp+448h]; this
0x140218c5a  test    al, al
0x140218c5c  jnz     loc_140218F4F
0x140218c62  xorps   xmm0, xmm0
0x140218c65  movups  xmmword ptr [rsp+448h+Src], xmm0
0x140218c6d  mov     r8, r13
0x140218c70  lea     rdx, [rsp+448h+Src]
0x140218c78  lea     rcx, [rsp+448h+var_228]
0x140218c80  call    ?subspan@?$span@$$CBW4byte@gsl@@$0?0@gsl@@QEBA?AV12@_K0@Z; gsl::span<gsl::byte const,-1>::subspan(unsigned __int64,unsigned __int64)
0x140218c85  mov     rcx, [rsp+448h+var_400]
0x140218c8a  mov     rcx, [rcx+360h]
0x140218c91  mov     r8, [rbx+8]; Size
0x140218c95  mov     rdx, [rsp+448h+Src+8]; Src
0x140218c9d  mov     rcx, [rcx+8]; void *
0x140218ca1  call    memcpy_0
0x140218ca6  mov     r13, [r15]
0x140218ca9  lea     rcx, [r13+10h]; this
0x140218cad  call    ?GetVmName@VirtualMachine@@UEBAPEBGXZ; VirtualMachine::GetVmName(void)
0x140218cb2  or      rcx, 0FFFFFFFFFFFFFFFFh
0x140218cb6  xor     edx, edx
0x140218cb8  inc     rcx
0x140218cbb  cmp     [rax+rcx*2], dx
0x140218cbf  jnz     short loc_140218CB8
0x140218cc1  mov     [rsp+448h+var_3C8], rax
0x140218cc9  mov     [rsp+448h+var_3C0], rcx
0x140218cd1  lea     rax, aImportvpstate; "ImportVpState"
0x140218cd8  mov     qword ptr [rsp+448h+var_3E8.Data1], rax
0x140218cdd  mov     qword ptr [rsp+448h+var_3E8.Data4], 0Dh
0x140218ce6  lea     rdx, [r13+470h]
0x140218ced  lea     r8, [rsp+448h+var_3C8]
0x140218cf5  lea     rcx, [rsp+448h+var_3E8]
0x140218cfa  call    ?CvmLmProtocolEvent@VmWorkerTrace@@SAXV?$basic_string_view@DU?$char_traits@D@std@@@std@@AEBU_GUID@@V?$basic_string_view@GU?$char_traits@G@std@@@3@@Z; VmWorkerTrace::CvmLmProtocolEvent(std::string_view,_GUID const &,std::basic_string_view<ushort>)
0x140218cff  mov     r13, [rbx+8]
0x140218d03  mov     rax, [rsp+448h+var_400]
0x140218d08  mov     rax, [rax+360h]
0x140218d0f  mov     rax, [rax+18h]
0x140218d13  mov     [rsp+448h+Src], rax
0x140218d1b  mov     rax, [r15]
0x140218d1e  mov     rcx, [rax+400h]
0x140218d25  add     rcx, 18h
0x140218d29  mov     rax, [rcx]
0x140218d2c  mov     rax, [rax]
0x140218d2f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140218d34  xor     r8d, r8d
0x140218d37  mov     r9, r13
0x140218d3a  mov     rdx, [rsp+448h+Src]
0x140218d42  mov     rcx, rax
0x140218d45  call    cs:__imp_VidTdxImportVpState
0x140218d4c  nop     dword ptr [rax+rax+00h]
0x140218d51  mov     rcx, [rsp+448h]; this
0x140218d59  test    eax, eax
0x140218d5b  jz      loc_140218F66
0x140218d61  add     rsi, 10h
0x140218d65  add     rsi, [rbx+8]
0x140218d69  inc     r14
0x140218d6c  mov     [rsp+448h+var_3F8], r14
0x140218d71  inc     r12
0x140218d74  jmp     loc_140218B94
0x140218d79  lea     rcx, [rsp+448h+var_218]
0x140218d81  call    ?_Tidy@?$vector@T_VID_VSM_MBP_PERMISSIONS@@V?$allocator@T_VID_VSM_MBP_PERMISSIONS@@@std@@@std@@AEAAXXZ; std::vector<_VID_VSM_MBP_PERMISSIONS>::_Tidy(void)
0x140218d86  xor     r12d, r12d
0x140218d89  cmp     [rsp+448h+var_418], r12d
0x140218d8e  jz      loc_1402189CB
0x140218d94  xor     r8d, r8d; unsigned __int64
0x140218d97  xor     edx, edx; struct VmMigrationNetworkBuffer *
0x140218d99  mov     rcx, [rdi]; this
0x140218d9c  call    ?AcknowledgeMessageSequence@VmMigrationConnection@@QEAAJPEBVVmMigrationNetworkBuffer@@_K@Z; VmMigrationConnection::AcknowledgeMessageSequence(VmMigrationNetworkBuffer const *,unsigned __int64)
0x140218da1  mov     rcx, [rsp+448h]; this
0x140218da9  test    eax, eax
0x140218dab  js      loc_140218F78
0x140218db1  jmp     short loc_140218DBD
0x140218db3  mov     r14, [rsp+448h+var_3F8]
0x140218db8  mov     r15, [rsp+448h+var_408]
0x140218dbd  mov     r13d, [rsp+448h+var_414]
0x140218dc2  mov     rdi, [r15]
0x140218dc5  lea     rcx, [rdi+10h]; this
0x140218dc9  call    ?GetVmName@VirtualMachine@@UEBAPEBGXZ; VirtualMachine::GetVmName(void)
0x140218dce  mov     rbx, rax
0x140218dd1  mov     edx, r13d
0x140218dd4  lea     rcx, [rsp+448h+var_188]
0x140218ddc  call    ?SetStopResult@?$ActivityBase@VVmWorkerTrace@@$0A@$0EAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXJPEAJ@Z; wil::ActivityBase<VmWorkerTrace,0,262144,5,0,_TlgReflectorTag_Param0IsProviderType>::SetStopResult(long,long *)
0x140218de1  lea     rdx, [rdi+470h]; struct _GUID *
0x140218de8  mov     r9, r14; unsigned __int64
0x140218deb  mov     r8, rbx; unsigned __int16 *
0x140218dee  lea     rcx, [rsp+448h+var_188]; this
0x140218df6  call    ?Stop@MigrationTransferTdxVpState@VmWorkerTrace@@QEAAXAEBU_GUID@@PEBG_K@Z; VmWorkerTrace::MigrationTransferTdxVpState::Stop(_GUID const &,ushort const *,unsigned __int64)
0x140218dfb  mov     rcx, [r15]
0x140218dfe  add     rcx, 10h; this
0x140218e02  call    ?GetVmName@VirtualMachine@@UEBAPEBGXZ; VirtualMachine::GetVmName(void)
0x140218e07  mov     [rsp+448h+var_408], rax
0x140218e0c  lea     r8, [rsp+448h+var_408]; __int64
  ... truncated ...
```
