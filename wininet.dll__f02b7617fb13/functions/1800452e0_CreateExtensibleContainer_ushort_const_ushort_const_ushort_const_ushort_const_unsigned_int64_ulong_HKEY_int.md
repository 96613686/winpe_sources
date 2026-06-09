# CreateExtensibleContainer(ushort const *,ushort const *,ushort const *,ushort const *,unsigned __int64,ulong,HKEY__ *,int *)

- ea: `0x1800452e0`
- end: `0x180045c7b`
- name: `?CreateExtensibleContainer@@YAJPEBG000_KKPEAUHKEY__@@PEAH@Z`
- size: `2459`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, unsigned __int64, BYTE Data, HKEY, int *)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, installer_update`

## callers

- `0x18012ea30`

## callees

- `0x180020468`
- `0x18002086c`
- `0x180025910`
- `0x1800452e0`
- `0x180046a1c`
- `0x1800a85a8`
- `0x180110154`
- `0x180132988`
- `0x18014a7a0`
- `0x18014b3b4`
- `0x1801e1790`
- `0x1801e5f64`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18004570e`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180045753`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180045b22`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180045b70`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180045b81`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180045b92`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18004570e`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180045753`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180045b22`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180045b70`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180045b81`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180045b92`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18004544b`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18004573b`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18004544b`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18004573b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180045878`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180045878`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180045496`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180045496`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x180045aba`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x180045aba`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180045561`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800455e4`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18004566c`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800456b3`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800456fa`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180045561`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800455e4`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18004566c`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800456b3`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800456fa`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800454dd`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800454dd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180045812`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180045aa6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180045812`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180045aa6`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180045a48`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180045a85`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180045aeb`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180045a48`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180045a85`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180045aeb`
- `RPCRT4!RpcRevertToSelf` at `0x180045824`
- `RPCRT4!RpcRevertToSelf` at `0x180045824`

## string_xrefs

- `0x1800455ba`: `CachePath`
- `0x1800459e6`: `CachePath`
- `0x18004553a`: `CachePrefix`
- `0x1800459c8`: `CachePrefix`
- `0x1800456d2`: `CacheOptions`
- `0x180045a31`: `CacheOptions`
- `0x180045644`: `CacheRelativePath`
- `0x180045a07`: `CacheRelativePath`
- `0x18004568b`: `CacheLimit`
- `0x180045ad9`: `CacheLimit`
- `0x180045a73`: `CacheRepair`

## pseudocode

