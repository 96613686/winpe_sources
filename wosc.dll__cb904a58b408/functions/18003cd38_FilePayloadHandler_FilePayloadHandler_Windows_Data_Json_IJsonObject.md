# FilePayloadHandler::FilePayloadHandler(Windows::Data::Json::IJsonObject *)

- ea: `0x18003cd38`
- end: `0x18003d1b3`
- name: `??0FilePayloadHandler@@QEAA@PEAUIJsonObject@Json@Data@Windows@@@Z`
- size: `1147`
- prototype: `FilePayloadHandler *__fastcall(FilePayloadHandler *__hidden this, struct Windows::Data::Json::IJsonObject *)`
- caller_count: `1`
- callee_count: `22`
- tags: `reparse_path, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18003c8e4`

## callees

- `0x180003110`
- `0x180003c88`
- `0x18000a1f0`
- `0x18000a250`
- `0x18000b0bc`
- `0x1800101e0`
- `0x1800101fc`
- `0x180010278`
- `0x180011b20`
- `0x18001472c`
- `0x180014f30`
- `0x180019ed8`
- `0x180019fb0`
- `0x180020748`
- `0x18002b254`
- `0x18003cd38`
- `0x18003ddec`
- `0x18003df48`
- `0x18003e104`
- `0x18003e938`
- `0x180042404`
- `0x180059010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003ced4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003cfb8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003cfde`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003d067`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003ced4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003cfb8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003cfde`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003d067`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18003cf42`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18003cf82`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18003cf42`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18003cf82`
- `api-ms-win-core-path-l1-1-0!PathCchCanonicalize` at `0x18003cee9`
- `api-ms-win-core-path-l1-1-0!PathCchCanonicalize` at `0x18003cee9`

## string_xrefs

- `0x18003d1a1`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18003cf13`: `The specified OneSettings Payload directory is not known (%ws)`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
FilePayloadHandler *__fastcall FilePayloadHandler::FilePayloadHandler(
        FilePayloadHandler *this,
        struct Windows::Data::Json::IJsonObject *a2)
{
  char *v4; // r15
  char *v5; // r13
  char *v6; // r12
  __int64 (__fastcall *v7)(struct Windows::Data::Json::IJsonObject *, __int64, HSTRING *); // rbx
  int v8; // eax
  __int64 (__fastcall *v9)(struct Windows::Data::Json::IJsonObject *, __int64, HSTRING *); // rbx
  int v10; // eax
  const WCHAR *StringRawBuffer; // rbx
  HRESULT v12; // eax
  char IsDirectoryKnown; // al
  __int64 v14; // rbx
  __int64 v15; // rdx
  const char *v16; // r9
  const char *v17; // r9
  __int64 v18; // rbx
  __int64 v19; // r8
  PCWSTR v20; // rax
  __int64 v21; // rax
  int (__fastcall *v22)(struct Windows::Data::Json::IJsonObject *, __int64, HSTRING *); // rbx
  const unsigned __int16 *v23; // rdx
  __int64 v24; // rax
  __int64 FlightTypeFromMetadata; // rax
  __int64 v26; // rax
  int v28; // [rsp+20h] [rbp-E0h]
  LPWSTR lpDst; // [rsp+40h] [rbp-C0h] BYREF
  HSTRING v30; // [rsp+48h] [rbp-B8h] BYREF
  HSTRING v31; // [rsp+50h] [rbp-B0h] BYREF
  HSTRING string; // [rsp+58h] [rbp-A8h] BYREF
  int v33; // [rsp+60h] [rbp-A0h]
  FilePayloadHandler *v34; // [rsp+68h] [rbp-98h]
  HSTRING_HEADER hstringHeader; // [rsp+70h] [rbp-90h] BYREF
  __int64 v36; // [rsp+88h] [rbp-78h]
  WCHAR pszPathOut[264]; // [rsp+90h] [rbp-70h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2E8h] [rbp+1E8h]

