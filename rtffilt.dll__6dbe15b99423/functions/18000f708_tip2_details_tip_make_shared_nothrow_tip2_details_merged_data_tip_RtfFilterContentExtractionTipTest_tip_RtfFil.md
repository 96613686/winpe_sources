# tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<_tip_RtfFilterContentExtractionTipTest,_tip_RtfFilterContentExtractionTipTest>,_GUID * &>(_GUID * &)

- ea: `0x18000f708`
- end: `0x18000f7d3`
- name: `??$tip_make_shared_nothrow@V?$merged_data@U_tip_RtfFilterContentExtractionTipTest@@U1@@details@tip2@@AEAPEAU_GUID@@@details@tip2@@YA?AV?$com_ptr_t@V?$merged_data@U_tip_RtfFilterContentExtractionTipTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@AEAPEAU_GUID@@@Z`
- size: `203`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000eb50`

## callees

- `0x18000c558`
- `0x18000f708`
- `0x18000f904`
- `0x18001779c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000f71d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000f71d`

## pseudocode

```c
_QWORD *__fastcall tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<_tip_RtfFilterContentExtractionTipTest,_tip_RtfFilterContentExtractionTipTest>,_GUID * &>(
        _QWORD *a1,
        __int64 *a2)
{
  _QWORD *v4; // rax
  wil::details::in1diag3 *v5; // rcx
  _QWORD *v6; // rsi
  __int64 v7; // rdi
  __int64 v8; // r8
  _QWORD *result; // rax
  _DWORD v10[2]; // [rsp+20h] [rbp-58h] BYREF
  const char *v11; // [rsp+28h] [rbp-50h]
  __int16 v12; // [rsp+30h] [rbp-48h]
  int v13; // [rsp+32h] [rbp-46h]
  __int16 v14; // [rsp+36h] [rbp-42h]
  __int128 v15; // [rsp+38h] [rbp-40h]
  __int64 v16; // [rsp+48h] [rbp-30h]

  v4 = CoTaskMemAlloc(0x120u);
  v6 = v4;
  if ( !v4 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v5);
  v7 = *a2;
  *v4 = &tip2::details::test_data_interface::`vftable';
  v13 = 0;
  v14 = 0;
  v16 = 0;
  v11 = "RtfFilterContentExtractionTipTest";
  v10[0] = 52974008;
  v10[1] = 16645;
  v12 = 257;
  v15 = 0;
  tip2::details::shared_data<1,0,0>::shared_data<1,0,0>(v4 + 1, v4, v10);
  *((_WORD *)v6 + 136) = 0;
  *v6 = &tip2::details::merged_data<_tip_RtfFilterContentExtractionTipTest,_tip_RtfFilterContentExtractionTipTest>::`vftable';
  *((_DWORD *)v6 + 70) = 1;
  v6[33] = v6 + 2;
  tip2::details::shared_data<1,0,0>::open_without_lock((__int64)(v6 + 1), v7, v8);
  result = a1;
  *a1 = v6;
  return result;
}

```

## disassembly

```asm
0x18000f708  push    rbx
0x18000f70a  push    rsi
0x18000f70b  push    rdi
0x18000f70c  push    r14
0x18000f70e  sub     rsp, 58h
0x18000f712  mov     r14, rcx
0x18000f715  mov     rdi, rdx
0x18000f718  mov     ecx, 120h; cb
0x18000f71d  call    cs:__imp_CoTaskMemAlloc
0x18000f723  mov     rsi, rax
0x18000f726  test    rax, rax
0x18000f729  jz      loc_18000F7CD
0x18000f72f  mov     rdi, [rdi]
0x18000f732  lea     rax, ??_7test_data_interface@details@tip2@@6B@; const tip2::details::test_data_interface::`vftable'
0x18000f739  xor     ecx, ecx
0x18000f73b  mov     [rsi], rax
0x18000f73e  lea     rax, aRtffilterconte; "RtfFilterContentExtractionTipTest"
0x18000f745  mov     [rsp+78h+var_46], ecx
0x18000f749  mov     [rsp+78h+var_42], cx
0x18000f74e  lea     r8, [rsp+78h+var_58]
0x18000f753  xorps   xmm0, xmm0
0x18000f756  mov     [rsp+78h+var_30], rcx
0x18000f75b  mov     rdx, rsi
0x18000f75e  mov     [rsp+78h+var_50], rax
0x18000f763  lea     rcx, [rsi+8]
0x18000f767  mov     [rsp+78h+var_58], 32851B8h
0x18000f76f  mov     [rsp+78h+var_54], 4105h
0x18000f777  mov     [rsp+78h+var_48], 101h
0x18000f77e  movdqu  [rsp+78h+var_40], xmm0
0x18000f784  call    ??0?$shared_data@$00$0A@$0A@@details@tip2@@QEAA@AEAUtest_data_interface@12@AEBUtest_info@2@@Z; tip2::details::shared_data<1,0,0>::shared_data<1,0,0>(tip2::details::test_data_interface &,tip2::test_info const &)
0x18000f789  lea     rax, ??_7?$merged_data@U_tip_RtfFilterContentExtractionTipTest@@U1@@details@tip2@@6B@; const tip2::details::merged_data<_tip_RtfFilterContentExtractionTipTest,_tip_RtfFilterContentExtractionTipTest>::`vftable'
0x18000f790  mov     word ptr [rsi+110h], 0
0x18000f799  mov     [rsi], rax
0x18000f79c  lea     rcx, [rsi+8]
0x18000f7a0  lea     rax, [rsi+10h]
0x18000f7a4  mov     dword ptr [rsi+118h], 1
0x18000f7ae  mov     rdx, rdi
0x18000f7b1  mov     [rsi+108h], rax
0x18000f7b8  call    ?open_without_lock@?$shared_data@$00$0A@$0A@@details@tip2@@IEAAXPEAU_GUID@@@Z; tip2::details::shared_data<1,0,0>::open_without_lock(_GUID *)
0x18000f7bd  mov     rax, r14
0x18000f7c0  mov     [r14], rsi
0x18000f7c3  add     rsp, 58h
0x18000f7c7  pop     r14
0x18000f7c9  pop     rdi
0x18000f7ca  pop     rsi
0x18000f7cb  pop     rbx
0x18000f7cc  retn
0x18000f7cd  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
