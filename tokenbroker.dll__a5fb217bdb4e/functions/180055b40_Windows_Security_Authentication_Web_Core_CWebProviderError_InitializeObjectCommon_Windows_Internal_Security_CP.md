# Windows::Security::Authentication::Web::Core::CWebProviderError::InitializeObjectCommon(Windows::Internal::Security::CPropertiesSerializer &)

- ea: `0x180055b40`
- end: `0x180055df3`
- name: `?InitializeObjectCommon@CWebProviderError@Core@Web@Authentication@Security@Windows@@AEAAJAEAVCPropertiesSerializer@5Internal@6@@Z`
- size: `691`
- prototype: `int(Windows::Security::Authentication::Web::Core::CWebProviderError *__hidden this, struct Windows::Internal::Security::CPropertiesSerializer *)`
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x180055aa0`

## callees

- `0x180007350`
- `0x18000bd40`
- `0x180016f44`
- `0x1800175c0`
- `0x180018224`
- `0x180018674`
- `0x180018720`
- `0x180025c60`
- `0x180055b40`
- `0x18008e690`
- `0x18011b010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180055b98`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180055c86`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180055d19`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180055b98`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180055c86`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180055d19`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180055b80`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180055c6d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180055d00`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180055b80`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180055c6d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180055d00`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180055cd0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180055d91`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180055cd0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180055d91`

## string_xrefs

- `0x180055c3b`: `onecore\ds\security\tokenbroker\api\lib\webtoken.cpp`
- `0x180055cb1`: `onecore\ds\security\tokenbroker\api\lib\webtoken.cpp`
- `0x180055d42`: `onecore\ds\security\tokenbroker\api\lib\webtoken.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Windows::Security::Authentication::Web::Core::CWebProviderError::InitializeObjectCommon(
        Windows::Security::Authentication::Web::Core::CWebProviderError *this,
        struct Windows::Internal::Security::CPropertiesSerializer *a2)
{
  int v4; // esi
  __int64 *v5; // rcx
  __int64 v6; // rax
  int EmptyPropertyBag; // ebx
  __int64 v8; // r8
  int StringProperty; // eax
  int HStringPropertyBagProperty; // eax
  __int64 v11; // rdx
  __int64 v12; // rcx
  HSTRING v14; // [rsp+20h] [rbp-60h] BYREF
  __int64 v15; // [rsp+28h] [rbp-58h] BYREF
  _QWORD *v16; // [rsp+30h] [rbp-50h] BYREF
  __int64 v17; // [rsp+38h] [rbp-48h] BYREF
  _QWORD *v18; // [rsp+40h] [rbp-40h] BYREF
  int v19; // [rsp+48h] [rbp-38h]
  HSTRING string; // [rsp+50h] [rbp-30h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+58h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+18h]

  v4 = 0;
  if ( WindowsCreateStringReference(L"WTE_Code", 8u, &hstringHeader, &string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  LODWORD(v14) = 0;
  v18 = 0;
  v19 = 0;
  if ( string )
  {
    v5 = (__int64 *)*((_QWORD *)a2 + 1);
    v6 = *v5;
    v16 = &v18;
    v17 = 0;
    EmptyPropertyBag = (*(__int64 (__fastcall **)(__int64 *, HSTRING, __int64 *))(v6 + 48))(v5, string, &v17);
    RoVariant::OutRef::~OutRef((RoVariant::OutRef *)&v16);
    if ( EmptyPropertyBag >= 0 )
    {
      v16 = v18;
      LODWORD(v17) = v19;
      LODWORD(v14) = 0;
      EmptyPropertyBag = RoVariant::Accessor::VerifyPV((RoVariant::Accessor *)&v16);
      if ( EmptyPropertyBag >= 0 )
      {
        EmptyPropertyBag = (*(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v8 + 88LL))(v8, &v14);
        if ( EmptyPropertyBag >= 0 )
          v4 = (int)v14;
      }
    }
  }
  else
  {
    EmptyPropertyBag = -2147024809;
  }
  RoVariant::~RoVariant((RoVariant *)&v18);
  if ( EmptyPropertyBag < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x131,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\api\\lib\\webtoken.cpp",
      (const char *)(unsigned int)EmptyPropertyBag,
      (int)v14);
    return (unsigned int)EmptyPropertyBag;
  }
  v14 = 0;
  if ( WindowsCreateStringReference(L"WTE_Message", 0xBu, &hstringHeader, &string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  StringProperty = Windows::Internal::Security::CPropertiesSerializer::GetStringProperty(a2, string, &v14);
  EmptyPropertyBag = 0;
  if ( StringProperty != -2147483637 )
    EmptyPropertyBag = StringProperty;
  if ( EmptyPropertyBag < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x136,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\api\\lib\\webtoken.cpp",
      (const char *)(unsigned int)EmptyPropertyBag,
      (int)v14);
    goto LABEL_18;
  }
  v15 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v15);
  if ( WindowsCreateStringReference(L"WTE_PropertyBag", 0xFu, &hstringHeader, &string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  HStringPropertyBagProperty = Windows::Internal::Security::CPropertiesSerializer::GetHStringPropertyBagProperty(
                                 a2,
                                 string,
                                 &v15);
  EmptyPropertyBag = 0;
  if ( HStringPropertyBagProperty != -2147483637 )
    EmptyPropertyBag = HStringPropertyBagProperty;
  if ( EmptyPropertyBag < 0 )
  {
    v11 = 315;
LABEL_26:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v11,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\api\\lib\\webtoken.cpp",
      (const char *)(unsigned int)EmptyPropertyBag,
      (int)v14);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v15);
LABEL_18:
    if ( v14 )
      WindowsDeleteString(v14);
    return (unsigned int)EmptyPropertyBag;
  }
  if ( !v15 )
  {
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v15);
    EmptyPropertyBag = MakeEmptyPropertyBag(&v15);
    if ( EmptyPropertyBag < 0 )
    {
      v11 = 320;
      goto LABEL_26;
    }
  }
  *((_DWORD *)this + 22) = v4;
  WindowsDeleteString(*((HSTRING *)this + 12));
  *((_QWORD *)this + 12) = v14;
  v14 = 0;
  v12 = *((_QWORD *)this + 13);
  *((_QWORD *)this + 13) = v15;
  if ( v12 )
  {
    v15 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
  }
  return (unsigned int)EmptyPropertyBag;
}

```

