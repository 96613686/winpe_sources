# SHRegGetValueW

- ea: `0x180005da0`
- end: `0x180006894`
- name: `SHRegGetValueW`
- size: `2804`
- prototype: `LSTATUS __stdcall(HKEY hkey, LPCWSTR pszSubKey, LPCWSTR pszValue, SRRF srrfFlags, DWORD *pdwType, void *pvData, DWORD *pcbData)`
- caller_count: `10`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x180004c80`
- `0x180005534`
- `0x180005b30`
- `0x180005cf0`
- `0x1800075f0`
- `0x18002c850`
- `0x18004bd74`
- `0x18005c850`
- `0x180070970`
- `0x180070a40`

## callees

- `0x180005da0`
- `0x180007120`
- `0x180008018`
- `0x1800080d0`
- `0x180066910`
- `0x1800672e8`
- `0x18009341c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006338`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006602`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006338`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006602`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180006493`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180006493`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800061ac`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180006464`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800065f7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000667e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800061ac`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180006464`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800065f7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000667e`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrDupW` at `0x18000616c`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrDupW` at `0x18000616c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180005ff8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180005ff8`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180005e74`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180005f92`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800064d2`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180005e74`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180005f92`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800064d2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180005f35`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180005f35`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18000618c`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18000618c`
- `api-ms-win-core-sysinfo-l1-2-0!GetOsSafeBootMode` at `0x1800066d9`
- `api-ms-win-core-sysinfo-l1-2-0!GetOsSafeBootMode` at `0x18000678c`
- `api-ms-win-core-sysinfo-l1-2-0!GetOsSafeBootMode` at `0x1800066d9`
- `api-ms-win-core-sysinfo-l1-2-0!GetOsSafeBootMode` at `0x18000678c`

## pseudocode

