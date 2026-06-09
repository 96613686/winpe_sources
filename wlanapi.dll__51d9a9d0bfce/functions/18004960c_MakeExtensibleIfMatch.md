# MakeExtensibleIfMatch

- ea: `0x18004960c`
- end: `0x180049b5c`
- name: `MakeExtensibleIfMatch`
- size: `1360`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18004a660`

## callees

- `0x1800063a0`
- `0x180019a20`
- `0x180028140`
- `0x180042eac`
- `0x18004960c`
- `0x180049cb0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180049687`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180049687`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800498ea`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180049952`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800499cb`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180049a41`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180049aa7`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800498ea`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180049952`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800499cb`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180049a41`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180049aa7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180049b20`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180049b2d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180049b20`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180049b2d`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18004981f`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18004981f`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x18004999a`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x180049a10`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x18004999a`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x180049a10`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180049786`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180049786`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180049b02`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180049b11`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180049b02`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180049b11`
- `DEVOBJ!DevObjOpenDevRegKey` at `0x180049675`
- `DEVOBJ!DevObjOpenDevRegKey` at `0x180049675`

## string_xrefs

- `0x1800497f9`: `Ndi\IHVExtensions`
- `0x1800498d8`: `ExtensibilityDLL`
- `0x1800499b1`: `UIExtensibilityCLSID`
- `0x180049a27`: `DiagnosticsID`
- `0x18004986d`: `%windir%\system32\someihv.dll`

## pseudocode

