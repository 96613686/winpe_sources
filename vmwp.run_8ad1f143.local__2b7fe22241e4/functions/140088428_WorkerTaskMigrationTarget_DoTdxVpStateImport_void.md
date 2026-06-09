# WorkerTaskMigrationTarget::DoTdxVpStateImport(void)

- ea: `0x140088428`
- end: `0x140088a8b`
- name: `?DoTdxVpStateImport@WorkerTaskMigrationTarget@@AEAAJXZ`
- size: `1635`
- prototype: `__int64 __fastcall(WorkerTaskMigrationTarget *__hidden this)`
- caller_count: `1`
- callee_count: `30`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x14008f9d0`

## callees

- `0x14002ecf0`
- `0x140031ca8`
- `0x14005342c`
- `0x14005b648`
- `0x14005e804`
- `0x14006af58`
- `0x14006fee8`
- `0x14007a74c`
- `0x14007aac0`
- `0x140081798`
- `0x140088374`
- `0x140088428`
- `0x140089724`
- `0x1400897f8`
- `0x14008b2f4`
- `0x14008f2a8`
- `0x140090674`
- `0x1400906a0`
- `0x1400b2728`
- `0x1400c25d0`
- `0x1400c2600`
- `0x1400ce7e4`
- `0x1400ce8a4`
- `0x1400fe1dc`
- `0x140132960`
- `0x14013361c`
- `0x140135955`
- `0x1401dd4f4`
- `0x14021e7ac`
- `0x1402c2010`

## import_xrefs

- `vid!VidTdxImportVpState` at `0x14008893a`
- `vid!VidTdxImportVpState` at `0x14008893a`

## string_xrefs

- `0x14008859c`: `onecore\vm\worker\migration\workertaskmigrationtarget.cpp`
- `0x140088647`: `onecore\vm\worker\migration\workertaskmigrationtarget.cpp`
- `0x140088682`: `onecore\vm\worker\migration\workertaskmigrationtarget.cpp`
- `0x14008870b`: `onecore\vm\worker\migration\workertaskmigrationtarget.cpp`
- `0x140088746`: `onecore\vm\worker\migration\workertaskmigrationtarget.cpp`
- `0x1400887e2`: `onecore\vm\worker\migration\workertaskmigrationtarget.cpp`
- `0x14008886f`: `onecore\vm\worker\migration\workertaskmigrationtarget.cpp`
- `0x1400888a8`: `onecore\vm\worker\migration\workertaskmigrationtarget.cpp`
- `0x140088952`: `onecore\vm\worker\migration\workertaskmigrationtarget.cpp`
- `0x1400889b6`: `onecore\vm\worker\migration\workertaskmigrationtarget.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall WorkerTaskMigrationTarget::DoTdxVpStateImport(WorkerTaskMigrationTarget *this)
{
  unsigned __int64 v2; // r15
  char *v3; // r12
  const struct _GUID *v4; // rsi
  const unsigned __int16 *v5; // rdi
  __int64 v6; // rbx
  int v7; // eax
  int v8; // eax
  char *v9; // rbx
  int v10; // eax
  __int64 v11; // rdi
  unsigned __int64 i; // rsi
  _QWORD *v13; // rbx
  char v14; // al
  __int64 v15; // r9
  __int64 v16; // r13
  __int64 v17; // rax
  const char *v18; // r9
  int v19; // eax
  const struct Vml::ExceptionTraceParameters *v20; // r8
  unsigned int v21; // r13d
  const struct _GUID *v22; // rdi
  const unsigned __int16 *v23; // rbx
  int v25; // [rsp+20h] [rbp-3F8h]
  int v26; // [rsp+20h] [rbp-3F8h]
  char *v27; // [rsp+30h] [rbp-3E8h] BYREF
  unsigned __int64 VmName; // [rsp+38h] [rbp-3E0h] BYREF
  __int64 v29; // [rsp+40h] [rbp-3D8h] BYREF
  unsigned __int64 v30; // [rsp+48h] [rbp-3D0h]
  struct _GUID v31; // [rsp+50h] [rbp-3C8h] BYREF
  _BYTE v32[16]; // [rsp+60h] [rbp-3B8h] BYREF
  _BYTE v33[336]; // [rsp+70h] [rbp-3A8h] BYREF
  void *Src[2]; // [rsp+1C0h] [rbp-258h] BYREF
  _BYTE v35[5]; // [rsp+1D0h] [rbp-248h] BYREF
  __int16 v36; // [rsp+1D5h] [rbp-243h]
  char v37; // [rsp+1D7h] [rbp-241h]
  __int64 v38; // [rsp+1D8h] [rbp-240h]
  __int64 v39; // [rsp+1E0h] [rbp-238h]
  char v40; // [rsp+1E8h] [rbp-230h]
  int v41; // [rsp+1E9h] [rbp-22Fh]
  __int16 v42; // [rsp+1EDh] [rbp-22Bh]
  char v43; // [rsp+1EFh] [rbp-229h]
  __int128 v44; // [rsp+1F0h] [rbp-228h] BYREF
  unsigned __int8 *v45[2]; // [rsp+200h] [rbp-218h] BYREF
  __int64 v46; // [rsp+210h] [rbp-208h]
  _BYTE v47[40]; // [rsp+220h] [rbp-1F8h] BYREF
  _BYTE v48[72]; // [rsp+248h] [rbp-1D0h] BYREF
  _QWORD v49[42]; // [rsp+290h] [rbp-188h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+418h] [rbp+0h]

  LODWORD(v27) = 0;
  v2 = 0;
  v30 = 0;
  v31 = 0;
  v3 = (char *)this + 16;
  v29 = (__int64)this + 16;
  Vml::VmPerfTraceOperation::VmPerfTraceOperation(
    (Vml::VmPerfTraceOperation *)v47,
    (struct Vml::VmPerfTraceComponent *)&g_MigrationPerfTrace,
    (const struct _GUID *)(*((_QWORD *)this + 2) + 1136LL),
    &v31);
  VmName = (unsigned __int64)VirtualMachine::GetVmName((VirtualMachine *)(*(_QWORD *)v3 + 16LL));
  Vml::VmPerfTraceOperation::BeginOperation<unsigned short const *>(
    (Vml::VmPerfTraceOperation *)v47,
    &VMWP_PERF_MIGRATION_TARGET_TDX_START_IMPORT_VP_STATES);
  memset_0(v49, 0, sizeof(v49));
  v4 = *(const struct _GUID **)v3;
  v5 = VirtualMachine::GetVmName((VirtualMachine *)(*(_QWORD *)v3 + 16LL));
  v6 = *(_QWORD *)(WorkerAsyncTask<VmWorkerTrace::TargetMigrationTask>::GetCurrentActivity(this, v33) + 272);
  memset_0(v49, 0, sizeof(v49));
  wil::ActivityBase<VmWorkerTrace,0,262144,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<VmWorkerTrace,0,262144,4,0,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v49);
  v49[0] = &VmWorkerTrace::MigrationTransferTdxVpState::`vftable';
  v27 = (char *)2;
  wil::ActivityBase<VmWorkerTrace,2,512,4,0,_TlgReflectorTag_Param0IsProviderType>::SetRelatedActivityId(v49, v6 + 8);
  VmWorkerTrace::MigrationTransferTdxVpState::StartActivity(
    (VmWorkerTrace::MigrationTransferTdxVpState *)v49,
    v4 + 71,
    v5);
  VmWorkerTrace::TargetMigrationTask::~TargetMigrationTask((VmWorkerTrace::TargetMigrationTask *)v33);
  v7 = VmMigrationConnection::BeginMessageSequence(*((_QWORD *)this + 55), 53);
  try
  {
    if ( v7 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xD71,
        (unsigned int)"onecore\\vm\\worker\\migration\\workertaskmigrationtarget.cpp",
        (const char *)(unsigned int)v7,
        v25);
    LODWORD(v27) = 0;
    do
    {
      Src[0] = 0;
      VmName = 0;
      v35[0] = -1;
      *(_DWORD *)&v35[1] = 0;
      v36 = 0;
      v37 = 0;
      v38 = 0;
      v39 = 0;
      v40 = 0;
      v41 = 0;
      v42 = 0;
      v43 = 0;
      v8 = VmMigrationConnection::ReceiveMessage(
             *((VmMigrationConnection **)this + 55),
             (unsigned __int64 *)Src,
             &VmName,
             (int *)&v27,
             (struct _SECURE_MIGRATION_CONTROL_DATA *)v35);
      if ( v8 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xD7D,
          (unsigned int)"onecore\\vm\\worker\\migration\\workertaskmigrationtarget.cpp",
          (const char *)(unsigned int)v8,
          v26);
      if ( v8 == 294977 )
      {
        LODWORD(v27) = 0;
        if ( !(unsigned int)VmMigrationConnection::GetAsyncSendError(
                              *((VmMigrationConnection **)this + 55),
                              (int *)&v27) )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0xD7E,
            (unsigned int)"onecore\\vm\\worker\\migration\\workertaskmigrationtarget.cpp",
            (const char *)0x8007054FLL,
            v26);
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xD7E,
          (unsigned int)"onecore\\vm\\worker\\migration\\workertaskmigrationtarget.cpp",
          (const char *)(unsigned int)v27,
          v26);
      }
      *(_OWORD *)v45 = 0;
      v46 = 0;
      v9 = (char *)Src[0];
      std::vector<enum gsl::byte>::vector<enum gsl::byte>(v45, Src[0]);
      v10 = VmMigrationConnection::ReceiveMessageData(
              *((VmMigrationConnection **)this + 55),
              v45[0],
              (unsigned __int64)v9,
              (struct _SECURE_MIGRATION_CONTROL_DATA *)v35);
      if ( v10 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xD84,
          (unsigned int)"onecore\\vm\\worker\\migration\\workertaskmigrationtarget.cpp",
          (const char *)(unsigned int)v10,
          v26);
      if ( v10 == 294977 )
      {
        LODWORD(v27) = 0;
        if ( !(unsigned int)VmMigrationConnection::GetAsyncSendError(
                              *((VmMigrationConnection **)this + 55),
                              (int *)&v27) )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0xD85,
            (unsigned int)"onecore\\vm\\worker\\migration\\workertaskmigrationtarget.cpp",
            (const char *)0x8007054FLL,
            v26);
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xD85,
          (unsigned int)"onecore\\vm\\worker\\migration\\workertaskmigrationtarget.cpp",
          (const char *)(unsigned int)v27,
          v26);
      }
      v44 = 0;
      gsl::span<unsigned char,-1>::span<unsigned char,-1>(v32, v45);
      gsl::span<enum gsl::byte const,-1>::subspan(v32, &v44, v39, &v9[-v39]);
      v11 = 0;
      for ( i = 0; i < VmName; ++i )
      {
        if ( v11 + 16 > (unsigned __int64)v44 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0xD8E,
            (unsigned int)"onecore\\vm\\worker\\migration\\workertaskmigrationtarget.cpp",
            (const char *)0x8007000DLL,
            v26);
        *(_OWORD *)Src = 0;
        gsl::span<enum gsl::byte const,-1>::subspan(&v44, Src, v11, 16);
        v13 = Src[1];
        v31 = *(struct _GUID *)Src;
        if ( (unsigned __int64)gsl::span<unsigned char,-1>::size_bytes(&v31) < 0x10 )
        {
          v13 = 0;
        }
        else
        {
          gsl::span<unsigned char,-1>::size_bytes(&v31);
          if ( v13 )
          {
            v14 = 0;
            goto LABEL_26;
          }
        }
        v14 = 1;
LABEL_26:
        if ( v14 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0xD92,
            (unsigned int)"onecore\\vm\\worker\\migration\\workertaskmigrationtarget.cpp",
            (const char *)0x8000FFFFLL,
            v26);
        v15 = v13[1];
        if ( v11 + v15 + 16 > (unsigned __int64)v44 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0xD94,
            (unsigned int)"onecore\\vm\\worker\\migration\\workertaskmigrationtarget.cpp",
            (const char *)0x8007000DLL,
            v26);
        *(_OWORD *)Src = 0;
        gsl::span<enum gsl::byte const,-1>::subspan(&v44, Src, v11 + 16, v15);
        memcpy_0(*(void **)(*((_QWORD *)this + 105) + 8LL), Src[1], v13[1]);
        v16 = v13[1];
        Src[0] = *(void **)(*((_QWORD *)this + 105) + 24LL);
        v17 = (**(__int64 (__fastcall ***)(__int64))(*(_QWORD *)(*(_QWORD *)v3 + 1024LL) + 24LL))(*(_QWORD *)(*(_QWORD *)v3 + 1024LL) + 24LL);
        if ( !(unsigned int)VidTdxImportVpState(v17, Src[0], 0, v16) )
          wil::details::in1diag3::Throw_GetLastError(
            retaddr,
            (void *)0xDA0,
            (unsigned int)"onecore\\vm\\worker\\migration\\workertaskmigrationtarget.cpp",
            v18);
        v11 += v13[1] + 16LL;
        v30 = ++v2;
      }
      std::vector<_VID_VSM_MBP_PERMISSIONS>::_Tidy(v45);
    }
    while ( !(_DWORD)v27 );
    v19 = VmMigrationConnection::AcknowledgeMessageSequence(*((VmMigrationConnection **)this + 55), 0, 0);
    if ( v19 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xDA8,
        (unsigned int)"onecore\\vm\\worker\\migration\\workertaskmigrationtarget.cpp",
        (const char *)(unsigned int)v19,
        v26);
  }
  catch ( ... )
  {
    HIDWORD(v27) = Vml::GetHResultFromThrownExceptionAndTrace((Vml *)0x41E2, (unsigned __int16)&off_1402DB430, v20);
    v2 = v30;
    v3 = (char *)v29;
  }
  v21 = HIDWORD(v27);
  v22 = *(const struct _GUID **)v3;
  v23 = VirtualMachine::GetVmName((VirtualMachine *)(*(_QWORD *)v3 + 16LL));
  wil::ActivityBase<VmWorkerTrace,0,262144,5,0,_TlgReflectorTag_Param0IsProviderType>::SetStopResult(v49, v21);
  VmWorkerTrace::MigrationTransferTdxVpState::Stop((VmWorkerTrace::MigrationTransferTdxVpState *)v49, v22 + 71, v23, v2);
  v29 = (__int64)VirtualMachine::GetVmName((VirtualMachine *)(*(_QWORD *)v3 + 16LL));
  Vml::VmPerfTraceOperation::EndOperation<unsigned short const *>(
    (Vml::VmPerfTraceOperation *)v47,
    &VMWP_PERF_MIGRATION_TARGET_TDX_STOP_IMPORT_VP_STATES,
    (__int64)&v29);
  VmWorkerTrace::MigrationTransferTdxVpState::~MigrationTransferTdxVpState((VmWorkerTrace::MigrationTransferTdxVpState *)v49);
  std::wstring::_Tidy_deallocate(v48);
  return v21;
}

```

