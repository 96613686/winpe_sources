# Windows::UI::Core::WindowServer::AttachWindowsMessageDeliveryInputObject(HWND__ *)

- ea: `0x180025584`
- end: `0x180025824`
- name: `?AttachWindowsMessageDeliveryInputObject@WindowServer@Core@UI@Windows@@QEAAXPEAUHWND__@@@Z`
- size: `672`
- prototype: `void __fastcall(Windows::UI::Core::WindowServer *__hidden this, HWND)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1800246c0`

## callees

- `0x1800038e0`
- `0x180025584`
- `0x180050360`
- `0x1800c73c0`
- `0x1800ca010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18002580a`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18002581d`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18002580a`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18002581d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800255ce`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180025658`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800255ce`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180025658`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800255f7`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180025681`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800255f7`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180025681`

## string_xrefs

- `0x180025764`: `onecoreuap\windows\advcore\winrt\onecoreiwindow\corewindow\common\windowserver.cpp`
- `0x180025779`: `onecoreuap\windows\advcore\winrt\onecoreiwindow\corewindow\common\windowserver.cpp`
- `0x18002578e`: `onecoreuap\windows\advcore\winrt\onecoreiwindow\corewindow\common\windowserver.cpp`
- `0x1800257a3`: `onecoreuap\windows\advcore\winrt\onecoreiwindow\corewindow\common\windowserver.cpp`
- `0x1800257ec`: `onecoreuap\windows\advcore\winrt\onecoreiwindow\corewindow\common\windowserver.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
void __fastcall Windows::UI::Core::WindowServer::AttachWindowsMessageDeliveryInputObject(
        Windows::UI::Core::WindowServer *this,
        HWND a2)
{
  unsigned int v2; // edi
  HRESULT v3; // eax
  HSTRING v4; // rbx
  int ActivationFactory; // eax
  int v6; // eax
  HRESULT v7; // eax
  HSTRING v8; // rbx
  int v9; // eax
  int v10; // eax
  __int64 v11; // rcx
  __int64 v12; // rcx
  __int64 v13; // rcx
  __int64 v14; // rcx
  int v15; // eax
  int v16; // [rsp+20h] [rbp-60h]
  __int64 v17; // [rsp+30h] [rbp-50h] BYREF
  int v18[2]; // [rsp+38h] [rbp-48h] BYREF
  __int64 v19; // [rsp+40h] [rbp-40h] BYREF
  __int64 v20; // [rsp+48h] [rbp-38h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+50h] [rbp-30h] BYREF
  HSTRING string; // [rsp+68h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+8h]

  v2 = (unsigned int)a2;
  v20 = 0;
  string = 0;
  v3 = WindowsCreateStringReference(L"Windows.UI.Internal.Input.InputSite", 0x23u, &hstringHeader, &string);
  if ( v3 < 0 )
  {
    RaiseException(v3, 1u, 0, 0);
    goto LABEL_25;
  }
  v4 = string;
  Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v20);
  ActivationFactory = RoGetActivationFactory(v4, &GUID_73f80911_7a51_5b0f_906b_f6402ea6c3cb, &v20);
  if ( ActivationFactory < 0 )
    wil::details::in1diag3::FailFast_Hr(
      retaddr,
      (void *)0x36F,
      (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\onecoreiwindow\\corewindow\\common\\windowserver.cpp",
      (const char *)(unsigned int)ActivationFactory,
      v16);
  v19 = 0;
  v6 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v20 + 56LL))(v20, (int)v2, &v19);
  if ( v6 < 0 )
    wil::details::in1diag3::FailFast_Hr(
      retaddr,
      (void *)0x372,
      (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\onecoreiwindow\\corewindow\\common\\windowserver.cpp",
      (const char *)(unsigned int)v6,
      v16);
  v17 = 0;
  string = 0;
  v7 = WindowsCreateStringReference(L"Windows.UI.Internal.Input.WindowsMessageDelivery", 0x30u, &hstringHeader, &string);
  if ( v7 < 0 )
  {
LABEL_25:
    RaiseException(v7, 1u, 0, 0);
    JUMPOUT(0x180025823LL);
  }
  v8 = string;
  Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v17);
  v9 = RoGetActivationFactory(v8, &GUID_51344833_a92f_5989_87ed_e1282500d7c8, &v17);
  if ( v9 < 0 )
    wil::details::in1diag3::FailFast_Hr(
      retaddr,
      (void *)0x376,
      (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\onecoreiwindow\\corewindow\\common\\windowserver.cpp",
      (const char *)(unsigned int)v9,
      v16);
  *(_QWORD *)v18 = 0;
  v10 = (*(__int64 (__fastcall **)(__int64, __int64, int *))(*(_QWORD *)v17 + 56LL))(v17, v19, v18);
  if ( v10 < 0 )
    wil::details::in1diag3::FailFast_Hr(
      retaddr,
      (void *)0x37B,
      (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\onecoreiwindow\\corewindow\\common\\windowserver.cpp",
      (const char *)(unsigned int)v10,
      v16);
  v11 = *(_QWORD *)v18;
  if ( !*(_QWORD *)v18 )
  {
    v15 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, _QWORD))(*(_QWORD *)v17 + 48LL))(v17, v19, v2, 0);
    if ( v15 < 0 )
      wil::details::in1diag3::FailFast_Hr(
        retaddr,
        (void *)0x383,
        (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\onecoreiwindow\\corewindow\\common\\windowserver.cpp",
        (const char *)(unsigned int)v15,
        (int)v18);
    v11 = *(_QWORD *)v18;
  }
  if ( v11 )
  {
    *(_QWORD *)v18 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
  }
  v12 = v17;
  if ( v17 )
  {
    v17 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
  }
  v13 = v19;
  if ( v19 )
  {
    v19 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
  }
  v14 = v20;
  if ( v20 )
  {
    v20 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
  }
}

```

