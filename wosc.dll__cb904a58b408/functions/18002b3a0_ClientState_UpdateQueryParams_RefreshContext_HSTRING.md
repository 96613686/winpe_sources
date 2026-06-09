# ClientState::UpdateQueryParams(RefreshContext *,HSTRING__ *)

- ea: `0x18002b3a0`
- end: `0x18002b5e4`
- name: `?UpdateQueryParams@ClientState@@AEAAXPEAVRefreshContext@@PEAUHSTRING__@@@Z`
- size: `580`
- prototype: `void __fastcall(ClientState *__hidden this, struct RefreshContext *, HSTRING)`
- caller_count: `2`
- callee_count: `13`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180026928`
- `0x180029cc8`

## callees

- `0x180003110`
- `0x180006b9c`
- `0x180009e38`
- `0x1800101fc`
- `0x180010278`
- `0x180014f30`
- `0x180019ed8`
- `0x180028508`
- `0x18002b3a0`
- `0x18002bde4`
- `0x18002dc84`
- `0x18002e110`
- `0x18002e298`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002b43a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002b457`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002b49f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002b4bc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002b43a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002b457`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002b49f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002b4bc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002b542`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002b542`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002b4f8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002b57e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002b4f8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002b57e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002b50f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002b50f`

## string_xrefs

