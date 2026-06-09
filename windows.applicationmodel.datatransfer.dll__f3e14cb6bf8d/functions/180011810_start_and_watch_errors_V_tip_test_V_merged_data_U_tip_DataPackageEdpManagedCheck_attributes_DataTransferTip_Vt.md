# ??$start_and_watch_errors@V?$tip_test@V?$merged_data@U_tip_DataPackageEdpManagedCheck_attributes@DataTransferTip@@Vtest_data_basic@tip2@@@details@tip2@@@tip2@@@tip2@@YA?A_PXZ

- ea: `0x180011810`
- end: `0x180011913`
- name: `??$start_and_watch_errors@V?$tip_test@V?$merged_data@U_tip_DataPackageEdpManagedCheck_attributes@DataTransferTip@@Vtest_data_basic@tip2@@@details@tip2@@@tip2@@@tip2@@YA?A_PXZ`
- size: `259`
- prototype: ``
- caller_count: `7`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000e5a0`
- `0x18000e874`
- `0x18000eb1c`
- `0x18000edc0`
- `0x18000f09c`
- `0x18000f340`
- `0x18000f5e8`

## callees

- `0x180011810`
- `0x18001191c`
- `0x180016c04`
- `0x1800314ac`
- `0x18005f100`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800118c6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800118c6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001185b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800118fa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001185b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800118fa`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall tip2::start_and_watch_errors<tip2::tip_test<tip2::details::merged_data<DataTransferTip::_tip_DataPackageEdpManagedCheck_attributes,tip2::test_data_basic>>>(
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

  v2 = (volatile signed __int32 **)tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<DataTransferTip::_tip_DataPackageEdpManagedCheck_attributes,tip2::test_data_basic>,>(&pv);
  v3 = *v2;
  *v2 = 0;
  v4 = pv;
  if ( pv && _InterlockedExchangeAdd((volatile signed __int32 *)pv + 84, 0xFFFFFFFF) == 1 )
  {
    tip2::details::merged_data<DataTransferTip::_tip_DataPackageEdpManagedCheck_attributes,tip2::test_data_basic>::~merged_data<DataTransferTip::_tip_DataPackageEdpManagedCheck_attributes,tip2::test_data_basic>(v4);
    CoTaskMemFree(v4);
  }
  tip2::details::shared_data<0,0,1>::start(v3 + 2, v10);
  *(_QWORD *)a1 = &tip2::test_watcher<tip2::details::merged_data<DataTransferTip::_tip_DataPackageEdpManagedCheck_attributes,tip2::test_data_basic>>::`vftable';
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
      tip2::details::merged_data<DataTransferTip::_tip_DataPackageEdpManagedCheck_attributes,tip2::test_data_basic>::~merged_data<DataTransferTip::_tip_DataPackageEdpManagedCheck_attributes,tip2::test_data_basic>(v3);
      CoTaskMemFree((LPVOID)v3);
    }
  }
  return a1;
}

```

## disassembly

```asm
0x180011810  mov     [rsp+arg_10], rbx
0x180011815  mov     [rsp+arg_18], rsi
0x18001181a  push    rdi
0x18001181b  sub     rsp, 30h
0x18001181f  mov     rsi, rcx
0x180011822  lea     rcx, [rsp+38h+pv]
0x180011827  call    ??$tip_make_shared_nothrow@V?$merged_data@U_tip_DataPackageEdpManagedCheck_attributes@DataTransferTip@@Vtest_data_basic@tip2@@@details@tip2@@$$V@details@tip2@@YA?AV?$com_ptr_t@V?$merged_data@U_tip_DataPackageEdpManagedCheck_attributes@DataTransferTip@@Vtest_data_basic@tip2@@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ; tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<DataTransferTip::_tip_DataPackageEdpManagedCheck_attributes,tip2::test_data_basic>,>(void)
0x18001182c  mov     rbx, [rax]
0x18001182f  mov     qword ptr [rax], 0
0x180011836  mov     rdi, [rsp+38h+pv]
0x18001183b  test    rdi, rdi
0x18001183e  jz      short loc_180011861
0x180011840  or      eax, 0FFFFFFFFh
0x180011843  lock xadd [rdi+150h], eax
0x18001184b  cmp     eax, 1
0x18001184e  jnz     short loc_180011861
0x180011850  mov     rcx, rdi
0x180011853  call    ??1?$merged_data@U_tip_DataPackageEdpManagedCheck_attributes@DataTransferTip@@Vtest_data_basic@tip2@@@details@tip2@@QEAA@XZ; tip2::details::merged_data<DataTransferTip::_tip_DataPackageEdpManagedCheck_attributes,tip2::test_data_basic>::~merged_data<DataTransferTip::_tip_DataPackageEdpManagedCheck_attributes,tip2::test_data_basic>(void)
0x180011858  mov     rcx, rdi; pv
0x18001185b  call    cs:__imp_CoTaskMemFree
0x180011861  lea     rcx, [rbx+8]
0x180011865  lea     rdx, [rsp+38h+var_18]
0x18001186a  call    ?start@?$shared_data@$0A@$0A@$00@details@tip2@@AEAA?AU_GUID@@XZ; tip2::details::shared_data<0,0,1>::start(void)
0x18001186f  lea     rax, ??_7?$test_watcher@V?$merged_data@U_tip_DataPackageEdpManagedCheck_attributes@DataTransferTip@@Vtest_data_basic@tip2@@@details@tip2@@@tip2@@6B@; const tip2::test_watcher<tip2::details::merged_data<DataTransferTip::_tip_DataPackageEdpManagedCheck_attributes,tip2::test_data_basic>>::`vftable'
0x180011876  mov     [rsi], rax
0x180011879  lea     rdi, [rsi+8]
0x18001187d  mov     qword ptr [rdi], 0
0x180011884  mov     [rdi+8], rsi
0x180011888  mov     qword ptr [rdi+10h], 0
0x180011890  mov     dword ptr [rdi+18h], 0
0x180011897  mov     qword ptr [rdi+20h], 0
0x18001189f  mov     byte ptr [rdi+28h], 0
0x1800118a3  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, 0; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x1800118ab  jz      short loc_1800118CF
0x1800118ad  mov     dl, 1
0x1800118af  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x1800118b4  mov     [rdi], rax
0x1800118b7  test    rax, rax
0x1800118ba  jz      short loc_1800118CF
0x1800118bc  mov     rcx, [rax]
0x1800118bf  mov     [rdi+10h], rcx
0x1800118c3  mov     [rax], rdi
0x1800118c6  call    cs:__imp_GetCurrentThreadId
0x1800118cc  mov     [rdi+18h], eax
0x1800118cf  mov     [rsi+38h], rbx
0x1800118d3  test    rbx, rbx
0x1800118d6  jz      short loc_180011900
0x1800118d8  lock inc dword ptr [rbx+150h]
0x1800118df  or      eax, 0FFFFFFFFh
0x1800118e2  lock xadd [rbx+150h], eax
0x1800118ea  cmp     eax, 1
0x1800118ed  jnz     short loc_180011900
0x1800118ef  mov     rcx, rbx
0x1800118f2  call    ??1?$merged_data@U_tip_DataPackageEdpManagedCheck_attributes@DataTransferTip@@Vtest_data_basic@tip2@@@details@tip2@@QEAA@XZ; tip2::details::merged_data<DataTransferTip::_tip_DataPackageEdpManagedCheck_attributes,tip2::test_data_basic>::~merged_data<DataTransferTip::_tip_DataPackageEdpManagedCheck_attributes,tip2::test_data_basic>(void)
0x1800118f7  mov     rcx, rbx; pv
0x1800118fa  call    cs:__imp_CoTaskMemFree
0x180011900  mov     rax, rsi
0x180011903  mov     rbx, [rsp+38h+arg_10]
0x180011908  mov     rsi, [rsp+38h+arg_18]
0x18001190d  add     rsp, 30h
0x180011911  pop     rdi
0x180011912  retn
```
