# wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)

- ea: `0x18000ae68`
- end: `0x18000afad`
- name: `?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z`
- size: `325`
- prototype: `void __fastcall(PVOID pv, unsigned int, unsigned __int16, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callers

- `0x18000e4f0`

## callees

- `0x18000ae68`
- `0x18000ec2c`
- `0x18000edd0`
- `0x18001c150`
- `0x18001d010`

## import_xrefs

- `KERNEL32!SetLastError` at `0x18000af43`
- `KERNEL32!SetLastError` at `0x18000af43`
- `KERNEL32!GetLastError` at `0x18000af0f`
- `KERNEL32!GetLastError` at `0x18000af0f`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18000aec9`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18000aec9`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18000af86`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18000af86`
- `KERNEL32!SetThreadpoolTimer` at `0x18000af6e`
- `KERNEL32!SetThreadpoolTimer` at `0x18000af6e`
- `KERNEL32!CreateThreadpoolTimer` at `0x18000af2a`
- `KERNEL32!CreateThreadpoolTimer` at `0x18000af2a`

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
0x18000ae68  push    rbx
0x18000ae6a  push    rbp
0x18000ae6b  push    rsi
0x18000ae6c  push    rdi
0x18000ae6d  push    r14
0x18000ae6f  push    r15
0x18000ae71  sub     rsp, 48h
0x18000ae75  mov     rax, cs:__security_cookie
0x18000ae7c  xor     rax, rsp
0x18000ae7f  mov     [rsp+78h+var_40], rax
0x18000ae84  xor     r15d, r15d
0x18000ae87  mov     r14d, r9d
0x18000ae8a  movzx   ebp, r8w
0x18000ae8e  mov     ebx, edx
0x18000ae90  mov     rdi, rcx
0x18000ae93  cmp     [rcx], r15b
0x18000ae96  jz      loc_18000AF92
0x18000ae9c  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, r15b; bool wil::details::g_processShutdownInProgress
0x18000aea3  jnz     loc_18000AF92
0x18000aea9  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18000aeb0  test    rax, rax
0x18000aeb3  jz      short loc_18000AEC2
0x18000aeb5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000aeba  test    al, al
0x18000aebc  jnz     loc_18000AF92
0x18000aec2  lea     rsi, [rdi+28h]
0x18000aec6  mov     rcx, rsi; SRWLock
0x18000aec9  call    cs:__imp_AcquireSRWLockExclusive
0x18000aed0  nop     dword ptr [rax+rax+00h]
0x18000aed5  lea     rcx, [rdi+0E8h]; this
0x18000aedc  mov     [rsp+78h+var_4A], r15w
0x18000aee2  mov     r8d, 0Ch; SourceSize
0x18000aee8  mov     [rsp+78h+Source], ebx
0x18000aeec  lea     rdx, [rsp+78h+Source]; Source
0x18000aef1  mov     [rsp+78h+var_4C], bp
0x18000aef6  mov     [rsp+78h+var_48], r14d
0x18000aefb  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x18000af00  lea     r14, [rdi+38h]
0x18000af04  cmp     [rdi+40h], r15b
0x18000af08  jnz     short loc_18000AF7E
0x18000af0a  cmp     [r14], r15
0x18000af0d  jnz     short loc_18000AF4F
0x18000af0f  call    cs:__imp_GetLastError
0x18000af16  nop     dword ptr [rax+rax+00h]
0x18000af1b  xor     r8d, r8d; pcbe
0x18000af1e  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_5035b992506f4af81a770c5842624510_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18000af25  mov     rdx, rdi; pv
0x18000af28  mov     ebx, eax
0x18000af2a  call    cs:__imp_CreateThreadpoolTimer
0x18000af31  nop     dword ptr [rax+rax+00h]
0x18000af36  mov     rdx, rax
0x18000af39  mov     rcx, r14
0x18000af3c  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x18000af41  mov     ecx, ebx; dwErrCode
0x18000af43  call    cs:__imp_SetLastError
0x18000af4a  nop     dword ptr [rax+rax+00h]
0x18000af4f  mov     rcx, [r14]; pti
0x18000af52  test    rcx, rcx
0x18000af55  jz      short loc_18000AF7E
0x18000af57  mov     r9d, 4E2h; msWindowLength
0x18000af5d  mov     qword ptr [rsp+78h+pftDueTime.dwLowDateTime], 0FFFFFFFFFD050F80h
0x18000af66  xor     r8d, r8d; msPeriod
0x18000af69  lea     rdx, [rsp+78h+pftDueTime]; pftDueTime
0x18000af6e  call    cs:__imp_SetThreadpoolTimer
0x18000af75  nop     dword ptr [rax+rax+00h]
0x18000af7a  mov     byte ptr [rdi+40h], 1
0x18000af7e  test    rsi, rsi
0x18000af81  jz      short loc_18000AF92
0x18000af83  mov     rcx, rsi; SRWLock
0x18000af86  call    cs:__imp_ReleaseSRWLockExclusive
0x18000af8d  nop     dword ptr [rax+rax+00h]
0x18000af92  mov     rcx, [rsp+78h+var_40]
0x18000af97  xor     rcx, rsp; StackCookie
0x18000af9a  call    __security_check_cookie
0x18000af9f  add     rsp, 48h
0x18000afa3  pop     r15
0x18000afa5  pop     r14
0x18000afa7  pop     rdi
0x18000afa8  pop     rsi
0x18000afa9  pop     rbp
0x18000afaa  pop     rbx
0x18000afab  retn
```
