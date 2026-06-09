# BackupUserData(ushort const *,ushort *,ushort const *)

- ea: `0x18002fc14`
- end: `0x1800300c4`
- name: `?BackupUserData@@YAJPEBGPEAG0@Z`
- size: `1200`
- prototype: `void __fastcall __noreturn(LPCWSTR lpSubKey, WCHAR *lpString1, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180032ac4`

## callees

- `0x180006df4`
- `0x180006eb8`
- `0x18002fc14`
- `0x1800305f4`
- `0x1800307cc`
- `0x18007728a`
- `0x1800772c0`

## import_xrefs

- `SHELL32!SHFileOperationW` at `0x18002ffda`
- `SHELL32!SHFileOperationW` at `0x18002ffda`
- `SHLWAPI!PathRemoveBackslashW` at `0x18002feb8`
- `SHLWAPI!PathRemoveBackslashW` at `0x18002ff03`
- `SHLWAPI!PathRemoveBackslashW` at `0x18002feb8`
- `SHLWAPI!PathRemoveBackslashW` at `0x18002ff03`
- `SHLWAPI!PathFindFileNameW` at `0x18002fed0`
- `SHLWAPI!PathFindFileNameW` at `0x18002fed0`
- `SHLWAPI!PathCommonPrefixW` at `0x18002ff1b`
- `SHLWAPI!PathCommonPrefixW` at `0x18002ff1b`
- `SHLWAPI!PathIsFileSpecW` at `0x18002fedd`
- `SHLWAPI!PathIsFileSpecW` at `0x18002fedd`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x18002fef2`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x18002fef2`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x18002fd1e`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x18002fd1e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002fe3b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002fe4c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002fe3b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002fe4c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180030009`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180030017`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180030009`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180030017`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002fea5`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002fea5`
- `api-ms-win-core-registry-l1-1-0!RegUnLoadKeyW` at `0x18003005a`
- `api-ms-win-core-registry-l1-1-0!RegUnLoadKeyW` at `0x18003005a`
- `api-ms-win-core-registry-l1-1-0!RegLoadKeyW` at `0x18002fd59`
- `api-ms-win-core-registry-l1-1-0!RegLoadKeyW` at `0x18002fd59`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002fe1f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002fe1f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180030022`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180030022`
- `KERNEL32!lstrcmpiW` at `0x18002ff2f`
- `KERNEL32!lstrcmpiW` at `0x18002ff2f`
- `ntdll!RtlAdjustPrivilege` at `0x18002fd41`
- `ntdll!RtlAdjustPrivilege` at `0x18002fd71`
- `ntdll!RtlAdjustPrivilege` at `0x180030046`
- `ntdll!RtlAdjustPrivilege` at `0x18003006e`
- `ntdll!RtlAdjustPrivilege` at `0x18002fd41`
- `ntdll!RtlAdjustPrivilege` at `0x18002fd71`
- `ntdll!RtlAdjustPrivilege` at `0x180030046`
- `ntdll!RtlAdjustPrivilege` at `0x18003006e`
- `ntdll!RtlNtStatusToDosError` at `0x18002fd7b`
- `ntdll!RtlNtStatusToDosError` at `0x180030078`
- `ntdll!RtlNtStatusToDosError` at `0x18002fd7b`
- `ntdll!RtlNtStatusToDosError` at `0x180030078`
- `SHCORE!__imp_SHCreateDirectoryExW` at `0x18002fcef`
- `SHCORE!__imp_SHCreateDirectoryExW` at `0x18002fcef`

## pseudocode

```c
// AFR coverage: BackupUserData copies selected user's shell folders during admin-gated delete-user backup; source from HKLM ProfileList/loaded ntuser.dat, not low-priv arbitrary file.
void __fastcall __noreturn BackupUserData(LPCWSTR lpSubKey, WCHAR *lpString1, const unsigned __int16 *a3)
{
  const WCHAR *v5; // rdi
  int v6; // eax
  int v7; // eax
  ULONG KeyW; // ebx
  WCHAR *v9; // rax
  __int64 v10; // rcx
  const WCHAR *v11; // r8
  __int64 v12; // rdx
  WCHAR *v13; // rcx
  BYTE *v14; // rsi
  HLOCAL v15; // rax
  void *v16; // rdi
  BYTE *v17; // r15
  unsigned __int16 *v18; // r13
  int v19; // esi
  unsigned int v20; // edi
  LSTATUS Value; // eax
  __int64 v22; // rax
  __int64 v23; // rax
  __int64 v24; // rax
  __int64 v25; // rax
  int v26; // eax
  const unsigned __int16 *v27; // rdx
  int v28; // eax
  unsigned __int8 OldValue[4]; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int cchPath; // [rsp+34h] [rbp-CCh]
  int cchPath_4; // [rsp+38h] [rbp-C8h] BYREF
  HKEY hKey; // [rsp+40h] [rbp-C0h] BYREF
  struct _SHFILEOPSTRUCTW lpValueName; // [rsp+48h] [rbp-B8h] BYREF
  PCWSTR pszMore; // [rsp+80h] [rbp-80h]
  __int128 hMem; // [rsp+88h] [rbp-78h]
  LPCWSTR v36; // [rsp+98h] [rbp-68h]
  WCHAR pszPathOut[264]; // [rsp+A0h] [rbp-60h] BYREF
  WCHAR SubKey[264]; // [rsp+2B0h] [rbp+1B0h] BYREF
  WCHAR achPath[264]; // [rsp+4C0h] [rbp+3C0h] BYREF

  v36 = lpSubKey;
  v5 = lpSubKey;
  memset_0(pszPathOut, 0, 0x208u);
  lpValueName.hwnd = (HWND)L"Desktop";
  *(_QWORD *)&lpValueName.wFunc = L"Personal";
  lpValueName.pFrom = L"My Pictures";
  lpValueName.pTo = L"My Music";
  *(_QWORD *)&lpValueName.fFlags = L"My Video";
  lpValueName.hNameMappings = L"Favorites";
  if ( v5 )
  {
    if ( *v5 )
    {
      if ( lpString1 )
      {
        if ( *lpString1 )
        {
          if ( a3 )
          {
            if ( *a3 )
            {
              v6 = SHCreateDirectoryExW(0, a3, 0);
              if ( v6 == 80 || v6 == 183 || !v6 )
              {
                if ( PathCchCombine(pszPathOut, 0x104u, lpString1, L"ntuser.dat") < 0 )
                {
                  KeyW = 122;
                }
                else
                {
                  OldValue[0] = 0;
                  v7 = RtlAdjustPrivilege(0x12u, 1u, 0, OldValue);
                  if ( v7 < 0 )
                  {
                    KeyW = RtlNtStatusToDosError(v7);
                  }
                  else
                  {
                    KeyW = RegLoadKeyW(HKEY_USERS, v5, pszPathOut);
                    RtlAdjustPrivilege(0x12u, OldValue[0], 0, OldValue);
                  }
                }
                if ( !KeyW )
                {
                  hKey = 0;
                  v9 = SubKey;
                  v10 = 2147483646;
                  v11 = v5;
                  v12 = 260;
                  do
                  {
                    if ( !v10 )
                      break;
                    if ( !*v11 )
                      break;
                    *v9++ = *v11++;
                    --v10;
                    --v12;
                  }
                  while ( v12 );
                  v13 = v9 - 1;
                  if ( v12 )
                    v13 = v9;
                  *v13 = 0;
                  if ( !v12
                    || (int)StringCchCatW(
                              SubKey,
                              0x104u,
                              L"\\Software\\Microsoft\\Windows\\CurrentVersion\\Explorer\\Shell Folders") < 0
                    || RegOpenKeyExW(HKEY_USERS, SubKey, 0, 1u, &hKey) )
                  {
                    goto LABEL_53;
                  }
                  v14 = (BYTE *)LocalAlloc(0x40u, 0xC32u);
                  *(_QWORD *)&hMem = v14;
                  v15 = LocalAlloc(0x40u, 0xC32u);
                  *((_QWORD *)&hMem + 1) = v15;
                  v16 = v15;
                  if ( v14 && v15 )
                  {
                    v17 = v14;
                    v18 = (unsigned __int16 *)v15;
                    v19 = 1560;
                    v20 = 0;
                    cchPath = 1560;
                    do
                    {
                      cchPath_4 = 2 * v19;
                      Value = RegQueryValueExW(
                                hKey,
                                *((LPCWSTR *)&lpValueName.hwnd + (int)v20),
                                0,
                                0,
                                v17,
                                (LPDWORD)&cchPath_4);
                      if ( Value )
                      {
                        if ( Value != 2 )
                          break;
                      }
                      else
                      {
                        PathRemoveBackslashW((LPWSTR)v17);
                        StringCchCopyW(v18, cchPath, a3);
                        pszMore = PathFindFileNameW((LPCWSTR)v17);
                        if ( PathIsFileSpecW(pszMore) )
                          PathCchAppend(v18, cchPath, pszMore);
                        if ( !*lpString1
                          || !PathRemoveBackslashW(lpString1)
                          || !PathCommonPrefixW(lpString1, (LPCWSTR)v17, achPath)
                          || lstrcmpiW(lpString1, achPath) )
                        {
                          EnsureAdminFileAccess((LPWSTR)v17);
                        }
                        v22 = -1;
                        do
                          ++v22;
                        while ( *(_WORD *)&v17[2 * v22] );
                        v23 = (unsigned int)(v22 + 1);
                        v19 -= v23;
                        v17 += 2 * v23;
                        v24 = -1;
                        do
                          ++v24;
                        while ( v18[v24] );
                        v25 = (unsigned int)(v24 + 1);
                        cchPath -= v25;
                        v18 += v25;
                      }
                      ++v20;
                    }
                    while ( v20 < 6 );
                    v16 = (void *)*((_QWORD *)&hMem + 1);
                    v14 = (BYTE *)hMem;
                    if ( *(_WORD *)hMem )
                    {
                      if ( **((_WORD **)&hMem + 1) )
                      {
                        *(_OWORD *)&lpValueName.hwnd = 0;
                        lpValueName.wFunc = 1;
                        memset(&lpValueName.fFlags, 0, 24);
                        lpValueName.fFlags = 3609;
                        *(_OWORD *)&lpValueName.pFrom = hMem;
                        v26 = SHFileOperationW(&lpValueName);
                        if ( v26 == 1223 || !v26 )
                          DeleteFilesInTree(a3, v27);
                      }
                    }
                  }
                  else if ( !v14 )
                  {
LABEL_50:
                    if ( v16 )
                      LocalFree(v16);
                    RegCloseKey(hKey);
                    v5 = v36;
LABEL_53:
                    OldValue[0] = 0;
                    v28 = RtlAdjustPrivilege(0x12u, 1u, 0, OldValue);
                    if ( v28 < 0 )
                    {
                      RtlNtStatusToDosError(v28);
                    }
                    else
                    {
                      RegUnLoadKeyW(HKEY_USERS, v5);
                      RtlAdjustPrivilege(0x12u, OldValue[0], 0, OldValue);
                    }
                    return;
                  }
                  LocalFree(v14);
                  goto LABEL_50;
                }
              }
            }
          }
        }
      }
    }
  }
}

