# wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)

- ea: `0x18000afb4`
- end: `0x18000b0e3`
- name: `?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z`
- size: `303`
- prototype: `void __fastcall(PVOID pv, unsigned int, struct wil_details_FeatureReportingCache *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x18000c918`

## callees

- `0x18000afb4`
- `0x18000ec2c`
- `0x18000edd0`
- `0x18001d010`

## import_xrefs

- `KERNEL32!SetLastError` at `0x18000b077`
- `KERNEL32!SetLastError` at `0x18000b077`
- `KERNEL32!GetLastError` at `0x18000b043`
- `KERNEL32!GetLastError` at `0x18000b043`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18000b005`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18000b005`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18000b0c0`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18000b0c0`
- `KERNEL32!SetThreadpoolTimer` at `0x18000b0a8`
- `KERNEL32!SetThreadpoolTimer` at `0x18000b0a8`
- `KERNEL32!CreateThreadpoolTimer` at `0x18000b05e`
- `KERNEL32!CreateThreadpoolTimer` at `0x18000b05e`

## pseudocode

```c
void __fastcall wil::details::EnabledStateManager::QueueBackgroundUsageReporting(
        RTL_SRWLOCK *pv,
        __int64 a2,
        struct wil_details_FeatureReportingCache *a3)
{
  struct _TP_TIMER **v5; // r14
  DWORD LastError; // ebx
  struct _TP_TIMER *ThreadpoolTimer; // rax
  struct _TP_TIMER *v8; // rcx
  _QWORD Source[3]; // [rsp+20h] [rbp-18h] BYREF
  struct _FILETIME pftDueTime; // [rsp+40h] [rbp+8h] BYREF

  if ( LOBYTE(pv->Ptr)
    && !wil::details::g_processShutdownInProgress
    && (!wil::details::g_pfnDllShutdownInProgress || !(unsigned __int8)wil::details::g_pfnDllShutdownInProgress()) )
  {
    AcquireSRWLockExclusive(pv + 1);
    Source[0] = 52965666;
    Source[1] = a3;
    wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)&pv[6], Source, 0x10u);
    v5 = (struct _TP_TIMER **)&pv[2];
    if ( !LOBYTE(pv[3].Ptr) )
    {
      if ( !*v5 )
      {
        LastError = GetLastError();
        ThreadpoolTimer = CreateThreadpoolTimer(
                            _lambda_0374aa0a5d1201b2358c6bce99369c58_::_lambda_invoker_cdecl_,
                            pv,
                            0);
        wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
          (struct _TP_TIMER **)&pv[2],
          ThreadpoolTimer);
        SetLastError(LastError);
      }
      v8 = *v5;
      if ( *v5 )
      {
        pftDueTime = (struct _FILETIME)-3000000000LL;
        SetThreadpoolTimer(v8, &pftDueTime, 0, 0x124F8u);
        LOBYTE(pv[3].Ptr) = 1;
      }
    }
    if ( pv != (RTL_SRWLOCK *)-8LL )
      ReleaseSRWLockExclusive(pv + 1);
  }
}

```

## disassembly

```asm
0x18000afb4  mov     [rsp+arg_8], rbx
0x18000afb9  mov     [rsp+arg_10], rsi
0x18000afbe  mov     [rsp+arg_18], rdi
0x18000afc3  push    r14
0x18000afc5  sub     rsp, 30h
0x18000afc9  cmp     byte ptr [rcx], 0
0x18000afcc  mov     rbx, r8
0x18000afcf  mov     rdi, rcx
0x18000afd2  jz      loc_18000B0CC
0x18000afd8  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x18000afdf  jnz     loc_18000B0CC
0x18000afe5  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18000afec  test    rax, rax
0x18000afef  jz      short loc_18000AFFE
0x18000aff1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000aff6  test    al, al
0x18000aff8  jnz     loc_18000B0CC
0x18000affe  lea     rsi, [rdi+8]
0x18000b002  mov     rcx, rsi; SRWLock
0x18000b005  call    cs:__imp_AcquireSRWLockExclusive
0x18000b00c  nop     dword ptr [rax+rax+00h]
0x18000b011  lea     rcx, [rdi+30h]; this
0x18000b015  mov     [rsp+38h+Source], 3283122h
0x18000b01e  mov     r8d, 10h; SourceSize
0x18000b024  mov     [rsp+38h+var_10], rbx
0x18000b029  lea     rdx, [rsp+38h+Source]; Source
0x18000b02e  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x18000b033  cmp     byte ptr [rdi+18h], 0
0x18000b037  lea     r14, [rdi+10h]
0x18000b03b  jnz     short loc_18000B0B8
0x18000b03d  cmp     qword ptr [r14], 0
0x18000b041  jnz     short loc_18000B083
0x18000b043  call    cs:__imp_GetLastError
0x18000b04a  nop     dword ptr [rax+rax+00h]
0x18000b04f  xor     r8d, r8d; pcbe
0x18000b052  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_0374aa0a5d1201b2358c6bce99369c58_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18000b059  mov     rdx, rdi; pv
0x18000b05c  mov     ebx, eax
0x18000b05e  call    cs:__imp_CreateThreadpoolTimer
0x18000b065  nop     dword ptr [rax+rax+00h]
0x18000b06a  mov     rdx, rax
0x18000b06d  mov     rcx, r14
0x18000b070  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x18000b075  mov     ecx, ebx; dwErrCode
0x18000b077  call    cs:__imp_SetLastError
0x18000b07e  nop     dword ptr [rax+rax+00h]
0x18000b083  mov     rcx, [r14]; pti
0x18000b086  test    rcx, rcx
0x18000b089  jz      short loc_18000B0B8
0x18000b08b  mov     rax, 0FFFFFFFF4D2FA200h
0x18000b095  lea     rdx, [rsp+38h+pftDueTime]; pftDueTime
0x18000b09a  mov     r9d, 124F8h; msWindowLength
0x18000b0a0  mov     qword ptr [rsp+38h+pftDueTime.dwLowDateTime], rax
0x18000b0a5  xor     r8d, r8d; msPeriod
0x18000b0a8  call    cs:__imp_SetThreadpoolTimer
0x18000b0af  nop     dword ptr [rax+rax+00h]
0x18000b0b4  mov     byte ptr [rdi+18h], 1
0x18000b0b8  test    rsi, rsi
0x18000b0bb  jz      short loc_18000B0CC
0x18000b0bd  mov     rcx, rsi; SRWLock
0x18000b0c0  call    cs:__imp_ReleaseSRWLockExclusive
0x18000b0c7  nop     dword ptr [rax+rax+00h]
0x18000b0cc  mov     rbx, [rsp+38h+arg_8]
0x18000b0d1  mov     rsi, [rsp+38h+arg_10]
0x18000b0d6  mov     rdi, [rsp+38h+arg_18]
0x18000b0db  add     rsp, 30h
0x18000b0df  pop     r14
0x18000b0e1  retn
```
