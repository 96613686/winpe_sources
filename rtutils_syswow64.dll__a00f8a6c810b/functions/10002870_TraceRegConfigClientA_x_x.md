# TraceRegConfigClientA(x,x)

- ea: `0x10002870`
- end: `0x10002c87`
- name: `_TraceRegConfigClientA@8`
- size: `1047`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x100027e0`

## callees

- `0x10002870`
- `0x10002c90`
- `0x10002d80`
- `0x10002e2f`
- `0x10003c20`
- `0x10003c40`
- `0x100083b2`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_mbstowcs` at `0x10002b09`
- `api-ms-win-crt-private-l1-1-0!_o_mbstowcs` at `0x10002b09`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x10002c61`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x10002c61`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsA` at `0x10002aea`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsA` at `0x10002aea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x10005710`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x10005710`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x10002bb3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x10002bb3`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x100028d8`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x10002939`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x10002991`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x100029f2`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x10002a4a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x10002aa1`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x100028d8`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x10002939`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x10002991`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x100029f2`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x10002a4a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x10002aa1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x100056eb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x100056eb`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x10002b2d`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x10002b2d`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenA` at `0x10002af9`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenA` at `0x10002af9`

## string_xrefs

- `0x10002a96`: `FileDirectory`

## pseudocode

```c
LSTATUS __fastcall TraceRegConfigClientA(int a1, int a2)
{
  HKEY v3; // eax
  int v4; // edx
  unsigned int v5; // ecx
  int v6; // eax
  int v7; // edx
  unsigned int v8; // ecx
  int v9; // eax
  int v10; // eax
  int v11; // eax
  HANDLE EventA; // eax
  LSTATUS result; // eax
  int v14; // edi
  size_t v15; // [esp+0h] [ebp-22Ch]
  size_t v16; // [esp+0h] [ebp-22Ch]
  size_t v17; // [esp+0h] [ebp-22Ch]
  size_t v18; // [esp+0h] [ebp-22Ch]
  const char *v19; // [esp+4h] [ebp-228h]
  const char *v20; // [esp+4h] [ebp-228h]
  const char *v21; // [esp+4h] [ebp-228h]
  size_t *v22; // [esp+4h] [ebp-228h]
  char psz[4]; // [esp+8h] [ebp-224h] BYREF
  HKEY hKey; // [esp+Ch] [ebp-220h] BYREF
  DWORD Type; // [esp+10h] [ebp-21Ch] BYREF
  DWORD cbData; // [esp+14h] [ebp-218h] BYREF
  BYTE Data[4]; // [esp+18h] [ebp-214h] BYREF
  CHAR SubKey[260]; // [esp+1Ch] [ebp-210h] BYREF
  BYTE v29[264]; // [esp+120h] [ebp-10Ch] BYREF

  hKey = 0;
  *(_DWORD *)psz = 0;
  if ( !a2 )
  {
    v3 = *(HKEY *)(a1 + 1036);
    hKey = v3;
    goto LABEL_3;
  }
  result = StringCchCopyA((STRSAFE_LPSTR)"Software\\Microsoft\\Tracing", v15, v19);
  if ( result < 0 )
    return (unsigned __int16)result;
  result = StringCchCatA((STRSAFE_LPSTR)"\\", v16, v20);
  if ( result < 0 )
    return (unsigned __int16)result;
  result = StringCchCatA((STRSAFE_LPSTR)(a1 + 40), v17, v21);
  if ( result < 0 )
    return (unsigned __int16)result;
  if ( !RegOpenKeyExA(HKEY_LOCAL_MACHINE, SubKey, 0, 0x20019u, &hKey)
    || (v14 = TraceRegCreateDefaultsA(SubKey, &hKey)) == 0 )
  {
    v3 = hKey;
    *(_DWORD *)(a1 + 1036) = hKey;
LABEL_3:
    cbData = 4;
    if ( RegQueryValueExA(v3, "EnableFileTracing", 0, &Type, Data, &cbData) || Type != 4 )
    {
      v4 = 0;
      *(_DWORD *)Data = 0;
    }
    else
    {
      v4 = *(_DWORD *)Data;
    }
    v5 = *(_DWORD *)(a1 + 32) & 0xFFFFFFFD;
    if ( v4 == 1 )
      v5 = *(_DWORD *)(a1 + 32) | 2;
    *(_DWORD *)(a1 + 32) = v5;
    cbData = 4;
    if ( RegQueryValueExA(hKey, "FileTracingMask", 0, &Type, Data, &cbData) || Type != 4 )
    {
      v6 = -65536;
      *(_DWORD *)Data = -65536;
    }
    else
    {
      v6 = *(_DWORD *)Data;
    }
    cbData = 4;
    *(_DWORD *)(a1 + 240) = v6 & 0xFFFF0000;
    if ( RegQueryValueExA(hKey, "EnableConsoleTracing", 0, &Type, Data, &cbData) || Type != 4 )
    {
      v7 = 0;
      *(_DWORD *)Data = 0;
    }
    else
    {
      v7 = *(_DWORD *)Data;
    }
    v8 = *(_DWORD *)(a1 + 32) & 0xFFFFFFFB;
    if ( v7 == 1 )
      v8 = *(_DWORD *)(a1 + 32) | 4;
    *(_DWORD *)(a1 + 32) = v8;
    cbData = 4;
    if ( RegQueryValueExA(hKey, "ConsoleTracingMask", 0, &Type, Data, &cbData) || Type != 4 )
    {
      v9 = -65536;
      *(_DWORD *)Data = -65536;
    }
    else
    {
      v9 = *(_DWORD *)Data;
    }
    cbData = 4;
    *(_DWORD *)(a1 + 244) = v9 & 0xFFFF0000;
    if ( RegQueryValueExA(hKey, "MaxFileSize", 0, &Type, Data, &cbData) || Type != 4 )
    {
      v10 = 0x100000;
      *(_DWORD *)Data = 0x100000;
    }
    else
    {
      v10 = *(_DWORD *)Data;
    }
    *(_DWORD *)(a1 + 248) = v10;
    cbData = 260;
    v29[260] = 0;
    if ( !RegQueryValueExA(hKey, "FileDirectory", 0, &Type, v29, &cbData) && (Type == 2 || Type == 1) )
    {
      if ( cbData >= 0x105 )
        __report_rangecheckfailure();
      v29[cbData] = 0;
      goto LABEL_26;
    }
    result = StringCchCopyA((STRSAFE_LPSTR)"%windir%\\tracing", v15, v19);
    if ( result >= 0 )
    {
      StringCchLengthA(psz, v18, v22);
      cbData = *(_DWORD *)psz + 1;
LABEL_26:
      if ( ExpandEnvironmentStringsA((LPCSTR)v29, (LPSTR)(a1 + 252), 0x104u)
        && ((v11 = lstrlenA((LPCSTR)(a1 + 252)),
             __o_mbstowcs(a1 + 514, a1 + 252, v11 + 1),
             (EventA = *(HANDLE *)(a1 + 1040)) != 0)
         || (EventA = CreateEventA(0, 0, 0, 0), (*(_DWORD *)(a1 + 1040) = EventA) != 0)) )
      {
        return RegNotifyChangeKeyValue(*(HKEY *)(a1 + 1036), 0, 0xEu, EventA, 1);
      }
      else
      {
        return GetLastError();
      }
    }
    return (unsigned __int16)result;
  }
  if ( hKey )
    RegCloseKey(hKey);
  *(_DWORD *)(a1 + 1036) = 0;
  return v14;
}

```