```

## disassembly

```asm
0x18002fc14  mov     [rsp-8+arg_18], rbx; AFR coverage: BackupUserData copies selected user's shell folders during admin-gated delete-user backup; source from HKLM ProfileList/loaded ntuser.dat, not low-priv arbitrary file.
0x18002fc19  push    rbp
0x18002fc1a  push    rsi
0x18002fc1b  push    rdi
0x18002fc1c  push    r12
0x18002fc1e  push    r13
0x18002fc20  push    r14
0x18002fc22  push    r15
0x18002fc24  lea     rbp, [rsp-5E0h]
0x18002fc2c  sub     rsp, 6E0h
0x18002fc33  mov     rax, cs:__security_cookie
0x18002fc3a  xor     rax, rsp
0x18002fc3d  mov     [rbp+610h+var_40], rax
0x18002fc44  mov     r12, r8
0x18002fc47  mov     [rbp+610h+var_678], rcx
0x18002fc4b  mov     r14, rdx
0x18002fc4e  mov     rdi, rcx
0x18002fc51  xor     edx, edx; Val
0x18002fc53  lea     rcx, [rbp+610h+pszPathOut]; void *
0x18002fc57  mov     r8d, 208h; Size
0x18002fc5d  call    memset_0
0x18002fc62  lea     rax, aDesktop
0x18002fc69  xor     r15d, r15d
0x18002fc6c  mov     [rsp+710h+lpValueName], rax
0x18002fc71  lea     rax, aPersonal
0x18002fc78  mov     [rsp+710h+lpValueName+8], rax
0x18002fc7d  lea     rax, aMyPictures
0x18002fc84  mov     qword ptr [rsp+710h+var_6B8], rax
0x18002fc89  lea     rax, aMyMusic
0x18002fc90  mov     qword ptr [rsp+710h+var_6B8+8], rax
0x18002fc95  lea     rax, aMyVideo
0x18002fc9c  mov     qword ptr [rsp+710h+var_6A8], rax
0x18002fca1  lea     rax, aFavorites
0x18002fca8  mov     qword ptr [rsp+710h+var_6A8+8], rax
0x18002fcad  test    rdi, rdi
0x18002fcb0  jz      loc_180030095
0x18002fcb6  cmp     [rdi], r15w
0x18002fcba  jz      loc_180030095
0x18002fcc0  test    r14, r14
0x18002fcc3  jz      loc_180030095
0x18002fcc9  cmp     [r14], r15w
0x18002fccd  jz      loc_180030095
0x18002fcd3  test    r12, r12
0x18002fcd6  jz      loc_180030095
0x18002fcdc  cmp     [r12], r15w
0x18002fce1  jz      loc_180030095
0x18002fce7  xor     r8d, r8d; psa
0x18002fcea  mov     rdx, r12; pszPath
0x18002fced  xor     ecx, ecx; hwnd
0x18002fcef  call    cs:__imp_SHCreateDirectoryExW
0x18002fcf5  cmp     eax, 50h ; 'P'
0x18002fcf8  jz      short loc_18002FD09
0x18002fcfa  cmp     eax, 0B7h
0x18002fcff  jz      short loc_18002FD09
0x18002fd01  test    eax, eax
0x18002fd03  jnz     loc_18003009A
0x18002fd09  mov     esi, 104h
0x18002fd0e  lea     r9, pszMore
0x18002fd15  mov     edx, esi; cchPathOut
0x18002fd17  lea     rcx, [rbp+610h+pszPathOut]; pszPathOut
0x18002fd1b  mov     r8, r14; pszPathIn
0x18002fd1e  call    cs:__imp_PathCchCombine
0x18002fd24  mov     r13d, 7Ah ; 'z'
0x18002fd2a  test    eax, eax
0x18002fd2c  js      short loc_18002FD85
0x18002fd2e  lea     r9, [rsp+710h+OldValue]; OldValue
0x18002fd33  mov     [rsp+710h+OldValue], r15b
0x18002fd38  xor     r8d, r8d; ForThread
0x18002fd3b  lea     ecx, [r13-68h]; Privilege
0x18002fd3f  mov     dl, 1; NewValue
0x18002fd41  call    cs:__imp_RtlAdjustPrivilege
0x18002fd47  test    eax, eax
0x18002fd49  js      short loc_18002FD79
0x18002fd4b  lea     r8, [rbp+610h+pszPathOut]; lpFile
0x18002fd4f  mov     rdx, rdi; lpSubKey
0x18002fd52  mov     rcx, 0FFFFFFFF80000003h; hKey
0x18002fd59  call    cs:__imp_RegLoadKeyW
0x18002fd5f  mov     dl, [rsp+710h+OldValue]; NewValue
0x18002fd63  lea     r9, [rsp+710h+OldValue]; OldValue
0x18002fd68  xor     r8d, r8d; ForThread
0x18002fd6b  lea     ecx, [r13-68h]; Privilege
0x18002fd6f  mov     ebx, eax
0x18002fd71  call    cs:__imp_RtlAdjustPrivilege
0x18002fd77  jmp     short loc_18002FD88
0x18002fd79  mov     ecx, eax; Status
0x18002fd7b  call    cs:__imp_RtlNtStatusToDosError
0x18002fd81  mov     ebx, eax
0x18002fd83  jmp     short loc_18002FD88
0x18002fd85  mov     ebx, r13d
0x18002fd88  test    ebx, ebx
0x18002fd8a  jnz     loc_18003007E
0x18002fd90  mov     [rsp+710h+hKey], r15
0x18002fd95  lea     rax, [rbp+610h+SubKey]
0x18002fd9c  mov     ecx, 7FFFFFFEh
0x18002fda1  mov     r8, rdi
0x18002fda4  mov     rdx, rsi
0x18002fda7  test    rcx, rcx
0x18002fdaa  jz      short loc_18002FDCB
0x18002fdac  movzx   r9d, word ptr [r8]
0x18002fdb0  test    r9w, r9w
0x18002fdb4  jz      short loc_18002FDCB
0x18002fdb6  mov     [rax], r9w
0x18002fdba  add     r8, 2
0x18002fdbe  add     rax, 2
0x18002fdc2  dec     rcx
0x18002fdc5  sub     rdx, 1
0x18002fdc9  jnz     short loc_18002FDA7
0x18002fdcb  test    rdx, rdx
0x18002fdce  lea     rcx, [rax-2]
0x18002fdd2  cmovnz  rcx, rax
0x18002fdd6  mov     [rcx], r15w
0x18002fdda  jz      loc_18003002E
0x18002fde0  lea     r8, aSoftwareMicros_7
0x18002fde7  mov     rdx, rsi; unsigned __int64
0x18002fdea  lea     rcx, [rbp+610h+SubKey]; unsigned __int16 *
0x18002fdf1  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z
0x18002fdf6  test    eax, eax
0x18002fdf8  js      loc_18003002E
0x18002fdfe  lea     rax, [rsp+710h+hKey]
0x18002fe03  mov     r9d, 1; samDesired
0x18002fe09  xor     r8d, r8d; ulOptions
0x18002fe0c  mov     [rsp+710h+phkResult], rax; phkResult
0x18002fe11  lea     rdx, [rbp+610h+SubKey]; lpSubKey
0x18002fe18  mov     rcx, 0FFFFFFFF80000003h; hKey
0x18002fe1f  call    cs:__imp_RegOpenKeyExW
0x18002fe25  mov     ebx, eax
0x18002fe27  test    eax, eax
0x18002fe29  jnz     loc_180030031
0x18002fe2f  lea     ebx, [rax+40h]
0x18002fe32  mov     edi, 0C32h
0x18002fe37  mov     edx, edi; uBytes
0x18002fe39  mov     ecx, ebx; uFlags
0x18002fe3b  call    cs:__imp_LocalAlloc
0x18002fe41  mov     edx, edi; uBytes
0x18002fe43  mov     ecx, ebx; uFlags
0x18002fe45  mov     rsi, rax
0x18002fe48  mov     qword ptr [rbp+610h+hMem], rax
0x18002fe4c  call    cs:__imp_LocalAlloc
0x18002fe52  mov     qword ptr [rbp+610h+hMem+8], rax
0x18002fe56  mov     rdi, rax
0x18002fe59  test    rsi, rsi
0x18002fe5c  jz      loc_18002FFFC
0x18002fe62  test    rax, rax
0x18002fe65  jz      loc_18002FFFC
0x18002fe6b  mov     r15, rsi
0x18002fe6e  mov     r13, rax
0x18002fe71  mov     esi, 618h
0x18002fe76  xor     edi, edi
0x18002fe78  mov     dword ptr [rsp+710h+cchPath], esi
0x18002fe7c  mov     rcx, [rsp+710h+hKey]; hKey
0x18002fe81  lea     eax, [rsi+rsi]
0x18002fe84  mov     dword ptr [rsp+710h+cchPath+4], eax
0x18002fe88  xor     r9d, r9d; lpType
0x18002fe8b  lea     rax, [rsp+710h+cchPath+4]
0x18002fe90  movsxd  rdx, edi
0x18002fe93  mov     [rsp+710h+lpcbData], rax; lpcbData
0x18002fe98  xor     r8d, r8d; lpReserved
0x18002fe9b  mov     [rsp+710h+phkResult], r15; lpData
0x18002fea0  mov     rdx, [rsp+rdx*8+710h+lpValueName]; lpValueName
0x18002fea5  call    cs:__imp_RegQueryValueExW
0x18002feab  mov     ebx, eax
0x18002fead  test    eax, eax
0x18002feaf  jnz     loc_18002FF79
0x18002feb5  mov     rcx, r15; pszPath
0x18002feb8  call    cs:__imp_PathRemoveBackslashW
0x18002febe  mov     edx, dword ptr [rsp+710h+cchPath]; unsigned __int64
0x18002fec2  mov     r8, r12; unsigned __int16 *
0x18002fec5  mov     rcx, r13; unsigned __int16 *
0x18002fec8  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z
0x18002fecd  mov     rcx, r15; pszPath
0x18002fed0  call    cs:__imp_PathFindFileNameW
0x18002fed6  mov     rcx, rax; pszPath
0x18002fed9  mov     [rbp+610h+pszMore], rax
0x18002fedd  call    cs:__imp_PathIsFileSpecW
0x18002fee3  test    eax, eax
0x18002fee5  jz      short loc_18002FEF8
0x18002fee7  mov     r8, [rbp+610h+pszMore]; pszMore
0x18002feeb  mov     rcx, r13; pszPath
0x18002feee  mov     edx, dword ptr [rsp+710h+cchPath]; cchPath
0x18002fef2  call    cs:__imp_PathCchAppend
0x18002fef8  xor     eax, eax
0x18002fefa  cmp     [r14], ax
0x18002fefe  jz      short loc_18002FF3B
0x18002ff00  mov     rcx, r14; pszPath
0x18002ff03  call    cs:__imp_PathRemoveBackslashW
0x18002ff09  test    rax, rax
0x18002ff0c  jz      short loc_18002FF3B
0x18002ff0e  lea     r8, [rbp+610h+achPath]; achPath
0x18002ff15  mov     rdx, r15; pszFile2
0x18002ff18  mov     rcx, r14; pszFile1
0x18002ff1b  call    cs:__imp_PathCommonPrefixW
0x18002ff21  test    eax, eax
0x18002ff23  jz      short loc_18002FF3B
0x18002ff25  lea     rdx, [rbp+610h+achPath]; lpString2
0x18002ff2c  mov     rcx, r14; lpString1
0x18002ff2f  call    cs:__imp_lstrcmpiW
0x18002ff35  xor     ecx, ecx
0x18002ff37  test    eax, eax
0x18002ff39  jz      short loc_18002FF45
0x18002ff3b  mov     rcx, r15; pObjectName
0x18002ff3e  call    ?EnsureAdminFileAccess@@YAKPEAG@Z
0x18002ff43  xor     ecx, ecx
0x18002ff45  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18002ff49  mov     rax, rdx
0x18002ff4c  inc     rax
0x18002ff4f  cmp     [r15+rax*2], cx
0x18002ff54  jnz     short loc_18002FF4C
0x18002ff56  inc     eax
0x18002ff58  sub     esi, eax
0x18002ff5a  lea     r15, [r15+rax*2]
0x18002ff5e  mov     rax, rdx
0x18002ff61  inc     rax
0x18002ff64  cmp     [r13+rax*2+0], cx
0x18002ff6a  jnz     short loc_18002FF61
0x18002ff6c  inc     eax
0x18002ff6e  sub     dword ptr [rsp+710h+cchPath], eax
0x18002ff72  lea     r13, [r13+rax*2+0]
0x18002ff77  jmp     short loc_18002FF7E
0x18002ff79  cmp     eax, 2
0x18002ff7c  jnz     short loc_18002FF89
0x18002ff7e  inc     edi
0x18002ff80  cmp     edi, 6
0x18002ff83  jb      loc_18002FE7C
0x18002ff89  mov     rsi, qword ptr [rbp+610h+hMem]
0x18002ff8d  xor     r15d, r15d
0x18002ff90  mov     rdi, qword ptr [rbp+610h+hMem+8]
0x18002ff94  cmp     [rsi], r15w
0x18002ff98  jz      short loc_180030006
0x18002ff9a  cmp     [rdi], r15w
0x18002ff9e  jz      short loc_180030006
0x18002ffa0  xorps   xmm0, xmm0
0x18002ffa3  lea     rcx, [rsp+710h+lpValueName]; lpFileOp
0x18002ffa8  xor     eax, eax
0x18002ffaa  movups  [rsp+710h+var_6B8], xmm0
0x18002ffaf  mov     [rsp+710h+var_698], rax
0x18002ffb4  mov     eax, 0E19h
0x18002ffb9  movups  xmmword ptr [rsp+710h+lpValueName], xmm0
0x18002ffbe  mov     dword ptr [rsp+710h+lpValueName+8], 1
0x18002ffc6  movups  [rsp+710h+var_6A8], xmm0
0x18002ffcb  mov     word ptr [rsp+710h+var_6A8], ax
0x18002ffd0  mov     qword ptr [rsp+710h+var_6B8], rsi
0x18002ffd5  mov     qword ptr [rsp+710h+var_6B8+8], rdi
0x18002ffda  call    cs:__imp_SHFileOperationW
0x18002ffe0  mov     ebx, eax
0x18002ffe2  cmp     eax, 4C7h
0x18002ffe7  jnz     short loc_18002FFEE
0x18002ffe9  mov     ebx, r15d
0x18002ffec  jmp     short loc_18002FFF2
0x18002ffee  test    eax, eax
0x18002fff0  jnz     short loc_180030006
0x18002fff2  mov     rcx, r12; unsigned __int16 *
0x18002fff5  call    ?DeleteFilesInTree@@YAXPEBG0@Z
0x18002fffa  jmp     short loc_180030006
0x18002fffc  mov     ebx, 0Eh
0x180030001  test    rsi, rsi
0x180030004  jz      short loc_18003000F
0x180030006  mov     rcx, rsi; hMem
0x180030009  call    cs:__imp_LocalFree
0x18003000f  test    rdi, rdi
0x180030012  jz      short loc_18003001D
0x180030014  mov     rcx, rdi; hMem
0x180030017  call    cs:__imp_LocalFree
0x18003001d  mov     rcx, [rsp+710h+hKey]; hKey
0x180030022  call    cs:__imp_RegCloseKey
0x180030028  mov     rdi, [rbp+610h+var_678]
0x18003002c  jmp     short loc_180030031
0x18003002e  mov     ebx, r13d
0x180030031  xor     r8d, r8d; ForThread
0x180030034  mov     [rsp+710h+OldValue], r15b
0x180030039  lea     r9, [rsp+710h+OldValue]; OldValue
0x18003003e  mov     dl, 1; NewValue
0x180030040  lea     esi, [r8+12h]
0x180030044  mov     ecx, esi; Privilege
0x180030046  call    cs:__imp_RtlAdjustPrivilege
0x18003004c  test    eax, eax
0x18003004e  js      short loc_180030076
0x180030050  mov     rdx, rdi; lpSubKey
0x180030053  mov     rcx, 0FFFFFFFF80000003h; hKey
0x18003005a  call    cs:__imp_RegUnLoadKeyW
0x180030060  mov     dl, [rsp+710h+OldValue]; NewValue
0x180030064  lea     r9, [rsp+710h+OldValue]; OldValue
0x180030069  xor     r8d, r8d; ForThread
0x18003006c  mov     ecx, esi; Privilege
0x18003006e  call    cs:__imp_RtlAdjustPrivilege
0x180030074  jmp     short loc_18003007E
0x180030076  mov     ecx, eax; Status
0x180030078  call    cs:__imp_RtlNtStatusToDosError
0x18003007e  cmp     ebx, 2
0x180030081  mov     eax, r15d
0x180030084  cmovnz  eax, ebx
0x180030087  test    eax, eax
0x180030089  jle     short loc_18003009A
0x18003008b  movzx   eax, ax
0x18003008e  or      eax, 80070000h
0x180030093  jmp     short loc_18003009A
0x180030095  mov     eax, 80070057h
0x18003009a  mov     rcx, [rbp+610h+var_40]
0x1800300a1  xor     rcx, rsp; StackCookie
0x1800300a4  call    __security_check_cookie
0x1800300a9  mov     rbx, [rsp+710h+arg_18]
  ... truncated ...
```
