# TraceRegCreateDefaultsA

- ea: `0x180007a68`
- end: `0x180007e2d`
- name: `TraceRegCreateDefaultsA`
- size: `965`
- prototype: `__int64 __fastcall(LPCSTR lpSubKey, PHKEY phkResult)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180002130`

## callees

- `0x1800028a0`
- `0x180003bb0`
- `0x180004456`
- `0x180007a68`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x180007b4c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x180007c04`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x180007c3c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x180007b4c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x180007c04`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x180007c3c`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExA` at `0x180007b11`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExA` at `0x180007b92`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExA` at `0x180007b11`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExA` at `0x180007b92`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x180007c89`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x180007cb9`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x180007cee`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x180007d29`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x180007d5e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x180007d96`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x180007e01`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x180007c89`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x180007cb9`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x180007cee`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x180007d29`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x180007d5e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x180007d96`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x180007e01`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180007b5c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180007c61`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180007b5c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180007c61`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x180007bce`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x180007bce`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenA` at `0x180007dd2`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenA` at `0x180007dd2`

## string_xrefs

- `0x180007b45`: `FileDirectory`
- `0x180007ddb`: `FileDirectory`

## pseudocode

```c
int __fastcall TraceRegCreateDefaultsA(LPCSTR lpSubKey, PHKEY phkResult)
{
  int result; // eax
  HKEY v5; // rcx
  LSTATUS v6; // esi
  HKEY v7; // rcx
  HKEY v8; // rcx
  HKEY v9; // rcx
  HKEY v10; // rcx
  const char *v11; // r8
  int v12; // eax
  HKEY v13; // rcx
  DWORD cbData; // [rsp+50h] [rbp-B0h] BYREF
  BYTE v15[4]; // [rsp+54h] [rbp-ACh] BYREF
  DWORD Type; // [rsp+58h] [rbp-A8h] BYREF
  BYTE v17[4]; // [rsp+5Ch] [rbp-A4h] BYREF
  DWORD dwDisposition; // [rsp+60h] [rbp-A0h] BYREF
  BYTE v19[4]; // [rsp+64h] [rbp-9Ch] BYREF
  BYTE v20[8]; // [rsp+68h] [rbp-98h] BYREF
  HKEY hKey; // [rsp+70h] [rbp-90h] BYREF
  BYTE Data[272]; // [rsp+80h] [rbp-80h] BYREF
  char pszDest[272]; // [rsp+190h] [rbp+90h] BYREF

  cbData = 0;
  *(_DWORD *)v15 = 0;
  *(_DWORD *)v17 = 0;
  dwDisposition = 0;
  memset_0(Data, 0, 0x104u);
  hKey = 0;
  Type = 0;
  *(_DWORD *)v20 = 0;
  *(_DWORD *)v19 = 0;
  *phkResult = 0;
  result = RegCreateKeyExA(
             HKEY_LOCAL_MACHINE,
             "Software\\Microsoft\\Tracing",
             0,
             0,
             0,
             0x2001Fu,
             0,
             phkResult,
             &dwDisposition);
  if ( !result )
  {
    v5 = *phkResult;
    cbData = 260;
    v6 = RegQueryValueExA(v5, "FileDirectory", 0, &Type, Data, &cbData);
    if ( *phkResult )
    {
      RegCloseKey(*phkResult);
      *phkResult = 0;
    }
    result = RegCreateKeyExA(HKEY_LOCAL_MACHINE, lpSubKey, 0, 0, 0, 0x2001Bu, 0, phkResult, &dwDisposition);
    if ( !result )
    {
      *(_DWORD *)v15 = 0;
      cbData = 4;
      *(_DWORD *)v17 = 0;
      if ( !RegOpenKeyExA(HKEY_LOCAL_MACHINE, "Software\\Microsoft\\Tracing", 0, 0x20119u, &hKey) )
      {
        if ( !RegQueryValueExA(hKey, "EnableFileTracing", 0, &Type, v20, &cbData) && Type == 4 )
        {
          if ( !RegQueryValueExA(hKey, "EnableAutoFileTracing", 0, &Type, v19, &cbData) && Type == 4 )
            *(_DWORD *)v17 = *(_DWORD *)v19;
          *(_DWORD *)v15 = *(_DWORD *)v20;
        }
        RegCloseKey(hKey);
      }
      result = RegSetValueExA(*phkResult, "EnableFileTracing", 0, 4u, v15, cbData);
      if ( !result )
      {
        result = RegSetValueExA(*phkResult, "EnableAutoFileTracing", 0, 4u, v17, cbData);
        if ( !result )
        {
          v7 = *phkResult;
          *(_DWORD *)v15 = 0;
          result = RegSetValueExA(v7, "EnableConsoleTracing", 0, 4u, v15, cbData);
          if ( !result )
          {
            v8 = *phkResult;
            *(_DWORD *)v15 = -65536;
            result = RegSetValueExA(v8, "FileTracingMask", 0, 4u, v15, cbData);
            if ( !result )
            {
              v9 = *phkResult;
              *(_DWORD *)v15 = -65536;
              result = RegSetValueExA(v9, "ConsoleTracingMask", 0, 4u, v15, cbData);
              if ( !result )
              {
                v10 = *phkResult;
                *(_DWORD *)v15 = 0x100000;
                result = RegSetValueExA(v10, "MaxFileSize", 0, 4u, v15, cbData);
                if ( !result )
                {
                  v11 = (const char *)Data;
                  if ( v6 )
                    v11 = "%windir%\\tracing";
                  result = StringCchCopyA(pszDest, 0x104u, v11);
                  if ( result >= 0 )
                  {
                    v12 = lstrlenA(pszDest);
                    v13 = *phkResult;
                    cbData = v12 + 1;
                    return RegSetValueExA(v13, "FileDirectory", 0, 2u, (const BYTE *)pszDest, v12 + 1);
                  }
                  else
                  {
                    return (unsigned __int16)result;
                  }
                }
              }
            }
          }
        }
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x180007a68  mov     [rsp-8+arg_10], rbx
0x180007a6d  push    rbp
0x180007a6e  push    rsi
0x180007a6f  push    rdi
0x180007a70  push    r14
0x180007a72  push    r15
0x180007a74  lea     rbp, [rsp-1B0h]
0x180007a7c  sub     rsp, 2B0h
0x180007a83  mov     rax, cs:__security_cookie
0x180007a8a  xor     rax, rsp
0x180007a8d  mov     [rbp+1D0h+var_30], rax
0x180007a94  xor     r14d, r14d
0x180007a97  mov     rbx, rdx
0x180007a9a  mov     rdi, rcx
0x180007a9d  mov     [rsp+2D0h+cbData], r14d
0x180007aa2  xor     edx, edx; Val
0x180007aa4  mov     dword ptr [rsp+2D0h+var_27C], r14d
0x180007aa9  lea     rcx, [rbp+1D0h+Data]; void *
0x180007aad  mov     dword ptr [rsp+2D0h+var_274], r14d
0x180007ab2  mov     r8d, 104h; Size
0x180007ab8  mov     [rsp+2D0h+dwDisposition], r14d
0x180007abd  call    memset_0
0x180007ac2  lea     rax, [rsp+2D0h+dwDisposition]
0x180007ac7  mov     [rsp+2D0h+hKey], r14
0x180007acc  mov     [rsp+2D0h+lpdwDisposition], rax; lpdwDisposition
0x180007ad1  lea     rdx, SubKey; "Software\\Microsoft\\Tracing"
0x180007ad8  mov     [rsp+2D0h+phkResult], rbx; phkResult
0x180007add  mov     r15, 0FFFFFFFF80000002h
0x180007ae4  mov     [rsp+2D0h+lpSecurityAttributes], r14; lpSecurityAttributes
0x180007ae9  xor     r9d, r9d; lpClass
0x180007aec  mov     [rsp+2D0h+samDesired], 2001Fh; samDesired
0x180007af4  xor     r8d, r8d; Reserved
0x180007af7  mov     rcx, r15; hKey
0x180007afa  mov     [rsp+2D0h+dwOptions], r14d; dwOptions
0x180007aff  mov     [rsp+2D0h+Type], r14d
0x180007b04  mov     dword ptr [rsp+2D0h+var_268], r14d
0x180007b09  mov     dword ptr [rsp+2D0h+var_26C], r14d
0x180007b0e  mov     [rbx], r14
0x180007b11  call    cs:__imp_RegCreateKeyExA
0x180007b17  test    eax, eax
0x180007b19  jnz     loc_180007E07
0x180007b1f  mov     rcx, [rbx]; hKey
0x180007b22  lea     rax, [rsp+2D0h+cbData]
0x180007b27  mov     qword ptr [rsp+2D0h+samDesired], rax; lpcbData
0x180007b2c  lea     r9, [rsp+2D0h+Type]; lpType
0x180007b31  lea     rax, [rbp+1D0h+Data]
0x180007b35  mov     [rsp+2D0h+cbData], 104h
0x180007b3d  xor     r8d, r8d; lpReserved
0x180007b40  mov     qword ptr [rsp+2D0h+dwOptions], rax; lpData
0x180007b45  lea     rdx, aFiledirectory_0; "FileDirectory"
0x180007b4c  call    cs:__imp_RegQueryValueExA
0x180007b52  mov     rcx, [rbx]; hKey
0x180007b55  mov     esi, eax
0x180007b57  test    rcx, rcx
0x180007b5a  jz      short loc_180007B65
0x180007b5c  call    cs:__imp_RegCloseKey
0x180007b62  mov     [rbx], r14
0x180007b65  lea     rax, [rsp+2D0h+dwDisposition]
0x180007b6a  xor     r9d, r9d; lpClass
0x180007b6d  mov     [rsp+2D0h+lpdwDisposition], rax; lpdwDisposition
0x180007b72  xor     r8d, r8d; Reserved
0x180007b75  mov     [rsp+2D0h+phkResult], rbx; phkResult
0x180007b7a  mov     rdx, rdi; lpSubKey
0x180007b7d  mov     [rsp+2D0h+lpSecurityAttributes], r14; lpSecurityAttributes
0x180007b82  mov     rcx, r15; hKey
0x180007b85  mov     [rsp+2D0h+samDesired], 2001Bh; samDesired
0x180007b8d  mov     [rsp+2D0h+dwOptions], r14d; dwOptions
0x180007b92  call    cs:__imp_RegCreateKeyExA
0x180007b98  test    eax, eax
0x180007b9a  jnz     loc_180007E07
0x180007ba0  lea     edi, [rax+4]
0x180007ba3  mov     dword ptr [rsp+2D0h+var_27C], r14d
0x180007ba8  lea     rax, [rsp+2D0h+hKey]
0x180007bad  mov     [rsp+2D0h+cbData], edi
0x180007bb1  mov     r9d, 20119h; samDesired
0x180007bb7  mov     qword ptr [rsp+2D0h+dwOptions], rax; phkResult
0x180007bbc  xor     r8d, r8d; ulOptions
0x180007bbf  mov     dword ptr [rsp+2D0h+var_274], r14d
0x180007bc4  lea     rdx, SubKey; "Software\\Microsoft\\Tracing"
0x180007bcb  mov     rcx, r15; hKey
0x180007bce  call    cs:__imp_RegOpenKeyExA
0x180007bd4  test    eax, eax
0x180007bd6  jnz     loc_180007C67
0x180007bdc  mov     rcx, [rsp+2D0h+hKey]; hKey
0x180007be1  lea     rax, [rsp+2D0h+cbData]
0x180007be6  mov     qword ptr [rsp+2D0h+samDesired], rax; lpcbData
0x180007beb  lea     r9, [rsp+2D0h+Type]; lpType
0x180007bf0  lea     rax, [rsp+2D0h+var_268]
0x180007bf5  xor     r8d, r8d; lpReserved
0x180007bf8  lea     rdx, ValueName; "EnableFileTracing"
0x180007bff  mov     qword ptr [rsp+2D0h+dwOptions], rax; lpData
0x180007c04  call    cs:__imp_RegQueryValueExA
0x180007c0a  test    eax, eax
0x180007c0c  jnz     short loc_180007C5C
0x180007c0e  cmp     [rsp+2D0h+Type], edi
0x180007c12  jnz     short loc_180007C5C
0x180007c14  mov     rcx, [rsp+2D0h+hKey]; hKey
0x180007c19  lea     rax, [rsp+2D0h+cbData]
0x180007c1e  mov     qword ptr [rsp+2D0h+samDesired], rax; lpcbData
0x180007c23  lea     r9, [rsp+2D0h+Type]; lpType
0x180007c28  lea     rax, [rsp+2D0h+var_26C]
0x180007c2d  xor     r8d, r8d; lpReserved
0x180007c30  lea     rdx, aEnableautofile; "EnableAutoFileTracing"
0x180007c37  mov     qword ptr [rsp+2D0h+dwOptions], rax; lpData
0x180007c3c  call    cs:__imp_RegQueryValueExA
0x180007c42  test    eax, eax
0x180007c44  jnz     short loc_180007C54
0x180007c46  cmp     [rsp+2D0h+Type], edi
0x180007c4a  jnz     short loc_180007C54
0x180007c4c  mov     eax, dword ptr [rsp+2D0h+var_26C]
0x180007c50  mov     dword ptr [rsp+2D0h+var_274], eax
0x180007c54  mov     eax, dword ptr [rsp+2D0h+var_268]
0x180007c58  mov     dword ptr [rsp+2D0h+var_27C], eax
0x180007c5c  mov     rcx, [rsp+2D0h+hKey]; hKey
0x180007c61  call    cs:__imp_RegCloseKey
0x180007c67  mov     eax, [rsp+2D0h+cbData]
0x180007c6b  lea     rdx, ValueName; "EnableFileTracing"
0x180007c72  mov     rcx, [rbx]; hKey
0x180007c75  mov     r9d, edi; dwType
0x180007c78  mov     [rsp+2D0h+samDesired], eax; cbData
0x180007c7c  xor     r8d, r8d; Reserved
0x180007c7f  lea     rax, [rsp+2D0h+var_27C]
0x180007c84  mov     qword ptr [rsp+2D0h+dwOptions], rax; lpData
0x180007c89  call    cs:__imp_RegSetValueExA
0x180007c8f  test    eax, eax
0x180007c91  jnz     loc_180007E07
0x180007c97  mov     eax, [rsp+2D0h+cbData]
0x180007c9b  lea     rdx, aEnableautofile; "EnableAutoFileTracing"
0x180007ca2  mov     rcx, [rbx]; hKey
0x180007ca5  mov     r9d, edi; dwType
0x180007ca8  mov     [rsp+2D0h+samDesired], eax; cbData
0x180007cac  xor     r8d, r8d; Reserved
0x180007caf  lea     rax, [rsp+2D0h+var_274]
0x180007cb4  mov     qword ptr [rsp+2D0h+dwOptions], rax; lpData
0x180007cb9  call    cs:__imp_RegSetValueExA
0x180007cbf  test    eax, eax
0x180007cc1  jnz     loc_180007E07
0x180007cc7  mov     eax, [rsp+2D0h+cbData]
0x180007ccb  lea     rdx, aEnableconsolet_0; "EnableConsoleTracing"
0x180007cd2  mov     rcx, [rbx]; hKey
0x180007cd5  mov     r9d, edi; dwType
0x180007cd8  mov     [rsp+2D0h+samDesired], eax; cbData
0x180007cdc  xor     r8d, r8d; Reserved
0x180007cdf  lea     rax, [rsp+2D0h+var_27C]
0x180007ce4  mov     dword ptr [rsp+2D0h+var_27C], r14d
0x180007ce9  mov     qword ptr [rsp+2D0h+dwOptions], rax; lpData
0x180007cee  call    cs:__imp_RegSetValueExA
0x180007cf4  test    eax, eax
0x180007cf6  jnz     loc_180007E07
0x180007cfc  mov     eax, [rsp+2D0h+cbData]
0x180007d00  lea     rdx, aFiletracingmas_0; "FileTracingMask"
0x180007d07  mov     rcx, [rbx]; hKey
0x180007d0a  mov     r15d, 0FFFF0000h
0x180007d10  mov     [rsp+2D0h+samDesired], eax; cbData
0x180007d14  mov     r9d, edi; dwType
0x180007d17  lea     rax, [rsp+2D0h+var_27C]
0x180007d1c  mov     dword ptr [rsp+2D0h+var_27C], r15d
0x180007d21  xor     r8d, r8d; Reserved
0x180007d24  mov     qword ptr [rsp+2D0h+dwOptions], rax; lpData
0x180007d29  call    cs:__imp_RegSetValueExA
0x180007d2f  test    eax, eax
0x180007d31  jnz     loc_180007E07
0x180007d37  mov     eax, [rsp+2D0h+cbData]
0x180007d3b  lea     rdx, aConsoletracing; "ConsoleTracingMask"
0x180007d42  mov     rcx, [rbx]; hKey
0x180007d45  mov     r9d, edi; dwType
0x180007d48  mov     [rsp+2D0h+samDesired], eax; cbData
0x180007d4c  xor     r8d, r8d; Reserved
0x180007d4f  lea     rax, [rsp+2D0h+var_27C]
0x180007d54  mov     dword ptr [rsp+2D0h+var_27C], r15d
0x180007d59  mov     qword ptr [rsp+2D0h+dwOptions], rax; lpData
0x180007d5e  call    cs:__imp_RegSetValueExA
0x180007d64  test    eax, eax
0x180007d66  jnz     loc_180007E07
0x180007d6c  mov     eax, [rsp+2D0h+cbData]
0x180007d70  lea     rdx, aMaxfilesize; "MaxFileSize"
0x180007d77  mov     rcx, [rbx]; hKey
0x180007d7a  mov     r9d, edi; dwType
0x180007d7d  mov     [rsp+2D0h+samDesired], eax; cbData
0x180007d81  xor     r8d, r8d; Reserved
0x180007d84  lea     rax, [rsp+2D0h+var_27C]
0x180007d89  mov     dword ptr [rsp+2D0h+var_27C], 100000h
0x180007d91  mov     qword ptr [rsp+2D0h+dwOptions], rax; lpData
0x180007d96  call    cs:__imp_RegSetValueExA
0x180007d9c  test    eax, eax
0x180007d9e  jnz     short loc_180007E07
0x180007da0  lea     rax, Src; "%windir%\\tracing"
0x180007da7  test    esi, esi
0x180007da9  lea     r8, [rbp+1D0h+Data]
0x180007dad  mov     edx, 104h; cchDest
0x180007db2  cmovnz  r8, rax; pszSrc
0x180007db6  lea     rcx, [rbp+1D0h+pszDest]; pszDest
0x180007dbd  call    StringCchCopyA
0x180007dc2  test    eax, eax
0x180007dc4  jns     short loc_180007DCB
0x180007dc6  movzx   eax, ax
0x180007dc9  jmp     short loc_180007E07
0x180007dcb  lea     rcx, [rbp+1D0h+pszDest]; lpString
0x180007dd2  call    cs:__imp_lstrlenA
0x180007dd8  mov     rcx, [rbx]; hKey
0x180007ddb  lea     rdx, aFiledirectory_0; "FileDirectory"
0x180007de2  inc     eax
0x180007de4  mov     r9d, 2; dwType
0x180007dea  mov     [rsp+2D0h+samDesired], eax; cbData
0x180007dee  xor     r8d, r8d; Reserved
0x180007df1  mov     [rsp+2D0h+cbData], eax
0x180007df5  lea     rax, [rbp+1D0h+pszDest]
0x180007dfc  mov     qword ptr [rsp+2D0h+dwOptions], rax; lpData
0x180007e01  call    cs:__imp_RegSetValueExA
0x180007e07  mov     rcx, [rbp+1D0h+var_30]
0x180007e0e  xor     rcx, rsp; StackCookie
0x180007e11  call    __security_check_cookie
0x180007e16  mov     rbx, [rsp+2D0h+arg_10]
0x180007e1e  add     rsp, 2B0h
0x180007e25  pop     r15
0x180007e27  pop     r14
0x180007e29  pop     rdi
0x180007e2a  pop     rsi
0x180007e2b  pop     rbp
0x180007e2c  retn
```
