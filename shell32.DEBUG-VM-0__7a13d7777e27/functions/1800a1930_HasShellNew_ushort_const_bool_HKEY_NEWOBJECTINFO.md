# _HasShellNew(ushort const *,bool,HKEY__ * *,NEWOBJECTINFO *)

- ea: `0x1800a1930`
- end: `0x1800a1fc0`
- name: `?_HasShellNew@@YAHPEBG_NPEAPEAUHKEY__@@PEAUNEWOBJECTINFO@@@Z`
- size: `1680`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, HKEY *, struct NEWOBJECTINFO *)`
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800f267c`
- `0x1804854a4`

## callees

- `0x18003eab0`
- `0x1800a1930`
- `0x180233280`
- `0x1804836a4`
- `0x180483ab0`
- `0x18048608c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800a1adc`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800a1b0e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800a1b53`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800a1b86`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800a1bcd`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800a1adc`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800a1b0e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800a1b53`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800a1b86`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800a1bcd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800a1b21`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800a1b95`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800a1be2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800a1c18`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800a1e51`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800a1f0b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800a1b21`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800a1b95`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800a1be2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800a1c18`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800a1e51`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800a1f0b`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800a1a09`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800a1a8f`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800a1a09`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800a1a8f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800a1cf0`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800a1d5e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800a1dba`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800a1de6`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800a1e12`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800a1e3e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800a1e7a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800a1ea4`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800a1ece`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800a1ef8`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800a1cf0`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800a1d5e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800a1dba`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800a1de6`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800a1e12`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800a1e3e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800a1e7a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800a1ea4`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800a1ece`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800a1ef8`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x1800a1991`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x1800a1991`
- `SHLWAPI!AssocQueryStringW` at `0x1800a1cb3`
- `SHLWAPI!AssocQueryStringW` at `0x1800a1cb3`

## string_xrefs

- `0x1800a1a47`: `%s\CLSID`
- `0x1800a1aa7`: `CLSID\%s`
- `0x1800a1dab`: `Command`
- `0x1800a1e6b`: `Command`
- `0x1800a1e27`: `Directory`
- `0x1800a1ee1`: `Directory`

## pseudocode

