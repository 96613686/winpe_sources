# AccessibilityDialog::ToggleAT(ushort const *)

- ea: `0x140022b10`
- end: `0x140022c87`
- name: `?ToggleAT@AccessibilityDialog@@AEAAXPEBG@Z`
- size: `375`
- prototype: `void __fastcall(AccessibilityDialog *__hidden this, const unsigned __int16 *)`
- caller_count: `7`
- callee_count: `19`
- tags: `broker_com_uri`

## callers

- `0x14001f584`
- `0x14001f5d4`
- `0x14001f624`
- `0x14001f674`
- `0x14001f6c4`
- `0x14001f778`
- `0x14001f818`

## callees

- `0x140002480`
- `0x14000ccdc`
- `0x14001355c`
- `0x1400135f0`
- `0x140017290`
- `0x1400178a4`
- `0x140017904`
- `0x1400189dc`
- `0x140018ac8`
- `0x14001d3b4`
- `0x14001d730`
- `0x14001f410`
- `0x1400205a8`
- `0x140020d04`
- `0x140020ea8`
- `0x140022168`
- `0x140022b10`
- `0x140022d84`
- `0x140022e08`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
void __fastcall AccessibilityDialog::ToggleAT(AccessibilityDialog *this, unsigned __int16 *a2)
{
  Accommodation *v4; // rax
  struct Accommodation *v5; // rsi
  int IsRunning; // r12d
  __int64 v7; // rbx
  __int64 ToggleName; // rax
  __int64 v9; // r8
  __int64 v10; // rdx
  char v11; // bl
  int v12; // r8d
  int v13; // r9d
  StartList *v14; // rcx
  bool v15; // r8
  _BYTE v16[8]; // [rsp+20h] [rbp-E0h] BYREF
  _BYTE v17[8]; // [rsp+28h] [rbp-D8h] BYREF
  unsigned __int16 *v18; // [rsp+30h] [rbp-D0h] BYREF
  Accommodation *v19; // [rsp+38h] [rbp-C8h] BYREF
  _QWORD v20[2]; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v21[352]; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v22[32]; // [rsp+1B0h] [rbp+B0h] BYREF

  v18 = a2;
  v4 = Accommodation::Open(a2);
  v5 = v4;
  v19 = v4;
  if ( v4 )
  {
    IsRunning = Accommodation::IsRunning(v4);
    v7 = *((_QWORD *)this + 6);
    ToggleName = anonymous_namespace_::GetToggleName(v22, a2);
    v20[0] = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(ToggleName, ToggleName, v9);
    v20[1] = *(_QWORD *)(v10 + 16);
    XamlUI::GetElementAs<winrt::Windows::UI::Xaml::Controls::ToggleSwitch>(v7, v17, v20);
    std::wstring::_Tidy_deallocate(v22);
    v11 = winrt::impl::consume_Windows_UI_Xaml_Controls_IToggleSwitch<winrt::Windows::UI::Xaml::Controls::IToggleSwitch>::IsOn(v17);
    v16[0] = v11;
    if ( v11 != (IsRunning != 0) )
    {
      ATManager::ATManager((ATManager *)v21, 0);
      if ( IsRunning )
      {
        StartList::Stop((StartList *)v21, v5);
        if ( (unsigned __int8)anonymous_namespace_::IsSupportedAT(a2) && (unsigned int)Accommodation::IsRunning(v5) )
          StartList::StartProcess(v14, a2, v15);
      }
      else
      {
        StartList::Start((StartList *)v21, v5, v12, v13);
      }
      ATManager::~ATManager((ATManager *)v21);
    }
    AccessibilityDialog::SetToggleTextState(this, a2, v11);
    AccessibilityFlyoutTelemetryProvider::ATToggled<unsigned short const * &,bool &>(&v18, v16);
    winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(v17);
  }
  std::unique_ptr<Accommodation>::~unique_ptr<Accommodation>(&v19);
}

