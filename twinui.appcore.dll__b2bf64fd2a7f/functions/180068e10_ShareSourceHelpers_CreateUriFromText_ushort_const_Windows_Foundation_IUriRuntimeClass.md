# ShareSourceHelpers::CreateUriFromText(ushort const *,Windows::Foundation::IUriRuntimeClass * *)

- ea: `0x180068e10`
- end: `0x180068f2c`
- name: `?CreateUriFromText@ShareSourceHelpers@@YAJPEBGPEAPEAUIUriRuntimeClass@Foundation@Windows@@@Z`
- size: `284`
- prototype: `__int64 __fastcall(PCWSTR sourceString, const unsigned __int16 *, struct Windows::Foundation::IUriRuntimeClass **)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180068840`

## callees

- `0x180003d24`
- `0x180016c98`
- `0x18002b1b0`
- `0x180068e10`
- `0x180085010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180068e6d`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180068ed3`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180068e6d`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180068ed3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180068e54`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180068ee7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180068e54`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180068ee7`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180068e8e`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180068e8e`

## string_xrefs

- `0x180068e4d`: `Windows.Foundation.Uri`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ShareSourceHelpers::CreateUriFromText(
        PCWSTR sourceString,
        const unsigned __int16 *a2,
        struct Windows::Foundation::IUriRuntimeClass **a3)
{
  HSTRING v5; // rbx
  int ActivationFactory; // ebx
  __int64 v7; // rbx
  __int64 (__fastcall *v8)(__int64, HSTRING, const unsigned __int16 *); // rsi
  unsigned __int64 v9; // rcx
  UINT32 length; // [rsp+20h] [rbp-40h] BYREF
  __int64 v12; // [rsp+28h] [rbp-38h] BYREF
  HSTRING string; // [rsp+30h] [rbp-30h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+38h] [rbp-28h] BYREF

  *(_QWORD *)a2 = 0;
  v12 = 0;
  if ( WindowsCreateStringReference(L"Windows.Foundation.Uri", 0x16u, &hstringHeader, &string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  v5 = string;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v12);
  ActivationFactory = RoGetActivationFactory(v5, &GUID_44a9796f_723e_4fdf_a218_033e75b0c084, &v12);
  if ( ActivationFactory >= 0 )
  {
    v7 = v12;
    v8 = *(__int64 (__fastcall **)(__int64, HSTRING, const unsigned __int16 *))(*(_QWORD *)v12 + 48LL);
    length = 0;
    v9 = -1;
    do
      ++v9;
    while ( sourceString[v9] );
    if ( (int)ULongLongToUInt(v9, &length) < 0 )
      RaiseException(0xC000000D, 1u, 0, 0);
    WindowsCreateStringReference(sourceString, length, &hstringHeader, &string);
    ActivationFactory = v8(v7, string, a2);
  }
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v12);
  return (unsigned int)ActivationFactory;
}

```

## disassembly

```asm
0x180068e10  mov     [rsp-28h+arg_10], rbx
0x180068e15  push    rbp
0x180068e16  push    rsi
0x180068e17  push    rdi
0x180068e18  push    r14
0x180068e1a  push    r15
0x180068e1c  mov     rbp, rsp
0x180068e1f  sub     rsp, 60h
0x180068e23  mov     rax, cs:__security_cookie
0x180068e2a  xor     rax, rsp
0x180068e2d  mov     [rbp+var_10], rax
0x180068e31  mov     r14, rdx
0x180068e34  mov     rdi, rcx
0x180068e37  xor     r15d, r15d
0x180068e3a  mov     [rdx], r15
0x180068e3d  mov     [rbp+var_38], r15
0x180068e41  lea     r9, [rbp+string]; string
0x180068e45  lea     r8, [rbp+hstringHeader]; hstringHeader
0x180068e49  lea     edx, [r15+16h]; length
0x180068e4d  lea     rcx, ?RuntimeClass_Windows_Foundation_Uri@@3QBGB; "Windows.Foundation.Uri"
0x180068e54  call    cs:__imp_WindowsCreateStringReference
0x180068e5a  test    eax, eax
0x180068e5c  jns     short loc_180068E73
0x180068e5e  xor     r9d, r9d; lpArguments
0x180068e61  xor     r8d, r8d; nNumberOfArguments
0x180068e64  lea     edx, [r15+1]; dwExceptionFlags
0x180068e68  mov     ecx, 0C000000Dh; dwExceptionCode
0x180068e6d  call    cs:__imp_RaiseException
0x180068e73  mov     rbx, [rbp+string]
0x180068e77  lea     rcx, [rbp+var_38]
0x180068e7b  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180068e80  lea     r8, [rbp+var_38]
0x180068e84  lea     rdx, _GUID_44a9796f_723e_4fdf_a218_033e75b0c084
0x180068e8b  mov     rcx, rbx
0x180068e8e  call    cs:__imp_RoGetActivationFactory
0x180068e94  mov     ebx, eax
0x180068e96  test    eax, eax
0x180068e98  js      short loc_180068F01
0x180068e9a  mov     rbx, [rbp+var_38]
0x180068e9e  mov     rax, [rbx]
0x180068ea1  mov     rsi, [rax+30h]
0x180068ea5  mov     [rbp+length], r15d
0x180068ea9  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180068ead  inc     rcx; unsigned __int64
0x180068eb0  cmp     [rdi+rcx*2], r15w
0x180068eb5  jnz     short loc_180068EAD
0x180068eb7  lea     rdx, [rbp+length]; unsigned int *
0x180068ebb  call    ?ULongLongToUInt@@YAJ_KPEAI@Z; ULongLongToUInt(unsigned __int64,uint *)
0x180068ec0  test    eax, eax
0x180068ec2  jns     short loc_180068ED9
0x180068ec4  xor     r9d, r9d; lpArguments
0x180068ec7  xor     r8d, r8d; nNumberOfArguments
0x180068eca  lea     edx, [r9+1]; dwExceptionFlags
0x180068ece  mov     ecx, 0C000000Dh; dwExceptionCode
0x180068ed3  call    cs:__imp_RaiseException
0x180068ed9  lea     r9, [rbp+string]; string
0x180068edd  lea     r8, [rbp+hstringHeader]; hstringHeader
0x180068ee1  mov     edx, [rbp+length]; length
0x180068ee4  mov     rcx, rdi; sourceString
0x180068ee7  call    cs:__imp_WindowsCreateStringReference
0x180068eed  mov     r8, r14
0x180068ef0  mov     rdx, [rbp+string]
0x180068ef4  mov     rcx, rbx
0x180068ef7  mov     rax, rsi
0x180068efa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180068eff  mov     ebx, eax
0x180068f01  lea     rcx, [rbp+var_38]
0x180068f05  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180068f0a  mov     eax, ebx
0x180068f0c  mov     rcx, [rbp+var_10]
0x180068f10  xor     rcx, rsp; StackCookie
0x180068f13  call    __security_check_cookie
0x180068f18  mov     rbx, [rsp+60h+arg_10]
0x180068f20  add     rsp, 60h
0x180068f24  pop     r15
0x180068f26  pop     r14
0x180068f28  pop     rdi
0x180068f29  pop     rsi
0x180068f2a  pop     rbp
0x180068f2b  retn
```
