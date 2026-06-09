# NotificationParser::SavePushDownAttributes(Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *> *)

- ea: `0x1800119b0`
- end: `0x180011b8d`
- name: `?SavePushDownAttributes@NotificationParser@@AEAAXPEAU?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@@Z`
- size: `477`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180018d90`

## callees

- `0x180005670`
- `0x1800119b0`
- `0x18001b848`
- `0x18001ff00`
- `0x180032010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180011b4b`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180011b66`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180011b81`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180011b4b`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180011b66`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180011b81`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800119fd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180011a45`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180011a8c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800119fd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180011a45`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180011a8c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180011b04`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180011b04`

## string_xrefs

- `0x180011a85`: `baseUri`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall NotificationParser::SavePushDownAttributes(__int64 a1, __int64 a2)
{
  void (__fastcall *v4)(__int64, HSTRING, __int64); // rsi
  void (__fastcall *v5)(__int64, HSTRING, __int64); // rsi
  __int64 (__fastcall *v6)(__int64, HSTRING, int *); // rdi
  __int64 result; // rax
  __int64 v8; // rcx
  __int64 v9; // rsi
  __int64 (__fastcall *v10)(__int64, __int64); // rdi
  int v11[2]; // [rsp+20h] [rbp-48h] BYREF
  HSTRING string; // [rsp+28h] [rbp-40h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+30h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  v4 = *(void (__fastcall **)(__int64, HSTRING, __int64))(*(_QWORD *)a2 + 48LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(a1 + 8);
  if ( WindowsCreateStringReference(L"lang", 4u, &hstringHeader, &string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  v4(a2, string, a1 + 8);
  v5 = *(void (__fastcall **)(__int64, HSTRING, __int64))(*(_QWORD *)a2 + 48LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(a1 + 16);
  if ( WindowsCreateStringReference(L"addImageQuery", 0xDu, &hstringHeader, &string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  v5(a2, string, a1 + 16);
  *(_QWORD *)v11 = 0;
  v6 = *(__int64 (__fastcall **)(__int64, HSTRING, int *))(*(_QWORD *)a2 + 48LL);
  if ( WindowsCreateStringReference(L"baseUri", 7u, &hstringHeader, &string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  result = v6(a2, string, v11);
  if ( (int)result >= 0 )
  {
    v9 = *(_QWORD *)v11;
    v10 = *(__int64 (__fastcall **)(__int64, __int64))(**(_QWORD **)v11 + 152LL);
    WindowsDeleteString(*(HSTRING *)(a1 + 24));
    *(_QWORD *)(a1 + 24) = 0;
    result = v10(v9, a1 + 24);
    if ( (int)result < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x39C,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\notificationparser\\src\\notificationparser.cpp",
        (const char *)(unsigned int)result,
        v11[0]);
  }
  v8 = *(_QWORD *)v11;
  if ( *(_QWORD *)v11 )
  {
    *(_QWORD *)v11 = 0;
    return (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
  }
  return result;
}

```

## disassembly

```asm
0x1800119b0  mov     [rsp+arg_10], rbx
0x1800119b5  mov     [rsp+arg_18], rbp
0x1800119ba  push    rsi
0x1800119bb  push    rdi
0x1800119bc  push    r14
0x1800119be  sub     rsp, 50h
0x1800119c2  mov     rax, cs:__security_cookie
0x1800119c9  xor     rax, rsp
0x1800119cc  mov     [rsp+68h+var_20], rax
0x1800119d1  mov     rbx, rdx
0x1800119d4  mov     rbp, rcx
0x1800119d7  mov     rax, [rdx]
0x1800119da  mov     rsi, [rax+30h]
0x1800119de  add     rcx, 8
0x1800119e2  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800119e7  lea     r9, [rsp+68h+string]; string
0x1800119ec  lea     r8, [rsp+68h+hstringHeader]; hstringHeader
0x1800119f1  mov     edx, 4; length
0x1800119f6  lea     rcx, aLang; "lang"
0x1800119fd  call    cs:__imp_WindowsCreateStringReference
0x180011a03  test    eax, eax
0x180011a05  js      loc_180011B3B
0x180011a0b  lea     r8, [rbp+8]
0x180011a0f  mov     rdx, [rsp+68h+string]
0x180011a14  mov     rcx, rbx
0x180011a17  mov     rax, rsi
0x180011a1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011a1f  mov     rax, [rbx]
0x180011a22  mov     rsi, [rax+30h]
0x180011a26  lea     rcx, [rbp+10h]
0x180011a2a  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180011a2f  lea     r9, [rsp+68h+string]; string
0x180011a34  lea     r8, [rsp+68h+hstringHeader]; hstringHeader
0x180011a39  mov     edx, 0Dh; length
0x180011a3e  lea     rcx, aAddimagequery; "addImageQuery"
0x180011a45  call    cs:__imp_WindowsCreateStringReference
0x180011a4b  test    eax, eax
0x180011a4d  js      loc_180011B56
0x180011a53  lea     r8, [rbp+10h]
0x180011a57  mov     rdx, [rsp+68h+string]
0x180011a5c  mov     rcx, rbx
0x180011a5f  mov     rax, rsi
0x180011a62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011a67  xor     r14d, r14d
0x180011a6a  mov     qword ptr [rsp+68h+var_48], r14; int
0x180011a6f  mov     rax, [rbx]
0x180011a72  mov     rdi, [rax+30h]
0x180011a76  lea     r9, [rsp+68h+string]; string
0x180011a7b  lea     r8, [rsp+68h+hstringHeader]; hstringHeader
0x180011a80  mov     edx, 7; length
0x180011a85  lea     rcx, aBaseuri; "baseUri"
0x180011a8c  call    cs:__imp_WindowsCreateStringReference
0x180011a92  test    eax, eax
0x180011a94  js      loc_180011B71
0x180011a9a  lea     r8, [rsp+68h+var_48]
0x180011a9f  mov     rdx, [rsp+68h+string]
0x180011aa4  mov     rcx, rbx
0x180011aa7  mov     rax, rdi
0x180011aaa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011aaf  test    eax, eax
0x180011ab1  jns     short loc_180011AF1
0x180011ab3  mov     rcx, qword ptr [rsp+68h+var_48]
0x180011ab8  test    rcx, rcx
0x180011abb  jz      short loc_180011ACF
0x180011abd  mov     qword ptr [rsp+68h+var_48], r14
0x180011ac2  mov     rax, [rcx]
0x180011ac5  mov     rax, [rax+10h]
0x180011ac9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011ace  nop
0x180011acf  mov     rcx, [rsp+68h+var_20]
0x180011ad4  xor     rcx, rsp; StackCookie
0x180011ad7  call    __security_check_cookie
0x180011adc  lea     r11, [rsp+68h+var_18]
0x180011ae1  mov     rbx, [r11+30h]
0x180011ae5  mov     rbp, [r11+38h]
0x180011ae9  mov     rsp, r11
0x180011aec  pop     r14
0x180011aee  pop     rdi
0x180011aef  pop     rsi
0x180011af0  retn
0x180011af1  mov     rsi, qword ptr [rsp+68h+var_48]
0x180011af6  mov     rax, [rsi]
0x180011af9  mov     rdi, [rax+98h]
0x180011b00  mov     rcx, [rbp+18h]; string
0x180011b04  call    cs:__imp_WindowsDeleteString
0x180011b0a  mov     [rbp+18h], r14
0x180011b0e  lea     rdx, [rbp+18h]
0x180011b12  mov     rcx, rsi
0x180011b15  mov     rax, rdi
0x180011b18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011b1d  mov     rcx, [rsp+68h]; this
0x180011b22  test    eax, eax
0x180011b24  jns     short loc_180011AB3
0x180011b26  mov     r9d, eax; char *
0x180011b29  lea     r8, aOnecoreuapBase_15; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180011b30  mov     edx, 39Ch; void *
0x180011b35  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180011b3b  xor     r9d, r9d; lpArguments
0x180011b3e  xor     r8d, r8d; nNumberOfArguments
0x180011b41  mov     edx, 1; dwExceptionFlags
0x180011b46  mov     ecx, 0C000000Dh; dwExceptionCode
0x180011b4b  call    cs:__imp_RaiseException
0x180011b51  jmp     loc_180011A0B
0x180011b56  xor     r9d, r9d; lpArguments
0x180011b59  xor     r8d, r8d; nNumberOfArguments
0x180011b5c  mov     edx, 1; dwExceptionFlags
0x180011b61  mov     ecx, 0C000000Dh; dwExceptionCode
0x180011b66  call    cs:__imp_RaiseException
0x180011b6c  jmp     loc_180011A53
0x180011b71  xor     r9d, r9d; lpArguments
0x180011b74  xor     r8d, r8d; nNumberOfArguments
0x180011b77  mov     edx, 1; dwExceptionFlags
0x180011b7c  mov     ecx, 0C000000Dh; dwExceptionCode
0x180011b81  call    cs:__imp_RaiseException
0x180011b87  jmp     loc_180011A9A
```
