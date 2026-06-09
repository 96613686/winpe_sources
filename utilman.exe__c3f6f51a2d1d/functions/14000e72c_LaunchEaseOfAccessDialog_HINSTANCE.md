# LaunchEaseOfAccessDialog(HINSTANCE__ *)

- ea: `0x14000e72c`
- end: `0x14000e813`
- name: `?LaunchEaseOfAccessDialog@@YAXPEAUHINSTANCE__@@@Z`
- size: `231`
- prototype: `void __fastcall(HINSTANCE)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140012f54`

## callees

- `0x140002760`
- `0x140002fa0`
- `0x140009ee0`
- `0x14000c354`
- `0x14000c3f4`
- `0x14000ccdc`
- `0x14000ccf8`
- `0x14000cf60`
- `0x14000d6b0`
- `0x14000ffc0`
- `0x1400121cc`
- `0x140022098`
- `0x140024aa8`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
void __fastcall LaunchEaseOfAccessDialog(HINSTANCE a1)
{
  _QWORD *v2; // rax
  _QWORD *v3; // rbx
  __int128 v4; // [rsp+20h] [rbp-50h] BYREF
  _BYTE v5[64]; // [rsp+30h] [rbp-40h] BYREF
  _QWORD *v6; // [rsp+88h] [rbp+18h] BYREF
  __int64 v7; // [rsp+90h] [rbp+20h] BYREF

  v6 = 0;
  v2 = (_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_AccessibilityDialogFlyoutLaunchTest,_tip_AccessibilityDialogFlyoutLaunchTest>>::ensure_data(&v6);
  tip2::details::shared_data<1,0,0>::start(*v2 + 8LL, &v4);
  tip2::test_watcher<tip2::details::merged_data<_tip_AccessibilityDialogFlyoutLaunchTest,_tip_AccessibilityDialogFlyoutLaunchTest>>::test_watcher<tip2::details::merged_data<_tip_AccessibilityDialogFlyoutLaunchTest,_tip_AccessibilityDialogFlyoutLaunchTest>>(
    v5,
    &v6);
  wil::com_ptr_t<tip2::details::merged_data<_tip_AccessibilityDialogFlyoutLaunchTest,_tip_AccessibilityDialogFlyoutLaunchTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_AccessibilityDialogFlyoutLaunchTest,_tip_AccessibilityDialogFlyoutLaunchTest>,wil::err_returncode_policy>(&v6);
  InitializeXamlIslands(&v7);
  *(_QWORD *)&v4 = &v7;
  BYTE8(v4) = 1;
  v3 = operator new(0x148u);
  memset_0(v3, 0, 0x148u);
  AccessibilityDialog::AccessibilityDialog((AccessibilityDialog *)v3);
  *v3 = &winrt::impl::heap_implements<AccessibilityDialog>::`vftable'{for `winrt::impl::producers_base<AccessibilityDialog,std::tuple<winrt::Windows::Foundation::IInspectable,ILightDismissNotification>>'};
  v3[2] = &winrt::impl::heap_implements<AccessibilityDialog>::`vftable'{for `winrt::impl::root_implements<AccessibilityDialog,winrt::Windows::Foundation::IInspectable,ILightDismissNotification>'};
  v6 = v3;
  AccessibilityDialog::Run((AccessibilityDialog *)v3, a1);
  winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref((__int64 *)&v6);
  winrt::impl::consume_Windows_Foundation_IClosable<winrt::Windows::UI::Xaml::Hosting::DesktopWindowXamlSource>::Close(&v7);
  winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(&v7);
  tip2::test_watcher<tip2::details::merged_data<_tip_AccessibilityDialogFlyoutLaunchTest,_tip_AccessibilityDialogFlyoutLaunchTest>>::~test_watcher<tip2::details::merged_data<_tip_AccessibilityDialogFlyoutLaunchTest,_tip_AccessibilityDialogFlyoutLaunchTest>>(v5);
}

```

## disassembly

```asm
0x14000e72c  mov     [rsp-8+arg_0], rbx
0x14000e731  mov     [rsp-8+arg_18], rdi
0x14000e736  push    rbp
0x14000e737  mov     rbp, rsp
0x14000e73a  sub     rsp, 70h
0x14000e73e  mov     rdi, rcx
0x14000e741  mov     [rbp+arg_8], 0
0x14000e749  lea     rcx, [rbp+arg_8]
0x14000e74d  call    ?ensure_data@?$tip_test@V?$merged_data@U_tip_AccessibilityDialogFlyoutLaunchTest@@U1@@details@tip2@@@tip2@@AEBAAEAV?$com_ptr_t@V?$merged_data@U_tip_AccessibilityDialogFlyoutLaunchTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ; tip2::tip_test<tip2::details::merged_data<_tip_AccessibilityDialogFlyoutLaunchTest,_tip_AccessibilityDialogFlyoutLaunchTest>>::ensure_data(void)
0x14000e752  mov     rcx, [rax]
0x14000e755  add     rcx, 8
0x14000e759  lea     rdx, [rbp+var_50]
0x14000e75d  call    ?start@?$shared_data@$00$0A@$0A@@details@tip2@@AEAA?AU_GUID@@XZ; tip2::details::shared_data<1,0,0>::start(void)
0x14000e762  lea     rdx, [rbp+arg_8]
0x14000e766  lea     rcx, [rbp+var_40]
0x14000e76a  call    ??0?$test_watcher@V?$merged_data@U_tip_AccessibilityDialogFlyoutLaunchTest@@U1@@details@tip2@@@tip2@@IEAA@AEAV?$com_ptr_t@V?$merged_data@U_tip_AccessibilityDialogFlyoutLaunchTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@@Z; tip2::test_watcher<tip2::details::merged_data<_tip_AccessibilityDialogFlyoutLaunchTest,_tip_AccessibilityDialogFlyoutLaunchTest>>::test_watcher<tip2::details::merged_data<_tip_AccessibilityDialogFlyoutLaunchTest,_tip_AccessibilityDialogFlyoutLaunchTest>>(wil::com_ptr_t<tip2::details::merged_data<_tip_AccessibilityDialogFlyoutLaunchTest,_tip_AccessibilityDialogFlyoutLaunchTest>,wil::err_returncode_policy> &)
0x14000e76f  lea     rcx, [rbp+arg_8]
0x14000e773  call    ??1?$com_ptr_t@V?$merged_data@U_tip_AccessibilityDialogFlyoutLaunchTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_AccessibilityDialogFlyoutLaunchTest,_tip_AccessibilityDialogFlyoutLaunchTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_AccessibilityDialogFlyoutLaunchTest,_tip_AccessibilityDialogFlyoutLaunchTest>,wil::err_returncode_policy>(void)
0x14000e778  nop
0x14000e779  lea     rcx, [rbp+arg_10]
0x14000e77d  call    ?InitializeXamlIslands@@YA?AUWindowsXamlManager@Hosting@Xaml@UI@Windows@winrt@@XZ; InitializeXamlIslands(void)
0x14000e782  nop
0x14000e783  lea     rax, [rbp+arg_10]
0x14000e787  mov     [rbp+var_50], rax
0x14000e78b  mov     [rbp+var_48], 1
0x14000e78f  mov     ecx, 148h; Size
0x14000e794  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14000e799  mov     rbx, rax
0x14000e79c  xor     edx, edx; Val
0x14000e79e  mov     r8d, 148h; Size
0x14000e7a4  mov     rcx, rax; void *
0x14000e7a7  call    memset_0
0x14000e7ac  mov     rcx, rbx; this
0x14000e7af  call    ??0AccessibilityDialog@@QEAA@XZ; AccessibilityDialog::AccessibilityDialog(void)
0x14000e7b4  lea     r10, ??_7?$heap_implements@VAccessibilityDialog@@@impl@winrt@@6B?$producers_base@VAccessibilityDialog@@V?$tuple@UIInspectable@Foundation@Windows@winrt@@UILightDismissNotification@@@std@@@12@@; const winrt::impl::heap_implements<AccessibilityDialog>::`vftable'{for `winrt::impl::producers_base<AccessibilityDialog,std::tuple<winrt::Windows::Foundation::IInspectable,ILightDismissNotification>>'}
0x14000e7bb  mov     [rbx], r10
0x14000e7be  lea     rax, ??_7?$heap_implements@VAccessibilityDialog@@@impl@winrt@@6B?$root_implements@VAccessibilityDialog@@UIInspectable@Foundation@Windows@winrt@@UILightDismissNotification@@@12@@; const winrt::impl::heap_implements<AccessibilityDialog>::`vftable'{for `winrt::impl::root_implements<AccessibilityDialog,winrt::Windows::Foundation::IInspectable,ILightDismissNotification>'}
0x14000e7c5  mov     [rbx+10h], rax
0x14000e7c9  mov     [rbp+arg_8], rbx
0x14000e7cd  mov     rdx, rdi; HINSTANCE
0x14000e7d0  mov     rcx, rbx; this
0x14000e7d3  call    ?Run@AccessibilityDialog@@QEAAXPEAUHINSTANCE__@@@Z; AccessibilityDialog::Run(HINSTANCE__ *)
0x14000e7d8  nop
0x14000e7d9  lea     rcx, [rbp+arg_8]
0x14000e7dd  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x14000e7e2  nop
0x14000e7e3  lea     rcx, [rbp+arg_10]
0x14000e7e7  call    ?Close@?$consume_Windows_Foundation_IClosable@UDesktopWindowXamlSource@Hosting@Xaml@UI@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Foundation_IClosable<winrt::Windows::UI::Xaml::Hosting::DesktopWindowXamlSource>::Close(void)
0x14000e7ec  nop
0x14000e7ed  lea     rcx, [rbp+arg_10]
0x14000e7f1  call    ??1?$com_ptr@UIWeakReferenceSource@impl@winrt@@@winrt@@QEAA@XZ; winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(void)
0x14000e7f6  nop
0x14000e7f7  lea     rcx, [rbp+var_40]
0x14000e7fb  call    ??1?$test_watcher@V?$merged_data@U_tip_AccessibilityDialogFlyoutLaunchTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_watcher<tip2::details::merged_data<_tip_AccessibilityDialogFlyoutLaunchTest,_tip_AccessibilityDialogFlyoutLaunchTest>>::~test_watcher<tip2::details::merged_data<_tip_AccessibilityDialogFlyoutLaunchTest,_tip_AccessibilityDialogFlyoutLaunchTest>>(void)
0x14000e800  lea     r11, [rsp+70h+var_s0]
0x14000e805  mov     rbx, [r11+10h]
0x14000e809  mov     rdi, [r11+28h]
0x14000e80d  mov     rsp, r11
0x14000e810  pop     rbp
0x14000e811  retn
```
