# Windows::UI::Core::WindowServer::CreateActivationController(HWND__ *)

- ea: `0x180023b5c`
- end: `0x180023d41`
- name: `?CreateActivationController@WindowServer@Core@UI@Windows@@QEAAJPEAUHWND__@@@Z`
- size: `485`
- prototype: `__int64 __fastcall(Windows::UI::Core::WindowServer *__hidden this, HWND)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180018350`

## callees

- `0x1800038e0`
- `0x180014754`
- `0x180023b5c`
- `0x180023d6c`
- `0x1800c73c0`
- `0x1800ca010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180023d28`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180023d28`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180023ba3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180023ba3`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180023bcc`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180023bcc`

## string_xrefs

- `0x180023c91`: `onecoreuap\windows\advcore\winrt\onecoreiwindow\corewindow\common\windowserver.cpp`
- `0x180023cea`: `onecoreuap\windows\advcore\winrt\onecoreiwindow\corewindow\common\windowserver.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall Windows::UI::Core::WindowServer::CreateActivationController(
        Windows::UI::Core::WindowServer *this,
        HWND a2)
{
  __int64 *v2; // rbx
  int v3; // esi
  HRESULT v5; // eax
  HSTRING v6; // rbx
  int ActivationFactory; // eax
  unsigned int v8; // ebx
  int v9; // eax
  __int64 v10; // rcx
  Windows::UI::Core::WindowServer *v11; // rcx
  __int64 v12; // rcx
  Windows::UI::Core::WindowServer *v14; // rcx
  __int64 v15; // rcx
  __int64 v16; // rcx
  __int64 v17; // [rsp+20h] [rbp-40h] BYREF
  Windows::UI::Core::WindowServer *v18; // [rsp+28h] [rbp-38h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+30h] [rbp-30h] BYREF
  HSTRING string; // [rsp+48h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+18h]

  v3 = (int)a2;
  v17 = 0;
  string = 0;
  v5 = WindowsCreateStringReference(L"Windows.UI.Internal.Input.ActivationController", 0x2Eu, &hstringHeader, &string);
  if ( v5 < 0 )
  {
    RaiseException(v5, 1u, 0, 0);
    goto LABEL_19;
  }
  v6 = string;
  Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v17);
  ActivationFactory = RoGetActivationFactory(v6, &GUID_d91fd4d4_4fb2_516f_938c_c27e3a1addd7, &v17);
  v8 = ActivationFactory;
  if ( ActivationFactory < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x452,
      (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\onecoreiwindow\\corewindow\\common\\windowserver.cpp",
      (const char *)(unsigned int)ActivationFactory,
      v17);
    v16 = v17;
    if ( v17 )
    {
      v17 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
    }
    return v8;
  }
  v18 = 0;
  v9 = (*(__int64 (__fastcall **)(__int64, _QWORD, Windows::UI::Core::WindowServer **))(*(_QWORD *)v17 + 48LL))(
         v17,
         v3,
         &v18);
  v8 = v9;
  if ( v9 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x455,
      (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\onecoreiwindow\\corewindow\\common\\windowserver.cpp",
      (const char *)(unsigned int)v9,
      v17);
    v14 = v18;
    if ( v18 )
    {
      v18 = 0;
      (*(void (__fastcall **)(Windows::UI::Core::WindowServer *))(*(_QWORD *)v14 + 16LL))(v14);
    }
    v15 = v17;
    if ( v17 )
    {
      v17 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
    }
    return v8;
  }
  v2 = (__int64 *)((char *)this + 3304);
  this = v18;
  v18 = 0;
  DisposableComPtr<Windows::UI::Internal::Input::IActivationController>::Close(v2);
  v10 = *v2;
  if ( *v2 )
LABEL_19:
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
  *v2 = (__int64)this;
  v11 = v18;
  if ( v18 )
  {
    v18 = 0;
    (*(void (__fastcall **)(Windows::UI::Core::WindowServer *))(*(_QWORD *)v11 + 16LL))(v11);
  }
  v12 = v17;
  if ( v17 )
  {
    v17 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
  }
  return 0;
}

```

## disassembly

