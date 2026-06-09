# CPackagedComCatalog::GetPackagedSystemMetadataFilePath(OpaqueString const &,OpaqueString const &,OpaqueString &)

- ea: `0x1800e5c98`
- end: `0x1800e5eed`
- name: `?GetPackagedSystemMetadataFilePath@CPackagedComCatalog@@CAJAEBVOpaqueString@@0AEAV2@@Z`
- size: `597`
- prototype: `__int64 __fastcall(const struct OpaqueString *, const struct OpaqueString *, struct OpaqueString *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800e6708`

## callees

- `0x180013080`
- `0x180034260`
- `0x18004b524`
- `0x18004bf1c`
- `0x180074d98`
- `0x1800b7ac0`
- `0x1800e5c98`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e5ea4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e5ea4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800e5cd0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800e5d2f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800e5d91`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800e5de7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800e5e3e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800e5cd0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800e5d2f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800e5d91`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800e5de7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800e5e3e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsPreallocateStringBuffer` at `0x1800e5dc5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsPreallocateStringBuffer` at `0x1800e5dc5`
- `KERNELBASE!GetSystemMetadataPathForPackage` at `0x1800e5ce6`
- `KERNELBASE!GetSystemMetadataPathForPackage` at `0x1800e5dfd`
- `KERNELBASE!GetSystemMetadataPathForPackage` at `0x1800e5ce6`
- `KERNELBASE!GetSystemMetadataPathForPackage` at `0x1800e5dfd`

## string_xrefs

- `0x1800e5d4b`: `onecore\com\combase\catalog\packagedcomcatalog.cpp`
- `0x1800e5e5a`: `onecore\com\combase\catalog\packagedcomcatalog.cpp`
- `0x1800e5d6d`: `\PackagedCom\`
- `0x1800e5cf2`: `Failed call to GetSystemMetadataPathForPackage. PackageId=%S hr=%!HRESULT!`
- `0x1800e5e61`: `Failed call to GetSystemMetadataPathForPackage. PackageId=%S hr=%!HRESULT!`
- `0x1800e5d3f`: `CPackagedComCatalog::GetPackagedSystemMetadataFilePath`
- `0x1800e5e4e`: `CPackagedComCatalog::GetPackagedSystemMetadataFilePath`

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
  if ( dword_1801574B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(0) )
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
        if ( dword_1801574B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(0) )
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
0x1800e5c98  push    rbp
0x1800e5c9a  push    rbx
0x1800e5c9b  push    rsi
0x1800e5c9c  push    rdi
0x1800e5c9d  push    r12
0x1800e5c9f  push    r14
0x1800e5ca1  push    r15
0x1800e5ca3  mov     rbp, rsp
0x1800e5ca6  sub     rsp, 80h
0x1800e5cad  mov     rax, cs:__security_cookie
0x1800e5cb4  xor     rax, rsp
0x1800e5cb7  mov     [rbp+var_8], rax
0x1800e5cbb  mov     rbx, rdx
0x1800e5cbe  mov     [rbp+var_40], 0
0x1800e5cc5  mov     r14, rcx
0x1800e5cc8  xor     edx, edx; length
0x1800e5cca  mov     rcx, [rcx]; string
0x1800e5ccd  mov     r15, r8
0x1800e5cd0  call    cs:__imp_WindowsGetStringRawBuffer
0x1800e5cd7  nop     dword ptr [rax+rax+00h]
0x1800e5cdc  xor     r8d, r8d
0x1800e5cdf  lea     rdx, [rbp+var_40]
0x1800e5ce3  mov     rcx, rax
0x1800e5ce6  call    cs:__imp_GetSystemMetadataPathForPackage
0x1800e5ced  nop     dword ptr [rax+rax+00h]
0x1800e5cf2  lea     rsi, aFailedCallToGe; "Failed call to GetSystemMetadataPathFor"...
0x1800e5cf9  mov     edi, eax
0x1800e5cfb  cmp     eax, 7Ah ; 'z'
0x1800e5cfe  jz      short loc_1800E5D6D
0x1800e5d00  test    eax, eax
0x1800e5d02  jle     short loc_1800E5D0D
0x1800e5d04  movzx   edi, ax
0x1800e5d07  or      edi, 80070000h
0x1800e5d0d  mov     eax, cs:dword_1801574B8
0x1800e5d13  test    eax, eax
0x1800e5d15  jnz     short loc_1800E5D2A
0x1800e5d17  cmp     cs:?gfEnableTracing@@3HA, eax; int gfEnableTracing
0x1800e5d1d  jz      short loc_1800E5D65
0x1800e5d1f  xor     ecx, ecx
0x1800e5d21  call    IsWppLevelEnabled
0x1800e5d26  test    al, al
0x1800e5d28  jz      short loc_1800E5D65
0x1800e5d2a  mov     rcx, [r14]; string
0x1800e5d2d  xor     edx, edx; length
0x1800e5d2f  call    cs:__imp_WindowsGetStringRawBuffer
0x1800e5d36  nop     dword ptr [rax+rax+00h]
0x1800e5d3b  mov     [rsp+80h+var_50], edi
0x1800e5d3f  lea     rdx, aCpackagedcomca; "CPackagedComCatalog::GetPackagedSystemM"...
0x1800e5d46  mov     [rsp+80h+var_58], rax
0x1800e5d4b  lea     rcx, aOnecoreComComb_81; "onecore\\com\\combase\\catalog\\package"...
0x1800e5d52  xor     r9d, r9d
0x1800e5d55  mov     [rsp+80h+var_60], rsi
0x1800e5d5a  mov     r8d, 1950h
0x1800e5d60  call    ??$ComTraceMessageT@PEAGJ@@YAXPEBD0HW4TraceLevel@@PEBGPEAGJ@Z; ComTraceMessageT<ushort *,long>(char const *,char const *,int,TraceLevel,ushort const *,ushort *,long)
0x1800e5d65  test    edi, edi
0x1800e5d67  js      loc_1800E5ECC
0x1800e5d6d  movups  xmm0, xmmword ptr cs:aPackagedcom; "\\PackagedCom\\"
0x1800e5d74  mov     rcx, [rbx]; string
0x1800e5d77  lea     rdx, [rbp+length]; length
0x1800e5d7b  movups  xmm1, xmmword ptr cs:aPackagedcom+0Ch; "gedCom\\"
0x1800e5d82  mov     [rbp+length], 0
0x1800e5d89  movups  xmmword ptr [rbp+var_28], xmm0
0x1800e5d8d  movups  xmmword ptr [rbp+var_28+0Ch], xmm1
0x1800e5d91  call    cs:__imp_WindowsGetStringRawBuffer
0x1800e5d98  nop     dword ptr [rax+rax+00h]
0x1800e5d9d  mov     ecx, [rbp+length]
0x1800e5da0  lea     r8, [rbp+bufferHandle]; bufferHandle
0x1800e5da4  mov     esi, [rbp+var_40]
0x1800e5da7  lea     rdx, [rbp+charBuffer]; charBuffer
0x1800e5dab  add     ecx, 0Ch
0x1800e5dae  mov     [rbp+charBuffer], 0
0x1800e5db6  add     esi, ecx
0x1800e5db8  mov     [rbp+bufferHandle], 0
0x1800e5dc0  mov     ecx, esi; length
0x1800e5dc2  mov     r12, rax
0x1800e5dc5  call    cs:__imp_WindowsPreallocateStringBuffer
0x1800e5dcc  nop     dword ptr [rax+rax+00h]
0x1800e5dd1  mov     edi, eax
0x1800e5dd3  test    eax, eax
0x1800e5dd5  js      loc_1800E5EC3
0x1800e5ddb  mov     rcx, [r14]; string
0x1800e5dde  xor     edx, edx; length
0x1800e5de0  mov     rbx, [rbp+charBuffer]
0x1800e5de4  mov     [rbp+var_40], esi
0x1800e5de7  call    cs:__imp_WindowsGetStringRawBuffer
0x1800e5dee  nop     dword ptr [rax+rax+00h]
0x1800e5df3  mov     r8, rbx
0x1800e5df6  lea     rdx, [rbp+var_40]
0x1800e5dfa  mov     rcx, rax
0x1800e5dfd  call    cs:__imp_GetSystemMetadataPathForPackage
0x1800e5e04  nop     dword ptr [rax+rax+00h]
0x1800e5e09  test    eax, eax
0x1800e5e0b  jz      short loc_1800E5E7F
0x1800e5e0d  jg      short loc_1800E5E13
0x1800e5e0f  mov     edi, eax
0x1800e5e11  jmp     short loc_1800E5E1C
0x1800e5e13  movzx   edi, ax
0x1800e5e16  or      edi, 80070000h
0x1800e5e1c  mov     eax, cs:dword_1801574B8
0x1800e5e22  test    eax, eax
0x1800e5e24  jnz     short loc_1800E5E39
0x1800e5e26  cmp     cs:?gfEnableTracing@@3HA, eax; int gfEnableTracing
0x1800e5e2c  jz      short loc_1800E5E7B
0x1800e5e2e  xor     ecx, ecx
0x1800e5e30  call    IsWppLevelEnabled
0x1800e5e35  test    al, al
0x1800e5e37  jz      short loc_1800E5E7B
0x1800e5e39  mov     rcx, [r14]; string
0x1800e5e3c  xor     edx, edx; length
0x1800e5e3e  call    cs:__imp_WindowsGetStringRawBuffer
0x1800e5e45  nop     dword ptr [rax+rax+00h]
0x1800e5e4a  mov     [rsp+80h+var_50], edi
0x1800e5e4e  lea     rdx, aCpackagedcomca; "CPackagedComCatalog::GetPackagedSystemM"...
0x1800e5e55  mov     [rsp+80h+var_58], rax
0x1800e5e5a  lea     rcx, aOnecoreComComb_81; "onecore\\com\\combase\\catalog\\package"...
0x1800e5e61  lea     rax, aFailedCallToGe; "Failed call to GetSystemMetadataPathFor"...
0x1800e5e68  xor     r9d, r9d
0x1800e5e6b  mov     r8d, 196Eh
0x1800e5e71  mov     [rsp+80h+var_60], rax
0x1800e5e76  call    ??$ComTraceMessageT@PEAGJ@@YAXPEBD0HW4TraceLevel@@PEBGPEAGJ@Z; ComTraceMessageT<ushort *,long>(char const *,char const *,int,TraceLevel,ushort const *,ushort *,long)
0x1800e5e7b  test    edi, edi
0x1800e5e7d  js      short loc_1800E5EC3
0x1800e5e7f  mov     rcx, [rbp+charBuffer]; unsigned __int16 *
0x1800e5e83  lea     eax, [rsi+1]
0x1800e5e86  mov     edx, eax; unsigned __int64
0x1800e5e88  lea     r8, [rbp+var_28]; unsigned __int16 *
0x1800e5e8c  mov     ebx, eax
0x1800e5e8e  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800e5e93  mov     rcx, [rbp+charBuffer]; unsigned __int16 *
0x1800e5e97  mov     r8, r12; unsigned __int16 *
0x1800e5e9a  mov     edx, ebx; unsigned __int64
0x1800e5e9c  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800e5ea1  mov     rcx, [r15]; string
0x1800e5ea4  call    cs:__imp_WindowsDeleteString
0x1800e5eab  nop     dword ptr [rax+rax+00h]
0x1800e5eb0  mov     rdx, r15
0x1800e5eb3  mov     qword ptr [r15], 0
0x1800e5eba  lea     rcx, [rbp+bufferHandle]
0x1800e5ebe  call    ?make_hstring_from_buffer_nothrow@wil@@YAJ$$QEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING_BUFFER__@@P6AJPEAU1@@Z$1?WindowsDeleteStringBuffer@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAPEAUHSTRING__@@@Z; wil::make_hstring_from_buffer_nothrow(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING_BUFFER__ *,long (*)(HSTRING_BUFFER__ *),&WindowsDeleteStringBuffer(HSTRING_BUFFER__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING_BUFFER__ *,HSTRING_BUFFER__ *,0,std::nullptr_t>>> &&,HSTRING__ * *)
0x1800e5ec3  lea     rcx, [rbp+bufferHandle]
0x1800e5ec7  call    ??1?$unique_storage@U?$resource_policy@PEAUHSTRING_BUFFER__@@P6AJPEAU1@@Z$1?WindowsDeleteStringBuffer@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HSTRING_BUFFER__ *,long (*)(HSTRING_BUFFER__ *),&WindowsDeleteStringBuffer(HSTRING_BUFFER__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING_BUFFER__ *,HSTRING_BUFFER__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING_BUFFER__ *,long (*)(HSTRING_BUFFER__ *),&WindowsDeleteStringBuffer(HSTRING_BUFFER__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING_BUFFER__ *,HSTRING_BUFFER__ *,0,std::nullptr_t>>(void)
0x1800e5ecc  mov     eax, edi
0x1800e5ece  mov     rcx, [rbp+var_8]
0x1800e5ed2  xor     rcx, rsp; StackCookie
0x1800e5ed5  call    __security_check_cookie
0x1800e5eda  add     rsp, 80h
0x1800e5ee1  pop     r15
0x1800e5ee3  pop     r14
0x1800e5ee5  pop     r12
0x1800e5ee7  pop     rdi
0x1800e5ee8  pop     rsi
0x1800e5ee9  pop     rbx
0x1800e5eea  pop     rbp
0x1800e5eeb  retn
```
