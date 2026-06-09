# ProofOfPossessionTokenProvider::GetLoginUrl(ushort * *)

- ea: `0x1800028a4`
- end: `0x180002b83`
- name: `?GetLoginUrl@ProofOfPossessionTokenProvider@@YAJPEAPEAG@Z`
- size: `735`
- prototype: `__int64 __fastcall(unsigned __int16 **this, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180002fcc`
- `0x180003be0`

## callees

- `0x1800028a4`
- `0x18000521c`
- `0x180078a5c`
- `0x1800912b4`
- `0x1800a11c0`
- `0x1800a2600`
- `0x1801272d4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000298f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000298f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000292d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000292d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000295e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000295e`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x180002a0e`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x180002ab5`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x180002a0e`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x180002ab5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800028ea`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180002a69`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800028ea`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180002a69`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800029b0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180002b05`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800029b0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180002b05`

## string_xrefs

- `0x1800029cf`: `onecoreuap\inetcore\lib\proofofpossessiontokenprovider\proofofpossessiontokenprovider.cxx`
- `0x180002a3a`: `onecoreuap\inetcore\lib\proofofpossessiontokenprovider\proofofpossessiontokenprovider.cxx`
- `0x180002a85`: `onecoreuap\inetcore\lib\proofofpossessiontokenprovider\proofofpossessiontokenprovider.cxx`
- `0x180002aee`: `onecoreuap\inetcore\lib\proofofpossessiontokenprovider\proofofpossessiontokenprovider.cxx`
- `0x180002b42`: `onecoreuap\inetcore\lib\proofofpossessiontokenprovider\proofofpossessiontokenprovider.cxx`

## pseudocode

```c
__int64 __fastcall ProofOfPossessionTokenProvider::GetLoginUrl(unsigned __int16 **this, unsigned __int16 **a2)
{
  signed int v3; // edi
  unsigned __int16 *v4; // rax
  unsigned __int16 *v5; // rsi
  BYTE *v6; // rbx
  LSTATUS v7; // eax
  LSTATUS v8; // eax
  unsigned int PersistedRegistryLocationW; // ebx
  __int64 v11; // rdx
  HKEY v12; // rax
  const char *v13; // r9
  HKEY v14; // rbx
  int v15; // eax
  int v16; // esi
  bool v17; // sf
  bool v18; // sf
  int TokenProviderLoginUrls; // eax
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+18h]
  DWORD cbData; // [rsp+58h] [rbp+28h] BYREF
  HKEY hKey; // [rsp+60h] [rbp+30h] BYREF

  if ( IsInternetExplorerApp() )
  {
    v3 = -2147024809;
    if ( this )
    {
      *this = 0;
      cbData = 4168;
      v4 = (unsigned __int16 *)CoTaskMemAlloc(0x104Cu);
      v5 = v4;
      if ( v4 )
      {
        v6 = (BYTE *)v4;
        hKey = 0;
        v7 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\IdentityCRL", 0, 0x101u, &hKey);
        v3 = v7;
        if ( v7 )
        {
          if ( v7 > 0 )
            v3 = (unsigned __int16)v7 | 0x80070000;
        }
        else
        {
          v8 = RegQueryValueExW(hKey, L"LoginUrl", 0, 0, v6, &cbData);
          v3 = v8;
          if ( v8 )
          {
            if ( v8 > 0 )
              v3 = (unsigned __int16)v8 | 0x80070000;
          }
          else
          {
            *(_DWORD *)&v6[2 * ((unsigned __int64)cbData >> 1)] = 0;
            v6 = 0;
            *this = v5;
          }
          RegCloseKey(hKey);
        }
        if ( v6 )
          CoTaskMemFree(v6);
        if ( v3 < 0 )
          goto LABEL_17;
        return 0;
      }
      v3 = -2147024882;
    }
LABEL_17:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xFB,
      (int)"onecoreuap\\inetcore\\lib\\proofofpossessiontokenprovider\\proofofpossessiontokenprovider.cxx",
      (const char *)(unsigned int)v3);
    return (unsigned int)v3;
  }
  cbData = 0;
  PersistedRegistryLocationW = GetPersistedRegistryLocationW(L"IdentityCRL", L"Software\\Microsoft\\IdentityCRL", 0, 0);
  if ( PersistedRegistryLocationW != 234 )
  {
    MicrosoftTelemetryAssertTriggeredNoArgs();
    if ( PersistedRegistryLocationW )
    {
      if ( (int)PersistedRegistryLocationW > 0 )
        PersistedRegistryLocationW = (unsigned __int16)PersistedRegistryLocationW | 0x80070000;
      v11 = 269;
    }
    else
    {
      PersistedRegistryLocationW = -2147418113;
      v11 = 268;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v11,
      (int)"onecoreuap\\inetcore\\lib\\proofofpossessiontokenprovider\\proofofpossessiontokenprovider.cxx",
      (const char *)PersistedRegistryLocationW);
    return PersistedRegistryLocationW;
  }
  v12 = (HKEY)CoTaskMemAlloc(cbData);
  hKey = v12;
  v14 = v12;
  if ( !v12 )
    wil::details::in1diag3::_FailFast_NullAlloc(
      retaddr,
      (void *)0x112,
      (int)"onecoreuap\\inetcore\\lib\\proofofpossessiontokenprovider\\proofofpossessiontokenprovider.cxx",
      v13);
  v15 = GetPersistedRegistryLocationW(L"IdentityCRL", L"Software\\Microsoft\\IdentityCRL", v12, cbData);
  v16 = (unsigned __int16)v15;
  v3 = v15;
  v17 = v15 < 0;
  if ( v15 > 0 )
    v17 = 1;
  if ( v17 )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  v18 = v3 < 0;
  if ( v3 > 0 )
  {
    v3 = v16 | 0x80070000;
    v18 = 1;
  }
  if ( v18 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x11E,
      (int)"onecoreuap\\inetcore\\lib\\proofofpossessiontokenprovider\\proofofpossessiontokenprovider.cxx",
      (const char *)(unsigned int)v3);
    CoTaskMemFree(v14);
    return (unsigned int)v3;
  }
  TokenProviderLoginUrls = GetTokenProviderLoginUrls(HKEY_LOCAL_MACHINE, (LPCWSTR)v14, L"LoginUrl", this, 0);
  PersistedRegistryLocationW = TokenProviderLoginUrls;
  if ( TokenProviderLoginUrls < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x120,
      (int)"onecoreuap\\inetcore\\lib\\proofofpossessiontokenprovider\\proofofpossessiontokenprovider.cxx",
      (const char *)(unsigned int)TokenProviderLoginUrls);
    wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>((void **)&hKey);
    return PersistedRegistryLocationW;
  }
  wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>((void **)&hKey);
  return 0;
}

