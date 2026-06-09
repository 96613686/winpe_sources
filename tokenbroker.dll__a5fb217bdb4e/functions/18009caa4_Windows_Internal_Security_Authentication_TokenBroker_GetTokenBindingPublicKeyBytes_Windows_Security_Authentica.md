# Windows::Internal::Security::Authentication::TokenBroker::GetTokenBindingPublicKeyBytes(Windows::Security::Authentication::Web::TokenBindingKeyType,Windows::Foundation::IUriRuntimeClass *,Windows::Security::Authentication::Web::TokenBindingKeyType *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>> &,ulong &)

- ea: `0x18009caa4`
- end: `0x18009cd97`
- name: `?GetTokenBindingPublicKeyBytes@TokenBroker@Authentication@Security@Internal@Windows@@YAJW4TokenBindingKeyType@Web@235@PEAUIUriRuntimeClass@Foundation@5@PEAW467235@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@AEAK@Z`
- size: `755`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18009cda0`

## callees

- `0x18000bd40`
- `0x18001a510`
- `0x180045a04`
- `0x18004fdbc`
- `0x180055418`
- `0x18009caa4`
- `0x18009ce74`
- `0x1800ea1ec`
- `0x1800ea284`
- `0x1800ea358`
- `0x18011b010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18009cbc9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18009cbfa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18009cbc9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18009cbfa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009cb66`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009cb98`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009cc3f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009cc92`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009ccfa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009cd3e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009cd5f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009cb66`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009cb98`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009cc3f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009cc92`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009ccfa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009cd3e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009cd5f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x18009cb85`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x18009cb85`

## string_xrefs

- `0x18009cb4b`: `onecore\ds\security\tokenbroker\broker\lib\tbtokenbinding.cpp`
- `0x18009cc24`: `onecore\ds\security\tokenbroker\broker\lib\tbtokenbinding.cpp`
- `0x18009cc77`: `onecore\ds\security\tokenbroker\broker\lib\tbtokenbinding.cpp`
- `0x18009ccdf`: `onecore\ds\security\tokenbroker\broker\lib\tbtokenbinding.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall Windows::Internal::Security::Authentication::TokenBroker::GetTokenBindingPublicKeyBytes(
        int a1,
        __int64 a2,
        int *a3,
        __int64 a4,
        _DWORD *a5)
{
  unsigned int v9; // esi
  int v10; // eax
  unsigned int v11; // ebx
  int v12; // ecx
  int v13; // r8d
  int v14; // r9d
  PCWSTR StringRawBuffer; // rax
  int Key; // eax
  int CurrentKey; // eax
  int TokenBindingPublicKeyWrapper; // eax
  int v20; // [rsp+20h] [rbp-50h]
  int v21; // [rsp+30h] [rbp-40h] BYREF
  HSTRING string; // [rsp+38h] [rbp-38h] BYREF
  __int64 v23; // [rsp+40h] [rbp-30h] BYREF
  __int64 v24; // [rsp+48h] [rbp-28h] BYREF
  _QWORD v25[2]; // [rsp+50h] [rbp-20h] BYREF
  char v26; // [rsp+60h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+28h]
  int v28; // [rsp+A0h] [rbp+30h] BYREF
  int v29; // [rsp+A8h] [rbp+38h] BYREF

  v24 = 0;
  v29 = 0;
  v23 = 0;
  v9 = -1;
  v28 = 0;
  if ( (unsigned int)dword_180175000 > 4 )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      &dword_180175000,
      byte_180145431,
      0,
      0);
  v25[1] = &v23;
  v26 = 1;
  if ( a1 )
  {
    if ( a1 == 1 )
      v9 = 2;
  }
  else
  {
    v9 = 0;
  }
  string = 0;
  v10 = (*(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)a2 + 64LL))(a2, &string);
  v11 = v10;
  if ( v10 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x248,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\tbtokenbinding.cpp",
      (const char *)(unsigned int)v10,
      v20);
    if ( string )
      WindowsDeleteString(string);
    if ( v23 )
      TokenBindingFreeKey();
LABEL_43:
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v24);
    return v11;
  }
  if ( WindowsIsStringEmpty(string) )
  {
    if ( string )
      WindowsDeleteString(string);
    if ( v23 )
      TokenBindingFreeKey();
    v11 = -2147024809;
    goto LABEL_43;
  }
  if ( (unsigned int)dword_180175000 > 5 )
  {
    v25[0] = WindowsGetStringRawBuffer(string, 0);
    v21 = v9;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>>(
      v12,
      (unsigned int)byte_180145463,
      v13,
      v14,
      (__int64)&v21,
      (__int64)v25);
  }
  StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
  if ( a1 != 2 )
  {
    Key = TokenBindingGetKey(v9, StringRawBuffer, &v23);
    v11 = Key;
    if ( Key < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x25C,
        (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\tbtokenbinding.cpp",
        (const char *)(unsigned int)Key,
        v20);
      if ( string )
        WindowsDeleteString(string);
      if ( v23 )
        TokenBindingFreeKey();
      goto LABEL_43;
    }
LABEL_38:
    TokenBindingPublicKeyWrapper = Windows::Internal::Security::Authentication::TokenBroker::GetTokenBindingPublicKeyWrapper(
                                     v23,
                                     &v24,
                                     &v29);
    v11 = TokenBindingPublicKeyWrapper;
    if ( TokenBindingPublicKeyWrapper >= 0 )
    {
      *a3 = a1;
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>::swap(
        &v24,
        a4);
      *a5 = v29;
      if ( string )
        WindowsDeleteString(string);
      if ( v23 )
        TokenBindingFreeKey();
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x27C,
        (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\tbtokenbinding.cpp",
        (const char *)(unsigned int)TokenBindingPublicKeyWrapper,
        v20);
      if ( string )
        WindowsDeleteString(string);
      if ( v23 )
        TokenBindingFreeKey();
    }
    goto LABEL_43;
  }
  CurrentKey = TokenBindingGetCurrentKey(StringRawBuffer, &v23, &v28);
  v11 = CurrentKey;
  if ( CurrentKey < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x266,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\tbtokenbinding.cpp",
      (const char *)(unsigned int)CurrentKey,
      v20);
    if ( string )
      WindowsDeleteString(string);
    if ( v23 )
      TokenBindingFreeKey();
    goto LABEL_43;
  }
  if ( !v28 )
  {
    a1 = 0;
    goto LABEL_38;
  }
  if ( v28 == 2 )
  {
    a1 = 1;
    goto LABEL_38;
  }
  if ( string )
    WindowsDeleteString(string);
  if ( v23 )
    TokenBindingFreeKey();
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v24);
  return 50;
}

```

