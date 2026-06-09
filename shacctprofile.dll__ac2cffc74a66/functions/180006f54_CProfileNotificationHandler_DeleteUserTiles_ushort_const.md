# CProfileNotificationHandler::_DeleteUserTiles(ushort const *)

- ea: `0x180006f54`
- end: `0x18000719f`
- name: `?_DeleteUserTiles@CProfileNotificationHandler@@AEAAJPEBG@Z`
- size: `587`
- prototype: `__int64 __fastcall(CProfileNotificationHandler *this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, reparse_path, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180006890`

## callees

- `0x180002230`
- `0x180005830`
- `0x180006f54`
- `0x180007770`
- `0x1800088f8`

## import_xrefs

- `SHCORE!SHStrDupW` at `0x180006fef`
- `SHCORE!SHStrDupW` at `0x180007029`
- `SHCORE!SHStrDupW` at `0x1800070ed`
- `SHCORE!SHStrDupW` at `0x180007126`
- `SHCORE!SHStrDupW` at `0x180006fef`
- `SHCORE!SHStrDupW` at `0x180007029`
- `SHCORE!SHStrDupW` at `0x1800070ed`
- `SHCORE!SHStrDupW` at `0x180007126`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x180007057`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x180007057`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x180007110`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x180007110`
- `SHELL32!SHGetKnownFolderPath` at `0x18000707b`
- `SHELL32!SHGetKnownFolderPath` at `0x18000707b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000703b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180007138`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180007148`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180007168`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180007178`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000703b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180007138`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180007148`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180007168`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180007178`

## pseudocode

```c
__int64 __fastcall CProfileNotificationHandler::_DeleteUserTiles(
        CProfileNotificationHandler *this,
        const unsigned __int16 *a2)
{
  const wchar_t *v2; // r8
  __int64 v3; // rsi
  WCHAR *v4; // rax
  __int64 v6; // rcx
  __int64 v7; // rdx
  WCHAR *v8; // rcx
  HRESULT CurrentUsersSidString; // eax
  HRESULT v10; // ebx
  LPWSTR v11; // rcx
  HRESULT v12; // ebx
  PWSTR v13; // rax
  WCHAR *v14; // r8
  __int64 v15; // rdx
  WCHAR *v16; // rcx
  HRESULT v17; // eax
  LPWSTR v18; // rcx
  PWSTR v19; // rcx
  LPWSTR v20; // rcx
  LPWSTR v21; // rcx
  LPWSTR ppwsz; // [rsp+20h] [rbp-E0h] BYREF
  PWSTR ppszPath; // [rsp+28h] [rbp-D8h] BYREF
  LPWSTR v25; // [rsp+30h] [rbp-D0h] BYREF
  LPWSTR v26; // [rsp+38h] [rbp-C8h] BYREF
  WCHAR psz[264]; // [rsp+40h] [rbp-C0h] BYREF

  v2 = L"Software\\Microsoft\\Windows\\CurrentVersion\\AccountPicture\\Users\\";
  v3 = 2147483646;
  v26 = 0;
  v4 = psz;
  v6 = 2147483646;
  v7 = 260;
  do
  {
    if ( !v6 )
      break;
    if ( !*v2 )
      break;
    *v4++ = *v2++;
    --v6;
    --v7;
  }
  while ( v7 );
  v8 = v4 - 1;
  if ( v7 )
    v8 = v4;
  *v8 = 0;
  if ( v7 )
  {
    ppwsz = 0;
    if ( a2 )
      CurrentUsersSidString = SHStrDupW(a2, &ppwsz);
    else
      CurrentUsersSidString = GetCurrentUsersSidString(&ppwsz);
    v10 = CurrentUsersSidString;
    if ( CurrentUsersSidString >= 0 )
    {
      v10 = StringCchCatW(psz, 0x104u, ppwsz);
      if ( v10 >= 0 )
        v10 = SHStrDupW(psz, &v26);
    }
    v11 = ppwsz;
    ppwsz = 0;
    CoTaskMemFree(v11);
    if ( v10 >= 0 )
      RegDeleteKeyExW(HKEY_LOCAL_MACHINE, v26, 0, 0);
  }
  v25 = 0;
  ppszPath = 0;
  v12 = SHGetKnownFolderPath(&FOLDERID_PublicUserTiles, 0x9000u, 0, &ppszPath);
  if ( v12 >= 0 )
  {
    v13 = ppszPath;
    v14 = psz;
    v15 = 260;
    do
    {
      if ( !v3 )
        break;
      if ( !*v13 )
        break;
      *v14++ = *v13++;
      --v3;
      --v15;
    }
    while ( v15 );
    v16 = v14 - 1;
    v12 = v15 == 0 ? 0x8007007A : 0;
    if ( v15 )
      v16 = v14;
    *v16 = 0;
    if ( v15 )
    {
      ppwsz = 0;
      if ( a2 )
        v17 = SHStrDupW(a2, &ppwsz);
      else
        v17 = GetCurrentUsersSidString(&ppwsz);
      v12 = v17;
      if ( v17 >= 0 )
      {
        v12 = PathCchAppend(psz, 0x104u, a2);
        if ( v12 >= 0 )
          v12 = SHStrDupW(psz, &v25);
      }
      v18 = ppwsz;
      ppwsz = 0;
      CoTaskMemFree(v18);
    }
  }
  v19 = ppszPath;
  ppszPath = 0;
  CoTaskMemFree(v19);
  if ( v12 >= 0 )
    v12 = RecursiveRemoveDirectory(v25);
  v20 = v25;
  v25 = 0;
  CoTaskMemFree(v20);
  v21 = v26;
  v26 = 0;
  CoTaskMemFree(v21);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x180006f54  push    rbp
0x180006f56  push    rbx
0x180006f57  push    rsi
0x180006f58  push    rdi
0x180006f59  push    r14
0x180006f5b  push    r15
0x180006f5d  lea     rbp, [rsp-168h]
0x180006f65  sub     rsp, 268h
0x180006f6c  mov     rax, cs:__security_cookie
0x180006f73  xor     rax, rsp
0x180006f76  mov     [rbp+190h+var_40], rax
0x180006f7d  xor     r14d, r14d
0x180006f80  lea     r8, aSoftwareMicros_0; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180006f87  mov     esi, 7FFFFFFEh
0x180006f8c  mov     [rsp+290h+var_258], r14
0x180006f91  mov     r15d, 104h
0x180006f97  lea     rax, [rsp+290h+psz]
0x180006f9c  mov     rdi, rdx
0x180006f9f  mov     ecx, esi
0x180006fa1  mov     edx, r15d
0x180006fa4  test    rcx, rcx
0x180006fa7  jz      short loc_180006FC8
0x180006fa9  movzx   r9d, word ptr [r8]
0x180006fad  test    r9w, r9w
0x180006fb1  jz      short loc_180006FC8
0x180006fb3  mov     [rax], r9w
0x180006fb7  add     r8, 2
0x180006fbb  add     rax, 2
0x180006fbf  dec     rcx
0x180006fc2  sub     rdx, 1
0x180006fc6  jnz     short loc_180006FA4
0x180006fc8  test    rdx, rdx
0x180006fcb  lea     rcx, [rax-2]
0x180006fcf  cmovnz  rcx, rax
0x180006fd3  mov     [rcx], r14w
0x180006fd7  jz      loc_18000705D
0x180006fdd  mov     [rsp+290h+ppwsz], r14
0x180006fe2  test    rdi, rdi
0x180006fe5  jz      short loc_180006FF7
0x180006fe7  lea     rdx, [rsp+290h+ppwsz]; ppwsz
0x180006fec  mov     rcx, rdi; psz
0x180006fef  call    cs:__imp_SHStrDupW
0x180006ff5  jmp     short loc_180007001
0x180006ff7  lea     rcx, [rsp+290h+ppwsz]; ppwsz
0x180006ffc  call    ?GetCurrentUsersSidString@@YAJPEAPEAG@Z; GetCurrentUsersSidString(ushort * *)
0x180007001  mov     ebx, eax
0x180007003  test    eax, eax
0x180007005  js      short loc_180007031
0x180007007  mov     r8, [rsp+290h+ppwsz]; unsigned __int16 *
0x18000700c  lea     rcx, [rsp+290h+psz]; unsigned __int16 *
0x180007011  mov     rdx, r15; unsigned __int64
0x180007014  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180007019  mov     ebx, eax
0x18000701b  test    eax, eax
0x18000701d  js      short loc_180007031
0x18000701f  lea     rdx, [rsp+290h+var_258]; ppwsz
0x180007024  lea     rcx, [rsp+290h+psz]; psz
0x180007029  call    cs:__imp_SHStrDupW
0x18000702f  mov     ebx, eax
0x180007031  mov     rcx, [rsp+290h+ppwsz]; pv
0x180007036  mov     [rsp+290h+ppwsz], r14
0x18000703b  call    cs:__imp_CoTaskMemFree
0x180007041  test    ebx, ebx
0x180007043  js      short loc_18000705D
0x180007045  mov     rdx, [rsp+290h+var_258]; lpSubKey
0x18000704a  xor     r9d, r9d; Reserved
0x18000704d  xor     r8d, r8d; samDesired
0x180007050  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180007057  call    cs:__imp_RegDeleteKeyExW
0x18000705d  lea     r9, [rsp+290h+ppszPath]; ppszPath
0x180007062  mov     [rsp+290h+var_260], r14
0x180007067  xor     r8d, r8d; hToken
0x18000706a  mov     [rsp+290h+ppszPath], r14
0x18000706f  mov     edx, 9000h; dwFlags
0x180007074  lea     rcx, FOLDERID_PublicUserTiles; rfid
0x18000707b  call    cs:__imp_SHGetKnownFolderPath
0x180007081  mov     ebx, eax
0x180007083  test    eax, eax
0x180007085  js      loc_18000713E
0x18000708b  mov     rax, [rsp+290h+ppszPath]
0x180007090  lea     r8, [rsp+290h+psz]
0x180007095  mov     rdx, r15
0x180007098  test    rsi, rsi
0x18000709b  jz      short loc_1800070BA
0x18000709d  movzx   ecx, word ptr [rax]
0x1800070a0  test    cx, cx
0x1800070a3  jz      short loc_1800070BA
0x1800070a5  mov     [r8], cx
0x1800070a9  add     rax, 2
0x1800070ad  add     r8, 2
0x1800070b1  dec     rsi
0x1800070b4  sub     rdx, 1
0x1800070b8  jnz     short loc_180007098
0x1800070ba  mov     rax, rdx
0x1800070bd  lea     rcx, [r8-2]
0x1800070c1  neg     rax
0x1800070c4  sbb     ebx, ebx
0x1800070c6  not     ebx
0x1800070c8  and     ebx, 8007007Ah
0x1800070ce  test    rdx, rdx
0x1800070d1  cmovnz  rcx, r8
0x1800070d5  mov     [rcx], r14w
0x1800070d9  jz      short loc_18000713E
0x1800070db  mov     [rsp+290h+ppwsz], r14
0x1800070e0  test    rdi, rdi
0x1800070e3  jz      short loc_1800070F5
0x1800070e5  lea     rdx, [rsp+290h+ppwsz]; ppwsz
0x1800070ea  mov     rcx, rdi; psz
0x1800070ed  call    cs:__imp_SHStrDupW
0x1800070f3  jmp     short loc_1800070FF
0x1800070f5  lea     rcx, [rsp+290h+ppwsz]; ppwsz
0x1800070fa  call    ?GetCurrentUsersSidString@@YAJPEAPEAG@Z; GetCurrentUsersSidString(ushort * *)
0x1800070ff  mov     ebx, eax
0x180007101  test    eax, eax
0x180007103  js      short loc_18000712E
0x180007105  mov     r8, rdi; pszMore
0x180007108  lea     rcx, [rsp+290h+psz]; pszPath
0x18000710d  mov     rdx, r15; cchPath
0x180007110  call    cs:__imp_PathCchAppend
0x180007116  mov     ebx, eax
0x180007118  test    eax, eax
0x18000711a  js      short loc_18000712E
0x18000711c  lea     rdx, [rsp+290h+var_260]; ppwsz
0x180007121  lea     rcx, [rsp+290h+psz]; psz
0x180007126  call    cs:__imp_SHStrDupW
0x18000712c  mov     ebx, eax
0x18000712e  mov     rcx, [rsp+290h+ppwsz]; pv
0x180007133  mov     [rsp+290h+ppwsz], r14
0x180007138  call    cs:__imp_CoTaskMemFree
0x18000713e  mov     rcx, [rsp+290h+ppszPath]; pv
0x180007143  mov     [rsp+290h+ppszPath], r14
0x180007148  call    cs:__imp_CoTaskMemFree
0x18000714e  test    ebx, ebx
0x180007150  js      short loc_18000715E
0x180007152  mov     rcx, [rsp+290h+var_260]; unsigned __int16 *
0x180007157  call    ?RecursiveRemoveDirectory@@YAJPEBG@Z; RecursiveRemoveDirectory(ushort const *)
0x18000715c  mov     ebx, eax
0x18000715e  mov     rcx, [rsp+290h+var_260]; pv
0x180007163  mov     [rsp+290h+var_260], r14
0x180007168  call    cs:__imp_CoTaskMemFree
0x18000716e  mov     rcx, [rsp+290h+var_258]; pv
0x180007173  mov     [rsp+290h+var_258], r14
0x180007178  call    cs:__imp_CoTaskMemFree
0x18000717e  mov     eax, ebx
0x180007180  mov     rcx, [rbp+190h+var_40]
0x180007187  xor     rcx, rsp; StackCookie
0x18000718a  call    __security_check_cookie
0x18000718f  add     rsp, 268h
0x180007196  pop     r15
0x180007198  pop     r14
0x18000719a  pop     rdi
0x18000719b  pop     rsi
0x18000719c  pop     rbx
0x18000719d  pop     rbp
0x18000719e  retn
```
