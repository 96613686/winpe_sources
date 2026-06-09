# ComputeService::Management::VmmsDetails::StartWorkerProcess(std::shared_ptr<ComputeService::Management::ComputeSystem> const &,IVmInitializationContext *,ComputeService::Management::VirtualMachineConfiguration const *,ComputeService::Management::VirtualMachineState *,IVmHandleBrokerManager *,Vml::VmReferencePtr<HyperVRepository,Vml::VmUserReferenceTraits>)

- ea: `0x1401dfa44`
- end: `0x1401dfcbb`
- name: `?StartWorkerProcess@VmmsDetails@Management@ComputeService@@YAXAEBV?$shared_ptr@VComputeSystem@Management@ComputeService@@@std@@PEAUIVmInitializationContext@@PEBUVirtualMachineConfiguration@23@PEAUVirtualMachineState@23@PEAUIVmHandleBrokerManager@@V?$VmReferencePtr@VHyperVRepository@@VVmUserReferenceTraits@Vml@@@Vml@@@Z`
- size: `631`
- prototype: ``
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1401de020`

## callees

- `0x140024000`
- `0x14005a600`
- `0x140067860`
- `0x14007f03c`
- `0x14007fed4`
- `0x14007ff94`
- `0x14007ffbc`
- `0x140080124`
- `0x140080180`
- `0x1400b4cc8`
- `0x1400b5288`
- `0x1400c40e0`
- `0x1401332f0`
- `0x1401b1d4c`
- `0x1401dbeb4`
- `0x1401dfa44`
- `0x140242a40`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x1401dfaec`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x1401dfaec`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x1401dfbfd`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x1401dfbfd`
- `RPCRT4!UuidFromStringW` at `0x1401dfaa1`
- `RPCRT4!UuidFromStringW` at `0x1401dfaa1`

## string_xrefs

- `0x1401dfac5`: `onecore\vm\compute\management\orchestration\vmmsvirtualmachine\vmmsvirtualmachineorchestrator.cpp`
- `0x1401dfb12`: `onecore\vm\compute\management\orchestration\vmmsvirtualmachine\vmmsvirtualmachineorchestrator.cpp`
- `0x1401dfb51`: `onecore\vm\compute\management\orchestration\vmmsvirtualmachine\vmmsvirtualmachineorchestrator.cpp`
- `0x1401dfb6e`: `/configuration/security/settings/appcontainer_launch_opt_out`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall ComputeService::Management::VmmsDetails::StartWorkerProcess(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        HyperVRepository **a6)
{
  unsigned __int16 *v10; // rcx
  PTP_WAIT ThreadpoolWait; // rax
  const char *v13; // r9
  int v14; // eax
  __int64 started; // rax
  const struct VmInitParameters *v16; // r8
  __int64 v17; // rax
  __int64 v18; // rax
  int v20; // [rsp+20h] [rbp-89h]
  unsigned int *v21; // [rsp+20h] [rbp-89h]
  unsigned int v22[2]; // [rsp+30h] [rbp-79h] BYREF
  HyperVRepository **v23; // [rsp+38h] [rbp-71h]
  char v24; // [rsp+40h] [rbp-69h]
  _BYTE v25[40]; // [rsp+48h] [rbp-61h] BYREF
  _QWORD v26[3]; // [rsp+70h] [rbp-39h] BYREF
  int v27; // [rsp+88h] [rbp-21h] BYREF
  UUID Uuid; // [rsp+90h] [rbp-19h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+4Fh]

  v26[2] = a6;
  Uuid = 0;
  v10 = (unsigned __int16 *)(a3 + 8);
  if ( *(_QWORD *)(a3 + 32) > 7u )
    v10 = *(unsigned __int16 **)v10;
  if ( !v10 || UuidFromStringW(v10, &Uuid) )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x17D,
      (unsigned int)"onecore\\vm\\compute\\management\\orchestration\\vmmsvirtualmachine\\vmmsvirtualmachineorchestrator.cpp",
      (const char *)0x8007000DLL,
      v20);
  ThreadpoolWait = CreateThreadpoolWait(
                     ComputeService::Management::VmmsDetails::OnWorkerProcessExit,
                     (PVOID)(a4 + 72),
                     0);
  wil::details::unique_storage<wil::details::resource_policy<_TP_WAIT *,void (*)(_TP_WAIT *),&void CloseThreadpoolWait(_TP_WAIT *),wistd::integral_constant<unsigned __int64,0>,_TP_WAIT *,_TP_WAIT *,0,std::nullptr_t>>::reset(
    a4 + 664,
    ThreadpoolWait);
  if ( !*(_QWORD *)(a4 + 664) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x184,
      (unsigned int)"onecore\\vm\\compute\\management\\orchestration\\vmmsvirtualmachine\\vmmsvirtualmachineorchestrator.cpp",
      v13);
  v22[0] = *(_BYTE *)(a4 + 1748) != 0;
  v23 = a6;
  v24 = 1;
  v14 = HyperVRepository::Lock(*a6, 0);
  if ( v14 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x197,
      (unsigned int)"onecore\\vm\\compute\\management\\orchestration\\vmmsvirtualmachine\\vmmsvirtualmachineorchestrator.cpp",
      (const char *)(unsigned int)v14,
      v20);
  v27 = 0;
  if ( (unsigned int)HyperVRepository::ReadBoolean(
                       *a6,
                       L"/configuration/security/settings/appcontainer_launch_opt_out",
                       &v27)
    || (v22[1] = 1, !v27) )
  {
    v22[1] = 0;
  }
  HyperVRepository::Unlock(*a6);
  started = ComputeService::Vmwp::StartWorkerProcess(v25, &Uuid, *(_QWORD *)(a3 + 4344), *(_QWORD *)(a4 + 816));
  ComputeService::Vmwp::WorkerProcessContext::operator=(a4 + 624, started);
  ComputeService::Vmwp::WorkerProcessContext::~WorkerProcessContext((ComputeService::Vmwp::WorkerProcessContext *)v25);
  v26[0] = a2;
  v26[1] = a5;
  ComputeService::Vmwp::InitializeWorkerProcess(
    (ComputeService::Vmwp *)(a4 + 624),
    (const struct ComputeService::Vmwp::WorkerProcessContext *)v26,
    v16);
  SetThreadpoolWait(*(PTP_WAIT *)(a4 + 664), *(HANDLE *)(a4 + 648), 0);
  *(_QWORD *)v22 = ComputeService::Management::VmmsDetails::OnGuestCrash;
  v17 = Vml::VmComMultiInstanceObject<ComputeService::VmCommonHelpers::VirtualMachineWorkerProcessGuestCrashEventSink>::CreateInstance<std::shared_ptr<ComputeService::Management::ComputeSystem> const &,void (*)(std::shared_ptr<ComputeService::Management::ComputeSystem> const &,_GUEST_CRASH_INFO const *)>(
          a1,
          v22);
  Vml::VmComPtr<IStream>::Attach<Vml::VmComFixedMemStream>(a4 + 672, v17);
  Vml::VmComEventConnect(
    *(Vml **)(a4 + 640),
    (struct IUnknown *)&IID_IVmGuestCrashEvents,
    *(const struct _GUID **)(a4 + 672),
    (struct IUnknown *)(a4 + 680),
    v22);
  v27 = 1;
  v18 = Vml::VmComMultiInstanceObject<ComputeService::UtilityVm::WorkerProcessEventSink>::CreateInstance<std::shared_ptr<ComputeService::Management::ComputeSystem> const &,enum ComputeService::UtilityVm::WorkerEventSinkNotificationType>(
          a1,
          &v27);
  Vml::VmComPtr<IStream>::Attach<Vml::VmComFixedMemStream>(a4 + 688, v18);
  Vml::VmComEventConnect(
    *(Vml **)(a4 + 640),
    (struct IUnknown *)&IID_IVmVirtualMachineEvents,
    *(const struct _GUID **)(a4 + 688),
    (struct IUnknown *)(a4 + 696),
    v21);
  return Vml::VmReferencePtr<VmRepository,Vml::VmUserReferenceTraits>::~VmReferencePtr<VmRepository,Vml::VmUserReferenceTraits>(a6);
}

```

