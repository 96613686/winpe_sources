# Microsoft::Bing::LanguageUnderstanding::Client::ClientContextCreator::SetClientContextGroup(std::shared_ptr<Bing::Speech::ClientContext> &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &,Windows::Data::Json::IJsonValue *)

- ea: `0x1801d7330`
- end: `0x1801d7958`
- name: `?SetClientContextGroup@ClientContextCreator@Client@LanguageUnderstanding@Bing@Microsoft@@CAJAEAV?$shared_ptr@VClientContext@Speech@Bing@@@std@@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@7@PEAUIJsonValue@Json@Data@Windows@@@Z`
- size: `1576`
- prototype: ``
- caller_count: `1`
- callee_count: `24`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180028994`

## callees

- `0x180021944`
- `0x180026508`
- `0x180029860`
- `0x18002ae70`
- `0x18002b750`
- `0x18002d404`
- `0x18002f130`
- `0x180030738`
- `0x1800316e0`
- `0x18003c550`
- `0x18004bb40`
- `0x180079e30`
- `0x1801a658c`
- `0x1801d50a4`
- `0x1801d5470`
- `0x1801d57f0`
- `0x1801d5e7c`
- `0x1801d6338`
- `0x1801d6450`
- `0x1801d70a8`
- `0x1801d7268`
- `0x1801d7330`
- `0x180268698`
- `0x18028b010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801d7490`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801d7555`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801d764f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801d77a6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801d77cb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801d7811`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801d78a6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801d7490`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801d7555`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801d764f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801d77a6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801d77cb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801d7811`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801d78a6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801d74bc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801d7581`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801d767b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801d74bc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801d7581`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801d767b`

## pseudocode

```c
// Hidden C++ exception states: #wind=16
__int64 __fastcall Microsoft::Bing::LanguageUnderstanding::Client::ClientContextCreator::SetClientContextGroup(
        _QWORD *a1,
        __int64 a2,
        __int64 a3)
{
  int v6; // eax
  unsigned int v7; // ebx
  int v8; // eax
  __int64 v9; // rdx
  __int64 v10; // rdi
  __int64 (__fastcall *v11)(__int64, __int64 *); // rbx
  int v12; // eax
  __int64 v13; // rdi
  __int64 (__fastcall *v14)(__int64, HSTRING *); // rbx
  int v15; // eax
  PCWSTR StringRawBuffer; // rax
  __int64 v17; // rdi
  __int64 (__fastcall *v18)(__int64, __int64 **); // rbx
  int v19; // eax
  __int64 *v20; // rdi
  __int64 v21; // rax
  __int64 (__fastcall *v22)(__int64 *, HSTRING *); // rbx
  int v23; // eax
  PCWSTR v24; // rax
  __int64 v25; // r8
  __int64 (__fastcall *v26)(__int64 *, HSTRING *); // rbx
  PCWSTR v27; // rax
  __int64 v28; // r8
  _QWORD *v29; // rbx
  __int64 v30; // rcx
  __int64 v31; // r8
  __int64 v32; // rdx
  __int64 v33; // r8
  __int64 v34; // rdx
  __int64 v35; // r8
  _QWORD *v36; // rdx
  __int64 v37; // r8
  int v38; // eax
  __int64 v39; // rdx
  __int64 v40; // rdx
  _QWORD *v41; // rax
  int v43; // [rsp+20h] [rbp-E0h] BYREF
  HSTRING string; // [rsp+28h] [rbp-D8h] BYREF
  HSTRING v45; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v46; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v47; // [rsp+40h] [rbp-C0h] BYREF
  __int64 *v48; // [rsp+48h] [rbp-B8h] BYREF
  int v49; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v50; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v51; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v52[16]; // [rsp+68h] [rbp-98h] BYREF
  _QWORD v53[3]; // [rsp+78h] [rbp-88h] BYREF
  unsigned __int64 v54; // [rsp+90h] [rbp-70h]
  _BYTE v55[40]; // [rsp+98h] [rbp-68h] BYREF
  _BYTE v56[32]; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v57[16]; // [rsp+E0h] [rbp-20h] BYREF
  _BYTE v58[8]; // [rsp+F0h] [rbp-10h] BYREF
  Bing::Speech::ClientContextItem *v59; // [rsp+F8h] [rbp-8h]
  Bing::Speech::ClientContextItem *v60; // [rsp+100h] [rbp+0h]
  _BYTE v61[32]; // [rsp+110h] [rbp+10h] BYREF
  _BYTE v62[16]; // [rsp+130h] [rbp+30h] BYREF
  _BYTE v63[24]; // [rsp+140h] [rbp+40h] BYREF
  _BYTE v64[24]; // [rsp+158h] [rbp+58h] BYREF
  _BYTE v65[32]; // [rsp+170h] [rbp+70h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1C8h] [rbp+C8h]

  Bing::Speech::ClientContextGroup::ClientContextGroup(v56);
  v51 = a3;
  Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncActionCompletedHandler>::InternalAddRef(&v51);
  v50 = 0;
  v6 = Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonValue>::As<Windows::Data::Json::IJsonObject>(&v51, &v50);
  v7 = v6;
  if ( v6 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xC3,
      (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\rnl\\src\\clientcontextcreator.cpp",
      (const char *)(unsigned int)v6,
      v43);
    goto LABEL_50;
  }
  v46 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v46);
  v8 = Speech::JsonHelpers::Iterator(v50, &v46);
  v7 = v8;
  if ( v8 < 0 )
  {
    v9 = 198;
    goto LABEL_5;
  }
  LOBYTE(v43) = 0;
  v8 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v46 + 56LL))(v46, &v43);
  v7 = v8;
  if ( v8 < 0 )
  {
    v9 = 200;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\rnl\\src\\clientcontextcreator.cpp",
      (const char *)(unsigned int)v8,
      v43);
