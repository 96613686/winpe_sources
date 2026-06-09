# tip2::tip_test<tip2::details::merged_data<AfsTip::_tip_CRHomeCloudTip,AfsTip::_tip_CRHomeCloudTip>>::start_and_watch_errors(void)

- ea: `0x1800685c8`
- end: `0x1800686bf`
- name: `?start_and_watch_errors@?$tip_test@V?$merged_data@U_tip_CRHomeCloudTip@AfsTip@@U12@@details@tip2@@@tip2@@QEAA?AV?$test_watcher@V?$merged_data@U_tip_CRHomeCloudTip@AfsTip@@U12@@details@tip2@@@2@XZ`
- size: `247`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x180061d10`

## callees

- `0x180009610`
- `0x18001bed0`
- `0x180060e40`
- `0x180067ca8`
- `0x1800685c8`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006861a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006861a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180068690`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180068690`

## pseudocode

```c
__int64 __fastcall tip2::tip_test<tip2::details::merged_data<AfsTip::_tip_CRHomeCloudTip,AfsTip::_tip_CRHomeCloudTip>>::start_and_watch_errors(
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
    if ( _InterlockedExchangeAdd(v4 + 78, 0xFFFFFFFF) == 1 )
    {
      tip2::details::merged_data<AfsTip::_tip_CRHomeCloudTip,AfsTip::_tip_CRHomeCloudTip>::~merged_data<AfsTip::_tip_CRHomeCloudTip,AfsTip::_tip_CRHomeCloudTip>((struct _RTL_CRITICAL_SECTION *)v4);
      CoTaskMemFree((LPVOID)v4);
    }
  }
  v5 = tip2::tip_test<tip2::details::merged_data<AfsTip::_tip_CRHomeCloudTip,AfsTip::_tip_CRHomeCloudTip>>::ensure_data(a1);
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
    _InterlockedIncrement(v10 + 78);
  return a2;
}

```

## disassembly

```asm
0x1800685c8  mov     [rsp+arg_8], rbx
0x1800685cd  mov     [rsp+arg_10], rsi
0x1800685d2  push    rdi
0x1800685d3  sub     rsp, 30h
0x1800685d7  mov     rdi, rdx
0x1800685da  mov     rsi, rcx
0x1800685dd  mov     rbx, [rcx]
0x1800685e0  test    rbx, rbx
0x1800685e3  jz      short loc_180068620
0x1800685e5  cmp     qword ptr [rbx+0F8h], 0
0x1800685ed  jnz     short loc_1800685F8
0x1800685ef  test    dword ptr [rbx+48h], 100h
0x1800685f6  jz      short loc_180068620
0x1800685f8  mov     qword ptr [rcx], 0
0x1800685ff  or      eax, 0FFFFFFFFh
0x180068602  lock xadd [rbx+138h], eax
0x18006860a  cmp     eax, 1
0x18006860d  jnz     short loc_180068620
0x18006860f  mov     rcx, rbx
0x180068612  call    ??1?$merged_data@U_tip_CRHomeCloudTip@AfsTip@@U12@@details@tip2@@QEAA@XZ; tip2::details::merged_data<AfsTip::_tip_CRHomeCloudTip,AfsTip::_tip_CRHomeCloudTip>::~merged_data<AfsTip::_tip_CRHomeCloudTip,AfsTip::_tip_CRHomeCloudTip>(void)
0x180068617  mov     rcx, rbx; pv
0x18006861a  call    cs:__imp_CoTaskMemFree
0x180068620  mov     rcx, rsi
0x180068623  call    ?ensure_data@?$tip_test@V?$merged_data@U_tip_CRHomeCloudTip@AfsTip@@U12@@details@tip2@@@tip2@@AEBAAEAV?$com_ptr_t@V?$merged_data@U_tip_CRHomeCloudTip@AfsTip@@U12@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ; tip2::tip_test<tip2::details::merged_data<AfsTip::_tip_CRHomeCloudTip,AfsTip::_tip_CRHomeCloudTip>>::ensure_data(void)
0x180068628  mov     rcx, [rax]
0x18006862b  add     rcx, 8
0x18006862f  lea     rdx, [rsp+38h+var_18]
0x180068634  call    ?start@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAA?AU_GUID@@XZ; tip2::details::shared_data<0,0,0>::start(void)
0x180068639  lea     rax, ??_7?$test_watcher@V?$merged_data@U_tip_CNRegisterWnpEndpointTip@CloudNotificationsTip@@U12@@details@tip2@@@tip2@@6B@; const tip2::test_watcher<tip2::details::merged_data<CloudNotificationsTip::_tip_CNRegisterWnpEndpointTip,CloudNotificationsTip::_tip_CNRegisterWnpEndpointTip>>::`vftable'
0x180068640  mov     [rdi], rax
0x180068643  lea     rbx, [rdi+8]
0x180068647  mov     qword ptr [rbx], 0
0x18006864e  mov     [rbx+8], rdi
0x180068652  mov     qword ptr [rbx+10h], 0
0x18006865a  mov     dword ptr [rbx+18h], 0
0x180068661  mov     qword ptr [rbx+20h], 0
0x180068669  mov     byte ptr [rbx+28h], 0
0x18006866d  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, 0; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180068675  jz      short loc_180068699
0x180068677  mov     dl, 1
0x180068679  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x18006867e  mov     [rbx], rax
0x180068681  test    rax, rax
0x180068684  jz      short loc_180068699
0x180068686  mov     rcx, [rax]
0x180068689  mov     [rbx+10h], rcx
0x18006868d  mov     [rax], rbx
0x180068690  call    cs:__imp_GetCurrentThreadId
0x180068696  mov     [rbx+18h], eax
0x180068699  mov     rax, [rsi]
0x18006869c  mov     [rdi+38h], rax
0x1800686a0  test    rax, rax
0x1800686a3  jz      short loc_1800686AC
0x1800686a5  lock inc dword ptr [rax+138h]
0x1800686ac  mov     rax, rdi
0x1800686af  mov     rbx, [rsp+38h+arg_8]
0x1800686b4  mov     rsi, [rsp+38h+arg_10]
0x1800686b9  add     rsp, 30h
0x1800686bd  pop     rdi
0x1800686be  retn
```
