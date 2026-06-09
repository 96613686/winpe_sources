# wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x1800051b0`
- end: `0x180005376`
- name: `?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `454`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x18001c330`

## callees

- `0x180004600`
- `0x1800051b0`
- `0x18000537c`
- `0x180005600`
- `0x1800058c4`
- `0x180006cbc`
- `0x180006d00`
- `0x1800207b4`
- `0x180025e60`
- `0x180042010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180005248`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800052a6`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180005248`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800052a6`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000526f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000526f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005312`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005312`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800052f4`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800052f4`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
void __fastcall wil::details::FeatureStateManager::RecordFeatureUsage(
        __int64 a1,
        unsigned int a2,
        unsigned int a3,
        unsigned int a4)
{
  __int64 v8; // rsi
  int v9; // eax
  char v10; // di
  PSRWLOCK v11; // rcx
  PTP_TIMER ThreadpoolTimer; // rax
  PSRWLOCK SRWLock; // [rsp+50h] [rbp+8h] BYREF

  if ( !*(_BYTE *)a1 || !wil::details::FeatureStateManager::EnsureStateData((wil::details::FeatureStateManager *)a1) )
    return;
  v8 = *(_QWORD *)(a1 + 24);
  if ( a3 == 254 )
  {
    wil::details_abi::FeatureStateData::RecordUsage(*(PSRWLOCK *)(a1 + 24));
LABEL_11:
    if ( !wil::details::g_processShutdownInProgress
      && (!wil::details::g_pfnDllShutdownInProgress || !(unsigned __int8)wil::details::g_pfnDllShutdownInProgress(v11)) )
    {
      AcquireSRWLockExclusive((PSRWLOCK)(a1 + 32));
      if ( !*(_BYTE *)(a1 + 65) )
      {
        if ( !*(_QWORD *)(a1 + 48) )
        {
          wil::last_error_context::last_error_context((wil::last_error_context *)&SRWLock);
          ThreadpoolTimer = CreateThreadpoolTimer(
                              _lambda_d51448ba32f8ef42e59400edd4566183_::_lambda_invoker_cdecl_,
                              (PVOID)a1,
                              0);
          wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
            a1 + 48,
            ThreadpoolTimer);
          if ( !(_BYTE)SRWLock )
            SetLastError(HIDWORD(SRWLock));
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
    wil::srwlock::lock_exclusive(*(_QWORD *)(a1 + 24), &SRWLock);
    if ( a3 <= 7 && (v9 = 204, _bittest(&v9, a3)) || a3 - 256 <= 0x7F )
    {
      wil::details_abi::UsageIndex<enum wil_details_ServiceReportingKind,unsigned int,0>::RecordUsage((wil::details_abi::RawUsageIndex *)(v8 + 8));
      v10 = *(_BYTE *)(v8 + 64);
    }
    else
    {
      v10 = wil::details_abi::UsageIndex<enum wil_details_ServiceReportingKind,unsigned int,2>::RecordUsage(
              v8 + 72,
              a3,
              a2,
              a4,
              0);
    }
    v11 = SRWLock;
    if ( SRWLock )
      ReleaseSRWLockExclusive(SRWLock);
    if ( v10 )
      goto LABEL_11;
  }
}

```

## disassembly

