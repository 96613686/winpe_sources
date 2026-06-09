# Windows::Security::Authentication::Web::Core::CWebProviderError::Serialize(Windows::Internal::Security::CPropertiesSerializer &)

- ea: `0x180046e74`
- end: `0x180047114`
- name: `?Serialize@CWebProviderError@Core@Web@Authentication@Security@Windows@@AEAAJAEAVCPropertiesSerializer@5Internal@6@@Z`
- size: `672`
- prototype: `int(Windows::Security::Authentication::Web::Core::CWebProviderError *__hidden this, struct Windows::Internal::Security::CPropertiesSerializer *)`
- caller_count: `3`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180046d80`
- `0x1800f7c50`
- `0x1800f9da0`

## callees

- `0x180007350`
- `0x18000bd40`
- `0x18001873c`
- `0x180046e74`
- `0x18004711c`
- `0x1800471e0`
- `0x18008e690`
- `0x18011b010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180047091`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800470ab`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800470e2`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180047091`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800470ab`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800470e2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180046eae`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180046f64`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180047018`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180046eae`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180046f64`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180047018`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x180046ed9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x180046ed9`

## string_xrefs

- `0x180046fce`: `onecore\ds\security\tokenbroker\api\lib\webtoken.cpp`
- `0x18004704d`: `onecore\ds\security\tokenbroker\api\lib\webtoken.cpp`
- `0x1800470bb`: `onecore\ds\security\tokenbroker\api\lib\webtoken.cpp`
- `0x1800470f4`: `onecore\ds\security\tokenbroker\api\lib\webtoken.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Windows::Security::Authentication::Web::Core::CWebProviderError::Serialize(
        Windows::Security::Authentication::Web::Core::CWebProviderError *this,
        struct Windows::Internal::Security::CPropertiesSerializer *a2)
{
  int v4; // ebx
  unsigned int v5; // ebx
  __int64 v6; // rdi
  __int64 (__fastcall *v7)(__int64, __int64 *); // rbx
  int v8; // eax
  __int64 v9; // rcx
  int v10; // eax
  __int64 v11; // rbx
  int v12; // eax
  __int64 v14; // rcx
  HSTRING v15; // rbx
  __int64 v16; // rdx
  __int64 v17; // rcx
  __int64 v18; // [rsp+20h] [rbp-40h] BYREF
  int v19; // [rsp+28h] [rbp-38h] BYREF
  HSTRING string; // [rsp+30h] [rbp-30h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+38h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+18h]

  v4 = *((_DWORD *)this + 22);
  if ( WindowsCreateStringReference(L"WTE_Code", 8u, &hstringHeader, &string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  v5 = Windows::Internal::Security::CPropertiesSerializer::AddInt32Property(a2, string, v4);
  if ( (v5 & 0x80000000) != 0 )
  {
    v16 = 206;
    goto LABEL_27;
  }
  if ( !WindowsIsStringEmpty(*((HSTRING *)this + 12)) )
  {
    v15 = (HSTRING)*((_QWORD *)this + 12);
    if ( WindowsCreateStringReference(L"WTE_Message", 0xBu, &hstringHeader, &string) < 0 )
      RaiseException(0xC000000D, 1u, 0, 0);
    v5 = Windows::Internal::Security::CPropertiesSerializer::AddStringProperty(a2, string, v15);
    if ( (v5 & 0x80000000) != 0 )
    {
      v16 = 212;
LABEL_27:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v16,
        (unsigned int)"onecore\\ds\\security\\tokenbroker\\api\\lib\\webtoken.cpp",
        (const char *)v5,
        v18);
      return v5;
    }
  }
  v18 = 0;
  v6 = *((_QWORD *)this + 13);
  v7 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v6 + 72LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v18);
  v8 = v7(v6, &v18);
  v5 = v8;
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xDC,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\api\\lib\\webtoken.cpp",
      (const char *)(unsigned int)v8,
      v18);
    v17 = v18;
    if ( v18 )
    {
      v18 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
    }
  }
  else
  {
    v9 = v18;
    if ( !v18 )
    {
LABEL_13:
      if ( v9 )
      {
        v18 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
      }
      return v5;
    }
    v19 = 0;
    v10 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v18 + 56LL))(v18, &v19);
    v5 = v10;
    if ( v10 >= 0 )
    {
      if ( v19 )
      {
        v11 = v18;
        if ( WindowsCreateStringReference(L"WTE_PropertyBag", 0xFu, &hstringHeader, &string) < 0 )
          RaiseException(0xC000000D, 1u, 0, 0);
        v12 = Windows::Internal::Security::CPropertiesSerializer::AddHStringPropertyBagProperty(a2, string, v11);
        v5 = v12;
        if ( v12 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xE6,
            (unsigned int)"onecore\\ds\\security\\tokenbroker\\api\\lib\\webtoken.cpp",
            (const char *)(unsigned int)v12,
            v18);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v18);
          return v5;
        }
      }
      v9 = v18;
      goto LABEL_13;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xE0,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\api\\lib\\webtoken.cpp",
      (const char *)(unsigned int)v10,
      v18);
    v14 = v18;
    if ( v18 )
    {
      v18 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
    }
  }
  return v5;
}

```

