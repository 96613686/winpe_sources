# FileContentPurveyor::CreateStringFromMultiByte(uint,char const *,int)

- ea: `0x180015a4c`
- end: `0x180015b9d`
- name: `?CreateStringFromMultiByte@FileContentPurveyor@@SAPEAUHSTRING__@@IPEBDH@Z`
- size: `337`
- prototype: `HSTRING __fastcall(UINT CodePage, LPCCH lpMultiByteStr, int cbMultiByte)`
- caller_count: `3`
- callee_count: `8`
- tags: `registry_config, loader_planting`

## callers

- `0x1800156e4`
- `0x18004c1fc`
- `0x18004dd14`

## callees

- `0x180009c0c`
- `0x18000a250`
- `0x18000a7c0`
- `0x1800101e0`
- `0x1800101fc`
- `0x180014d84`
- `0x180015a4c`
- `0x18001a664`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteStringBuffer` at `0x180015ac5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteStringBuffer` at `0x180015ac5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsPreallocateStringBuffer` at `0x180015ae6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsPreallocateStringBuffer` at `0x180015ae6`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180015a86`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180015b21`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180015a86`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180015b21`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
HSTRING __fastcall FileContentPurveyor::CreateStringFromMultiByte(UINT CodePage, LPCCH lpMultiByteStr, int cbMultiByte)
{
  int cchWideChar; // ebx
  const char *v7; // r9
  HSTRING_BUFFER v8; // rdi
  HRESULT v9; // eax
  int v10; // eax
  const char *v11; // r9
  HSTRING v12; // rbx
  int lpWideCharStr; // [rsp+20h] [rbp-38h]
  int lpWideCharStra; // [rsp+20h] [rbp-38h]
  HSTRING string; // [rsp+30h] [rbp-28h] BYREF
  WCHAR *charBuffer; // [rsp+38h] [rbp-20h] BYREF
  _BYTE v18[24]; // [rsp+40h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+30h]
  HSTRING_BUFFER bufferHandle; // [rsp+A8h] [rbp+50h] BYREF

  bufferHandle = 0;
  cchWideChar = MultiByteToWideChar(CodePage, 0, lpMultiByteStr, cbMultiByte, 0, 0);
  if ( cchWideChar <= 0 )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0xE0,
      (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\PayloadHandlers\\FileContentPurveyor.h",
      v7);
  charBuffer = 0;
  v8 = bufferHandle;
  if ( bufferHandle )
  {
    wil::last_error_context::last_error_context((wil::last_error_context *)v18);
    WindowsDeleteStringBuffer(v8);
    wil::last_error_context::~last_error_context((wil::last_error_context *)v18);
  }
  bufferHandle = 0;
  v9 = WindowsPreallocateStringBuffer(cchWideChar, &charBuffer, &bufferHandle);
  if ( v9 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xEB,
      (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\PayloadHandlers\\FileContentPurveyor.h",
      (const char *)(unsigned int)v9,
      lpWideCharStr);
  v10 = MultiByteToWideChar(CodePage, 0, lpMultiByteStr, cbMultiByte, charBuffer, cchWideChar);
  if ( v10 <= 0 )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0xEF,
      (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\PayloadHandlers\\FileContentPurveyor.h",
      v11);
  if ( cchWideChar != v10 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xF0,
      (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\PayloadHandlers\\FileContentPurveyor.h",
      (const char *)0x8000FFFFLL,
      lpWideCharStra);
  wil::make_hstring_from_buffer(&string);
  v12 = string;
  string = 0;
  wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&string);
  wil::details::unique_storage<wil::details::resource_policy<HSTRING_BUFFER__ *,long (*)(HSTRING_BUFFER__ *),&long WindowsDeleteStringBuffer(HSTRING_BUFFER__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING_BUFFER__ *,HSTRING_BUFFER__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING_BUFFER__ *,long (*)(HSTRING_BUFFER__ *),&long WindowsDeleteStringBuffer(HSTRING_BUFFER__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING_BUFFER__ *,HSTRING_BUFFER__ *,0,std::nullptr_t>>(&bufferHandle);
  return v12;
}

```

## disassembly

