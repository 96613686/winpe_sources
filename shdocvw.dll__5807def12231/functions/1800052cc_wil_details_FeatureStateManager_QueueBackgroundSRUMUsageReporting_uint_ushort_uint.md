# wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)

- ea: `0x1800052cc`
- end: `0x1800053ae`
- name: `?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z`
- size: `226`
- prototype: `void __fastcall(PVOID pv, unsigned int, unsigned __int16, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x1800108b0`

## callees

- `0x180003b30`
- `0x180003c60`
- `0x1800042f0`
- `0x1800052cc`
- `0x180005540`
- `0x180005560`
- `0x180005590`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180005308`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180005308`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180005394`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180005394`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000535f`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000535f`

## pseudocode

```c
void __fastcall wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(
        char *pv,
        int a2,
        __int16 a3,
        int a4)
{
  PTP_TIMER ThreadpoolTimer; // rax
  int v9; // [rsp+20h] [rbp-28h] BYREF
  __int16 v10; // [rsp+24h] [rbp-24h]
  __int16 v11; // [rsp+26h] [rbp-22h]
  int v12; // [rsp+28h] [rbp-20h]
  char v13; // [rsp+50h] [rbp+8h] BYREF

  if ( *pv && !wil::ProcessShutdownInProgress((wil *)pv) )
  {
    AcquireSRWLockExclusive((PSRWLOCK)pv + 5);
    v11 = 0;
    v9 = a2;
    v10 = a3;
    v12 = a4;
    wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)(pv + 232), &v9, 0xCu);
    if ( !pv[64] )
    {
      if ( !*((_QWORD *)pv + 7) )
      {
        wil::last_error_context::last_error_context((wil::last_error_context *)&v13);
        ThreadpoolTimer = CreateThreadpoolTimer(
                            _lambda_5035b992506f4af81a770c5842624510_::_lambda_invoker_cdecl_,
                            pv,
                            0);
        wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
          pv + 56,
          ThreadpoolTimer);
        wil::last_error_context::~last_error_context((wil::last_error_context *)&v13);
      }
      wil::details::EnsureCoalescedTimer_SetTimer((struct _TP_TIMER **)pv + 7, pv + 64, 5000);
    }
    if ( pv != (char *)-40LL )
      ReleaseSRWLockExclusive((PSRWLOCK)pv + 5);
  }
}

```

## disassembly

```asm
0x1800052cc  mov     [rsp+arg_8], rbx
0x1800052d1  mov     [rsp+arg_10], rbp
0x1800052d6  push    rsi
0x1800052d7  push    rdi
0x1800052d8  push    r14
0x1800052da  sub     rsp, 30h
0x1800052de  mov     edi, r9d
0x1800052e1  movzx   ebp, r8w
0x1800052e5  mov     r14d, edx
0x1800052e8  mov     rbx, rcx
0x1800052eb  cmp     byte ptr [rcx], 0
0x1800052ee  jz      loc_18000539B
0x1800052f4  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x1800052f9  test    al, al
0x1800052fb  jnz     loc_18000539B
0x180005301  lea     rsi, [rbx+28h]
0x180005305  mov     rcx, rsi; SRWLock
0x180005308  call    cs:__imp_AcquireSRWLockExclusive
0x18000530e  xor     eax, eax
0x180005310  mov     [rsp+48h+var_22], ax
0x180005315  mov     [rsp+48h+var_28], r14d
0x18000531a  mov     [rsp+48h+var_24], bp
0x18000531f  mov     [rsp+48h+var_20], edi
0x180005323  lea     rcx, [rbx+0E8h]; this
0x18000532a  lea     r8d, [rax+0Ch]; unsigned __int64
0x18000532e  lea     rdx, [rsp+48h+var_28]; void *
0x180005333  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x180005338  cmp     byte ptr [rbx+40h], 0
0x18000533c  jnz     short loc_18000538C
0x18000533e  lea     rdi, [rbx+38h]
0x180005342  cmp     qword ptr [rdi], 0
0x180005346  jnz     short loc_18000537A
0x180005348  lea     rcx, [rsp+48h+arg_0]; this
0x18000534d  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180005352  xor     r8d, r8d; pcbe
0x180005355  mov     rdx, rbx; pv
0x180005358  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_5035b992506f4af81a770c5842624510_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18000535f  call    cs:__imp_CreateThreadpoolTimer
0x180005365  mov     rdx, rax
0x180005368  mov     rcx, rdi
0x18000536b  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x180005370  lea     rcx, [rsp+48h+arg_0]; this
0x180005375  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18000537a  mov     r8d, 1388h
0x180005380  lea     rdx, [rbx+40h]
0x180005384  mov     rcx, rdi
0x180005387  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x18000538c  test    rsi, rsi
0x18000538f  jz      short loc_18000539B
0x180005391  mov     rcx, rsi; SRWLock
0x180005394  call    cs:__imp_ReleaseSRWLockExclusive
0x18000539a  nop
0x18000539b  mov     rbx, [rsp+48h+arg_8]
0x1800053a0  mov     rbp, [rsp+48h+arg_10]
0x1800053a5  add     rsp, 30h
0x1800053a9  pop     r14
0x1800053ab  pop     rdi
0x1800053ac  pop     rsi
0x1800053ad  retn
```