```c
LSTATUS __stdcall SHRegGetValueW(
        HKEY hkey,
        LPCWSTR pszSubKey,
        LPCWSTR pszValue,
        SRRF srrfFlags,
        DWORD *pdwType,
        void *pvData,
        DWORD *pcbData)
{
  DWORD v8; // ecx
  const WCHAR *v9; // rax
  int LastError; // ebx
  unsigned int v12; // eax
  DWORD v13; // edx
  HKEY v15; // rax
  DWORD v16; // ecx
  unsigned int v17; // eax
  DWORD v18; // r8d
  DWORD v19; // edx
  int v20; // eax
  unsigned __int64 v21; // r10
  __int64 v22; // r8
  int v23; // r9d
  DWORD v24; // eax
  unsigned __int64 v25; // r9
  __int64 v26; // r8
  DWORD v27; // edx
  unsigned __int64 v28; // rcx
  unsigned __int64 v29; // rax
  DWORD v30; // r8d
  unsigned __int64 v31; // rax
  WCHAR *v32; // rcx
  DWORD v33; // r15d
  HKEY v34; // rbx
  const WCHAR *v35; // rax
  DWORD v36; // r15d
  DWORD v37; // eax
  unsigned __int64 v38; // rcx
  int v39; // eax
  unsigned __int64 v40; // r10
  __int64 v41; // rdx
  int v42; // r9d
  __int64 v43; // rcx
  unsigned __int64 v44; // rcx
  __int64 v45; // rcx
  unsigned __int64 v46; // rcx
  int v47; // eax
  int v48; // eax
  HKEY lpData; // rax
  WCHAR *v50; // r8
  __int64 v51; // rdx
  DWORD v52; // ecx
  int v53; // eax
  __int64 v54; // rcx
  unsigned __int64 v55; // rcx
  DWORD v56; // eax
  unsigned __int64 v57; // rcx
  unsigned __int64 v58; // rcx
  DWORD v59; // eax
  bool v60; // zf
  bool v61; // zf
  unsigned __int64 v62; // rcx
  DWORD cbData; // [rsp+40h] [rbp-31h] BYREF
  DWORD Type; // [rsp+44h] [rbp-2Dh] BYREF
  DWORD v65; // [rsp+48h] [rbp-29h] BYREF
  HKEY phkResult; // [rsp+50h] [rbp-21h] BYREF
  LPWSTR lpDst; // [rsp+58h] [rbp-19h]
  LPCWSTR lpValueName; // [rsp+60h] [rbp-11h]
  DWORD Size; // [rsp+68h] [rbp-9h]
  DWORD Size_4; // [rsp+6Ch] [rbp-5h] BYREF
  DWORD v71[2]; // [rsp+70h] [rbp-1h] BYREF

  v8 = 0;
  v9 = pszValue;
  lpValueName = pszValue;
  if ( pvData && pcbData )
  {
    Size = *pcbData;
    v8 = 0;
  }
  else
  {
    Size = 0;
  }
  if ( hkey
    && (_WORD)srrfFlags
    && ((unsigned __int16)srrfFlags == 0xFFFF || (srrfFlags & 4) == 0 || (srrfFlags & 0x10000000) != 0)
    && (!pvData || pcbData) )
  {
    if ( pszSubKey && *pszSubKey )
    {
      phkResult = 0;
      LastError = RegOpenKeyExW(hkey, pszSubKey, 0, 1u, &phkResult);
      if ( LastError )
        goto LABEL_27;
      v15 = phkResult;
      lpDst = (LPWSTR)phkResult;
      if ( (srrfFlags & 0x70000) != 0 )
      {
        Type = LastError;
        GetOsSafeBootMode(&Type);
        if ( Type )
        {
          if ( Type == 1 )
          {
            v60 = (srrfFlags & 0x20000) == 0;
          }
          else
          {
            if ( Type != 2 )
            {
              LastError = 1003;
              goto LABEL_47;
            }
            v60 = (srrfFlags & 0x40000) == 0;
          }
          LastError = 31;
          if ( !v60 )
            LastError = 0;
        }
        else if ( (srrfFlags & 0x10000) == 0 )
        {
          LastError = 31;
          goto LABEL_47;
        }
        v15 = (HKEY)lpDst;
      }
      if ( !LastError )
      {
        v65 = 0;
        if ( pvData )
          v16 = *pcbData;
        else
          v16 = 0;
        Type = v16;
        cbData = v16;
        v17 = RegQueryValueExW(v15, lpValueName, 0, &v65, (LPBYTE)pvData, &cbData);
        LastError = v17;
        if ( !v17 || v17 == 234 )
        {
          v18 = v65;
          if ( v65 == 1 )
          {
            if ( v17 || !pvData )
            {
              v19 = cbData + 2;
              if ( cbData + 2 < cbData )
              {
                v19 = -1;
                LastError = 534;
              }
            }
            else
            {
              v40 = cbData;
              v41 = cbData >> 1;
              if ( !(_DWORD)v41 || *((_WORD *)pvData + (unsigned int)(v41 - 1)) )
              {
                v42 = 1;
                if ( (int)v41 + 1 <= Type >> 1 )
                  *((_WORD *)pvData + v41) = 0;
                else
                  LastError = 234;
              }
              else
              {
                v42 = 0;
              }
              v43 = (unsigned int)(v42 + v41);
              v19 = v40;
              v44 = 2 * v43;
              if ( v40 <= v44 )
                v19 = v44;
            }
LABEL_41:
            if ( LastError && LastError != 234 )
              goto LABEL_43;
            switch ( v18 )
            {
              case 1u:
                v39 = LastError;
                if ( (srrfFlags & 2) == 0 )
                  v39 = 1630;
                LastError = v39;
                goto LABEL_43;
              case 4u:
                if ( (srrfFlags & 0x10) == 0 )
                  LastError = 1630;
                goto LABEL_43;
              case 0u:
                if ( (srrfFlags & 1) == 0 )
                  LastError = 1630;
                goto LABEL_43;
              case 2u:
                if ( (srrfFlags & 4) == 0 )
                  LastError = 1630;
                goto LABEL_43;
              case 3u:
                if ( (srrfFlags & 8) != 0 )
                {
                  if ( (unsigned __int16)srrfFlags == 72 )
                  {
                    if ( v19 > 8 )
                      LastError = 1629;
                  }
                  else if ( (unsigned __int16)srrfFlags == 24 && v19 > 4 )
                  {
                    LastError = 1629;
                  }
                  goto LABEL_43;
                }
                break;
              case 7u:
                if ( (srrfFlags & 0x20) == 0 )
                  LastError = 1630;
                goto LABEL_43;
              case 0xBu:
                if ( (srrfFlags & 0x40) == 0 )
                  LastError = 1630;
                goto LABEL_43;
              default:
                if ( (unsigned __int16)srrfFlags == 0xFFFF )
                {
LABEL_43:
                  if ( pdwType )
                    *pdwType = v18;
                  if ( pcbData )
                    *pcbData = v19;
                  goto LABEL_47;
                }
                break;
            }
            LastError = 1630;
            goto LABEL_43;
          }
          if ( v65 == 2 )
          {
            if ( (srrfFlags & 0x10000000) != 0 )
            {
              v53 = NullTerminateRegSzStringW(pvData, &cbData, Type, v17);
              v18 = v65;
              LastError = v53;
            }
            else
            {
              LastError = NullTerminateRegExpandSzStringW((HKEY)lpDst, (__int64)&cbData, Type, v17);
              v18 = 1;
            }
            goto LABEL_40;
          }
          if ( v65 != 7 )
          {
LABEL_40:
            v19 = cbData;
            goto LABEL_41;
          }
          LastError = NullTerminateRegMultiSzStringW(pvData, &cbData, Type, v17);
        }
        v18 = v65;
        goto LABEL_40;
      }
LABEL_47:
      RegCloseKey(phkResult);
      goto LABEL_26;
    }
    LastError = 0;
    if ( (srrfFlags & 0x70000) != 0 )
    {
      Type = 0;
      GetOsSafeBootMode(&Type);
      if ( Type )
      {
        if ( Type == 1 )
        {
          v61 = (srrfFlags & 0x20000) == 0;
        }
        else
        {
          if ( Type != 2 )
          {
            LastError = 1003;
            goto LABEL_26;
          }
          v61 = (srrfFlags & 0x40000) == 0;
        }
        LastError = 31;
        v8 = 0;
        if ( !v61 )
          LastError = 0;
      }
      else
      {
        if ( (srrfFlags & 0x10000) == 0 )
        {
          LastError = 31;
          goto LABEL_26;
        }
        v8 = 0;
      }
      v9 = lpValueName;
    }
    if ( LastError )
      goto LABEL_27;
    Type = 0;
    if ( pvData )
      v8 = *pcbData;
    v65 = v8;
    cbData = v8;
    v12 = RegQueryValueExW(hkey, v9, 0, &Type, (LPBYTE)pvData, &cbData);
    LastError = v12;
    if ( v12 && v12 != 234 )
    {
      v13 = Type;
      goto LABEL_20;
    }
    v13 = Type;
    if ( Type == 1 )
    {
      if ( v12 || !pvData )
      {
        if ( cbData + 2 >= cbData )
        {
          cbData += 2;
        }
        else
        {
          cbData = -1;
          LastError = 534;
        }
      }
      else
      {
        v21 = cbData;
        v22 = cbData >> 1;
        if ( !(_DWORD)v22 || *((_WORD *)pvData + (unsigned int)(v22 - 1)) )
        {
          v23 = 1;
          if ( (int)v22 + 1 <= v65 >> 1 )
            *((_WORD *)pvData + v22) = 0;
          else
            LastError = 234;
        }
        else
        {
          v23 = 0;
        }
        v24 = v21;
        if ( v21 <= 2 * (unsigned __int64)(unsigned int)(v23 + v22) )
          v24 = 2 * (v23 + v22);
        cbData = v24;
      }
LABEL_20:
      if ( LastError && LastError != 234 )
        goto LABEL_22;
      switch ( v13 )
      {
        case 1u:
          v20 = LastError;
          if ( (srrfFlags & 2) == 0 )
            v20 = 1630;
          LastError = v20;
          goto LABEL_22;
        case 4u:
          if ( (srrfFlags & 0x10) == 0 )
            LastError = 1630;
          goto LABEL_22;
        case 0u:
          if ( (srrfFlags & 1) == 0 )
            LastError = 1630;
          goto LABEL_22;
        case 2u:
          if ( (srrfFlags & 4) == 0 )
            LastError = 1630;
          goto LABEL_22;
        case 3u:
          if ( (srrfFlags & 8) != 0 )
          {
            if ( (unsigned __int16)srrfFlags == 72 )
            {
              if ( cbData > 8 )
                LastError = 1629;
            }
            else if ( (unsigned __int16)srrfFlags == 24 && cbData > 4 )
            {
              LastError = 1629;
            }
            goto LABEL_22;
          }
          break;
        case 7u:
          if ( (srrfFlags & 0x20) == 0 )
            LastError = 1630;
          goto LABEL_22;
        case 0xBu:
          if ( (srrfFlags & 0x40) == 0 )
            LastError = 1630;
          goto LABEL_22;
        default:
          if ( (unsigned __int16)srrfFlags == 0xFFFF )
          {
LABEL_22:
            if ( pdwType )
              *pdwType = v13;
            if ( pcbData )
              *pcbData = cbData;
LABEL_26:
            if ( !LastError )
              return LastError;
            goto LABEL_27;
          }
          break;
      }
      LastError = 1630;
      goto LABEL_22;
    }
    if ( Type != 2 )
    {
      if ( Type == 7 )
      {
        v47 = NullTerminateRegMultiSzStringW(pvData, &cbData, v65, v12);
        v13 = Type;
        LastError = v47;
      }
      goto LABEL_20;
    }
    if ( (srrfFlags & 0x10000000) != 0 )
    {
      v48 = NullTerminateRegSzStringW(pvData, &cbData, v65, v12);
      v13 = Type;
      LastError = v48;
      goto LABEL_20;
    }
    if ( pvData )
    {
      v25 = cbData;
      v26 = cbData >> 1;
      if ( (_DWORD)v26 && !*((_WORD *)pvData + (unsigned int)(v26 - 1)) )
      {
        v27 = v65;
        v28 = cbData;
        v29 = 2LL * (unsigned int)v26;
        if ( cbData <= v29 )
          v28 = (unsigned int)v29;
        phkResult = (HKEY)v28;
        v30 = v28;
        LODWORD(v31) = v28;
LABEL_78:
        cbData = v30;
        v32 = (WCHAR *)pvData;
        Size_4 = v27;
        goto LABEL_79;
      }
      v27 = v65;
      v45 = (unsigned int)(v26 + 1);
      if ( (int)v26 + 1 <= v65 >> 1 )
      {
        v57 = 2 * v45;
        *((_WORD *)pvData + v26) = 0;
        v30 = v25;
        if ( v25 <= v57 )
          v30 = v57;
        LODWORD(v31) = v30;
        phkResult = (HKEY)v30;
        goto LABEL_78;
      }
      v46 = 2 * v45;
      v31 = cbData;
      LastError = 234;
      if ( cbData <= v46 )
        v31 = (unsigned int)v46;
      v27 = 0;
      Size_4 = 0;
      v32 = (WCHAR *)pvData;
      cbData = v31;
      phkResult = (HKEY)v31;
    }
    else
    {
      v27 = 0;
      Size_4 = 0;
      phkResult = (HKEY)(cbData + 2);
      LODWORD(v31) = cbData + 2;
      v32 = 0;
    }
LABEL_79:
    lpDst = v32;
    if ( !(_DWORD)v31 )
    {
      v33 = Size_4;
      if ( Size_4 )
      {
        LODWORD(v34) = (_DWORD)phkResult;
LABEL_82:
        v35 = StrDupW(v32);
        lpValueName = v35;
        if ( v35 )
        {
          v36 = v33 >> 1;
          v37 = ExpandEnvironmentStringsW(v35, lpDst, v36);
          v71[0] = v37;
          if ( v37 )
            LastError = v36 < v37 ? 0xEA : 0;
          else
            LastError = GetLastError();
          LocalFree((HLOCAL)lpValueName);
          v38 = 2LL * v71[0];
          if ( v38 <= (unsigned int)phkResult )
            LODWORD(v38) = (_DWORD)phkResult;
          cbData = v38;
          if ( LastError || (unsigned int)v38 <= v65 || !pvData )
          {
            if ( LastError == 234 && !pvData )
              LastError = 0;
          }
          else
          {
            LastError = 234;
          }
        }
        else
        {
          v62 = 2 * ((unsigned __int64)(unsigned int)v34 >> 1);
          if ( v62 <= (unsigned int)v34 )
            LODWORD(v62) = (_DWORD)v34;
          LastError = 14;
          cbData = v62;
        }
        if ( lpDst != pvData )
          LocalFree(lpDst);
      }
LABEL_91:
      v13 = 1;
      goto LABEL_20;
    }
    LODWORD(v34) = (_DWORD)phkResult;
    if ( v27 )
    {
      v33 = Size_4;
      goto LABEL_82;
    }
    *(_QWORD *)v71 = (unsigned int)phkResult;
    Size_4 = (unsigned int)phkResult;
    lpData = (HKEY)LocalAlloc(0x40u, (unsigned int)phkResult);
    phkResult = lpData;
    if ( !lpData )
    {
      LastError = GetLastError();
      v13 = 1;
      goto LABEL_20;
    }
    if ( lpDst )
    {
      memcpy_0(lpData, lpDst, *(_QWORD *)v71 - 2LL);
      v52 = Size_4;
      v50 = (WCHAR *)phkResult;
    }
    else
    {
      v71[0] = 0;
      if ( RegQueryValueExW(hkey, lpValueName, 0, v71, (LPBYTE)lpData, &Size_4) || v71[0] != Type )
      {
        LastError = 1003;
        LocalFree(phkResult);
        goto LABEL_91;
      }
      v50 = (WCHAR *)phkResult;
      v51 = Size_4 >> 1;
      if ( !(_DWORD)v51 || *((_WORD *)phkResult + (unsigned int)(v51 - 1)) )
      {
        v54 = (unsigned int)(v51 + 1);
        if ( (int)v51 + 1 > (unsigned int)v34 >> 1 )
        {
          v55 = 2 * v54;
          v56 = Size_4;
          LastError = 1003;
          if ( Size_4 <= v55 )
            v56 = v55;
          Size_4 = v56;
          LocalFree(phkResult);
          goto LABEL_91;
        }
        v58 = 2 * v54;
        *((_WORD *)phkResult + v51) = 0;
        v59 = Size_4;
        if ( Size_4 <= v58 )
          v59 = v58;
        v52 = v59;
        Size_4 = v59;
      }
      else
      {
        v52 = Size_4;
        if ( Size_4 <= 2 * (unsigned __int64)(unsigned int)v51 )
          v52 = 2 * v51;
        Size_4 = v52;
      }
    }
    v33 = (unsigned int)v34;
    v34 = (HKEY)v52;
    v32 = v50;
    phkResult = v34;
    lpDst = v50;
    goto LABEL_82;
  }
  LastError = 87;
LABEL_27:
  if ( (srrfFlags & 0x20000000) != 0 && Size && pvData )
    memset_0(pvData, 0, Size);
  return LastError;
}

```

