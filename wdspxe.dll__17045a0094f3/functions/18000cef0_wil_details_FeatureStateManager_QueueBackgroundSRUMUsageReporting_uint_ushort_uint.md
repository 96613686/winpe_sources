# wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)

- ea: `0x18000cef0`
- end: `0x18000d035`
- name: `?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z`
- size: `325`
- prototype: `void __fastcall(PVOID pv, unsigned int, unsigned __int16, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callers

- `0x180010600`

## callees

- `0x18000cef0`
- `0x180010adc`
- `0x180010c80`
- `0x180011a90`
- `0x180013010`

## import_xrefs

- `KERNEL32!SetLastError` at `0x18000cfcb`
- `KERNEL32!SetLastError` at `0x18000cfcb`
- `KERNEL32!GetLastError` at `0x18000cf97`
- `KERNEL32!GetLastError` at `0x18000cf97`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18000cf51`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18000cf51`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18000d00e`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18000d00e`
- `KERNEL32!SetThreadpoolTimer` at `0x18000cff6`
- `KERNEL32!SetThreadpoolTimer` at `0x18000cff6`
- `KERNEL32!CreateThreadpoolTimer` at `0x18000cfb2`
- `KERNEL32!CreateThreadpoolTimer` at `0x18000cfb2`

## pseudocode

```c
void __fastcall wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(
        RTL_SRWLOCK *pv,
        int a2,
        __int16 a3,
        int a4)
{
  struct _TP_TIMER **v8; // r14
  DWORD LastError; // ebx
  struct _TP_TIMER *ThreadpoolTimer; // rax
  struct _TP_TIMER *v11; // rcx
  struct _FILETIME pftDueTime; // [rsp+20h] [rbp-58h] BYREF
  int Source; // [rsp+28h] [rbp-50h] BYREF
  __int16 v14; // [rsp+2Ch] [rbp-4Ch]
  __int16 v15; // [rsp+2Eh] [rbp-4Ah]
  int v16; // [rsp+30h] [rbp-48h]

  if ( LOBYTE(pv->Ptr)
    && !wil::details::g_processShutdownInProgress
    && (!wil::details::g_pfnDllShutdownInProgress || !(unsigned __int8)wil::details::g_pfnDllShutdownInProgress()) )
  {
    AcquireSRWLockExclusive(pv + 5);
    v15 = 0;
    Source = a2;
    v14 = a3;
    v16 = a4;
    wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)&pv[29], &Source, 0xCu);
    v8 = (struct _TP_TIMER **)&pv[7];
    if ( !LOBYTE(pv[8].Ptr) )
    {
      if ( !*v8 )
      {
        LastError = GetLastError();
        ThreadpoolTimer = CreateThreadpoolTimer(
                            _lambda_5035b992506f4af81a770c5842624510_::_lambda_invoker_cdecl_,
                            pv,
                            0);
        wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
          (struct _TP_TIMER **)&pv[7],
          ThreadpoolTimer);
        SetLastError(LastError);
      }
      v11 = *v8;
      if ( *v8 )
      {
        pftDueTime = (struct _FILETIME)-50000000LL;
        SetThreadpoolTimer(v11, &pftDueTime, 0, 0x4E2u);
        LOBYTE(pv[8].Ptr) = 1;
      }
    }
    if ( pv != (RTL_SRWLOCK *)-40LL )
      ReleaseSRWLockExclusive(pv + 5);
  }
}

