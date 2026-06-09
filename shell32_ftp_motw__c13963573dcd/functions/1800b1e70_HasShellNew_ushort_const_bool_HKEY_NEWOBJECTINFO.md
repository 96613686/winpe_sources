# _HasShellNew(ushort const *,bool,HKEY__ * *,NEWOBJECTINFO *)

- ea: `0x1800b1e70`
- end: `0x1800b2597`
- name: `?_HasShellNew@@YAHPEBG_NPEAPEAUHKEY__@@PEAUNEWOBJECTINFO@@@Z`
- size: `1831`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, HKEY *, struct NEWOBJECTINFO *)`
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800f59d4`
- `0x1804baa74`

## callees

- `0x18003a3e0`
- `0x1800b1e70`
- `0x180249490`
- `0x1804b8afc`
- `0x1804b8f44`
- `0x1804bb70c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800b2080`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800b2106`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800b215f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800b219b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800b2404`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800b24dc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800b2080`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800b2106`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800b215f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800b219b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800b2404`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800b24dc`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800b1f50`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800b1fdc`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800b1f50`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800b1fdc`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800b202f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800b2067`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800b20b8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800b20f1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800b2144`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800b202f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800b2067`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800b20b8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800b20f1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800b2144`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800b227f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800b22f3`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800b2355`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800b2387`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800b23b9`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800b23eb`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800b2433`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800b2463`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800b2493`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800b24c3`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800b227f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800b22f3`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800b2355`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800b2387`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800b23b9`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800b23eb`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800b2433`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800b2463`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800b2493`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800b24c3`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x1800b1ed1`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x1800b1ed1`
- `SHLWAPI!AssocQueryStringW` at `0x1800b223c`
- `SHLWAPI!AssocQueryStringW` at `0x1800b223c`

## string_xrefs