## disassembly

```asm
0x180005da0  push    rbp
0x180005da2  push    rdi
0x180005da3  push    r12
0x180005da5  push    r13
0x180005da7  push    r14
0x180005da9  push    r15
0x180005dab  lea     rbp, [rsp-17h]
0x180005db0  sub     rsp, 88h
0x180005db7  mov     rax, cs:__security_cookie
0x180005dbe  xor     rax, rsp
0x180005dc1  mov     [rbp+3Fh+var_38], rax
0x180005dc5  mov     r14, [rbp+3Fh+pvData]
0x180005dc9  mov     r15, rcx
0x180005dcc  mov     r13, [rbp+3Fh+pdwType]
0x180005dd0  xor     ecx, ecx
0x180005dd2  mov     r12, [rbp+3Fh+pcbData]
0x180005dd6  mov     rax, r8
0x180005dd9  mov     [rbp+3Fh+lpValueName], rax
0x180005ddd  mov     edi, r9d
0x180005de0  test    r14, r14
0x180005de3  jnz     loc_180006003
0x180005de9  mov     dword ptr [rbp+3Fh+Size], ecx
0x180005dec  mov     [rsp+0B0h+arg_18], rbx
0x180005df4  mov     [rsp+0B0h+var_30], rsi
0x180005dfc  test    r15, r15
0x180005dff  jz      short loc_180005E1E
0x180005e01  movzx   esi, di
0x180005e04  test    esi, esi
0x180005e06  jz      short loc_180005E1E
0x180005e08  cmp     esi, 0FFFFh
0x180005e0e  jnz     loc_18000608B
0x180005e14  test    r14, r14
0x180005e17  jz      short loc_180005E28
0x180005e19  test    r12, r12
0x180005e1c  jnz     short loc_180005E28
0x180005e1e  mov     ebx, 57h ; 'W'
0x180005e23  jmp     loc_180005ED8
0x180005e28  test    rdx, rdx
0x180005e2b  jnz     loc_180005F12
0x180005e31  mov     ebx, ecx
0x180005e33  test    edi, 70000h
0x180005e39  jnz     loc_180006785
0x180005e3f  test    ebx, ebx
0x180005e41  jnz     loc_180005ED8
0x180005e47  mov     [rbp+3Fh+Type], ecx
0x180005e4a  test    r14, r14
0x180005e4d  jz      short loc_180005E53
0x180005e4f  mov     ecx, [r12]
0x180005e53  mov     [rbp+3Fh+var_68], ecx
0x180005e56  lea     r9, [rbp+3Fh+Type]; lpType
0x180005e5a  mov     [rbp+3Fh+cbData], ecx
0x180005e5d  xor     r8d, r8d; lpReserved
0x180005e60  lea     rcx, [rbp+3Fh+cbData]
0x180005e64  mov     rdx, rax; lpValueName
0x180005e67  mov     [rsp+0B0h+lpcbData], rcx; lpcbData
0x180005e6c  mov     rcx, r15; hKey
0x180005e6f  mov     [rsp+0B0h+lpData], r14; lpData
0x180005e74  call    cs:__imp_RegQueryValueExW
0x180005e7a  mov     ebx, eax
0x180005e7c  test    eax, eax
0x180005e7e  jz      short loc_180005E8B
0x180005e80  cmp     eax, 0EAh
0x180005e85  jnz     loc_180006038
0x180005e8b  mov     edx, [rbp+3Fh+Type]
0x180005e8e  mov     eax, edx
0x180005e90  sub     eax, 1
0x180005e93  jz      loc_180006040
0x180005e99  sub     eax, 1
0x180005e9c  jz      loc_1800060EC
0x180005ea2  cmp     eax, 5
0x180005ea5  jz      loc_1800063BF
0x180005eab  test    ebx, ebx
0x180005ead  jz      loc_18000601A
0x180005eb3  cmp     ebx, 0EAh
0x180005eb9  jz      loc_18000601A
0x180005ebf  test    r13, r13
0x180005ec2  jz      short loc_180005EC8
0x180005ec4  mov     [r13+0], edx
0x180005ec8  test    r12, r12
0x180005ecb  jz      short loc_180005ED4
0x180005ecd  mov     eax, [rbp+3Fh+cbData]
0x180005ed0  mov     [r12], eax
0x180005ed4  test    ebx, ebx
0x180005ed6  jz      short loc_180005EE2
0x180005ed8  bt      edi, 1Dh
0x180005edc  jb      loc_18000686E
0x180005ee2  mov     rsi, [rsp+0B0h+var_30]
0x180005eea  mov     eax, ebx
0x180005eec  mov     rbx, [rsp+0B0h+arg_18]
0x180005ef4  mov     rcx, [rbp+3Fh+var_38]
0x180005ef8  xor     rcx, rsp; StackCookie
0x180005efb  call    __security_check_cookie
0x180005f00  add     rsp, 88h
0x180005f07  pop     r15
0x180005f09  pop     r14
0x180005f0b  pop     r13
0x180005f0d  pop     r12
0x180005f0f  pop     rdi
0x180005f10  pop     rbp
0x180005f11  retn
0x180005f12  cmp     word ptr [rdx], 0
0x180005f16  jz      loc_180005E31
0x180005f1c  mov     [rbp+3Fh+phkResult], rcx
0x180005f20  lea     rax, [rbp+3Fh+phkResult]
0x180005f24  mov     rcx, r15; hKey
0x180005f27  mov     [rsp+0B0h+lpData], rax; phkResult
0x180005f2c  mov     r9d, 1; samDesired
0x180005f32  xor     r8d, r8d; ulOptions
0x180005f35  call    cs:__imp_RegOpenKeyExW
0x180005f3b  mov     ebx, eax
0x180005f3d  test    eax, eax
0x180005f3f  jnz     short loc_180005ED8
0x180005f41  mov     rax, [rbp+3Fh+phkResult]
0x180005f45  mov     [rbp+3Fh+lpDst], rax
0x180005f49  test    edi, 70000h
0x180005f4f  jnz     loc_1800066D2
0x180005f55  test    ebx, ebx
0x180005f57  jnz     loc_180005FF4
0x180005f5d  mov     [rbp+3Fh+var_68], ebx
0x180005f60  test    r14, r14
0x180005f63  jz      loc_18000622F
0x180005f69  mov     ecx, [r12]
0x180005f6d  mov     r15, [rbp+3Fh+lpValueName]
0x180005f71  lea     r9, [rbp+3Fh+var_68]; lpType
0x180005f75  mov     [rbp+3Fh+Type], ecx
0x180005f78  xor     r8d, r8d; lpReserved
0x180005f7b  mov     [rbp+3Fh+cbData], ecx
0x180005f7e  mov     rdx, r15; lpValueName
0x180005f81  lea     rcx, [rbp+3Fh+cbData]
0x180005f85  mov     [rsp+0B0h+lpcbData], rcx; lpcbData
0x180005f8a  mov     rcx, rax; hKey
0x180005f8d  mov     [rsp+0B0h+lpData], r14; lpData
0x180005f92  call    cs:__imp_RegQueryValueExW
0x180005f98  mov     ebx, eax
0x180005f9a  test    eax, eax
0x180005f9c  jz      short loc_180005FA9
0x180005f9e  cmp     eax, 0EAh
0x180005fa3  jnz     loc_180006226
0x180005fa9  mov     r8d, [rbp+3Fh+var_68]
0x180005fad  mov     eax, r8d
0x180005fb0  sub     eax, 1
0x180005fb3  jz      loc_180006236
0x180005fb9  sub     eax, 1
0x180005fbc  jz      loc_180006345
0x180005fc2  cmp     eax, 5
0x180005fc5  jz      loc_180006211
0x180005fcb  mov     edx, [rbp+3Fh+cbData]
0x180005fce  test    ebx, ebx
0x180005fd0  jz      loc_1800061F2
0x180005fd6  cmp     ebx, 0EAh
0x180005fdc  jz      loc_1800061F2
0x180005fe2  test    r13, r13
0x180005fe5  jz      short loc_180005FEB
0x180005fe7  mov     [r13+0], r8d
0x180005feb  test    r12, r12
0x180005fee  jz      short loc_180005FF4
0x180005ff0  mov     [r12], edx
0x180005ff4  mov     rcx, [rbp+3Fh+phkResult]; hKey
0x180005ff8  call    cs:__imp_RegCloseKey
0x180005ffe  jmp     loc_180005ED4
0x180006003  test    r12, r12
0x180006006  jz      loc_180005DE9
0x18000600c  mov     ecx, [r12]
0x180006010  mov     dword ptr [rbp+3Fh+Size], ecx
0x180006013  xor     ecx, ecx
0x180006015  jmp     loc_180005DEC
0x18000601a  cmp     edx, 1
0x18000601d  jnz     loc_1800060A4
0x180006023  mov     eax, ebx
0x180006025  test    dil, 2
0x180006029  mov     ebx, 65Eh
0x18000602e  cmovz   eax, ebx
0x180006031  mov     ebx, eax
0x180006033  jmp     loc_180005EBF
0x180006038  mov     edx, [rbp+3Fh+Type]
0x18000603b  jmp     loc_180005EAB
0x180006040  test    ebx, ebx
0x180006042  jnz     short loc_1800060C1
0x180006044  test    r14, r14
0x180006047  jz      loc_1800060CD
0x18000604d  mov     r10d, [rbp+3Fh+cbData]
0x180006051  mov     r8d, r10d
0x180006054  shr     r8d, 1
0x180006057  cmp     r8d, 1
0x18000605b  jb      loc_18000627F
0x180006061  lea     eax, [r8-1]
0x180006065  cmp     [r14+rax*2], bx
0x18000606a  jnz     loc_18000627F
0x180006070  xor     r9d, r9d
0x180006073  lea     ecx, [r9+r8]
0x180006077  mov     rax, r10
0x18000607a  add     rcx, rcx
0x18000607d  cmp     r10, rcx
0x180006080  cmovbe  eax, ecx
0x180006083  mov     [rbp+3Fh+cbData], eax
0x180006086  jmp     loc_180005EAB
0x18000608b  test    dil, 4
0x18000608f  jz      loc_180005E14
0x180006095  bt      edi, 1Ch
0x180006099  jnb     loc_180005E1E
0x18000609f  jmp     loc_180005E14
0x1800060a4  cmp     edx, 4
0x1800060a7  jnz     loc_1800063FC
0x1800060ad  test    dil, 10h
0x1800060b1  jnz     loc_180005EBF
0x1800060b7  mov     ebx, 65Eh
0x1800060bc  jmp     loc_180005EBF
0x1800060c1  cmp     ebx, 0EAh
0x1800060c7  jnz     loc_180005EAB
0x1800060cd  mov     eax, [rbp+3Fh+cbData]
0x1800060d0  lea     ecx, [rax+2]
0x1800060d3  cmp     ecx, eax
0x1800060d5  jnb     loc_18000680F
0x1800060db  mov     [rbp+3Fh+cbData], 0FFFFFFFFh
0x1800060e2  mov     ebx, 216h
0x1800060e7  jmp     loc_180005EAB
0x1800060ec  bt      edi, 1Ch
0x1800060f0  jb      loc_180006444
0x1800060f6  test    ebx, ebx
0x1800060f8  jnz     loc_1800062D1
0x1800060fe  test    r14, r14
0x180006101  jz      loc_1800062D1
0x180006107  mov     r9d, [rbp+3Fh+cbData]
0x18000610b  mov     r8d, r9d
0x18000610e  shr     r8d, 1
0x180006111  cmp     r8d, 1
0x180006115  jb      loc_180006383
0x18000611b  lea     eax, [r8-1]
0x18000611f  cmp     [r14+rax*2], bx
0x180006124  jnz     loc_180006383
0x18000612a  mov     edx, [rbp+3Fh+var_68]
0x18000612d  mov     ecx, r9d
0x180006130  mov     eax, r8d
0x180006133  add     rax, rax
0x180006136  cmp     r9, rax
0x180006139  cmovbe  ecx, eax
0x18000613c  mov     [rbp+3Fh+phkResult], rcx
0x180006140  mov     r8d, ecx
0x180006143  mov     eax, ecx
0x180006145  mov     [rbp+3Fh+cbData], r8d
0x180006149  mov     rcx, r14; pszSrch
0x18000614c  mov     dword ptr [rbp+3Fh+Size+4], edx
0x18000614f  mov     [rbp+3Fh+lpDst], rcx
0x180006153  test    eax, eax
0x180006155  jnz     loc_1800062BC
0x18000615b  mov     r15d, dword ptr [rbp+3Fh+Size+4]
0x18000615f  test    r15d, r15d
0x180006162  jz      loc_1800061E8
0x180006168  mov     rbx, [rbp+3Fh+phkResult]
0x18000616c  call    cs:__imp_StrDupW
0x180006172  mov     [rbp+3Fh+lpValueName], rax
0x180006176  test    rax, rax
0x180006179  jz      loc_1800067F2
0x18000617f  mov     rdx, [rbp+3Fh+lpDst]; lpDst
0x180006183  mov     rcx, rax; lpSrc
0x180006186  shr     r15d, 1
0x180006189  mov     r8d, r15d; nSize
0x18000618c  call    cs:__imp_ExpandEnvironmentStringsW
0x180006192  mov     [rbp+3Fh+var_40], eax
0x180006195  test    eax, eax
0x180006197  jz      loc_180006338
0x18000619d  cmp     r15d, eax
0x1800061a0  sbb     ebx, ebx
0x1800061a2  and     ebx, 0EAh
0x1800061a8  mov     rcx, [rbp+3Fh+lpValueName]; hMem
0x1800061ac  call    cs:__imp_LocalFree
0x1800061b2  mov     rdx, [rbp+3Fh+phkResult]
0x1800061b6  mov     ecx, [rbp+3Fh+var_40]
0x1800061b9  add     rcx, rcx
0x1800061bc  mov     eax, edx
0x1800061be  cmp     rcx, rax
0x1800061c1  cmovbe  ecx, edx
0x1800061c4  mov     [rbp+3Fh+cbData], ecx
0x1800061c7  test    ebx, ebx
0x1800061c9  jz      loc_1800062A0
0x1800061cf  cmp     ebx, 0EAh
0x1800061d5  jz      loc_1800067E5
0x1800061db  mov     rax, [rbp+3Fh+lpDst]
0x1800061df  cmp     rax, r14
0x1800061e2  jnz     loc_180006461
0x1800061e8  mov     edx, 1
0x1800061ed  jmp     loc_180005EAB
0x1800061f2  cmp     r8d, 1
0x1800061f6  jnz     loc_1800062F1
0x1800061fc  mov     eax, ebx
0x1800061fe  test    dil, 2
0x180006202  mov     ebx, 65Eh
0x180006207  cmovz   eax, ebx
0x18000620a  mov     ebx, eax
0x18000620c  jmp     loc_180005FE2
0x180006211  mov     r8d, [rbp+3Fh+Type]
0x180006215  lea     rdx, [rbp+3Fh+cbData]
0x180006219  mov     r9d, ebx
0x18000621c  mov     rcx, r14
0x18000621f  call    NullTerminateRegMultiSzStringW
0x180006224  mov     ebx, eax
0x180006226  mov     r8d, [rbp+3Fh+var_68]
0x18000622a  jmp     loc_180005FCB
0x18000622f  xor     ecx, ecx
0x180006231  jmp     loc_180005F6D
  ... truncated ...
```