LABEL_6:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v46);
    goto LABEL_50;
  }
  while ( (_BYTE)v43 )
  {
    v47 = 0;
    v10 = v46;
    v11 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v46 + 48LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v47);
    v12 = v11(v10, &v47);
    v7 = v12;
    if ( v12 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xCD,
        (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\rnl\\src\\clientcontextcreator.cpp",
        (const char *)(unsigned int)v12,
        v43);
      goto LABEL_48;
    }
    string = 0;
    v13 = v47;
    v14 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v47 + 48LL);
    WindowsDeleteString(0);
    string = 0;
    v15 = v14(v13, &string);
    v7 = v15;
    if ( v15 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xD0,
        (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\rnl\\src\\clientcontextcreator.cpp",
        (const char *)(unsigned int)v15,
        v43);
      goto LABEL_46;
    }
    StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
    std::wstring::wstring(v55, StringRawBuffer);
    v48 = 0;
    v17 = v47;
    v18 = *(__int64 (__fastcall **)(__int64, __int64 **))(*(_QWORD *)v47 + 56LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v48);
    v19 = v18(v17, &v48);
    v7 = v19;
    if ( v19 < 0 )
    {
      v40 = 212;
      goto LABEL_43;
    }
    v49 = 0;
    v19 = (*(__int64 (__fastcall **)(__int64 *, int *))(*v48 + 48))(v48, &v49);
    v7 = v19;
    if ( v19 < 0 )
    {
      v40 = 215;
LABEL_43:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v40,
        (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\rnl\\src\\clientcontextcreator.cpp",
        (const char *)(unsigned int)v19,
        v43);
      goto LABEL_44;
    }
    v45 = 0;
    std::wstring::wstring(v53);
    v20 = v48;
    v21 = *v48;
    if ( v49 == 3 )
    {
      v22 = *(__int64 (__fastcall **)(__int64 *, HSTRING *))(v21 + 64);
      WindowsDeleteString(v45);
      v45 = 0;
      v23 = v22(v20, &v45);
      v7 = v23;
      if ( v23 < 0 )
      {
        v39 = 222;
LABEL_37:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v39,
          (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\rnl\\src\\clientcontextcreator.cpp",
          (const char *)(unsigned int)v23,
          v43);
        goto LABEL_38;
      }
      v24 = WindowsGetStringRawBuffer(v45, 0);
      v25 = -1;
      do
        ++v25;
      while ( v24[v25] );
      std::wstring::_Assign<unsigned short>(v53, v24, v25);
      Halsey::HalseyStringUtil::Replace(v53, L"\\", L"\\\\");
      Halsey::HalseyStringUtil::Replace(v53, L"\n", L"\\n");
      Halsey::HalseyStringUtil::Replace(v53, L"\r", L"\\r");
      Halsey::HalseyStringUtil::Replace(v53, L"\t", L"\\t");
      Halsey::HalseyStringUtil::Replace(v53, &dword_1802E28B4, L"\\f");
      Halsey::HalseyStringUtil::Replace(v53, L"\b", L"\\b");
      Halsey::HalseyStringUtil::Replace(v53, L"\"", L"\\\"");
    }
    else
    {
      v26 = *(__int64 (__fastcall **)(__int64 *, HSTRING *))(v21 + 56);
      WindowsDeleteString(v45);
      v45 = 0;
      v23 = v26(v20, &v45);
      v7 = v23;
      if ( v23 < 0 )
      {
        v39 = 236;
        goto LABEL_37;
      }
      v27 = WindowsGetStringRawBuffer(v45, 0);
      v28 = -1;
      do
        ++v28;
      while ( v27[v28] );
      std::wstring::_Assign<unsigned short>(v53, v27, v28);
    }
    v29 = v53;
    if ( v54 > 7 )
      v29 = (_QWORD *)v53[0];
    v30 = *(_QWORD *)std::map<std::wstring,std::wstring>::_Try_emplace<std::wstring const &,>(v57, v52, v55) + 64LL;
    v31 = -1;
    do
      ++v31;
    while ( *((_WORD *)v29 + v31) );
    std::wstring::_Assign<unsigned short>(v30, v29, v31);
    std::wstring::wstring(v61);
    std::map<std::wstring,std::wstring>::map<std::wstring,std::wstring>(v62);
    std::vector<std::unique_ptr<DGGInfo::SPDGGITEM>>::vector<std::unique_ptr<DGGInfo::SPDGGITEM>>(v63, v32, v33);
    std::vector<std::unique_ptr<DGGInfo::SPDGGITEM>>::vector<std::unique_ptr<DGGInfo::SPDGGITEM>>(v64, v34, v35);
    std::wstring::wstring(v65);
    std::wstring::operator=(v61, v55);
    v36 = v53;
    if ( v54 > 7 )
      v36 = (_QWORD *)v53[0];
    v37 = -1;
    do
      ++v37;
    while ( *((_WORD *)v36 + v37) );
    std::wstring::_Assign<unsigned short>(v65, v36, v37);
    if ( v59 == v60 )
    {
      std::vector<Bing::Speech::ClientContextItem>::_Emplace_reallocate<Bing::Speech::ClientContextItem const &>(
        v58,
        v59,
        v61);
    }
    else
    {
      Bing::Speech::ClientContextItem::ClientContextItem(v59, (const struct Bing::Speech::ClientContextItem *)v61);
      v59 = (Bing::Speech::ClientContextItem *)((char *)v59 + 128);
    }
    v38 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v46 + 64LL))(v46, &v43);
    v7 = v38;
    if ( v38 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xF7,
        (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\rnl\\src\\clientcontextcreator.cpp",
        (const char *)(unsigned int)v38,
        v43);
      Bing::Speech::ClientContextItem::~ClientContextItem((Bing::Speech::ClientContextItem *)v61);
LABEL_38:
      std::wstring::_Tidy_deallocate(v53);
      WindowsDeleteString(v45);
      v45 = 0;
LABEL_44:
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v48);
      std::wstring::_Tidy_deallocate(v55);
