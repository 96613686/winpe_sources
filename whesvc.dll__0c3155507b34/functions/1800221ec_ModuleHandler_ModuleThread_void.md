# ModuleHandler::ModuleThread(void)

- ea: `0x1800221ec`
- end: `0x180022753`
- name: `?ModuleThread@ModuleHandler@@QEAAJXZ`
- size: `1383`
- prototype: `__int64 __fastcall(ModuleHandler *__hidden this)`
- caller_count: `1`
- callee_count: `14`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180014c50`

## callees

- `0x1800032e0`
- `0x180009044`
- `0x18000a6c4`
- `0x18000b5c4`
- `0x180011578`
- `0x1800142e0`
- `0x180015c20`
- `0x180019fd8`
- `0x18001a100`
- `0x18001b190`
- `0x18001befc`
- `0x1800221ec`
- `0x1800248c8`
- `0x180029010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002232a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800226c5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002232a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800226c5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002231c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800226b7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002231c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800226b7`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180022414`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180022574`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18002266b`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18002271a`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180022414`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180022574`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18002266b`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18002271a`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x1800222ad`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x1800222ad`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18002260d`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18002260d`

## pseudocode

```c
__int64 __fastcall ModuleHandler::ModuleThread(ModuleHandler *this)
{
  ModuleHandler *v1; // rsi
  char *v2; // rbx
  __int64 v3; // r8
  HRESULT v4; // eax
  int v5; // r14d
  unsigned int v6; // ebx
  struct _Mtx_internal_imp_t *Instance; // rax
  void *v8; // rbx
  HANDLE ProcessHeap; // rax
  _QWORD **v11; // r15
  __int64 v12; // rcx
  unsigned int v13; // ebx
  struct _Mtx_internal_imp_t *v14; // rax
  const char *v15; // rax
  unsigned int v16; // ebx
  struct _Mtx_internal_imp_t *v17; // rax
  int v18; // eax
  DWORD v19; // ecx
  unsigned int v20; // ebx
  struct _Mtx_internal_imp_t *v21; // rax
  void *v22; // rbx
  HANDLE v23; // rax
  unsigned int v24; // ebx
  struct _Mtx_internal_imp_t *v25; // rax
  int v26; // [rsp+20h] [rbp-178h]
  int v27; // [rsp+30h] [rbp-168h] BYREF
  __int128 v28; // [rsp+38h] [rbp-160h] BYREF
  __int64 v29; // [rsp+48h] [rbp-150h]
  char v30; // [rsp+51h] [rbp-147h]
  const char *v31; // [rsp+58h] [rbp-140h] BYREF
  __int128 v32; // [rsp+60h] [rbp-138h] BYREF
  __int128 lpMem; // [rsp+70h] [rbp-128h]
  __int128 v34; // [rsp+80h] [rbp-118h] BYREF
  __int64 v35; // [rsp+90h] [rbp-108h]
  int v36; // [rsp+98h] [rbp-100h]
  __int64 v37; // [rsp+A0h] [rbp-F8h]
  char v38; // [rsp+A8h] [rbp-F0h]
  ModuleHandler *v39; // [rsp+B0h] [rbp-E8h]
  char *v40; // [rsp+B8h] [rbp-E0h]
  _QWORD **v41; // [rsp+C0h] [rbp-D8h]
  _DWORD v42[2]; // [rsp+C8h] [rbp-D0h] BYREF
  __int64 v43; // [rsp+D0h] [rbp-C8h]
  __int64 v44; // [rsp+D8h] [rbp-C0h]
  __int64 v45; // [rsp+E0h] [rbp-B8h]
  void (__fastcall *v46)(const struct _WINDIAG_CALLBACK_INFO *, struct _WINDIAG_VALUE *); // [rsp+E8h] [rbp-B0h]
  ModuleHandler *v47; // [rsp+F0h] [rbp-A8h]
  ModuleHandler *v48; // [rsp+F8h] [rbp-A0h]
  char v49; // [rsp+100h] [rbp-98h]
  ModuleHandler *v50; // [rsp+108h] [rbp-90h]
  char v51; // [rsp+110h] [rbp-88h]
  __int128 *v52; // [rsp+118h] [rbp-80h]
  char v53; // [rsp+120h] [rbp-78h]
  __int128 v54; // [rsp+128h] [rbp-70h] BYREF
  __m128i si128; // [rsp+138h] [rbp-60h]
  _OWORD v56[2]; // [rsp+148h] [rbp-50h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+198h] [rbp+0h]

  v1 = this;
  v39 = this;
  v2 = (char *)this + 40;
  v40 = (char *)this + 40;
  v3 = *((_QWORD *)this + 39);
  if ( *(_DWORD *)v3 == 1 )
  {
    wil::ActivityThreadWatcher::ActivityThreadWatcher(
      (wil::ActivityThreadWatcher *)&v32,
      (ModuleHandler *)((char *)this + 40),
      (const struct wil::details::StoredCallContextInfo *)(v3 + 40));
  }
  else
  {
    v32 = 0;
    lpMem = 0;
    v34 = 0;
    v35 = 0;
    v36 = 0;
    v37 = 0;
    v38 = 0;
  }
  v48 = v1;
  v49 = 1;
  v50 = v1;
  v51 = 1;
  v4 = CoInitializeEx(0, 0);
  v5 = v4;
  if ( v4 < 0 )
  {
    ((void (__stdcall *)(wil::details::in1diag3 *, void *, unsigned int, const char *, int))wil::details::in1diag3::Return_Hr)(
      retaddr,
      (void *)0x1C2,
      (unsigned int)"pcshell\\base\\whesvc\\lib\\modulehandler.cpp",
      (const char *)(unsigned int)v4,
      v26);
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFixes5D>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_BugFixes5D>::GetImpl'::`2'::impl) )
      wil::ActivityBase<WhesvcTelemetryProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v2);
    v6 = *((_DWORD *)v1 + 4);
    Instance = OrchestratorSingleton::GetInstance();
    OrchestratorSingleton::SignalModuleFinished(Instance, v6);
