# Windows::UI::Core::WindowServer::CreateInputSite(HWND__ *)

- ea: `0x1800252b4`
- end: `0x18002557d`
- name: `?CreateInputSite@WindowServer@Core@UI@Windows@@QEAAJPEAUHWND__@@@Z`
- size: `713`
- prototype: `__int64 __fastcall(Windows::UI::Core::WindowServer *__hidden this, HWND)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1800246c0`

## callees

- `0x1800038e0`
- `0x180014754`
- `0x1800252b4`
- `0x1800264a8`
- `0x180050360`
- `0x1800c73c0`
- `0x1800ca010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800254cf`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800254cf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800252fb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800252fb`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180025324`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180025324`

## string_xrefs

- `0x1800253f6`: `onecoreuap\windows\advcore\winrt\onecoreiwindow\corewindow\common\windowserver.cpp`
- `0x18002549c`: `onecoreuap\windows\advcore\winrt\onecoreiwindow\corewindow\common\windowserver.cpp`
- `0x1800254b1`: `onecoreuap\windows\advcore\winrt\onecoreiwindow\corewindow\common\windowserver.cpp`
- `0x1800254dd`: `onecoreuap\windows\advcore\winrt\onecoreiwindow\corewindow\common\windowserver.cpp`
- `0x180025515`: `onecoreuap\windows\advcore\winrt\onecoreiwindow\corewindow\common\windowserver.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall Windows::UI::Core::WindowServer::CreateInputSite(Windows::UI::Core::WindowServer *this, HWND a2)
{
  unsigned int v2; // ebx
  int v3; // edi
  HRESULT v5; // eax
  HSTRING v6; // rbx
  int ActivationFactory; // eax
  int v8; // eax
  __int64 v9; // rdi
  __int64 v10; // rcx
  __int64 v11; // rcx
  __int64 v13; // rcx
  __int64 (__fastcall ***v14)(_QWORD, GUID *, __int64 *); // rdi
  __int64 (__fastcall *v15)(_QWORD, GUID *, __int64 *); // rbx
  int v16; // eax
  __int64 v17; // rdi
  __int64 (__fastcall *v18)(__int64, __int64 *); // rbx
  int v19; // eax
  int v20; // eax
  __int64 v21; // [rsp+20h] [rbp-50h] BYREF
  __int64 v22; // [rsp+28h] [rbp-48h] BYREF
  __int64 v23; // [rsp+30h] [rbp-40h] BYREF
  __int64 v24; // [rsp+38h] [rbp-38h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+40h] [rbp-30h] BYREF
  HSTRING string; // [rsp+58h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+18h]

  v3 = (int)a2;
  v21 = 0;
  string = 0;
  v5 = WindowsCreateStringReference(L"Windows.UI.Internal.Input.InputSite", 0x23u, &hstringHeader, &string);
  if ( v5 < 0 )
  {
    RaiseException(v5, 1u, 0, 0);
    goto LABEL_20;
  }
  v6 = string;
  Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v21);
  ActivationFactory = RoGetActivationFactory(v6, &GUID_73f80911_7a51_5b0f_906b_f6402ea6c3cb, &v21);
  v2 = ActivationFactory;
  if ( ActivationFactory < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x34A,
      (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\onecoreiwindow\\corewindow\\common\\windowserver.cpp",
      (const char *)(unsigned int)ActivationFactory,
      v21);
    v13 = v21;
    if ( v21 )
    {
      v21 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
    }
    return v2;
  }
  v22 = 0;
  if ( *((_BYTE *)this + 3132) )
  {
    v24 = 0;
    v14 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))*((_QWORD *)this + 402);
    v15 = **v14;
    Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v24);
    v16 = v15(v14, &GUID_9f40e6a8_1040_54e9_a3bc_ccedfeb9e851, &v24);
    if ( v16 < 0 )
      wil::details::in1diag3::FailFast_Hr(
        retaddr,
        (void *)0x35E,
        (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\onecoreiwindow\\corewindow\\common\\windowserver.cpp",
        (const char *)(unsigned int)v16,
        v21);
    v23 = 0;
    v17 = v24;
    v18 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v24 + 48LL);
    Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v23);
    v19 = v18(v17, &v23);
    if ( v19 < 0 )
      wil::details::in1diag3::FailFast_Hr(
        retaddr,
        (void *)0x361,
        (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\onecoreiwindow\\corewindow\\common\\windowserver.cpp",
        (const char *)(unsigned int)v19,
        v21);
    v20 = (*(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v21 + 48LL))(v21, v23, &v22);
    v2 = v20;
    if ( v20 >= 0 )
    {
      Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v23);
      Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v24);
      goto LABEL_5;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x363,
      (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\onecoreiwindow\\corewindow\\common\\windowserver.cpp",
      (const char *)(unsigned int)v20,
      v21);
    Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v23);
    Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v24);
    goto LABEL_23;
  }
  v8 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v21 + 56LL))(v21, v3, &v22);
  v2 = v8;
  if ( v8 < 0 )
  {
LABEL_20:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x353,
      (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\onecoreiwindow\\corewindow\\common\\windowserver.cpp",
      (const char *)(unsigned int)v8,
      v21);
LABEL_23:
    Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v22);
    Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v21);
    return v2;
  }
