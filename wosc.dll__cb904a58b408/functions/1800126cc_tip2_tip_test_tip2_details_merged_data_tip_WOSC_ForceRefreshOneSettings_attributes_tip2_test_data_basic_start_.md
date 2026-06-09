# tip2::tip_test<tip2::details::merged_data<_tip_WOSC_ForceRefreshOneSettings_attributes,tip2::test_data_basic>>::start(void)

- ea: `0x1800126cc`
- end: `0x180012764`
- name: `?start@?$tip_test@V?$merged_data@U_tip_WOSC_ForceRefreshOneSettings_attributes@@Vtest_data_basic@tip2@@@details@tip2@@@tip2@@QEAA?AU_GUID@@XZ`
- size: `152`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000b3f0`

## callees

- `0x180009724`
- `0x180009ff0`
- `0x18000da20`
- `0x18000ff18`
- `0x180011004`
- `0x18001247c`
- `0x1800126cc`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001270b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001270b`

## pseudocode

```c
__int64 __fastcall tip2::tip_test<tip2::details::merged_data<_tip_WOSC_ForceRefreshOneSettings_attributes,tip2::test_data_basic>>::start(
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
    v7 = tip2::details::merged_data<_tip_WOSC_ForceRefreshOneSettings_attributes,tip2::test_data_basic>::merged_data<_tip_WOSC_ForceRefreshOneSettings_attributes,tip2::test_data_basic>(v5);
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
0x1800126cc  mov     [rsp+arg_8], rbx
0x1800126d1  push    rdi
0x1800126d2  sub     rsp, 20h
0x1800126d6  mov     r8, [rcx]
0x1800126d9  mov     rdi, rdx
0x1800126dc  mov     rbx, rcx
0x1800126df  test    r8, r8
0x1800126e2  jz      short loc_180012700
0x1800126e4  lea     rcx, [r8+8]
0x1800126e8  call    ?has_ever_started@?$shared_data@$0A@$0A@$00@details@tip2@@AEAA_NXZ; tip2::details::shared_data<0,0,1>::has_ever_started(void)
0x1800126ed  test    al, al
0x1800126ef  jz      short loc_180012700
0x1800126f1  mov     rcx, r8; pv
0x1800126f4  mov     qword ptr [rbx], 0
0x1800126fb  call    ?Release@?$merged_data@U_tip_WOSC_TIP_CnsMergeWithOneSettings_attributes@@Vtest_data_basic@tip2@@@details@tip2@@AEAAKXZ; tip2::details::merged_data<_tip_WOSC_TIP_CnsMergeWithOneSettings_attributes,tip2::test_data_basic>::Release(void)
0x180012700  cmp     qword ptr [rbx], 0
0x180012704  jnz     short loc_180012741
0x180012706  mov     ecx, 158h; cb
0x18001270b  call    cs:__imp_CoTaskMemAlloc
0x180012711  test    rax, rax
0x180012714  jz      short loc_18001275E
0x180012716  mov     rcx, rax
0x180012719  call    ??0?$merged_data@U_tip_WOSC_ForceRefreshOneSettings_attributes@@Vtest_data_basic@tip2@@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_WOSC_ForceRefreshOneSettings_attributes,tip2::test_data_basic>::merged_data<_tip_WOSC_ForceRefreshOneSettings_attributes,tip2::test_data_basic>(void)
0x18001271e  mov     rcx, [rbx]; pv
0x180012721  mov     [rsp+28h+arg_0], 0
0x18001272a  mov     [rbx], rax
0x18001272d  test    rcx, rcx
0x180012730  jz      short loc_180012737
0x180012732  call    ?Release@?$merged_data@U_tip_WOSC_TIP_CnsMergeWithOneSettings_attributes@@Vtest_data_basic@tip2@@@details@tip2@@AEAAKXZ; tip2::details::merged_data<_tip_WOSC_TIP_CnsMergeWithOneSettings_attributes,tip2::test_data_basic>::Release(void)
0x180012737  lea     rcx, [rsp+28h+arg_0]
0x18001273c  call    ??1?$com_ptr_t@V?$merged_data@U_tip_WOSC_ForceRefreshOneSettings_attributes@@Vtest_data_basic@tip2@@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_WOSC_ForceRefreshOneSettings_attributes,tip2::test_data_basic>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WOSC_ForceRefreshOneSettings_attributes,tip2::test_data_basic>,wil::err_returncode_policy>(void)
0x180012741  mov     rcx, [rbx]
0x180012744  mov     rdx, rdi
0x180012747  add     rcx, 8
0x18001274b  call    ?start@?$shared_data@$0A@$0A@$00@details@tip2@@AEAA?AU_GUID@@XZ; tip2::details::shared_data<0,0,1>::start(void)
0x180012750  mov     rbx, [rsp+28h+arg_8]
0x180012755  mov     rax, rdi
0x180012758  add     rsp, 20h
0x18001275c  pop     rdi
0x18001275d  retn
0x18001275e  call    ?FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::FailFastImmediate_Unexpected(void)
```
