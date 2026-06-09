# WriteLegacyProxySettingsHelper(tagProxySettings *,HKEY__ *,ulong)

- ea: `0x1800aa5a8`
- end: `0x1800aaa74`
- name: `?WriteLegacyProxySettingsHelper@@YAJPEAUtagProxySettings@@PEAUHKEY__@@K@Z`
- size: `1228`
- prototype: `int(struct tagProxySettings *, HKEY, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18004b358`

## callees

- `0x18002acec`
- `0x18005a398`
- `0x1800a1d10`
- `0x1800a2660`
- `0x1800aa5a8`
- `0x1800d1c64`
- `0x1800db6b0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800aaa1b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800aaa1b`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800aa71c`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800aa71c`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800aa77b`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800aa7f7`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800aa8a9`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800aa95d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800aaa0b`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800aa77b`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800aa7f7`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800aa8a9`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800aa95d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800aaa0b`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800aa826`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800aa8d8`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800aa98c`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800aa9bf`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800aa826`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800aa8d8`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800aa98c`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800aa9bf`

## string_xrefs

- `0x1800aa937`: `AutoConfigURL`
- `0x1800aa985`: `AutoConfigURL`

## pseudocode

```c
__int64 __fastcall WriteLegacyProxySettingsHelper(struct tagProxySettings *a1, HKEY a2, int a3)
{
  int v6; // edx
  int v7; // ecx
  int v8; // r8d
  signed int PersistedRegistryLocation; // ebx
  LSTATUS v10; // eax
  LSTATUS v11; // eax
  __int64 v12; // rcx
  LSTATUS v13; // eax
  LSTATUS v14; // eax
  __int64 v15; // rcx
  LSTATUS v16; // eax
  LSTATUS v17; // eax
  __int64 v18; // rcx
  LSTATUS v19; // eax
  LSTATUS v20; // eax
  LSTATUS v21; // eax
  DWORD dwOptions[2]; // [rsp+20h] [rbp-E0h]
  HKEY hKey; // [rsp+50h] [rbp-B0h] BYREF
  DWORD v25; // [rsp+58h] [rbp-A8h] BYREF
  int v26; // [rsp+5Ch] [rbp-A4h]
  BYTE Data[16]; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR SubKey[60]; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v29[408]; // [rsp+E8h] [rbp-18h] BYREF

  wcscpy(SubKey, L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Internet Settings");
  v26 = 0;
  hKey = 0;
  *(_DWORD *)Data = 0;
  v25 = 0;
  memset_0(v29, 0, 0x190u);
  if ( (xmmword_180107A60 & 0x20) != 0 )
    WPP_SF_qDSSSqD(
      v7,
      v6,
      v8,
      (_DWORD)a1,
      *((_DWORD *)a1 + 1),
      *((_QWORD *)a1 + 3),
      *((_QWORD *)a1 + 4),
      *((_QWORD *)a1 + 5),
      (__int64)a2,
      a3);
  if ( a2 == HKEY_LOCAL_MACHINE )
  {
    PersistedRegistryLocation = WxGetPersistedRegistryLocation(
                                  L"InternetSettings",
                                  L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Internet Settings",
                                  0,
                                  SubKey);
    if ( PersistedRegistryLocation < 0 )
    {
      v26 = 2487;
      goto LABEL_63;
    }
  }
  v10 = RegCreateKeyExW(a2, SubKey, 0, 0, 0, a3 | 0x20006, 0, &hKey, 0);
  PersistedRegistryLocation = v10;
  if ( v10 > 0 )
    PersistedRegistryLocation = (unsigned __int16)v10 | 0x80070000;
  if ( PersistedRegistryLocation < 0 )
  {
    v26 = 2498;
    goto LABEL_63;
  }
  if ( (*((_BYTE *)a1 + 4) & 2) != 0 )
    *(_DWORD *)Data = 1;
  v11 = RegSetValueExW(hKey, L"ProxyEnable", 0, 4u, Data, 4u);
  PersistedRegistryLocation = v11;
  if ( v11 > 0 )
    PersistedRegistryLocation = (unsigned __int16)v11 | 0x80070000;
  if ( PersistedRegistryLocation < 0 )
  {
    v26 = 2514;
    goto LABEL_63;
  }
  v12 = *((_QWORD *)a1 + 3);
  if ( v12 )
  {
    PersistedRegistryLocation = WxStringCchLengthDWordW(v12, 0x7FFFFFFF, &v25);
    if ( PersistedRegistryLocation < 0 )
    {
      v26 = 2522;
      goto LABEL_63;
    }
    v25 = 2 * v25 + 2;
    v13 = RegSetValueExW(hKey, L"ProxyServer", 0, 1u, *((const BYTE **)a1 + 3), v25);
    PersistedRegistryLocation = v13;
    if ( v13 > 0 )
      PersistedRegistryLocation = (unsigned __int16)v13 | 0x80070000;
    if ( PersistedRegistryLocation < 0 )
    {
      v26 = 2530;
      goto LABEL_63;
    }
  }
  else
  {
    v14 = RegDeleteValueW(hKey, L"ProxyServer");
    if ( v14 != 2 )
    {
      PersistedRegistryLocation = v14 > 0 ? (unsigned __int16)v14 | 0x80070000 : v14;
      if ( PersistedRegistryLocation < 0 )
      {
        v26 = 2537;
        goto LABEL_63;
      }
    }
  }
  v15 = *((_QWORD *)a1 + 4);
  if ( v15 )
  {
    PersistedRegistryLocation = WxStringCchLengthDWordW(v15, 0x7FFFFFFF, &v25);
    if ( PersistedRegistryLocation < 0 )
    {
      v26 = 2548;
      goto LABEL_63;
    }
    v25 = 2 * v25 + 2;
    v16 = RegSetValueExW(hKey, L"ProxyOverride", 0, 1u, *((const BYTE **)a1 + 4), v25);
    PersistedRegistryLocation = v16;
    if ( v16 > 0 )
      PersistedRegistryLocation = (unsigned __int16)v16 | 0x80070000;
    if ( PersistedRegistryLocation < 0 )
    {
      v26 = 2556;
      goto LABEL_63;
    }
  }
  else
  {
    v17 = RegDeleteValueW(hKey, L"ProxyOverride");
    if ( v17 != 2 )
    {
      PersistedRegistryLocation = v17 > 0 ? (unsigned __int16)v17 | 0x80070000 : v17;
      if ( PersistedRegistryLocation < 0 )
      {
        v26 = 2563;
        goto LABEL_63;
      }
    }
  }
  if ( (*((_BYTE *)a1 + 4) & 4) != 0 && (v18 = *((_QWORD *)a1 + 5)) != 0 )
  {
    PersistedRegistryLocation = WxStringCchLengthDWordW(v18, 0x7FFFFFFF, &v25);
    if ( PersistedRegistryLocation < 0 )
    {
      v26 = 2574;
      goto LABEL_63;
    }
    v19 = RegSetValueExW(hKey, L"AutoConfigURL", 0, 1u, *((const BYTE **)a1 + 5), 2 * v25 + 2);
    PersistedRegistryLocation = v19;
    if ( v19 > 0 )
      PersistedRegistryLocation = (unsigned __int16)v19 | 0x80070000;
    if ( PersistedRegistryLocation < 0 )
    {
      v26 = 2582;
      goto LABEL_63;
    }
  }
  else
  {
    v20 = RegDeleteValueW(hKey, L"AutoConfigURL");
    if ( v20 != 2 )
    {
      PersistedRegistryLocation = v20 > 0 ? (unsigned __int16)v20 | 0x80070000 : v20;
      if ( PersistedRegistryLocation < 0 )
      {
        v26 = 2589;
        goto LABEL_63;
      }
    }
  }
  v21 = RegDeleteValueW(hKey, L"AutoDetect");
  if ( v21 == 2
    || (v21 > 0 ? (PersistedRegistryLocation = (unsigned __int16)v21 | 0x80070000) : (PersistedRegistryLocation = v21),
        PersistedRegistryLocation >= 0) )
  {
    *(_DWORD *)Data = 1;
    RegSetValueExW(hKey, L"MigrateProxy", 0, 4u, Data, 4u);
  }
  else
  {
    v26 = 2601;
  }
LABEL_63:
  if ( hKey )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  if ( (xmmword_180107A60 & 0x20) != 0 )
    WPP_SF_d(
      1029,
      62,
      WPP_e24404dfc44e30604b090ca3bc8bd519_Traceguids,
      (unsigned int)PersistedRegistryLocation,
      *(_QWORD *)dwOptions);
  return (unsigned int)PersistedRegistryLocation;
}

```