LABEL_8:
    wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)&v34);
    if ( BYTE8(lpMem) )
    {
      v8 = (void *)lpMem;
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v8);
    }
    return (unsigned int)v5;
  }
  v30 = 1;
  v28 = 0;
  v29 = 0;
  v11 = (_QWORD **)((char *)v1 + 24);
  v41 = (_QWORD **)((char *)v1 + 24);
  v12 = *((_QWORD *)v1 + 3);
  v42[0] = *(_DWORD *)(v12 + 16);
  v42[1] = 0;
  v43 = *(_QWORD *)(v12 + 8);
  v44 = *((_QWORD *)v1 + 1);
  v45 = *(_QWORD *)v1;
  v46 = ModuleHandler::WinDiagExecutionCallback;
  v47 = v1;
  v5 = WinDiag(*(_QWORD *)v12, v42, &v28);
  v27 = v5;
  v52 = &v28;
  v53 = 1;
  if ( v5 == -2147201017 )
  {
    if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFixes5D>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_BugFixes5D>::GetImpl'::`2'::impl) )
      wil::ActivityBase<WhesvcTelemetryProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v2);
    qword_180034DE0(&v28);
    CoUninitialize();
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFixes5D>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_BugFixes5D>::GetImpl'::`2'::impl) )
      wil::ActivityBase<WhesvcTelemetryProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v2);
    v13 = *((_DWORD *)v1 + 4);
    v14 = OrchestratorSingleton::GetInstance();
    OrchestratorSingleton::SignalModuleFinished(v14, v13);
  }
  else
  {
    if ( v5 < 0 )
    {
      v54 = 0;
      si128 = _mm_load_si128((const __m128i *)&_xmm);
      LOBYTE(v54) = 0;
      v31 = "<n/a>";
      if ( (_DWORD)v28 == 4 && *((_QWORD *)&v28 + 1) )
      {
        if ( __eh34_try(-1, 0) )
        {
          __eh34_scope_strut(0);
          memset(v56, 0, sizeof(v56));
          std::string::_Construct<1,char const *>(v56, *((_QWORD *)&v28 + 1), (unsigned int)v29);
          std::string::operator=(&v54, v56);
          std::string::~string((char **)v56);
          v15 = (const char *)&v54;
          if ( si128.m128i_i64[1] > 0xFuLL )
            v15 = (const char *)v54;
          v31 = v15;
        }
        if ( __eh34_catch(0) )
        {
          if ( __eh34_catch_type(0, &std::bad_alloc `RTTI Type Descriptor', 0) )
          {
            v5 = v27;
            v1 = v39;
            v2 = v40;
            v11 = v41;
            __eh34_try_continuation(0, &std::bad_alloc `RTTI Type Descriptor', &loc_180022507);
          }
        }
      }
      WhesvcTelemetryProvider::WhesvcModuleActivity::ModuleFailureDetails<char const * &,char const * &>(
        v2,
        **v11,
        &v31);
      ((void (__stdcall *)(wil::details::in1diag3 *, void *, unsigned int, const char *, int))wil::details::in1diag3::Return_Hr)(
        retaddr,
        (void *)0x1F5,
        (unsigned int)"pcshell\\base\\whesvc\\lib\\modulehandler.cpp",
        (const char *)(unsigned int)v5,
        v26);
      std::string::~string((char **)&v54);
      qword_180034DE0(&v28);
      CoUninitialize();
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFixes5D>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_BugFixes5D>::GetImpl'::`2'::impl) )
        wil::ActivityBase<WhesvcTelemetryProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v2);
      v16 = *((_DWORD *)v1 + 4);
      v17 = OrchestratorSingleton::GetInstance();
      OrchestratorSingleton::SignalModuleFinished(v17, v16);
      goto LABEL_8;
    }
    if ( (_DWORD)v28 == 5 )
    {
      while ( 1 )
      {
        v27 = 0;
        v54 = 0;
        si128.m128i_i64[0] = 0;
        v18 = qword_180034DD8(*((_QWORD *)&v28 + 1), 0, &v54, &v27);
        v5 = v18;
        if ( v18 < 0 )
          break;
        if ( v27 )
        {
          qword_180034DE0(&v54);
          goto LABEL_34;
        }
        v19 = *((_DWORD *)v1 + 8);
        if ( v19 )
          Sleep(v19);
        qword_180034DE0(&v54);
      }
      ((void (__stdcall *)(wil::details::in1diag3 *, void *, unsigned int, const char *, int))wil::details::in1diag3::Return_Hr)(
        retaddr,
        (void *)0x1FF,
        (unsigned int)"pcshell\\base\\whesvc\\lib\\modulehandler.cpp",
        (const char *)(unsigned int)v18,
        v26);
      qword_180034DE0(&v28);
      CoUninitialize();
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFixes5D>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_BugFixes5D>::GetImpl'::`2'::impl) )
        wil::ActivityBase<WhesvcTelemetryProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v2);
      v24 = *((_DWORD *)v1 + 4);
      v25 = OrchestratorSingleton::GetInstance();
      OrchestratorSingleton::SignalModuleFinished(v25, v24);
      goto LABEL_8;
    }
