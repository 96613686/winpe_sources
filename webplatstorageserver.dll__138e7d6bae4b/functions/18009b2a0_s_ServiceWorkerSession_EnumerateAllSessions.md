# s_ServiceWorkerSession_EnumerateAllSessions

- ea: `0x18009b2a0`
- end: `0x18009b570`
- name: `s_ServiceWorkerSession_EnumerateAllSessions`
- size: `720`
- prototype: ``
- caller_count: `0`
- callee_count: `19`
- tags: `registry_config, service_task`

## callees

- `0x18000f2b0`
- `0x18001d480`
- `0x18001f470`
- `0x1800206fc`
- `0x1800230c0`
- `0x1800273f0`
- `0x18002d290`
- `0x180039348`
- `0x18003ac54`
- `0x18003ad5c`
- `0x180069d8c`
- `0x180078d3c`
- `0x180080fb0`
- `0x180081b40`
- `0x1800924c0`
- `0x180095734`
- `0x180096538`
- `0x180096a24`
- `0x18009b2a0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_terminate` at `0x18009b561`
- `api-ms-win-crt-private-l1-1-0!_o_terminate` at `0x18009b568`
- `api-ms-win-crt-private-l1-1-0!_o_terminate` at `0x18009b561`
- `api-ms-win-crt-private-l1-1-0!_o_terminate` at `0x18009b568`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18009b52b`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18009b52b`

## string_xrefs

