# TraceRegCreateDefaultsA(x,x)

- ea: `0x100083b2`
- end: `0x100086bd`
- name: `_TraceRegCreateDefaultsA@8`
- size: `779`
- prototype: `int __fastcall(LPCSTR lpSubKey, PHKEY phkResult)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x10002870`

## callees

- `0x10002d80`
- `0x10003c20`
- `0x10004567`
- `0x100083b2`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x100084c0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x100084c0`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x1000844f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x100084ef`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x10008523`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x1000844f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x100084ef`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x10008523`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1000845e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x10008554`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1000845e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x10008554`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x10008571`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x10008596`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x100085c1`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x100085f0`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x1000861f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x1000864e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x100086a8`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x10008571`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x10008596`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x100085c1`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x100085f0`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x1000861f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x1000864e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x100086a8`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExA` at `0x1000841a`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExA` at `0x10008483`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExA` at `0x1000841a`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExA` at `0x10008483`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenA` at `0x10008689`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenA` at `0x10008689`

## string_xrefs

- `0x10008448`: `FileDirectory`
- `0x100086a1`: `FileDirectory`

## pseudocode

```c
int __fastcall TraceRegCreateDefaultsA(LPCSTR lpSubKey, PHKEY phkResult)
{
  int result; // eax
  LSTATUS v5; // ebx
  char *v6; // eax
  size_t v7; // [esp+0h] [ebp-238h]
  const char *v8; // [esp+4h] [ebp-234h]
  DWORD dwDisposition; // [esp+Ch] [ebp-22Ch] BYREF
  BYTE v10[4]; // [esp+10h] [ebp-228h] BYREF
  BYTE v11[4]; // [esp+14h] [ebp-224h] BYREF
  BYTE v12[4]; // [esp+18h] [ebp-220h] BYREF
  HKEY phkResulta; // [esp+1Ch] [ebp-21Ch] BYREF
  DWORD Type; // [esp+20h] [ebp-218h] BYREF
  BYTE v15[4]; // [esp+24h] [ebp-214h] BYREF
  DWORD cbData; // [esp+28h] [ebp-210h] BYREF
  CHAR String[260]; // [esp+2Ch] [ebp-20Ch] BYREF
  BYTE Data[260]; // [esp+130h] [ebp-108h] BYREF

  memset(Data, 0, sizeof(Data));
  phkResulta = 0;
  Type = 0;
  *(_DWORD *)v11 = 0;
  *(_DWORD *)v12 = 0;
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
    cbData = 260;
    v5 = RegQueryValueExA(*phkResult, "FileDirectory", 0, &Type, Data, &cbData);
    if ( *phkResult )
    {
      RegCloseKey(*phkResult);
      *phkResult = 0;
    }
    result = RegCreateKeyExA(HKEY_LOCAL_MACHINE, lpSubKey, 0, 0, 0, 0x2001Bu, 0, phkResult, &dwDisposition);
    if ( !result )
    {
      cbData = 4;
      *(_DWORD *)v15 = 0;
      *(_DWORD *)v10 = 0;
      if ( !RegOpenKeyExA(HKEY_LOCAL_MACHINE, "Software\\Microsoft\\Tracing", 0, 0x20119u, &phkResulta) )
      {
        if ( !RegQueryValueExA(phkResulta, "EnableFileTracing", 0, &Type, v11, &cbData) && Type == 4 )
        {
          if ( !RegQueryValueExA(phkResulta, "EnableAutoFileTracing", 0, &Type, v12, &cbData) && Type == 4 )
            *(_DWORD *)v10 = *(_DWORD *)v12;
          *(_DWORD *)v15 = *(_DWORD *)v11;
        }
        RegCloseKey(phkResulta);
      }
      result = RegSetValueExA(*phkResult, "EnableFileTracing", 0, 4u, v15, cbData);
      if ( !result )
      {
        result = RegSetValueExA(*phkResult, "EnableAutoFileTracing", 0, 4u, v10, cbData);
        if ( !result )
        {
          *(_DWORD *)v15 = 0;
          result = RegSetValueExA(*phkResult, "EnableConsoleTracing", 0, 4u, v15, cbData);
          if ( !result )
          {
            *(_DWORD *)v15 = -65536;
            result = RegSetValueExA(*phkResult, "FileTracingMask", 0, 4u, v15, cbData);
            if ( !result )
            {
              *(_DWORD *)v15 = -65536;
              result = RegSetValueExA(*phkResult, "ConsoleTracingMask", 0, 4u, v15, cbData);
              if ( !result )
              {
                *(_DWORD *)v15 = 0x100000;
                result = RegSetValueExA(*phkResult, "MaxFileSize", 0, 4u, v15, cbData);
                if ( !result )
                {
                  v6 = "%windir%\\tracing";
                  if ( !v5 )
                    v6 = (char *)Data;
                  result = StringCchCopyA(v6, v7, v8);
                  if ( result >= 0 )
                  {
                    cbData = lstrlenA(String) + 1;
                    return RegSetValueExA(*phkResult, "FileDirectory", 0, 2u, (const BYTE *)String, cbData);
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
0x100083b2  mov     edi, edi
0x100083b4  push    ebp
0x100083b5  mov     ebp, esp
0x100083b7  sub     esp, 22Ch
0x100083bd  mov     eax, ___security_cookie
0x100083c2  xor     eax, ebp
0x100083c4  mov     [ebp+var_4], eax
0x100083c7  push    ebx
0x100083c8  push    esi; pszSrc
0x100083c9  push    edi; cchDest
0x100083ca  push    104h; Size
0x100083cf  xor     ebx, ebx
0x100083d1  lea     eax, [ebp+Data]
0x100083d7  push    ebx; Val
0x100083d8  push    eax; void *
0x100083d9  mov     esi, edx
0x100083db  mov     edi, ecx
0x100083dd  call    _memset
0x100083e2  add     esp, 0Ch
0x100083e5  mov     [ebp+phkResult], ebx
0x100083eb  lea     eax, [ebp+dwDisposition]
0x100083f1  mov     [ebp+Type], ebx
0x100083f7  mov     dword ptr [ebp+var_224], ebx
0x100083fd  mov     dword ptr [ebp+var_220], ebx
0x10008403  push    eax; lpdwDisposition
0x10008404  push    esi; phkResult
0x10008405  push    ebx; lpSecurityAttributes
0x10008406  push    2001Fh; samDesired
0x1000840b  push    ebx; dwOptions
0x1000840c  push    ebx; lpClass
0x1000840d  push    ebx; Reserved
0x1000840e  push    offset SubKey; "Software\\Microsoft\\Tracing"
0x10008413  push    80000002h; hKey
0x10008418  mov     [esi], ebx
0x1000841a  call    ds:__imp__RegCreateKeyExA@36; RegCreateKeyExA(x,x,x,x,x,x,x,x,x)
0x10008420  test    eax, eax
0x10008422  jnz     loc_100086AE
0x10008428  lea     eax, [ebp+cbData]
0x1000842e  mov     [ebp+cbData], 104h
0x10008438  push    eax; lpcbData
0x10008439  lea     eax, [ebp+Data]
0x1000843f  push    eax; lpData
0x10008440  lea     eax, [ebp+Type]
0x10008446  push    eax; lpType
0x10008447  push    ebx; lpReserved
0x10008448  push    offset aFiledirectory_0; "FileDirectory"
0x1000844d  push    dword ptr [esi]; hKey
0x1000844f  call    ds:__imp__RegQueryValueExA@24; RegQueryValueExA(x,x,x,x,x,x)
0x10008455  cmp     dword ptr [esi], 0
0x10008458  mov     ebx, eax
0x1000845a  jz      short loc_1000846A
0x1000845c  push    dword ptr [esi]; hKey
0x1000845e  call    ds:__imp__RegCloseKey@4; RegCloseKey(x)
0x10008464  xor     ecx, ecx
0x10008466  mov     [esi], ecx
0x10008468  jmp     short loc_1000846C
0x1000846a  xor     ecx, ecx
0x1000846c  lea     eax, [ebp+dwDisposition]
0x10008472  push    eax; lpdwDisposition
0x10008473  push    esi; phkResult
0x10008474  push    ecx; lpSecurityAttributes
0x10008475  push    2001Bh; samDesired
0x1000847a  push    ecx; dwOptions
0x1000847b  push    ecx; lpClass
0x1000847c  push    ecx; Reserved
0x1000847d  push    edi; lpSubKey
0x1000847e  push    80000002h; hKey
0x10008483  call    ds:__imp__RegCreateKeyExA@36; RegCreateKeyExA(x,x,x,x,x,x,x,x,x)
0x10008489  test    eax, eax
0x1000848b  jnz     loc_100086AE
0x10008491  lea     eax, [ebp+phkResult]
0x10008497  mov     [ebp+cbData], 4
0x100084a1  push    eax; phkResult
0x100084a2  push    20119h; samDesired
0x100084a7  xor     edi, edi
0x100084a9  push    edi; ulOptions
0x100084aa  push    offset SubKey; "Software\\Microsoft\\Tracing"
0x100084af  push    80000002h; hKey
0x100084b4  mov     dword ptr [ebp+var_214], edi
0x100084ba  mov     dword ptr [ebp+var_228], edi
0x100084c0  call    ds:__imp__RegOpenKeyExA@20; RegOpenKeyExA(x,x,x,x,x)
0x100084c6  test    eax, eax
0x100084c8  jnz     loc_1000855A
0x100084ce  lea     eax, [ebp+cbData]
0x100084d4  push    eax; lpcbData
0x100084d5  lea     eax, [ebp+var_224]
0x100084db  push    eax; lpData
0x100084dc  lea     eax, [ebp+Type]
0x100084e2  push    eax; lpType
0x100084e3  push    edi; lpReserved
0x100084e4  push    offset aEnablefiletrac_0; "EnableFileTracing"
0x100084e9  push    [ebp+phkResult]; hKey
0x100084ef  call    ds:__imp__RegQueryValueExA@24; RegQueryValueExA(x,x,x,x,x,x)
0x100084f5  test    eax, eax
0x100084f7  jnz     short loc_1000854E
0x100084f9  cmp     [ebp+Type], 4
0x10008500  jnz     short loc_1000854E
0x10008502  lea     eax, [ebp+cbData]
0x10008508  push    eax; lpcbData
0x10008509  lea     eax, [ebp+var_220]
0x1000850f  push    eax; lpData
0x10008510  lea     eax, [ebp+Type]
0x10008516  push    eax; lpType
0x10008517  push    edi; lpReserved
0x10008518  push    offset aEnableautofile; "EnableAutoFileTracing"
0x1000851d  push    [ebp+phkResult]; hKey
0x10008523  call    ds:__imp__RegQueryValueExA@24; RegQueryValueExA(x,x,x,x,x,x)
0x10008529  test    eax, eax
0x1000852b  jnz     short loc_10008542
0x1000852d  cmp     [ebp+Type], 4
0x10008534  jnz     short loc_10008542
0x10008536  mov     eax, dword ptr [ebp+var_220]
0x1000853c  mov     dword ptr [ebp+var_228], eax
0x10008542  mov     eax, dword ptr [ebp+var_224]
0x10008548  mov     dword ptr [ebp+var_214], eax
0x1000854e  push    [ebp+phkResult]; hKey
0x10008554  call    ds:__imp__RegCloseKey@4; RegCloseKey(x)
0x1000855a  push    [ebp+cbData]; cbData
0x10008560  lea     eax, [ebp+var_214]
0x10008566  push    eax; lpData
0x10008567  push    4; dwType
0x10008569  push    edi; Reserved
0x1000856a  push    offset aEnablefiletrac_0; "EnableFileTracing"
0x1000856f  push    dword ptr [esi]; hKey
0x10008571  call    ds:__imp__RegSetValueExA@24; RegSetValueExA(x,x,x,x,x,x)
0x10008577  test    eax, eax
0x10008579  jnz     loc_100086AE
0x1000857f  push    [ebp+cbData]; cbData
0x10008585  lea     eax, [ebp+var_228]
0x1000858b  push    eax; lpData
0x1000858c  push    4; dwType
0x1000858e  push    edi; Reserved
0x1000858f  push    offset aEnableautofile; "EnableAutoFileTracing"
0x10008594  push    dword ptr [esi]; hKey
0x10008596  call    ds:__imp__RegSetValueExA@24; RegSetValueExA(x,x,x,x,x,x)
0x1000859c  test    eax, eax
0x1000859e  jnz     loc_100086AE
0x100085a4  push    [ebp+cbData]; cbData
0x100085aa  lea     eax, [ebp+var_214]
0x100085b0  mov     dword ptr [ebp+var_214], edi
0x100085b6  push    eax; lpData
0x100085b7  push    4; dwType
0x100085b9  push    edi; Reserved
0x100085ba  push    offset ValueName; "EnableConsoleTracing"
0x100085bf  push    dword ptr [esi]; hKey
0x100085c1  call    ds:__imp__RegSetValueExA@24; RegSetValueExA(x,x,x,x,x,x)
0x100085c7  test    eax, eax
0x100085c9  jnz     loc_100086AE
0x100085cf  push    [ebp+cbData]; cbData
0x100085d5  lea     eax, [ebp+var_214]
0x100085db  mov     dword ptr [ebp+var_214], 0FFFF0000h
0x100085e5  push    eax; lpData
0x100085e6  push    4; dwType
0x100085e8  push    edi; Reserved
0x100085e9  push    offset aFiletracingmas_0; "FileTracingMask"
0x100085ee  push    dword ptr [esi]; hKey
0x100085f0  call    ds:__imp__RegSetValueExA@24; RegSetValueExA(x,x,x,x,x,x)
0x100085f6  test    eax, eax
0x100085f8  jnz     loc_100086AE
0x100085fe  push    [ebp+cbData]; cbData
0x10008604  lea     eax, [ebp+var_214]
0x1000860a  mov     dword ptr [ebp+var_214], 0FFFF0000h
0x10008614  push    eax; lpData
0x10008615  push    4; dwType
0x10008617  push    edi; Reserved
0x10008618  push    offset aConsoletracing; "ConsoleTracingMask"
0x1000861d  push    dword ptr [esi]; hKey
0x1000861f  call    ds:__imp__RegSetValueExA@24; RegSetValueExA(x,x,x,x,x,x)
0x10008625  test    eax, eax
0x10008627  jnz     loc_100086AE
0x1000862d  push    [ebp+cbData]; cbData
0x10008633  lea     eax, [ebp+var_214]
0x10008639  mov     dword ptr [ebp+var_214], 100000h
0x10008643  push    eax; lpData
0x10008644  push    4; dwType
0x10008646  push    edi; Reserved
0x10008647  push    offset aMaxfilesize; "MaxFileSize"
0x1000864c  push    dword ptr [esi]; hKey
0x1000864e  call    ds:__imp__RegSetValueExA@24; RegSetValueExA(x,x,x,x,x,x)
0x10008654  test    eax, eax
0x10008656  jnz     short loc_100086AE
0x10008658  lea     ecx, [ebp+Data]
0x1000865e  test    ebx, ebx
0x10008660  mov     eax, offset Src; "%windir%\\tracing"
0x10008665  mov     edx, 104h
0x1000866a  cmovz   eax, ecx
0x1000866d  lea     ecx, [ebp+String]
0x10008673  push    eax; pszDest
0x10008674  call    _StringCchCopyA@12; StringCchCopyA(x,x,x)
0x10008679  test    eax, eax
0x1000867b  jns     short loc_10008682
0x1000867d  movzx   eax, ax
0x10008680  jmp     short loc_100086AE
0x10008682  lea     eax, [ebp+String]
0x10008688  push    eax; lpString
0x10008689  call    ds:__imp__lstrlenA@4; lstrlenA(x)
0x1000868f  inc     eax
0x10008690  push    eax; cbData
0x10008691  mov     [ebp+cbData], eax
0x10008697  lea     eax, [ebp+String]
0x1000869d  push    eax; lpData
0x1000869e  push    2; dwType
0x100086a0  push    edi; Reserved
0x100086a1  push    offset aFiledirectory_0; "FileDirectory"
0x100086a6  push    dword ptr [esi]; hKey
0x100086a8  call    ds:__imp__RegSetValueExA@24; RegSetValueExA(x,x,x,x,x,x)
0x100086ae  mov     ecx, [ebp+var_4]
0x100086b1  pop     edi
0x100086b2  pop     esi
0x100086b3  xor     ecx, ebp; StackCookie
0x100086b5  pop     ebx
0x100086b6  call    @__security_check_cookie@4; __security_check_cookie(x)
0x100086bb  leave
0x100086bc  retn
```
