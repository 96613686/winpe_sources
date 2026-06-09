# ComputeService::Communication::BridgeRelay::BridgeRelay(ComputeService::Communication::BridgeRelayProperties const &,wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>>,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,ComputeService::Management::CancellationToken)

- ea: `0x1400f1f44`
- end: `0x1400f234a`
- name: `??0BridgeRelay@Communication@ComputeService@@QEAA@AEBUBridgeRelayProperties@12@V?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@VCancellationToken@Management@2@@Z`
- size: `1030`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1400edb60`

## callees

- `0x140005360`
- `0x140008760`
- `0x1400341ac`
- `0x14003aa4c`
- `0x1400ee9a8`
- `0x1400ef834`
- `0x1400f1f44`
- `0x1400f24fc`
- `0x1400f26b8`
- `0x1400fe010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400f221e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400f221e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1400f21d7`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1400f21d7`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x1400f201c`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x1400f201c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400f21dd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400f21dd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400f22c9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400f22c9`

## string_xrefs

- `0x1400f2338`: `onecore\vm\compute\common\transport\transportrelay.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=22
__int64 __fastcall ComputeService::Communication::BridgeRelay::BridgeRelay(
        __int64 a1,
        __int64 a2,
        HANDLE *a3,
        _OWORD *a4,
        _QWORD *a5)
{
  __int64 v8; // rsi
  __int64 v9; // rcx
  __int64 v10; // rax
  __int64 v11; // rcx
  __int64 v12; // rcx
  __int64 v13; // rbx
  __int64 v14; // rcx
  __int128 v15; // xmm1
  bool v16; // zf
  __int128 v17; // xmm0
  int v18; // ecx
  int v19; // eax
  volatile signed __int32 *v20; // xmm7_8
  volatile signed __int32 *v21; // xmm6_8
  volatile signed __int32 *v22; // rcx
  unsigned int v24; // [rsp+28h] [rbp-C1h]
  __int128 v25; // [rsp+38h] [rbp-B1h] BYREF
  __int128 v26; // [rsp+48h] [rbp-A1h] BYREF
  HANDLE v27; // [rsp+58h] [rbp-91h] BYREF
  _QWORD v28[3]; // [rsp+60h] [rbp-89h] BYREF
  __int128 v29; // [rsp+78h] [rbp-71h] BYREF
  _QWORD *v30; // [rsp+88h] [rbp-61h]
  _OWORD v31[2]; // [rsp+90h] [rbp-59h] BYREF
  __int64 v32; // [rsp+B0h] [rbp-39h]
  HANDLE *v33; // [rsp+B8h] [rbp-31h]
  _QWORD *v34; // [rsp+C0h] [rbp-29h]
  _OWORD *v35; // [rsp+C8h] [rbp-21h]
  wil::details::in1diag3 *retaddr; // [rsp+140h] [rbp+57h]

  v28[1] = a2;
  v32 = a1;
  v33 = a3;
  v35 = a4;
  v30 = a5;
  v34 = a5;
  *(_QWORD *)a1 = &ComputeService::Communication::BridgeRelay::`vftable';
  v8 = a1 + 8;
  v27 = (HANDLE)(a1 + 8);
  v9 = *a5;
  v10 = a5[1];
  *a5 = 0;
  a5[1] = 0;
  *(_QWORD *)&v25 = &v26;
  *(_QWORD *)v8 = &TransportRelay::`vftable';
  *(_QWORD *)(v8 + 8) = 0;
  *(_QWORD *)(v8 + 16) = 0;
  *(_QWORD *)(v8 + 24) = 0;
  *(_QWORD *)(v8 + 32) = 0;
  *(_QWORD *)(v8 + 40) = 0;
  *(_QWORD *)(v8 + 48) = 0;
  *(_QWORD *)(v8 + 56) = 0;
  *(_QWORD *)(v8 + 64) = 0;
  *(_QWORD *)(v8 + 72) = v9;
  *(_QWORD *)(v8 + 80) = v10;
  v26 = 0;
  *(_QWORD *)(v8 + 88) = 0;
  *(_DWORD *)(v8 + 96) = 0;
  *(_QWORD *)(v8 + 104) = 0;
  *(_QWORD *)(v8 + 112) = 0;
  *(_DWORD *)(v8 + 128) = 0;
  InitializeSRWLock((PSRWLOCK)(v8 + 120));
  *(_DWORD *)(v8 + 136) = 0;
  *(_QWORD *)(v8 + 144) = 0;
  *(_QWORD *)(v8 + 152) = 0;
  *(_QWORD *)(v8 + 160) = 0;
  *(_QWORD *)(v8 + 168) = 0;
  *(_QWORD *)(v8 + 176) = 0;
  *(_QWORD *)(v8 + 184) = 0;
  *(_QWORD *)(v8 + 192) = 0;
  *(_OWORD *)(v8 + 200) = 0;
  *(_QWORD *)(v8 + 216) = 0;
  *(_QWORD *)(v8 + 224) = 7;
  *(_WORD *)(v8 + 200) = 0;
  *(_BYTE *)(v8 + 232) = 0;
  _create___event_t_V__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil__Uerr_exception_policy_2__wil__QEAAXW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
    (void **)(v8 + 184),
    1);
  _create___event_t_V__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil__Uerr_exception_policy_2__wil__QEAAXW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
    (void **)(v8 + 192),
    1);
  v11 = *((_QWORD *)&v26 + 1);
  if ( *((_QWORD *)&v26 + 1)
    && _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v26 + 1) + 12LL), 0xFFFFFFFF) == 1 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 8LL))(v11);
  }
  *(_QWORD *)(a1 + 248) = 0;
  *(_QWORD *)(a1 + 256) = 0;
  *(_QWORD *)(a1 + 264) = 0;
  *(_DWORD *)(a1 + 272) = 0;
  _create___event_t_V__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil__Uerr_exception_policy_2__wil__QEAAXW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
    (void **)(a1 + 248),
    1);
  _create___event_t_V__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil__Uerr_exception_policy_2__wil__QEAAXW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
    (void **)(a1 + 256),
    1);
  _create___event_t_V__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil__Uerr_exception_policy_2__wil__QEAAXW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
    (void **)(a1 + 264),
    1);
  v29 = 0;
  v27 = *a3;
  *a3 = (HANDLE)-1LL;
  ComputeService::Communication::BridgeRelay::CreatePipeTransport(v12, &v29, &v27);
  v26 = 0;
  v13 = v28[1];
  ComputeService::Communication::BridgeRelay::CreateSocketTransport(v14, &v26, v28[1]);
  v15 = a4[1];
  LOBYTE(v24) = *(_BYTE *)(v13 + 33);
  v31[0] = *a4;
  v31[1] = v15;
  v16 = *(_BYTE *)(v13 + 32) == 0;
  *((_QWORD *)a4 + 2) = 0;
  *((_QWORD *)a4 + 3) = 7;
  *(_WORD *)a4 = 0;
  if ( v16 )
  {
    *(_OWORD *)&v28[1] = v29;
    v17 = v26;
  }
  else
  {
    *(_OWORD *)&v28[1] = v26;
    v17 = v29;
  }
  v29 = 0;
  v25 = v17;
  v26 = 0;
  TransportRelay::Configure(v8, &v25, &v28[1], v31);
  AcquireSRWLockExclusive((PSRWLOCK)(v8 + 120));
  *(_DWORD *)(v8 + 128) = GetCurrentThreadId();
  *(_QWORD *)&v25 = v8 + 120;
  v18 = *(_DWORD *)(v8 + 136);
  if ( v18 )
  {
    if ( v18 != 1 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0xAE,
        (unsigned int)"onecore\\vm\\compute\\common\\transport\\transportrelay.cpp",
        (const char *)0x139F,
        v24);
    v19 = 3;
  }
  else
  {
    v19 = 2;
  }
  *(_DWORD *)(v8 + 136) = v19;
  *(_QWORD *)(v8 + 104) = a1;
  *(_DWORD *)(v8 + 128) = 0;
  ReleaseSRWLockExclusive((PSRWLOCK)(v8 + 120));
  TransportRelay::Start((RTL_SRWLOCK *)(a1 + 8), *(void **)(a1 + 256));
  v20 = (volatile signed __int32 *)_mm_srli_si128((__m128i)0LL, 8).m128i_u64[0];
  if ( v20 )
  {
    if ( _InterlockedExchangeAdd(v20 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v20)(v20);
      if ( _InterlockedExchangeAdd(v20 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v20 + 8LL))(v20);
    }
  }
  v21 = (volatile signed __int32 *)_mm_srli_si128((__m128i)0LL, 8).m128i_u64[0];
  if ( v21 )
  {
    if ( _InterlockedExchangeAdd(v21 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v21)(v21);
      if ( _InterlockedExchangeAdd(v21 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v21 + 8LL))(v21);
    }
  }
  if ( (char *)*a3 - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    CloseHandle(*a3);
  std::wstring::~wstring(a4);
  v22 = (volatile signed __int32 *)v30[1];
  if ( v22 && _InterlockedExchangeAdd(v22 + 3, 0xFFFFFFFF) == 1 )
    (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v22 + 8LL))(v22);
  return a1;
}

```

