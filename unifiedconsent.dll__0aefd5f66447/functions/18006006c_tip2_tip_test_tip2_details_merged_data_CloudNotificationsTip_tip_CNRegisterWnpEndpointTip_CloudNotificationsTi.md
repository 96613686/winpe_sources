# tip2::tip_test<tip2::details::merged_data<CloudNotificationsTip::_tip_CNRegisterWnpEndpointTip,CloudNotificationsTip::_tip_CNRegisterWnpEndpointTip>>::start_and_watch_errors(void)

- ea: `0x18006006c`
- end: `0x180060163`
- name: `?start_and_watch_errors@?$tip_test@V?$merged_data@U_tip_CNRegisterWnpEndpointTip@CloudNotificationsTip@@U12@@details@tip2@@@tip2@@QEAA?AV?$test_watcher@V?$merged_data@U_tip_CNRegisterWnpEndpointTip@CloudNotificationsTip@@U12@@details@tip2@@@2@XZ`
- size: `247`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x18005d2e8`

## callees

- `0x180009610`
- `0x18001bed0`
- `0x180058544`
- `0x18005ebec`
- `0x18006006c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800600be`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800600be`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180060134`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180060134`

## pseudocode

```c
__int64 __fastcall tip2::tip_test<tip2::details::merged_data<CloudNotificationsTip::_tip_CNRegisterWnpEndpointTip,CloudNotificationsTip::_tip_CNRegisterWnpEndpointTip>>::start_and_watch_errors(
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
    if ( _InterlockedExchangeAdd(v4 + 96, 0xFFFFFFFF) == 1 )
    {
      tip2::details::merged_data<CloudNotificationsTip::_tip_CNRegisterWnpEndpointTip,CloudNotificationsTip::_tip_CNRegisterWnpEndpointTip>::~merged_data<CloudNotificationsTip::_tip_CNRegisterWnpEndpointTip,CloudNotificationsTip::_tip_CNRegisterWnpEndpointTip>((struct _RTL_CRITICAL_SECTION *)v4);
      CoTaskMemFree((LPVOID)v4);
    }
  }
  v5 = tip2::tip_test<tip2::details::merged_data<CloudNotificationsTip::_tip_CNRegisterWnpEndpointTip,CloudNotificationsTip::_tip_CNRegisterWnpEndpointTip>>::ensure_data(a1);
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
    _InterlockedIncrement(v10 + 96);
  return a2;
}

```

## disassembly

```asm
0x18006006c  mov     [rsp+arg_8], rbx
0x180060071  mov     [rsp+arg_10], rsi
0x180060076  push    rdi
0x180060077  sub     rsp, 30h
0x18006007b  mov     rdi, rdx
0x18006007e  mov     rsi, rcx
0x180060081  mov     rbx, [rcx]
0x180060084  test    rbx, rbx
0x180060087  jz      short loc_1800600C4
0x180060089  cmp     qword ptr [rbx+0F8h], 0
0x180060091  jnz     short loc_18006009C
0x180060093  test    dword ptr [rbx+48h], 100h
0x18006009a  jz      short loc_1800600C4
0x18006009c  mov     qword ptr [rcx], 0
0x1800600a3  or      eax, 0FFFFFFFFh
0x1800600a6  lock xadd [rbx+180h], eax
0x1800600ae  cmp     eax, 1
0x1800600b1  jnz     short loc_1800600C4
0x1800600b3  mov     rcx, rbx
0x1800600b6  call    ??1?$merged_data@U_tip_CNRegisterWnpEndpointTip@CloudNotificationsTip@@U12@@details@tip2@@QEAA@XZ; tip2::details::merged_data<CloudNotificationsTip::_tip_CNRegisterWnpEndpointTip,CloudNotificationsTip::_tip_CNRegisterWnpEndpointTip>::~merged_data<CloudNotificationsTip::_tip_CNRegisterWnpEndpointTip,CloudNotificationsTip::_tip_CNRegisterWnpEndpointTip>(void)
0x1800600bb  mov     rcx, rbx; pv
0x1800600be  call    cs:__imp_CoTaskMemFree
0x1800600c4  mov     rcx, rsi
0x1800600c7  call    ?ensure_data@?$tip_test@V?$merged_data@U_tip_CNRegisterWnpEndpointTip@CloudNotificationsTip@@U12@@details@tip2@@@tip2@@AEBAAEAV?$com_ptr_t@V?$merged_data@U_tip_CNRegisterWnpEndpointTip@CloudNotificationsTip@@U12@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ; tip2::tip_test<tip2::details::merged_data<CloudNotificationsTip::_tip_CNRegisterWnpEndpointTip,CloudNotificationsTip::_tip_CNRegisterWnpEndpointTip>>::ensure_data(void)
0x1800600cc  mov     rcx, [rax]
0x1800600cf  add     rcx, 8
0x1800600d3  lea     rdx, [rsp+38h+var_18]
0x1800600d8  call    ?start@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAA?AU_GUID@@XZ; tip2::details::shared_data<0,0,0>::start(void)
0x1800600dd  lea     rax, ??_7?$test_watcher@V?$merged_data@U_tip_CNRegisterWnpEndpointTip@CloudNotificationsTip@@U12@@details@tip2@@@tip2@@6B@; const tip2::test_watcher<tip2::details::merged_data<CloudNotificationsTip::_tip_CNRegisterWnpEndpointTip,CloudNotificationsTip::_tip_CNRegisterWnpEndpointTip>>::`vftable'
0x1800600e4  mov     [rdi], rax
0x1800600e7  lea     rbx, [rdi+8]
0x1800600eb  mov     qword ptr [rbx], 0
0x1800600f2  mov     [rbx+8], rdi
0x1800600f6  mov     qword ptr [rbx+10h], 0
0x1800600fe  mov     dword ptr [rbx+18h], 0
0x180060105  mov     qword ptr [rbx+20h], 0
0x18006010d  mov     byte ptr [rbx+28h], 0
0x180060111  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, 0; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180060119  jz      short loc_18006013D
0x18006011b  mov     dl, 1
0x18006011d  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x180060122  mov     [rbx], rax
0x180060125  test    rax, rax
0x180060128  jz      short loc_18006013D
0x18006012a  mov     rcx, [rax]
0x18006012d  mov     [rbx+10h], rcx
0x180060131  mov     [rax], rbx
0x180060134  call    cs:__imp_GetCurrentThreadId
0x18006013a  mov     [rbx+18h], eax
0x18006013d  mov     rax, [rsi]
0x180060140  mov     [rdi+38h], rax
0x180060144  test    rax, rax
0x180060147  jz      short loc_180060150
0x180060149  lock inc dword ptr [rax+180h]
0x180060150  mov     rax, rdi
0x180060153  mov     rbx, [rsp+38h+arg_8]
0x180060158  mov     rsi, [rsp+38h+arg_10]
0x18006015d  add     rsp, 30h
0x180060161  pop     rdi
0x180060162  retn
```
