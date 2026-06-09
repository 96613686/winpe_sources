# ??$start_and_watch_errors@V?$tip_test@V?$merged_data@U_tip_UnifiedConsentSyncTaskTipTest@ConsentCoordinationTip@@U12@@details@tip2@@@tip2@@@tip2@@YA?A_PXZ

- ea: `0x180012870`
- end: `0x180012973`
- name: `??$start_and_watch_errors@V?$tip_test@V?$merged_data@U_tip_UnifiedConsentSyncTaskTipTest@ConsentCoordinationTip@@U12@@details@tip2@@@tip2@@@tip2@@YA?A_PXZ`
- size: `259`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x180018380`

## callees

- `0x180009610`
- `0x180012870`
- `0x18001297c`
- `0x180013a68`
- `0x18001bed0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800128bb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001295a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800128bb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001295a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180012926`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180012926`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall tip2::start_and_watch_errors<tip2::tip_test<tip2::details::merged_data<ConsentCoordinationTip::_tip_UnifiedConsentSyncTaskTipTest,ConsentCoordinationTip::_tip_UnifiedConsentSyncTaskTipTest>>>(
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

  v2 = (volatile signed __int32 **)tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<ConsentCoordinationTip::_tip_UnifiedConsentSyncTaskTipTest,ConsentCoordinationTip::_tip_UnifiedConsentSyncTaskTipTest>,>(&pv);
  v3 = *v2;
  *v2 = 0;
  v4 = pv;
  if ( pv && _InterlockedExchangeAdd((volatile signed __int32 *)pv + 72, 0xFFFFFFFF) == 1 )
  {
    tip2::details::merged_data<ConsentCoordinationTip::_tip_UnifiedConsentSyncTaskTipTest,ConsentCoordinationTip::_tip_UnifiedConsentSyncTaskTipTest>::~merged_data<ConsentCoordinationTip::_tip_UnifiedConsentSyncTaskTipTest,ConsentCoordinationTip::_tip_UnifiedConsentSyncTaskTipTest>(v4);
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
    _InterlockedIncrement(v3 + 72);
    if ( _InterlockedExchangeAdd(v3 + 72, 0xFFFFFFFF) == 1 )
    {
      tip2::details::merged_data<ConsentCoordinationTip::_tip_UnifiedConsentSyncTaskTipTest,ConsentCoordinationTip::_tip_UnifiedConsentSyncTaskTipTest>::~merged_data<ConsentCoordinationTip::_tip_UnifiedConsentSyncTaskTipTest,ConsentCoordinationTip::_tip_UnifiedConsentSyncTaskTipTest>(v3);
      CoTaskMemFree((LPVOID)v3);
    }
  }
  return a1;
}

