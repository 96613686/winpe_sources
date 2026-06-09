# tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<CloudNotificationsTip::_tip_CNCreateWnpChannelTip,CloudNotificationsTip::_tip_CNCreateWnpChannelTip>,>(void)

- ea: `0x180057af8`
- end: `0x180057c32`
- name: `??$tip_make_shared_nothrow@V?$merged_data@U_tip_CNCreateWnpChannelTip@CloudNotificationsTip@@U12@@details@tip2@@$$V@details@tip2@@YA?AV?$com_ptr_t@V?$merged_data@U_tip_CNCreateWnpChannelTip@CloudNotificationsTip@@U12@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ`
- size: `314`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x18005eb58`

## callees

- `0x18000e434`
- `0x180012fe8`
- `0x180057af8`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180057b0a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180057b0a`

## string_xrefs

- `0x180057b39`: `CNCreateWnpChannelTip`

## pseudocode

```c
_QWORD *__fastcall tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<CloudNotificationsTip::_tip_CNCreateWnpChannelTip,CloudNotificationsTip::_tip_CNCreateWnpChannelTip>,>(
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

  v2 = CoTaskMemAlloc(0x1A0u);
  v4 = v2;
  if ( !v2 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v3);
  v6[0] = 60260990;
  v9 = 0;
  *v2 = &tip2::details::test_data_interface::`vftable';
  v10 = 0;
  v12 = 0;
  v7 = "CNCreateWnpChannelTip";
  v6[1] = 49408;
  v8 = 257;
  v11 = 0;
  tip2::details::shared_data<0,0,0>::shared_data<0,0,0>(v2 + 1, v2, v6);
  *((_OWORD *)v4 + 17) = 0;
  v4[36] = 0;
  v4[37] = 7;
  *((_WORD *)v4 + 136) = 0;
  *((_OWORD *)v4 + 19) = 0;
  v4[40] = 0;
  v4[41] = 7;
  *((_WORD *)v4 + 152) = 0;
  *((_OWORD *)v4 + 21) = 0;
  v4[44] = 0;
  v4[45] = 7;
  *((_WORD *)v4 + 168) = 0;
  *((_OWORD *)v4 + 23) = 0;
  v4[48] = 0;
  v4[49] = 7;
  *((_WORD *)v4 + 184) = 0;
  v4[50] = 1;
  *v4 = &tip2::details::merged_data<CloudNotificationsTip::_tip_CNCreateWnpChannelTip,CloudNotificationsTip::_tip_CNCreateWnpChannelTip>::`vftable';
  v4[33] = v4 + 2;
  result = a1;
  *((_DWORD *)v4 + 102) = 1;
  *a1 = v4;
  return result;
}

```

## disassembly

```asm
0x180057af8  mov     [rsp+arg_0], rbx
0x180057afd  push    rdi
0x180057afe  sub     rsp, 50h
0x180057b02  mov     rdi, rcx
0x180057b05  mov     ecx, 1A0h; cb
0x180057b0a  call    cs:__imp_CoTaskMemAlloc
0x180057b10  mov     rbx, rax
0x180057b13  test    rax, rax
0x180057b16  jz      loc_180057C2C
0x180057b1c  xor     ecx, ecx
0x180057b1e  mov     [rsp+58h+var_38], 397827Eh
0x180057b26  lea     rax, ??_7test_data_interface@details@tip2@@6B@; const tip2::details::test_data_interface::`vftable'
0x180057b2d  mov     [rsp+58h+var_26], ecx
0x180057b31  mov     [rbx], rax
0x180057b34  lea     r8, [rsp+58h+var_38]
0x180057b39  lea     rax, aCncreatewnpcha; "CNCreateWnpChannelTip"
0x180057b40  mov     [rsp+58h+var_22], cx
0x180057b45  xorps   xmm0, xmm0
0x180057b48  mov     [rsp+58h+var_10], rcx
0x180057b4d  lea     rcx, [rbx+8]
0x180057b51  mov     [rsp+58h+var_30], rax
0x180057b56  mov     rdx, rbx
0x180057b59  mov     [rsp+58h+var_34], 0C100h
0x180057b61  mov     [rsp+58h+var_28], 101h
0x180057b68  movdqu  [rsp+58h+var_20], xmm0
0x180057b6e  call    ??0?$shared_data@$0A@$0A@$0A@@details@tip2@@QEAA@AEAUtest_data_interface@12@AEBUtest_info@2@@Z; tip2::details::shared_data<0,0,0>::shared_data<0,0,0>(tip2::details::test_data_interface &,tip2::test_info const &)
0x180057b73  xor     eax, eax
0x180057b75  xorps   xmm0, xmm0
0x180057b78  movups  xmmword ptr [rbx+110h], xmm0
0x180057b7f  mov     qword ptr [rbx+120h], 0
0x180057b8a  mov     ecx, 7
0x180057b8f  mov     [rbx+128h], rcx
0x180057b96  mov     [rbx+110h], ax
0x180057b9d  movups  xmmword ptr [rbx+130h], xmm0
0x180057ba4  mov     [rbx+140h], rax
0x180057bab  mov     [rbx+148h], rcx
0x180057bb2  mov     [rbx+130h], ax
0x180057bb9  movups  xmmword ptr [rbx+150h], xmm0
0x180057bc0  mov     [rbx+160h], rax
0x180057bc7  mov     [rbx+168h], rcx
0x180057bce  mov     [rbx+150h], ax
0x180057bd5  movups  xmmword ptr [rbx+170h], xmm0
0x180057bdc  mov     [rbx+180h], rax
0x180057be3  mov     [rbx+188h], rcx
0x180057bea  mov     [rbx+170h], ax
0x180057bf1  lea     rax, ??_7?$merged_data@U_tip_CNCreateWnpChannelTip@CloudNotificationsTip@@U12@@details@tip2@@6B@; const tip2::details::merged_data<CloudNotificationsTip::_tip_CNCreateWnpChannelTip,CloudNotificationsTip::_tip_CNCreateWnpChannelTip>::`vftable'
0x180057bf8  mov     qword ptr [rbx+190h], 1
0x180057c03  mov     [rbx], rax
0x180057c06  lea     rax, [rbx+10h]
0x180057c0a  mov     [rbx+108h], rax
0x180057c11  mov     rax, rdi
0x180057c14  mov     dword ptr [rbx+198h], 1
0x180057c1e  mov     [rdi], rbx
0x180057c21  mov     rbx, [rsp+58h+arg_0]
0x180057c26  add     rsp, 50h
0x180057c2a  pop     rdi
0x180057c2b  retn
0x180057c2c  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
