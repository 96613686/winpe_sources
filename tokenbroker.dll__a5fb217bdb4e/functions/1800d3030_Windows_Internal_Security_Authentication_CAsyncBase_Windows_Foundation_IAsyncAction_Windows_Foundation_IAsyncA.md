# Windows::Internal::Security::Authentication::CAsyncBase<Windows::Foundation::IAsyncAction,Windows::Foundation::IAsyncActionCompletedHandler,Windows::Internal::Security::Authentication::Web::PushCookiesParams,Microsoft::WRL::AsyncCausalityOptions<&ushort const near * const Windows::Internal::Security::Authentication::Web::PushCookiesAsyncActionName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::OnStart(void)

- ea: `0x1800d3030`
- end: `0x1800d3151`
- name: `?OnStart@?$CAsyncBase@UIAsyncAction@Foundation@Windows@@UIAsyncActionCompletedHandler@23@UPushCookiesParams@Web@Authentication@Security@Internal@3@U?$AsyncCausalityOptions@$1?PushCookiesAsyncActionName@Web@Authentication@Security@Internal@Windows@@3QBGB$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Authentication@Security@Internal@Windows@@MEAAJXZ`
- size: `289`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800839c4`
- `0x1800d3030`
- `0x18011b010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800d3104`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800d3104`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x1800d306b`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x1800d306b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d3077`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d30a0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d30d4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d3077`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d30a0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d30d4`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800d312e`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800d312e`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800d3120`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800d3120`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpool` at `0x1800d3092`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpool` at `0x1800d3092`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpool` at `0x1800d313c`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpool` at `0x1800d313c`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800d30c6`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800d30c6`

## pseudocode

