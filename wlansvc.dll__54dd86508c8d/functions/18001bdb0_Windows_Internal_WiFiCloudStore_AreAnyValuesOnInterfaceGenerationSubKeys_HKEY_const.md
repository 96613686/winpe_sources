# Windows::Internal::WiFiCloudStore::AreAnyValuesOnInterfaceGenerationSubKeys(HKEY__ * const)

- ea: `0x18001bdb0`
- end: `0x18001c16f`
- name: `?AreAnyValuesOnInterfaceGenerationSubKeys@WiFiCloudStore@Internal@Windows@@YA_NQEAUHKEY__@@@Z`
- size: `959`
- prototype: `bool __fastcall(HKEY hKey, HKEY)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config`

## callers

- `0x18001c9ec`

## callees

- `0x18000a994`
- `0x18000d650`
- `0x18001a0d0`
- `0x18001bdb0`
- `0x18001c180`
- `0x18001c9cc`
- `0x180039d04`
- `0x18006a050`
- `0x1800cf244`
- `0x180106340`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001bf0c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001bfd0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001bf0c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001bfd0`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18001be31`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18001c04f`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18001be31`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18001c04f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001c085`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001c099`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001c0e5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001c085`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001c099`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001c0e5`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18001beb8`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18001beb8`

## string_xrefs

- `0x18001be46`: `onecore\net\wificloudstore\registry\lib\wificdsproducerreg.cpp`
- `0x18001becd`: `onecore\net\wificloudstore\registry\lib\wificdsproducerreg.cpp`
- `0x18001bf21`: `onecore\net\wificloudstore\registry\lib\wificdsproducerreg.cpp`
- `0x18001c000`: `onecore\net\wificloudstore\registry\lib\wificdsproducerreg.cpp`
- `0x18001c064`: `onecore\net\wificloudstore\registry\lib\wificdsproducerreg.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3 #try_helpers=1
char __fastcall Windows::Internal::WiFiCloudStore::AreAnyValuesOnInterfaceGenerationSubKeys(HKEY hKey, HKEY a2)
{
  int v3; // edi
  unsigned int v4; // eax
  DWORD v5; // esi
  unsigned int v6; // eax
  HKEY *v7; // rax
  unsigned int v8; // eax
  int *i; // r14
  const WCHAR *v10; // rdx
  unsigned int v11; // r15d
  unsigned int InfoKeyW; // eax
  unsigned int lpcSubKeys; // [rsp+20h] [rbp-E8h]
  unsigned int lpcSubKeysa; // [rsp+20h] [rbp-E8h]
  unsigned int lpcSubKeysb; // [rsp+20h] [rbp-E8h]
  unsigned int lpcSubKeysc; // [rsp+20h] [rbp-E8h]
  unsigned int lpcSubKeysd; // [rsp+20h] [rbp-E8h]
  DWORD cbMaxSubKeyLen; // [rsp+64h] [rbp-A4h] BYREF
  DWORD cSubKeys; // [rsp+68h] [rbp-A0h] BYREF
  DWORD cValues[3]; // [rsp+6Ch] [rbp-9Ch] BYREF
  HKEY phkResult; // [rsp+78h] [rbp-90h] BYREF
  HKEY hKeya; // [rsp+80h] [rbp-88h] BYREF
  DWORD cchName; // [rsp+88h] [rbp-80h] BYREF
  LPWSTR lpName[2]; // [rsp+90h] [rbp-78h] BYREF
  __int64 v26; // [rsp+A0h] [rbp-68h]
  HKEY v27; // [rsp+A8h] [rbp-60h]
  LPCWSTR lpSubKey[4]; // [rsp+B0h] [rbp-58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+0h]

  v27 = hKey;
  v3 = 0;
  cSubKeys = 0;
  cbMaxSubKeyLen = 0;
  v4 = RegQueryInfoKeyW(hKey, 0, 0, 0, &cSubKeys, &cbMaxSubKeyLen, 0, 0, 0, 0, 0, 0);
  if ( v4 )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x1E,
      (unsigned int)"onecore\\net\\wificloudstore\\registry\\lib\\wificdsproducerreg.cpp",
      (const char *)v4,
      lpcSubKeys);
  std::vector<unsigned short>::vector<unsigned short>(lpName, cbMaxSubKeyLen + 1);
  v5 = 0;
