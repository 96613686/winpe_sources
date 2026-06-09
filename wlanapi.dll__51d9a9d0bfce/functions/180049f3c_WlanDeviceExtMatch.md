# WlanDeviceExtMatch

- ea: `0x180049f3c`
- end: `0x18004a316`
- name: `WlanDeviceExtMatch`
- size: `986`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18004a320`

## callees

- `0x1800063a0`
- `0x180006934`
- `0x180019a20`
- `0x180028140`
- `0x180049b64`
- `0x180049cb0`
- `0x180049f3c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180049fe5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180049fe5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004a112`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004a112`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004a23a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004a28c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004a23a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004a28c`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18004a085`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18004a1c5`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18004a21f`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18004a085`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18004a1c5`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18004a21f`
- `DEVOBJ!DevObjOpenDevRegKey` at `0x180049fd6`
- `DEVOBJ!DevObjOpenDevRegKey` at `0x180049fd6`

## string_xrefs

- `0x18004a108`: `Ndi\IHVExtensions`
- `0x18004a167`: `ExtensibilityDLL`
- `0x18004a1a8`: `UIExtensibilityCLSID`
- `0x18004a1f9`: `DiagnosticsID`

## pseudocode

```c
__int64 __fastcall WlanDeviceExtMatch(__int64 a1, __int64 a2, _QWORD *a3, __int64 a4, _DWORD *a5)
{
  HKEY v9; // rsi
  DWORD LastError; // eax
  unsigned int RegistryString; // ebx
  union DOT11_OUI_HEADER *v12; // rcx
  __int64 v13; // rdx
  __int64 v14; // rax
  unsigned int v15; // eax
  _BYTE *v16; // rbx
  __int64 v17; // rdi
  __int64 v18; // rax
  char v19; // al
  HKEY v20; // rcx
  _BYTE *v21; // rbx
  unsigned int v22; // eax
  HKEY hKey; // [rsp+30h] [rbp-61h] BYREF
  GUID pclsid; // [rsp+38h] [rbp-59h] BYREF
  OLECHAR sz[40]; // [rsp+50h] [rbp-41h] BYREF

  pclsid = 0;
  hKey = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
  if ( WPP_GLOBAL_Control != (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, &WPP_52d70405f63e3f10ed920fefc30aa7c8_Traceguids);
  }
  v9 = (HKEY)DevObjOpenDevRegKey(a1, a2, 1, 0, 2, 131097);
  if ( v9 != HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL
    || (LastError = GetLastError(), (RegistryString = LastError) == 0) )
  {
    RegistryString = ReadRegistryString(v9, L"NetCfgInstanceId", 0x4Eu, sz);
    if ( !RegistryString )
    {
      if ( WPP_GLOBAL_Control != (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, &WPP_52d70405f63e3f10ed920fefc30aa7c8_Traceguids, sz);
      }
      RegistryString = CLSIDFromString(sz, &pclsid);
      if ( RegistryString )
      {
        if ( WPP_GLOBAL_Control != (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control
          && *((_BYTE *)WPP_GLOBAL_Control + 25)
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            23,
            &WPP_52d70405f63e3f10ed920fefc30aa7c8_Traceguids,
            RegistryString);
        }
      }
      else
      {
        v14 = *(_QWORD *)&pclsid.Data1 - *a3;
        if ( *(_QWORD *)&pclsid.Data1 == *a3 )
          v14 = *(_QWORD *)pclsid.Data4 - a3[1];
        if ( v14 )
        {
          *a5 = 0;
        }
        else
        {
          *a5 = 1;
          v15 = RegOpenKeyExW(v9, L"Ndi\\IHVExtensions", 0, 0x20019u, &hKey);
          if ( v15 )
          {
            if ( WPP_GLOBAL_Control != (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, &WPP_52d70405f63e3f10ed920fefc30aa7c8_Traceguids, v15);
            }
            RegistryString = 0;
          }
          else
          {
            *(_DWORD *)a4 = ReadRegistryString(hKey, L"ExtensibilityDLL", 0x208u, (LPWSTR)(a4 + 8)) == 0;
            ReadRegistryString(hKey, L"GroupName", 0x208u, (LPWSTR)(a4 + 528));
            ReadRegistryString(hKey, L"UIExtensibilityCLSID", 0x4Eu, sz);
            v16 = (_BYTE *)(a4 + 1048);
            v17 = 16;
            if ( CLSIDFromString(sz, (LPCLSID)(a4 + 1048)) )
            {
              v18 = 16;
              do
              {
                *v16++ = 0;
                --v18;
              }
              while ( v18 );
            }
            ReadRegistryNumber(hKey);
            v19 = *(_BYTE *)(a4 + 6);
            *(_BYTE *)(a4 + 6) = *(_BYTE *)(a4 + 4);
            v20 = hKey;
            *(_BYTE *)(a4 + 4) = v19;
            ReadRegistryString(v20, L"DiagnosticsID", 0x4Eu, sz);
            v21 = (_BYTE *)(a4 + 1064);
            if ( CLSIDFromString(sz, (LPCLSID)(a4 + 1064)) )
            {
              do
              {
                *v21++ = 0;
                --v17;
              }
              while ( v17 );
            }
            RegistryString = 0;
            v22 = RegCloseKey(hKey);
            if ( v22
              && WPP_GLOBAL_Control != (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, &WPP_52d70405f63e3f10ed920fefc30aa7c8_Traceguids, v22);
            }
          }
        }
      }
    }
    LastError = RegCloseKey(v9);
    if ( !LastError )
      goto LABEL_47;
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control )
      return RegistryString;
    if ( *((_BYTE *)WPP_GLOBAL_Control + 25) < 3u || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_48;
    v13 = 26;
LABEL_46:
    WPP_SF_d(*((_QWORD *)v12 + 2), v13, &WPP_52d70405f63e3f10ed920fefc30aa7c8_Traceguids, LastError);
LABEL_47:
    v12 = WPP_GLOBAL_Control;
    goto LABEL_48;
  }
  v12 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control )
    return RegistryString;
  if ( *((_BYTE *)WPP_GLOBAL_Control + 25) && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v13 = 21;
    goto LABEL_46;
  }
