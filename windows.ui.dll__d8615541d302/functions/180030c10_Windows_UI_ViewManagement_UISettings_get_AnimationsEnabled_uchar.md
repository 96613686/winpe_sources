# Windows::UI::ViewManagement::UISettings::get_AnimationsEnabled(uchar *)

- ea: `0x180030c10`
- end: `0x180030db1`
- name: `?get_AnimationsEnabled@UISettings@ViewManagement@UI@Windows@@UEAAJPEAE@Z`
- size: `417`
- prototype: `__int64 __fastcall(Windows::UI::ViewManagement::UISettings *__hidden this, unsigned __int8 *)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, loader_planting`

## callees

- `0x180014754`
- `0x180030c10`
- `0x180031410`
- `0x180031430`
- `0x18004ed78`
- `0x1800581b8`
- `0x180061740`
- `0x180084ef0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180030d69`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180030d69`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180030cee`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180030cee`
- `ntdll!RtlIsMultiSessionSku` at `0x180030d12`
- `ntdll!RtlIsMultiSessionSku` at `0x180030d12`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x180030c35`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x180030c35`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!SystemParametersInfoW` at `0x180030c65`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!SystemParametersInfoW` at `0x180030c65`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Windows::UI::ViewManagement::UISettings::get_AnimationsEnabled(
        Windows::UI::ViewManagement::UISettings *this,
        bool *a2)
{
  __int64 v3; // rdx
  __int64 v4; // rcx
  __int64 v5; // r8
  int v6; // eax
  const char *v7; // r9
  bool v8; // di
  unsigned int v10; // ebx
  int OneCoreRegistryKey; // eax
  HKEY v12; // rbx
  unsigned int ValueW; // eax
  int pdwType; // [rsp+20h] [rbp-20h]
  unsigned int pdwTypea; // [rsp+20h] [rbp-20h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+18h]
  int pvParam; // [rsp+68h] [rbp+28h] BYREF
  DWORD pcbData; // [rsp+70h] [rbp+30h] BYREF
  HKEY hKey; // [rsp+78h] [rbp+38h] BYREF

  *a2 = 0;
  pvParam = 0;
  RtlGetDeviceFamilyInfoEnum(0, &pvParam, 0);
  v6 = pvParam;
  if ( pvParam != 3 )
  {
    if ( pvParam == 6 )
    {
      if ( (unsigned __int8)RtlIsMultiSessionSku() )
        goto LABEL_2;
      v6 = pvParam;
    }
    if ( v6 != 9 )
    {
      v8 = 1;
      hKey = 0;
      OneCoreRegistryKey = anonymous_namespace_::GetOneCoreRegistryKey(&hKey, v3, v5);
      if ( OneCoreRegistryKey < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x2C4,
          (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\uisettings\\uisettings.cpp",
          (const char *)(unsigned int)OneCoreRegistryKey,
          pdwType);
      v12 = hKey;
      if ( hKey )
      {
        pvParam = 0;
        pcbData = 4;
        ValueW = RegGetValueW(hKey, 0, L"EnableAnimations", 0x10u, 0, &pvParam, &pcbData);
        if ( ValueW )
        {
          if ( ValueW != 2 )
          {
            v10 = wil::details::in1diag3::Return_Win32(
                    retaddr,
                    (void *)0x2D9,
                    (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\uisettings\\uisettings.cpp",
                    (const char *)ValueW,
                    pdwTypea);
            wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
            return v10;
          }
        }
        else
        {
          v8 = pvParam != 0;
        }
      }
      if ( v12 )
        RegCloseKey(v12);
      goto LABEL_5;
    }
  }
LABEL_2:
  pvParam = 0;
  if ( !(unsigned __int8)IsSystemParametersInfoWPresent(v4) )
  {
    v10 = -2147467263;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2BD,
      (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\uisettings\\uisettings.cpp",
      (const char *)0x80004001LL,
      pdwType);
    return v10;
  }
  if ( SystemParametersInfoW(0x1042u, 0, &pvParam, 0) )
  {
    v8 = pvParam != 0;
LABEL_5:
    *a2 = v8;
    return 0;
  }
  return wil::details::in1diag3::Return_GetLastError(
           retaddr,
           (void *)0x2BE,
           (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\uisettings\\uisettings.cpp",
           v7);
}

```

## disassembly

