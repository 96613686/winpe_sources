# CUserTileStore::GetUserTilePathBySizeNoDefault(ushort const *,uint,ushort * *)

- ea: `0x180015920`
- end: `0x180015eee`
- name: `?GetUserTilePathBySizeNoDefault@CUserTileStore@@UEAAJPEBGIPEAPEAG@Z`
- size: `1486`
- prototype: `int(CUserTileStore *__hidden this, const unsigned __int16 *, unsigned int, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callees

- `0x1800156f0`
- `0x180015920`
- `0x180015ef4`
- `0x180015fc0`
- `0x18003cdf8`
- `0x18004ad7c`
- `0x18004b1e4`
- `0x18004c40c`
- `0x180054130`
- `0x1800c3a44`
- `0x1800c3a9c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015c3e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015c3e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180015bda`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180015bda`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180015b03`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180015b03`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180015b8a`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180015d7a`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180015b8a`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180015d7a`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!SHExpandEnvironmentStringsW` at `0x180015bb9`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!SHExpandEnvironmentStringsW` at `0x180015bb9`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x180015a11`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x180015bf0`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x180015c91`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x180015a11`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x180015bf0`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x180015c91`
- `SHCORE!__imp_SHWindowsPolicy` at `0x180015972`
- `SHCORE!__imp_SHWindowsPolicy` at `0x180015972`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180015ad4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180015b23`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180015ad4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180015b23`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180015cd3`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180015e63`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180015cd3`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180015e63`

## pseudocode

