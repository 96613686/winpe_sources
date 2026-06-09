# CLightDismissClientStore::_DismissClients(void)

- ea: `0x180018630`
- end: `0x1800189f6`
- name: `?_DismissClients@CLightDismissClientStore@@AEAAJXZ`
- size: `966`
- prototype: `__int64 __fastcall(CLightDismissClientStore *__hidden this)`
- caller_count: `9`
- callee_count: `24`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x1800169b8`
- `0x180016ac0`
- `0x180017910`
- `0x180017eb0`
- `0x18002f670`
- `0x1800476b0`
- `0x18008355c`
- `0x180084120`
- `0x180084284`

## callees

- `0x180013f14`
- `0x1800184ac`
- `0x180018548`
- `0x180018630`
- `0x1800189fc`
- `0x180018af0`
- `0x180018b34`
- `0x180018b5c`
- `0x180018bf8`
- `0x180018c4c`
- `0x1800192d0`
- `0x1800193b4`
- `0x1800361f4`
- `0x180036350`
- `0x18003636c`
- `0x180048d84`
- `0x180054130`
- `0x180054500`
- `0x180054ad4`
- `0x180059b4c`
- `0x18005a1c2`
- `0x1800820b0`
- `0x180084630`
- `0x1800ed010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001878e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001878e`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x180018953`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x180018953`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x1800187f8`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x1800187f8`
- `api-ms-win-core-com-l1-1-0!CoDisableCallCancellation` at `0x180018937`
- `api-ms-win-core-com-l1-1-0!CoDisableCallCancellation` at `0x180018937`
- `api-ms-win-core-com-l1-1-0!CoEnableCallCancellation` at `0x1800187bc`
- `api-ms-win-core-com-l1-1-0!CoEnableCallCancellation` at `0x1800187bc`

## pseudocode

```c
__int64 __fastcall CLightDismissClientStore::_DismissClients(
        CLightDismissClientStore *this,
        unsigned int a2,
        unsigned int a3)
{
  CLightDismissClientStore *v3; // r15
  int Instance; // ebx
  __int64 *v5; // rcx
  __int64 v6; // rdi
  void *v7; // rdx
  __int64 v8; // rcx
  __int64 *v9; // r15
  DWORD CurrentThreadId; // eax
  struct IUnknown *v11; // r12
  CAgileObjectContainer *v12; // r14
  int CurrentApartmentId; // esi
  CAgileObjectContainer *v14; // rax
  CAgileObjectContainer *v15; // rax
  volatile signed __int32 *v16; // rbx
  __int64 v17; // rdx
  __int64 v18; // rcx
  __int64 v19; // r13
  __int64 v20; // rax
  unsigned int v22[2]; // [rsp+40h] [rbp-C0h] BYREF
  DWORD Parameter; // [rsp+48h] [rbp-B8h] BYREF
  char v24; // [rsp+4Ch] [rbp-B4h]
  HRESULT v25; // [rsp+50h] [rbp-B0h]
  void *phNewTimer; // [rsp+58h] [rbp-A8h] BYREF
  char *v27; // [rsp+60h] [rbp-A0h]
  CLightDismissClientStore *v28; // [rsp+68h] [rbp-98h]
  void **v29; // [rsp+70h] [rbp-90h] BYREF
  int v30; // [rsp+78h] [rbp-88h] BYREF
  char v31; // [rsp+7Ch] [rbp-84h]
  int v32; // [rsp+A0h] [rbp-60h] BYREF
  const char *v33; // [rsp+A8h] [rbp-58h]
  __int64 v34; // [rsp+B0h] [rbp-50h]
  char v35; // [rsp+B8h] [rbp-48h]
  int v36; // [rsp+C0h] [rbp-40h]
  _BYTE v37[152]; // [rsp+C8h] [rbp-38h] BYREF
  __int128 v38; // [rsp+160h] [rbp+60h]
  int v39; // [rsp+170h] [rbp+70h]
  __int64 v40; // [rsp+178h] [rbp+78h]
  int *v41; // [rsp+180h] [rbp+80h]
  __int64 v42; // [rsp+188h] [rbp+88h] BYREF
  _QWORD v43[3]; // [rsp+190h] [rbp+90h] BYREF
  int v44; // [rsp+1A8h] [rbp+A8h]
  int *v45; // [rsp+1B0h] [rbp+B0h]
  char v46; // [rsp+1B8h] [rbp+B8h]

  v28 = this;
  v3 = this;
  Instance = 0;
  v27 = (char *)this + 176;
  if ( *((_QWORD *)this + 22)
    || (Instance = shell::TaskScheduler::CreateInstance(
                     (const struct _GUID *)this,
                     a2,
                     a3,
                     (struct TaskScheduler **)this + 22),
        Instance >= 0) )
  {
LABEL_35:
    v20 = *((_QWORD *)v3 + 16);
    if ( !v20 )
      return (unsigned int)Instance;
    v5 = (__int64 *)*((_QWORD *)v3 + 15);
    v6 = *v5;
    if ( v20 != 1 )
      memmove_0(v5, v5 + 1, 8 * (v20 - 1));
    --*((_QWORD *)v3 + 16);
    v30 = 0;
    v33 = "LightDismissDismissClient";
    v38 = 0;
    v31 = 0;
    v35 = 0;
    v32 = 0;
    v34 = 0;
    v36 = 0;
    memset_0(v37, 0, sizeof(v37));
    v39 = 1;
    v40 = 0;
    v42 = 0;
    v41 = &v30;
    v43[1] = &v29;
    v45 = &v32;
    v43[0] = 0;
    v43[2] = 0;
    v44 = 0;
    v46 = 0;
    v29 = &LightDismissFrameworkTelemetry::LightDismissDismissClient::`vftable';
    LightDismissFrameworkTelemetry::LightDismissDismissClient::StartActivity(
      (LightDismissFrameworkTelemetry::LightDismissDismissClient *)&v29,
      *(_DWORD *)(v6 + 40));
    while ( *(_QWORD *)(v6 + 56) )
      v6 = *(_QWORD *)(v6 + 56);
    v9 = (__int64 *)v27;
    while ( 1 )
    {
      if ( (Microsoft_Windows_WindowsUIImmersiveEnableBits & 1) != 0 )
        McTemplateU0pq_EventWriteTransfer(v8, v7, *(_QWORD *)(v6 + 8), *(unsigned int *)(v6 + 40));
      CurrentThreadId = GetCurrentThreadId();
      v24 = 0;
      Parameter = CurrentThreadId;
      v25 = -2147467259;
      phNewTimer = 0;
      CBaseRPCTimeout::Disarm((CBaseRPCTimeout *)&Parameter);
      v25 = CoEnableCallCancellation(0);
      if ( v25 >= 0 )
        CreateTimerQueueTimer(&phNewTimer, 0, CBaseRPCTimeout::s_Callback, &Parameter, 0x3E8u, 0x3E8u, 0);
      *(_QWORD *)v22 = 0;
      Microsoft::WRL::ComPtr<CAgileObjectContainer>::InternalRelease(v22);
      v11 = *(struct IUnknown **)(v6 + 32);
      v12 = 0;
      v22[0] = 0;
      CurrentApartmentId = CAgileObjectContainer::s_GetCurrentApartmentId(v22);
      if ( CurrentApartmentId < 0 )
        goto LABEL_22;
      v14 = (CAgileObjectContainer *)operator new(0x28u, (const struct std::nothrow_t *)&std::nothrow);
      if ( v14 )
      {
        v15 = CAgileObjectContainer::CAgileObjectContainer(v14, v11, v22[0]);
        v16 = (volatile signed __int32 *)v15;
        if ( v15 )
          break;
      }
      CurrentApartmentId = -2147024882;
      Instance = -2147024882;
LABEL_26:
      v19 = *(_QWORD *)(v6 + 48);
      Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(v6 + 32);
      operator delete((void *)v6, (const struct std::nothrow_t *)0x40);
      v6 = v19;
      if ( v19 )
        *(_QWORD *)(v19 + 56) = 0;
      if ( v12 )
        CAgileObjectContainer::Release(v12);
      if ( v25 >= 0 )
      {
        v25 = -2147467259;
        CoDisableCallCancellation(0);
        v7 = phNewTimer;
        if ( phNewTimer )
          DeleteTimerQueueTimer(0, phNewTimer, (HANDLE)0xFFFFFFFFFFFFFFFFLL);
      }
      if ( !v19 )
      {
        wil::ActivityBase<LightDismissFrameworkLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(
          &v29,
          (unsigned int)CurrentApartmentId);
        v29 = &LightDismissFrameworkTelemetry::LightDismissDismissClient::`vftable';
        wil::ActivityBase<LightDismissFrameworkLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(&v29);
        wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)v43);
        wil::details::shared_object<wil::ActivityBase<LightDismissFrameworkLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<LightDismissFrameworkLogging,_TlgReflectorTag_Param0IsProviderType>>::reset(&v42);
        wil::ActivityBase<LightDismissFrameworkLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<LightDismissFrameworkLogging,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<LightDismissFrameworkLogging,_TlgReflectorTag_Param0IsProviderType>(&v30);
        v3 = v28;
        goto LABEL_35;
      }
    }
    *((_DWORD *)v15 + 7) = 0;
    CurrentApartmentId = GlobalInterfaceTable::s_Retrieve();
    if ( CurrentApartmentId >= 0 )
    {
      CurrentApartmentId = ((__int64 (__fastcall *)(struct IGlobalInterfaceTable *, struct IUnknown *, GUID *, volatile signed __int32 *))GlobalInterfaceTable::s_pGlobalInterfaceTable->lpVtbl->RegisterInterfaceInGlobal)(
                             GlobalInterfaceTable::s_pGlobalInterfaceTable,
                             v11,
                             &GUID_8d4d1ec2_4740_4fc5_b4b1_6dc3722a2eeb,
                             v16 + 7);
      if ( CurrentApartmentId >= 0 )
      {
        CurrentApartmentId = AgileGitPtr::Initialize(v16 + 4, v17, &GUID_8d4d1ec2_4740_4fc5_b4b1_6dc3722a2eeb, v11);
        if ( CurrentApartmentId >= 0 )
        {
          v12 = (CAgileObjectContainer *)v16;
          _InterlockedIncrement(v16);
        }
      }
    }
    CAgileObjectContainer::Release((CAgileObjectContainer *)v16);
