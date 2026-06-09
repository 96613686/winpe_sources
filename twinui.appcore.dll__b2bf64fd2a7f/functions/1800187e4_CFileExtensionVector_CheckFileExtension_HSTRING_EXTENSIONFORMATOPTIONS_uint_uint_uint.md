# CFileExtensionVector::CheckFileExtension(HSTRING__ *,EXTENSIONFORMATOPTIONS,uint,uint,uint)

- ea: `0x1800187e4`
- end: `0x180018a28`
- name: `?CheckFileExtension@CFileExtensionVector@@SAJPEAUHSTRING__@@W4EXTENSIONFORMATOPTIONS@@III@Z`
- size: `580`
- prototype: ``
- caller_count: `3`
- callee_count: `6`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800534d4`
- `0x18005bbe0`
- `0x18005bf30`

## callees

- `0x1800187e4`
- `0x1800193f4`
- `0x180022fe0`
- `0x18002b1b0`
- `0x18004bca4`
- `0x18005add0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LockResource` at `0x180018897`
- `api-ms-win-core-libraryloader-l1-2-0!LockResource` at `0x180018897`
- `api-ms-win-core-libraryloader-l1-2-0!FindResourceExW` at `0x18001886c`
- `api-ms-win-core-libraryloader-l1-2-0!FindResourceExW` at `0x18001886c`
- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x180018885`
- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x180018885`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180018943`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180018943`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180018971`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180018971`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001892c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001892c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsStringHasEmbeddedNull` at `0x180018836`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsStringHasEmbeddedNull` at `0x180018836`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrChrW` at `0x180018988`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrChrW` at `0x180018999`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrChrW` at `0x1800189aa`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrChrW` at `0x180018988`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrChrW` at `0x180018999`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrChrW` at `0x1800189aa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800189f8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800189f8`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x1800189e9`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x1800189e9`

## pseudocode

```c
__int64 __fastcall CFileExtensionVector::CheckFileExtension(
        HSTRING a1,
        char a2,
        unsigned int a3,
        unsigned int a4,
        unsigned int a5)
{
  unsigned int v9; // edi
  HRSRC Resource; // rax
  HGLOBAL v11; // rax
  _WORD *v12; // rcx
  unsigned int v13; // edx
  unsigned int v14; // r14d
  const WCHAR *v15; // rdx
  __int64 v16; // rdx
  LPVOID v17; // r8
  __int64 v18; // r8
  PCWSTR StringRawBuffer; // rax
  const WCHAR *v20; // rbx
  __int64 v21; // rdx
  __int64 v22; // r8
  void *v23; // r9
  BOOL hasEmbedNull; // [rsp+20h] [rbp-41h] BYREF
  LPVOID pv; // [rsp+28h] [rbp-39h] BYREF
  __int64 v27; // [rsp+30h] [rbp-31h]
  __int64 v28; // [rsp+38h] [rbp-29h]
  HSTRING v29[4]; // [rsp+40h] [rbp-21h] BYREF
  HSTRING string; // [rsp+60h] [rbp-1h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+68h] [rbp+7h] BYREF

  v29[0] = a1;
  pv = 0;
  v27 = 0;
  v28 = 0;
  hasEmbedNull = 0;
  WindowsStringHasEmbeddedNull(a1, &hasEmbedNull);
  if ( !hasEmbedNull )
  {
    if ( WindowsCreateStringReference(L"*", 1u, &hstringHeader, &string) < 0 )
      RaiseException(0xC000000D, 1u, 0, 0);
    if ( (unsigned __int8)Windows::Internal::operator==(v29, &string) )
    {
      if ( (a2 & 1) != 0 )
      {
        v18 = a4;
LABEL_26:
        v9 = -2147024809;
        if ( (int)Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::Initialize(
                    &pv,
                    &_ImageBase,
                    v18) < 0 )
          goto LABEL_29;
        Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<unsigned short>>::_EnsureCount(
          &pv,
          v21,
          v22,
          pv);
        v16 = (unsigned int)v27;
        v17 = v23;
        goto LABEL_28;
      }
    }
    else
    {
      StringRawBuffer = WindowsGetStringRawBuffer(a1, 0);
      if ( *StringRawBuffer != 46
        || (v20 = StringRawBuffer + 1, StrChrW(StringRawBuffer + 1, 0x2Eu))
        || StrChrW(v20, 0x2Au)
        || StrChrW(v20, 0x3Fu) )
      {
        v18 = a5;
        goto LABEL_26;
      }
    }
    return 0;
  }
  v9 = -2147024809;
  Resource = FindResourceExW(&_ImageBase, (LPCWSTR)6, (LPCWSTR)(unsigned __int16)((a3 >> 4) + 1), 0);
  if ( !Resource )
    return v9;
  v11 = LoadResource(&_ImageBase, Resource);
  if ( !v11 )
    return v9;
  v12 = LockResource(v11);
  if ( !v12 )
    return v9;
  v13 = 0;
  v14 = a3 & 0xF;
  if ( v14 )
  {
    do
    {
      ++v13;
      v12 += (unsigned __int16)*v12 + 1;
    }
    while ( v13 < v14 );
  }
  v15 = v12 + 1;
  if ( !*v12 )
    v15 = &pszDefault;
  if ( (int)Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Initialize(
              &pv,
              v15,
              (unsigned __int16)*v12) >= 0 )
  {
    v16 = v27;
    v17 = pv;
    if ( v27 == -1 )
    {
      if ( pv )
      {
        do
          ++v16;
        while ( *((_WORD *)pv + v16) );
      }
      else
      {
        v16 = 0;
      }
    }
LABEL_28:
    RoOriginateErrorW(2147942487LL, v16, v17);
  }
LABEL_29:
  if ( pv )
    CoTaskMemFree(pv);
  return v9;
}

