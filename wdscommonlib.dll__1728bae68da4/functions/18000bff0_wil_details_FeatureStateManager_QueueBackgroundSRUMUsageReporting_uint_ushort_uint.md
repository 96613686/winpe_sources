# wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)

- ea: `0x18000bff0`
- end: `0x18000c135`
- name: `?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z`
- size: `325`
- prototype: `void __fastcall(PVOID pv, unsigned int, unsigned __int16, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callers

- `0x18000e170`

## callees

- `0x18000bff0`
- `0x18000e624`
- `0x18000e7c8`
- `0x180030390`
- `0x180031010`

## import_xrefs

- `KERNEL32!SetLastError` at `0x18000c0cb`
- `KERNEL32!SetLastError` at `0x18000c0cb`
- `KERNEL32!GetLastError` at `0x18000c097`
- `KERNEL32!GetLastError` at `0x18000c097`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18000c051`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18000c051`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18000c10e`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18000c10e`
- `KERNEL32!SetThreadpoolTimer` at `0x18000c0f6`
- `KERNEL32!SetThreadpoolTimer` at `0x18000c0f6`
- `KERNEL32!CreateThreadpoolTimer` at `0x18000c0b2`
- `KERNEL32!CreateThreadpoolTimer` at `0x18000c0b2`

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
0x18000bff0  push    rbx
0x18000bff2  push    rbp
0x18000bff3  push    rsi
0x18000bff4  push    rdi
0x18000bff5  push    r14
0x18000bff7  push    r15
0x18000bff9  sub     rsp, 48h
0x18000bffd  mov     rax, cs:__security_cookie
0x18000c004  xor     rax, rsp
0x18000c007  mov     [rsp+78h+var_40], rax
0x18000c00c  xor     r15d, r15d
0x18000c00f  mov     r14d, r9d
0x18000c012  movzx   ebp, r8w
0x18000c016  mov     ebx, edx
0x18000c018  mov     rdi, rcx
0x18000c01b  cmp     [rcx], r15b
0x18000c01e  jz      loc_18000C11A
0x18000c024  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, r15b; bool wil::details::g_processShutdownInProgress
0x18000c02b  jnz     loc_18000C11A
0x18000c031  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18000c038  test    rax, rax
0x18000c03b  jz      short loc_18000C04A
0x18000c03d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c042  test    al, al
0x18000c044  jnz     loc_18000C11A
0x18000c04a  lea     rsi, [rdi+28h]
0x18000c04e  mov     rcx, rsi; SRWLock
0x18000c051  call    cs:__imp_AcquireSRWLockExclusive
0x18000c058  nop     dword ptr [rax+rax+00h]
0x18000c05d  lea     rcx, [rdi+0E8h]; this
0x18000c064  mov     [rsp+78h+var_4A], r15w
0x18000c06a  mov     r8d, 0Ch; SourceSize
0x18000c070  mov     [rsp+78h+Source], ebx
0x18000c074  lea     rdx, [rsp+78h+Source]; Source
0x18000c079  mov     [rsp+78h+var_4C], bp
0x18000c07e  mov     [rsp+78h+var_48], r14d
0x18000c083  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x18000c088  lea     r14, [rdi+38h]
0x18000c08c  cmp     [rdi+40h], r15b
0x18000c090  jnz     short loc_18000C106
0x18000c092  cmp     [r14], r15
0x18000c095  jnz     short loc_18000C0D7
0x18000c097  call    cs:__imp_GetLastError
0x18000c09e  nop     dword ptr [rax+rax+00h]
0x18000c0a3  xor     r8d, r8d; pcbe
0x18000c0a6  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_5035b992506f4af81a770c5842624510_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18000c0ad  mov     rdx, rdi; pv
0x18000c0b0  mov     ebx, eax
0x18000c0b2  call    cs:__imp_CreateThreadpoolTimer
0x18000c0b9  nop     dword ptr [rax+rax+00h]
0x18000c0be  mov     rdx, rax
0x18000c0c1  mov     rcx, r14
0x18000c0c4  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x18000c0c9  mov     ecx, ebx; dwErrCode
0x18000c0cb  call    cs:__imp_SetLastError
0x18000c0d2  nop     dword ptr [rax+rax+00h]
0x18000c0d7  mov     rcx, [r14]; pti
0x18000c0da  test    rcx, rcx
0x18000c0dd  jz      short loc_18000C106
0x18000c0df  mov     r9d, 4E2h; msWindowLength
0x18000c0e5  mov     qword ptr [rsp+78h+pftDueTime.dwLowDateTime], 0FFFFFFFFFD050F80h
0x18000c0ee  xor     r8d, r8d; msPeriod
0x18000c0f1  lea     rdx, [rsp+78h+pftDueTime]; pftDueTime
0x18000c0f6  call    cs:__imp_SetThreadpoolTimer
0x18000c0fd  nop     dword ptr [rax+rax+00h]
0x18000c102  mov     byte ptr [rdi+40h], 1
0x18000c106  test    rsi, rsi
0x18000c109  jz      short loc_18000C11A
0x18000c10b  mov     rcx, rsi; SRWLock
0x18000c10e  call    cs:__imp_ReleaseSRWLockExclusive
0x18000c115  nop     dword ptr [rax+rax+00h]
0x18000c11a  mov     rcx, [rsp+78h+var_40]
0x18000c11f  xor     rcx, rsp; StackCookie
0x18000c122  call    __security_check_cookie
0x18000c127  add     rsp, 48h
0x18000c12b  pop     r15
0x18000c12d  pop     r14
0x18000c12f  pop     rdi
0x18000c130  pop     rsi
0x18000c131  pop     rbp
0x18000c132  pop     rbx
0x18000c133  retn
```