```c
__int64 __fastcall Windows::Internal::Security::Authentication::CAsyncBase<Windows::Foundation::IAsyncAction,Windows::Foundation::IAsyncActionCompletedHandler,Windows::Internal::Security::Authentication::Web::PushCookiesParams,Microsoft::WRL::AsyncCausalityOptions<&unsigned short const near * const Windows::Internal::Security::Authentication::Web::PushCookiesAsyncActionName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::OnStart(
        __int64 a1)
{
  void *v1; // r14
  signed int v3; // ebx
  struct _TP_WORK *ThreadpoolWork; // rdi
  HMODULE *v5; // r15
  struct _TP_POOL *Threadpool; // rsi
  signed int LastError; // eax
  signed int v8; // eax
  signed int v9; // eax

  v1 = (void *)(a1 - 16);
  v3 = 0;
  ThreadpoolWork = 0;
  (*(void (__fastcall **)(__int64))(*(_QWORD *)(a1 - 16) + 8LL))(a1 - 16);
  v5 = (HMODULE *)(a1 + 168);
  if ( !GetModuleHandleExW(
          4u,
          (LPCWSTR)Windows::Internal::Security::Authentication::CAsyncBase<Windows::Foundation::IAsyncAction,Windows::Foundation::IAsyncActionCompletedHandler,Windows::Internal::Security::Authentication::Web::PushCookiesParams,Microsoft::WRL::AsyncCausalityOptions<&unsigned short const near * const Windows::Internal::Security::Authentication::Web::PushCookiesAsyncActionName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::WorkerStub,
          (HMODULE *)(a1 + 168)) )
  {
    Threadpool = 0;
    LastError = GetLastError();
    v3 = LastError;
    if ( LastError > 0 )
      v3 = (unsigned __int16)LastError | 0x80070000;
    if ( v3 < 0 )
      goto LABEL_13;
  }
  Threadpool = CreateThreadpool(0);
  if ( !Threadpool )
  {
    v8 = GetLastError();
    v3 = v8;
    if ( v8 > 0 )
      v3 = (unsigned __int16)v8 | 0x80070000;
    if ( v3 < 0 )
      goto LABEL_13;
  }
  ThreadpoolWork = CreateThreadpoolWork(
                     Windows::Internal::Security::Authentication::CAsyncBase<Windows::Foundation::IAsyncAction,Windows::Foundation::IAsyncActionCompletedHandler,Windows::Internal::Security::Authentication::Web::PushCookiesParams,Microsoft::WRL::AsyncCausalityOptions<&unsigned short const near * const Windows::Internal::Security::Authentication::Web::PushCookiesAsyncActionName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::WorkerStub,
                     v1,
                     0);
  if ( ThreadpoolWork )
    goto LABEL_16;
  v9 = GetLastError();
  v3 = v9;
  if ( v9 > 0 )
    v3 = (unsigned __int16)v9 | 0x80070000;
  if ( v3 >= 0 )
  {
LABEL_16:
    SubmitThreadpoolWork(ThreadpoolWork);
  }
  else
  {
LABEL_13:
    (*(void (__fastcall **)(void *))(*(_QWORD *)v1 + 16LL))(v1);
    if ( *v5 )
    {
      FreeLibrary(*v5);
      *v5 = 0;
    }
    Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncCausalityOptions<&unsigned short const near * const Windows::Internal::Security::Authentication::Web::DeleteAccountAsyncActionName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TryTransitionToError(
      a1,
      (unsigned int)v3);
  }
  if ( ThreadpoolWork )
    CloseThreadpoolWork(ThreadpoolWork);
  if ( Threadpool )
    CloseThreadpool(Threadpool);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x1800d3030  push    rbx
0x1800d3032  push    rbp
0x1800d3033  push    rsi
0x1800d3034  push    rdi
0x1800d3035  push    r14
0x1800d3037  push    r15
0x1800d3039  sub     rsp, 28h
0x1800d303d  lea     r14, [rcx-10h]
0x1800d3041  mov     rbp, rcx
0x1800d3044  mov     rax, [r14]
0x1800d3047  mov     rcx, r14
0x1800d304a  xor     ebx, ebx
0x1800d304c  xor     edi, edi
0x1800d304e  mov     rax, [rax+8]
0x1800d3052  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d3057  lea     r15, [rbp+0A8h]
0x1800d305e  mov     r8, r15; phModule
0x1800d3061  lea     rdx, ?WorkerStub@?$CAsyncBase@UIAsyncAction@Foundation@Windows@@UIAsyncActionCompletedHandler@23@UPushCookiesParams@Web@Authentication@Security@Internal@3@U?$AsyncCausalityOptions@$1?PushCookiesAsyncActionName@Web@Authentication@Security@Internal@Windows@@3QBGB$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Authentication@Security@Internal@Windows@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; lpModuleName
0x1800d3068  lea     ecx, [rbx+4]; dwFlags
0x1800d306b  call    cs:__imp_GetModuleHandleExW
0x1800d3071  test    eax, eax
0x1800d3073  jnz     short loc_1800D3090
0x1800d3075  xor     esi, esi
0x1800d3077  call    cs:__imp_GetLastError
0x1800d307d  mov     ebx, eax
0x1800d307f  test    eax, eax
0x1800d3081  jle     short loc_1800D308C
0x1800d3083  movzx   ebx, ax
0x1800d3086  or      ebx, 80070000h
0x1800d308c  test    ebx, ebx
0x1800d308e  js      short loc_1800D30ED
0x1800d3090  xor     ecx, ecx; reserved
0x1800d3092  call    cs:__imp_CreateThreadpool
0x1800d3098  mov     rsi, rax
0x1800d309b  test    rax, rax
0x1800d309e  jnz     short loc_1800D30B9
0x1800d30a0  call    cs:__imp_GetLastError
0x1800d30a6  mov     ebx, eax
0x1800d30a8  test    eax, eax
0x1800d30aa  jle     short loc_1800D30B5
0x1800d30ac  movzx   ebx, ax
0x1800d30af  or      ebx, 80070000h
0x1800d30b5  test    ebx, ebx
0x1800d30b7  js      short loc_1800D30ED
0x1800d30b9  xor     r8d, r8d; pcbe
0x1800d30bc  lea     rcx, ?WorkerStub@?$CAsyncBase@UIAsyncAction@Foundation@Windows@@UIAsyncActionCompletedHandler@23@UPushCookiesParams@Web@Authentication@Security@Internal@3@U?$AsyncCausalityOptions@$1?PushCookiesAsyncActionName@Web@Authentication@Security@Internal@Windows@@3QBGB$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Authentication@Security@Internal@Windows@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x1800d30c3  mov     rdx, r14; pv
0x1800d30c6  call    cs:__imp_CreateThreadpoolWork
0x1800d30cc  mov     rdi, rax
0x1800d30cf  test    rax, rax
0x1800d30d2  jnz     short loc_1800D311D
0x1800d30d4  call    cs:__imp_GetLastError
0x1800d30da  mov     ebx, eax
0x1800d30dc  test    eax, eax
0x1800d30de  jle     short loc_1800D30E9
0x1800d30e0  movzx   ebx, ax
0x1800d30e3  or      ebx, 80070000h
0x1800d30e9  test    ebx, ebx
0x1800d30eb  jns     short loc_1800D311D
0x1800d30ed  mov     rax, [r14]
0x1800d30f0  mov     rcx, r14
0x1800d30f3  mov     rax, [rax+10h]
0x1800d30f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d30fc  mov     rcx, [r15]; hLibModule
0x1800d30ff  test    rcx, rcx
0x1800d3102  jz      short loc_1800D3111
0x1800d3104  call    cs:__imp_FreeLibrary
0x1800d310a  mov     qword ptr [r15], 0
0x1800d3111  mov     edx, ebx
0x1800d3113  mov     rcx, rbp
0x1800d3116  call    ?TryTransitionToError@?$AsyncBase@UIAsyncActionCompletedHandler@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncCausalityOptions@$1?DeleteAccountAsyncActionName@Web@Authentication@Security@Internal@Windows@@3QBGB$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@IEAA_NJW4CancelTransitionPolicy@23@PEAX@Z; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncCausalityOptions<&ushort const near * const Windows::Internal::Security::Authentication::Web::DeleteAccountAsyncActionName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TryTransitionToError(long,Microsoft::WRL::CancelTransitionPolicy,void *)
0x1800d311b  jmp     short loc_1800D3126
0x1800d311d  mov     rcx, rdi; pwk
0x1800d3120  call    cs:__imp_SubmitThreadpoolWork
0x1800d3126  test    rdi, rdi
0x1800d3129  jz      short loc_1800D3134
0x1800d312b  mov     rcx, rdi; pwk
0x1800d312e  call    cs:__imp_CloseThreadpoolWork
0x1800d3134  test    rsi, rsi
0x1800d3137  jz      short loc_1800D3142
0x1800d3139  mov     rcx, rsi; ptpp
0x1800d313c  call    cs:__imp_CloseThreadpool
0x1800d3142  mov     eax, ebx
0x1800d3144  add     rsp, 28h
0x1800d3148  pop     r15
0x1800d314a  pop     r14
0x1800d314c  pop     rdi
0x1800d314d  pop     rsi
0x1800d314e  pop     rbp
0x1800d314f  pop     rbx
0x1800d3150  retn
```
