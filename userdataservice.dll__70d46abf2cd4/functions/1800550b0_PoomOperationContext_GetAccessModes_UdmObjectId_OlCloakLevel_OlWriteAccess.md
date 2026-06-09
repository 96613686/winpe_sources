# PoomOperationContext::GetAccessModes(UdmObjectId,OlCloakLevel *,OlWriteAccess *)

- ea: `0x1800550b0`
- end: `0x180055547`
- name: `?GetAccessModes@PoomOperationContext@@UEAAJUUdmObjectId@@PEAW4OlCloakLevel@@PEAW4OlWriteAccess@@@Z`
- size: `1175`
- prototype: ``
- caller_count: `0`
- callee_count: `12`
- tags: `service_task, broker_com_uri`

## callees

- `0x180008ee8`
- `0x18000ae80`
- `0x1800550b0`
- `0x180059bc8`
- `0x180059cac`
- `0x180069ca8`
- `0x180072ccc`
- `0x18007f77c`
- `0x180097d74`
- `0x1800e482c`
- `0x18012c7b0`
- `0x18012e010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x1800554c5`
- `msvcrt!_wcsicmp` at `0x1800554dd`
- `msvcrt!_wcsicmp` at `0x1800554f5`
- `msvcrt!_wcsicmp` at `0x1800554c5`
- `msvcrt!_wcsicmp` at `0x1800554dd`
- `msvcrt!_wcsicmp` at `0x1800554f5`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x1800553f5`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18005543a`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x1800553f5`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18005543a`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x1800551f2`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180055289`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180055352`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x1800551f2`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180055289`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180055352`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x1800552db`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x1800552db`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005519f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180055457`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005550c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005519f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180055457`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005550c`

## pseudocode

```c
__int64 __fastcall PoomOperationContext::GetAccessModes(_QWORD *a1, unsigned int *a2, int *a3, _DWORD *a4)
{
  unsigned int v4; // esi
  __int64 v6; // rcx
  int v9; // eax
  __int64 v10; // r8
  unsigned int v11; // edi
  int v13; // eax
  __int64 v14; // r8
  unsigned int v15; // edi
  HLOCAL v16; // rcx
  StorePropertyCache *v17; // rbx
  int PropertiesForStore; // eax
  __int64 v19; // rcx
  __int64 v20; // r8
  unsigned int v21; // ebx
  _DWORD *v22; // rax
  int v23; // eax
  int v24; // eax
  const wchar_t *v25; // rbx
  WINBOOL fPending; // [rsp+30h] [rbp-50h] BYREF
  HLOCAL hMem; // [rsp+38h] [rbp-48h] BYREF
  __int64 v28; // [rsp+40h] [rbp-40h] BYREF
  LPVOID v29; // [rsp+48h] [rbp-38h] BYREF
  LPVOID Context; // [rsp+50h] [rbp-30h] BYREF
  WINBOOL v31[2]; // [rsp+58h] [rbp-28h] BYREF
  _DWORD v32[4]; // [rsp+60h] [rbp-20h] BYREF

  v4 = *a2;
  v6 = a1[5];
  v28 = 0;
  v9 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v6 + 64LL))(v6, v4, &v28);
  v11 = v9;
  if ( v9 < 0 )
  {
    Log_HREvent_16((unsigned int)v9, 1, v10, 847);
    ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(&v28);
    return v11;
  }
  v32[0] = (*(__int64 (__fastcall **)(_QWORD *))(*a1 + 40LL))(a1);
  v32[1] = (*(__int64 (__fastcall **)(_QWORD *))(*a1 + 48LL))(a1);
  v32[2] = -2106261473;
  v32[3] = 280428555;
  hMem = 0;
  v13 = (*(__int64 (__fastcall **)(__int64, __int64, _DWORD *, _QWORD, HLOCAL *))(*(_QWORD *)v28 + 48LL))(
          v28,
          4,
          v32,
          0,
          &hMem);
  v15 = v13;
  if ( v13 < 0 )
  {
    Log_HREvent_16((unsigned int)v13, 1, v14, 852);
    if ( hMem )
      LocalFree(hMem);
    ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(&v28);
    return v15;
  }
  v16 = hMem;
  if ( (*((_WORD *)hMem + 39) & 0x300) == 0 && *((_DWORD *)hMem + 20) )
  {
    *(_QWORD *)v31 = 0;
    fPending = 0;
    Context = 0;
    InitOnceBeginInitialize(&stru_18015EA68, 0, &fPending, &Context);
    v17 = (StorePropertyCache *)Context;
    if ( !Context )
    {
      v29 = &stru_18015EA68;
      v17 = (StorePropertyCache *)tlx::_LazyImpl<StorePropertyCache,tlx::lazy_construct<StorePropertyCache>,tlx::static_lazy<StorePropertyCache,0,tlx::lazy_construct<StorePropertyCache>>>::_Initializer::_Construct(&v29);
      tlx::_LazyImpl<ComposingStatusChangedEventSink,tlx::lazy_construct<ComposingStatusChangedEventSink>,tlx::static_lazy<ComposingStatusChangedEventSink,0,tlx::lazy_construct<ComposingStatusChangedEventSink>>>::_Initializer::~_Initializer(&v29);
    }
    PropertiesForStore = StorePropertyCache::GetPropertiesForStore(v17, v4, (const struct StorePropertySet **)v31);
    if ( PropertiesForStore < 0 )
      Log_HREvent_16((unsigned int)PropertiesForStore, 0, v20, 858);
    if ( *(_QWORD *)v31 )
      v21 = **(_DWORD **)v31;
    else
      v21 = -1;
    v22 = *(_DWORD **)(wil::details::static_lazy<UserDataServiceTelemetry>::get(
                         v19,
                         _lambda_64251f8b2e64e7c9e2bb8171f69baa1e_::_lambda_invoker_cdecl_)
                     + 8);
    if ( v22 && *v22 )
    {
      Context = 0;
      v31[0] = 0;
      if ( InitOnceBeginInitialize(&`UserDataServiceTelemetry::Instance'::`2'::wrapper, 0, v31, &Context) && v31[0] )
      {
        qword_18015D290 = 0;
        qword_18015D288 = (__int64)&UserDataServiceTelemetry::`vftable';
        Context = &qword_18015D288;
        byte_18015D298 = 0;
        dword_18015D29C = 0;
        InitializeCriticalSectionEx(&stru_18015D2A0, 0, 0);
        qword_18015D2E0 = 0;
        qword_18015D2C8 = (__int64)&qword_18015D2C8;
        qword_18015D2D0 = (__int64)&qword_18015D2C8;
        qword_18015D2D8 = (__int64)&qword_18015D2C8;
        qword_18015D2E8 = (__int64)&qword_18015D2E8;
        qword_18015D2F0 = (__int64)&qword_18015D2E8;
        xmmword_18015D2F8 = 0;
        word_18015D308 = 2048;
        atexit(_lambda_64251f8b2e64e7c9e2bb8171f69baa1e_::_lambda_invoker_cdecl_);
        v29 = 0;
        fPending = 0;
        if ( InitOnceBeginInitialize(&`UserDataServiceProvider::Instance'::`2'::wrapper, 0, &fPending, &v29) && fPending )
        {
          qword_18015D208 = 0;
          v29 = &qword_18015D200;
          qword_18015D200 = (__int64)&UserDataServiceProvider::`vftable';
          byte_18015D210 = 0;
          dword_18015D214 = 0;
          CallbackContext = &`UserDataServiceProvider::StaticHandle::StaticHandle'::`2'::__hInner;
          atexit(_lambda_54f6ef7866792d4b3470b3f7b9ab6fcd_::_lambda_invoker_cdecl_);
          qword_18015D208 = (__int64)CallbackContext;
          byte_18015D210 = 1;
          TraceLoggingRegisterEx_EventRegister_EventSetInformation(CallbackContext);
          dword_18015D214 = 1;
          (*(void (__fastcall **)(__int64 *))(qword_18015D200 + 8))(&qword_18015D200);
          InitOnceComplete(&`UserDataServiceProvider::Instance'::`2'::wrapper, 0, &qword_18015D200);
        }
        qword_18015D290 = *((_QWORD *)v29 + 1);
        byte_18015D298 = 0;
        dword_18015D29C = 1;
        (*(void (__fastcall **)(__int64 *))(qword_18015D288 + 8))(&qword_18015D288);
        InitOnceComplete(&`UserDataServiceTelemetry::Instance'::`2'::wrapper, 0, &qword_18015D288);
      }
      UserDataServiceTelemetry::SkippedSuppressedStore_((UserDataServiceTelemetry *)Context, v4, v21);
    }
    goto LABEL_25;
  }
  v23 = 2;
  if ( (*((_WORD *)hMem + 3) & 0x300) == 0 )
    v23 = *((_DWORD *)hMem + 2);
  *a3 = v23;
  if ( (*((_WORD *)v16 + 15) & 0x300) != 0 )
  {
    v24 = (*(__int64 (__fastcall **)(_QWORD *))(*a1 + 144LL))(a1);
    v16 = hMem;
  }
  else
  {
    v24 = *((_DWORD *)v16 + 8);
  }
  *a4 = v24;
  if ( (*((_WORD *)v16 + 27) & 0x300) == 0 )
  {
    v25 = (const wchar_t *)*((_QWORD *)v16 + 7);
    if ( !_wcsicmp(v25, L"VVM") || !_wcsicmp(v25, L"OMTP11") || !_wcsicmp(v25, L"ALU6") )
    {
LABEL_25:
      if ( hMem )
        LocalFree(hMem);
      if ( v28 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
      return 2147943568LL;
    }
    v16 = hMem;
  }
  if ( v16 )
    LocalFree(v16);
  if ( v28 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
  return 0;
}

```

## disassembly

```asm
0x1800550b0  push    rbp
0x1800550b2  push    rbx
0x1800550b3  push    rsi
0x1800550b4  push    rdi
0x1800550b5  push    r12
0x1800550b7  push    r14
0x1800550b9  push    r15
0x1800550bb  mov     rbp, rsp
0x1800550be  sub     rsp, 80h
0x1800550c5  mov     rax, cs:__security_cookie
0x1800550cc  xor     rax, rsp
0x1800550cf  mov     [rbp+var_10], rax
0x1800550d3  mov     esi, [rdx]
0x1800550d5  mov     rbx, rcx
0x1800550d8  mov     rcx, [rcx+28h]
0x1800550dc  mov     r14, r8
0x1800550df  xor     r12d, r12d
0x1800550e2  lea     r8, [rbp+var_40]
0x1800550e6  mov     [rbp+var_40], r12
0x1800550ea  mov     edx, esi
0x1800550ec  mov     r15, r9
0x1800550ef  mov     rax, [rcx]
0x1800550f2  mov     rax, [rax+40h]
0x1800550f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800550fb  mov     edi, eax
0x1800550fd  test    eax, eax
0x1800550ff  jns     short loc_180055123
0x180055101  mov     edx, 1
0x180055106  mov     r9d, 34Fh
0x18005510c  mov     ecx, eax
0x18005510e  call    Log_HREvent_16
0x180055113  lea     rcx, [rbp+var_40]
0x180055117  call    ??1?$CComPtrBase@UISODACompletionCallback@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(void)
0x18005511c  mov     eax, edi
0x18005511e  jmp     loc_180055529
0x180055123  mov     rax, [rbx]
0x180055126  mov     rcx, rbx
0x180055129  mov     rax, [rax+28h]
0x18005512d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055132  mov     [rbp+var_20], eax
0x180055135  mov     rcx, rbx
0x180055138  mov     rax, [rbx]
0x18005513b  mov     rax, [rax+30h]
0x18005513f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055144  mov     rcx, [rbp+var_40]
0x180055148  lea     rdx, [rbp+hMem]
0x18005514c  mov     [rbp+var_1C], eax
0x18005514f  lea     r8, [rbp+var_20]
0x180055153  mov     [rbp+var_18], 8275001Fh
0x18005515a  xor     r9d, r9d
0x18005515d  mov     [rbp+var_14], 10B7000Bh
0x180055164  mov     [rbp+hMem], r12
0x180055168  mov     rax, [rcx]
0x18005516b  mov     [rsp+80h+var_60], rdx
0x180055170  mov     edx, 4
0x180055175  mov     rax, [rax+30h]
0x180055179  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005517e  mov     edi, eax
0x180055180  test    eax, eax
0x180055182  jns     short loc_1800551B5
0x180055184  mov     edx, 1
0x180055189  mov     r9d, 354h
0x18005518f  mov     ecx, eax
0x180055191  call    Log_HREvent_16
0x180055196  mov     rcx, [rbp+hMem]; hMem
0x18005519a  test    rcx, rcx
0x18005519d  jz      short loc_1800551A5
0x18005519f  call    cs:__imp_LocalFree
0x1800551a5  lea     rcx, [rbp+var_40]
0x1800551a9  call    ??1?$CComPtrBase@UISODACompletionCallback@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(void)
0x1800551ae  mov     eax, edi
0x1800551b0  jmp     loc_180055529
0x1800551b5  mov     rcx, [rbp+hMem]
0x1800551b9  mov     edi, 300h
0x1800551be  test    [rcx+4Eh], di
0x1800551c2  jnz     loc_18005547C
0x1800551c8  cmp     [rcx+50h], r12d
0x1800551cc  jz      loc_18005547C
0x1800551d2  lea     rdi, stru_18015EA68
0x1800551d9  mov     qword ptr [rbp+var_28], r12
0x1800551dd  mov     rcx, rdi; lpInitOnce
0x1800551e0  mov     [rbp+fPending], r12d
0x1800551e4  lea     r9, [rbp+Context]; lpContext
0x1800551e8  mov     [rbp+Context], r12
0x1800551ec  lea     r8, [rbp+fPending]; fPending
0x1800551f0  xor     edx, edx; dwFlags
0x1800551f2  call    cs:__imp_InitOnceBeginInitialize
0x1800551f8  mov     rbx, [rbp+Context]
0x1800551fc  test    rbx, rbx
0x1800551ff  jnz     short loc_18005521A
0x180055201  lea     rcx, [rbp+var_38]
0x180055205  mov     [rbp+var_38], rdi
0x180055209  call    ?_Construct@_Initializer@?$_LazyImpl@VStorePropertyCache@@V?$lazy_construct@VStorePropertyCache@@@tlx@@V?$static_lazy@VStorePropertyCache@@$0A@V?$lazy_construct@VStorePropertyCache@@@tlx@@@3@@tlx@@QEAAPEAXXZ; tlx::_LazyImpl<StorePropertyCache,tlx::lazy_construct<StorePropertyCache>,tlx::static_lazy<StorePropertyCache,0,tlx::lazy_construct<StorePropertyCache>>>::_Initializer::_Construct(void)
0x18005520e  lea     rcx, [rbp+var_38]
0x180055212  mov     rbx, rax
0x180055215  call    ??1_Initializer@?$_LazyImpl@VComposingStatusChangedEventSink@@V?$lazy_construct@VComposingStatusChangedEventSink@@@tlx@@V?$static_lazy@VComposingStatusChangedEventSink@@$0A@V?$lazy_construct@VComposingStatusChangedEventSink@@@tlx@@@3@@tlx@@QEAA@XZ; tlx::_LazyImpl<ComposingStatusChangedEventSink,tlx::lazy_construct<ComposingStatusChangedEventSink>,tlx::static_lazy<ComposingStatusChangedEventSink,0,tlx::lazy_construct<ComposingStatusChangedEventSink>>>::_Initializer::~_Initializer(void)
0x18005521a  lea     r8, [rbp+var_28]; struct StorePropertySet **
0x18005521e  mov     edx, esi; unsigned int
0x180055220  mov     rcx, rbx; this
0x180055223  call    ?GetPropertiesForStore@StorePropertyCache@@QEAAJKPEAPEBUStorePropertySet@@@Z; StorePropertyCache::GetPropertiesForStore(ulong,StorePropertySet const * *)
0x180055228  test    eax, eax
0x18005522a  jns     short loc_18005523B
0x18005522c  xor     edx, edx
0x18005522e  mov     r9d, 35Ah
0x180055234  mov     ecx, eax
0x180055236  call    Log_HREvent_16
0x18005523b  mov     rax, qword ptr [rbp+var_28]
0x18005523f  test    rax, rax
0x180055242  jz      short loc_180055248
0x180055244  mov     ebx, [rax]
0x180055246  jmp     short loc_18005524D
0x180055248  mov     ebx, 0FFFFFFFFh
0x18005524d  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_64251f8b2e64e7c9e2bb8171f69baa1e_@@CA@XZ; _lambda_64251f8b2e64e7c9e2bb8171f69baa1e_::_lambda_invoker_cdecl_(void)
0x180055254  call    ?get@?$static_lazy@VUserDataServiceTelemetry@@@details@wil@@QEAAPEAVUserDataServiceTelemetry@@P6AXXZ@Z; wil::details::static_lazy<UserDataServiceTelemetry>::get(void (*)(void))
0x180055259  mov     rax, [rax+8]
0x18005525d  test    rax, rax
0x180055260  jz      loc_18005544E
0x180055266  mov     eax, [rax]
0x180055268  test    eax, eax
0x18005526a  jz      loc_18005544E
0x180055270  lea     r9, [rbp+Context]; lpContext
0x180055274  mov     [rbp+Context], r12
0x180055278  lea     r8, [rbp+var_28]; fPending
0x18005527c  mov     [rbp+var_28], r12d
0x180055280  xor     edx, edx; dwFlags
0x180055282  lea     rcx, ?wrapper@?1??Instance@UserDataServiceTelemetry@@KAPEAV2@XZ@4V?$static_lazy@VUserDataServiceTelemetry@@@details@wil@@A; lpInitOnce
0x180055289  call    cs:__imp_InitOnceBeginInitialize
0x18005528f  test    eax, eax
0x180055291  jz      loc_180055440
0x180055297  cmp     [rbp+var_28], r12d
0x18005529b  jz      loc_180055440
0x1800552a1  lea     rax, ??_7UserDataServiceTelemetry@@6B@; const UserDataServiceTelemetry::`vftable'
0x1800552a8  mov     cs:qword_18015D290, r12
0x1800552af  lea     r14, qword_18015D288
0x1800552b6  mov     cs:qword_18015D288, rax
0x1800552bd  xor     r8d, r8d; Flags
0x1800552c0  mov     [rbp+Context], r14
0x1800552c4  xor     edx, edx; dwSpinCount
0x1800552c6  mov     cs:byte_18015D298, r12b
0x1800552cd  lea     rcx, stru_18015D2A0; lpCriticalSection
0x1800552d4  mov     cs:dword_18015D29C, r12d
0x1800552db  call    cs:__imp_InitializeCriticalSectionEx
0x1800552e1  lea     rax, qword_18015D2C8
0x1800552e8  mov     cs:qword_18015D2E0, r12
0x1800552ef  mov     cs:qword_18015D2C8, rax
0x1800552f6  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_64251f8b2e64e7c9e2bb8171f69baa1e_@@CA@XZ; void (__cdecl *)()
0x1800552fd  mov     cs:qword_18015D2D0, rax
0x180055304  xorps   xmm0, xmm0
0x180055307  mov     cs:qword_18015D2D8, rax
0x18005530e  lea     rax, qword_18015D2E8
0x180055315  mov     cs:qword_18015D2E8, rax
0x18005531c  mov     cs:qword_18015D2F0, rax
0x180055323  movdqu  cs:xmmword_18015D2F8, xmm0
0x18005532b  mov     cs:word_18015D308, 800h
0x180055334  call    atexit
0x180055339  lea     r9, [rbp+var_38]; lpContext
0x18005533d  mov     [rbp+var_38], r12
0x180055341  lea     r8, [rbp+fPending]; fPending
0x180055345  mov     [rbp+fPending], r12d
0x180055349  xor     edx, edx; dwFlags
0x18005534b  lea     rcx, ?wrapper@?1??Instance@UserDataServiceProvider@@KAPEAV2@XZ@4V?$static_lazy@VUserDataServiceProvider@@@details@wil@@A; lpInitOnce
0x180055352  call    cs:__imp_InitOnceBeginInitialize
0x180055358  test    eax, eax
0x18005535a  jz      loc_1800553FB
0x180055360  cmp     [rbp+fPending], r12d
0x180055364  jz      loc_1800553FB
0x18005536a  lea     rdi, qword_18015D200
0x180055371  mov     cs:qword_18015D208, r12
0x180055378  lea     rax, ??_7UserDataServiceProvider@@6B@; const UserDataServiceProvider::`vftable'
0x18005537f  mov     [rbp+var_38], rdi
0x180055383  mov     cs:qword_18015D200, rax
0x18005538a  mov     cs:byte_18015D210, r12b
0x180055391  mov     cs:dword_18015D214, r12d
0x180055398  lea     rax, ?__hInner@?1???0StaticHandle@UserDataServiceProvider@@QEAA@XZ@4U_tlgProvider_t@@A; _tlgProvider_t `UserDataServiceProvider::StaticHandle::StaticHandle(void)'::`2'::__hInner
0x18005539f  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_54f6ef7866792d4b3470b3f7b9ab6fcd_@@CA@XZ; void (__cdecl *)()
0x1800553a6  mov     cs:CallbackContext, rax
0x1800553ad  call    atexit
0x1800553b2  mov     rcx, cs:CallbackContext; CallbackContext
0x1800553b9  mov     cs:qword_18015D208, rcx
0x1800553c0  mov     cs:byte_18015D210, 1
0x1800553c7  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x1800553cc  mov     rax, cs:qword_18015D200
0x1800553d3  mov     rcx, rdi
0x1800553d6  mov     cs:dword_18015D214, 1
0x1800553e0  mov     rax, [rax+8]
0x1800553e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800553e9  mov     r8, rdi; lpContext
0x1800553ec  lea     rcx, ?wrapper@?1??Instance@UserDataServiceProvider@@KAPEAV2@XZ@4V?$static_lazy@VUserDataServiceProvider@@@details@wil@@A; lpInitOnce
0x1800553f3  xor     edx, edx; dwFlags
0x1800553f5  call    cs:__imp_InitOnceComplete
0x1800553fb  mov     rax, [rbp+var_38]
0x1800553ff  mov     rcx, [rax+8]
0x180055403  mov     rax, cs:qword_18015D288
0x18005540a  mov     cs:qword_18015D290, rcx
0x180055411  mov     rcx, r14
0x180055414  mov     cs:byte_18015D298, r12b
0x18005541b  mov     cs:dword_18015D29C, 1
0x180055425  mov     rax, [rax+8]
0x180055429  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005542e  mov     r8, r14; lpContext
0x180055431  lea     rcx, ?wrapper@?1??Instance@UserDataServiceTelemetry@@KAPEAV2@XZ@4V?$static_lazy@VUserDataServiceTelemetry@@@details@wil@@A; lpInitOnce
0x180055438  xor     edx, edx; dwFlags
0x18005543a  call    cs:__imp_InitOnceComplete
0x180055440  mov     rcx, [rbp+Context]; this
0x180055444  mov     r8d, ebx; unsigned int
0x180055447  mov     edx, esi; unsigned int
0x180055449  call    ?SkippedSuppressedStore_@UserDataServiceTelemetry@@QEAAXKK@Z; UserDataServiceTelemetry::SkippedSuppressedStore_(ulong,ulong)
0x18005544e  mov     rcx, [rbp+hMem]; hMem
0x180055452  test    rcx, rcx
0x180055455  jz      short loc_18005545D
0x180055457  call    cs:__imp_LocalFree
0x18005545d  mov     rcx, [rbp+var_40]
0x180055461  test    rcx, rcx
0x180055464  jz      short loc_180055472
0x180055466  mov     rax, [rcx]
0x180055469  mov     rax, [rax+10h]
0x18005546d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055472  mov     eax, 80070490h
0x180055477  jmp     loc_180055529
0x18005547c  mov     eax, 2
0x180055481  test    [rcx+6], di
0x180055485  jnz     short loc_18005548A
0x180055487  mov     eax, [rcx+8]
0x18005548a  mov     [r14], eax
0x18005548d  test    [rcx+1Eh], di
0x180055491  jz      short loc_1800554AB
0x180055493  mov     rax, [rbx]
0x180055496  mov     rcx, rbx
0x180055499  mov     rax, [rax+90h]
0x1800554a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800554a5  mov     rcx, [rbp+hMem]
0x1800554a9  jmp     short loc_1800554AE
0x1800554ab  mov     eax, [rcx+20h]
0x1800554ae  mov     [r15], eax
0x1800554b1  test    [rcx+36h], di
0x1800554b5  jnz     short loc_180055507
0x1800554b7  mov     rbx, [rcx+38h]
0x1800554bb  lea     rdx, aVvm; "VVM"
0x1800554c2  mov     rcx, rbx; String1
0x1800554c5  call    cs:__imp__wcsicmp
0x1800554cb  test    eax, eax
0x1800554cd  jz      loc_18005544E
0x1800554d3  lea     rdx, aOmtp11; "OMTP11"
0x1800554da  mov     rcx, rbx; String1
0x1800554dd  call    cs:__imp__wcsicmp
0x1800554e3  test    eax, eax
0x1800554e5  jz      loc_18005544E
0x1800554eb  lea     rdx, aAlu6; "ALU6"
0x1800554f2  mov     rcx, rbx; String1
0x1800554f5  call    cs:__imp__wcsicmp
0x1800554fb  test    eax, eax
0x1800554fd  jz      loc_18005544E
0x180055503  mov     rcx, [rbp+hMem]; hMem
0x180055507  test    rcx, rcx
0x18005550a  jz      short loc_180055512
0x18005550c  call    cs:__imp_LocalFree
0x180055512  mov     rcx, [rbp+var_40]
0x180055516  test    rcx, rcx
0x180055519  jz      short loc_180055527
0x18005551b  mov     rax, [rcx]
0x18005551e  mov     rax, [rax+10h]
0x180055522  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055527  xor     eax, eax
0x180055529  mov     rcx, [rbp+var_10]
0x18005552d  xor     rcx, rsp; StackCookie
0x180055530  call    __security_check_cookie
0x180055535  add     rsp, 80h
0x18005553c  pop     r15
0x18005553e  pop     r14
0x180055540  pop     r12
0x180055542  pop     rdi
0x180055543  pop     rsi
0x180055544  pop     rbx
0x180055545  pop     rbp
0x180055546  retn
```
