# VersionUtils::ReadCurrentOSVersion(void)

- ea: `0x1800181c0`
- end: `0x18001867c`
- name: `?ReadCurrentOSVersion@VersionUtils@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ`
- size: `1212`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `3`
- callee_count: `13`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1800155cc`
- `0x1800165e0`
- `0x180017ec8`

## callees

- `0x180003110`
- `0x18000a230`
- `0x1800101fc`
- `0x180010278`
- `0x18001331c`
- `0x180013340`
- `0x1800142a0`
- `0x180014b08`
- `0x1800181c0`
- `0x180019efc`
- `0x18001a718`
- `0x18004f448`
- `0x18004f580`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800182d7`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001832f`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180018388`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800183e1`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800184b7`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800182d7`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001832f`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180018388`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800183e1`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800184b7`

## string_xrefs

- `0x180018267`: `onecore\base\flighting\common\inc\VersionUtils.h`
- `0x1800182ec`: `onecore\base\flighting\common\inc\VersionUtils.h`
- `0x180018344`: `onecore\base\flighting\common\inc\VersionUtils.h`
- `0x18001839d`: `onecore\base\flighting\common\inc\VersionUtils.h`
- `0x1800183f6`: `onecore\base\flighting\common\inc\VersionUtils.h`
- `0x18001846f`: `onecore\base\flighting\common\inc\VersionUtils.h`
- `0x1800184cc`: `onecore\base\flighting\common\inc\VersionUtils.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=11 #try_helpers=1
HKEY __fastcall VersionUtils::ReadCurrentOSVersion(HKEY a1)
{
  unsigned int v2; // r8d
  int v3; // ecx
  char v4; // di
  char v5; // al
  unsigned int ValueW; // eax
  unsigned int v8; // eax
  unsigned int v9; // eax
  unsigned int v10; // eax
  unsigned int v11; // r8d
  int v12; // eax
  unsigned int v13; // eax
  __int64 v14; // rax
  __int64 v15; // rax
  __int64 v16; // rax
  __int64 v17; // rax
  __int64 v18; // rax
  int pdwType; // [rsp+20h] [rbp-5E8h]
  unsigned int pdwTypea; // [rsp+20h] [rbp-5E8h]
  unsigned int pdwTypeb; // [rsp+20h] [rbp-5E8h]
  unsigned int pdwTypec; // [rsp+20h] [rbp-5E8h]
  unsigned int pdwTyped; // [rsp+20h] [rbp-5E8h]
  unsigned int pdwTypee; // [rsp+20h] [rbp-5E8h]
  DWORD pcbData; // [rsp+40h] [rbp-5C8h] BYREF
  HKEY hkey; // [rsp+48h] [rbp-5C0h] BYREF
  int v27; // [rsp+50h] [rbp-5B8h] BYREF
  int v28; // [rsp+54h] [rbp-5B4h] BYREF
  int v29; // [rsp+58h] [rbp-5B0h] BYREF
  int v30; // [rsp+5Ch] [rbp-5ACh] BYREF
  int pvData; // [rsp+60h] [rbp-5A8h] BYREF
  HKEY v32[3]; // [rsp+68h] [rbp-5A0h] BYREF
  _BYTE v33[32]; // [rsp+80h] [rbp-588h] BYREF
  _BYTE v34[32]; // [rsp+A0h] [rbp-568h] BYREF
  _BYTE v35[32]; // [rsp+C0h] [rbp-548h] BYREF
  _BYTE v36[32]; // [rsp+E0h] [rbp-528h] BYREF
  _BYTE v37[32]; // [rsp+100h] [rbp-508h] BYREF
  _BYTE v38[32]; // [rsp+120h] [rbp-4E8h] BYREF
  _BYTE v39[32]; // [rsp+140h] [rbp-4C8h] BYREF
  _BYTE v40[32]; // [rsp+160h] [rbp-4A8h] BYREF
  _BYTE v41[32]; // [rsp+180h] [rbp-488h] BYREF
  _BYTE v42[528]; // [rsp+1A0h] [rbp-468h] BYREF
  _BYTE v43[528]; // [rsp+3B0h] [rbp-258h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+608h] [rbp+0h]

  v32[1] = a1;
  hkey = 0;
  RegPersistedKey::RegPersistedKey(
    (RegPersistedKey *)v42,
    L"FeatureManagement",
    L"SYSTEM\\Software\\Microsoft\\BuildLayers");
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &hkey,
    0);
  v3 = RegPersistedKey::RegOpenKeyW((RegPersistedKey *)v42, L"DesktopEditions", v2, &hkey);
  if ( (int)(v3 + 0x80000000) < 0 || v3 == -2147024894 )
  {
    v5 = 0;
    v4 = 1;
  }
  else
  {
    v4 = 1;
    v5 = 1;
  }
  if ( v5 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x55,
      (unsigned int)"onecore\\base\\flighting\\common\\inc\\VersionUtils.h",
      (const char *)(unsigned int)v3,
      pdwType);
  if ( v3 >= 0 )
  {
    pvData = 0;
    pcbData = 4;
    ValueW = RegGetValueW(hkey, 0, L"MajorVersion", 0x10u, 0, &pvData, &pcbData);
    if ( ValueW )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x5D,
        (unsigned int)"onecore\\base\\flighting\\common\\inc\\VersionUtils.h",
        (const char *)ValueW,
        pdwTypea);
    v30 = 0;
    pcbData = 4;
    v8 = RegGetValueW(hkey, 0, L"MinorVersion", 0x10u, 0, &v30, &pcbData);
    if ( v8 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x61,
        (unsigned int)"onecore\\base\\flighting\\common\\inc\\VersionUtils.h",
        (const char *)v8,
        pdwTypeb);
    v29 = 0;
    pcbData = 4;
    v9 = RegGetValueW(hkey, 0, L"BuildNumber", 0x10u, 0, &v29, &pcbData);
    if ( v9 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x65,
        (unsigned int)"onecore\\base\\flighting\\common\\inc\\VersionUtils.h",
        (const char *)v9,
        pdwTypec);
    v27 = 0;
    pcbData = 4;
    v10 = RegGetValueW(hkey, 0, L"BuildQfe", 0x10u, 0, &v27, &pcbData);
    if ( v10 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x69,
        (unsigned int)"onecore\\base\\flighting\\common\\inc\\VersionUtils.h",
        (const char *)v10,
        pdwTyped);
    v32[0] = 0;
    RegPersistedKey::RegPersistedKey(
      (RegPersistedKey *)v43,
      L"FeatureManagement",
      L"SYSTEM\\Software\\Microsoft\\ServicingLayers");
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
      v32,
      0);
    v12 = RegPersistedKey::RegOpenKeyW((RegPersistedKey *)v43, L"_EDITION_", v11, v32);
    if ( ((v12 + 0x80000000) & 0x80000000) != 0 || v12 == -2147024894 )
      v4 = 0;
    if ( v4 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x6F,
        (unsigned int)"onecore\\base\\flighting\\common\\inc\\VersionUtils.h",
        (const char *)(unsigned int)v12,
        pdwTyped);
    if ( v12 >= 0 )
    {
      v28 = 0;
      pcbData = 4;
      v13 = RegGetValueW(v32[0], 0, L"BuildQfe", 0x10u, 0, &v28, &pcbData);
      if ( v13 )
        wil::details::in1diag3::Throw_Win32(
          retaddr,
          (void *)0x74,
          (unsigned int)"onecore\\base\\flighting\\common\\inc\\VersionUtils.h",
          (const char *)v13,
          pdwTypee);
      v27 = v28;
    }
    std::_Integral_to_string<unsigned short,unsigned long>(v36);
    std::_Integral_to_string<unsigned short,unsigned long>(v35);
    std::_Integral_to_string<unsigned short,unsigned long>(v34);
    std::_Integral_to_string<unsigned short,unsigned long>(v33);
    v14 = std::operator+<unsigned short>(v41, v33, L".");
    v15 = std::operator+<unsigned short>(v40, v14, v34);
    v16 = std::operator+<unsigned short>(v39, v15, L".");
    v17 = std::operator+<unsigned short>(v38, v16, v35);
    v18 = std::operator+<unsigned short>(v37, v17, L".");
    std::operator+<unsigned short>(a1, v18, v36);
    std::wstring::_Tidy_deallocate(v37);
    std::wstring::_Tidy_deallocate(v38);
    std::wstring::_Tidy_deallocate(v39);
    std::wstring::_Tidy_deallocate(v40);
    std::wstring::_Tidy_deallocate(v41);
    std::wstring::_Tidy_deallocate(v33);
    std::wstring::_Tidy_deallocate(v34);
    std::wstring::_Tidy_deallocate(v35);
    std::wstring::_Tidy_deallocate(v36);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(v32);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
    return a1;
  }
  else
  {
    std::wstring::wstring(a1);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
    return a1;
  }
}

