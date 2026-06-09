# tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<_tip_AccessibilityDialogFlyoutLaunchTest,_tip_AccessibilityDialogFlyoutLaunchTest>,>(void)

- ea: `0x14000bfe0`
- end: `0x14000c098`
- name: `??$tip_make_shared_nothrow@V?$merged_data@U_tip_AccessibilityDialogFlyoutLaunchTest@@U1@@details@tip2@@$$V@details@tip2@@YA?AV?$com_ptr_t@V?$merged_data@U_tip_AccessibilityDialogFlyoutLaunchTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ`
- size: `184`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x14000ffc0`

## callees

- `0x140009694`
- `0x14000bfe0`
- `0x14000c290`

## import_xrefs

- `ole32!CoTaskMemAlloc` at `0x14000bff2`
- `ole32!CoTaskMemAlloc` at `0x14000bff2`

## string_xrefs

- `0x14000c014`: `AccessibilityDialogFlyoutLaunchTest`

## pseudocode

```c
_QWORD *__fastcall tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<_tip_AccessibilityDialogFlyoutLaunchTest,_tip_AccessibilityDialogFlyoutLaunchTest>,>(
        _QWORD *a1)
{
  wil::details::in1diag3 *v2; // rcx
  _DWORD *v3; // rbx
  _QWORD *result; // rax
  _DWORD v5[2]; // [rsp+20h] [rbp-38h] BYREF
  const char *v6; // [rsp+28h] [rbp-30h]
  __int16 v7; // [rsp+30h] [rbp-28h]
  int v8; // [rsp+32h] [rbp-26h]
  __int16 v9; // [rsp+36h] [rbp-22h]
  __int128 v10; // [rsp+38h] [rbp-20h]
  __int64 v11; // [rsp+48h] [rbp-10h]

  v3 = CoTaskMemAlloc(0x118u);
  if ( !v3 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v2);
  v5[0] = 36957240;
  v8 = 0;
  v6 = "AccessibilityDialogFlyoutLaunchTest";
  v9 = 0;
  v11 = 0;
  *(_QWORD *)v3 = &winrt::impl::producers_base<AccessibilityDialog,std::tuple<winrt::Windows::Foundation::IInspectable,ILightDismissNotification>>::`vftable';
  v5[1] = 16640;
  v7 = 2;
  v10 = 0;
  tip2::details::shared_data<1,0,0>::shared_data<1,0,0>(v3 + 2, v3, v5);
  v3[68] = 1;
  *(_QWORD *)v3 = &tip2::details::merged_data<_tip_AccessibilityDialogFlyoutLaunchTest,_tip_AccessibilityDialogFlyoutLaunchTest>::`vftable';
  *((_QWORD *)v3 + 33) = v3 + 4;
  result = a1;
  *a1 = v3;
  return result;
}

```

## disassembly

```asm
0x14000bfe0  mov     [rsp+arg_0], rbx
0x14000bfe5  push    rdi
0x14000bfe6  sub     rsp, 50h
0x14000bfea  mov     rdi, rcx
0x14000bfed  mov     ecx, 118h; cb
0x14000bff2  call    cs:__imp_CoTaskMemAlloc
0x14000bff9  nop     dword ptr [rax+rax+00h]
0x14000bffe  mov     rbx, rax
0x14000c001  test    rax, rax
0x14000c004  jz      loc_14000C092
0x14000c00a  xor     edx, edx
0x14000c00c  mov     [rsp+58h+var_38], 233EC38h
0x14000c014  lea     rcx, aAccessibilityd; "AccessibilityDialogFlyoutLaunchTest"
0x14000c01b  mov     [rsp+58h+var_26], edx
0x14000c01f  mov     [rsp+58h+var_30], rcx
0x14000c024  lea     rax, ??_7?$producers_base@VAccessibilityDialog@@V?$tuple@UIInspectable@Foundation@Windows@winrt@@UILightDismissNotification@@@std@@@impl@winrt@@6B@; const winrt::impl::producers_base<AccessibilityDialog,std::tuple<winrt::Windows::Foundation::IInspectable,ILightDismissNotification>>::`vftable'
0x14000c02b  mov     [rsp+58h+var_22], dx
0x14000c030  lea     rcx, [rbx+8]
0x14000c034  mov     [rsp+58h+var_10], rdx
0x14000c039  lea     r8, [rsp+58h+var_38]
0x14000c03e  xorps   xmm0, xmm0
0x14000c041  mov     [rbx], rax
0x14000c044  mov     rdx, rbx
0x14000c047  mov     [rsp+58h+var_34], 4100h
0x14000c04f  mov     [rsp+58h+var_28], 2
0x14000c056  movdqu  [rsp+58h+var_20], xmm0
0x14000c05c  call    ??0?$shared_data@$00$0A@$0A@@details@tip2@@QEAA@AEAUtest_data_interface@12@AEBUtest_info@2@@Z; tip2::details::shared_data<1,0,0>::shared_data<1,0,0>(tip2::details::test_data_interface &,tip2::test_info const &)
0x14000c061  lea     rax, ??_7?$merged_data@U_tip_AccessibilityDialogFlyoutLaunchTest@@U1@@details@tip2@@6B@; const tip2::details::merged_data<_tip_AccessibilityDialogFlyoutLaunchTest,_tip_AccessibilityDialogFlyoutLaunchTest>::`vftable'
0x14000c068  mov     dword ptr [rbx+110h], 1
0x14000c072  mov     [rbx], rax
0x14000c075  lea     rax, [rbx+10h]
0x14000c079  mov     [rbx+108h], rax
0x14000c080  mov     rax, rdi
0x14000c083  mov     [rdi], rbx
0x14000c086  mov     rbx, [rsp+58h+arg_0]
0x14000c08b  add     rsp, 50h
0x14000c08f  pop     rdi
0x14000c090  retn
0x14000c092  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
