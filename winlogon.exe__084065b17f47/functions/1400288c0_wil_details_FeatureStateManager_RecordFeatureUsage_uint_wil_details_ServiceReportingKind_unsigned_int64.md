# wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x1400288c0`
- end: `0x140028a18`
- name: `?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `344`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, service_task`

## callers

- `0x1400446f0`

## callees

- `0x1400288c0`
- `0x140028a20`
- `0x140028aac`
- `0x140028acc`
- `0x140028b88`
- `0x140029270`
- `0x1400292b4`
- `0x14004a58c`
- `0x14004a5ac`
- `0x14004b6d0`
- `0x140057de0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400289ff`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400289ff`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140028926`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14002899d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140028926`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14002899d`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1400289ca`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1400289ca`

## pseudocode

```c
void __fastcall wil::details::FeatureStateManager::RecordFeatureUsage(
        __int64 a1,
        unsigned int a2,
        unsigned int a3,
        unsigned int a4)
{
  __int64 v8; // rsi
  int v9; // eax
  char v10; // bl
  wil *v11; // rcx
  PTP_TIMER ThreadpoolTimer; // rax
  __int64 v13; // [rsp+40h] [rbp+8h] BYREF

  if ( !*(_BYTE *)a1 || !wil::details::FeatureStateManager::EnsureStateData((wil::details::FeatureStateManager *)a1) )
    return;
  v8 = *(_QWORD *)(a1 + 24);
  if ( a3 == 254 )
  {
    wil::details_abi::FeatureStateData::RecordUsage(*(PSRWLOCK *)(a1 + 24));
  }
  else
  {
    if ( a3 >= 0xC8 && ((int)a3 < 256 || a3 >= 0x200) )
      return;
    if ( (AcquireSRWLockExclusive(*(PSRWLOCK *)(a1 + 24)), v13 = v8, a3 <= 7) && (v9 = 204, _bittest(&v9, a3))
      || a3 - 256 <= 0x7F )
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
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v13);
    if ( !v10 )
      return;
  }
  if ( !wil::ProcessShutdownInProgress(v11) )
  {
    AcquireSRWLockExclusive((PSRWLOCK)(a1 + 32));
    if ( !*(_BYTE *)(a1 + 65) )
    {
      if ( !*(_QWORD *)(a1 + 48) )
      {
        wil::last_error_context::last_error_context((wil::last_error_context *)&v13);
        ThreadpoolTimer = CreateThreadpoolTimer(
                            _lambda_d51448ba32f8ef42e59400edd4566183_::_lambda_invoker_cdecl_,
                            (PVOID)a1,
                            0);
        wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
          a1 + 48,
          ThreadpoolTimer);
        wil::last_error_context::~last_error_context((wil::last_error_context *)&v13);
      }
      wil::details::EnsureCoalescedTimer_SetTimer(a1 + 48, a1 + 65, 300000);
    }
    if ( a1 != -32 )
      ReleaseSRWLockExclusive((PSRWLOCK)(a1 + 32));
  }
}

```

## disassembly

```asm
0x1400288c0  mov     [rsp+arg_8], rbx
0x1400288c5  mov     [rsp+arg_10], rbp
0x1400288ca  push    rsi
0x1400288cb  push    rdi
0x1400288cc  push    r14
0x1400288ce  sub     rsp, 20h
0x1400288d2  cmp     byte ptr [rcx], 0
0x1400288d5  mov     r14, r9
0x1400288d8  mov     ebx, r8d
0x1400288db  mov     ebp, edx
0x1400288dd  mov     rdi, rcx
0x1400288e0  jz      loc_140028A05
0x1400288e6  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x1400288eb  test    al, al
0x1400288ed  jz      loc_140028A05
0x1400288f3  mov     rsi, [rdi+18h]
0x1400288f7  cmp     ebx, 0FEh
0x1400288fd  jz      loc_140028985
0x140028903  cmp     ebx, 0C8h
0x140028909  jb      short loc_140028923
0x14002890b  cmp     ebx, 100h
0x140028911  jl      loc_140028A05
0x140028917  cmp     ebx, 200h
0x14002891d  jnb     loc_140028A05
0x140028923  mov     rcx, rsi; SRWLock
0x140028926  call    cs:__imp_AcquireSRWLockExclusive
0x14002892c  mov     [rsp+38h+arg_0], rsi
0x140028931  cmp     ebx, 7
0x140028934  ja      short loc_140028940
0x140028936  mov     eax, 0CCh
0x14002893b  bt      eax, ebx
0x14002893e  jb      short loc_140028960
0x140028940  lea     eax, [rbx-100h]
0x140028946  cmp     eax, 7Fh
0x140028949  jbe     short loc_140028960
0x14002894b  mov     r9d, r14d
0x14002894e  lea     rcx, [rsi+48h]
0x140028952  mov     r8d, ebp
0x140028955  mov     edx, ebx
0x140028957  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$01@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,2>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x14002895c  mov     bl, al
0x14002895e  jmp     short loc_140028971
0x140028960  mov     r8d, ebp
0x140028963  lea     rcx, [rsi+8]
0x140028967  mov     edx, ebx
0x140028969  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$0A@@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,0>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x14002896e  mov     bl, [rsi+40h]
0x140028971  lea     rcx, [rsp+38h+arg_0]
0x140028976  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x14002897b  test    bl, bl
0x14002897d  jz      loc_140028A05
0x140028983  jmp     short loc_14002898D
0x140028985  mov     rcx, rsi; SRWLock
0x140028988  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x14002898d  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x140028992  test    al, al
0x140028994  jnz     short loc_140028A05
0x140028996  lea     rbx, [rdi+20h]
0x14002899a  mov     rcx, rbx; SRWLock
0x14002899d  call    cs:__imp_AcquireSRWLockExclusive
0x1400289a3  cmp     byte ptr [rdi+41h], 0
0x1400289a7  jnz     short loc_1400289F7
0x1400289a9  lea     rsi, [rdi+30h]
0x1400289ad  cmp     qword ptr [rsi], 0
0x1400289b1  jnz     short loc_1400289E5
0x1400289b3  lea     rcx, [rsp+38h+arg_0]; this
0x1400289b8  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x1400289bd  xor     r8d, r8d; pcbe
0x1400289c0  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_d51448ba32f8ef42e59400edd4566183_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x1400289c7  mov     rdx, rdi; pv
0x1400289ca  call    cs:__imp_CreateThreadpoolTimer
0x1400289d0  mov     rdx, rax
0x1400289d3  mov     rcx, rsi
0x1400289d6  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x1400289db  lea     rcx, [rsp+38h+arg_0]; this
0x1400289e0  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x1400289e5  mov     r8d, 493E0h
0x1400289eb  lea     rdx, [rdi+41h]
0x1400289ef  mov     rcx, rsi
0x1400289f2  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x1400289f7  test    rbx, rbx
0x1400289fa  jz      short loc_140028A05
0x1400289fc  mov     rcx, rbx; SRWLock
0x1400289ff  call    cs:__imp_ReleaseSRWLockExclusive
0x140028a05  mov     rbx, [rsp+38h+arg_8]
0x140028a0a  mov     rbp, [rsp+38h+arg_10]
0x140028a0f  add     rsp, 20h
0x140028a13  pop     r14
0x140028a15  pop     rdi
0x140028a16  pop     rsi
0x140028a17  retn
```
