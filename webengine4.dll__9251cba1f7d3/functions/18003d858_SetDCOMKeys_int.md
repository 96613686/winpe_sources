# SetDCOMKeys(int)

- ea: `0x18003d858`
- end: `0x18003dd06`
- name: `?SetDCOMKeys@@YAJH@Z`
- size: `1198`
- prototype: `__int64 __fastcall(int)`
- caller_count: `3`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18003c1e8`
- `0x18003dd10`
- `0x18003ef38`

## callees

- `0x180038f7c`
- `0x18003d858`
- `0x18004d030`
- `0x18004d754`

## import_xrefs

- `KERNEL32!lstrlenW` at `0x18003da8b`
- `KERNEL32!lstrlenW` at `0x18003dac7`
- `KERNEL32!lstrlenW` at `0x18003dc11`
- `KERNEL32!lstrlenW` at `0x18003da8b`
- `KERNEL32!lstrlenW` at `0x18003dac7`
- `KERNEL32!lstrlenW` at `0x18003dc11`
- `ADVAPI32!RegCloseKey` at `0x18003dc62`
- `ADVAPI32!RegCloseKey` at `0x18003dc72`
- `ADVAPI32!RegCloseKey` at `0x18003dcb9`
- `ADVAPI32!RegCloseKey` at `0x18003dcc9`
- `ADVAPI32!RegCloseKey` at `0x18003dc62`
- `ADVAPI32!RegCloseKey` at `0x18003dc72`
- `ADVAPI32!RegCloseKey` at `0x18003dcb9`
- `ADVAPI32!RegCloseKey` at `0x18003dcc9`
- `ADVAPI32!RegCreateKeyExW` at `0x18003d998`
- `ADVAPI32!RegCreateKeyExW` at `0x18003da01`
- `ADVAPI32!RegCreateKeyExW` at `0x18003d998`
- `ADVAPI32!RegCreateKeyExW` at `0x18003da01`
- `ADVAPI32!RegOpenKeyExW` at `0x18003d8d4`
- `ADVAPI32!RegOpenKeyExW` at `0x18003d902`
- `ADVAPI32!RegOpenKeyExW` at `0x18003d963`
- `ADVAPI32!RegOpenKeyExW` at `0x18003d9c8`
- `ADVAPI32!RegOpenKeyExW` at `0x18003d8d4`
- `ADVAPI32!RegOpenKeyExW` at `0x18003d902`
- `ADVAPI32!RegOpenKeyExW` at `0x18003d963`
- `ADVAPI32!RegOpenKeyExW` at `0x18003d9c8`
- `ADVAPI32!RegSetValueExW` at `0x18003dab5`
- `ADVAPI32!RegSetValueExW` at `0x18003daf1`
- `ADVAPI32!RegSetValueExW` at `0x18003db2a`
- `ADVAPI32!RegSetValueExW` at `0x18003db62`
- `ADVAPI32!RegSetValueExW` at `0x18003dbae`
- `ADVAPI32!RegSetValueExW` at `0x18003dc40`
- `ADVAPI32!RegSetValueExW` at `0x18003dab5`
- `ADVAPI32!RegSetValueExW` at `0x18003daf1`
- `ADVAPI32!RegSetValueExW` at `0x18003db2a`
- `ADVAPI32!RegSetValueExW` at `0x18003db62`
- `ADVAPI32!RegSetValueExW` at `0x18003dbae`
- `ADVAPI32!RegSetValueExW` at `0x18003dc40`
- `ADVAPI32!RegDeleteKeyW` at `0x18003d927`
- `ADVAPI32!RegDeleteKeyW` at `0x18003d939`
- `ADVAPI32!RegDeleteKeyW` at `0x18003dc92`
- `ADVAPI32!RegDeleteKeyW` at `0x18003dca9`
- `ADVAPI32!RegDeleteKeyW` at `0x18003d927`
- `ADVAPI32!RegDeleteKeyW` at `0x18003d939`
- `ADVAPI32!RegDeleteKeyW` at `0x18003dc92`
- `ADVAPI32!RegDeleteKeyW` at `0x18003dca9`

## string_xrefs

- `0x18003d8f8`: `CLSID`
- `0x18003db10`: `DllSurrogate`
- `0x18003da28`: `System.Web.Configuration.RemoteWebConfigurationHostServerV4_64`

## pseudocode

```c
__int64 __fastcall SetDCOMKeys(int a1)
{
  unsigned int v2; // ebx
  BYTE *v3; // r14
  LSTATUS v4; // eax
  LSTATUS v5; // eax
  __int64 v6; // rdi
  __int64 v7; // rdx
  WCHAR *v8; // rcx
  WCHAR v9; // ax
  WCHAR *v10; // rax
  int v11; // eax
  int v12; // eax
  int PermissionsBlobForDCOMConfig; // eax
  WCHAR *v14; // rcx
  WCHAR v15; // ax
  WCHAR *v16; // rax
  int v17; // eax
  HKEY v19; // [rsp+58h] [rbp-B0h] BYREF
  BYTE Data[8]; // [rsp+60h] [rbp-A8h] BYREF
  HKEY phkResult; // [rsp+68h] [rbp-A0h] BYREF
  HKEY hKey; // [rsp+70h] [rbp-98h] BYREF
  HKEY v23; // [rsp+78h] [rbp-90h] BYREF
  BYTE *lpData; // [rsp+80h] [rbp-88h] BYREF
  WCHAR String[104]; // [rsp+88h] [rbp-80h] BYREF

  phkResult = 0;
  hKey = 0;
  v23 = 0;
  v19 = 0;
  lpData = 0;
  v2 = 0;
  v3 = 0;
  v4 = RegOpenKeyExW(HKEY_CLASSES_ROOT, L"AppID", 0, 0x2001Fu, &hKey);
  if ( v4 )
  {
    hKey = 0;
    goto LABEL_36;
  }
  v4 = RegOpenKeyExW(HKEY_CLASSES_ROOT, L"CLSID", 0, 0x2001Fu, &phkResult);
  if ( v4 )
  {
    phkResult = 0;
    goto LABEL_36;
  }
  if ( !a1 )
  {
    RegDeleteKeyW(hKey, L"{22A769D8-A44E-46FB-B264-0A411E42AEE0}");
    RegDeleteKeyW(phkResult, L"{DFD0D215-72C0-450d-92B5-10971FC24625}");
LABEL_38:
    if ( v23 )
      RegCloseKey(v23);
    goto LABEL_40;
  }
  if ( RegOpenKeyExW(hKey, L"{22A769D8-A44E-46FB-B264-0A411E42AEE0}", 0, 0x20006u, &v19) )
  {
    v4 = RegCreateKeyExW(hKey, L"{22A769D8-A44E-46FB-B264-0A411E42AEE0}", 0, 0, 0, 0x20006u, 0, &v19, 0);
    if ( v4 )
    {
      v19 = 0;
LABEL_36:
      v2 = (unsigned __int16)v4 | 0x80070000;
      if ( v4 <= 0 )
        v2 = v4;
      goto LABEL_38;
    }
  }
  if ( !RegOpenKeyExW(phkResult, L"{DFD0D215-72C0-450d-92B5-10971FC24625}", 0, 0x20006u, &v23)
    || (v5 = RegCreateKeyExW(phkResult, L"{DFD0D215-72C0-450d-92B5-10971FC24625}", 0, 0, 0, 0x20006u, 0, &v23, 0)) == 0 )
  {
    v6 = 100;
    v7 = 100;
    v8 = String;
    do
    {
      if ( v7 == -2147483546 )
        break;
      v9 = *(WCHAR *)((char *)v8
                    + (char *)L"System.Web.Configuration.RemoteWebConfigurationHostServerV4_64"
                    - (char *)String);
      if ( !v9 )
        break;
      *v8++ = v9;
      --v7;
    }
    while ( v7 );
    v10 = v8 - 1;
    if ( v7 )
      v10 = v8;
    *v10 = 0;
    v2 = v7 == 0 ? 0x8007007A : 0;
    if ( !v7 )
      goto LABEL_38;
    v11 = lstrlenW(String);
    v4 = RegSetValueExW(v19, 0, 0, 1u, (const BYTE *)String, 2 * v11 + 2);
    if ( !v4 )
    {
      v12 = lstrlenW(String);
      v4 = RegSetValueExW(v23, 0, 0, 1u, (const BYTE *)String, 2 * v12 + 2);
      if ( !v4 )
      {
        String[0] = 0;
        v4 = RegSetValueExW(v19, L"DllSurrogate", 0, 1u, (const BYTE *)String, 2u);
        if ( !v4 )
        {
          *(_DWORD *)Data = 6;
          v4 = RegSetValueExW(v19, L"AuthenticationLevel", 0, 4u, Data, 4u);
          if ( !v4 )
          {
            PermissionsBlobForDCOMConfig = GetPermissionsBlobForDCOMConfig(&lpData, (unsigned int *)Data);
            v3 = lpData;
            v2 = PermissionsBlobForDCOMConfig;
            if ( PermissionsBlobForDCOMConfig )
              goto LABEL_38;
            v4 = RegSetValueExW(v19, L"LaunchPermission", 0, 3u, lpData, *(DWORD *)Data);
            if ( !v4 )
            {
              v14 = String;
              do
              {
                if ( v6 == -2147483546 )
                  break;
                v15 = *(WCHAR *)((char *)v14 + (char *)L"{22A769D8-A44E-46FB-B264-0A411E42AEE0}" - (char *)String);
                if ( !v15 )
                  break;
                *v14++ = v15;
                --v6;
              }
              while ( v6 );
              v16 = v14 - 1;
              if ( v6 )
                v16 = v14;
              *v16 = 0;
              v2 = v6 == 0 ? 0x8007007A : 0;
              if ( !v6 )
                goto LABEL_38;
              v17 = lstrlenW(String);
              v4 = RegSetValueExW(v23, L"AppId", 0, 1u, (const BYTE *)String, 2 * v17 + 2);
              if ( !v4 )
                goto LABEL_38;
            }
          }
        }
      }
    }
    goto LABEL_36;
  }
  v2 = (unsigned __int16)v5 | 0x80070000;
  v23 = 0;
  if ( v5 <= 0 )
    v2 = v5;
LABEL_40:
  if ( v19 )
    RegCloseKey(v19);
  if ( v2 && a1 )
  {
    if ( phkResult )
      RegDeleteKeyW(phkResult, L"{DFD0D215-72C0-450d-92B5-10971FC24625}");
    if ( hKey )
      RegDeleteKeyW(hKey, L"{DFD0D215-72C0-450d-92B5-10971FC24625}");
  }
  if ( phkResult )
    RegCloseKey(phkResult);
  if ( hKey )
    RegCloseKey(hKey);
  MemFree(v3);
  return v2;
}

