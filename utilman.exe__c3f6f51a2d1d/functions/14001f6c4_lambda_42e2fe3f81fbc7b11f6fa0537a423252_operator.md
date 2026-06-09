# _lambda_42e2fe3f81fbc7b11f6fa0537a423252_::operator()

- ea: `0x14001f6c4`
- end: `0x14001f70b`
- name: `_lambda_42e2fe3f81fbc7b11f6fa0537a423252_::operator()`
- size: `71`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x140020bb0`

## callees

- `0x140009ee0`
- `0x14001f6c4`
- `0x140022b10`
- `0x140023020`

## string_xrefs

- `0x14001f6e0`: `voiceaccess`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall lambda_42e2fe3f81fbc7b11f6fa0537a423252_::operator()(__int64 a1, __int64 a2, AccessibilityDialog *a3)
{
  const char *v3; // r9
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  AccessibilityDialog *v5; // [rsp+40h] [rbp+18h] BYREF

  v5 = a3;
  winrt::weak_ref<AccessibilityDialog>::get(a1, &v5);
  try
  {
    if ( v5 )
      AccessibilityDialog::ToggleAT(v5, L"voiceaccess");
    if ( v5 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref((__int64 *)&v5);
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0x2B8,
      (unsigned int)"enduser\\ezap\\easeofaccess\\accessibilitydialog\\accessibilitydialog.cpp",
      v3);
  }
}

```

## disassembly

```asm
0x14001f6c4  mov     [rsp+arg_10], r8
0x14001f6c9  sub     rsp, 28h
0x14001f6cd  lea     rdx, [rsp+28h+arg_10]
0x14001f6d2  call    ?get@?$weak_ref@VAccessibilityDialog@@@winrt@@QEBA@XZ; winrt::weak_ref<AccessibilityDialog>::get(void)
0x14001f6d7  nop
0x14001f6d8  cmp     [rsp+28h+arg_10], 0
0x14001f6de  jz      short loc_14001F6F2
0x14001f6e0  lea     rdx, aVoiceaccess; "voiceaccess"
0x14001f6e7  mov     rcx, [rsp+28h+arg_10]; this
0x14001f6ec  call    ?ToggleAT@AccessibilityDialog@@AEAAXPEBG@Z; AccessibilityDialog::ToggleAT(ushort const *)
0x14001f6f1  nop
0x14001f6f2  cmp     [rsp+28h+arg_10], 0
0x14001f6f8  jz      short loc_14001F705
0x14001f6fa  lea     rcx, [rsp+28h+arg_10]
0x14001f6ff  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x14001f704  nop
0x14001f705  add     rsp, 28h
0x14001f709  retn
```
