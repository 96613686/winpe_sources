# TraceRegConfigClientW(x,x)

- ea: `0x100032d0`
- end: `0x10003625`
- name: `_TraceRegConfigClientW@8`
- size: `853`
- prototype: `LSTATUS __usercall@<eax>(int@<ecx>, size_t@<edi>)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x100037bd`

## callees

- `0x100032d0`
- `0x1000362b`
- `0x100036b5`
- `0x10003754`
- `0x10003c20`
- `0x10003c40`
- `0x1000872c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcstombs` at `0x100035c9`
- `api-ms-win-crt-private-l1-1-0!_o_wcstombs` at `0x100035c9`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x100035e0`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x100035e0`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x100035ae`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x100035ae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1000361d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1000361d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x10005ba2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x10005ba2`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x100033ae`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x10003404`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x10003454`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x100034aa`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x100034fa`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1000354b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x100033ae`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x10003404`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x10003454`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x100034aa`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x100034fa`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1000354b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1000336d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1000336d`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x100035fd`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x100035fd`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x100035b9`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x100035b9`

## string_xrefs

- `0x10003540`: `FileDirectory`

## pseudocode

```c
LSTATUS __usercall TraceRegConfigClientW@<eax>(int a1@<ecx>, size_t a2@<edi>)
{
  LSTATUS result; // eax
  HKEY v4; // eax
  int v5; // edx
  unsigned int v6; // ecx
  int v7; // eax
  int v8; // edx
  unsigned int v9; // ecx
  int v10; // eax
  int v11; // eax
  int v12; // eax
  HANDLE EventW; // eax
  int v14; // edi
  size_t v16; // [esp-4h] [ebp-434h]
  size_t v17; // [esp+0h] [ebp-430h]
  size_t v18; // [esp+0h] [ebp-430h]
  size_t v19; // [esp+0h] [ebp-430h]
  const wchar_t *v20; // [esp+0h] [ebp-430h]
  size_t *v21; // [esp+0h] [ebp-430h]
  wchar_t psz[2]; // [esp+4h] [ebp-42Ch] BYREF
  HKEY phkResult; // [esp+8h] [ebp-428h] BYREF
  DWORD Type; // [esp+Ch] [ebp-424h] BYREF
  DWORD cbData; // [esp+10h] [ebp-420h] BYREF
  BYTE Data[4]; // [esp+14h] [ebp-41Ch] BYREF
  WCHAR SubKey[260]; // [esp+18h] [ebp-418h] BYREF
  BYTE v28[2]; // [esp+220h] [ebp-210h] BYREF
  __int16 v29; // [esp+428h] [ebp-8h]

  phkResult = 0;
  result = StringCchCopyW((STRSAFE_LPWSTR)L"Software\\Microsoft\\Tracing", v17, 0);
  if ( result < 0 )
    return (unsigned __int16)result;
  result = StringCchCatW((STRSAFE_LPWSTR)L"\\", v18, *(STRSAFE_LPCWSTR *)psz);
  if ( result < 0 )
    return (unsigned __int16)result;
  result = StringCchCatW((STRSAFE_LPWSTR)(a1 + 104), v19, *(STRSAFE_LPCWSTR *)psz);
  if ( result < 0 )
    return (unsigned __int16)result;
  if ( RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0x20019u, &phkResult)
    && (v14 = TraceRegCreateDefaultsW(SubKey, &phkResult)) != 0 )
  {
    if ( phkResult )
      RegCloseKey(phkResult);
    *(_DWORD *)(a1 + 1036) = 0;
    return v14;
  }
  else
  {
    v4 = phkResult;
    *(_DWORD *)(a1 + 1036) = phkResult;
    cbData = 4;
    if ( RegQueryValueExW(v4, L"EnableFileTracing", 0, &Type, Data, &cbData) || Type != 4 )
    {
      v5 = 0;
      *(_DWORD *)Data = 0;
    }
    else
    {
      v5 = *(_DWORD *)Data;
    }
    v6 = *(_DWORD *)(a1 + 32) & 0xFFFFFFFD;
    if ( v5 == 1 )
      v6 = *(_DWORD *)(a1 + 32) | 2;
    *(_DWORD *)(a1 + 32) = v6;
    cbData = 4;
    if ( RegQueryValueExW(phkResult, L"FileTracingMask", 0, &Type, Data, &cbData) || Type != 4 )
    {
      v7 = -65536;
      *(_DWORD *)Data = -65536;
    }
    else
    {
      v7 = *(_DWORD *)Data;
    }
    cbData = 4;
    *(_DWORD *)(a1 + 240) = v7 & 0xFFFF0000;
    if ( RegQueryValueExW(phkResult, L"EnableConsoleTracing", 0, &Type, Data, &cbData) || Type != 4 )
    {
      v8 = 0;
      *(_DWORD *)Data = 0;
    }
    else
    {
      v8 = *(_DWORD *)Data;
    }
    v9 = *(_DWORD *)(a1 + 32) & 0xFFFFFFFB;
    if ( v8 == 1 )
      v9 = *(_DWORD *)(a1 + 32) | 4;
    *(_DWORD *)(a1 + 32) = v9;
    cbData = 4;
    if ( RegQueryValueExW(phkResult, L"ConsoleTracingMask", 0, &Type, Data, &cbData) || Type != 4 )
    {
      v10 = -65536;
      *(_DWORD *)Data = -65536;
    }
    else
    {
      v10 = *(_DWORD *)Data;
    }
    cbData = 4;
    *(_DWORD *)(a1 + 244) = v10 & 0xFFFF0000;
    if ( RegQueryValueExW(phkResult, L"MaxFileSize", 0, &Type, Data, &cbData) || Type != 4 )
    {
      v11 = 0x100000;
      *(_DWORD *)Data = 0x100000;
    }
    else
    {
      v11 = *(_DWORD *)Data;
    }
    *(_DWORD *)(a1 + 248) = v11;
    v29 = 0;
    cbData = 520;
    if ( !RegQueryValueExW(phkResult, L"FileDirectory", 0, &Type, v28, &cbData) && (Type == 2 || Type == 1) )
    {
      if ( (cbData & 0xFFFFFFFE) >= 0x20A )
        __report_rangecheckfailure();
      *(_WORD *)&v28[cbData & 0xFFFFFFFE] = 0;
    }
    else
    {
      result = StringCchCopyW((STRSAFE_LPWSTR)L"%windir%\\tracing", a2, v20);
      if ( result < 0 )
        return (unsigned __int16)result;
      StringCchLengthW(psz, v16, v21);
      cbData = 2 * *(_DWORD *)psz + 2;
    }
    if ( ExpandEnvironmentStringsW((LPCWSTR)v28, (LPWSTR)(a1 + 514), 0x104u)
      && ((v12 = lstrlenW((LPCWSTR)(a1 + 514)),
           _wcstombs((char *)(a1 + 252), (const wchar_t *)(a1 + 514), v12 + 1),
           (EventW = *(HANDLE *)(a1 + 1040)) != 0)
       || (EventW = CreateEventW(0, 0, 0, 0), (*(_DWORD *)(a1 + 1040) = EventW) != 0)) )
    {
      return RegNotifyChangeKeyValue(*(HKEY *)(a1 + 1036), 0, 0xEu, EventW, 1);
    }
    else
    {
      return GetLastError();
    }
  }
}

