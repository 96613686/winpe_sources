# tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<CloudNotificationsTip::_tip_CNRegisterWnpEndpointTip,CloudNotificationsTip::_tip_CNRegisterWnpEndpointTip>,>(void)

- ea: `0x180057c38`
- end: `0x180057d5d`
- name: `??$tip_make_shared_nothrow@V?$merged_data@U_tip_CNRegisterWnpEndpointTip@CloudNotificationsTip@@U12@@details@tip2@@$$V@details@tip2@@YA?AV?$com_ptr_t@V?$merged_data@U_tip_CNRegisterWnpEndpointTip@CloudNotificationsTip@@U12@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ`
- size: `293`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x18005ebec`

## callees

- `0x18000e434`
- `0x180012fe8`
- `0x180057c38`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180057c4a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180057c4a`

## pseudocode

```c
_QWORD *__fastcall tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<CloudNotificationsTip::_tip_CNRegisterWnpEndpointTip,CloudNotificationsTip::_tip_CNRegisterWnpEndpointTip>,>(
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

  v2 = CoTaskMemAlloc(0x188u);
  v4 = v2;
  if ( !v2 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v3);
  v6[0] = 60260968;
  v9 = 0;
  *v2 = &tip2::details::test_data_interface::`vftable';
  v10 = 0;
  v12 = 0;
  v7 = "CNRegisterWnpEndpointTip";
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
  v4[47] = 0;
  v4[46] = 1;
  *v4 = &tip2::details::merged_data<CloudNotificationsTip::_tip_CNRegisterWnpEndpointTip,CloudNotificationsTip::_tip_CNRegisterWnpEndpointTip>::`vftable';
  v4[33] = v4 + 2;
  result = a1;
  *((_DWORD *)v4 + 96) = 1;
  *a1 = v4;
  return result;
}

```

## disassembly

```asm
0x180057c38  mov     [rsp+arg_0], rbx
0x180057c3d  push    rdi
0x180057c3e  sub     rsp, 50h
0x180057c42  mov     rdi, rcx
0x180057c45  mov     ecx, 188h; cb
0x180057c4a  call    cs:__imp_CoTaskMemAlloc
0x180057c50  mov     rbx, rax
0x180057c53  test    rax, rax
0x180057c56  jz      loc_180057D57
0x180057c5c  xor     ecx, ecx
0x180057c5e  mov     [rsp+58h+var_38], 3978268h
0x180057c66  lea     rax, ??_7test_data_interface@details@tip2@@6B@; const tip2::details::test_data_interface::`vftable'
0x180057c6d  mov     [rsp+58h+var_26], ecx
0x180057c71  mov     [rbx], rax
0x180057c74  lea     r8, [rsp+58h+var_38]
0x180057c79  lea     rax, aCnregisterwnpe; "CNRegisterWnpEndpointTip"
0x180057c80  mov     [rsp+58h+var_22], cx
0x180057c85  xorps   xmm0, xmm0
0x180057c88  mov     [rsp+58h+var_10], rcx
0x180057c8d  lea     rcx, [rbx+8]
0x180057c91  mov     [rsp+58h+var_30], rax
0x180057c96  mov     rdx, rbx
0x180057c99  mov     [rsp+58h+var_34], 0C100h
0x180057ca1  mov     [rsp+58h+var_28], 101h
0x180057ca8  movdqu  [rsp+58h+var_20], xmm0
0x180057cae  call    ??0?$shared_data@$0A@$0A@$0A@@details@tip2@@QEAA@AEAUtest_data_interface@12@AEBUtest_info@2@@Z; tip2::details::shared_data<0,0,0>::shared_data<0,0,0>(tip2::details::test_data_interface &,tip2::test_info const &)
0x180057cb3  xor     eax, eax
0x180057cb5  xorps   xmm0, xmm0
0x180057cb8  movups  xmmword ptr [rbx+110h], xmm0
0x180057cbf  mov     qword ptr [rbx+120h], 0
0x180057cca  mov     ecx, 7
0x180057ccf  mov     [rbx+128h], rcx
0x180057cd6  mov     [rbx+110h], ax
0x180057cdd  movups  xmmword ptr [rbx+130h], xmm0
0x180057ce4  mov     [rbx+140h], rax
0x180057ceb  mov     [rbx+148h], rcx
0x180057cf2  mov     [rbx+130h], ax
0x180057cf9  movups  xmmword ptr [rbx+150h], xmm0
0x180057d00  mov     [rbx+160h], rax
0x180057d07  mov     [rbx+168h], rcx
0x180057d0e  mov     [rbx+150h], ax
0x180057d15  mov     [rbx+178h], rax
0x180057d1c  lea     rax, ??_7?$merged_data@U_tip_CNRegisterWnpEndpointTip@CloudNotificationsTip@@U12@@details@tip2@@6B@; const tip2::details::merged_data<CloudNotificationsTip::_tip_CNRegisterWnpEndpointTip,CloudNotificationsTip::_tip_CNRegisterWnpEndpointTip>::`vftable'
0x180057d23  mov     qword ptr [rbx+170h], 1
0x180057d2e  mov     [rbx], rax
0x180057d31  lea     rax, [rbx+10h]
0x180057d35  mov     [rbx+108h], rax
0x180057d3c  mov     rax, rdi
0x180057d3f  mov     dword ptr [rbx+180h], 1
0x180057d49  mov     [rdi], rbx
0x180057d4c  mov     rbx, [rsp+58h+arg_0]
0x180057d51  add     rsp, 50h
0x180057d55  pop     rdi
0x180057d56  retn
0x180057d57  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
