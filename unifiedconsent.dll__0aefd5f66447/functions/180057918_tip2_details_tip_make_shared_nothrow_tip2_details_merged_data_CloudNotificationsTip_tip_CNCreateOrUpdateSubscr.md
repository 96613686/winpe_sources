# tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<CloudNotificationsTip::_tip_CNCreateOrUpdateSubscriptionTip,CloudNotificationsTip::_tip_CNCreateOrUpdateSubscriptionTip>,>(void)

- ea: `0x180057918`
- end: `0x180057aef`
- name: `??$tip_make_shared_nothrow@V?$merged_data@U_tip_CNCreateOrUpdateSubscriptionTip@CloudNotificationsTip@@U12@@details@tip2@@$$V@details@tip2@@YA?AV?$com_ptr_t@V?$merged_data@U_tip_CNCreateOrUpdateSubscriptionTip@CloudNotificationsTip@@U12@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ`
- size: `471`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x18005eac4`

## callees

- `0x18000e434`
- `0x180012fe8`
- `0x180057918`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18005792f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18005792f`

## string_xrefs

- `0x180057960`: `CNCreateOrUpdateSubscriptionTip`

## pseudocode

```c
_QWORD *__fastcall tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<CloudNotificationsTip::_tip_CNCreateOrUpdateSubscriptionTip,CloudNotificationsTip::_tip_CNCreateOrUpdateSubscriptionTip>,>(
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

  v2 = CoTaskMemAlloc(0x248u);
  v4 = v2;
  if ( !v2 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v3);
  v6[0] = 58205074;
  v9 = 0;
  *v2 = &tip2::details::test_data_interface::`vftable';
  v10 = 0;
  v7 = "CNCreateOrUpdateSubscriptionTip";
  v6[1] = 49408;
  v8 = 513;
  v11 = 0;
  v12 = 0;
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
  *((_OWORD *)v4 + 25) = 0;
  v4[52] = 0;
  v4[53] = 7;
  *((_WORD *)v4 + 200) = 0;
  *((_OWORD *)v4 + 27) = 0;
  v4[56] = 0;
  v4[57] = 7;
  *((_WORD *)v4 + 216) = 0;
  *((_OWORD *)v4 + 29) = 0;
  v4[60] = 0;
  v4[61] = 7;
  *((_WORD *)v4 + 232) = 0;
  *((_OWORD *)v4 + 31) = 0;
  v4[64] = 0;
  v4[65] = 7;
  *((_WORD *)v4 + 248) = 0;
  *((_OWORD *)v4 + 33) = 0;
  v4[68] = 0;
  v4[69] = 7;
  *((_WORD *)v4 + 264) = 0;
  *((_DWORD *)v4 + 142) = 0;
  *((_WORD *)v4 + 286) = 0;
  v4[70] = 1;
  *v4 = &tip2::details::merged_data<CloudNotificationsTip::_tip_CNCreateOrUpdateSubscriptionTip,CloudNotificationsTip::_tip_CNCreateOrUpdateSubscriptionTip>::`vftable';
  v4[33] = v4 + 2;
  result = a1;
  *((_DWORD *)v4 + 144) = 1;
  *a1 = v4;
  return result;
}

```

## disassembly