```

## disassembly

```asm
0x18000cef0  push    rbx
0x18000cef2  push    rbp
0x18000cef3  push    rsi
0x18000cef4  push    rdi
0x18000cef5  push    r14
0x18000cef7  push    r15
0x18000cef9  sub     rsp, 48h
0x18000cefd  mov     rax, cs:__security_cookie
0x18000cf04  xor     rax, rsp
0x18000cf07  mov     [rsp+78h+var_40], rax
0x18000cf0c  xor     r15d, r15d
0x18000cf0f  mov     r14d, r9d
0x18000cf12  movzx   ebp, r8w
0x18000cf16  mov     ebx, edx
0x18000cf18  mov     rdi, rcx
0x18000cf1b  cmp     [rcx], r15b
0x18000cf1e  jz      loc_18000D01A
0x18000cf24  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, r15b; bool wil::details::g_processShutdownInProgress
0x18000cf2b  jnz     loc_18000D01A
0x18000cf31  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18000cf38  test    rax, rax
0x18000cf3b  jz      short loc_18000CF4A
0x18000cf3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cf42  test    al, al
0x18000cf44  jnz     loc_18000D01A
0x18000cf4a  lea     rsi, [rdi+28h]
0x18000cf4e  mov     rcx, rsi; SRWLock
0x18000cf51  call    cs:__imp_AcquireSRWLockExclusive
0x18000cf58  nop     dword ptr [rax+rax+00h]
0x18000cf5d  lea     rcx, [rdi+0E8h]; this
0x18000cf64  mov     [rsp+78h+var_4A], r15w
0x18000cf6a  mov     r8d, 0Ch; SourceSize
0x18000cf70  mov     [rsp+78h+Source], ebx
0x18000cf74  lea     rdx, [rsp+78h+Source]; Source
0x18000cf79  mov     [rsp+78h+var_4C], bp
0x18000cf7e  mov     [rsp+78h+var_48], r14d
0x18000cf83  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x18000cf88  lea     r14, [rdi+38h]
0x18000cf8c  cmp     [rdi+40h], r15b
0x18000cf90  jnz     short loc_18000D006
0x18000cf92  cmp     [r14], r15
0x18000cf95  jnz     short loc_18000CFD7
0x18000cf97  call    cs:__imp_GetLastError
0x18000cf9e  nop     dword ptr [rax+rax+00h]
0x18000cfa3  xor     r8d, r8d; pcbe
0x18000cfa6  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_5035b992506f4af81a770c5842624510_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18000cfad  mov     rdx, rdi; pv
0x18000cfb0  mov     ebx, eax
0x18000cfb2  call    cs:__imp_CreateThreadpoolTimer
0x18000cfb9  nop     dword ptr [rax+rax+00h]
0x18000cfbe  mov     rdx, rax
0x18000cfc1  mov     rcx, r14
0x18000cfc4  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x18000cfc9  mov     ecx, ebx; dwErrCode
0x18000cfcb  call    cs:__imp_SetLastError
0x18000cfd2  nop     dword ptr [rax+rax+00h]
0x18000cfd7  mov     rcx, [r14]; pti
0x18000cfda  test    rcx, rcx
0x18000cfdd  jz      short loc_18000D006
0x18000cfdf  mov     r9d, 4E2h; msWindowLength
0x18000cfe5  mov     qword ptr [rsp+78h+pftDueTime.dwLowDateTime], 0FFFFFFFFFD050F80h
0x18000cfee  xor     r8d, r8d; msPeriod
0x18000cff1  lea     rdx, [rsp+78h+pftDueTime]; pftDueTime
0x18000cff6  call    cs:__imp_SetThreadpoolTimer
0x18000cffd  nop     dword ptr [rax+rax+00h]
0x18000d002  mov     byte ptr [rdi+40h], 1
0x18000d006  test    rsi, rsi
0x18000d009  jz      short loc_18000D01A
0x18000d00b  mov     rcx, rsi; SRWLock
0x18000d00e  call    cs:__imp_ReleaseSRWLockExclusive
0x18000d015  nop     dword ptr [rax+rax+00h]
0x18000d01a  mov     rcx, [rsp+78h+var_40]
0x18000d01f  xor     rcx, rsp; StackCookie
0x18000d022  call    __security_check_cookie
0x18000d027  add     rsp, 48h
0x18000d02b  pop     r15
0x18000d02d  pop     r14
0x18000d02f  pop     rdi
0x18000d030  pop     rsi
0x18000d031  pop     rbp
0x18000d032  pop     rbx
0x18000d033  retn
```