```

## disassembly

```asm
0x180012870  mov     [rsp+arg_10], rbx
0x180012875  mov     [rsp+arg_18], rsi
0x18001287a  push    rdi
0x18001287b  sub     rsp, 30h
0x18001287f  mov     rsi, rcx
0x180012882  lea     rcx, [rsp+38h+pv]
0x180012887  call    ??$tip_make_shared_nothrow@V?$merged_data@U_tip_UnifiedConsentSyncTaskTipTest@ConsentCoordinationTip@@U12@@details@tip2@@$$V@details@tip2@@YA?AV?$com_ptr_t@V?$merged_data@U_tip_UnifiedConsentSyncTaskTipTest@ConsentCoordinationTip@@U12@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ; tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<ConsentCoordinationTip::_tip_UnifiedConsentSyncTaskTipTest,ConsentCoordinationTip::_tip_UnifiedConsentSyncTaskTipTest>,>(void)
0x18001288c  mov     rbx, [rax]
0x18001288f  mov     qword ptr [rax], 0
0x180012896  mov     rdi, [rsp+38h+pv]
0x18001289b  test    rdi, rdi
0x18001289e  jz      short loc_1800128C1
0x1800128a0  or      eax, 0FFFFFFFFh
0x1800128a3  lock xadd [rdi+120h], eax
0x1800128ab  cmp     eax, 1
0x1800128ae  jnz     short loc_1800128C1
0x1800128b0  mov     rcx, rdi
0x1800128b3  call    ??1?$merged_data@U_tip_UnifiedConsentSyncTaskTipTest@ConsentCoordinationTip@@U12@@details@tip2@@QEAA@XZ; tip2::details::merged_data<ConsentCoordinationTip::_tip_UnifiedConsentSyncTaskTipTest,ConsentCoordinationTip::_tip_UnifiedConsentSyncTaskTipTest>::~merged_data<ConsentCoordinationTip::_tip_UnifiedConsentSyncTaskTipTest,ConsentCoordinationTip::_tip_UnifiedConsentSyncTaskTipTest>(void)
0x1800128b8  mov     rcx, rdi; pv
0x1800128bb  call    cs:__imp_CoTaskMemFree
0x1800128c1  lea     rcx, [rbx+8]
0x1800128c5  lea     rdx, [rsp+38h+var_18]
0x1800128ca  call    ?start@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAA?AU_GUID@@XZ; tip2::details::shared_data<0,0,0>::start(void)
0x1800128cf  lea     rax, ??_7?$test_watcher@V?$merged_data@U_tip_CNRegisterWnpEndpointTip@CloudNotificationsTip@@U12@@details@tip2@@@tip2@@6B@; const tip2::test_watcher<tip2::details::merged_data<CloudNotificationsTip::_tip_CNRegisterWnpEndpointTip,CloudNotificationsTip::_tip_CNRegisterWnpEndpointTip>>::`vftable'
0x1800128d6  mov     [rsi], rax
0x1800128d9  lea     rdi, [rsi+8]
0x1800128dd  mov     qword ptr [rdi], 0
0x1800128e4  mov     [rdi+8], rsi
0x1800128e8  mov     qword ptr [rdi+10h], 0
0x1800128f0  mov     dword ptr [rdi+18h], 0
0x1800128f7  mov     qword ptr [rdi+20h], 0
0x1800128ff  mov     byte ptr [rdi+28h], 0
0x180012903  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, 0; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x18001290b  jz      short loc_18001292F
0x18001290d  mov     dl, 1
0x18001290f  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x180012914  mov     [rdi], rax
0x180012917  test    rax, rax
0x18001291a  jz      short loc_18001292F
0x18001291c  mov     rcx, [rax]
0x18001291f  mov     [rdi+10h], rcx
0x180012923  mov     [rax], rdi
0x180012926  call    cs:__imp_GetCurrentThreadId
0x18001292c  mov     [rdi+18h], eax
0x18001292f  mov     [rsi+38h], rbx
0x180012933  test    rbx, rbx
0x180012936  jz      short loc_180012960
0x180012938  lock inc dword ptr [rbx+120h]
0x18001293f  or      eax, 0FFFFFFFFh
0x180012942  lock xadd [rbx+120h], eax
0x18001294a  cmp     eax, 1
0x18001294d  jnz     short loc_180012960
0x18001294f  mov     rcx, rbx
0x180012952  call    ??1?$merged_data@U_tip_UnifiedConsentSyncTaskTipTest@ConsentCoordinationTip@@U12@@details@tip2@@QEAA@XZ; tip2::details::merged_data<ConsentCoordinationTip::_tip_UnifiedConsentSyncTaskTipTest,ConsentCoordinationTip::_tip_UnifiedConsentSyncTaskTipTest>::~merged_data<ConsentCoordinationTip::_tip_UnifiedConsentSyncTaskTipTest,ConsentCoordinationTip::_tip_UnifiedConsentSyncTaskTipTest>(void)
0x180012957  mov     rcx, rbx; pv
0x18001295a  call    cs:__imp_CoTaskMemFree
0x180012960  mov     rax, rsi
0x180012963  mov     rbx, [rsp+38h+arg_10]
0x180012968  mov     rsi, [rsp+38h+arg_18]
0x18001296d  add     rsp, 30h
0x180012971  pop     rdi
0x180012972  retn
```
