# CCDBurn::_EnsureStagingFolder(int,ushort const *,ushort *,ulong)

- ea: `0x18026c808`
- end: `0x18026cc22`
- name: `?_EnsureStagingFolder@CCDBurn@@CAHHPEBGPEAGK@Z`
- size: `1050`
- prototype: `__int64 __fastcall(int, const unsigned __int16 *, unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, reparse_path, registry_config, broker_com_uri`

## callers

- `0x180168420`

## callees

- `0x18000d220`
- `0x18000d240`
- `0x18001aae0`
- `0x18003a3e0`
- `0x180249490`
- `0x18024a53c`
- `0x18026b598`
- `0x18026c808`
- `0x18026e5e8`
- `0x180270334`
- `0x1805b2010`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18026cbdd`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18026cbdd`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18026cb5e`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18026cb5e`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18026ca11`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18026ca3c`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18026ca11`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18026ca3c`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x18026c873`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x18026ca65`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x18026c873`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x18026ca65`
- `api-ms-win-core-path-l1-1-0!PathCchRemoveFileSpec` at `0x18026c8d2`
- `api-ms-win-core-path-l1-1-0!PathCchRemoveFileSpec` at `0x18026c8d2`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x18026c84d`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x18026c84d`
- `api-ms-win-shcore-registry-l1-1-0!SHGetValueW` at `0x18026c948`
- `api-ms-win-shcore-registry-l1-1-0!SHGetValueW` at `0x18026cb25`
- `api-ms-win-shcore-registry-l1-1-0!SHGetValueW` at `0x18026c948`
- `api-ms-win-shcore-registry-l1-1-0!SHGetValueW` at `0x18026cb25`
- `api-ms-win-shcore-registry-l1-1-0!SHSetValueW` at `0x18026cbbf`
- `api-ms-win-shcore-registry-l1-1-0!SHSetValueW` at `0x18026cbbf`
- `SHCORE!__imp_SHCreateDirectoryExW` at `0x18026cb86`
- `SHCORE!__imp_SHCreateDirectoryExW` at `0x18026cb86`
- `api-ms-win-storage-exports-internal-l1-1-0!SHGetFolderPathEx` at `0x18026c8a6`
- `api-ms-win-storage-exports-internal-l1-1-0!SHGetFolderPathEx` at `0x18026c8a6`
- `api-ms-win-storage-exports-external-l1-1-0!STORAGE_CEnumFiles_CreateInstance` at `0x18026c994`
- `api-ms-win-storage-exports-external-l1-1-0!STORAGE_CEnumFiles_CreateInstance` at `0x18026c994`

## string_xrefs