```c
__int64 __fastcall CUserTileStore::GetUserTilePathBySizeNoDefault(
        CUserTileStore *this,
        const unsigned __int16 *a2,
        unsigned int a3,
        unsigned __int16 **a4)
{
  int TileTypeForLargeSize; // eax
  int v7; // esi
  const unsigned __int16 *v8; // rdx
  __int64 v9; // rdi
  __int64 v10; // rax
  const wchar_t *v11; // rcx
  __int64 v12; // r8
  WCHAR *v13; // r9
  WCHAR *v14; // rdx
  signed int v15; // ebx
  HRESULT CurrentUsersSidString; // eax
  WCHAR *v17; // rax
  __int64 v18; // rdx
  __int64 v19; // r8
  LPWSTR v20; // rax
  bool v21; // zf
  __int64 v22; // rdx
  WCHAR *v23; // r8
  WCHAR *v24; // rcx
  LPWSTR v25; // rcx
  LSTATUS v26; // eax
  WCHAR *v27; // rcx
  const unsigned __int16 *v28; // rdx
  WCHAR *v29; // r14
  const WCHAR *v30; // rdi
  LSTATUS ValueW; // eax
  signed int LastError; // eax
  _QWORD *v34; // rax
  unsigned int v35; // edx
  int DefaultUserPicturePathBySize; // eax
  unsigned int LargeSizeForTileType; // eax
  bool v38; // cl
  unsigned int v39; // r9d
  LSTATUS v40; // eax
  const WCHAR *v41; // rdi
  _QWORD *v42; // rax
  LPWSTR ppwsz; // [rsp+40h] [rbp-C0h] BYREF
  LPCWSTR lpSubKey; // [rsp+48h] [rbp-B8h] BYREF
  HKEY hkey; // [rsp+50h] [rbp-B0h] BYREF
  HSTRING string[5]; // [rsp+58h] [rbp-A8h] BYREF
  unsigned __int16 pvData[264]; // [rsp+80h] [rbp-80h] BYREF
  WCHAR v48[264]; // [rsp+290h] [rbp+190h] BYREF
  WCHAR psz[264]; // [rsp+4A0h] [rbp+3A0h] BYREF

  *a4 = 0;
  TileTypeForLargeSize = _GetTileTypeForLargeSize(a3);
  *a4 = 0;
  v7 = TileTypeForLargeSize;
  if ( !(unsigned int)SHWindowsPolicy(POLID_UseDefaultTile) && v7 != 3 )
  {
    v9 = 2147483646;
    hkey = 0;
    v10 = 2147483646;
    lpSubKey = 0;
    v11 = L"Software\\Microsoft\\Windows\\CurrentVersion\\AccountPicture\\Users\\";
    v12 = 260;
    v13 = v48;
    do
    {
      if ( !v10 )
        break;
      if ( !*v11 )
        break;
      *v13++ = *v11++;
      --v10;
      --v12;
    }
    while ( v12 );
    v14 = v13 - 1;
    v15 = v12 == 0 ? 0x8007007A : 0;
    if ( v12 )
      v14 = v13;
    *v14 = 0;
    if ( v12 )
    {
      ppwsz = 0;
      if ( a2 )
        CurrentUsersSidString = SHStrDupW(a2, &ppwsz);
      else
        CurrentUsersSidString = GetCurrentUsersSidString(&ppwsz);
      v15 = CurrentUsersSidString;
      if ( CurrentUsersSidString >= 0 )
      {
        v17 = v48;
        v18 = 260;
        do
        {
          if ( !*v17 )
            break;
          ++v17;
          --v18;
        }
        while ( v18 );
        v15 = v18 == 0 ? 0x80070057 : 0;
        v19 = (260 - v18) & -(__int64)(v18 != 0);
        if ( v18 )
        {
          v20 = ppwsz;
          v22 = 260 - v19;
          v21 = v19 == 260;
          v23 = &v48[v19];
          if ( !v21 )
          {
            do
            {
              if ( !v9 )
                break;
              if ( !*v20 )
                break;
              *v23++ = *v20++;
              --v9;
              --v22;
            }
            while ( v22 );
          }
          v24 = v23 - 1;
          v15 = v22 == 0 ? 0x8007007A : 0;
          if ( v22 )
            v24 = v23;
          *v24 = 0;
          if ( v22 )
            v15 = SHStrDupW(v48, (LPWSTR *)&lpSubKey);
        }
      }
      v25 = ppwsz;
      ppwsz = 0;
      CoTaskMemFree(v25);
      if ( v15 >= 0 )
      {
        v26 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, lpSubKey, 0, 0x20119u, &hkey);
        v15 = v26;
        if ( v26 > 0 )
          v15 = (unsigned __int16)v26 | 0x80070000;
      }
    }
    v27 = (WCHAR *)lpSubKey;
    lpSubKey = 0;
    CoTaskMemFree(v27);
    if ( v15 < 0 )
      return (unsigned int)v15;
    v29 = 0;
    if ( v7 == 8 )
    {
      v30 = L"Video192";
      goto LABEL_33;
    }
    if ( v7 > 8 )
    {
      switch ( v7 )
      {
        case 9:
          v30 = L"Image240";
          break;
        case 10:
          v30 = L"Video240";
          break;
        case 11:
          v30 = L"Image64";
          break;
        case 12:
          v30 = L"Image208";
          break;
        case 13:
          v30 = L"Image424";
          break;
        case 14:
          v30 = L"Image1080";
          break;
        default:
          goto LABEL_83;
      }
    }
    else
    {
      switch ( v7 )
      {
        case 0:
          v30 = L"Image96";
          break;
        case 1:
          v30 = L"Image448";
          break;
        case 2:
          v30 = L"Video448";
          break;
        case 4:
          v30 = L"Image32";
          break;
        case 5:
          v30 = L"Image40";
          break;
        case 6:
          v30 = L"Image48";
          break;
        case 7:
          v30 = L"Image192";
          break;
        default:
LABEL_83:
          v42 = (_QWORD *)Windows::Internal::StringReference::StringReference(
                            string,
                            (const unsigned __int16 (*)[26])v28);
          RoOriginateError(2147500037LL, *v42);
          v15 = -2147467259;
          goto LABEL_37;
      }
    }
LABEL_33:
    LODWORD(ppwsz) = 520;
    ValueW = RegGetValueW(hkey, 0, v30, 2u, 0, pvData, (LPDWORD)&ppwsz);
    v15 = ValueW;
    if ( ValueW )
    {
      pvData[0] = 0;
      if ( ValueW > 0 )
        v15 = (unsigned __int16)ValueW | 0x80070000;
    }
    if ( v15 >= 0 )
      goto LABEL_97;
    switch ( v7 )
    {
      case 4:
        v41 = L"Image40";
        break;
      case 6:
        v41 = L"Image96";
        break;
      case 7:
        v41 = L"Image200";
        break;
      case 8:
        v41 = L"Video200";
        break;
      default:
        goto LABEL_37;
    }
    LODWORD(ppwsz) = 520;
    v40 = RegGetValueW(hkey, 0, v41, 2u, 0, pvData, (LPDWORD)&ppwsz);
    v15 = v40;
    if ( v40 )
    {
      pvData[0] = 0;
      if ( v40 > 0 )
        v15 = (unsigned __int16)v40 | 0x80070000;
    }
    if ( v15 >= 0 )
    {
LABEL_97:
      if ( (unsigned int)SHExpandEnvironmentStringsW(pvData, psz, 260) )
      {
        v29 = psz;
      }
      else
      {
        v29 = pvData;
        LastError = GetLastError();
        v15 = LastError;
        if ( LastError > 0 )
          v15 = (unsigned __int16)LastError | 0x80070000;
        if ( v15 >= 0 )
          v15 = -2147467259;
      }
    }
LABEL_37:
    if ( hkey )
      RegCloseKey(hkey);
    if ( v15 >= 0 )
      return (unsigned int)SHStrDupW(v29, a4);
    return (unsigned int)v15;
  }
  v15 = -2147467259;
  v34 = (_QWORD *)Windows::Internal::StringReference::StringReference(string, (const unsigned __int16 (*)[42])v8);
  RoOriginateError(2147500037LL, *v34);
  if ( !(unsigned __int8)_IsVideoAccountPictureType((unsigned int)v7) )
  {
    if ( _IsGuestAccount(a2) )
    {
      DefaultUserPicturePathBySize = SHGetDefaultGuestPicturePath(pvData, v35);
    }
    else
    {
      LargeSizeForTileType = _GetLargeSizeForTileType((unsigned int)v7);
      DefaultUserPicturePathBySize = _GetDefaultUserPicturePathBySize(v38, LargeSizeForTileType, pvData, v39);
    }
    v15 = DefaultUserPicturePathBySize;
    if ( DefaultUserPicturePathBySize >= 0 )
    {
      v29 = pvData;
      return (unsigned int)SHStrDupW(v29, a4);
    }
  }
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x180015920  mov     [rsp-8+arg_0], rbx
0x180015925  mov     [rsp-8+arg_10], rsi
0x18001592a  push    rbp
0x18001592b  push    rdi
0x18001592c  push    r12
0x18001592e  push    r14
0x180015930  push    r15
0x180015932  lea     rbp, [rsp-5C0h]
0x18001593a  sub     rsp, 6C0h
0x180015941  mov     rax, cs:__security_cookie
0x180015948  xor     rax, rsp
0x18001594b  mov     [rbp+5E0h+var_30], rax
0x180015952  xor     r12d, r12d
0x180015955  mov     ecx, r8d
0x180015958  mov     [r9], r12
0x18001595b  mov     r15, r9
0x18001595e  mov     r14, rdx
0x180015961  call    ?_GetTileTypeForLargeSize@@YA?AW4USER_TILE_TYPE@@I@Z; _GetTileTypeForLargeSize(uint)
0x180015966  lea     rcx, POLID_UseDefaultTile
0x18001596d  mov     [r15], r12
0x180015970  mov     esi, eax
0x180015972  call    cs:__imp_SHWindowsPolicy
0x180015979  nop     dword ptr [rax+rax+00h]
0x18001597e  test    eax, eax
0x180015980  jnz     loc_180015CBD
0x180015986  cmp     esi, 3
0x180015989  jz      loc_180015CBD
0x18001598f  mov     edi, 7FFFFFFEh
0x180015994  mov     [rsp+6E0h+hkey], r12
0x180015999  mov     eax, edi
0x18001599b  mov     [rsp+6E0h+lpSubKey], r12
0x1800159a0  lea     rcx, aSoftwareMicros_5; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1800159a7  mov     r8d, 104h
0x1800159ad  lea     r9, [rbp+5E0h+var_450]
0x1800159b4  test    rax, rax
0x1800159b7  jz      short loc_1800159D6
0x1800159b9  movzx   edx, word ptr [rcx]
0x1800159bc  test    dx, dx
0x1800159bf  jz      short loc_1800159D6
0x1800159c1  mov     [r9], dx
0x1800159c5  add     rcx, 2
0x1800159c9  add     r9, 2
0x1800159cd  dec     rax
0x1800159d0  sub     r8, 1
0x1800159d4  jnz     short loc_1800159B4
0x1800159d6  mov     rax, r8
0x1800159d9  lea     rdx, [r9-2]
0x1800159dd  neg     rax
0x1800159e0  sbb     ebx, ebx
0x1800159e2  not     ebx
0x1800159e4  and     ebx, 8007007Ah
0x1800159ea  test    r8, r8
0x1800159ed  cmovnz  rdx, r9
0x1800159f1  mov     [rdx], r12w
0x1800159f5  jz      loc_180015B19
0x1800159fb  mov     [rsp+6E0h+ppwsz], r12
0x180015a00  test    r14, r14
0x180015a03  jz      loc_180015C6B
0x180015a09  lea     rdx, [rsp+6E0h+ppwsz]; ppwsz
0x180015a0e  mov     rcx, r14; psz
0x180015a11  call    cs:__imp_SHStrDupW
0x180015a18  nop     dword ptr [rax+rax+00h]
0x180015a1d  mov     ebx, eax
0x180015a1f  test    eax, eax
0x180015a21  js      loc_180015ACA
0x180015a27  mov     r9d, 104h
0x180015a2d  lea     rax, [rbp+5E0h+var_450]
0x180015a34  mov     edx, r9d
0x180015a37  cmp     [rax], r12w
0x180015a3b  jz      short loc_180015A47
0x180015a3d  add     rax, 2
0x180015a41  sub     rdx, 1
0x180015a45  jnz     short loc_180015A37
0x180015a47  mov     rax, rdx
0x180015a4a  mov     rcx, r9
0x180015a4d  neg     rax
0x180015a50  mov     rax, rdx
0x180015a53  sbb     ebx, ebx
0x180015a55  sub     rcx, rdx
0x180015a58  not     ebx
0x180015a5a  and     ebx, 80070057h
0x180015a60  neg     rax
0x180015a63  sbb     r8, r8
0x180015a66  and     r8, rcx
0x180015a69  test    rdx, rdx
0x180015a6c  jz      short loc_180015ACA
0x180015a6e  mov     rax, [rsp+6E0h+ppwsz]
0x180015a73  mov     rdx, r9
0x180015a76  sub     rdx, r8
0x180015a79  lea     r8, [rbp+r8*2+5E0h+var_450]
0x180015a81  jz      short loc_180015AA5
0x180015a83  test    rdi, rdi
0x180015a86  jz      short loc_180015AA5
0x180015a88  movzx   ecx, word ptr [rax]
0x180015a8b  test    cx, cx
0x180015a8e  jz      short loc_180015AA5
0x180015a90  mov     [r8], cx
0x180015a94  add     rax, 2
0x180015a98  add     r8, 2
0x180015a9c  dec     rdi
0x180015a9f  sub     rdx, 1
0x180015aa3  jnz     short loc_180015A83
0x180015aa5  mov     rax, rdx
0x180015aa8  lea     rcx, [r8-2]
0x180015aac  neg     rax
0x180015aaf  sbb     ebx, ebx
0x180015ab1  not     ebx
0x180015ab3  and     ebx, 8007007Ah
0x180015ab9  test    rdx, rdx
0x180015abc  cmovnz  rcx, r8
0x180015ac0  mov     [rcx], r12w
0x180015ac4  jnz     loc_180015C85
0x180015aca  mov     rcx, [rsp+6E0h+ppwsz]; pv
0x180015acf  mov     [rsp+6E0h+ppwsz], r12
0x180015ad4  call    cs:__imp_CoTaskMemFree
0x180015adb  nop     dword ptr [rax+rax+00h]
0x180015ae0  test    ebx, ebx
0x180015ae2  js      short loc_180015B19
0x180015ae4  mov     rdx, [rsp+6E0h+lpSubKey]; lpSubKey
0x180015ae9  lea     rax, [rsp+6E0h+hkey]
0x180015aee  mov     r9d, 20119h; samDesired
0x180015af4  mov     [rsp+6E0h+phkResult], rax; phkResult
0x180015af9  xor     r8d, r8d; ulOptions
0x180015afc  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180015b03  call    cs:__imp_RegOpenKeyExW
0x180015b0a  nop     dword ptr [rax+rax+00h]
0x180015b0f  mov     ebx, eax
0x180015b11  test    eax, eax
0x180015b13  jg      loc_180015C2C
0x180015b19  mov     rcx, [rsp+6E0h+lpSubKey]; pv
0x180015b1e  mov     [rsp+6E0h+lpSubKey], r12
0x180015b23  call    cs:__imp_CoTaskMemFree
0x180015b2a  nop     dword ptr [rax+rax+00h]
0x180015b2f  test    ebx, ebx
0x180015b31  js      loc_180015BFE
0x180015b37  mov     r14, r12
0x180015b3a  cmp     esi, 8
0x180015b3d  jz      loc_180015C5F
0x180015b43  jg      loc_180015E23
0x180015b49  mov     ecx, esi
0x180015b4b  test    esi, esi
0x180015b4d  jnz     loc_180015DBD
0x180015b53  lea     rdi, aImage96; "Image96"
0x180015b5a  mov     rcx, [rsp+6E0h+hkey]; hkey
0x180015b5f  lea     rax, [rsp+6E0h+ppwsz]
0x180015b64  mov     [rsp+6E0h+pcbData], rax; pcbData
0x180015b69  mov     r9d, 2; dwFlags
0x180015b6f  lea     rax, [rbp+5E0h+var_660]
0x180015b73  mov     dword ptr [rsp+6E0h+ppwsz], 208h
0x180015b7b  mov     [rsp+6E0h+pvData], rax; pvData
0x180015b80  mov     r8, rdi; lpValue
0x180015b83  xor     edx, edx; lpSubKey
0x180015b85  mov     [rsp+6E0h+phkResult], r12; pdwType
0x180015b8a  call    cs:__imp_RegGetValueW
0x180015b91  nop     dword ptr [rax+rax+00h]
0x180015b96  mov     ebx, eax
0x180015b98  test    eax, eax
0x180015b9a  jnz     loc_180015CA4
0x180015ba0  test    ebx, ebx
0x180015ba2  js      loc_180015D99
0x180015ba8  mov     r8d, 104h
0x180015bae  lea     rdx, [rbp+5E0h+psz]
0x180015bb5  lea     rcx, [rbp+5E0h+var_660]
0x180015bb9  call    cs:__imp_SHExpandEnvironmentStringsW
0x180015bc0  nop     dword ptr [rax+rax+00h]
0x180015bc5  test    eax, eax
0x180015bc7  jz      short loc_180015C3A
0x180015bc9  lea     r14, [rbp+5E0h+psz]
0x180015bd0  mov     rcx, [rsp+6E0h+hkey]; hKey
0x180015bd5  test    rcx, rcx
0x180015bd8  jz      short loc_180015BE6
0x180015bda  call    cs:__imp_RegCloseKey
0x180015be1  nop     dword ptr [rax+rax+00h]
0x180015be6  test    ebx, ebx
0x180015be8  js      short loc_180015BFE
0x180015bea  mov     rdx, r15; ppwsz
0x180015bed  mov     rcx, r14; psz
0x180015bf0  call    cs:__imp_SHStrDupW
0x180015bf7  nop     dword ptr [rax+rax+00h]
0x180015bfc  mov     ebx, eax
0x180015bfe  mov     eax, ebx
0x180015c00  mov     rcx, [rbp+5E0h+var_30]
0x180015c07  xor     rcx, rsp; StackCookie
0x180015c0a  call    __security_check_cookie
0x180015c0f  lea     r11, [rsp+6E0h+var_20]
0x180015c17  mov     rbx, [r11+30h]
0x180015c1b  mov     rsi, [r11+40h]
0x180015c1f  mov     rsp, r11
0x180015c22  pop     r15
0x180015c24  pop     r14
0x180015c26  pop     r12
0x180015c28  pop     rdi
0x180015c29  pop     rbp
0x180015c2a  retn
0x180015c2c  movzx   ebx, ax
0x180015c2f  or      ebx, 80070000h
0x180015c35  jmp     loc_180015B19
0x180015c3a  lea     r14, [rbp+5E0h+var_660]
0x180015c3e  call    cs:__imp_GetLastError
0x180015c45  nop     dword ptr [rax+rax+00h]
0x180015c4a  mov     ebx, eax
0x180015c4c  test    eax, eax
0x180015c4e  jg      short loc_180015C7A
0x180015c50  test    ebx, ebx
0x180015c52  mov     edi, 80004005h
0x180015c57  cmovns  ebx, edi
0x180015c5a  jmp     loc_180015BD0
0x180015c5f  lea     rdi, aVideo192; "Video192"
0x180015c66  jmp     loc_180015B5A
0x180015c6b  lea     rcx, [rsp+6E0h+ppwsz]; ppwsz
0x180015c70  call    ?GetCurrentUsersSidString@@YAJPEAPEAG@Z; GetCurrentUsersSidString(ushort * *)
0x180015c75  jmp     loc_180015A1D
0x180015c7a  movzx   ebx, ax
0x180015c7d  or      ebx, 80070000h
0x180015c83  jmp     short loc_180015C50
0x180015c85  lea     rdx, [rsp+6E0h+lpSubKey]; ppwsz
0x180015c8a  lea     rcx, [rbp+5E0h+var_450]; psz
0x180015c91  call    cs:__imp_SHStrDupW
0x180015c98  nop     dword ptr [rax+rax+00h]
0x180015c9d  mov     ebx, eax
0x180015c9f  jmp     loc_180015ACA
0x180015ca4  mov     [rbp+5E0h+var_660], r12w
0x180015ca9  jle     loc_180015BA0
0x180015caf  movzx   ebx, ax
0x180015cb2  or      ebx, 80070000h
0x180015cb8  jmp     loc_180015BA0
0x180015cbd  mov     edi, 80004005h
0x180015cc2  lea     rcx, [rsp+6E0h+string]; string
0x180015cc7  mov     ebx, edi
0x180015cc9  call    ??$?0$0CK@@StringReference@Internal@Windows@@QEAA@AEAY0CK@$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[42])
0x180015cce  mov     ecx, edi
0x180015cd0  mov     rdx, [rax]
0x180015cd3  call    cs:__imp_RoOriginateError
0x180015cda  nop     dword ptr [rax+rax+00h]
0x180015cdf  mov     ecx, esi
0x180015ce1  call    ?_IsVideoAccountPictureType@@YA_NW4USER_TILE_TYPE@@@Z; _IsVideoAccountPictureType(USER_TILE_TYPE)
0x180015ce6  test    al, al
0x180015ce8  jnz     loc_180015BFE
0x180015cee  mov     rcx, r14; unsigned __int16 *
0x180015cf1  call    ?_IsGuestAccount@@YA_NPEBG@Z; _IsGuestAccount(ushort const *)
0x180015cf6  test    al, al
0x180015cf8  jz      short loc_180015D16
0x180015cfa  lea     rcx, [rbp+5E0h+var_660]; unsigned __int16 *
0x180015cfe  call    ?SHGetDefaultGuestPicturePath@@YAJPEAGK@Z; SHGetDefaultGuestPicturePath(ushort *,ulong)
0x180015d03  mov     ebx, eax
0x180015d05  test    eax, eax
0x180015d07  js      loc_180015BFE
0x180015d0d  lea     r14, [rbp+5E0h+var_660]
0x180015d11  jmp     loc_180015BEA
0x180015d16  mov     ecx, esi
0x180015d18  call    ?_GetLargeSizeForTileType@@YAIW4USER_TILE_TYPE@@@Z; _GetLargeSizeForTileType(USER_TILE_TYPE)
0x180015d1d  lea     r8, [rbp+5E0h+var_660]; unsigned __int16 *
0x180015d21  mov     edx, eax; unsigned int
0x180015d23  call    ?_GetDefaultUserPicturePathBySize@@YAJ_NIPEAGK@Z; _GetDefaultUserPicturePathBySize(bool,uint,ushort *,ulong)
0x180015d28  jmp     short loc_180015D03
0x180015d2a  sub     esi, 4
0x180015d2d  jz      short loc_180015DA2
0x180015d2f  sub     esi, 2
0x180015d32  jz      loc_180015EE2
0x180015d38  sub     esi, 1
0x180015d3b  jz      loc_180015ED6
0x180015d41  cmp     esi, 1
0x180015d44  jz      loc_180015ECA
0x180015d4a  mov     rcx, [rsp+6E0h+hkey]; hkey
0x180015d4f  lea     rax, [rsp+6E0h+ppwsz]
0x180015d54  mov     [rsp+6E0h+pcbData], rax; pcbData
0x180015d59  mov     r9d, 2; dwFlags
0x180015d5f  lea     rax, [rbp+5E0h+var_660]
0x180015d63  mov     dword ptr [rsp+6E0h+ppwsz], 208h
0x180015d6b  mov     [rsp+6E0h+pvData], rax; pvData
0x180015d70  mov     r8, rdi; lpValue
0x180015d73  xor     edx, edx; lpSubKey
0x180015d75  mov     [rsp+6E0h+phkResult], r12; pdwType
0x180015d7a  call    cs:__imp_RegGetValueW
0x180015d81  nop     dword ptr [rax+rax+00h]
0x180015d86  mov     ebx, eax
0x180015d88  test    eax, eax
0x180015d8a  jnz     short loc_180015DAB
0x180015d8c  test    ebx, ebx
0x180015d8e  js      loc_180015BD0
0x180015d94  jmp     loc_180015BA8
0x180015d99  cmp     esi, 4
0x180015d9c  jnz     loc_180015EB2
0x180015da2  lea     rdi, aImage40; "Image40"
0x180015da9  jmp     short loc_180015D4A
0x180015dab  mov     [rbp+5E0h+var_660], r12w
0x180015db0  jle     short loc_180015D8C
0x180015db2  movzx   ebx, ax
0x180015db5  or      ebx, 80070000h
0x180015dbb  jmp     short loc_180015D8C
0x180015dbd  sub     ecx, 1
0x180015dc0  jz      short loc_180015E17
0x180015dc2  sub     ecx, 1
0x180015dc5  jz      short loc_180015E0B
0x180015dc7  sub     ecx, 2
0x180015dca  jz      short loc_180015DFF
0x180015dcc  sub     ecx, 1
0x180015dcf  jz      short loc_180015DF3
0x180015dd1  sub     ecx, 1
0x180015dd4  jz      short loc_180015DE7
  ... truncated ...
```
