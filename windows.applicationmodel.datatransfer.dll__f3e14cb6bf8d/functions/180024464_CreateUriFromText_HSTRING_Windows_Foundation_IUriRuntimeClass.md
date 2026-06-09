# CreateUriFromText(HSTRING__ *,Windows::Foundation::IUriRuntimeClass * *)

- ea: `0x180024464`
- end: `0x180024590`
- name: `?CreateUriFromText@@YAJPEAUHSTRING__@@PEAPEAUIUriRuntimeClass@Foundation@Windows@@@Z`
- size: `300`
- prototype: `__int64 __fastcall(HSTRING, struct Windows::Foundation::IUriRuntimeClass **)`
- caller_count: `5`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000cad0`
- `0x18000cc00`
- `0x180038a10`
- `0x180049410`
- `0x180053cb0`

## callees

- `0x180002ad0`
- `0x180024464`
- `0x180081010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800244aa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800244aa`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x18002454d`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x18002454d`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18002453b`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18002453b`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800244c3`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800244c3`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800244f9`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800244f9`

## string_xrefs

- `0x1800244a3`: `Windows.Foundation.Uri`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CreateUriFromText(HSTRING a1, struct Windows::Foundation::IUriRuntimeClass **a2)
{
  int ActivationFactory; // ebx
  unsigned int StringW; // eax
  __int64 v6; // rcx
  __int64 v8; // [rsp+20h] [rbp-40h] BYREF
  WCHAR Buffer[4]; // [rsp+28h] [rbp-38h] BYREF
  HSTRING string; // [rsp+30h] [rbp-30h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+38h] [rbp-28h] BYREF

  *a2 = 0;
  v8 = 0;
  if ( WindowsCreateStringReference(L"Windows.Foundation.Uri", 0x16u, &hstringHeader, &string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  ActivationFactory = RoGetActivationFactory(string, &GUID_44a9796f_723e_4fdf_a218_033e75b0c084, &v8);
  if ( ActivationFactory >= 0 )
  {
    ActivationFactory = (*(__int64 (__fastcall **)(__int64, HSTRING, struct Windows::Foundation::IUriRuntimeClass **))(*(_QWORD *)v8 + 48LL))(
                          v8,
                          a1,
                          a2);
    if ( ActivationFactory < 0 )
    {
      *(_QWORD *)Buffer = 0;
      StringW = LoadStringW(&_ImageBase, 8u, Buffer, 0);
      if ( StringW )
        RoOriginateErrorW((unsigned int)ActivationFactory, StringW, *(_QWORD *)Buffer);
    }
  }
  v6 = v8;
  if ( v8 )
  {
    v8 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
  }
  return (unsigned int)ActivationFactory;
}

```

## disassembly

```asm
0x180024464  mov     [rsp-18h+arg_10], rbx
0x180024469  push    rbp
0x18002446a  push    rsi
0x18002446b  push    rdi
0x18002446c  mov     rbp, rsp
0x18002446f  sub     rsp, 60h
0x180024473  mov     rax, cs:__security_cookie
0x18002447a  xor     rax, rsp
0x18002447d  mov     [rbp+var_10], rax
0x180024481  mov     rdi, rdx
0x180024484  mov     rsi, rcx
0x180024487  mov     qword ptr [rdx], 0
0x18002448e  mov     [rbp+var_40], 0
0x180024496  lea     r9, [rbp+string]; string
0x18002449a  lea     r8, [rbp+hstringHeader]; hstringHeader
0x18002449e  mov     edx, 16h; length
0x1800244a3  lea     rcx, ?RuntimeClass_Windows_Foundation_Uri@@3QBGB; "Windows.Foundation.Uri"
0x1800244aa  call    cs:__imp_WindowsCreateStringReference
0x1800244b0  test    eax, eax
0x1800244b2  jns     short loc_1800244C9
0x1800244b4  xor     r9d, r9d; lpArguments
0x1800244b7  xor     r8d, r8d; nNumberOfArguments
0x1800244ba  lea     edx, [r9+1]; dwExceptionFlags
0x1800244be  mov     ecx, 0C000000Dh; dwExceptionCode
0x1800244c3  call    cs:__imp_RaiseException
0x1800244c9  mov     rbx, [rbp+string]
0x1800244cd  mov     rcx, [rbp+var_40]
0x1800244d1  test    rcx, rcx
0x1800244d4  jz      short loc_1800244EB
0x1800244d6  mov     [rbp+var_40], 0
0x1800244de  mov     rax, [rcx]
0x1800244e1  mov     rax, [rax+10h]
0x1800244e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800244ea  nop
0x1800244eb  lea     r8, [rbp+var_40]
0x1800244ef  lea     rdx, _GUID_44a9796f_723e_4fdf_a218_033e75b0c084
0x1800244f6  mov     rcx, rbx
0x1800244f9  call    cs:__imp_RoGetActivationFactory
0x1800244ff  mov     ebx, eax
0x180024501  test    eax, eax
0x180024503  js      short loc_180024554
0x180024505  mov     rcx, [rbp+var_40]
0x180024509  mov     rax, [rcx]
0x18002450c  mov     r8, rdi
0x18002450f  mov     rdx, rsi
0x180024512  mov     rax, [rax+30h]
0x180024516  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002451b  mov     ebx, eax
0x18002451d  test    eax, eax
0x18002451f  jns     short loc_180024554
0x180024521  mov     qword ptr [rbp+Buffer], 0
0x180024529  xor     r9d, r9d; cchBufferMax
0x18002452c  lea     r8, [rbp+Buffer]; lpBuffer
0x180024530  lea     edx, [r9+8]; uID
0x180024534  lea     rcx, __ImageBase; hInstance
0x18002453b  call    cs:__imp_LoadStringW
0x180024541  test    eax, eax
0x180024543  jz      short loc_180024554
0x180024545  mov     r8, qword ptr [rbp+Buffer]
0x180024549  mov     edx, eax
0x18002454b  mov     ecx, ebx
0x18002454d  call    cs:__imp_RoOriginateErrorW
0x180024553  nop
0x180024554  mov     rcx, [rbp+var_40]
0x180024558  test    rcx, rcx
0x18002455b  jz      short loc_180024572
0x18002455d  mov     [rbp+var_40], 0
0x180024565  mov     rax, [rcx]
0x180024568  mov     rax, [rax+10h]
0x18002456c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024571  nop
0x180024572  mov     eax, ebx
0x180024574  mov     rcx, [rbp+var_10]
0x180024578  xor     rcx, rsp; StackCookie
0x18002457b  call    __security_check_cookie
0x180024580  mov     rbx, [rsp+60h+arg_10]
0x180024588  add     rsp, 60h
0x18002458c  pop     rdi
0x18002458d  pop     rsi
0x18002458e  pop     rbp
0x18002458f  retn
```