## disassembly

```asm
0x180025584  mov     [rsp-8+arg_0], rbx
0x180025589  mov     [rsp-8+arg_10], rdi
0x18002558e  push    rbp
0x18002558f  mov     rbp, rsp
0x180025592  sub     rsp, 80h
0x180025599  mov     rax, cs:__security_cookie
0x1800255a0  xor     rax, rsp
0x1800255a3  mov     [rbp+var_10], rax
0x1800255a7  mov     rdi, rdx
0x1800255aa  mov     [rbp+var_38], 0
0x1800255b2  mov     [rbp+string], 0
0x1800255ba  lea     r9, [rbp+string]; string
0x1800255be  lea     r8, [rbp+hstringHeader]; hstringHeader
0x1800255c2  mov     edx, 23h ; '#'; length
0x1800255c7  lea     rcx, ?RuntimeClass_Windows_UI_Internal_Input_InputSite@@3QBGB; "Windows.UI.Internal.Input.InputSite"
0x1800255ce  call    cs:__imp_WindowsCreateStringReference
0x1800255d4  test    eax, eax
0x1800255d6  js      loc_1800257FE
0x1800255dc  mov     rbx, [rbp+string]
0x1800255e0  lea     rcx, [rbp+var_38]
0x1800255e4  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x1800255e9  lea     r8, [rbp+var_38]
0x1800255ed  lea     rdx, _GUID_73f80911_7a51_5b0f_906b_f6402ea6c3cb
0x1800255f4  mov     rcx, rbx
0x1800255f7  call    cs:__imp_RoGetActivationFactory
0x1800255fd  mov     rcx, [rbp+8]; this
0x180025601  test    eax, eax
0x180025603  js      loc_180025761
0x180025609  mov     [rbp+var_40], 0
0x180025611  mov     rcx, [rbp+var_38]
0x180025615  mov     rax, [rcx]
0x180025618  movsxd  rdx, edi
0x18002561b  lea     r8, [rbp+var_40]
0x18002561f  mov     rax, [rax+38h]
0x180025623  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025628  mov     rcx, [rbp+8]; this
0x18002562c  test    eax, eax
0x18002562e  js      loc_180025776
0x180025634  mov     [rbp+var_50], 0
0x18002563c  mov     [rbp+string], 0
0x180025644  lea     r9, [rbp+string]; string
0x180025648  lea     r8, [rbp+hstringHeader]; hstringHeader
0x18002564c  mov     edx, 30h ; '0'; length
0x180025651  lea     rcx, ?RuntimeClass_Windows_UI_Internal_Input_WindowsMessageDelivery@@3QBGB; "Windows.UI.Internal.Input.WindowsMessag"...
0x180025658  call    cs:__imp_WindowsCreateStringReference
0x18002565e  test    eax, eax
0x180025660  js      loc_180025811
0x180025666  mov     rbx, [rbp+string]
0x18002566a  lea     rcx, [rbp+var_50]
0x18002566e  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x180025673  lea     r8, [rbp+var_50]
0x180025677  lea     rdx, _GUID_51344833_a92f_5989_87ed_e1282500d7c8
0x18002567e  mov     rcx, rbx
0x180025681  call    cs:__imp_RoGetActivationFactory
0x180025687  mov     rcx, [rbp+8]; this
0x18002568b  test    eax, eax
0x18002568d  js      loc_18002578B
0x180025693  mov     qword ptr [rbp+var_48], 0
0x18002569b  mov     rcx, [rbp+var_50]
0x18002569f  mov     rax, [rcx]
0x1800256a2  lea     r8, [rbp+var_48]
0x1800256a6  mov     rdx, [rbp+var_40]
0x1800256aa  mov     rax, [rax+38h]
0x1800256ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800256b3  mov     rcx, [rbp+8]; this
0x1800256b7  test    eax, eax
0x1800256b9  js      loc_1800257A0
0x1800256bf  mov     rcx, qword ptr [rbp+var_48]
0x1800256c3  test    rcx, rcx
0x1800256c6  jz      loc_1800257B5
0x1800256cc  test    rcx, rcx
0x1800256cf  jz      short loc_1800256E6
0x1800256d1  mov     qword ptr [rbp+var_48], 0
0x1800256d9  mov     rax, [rcx]
0x1800256dc  mov     rax, [rax+10h]
0x1800256e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800256e5  nop
0x1800256e6  mov     rcx, [rbp+var_50]
0x1800256ea  test    rcx, rcx
0x1800256ed  jz      short loc_180025704
0x1800256ef  mov     [rbp+var_50], 0
0x1800256f7  mov     rax, [rcx]
0x1800256fa  mov     rax, [rax+10h]
0x1800256fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025703  nop
0x180025704  mov     rcx, [rbp+var_40]
0x180025708  test    rcx, rcx
0x18002570b  jz      short loc_180025722
0x18002570d  mov     [rbp+var_40], 0
0x180025715  mov     rax, [rcx]
0x180025718  mov     rax, [rax+10h]
0x18002571c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025721  nop
0x180025722  mov     rcx, [rbp+var_38]
0x180025726  test    rcx, rcx
0x180025729  jz      short loc_180025740
0x18002572b  mov     [rbp+var_38], 0
0x180025733  mov     rax, [rcx]
0x180025736  mov     rax, [rax+10h]
0x18002573a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002573f  nop
0x180025740  mov     rcx, [rbp+var_10]
0x180025744  xor     rcx, rsp; StackCookie
0x180025747  call    __security_check_cookie
0x18002574c  lea     r11, [rsp+80h+var_s0]
0x180025754  mov     rbx, [r11+10h]
0x180025758  mov     rdi, [r11+20h]
0x18002575c  mov     rsp, r11
0x18002575f  pop     rbp
0x180025760  retn
0x180025761  mov     r9d, eax; char *
0x180025764  lea     r8, aOnecoreuapWind_28; "onecoreuap\\windows\\advcore\\winrt\\on"...
0x18002576b  mov     edx, 36Fh; void *
0x180025770  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x180025776  mov     r9d, eax; char *
0x180025779  lea     r8, aOnecoreuapWind_28; "onecoreuap\\windows\\advcore\\winrt\\on"...
0x180025780  mov     edx, 372h; void *
0x180025785  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x18002578b  mov     r9d, eax; char *
0x18002578e  lea     r8, aOnecoreuapWind_28; "onecoreuap\\windows\\advcore\\winrt\\on"...
0x180025795  mov     edx, 376h; void *
0x18002579a  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x1800257a0  mov     r9d, eax; char *
0x1800257a3  lea     r8, aOnecoreuapWind_28; "onecoreuap\\windows\\advcore\\winrt\\on"...
0x1800257aa  mov     edx, 37Bh; void *
0x1800257af  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x1800257b5  mov     rcx, [rbp+var_50]
0x1800257b9  mov     rax, [rcx]
0x1800257bc  mov     r8d, edi
0x1800257bf  lea     rdx, [rbp+var_48]
0x1800257c3  mov     qword ptr [rsp+80h+var_60], rdx; int
0x1800257c8  xor     r9d, r9d
0x1800257cb  mov     rdx, [rbp+var_40]
0x1800257cf  mov     rax, [rax+30h]
0x1800257d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800257d8  mov     rcx, [rbp+8]; this
0x1800257dc  test    eax, eax
0x1800257de  js      short loc_1800257E9
0x1800257e0  mov     rcx, qword ptr [rbp+var_48]
0x1800257e4  jmp     loc_1800256CC
0x1800257e9  mov     r9d, eax; char *
0x1800257ec  lea     r8, aOnecoreuapWind_28; "onecoreuap\\windows\\advcore\\winrt\\on"...
0x1800257f3  mov     edx, 383h; void *
0x1800257f8  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x1800257fe  xor     r9d, r9d; lpArguments
0x180025801  xor     r8d, r8d; nNumberOfArguments
0x180025804  lea     edx, [r9+1]; dwExceptionFlags
0x180025808  mov     ecx, eax; dwExceptionCode
0x18002580a  call    cs:__imp_RaiseException
0x180025810  nop
0x180025811  xor     r9d, r9d; lpArguments
0x180025814  xor     r8d, r8d; nNumberOfArguments
0x180025817  lea     edx, [r9+1]; dwExceptionFlags
0x18002581b  mov     ecx, eax; dwExceptionCode
0x18002581d  call    cs:__imp_RaiseException
```
