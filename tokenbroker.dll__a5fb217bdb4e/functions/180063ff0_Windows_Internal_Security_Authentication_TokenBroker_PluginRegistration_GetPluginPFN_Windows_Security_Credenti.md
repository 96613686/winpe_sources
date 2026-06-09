# Windows::Internal::Security::Authentication::TokenBroker::PluginRegistration::GetPluginPFN(Windows::Security::Credentials::IWebAccountProvider *,HSTRING__ * *)

- ea: `0x180063ff0`
- end: `0x18006426b`
- name: `?GetPluginPFN@PluginRegistration@TokenBroker@Authentication@Security@Internal@Windows@@SAJPEAUIWebAccountProvider@Credentials@46@PEAPEAUHSTRING__@@@Z`
- size: `635`
- prototype: `__int64 __fastcall(struct Windows::Security::Credentials::IWebAccountProvider *, HSTRING *)`
- caller_count: `16`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180070390`
- `0x180070660`
- `0x1800729e0`
- `0x1800a6a30`
- `0x1800abfec`
- `0x1800ac658`
- `0x1800aef20`
- `0x1800e38ec`
- `0x1800e4294`
- `0x180100498`
- `0x180104748`
- `0x180104f84`
- `0x180109a4c`
- `0x18010b53c`
- `0x18010f754`
- `0x18010fa10`

## callees

- `0x180007350`
- `0x18000bd40`
- `0x180029478`
- `0x180031cf8`
- `0x180040980`
- `0x1800426b0`
- `0x180063ff0`
- `0x18011b010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800640a9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800640ce`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800640dd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800641c3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800640a9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800640ce`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800640dd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800641c3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180064060`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180064070`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180064080`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180064219`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180064228`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180064237`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180064246`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180064060`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180064070`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180064080`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180064219`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180064228`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180064237`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180064246`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x1800640b6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x1800640b6`

## string_xrefs

- `0x180064045`: `onecore\ds\security\tokenbroker\pluginmgr\lib\plugreg.cpp`
- `0x18006414b`: `onecore\ds\security\tokenbroker\pluginmgr\lib\plugreg.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall Windows::Internal::Security::Authentication::TokenBroker::PluginRegistration::GetPluginPFN(
        __int64 (__fastcall ***a1)(struct Windows::Security::Credentials::IWebAccountProvider *, GUID *, __int64 *),
        HSTRING *a2)
{
  int v3; // eax
  unsigned int v4; // ebx
  HSTRING v6; // rdi
  HSTRING v7; // rbx
  HSTRING v8; // rsi
  PCWSTR v9; // rax
  int v10; // ecx
  int v11; // r8d
  int v12; // r9d
  int v13; // r14d
  __int64 v14; // rdx
  struct Windows::Internal::Security::Authentication::Web::IWamProviderRegistrationStatics *v15; // r15
  __int64 (__fastcall *v16)(struct Windows::Internal::Security::Authentication::Web::IWamProviderRegistrationStatics *, HSTRING, __int64 *); // r14
  int v17; // r9d
  int v18; // [rsp+20h] [rbp-60h]
  struct Windows::Internal::Security::Authentication::Web::IWamProviderRegistrationStatics *v19; // [rsp+40h] [rbp-40h] BYREF
  HSTRING v20; // [rsp+48h] [rbp-38h] BYREF
  HSTRING v21; // [rsp+50h] [rbp-30h] BYREF
  HSTRING string; // [rsp+58h] [rbp-28h] BYREF
  PCWSTR StringRawBuffer; // [rsp+60h] [rbp-20h] BYREF
  PCWSTR v24; // [rsp+68h] [rbp-18h] BYREF
  int v25[2]; // [rsp+70h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+28h]
  HSTRING v27; // [rsp+C0h] [rbp+40h] BYREF
  __int64 v28; // [rsp+C8h] [rbp+48h] BYREF

  v20 = 0;
  v21 = 0;
  string = 0;
  v3 = Windows::Internal::Security::Authentication::TokenBroker::PluginManager::MapAliasesToPluginId(
         a1,
         &v20,
         &v21,
         &string);
  v4 = v3;
  if ( v3 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x15E,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\pluginmgr\\lib\\plugreg.cpp",
      (const char *)(unsigned int)v3,
      v18);
    if ( string )
      WindowsDeleteString(string);
    if ( v21 )
      WindowsDeleteString(v21);
    if ( v20 )
      WindowsDeleteString(v20);
    return v4;
  }
  v6 = v20;
  v7 = v21;
  v8 = string;
  if ( (unsigned int)dword_180175000 > 4 )
  {
    StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
    if ( WindowsIsStringEmpty(v7) )
      v9 = L"NULL";
    else
      v9 = WindowsGetStringRawBuffer(v7, 0);
    v24 = v9;
    *(_QWORD *)v25 = WindowsGetStringRawBuffer(v6, 0);
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
      v10,
      (unsigned int)byte_1801441C5,
      v11,
      v12,
      (__int64)v25,
      (__int64)&v24,
      (__int64)&StringRawBuffer);
  }
  v27 = 0;
  v19 = 0;
  v28 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v19);
  v13 = _InstantiateProviderRegistrationStatics(&v19);
  if ( v13 >= 0 )
  {
    v15 = v19;
    v16 = *(__int64 (__fastcall **)(struct Windows::Internal::Security::Authentication::Web::IWamProviderRegistrationStatics *, HSTRING, __int64 *))(*(_QWORD *)v19 + 48LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v28);
    v13 = v16(v15, v8, &v28);
    if ( v13 >= 0 )
    {
      v13 = (*(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v28 + 88LL))(v28, &v27);
      if ( v13 >= 0 )
      {
        if ( (unsigned int)dword_180175000 > 5 )
        {
          *(_QWORD *)v25 = WindowsGetStringRawBuffer(v27, 0);
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
            (unsigned int)&dword_180175000,
            (unsigned int)byte_18014418D,
            0,
            v17,
            (__int64)v25);
        }
        *a2 = v27;
        v27 = 0;
        goto LABEL_24;
      }
      v14 = 375;
    }
    else
    {
      v14 = 373;
    }
  }
  else
  {
    v14 = 369;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v14,
    (unsigned int)"onecore\\ds\\security\\tokenbroker\\pluginmgr\\lib\\plugreg.cpp",
    (const char *)(unsigned int)v13,
    v18);
