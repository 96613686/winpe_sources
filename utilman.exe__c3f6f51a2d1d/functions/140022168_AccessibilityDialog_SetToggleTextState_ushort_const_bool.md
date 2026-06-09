# AccessibilityDialog::SetToggleTextState(ushort const *,bool)

- ea: `0x140022168`
- end: `0x140022275`
- name: `?SetToggleTextState@AccessibilityDialog@@AEAAXPEBG_N@Z`
- size: `269`
- prototype: `void __fastcall(AccessibilityDialog *__hidden this, const unsigned __int16 *, bool)`
- caller_count: `2`
- callee_count: `14`
- tags: `broker_com_uri`

## callers

- `0x14002227c`
- `0x140022b10`

## callees

- `0x140002480`
- `0x140009ee0`
- `0x14000ccdc`
- `0x14001e58c`
- `0x14001f2d4`
- `0x14001f304`
- `0x14001fcd8`
- `0x140020648`
- `0x140022168`
- `0x140022aa8`
- `0x140022d84`
- `0x140022e08`
- `0x1400256b4`
- `0x140025c84`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
void __fastcall AccessibilityDialog::SetToggleTextState(
        AccessibilityDialog *this,
        const unsigned __int16 *a2,
        unsigned __int8 a3)
{
  int v3; // esi
  __int64 v5; // rbx
  __int64 ToggleTextName; // rax
  __int64 v7; // r8
  __int64 v8; // rdx
  __int64 v9; // rbx
  _QWORD *Name; // rax
  __int64 v11[2]; // [rsp+20h] [rbp-49h] BYREF
  _QWORD v12[2]; // [rsp+30h] [rbp-39h] BYREF
  __int64 v13; // [rsp+40h] [rbp-29h] BYREF
  _BYTE v14[32]; // [rsp+48h] [rbp-21h] BYREF
  _BYTE v15[32]; // [rsp+68h] [rbp-1h] BYREF
  _BYTE v16[32]; // [rsp+88h] [rbp+1Fh] BYREF

  v3 = a3;
  v5 = *((_QWORD *)this + 6);
  ToggleTextName = anonymous_namespace_::GetToggleTextName(v15, a2);
  v12[0] = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(ToggleTextName, ToggleTextName, v7);
  v12[1] = *(_QWORD *)(v8 + 16);
  v9 = XamlUI::XamlContentRoot(v5, &v13);
  winrt::param::hstring::hstring(v14, v12);
  Name = (_QWORD *)winrt::impl::consume_Windows_UI_Xaml_IFrameworkElement<winrt::Windows::UI::Xaml::IFrameworkElement>::FindName(
                     v9,
                     v11,
                     v14);
  winrt::impl::as<winrt::Windows::UI::Xaml::Controls::TextBlock,winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type,0>(
    v12,
    *Name);
  if ( v11[0] )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(v11);
  winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(&v13);
  std::wstring::_Tidy_deallocate(v15);
  XamlResourceUtils::LoadWString((__int64)v16, *((HINSTANCE *)this + 4), v3 + 606);
  winrt::param::hstring::hstring((winrt::param::hstring *)v14);
  winrt::impl::consume_Windows_UI_Xaml_Controls_ITextBlock<winrt::Windows::UI::Xaml::Controls::ITextBlock>::Text(
    v12,
    v14);
  std::wstring::_Tidy_deallocate(v16);
  winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(v12);
}

