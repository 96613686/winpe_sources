# tip2::tip_test<tip2::details::merged_data<_tip_PidlNormalizationTest,_tip_PidlNormalizationTest>>::ensure_data(void)

- ea: `0x18002a58c`
- end: `0x18002a5e5`
- name: `?ensure_data@?$tip_test@V?$merged_data@U_tip_PidlNormalizationTest@@U1@@details@tip2@@@tip2@@AEBAAEAV?$com_ptr_t@V?$merged_data@U_tip_PidlNormalizationTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ`
- size: `89`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000f430`
- `0x180029510`

## callees

- `0x1800177c8`
- `0x180028ee8`
- `0x1800291f8`
- `0x180029930`
- `0x18002a58c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002a5a0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002a5a0`

## pseudocode

```c
void **__fastcall tip2::tip_test<tip2::details::merged_data<_tip_PidlNormalizationTest,_tip_PidlNormalizationTest>>::ensure_data(
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
    v4 = tip2::details::merged_data<_tip_PidlNormalizationTest,_tip_PidlNormalizationTest>::merged_data<_tip_PidlNormalizationTest,_tip_PidlNormalizationTest>(v2);
    v5 = *a1;
    v7 = 0;
    *a1 = (void *)v4;
    if ( v5 )
      tip2::details::merged_data<_tip_PidlNormalizationTest,_tip_PidlNormalizationTest>::Release(v5);
    wil::com_ptr_t<tip2::details::merged_data<_tip_PidlNormalizationTest,_tip_PidlNormalizationTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_PidlNormalizationTest,_tip_PidlNormalizationTest>,wil::err_returncode_policy>(&v7);
  }
  return a1;
}

```

## disassembly

```asm
0x18002a58c  push    rbx
0x18002a58e  sub     rsp, 20h
0x18002a592  cmp     qword ptr [rcx], 0
0x18002a596  mov     rbx, rcx
0x18002a599  jnz     short loc_18002A5D6
0x18002a59b  mov     ecx, 120h; cb
0x18002a5a0  call    cs:__imp_CoTaskMemAlloc
0x18002a5a6  test    rax, rax
0x18002a5a9  jz      short loc_18002A5DF
0x18002a5ab  mov     rcx, rax
0x18002a5ae  call    ??0?$merged_data@U_tip_PidlNormalizationTest@@U1@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_PidlNormalizationTest,_tip_PidlNormalizationTest>::merged_data<_tip_PidlNormalizationTest,_tip_PidlNormalizationTest>(void)
0x18002a5b3  mov     rcx, [rbx]; pv
0x18002a5b6  mov     [rsp+28h+arg_0], 0
0x18002a5bf  mov     [rbx], rax
0x18002a5c2  test    rcx, rcx
0x18002a5c5  jz      short loc_18002A5CC
0x18002a5c7  call    ?Release@?$merged_data@U_tip_PidlNormalizationTest@@U1@@details@tip2@@AEAAKXZ; tip2::details::merged_data<_tip_PidlNormalizationTest,_tip_PidlNormalizationTest>::Release(void)
0x18002a5cc  lea     rcx, [rsp+28h+arg_0]
0x18002a5d1  call    ??1?$com_ptr_t@V?$merged_data@U_tip_PidlNormalizationTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_PidlNormalizationTest,_tip_PidlNormalizationTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_PidlNormalizationTest,_tip_PidlNormalizationTest>,wil::err_returncode_policy>(void)
0x18002a5d6  mov     rax, rbx
0x18002a5d9  add     rsp, 20h
0x18002a5dd  pop     rbx
0x18002a5de  retn
0x18002a5df  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