- `0x18026c933`: `StagingPath`
- `0x18026cb0d`: `NextStagingPathIndex`
- `0x18026cbae`: `NextStagingPathIndex`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CCDBurn::_EnsureStagingFolder(int a1, const unsigned __int16 *a2, unsigned __int16 *a3)
{
  unsigned int IsStagingPathOK; // ebx
  const WCHAR *FileNameW; // rax
  unsigned int v8; // r8d
  unsigned int v9; // r12d
  int v10; // esi
  int v11; // r15d
  int v12; // r14d
  void *pvData; // [rsp+20h] [rbp-E0h]
  DWORD pcbData; // [rsp+30h] [rbp-D0h] BYREF
  DWORD v16[2]; // [rsp+38h] [rbp-C8h] BYREF
  _BYTE v17[44]; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR String1[290]; // [rsp+6Ch] [rbp-94h] BYREF
  WCHAR pszPath[264]; // [rsp+2B0h] [rbp+1B0h] BYREF
  WCHAR String2[264]; // [rsp+4C0h] [rbp+3C0h] BYREF
  WCHAR pszPathOut[264]; // [rsp+6D0h] [rbp+5D0h] BYREF

  *a3 = 0;
  IsStagingPathOK = 0;
  FileNameW = PathFindFileNameW(a2);
  if ( PathCchCombine(
         pszPathOut,
         0x104u,
         L"Software\\Microsoft\\Windows\\CurrentVersion\\Explorer\\CD Burning\\StagingInfo",
         FileNameW) < 0 )
    return IsStagingPathOK;
  pszPath[0] = 0;
  if ( (int)SHGetFolderPathEx(&FOLDERID_CDBurning, 0x8000, 0, a3, 260) >= 0 )
  {
    StringCchCopyW(pszPath, 0x104u, a3);
    PathCchRemoveFileSpec(pszPath, 0x104u);
    IsStagingPathOK = CCDBurn::_IsStagingPathOK(a3, a2);
  }
  v9 = IsStagingPathOK;
  if ( IsStagingPathOK )
    goto LABEL_32;
  if ( CCDBurn::_GetDriveLetterBasedStagingPath(a1, a3, v8) )
  {
    IsStagingPathOK = CCDBurn::_IsStagingPathOK(a3, a2);
    if ( IsStagingPathOK )
      goto LABEL_32;
  }
  pcbData = 520;
  if ( !SHGetValueW(HKEY_CURRENT_USER, pszPathOut, L"StagingPath", 0, a3, &pcbData) )
  {
    IsStagingPathOK = CCDBurn::_IsStagingPathOK(a3, a2);
    if ( IsStagingPathOK )
      goto LABEL_32;
  }
  if ( !pszPath[0] )
    return IsStagingPathOK;
  ATL::CComPtr<IClassFactory>::CComPtr<IClassFactory>(v16);
  v10 = 1;
  if ( (int)STORAGE_CEnumFiles_CreateInstance(0, &GUID_4e31e71d_945b_471d_88a9_061b207facaa, v16) >= 0 )
  {
    memset_0(v17, 0, 0x268u);
    v11 = (*(__int64 (__fastcall **)(_QWORD, WCHAR *, _BYTE *))(**(_QWORD **)v16 + 32LL))(*(_QWORD *)v16, pszPath, v17);
    if ( !v11 )
    {
      while ( 1 )
      {
        if ( IsStagingPathOK )
          goto LABEL_23;
        if ( (v17[0] & 0x10) == 0
          || CompareStringOrdinal(String1, -1, L".", -1, 1) == 2
          || CompareStringOrdinal(String1, -1, L"..", -1, 1) == 2
          || PathCchCombine(String2, 0x104u, pszPath, String1) < 0
          || !(unsigned int)CCDBurn::_IsStagingPathOK(String2, a2) )
        {
          goto LABEL_21;
        }
        if ( (int)StringCchCopyW(a3, 0x104u, String2) < 0 )
          break;
        IsStagingPathOK = 1;
LABEL_22:
        if ( v11 )
          goto LABEL_23;
      }
      IsStagingPathOK = 0;
LABEL_21:
      v11 = (*(__int64 (__fastcall **)(_QWORD, _BYTE *))(**(_QWORD **)v16 + 56LL))(*(_QWORD *)v16, v17);
      goto LABEL_22;
    }
  }
LABEL_23:
  ATL::CComPtr<IUICommandWithBackgroundColor>::~CComPtr<IUICommandWithBackgroundColor>(v16);
  if ( IsStagingPathOK )
  {
LABEL_32:
    v10 = 0;
    if ( !v9 )
      return IsStagingPathOK;
    goto LABEL_33;
  }
  if ( pszPath[0] )
  {
    pcbData = 1;
    v16[0] = 4;
    SHGetValueW(
      HKEY_CURRENT_USER,
      L"Software\\Microsoft\\Windows\\CurrentVersion\\Explorer\\CD Burning\\StagingInfo",
      L"NextStagingPathIndex",
      0,
      &pcbData,
      v16);
    v12 = 0;
    while ( 1 )
    {
      do
        LODWORD(pvData) = pcbData;
      while ( (int)StringCchPrintfW(a3, 0x104u, L"%s\\Burn%d", pszPath, pvData) < 0 );
      if ( GetFileAttributesW(a3) == -1 )
        break;
      ++pcbData;
      if ( (unsigned int)++v12 >= 0x32 )
        return IsStagingPathOK;
    }
    if ( !SHCreateDirectoryExW(0, a3, 0) )
    {
      IsStagingPathOK = 1;
      ++pcbData;
      SHSetValueW(
        HKEY_CURRENT_USER,
        L"Software\\Microsoft\\Windows\\CurrentVersion\\Explorer\\CD Burning\\StagingInfo",
        L"NextStagingPathIndex",
        4u,
        &pcbData,
        4u);
LABEL_33:
      SetFileAttributesW(a3, 3u);
      if ( v10 )
        CCDBurn::_CreateLocalizationDesktopIni(a3);
    }
  }
  return IsStagingPathOK;
}