```asm
0x180057918  mov     [rsp+arg_0], rbx
0x18005791d  mov     [rsp+arg_8], rbp
0x180057922  push    rdi
0x180057923  sub     rsp, 50h
0x180057927  mov     rdi, rcx
0x18005792a  mov     ecx, 248h; cb
0x18005792f  call    cs:__imp_CoTaskMemAlloc
0x180057935  xor     ebp, ebp
0x180057937  mov     rbx, rax
0x18005793a  test    rax, rax
0x18005793d  jz      loc_180057AE9
0x180057943  xor     ecx, ecx
0x180057945  mov     [rsp+58h+var_38], 3782392h
0x18005794d  lea     rax, ??_7test_data_interface@details@tip2@@6B@; const tip2::details::test_data_interface::`vftable'
0x180057954  mov     [rsp+58h+var_26], ecx
0x180057958  mov     [rbx], rax
0x18005795b  lea     r8, [rsp+58h+var_38]
0x180057960  lea     rax, aCncreateorupda; "CNCreateOrUpdateSubscriptionTip"
0x180057967  mov     [rsp+58h+var_22], cx
0x18005796c  xorps   xmm0, xmm0
0x18005796f  mov     [rsp+58h+var_30], rax
0x180057974  lea     rcx, [rbx+8]
0x180057978  mov     [rsp+58h+var_34], 0C100h
0x180057980  mov     rdx, rbx
0x180057983  mov     [rsp+58h+var_28], 201h
0x18005798a  movdqu  [rsp+58h+var_20], xmm0
0x180057990  mov     [rsp+58h+var_10], rbp
0x180057995  call    ??0?$shared_data@$0A@$0A@$0A@@details@tip2@@QEAA@AEAUtest_data_interface@12@AEBUtest_info@2@@Z; tip2::details::shared_data<0,0,0>::shared_data<0,0,0>(tip2::details::test_data_interface &,tip2::test_info const &)
0x18005799a  lea     ecx, [rbp+7]
0x18005799d  xorps   xmm0, xmm0
0x1800579a0  movups  xmmword ptr [rbx+110h], xmm0
0x1800579a7  mov     [rbx+120h], rbp
0x1800579ae  lea     rax, ??_7?$merged_data@U_tip_CNCreateOrUpdateSubscriptionTip@CloudNotificationsTip@@U12@@details@tip2@@6B@; const tip2::details::merged_data<CloudNotificationsTip::_tip_CNCreateOrUpdateSubscriptionTip,CloudNotificationsTip::_tip_CNCreateOrUpdateSubscriptionTip>::`vftable'
0x1800579b5  mov     [rbx+128h], rcx
0x1800579bc  mov     [rbx+110h], bp
0x1800579c3  movups  xmmword ptr [rbx+130h], xmm0
0x1800579ca  mov     [rbx+140h], rbp
0x1800579d1  mov     [rbx+148h], rcx
0x1800579d8  mov     [rbx+130h], bp
0x1800579df  movups  xmmword ptr [rbx+150h], xmm0
0x1800579e6  mov     [rbx+160h], rbp
0x1800579ed  mov     [rbx+168h], rcx
0x1800579f4  mov     [rbx+150h], bp
0x1800579fb  movups  xmmword ptr [rbx+170h], xmm0
0x180057a02  mov     [rbx+180h], rbp
0x180057a09  mov     [rbx+188h], rcx
0x180057a10  mov     [rbx+170h], bp
0x180057a17  movups  xmmword ptr [rbx+190h], xmm0
0x180057a1e  mov     [rbx+1A0h], rbp
0x180057a25  mov     [rbx+1A8h], rcx
0x180057a2c  mov     [rbx+190h], bp
0x180057a33  movups  xmmword ptr [rbx+1B0h], xmm0
0x180057a3a  mov     [rbx+1C0h], rbp
0x180057a41  mov     [rbx+1C8h], rcx
0x180057a48  mov     [rbx+1B0h], bp
0x180057a4f  movups  xmmword ptr [rbx+1D0h], xmm0
0x180057a56  mov     [rbx+1E0h], rbp
0x180057a5d  mov     [rbx+1E8h], rcx
0x180057a64  mov     [rbx+1D0h], bp
0x180057a6b  movups  xmmword ptr [rbx+1F0h], xmm0
0x180057a72  mov     [rbx+200h], rbp
0x180057a79  mov     [rbx+208h], rcx
0x180057a80  mov     [rbx+1F0h], bp
0x180057a87  movups  xmmword ptr [rbx+210h], xmm0
0x180057a8e  mov     [rbx+220h], rbp
0x180057a95  mov     [rbx+228h], rcx
0x180057a9c  mov     [rbx+210h], bp
0x180057aa3  mov     [rbx+238h], ebp
0x180057aa9  mov     [rbx+23Ch], bp
0x180057ab0  mov     rbp, [rsp+58h+arg_8]
0x180057ab5  mov     qword ptr [rbx+230h], 1
0x180057ac0  mov     [rbx], rax
0x180057ac3  lea     rax, [rbx+10h]
0x180057ac7  mov     [rbx+108h], rax
0x180057ace  mov     rax, rdi
0x180057ad1  mov     dword ptr [rbx+240h], 1
0x180057adb  mov     [rdi], rbx
0x180057ade  mov     rbx, [rsp+58h+arg_0]
0x180057ae3  add     rsp, 50h
0x180057ae7  pop     rdi
0x180057ae8  retn
0x180057ae9  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
