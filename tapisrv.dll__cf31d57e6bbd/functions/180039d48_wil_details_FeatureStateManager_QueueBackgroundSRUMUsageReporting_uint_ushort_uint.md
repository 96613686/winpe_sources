# wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)

- ea: `0x180039d48`
- end: `0x180039e2a`
- name: `?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z`
- size: `226`
- prototype: `void __fastcall(char *pv, int, __int16, int)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18003c030`

## callees

- `0x18003601c`
- `0x180036294`
- `0x180036580`
- `0x180037ac4`
- `0x180039d14`
- `0x180039d48`
- `0x18003c60c`
- `0x18003c714`

## import_xrefs

- `KERNEL32!CreateThreadpoolTimer` at `0x180039de0`
- `KERNEL32!CreateThreadpoolTimer` at `0x180039de0`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180039d84`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180039d84`

## pseudocode

```c
void __fastcall wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(
        char *pv,
        int a2,
        __int16 a3,
        int a4)
{
  PTP_TIMER ThreadpoolTimer; // rax
  RTL_SRWLOCK *v9; // [rsp+20h] [rbp-38h] BYREF
  int v10; // [rsp+28h] [rbp-30h] BYREF
  __int16 v11; // [rsp+2Ch] [rbp-2Ch]
  __int16 v12; // [rsp+2Eh] [rbp-2Ah]
  int v13; // [rsp+30h] [rbp-28h]
  char v14; // [rsp+60h] [rbp+8h] BYREF

  if ( *pv && !wil::ProcessShutdownInProgress((wil *)pv) )
  {
    AcquireSRWLockExclusive((PSRWLOCK)pv + 5);
    v9 = (RTL_SRWLOCK *)(pv + 40);
    v12 = 0;
    v10 = a2;
    v11 = a3;
    v13 = a4;
    wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)(pv + 232), &v10, 0xCu);
    if ( !pv[64] )
    {
      if ( !*((_QWORD *)pv + 7) )
      {
        wil::last_error_context::last_error_context((wil::last_error_context *)&v14);
        ThreadpoolTimer = CreateThreadpoolTimer(
                            _lambda_5035b992506f4af81a770c5842624510_::_lambda_invoker_cdecl_,
                            pv,
                            0);
        wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
          pv + 56,
          ThreadpoolTimer);
        wil::last_error_context::~last_error_context((wil::last_error_context *)&v14);
      }
      wil::details::EnsureCoalescedTimer_SetTimer((struct _TP_TIMER **)pv + 7, pv + 64, 5000);
    }
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v9);
  }
}

```

## disassembly

```asm
0x180039d48  mov     [rsp+arg_8], rbx
0x180039d4d  mov     [rsp+arg_10], rbp
0x180039d52  push    rsi
0x180039d53  push    rdi
0x180039d54  push    r14
0x180039d56  sub     rsp, 40h
0x180039d5a  cmp     byte ptr [rcx], 0
0x180039d5d  mov     esi, r9d
0x180039d60  movzx   ebp, r8w
0x180039d64  mov     r14d, edx
0x180039d67  mov     rdi, rcx
0x180039d6a  jz      loc_180039E17
0x180039d70  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x180039d75  test    al, al
0x180039d77  jnz     loc_180039E17
0x180039d7d  lea     rbx, [rdi+28h]
0x180039d81  mov     rcx, rbx; SRWLock
0x180039d84  call    cs:__imp_AcquireSRWLockExclusive
0x180039d8a  xor     eax, eax
0x180039d8c  mov     [rsp+58h+var_38], rbx
0x180039d91  lea     rcx, [rdi+0E8h]; this
0x180039d98  mov     [rsp+58h+var_2A], ax
0x180039d9d  lea     rdx, [rsp+58h+var_30]; void *
0x180039da2  mov     [rsp+58h+var_30], r14d
0x180039da7  mov     [rsp+58h+var_2C], bp
0x180039dac  lea     r8d, [rax+0Ch]; unsigned __int64
0x180039db0  mov     [rsp+58h+var_28], esi
0x180039db4  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x180039db9  cmp     byte ptr [rdi+40h], 0
0x180039dbd  jnz     short loc_180039E0D
0x180039dbf  lea     rbx, [rdi+38h]
0x180039dc3  cmp     qword ptr [rbx], 0
0x180039dc7  jnz     short loc_180039DFB
0x180039dc9  lea     rcx, [rsp+58h+arg_0]; this
0x180039dce  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180039dd3  xor     r8d, r8d; pcbe
0x180039dd6  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_5035b992506f4af81a770c5842624510_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180039ddd  mov     rdx, rdi; pv
0x180039de0  call    cs:__imp_CreateThreadpoolTimer
0x180039de6  mov     rdx, rax
0x180039de9  mov     rcx, rbx
0x180039dec  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x180039df1  lea     rcx, [rsp+58h+arg_0]; this
0x180039df6  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180039dfb  mov     r8d, 1388h
0x180039e01  lea     rdx, [rdi+40h]
0x180039e05  mov     rcx, rbx
0x180039e08  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x180039e0d  lea     rcx, [rsp+58h+var_38]
0x180039e12  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180039e17  mov     rbx, [rsp+58h+arg_8]
0x180039e1c  mov     rbp, [rsp+58h+arg_10]
0x180039e21  add     rsp, 40h
0x180039e25  pop     r14
0x180039e27  pop     rdi
0x180039e28  pop     rsi
0x180039e29  retn
```