LABEL_5:
  v9 = v22;
  v22 = 0;
  DisposableComPtr<Windows::UI::Internal::Input::IInputSite>::Close((char *)this + 3296);
  if ( *((_QWORD *)this + 412) )
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 412) + 16LL))(*((_QWORD *)this + 412));
  *((_QWORD *)this + 412) = v9;
  v10 = v22;
  if ( v22 )
  {
    v22 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
  }
  v11 = v21;
  if ( v21 )
  {
    v21 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
  }
  return 0;
}

```

## disassembly

```asm
0x1800252b4  mov     [rsp-18h+arg_10], rbx
0x1800252b9  push    rbp
0x1800252ba  push    rsi
0x1800252bb  push    rdi
0x1800252bc  mov     rbp, rsp
0x1800252bf  sub     rsp, 70h
0x1800252c3  mov     rax, cs:__security_cookie
0x1800252ca  xor     rax, rsp
0x1800252cd  mov     [rbp+var_10], rax
0x1800252d1  mov     rdi, rdx
0x1800252d4  mov     rsi, rcx
0x1800252d7  mov     [rbp+var_50], 0
0x1800252df  mov     [rbp+string], 0
0x1800252e7  lea     r9, [rbp+string]; string
0x1800252eb  lea     r8, [rbp+hstringHeader]; hstringHeader
0x1800252ef  mov     edx, 23h ; '#'; length
0x1800252f4  lea     rcx, ?RuntimeClass_Windows_UI_Internal_Input_InputSite@@3QBGB; "Windows.UI.Internal.Input.InputSite"
0x1800252fb  call    cs:__imp_WindowsCreateStringReference
0x180025301  test    eax, eax
0x180025303  js      loc_1800254C3
0x180025309  mov     rbx, [rbp+string]
0x18002530d  lea     rcx, [rbp+var_50]
0x180025311  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x180025316  lea     r8, [rbp+var_50]
0x18002531a  lea     rdx, _GUID_73f80911_7a51_5b0f_906b_f6402ea6c3cb
0x180025321  mov     rcx, rbx
0x180025324  call    cs:__imp_RoGetActivationFactory
0x18002532a  mov     ebx, eax
0x18002532c  test    eax, eax
0x18002532e  js      loc_1800253EF
0x180025334  mov     [rbp+var_48], 0
0x18002533c  cmp     byte ptr [rsi+0C3Ch], 0
0x180025343  jnz     loc_18002542A
0x180025349  mov     rcx, [rbp+var_50]
0x18002534d  mov     rax, [rcx]
0x180025350  movsxd  rdx, edi
0x180025353  lea     r8, [rbp+var_48]
0x180025357  mov     rax, [rax+38h]
0x18002535b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025360  mov     ebx, eax
0x180025362  test    eax, eax
0x180025364  js      loc_1800254D6
0x18002536a  lea     rbx, [rsi+0CE0h]
0x180025371  mov     rdi, [rbp+var_48]
0x180025375  mov     [rbp+var_48], 0
0x18002537d  mov     rcx, rbx
0x180025380  call    ?Close@?$DisposableComPtr@UIInputSite@Input@Internal@UI@Windows@@@@AEAAXXZ; DisposableComPtr<Windows::UI::Internal::Input::IInputSite>::Close(void)
0x180025385  nop
0x180025386  mov     rcx, [rbx]
0x180025389  test    rcx, rcx
0x18002538c  jnz     loc_18002556B
0x180025392  mov     [rbx], rdi
0x180025395  mov     rcx, [rbp+var_48]
0x180025399  test    rcx, rcx
0x18002539c  jz      short loc_1800253B3
0x18002539e  mov     [rbp+var_48], 0
0x1800253a6  mov     rax, [rcx]
0x1800253a9  mov     rax, [rax+10h]
0x1800253ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800253b2  nop
0x1800253b3  mov     rcx, [rbp+var_50]
0x1800253b7  test    rcx, rcx
0x1800253ba  jz      short loc_1800253D1
0x1800253bc  mov     [rbp+var_50], 0
0x1800253c4  mov     rax, [rcx]
0x1800253c7  mov     rax, [rax+10h]
0x1800253cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800253d0  nop
0x1800253d1  xor     eax, eax
0x1800253d3  mov     rcx, [rbp+var_10]
0x1800253d7  xor     rcx, rsp; StackCookie
0x1800253da  call    __security_check_cookie
0x1800253df  mov     rbx, [rsp+70h+arg_10]
0x1800253e7  add     rsp, 70h
0x1800253eb  pop     rdi
0x1800253ec  pop     rsi
0x1800253ed  pop     rbp
0x1800253ee  retn
0x1800253ef  mov     rcx, [rbp+18h]; this
0x1800253f3  mov     r9d, ebx; char *
0x1800253f6  lea     r8, aOnecoreuapWind_28; "onecoreuap\\windows\\advcore\\winrt\\on"...
0x1800253fd  mov     edx, 34Ah; void *
0x180025402  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180025407  nop
0x180025408  mov     rcx, [rbp+var_50]
0x18002540c  test    rcx, rcx
0x18002540f  jz      short loc_180025426
0x180025411  mov     [rbp+var_50], 0
0x180025419  mov     rax, [rcx]
0x18002541c  mov     rax, [rax+10h]
0x180025420  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025425  nop
0x180025426  mov     eax, ebx
0x180025428  jmp     short loc_1800253D3
0x18002542a  mov     [rbp+var_38], 0
0x180025432  mov     rdi, [rsi+0C90h]
0x180025439  mov     rax, [rdi]
0x18002543c  mov     rbx, [rax]
0x18002543f  lea     rcx, [rbp+var_38]
0x180025443  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x180025448  lea     r8, [rbp+var_38]
0x18002544c  lea     rdx, _GUID_9f40e6a8_1040_54e9_a3bc_ccedfeb9e851
0x180025453  mov     rcx, rdi
0x180025456  mov     rax, rbx
0x180025459  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002545e  mov     rcx, [rbp+18h]; this
0x180025462  test    eax, eax
0x180025464  js      short loc_1800254AE
0x180025466  mov     [rbp+var_40], 0
0x18002546e  mov     rdi, [rbp+var_38]
0x180025472  mov     rax, [rdi]
0x180025475  mov     rbx, [rax+30h]
0x180025479  lea     rcx, [rbp+var_40]
0x18002547d  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x180025482  lea     rdx, [rbp+var_40]
0x180025486  mov     rcx, rdi
0x180025489  mov     rax, rbx
0x18002548c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025491  mov     rcx, [rbp+18h]; this
0x180025495  test    eax, eax
0x180025497  jns     short loc_1800254F0
0x180025499  mov     r9d, eax; char *
0x18002549c  lea     r8, aOnecoreuapWind_28; "onecoreuap\\windows\\advcore\\winrt\\on"...
0x1800254a3  mov     edx, 361h; void *
0x1800254a8  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x1800254ae  mov     r9d, eax; char *
0x1800254b1  lea     r8, aOnecoreuapWind_28; "onecoreuap\\windows\\advcore\\winrt\\on"...
0x1800254b8  mov     edx, 35Eh; void *
0x1800254bd  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x1800254c3  xor     r9d, r9d; lpArguments
0x1800254c6  xor     r8d, r8d; nNumberOfArguments
0x1800254c9  lea     edx, [r9+1]; dwExceptionFlags
0x1800254cd  mov     ecx, eax; dwExceptionCode
0x1800254cf  call    cs:__imp_RaiseException
0x1800254d5  nop
0x1800254d6  mov     rcx, [rbp+18h]; this
0x1800254da  mov     r9d, eax; char *
0x1800254dd  lea     r8, aOnecoreuapWind_28; "onecoreuap\\windows\\advcore\\winrt\\on"...
0x1800254e4  mov     edx, 353h; void *
0x1800254e9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800254ee  jmp     short loc_18002553B
0x1800254f0  mov     rcx, [rbp+var_50]
0x1800254f4  mov     rax, [rcx]
0x1800254f7  lea     r8, [rbp+var_48]
0x1800254fb  mov     rdx, [rbp+var_40]
0x1800254ff  mov     rax, [rax+30h]
0x180025503  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025508  mov     ebx, eax
0x18002550a  test    eax, eax
0x18002550c  jns     short loc_180025553
0x18002550e  mov     rcx, [rbp+18h]; this
0x180025512  mov     r9d, eax; char *
0x180025515  lea     r8, aOnecoreuapWind_28; "onecoreuap\\windows\\advcore\\winrt\\on"...
0x18002551c  mov     edx, 363h; void *
0x180025521  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180025526  nop
0x180025527  lea     rcx, [rbp+var_40]
0x18002552b  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x180025530  nop
0x180025531  lea     rcx, [rbp+var_38]
0x180025535  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x18002553a  nop
0x18002553b  lea     rcx, [rbp+var_48]
0x18002553f  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x180025544  nop
0x180025545  lea     rcx, [rbp+var_50]
0x180025549  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x18002554e  jmp     loc_180025426
0x180025553  lea     rcx, [rbp+var_40]
0x180025557  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x18002555c  nop
0x18002555d  lea     rcx, [rbp+var_38]
0x180025561  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x180025566  jmp     loc_18002536A
0x18002556b  mov     rax, [rcx]
0x18002556e  mov     rax, [rax+10h]
0x180025572  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025577  jmp     loc_180025392
```