```c
__int64 __fastcall MakeExtensibleIfMatch(__int64 a1, __int64 a2, _QWORD *a3, __int64 a4, _DWORD *a5)
{
  int v7; // esi
  __int64 v8; // r14
  DWORD LastError; // ebx
  int v10; // r13d
  DWORD RegistryString; // eax
  unsigned int v12; // eax
  __int64 v13; // rax
  HKEY v14; // r12
  unsigned int v15; // eax
  unsigned int v16; // eax
  union DOT11_OUI_HEADER *v17; // rcx
  __int64 v18; // rdx
  __int64 v19; // rax
  const BYTE *v20; // rcx
  char v21; // al
  HKEY v22; // rcx
  HKEY hKey; // [rsp+58h] [rbp-79h]
  HKEY phkResult; // [rsp+60h] [rbp-71h] BYREF
  LPOLESTR lpsz; // [rsp+68h] [rbp-69h] BYREF
  LPOLESTR v27; // [rsp+70h] [rbp-61h] BYREF
  GUID pclsid; // [rsp+78h] [rbp-59h] BYREF
  OLECHAR sz[40]; // [rsp+90h] [rbp-41h] BYREF

  lpsz = 0;
  v7 = 1;
  v27 = 0;
  v8 = -1;
  phkResult = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
  pclsid = 0;
  hKey = (HKEY)DevObjOpenDevRegKey(a1, a2, 1, 0, 2, 131097);
  if ( hKey == HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL )
  {
    LastError = GetLastError();
    if ( LastError )
    {
      v7 = 0;
      if ( WPP_GLOBAL_Control != (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25)
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 36, &WPP_52d70405f63e3f10ed920fefc30aa7c8_Traceguids, LastError);
        v10 = 0;
      }
      else
      {
        v10 = 0;
      }
      goto LABEL_74;
    }
  }
  RegistryString = ReadRegistryString(hKey, L"NetCfgInstanceId", 0x4Eu, sz);
  LastError = RegistryString;
  if ( RegistryString )
  {
    if ( WPP_GLOBAL_Control != (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25)
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        37,
        &WPP_52d70405f63e3f10ed920fefc30aa7c8_Traceguids,
        RegistryString);
    }
LABEL_12:
    v10 = 0;
LABEL_74:
    v14 = hKey;
    goto LABEL_75;
  }
  if ( WPP_GLOBAL_Control != (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 38, &WPP_52d70405f63e3f10ed920fefc30aa7c8_Traceguids, sz);
  }
  v12 = CLSIDFromString(sz, &pclsid);
  LastError = v12;
  if ( v12 )
  {
    if ( WPP_GLOBAL_Control != (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25)
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 39, &WPP_52d70405f63e3f10ed920fefc30aa7c8_Traceguids, v12);
    }
    v7 = 1;
    goto LABEL_12;
  }
  v13 = *(_QWORD *)&pclsid.Data1 - *a3;
  if ( *(_QWORD *)&pclsid.Data1 == *a3 )
    v13 = *(_QWORD *)pclsid.Data4 - a3[1];
  if ( v13 )
  {
    v7 = 1;
    v10 = 0;
    *a5 = 0;
    goto LABEL_74;
  }
  v10 = 1;
  *a5 = 1;
  v14 = hKey;
  v15 = RegCreateKeyExW(hKey, L"Ndi\\IHVExtensions", 0, 0, 0, 0xF003Fu, 0, &phkResult, 0);
  LastError = v15;
  if ( !v15 )
  {
    if ( *(_WORD *)(a4 + 8)
      || (v16 = StringCchPrintfW((STRSAFE_LPWSTR)(a4 + 8), 0x104u, L"%s", L"%windir%\\system32\\someihv.dll")) == 0 )
    {
      v19 = -1;
      do
        ++v19;
      while ( *(_WORD *)(a4 + 8 + 2 * v19) );
      v16 = RegSetValueExW(phkResult, L"ExtensibilityDLL", 0, 1u, (const BYTE *)(a4 + 8), 2 * v19 + 2);
      LastError = v16;
      if ( v16 )
      {
        v17 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control
          || !*((_BYTE *)WPP_GLOBAL_Control + 25)
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        {
          goto LABEL_38;
        }
        v18 = 42;
      }
      else
      {
        v20 = (const BYTE *)(a4 + 528);
        if ( !*(_WORD *)(a4 + 528) )
          goto LABEL_86;
        do
          ++v8;
        while ( *(_WORD *)&v20[2 * v8] );
        v16 = RegSetValueExW(phkResult, L"GroupName", 0, 1u, v20, 2 * v8 + 2);
        LastError = v16;
        if ( v16 )
        {
          v17 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control
            || !*((_BYTE *)WPP_GLOBAL_Control + 25)
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          {
            goto LABEL_38;
          }
          v18 = 43;
        }
        else
        {
LABEL_86:
          if ( !StringFromCLSID((const IID *const)(a4 + 1048), &lpsz)
            && lpsz
            && (v16 = RegSetValueExW(phkResult, L"UIExtensibilityCLSID", 0, 1u, (const BYTE *)lpsz, 0x4Eu),
                (LastError = v16) != 0) )
          {
            v17 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control
              || !*((_BYTE *)WPP_GLOBAL_Control + 25)
              || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
            {
              goto LABEL_38;
            }
            v18 = 44;
          }
          else if ( !StringFromCLSID((const IID *const)(a4 + 1064), &v27)
                 && v27
                 && (v16 = RegSetValueExW(phkResult, L"DiagnosticsID", 0, 1u, (const BYTE *)v27, 0x4Eu),
                     (LastError = v16) != 0) )
          {
            v17 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control
              || !*((_BYTE *)WPP_GLOBAL_Control + 25)
              || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
            {
              goto LABEL_38;
            }
            v18 = 45;
          }
          else
          {
            v21 = *(_BYTE *)(a4 + 6);
            *(_BYTE *)(a4 + 6) = *(_BYTE *)(a4 + 4);
            v22 = phkResult;
            *(_BYTE *)(a4 + 4) = v21;
            v16 = RegSetValueExW(v22, L"AdapterOUI", 0, 4u, (const BYTE *)(a4 + 4), 4u);
            LastError = v16;
            if ( !v16 )
              goto LABEL_38;
            v17 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control
              || !*((_BYTE *)WPP_GLOBAL_Control + 25)
              || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
            {
              goto LABEL_38;
            }
            v18 = 46;
          }
        }
      }
    }
    else
    {
      LastError = 87;
      v17 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      {
        goto LABEL_38;
      }
      v18 = 41;
    }
    WPP_SF_d(*((_QWORD *)v17 + 2), v18, &WPP_52d70405f63e3f10ed920fefc30aa7c8_Traceguids, v16);
LABEL_38:
    v7 = 1;
    goto LABEL_75;
  }
  if ( WPP_GLOBAL_Control != (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25)
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 40, &WPP_52d70405f63e3f10ed920fefc30aa7c8_Traceguids, v15);
  }
  v7 = 1;
  v10 = 0;
LABEL_75:
  if ( lpsz )
    CoTaskMemFree(lpsz);
  if ( v27 )
    CoTaskMemFree(v27);
  if ( v10 )
    RegCloseKey(phkResult);
  if ( v7 )
    RegCloseKey(v14);
  return LastError;
}

```