LABEL_34:
    if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFixes5D>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_BugFixes5D>::GetImpl'::`2'::impl) )
      wil::ActivityBase<WhesvcTelemetryProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v2);
    qword_180034DE0(&v28);
    CoUninitialize();
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFixes5D>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_BugFixes5D>::GetImpl'::`2'::impl) )
      wil::ActivityBase<WhesvcTelemetryProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v2);
    v20 = *((_DWORD *)v1 + 4);
    v21 = OrchestratorSingleton::GetInstance();
    OrchestratorSingleton::SignalModuleFinished(v21, v20);
  }
  wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)&v34);
  if ( BYTE8(lpMem) )
  {
    v22 = (void *)lpMem;
    v23 = GetProcessHeap();
    HeapFree(v23, 0, v22);
  }
  return 0;
}

```

## disassembly

```asm
0x1800221ec  push    rbx
0x1800221ee  push    rsi
0x1800221ef  push    r14
0x1800221f1  push    r15
0x1800221f3  sub     rsp, 178h
0x1800221fa  mov     rax, cs:__security_cookie
0x180022201  xor     rax, rsp
0x180022204  mov     [rsp+198h+var_30], rax
0x18002220c  mov     rsi, rcx
0x18002220f  mov     [rsp+198h+var_E8], rcx
0x180022217  lea     rbx, [rcx+28h]
0x18002221b  mov     [rsp+198h+var_E0], rbx
0x180022223  mov     r8, [rbx+110h]
0x18002222a  cmp     dword ptr [r8], 1
0x18002222e  jnz     short loc_180022243
0x180022230  add     r8, 28h ; '('; struct wil::details::StoredCallContextInfo *
0x180022234  mov     rdx, rbx; struct wil::details::IFailureCallback *
0x180022237  lea     rcx, [rsp+198h+var_138]; this
0x18002223c  call    ??0ActivityThreadWatcher@wil@@QEAA@PEAUIFailureCallback@details@1@AEBVStoredCallContextInfo@31@@Z; wil::ActivityThreadWatcher::ActivityThreadWatcher(wil::details::IFailureCallback *,wil::details::StoredCallContextInfo const &)
0x180022241  jmp     short loc_180022289
0x180022243  mov     [rsp+198h+var_120], 0
0x180022248  xorps   xmm0, xmm0
0x18002224b  movups  [rsp+198h+var_138], xmm0
0x180022250  movups  xmmword ptr [rsp+70h], xmm0
0x180022255  movdqa  [rsp+198h+var_118], xmm0
0x18002225e  mov     [rsp+198h+var_108], 0
0x18002226a  mov     [rsp+198h+var_100], 0
0x180022275  mov     [rsp+198h+var_F8], 0
0x180022281  mov     [rsp+198h+var_F0], 0
0x180022289  mov     [rsp+198h+var_A0], rsi
0x180022291  mov     [rsp+198h+var_98], 1
0x180022299  mov     [rsp+198h+var_90], rsi
0x1800222a1  mov     [rsp+198h+var_88], 1
0x1800222a9  xor     edx, edx; dwCoInit
0x1800222ab  xor     ecx, ecx; pvReserved
0x1800222ad  call    cs:__imp_CoInitializeEx
0x1800222b3  mov     r14d, eax
0x1800222b6  test    eax, eax
0x1800222b8  jns     short loc_180022338
0x1800222ba  mov     rcx, [rsp+198h]; this
0x1800222c2  mov     r9d, eax; char *
0x1800222c5  lea     r8, aPcshellBaseWhe_2; "pcshell\\base\\whesvc\\lib\\modulehandl"...
0x1800222cc  mov     edx, 1C2h; void *
0x1800222d1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800222d6  nop
0x1800222d7  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_BugFixes5D@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_BugFixes5D@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFixes5D> `wil::Feature<__WilFeatureTraits_Feature_BugFixes5D>::GetImpl(void)'::`2'::impl
0x1800222de  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_BugFixes5D@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFixes5D>::__private_IsEnabled(void)
0x1800222e3  test    al, al
0x1800222e5  jz      short loc_1800222F0
0x1800222e7  mov     rcx, rbx
0x1800222ea  call    ?Stop@?$ActivityBase@VWhesvcTelemetryProvider@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<WhesvcTelemetryProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x1800222ef  nop
0x1800222f0  mov     ebx, [rsi+10h]
0x1800222f3  call    ?GetInstance@OrchestratorSingleton@@SAAEAV1@XZ; OrchestratorSingleton::GetInstance(void)
0x1800222f8  mov     edx, ebx; unsigned int
0x1800222fa  mov     rcx, rax; this
0x1800222fd  call    ?SignalModuleFinished@OrchestratorSingleton@@QEAAXI@Z; OrchestratorSingleton::SignalModuleFinished(uint)
0x180022302  nop
0x180022303  lea     rcx, [rsp+198h+var_118]; this
0x18002230b  call    ??1ThreadFailureCallbackHolder@details@wil@@QEAA@XZ; wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder(void)
0x180022310  cmp     [rsp+198h+var_120], 0
0x180022315  jz      short loc_180022330
0x180022317  mov     rbx, [rsp+198h+lpMem]
0x18002231c  call    cs:__imp_GetProcessHeap
0x180022322  mov     r8, rbx; lpMem
0x180022325  xor     edx, edx; dwFlags
0x180022327  mov     rcx, rax; hHeap
0x18002232a  call    cs:__imp_HeapFree
0x180022330  mov     eax, r14d
0x180022333  jmp     loc_1800226CD
0x180022338  mov     [rsp+198h+var_147], 1
0x18002233d  xorps   xmm0, xmm0
0x180022340  xor     eax, eax
0x180022342  movups  [rsp+198h+var_160], xmm0
0x180022347  mov     [rsp+198h+var_150], rax
0x18002234c  lea     r15, [rsi+18h]
0x180022350  mov     [rsp+198h+var_D8], r15
0x180022358  mov     rcx, [r15]
0x18002235b  mov     eax, [rcx+10h]
0x18002235e  mov     [rsp+198h+var_D0], eax
0x180022365  xor     eax, eax
0x180022367  mov     [rsp+198h+var_CC], eax
0x18002236e  mov     rax, [rcx+8]
0x180022372  mov     [rsp+198h+var_C8], rax
0x18002237a  mov     rax, [rsi+8]
0x18002237e  mov     [rsp+198h+var_C0], rax
0x180022386  mov     rax, [rsi]
0x180022389  mov     [rsp+198h+var_B8], rax
0x180022391  lea     rax, ?WinDiagExecutionCallback@ModuleHandler@@SAXPEBU_WINDIAG_CALLBACK_INFO@@PEAU_WINDIAG_VALUE@@@Z; ModuleHandler::WinDiagExecutionCallback(_WINDIAG_CALLBACK_INFO const *,_WINDIAG_VALUE *)
0x180022398  mov     [rsp+198h+var_B0], rax
0x1800223a0  mov     [rsp+198h+var_A8], rsi
0x1800223a8  lea     r8, [rsp+198h+var_160]
0x1800223ad  lea     rdx, [rsp+198h+var_D0]
0x1800223b5  mov     rcx, [rcx]
0x1800223b8  mov     rax, cs:?WinDiag@@3U_unnamed_type_WinDiag_@@A; _unnamed_type_WinDiag_ WinDiag
0x1800223bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800223c4  mov     r14d, eax
0x1800223c7  mov     [rsp+198h+var_168], eax
0x1800223cb  lea     rax, [rsp+198h+var_160]
0x1800223d0  mov     [rsp+198h+var_80], rax
0x1800223d8  mov     [rsp+198h+var_78], 1
0x1800223e0  cmp     r14d, 80045007h
0x1800223e7  jnz     short loc_18002244C
0x1800223e9  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_BugFixes5D@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_BugFixes5D@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFixes5D> `wil::Feature<__WilFeatureTraits_Feature_BugFixes5D>::GetImpl(void)'::`2'::impl
0x1800223f0  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_BugFixes5D@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFixes5D>::__private_IsEnabled(void)
0x1800223f5  test    al, al
0x1800223f7  jnz     short loc_180022402
0x1800223f9  mov     rcx, rbx
0x1800223fc  call    ?Stop@?$ActivityBase@VWhesvcTelemetryProvider@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<WhesvcTelemetryProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x180022401  nop
0x180022402  lea     rcx, [rsp+198h+var_160]
0x180022407  mov     rax, cs:qword_180034DE0
0x18002240e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022413  nop
0x180022414  call    cs:__imp_CoUninitialize
0x18002241a  nop
0x18002241b  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_BugFixes5D@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_BugFixes5D@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFixes5D> `wil::Feature<__WilFeatureTraits_Feature_BugFixes5D>::GetImpl(void)'::`2'::impl
0x180022422  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_BugFixes5D@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFixes5D>::__private_IsEnabled(void)
0x180022427  test    al, al
0x180022429  jz      short loc_180022434
0x18002242b  mov     rcx, rbx
0x18002242e  call    ?Stop@?$ActivityBase@VWhesvcTelemetryProvider@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<WhesvcTelemetryProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x180022433  nop
0x180022434  mov     ebx, [rsi+10h]
0x180022437  call    ?GetInstance@OrchestratorSingleton@@SAAEAV1@XZ; OrchestratorSingleton::GetInstance(void)
0x18002243c  mov     edx, ebx; unsigned int
0x18002243e  mov     rcx, rax; this
0x180022441  call    ?SignalModuleFinished@OrchestratorSingleton@@QEAAXI@Z; OrchestratorSingleton::SignalModuleFinished(uint)
0x180022446  nop
0x180022447  jmp     loc_18002269E
0x18002244c  test    r14d, r14d
0x18002244f  jns     loc_1800225AC
0x180022455  xorps   xmm0, xmm0
0x180022458  movups  [rsp+198h+var_70], xmm0
0x180022460  movdqa  xmm1, cs:__xmm@000000000000000f0000000000000000
0x180022468  movdqu  [rsp+198h+var_60], xmm1
0x180022471  mov     byte ptr [rsp+198h+var_70], 0
0x180022479  lea     rax, aNA; "<n/a>"
0x180022480  mov     [rsp+198h+var_140], rax
0x180022485  cmp     dword ptr [rsp+198h+var_160], 4
0x18002248a  jnz     loc_180022524
0x180022490  mov     rdx, qword ptr [rsp+198h+var_160+8]
0x180022495  test    rdx, rdx
0x180022498  jz      loc_180022524
0x18002249e  movups  [rsp+198h+var_50], xmm0
0x1800224a6  xorps   xmm1, xmm1
0x1800224a9  movdqu  [rsp+198h+var_40], xmm1
0x1800224b2  mov     r8d, dword ptr [rsp+198h+var_150]
0x1800224b7  lea     rcx, [rsp+198h+var_50]
0x1800224bf  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x1800224c4  lea     rdx, [rsp+198h+var_50]
0x1800224cc  lea     rcx, [rsp+198h+var_70]
0x1800224d4  call    ??4?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::string::operator=(std::string &&)
0x1800224d9  lea     rcx, [rsp+198h+var_50]
0x1800224e1  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x1800224e6  lea     rax, [rsp+198h+var_70]
0x1800224ee  cmp     qword ptr [rsp+198h+var_60+8], 0Fh
0x1800224f7  cmova   rax, qword ptr [rsp+198h+var_70]
0x180022500  mov     [rsp+198h+var_140], rax
0x180022505  jmp     short loc_180022524
0x180022507  mov     r14d, [rsp+198h+var_168]
0x18002250c  mov     rsi, [rsp+198h+var_E8]
0x180022514  mov     rbx, [rsp+198h+var_E0]
0x18002251c  mov     r15, [rsp+198h+var_D8]
0x180022524  mov     rdx, [r15]
0x180022527  lea     r8, [rsp+198h+var_140]
0x18002252c  mov     rdx, [rdx]
0x18002252f  mov     rcx, rbx
0x180022532  call    ??$ModuleFailureDetails@AEAPEBDAEAPEBD@WhesvcModuleActivity@WhesvcTelemetryProvider@@QEAAXAEAPEBD0@Z; WhesvcTelemetryProvider::WhesvcModuleActivity::ModuleFailureDetails<char const * &,char const * &>(char const * &,char const * &)
0x180022537  mov     rcx, [rsp+198h]; this
0x18002253f  mov     r9d, r14d; char *
0x180022542  lea     r8, aPcshellBaseWhe_2; "pcshell\\base\\whesvc\\lib\\modulehandl"...
0x180022549  mov     edx, 1F5h; void *
0x18002254e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180022553  nop
0x180022554  lea     rcx, [rsp+198h+var_70]
0x18002255c  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x180022561  nop
0x180022562  lea     rcx, [rsp+198h+var_160]
0x180022567  mov     rax, cs:qword_180034DE0
0x18002256e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022573  nop
0x180022574  call    cs:__imp_CoUninitialize
0x18002257a  nop
0x18002257b  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_BugFixes5D@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_BugFixes5D@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFixes5D> `wil::Feature<__WilFeatureTraits_Feature_BugFixes5D>::GetImpl(void)'::`2'::impl
0x180022582  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_BugFixes5D@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFixes5D>::__private_IsEnabled(void)
0x180022587  test    al, al
0x180022589  jz      short loc_180022594
0x18002258b  mov     rcx, rbx
0x18002258e  call    ?Stop@?$ActivityBase@VWhesvcTelemetryProvider@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<WhesvcTelemetryProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x180022593  nop
0x180022594  mov     ebx, [rsi+10h]
0x180022597  call    ?GetInstance@OrchestratorSingleton@@SAAEAV1@XZ; OrchestratorSingleton::GetInstance(void)
0x18002259c  mov     edx, ebx; unsigned int
0x18002259e  mov     rcx, rax; this
0x1800225a1  call    ?SignalModuleFinished@OrchestratorSingleton@@QEAAXI@Z; OrchestratorSingleton::SignalModuleFinished(uint)
0x1800225a6  nop
0x1800225a7  jmp     loc_180022303
0x1800225ac  cmp     dword ptr [rsp+198h+var_160], 5
0x1800225b1  jnz     loc_180022640
0x1800225b7  mov     [rsp+198h+var_168], 0
0x1800225bf  xorps   xmm0, xmm0
0x1800225c2  xor     eax, eax
0x1800225c4  movups  [rsp+198h+var_70], xmm0
0x1800225cc  mov     qword ptr [rsp+198h+var_60], rax
0x1800225d4  lea     r9, [rsp+198h+var_168]
0x1800225d9  lea     r8, [rsp+198h+var_70]
0x1800225e1  xor     edx, edx
0x1800225e3  mov     rcx, qword ptr [rsp+198h+var_160+8]
0x1800225e8  mov     rax, cs:qword_180034DD8
0x1800225ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800225f4  mov     r14d, eax
0x1800225f7  test    eax, eax
0x1800225f9  js      loc_1800226EB
0x1800225ff  cmp     [rsp+198h+var_168], 0
0x180022604  jnz     short loc_18002262B
0x180022606  mov     ecx, [rsi+20h]; dwMilliseconds
0x180022609  test    ecx, ecx
0x18002260b  jz      short loc_180022614
0x18002260d  call    cs:__imp_Sleep
0x180022613  nop
0x180022614  lea     rcx, [rsp+198h+var_70]
0x18002261c  mov     rax, cs:qword_180034DE0
0x180022623  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022628  nop
0x180022629  jmp     short loc_1800225B7
0x18002262b  lea     rcx, [rsp+198h+var_70]
0x180022633  mov     rax, cs:qword_180034DE0
0x18002263a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002263f  nop
0x180022640  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_BugFixes5D@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_BugFixes5D@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFixes5D> `wil::Feature<__WilFeatureTraits_Feature_BugFixes5D>::GetImpl(void)'::`2'::impl
0x180022647  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_BugFixes5D@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFixes5D>::__private_IsEnabled(void)
0x18002264c  test    al, al
0x18002264e  jnz     short loc_180022659
0x180022650  mov     rcx, rbx
0x180022653  call    ?Stop@?$ActivityBase@VWhesvcTelemetryProvider@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<WhesvcTelemetryProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x180022658  nop
0x180022659  lea     rcx, [rsp+198h+var_160]
0x18002265e  mov     rax, cs:qword_180034DE0
0x180022665  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002266a  nop
0x18002266b  call    cs:__imp_CoUninitialize
0x180022671  nop
0x180022672  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_BugFixes5D@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_BugFixes5D@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFixes5D> `wil::Feature<__WilFeatureTraits_Feature_BugFixes5D>::GetImpl(void)'::`2'::impl
0x180022679  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_BugFixes5D@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFixes5D>::__private_IsEnabled(void)
0x18002267e  test    al, al
0x180022680  jz      short loc_18002268B
0x180022682  mov     rcx, rbx
0x180022685  call    ?Stop@?$ActivityBase@VWhesvcTelemetryProvider@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<WhesvcTelemetryProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x18002268a  nop
0x18002268b  mov     ebx, [rsi+10h]
0x18002268e  call    ?GetInstance@OrchestratorSingleton@@SAAEAV1@XZ; OrchestratorSingleton::GetInstance(void)
0x180022693  mov     edx, ebx; unsigned int
0x180022695  mov     rcx, rax; this
0x180022698  call    ?SignalModuleFinished@OrchestratorSingleton@@QEAAXI@Z; OrchestratorSingleton::SignalModuleFinished(uint)
0x18002269d  nop
0x18002269e  lea     rcx, [rsp+198h+var_118]; this
0x1800226a6  call    ??1ThreadFailureCallbackHolder@details@wil@@QEAA@XZ; wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder(void)
0x1800226ab  cmp     [rsp+198h+var_120], 0
0x1800226b0  jz      short loc_1800226CB
0x1800226b2  mov     rbx, [rsp+198h+lpMem]
0x1800226b7  call    cs:__imp_GetProcessHeap
0x1800226bd  mov     r8, rbx; lpMem
0x1800226c0  xor     edx, edx; dwFlags
0x1800226c2  mov     rcx, rax; hHeap
0x1800226c5  call    cs:__imp_HeapFree
0x1800226cb  xor     eax, eax
0x1800226cd  mov     rcx, [rsp+198h+var_30]
0x1800226d5  xor     rcx, rsp; StackCookie
0x1800226d8  call    __security_check_cookie
0x1800226dd  add     rsp, 178h
0x1800226e4  pop     r15
0x1800226e6  pop     r14
0x1800226e8  pop     rsi
0x1800226e9  pop     rbx
0x1800226ea  retn
0x1800226eb  mov     rcx, [rsp+198h]; this
0x1800226f3  mov     r9d, r14d; char *
0x1800226f6  lea     r8, aPcshellBaseWhe_2; "pcshell\\base\\whesvc\\lib\\modulehandl"...
0x1800226fd  mov     edx, 1FFh; void *
0x180022702  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180022707  nop
0x180022708  lea     rcx, [rsp+198h+var_160]
0x18002270d  mov     rax, cs:qword_180034DE0
0x180022714  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022719  nop
0x18002271a  call    cs:__imp_CoUninitialize
0x180022720  nop
0x180022721  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_BugFixes5D@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_BugFixes5D@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFixes5D> `wil::Feature<__WilFeatureTraits_Feature_BugFixes5D>::GetImpl(void)'::`2'::impl
0x180022728  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_BugFixes5D@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFixes5D>::__private_IsEnabled(void)
0x18002272d  test    al, al
0x18002272f  jz      short loc_18002273A
0x180022731  mov     rcx, rbx
0x180022734  call    ?Stop@?$ActivityBase@VWhesvcTelemetryProvider@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<WhesvcTelemetryProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x180022739  nop
0x18002273a  mov     ebx, [rsi+10h]
0x18002273d  call    ?GetInstance@OrchestratorSingleton@@SAAEAV1@XZ; OrchestratorSingleton::GetInstance(void)
0x180022742  mov     edx, ebx; unsigned int
0x180022744  mov     rcx, rax; this
0x180022747  call    ?SignalModuleFinished@OrchestratorSingleton@@QEAAXI@Z; OrchestratorSingleton::SignalModuleFinished(uint)
  ... truncated ...
```