LABEL_22:
    Instance = CurrentApartmentId;
    if ( CurrentApartmentId >= 0 )
    {
      v18 = *v9;
      *(_QWORD *)v22 = v12;
      if ( v12 )
        _InterlockedIncrement((volatile signed __int32 *)v12);
      shell::TaskScheduler::AddTask__lambda_0772b9cc429bfbb776337f4e61735bae___(v18, v22);
      Microsoft::WRL::ComPtr<CAgileObjectContainer>::InternalRelease(v22);
    }
    goto LABEL_26;
  }
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x180018630  push    rbp
0x180018632  push    rbx
0x180018633  push    rsi
0x180018634  push    rdi
0x180018635  push    r12
0x180018637  push    r13
0x180018639  push    r14
0x18001863b  push    r15
0x18001863d  lea     rbp, [rsp-0D8h]
0x180018645  sub     rsp, 1D8h
0x18001864c  mov     rax, cs:__security_cookie
0x180018653  xor     rax, rsp
0x180018656  mov     [rbp+110h+var_50], rax
0x18001865d  xor     r12d, r12d
0x180018660  mov     [rsp+210h+var_1A8], rcx
0x180018665  lea     r9, [rcx+0B0h]; struct TaskScheduler **
0x18001866c  mov     r15, rcx
0x18001866f  mov     ebx, r12d
0x180018672  mov     [rsp+210h+var_1B0], r9
0x180018677  cmp     [r9], r12
0x18001867a  jnz     loc_1800189B1
0x180018680  call    ?CreateInstance@TaskScheduler@shell@@SAJAEBU_GUID@@KKPEAPEAV12@@Z; shell::TaskScheduler::CreateInstance(_GUID const &,ulong,ulong,shell::TaskScheduler * *)
0x180018685  mov     ebx, eax
0x180018687  test    eax, eax
0x180018689  jns     loc_1800189B1
0x18001868f  jmp     loc_1800189C1
0x180018694  mov     rcx, [r15+78h]; void *
0x180018698  lea     rbx, ??_7LightDismissDismissClient@LightDismissFrameworkTelemetry@@6B@; const LightDismissFrameworkTelemetry::LightDismissDismissClient::`vftable'
0x18001869f  mov     rdi, [rcx]
0x1800186a2  test    rax, rax
0x1800186a5  jz      short loc_1800186C4
0x1800186a7  lea     r8, [rax-1]
0x1800186ab  test    r8, r8
0x1800186ae  jz      short loc_1800186BD
0x1800186b0  shl     r8, 3; Size
0x1800186b4  lea     rdx, [rcx+8]; Src
0x1800186b8  call    memmove_0
0x1800186bd  dec     qword ptr [r15+80h]
0x1800186c4  lea     rax, aLightdismissdi; "LightDismissDismissClient"
0x1800186cb  mov     [rsp+210h+var_198], r12d
0x1800186d0  xorps   xmm0, xmm0
0x1800186d3  mov     [rbp+110h+var_168], rax
0x1800186d7  xor     edx, edx; Val
0x1800186d9  movdqa  [rbp+110h+var_B0], xmm0
0x1800186de  mov     r8d, 98h; Size
0x1800186e4  mov     [rsp+210h+var_194], r12b
0x1800186e9  lea     rcx, [rbp+110h+var_148]; void *
0x1800186ed  mov     [rbp+110h+var_158], r12b
0x1800186f1  mov     [rbp+110h+var_170], r12d
0x1800186f5  mov     [rbp+110h+var_160], r12
0x1800186f9  mov     [rbp+110h+var_150], r12d
0x1800186fd  call    memset_0
0x180018702  xor     eax, eax
0x180018704  mov     [rbp+110h+var_A0], 1
0x18001870b  mov     [rbp+110h+var_98], rax
0x18001870f  lea     rcx, [rsp+210h+var_1A0]; this
0x180018714  lea     rax, [rsp+210h+var_198]
0x180018719  mov     [rbp+110h+var_88], r12
0x180018720  mov     [rbp+110h+var_90], rax
0x180018727  lea     rax, [rsp+210h+var_1A0]
0x18001872c  mov     [rbp+110h+var_78], rax
0x180018733  lea     rax, [rbp+110h+var_170]
0x180018737  mov     [rbp+110h+var_60], rax
0x18001873e  mov     [rbp+110h+var_80], r12
0x180018745  mov     [rbp+110h+var_70], r12
0x18001874c  mov     [rbp+110h+var_68], r12d
0x180018753  mov     [rbp+110h+var_58], r12b
0x18001875a  mov     [rsp+210h+var_1A0], rbx
0x18001875f  mov     edx, [rdi+28h]; int
0x180018762  call    ?StartActivity@LightDismissDismissClient@LightDismissFrameworkTelemetry@@QEAAXH@Z; LightDismissFrameworkTelemetry::LightDismissDismissClient::StartActivity(int)
0x180018767  jmp     short loc_18001876D
0x180018769  mov     rdi, [rdi+38h]
0x18001876d  cmp     [rdi+38h], r12
0x180018771  jnz     short loc_180018769
0x180018773  mov     r15, [rsp+210h+var_1B0]
0x180018778  test    cs:Microsoft_Windows_WindowsUIImmersiveEnableBits, 1
0x18001877f  jz      short loc_18001878E
0x180018781  mov     r9d, [rdi+28h]
0x180018785  mov     r8, [rdi+8]
0x180018789  call    McTemplateU0pq_EventWriteTransfer
0x18001878e  call    cs:__imp_GetCurrentThreadId
0x180018795  nop     dword ptr [rax+rax+00h]
0x18001879a  lea     rcx, [rsp+210h+Parameter]; this
0x18001879f  mov     [rsp+210h+var_1C4], r12b
0x1800187a4  mov     [rsp+210h+Parameter], eax
0x1800187a8  mov     [rsp+210h+var_1C0], 80004005h
0x1800187b0  mov     [rsp+210h+phNewTimer], r12
0x1800187b5  call    ?Disarm@CBaseRPCTimeout@@QEAAXXZ; CBaseRPCTimeout::Disarm(void)
0x1800187ba  xor     ecx, ecx; pReserved
0x1800187bc  call    cs:__imp_CoEnableCallCancellation
0x1800187c3  nop     dword ptr [rax+rax+00h]
0x1800187c8  mov     [rsp+210h+var_1C0], eax
0x1800187cc  test    eax, eax
0x1800187ce  js      short loc_180018804
0x1800187d0  mov     [rsp+210h+Flags], r12d; Flags
0x1800187d5  lea     r9, [rsp+210h+Parameter]; Parameter
0x1800187da  mov     [rsp+210h+Period], 3E8h; Period
0x1800187e2  lea     r8, ?s_Callback@CBaseRPCTimeout@@CAXPEAXE@Z; Callback
0x1800187e9  xor     edx, edx; TimerQueue
0x1800187eb  mov     [rsp+210h+DueTime], 3E8h; DueTime
0x1800187f3  lea     rcx, [rsp+210h+phNewTimer]; phNewTimer
0x1800187f8  call    cs:__imp_CreateTimerQueueTimer
0x1800187ff  nop     dword ptr [rax+rax+00h]
0x180018804  lea     rcx, [rsp+210h+var_1D0]
0x180018809  mov     qword ptr [rsp+210h+var_1D0], r12
0x18001880e  call    ?InternalRelease@?$ComPtr@VCAgileObjectContainer@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<CAgileObjectContainer>::InternalRelease(void)
0x180018813  mov     r12, [rdi+20h]
0x180018817  lea     rcx, [rsp+210h+var_1D0]; unsigned int *
0x18001881c  xor     r14d, r14d
0x18001881f  mov     [rsp+210h+var_1D0], r14d
0x180018824  call    ?s_GetCurrentApartmentId@CAgileObjectContainer@@KAJPEAK@Z; CAgileObjectContainer::s_GetCurrentApartmentId(ulong *)
0x180018829  mov     esi, eax
0x18001882b  test    eax, eax
0x18001882d  js      loc_1800188C5
0x180018833  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001883a  lea     ecx, [r14+28h]; unsigned __int64
0x18001883e  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180018843  test    rax, rax
0x180018846  jz      loc_1800189E7
0x18001884c  mov     r8d, [rsp+210h+var_1D0]; unsigned int
0x180018851  mov     rdx, r12; struct IUnknown *
0x180018854  mov     rcx, rax; this
0x180018857  call    ??0CAgileObjectContainer@@IEAA@PEAUIUnknown@@K@Z; CAgileObjectContainer::CAgileObjectContainer(IUnknown *,ulong)
0x18001885c  mov     rbx, rax
0x18001885f  test    rax, rax
0x180018862  jz      loc_1800189E7
0x180018868  mov     [rax+1Ch], r14d
0x18001886c  call    ?s_Retrieve@GlobalInterfaceTable@@CAJXZ; GlobalInterfaceTable::s_Retrieve(void)
0x180018871  mov     esi, eax
0x180018873  test    eax, eax
0x180018875  js      short loc_1800188BD
0x180018877  mov     rcx, cs:?s_pGlobalInterfaceTable@GlobalInterfaceTable@@0PEAUIGlobalInterfaceTable@@EA; IGlobalInterfaceTable * GlobalInterfaceTable::s_pGlobalInterfaceTable
0x18001887e  lea     r9, [rbx+1Ch]
0x180018882  lea     r8, _GUID_8d4d1ec2_4740_4fc5_b4b1_6dc3722a2eeb
0x180018889  mov     rdx, [rcx]
0x18001888c  mov     rax, [rdx+18h]
0x180018890  mov     rdx, r12
0x180018893  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018898  mov     esi, eax
0x18001889a  test    eax, eax
0x18001889c  js      short loc_1800188BD
0x18001889e  lea     rcx, [rbx+10h]
0x1800188a2  mov     r9, r12
0x1800188a5  lea     r8, _GUID_8d4d1ec2_4740_4fc5_b4b1_6dc3722a2eeb
0x1800188ac  call    ?Initialize@AgileGitPtr@@QEAAJW4AgileReferenceOptions@@AEBU_GUID@@PEAUIUnknown@@@Z; AgileGitPtr::Initialize(AgileReferenceOptions,_GUID const &,IUnknown *)
0x1800188b1  mov     esi, eax
0x1800188b3  test    eax, eax
0x1800188b5  js      short loc_1800188BD
0x1800188b7  mov     r14, rbx
0x1800188ba  lock inc dword ptr [rbx]
0x1800188bd  mov     rcx, rbx; this
0x1800188c0  call    ?Release@CAgileObjectContainer@@QEAAKXZ; CAgileObjectContainer::Release(void)
0x1800188c5  xor     r12d, r12d
0x1800188c8  mov     ebx, esi
0x1800188ca  test    esi, esi
0x1800188cc  js      short loc_1800188F3
0x1800188ce  mov     rcx, [r15]
0x1800188d1  mov     qword ptr [rsp+210h+var_1D0], r14
0x1800188d6  test    r14, r14
0x1800188d9  jz      short loc_1800188DF
0x1800188db  lock inc dword ptr [r14]
0x1800188df  lea     rdx, [rsp+210h+var_1D0]
0x1800188e4  call    shell__TaskScheduler__AddTask__lambda_0772b9cc429bfbb776337f4e61735bae___
0x1800188e9  lea     rcx, [rsp+210h+var_1D0]
0x1800188ee  call    ?InternalRelease@?$ComPtr@VCAgileObjectContainer@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<CAgileObjectContainer>::InternalRelease(void)
0x1800188f3  mov     r13, [rdi+30h]
0x1800188f7  lea     rcx, [rdi+20h]
0x1800188fb  call    ?InternalRelease@?$ComPtr@UIFrameTaskManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(void)
0x180018900  mov     edx, 40h ; '@'; struct std::nothrow_t *
0x180018905  mov     rcx, rdi; void *
0x180018908  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001890d  mov     rdi, r13
0x180018910  test    r13, r13
0x180018913  jz      short loc_180018919
0x180018915  mov     [r13+38h], r12
0x180018919  test    r14, r14
0x18001891c  jz      short loc_180018926
0x18001891e  mov     rcx, r14; this
0x180018921  call    ?Release@CAgileObjectContainer@@QEAAKXZ; CAgileObjectContainer::Release(void)
0x180018926  cmp     [rsp+210h+var_1C0], r12d
0x18001892b  jl      short loc_18001895F
0x18001892d  xor     ecx, ecx; pReserved
0x18001892f  mov     [rsp+210h+var_1C0], 80004005h
0x180018937  call    cs:__imp_CoDisableCallCancellation
0x18001893e  nop     dword ptr [rax+rax+00h]
0x180018943  mov     rdx, [rsp+210h+phNewTimer]; Timer
0x180018948  test    rdx, rdx
0x18001894b  jz      short loc_18001895F
0x18001894d  or      r8, 0FFFFFFFFFFFFFFFFh; CompletionEvent
0x180018951  xor     ecx, ecx; TimerQueue
0x180018953  call    cs:__imp_DeleteTimerQueueTimer
0x18001895a  nop     dword ptr [rax+rax+00h]
0x18001895f  test    r13, r13
0x180018962  jnz     loc_180018778
0x180018968  mov     edx, esi
0x18001896a  lea     rcx, [rsp+210h+var_1A0]
0x18001896f  call    ?Stop@?$ActivityBase@VLightDismissFrameworkLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<LightDismissFrameworkLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x180018974  lea     rax, ??_7LightDismissDismissClient@LightDismissFrameworkTelemetry@@6B@; const LightDismissFrameworkTelemetry::LightDismissDismissClient::`vftable'
0x18001897b  lea     rcx, [rsp+210h+var_1A0]
0x180018980  mov     [rsp+210h+var_1A0], rax
0x180018985  call    ?Destroy@?$ActivityBase@VLightDismissFrameworkLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<LightDismissFrameworkLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x18001898a  lea     rcx, [rbp+110h+var_80]; this
0x180018991  call    ??1ThreadFailureCallbackHolder@details@wil@@QEAA@XZ; wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder(void)
0x180018996  lea     rcx, [rbp+110h+var_88]
0x18001899d  call    ?reset@?$shared_object@V?$ActivityData@VLightDismissFrameworkLogging@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VLightDismissFrameworkLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@@details@wil@@QEAAXXZ; wil::details::shared_object<wil::ActivityBase<LightDismissFrameworkLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<LightDismissFrameworkLogging,_TlgReflectorTag_Param0IsProviderType>>::reset(void)
0x1800189a2  lea     rcx, [rsp+210h+var_198]
0x1800189a7  call    ??1?$ActivityData@VLightDismissFrameworkLogging@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VLightDismissFrameworkLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<LightDismissFrameworkLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<LightDismissFrameworkLogging,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<LightDismissFrameworkLogging,_TlgReflectorTag_Param0IsProviderType>(void)
0x1800189ac  mov     r15, [rsp+210h+var_1A8]
0x1800189b1  mov     rax, [r15+80h]
0x1800189b8  test    rax, rax
0x1800189bb  jnz     loc_180018694
0x1800189c1  mov     eax, ebx
0x1800189c3  mov     rcx, [rbp+110h+var_50]
0x1800189ca  xor     rcx, rsp; StackCookie
0x1800189cd  call    __security_check_cookie
0x1800189d2  add     rsp, 1D8h
0x1800189d9  pop     r15
0x1800189db  pop     r14
0x1800189dd  pop     r13
0x1800189df  pop     r12
0x1800189e1  pop     rdi
0x1800189e2  pop     rsi
0x1800189e3  pop     rbx
0x1800189e4  pop     rbp
0x1800189e5  retn
0x1800189e7  mov     esi, 8007000Eh
0x1800189ec  xor     r12d, r12d
0x1800189ef  mov     ebx, esi
0x1800189f1  jmp     loc_1800188F3
```
