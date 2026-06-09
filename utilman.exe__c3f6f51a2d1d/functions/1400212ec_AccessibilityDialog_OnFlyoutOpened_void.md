# AccessibilityDialog::OnFlyoutOpened(void)

- ea: `0x1400212ec`
- end: `0x14002135a`
- name: `?OnFlyoutOpened@AccessibilityDialog@@AEAAXXZ`
- size: `110`
- prototype: `void __fastcall(AccessibilityDialog *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callers

- `0x14001d26c`

## callees

- `0x14000ccdc`
- `0x14001e51c`
- `0x14001fae4`
- `0x14001fe00`
- `0x140020d98`
- `0x14002284c`
- `0x140022ea8`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall AccessibilityDialog::OnFlyoutOpened(AccessibilityDialog *this)
{
  _QWORD *v2; // rax
  BOOL IsRightToLeft; // [rsp+30h] [rbp+8h] BYREF
  __int64 v4; // [rsp+38h] [rbp+10h] BYREF
  __int64 v5; // [rsp+40h] [rbp+18h] BYREF

  AccessibilityDialog::SetupLightDismissLayer(this);
  v2 = (_QWORD *)winrt::impl::consume_Windows_UI_Core_ICoreWindowStatic<winrt::Windows::UI::Core::ICoreWindowStatic>::GetForCurrentThread(
                   (char *)this + 120,
                   &v5);
  winrt::impl::as<winrt::Windows::UI::Xaml::FrameworkElement,winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type,0>(
    &v4,
    *v2);
  winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(&v5);
  IsRightToLeft = anonymous_namespace_::IsRightToLeft();
  winrt::impl::consume_Windows_UI_Xaml_IFrameworkElement<winrt::Windows::UI::Xaml::IFrameworkElement>::FlowDirection(
    &v4,
    &IsRightToLeft);
  tip2::tip_test<tip2::details::merged_data<_tip_AccessibilityDialogFlyoutLaunchTest,_tip_AccessibilityDialogFlyoutLaunchTest>>::complete((char *)this + 320);
  winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(&v4);
}

```

## disassembly

```asm
0x1400212ec  push    rbx
0x1400212ee  sub     rsp, 20h
0x1400212f2  mov     rbx, rcx
0x1400212f5  call    ?SetupLightDismissLayer@AccessibilityDialog@@AEAAXXZ; AccessibilityDialog::SetupLightDismissLayer(void)
0x1400212fa  lea     rcx, [rbx+78h]
0x1400212fe  lea     rdx, [rsp+28h+arg_10]
0x140021303  call    ?GetForCurrentThread@?$consume_Windows_UI_Core_ICoreWindowStatic@UICoreWindowStatic@Core@UI@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_UI_Core_ICoreWindowStatic<winrt::Windows::UI::Core::ICoreWindowStatic>::GetForCurrentThread(void)
0x140021308  nop
0x140021309  mov     rdx, [rax]
0x14002130c  lea     rcx, [rsp+28h+arg_8]
0x140021311  call    ??$as@UFrameworkElement@Xaml@UI@Windows@winrt@@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@5@$0A@@impl@winrt@@YA?AUFrameworkElement@Xaml@UI@Windows@1@PEAUtype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@01@@Z; winrt::impl::as<winrt::Windows::UI::Xaml::FrameworkElement,winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type,0>(winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type *)
0x140021316  nop
0x140021317  lea     rcx, [rsp+28h+arg_10]
0x14002131c  call    ??1?$com_ptr@UIWeakReferenceSource@impl@winrt@@@winrt@@QEAA@XZ; winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(void)
0x140021321  call    _anonymous_namespace___IsRightToLeft
0x140021326  movzx   eax, al
0x140021329  mov     [rsp+28h+arg_0], eax
0x14002132d  lea     rdx, [rsp+28h+arg_0]
0x140021332  lea     rcx, [rsp+28h+arg_8]
0x140021337  call    ?FlowDirection@?$consume_Windows_UI_Xaml_IFrameworkElement@UIFrameworkElement@Xaml@UI@Windows@winrt@@@impl@winrt@@QEBA@AEBW40Xaml@UI@Windows@3@@Z; winrt::impl::consume_Windows_UI_Xaml_IFrameworkElement<winrt::Windows::UI::Xaml::IFrameworkElement>::FlowDirection(winrt::Windows::UI::Xaml::FlowDirection const &)
0x14002133c  lea     rcx, [rbx+140h]
0x140021343  call    ?complete@?$tip_test@V?$merged_data@U_tip_AccessibilityDialogFlyoutLaunchTest@@U1@@details@tip2@@@tip2@@QEAAXXZ; tip2::tip_test<tip2::details::merged_data<_tip_AccessibilityDialogFlyoutLaunchTest,_tip_AccessibilityDialogFlyoutLaunchTest>>::complete(void)
0x140021348  nop
0x140021349  lea     rcx, [rsp+28h+arg_8]
0x14002134e  call    ??1?$com_ptr@UIWeakReferenceSource@impl@winrt@@@winrt@@QEAA@XZ; winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(void)
0x140021353  add     rsp, 20h
0x140021357  pop     rbx
0x140021358  retn
```