## disassembly

```asm
0x18009caa4  mov     [rsp-28h+arg_10], rbx
0x18009caa9  push    rbp
0x18009caaa  push    rsi
0x18009caab  push    rdi
0x18009caac  push    r14
0x18009caae  push    r15
0x18009cab0  mov     rbp, rsp
0x18009cab3  sub     rsp, 70h
0x18009cab7  mov     r14, r9
0x18009caba  mov     r15, r8
0x18009cabd  mov     rbx, rdx
0x18009cac0  mov     edi, ecx
0x18009cac2  mov     [rbp+var_28], 0
0x18009caca  mov     [rbp+arg_8], 0
0x18009cad1  mov     [rbp+var_30], 0
0x18009cad9  or      esi, 0FFFFFFFFh
0x18009cadc  mov     [rbp+arg_0], 0
0x18009cae3  mov     eax, cs:dword_180175000
0x18009cae9  cmp     eax, 4
0x18009caec  jbe     short loc_18009CB07
0x18009caee  xor     r9d, r9d
0x18009caf1  xor     r8d, r8d
0x18009caf4  lea     rdx, byte_180145431
0x18009cafb  lea     rcx, dword_180175000
0x18009cb02  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x18009cb07  lea     rax, [rbp+var_30]
0x18009cb0b  mov     [rbp+var_18], rax
0x18009cb0f  mov     [rbp+var_10], 1
0x18009cb13  test    edi, edi
0x18009cb15  jz      short loc_18009CB21
0x18009cb17  cmp     edi, 1
0x18009cb1a  jnz     short loc_18009CB23
0x18009cb1c  lea     esi, [rdi+1]
0x18009cb1f  jmp     short loc_18009CB23
0x18009cb21  xor     esi, esi
0x18009cb23  mov     [rbp+string], 0
0x18009cb2b  mov     rax, [rbx]
0x18009cb2e  lea     rdx, [rbp+string]
0x18009cb32  mov     rcx, rbx
0x18009cb35  mov     rax, [rax+40h]
0x18009cb39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009cb3e  mov     ebx, eax
0x18009cb40  test    eax, eax
0x18009cb42  jns     short loc_18009CB81
0x18009cb44  mov     rcx, [rbp+28h]; this
0x18009cb48  mov     r9d, eax; char *
0x18009cb4b  lea     r8, aOnecoreDsSecur_46; "onecore\\ds\\security\\tokenbroker\\bro"...
0x18009cb52  mov     edx, 248h; void *
0x18009cb57  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009cb5c  nop
0x18009cb5d  mov     rcx, [rbp+string]; string
0x18009cb61  test    rcx, rcx
0x18009cb64  jz      short loc_18009CB6D
0x18009cb66  call    cs:__imp_WindowsDeleteString
0x18009cb6c  nop
0x18009cb6d  mov     rcx, [rbp+var_30]
0x18009cb71  test    rcx, rcx
0x18009cb74  jz      short loc_18009CB7C
0x18009cb76  call    TokenBindingFreeKey
0x18009cb7b  nop
0x18009cb7c  jmp     loc_18009CD10
0x18009cb81  mov     rcx, [rbp+string]; string
0x18009cb85  call    cs:__imp_WindowsIsStringEmpty
0x18009cb8b  test    eax, eax
0x18009cb8d  jz      short loc_18009CBB8
0x18009cb8f  mov     rcx, [rbp+string]; string
0x18009cb93  test    rcx, rcx
0x18009cb96  jz      short loc_18009CB9F
0x18009cb98  call    cs:__imp_WindowsDeleteString
0x18009cb9e  nop
0x18009cb9f  mov     rcx, [rbp+var_30]
0x18009cba3  test    rcx, rcx
0x18009cba6  jz      short loc_18009CBAE
0x18009cba8  call    TokenBindingFreeKey
0x18009cbad  nop
0x18009cbae  mov     ebx, 80070057h
0x18009cbb3  jmp     loc_18009CD10
0x18009cbb8  mov     eax, cs:dword_180175000
0x18009cbbe  cmp     eax, 5
0x18009cbc1  jbe     short loc_18009CBF4
0x18009cbc3  xor     edx, edx; length
0x18009cbc5  mov     rcx, [rbp+string]; string
0x18009cbc9  call    cs:__imp_WindowsGetStringRawBuffer
0x18009cbcf  mov     [rbp+var_20], rax
0x18009cbd3  mov     [rbp+var_40], esi
0x18009cbd6  lea     rax, [rbp+var_20]
0x18009cbda  mov     [rsp+70h+var_48], rax
0x18009cbdf  lea     rax, [rbp+var_40]
0x18009cbe3  mov     qword ptr [rsp+70h+var_50], rax; int
0x18009cbe8  lea     rdx, byte_180145463
0x18009cbef  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &)
0x18009cbf4  xor     edx, edx; length
0x18009cbf6  mov     rcx, [rbp+string]; string
0x18009cbfa  call    cs:__imp_WindowsGetStringRawBuffer
0x18009cc00  cmp     edi, 2
0x18009cc03  jz      short loc_18009CC5A
0x18009cc05  lea     r8, [rbp+var_30]
0x18009cc09  mov     rdx, rax
0x18009cc0c  mov     ecx, esi
0x18009cc0e  call    TokenBindingGetKey
0x18009cc13  mov     ebx, eax
0x18009cc15  test    eax, eax
0x18009cc17  jns     loc_18009CCC1
0x18009cc1d  mov     rcx, [rbp+28h]; this
0x18009cc21  mov     r9d, eax; char *
0x18009cc24  lea     r8, aOnecoreDsSecur_46; "onecore\\ds\\security\\tokenbroker\\bro"...
0x18009cc2b  mov     edx, 25Ch; void *
0x18009cc30  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009cc35  nop
0x18009cc36  mov     rcx, [rbp+string]; string
0x18009cc3a  test    rcx, rcx
0x18009cc3d  jz      short loc_18009CC46
0x18009cc3f  call    cs:__imp_WindowsDeleteString
0x18009cc45  nop
0x18009cc46  mov     rcx, [rbp+var_30]
0x18009cc4a  test    rcx, rcx
0x18009cc4d  jz      short loc_18009CC55
0x18009cc4f  call    TokenBindingFreeKey
0x18009cc54  nop
0x18009cc55  jmp     loc_18009CD10
0x18009cc5a  lea     r8, [rbp+arg_0]
0x18009cc5e  lea     rdx, [rbp+var_30]
0x18009cc62  mov     rcx, rax
0x18009cc65  call    TokenBindingGetCurrentKey
0x18009cc6a  mov     ebx, eax
0x18009cc6c  test    eax, eax
0x18009cc6e  jns     short loc_18009CCAA
0x18009cc70  mov     rcx, [rbp+28h]; this
0x18009cc74  mov     r9d, eax; char *
0x18009cc77  lea     r8, aOnecoreDsSecur_46; "onecore\\ds\\security\\tokenbroker\\bro"...
0x18009cc7e  mov     edx, 266h; void *
0x18009cc83  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009cc88  nop
0x18009cc89  mov     rcx, [rbp+string]; string
0x18009cc8d  test    rcx, rcx
0x18009cc90  jz      short loc_18009CC99
0x18009cc92  call    cs:__imp_WindowsDeleteString
0x18009cc98  nop
0x18009cc99  mov     rcx, [rbp+var_30]
0x18009cc9d  test    rcx, rcx
0x18009cca0  jz      short loc_18009CCA8
0x18009cca2  call    TokenBindingFreeKey
0x18009cca7  nop
0x18009cca8  jmp     short loc_18009CD10
0x18009ccaa  mov     eax, [rbp+arg_0]
0x18009ccad  test    eax, eax
0x18009ccaf  jnz     short loc_18009CCB5
0x18009ccb1  xor     edi, edi
0x18009ccb3  jmp     short loc_18009CCC1
0x18009ccb5  cmp     eax, 2
0x18009ccb8  jnz     loc_18009CD56
0x18009ccbe  lea     edi, [rax-1]
0x18009ccc1  lea     r8, [rbp+arg_8]
0x18009ccc5  lea     rdx, [rbp+var_28]
0x18009ccc9  mov     rcx, [rbp+var_30]
0x18009cccd  call    ?GetTokenBindingPublicKeyWrapper@TokenBroker@Authentication@Security@Internal@Windows@@YAJPEAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@PEAK@Z; Windows::Internal::Security::Authentication::TokenBroker::GetTokenBindingPublicKeyWrapper(void *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>> &,ulong *)
0x18009ccd2  mov     ebx, eax
0x18009ccd4  test    eax, eax
0x18009ccd6  jns     short loc_18009CD1D
0x18009ccd8  mov     rcx, [rbp+28h]; this
0x18009ccdc  mov     r9d, eax; char *
0x18009ccdf  lea     r8, aOnecoreDsSecur_46; "onecore\\ds\\security\\tokenbroker\\bro"...
0x18009cce6  mov     edx, 27Ch; void *
0x18009cceb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009ccf0  nop
0x18009ccf1  mov     rcx, [rbp+string]; string
0x18009ccf5  test    rcx, rcx
0x18009ccf8  jz      short loc_18009CD01
0x18009ccfa  call    cs:__imp_WindowsDeleteString
0x18009cd00  nop
0x18009cd01  mov     rcx, [rbp+var_30]
0x18009cd05  test    rcx, rcx
0x18009cd08  jz      short loc_18009CD10
0x18009cd0a  call    TokenBindingFreeKey
0x18009cd0f  nop
0x18009cd10  lea     rcx, [rbp+var_28]
0x18009cd14  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x18009cd19  mov     eax, ebx
0x18009cd1b  jmp     short loc_18009CD83
0x18009cd1d  mov     [r15], edi
0x18009cd20  mov     rdx, r14
0x18009cd23  lea     rcx, [rbp+var_28]
0x18009cd27  call    ?swap@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAXAEAV12@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>::swap(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>> &)
0x18009cd2c  mov     rcx, [rbp+arg_20]
0x18009cd30  mov     eax, [rbp+arg_8]
0x18009cd33  mov     [rcx], eax
0x18009cd35  mov     rcx, [rbp+string]; string
0x18009cd39  test    rcx, rcx
0x18009cd3c  jz      short loc_18009CD45
0x18009cd3e  call    cs:__imp_WindowsDeleteString
0x18009cd44  nop
0x18009cd45  mov     rcx, [rbp+var_30]
0x18009cd49  test    rcx, rcx
0x18009cd4c  jz      short loc_18009CD54
0x18009cd4e  call    TokenBindingFreeKey
0x18009cd53  nop
0x18009cd54  jmp     short loc_18009CD10
0x18009cd56  mov     rcx, [rbp+string]; string
0x18009cd5a  test    rcx, rcx
0x18009cd5d  jz      short loc_18009CD66
0x18009cd5f  call    cs:__imp_WindowsDeleteString
0x18009cd65  nop
0x18009cd66  mov     rcx, [rbp+var_30]
0x18009cd6a  test    rcx, rcx
0x18009cd6d  jz      short loc_18009CD75
0x18009cd6f  call    TokenBindingFreeKey
0x18009cd74  nop
0x18009cd75  lea     rcx, [rbp+var_28]
0x18009cd79  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x18009cd7e  mov     eax, 32h ; '2'
0x18009cd83  mov     rbx, [rsp+70h+arg_10]
0x18009cd8b  add     rsp, 70h
0x18009cd8f  pop     r15
0x18009cd91  pop     r14
0x18009cd93  pop     rdi
0x18009cd94  pop     rsi
0x18009cd95  pop     rbp
0x18009cd96  retn
```