## disassembly

```asm
0x1800aa5a8  mov     [rsp-8+arg_18], rbx
0x1800aa5ad  push    rbp
0x1800aa5ae  push    rsi
0x1800aa5af  push    rdi
0x1800aa5b0  push    r14
0x1800aa5b2  push    r15
0x1800aa5b4  lea     rbp, [rsp-190h]
0x1800aa5bc  sub     rsp, 290h
0x1800aa5c3  mov     rax, cs:__security_cookie
0x1800aa5ca  xor     rax, rsp
0x1800aa5cd  mov     [rbp+1B0h+var_30], rax
0x1800aa5d4  movaps  xmm0, xmmword ptr cs:aSoftwareMicros_2; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x1800aa5db  mov     r14d, r8d
0x1800aa5de  movaps  xmm1, xmmword ptr cs:aSoftwareMicros_2+10h; "\\Microsoft\\Windows\\CurrentVersion\\I"...
0x1800aa5e5  mov     r15, rdx
0x1800aa5e8  movaps  xmmword ptr [rsp+2B0h+SubKey], xmm0
0x1800aa5ed  mov     rdi, rcx
0x1800aa5f0  movaps  xmm0, xmmword ptr cs:aSoftwareMicros_2+20h; "ft\\Windows\\CurrentVersion\\Internet S"...
0x1800aa5f7  lea     rcx, [rbp+1B0h+var_1C8]; void *
0x1800aa5fb  movaps  [rbp+1B0h+var_230], xmm1
0x1800aa5ff  xor     edx, edx; Val
0x1800aa601  movaps  xmm1, xmmword ptr cs:aSoftwareMicros_2+30h; "ws\\CurrentVersion\\Internet Settings"
0x1800aa608  mov     r8d, 190h; Size
0x1800aa60e  movaps  [rbp+1B0h+var_220], xmm0
0x1800aa612  movaps  xmm0, xmmword ptr cs:aSoftwareMicros_2+40h; "ntVersion\\Internet Settings"
0x1800aa619  movaps  [rbp+1B0h+var_210], xmm1
0x1800aa61d  movaps  xmm1, xmmword ptr cs:aSoftwareMicros_2+50h; "n\\Internet Settings"
0x1800aa624  movaps  [rbp+1B0h+var_200], xmm0
0x1800aa628  movaps  xmm0, xmmword ptr cs:aSoftwareMicros_2+60h; "et Settings"
0x1800aa62f  movaps  [rbp+1B0h+var_1F0], xmm1
0x1800aa633  movsd   xmm1, qword ptr cs:aSoftwareMicros_2+70h; "ngs"
0x1800aa63b  movaps  [rbp+1B0h+var_1E0], xmm0
0x1800aa63f  movsd   [rbp+1B0h+var_1D0], xmm1
0x1800aa644  mov     [rsp+2B0h+var_254], 0
0x1800aa64c  mov     [rsp+2B0h+hKey], 0
0x1800aa655  mov     dword ptr [rsp+2B0h+Data], 0
0x1800aa65d  mov     [rsp+2B0h+var_258], 0
0x1800aa665  call    memset_0
0x1800aa66a  test    byte ptr cs:xmmword_180107A60, 20h
0x1800aa671  jz      short loc_1800AA6A7
0x1800aa673  mov     rax, [rdi+28h]
0x1800aa677  mov     r9, rdi
0x1800aa67a  mov     [rsp+2B0h+var_268], r14d
0x1800aa67f  mov     [rsp+2B0h+lpdwDisposition], r15
0x1800aa684  mov     [rsp+2B0h+phkResult], rax
0x1800aa689  mov     rax, [rdi+20h]
0x1800aa68d  mov     [rsp+2B0h+lpSecurityAttributes], rax
0x1800aa692  mov     rax, [rdi+18h]
0x1800aa696  mov     qword ptr [rsp+2B0h+samDesired], rax
0x1800aa69b  mov     eax, [rdi+4]
0x1800aa69e  mov     [rsp+2B0h+dwOptions], eax
0x1800aa6a2  call    WPP_SF_qDSSSqD
0x1800aa6a7  cmp     r15, 0FFFFFFFF80000002h
0x1800aa6ae  jnz     short loc_1800AA6DE
0x1800aa6b0  lea     r9, [rsp+2B0h+SubKey]
0x1800aa6b5  xor     r8d, r8d
0x1800aa6b8  lea     rdx, aSoftwareMicros_2; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x1800aa6bf  lea     rcx, aInternetsettin; "InternetSettings"
0x1800aa6c6  call    WxGetPersistedRegistryLocation
0x1800aa6cb  mov     ebx, eax
0x1800aa6cd  test    eax, eax
0x1800aa6cf  jns     short loc_1800AA6DE
0x1800aa6d1  mov     [rsp+2B0h+var_254], 9B7h
0x1800aa6d9  jmp     loc_1800AAA11
0x1800aa6de  mov     [rsp+2B0h+lpdwDisposition], 0; lpdwDisposition
0x1800aa6e7  lea     rax, [rsp+2B0h+hKey]
0x1800aa6ec  mov     [rsp+2B0h+phkResult], rax; phkResult
0x1800aa6f1  lea     rdx, [rsp+2B0h+SubKey]; lpSubKey
0x1800aa6f6  mov     [rsp+2B0h+lpSecurityAttributes], 0; lpSecurityAttributes
0x1800aa6ff  or      r14d, 20006h
0x1800aa706  mov     [rsp+2B0h+samDesired], r14d; samDesired
0x1800aa70b  xor     r9d, r9d; lpClass
0x1800aa70e  xor     r8d, r8d; Reserved
0x1800aa711  mov     [rsp+2B0h+dwOptions], 0; dwOptions
0x1800aa719  mov     rcx, r15; hKey
0x1800aa71c  call    cs:__imp_RegCreateKeyExW
0x1800aa722  mov     ebx, eax
0x1800aa724  mov     r14d, 80070000h
0x1800aa72a  test    eax, eax
0x1800aa72c  jle     short loc_1800AA734
0x1800aa72e  movzx   ebx, ax
0x1800aa731  or      ebx, r14d
0x1800aa734  test    ebx, ebx
0x1800aa736  jns     short loc_1800AA745
0x1800aa738  mov     [rsp+2B0h+var_254], 9C2h
0x1800aa740  jmp     loc_1800AAA11
0x1800aa745  test    byte ptr [rdi+4], 2
0x1800aa749  mov     r15d, 1
0x1800aa74f  jz      short loc_1800AA756
0x1800aa751  mov     dword ptr [rsp+2B0h+Data], r15d
0x1800aa756  mov     rcx, [rsp+2B0h+hKey]; hKey
0x1800aa75b  lea     rax, [rsp+2B0h+Data]
0x1800aa760  mov     esi, 4
0x1800aa765  lea     rdx, aProxyenable; "ProxyEnable"
0x1800aa76c  mov     [rsp+2B0h+samDesired], esi; cbData
0x1800aa770  mov     r9d, esi; dwType
0x1800aa773  xor     r8d, r8d; Reserved
0x1800aa776  mov     qword ptr [rsp+2B0h+dwOptions], rax; lpData
0x1800aa77b  call    cs:__imp_RegSetValueExW
0x1800aa781  mov     ebx, eax
0x1800aa783  test    eax, eax
0x1800aa785  jle     short loc_1800AA78D
0x1800aa787  movzx   ebx, ax
0x1800aa78a  or      ebx, r14d
0x1800aa78d  test    ebx, ebx
0x1800aa78f  jns     short loc_1800AA79E
0x1800aa791  mov     [rsp+2B0h+var_254], 9D2h
0x1800aa799  jmp     loc_1800AAA11
0x1800aa79e  mov     rcx, [rdi+18h]
0x1800aa7a2  test    rcx, rcx
0x1800aa7a5  jz      short loc_1800AA81A
0x1800aa7a7  lea     r8, [rsp+2B0h+var_258]
0x1800aa7ac  mov     edx, 7FFFFFFFh
0x1800aa7b1  call    WxStringCchLengthDWordW
0x1800aa7b6  mov     ebx, eax
0x1800aa7b8  test    eax, eax
0x1800aa7ba  jns     short loc_1800AA7C9
0x1800aa7bc  mov     [rsp+2B0h+var_254], 9DAh
0x1800aa7c4  jmp     loc_1800AAA11
0x1800aa7c9  mov     eax, [rsp+2B0h+var_258]
0x1800aa7cd  lea     rdx, aProxyserver; "ProxyServer"
0x1800aa7d4  mov     rcx, [rsp+2B0h+hKey]; hKey
0x1800aa7d9  mov     r9d, r15d; dwType
0x1800aa7dc  xor     r8d, r8d; Reserved
0x1800aa7df  lea     eax, ds:2[rax*2]
0x1800aa7e6  mov     [rsp+2B0h+samDesired], eax; cbData
0x1800aa7ea  mov     [rsp+2B0h+var_258], eax
0x1800aa7ee  mov     rax, [rdi+18h]
0x1800aa7f2  mov     qword ptr [rsp+2B0h+dwOptions], rax; lpData
0x1800aa7f7  call    cs:__imp_RegSetValueExW
0x1800aa7fd  mov     ebx, eax
0x1800aa7ff  test    eax, eax
0x1800aa801  jle     short loc_1800AA809
0x1800aa803  movzx   ebx, ax
0x1800aa806  or      ebx, r14d
0x1800aa809  test    ebx, ebx
0x1800aa80b  jns     short loc_1800AA850
0x1800aa80d  mov     [rsp+2B0h+var_254], 9E2h
0x1800aa815  jmp     loc_1800AAA11
0x1800aa81a  mov     rcx, [rsp+2B0h+hKey]; hKey
0x1800aa81f  lea     rdx, aProxyserver; "ProxyServer"
0x1800aa826  call    cs:__imp_RegDeleteValueW
0x1800aa82c  cmp     eax, 2
0x1800aa82f  jz      short loc_1800AA850
0x1800aa831  test    eax, eax
0x1800aa833  jg      short loc_1800AA839
0x1800aa835  mov     ebx, eax
0x1800aa837  jmp     short loc_1800AA83F
0x1800aa839  movzx   ebx, ax
0x1800aa83c  or      ebx, r14d
0x1800aa83f  test    ebx, ebx
0x1800aa841  jns     short loc_1800AA850
0x1800aa843  mov     [rsp+2B0h+var_254], 9E9h
0x1800aa84b  jmp     loc_1800AAA11
0x1800aa850  mov     rcx, [rdi+20h]
0x1800aa854  test    rcx, rcx
0x1800aa857  jz      short loc_1800AA8CC
0x1800aa859  lea     r8, [rsp+2B0h+var_258]
0x1800aa85e  mov     edx, 7FFFFFFFh
0x1800aa863  call    WxStringCchLengthDWordW
0x1800aa868  mov     ebx, eax
0x1800aa86a  test    eax, eax
0x1800aa86c  jns     short loc_1800AA87B
0x1800aa86e  mov     [rsp+2B0h+var_254], 9F4h
0x1800aa876  jmp     loc_1800AAA11
0x1800aa87b  mov     eax, [rsp+2B0h+var_258]
0x1800aa87f  lea     rdx, aProxyoverride; "ProxyOverride"
0x1800aa886  mov     rcx, [rsp+2B0h+hKey]; hKey
0x1800aa88b  mov     r9d, r15d; dwType
0x1800aa88e  xor     r8d, r8d; Reserved
0x1800aa891  lea     eax, ds:2[rax*2]
0x1800aa898  mov     [rsp+2B0h+samDesired], eax; cbData
0x1800aa89c  mov     [rsp+2B0h+var_258], eax
0x1800aa8a0  mov     rax, [rdi+20h]
0x1800aa8a4  mov     qword ptr [rsp+2B0h+dwOptions], rax; lpData
0x1800aa8a9  call    cs:__imp_RegSetValueExW
0x1800aa8af  mov     ebx, eax
0x1800aa8b1  test    eax, eax
0x1800aa8b3  jle     short loc_1800AA8BB
0x1800aa8b5  movzx   ebx, ax
0x1800aa8b8  or      ebx, r14d
0x1800aa8bb  test    ebx, ebx
0x1800aa8bd  jns     short loc_1800AA902
0x1800aa8bf  mov     [rsp+2B0h+var_254], 9FCh
0x1800aa8c7  jmp     loc_1800AAA11
0x1800aa8cc  mov     rcx, [rsp+2B0h+hKey]; hKey
0x1800aa8d1  lea     rdx, aProxyoverride; "ProxyOverride"
0x1800aa8d8  call    cs:__imp_RegDeleteValueW
0x1800aa8de  cmp     eax, 2
0x1800aa8e1  jz      short loc_1800AA902
0x1800aa8e3  test    eax, eax
0x1800aa8e5  jg      short loc_1800AA8EB
0x1800aa8e7  mov     ebx, eax
0x1800aa8e9  jmp     short loc_1800AA8F1
0x1800aa8eb  movzx   ebx, ax
0x1800aa8ee  or      ebx, r14d
0x1800aa8f1  test    ebx, ebx
0x1800aa8f3  jns     short loc_1800AA902
0x1800aa8f5  mov     [rsp+2B0h+var_254], 0A03h
0x1800aa8fd  jmp     loc_1800AAA11
0x1800aa902  test    [rdi+4], sil
0x1800aa906  jz      short loc_1800AA980
0x1800aa908  mov     rcx, [rdi+28h]
0x1800aa90c  test    rcx, rcx
0x1800aa90f  jz      short loc_1800AA980
0x1800aa911  lea     r8, [rsp+2B0h+var_258]
0x1800aa916  mov     edx, 7FFFFFFFh
0x1800aa91b  call    WxStringCchLengthDWordW
0x1800aa920  mov     ebx, eax
0x1800aa922  test    eax, eax
0x1800aa924  jns     short loc_1800AA933
0x1800aa926  mov     [rsp+2B0h+var_254], 0A0Eh
0x1800aa92e  jmp     loc_1800AAA11
0x1800aa933  mov     eax, [rsp+2B0h+var_258]
0x1800aa937  lea     rdx, aAutoconfigurl; "AutoConfigURL"
0x1800aa93e  mov     rcx, [rsp+2B0h+hKey]; hKey
0x1800aa943  mov     r9d, r15d; dwType
0x1800aa946  xor     r8d, r8d; Reserved
0x1800aa949  lea     eax, ds:2[rax*2]
0x1800aa950  mov     [rsp+2B0h+samDesired], eax; cbData
0x1800aa954  mov     rax, [rdi+28h]
0x1800aa958  mov     qword ptr [rsp+2B0h+dwOptions], rax; lpData
0x1800aa95d  call    cs:__imp_RegSetValueExW
0x1800aa963  mov     ebx, eax
0x1800aa965  test    eax, eax
0x1800aa967  jle     short loc_1800AA96F
0x1800aa969  movzx   ebx, ax
0x1800aa96c  or      ebx, r14d
0x1800aa96f  test    ebx, ebx
0x1800aa971  jns     short loc_1800AA9B3
0x1800aa973  mov     [rsp+2B0h+var_254], 0A16h
0x1800aa97b  jmp     loc_1800AAA11
0x1800aa980  mov     rcx, [rsp+2B0h+hKey]; hKey
0x1800aa985  lea     rdx, aAutoconfigurl; "AutoConfigURL"
0x1800aa98c  call    cs:__imp_RegDeleteValueW
0x1800aa992  cmp     eax, 2
0x1800aa995  jz      short loc_1800AA9B3
0x1800aa997  test    eax, eax
0x1800aa999  jg      short loc_1800AA99F
0x1800aa99b  mov     ebx, eax
0x1800aa99d  jmp     short loc_1800AA9A5
0x1800aa99f  movzx   ebx, ax
0x1800aa9a2  or      ebx, r14d
0x1800aa9a5  test    ebx, ebx
0x1800aa9a7  jns     short loc_1800AA9B3
0x1800aa9a9  mov     [rsp+2B0h+var_254], 0A1Dh
0x1800aa9b1  jmp     short loc_1800AAA11
0x1800aa9b3  mov     rcx, [rsp+2B0h+hKey]; hKey
0x1800aa9b8  lea     rdx, aAutodetect; "AutoDetect"
0x1800aa9bf  call    cs:__imp_RegDeleteValueW
0x1800aa9c5  cmp     eax, 2
0x1800aa9c8  jz      short loc_1800AA9E6
0x1800aa9ca  test    eax, eax
0x1800aa9cc  jg      short loc_1800AA9D2
0x1800aa9ce  mov     ebx, eax
0x1800aa9d0  jmp     short loc_1800AA9D8
0x1800aa9d2  movzx   ebx, ax
0x1800aa9d5  or      ebx, r14d
0x1800aa9d8  test    ebx, ebx
0x1800aa9da  jns     short loc_1800AA9E6
0x1800aa9dc  mov     [rsp+2B0h+var_254], 0A29h
0x1800aa9e4  jmp     short loc_1800AAA11
0x1800aa9e6  mov     rcx, [rsp+2B0h+hKey]; hKey
0x1800aa9eb  lea     rax, [rsp+2B0h+Data]
0x1800aa9f0  mov     [rsp+2B0h+samDesired], esi; cbData
0x1800aa9f4  lea     rdx, aMigrateproxy; "MigrateProxy"
0x1800aa9fb  mov     r9d, esi; dwType
0x1800aa9fe  mov     qword ptr [rsp+2B0h+dwOptions], rax; lpData
0x1800aaa03  xor     r8d, r8d; Reserved
0x1800aaa06  mov     dword ptr [rsp+2B0h+Data], r15d
0x1800aaa0b  call    cs:__imp_RegSetValueExW
0x1800aaa11  mov     rcx, [rsp+2B0h+hKey]; hKey
0x1800aaa16  test    rcx, rcx
0x1800aaa19  jz      short loc_1800AAA2A
0x1800aaa1b  call    cs:__imp_RegCloseKey
0x1800aaa21  mov     [rsp+2B0h+hKey], 0
0x1800aaa2a  test    byte ptr cs:xmmword_180107A60, 20h
0x1800aaa31  jz      short loc_1800AAA4C
0x1800aaa33  mov     edx, 3Eh ; '>'
0x1800aaa38  lea     r8, WPP_e24404dfc44e30604b090ca3bc8bd519_Traceguids
0x1800aaa3f  mov     ecx, 405h
0x1800aaa44  mov     r9d, ebx
0x1800aaa47  call    WPP_SF_d
0x1800aaa4c  mov     eax, ebx
0x1800aaa4e  mov     rcx, [rbp+1B0h+var_30]
0x1800aaa55  xor     rcx, rsp; StackCookie
0x1800aaa58  call    __security_check_cookie
0x1800aaa5d  mov     rbx, [rsp+2B0h+arg_18]
0x1800aaa65  add     rsp, 290h
0x1800aaa6c  pop     r15
0x1800aaa6e  pop     r14
0x1800aaa70  pop     rdi
0x1800aaa71  pop     rsi
0x1800aaa72  pop     rbp
0x1800aaa73  retn
```
