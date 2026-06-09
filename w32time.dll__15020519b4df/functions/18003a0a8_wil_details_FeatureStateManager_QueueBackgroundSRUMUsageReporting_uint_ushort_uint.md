# wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)

- ea: `0x18003a0a8`
- end: `0x18003a17d`
- name: `?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z`
- size: `213`
- prototype: `void __fastcall(PVOID pv, unsigned int, unsigned __int16, unsigned int)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x180048450`

## callees

- `0x1800345fc`
- `0x18003a0a8`
- `0x18003a258`
- `0x18003a280`
- `0x18003a2c8`
- `0x18003a2f0`
- `0x18003a320`
- `0x18003cbf8`
- `0x180048ba4`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18003a133`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18003a133`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(
        char *pv,
        int a2,
        __int16 a3,
        int a4)
{
  PTP_TIMER ThreadpoolTimer; // rax
  RTL_SRWLOCK *v9; // [rsp+20h] [rbp-48h] BYREF
  int v10; // [rsp+28h] [rbp-40h] BYREF
  __int16 v11; // [rsp+2Ch] [rbp-3Ch]
  __int16 v12; // [rsp+2Eh] [rbp-3Ah]
  int v13; // [rsp+30h] [rbp-38h]
  char v14; // [rsp+70h] [rbp+8h] BYREF

  if ( *pv && !wil::ProcessShutdownInProgress((wil *)pv) )
  {
    wil::srwlock::lock_exclusive((RTL_SRWLOCK *)pv + 5, &v9);
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
0x18003a0a8  push    rbx
0x18003a0aa  push    rbp
0x18003a0ab  push    rsi
0x18003a0ac  push    rdi
0x18003a0ad  sub     rsp, 48h
0x18003a0b1  mov     edi, r9d
0x18003a0b4  movzx   esi, r8w
0x18003a0b8  mov     ebp, edx
0x18003a0ba  mov     rbx, rcx
0x18003a0bd  cmp     byte ptr [rcx], 0
0x18003a0c0  jz      loc_18003A173
0x18003a0c6  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x18003a0cb  test    al, al
0x18003a0cd  jnz     loc_18003A173
0x18003a0d3  lea     rcx, [rbx+28h]
0x18003a0d7  lea     rdx, [rsp+68h+var_48]
0x18003a0dc  call    ?lock_exclusive@srwlock@wil@@QEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::srwlock::lock_exclusive(void)
0x18003a0e1  nop
0x18003a0e2  xor     eax, eax
0x18003a0e4  mov     [rsp+68h+var_3A], ax
0x18003a0e9  mov     [rsp+68h+var_40], ebp
0x18003a0ed  mov     [rsp+68h+var_3C], si
0x18003a0f2  mov     [rsp+68h+var_38], edi
0x18003a0f6  lea     rcx, [rbx+0E8h]; this
0x18003a0fd  lea     r8d, [rax+0Ch]; unsigned __int64
0x18003a101  lea     rdx, [rsp+68h+var_40]; void *
0x18003a106  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x18003a10b  cmp     byte ptr [rbx+40h], 0
0x18003a10f  jnz     short loc_18003A168
0x18003a111  lea     rdi, [rbx+38h]
0x18003a115  cmp     qword ptr [rdi], 0
0x18003a119  jnz     short loc_18003A155
0x18003a11b  lea     rcx, [rsp+68h+arg_0]; this
0x18003a120  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18003a125  nop
0x18003a126  xor     r8d, r8d; pcbe
0x18003a129  mov     rdx, rbx; pv
0x18003a12c  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_5035b992506f4af81a770c5842624510_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18003a133  call    cs:__imp_CreateThreadpoolTimer
0x18003a13a  nop     dword ptr [rax+rax+00h]
0x18003a13f  mov     rdx, rax
0x18003a142  mov     rcx, rdi
0x18003a145  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x18003a14a  nop
0x18003a14b  lea     rcx, [rsp+68h+arg_0]; this
0x18003a150  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18003a155  mov     r8d, 1388h
0x18003a15b  lea     rdx, [rbx+40h]
0x18003a15f  mov     rcx, rdi
0x18003a162  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x18003a167  nop
0x18003a168  lea     rcx, [rsp+68h+var_48]
0x18003a16d  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18003a172  nop
0x18003a173  add     rsp, 48h
0x18003a177  pop     rdi
0x18003a178  pop     rsi
0x18003a179  pop     rbp
0x18003a17a  pop     rbx
0x18003a17b  retn
```
