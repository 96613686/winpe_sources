# ??$start_and_watch_errors@V?$tip_test@V?$merged_data@U_tip_DesktopStickerEditorLaunchTest_attributes@@Vtest_data_basic@tip2@@@details@tip2@@@tip2@@@tip2@@YA?A_PXZ

- ea: `0x18002f458`
- end: `0x18002f56e`
- name: `??$start_and_watch_errors@V?$tip_test@V?$merged_data@U_tip_DesktopStickerEditorLaunchTest_attributes@@Vtest_data_basic@tip2@@@details@tip2@@@tip2@@@tip2@@YA?A_PXZ`
- size: `278`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x180030ef0`

## callees

- `0x180006710`
- `0x18002f458`
- `0x18002f574`
- `0x18002fc48`
- `0x1800345d0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002f514`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002f514`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002f4a3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002f54e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002f4a3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002f54e`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall tip2::start_and_watch_errors<tip2::tip_test<tip2::details::merged_data<_tip_DesktopStickerEditorLaunchTest_attributes,tip2::test_data_basic>>>(
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

  v2 = (volatile signed __int32 **)tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<_tip_DesktopStickerEditorLaunchTest_attributes,tip2::test_data_basic>,>(&pv);
  v3 = *v2;
  *v2 = 0;
  v4 = pv;
  if ( pv && _InterlockedExchangeAdd((volatile signed __int32 *)pv + 84, 0xFFFFFFFF) == 1 )
  {
    tip2::details::merged_data<_tip_DesktopStickerEditorLaunchTest_attributes,tip2::test_data_basic>::~merged_data<_tip_DesktopStickerEditorLaunchTest_attributes,tip2::test_data_basic>(v4);
    CoTaskMemFree(v4);
  }
  tip2::details::shared_data<0,0,1>::start(v3 + 2, v10);
  *(_QWORD *)a1 = &tip2::test_watcher<tip2::details::merged_data<_tip_DesktopStickerEditorLaunchTest_attributes,tip2::test_data_basic>>::`vftable';
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
    _InterlockedIncrement(v3 + 84);
    if ( _InterlockedExchangeAdd(v3 + 84, 0xFFFFFFFF) == 1 )
    {
      tip2::details::merged_data<_tip_DesktopStickerEditorLaunchTest_attributes,tip2::test_data_basic>::~merged_data<_tip_DesktopStickerEditorLaunchTest_attributes,tip2::test_data_basic>(v3);
      CoTaskMemFree((LPVOID)v3);
    }
  }
  return a1;
}

```

## disassembly

```asm
0x18002f458  mov     [rsp+arg_10], rbx
0x18002f45d  mov     [rsp+arg_18], rsi
0x18002f462  push    rdi
0x18002f463  sub     rsp, 30h
0x18002f467  mov     rsi, rcx
0x18002f46a  lea     rcx, [rsp+38h+pv]
0x18002f46f  call    ??$tip_make_shared_nothrow@V?$merged_data@U_tip_DesktopStickerEditorLaunchTest_attributes@@Vtest_data_basic@tip2@@@details@tip2@@$$V@details@tip2@@YA?AV?$com_ptr_t@V?$merged_data@U_tip_DesktopStickerEditorLaunchTest_attributes@@Vtest_data_basic@tip2@@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ; tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<_tip_DesktopStickerEditorLaunchTest_attributes,tip2::test_data_basic>,>(void)
0x18002f474  mov     rbx, [rax]
0x18002f477  mov     qword ptr [rax], 0
0x18002f47e  mov     rdi, [rsp+38h+pv]
0x18002f483  test    rdi, rdi
0x18002f486  jz      short loc_18002F4AF
0x18002f488  or      eax, 0FFFFFFFFh
0x18002f48b  lock xadd [rdi+150h], eax
0x18002f493  cmp     eax, 1
0x18002f496  jnz     short loc_18002F4AF
0x18002f498  mov     rcx, rdi
0x18002f49b  call    ??1?$merged_data@U_tip_DesktopStickerEditorLaunchTest_attributes@@Vtest_data_basic@tip2@@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_DesktopStickerEditorLaunchTest_attributes,tip2::test_data_basic>::~merged_data<_tip_DesktopStickerEditorLaunchTest_attributes,tip2::test_data_basic>(void)
0x18002f4a0  mov     rcx, rdi; pv
0x18002f4a3  call    cs:__imp_CoTaskMemFree
0x18002f4aa  nop     dword ptr [rax+rax+00h]
0x18002f4af  lea     rcx, [rbx+8]
0x18002f4b3  lea     rdx, [rsp+38h+var_18]
0x18002f4b8  call    ?start@?$shared_data@$0A@$0A@$00@details@tip2@@AEAA?AU_GUID@@XZ; tip2::details::shared_data<0,0,1>::start(void)
0x18002f4bd  lea     rax, ??_7?$test_watcher@V?$merged_data@U_tip_DesktopStickerEditorLaunchTest_attributes@@Vtest_data_basic@tip2@@@details@tip2@@@tip2@@6B@; const tip2::test_watcher<tip2::details::merged_data<_tip_DesktopStickerEditorLaunchTest_attributes,tip2::test_data_basic>>::`vftable'
0x18002f4c4  mov     [rsi], rax
0x18002f4c7  lea     rdi, [rsi+8]
0x18002f4cb  mov     qword ptr [rdi], 0
0x18002f4d2  mov     [rdi+8], rsi
0x18002f4d6  mov     qword ptr [rdi+10h], 0
0x18002f4de  mov     dword ptr [rdi+18h], 0
0x18002f4e5  mov     qword ptr [rdi+20h], 0
0x18002f4ed  mov     byte ptr [rdi+28h], 0
0x18002f4f1  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, 0; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x18002f4f9  jz      short loc_18002F523
0x18002f4fb  mov     dl, 1
0x18002f4fd  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x18002f502  mov     [rdi], rax
0x18002f505  test    rax, rax
0x18002f508  jz      short loc_18002F523
0x18002f50a  mov     rcx, [rax]
0x18002f50d  mov     [rdi+10h], rcx
0x18002f511  mov     [rax], rdi
0x18002f514  call    cs:__imp_GetCurrentThreadId
0x18002f51b  nop     dword ptr [rax+rax+00h]
0x18002f520  mov     [rdi+18h], eax
0x18002f523  mov     [rsi+38h], rbx
0x18002f527  test    rbx, rbx
0x18002f52a  jz      short loc_18002F55A
0x18002f52c  lock inc dword ptr [rbx+150h]
0x18002f533  or      eax, 0FFFFFFFFh
0x18002f536  lock xadd [rbx+150h], eax
0x18002f53e  cmp     eax, 1
0x18002f541  jnz     short loc_18002F55A
0x18002f543  mov     rcx, rbx
0x18002f546  call    ??1?$merged_data@U_tip_DesktopStickerEditorLaunchTest_attributes@@Vtest_data_basic@tip2@@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_DesktopStickerEditorLaunchTest_attributes,tip2::test_data_basic>::~merged_data<_tip_DesktopStickerEditorLaunchTest_attributes,tip2::test_data_basic>(void)
0x18002f54b  mov     rcx, rbx; pv
0x18002f54e  call    cs:__imp_CoTaskMemFree
0x18002f555  nop     dword ptr [rax+rax+00h]
0x18002f55a  mov     rax, rsi
0x18002f55d  mov     rbx, [rsp+38h+arg_10]
0x18002f562  mov     rsi, [rsp+38h+arg_18]
0x18002f567  add     rsp, 30h
0x18002f56b  pop     rdi
0x18002f56c  retn
```
