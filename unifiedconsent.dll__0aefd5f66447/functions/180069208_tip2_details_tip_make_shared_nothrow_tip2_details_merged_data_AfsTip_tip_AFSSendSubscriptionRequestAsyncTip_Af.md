# tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<AfsTip::_tip_AFSSendSubscriptionRequestAsyncTip,AfsTip::_tip_AFSSendSubscriptionRequestAsyncTip>,>(void)

- ea: `0x180069208`
- end: `0x1800693a8`
- name: `??$tip_make_shared_nothrow@V?$merged_data@U_tip_AFSSendSubscriptionRequestAsyncTip@AfsTip@@U12@@details@tip2@@$$V@details@tip2@@YA?AV?$com_ptr_t@V?$merged_data@U_tip_AFSSendSubscriptionRequestAsyncTip@AfsTip@@U12@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ`
- size: `416`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x18006c260`

## callees

- `0x18000e434`
- `0x180012fe8`
- `0x180069208`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18006921f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18006921f`

## pseudocode

```c
_QWORD *__fastcall tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<AfsTip::_tip_AFSSendSubscriptionRequestAsyncTip,AfsTip::_tip_AFSSendSubscriptionRequestAsyncTip>,>(
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

  v2 = CoTaskMemAlloc(0x208u);
  v4 = v2;
  if ( !v2 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v3);
  v6[0] = 58205109;
  v9 = 0;
  *v2 = &tip2::details::test_data_interface::`vftable';
  v10 = 0;
  v7 = "AFSSendSubscriptionRequestAsyncTip";
  v6[1] = 49408;
  v8 = 257;
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
  *((_WORD *)v4 + 252) = 0;
  *((_BYTE *)v4 + 506) = 0;
  v4[62] = 1;
  *v4 = &tip2::details::merged_data<AfsTip::_tip_AFSSendSubscriptionRequestAsyncTip,AfsTip::_tip_AFSSendSubscriptionRequestAsyncTip>::`vftable';
  v4[33] = v4 + 2;
  result = a1;
  *((_DWORD *)v4 + 128) = 1;
  *a1 = v4;
  return result;
}

```

## disassembly

```asm
0x180069208  mov     [rsp+arg_0], rbx
0x18006920d  mov     [rsp+arg_8], rbp
0x180069212  push    rdi
0x180069213  sub     rsp, 50h
0x180069217  mov     rdi, rcx
0x18006921a  mov     ecx, 208h; cb
0x18006921f  call    cs:__imp_CoTaskMemAlloc
0x180069225  xor     ebp, ebp
0x180069227  mov     rbx, rax
0x18006922a  test    rax, rax
0x18006922d  jz      loc_1800693A2
0x180069233  xor     ecx, ecx
0x180069235  mov     [rsp+58h+var_38], 37823B5h
0x18006923d  lea     rax, ??_7test_data_interface@details@tip2@@6B@; const tip2::details::test_data_interface::`vftable'
0x180069244  mov     [rsp+58h+var_26], ecx
0x180069248  mov     [rbx], rax
0x18006924b  lea     r8, [rsp+58h+var_38]
0x180069250  lea     rax, aAfssendsubscri; "AFSSendSubscriptionRequestAsyncTip"
0x180069257  mov     [rsp+58h+var_22], cx
0x18006925c  xorps   xmm0, xmm0
0x18006925f  mov     [rsp+58h+var_30], rax
0x180069264  lea     rcx, [rbx+8]
0x180069268  mov     [rsp+58h+var_34], 0C100h
0x180069270  mov     rdx, rbx
0x180069273  mov     [rsp+58h+var_28], 101h
0x18006927a  movdqu  [rsp+58h+var_20], xmm0
0x180069280  mov     [rsp+58h+var_10], rbp
0x180069285  call    ??0?$shared_data@$0A@$0A@$0A@@details@tip2@@QEAA@AEAUtest_data_interface@12@AEBUtest_info@2@@Z; tip2::details::shared_data<0,0,0>::shared_data<0,0,0>(tip2::details::test_data_interface &,tip2::test_info const &)
0x18006928a  lea     ecx, [rbp+7]
0x18006928d  xorps   xmm0, xmm0
0x180069290  movups  xmmword ptr [rbx+110h], xmm0
0x180069297  mov     [rbx+120h], rbp
0x18006929e  lea     rax, ??_7?$merged_data@U_tip_AFSSendSubscriptionRequestAsyncTip@AfsTip@@U12@@details@tip2@@6B@; const tip2::details::merged_data<AfsTip::_tip_AFSSendSubscriptionRequestAsyncTip,AfsTip::_tip_AFSSendSubscriptionRequestAsyncTip>::`vftable'
0x1800692a5  mov     [rbx+128h], rcx
0x1800692ac  mov     [rbx+110h], bp
0x1800692b3  movups  xmmword ptr [rbx+130h], xmm0
0x1800692ba  mov     [rbx+140h], rbp
0x1800692c1  mov     [rbx+148h], rcx
0x1800692c8  mov     [rbx+130h], bp
0x1800692cf  movups  xmmword ptr [rbx+150h], xmm0
0x1800692d6  mov     [rbx+160h], rbp
0x1800692dd  mov     [rbx+168h], rcx
0x1800692e4  mov     [rbx+150h], bp
0x1800692eb  movups  xmmword ptr [rbx+170h], xmm0
0x1800692f2  mov     [rbx+180h], rbp
0x1800692f9  mov     [rbx+188h], rcx
0x180069300  mov     [rbx+170h], bp
0x180069307  movups  xmmword ptr [rbx+190h], xmm0
0x18006930e  mov     [rbx+1A0h], rbp
0x180069315  mov     [rbx+1A8h], rcx
0x18006931c  mov     [rbx+190h], bp
0x180069323  movups  xmmword ptr [rbx+1B0h], xmm0
0x18006932a  mov     [rbx+1C0h], rbp
0x180069331  mov     [rbx+1C8h], rcx
0x180069338  mov     [rbx+1B0h], bp
0x18006933f  movups  xmmword ptr [rbx+1D0h], xmm0
0x180069346  mov     [rbx+1E0h], rbp
0x18006934d  mov     [rbx+1E8h], rcx
0x180069354  mov     [rbx+1D0h], bp
0x18006935b  mov     [rbx+1F8h], bp
0x180069362  mov     [rbx+1FAh], bpl
0x180069369  mov     rbp, [rsp+58h+arg_8]
0x18006936e  mov     qword ptr [rbx+1F0h], 1
0x180069379  mov     [rbx], rax
0x18006937c  lea     rax, [rbx+10h]
0x180069380  mov     [rbx+108h], rax
0x180069387  mov     rax, rdi
0x18006938a  mov     dword ptr [rbx+200h], 1
0x180069394  mov     [rdi], rbx
0x180069397  mov     rbx, [rsp+58h+arg_0]
0x18006939c  add     rsp, 50h
0x1800693a0  pop     rdi
0x1800693a1  retn
0x1800693a2  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
