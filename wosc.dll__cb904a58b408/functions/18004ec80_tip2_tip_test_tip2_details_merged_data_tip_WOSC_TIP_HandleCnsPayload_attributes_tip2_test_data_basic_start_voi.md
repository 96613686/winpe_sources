# tip2::tip_test<tip2::details::merged_data<_tip_WOSC_TIP_HandleCnsPayload_attributes,tip2::test_data_basic>>::start(void)

- ea: `0x18004ec80`
- end: `0x18004ed18`
- name: `?start@?$tip_test@V?$merged_data@U_tip_WOSC_TIP_HandleCnsPayload_attributes@@Vtest_data_basic@tip2@@@details@tip2@@@tip2@@QEAA?AU_GUID@@XZ`
- size: `152`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18004b49c`

## callees

- `0x180009ff0`
- `0x18000da20`
- `0x18000ff18`
- `0x180011004`
- `0x18001247c`
- `0x18004b508`
- `0x18004ec80`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18004ecbf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18004ecbf`

## pseudocode

```c
__int64 __fastcall tip2::tip_test<tip2::details::merged_data<_tip_WOSC_TIP_HandleCnsPayload_attributes,tip2::test_data_basic>>::start(
        __int64 *a1,
        __int64 a2)
{
  volatile signed __int32 *v4; // r8
  LPVOID v5; // rax
  wil::details::in1diag3 *v6; // rcx
  __int64 v7; // rax
  volatile signed __int32 *v8; // rcx
  void *v10; // [rsp+30h] [rbp+8h] BYREF

  if ( *a1 && (unsigned __int8)tip2::details::shared_data<0,0,1>::has_ever_started(*a1 + 8) )
  {
    *a1 = 0;
    tip2::details::merged_data<_tip_WOSC_TIP_CnsMergeWithOneSettings_attributes,tip2::test_data_basic>::Release(v4);
  }
  if ( !*a1 )
  {
    v5 = CoTaskMemAlloc(0x158u);
    if ( !v5 )
      wil::details::in1diag3::FailFastImmediate_Unexpected(v6);
    v7 = tip2::details::merged_data<_tip_WOSC_TIP_HandleCnsPayload_attributes,tip2::test_data_basic>::merged_data<_tip_WOSC_TIP_HandleCnsPayload_attributes,tip2::test_data_basic>(v5);
    v8 = (volatile signed __int32 *)*a1;
    v10 = 0;
    *a1 = v7;
    if ( v8 )
      tip2::details::merged_data<_tip_WOSC_TIP_CnsMergeWithOneSettings_attributes,tip2::test_data_basic>::Release(v8);
    wil::com_ptr_t<tip2::details::merged_data<_tip_WOSC_ForceRefreshOneSettings_attributes,tip2::test_data_basic>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WOSC_ForceRefreshOneSettings_attributes,tip2::test_data_basic>,wil::err_returncode_policy>(&v10);
  }
  tip2::details::shared_data<0,0,1>::start(*a1 + 8, a2);
  return a2;
}

```

## disassembly

```asm
0x18004ec80  mov     [rsp+arg_8], rbx
0x18004ec85  push    rdi
0x18004ec86  sub     rsp, 20h
0x18004ec8a  mov     r8, [rcx]
0x18004ec8d  mov     rdi, rdx
0x18004ec90  mov     rbx, rcx
0x18004ec93  test    r8, r8
0x18004ec96  jz      short loc_18004ECB4
0x18004ec98  lea     rcx, [r8+8]
0x18004ec9c  call    ?has_ever_started@?$shared_data@$0A@$0A@$00@details@tip2@@AEAA_NXZ; tip2::details::shared_data<0,0,1>::has_ever_started(void)
0x18004eca1  test    al, al
0x18004eca3  jz      short loc_18004ECB4
0x18004eca5  mov     rcx, r8; pv
0x18004eca8  mov     qword ptr [rbx], 0
0x18004ecaf  call    ?Release@?$merged_data@U_tip_WOSC_TIP_CnsMergeWithOneSettings_attributes@@Vtest_data_basic@tip2@@@details@tip2@@AEAAKXZ; tip2::details::merged_data<_tip_WOSC_TIP_CnsMergeWithOneSettings_attributes,tip2::test_data_basic>::Release(void)
0x18004ecb4  cmp     qword ptr [rbx], 0
0x18004ecb8  jnz     short loc_18004ECF5
0x18004ecba  mov     ecx, 158h; cb
0x18004ecbf  call    cs:__imp_CoTaskMemAlloc
0x18004ecc5  test    rax, rax
0x18004ecc8  jz      short loc_18004ED12
0x18004ecca  mov     rcx, rax
0x18004eccd  call    ??0?$merged_data@U_tip_WOSC_TIP_HandleCnsPayload_attributes@@Vtest_data_basic@tip2@@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_WOSC_TIP_HandleCnsPayload_attributes,tip2::test_data_basic>::merged_data<_tip_WOSC_TIP_HandleCnsPayload_attributes,tip2::test_data_basic>(void)
0x18004ecd2  mov     rcx, [rbx]; pv
0x18004ecd5  mov     [rsp+28h+arg_0], 0
0x18004ecde  mov     [rbx], rax
0x18004ece1  test    rcx, rcx
0x18004ece4  jz      short loc_18004ECEB
0x18004ece6  call    ?Release@?$merged_data@U_tip_WOSC_TIP_CnsMergeWithOneSettings_attributes@@Vtest_data_basic@tip2@@@details@tip2@@AEAAKXZ; tip2::details::merged_data<_tip_WOSC_TIP_CnsMergeWithOneSettings_attributes,tip2::test_data_basic>::Release(void)
0x18004eceb  lea     rcx, [rsp+28h+arg_0]
0x18004ecf0  call    ??1?$com_ptr_t@V?$merged_data@U_tip_WOSC_ForceRefreshOneSettings_attributes@@Vtest_data_basic@tip2@@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_WOSC_ForceRefreshOneSettings_attributes,tip2::test_data_basic>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WOSC_ForceRefreshOneSettings_attributes,tip2::test_data_basic>,wil::err_returncode_policy>(void)
0x18004ecf5  mov     rcx, [rbx]
0x18004ecf8  mov     rdx, rdi
0x18004ecfb  add     rcx, 8
0x18004ecff  call    ?start@?$shared_data@$0A@$0A@$00@details@tip2@@AEAA?AU_GUID@@XZ; tip2::details::shared_data<0,0,1>::start(void)
0x18004ed04  mov     rbx, [rsp+28h+arg_8]
0x18004ed09  mov     rax, rdi
0x18004ed0c  add     rsp, 20h
0x18004ed10  pop     rdi
0x18004ed11  retn
0x18004ed12  call    ?FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::FailFastImmediate_Unexpected(void)
```
