# LogCommandManager::GetLogCommandPayload(ushort * *)

- ea: `0x1800812c4`
- end: `0x1800815c6`
- name: `?GetLogCommandPayload@LogCommandManager@@QEAAJPEAPEAG@Z`
- size: `770`
- prototype: `__int64 __fastcall(LogCommandManager *__hidden this, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800437dc`

## callees

- `0x180007440`
- `0x18000ba54`
- `0x18000fe0c`
- `0x180036de8`
- `0x180044fa8`
- `0x18007e4b8`
- `0x180080464`
- `0x18008050c`
- `0x1800805ac`
- `0x1800805fc`
- `0x1800807c4`
- `0x1800812c4`
- `0x180096010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180081471`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180081471`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800813a5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800813a5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18008150f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18008150f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800814be`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008156d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800814be`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008156d`

## string_xrefs

- `0x18008135c`: `Windows.Data.Json.JsonValue`
- `0x18008130a`: `Windows.Data.Json.JsonObject`
- `0x180081339`: `onecoreuap\base\diagnosis\platform\notifications\prov\common\logcommandmanager.cpp`
- `0x18008138c`: `onecoreuap\base\diagnosis\platform\notifications\prov\common\logcommandmanager.cpp`
- `0x1800813ec`: `onecoreuap\base\diagnosis\platform\notifications\prov\common\logcommandmanager.cpp`
- `0x180081441`: `onecoreuap\base\diagnosis\platform\notifications\prov\common\logcommandmanager.cpp`
- `0x18008149a`: `onecoreuap\base\diagnosis\platform\notifications\prov\common\logcommandmanager.cpp`
- `0x1800814e8`: `onecoreuap\base\diagnosis\platform\notifications\prov\common\logcommandmanager.cpp`
- `0x180081535`: `onecoreuap\base\diagnosis\platform\notifications\prov\common\logcommandmanager.cpp`

## pseudocode

```c
__int64 __fastcall LogCommandManager::GetLogCommandPayload(LogCommandManager *this, unsigned __int16 **a2)
{
  int v4; // eax
  int v5; // eax
  struct _RTL_CRITICAL_SECTION *v6; // r14
  int v7; // eax
  __int64 v8; // rsi
  __int64 (__fastcall *v9)(__int64, _QWORD, __int64); // rdi
  __int64 v10; // rbx
  __int64 v11; // rax
  int v12; // eax
  __int64 v13; // rdx
  __int64 v14; // r8
  __int64 v15; // r9
  __int64 v16; // rdx
  __int64 v17; // r8
  __int64 v18; // r9
  int v19; // eax
  __int64 v20; // rdi
  __int64 (__fastcall *v21)(__int64, HSTRING *); // rbx
  int v22; // eax
  const unsigned __int16 *StringRawBuffer; // rax
  int v24; // eax
  unsigned __int16 *Reserved1; // rax
  __int64 v26; // rdx
  __int64 v27; // r8
  __int64 v28; // r9
  __int64 v29; // rdx
  __int64 v30; // r8
  __int64 v31; // r9
  __int64 v32; // rdx
  __int64 v33; // r8
  __int64 v34; // r9
  HSTRING string; // [rsp+20h] [rbp-88h] BYREF
  __int64 v37; // [rsp+28h] [rbp-80h] BYREF
  __int64 v38; // [rsp+30h] [rbp-78h] BYREF
  __int64 v39; // [rsp+38h] [rbp-70h] BYREF
  __int64 v40; // [rsp+40h] [rbp-68h] BYREF
  _QWORD v41[2]; // [rsp+48h] [rbp-60h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+58h] [rbp-50h] BYREF
  __int64 v43; // [rsp+70h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+0h]

  *a2 = 0;
  v37 = 0;
  v43 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.Data.Json.JsonObject",
    0x1Du,
    0x1Cu);
  v4 = Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>>(v43, &v37);
  if ( v4 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x6F,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\common\\logcommandmanager.cpp",
      (const char *)(unsigned int)v4,
      (int)string);
  v41[0] = 0;
  v43 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.Data.Json.JsonValue",
    0x1Cu,
    0x1Bu);
  v5 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonValueStatics>>(
         v43,
         v41);
  if ( v5 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x72,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\common\\logcommandmanager.cpp",
      (const char *)(unsigned int)v5,
      (int)string);
  v6 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 16);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  v41[1] = (char *)this + 16;
  if ( *((_BYTE *)this + 57) )
  {
    LogCommandManager::BuildPrecommandPayload(&v40, (__int64)this + 56);
    v38 = 0;
    v7 = Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>::As<Windows::Data::Json::IJsonValue>(&v40, &v38);
    if ( v7 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x7B,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\common\\logcommandmanager.cpp",
        (const char *)(unsigned int)v7,
        (int)string);
    v8 = v37;
    v9 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64))(*(_QWORD *)v37 + 56LL);
    v10 = v38;
    v11 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, off_180098390);
    v12 = v9(v8, *(_QWORD *)(v11 + 24), v10);
    if ( v12 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x7C,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\common\\logcommandmanager.cpp",
        (const char *)(unsigned int)v12,
        (int)string);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v38, v13, v14, v15);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v40, v16, v17, v18);
  }
  if ( v6 )
    LeaveCriticalSection(v6);
  v39 = 0;
  v19 = Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>::As<Windows::Data::Json::IJsonValue>(&v37, &v39);
  if ( v19 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x81,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\common\\logcommandmanager.cpp",
      (const char *)(unsigned int)v19,
      (int)string);
  string = 0;
  v20 = v39;
  v21 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v39 + 56LL);
  WindowsDeleteString(0);
  string = 0;
  v22 = v21(v20, &string);
  if ( v22 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x84,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\common\\logcommandmanager.cpp",
      (const char *)(unsigned int)v22,
      (int)string);
  memset(&hstringHeader, 0, sizeof(hstringHeader));
  StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
  v24 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Initialize(
          (__int64)&hstringHeader,
          StringRawBuffer,
          0xFFFFFFFFFFFFFFFFuLL);
  if ( v24 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x87,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\common\\logcommandmanager.cpp",
      (const char *)(unsigned int)v24,
      (int)string);
  Reserved1 = (unsigned __int16 *)hstringHeader.Reserved.Reserved1;
  memset(&hstringHeader, 0, sizeof(hstringHeader));
  *a2 = Reserved1;
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&hstringHeader);
  WindowsDeleteString(string);
  string = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v39, v26, v27, v28);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v41, v29, v30, v31);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v37, v32, v33, v34);
  return 0;
}

```