## disassembly

```asm
0x18004960c  mov     [rsp-8+arg_10], rbx
0x180049611  push    rbp
0x180049612  push    rsi
0x180049613  push    rdi
0x180049614  push    r12
0x180049616  push    r13
0x180049618  push    r14
0x18004961a  push    r15
0x18004961c  lea     rbp, [rsp-1Fh]
0x180049621  sub     rsp, 0F0h
0x180049628  mov     rax, cs:__security_cookie
0x18004962f  xor     rax, rsp
0x180049632  mov     [rbp+4Fh+var_40], rax
0x180049636  mov     r12, [rbp+4Fh+arg_20]
0x18004963a  xor     eax, eax
0x18004963c  mov     r15, r9
0x18004963f  mov     [rsp+120h+samDesired], 20019h
0x180049647  mov     r13, r8
0x18004964a  mov     [rbp+4Fh+var_CC], eax
0x18004964d  xorps   xmm0, xmm0
0x180049650  mov     [rbp+4Fh+lpsz], rax
0x180049654  lea     esi, [rax+1]
0x180049657  mov     [rbp+4Fh+var_B0], rax
0x18004965b  or      r14, 0FFFFFFFFFFFFFFFFh
0x18004965f  mov     [rsp+120h+dwOptions], 2
0x180049667  mov     r8d, esi
0x18004966a  mov     [rbp+4Fh+var_C0], r14
0x18004966e  xor     r9d, r9d
0x180049671  movups  xmmword ptr [rbp+4Fh+pclsid.Data1], xmm0
0x180049675  call    cs:__imp_DevObjOpenDevRegKey
0x18004967b  mov     [rbp+4Fh+hKey], rax
0x18004967f  mov     rdi, rax
0x180049682  cmp     rax, r14
0x180049685  jnz     short loc_1800496E0
0x180049687  call    cs:__imp_GetLastError
0x18004968d  mov     ebx, eax
0x18004968f  xor     eax, eax
0x180049691  test    ebx, ebx
0x180049693  jz      short loc_1800496E0
0x180049695  mov     esi, eax
0x180049697  mov     rcx, cs:WPP_GLOBAL_Control
0x18004969e  lea     rdi, WPP_GLOBAL_Control
0x1800496a5  cmp     rcx, rdi
0x1800496a8  jz      loc_180049AF2
0x1800496ae  cmp     byte ptr [rcx+19h], 1
0x1800496b2  jb      loc_180049AF2
0x1800496b8  test    byte ptr [rcx+1Ch], 1
0x1800496bc  jz      loc_180049AF2
0x1800496c2  mov     rcx, [rcx+10h]
0x1800496c6  lea     edx, [rax+24h]
0x1800496c9  mov     r9d, ebx
0x1800496cc  lea     r8, WPP_52d70405f63e3f10ed920fefc30aa7c8_Traceguids
0x1800496d3  call    WPP_SF_d
0x1800496d8  mov     r13d, esi
0x1800496db  jmp     loc_180049AF5
0x1800496e0  lea     r9, [rbp+4Fh+sz]; lpDst
0x1800496e4  mov     [rsp+120h+var_D0], esi
0x1800496e8  mov     r8d, 4Eh ; 'N'; dwBytes
0x1800496ee  lea     rdx, aNetcfginstance; "NetCfgInstanceId"
0x1800496f5  mov     rcx, rdi; hKey
0x1800496f8  call    ReadRegistryString
0x1800496fd  mov     ebx, eax
0x1800496ff  test    eax, eax
0x180049701  jz      short loc_180049743
0x180049703  mov     rcx, cs:WPP_GLOBAL_Control
0x18004970a  lea     rdi, WPP_GLOBAL_Control
0x180049711  cmp     rcx, rdi
0x180049714  jz      short loc_18004973A
0x180049716  cmp     [rcx+19h], sil
0x18004971a  jb      short loc_18004973A
0x18004971c  test    [rcx+1Ch], sil
0x180049720  jz      short loc_18004973A
0x180049722  mov     rcx, [rcx+10h]
0x180049726  lea     r8, WPP_52d70405f63e3f10ed920fefc30aa7c8_Traceguids
0x18004972d  mov     edx, 25h ; '%'
0x180049732  mov     r9d, eax
0x180049735  call    WPP_SF_d
0x18004973a  mov     r13d, [rbp+4Fh+var_CC]
0x18004973e  jmp     loc_180049AF5
0x180049743  mov     rcx, cs:WPP_GLOBAL_Control
0x18004974a  lea     rdi, WPP_GLOBAL_Control
0x180049751  lea     rsi, WPP_52d70405f63e3f10ed920fefc30aa7c8_Traceguids
0x180049758  cmp     rcx, rdi
0x18004975b  jz      short loc_18004977E
0x18004975d  cmp     byte ptr [rcx+19h], 4
0x180049761  jb      short loc_18004977E
0x180049763  test    byte ptr [rcx+1Ch], 1
0x180049767  jz      short loc_18004977E
0x180049769  mov     rcx, [rcx+10h]
0x18004976d  lea     r9, [rbp+4Fh+sz]
0x180049771  mov     edx, 26h ; '&'
0x180049776  mov     r8, rsi
0x180049779  call    WPP_SF_S
0x18004977e  lea     rdx, [rbp+4Fh+pclsid]; pclsid
0x180049782  lea     rcx, [rbp+4Fh+sz]; lpsz
0x180049786  call    cs:__imp_CLSIDFromString
0x18004978c  xor     ecx, ecx
0x18004978e  mov     ebx, eax
0x180049790  test    eax, eax
0x180049792  jz      short loc_1800497C9
0x180049794  mov     rcx, cs:WPP_GLOBAL_Control
0x18004979b  cmp     rcx, rdi
0x18004979e  jz      short loc_1800497C0
0x1800497a0  cmp     byte ptr [rcx+19h], 1
0x1800497a4  jb      short loc_1800497C0
0x1800497a6  test    byte ptr [rcx+1Ch], 1
0x1800497aa  jz      short loc_1800497C0
0x1800497ac  mov     rcx, [rcx+10h]
0x1800497b0  mov     edx, 27h ; '''
0x1800497b5  mov     r9d, eax
0x1800497b8  mov     r8, rsi
0x1800497bb  call    WPP_SF_d
0x1800497c0  mov     esi, [rsp+120h+var_D0]
0x1800497c4  jmp     loc_18004973A
0x1800497c9  mov     rax, qword ptr [rbp+4Fh+pclsid.Data1]
0x1800497cd  sub     rax, [r13+0]
0x1800497d1  jnz     short loc_1800497DB
0x1800497d3  mov     rax, qword ptr [rbp+4Fh+pclsid.Data4]
0x1800497d7  sub     rax, [r13+8]
0x1800497db  test    rax, rax
0x1800497de  jnz     loc_180049AE5
0x1800497e4  mov     [rsp+120h+lpdwDisposition], rcx; lpdwDisposition
0x1800497e9  lea     r13d, [rax+1]
0x1800497ed  lea     rax, [rbp+4Fh+var_C0]
0x1800497f1  mov     [r12], r13d
0x1800497f5  mov     r12, [rbp+4Fh+hKey]
0x1800497f9  lea     rdx, SubKey; "Ndi\\IHVExtensions"
0x180049800  mov     [rsp+120h+phkResult], rax; phkResult
0x180049805  xor     r9d, r9d; lpClass
0x180049808  mov     [rsp+120h+lpSecurityAttributes], rcx; lpSecurityAttributes
0x18004980d  xor     r8d, r8d; Reserved
0x180049810  mov     [rsp+120h+samDesired], 0F003Fh; samDesired
0x180049818  mov     [rsp+120h+dwOptions], ecx; dwOptions
0x18004981c  mov     rcx, r12; hKey
0x18004981f  call    cs:__imp_RegCreateKeyExW
0x180049825  xor     ecx, ecx
0x180049827  mov     ebx, eax
0x180049829  test    eax, eax
0x18004982b  jz      short loc_180049864
0x18004982d  mov     rcx, cs:WPP_GLOBAL_Control
0x180049834  cmp     rcx, rdi
0x180049837  jz      short loc_180049858
0x180049839  cmp     [rcx+19h], r13b
0x18004983d  jb      short loc_180049858
0x18004983f  test    [rcx+1Ch], r13b
0x180049843  jz      short loc_180049858
0x180049845  mov     rcx, [rcx+10h]
0x180049849  lea     edx, [r13+27h]
0x18004984d  mov     r9d, eax
0x180049850  mov     r8, rsi
0x180049853  call    WPP_SF_d
0x180049858  mov     esi, r13d
0x18004985b  mov     r13d, [rbp+4Fh+var_CC]
0x18004985f  jmp     loc_180049AF9
0x180049864  lea     rbx, [r15+8]
0x180049868  cmp     [rbx], cx
0x18004986b  jnz     short loc_1800498BD
0x18004986d  lea     r9, aWindirSystem32; "%windir%\\system32\\someihv.dll"
0x180049874  mov     edx, 104h; cchDest
0x180049879  lea     r8, aS_0; "%s"
0x180049880  mov     rcx, rbx; pszDest
0x180049883  call    StringCchPrintfW
0x180049888  xor     ecx, ecx
0x18004988a  test    eax, eax
0x18004988c  jz      short loc_1800498BD
0x18004988e  lea     ebx, [rcx+57h]
0x180049891  mov     rcx, cs:WPP_GLOBAL_Control
0x180049898  cmp     rcx, rdi
0x18004989b  jz      short loc_1800498B5
0x18004989d  test    [rcx+1Ch], r13b
0x1800498a1  jz      short loc_1800498B5
0x1800498a3  lea     edx, [rbx-2Eh]
0x1800498a6  mov     rcx, [rcx+10h]
0x1800498aa  mov     r9d, eax
0x1800498ad  mov     r8, rsi
0x1800498b0  call    WPP_SF_d
0x1800498b5  mov     esi, r13d
0x1800498b8  jmp     loc_180049AF9
0x1800498bd  mov     rax, r14
0x1800498c0  inc     rax
0x1800498c3  cmp     [rbx+rax*2], cx
0x1800498c7  jnz     short loc_1800498C0
0x1800498c9  mov     rcx, [rbp+4Fh+var_C0]; hKey
0x1800498cd  lea     eax, ds:2[rax*2]
0x1800498d4  mov     [rsp+120h+samDesired], eax; cbData
0x1800498d8  lea     rdx, ValueName; "ExtensibilityDLL"
0x1800498df  mov     r9d, r13d; dwType
0x1800498e2  mov     qword ptr [rsp+120h+dwOptions], rbx; lpData
0x1800498e7  xor     r8d, r8d; Reserved
0x1800498ea  call    cs:__imp_RegSetValueExW
0x1800498f0  mov     ebx, eax
0x1800498f2  test    eax, eax
0x1800498f4  jz      short loc_180049915
0x1800498f6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800498fd  cmp     rcx, rdi
0x180049900  jz      short loc_1800498B5
0x180049902  cmp     [rcx+19h], r13b
0x180049906  jb      short loc_1800498B5
0x180049908  test    [rcx+1Ch], r13b
0x18004990c  jz      short loc_1800498B5
0x18004990e  mov     edx, 2Ah ; '*'
0x180049913  jmp     short loc_1800498A6
0x180049915  lea     rcx, [r15+210h]
0x18004991c  xor     ebx, ebx
0x18004991e  cmp     [rcx], bx
0x180049921  jz      short loc_18004998C
0x180049923  inc     r14
0x180049926  cmp     [rcx+r14*2], bx
0x18004992b  jnz     short loc_180049923
0x18004992d  lea     eax, ds:2[r14*2]
0x180049935  mov     r9d, r13d; dwType
0x180049938  mov     [rsp+120h+samDesired], eax; cbData
0x18004993c  lea     rdx, aGroupname; "GroupName"
0x180049943  mov     qword ptr [rsp+120h+dwOptions], rcx; lpData
0x180049948  xor     r8d, r8d; Reserved
0x18004994b  mov     rcx, [rbp+4Fh+var_C0]; hKey
0x18004994f  mov     r14d, r13d
0x180049952  call    cs:__imp_RegSetValueExW
0x180049958  mov     ebx, eax
0x18004995a  test    eax, eax
0x18004995c  jz      short loc_18004998F
0x18004995e  mov     rcx, cs:WPP_GLOBAL_Control
0x180049965  cmp     rcx, rdi
0x180049968  jz      loc_1800498B5
0x18004996e  cmp     [rcx+19h], r14b
0x180049972  jb      loc_1800498B5
0x180049978  test    [rcx+1Ch], r14b
0x18004997c  jz      loc_1800498B5
0x180049982  mov     edx, 2Bh ; '+'
0x180049987  jmp     loc_1800498A6
0x18004998c  mov     r14d, r13d
0x18004998f  lea     rcx, [r15+418h]; rclsid
0x180049996  lea     rdx, [rbp+4Fh+lpsz]; lplpsz
0x18004999a  call    cs:__imp_StringFromCLSID
0x1800499a0  test    eax, eax
0x1800499a2  jnz     short loc_180049A05
0x1800499a4  mov     rax, [rbp+4Fh+lpsz]
0x1800499a8  test    rax, rax
0x1800499ab  jz      short loc_180049A05
0x1800499ad  mov     rcx, [rbp+4Fh+var_C0]; hKey
0x1800499b1  lea     rdx, aUiextensibilit; "UIExtensibilityCLSID"
0x1800499b8  mov     [rsp+120h+samDesired], 4Eh ; 'N'; cbData
0x1800499c0  mov     r9d, r14d; dwType
0x1800499c3  xor     r8d, r8d; Reserved
0x1800499c6  mov     qword ptr [rsp+120h+dwOptions], rax; lpData
0x1800499cb  call    cs:__imp_RegSetValueExW
0x1800499d1  mov     ebx, eax
0x1800499d3  test    eax, eax
0x1800499d5  jz      short loc_180049A05
0x1800499d7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800499de  cmp     rcx, rdi
0x1800499e1  jz      loc_1800498B5
0x1800499e7  cmp     [rcx+19h], r14b
0x1800499eb  jb      loc_1800498B5
0x1800499f1  test    [rcx+1Ch], r14b
0x1800499f5  jz      loc_1800498B5
0x1800499fb  mov     edx, 2Ch ; ','
0x180049a00  jmp     loc_1800498A6
0x180049a05  lea     rcx, [r15+428h]; rclsid
0x180049a0c  lea     rdx, [rbp+4Fh+var_B0]; lplpsz
0x180049a10  call    cs:__imp_StringFromCLSID
0x180049a16  test    eax, eax
0x180049a18  jnz     short loc_180049A7B
0x180049a1a  mov     rax, [rbp+4Fh+var_B0]
0x180049a1e  test    rax, rax
0x180049a21  jz      short loc_180049A7B
0x180049a23  mov     rcx, [rbp+4Fh+var_C0]; hKey
0x180049a27  lea     rdx, aDiagnosticsid; "DiagnosticsID"
0x180049a2e  mov     [rsp+120h+samDesired], 4Eh ; 'N'; cbData
0x180049a36  mov     r9d, r14d; dwType
0x180049a39  xor     r8d, r8d; Reserved
0x180049a3c  mov     qword ptr [rsp+120h+dwOptions], rax; lpData
0x180049a41  call    cs:__imp_RegSetValueExW
0x180049a47  mov     ebx, eax
0x180049a49  test    eax, eax
0x180049a4b  jz      short loc_180049A7B
0x180049a4d  mov     rcx, cs:WPP_GLOBAL_Control
0x180049a54  cmp     rcx, rdi
0x180049a57  jz      loc_1800498B5
0x180049a5d  cmp     [rcx+19h], r14b
0x180049a61  jb      loc_1800498B5
0x180049a67  test    [rcx+1Ch], r14b
0x180049a6b  jz      loc_1800498B5
0x180049a71  mov     edx, 2Dh ; '-'
0x180049a76  jmp     loc_1800498A6
0x180049a7b  lea     rdx, [r15+4]
0x180049a7f  mov     r9d, 4; dwType
0x180049a85  mov     cl, [rdx]
0x180049a87  xor     r8d, r8d; Reserved
0x180049a8a  mov     al, [rdx+2]
0x180049a8d  mov     [rdx+2], cl
0x180049a90  mov     rcx, [rbp+4Fh+var_C0]; hKey
0x180049a94  mov     [rsp+120h+samDesired], r9d; cbData
0x180049a99  mov     [rdx], al
0x180049a9b  mov     qword ptr [rsp+120h+dwOptions], rdx; lpData
0x180049aa0  lea     rdx, aAdapteroui; "AdapterOUI"
0x180049aa7  call    cs:__imp_RegSetValueExW
0x180049aad  mov     ebx, eax
0x180049aaf  test    eax, eax
0x180049ab1  jz      loc_1800498B5
  ... truncated ...
```