- `0x1800b1f94`: `%s\CLSID`
- `0x1800b1ffa`: `CLSID\%s`
- `0x1800b2346`: `Command`
- `0x1800b2424`: `Command`
- `0x1800b23d4`: `Directory`
- `0x1800b24ac`: `Directory`

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
0x1800b1e70  mov     [rsp-8+arg_8], rbx
0x1800b1e75  push    rbp
0x1800b1e76  push    rsi
0x1800b1e77  push    rdi
0x1800b1e78  push    r12
0x1800b1e7a  push    r13
0x1800b1e7c  push    r14
0x1800b1e7e  push    r15
0x1800b1e80  lea     rbp, [rsp-0E0h]
0x1800b1e88  sub     rsp, 1E0h
0x1800b1e8f  mov     rax, cs:__security_cookie
0x1800b1e96  xor     rax, rsp
0x1800b1e99  mov     [rbp+110h+var_40], rax
0x1800b1ea0  xor     edi, edi
0x1800b1ea2  mov     [rsp+210h+var_1D0], dl
0x1800b1ea6  cmp     word ptr [rcx], 2Eh ; '.'
0x1800b1eaa  mov     r15, r9
0x1800b1ead  mov     r13, r8
0x1800b1eb0  mov     r12, rcx
0x1800b1eb3  mov     ebx, edi
0x1800b1eb5  jz      short loc_1800B1F1D
0x1800b1eb7  xor     esi, esi
0x1800b1eb9  mov     eax, esi
0x1800b1ebb  cmp     edi, 1
0x1800b1ebe  jnb     short loc_1800B1EE6
0x1800b1ec0  lea     rax, off_1805BAF00; "Folder"
0x1800b1ec7  movsxd  rdx, edi
0x1800b1eca  mov     rcx, r12; pszStr1
0x1800b1ecd  mov     rdx, [rax+rdx*8]; pszStr2
0x1800b1ed1  call    cs:__imp_StrCmpICW
0x1800b1ed8  nop     dword ptr [rax+rax+00h]
0x1800b1edd  test    eax, eax
0x1800b1edf  jnz     short loc_1800B1F19
0x1800b1ee1  mov     eax, 1
0x1800b1ee6  xor     edi, edi
0x1800b1ee8  test    eax, eax
0x1800b1eea  jnz     short loc_1800B1F1D
0x1800b1eec  mov     eax, ebx
0x1800b1eee  mov     rcx, [rbp+110h+var_40]
0x1800b1ef5  xor     rcx, rsp; StackCookie
0x1800b1ef8  call    __security_check_cookie
0x1800b1efd  mov     rbx, [rsp+210h+arg_8]
0x1800b1f05  add     rsp, 1E0h
0x1800b1f0c  pop     r15
0x1800b1f0e  pop     r14
0x1800b1f10  pop     r13
0x1800b1f12  pop     r12
0x1800b1f14  pop     rdi
0x1800b1f15  pop     rsi
0x1800b1f16  pop     rbp
0x1800b1f17  retn
0x1800b1f19  inc     edi
0x1800b1f1b  jmp     short loc_1800B1EB9
0x1800b1f1d  lea     rax, [rsp+210h+Type]
0x1800b1f22  mov     [rsp+210h+Type], 80h
0x1800b1f2a  mov     [rsp+210h+pcbData], rax; pcbData
0x1800b1f2f  mov     r9d, 2; dwFlags
0x1800b1f35  lea     rax, [rbp+110h+pszAssoc]
0x1800b1f39  xor     r8d, r8d; lpValue
0x1800b1f3c  mov     [rsp+210h+pvData], rax; pvData
0x1800b1f41  mov     rdx, r12; lpSubKey
0x1800b1f44  mov     rcx, 0FFFFFFFF80000000h; hkey
0x1800b1f4b  mov     [rsp+210h+pdwType], rdi; pdwType
0x1800b1f50  call    cs:__imp_RegGetValueW
0x1800b1f57  nop     dword ptr [rax+rax+00h]
0x1800b1f5c  test    eax, eax
0x1800b1f5e  jnz     short loc_1800B1F66
0x1800b1f60  movzx   ecx, [rbp+110h+pszAssoc]
0x1800b1f64  jmp     short loc_1800B1F76
0x1800b1f66  mov     ecx, edi
0x1800b1f68  mov     [rbp+110h+pszAssoc], cx
0x1800b1f6c  jle     short loc_1800B1F78
0x1800b1f6e  movzx   eax, ax
0x1800b1f71  or      eax, 80070000h
0x1800b1f76  test    eax, eax
0x1800b1f78  jnz     loc_1800B1EEC
0x1800b1f7e  test    cx, cx
0x1800b1f81  jz      loc_1800B1EEC
0x1800b1f87  mov     r14d, 40h ; '@'
0x1800b1f8d  lea     r9, [rbp+110h+pszAssoc]
0x1800b1f91  mov     edx, r14d; unsigned __int64
0x1800b1f94  lea     r8, aSClsid; "%s\\CLSID"
0x1800b1f9b  lea     rcx, [rbp+110h+SubKey]; unsigned __int16 *
0x1800b1f9f  mov     rsi, rdi
0x1800b1fa2  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800b1fa7  lea     rax, [rsp+210h+Type]
0x1800b1fac  mov     [rsp+210h+Type], 4Eh ; 'N'
0x1800b1fb4  mov     [rsp+210h+pcbData], rax; pcbData
0x1800b1fb9  lea     r9d, [r14-3Eh]; dwFlags
0x1800b1fbd  lea     rax, [rbp+110h+var_90]
0x1800b1fc4  xor     r8d, r8d; lpValue
0x1800b1fc7  mov     [rsp+210h+pvData], rax; pvData
0x1800b1fcc  lea     rdx, [rbp+110h+SubKey]; lpSubKey
0x1800b1fd0  mov     rcx, 0FFFFFFFF80000000h; hkey
0x1800b1fd7  mov     [rsp+210h+pdwType], rdi; pdwType
0x1800b1fdc  call    cs:__imp_RegGetValueW
0x1800b1fe3  nop     dword ptr [rax+rax+00h]
0x1800b1fe8  test    eax, eax
0x1800b1fea  jnz     loc_1800B22B3
0x1800b1ff0  lea     r9, [rbp+110h+var_90]
0x1800b1ff7  mov     rdx, r14; unsigned __int64
0x1800b1ffa  lea     r8, aClsidS; "CLSID\\%s"
0x1800b2001  lea     rcx, [rbp+110h+SubKey]; unsigned __int16 *
0x1800b2005  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800b200a  lea     rax, [rsp+210h+phkResult]
0x1800b200f  mov     [rsp+210h+phkResult], rdi
0x1800b2014  mov     r9d, 20019h; samDesired
0x1800b201a  mov     [rsp+210h+pdwType], rax; phkResult
0x1800b201f  xor     r8d, r8d; ulOptions
0x1800b2022  lea     rdx, [rbp+110h+SubKey]; lpSubKey
0x1800b2026  mov     rcx, 0FFFFFFFF80000000h; hKey
0x1800b202d  mov     ebx, edi
0x1800b202f  call    cs:__imp_RegOpenKeyExW
0x1800b2036  nop     dword ptr [rax+rax+00h]
0x1800b203b  test    eax, eax
0x1800b203d  jnz     loc_1800B21E9
0x1800b2043  mov     rcx, [rsp+210h+phkResult]; hKey
0x1800b2048  lea     rax, [rsp+210h+var_1C8]
0x1800b204d  mov     r9d, 20019h; samDesired
0x1800b2053  mov     [rsp+210h+pdwType], rax; phkResult
0x1800b2058  xor     r8d, r8d; ulOptions
0x1800b205b  mov     [rsp+210h+var_1C8], rdi
0x1800b2060  lea     rdx, aShellnew; "ShellNew"
0x1800b2067  call    cs:__imp_RegOpenKeyExW
0x1800b206e  nop     dword ptr [rax+rax+00h]
0x1800b2073  test    eax, eax
0x1800b2075  jz      loc_1800B22D1
0x1800b207b  mov     rcx, [rsp+210h+phkResult]; hKey
0x1800b2080  call    cs:__imp_RegCloseKey
0x1800b2087  nop     dword ptr [rax+rax+00h]
0x1800b208c  test    ebx, ebx
0x1800b208e  jnz     loc_1800B21E4
0x1800b2094  lea     rax, [rsp+210h+hKey]
0x1800b2099  mov     [rsp+210h+hKey], rdi
0x1800b209e  mov     r9d, 20019h; samDesired
0x1800b20a4  mov     [rsp+210h+pdwType], rax; phkResult
0x1800b20a9  xor     r8d, r8d; ulOptions
0x1800b20ac  mov     rdx, r12; lpSubKey
0x1800b20af  mov     rcx, 0FFFFFFFF80000000h; hKey
0x1800b20b6  mov     ebx, edi
0x1800b20b8  call    cs:__imp_RegOpenKeyExW
0x1800b20bf  nop     dword ptr [rax+rax+00h]
0x1800b20c4  test    eax, eax
0x1800b20c6  jnz     loc_1800B2171
0x1800b20cc  mov     rcx, [rsp+210h+hKey]; hKey
0x1800b20d1  lea     rax, [rsp+210h+var_1A8]
0x1800b20d6  mov     r9d, 20019h; samDesired
0x1800b20dc  mov     [rsp+210h+pdwType], rax; phkResult
0x1800b20e1  xor     r8d, r8d; ulOptions
0x1800b20e4  mov     [rsp+210h+var_1A8], 0
0x1800b20ed  lea     rdx, [rbp+110h+pszAssoc]; lpSubKey
0x1800b20f1  call    cs:__imp_RegOpenKeyExW
0x1800b20f8  nop     dword ptr [rax+rax+00h]
0x1800b20fd  mov     rcx, [rsp+210h+hKey]; hKey
0x1800b2102  test    eax, eax
0x1800b2104  jnz     short loc_1800B2121
0x1800b2106  call    cs:__imp_RegCloseKey
0x1800b210d  nop     dword ptr [rax+rax+00h]
0x1800b2112  mov     rcx, [rsp+210h+var_1A8]; hKey
0x1800b2117  mov     edi, 1
0x1800b211c  mov     [rsp+210h+hKey], rcx
0x1800b2121  lea     rax, [rsp+210h+var_1C0]
0x1800b2126  mov     [rsp+210h+var_1C0], 0
0x1800b212f  mov     r9d, 20019h; samDesired
0x1800b2135  mov     [rsp+210h+pdwType], rax; phkResult
0x1800b213a  xor     r8d, r8d; ulOptions
0x1800b213d  lea     rdx, aShellnew; "ShellNew"
0x1800b2144  call    cs:__imp_RegOpenKeyExW
0x1800b214b  nop     dword ptr [rax+rax+00h]
0x1800b2150  xor     ecx, ecx
0x1800b2152  test    eax, eax
0x1800b2154  jz      loc_1800B225D
0x1800b215a  mov     rcx, [rsp+210h+hKey]; hKey
0x1800b215f  call    cs:__imp_RegCloseKey
0x1800b2166  nop     dword ptr [rax+rax+00h]
0x1800b216b  test    ebx, ebx
0x1800b216d  jnz     short loc_1800B21AC
0x1800b216f  xor     edi, edi
0x1800b2171  test    ebx, ebx
0x1800b2173  jnz     loc_1800B2214
0x1800b2179  xor     r15d, r15d
0x1800b217c  cmp     [rsp+210h+var_1D0], r15b
0x1800b2181  jnz     loc_1800B2564
0x1800b2187  test    ebx, ebx
0x1800b2189  jnz     loc_1800B2325
0x1800b218f  test    rsi, rsi
0x1800b2192  jz      loc_1800B1EEC
0x1800b2198  mov     rcx, rsi; hKey
0x1800b219b  call    cs:__imp_RegCloseKey
0x1800b21a2  nop     dword ptr [rax+rax+00h]
0x1800b21a7  jmp     loc_1800B1EEC
0x1800b21ac  test    r15, r15
0x1800b21af  jz      short loc_1800B216F
0x1800b21b1  test    edi, edi
0x1800b21b3  lea     rax, aSShellnew; "%s\\ShellNew"
0x1800b21ba  lea     r8, aSSShellnew; "%s\\%s\\ShellNew"
0x1800b21c1  mov     r9, r12
0x1800b21c4  cmovz   r8, rax; unsigned __int16 *
0x1800b21c8  lea     rcx, [r15+29Ch]; unsigned __int16 *
0x1800b21cf  lea     rax, [rbp+110h+pszAssoc]
0x1800b21d3  mov     edx, 104h; unsigned __int64
0x1800b21d8  mov     [rsp+210h+pdwType], rax
0x1800b21dd  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800b21e2  jmp     short loc_1800B216F
0x1800b21e4  test    r15, r15
0x1800b21e7  jnz     short loc_1800B21F3
0x1800b21e9  test    ebx, ebx
0x1800b21eb  jz      loc_1800B2094
0x1800b21f1  jmp     short loc_1800B2214
0x1800b21f3  lea     rcx, [r15+29Ch]; unsigned __int16 *
0x1800b21fa  mov     [rsp+210h+pdwType], rdi
0x1800b21ff  lea     r9, [rbp+110h+SubKey]
0x1800b2203  mov     edx, 104h; unsigned __int64
0x1800b2208  lea     r8, aSShellnew; "%s\\ShellNew"
0x1800b220f  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800b2214  xor     r9d, r9d; pszExtra
0x1800b2217  mov     [rsp+210h+pcchOut], r14d
0x1800b221c  lea     rax, [rsp+210h+pcchOut]
0x1800b2221  mov     ecx, 800h; flags
0x1800b2226  mov     [rsp+210h+pvData], rax; pcchOut
0x1800b222b  lea     r8, [rbp+110h+pszAssoc]; pszAssoc
0x1800b222f  lea     rax, [rbp+110h+SubKey]
0x1800b2233  lea     edx, [r9+3]; str
0x1800b2237  mov     [rsp+210h+pdwType], rax; pszOut
0x1800b223c  call    cs:__imp_AssocQueryStringW
0x1800b2243  nop     dword ptr [rax+rax+00h]
0x1800b2248  mov     edi, eax
0x1800b224a  test    eax, eax
0x1800b224c  jns     loc_1800B24ED
0x1800b2252  xor     r15d, r15d
0x1800b2255  mov     ebx, r15d
0x1800b2258  jmp     loc_1800B217C
0x1800b225d  mov     [rsp+210h+pvData], rcx; lpcbData
0x1800b2262  lea     r9, [rsp+210h+Type]; lpType
0x1800b2267  mov     [rsp+210h+pdwType], rcx; lpData
0x1800b226c  lea     rdx, ValueName; "FileName"
0x1800b2273  mov     [rsp+210h+Type], ecx
0x1800b2277  xor     r8d, r8d; lpReserved
0x1800b227a  mov     rcx, [rsp+210h+var_1C0]; hKey
0x1800b227f  call    cs:__imp_RegQueryValueExW
0x1800b2286  nop     dword ptr [rax+rax+00h]
0x1800b228b  xor     ecx, ecx
0x1800b228d  test    eax, eax
0x1800b228f  jnz     loc_1800B2337
0x1800b2295  mov     eax, [rsp+210h+Type]
0x1800b2299  dec     eax
0x1800b229b  cmp     eax, 1
0x1800b229e  ja      loc_1800B2337
0x1800b22a4  mov     rsi, [rsp+210h+var_1C0]
0x1800b22a9  mov     ebx, 1
0x1800b22ae  jmp     loc_1800B215A
0x1800b22b3  mov     [rbp+110h+var_90], di
0x1800b22ba  jle     short loc_1800B22C6
0x1800b22bc  movzx   eax, ax
0x1800b22bf  or      eax, 80070000h
0x1800b22c4  test    eax, eax
0x1800b22c6  jz      loc_1800B1FF0
0x1800b22cc  jmp     loc_1800B2094
0x1800b22d1  mov     rcx, [rsp+210h+var_1C8]; hKey
0x1800b22d6  lea     r9, [rsp+210h+var_19C]; lpType
0x1800b22db  mov     [rsp+210h+pvData], rdi; lpcbData
0x1800b22e0  lea     rdx, ValueName; "FileName"
0x1800b22e7  xor     r8d, r8d; lpReserved
0x1800b22ea  mov     [rsp+210h+pdwType], rdi; lpData
0x1800b22ef  mov     [rsp+210h+var_19C], edi
0x1800b22f3  call    cs:__imp_RegQueryValueExW
0x1800b22fa  nop     dword ptr [rax+rax+00h]
0x1800b22ff  test    eax, eax
0x1800b2301  jnz     loc_1800B2415
0x1800b2307  mov     eax, [rsp+210h+var_19C]
0x1800b230b  dec     eax
0x1800b230d  cmp     eax, 1
0x1800b2310  ja      loc_1800B2415
0x1800b2316  mov     rsi, [rsp+210h+var_1C8]
0x1800b231b  mov     ebx, 1
0x1800b2320  jmp     loc_1800B207B
0x1800b2325  test    r13, r13
0x1800b2328  jz      loc_1800B218F
0x1800b232e  mov     [r13+0], rsi
0x1800b2332  jmp     loc_1800B1EEC
0x1800b2337  mov     [rsp+210h+pvData], rcx; lpcbData
0x1800b233c  lea     r9, [rsp+210h+Type]; lpType
0x1800b2341  mov     [rsp+210h+pdwType], rcx; lpData
0x1800b2346  lea     rdx, aCommand; "Command"
0x1800b234d  mov     rcx, [rsp+210h+var_1C0]; hKey
0x1800b2352  xor     r8d, r8d; lpReserved
0x1800b2355  call    cs:__imp_RegQueryValueExW
0x1800b235c  nop     dword ptr [rax+rax+00h]
0x1800b2361  xor     ecx, ecx
0x1800b2363  test    eax, eax
0x1800b2365  jz      loc_1800B253C
0x1800b236b  mov     [rsp+210h+pvData], rcx; lpcbData
0x1800b2370  lea     rdx, aData_0; "Data"
0x1800b2377  mov     [rsp+210h+pdwType], rcx; lpData
0x1800b237c  xor     r9d, r9d; lpType
0x1800b237f  mov     rcx, [rsp+210h+var_1C0]; hKey
0x1800b2384  xor     r8d, r8d; lpReserved
0x1800b2387  call    cs:__imp_RegQueryValueExW
0x1800b238e  nop     dword ptr [rax+rax+00h]
0x1800b2393  xor     ecx, ecx
  ... truncated ...
```
