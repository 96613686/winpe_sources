# IsAppPropertiesViewAllowed(Windows::Internal::Security::Authentication::TokenBroker::JsonObjectReader &,HSTRING__ *)

- ea: `0x18003ab30`
- end: `0x18003ac92`
- name: `?IsAppPropertiesViewAllowed@@YA_NAEAVJsonObjectReader@TokenBroker@Authentication@Security@Internal@Windows@@PEAUHSTRING__@@@Z`
- size: `354`
- prototype: `bool __fastcall(struct Windows::Internal::Security::Authentication::TokenBroker::JsonObjectReader *this, HSTRING string)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180071a9c`

## callees

- `0x180007350`
- `0x180037024`
- `0x18003a7f0`
- `0x18003ab30`
- `0x18008e690`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18003ac5a`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18003ac5a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18003abca`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18003abca`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18003ab71`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18003ab71`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003ab94`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003ab94`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003ab89`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003ac09`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003ac21`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003ac6e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003ac86`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003ab89`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003ac09`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003ac21`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003ac6e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003ac86`
- `api-ms-win-core-string-l2-1-0!CharLowerW` at `0x18003ab9d`
- `api-ms-win-core-string-l2-1-0!CharLowerW` at `0x18003ab9d`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
bool __fastcall IsAppPropertiesViewAllowed(
        struct Windows::Internal::Security::Authentication::TokenBroker::JsonObjectReader *this,
        HSTRING string)
{
  HSTRING v3; // rbx
  WCHAR *StringRawBuffer; // rax
  bool v6; // [rsp+20h] [rbp-60h] BYREF
  HSTRING newString; // [rsp+28h] [rbp-58h] BYREF
  int v8; // [rsp+30h] [rbp-50h] BYREF
  char v9; // [rsp+34h] [rbp-4Ch]
  HSTRING v10[2]; // [rsp+38h] [rbp-48h] BYREF
  HSTRING v11; // [rsp+48h] [rbp-38h]
  HSTRING stringa; // [rsp+50h] [rbp-30h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+58h] [rbp-28h] BYREF

  if ( !string )
    return 0;
  newString = 0;
  if ( WindowsDuplicateString(string, &newString) < 0 )
    return 0;
  v3 = newString;
  v11 = newString;
  WindowsDeleteString(0);
  StringRawBuffer = (WCHAR *)WindowsGetStringRawBuffer(v3, 0);
  CharLowerW(StringRawBuffer);
  v8 = 5;
  v9 = 0;
  *(_OWORD *)v10 = 0;
  if ( WindowsCreateStringReference(L"HasPropertiesView", 0x11u, &hstringHeader, &stringa) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  if ( Windows::Internal::Security::Authentication::TokenBroker::JsonObjectReader::GetPerAppProperty(
         this,
         v3,
         stringa,
         (struct Windows::Internal::Security::Authentication::TokenBroker::JsonObjectProperty *)&v8) < 0
    || (v6 = 0,
        (int)Windows::Internal::Security::Authentication::TokenBroker::JsonObjectProperty::GetBooleanValue(
               (Windows::Internal::Security::Authentication::TokenBroker::JsonObjectProperty *)&v8,
               &v6) < 0) )
  {
    if ( v10[1] )
      WindowsDeleteString(v10[1]);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v10);
    if ( v3 )
      WindowsDeleteString(v3);
    return 0;
  }
  if ( v10[1] )
    WindowsDeleteString(v10[1]);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v10);
  if ( v3 )
    WindowsDeleteString(v3);
  return v6;
}

```

## disassembly

