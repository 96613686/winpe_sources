# tip2::tip_test<tip2::details::merged_data<AfsTip::_tip_AFSSendSubscriptionRequestAsyncTip,AfsTip::_tip_AFSSendSubscriptionRequestAsyncTip>>::start_and_watch_errors(void)

- ea: `0x18006cad0`
- end: `0x18006cbc7`
- name: `?start_and_watch_errors@?$tip_test@V?$merged_data@U_tip_AFSSendSubscriptionRequestAsyncTip@AfsTip@@U12@@details@tip2@@@tip2@@QEAA?AV?$test_watcher@V?$merged_data@U_tip_AFSSendSubscriptionRequestAsyncTip@AfsTip@@U12@@details@tip2@@@2@XZ`
- size: `247`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x18006a080`

## callees

- `0x180009610`
- `0x18001bed0`
- `0x180069484`
- `0x18006c260`
- `0x18006cad0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006cb22`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006cb22`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18006cb98`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18006cb98`

## pseudocode

```c
__int64 __fastcall tip2::tip_test<tip2::details::merged_data<AfsTip::_tip_AFSSendSubscriptionRequestAsyncTip,AfsTip::_tip_AFSSendSubscriptionRequestAsyncTip>>::start_and_watch_errors(
        volatile signed __int32 **a1,
        __int64 a2)
{
  volatile signed __int32 *v4; // rbx
  volatile signed __int32 **v5; // rax
  __int64 v6; // rdx
  __int64 v7; // rcx
  _QWORD *v8; // rbx
  _QWORD *Local; // rax
  volatile signed __int32 *v10; // rax
  _BYTE v12[24]; // [rsp+20h] [rbp-18h] BYREF

  v4 = *a1;
  if ( *a1 && (*((_QWORD *)v4 + 31) || (v4[18] & 0x100) != 0) )
  {
    *a1 = 0;
    if ( _InterlockedExchangeAdd(v4 + 128, 0xFFFFFFFF) == 1 )
    {
      tip2::details::merged_data<AfsTip::_tip_AFSSendSubscriptionRequestAsyncTip,AfsTip::_tip_AFSSendSubscriptionRequestAsyncTip>::~merged_data<AfsTip::_tip_AFSSendSubscriptionRequestAsyncTip,AfsTip::_tip_AFSSendSubscriptionRequestAsyncTip>((struct _RTL_CRITICAL_SECTION *)v4);
      CoTaskMemFree((LPVOID)v4);
    }
  }
  v5 = tip2::tip_test<tip2::details::merged_data<AfsTip::_tip_AFSSendSubscriptionRequestAsyncTip,AfsTip::_tip_AFSSendSubscriptionRequestAsyncTip>>::ensure_data(a1);
  tip2::details::shared_data<0,0,0>::start(*v5 + 2, v12);
  *(_QWORD *)a2 = &tip2::test_watcher<tip2::details::merged_data<CloudNotificationsTip::_tip_CNRegisterWnpEndpointTip,CloudNotificationsTip::_tip_CNRegisterWnpEndpointTip>>::`vftable';
  v8 = (_QWORD *)(a2 + 8);
  *(_QWORD *)(a2 + 8) = 0;
  *(_QWORD *)(a2 + 16) = a2;
  *(_QWORD *)(a2 + 24) = 0;
  *(_DWORD *)(a2 + 32) = 0;
  *(_QWORD *)(a2 + 40) = 0;
  *(_BYTE *)(a2 + 48) = 0;
  if ( wil::details::g_pThreadFailureCallbacks )
  {
    LOBYTE(v6) = 1;
    Local = (_QWORD *)wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(
                        v7,
                        v6);
    *v8 = Local;
    if ( Local )
    {
      *(_QWORD *)(a2 + 24) = *Local;
      *Local = v8;
      *(_DWORD *)(a2 + 32) = GetCurrentThreadId();
    }
  }
  v10 = *a1;
  *(_QWORD *)(a2 + 56) = *a1;
  if ( v10 )
    _InterlockedIncrement(v10 + 128);
  return a2;
}