```c
__int64 __fastcall CreateExtensibleContainer(
        const unsigned __int16 *a1,
        BYTE *a2,
        BYTE *a3,
        const unsigned __int16 *a4,
        unsigned __int64 a5,
        int Data,
        HKEY a7,
        int *a8)
{
  int v11; // ebx
  BYTE *v12; // r12
  const WCHAR *v13; // r13
  __int64 v14; // rsi
  signed int v15; // edi
  const unsigned __int16 *v16; // rdx
  BYTE *v17; // r14
  int v18; // esi
  __int64 v19; // rdi
  const WCHAR *v20; // r15
  int i; // edx
  LSTATUS v22; // eax
  LSTATUS ValueW; // eax
  const WCHAR *v24; // r13
  LSTATUS v25; // eax
  HKEY v26; // r15
  LSTATUS v27; // eax
  LSTATUS v28; // eax
  LSTATUS v29; // eax
  __int64 v30; // r8
  int v31; // esi
  unsigned __int16 v33; // dx
  __int64 v34; // rax
  const WCHAR *v35; // r15
  HKEY v36; // r13
  int v37; // r9d
  int v38; // r9d
  int v39; // r9d
  LSTATUS v40; // eax
  LSTATUS v41; // eax
  LSTATUS v42; // eax
  int v43; // [rsp+50h] [rbp-B0h]
  int v44; // [rsp+58h] [rbp-A8h] BYREF
  int v45; // [rsp+5Ch] [rbp-A4h]
  HKEY hKey; // [rsp+60h] [rbp-A0h]
  const WCHAR *v47; // [rsp+68h] [rbp-98h] BYREF
  __int64 v48; // [rsp+70h] [rbp-90h]
  const WCHAR *v49; // [rsp+78h] [rbp-88h] BYREF
  __int64 v50; // [rsp+80h] [rbp-80h]
  LPCWSTR v51; // [rsp+88h] [rbp-78h]
  BYTE *lpData; // [rsp+90h] [rbp-70h]
  BYTE *v53; // [rsp+98h] [rbp-68h]
  const WCHAR *v54; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v55; // [rsp+A8h] [rbp-58h]
  const WCHAR *v56; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v57; // [rsp+B8h] [rbp-48h]
  LPCWSTR lpSubKey; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v59; // [rsp+C8h] [rbp-38h]
  int *v60; // [rsp+D0h] [rbp-30h]
  DWORD cchName; // [rsp+D8h] [rbp-28h] BYREF
  HKEY v62; // [rsp+E0h] [rbp-20h] BYREF
  BYTE v63[4]; // [rsp+E8h] [rbp-18h] BYREF
  int pvData; // [rsp+ECh] [rbp-14h] BYREF
  int v65; // [rsp+F0h] [rbp-10h] BYREF
  BYTE v66[12]; // [rsp+F4h] [rbp-Ch] BYREF
  WCHAR Name[264]; // [rsp+100h] [rbp+0h] BYREF

  hKey = a7;
  v60 = a8;
  v53 = a3;
  v11 = 0;
  lpData = a2;
  v51 = a1;
  v45 = 0;
  v43 = 0;
  v62 = 0;
  memset_0(Name, 0, 0x208u);
  v12 = (BYTE *)&::Data;
  v50 = 0;
  v13 = &::Data;
  v59 = 0;
  v48 = 0;
  v57 = 0;
  v55 = 0;
  pvData = 0;
  v65 = 0;
  *(_DWORD *)v66 = 0;
  *(_DWORD *)v63 = 0;
  cchName = 0;
  v49 = &::Data;
  lpSubKey = &::Data;
  v47 = &::Data;
  v56 = &::Data;
  v54 = &::Data;
  if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
    WPP_SF_SSSSidq(
      0,
      10,
      (unsigned int)WPP_1af76d9ad7163b4b1c76b77142f1718e_Traceguids,
      (_DWORD)v51,
      (__int64)a2,
      (__int64)a3,
      (__int64)a4,
      a5,
      Data,
      (__int64)v60);
  if ( v60 )
    *v60 = 0;
  if ( !v51 || !*v51 )
  {
    v45 = 72;
    goto LABEL_80;
  }
  if ( !a2 || !*(_WORD *)a2 )
  {
    v45 = 73;
LABEL_80:
    v15 = -2147024809;
    v31 = 0;
    goto LABEL_65;
  }
  if ( !a3 || !*(_WORD *)a3 )
  {
    v45 = 74;
    goto LABEL_80;
  }
  v14 = -1;
  do
    ++v14;
  while ( a4[v14] );
  v45 = 0;
  v44 = 0;
  v15 = WxRpcImpersonateNonElevatedCaller(&v44);
  if ( v15 < 0 )
  {
    v31 = 0;
    v45 = 82;
    goto LABEL_65;
  }
  v11 = v44;
  v15 = WxValidateCacheDirectory((const unsigned __int16 *)v53);
  if ( v15 < 0 )
  {
    v45 = 88;
    goto LABEL_64;
  }
  v16 = a4;
  v17 = v53;
  if ( (unsigned int)_o__wcsnicmp(v53, v16, (unsigned int)v14) )
  {
    v18 = v50;
  }
  else
  {
    v15 = CWxString::Set((CWxString *)&v49, (const unsigned __int16 *)&v17[2 * (unsigned int)v14]);
    if ( v15 < 0 )
    {
      v45 = 96;
      goto LABEL_64;
    }
    CWxString::UnLeading((CWxString *)&v49, v33);
    v18 = v50;
    v12 = (BYTE *)v49;
    if ( (_DWORD)v50 )
    {
      v34 = (unsigned int)(v50 - 1);
      if ( v49[v34] == 92 && (unsigned int)v34 <= HIDWORD(v50) )
      {
        v18 = v50 - 1;
        LODWORD(v50) = v50 - 1;
        v49[v34] = 0;
      }
    }
  }
  v19 = -1;
  do
    ++v19;
  while ( *(_WORD *)&lpData[2 * v19] );
  v53 = (BYTE *)v19;
  *(_DWORD *)v63 = a5 >> 10;
  v43 = 1;
  if ( !*(_DWORD *)v63 )
    *(_DWORD *)v63 = 1;
  AcquireSRWLockExclusive(&g_srwExtensibleContainerConfig);
  v20 = v56;
  for ( i = 0; ; i = v44 + 1 )
  {
    v44 = i;
    if ( (_DWORD)v59 )
    {
      LODWORD(v59) = 0;
      *lpSubKey = 0;
    }
    cchName = 260;
    v22 = RegEnumKeyExW(hKey, i, Name, &cchName, 0, 0, 0, 0);
    v15 = v22;
    if ( v22 == 259 )
    {
      v35 = v51;
      v36 = hKey;
      v15 = WxOpenRegistryKey(hKey, v51, 0xFu, 1, &v62);
      if ( v15 < 0 )
      {
        v45 = 263;
        goto LABEL_64;
      }
      v15 = WxSetRegistryString(v62, L"CachePrefix", lpData, v37);
      if ( v15 < 0 )
      {
        v45 = 270;
      }
      else
      {
        v15 = WxSetRegistryString(v62, L"CachePath", v17, v38);
        if ( v15 < 0 )
        {
          v45 = 271;
        }
        else if ( v18 && (v15 = WxSetRegistryString(v62, L"CacheRelativePath", v12, v39), v15 < 0) )
        {
          v45 = 274;
        }
        else
        {
          v40 = RegSetValueExW(v62, L"CacheOptions", 0, 4u, (const BYTE *)&Data, 4u);
          v15 = v40;
          if ( v40 > 0 )
            v15 = (unsigned __int16)v40 | 0x80070000;
          if ( v15 < 0 )
          {
            v45 = 276;
          }
          else
          {
            v41 = RegSetValueExW(v62, L"CacheRepair", 0, 4u, v66, 4u);
            v15 = v41;
            if ( v41 > 0 )
              v15 = (unsigned __int16)v41 | 0x80070000;
            if ( v15 >= 0 )
            {
              v42 = RegSetValueExW(v62, L"CacheLimit", 0, 4u, v63, 4u);
              v15 = v42;
              if ( v42 > 0 )
                v15 = (unsigned __int16)v42 | 0x80070000;
              if ( v15 >= 0 )
                goto LABEL_64;
              v45 = 278;
            }
            else
            {
              v45 = 277;
            }
          }
        }
      }
      if ( v62 )
      {
        RegCloseKey(v62);
        v62 = 0;
      }
      RegDeleteTreeW(v36, v35);
      goto LABEL_64;
    }
    if ( v22 > 0 )
      v15 = (unsigned __int16)v22 | 0x80070000;
    if ( v15 < 0 )
    {
      v45 = 137;
      goto LABEL_64;
    }
    v15 = CWxString::Set((CWxString *)&lpSubKey, Name);
    if ( v15 < 0 )
    {
      v45 = 138;
      goto LABEL_64;
    }
    if ( (_DWORD)v48 )
    {
      LODWORD(v48) = 0;
      *v13 = 0;
    }
    cchName = 520;
    ValueW = RegGetValueW(hKey, lpSubKey, L"CachePrefix", 2u, 0, Name, &cchName);
    v15 = ValueW;
    if ( ValueW != 2 )
      break;
LABEL_54:
    ;
  }
  if ( ValueW > 0 )
    v15 = (unsigned __int16)ValueW | 0x80070000;
  if ( v15 < 0 )
  {
    v45 = 151;
    goto LABEL_64;
  }
  v15 = CWxString::Set((CWxString *)&v47, Name);
  if ( v15 < 0 )
  {
    v45 = 152;
    goto LABEL_64;
  }
  if ( (_DWORD)v57 )
  {
    LODWORD(v57) = 0;
    *v20 = 0;
  }
  v24 = lpSubKey;
  cchName = 520;
  v25 = RegGetValueW(hKey, lpSubKey, L"CachePath", 2u, 0, Name, &cchName);
  v15 = v25;
  if ( v25 == 2 )
  {
    v13 = v47;
    goto LABEL_54;
  }
  if ( v25 > 0 )
    v15 = (unsigned __int16)v25 | 0x80070000;
  if ( v15 < 0 )
  {
    v45 = 165;
    goto LABEL_64;
  }
  v15 = CWxString::Set((CWxString *)&v56, Name);
  if ( v15 < 0 )
  {
    v45 = 166;
    goto LABEL_64;
  }
  if ( (_DWORD)v55 )
  {
    LODWORD(v55) = 0;
    *v54 = 0;
  }
  v26 = hKey;
  cchName = 520;
  v27 = RegGetValueW(hKey, v24, L"CacheRelativePath", 2u, 0, Name, &cchName);
  v15 = v27;
  if ( v27 != 2 )
  {
    if ( v27 > 0 )
      v15 = (unsigned __int16)v27 | 0x80070000;
    if ( v15 < 0 )
    {
      v45 = 177;
      goto LABEL_64;
    }
    v15 = CWxString::Set((CWxString *)&v54, Name);
    if ( v15 < 0 )
    {
      v45 = 178;
      goto LABEL_64;
    }
  }
  pvData = 0;
  cchName = 4;
  v28 = RegGetValueW(v26, v24, L"CacheLimit", 0x18u, 0, &pvData, &cchName);
  v15 = v28;
  if ( v28 != 2 )
  {
    if ( v28 > 0 )
      v15 = (unsigned __int16)v28 | 0x80070000;
    if ( v15 < 0 )
    {
      v45 = 190;
      goto LABEL_64;
    }
  }
  v65 = 0;
  cchName = 4;
  v29 = RegGetValueW(v26, v24, L"CacheOptions", 0x18u, 0, &v65, &cchName);
  v15 = v29;
  if ( v29 != 2 )
  {
    if ( v29 > 0 )
      v15 = (unsigned __int16)v29 | 0x80070000;
    if ( v15 < 0 )
    {
      v45 = 202;
      goto LABEL_64;
    }
  }
  v15 = 0;
  if ( (unsigned int)_o__wcsicmp(v24) )
  {
    v30 = (unsigned int)v53;
    v13 = v47;
    if ( (unsigned int)v53 >= (unsigned int)v48 )
      v30 = (unsigned int)v48;
    if ( !(unsigned int)_o__wcsnicmp(v47, lpData, v30) )
    {
      v15 = -2147024713;
      v45 = 236;
      goto LABEL_64;
    }
    v20 = v56;
    if ( !(unsigned int)_o__wcsicmp(v56) )
    {
      v15 = -2147024713;
      v45 = 245;
      goto LABEL_64;
    }
    if ( v18 && !(unsigned int)_o__wcsicmp(v54) )
    {
      v15 = -2147024713;
      v45 = 255;
      goto LABEL_64;
    }
    goto LABEL_54;
  }
  if ( !(unsigned int)_o__wcsicmp(v47)
    && !(unsigned int)_o__wcsicmp(v56)
    && !(unsigned int)_o__wcsicmp(v54)
    && pvData == *(_DWORD *)v63
    && v65 == Data )
  {
    v31 = 1;
    *v60 = 1;
    goto LABEL_65;
  }
  v15 = -2147024713;
  v45 = 227;
LABEL_64:
  v31 = v43;
LABEL_65:
  if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
    WPP_SF_d(1036, 11, WPP_1af76d9ad7163b4b1c76b77142f1718e_Traceguids, (unsigned int)v15);
  CWxString::_Release((CWxString *)&v54);
  CWxString::_Release((CWxString *)&v56);
  CWxString::_Release((CWxString *)&v47);
  CWxString::_Release((CWxString *)&lpSubKey);
  CWxString::_Release((CWxString *)&v49);
  if ( v62 )
  {
    RegCloseKey(v62);
    v62 = 0;
  }
  if ( v11 )
    RpcRevertToSelf();
  if ( v31 )
    ReleaseSRWLockExclusive(&g_srwExtensibleContainerConfig);
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x1800452e0  push    rbp
0x1800452e2  push    rbx
0x1800452e3  push    rsi
0x1800452e4  push    rdi
0x1800452e5  push    r12
0x1800452e7  push    r13
0x1800452e9  push    r14
0x1800452eb  push    r15
0x1800452ed  lea     rbp, [rsp-228h]
0x1800452f5  sub     rsp, 328h
0x1800452fc  mov     rax, cs:__security_cookie
0x180045303  xor     rax, rsp
0x180045306  mov     [rbp+260h+var_50], rax
0x18004530d  mov     rax, [rbp+260h+arg_30]
0x180045314  mov     rdi, r8
0x180045317  mov     [rsp+360h+hKey], rax
0x18004531c  mov     rsi, rdx
0x18004531f  mov     rax, [rbp+260h+arg_38]
0x180045326  mov     r14, r9
0x180045329  mov     [rbp+260h+var_290], rax
0x18004532d  xor     eax, eax
0x18004532f  mov     [rbp+260h+var_2C8], r8
0x180045333  mov     ebx, eax
0x180045335  mov     [rbp+260h+lpData], rdx
0x180045339  mov     r8d, 208h; Size
0x18004533f  mov     [rbp+260h+var_2D8], rcx
0x180045343  xor     edx, edx; Val
0x180045345  lea     rcx, [rbp+260h+Name]; void *
0x180045349  mov     [rsp+360h+var_304], eax
0x18004534d  mov     [rsp+360h+var_310], eax
0x180045351  mov     [rbp+260h+var_280], rax
0x180045355  call    memset_0
0x18004535a  xor     ecx, ecx
0x18004535c  lea     r12, Data
0x180045363  mov     [rbp+260h+var_2E0], rcx
0x180045367  mov     r13, r12
0x18004536a  mov     [rbp+260h+var_298], rcx
0x18004536e  mov     [rsp+360h+var_2F0], rcx
0x180045373  mov     [rbp+260h+var_2A8], rcx
0x180045377  mov     [rbp+260h+var_2B8], rcx
0x18004537b  mov     [rbp+260h+pvData], ecx
0x18004537e  mov     [rbp+260h+var_270], ecx
0x180045381  mov     dword ptr [rbp+260h+var_26C], ecx
0x180045384  mov     dword ptr [rbp+260h+var_278], ecx
0x180045387  mov     [rbp+260h+cchName], ecx
0x18004538a  mov     [rsp+360h+var_2E8], r12
0x18004538f  mov     [rbp+260h+lpSubKey], r12
0x180045393  mov     [rsp+360h+var_2F8], r12
0x180045398  mov     [rbp+260h+var_2B0], r12
0x18004539c  mov     [rbp+260h+var_2C0], r12
0x1800453a0  test    byte ptr cs:xmmword_180266B60+1, 10h
0x1800453a7  mov     r15, [rbp+260h+arg_20]
0x1800453ae  jnz     loc_1800458CD
0x1800453b4  mov     rax, [rbp+260h+var_290]
0x1800453b8  test    rax, rax
0x1800453bb  jz      short loc_1800453BF
0x1800453bd  mov     [rax], ecx
0x1800453bf  mov     rax, [rbp+260h+var_2D8]
0x1800453c3  test    rax, rax
0x1800453c6  jz      loc_180045C6E
0x1800453cc  cmp     [rax], cx
0x1800453cf  jz      loc_180045C6E
0x1800453d5  test    rsi, rsi
0x1800453d8  jz      loc_1800458B9
0x1800453de  cmp     [rsi], cx
0x1800453e1  jz      loc_1800458B9
0x1800453e7  test    rdi, rdi
0x1800453ea  jz      loc_180045C61
0x1800453f0  cmp     [rdi], cx
0x1800453f3  jz      loc_180045C61
0x1800453f9  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800453fd  inc     rsi
0x180045400  cmp     [r14+rsi*2], cx
0x180045405  jnz     short loc_1800453FD
0x180045407  mov     [rsp+360h+var_304], ecx
0x18004540b  mov     [rsp+360h+var_308], ecx
0x18004540f  lea     rcx, [rsp+360h+var_308]; int *
0x180045414  call    ?WxRpcImpersonateNonElevatedCaller@@YAJPEAH@Z; WxRpcImpersonateNonElevatedCaller(int *)
0x180045419  xor     ecx, ecx
0x18004541b  mov     edi, eax
0x18004541d  test    eax, eax
0x18004541f  js      loc_1800458A2
0x180045425  mov     rcx, [rbp+260h+var_2C8]; unsigned __int16 *
0x180045429  mov     ebx, [rsp+360h+var_308]
0x18004542d  call    ?WxValidateCacheDirectory@@YAJPEBG@Z; WxValidateCacheDirectory(ushort const *)
0x180045432  mov     edi, eax
0x180045434  test    eax, eax
0x180045436  js      loc_180045910
0x18004543c  mov     rdx, r14
0x18004543f  mov     r8d, esi
0x180045442  mov     r14, [rbp+260h+var_2C8]
0x180045446  mov     rcx, r14
0x180045449  mov     edi, esi
0x18004544b  call    cs:__imp__o__wcsnicmp
0x180045451  xor     edx, edx
0x180045453  test    eax, eax
0x180045455  jz      loc_18004592F
0x18004545b  mov     esi, dword ptr [rbp+260h+var_2E0]
0x18004545e  mov     rax, [rbp+260h+lpData]
0x180045462  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180045466  inc     rdi
0x180045469  cmp     [rax+rdi*2], dx
0x18004546d  jnz     short loc_180045466
0x18004546f  shr     r15, 0Ah
0x180045473  mov     eax, 1
0x180045478  mov     [rbp+260h+var_2C8], rdi
0x18004547c  xor     edi, edi
0x18004547e  mov     dword ptr [rbp+260h+var_278], r15d
0x180045482  mov     [rsp+360h+var_310], eax
0x180045486  test    r15d, r15d
0x180045489  jz      loc_18004598A
0x18004548f  lea     rcx, ?g_srwExtensibleContainerConfig@@3VWxSrw@@A; SRWLock
0x180045496  call    cs:__imp_AcquireSRWLockExclusive
0x18004549c  mov     r15, [rbp+260h+var_2B0]
0x1800454a0  mov     edx, edi; dwIndex
0x1800454a2  mov     [rsp+360h+var_308], edx
0x1800454a6  cmp     dword ptr [rbp+260h+var_298], edi
0x1800454a9  jz      short loc_1800454B5
0x1800454ab  mov     rcx, [rbp+260h+lpSubKey]
0x1800454af  mov     dword ptr [rbp+260h+var_298], edi
0x1800454b2  mov     [rcx], di
0x1800454b5  mov     rcx, [rsp+360h+hKey]; hKey
0x1800454ba  lea     r9, [rbp+260h+cchName]; lpcchName
0x1800454be  mov     [rsp+360h+lpftLastWriteTime], rdi; lpftLastWriteTime
0x1800454c3  lea     r8, [rbp+260h+Name]; lpName
0x1800454c7  mov     [rsp+360h+lpcchClass], rdi; lpcchClass
0x1800454cc  mov     [rsp+360h+lpClass], rdi; lpClass
0x1800454d1  mov     [rsp+360h+lpReserved], rdi; lpReserved
0x1800454d6  mov     [rbp+260h+cchName], 104h
0x1800454dd  call    cs:__imp_RegEnumKeyExW
0x1800454e3  mov     edi, eax
0x1800454e5  cmp     eax, 103h
0x1800454ea  jz      loc_180045992
0x1800454f0  test    eax, eax
0x1800454f2  jle     short loc_1800454FD
0x1800454f4  movzx   edi, ax
0x1800454f7  or      edi, 80070000h
0x1800454fd  test    edi, edi
0x1800454ff  js      loc_180045C13
0x180045505  lea     rdx, [rbp+260h+Name]; unsigned __int16 *
0x180045509  lea     rcx, [rbp+260h+lpSubKey]; this
0x18004550d  call    ?Set@CWxString@@QEAAJPEBG@Z; CWxString::Set(ushort const *)
0x180045512  xor     ecx, ecx
0x180045514  mov     edi, eax
0x180045516  test    eax, eax
0x180045518  js      loc_180045C06
0x18004551e  cmp     dword ptr [rsp+360h+var_2F0], ecx
0x180045522  jz      short loc_18004552D
0x180045524  mov     dword ptr [rsp+360h+var_2F0], ecx
0x180045528  mov     [r13+0], cx
0x18004552d  mov     rdx, [rbp+260h+lpSubKey]; lpSubKey
0x180045531  lea     rax, [rbp+260h+cchName]
0x180045535  mov     [rsp+360h+lpcchClass], rax; pcbData
0x18004553a  lea     r8, Value; "CachePrefix"
0x180045541  lea     rax, [rbp+260h+Name]
0x180045545  mov     [rbp+260h+cchName], 208h
0x18004554c  mov     [rsp+360h+lpClass], rax; pvData
0x180045551  mov     r9d, 2; dwFlags
0x180045557  mov     [rsp+360h+lpReserved], rcx; pdwType
0x18004555c  mov     rcx, [rsp+360h+hKey]; hkey
0x180045561  call    cs:__imp_RegGetValueW
0x180045567  mov     edi, eax
0x180045569  cmp     eax, 2
0x18004556c  jz      loc_180045769
0x180045572  test    eax, eax
0x180045574  jle     short loc_18004557F
0x180045576  movzx   edi, ax
0x180045579  or      edi, 80070000h
0x18004557f  test    edi, edi
0x180045581  js      loc_180045BF9
0x180045587  lea     rdx, [rbp+260h+Name]; unsigned __int16 *
0x18004558b  lea     rcx, [rsp+360h+var_2F8]; this
0x180045590  call    ?Set@CWxString@@QEAAJPEBG@Z; CWxString::Set(ushort const *)
0x180045595  xor     ecx, ecx
0x180045597  mov     edi, eax
0x180045599  test    eax, eax
0x18004559b  js      loc_180045BEC
0x1800455a1  cmp     dword ptr [rbp+260h+var_2A8], ecx
0x1800455a4  jz      short loc_1800455AD
0x1800455a6  mov     dword ptr [rbp+260h+var_2A8], ecx
0x1800455a9  mov     [r15], cx
0x1800455ad  mov     r13, [rbp+260h+lpSubKey]
0x1800455b1  lea     rax, [rbp+260h+cchName]
0x1800455b5  mov     [rsp+360h+lpcchClass], rax; pcbData
0x1800455ba  lea     r8, aCachepath; "CachePath"
0x1800455c1  lea     rax, [rbp+260h+Name]
0x1800455c5  mov     [rbp+260h+cchName], 208h
0x1800455cc  mov     [rsp+360h+lpClass], rax; pvData
0x1800455d1  mov     r9d, 2; dwFlags
0x1800455d7  mov     [rsp+360h+lpReserved], rcx; pdwType
0x1800455dc  mov     rdx, r13; lpSubKey
0x1800455df  mov     rcx, [rsp+360h+hKey]; hkey
0x1800455e4  call    cs:__imp_RegGetValueW
0x1800455ea  mov     edi, eax
0x1800455ec  cmp     eax, 2
0x1800455ef  jz      loc_180045B42
0x1800455f5  test    eax, eax
0x1800455f7  jle     short loc_180045602
0x1800455f9  movzx   edi, ax
0x1800455fc  or      edi, 80070000h
0x180045602  test    edi, edi
0x180045604  js      loc_180045BDF
0x18004560a  lea     rdx, [rbp+260h+Name]; unsigned __int16 *
0x18004560e  lea     rcx, [rbp+260h+var_2B0]; this
0x180045612  call    ?Set@CWxString@@QEAAJPEBG@Z; CWxString::Set(ushort const *)
0x180045617  xor     ecx, ecx
0x180045619  mov     edi, eax
0x18004561b  test    eax, eax
0x18004561d  js      loc_180045BD2
0x180045623  cmp     dword ptr [rbp+260h+var_2B8], ecx
0x180045626  jz      short loc_180045636
0x180045628  mov     eax, ecx
0x18004562a  mov     dword ptr [rbp+260h+var_2B8], ecx
0x18004562d  mov     rcx, [rbp+260h+var_2C0]
0x180045631  mov     [rcx], ax
0x180045634  xor     ecx, ecx
0x180045636  mov     r15, [rsp+360h+hKey]
0x18004563b  lea     rax, [rbp+260h+cchName]
0x18004563f  mov     [rsp+360h+lpcchClass], rax; pcbData
0x180045644  lea     r8, aCacherelativep; "CacheRelativePath"
0x18004564b  lea     rax, [rbp+260h+Name]
0x18004564f  mov     [rbp+260h+cchName], 208h
0x180045656  mov     [rsp+360h+lpClass], rax; pvData
0x18004565b  mov     r9d, 2; dwFlags
0x180045661  mov     [rsp+360h+lpReserved], rcx; pdwType
0x180045666  mov     rdx, r13; lpSubKey
0x180045669  mov     rcx, r15; hkey
0x18004566c  call    cs:__imp_RegGetValueW
0x180045672  mov     edi, eax
0x180045674  cmp     eax, 2
0x180045677  jnz     loc_180045797
0x18004567d  xor     ecx, ecx
0x18004567f  lea     rax, [rbp+260h+cchName]
0x180045683  mov     [rbp+260h+pvData], ecx
0x180045686  mov     [rsp+360h+lpcchClass], rax; pcbData
0x18004568b  lea     r8, aCachelimit; "CacheLimit"
0x180045692  lea     rax, [rbp+260h+pvData]
0x180045696  mov     [rbp+260h+cchName], 4
0x18004569d  mov     [rsp+360h+lpClass], rax; pvData
0x1800456a2  mov     r9d, 18h; dwFlags
0x1800456a8  mov     [rsp+360h+lpReserved], rcx; pdwType
0x1800456ad  mov     rdx, r13; lpSubKey
0x1800456b0  mov     rcx, r15; hkey
0x1800456b3  call    cs:__imp_RegGetValueW
0x1800456b9  xor     ecx, ecx
0x1800456bb  mov     edi, eax
0x1800456bd  cmp     eax, 2
0x1800456c0  jnz     loc_180045880
0x1800456c6  lea     rax, [rbp+260h+cchName]
0x1800456ca  mov     [rbp+260h+var_270], ecx
0x1800456cd  mov     [rsp+360h+lpcchClass], rax; pcbData
0x1800456d2  lea     r8, aCacheoptions; "CacheOptions"
0x1800456d9  lea     rax, [rbp+260h+var_270]
0x1800456dd  mov     [rbp+260h+cchName], 4
0x1800456e4  mov     [rsp+360h+lpClass], rax; pvData
0x1800456e9  mov     r9d, 18h; dwFlags
0x1800456ef  mov     [rsp+360h+lpReserved], rcx; pdwType
0x1800456f4  mov     rdx, r13; lpSubKey
0x1800456f7  mov     rcx, r15; hkey
0x1800456fa  call    cs:__imp_RegGetValueW
0x180045700  mov     edi, eax
0x180045702  cmp     eax, 2
0x180045705  jnz     short loc_180045778
0x180045707  mov     rdx, [rbp+260h+var_2D8]
0x18004570b  mov     rcx, r13
0x18004570e  call    cs:__imp__o__wcsicmp
0x180045714  mov     rdx, [rbp+260h+lpData]
0x180045718  xor     edi, edi
0x18004571a  test    eax, eax
0x18004571c  jz      loc_180045B6B
0x180045722  mov     rcx, [rbp+260h+var_2C8]
0x180045726  cmp     ecx, dword ptr [rsp+360h+var_2F0]
0x18004572a  mov     r8d, ecx
0x18004572d  mov     r13, [rsp+360h+var_2F8]
0x180045732  cmovnb  r8d, dword ptr [rsp+360h+var_2F0]
0x180045738  mov     rcx, r13
0x18004573b  call    cs:__imp__o__wcsnicmp
0x180045741  test    eax, eax
0x180045743  jz      loc_18004591D
0x180045749  mov     r15, [rbp+260h+var_2B0]
0x18004574d  mov     rdx, r14
0x180045750  mov     rcx, r15
0x180045753  call    cs:__imp__o__wcsicmp
0x180045759  test    eax, eax
0x18004575b  jz      loc_180045B59
0x180045761  test    esi, esi
0x180045763  jnz     loc_180045B1B
0x180045769  mov     edx, [rsp+360h+var_308]
0x18004576d  add     edx, [rsp+360h+var_310]
0x180045771  xor     edi, edi
0x180045773  jmp     loc_1800454A2
0x180045778  test    eax, eax
0x18004577a  jle     short loc_180045785
0x18004577c  movzx   edi, ax
0x18004577f  or      edi, 80070000h
0x180045785  test    edi, edi
0x180045787  jns     loc_180045707
0x18004578d  mov     [rsp+360h+var_304], 0CAh
0x180045795  jmp     short loc_1800457CD
0x180045797  test    eax, eax
  ... truncated ...
```