```asm
0x18003ab30  mov     [rsp-8+arg_10], rbx
0x18003ab35  mov     [rsp-8+arg_18], rdi
0x18003ab3a  push    rbp
0x18003ab3b  mov     rbp, rsp
0x18003ab3e  sub     rsp, 80h
0x18003ab45  mov     rax, cs:__security_cookie
0x18003ab4c  xor     rax, rsp
0x18003ab4f  mov     [rbp+var_10], rax
0x18003ab53  mov     rax, rdx
0x18003ab56  mov     rdi, rcx
0x18003ab59  test    rdx, rdx
0x18003ab5c  jz      loc_18003AC8C
0x18003ab62  mov     [rbp+newString], 0
0x18003ab6a  lea     rdx, [rbp+newString]; newString
0x18003ab6e  mov     rcx, rax; string
0x18003ab71  call    cs:__imp_WindowsDuplicateString
0x18003ab77  test    eax, eax
0x18003ab79  js      loc_18003AC90
0x18003ab7f  mov     rbx, [rbp+newString]
0x18003ab83  mov     [rbp+var_38], rbx
0x18003ab87  xor     ecx, ecx; string
0x18003ab89  call    cs:__imp_WindowsDeleteString
0x18003ab8f  xor     edx, edx; length
0x18003ab91  mov     rcx, rbx; string
0x18003ab94  call    cs:__imp_WindowsGetStringRawBuffer
0x18003ab9a  mov     rcx, rax; lpsz
0x18003ab9d  call    cs:__imp_CharLowerW
0x18003aba3  mov     [rbp+var_50], 5
0x18003abaa  mov     [rbp+var_4C], 0
0x18003abae  xorps   xmm0, xmm0
0x18003abb1  movdqu  xmmword ptr [rbp+var_48], xmm0
0x18003abb6  lea     r9, [rbp+string]; string
0x18003abba  lea     r8, [rbp+hstringHeader]; hstringHeader
0x18003abbe  mov     edx, 11h; length
0x18003abc3  lea     rcx, aHaspropertiesv; "HasPropertiesView"
0x18003abca  call    cs:__imp_WindowsCreateStringReference
0x18003abd0  test    eax, eax
0x18003abd2  js      short loc_18003AC4B
0x18003abd4  lea     r9, [rbp+var_50]; struct Windows::Internal::Security::Authentication::TokenBroker::JsonObjectProperty *
0x18003abd8  mov     r8, [rbp+string]; HSTRING
0x18003abdc  mov     rdx, rbx; HSTRING
0x18003abdf  mov     rcx, rdi; this
0x18003abe2  call    ?GetPerAppProperty@JsonObjectReader@TokenBroker@Authentication@Security@Internal@Windows@@QEAAJPEAUHSTRING__@@0AEAVJsonObjectProperty@23456@@Z; Windows::Internal::Security::Authentication::TokenBroker::JsonObjectReader::GetPerAppProperty(HSTRING__ *,HSTRING__ *,Windows::Internal::Security::Authentication::TokenBroker::JsonObjectProperty &)
0x18003abe7  test    eax, eax
0x18003abe9  js      short loc_18003AC65
0x18003abeb  mov     [rbp+var_60], 0
0x18003abef  lea     rdx, [rbp+var_60]; bool *
0x18003abf3  lea     rcx, [rbp+var_50]; this
0x18003abf7  call    ?GetBooleanValue@JsonObjectProperty@TokenBroker@Authentication@Security@Internal@Windows@@QEBAJAEA_N@Z; Windows::Internal::Security::Authentication::TokenBroker::JsonObjectProperty::GetBooleanValue(bool &)
0x18003abfc  test    eax, eax
0x18003abfe  js      short loc_18003AC65
0x18003ac00  mov     rcx, [rbp+var_48+8]; string
0x18003ac04  test    rcx, rcx
0x18003ac07  jz      short loc_18003AC0F
0x18003ac09  call    cs:__imp_WindowsDeleteString
0x18003ac0f  lea     rcx, [rbp+var_48]
0x18003ac13  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18003ac18  nop
0x18003ac19  test    rbx, rbx
0x18003ac1c  jz      short loc_18003AC27
0x18003ac1e  mov     rcx, rbx; string
0x18003ac21  call    cs:__imp_WindowsDeleteString
0x18003ac27  mov     al, [rbp+var_60]
0x18003ac2a  mov     rcx, [rbp+var_10]
0x18003ac2e  xor     rcx, rsp; StackCookie
0x18003ac31  call    __security_check_cookie
0x18003ac36  lea     r11, [rsp+80h+var_s0]
0x18003ac3e  mov     rbx, [r11+20h]
0x18003ac42  mov     rdi, [r11+28h]
0x18003ac46  mov     rsp, r11
0x18003ac49  pop     rbp
0x18003ac4a  retn
0x18003ac4b  xor     r9d, r9d; lpArguments
0x18003ac4e  xor     r8d, r8d; nNumberOfArguments
0x18003ac51  lea     edx, [r9+1]; dwExceptionFlags
0x18003ac55  mov     ecx, 0C000000Dh; dwExceptionCode
0x18003ac5a  call    cs:__imp_RaiseException
0x18003ac60  jmp     loc_18003ABD4
0x18003ac65  mov     rcx, [rbp+var_48+8]; string
0x18003ac69  test    rcx, rcx
0x18003ac6c  jz      short loc_18003AC74
0x18003ac6e  call    cs:__imp_WindowsDeleteString
0x18003ac74  lea     rcx, [rbp+var_48]
0x18003ac78  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18003ac7d  nop
0x18003ac7e  test    rbx, rbx
0x18003ac81  jz      short loc_18003AC8C
0x18003ac83  mov     rcx, rbx; string
0x18003ac86  call    cs:__imp_WindowsDeleteString
0x18003ac8c  xor     al, al
0x18003ac8e  jmp     short loc_18003AC2A
0x18003ac90  jmp     short loc_18003AC8C
```
