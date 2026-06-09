# AccessibilityDialog::SetToggleUiState(ushort const *)

- ea: `0x14002227c`
- end: `0x140022353`
- name: `?SetToggleUiState@AccessibilityDialog@@AEAAXPEBG@Z`
- size: `215`
- prototype: `void __fastcall(AccessibilityDialog *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x14002235c`

## callees

- `0x140002480`
- `0x14000ccdc`
- `0x1400189dc`
- `0x140018ac8`
- `0x14001d730`
- `0x14001f410`
- `0x1400205a8`
- `0x140020d54`
- `0x140022168`
- `0x14002227c`
- `0x140022d84`
- `0x140022e08`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall AccessibilityDialog::SetToggleUiState(AccessibilityDialog *this, const unsigned __int16 *a2)
{
  Accommodation *v4; // rax
  unsigned __int8 v5; // di
  __int64 v6; // rbx
  __int64 ToggleName; // rax
  __int64 v8; // r8
  __int64 v9; // rdx
  __int64 v10; // rdx
  __int64 v11; // [rsp+20h] [rbp-68h] BYREF
  Accommodation *v12; // [rsp+28h] [rbp-60h] BYREF
  _QWORD v13[2]; // [rsp+30h] [rbp-58h] BYREF
  _BYTE v14[32]; // [rsp+40h] [rbp-48h] BYREF

  v4 = Accommodation::Open(a2);
  v12 = v4;
  if ( v4 )
  {
    v5 = (unsigned int)Accommodation::IsRunning(v4) != 0;
    v6 = *((_QWORD *)this + 6);
    ToggleName = anonymous_namespace_::GetToggleName(v14, a2);
    v13[0] = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(ToggleName, ToggleName, v8);
    v13[1] = *(_QWORD *)(v9 + 16);
    XamlUI::GetElementAs<winrt::Windows::UI::Xaml::Controls::ToggleSwitch>(v6, &v11, v13);
    std::wstring::_Tidy_deallocate(v14);
    LOBYTE(v10) = v5;
    winrt::impl::consume_Windows_UI_Xaml_Controls_IToggleSwitch<winrt::Windows::UI::Xaml::Controls::IToggleSwitch>::IsOn(
      &v11,
      v10);
    AccessibilityDialog::SetToggleTextState(this, a2, v5);
    winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(&v11);
  }
  std::unique_ptr<Accommodation>::~unique_ptr<Accommodation>(&v12);
}

```

## disassembly

```asm
0x14002227c  mov     [rsp+arg_10], rbx
0x140022281  push    rbp
0x140022282  push    rsi
0x140022283  push    rdi
0x140022284  sub     rsp, 70h
0x140022288  mov     rax, cs:__security_cookie
0x14002228f  xor     rax, rsp
0x140022292  mov     [rsp+88h+var_28], rax
0x140022297  mov     rsi, rdx
0x14002229a  mov     rbp, rcx
0x14002229d  mov     rcx, rdx; unsigned __int16 *
0x1400222a0  call    ?Open@Accommodation@@SAPEAV1@PEBG@Z; Accommodation::Open(ushort const *)
0x1400222a5  mov     [rsp+88h+var_60], rax
0x1400222aa  test    rax, rax
0x1400222ad  jz      short loc_14002232B
0x1400222af  mov     rcx, rax; this
0x1400222b2  call    ?IsRunning@Accommodation@@QEAAHXZ; Accommodation::IsRunning(void)
0x1400222b7  test    eax, eax
0x1400222b9  setnz   dil
0x1400222bd  mov     rbx, [rbp+30h]
0x1400222c1  mov     rdx, rsi
0x1400222c4  lea     rcx, [rsp+88h+var_48]
0x1400222c9  call    _anonymous_namespace___GetToggleName
0x1400222ce  mov     rdx, rax
0x1400222d1  mov     rcx, rax
0x1400222d4  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1400222d9  mov     [rsp+88h+var_58], rax
0x1400222de  mov     rax, [rdx+10h]
0x1400222e2  mov     [rsp+88h+var_50], rax
0x1400222e7  lea     r8, [rsp+88h+var_58]
0x1400222ec  lea     rdx, [rsp+88h+var_68]
0x1400222f1  mov     rcx, rbx
0x1400222f4  call    ??$GetElementAs@UToggleSwitch@Controls@Xaml@UI@Windows@winrt@@@XamlUI@@QEBA?AUToggleSwitch@Controls@Xaml@UI@Windows@winrt@@V?$basic_string_view@GU?$char_traits@G@std@@@std@@@Z; XamlUI::GetElementAs<winrt::Windows::UI::Xaml::Controls::ToggleSwitch>(std::basic_string_view<ushort>)
0x1400222f9  nop
0x1400222fa  lea     rcx, [rsp+88h+var_48]
0x1400222ff  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x140022304  mov     dl, dil
0x140022307  lea     rcx, [rsp+88h+var_68]
0x14002230c  call    ?IsOn@?$consume_Windows_UI_Xaml_Controls_IToggleSwitch@UIToggleSwitch@Controls@Xaml@UI@Windows@winrt@@@impl@winrt@@QEBA@_N@Z; winrt::impl::consume_Windows_UI_Xaml_Controls_IToggleSwitch<winrt::Windows::UI::Xaml::Controls::IToggleSwitch>::IsOn(bool)
0x140022311  mov     r8b, dil; bool
0x140022314  mov     rdx, rsi; unsigned __int16 *
0x140022317  mov     rcx, rbp; this
0x14002231a  call    ?SetToggleTextState@AccessibilityDialog@@AEAAXPEBG_N@Z; AccessibilityDialog::SetToggleTextState(ushort const *,bool)
0x14002231f  nop
0x140022320  lea     rcx, [rsp+88h+var_68]
0x140022325  call    ??1?$com_ptr@UIWeakReferenceSource@impl@winrt@@@winrt@@QEAA@XZ; winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(void)
0x14002232a  nop
0x14002232b  lea     rcx, [rsp+88h+var_60]
0x140022330  call    ??1?$unique_ptr@VAccommodation@@U?$default_delete@VAccommodation@@@std@@@std@@QEAA@XZ; std::unique_ptr<Accommodation>::~unique_ptr<Accommodation>(void)
0x140022335  mov     rcx, [rsp+88h+var_28]
0x14002233a  xor     rcx, rsp; StackCookie
0x14002233d  call    __security_check_cookie
0x140022342  mov     rbx, [rsp+88h+arg_10]
0x14002234a  add     rsp, 70h
0x14002234e  pop     rdi
0x14002234f  pop     rsi
0x140022350  pop     rbp
0x140022351  retn
```
