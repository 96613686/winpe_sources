# tip2::details::merged_data<_tip_AccessibilityDialogFlyoutLaunchTest,_tip_AccessibilityDialogFlyoutLaunchTest>::merged_data<_tip_AccessibilityDialogFlyoutLaunchTest,_tip_AccessibilityDialogFlyoutLaunchTest>(_GUID *)

- ea: `0x14001f1e0`
- end: `0x14001f289`
- name: `??0?$merged_data@U_tip_AccessibilityDialogFlyoutLaunchTest@@U1@@details@tip2@@QEAA@PEAU_GUID@@@Z`
- size: `169`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x14001ecbc`

## callees

- `0x14000c290`
- `0x140023104`

## string_xrefs

- `0x14001f216`: `AccessibilityDialogFlyoutLaunchTest`

## pseudocode

```c
__int64 __fastcall tip2::details::merged_data<_tip_AccessibilityDialogFlyoutLaunchTest,_tip_AccessibilityDialogFlyoutLaunchTest>::merged_data<_tip_AccessibilityDialogFlyoutLaunchTest,_tip_AccessibilityDialogFlyoutLaunchTest>(
        __int64 a1,
        __int64 a2)
{
  __int64 v4; // r8
  _DWORD v6[2]; // [rsp+20h] [rbp-38h] BYREF
  const char *v7; // [rsp+28h] [rbp-30h]
  __int16 v8; // [rsp+30h] [rbp-28h]
  int v9; // [rsp+32h] [rbp-26h]
  __int16 v10; // [rsp+36h] [rbp-22h]
  __int128 v11; // [rsp+38h] [rbp-20h]
  __int64 v12; // [rsp+48h] [rbp-10h]

  v6[0] = 36957240;
  v6[1] = 16640;
  *(_QWORD *)a1 = &winrt::impl::producers_base<AccessibilityDialog,std::tuple<winrt::Windows::Foundation::IInspectable,ILightDismissNotification>>::`vftable';
  v7 = "AccessibilityDialogFlyoutLaunchTest";
  v9 = 0;
  v10 = 0;
  v8 = 2;
  v11 = 0;
  v12 = 0;
  tip2::details::shared_data<1,0,0>::shared_data<1,0,0>(a1 + 8, a1, v6);
  *(_DWORD *)(a1 + 272) = 1;
  *(_QWORD *)a1 = &tip2::details::merged_data<_tip_AccessibilityDialogFlyoutLaunchTest,_tip_AccessibilityDialogFlyoutLaunchTest>::`vftable';
  *(_QWORD *)(a1 + 264) = a1 + 16;
  tip2::details::shared_data<1,0,0>::open_without_lock(a1 + 8, a2, v4);
  return a1;
}

```

## disassembly

```asm
0x14001f1e0  mov     r11, rsp
0x14001f1e3  mov     [r11+8], rbx
0x14001f1e7  mov     [r11+10h], rsi
0x14001f1eb  push    rdi
0x14001f1ec  sub     rsp, 50h
0x14001f1f0  mov     rsi, rcx
0x14001f1f3  mov     [rsp+58h+var_38], 233EC38h
0x14001f1fb  mov     rdi, rdx
0x14001f1fe  mov     [rsp+58h+var_34], 4100h
0x14001f206  xor     edx, edx
0x14001f208  lea     rax, ??_7?$producers_base@VAccessibilityDialog@@V?$tuple@UIInspectable@Foundation@Windows@winrt@@UILightDismissNotification@@@std@@@impl@winrt@@6B@; const winrt::impl::producers_base<AccessibilityDialog,std::tuple<winrt::Windows::Foundation::IInspectable,ILightDismissNotification>>::`vftable'
0x14001f20f  mov     [rcx], rax
0x14001f212  lea     r8, [r11-38h]
0x14001f216  lea     rcx, aAccessibilityd; "AccessibilityDialogFlyoutLaunchTest"
0x14001f21d  xorps   xmm0, xmm0
0x14001f220  mov     [r11-30h], rcx
0x14001f224  lea     rcx, [rsi+8]
0x14001f228  mov     [rsp+58h+var_26], edx
0x14001f22c  mov     [rsp+58h+var_22], dx
0x14001f231  mov     [rsp+58h+var_28], 2
0x14001f238  movdqu  [rsp+58h+var_20], xmm0
0x14001f23e  mov     [r11-10h], rdx
0x14001f242  mov     rdx, rsi
0x14001f245  call    ??0?$shared_data@$00$0A@$0A@@details@tip2@@QEAA@AEAUtest_data_interface@12@AEBUtest_info@2@@Z; tip2::details::shared_data<1,0,0>::shared_data<1,0,0>(tip2::details::test_data_interface &,tip2::test_info const &)
0x14001f24a  lea     rax, ??_7?$merged_data@U_tip_AccessibilityDialogFlyoutLaunchTest@@U1@@details@tip2@@6B@; const tip2::details::merged_data<_tip_AccessibilityDialogFlyoutLaunchTest,_tip_AccessibilityDialogFlyoutLaunchTest>::`vftable'
0x14001f251  mov     dword ptr [rsi+110h], 1
0x14001f25b  mov     [rsi], rax
0x14001f25e  lea     rcx, [rsi+8]
0x14001f262  lea     rax, [rsi+10h]
0x14001f266  mov     rdx, rdi
0x14001f269  mov     [rsi+108h], rax
0x14001f270  call    ?open_without_lock@?$shared_data@$00$0A@$0A@@details@tip2@@IEAAXPEAU_GUID@@@Z; tip2::details::shared_data<1,0,0>::open_without_lock(_GUID *)
0x14001f275  mov     rbx, [rsp+58h+arg_0]
0x14001f27a  mov     rax, rsi
0x14001f27d  mov     rsi, [rsp+58h+arg_8]
0x14001f282  add     rsp, 50h
0x14001f286  pop     rdi
0x14001f287  retn
```
