# XamlUI::SetFlowDirection(void)

- ea: `0x14002556c`
- end: `0x1400255fc`
- name: `?SetFlowDirection@XamlUI@@AEAAXXZ`
- size: `144`
- prototype: `void __fastcall(XamlUI *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1400247dc`

## callees

- `0x14000ccdc`
- `0x14001fe00`
- `0x140022dcc`
- `0x14002556c`
- `0x1400256b4`

## import_xrefs

- `KERNEL32!GetLocaleInfoEx` at `0x140025598`
- `KERNEL32!GetLocaleInfoEx` at `0x140025598`

## string_xrefs

- `0x1400255a8`: `enduser\ezap\xamlcommon\xamlui.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall XamlUI::SetFlowDirection(XamlUI *this)
{
  const char *v2; // r9
  __int64 v3; // rax
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  int LCData; // [rsp+38h] [rbp+10h] BYREF
  __int64 v6; // [rsp+40h] [rbp+18h] BYREF

  LCData = 0;
  if ( !GetLocaleInfoEx(0, 0x20000070u, (LPWSTR)&LCData, 2) )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x2C,
      (unsigned int)"enduser\\ezap\\xamlcommon\\xamlui.cpp",
      v2);
  if ( LCData == 1 )
  {
    v3 = XamlUI::XamlContentRoot(this, &v6);
    wcscpy((wchar_t *)&LCData, L"\x01");
    winrt::impl::consume_Windows_UI_Xaml_IFrameworkElement<winrt::Windows::UI::Xaml::IFrameworkElement>::FlowDirection(
      v3,
      &LCData);
    winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(&v6);
  }
}

```

## disassembly

```asm
0x14002556c  mov     [rsp+arg_0], rbx
0x140025571  push    rdi
0x140025572  sub     rsp, 20h
0x140025576  mov     rdi, rcx
0x140025579  mov     [rsp+28h+LCData], 0
0x140025581  mov     rbx, [rsp+28h]
0x140025586  mov     r9d, 2; cchData
0x14002558c  lea     r8, [rsp+28h+LCData]; lpLCData
0x140025591  mov     edx, 20000070h; LCType
0x140025596  xor     ecx, ecx; lpLocaleName
0x140025598  call    cs:__imp_GetLocaleInfoEx
0x14002559f  nop     dword ptr [rax+rax+00h]
0x1400255a4  test    eax, eax
0x1400255a6  jnz     short loc_1400255BB
0x1400255a8  lea     r8, aEnduserEzapXam; "enduser\\ezap\\xamlcommon\\xamlui.cpp"
0x1400255af  lea     edx, [rax+2Ch]; void *
0x1400255b2  mov     rcx, rbx; this
0x1400255b5  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x1400255bb  cmp     [rsp+28h+LCData], 1
0x1400255c0  jnz     short loc_1400255F0
0x1400255c2  lea     rdx, [rsp+28h+arg_10]
0x1400255c7  mov     rcx, rdi
0x1400255ca  call    ?XamlContentRoot@XamlUI@@QEBA?AUFrameworkElement@Xaml@UI@Windows@winrt@@XZ; XamlUI::XamlContentRoot(void)
0x1400255cf  nop
0x1400255d0  mov     [rsp+28h+LCData], 1
0x1400255d8  lea     rdx, [rsp+28h+LCData]
0x1400255dd  mov     rcx, rax
0x1400255e0  call    ?FlowDirection@?$consume_Windows_UI_Xaml_IFrameworkElement@UIFrameworkElement@Xaml@UI@Windows@winrt@@@impl@winrt@@QEBA@AEBW40Xaml@UI@Windows@3@@Z; winrt::impl::consume_Windows_UI_Xaml_IFrameworkElement<winrt::Windows::UI::Xaml::IFrameworkElement>::FlowDirection(winrt::Windows::UI::Xaml::FlowDirection const &)
0x1400255e5  nop
0x1400255e6  lea     rcx, [rsp+28h+arg_10]
0x1400255eb  call    ??1?$com_ptr@UIWeakReferenceSource@impl@winrt@@@winrt@@QEAA@XZ; winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(void)
0x1400255f0  mov     rbx, [rsp+28h+arg_0]
0x1400255f5  add     rsp, 20h
0x1400255f9  pop     rdi
0x1400255fa  retn
```
