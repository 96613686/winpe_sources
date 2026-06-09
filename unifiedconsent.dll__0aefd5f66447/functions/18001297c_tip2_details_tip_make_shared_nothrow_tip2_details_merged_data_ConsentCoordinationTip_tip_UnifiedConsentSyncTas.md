# tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<ConsentCoordinationTip::_tip_UnifiedConsentSyncTaskTipTest,ConsentCoordinationTip::_tip_UnifiedConsentSyncTaskTipTest>,>(void)

- ea: `0x18001297c`
- end: `0x180012a42`
- name: `??$tip_make_shared_nothrow@V?$merged_data@U_tip_UnifiedConsentSyncTaskTipTest@ConsentCoordinationTip@@U12@@details@tip2@@$$V@details@tip2@@YA?AV?$com_ptr_t@V?$merged_data@U_tip_UnifiedConsentSyncTaskTipTest@ConsentCoordinationTip@@U12@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ`
- size: `198`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x180012870`

## callees

- `0x18000e434`
- `0x18001297c`
- `0x180012fe8`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001298e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001298e`

## string_xrefs

- `0x1800129bd`: `UnifiedConsentSyncTaskTipTest`

## pseudocode

```c
_QWORD *__fastcall tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<ConsentCoordinationTip::_tip_UnifiedConsentSyncTaskTipTest,ConsentCoordinationTip::_tip_UnifiedConsentSyncTaskTipTest>,>(
        _QWORD *a1)
{
  _QWORD *v2; // rax
  wil::details::in1diag3 *v3; // rcx
  _QWORD *v4; // rbx
  _QWORD *result; // rax
  _DWORD v6[2]; // [rsp+20h] [rbp-38h] BYREF
  const char *v7; // [rsp+28h] [rbp-30h]
  __int16 v8; // [rsp+30h] [rbp-28h]
  int v9; // [rsp+32h] [rbp-26h]
  __int16 v10; // [rsp+36h] [rbp-22h]
  __int128 v11; // [rsp+38h] [rbp-20h]
  __int64 v12; // [rsp+48h] [rbp-10h]

  v2 = CoTaskMemAlloc(0x128u);
  v4 = v2;
  if ( !v2 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v3);
  v6[0] = 44958737;
  v9 = 0;
  *v2 = &tip2::details::test_data_interface::`vftable';
  v10 = 0;
  v12 = 0;
  v7 = "UnifiedConsentSyncTaskTipTest";
  v6[1] = 49408;
  v8 = 1793;
  v11 = 0;
  tip2::details::shared_data<0,0,0>::shared_data<0,0,0>(v2 + 1, v2, v6);
  v4[34] = 0x10000;
  *v4 = &tip2::details::merged_data<ConsentCoordinationTip::_tip_UnifiedConsentSyncTaskTipTest,ConsentCoordinationTip::_tip_UnifiedConsentSyncTaskTipTest>::`vftable';
  v4[33] = v4 + 2;
  result = a1;
  *((_DWORD *)v4 + 70) = 65537;
  *((_DWORD *)v4 + 72) = 1;
  *a1 = v4;
  return result;
}

```

## disassembly

```asm
0x18001297c  mov     [rsp+arg_0], rbx
0x180012981  push    rdi
0x180012982  sub     rsp, 50h
0x180012986  mov     rdi, rcx
0x180012989  mov     ecx, 128h; cb
0x18001298e  call    cs:__imp_CoTaskMemAlloc
0x180012994  mov     rbx, rax
0x180012997  test    rax, rax
0x18001299a  jz      loc_180012A3C
0x1800129a0  xor     ecx, ecx
0x1800129a2  mov     [rsp+58h+var_38], 2AE0411h
0x1800129aa  lea     rax, ??_7test_data_interface@details@tip2@@6B@; const tip2::details::test_data_interface::`vftable'
0x1800129b1  mov     [rsp+58h+var_26], ecx
0x1800129b5  mov     [rbx], rax
0x1800129b8  lea     r8, [rsp+58h+var_38]
0x1800129bd  lea     rax, aUnifiedconsent_4; "UnifiedConsentSyncTaskTipTest"
0x1800129c4  mov     [rsp+58h+var_22], cx
0x1800129c9  xorps   xmm0, xmm0
0x1800129cc  mov     [rsp+58h+var_10], rcx
0x1800129d1  lea     rcx, [rbx+8]
0x1800129d5  mov     [rsp+58h+var_30], rax
0x1800129da  mov     rdx, rbx
0x1800129dd  mov     [rsp+58h+var_34], 0C100h
0x1800129e5  mov     [rsp+58h+var_28], 701h
0x1800129ec  movdqu  [rsp+58h+var_20], xmm0
0x1800129f2  call    ??0?$shared_data@$0A@$0A@$0A@@details@tip2@@QEAA@AEAUtest_data_interface@12@AEBUtest_info@2@@Z; tip2::details::shared_data<0,0,0>::shared_data<0,0,0>(tip2::details::test_data_interface &,tip2::test_info const &)
0x1800129f7  lea     rax, ??_7?$merged_data@U_tip_UnifiedConsentSyncTaskTipTest@ConsentCoordinationTip@@U12@@details@tip2@@6B@; const tip2::details::merged_data<ConsentCoordinationTip::_tip_UnifiedConsentSyncTaskTipTest,ConsentCoordinationTip::_tip_UnifiedConsentSyncTaskTipTest>::`vftable'
0x1800129fe  mov     qword ptr [rbx+110h], 10000h
0x180012a09  mov     [rbx], rax
0x180012a0c  lea     rax, [rbx+10h]
0x180012a10  mov     [rbx+108h], rax
0x180012a17  mov     rax, rdi
0x180012a1a  mov     dword ptr [rbx+118h], 10001h
0x180012a24  mov     dword ptr [rbx+120h], 1
0x180012a2e  mov     [rdi], rbx
0x180012a31  mov     rbx, [rsp+58h+arg_0]
0x180012a36  add     rsp, 50h
0x180012a3a  pop     rdi
0x180012a3b  retn
0x180012a3c  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