## disassembly

```asm
0x1400f1f44  mov     rax, rsp
0x1400f1f47  push    rbp
0x1400f1f48  push    rbx
0x1400f1f49  push    rsi
0x1400f1f4a  push    rdi
0x1400f1f4b  push    r12
0x1400f1f4d  push    r13
0x1400f1f4f  push    r14
0x1400f1f51  push    r15
0x1400f1f53  lea     rbp, [rax-57h]
0x1400f1f57  sub     rsp, 0F8h
0x1400f1f5e  movaps  xmmword ptr [rax-58h], xmm6
0x1400f1f62  movaps  xmmword ptr [rax-68h], xmm7
0x1400f1f66  mov     rax, cs:__security_cookie
0x1400f1f6d  xor     rax, rsp
0x1400f1f70  mov     [rbp+4Fh+var_68], rax
0x1400f1f74  mov     r14, r9
0x1400f1f77  mov     r12, r8
0x1400f1f7a  mov     qword ptr [rsp+130h+var_D8+8], rdx
0x1400f1f7f  mov     r15, rcx
0x1400f1f82  mov     [rbp+4Fh+var_88], rcx
0x1400f1f86  mov     [rbp+4Fh+var_80], r8
0x1400f1f8a  mov     [rbp+4Fh+var_70], r9
0x1400f1f8e  mov     rdx, [rbp+4Fh+arg_20]
0x1400f1f92  mov     [rbp+4Fh+var_B0], rdx
0x1400f1f96  mov     [rbp+4Fh+var_78], rdx
0x1400f1f9a  lea     rax, ??_7BridgeRelay@Communication@ComputeService@@6B@; const ComputeService::Communication::BridgeRelay::`vftable'
0x1400f1fa1  mov     [rcx], rax
0x1400f1fa4  lea     rsi, [rcx+8]
0x1400f1fa8  mov     [rsp+130h+var_E0], rsi
0x1400f1fad  mov     rcx, [rdx]
0x1400f1fb0  mov     rax, [rdx+8]
0x1400f1fb4  xor     edi, edi
0x1400f1fb6  mov     [rdx], rdi
0x1400f1fb9  mov     [rdx+8], rdi
0x1400f1fbd  lea     rdx, [rsp+130h+var_F8+8]
0x1400f1fc2  mov     qword ptr [rsp+130h+var_108+8], rdx
0x1400f1fc7  lea     rdx, ??_7TransportRelay@@6B@; const TransportRelay::`vftable'
0x1400f1fce  mov     [rsi], rdx
0x1400f1fd1  mov     [rsi+8], rdi
0x1400f1fd5  mov     [rsi+10h], rdi
0x1400f1fd9  mov     [rsi+18h], rdi
0x1400f1fdd  mov     [rsi+20h], rdi
0x1400f1fe1  mov     [rsi+28h], rdi
0x1400f1fe5  mov     [rsi+30h], rdi
0x1400f1fe9  mov     [rsi+38h], rdi
0x1400f1fed  mov     [rsi+40h], rdi
0x1400f1ff1  mov     [rsi+48h], rcx
0x1400f1ff5  mov     [rsi+50h], rax
0x1400f1ff9  xorps   xmm0, xmm0
0x1400f1ffc  movdqu  [rsp+130h+var_F8+8], xmm0
0x1400f2002  mov     [rsi+58h], rdi
0x1400f2006  mov     [rsi+60h], edi
0x1400f2009  mov     [rsi+68h], rdi
0x1400f200d  mov     [rsi+70h], rdi
0x1400f2011  lea     r13, [rsi+78h]
0x1400f2015  mov     [r13+8], edi
0x1400f2019  mov     rcx, r13; SRWLock
0x1400f201c  call    cs:__imp_InitializeSRWLock
0x1400f2022  mov     [rsi+88h], edi
0x1400f2028  mov     [rsi+90h], rdi
0x1400f202f  mov     [rsi+98h], rdi
0x1400f2036  mov     [rsi+0A0h], rdi
0x1400f203d  mov     [rsi+0A8h], rdi
0x1400f2044  mov     [rsi+0B0h], rdi
0x1400f204b  lea     rcx, [rsi+0B8h]
0x1400f2052  mov     [rcx], rdi
0x1400f2055  lea     rbx, [rsi+0C0h]
0x1400f205c  mov     [rbx], rdi
0x1400f205f  xorps   xmm0, xmm0
0x1400f2062  movups  xmmword ptr [rsi+0C8h], xmm0
0x1400f2069  mov     [rsi+0D8h], rdi
0x1400f2070  mov     qword ptr [rsi+0E0h], 7
0x1400f207b  mov     [rsi+0C8h], di
0x1400f2082  mov     [rsi+0E8h], dil
0x1400f2089  lea     edx, [rdi+1]
0x1400f208c  call    ?create@?$event_t@V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@Uerr_exception_policy@2@@wil@@QEAAXW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x1400f2091  lea     edx, [rdi+1]
0x1400f2094  mov     rcx, rbx
0x1400f2097  call    ?create@?$event_t@V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@Uerr_exception_policy@2@@wil@@QEAAXW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x1400f209c  nop
0x1400f209d  mov     rcx, [rsp+130h+var_E8]
0x1400f20a2  test    rcx, rcx
0x1400f20a5  jz      short loc_1400F20C1
0x1400f20a7  or      eax, 0FFFFFFFFh
0x1400f20aa  lock xadd [rcx+0Ch], eax
0x1400f20af  cmp     eax, 1
0x1400f20b2  jnz     short loc_1400F20C1
0x1400f20b4  mov     rax, [rcx]
0x1400f20b7  mov     rax, [rax+8]
0x1400f20bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400f20c0  nop
0x1400f20c1  lea     rcx, [r15+0F8h]
0x1400f20c8  mov     [rcx], rdi
0x1400f20cb  lea     rdi, [r15+100h]
0x1400f20d2  mov     qword ptr [rdi], 0
0x1400f20d9  lea     rbx, [r15+108h]
0x1400f20e0  mov     qword ptr [rbx], 0
0x1400f20e7  mov     dword ptr [r15+110h], 0
0x1400f20f2  mov     edx, 1
0x1400f20f7  call    ?create@?$event_t@V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@Uerr_exception_policy@2@@wil@@QEAAXW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x1400f20fc  mov     edx, 1
0x1400f2101  mov     rcx, rdi
0x1400f2104  call    ?create@?$event_t@V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@Uerr_exception_policy@2@@wil@@QEAAXW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x1400f2109  mov     edx, 1
0x1400f210e  mov     rcx, rbx
0x1400f2111  call    ?create@?$event_t@V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@Uerr_exception_policy@2@@wil@@QEAAXW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x1400f2116  xorps   xmm0, xmm0
0x1400f2119  movups  [rbp+4Fh+var_C0], xmm0
0x1400f211d  mov     rax, [r12]
0x1400f2121  mov     [rsp+130h+var_E0], rax
0x1400f2126  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1400f212a  mov     [r12], rdi
0x1400f212e  lea     r8, [rsp+130h+var_E0]
0x1400f2133  lea     rdx, [rbp+4Fh+var_C0]
0x1400f2137  call    ?CreatePipeTransport@BridgeRelay@Communication@ComputeService@@QEAA?AV?$shared_ptr@VTransport@@@std@@V?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@Z; ComputeService::Communication::BridgeRelay::CreatePipeTransport(wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>>)
0x1400f213c  nop
0x1400f213d  xorps   xmm0, xmm0
0x1400f2140  movups  [rsp+130h+var_F8+8], xmm0
0x1400f2145  mov     rbx, qword ptr [rsp+130h+var_D8+8]
0x1400f214a  mov     r8, rbx
0x1400f214d  lea     rdx, [rsp+130h+var_F8+8]
0x1400f2152  call    ?CreateSocketTransport@BridgeRelay@Communication@ComputeService@@QEAA?AV?$shared_ptr@VTransport@@@std@@AEBUBridgeRelayProperties@23@@Z; ComputeService::Communication::BridgeRelay::CreateSocketTransport(ComputeService::Communication::BridgeRelayProperties const &)
0x1400f2157  nop
0x1400f2158  mov     cl, [rbx+21h]
0x1400f215b  xor     edx, edx
0x1400f215d  movups  xmm0, xmmword ptr [r14]
0x1400f2161  movups  xmm1, xmmword ptr [r14+10h]
0x1400f2166  xorps   xmm7, xmm7
0x1400f2169  xorps   xmm6, xmm6
0x1400f216c  mov     byte ptr [rsp+130h+var_110], cl; unsigned int
0x1400f2170  lea     r9, [rbp+4Fh+var_A8]
0x1400f2174  lea     r8, [rsp+130h+var_D8+8]
0x1400f2179  movups  [rbp+4Fh+var_A8], xmm0
0x1400f217d  movups  [rbp+4Fh+var_98], xmm1
0x1400f2181  mov     rcx, rsi
0x1400f2184  cmp     [rbx+20h], dl
0x1400f2187  mov     [r14+10h], rdx
0x1400f218b  mov     qword ptr [r14+18h], 7
0x1400f2193  mov     [r14], dx
0x1400f2197  lea     rdx, [rsp+130h+var_108+8]
0x1400f219c  jz      short loc_1400F21AF
0x1400f219e  movaps  xmm0, [rsp+130h+var_F8+8]
0x1400f21a3  movdqa  xmmword ptr [rsp+130h+var_D8+8], xmm0
0x1400f21a9  movaps  xmm0, [rbp+4Fh+var_C0]
0x1400f21ad  jmp     short loc_1400F21BE
0x1400f21af  movaps  xmm0, [rbp+4Fh+var_C0]
0x1400f21b3  movdqa  xmmword ptr [rsp+130h+var_D8+8], xmm0
0x1400f21b9  movaps  xmm0, [rsp+130h+var_F8+8]
0x1400f21be  movdqa  [rbp+4Fh+var_C0], xmm6
0x1400f21c3  movdqa  [rsp+130h+var_108+8], xmm0
0x1400f21c9  movdqa  [rsp+130h+var_F8+8], xmm7
0x1400f21cf  call    ?Configure@TransportRelay@@QEAAXV?$shared_ptr@VTransport@@@std@@0V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@3@_NK@Z; TransportRelay::Configure(std::shared_ptr<Transport>,std::shared_ptr<Transport>,std::wstring,bool,ulong)
0x1400f21d4  mov     rcx, r13; SRWLock
0x1400f21d7  call    cs:__imp_AcquireSRWLockExclusive
0x1400f21dd  call    cs:__imp_GetCurrentThreadId
0x1400f21e3  mov     [r13+8], eax
0x1400f21e7  mov     qword ptr [rsp+130h+var_108+8], r13
0x1400f21ec  mov     ecx, [rsi+88h]
0x1400f21f2  test    ecx, ecx
0x1400f21f4  jz      short loc_1400F2204
0x1400f21f6  cmp     ecx, 1
0x1400f21f9  jnz     loc_1400F232E
0x1400f21ff  lea     eax, [rcx+2]
0x1400f2202  jmp     short loc_1400F2209
0x1400f2204  mov     eax, 2
0x1400f2209  mov     [rsi+88h], eax
0x1400f220f  mov     [rsi+68h], r15
0x1400f2213  mov     dword ptr [r13+8], 0
0x1400f221b  mov     rcx, r13; SRWLock
0x1400f221e  call    cs:__imp_ReleaseSRWLockExclusive
0x1400f2224  lea     rcx, [r15+8]; pv
0x1400f2228  mov     rdx, [r15+100h]; void *
0x1400f222f  call    ?Start@TransportRelay@@QEAAXPEAX@Z; TransportRelay::Start(void *)
0x1400f2234  nop
0x1400f2235  psrldq  xmm7, 8
0x1400f223a  movq    rbx, xmm7
0x1400f223f  test    rbx, rbx
0x1400f2242  jz      short loc_1400F2278
0x1400f2244  mov     eax, edi
0x1400f2246  lock xadd [rbx+8], eax
0x1400f224b  add     eax, edi
0x1400f224d  jnz     short loc_1400F2278
0x1400f224f  mov     rax, [rbx]
0x1400f2252  mov     rcx, rbx
0x1400f2255  mov     rax, [rax]
0x1400f2258  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400f225d  mov     eax, edi
0x1400f225f  lock xadd [rbx+0Ch], eax
0x1400f2264  add     eax, edi
0x1400f2266  jnz     short loc_1400F2278
0x1400f2268  mov     rax, [rbx]
0x1400f226b  mov     rcx, rbx
0x1400f226e  mov     rax, [rax+8]
0x1400f2272  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400f2277  nop
0x1400f2278  psrldq  xmm6, 8
0x1400f227d  movq    rbx, xmm6
0x1400f2282  test    rbx, rbx
0x1400f2285  jz      short loc_1400F22BB
0x1400f2287  mov     eax, edi
0x1400f2289  lock xadd [rbx+8], eax
0x1400f228e  add     eax, edi
0x1400f2290  jnz     short loc_1400F22BB
0x1400f2292  mov     rax, [rbx]
0x1400f2295  mov     rcx, rbx
0x1400f2298  mov     rax, [rax]
0x1400f229b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400f22a0  mov     eax, edi
0x1400f22a2  lock xadd [rbx+0Ch], eax
0x1400f22a7  add     eax, edi
0x1400f22a9  jnz     short loc_1400F22BB
0x1400f22ab  mov     rax, [rbx]
0x1400f22ae  mov     rcx, rbx
0x1400f22b1  mov     rax, [rax+8]
0x1400f22b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400f22ba  nop
0x1400f22bb  mov     rcx, [r12]; hObject
0x1400f22bf  lea     rax, [rcx-1]
0x1400f22c3  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1400f22c7  ja      short loc_1400F22D0
0x1400f22c9  call    cs:__imp_CloseHandle
0x1400f22cf  nop
0x1400f22d0  mov     rcx, r14; void *
0x1400f22d3  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400f22d8  nop
0x1400f22d9  mov     rcx, [rbp+4Fh+var_B0]
0x1400f22dd  mov     rcx, [rcx+8]
0x1400f22e1  test    rcx, rcx
0x1400f22e4  jz      short loc_1400F22FD
0x1400f22e6  mov     edx, edi
0x1400f22e8  lock xadd [rcx+0Ch], edx
0x1400f22ed  add     edx, edi
0x1400f22ef  jnz     short loc_1400F22FD
0x1400f22f1  mov     rdx, [rcx]
0x1400f22f4  mov     rax, [rdx+8]
0x1400f22f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400f22fd  mov     rax, r15
0x1400f2300  mov     rcx, [rbp+4Fh+var_68]
0x1400f2304  xor     rcx, rsp; StackCookie
0x1400f2307  call    __security_check_cookie
0x1400f230c  lea     r11, [rsp+130h+var_38]
0x1400f2314  movaps  xmm6, xmmword ptr [r11-18h]
0x1400f2319  movaps  xmm7, xmmword ptr [r11-28h]
0x1400f231e  mov     rsp, r11
0x1400f2321  pop     r15
0x1400f2323  pop     r14
0x1400f2325  pop     r13
0x1400f2327  pop     r12
0x1400f2329  pop     rdi
0x1400f232a  pop     rsi
0x1400f232b  pop     rbx
0x1400f232c  pop     rbp
0x1400f232d  retn
0x1400f232e  mov     rcx, [rbp+57h]; this
0x1400f2332  mov     r9d, 139Fh; char *
0x1400f2338  lea     r8, aOnecoreVmCompu_0; "onecore\\vm\\compute\\common\\transport"...
0x1400f233f  mov     edx, 0AEh; void *
0x1400f2344  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
```
