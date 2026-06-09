# AccentColors::UpdateHistory(ulong,bool)

- ea: `0x18011d9b8`
- end: `0x18011de90`
- name: `?UpdateHistory@AccentColors@@SAJK_N@Z`
- size: `1240`
- prototype: `__int64 __fastcall(unsigned int, bool)`
- caller_count: `2`
- callee_count: `10`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18011d7a8`
- `0x18011e114`

## callees

- `0x18000fea0`
- `0x180010940`
- `0x1800e34bc`
- `0x18011d9b8`
- `0x18011de98`
- `0x18011df4c`
- `0x18011e33c`
- `0x18011e374`
- `0x18015cb00`
- `0x180469e00`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18011dab7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18011dab7`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18011dbc0`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18011dc74`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18011dbc0`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18011dc74`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18011dbfb`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18011dd39`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18011ddfa`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18011de47`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18011dbfb`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18011dd39`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18011ddfa`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18011de47`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18011da5f`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18011db27`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18011da5f`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18011db27`

## pseudocode

```c
__int64 __fastcall AccentColors::UpdateHistory(unsigned int a1)
{
  BOOL v2; // r12d
  HKEY *phkResult; // rax
  HKEY v4; // rcx
  LSTATUS Key; // eax
  signed int v6; // ebx
  __int64 v7; // rdx
  bool IsKnownColor; // si
  HKEY *v9; // rax
  HKEY v10; // rcx
  LSTATUS v11; // eax
  bool v12; // dl
  bool v13; // sf
  HKEY *v14; // rax
  HKEY v15; // rcx
  LSTATUS v16; // eax
  signed int v17; // edi
  int v18; // r15d
  LSTATUS v19; // eax
  bool v20; // sf
  int v21; // ebx
  LSTATUS v22; // eax
  __int64 v23; // rax
  int v24; // esi
  int v25; // ebx
  int v26; // eax
  int i; // edx
  int v28; // ebx
  int v29; // edi
  signed int v30; // edx
  int v31; // r8d
  int v32; // r9d
  LSTATUS v33; // eax
  int dwOptions; // [rsp+20h] [rbp-E0h]
  DWORD dwOptionsa[2]; // [rsp+20h] [rbp-E0h]
  BYTE Data[4]; // [rsp+50h] [rbp-B0h] BYREF
  BYTE v38[4]; // [rsp+54h] [rbp-ACh] BYREF
  DWORD cbData; // [rsp+58h] [rbp-A8h] BYREF
  HKEY v40; // [rsp+60h] [rbp-A0h] BYREF
  HKEY hKey; // [rsp+68h] [rbp-98h] BYREF
  BYTE v42[8]; // [rsp+70h] [rbp-90h] BYREF
  HKEY v43[2]; // [rsp+78h] [rbp-88h] BYREF
  _DWORD v44[6]; // [rsp+88h] [rbp-78h] BYREF
  WCHAR ValueName[264]; // [rsp+A0h] [rbp-60h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2F8h] [rbp+1F8h]

  hKey = 0;
  v40 = 0;
  v2 = IsAutoColorizationEnabled();
  CCurrentColorUser::CCurrentColorUser(v43, 0x2001Fu);
  phkResult = (HKEY *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(&hKey);
  v4 = v43[0];
  if ( CCurrentColorUser::_overrideCurrentUser )
    v4 = CCurrentColorUser::_overrideCurrentUser;
  Key = RegCreateKeyExW(
          v4,
          L"Software\\Microsoft\\Windows\\CurrentVersion\\Themes\\History",
          0,
          0,
          0,
          0x2001Fu,
          0,
          phkResult,
          0);
  v6 = Key;
  if ( Key > 0 )
    v6 = (unsigned __int16)Key | 0x80070000;
  if ( v6 < 0 )
  {
    v7 = 365;
LABEL_18:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"onecoreuap\\shell\\lib\\occolorlib\\accentcolors.cpp",
      (const char *)(unsigned int)v6,
      dwOptions);
    goto LABEL_66;
  }
  IsKnownColor = 0;
  v9 = (HKEY *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(&v40);
  v10 = v43[0];
  if ( CCurrentColorUser::_overrideCurrentUser )
    v10 = CCurrentColorUser::_overrideCurrentUser;
  v11 = RegOpenKeyExW(v10, L"Software\\Microsoft\\Windows\\CurrentVersion\\Themes\\History\\Colors", 0, 0x2001Fu, v9);
  v13 = v11 < 0;
  if ( v11 > 0 )
    v13 = 1;
  if ( v13 )
  {
    IsKnownColor = AccentColors::_IsKnownColor(a1, v12);
    v14 = (HKEY *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(&v40);
    v15 = v43[0];
    if ( CCurrentColorUser::_overrideCurrentUser )
      v15 = CCurrentColorUser::_overrideCurrentUser;
    v16 = RegCreateKeyExW(
            v15,
            L"Software\\Microsoft\\Windows\\CurrentVersion\\Themes\\History\\Colors",
            0,
            0,
            0,
            0x2001Fu,
            0,
            v14,
            0);
    v6 = v16;
    if ( v16 > 0 )
      v6 = (unsigned __int16)v16 | 0x80070000;
    if ( v6 < 0 )
    {
      v7 = 371;
      goto LABEL_18;
    }
  }
  if ( !AccentColors::_IsKnownColor(a1, v12) || IsKnownColor )
  {
    v17 = 0;
    v18 = 0;
    *(_DWORD *)Data = 0;
    if ( !IsKnownColor && a1 != 195948557 )
    {
      v44[0] = a1;
      v18 = 1;
    }
    cbData = 4;
    v19 = RegQueryValueExW(hKey, L"AutoColor", 0, 0, Data, &cbData);
    v20 = v19 < 0;
    if ( v19 > 0 )
      v20 = 1;
    if ( v20 )
    {
      *(_DWORD *)Data = v2;
      RegSetValueExW(hKey, L"AutoColor", 0, 4u, Data, 4u);
    }
    v21 = 0;
    while ( v21 < 5 )
    {
      if ( *(_DWORD *)Data == 1 && !v21 )
        goto LABEL_39;
      dwOptionsa[0] = v21;
      v17 = StringCchPrintfW(ValueName, 0x104u, L"%s%u", L"ColorHistory", *(_QWORD *)dwOptionsa);
      if ( v17 < 0 )
        goto LABEL_39;
      *(_DWORD *)v38 = 0;
      cbData = 4;
      v22 = RegQueryValueExW(v40, ValueName, 0, 0, v38, &cbData);
      v17 = v22;
      if ( v22 > 0 )
        v17 = (unsigned __int16)v22 | 0x80070000;
      if ( v17 < 0 )
      {
LABEL_39:
        ++v21;
        if ( v17 < 0 )
          break;
      }
      else
      {
        if ( ((a1 ^ *(_DWORD *)v38) & 0xFFFFFF) != 0 )
        {
          v23 = v18++;
          v44[v23] = *(_DWORD *)v38;
        }
        ++v21;
      }
    }
    v24 = 0;
    v25 = 0;
    do
    {
LABEL_41:
      if ( v25 >= v18 )
        break;
      dwOptionsa[0] = v24;
      v26 = StringCchPrintfW(ValueName, 0x104u, L"%s%u", L"ColorHistory", *(_QWORD *)dwOptionsa);
      if ( v26 >= 0 )
      {
        for ( i = 0; i < v25; ++i )
        {
          if ( ((v44[v25] ^ v44[i]) & 0xFFFFFF) == 0 )
          {
            ++v25;
            goto LABEL_41;
          }
        }
        v26 = RegSetValueExW(v40, ValueName, 0, 4u, (const BYTE *)&v44[v25], 4u);
        if ( v26 > 0 )
          v26 = (unsigned __int16)v26 | 0x80070000;
        ++v24;
      }
      ++v25;
    }
    while ( v26 >= 0 );
    v28 = 0;
    v29 = v24;
    do
    {
      if ( v29 >= 5 || v28 >= 5 )
        break;
      dwOptionsa[0] = v29;
      v30 = StringCchPrintfW(ValueName, 0x104u, L"%s%u", L"ColorHistory", *(_QWORD *)dwOptionsa);
      if ( v30 >= 0 )
      {
LABEL_56:
        if ( (unsigned int)v28 < 4 )
        {
          v31 = 0;
          v32 = *((_DWORD *)qword_180555F00 + v28);
          *(_DWORD *)v38 = v32;
          while ( v31 < v24 )
          {
            if ( ((v44[v31] ^ v32) & 0xFFFFFF) == 0 )
            {
              ++v28;
              goto LABEL_56;
            }
            ++v31;
          }
          v33 = RegSetValueExW(v40, ValueName, 0, 4u, v38, 4u);
          v30 = v33;
          if ( v33 > 0 )
            v30 = (unsigned __int16)v33 | 0x80070000;
        }
      }
      ++v29;
      ++v28;
    }
    while ( v30 >= 0 );
  }
  *(_DWORD *)v42 = v2;
  RegSetValueExW(hKey, L"AutoColor", 0, 4u, v42, 4u);
  v6 = 0;
LABEL_66:
  CCurrentUser::~CCurrentUser((CCurrentUser *)v43);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v40);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18011d9b8  push    rbp
0x18011d9ba  push    rbx
0x18011d9bb  push    rsi
0x18011d9bc  push    rdi
0x18011d9bd  push    r12
0x18011d9bf  push    r14
0x18011d9c1  push    r15
0x18011d9c3  lea     rbp, [rsp-1C0h]
0x18011d9cb  sub     rsp, 2C0h
0x18011d9d2  mov     rax, cs:__security_cookie
0x18011d9d9  xor     rax, rsp
0x18011d9dc  mov     [rbp+1F0h+var_40], rax
0x18011d9e3  mov     r14d, ecx
0x18011d9e6  mov     [rsp+2F0h+hKey], 0
0x18011d9ef  mov     [rsp+2F0h+var_290], 0
0x18011d9f8  call    ?IsAutoColorizationEnabled@@YA_NXZ; IsAutoColorizationEnabled(void)
0x18011d9fd  mov     edi, 2001Fh
0x18011da02  movzx   r12d, al
0x18011da06  mov     edx, edi; samDesired
0x18011da08  lea     rcx, [rsp+2F0h+var_278]; phkResult
0x18011da0d  call    ??0CCurrentColorUser@@QEAA@K@Z; CCurrentColorUser::CCurrentColorUser(ulong)
0x18011da12  lea     rcx, [rsp+2F0h+hKey]
0x18011da17  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(void)
0x18011da1c  mov     rdx, cs:?_overrideCurrentUser@CCurrentColorUser@@0PEAUHKEY__@@EA; HKEY__ * CCurrentColorUser::_overrideCurrentUser
0x18011da23  mov     rcx, [rsp+2F0h+var_278]
0x18011da28  test    rdx, rdx
0x18011da2b  mov     [rsp+2F0h+lpdwDisposition], 0; lpdwDisposition
0x18011da34  mov     [rsp+2F0h+phkResult], rax; phkResult
0x18011da39  cmovnz  rcx, rdx; hKey
0x18011da3d  mov     [rsp+2F0h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18011da46  lea     rdx, aSoftwareMicros_44; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18011da4d  xor     r9d, r9d; lpClass
0x18011da50  mov     [rsp+2F0h+samDesired], edi; samDesired
0x18011da54  xor     r8d, r8d; Reserved
0x18011da57  mov     [rsp+2F0h+dwOptions], 0; dwOptions
0x18011da5f  call    cs:__imp_RegCreateKeyExW
0x18011da65  mov     ebx, eax
0x18011da67  mov     r15d, 80070000h
0x18011da6d  test    eax, eax
0x18011da6f  jle     short loc_18011DA77
0x18011da71  movzx   ebx, ax
0x18011da74  or      ebx, r15d
0x18011da77  test    ebx, ebx
0x18011da79  jns     short loc_18011DA85
0x18011da7b  mov     edx, 16Dh
0x18011da80  jmp     loc_18011DB42
0x18011da85  lea     rcx, [rsp+2F0h+var_290]
0x18011da8a  xor     sil, sil
0x18011da8d  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(void)
0x18011da92  mov     rdx, cs:?_overrideCurrentUser@CCurrentColorUser@@0PEAUHKEY__@@EA; HKEY__ * CCurrentColorUser::_overrideCurrentUser
0x18011da99  mov     r9d, edi; samDesired
0x18011da9c  mov     rcx, [rsp+2F0h+var_278]
0x18011daa1  test    rdx, rdx
0x18011daa4  mov     qword ptr [rsp+2F0h+dwOptions], rax; phkResult
0x18011daa9  cmovnz  rcx, rdx; hKey
0x18011daad  xor     r8d, r8d; ulOptions
0x18011dab0  lea     rdx, aSoftwareMicros_10; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18011dab7  call    cs:__imp_RegOpenKeyExW
0x18011dabd  test    eax, eax
0x18011dabf  jle     short loc_18011DAC9
0x18011dac1  movzx   eax, ax
0x18011dac4  or      eax, r15d
0x18011dac7  test    eax, eax
0x18011dac9  jns     loc_18011DB5D
0x18011dacf  mov     ecx, r14d; unsigned int
0x18011dad2  call    ?_IsKnownColor@AccentColors@@CA_NK_N@Z; AccentColors::_IsKnownColor(ulong,bool)
0x18011dad7  lea     rcx, [rsp+2F0h+var_290]
0x18011dadc  mov     sil, al
0x18011dadf  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(void)
0x18011dae4  mov     r8, cs:?_overrideCurrentUser@CCurrentColorUser@@0PEAUHKEY__@@EA; HKEY__ * CCurrentColorUser::_overrideCurrentUser
0x18011daeb  lea     rdx, aSoftwareMicros_10; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18011daf2  mov     rcx, [rsp+2F0h+var_278]
0x18011daf7  test    r8, r8
0x18011dafa  mov     [rsp+2F0h+lpdwDisposition], 0; lpdwDisposition
0x18011db03  mov     [rsp+2F0h+phkResult], rax; phkResult
0x18011db08  cmovnz  rcx, r8; hKey
0x18011db0c  mov     [rsp+2F0h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18011db15  xor     r9d, r9d; lpClass
0x18011db18  xor     r8d, r8d; Reserved
0x18011db1b  mov     [rsp+2F0h+samDesired], edi; samDesired
0x18011db1f  mov     [rsp+2F0h+dwOptions], 0; int
0x18011db27  call    cs:__imp_RegCreateKeyExW
0x18011db2d  mov     ebx, eax
0x18011db2f  test    eax, eax
0x18011db31  jle     short loc_18011DB39
0x18011db33  movzx   ebx, ax
0x18011db36  or      ebx, r15d
0x18011db39  test    ebx, ebx
0x18011db3b  jns     short loc_18011DB5D
0x18011db3d  mov     edx, 173h; void *
0x18011db42  mov     rcx, [rbp+1F8h]; this
0x18011db49  lea     r8, aOnecoreuapShel; "onecoreuap\\shell\\lib\\occolorlib\\acc"...
0x18011db50  mov     r9d, ebx; char *
0x18011db53  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18011db58  jmp     loc_18011DE4F
0x18011db5d  mov     ecx, r14d; unsigned int
0x18011db60  call    ?_IsKnownColor@AccentColors@@CA_NK_N@Z; AccentColors::_IsKnownColor(ulong,bool)
0x18011db65  mov     ebx, 4
0x18011db6a  test    al, al
0x18011db6c  jz      short loc_18011DB77
0x18011db6e  test    sil, sil
0x18011db71  jz      loc_18011DE22
0x18011db77  xor     edi, edi
0x18011db79  xor     r15d, r15d
0x18011db7c  mov     dword ptr [rsp+2F0h+Data], edi
0x18011db80  test    sil, sil
0x18011db83  jnz     short loc_18011DB96
0x18011db85  cmp     r14d, 0BADF00Dh
0x18011db8c  jz      short loc_18011DB96
0x18011db8e  mov     [rbp+1F0h+var_268], r14d
0x18011db92  lea     r15d, [rdi+1]
0x18011db96  mov     rcx, [rsp+2F0h+hKey]; hKey
0x18011db9b  lea     rax, [rsp+2F0h+cbData]
0x18011dba0  mov     qword ptr [rsp+2F0h+samDesired], rax; lpcbData
0x18011dba5  lea     rdx, aAutocolor; "AutoColor"
0x18011dbac  lea     rax, [rsp+2F0h+Data]
0x18011dbb1  mov     [rsp+2F0h+cbData], ebx
0x18011dbb5  xor     r9d, r9d; lpType
0x18011dbb8  mov     qword ptr [rsp+2F0h+dwOptions], rax; lpData
0x18011dbbd  xor     r8d, r8d; lpReserved
0x18011dbc0  call    cs:__imp_RegQueryValueExW
0x18011dbc6  test    eax, eax
0x18011dbc8  jle     short loc_18011DBD4
0x18011dbca  movzx   eax, ax
0x18011dbcd  or      eax, 80070000h
0x18011dbd2  test    eax, eax
0x18011dbd4  jns     short loc_18011DC01
0x18011dbd6  mov     rcx, [rsp+2F0h+hKey]; hKey
0x18011dbdb  lea     rax, [rsp+2F0h+Data]
0x18011dbe0  mov     [rsp+2F0h+samDesired], ebx; cbData
0x18011dbe4  lea     rdx, aAutocolor; "AutoColor"
0x18011dbeb  mov     r9d, ebx; dwType
0x18011dbee  mov     qword ptr [rsp+2F0h+dwOptions], rax; lpData
0x18011dbf3  xor     r8d, r8d; Reserved
0x18011dbf6  mov     dword ptr [rsp+2F0h+Data], r12d
0x18011dbfb  call    cs:__imp_RegSetValueExW
0x18011dc01  xor     ebx, ebx
0x18011dc03  cmp     ebx, 5
0x18011dc06  jge     loc_18011DCBA
0x18011dc0c  cmp     dword ptr [rsp+2F0h+Data], 1
0x18011dc11  jnz     short loc_18011DC1B
0x18011dc13  test    ebx, ebx
0x18011dc15  jz      loc_18011DCB0
0x18011dc1b  lea     r9, aColorhistory; "ColorHistory"
0x18011dc22  mov     [rsp+2F0h+dwOptions], ebx
0x18011dc26  lea     r8, aSU; "%s%u"
0x18011dc2d  mov     edx, 104h; unsigned __int64
0x18011dc32  lea     rcx, [rbp+1F0h+ValueName]; unsigned __int16 *
0x18011dc36  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18011dc3b  mov     edi, eax
0x18011dc3d  test    eax, eax
0x18011dc3f  js      short loc_18011DCB0
0x18011dc41  mov     rcx, [rsp+2F0h+var_290]; hKey
0x18011dc46  lea     rax, [rsp+2F0h+cbData]
0x18011dc4b  mov     qword ptr [rsp+2F0h+samDesired], rax; lpcbData
0x18011dc50  lea     rdx, [rbp+1F0h+ValueName]; lpValueName
0x18011dc54  lea     rax, [rsp+2F0h+var_29C]
0x18011dc59  mov     dword ptr [rsp+2F0h+var_29C], 0
0x18011dc61  xor     r9d, r9d; lpType
0x18011dc64  mov     qword ptr [rsp+2F0h+dwOptions], rax; lpData
0x18011dc69  xor     r8d, r8d; lpReserved
0x18011dc6c  mov     [rsp+2F0h+cbData], 4
0x18011dc74  call    cs:__imp_RegQueryValueExW
0x18011dc7a  mov     edi, eax
0x18011dc7c  test    eax, eax
0x18011dc7e  jle     short loc_18011DC89
0x18011dc80  movzx   edi, ax
0x18011dc83  or      edi, 80070000h
0x18011dc89  test    edi, edi
0x18011dc8b  js      short loc_18011DCB0
0x18011dc8d  mov     ecx, dword ptr [rsp+2F0h+var_29C]
0x18011dc91  mov     eax, ecx
0x18011dc93  xor     eax, r14d
0x18011dc96  test    eax, 0FFFFFFh
0x18011dc9b  jnz     short loc_18011DCA4
0x18011dc9d  inc     ebx
0x18011dc9f  jmp     loc_18011DC03
0x18011dca4  movsxd  rax, r15d
0x18011dca7  inc     r15d
0x18011dcaa  mov     [rbp+rax*4+1F0h+var_268], ecx
0x18011dcae  jmp     short loc_18011DC9D
0x18011dcb0  inc     ebx
0x18011dcb2  test    edi, edi
0x18011dcb4  jns     loc_18011DC03
0x18011dcba  xor     esi, esi
0x18011dcbc  xor     ebx, ebx
0x18011dcbe  lea     r14d, [rsi+1]
0x18011dcc2  cmp     ebx, r15d
0x18011dcc5  jge     loc_18011DD59
0x18011dccb  lea     r9, aColorhistory; "ColorHistory"
0x18011dcd2  mov     [rsp+2F0h+dwOptions], esi
0x18011dcd6  lea     r8, aSU; "%s%u"
0x18011dcdd  mov     edx, 104h; unsigned __int64
0x18011dce2  lea     rcx, [rbp+1F0h+ValueName]; unsigned __int16 *
0x18011dce6  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18011dceb  test    eax, eax
0x18011dced  js      short loc_18011DD4E
0x18011dcef  movsxd  rax, ebx
0x18011dcf2  lea     r8, [rbp+1F0h+var_268]
0x18011dcf6  xor     edx, edx
0x18011dcf8  lea     r8, [r8+rax*4]
0x18011dcfc  cmp     edx, ebx
0x18011dcfe  jge     short loc_18011DD1C
0x18011dd00  movsxd  rax, edx
0x18011dd03  mov     ecx, [rbp+rax*4+1F0h+var_268]
0x18011dd07  xor     ecx, [r8]
0x18011dd0a  test    ecx, 0FFFFFFh
0x18011dd10  jz      short loc_18011DD17
0x18011dd12  add     edx, r14d
0x18011dd15  jmp     short loc_18011DCFC
0x18011dd17  add     ebx, r14d
0x18011dd1a  jmp     short loc_18011DCC2
0x18011dd1c  mov     rcx, [rsp+2F0h+var_290]; hKey
0x18011dd21  lea     rdx, [rbp+1F0h+ValueName]; lpValueName
0x18011dd25  mov     eax, 4
0x18011dd2a  mov     [rsp+2F0h+samDesired], eax; cbData
0x18011dd2e  mov     r9d, eax; dwType
0x18011dd31  mov     qword ptr [rsp+2F0h+dwOptions], r8; lpData
0x18011dd36  xor     r8d, r8d; Reserved
0x18011dd39  call    cs:__imp_RegSetValueExW
0x18011dd3f  test    eax, eax
0x18011dd41  jle     short loc_18011DD4B
0x18011dd43  movzx   eax, ax
0x18011dd46  or      eax, 80070000h
0x18011dd4b  add     esi, r14d
0x18011dd4e  add     ebx, r14d
0x18011dd51  test    eax, eax
0x18011dd53  jns     loc_18011DCC2
0x18011dd59  xor     ebx, ebx
0x18011dd5b  mov     edi, esi
0x18011dd5d  cmp     edi, 5
0x18011dd60  jge     loc_18011DE1D
0x18011dd66  cmp     ebx, 5
0x18011dd69  jge     loc_18011DE1D
0x18011dd6f  lea     r9, aColorhistory; "ColorHistory"
0x18011dd76  mov     [rsp+2F0h+dwOptions], edi
0x18011dd7a  lea     r8, aSU; "%s%u"
0x18011dd81  mov     edx, 104h; unsigned __int64
0x18011dd86  lea     rcx, [rbp+1F0h+ValueName]; unsigned __int16 *
0x18011dd8a  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18011dd8f  mov     edx, eax
0x18011dd91  test    eax, eax
0x18011dd93  js      short loc_18011DE0F
0x18011dd95  mov     r10d, 4
0x18011dd9b  cmp     ebx, 5
0x18011dd9e  jge     short loc_18011DE0F
0x18011dda0  cmp     ebx, r10d
0x18011dda3  jnb     short loc_18011DE0F
0x18011dda5  movsxd  rcx, ebx
0x18011dda8  lea     r9, qword_180555F00
0x18011ddaf  xor     r8d, r8d
0x18011ddb2  mov     r9d, [r9+rcx*4]
0x18011ddb6  mov     dword ptr [rsp+2F0h+var_29C], r9d
0x18011ddbb  cmp     r8d, esi
0x18011ddbe  jge     short loc_18011DDDC
0x18011ddc0  movsxd  rax, r8d
0x18011ddc3  mov     ecx, r9d
0x18011ddc6  xor     ecx, [rbp+rax*4+1F0h+var_268]
0x18011ddca  test    ecx, 0FFFFFFh
0x18011ddd0  jz      short loc_18011DDD7
0x18011ddd2  add     r8d, r14d
0x18011ddd5  jmp     short loc_18011DDBB
0x18011ddd7  add     ebx, r14d
0x18011ddda  jmp     short loc_18011DD9B
0x18011dddc  mov     rcx, [rsp+2F0h+var_290]; hKey
0x18011dde1  lea     rax, [rsp+2F0h+var_29C]
0x18011dde6  mov     [rsp+2F0h+samDesired], r10d; cbData
0x18011ddeb  lea     rdx, [rbp+1F0h+ValueName]; lpValueName
0x18011ddef  mov     r9d, r10d; dwType
0x18011ddf2  mov     qword ptr [rsp+2F0h+dwOptions], rax; lpData
0x18011ddf7  xor     r8d, r8d; Reserved
0x18011ddfa  call    cs:__imp_RegSetValueExW
0x18011de00  mov     edx, eax
0x18011de02  test    eax, eax
0x18011de04  jle     short loc_18011DE0F
0x18011de06  movzx   edx, ax
0x18011de09  or      edx, 80070000h
0x18011de0f  add     edi, r14d
0x18011de12  add     ebx, r14d
0x18011de15  test    edx, edx
0x18011de17  jns     loc_18011DD5D
0x18011de1d  mov     ebx, 4
0x18011de22  mov     rcx, [rsp+2F0h+hKey]; hKey
0x18011de27  lea     rax, [rsp+2F0h+var_280]
0x18011de2c  mov     [rsp+2F0h+samDesired], ebx; cbData
0x18011de30  lea     rdx, aAutocolor; "AutoColor"
0x18011de37  mov     r9d, ebx; dwType
0x18011de3a  mov     qword ptr [rsp+2F0h+dwOptions], rax; lpData
0x18011de3f  xor     r8d, r8d; Reserved
0x18011de42  mov     dword ptr [rsp+2F0h+var_280], r12d
0x18011de47  call    cs:__imp_RegSetValueExW
0x18011de4d  xor     ebx, ebx
0x18011de4f  lea     rcx, [rsp+2F0h+var_278]; this
0x18011de54  call    ??1CCurrentUser@@QEAA@XZ; CCurrentUser::~CCurrentUser(void)
0x18011de59  lea     rcx, [rsp+2F0h+var_290]
0x18011de5e  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18011de63  lea     rcx, [rsp+2F0h+hKey]
0x18011de68  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18011de6d  mov     eax, ebx
0x18011de6f  mov     rcx, [rbp+1F0h+var_40]
  ... truncated ...
```
