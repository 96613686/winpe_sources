# tip2::tip_test<tip2::details::merged_data<BugFix_49687435::TipTest::_tip_WlanDiscoveryProfileGenerationTest,BugFix_49687435::TipTest::_tip_WlanDiscoveryProfileGenerationTest>>::start(void)

- ea: `0x180061dc4`
- end: `0x180061e5f`
- name: `?start@?$tip_test@V?$merged_data@U_tip_WlanDiscoveryProfileGenerationTest@TipTest@BugFix_49687435@@U123@@details@tip2@@@tip2@@QEAA?AU_GUID@@XZ`
- size: `155`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18005e368`

## callees

- `0x18004fc98`
- `0x18005e3b0`
- `0x18005e72c`
- `0x18005fed8`
- `0x1800612d4`
- `0x180061c10`
- `0x180061dc4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180061dff`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180061dff`

## pseudocode

```c
__int64 __fastcall tip2::tip_test<tip2::details::merged_data<BugFix_49687435::TipTest::_tip_WlanDiscoveryProfileGenerationTest,BugFix_49687435::TipTest::_tip_WlanDiscoveryProfileGenerationTest>>::start(
        __int64 *a1,
        __int64 a2)
{
  _QWORD *v2; // rax
  LPVOID v5; // rax
  wil::details::in1diag3 *v6; // rcx
  __int64 v7; // rax
  void *v8; // rcx
  __int64 v10; // [rsp+30h] [rbp+8h] BYREF

  v2 = (_QWORD *)*a1;
  if ( *a1 && (v2[31] || (v2[9] & 0x100) != 0) )
    wil::com_ptr_t<tip2::details::merged_data<BugFix_49687435::TipTest::_tip_WlanDiscoveryProfileGenerationTest,BugFix_49687435::TipTest::_tip_WlanDiscoveryProfileGenerationTest>,wil::err_returncode_policy>::reset();
  if ( !*a1 )
  {
    v5 = CoTaskMemAlloc(0x138u);
    if ( !v5 )
      wil::details::in1diag3::_FailFastImmediate_Unexpected(v6);
    v7 = tip2::details::merged_data<BugFix_49687435::TipTest::_tip_WlanDiscoveryProfileGenerationTest,BugFix_49687435::TipTest::_tip_WlanDiscoveryProfileGenerationTest>::merged_data<BugFix_49687435::TipTest::_tip_WlanDiscoveryProfileGenerationTest,BugFix_49687435::TipTest::_tip_WlanDiscoveryProfileGenerationTest>(v5);
    v8 = (void *)*a1;
    v10 = 0;
    *a1 = v7;
    if ( v8 )
      tip2::details::merged_data<BugFix_49687435::TipTest::_tip_WlanDiscoveryProfileGenerationTest,BugFix_49687435::TipTest::_tip_WlanDiscoveryProfileGenerationTest>::Release(v8);
    wil::com_ptr_t<tip2::details::merged_data<BugFix_49687435::TipTest::_tip_WlanDiscoveryProfileGenerationTest,BugFix_49687435::TipTest::_tip_WlanDiscoveryProfileGenerationTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<BugFix_49687435::TipTest::_tip_WlanDiscoveryProfileGenerationTest,BugFix_49687435::TipTest::_tip_WlanDiscoveryProfileGenerationTest>,wil::err_returncode_policy>(&v10);
  }
  tip2::details::shared_data<0,0,0>::start(*a1 + 8, a2);
  return a2;
}

```

## disassembly

```asm
0x180061dc4  mov     [rsp+arg_8], rbx
0x180061dc9  push    rdi
0x180061dca  sub     rsp, 20h
0x180061dce  mov     rax, [rcx]
0x180061dd1  mov     rdi, rdx
0x180061dd4  mov     rbx, rcx
0x180061dd7  test    rax, rax
0x180061dda  jz      short loc_180061DF4
0x180061ddc  cmp     qword ptr [rax+0F8h], 0
0x180061de4  jnz     short loc_180061DEF
0x180061de6  test    dword ptr [rax+48h], 100h
0x180061ded  jz      short loc_180061DF4
0x180061def  call    ?reset@?$com_ptr_t@V?$merged_data@U_tip_WlanDiscoveryProfileGenerationTest@TipTest@BugFix_49687435@@U123@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<tip2::details::merged_data<BugFix_49687435::TipTest::_tip_WlanDiscoveryProfileGenerationTest,BugFix_49687435::TipTest::_tip_WlanDiscoveryProfileGenerationTest>,wil::err_returncode_policy>::reset(void)
0x180061df4  cmp     qword ptr [rbx], 0
0x180061df8  jnz     short loc_180061E41
0x180061dfa  mov     ecx, 138h; cb
0x180061dff  call    cs:__imp_CoTaskMemAlloc
0x180061e06  nop     dword ptr [rax+rax+00h]
0x180061e0b  test    rax, rax
0x180061e0e  jnz     short loc_180061E16
0x180061e10  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180061e16  mov     rcx, rax
0x180061e19  call    ??0?$merged_data@U_tip_WlanDiscoveryProfileGenerationTest@TipTest@BugFix_49687435@@U123@@details@tip2@@QEAA@XZ; tip2::details::merged_data<BugFix_49687435::TipTest::_tip_WlanDiscoveryProfileGenerationTest,BugFix_49687435::TipTest::_tip_WlanDiscoveryProfileGenerationTest>::merged_data<BugFix_49687435::TipTest::_tip_WlanDiscoveryProfileGenerationTest,BugFix_49687435::TipTest::_tip_WlanDiscoveryProfileGenerationTest>(void)
0x180061e1e  mov     rcx, [rbx]; pv
0x180061e21  mov     [rsp+28h+arg_0], 0
0x180061e2a  mov     [rbx], rax
0x180061e2d  test    rcx, rcx
0x180061e30  jz      short loc_180061E37
0x180061e32  call    ?Release@?$merged_data@U_tip_WlanDiscoveryProfileGenerationTest@TipTest@BugFix_49687435@@U123@@details@tip2@@AEAAKXZ; tip2::details::merged_data<BugFix_49687435::TipTest::_tip_WlanDiscoveryProfileGenerationTest,BugFix_49687435::TipTest::_tip_WlanDiscoveryProfileGenerationTest>::Release(void)
0x180061e37  lea     rcx, [rsp+28h+arg_0]
0x180061e3c  call    ??1?$com_ptr_t@V?$merged_data@U_tip_WlanDiscoveryProfileGenerationTest@TipTest@BugFix_49687435@@U123@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<BugFix_49687435::TipTest::_tip_WlanDiscoveryProfileGenerationTest,BugFix_49687435::TipTest::_tip_WlanDiscoveryProfileGenerationTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<BugFix_49687435::TipTest::_tip_WlanDiscoveryProfileGenerationTest,BugFix_49687435::TipTest::_tip_WlanDiscoveryProfileGenerationTest>,wil::err_returncode_policy>(void)
0x180061e41  mov     rcx, [rbx]
0x180061e44  mov     rdx, rdi
0x180061e47  add     rcx, 8
0x180061e4b  call    ?start@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAA?AU_GUID@@XZ; tip2::details::shared_data<0,0,0>::start(void)
0x180061e50  mov     rbx, [rsp+28h+arg_8]
0x180061e55  mov     rax, rdi
0x180061e58  add     rsp, 20h
0x180061e5c  pop     rdi
0x180061e5d  retn
```
