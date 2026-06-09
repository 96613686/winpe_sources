# tip2::tip_test<tip2::details::merged_data<CloudNotificationsTip::_tip_CNCreateOrUpdateSubscriptionTip,CloudNotificationsTip::_tip_CNCreateOrUpdateSubscriptionTip>>::start_and_watch_errors(void)

- ea: `0x18005fe6c`
- end: `0x18005ff63`
- name: `?start_and_watch_errors@?$tip_test@V?$merged_data@U_tip_CNCreateOrUpdateSubscriptionTip@CloudNotificationsTip@@U12@@details@tip2@@@tip2@@QEAA?AV?$test_watcher@V?$merged_data@U_tip_CNCreateOrUpdateSubscriptionTip@CloudNotificationsTip@@U12@@details@tip2@@@2@XZ`
- size: `247`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x180059840`

## callees

- `0x180009610`
- `0x18001bed0`
- `0x1800583f0`
- `0x18005eac4`
- `0x18005fe6c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005febe`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005febe`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005ff34`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005ff34`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall tip2::tip_test<tip2::details::merged_data<CloudNotificationsTip::_tip_CNCreateOrUpdateSubscriptionTip,CloudNotificationsTip::_tip_CNCreateOrUpdateSubscriptionTip>>::start_and_watch_errors(
        __int64 *a1,
        __int64 a2)
{
  __int64 v4; // rbx
  __int64 *v5; // rax
  __int64 v6; // rdx
  __int64 v7; // rcx
  _QWORD *v8; // rbx
  _QWORD *Local; // rax
  __int64 v10; // rax
  _BYTE v12[24]; // [rsp+20h] [rbp-18h] BYREF

  v4 = *a1;
  if ( *a1 && (*(_QWORD *)(v4 + 248) || (*(_DWORD *)(v4 + 72) & 0x100) != 0) )
  {
    *a1 = 0;
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v4 + 576), 0xFFFFFFFF) == 1 )
    {
      tip2::details::merged_data<CloudNotificationsTip::_tip_CNCreateOrUpdateSubscriptionTip,CloudNotificationsTip::_tip_CNCreateOrUpdateSubscriptionTip>::~merged_data<CloudNotificationsTip::_tip_CNCreateOrUpdateSubscriptionTip,CloudNotificationsTip::_tip_CNCreateOrUpdateSubscriptionTip>((struct _RTL_CRITICAL_SECTION *)v4);
      CoTaskMemFree((LPVOID)v4);
    }
  }
  v5 = tip2::tip_test<tip2::details::merged_data<CloudNotificationsTip::_tip_CNCreateOrUpdateSubscriptionTip,CloudNotificationsTip::_tip_CNCreateOrUpdateSubscriptionTip>>::ensure_data(a1);
  tip2::details::shared_data<0,0,0>::start(*v5 + 8, v12);
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
    _InterlockedIncrement((volatile signed __int32 *)(v10 + 576));
  return a2;
}