## disassembly

```asm
0x180046e74  mov     [rsp-18h+arg_10], rbx
0x180046e79  push    rbp
0x180046e7a  push    rsi
0x180046e7b  push    rdi
0x180046e7c  mov     rbp, rsp
0x180046e7f  sub     rsp, 60h
0x180046e83  mov     rax, cs:__security_cookie
0x180046e8a  xor     rax, rsp
0x180046e8d  mov     [rbp+var_10], rax
0x180046e91  mov     rsi, rdx
0x180046e94  mov     rdi, rcx
0x180046e97  mov     ebx, [rcx+58h]
0x180046e9a  lea     r9, [rbp+string]; string
0x180046e9e  lea     r8, [rbp+hstringHeader]; hstringHeader
0x180046ea2  mov     edx, 8; length
0x180046ea7  lea     rcx, aWteCode; "WTE_Code"
0x180046eae  call    cs:__imp_WindowsCreateStringReference
0x180046eb4  test    eax, eax
0x180046eb6  js      loc_180047082
0x180046ebc  mov     r8d, ebx; int
0x180046ebf  mov     rdx, [rbp+string]; HSTRING
0x180046ec3  mov     rcx, rsi; this
0x180046ec6  call    ?AddInt32Property@CPropertiesSerializer@Security@Internal@Windows@@QEAAJPEAUHSTRING__@@H@Z; Windows::Internal::Security::CPropertiesSerializer::AddInt32Property(HSTRING__ *,int)
0x180046ecb  mov     ebx, eax
0x180046ecd  test    eax, eax
0x180046ecf  js      loc_1800470B6
0x180046ed5  mov     rcx, [rdi+60h]; string
0x180046ed9  call    cs:__imp_WindowsIsStringEmpty
0x180046edf  test    eax, eax
0x180046ee1  jz      loc_180047000
0x180046ee7  mov     [rbp+var_40], 0
0x180046eef  mov     rdi, [rdi+68h]
0x180046ef3  mov     rax, [rdi]
0x180046ef6  mov     rbx, [rax+48h]
0x180046efa  lea     rcx, [rbp+var_40]
0x180046efe  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180046f03  lea     rdx, [rbp+var_40]
0x180046f07  mov     rcx, rdi
0x180046f0a  mov     rax, rbx
0x180046f0d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046f12  mov     ebx, eax
0x180046f14  test    eax, eax
0x180046f16  js      loc_180047046
0x180046f1c  mov     rcx, [rbp+var_40]
0x180046f20  test    rcx, rcx
0x180046f23  jz      short loc_180046F8F
0x180046f25  mov     [rbp+var_38], 0
0x180046f2c  mov     rax, [rcx]
0x180046f2f  lea     rdx, [rbp+var_38]
0x180046f33  mov     rax, [rax+38h]
0x180046f37  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046f3c  mov     ebx, eax
0x180046f3e  test    eax, eax
0x180046f40  js      loc_180046FC7
0x180046f46  cmp     [rbp+var_38], 0
0x180046f4a  jbe     short loc_180046F8B
0x180046f4c  mov     rbx, [rbp+var_40]
0x180046f50  lea     r9, [rbp+string]; string
0x180046f54  lea     r8, [rbp+hstringHeader]; hstringHeader
0x180046f58  mov     edx, 0Fh; length
0x180046f5d  lea     rcx, aWtePropertybag; "WTE_PropertyBag"
0x180046f64  call    cs:__imp_WindowsCreateStringReference
0x180046f6a  test    eax, eax
0x180046f6c  js      loc_18004709C
0x180046f72  mov     r8, rbx
0x180046f75  mov     rdx, [rbp+string]
0x180046f79  mov     rcx, rsi
0x180046f7c  call    ?AddHStringPropertyBagProperty@CPropertiesSerializer@Security@Internal@Windows@@QEAAJPEAUHSTRING__@@PEAU?$IMapView@PEAUHSTRING__@@PEAU1@@Collections@Foundation@4@@Z; Windows::Internal::Security::CPropertiesSerializer::AddHStringPropertyBagProperty(HSTRING__ *,Windows::Foundation::Collections::IMapView<HSTRING__ *,HSTRING__ *> *)
0x180046f81  mov     ebx, eax
0x180046f83  test    eax, eax
0x180046f85  js      loc_1800470ED
0x180046f8b  mov     rcx, [rbp+var_40]
0x180046f8f  test    rcx, rcx
0x180046f92  jz      short loc_180046FA9
0x180046f94  mov     [rbp+var_40], 0
0x180046f9c  mov     rax, [rcx]
0x180046f9f  mov     rax, [rax+10h]
0x180046fa3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046fa8  nop
0x180046fa9  mov     eax, ebx
0x180046fab  mov     rcx, [rbp+var_10]
0x180046faf  xor     rcx, rsp; StackCookie
0x180046fb2  call    __security_check_cookie
0x180046fb7  mov     rbx, [rsp+60h+arg_10]
0x180046fbf  add     rsp, 60h
0x180046fc3  pop     rdi
0x180046fc4  pop     rsi
0x180046fc5  pop     rbp
0x180046fc6  retn
0x180046fc7  mov     rcx, [rbp+18h]; this
0x180046fcb  mov     r9d, ebx; char *
0x180046fce  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\tokenbroker\\api"...
0x180046fd5  mov     edx, 0E0h; void *
0x180046fda  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180046fdf  nop
0x180046fe0  mov     rcx, [rbp+var_40]
0x180046fe4  test    rcx, rcx
0x180046fe7  jz      short loc_180046FFE
0x180046fe9  mov     [rbp+var_40], 0
0x180046ff1  mov     rax, [rcx]
0x180046ff4  mov     rax, [rax+10h]
0x180046ff8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046ffd  nop
0x180046ffe  jmp     short loc_180046FA9
0x180047000  mov     rbx, [rdi+60h]
0x180047004  lea     r9, [rbp+string]; string
0x180047008  lea     r8, [rbp+hstringHeader]; hstringHeader
0x18004700c  mov     edx, 0Bh; length
0x180047011  lea     rcx, aWteMessage; "WTE_Message"
0x180047018  call    cs:__imp_WindowsCreateStringReference
0x18004701e  test    eax, eax
0x180047020  js      loc_1800470D3
0x180047026  mov     r8, rbx; HSTRING
0x180047029  mov     rdx, [rbp+string]; HSTRING
0x18004702d  mov     rcx, rsi; this
0x180047030  call    ?AddStringProperty@CPropertiesSerializer@Security@Internal@Windows@@QEAAJPEAUHSTRING__@@0@Z; Windows::Internal::Security::CPropertiesSerializer::AddStringProperty(HSTRING__ *,HSTRING__ *)
0x180047035  mov     ebx, eax
0x180047037  test    eax, eax
0x180047039  jns     loc_180046EE7
0x18004703f  mov     edx, 0D4h
0x180047044  jmp     short loc_1800470BB
0x180047046  mov     rcx, [rbp+18h]; this
0x18004704a  mov     r9d, ebx; char *
0x18004704d  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\tokenbroker\\api"...
0x180047054  mov     edx, 0DCh; void *
0x180047059  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004705e  nop
0x18004705f  mov     rcx, [rbp+var_40]
0x180047063  test    rcx, rcx
0x180047066  jz      short loc_18004707D
0x180047068  mov     [rbp+var_40], 0
0x180047070  mov     rax, [rcx]
0x180047073  mov     rax, [rax+10h]
0x180047077  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004707c  nop
0x18004707d  jmp     loc_180046FA9
0x180047082  xor     r9d, r9d; lpArguments
0x180047085  xor     r8d, r8d; nNumberOfArguments
0x180047088  lea     edx, [r9+1]; dwExceptionFlags
0x18004708c  mov     ecx, 0C000000Dh; dwExceptionCode
0x180047091  call    cs:__imp_RaiseException
0x180047097  jmp     loc_180046EBC
0x18004709c  xor     r9d, r9d; lpArguments
0x18004709f  xor     r8d, r8d; nNumberOfArguments
0x1800470a2  lea     edx, [r9+1]; dwExceptionFlags
0x1800470a6  mov     ecx, 0C000000Dh; dwExceptionCode
0x1800470ab  call    cs:__imp_RaiseException
0x1800470b1  jmp     loc_180046F72
0x1800470b6  mov     edx, 0CEh; void *
0x1800470bb  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\tokenbroker\\api"...
0x1800470c2  mov     r9d, ebx; char *
0x1800470c5  mov     rcx, [rbp+18h]; this
0x1800470c9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800470ce  jmp     loc_180046FA9
0x1800470d3  xor     r9d, r9d; lpArguments
0x1800470d6  xor     r8d, r8d; nNumberOfArguments
0x1800470d9  lea     edx, [r9+1]; dwExceptionFlags
0x1800470dd  mov     ecx, 0C000000Dh; dwExceptionCode
0x1800470e2  call    cs:__imp_RaiseException
0x1800470e8  jmp     loc_180047026
0x1800470ed  mov     rcx, [rbp+18h]; this
0x1800470f1  mov     r9d, ebx; char *
0x1800470f4  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\tokenbroker\\api"...
0x1800470fb  mov     edx, 0E6h; void *
0x180047100  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180047105  nop
0x180047106  lea     rcx, [rbp+var_40]
0x18004710a  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18004710f  jmp     loc_180046FA9
```
