# Windows::UI::ViewManagement::UISettings::get_MessageDuration(uint *)

- ea: `0x180030dc0`
- end: `0x180030f22`
- name: `?get_MessageDuration@UISettings@ViewManagement@UI@Windows@@UEAAJPEAI@Z`
- size: `354`
- prototype: `__int64 __fastcall(Windows::UI::ViewManagement::UISettings *__hidden this, unsigned int *)`
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config`

## callees

- `0x180014754`
- `0x180030dc0`
- `0x180031368`
- `0x180031410`
- `0x180031430`
- `0x18004ed78`
- `0x1800581b8`
- `0x180061740`
- `0x180084ef0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180030ede`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180030ede`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180030e4c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180030e4c`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!SystemParametersInfoW` at `0x180030dff`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!SystemParametersInfoW` at `0x180030dff`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Windows::UI::ViewManagement::UISettings::get_MessageDuration(
        Windows::UI::ViewManagement::UISettings *this,
        unsigned int *a2)
{
  __int64 v3; // rdx
  __int64 v4; // rcx
  __int64 v5; // r8
  const char *v6; // r9
  unsigned int v7; // edi
  int OneCoreRegistryKey; // eax
  HKEY v10; // rbx
  unsigned int v11; // ebx
  unsigned int ValueW; // eax
  int pdwType; // [rsp+20h] [rbp-20h]
  unsigned int pdwTypea; // [rsp+20h] [rbp-20h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+18h]
  unsigned int pvParam; // [rsp+68h] [rbp+28h] BYREF
  DWORD pcbData; // [rsp+70h] [rbp+30h] BYREF
  HKEY hKey; // [rsp+78h] [rbp+38h] BYREF

  *a2 = 0;
  if ( !(unsigned __int8)anonymous_namespace_::IsDesktop(this) )
  {
    v7 = 5;
    hKey = 0;
    OneCoreRegistryKey = anonymous_namespace_::GetOneCoreRegistryKey(&hKey, v3, v5);
    if ( OneCoreRegistryKey < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x295,
        (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\uisettings\\uisettings.cpp",
        (const char *)(unsigned int)OneCoreRegistryKey,
        pdwType);
    v10 = hKey;
    if ( hKey )
    {
      pvParam = 0;
      pcbData = 4;
      ValueW = RegGetValueW(hKey, 0, L"MessageDuration", 0x10u, 0, &pvParam, &pcbData);
      if ( ValueW )
      {
        if ( ValueW != 2 )
        {
          v11 = wil::details::in1diag3::Return_Win32(
                  retaddr,
                  (void *)0x2AA,
                  (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\uisettings\\uisettings.cpp",
                  (const char *)ValueW,
                  pdwTypea);
          wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
          return v11;
        }
      }
      else
      {
        v7 = pvParam;
      }
    }
    if ( v10 )
      RegCloseKey(v10);
    goto LABEL_5;
  }
  pvParam = 0;
  if ( !(unsigned __int8)IsSystemParametersInfoWPresent(v4) )
  {
    v11 = -2147467263;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x28E,
      (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\uisettings\\uisettings.cpp",
      (const char *)0x80004001LL,
      pdwType);
    return v11;
  }
  if ( SystemParametersInfoW(0x2016u, 0, &pvParam, 0) )
  {
    v7 = pvParam;
LABEL_5:
    *a2 = v7;
    return 0;
  }
  return wil::details::in1diag3::Return_GetLastError(
           retaddr,
           (void *)0x28F,
           (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\uisettings\\uisettings.cpp",
           v6);
}

```

## disassembly

