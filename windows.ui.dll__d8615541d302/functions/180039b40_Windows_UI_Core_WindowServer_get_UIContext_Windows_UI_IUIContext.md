# Windows::UI::Core::WindowServer::get_UIContext(Windows::UI::IUIContext * *)

- ea: `0x180039b40`
- end: `0x180039cc1`
- name: `?get_UIContext@WindowServer@Core@UI@Windows@@UEAAJPEAPEAUIUIContext@34@@Z`
- size: `385`
- prototype: `__int64 __fastcall(Windows::UI::Core::WindowServer *__hidden this, struct Windows::UI::IUIContext **)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x1800038e0`
- `0x180039b40`
- `0x180050360`
- `0x1800c73c0`
- `0x1800ca010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180039cba`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180039cba`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180039ba5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180039ba5`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180039bd1`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180039bd1`

## string_xrefs

- `0x180039c87`: `onecoreuap\windows\advcore\winrt\onecoreiwindow\corewindow\common\windowserver.cpp`
- `0x180039c9c`: `onecoreuap\windows\advcore\winrt\onecoreiwindow\corewindow\common\windowserver.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::UI::Core::WindowServer::get_UIContext(
        Windows::UI::Core::WindowServer *this,
        struct Windows::UI::IUIContext **a2)
{
  char *v4; // rbp
  HRESULT v5; // eax
  HSTRING v6; // rbx
  int ActivationFactory; // eax
  __int64 v8; // rdi
  __int64 (__fastcall *v9)(__int64, char *, _QWORD, _QWORD *); // rbx
  _QWORD *v10; // rsi
  int v11; // eax
  __int64 v12; // rcx
  int v14; // [rsp+20h] [rbp-58h]
  __int64 v15; // [rsp+30h] [rbp-48h] BYREF
  HSTRING_HEADER v16; // [rsp+38h] [rbp-40h] BYREF
  HSTRING v17; // [rsp+50h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  *a2 = 0;
  v4 = (char *)this - 64;
  if ( *((_QWORD *)this + 410) )
  {
    v10 = (_QWORD *)((char *)this + 3280);
  }
  else
  {
    v15 = 0;
    v17 = 0;
    v5 = WindowsCreateStringReference(L"Windows.UI.UIContext", 0x14u, &v16, &v17);
    if ( v5 < 0 )
    {
      RaiseException(v5, 1u, 0, 0);
      JUMPOUT(0x180039CC0LL);
    }
    v6 = v17;
    Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v15);
    ActivationFactory = RoGetActivationFactory(v6, &GUID_97473389_5b37_5c96_9c2b_0fd29d43a6c1, &v15);
    if ( ActivationFactory < 0 )
      wil::details::in1diag3::FailFast_Hr(
        retaddr,
        (void *)0x132C,
        (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\onecoreiwindow\\corewindow\\common\\windowserver.cpp",
        (const char *)(unsigned int)ActivationFactory,
        v14);
    v8 = v15;
    v9 = *(__int64 (__fastcall **)(__int64, char *, _QWORD, _QWORD *))(*(_QWORD *)v15 + 56LL);
    v10 = (_QWORD *)((char *)this + 3280);
    Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(v10);
    v11 = v9(v8, v4, 0, v10);
    if ( v11 < 0 )
      wil::details::in1diag3::FailFast_Hr(
        retaddr,
        (void *)0x132E,
        (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\onecoreiwindow\\corewindow\\common\\windowserver.cpp",
        (const char *)(unsigned int)v11,
        v14);
    v12 = v15;
    if ( v15 )
    {
      v15 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
    }
  }
  if ( *v10 )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v10 + 8LL))(*v10);
  *a2 = (struct Windows::UI::IUIContext *)*v10;
  return 0;
}

```

## disassembly