## disassembly

```asm
0x1800812c4  mov     r11, rsp
0x1800812c7  mov     [r11+18h], rbx
0x1800812cb  push    rsi
0x1800812cc  push    rdi
0x1800812cd  push    r12
0x1800812cf  push    r14
0x1800812d1  push    r15
0x1800812d3  sub     rsp, 80h
0x1800812da  mov     rax, cs:__security_cookie
0x1800812e1  xor     rax, rsp
0x1800812e4  mov     [rsp+0A8h+var_30], rax
0x1800812e9  mov     r15, rdx
0x1800812ec  mov     rbx, rcx
0x1800812ef  xor     r12d, r12d
0x1800812f2  mov     [rdx], r12
0x1800812f5  mov     [r11-80h], r12
0x1800812f9  mov     [r11-38h], r12
0x1800812fd  lea     edi, [r12+1Ch]
0x180081302  mov     r9d, edi; unsigned int
0x180081305  lea     r8d, [r12+1Dh]; unsigned int
0x18008130a  lea     rdx, ?RuntimeClass_Windows_Data_Json_JsonObject@@3QBGB; "Windows.Data.Json.JsonObject"
0x180081311  lea     rcx, [r11-50h]; hstringHeader
0x180081315  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18008131a  nop
0x18008131b  lea     rdx, [rsp+0A8h+var_80]
0x180081320  mov     rcx, [rsp+0A8h+var_38]
0x180081325  call    ??$ActivateInstance@V?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>>)
0x18008132a  mov     rcx, [rsp+0A8h]; this
0x180081332  test    eax, eax
0x180081334  jns     short loc_180081349
0x180081336  mov     r9d, eax; char *
0x180081339  lea     r8, aOnecoreuapBase_31; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180081340  lea     edx, [rdi+53h]; void *
0x180081343  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180081349  mov     [rsp+0A8h+var_60], r12
0x18008134e  mov     [rsp+0A8h+var_38], r12
0x180081353  mov     r9d, 1Bh; unsigned int
0x180081359  mov     r8d, edi; unsigned int
0x18008135c  lea     rdx, ?RuntimeClass_Windows_Data_Json_JsonValue@@3QBGB; "Windows.Data.Json.JsonValue"
0x180081363  lea     rcx, [rsp+0A8h+hstringHeader]; hstringHeader
0x180081368  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18008136d  nop
0x18008136e  lea     rdx, [rsp+0A8h+var_60]
0x180081373  mov     rcx, [rsp+0A8h+var_38]
0x180081378  call    ??$GetActivationFactory@V?$ComPtr@UIJsonValueStatics@Json@Data@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIJsonValueStatics@Json@Data@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonValueStatics>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonValueStatics>>)
0x18008137d  mov     rcx, [rsp+0A8h]; this
0x180081385  test    eax, eax
0x180081387  jns     short loc_18008139E
0x180081389  mov     r9d, eax; char *
0x18008138c  lea     r8, aOnecoreuapBase_31; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180081393  mov     edx, 72h ; 'r'; void *
0x180081398  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18008139e  lea     r14, [rbx+10h]
0x1800813a2  mov     rcx, r14; lpCriticalSection
0x1800813a5  call    cs:__imp_EnterCriticalSection
0x1800813ab  mov     [rsp+0A8h+var_58], r14
0x1800813b0  lea     rdx, [rbx+38h]
0x1800813b4  cmp     [rdx+1], r12b
0x1800813b8  jz      loc_180081469
0x1800813be  lea     rcx, [rsp+0A8h+var_68]
0x1800813c3  call    ?BuildPrecommandPayload@LogCommandManager@@CA?AV?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@AEAUPrecommandScenario@1@@Z; LogCommandManager::BuildPrecommandPayload(LogCommandManager::PrecommandScenario &)
0x1800813c8  nop
0x1800813c9  mov     [rsp+0A8h+var_78], r12
0x1800813ce  lea     rdx, [rsp+0A8h+var_78]
0x1800813d3  lea     rcx, [rsp+0A8h+var_68]
0x1800813d8  call    ??$As@UIJsonValue@Json@Data@Windows@@@?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIJsonValue@Json@Data@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>::As<Windows::Data::Json::IJsonValue>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonValue>>)
0x1800813dd  mov     rcx, [rsp+0A8h]; this
0x1800813e5  test    eax, eax
0x1800813e7  jns     short loc_1800813FD
0x1800813e9  mov     r9d, eax; char *
0x1800813ec  lea     r8, aOnecoreuapBase_31; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800813f3  mov     edx, 7Bh ; '{'; void *
0x1800813f8  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800813fd  mov     rsi, [rsp+0A8h+var_80]
0x180081402  mov     rax, [rsi]
0x180081405  mov     rdi, [rax+38h]
0x180081409  mov     rbx, [rsp+0A8h+var_78]
0x18008140e  lea     rdx, off_180098390; "PrecommandStage"
0x180081415  lea     rcx, [rsp+0A8h+hstringHeader]
0x18008141a  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18008141f  nop
0x180081420  mov     r8, rbx
0x180081423  mov     rdx, [rax+18h]
0x180081427  mov     rcx, rsi
0x18008142a  mov     rax, rdi
0x18008142d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180081432  mov     rcx, [rsp+0A8h]; this
0x18008143a  test    eax, eax
0x18008143c  jns     short loc_180081453
0x18008143e  mov     r9d, eax; char *
0x180081441  lea     r8, aOnecoreuapBase_31; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180081448  mov     edx, 7Ch ; '|'; void *
0x18008144d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180081453  lea     rcx, [rsp+0A8h+var_78]
0x180081458  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18008145d  nop
0x18008145e  lea     rcx, [rsp+0A8h+var_68]
0x180081463  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180081468  nop
0x180081469  test    r14, r14
0x18008146c  jz      short loc_180081477
0x18008146e  mov     rcx, r14; lpCriticalSection
0x180081471  call    cs:__imp_LeaveCriticalSection
0x180081477  mov     [rsp+0A8h+var_70], r12
0x18008147c  lea     rdx, [rsp+0A8h+var_70]
0x180081481  lea     rcx, [rsp+0A8h+var_80]
0x180081486  call    ??$As@UIJsonValue@Json@Data@Windows@@@?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIJsonValue@Json@Data@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>::As<Windows::Data::Json::IJsonValue>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonValue>>)
0x18008148b  mov     rcx, [rsp+0A8h]; this
0x180081493  test    eax, eax
0x180081495  jns     short loc_1800814AB
0x180081497  mov     r9d, eax; char *
0x18008149a  lea     r8, aOnecoreuapBase_31; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800814a1  mov     edx, 81h; void *
0x1800814a6  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800814ab  mov     [rsp+0A8h+string], r12
0x1800814b0  mov     rdi, [rsp+0A8h+var_70]
0x1800814b5  mov     rax, [rdi]
0x1800814b8  mov     rbx, [rax+38h]
0x1800814bc  xor     ecx, ecx; string
0x1800814be  call    cs:__imp_WindowsDeleteString
0x1800814c4  mov     [rsp+0A8h+string], r12; int
0x1800814c9  lea     rdx, [rsp+0A8h+string]
0x1800814ce  mov     rcx, rdi
0x1800814d1  mov     rax, rbx
0x1800814d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800814d9  mov     rcx, [rsp+0A8h]; this
0x1800814e1  test    eax, eax
0x1800814e3  jns     short loc_1800814F9
0x1800814e5  mov     r9d, eax; char *
0x1800814e8  lea     r8, aOnecoreuapBase_31; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800814ef  mov     edx, 84h; void *
0x1800814f4  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800814f9  mov     qword ptr [rsp+0A8h+hstringHeader.Reserved], r12
0x1800814fe  mov     qword ptr [rsp+0A8h+hstringHeader.Reserved+8], r12
0x180081503  mov     qword ptr [rsp+0A8h+hstringHeader.Reserved+10h], r12
0x180081508  xor     edx, edx; length
0x18008150a  mov     rcx, [rsp+0A8h+string]; string
0x18008150f  call    cs:__imp_WindowsGetStringRawBuffer
0x180081515  or      r8, 0FFFFFFFFFFFFFFFFh
0x180081519  mov     rdx, rax
0x18008151c  lea     rcx, [rsp+0A8h+hstringHeader]
0x180081521  call    ?_Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Initialize(ushort const *,unsigned __int64)
0x180081526  mov     rcx, [rsp+0A8h]; this
0x18008152e  test    eax, eax
0x180081530  jns     short loc_180081546
0x180081532  mov     r9d, eax; char *
0x180081535  lea     r8, aOnecoreuapBase_31; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18008153c  mov     edx, 87h; void *
0x180081541  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180081546  mov     rax, qword ptr [rsp+0A8h+hstringHeader.Reserved]
0x18008154b  mov     qword ptr [rsp+0A8h+hstringHeader.Reserved], r12
0x180081550  mov     qword ptr [rsp+0A8h+hstringHeader.Reserved+10h], r12
0x180081555  mov     qword ptr [rsp+0A8h+hstringHeader.Reserved+8], r12
0x18008155a  mov     [r15], rax
0x18008155d  lea     rcx, [rsp+0A8h+hstringHeader]
0x180081562  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180081567  nop
0x180081568  mov     rcx, [rsp+0A8h+string]; string
0x18008156d  call    cs:__imp_WindowsDeleteString
0x180081573  mov     [rsp+0A8h+string], r12
0x180081578  lea     rcx, [rsp+0A8h+var_70]
0x18008157d  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180081582  nop
0x180081583  lea     rcx, [rsp+0A8h+var_60]
0x180081588  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18008158d  nop
0x18008158e  lea     rcx, [rsp+0A8h+var_80]
0x180081593  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180081598  xor     eax, eax
0x18008159a  jmp     short loc_1800815A0
0x18008159c  mov     eax, dword ptr [rsp+0A8h+string]
0x1800815a0  mov     rcx, [rsp+0A8h+var_30]
0x1800815a5  xor     rcx, rsp; StackCookie
0x1800815a8  call    __security_check_cookie
0x1800815ad  mov     rbx, [rsp+0A8h+arg_10]
0x1800815b5  add     rsp, 80h
0x1800815bc  pop     r15
0x1800815be  pop     r14
0x1800815c0  pop     r12
0x1800815c2  pop     rdi
0x1800815c3  pop     rsi
0x1800815c4  retn
```
