# _GetTilePath(USER_TILE_TYPE,ushort const *,bool,ushort * *)

- ea: `0x180014e10`
- end: `0x180015544`
- name: `?_GetTilePath@@YAJW4USER_TILE_TYPE@@PEBG_NPEAPEAG@Z`
- size: `1844`
- prototype: `int __high(enum USER_TILE_TYPE, const unsigned __int16 *, bool, unsigned __int16 **)`
- caller_count: `14`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x1800149b0`
- `0x1800149f0`
- `0x180014d00`
- `0x18003b9c4`
- `0x180046aec`
- `0x1800477f0`
- `0x1800c9770`
- `0x1800c97f0`
- `0x1800c9b60`
- `0x1800cba40`
- `0x1800cc180`
- `0x1800cc550`
- `0x1800cdeb0`
- `0x1800cfde0`

## callees

- `0x18000da00`
- `0x180014e10`
- `0x1800156f0`
- `0x18003cdf8`
- `0x18003d244`
- `0x18004ad7c`
- `0x18004b1e4`
- `0x180054130`
- `0x1800c3a44`
- `0x1800c3a9c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015155`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015155`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001508b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001508b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180014fe1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180014fe1`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001511c`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800152a9`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001511c`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800152a9`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180015466`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180015466`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!SHExpandEnvironmentStringsW` at `0x180015066`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!SHExpandEnvironmentStringsW` at `0x180015066`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x180014f0f`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x1800150a5`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x1800151bd`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x180015228`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x180014f0f`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x1800150a5`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x1800151bd`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x180015228`
- `SHCORE!__imp_SHWindowsPolicy` at `0x180014e5d`
- `SHCORE!__imp_SHWindowsPolicy` at `0x180014e5d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180014ee8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180014fae`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180015001`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180015248`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180014ee8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180014fae`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180015001`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180015248`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x1800153ba`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180015430`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x1800153ba`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180015430`

## string_xrefs

- `0x18001545d`: `%ProgramData%`

## pseudocode