```

## disassembly

```asm
0x140022b10  mov     [rsp-8+arg_10], rbx
0x140022b15  mov     [rsp-8+arg_18], rsi
0x140022b1a  push    rbp
0x140022b1b  push    rdi
0x140022b1c  push    r12
0x140022b1e  push    r14
0x140022b20  push    r15
0x140022b22  lea     rbp, [rsp-0E0h]
0x140022b2a  sub     rsp, 1E0h
0x140022b31  mov     rax, cs:__security_cookie
0x140022b38  xor     rax, rsp
0x140022b3b  mov     [rbp+100h+var_30], rax
0x140022b42  mov     r14, rdx
0x140022b45  mov     r15, rcx
0x140022b48  mov     [rsp+200h+var_1D0], rdx
0x140022b4d  mov     rcx, rdx; unsigned __int16 *
0x140022b50  call    ?Open@Accommodation@@SAPEAV1@PEBG@Z; Accommodation::Open(ushort const *)
0x140022b55  mov     rsi, rax
0x140022b58  mov     [rsp+200h+var_1C8], rax
0x140022b5d  test    rax, rax
0x140022b60  jz      loc_140022C51
0x140022b66  mov     rcx, rax; this
0x140022b69  call    ?IsRunning@Accommodation@@QEAAHXZ; Accommodation::IsRunning(void)
0x140022b6e  mov     r12d, eax
0x140022b71  test    eax, eax
0x140022b73  setnz   dil
0x140022b77  mov     rbx, [r15+30h]
0x140022b7b  mov     rdx, r14
0x140022b7e  lea     rcx, [rbp+100h+var_50]
0x140022b85  call    _anonymous_namespace___GetToggleName
0x140022b8a  mov     rdx, rax
0x140022b8d  mov     rcx, rax
0x140022b90  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x140022b95  mov     [rsp+200h+var_1C0], rax
0x140022b9a  mov     rax, [rdx+10h]
0x140022b9e  mov     [rsp+200h+var_1B8], rax
0x140022ba3  lea     r8, [rsp+200h+var_1C0]
0x140022ba8  lea     rdx, [rsp+200h+var_1D8]
0x140022bad  mov     rcx, rbx
0x140022bb0  call    ??$GetElementAs@UToggleSwitch@Controls@Xaml@UI@Windows@winrt@@@XamlUI@@QEBA?AUToggleSwitch@Controls@Xaml@UI@Windows@winrt@@V?$basic_string_view@GU?$char_traits@G@std@@@std@@@Z; XamlUI::GetElementAs<winrt::Windows::UI::Xaml::Controls::ToggleSwitch>(std::basic_string_view<ushort>)
0x140022bb5  nop
0x140022bb6  lea     rcx, [rbp+100h+var_50]
0x140022bbd  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x140022bc2  lea     rcx, [rsp+200h+var_1D8]
0x140022bc7  call    ?IsOn@?$consume_Windows_UI_Xaml_Controls_IToggleSwitch@UIToggleSwitch@Controls@Xaml@UI@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_UI_Xaml_Controls_IToggleSwitch<winrt::Windows::UI::Xaml::Controls::IToggleSwitch>::IsOn(void)
0x140022bcc  mov     bl, al
0x140022bce  mov     [rsp+200h+var_1E0], al
0x140022bd2  cmp     al, dil
0x140022bd5  jz      short loc_140022C28
0x140022bd7  xor     edx, edx; int
0x140022bd9  lea     rcx, [rsp+200h+var_1B0]; this
0x140022bde  call    ??0ATManager@@QEAA@H@Z; ATManager::ATManager(int)
0x140022be3  nop
0x140022be4  mov     rdx, rsi; struct Accommodation *
0x140022be7  lea     rcx, [rsp+200h+var_1B0]; this
0x140022bec  test    r12d, r12d
0x140022bef  jnz     short loc_140022BF8
0x140022bf1  call    ?Start@StartList@@QEAAJPEAVAccommodation@@HH@Z; StartList::Start(Accommodation *,int,int)
0x140022bf6  jmp     short loc_140022C1E
0x140022bf8  call    ?Stop@StartList@@QEAAJPEAVAccommodation@@@Z; StartList::Stop(Accommodation *)
0x140022bfd  mov     rcx, r14; Str
0x140022c00  call    _anonymous_namespace___IsSupportedAT
0x140022c05  test    al, al
0x140022c07  jz      short loc_140022C1E
0x140022c09  mov     rcx, rsi; this
0x140022c0c  call    ?IsRunning@Accommodation@@QEAAHXZ; Accommodation::IsRunning(void)
0x140022c11  test    eax, eax
0x140022c13  jz      short loc_140022C1E
0x140022c15  mov     rdx, r14; unsigned __int16 *
0x140022c18  call    ?StartProcess@StartList@@QEAAJPEBG_N@Z; StartList::StartProcess(ushort const *,bool)
0x140022c1d  nop
0x140022c1e  lea     rcx, [rsp+200h+var_1B0]; this
0x140022c23  call    ??1ATManager@@QEAA@XZ; ATManager::~ATManager(void)
0x140022c28  mov     r8b, bl; bool
0x140022c2b  mov     rdx, r14; unsigned __int16 *
0x140022c2e  mov     rcx, r15; this
0x140022c31  call    ?SetToggleTextState@AccessibilityDialog@@AEAAXPEBG_N@Z; AccessibilityDialog::SetToggleTextState(ushort const *,bool)
0x140022c36  lea     rdx, [rsp+200h+var_1E0]
0x140022c3b  lea     rcx, [rsp+200h+var_1D0]
0x140022c40  call    ??$ATToggled@AEAPEBGAEA_N@AccessibilityFlyoutTelemetryProvider@@SAXAEAPEBGAEA_N@Z; AccessibilityFlyoutTelemetryProvider::ATToggled<ushort const * &,bool &>(ushort const * &,bool &)
0x140022c45  nop
0x140022c46  lea     rcx, [rsp+200h+var_1D8]
0x140022c4b  call    ??1?$com_ptr@UIWeakReferenceSource@impl@winrt@@@winrt@@QEAA@XZ; winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(void)
0x140022c50  nop
0x140022c51  lea     rcx, [rsp+200h+var_1C8]
0x140022c56  call    ??1?$unique_ptr@VAccommodation@@U?$default_delete@VAccommodation@@@std@@@std@@QEAA@XZ; std::unique_ptr<Accommodation>::~unique_ptr<Accommodation>(void)
0x140022c5b  mov     rcx, [rbp+100h+var_30]
0x140022c62  xor     rcx, rsp; StackCookie
0x140022c65  call    __security_check_cookie
0x140022c6a  lea     r11, [rsp+200h+var_20]
0x140022c72  mov     rbx, [r11+40h]
0x140022c76  mov     rsi, [r11+48h]
0x140022c7a  mov     rsp, r11
0x140022c7d  pop     r15
0x140022c7f  pop     r14
0x140022c81  pop     r12
0x140022c83  pop     rdi
0x140022c84  pop     rbp
0x140022c85  retn
```