## disassembly

```asm
0x1401dfa44  push    rbp
0x1401dfa46  push    rbx
0x1401dfa47  push    rsi
0x1401dfa48  push    rdi
0x1401dfa49  push    r12
0x1401dfa4b  push    r13
0x1401dfa4d  push    r14
0x1401dfa4f  push    r15
0x1401dfa51  lea     rbp, [rsp-0Fh]
0x1401dfa56  sub     rsp, 0B8h
0x1401dfa5d  mov     rax, cs:__security_cookie
0x1401dfa64  xor     rax, rsp
0x1401dfa67  mov     [rbp+47h+var_50], rax
0x1401dfa6b  mov     rsi, r9
0x1401dfa6e  mov     rbx, r8
0x1401dfa71  mov     r12, rdx
0x1401dfa74  mov     r15, rcx
0x1401dfa77  mov     r13, [rbp+47h+arg_20]
0x1401dfa7b  mov     rdi, [rbp+47h+arg_28]
0x1401dfa7f  mov     [rbp+47h+var_70], rdi
0x1401dfa83  xorps   xmm0, xmm0
0x1401dfa86  movups  xmmword ptr [rbp+47h+Uuid.Data1], xmm0
0x1401dfa8a  lea     rcx, [r8+8]
0x1401dfa8e  cmp     qword ptr [rcx+18h], 7
0x1401dfa93  jbe     short loc_1401DFA98
0x1401dfa95  mov     rcx, [rcx]; StringUuid
0x1401dfa98  test    rcx, rcx
0x1401dfa9b  jz      short loc_1401DFAB5
0x1401dfa9d  lea     rdx, [rbp+47h+Uuid]; Uuid
0x1401dfaa1  call    cs:__imp_UuidFromStringW
0x1401dfaa8  nop     dword ptr [rax+rax+00h]
0x1401dfaad  test    eax, eax
0x1401dfaaf  jnz     short loc_1401DFAB5
0x1401dfab1  mov     al, 1
0x1401dfab3  jmp     short loc_1401DFAB7
0x1401dfab5  xor     al, al
0x1401dfab7  mov     rcx, [rbp+4Fh]; this
0x1401dfabb  test    al, al
0x1401dfabd  jnz     short loc_1401DFAD7
0x1401dfabf  mov     r9d, 8007000Dh; char *
0x1401dfac5  lea     r8, aOnecoreVmCompu_43; "onecore\\vm\\compute\\management\\orche"...
0x1401dfacc  mov     edx, 17Dh; void *
0x1401dfad1  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1401dfad7  lea     r14, [rsi+298h]
0x1401dfade  lea     rdx, [rsi+48h]; pv
0x1401dfae2  xor     r8d, r8d; pcbe
0x1401dfae5  lea     rcx, ?OnWorkerProcessExit@VmmsDetails@Management@ComputeService@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@Z; pfnwa
0x1401dfaec  call    cs:__imp_CreateThreadpoolWait
0x1401dfaf3  nop     dword ptr [rax+rax+00h]
0x1401dfaf8  mov     rdx, rax
0x1401dfafb  mov     rcx, r14
0x1401dfafe  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_WAIT@@P6AXPEAU1@@Z$1?CloseThreadpoolWait@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_WAIT@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_WAIT *,void (*)(_TP_WAIT *),&CloseThreadpoolWait(_TP_WAIT *),wistd::integral_constant<unsigned __int64,0>,_TP_WAIT *,_TP_WAIT *,0,std::nullptr_t>>::reset(_TP_WAIT *)
0x1401dfb03  cmp     qword ptr [r14], 0
0x1401dfb07  setz    al
0x1401dfb0a  mov     rcx, [rbp+4Fh]; this
0x1401dfb0e  test    al, al
0x1401dfb10  jz      short loc_1401DFB24
0x1401dfb12  lea     r8, aOnecoreVmCompu_43; "onecore\\vm\\compute\\management\\orche"...
0x1401dfb19  mov     edx, 184h; void *
0x1401dfb1e  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1401dfb24  xor     eax, eax
0x1401dfb26  cmp     [rsi+6D4h], al
0x1401dfb2c  lea     ecx, [rax+1]
0x1401dfb2f  cmovnz  eax, ecx
0x1401dfb32  mov     [rbp+47h+var_C0], eax
0x1401dfb35  mov     [rbp+47h+var_B8], rdi
0x1401dfb39  mov     [rbp+47h+var_B0], cl
0x1401dfb3c  xor     edx, edx
0x1401dfb3e  mov     rcx, [rdi]
0x1401dfb41  call    ?Lock@HyperVRepository@@UEAAJW4VmRepositoryLockFlags@@@Z; HyperVRepository::Lock(VmRepositoryLockFlags)
0x1401dfb46  mov     rcx, [rbp+4Fh]; this
0x1401dfb4a  test    eax, eax
0x1401dfb4c  jns     short loc_1401DFB63
0x1401dfb4e  mov     r9d, eax; char *
0x1401dfb51  lea     r8, aOnecoreVmCompu_43; "onecore\\vm\\compute\\management\\orche"...
0x1401dfb58  mov     edx, 197h; void *
0x1401dfb5d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1401dfb63  mov     [rbp+47h+var_68], 0
0x1401dfb6a  lea     r8, [rbp+47h+var_68]; int *
0x1401dfb6e  lea     rdx, ?SECURITY_SETTING_APPCONTAINER_LAUNCH_OPT_OUT@@3QBGB; "/configuration/security/settings/appcon"...
0x1401dfb75  mov     rcx, [rdi]; this
0x1401dfb78  call    ?ReadBoolean@HyperVRepository@@UEBAJPEBGAEAH@Z; HyperVRepository::ReadBoolean(ushort const *,int &)
0x1401dfb7d  test    eax, eax
0x1401dfb7f  jnz     short loc_1401DFB8D
0x1401dfb81  cmp     [rbp+47h+var_68], eax
0x1401dfb84  mov     [rbp+47h+var_C0+4], 1
0x1401dfb8b  jnz     short loc_1401DFB94
0x1401dfb8d  mov     [rbp+47h+var_C0+4], 0
0x1401dfb94  mov     rcx, [rdi]; this
0x1401dfb97  call    ?Unlock@HyperVRepository@@UEAAJXZ; HyperVRepository::Unlock(void)
0x1401dfb9c  nop
0x1401dfb9d  lea     rax, [rbp+47h+var_C0]
0x1401dfba1  mov     [rsp+0F0h+var_D0], rax; unsigned int *
0x1401dfba6  mov     r9, [rsi+330h]
0x1401dfbad  mov     r8, [rbx+10F8h]
0x1401dfbb4  lea     rdx, [rbp+47h+Uuid]
0x1401dfbb8  lea     rcx, [rbp+47h+var_A8]
0x1401dfbbc  call    ?StartWorkerProcess@Vmwp@ComputeService@@YA?AUWorkerProcessContext@12@AEBU_GUID@@PEAX1AEBUStartWorkerProcessContext@12@@Z; ComputeService::Vmwp::StartWorkerProcess(_GUID const &,void *,void *,ComputeService::Vmwp::StartWorkerProcessContext const &)
0x1401dfbc1  lea     rbx, [rsi+270h]
0x1401dfbc8  mov     rdx, rax
0x1401dfbcb  mov     rcx, rbx
0x1401dfbce  call    ??4WorkerProcessContext@Vmwp@ComputeService@@QEAAAEAU012@$$QEAU012@@Z; ComputeService::Vmwp::WorkerProcessContext::operator=(ComputeService::Vmwp::WorkerProcessContext &&)
0x1401dfbd3  lea     rcx, [rbp+47h+var_A8]; this
0x1401dfbd7  call    ??1WorkerProcessContext@Vmwp@ComputeService@@QEAA@XZ; ComputeService::Vmwp::WorkerProcessContext::~WorkerProcessContext(void)
0x1401dfbdc  mov     [rbp+47h+var_80], r12
0x1401dfbe0  mov     [rbp+47h+var_78], r13
0x1401dfbe4  lea     rdx, [rbp+47h+var_80]; struct ComputeService::Vmwp::WorkerProcessContext *
0x1401dfbe8  mov     rcx, rbx; this
0x1401dfbeb  call    ?InitializeWorkerProcess@Vmwp@ComputeService@@YAXAEBUWorkerProcessContext@12@AEBUVmInitParameters@@@Z; ComputeService::Vmwp::InitializeWorkerProcess(ComputeService::Vmwp::WorkerProcessContext const &,VmInitParameters const &)
0x1401dfbf0  xor     r8d, r8d; pftTimeout
0x1401dfbf3  mov     rdx, [rsi+288h]; h
0x1401dfbfa  mov     rcx, [r14]; pwa
0x1401dfbfd  call    cs:__imp_SetThreadpoolWait
0x1401dfc04  nop     dword ptr [rax+rax+00h]
0x1401dfc09  lea     rax, ?OnGuestCrash@VmmsDetails@Management@ComputeService@@YAXAEBV?$shared_ptr@VComputeSystem@Management@ComputeService@@@std@@PEBU_GUEST_CRASH_INFO@@@Z; ComputeService::Management::VmmsDetails::OnGuestCrash(std::shared_ptr<ComputeService::Management::ComputeSystem> const &,_GUEST_CRASH_INFO const *)
0x1401dfc10  mov     qword ptr [rbp+47h+var_C0], rax
0x1401dfc14  lea     rbx, [rsi+2A0h]
0x1401dfc1b  lea     rdx, [rbp+47h+var_C0]
0x1401dfc1f  mov     rcx, r15
0x1401dfc22  call    ??$CreateInstance@AEBV?$shared_ptr@VComputeSystem@Management@ComputeService@@@std@@P6AXAEBV12@PEBU_GUEST_CRASH_INFO@@@Z@?$VmComMultiInstanceObject@VVirtualMachineWorkerProcessGuestCrashEventSink@VmCommonHelpers@ComputeService@@@Vml@@SAPEAVVirtualMachineWorkerProcessGuestCrashEventSink@VmCommonHelpers@ComputeService@@AEBV?$shared_ptr@VComputeSystem@Management@ComputeService@@@std@@$$QEAP6AX0PEBU_GUEST_CRASH_INFO@@@Z@Z; Vml::VmComMultiInstanceObject<ComputeService::VmCommonHelpers::VirtualMachineWorkerProcessGuestCrashEventSink>::CreateInstance<std::shared_ptr<ComputeService::Management::ComputeSystem> const &,void (*)(std::shared_ptr<ComputeService::Management::ComputeSystem> const &,_GUEST_CRASH_INFO const *)>(std::shared_ptr<ComputeService::Management::ComputeSystem> const &,void (*&&)(std::shared_ptr<ComputeService::Management::ComputeSystem> const &,_GUEST_CRASH_INFO const *))
0x1401dfc27  mov     rdx, rax
0x1401dfc2a  mov     rcx, rbx
0x1401dfc2d  call    ??$Attach@VVmComFixedMemStream@Vml@@@?$VmComPtr@UIStream@@@Vml@@QEAAXPEAVVmComFixedMemStream@1@@Z; Vml::VmComPtr<IStream>::Attach<Vml::VmComFixedMemStream>(Vml::VmComFixedMemStream *)
0x1401dfc32  lea     r9, [rsi+2A8h]; struct IUnknown *
0x1401dfc39  mov     r8, [rbx]; struct _GUID *
0x1401dfc3c  lea     rdx, IID_IVmGuestCrashEvents; struct IUnknown *
0x1401dfc43  mov     rcx, [rsi+280h]; this
0x1401dfc4a  call    ?VmComEventConnect@Vml@@YAXPEAUIUnknown@@AEBU_GUID@@0PEAK@Z; Vml::VmComEventConnect(IUnknown *,_GUID const &,IUnknown *,ulong *)
0x1401dfc4f  mov     [rbp+47h+var_68], 1
0x1401dfc56  lea     rbx, [rsi+2B0h]
0x1401dfc5d  lea     rdx, [rbp+47h+var_68]
0x1401dfc61  mov     rcx, r15
0x1401dfc64  call    ??$CreateInstance@AEBV?$shared_ptr@VComputeSystem@Management@ComputeService@@@std@@W4WorkerEventSinkNotificationType@UtilityVm@ComputeService@@@?$VmComMultiInstanceObject@VWorkerProcessEventSink@UtilityVm@ComputeService@@@Vml@@SAPEAVWorkerProcessEventSink@UtilityVm@ComputeService@@AEBV?$shared_ptr@VComputeSystem@Management@ComputeService@@@std@@$$QEAW4WorkerEventSinkNotificationType@34@@Z; Vml::VmComMultiInstanceObject<ComputeService::UtilityVm::WorkerProcessEventSink>::CreateInstance<std::shared_ptr<ComputeService::Management::ComputeSystem> const &,ComputeService::UtilityVm::WorkerEventSinkNotificationType>(std::shared_ptr<ComputeService::Management::ComputeSystem> const &,ComputeService::UtilityVm::WorkerEventSinkNotificationType &&)
0x1401dfc69  mov     rdx, rax
0x1401dfc6c  mov     rcx, rbx
0x1401dfc6f  call    ??$Attach@VVmComFixedMemStream@Vml@@@?$VmComPtr@UIStream@@@Vml@@QEAAXPEAVVmComFixedMemStream@1@@Z; Vml::VmComPtr<IStream>::Attach<Vml::VmComFixedMemStream>(Vml::VmComFixedMemStream *)
0x1401dfc74  lea     r9, [rsi+2B8h]; struct IUnknown *
0x1401dfc7b  mov     r8, [rbx]; struct _GUID *
0x1401dfc7e  lea     rdx, IID_IVmVirtualMachineEvents; struct IUnknown *
0x1401dfc85  mov     rcx, [rsi+280h]; this
0x1401dfc8c  call    ?VmComEventConnect@Vml@@YAXPEAUIUnknown@@AEBU_GUID@@0PEAK@Z; Vml::VmComEventConnect(IUnknown *,_GUID const &,IUnknown *,ulong *)
0x1401dfc91  nop
0x1401dfc92  mov     rcx, rdi
0x1401dfc95  call    ??1?$VmReferencePtr@VVmRepository@@VVmUserReferenceTraits@Vml@@@Vml@@QEAA@XZ; Vml::VmReferencePtr<VmRepository,Vml::VmUserReferenceTraits>::~VmReferencePtr<VmRepository,Vml::VmUserReferenceTraits>(void)
0x1401dfc9a  mov     rcx, [rbp+47h+var_50]
0x1401dfc9e  xor     rcx, rsp; StackCookie
0x1401dfca1  call    __security_check_cookie
0x1401dfca6  add     rsp, 0B8h
0x1401dfcad  pop     r15
0x1401dfcaf  pop     r14
0x1401dfcb1  pop     r13
0x1401dfcb3  pop     r12
0x1401dfcb5  pop     rdi
0x1401dfcb6  pop     rsi
0x1401dfcb7  pop     rbx
0x1401dfcb8  pop     rbp
0x1401dfcb9  retn
```
