# wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x180012c30`
- end: `0x180012d94`
- name: `?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `356`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x1800323b0`

## callees

- `0x180012c30`
- `0x180012d9c`
- `0x180012f24`
- `0x180012f68`
- `0x1800267d4`
- `0x180031040`
- `0x180031074`
- `0x180085010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180012c91`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180012d23`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180012c91`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180012d23`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180012ce2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180012d80`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180012ce2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180012d80`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012d36`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012d36`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180012d5f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180012d5f`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180012d4b`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180012d4b`

## pseudocode

```c
void __fastcall wil::details::FeatureStateManager::RecordFeatureUsage(
        __int64 a1,
        unsigned int a2,
        unsigned int a3,
        unsigned int a4)
{
  __int64 v8; // r14
  int v9; // eax
  char v10; // di
  DWORD LastError; // edi
  PTP_TIMER ThreadpoolTimer; // rax

  if ( !*(_BYTE *)a1 || !wil::details::FeatureStateManager::EnsureStateData((wil::details::FeatureStateManager *)a1) )
    return;
  v8 = *(_QWORD *)(a1 + 24);
  if ( a3 == 254 )
  {
    wil::details_abi::FeatureStateData::RecordUsage(*(PSRWLOCK *)(a1 + 24));
LABEL_17:
    if ( !wil::details::g_processShutdownInProgress
      && (!wil::details::g_pfnDllShutdownInProgress || !(unsigned __int8)wil::details::g_pfnDllShutdownInProgress()) )
    {
      AcquireSRWLockExclusive((PSRWLOCK)(a1 + 32));
      if ( !*(_BYTE *)(a1 + 65) )
      {
        if ( !*(_QWORD *)(a1 + 48) )
        {
          LastError = GetLastError();
          ThreadpoolTimer = CreateThreadpoolTimer(
                              _lambda_d51448ba32f8ef42e59400edd4566183_::_lambda_invoker_cdecl_,
                              (PVOID)a1,
                              0);
          wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
            a1 + 48,
            ThreadpoolTimer);
          SetLastError(LastError);
        }
        wil::details::EnsureCoalescedTimer_SetTimer(a1 + 48, a1 + 65, 300000);
      }
      if ( a1 != -32 )
        ReleaseSRWLockExclusive((PSRWLOCK)(a1 + 32));
    }
    return;
  }
  if ( a3 < 0xC8 || (int)a3 >= 256 && a3 < 0x200 )
  {
    AcquireSRWLockExclusive(*(PSRWLOCK *)(a1 + 24));
    if ( a3 <= 7 && (v9 = 204, _bittest(&v9, a3)) || a3 - 256 <= 0x7F )
    {
      wil::details_abi::UsageIndex<enum wil_details_ServiceReportingKind,unsigned int,0>::RecordUsage(v8 + 8, a3, a2);
      v10 = *(_BYTE *)(v8 + 64);
    }
    else
    {
      v10 = wil::details_abi::UsageIndex<enum wil_details_ServiceReportingKind,unsigned int,2>::RecordUsage(
              v8 + 72,
              a3,
              a2,
              a4);
    }
    if ( v8 )
      ReleaseSRWLockExclusive((PSRWLOCK)v8);
    if ( v10 )
      goto LABEL_17;
  }
}

```

## disassembly