```c
__int64 __fastcall _HasShellNew(const unsigned __int16 *a1, char a2, HKEY *a3, struct NEWOBJECTINFO *a4)
{
  HRESULT v4; // edi
  unsigned int v8; // ebx
  int v9; // eax
  int ValueW; // eax
  bool v12; // zf
  WCHAR v13; // cx
  __int64 v14; // r14
  HKEY v15; // rsi
  LSTATUS v16; // eax
  bool v17; // zf
  _WORD *v18; // rdx
  _WORD *v19; // rcx
  LSTATUS v20; // eax
  HKEY v21; // rcx
  const unsigned __int16 *v22; // r8
  __int64 v23; // rcx
  WCHAR *v24; // r8
  __int64 v25; // rcx
  ShellNewItemMenuTelemetry *v26; // rcx
  HKEY v28; // [rsp+48h] [rbp-B8h] BYREF
  HKEY v29; // [rsp+50h] [rbp-B0h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-A8h] BYREF
  HKEY phkResult; // [rsp+60h] [rbp-A0h] BYREF
  HKEY v32; // [rsp+68h] [rbp-98h] BYREF
  DWORD Type; // [rsp+70h] [rbp-90h] BYREF
  DWORD v34; // [rsp+74h] [rbp-8Ch] BYREF
  DWORD pcchOut; // [rsp+78h] [rbp-88h] BYREF
  WCHAR pszAssoc[64]; // [rsp+80h] [rbp-80h] BYREF
  WCHAR SubKey[64]; // [rsp+100h] [rbp+0h] BYREF
  _WORD pvData[40]; // [rsp+180h] [rbp+80h] BYREF

  v4 = 0;
  v8 = 0;
  if ( *a1 == 46 )
    goto LABEL_8;
  while ( 1 )
  {
    v9 = 0;
    if ( v4 )
      break;
    if ( !StrCmpICW(a1, L"Folder") )
    {
      v9 = 1;
      break;
    }
    v4 = 1;
  }
  v4 = 0;
  if ( v9 )
  {
LABEL_8:
    Type = 128;
    ValueW = RegGetValueW(HKEY_CLASSES_ROOT, a1, 0, 2u, 0, pszAssoc, &Type);
    v12 = ValueW == 0;
    if ( ValueW )
    {
      v13 = 0;
      pszAssoc[0] = 0;
      if ( ValueW <= 0 )
      {
LABEL_13:
        if ( !v12 || !v13 )
          return v8;
        v14 = 64;
        v15 = 0;
        StringCchPrintfW(SubKey, 0x40u, L"%s\\CLSID", pszAssoc);
        Type = 78;
        v16 = RegGetValueW(HKEY_CLASSES_ROOT, SubKey, 0, 2u, 0, pvData, &Type);
        v17 = v16 == 0;
        if ( v16 )
        {
          pvData[0] = 0;
          if ( v16 > 0 )
            v17 = 0;
          if ( !v17 )
          {
LABEL_19:
            hKey = 0;
            v8 = 0;
            if ( !RegOpenKeyExW(HKEY_CLASSES_ROOT, a1, 0, 0x20019u, &hKey) )
            {
              v32 = 0;
              v20 = RegOpenKeyExW(hKey, pszAssoc, 0, 0x20019u, &v32);
              v21 = hKey;
              if ( !v20 )
              {
                RegCloseKey(hKey);
                v21 = v32;
                v4 = 1;
                hKey = v32;
              }
              v29 = 0;
              if ( !RegOpenKeyExW(v21, L"ShellNew", 0, 0x20019u, &v29) )
              {
                Type = 0;
                if ( (RegQueryValueExW(v29, L"FileName", 0, &Type, 0, 0) || Type - 1 > 1)
                  && (RegQueryValueExW(v29, L"Command", 0, &Type, 0, 0) || Type - 1 > 1)
                  && RegQueryValueExW(v29, L"Data", 0, 0, 0, 0)
                  && RegQueryValueExW(v29, L"NullFile", 0, 0, 0, 0)
                  && RegQueryValueExW(v29, L"Directory", 0, 0, 0, 0) )
                {
                  RegCloseKey(v29);
                }
                else
                {
                  v15 = v29;
                  v8 = 1;
                }
              }
              RegCloseKey(hKey);
              if ( v8 && a4 )
              {
                v22 = L"%s\\%s\\ShellNew";
                if ( !v4 )
                  v22 = L"%s\\ShellNew";
                StringCchPrintfW((unsigned __int16 *)a4 + 334, 0x104u, v22, a1, pszAssoc);
              }
              v4 = 0;
            }
            if ( !v8 )
              goto LABEL_26;
            goto LABEL_38;
          }
        }
        StringCchPrintfW(SubKey, 0x40u, L"CLSID\\%s", pvData);
        phkResult = 0;
        v8 = 0;
        if ( RegOpenKeyExW(HKEY_CLASSES_ROOT, SubKey, 0, 0x20019u, &phkResult) )
          goto LABEL_35;
        v28 = 0;
        if ( !RegOpenKeyExW(phkResult, L"ShellNew", 0, 0x20019u, &v28) )
        {
          v34 = 0;
          if ( (RegQueryValueExW(v28, L"FileName", 0, &v34, 0, 0) || v34 - 1 > 1)
            && (RegQueryValueExW(v28, L"Command", 0, &v34, 0, 0) || v34 - 1 > 1)
            && RegQueryValueExW(v28, L"Data", 0, 0, 0, 0)
            && RegQueryValueExW(v28, L"NullFile", 0, 0, 0, 0)
            && RegQueryValueExW(v28, L"Directory", 0, 0, 0, 0) )
          {
            RegCloseKey(v28);
          }
          else
          {
            v15 = v28;
            v8 = 1;
          }
        }
        RegCloseKey(phkResult);
        if ( !v8 )
          goto LABEL_19;
        if ( a4 )
        {
          StringCchPrintfW((unsigned __int16 *)a4 + 334, 0x104u, L"%s\\ShellNew", SubKey, 0);
        }
        else
        {
LABEL_35:
          if ( !v8 )
            goto LABEL_19;
        }
LABEL_38:
        pcchOut = 64;
        v4 = AssocQueryStringW(0x800u, ASSOCSTR_FRIENDLYDOCNAME, pszAssoc, 0, SubKey, &pcchOut);
        if ( v4 >= 0 )
        {
          if ( a4 )
          {
            v18 = (_WORD *)((char *)a4 + 20);
            v23 = 2147483646;
            v24 = SubKey;
            do
            {
              if ( !v23 )
                break;
              if ( !*v24 )
                break;
              *v18++ = *v24++;
              --v23;
              --v14;
            }
            while ( v14 );
            v19 = v18 - 1;
            if ( v14 )
              v19 = v18;
            *v19 = 0;
          }
        }
        else
        {
          v8 = 0;
        }
LABEL_26:
        if ( a2 && ShellNewItemMenuTelemetry::IsEnabled((unsigned __int8)v19, (unsigned __int64)v18) )
        {
          wil::details::static_lazy<ShellNewItemMenuTelemetry>::get(
            v25,
            _lambda_fa40fb0a4d2e6ea96376f9af081e34b4_::_lambda_invoker_cdecl_);
          ShellNewItemMenuTelemetry::ShellNewItemExtAndProgId_(v26, v8 != 0, a1, pszAssoc, v4);
        }
        if ( v8 && a3 )
        {
          *a3 = v15;
        }
        else if ( v15 )
        {
          RegCloseKey(v15);
        }
        return v8;
      }
      ValueW = (unsigned __int16)ValueW | 0x80070000;
    }
    else
    {
      v13 = pszAssoc[0];
    }
    v12 = ValueW == 0;
    goto LABEL_13;
  }
  return v8;
}

```