```

## disassembly

```asm
0x1800028a4  mov     [rsp-18h+arg_0], rbx
0x1800028a9  mov     [rsp-18h+arg_18], rsi
0x1800028ae  push    rbp
0x1800028af  push    rdi
0x1800028b0  push    r14
0x1800028b2  mov     rbp, rsp
0x1800028b5  sub     rsp, 30h
0x1800028b9  mov     r14, rcx
0x1800028bc  call    ?IsInternetExplorerApp@@YAHXZ; IsInternetExplorerApp(void)
0x1800028c1  test    eax, eax
0x1800028c3  jz      loc_1800029EA
0x1800028c9  mov     edi, 80070057h
0x1800028ce  test    r14, r14
0x1800028d1  jz      loc_1800029CB
0x1800028d7  mov     ecx, 104Ch; cb
0x1800028dc  mov     qword ptr [r14], 0
0x1800028e3  mov     [rbp+cbData], 1048h
0x1800028ea  call    cs:__imp_CoTaskMemAlloc
0x1800028f1  nop     dword ptr [rax+rax+00h]
0x1800028f6  mov     rsi, rax
0x1800028f9  test    rax, rax
0x1800028fc  jz      loc_1800029C6
0x180002902  mov     rbx, rax
0x180002905  mov     [rbp+hKey], 0
0x18000290d  lea     rax, [rbp+hKey]
0x180002911  mov     r9d, 101h; samDesired
0x180002917  xor     r8d, r8d; ulOptions
0x18000291a  mov     [rsp+30h+phkResult], rax; phkResult
0x18000291f  lea     rdx, SubKey; "Software\\Microsoft\\IdentityCRL"
0x180002926  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000292d  call    cs:__imp_RegOpenKeyExW
0x180002934  nop     dword ptr [rax+rax+00h]
0x180002939  mov     edi, eax
0x18000293b  test    eax, eax
0x18000293d  jnz     short loc_18000299D
0x18000293f  mov     rcx, [rbp+hKey]; hKey
0x180002943  lea     rax, [rbp+cbData]
0x180002947  mov     [rsp+30h+lpcbData], rax; lpcbData
0x18000294c  lea     rdx, ValueName; "LoginUrl"
0x180002953  xor     r9d, r9d; lpType
0x180002956  mov     [rsp+30h+phkResult], rbx; lpData
0x18000295b  xor     r8d, r8d; lpReserved
0x18000295e  call    cs:__imp_RegQueryValueExW
0x180002965  nop     dword ptr [rax+rax+00h]
0x18000296a  mov     edi, eax
0x18000296c  test    eax, eax
0x18000296e  jnz     short loc_180002980
0x180002970  mov     ecx, [rbp+cbData]
0x180002973  shr     rcx, 1
0x180002976  mov     [rbx+rcx*2], eax
0x180002979  xor     ebx, ebx
0x18000297b  mov     [r14], rsi
0x18000297e  jmp     short loc_18000298B
0x180002980  jle     short loc_18000298B
0x180002982  movzx   edi, ax
0x180002985  or      edi, 80070000h
0x18000298b  mov     rcx, [rbp+hKey]; hKey
0x18000298f  call    cs:__imp_RegCloseKey
0x180002996  nop     dword ptr [rax+rax+00h]
0x18000299b  jmp     short loc_1800029A8
0x18000299d  jle     short loc_1800029A8
0x18000299f  movzx   edi, ax
0x1800029a2  or      edi, 80070000h
0x1800029a8  test    rbx, rbx
0x1800029ab  jz      short loc_1800029BC
0x1800029ad  mov     rcx, rbx; pv
0x1800029b0  call    cs:__imp_CoTaskMemFree
0x1800029b7  nop     dword ptr [rax+rax+00h]
0x1800029bc  test    edi, edi
0x1800029be  jns     loc_180002B6D
0x1800029c4  jmp     short loc_1800029CB
0x1800029c6  mov     edi, 8007000Eh
0x1800029cb  mov     rcx, [rbp+18h]; this
0x1800029cf  lea     r8, aOnecoreuapInet_36; "onecoreuap\\inetcore\\lib\\proofofposse"...
0x1800029d6  mov     r9d, edi; char *
0x1800029d9  mov     edx, 0FBh; void *
0x1800029de  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800029e3  mov     eax, edi
0x1800029e5  jmp     loc_180002B6F
0x1800029ea  lea     rax, [rbp+cbData]
0x1800029ee  mov     [rbp+cbData], 0
0x1800029f5  xor     r9d, r9d
0x1800029f8  mov     [rsp+30h+phkResult], rax; int
0x1800029fd  xor     r8d, r8d
0x180002a00  lea     rdx, SubKey; "Software\\Microsoft\\IdentityCRL"
0x180002a07  lea     rcx, aIdentitycrl; "IdentityCRL"
0x180002a0e  call    cs:__imp_GetPersistedRegistryLocationW
0x180002a15  nop     dword ptr [rax+rax+00h]
0x180002a1a  mov     ebx, eax
0x180002a1c  cmp     eax, 0EAh
0x180002a21  jz      short loc_180002A66
0x180002a23  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180002a28  test    ebx, ebx
0x180002a2a  jnz     short loc_180002A50
0x180002a2c  mov     ebx, 8000FFFFh
0x180002a31  mov     edx, 10Ch; void *
0x180002a36  mov     rcx, [rbp+18h]; this
0x180002a3a  lea     r8, aOnecoreuapInet_36; "onecoreuap\\inetcore\\lib\\proofofposse"...
0x180002a41  mov     r9d, ebx; char *
0x180002a44  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180002a49  mov     eax, ebx
0x180002a4b  jmp     loc_180002B6F
0x180002a50  jle     short loc_180002A5B
0x180002a52  movzx   ebx, bx
0x180002a55  or      ebx, 80070000h
0x180002a5b  test    ebx, ebx
0x180002a5d  jns     short loc_180002A49
0x180002a5f  mov     edx, 10Dh
0x180002a64  jmp     short loc_180002A36
0x180002a66  mov     ecx, [rbp+cbData]; cb
0x180002a69  call    cs:__imp_CoTaskMemAlloc
0x180002a70  nop     dword ptr [rax+rax+00h]
0x180002a75  mov     [rbp+hKey], rax
0x180002a79  mov     rbx, rax
0x180002a7c  test    rax, rax
0x180002a7f  jnz     short loc_180002A97
0x180002a81  mov     rcx, [rbp+18h]; this
0x180002a85  lea     r8, aOnecoreuapInet_36; "onecoreuap\\inetcore\\lib\\proofofposse"...
0x180002a8c  mov     edx, 112h; void *
0x180002a91  call    ?_FailFast_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_NullAlloc(void *,uint,char const *)
0x180002a97  mov     r9d, [rbp+cbData]
0x180002a9b  lea     rdx, SubKey; "Software\\Microsoft\\IdentityCRL"
0x180002aa2  mov     r8, rbx
0x180002aa5  mov     [rsp+30h+phkResult], 0; int
0x180002aae  lea     rcx, aIdentitycrl; "IdentityCRL"
0x180002ab5  call    cs:__imp_GetPersistedRegistryLocationW
0x180002abc  nop     dword ptr [rax+rax+00h]
0x180002ac1  movzx   esi, ax
0x180002ac4  mov     edi, eax
0x180002ac6  test    eax, eax
0x180002ac8  jle     short loc_180002AD3
0x180002aca  mov     eax, esi
0x180002acc  or      eax, 80070000h
0x180002ad1  test    eax, eax
0x180002ad3  jns     short loc_180002ADA
0x180002ad5  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180002ada  test    edi, edi
0x180002adc  jle     short loc_180002AE8
0x180002ade  mov     edi, esi
0x180002ae0  or      edi, 80070000h
0x180002ae6  test    edi, edi
0x180002ae8  jns     short loc_180002B16
0x180002aea  mov     rcx, [rbp+18h]; this
0x180002aee  lea     r8, aOnecoreuapInet_36; "onecoreuap\\inetcore\\lib\\proofofposse"...
0x180002af5  mov     r9d, edi; char *
0x180002af8  mov     edx, 11Eh; void *
0x180002afd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180002b02  mov     rcx, rbx; pv
0x180002b05  call    cs:__imp_CoTaskMemFree
0x180002b0c  nop     dword ptr [rax+rax+00h]
0x180002b11  jmp     loc_1800029E3
0x180002b16  mov     r9, r14; unsigned __int16 **
0x180002b19  mov     [rsp+30h+phkResult], 0; int
0x180002b22  lea     r8, ValueName; "LoginUrl"
0x180002b29  mov     rdx, rbx; lpSubKey
0x180002b2c  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180002b33  call    ?GetTokenProviderLoginUrls@@YAJPEAUHKEY__@@PEBG1PEAPEAGPEA_K@Z; GetTokenProviderLoginUrls(HKEY__ *,ushort const *,ushort const *,ushort * *,unsigned __int64 *)
0x180002b38  mov     ebx, eax
0x180002b3a  test    eax, eax
0x180002b3c  jns     short loc_180002B64
0x180002b3e  mov     rcx, [rbp+18h]; this
0x180002b42  lea     r8, aOnecoreuapInet_36; "onecoreuap\\inetcore\\lib\\proofofposse"...
0x180002b49  mov     r9d, eax; char *
0x180002b4c  mov     edx, 120h; void *
0x180002b51  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180002b56  lea     rcx, [rbp+hKey]
0x180002b5a  call    ??1?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>(void)
0x180002b5f  jmp     loc_180002A49
0x180002b64  lea     rcx, [rbp+hKey]
0x180002b68  call    ??1?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>(void)
0x180002b6d  xor     eax, eax
0x180002b6f  mov     rbx, [rsp+30h+arg_0]
0x180002b74  mov     rsi, [rsp+30h+arg_18]
0x180002b79  add     rsp, 30h
0x180002b7d  pop     r14
0x180002b7f  pop     rdi
0x180002b80  pop     rbp
0x180002b81  retn
```
