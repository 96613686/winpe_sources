# wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)

- ea: `0x180026804`
- end: `0x1800268e7`
- name: `?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z`
- size: `227`
- prototype: `void __fastcall(PVOID pv, unsigned int, unsigned __int16, unsigned int)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180028190`

## callees

- `0x1800220dc`
- `0x1800223fc`
- `0x180023b9c`
- `0x180025784`
- `0x180025cd4`
- `0x180026804`
- `0x1800284a0`
- `0x1800285ac`

## import_xrefs

- `KERNEL32!AcquireSRWLockExclusive` at `0x180026840`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180026840`
- `KERNEL32!CreateThreadpoolTimer` at `0x18002689c`
- `KERNEL32!CreateThreadpoolTimer` at `0x18002689c`

## pseudocode

```c
void __fastcall wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(
        char *pv,
        int a2,
        __int16 a3,
        int a4)
{
  PTP_TIMER ThreadpoolTimer; // rax
  char *v9; // [rsp+20h] [rbp-38h] BYREF
  int v10; // [rsp+28h] [rbp-30h] BYREF
  __int16 v11; // [rsp+2Ch] [rbp-2Ch]
  __int16 v12; // [rsp+2Eh] [rbp-2Ah]
  int v13; // [rsp+30h] [rbp-28h]
  char v14; // [rsp+60h] [rbp+8h] BYREF

  if ( *pv && !wil::ProcessShutdownInProgress((wil *)pv) )
  {
    AcquireSRWLockExclusive((PSRWLOCK)pv + 5);
    v9 = pv + 40;
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
0x180026804  mov     [rsp+arg_8], rbx
0x180026809  mov     [rsp+arg_10], rbp
0x18002680e  push    rsi
0x18002680f  push    rdi
0x180026810  push    r14
0x180026812  sub     rsp, 40h
0x180026816  mov     esi, r9d
0x180026819  movzx   ebp, r8w
0x18002681d  mov     r14d, edx
0x180026820  mov     rdi, rcx
0x180026823  cmp     byte ptr [rcx], 0
0x180026826  jz      loc_1800268D4
0x18002682c  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x180026831  test    al, al
0x180026833  jnz     loc_1800268D4
0x180026839  lea     rbx, [rdi+28h]
0x18002683d  mov     rcx, rbx; SRWLock
0x180026840  call    cs:__imp_AcquireSRWLockExclusive
0x180026846  mov     [rsp+58h+var_38], rbx
0x18002684b  xor     eax, eax
0x18002684d  mov     [rsp+58h+var_2A], ax
0x180026852  mov     [rsp+58h+var_30], r14d
0x180026857  mov     [rsp+58h+var_2C], bp
0x18002685c  mov     [rsp+58h+var_28], esi
0x180026860  lea     rcx, [rdi+0E8h]; this
0x180026867  lea     r8d, [rax+0Ch]; unsigned __int64
0x18002686b  lea     rdx, [rsp+58h+var_30]; void *
0x180026870  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x180026875  cmp     byte ptr [rdi+40h], 0
0x180026879  jnz     short loc_1800268C9
0x18002687b  lea     rbx, [rdi+38h]
0x18002687f  cmp     qword ptr [rbx], 0
0x180026883  jnz     short loc_1800268B7
0x180026885  lea     rcx, [rsp+58h+arg_0]; this
0x18002688a  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18002688f  xor     r8d, r8d; pcbe
0x180026892  mov     rdx, rdi; pv
0x180026895  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_5035b992506f4af81a770c5842624510_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18002689c  call    cs:__imp_CreateThreadpoolTimer
0x1800268a2  mov     rdx, rax
0x1800268a5  mov     rcx, rbx
0x1800268a8  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x1800268ad  lea     rcx, [rsp+58h+arg_0]; this
0x1800268b2  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x1800268b7  mov     r8d, 1388h
0x1800268bd  lea     rdx, [rdi+40h]
0x1800268c1  mov     rcx, rbx
0x1800268c4  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x1800268c9  lea     rcx, [rsp+58h+var_38]
0x1800268ce  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x1800268d3  nop
0x1800268d4  mov     rbx, [rsp+58h+arg_8]
0x1800268d9  mov     rbp, [rsp+58h+arg_10]
0x1800268de  add     rsp, 40h
0x1800268e2  pop     r14
0x1800268e4  pop     rdi
0x1800268e5  pop     rsi
0x1800268e6  retn
```
