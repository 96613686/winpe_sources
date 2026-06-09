# tip2::tip_test<tip2::details::merged_data<_tip_MruLookupTest,_tip_MruLookupTest>>::ensure_data(void)

- ea: `0x18002a52c`
- end: `0x18002a585`
- name: `?ensure_data@?$tip_test@V?$merged_data@U_tip_MruLookupTest@@U1@@details@tip2@@@tip2@@AEBAAEAV?$com_ptr_t@V?$merged_data@U_tip_MruLookupTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ`
- size: `89`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180005598`
- `0x1800294d4`

## callees

- `0x1800177c8`
- `0x180028e4c`
- `0x1800291dc`
- `0x1800298f0`
- `0x18002a52c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002a540`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002a540`

## pseudocode

```c
void **__fastcall tip2::tip_test<tip2::details::merged_data<_tip_MruLookupTest,_tip_MruLookupTest>>::ensure_data(
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
    v4 = tip2::details::merged_data<_tip_MruLookupTest,_tip_MruLookupTest>::merged_data<_tip_MruLookupTest,_tip_MruLookupTest>(v2);
    v5 = *a1;
    v7 = 0;
    *a1 = (void *)v4;
    if ( v5 )
      tip2::details::merged_data<_tip_MruLookupTest,_tip_MruLookupTest>::Release(v5);
    wil::com_ptr_t<tip2::details::merged_data<_tip_MruLookupTest,_tip_MruLookupTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_MruLookupTest,_tip_MruLookupTest>,wil::err_returncode_policy>(&v7);
  }
  return a1;
}

```

## disassembly

```asm
0x18002a52c  push    rbx
0x18002a52e  sub     rsp, 20h
0x18002a532  cmp     qword ptr [rcx], 0
0x18002a536  mov     rbx, rcx
0x18002a539  jnz     short loc_18002A576
0x18002a53b  mov     ecx, 120h; cb
0x18002a540  call    cs:__imp_CoTaskMemAlloc
0x18002a546  test    rax, rax
0x18002a549  jz      short loc_18002A57F
0x18002a54b  mov     rcx, rax
0x18002a54e  call    ??0?$merged_data@U_tip_MruLookupTest@@U1@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_MruLookupTest,_tip_MruLookupTest>::merged_data<_tip_MruLookupTest,_tip_MruLookupTest>(void)
0x18002a553  mov     rcx, [rbx]; pv
0x18002a556  mov     [rsp+28h+arg_0], 0
0x18002a55f  mov     [rbx], rax
0x18002a562  test    rcx, rcx
0x18002a565  jz      short loc_18002A56C
0x18002a567  call    ?Release@?$merged_data@U_tip_MruLookupTest@@U1@@details@tip2@@AEAAKXZ; tip2::details::merged_data<_tip_MruLookupTest,_tip_MruLookupTest>::Release(void)
0x18002a56c  lea     rcx, [rsp+28h+arg_0]
0x18002a571  call    ??1?$com_ptr_t@V?$merged_data@U_tip_MruLookupTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_MruLookupTest,_tip_MruLookupTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_MruLookupTest,_tip_MruLookupTest>,wil::err_returncode_policy>(void)
0x18002a576  mov     rax, rbx
0x18002a579  add     rsp, 20h
0x18002a57d  pop     rbx
0x18002a57e  retn
0x18002a57f  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