  v34 = this;
  v33 = 0;
  *(_QWORD *)this = &FilePayloadHandler::`vftable';
  v4 = (char *)this + 8;
  *(_OWORD *)((char *)this + 8) = 0;
  *((_QWORD *)this + 3) = 0;
  *((_QWORD *)this + 4) = 7;
  *((_WORD *)this + 4) = 0;
  *(_OWORD *)((char *)this + 40) = 0;
  *((_QWORD *)this + 7) = 0;
  *((_QWORD *)this + 8) = 7;
  *((_WORD *)this + 20) = 0;
  *(_OWORD *)((char *)this + 72) = 0;
  *((_QWORD *)this + 11) = 0;
  *((_QWORD *)this + 12) = 7;
  *((_WORD *)this + 36) = 0;
  *(_OWORD *)((char *)this + 104) = 0;
  *((_QWORD *)this + 15) = 0;
  *((_QWORD *)this + 16) = 7;
  *((_WORD *)this + 52) = 0;
  v5 = (char *)this + 136;
  *(_OWORD *)((char *)this + 136) = 0;
  *((_QWORD *)this + 19) = 0;
  *((_QWORD *)this + 20) = 7;
  *((_WORD *)this + 68) = 0;
  v6 = (char *)this + 168;
  *(_OWORD *)((char *)this + 168) = 0;
  *((_QWORD *)this + 23) = 0;
  *((_QWORD *)this + 24) = 7;
  *((_WORD *)this + 84) = 0;
  string = 0;
  v7 = *(__int64 (__fastcall **)(struct Windows::Data::Json::IJsonObject *, __int64, HSTRING *))(*(_QWORD *)a2 + 80LL);
  wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(
    &string,
    0);
  v36 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"Dir", 4u, 3u);
  v8 = v7(a2, v36, &string);
  if ( v8 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x25,
      (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\payloadhandlers\\filepayloadhandler.cpp",
      (const char *)(unsigned int)v8,
      v28);
  v30 = 0;
  v9 = *(__int64 (__fastcall **)(struct Windows::Data::Json::IJsonObject *, __int64, HSTRING *))(*(_QWORD *)a2 + 80LL);
  wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(
    &v30,
    0);
  v36 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"Name", 5u, 4u);
  v10 = v9(a2, v36, &v30);
  if ( v10 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x29,
      (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\payloadhandlers\\filepayloadhandler.cpp",
      (const char *)(unsigned int)v10,
      v28);
  memset_0(pszPathOut, 0, 0x208u);
  StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
  v12 = PathCchCanonicalize(pszPathOut, 0x104u, StringRawBuffer);
  if ( v12 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x31,
      (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\payloadhandlers\\filepayloadhandler.cpp",
      (const char *)(unsigned int)v12,
      v28);
  IsDirectoryKnown = FilePayloadHandler::IsDirectoryKnown(pszPathOut);
  wil::details::in1diag3::Throw_HrIfFalseMsg(
    retaddr,
    (void *)0x33,
    (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\payloadhandlers\\filepayloadhandler.cpp",
    (const char *)0x80070005LL,
    IsDirectoryKnown,
    (bool)"The specified OneSettings Payload directory is not known (%ws)",
    (const char *)StringRawBuffer);
  v14 = ExpandEnvironmentStringsW(pszPathOut, 0, 0);
  wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
    &lpDst,
    v15,
    v14);
  v33 = 2;
  if ( !lpDst )
    wil::details::in1diag3::_Throw_NullAlloc(
      retaddr,
      (void *)0xFF8,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      v16);
  if ( !ExpandEnvironmentStringsW(pszPathOut, lpDst, v14) )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x40,
      (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\payloadhandlers\\filepayloadhandler.cpp",
      v17);
  v18 = -1;
  v19 = -1;
  do
    ++v19;
  while ( lpDst[v19] );
  std::wstring::_Assign<unsigned short>(v4, lpDst);
  v20 = WindowsGetStringRawBuffer(v30, 0);
  do
    ++v18;
  while ( v20[v18] );
  std::wstring::_Assign<unsigned short>((char *)this + 40, v20);
  WindowsGetStringRawBuffer(v30, 0);
  v21 = FilePayloadHandler::CreateFullPath(&hstringHeader, lpDst);
  std::wstring::operator=((char *)this + 72, v21);
  std::wstring::_Tidy_deallocate(&hstringHeader);
  v31 = 0;
  v22 = *(int (__fastcall **)(struct Windows::Data::Json::IJsonObject *, __int64, HSTRING *))(*(_QWORD *)a2 + 80LL);
  wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(
    &v31,
    0);
  v36 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"NameBackup", 0xBu, 0xAu);
  if ( v22(a2, v36, &v31) >= 0 )
  {
    WindowsGetStringRawBuffer(v31, 0);
    v24 = FilePayloadHandler::CreateFullPath(&hstringHeader, lpDst);
    std::wstring::operator=((char *)this + 104, v24);
    std::wstring::_Tidy_deallocate(&hstringHeader);
  }
  wil::CreateDirectoryDeep((wil *)lpDst, v23);
  FlightTypeFromMetadata = GetFlightTypeFromMetadata(&hstringHeader, a2);
  std::wstring::operator=(v5, FlightTypeFromMetadata);
  std::wstring::_Tidy_deallocate(&hstringHeader);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_OneSettingsClient_PushNotificationPayload>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_OneSettingsClient_PushNotificationPayload>::GetImpl'::`2'::impl) )
  {
    v26 = FilePayloadHandler::CreateCnsPathName(this, &hstringHeader);
    std::wstring::operator=(v6, v26);
    std::wstring::_Tidy_deallocate(&hstringHeader);
  }
  wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&v31);
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&lpDst);
  wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&v30);
  wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&string);
  return this;
}

