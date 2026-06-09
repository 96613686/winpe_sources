# tip2::tip_test<tip2::details::merged_data<_tip_WOSC_ForceRefreshOneSettingsCtacOverrides_attributes,tip2::test_data_basic>>::start(void)

- ea: `0x18001262c`
- end: `0x1800126c4`
- name: `?start@?$tip_test@V?$merged_data@U_tip_WOSC_ForceRefreshOneSettingsCtacOverrides_attributes@@Vtest_data_basic@tip2@@@details@tip2@@@tip2@@QEAA?AU_GUID@@XZ`
- size: `152`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000b5d0`

## callees

- `0x180009630`
- `0x180009ff0`
- `0x18000da20`
- `0x18000ff18`
- `0x180011004`
- `0x18001247c`
- `0x18001262c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001266b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001266b`

## pseudocode

```c
__int64 __fastcall tip2::tip_test<tip2::details::merged_data<_tip_WOSC_ForceRefreshOneSettingsCtacOverrides_attributes,tip2::test_data_basic>>::start(
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
    v7 = tip2::details::merged_data<_tip_WOSC_ForceRefreshOneSettingsCtacOverrides_attributes,tip2::test_data_basic>::merged_data<_tip_WOSC_ForceRefreshOneSettingsCtacOverrides_attributes,tip2::test_data_basic>(v5);
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
0x18001262c  mov     [rsp+arg_8], rbx
0x180012631  push    rdi
0x180012632  sub     rsp, 20h
0x180012636  mov     r8, [rcx]
0x180012639  mov     rdi, rdx
0x18001263c  mov     rbx, rcx
0x18001263f  test    r8, r8
0x180012642  jz      short loc_180012660
0x180012644  lea     rcx, [r8+8]
0x180012648  call    ?has_ever_started@?$shared_data@$0A@$0A@$00@details@tip2@@AEAA_NXZ; tip2::details::shared_data<0,0,1>::has_ever_started(void)
0x18001264d  test    al, al
0x18001264f  jz      short loc_180012660
0x180012651  mov     rcx, r8; pv
0x180012654  mov     qword ptr [rbx], 0
0x18001265b  call    ?Release@?$merged_data@U_tip_WOSC_TIP_CnsMergeWithOneSettings_attributes@@Vtest_data_basic@tip2@@@details@tip2@@AEAAKXZ; tip2::details::merged_data<_tip_WOSC_TIP_CnsMergeWithOneSettings_attributes,tip2::test_data_basic>::Release(void)
0x180012660  cmp     qword ptr [rbx], 0
0x180012664  jnz     short loc_1800126A1
0x180012666  mov     ecx, 158h; cb
0x18001266b  call    cs:__imp_CoTaskMemAlloc
0x180012671  test    rax, rax
0x180012674  jz      short loc_1800126BE
0x180012676  mov     rcx, rax
0x180012679  call    ??0?$merged_data@U_tip_WOSC_ForceRefreshOneSettingsCtacOverrides_attributes@@Vtest_data_basic@tip2@@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_WOSC_ForceRefreshOneSettingsCtacOverrides_attributes,tip2::test_data_basic>::merged_data<_tip_WOSC_ForceRefreshOneSettingsCtacOverrides_attributes,tip2::test_data_basic>(void)
0x18001267e  mov     rcx, [rbx]; pv
0x180012681  mov     [rsp+28h+arg_0], 0
0x18001268a  mov     [rbx], rax
0x18001268d  test    rcx, rcx
0x180012690  jz      short loc_180012697
0x180012692  call    ?Release@?$merged_data@U_tip_WOSC_TIP_CnsMergeWithOneSettings_attributes@@Vtest_data_basic@tip2@@@details@tip2@@AEAAKXZ; tip2::details::merged_data<_tip_WOSC_TIP_CnsMergeWithOneSettings_attributes,tip2::test_data_basic>::Release(void)
0x180012697  lea     rcx, [rsp+28h+arg_0]
0x18001269c  call    ??1?$com_ptr_t@V?$merged_data@U_tip_WOSC_ForceRefreshOneSettings_attributes@@Vtest_data_basic@tip2@@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_WOSC_ForceRefreshOneSettings_attributes,tip2::test_data_basic>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WOSC_ForceRefreshOneSettings_attributes,tip2::test_data_basic>,wil::err_returncode_policy>(void)
0x1800126a1  mov     rcx, [rbx]
0x1800126a4  mov     rdx, rdi
0x1800126a7  add     rcx, 8
0x1800126ab  call    ?start@?$shared_data@$0A@$0A@$00@details@tip2@@AEAA?AU_GUID@@XZ; tip2::details::shared_data<0,0,1>::start(void)
0x1800126b0  mov     rbx, [rsp+28h+arg_8]
0x1800126b5  mov     rax, rdi
0x1800126b8  add     rsp, 20h
0x1800126bc  pop     rdi
0x1800126bd  retn
0x1800126be  call    ?FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::FailFastImmediate_Unexpected(void)
```