```

## disassembly

```asm
0x18005fe6c  mov     [rsp+arg_8], rbx
0x18005fe71  mov     [rsp+arg_10], rsi
0x18005fe76  push    rdi
0x18005fe77  sub     rsp, 30h
0x18005fe7b  mov     rdi, rdx
0x18005fe7e  mov     rsi, rcx
0x18005fe81  mov     rbx, [rcx]
0x18005fe84  test    rbx, rbx
0x18005fe87  jz      short loc_18005FEC4
0x18005fe89  cmp     qword ptr [rbx+0F8h], 0
0x18005fe91  jnz     short loc_18005FE9C
0x18005fe93  test    dword ptr [rbx+48h], 100h
0x18005fe9a  jz      short loc_18005FEC4
0x18005fe9c  mov     qword ptr [rcx], 0
0x18005fea3  or      eax, 0FFFFFFFFh
0x18005fea6  lock xadd [rbx+240h], eax
0x18005feae  cmp     eax, 1
0x18005feb1  jnz     short loc_18005FEC4
0x18005feb3  mov     rcx, rbx
0x18005feb6  call    ??1?$merged_data@U_tip_CNCreateOrUpdateSubscriptionTip@CloudNotificationsTip@@U12@@details@tip2@@QEAA@XZ; tip2::details::merged_data<CloudNotificationsTip::_tip_CNCreateOrUpdateSubscriptionTip,CloudNotificationsTip::_tip_CNCreateOrUpdateSubscriptionTip>::~merged_data<CloudNotificationsTip::_tip_CNCreateOrUpdateSubscriptionTip,CloudNotificationsTip::_tip_CNCreateOrUpdateSubscriptionTip>(void)
0x18005febb  mov     rcx, rbx; pv
0x18005febe  call    cs:__imp_CoTaskMemFree
0x18005fec4  mov     rcx, rsi
0x18005fec7  call    ?ensure_data@?$tip_test@V?$merged_data@U_tip_CNCreateOrUpdateSubscriptionTip@CloudNotificationsTip@@U12@@details@tip2@@@tip2@@AEBAAEAV?$com_ptr_t@V?$merged_data@U_tip_CNCreateOrUpdateSubscriptionTip@CloudNotificationsTip@@U12@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ; tip2::tip_test<tip2::details::merged_data<CloudNotificationsTip::_tip_CNCreateOrUpdateSubscriptionTip,CloudNotificationsTip::_tip_CNCreateOrUpdateSubscriptionTip>>::ensure_data(void)
0x18005fecc  mov     rcx, [rax]
0x18005fecf  add     rcx, 8
0x18005fed3  lea     rdx, [rsp+38h+var_18]
0x18005fed8  call    ?start@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAA?AU_GUID@@XZ; tip2::details::shared_data<0,0,0>::start(void)
0x18005fedd  lea     rax, ??_7?$test_watcher@V?$merged_data@U_tip_CNRegisterWnpEndpointTip@CloudNotificationsTip@@U12@@details@tip2@@@tip2@@6B@; const tip2::test_watcher<tip2::details::merged_data<CloudNotificationsTip::_tip_CNRegisterWnpEndpointTip,CloudNotificationsTip::_tip_CNRegisterWnpEndpointTip>>::`vftable'
0x18005fee4  mov     [rdi], rax
0x18005fee7  lea     rbx, [rdi+8]
0x18005feeb  mov     qword ptr [rbx], 0
0x18005fef2  mov     [rbx+8], rdi
0x18005fef6  mov     qword ptr [rbx+10h], 0
0x18005fefe  mov     dword ptr [rbx+18h], 0
0x18005ff05  mov     qword ptr [rbx+20h], 0
0x18005ff0d  mov     byte ptr [rbx+28h], 0
0x18005ff11  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, 0; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x18005ff19  jz      short loc_18005FF3D
0x18005ff1b  mov     dl, 1
0x18005ff1d  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x18005ff22  mov     [rbx], rax
0x18005ff25  test    rax, rax
0x18005ff28  jz      short loc_18005FF3D
0x18005ff2a  mov     rcx, [rax]
0x18005ff2d  mov     [rbx+10h], rcx
0x18005ff31  mov     [rax], rbx
0x18005ff34  call    cs:__imp_GetCurrentThreadId
0x18005ff3a  mov     [rbx+18h], eax
0x18005ff3d  mov     rax, [rsi]
0x18005ff40  mov     [rdi+38h], rax
0x18005ff44  test    rax, rax
0x18005ff47  jz      short loc_18005FF50
0x18005ff49  lock inc dword ptr [rax+240h]
0x18005ff50  mov     rax, rdi
0x18005ff53  mov     rbx, [rsp+38h+arg_8]
0x18005ff58  mov     rsi, [rsp+38h+arg_10]
0x18005ff5d  add     rsp, 30h
0x18005ff61  pop     rdi
0x18005ff62  retn
```
