# MoveTryPositionPropertiesToPropertySet(HWND__ *,Windows::Internal::ShellHelpers::PropertySetHelper &)

- ea: `0x18037c6a0`
- end: `0x18037ca02`
- name: `?MoveTryPositionPropertiesToPropertySet@@YAJPEAUHWND__@@AEAVPropertySetHelper@ShellHelpers@Internal@Windows@@@Z`
- size: `866`
- prototype: `int(HWND, struct Windows::Internal::ShellHelpers::PropertySetHelper *)`
- caller_count: `2`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18037abb8`
- `0x18037f630`

## callees

- `0x1800237c8`
- `0x180047278`
- `0x18007b3e0`
- `0x1800edeb4`
- `0x1801c7ebc`
- `0x180356360`
- `0x18037c6a0`

## import_xrefs

- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetPropW` at `0x18037c6ce`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetPropW` at `0x18037c75f`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetPropW` at `0x18037c7b5`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetPropW` at `0x18037c80b`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetPropW` at `0x18037c861`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetPropW` at `0x18037c8b4`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetPropW` at `0x18037c6ce`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetPropW` at `0x18037c75f`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetPropW` at `0x18037c7b5`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetPropW` at `0x18037c80b`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetPropW` at `0x18037c861`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetPropW` at `0x18037c8b4`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!RemovePropW` at `0x18037c91d`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!RemovePropW` at `0x18037c92e`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!RemovePropW` at `0x18037c93f`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!RemovePropW` at `0x18037c950`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!RemovePropW` at `0x18037c961`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!RemovePropW` at `0x18037c972`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!RemovePropW` at `0x18037c987`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!RemovePropW` at `0x18037c998`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!RemovePropW` at `0x18037c9a9`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!RemovePropW` at `0x18037c9ba`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!RemovePropW` at `0x18037c9cb`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!RemovePropW` at `0x18037c9dc`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!RemovePropW` at `0x18037c91d`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!RemovePropW` at `0x18037c92e`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!RemovePropW` at `0x18037c93f`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!RemovePropW` at `0x18037c950`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!RemovePropW` at `0x18037c961`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!RemovePropW` at `0x18037c972`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!RemovePropW` at `0x18037c987`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!RemovePropW` at `0x18037c998`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!RemovePropW` at `0x18037c9a9`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!RemovePropW` at `0x18037c9ba`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!RemovePropW` at `0x18037c9cb`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!RemovePropW` at `0x18037c9dc`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall MoveTryPositionPropertiesToPropertySet(
        HWND a1,
        struct Windows::Internal::ShellHelpers::PropertySetHelper *a2)
{
  bool *v3; // r9
  __int64 v4; // r9
  __int64 v5; // r8
  int v6; // eax
  unsigned int v7; // ebx
  __int64 v8; // rdx
  int v10; // [rsp+20h] [rbp-50h] BYREF
  HWND hWnd[2]; // [rsp+28h] [rbp-48h] BYREF
  char v12; // [rsp+38h] [rbp-38h]
  HSTRING_HEADER hstringHeader; // [rsp+40h] [rbp-30h] BYREF
  HSTRING v14; // [rsp+58h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+8h]

  hWnd[0] = a1;
  if ( (unsigned int)GetPropW(a1, L"TryPositionView") )
  {
    hWnd[1] = (HWND)hWnd;
    v12 = 1;
    LOBYTE(v10) = 0;
    if ( CallerIdentity::CheckCapabilityFromWindow(
           (CallerIdentity *)hWnd[0],
           (HWND)&stru_18078D430,
           (const unsigned __int16 *)&v10,
           v3) >= 0
      && (_BYTE)v10 )
    {
      v14 = 0;
      Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"TryPositionView", 0x10u, 0xFu);
      LOBYTE(v4) = 1;
      v6 = Windows::Internal::ShellHelpers::PropertySetHelper::SetValue<unsigned char>(a2, v14, v5, v4);
      v7 = v6;
      if ( v6 < 0 )
      {
        v8 = 454;
LABEL_16:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v8,
          (unsigned int)"pcshell\\twinui\\appmanager\\lib\\appviewmanager.cpp",
          (const char *)(unsigned int)v6,
          v10);
        RemovePropW(hWnd[0], L"TryPositionView");
        RemovePropW(hWnd[0], L"TryPositionView.Left");
        RemovePropW(hWnd[0], L"TryPositionView.Top");
        RemovePropW(hWnd[0], L"TryPositionView.Right");
        RemovePropW(hWnd[0], L"TryPositionView.Bottom");
        RemovePropW(hWnd[0], L"TryPositionView.Flags");
        return v7;
      }
      GetPropW(hWnd[0], L"TryPositionView.Left");
      v14 = 0;
      Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"TryPositionView.Left", 0x15u, 0x14u);
      v6 = Windows::Internal::ShellHelpers::PropertySetHelper::SetValue<unsigned int>(a2, v14);
      v7 = v6;
      if ( v6 < 0 )
      {
        v8 = 458;
        goto LABEL_16;
      }
      GetPropW(hWnd[0], L"TryPositionView.Top");
      v14 = 0;
      Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"TryPositionView.Top", 0x14u, 0x13u);
      v6 = Windows::Internal::ShellHelpers::PropertySetHelper::SetValue<unsigned int>(a2, v14);
      v7 = v6;
      if ( v6 < 0 )
      {
        v8 = 462;
        goto LABEL_16;
      }
      GetPropW(hWnd[0], L"TryPositionView.Right");
      v14 = 0;
      Microsoft::WRL::Wrappers::HStringReference::CreateReference(
        &hstringHeader,
        L"TryPositionView.Right",
        0x16u,
        0x15u);
      v6 = Windows::Internal::ShellHelpers::PropertySetHelper::SetValue<unsigned int>(a2, v14);
      v7 = v6;
      if ( v6 < 0 )
      {
        v8 = 466;
        goto LABEL_16;
      }
      GetPropW(hWnd[0], L"TryPositionView.Bottom");
      v14 = 0;
      Microsoft::WRL::Wrappers::HStringReference::CreateReference(
        &hstringHeader,
        L"TryPositionView.Bottom",
        0x17u,
        0x16u);
      v6 = Windows::Internal::ShellHelpers::PropertySetHelper::SetValue<unsigned int>(a2, v14);
      v7 = v6;
      if ( v6 < 0 )
      {
        v8 = 470;
        goto LABEL_16;
      }
      GetPropW(hWnd[0], L"TryPositionView.Flags");
      v14 = 0;
      Microsoft::WRL::Wrappers::HStringReference::CreateReference(
        &hstringHeader,
        L"TryPositionView.Flags",
        0x16u,
        0x15u);
      v6 = Windows::Internal::ShellHelpers::PropertySetHelper::SetValue<unsigned int>(a2, v14);
      v7 = v6;
      if ( v6 < 0 )
      {
        v8 = 474;
        goto LABEL_16;
      }
    }
    RemovePropW(hWnd[0], L"TryPositionView");
    RemovePropW(hWnd[0], L"TryPositionView.Left");
    RemovePropW(hWnd[0], L"TryPositionView.Top");
    RemovePropW(hWnd[0], L"TryPositionView.Right");
    RemovePropW(hWnd[0], L"TryPositionView.Bottom");
    RemovePropW(hWnd[0], L"TryPositionView.Flags");
  }
  return 0;
}

```