```c
HRESULT __fastcall _GetTilePath(unsigned int a1, const WCHAR *a2, char a3, LPWSTR *a4)
{
  unsigned __int16 *v5; // r14
  const unsigned __int16 *v8; // rdx
  __int64 v9; // rdi
  __int64 v10; // rdx
  WCHAR *v11; // rcx
  const wchar_t *v12; // r8
  __int64 v13; // r9
  WCHAR *v14; // r10
  WCHAR *v15; // rdx
  HRESULT Error; // esi
  int ValueW; // ebx
  HRESULT CurrentUsersSidString; // eax
  __int64 v19; // rdx
  WCHAR *v20; // rax
  LPWSTR v21; // rcx
  _WORD *v22; // r8
  _WORD *v23; // rcx
  LPWSTR v24; // rcx
  LSTATUS v25; // eax
  WCHAR *v26; // rcx
  const unsigned __int16 *v27; // rdx
  int v28; // eax
  bool v30; // sf
  const WCHAR *v31; // rdi
  signed int LastError; // eax
  unsigned int v33; // edx
  const WCHAR *v34; // rcx
  WCHAR *v35; // rcx
  bool v36; // sf
  const WCHAR *v37; // rdi
  _QWORD *v38; // rax
  _QWORD *v39; // rax
  int LargeSizeForTileType; // ebx
  DWORD v41; // eax
  LPCWSTR lpSubKey; // [rsp+40h] [rbp-C0h] BYREF
  char v43; // [rsp+48h] [rbp-B8h]
  LPWSTR ppwsz; // [rsp+50h] [rbp-B0h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-A8h] BYREF
  HSTRING string[4]; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 pvData[264]; // [rsp+80h] [rbp-80h] BYREF
  WCHAR psz[260]; // [rsp+290h] [rbp+190h] BYREF
  _BYTE v50[528]; // [rsp+4A0h] [rbp+3A0h] BYREF

  v43 = a3;
  *a4 = 0;
  v5 = 0;
  if ( (unsigned int)SHWindowsPolicy(POLID_UseDefaultTile) || a1 == 3 )
  {
    ValueW = -2147467259;
    v39 = (_QWORD *)Windows::Internal::StringReference::StringReference(string, (const unsigned __int16 (*)[42])v8);
    RoOriginateError(2147500037LL, *v39);
    Error = -2147024774;
    goto LABEL_31;
  }
  v9 = 2147483646;
  hKey = 0;
  v10 = 2147483646;
  lpSubKey = 0;
  v11 = 0;
  v12 = L"Software\\Microsoft\\Windows\\CurrentVersion\\AccountPicture\\Users\\";
  v13 = 260;
  v14 = psz;
  do
  {
    if ( !v10 )
      break;
    if ( !*v12 )
      break;
    *v14++ = *v12++;
    --v10;
    --v13;
  }
  while ( v13 );
  v15 = v14 - 1;
  Error = -2147024774;
  ValueW = -2147024774;
  if ( v13 )
  {
    v15 = v14;
    ValueW = 0;
  }
  *v15 = 0;
  if ( !v13 )
    goto LABEL_10;
  ppwsz = 0;
  if ( a2 )
    CurrentUsersSidString = SHStrDupW(a2, &ppwsz);
  else
    CurrentUsersSidString = GetCurrentUsersSidString(&ppwsz);
  ValueW = CurrentUsersSidString;
  if ( CurrentUsersSidString >= 0 )
  {
    v19 = 260;
    v20 = psz;
    do
    {
      if ( !*v20 )
        break;
      ++v20;
      --v19;
    }
    while ( v19 );
    ValueW = -2147024809;
    if ( v19 )
    {
      v21 = ppwsz;
      v22 = v50 - 2 * v19 + 6;
      do
      {
        if ( !v9 )
          break;
        if ( !*v21 )
          break;
        *v22++ = *v21++;
        --v9;
        --v19;
      }
      while ( v19 );
      v23 = v22 - 1;
      ValueW = -2147024774;
      if ( v19 )
      {
        v23 = v22;
        ValueW = 0;
      }
      *v23 = 0;
      if ( v19 )
        ValueW = SHStrDupW(psz, (LPWSTR *)&lpSubKey);
    }
  }
  v24 = ppwsz;
  ppwsz = 0;
  CoTaskMemFree(v24);
  if ( ValueW < 0 )
  {
    v11 = (WCHAR *)lpSubKey;
LABEL_10:
    lpSubKey = 0;
    CoTaskMemFree(v11);
    goto LABEL_30;
  }
  v25 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, lpSubKey, 0, 0x20119u, &hKey);
  ValueW = v25;
  if ( v25 > 0 )
    ValueW = (unsigned __int16)v25 | 0x80070000;
  v26 = (WCHAR *)lpSubKey;
  lpSubKey = 0;
  CoTaskMemFree(v26);
  if ( ValueW >= 0 )
  {
    if ( a1 )
    {
      if ( a1 != 8 )
      {
        switch ( a1 )
        {
          case 1u:
            v31 = L"Image448";
            goto LABEL_45;
          case 2u:
            v31 = L"Video448";
            goto LABEL_45;
          case 4u:
            v31 = L"Image32";
            goto LABEL_45;
          case 5u:
            v31 = L"Image40";
            goto LABEL_45;
          case 6u:
            v31 = L"Image48";
            goto LABEL_45;
          case 7u:
            v31 = L"Image192";
            goto LABEL_45;
          case 9u:
            v31 = L"Image240";
            goto LABEL_45;
          case 0xAu:
            v31 = L"Video240";
            goto LABEL_45;
          case 0xBu:
            v31 = L"Image64";
            goto LABEL_45;
          case 0xCu:
            v31 = L"Image208";
            goto LABEL_45;
          case 0xDu:
            v31 = L"Image424";
            goto LABEL_45;
          case 0xEu:
            v31 = L"Image1080";
            goto LABEL_45;
          default:
            v38 = (_QWORD *)Windows::Internal::StringReference::StringReference(
                              string,
                              (const unsigned __int16 (*)[26])v27);
            RoOriginateError(2147500037LL, *v38);
            ValueW = -2147467259;
            break;
        }
LABEL_39:
        if ( hKey )
          RegCloseKey(hKey);
        if ( ValueW >= 0 )
          return SHStrDupW(v5, a4);
        goto LABEL_30;
      }
      v31 = L"Video192";
    }
    else
    {
      v31 = L"Image96";
    }
LABEL_45:
    LODWORD(lpSubKey) = 520;
    ValueW = RegGetValueW(hKey, 0, v31, 2u, 0, pvData, (LPDWORD)&lpSubKey);
    if ( ValueW )
    {
      pvData[0] = 0;
      v30 = ValueW < 0;
      if ( ValueW <= 0 )
        goto LABEL_36;
      ValueW = (unsigned __int16)ValueW | 0x80070000;
    }
    v30 = ValueW < 0;
LABEL_36:
    if ( !v30 )
    {
LABEL_37:
      if ( (unsigned int)SHExpandEnvironmentStringsW(pvData, v50, 260) )
      {
        v5 = (unsigned __int16 *)v50;
      }
      else
      {
        v5 = pvData;
        LastError = GetLastError();
        ValueW = LastError;
        if ( LastError > 0 )
          ValueW = (unsigned __int16)LastError | 0x80070000;
        if ( ValueW >= 0 )
          ValueW = -2147467259;
      }
      goto LABEL_39;
    }
    switch ( a1 )
    {
      case 4u:
        v37 = L"Image40";
        break;
      case 6u:
        v37 = L"Image96";
        break;
      case 7u:
        v37 = L"Image200";
        break;
      case 8u:
        v37 = L"Video200";
        break;
      default:
        goto LABEL_39;
    }
    LODWORD(lpSubKey) = 520;
    ValueW = RegGetValueW(hKey, 0, v37, 2u, 0, pvData, (LPDWORD)&lpSubKey);
    if ( ValueW )
    {
      pvData[0] = 0;
      v36 = ValueW < 0;
      if ( ValueW <= 0 )
      {
LABEL_70:
        if ( v36 )
          goto LABEL_39;
        goto LABEL_37;
      }
      ValueW = (unsigned __int16)ValueW | 0x80070000;
    }
    v36 = ValueW < 0;
    goto LABEL_70;
  }
LABEL_30:
  if ( !v43 )
    return ValueW;
LABEL_31:
  if ( a1 <= 0xA )
  {
    v28 = 1284;
    if ( _bittest(&v28, a1) )
    {
      if ( ValueW < 0 )
        return ValueW;
      return SHStrDupW(v5, a4);
    }
  }
  if ( !_IsGuestAccount(a2) )
  {
    LargeSizeForTileType = _GetLargeSizeForTileType(a1);
    v41 = ExpandEnvironmentStringsW(L"%ProgramData%", psz, 0x104u);
    if ( v41 )
    {
      if ( v41 > 0x104 )
        goto LABEL_60;
    }
    else
    {
      Error = ResultFromKnownLastError();
      if ( Error < 0 )
        goto LABEL_60;
    }
    lpSubKey = 0;
    switch ( LargeSizeForTileType )
    {
      case 32:
        v34 = L"user-32.png";
        break;
      case 40:
        v34 = L"user-40.png";
        break;
      case 48:
        v34 = L"user-48.png";
        break;
      case 192:
        v34 = L"user-192.png";
        break;
      default:
        v34 = L"user.png";
        break;
    }
    Error = SHStrDupW(v34, (LPWSTR *)&lpSubKey);
    if ( Error >= 0 )
      Error = StringCchPrintfW(pvData, 0x104u, L"%s\\%s\\%s", psz, L"Microsoft\\User Account Pictures", lpSubKey);
    v35 = (WCHAR *)lpSubKey;
    lpSubKey = 0;
    CoTaskMemFree(v35);
    goto LABEL_60;
  }
  Error = SHGetDefaultGuestPicturePath(pvData, v33);
LABEL_60:
  if ( Error >= 0 )
  {
    v5 = pvData;
    return SHStrDupW(v5, a4);
  }
  return Error;
}

```