```

## disassembly

```asm
0x18003cd38  mov     [rsp-8+arg_10], rbx
0x18003cd3d  push    rbp
0x18003cd3e  push    rsi
0x18003cd3f  push    rdi
0x18003cd40  push    r12
0x18003cd42  push    r13
0x18003cd44  push    r14
0x18003cd46  push    r15
0x18003cd48  lea     rbp, [rsp-1B0h]
0x18003cd50  sub     rsp, 2B0h
0x18003cd57  mov     rax, cs:__security_cookie
0x18003cd5e  xor     rax, rsp
0x18003cd61  mov     [rbp+1E0h+var_40], rax
0x18003cd68  mov     rdi, rdx
0x18003cd6b  mov     rsi, rcx
0x18003cd6e  mov     [rsp+2E0h+var_278], rcx
0x18003cd73  xor     r14d, r14d
0x18003cd76  mov     [rsp+2E0h+var_280], r14d
0x18003cd7b  lea     rax, ??_7FilePayloadHandler@@6B@; const FilePayloadHandler::`vftable'
0x18003cd82  mov     [rcx], rax
0x18003cd85  lea     r15, [rcx+8]
0x18003cd89  xorps   xmm0, xmm0
0x18003cd8c  movups  xmmword ptr [r15], xmm0
0x18003cd90  mov     [r15+10h], r14
0x18003cd94  lea     edx, [r14+7]
0x18003cd98  mov     [r15+18h], rdx
0x18003cd9c  mov     [r15], r14w
0x18003cda0  movups  xmmword ptr [rcx+28h], xmm0
0x18003cda4  mov     [rcx+38h], r14
0x18003cda8  mov     [rcx+40h], rdx
0x18003cdac  mov     [rcx+28h], r14w
0x18003cdb1  movups  xmmword ptr [rcx+48h], xmm0
0x18003cdb5  mov     [rcx+58h], r14
0x18003cdb9  mov     [rcx+60h], rdx
0x18003cdbd  mov     [rcx+48h], r14w
0x18003cdc2  movups  xmmword ptr [rcx+68h], xmm0
0x18003cdc6  mov     [rcx+78h], r14
0x18003cdca  mov     [rcx+80h], rdx
0x18003cdd1  mov     [rcx+68h], r14w
0x18003cdd6  lea     r13, [rcx+88h]
0x18003cddd  movups  xmmword ptr [r13+0], xmm0
0x18003cde2  mov     [r13+10h], r14
0x18003cde6  mov     [r13+18h], rdx
0x18003cdea  mov     [r13+0], r14w
0x18003cdef  lea     r12, [rcx+0A8h]
0x18003cdf6  movups  xmmword ptr [r12], xmm0
0x18003cdfb  mov     [r12+10h], r14
0x18003ce00  mov     [r12+18h], rdx
0x18003ce05  mov     [r12], r14w
0x18003ce0a  mov     [rsp+2E0h+string], r14
0x18003ce0f  mov     rax, [rdi]
0x18003ce12  mov     rbx, [rax+50h]
0x18003ce16  xor     edx, edx
0x18003ce18  lea     rcx, [rsp+2E0h+string]
0x18003ce1d  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHSTRING__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(HSTRING__ *)
0x18003ce22  mov     [rbp+1E0h+var_258], r14
0x18003ce26  lea     r9d, [r14+3]; unsigned int
0x18003ce2a  lea     r8d, [r14+4]; unsigned int
0x18003ce2e  lea     rdx, aDir; "Dir"
0x18003ce35  lea     rcx, [rsp+2E0h+hstringHeader]; hstringHeader
0x18003ce3a  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18003ce3f  nop
0x18003ce40  lea     r8, [rsp+2E0h+string]
0x18003ce45  mov     rdx, [rbp+1E0h+var_258]
0x18003ce49  mov     rcx, rdi
0x18003ce4c  mov     rax, rbx
0x18003ce4f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ce54  mov     rcx, [rbp+1E8h]; this
0x18003ce5b  test    eax, eax
0x18003ce5d  js      loc_18003D162
0x18003ce63  mov     [rsp+2E0h+var_298], r14
0x18003ce68  mov     rax, [rdi]
0x18003ce6b  mov     rbx, [rax+50h]
0x18003ce6f  xor     edx, edx
0x18003ce71  lea     rcx, [rsp+2E0h+var_298]
0x18003ce76  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHSTRING__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(HSTRING__ *)
0x18003ce7b  mov     [rbp+1E0h+var_258], r14
0x18003ce7f  lea     r9d, [r14+4]; unsigned int
0x18003ce83  lea     r8d, [r14+5]; unsigned int
0x18003ce87  lea     rdx, aName; "Name"
0x18003ce8e  lea     rcx, [rsp+2E0h+hstringHeader]; hstringHeader
0x18003ce93  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18003ce98  nop
0x18003ce99  lea     r8, [rsp+2E0h+var_298]
0x18003ce9e  mov     rdx, [rbp+1E0h+var_258]
0x18003cea2  mov     rcx, rdi
0x18003cea5  mov     rax, rbx
0x18003cea8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003cead  mov     rcx, [rbp+1E8h]; this
0x18003ceb4  test    eax, eax
0x18003ceb6  js      loc_18003D177
0x18003cebc  xor     edx, edx; Val
0x18003cebe  mov     r8d, 208h; Size
0x18003cec4  lea     rcx, [rbp+1E0h+pszPathOut]; void *
0x18003cec8  call    memset_0
0x18003cecd  xor     edx, edx; length
0x18003cecf  mov     rcx, [rsp+2E0h+string]; string
0x18003ced4  call    cs:__imp_WindowsGetStringRawBuffer
0x18003ceda  mov     rbx, rax
0x18003cedd  mov     r8, rax; pszPathIn
0x18003cee0  mov     edx, 104h; cchPathOut
0x18003cee5  lea     rcx, [rbp+1E0h+pszPathOut]; pszPathOut
0x18003cee9  call    cs:__imp_PathCchCanonicalize
0x18003ceef  mov     rcx, [rbp+1E8h]; this
0x18003cef6  test    eax, eax
0x18003cef8  js      loc_18003D18C
0x18003cefe  lea     rcx, [rbp+1E0h+pszPathOut]; unsigned __int16 *
0x18003cf02  call    ?IsDirectoryKnown@FilePayloadHandler@@CA_NPEBG@Z; FilePayloadHandler::IsDirectoryKnown(ushort const *)
0x18003cf07  mov     rcx, [rbp+1E8h]; this
0x18003cf0e  mov     [rsp+2E0h+var_2B0], rbx; char *
0x18003cf13  lea     rdx, aTheSpecifiedOn; "The specified OneSettings Payload direc"...
0x18003cf1a  mov     qword ptr [rsp+2E0h+var_2B8], rdx; bool
0x18003cf1f  mov     [rsp+2E0h+var_2C0], al; char
0x18003cf23  mov     r9d, 80070005h; char *
0x18003cf29  lea     r8, aOnecoreBaseFli_9; "onecore\\base\\flighting\\onesettings\\"...
0x18003cf30  lea     edx, [r14+33h]; void *
0x18003cf34  call    ?Throw_HrIfFalseMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfFalseMsg(void *,uint,char const *,long,bool,char const *,...)
0x18003cf39  xor     r8d, r8d; nSize
0x18003cf3c  xor     edx, edx; lpDst
0x18003cf3e  lea     rcx, [rbp+1E0h+pszPathOut]; lpSrc
0x18003cf42  call    cs:__imp_ExpandEnvironmentStringsW
0x18003cf48  mov     ebx, eax
0x18003cf4a  mov     r8d, eax
0x18003cf4d  lea     rcx, [rsp+2E0h+lpDst]
0x18003cf52  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x18003cf57  mov     [rsp+2E0h+var_280], 2
0x18003cf5f  mov     rcx, [rbp+1E8h]; this
0x18003cf66  mov     rdx, [rsp+2E0h+lpDst]; lpDst
0x18003cf6b  test    rdx, rdx
0x18003cf6e  jz      loc_18003D1A1
0x18003cf74  mov     r14, [rbp+1E8h]
0x18003cf7b  mov     r8d, ebx; nSize
0x18003cf7e  lea     rcx, [rbp+1E0h+pszPathOut]; lpSrc
0x18003cf82  call    cs:__imp_ExpandEnvironmentStringsW
0x18003cf88  test    eax, eax
0x18003cf8a  jz      loc_18003D14D
0x18003cf90  mov     rdx, [rsp+2E0h+lpDst]
0x18003cf95  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18003cf99  mov     r8, rbx
0x18003cf9c  xor     r14d, r14d
0x18003cf9f  inc     r8
0x18003cfa2  cmp     [rdx+r8*2], r14w
0x18003cfa7  jnz     short loc_18003CF9F
0x18003cfa9  mov     rcx, r15
0x18003cfac  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x18003cfb1  xor     edx, edx; length
0x18003cfb3  mov     rcx, [rsp+2E0h+var_298]; string
0x18003cfb8  call    cs:__imp_WindowsGetStringRawBuffer
0x18003cfbe  inc     rbx
0x18003cfc1  cmp     [rax+rbx*2], r14w
0x18003cfc6  jnz     short loc_18003CFBE
0x18003cfc8  mov     r8, rbx
0x18003cfcb  mov     rdx, rax
0x18003cfce  lea     rcx, [rsi+28h]
0x18003cfd2  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x18003cfd7  xor     edx, edx; length
0x18003cfd9  mov     rcx, [rsp+2E0h+var_298]; string
0x18003cfde  call    cs:__imp_WindowsGetStringRawBuffer
0x18003cfe4  mov     r8, rax
0x18003cfe7  mov     rdx, [rsp+2E0h+lpDst]
0x18003cfec  lea     rcx, [rsp+2E0h+hstringHeader]
0x18003cff1  call    ?CreateFullPath@FilePayloadHandler@@CA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBG0@Z; FilePayloadHandler::CreateFullPath(ushort const *,ushort const *)
0x18003cff6  mov     rdx, rax
0x18003cff9  lea     rcx, [rsi+48h]
0x18003cffd  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18003d002  lea     rcx, [rsp+2E0h+hstringHeader]
0x18003d007  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003d00c  mov     [rsp+2E0h+var_290], r14
0x18003d011  mov     rax, [rdi]
0x18003d014  mov     rbx, [rax+50h]
0x18003d018  xor     edx, edx
0x18003d01a  lea     rcx, [rsp+2E0h+var_290]
0x18003d01f  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHSTRING__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(HSTRING__ *)
0x18003d024  mov     [rbp+1E0h+var_258], r14
0x18003d028  mov     r9d, 0Ah; unsigned int
0x18003d02e  lea     r8d, [r9+1]; unsigned int
0x18003d032  lea     rdx, aNamebackup; "NameBackup"
0x18003d039  lea     rcx, [rsp+2E0h+hstringHeader]; hstringHeader
0x18003d03e  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18003d043  nop
0x18003d044  lea     r8, [rsp+2E0h+var_290]
0x18003d049  mov     rdx, [rbp+1E0h+var_258]
0x18003d04d  mov     rcx, rdi
0x18003d050  mov     rax, rbx
0x18003d053  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d058  nop
0x18003d059  shr     eax, 1Fh
0x18003d05c  xor     al, 1
0x18003d05e  jz      short loc_18003D095
0x18003d060  xor     edx, edx; length
0x18003d062  mov     rcx, [rsp+2E0h+var_290]; string
0x18003d067  call    cs:__imp_WindowsGetStringRawBuffer
0x18003d06d  mov     r8, rax
0x18003d070  mov     rdx, [rsp+2E0h+lpDst]
0x18003d075  lea     rcx, [rsp+2E0h+hstringHeader]
0x18003d07a  call    ?CreateFullPath@FilePayloadHandler@@CA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBG0@Z; FilePayloadHandler::CreateFullPath(ushort const *,ushort const *)
0x18003d07f  mov     rdx, rax
0x18003d082  lea     rcx, [rsi+68h]
0x18003d086  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18003d08b  lea     rcx, [rsp+2E0h+hstringHeader]
0x18003d090  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003d095  mov     rcx, [rsp+2E0h+lpDst]; this
0x18003d09a  call    ?CreateDirectoryDeep@wil@@YAXPEBG@Z; wil::CreateDirectoryDeep(ushort const *)
0x18003d09f  mov     rdx, rdi
0x18003d0a2  lea     rcx, [rsp+2E0h+hstringHeader]
0x18003d0a7  call    ?GetFlightTypeFromMetadata@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAUIJsonObject@Json@Data@Windows@@@Z; GetFlightTypeFromMetadata(Windows::Data::Json::IJsonObject *)
0x18003d0ac  mov     rdx, rax
0x18003d0af  mov     rcx, r13
0x18003d0b2  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18003d0b7  lea     rcx, [rsp+2E0h+hstringHeader]
0x18003d0bc  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003d0c1  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_OneSettingsClient_PushNotificationPayload@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_OneSettingsClient_PushNotificationPayload@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_OneSettingsClient_PushNotificationPayload> `wil::Feature<__WilFeatureTraits_Feature_OneSettingsClient_PushNotificationPayload>::GetImpl(void)'::`2'::impl
0x18003d0c8  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_OneSettingsClient_PushNotificationPayload@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_OneSettingsClient_PushNotificationPayload>::__private_IsEnabled(wil::ReportingKind)
0x18003d0cd  test    al, al
0x18003d0cf  jz      short loc_18003D0F4
0x18003d0d1  lea     rdx, [rsp+2E0h+hstringHeader]
0x18003d0d6  mov     rcx, rsi
0x18003d0d9  call    ?CreateCnsPathName@FilePayloadHandler@@AEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; FilePayloadHandler::CreateCnsPathName(void)
0x18003d0de  mov     rdx, rax
0x18003d0e1  mov     rcx, r12
0x18003d0e4  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18003d0e9  lea     rcx, [rsp+2E0h+hstringHeader]
0x18003d0ee  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003d0f3  nop
0x18003d0f4  lea     rcx, [rsp+2E0h+var_290]
0x18003d0f9  call    ??1?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(void)
0x18003d0fe  nop
0x18003d0ff  lea     rcx, [rsp+2E0h+lpDst]
0x18003d104  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18003d109  nop
0x18003d10a  lea     rcx, [rsp+2E0h+var_298]
0x18003d10f  call    ??1?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(void)
0x18003d114  nop
0x18003d115  lea     rcx, [rsp+2E0h+string]
0x18003d11a  call    ??1?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(void)
0x18003d11f  nop
0x18003d120  mov     rax, rsi
0x18003d123  mov     rcx, [rbp+1E0h+var_40]
0x18003d12a  xor     rcx, rsp; StackCookie
0x18003d12d  call    __security_check_cookie
0x18003d132  mov     rbx, [rsp+2E0h+arg_10]
0x18003d13a  add     rsp, 2B0h
0x18003d141  pop     r15
0x18003d143  pop     r14
0x18003d145  pop     r13
0x18003d147  pop     r12
0x18003d149  pop     rdi
0x18003d14a  pop     rsi
0x18003d14b  pop     rbp
0x18003d14c  retn
0x18003d14d  lea     r8, aOnecoreBaseFli_9; "onecore\\base\\flighting\\onesettings\\"...
0x18003d154  mov     edx, 40h ; '@'; void *
0x18003d159  mov     rcx, r14; this
0x18003d15c  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x18003d162  mov     r9d, eax; char *
0x18003d165  lea     r8, aOnecoreBaseFli_9; "onecore\\base\\flighting\\onesettings\\"...
0x18003d16c  mov     edx, 25h ; '%'; void *
0x18003d171  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18003d177  mov     r9d, eax; char *
0x18003d17a  lea     r8, aOnecoreBaseFli_9; "onecore\\base\\flighting\\onesettings\\"...
0x18003d181  mov     edx, 29h ; ')'; void *
0x18003d186  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18003d18c  mov     r9d, eax; char *
0x18003d18f  lea     r8, aOnecoreBaseFli_9; "onecore\\base\\flighting\\onesettings\\"...
0x18003d196  mov     edx, 31h ; '1'; void *
0x18003d19b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18003d1a1  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18003d1a8  mov     edx, 0FF8h; void *
0x18003d1ad  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
```
