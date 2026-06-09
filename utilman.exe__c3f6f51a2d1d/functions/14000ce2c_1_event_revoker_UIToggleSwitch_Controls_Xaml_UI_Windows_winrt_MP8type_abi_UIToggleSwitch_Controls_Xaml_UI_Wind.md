# ??1?$event_revoker@UIToggleSwitch@Controls@Xaml@UI@Windows@winrt@@$MP8type@?$abi@UIToggleSwitch@Controls@Xaml@UI@Windows@winrt@@X@impl@6@EAAHUevent_token@6@@_E1??_97896@$BLA@AA@impl@winrt@@QEAA@XZ

- ea: `0x14000ce2c`
- end: `0x14000ce95`
- name: `??1?$event_revoker@UIToggleSwitch@Controls@Xaml@UI@Windows@winrt@@$MP8type@?$abi@UIToggleSwitch@Controls@Xaml@UI@Windows@winrt@@X@impl@6@EAAHUevent_token@6@@_E1??_97896@$BLA@AA@impl@winrt@@QEAA@XZ`
- size: `105`
- prototype: ``
- caller_count: `3`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x14000d06c`
- `0x14001f504`
- `0x140021538`

## callees

- `0x140009ee0`
- `0x14000ccdc`
- `0x14000ce2c`
- `0x14000d3d0`
- `0x140029010`

## pseudocode

```c
__int64 __fastcall __1__event_revoker_UIToggleSwitch_Controls_Xaml_UI_Windows_winrt___MP8type___abi_UIToggleSwitch_Controls_Xaml_UI_Windows_winrt__X_impl_6_EAAHUevent_token_6___E1___97896__BLA_AA_impl_winrt__QEAA_XZ(
        __int64 *a1)
{
  __int64 v2; // rcx
  __int64 result; // rax
  __int64 v4; // [rsp+30h] [rbp+8h] BYREF

  v2 = *a1;
  if ( v2 )
  {
    v4 = 0;
    (*(void (__fastcall **)(__int64, __int64 *, __int64 *))(*(_QWORD *)v2 + 24LL))(
      v2,
      winrt::impl::guid_v<winrt::Windows::UI::Xaml::Controls::IToggleSwitch>,
      &v4);
    if ( v4 )
       winrt::impl::abi<winrt::Windows::UI::Xaml::Controls::IToggleSwitch,void>::type::`vcall'{176,{flat}}(v4, a1[1]);
    result = winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(&v4);
  }
  if ( *a1 )
    return winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a1);
  return result;
}

```

## disassembly

```asm
0x14000ce2c  push    rbx
0x14000ce2e  sub     rsp, 20h
0x14000ce32  mov     rbx, rcx
0x14000ce35  mov     rcx, [rcx]
0x14000ce38  test    rcx, rcx
0x14000ce3b  jz      short loc_14000CE80
0x14000ce3d  mov     [rsp+28h+arg_0], 0
0x14000ce46  lea     r8, [rsp+28h+arg_0]
0x14000ce4b  mov     rax, [rcx]
0x14000ce4e  lea     rdx, ??$guid_v@UIToggleSwitch@Controls@Xaml@UI@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::UI::Xaml::Controls::IToggleSwitch>
0x14000ce55  mov     rax, [rax+18h]
0x14000ce59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ce5e  mov     rcx, [rsp+28h+arg_0]
0x14000ce63  mov     [rsp+28h+arg_0], rcx
0x14000ce68  test    rcx, rcx
0x14000ce6b  jz      short loc_14000CE76
0x14000ce6d  mov     rdx, [rbx+8]
0x14000ce71  call    ??_9type@?$abi@UIToggleSwitch@Controls@Xaml@UI@Windows@winrt@@X@impl@winrt@@$BLA@AA; [thunk]: winrt::impl::abi<winrt::Windows::UI::Xaml::Controls::IToggleSwitch,void>::type::`vcall'{176,{flat}}
0x14000ce76  lea     rcx, [rsp+28h+arg_0]
0x14000ce7b  call    ??1?$com_ptr@UIWeakReferenceSource@impl@winrt@@@winrt@@QEAA@XZ; winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(void)
0x14000ce80  cmp     qword ptr [rbx], 0
0x14000ce84  jz      short loc_14000CE8E
0x14000ce86  mov     rcx, rbx
0x14000ce89  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x14000ce8e  add     rsp, 20h
0x14000ce92  pop     rbx
0x14000ce93  retn
```
