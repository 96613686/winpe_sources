# tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest,CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest>,>(void)

- ea: `0x18000de94`
- end: `0x18000df7e`
- name: `??$tip_make_shared_nothrow@V?$merged_data@U_tip_DiagHealthTipTest@DiagHealth@CalliopeTipTests@@U123@@details@tip2@@$$V@details@tip2@@YA?AV?$com_ptr_t@V?$merged_data@U_tip_DiagHealthTipTest@DiagHealth@CalliopeTipTests@@U123@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ`
- size: `234`
- prototype: `_QWORD *__fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000d988`

## callees

- `0x180007600`
- `0x180008940`
- `0x18000de94`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000deb1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000deb1`

## pseudocode

```c
_QWORD *__fastcall tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest,CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest>,>(
        _QWORD *a1)
{
  _QWORD *v2; // rax
  wil::details::in1diag3 *v3; // rcx
  _QWORD *v4; // rbx
  _QWORD *result; // rax
  __int128 v6; // [rsp+20h] [rbp-60h]
  _OWORD v7[3]; // [rsp+50h] [rbp-30h] BYREF

  v2 = CoTaskMemAlloc(0x128u);
  v4 = v2;
  if ( !v2 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v3);
  *(_QWORD *)&v6 = 0x410003A79AC7LL;
  *v2 = &tip2::details::test_data_interface::`vftable';
  *((_QWORD *)&v6 + 1) = "DiagHealthTipTest";
  v7[0] = v6;
  v7[1] = 1u;
  v7[2] = 0u;
  tip2::details::shared_data<1,0,0>::shared_data<1,0,0>(v2 + 1, v2, v7);
  *((_DWORD *)v4 + 68) = 0;
  *v4 = &tip2::details::merged_data<CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest,CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest>::`vftable';
  *(_QWORD *)((char *)v4 + 276) = 1;
  v4[33] = v4 + 2;
  result = a1;
  *((_DWORD *)v4 + 72) = 1;
  *a1 = v4;
  return result;
}

```

## disassembly

```asm
0x18000de94  mov     [rsp-8+arg_0], rbx
0x18000de99  mov     [rsp-8+arg_8], rdi
0x18000de9e  push    rbp
0x18000de9f  mov     rbp, rsp
0x18000dea2  sub     rsp, 80h
0x18000dea9  mov     rdi, rcx
0x18000deac  mov     ecx, 128h; cb
0x18000deb1  call    cs:__imp_CoTaskMemAlloc
0x18000deb7  mov     rbx, rax
0x18000deba  test    rax, rax
0x18000debd  jz      loc_18000DF78
0x18000dec3  xorps   xmm0, xmm0
0x18000dec6  mov     dword ptr [rbp+var_60], 3A79AC7h
0x18000decd  movdqu  [rbp+var_50+8], xmm0
0x18000ded2  lea     rax, ??_7test_data_interface@details@tip2@@6B@; const tip2::details::test_data_interface::`vftable'
0x18000ded9  mov     dword ptr [rbp+var_60+4], 4100h
0x18000dee0  mov     [rbx], rax
0x18000dee3  lea     rcx, [rbx+8]
0x18000dee7  lea     rax, aDiaghealthtipt; "DiagHealthTipTest"
0x18000deee  mov     word ptr [rbp+var_50], 1
0x18000def4  mov     qword ptr [rbp+var_60+8], rax
0x18000def8  lea     r8, [rbp+var_30]
0x18000defc  movups  xmm0, [rbp+var_60]
0x18000df00  xor     eax, eax
0x18000df02  mov     rdx, rbx
0x18000df05  mov     dword ptr [rbp+var_50+2], eax
0x18000df08  movups  [rbp+var_30], xmm0
0x18000df0c  mov     word ptr [rbp+var_50+6], ax
0x18000df10  movups  xmm1, [rbp+var_50]
0x18000df14  mov     [rbp+var_38], rax
0x18000df18  movups  xmm0, xmmword ptr [rbp-40h]
0x18000df1c  movups  [rbp+var_20], xmm1
0x18000df20  movups  [rbp+var_10], xmm0
0x18000df24  call    ??0?$shared_data@$00$0A@$0A@@details@tip2@@QEAA@AEAUtest_data_interface@12@AEBUtest_info@2@@Z; tip2::details::shared_data<1,0,0>::shared_data<1,0,0>(tip2::details::test_data_interface &,tip2::test_info const &)
0x18000df29  lea     rax, ??_7?$merged_data@U_tip_DiagHealthTipTest@DiagHealth@CalliopeTipTests@@U123@@details@tip2@@6B@; const tip2::details::merged_data<CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest,CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest>::`vftable'
0x18000df30  mov     dword ptr [rbx+110h], 0
0x18000df3a  mov     [rbx], rax
0x18000df3d  lea     r11, [rsp+80h+var_s0]
0x18000df45  lea     rax, [rbx+10h]
0x18000df49  mov     qword ptr [rbx+114h], 1
0x18000df54  mov     [rbx+108h], rax
0x18000df5b  mov     rax, rdi
0x18000df5e  mov     dword ptr [rbx+120h], 1
0x18000df68  mov     [rdi], rbx
0x18000df6b  mov     rbx, [r11+10h]
0x18000df6f  mov     rdi, [r11+18h]
0x18000df73  mov     rsp, r11
0x18000df76  pop     rbp
0x18000df77  retn
0x18000df78  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
