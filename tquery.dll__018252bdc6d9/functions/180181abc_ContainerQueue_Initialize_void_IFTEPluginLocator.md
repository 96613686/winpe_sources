# ContainerQueue::Initialize(void *,IFTEPluginLocator *)

- ea: `0x180181abc`
- end: `0x180181dad`
- name: `?Initialize@ContainerQueue@@QEAAXPEAXPEAUIFTEPluginLocator@@@Z`
- size: `753`
- prototype: `void __fastcall(PVOID pv, HANDLE hSourceHandle, struct IFTEPluginLocator *)`
- caller_count: `1`
- callee_count: `16`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180203ea0`

## callees

- `0x180038f08`
- `0x1800954d8`
- `0x1800f510c`
- `0x180147154`
- `0x180147190`
- `0x18014d7e0`
- `0x18014d800`
- `0x180181abc`
- `0x180181db4`
- `0x180181e04`
- `0x180181e28`
- `0x180181f74`
- `0x18018203c`
- `0x180188d90`
- `0x18018e800`
- `0x180203d88`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180181d76`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180181d76`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x180181d22`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x180181d22`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180181d41`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180181d41`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180181b40`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180181b49`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180181b40`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180181b49`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180181b75`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180181b75`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180181b06`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180181b06`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x180181bcc`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x180181bcc`
- `api-ms-win-containers-cmclient-l1-2-0!CmsRegisterForContainerNotifications` at `0x180181ceb`
- `api-ms-win-containers-cmclient-l1-2-0!CmsRegisterForContainerNotifications` at `0x180181ceb`
- `api-ms-win-containers-cmclient-l1-5-0!CmsOpenContainer` at `0x180181cb8`
- `api-ms-win-containers-cmclient-l1-5-0!CmsOpenContainer` at `0x180181cb8`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall ContainerQueue::Initialize(char *pv, HANDLE hSourceHandle, struct IFTEPluginLocator *a3)
{
  BOOL (__stdcall *v6)(PINIT_ONCE, PVOID, PVOID *); // rax
  const char *v7; // r9
  HANDLE CurrentProcess; // rbx
  HANDLE v9; // rax
  const char *v10; // r9
  HRESULT v11; // eax
  unsigned int v12; // r8d
  int QueryPipeNameForContainer; // eax
  struct _RTL_CRITICAL_SECTION *v14; // rax
  const wchar_t *v15; // r9
  __int64 v16; // rdx
  int v17; // eax
  int v18; // eax
  struct _TP_WORK *ThreadpoolWork; // rbx
  const char *v20; // r9
  struct _TP_WORK *v21; // rsi
  int dwDesiredAccess; // [rsp+20h] [rbp-E0h]
  wchar_t *v23; // [rsp+40h] [rbp-C0h] BYREF
  wchar_t **v24; // [rsp+48h] [rbp-B8h] BYREF
  HANDLE TargetHandle; // [rsp+50h] [rbp-B0h] BYREF
  char v26; // [rsp+58h] [rbp-A8h]
  _QWORD v27[2]; // [rsp+60h] [rbp-A0h] BYREF
  wchar_t v28[264]; // [rsp+70h] [rbp-90h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2B8h] [rbp+1B8h]

  v6 = (BOOL (__stdcall *)(PINIT_ONCE, PVOID, PVOID *))lambda_fdcaeea7c7dbb89a6a8a81b57f5901d8_::operator_int____cdecl____RTL_RUN_ONCE___void___void_____();
  if ( !InitOnceExecuteOnce(&InitOnce, v6, 0, 0) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x98,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\tquery\\cifrmwrk\\queryserver.cxx",
      v7);
  v24 = (wchar_t **)(pv + 56);
  TargetHandle = 0;
  v26 = 1;
  CurrentProcess = GetCurrentProcess();
  v9 = GetCurrentProcess();
  if ( !DuplicateHandle(v9, hSourceHandle, CurrentProcess, &TargetHandle, 0, 0, 2u) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0xA1,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\tquery\\cifrmwrk\\queryserver.cxx",
      v10);
  wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>(&v24);
  v23 = 0;
  v24 = &v23;
  TargetHandle = 0;
  v26 = 1;
  v11 = StringFromCLSID((const IID *const)(pv + 20), (LPOLESTR *)&TargetHandle);
  if ( v11 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xA4,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\tquery\\cifrmwrk\\queryserver.cxx",
      (const char *)(unsigned int)v11,
      dwDesiredAccess);
  wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>(&v24);
  QueryPipeNameForContainer = GetQueryPipeNameForContainer(v23, v28, v12);
  if ( QueryPipeNameForContainer < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xA7,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\tquery\\cifrmwrk\\queryserver.cxx",
      (const char *)(unsigned int)QueryPipeNameForContainer,
      dwDesiredAccess);
  v14 = (struct _RTL_CRITICAL_SECTION *)operator new(0x1B8u, (const struct std::nothrow_t *)&std::nothrow);
  v27[0] = v14;
  if ( v14 )
    v14 = (struct _RTL_CRITICAL_SECTION *)CRequestQueue::CRequestQueue(
                                            v14,
                                            (struct CEventSem *)(pv + 72),
                                            a3,
                                            v15,
                                            v28,
                                            *((void **)pv + 7));
  v16 = *((_QWORD *)pv + 8);
  *((_QWORD *)pv + 8) = v14;
  if ( v16 )
    std::default_delete<CRequestQueue>::operator()();
  if ( !*((_QWORD *)pv + 8) )
    wil::details::in1diag3::_Throw_NullAlloc(
      retaddr,
      (void *)0xAA,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\tquery\\cifrmwrk\\queryserver.cxx",
      (const char *)v15);
  wil::details::unique_storage<wil::details::resource_policy<void *,void (void * &),&void ContainerHelperDetails::CloseContainer(void * &),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(
    pv + 40,
    0);
  v17 = CmsOpenContainer(pv + 20, 22, 97, pv + 40);
  if ( v17 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xB0,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\tquery\\cifrmwrk\\queryserver.cxx",
      (const char *)(unsigned int)v17,
      dwDesiredAccess);
  v18 = CmsRegisterForContainerNotifications(
          *((_QWORD *)pv + 5),
          &lambda_38f48f0a5ccff0caa0b151288d4e7c01_::_lambda_invoker_cdecl_,
          pv);
  if ( v18 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xBA,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\tquery\\cifrmwrk\\queryserver.cxx",
      (const char *)(unsigned int)v18,
      dwDesiredAccess);
  ThreadpoolWork = CreateThreadpoolWork(ContainerQueue::s_QueryServerWork, pv, &ContainerQueue::s_threadPoolEnv);
  v21 = (struct _TP_WORK *)*((_QWORD *)pv + 6);
  if ( v21 )
  {
    wil::last_error_context::last_error_context((wil::last_error_context *)v27);
    CloseThreadpoolWork(v21);
    wil::last_error_context::~last_error_context((wil::last_error_context *)v27);
  }
  *((_QWORD *)pv + 6) = ThreadpoolWork;
  if ( !ThreadpoolWork )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0xBE,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\tquery\\cifrmwrk\\queryserver.cxx",
      v20);
  SubmitThreadpoolWork(ThreadpoolWork);
  XCoMem<unsigned char>::~XCoMem<unsigned char>(&v23);
}

```

