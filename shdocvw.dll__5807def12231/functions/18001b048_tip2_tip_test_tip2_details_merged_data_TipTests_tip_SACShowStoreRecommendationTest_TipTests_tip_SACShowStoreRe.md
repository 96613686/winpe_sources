# tip2::tip_test<tip2::details::merged_data<TipTests::_tip_SACShowStoreRecommendationTest,TipTests::_tip_SACShowStoreRecommendationTest>>::ensure_data(void)

- ea: `0x18001b048`
- end: `0x18001b0a1`
- name: `?ensure_data@?$tip_test@V?$merged_data@U_tip_SACShowStoreRecommendationTest@TipTests@@U12@@details@tip2@@@tip2@@AEBAAEAV?$com_ptr_t@V?$merged_data@U_tip_SACShowStoreRecommendationTest@TipTests@@U12@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ`
- size: `89`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18001d900`

## callees

- `0x18000c45c`
- `0x180014374`
- `0x180014bf4`
- `0x180018788`
- `0x18001b048`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001b05c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001b05c`

## pseudocode

```c
void **__fastcall tip2::tip_test<tip2::details::merged_data<TipTests::_tip_SACShowStoreRecommendationTest,TipTests::_tip_SACShowStoreRecommendationTest>>::ensure_data(
        void **a1)
{
  LPVOID v2; // rax
  wil::details::in1diag3 *v3; // rcx
  __int64 v4; // rax
  void *v5; // rcx
  __int64 v7; // [rsp+30h] [rbp+8h] BYREF

  if ( !*a1 )
  {
    v2 = CoTaskMemAlloc(0x120u);
    if ( !v2 )
      wil::details::in1diag3::_FailFastImmediate_Unexpected(v3);
    v4 = tip2::details::merged_data<TipTests::_tip_SACShowStoreRecommendationTest,TipTests::_tip_SACShowStoreRecommendationTest>::merged_data<TipTests::_tip_SACShowStoreRecommendationTest,TipTests::_tip_SACShowStoreRecommendationTest>(v2);
    v5 = *a1;
    v7 = 0;
    *a1 = (void *)v4;
    if ( v5 )
      tip2::details::merged_data<TipTests::_tip_SACShowStoreRecommendationTest,TipTests::_tip_SACShowStoreRecommendationTest>::Release(v5);
    wil::com_ptr_t<tip2::details::merged_data<TipTests::_tip_SACShowStoreRecommendationTest,TipTests::_tip_SACShowStoreRecommendationTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<TipTests::_tip_SACShowStoreRecommendationTest,TipTests::_tip_SACShowStoreRecommendationTest>,wil::err_returncode_policy>(&v7);
  }
  return a1;
}

```

## disassembly

```asm
0x18001b048  push    rbx
0x18001b04a  sub     rsp, 20h
0x18001b04e  cmp     qword ptr [rcx], 0
0x18001b052  mov     rbx, rcx
0x18001b055  jnz     short loc_18001B098
0x18001b057  mov     ecx, 120h; cb
0x18001b05c  call    cs:__imp_CoTaskMemAlloc
0x18001b062  test    rax, rax
0x18001b065  jnz     short loc_18001B06D
0x18001b067  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18001b06d  mov     rcx, rax
0x18001b070  call    ??0?$merged_data@U_tip_SACShowStoreRecommendationTest@TipTests@@U12@@details@tip2@@QEAA@XZ; tip2::details::merged_data<TipTests::_tip_SACShowStoreRecommendationTest,TipTests::_tip_SACShowStoreRecommendationTest>::merged_data<TipTests::_tip_SACShowStoreRecommendationTest,TipTests::_tip_SACShowStoreRecommendationTest>(void)
0x18001b075  mov     rcx, [rbx]; pv
0x18001b078  mov     [rsp+28h+arg_0], 0
0x18001b081  mov     [rbx], rax
0x18001b084  test    rcx, rcx
0x18001b087  jz      short loc_18001B08E
0x18001b089  call    ?Release@?$merged_data@U_tip_SACShowStoreRecommendationTest@TipTests@@U12@@details@tip2@@AEAAKXZ; tip2::details::merged_data<TipTests::_tip_SACShowStoreRecommendationTest,TipTests::_tip_SACShowStoreRecommendationTest>::Release(void)
0x18001b08e  lea     rcx, [rsp+28h+arg_0]
0x18001b093  call    ??1?$com_ptr_t@V?$merged_data@U_tip_SACShowStoreRecommendationTest@TipTests@@U12@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<TipTests::_tip_SACShowStoreRecommendationTest,TipTests::_tip_SACShowStoreRecommendationTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<TipTests::_tip_SACShowStoreRecommendationTest,TipTests::_tip_SACShowStoreRecommendationTest>,wil::err_returncode_policy>(void)
0x18001b098  mov     rax, rbx
0x18001b09b  add     rsp, 20h
0x18001b09f  pop     rbx
0x18001b0a0  retn
```
