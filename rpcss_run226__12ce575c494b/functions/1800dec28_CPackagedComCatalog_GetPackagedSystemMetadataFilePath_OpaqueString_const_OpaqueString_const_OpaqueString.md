# CPackagedComCatalog::GetPackagedSystemMetadataFilePath(OpaqueString const &,OpaqueString const &,OpaqueString &)

- ea: `0x1800dec28`
- end: `0x1800dee46`
- name: `?GetPackagedSystemMetadataFilePath@CPackagedComCatalog@@CAJAEBVOpaqueString@@0AEAV2@@Z`
- size: `542`
- prototype: `__int64 __fastcall(const struct OpaqueString *, const struct OpaqueString *, struct OpaqueString *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800df5f0`

## callees

- `0x18000d0dc`
- `0x180034540`
- `0x1800418c0`
- `0x180042270`
- `0x180070740`
- `0x1800b27e0`
- `0x1800dec28`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800dee04`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800dee04`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800dec60`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800decb3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800ded0f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800ded59`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800deda4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800dec60`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800decb3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800ded0f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800ded59`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800deda4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsPreallocateStringBuffer` at `0x1800ded3d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsPreallocateStringBuffer` at `0x1800ded3d`
- `KERNELBASE!GetSystemMetadataPathForPackage` at `0x1800dec70`
- `KERNELBASE!GetSystemMetadataPathForPackage` at `0x1800ded69`
- `KERNELBASE!GetSystemMetadataPathForPackage` at `0x1800dec70`
- `KERNELBASE!GetSystemMetadataPathForPackage` at `0x1800ded69`

## string_xrefs

- `0x1800decc9`: `onecore\com\combase\catalog\packagedcomcatalog.cpp`
- `0x1800dedba`: `onecore\com\combase\catalog\packagedcomcatalog.cpp`
- `0x1800dec76`: `Failed call to GetSystemMetadataPathForPackage. PackageId=%S hr=%!HRESULT!`
- `0x1800dedc1`: `Failed call to GetSystemMetadataPathForPackage. PackageId=%S hr=%!HRESULT!`
- `0x1800decbd`: `CPackagedComCatalog::GetPackagedSystemMetadataFilePath`
- `0x1800dedae`: `CPackagedComCatalog::GetPackagedSystemMetadataFilePath`
- `0x1800deceb`: `\PackagedCom\`

## pseudocode

```c
__int64 __fastcall CPackagedComCatalog::GetPackagedSystemMetadataFilePath(HSTRING *a1, HSTRING *a2, HSTRING *a3)
{
  PCWSTR StringRawBuffer; // rax
  int SystemMetadataPathForPackage; // eax
  int v8; // edi
  PCWSTR v9; // rax
  HSTRING v10; // rcx
  PCWSTR v11; // rax
  UINT32 v12; // esi
  const unsigned __int16 *v13; // r12
  HSTRING v14; // rcx
  WCHAR *v15; // rbx
  PCWSTR v16; // rax
  int v17; // eax
  PCWSTR v18; // rax
  __int64 v20; // [rsp+30h] [rbp-50h]
  UINT32 v21; // [rsp+40h] [rbp-40h] BYREF
  UINT32 length; // [rsp+44h] [rbp-3Ch] BYREF
  WCHAR *charBuffer; // [rsp+48h] [rbp-38h] BYREF
  HSTRING_BUFFER bufferHandle; // [rsp+50h] [rbp-30h] BYREF
  unsigned __int16 v25[16]; // [rsp+58h] [rbp-28h] BYREF

  v21 = 0;
  StringRawBuffer = WindowsGetStringRawBuffer(*a1, 0);
  SystemMetadataPathForPackage = GetSystemMetadataPathForPackage(StringRawBuffer, &v21, 0);
  v8 = SystemMetadataPathForPackage;
  if ( SystemMetadataPathForPackage == 122 )
    goto LABEL_9;
  if ( SystemMetadataPathForPackage > 0 )
    v8 = (unsigned __int16)SystemMetadataPathForPackage | 0x80070000;
  if ( dword_18014E4B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(0) )
  {
    v9 = WindowsGetStringRawBuffer(*a1, 0);
    ComTraceMessageT<unsigned short *,long>(
      (unsigned int)"onecore\\com\\combase\\catalog\\packagedcomcatalog.cpp",
      (unsigned int)"CPackagedComCatalog::GetPackagedSystemMetadataFilePath",
      6480,
      0,
      (__int64)L"Failed call to GetSystemMetadataPathForPackage. PackageId=%S hr=%!HRESULT!",
      v9,
      v8);
  }
  if ( v8 >= 0 )
  {
LABEL_9:
    v10 = *a2;
    length = 0;
    *(_OWORD *)v25 = *(_OWORD *)L"\\PackagedCom\\";
    *(_OWORD *)&v25[6] = *(_OWORD *)L"gedCom\\";
    v11 = WindowsGetStringRawBuffer(v10, &length);
    charBuffer = 0;
    v12 = length + 12 + v21;
    bufferHandle = 0;
    v13 = v11;
    v8 = WindowsPreallocateStringBuffer(v12, &charBuffer, &bufferHandle);
    if ( v8 >= 0 )
    {
      v14 = *a1;
      v15 = charBuffer;
      v21 = v12;
      v16 = WindowsGetStringRawBuffer(v14, 0);
      v17 = GetSystemMetadataPathForPackage(v16, &v21, v15);
      if ( v17 )
      {
        if ( v17 > 0 )
          v8 = (unsigned __int16)v17 | 0x80070000;
        else
          v8 = v17;
        if ( dword_18014E4B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(0) )
        {
          v18 = WindowsGetStringRawBuffer(*a1, 0);
          LODWORD(v20) = v8;
          ComTraceMessageT<unsigned short *,long>(
            (unsigned int)"onecore\\com\\combase\\catalog\\packagedcomcatalog.cpp",
            (unsigned int)"CPackagedComCatalog::GetPackagedSystemMetadataFilePath",
            6510,
            0,
            (__int64)L"Failed call to GetSystemMetadataPathForPackage. PackageId=%S hr=%!HRESULT!",
            v18,
            v20);
        }
      }
      else
      {
        StringCchCatW(charBuffer, v12 + 1, v25);
        StringCchCatW(charBuffer, v12 + 1, v13);
        WindowsDeleteString(*a3);
        *a3 = 0;
        wil::make_hstring_from_buffer_nothrow(&bufferHandle, a3);
      }
    }
    wil::details::unique_storage<wil::details::resource_policy<HSTRING_BUFFER__ *,long (*)(HSTRING_BUFFER__ *),&long WindowsDeleteStringBuffer(HSTRING_BUFFER__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING_BUFFER__ *,HSTRING_BUFFER__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING_BUFFER__ *,long (*)(HSTRING_BUFFER__ *),&long WindowsDeleteStringBuffer(HSTRING_BUFFER__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING_BUFFER__ *,HSTRING_BUFFER__ *,0,std::nullptr_t>>(&bufferHandle);
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1800dec28  push    rbp
0x1800dec2a  push    rbx
0x1800dec2b  push    rsi
0x1800dec2c  push    rdi
0x1800dec2d  push    r12
0x1800dec2f  push    r14
0x1800dec31  push    r15
0x1800dec33  mov     rbp, rsp
0x1800dec36  sub     rsp, 80h
0x1800dec3d  mov     rax, cs:__security_cookie
0x1800dec44  xor     rax, rsp
0x1800dec47  mov     [rbp+var_8], rax
0x1800dec4b  mov     rbx, rdx
0x1800dec4e  mov     [rbp+var_40], 0
0x1800dec55  mov     r14, rcx
0x1800dec58  xor     edx, edx; length
0x1800dec5a  mov     rcx, [rcx]; string
0x1800dec5d  mov     r15, r8
0x1800dec60  call    cs:__imp_WindowsGetStringRawBuffer
0x1800dec66  xor     r8d, r8d
0x1800dec69  lea     rdx, [rbp+var_40]
0x1800dec6d  mov     rcx, rax
0x1800dec70  call    cs:__imp_GetSystemMetadataPathForPackage
0x1800dec76  lea     rsi, aFailedCallToGe; "Failed call to GetSystemMetadataPathFor"...
0x1800dec7d  mov     edi, eax
0x1800dec7f  cmp     eax, 7Ah ; 'z'
0x1800dec82  jz      short loc_1800DECEB
0x1800dec84  test    eax, eax
0x1800dec86  jle     short loc_1800DEC91
0x1800dec88  movzx   edi, ax
0x1800dec8b  or      edi, 80070000h
0x1800dec91  mov     eax, cs:dword_18014E4B8
0x1800dec97  test    eax, eax
0x1800dec99  jnz     short loc_1800DECAE
0x1800dec9b  cmp     cs:?gfEnableTracing@@3HA, eax; int gfEnableTracing
0x1800deca1  jz      short loc_1800DECE3
0x1800deca3  xor     ecx, ecx
0x1800deca5  call    IsWppLevelEnabled
0x1800decaa  test    al, al
0x1800decac  jz      short loc_1800DECE3
0x1800decae  mov     rcx, [r14]; string
0x1800decb1  xor     edx, edx; length
0x1800decb3  call    cs:__imp_WindowsGetStringRawBuffer
0x1800decb9  mov     [rsp+80h+var_50], edi
0x1800decbd  lea     rdx, aCpackagedcomca; "CPackagedComCatalog::GetPackagedSystemM"...
0x1800decc4  mov     [rsp+80h+var_58], rax
0x1800decc9  lea     rcx, aOnecoreComComb_81; "onecore\\com\\combase\\catalog\\package"...
0x1800decd0  xor     r9d, r9d
0x1800decd3  mov     [rsp+80h+var_60], rsi
0x1800decd8  mov     r8d, 1950h
0x1800decde  call    ??$ComTraceMessageT@PEAGJ@@YAXPEBD0HW4TraceLevel@@PEBGPEAGJ@Z; ComTraceMessageT<ushort *,long>(char const *,char const *,int,TraceLevel,ushort const *,ushort *,long)
0x1800dece3  test    edi, edi
0x1800dece5  js      loc_1800DEE26
0x1800deceb  movups  xmm0, xmmword ptr cs:aPackagedcom; "\\PackagedCom\\"
0x1800decf2  mov     rcx, [rbx]; string
0x1800decf5  lea     rdx, [rbp+length]; length
0x1800decf9  movups  xmm1, xmmword ptr cs:aPackagedcom+0Ch; "gedCom\\"
0x1800ded00  mov     [rbp+length], 0
0x1800ded07  movups  xmmword ptr [rbp+var_28], xmm0
0x1800ded0b  movups  xmmword ptr [rbp+var_28+0Ch], xmm1
0x1800ded0f  call    cs:__imp_WindowsGetStringRawBuffer
0x1800ded15  mov     ecx, [rbp+length]
0x1800ded18  lea     r8, [rbp+bufferHandle]; bufferHandle
0x1800ded1c  mov     esi, [rbp+var_40]
0x1800ded1f  lea     rdx, [rbp+charBuffer]; charBuffer
0x1800ded23  add     ecx, 0Ch
0x1800ded26  mov     [rbp+charBuffer], 0
0x1800ded2e  add     esi, ecx
0x1800ded30  mov     [rbp+bufferHandle], 0
0x1800ded38  mov     ecx, esi; length
0x1800ded3a  mov     r12, rax
0x1800ded3d  call    cs:__imp_WindowsPreallocateStringBuffer
0x1800ded43  mov     edi, eax
0x1800ded45  test    eax, eax
0x1800ded47  js      loc_1800DEE1D
0x1800ded4d  mov     rcx, [r14]; string
0x1800ded50  xor     edx, edx; length
0x1800ded52  mov     rbx, [rbp+charBuffer]
0x1800ded56  mov     [rbp+var_40], esi
0x1800ded59  call    cs:__imp_WindowsGetStringRawBuffer
0x1800ded5f  mov     r8, rbx
0x1800ded62  lea     rdx, [rbp+var_40]
0x1800ded66  mov     rcx, rax
0x1800ded69  call    cs:__imp_GetSystemMetadataPathForPackage
0x1800ded6f  test    eax, eax
0x1800ded71  jz      short loc_1800DEDDF
0x1800ded73  jg      short loc_1800DED79
0x1800ded75  mov     edi, eax
0x1800ded77  jmp     short loc_1800DED82
0x1800ded79  movzx   edi, ax
0x1800ded7c  or      edi, 80070000h
0x1800ded82  mov     eax, cs:dword_18014E4B8
0x1800ded88  test    eax, eax
0x1800ded8a  jnz     short loc_1800DED9F
0x1800ded8c  cmp     cs:?gfEnableTracing@@3HA, eax; int gfEnableTracing
0x1800ded92  jz      short loc_1800DEDDB
0x1800ded94  xor     ecx, ecx
0x1800ded96  call    IsWppLevelEnabled
0x1800ded9b  test    al, al
0x1800ded9d  jz      short loc_1800DEDDB
0x1800ded9f  mov     rcx, [r14]; string
0x1800deda2  xor     edx, edx; length
0x1800deda4  call    cs:__imp_WindowsGetStringRawBuffer
0x1800dedaa  mov     [rsp+80h+var_50], edi
0x1800dedae  lea     rdx, aCpackagedcomca; "CPackagedComCatalog::GetPackagedSystemM"...
0x1800dedb5  mov     [rsp+80h+var_58], rax
0x1800dedba  lea     rcx, aOnecoreComComb_81; "onecore\\com\\combase\\catalog\\package"...
0x1800dedc1  lea     rax, aFailedCallToGe; "Failed call to GetSystemMetadataPathFor"...
0x1800dedc8  xor     r9d, r9d
0x1800dedcb  mov     r8d, 196Eh
0x1800dedd1  mov     [rsp+80h+var_60], rax
0x1800dedd6  call    ??$ComTraceMessageT@PEAGJ@@YAXPEBD0HW4TraceLevel@@PEBGPEAGJ@Z; ComTraceMessageT<ushort *,long>(char const *,char const *,int,TraceLevel,ushort const *,ushort *,long)
0x1800deddb  test    edi, edi
0x1800deddd  js      short loc_1800DEE1D
0x1800deddf  mov     rcx, [rbp+charBuffer]; unsigned __int16 *
0x1800dede3  lea     eax, [rsi+1]
0x1800dede6  mov     edx, eax; unsigned __int64
0x1800dede8  lea     r8, [rbp+var_28]; unsigned __int16 *
0x1800dedec  mov     ebx, eax
0x1800dedee  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800dedf3  mov     rcx, [rbp+charBuffer]; unsigned __int16 *
0x1800dedf7  mov     r8, r12; unsigned __int16 *
0x1800dedfa  mov     edx, ebx; unsigned __int64
0x1800dedfc  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800dee01  mov     rcx, [r15]; string
0x1800dee04  call    cs:__imp_WindowsDeleteString
0x1800dee0a  mov     rdx, r15
0x1800dee0d  mov     qword ptr [r15], 0
0x1800dee14  lea     rcx, [rbp+bufferHandle]
0x1800dee18  call    ?make_hstring_from_buffer_nothrow@wil@@YAJ$$QEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING_BUFFER__@@P6AJPEAU1@@Z$1?WindowsDeleteStringBuffer@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAPEAUHSTRING__@@@Z; wil::make_hstring_from_buffer_nothrow(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING_BUFFER__ *,long (*)(HSTRING_BUFFER__ *),&WindowsDeleteStringBuffer(HSTRING_BUFFER__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING_BUFFER__ *,HSTRING_BUFFER__ *,0,std::nullptr_t>>> &&,HSTRING__ * *)
0x1800dee1d  lea     rcx, [rbp+bufferHandle]
0x1800dee21  call    ??1?$unique_storage@U?$resource_policy@PEAUHSTRING_BUFFER__@@P6AJPEAU1@@Z$1?WindowsDeleteStringBuffer@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HSTRING_BUFFER__ *,long (*)(HSTRING_BUFFER__ *),&WindowsDeleteStringBuffer(HSTRING_BUFFER__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING_BUFFER__ *,HSTRING_BUFFER__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING_BUFFER__ *,long (*)(HSTRING_BUFFER__ *),&WindowsDeleteStringBuffer(HSTRING_BUFFER__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING_BUFFER__ *,HSTRING_BUFFER__ *,0,std::nullptr_t>>(void)
0x1800dee26  mov     eax, edi
0x1800dee28  mov     rcx, [rbp+var_8]
0x1800dee2c  xor     rcx, rsp; StackCookie
0x1800dee2f  call    __security_check_cookie
0x1800dee34  add     rsp, 80h
0x1800dee3b  pop     r15
0x1800dee3d  pop     r14
0x1800dee3f  pop     r12
0x1800dee41  pop     rdi
0x1800dee42  pop     rsi
0x1800dee43  pop     rbx
0x1800dee44  pop     rbp
0x1800dee45  retn
```
