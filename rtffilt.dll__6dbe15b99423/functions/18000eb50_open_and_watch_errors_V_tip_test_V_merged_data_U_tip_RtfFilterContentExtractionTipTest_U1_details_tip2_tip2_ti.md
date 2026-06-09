# ??$open_and_watch_errors@V?$tip_test@V?$merged_data@U_tip_RtfFilterContentExtractionTipTest@@U1@@details@tip2@@@tip2@@@tip2@@YA?A_PXZ

- ea: `0x18000eb50`
- end: `0x18000ec2f`
- name: `??$open_and_watch_errors@V?$tip_test@V?$merged_data@U_tip_RtfFilterContentExtractionTipTest@@U1@@details@tip2@@@tip2@@@tip2@@YA?A_PXZ`
- size: `223`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x180011994`

## callees

- `0x18000eb50`
- `0x18000f708`
- `0x18000f9c0`
- `0x18000fcd4`
- `0x180015fc0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000ebb0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000ebdb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000ec1b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000ebb0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000ebdb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000ec1b`

## pseudocode

```c
__int64 __fastcall tip2::open_and_watch_errors<tip2::tip_test<tip2::details::merged_data<_tip_RtfFilterContentExtractionTipTest,_tip_RtfFilterContentExtractionTipTest>>>(
        __int64 a1)
{
  void **v2; // rax
  void *v3; // rdx
  volatile signed __int32 *v4; // rbx
  void *v5; // rbx
  __int64 v6; // rax
  void *v7; // rbx
  __int64 v9; // [rsp+30h] [rbp+8h] BYREF
  LPVOID pv; // [rsp+38h] [rbp+10h] BYREF
  LPVOID v11; // [rsp+40h] [rbp+18h] BYREF

  pv = 0;
  v9 = 0;
  v2 = (void **)tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<_tip_RtfFilterContentExtractionTipTest,_tip_RtfFilterContentExtractionTipTest>,_GUID * &>(
                  &v11,
                  &v9);
  v3 = *v2;
  *v2 = 0;
  v4 = (volatile signed __int32 *)pv;
  pv = v3;
  if ( v4 && _InterlockedExchangeAdd(v4 + 70, 0xFFFFFFFF) == 1 )
  {
    tip2::details::merged_data<_tip_RtfFilterContentExtractionTipTest,_tip_RtfFilterContentExtractionTipTest>::~merged_data<_tip_RtfFilterContentExtractionTipTest,_tip_RtfFilterContentExtractionTipTest>(v4);
    CoTaskMemFree((LPVOID)v4);
  }
  v5 = v11;
  if ( v11 && _InterlockedExchangeAdd((volatile signed __int32 *)v11 + 70, 0xFFFFFFFF) == 1 )
  {
    tip2::details::merged_data<_tip_RtfFilterContentExtractionTipTest,_tip_RtfFilterContentExtractionTipTest>::~merged_data<_tip_RtfFilterContentExtractionTipTest,_tip_RtfFilterContentExtractionTipTest>(v5);
    CoTaskMemFree(v5);
  }
  v6 = tip2::tip_test<tip2::details::merged_data<_tip_RtfFilterContentExtractionTipTest,_tip_RtfFilterContentExtractionTipTest>>::ensure_data(&pv);
  tip2::test_watcher<tip2::details::merged_data<_tip_RtfFilterContentExtractionTipTest,_tip_RtfFilterContentExtractionTipTest>>::test_watcher<tip2::details::merged_data<_tip_RtfFilterContentExtractionTipTest,_tip_RtfFilterContentExtractionTipTest>>(
    a1,
    v6);
  v7 = pv;
  if ( pv && _InterlockedExchangeAdd((volatile signed __int32 *)pv + 70, 0xFFFFFFFF) == 1 )
  {
    tip2::details::merged_data<_tip_RtfFilterContentExtractionTipTest,_tip_RtfFilterContentExtractionTipTest>::~merged_data<_tip_RtfFilterContentExtractionTipTest,_tip_RtfFilterContentExtractionTipTest>(v7);
    CoTaskMemFree(v7);
  }
  return a1;
}