```

## disassembly

```asm
0x1800181c0  push    rbx
0x1800181c2  push    rsi
0x1800181c3  push    rdi
0x1800181c4  push    r12
0x1800181c6  push    r14
0x1800181c8  push    r15
0x1800181ca  sub     rsp, 5D8h
0x1800181d1  mov     rax, cs:__security_cookie
0x1800181d8  xor     rax, rsp
0x1800181db  mov     [rsp+608h+var_48], rax
0x1800181e3  mov     rbx, rcx
0x1800181e6  mov     [rsp+608h+var_598], rcx
0x1800181eb  xor     esi, esi
0x1800181ed  mov     [rsp+608h+hkey], rsi
0x1800181f2  lea     r8, aSystemSoftware; "SYSTEM\\Software\\Microsoft\\BuildLayer"...
0x1800181f9  lea     rdx, aFeaturemanagem; "FeatureManagement"
0x180018200  lea     rcx, [rsp+608h+var_468]; this
0x180018208  call    ??0RegPersistedKey@@QEAA@PEBG0@Z; RegPersistedKey::RegPersistedKey(ushort const *,ushort const *)
0x18001820d  xor     edx, edx
0x18001820f  lea     rcx, [rsp+608h+hkey]
0x180018214  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x180018219  lea     r9, [rsp+608h+hkey]; HKEY *
0x18001821e  lea     rdx, aDesktopedition; "DesktopEditions"
0x180018225  lea     rcx, [rsp+608h+var_468]; this
0x18001822d  call    ?RegOpenKeyW@RegPersistedKey@@QEAAJPEBGKPEAPEAUHKEY__@@@Z; RegPersistedKey::RegOpenKeyW(ushort const *,ulong,HKEY__ * *)
0x180018232  mov     ecx, eax
0x180018234  mov     r12d, 80000000h
0x18001823a  add     eax, r12d
0x18001823d  test    r12d, eax
0x180018240  jnz     short loc_180018252
0x180018242  cmp     ecx, 80070002h
0x180018248  jz      short loc_180018252
0x18001824a  mov     dil, 1
0x18001824d  mov     al, dil
0x180018250  jmp     short loc_180018258
0x180018252  mov     al, sil
0x180018255  mov     dil, 1
0x180018258  mov     r10, [rsp+608h]
0x180018260  test    al, al
0x180018262  jz      short loc_18001827B
0x180018264  mov     r9d, ecx; char *
0x180018267  lea     r8, aOnecoreBaseFli_12; "onecore\\base\\flighting\\common\\inc\\"...
0x18001826e  mov     edx, 55h ; 'U'; void *
0x180018273  mov     rcx, r10; this
0x180018276  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001827b  test    ecx, ecx
0x18001827d  jns     short loc_18001829A
0x18001827f  mov     rcx, rbx
0x180018282  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180018287  nop
0x180018288  lea     rcx, [rsp+608h+hkey]
0x18001828d  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180018292  mov     rax, rbx
0x180018295  jmp     loc_18001865A
0x18001829a  mov     [rsp+608h+var_5A8], esi
0x18001829e  mov     r14d, 4
0x1800182a4  mov     [rsp+608h+var_5C8], r14d
0x1800182a9  lea     rax, [rsp+608h+var_5C8]
0x1800182ae  mov     [rsp+608h+pcbData], rax; pcbData
0x1800182b3  lea     rax, [rsp+608h+var_5A8]
0x1800182b8  mov     [rsp+608h+pvData], rax; pvData
0x1800182bd  mov     [rsp+608h+pdwType], rsi; unsigned int
0x1800182c2  lea     r15d, [r14+0Ch]
0x1800182c6  mov     r9d, r15d; dwFlags
0x1800182c9  lea     r8, Value; "MajorVersion"
0x1800182d0  xor     edx, edx; lpSubKey
0x1800182d2  mov     rcx, [rsp+608h+hkey]; hkey
0x1800182d7  call    cs:__imp_RegGetValueW
0x1800182dd  mov     rcx, [rsp+608h]; this
0x1800182e5  test    eax, eax
0x1800182e7  jz      short loc_1800182FC
0x1800182e9  mov     r9d, eax; char *
0x1800182ec  lea     r8, aOnecoreBaseFli_12; "onecore\\base\\flighting\\common\\inc\\"...
0x1800182f3  lea     edx, [r14+59h]; void *
0x1800182f7  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x1800182fc  mov     [rsp+608h+var_5AC], esi
0x180018300  mov     [rsp+608h+var_5C8], r14d
0x180018305  lea     rax, [rsp+608h+var_5C8]
0x18001830a  mov     [rsp+608h+pcbData], rax; pcbData
0x18001830f  lea     rax, [rsp+608h+var_5AC]
0x180018314  mov     [rsp+608h+pvData], rax; pvData
0x180018319  mov     [rsp+608h+pdwType], rsi; unsigned int
0x18001831e  mov     r9d, r15d; dwFlags
0x180018321  lea     r8, aMinorversion; "MinorVersion"
0x180018328  xor     edx, edx; lpSubKey
0x18001832a  mov     rcx, [rsp+608h+hkey]; hkey
0x18001832f  call    cs:__imp_RegGetValueW
0x180018335  mov     rcx, [rsp+608h]; this
0x18001833d  test    eax, eax
0x18001833f  jz      short loc_180018355
0x180018341  mov     r9d, eax; char *
0x180018344  lea     r8, aOnecoreBaseFli_12; "onecore\\base\\flighting\\common\\inc\\"...
0x18001834b  mov     edx, 61h ; 'a'; void *
0x180018350  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x180018355  mov     [rsp+608h+var_5B0], esi
0x180018359  mov     [rsp+608h+var_5C8], r14d
0x18001835e  lea     rax, [rsp+608h+var_5C8]
0x180018363  mov     [rsp+608h+pcbData], rax; pcbData
0x180018368  lea     rax, [rsp+608h+var_5B0]
0x18001836d  mov     [rsp+608h+pvData], rax; pvData
0x180018372  mov     [rsp+608h+pdwType], rsi; unsigned int
0x180018377  mov     r9d, r15d; dwFlags
0x18001837a  lea     r8, aBuildnumber; "BuildNumber"
0x180018381  xor     edx, edx; lpSubKey
0x180018383  mov     rcx, [rsp+608h+hkey]; hkey
0x180018388  call    cs:__imp_RegGetValueW
0x18001838e  mov     rcx, [rsp+608h]; this
0x180018396  test    eax, eax
0x180018398  jz      short loc_1800183AE
0x18001839a  mov     r9d, eax; char *
0x18001839d  lea     r8, aOnecoreBaseFli_12; "onecore\\base\\flighting\\common\\inc\\"...
0x1800183a4  mov     edx, 65h ; 'e'; void *
0x1800183a9  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x1800183ae  mov     [rsp+608h+var_5B8], esi
0x1800183b2  mov     [rsp+608h+var_5C8], r14d
0x1800183b7  lea     rax, [rsp+608h+var_5C8]
0x1800183bc  mov     [rsp+608h+pcbData], rax; pcbData
0x1800183c1  lea     rax, [rsp+608h+var_5B8]
0x1800183c6  mov     [rsp+608h+pvData], rax; pvData
0x1800183cb  mov     [rsp+608h+pdwType], rsi; int
0x1800183d0  mov     r9d, r15d; dwFlags
0x1800183d3  lea     r8, aBuildqfe; "BuildQfe"
0x1800183da  xor     edx, edx; lpSubKey
0x1800183dc  mov     rcx, [rsp+608h+hkey]; hkey
0x1800183e1  call    cs:__imp_RegGetValueW
0x1800183e7  mov     rcx, [rsp+608h]; this
0x1800183ef  test    eax, eax
0x1800183f1  jz      short loc_180018407
0x1800183f3  mov     r9d, eax; char *
0x1800183f6  lea     r8, aOnecoreBaseFli_12; "onecore\\base\\flighting\\common\\inc\\"...
0x1800183fd  mov     edx, 69h ; 'i'; void *
0x180018402  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x180018407  mov     [rsp+608h+var_5A0], rsi
0x18001840c  lea     r8, aSystemSoftware_0; "SYSTEM\\Software\\Microsoft\\ServicingL"...
0x180018413  lea     rdx, aFeaturemanagem; "FeatureManagement"
0x18001841a  lea     rcx, [rsp+608h+var_258]; this
0x180018422  call    ??0RegPersistedKey@@QEAA@PEBG0@Z; RegPersistedKey::RegPersistedKey(ushort const *,ushort const *)
0x180018427  xor     edx, edx
0x180018429  lea     rcx, [rsp+608h+var_5A0]
0x18001842e  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x180018433  lea     r9, [rsp+608h+var_5A0]; HKEY *
0x180018438  lea     rdx, aEdition; "_EDITION_"
0x18001843f  lea     rcx, [rsp+608h+var_258]; this
0x180018447  call    ?RegOpenKeyW@RegPersistedKey@@QEAAJPEBGKPEAPEAUHKEY__@@@Z; RegPersistedKey::RegOpenKeyW(ushort const *,ulong,HKEY__ * *)
0x18001844c  lea     ecx, [rax+r12]
0x180018450  test    r12d, ecx
0x180018453  jnz     short loc_18001845C
0x180018455  cmp     eax, 80070002h
0x18001845a  jnz     short loc_18001845F
0x18001845c  mov     dil, sil
0x18001845f  mov     rcx, [rsp+608h]; this
0x180018467  test    dil, dil
0x18001846a  jz      short loc_180018480
0x18001846c  mov     r9d, eax; char *
0x18001846f  lea     r8, aOnecoreBaseFli_12; "onecore\\base\\flighting\\common\\inc\\"...
0x180018476  mov     edx, 6Fh ; 'o'; void *
0x18001847b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180018480  test    eax, eax
0x180018482  js      short loc_1800184E7
0x180018484  mov     [rsp+608h+var_5B4], esi
0x180018488  mov     [rsp+608h+var_5C8], r14d
0x18001848d  lea     rax, [rsp+608h+var_5C8]
0x180018492  mov     [rsp+608h+pcbData], rax; pcbData
0x180018497  lea     rax, [rsp+608h+var_5B4]
0x18001849c  mov     [rsp+608h+pvData], rax; pvData
0x1800184a1  mov     [rsp+608h+pdwType], rsi; unsigned int
0x1800184a6  mov     r9d, r15d; dwFlags
0x1800184a9  lea     r8, aBuildqfe; "BuildQfe"
0x1800184b0  xor     edx, edx; lpSubKey
0x1800184b2  mov     rcx, [rsp+608h+var_5A0]; hkey
0x1800184b7  call    cs:__imp_RegGetValueW
0x1800184bd  mov     rcx, [rsp+608h]; this
0x1800184c5  test    eax, eax
0x1800184c7  jz      short loc_1800184DD
0x1800184c9  mov     r9d, eax; char *
0x1800184cc  lea     r8, aOnecoreBaseFli_12; "onecore\\base\\flighting\\common\\inc\\"...
0x1800184d3  mov     edx, 74h ; 't'; void *
0x1800184d8  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x1800184dd  mov     edx, [rsp+608h+var_5B4]
0x1800184e1  mov     [rsp+608h+var_5B8], edx
0x1800184e5  jmp     short loc_1800184EB
0x1800184e7  mov     edx, [rsp+608h+var_5B8]
0x1800184eb  lea     rcx, [rsp+608h+var_528]
0x1800184f3  call    ??$_Integral_to_string@GK@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@K@Z; std::_Integral_to_string<ushort,ulong>(ulong)
0x1800184f8  nop
0x1800184f9  mov     edx, [rsp+608h+var_5B0]
0x1800184fd  lea     rcx, [rsp+608h+var_548]
0x180018505  call    ??$_Integral_to_string@GK@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@K@Z; std::_Integral_to_string<ushort,ulong>(ulong)
0x18001850a  nop
0x18001850b  mov     edx, [rsp+608h+var_5AC]
0x18001850f  lea     rcx, [rsp+608h+var_568]
0x180018517  call    ??$_Integral_to_string@GK@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@K@Z; std::_Integral_to_string<ushort,ulong>(ulong)
0x18001851c  nop
0x18001851d  mov     edx, [rsp+608h+var_5A8]
0x180018521  lea     rcx, [rsp+608h+var_588]
0x180018529  call    ??$_Integral_to_string@GK@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@K@Z; std::_Integral_to_string<ushort,ulong>(ulong)
0x18001852e  nop
0x18001852f  lea     rdi, asc_180060104; "."
0x180018536  mov     r8, rdi
0x180018539  lea     rdx, [rsp+608h+var_588]
0x180018541  lea     rcx, [rsp+608h+var_488]
0x180018549  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@QEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const * const)
0x18001854e  nop
0x18001854f  lea     r8, [rsp+608h+var_568]
0x180018557  mov     rdx, rax
0x18001855a  lea     rcx, [rsp+608h+var_4A8]
0x180018562  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@0@Z; std::operator+<ushort>(std::wstring &&,std::wstring &&)
0x180018567  nop
0x180018568  mov     r8, rdi
0x18001856b  mov     rdx, rax
0x18001856e  lea     rcx, [rsp+608h+var_4C8]
0x180018576  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@QEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const * const)
0x18001857b  nop
0x18001857c  lea     r8, [rsp+608h+var_548]
0x180018584  mov     rdx, rax
0x180018587  lea     rcx, [rsp+608h+var_4E8]
0x18001858f  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@0@Z; std::operator+<ushort>(std::wstring &&,std::wstring &&)
0x180018594  nop
0x180018595  mov     r8, rdi
0x180018598  mov     rdx, rax
0x18001859b  lea     rcx, [rsp+608h+var_508]
0x1800185a3  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@QEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const * const)
0x1800185a8  nop
0x1800185a9  lea     r8, [rsp+608h+var_528]
0x1800185b1  mov     rdx, rax
0x1800185b4  mov     rcx, rbx
0x1800185b7  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@0@Z; std::operator+<ushort>(std::wstring &&,std::wstring &&)
0x1800185bc  nop
0x1800185bd  lea     rcx, [rsp+608h+var_508]
0x1800185c5  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800185ca  nop
0x1800185cb  lea     rcx, [rsp+608h+var_4E8]
0x1800185d3  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800185d8  nop
0x1800185d9  lea     rcx, [rsp+608h+var_4C8]
0x1800185e1  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800185e6  nop
0x1800185e7  lea     rcx, [rsp+608h+var_4A8]
0x1800185ef  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800185f4  nop
0x1800185f5  lea     rcx, [rsp+608h+var_488]
0x1800185fd  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180018602  nop
0x180018603  lea     rcx, [rsp+608h+var_588]
0x18001860b  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180018610  nop
0x180018611  lea     rcx, [rsp+608h+var_568]
0x180018619  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001861e  nop
0x18001861f  lea     rcx, [rsp+608h+var_548]
0x180018627  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001862c  nop
0x18001862d  lea     rcx, [rsp+608h+var_528]
0x180018635  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001863a  nop
0x18001863b  lea     rcx, [rsp+608h+var_5A0]
0x180018640  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180018645  nop
0x180018646  lea     rcx, [rsp+608h+hkey]
0x18001864b  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180018650  mov     rax, rbx
0x180018653  jmp     short loc_18001865A
0x180018655  mov     rax, [rsp+608h+var_598]
0x18001865a  mov     rcx, [rsp+608h+var_48]
0x180018662  xor     rcx, rsp; StackCookie
0x180018665  call    __security_check_cookie
0x18001866a  add     rsp, 5D8h
0x180018671  pop     r15
0x180018673  pop     r14
0x180018675  pop     r12
0x180018677  pop     rdi
0x180018678  pop     rsi
0x180018679  pop     rbx
0x18001867a  retn
```