LABEL_4:
  cValues[1] = v5;
  if ( v5 >= cSubKeys )
  {
    if ( lpName[0] )
      std::_Deallocate<16>(
        lpName[0],
        (const struct std::nothrow_t *)(2 * ((signed __int64)(v26 - (unsigned __int64)lpName[0]) >> 1)));
    return 0;
  }
  else
  {
    cchName = lpName[1] - lpName[0];
    v6 = RegEnumKeyExW(hKey, v5, lpName[0], &cchName, 0, 0, 0, 0);
    if ( v6 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x29,
        (unsigned int)"onecore\\net\\wificloudstore\\registry\\lib\\wificdsproducerreg.cpp",
        (const char *)v6,
        lpcSubKeysa);
    hKeya = 0;
    v7 = (HKEY *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(&hKeya);
    v8 = RegOpenKeyExW(hKey, lpName[0], 0, 0x20019u, v7);
    if ( v8 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x2B,
        (unsigned int)"onecore\\net\\wificloudstore\\registry\\lib\\wificdsproducerreg.cpp",
        (const char *)v8,
        lpcSubKeysb);
    for ( i = (int *)Windows::Internal::WiFiCloudStore::c_allProfileGenerations; ; ++i )
    {
      if ( i == &dword_18024852C )
      {
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKeya);
        ++v5;
        goto LABEL_4;
      }
      phkResult = 0;
      if ( *i == 0x80000000 )
      {
        std::wstring::wstring(lpSubKey, L"Irrelevant");
      }
      else if ( *i == 0x7FFFFFFF )
      {
        std::wstring::wstring(lpSubKey, L"All");
      }
      else
      {
        std::to_wstring(lpSubKey, (unsigned int)*i);
      }
      v3 |= 1u;
      v10 = (const WCHAR *)lpSubKey;
      if ( lpSubKey[3] > (LPCWSTR)7 )
        v10 = lpSubKey[0];
      v11 = RegOpenKeyExW(hKeya, v10, 0, 0x20019u, &phkResult);
      std::pair<std::wstring,void *>::~pair<std::wstring,void *>(lpSubKey);
      if ( v11 != 2 )
      {
        if ( v11 )
          wil::details::in1diag3::Throw_Win32(
            retaddr,
            (void *)0x35,
            (unsigned int)"onecore\\net\\wificloudstore\\registry\\lib\\wificdsproducerreg.cpp",
            (const char *)v11,
            lpcSubKeysc);
        cValues[0] = 0;
        InfoKeyW = RegQueryInfoKeyW(phkResult, 0, 0, 0, 0, 0, 0, cValues, 0, 0, 0, 0);
        if ( InfoKeyW )
          wil::details::in1diag3::Throw_Win32(
            retaddr,
            (void *)0x39,
            (unsigned int)"onecore\\net\\wificloudstore\\registry\\lib\\wificdsproducerreg.cpp",
            (const char *)InfoKeyW,
            lpcSubKeysd);
        if ( cValues[0] )
          break;
      }
      if ( phkResult )
        RegCloseKey(phkResult);
    }
    if ( phkResult )
      RegCloseKey(phkResult);
    if ( hKeya )
      RegCloseKey(hKeya);
    if ( lpName[0] )
    {
      std::_Deallocate<16>(
        lpName[0],
        (const struct std::nothrow_t *)(2 * ((signed __int64)(v26 - (unsigned __int64)lpName[0]) >> 1)));
      *(_OWORD *)lpName = 0;
      v26 = 0;
    }
    return 1;
  }
}