```asm
0x180030c10  mov     [rsp-18h+arg_0], rbx
0x180030c15  push    rbp
0x180030c16  push    rsi
0x180030c17  push    rdi
0x180030c18  mov     rbp, rsp
0x180030c1b  sub     rsp, 40h
0x180030c1f  mov     rsi, rdx
0x180030c22  mov     byte ptr [rdx], 0
0x180030c25  mov     [rbp+pvParam], 0
0x180030c2c  xor     r8d, r8d
0x180030c2f  lea     rdx, [rbp+pvParam]
0x180030c33  xor     ecx, ecx
0x180030c35  call    cs:__imp_RtlGetDeviceFamilyInfoEnum
0x180030c3b  mov     eax, [rbp+pvParam]
0x180030c3e  cmp     eax, 3
0x180030c41  jnz     loc_180030D0D
0x180030c47  mov     [rbp+pvParam], 0
0x180030c4e  call    IsSystemParametersInfoWPresent
0x180030c53  test    al, al
0x180030c55  jz      short loc_180030C89
0x180030c57  xor     r9d, r9d; fWinIni
0x180030c5a  lea     r8, [rbp+pvParam]; pvParam
0x180030c5e  xor     edx, edx; uiParam
0x180030c60  mov     ecx, 1042h; uiAction
0x180030c65  call    cs:__imp_SystemParametersInfoW
0x180030c6b  test    eax, eax
0x180030c6d  jz      short loc_180030CAA
0x180030c6f  cmp     [rbp+pvParam], 0
0x180030c73  setnz   dil
0x180030c77  mov     [rsi], dil
0x180030c7a  xor     eax, eax
0x180030c7c  mov     rbx, [rsp+40h+arg_0]
0x180030c81  add     rsp, 40h
0x180030c85  pop     rdi
0x180030c86  pop     rsi
0x180030c87  pop     rbp
0x180030c88  retn
0x180030c89  mov     rcx, [rbp+18h]; this
0x180030c8d  mov     ebx, 80004001h
0x180030c92  mov     r9d, ebx; char *
0x180030c95  lea     r8, aOnecoreuapWind_21; "onecoreuap\\windows\\advcore\\winrt\\ui"...
0x180030c9c  mov     edx, 2BDh; void *
0x180030ca1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180030ca6  mov     eax, ebx
0x180030ca8  jmp     short loc_180030C7C
0x180030caa  mov     rcx, [rbp+18h]; this
0x180030cae  lea     r8, aOnecoreuapWind_21; "onecoreuap\\windows\\advcore\\winrt\\ui"...
0x180030cb5  mov     edx, 2BEh; void *
0x180030cba  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180030cbf  jmp     short loc_180030C7C
0x180030cc1  mov     dil, 1
0x180030cc4  mov     [rbp+hKey], 0
0x180030ccc  lea     rcx, [rbp+hKey]
0x180030cd0  call    _anonymous_namespace___GetOneCoreRegistryKey
0x180030cd5  mov     rcx, [rbp+18h]; this
0x180030cd9  test    eax, eax
0x180030cdb  js      short loc_180030CF7
0x180030cdd  mov     rbx, [rbp+hKey]
0x180030ce1  test    rbx, rbx
0x180030ce4  jnz     short loc_180030D2E
0x180030ce6  test    rbx, rbx
0x180030ce9  jz      short loc_180030CF5
0x180030ceb  mov     rcx, rbx; hKey
0x180030cee  call    cs:__imp_RegCloseKey
0x180030cf4  nop
0x180030cf5  jmp     short loc_180030C77
0x180030cf7  mov     r9d, eax; char *
0x180030cfa  lea     r8, aOnecoreuapWind_21; "onecoreuap\\windows\\advcore\\winrt\\ui"...
0x180030d01  mov     edx, 2C4h; void *
0x180030d06  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180030d0b  jmp     short loc_180030CDD
0x180030d0d  cmp     eax, 6
0x180030d10  jnz     short loc_180030D23
0x180030d12  call    cs:__imp_RtlIsMultiSessionSku
0x180030d18  test    al, al
0x180030d1a  jnz     loc_180030C47
0x180030d20  mov     eax, [rbp+pvParam]
0x180030d23  cmp     eax, 9
0x180030d26  jz      loc_180030C47
0x180030d2c  jmp     short loc_180030CC1
0x180030d2e  mov     [rbp+pvParam], 0
0x180030d35  mov     [rbp+arg_10], 4
0x180030d3c  lea     rax, [rbp+arg_10]
0x180030d40  mov     [rsp+40h+pcbData], rax; pcbData
0x180030d45  lea     rax, [rbp+pvParam]
0x180030d49  mov     [rsp+40h+pvData], rax; pvData
0x180030d4e  mov     [rsp+40h+pdwType], 0; unsigned int
0x180030d57  mov     r9d, 10h; dwFlags
0x180030d5d  lea     r8, aEnableanimatio; "EnableAnimations"
0x180030d64  xor     edx, edx; lpSubKey
0x180030d66  mov     rcx, rbx; hkey
0x180030d69  call    cs:__imp_RegGetValueW
0x180030d6f  test    eax, eax
0x180030d71  jnz     short loc_180030D7F
0x180030d73  cmp     [rbp+pvParam], eax
0x180030d76  setnz   dil
0x180030d7a  jmp     loc_180030CE6
0x180030d7f  cmp     eax, 2
0x180030d82  jz      loc_180030CE6
0x180030d88  mov     rcx, [rbp+18h]; this
0x180030d8c  mov     r9d, eax; char *
0x180030d8f  lea     r8, aOnecoreuapWind_21; "onecoreuap\\windows\\advcore\\winrt\\ui"...
0x180030d96  mov     edx, 2D9h; void *
0x180030d9b  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180030da0  mov     ebx, eax
0x180030da2  lea     rcx, [rbp+hKey]
0x180030da6  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180030dab  nop
0x180030dac  jmp     loc_180030CA6
```
