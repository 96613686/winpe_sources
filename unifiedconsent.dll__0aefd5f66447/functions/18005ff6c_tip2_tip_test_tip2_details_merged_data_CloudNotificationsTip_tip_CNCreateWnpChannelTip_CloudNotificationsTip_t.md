# tip2::tip_test<tip2::details::merged_data<CloudNotificationsTip::_tip_CNCreateWnpChannelTip,CloudNotificationsTip::_tip_CNCreateWnpChannelTip>>::start_and_watch_errors(void)

- ea: `0x18005ff6c`
- end: `0x180060063`
- name: `?start_and_watch_errors@?$tip_test@V?$merged_data@U_tip_CNCreateWnpChannelTip@CloudNotificationsTip@@U12@@details@tip2@@@tip2@@QEAA?AV?$test_watcher@V?$merged_data@U_tip_CNCreateWnpChannelTip@CloudNotificationsTip@@U12@@details@tip2@@@2@XZ`
- size: `247`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x18005ba20`

## callees

- `0x180009610`
- `0x18001bed0`
- `0x180058488`
- `0x18005eb58`
- `0x18005ff6c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005ffbe`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005ffbe`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180060034`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180060034`

## pseudocode

```c
__int64 __fastcall tip2::tip_test<tip2::details::merged_data<CloudNotificationsTip::_tip_CNCreateWnpChannelTip,CloudNotificationsTip::_tip_CNCreateWnpChannelTip>>::start_and_watch_errors(
        struct _RTL_CRITICAL_SECTION **a1,
        __int64 a2)
{
  struct _RTL_CRITICAL_SECTION *v4; // rbx
  struct _RTL_CRITICAL_SECTION **v5; // rax
  __int64 v6; // rdx
  __int64 v7; // rcx
  _QWORD *v8; // rbx
  _QWORD *Local; // rax
  struct _RTL_CRITICAL_SECTION *v10; // rax
  _BYTE v12[24]; // [rsp+20h] [rbp-18h] BYREF

  v4 = *a1;
  if ( *a1 && (*(_QWORD *)&v4[6].LockCount || (v4[1].SpinCount & 0x100) != 0) )
  {
    *a1 = 0;
    if ( _InterlockedExchangeAdd(&v4[10].LockCount, 0xFFFFFFFF) == 1 )
    {
      tip2::details::merged_data<CloudNotificationsTip::_tip_CNCreateWnpChannelTip,CloudNotificationsTip::_tip_CNCreateWnpChannelTip>::~merged_data<CloudNotificationsTip::_tip_CNCreateWnpChannelTip,CloudNotificationsTip::_tip_CNCreateWnpChannelTip>(v4);
      CoTaskMemFree(v4);
    }
  }
  v5 = tip2::tip_test<tip2::details::merged_data<CloudNotificationsTip::_tip_CNCreateWnpChannelTip,CloudNotificationsTip::_tip_CNCreateWnpChannelTip>>::ensure_data(a1);
  tip2::details::shared_data<0,0,0>::start(&(*v5)->LockCount, v12);
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
    _InterlockedIncrement(&v10[10].LockCount);
  return a2;
}

```

## disassembly