```

## disassembly

```asm
0x140022168  mov     [rsp-8+arg_10], rbx
0x14002216d  push    rbp
0x14002216e  push    rsi
0x14002216f  push    rdi
0x140022170  lea     rbp, [rsp-47h]
0x140022175  sub     rsp, 0B0h
0x14002217c  mov     rax, cs:__security_cookie
0x140022183  xor     rax, rsp
0x140022186  mov     [rbp+57h+var_18], rax
0x14002218a  movzx   esi, r8b
0x14002218e  mov     rdi, rcx
0x140022191  mov     rbx, [rcx+30h]
0x140022195  lea     rcx, [rbp+57h+var_58]
0x140022199  call    _anonymous_namespace___GetToggleTextName
0x14002219e  mov     rdx, rax
0x1400221a1  mov     rcx, rax
0x1400221a4  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1400221a9  mov     [rbp+57h+var_90], rax
0x1400221ad  mov     rax, [rdx+10h]
0x1400221b1  mov     [rbp+57h+var_88], rax
0x1400221b5  lea     rdx, [rbp+57h+var_80]
0x1400221b9  mov     rcx, rbx
0x1400221bc  call    ?XamlContentRoot@XamlUI@@QEBA?AUFrameworkElement@Xaml@UI@Windows@winrt@@XZ; XamlUI::XamlContentRoot(void)
0x1400221c1  mov     rbx, rax
0x1400221c4  lea     rdx, [rbp+57h+var_90]
0x1400221c8  lea     rcx, [rbp+57h+var_78]
0x1400221cc  call    ??0hstring@param@winrt@@QEAA@AEBV?$basic_string_view@GU?$char_traits@G@std@@@std@@@Z; winrt::param::hstring::hstring(std::basic_string_view<ushort> const &)
0x1400221d1  lea     r8, [rbp+57h+var_78]
0x1400221d5  lea     rdx, [rbp+57h+var_A0]
0x1400221d9  mov     rcx, rbx
0x1400221dc  call    ?FindName@?$consume_Windows_UI_Xaml_IFrameworkElement@UIFrameworkElement@Xaml@UI@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@@Z; winrt::impl::consume_Windows_UI_Xaml_IFrameworkElement<winrt::Windows::UI::Xaml::IFrameworkElement>::FindName(winrt::param::hstring const &)
0x1400221e1  nop
0x1400221e2  mov     rdx, [rax]
0x1400221e5  lea     rcx, [rbp+57h+var_90]
0x1400221e9  call    ??$as@UTextBlock@Controls@Xaml@UI@Windows@winrt@@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@6@$0A@@impl@winrt@@YA?AUTextBlock@Controls@Xaml@UI@Windows@1@PEAUtype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@01@@Z; winrt::impl::as<winrt::Windows::UI::Xaml::Controls::TextBlock,winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type,0>(winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type *)
0x1400221ee  nop
0x1400221ef  cmp     [rbp+57h+var_A0], 0
0x1400221f4  jz      short loc_140022200
0x1400221f6  lea     rcx, [rbp+57h+var_A0]
0x1400221fa  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x1400221ff  nop
0x140022200  lea     rcx, [rbp+57h+var_80]
0x140022204  call    ??1?$com_ptr@UIWeakReferenceSource@impl@winrt@@@winrt@@QEAA@XZ; winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(void)
0x140022209  nop
0x14002220a  lea     rcx, [rbp+57h+var_58]
0x14002220e  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x140022213  lea     r8d, [rsi+25Eh]
0x14002221a  mov     rdx, [rdi+20h]
0x14002221e  lea     rcx, [rbp+57h+var_38]
0x140022222  call    ?LoadWString@XamlResourceUtils@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAUHINSTANCE__@@H@Z; XamlResourceUtils::LoadWString(HINSTANCE__ *,int)
0x140022227  nop
0x140022228  mov     rdx, rax
0x14002222b  lea     rcx, [rbp+57h+var_78]; this
0x14002222f  call    ??0hstring@param@winrt@@QEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; winrt::param::hstring::hstring(std::wstring const &)
0x140022234  lea     rdx, [rbp+57h+var_78]
0x140022238  lea     rcx, [rbp+57h+var_90]
0x14002223c  call    ?Text@?$consume_Windows_UI_Xaml_Controls_ITextBlock@UITextBlock@Controls@Xaml@UI@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@@Z; winrt::impl::consume_Windows_UI_Xaml_Controls_ITextBlock<winrt::Windows::UI::Xaml::Controls::ITextBlock>::Text(winrt::param::hstring const &)
0x140022241  nop
0x140022242  lea     rcx, [rbp+57h+var_38]
0x140022246  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14002224b  nop
0x14002224c  lea     rcx, [rbp+57h+var_90]
0x140022250  call    ??1?$com_ptr@UIWeakReferenceSource@impl@winrt@@@winrt@@QEAA@XZ; winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(void)
0x140022255  mov     rcx, [rbp+57h+var_18]
0x140022259  xor     rcx, rsp; StackCookie
0x14002225c  call    __security_check_cookie
0x140022261  mov     rbx, [rsp+0C0h+arg_10]
0x140022269  add     rsp, 0B0h
0x140022270  pop     rdi
0x140022271  pop     rsi
0x140022272  pop     rbp
0x140022273  retn
```
