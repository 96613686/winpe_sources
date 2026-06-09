# tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<AfsTip::_tip_CRHomeCloudTip,AfsTip::_tip_CRHomeCloudTip>,>(void)

- ea: `0x180060614`
- end: `0x1800606f9`
- name: `??$tip_make_shared_nothrow@V?$merged_data@U_tip_CRHomeCloudTip@AfsTip@@U12@@details@tip2@@$$V@details@tip2@@YA?AV?$com_ptr_t@V?$merged_data@U_tip_CRHomeCloudTip@AfsTip@@U12@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ`
- size: `229`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x180067ca8`

## callees

- `0x18000e434`
- `0x180012fe8`
- `0x180060614`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180060626`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180060626`

## pseudocode

```c
_QWORD *__fastcall tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<AfsTip::_tip_CRHomeCloudTip,AfsTip::_tip_CRHomeCloudTip>,>(
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

  v2 = CoTaskMemAlloc(0x140u);
  v4 = v2;
  if ( !v2 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v3);
  v6[0] = 58129034;
  v9 = 0;
  *v2 = &tip2::details::test_data_interface::`vftable';
  v10 = 0;
  v12 = 0;
  v7 = "CRHomeCloudTip";
  v6[1] = 49408;
  v8 = 257;
  v11 = 0;
  tip2::details::shared_data<0,0,0>::shared_data<0,0,0>(v2 + 1, v2, v6);
  *((_OWORD *)v4 + 17) = 0;
  v4[36] = 0;
  v4[37] = 7;
  *((_WORD *)v4 + 136) = 0;
  v4[38] = 1;
  *v4 = &tip2::details::merged_data<AfsTip::_tip_CRHomeCloudTip,AfsTip::_tip_CRHomeCloudTip>::`vftable';
  v4[33] = v4 + 2;
  result = a1;
  *((_DWORD *)v4 + 78) = 1;
  *a1 = v4;
  return result;
}

```

## disassembly

```asm
0x180060614  mov     [rsp+arg_0], rbx
0x180060619  push    rdi
0x18006061a  sub     rsp, 50h
0x18006061e  mov     rdi, rcx
0x180060621  mov     ecx, 140h; cb
0x180060626  call    cs:__imp_CoTaskMemAlloc
0x18006062c  mov     rbx, rax
0x18006062f  test    rax, rax
0x180060632  jz      loc_1800606F3
0x180060638  xor     ecx, ecx
0x18006063a  mov     [rsp+58h+var_38], 376FA8Ah
0x180060642  lea     rax, ??_7test_data_interface@details@tip2@@6B@; const tip2::details::test_data_interface::`vftable'
0x180060649  mov     [rsp+58h+var_26], ecx
0x18006064d  mov     [rbx], rax
0x180060650  lea     r8, [rsp+58h+var_38]
0x180060655  lea     rax, aCrhomecloudtip; "CRHomeCloudTip"
0x18006065c  mov     [rsp+58h+var_22], cx
0x180060661  xorps   xmm0, xmm0
0x180060664  mov     [rsp+58h+var_10], rcx
0x180060669  lea     rcx, [rbx+8]
0x18006066d  mov     [rsp+58h+var_30], rax
0x180060672  mov     rdx, rbx
0x180060675  mov     [rsp+58h+var_34], 0C100h
0x18006067d  mov     [rsp+58h+var_28], 101h
0x180060684  movdqu  [rsp+58h+var_20], xmm0
0x18006068a  call    ??0?$shared_data@$0A@$0A@$0A@@details@tip2@@QEAA@AEAUtest_data_interface@12@AEBUtest_info@2@@Z; tip2::details::shared_data<0,0,0>::shared_data<0,0,0>(tip2::details::test_data_interface &,tip2::test_info const &)
0x18006068f  xor     eax, eax
0x180060691  xorps   xmm0, xmm0
0x180060694  movups  xmmword ptr [rbx+110h], xmm0
0x18006069b  mov     qword ptr [rbx+120h], 0
0x1800606a6  mov     qword ptr [rbx+128h], 7
0x1800606b1  mov     [rbx+110h], ax
0x1800606b8  lea     rax, ??_7?$merged_data@U_tip_CRHomeCloudTip@AfsTip@@U12@@details@tip2@@6B@; const tip2::details::merged_data<AfsTip::_tip_CRHomeCloudTip,AfsTip::_tip_CRHomeCloudTip>::`vftable'
0x1800606bf  mov     qword ptr [rbx+130h], 1
0x1800606ca  mov     [rbx], rax
0x1800606cd  lea     rax, [rbx+10h]
0x1800606d1  mov     [rbx+108h], rax
0x1800606d8  mov     rax, rdi
0x1800606db  mov     dword ptr [rbx+138h], 1
0x1800606e5  mov     [rdi], rbx
0x1800606e8  mov     rbx, [rsp+58h+arg_0]
0x1800606ed  add     rsp, 50h
0x1800606f1  pop     rdi
0x1800606f2  retn
0x1800606f3  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