```asm
0x18005ff6c  mov     [rsp+arg_8], rbx
0x18005ff71  mov     [rsp+arg_10], rsi
0x18005ff76  push    rdi
0x18005ff77  sub     rsp, 30h
0x18005ff7b  mov     rdi, rdx
0x18005ff7e  mov     rsi, rcx
0x18005ff81  mov     rbx, [rcx]
0x18005ff84  test    rbx, rbx
0x18005ff87  jz      short loc_18005FFC4
0x18005ff89  cmp     qword ptr [rbx+0F8h], 0
0x18005ff91  jnz     short loc_18005FF9C
0x18005ff93  test    dword ptr [rbx+48h], 100h
0x18005ff9a  jz      short loc_18005FFC4
0x18005ff9c  mov     qword ptr [rcx], 0
0x18005ffa3  or      eax, 0FFFFFFFFh
0x18005ffa6  lock xadd [rbx+198h], eax
0x18005ffae  cmp     eax, 1
0x18005ffb1  jnz     short loc_18005FFC4
0x18005ffb3  mov     rcx, rbx
0x18005ffb6  call    ??1?$merged_data@U_tip_CNCreateWnpChannelTip@CloudNotificationsTip@@U12@@details@tip2@@QEAA@XZ; tip2::details::merged_data<CloudNotificationsTip::_tip_CNCreateWnpChannelTip,CloudNotificationsTip::_tip_CNCreateWnpChannelTip>::~merged_data<CloudNotificationsTip::_tip_CNCreateWnpChannelTip,CloudNotificationsTip::_tip_CNCreateWnpChannelTip>(void)
0x18005ffbb  mov     rcx, rbx; pv
0x18005ffbe  call    cs:__imp_CoTaskMemFree
0x18005ffc4  mov     rcx, rsi
0x18005ffc7  call    ?ensure_data@?$tip_test@V?$merged_data@U_tip_CNCreateWnpChannelTip@CloudNotificationsTip@@U12@@details@tip2@@@tip2@@AEBAAEAV?$com_ptr_t@V?$merged_data@U_tip_CNCreateWnpChannelTip@CloudNotificationsTip@@U12@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ; tip2::tip_test<tip2::details::merged_data<CloudNotificationsTip::_tip_CNCreateWnpChannelTip,CloudNotificationsTip::_tip_CNCreateWnpChannelTip>>::ensure_data(void)
0x18005ffcc  mov     rcx, [rax]
0x18005ffcf  add     rcx, 8
0x18005ffd3  lea     rdx, [rsp+38h+var_18]
0x18005ffd8  call    ?start@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAA?AU_GUID@@XZ; tip2::details::shared_data<0,0,0>::start(void)
0x18005ffdd  lea     rax, ??_7?$test_watcher@V?$merged_data@U_tip_CNRegisterWnpEndpointTip@CloudNotificationsTip@@U12@@details@tip2@@@tip2@@6B@; const tip2::test_watcher<tip2::details::merged_data<CloudNotificationsTip::_tip_CNRegisterWnpEndpointTip,CloudNotificationsTip::_tip_CNRegisterWnpEndpointTip>>::`vftable'
0x18005ffe4  mov     [rdi], rax
0x18005ffe7  lea     rbx, [rdi+8]
0x18005ffeb  mov     qword ptr [rbx], 0
0x18005fff2  mov     [rbx+8], rdi
0x18005fff6  mov     qword ptr [rbx+10h], 0
0x18005fffe  mov     dword ptr [rbx+18h], 0
0x180060005  mov     qword ptr [rbx+20h], 0
0x18006000d  mov     byte ptr [rbx+28h], 0
0x180060011  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, 0; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180060019  jz      short loc_18006003D
0x18006001b  mov     dl, 1
0x18006001d  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x180060022  mov     [rbx], rax
0x180060025  test    rax, rax
0x180060028  jz      short loc_18006003D
0x18006002a  mov     rcx, [rax]
0x18006002d  mov     [rbx+10h], rcx
0x180060031  mov     [rax], rbx
0x180060034  call    cs:__imp_GetCurrentThreadId
0x18006003a  mov     [rbx+18h], eax
0x18006003d  mov     rax, [rsi]
0x180060040  mov     [rdi+38h], rax
0x180060044  test    rax, rax
0x180060047  jz      short loc_180060050
0x180060049  lock inc dword ptr [rax+198h]
0x180060050  mov     rax, rdi
0x180060053  mov     rbx, [rsp+38h+arg_8]
0x180060058  mov     rsi, [rsp+38h+arg_10]
0x18006005d  add     rsp, 30h
0x180060061  pop     rdi
0x180060062  retn
```
