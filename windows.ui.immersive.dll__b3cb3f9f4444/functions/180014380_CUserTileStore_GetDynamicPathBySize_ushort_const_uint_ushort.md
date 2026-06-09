# CUserTileStore::GetDynamicPathBySize(ushort const *,uint,ushort * *)

- ea: `0x180014380`
- end: `0x1800148d0`
- name: `?GetDynamicPathBySize@CUserTileStore@@UEAAJPEBGIPEAPEAG@Z`
- size: `1360`
- prototype: `int(CUserTileStore *__hidden this, const unsigned __int16 *, unsigned int, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callees

- `0x180014380`
- `0x1800148d8`
- `0x1800156f0`
- `0x180015fc0`
- `0x18003cdf8`
- `0x18004ad7c`
- `0x18004b1e4`
- `0x18004c40c`
- `0x180054130`
- `0x1800c3a44`
- `0x1800c3a9c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800147ed`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800147ed`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001481c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001481c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001457e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001457e`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800146f1`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180014799`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800146f1`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180014799`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!SHExpandEnvironmentStringsW` at `0x1800147d0`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!SHExpandEnvironmentStringsW` at `0x1800147d0`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x18001446a`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x180014537`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x180014894`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x18001446a`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x180014537`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x180014894`
- `SHCORE!__imp_SHWindowsPolicy` at `0x1800143cf`
- `SHCORE!__imp_SHWindowsPolicy` at `0x1800143cf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001454f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800145a3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001454f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800145a3`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18001467a`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180014844`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18001467a`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180014844`

## pseudocode

```c
__int64 __fastcall CUserTileStore::GetDynamicPathBySize(
        CUserTileStore *this,
        const unsigned __int16 *a2,
        unsigned int a3,
        unsigned __int16 **a4)
{
  int TileTypeForDynamicSize; // eax
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
  LPWSTR v27; // rcx
  const unsigned __int16 *v28; // rdx
  unsigned __int16 *v29; // r14
  const WCHAR *v30; // rdi
  _QWORD *v31; // rax
  LSTATUS ValueW; // eax
  const WCHAR *v33; // rdi
  LSTATUS v34; // eax
  signed int LastError; // eax
  _QWORD *v36; // rax
  unsigned int v37; // edx
  int DefaultUserPicturePathBySize; // eax
  unsigned int LargeSizeForTileType; // eax
  bool v40; // cl
  unsigned int v41; // r9d
  LPWSTR ppwsz; // [rsp+40h] [rbp-C0h] BYREF
  LPWSTR v44; // [rsp+48h] [rbp-B8h] BYREF
  HKEY hkey; // [rsp+50h] [rbp-B0h] BYREF
  HSTRING string[5]; // [rsp+58h] [rbp-A8h] BYREF
  unsigned __int16 pvData[264]; // [rsp+80h] [rbp-80h] BYREF
  WCHAR psz[264]; // [rsp+290h] [rbp+190h] BYREF
  _BYTE v49[528]; // [rsp+4A0h] [rbp+3A0h] BYREF

  TileTypeForDynamicSize = _GetTileTypeForDynamicSize(a3);
  *a4 = 0;
  v7 = TileTypeForDynamicSize;
  if ( !(unsigned int)SHWindowsPolicy(POLID_UseDefaultTile) && v7 != 3 )
  {
    v9 = 2147483646;
    hkey = 0;
    v10 = 2147483646;
    v44 = 0;
    v11 = L"Software\\Microsoft\\Windows\\CurrentVersion\\AccountPicture\\Users\\";
    v12 = 260;
    v13 = psz;
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
        v17 = psz;
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
          v23 = &psz[v19];
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
            v15 = SHStrDupW(psz, &v44);
        }
      }
      v25 = ppwsz;
      ppwsz = 0;
      CoTaskMemFree(v25);
      if ( v15 >= 0 )
      {
        v26 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v44, 0, 0x20119u, &hkey);
        v15 = v26;
        if ( v26 > 0 )
          v15 = (unsigned __int16)v26 | 0x80070000;
      }
    }
    v27 = v44;
    v44 = 0;
    CoTaskMemFree(v27);
    if ( v15 < 0 )
      return (unsigned int)v15;
    v29 = 0;
    if ( v7 == 8 )
    {
      v30 = L"Video192";
    }
    else if ( v7 > 8 )
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
          goto LABEL_53;
      }
    }
    else if ( v7 )
    {
      switch ( v7 )
      {
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
LABEL_53:
          v31 = (_QWORD *)Windows::Internal::StringReference::StringReference(
                            string,
                            (const unsigned __int16 (*)[26])v28);
          RoOriginateError(2147500037LL, *v31);
          v15 = -2147467259;
          goto LABEL_82;
      }
    }
    else
    {
      v30 = L"Image96";
    }
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
      goto LABEL_96;
    switch ( v7 )
    {
      case 4:
        v33 = L"Image40";
        break;
      case 6:
        v33 = L"Image96";
        break;
      case 7:
        v33 = L"Image200";
        break;
      case 8:
        v33 = L"Video200";
        break;
      default:
        goto LABEL_82;
    }
    LODWORD(ppwsz) = 520;
    v34 = RegGetValueW(hkey, 0, v33, 2u, 0, pvData, (LPDWORD)&ppwsz);
    v15 = v34;
    if ( v34 )
    {
      pvData[0] = 0;
      if ( v34 > 0 )
        v15 = (unsigned __int16)v34 | 0x80070000;
    }
    if ( v15 >= 0 )
    {
LABEL_96:
      if ( (unsigned int)SHExpandEnvironmentStringsW(pvData, v49, 260) )
      {
        v29 = (unsigned __int16 *)v49;
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
LABEL_82:
    if ( hkey )
      RegCloseKey(hkey);
    if ( v15 >= 0 )
      return (unsigned int)SHStrDupW(v29, a4);
    return (unsigned int)v15;
  }
  v15 = -2147467259;
  v36 = (_QWORD *)Windows::Internal::StringReference::StringReference(string, (const unsigned __int16 (*)[42])v8);
  RoOriginateError(2147500037LL, *v36);
  if ( !(unsigned __int8)_IsVideoAccountPictureType((unsigned int)v7) )
  {
    if ( _IsGuestAccount(a2) )
    {
      DefaultUserPicturePathBySize = SHGetDefaultGuestPicturePath(pvData, v37);
    }
    else
    {
      LargeSizeForTileType = _GetLargeSizeForTileType((unsigned int)v7);
      DefaultUserPicturePathBySize = _GetDefaultUserPicturePathBySize(v40, LargeSizeForTileType, pvData, v41);
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
0x180014380  mov     [rsp-8+arg_0], rbx
0x180014385  mov     [rsp-8+arg_10], rsi
0x18001438a  push    rbp
0x18001438b  push    rdi
0x18001438c  push    r12
0x18001438e  push    r14
0x180014390  push    r15
0x180014392  lea     rbp, [rsp-5C0h]
0x18001439a  sub     rsp, 6C0h
0x1800143a1  mov     rax, cs:__security_cookie
0x1800143a8  xor     rax, rsp
0x1800143ab  mov     [rbp+5E0h+var_30], rax
0x1800143b2  mov     ecx, r8d
0x1800143b5  mov     r15, r9
0x1800143b8  mov     r14, rdx
0x1800143bb  call    ?_GetTileTypeForDynamicSize@@YA?AW4USER_TILE_TYPE@@I@Z; _GetTileTypeForDynamicSize(uint)
0x1800143c0  xor     r12d, r12d
0x1800143c3  lea     rcx, POLID_UseDefaultTile
0x1800143ca  mov     [r15], r12
0x1800143cd  mov     esi, eax
0x1800143cf  call    cs:__imp_SHWindowsPolicy
0x1800143d6  nop     dword ptr [rax+rax+00h]
0x1800143db  test    eax, eax
0x1800143dd  jnz     loc_18001482E
0x1800143e3  cmp     esi, 3
0x1800143e6  jz      loc_18001482E
0x1800143ec  mov     edi, 7FFFFFFEh
0x1800143f1  mov     [rsp+6E0h+hkey], r12
0x1800143f6  mov     eax, edi
0x1800143f8  mov     [rsp+6E0h+var_698], r12
0x1800143fd  lea     rcx, aSoftwareMicros_5; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180014404  mov     r8d, 104h
0x18001440a  lea     r9, [rbp+5E0h+psz]
0x180014411  test    rax, rax
0x180014414  jz      short loc_180014433
0x180014416  movzx   edx, word ptr [rcx]
0x180014419  test    dx, dx
0x18001441c  jz      short loc_180014433
0x18001441e  mov     [r9], dx
0x180014422  add     rcx, 2
0x180014426  add     r9, 2
0x18001442a  dec     rax
0x18001442d  sub     r8, 1
0x180014431  jnz     short loc_180014411
0x180014433  mov     rax, r8
0x180014436  lea     rdx, [r9-2]
0x18001443a  neg     rax
0x18001443d  sbb     ebx, ebx
0x18001443f  not     ebx
0x180014441  and     ebx, 8007007Ah
0x180014447  test    r8, r8
0x18001444a  cmovnz  rdx, r9
0x18001444e  mov     [rdx], r12w
0x180014452  jz      loc_180014599
0x180014458  mov     [rsp+6E0h+ppwsz], r12
0x18001445d  test    r14, r14
0x180014460  jz      short loc_180014478
0x180014462  lea     rdx, [rsp+6E0h+ppwsz]; ppwsz
0x180014467  mov     rcx, r14; psz
0x18001446a  call    cs:__imp_SHStrDupW
0x180014471  nop     dword ptr [rax+rax+00h]
0x180014476  jmp     short loc_180014482
0x180014478  lea     rcx, [rsp+6E0h+ppwsz]; ppwsz
0x18001447d  call    ?GetCurrentUsersSidString@@YAJPEAPEAG@Z; GetCurrentUsersSidString(ushort * *)
0x180014482  mov     ebx, eax
0x180014484  test    eax, eax
0x180014486  js      loc_180014545
0x18001448c  mov     r9d, 104h
0x180014492  lea     rax, [rbp+5E0h+psz]
0x180014499  mov     edx, r9d
0x18001449c  cmp     [rax], r12w
0x1800144a0  jz      short loc_1800144AC
0x1800144a2  add     rax, 2
0x1800144a6  sub     rdx, 1
0x1800144aa  jnz     short loc_18001449C
0x1800144ac  mov     rax, rdx
0x1800144af  mov     rcx, r9
0x1800144b2  neg     rax
0x1800144b5  mov     rax, rdx
0x1800144b8  sbb     ebx, ebx
0x1800144ba  sub     rcx, rdx
0x1800144bd  not     ebx
0x1800144bf  and     ebx, 80070057h
0x1800144c5  neg     rax
0x1800144c8  sbb     r8, r8
0x1800144cb  and     r8, rcx
0x1800144ce  test    rdx, rdx
0x1800144d1  jz      short loc_180014545
0x1800144d3  mov     rax, [rsp+6E0h+ppwsz]
0x1800144d8  mov     rdx, r9
0x1800144db  sub     rdx, r8
0x1800144de  lea     r8, [rbp+r8*2+5E0h+psz]
0x1800144e6  jz      short loc_18001450A
0x1800144e8  test    rdi, rdi
0x1800144eb  jz      short loc_18001450A
0x1800144ed  movzx   ecx, word ptr [rax]
0x1800144f0  test    cx, cx
0x1800144f3  jz      short loc_18001450A
0x1800144f5  mov     [r8], cx
0x1800144f9  add     rax, 2
0x1800144fd  add     r8, 2
0x180014501  dec     rdi
0x180014504  sub     rdx, 1
0x180014508  jnz     short loc_1800144E8
0x18001450a  mov     rax, rdx
0x18001450d  lea     rcx, [r8-2]
0x180014511  neg     rax
0x180014514  sbb     ebx, ebx
0x180014516  not     ebx
0x180014518  and     ebx, 8007007Ah
0x18001451e  test    rdx, rdx
0x180014521  cmovnz  rcx, r8
0x180014525  mov     [rcx], r12w
0x180014529  jz      short loc_180014545
0x18001452b  lea     rdx, [rsp+6E0h+var_698]; ppwsz
0x180014530  lea     rcx, [rbp+5E0h+psz]; psz
0x180014537  call    cs:__imp_SHStrDupW
0x18001453e  nop     dword ptr [rax+rax+00h]
0x180014543  mov     ebx, eax
0x180014545  mov     rcx, [rsp+6E0h+ppwsz]; pv
0x18001454a  mov     [rsp+6E0h+ppwsz], r12
0x18001454f  call    cs:__imp_CoTaskMemFree
0x180014556  nop     dword ptr [rax+rax+00h]
0x18001455b  test    ebx, ebx
0x18001455d  js      short loc_180014599
0x18001455f  mov     rdx, [rsp+6E0h+var_698]; lpSubKey
0x180014564  lea     rax, [rsp+6E0h+hkey]
0x180014569  mov     r9d, 20119h; samDesired
0x18001456f  mov     [rsp+6E0h+phkResult], rax; phkResult
0x180014574  xor     r8d, r8d; ulOptions
0x180014577  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001457e  call    cs:__imp_RegOpenKeyExW
0x180014585  nop     dword ptr [rax+rax+00h]
0x18001458a  mov     ebx, eax
0x18001458c  test    eax, eax
0x18001458e  jle     short loc_180014599
0x180014590  movzx   ebx, ax
0x180014593  or      ebx, 80070000h
0x180014599  mov     rcx, [rsp+6E0h+var_698]; pv
0x18001459e  mov     [rsp+6E0h+var_698], r12
0x1800145a3  call    cs:__imp_CoTaskMemFree
0x1800145aa  nop     dword ptr [rax+rax+00h]
0x1800145af  test    ebx, ebx
0x1800145b1  js      loc_1800148A2
0x1800145b7  mov     r14, r12
0x1800145ba  cmp     esi, 8
0x1800145bd  jz      short loc_18001463D
0x1800145bf  jg      loc_180014646
0x1800145c5  mov     ecx, esi
0x1800145c7  test    esi, esi
0x1800145c9  jz      short loc_180014631
0x1800145cb  sub     ecx, 1
0x1800145ce  jz      short loc_180014625
0x1800145d0  sub     ecx, 1
0x1800145d3  jz      short loc_180014619
0x1800145d5  sub     ecx, 2
0x1800145d8  jz      short loc_18001460D
0x1800145da  sub     ecx, 1
0x1800145dd  jz      short loc_180014601
0x1800145df  sub     ecx, 1
0x1800145e2  jz      short loc_1800145F5
0x1800145e4  cmp     ecx, 1
0x1800145e7  jnz     short loc_180014666
0x1800145e9  lea     rdi, aImage192; "Image192"
0x1800145f0  jmp     loc_1800146C1
0x1800145f5  lea     rdi, aImage48; "Image48"
0x1800145fc  jmp     loc_1800146C1
0x180014601  lea     rdi, aImage40; "Image40"
0x180014608  jmp     loc_1800146C1
0x18001460d  lea     rdi, aImage32; "Image32"
0x180014614  jmp     loc_1800146C1
0x180014619  lea     rdi, aVideo448; "Video448"
0x180014620  jmp     loc_1800146C1
0x180014625  lea     rdi, aImage448; "Image448"
0x18001462c  jmp     loc_1800146C1
0x180014631  lea     rdi, aImage96; "Image96"
0x180014638  jmp     loc_1800146C1
0x18001463d  lea     rdi, aVideo192; "Video192"
0x180014644  jmp     short loc_1800146C1
0x180014646  mov     ecx, esi
0x180014648  sub     ecx, 9
0x18001464b  jz      short loc_1800146BA
0x18001464d  sub     ecx, 1
0x180014650  jz      short loc_1800146B1
0x180014652  sub     ecx, 1
0x180014655  jz      short loc_1800146A8
0x180014657  sub     ecx, 1
0x18001465a  jz      short loc_18001469F
0x18001465c  sub     ecx, 1
0x18001465f  jz      short loc_180014696
0x180014661  cmp     ecx, 1
0x180014664  jz      short loc_18001468D
0x180014666  lea     rcx, [rsp+6E0h+string]; string
0x18001466b  call    ??$?0$0BK@@StringReference@Internal@Windows@@QEAA@AEAY0BK@$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[26])
0x180014670  mov     edi, 80004005h
0x180014675  mov     ecx, edi
0x180014677  mov     rdx, [rax]
0x18001467a  call    cs:__imp_RoOriginateError
0x180014681  nop     dword ptr [rax+rax+00h]
0x180014686  mov     ebx, edi
0x180014688  jmp     loc_180014812
0x18001468d  lea     rdi, aImage1080; "Image1080"
0x180014694  jmp     short loc_1800146C1
0x180014696  lea     rdi, aImage424; "Image424"
0x18001469d  jmp     short loc_1800146C1
0x18001469f  lea     rdi, aImage208; "Image208"
0x1800146a6  jmp     short loc_1800146C1
0x1800146a8  lea     rdi, aImage64; "Image64"
0x1800146af  jmp     short loc_1800146C1
0x1800146b1  lea     rdi, aVideo240; "Video240"
0x1800146b8  jmp     short loc_1800146C1
0x1800146ba  lea     rdi, aImage240; "Image240"
0x1800146c1  mov     rcx, [rsp+6E0h+hkey]; hkey
0x1800146c6  lea     rax, [rsp+6E0h+ppwsz]
0x1800146cb  mov     [rsp+6E0h+pcbData], rax; pcbData
0x1800146d0  mov     r9d, 2; dwFlags
0x1800146d6  lea     rax, [rbp+5E0h+var_660]
0x1800146da  mov     dword ptr [rsp+6E0h+ppwsz], 208h
0x1800146e2  mov     [rsp+6E0h+pvData], rax; pvData
0x1800146e7  mov     r8, rdi; lpValue
0x1800146ea  xor     edx, edx; lpSubKey
0x1800146ec  mov     [rsp+6E0h+phkResult], r12; pdwType
0x1800146f1  call    cs:__imp_RegGetValueW
0x1800146f8  nop     dword ptr [rax+rax+00h]
0x1800146fd  mov     ebx, eax
0x1800146ff  test    eax, eax
0x180014701  jz      short loc_180014713
0x180014703  mov     [rbp+5E0h+var_660], r12w
0x180014708  jle     short loc_180014713
0x18001470a  movzx   ebx, ax
0x18001470d  or      ebx, 80070000h
0x180014713  test    ebx, ebx
0x180014715  jns     loc_1800147BF
0x18001471b  cmp     esi, 4
0x18001471e  jz      short loc_180014762
0x180014720  cmp     esi, 6
0x180014723  jz      short loc_180014759
0x180014725  cmp     esi, 7
0x180014728  jz      short loc_180014750
0x18001472a  cmp     esi, 8
0x18001472d  jnz     loc_180014812
0x180014733  sub     esi, 4
0x180014736  jz      short loc_180014762
0x180014738  sub     esi, 2
0x18001473b  jz      short loc_180014759
0x18001473d  sub     esi, 1
0x180014740  jz      short loc_180014750
0x180014742  cmp     esi, 1
0x180014745  jnz     short loc_180014769
0x180014747  lea     rdi, aVideo200; "Video200"
0x18001474e  jmp     short loc_180014769
0x180014750  lea     rdi, aImage200; "Image200"
0x180014757  jmp     short loc_180014769
0x180014759  lea     rdi, aImage96; "Image96"
0x180014760  jmp     short loc_180014769
0x180014762  lea     rdi, aImage40; "Image40"
0x180014769  mov     rcx, [rsp+6E0h+hkey]; hkey
0x18001476e  lea     rax, [rsp+6E0h+ppwsz]
0x180014773  mov     [rsp+6E0h+pcbData], rax; pcbData
0x180014778  mov     r9d, 2; dwFlags
0x18001477e  lea     rax, [rbp+5E0h+var_660]
0x180014782  mov     dword ptr [rsp+6E0h+ppwsz], 208h
0x18001478a  mov     [rsp+6E0h+pvData], rax; pvData
0x18001478f  mov     r8, rdi; lpValue
0x180014792  xor     edx, edx; lpSubKey
0x180014794  mov     [rsp+6E0h+phkResult], r12; pdwType
0x180014799  call    cs:__imp_RegGetValueW
0x1800147a0  nop     dword ptr [rax+rax+00h]
0x1800147a5  mov     ebx, eax
0x1800147a7  test    eax, eax
0x1800147a9  jz      short loc_1800147BB
0x1800147ab  mov     [rbp+5E0h+var_660], r12w
0x1800147b0  jle     short loc_1800147BB
0x1800147b2  movzx   ebx, ax
0x1800147b5  or      ebx, 80070000h
0x1800147bb  test    ebx, ebx
0x1800147bd  js      short loc_180014812
0x1800147bf  mov     r8d, 104h
0x1800147c5  lea     rdx, [rbp+5E0h+var_240]
0x1800147cc  lea     rcx, [rbp+5E0h+var_660]
0x1800147d0  call    cs:__imp_SHExpandEnvironmentStringsW
0x1800147d7  nop     dword ptr [rax+rax+00h]
0x1800147dc  test    eax, eax
0x1800147de  jz      short loc_1800147E9
0x1800147e0  lea     r14, [rbp+5E0h+var_240]
0x1800147e7  jmp     short loc_180014812
0x1800147e9  lea     r14, [rbp+5E0h+var_660]
0x1800147ed  call    cs:__imp_GetLastError
0x1800147f4  nop     dword ptr [rax+rax+00h]
0x1800147f9  mov     ebx, eax
0x1800147fb  test    eax, eax
0x1800147fd  jle     short loc_180014808
0x1800147ff  movzx   ebx, ax
0x180014802  or      ebx, 80070000h
0x180014808  test    ebx, ebx
0x18001480a  mov     edi, 80004005h
0x18001480f  cmovns  ebx, edi
0x180014812  mov     rcx, [rsp+6E0h+hkey]; hKey
0x180014817  test    rcx, rcx
0x18001481a  jz      short loc_180014828
  ... truncated ...
```
