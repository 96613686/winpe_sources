# AccessibilityDialog::~AccessibilityDialog(void)

- ea: `0x14000d06c`
- end: `0x14000d179`
- name: `??1AccessibilityDialog@@UEAA@XZ`
- size: `269`
- prototype: `void __fastcall(AccessibilityDialog *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14000d400`

## callees

- `0x14000ccb4`
- `0x14000ccdc`
- `0x14000cd18`
- `0x14000cd74`
- `0x14000cdd0`
- `0x14000ce2c`
- `0x14000cf04`
- `0x14000cf88`
- `0x14000cfa0`

## pseudocode

```c
void __fastcall AccessibilityDialog::~AccessibilityDialog(AccessibilityDialog *this)
{
  tip2::tip_test<tip2::details::merged_data<_tip_AccessibilityDialogFlyoutLaunchTest,_tip_AccessibilityDialogFlyoutLaunchTest>>::~tip_test<tip2::details::merged_data<_tip_AccessibilityDialogFlyoutLaunchTest,_tip_AccessibilityDialogFlyoutLaunchTest>>((char *)this + 320);
  wil::com_ptr_t<ILightDismissProvider,wil::err_exception_policy>::~com_ptr_t<ILightDismissProvider,wil::err_exception_policy>((char *)this + 312);
  __1__event_revoker_UIFrameworkElement_Xaml_UI_Windows_winrt___MP8type___abi_UIFrameworkElement_Xaml_UI_Windows_winrt__X_impl_5_EAAHUevent_token_5___E1___96785__BBGA_AA_impl_winrt__QEAA_XZ((char *)this + 288);
  __1__event_revoker_UIFrameworkElement_Xaml_UI_Windows_winrt___MP8type___abi_UIFrameworkElement_Xaml_UI_Windows_winrt__X_impl_5_EAAHUevent_token_5___E1___96785__BBGA_AA_impl_winrt__QEAA_XZ((char *)this + 272);
  __1__event_revoker_UIFlyoutBase_Primitives_Controls_Xaml_UI_Windows_winrt___MP8type___abi_UIFlyoutBase_Primitives_Controls_Xaml_UI_Windows_winrt__X_impl_7_EAAHUevent_token_7___E1___989impl_7__BEI_AA_impl_winrt__QEAA_XZ((char *)this + 256);
  __1__event_revoker_UIFlyoutBase_Primitives_Controls_Xaml_UI_Windows_winrt___MP8type___abi_UIFlyoutBase_Primitives_Controls_Xaml_UI_Windows_winrt__X_impl_7_EAAHUevent_token_7___E1___989impl_7__BFI_AA_impl_winrt__QEAA_XZ((char *)this + 240);
  __1__event_revoker_UIToggleSwitch_Controls_Xaml_UI_Windows_winrt___MP8type___abi_UIToggleSwitch_Controls_Xaml_UI_Windows_winrt__X_impl_6_EAAHUevent_token_6___E1___97896__BLA_AA_impl_winrt__QEAA_XZ((char *)this + 224);
  __1__event_revoker_UIToggleSwitch_Controls_Xaml_UI_Windows_winrt___MP8type___abi_UIToggleSwitch_Controls_Xaml_UI_Windows_winrt__X_impl_6_EAAHUevent_token_6___E1___97896__BLA_AA_impl_winrt__QEAA_XZ((char *)this + 208);
  __1__event_revoker_UIToggleSwitch_Controls_Xaml_UI_Windows_winrt___MP8type___abi_UIToggleSwitch_Controls_Xaml_UI_Windows_winrt__X_impl_6_EAAHUevent_token_6___E1___97896__BLA_AA_impl_winrt__QEAA_XZ((char *)this + 192);
  __1__event_revoker_UIToggleSwitch_Controls_Xaml_UI_Windows_winrt___MP8type___abi_UIToggleSwitch_Controls_Xaml_UI_Windows_winrt__X_impl_6_EAAHUevent_token_6___E1___97896__BLA_AA_impl_winrt__QEAA_XZ((char *)this + 176);
  __1__event_revoker_UIToggleSwitch_Controls_Xaml_UI_Windows_winrt___MP8type___abi_UIToggleSwitch_Controls_Xaml_UI_Windows_winrt__X_impl_6_EAAHUevent_token_6___E1___97896__BLA_AA_impl_winrt__QEAA_XZ((char *)this + 160);
  __1__event_revoker_UIToggleSwitch_Controls_Xaml_UI_Windows_winrt___MP8type___abi_UIToggleSwitch_Controls_Xaml_UI_Windows_winrt__X_impl_6_EAAHUevent_token_6___E1___97896__BLA_AA_impl_winrt__QEAA_XZ((char *)this + 144);
  __1__event_revoker_UIToggleSwitch_Controls_Xaml_UI_Windows_winrt___MP8type___abi_UIToggleSwitch_Controls_Xaml_UI_Windows_winrt__X_impl_6_EAAHUevent_token_6___E1___97896__BLA_AA_impl_winrt__QEAA_XZ((char *)this + 128);
  winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>((_QWORD *)this + 15);
  winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>((_QWORD *)this + 14);
  winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>((_QWORD *)this + 13);
  winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>((_QWORD *)this + 12);
  winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>((_QWORD *)this + 11);
  winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>((_QWORD *)this + 10);
  winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>((_QWORD *)this + 9);
  winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>((_QWORD *)this + 8);
  winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>((_QWORD *)this + 7);
  std::unique_ptr<XamlUI>::~unique_ptr<XamlUI>((char *)this + 48);
  winrt::impl::root_implements<AccessibilityDialog,winrt::Windows::Foundation::IInspectable,ILightDismissNotification>::~root_implements<AccessibilityDialog,winrt::Windows::Foundation::IInspectable,ILightDismissNotification>((char *)this + 16);
}

```