## disassembly

```asm
0x140088428  mov     [rsp+arg_8], rbx
0x14008842d  mov     [rsp+arg_10], rsi
0x140088432  push    rdi
0x140088433  push    r12
0x140088435  push    r13
0x140088437  push    r14
0x140088439  push    r15
0x14008843b  sub     rsp, 3F0h
0x140088442  mov     rax, cs:__security_cookie
0x140088449  xor     rax, rsp
0x14008844c  mov     [rsp+418h+var_38], rax
0x140088454  mov     r14, rcx
0x140088457  mov     dword ptr [rsp+418h+var_3E8], 0
0x14008845f  xor     r15d, r15d
0x140088462  mov     [rsp+418h+var_3D0], r15
0x140088467  xorps   xmm0, xmm0
0x14008846a  movups  xmmword ptr [rsp+418h+var_3C8.Data1], xmm0
0x14008846f  lea     r12, [rcx+10h]
0x140088473  mov     [rsp+418h+var_3D8], r12
0x140088478  mov     r8, [r12]
0x14008847c  add     r8, 470h; struct _GUID *
0x140088483  lea     r9, [rsp+418h+var_3C8]; struct _GUID *
0x140088488  lea     rdx, ?g_MigrationPerfTrace@@3VVmPerfTraceComponent@Vml@@A; struct Vml::VmPerfTraceComponent *
0x14008848f  lea     rcx, [rsp+418h+var_1F8]; this
0x140088497  call    ??0VmPerfTraceOperation@Vml@@QEAA@AEAVVmPerfTraceComponent@1@AEBU_GUID@@1@Z; Vml::VmPerfTraceOperation::VmPerfTraceOperation(Vml::VmPerfTraceComponent &,_GUID const &,_GUID const &)
0x14008849c  nop
0x14008849d  mov     rcx, [r12]
0x1400884a1  add     rcx, 10h; this
0x1400884a5  call    ?GetVmName@VirtualMachine@@UEBAPEBGXZ; VirtualMachine::GetVmName(void)
0x1400884aa  mov     [rsp+418h+var_3E0], rax
0x1400884af  lea     r8, [rsp+418h+var_3E0]
0x1400884b4  lea     rdx, VMWP_PERF_MIGRATION_TARGET_TDX_START_IMPORT_VP_STATES; EventDescriptor
0x1400884bb  lea     rcx, [rsp+418h+var_1F8]; this
0x1400884c3  call    ??$BeginOperation@PEBG@VmPerfTraceOperation@Vml@@QEAAXAEBU_EVENT_DESCRIPTOR@@$$QEAPEBG@Z; Vml::VmPerfTraceOperation::BeginOperation<ushort const *>(_EVENT_DESCRIPTOR const &,ushort const * &&)
0x1400884c8  mov     r13d, 150h
0x1400884ce  mov     r8d, r13d; Size
0x1400884d1  xor     edx, edx; Val
0x1400884d3  lea     rcx, [rsp+418h+var_188]; void *
0x1400884db  call    memset_0
0x1400884e0  mov     rsi, [r12]
0x1400884e4  lea     rcx, [rsi+10h]; this
0x1400884e8  call    ?GetVmName@VirtualMachine@@UEBAPEBGXZ; VirtualMachine::GetVmName(void)
0x1400884ed  mov     rdi, rax
0x1400884f0  lea     rdx, [rsp+418h+var_3A8]
0x1400884f5  mov     rcx, r14
0x1400884f8  call    ?GetCurrentActivity@?$WorkerAsyncTask@VTargetMigrationTask@VmWorkerTrace@@@@IEAA?AVTargetMigrationTask@VmWorkerTrace@@XZ; WorkerAsyncTask<VmWorkerTrace::TargetMigrationTask>::GetCurrentActivity(void)
0x1400884fd  nop
0x1400884fe  mov     rbx, [rax+110h]
0x140088505  mov     r8d, r13d; Size
0x140088508  xor     edx, edx; Val
0x14008850a  lea     rcx, [rsp+418h+var_188]; void *
0x140088512  call    memset_0
0x140088517  lea     rdx, aMigrationtrans_6; "MigrationTransferTdxVpState"
0x14008851e  lea     rcx, [rsp+418h+var_188]; struct wil::details::IFailureCallback *
0x140088526  call    ??0?$ActivityBase@VVmWorkerTrace@@$0A@$0EAAAA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<VmWorkerTrace,0,262144,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<VmWorkerTrace,0,262144,4,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x14008852b  lea     rax, ??_7MigrationTransferTdxVpState@VmWorkerTrace@@6B@; const VmWorkerTrace::MigrationTransferTdxVpState::`vftable'
0x140088532  mov     [rsp+418h+var_188], rax
0x14008853a  mov     dword ptr [rsp+418h+var_3E8], 2
0x140088542  lea     rdx, [rbx+8]
0x140088546  lea     rcx, [rsp+418h+var_188]
0x14008854e  call    ?SetRelatedActivityId@?$ActivityBase@VVmWorkerTrace@@$01$0CAA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXAEBU_GUID@@@Z; wil::ActivityBase<VmWorkerTrace,2,512,4,0,_TlgReflectorTag_Param0IsProviderType>::SetRelatedActivityId(_GUID const &)
0x140088553  lea     rdx, [rsi+470h]; struct _GUID *
0x14008855a  mov     r8, rdi; unsigned __int16 *
0x14008855d  lea     rcx, [rsp+418h+var_188]; this
0x140088565  call    ?StartActivity@MigrationTransferTdxVpState@VmWorkerTrace@@QEAAXAEBU_GUID@@PEBG@Z; VmWorkerTrace::MigrationTransferTdxVpState::StartActivity(_GUID const &,ushort const *)
0x14008856a  nop
0x14008856b  lea     rcx, [rsp+418h+var_3A8]; this
0x140088570  call    ??1TargetMigrationTask@VmWorkerTrace@@QEAA@XZ; VmWorkerTrace::TargetMigrationTask::~TargetMigrationTask(void)
0x140088575  xor     r13d, r13d
0x140088578  mov     dword ptr [rsp+418h+var_3E8+4], r13d
0x14008857d  lea     edx, [r15+35h]
0x140088581  mov     rcx, [r14+1B8h]
0x140088588  call    ?BeginMessageSequence@VmMigrationConnection@@QEAAJW4MESSAGE_SEQUENCE_TYPE@1@@Z; VmMigrationConnection::BeginMessageSequence(VmMigrationConnection::MESSAGE_SEQUENCE_TYPE)
0x14008858d  mov     rcx, [rsp+418h]; this
0x140088595  test    eax, eax
0x140088597  jns     short loc_1400885AD
0x140088599  mov     r9d, eax; char *
0x14008859c  lea     r8, aOnecoreVmWorke_89; "onecore\\vm\\worker\\migration\\workert"...
0x1400885a3  mov     edx, 0D71h; void *
0x1400885a8  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1400885ad  mov     dword ptr [rsp+418h+var_3E8], r13d
0x1400885b2  mov     [rsp+418h+Src], r13
0x1400885ba  mov     [rsp+418h+var_3E0], r13
0x1400885bf  mov     [rsp+418h+var_248], 0FFh
0x1400885c7  xor     eax, eax
0x1400885c9  mov     dword ptr [rsp+418h+var_248+1], eax
0x1400885d0  mov     [rsp+418h+var_243], ax
0x1400885d8  mov     [rsp+418h+var_241], al
0x1400885df  mov     [rsp+418h+var_240], r13
0x1400885e7  mov     [rsp+418h+var_238], r13
0x1400885ef  mov     [rsp+418h+var_230], r13b
0x1400885f7  mov     [rsp+418h+var_22F], eax
0x1400885fe  mov     [rsp+418h+var_22B], ax
0x140088606  mov     [rsp+418h+var_229], al
0x14008860d  lea     rax, [rsp+418h+var_248]
0x140088615  mov     qword ptr [rsp+418h+var_3F8], rax; int
0x14008861a  lea     r9, [rsp+418h+var_3E8]; int *
0x14008861f  lea     r8, [rsp+418h+var_3E0]; unsigned __int64 *
0x140088624  lea     rdx, [rsp+418h+Src]; unsigned __int64 *
0x14008862c  mov     rcx, [r14+1B8h]; this
0x140088633  call    ?ReceiveMessage@VmMigrationConnection@@QEAAJAEA_K0AEAHAEAU_SECURE_MIGRATION_CONTROL_DATA@@@Z; VmMigrationConnection::ReceiveMessage(unsigned __int64 &,unsigned __int64 &,int &,_SECURE_MIGRATION_CONTROL_DATA &)
0x140088638  mov     rcx, [rsp+418h]; this
0x140088640  test    eax, eax
0x140088642  jns     short loc_140088658
0x140088644  mov     r9d, eax; char *
0x140088647  lea     r8, aOnecoreVmWorke_89; "onecore\\vm\\worker\\migration\\workert"...
0x14008864e  mov     edx, 0D7Dh; void *
0x140088653  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140088658  cmp     eax, 48041h
0x14008865d  jnz     short loc_1400886AF
0x14008865f  mov     dword ptr [rsp+418h+var_3E8], r13d
0x140088664  lea     rdx, [rsp+418h+var_3E8]; int *
0x140088669  mov     rcx, [r14+1B8h]; this
0x140088670  call    ?GetAsyncSendError@VmMigrationConnection@@QEAAHAEAJ@Z; VmMigrationConnection::GetAsyncSendError(long &)
0x140088675  test    eax, eax
0x140088677  setz    al
0x14008867a  mov     rcx, [rsp+418h]; this
0x140088682  lea     r8, aOnecoreVmWorke_89; "onecore\\vm\\worker\\migration\\workert"...
0x140088689  mov     edx, 0D7Eh; void *
0x14008868e  test    al, al
0x140088690  jz      short loc_14008869D
0x140088692  mov     r9d, 8007054Fh; char *
0x140088698  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14008869d  mov     rcx, [rsp+418h]; this
0x1400886a5  mov     r9d, dword ptr [rsp+418h+var_3E8]; char *
0x1400886aa  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1400886af  xorps   xmm0, xmm0
0x1400886b2  xor     eax, eax
0x1400886b4  movups  xmmword ptr [rsp+418h+var_218], xmm0
0x1400886bc  mov     [rsp+418h+var_208], rax
0x1400886c4  mov     rbx, [rsp+418h+Src]
0x1400886cc  mov     rdx, rbx
0x1400886cf  lea     rcx, [rsp+418h+var_218]
0x1400886d7  call    ??0?$vector@W4byte@gsl@@V?$allocator@W4byte@gsl@@@std@@@std@@QEAA@_KAEBV?$allocator@W4byte@gsl@@@1@@Z; std::vector<gsl::byte>::vector<gsl::byte>(unsigned __int64,std::allocator<gsl::byte> const &)
0x1400886dc  nop
0x1400886dd  lea     r9, [rsp+418h+var_248]; struct _SECURE_MIGRATION_CONTROL_DATA *
0x1400886e5  mov     r8, rbx; unsigned __int64
0x1400886e8  mov     rdx, [rsp+418h+var_218]; unsigned __int8 *
0x1400886f0  mov     rcx, [r14+1B8h]; this
0x1400886f7  call    ?ReceiveMessageData@VmMigrationConnection@@QEAAJPEAE_KAEAU_SECURE_MIGRATION_CONTROL_DATA@@@Z; VmMigrationConnection::ReceiveMessageData(uchar *,unsigned __int64,_SECURE_MIGRATION_CONTROL_DATA &)
0x1400886fc  mov     rcx, [rsp+418h]; this
0x140088704  test    eax, eax
0x140088706  jns     short loc_14008871C
0x140088708  mov     r9d, eax; char *
0x14008870b  lea     r8, aOnecoreVmWorke_89; "onecore\\vm\\worker\\migration\\workert"...
0x140088712  mov     edx, 0D84h; void *
0x140088717  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14008871c  cmp     eax, 48041h
0x140088721  jnz     short loc_140088773
0x140088723  mov     dword ptr [rsp+418h+var_3E8], r13d
0x140088728  lea     rdx, [rsp+418h+var_3E8]; int *
0x14008872d  mov     rcx, [r14+1B8h]; this
0x140088734  call    ?GetAsyncSendError@VmMigrationConnection@@QEAAHAEAJ@Z; VmMigrationConnection::GetAsyncSendError(long &)
0x140088739  test    eax, eax
0x14008873b  setz    al
0x14008873e  mov     rcx, [rsp+418h]; this
0x140088746  lea     r8, aOnecoreVmWorke_89; "onecore\\vm\\worker\\migration\\workert"...
0x14008874d  mov     edx, 0D85h; void *
0x140088752  test    al, al
0x140088754  jz      short loc_140088761
0x140088756  mov     r9d, 8007054Fh; char *
0x14008875c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140088761  mov     rcx, [rsp+418h]; this
0x140088769  mov     r9d, dword ptr [rsp+418h+var_3E8]; char *
0x14008876e  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140088773  xorps   xmm0, xmm0
0x140088776  movups  [rsp+418h+var_228], xmm0
0x14008877e  lea     rdx, [rsp+418h+var_218]
0x140088786  lea     rcx, [rsp+418h+var_3B8]
0x14008878b  call    ??$?0$0?0V?$vector@EV?$allocator@E@std@@@std@@$0A@@?$span@E$0?0@gsl@@QEAA@AEAV?$vector@EV?$allocator@E@std@@@std@@@Z; gsl::span<uchar,-1>::span<uchar,-1>(std::vector<uchar> &)
0x140088790  mov     r8, [rsp+418h+var_238]
0x140088798  sub     rbx, r8
0x14008879b  mov     r9, rbx
0x14008879e  lea     rdx, [rsp+418h+var_228]
0x1400887a6  lea     rcx, [rsp+418h+var_3B8]
0x1400887ab  call    ?subspan@?$span@$$CBW4byte@gsl@@$0?0@gsl@@QEBA?AV12@_K0@Z; gsl::span<gsl::byte const,-1>::subspan(unsigned __int64,unsigned __int64)
0x1400887b0  mov     rdi, r13
0x1400887b3  mov     rsi, r13
0x1400887b6  cmp     rsi, [rsp+418h+var_3E0]
0x1400887bb  jnb     loc_14008897B
0x1400887c1  lea     r13, [rdi+10h]
0x1400887c5  cmp     r13, qword ptr [rsp+418h+var_228]
0x1400887cd  setnbe  al
0x1400887d0  mov     rcx, [rsp+418h]; this
0x1400887d8  test    al, al
0x1400887da  jz      short loc_1400887F3
0x1400887dc  mov     r9d, 8007000Dh; char *
0x1400887e2  lea     r8, aOnecoreVmWorke_89; "onecore\\vm\\worker\\migration\\workert"...
0x1400887e9  mov     edx, 0D8Eh; void *
0x1400887ee  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1400887f3  xorps   xmm0, xmm0
0x1400887f6  movups  xmmword ptr [rsp+418h+Src], xmm0
0x1400887fe  mov     r9d, 10h
0x140088804  mov     r8, rdi
0x140088807  lea     rdx, [rsp+418h+Src]
0x14008880f  lea     rcx, [rsp+418h+var_228]
0x140088817  call    ?subspan@?$span@$$CBW4byte@gsl@@$0?0@gsl@@QEBA?AV12@_K0@Z; gsl::span<gsl::byte const,-1>::subspan(unsigned __int64,unsigned __int64)
0x14008881c  mov     rbx, [rsp+418h+Src+8]
0x140088824  mov     rax, [rsp+418h+Src]
0x14008882c  mov     qword ptr [rsp+418h+var_3C8.Data1], rax
0x140088831  mov     qword ptr [rsp+418h+var_3C8.Data4], rbx
0x140088836  lea     rcx, [rsp+418h+var_3C8]
0x14008883b  call    ?size_bytes@?$span@E$0?0@gsl@@QEBA_KXZ; gsl::span<uchar,-1>::size_bytes(void)
0x140088840  cmp     rax, 10h
0x140088844  jb      short loc_140088859
0x140088846  lea     rcx, [rsp+418h+var_3C8]
0x14008884b  call    ?size_bytes@?$span@E$0?0@gsl@@QEBA_KXZ; gsl::span<uchar,-1>::size_bytes(void)
0x140088850  test    rbx, rbx
0x140088853  jz      short loc_14008885B
0x140088855  xor     al, al
0x140088857  jmp     short loc_14008885D
0x140088859  xor     ebx, ebx
0x14008885b  mov     al, 1
0x14008885d  mov     rcx, [rsp+418h]; this
0x140088865  test    al, al
0x140088867  jz      short loc_140088880
0x140088869  mov     r9d, 8000FFFFh; char *
0x14008886f  lea     r8, aOnecoreVmWorke_89; "onecore\\vm\\worker\\migration\\workert"...
0x140088876  mov     edx, 0D92h; void *
0x14008887b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140088880  mov     r9, [rbx+8]
0x140088884  lea     rax, [r9+10h]
0x140088888  add     rax, rdi
0x14008888b  cmp     rax, qword ptr [rsp+418h+var_228]
0x140088893  setnbe  al
0x140088896  mov     rcx, [rsp+418h]; this
0x14008889e  test    al, al
0x1400888a0  jz      short loc_1400888B9
0x1400888a2  mov     r9d, 8007000Dh; char *
0x1400888a8  lea     r8, aOnecoreVmWorke_89; "onecore\\vm\\worker\\migration\\workert"...
0x1400888af  mov     edx, 0D94h; void *
0x1400888b4  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1400888b9  xorps   xmm0, xmm0
0x1400888bc  movups  xmmword ptr [rsp+418h+Src], xmm0
0x1400888c4  mov     r8, r13
0x1400888c7  lea     rdx, [rsp+418h+Src]
0x1400888cf  lea     rcx, [rsp+418h+var_228]
0x1400888d7  call    ?subspan@?$span@$$CBW4byte@gsl@@$0?0@gsl@@QEBA?AV12@_K0@Z; gsl::span<gsl::byte const,-1>::subspan(unsigned __int64,unsigned __int64)
0x1400888dc  mov     rcx, [r14+348h]
0x1400888e3  mov     r8, [rbx+8]; Size
0x1400888e7  mov     rdx, [rsp+418h+Src+8]; Src
0x1400888ef  mov     rcx, [rcx+8]; void *
0x1400888f3  call    memcpy_0
0x1400888f8  mov     r13, [rbx+8]
0x1400888fc  mov     rax, [r14+348h]
0x140088903  mov     rax, [rax+18h]
0x140088907  mov     [rsp+418h+Src], rax
0x14008890f  mov     rax, [r12]
0x140088913  mov     rcx, [rax+400h]
0x14008891a  add     rcx, 18h
0x14008891e  mov     rax, [rcx]
0x140088921  mov     rax, [rax]
0x140088924  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140088929  xor     r8d, r8d
0x14008892c  mov     r9, r13
0x14008892f  mov     rdx, [rsp+418h+Src]
0x140088937  mov     rcx, rax
0x14008893a  call    cs:__imp_VidTdxImportVpState
0x140088941  nop     dword ptr [rax+rax+00h]
0x140088946  mov     rcx, [rsp+418h]; this
0x14008894e  test    eax, eax
0x140088950  jnz     short loc_140088963
0x140088952  lea     r8, aOnecoreVmWorke_89; "onecore\\vm\\worker\\migration\\workert"...
0x140088959  mov     edx, 0DA0h; void *
0x14008895e  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x140088963  add     rdi, 10h
0x140088967  add     rdi, [rbx+8]
0x14008896b  inc     r15
0x14008896e  mov     [rsp+418h+var_3D0], r15
0x140088973  inc     rsi
0x140088976  jmp     loc_1400887B6
0x14008897b  lea     rcx, [rsp+418h+var_218]
0x140088983  call    ?_Tidy@?$vector@T_VID_VSM_MBP_PERMISSIONS@@V?$allocator@T_VID_VSM_MBP_PERMISSIONS@@@std@@@std@@AEAAXXZ; std::vector<_VID_VSM_MBP_PERMISSIONS>::_Tidy(void)
0x140088988  xor     r13d, r13d
0x14008898b  cmp     dword ptr [rsp+418h+var_3E8], r13d
0x140088990  jz      loc_1400885B2
0x140088996  xor     r8d, r8d; unsigned __int64
0x140088999  xor     edx, edx; struct VmMigrationNetworkBuffer *
0x14008899b  mov     rcx, [r14+1B8h]; this
0x1400889a2  call    ?AcknowledgeMessageSequence@VmMigrationConnection@@QEAAJPEBVVmMigrationNetworkBuffer@@_K@Z; VmMigrationConnection::AcknowledgeMessageSequence(VmMigrationNetworkBuffer const *,unsigned __int64)
0x1400889a7  mov     rcx, [rsp+418h]; this
0x1400889af  test    eax, eax
0x1400889b1  jns     short loc_1400889C8
0x1400889b3  mov     r9d, eax; char *
0x1400889b6  lea     r8, aOnecoreVmWorke_89; "onecore\\vm\\worker\\migration\\workert"...
0x1400889bd  mov     edx, 0DA8h; void *
0x1400889c2  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1400889c8  jmp     short loc_1400889D4
0x1400889ca  mov     r15, [rsp+418h+var_3D0]
0x1400889cf  mov     r12, [rsp+418h+var_3D8]
0x1400889d4  mov     r13d, dword ptr [rsp+418h+var_3E8+4]
0x1400889d9  mov     rdi, [r12]
0x1400889dd  lea     rcx, [rdi+10h]; this
0x1400889e1  call    ?GetVmName@VirtualMachine@@UEBAPEBGXZ; VirtualMachine::GetVmName(void)
0x1400889e6  mov     rbx, rax
0x1400889e9  mov     edx, r13d
0x1400889ec  lea     rcx, [rsp+418h+var_188]
0x1400889f4  call    ?SetStopResult@?$ActivityBase@VVmWorkerTrace@@$0A@$0EAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXJPEAJ@Z; wil::ActivityBase<VmWorkerTrace,0,262144,5,0,_TlgReflectorTag_Param0IsProviderType>::SetStopResult(long,long *)
0x1400889f9  lea     rdx, [rdi+470h]; struct _GUID *
0x140088a00  mov     r9, r15; unsigned __int64
  ... truncated ...
```
