# tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest,CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest>,_GUID * &>(_GUID * &)

- ea: `0x180005c34`
- end: `0x180005d41`
- name: `??$tip_make_shared_nothrow@V?$merged_data@U_tip_DiagHealthTipTest@DiagHealth@CalliopeTipTests@@U123@@details@tip2@@AEAPEAU_GUID@@@details@tip2@@YA?AV?$com_ptr_t@V?$merged_data@U_tip_DiagHealthTipTest@DiagHealth@CalliopeTipTests@@U123@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@AEAPEAU_GUID@@@Z`
- size: `269`
- prototype: `_QWORD *__fastcall(_QWORD *, __int64 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x180004d9c`

## callees

- `0x180005c34`
- `0x18000649c`
- `0x180007600`
- `0x180008940`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180005c5d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180005c5d`

## pseudocode

```c
_QWORD *__fastcall tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest,CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest>,_GUID * &>(
        _QWORD *a1,
        __int64 *a2)
{
  _QWORD *v4; // rax
  wil::details::in1diag3 *v5; // rcx
  _QWORD *v6; // rsi
  __int64 v7; // rdi
  __int128 v9; // [rsp+20h] [rbp-60h]
  _OWORD v10[3]; // [rsp+50h] [rbp-30h] BYREF

  v4 = CoTaskMemAlloc(0x128u);
  v6 = v4;
  if ( !v4 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v5);
  v7 = *a2;
  *v4 = &tip2::details::test_data_interface::`vftable';
  *(_QWORD *)&v9 = 0x410003A79AC7LL;
  *((_QWORD *)&v9 + 1) = "DiagHealthTipTest";
  v10[0] = v9;
  v10[2] = 0u;
  v10[1] = 1u;
  tip2::details::shared_data<1,0,0>::shared_data<1,0,0>(v4 + 1, v4, v10);
  *((_DWORD *)v6 + 68) = 0;
  *v6 = &tip2::details::merged_data<CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest,CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest>::`vftable';
  *(_QWORD *)((char *)v6 + 276) = 1;
  v6[33] = v6 + 2;
  *((_DWORD *)v6 + 72) = 1;
  tip2::details::shared_data<1,0,0>::open_without_lock(v6 + 1, v7);
  *a1 = v6;
  return a1;
}

```

## disassembly

```asm
0x180005c34  mov     rax, rsp
0x180005c37  mov     [rax+8], rbx
0x180005c3b  mov     [rax+10h], rsi
0x180005c3f  mov     [rax+18h], rdi
0x180005c43  mov     [rax+20h], r14
0x180005c47  push    rbp
0x180005c48  mov     rbp, rsp
0x180005c4b  sub     rsp, 80h
0x180005c52  mov     r14, rcx
0x180005c55  mov     rdi, rdx
0x180005c58  mov     ecx, 128h; cb
0x180005c5d  call    cs:__imp_CoTaskMemAlloc
0x180005c63  mov     rsi, rax
0x180005c66  test    rax, rax
0x180005c69  jz      loc_180005D3B
0x180005c6f  mov     rdi, [rdi]
0x180005c72  lea     rax, ??_7test_data_interface@details@tip2@@6B@; const tip2::details::test_data_interface::`vftable'
0x180005c79  xorps   xmm0, xmm0
0x180005c7c  mov     [rsi], rax
0x180005c7f  movdqu  [rbp+var_50+8], xmm0
0x180005c84  lea     rax, aDiaghealthtipt; "DiagHealthTipTest"
0x180005c8b  mov     dword ptr [rbp+var_60], 3A79AC7h
0x180005c92  mov     qword ptr [rbp+var_60+8], rax
0x180005c96  lea     r8, [rbp+var_30]
0x180005c9a  xor     eax, eax
0x180005c9c  mov     dword ptr [rbp+var_60+4], 4100h
0x180005ca3  movups  xmm0, [rbp+var_60]
0x180005ca7  mov     dword ptr [rbp+var_50+2], eax
0x180005caa  lea     rcx, [rsi+8]
0x180005cae  mov     word ptr [rbp+var_50+6], ax
0x180005cb2  mov     rdx, rsi
0x180005cb5  movups  [rbp+var_30], xmm0
0x180005cb9  mov     [rbp+var_38], rax
0x180005cbd  movups  xmm0, xmmword ptr [rbp-40h]
0x180005cc1  mov     word ptr [rbp+var_50], 1
0x180005cc7  movups  xmm1, [rbp+var_50]
0x180005ccb  movups  [rbp+var_10], xmm0
0x180005ccf  movups  [rbp+var_20], xmm1
0x180005cd3  call    ??0?$shared_data@$00$0A@$0A@@details@tip2@@QEAA@AEAUtest_data_interface@12@AEBUtest_info@2@@Z; tip2::details::shared_data<1,0,0>::shared_data<1,0,0>(tip2::details::test_data_interface &,tip2::test_info const &)
0x180005cd8  lea     rax, ??_7?$merged_data@U_tip_DiagHealthTipTest@DiagHealth@CalliopeTipTests@@U123@@details@tip2@@6B@; const tip2::details::merged_data<CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest,CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest>::`vftable'
0x180005cdf  mov     dword ptr [rsi+110h], 0
0x180005ce9  mov     [rsi], rax
0x180005cec  lea     rcx, [rsi+8]
0x180005cf0  lea     rax, [rsi+10h]
0x180005cf4  mov     qword ptr [rsi+114h], 1
0x180005cff  mov     rdx, rdi
0x180005d02  mov     [rsi+108h], rax
0x180005d09  mov     dword ptr [rsi+120h], 1
0x180005d13  call    ?open_without_lock@?$shared_data@$00$0A@$0A@@details@tip2@@IEAAXPEAU_GUID@@@Z; tip2::details::shared_data<1,0,0>::open_without_lock(_GUID *)
0x180005d18  lea     r11, [rsp+80h+var_s0]
0x180005d20  mov     [r14], rsi
0x180005d23  mov     rbx, [r11+10h]
0x180005d27  mov     rax, r14
0x180005d2a  mov     rsi, [r11+18h]
0x180005d2e  mov     rdi, [r11+20h]
0x180005d32  mov     r14, [r11+28h]
0x180005d36  mov     rsp, r11
0x180005d39  pop     rbp
0x180005d3a  retn
0x180005d3b  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