```

## disassembly

```asm
0x18001bdb0  mov     [rsp+arg_8], rbx
0x18001bdb5  mov     [rsp+arg_10], rsi
0x18001bdba  push    rdi
0x18001bdbb  push    r12
0x18001bdbd  push    r13
0x18001bdbf  push    r14
0x18001bdc1  push    r15
0x18001bdc3  sub     rsp, 0E0h
0x18001bdca  mov     rax, cs:__security_cookie
0x18001bdd1  xor     rax, rsp
0x18001bdd4  mov     [rsp+108h+var_38], rax
0x18001bddc  mov     r12, rcx
0x18001bddf  mov     [rsp+108h+var_60], rcx
0x18001bde7  xor     ebx, ebx
0x18001bde9  mov     edi, ebx
0x18001bdeb  mov     [rsp+108h+var_A8], ebx
0x18001bdef  mov     [rsp+108h+cSubKeys], ebx
0x18001bdf3  mov     [rsp+108h+cbMaxSubKeyLen], ebx
0x18001bdf7  mov     [rsp+108h+lpftLastWriteTime], rbx; lpftLastWriteTime
0x18001bdfc  mov     [rsp+108h+lpcbSecurityDescriptor], rbx; lpcbSecurityDescriptor
0x18001be01  mov     [rsp+108h+lpcbMaxValueLen], rbx; lpcbMaxValueLen
0x18001be06  mov     [rsp+108h+lpcbMaxValueNameLen], rbx; lpcbMaxValueNameLen
0x18001be0b  mov     [rsp+108h+lpcValues], rbx; lpcValues
0x18001be10  mov     [rsp+108h+lpcbMaxClassLen], rbx; lpcbMaxClassLen
0x18001be15  lea     rax, [rsp+108h+cbMaxSubKeyLen]
0x18001be1a  mov     [rsp+108h+lpcbMaxSubKeyLen], rax; lpcbMaxSubKeyLen
0x18001be1f  lea     rax, [rsp+108h+cSubKeys]
0x18001be24  mov     [rsp+108h+lpcSubKeys], rax; unsigned int
0x18001be29  xor     r9d, r9d; lpReserved
0x18001be2c  xor     r8d, r8d; lpcchClass
0x18001be2f  xor     edx, edx; lpClass
0x18001be31  call    cs:__imp_RegQueryInfoKeyW
0x18001be37  mov     rcx, [rsp+108h]; this
0x18001be3f  test    eax, eax
0x18001be41  jz      short loc_18001BE56
0x18001be43  mov     r9d, eax; char *
0x18001be46  lea     r8, aOnecoreNetWifi; "onecore\\net\\wificloudstore\\registry"...
0x18001be4d  lea     edx, [rbx+1Eh]; void *
0x18001be50  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x18001be56  mov     edx, [rsp+108h+cbMaxSubKeyLen]
0x18001be5a  inc     edx
0x18001be5c  lea     rcx, [rsp+108h+lpName]
0x18001be64  call    ??0?$vector@GV?$allocator@G@std@@@std@@QEAA@_KAEBV?$allocator@G@1@@Z; std::vector<ushort>::vector<ushort>(unsigned __int64,std::allocator<ushort> const &)
0x18001be69  nop
0x18001be6a  mov     esi, ebx
0x18001be6c  mov     [rsp+108h+var_98], esi
0x18001be70  cmp     esi, [rsp+108h+cSubKeys]
0x18001be74  jnb     loc_18001C11D
0x18001be7a  mov     rax, [rsp+108h+lpName+8]
0x18001be82  mov     r8, [rsp+108h+lpName]; lpName
0x18001be8a  sub     rax, r8
0x18001be8d  sar     rax, 1
0x18001be90  mov     [rsp+108h+cchName], eax
0x18001be97  mov     [rsp+108h+lpcValues], rbx; lpftLastWriteTime
0x18001be9c  mov     [rsp+108h+lpcbMaxClassLen], rbx; lpcchClass
0x18001bea1  mov     [rsp+108h+lpcbMaxSubKeyLen], rbx; lpClass
0x18001bea6  mov     [rsp+108h+lpcSubKeys], rbx; unsigned int
0x18001beab  lea     r9, [rsp+108h+cchName]; lpcchName
0x18001beb3  mov     edx, esi; dwIndex
0x18001beb5  mov     rcx, r12; hKey
0x18001beb8  call    cs:__imp_RegEnumKeyExW
0x18001bebe  mov     rcx, [rsp+108h]; this
0x18001bec6  test    eax, eax
0x18001bec8  jz      short loc_18001BEDE
0x18001beca  mov     r9d, eax; char *
0x18001becd  lea     r8, aOnecoreNetWifi; "onecore\\net\\wificloudstore\\registry"...
0x18001bed4  mov     edx, 29h ; ')'; void *
0x18001bed9  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x18001bede  mov     [rsp+108h+hKey], rbx
0x18001bee6  lea     rcx, [rsp+108h+hKey]
0x18001beee  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(void)
0x18001bef3  mov     [rsp+108h+lpcSubKeys], rax; unsigned int
0x18001bef8  mov     r9d, 20019h; samDesired
0x18001befe  xor     r8d, r8d; ulOptions
0x18001bf01  mov     rdx, [rsp+108h+lpName]; lpSubKey
0x18001bf09  mov     rcx, r12; hKey
0x18001bf0c  call    cs:__imp_RegOpenKeyExW
0x18001bf12  mov     rcx, [rsp+108h]; this
0x18001bf1a  test    eax, eax
0x18001bf1c  jz      short loc_18001BF32
0x18001bf1e  mov     r9d, eax; char *
0x18001bf21  lea     r8, aOnecoreNetWifi; "onecore\\net\\wificloudstore\\registry"...
0x18001bf28  mov     edx, 2Bh ; '+'; void *
0x18001bf2d  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x18001bf32  lea     r14, ?c_allProfileGenerations@WiFiCloudStore@Internal@Windows@@3V?$array@W4ProfileGeneration@WiFiCloudStore@Internal@Windows@@$04@std@@B; std::array<Windows::Internal::WiFiCloudStore::ProfileGeneration,5> const Windows::Internal::WiFiCloudStore::c_allProfileGenerations
0x18001bf39  lea     r13, dword_18024852C
0x18001bf40  cmp     r14, r13
0x18001bf43  jz      loc_18001C0F4
0x18001bf49  mov     [rsp+108h+phkResult], rbx
0x18001bf4e  lea     rcx, [rsp+108h+lpSubKey]
0x18001bf56  cmp     dword ptr [r14], 80000000h
0x18001bf5d  jz      short loc_18001BF80
0x18001bf5f  cmp     dword ptr [r14], 7FFFFFFFh
0x18001bf66  jz      short loc_18001BF72
0x18001bf68  mov     edx, [r14]
0x18001bf6b  call    ?to_wstring@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@H@Z; std::to_wstring(int)
0x18001bf70  jmp     short loc_18001BF8C
0x18001bf72  lea     rdx, aAll_0; "All"
0x18001bf79  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18001bf7e  jmp     short loc_18001BF70
0x18001bf80  lea     rdx, aIrrelevant; "Irrelevant"
0x18001bf87  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18001bf8c  or      edi, 1
0x18001bf8f  mov     [rsp+108h+var_A8], edi
0x18001bf93  mov     rcx, [rsp+108h+lpSubKey]
0x18001bf9b  cmp     [rsp+108h+var_40], 7
0x18001bfa4  setnbe  al
0x18001bfa7  lea     rdx, [rsp+108h+lpSubKey]
0x18001bfaf  test    al, al
0x18001bfb1  cmovnz  rdx, rcx; lpSubKey
0x18001bfb5  lea     rax, [rsp+108h+phkResult]
0x18001bfba  mov     [rsp+108h+lpcSubKeys], rax; unsigned int
0x18001bfbf  mov     r9d, 20019h; samDesired
0x18001bfc5  xor     r8d, r8d; ulOptions
0x18001bfc8  mov     rcx, [rsp+108h+hKey]; hKey
0x18001bfd0  call    cs:__imp_RegOpenKeyExW
0x18001bfd6  mov     r15d, eax
0x18001bfd9  lea     rcx, [rsp+108h+lpSubKey]; void *
0x18001bfe1  call    ??1?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@QEAA@XZ; std::pair<std::wstring,void *>::~pair<std::wstring,void *>(void)
0x18001bfe6  cmp     r15d, 2
0x18001bfea  jz      loc_18001C0DB
0x18001bff0  mov     rcx, [rsp+108h]; this
0x18001bff8  test    r15d, r15d
0x18001bffb  jz      short loc_18001C011
0x18001bffd  mov     r9d, r15d; char *
0x18001c000  lea     r8, aOnecoreNetWifi; "onecore\\net\\wificloudstore\\registry"...
0x18001c007  mov     edx, 35h ; '5'; void *
0x18001c00c  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x18001c011  mov     [rsp+108h+cValues], ebx
0x18001c015  mov     [rsp+108h+lpftLastWriteTime], rbx; lpftLastWriteTime
0x18001c01a  mov     [rsp+108h+lpcbSecurityDescriptor], rbx; lpcbSecurityDescriptor
0x18001c01f  mov     [rsp+108h+lpcbMaxValueLen], rbx; lpcbMaxValueLen
0x18001c024  mov     [rsp+108h+lpcbMaxValueNameLen], rbx; lpcbMaxValueNameLen
0x18001c029  lea     rax, [rsp+108h+cValues]
0x18001c02e  mov     [rsp+108h+lpcValues], rax; lpcValues
0x18001c033  mov     [rsp+108h+lpcbMaxClassLen], rbx; lpcbMaxClassLen
0x18001c038  mov     [rsp+108h+lpcbMaxSubKeyLen], rbx; lpcbMaxSubKeyLen
0x18001c03d  mov     [rsp+108h+lpcSubKeys], rbx; unsigned int
0x18001c042  xor     r9d, r9d; lpReserved
0x18001c045  xor     r8d, r8d; lpcchClass
0x18001c048  xor     edx, edx; lpClass
0x18001c04a  mov     rcx, [rsp+108h+phkResult]; hKey
0x18001c04f  call    cs:__imp_RegQueryInfoKeyW
0x18001c055  mov     rcx, [rsp+108h]; this
0x18001c05d  test    eax, eax
0x18001c05f  jz      short loc_18001C075
0x18001c061  mov     r9d, eax; char *
0x18001c064  lea     r8, aOnecoreNetWifi; "onecore\\net\\wificloudstore\\registry"...
0x18001c06b  mov     edx, 39h ; '9'; void *
0x18001c070  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x18001c075  cmp     [rsp+108h+cValues], ebx
0x18001c079  jbe     short loc_18001C0DB
0x18001c07b  mov     rcx, [rsp+108h+phkResult]; hKey
0x18001c080  test    rcx, rcx
0x18001c083  jz      short loc_18001C08C
0x18001c085  call    cs:__imp_RegCloseKey
0x18001c08b  nop
0x18001c08c  mov     rcx, [rsp+108h+hKey]; hKey
0x18001c094  test    rcx, rcx
0x18001c097  jz      short loc_18001C0A0
0x18001c099  call    cs:__imp_RegCloseKey
0x18001c09f  nop
0x18001c0a0  mov     rcx, [rsp+108h+lpName]
0x18001c0a8  test    rcx, rcx
0x18001c0ab  jz      short loc_18001C0D7
0x18001c0ad  mov     rdx, [rsp+108h+var_68]
0x18001c0b5  sub     rdx, rcx
0x18001c0b8  sar     rdx, 1
0x18001c0bb  add     rdx, rdx
0x18001c0be  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18001c0c3  xorps   xmm0, xmm0
0x18001c0c6  movdqu  xmmword ptr [rsp+108h+lpName], xmm0
0x18001c0cf  mov     [rsp+108h+var_68], rbx
0x18001c0d7  mov     al, 1
0x18001c0d9  jmp     short loc_18001C142
0x18001c0db  mov     rcx, [rsp+108h+phkResult]; hKey
0x18001c0e0  test    rcx, rcx
0x18001c0e3  jz      short loc_18001C0EB
0x18001c0e5  call    cs:__imp_RegCloseKey
0x18001c0eb  add     r14, 4
0x18001c0ef  jmp     loc_18001BF40
0x18001c0f4  lea     rcx, [rsp+108h+hKey]
0x18001c0fc  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18001c101  nop
0x18001c102  jmp     short loc_18001C116
0x18001c104  xor     ebx, ebx
0x18001c106  mov     esi, [rsp+108h+var_98]
0x18001c10a  mov     edi, [rsp+108h+var_A8]
0x18001c10e  mov     r12, [rsp+108h+var_60]
0x18001c116  inc     esi
0x18001c118  jmp     loc_18001BE6C
0x18001c11d  mov     rcx, [rsp+108h+lpName]
0x18001c125  test    rcx, rcx
0x18001c128  jz      short loc_18001C140
0x18001c12a  mov     rdx, [rsp+108h+var_68]
0x18001c132  sub     rdx, rcx
0x18001c135  sar     rdx, 1
0x18001c138  add     rdx, rdx
0x18001c13b  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18001c140  xor     al, al
0x18001c142  mov     rcx, [rsp+108h+var_38]
0x18001c14a  xor     rcx, rsp; StackCookie
0x18001c14d  call    __security_check_cookie
0x18001c152  lea     r11, [rsp+108h+var_28]
0x18001c15a  mov     rbx, [r11+38h]
0x18001c15e  mov     rsi, [r11+40h]
0x18001c162  mov     rsp, r11
0x18001c165  pop     r15
0x18001c167  pop     r14
0x18001c169  pop     r13
0x18001c16b  pop     r12
0x18001c16d  pop     rdi
0x18001c16e  retn
```
