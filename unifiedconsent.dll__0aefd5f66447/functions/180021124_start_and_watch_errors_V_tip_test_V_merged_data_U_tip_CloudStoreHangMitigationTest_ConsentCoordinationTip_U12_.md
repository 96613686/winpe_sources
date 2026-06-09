# ??$start_and_watch_errors@V?$tip_test@V?$merged_data@U_tip_CloudStoreHangMitigationTest@ConsentCoordinationTip@@U12@@details@tip2@@@tip2@@@tip2@@YA?A_PXZ

- ea: `0x180021124`
- end: `0x180021227`
- name: `??$start_and_watch_errors@V?$tip_test@V?$merged_data@U_tip_CloudStoreHangMitigationTest@ConsentCoordinationTip@@U12@@details@tip2@@@tip2@@@tip2@@YA?A_PXZ`
- size: `259`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x18002be40`

## callees

- `0x180009610`
- `0x18001bed0`
- `0x180021124`
- `0x180021230`
- `0x1800229ac`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002116f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002120e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002116f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002120e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800211da`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800211da`

## pseudocode

```c
__int64 __fastcall tip2::start_and_watch_errors<tip2::tip_test<tip2::details::merged_data<ConsentCoordinationTip::_tip_CloudStoreHangMitigationTest,ConsentCoordinationTip::_tip_CloudStoreHangMitigationTest>>>(
        __int64 a1)
{
  volatile signed __int32 **v2; // rax
  volatile signed __int32 *v3; // rbx
  void *v4; // rdi
  __int64 v5; // rdx
  __int64 v6; // rcx
  _QWORD *v7; // rdi
  _QWORD *Local; // rax
  _BYTE v10[24]; // [rsp+20h] [rbp-18h] BYREF
  LPVOID pv; // [rsp+48h] [rbp+10h] BYREF

  v2 = (volatile signed __int32 **)tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<ConsentCoordinationTip::_tip_CloudStoreHangMitigationTest,ConsentCoordinationTip::_tip_CloudStoreHangMitigationTest>,>(&pv);
  v3 = *v2;
  *v2 = 0;
  v4 = pv;
  if ( pv && _InterlockedExchangeAdd((volatile signed __int32 *)pv + 70, 0xFFFFFFFF) == 1 )
  {
    tip2::details::merged_data<ConsentCoordinationTip::_tip_CloudStoreHangMitigationTest,ConsentCoordinationTip::_tip_CloudStoreHangMitigationTest>::~merged_data<ConsentCoordinationTip::_tip_CloudStoreHangMitigationTest,ConsentCoordinationTip::_tip_CloudStoreHangMitigationTest>(v4);
    CoTaskMemFree(v4);
  }
  tip2::details::shared_data<0,0,0>::start(v3 + 2, v10);
  *(_QWORD *)a1 = &tip2::test_watcher<tip2::details::merged_data<CloudNotificationsTip::_tip_CNRegisterWnpEndpointTip,CloudNotificationsTip::_tip_CNRegisterWnpEndpointTip>>::`vftable';
  v7 = (_QWORD *)(a1 + 8);
  *(_QWORD *)(a1 + 8) = 0;
  *(_QWORD *)(a1 + 16) = a1;
  *(_QWORD *)(a1 + 24) = 0;
  *(_DWORD *)(a1 + 32) = 0;
  *(_QWORD *)(a1 + 40) = 0;
  *(_BYTE *)(a1 + 48) = 0;
  if ( wil::details::g_pThreadFailureCallbacks )
  {
    LOBYTE(v5) = 1;
    Local = (_QWORD *)wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(
                        v6,
                        v5);
    *v7 = Local;
    if ( Local )
    {
      *(_QWORD *)(a1 + 24) = *Local;
      *Local = v7;
      *(_DWORD *)(a1 + 32) = GetCurrentThreadId();
    }
  }
  *(_QWORD *)(a1 + 56) = v3;
  if ( v3 )
  {
    _InterlockedIncrement(v3 + 70);
    if ( _InterlockedExchangeAdd(v3 + 70, 0xFFFFFFFF) == 1 )
    {
      tip2::details::merged_data<ConsentCoordinationTip::_tip_CloudStoreHangMitigationTest,ConsentCoordinationTip::_tip_CloudStoreHangMitigationTest>::~merged_data<ConsentCoordinationTip::_tip_CloudStoreHangMitigationTest,ConsentCoordinationTip::_tip_CloudStoreHangMitigationTest>(v3);
      CoTaskMemFree((LPVOID)v3);
    }
  }
  return a1;
}

```

## disassembly

```asm
0x180021124  mov     [rsp+arg_10], rbx
0x180021129  mov     [rsp+arg_18], rsi
0x18002112e  push    rdi
0x18002112f  sub     rsp, 30h
0x180021133  mov     rsi, rcx
0x180021136  lea     rcx, [rsp+38h+pv]
0x18002113b  call    ??$tip_make_shared_nothrow@V?$merged_data@U_tip_CloudStoreHangMitigationTest@ConsentCoordinationTip@@U12@@details@tip2@@$$V@details@tip2@@YA?AV?$com_ptr_t@V?$merged_data@U_tip_CloudStoreHangMitigationTest@ConsentCoordinationTip@@U12@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ; tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<ConsentCoordinationTip::_tip_CloudStoreHangMitigationTest,ConsentCoordinationTip::_tip_CloudStoreHangMitigationTest>,>(void)
0x180021140  mov     rbx, [rax]
0x180021143  mov     qword ptr [rax], 0
0x18002114a  mov     rdi, [rsp+38h+pv]
0x18002114f  test    rdi, rdi
0x180021152  jz      short loc_180021175
0x180021154  or      eax, 0FFFFFFFFh
0x180021157  lock xadd [rdi+118h], eax
0x18002115f  cmp     eax, 1
0x180021162  jnz     short loc_180021175
0x180021164  mov     rcx, rdi
0x180021167  call    ??1?$merged_data@U_tip_CloudStoreHangMitigationTest@ConsentCoordinationTip@@U12@@details@tip2@@QEAA@XZ; tip2::details::merged_data<ConsentCoordinationTip::_tip_CloudStoreHangMitigationTest,ConsentCoordinationTip::_tip_CloudStoreHangMitigationTest>::~merged_data<ConsentCoordinationTip::_tip_CloudStoreHangMitigationTest,ConsentCoordinationTip::_tip_CloudStoreHangMitigationTest>(void)
0x18002116c  mov     rcx, rdi; pv
0x18002116f  call    cs:__imp_CoTaskMemFree
0x180021175  lea     rcx, [rbx+8]
0x180021179  lea     rdx, [rsp+38h+var_18]
0x18002117e  call    ?start@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAA?AU_GUID@@XZ; tip2::details::shared_data<0,0,0>::start(void)
0x180021183  lea     rax, ??_7?$test_watcher@V?$merged_data@U_tip_CNRegisterWnpEndpointTip@CloudNotificationsTip@@U12@@details@tip2@@@tip2@@6B@; const tip2::test_watcher<tip2::details::merged_data<CloudNotificationsTip::_tip_CNRegisterWnpEndpointTip,CloudNotificationsTip::_tip_CNRegisterWnpEndpointTip>>::`vftable'
0x18002118a  mov     [rsi], rax
0x18002118d  lea     rdi, [rsi+8]
0x180021191  mov     qword ptr [rdi], 0
0x180021198  mov     [rdi+8], rsi
0x18002119c  mov     qword ptr [rdi+10h], 0
0x1800211a4  mov     dword ptr [rdi+18h], 0
0x1800211ab  mov     qword ptr [rdi+20h], 0
0x1800211b3  mov     byte ptr [rdi+28h], 0
0x1800211b7  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, 0; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x1800211bf  jz      short loc_1800211E3
0x1800211c1  mov     dl, 1
0x1800211c3  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x1800211c8  mov     [rdi], rax
0x1800211cb  test    rax, rax
0x1800211ce  jz      short loc_1800211E3
0x1800211d0  mov     rcx, [rax]
0x1800211d3  mov     [rdi+10h], rcx
0x1800211d7  mov     [rax], rdi
0x1800211da  call    cs:__imp_GetCurrentThreadId
0x1800211e0  mov     [rdi+18h], eax
0x1800211e3  mov     [rsi+38h], rbx
0x1800211e7  test    rbx, rbx
0x1800211ea  jz      short loc_180021214
0x1800211ec  lock inc dword ptr [rbx+118h]
0x1800211f3  or      eax, 0FFFFFFFFh
0x1800211f6  lock xadd [rbx+118h], eax
0x1800211fe  cmp     eax, 1
0x180021201  jnz     short loc_180021214
0x180021203  mov     rcx, rbx
0x180021206  call    ??1?$merged_data@U_tip_CloudStoreHangMitigationTest@ConsentCoordinationTip@@U12@@details@tip2@@QEAA@XZ; tip2::details::merged_data<ConsentCoordinationTip::_tip_CloudStoreHangMitigationTest,ConsentCoordinationTip::_tip_CloudStoreHangMitigationTest>::~merged_data<ConsentCoordinationTip::_tip_CloudStoreHangMitigationTest,ConsentCoordinationTip::_tip_CloudStoreHangMitigationTest>(void)
0x18002120b  mov     rcx, rbx; pv
0x18002120e  call    cs:__imp_CoTaskMemFree
0x180021214  mov     rax, rsi
0x180021217  mov     rbx, [rsp+38h+arg_10]
0x18002121c  mov     rsi, [rsp+38h+arg_18]
0x180021221  add     rsp, 30h
0x180021225  pop     rdi
0x180021226  retn
```