```

## disassembly

```asm
0x18000eb50  mov     rax, rsp
0x18000eb53  mov     [rax+20h], rbx
0x18000eb57  push    rdi
0x18000eb58  sub     rsp, 20h
0x18000eb5c  mov     rdi, rcx
0x18000eb5f  mov     qword ptr [rax+10h], 0
0x18000eb67  lea     rcx, [rax+18h]
0x18000eb6b  mov     qword ptr [rax+8], 0
0x18000eb73  lea     rdx, [rax+8]
0x18000eb77  call    ??$tip_make_shared_nothrow@V?$merged_data@U_tip_RtfFilterContentExtractionTipTest@@U1@@details@tip2@@AEAPEAU_GUID@@@details@tip2@@YA?AV?$com_ptr_t@V?$merged_data@U_tip_RtfFilterContentExtractionTipTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@AEAPEAU_GUID@@@Z; tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<_tip_RtfFilterContentExtractionTipTest,_tip_RtfFilterContentExtractionTipTest>,_GUID * &>(_GUID * &)
0x18000eb7c  mov     rdx, [rax]
0x18000eb7f  mov     qword ptr [rax], 0
0x18000eb86  mov     rbx, [rsp+28h+pv]
0x18000eb8b  mov     [rsp+28h+pv], rdx
0x18000eb90  test    rbx, rbx
0x18000eb93  jz      short loc_18000EBB6
0x18000eb95  or      eax, 0FFFFFFFFh
0x18000eb98  lock xadd [rbx+118h], eax
0x18000eba0  cmp     eax, 1
0x18000eba3  jnz     short loc_18000EBB6
0x18000eba5  mov     rcx, rbx
0x18000eba8  call    ??1?$merged_data@U_tip_RtfFilterContentExtractionTipTest@@U1@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_RtfFilterContentExtractionTipTest,_tip_RtfFilterContentExtractionTipTest>::~merged_data<_tip_RtfFilterContentExtractionTipTest,_tip_RtfFilterContentExtractionTipTest>(void)
0x18000ebad  mov     rcx, rbx; pv
0x18000ebb0  call    cs:__imp_CoTaskMemFree
0x18000ebb6  mov     rbx, [rsp+28h+arg_10]
0x18000ebbb  test    rbx, rbx
0x18000ebbe  jz      short loc_18000EBE1
0x18000ebc0  or      eax, 0FFFFFFFFh
0x18000ebc3  lock xadd [rbx+118h], eax
0x18000ebcb  cmp     eax, 1
0x18000ebce  jnz     short loc_18000EBE1
0x18000ebd0  mov     rcx, rbx
0x18000ebd3  call    ??1?$merged_data@U_tip_RtfFilterContentExtractionTipTest@@U1@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_RtfFilterContentExtractionTipTest,_tip_RtfFilterContentExtractionTipTest>::~merged_data<_tip_RtfFilterContentExtractionTipTest,_tip_RtfFilterContentExtractionTipTest>(void)
0x18000ebd8  mov     rcx, rbx; pv
0x18000ebdb  call    cs:__imp_CoTaskMemFree
0x18000ebe1  lea     rcx, [rsp+28h+pv]
0x18000ebe6  call    ?ensure_data@?$tip_test@V?$merged_data@U_tip_RtfFilterContentExtractionTipTest@@U1@@details@tip2@@@tip2@@AEBAAEAV?$com_ptr_t@V?$merged_data@U_tip_RtfFilterContentExtractionTipTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ; tip2::tip_test<tip2::details::merged_data<_tip_RtfFilterContentExtractionTipTest,_tip_RtfFilterContentExtractionTipTest>>::ensure_data(void)
0x18000ebeb  mov     rdx, rax
0x18000ebee  mov     rcx, rdi
0x18000ebf1  call    ??0?$test_watcher@V?$merged_data@U_tip_RtfFilterContentExtractionTipTest@@U1@@details@tip2@@@tip2@@IEAA@AEAV?$com_ptr_t@V?$merged_data@U_tip_RtfFilterContentExtractionTipTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@@Z; tip2::test_watcher<tip2::details::merged_data<_tip_RtfFilterContentExtractionTipTest,_tip_RtfFilterContentExtractionTipTest>>::test_watcher<tip2::details::merged_data<_tip_RtfFilterContentExtractionTipTest,_tip_RtfFilterContentExtractionTipTest>>(wil::com_ptr_t<tip2::details::merged_data<_tip_RtfFilterContentExtractionTipTest,_tip_RtfFilterContentExtractionTipTest>,wil::err_returncode_policy> &)
0x18000ebf6  mov     rbx, [rsp+28h+pv]
0x18000ebfb  test    rbx, rbx
0x18000ebfe  jz      short loc_18000EC21
0x18000ec00  or      eax, 0FFFFFFFFh
0x18000ec03  lock xadd [rbx+118h], eax
0x18000ec0b  cmp     eax, 1
0x18000ec0e  jnz     short loc_18000EC21
0x18000ec10  mov     rcx, rbx
0x18000ec13  call    ??1?$merged_data@U_tip_RtfFilterContentExtractionTipTest@@U1@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_RtfFilterContentExtractionTipTest,_tip_RtfFilterContentExtractionTipTest>::~merged_data<_tip_RtfFilterContentExtractionTipTest,_tip_RtfFilterContentExtractionTipTest>(void)
0x18000ec18  mov     rcx, rbx; pv
0x18000ec1b  call    cs:__imp_CoTaskMemFree
0x18000ec21  mov     rbx, [rsp+28h+arg_18]
0x18000ec26  mov     rax, rdi
0x18000ec29  add     rsp, 20h
0x18000ec2d  pop     rdi
0x18000ec2e  retn
```