```asm
0x1800051b0  mov     [rsp+arg_8], rbx
0x1800051b5  mov     [rsp+arg_10], rbp
0x1800051ba  push    rsi
0x1800051bb  push    rdi
0x1800051bc  push    r14
0x1800051be  sub     rsp, 30h
0x1800051c2  mov     r14, r9
0x1800051c5  mov     edi, r8d
0x1800051c8  mov     ebp, edx
0x1800051ca  mov     rbx, rcx
0x1800051cd  mov     [rsp+48h+var_28], 0
0x1800051d5  cmp     byte ptr [rcx], 0
0x1800051d8  jz      loc_1800052AD
0x1800051de  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x1800051e3  test    al, al
0x1800051e5  jz      loc_1800052AD
0x1800051eb  mov     rsi, [rbx+18h]
0x1800051ef  cmp     edi, 0FEh
0x1800051f5  jz      loc_1800052C0
0x1800051fb  cmp     edi, 0C8h
0x180005201  jnb     loc_180005330
0x180005207  lea     rdx, [rsp+48h+SRWLock]
0x18000520c  mov     rcx, rsi
0x18000520f  call    ?lock_exclusive@srwlock@wil@@QEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::srwlock::lock_exclusive(void)
0x180005214  nop
0x180005215  cmp     edi, 7
0x180005218  ja      loc_18000534D
0x18000521e  mov     eax, 0CCh
0x180005223  bt      eax, edi
0x180005226  jnb     loc_18000534D
0x18000522c  mov     r8d, ebp
0x18000522f  mov     edx, edi
0x180005231  lea     rcx, [rsi+8]; this
0x180005235  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$0A@@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,0>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x18000523a  movzx   edi, byte ptr [rsi+40h]
0x18000523e  mov     rcx, [rsp+48h+SRWLock]; SRWLock
0x180005243  test    rcx, rcx
0x180005246  jz      short loc_18000524E
0x180005248  call    cs:__imp_ReleaseSRWLockExclusive
0x18000524e  test    dil, dil
0x180005251  jz      short loc_1800052AD
0x180005253  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x18000525a  jnz     short loc_1800052AD
0x18000525c  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x180005263  test    rax, rax
0x180005266  jnz     short loc_1800052CA
0x180005268  lea     rsi, [rbx+20h]
0x18000526c  mov     rcx, rsi; SRWLock
0x18000526f  call    cs:__imp_AcquireSRWLockExclusive
0x180005275  mov     [rsp+48h+var_20], rsi
0x18000527a  mov     edi, 8
0x18000527f  mov     [rsp+48h+var_28], edi
0x180005283  and     edi, 0FFFFFFF7h
0x180005286  mov     [rsp+48h+var_28], edi
0x18000528a  or      edi, 4
0x18000528d  mov     [rsp+48h+var_28], edi
0x180005291  cmp     byte ptr [rbx+41h], 0
0x180005295  jz      short loc_1800052D5
0x180005297  and     edi, 0FFFFFFFBh
0x18000529a  mov     [rsp+48h+var_28], edi
0x18000529e  test    rsi, rsi
0x1800052a1  jz      short loc_1800052AD
0x1800052a3  mov     rcx, rsi; SRWLock
0x1800052a6  call    cs:__imp_ReleaseSRWLockExclusive
0x1800052ac  nop
0x1800052ad  mov     rbx, [rsp+48h+arg_8]
0x1800052b2  mov     rbp, [rsp+48h+arg_10]
0x1800052b7  add     rsp, 30h
0x1800052bb  pop     r14
0x1800052bd  pop     rdi
0x1800052be  pop     rsi
0x1800052bf  retn
0x1800052c0  mov     rcx, rsi; SRWLock
0x1800052c3  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x1800052c8  jmp     short loc_180005253
0x1800052ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800052cf  test    al, al
0x1800052d1  jz      short loc_180005268
0x1800052d3  jmp     short loc_1800052AD
0x1800052d5  cmp     qword ptr [rbx+30h], 0
0x1800052da  jnz     short loc_180005318
0x1800052dc  lea     rcx, [rsp+48h+SRWLock]; this
0x1800052e1  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x1800052e6  nop
0x1800052e7  xor     r8d, r8d; pcbe
0x1800052ea  mov     rdx, rbx; pv
0x1800052ed  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_d51448ba32f8ef42e59400edd4566183_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x1800052f4  call    cs:__imp_CreateThreadpoolTimer
0x1800052fa  mov     rdx, rax
0x1800052fd  lea     rcx, [rbx+30h]
0x180005301  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x180005306  nop
0x180005307  cmp     byte ptr [rsp+48h+SRWLock], 0
0x18000530c  jnz     short loc_180005318
0x18000530e  mov     ecx, dword ptr [rsp+48h+SRWLock+4]; dwErrCode
0x180005312  call    cs:__imp_SetLastError
0x180005318  mov     r8d, 493E0h
0x18000531e  lea     rdx, [rbx+41h]
0x180005322  lea     rcx, [rbx+30h]
0x180005326  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x18000532b  jmp     loc_180005297
0x180005330  cmp     edi, 100h
0x180005336  jl      loc_1800052AD
0x18000533c  cmp     edi, 200h
0x180005342  jnb     loc_1800052AD
0x180005348  jmp     loc_180005207
0x18000534d  lea     eax, [rdi-100h]
0x180005353  cmp     eax, 7Fh
0x180005356  jbe     loc_18000522C
0x18000535c  mov     r9d, r14d
0x18000535f  lea     rcx, [rsi+48h]
0x180005363  mov     r8d, ebp
0x180005366  mov     edx, edi
0x180005368  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$01@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,2>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x18000536d  movzx   edi, al
0x180005370  jmp     loc_18000523E
```