- `0x18009b2eb`: `SW_ServiceWorkerSession_EnumerateAllSessions`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall s_ServiceWorkerSession_EnumerateAllSessions(__int64 a1, _QWORD *a2, _DWORD *a3, __int64 *a4)
{
  struct HangDetectionWatchDog *v7; // rdx
  unsigned int v8; // r14d
  __int64 v9; // rbx
  _QWORD **v10; // rcx
  __int64 v11; // rdx
  _QWORD *v12; // rax
  unsigned __int64 v13; // r15
  char *v14; // rbx
  unsigned __int64 v15; // r8
  __int64 v16; // rcx
  __int64 i; // rdx
  __int64 v18; // rcx
  __int64 v19; // rdx
  __int64 v20; // rbx
  __int64 v21; // rcx
  __int64 *v22; // rax
  __int64 v23; // rcx
  const char *v24; // r9
  volatile signed __int64 *v25; // rcx
  wil *v27; // rcx
  _QWORD **v28; // [rsp+20h] [rbp-1F8h] BYREF
  _QWORD v29[2]; // [rsp+30h] [rbp-1E8h] BYREF
  __int128 v30; // [rsp+40h] [rbp-1D8h] BYREF
  __int64 v31; // [rsp+50h] [rbp-1C8h]
  volatile signed __int64 *v32; // [rsp+58h] [rbp-1C0h] BYREF
  _QWORD *v33; // [rsp+60h] [rbp-1B8h] BYREF
  _OWORD v34[2]; // [rsp+68h] [rbp-1B0h] BYREF
  __int64 v35; // [rsp+88h] [rbp-190h]
  _QWORD v36[43]; // [rsp+90h] [rbp-188h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+218h] [rbp+0h]

  SetThreadName((WCHAR *)L"RPC SWSess_EnumAllSess");
  HangDetectionWatchDog::Activity::Activity((HangDetectionWatchDog::Activity *)&v32, v7);
  v8 = 0;
  *a3 = 0;
  *a4 = 0;
  wil::ActivityBase<StorageServerProvider,0,4,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<StorageServerProvider,0,4,4,0,_TlgReflectorTag_Param0IsProviderType>(
    v36,
    "SW_ServiceWorkerSession_EnumerateAllSessions");
  try
  {
    v36[0] = &ServiceWorkerTraceLogging::SW_ServiceWorkerSession_EnumerateAllSessions::`vftable';
    ServiceWorkerTraceLogging::SW_ServiceWorkerSession_EnumerateAllSessions::StartActivity(
      (ServiceWorkerTraceLogging::SW_ServiceWorkerSession_EnumerateAllSessions *)v36,
      a2);
    v9 = a2[3];
    wil::EnterCriticalSection(v29, v9 + 256);
    v10 = *(_QWORD ***)(v9 + 304);
    v12 = *v10;
    v30 = 0;
    v31 = 0;
    v33 = v12;
    v28 = v10;
    v11 = 0;
    while ( v12 != v10 )
    {
      ++v11;
      v12 = (_QWORD *)*v12;
    }
    std::vector<std::shared_ptr<WebStorageActiveReference>>::_Construct_n<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::shared_ptr<WebStorageActiveReference>>>>,std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::shared_ptr<WebStorageActiveReference>>>>>(
      &v30,
      v11,
      &v33,
      &v28);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>(v29);
    if ( (__int64)(*((_QWORD *)&v30 + 1) - v30) >> 4 )
    {
      memset(v34, 0, sizeof(v34));
      v35 = 0;
      std::_Container_base12::_Alloc_proxy<std::allocator<std::_Container_proxy>>(v34);
      v13 = 28 * ((__int64)(*((_QWORD *)&v30 + 1) - v30) >> 4);
      v14 = (char *)RpcHelper::AllocationTracker::Allocate((RpcHelper::AllocationTracker *)v34, v13);
      memset_0(v14, 0, v13);
      v15 = 0;
      v16 = *((_QWORD *)&v30 + 1);
      for ( i = v30; v15 < (__int64)(*((_QWORD *)&v30 + 1) - v30) >> 4; i = v30 )
      {
        v18 = *(_QWORD *)(i + 16 * v15);
        v19 = 28 * v15;
        v14[v19] = *(_BYTE *)(v18 + 120);
        *(_DWORD *)&v14[v19 + 8] = *(_DWORD *)(v18 + 116);
        *(_DWORD *)&v14[v19 + 4] = *(_DWORD *)(v18 + 112);
        *(_OWORD *)&v14[v19 + 12] = *(_OWORD *)(v18 + 96);
        ++v15;
        v16 = *((_QWORD *)&v30 + 1);
      }
      *a4 = (__int64)v14;
      *a3 = wil::safe_cast_failfast<unsigned int,unsigned __int64,0>((v16 - i) >> 4);
      std::deque<void *>::_Tidy(v34);
      RpcHelper::AllocationTracker::~AllocationTracker((RpcHelper::AllocationTracker *)v34);
    }
    v20 = *a4;
    gsl::details::extent_type<-1>::extent_type<-1>(v29, (unsigned int)*a3);
    if ( v29[0] != -1 && (v20 || !v29[0]) )
    {
      v22 = (__int64 *)gsl::details::extent_type<-1>::extent_type<-1>(v29, v29[0]);
      v23 = *v22;
      if ( *v22 != -1 && (v20 || !v23) )
      {
        v29[0] = *v22;
        v29[1] = v20;
        ServiceWorkerTraceLogging::SW_ServiceWorkerSession_EnumerateAllSessions::Stop(v36, v29);
        std::vector<std::shared_ptr<WebStorageActiveReference>>::_Tidy(&v30);
        ServiceWorkerTraceLogging::SW_ServiceWorkerSession_EnumerateAllSessions::~SW_ServiceWorkerSession_EnumerateAllSessions((ServiceWorkerTraceLogging::SW_ServiceWorkerSession_EnumerateAllSessions *)v36);
        goto LABEL_23;
      }
      _o_terminate(v23);
    }
    _o_terminate(v21);
    JUMPOUT(0x18009B56ELL);
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0xA9,
      (unsigned int)"onecoreuap\\inetcore\\webplatstorageserver\\serviceworkerstorage\\serviceworkerrpcapi.cxx",
      v24);
    LODWORD(v28) = wil::ResultFromCaughtException(v27);
    v8 = (unsigned int)v28;
  }
LABEL_23:
  v25 = v32;
  if ( _InterlockedExchangeAdd64(v32, 0xFFFFFFFFFFFFFFFFuLL) == 1 )
    SetThreadpoolTimer(*((PTP_TIMER *)v25 + 1), 0, 0, 0);
  SetThreadName((WCHAR *)&word_1800D6108);
  return v8;
}

```

## disassembly

```asm
0x18009b2a0  push    rbx
0x18009b2a2  push    rsi
0x18009b2a3  push    rdi
0x18009b2a4  push    r14
0x18009b2a6  push    r15
0x18009b2a8  sub     rsp, 1F0h
0x18009b2af  mov     rax, cs:__security_cookie
0x18009b2b6  xor     rax, rsp
0x18009b2b9  mov     [rsp+218h+var_30], rax
0x18009b2c1  mov     rsi, r9
0x18009b2c4  mov     rdi, r8
0x18009b2c7  mov     rbx, rdx
0x18009b2ca  lea     rcx, aRpcSwsessEnuma; "RPC SWSess_EnumAllSess"
0x18009b2d1  call    SetThreadName
0x18009b2d6  nop
0x18009b2d7  lea     rcx, [rsp+218h+var_1C0]; this
0x18009b2dc  call    ??0Activity@HangDetectionWatchDog@@QEAA@PEAV1@@Z; HangDetectionWatchDog::Activity::Activity(HangDetectionWatchDog *)
0x18009b2e1  nop
0x18009b2e2  xor     r14d, r14d
0x18009b2e5  mov     [rdi], r14d
0x18009b2e8  mov     [rsi], r14
0x18009b2eb  lea     rdx, aSwServiceworke_12; "SW_ServiceWorkerSession_EnumerateAllSes"...
0x18009b2f2  lea     rcx, [rsp+218h+var_188]
0x18009b2fa  call    ??0?$ActivityBase@VStorageServerProvider@@$0A@$03$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<StorageServerProvider,0,4,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<StorageServerProvider,0,4,4,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x18009b2ff  lea     rax, ??_7SW_ServiceWorkerSession_EnumerateAllSessions@ServiceWorkerTraceLogging@@6B@; const ServiceWorkerTraceLogging::SW_ServiceWorkerSession_EnumerateAllSessions::`vftable'
0x18009b306  mov     [rsp+218h+var_188], rax
0x18009b30e  mov     rdx, rbx; void *
0x18009b311  lea     rcx, [rsp+218h+var_188]; this
0x18009b319  call    ?StartActivity@SW_ServiceWorkerSession_EnumerateAllSessions@ServiceWorkerTraceLogging@@QEAAXPEAX@Z; ServiceWorkerTraceLogging::SW_ServiceWorkerSession_EnumerateAllSessions::StartActivity(void *)
0x18009b31e  nop
0x18009b31f  mov     rbx, [rbx+18h]
0x18009b323  lea     rdx, [rbx+100h]
0x18009b32a  lea     rcx, [rsp+218h+var_1E8]
0x18009b32f  call    ?EnterCriticalSection@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_CRITICAL_SECTION@@@Z; wil::EnterCriticalSection(_RTL_CRITICAL_SECTION *)
0x18009b334  mov     rcx, [rbx+130h]
0x18009b33b  mov     rax, [rcx]
0x18009b33e  xorps   xmm0, xmm0
0x18009b341  movdqu  [rsp+218h+var_1D8], xmm0
0x18009b347  mov     [rsp+218h+var_1C8], r14
0x18009b34c  mov     [rsp+218h+var_1B8], rax
0x18009b351  mov     [rsp+218h+var_1F8], rcx
0x18009b356  xor     edx, edx
0x18009b358  cmp     rax, rcx
0x18009b35b  jz      short loc_18009B365
0x18009b35d  inc     rdx
0x18009b360  mov     rax, [rax]
0x18009b363  jmp     short loc_18009B358
0x18009b365  lea     r9, [rsp+218h+var_1F8]
0x18009b36a  lea     r8, [rsp+218h+var_1B8]
0x18009b36f  lea     rcx, [rsp+218h+var_1D8]
0x18009b374  call    ??$_Construct_n@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@V?$shared_ptr@VWebStorageActiveReference@@@std@@@std@@@std@@@std@@V12@@?$vector@V?$shared_ptr@VWebStorageActiveReference@@@std@@V?$allocator@V?$shared_ptr@VWebStorageActiveReference@@@std@@@2@@std@@AEAAX_K$$QEAV?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@V?$shared_ptr@VWebStorageActiveReference@@@std@@@std@@@std@@@1@1@Z; std::vector<std::shared_ptr<WebStorageActiveReference>>::_Construct_n<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::shared_ptr<WebStorageActiveReference>>>>,std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::shared_ptr<WebStorageActiveReference>>>>>(unsigned __int64,std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::shared_ptr<WebStorageActiveReference>>>> &&,std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::shared_ptr<WebStorageActiveReference>>>> &&)
0x18009b379  lea     rcx, [rsp+218h+var_1E8]
0x18009b37e  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>(void)
0x18009b383  nop
0x18009b384  mov     rax, qword ptr [rsp+218h+var_1D8+8]
0x18009b389  sub     rax, qword ptr [rsp+218h+var_1D8]
0x18009b38e  sar     rax, 4
0x18009b392  test    rax, rax
0x18009b395  jz      loc_18009B47D
0x18009b39b  xorps   xmm0, xmm0
0x18009b39e  movdqu  [rsp+218h+var_1B0], xmm0
0x18009b3a4  xorps   xmm1, xmm1
0x18009b3a7  movdqu  [rsp+218h+var_1A0], xmm1
0x18009b3ad  mov     [rsp+218h+var_190], 0
0x18009b3b9  lea     rcx, [rsp+218h+var_1B0]
0x18009b3be  call    ??$_Alloc_proxy@V?$allocator@U_Container_proxy@std@@@std@@@_Container_base12@std@@QEAAX$$QEAV?$allocator@U_Container_proxy@std@@@1@@Z; std::_Container_base12::_Alloc_proxy<std::allocator<std::_Container_proxy>>(std::allocator<std::_Container_proxy> &&)
0x18009b3c3  nop
0x18009b3c4  mov     rax, qword ptr [rsp+218h+var_1D8+8]
0x18009b3c9  sub     rax, qword ptr [rsp+218h+var_1D8]
0x18009b3ce  sar     rax, 4
0x18009b3d2  imul    r15, rax, 1Ch
0x18009b3d6  mov     rdx, r15; unsigned __int64
0x18009b3d9  lea     rcx, [rsp+218h+var_1B0]; this
0x18009b3de  call    ?Allocate@AllocationTracker@RpcHelper@@QEAAPEAX_K@Z; RpcHelper::AllocationTracker::Allocate(unsigned __int64)
0x18009b3e3  mov     rbx, rax
0x18009b3e6  mov     r8, r15; Size
0x18009b3e9  xor     edx, edx; Val
0x18009b3eb  mov     rcx, rax; void *
0x18009b3ee  call    memset_0
0x18009b3f3  xor     r8d, r8d
0x18009b3f6  mov     rcx, qword ptr [rsp+218h+var_1D8+8]
0x18009b3fb  mov     rax, rcx
0x18009b3fe  mov     rdx, qword ptr [rsp+218h+var_1D8]
0x18009b403  sub     rax, rdx
0x18009b406  sar     rax, 4
0x18009b40a  test    rax, rax
0x18009b40d  jz      short loc_18009B457
0x18009b40f  mov     rax, r8
0x18009b412  add     rax, rax
0x18009b415  mov     rcx, [rdx+rax*8]
0x18009b419  imul    rdx, r8, 1Ch
0x18009b41d  mov     al, [rcx+78h]
0x18009b420  mov     [rdx+rbx], al
0x18009b423  mov     eax, [rcx+74h]
0x18009b426  mov     [rdx+rbx+8], eax
0x18009b42a  mov     eax, [rcx+70h]
0x18009b42d  mov     [rdx+rbx+4], eax
0x18009b431  movups  xmm0, xmmword ptr [rcx+60h]
0x18009b435  movdqu  xmmword ptr [rdx+rbx+0Ch], xmm0
0x18009b43b  inc     r8
0x18009b43e  mov     rcx, qword ptr [rsp+218h+var_1D8+8]
0x18009b443  mov     rax, rcx
0x18009b446  mov     rdx, qword ptr [rsp+218h+var_1D8]
0x18009b44b  sub     rax, rdx
0x18009b44e  sar     rax, 4
0x18009b452  cmp     r8, rax
0x18009b455  jb      short loc_18009B40F
0x18009b457  mov     [rsi], rbx
0x18009b45a  sub     rcx, rdx
0x18009b45d  sar     rcx, 4
0x18009b461  call    ??$safe_cast_failfast@I_K$0A@@wil@@YAI_K@Z; wil::safe_cast_failfast<uint,unsigned __int64,0>(unsigned __int64)
0x18009b466  mov     [rdi], eax
0x18009b468  lea     rcx, [rsp+218h+var_1B0]
0x18009b46d  call    ?_Tidy@?$deque@PEAXV?$allocator@PEAX@std@@@std@@AEAAXXZ; std::deque<void *>::_Tidy(void)
0x18009b472  nop
0x18009b473  lea     rcx, [rsp+218h+var_1B0]; this
0x18009b478  call    ??1AllocationTracker@RpcHelper@@QEAA@XZ; RpcHelper::AllocationTracker::~AllocationTracker(void)
0x18009b47d  mov     rbx, [rsi]
0x18009b480  mov     edx, [rdi]
0x18009b482  lea     rcx, [rsp+218h+var_1E8]
0x18009b487  call    ??0?$extent_type@$0?0@details@gsl@@QEAA@_K@Z; gsl::details::extent_type<-1>::extent_type<-1>(unsigned __int64)
0x18009b48c  mov     rdx, [rsp+218h+var_1E8]
0x18009b491  cmp     rdx, 0FFFFFFFFFFFFFFFFh
0x18009b495  jz      loc_18009B568
0x18009b49b  test    rbx, rbx
0x18009b49e  jnz     short loc_18009B4A9
0x18009b4a0  test    rdx, rdx
0x18009b4a3  jnz     loc_18009B568
0x18009b4a9  lea     rcx, [rsp+218h+var_1E8]
0x18009b4ae  call    ??0?$extent_type@$0?0@details@gsl@@QEAA@_K@Z; gsl::details::extent_type<-1>::extent_type<-1>(unsigned __int64)
0x18009b4b3  mov     rcx, [rax]
0x18009b4b6  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18009b4ba  jz      loc_18009B561
0x18009b4c0  test    rbx, rbx
0x18009b4c3  jnz     short loc_18009B4CE
0x18009b4c5  test    rcx, rcx
0x18009b4c8  jnz     loc_18009B561
0x18009b4ce  mov     [rsp+218h+var_1E8], rcx
0x18009b4d3  mov     [rsp+218h+var_1E0], rbx
0x18009b4d8  lea     rdx, [rsp+218h+var_1E8]
0x18009b4dd  lea     rcx, [rsp+218h+var_188]
0x18009b4e5  call    ?Stop@SW_ServiceWorkerSession_EnumerateAllSessions@ServiceWorkerTraceLogging@@QEAAXV?$span@$$CBURPCServiceWorkerManager@@$0?0@gsl@@@Z; ServiceWorkerTraceLogging::SW_ServiceWorkerSession_EnumerateAllSessions::Stop(gsl::span<RPCServiceWorkerManager const,-1>)
0x18009b4ea  nop
0x18009b4eb  lea     rcx, [rsp+218h+var_1D8]
0x18009b4f0  call    ?_Tidy@?$vector@V?$shared_ptr@VWebStorageActiveReference@@@std@@V?$allocator@V?$shared_ptr@VWebStorageActiveReference@@@std@@@2@@std@@AEAAXXZ; std::vector<std::shared_ptr<WebStorageActiveReference>>::_Tidy(void)
0x18009b4f5  nop
0x18009b4f6  lea     rcx, [rsp+218h+var_188]; this
0x18009b4fe  call    ??1SW_ServiceWorkerSession_EnumerateAllSessions@ServiceWorkerTraceLogging@@QEAA@XZ; ServiceWorkerTraceLogging::SW_ServiceWorkerSession_EnumerateAllSessions::~SW_ServiceWorkerSession_EnumerateAllSessions(void)
0x18009b503  nop
0x18009b504  jmp     short loc_18009B50B
0x18009b506  mov     r14d, dword ptr [rsp+218h+var_1F8]
0x18009b50b  mov     rcx, [rsp+218h+var_1C0]
0x18009b510  or      rax, 0FFFFFFFFFFFFFFFFh
0x18009b514  lock xadd [rcx], rax
0x18009b519  cmp     rax, 1
0x18009b51d  jnz     short loc_18009B532
0x18009b51f  xor     r9d, r9d; msWindowLength
0x18009b522  xor     r8d, r8d; msPeriod
0x18009b525  xor     edx, edx; pftDueTime
0x18009b527  mov     rcx, [rcx+8]; pti
0x18009b52b  call    cs:__imp_SetThreadpoolTimer
0x18009b531  nop
0x18009b532  lea     rcx, word_1800D6108; lpWideCharStr
0x18009b539  call    SetThreadName
0x18009b53e  nop
0x18009b53f  mov     eax, r14d
0x18009b542  mov     rcx, [rsp+218h+var_30]
0x18009b54a  xor     rcx, rsp; StackCookie
0x18009b54d  call    __security_check_cookie
0x18009b552  add     rsp, 1F0h
0x18009b559  pop     r15
0x18009b55b  pop     r14
0x18009b55d  pop     rdi
0x18009b55e  pop     rsi
0x18009b55f  pop     rbx
0x18009b560  retn
0x18009b561  call    cs:__imp__o_terminate
0x18009b567  nop
0x18009b568  call    cs:__imp__o_terminate
```
