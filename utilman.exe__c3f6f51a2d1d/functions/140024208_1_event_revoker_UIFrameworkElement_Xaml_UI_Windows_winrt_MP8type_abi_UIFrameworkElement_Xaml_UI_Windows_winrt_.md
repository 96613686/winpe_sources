# ??1?$event_revoker@UIFrameworkElement@Xaml@UI@Windows@winrt@@$MP8type@?$abi@UIFrameworkElement@Xaml@UI@Windows@winrt@@X@impl@5@EAAHUevent_token@5@@_E1??_96785@$BBJA@AA@impl@winrt@@QEAA@XZ

- ea: `0x140024208`
- end: `0x140024241`
- name: `??1?$event_revoker@UIFrameworkElement@Xaml@UI@Windows@winrt@@$MP8type@?$abi@UIFrameworkElement@Xaml@UI@Windows@winrt@@X@impl@5@EAAHUevent_token@5@@_E1??_96785@$BBJA@AA@impl@winrt@@QEAA@XZ`
- size: `57`
- prototype: ``
- caller_count: `5`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x140024284`
- `0x1400242f0`
- `0x140025030`
- `0x1400256e8`
- `0x140027f00`

## callees

- `0x140009ee0`
- `0x140010798`
- `0x140024208`
- `0x1400257e8`

## pseudocode

```c
void __fastcall __1__event_revoker_UIFrameworkElement_Xaml_UI_Windows_winrt___MP8type___abi_UIFrameworkElement_Xaml_UI_Windows_winrt__X_impl_5_EAAHUevent_token_5___E1___96785__BBJA_AA_impl_winrt__QEAA_XZ(
        __int64 *a1)
{
  __int64 v2; // rax
  char v3; // [rsp+30h] [rbp+8h] BYREF

  if ( *a1 )
  {
    v2 = winrt::weak_ref<winrt::Windows::UI::Xaml::IFrameworkElement>::get(a1, &v3);
    _revoke_impl___event_revoker_UIFrameworkElement_Xaml_UI_Windows_winrt___MP8type___abi_UIFrameworkElement_Xaml_UI_Windows_winrt__X_impl_5_EAAHUevent_token_5___E1___96785__BBJA_AA_impl_winrt__AEAAXUIFrameworkElement_Xaml_UI_Windows_3__Z(
      a1,
      v2);
  }
  if ( *a1 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a1);
}

```

## disassembly

```asm
0x140024208  push    rbx
0x14002420a  sub     rsp, 20h
0x14002420e  cmp     qword ptr [rcx], 0
0x140024212  mov     rbx, rcx
0x140024215  jz      short loc_14002422C
0x140024217  lea     rdx, [rsp+28h+arg_0]
0x14002421c  call    ?get@?$weak_ref@UIFrameworkElement@Xaml@UI@Windows@winrt@@@winrt@@QEBA@XZ; winrt::weak_ref<winrt::Windows::UI::Xaml::IFrameworkElement>::get(void)
0x140024221  mov     rdx, rax
0x140024224  mov     rcx, rbx
0x140024227  call    ?revoke_impl@?$event_revoker@UIFrameworkElement@Xaml@UI@Windows@winrt@@$MP8type@?$abi@UIFrameworkElement@Xaml@UI@Windows@winrt@@X@impl@5@EAAHUevent_token@5@@_E1??_96785@$BBJA@AA@impl@winrt@@AEAAXUIFrameworkElement@Xaml@UI@Windows@3@@Z
0x14002422c  cmp     qword ptr [rbx], 0
0x140024230  jz      short loc_14002423A
0x140024232  mov     rcx, rbx
0x140024235  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x14002423a  add     rsp, 20h
0x14002423e  pop     rbx
0x14002423f  retn
```
