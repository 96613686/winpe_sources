# wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)

- ea: `0x18000b4b0`
- end: `0x18000b5f5`
- name: `?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z`
- size: `325`
- prototype: `void __fastcall(PVOID pv, unsigned int, unsigned __int16, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callers

- `0x18000d630`

## callees

- `0x18000b4b0`
- `0x18000dae4`
- `0x18000dc88`
- `0x18002f3e0`
- `0x180030010`

## import_xrefs

- `KERNEL32!SetLastError` at `0x18000b58b`
- `KERNEL32!SetLastError` at `0x18000b58b`
- `KERNEL32!GetLastError` at `0x18000b557`
- `KERNEL32!GetLastError` at `0x18000b557`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18000b511`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18000b511`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18000b5ce`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18000b5ce`
- `KERNEL32!SetThreadpoolTimer` at `0x18000b5b6`
- `KERNEL32!SetThreadpoolTimer` at `0x18000b5b6`
- `KERNEL32!CreateThreadpoolTimer` at `0x18000b572`
- `KERNEL32!CreateThreadpoolTimer` at `0x18000b572`

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
0x18000b4b0  push    rbx
0x18000b4b2  push    rbp
0x18000b4b3  push    rsi
0x18000b4b4  push    rdi
0x18000b4b5  push    r14
0x18000b4b7  push    r15
0x18000b4b9  sub     rsp, 48h
0x18000b4bd  mov     rax, cs:__security_cookie
0x18000b4c4  xor     rax, rsp
0x18000b4c7  mov     [rsp+78h+var_40], rax
0x18000b4cc  xor     r15d, r15d
0x18000b4cf  mov     r14d, r9d
0x18000b4d2  movzx   ebp, r8w
0x18000b4d6  mov     ebx, edx
0x18000b4d8  mov     rdi, rcx
0x18000b4db  cmp     [rcx], r15b
0x18000b4de  jz      loc_18000B5DA
0x18000b4e4  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, r15b; bool wil::details::g_processShutdownInProgress
0x18000b4eb  jnz     loc_18000B5DA
0x18000b4f1  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18000b4f8  test    rax, rax
0x18000b4fb  jz      short loc_18000B50A
0x18000b4fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b502  test    al, al
0x18000b504  jnz     loc_18000B5DA
0x18000b50a  lea     rsi, [rdi+28h]
0x18000b50e  mov     rcx, rsi; SRWLock
0x18000b511  call    cs:__imp_AcquireSRWLockExclusive
0x18000b518  nop     dword ptr [rax+rax+00h]
0x18000b51d  lea     rcx, [rdi+0E8h]; this
0x18000b524  mov     [rsp+78h+var_4A], r15w
0x18000b52a  mov     r8d, 0Ch; SourceSize
0x18000b530  mov     [rsp+78h+Source], ebx
0x18000b534  lea     rdx, [rsp+78h+Source]; Source
0x18000b539  mov     [rsp+78h+var_4C], bp
0x18000b53e  mov     [rsp+78h+var_48], r14d
0x18000b543  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x18000b548  lea     r14, [rdi+38h]
0x18000b54c  cmp     [rdi+40h], r15b
0x18000b550  jnz     short loc_18000B5C6
0x18000b552  cmp     [r14], r15
0x18000b555  jnz     short loc_18000B597
0x18000b557  call    cs:__imp_GetLastError
0x18000b55e  nop     dword ptr [rax+rax+00h]
0x18000b563  xor     r8d, r8d; pcbe
0x18000b566  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_5035b992506f4af81a770c5842624510_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18000b56d  mov     rdx, rdi; pv
0x18000b570  mov     ebx, eax
0x18000b572  call    cs:__imp_CreateThreadpoolTimer
0x18000b579  nop     dword ptr [rax+rax+00h]
0x18000b57e  mov     rdx, rax
0x18000b581  mov     rcx, r14
0x18000b584  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x18000b589  mov     ecx, ebx; dwErrCode
0x18000b58b  call    cs:__imp_SetLastError
0x18000b592  nop     dword ptr [rax+rax+00h]
0x18000b597  mov     rcx, [r14]; pti
0x18000b59a  test    rcx, rcx
0x18000b59d  jz      short loc_18000B5C6
0x18000b59f  mov     r9d, 4E2h; msWindowLength
0x18000b5a5  mov     qword ptr [rsp+78h+pftDueTime.dwLowDateTime], 0FFFFFFFFFD050F80h
0x18000b5ae  xor     r8d, r8d; msPeriod
0x18000b5b1  lea     rdx, [rsp+78h+pftDueTime]; pftDueTime
0x18000b5b6  call    cs:__imp_SetThreadpoolTimer
0x18000b5bd  nop     dword ptr [rax+rax+00h]
0x18000b5c2  mov     byte ptr [rdi+40h], 1
0x18000b5c6  test    rsi, rsi
0x18000b5c9  jz      short loc_18000B5DA
0x18000b5cb  mov     rcx, rsi; SRWLock
0x18000b5ce  call    cs:__imp_ReleaseSRWLockExclusive
0x18000b5d5  nop     dword ptr [rax+rax+00h]
0x18000b5da  mov     rcx, [rsp+78h+var_40]
0x18000b5df  xor     rcx, rsp; StackCookie
0x18000b5e2  call    __security_check_cookie
0x18000b5e7  add     rsp, 48h
0x18000b5eb  pop     r15
0x18000b5ed  pop     r14
0x18000b5ef  pop     rdi
0x18000b5f0  pop     rsi
0x18000b5f1  pop     rbp
0x18000b5f2  pop     rbx
0x18000b5f3  retn
```