## disassembly

```asm
0x1800a1930  mov     [rsp-8+arg_8], rbx
0x1800a1935  push    rbp
0x1800a1936  push    rsi
0x1800a1937  push    rdi
0x1800a1938  push    r12
0x1800a193a  push    r13
0x1800a193c  push    r14
0x1800a193e  push    r15
0x1800a1940  lea     rbp, [rsp-0E0h]
0x1800a1948  sub     rsp, 1E0h
0x1800a194f  mov     rax, cs:__security_cookie
0x1800a1956  xor     rax, rsp
0x1800a1959  mov     [rbp+110h+var_40], rax
0x1800a1960  xor     edi, edi
0x1800a1962  mov     [rsp+210h+var_1D0], dl
0x1800a1966  cmp     word ptr [rcx], 2Eh ; '.'
0x1800a196a  mov     r15, r9
0x1800a196d  mov     r13, r8
0x1800a1970  mov     r12, rcx
0x1800a1973  mov     ebx, edi
0x1800a1975  jz      short loc_1800A19D6
0x1800a1977  xor     esi, esi
0x1800a1979  mov     eax, esi
0x1800a197b  cmp     edi, 1
0x1800a197e  jnb     short loc_1800A19A0
0x1800a1980  lea     rax, off_180579EF0; "Folder"
0x1800a1987  movsxd  rdx, edi
0x1800a198a  mov     rcx, r12; pszStr1
0x1800a198d  mov     rdx, [rax+rdx*8]; pszStr2
0x1800a1991  call    cs:__imp_StrCmpICW
0x1800a1997  test    eax, eax
0x1800a1999  jnz     short loc_1800A19D2
0x1800a199b  mov     eax, 1
0x1800a19a0  xor     edi, edi
0x1800a19a2  test    eax, eax
0x1800a19a4  jnz     short loc_1800A19D6
0x1800a19a6  mov     eax, ebx
0x1800a19a8  mov     rcx, [rbp+110h+var_40]
0x1800a19af  xor     rcx, rsp; StackCookie
0x1800a19b2  call    __security_check_cookie
0x1800a19b7  mov     rbx, [rsp+210h+arg_8]
0x1800a19bf  add     rsp, 1E0h
0x1800a19c6  pop     r15
0x1800a19c8  pop     r14
0x1800a19ca  pop     r13
0x1800a19cc  pop     r12
0x1800a19ce  pop     rdi
0x1800a19cf  pop     rsi
0x1800a19d0  pop     rbp
0x1800a19d1  retn
0x1800a19d2  inc     edi
0x1800a19d4  jmp     short loc_1800A1979
0x1800a19d6  lea     rax, [rsp+210h+Type]
0x1800a19db  mov     [rsp+210h+Type], 80h
0x1800a19e3  mov     [rsp+210h+pcbData], rax; pcbData
0x1800a19e8  mov     r9d, 2; dwFlags
0x1800a19ee  lea     rax, [rbp+110h+pszAssoc]
0x1800a19f2  xor     r8d, r8d; lpValue
0x1800a19f5  mov     [rsp+210h+pvData], rax; pvData
0x1800a19fa  mov     rdx, r12; lpSubKey
0x1800a19fd  mov     rcx, 0FFFFFFFF80000000h; hkey
0x1800a1a04  mov     [rsp+210h+pdwType], rdi; pdwType
0x1800a1a09  call    cs:__imp_RegGetValueW
0x1800a1a0f  test    eax, eax
0x1800a1a11  jnz     short loc_1800A1A19
0x1800a1a13  movzx   ecx, [rbp+110h+pszAssoc]
0x1800a1a17  jmp     short loc_1800A1A29
0x1800a1a19  mov     ecx, edi
0x1800a1a1b  mov     [rbp+110h+pszAssoc], cx
0x1800a1a1f  jle     short loc_1800A1A2B
0x1800a1a21  movzx   eax, ax
0x1800a1a24  or      eax, 80070000h
0x1800a1a29  test    eax, eax
0x1800a1a2b  jnz     loc_1800A19A6
0x1800a1a31  test    cx, cx
0x1800a1a34  jz      loc_1800A19A6
0x1800a1a3a  mov     r14d, 40h ; '@'
0x1800a1a40  lea     r9, [rbp+110h+pszAssoc]
0x1800a1a44  mov     edx, r14d; unsigned __int64
0x1800a1a47  lea     r8, aSClsid; "%s\\CLSID"
0x1800a1a4e  lea     rcx, [rbp+110h+SubKey]; unsigned __int16 *
0x1800a1a52  mov     rsi, rdi
0x1800a1a55  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800a1a5a  lea     rax, [rsp+210h+Type]
0x1800a1a5f  mov     [rsp+210h+Type], 4Eh ; 'N'
0x1800a1a67  mov     [rsp+210h+pcbData], rax; pcbData
0x1800a1a6c  lea     r9d, [r14-3Eh]; dwFlags
0x1800a1a70  lea     rax, [rbp+110h+var_90]
0x1800a1a77  xor     r8d, r8d; lpValue
0x1800a1a7a  mov     [rsp+210h+pvData], rax; pvData
0x1800a1a7f  lea     rdx, [rbp+110h+SubKey]; lpSubKey
0x1800a1a83  mov     rcx, 0FFFFFFFF80000000h; hkey
0x1800a1a8a  mov     [rsp+210h+pdwType], rdi; pdwType
0x1800a1a8f  call    cs:__imp_RegGetValueW
0x1800a1a95  test    eax, eax
0x1800a1a97  jnz     loc_1800A1D1E
0x1800a1a9d  lea     r9, [rbp+110h+var_90]
0x1800a1aa4  mov     rdx, r14; unsigned __int64
0x1800a1aa7  lea     r8, aClsidS; "CLSID\\%s"
0x1800a1aae  lea     rcx, [rbp+110h+SubKey]; unsigned __int16 *
0x1800a1ab2  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800a1ab7  lea     rax, [rsp+210h+phkResult]
0x1800a1abc  mov     [rsp+210h+phkResult], rdi
0x1800a1ac1  mov     r9d, 20019h; samDesired
0x1800a1ac7  mov     [rsp+210h+pdwType], rax; phkResult
0x1800a1acc  xor     r8d, r8d; ulOptions
0x1800a1acf  lea     rdx, [rbp+110h+SubKey]; lpSubKey
0x1800a1ad3  mov     rcx, 0FFFFFFFF80000000h; hKey
0x1800a1ada  mov     ebx, edi
0x1800a1adc  call    cs:__imp_RegOpenKeyExW
0x1800a1ae2  test    eax, eax
0x1800a1ae4  jnz     loc_1800A1C60
0x1800a1aea  mov     rcx, [rsp+210h+phkResult]; hKey
0x1800a1aef  lea     rax, [rsp+210h+var_1C8]
0x1800a1af4  mov     r9d, 20019h; samDesired
0x1800a1afa  mov     [rsp+210h+pdwType], rax; phkResult
0x1800a1aff  xor     r8d, r8d; ulOptions
0x1800a1b02  mov     [rsp+210h+var_1C8], rdi
0x1800a1b07  lea     rdx, aShellnew; "ShellNew"
0x1800a1b0e  call    cs:__imp_RegOpenKeyExW
0x1800a1b14  test    eax, eax
0x1800a1b16  jz      loc_1800A1D3C
0x1800a1b1c  mov     rcx, [rsp+210h+phkResult]; hKey
0x1800a1b21  call    cs:__imp_RegCloseKey
0x1800a1b27  test    ebx, ebx
0x1800a1b29  jnz     loc_1800A1C5B
0x1800a1b2f  lea     rax, [rsp+210h+hKey]
0x1800a1b34  mov     [rsp+210h+hKey], rdi
0x1800a1b39  mov     r9d, 20019h; samDesired
0x1800a1b3f  mov     [rsp+210h+pdwType], rax; phkResult
0x1800a1b44  xor     r8d, r8d; ulOptions
0x1800a1b47  mov     rdx, r12; lpSubKey
0x1800a1b4a  mov     rcx, 0FFFFFFFF80000000h; hKey
0x1800a1b51  mov     ebx, edi
0x1800a1b53  call    cs:__imp_RegOpenKeyExW
0x1800a1b59  test    eax, eax
0x1800a1b5b  jnz     loc_1800A1BEE
0x1800a1b61  mov     rcx, [rsp+210h+hKey]; hKey
0x1800a1b66  lea     rax, [rsp+210h+var_1A8]
0x1800a1b6b  mov     r9d, 20019h; samDesired
0x1800a1b71  mov     [rsp+210h+pdwType], rax; phkResult
0x1800a1b76  xor     r8d, r8d; ulOptions
0x1800a1b79  mov     [rsp+210h+var_1A8], 0
0x1800a1b82  lea     rdx, [rbp+110h+pszAssoc]; lpSubKey
0x1800a1b86  call    cs:__imp_RegOpenKeyExW
0x1800a1b8c  mov     rcx, [rsp+210h+hKey]; hKey
0x1800a1b91  test    eax, eax
0x1800a1b93  jnz     short loc_1800A1BAA
0x1800a1b95  call    cs:__imp_RegCloseKey
0x1800a1b9b  mov     rcx, [rsp+210h+var_1A8]; hKey
0x1800a1ba0  mov     edi, 1
0x1800a1ba5  mov     [rsp+210h+hKey], rcx
0x1800a1baa  lea     rax, [rsp+210h+var_1C0]
0x1800a1baf  mov     [rsp+210h+var_1C0], 0
0x1800a1bb8  mov     r9d, 20019h; samDesired
0x1800a1bbe  mov     [rsp+210h+pdwType], rax; phkResult
0x1800a1bc3  xor     r8d, r8d; ulOptions
0x1800a1bc6  lea     rdx, aShellnew; "ShellNew"
0x1800a1bcd  call    cs:__imp_RegOpenKeyExW
0x1800a1bd3  xor     ecx, ecx
0x1800a1bd5  test    eax, eax
0x1800a1bd7  jz      loc_1800A1CCE
0x1800a1bdd  mov     rcx, [rsp+210h+hKey]; hKey
0x1800a1be2  call    cs:__imp_RegCloseKey
0x1800a1be8  test    ebx, ebx
0x1800a1bea  jnz     short loc_1800A1C23
0x1800a1bec  xor     edi, edi
0x1800a1bee  test    ebx, ebx
0x1800a1bf0  jnz     loc_1800A1C8B
0x1800a1bf6  xor     r15d, r15d
0x1800a1bf9  cmp     [rsp+210h+var_1D0], r15b
0x1800a1bfe  jnz     loc_1800A1F8D
0x1800a1c04  test    ebx, ebx
0x1800a1c06  jnz     loc_1800A1D8A
0x1800a1c0c  test    rsi, rsi
0x1800a1c0f  jz      loc_1800A19A6
0x1800a1c15  mov     rcx, rsi; hKey
0x1800a1c18  call    cs:__imp_RegCloseKey
0x1800a1c1e  jmp     loc_1800A19A6
0x1800a1c23  test    r15, r15
0x1800a1c26  jz      short loc_1800A1BEC
0x1800a1c28  test    edi, edi
0x1800a1c2a  lea     rax, aSShellnew; "%s\\ShellNew"
0x1800a1c31  lea     r8, aSSShellnew; "%s\\%s\\ShellNew"
0x1800a1c38  mov     r9, r12
0x1800a1c3b  cmovz   r8, rax; unsigned __int16 *
0x1800a1c3f  lea     rcx, [r15+29Ch]; unsigned __int16 *
0x1800a1c46  lea     rax, [rbp+110h+pszAssoc]
0x1800a1c4a  mov     edx, 104h; unsigned __int64
0x1800a1c4f  mov     [rsp+210h+pdwType], rax
0x1800a1c54  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800a1c59  jmp     short loc_1800A1BEC
0x1800a1c5b  test    r15, r15
0x1800a1c5e  jnz     short loc_1800A1C6A
0x1800a1c60  test    ebx, ebx
0x1800a1c62  jz      loc_1800A1B2F
0x1800a1c68  jmp     short loc_1800A1C8B
0x1800a1c6a  lea     rcx, [r15+29Ch]; unsigned __int16 *
0x1800a1c71  mov     [rsp+210h+pdwType], rdi
0x1800a1c76  lea     r9, [rbp+110h+SubKey]
0x1800a1c7a  mov     edx, 104h; unsigned __int64
0x1800a1c7f  lea     r8, aSShellnew; "%s\\ShellNew"
0x1800a1c86  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800a1c8b  xor     r9d, r9d; pszExtra
0x1800a1c8e  mov     [rsp+210h+pcchOut], r14d
0x1800a1c93  lea     rax, [rsp+210h+pcchOut]
0x1800a1c98  mov     ecx, 800h; flags
0x1800a1c9d  mov     [rsp+210h+pvData], rax; pcchOut
0x1800a1ca2  lea     r8, [rbp+110h+pszAssoc]; pszAssoc
0x1800a1ca6  lea     rax, [rbp+110h+SubKey]
0x1800a1caa  lea     edx, [r9+3]; str
0x1800a1cae  mov     [rsp+210h+pdwType], rax; pszOut
0x1800a1cb3  call    cs:__imp_AssocQueryStringW
0x1800a1cb9  mov     edi, eax
0x1800a1cbb  test    eax, eax
0x1800a1cbd  jns     loc_1800A1F16
0x1800a1cc3  xor     r15d, r15d
0x1800a1cc6  mov     ebx, r15d
0x1800a1cc9  jmp     loc_1800A1BF9
0x1800a1cce  mov     [rsp+210h+pvData], rcx; lpcbData
0x1800a1cd3  lea     r9, [rsp+210h+Type]; lpType
0x1800a1cd8  mov     [rsp+210h+pdwType], rcx; lpData
0x1800a1cdd  lea     rdx, ValueName; "FileName"
0x1800a1ce4  mov     [rsp+210h+Type], ecx
0x1800a1ce8  xor     r8d, r8d; lpReserved
0x1800a1ceb  mov     rcx, [rsp+210h+var_1C0]; hKey
0x1800a1cf0  call    cs:__imp_RegQueryValueExW
0x1800a1cf6  xor     ecx, ecx
0x1800a1cf8  test    eax, eax
0x1800a1cfa  jnz     loc_1800A1D9C
0x1800a1d00  mov     eax, [rsp+210h+Type]
0x1800a1d04  dec     eax
0x1800a1d06  cmp     eax, 1
0x1800a1d09  ja      loc_1800A1D9C
0x1800a1d0f  mov     rsi, [rsp+210h+var_1C0]
0x1800a1d14  mov     ebx, 1
0x1800a1d19  jmp     loc_1800A1BDD
0x1800a1d1e  mov     [rbp+110h+var_90], di
0x1800a1d25  jle     short loc_1800A1D31
0x1800a1d27  movzx   eax, ax
0x1800a1d2a  or      eax, 80070000h
0x1800a1d2f  test    eax, eax
0x1800a1d31  jz      loc_1800A1A9D
0x1800a1d37  jmp     loc_1800A1B2F
0x1800a1d3c  mov     rcx, [rsp+210h+var_1C8]; hKey
0x1800a1d41  lea     r9, [rsp+210h+var_19C]; lpType
0x1800a1d46  mov     [rsp+210h+pvData], rdi; lpcbData
0x1800a1d4b  lea     rdx, ValueName; "FileName"
0x1800a1d52  xor     r8d, r8d; lpReserved
0x1800a1d55  mov     [rsp+210h+pdwType], rdi; lpData
0x1800a1d5a  mov     [rsp+210h+var_19C], edi
0x1800a1d5e  call    cs:__imp_RegQueryValueExW
0x1800a1d64  test    eax, eax
0x1800a1d66  jnz     loc_1800A1E5C
0x1800a1d6c  mov     eax, [rsp+210h+var_19C]
0x1800a1d70  dec     eax
0x1800a1d72  cmp     eax, 1
0x1800a1d75  ja      loc_1800A1E5C
0x1800a1d7b  mov     rsi, [rsp+210h+var_1C8]
0x1800a1d80  mov     ebx, 1
0x1800a1d85  jmp     loc_1800A1B1C
0x1800a1d8a  test    r13, r13
0x1800a1d8d  jz      loc_1800A1C0C
0x1800a1d93  mov     [r13+0], rsi
0x1800a1d97  jmp     loc_1800A19A6
0x1800a1d9c  mov     [rsp+210h+pvData], rcx; lpcbData
0x1800a1da1  lea     r9, [rsp+210h+Type]; lpType
0x1800a1da6  mov     [rsp+210h+pdwType], rcx; lpData
0x1800a1dab  lea     rdx, aCommand; "Command"
0x1800a1db2  mov     rcx, [rsp+210h+var_1C0]; hKey
0x1800a1db7  xor     r8d, r8d; lpReserved
0x1800a1dba  call    cs:__imp_RegQueryValueExW
0x1800a1dc0  xor     ecx, ecx
0x1800a1dc2  test    eax, eax
0x1800a1dc4  jz      loc_1800A1F65
0x1800a1dca  mov     [rsp+210h+pvData], rcx; lpcbData
0x1800a1dcf  lea     rdx, aData_0; "Data"
0x1800a1dd6  mov     [rsp+210h+pdwType], rcx; lpData
0x1800a1ddb  xor     r9d, r9d; lpType
0x1800a1dde  mov     rcx, [rsp+210h+var_1C0]; hKey
0x1800a1de3  xor     r8d, r8d; lpReserved
0x1800a1de6  call    cs:__imp_RegQueryValueExW
0x1800a1dec  xor     ecx, ecx
0x1800a1dee  test    eax, eax
0x1800a1df0  jz      loc_1800A1D0F
0x1800a1df6  mov     [rsp+210h+pvData], rcx; lpcbData
0x1800a1dfb  lea     rdx, aNullfile; "NullFile"
0x1800a1e02  mov     [rsp+210h+pdwType], rcx; lpData
0x1800a1e07  xor     r9d, r9d; lpType
0x1800a1e0a  mov     rcx, [rsp+210h+var_1C0]; hKey
0x1800a1e0f  xor     r8d, r8d; lpReserved
0x1800a1e12  call    cs:__imp_RegQueryValueExW
0x1800a1e18  xor     ecx, ecx
0x1800a1e1a  test    eax, eax
0x1800a1e1c  jz      loc_1800A1D0F
0x1800a1e22  mov     [rsp+210h+pvData], rcx; lpcbData
0x1800a1e27  lea     rdx, aDirectory; "Directory"
0x1800a1e2e  mov     [rsp+210h+pdwType], rcx; lpData
0x1800a1e33  xor     r9d, r9d; lpType
0x1800a1e36  mov     rcx, [rsp+210h+var_1C0]; hKey
  ... truncated ...
```