## disassembly

```asm
0x180055b40  mov     [rsp-18h+arg_10], rbx
0x180055b45  mov     [rsp-18h+arg_18], rsi
0x180055b4a  push    rbp
0x180055b4b  push    rdi
0x180055b4c  push    r14
0x180055b4e  mov     rbp, rsp
0x180055b51  sub     rsp, 80h
0x180055b58  mov     rax, cs:__security_cookie
0x180055b5f  xor     rax, rsp
0x180055b62  mov     [rbp+var_10], rax
0x180055b66  mov     r14, rdx
0x180055b69  mov     rdi, rcx
0x180055b6c  xor     esi, esi
0x180055b6e  lea     r9, [rbp+string]; string
0x180055b72  lea     r8, [rbp+hstringHeader]; hstringHeader
0x180055b76  lea     edx, [rsi+8]; length
0x180055b79  lea     rcx, aWteCode; "WTE_Code"
0x180055b80  call    cs:__imp_WindowsCreateStringReference
0x180055b86  test    eax, eax
0x180055b88  jns     short loc_180055B9E
0x180055b8a  xor     r9d, r9d; lpArguments
0x180055b8d  xor     r8d, r8d; nNumberOfArguments
0x180055b90  lea     edx, [rsi+1]; dwExceptionFlags
0x180055b93  mov     ecx, 0C000000Dh; dwExceptionCode
0x180055b98  call    cs:__imp_RaiseException
0x180055b9e  mov     rdx, [rbp+string]
0x180055ba2  mov     dword ptr [rbp+var_60], esi
0x180055ba5  mov     [rbp+var_40], rsi
0x180055ba9  mov     [rbp+var_38], esi
0x180055bac  test    rdx, rdx
0x180055baf  jz      short loc_180055C22
0x180055bb1  mov     rcx, [r14+8]
0x180055bb5  mov     rax, [rcx]
0x180055bb8  lea     r8, [rbp+var_40]
0x180055bbc  mov     [rbp+var_50], r8
0x180055bc0  mov     [rbp+var_48], rsi
0x180055bc4  lea     r8, [rbp+var_48]
0x180055bc8  mov     rax, [rax+30h]
0x180055bcc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055bd1  mov     ebx, eax
0x180055bd3  lea     rcx, [rbp+var_50]; this
0x180055bd7  call    ??1OutRef@RoVariant@@QEAA@XZ; RoVariant::OutRef::~OutRef(void)
0x180055bdc  mov     eax, ebx
0x180055bde  shr     eax, 1Fh
0x180055be1  xor     al, 1
0x180055be3  jz      short loc_180055C27
0x180055be5  mov     r8, [rbp+var_40]
0x180055be9  mov     [rbp+var_50], r8
0x180055bed  mov     eax, [rbp+var_38]
0x180055bf0  mov     dword ptr [rbp+var_48], eax
0x180055bf3  mov     dword ptr [rbp+var_60], esi
0x180055bf6  lea     rcx, [rbp+var_50]; this
0x180055bfa  call    ?VerifyPV@Accessor@RoVariant@@AEBAJXZ; RoVariant::Accessor::VerifyPV(void)
0x180055bff  mov     ebx, eax
0x180055c01  test    eax, eax
0x180055c03  js      short loc_180055C27
0x180055c05  mov     rax, [r8]
0x180055c08  lea     rdx, [rbp+var_60]
0x180055c0c  mov     rcx, r8
0x180055c0f  mov     rax, [rax+58h]
0x180055c13  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055c18  mov     ebx, eax
0x180055c1a  test    eax, eax
0x180055c1c  cmovns  esi, dword ptr [rbp+var_60]
0x180055c20  jmp     short loc_180055C27
0x180055c22  mov     ebx, 80070057h
0x180055c27  lea     rcx, [rbp+var_40]; this
0x180055c2b  call    ??1RoVariant@@QEAA@XZ; RoVariant::~RoVariant(void)
0x180055c30  test    ebx, ebx
0x180055c32  jns     short loc_180055C51
0x180055c34  mov     rcx, [rbp+18h]; this
0x180055c38  mov     r9d, ebx; char *
0x180055c3b  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\tokenbroker\\api"...
0x180055c42  mov     edx, 131h; void *
0x180055c47  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180055c4c  jmp     loc_180055DCD
0x180055c51  mov     [rbp+var_60], 0
0x180055c59  lea     r9, [rbp+string]; string
0x180055c5d  lea     r8, [rbp+hstringHeader]; hstringHeader
0x180055c61  mov     edx, 0Bh; length
0x180055c66  lea     rcx, aWteMessage; "WTE_Message"
0x180055c6d  call    cs:__imp_WindowsCreateStringReference
0x180055c73  test    eax, eax
0x180055c75  jns     short loc_180055C8C
0x180055c77  xor     r9d, r9d; lpArguments
0x180055c7a  xor     r8d, r8d; nNumberOfArguments
0x180055c7d  lea     edx, [r9+1]; dwExceptionFlags
0x180055c81  mov     ecx, 0C000000Dh; dwExceptionCode
0x180055c86  call    cs:__imp_RaiseException
0x180055c8c  lea     r8, [rbp+var_60]; HSTRING *
0x180055c90  mov     rdx, [rbp+string]; HSTRING
0x180055c94  mov     rcx, r14; this
0x180055c97  call    ?GetStringProperty@CPropertiesSerializer@Security@Internal@Windows@@QEAAJPEAUHSTRING__@@PEAPEAU5@@Z; Windows::Internal::Security::CPropertiesSerializer::GetStringProperty(HSTRING__ *,HSTRING__ * *)
0x180055c9c  xor     ebx, ebx
0x180055c9e  cmp     eax, 8000000Bh
0x180055ca3  cmovnz  ebx, eax
0x180055ca6  test    ebx, ebx
0x180055ca8  jns     short loc_180055CDB
0x180055caa  mov     rcx, [rbp+18h]; this
0x180055cae  mov     r9d, ebx; char *
0x180055cb1  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\tokenbroker\\api"...
0x180055cb8  mov     edx, 136h; void *
0x180055cbd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180055cc2  nop
0x180055cc3  mov     rcx, [rbp+var_60]; string
0x180055cc7  test    rcx, rcx
0x180055cca  jz      loc_180055DCD
0x180055cd0  call    cs:__imp_WindowsDeleteString
0x180055cd6  jmp     loc_180055DCD
0x180055cdb  mov     [rbp+var_58], 0
0x180055ce3  lea     rcx, [rbp+var_58]
0x180055ce7  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180055cec  lea     r9, [rbp+string]; string
0x180055cf0  lea     r8, [rbp+hstringHeader]; hstringHeader
0x180055cf4  mov     edx, 0Fh; length
0x180055cf9  lea     rcx, aWtePropertybag; "WTE_PropertyBag"
0x180055d00  call    cs:__imp_WindowsCreateStringReference
0x180055d06  test    eax, eax
0x180055d08  jns     short loc_180055D1F
0x180055d0a  xor     r9d, r9d; lpArguments
0x180055d0d  xor     r8d, r8d; nNumberOfArguments
0x180055d10  lea     edx, [r9+1]; dwExceptionFlags
0x180055d14  mov     ecx, 0C000000Dh; dwExceptionCode
0x180055d19  call    cs:__imp_RaiseException
0x180055d1f  lea     r8, [rbp+var_58]
0x180055d23  mov     rdx, [rbp+string]
0x180055d27  mov     rcx, r14
0x180055d2a  call    ?GetHStringPropertyBagProperty@CPropertiesSerializer@Security@Internal@Windows@@QEAAJPEAUHSTRING__@@PEAPEAU?$IMap@PEAUHSTRING__@@PEAU1@@Collections@Foundation@4@@Z; Windows::Internal::Security::CPropertiesSerializer::GetHStringPropertyBagProperty(HSTRING__ *,Windows::Foundation::Collections::IMap<HSTRING__ *,HSTRING__ *> * *)
0x180055d2f  xor     ebx, ebx
0x180055d31  cmp     eax, 8000000Bh
0x180055d36  cmovnz  ebx, eax
0x180055d39  test    ebx, ebx
0x180055d3b  jns     short loc_180055D64
0x180055d3d  mov     edx, 13Bh; void *
0x180055d42  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\tokenbroker\\api"...
0x180055d49  mov     r9d, ebx; char *
0x180055d4c  mov     rcx, [rbp+18h]; this
0x180055d50  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180055d55  nop
0x180055d56  lea     rcx, [rbp+var_58]
0x180055d5a  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180055d5f  jmp     loc_180055CC3
0x180055d64  cmp     [rbp+var_58], 0
0x180055d69  jnz     short loc_180055D8A
0x180055d6b  lea     rcx, [rbp+var_58]
0x180055d6f  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180055d74  lea     rcx, [rbp+var_58]
0x180055d78  call    ?MakeEmptyPropertyBag@@YAJPEAPEAU?$IMap@PEAUHSTRING__@@PEAU1@@Collections@Foundation@Windows@@@Z; MakeEmptyPropertyBag(Windows::Foundation::Collections::IMap<HSTRING__ *,HSTRING__ *> * *)
0x180055d7d  mov     ebx, eax
0x180055d7f  test    eax, eax
0x180055d81  jns     short loc_180055D8A
0x180055d83  mov     edx, 140h
0x180055d88  jmp     short loc_180055D42
0x180055d8a  mov     [rdi+58h], esi
0x180055d8d  mov     rcx, [rdi+60h]; string
0x180055d91  call    cs:__imp_WindowsDeleteString
0x180055d97  mov     rax, [rbp+var_60]
0x180055d9b  mov     [rdi+60h], rax
0x180055d9f  mov     [rbp+var_60], 0
0x180055da7  mov     rcx, [rdi+68h]
0x180055dab  mov     rax, [rbp+var_58]
0x180055daf  mov     [rdi+68h], rax
0x180055db3  test    rcx, rcx
0x180055db6  jz      short loc_180055DCD
0x180055db8  mov     [rbp+var_58], 0
0x180055dc0  mov     rax, [rcx]
0x180055dc3  mov     rax, [rax+10h]
0x180055dc7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055dcc  nop
0x180055dcd  mov     eax, ebx
0x180055dcf  mov     rcx, [rbp+var_10]
0x180055dd3  xor     rcx, rsp; StackCookie
0x180055dd6  call    __security_check_cookie
0x180055ddb  lea     r11, [rsp+80h+var_s0]
0x180055de3  mov     rbx, [r11+30h]
0x180055de7  mov     rsi, [r11+38h]
0x180055deb  mov     rsp, r11
0x180055dee  pop     r14
0x180055df0  pop     rdi
0x180055df1  pop     rbp
0x180055df2  retn
```