LABEL_46:
      WindowsDeleteString(string);
      string = 0;
LABEL_48:
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v47);
      goto LABEL_6;
    }
    Bing::Speech::ClientContextItem::~ClientContextItem((Bing::Speech::ClientContextItem *)v61);
    std::wstring::_Tidy_deallocate(v53);
    WindowsDeleteString(v45);
    v45 = 0;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v48);
    std::wstring::_Tidy_deallocate(v55);
    WindowsDeleteString(string);
    string = 0;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v47);
  }
  v41 = (_QWORD *)std::map<std::wstring,Bing::Speech::ClientContextGroup>::_Try_emplace<std::wstring const &,>(
                    *a1,
                    v52,
                    a2);
  Bing::Speech::ClientContextGroup::operator=(*v41 + 64LL, v56);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v46);
  v7 = 0;
LABEL_50:
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v50);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v51);
  Bing::Speech::ClientContextGroup::~ClientContextGroup((Bing::Speech::ClientContextGroup *)v56);
  return v7;
}

```

## disassembly

```asm
0x1801d7330  mov     [rsp-8+arg_10], rbx
0x1801d7335  mov     [rsp-8+arg_18], rsi
0x1801d733a  push    rbp
0x1801d733b  push    rdi
0x1801d733c  push    r12
0x1801d733e  push    r14
0x1801d7340  push    r15
0x1801d7342  lea     rbp, [rsp-0A0h]
0x1801d734a  sub     rsp, 1A0h
0x1801d7351  mov     rax, cs:__security_cookie
0x1801d7358  xor     rax, rsp
0x1801d735b  mov     [rbp+0C0h+var_30], rax
0x1801d7362  mov     rbx, r8
0x1801d7365  mov     rsi, rdx
0x1801d7368  mov     r14, rcx
0x1801d736b  lea     rcx, [rbp+0C0h+var_100]
0x1801d736f  call    ??0ClientContextGroup@Speech@Bing@@QEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Bing::Speech::ClientContextGroup::ClientContextGroup(std::wstring const &)
0x1801d7374  nop
0x1801d7375  mov     [rsp+1C0h+var_160], rbx
0x1801d737a  lea     rcx, [rsp+1C0h+var_160]
0x1801d737f  call    ?InternalAddRef@?$ComPtr@UIAsyncActionCompletedHandler@Foundation@Windows@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncActionCompletedHandler>::InternalAddRef(void)
0x1801d7384  nop
0x1801d7385  xor     r15d, r15d
0x1801d7388  mov     [rsp+1C0h+var_168], r15
0x1801d738d  lea     rdx, [rsp+1C0h+var_168]
0x1801d7392  lea     rcx, [rsp+1C0h+var_160]
0x1801d7397  call    ??$As@UIJsonObject@Json@Data@Windows@@@?$ComPtr@UIJsonValue@Json@Data@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonValue>::As<Windows::Data::Json::IJsonObject>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>>)
0x1801d739c  mov     ebx, eax
0x1801d739e  test    eax, eax
0x1801d73a0  jns     short loc_1801D73C2
0x1801d73a2  mov     rcx, [rbp+0C8h]; this
0x1801d73a9  mov     r9d, eax; char *
0x1801d73ac  lea     r8, aOnecoreuapEndu_16; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x1801d73b3  mov     edx, 0C3h; void *
0x1801d73b8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801d73bd  jmp     loc_1801D790C
0x1801d73c2  mov     [rsp+1C0h+var_188], r15
0x1801d73c7  lea     rcx, [rsp+1C0h+var_188]
0x1801d73cc  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801d73d1  lea     rdx, [rsp+1C0h+var_188]
0x1801d73d6  mov     rcx, [rsp+1C0h+var_168]
0x1801d73db  call    ?Iterator@JsonHelpers@Speech@@SAJPEAUIJsonObject@Json@Data@Windows@@PEAPEAU?$IIterator@PEAU?$IKeyValuePair@PEAUHSTRING__@@PEAUIJsonValue@Json@Data@Windows@@@Collections@Foundation@Windows@@@Collections@Foundation@6@@Z; Speech::JsonHelpers::Iterator(Windows::Data::Json::IJsonObject *,Windows::Foundation::Collections::IIterator<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,Windows::Data::Json::IJsonValue *> *> * *)
0x1801d73e0  mov     ebx, eax
0x1801d73e2  test    eax, eax
0x1801d73e4  jns     short loc_1801D7411
0x1801d73e6  mov     edx, 0C6h; void *
0x1801d73eb  lea     r8, aOnecoreuapEndu_16; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x1801d73f2  mov     r9d, eax; char *
0x1801d73f5  mov     rcx, [rbp+0C8h]; this
0x1801d73fc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801d7401  nop
0x1801d7402  lea     rcx, [rsp+1C0h+var_188]
0x1801d7407  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801d740c  jmp     loc_1801D790C
0x1801d7411  mov     byte ptr [rsp+1C0h+var_1A0], r15b; int
0x1801d7416  mov     rcx, [rsp+1C0h+var_188]
0x1801d741b  mov     rax, [rcx]
0x1801d741e  lea     rdx, [rsp+1C0h+var_1A0]
0x1801d7423  mov     rax, [rax+38h]
0x1801d7427  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801d742c  mov     ebx, eax
0x1801d742e  test    eax, eax
0x1801d7430  jns     short loc_1801D7439
0x1801d7432  mov     edx, 0C8h
0x1801d7437  jmp     short loc_1801D73EB
0x1801d7439  or      r12, 0FFFFFFFFFFFFFFFFh
0x1801d743d  cmp     byte ptr [rsp+1C0h+var_1A0], r15b
0x1801d7442  jz      loc_1801D78DE
0x1801d7448  mov     [rsp+1C0h+var_180], r15
0x1801d744d  mov     rdi, [rsp+1C0h+var_188]
0x1801d7452  mov     rax, [rdi]
0x1801d7455  mov     rbx, [rax+30h]
0x1801d7459  lea     rcx, [rsp+1C0h+var_180]
0x1801d745e  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801d7463  lea     rdx, [rsp+1C0h+var_180]
0x1801d7468  mov     rcx, rdi
0x1801d746b  mov     rax, rbx
0x1801d746e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801d7473  mov     ebx, eax
0x1801d7475  test    eax, eax
0x1801d7477  js      loc_1801D78B3
0x1801d747d  mov     [rsp+1C0h+string], r15
0x1801d7482  mov     rdi, [rsp+1C0h+var_180]
0x1801d7487  mov     rax, [rdi]
0x1801d748a  mov     rbx, [rax+30h]
0x1801d748e  xor     ecx, ecx; string
0x1801d7490  call    cs:__imp_WindowsDeleteString
0x1801d7496  mov     [rsp+1C0h+string], r15
0x1801d749b  lea     rdx, [rsp+1C0h+string]
0x1801d74a0  mov     rcx, rdi
0x1801d74a3  mov     rax, rbx
0x1801d74a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801d74ab  mov     ebx, eax
0x1801d74ad  test    eax, eax
0x1801d74af  js      loc_1801D7885
0x1801d74b5  xor     edx, edx; length
0x1801d74b7  mov     rcx, [rsp+1C0h+string]; string
0x1801d74bc  call    cs:__imp_WindowsGetStringRawBuffer
0x1801d74c2  mov     rdx, rax
0x1801d74c5  lea     rcx, [rbp+0C0h+var_128]
0x1801d74c9  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1801d74ce  nop
0x1801d74cf  mov     [rsp+1C0h+var_178], r15
0x1801d74d4  mov     rdi, [rsp+1C0h+var_180]
0x1801d74d9  mov     rax, [rdi]
0x1801d74dc  mov     rbx, [rax+38h]
0x1801d74e0  lea     rcx, [rsp+1C0h+var_178]
0x1801d74e5  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801d74ea  lea     rdx, [rsp+1C0h+var_178]
0x1801d74ef  mov     rcx, rdi
0x1801d74f2  mov     rax, rbx
0x1801d74f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801d74fa  mov     ebx, eax
0x1801d74fc  test    eax, eax
0x1801d74fe  js      loc_1801D7853
0x1801d7504  mov     [rsp+1C0h+var_170], r15d
0x1801d7509  mov     rcx, [rsp+1C0h+var_178]
0x1801d750e  mov     rax, [rcx]
0x1801d7511  lea     rdx, [rsp+1C0h+var_170]
0x1801d7516  mov     rax, [rax+30h]
0x1801d751a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801d751f  mov     ebx, eax
0x1801d7521  test    eax, eax
0x1801d7523  js      loc_1801D784C
0x1801d7529  mov     [rsp+1C0h+var_190], r15
0x1801d752e  lea     rcx, [rsp+1C0h+var_148]
0x1801d7533  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1801d7538  nop
0x1801d7539  mov     rdi, [rsp+1C0h+var_178]
0x1801d753e  mov     rcx, [rsp+1C0h+var_190]; string
0x1801d7543  mov     rax, [rdi]
0x1801d7546  cmp     [rsp+1C0h+var_170], 3
0x1801d754b  jnz     loc_1801D764B
0x1801d7551  mov     rbx, [rax+40h]
0x1801d7555  call    cs:__imp_WindowsDeleteString
0x1801d755b  mov     [rsp+1C0h+var_190], r15
0x1801d7560  lea     rdx, [rsp+1C0h+var_190]
0x1801d7565  mov     rcx, rdi
0x1801d7568  mov     rax, rbx
0x1801d756b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801d7570  mov     ebx, eax
0x1801d7572  test    eax, eax
0x1801d7574  js      loc_1801D77E5
0x1801d757a  xor     edx, edx; length
0x1801d757c  mov     rcx, [rsp+1C0h+var_190]; string
0x1801d7581  call    cs:__imp_WindowsGetStringRawBuffer
0x1801d7587  mov     r8, r12
0x1801d758a  inc     r8
0x1801d758d  cmp     [rax+r8*2], r15w
0x1801d7592  jnz     short loc_1801D758A
0x1801d7594  mov     rdx, rax
0x1801d7597  lea     rcx, [rsp+1C0h+var_148]
0x1801d759c  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x1801d75a1  lea     r8, asc_1802C26DC; "\\\\"
0x1801d75a8  lea     rdx, SubBlock; "\\"
0x1801d75af  lea     rcx, [rsp+1C0h+var_148]
0x1801d75b4  call    ?Replace@HalseyStringUtil@Halsey@@SAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBG1@Z; Halsey::HalseyStringUtil::Replace(std::wstring &,ushort const *,ushort const *)
0x1801d75b9  lea     r8, aN; "\\n"
0x1801d75c0  lea     rdx, asc_1802B2110; "\n"
0x1801d75c7  lea     rcx, [rsp+1C0h+var_148]
0x1801d75cc  call    ?Replace@HalseyStringUtil@Halsey@@SAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBG1@Z; Halsey::HalseyStringUtil::Replace(std::wstring &,ushort const *,ushort const *)
0x1801d75d1  lea     r8, aR_1; "\\r"
0x1801d75d8  lea     rdx, asc_1802E27F8; "\r"
0x1801d75df  lea     rcx, [rsp+1C0h+var_148]
0x1801d75e4  call    ?Replace@HalseyStringUtil@Halsey@@SAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBG1@Z; Halsey::HalseyStringUtil::Replace(std::wstring &,ushort const *,ushort const *)
0x1801d75e9  lea     r8, aT_0; "\\t"
0x1801d75f0  lea     rdx, asc_1802E28C0; "\t"
0x1801d75f7  lea     rcx, [rsp+1C0h+var_148]
0x1801d75fc  call    ?Replace@HalseyStringUtil@Halsey@@SAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBG1@Z; Halsey::HalseyStringUtil::Replace(std::wstring &,ushort const *,ushort const *)
0x1801d7601  lea     r8, asc_1802E28B8; "\\f"
0x1801d7608  lea     rdx, dword_1802E28B4
0x1801d760f  lea     rcx, [rsp+1C0h+var_148]
0x1801d7614  call    ?Replace@HalseyStringUtil@Halsey@@SAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBG1@Z; Halsey::HalseyStringUtil::Replace(std::wstring &,ushort const *,ushort const *)
0x1801d7619  lea     r8, aB_0; "\\b"
0x1801d7620  lea     rdx, asc_1802E28A8; "\b"
0x1801d7627  lea     rcx, [rsp+1C0h+var_148]
0x1801d762c  call    ?Replace@HalseyStringUtil@Halsey@@SAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBG1@Z; Halsey::HalseyStringUtil::Replace(std::wstring &,ushort const *,ushort const *)
0x1801d7631  lea     r8, asc_1802E28A0; "\\\""
0x1801d7638  lea     rdx, asc_1802C6644; "\""
0x1801d763f  lea     rcx, [rsp+1C0h+var_148]
0x1801d7644  call    ?Replace@HalseyStringUtil@Halsey@@SAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBG1@Z; Halsey::HalseyStringUtil::Replace(std::wstring &,ushort const *,ushort const *)
0x1801d7649  jmp     short loc_1801D769B
0x1801d764b  mov     rbx, [rax+38h]
0x1801d764f  call    cs:__imp_WindowsDeleteString
0x1801d7655  mov     [rsp+1C0h+var_190], r15
0x1801d765a  lea     rdx, [rsp+1C0h+var_190]
0x1801d765f  mov     rcx, rdi
0x1801d7662  mov     rax, rbx
0x1801d7665  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801d766a  mov     ebx, eax
0x1801d766c  test    eax, eax
0x1801d766e  js      loc_1801D7845
0x1801d7674  xor     edx, edx; length
0x1801d7676  mov     rcx, [rsp+1C0h+var_190]; string
0x1801d767b  call    cs:__imp_WindowsGetStringRawBuffer
0x1801d7681  mov     r8, r12
0x1801d7684  inc     r8
0x1801d7687  cmp     [rax+r8*2], r15w
0x1801d768c  jnz     short loc_1801D7684
0x1801d768e  mov     rdx, rax
0x1801d7691  lea     rcx, [rsp+1C0h+var_148]
0x1801d7696  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x1801d769b  lea     rbx, [rsp+1C0h+var_148]
0x1801d76a0  cmp     [rbp+0C0h+var_130], 7
0x1801d76a5  cmova   rbx, [rsp+1C0h+var_148]
0x1801d76ab  lea     r8, [rbp+0C0h+var_128]
0x1801d76af  lea     rdx, [rsp+1C0h+var_158]
0x1801d76b4  lea     rcx, [rbp+0C0h+var_E0]
0x1801d76b8  call    ??$_Try_emplace@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$$V@?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@PEAX@std@@_N@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::map<std::wstring,std::wstring>::_Try_emplace<std::wstring const &,>(std::wstring const &)
0x1801d76bd  mov     rcx, [rax]
0x1801d76c0  add     rcx, 40h ; '@'
0x1801d76c4  mov     r8, r12
0x1801d76c7  inc     r8
0x1801d76ca  cmp     [rbx+r8*2], r15w
0x1801d76cf  jnz     short loc_1801D76C7
0x1801d76d1  mov     rdx, rbx
0x1801d76d4  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x1801d76d9  lea     rcx, [rbp+0C0h+var_B0]
0x1801d76dd  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1801d76e2  nop
0x1801d76e3  lea     rcx, [rbp+0C0h+var_90]
0x1801d76e7  call    ??0?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@QEAA@XZ; std::map<std::wstring,std::wstring>::map<std::wstring,std::wstring>(void)
0x1801d76ec  nop
0x1801d76ed  lea     rcx, [rbp+0C0h+var_80]
0x1801d76f1  call    ??0?$vector@V?$unique_ptr@USPDGGITEM@DGGInfo@@U?$default_delete@USPDGGITEM@DGGInfo@@@std@@@std@@V?$allocator@V?$unique_ptr@USPDGGITEM@DGGInfo@@U?$default_delete@USPDGGITEM@DGGInfo@@@std@@@std@@@2@@std@@QEAA@XZ; std::vector<std::unique_ptr<DGGInfo::SPDGGITEM>>::vector<std::unique_ptr<DGGInfo::SPDGGITEM>>(void)
0x1801d76f6  nop
0x1801d76f7  lea     rcx, [rbp+0C0h+var_68]
0x1801d76fb  call    ??0?$vector@V?$unique_ptr@USPDGGITEM@DGGInfo@@U?$default_delete@USPDGGITEM@DGGInfo@@@std@@@std@@V?$allocator@V?$unique_ptr@USPDGGITEM@DGGInfo@@U?$default_delete@USPDGGITEM@DGGInfo@@@std@@@std@@@2@@std@@QEAA@XZ; std::vector<std::unique_ptr<DGGInfo::SPDGGITEM>>::vector<std::unique_ptr<DGGInfo::SPDGGITEM>>(void)
0x1801d7700  nop
0x1801d7701  lea     rcx, [rbp+0C0h+var_50]
0x1801d7705  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1801d770a  nop
0x1801d770b  lea     rdx, [rbp+0C0h+var_128]
0x1801d770f  lea     rcx, [rbp+0C0h+var_B0]
0x1801d7713  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x1801d7718  nop
0x1801d7719  lea     rdx, [rsp+1C0h+var_148]
0x1801d771e  cmp     [rbp+0C0h+var_130], 7
0x1801d7723  cmova   rdx, [rsp+1C0h+var_148]
0x1801d7729  mov     r8, r12
0x1801d772c  inc     r8
0x1801d772f  cmp     [rdx+r8*2], r15w
0x1801d7734  jnz     short loc_1801D772C
0x1801d7736  lea     rcx, [rbp+0C0h+var_50]
0x1801d773a  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x1801d773f  mov     rax, [rbp+0C0h+var_C8]
0x1801d7743  cmp     rax, [rbp+0C0h+var_C0]
0x1801d7747  jz      short loc_1801D775C
0x1801d7749  lea     rdx, [rbp+0C0h+var_B0]; struct Bing::Speech::ClientContextItem *
0x1801d774d  mov     rcx, rax; this
0x1801d7750  call    ??0ClientContextItem@Speech@Bing@@QEAA@AEBV012@@Z; Bing::Speech::ClientContextItem::ClientContextItem(Bing::Speech::ClientContextItem const &)
0x1801d7755  sub     [rbp+0C0h+var_C8], 0FFFFFFFFFFFFFF80h
0x1801d775a  jmp     short loc_1801D776C
0x1801d775c  lea     r8, [rbp+0C0h+var_B0]
0x1801d7760  mov     rdx, rax
0x1801d7763  lea     rcx, [rbp+0C0h+var_D0]
0x1801d7767  call    ??$_Emplace_reallocate@AEBVClientContextItem@Speech@Bing@@@?$vector@VClientContextItem@Speech@Bing@@V?$allocator@VClientContextItem@Speech@Bing@@@std@@@std@@AEAAPEAVClientContextItem@Speech@Bing@@QEAV234@AEBV234@@Z; std::vector<Bing::Speech::ClientContextItem>::_Emplace_reallocate<Bing::Speech::ClientContextItem const &>(Bing::Speech::ClientContextItem * const,Bing::Speech::ClientContextItem const &)
0x1801d776c  mov     rcx, [rsp+1C0h+var_188]
0x1801d7771  mov     rax, [rcx]
0x1801d7774  lea     rdx, [rsp+1C0h+var_1A0]
0x1801d7779  mov     rax, [rax+40h]
0x1801d777d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801d7782  mov     ebx, eax
0x1801d7784  test    eax, eax
0x1801d7786  js      loc_1801D781E
0x1801d778c  lea     rcx, [rbp+0C0h+var_B0]; this
0x1801d7790  call    ??1ClientContextItem@Speech@Bing@@QEAA@XZ; Bing::Speech::ClientContextItem::~ClientContextItem(void)
0x1801d7795  nop
0x1801d7796  lea     rcx, [rsp+1C0h+var_148]
0x1801d779b  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1801d77a0  nop
0x1801d77a1  mov     rcx, [rsp+1C0h+var_190]; string
0x1801d77a6  call    cs:__imp_WindowsDeleteString
0x1801d77ac  mov     [rsp+1C0h+var_190], r15
0x1801d77b1  lea     rcx, [rsp+1C0h+var_178]
0x1801d77b6  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801d77bb  nop
0x1801d77bc  lea     rcx, [rbp+0C0h+var_128]
0x1801d77c0  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1801d77c5  nop
0x1801d77c6  mov     rcx, [rsp+1C0h+string]; string
0x1801d77cb  call    cs:__imp_WindowsDeleteString
0x1801d77d1  mov     [rsp+1C0h+string], r15
0x1801d77d6  lea     rcx, [rsp+1C0h+var_180]
0x1801d77db  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801d77e0  jmp     loc_1801D743D
0x1801d77e5  mov     edx, 0DEh; void *
0x1801d77ea  lea     r8, aOnecoreuapEndu_16; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x1801d77f1  mov     r9d, eax; char *
0x1801d77f4  mov     rcx, [rbp+0C8h]; this
0x1801d77fb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801d7800  nop
0x1801d7801  lea     rcx, [rsp+1C0h+var_148]
0x1801d7806  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1801d780b  nop
0x1801d780c  mov     rcx, [rsp+1C0h+var_190]; string
0x1801d7811  call    cs:__imp_WindowsDeleteString
0x1801d7817  mov     [rsp+1C0h+var_190], r15
0x1801d781c  jmp     short loc_1801D786F
0x1801d781e  mov     rcx, [rbp+0C8h]; this
  ... truncated ...
```