LABEL_48:
  if ( v12 != (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control
    && *((_BYTE *)v12 + 25) >= 4u
    && (*((_BYTE *)v12 + 28) & 1) != 0 )
  {
    WPP_SF_d(*((_QWORD *)v12 + 2), 27, &WPP_52d70405f63e3f10ed920fefc30aa7c8_Traceguids, RegistryString);
  }
  return RegistryString;
}

```

## disassembly

```asm
0x180049f3c  push    rbp
0x180049f3e  push    rbx
0x180049f3f  push    rsi
0x180049f40  push    rdi
0x180049f41  push    r12
0x180049f43  push    r14
0x180049f45  push    r15
0x180049f47  lea     rbp, [rsp-1Fh]
0x180049f4c  sub     rsp, 0B0h
0x180049f53  mov     rax, cs:__security_cookie
0x180049f5a  xor     rax, rsp
0x180049f5d  mov     [rbp+4Fh+var_40], rax
0x180049f61  mov     r14, [rbp+4Fh+arg_20]
0x180049f65  xorps   xmm0, xmm0
0x180049f68  movups  xmmword ptr [rbp+4Fh+pclsid.Data1], xmm0
0x180049f6c  mov     r15, r9
0x180049f6f  mov     [rbp+4Fh+hKey], 0FFFFFFFFFFFFFFFFh
0x180049f77  mov     rdi, r8
0x180049f7a  mov     rsi, rdx
0x180049f7d  mov     rbx, rcx
0x180049f80  mov     rcx, cs:WPP_GLOBAL_Control
0x180049f87  lea     rax, WPP_GLOBAL_Control
0x180049f8e  mov     r12d, 1
0x180049f94  cmp     rcx, rax
0x180049f97  jz      short loc_180049FBA
0x180049f99  cmp     byte ptr [rcx+19h], 4
0x180049f9d  jb      short loc_180049FBA
0x180049f9f  test    [rcx+1Ch], r12b
0x180049fa3  jz      short loc_180049FBA
0x180049fa5  mov     rcx, [rcx+10h]
0x180049fa9  lea     edx, [r12+13h]
0x180049fae  lea     r8, WPP_52d70405f63e3f10ed920fefc30aa7c8_Traceguids
0x180049fb5  call    WPP_SF_
0x180049fba  mov     [rsp+0E0h+var_B8], 20019h
0x180049fc2  xor     r9d, r9d
0x180049fc5  mov     r8d, r12d
0x180049fc8  mov     dword ptr [rsp+0E0h+phkResult], 2
0x180049fd0  mov     rdx, rsi
0x180049fd3  mov     rcx, rbx
0x180049fd6  call    cs:__imp_DevObjOpenDevRegKey
0x180049fdc  mov     rsi, rax
0x180049fdf  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180049fe3  jnz     short loc_18004A024
0x180049fe5  call    cs:__imp_GetLastError
0x180049feb  mov     ebx, eax
0x180049fed  test    eax, eax
0x180049fef  jz      short loc_18004A024
0x180049ff1  mov     rcx, cs:WPP_GLOBAL_Control
0x180049ff8  lea     rdi, WPP_GLOBAL_Control
0x180049fff  cmp     rcx, rdi
0x18004a002  jz      loc_18004A2F6
0x18004a008  cmp     [rcx+19h], r12b
0x18004a00c  jb      loc_18004A2CD
0x18004a012  test    [rcx+1Ch], r12b
0x18004a016  jz      loc_18004A2CD
0x18004a01c  lea     edx, [rsi+16h]
0x18004a01f  jmp     loc_18004A2B3
0x18004a024  lea     r9, [rbp+4Fh+sz]; lpDst
0x18004a028  mov     r8d, 4Eh ; 'N'; dwBytes
0x18004a02e  lea     rdx, aNetcfginstance; "NetCfgInstanceId"
0x18004a035  mov     rcx, rsi; hKey
0x18004a038  call    ReadRegistryString
0x18004a03d  mov     ebx, eax
0x18004a03f  test    eax, eax
0x18004a041  jnz     loc_18004A282
0x18004a047  mov     rcx, cs:WPP_GLOBAL_Control
0x18004a04e  lea     rax, WPP_GLOBAL_Control
0x18004a055  cmp     rcx, rax
0x18004a058  jz      short loc_18004A07D
0x18004a05a  cmp     byte ptr [rcx+19h], 4
0x18004a05e  jb      short loc_18004A07D
0x18004a060  test    [rcx+1Ch], r12b
0x18004a064  jz      short loc_18004A07D
0x18004a066  mov     rcx, [rcx+10h]
0x18004a06a  lea     edx, [rbx+16h]
0x18004a06d  lea     r9, [rbp+4Fh+sz]
0x18004a071  lea     r8, WPP_52d70405f63e3f10ed920fefc30aa7c8_Traceguids
0x18004a078  call    WPP_SF_S
0x18004a07d  lea     rdx, [rbp+4Fh+pclsid]; pclsid
0x18004a081  lea     rcx, [rbp+4Fh+sz]; lpsz
0x18004a085  call    cs:__imp_CLSIDFromString
0x18004a08b  mov     ebx, eax
0x18004a08d  test    eax, eax
0x18004a08f  jz      short loc_18004A0D9
0x18004a091  mov     rcx, cs:WPP_GLOBAL_Control
0x18004a098  lea     rax, WPP_GLOBAL_Control
0x18004a09f  cmp     rcx, rax
0x18004a0a2  jz      loc_18004A282
0x18004a0a8  cmp     [rcx+19h], r12b
0x18004a0ac  jb      loc_18004A282
0x18004a0b2  test    [rcx+1Ch], r12b
0x18004a0b6  jz      loc_18004A282
0x18004a0bc  mov     rcx, [rcx+10h]
0x18004a0c0  lea     r8, WPP_52d70405f63e3f10ed920fefc30aa7c8_Traceguids
0x18004a0c7  mov     edx, 17h
0x18004a0cc  mov     r9d, ebx
0x18004a0cf  call    WPP_SF_d
0x18004a0d4  jmp     loc_18004A282
0x18004a0d9  mov     rax, qword ptr [rbp+4Fh+pclsid.Data1]
0x18004a0dd  sub     rax, [rdi]
0x18004a0e0  jnz     short loc_18004A0EA
0x18004a0e2  mov     rax, qword ptr [rbp+4Fh+pclsid.Data4]
0x18004a0e6  sub     rax, [rdi+8]
0x18004a0ea  test    rax, rax
0x18004a0ed  jnz     loc_18004A27B
0x18004a0f3  lea     rax, [rbp+4Fh+hKey]
0x18004a0f7  mov     [r14], r12d
0x18004a0fa  mov     r9d, 20019h; samDesired
0x18004a100  mov     [rsp+0E0h+phkResult], rax; phkResult
0x18004a105  xor     r8d, r8d; ulOptions
0x18004a108  lea     rdx, SubKey; "Ndi\\IHVExtensions"
0x18004a10f  mov     rcx, rsi; hKey
0x18004a112  call    cs:__imp_RegOpenKeyExW
0x18004a118  test    eax, eax
0x18004a11a  jz      short loc_18004A15A
0x18004a11c  mov     rcx, cs:WPP_GLOBAL_Control
0x18004a123  lea     rdi, WPP_GLOBAL_Control
0x18004a12a  cmp     rcx, rdi
0x18004a12d  jz      short loc_18004A153
0x18004a12f  cmp     byte ptr [rcx+19h], 4
0x18004a133  jb      short loc_18004A153
0x18004a135  test    [rcx+1Ch], r12b
0x18004a139  jz      short loc_18004A153
0x18004a13b  mov     rcx, [rcx+10h]
0x18004a13f  lea     r8, WPP_52d70405f63e3f10ed920fefc30aa7c8_Traceguids
0x18004a146  mov     edx, 18h
0x18004a14b  mov     r9d, eax
0x18004a14e  call    WPP_SF_d
0x18004a153  xor     ebx, ebx
0x18004a155  jmp     loc_18004A289
0x18004a15a  mov     rcx, [rbp+4Fh+hKey]; hKey
0x18004a15e  lea     r9, [r15+8]; lpDst
0x18004a162  mov     ebx, 208h
0x18004a167  lea     rdx, ValueName; "ExtensibilityDLL"
0x18004a16e  mov     r8d, ebx; dwBytes
0x18004a171  call    ReadRegistryString
0x18004a176  xor     ecx, ecx
0x18004a178  lea     r9, [r15+210h]; lpDst
0x18004a17f  test    eax, eax
0x18004a181  lea     rdx, aGroupname; "GroupName"
0x18004a188  mov     r8d, ebx; dwBytes
0x18004a18b  setz    cl
0x18004a18e  mov     [r15], ecx
0x18004a191  mov     rcx, [rbp+4Fh+hKey]; hKey
0x18004a195  call    ReadRegistryString
0x18004a19a  mov     rcx, [rbp+4Fh+hKey]; hKey
0x18004a19e  lea     r9, [rbp+4Fh+sz]; lpDst
0x18004a1a2  mov     r14d, 4Eh ; 'N'
0x18004a1a8  lea     rdx, aUiextensibilit; "UIExtensibilityCLSID"
0x18004a1af  mov     r8d, r14d; dwBytes
0x18004a1b2  call    ReadRegistryString
0x18004a1b7  lea     rbx, [r15+418h]
0x18004a1be  mov     rdx, rbx; pclsid
0x18004a1c1  lea     rcx, [rbp+4Fh+sz]; lpsz
0x18004a1c5  call    cs:__imp_CLSIDFromString
0x18004a1cb  lea     edi, [r14-3Eh]
0x18004a1cf  test    eax, eax
0x18004a1d1  jz      short loc_18004A1E0
0x18004a1d3  mov     eax, edi
0x18004a1d5  mov     byte ptr [rbx], 0
0x18004a1d8  add     rbx, r12
0x18004a1db  sub     rax, r12
0x18004a1de  jnz     short loc_18004A1D5
0x18004a1e0  mov     rcx, [rbp+4Fh+hKey]; hKey
0x18004a1e4  lea     rbx, [r15+4]
0x18004a1e8  mov     r8, rbx
0x18004a1eb  call    ReadRegistryNumber
0x18004a1f0  mov     cl, [rbx]
0x18004a1f2  lea     r9, [rbp+4Fh+sz]; lpDst
0x18004a1f6  mov     al, [rbx+2]
0x18004a1f9  lea     rdx, aDiagnosticsid; "DiagnosticsID"
0x18004a200  mov     [rbx+2], cl
0x18004a203  mov     r8d, r14d; dwBytes
0x18004a206  mov     rcx, [rbp+4Fh+hKey]; hKey
0x18004a20a  mov     [rbx], al
0x18004a20c  call    ReadRegistryString
0x18004a211  lea     rbx, [r15+428h]
0x18004a218  mov     rdx, rbx; pclsid
0x18004a21b  lea     rcx, [rbp+4Fh+sz]; lpsz
0x18004a21f  call    cs:__imp_CLSIDFromString
0x18004a225  test    eax, eax
0x18004a227  jz      short loc_18004A234
0x18004a229  mov     byte ptr [rbx], 0
0x18004a22c  add     rbx, r12
0x18004a22f  sub     rdi, r12
0x18004a232  jnz     short loc_18004A229
0x18004a234  xor     ebx, ebx
0x18004a236  mov     rcx, [rbp+4Fh+hKey]; hKey
0x18004a23a  call    cs:__imp_RegCloseKey
0x18004a240  test    eax, eax
0x18004a242  jz      short loc_18004A282
0x18004a244  mov     rcx, cs:WPP_GLOBAL_Control
0x18004a24b  lea     rdi, WPP_GLOBAL_Control
0x18004a252  cmp     rcx, rdi
0x18004a255  jz      short loc_18004A289
0x18004a257  cmp     byte ptr [rcx+19h], 3
0x18004a25b  jb      short loc_18004A289
0x18004a25d  test    [rcx+1Ch], r12b
0x18004a261  jz      short loc_18004A289
0x18004a263  mov     rcx, [rcx+10h]
0x18004a267  lea     edx, [rbx+19h]
0x18004a26a  mov     r9d, eax
0x18004a26d  lea     r8, WPP_52d70405f63e3f10ed920fefc30aa7c8_Traceguids
0x18004a274  call    WPP_SF_d
0x18004a279  jmp     short loc_18004A289
0x18004a27b  mov     dword ptr [r14], 0
0x18004a282  lea     rdi, WPP_GLOBAL_Control
0x18004a289  mov     rcx, rsi; hKey
0x18004a28c  call    cs:__imp_RegCloseKey
0x18004a292  test    eax, eax
0x18004a294  jz      short loc_18004A2C6
0x18004a296  mov     rcx, cs:WPP_GLOBAL_Control
0x18004a29d  cmp     rcx, rdi
0x18004a2a0  jz      short loc_18004A2F6
0x18004a2a2  cmp     byte ptr [rcx+19h], 3
0x18004a2a6  jb      short loc_18004A2CD
0x18004a2a8  test    [rcx+1Ch], r12b
0x18004a2ac  jz      short loc_18004A2CD
0x18004a2ae  mov     edx, 1Ah
0x18004a2b3  mov     rcx, [rcx+10h]
0x18004a2b7  lea     r8, WPP_52d70405f63e3f10ed920fefc30aa7c8_Traceguids
0x18004a2be  mov     r9d, eax
0x18004a2c1  call    WPP_SF_d
0x18004a2c6  mov     rcx, cs:WPP_GLOBAL_Control
0x18004a2cd  cmp     rcx, rdi
0x18004a2d0  jz      short loc_18004A2F6
0x18004a2d2  cmp     byte ptr [rcx+19h], 4
0x18004a2d6  jb      short loc_18004A2F6
0x18004a2d8  test    [rcx+1Ch], r12b
0x18004a2dc  jz      short loc_18004A2F6
0x18004a2de  mov     rcx, [rcx+10h]
0x18004a2e2  lea     r8, WPP_52d70405f63e3f10ed920fefc30aa7c8_Traceguids
0x18004a2e9  mov     edx, 1Bh
0x18004a2ee  mov     r9d, ebx
0x18004a2f1  call    WPP_SF_d
0x18004a2f6  mov     eax, ebx
0x18004a2f8  mov     rcx, [rbp+4Fh+var_40]
0x18004a2fc  xor     rcx, rsp; StackCookie
0x18004a2ff  call    __security_check_cookie
0x18004a304  add     rsp, 0B0h
0x18004a30b  pop     r15
0x18004a30d  pop     r14
0x18004a30f  pop     r12
0x18004a311  pop     rdi
0x18004a312  pop     rsi
0x18004a313  pop     rbx
0x18004a314  pop     rbp
0x18004a315  retn
```
