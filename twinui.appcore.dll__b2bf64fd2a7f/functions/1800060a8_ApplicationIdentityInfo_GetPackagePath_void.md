# ApplicationIdentityInfo::GetPackagePath(void)

- ea: `0x1800060a8`
- end: `0x18000631a`
- name: `?GetPackagePath@ApplicationIdentityInfo@@QEBA?AVHString@Wrappers@WRL@Microsoft@@XZ`
- size: `626`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180007ce0`

## callees

- `0x180003d24`
- `0x1800060a8`
- `0x18001e1c4`
- `0x18002b1b0`
- `0x18002b5b0`
- `0x180033d5c`
- `0x180085010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180006118`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800061f2`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180006118`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800061f2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180006251`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180006251`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180006101`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800061dc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180006101`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800061dc`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180006189`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180006189`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18000613a`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180006214`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18000613a`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180006214`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
_QWORD *__fastcall ApplicationIdentityInfo::GetPackagePath(__int64 a1, _QWORD *a2)
{
  HRESULT v4; // eax
  HSTRING v5; // rbx
  int ActivationFactory; // eax
  __int64 v7; // rsi
  __int64 (__fastcall *v8)(__int64, _QWORD, __int64, __int64 *); // rdi
  __int64 v9; // rbx
  DWORD LengthSid; // eax
  int v11; // eax
  HRESULT v12; // eax
  HSTRING v13; // rbx
  int v14; // eax
  __int64 v15; // rdi
  __int64 (__fastcall *v16)(__int64, __int64, _QWORD, _QWORD *); // rbx
  int v17; // eax
  __int64 v18; // rcx
  __int64 v19; // rcx
  void *v20; // rcx
  __int64 v21; // rcx
  int v23; // [rsp+20h] [rbp-39h]
  __int64 v24; // [rsp+38h] [rbp-21h] BYREF
  __int64 v25; // [rsp+40h] [rbp-19h] BYREF
  __int64 v26; // [rsp+48h] [rbp-11h] BYREF
  void *Block[2]; // [rsp+50h] [rbp-9h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+60h] [rbp+7h] BYREF
  HSTRING string; // [rsp+78h] [rbp+1Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+5Fh]

  Block[1] = a2;
  v25 = 0;
  string = 0;
  v4 = WindowsCreateStringReference(L"Windows.Internal.StateRepository.User", 0x25u, &hstringHeader, &string);
  if ( v4 < 0 )
    RaiseException(v4, 1u, 0, 0);
  v5 = string;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v25);
  ActivationFactory = RoGetActivationFactory(v5, &GUID_84103ccb_2fd7_4d6c_962e_5d8582b4c720, &v25);
  if ( ActivationFactory < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x9C,
      (unsigned int)"onecoreuap\\shell\\twinui\\centennial\\lib\\centennialactivation.cpp",
      (const char *)(unsigned int)ActivationFactory,
      v23);
  wil::details::GetTokenInfoWrap<_TOKEN_USER,wil::err_exception_policy,0>(Block);
  v26 = 0;
  v7 = v25;
  v8 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64, __int64 *))(*(_QWORD *)v25 + 144LL);
  v9 = *(_QWORD *)Block[0];
  LengthSid = GetLengthSid(*(PSID *)Block[0]);
  v11 = v8(v7, LengthSid, v9, &v26);
  if ( v11 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xA1,
      (unsigned int)"onecoreuap\\shell\\twinui\\centennial\\lib\\centennialactivation.cpp",
      (const char *)(unsigned int)v11,
      v23);
  v24 = 0;
  string = 0;
  v12 = WindowsCreateStringReference(L"Windows.Internal.StateRepository.Package", 0x28u, &hstringHeader, &string);
  if ( v12 < 0 )
    RaiseException(v12, 1u, 0, 0);
  v13 = string;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v24);
  v14 = RoGetActivationFactory(v13, &GUID_0450ce77_af0d_40ac_93fd_1e5d48c89419, &v24);
  if ( v14 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xA4,
      (unsigned int)"onecoreuap\\shell\\twinui\\centennial\\lib\\centennialactivation.cpp",
      (const char *)(unsigned int)v14,
      v23);
  *a2 = 0;
  v15 = v24;
  v16 = *(__int64 (__fastcall **)(__int64, __int64, _QWORD, _QWORD *))(*(_QWORD *)v24 + 608LL);
  WindowsDeleteString(0);
  *a2 = 0;
  v17 = v16(v15, v26, *(_QWORD *)(a1 + 104), a2);
  if ( v17 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xA7,
      (unsigned int)"onecoreuap\\shell\\twinui\\centennial\\lib\\centennialactivation.cpp",
      (const char *)(unsigned int)v17,
      v23);
  v18 = v24;
  if ( v24 )
  {
    v24 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
  }
  v19 = v26;
  if ( v26 )
  {
    v26 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
  }
  v20 = Block[0];
  Block[0] = 0;
  if ( v20 )
    operator delete(v20);
  v21 = v25;
  if ( v25 )
  {
    v25 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
  }
  return a2;
}