```asm
0x180030dc0  mov     [rsp-18h+arg_0], rbx
0x180030dc5  push    rbp
0x180030dc6  push    rsi
0x180030dc7  push    rdi
0x180030dc8  mov     rbp, rsp
0x180030dcb  sub     rsp, 40h
0x180030dcf  mov     rsi, rdx
0x180030dd2  mov     dword ptr [rdx], 0
0x180030dd8  call    _anonymous_namespace___IsDesktop
0x180030ddd  test    al, al
0x180030ddf  jz      short loc_180030E1D
0x180030de1  mov     [rbp+pvParam], 0
0x180030de8  call    IsSystemParametersInfoWPresent
0x180030ded  test    al, al
0x180030def  jz      short loc_180030E55
0x180030df1  xor     r9d, r9d; fWinIni
0x180030df4  lea     r8, [rbp+pvParam]; pvParam
0x180030df8  xor     edx, edx; uiParam
0x180030dfa  mov     ecx, 2016h; uiAction
0x180030dff  call    cs:__imp_SystemParametersInfoW
0x180030e05  test    eax, eax
0x180030e07  jz      short loc_180030E76
0x180030e09  mov     edi, [rbp+pvParam]
0x180030e0c  mov     [rsi], edi
0x180030e0e  xor     eax, eax
0x180030e10  mov     rbx, [rsp+40h+arg_0]
0x180030e15  add     rsp, 40h
0x180030e19  pop     rdi
0x180030e1a  pop     rsi
0x180030e1b  pop     rbp
0x180030e1c  retn
0x180030e1d  mov     edi, 5
0x180030e22  mov     [rbp+hKey], 0
0x180030e2a  lea     rcx, [rbp+hKey]
0x180030e2e  call    _anonymous_namespace___GetOneCoreRegistryKey
0x180030e33  mov     rcx, [rbp+18h]; this
0x180030e37  test    eax, eax
0x180030e39  js      short loc_180030E8D
0x180030e3b  mov     rbx, [rbp+hKey]
0x180030e3f  test    rbx, rbx
0x180030e42  jnz     short loc_180030EA3
0x180030e44  test    rbx, rbx
0x180030e47  jz      short loc_180030E53
0x180030e49  mov     rcx, rbx; hKey
0x180030e4c  call    cs:__imp_RegCloseKey
0x180030e52  nop
0x180030e53  jmp     short loc_180030E0C
0x180030e55  mov     rcx, [rbp+18h]; this
0x180030e59  mov     ebx, 80004001h
0x180030e5e  mov     r9d, ebx; char *
0x180030e61  lea     r8, aOnecoreuapWind_21; "onecoreuap\\windows\\advcore\\winrt\\ui"...
0x180030e68  mov     edx, 28Eh; void *
0x180030e6d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180030e72  mov     eax, ebx
0x180030e74  jmp     short loc_180030E10
0x180030e76  mov     rcx, [rbp+18h]; this
0x180030e7a  lea     r8, aOnecoreuapWind_21; "onecoreuap\\windows\\advcore\\winrt\\ui"...
0x180030e81  mov     edx, 28Fh; void *
0x180030e86  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180030e8b  jmp     short loc_180030E10
0x180030e8d  mov     r9d, eax; char *
0x180030e90  lea     r8, aOnecoreuapWind_21; "onecoreuap\\windows\\advcore\\winrt\\ui"...
0x180030e97  mov     edx, 295h; void *
0x180030e9c  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180030ea1  jmp     short loc_180030E3B
0x180030ea3  mov     [rbp+pvParam], 0
0x180030eaa  mov     [rbp+arg_10], 4
0x180030eb1  lea     rax, [rbp+arg_10]
0x180030eb5  mov     [rsp+40h+pcbData], rax; pcbData
0x180030eba  lea     rax, [rbp+pvParam]
0x180030ebe  mov     [rsp+40h+pvData], rax; pvData
0x180030ec3  mov     [rsp+40h+pdwType], 0; unsigned int
0x180030ecc  mov     r9d, 10h; dwFlags
0x180030ed2  lea     r8, aMessageduratio; "MessageDuration"
0x180030ed9  xor     edx, edx; lpSubKey
0x180030edb  mov     rcx, rbx; hkey
0x180030ede  call    cs:__imp_RegGetValueW
0x180030ee4  test    eax, eax
0x180030ee6  jnz     short loc_180030EF0
0x180030ee8  mov     edi, [rbp+pvParam]
0x180030eeb  jmp     loc_180030E44
0x180030ef0  cmp     eax, 2
0x180030ef3  jz      loc_180030E44
0x180030ef9  mov     rcx, [rbp+18h]; this
0x180030efd  mov     r9d, eax; char *
0x180030f00  lea     r8, aOnecoreuapWind_21; "onecoreuap\\windows\\advcore\\winrt\\ui"...
0x180030f07  mov     edx, 2AAh; void *
0x180030f0c  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180030f11  mov     ebx, eax
0x180030f13  lea     rcx, [rbp+hKey]
0x180030f17  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180030f1c  nop
0x180030f1d  jmp     loc_180030E72
```