## disassembly

```asm
0x180181abc  mov     [rsp-8+arg_18], rbx
0x180181ac1  push    rbp
0x180181ac2  push    rsi
0x180181ac3  push    rdi
0x180181ac4  push    r14
0x180181ac6  push    r15
0x180181ac8  lea     rbp, [rsp-190h]
0x180181ad0  sub     rsp, 290h
0x180181ad7  mov     rax, cs:__security_cookie
0x180181ade  xor     rax, rsp
0x180181ae1  mov     [rbp+1B0h+var_30], rax
0x180181ae8  mov     r15, r8
0x180181aeb  mov     rsi, rdx
0x180181aee  mov     rdi, rcx
0x180181af1  call    _lambda_fdcaeea7c7dbb89a6a8a81b57f5901d8___operator_int____cdecl____RTL_RUN_ONCE___void___void_____
0x180181af6  mov     rdx, rax; InitFn
0x180181af9  xor     r9d, r9d; Context
0x180181afc  xor     r8d, r8d; Parameter
0x180181aff  lea     rcx, InitOnce; InitOnce
0x180181b06  call    cs:__imp_InitOnceExecuteOnce
0x180181b0c  mov     rcx, [rbp+1B8h]; this
0x180181b13  test    eax, eax
0x180181b15  jnz     short loc_180181B29
0x180181b17  lea     r8, aOnecoreuapBase_100; "onecoreuap\\base\\appmodel\\search\\tqu"...
0x180181b1e  mov     edx, 98h; void *
0x180181b23  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x180181b29  lea     r14, [rdi+38h]
0x180181b2d  mov     [rsp+2B0h+var_268], r14
0x180181b32  mov     [rsp+2B0h+TargetHandle], 0
0x180181b3b  mov     [rsp+2B0h+var_258], 1
0x180181b40  call    cs:__imp_GetCurrentProcess
0x180181b46  mov     rbx, rax
0x180181b49  call    cs:__imp_GetCurrentProcess
0x180181b4f  mov     [rsp+2B0h+dwOptions], 2; dwOptions
0x180181b57  mov     [rsp+2B0h+bInheritHandle], 0; bInheritHandle
0x180181b5f  mov     [rsp+2B0h+dwDesiredAccess], 0; int
0x180181b67  lea     r9, [rsp+2B0h+TargetHandle]; lpTargetHandle
0x180181b6c  mov     r8, rbx; hTargetProcessHandle
0x180181b6f  mov     rdx, rsi; hSourceHandle
0x180181b72  mov     rcx, rax; hSourceProcessHandle
0x180181b75  call    cs:__imp_DuplicateHandle
0x180181b7b  mov     rcx, [rbp+1B8h]; this
0x180181b82  test    eax, eax
0x180181b84  jnz     short loc_180181B98
0x180181b86  lea     r8, aOnecoreuapBase_100; "onecoreuap\\base\\appmodel\\search\\tqu"...
0x180181b8d  mov     edx, 0A1h; void *
0x180181b92  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x180181b98  lea     rcx, [rsp+2B0h+var_268]
0x180181b9d  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>(void)
0x180181ba2  mov     [rsp+2B0h+var_270], 0
0x180181bab  lea     rax, [rsp+2B0h+var_270]
0x180181bb0  mov     [rsp+2B0h+var_268], rax
0x180181bb5  mov     [rsp+2B0h+TargetHandle], 0
0x180181bbe  mov     [rsp+2B0h+var_258], 1
0x180181bc3  lea     rdx, [rsp+2B0h+TargetHandle]; lplpsz
0x180181bc8  lea     rcx, [rdi+14h]; rclsid
0x180181bcc  call    cs:__imp_StringFromCLSID
0x180181bd2  mov     rcx, [rbp+1B8h]; this
0x180181bd9  test    eax, eax
0x180181bdb  jns     short loc_180181BF2
0x180181bdd  mov     r9d, eax; char *
0x180181be0  lea     r8, aOnecoreuapBase_100; "onecoreuap\\base\\appmodel\\search\\tqu"...
0x180181be7  mov     edx, 0A4h; void *
0x180181bec  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180181bf2  lea     rcx, [rsp+2B0h+var_268]
0x180181bf7  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>(void)
0x180181bfc  lea     rdx, [rsp+2B0h+var_240]; wchar_t *
0x180181c01  mov     rcx, [rsp+2B0h+var_270]; wchar_t *
0x180181c06  call    ?GetQueryPipeNameForContainer@@YAJPEB_WPEA_WK@Z; GetQueryPipeNameForContainer(wchar_t const *,wchar_t *,ulong)
0x180181c0b  mov     rcx, [rbp+1B8h]; this
0x180181c12  test    eax, eax
0x180181c14  jns     short loc_180181C2B
0x180181c16  mov     r9d, eax; char *
0x180181c19  lea     r8, aOnecoreuapBase_100; "onecoreuap\\base\\appmodel\\search\\tqu"...
0x180181c20  mov     edx, 0A7h; void *
0x180181c25  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180181c2b  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180181c32  mov     ecx, 1B8h; unsigned __int64
0x180181c37  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180181c3c  mov     [rsp+2B0h+var_250], rax
0x180181c41  test    rax, rax
0x180181c44  jz      short loc_180181C68
0x180181c46  lea     rdx, [rdi+48h]; struct CEventSem *
0x180181c4a  mov     rcx, [r14]
0x180181c4d  mov     qword ptr [rsp+2B0h+bInheritHandle], rcx; void *
0x180181c52  lea     rcx, [rsp+2B0h+var_240]
0x180181c57  mov     qword ptr [rsp+2B0h+dwDesiredAccess], rcx; int
0x180181c5c  mov     r8, r15; struct IFTEPluginLocator *
0x180181c5f  mov     rcx, rax; lpCriticalSection
0x180181c62  call    ??0CRequestQueue@@QEAA@AEAVCEventSem@@PEAUIFTEPluginLocator@@PEB_W2PEAX@Z; CRequestQueue::CRequestQueue(CEventSem &,IFTEPluginLocator *,wchar_t const *,wchar_t const *,void *)
0x180181c67  nop
0x180181c68  mov     rdx, [rdi+40h]
0x180181c6c  mov     [rdi+40h], rax
0x180181c70  test    rdx, rdx
0x180181c73  jz      short loc_180181C7A
0x180181c75  call    ??R?$default_delete@VCRequestQueue@@@std@@QEBAXPEAVCRequestQueue@@@Z; std::default_delete<CRequestQueue>::operator()(CRequestQueue *)
0x180181c7a  mov     rcx, [rbp+1B8h]; this
0x180181c81  cmp     qword ptr [rdi+40h], 0
0x180181c86  jnz     short loc_180181C9A
0x180181c88  lea     r8, aOnecoreuapBase_100; "onecoreuap\\base\\appmodel\\search\\tqu"...
0x180181c8f  mov     edx, 0AAh; void *
0x180181c94  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
0x180181c9a  lea     rbx, [rdi+28h]
0x180181c9e  xor     edx, edx
0x180181ca0  mov     rcx, rbx
0x180181ca3  call    ?reset@?$unique_storage@U?$resource_policy@PEAX$$A6AXAEAPEAX@Z$1?CloseContainer@ContainerHelperDetails@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::resource_policy<void *,void (void * &),&ContainerHelperDetails::CloseContainer(void * &),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(void *)
0x180181ca8  mov     r9, rbx
0x180181cab  mov     edx, 16h
0x180181cb0  lea     r8d, [rdx+4Bh]
0x180181cb4  lea     rcx, [rdi+14h]
0x180181cb8  call    cs:__imp_CmsOpenContainer
0x180181cbe  mov     rcx, [rbp+1B8h]; this
0x180181cc5  test    eax, eax
0x180181cc7  jns     short loc_180181CDE
0x180181cc9  mov     r9d, eax; char *
0x180181ccc  lea     r8, aOnecoreuapBase_100; "onecoreuap\\base\\appmodel\\search\\tqu"...
0x180181cd3  mov     edx, 0B0h; void *
0x180181cd8  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180181cde  mov     r8, rdi
0x180181ce1  lea     rdx, _lambda_38f48f0a5ccff0caa0b151288d4e7c01____lambda_invoker_cdecl_
0x180181ce8  mov     rcx, [rbx]
0x180181ceb  call    cs:__imp_CmsRegisterForContainerNotifications
0x180181cf1  mov     rcx, [rbp+1B8h]; this
0x180181cf8  test    eax, eax
0x180181cfa  jns     short loc_180181D11
0x180181cfc  mov     r9d, eax; char *
0x180181cff  lea     r8, aOnecoreuapBase_100; "onecoreuap\\base\\appmodel\\search\\tqu"...
0x180181d06  mov     edx, 0BAh; void *
0x180181d0b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180181d11  lea     r8, ?s_threadPoolEnv@ContainerQueue@@0U_TP_CALLBACK_ENVIRON_V3@@A; pcbe
0x180181d18  mov     rdx, rdi; pv
0x180181d1b  lea     rcx, ?s_QueryServerWork@ContainerQueue@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x180181d22  call    cs:__imp_CreateThreadpoolWork
0x180181d28  mov     rbx, rax
0x180181d2b  mov     rsi, [rdi+30h]
0x180181d2f  test    rsi, rsi
0x180181d32  jz      short loc_180181D51
0x180181d34  lea     rcx, [rsp+2B0h+var_250]; this
0x180181d39  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180181d3e  mov     rcx, rsi; pwk
0x180181d41  call    cs:__imp_CloseThreadpoolWork
0x180181d47  lea     rcx, [rsp+2B0h+var_250]; this
0x180181d4c  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180181d51  mov     [rdi+30h], rbx
0x180181d55  mov     rcx, [rbp+1B8h]; this
0x180181d5c  test    rbx, rbx
0x180181d5f  jnz     short loc_180181D73
0x180181d61  lea     r8, aOnecoreuapBase_100; "onecoreuap\\base\\appmodel\\search\\tqu"...
0x180181d68  mov     edx, 0BEh; void *
0x180181d6d  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x180181d73  mov     rcx, rbx; pwk
0x180181d76  call    cs:__imp_SubmitThreadpoolWork
0x180181d7c  nop
0x180181d7d  lea     rcx, [rsp+2B0h+var_270]
0x180181d82  call    ??1?$XCoMem@E@@QEAA@XZ; XCoMem<uchar>::~XCoMem<uchar>(void)
0x180181d87  mov     rcx, [rbp+1B0h+var_30]
0x180181d8e  xor     rcx, rsp; StackCookie
0x180181d91  call    __security_check_cookie
0x180181d96  mov     rbx, [rsp+2B0h+arg_18]
0x180181d9e  add     rsp, 290h
0x180181da5  pop     r15
0x180181da7  pop     r14
0x180181da9  pop     rdi
0x180181daa  pop     rsi
0x180181dab  pop     rbp
0x180181dac  retn
```
