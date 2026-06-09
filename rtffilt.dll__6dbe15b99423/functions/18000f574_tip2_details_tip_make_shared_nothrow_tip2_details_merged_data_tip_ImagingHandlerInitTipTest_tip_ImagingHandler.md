# tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<_tip_ImagingHandlerInitTipTest,_tip_ImagingHandlerInitTipTest>,>(void)

- ea: `0x18000f574`
- end: `0x18000f63f`
- name: `??$tip_make_shared_nothrow@V?$merged_data@U_tip_ImagingHandlerInitTipTest@@U1@@details@tip2@@$$V@details@tip2@@YA?AV?$com_ptr_t@V?$merged_data@U_tip_ImagingHandlerInitTipTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ`
- size: `203`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180010b80`

## callees

- `0x180003a84`
- `0x18000c558`
- `0x18000f574`
- `0x18000f904`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000f586`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000f586`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_QWORD *__fastcall tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<_tip_ImagingHandlerInitTipTest,_tip_ImagingHandlerInitTipTest>,>(
        _QWORD *a1)
{
  wil::details::in1diag3 *v2; // rcx
  char *v3; // rbx
  _DWORD v5[2]; // [rsp+20h] [rbp-38h] BYREF
  const char *v6; // [rsp+28h] [rbp-30h]
  __int16 v7; // [rsp+30h] [rbp-28h]
  int v8; // [rsp+32h] [rbp-26h]
  __int16 v9; // [rsp+36h] [rbp-22h]
  __int128 v10; // [rsp+38h] [rbp-20h]
  __int64 v11; // [rsp+48h] [rbp-10h]

  v3 = (char *)CoTaskMemAlloc(0x140u);
  if ( !v3 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v2);
  *(_QWORD *)v3 = &tip2::details::test_data_interface::`vftable';
  v5[0] = 52895181;
  v5[1] = 16644;
  v6 = "ImagingHandlerInitTipTest";
  v7 = 1;
  v8 = 0;
  v9 = 0;
  v10 = 0;
  v11 = 0;
  tip2::details::shared_data<1,0,0>::shared_data<1,0,0>(v3 + 8, v3, v5);
  std::wstring::wstring(v3 + 272, &dword_18001CFD4);
  v3[304] = 1;
  *(_QWORD *)v3 = &tip2::details::merged_data<_tip_ImagingHandlerInitTipTest,_tip_ImagingHandlerInitTipTest>::`vftable';
  *((_DWORD *)v3 + 78) = 1;
  *((_QWORD *)v3 + 33) = v3 + 16;
  *a1 = v3;
  return a1;
}

```

## disassembly

```asm
0x18000f574  mov     [rsp+arg_0], rbx
0x18000f579  push    rdi
0x18000f57a  sub     rsp, 50h
0x18000f57e  mov     rdi, rcx
0x18000f581  mov     ecx, 140h; cb
0x18000f586  call    cs:__imp_CoTaskMemAlloc
0x18000f58c  mov     rbx, rax
0x18000f58f  test    rax, rax
0x18000f592  jz      loc_18000F639
0x18000f598  lea     rax, ??_7test_data_interface@details@tip2@@6B@; const tip2::details::test_data_interface::`vftable'
0x18000f59f  mov     [rbx], rax
0x18000f5a2  lea     rcx, aImaginghandler_4; "ImagingHandlerInitTipTest"
0x18000f5a9  xor     edx, edx
0x18000f5ab  mov     [rsp+58h+var_38], 3271DCDh
0x18000f5b3  mov     [rsp+58h+var_34], 4104h
0x18000f5bb  mov     [rsp+58h+var_30], rcx
0x18000f5c0  mov     [rsp+58h+var_28], 1
0x18000f5c7  mov     [rsp+58h+var_26], edx
0x18000f5cb  mov     [rsp+58h+var_22], dx
0x18000f5d0  xorps   xmm0, xmm0
0x18000f5d3  movdqu  [rsp+58h+var_20], xmm0
0x18000f5d9  mov     [rsp+58h+var_10], rdx
0x18000f5de  lea     rcx, [rbx+8]
0x18000f5e2  lea     r8, [rsp+58h+var_38]
0x18000f5e7  mov     rdx, rbx
0x18000f5ea  call    ??0?$shared_data@$00$0A@$0A@@details@tip2@@QEAA@AEAUtest_data_interface@12@AEBUtest_info@2@@Z; tip2::details::shared_data<1,0,0>::shared_data<1,0,0>(tip2::details::test_data_interface &,tip2::test_info const &)
0x18000f5ef  lea     rcx, [rbx+110h]
0x18000f5f6  lea     rdx, dword_18001CFD4
0x18000f5fd  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18000f602  mov     byte ptr [rbx+130h], 1
0x18000f609  lea     rax, ??_7?$merged_data@U_tip_ImagingHandlerInitTipTest@@U1@@details@tip2@@6B@; const tip2::details::merged_data<_tip_ImagingHandlerInitTipTest,_tip_ImagingHandlerInitTipTest>::`vftable'
0x18000f610  mov     [rbx], rax
0x18000f613  mov     dword ptr [rbx+138h], 1
0x18000f61d  lea     rax, [rbx+10h]
0x18000f621  mov     [rbx+108h], rax
0x18000f628  mov     [rdi], rbx
0x18000f62b  mov     rax, rdi
0x18000f62e  mov     rbx, [rsp+58h+arg_0]
0x18000f633  add     rsp, 50h
0x18000f637  pop     rdi
0x18000f638  retn
0x18000f639  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