## disassembly

```asm
0x14000d06c  push    rbx
0x14000d06e  sub     rsp, 20h
0x14000d072  mov     rbx, rcx
0x14000d075  add     rcx, 140h
0x14000d07c  call    ??1?$tip_test@V?$merged_data@U_tip_AccessibilityDialogFlyoutLaunchTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::tip_test<tip2::details::merged_data<_tip_AccessibilityDialogFlyoutLaunchTest,_tip_AccessibilityDialogFlyoutLaunchTest>>::~tip_test<tip2::details::merged_data<_tip_AccessibilityDialogFlyoutLaunchTest,_tip_AccessibilityDialogFlyoutLaunchTest>>(void)
0x14000d081  lea     rcx, [rbx+138h]
0x14000d088  call    ??1?$com_ptr_t@UILightDismissProvider@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ILightDismissProvider,wil::err_exception_policy>::~com_ptr_t<ILightDismissProvider,wil::err_exception_policy>(void)
0x14000d08d  lea     rcx, [rbx+120h]
0x14000d094  call    ??1?$event_revoker@UIFrameworkElement@Xaml@UI@Windows@winrt@@$MP8type@?$abi@UIFrameworkElement@Xaml@UI@Windows@winrt@@X@impl@5@EAAHUevent_token@5@@_E1??_96785@$BBGA@AA@impl@winrt@@QEAA@XZ
0x14000d099  lea     rcx, [rbx+110h]
0x14000d0a0  call    ??1?$event_revoker@UIFrameworkElement@Xaml@UI@Windows@winrt@@$MP8type@?$abi@UIFrameworkElement@Xaml@UI@Windows@winrt@@X@impl@5@EAAHUevent_token@5@@_E1??_96785@$BBGA@AA@impl@winrt@@QEAA@XZ
0x14000d0a5  lea     rcx, [rbx+100h]
0x14000d0ac  call    ??1?$event_revoker@UIFlyoutBase@Primitives@Controls@Xaml@UI@Windows@winrt@@$MP8type@?$abi@UIFlyoutBase@Primitives@Controls@Xaml@UI@Windows@winrt@@X@impl@7@EAAHUevent_token@7@@_E1??_989impl@7@$BEI@AA@impl@winrt@@QEAA@XZ
0x14000d0b1  lea     rcx, [rbx+0F0h]
0x14000d0b8  call    ??1?$event_revoker@UIFlyoutBase@Primitives@Controls@Xaml@UI@Windows@winrt@@$MP8type@?$abi@UIFlyoutBase@Primitives@Controls@Xaml@UI@Windows@winrt@@X@impl@7@EAAHUevent_token@7@@_E1??_989impl@7@$BFI@AA@impl@winrt@@QEAA@XZ
0x14000d0bd  lea     rcx, [rbx+0E0h]
0x14000d0c4  call    ??1?$event_revoker@UIToggleSwitch@Controls@Xaml@UI@Windows@winrt@@$MP8type@?$abi@UIToggleSwitch@Controls@Xaml@UI@Windows@winrt@@X@impl@6@EAAHUevent_token@6@@_E1??_97896@$BLA@AA@impl@winrt@@QEAA@XZ
0x14000d0c9  lea     rcx, [rbx+0D0h]
0x14000d0d0  call    ??1?$event_revoker@UIToggleSwitch@Controls@Xaml@UI@Windows@winrt@@$MP8type@?$abi@UIToggleSwitch@Controls@Xaml@UI@Windows@winrt@@X@impl@6@EAAHUevent_token@6@@_E1??_97896@$BLA@AA@impl@winrt@@QEAA@XZ
0x14000d0d5  lea     rcx, [rbx+0C0h]
0x14000d0dc  call    ??1?$event_revoker@UIToggleSwitch@Controls@Xaml@UI@Windows@winrt@@$MP8type@?$abi@UIToggleSwitch@Controls@Xaml@UI@Windows@winrt@@X@impl@6@EAAHUevent_token@6@@_E1??_97896@$BLA@AA@impl@winrt@@QEAA@XZ
0x14000d0e1  lea     rcx, [rbx+0B0h]
0x14000d0e8  call    ??1?$event_revoker@UIToggleSwitch@Controls@Xaml@UI@Windows@winrt@@$MP8type@?$abi@UIToggleSwitch@Controls@Xaml@UI@Windows@winrt@@X@impl@6@EAAHUevent_token@6@@_E1??_97896@$BLA@AA@impl@winrt@@QEAA@XZ
0x14000d0ed  lea     rcx, [rbx+0A0h]
0x14000d0f4  call    ??1?$event_revoker@UIToggleSwitch@Controls@Xaml@UI@Windows@winrt@@$MP8type@?$abi@UIToggleSwitch@Controls@Xaml@UI@Windows@winrt@@X@impl@6@EAAHUevent_token@6@@_E1??_97896@$BLA@AA@impl@winrt@@QEAA@XZ
0x14000d0f9  lea     rcx, [rbx+90h]
0x14000d100  call    ??1?$event_revoker@UIToggleSwitch@Controls@Xaml@UI@Windows@winrt@@$MP8type@?$abi@UIToggleSwitch@Controls@Xaml@UI@Windows@winrt@@X@impl@6@EAAHUevent_token@6@@_E1??_97896@$BLA@AA@impl@winrt@@QEAA@XZ
0x14000d105  lea     rcx, [rbx+80h]
0x14000d10c  call    ??1?$event_revoker@UIToggleSwitch@Controls@Xaml@UI@Windows@winrt@@$MP8type@?$abi@UIToggleSwitch@Controls@Xaml@UI@Windows@winrt@@X@impl@6@EAAHUevent_token@6@@_E1??_97896@$BLA@AA@impl@winrt@@QEAA@XZ
0x14000d111  lea     rcx, [rbx+78h]
0x14000d115  call    ??1?$com_ptr@UIWeakReferenceSource@impl@winrt@@@winrt@@QEAA@XZ; winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(void)
0x14000d11a  lea     rcx, [rbx+70h]
0x14000d11e  call    ??1?$com_ptr@UIWeakReferenceSource@impl@winrt@@@winrt@@QEAA@XZ; winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(void)
0x14000d123  lea     rcx, [rbx+68h]
0x14000d127  call    ??1?$com_ptr@UIWeakReferenceSource@impl@winrt@@@winrt@@QEAA@XZ; winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(void)
0x14000d12c  lea     rcx, [rbx+60h]
0x14000d130  call    ??1?$com_ptr@UIWeakReferenceSource@impl@winrt@@@winrt@@QEAA@XZ; winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(void)
0x14000d135  lea     rcx, [rbx+58h]
0x14000d139  call    ??1?$com_ptr@UIWeakReferenceSource@impl@winrt@@@winrt@@QEAA@XZ; winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(void)
0x14000d13e  lea     rcx, [rbx+50h]
0x14000d142  call    ??1?$com_ptr@UIWeakReferenceSource@impl@winrt@@@winrt@@QEAA@XZ; winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(void)
0x14000d147  lea     rcx, [rbx+48h]
0x14000d14b  call    ??1?$com_ptr@UIWeakReferenceSource@impl@winrt@@@winrt@@QEAA@XZ; winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(void)
0x14000d150  lea     rcx, [rbx+40h]
0x14000d154  call    ??1?$com_ptr@UIWeakReferenceSource@impl@winrt@@@winrt@@QEAA@XZ; winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(void)
0x14000d159  lea     rcx, [rbx+38h]
0x14000d15d  call    ??1?$com_ptr@UIWeakReferenceSource@impl@winrt@@@winrt@@QEAA@XZ; winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(void)
0x14000d162  lea     rcx, [rbx+30h]
0x14000d166  call    ??1?$unique_ptr@VXamlUI@@U?$default_delete@VXamlUI@@@std@@@std@@QEAA@XZ; std::unique_ptr<XamlUI>::~unique_ptr<XamlUI>(void)
0x14000d16b  lea     rcx, [rbx+10h]
0x14000d16f  add     rsp, 20h
0x14000d173  pop     rbx
0x14000d174  jmp     ??1?$root_implements@VAccessibilityDialog@@UIInspectable@Foundation@Windows@winrt@@UILightDismissNotification@@@impl@winrt@@MEAA@XZ; winrt::impl::root_implements<AccessibilityDialog,winrt::Windows::Foundation::IInspectable,ILightDismissNotification>::~root_implements<AccessibilityDialog,winrt::Windows::Foundation::IInspectable,ILightDismissNotification>(void)
```