```

## disassembly

```asm
0x1800187e4  mov     [rsp-8+arg_0], rbx
0x1800187e9  mov     [rsp-8+arg_8], rsi
0x1800187ee  push    rbp
0x1800187ef  push    rdi
0x1800187f0  push    r12
0x1800187f2  push    r14
0x1800187f4  push    r15
0x1800187f6  lea     rbp, [rsp-2Fh]
0x1800187fb  sub     rsp, 90h
0x180018802  mov     rax, cs:__security_cookie
0x180018809  xor     rax, rsp
0x18001880c  mov     [rbp+4Fh+var_30], rax
0x180018810  xor     r12d, r12d
0x180018813  mov     [rbp+4Fh+var_70], rcx
0x180018817  mov     edi, edx
0x180018819  mov     [rbp+4Fh+pv], r12
0x18001881d  lea     rdx, [rbp+4Fh+hasEmbedNull]; hasEmbedNull
0x180018821  mov     [rbp+4Fh+var_80], r12
0x180018825  mov     [rbp+4Fh+var_78], r12
0x180018829  mov     r15d, r9d
0x18001882c  mov     [rbp+4Fh+hasEmbedNull], r12d
0x180018830  mov     r14d, r8d
0x180018833  mov     rbx, rcx
0x180018836  call    cs:__imp_WindowsStringHasEmbeddedNull
0x18001883c  lea     esi, [r12+1]
0x180018841  cmp     [rbp+4Fh+hasEmbedNull], r12d
0x180018845  jz      loc_18001891B
0x18001884b  mov     eax, r14d
0x18001884e  lea     edx, [rsi+5]; lpType
0x180018851  shr     eax, 4
0x180018854  lea     rcx, __ImageBase; hModule
0x18001885b  add     ax, si
0x18001885e  mov     ebx, 80070057h
0x180018863  movzx   r8d, ax; lpName
0x180018867  xor     r9d, r9d; wLanguage
0x18001886a  mov     edi, ebx
0x18001886c  call    cs:__imp_FindResourceExW
0x180018872  test    rax, rax
0x180018875  jz      loc_1800189FE
0x18001887b  mov     rdx, rax; hResInfo
0x18001887e  lea     rcx, __ImageBase; hModule
0x180018885  call    cs:__imp_LoadResource
0x18001888b  test    rax, rax
0x18001888e  jz      loc_1800189FE
0x180018894  mov     rcx, rax; hResData
0x180018897  call    cs:__imp_LockResource
0x18001889d  mov     rcx, rax
0x1800188a0  test    rax, rax
0x1800188a3  jz      loc_1800189FE
0x1800188a9  mov     edx, r12d
0x1800188ac  and     r14d, 0Fh
0x1800188b0  jbe     short loc_1800188C4
0x1800188b2  movzx   eax, word ptr [rcx]
0x1800188b5  add     edx, esi
0x1800188b7  lea     rcx, [rcx+rax*2]
0x1800188bb  add     rcx, 2
0x1800188bf  cmp     edx, r14d
0x1800188c2  jb      short loc_1800188B2
0x1800188c4  lea     rdx, [rcx+2]
0x1800188c8  cmp     [rcx], r12w
0x1800188cc  jnz     short loc_1800188D5
0x1800188ce  lea     rdx, pszDefault
0x1800188d5  movzx   r8d, word ptr [rcx]
0x1800188d9  lea     rcx, [rbp+4Fh+pv]
0x1800188dd  call    ?_Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Initialize(ushort const *,unsigned __int64)
0x1800188e2  test    eax, eax
0x1800188e4  js      loc_1800189EF
0x1800188ea  mov     rdx, [rbp+4Fh+var_80]
0x1800188ee  mov     r8, [rbp+4Fh+pv]
0x1800188f2  cmp     rdx, 0FFFFFFFFFFFFFFFFh
0x1800188f6  jnz     loc_1800189E7
0x1800188fc  test    r8, r8
0x1800188ff  jz      short loc_180018913
0x180018901  or      rdx, rdx
0x180018904  inc     rdx
0x180018907  cmp     [r8+rdx*2], r12w
0x18001890c  jnz     short loc_180018904
0x18001890e  jmp     loc_1800189E7
0x180018913  mov     rdx, r12
0x180018916  jmp     loc_1800189E7
0x18001891b  lea     r9, [rbp+4Fh+string]; string
0x18001891f  mov     edx, esi; length
0x180018921  lea     r8, [rbp+4Fh+hstringHeader]; hstringHeader
0x180018925  lea     rcx, asc_180097F30; "*"
0x18001892c  call    cs:__imp_WindowsCreateStringReference
0x180018932  test    eax, eax
0x180018934  jns     short loc_180018949
0x180018936  xor     r9d, r9d; lpArguments
0x180018939  xor     r8d, r8d; nNumberOfArguments
0x18001893c  mov     edx, esi; dwExceptionFlags
0x18001893e  mov     ecx, 0C000000Dh; dwExceptionCode
0x180018943  call    cs:__imp_RaiseException
0x180018949  lea     rdx, [rbp+4Fh+string]
0x18001894d  lea     rcx, [rbp+4Fh+var_70]
0x180018951  call    ??8Internal@Windows@@YA_NAEBVString@01@0@Z; Windows::Internal::operator==(Windows::Internal::String const &,Windows::Internal::String const &)
0x180018956  test    al, al
0x180018958  jz      short loc_18001896C
0x18001895a  test    sil, dil
0x18001895d  jz      short loc_180018964
0x18001895f  mov     r8d, r15d
0x180018962  jmp     short loc_1800189B9
0x180018964  mov     edi, r12d
0x180018967  jmp     loc_1800189FE
0x18001896c  xor     edx, edx; length
0x18001896e  mov     rcx, rbx; string
0x180018971  call    cs:__imp_WindowsGetStringRawBuffer
0x180018977  mov     edx, 2Eh ; '.'; wMatch
0x18001897c  cmp     [rax], dx
0x18001897f  jnz     short loc_1800189B5
0x180018981  lea     rbx, [rax+2]
0x180018985  mov     rcx, rbx; pszStart
0x180018988  call    cs:__imp_StrChrW
0x18001898e  test    rax, rax
0x180018991  jnz     short loc_1800189B5
0x180018993  lea     edx, [rax+2Ah]; wMatch
0x180018996  mov     rcx, rbx; pszStart
0x180018999  call    cs:__imp_StrChrW
0x18001899f  test    rax, rax
0x1800189a2  jnz     short loc_1800189B5
0x1800189a4  lea     edx, [rax+3Fh]; wMatch
0x1800189a7  mov     rcx, rbx; pszStart
0x1800189aa  call    cs:__imp_StrChrW
0x1800189b0  test    rax, rax
0x1800189b3  jz      short loc_180018964
0x1800189b5  mov     r8d, [rbp+4Fh+arg_20]
0x1800189b9  mov     ebx, 80070057h
0x1800189be  lea     rdx, __ImageBase
0x1800189c5  lea     rcx, [rbp+4Fh+pv]
0x1800189c9  mov     edi, ebx
0x1800189cb  call    ?Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEAUHINSTANCE__@@IG@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::Initialize(HINSTANCE__ *,uint,ushort)
0x1800189d0  test    eax, eax
0x1800189d2  js      short loc_1800189EF
0x1800189d4  mov     r9, [rbp+4Fh+pv]
0x1800189d8  lea     rcx, [rbp+4Fh+pv]
0x1800189dc  call    ?_EnsureCount@?$NativeString@V?$LocalMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<ushort>>::_EnsureCount(void)
0x1800189e1  mov     edx, dword ptr [rbp+4Fh+var_80]
0x1800189e4  mov     r8, r9
0x1800189e7  mov     ecx, ebx
0x1800189e9  call    cs:__imp_RoOriginateErrorW
0x1800189ef  mov     rcx, [rbp+4Fh+pv]; pv
0x1800189f3  test    rcx, rcx
0x1800189f6  jz      short loc_1800189FE
0x1800189f8  call    cs:__imp_CoTaskMemFree
0x1800189fe  mov     eax, edi
0x180018a00  mov     rcx, [rbp+4Fh+var_30]
0x180018a04  xor     rcx, rsp; StackCookie
0x180018a07  call    __security_check_cookie
0x180018a0c  lea     r11, [rsp+0B0h+var_20]
0x180018a14  mov     rbx, [r11+30h]
0x180018a18  mov     rsi, [r11+38h]
0x180018a1c  mov     rsp, r11
0x180018a1f  pop     r15
0x180018a21  pop     r14
0x180018a23  pop     r12
0x180018a25  pop     rdi
0x180018a26  pop     rbp
0x180018a27  retn
```
