# TraceRegCreateDefaultsW(x,x)

- ea: `0x1000872c`
- end: `0x10008a3e`
- name: `_TraceRegCreateDefaultsW@8`
- size: `786`
- prototype: `int __fastcall(LPCWSTR lpSubKey, PHKEY phkResult)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x100032d0`

## callees

- `0x1000362b`
- `0x10003c20`
- `0x10004567`
- `0x1000872c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x100087d8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x100088ce`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x100087d8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x100088ce`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x100087c9`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x10008869`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1000889d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x100087c9`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x10008869`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1000889d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x100088eb`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x10008910`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1000893b`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1000896a`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x10008999`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x100089c8`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x10008a29`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x100088eb`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x10008910`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1000893b`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1000896a`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x10008999`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x100089c8`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x10008a29`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x10008794`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x100087fd`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x10008794`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x100087fd`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1000883a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1000883a`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x10008a04`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x10008a04`

## string_xrefs

- `0x100087c2`: `FileDirectory`
- `0x10008a22`: `FileDirectory`

## pseudocode

```c
int __fastcall TraceRegCreateDefaultsW(LPCWSTR lpSubKey, PHKEY phkResult)
{
  int result; // eax
  LSTATUS v5; // ebx
  size_t v6; // [esp+0h] [ebp-440h]
  const wchar_t *v7; // [esp+4h] [ebp-43Ch]
  DWORD dwDisposition; // [esp+Ch] [ebp-434h] BYREF
  BYTE v9[4]; // [esp+10h] [ebp-430h] BYREF
  BYTE v10[4]; // [esp+14h] [ebp-42Ch] BYREF
  BYTE v11[4]; // [esp+18h] [ebp-428h] BYREF
  HKEY phkResulta; // [esp+1Ch] [ebp-424h] BYREF
  DWORD Type; // [esp+20h] [ebp-420h] BYREF
  BYTE v14[4]; // [esp+24h] [ebp-41Ch] BYREF
  DWORD cbData; // [esp+28h] [ebp-418h] BYREF
  wchar_t Data[260]; // [esp+2Ch] [ebp-414h] BYREF
  WCHAR String[260]; // [esp+234h] [ebp-20Ch] BYREF

  memset(Data, 0, sizeof(Data));
  phkResulta = 0;
  Type = 0;
  *(_DWORD *)v10 = 0;
  *(_DWORD *)v11 = 0;
  *phkResult = 0;
  result = RegCreateKeyExW(
             HKEY_LOCAL_MACHINE,
             L"Software\\Microsoft\\Tracing",
             0,
             0,
             0,
             0x2001Fu,
             0,
             phkResult,
             &dwDisposition);
  if ( !result )
  {
    cbData = 520;
    v5 = RegQueryValueExW(*phkResult, L"FileDirectory", 0, &Type, (LPBYTE)Data, &cbData);
    if ( *phkResult )
    {
      RegCloseKey(*phkResult);
      *phkResult = 0;
    }
    result = RegCreateKeyExW(HKEY_LOCAL_MACHINE, lpSubKey, 0, 0, 0, 0x2001Bu, 0, phkResult, &dwDisposition);
    if ( !result )
    {
      cbData = 4;
      *(_DWORD *)v14 = 0;
      *(_DWORD *)v9 = 0;
      if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\Tracing", 0, 0x20119u, &phkResulta) )
      {
        if ( !RegQueryValueExW(phkResulta, L"EnableFileTracing", 0, &Type, v10, &cbData) && Type == 4 )
        {
          if ( !RegQueryValueExW(phkResulta, L"EnableAutoFileTracing", 0, &Type, v11, &cbData) && Type == 4 )
            *(_DWORD *)v9 = *(_DWORD *)v11;
          *(_DWORD *)v14 = *(_DWORD *)v10;
        }
        RegCloseKey(phkResulta);
      }
      result = RegSetValueExW(*phkResult, L"EnableFileTracing", 0, 4u, v14, cbData);
      if ( !result )
      {
        result = RegSetValueExW(*phkResult, L"EnableAutoFileTracing", 0, 4u, v9, cbData);
        if ( !result )
        {
          *(_DWORD *)v14 = 0;
          result = RegSetValueExW(*phkResult, L"EnableConsoleTracing", 0, 4u, v14, cbData);
          if ( !result )
          {
            *(_DWORD *)v14 = -65536;
            result = RegSetValueExW(*phkResult, L"FileTracingMask", 0, 4u, v14, cbData);
            if ( !result )
            {
              *(_DWORD *)v14 = -65536;
              result = RegSetValueExW(*phkResult, L"ConsoleTracingMask", 0, 4u, v14, cbData);
              if ( !result )
              {
                *(_DWORD *)v14 = 0x100000;
                result = RegSetValueExW(*phkResult, L"MaxFileSize", 0, 4u, v14, cbData);
                if ( !result )
                {
                  if ( v5 )
                    result = StringCchCopyW((STRSAFE_LPWSTR)L"%windir%\\tracing", v6, v7);
                  else
                    result = StringCchCopyW(Data, v6, v7);
                  if ( result >= 0 )
                  {
                    cbData = 2 * lstrlenW(String) + 2;
                    return RegSetValueExW(*phkResult, L"FileDirectory", 0, 2u, (const BYTE *)String, cbData);
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
0x1000872c  mov     edi, edi
0x1000872e  push    ebp
0x1000872f  mov     ebp, esp
0x10008731  sub     esp, 434h
0x10008737  mov     eax, ___security_cookie
0x1000873c  xor     eax, ebp
0x1000873e  mov     [ebp+var_4], eax
0x10008741  push    ebx
0x10008742  push    esi; pszSrc
0x10008743  push    edi; cchDest
0x10008744  push    208h; Size
0x10008749  xor     ebx, ebx
0x1000874b  lea     eax, [ebp+Data]
0x10008751  push    ebx; Val
0x10008752  push    eax; void *
0x10008753  mov     esi, edx
0x10008755  mov     edi, ecx
0x10008757  call    _memset
0x1000875c  add     esp, 0Ch
0x1000875f  mov     [ebp+phkResult], ebx
0x10008765  lea     eax, [ebp+dwDisposition]
0x1000876b  mov     [ebp+Type], ebx
0x10008771  mov     dword ptr [ebp+var_42C], ebx
0x10008777  mov     dword ptr [ebp+var_428], ebx
0x1000877d  push    eax; lpdwDisposition
0x1000877e  push    esi; phkResult
0x1000877f  push    ebx; lpSecurityAttributes
0x10008780  push    2001Fh; samDesired
0x10008785  push    ebx; dwOptions
0x10008786  push    ebx; lpClass
0x10008787  push    ebx; Reserved
0x10008788  push    offset aSoftwareMicros; "Software\\Microsoft\\Tracing"
0x1000878d  push    80000002h; hKey
0x10008792  mov     [esi], ebx
0x10008794  call    ds:__imp__RegCreateKeyExW@36; RegCreateKeyExW(x,x,x,x,x,x,x,x,x)
0x1000879a  test    eax, eax
0x1000879c  jnz     loc_10008A2F
0x100087a2  lea     eax, [ebp+cbData]
0x100087a8  mov     [ebp+cbData], 208h
0x100087b2  push    eax; lpcbData
0x100087b3  lea     eax, [ebp+Data]
0x100087b9  push    eax; lpData
0x100087ba  lea     eax, [ebp+Type]
0x100087c0  push    eax; lpType
0x100087c1  push    ebx; lpReserved
0x100087c2  push    offset aFiledirectory; "FileDirectory"
0x100087c7  push    dword ptr [esi]; hKey
0x100087c9  call    ds:__imp__RegQueryValueExW@24; RegQueryValueExW(x,x,x,x,x,x)
0x100087cf  cmp     dword ptr [esi], 0
0x100087d2  mov     ebx, eax
0x100087d4  jz      short loc_100087E4
0x100087d6  push    dword ptr [esi]; hKey
0x100087d8  call    ds:__imp__RegCloseKey@4; RegCloseKey(x)
0x100087de  xor     ecx, ecx
0x100087e0  mov     [esi], ecx
0x100087e2  jmp     short loc_100087E6
0x100087e4  xor     ecx, ecx
0x100087e6  lea     eax, [ebp+dwDisposition]
0x100087ec  push    eax; lpdwDisposition
0x100087ed  push    esi; phkResult
0x100087ee  push    ecx; lpSecurityAttributes
0x100087ef  push    2001Bh; samDesired
0x100087f4  push    ecx; dwOptions
0x100087f5  push    ecx; lpClass
0x100087f6  push    ecx; Reserved
0x100087f7  push    edi; lpSubKey
0x100087f8  push    80000002h; hKey
0x100087fd  call    ds:__imp__RegCreateKeyExW@36; RegCreateKeyExW(x,x,x,x,x,x,x,x,x)
0x10008803  test    eax, eax
0x10008805  jnz     loc_10008A2F
0x1000880b  lea     eax, [ebp+phkResult]
0x10008811  mov     [ebp+cbData], 4
0x1000881b  push    eax; phkResult
0x1000881c  push    20119h; samDesired
0x10008821  xor     edi, edi
0x10008823  push    edi; ulOptions
0x10008824  push    offset aSoftwareMicros; "Software\\Microsoft\\Tracing"
0x10008829  push    80000002h; hKey
0x1000882e  mov     dword ptr [ebp+var_41C], edi
0x10008834  mov     dword ptr [ebp+var_430], edi
0x1000883a  call    ds:__imp__RegOpenKeyExW@20; RegOpenKeyExW(x,x,x,x,x)
0x10008840  test    eax, eax
0x10008842  jnz     loc_100088D4
0x10008848  lea     eax, [ebp+cbData]
0x1000884e  push    eax; lpcbData
0x1000884f  lea     eax, [ebp+var_42C]
0x10008855  push    eax; lpData
0x10008856  lea     eax, [ebp+Type]
0x1000885c  push    eax; lpType
0x1000885d  push    edi; lpReserved
0x1000885e  push    offset aEnablefiletrac; "EnableFileTracing"
0x10008863  push    [ebp+phkResult]; hKey
0x10008869  call    ds:__imp__RegQueryValueExW@24; RegQueryValueExW(x,x,x,x,x,x)
0x1000886f  test    eax, eax
0x10008871  jnz     short loc_100088C8
0x10008873  cmp     [ebp+Type], 4
0x1000887a  jnz     short loc_100088C8
0x1000887c  lea     eax, [ebp+cbData]
0x10008882  push    eax; lpcbData
0x10008883  lea     eax, [ebp+var_428]
0x10008889  push    eax; lpData
0x1000888a  lea     eax, [ebp+Type]
0x10008890  push    eax; lpType
0x10008891  push    edi; lpReserved
0x10008892  push    offset aEnableautofile_0; "EnableAutoFileTracing"
0x10008897  push    [ebp+phkResult]; hKey
0x1000889d  call    ds:__imp__RegQueryValueExW@24; RegQueryValueExW(x,x,x,x,x,x)
0x100088a3  test    eax, eax
0x100088a5  jnz     short loc_100088BC
0x100088a7  cmp     [ebp+Type], 4
0x100088ae  jnz     short loc_100088BC
0x100088b0  mov     eax, dword ptr [ebp+var_428]
0x100088b6  mov     dword ptr [ebp+var_430], eax
0x100088bc  mov     eax, dword ptr [ebp+var_42C]
0x100088c2  mov     dword ptr [ebp+var_41C], eax
0x100088c8  push    [ebp+phkResult]; hKey
0x100088ce  call    ds:__imp__RegCloseKey@4; RegCloseKey(x)
0x100088d4  push    [ebp+cbData]; cbData
0x100088da  lea     eax, [ebp+var_41C]
0x100088e0  push    eax; lpData
0x100088e1  push    4; dwType
0x100088e3  push    edi; Reserved
0x100088e4  push    offset aEnablefiletrac; "EnableFileTracing"
0x100088e9  push    dword ptr [esi]; hKey
0x100088eb  call    ds:__imp__RegSetValueExW@24; RegSetValueExW(x,x,x,x,x,x)
0x100088f1  test    eax, eax
0x100088f3  jnz     loc_10008A2F
0x100088f9  push    [ebp+cbData]; cbData
0x100088ff  lea     eax, [ebp+var_430]
0x10008905  push    eax; lpData
0x10008906  push    4; dwType
0x10008908  push    edi; Reserved
0x10008909  push    offset aEnableautofile_0; "EnableAutoFileTracing"
0x1000890e  push    dword ptr [esi]; hKey
0x10008910  call    ds:__imp__RegSetValueExW@24; RegSetValueExW(x,x,x,x,x,x)
0x10008916  test    eax, eax
0x10008918  jnz     loc_10008A2F
0x1000891e  push    [ebp+cbData]; cbData
0x10008924  lea     eax, [ebp+var_41C]
0x1000892a  mov     dword ptr [ebp+var_41C], edi
0x10008930  push    eax; lpData
0x10008931  push    4; dwType
0x10008933  push    edi; Reserved
0x10008934  push    offset aEnableconsolet; "EnableConsoleTracing"
0x10008939  push    dword ptr [esi]; hKey
0x1000893b  call    ds:__imp__RegSetValueExW@24; RegSetValueExW(x,x,x,x,x,x)
0x10008941  test    eax, eax
0x10008943  jnz     loc_10008A2F
0x10008949  push    [ebp+cbData]; cbData
0x1000894f  lea     eax, [ebp+var_41C]
0x10008955  mov     dword ptr [ebp+var_41C], 0FFFF0000h
0x1000895f  push    eax; lpData
0x10008960  push    4; dwType
0x10008962  push    edi; Reserved
0x10008963  push    offset aFiletracingmas; "FileTracingMask"
0x10008968  push    dword ptr [esi]; hKey
0x1000896a  call    ds:__imp__RegSetValueExW@24; RegSetValueExW(x,x,x,x,x,x)
0x10008970  test    eax, eax
0x10008972  jnz     loc_10008A2F
0x10008978  push    [ebp+cbData]; cbData
0x1000897e  lea     eax, [ebp+var_41C]
0x10008984  mov     dword ptr [ebp+var_41C], 0FFFF0000h
0x1000898e  push    eax; lpData
0x1000898f  push    4; dwType
0x10008991  push    edi; Reserved
0x10008992  push    offset aConsoletracing_0; "ConsoleTracingMask"
0x10008997  push    dword ptr [esi]; hKey
0x10008999  call    ds:__imp__RegSetValueExW@24; RegSetValueExW(x,x,x,x,x,x)
0x1000899f  test    eax, eax
0x100089a1  jnz     loc_10008A2F
0x100089a7  push    [ebp+cbData]; cbData
0x100089ad  lea     eax, [ebp+var_41C]
0x100089b3  mov     dword ptr [ebp+var_41C], 100000h
0x100089bd  push    eax; lpData
0x100089be  push    4; dwType
0x100089c0  push    edi; Reserved
0x100089c1  push    offset aMaxfilesize_0; "MaxFileSize"
0x100089c6  push    dword ptr [esi]; hKey
0x100089c8  call    ds:__imp__RegSetValueExW@24; RegSetValueExW(x,x,x,x,x,x)
0x100089ce  test    eax, eax
0x100089d0  jnz     short loc_10008A2F
0x100089d2  lea     ecx, [ebp+String]
0x100089d8  mov     edx, 104h
0x100089dd  test    ebx, ebx
0x100089df  jnz     short loc_100089EA
0x100089e1  lea     eax, [ebp+Data]
0x100089e7  push    eax
0x100089e8  jmp     short loc_100089EF
0x100089ea  push    offset aWindirTracing; "%windir%\\tracing"
0x100089ef  call    _StringCchCopyW@12; StringCchCopyW(x,x,x)
0x100089f4  test    eax, eax
0x100089f6  jns     short loc_100089FD
0x100089f8  movzx   eax, ax
0x100089fb  jmp     short loc_10008A2F
0x100089fd  lea     eax, [ebp+String]
0x10008a03  push    eax; lpString
0x10008a04  call    ds:__imp__lstrlenW@4; lstrlenW(x)
0x10008a0a  lea     eax, ds:2[eax*2]
0x10008a11  push    eax; cbData
0x10008a12  mov     [ebp+cbData], eax
0x10008a18  lea     eax, [ebp+String]
0x10008a1e  push    eax; lpData
0x10008a1f  push    2; dwType
0x10008a21  push    edi; Reserved
0x10008a22  push    offset aFiledirectory; "FileDirectory"
0x10008a27  push    dword ptr [esi]; hKey
0x10008a29  call    ds:__imp__RegSetValueExW@24; RegSetValueExW(x,x,x,x,x,x)
0x10008a2f  mov     ecx, [ebp+var_4]
0x10008a32  pop     edi
0x10008a33  pop     esi
0x10008a34  xor     ecx, ebp; StackCookie
0x10008a36  pop     ebx
0x10008a37  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10008a3c  leave
0x10008a3d  retn
```