```asm
0x180012c30  push    rbx
0x180012c32  push    rbp
0x180012c33  push    rsi
0x180012c34  push    rdi
0x180012c35  push    r14
0x180012c37  push    r15
0x180012c39  sub     rsp, 28h
0x180012c3d  mov     rbp, r9
0x180012c40  mov     edi, r8d
0x180012c43  mov     esi, edx
0x180012c45  mov     rbx, rcx
0x180012c48  cmp     byte ptr [rcx], 0
0x180012c4b  jz      loc_180012D87
0x180012c51  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x180012c56  test    al, al
0x180012c58  jz      loc_180012D87
0x180012c5e  mov     r14, [rbx+18h]
0x180012c62  cmp     edi, 0FEh
0x180012c68  jz      loc_180012CF2
0x180012c6e  cmp     edi, 0C8h
0x180012c74  jb      short loc_180012C8E
0x180012c76  cmp     edi, 100h
0x180012c7c  jl      loc_180012D87
0x180012c82  cmp     edi, 200h
0x180012c88  jnb     loc_180012D87
0x180012c8e  mov     rcx, r14; SRWLock
0x180012c91  call    cs:__imp_AcquireSRWLockExclusive
0x180012c97  cmp     edi, 7
0x180012c9a  ja      short loc_180012CA6
0x180012c9c  mov     eax, 0CCh
0x180012ca1  bt      eax, edi
0x180012ca4  jb      short loc_180012CC7
0x180012ca6  lea     eax, [rdi-100h]
0x180012cac  cmp     eax, 7Fh
0x180012caf  jbe     short loc_180012CC7
0x180012cb1  mov     r9d, ebp
0x180012cb4  lea     rcx, [r14+48h]
0x180012cb8  mov     r8d, esi
0x180012cbb  mov     edx, edi
0x180012cbd  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$01@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,2>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x180012cc2  movzx   edi, al
0x180012cc5  jmp     short loc_180012CDA
0x180012cc7  mov     r8d, esi
0x180012cca  mov     edx, edi
0x180012ccc  lea     rcx, [r14+8]
0x180012cd0  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$0A@@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,0>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x180012cd5  movzx   edi, byte ptr [r14+40h]
0x180012cda  test    r14, r14
0x180012cdd  jz      short loc_180012CE8
0x180012cdf  mov     rcx, r14; SRWLock
0x180012ce2  call    cs:__imp_ReleaseSRWLockExclusive
0x180012ce8  test    dil, dil
0x180012ceb  jnz     short loc_180012CFA
0x180012ced  jmp     loc_180012D87
0x180012cf2  mov     rcx, r14; SRWLock
0x180012cf5  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x180012cfa  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x180012d01  jnz     loc_180012D87
0x180012d07  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x180012d0e  test    rax, rax
0x180012d11  jz      short loc_180012D1C
0x180012d13  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012d18  test    al, al
0x180012d1a  jnz     short loc_180012D87
0x180012d1c  lea     rbp, [rbx+20h]
0x180012d20  mov     rcx, rbp; SRWLock
0x180012d23  call    cs:__imp_AcquireSRWLockExclusive
0x180012d29  cmp     byte ptr [rbx+41h], 0
0x180012d2d  jnz     short loc_180012D78
0x180012d2f  cmp     qword ptr [rbx+30h], 0
0x180012d34  jnz     short loc_180012D65
0x180012d36  call    cs:__imp_GetLastError
0x180012d3c  mov     edi, eax
0x180012d3e  xor     r8d, r8d; pcbe
0x180012d41  mov     rdx, rbx; pv
0x180012d44  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_d51448ba32f8ef42e59400edd4566183_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180012d4b  call    cs:__imp_CreateThreadpoolTimer
0x180012d51  mov     rdx, rax
0x180012d54  lea     rcx, [rbx+30h]
0x180012d58  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x180012d5d  mov     ecx, edi; dwErrCode
0x180012d5f  call    cs:__imp_SetLastError
0x180012d65  mov     r8d, 493E0h
0x180012d6b  lea     rdx, [rbx+41h]
0x180012d6f  lea     rcx, [rbx+30h]
0x180012d73  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x180012d78  test    rbp, rbp
0x180012d7b  jz      short loc_180012D87
0x180012d7d  mov     rcx, rbp; SRWLock
0x180012d80  call    cs:__imp_ReleaseSRWLockExclusive
0x180012d86  nop
0x180012d87  add     rsp, 28h
0x180012d8b  pop     r15
0x180012d8d  pop     r14
0x180012d8f  pop     rdi
0x180012d90  pop     rsi
0x180012d91  pop     rbp
0x180012d92  pop     rbx
0x180012d93  retn
```