## disassembly

```asm
0x18037c6a0  mov     [rsp-8+arg_10], rbx
0x18037c6a5  mov     [rsp-8+arg_18], rdi
0x18037c6aa  push    rbp
0x18037c6ab  mov     rbp, rsp
0x18037c6ae  sub     rsp, 70h
0x18037c6b2  mov     rax, cs:__security_cookie
0x18037c6b9  xor     rax, rsp
0x18037c6bc  mov     [rbp+var_10], rax
0x18037c6c0  mov     rdi, rdx
0x18037c6c3  mov     [rbp+hWnd], rcx
0x18037c6c7  lea     rdx, aTrypositionvie_3; "TryPositionView"
0x18037c6ce  call    cs:__imp_GetPropW
0x18037c6d4  test    eax, eax
0x18037c6d6  jz      loc_18037C9E2
0x18037c6dc  lea     rax, [rbp+hWnd]
0x18037c6e0  mov     [rbp+var_40], rax
0x18037c6e4  mov     [rbp+var_38], 1
0x18037c6e8  mov     byte ptr [rbp+var_50], 0
0x18037c6ec  lea     r8, [rbp+var_50]; unsigned __int16 *
0x18037c6f0  lea     rdx, stru_18078D430; HWND
0x18037c6f7  mov     rcx, [rbp+hWnd]; this
0x18037c6fb  call    ?CheckCapabilityFromWindow@CallerIdentity@@YAJPEAUHWND__@@PEBGPEA_N@Z; CallerIdentity::CheckCapabilityFromWindow(HWND__ *,ushort const *,bool *)
0x18037c700  test    eax, eax
0x18037c702  js      loc_18037C97C
0x18037c708  cmp     byte ptr [rbp+var_50], 0
0x18037c70c  jz      loc_18037C97C
0x18037c712  mov     [rbp+var_18], 0
0x18037c71a  mov     r9d, 0Fh; unsigned int
0x18037c720  lea     r8d, [r9+1]; unsigned int
0x18037c724  lea     rdx, aTrypositionvie_3; "TryPositionView"
0x18037c72b  lea     rcx, [rbp+hstringHeader]; hstringHeader
0x18037c72f  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18037c734  nop
0x18037c735  mov     r9b, 1
0x18037c738  mov     rdx, [rbp+var_18]
0x18037c73c  mov     rcx, rdi
0x18037c73f  call    ??$SetValue@E@PropertySetHelper@ShellHelpers@Internal@Windows@@AEAAJPEAUHSTRING__@@P8IPropertyValueStatics@Foundation@3@EAAJEPEAPEAUIInspectable@@@ZE@Z; Windows::Internal::ShellHelpers::PropertySetHelper::SetValue<uchar>(HSTRING__ *,long (Windows::Foundation::IPropertyValueStatics::*)(uchar,IInspectable * *),uchar)
0x18037c744  mov     ebx, eax
0x18037c746  test    eax, eax
0x18037c748  jns     short loc_18037C754
0x18037c74a  mov     edx, 1C6h
0x18037c74f  jmp     loc_18037C8FE
0x18037c754  lea     rdx, aTrypositionvie_2; "TryPositionView.Left"
0x18037c75b  mov     rcx, [rbp+hWnd]; hWnd
0x18037c75f  call    cs:__imp_GetPropW
0x18037c765  mov     rbx, rax
0x18037c768  mov     [rbp+var_18], 0
0x18037c770  mov     r9d, 14h; unsigned int
0x18037c776  lea     r8d, [r9+1]; unsigned int
0x18037c77a  lea     rdx, aTrypositionvie_2; "TryPositionView.Left"
0x18037c781  lea     rcx, [rbp+hstringHeader]; hstringHeader
0x18037c785  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18037c78a  nop
0x18037c78b  mov     r9d, ebx
0x18037c78e  mov     rdx, [rbp+var_18]; HSTRING
0x18037c792  mov     rcx, rdi; this
0x18037c795  call    ??$SetValue@I@PropertySetHelper@ShellHelpers@Internal@Windows@@AEAAJPEAUHSTRING__@@P8IPropertyValueStatics@Foundation@3@EAAJIPEAPEAUIInspectable@@@ZI@Z; Windows::Internal::ShellHelpers::PropertySetHelper::SetValue<uint>(HSTRING__ *,long (Windows::Foundation::IPropertyValueStatics::*)(uint,IInspectable * *),uint)
0x18037c79a  mov     ebx, eax
0x18037c79c  test    eax, eax
0x18037c79e  jns     short loc_18037C7AA
0x18037c7a0  mov     edx, 1CAh
0x18037c7a5  jmp     loc_18037C8FE
0x18037c7aa  lea     rdx, aTrypositionvie; "TryPositionView.Top"
0x18037c7b1  mov     rcx, [rbp+hWnd]; hWnd
0x18037c7b5  call    cs:__imp_GetPropW
0x18037c7bb  mov     rbx, rax
0x18037c7be  mov     [rbp+var_18], 0
0x18037c7c6  mov     r9d, 13h; unsigned int
0x18037c7cc  lea     r8d, [r9+1]; unsigned int
0x18037c7d0  lea     rdx, aTrypositionvie; "TryPositionView.Top"
0x18037c7d7  lea     rcx, [rbp+hstringHeader]; hstringHeader
0x18037c7db  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18037c7e0  nop
0x18037c7e1  mov     r9d, ebx
0x18037c7e4  mov     rdx, [rbp+var_18]; HSTRING
0x18037c7e8  mov     rcx, rdi; this
0x18037c7eb  call    ??$SetValue@I@PropertySetHelper@ShellHelpers@Internal@Windows@@AEAAJPEAUHSTRING__@@P8IPropertyValueStatics@Foundation@3@EAAJIPEAPEAUIInspectable@@@ZI@Z; Windows::Internal::ShellHelpers::PropertySetHelper::SetValue<uint>(HSTRING__ *,long (Windows::Foundation::IPropertyValueStatics::*)(uint,IInspectable * *),uint)
0x18037c7f0  mov     ebx, eax
0x18037c7f2  test    eax, eax
0x18037c7f4  jns     short loc_18037C800
0x18037c7f6  mov     edx, 1CEh
0x18037c7fb  jmp     loc_18037C8FE
0x18037c800  lea     rdx, aTrypositionvie_4; "TryPositionView.Right"
0x18037c807  mov     rcx, [rbp+hWnd]; hWnd
0x18037c80b  call    cs:__imp_GetPropW
0x18037c811  mov     rbx, rax
0x18037c814  mov     [rbp+var_18], 0
0x18037c81c  mov     r9d, 15h; unsigned int
0x18037c822  lea     r8d, [r9+1]; unsigned int
0x18037c826  lea     rdx, aTrypositionvie_4; "TryPositionView.Right"
0x18037c82d  lea     rcx, [rbp+hstringHeader]; hstringHeader
0x18037c831  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18037c836  nop
0x18037c837  mov     r9d, ebx
0x18037c83a  mov     rdx, [rbp+var_18]; HSTRING
0x18037c83e  mov     rcx, rdi; this
0x18037c841  call    ??$SetValue@I@PropertySetHelper@ShellHelpers@Internal@Windows@@AEAAJPEAUHSTRING__@@P8IPropertyValueStatics@Foundation@3@EAAJIPEAPEAUIInspectable@@@ZI@Z; Windows::Internal::ShellHelpers::PropertySetHelper::SetValue<uint>(HSTRING__ *,long (Windows::Foundation::IPropertyValueStatics::*)(uint,IInspectable * *),uint)
0x18037c846  mov     ebx, eax
0x18037c848  test    eax, eax
0x18037c84a  jns     short loc_18037C856
0x18037c84c  mov     edx, 1D2h
0x18037c851  jmp     loc_18037C8FE
0x18037c856  lea     rdx, aTrypositionvie_1; "TryPositionView.Bottom"
0x18037c85d  mov     rcx, [rbp+hWnd]; hWnd
0x18037c861  call    cs:__imp_GetPropW
0x18037c867  mov     rbx, rax
0x18037c86a  mov     [rbp+var_18], 0
0x18037c872  mov     r9d, 16h; unsigned int
0x18037c878  lea     r8d, [r9+1]; unsigned int
0x18037c87c  lea     rdx, aTrypositionvie_1; "TryPositionView.Bottom"
0x18037c883  lea     rcx, [rbp+hstringHeader]; hstringHeader
0x18037c887  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18037c88c  nop
0x18037c88d  mov     r9d, ebx
0x18037c890  mov     rdx, [rbp+var_18]; HSTRING
0x18037c894  mov     rcx, rdi; this
0x18037c897  call    ??$SetValue@I@PropertySetHelper@ShellHelpers@Internal@Windows@@AEAAJPEAUHSTRING__@@P8IPropertyValueStatics@Foundation@3@EAAJIPEAPEAUIInspectable@@@ZI@Z; Windows::Internal::ShellHelpers::PropertySetHelper::SetValue<uint>(HSTRING__ *,long (Windows::Foundation::IPropertyValueStatics::*)(uint,IInspectable * *),uint)
0x18037c89c  mov     ebx, eax
0x18037c89e  test    eax, eax
0x18037c8a0  jns     short loc_18037C8A9
0x18037c8a2  mov     edx, 1D6h
0x18037c8a7  jmp     short loc_18037C8FE
0x18037c8a9  lea     rdx, aTrypositionvie_0; "TryPositionView.Flags"
0x18037c8b0  mov     rcx, [rbp+hWnd]; hWnd
0x18037c8b4  call    cs:__imp_GetPropW
0x18037c8ba  mov     rbx, rax
0x18037c8bd  mov     [rbp+var_18], 0
0x18037c8c5  mov     r9d, 15h; unsigned int
0x18037c8cb  lea     r8d, [r9+1]; unsigned int
0x18037c8cf  lea     rdx, aTrypositionvie_0; "TryPositionView.Flags"
0x18037c8d6  lea     rcx, [rbp+hstringHeader]; hstringHeader
0x18037c8da  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18037c8df  nop
0x18037c8e0  mov     r9d, ebx
0x18037c8e3  mov     rdx, [rbp+var_18]; HSTRING
0x18037c8e7  mov     rcx, rdi; this
0x18037c8ea  call    ??$SetValue@I@PropertySetHelper@ShellHelpers@Internal@Windows@@AEAAJPEAUHSTRING__@@P8IPropertyValueStatics@Foundation@3@EAAJIPEAPEAUIInspectable@@@ZI@Z; Windows::Internal::ShellHelpers::PropertySetHelper::SetValue<uint>(HSTRING__ *,long (Windows::Foundation::IPropertyValueStatics::*)(uint,IInspectable * *),uint)
0x18037c8ef  mov     ebx, eax
0x18037c8f1  test    eax, eax
0x18037c8f3  jns     loc_18037C97C
0x18037c8f9  mov     edx, 1DAh; void *
0x18037c8fe  mov     r9d, eax; char *
0x18037c901  lea     r8, aPcshellTwinuiA_27; "pcshell\\twinui\\appmanager\\lib\\appvi"...
0x18037c908  mov     rcx, [rbp+8]; this
0x18037c90c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18037c911  nop
0x18037c912  lea     rdx, aTrypositionvie_3; "TryPositionView"
0x18037c919  mov     rcx, [rbp+hWnd]; hWnd
0x18037c91d  call    cs:__imp_RemovePropW
0x18037c923  lea     rdx, aTrypositionvie_2; "TryPositionView.Left"
0x18037c92a  mov     rcx, [rbp+hWnd]; hWnd
0x18037c92e  call    cs:__imp_RemovePropW
0x18037c934  lea     rdx, aTrypositionvie; "TryPositionView.Top"
0x18037c93b  mov     rcx, [rbp+hWnd]; hWnd
0x18037c93f  call    cs:__imp_RemovePropW
0x18037c945  lea     rdx, aTrypositionvie_4; "TryPositionView.Right"
0x18037c94c  mov     rcx, [rbp+hWnd]; hWnd
0x18037c950  call    cs:__imp_RemovePropW
0x18037c956  lea     rdx, aTrypositionvie_1; "TryPositionView.Bottom"
0x18037c95d  mov     rcx, [rbp+hWnd]; hWnd
0x18037c961  call    cs:__imp_RemovePropW
0x18037c967  lea     rdx, aTrypositionvie_0; "TryPositionView.Flags"
0x18037c96e  mov     rcx, [rbp+hWnd]; hWnd
0x18037c972  call    cs:__imp_RemovePropW
0x18037c978  mov     eax, ebx
0x18037c97a  jmp     short loc_18037C9E4
0x18037c97c  lea     rdx, aTrypositionvie_3; "TryPositionView"
0x18037c983  mov     rcx, [rbp+hWnd]; hWnd
0x18037c987  call    cs:__imp_RemovePropW
0x18037c98d  lea     rdx, aTrypositionvie_2; "TryPositionView.Left"
0x18037c994  mov     rcx, [rbp+hWnd]; hWnd
0x18037c998  call    cs:__imp_RemovePropW
0x18037c99e  lea     rdx, aTrypositionvie; "TryPositionView.Top"
0x18037c9a5  mov     rcx, [rbp+hWnd]; hWnd
0x18037c9a9  call    cs:__imp_RemovePropW
0x18037c9af  lea     rdx, aTrypositionvie_4; "TryPositionView.Right"
0x18037c9b6  mov     rcx, [rbp+hWnd]; hWnd
0x18037c9ba  call    cs:__imp_RemovePropW
0x18037c9c0  lea     rdx, aTrypositionvie_1; "TryPositionView.Bottom"
0x18037c9c7  mov     rcx, [rbp+hWnd]; hWnd
0x18037c9cb  call    cs:__imp_RemovePropW
0x18037c9d1  lea     rdx, aTrypositionvie_0; "TryPositionView.Flags"
0x18037c9d8  mov     rcx, [rbp+hWnd]; hWnd
0x18037c9dc  call    cs:__imp_RemovePropW
0x18037c9e2  xor     eax, eax
0x18037c9e4  mov     rcx, [rbp+var_10]
0x18037c9e8  xor     rcx, rsp; StackCookie
0x18037c9eb  call    __security_check_cookie
0x18037c9f0  lea     r11, [rsp+70h+var_s0]
0x18037c9f5  mov     rbx, [r11+20h]
0x18037c9f9  mov     rdi, [r11+28h]
0x18037c9fd  mov     rsp, r11
0x18037ca00  pop     rbp
0x18037ca01  retn
```