```

## disassembly

```asm
0x18026c808  mov     [rsp-8+arg_0], rbx
0x18026c80d  push    rbp
0x18026c80e  push    rsi
0x18026c80f  push    rdi
0x18026c810  push    r12
0x18026c812  push    r13
0x18026c814  push    r14
0x18026c816  push    r15
0x18026c818  lea     rbp, [rsp-7F0h]
0x18026c820  sub     rsp, 8F0h
0x18026c827  mov     rax, cs:__security_cookie
0x18026c82e  xor     rax, rsp
0x18026c831  mov     [rbp+820h+var_40], rax
0x18026c838  mov     rdi, r8
0x18026c83b  mov     r14, rdx
0x18026c83e  mov     esi, ecx
0x18026c840  xor     r13d, r13d
0x18026c843  mov     [r8], r13w
0x18026c847  mov     ebx, r13d
0x18026c84a  mov     rcx, rdx; pszPath
0x18026c84d  call    cs:__imp_PathFindFileNameW
0x18026c854  nop     dword ptr [rax+rax+00h]
0x18026c859  mov     r9, rax; pszMore
0x18026c85c  lea     r8, aSoftwareMicros_179; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18026c863  mov     r15d, 104h
0x18026c869  mov     edx, r15d; cchPathOut
0x18026c86c  lea     rcx, [rbp+820h+pszPathOut]; pszPathOut
0x18026c873  call    cs:__imp_PathCchCombine
0x18026c87a  nop     dword ptr [rax+rax+00h]
0x18026c87f  test    eax, eax
0x18026c881  js      loc_18026CBF5
0x18026c887  mov     [rbp+820h+pszPath], r13w
0x18026c88f  mov     dword ptr [rsp+920h+pvData], r15d
0x18026c894  mov     r9, rdi
0x18026c897  xor     r8d, r8d
0x18026c89a  mov     edx, 8000h
0x18026c89f  lea     rcx, FOLDERID_CDBurning
0x18026c8a6  call    cs:__imp_SHGetFolderPathEx
0x18026c8ad  nop     dword ptr [rax+rax+00h]
0x18026c8b2  test    eax, eax
0x18026c8b4  js      short loc_18026C8EB
0x18026c8b6  mov     r8, rdi; unsigned __int16 *
0x18026c8b9  mov     edx, r15d; unsigned __int64
0x18026c8bc  lea     rcx, [rbp+820h+pszPath]; unsigned __int16 *
0x18026c8c3  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18026c8c8  mov     edx, r15d; cchPath
0x18026c8cb  lea     rcx, [rbp+820h+pszPath]; pszPath
0x18026c8d2  call    cs:__imp_PathCchRemoveFileSpec
0x18026c8d9  nop     dword ptr [rax+rax+00h]
0x18026c8de  mov     rdx, r14; unsigned __int16 *
0x18026c8e1  mov     rcx, rdi; lpString2
0x18026c8e4  call    ?_IsStagingPathOK@CCDBurn@@CAHPEBG0@Z; CCDBurn::_IsStagingPathOK(ushort const *,ushort const *)
0x18026c8e9  mov     ebx, eax
0x18026c8eb  mov     r12d, ebx
0x18026c8ee  test    ebx, ebx
0x18026c8f0  jnz     loc_18026CBCD
0x18026c8f6  mov     rdx, rdi; unsigned __int16 *
0x18026c8f9  mov     ecx, esi; int
0x18026c8fb  call    ?_GetDriveLetterBasedStagingPath@CCDBurn@@CAHHPEAGK@Z; CCDBurn::_GetDriveLetterBasedStagingPath(int,ushort *,ulong)
0x18026c900  test    eax, eax
0x18026c902  jz      short loc_18026C919
0x18026c904  mov     rdx, r14; unsigned __int16 *
0x18026c907  mov     rcx, rdi; lpString2
0x18026c90a  call    ?_IsStagingPathOK@CCDBurn@@CAHPEBG0@Z; CCDBurn::_IsStagingPathOK(ushort const *,ushort const *)
0x18026c90f  mov     ebx, eax
0x18026c911  test    eax, eax
0x18026c913  jnz     loc_18026CBCD
0x18026c919  mov     [rsp+920h+var_8F0], 208h
0x18026c921  lea     rax, [rsp+920h+var_8F0]
0x18026c926  mov     [rsp+920h+pcbData], rax; pcbData
0x18026c92b  mov     [rsp+920h+pvData], rdi; pvData
0x18026c930  xor     r9d, r9d; pdwType
0x18026c933  lea     r8, aStagingpath; "StagingPath"
0x18026c93a  lea     rdx, [rbp+820h+pszPathOut]; pszSubKey
0x18026c941  mov     rcx, 0FFFFFFFF80000001h; hkey
0x18026c948  call    cs:__imp_SHGetValueW
0x18026c94f  nop     dword ptr [rax+rax+00h]
0x18026c954  test    eax, eax
0x18026c956  jnz     short loc_18026C96D
0x18026c958  mov     rdx, r14; unsigned __int16 *
0x18026c95b  mov     rcx, rdi; lpString2
0x18026c95e  call    ?_IsStagingPathOK@CCDBurn@@CAHPEBG0@Z; CCDBurn::_IsStagingPathOK(ushort const *,ushort const *)
0x18026c963  mov     ebx, eax
0x18026c965  test    eax, eax
0x18026c967  jnz     loc_18026CBCD
0x18026c96d  cmp     [rbp+820h+pszPath], r13w
0x18026c975  jz      loc_18026CBF5
0x18026c97b  lea     rcx, [rsp+920h+var_8E8]; void *
0x18026c980  call    ??0?$CComPtr@UIClassFactory@@@ATL@@QEAA@XZ; ATL::CComPtr<IClassFactory>::CComPtr<IClassFactory>(void)
0x18026c985  nop
0x18026c986  lea     r8, [rsp+920h+var_8E8]
0x18026c98b  lea     rdx, _GUID_4e31e71d_945b_471d_88a9_061b207facaa
0x18026c992  xor     ecx, ecx
0x18026c994  call    cs:__imp_STORAGE_CEnumFiles_CreateInstance
0x18026c99b  nop     dword ptr [rax+rax+00h]
0x18026c9a0  mov     esi, 1
0x18026c9a5  test    eax, eax
0x18026c9a7  js      loc_18026CAC9
0x18026c9ad  xor     edx, edx; Val
0x18026c9af  mov     r8d, 268h; Size
0x18026c9b5  lea     rcx, [rsp+920h+var_8E0]; void *
0x18026c9ba  call    memset_0
0x18026c9bf  mov     rcx, qword ptr [rsp+920h+var_8E8]
0x18026c9c4  mov     rax, [rcx]
0x18026c9c7  lea     r8, [rsp+920h+var_8E0]
0x18026c9cc  lea     rdx, [rbp+820h+pszPath]
0x18026c9d3  mov     rax, [rax+20h]
0x18026c9d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18026c9dc  mov     r15d, eax
0x18026c9df  test    eax, eax
0x18026c9e1  jnz     loc_18026CAC9
0x18026c9e7  test    ebx, ebx
0x18026c9e9  jnz     loc_18026CAC9
0x18026c9ef  test    [rsp+920h+var_8E0], 10h
0x18026c9f4  jz      loc_18026CAA7
0x18026c9fa  mov     dword ptr [rsp+920h+pvData], esi; bIgnoreCase
0x18026c9fe  or      r9d, 0FFFFFFFFh; cchCount2
0x18026ca02  lea     r8, asc_180630F30; "."
0x18026ca09  or      edx, r9d; cchCount1
0x18026ca0c  lea     rcx, [rsp+920h+String1]; lpString1
0x18026ca11  call    cs:__imp_CompareStringOrdinal
0x18026ca18  nop     dword ptr [rax+rax+00h]
0x18026ca1d  cmp     eax, 2
0x18026ca20  jz      loc_18026CAA7
0x18026ca26  mov     dword ptr [rsp+920h+pvData], esi; bIgnoreCase
0x18026ca2a  or      edx, 0FFFFFFFFh; cchCount1
0x18026ca2d  mov     r9d, edx; cchCount2
0x18026ca30  lea     r8, asc_180631550; ".."
0x18026ca37  lea     rcx, [rsp+920h+String1]; lpString1
0x18026ca3c  call    cs:__imp_CompareStringOrdinal
0x18026ca43  nop     dword ptr [rax+rax+00h]
0x18026ca48  cmp     eax, 2
0x18026ca4b  jz      short loc_18026CAA7
0x18026ca4d  lea     r9, [rsp+920h+String1]; pszMore
0x18026ca52  lea     r8, [rbp+820h+pszPath]; pszPathIn
0x18026ca59  mov     edx, 104h; cchPathOut
0x18026ca5e  lea     rcx, [rbp+820h+String2]; pszPathOut
0x18026ca65  call    cs:__imp_PathCchCombine
0x18026ca6c  nop     dword ptr [rax+rax+00h]
0x18026ca71  test    eax, eax
0x18026ca73  js      short loc_18026CAA7
0x18026ca75  mov     rdx, r14; unsigned __int16 *
0x18026ca78  lea     rcx, [rbp+820h+String2]; lpString2
0x18026ca7f  call    ?_IsStagingPathOK@CCDBurn@@CAHPEBG0@Z; CCDBurn::_IsStagingPathOK(ushort const *,ushort const *)
0x18026ca84  test    eax, eax
0x18026ca86  jz      short loc_18026CAA7
0x18026ca88  lea     r8, [rbp+820h+String2]; unsigned __int16 *
0x18026ca8f  mov     edx, 104h; unsigned __int64
0x18026ca94  mov     rcx, rdi; unsigned __int16 *
0x18026ca97  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18026ca9c  test    eax, eax
0x18026ca9e  js      short loc_18026CAA4
0x18026caa0  mov     ebx, esi
0x18026caa2  jmp     short loc_18026CAC0
0x18026caa4  mov     ebx, r13d
0x18026caa7  mov     rcx, qword ptr [rsp+920h+var_8E8]
0x18026caac  mov     rax, [rcx]
0x18026caaf  lea     rdx, [rsp+920h+var_8E0]
0x18026cab4  mov     rax, [rax+38h]
0x18026cab8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18026cabd  mov     r15d, eax
0x18026cac0  test    r15d, r15d
0x18026cac3  jz      loc_18026C9E7
0x18026cac9  lea     rcx, [rsp+920h+var_8E8]; void *
0x18026cace  call    ??1?$CComPtr@UIUICommandWithBackgroundColor@@@ATL@@QEAA@XZ; ATL::CComPtr<IUICommandWithBackgroundColor>::~CComPtr<IUICommandWithBackgroundColor>(void)
0x18026cad3  test    ebx, ebx
0x18026cad5  jnz     loc_18026CBCD
0x18026cadb  cmp     [rbp+820h+pszPath], r13w
0x18026cae3  jz      loc_18026CBF5
0x18026cae9  mov     [rsp+920h+var_8F0], esi
0x18026caed  lea     r15d, [rbx+4]
0x18026caf1  mov     [rsp+920h+var_8E8], r15d
0x18026caf6  lea     rax, [rsp+920h+var_8E8]
0x18026cafb  mov     [rsp+920h+pcbData], rax; pcbData
0x18026cb00  lea     rax, [rsp+920h+var_8F0]
0x18026cb05  mov     [rsp+920h+pvData], rax; pvData
0x18026cb0a  xor     r9d, r9d; pdwType
0x18026cb0d  lea     r8, aNextstagingpat; "NextStagingPathIndex"
0x18026cb14  lea     rdx, aSoftwareMicros_179; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18026cb1b  mov     r12, 0FFFFFFFF80000001h
0x18026cb22  mov     rcx, r12; hkey
0x18026cb25  call    cs:__imp_SHGetValueW
0x18026cb2c  nop     dword ptr [rax+rax+00h]
0x18026cb31  mov     r14d, r13d
0x18026cb34  mov     eax, [rsp+920h+var_8F0]
0x18026cb38  mov     dword ptr [rsp+920h+pvData], eax
0x18026cb3c  lea     r9, [rbp+820h+pszPath]
0x18026cb43  lea     r8, aSBurnD; "%s\\Burn%d"
0x18026cb4a  mov     edx, 104h; unsigned __int64
0x18026cb4f  mov     rcx, rdi; unsigned __int16 *
0x18026cb52  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18026cb57  test    eax, eax
0x18026cb59  js      short loc_18026CB34
0x18026cb5b  mov     rcx, rdi; lpFileName
0x18026cb5e  call    cs:__imp_GetFileAttributesW
0x18026cb65  nop     dword ptr [rax+rax+00h]
0x18026cb6a  cmp     eax, 0FFFFFFFFh
0x18026cb6d  jz      short loc_18026CB7E
0x18026cb6f  add     [rsp+920h+var_8F0], esi
0x18026cb73  inc     r14d
0x18026cb76  cmp     r14d, 32h ; '2'
0x18026cb7a  jb      short loc_18026CB34
0x18026cb7c  jmp     short loc_18026CBF5
0x18026cb7e  xor     r8d, r8d; psa
0x18026cb81  mov     rdx, rdi; pszPath
0x18026cb84  xor     ecx, ecx; hwnd
0x18026cb86  call    cs:__imp_SHCreateDirectoryExW
0x18026cb8d  nop     dword ptr [rax+rax+00h]
0x18026cb92  test    eax, eax
0x18026cb94  jnz     short loc_18026CBF5
0x18026cb96  mov     ebx, esi
0x18026cb98  add     [rsp+920h+var_8F0], esi
0x18026cb9c  mov     dword ptr [rsp+920h+pcbData], r15d; cbData
0x18026cba1  lea     rax, [rsp+920h+var_8F0]
0x18026cba6  mov     [rsp+920h+pvData], rax; pvData
0x18026cbab  mov     r9d, r15d; dwType
0x18026cbae  lea     r8, aNextstagingpat; "NextStagingPathIndex"
0x18026cbb5  lea     rdx, aSoftwareMicros_179; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18026cbbc  mov     rcx, r12; hkey
0x18026cbbf  call    cs:__imp_SHSetValueW
0x18026cbc6  nop     dword ptr [rax+rax+00h]
0x18026cbcb  jmp     short loc_18026CBD5
0x18026cbcd  mov     esi, r13d
0x18026cbd0  test    r12d, r12d
0x18026cbd3  jz      short loc_18026CBF5
0x18026cbd5  mov     edx, 3; dwFileAttributes
0x18026cbda  mov     rcx, rdi; lpFileName
0x18026cbdd  call    cs:__imp_SetFileAttributesW
0x18026cbe4  nop     dword ptr [rax+rax+00h]
0x18026cbe9  test    esi, esi
0x18026cbeb  jz      short loc_18026CBF5
0x18026cbed  mov     rcx, rdi; unsigned __int16 *
0x18026cbf0  call    ?_CreateLocalizationDesktopIni@CCDBurn@@CAJPEBG@Z; CCDBurn::_CreateLocalizationDesktopIni(ushort const *)
0x18026cbf5  mov     eax, ebx
0x18026cbf7  mov     rcx, [rbp+820h+var_40]
0x18026cbfe  xor     rcx, rsp; StackCookie
0x18026cc01  call    __security_check_cookie
0x18026cc06  mov     rbx, [rsp+920h+arg_0]
0x18026cc0e  add     rsp, 8F0h
0x18026cc15  pop     r15
0x18026cc17  pop     r14
0x18026cc19  pop     r13
0x18026cc1b  pop     r12
0x18026cc1d  pop     rdi
0x18026cc1e  pop     rsi
0x18026cc1f  pop     rbp
0x18026cc20  retn
```
