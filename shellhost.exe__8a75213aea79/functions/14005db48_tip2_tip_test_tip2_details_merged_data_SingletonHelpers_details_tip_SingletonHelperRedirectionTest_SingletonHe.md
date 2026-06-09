# tip2::tip_test<tip2::details::merged_data<SingletonHelpers::details::_tip_SingletonHelperRedirectionTest,SingletonHelpers::details::_tip_SingletonHelperRedirectionTest>>::ensure_data(void)

- ea: `0x14005db48`
- end: `0x14005dba1`
- name: `?ensure_data@?$tip_test@V?$merged_data@U_tip_SingletonHelperRedirectionTest@details@SingletonHelpers@@U123@@details@tip2@@@tip2@@AEBAAEAV?$com_ptr_t@V?$merged_data@U_tip_SingletonHelperRedirectionTest@details@SingletonHelpers@@U123@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ`
- size: `89`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x140053a4c`
- `0x14005b34c`

## callees

- `0x14004a824`
- `0x1400520f4`
- `0x140052d90`
- `0x14005a3b8`
- `0x14005db48`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14005db5c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14005db5c`

## pseudocode

```c
void **__fastcall tip2::tip_test<tip2::details::merged_data<SingletonHelpers::details::_tip_SingletonHelperRedirectionTest,SingletonHelpers::details::_tip_SingletonHelperRedirectionTest>>::ensure_data(
        void **a1)
{
  LPVOID v2; // rax
  wil::details::in1diag3 *v3; // rcx
  __int64 v4; // rax
  void *v5; // rcx
  __int64 v7; // [rsp+30h] [rbp+8h] BYREF

  if ( !*a1 )
  {
    v2 = CoTaskMemAlloc(0x140u);
    if ( !v2 )
      wil::details::in1diag3::_FailFastImmediate_Unexpected(v3);
    v4 = tip2::details::merged_data<SingletonHelpers::details::_tip_SingletonHelperRedirectionTest,SingletonHelpers::details::_tip_SingletonHelperRedirectionTest>::merged_data<SingletonHelpers::details::_tip_SingletonHelperRedirectionTest,SingletonHelpers::details::_tip_SingletonHelperRedirectionTest>(v2);
    v5 = *a1;
    v7 = 0;
    *a1 = (void *)v4;
    if ( v5 )
      tip2::details::merged_data<SingletonHelpers::details::_tip_SingletonHelperRedirectionTest,SingletonHelpers::details::_tip_SingletonHelperRedirectionTest>::Release(v5);
    wil::com_ptr_t<tip2::details::merged_data<SingletonHelpers::details::_tip_SingletonHelperRedirectionTest,SingletonHelpers::details::_tip_SingletonHelperRedirectionTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<SingletonHelpers::details::_tip_SingletonHelperRedirectionTest,SingletonHelpers::details::_tip_SingletonHelperRedirectionTest>,wil::err_returncode_policy>(&v7);
  }
  return a1;
}

```

## disassembly

```asm
0x14005db48  push    rbx
0x14005db4a  sub     rsp, 20h
0x14005db4e  cmp     qword ptr [rcx], 0
0x14005db52  mov     rbx, rcx
0x14005db55  jnz     short loc_14005DB98
0x14005db57  mov     ecx, 140h; cb
0x14005db5c  call    cs:__imp_CoTaskMemAlloc
0x14005db62  test    rax, rax
0x14005db65  jnz     short loc_14005DB6D
0x14005db67  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x14005db6d  mov     rcx, rax
0x14005db70  call    ??0?$merged_data@U_tip_SingletonHelperRedirectionTest@details@SingletonHelpers@@U123@@details@tip2@@QEAA@XZ; tip2::details::merged_data<SingletonHelpers::details::_tip_SingletonHelperRedirectionTest,SingletonHelpers::details::_tip_SingletonHelperRedirectionTest>::merged_data<SingletonHelpers::details::_tip_SingletonHelperRedirectionTest,SingletonHelpers::details::_tip_SingletonHelperRedirectionTest>(void)
0x14005db75  mov     rcx, [rbx]; pv
0x14005db78  mov     [rsp+28h+arg_0], 0
0x14005db81  mov     [rbx], rax
0x14005db84  test    rcx, rcx
0x14005db87  jz      short loc_14005DB8E
0x14005db89  call    ?Release@?$merged_data@U_tip_SingletonHelperRedirectionTest@details@SingletonHelpers@@U123@@details@tip2@@AEAAKXZ; tip2::details::merged_data<SingletonHelpers::details::_tip_SingletonHelperRedirectionTest,SingletonHelpers::details::_tip_SingletonHelperRedirectionTest>::Release(void)
0x14005db8e  lea     rcx, [rsp+28h+arg_0]
0x14005db93  call    ??1?$com_ptr_t@V?$merged_data@U_tip_SingletonHelperRedirectionTest@details@SingletonHelpers@@U123@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<SingletonHelpers::details::_tip_SingletonHelperRedirectionTest,SingletonHelpers::details::_tip_SingletonHelperRedirectionTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<SingletonHelpers::details::_tip_SingletonHelperRedirectionTest,SingletonHelpers::details::_tip_SingletonHelperRedirectionTest>,wil::err_returncode_policy>(void)
0x14005db98  mov     rax, rbx
0x14005db9b  add     rsp, 20h
0x14005db9f  pop     rbx
0x14005dba0  retn
```