```

## disassembly

```asm
0x18006cad0  mov     [rsp+arg_8], rbx
0x18006cad5  mov     [rsp+arg_10], rsi
0x18006cada  push    rdi
0x18006cadb  sub     rsp, 30h
0x18006cadf  mov     rdi, rdx
0x18006cae2  mov     rsi, rcx
0x18006cae5  mov     rbx, [rcx]
0x18006cae8  test    rbx, rbx
0x18006caeb  jz      short loc_18006CB28
0x18006caed  cmp     qword ptr [rbx+0F8h], 0
0x18006caf5  jnz     short loc_18006CB00
0x18006caf7  test    dword ptr [rbx+48h], 100h
0x18006cafe  jz      short loc_18006CB28
0x18006cb00  mov     qword ptr [rcx], 0
0x18006cb07  or      eax, 0FFFFFFFFh
0x18006cb0a  lock xadd [rbx+200h], eax
0x18006cb12  cmp     eax, 1
0x18006cb15  jnz     short loc_18006CB28
0x18006cb17  mov     rcx, rbx
0x18006cb1a  call    ??1?$merged_data@U_tip_AFSSendSubscriptionRequestAsyncTip@AfsTip@@U12@@details@tip2@@QEAA@XZ; tip2::details::merged_data<AfsTip::_tip_AFSSendSubscriptionRequestAsyncTip,AfsTip::_tip_AFSSendSubscriptionRequestAsyncTip>::~merged_data<AfsTip::_tip_AFSSendSubscriptionRequestAsyncTip,AfsTip::_tip_AFSSendSubscriptionRequestAsyncTip>(void)
0x18006cb1f  mov     rcx, rbx; pv
0x18006cb22  call    cs:__imp_CoTaskMemFree
0x18006cb28  mov     rcx, rsi
0x18006cb2b  call    ?ensure_data@?$tip_test@V?$merged_data@U_tip_AFSSendSubscriptionRequestAsyncTip@AfsTip@@U12@@details@tip2@@@tip2@@AEBAAEAV?$com_ptr_t@V?$merged_data@U_tip_AFSSendSubscriptionRequestAsyncTip@AfsTip@@U12@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ; tip2::tip_test<tip2::details::merged_data<AfsTip::_tip_AFSSendSubscriptionRequestAsyncTip,AfsTip::_tip_AFSSendSubscriptionRequestAsyncTip>>::ensure_data(void)
0x18006cb30  mov     rcx, [rax]
0x18006cb33  add     rcx, 8
0x18006cb37  lea     rdx, [rsp+38h+var_18]
0x18006cb3c  call    ?start@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAA?AU_GUID@@XZ; tip2::details::shared_data<0,0,0>::start(void)
0x18006cb41  lea     rax, ??_7?$test_watcher@V?$merged_data@U_tip_CNRegisterWnpEndpointTip@CloudNotificationsTip@@U12@@details@tip2@@@tip2@@6B@; const tip2::test_watcher<tip2::details::merged_data<CloudNotificationsTip::_tip_CNRegisterWnpEndpointTip,CloudNotificationsTip::_tip_CNRegisterWnpEndpointTip>>::`vftable'
0x18006cb48  mov     [rdi], rax
0x18006cb4b  lea     rbx, [rdi+8]
0x18006cb4f  mov     qword ptr [rbx], 0
0x18006cb56  mov     [rbx+8], rdi
0x18006cb5a  mov     qword ptr [rbx+10h], 0
0x18006cb62  mov     dword ptr [rbx+18h], 0
0x18006cb69  mov     qword ptr [rbx+20h], 0
0x18006cb71  mov     byte ptr [rbx+28h], 0
0x18006cb75  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, 0; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x18006cb7d  jz      short loc_18006CBA1
0x18006cb7f  mov     dl, 1
0x18006cb81  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x18006cb86  mov     [rbx], rax
0x18006cb89  test    rax, rax
0x18006cb8c  jz      short loc_18006CBA1
0x18006cb8e  mov     rcx, [rax]
0x18006cb91  mov     [rbx+10h], rcx
0x18006cb95  mov     [rax], rbx
0x18006cb98  call    cs:__imp_GetCurrentThreadId
0x18006cb9e  mov     [rbx+18h], eax
0x18006cba1  mov     rax, [rsi]
0x18006cba4  mov     [rdi+38h], rax
0x18006cba8  test    rax, rax
0x18006cbab  jz      short loc_18006CBB4
0x18006cbad  lock inc dword ptr [rax+200h]
0x18006cbb4  mov     rax, rdi
0x18006cbb7  mov     rbx, [rsp+38h+arg_8]
0x18006cbbc  mov     rsi, [rsp+38h+arg_10]
0x18006cbc1  add     rsp, 30h
0x18006cbc5  pop     rdi
0x18006cbc6  retn
```