- `0x18002b5bd`: `onecore\base\flighting\onesettings\libs\configurationsmanager\clientstate.cpp`
- `0x18002b5d1`: `onecore\base\flighting\onesettings\libs\configurationsmanager\clientstate.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall ClientState::UpdateQueryParams(ClientState *this, struct RefreshContext *a2, HSTRING a3)
{
  int v3; // esi
  char IsEnabled; // al
  __int64 v7; // r14
  __int64 v8; // rcx
  bool v9; // zf
  const WCHAR *v10; // rax
  HSTRING_HEADER *v11; // rax
  __int64 OSVersionFromCtacOverride; // rax
  void *v13; // rcx
  WCHAR *v14; // rbx
  const char *v15; // r9
  const unsigned __int16 *StringRawBuffer; // rax
  unsigned int v17; // r9d
  int Sha256Hash; // eax
  void *v19; // rcx
  const char *v20; // r9
  PVOID Reserved1; // [rsp+20h] [rbp-78h]
  int v22; // [rsp+20h] [rbp-78h]
  UINT32 length[2]; // [rsp+40h] [rbp-58h] BYREF
  const WCHAR *v24; // [rsp+48h] [rbp-50h] BYREF
  HSTRING_HEADER v25; // [rsp+50h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+0h]

  v3 = (int)a3;
  IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_WoscNoQueryRegex>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_WoscNoQueryRegex>::GetImpl'::`2'::impl);
  v7 = *((_QWORD *)this + 4);
  v8 = *((_QWORD *)this + 32);
  v9 = IsEnabled == 0;
  v10 = &String1;
  if ( v9 )
  {
    if ( v8 )
      v10 = (const WCHAR *)*((_QWORD *)this + 32);
    v24 = v10;
    v11 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v25, &v24);
    RefreshContext::_GetQueryParamsOld(
      (_DWORD)a2,
      (unsigned int)length,
      *(_QWORD *)a2,
      v3,
      (__int64)v11[1].Reserved.Reserved1,
      v7);
    WindowsDeleteString(*((HSTRING *)this + 30));
    *((_QWORD *)this + 30) = *(_QWORD *)length;
    *(_QWORD *)length = 0;
    WindowsDeleteString(0);
  }
  else
  {
    if ( v8 )
      v10 = (const WCHAR *)*((_QWORD *)this + 32);
    v24 = v10;
    Reserved1 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v25, &v24)[1].Reserved.Reserved1;
    RefreshContext::_GetQueryParams(
      (int)a2,
      (int)length,
      *(_QWORD *)a2,
      v3,
      (__int64)Reserved1,
      (ClientState *)((char *)this + 248),
      v7);
    WindowsDeleteString(*((HSTRING *)this + 30));
    *((_QWORD *)this + 30) = *(_QWORD *)length;
    *(_QWORD *)length = 0;
    WindowsDeleteString(0);
  }
  OSVersionFromCtacOverride = RefreshContext::GetOSVersionFromCtacOverride(a2, &v25);
  std::wstring::operator=((char *)this + 40, OSVersionFromCtacOverride);
  std::wstring::_Tidy_deallocate(&v25);
  v13 = (void *)*((_QWORD *)this + 28);
  *((_QWORD *)this + 28) = 0;
  CoTaskMemFree(v13);
  *((_DWORD *)this + 58) = 0;
  try
  {
    v14 = (WCHAR *)CoTaskMemAlloc(0x20u);
    v24 = v14;
    if ( !v14 )
      wil::details::in1diag3::_Throw_NullAlloc(
        retaddr,
        (void *)0x427,
        (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\configurationsmanager\\clientstate.cpp",
        v15);
    length[0] = 0;
    StringRawBuffer = WindowsGetStringRawBuffer(*((HSTRING *)this + 30), length);
    Sha256Hash = EncryptionHelper::GetSha256Hash(StringRawBuffer, length[0], (unsigned __int8 *)v14, v17);
    if ( Sha256Hash < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x42C,
        (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\configurationsmanager\\clientstate.cpp",
        (const char *)(unsigned int)Sha256Hash,
        v22);
    v24 = 0;
    v19 = (void *)*((_QWORD *)this + 28);
    *((_QWORD *)this + 28) = 0;
    CoTaskMemFree(v19);
    *((_QWORD *)this + 28) = v14;
    *((_DWORD *)this + 58) = 32;
    CCoTaskMemPtr<unsigned char>::~CCoTaskMemPtr<unsigned char>((void **)&v24);
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0x432,
      (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\configurationsmanager\\clientstate.cpp",
      v20);
  }
}

```

## disassembly

```asm
0x18002b3a0  mov     [rsp+arg_18], rbx
0x18002b3a5  push    rsi
0x18002b3a6  push    rdi
0x18002b3a7  push    r14
0x18002b3a9  sub     rsp, 80h
0x18002b3b0  mov     rax, cs:__security_cookie
0x18002b3b7  xor     rax, rsp
0x18002b3ba  mov     [rsp+98h+var_28], rax
0x18002b3bf  mov     rsi, r8
0x18002b3c2  mov     rbx, rdx
0x18002b3c5  mov     rdi, rcx
0x18002b3c8  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_WoscNoQueryRegex@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_WoscNoQueryRegex@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_WoscNoQueryRegex> `wil::Feature<__WilFeatureTraits_Feature_Servicing_WoscNoQueryRegex>::GetImpl(void)'::`2'::impl
0x18002b3cf  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_WoscNoQueryRegex@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_WoscNoQueryRegex>::__private_IsEnabled(void)
0x18002b3d4  mov     r14, [rdi+20h]
0x18002b3d8  mov     rcx, [rdi+100h]
0x18002b3df  lea     rdx, [rsp+98h+var_50]
0x18002b3e4  test    al, al
0x18002b3e6  lea     rax, String1
0x18002b3ed  jz      short loc_18002B460
0x18002b3ef  test    rcx, rcx
0x18002b3f2  cmovnz  rax, rcx
0x18002b3f6  mov     [rsp+98h+var_50], rax
0x18002b3fb  lea     rcx, [rsp+98h+var_48]
0x18002b400  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18002b405  nop
0x18002b406  lea     rcx, [rdi+0F8h]
0x18002b40d  mov     [rsp+98h+var_68], r14; __int64
0x18002b412  mov     [rsp+98h+var_70], rcx; Microsoft::WRL::Wrappers::HString *
0x18002b417  mov     rax, [rax+18h]
0x18002b41b  mov     [rsp+98h+var_78], rax; __int64
0x18002b420  mov     r9, rsi; int
0x18002b423  mov     r8, [rbx]; int
0x18002b426  lea     rdx, [rsp+98h+length]; int
0x18002b42b  mov     rcx, rbx; int
0x18002b42e  call    ?_GetQueryParams@RefreshContext@@AEAA?AVHString@Wrappers@WRL@Microsoft@@PEAUICommonTargetingAttributesFactory@Flighting@Internal@Windows@@PEAUHSTRING__@@1AEAV2345@PEAU?$IMapView@PEAUHSTRING__@@PEAU1@@Collections@Foundation@9@@Z; RefreshContext::_GetQueryParams(Windows::Internal::Flighting::ICommonTargetingAttributesFactory *,HSTRING__ *,HSTRING__ *,Microsoft::WRL::Wrappers::HString &,Windows::Foundation::Collections::IMapView<HSTRING__ *,HSTRING__ *> *)
0x18002b433  mov     rcx, [rdi+0F0h]; string
0x18002b43a  call    cs:__imp_WindowsDeleteString
0x18002b440  mov     rax, qword ptr [rsp+98h+length]
0x18002b445  mov     [rdi+0F0h], rax
0x18002b44c  mov     qword ptr [rsp+98h+length], 0
0x18002b455  xor     ecx, ecx; string
0x18002b457  call    cs:__imp_WindowsDeleteString
0x18002b45d  nop
0x18002b45e  jmp     short loc_18002B4C3
0x18002b460  test    rcx, rcx
0x18002b463  cmovnz  rax, rcx
0x18002b467  mov     [rsp+98h+var_50], rax
0x18002b46c  lea     rcx, [rsp+98h+var_48]
0x18002b471  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18002b476  nop
0x18002b477  mov     [rsp+98h+var_70], r14
0x18002b47c  mov     rax, [rax+18h]
0x18002b480  mov     [rsp+98h+var_78], rax; int
0x18002b485  mov     r9, rsi
0x18002b488  mov     r8, [rbx]
0x18002b48b  lea     rdx, [rsp+98h+length]
0x18002b490  mov     rcx, rbx
0x18002b493  call    ?_GetQueryParamsOld@RefreshContext@@AEAA?AVHString@Wrappers@WRL@Microsoft@@PEAUICommonTargetingAttributesFactory@Flighting@Internal@Windows@@PEAUHSTRING__@@1PEAU?$IMapView@PEAUHSTRING__@@PEAU1@@Collections@Foundation@9@@Z; RefreshContext::_GetQueryParamsOld(Windows::Internal::Flighting::ICommonTargetingAttributesFactory *,HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::IMapView<HSTRING__ *,HSTRING__ *> *)
0x18002b498  mov     rcx, [rdi+0F0h]; string
0x18002b49f  call    cs:__imp_WindowsDeleteString
0x18002b4a5  mov     rax, qword ptr [rsp+98h+length]
0x18002b4aa  mov     [rdi+0F0h], rax
0x18002b4b1  mov     qword ptr [rsp+98h+length], 0
0x18002b4ba  xor     ecx, ecx; string
0x18002b4bc  call    cs:__imp_WindowsDeleteString
0x18002b4c2  nop
0x18002b4c3  lea     rdx, [rsp+98h+var_48]
0x18002b4c8  mov     rcx, rbx
0x18002b4cb  call    ?GetOSVersionFromCtacOverride@RefreshContext@@QEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; RefreshContext::GetOSVersionFromCtacOverride(void)
0x18002b4d0  lea     rcx, [rdi+28h]
0x18002b4d4  mov     rdx, rax
0x18002b4d7  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18002b4dc  lea     rcx, [rsp+98h+var_48]
0x18002b4e1  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002b4e6  mov     rcx, [rdi+0E0h]; pv
0x18002b4ed  mov     qword ptr [rdi+0E0h], 0
0x18002b4f8  call    cs:__imp_CoTaskMemFree
0x18002b4fe  mov     dword ptr [rdi+0E8h], 0
0x18002b508  mov     esi, 20h ; ' '
0x18002b50d  mov     ecx, esi; cb
0x18002b50f  call    cs:__imp_CoTaskMemAlloc
0x18002b515  mov     rbx, rax
0x18002b518  mov     [rsp+98h+var_50], rax
0x18002b51d  mov     rcx, [rsp+98h]; this
0x18002b525  test    rax, rax
0x18002b528  jz      loc_18002B5BD
0x18002b52e  mov     [rsp+98h+length], 0
0x18002b536  lea     rdx, [rsp+98h+length]; length
0x18002b53b  mov     rcx, [rdi+0F0h]; string
0x18002b542  call    cs:__imp_WindowsGetStringRawBuffer
0x18002b548  mov     r8, rbx; unsigned __int8 *
0x18002b54b  mov     edx, [rsp+98h+length]; unsigned int
0x18002b54f  mov     rcx, rax; unsigned __int16 *
0x18002b552  call    ?GetSha256Hash@EncryptionHelper@@SAJPEBGKPEAEK@Z; EncryptionHelper::GetSha256Hash(ushort const *,ulong,uchar *,ulong)
0x18002b557  mov     rcx, [rsp+98h]; this
0x18002b55f  test    eax, eax
0x18002b561  js      short loc_18002B5CE
0x18002b563  mov     [rsp+98h+var_50], 0
0x18002b56c  mov     rcx, [rdi+0E0h]; pv
0x18002b573  mov     qword ptr [rdi+0E0h], 0
0x18002b57e  call    cs:__imp_CoTaskMemFree
0x18002b584  mov     [rdi+0E0h], rbx
0x18002b58b  mov     [rdi+0E8h], esi
0x18002b591  lea     rcx, [rsp+98h+var_50]
0x18002b596  call    ??1?$CCoTaskMemPtr@E@@QEAA@XZ; CCoTaskMemPtr<uchar>::~CCoTaskMemPtr<uchar>(void)
0x18002b59b  nop
0x18002b59c  mov     rcx, [rsp+98h+var_28]
0x18002b5a1  xor     rcx, rsp; StackCookie
0x18002b5a4  call    __security_check_cookie
0x18002b5a9  mov     rbx, [rsp+98h+arg_18]
0x18002b5b1  add     rsp, 80h
0x18002b5b8  pop     r14
0x18002b5ba  pop     rdi
0x18002b5bb  pop     rsi
0x18002b5bc  retn
0x18002b5bd  lea     r8, aOnecoreBaseFli_10; "onecore\\base\\flighting\\onesettings\\"...
0x18002b5c4  mov     edx, 427h; void *
0x18002b5c9  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
0x18002b5ce  mov     r9d, eax; char *
0x18002b5d1  lea     r8, aOnecoreBaseFli_10; "onecore\\base\\flighting\\onesettings\\"...
0x18002b5d8  mov     edx, 42Ch; void *
0x18002b5dd  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