```asm
0x180015a4c  push    rbp
0x180015a4e  push    rbx
0x180015a4f  push    rsi
0x180015a50  push    rdi
0x180015a51  push    r14
0x180015a53  push    r15
0x180015a55  mov     rbp, rsp
0x180015a58  sub     rsp, 58h
0x180015a5c  mov     esi, r8d
0x180015a5f  mov     r14, rdx
0x180015a62  mov     r15d, ecx
0x180015a65  mov     [rbp+bufferHandle], 0
0x180015a6d  mov     [rsp+58h+cchWideChar], 0; cchWideChar
0x180015a75  mov     [rsp+58h+lpWideCharStr], 0; int
0x180015a7e  mov     r9d, r8d; cbMultiByte
0x180015a81  mov     r8, rdx; lpMultiByteStr
0x180015a84  xor     edx, edx; dwFlags
0x180015a86  call    cs:__imp_MultiByteToWideChar
0x180015a8c  mov     ebx, eax
0x180015a8e  mov     rcx, [rbp+30h]; this
0x180015a92  test    eax, eax
0x180015a94  jg      short loc_180015AA8
0x180015a96  lea     r8, aOnecoreBaseFli_37; "onecore\\base\\flighting\\onesettings\\"...
0x180015a9d  mov     edx, 0E0h; void *
0x180015aa2  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x180015aa8  mov     [rbp+charBuffer], 0
0x180015ab0  mov     rdi, [rbp+bufferHandle]
0x180015ab4  test    rdi, rdi
0x180015ab7  jz      short loc_180015AD4
0x180015ab9  lea     rcx, [rbp+var_18]; this
0x180015abd  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180015ac2  mov     rcx, rdi; bufferHandle
0x180015ac5  call    cs:__imp_WindowsDeleteStringBuffer
0x180015acb  lea     rcx, [rbp+var_18]; this
0x180015acf  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180015ad4  mov     [rbp+bufferHandle], 0
0x180015adc  lea     r8, [rbp+bufferHandle]; bufferHandle
0x180015ae0  lea     rdx, [rbp+charBuffer]; charBuffer
0x180015ae4  mov     ecx, ebx; length
0x180015ae6  call    cs:__imp_WindowsPreallocateStringBuffer
0x180015aec  mov     rcx, [rbp+30h]; this
0x180015af0  test    eax, eax
0x180015af2  jns     short loc_180015B09
0x180015af4  mov     r9d, eax; char *
0x180015af7  lea     r8, aOnecoreBaseFli_37; "onecore\\base\\flighting\\onesettings\\"...
0x180015afe  mov     edx, 0EBh; void *
0x180015b03  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180015b09  mov     [rsp+58h+cchWideChar], ebx; cchWideChar
0x180015b0d  mov     rax, [rbp+charBuffer]
0x180015b11  mov     [rsp+58h+lpWideCharStr], rax; int
0x180015b16  mov     r9d, esi; cbMultiByte
0x180015b19  mov     r8, r14; lpMultiByteStr
0x180015b1c  xor     edx, edx; dwFlags
0x180015b1e  mov     ecx, r15d; CodePage
0x180015b21  call    cs:__imp_MultiByteToWideChar
0x180015b27  mov     rcx, [rbp+30h]; this
0x180015b2b  test    eax, eax
0x180015b2d  jg      short loc_180015B41
0x180015b2f  lea     r8, aOnecoreBaseFli_37; "onecore\\base\\flighting\\onesettings\\"...
0x180015b36  mov     edx, 0EFh; void *
0x180015b3b  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x180015b41  mov     rcx, [rbp+30h]; this
0x180015b45  cmp     ebx, eax
0x180015b47  jz      short loc_180015B61
0x180015b49  mov     r9d, 8000FFFFh; char *
0x180015b4f  lea     r8, aOnecoreBaseFli_37; "onecore\\base\\flighting\\onesettings\\"...
0x180015b56  mov     edx, 0F0h; void *
0x180015b5b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180015b61  lea     rdx, [rbp+bufferHandle]
0x180015b65  lea     rcx, [rbp+string]; string
0x180015b69  call    ?make_hstring_from_buffer@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@$$QEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING_BUFFER__@@P6AJPEAU1@@Z$1?WindowsDeleteStringBuffer@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@@Z; wil::make_hstring_from_buffer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING_BUFFER__ *,long (*)(HSTRING_BUFFER__ *),&WindowsDeleteStringBuffer(HSTRING_BUFFER__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING_BUFFER__ *,HSTRING_BUFFER__ *,0,std::nullptr_t>>> &&)
0x180015b6e  mov     rbx, [rbp+string]
0x180015b72  mov     [rbp+string], 0
0x180015b7a  lea     rcx, [rbp+string]
0x180015b7e  call    ??1?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(void)
0x180015b83  nop
0x180015b84  lea     rcx, [rbp+bufferHandle]
0x180015b88  call    ??1?$unique_storage@U?$resource_policy@PEAUHSTRING_BUFFER__@@P6AJPEAU1@@Z$1?WindowsDeleteStringBuffer@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HSTRING_BUFFER__ *,long (*)(HSTRING_BUFFER__ *),&WindowsDeleteStringBuffer(HSTRING_BUFFER__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING_BUFFER__ *,HSTRING_BUFFER__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING_BUFFER__ *,long (*)(HSTRING_BUFFER__ *),&WindowsDeleteStringBuffer(HSTRING_BUFFER__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING_BUFFER__ *,HSTRING_BUFFER__ *,0,std::nullptr_t>>(void)
0x180015b8d  mov     rax, rbx
0x180015b90  add     rsp, 58h
0x180015b94  pop     r15
0x180015b96  pop     r14
0x180015b98  pop     rdi
0x180015b99  pop     rsi
0x180015b9a  pop     rbx
0x180015b9b  pop     rbp
0x180015b9c  retn
```
