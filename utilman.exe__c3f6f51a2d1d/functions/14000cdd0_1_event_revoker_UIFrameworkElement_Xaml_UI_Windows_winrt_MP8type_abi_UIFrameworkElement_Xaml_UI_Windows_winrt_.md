# ??1?$event_revoker@UIFrameworkElement@Xaml@UI@Windows@winrt@@$MP8type@?$abi@UIFrameworkElement@Xaml@UI@Windows@winrt@@X@impl@5@EAAHUevent_token@5@@_E1??_96785@$BBGA@AA@impl@winrt@@QEAA@XZ

- ea: `0x14000cdd0`
- end: `0x14000ce23`
- name: `??1?$event_revoker@UIFrameworkElement@Xaml@UI@Windows@winrt@@$MP8type@?$abi@UIFrameworkElement@Xaml@UI@Windows@winrt@@X@impl@5@EAAHUevent_token@5@@_E1??_96785@$BBGA@AA@impl@winrt@@QEAA@XZ`
- size: `83`
- prototype: ``
- caller_count: `6`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x14000d06c`
- `0x14001f4a8`
- `0x140021538`
- `0x140024284`
- `0x1400247dc`
- `0x140027eea`

## callees

- `0x140009ee0`
- `0x14000ccdc`
- `0x14000cdd0`
- `0x14000d3b8`
- `0x140010798`

## pseudocode

```c
void __fastcall __1__event_revoker_UIFrameworkElement_Xaml_UI_Windows_winrt___MP8type___abi_UIFrameworkElement_Xaml_UI_Windows_winrt__X_impl_5_EAAHUevent_token_5___E1___96785__BBGA_AA_impl_winrt__QEAA_XZ(
        __int64 *a1)
{
  _QWORD *v2; // rdi
  char v3; // [rsp+30h] [rbp+8h] BYREF

  if ( *a1 )
  {
    v2 = (_QWORD *)winrt::weak_ref<winrt::Windows::UI::Xaml::IFrameworkElement>::get(a1, &v3);
    if ( *v2 )
       winrt::impl::abi<winrt::Windows::UI::Xaml::IFrameworkElement,void>::type::`vcall'{352,{flat}}(*v2, a1[1]);
    winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(v2);
  }
  if ( *a1 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a1);
}

```

## disassembly

```asm
0x14000cdd0  mov     [rsp+arg_8], rbx
0x14000cdd5  push    rdi
0x14000cdd6  sub     rsp, 20h
0x14000cdda  cmp     qword ptr [rcx], 0
0x14000cdde  mov     rbx, rcx
0x14000cde1  jz      short loc_14000CE09
0x14000cde3  lea     rdx, [rsp+28h+arg_0]
0x14000cde8  call    ?get@?$weak_ref@UIFrameworkElement@Xaml@UI@Windows@winrt@@@winrt@@QEBA@XZ; winrt::weak_ref<winrt::Windows::UI::Xaml::IFrameworkElement>::get(void)
0x14000cded  mov     rdi, rax
0x14000cdf0  mov     rcx, [rax]
0x14000cdf3  test    rcx, rcx
0x14000cdf6  jz      short loc_14000CE01
0x14000cdf8  mov     rdx, [rbx+8]
0x14000cdfc  call    ??_9type@?$abi@UIFrameworkElement@Xaml@UI@Windows@winrt@@X@impl@winrt@@$BBGA@AA; [thunk]: winrt::impl::abi<winrt::Windows::UI::Xaml::IFrameworkElement,void>::type::`vcall'{352,{flat}}
0x14000ce01  mov     rcx, rdi
0x14000ce04  call    ??1?$com_ptr@UIWeakReferenceSource@impl@winrt@@@winrt@@QEAA@XZ; winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(void)
0x14000ce09  cmp     qword ptr [rbx], 0
0x14000ce0d  jz      short loc_14000CE17
0x14000ce0f  mov     rcx, rbx
0x14000ce12  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x14000ce17  mov     rbx, [rsp+28h+arg_8]
0x14000ce1c  add     rsp, 20h
0x14000ce20  pop     rdi
0x14000ce21  retn
```