```

## disassembly

```asm
0x100032d0  mov     edi, edi
0x100032d2  push    ebp
0x100032d3  mov     ebp, esp
0x100032d5  sub     esp, 42Ch
0x100032db  mov     eax, ___security_cookie
0x100032e0  xor     eax, ebp
0x100032e2  mov     [ebp+var_4], eax
0x100032e5  push    esi; pcchLength
0x100032e6  mov     esi, ecx
0x100032e8  mov     [ebp+phkResult], 0
0x100032f2  push    offset aSoftwareMicros; "Software\\Microsoft\\Tracing"
0x100032f7  mov     edx, 104h
0x100032fc  mov     dword ptr [ebp+psz], 0
0x10003306  lea     ecx, [ebp+SubKey]
0x1000330c  call    _StringCchCopyW@12; StringCchCopyW(x,x,x)
0x10003311  test    eax, eax
0x10003313  js      loc_10003613
0x10003319  push    offset asc_10001298; "\\"
0x1000331e  mov     edx, 104h
0x10003323  lea     ecx, [ebp+SubKey]
0x10003329  call    _StringCchCatW@12; StringCchCatW(x,x,x)
0x1000332e  test    eax, eax
0x10003330  js      loc_10003613
0x10003336  lea     eax, [esi+68h]
0x10003339  mov     edx, 104h
0x1000333e  push    eax; pszDest
0x1000333f  lea     ecx, [ebp+SubKey]
0x10003345  call    _StringCchCatW@12; StringCchCatW(x,x,x)
0x1000334a  test    eax, eax
0x1000334c  js      loc_10003613
0x10003352  push    edi; cchMax
0x10003353  lea     eax, [ebp+phkResult]
0x10003359  push    eax; phkResult
0x1000335a  push    20019h; samDesired
0x1000335f  push    0; ulOptions
0x10003361  lea     eax, [ebp+SubKey]
0x10003367  push    eax; lpSubKey
0x10003368  push    80000002h; hKey
0x1000336d  call    ds:__imp__RegOpenKeyExW@20; RegOpenKeyExW(x,x,x,x,x)
0x10003373  test    eax, eax
0x10003375  jnz     loc_10005B7C
0x1000337b  mov     eax, [ebp+phkResult]
0x10003381  lea     ecx, [ebp+cbData]
0x10003387  push    ecx; lpcbData
0x10003388  lea     ecx, [ebp+Data]
0x1000338e  mov     [esi+40Ch], eax
0x10003394  push    ecx; lpData
0x10003395  lea     ecx, [ebp+Type]
0x1000339b  mov     [ebp+cbData], 4
0x100033a5  push    ecx; lpType
0x100033a6  push    0; lpReserved
0x100033a8  push    offset aEnablefiletrac; "EnableFileTracing"
0x100033ad  push    eax; hKey
0x100033ae  call    ds:__imp__RegQueryValueExW@24; RegQueryValueExW(x,x,x,x,x,x)
0x100033b4  test    eax, eax
0x100033b6  jz      loc_10005BB9
0x100033bc  xor     edx, edx
0x100033be  mov     dword ptr [ebp+Data], edx
0x100033c4  mov     ecx, [esi+20h]
0x100033c7  mov     eax, ecx
0x100033c9  or      eax, 2
0x100033cc  and     ecx, 0FFFFFFFDh
0x100033cf  cmp     edx, 1
0x100033d2  cmovz   ecx, eax
0x100033d5  lea     eax, [ebp+cbData]
0x100033db  push    eax; lpcbData
0x100033dc  lea     eax, [ebp+Data]
0x100033e2  mov     [esi+20h], ecx
0x100033e5  push    eax; lpData
0x100033e6  lea     eax, [ebp+Type]
0x100033ec  mov     [ebp+cbData], 4
0x100033f6  push    eax; lpType
0x100033f7  push    0; lpReserved
0x100033f9  push    offset aFiletracingmas; "FileTracingMask"
0x100033fe  push    [ebp+phkResult]; hKey
0x10003404  call    ds:__imp__RegQueryValueExW@24; RegQueryValueExW(x,x,x,x,x,x)
0x1000340a  test    eax, eax
0x1000340c  jz      loc_10005BD1
0x10003412  mov     eax, 0FFFF0000h
0x10003417  mov     dword ptr [ebp+Data], eax
0x1000341d  and     eax, 0FFFF0000h
0x10003422  mov     [ebp+cbData], 4
0x1000342c  mov     [esi+0F0h], eax
0x10003432  lea     eax, [ebp+cbData]
0x10003438  push    eax; lpcbData
0x10003439  lea     eax, [ebp+Data]
0x1000343f  push    eax; lpData
0x10003440  lea     eax, [ebp+Type]
0x10003446  push    eax; lpType
0x10003447  push    0; lpReserved
0x10003449  push    offset aEnableconsolet; "EnableConsoleTracing"
0x1000344e  push    [ebp+phkResult]; hKey
0x10003454  call    ds:__imp__RegQueryValueExW@24; RegQueryValueExW(x,x,x,x,x,x)
0x1000345a  test    eax, eax
0x1000345c  jz      loc_10005BE9
0x10003462  xor     edx, edx
0x10003464  mov     dword ptr [ebp+Data], edx
0x1000346a  mov     ecx, [esi+20h]
0x1000346d  mov     eax, ecx
0x1000346f  or      eax, 4
0x10003472  and     ecx, 0FFFFFFFBh
0x10003475  cmp     edx, 1
0x10003478  cmovz   ecx, eax
0x1000347b  lea     eax, [ebp+cbData]
0x10003481  push    eax; lpcbData
0x10003482  lea     eax, [ebp+Data]
0x10003488  mov     [esi+20h], ecx
0x1000348b  push    eax; lpData
0x1000348c  lea     eax, [ebp+Type]
0x10003492  mov     [ebp+cbData], 4
0x1000349c  push    eax; lpType
0x1000349d  push    0; lpReserved
0x1000349f  push    offset aConsoletracing_0; "ConsoleTracingMask"
0x100034a4  push    [ebp+phkResult]; hKey
0x100034aa  call    ds:__imp__RegQueryValueExW@24; RegQueryValueExW(x,x,x,x,x,x)
0x100034b0  test    eax, eax
0x100034b2  jz      loc_10005C01
0x100034b8  mov     eax, 0FFFF0000h
0x100034bd  mov     dword ptr [ebp+Data], eax
0x100034c3  and     eax, 0FFFF0000h
0x100034c8  mov     [ebp+cbData], 4
0x100034d2  mov     [esi+0F4h], eax
0x100034d8  lea     eax, [ebp+cbData]
0x100034de  push    eax; lpcbData
0x100034df  lea     eax, [ebp+Data]
0x100034e5  push    eax; lpData
0x100034e6  lea     eax, [ebp+Type]
0x100034ec  push    eax; lpType
0x100034ed  push    0; lpReserved
0x100034ef  push    offset aMaxfilesize_0; "MaxFileSize"
0x100034f4  push    [ebp+phkResult]; hKey
0x100034fa  call    ds:__imp__RegQueryValueExW@24; RegQueryValueExW(x,x,x,x,x,x)
0x10003500  test    eax, eax
0x10003502  jz      loc_10005C19
0x10003508  mov     eax, 100000h
0x1000350d  mov     dword ptr [ebp+Data], eax
0x10003513  mov     [esi+0F8h], eax
0x10003519  xor     eax, eax
0x1000351b  mov     [ebp+var_8], ax
0x1000351f  lea     eax, [ebp+cbData]
0x10003525  push    eax; lpcbData
0x10003526  lea     eax, [ebp+var_210]
0x1000352c  mov     [ebp+cbData], 208h
0x10003536  push    eax; lpData
0x10003537  lea     eax, [ebp+Type]
0x1000353d  push    eax; lpType
0x1000353e  push    0; lpReserved
0x10003540  push    offset aFiledirectory; "FileDirectory"
0x10003545  push    [ebp+phkResult]; hKey
0x1000354b  call    ds:__imp__RegQueryValueExW@24; RegQueryValueExW(x,x,x,x,x,x)
0x10003551  test    eax, eax
0x10003553  jz      loc_10005C31
0x10003559  push    offset aWindirTracing; "%windir%\\tracing"
0x1000355e  mov     edx, 104h
0x10003563  lea     ecx, [ebp+var_210]
0x10003569  call    _StringCchCopyW@12; StringCchCopyW(x,x,x)
0x1000356e  test    eax, eax
0x10003570  js      loc_10003618
0x10003576  lea     eax, [ebp+psz]
0x1000357c  push    eax; psz
0x1000357d  lea     ecx, [ebp+var_210]
0x10003583  call    _StringCchLengthW@12; StringCchLengthW(x,x,x)
0x10003588  mov     eax, dword ptr [ebp+psz]
0x1000358e  lea     eax, ds:2[eax*2]
0x10003595  mov     [ebp+cbData], eax
0x1000359b  push    104h; nSize
0x100035a0  lea     edi, [esi+202h]
0x100035a6  push    edi; lpDst
0x100035a7  lea     eax, [ebp+var_210]
0x100035ad  push    eax; lpSrc
0x100035ae  call    ds:__imp__ExpandEnvironmentStringsW@12; ExpandEnvironmentStringsW(x,x,x)
0x100035b4  test    eax, eax
0x100035b6  jz      short loc_1000361D
0x100035b8  push    edi; lpString
0x100035b9  call    ds:__imp__lstrlenW@4; lstrlenW(x)
0x100035bf  inc     eax
0x100035c0  push    eax; MaxCount
0x100035c1  lea     eax, [esi+0FCh]
0x100035c7  push    edi; Source
0x100035c8  push    eax; Dest
0x100035c9  call    ds:__imp__wcstombs
0x100035cf  mov     eax, [esi+410h]
0x100035d5  add     esp, 0Ch
0x100035d8  test    eax, eax
0x100035da  jnz     short loc_100035F0
0x100035dc  push    eax; lpName
0x100035dd  push    eax; bInitialState
0x100035de  push    eax; bManualReset
0x100035df  push    eax; lpEventAttributes
0x100035e0  call    ds:__imp__CreateEventW@16; CreateEventW(x,x,x,x)
0x100035e6  mov     [esi+410h], eax
0x100035ec  test    eax, eax
0x100035ee  jz      short loc_1000361D
0x100035f0  push    1; fAsynchronous
0x100035f2  push    eax; hEvent
0x100035f3  push    0Eh; dwNotifyFilter
0x100035f5  push    0; bWatchSubtree
0x100035f7  push    dword ptr [esi+40Ch]; hKey
0x100035fd  call    ds:__imp__RegNotifyChangeKeyValue@20; RegNotifyChangeKeyValue(x,x,x,x,x)
0x10003603  pop     edi
0x10003604  mov     ecx, [ebp+var_4]
0x10003607  xor     ecx, ebp; StackCookie
0x10003609  pop     esi
0x1000360a  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1000360f  mov     esp, ebp
0x10003611  pop     ebp
0x10003612  retn
0x10003613  movzx   eax, ax
0x10003616  jmp     short loc_10003604
0x10003618  movzx   eax, ax
0x1000361b  jmp     short loc_10003603
0x1000361d  call    ds:__imp__GetLastError@0; GetLastError()
0x10003623  jmp     short loc_10003603
0x10005b7c  lea     edx, [ebp+phkResult]; phkResult
0x10005b82  lea     ecx, [ebp+SubKey]; lpSubKey
0x10005b88  call    _TraceRegCreateDefaultsW@8; TraceRegCreateDefaultsW(x,x)
0x10005b8d  mov     edi, eax
0x10005b8f  test    edi, edi
0x10005b91  jz      loc_1000337B
0x10005b97  mov     ecx, [ebp+phkResult]
0x10005b9d  test    ecx, ecx
0x10005b9f  jz      short loc_10005BA8
0x10005ba1  push    ecx; hKey
0x10005ba2  call    ds:__imp__RegCloseKey@4; RegCloseKey(x)
0x10005ba8  mov     dword ptr [esi+40Ch], 0
0x10005bb2  mov     eax, edi
0x10005bb4  jmp     loc_10003603
0x10005bb9  cmp     [ebp+Type], 4
0x10005bc0  jnz     loc_100033BC
0x10005bc6  mov     edx, dword ptr [ebp+Data]
0x10005bcc  jmp     loc_100033C4
0x10005bd1  cmp     [ebp+Type], 4
0x10005bd8  jnz     loc_10003412
0x10005bde  mov     eax, dword ptr [ebp+Data]
0x10005be4  jmp     loc_1000341D
0x10005be9  cmp     [ebp+Type], 4
0x10005bf0  jnz     loc_10003462
0x10005bf6  mov     edx, dword ptr [ebp+Data]
0x10005bfc  jmp     loc_1000346A
0x10005c01  cmp     [ebp+Type], 4
0x10005c08  jnz     loc_100034B8
0x10005c0e  mov     eax, dword ptr [ebp+Data]
0x10005c14  jmp     loc_100034C3
0x10005c19  cmp     [ebp+Type], 4
0x10005c20  jnz     loc_10003508
0x10005c26  mov     eax, dword ptr [ebp+Data]
0x10005c2c  jmp     loc_10003513
0x10005c31  mov     eax, [ebp+Type]
0x10005c37  cmp     eax, 2
0x10005c3a  jz      short loc_10005C45
0x10005c3c  cmp     eax, 1
0x10005c3f  jnz     loc_10003559
0x10005c45  mov     eax, [ebp+cbData]
0x10005c4b  and     eax, 0FFFFFFFEh
0x10005c4e  cmp     eax, 20Ah
0x10005c53  jnb     short loc_10005C64
0x10005c55  xor     ecx, ecx
0x10005c57  mov     word ptr [ebp+eax+var_210], cx
0x10005c5f  jmp     loc_1000359B
0x10005c64  call    ___report_rangecheckfailure
```