## disassembly

```asm
0x10002870  mov     edi, edi
0x10002872  push    ebp
0x10002873  mov     ebp, esp
0x10002875  sub     esp, 224h
0x1000287b  mov     eax, ___security_cookie
0x10002880  xor     eax, ebp
0x10002882  mov     [ebp+var_4], eax
0x10002885  mov     [ebp+hKey], 0
0x1000288f  mov     dword ptr [ebp+psz], 0
0x10002899  push    esi; pcchLength
0x1000289a  mov     esi, ecx
0x1000289c  push    edi; cchMax
0x1000289d  test    edx, edx
0x1000289f  jnz     loc_10002B43
0x100028a5  mov     eax, [esi+40Ch]
0x100028ab  mov     [ebp+hKey], eax
0x100028b1  lea     ecx, [ebp+cbData]
0x100028b7  mov     [ebp+cbData], 4
0x100028c1  push    ecx; lpcbData
0x100028c2  lea     ecx, [ebp+Data]
0x100028c8  push    ecx; lpData
0x100028c9  lea     ecx, [ebp+Type]
0x100028cf  push    ecx; lpType
0x100028d0  push    0; lpReserved
0x100028d2  push    offset aEnablefiletrac_0; "EnableFileTracing"
0x100028d7  push    eax; hKey
0x100028d8  call    ds:__imp__RegQueryValueExA@24; RegQueryValueExA(x,x,x,x,x,x)
0x100028de  test    eax, eax
0x100028e0  jnz     loc_10002BD2
0x100028e6  cmp     [ebp+Type], 4
0x100028ed  jnz     loc_10002BD2
0x100028f3  mov     edx, dword ptr [ebp+Data]
0x100028f9  mov     ecx, [esi+20h]
0x100028fc  mov     eax, ecx
0x100028fe  or      eax, 2
0x10002901  and     ecx, 0FFFFFFFDh
0x10002904  cmp     edx, 1
0x10002907  cmovz   ecx, eax
0x1000290a  lea     eax, [ebp+cbData]
0x10002910  push    eax; lpcbData
0x10002911  lea     eax, [ebp+Data]
0x10002917  mov     [esi+20h], ecx
0x1000291a  push    eax; lpData
0x1000291b  lea     eax, [ebp+Type]
0x10002921  mov     [ebp+cbData], 4
0x1000292b  push    eax; lpType
0x1000292c  push    0; lpReserved
0x1000292e  push    offset aFiletracingmas_0; "FileTracingMask"
0x10002933  push    [ebp+hKey]; hKey
0x10002939  call    ds:__imp__RegQueryValueExA@24; RegQueryValueExA(x,x,x,x,x,x)
0x1000293f  test    eax, eax
0x10002941  jnz     loc_10002BDF
0x10002947  cmp     [ebp+Type], 4
0x1000294e  jnz     loc_10002BDF
0x10002954  mov     eax, dword ptr [ebp+Data]
0x1000295a  and     eax, 0FFFF0000h
0x1000295f  mov     [ebp+cbData], 4
0x10002969  mov     [esi+0F0h], eax
0x1000296f  lea     eax, [ebp+cbData]
0x10002975  push    eax; lpcbData
0x10002976  lea     eax, [ebp+Data]
0x1000297c  push    eax; lpData
0x1000297d  lea     eax, [ebp+Type]
0x10002983  push    eax; lpType
0x10002984  push    0; lpReserved
0x10002986  push    offset ValueName; "EnableConsoleTracing"
0x1000298b  push    [ebp+hKey]; hKey
0x10002991  call    ds:__imp__RegQueryValueExA@24; RegQueryValueExA(x,x,x,x,x,x)
0x10002997  test    eax, eax
0x10002999  jnz     loc_10002BEF
0x1000299f  cmp     [ebp+Type], 4
0x100029a6  jnz     loc_10002BEF
0x100029ac  mov     edx, dword ptr [ebp+Data]
0x100029b2  mov     ecx, [esi+20h]
0x100029b5  mov     eax, ecx
0x100029b7  or      eax, 4
0x100029ba  and     ecx, 0FFFFFFFBh
0x100029bd  cmp     edx, 1
0x100029c0  cmovz   ecx, eax
0x100029c3  lea     eax, [ebp+cbData]
0x100029c9  push    eax; lpcbData
0x100029ca  lea     eax, [ebp+Data]
0x100029d0  mov     [esi+20h], ecx
0x100029d3  push    eax; lpData
0x100029d4  lea     eax, [ebp+Type]
0x100029da  mov     [ebp+cbData], 4
0x100029e4  push    eax; lpType
0x100029e5  push    0; lpReserved
0x100029e7  push    offset aConsoletracing; "ConsoleTracingMask"
0x100029ec  push    [ebp+hKey]; hKey
0x100029f2  call    ds:__imp__RegQueryValueExA@24; RegQueryValueExA(x,x,x,x,x,x)
0x100029f8  test    eax, eax
0x100029fa  jnz     loc_10002BFC
0x10002a00  cmp     [ebp+Type], 4
0x10002a07  jnz     loc_10002BFC
0x10002a0d  mov     eax, dword ptr [ebp+Data]
0x10002a13  and     eax, 0FFFF0000h
0x10002a18  mov     [ebp+cbData], 4
0x10002a22  mov     [esi+0F4h], eax
0x10002a28  lea     eax, [ebp+cbData]
0x10002a2e  push    eax; lpcbData
0x10002a2f  lea     eax, [ebp+Data]
0x10002a35  push    eax; lpData
0x10002a36  lea     eax, [ebp+Type]
0x10002a3c  push    eax; lpType
0x10002a3d  push    0; lpReserved
0x10002a3f  push    offset aMaxfilesize; "MaxFileSize"
0x10002a44  push    [ebp+hKey]; hKey
0x10002a4a  call    ds:__imp__RegQueryValueExA@24; RegQueryValueExA(x,x,x,x,x,x)
0x10002a50  test    eax, eax
0x10002a52  jnz     loc_10002C0C
0x10002a58  cmp     [ebp+Type], 4
0x10002a5f  jnz     loc_10002C0C
0x10002a65  mov     eax, dword ptr [ebp+Data]
0x10002a6b  mov     [esi+0F8h], eax
0x10002a71  lea     eax, [ebp+cbData]
0x10002a77  push    eax; lpcbData
0x10002a78  lea     eax, [ebp+var_10C]
0x10002a7e  mov     [ebp+cbData], 104h
0x10002a88  push    eax; lpData
0x10002a89  lea     eax, [ebp+Type]
0x10002a8f  mov     [ebp+var_8], 0
0x10002a93  push    eax; lpType
0x10002a94  push    0; lpReserved
0x10002a96  push    offset aFiledirectory_0; "FileDirectory"
0x10002a9b  push    [ebp+hKey]; hKey
0x10002aa1  call    ds:__imp__RegQueryValueExA@24; RegQueryValueExA(x,x,x,x,x,x)
0x10002aa7  test    eax, eax
0x10002aa9  jnz     loc_10002C1C
0x10002aaf  mov     eax, [ebp+Type]
0x10002ab5  cmp     eax, 2
0x10002ab8  jnz     loc_10005702
0x10002abe  mov     eax, [ebp+cbData]
0x10002ac4  cmp     eax, 105h
0x10002ac9  jnb     loc_10002C82
0x10002acf  mov     [ebp+eax+var_10C], 0
0x10002ad7  push    104h; nSize
0x10002adc  lea     edi, [esi+0FCh]
0x10002ae2  push    edi; lpDst
0x10002ae3  lea     eax, [ebp+var_10C]
0x10002ae9  push    eax; lpSrc
0x10002aea  call    ds:__imp__ExpandEnvironmentStringsA@12; ExpandEnvironmentStringsA(x,x,x)
0x10002af0  test    eax, eax
0x10002af2  jz      loc_10005710
0x10002af8  push    edi; lpString
0x10002af9  call    ds:__imp__lstrlenA@4; lstrlenA(x)
0x10002aff  inc     eax
0x10002b00  push    eax
0x10002b01  lea     eax, [esi+202h]
0x10002b07  push    edi
0x10002b08  push    eax
0x10002b09  call    ds:__imp___o_mbstowcs
0x10002b0f  mov     eax, [esi+410h]
0x10002b15  add     esp, 0Ch
0x10002b18  test    eax, eax
0x10002b1a  jz      loc_10002C59
0x10002b20  push    1; fAsynchronous
0x10002b22  push    eax; hEvent
0x10002b23  push    0Eh; dwNotifyFilter
0x10002b25  push    0; bWatchSubtree
0x10002b27  push    dword ptr [esi+40Ch]; hKey
0x10002b2d  call    ds:__imp__RegNotifyChangeKeyValue@20; RegNotifyChangeKeyValue(x,x,x,x,x)
0x10002b33  mov     ecx, [ebp+var_4]
0x10002b36  pop     edi
0x10002b37  xor     ecx, ebp; StackCookie
0x10002b39  pop     esi
0x10002b3a  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10002b3f  mov     esp, ebp
0x10002b41  pop     ebp
0x10002b42  retn
0x10002b43  push    offset SubKey; "Software\\Microsoft\\Tracing"
0x10002b48  mov     edx, 104h
0x10002b4d  lea     ecx, [ebp+SubKey]
0x10002b53  call    _StringCchCopyA@12; StringCchCopyA(x,x,x)
0x10002b58  test    eax, eax
0x10002b5a  js      loc_10002C7A
0x10002b60  push    offset asc_10001294; "\\"
0x10002b65  mov     edx, 104h
0x10002b6a  lea     ecx, [ebp+SubKey]
0x10002b70  call    _StringCchCatA@12; StringCchCatA(x,x,x)
0x10002b75  test    eax, eax
0x10002b77  js      loc_10002C7A
0x10002b7d  lea     eax, [esi+28h]
0x10002b80  mov     edx, 104h
0x10002b85  push    eax; pszDest
0x10002b86  lea     ecx, [ebp+SubKey]
0x10002b8c  call    _StringCchCatA@12; StringCchCatA(x,x,x)
0x10002b91  test    eax, eax
0x10002b93  js      loc_10002C7A
0x10002b99  lea     eax, [ebp+hKey]
0x10002b9f  push    eax; phkResult
0x10002ba0  push    20019h; samDesired
0x10002ba5  push    0; ulOptions
0x10002ba7  lea     eax, [ebp+SubKey]
0x10002bad  push    eax; lpSubKey
0x10002bae  push    80000002h; hKey
0x10002bb3  call    ds:__imp__RegOpenKeyExA@20; RegOpenKeyExA(x,x,x,x,x)
0x10002bb9  test    eax, eax
0x10002bbb  jnz     loc_100056C5
0x10002bc1  mov     eax, [ebp+hKey]
0x10002bc7  mov     [esi+40Ch], eax
0x10002bcd  jmp     loc_100028B1
0x10002bd2  xor     edx, edx
0x10002bd4  mov     dword ptr [ebp+Data], edx
0x10002bda  jmp     loc_100028F9
0x10002bdf  mov     eax, 0FFFF0000h
0x10002be4  mov     dword ptr [ebp+Data], eax
0x10002bea  jmp     loc_1000295A
0x10002bef  xor     edx, edx
0x10002bf1  mov     dword ptr [ebp+Data], edx
0x10002bf7  jmp     loc_100029B2
0x10002bfc  mov     eax, 0FFFF0000h
0x10002c01  mov     dword ptr [ebp+Data], eax
0x10002c07  jmp     loc_10002A13
0x10002c0c  mov     eax, 100000h
0x10002c11  mov     dword ptr [ebp+Data], eax
0x10002c17  jmp     loc_10002A6B
0x10002c1c  push    offset Src; "%windir%\\tracing"
0x10002c21  mov     edx, 104h
0x10002c26  lea     ecx, [ebp+var_10C]
0x10002c2c  call    _StringCchCopyA@12; StringCchCopyA(x,x,x)
0x10002c31  test    eax, eax
0x10002c33  js      short loc_10002C7A
0x10002c35  lea     eax, [ebp+psz]
0x10002c3b  push    eax; psz
0x10002c3c  lea     ecx, [ebp+var_10C]
0x10002c42  call    _StringCchLengthA@12; StringCchLengthA(x,x,x)
0x10002c47  mov     eax, dword ptr [ebp+psz]
0x10002c4d  inc     eax
0x10002c4e  mov     [ebp+cbData], eax
0x10002c54  jmp     loc_10002AD7
0x10002c59  push    0; lpName
0x10002c5b  push    0; bInitialState
0x10002c5d  push    0; bManualReset
0x10002c5f  push    0; lpEventAttributes
0x10002c61  call    ds:__imp__CreateEventA@16; CreateEventA(x,x,x,x)
0x10002c67  mov     [esi+410h], eax
0x10002c6d  test    eax, eax
0x10002c6f  jnz     loc_10002B20
0x10002c75  jmp     loc_10005710
0x10002c7a  movzx   eax, ax
0x10002c7d  jmp     loc_10002B33
0x10002c82  call    ___report_rangecheckfailure
0x100056c5  lea     edx, [ebp+hKey]; phkResult
0x100056cb  lea     ecx, [ebp+SubKey]; lpSubKey
0x100056d1  call    _TraceRegCreateDefaultsA@8; TraceRegCreateDefaultsA(x,x)
0x100056d6  mov     edi, eax
0x100056d8  test    edi, edi
0x100056da  jz      loc_10002BC1
0x100056e0  mov     ecx, [ebp+hKey]
0x100056e6  test    ecx, ecx
0x100056e8  jz      short loc_100056F1
0x100056ea  push    ecx; hKey
0x100056eb  call    ds:__imp__RegCloseKey@4; RegCloseKey(x)
0x100056f1  mov     dword ptr [esi+40Ch], 0
0x100056fb  mov     eax, edi
0x100056fd  jmp     loc_10002B33
0x10005702  cmp     eax, 1
0x10005705  jnz     loc_10002C1C
0x1000570b  jmp     loc_10002ABE
0x10005710  call    ds:__imp__GetLastError@0; GetLastError()
0x10005716  jmp     loc_10002B33
```