```asm
0x180039b40  mov     r11, rsp
0x180039b43  mov     [r11+18h], rbx
0x180039b47  mov     [r11+20h], rbp
0x180039b4b  push    rsi
0x180039b4c  push    rdi
0x180039b4d  push    r14
0x180039b4f  sub     rsp, 60h
0x180039b53  mov     rax, cs:__security_cookie
0x180039b5a  xor     rax, rsp
0x180039b5d  mov     [rsp+78h+var_20], rax
0x180039b62  mov     r14, rdx
0x180039b65  mov     rsi, rcx
0x180039b68  mov     qword ptr [rdx], 0
0x180039b6f  lea     rbp, [rcx-40h]
0x180039b73  cmp     qword ptr [rbp+0D10h], 0
0x180039b7b  jnz     loc_180039C7B
0x180039b81  mov     qword ptr [r11-48h], 0
0x180039b89  mov     qword ptr [r11-28h], 0
0x180039b91  lea     r9, [r11-28h]; string
0x180039b95  lea     r8, [r11-40h]; hstringHeader
0x180039b99  mov     edx, 14h; length
0x180039b9e  lea     rcx, ?RuntimeClass_Windows_UI_UIContext@@3QBGB; "Windows.UI.UIContext"
0x180039ba5  call    cs:__imp_WindowsCreateStringReference
0x180039bab  test    eax, eax
0x180039bad  js      loc_180039CAE
0x180039bb3  mov     rbx, [rsp+78h+var_28]
0x180039bb8  lea     rcx, [rsp+78h+var_48]
0x180039bbd  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x180039bc2  lea     r8, [rsp+78h+var_48]
0x180039bc7  lea     rdx, _GUID_97473389_5b37_5c96_9c2b_0fd29d43a6c1
0x180039bce  mov     rcx, rbx
0x180039bd1  call    cs:__imp_RoGetActivationFactory
0x180039bd7  mov     rcx, [rsp+78h]; this
0x180039bdc  test    eax, eax
0x180039bde  js      loc_180039C84
0x180039be4  mov     rdi, [rsp+78h+var_48]
0x180039be9  mov     rax, [rdi]
0x180039bec  mov     rbx, [rax+38h]
0x180039bf0  add     rsi, 0CD0h
0x180039bf7  mov     rcx, rsi
0x180039bfa  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x180039bff  mov     r9, rsi
0x180039c02  xor     r8d, r8d
0x180039c05  mov     rdx, rbp
0x180039c08  mov     rcx, rdi
0x180039c0b  mov     rax, rbx
0x180039c0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039c13  mov     rcx, [rsp+78h]; this
0x180039c18  test    eax, eax
0x180039c1a  js      short loc_180039C99
0x180039c1c  mov     rcx, [rsp+78h+var_48]
0x180039c21  test    rcx, rcx
0x180039c24  jz      short loc_180039C3C
0x180039c26  mov     [rsp+78h+var_48], 0
0x180039c2f  mov     rax, [rcx]
0x180039c32  mov     rax, [rax+10h]
0x180039c36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039c3b  nop
0x180039c3c  mov     rcx, [rsi]
0x180039c3f  test    rcx, rcx
0x180039c42  jz      short loc_180039C51
0x180039c44  mov     rax, [rcx]
0x180039c47  mov     rax, [rax+8]
0x180039c4b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039c50  nop
0x180039c51  mov     rax, [rsi]
0x180039c54  mov     [r14], rax
0x180039c57  xor     eax, eax
0x180039c59  mov     rcx, [rsp+78h+var_20]
0x180039c5e  xor     rcx, rsp; StackCookie
0x180039c61  call    __security_check_cookie
0x180039c66  lea     r11, [rsp+78h+var_18]
0x180039c6b  mov     rbx, [r11+30h]
0x180039c6f  mov     rbp, [r11+38h]
0x180039c73  mov     rsp, r11
0x180039c76  pop     r14
0x180039c78  pop     rdi
0x180039c79  pop     rsi
0x180039c7a  retn
0x180039c7b  add     rsi, 0CD0h
0x180039c82  jmp     short loc_180039C3C
0x180039c84  mov     r9d, eax; char *
0x180039c87  lea     r8, aOnecoreuapWind_28; "onecoreuap\\windows\\advcore\\winrt\\on"...
0x180039c8e  mov     edx, 132Ch; void *
0x180039c93  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x180039c99  mov     r9d, eax; char *
0x180039c9c  lea     r8, aOnecoreuapWind_28; "onecoreuap\\windows\\advcore\\winrt\\on"...
0x180039ca3  mov     edx, 132Eh; void *
0x180039ca8  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x180039cae  xor     r9d, r9d; lpArguments
0x180039cb1  xor     r8d, r8d; nNumberOfArguments
0x180039cb4  lea     edx, [r9+1]; dwExceptionFlags
0x180039cb8  mov     ecx, eax; dwExceptionCode
0x180039cba  call    cs:__imp_RaiseException
```