```asm
0x180023b5c  mov     [rsp-18h+arg_10], rbx
0x180023b61  push    rbp
0x180023b62  push    rsi
0x180023b63  push    rdi
0x180023b64  mov     rbp, rsp
0x180023b67  sub     rsp, 60h
0x180023b6b  mov     rax, cs:__security_cookie
0x180023b72  xor     rax, rsp
0x180023b75  mov     [rbp+var_10], rax
0x180023b79  mov     rsi, rdx
0x180023b7c  mov     rdi, rcx
0x180023b7f  mov     [rbp+var_40], 0
0x180023b87  mov     [rbp+string], 0
0x180023b8f  lea     r9, [rbp+string]; string
0x180023b93  lea     r8, [rbp+hstringHeader]; hstringHeader
0x180023b97  mov     edx, 2Eh ; '.'; length
0x180023b9c  lea     rcx, ?RuntimeClass_Windows_UI_Internal_Input_ActivationController@@3QBGB; "Windows.UI.Internal.Input.ActivationCon"...
0x180023ba3  call    cs:__imp_WindowsCreateStringReference
0x180023ba9  test    eax, eax
0x180023bab  js      loc_180023D1C
0x180023bb1  mov     rbx, [rbp+string]
0x180023bb5  lea     rcx, [rbp+var_40]
0x180023bb9  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x180023bbe  lea     r8, [rbp+var_40]
0x180023bc2  lea     rdx, _GUID_d91fd4d4_4fb2_516f_938c_c27e3a1addd7
0x180023bc9  mov     rcx, rbx
0x180023bcc  call    cs:__imp_RoGetActivationFactory
0x180023bd2  mov     ebx, eax
0x180023bd4  test    eax, eax
0x180023bd6  js      loc_180023CE3
0x180023bdc  mov     [rbp+var_38], 0
0x180023be4  mov     rcx, [rbp+var_40]
0x180023be8  mov     rax, [rcx]
0x180023beb  movsxd  rdx, esi
0x180023bee  lea     r8, [rbp+var_38]
0x180023bf2  mov     rax, [rax+30h]
0x180023bf6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023bfb  mov     ebx, eax
0x180023bfd  test    eax, eax
0x180023bff  js      loc_180023C8A
0x180023c05  lea     rbx, [rdi+0CE8h]
0x180023c0c  mov     rdi, [rbp+var_38]
0x180023c10  mov     [rbp+var_38], 0
0x180023c18  mov     rcx, rbx
0x180023c1b  call    ?Close@?$DisposableComPtr@UIActivationController@Input@Internal@UI@Windows@@@@AEAAXXZ; DisposableComPtr<Windows::UI::Internal::Input::IActivationController>::Close(void)
0x180023c20  nop
0x180023c21  mov     rcx, [rbx]
0x180023c24  test    rcx, rcx
0x180023c27  jnz     loc_180023D2F
0x180023c2d  mov     [rbx], rdi
0x180023c30  mov     rcx, [rbp+var_38]
0x180023c34  test    rcx, rcx
0x180023c37  jz      short loc_180023C4E
0x180023c39  mov     [rbp+var_38], 0
0x180023c41  mov     rax, [rcx]
0x180023c44  mov     rax, [rax+10h]
0x180023c48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023c4d  nop
0x180023c4e  mov     rcx, [rbp+var_40]
0x180023c52  test    rcx, rcx
0x180023c55  jz      short loc_180023C6C
0x180023c57  mov     [rbp+var_40], 0
0x180023c5f  mov     rax, [rcx]
0x180023c62  mov     rax, [rax+10h]
0x180023c66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023c6b  nop
0x180023c6c  xor     eax, eax
0x180023c6e  mov     rcx, [rbp+var_10]
0x180023c72  xor     rcx, rsp; StackCookie
0x180023c75  call    __security_check_cookie
0x180023c7a  mov     rbx, [rsp+60h+arg_10]
0x180023c82  add     rsp, 60h
0x180023c86  pop     rdi
0x180023c87  pop     rsi
0x180023c88  pop     rbp
0x180023c89  retn
0x180023c8a  mov     rcx, [rbp+18h]; this
0x180023c8e  mov     r9d, ebx; char *
0x180023c91  lea     r8, aOnecoreuapWind_28; "onecoreuap\\windows\\advcore\\winrt\\on"...
0x180023c98  mov     edx, 455h; void *
0x180023c9d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180023ca2  nop
0x180023ca3  mov     rcx, [rbp+var_38]
0x180023ca7  test    rcx, rcx
0x180023caa  jz      short loc_180023CC1
0x180023cac  mov     [rbp+var_38], 0
0x180023cb4  mov     rax, [rcx]
0x180023cb7  mov     rax, [rax+10h]
0x180023cbb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023cc0  nop
0x180023cc1  mov     rcx, [rbp+var_40]
0x180023cc5  test    rcx, rcx
0x180023cc8  jz      short loc_180023CDF
0x180023cca  mov     [rbp+var_40], 0
0x180023cd2  mov     rax, [rcx]
0x180023cd5  mov     rax, [rax+10h]
0x180023cd9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023cde  nop
0x180023cdf  mov     eax, ebx
0x180023ce1  jmp     short loc_180023C6E
0x180023ce3  mov     rcx, [rbp+18h]; this
0x180023ce7  mov     r9d, ebx; char *
0x180023cea  lea     r8, aOnecoreuapWind_28; "onecoreuap\\windows\\advcore\\winrt\\on"...
0x180023cf1  mov     edx, 452h; void *
0x180023cf6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180023cfb  nop
0x180023cfc  mov     rcx, [rbp+var_40]
0x180023d00  test    rcx, rcx
0x180023d03  jz      short loc_180023D1A
0x180023d05  mov     [rbp+var_40], 0
0x180023d0d  mov     rax, [rcx]
0x180023d10  mov     rax, [rax+10h]
0x180023d14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023d19  nop
0x180023d1a  jmp     short loc_180023CDF
0x180023d1c  xor     r9d, r9d; lpArguments
0x180023d1f  xor     r8d, r8d; nNumberOfArguments
0x180023d22  lea     edx, [r9+1]; dwExceptionFlags
0x180023d26  mov     ecx, eax; dwExceptionCode
0x180023d28  call    cs:__imp_RaiseException
0x180023d2e  nop
0x180023d2f  mov     rax, [rcx]
0x180023d32  mov     rax, [rax+10h]
0x180023d36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023d3b  jmp     loc_180023C2D
```