```

## disassembly

```asm
0x1800060a8  mov     [rsp-8+arg_10], rbx
0x1800060ad  mov     [rsp-8+arg_18], rsi
0x1800060b2  push    rbp
0x1800060b3  push    rdi
0x1800060b4  push    r12
0x1800060b6  push    r14
0x1800060b8  push    r15
0x1800060ba  lea     rbp, [rsp-37h]
0x1800060bf  sub     rsp, 90h
0x1800060c6  mov     rax, cs:__security_cookie
0x1800060cd  xor     rax, rsp
0x1800060d0  mov     [rbp+57h+var_30], rax
0x1800060d4  mov     r14, rdx
0x1800060d7  mov     r15, rcx
0x1800060da  mov     [rbp+57h+var_58], rdx
0x1800060de  xor     r12d, r12d
0x1800060e1  mov     [rbp+57h+var_80], r12d
0x1800060e5  mov     [rbp+57h+var_70], r12
0x1800060e9  mov     [rbp+57h+string], r12
0x1800060ed  lea     r9, [rbp+57h+string]; string
0x1800060f1  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x1800060f5  lea     edx, [r12+25h]; length
0x1800060fa  lea     rcx, ?RuntimeClass_Windows_Internal_StateRepository_User@@3QBGB; "Windows.Internal.StateRepository.User"
0x180006101  call    cs:__imp_WindowsCreateStringReference
0x180006107  test    eax, eax
0x180006109  jns     short loc_18000611F
0x18000610b  xor     r9d, r9d; lpArguments
0x18000610e  xor     r8d, r8d; nNumberOfArguments
0x180006111  lea     edx, [r12+1]; dwExceptionFlags
0x180006116  mov     ecx, eax; dwExceptionCode
0x180006118  call    cs:__imp_RaiseException
0x18000611e  nop
0x18000611f  mov     rbx, [rbp+57h+string]
0x180006123  lea     rcx, [rbp+57h+var_70]
0x180006127  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18000612c  lea     r8, [rbp+57h+var_70]
0x180006130  lea     rdx, _GUID_84103ccb_2fd7_4d6c_962e_5d8582b4c720
0x180006137  mov     rcx, rbx
0x18000613a  call    cs:__imp_RoGetActivationFactory
0x180006140  mov     rcx, [rbp+5Fh]; this
0x180006144  test    eax, eax
0x180006146  jns     short loc_18000615D
0x180006148  mov     r9d, eax; char *
0x18000614b  lea     r8, aOnecoreuapShel_13; "onecoreuap\\shell\\twinui\\centennial\\"...
0x180006152  mov     edx, 9Ch; void *
0x180006157  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18000615d  lea     rcx, [rbp+57h+Block]
0x180006161  call    ??$GetTokenInfoWrap@U_TOKEN_USER@@Uerr_exception_policy@wil@@$0A@@details@wil@@YA?AV?$unique_ptr@U_TOKEN_USER@@Utoken_info_deleter@details@wil@@@wistd@@PEAX@Z; wil::details::GetTokenInfoWrap<_TOKEN_USER,wil::err_exception_policy,0>(void *)
0x180006166  mov     [rbp+57h+var_80], 2
0x18000616d  mov     [rbp+57h+var_68], r12
0x180006171  mov     rsi, [rbp+57h+var_70]
0x180006175  mov     rax, [rsi]
0x180006178  mov     rdi, [rax+90h]
0x18000617f  mov     rax, [rbp+57h+Block]
0x180006183  mov     rbx, [rax]
0x180006186  mov     rcx, rbx; pSid
0x180006189  call    cs:__imp_GetLengthSid
0x18000618f  lea     r9, [rbp+57h+var_68]
0x180006193  mov     r8, rbx
0x180006196  mov     edx, eax
0x180006198  mov     rcx, rsi
0x18000619b  mov     rax, rdi
0x18000619e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800061a3  mov     rcx, [rbp+5Fh]; this
0x1800061a7  test    eax, eax
0x1800061a9  jns     short loc_1800061C0
0x1800061ab  mov     r9d, eax; char *
0x1800061ae  lea     r8, aOnecoreuapShel_13; "onecoreuap\\shell\\twinui\\centennial\\"...
0x1800061b5  mov     edx, 0A1h; void *
0x1800061ba  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800061c0  mov     [rbp+57h+var_78], r12
0x1800061c4  mov     [rbp+57h+string], r12
0x1800061c8  lea     r9, [rbp+57h+string]; string
0x1800061cc  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x1800061d0  mov     edx, 28h ; '('; length
0x1800061d5  lea     rcx, ?RuntimeClass_Windows_Internal_StateRepository_Package@@3QBGB; "Windows.Internal.StateRepository.Packag"...
0x1800061dc  call    cs:__imp_WindowsCreateStringReference
0x1800061e2  test    eax, eax
0x1800061e4  jns     short loc_1800061F9
0x1800061e6  xor     r9d, r9d; lpArguments
0x1800061e9  xor     r8d, r8d; nNumberOfArguments
0x1800061ec  lea     edx, [r9+1]; dwExceptionFlags
0x1800061f0  mov     ecx, eax; dwExceptionCode
0x1800061f2  call    cs:__imp_RaiseException
0x1800061f8  nop
0x1800061f9  mov     rbx, [rbp+57h+string]
0x1800061fd  lea     rcx, [rbp+57h+var_78]
0x180006201  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180006206  lea     r8, [rbp+57h+var_78]
0x18000620a  lea     rdx, _GUID_0450ce77_af0d_40ac_93fd_1e5d48c89419
0x180006211  mov     rcx, rbx
0x180006214  call    cs:__imp_RoGetActivationFactory
0x18000621a  mov     rcx, [rbp+5Fh]; this
0x18000621e  test    eax, eax
0x180006220  jns     short loc_180006237
0x180006222  mov     r9d, eax; char *
0x180006225  lea     r8, aOnecoreuapShel_13; "onecoreuap\\shell\\twinui\\centennial\\"...
0x18000622c  mov     edx, 0A4h; void *
0x180006231  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180006237  mov     [r14], r12
0x18000623a  mov     [rbp+57h+var_80], 3
0x180006241  mov     rdi, [rbp+57h+var_78]
0x180006245  mov     rax, [rdi]
0x180006248  mov     rbx, [rax+260h]
0x18000624f  xor     ecx, ecx; string
0x180006251  call    cs:__imp_WindowsDeleteString
0x180006257  mov     [r14], r12
0x18000625a  mov     r9, r14
0x18000625d  mov     r8, [r15+68h]
0x180006261  mov     rdx, [rbp+57h+var_68]
0x180006265  mov     rcx, rdi
0x180006268  mov     rax, rbx
0x18000626b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006270  mov     rcx, [rbp+5Fh]; this
0x180006274  test    eax, eax
0x180006276  jns     short loc_18000628D
0x180006278  mov     r9d, eax; char *
0x18000627b  lea     r8, aOnecoreuapShel_13; "onecoreuap\\shell\\twinui\\centennial\\"...
0x180006282  mov     edx, 0A7h; void *
0x180006287  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18000628d  mov     rcx, [rbp+57h+var_78]
0x180006291  test    rcx, rcx
0x180006294  jz      short loc_1800062A7
0x180006296  mov     [rbp+57h+var_78], r12
0x18000629a  mov     rax, [rcx]
0x18000629d  mov     rax, [rax+10h]
0x1800062a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800062a6  nop
0x1800062a7  mov     rcx, [rbp+57h+var_68]
0x1800062ab  test    rcx, rcx
0x1800062ae  jz      short loc_1800062C1
0x1800062b0  mov     [rbp+57h+var_68], r12
0x1800062b4  mov     rax, [rcx]
0x1800062b7  mov     rax, [rax+10h]
0x1800062bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800062c0  nop
0x1800062c1  mov     rcx, [rbp+57h+Block]; Block
0x1800062c5  mov     [rbp+57h+Block], r12
0x1800062c9  test    rcx, rcx
0x1800062cc  jz      short loc_1800062D4
0x1800062ce  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800062d3  nop
0x1800062d4  mov     rcx, [rbp+57h+var_70]
0x1800062d8  test    rcx, rcx
0x1800062db  jz      short loc_1800062EE
0x1800062dd  mov     [rbp+57h+var_70], r12
0x1800062e1  mov     rdx, [rcx]
0x1800062e4  mov     rax, [rdx+10h]
0x1800062e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800062ed  nop
0x1800062ee  mov     rax, r14
0x1800062f1  mov     rcx, [rbp+57h+var_30]
0x1800062f5  xor     rcx, rsp; StackCookie
0x1800062f8  call    __security_check_cookie
0x1800062fd  lea     r11, [rsp+0B0h+var_20]
0x180006305  mov     rbx, [r11+40h]
0x180006309  mov     rsi, [r11+48h]
0x18000630d  mov     rsp, r11
0x180006310  pop     r15
0x180006312  pop     r14
0x180006314  pop     r12
0x180006316  pop     rdi
0x180006317  pop     rbp
0x180006318  retn
```