LABEL_24:
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v28);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v19);
  if ( v27 )
    WindowsDeleteString(v27);
  if ( v8 )
    WindowsDeleteString(v8);
  if ( v7 )
    WindowsDeleteString(v7);
  if ( v6 )
    WindowsDeleteString(v6);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x180063ff0  mov     [rsp-28h+arg_0], rbx
0x180063ff5  mov     [rsp-28h+arg_8], rsi
0x180063ffa  push    rbp
0x180063ffb  push    rdi
0x180063ffc  push    r12
0x180063ffe  push    r14
0x180064000  push    r15
0x180064002  mov     rbp, rsp
0x180064005  sub     rsp, 80h
0x18006400c  mov     r12, rdx
0x18006400f  mov     [rbp+var_38], 0
0x180064017  mov     [rbp+var_30], 0
0x18006401f  mov     [rbp+string], 0
0x180064027  lea     r9, [rbp+string]; struct Windows::Internal::String *
0x18006402b  lea     r8, [rbp+var_30]; struct Windows::Internal::String *
0x18006402f  lea     rdx, [rbp+var_38]; struct Windows::Internal::String *
0x180064033  call    ?MapAliasesToPluginId@PluginManager@TokenBroker@Authentication@Security@Internal@Windows@@SAJPEAUIWebAccountProvider@Credentials@46@AEAVString@56@11@Z; Windows::Internal::Security::Authentication::TokenBroker::PluginManager::MapAliasesToPluginId(Windows::Security::Credentials::IWebAccountProvider *,Windows::Internal::String &,Windows::Internal::String &,Windows::Internal::String &)
0x180064038  mov     ebx, eax
0x18006403a  test    eax, eax
0x18006403c  jns     short loc_18006408D
0x18006403e  mov     rcx, [rbp+28h]; this
0x180064042  mov     r9d, eax; char *
0x180064045  lea     r8, aOnecoreDsSecur_48; "onecore\\ds\\security\\tokenbroker\\plu"...
0x18006404c  mov     edx, 15Eh; void *
0x180064051  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180064056  nop
0x180064057  mov     rcx, [rbp+string]; string
0x18006405b  test    rcx, rcx
0x18006405e  jz      short loc_180064067
0x180064060  call    cs:__imp_WindowsDeleteString
0x180064066  nop
0x180064067  mov     rcx, [rbp+var_30]; string
0x18006406b  test    rcx, rcx
0x18006406e  jz      short loc_180064077
0x180064070  call    cs:__imp_WindowsDeleteString
0x180064076  nop
0x180064077  mov     rcx, [rbp+var_38]; string
0x18006407b  test    rcx, rcx
0x18006407e  jz      short loc_180064086
0x180064080  call    cs:__imp_WindowsDeleteString
0x180064086  mov     eax, ebx
0x180064088  jmp     loc_18006424F
0x18006408d  mov     eax, cs:dword_180175000
0x180064093  mov     rdi, [rbp+var_38]
0x180064097  mov     rbx, [rbp+var_30]
0x18006409b  mov     rsi, [rbp+string]
0x18006409f  cmp     eax, 4
0x1800640a2  jbe     short loc_18006410E
0x1800640a4  xor     edx, edx; length
0x1800640a6  mov     rcx, rsi; string
0x1800640a9  call    cs:__imp_WindowsGetStringRawBuffer
0x1800640af  mov     [rbp+var_20], rax
0x1800640b3  mov     rcx, rbx; string
0x1800640b6  call    cs:__imp_WindowsIsStringEmpty
0x1800640bc  test    eax, eax
0x1800640be  jz      short loc_1800640C9
0x1800640c0  lea     rax, aNull_1; "NULL"
0x1800640c7  jmp     short loc_1800640D4
0x1800640c9  xor     edx, edx; length
0x1800640cb  mov     rcx, rbx; string
0x1800640ce  call    cs:__imp_WindowsGetStringRawBuffer
0x1800640d4  mov     [rbp+var_18], rax
0x1800640d8  xor     edx, edx; length
0x1800640da  mov     rcx, rdi; string
0x1800640dd  call    cs:__imp_WindowsGetStringRawBuffer
0x1800640e3  mov     qword ptr [rbp+var_10], rax
0x1800640e7  lea     rax, [rbp+var_20]
0x1800640eb  mov     [rsp+80h+var_50], rax
0x1800640f0  lea     rax, [rbp+var_18]
0x1800640f4  mov     [rsp+80h+var_58], rax
0x1800640f9  lea     rax, [rbp+var_10]
0x1800640fd  mov     qword ptr [rsp+80h+var_60], rax; int
0x180064102  lea     rdx, byte_1801441C5
0x180064109  call    ??$Write@U?$_tlgWrapSz@G@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x18006410e  mov     [rbp+arg_10], 0
0x180064116  mov     [rbp+var_40], 0
0x18006411e  mov     [rbp+arg_18], 0
0x180064126  lea     rcx, [rbp+var_40]
0x18006412a  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18006412f  lea     rcx, [rbp+var_40]; struct Windows::Internal::Security::Authentication::Web::IWamProviderRegistrationStatics **
0x180064133  call    ?_InstantiateProviderRegistrationStatics@@YAJPEAPEAUIWamProviderRegistrationStatics@Web@Authentication@Security@Internal@Windows@@@Z; _InstantiateProviderRegistrationStatics(Windows::Internal::Security::Authentication::Web::IWamProviderRegistrationStatics * *)
0x180064138  mov     r14d, eax
0x18006413b  test    eax, eax
0x18006413d  jns     short loc_18006415C
0x18006413f  mov     edx, 171h; void *
0x180064144  mov     rcx, [rbp+28h]; this
0x180064148  mov     r9d, r14d; char *
0x18006414b  lea     r8, aOnecoreDsSecur_48; "onecore\\ds\\security\\tokenbroker\\plu"...
0x180064152  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180064157  jmp     loc_1800641FC
0x18006415c  mov     r15, [rbp+var_40]
0x180064160  mov     rax, [r15]
0x180064163  mov     r14, [rax+30h]
0x180064167  lea     rcx, [rbp+arg_18]
0x18006416b  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180064170  lea     r8, [rbp+arg_18]
0x180064174  mov     rdx, rsi
0x180064177  mov     rcx, r15
0x18006417a  mov     rax, r14
0x18006417d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180064182  mov     r14d, eax
0x180064185  test    eax, eax
0x180064187  jns     short loc_180064190
0x180064189  mov     edx, 175h
0x18006418e  jmp     short loc_180064144
0x180064190  mov     rcx, [rbp+arg_18]
0x180064194  mov     rax, [rcx]
0x180064197  lea     rdx, [rbp+arg_10]
0x18006419b  mov     rax, [rax+58h]
0x18006419f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800641a4  mov     r14d, eax
0x1800641a7  test    eax, eax
0x1800641a9  jns     short loc_1800641B2
0x1800641ab  mov     edx, 177h
0x1800641b0  jmp     short loc_180064144
0x1800641b2  mov     eax, cs:dword_180175000
0x1800641b8  cmp     eax, 5
0x1800641bb  jbe     short loc_1800641EC
0x1800641bd  xor     edx, edx; length
0x1800641bf  mov     rcx, [rbp+arg_10]; string
0x1800641c3  call    cs:__imp_WindowsGetStringRawBuffer
0x1800641c9  mov     qword ptr [rbp+var_10], rax
0x1800641cd  lea     rax, [rbp+var_10]
0x1800641d1  mov     qword ptr [rsp+80h+var_60], rax
0x1800641d6  xor     r8d, r8d
0x1800641d9  lea     rdx, byte_18014418D
0x1800641e0  lea     rcx, dword_180175000
0x1800641e7  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x1800641ec  mov     rax, [rbp+arg_10]
0x1800641f0  mov     [r12], rax
0x1800641f4  mov     [rbp+arg_10], 0
0x1800641fc  lea     rcx, [rbp+arg_18]
0x180064200  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180064205  nop
0x180064206  lea     rcx, [rbp+var_40]
0x18006420a  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18006420f  nop
0x180064210  mov     rcx, [rbp+arg_10]; string
0x180064214  test    rcx, rcx
0x180064217  jz      short loc_180064220
0x180064219  call    cs:__imp_WindowsDeleteString
0x18006421f  nop
0x180064220  test    rsi, rsi
0x180064223  jz      short loc_18006422F
0x180064225  mov     rcx, rsi; string
0x180064228  call    cs:__imp_WindowsDeleteString
0x18006422e  nop
0x18006422f  test    rbx, rbx
0x180064232  jz      short loc_18006423E
0x180064234  mov     rcx, rbx; string
0x180064237  call    cs:__imp_WindowsDeleteString
0x18006423d  nop
0x18006423e  test    rdi, rdi
0x180064241  jz      short loc_18006424C
0x180064243  mov     rcx, rdi; string
0x180064246  call    cs:__imp_WindowsDeleteString
0x18006424c  mov     eax, r14d
0x18006424f  lea     r11, [rsp+80h+var_s0]
0x180064257  mov     rbx, [r11+30h]
0x18006425b  mov     rsi, [r11+38h]
0x18006425f  mov     rsp, r11
0x180064262  pop     r15
0x180064264  pop     r14
0x180064266  pop     r12
0x180064268  pop     rdi
0x180064269  pop     rbp
0x18006426a  retn
```