```

## disassembly

```asm
0x18003d858  mov     rax, rsp
0x18003d85b  mov     [rax+8], rbx
0x18003d85f  mov     [rax+10h], rsi
0x18003d863  mov     [rax+18h], rdi
0x18003d867  mov     [rax+20h], r12
0x18003d86b  push    rbp
0x18003d86c  push    r14
0x18003d86e  push    r15
0x18003d870  lea     rbp, [rax-78h]
0x18003d874  sub     rsp, 160h
0x18003d87b  mov     rax, cs:__security_cookie
0x18003d882  xor     rax, rsp
0x18003d885  mov     [rbp+70h+var_20], rax
0x18003d889  xor     r12d, r12d
0x18003d88c  lea     rax, [rsp+170h+hKey]
0x18003d891  mov     r15d, ecx
0x18003d894  mov     [rsp+170h+var_110], r12
0x18003d899  mov     edi, 2001Fh
0x18003d89e  mov     [rsp+170h+hKey], r12
0x18003d8a3  mov     rsi, 0FFFFFFFF80000000h
0x18003d8aa  mov     [rsp+170h+var_100], r12
0x18003d8af  mov     r9d, edi; samDesired
0x18003d8b2  mov     [rsp+170h+var_120], r12
0x18003d8b7  mov     rcx, rsi; hKey
0x18003d8ba  mov     [rsp+170h+lpData], r12
0x18003d8bf  xor     r8d, r8d; ulOptions
0x18003d8c2  mov     [rsp+170h+phkResult], rax; phkResult
0x18003d8c7  lea     rdx, aAppid_0; "AppID"
0x18003d8ce  mov     ebx, r12d
0x18003d8d1  mov     r14d, r12d
0x18003d8d4  call    cs:__imp_RegOpenKeyExW
0x18003d8da  test    eax, eax
0x18003d8dc  jz      short loc_18003D8E8
0x18003d8de  mov     [rsp+170h+hKey], r12
0x18003d8e3  jmp     loc_18003DC4A
0x18003d8e8  lea     rax, [rsp+170h+var_110]
0x18003d8ed  mov     r9d, edi; samDesired
0x18003d8f0  xor     r8d, r8d; ulOptions
0x18003d8f3  mov     [rsp+170h+phkResult], rax; phkResult
0x18003d8f8  lea     rdx, aClsid; "CLSID"
0x18003d8ff  mov     rcx, rsi; hKey
0x18003d902  call    cs:__imp_RegOpenKeyExW
0x18003d908  test    eax, eax
0x18003d90a  jz      short loc_18003D916
0x18003d90c  mov     [rsp+170h+var_110], r12
0x18003d911  jmp     loc_18003DC4A
0x18003d916  mov     rcx, [rsp+170h+hKey]; hKey
0x18003d91b  test    r15d, r15d
0x18003d91e  jnz     short loc_18003D944
0x18003d920  lea     rdx, a22a769d8A44e46; "{22A769D8-A44E-46FB-B264-0A411E42AEE0}"
0x18003d927  call    cs:__imp_RegDeleteKeyW
0x18003d92d  mov     rcx, [rsp+170h+var_110]; hKey
0x18003d932  lea     rdx, aDfd0d21572c045; "{DFD0D215-72C0-450d-92B5-10971FC24625}"
0x18003d939  call    cs:__imp_RegDeleteKeyW
0x18003d93f  jmp     loc_18003DC58
0x18003d944  lea     rax, [rsp+170h+var_120]
0x18003d949  mov     ebx, 20006h
0x18003d94e  lea     rsi, a22a769d8A44e46; "{22A769D8-A44E-46FB-B264-0A411E42AEE0}"
0x18003d955  mov     [rsp+170h+phkResult], rax; phkResult
0x18003d95a  mov     r9d, ebx; samDesired
0x18003d95d  mov     rdx, rsi; lpSubKey
0x18003d960  xor     r8d, r8d; ulOptions
0x18003d963  call    cs:__imp_RegOpenKeyExW
0x18003d969  test    eax, eax
0x18003d96b  jz      short loc_18003D9AC
0x18003d96d  mov     rcx, [rsp+170h+hKey]; hKey
0x18003d972  lea     rax, [rsp+170h+var_120]
0x18003d977  mov     [rsp+170h+lpdwDisposition], r12; lpdwDisposition
0x18003d97c  xor     r9d, r9d; lpClass
0x18003d97f  mov     [rsp+170h+var_138], rax; phkResult
0x18003d984  xor     r8d, r8d; Reserved
0x18003d987  mov     [rsp+170h+lpSecurityAttributes], r12; lpSecurityAttributes
0x18003d98c  mov     rdx, rsi; lpSubKey
0x18003d98f  mov     [rsp+170h+samDesired], ebx; samDesired
0x18003d993  mov     dword ptr [rsp+170h+phkResult], r12d; dwOptions
0x18003d998  call    cs:__imp_RegCreateKeyExW
0x18003d99e  test    eax, eax
0x18003d9a0  jz      short loc_18003D9AC
0x18003d9a2  mov     [rsp+170h+var_120], r12
0x18003d9a7  jmp     loc_18003DC4A
0x18003d9ac  mov     rcx, [rsp+170h+var_110]; hKey
0x18003d9b1  lea     rax, [rsp+170h+var_100]
0x18003d9b6  mov     r9d, ebx; samDesired
0x18003d9b9  mov     [rsp+170h+phkResult], rax; phkResult
0x18003d9be  xor     r8d, r8d; ulOptions
0x18003d9c1  lea     rdx, aDfd0d21572c045; "{DFD0D215-72C0-450d-92B5-10971FC24625}"
0x18003d9c8  call    cs:__imp_RegOpenKeyExW
0x18003d9ce  test    eax, eax
0x18003d9d0  jz      short loc_18003DA23
0x18003d9d2  mov     rcx, [rsp+170h+var_110]; hKey
0x18003d9d7  lea     rax, [rsp+170h+var_100]
0x18003d9dc  mov     [rsp+170h+lpdwDisposition], r12; lpdwDisposition
0x18003d9e1  lea     rdx, aDfd0d21572c045; "{DFD0D215-72C0-450d-92B5-10971FC24625}"
0x18003d9e8  mov     [rsp+170h+var_138], rax; phkResult
0x18003d9ed  xor     r9d, r9d; lpClass
0x18003d9f0  mov     [rsp+170h+lpSecurityAttributes], r12; lpSecurityAttributes
0x18003d9f5  xor     r8d, r8d; Reserved
0x18003d9f8  mov     [rsp+170h+samDesired], ebx; samDesired
0x18003d9fc  mov     dword ptr [rsp+170h+phkResult], r12d; dwOptions
0x18003da01  call    cs:__imp_RegCreateKeyExW
0x18003da07  test    eax, eax
0x18003da09  jz      short loc_18003DA23
0x18003da0b  movzx   ebx, ax
0x18003da0e  or      ebx, 80070000h
0x18003da14  mov     [rsp+170h+var_100], r12
0x18003da19  test    eax, eax
0x18003da1b  cmovle  ebx, eax
0x18003da1e  jmp     loc_18003DC68
0x18003da23  mov     edi, 64h ; 'd'
0x18003da28  lea     r8, aSystemWebConfi; "System.Web.Configuration.RemoteWebConfi"...
0x18003da2f  lea     rax, [rbp+70h+String]
0x18003da33  mov     edx, edi
0x18003da35  sub     r8, rax
0x18003da38  lea     rcx, [rbp+70h+String]
0x18003da3c  lea     rax, [rdx+7FFFFF9Ah]
0x18003da43  test    rax, rax
0x18003da46  jz      short loc_18003DA5F
0x18003da48  movzx   eax, word ptr [r8+rcx]
0x18003da4d  test    ax, ax
0x18003da50  jz      short loc_18003DA5F
0x18003da52  mov     [rcx], ax
0x18003da55  add     rcx, 2
0x18003da59  sub     rdx, 1
0x18003da5d  jnz     short loc_18003DA3C
0x18003da5f  test    rdx, rdx
0x18003da62  lea     rax, [rcx-2]
0x18003da66  cmovnz  rax, rcx
0x18003da6a  mov     [rax], r12w
0x18003da6e  mov     rax, rdx
0x18003da71  neg     rax
0x18003da74  sbb     ebx, ebx
0x18003da76  not     ebx
0x18003da78  and     ebx, 8007007Ah
0x18003da7e  test    rdx, rdx
0x18003da81  jz      loc_18003DC58
0x18003da87  lea     rcx, [rbp+70h+String]; lpString
0x18003da8b  call    cs:__imp_lstrlenW
0x18003da91  mov     rcx, [rsp+170h+var_120]; hKey
0x18003da96  mov     r9d, 1; dwType
0x18003da9c  xor     r8d, r8d; Reserved
0x18003da9f  xor     edx, edx; lpValueName
0x18003daa1  lea     eax, ds:2[rax*2]
0x18003daa8  mov     [rsp+170h+samDesired], eax; cbData
0x18003daac  lea     rax, [rbp+70h+String]
0x18003dab0  mov     [rsp+170h+phkResult], rax; lpData
0x18003dab5  call    cs:__imp_RegSetValueExW
0x18003dabb  test    eax, eax
0x18003dabd  jnz     loc_18003DC4A
0x18003dac3  lea     rcx, [rbp+70h+String]; lpString
0x18003dac7  call    cs:__imp_lstrlenW
0x18003dacd  mov     rcx, [rsp+170h+var_100]; hKey
0x18003dad2  mov     r9d, 1; dwType
0x18003dad8  xor     r8d, r8d; Reserved
0x18003dadb  xor     edx, edx; lpValueName
0x18003dadd  lea     eax, ds:2[rax*2]
0x18003dae4  mov     [rsp+170h+samDesired], eax; cbData
0x18003dae8  lea     rax, [rbp+70h+String]
0x18003daec  mov     [rsp+170h+phkResult], rax; lpData
0x18003daf1  call    cs:__imp_RegSetValueExW
0x18003daf7  test    eax, eax
0x18003daf9  jnz     loc_18003DC4A
0x18003daff  mov     rcx, [rsp+170h+var_120]; hKey
0x18003db04  lea     rax, [rbp+70h+String]
0x18003db08  mov     [rsp+170h+samDesired], 2; cbData
0x18003db10  lea     rdx, aDllsurrogate; "DllSurrogate"
0x18003db17  mov     r9d, 1; dwType
0x18003db1d  mov     [rsp+170h+phkResult], rax; lpData
0x18003db22  xor     r8d, r8d; Reserved
0x18003db25  mov     [rbp+70h+String], r12w
0x18003db2a  call    cs:__imp_RegSetValueExW
0x18003db30  test    eax, eax
0x18003db32  jnz     loc_18003DC4A
0x18003db38  mov     rcx, [rsp+170h+var_120]; hKey
0x18003db3d  lea     r9d, [rax+4]; dwType
0x18003db41  lea     rax, [rsp+170h+Data]
0x18003db46  mov     [rsp+170h+samDesired], r9d; cbData
0x18003db4b  xor     r8d, r8d; Reserved
0x18003db4e  mov     [rsp+170h+phkResult], rax; lpData
0x18003db53  lea     rdx, aAuthentication; "AuthenticationLevel"
0x18003db5a  mov     dword ptr [rsp+170h+Data], 6
0x18003db62  call    cs:__imp_RegSetValueExW
0x18003db68  test    eax, eax
0x18003db6a  jnz     loc_18003DC4A
0x18003db70  lea     rdx, [rsp+170h+Data]; unsigned int *
0x18003db75  lea     rcx, [rsp+170h+lpData]; unsigned __int8 **
0x18003db7a  call    ?GetPermissionsBlobForDCOMConfig@@YAJPEAPEAEPEAK@Z; GetPermissionsBlobForDCOMConfig(uchar * *,ulong *)
0x18003db7f  mov     r14, [rsp+170h+lpData]
0x18003db84  mov     ebx, eax
0x18003db86  test    eax, eax
0x18003db88  jnz     loc_18003DC58
0x18003db8e  mov     eax, dword ptr [rsp+170h+Data]
0x18003db92  lea     r9d, [rbx+3]; dwType
0x18003db96  mov     rcx, [rsp+170h+var_120]; hKey
0x18003db9b  lea     rdx, aLaunchpermissi; "LaunchPermission"
0x18003dba2  mov     [rsp+170h+samDesired], eax; cbData
0x18003dba6  xor     r8d, r8d; Reserved
0x18003dba9  mov     [rsp+170h+phkResult], r14; lpData
0x18003dbae  call    cs:__imp_RegSetValueExW
0x18003dbb4  test    eax, eax
0x18003dbb6  jnz     loc_18003DC4A
0x18003dbbc  lea     rax, [rbp+70h+String]
0x18003dbc0  sub     rsi, rax
0x18003dbc3  lea     rcx, [rbp+70h+String]
0x18003dbc7  lea     rax, [rdi+7FFFFF9Ah]
0x18003dbce  test    rax, rax
0x18003dbd1  jz      short loc_18003DBE9
0x18003dbd3  movzx   eax, word ptr [rsi+rcx]
0x18003dbd7  test    ax, ax
0x18003dbda  jz      short loc_18003DBE9
0x18003dbdc  mov     [rcx], ax
0x18003dbdf  add     rcx, 2
0x18003dbe3  sub     rdi, 1
0x18003dbe7  jnz     short loc_18003DBC7
0x18003dbe9  test    rdi, rdi
0x18003dbec  lea     rax, [rcx-2]
0x18003dbf0  cmovnz  rax, rcx
0x18003dbf4  mov     [rax], r12w
0x18003dbf8  mov     rax, rdi
0x18003dbfb  neg     rax
0x18003dbfe  sbb     ebx, ebx
0x18003dc00  not     ebx
0x18003dc02  and     ebx, 8007007Ah
0x18003dc08  test    rdi, rdi
0x18003dc0b  jz      short loc_18003DC58
0x18003dc0d  lea     rcx, [rbp+70h+String]; lpString
0x18003dc11  call    cs:__imp_lstrlenW
0x18003dc17  mov     rcx, [rsp+170h+var_100]; hKey
0x18003dc1c  lea     rdx, aAppid; "AppId"
0x18003dc23  mov     r9d, 1; dwType
0x18003dc29  xor     r8d, r8d; Reserved
0x18003dc2c  lea     eax, ds:2[rax*2]
0x18003dc33  mov     [rsp+170h+samDesired], eax; cbData
0x18003dc37  lea     rax, [rbp+70h+String]
0x18003dc3b  mov     [rsp+170h+phkResult], rax; lpData
0x18003dc40  call    cs:__imp_RegSetValueExW
0x18003dc46  test    eax, eax
0x18003dc48  jz      short loc_18003DC58
0x18003dc4a  movzx   ebx, ax
0x18003dc4d  or      ebx, 80070000h
0x18003dc53  test    eax, eax
0x18003dc55  cmovle  ebx, eax
0x18003dc58  mov     rcx, [rsp+170h+var_100]; hKey
0x18003dc5d  test    rcx, rcx
0x18003dc60  jz      short loc_18003DC68
0x18003dc62  call    cs:__imp_RegCloseKey
0x18003dc68  mov     rcx, [rsp+170h+var_120]; hKey
0x18003dc6d  test    rcx, rcx
0x18003dc70  jz      short loc_18003DC78
0x18003dc72  call    cs:__imp_RegCloseKey
0x18003dc78  test    ebx, ebx
0x18003dc7a  jz      short loc_18003DCAF
0x18003dc7c  test    r15d, r15d
0x18003dc7f  jz      short loc_18003DCAF
0x18003dc81  mov     rcx, [rsp+170h+var_110]; hKey
0x18003dc86  test    rcx, rcx
0x18003dc89  jz      short loc_18003DC98
0x18003dc8b  lea     rdx, aDfd0d21572c045; "{DFD0D215-72C0-450d-92B5-10971FC24625}"
0x18003dc92  call    cs:__imp_RegDeleteKeyW
0x18003dc98  mov     rcx, [rsp+170h+hKey]; hKey
0x18003dc9d  test    rcx, rcx
0x18003dca0  jz      short loc_18003DCAF
0x18003dca2  lea     rdx, aDfd0d21572c045; "{DFD0D215-72C0-450d-92B5-10971FC24625}"
0x18003dca9  call    cs:__imp_RegDeleteKeyW
0x18003dcaf  mov     rcx, [rsp+170h+var_110]; hKey
0x18003dcb4  test    rcx, rcx
0x18003dcb7  jz      short loc_18003DCBF
0x18003dcb9  call    cs:__imp_RegCloseKey
0x18003dcbf  mov     rcx, [rsp+170h+hKey]; hKey
0x18003dcc4  test    rcx, rcx
0x18003dcc7  jz      short loc_18003DCCF
0x18003dcc9  call    cs:__imp_RegCloseKey
0x18003dccf  mov     rcx, r14; lpMem
0x18003dcd2  call    ?MemFree@@YAXPEAX@Z; MemFree(void *)
0x18003dcd7  mov     eax, ebx
0x18003dcd9  mov     rcx, [rbp+70h+var_20]
0x18003dcdd  xor     rcx, rsp; StackCookie
0x18003dce0  call    __security_check_cookie
0x18003dce5  lea     r11, [rsp+170h+var_10]
0x18003dced  mov     rbx, [r11+20h]
0x18003dcf1  mov     rsi, [r11+28h]
0x18003dcf5  mov     rdi, [r11+30h]
0x18003dcf9  mov     r12, [r11+38h]
0x18003dcfd  mov     rsp, r11
0x18003dd00  pop     r15
0x18003dd02  pop     r14
0x18003dd04  pop     rbp
0x18003dd05  retn
```