## disassembly

```asm
0x180014e10  mov     [rsp-8+arg_0], rbx
0x180014e15  push    rbp
0x180014e16  push    rsi
0x180014e17  push    rdi
0x180014e18  push    r12
0x180014e1a  push    r13
0x180014e1c  push    r14
0x180014e1e  push    r15
0x180014e20  lea     rbp, [rsp-5C0h]
0x180014e28  sub     rsp, 6C0h
0x180014e2f  mov     rax, cs:__security_cookie
0x180014e36  xor     rax, rsp
0x180014e39  mov     [rbp+5F0h+var_40], rax
0x180014e40  mov     r13d, ecx
0x180014e43  mov     [rsp+6F0h+var_6A8], r8b
0x180014e48  xor     ebx, ebx
0x180014e4a  lea     rcx, POLID_UseDefaultTile
0x180014e51  mov     [r9], rbx
0x180014e54  mov     r14d, ebx
0x180014e57  mov     r15, r9
0x180014e5a  mov     r12, rdx
0x180014e5d  call    cs:__imp_SHWindowsPolicy
0x180014e64  nop     dword ptr [rax+rax+00h]
0x180014e69  test    eax, eax
0x180014e6b  jnz     loc_18001541A
0x180014e71  cmp     r13d, 3
0x180014e75  jz      loc_18001541A
0x180014e7b  mov     edi, 7FFFFFFEh
0x180014e80  mov     [rsp+6F0h+hKey], rbx
0x180014e85  mov     edx, edi
0x180014e87  mov     [rsp+6F0h+lpSubKey], rbx
0x180014e8c  mov     ecx, ebx; pv
0x180014e8e  lea     r8, aSoftwareMicros_5; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180014e95  mov     r9d, 104h
0x180014e9b  lea     r10, [rbp+5F0h+psz]
0x180014ea2  test    rdx, rdx
0x180014ea5  jz      short loc_180014EC5
0x180014ea7  movzx   eax, word ptr [r8]
0x180014eab  test    ax, ax
0x180014eae  jz      short loc_180014EC5
0x180014eb0  mov     [r10], ax
0x180014eb4  add     r8, 2
0x180014eb8  add     r10, 2
0x180014ebc  dec     rdx
0x180014ebf  sub     r9, 1
0x180014ec3  jnz     short loc_180014EA2
0x180014ec5  xor     eax, eax
0x180014ec7  lea     rdx, [r10-2]
0x180014ecb  test    r9, r9
0x180014ece  mov     esi, 8007007Ah
0x180014ed3  mov     ebx, esi
0x180014ed5  cmovnz  rdx, r10
0x180014ed9  cmovnz  ebx, eax
0x180014edc  mov     [rdx], ax
0x180014edf  jnz     short loc_180014EF9
0x180014ee1  xor     edi, edi
0x180014ee3  mov     [rsp+6F0h+lpSubKey], rdi
0x180014ee8  call    cs:__imp_CoTaskMemFree
0x180014eef  nop     dword ptr [rax+rax+00h]
0x180014ef4  jmp     loc_180015015
0x180014ef9  mov     [rsp+6F0h+ppwsz], rax
0x180014efe  test    r12, r12
0x180014f01  jz      loc_180015197
0x180014f07  lea     rdx, [rsp+6F0h+ppwsz]; ppwsz
0x180014f0c  mov     rcx, r12; psz
0x180014f0f  call    cs:__imp_SHStrDupW
0x180014f16  nop     dword ptr [rax+rax+00h]
0x180014f1b  mov     ebx, eax
0x180014f1d  test    eax, eax
0x180014f1f  js      loc_1800151D0
0x180014f25  mov     edx, 104h
0x180014f2a  lea     rax, [rbp+5F0h+psz]
0x180014f31  cmp     [rax], r14w
0x180014f35  jz      short loc_180014F41
0x180014f37  add     rax, 2
0x180014f3b  sub     rdx, 1
0x180014f3f  jnz     short loc_180014F31
0x180014f41  xor     eax, eax
0x180014f43  mov     ebx, 80070057h
0x180014f48  test    rdx, rdx
0x180014f4b  cmovnz  ebx, eax
0x180014f4e  jz      loc_1800151D0
0x180014f54  mov     rcx, [rsp+6F0h+ppwsz]
0x180014f59  lea     rax, [rdx+rdx]
0x180014f5d  lea     r8, [rbp+5F0h+var_258]
0x180014f64  sub     r8, rax
0x180014f67  test    rdi, rdi
0x180014f6a  jz      short loc_180014F89
0x180014f6c  movzx   eax, word ptr [rcx]
0x180014f6f  test    ax, ax
0x180014f72  jz      short loc_180014F89
0x180014f74  mov     [r8], ax
0x180014f78  add     rcx, 2
0x180014f7c  add     r8, 2
0x180014f80  dec     rdi
0x180014f83  sub     rdx, 1
0x180014f87  jnz     short loc_180014F67
0x180014f89  xor     edi, edi
0x180014f8b  lea     rcx, [r8-2]
0x180014f8f  test    rdx, rdx
0x180014f92  mov     ebx, esi
0x180014f94  cmovnz  rcx, r8
0x180014f98  cmovnz  ebx, edi
0x180014f9b  mov     [rcx], di
0x180014f9e  jnz     loc_1800151B1
0x180014fa4  mov     rcx, [rsp+6F0h+ppwsz]; pv
0x180014fa9  mov     [rsp+6F0h+ppwsz], rdi
0x180014fae  call    cs:__imp_CoTaskMemFree
0x180014fb5  nop     dword ptr [rax+rax+00h]
0x180014fba  test    ebx, ebx
0x180014fbc  js      loc_180015147
0x180014fc2  mov     rdx, [rsp+6F0h+lpSubKey]; lpSubKey
0x180014fc7  lea     rax, [rsp+6F0h+hKey]
0x180014fcc  mov     r9d, 20119h; samDesired
0x180014fd2  mov     [rsp+6F0h+phkResult], rax; phkResult
0x180014fd7  xor     r8d, r8d; ulOptions
0x180014fda  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180014fe1  call    cs:__imp_RegOpenKeyExW
0x180014fe8  nop     dword ptr [rax+rax+00h]
0x180014fed  mov     ebx, eax
0x180014fef  test    eax, eax
0x180014ff1  jg      loc_180015139
0x180014ff7  mov     rcx, [rsp+6F0h+lpSubKey]; pv
0x180014ffc  mov     [rsp+6F0h+lpSubKey], rdi
0x180015001  call    cs:__imp_CoTaskMemFree
0x180015008  nop     dword ptr [rax+rax+00h]
0x18001500d  test    ebx, ebx
0x18001500f  jns     loc_1800150DC
0x180015015  cmp     [rsp+6F0h+var_6A8], 0
0x18001501a  jz      loc_180015413
0x180015020  cmp     r13d, 0Ah
0x180015024  ja      loc_1800151D7
0x18001502a  mov     eax, 504h
0x18001502f  bt      eax, r13d
0x180015033  jnb     loc_1800151D7
0x180015039  test    ebx, ebx
0x18001503b  jns     short loc_18001509F
0x18001503d  mov     eax, ebx
0x18001503f  jmp     short loc_1800150B1
0x180015041  xor     eax, eax
0x180015043  mov     [rbp+5F0h+var_670], ax
0x180015047  test    ebx, ebx
0x180015049  jg      loc_18001518C
0x18001504f  js      loc_1800152C8
0x180015055  mov     r8d, 104h
0x18001505b  lea     rdx, [rbp+5F0h+var_250]
0x180015062  lea     rcx, [rbp+5F0h+var_670]
0x180015066  call    cs:__imp_SHExpandEnvironmentStringsW
0x18001506d  nop     dword ptr [rax+rax+00h]
0x180015072  test    eax, eax
0x180015074  jz      loc_180015151
0x18001507a  lea     r14, [rbp+5F0h+var_250]
0x180015081  mov     rcx, [rsp+6F0h+hKey]; hKey
0x180015086  test    rcx, rcx
0x180015089  jz      short loc_180015097
0x18001508b  call    cs:__imp_RegCloseKey
0x180015092  nop     dword ptr [rax+rax+00h]
0x180015097  test    ebx, ebx
0x180015099  js      loc_18001540C
0x18001509f  mov     rdx, r15; ppwsz
0x1800150a2  mov     rcx, r14; psz
0x1800150a5  call    cs:__imp_SHStrDupW
0x1800150ac  nop     dword ptr [rax+rax+00h]
0x1800150b1  mov     rcx, [rbp+5F0h+var_40]
0x1800150b8  xor     rcx, rsp; StackCookie
0x1800150bb  call    __security_check_cookie
0x1800150c0  mov     rbx, [rsp+6F0h+arg_0]
0x1800150c8  add     rsp, 6C0h
0x1800150cf  pop     r15
0x1800150d1  pop     r14
0x1800150d3  pop     r13
0x1800150d5  pop     r12
0x1800150d7  pop     rdi
0x1800150d8  pop     rsi
0x1800150d9  pop     rbp
0x1800150da  retn
0x1800150dc  test    r13d, r13d
0x1800150df  jnz     loc_180015176
0x1800150e5  lea     rdi, aImage96; "Image96"
0x1800150ec  mov     rcx, [rsp+6F0h+hKey]; hkey
0x1800150f1  lea     rax, [rsp+6F0h+lpSubKey]
0x1800150f6  mov     [rsp+6F0h+pcbData], rax; pcbData
0x1800150fb  mov     r9d, 2; dwFlags
0x180015101  lea     rax, [rbp+5F0h+var_670]
0x180015105  mov     dword ptr [rsp+6F0h+lpSubKey], 208h
0x18001510d  mov     [rsp+6F0h+pvData], rax; pvData
0x180015112  mov     r8, rdi; lpValue
0x180015115  xor     edx, edx; lpSubKey
0x180015117  mov     [rsp+6F0h+phkResult], r14; pdwType
0x18001511c  call    cs:__imp_RegGetValueW
0x180015123  nop     dword ptr [rax+rax+00h]
0x180015128  mov     ebx, eax
0x18001512a  test    eax, eax
0x18001512c  jnz     loc_180015041
0x180015132  test    ebx, ebx
0x180015134  jmp     loc_18001504F
0x180015139  movzx   ebx, ax
0x18001513c  or      ebx, 80070000h
0x180015142  jmp     loc_180014FF7
0x180015147  mov     rcx, [rsp+6F0h+lpSubKey]
0x18001514c  jmp     loc_180014EE3
0x180015151  lea     r14, [rbp+5F0h+var_670]
0x180015155  call    cs:__imp_GetLastError
0x18001515c  nop     dword ptr [rax+rax+00h]
0x180015161  mov     ebx, eax
0x180015163  test    eax, eax
0x180015165  jg      short loc_1800151A6
0x180015167  test    ebx, ebx
0x180015169  mov     edi, 80004005h
0x18001516e  cmovns  ebx, edi
0x180015171  jmp     loc_180015081
0x180015176  cmp     r13d, 8
0x18001517a  jnz     loc_1800152F0
0x180015180  lea     rdi, aVideo192; "Video192"
0x180015187  jmp     loc_1800150EC
0x18001518c  movzx   ebx, bx
0x18001518f  or      ebx, 80070000h
0x180015195  jmp     short loc_180015132
0x180015197  lea     rcx, [rsp+6F0h+ppwsz]; ppwsz
0x18001519c  call    ?GetCurrentUsersSidString@@YAJPEAPEAG@Z; GetCurrentUsersSidString(ushort * *)
0x1800151a1  jmp     loc_180014F1B
0x1800151a6  movzx   ebx, ax
0x1800151a9  or      ebx, 80070000h
0x1800151af  jmp     short loc_180015167
0x1800151b1  lea     rdx, [rsp+6F0h+lpSubKey]; ppwsz
0x1800151b6  lea     rcx, [rbp+5F0h+psz]; psz
0x1800151bd  call    cs:__imp_SHStrDupW
0x1800151c4  nop     dword ptr [rax+rax+00h]
0x1800151c9  mov     ebx, eax
0x1800151cb  jmp     loc_180014FA4
0x1800151d0  xor     edi, edi
0x1800151d2  jmp     loc_180014FA4
0x1800151d7  mov     rcx, r12; unsigned __int16 *
0x1800151da  call    ?_IsGuestAccount@@YA_NPEBG@Z; _IsGuestAccount(ushort const *)
0x1800151df  test    al, al
0x1800151e1  jz      loc_180015448
0x1800151e7  lea     rcx, [rbp+5F0h+var_670]; unsigned __int16 *
0x1800151eb  call    ?SHGetDefaultGuestPicturePath@@YAJPEAGK@Z; SHGetDefaultGuestPicturePath(ushort *,ulong)
0x1800151f0  mov     esi, eax
0x1800151f2  test    esi, esi
0x1800151f4  js      loc_180015505
0x1800151fa  lea     r14, [rbp+5F0h+var_670]
0x1800151fe  jmp     loc_18001509F
0x180015203  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180015208  mov     esi, eax
0x18001520a  test    eax, eax
0x18001520c  js      short loc_1800151F2
0x18001520e  mov     [rsp+6F0h+lpSubKey], rdi
0x180015213  lea     rdx, [rsp+6F0h+lpSubKey]; ppwsz
0x180015218  cmp     ebx, 20h ; ' '
0x18001521b  jnz     loc_18001548A
0x180015221  lea     rcx, psz; "user-32.png"
0x180015228  call    cs:__imp_SHStrDupW
0x18001522f  nop     dword ptr [rax+rax+00h]
0x180015234  mov     esi, eax
0x180015236  test    eax, eax
0x180015238  jns     loc_1800154CC
0x18001523e  mov     rcx, [rsp+6F0h+lpSubKey]; pv
0x180015243  mov     [rsp+6F0h+lpSubKey], rdi
0x180015248  call    cs:__imp_CoTaskMemFree
0x18001524f  nop     dword ptr [rax+rax+00h]
0x180015254  jmp     short loc_1800151F2
0x180015256  mov     ecx, r13d
0x180015259  sub     ecx, 4
0x18001525c  jz      short loc_1800152D2
0x18001525e  sub     ecx, 2
0x180015261  jz      loc_180015400
0x180015267  sub     ecx, 1
0x18001526a  jz      loc_1800153F4
0x180015270  cmp     ecx, 1
0x180015273  jz      loc_1800153E8
0x180015279  mov     rcx, [rsp+6F0h+hKey]; hkey
0x18001527e  lea     rax, [rsp+6F0h+lpSubKey]
0x180015283  mov     [rsp+6F0h+pcbData], rax; pcbData
0x180015288  mov     r9d, 2; dwFlags
0x18001528e  lea     rax, [rbp+5F0h+var_670]
0x180015292  mov     dword ptr [rsp+6F0h+lpSubKey], 208h
0x18001529a  mov     [rsp+6F0h+pvData], rax; pvData
0x18001529f  mov     r8, rdi; lpValue
0x1800152a2  xor     edx, edx; lpSubKey
0x1800152a4  mov     [rsp+6F0h+phkResult], r14; pdwType
0x1800152a9  call    cs:__imp_RegGetValueW
0x1800152b0  nop     dword ptr [rax+rax+00h]
0x1800152b5  mov     ebx, eax
0x1800152b7  test    eax, eax
0x1800152b9  jnz     short loc_1800152DB
0x1800152bb  test    ebx, ebx
0x1800152bd  js      loc_180015081
0x1800152c3  jmp     loc_180015055
0x1800152c8  cmp     r13d, 4
0x1800152cc  jnz     loc_1800153CD
0x1800152d2  lea     rdi, aImage40; "Image40"
0x1800152d9  jmp     short loc_180015279
0x1800152db  xor     eax, eax
0x1800152dd  mov     [rbp+5F0h+var_670], ax
0x1800152e1  test    ebx, ebx
0x1800152e3  jle     short loc_1800152BD
0x1800152e5  movzx   ebx, bx
0x1800152e8  or      ebx, 80070000h
0x1800152ee  jmp     short loc_1800152BB
  ... truncated ...
```
