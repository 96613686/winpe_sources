# CCDBurn::_EnsureStagingFolder(int,ushort const *,ushort *,ulong)

- ea: `0x18025553c`
- end: `0x1802558fd`
- name: `?_EnsureStagingFolder@CCDBurn@@CAHHPEBGPEAGK@Z`
- size: `961`
- prototype: `__int64 __fastcall(int, const unsigned __int16 *, unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, reparse_path, registry_config, broker_com_uri`

## callers

- `0x18015819c`

## callees

- `0x18000d4b0`
- `0x18000d4c0`
- `0x18001bf10`
- `0x18003eab0`
- `0x180233280`
- `0x1802342fc`
- `0x1802544b4`
- `0x18025553c`
- `0x180257188`
- `0x180258c04`
- `0x180571010`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180255852`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180255852`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x1802558bf`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x1802558bf`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180255721`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180255742`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180255721`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180255742`
- `api-ms-win-core-path-l1-1-0!PathCchRemoveFileSpec` at `0x1802555f4`
- `api-ms-win-core-path-l1-1-0!PathCchRemoveFileSpec` at `0x1802555f4`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x1802555a1`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x180255765`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x1802555a1`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x180255765`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x180255581`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x180255581`
- `api-ms-win-shcore-registry-l1-1-0!SHGetValueW` at `0x180255664`
- `api-ms-win-shcore-registry-l1-1-0!SHGetValueW` at `0x18025581f`
- `api-ms-win-shcore-registry-l1-1-0!SHGetValueW` at `0x180255664`
- `api-ms-win-shcore-registry-l1-1-0!SHGetValueW` at `0x18025581f`
- `api-ms-win-shcore-registry-l1-1-0!SHSetValueW` at `0x1802558a7`
- `api-ms-win-shcore-registry-l1-1-0!SHSetValueW` at `0x1802558a7`
- `SHCORE!__imp_SHCreateDirectoryExW` at `0x180255874`
- `SHCORE!__imp_SHCreateDirectoryExW` at `0x180255874`
- `api-ms-win-storage-exports-internal-l1-1-0!SHGetFolderPathEx` at `0x1802555ce`
- `api-ms-win-storage-exports-internal-l1-1-0!SHGetFolderPathEx` at `0x1802555ce`
- `api-ms-win-storage-exports-external-l1-1-0!STORAGE_CEnumFiles_CreateInstance` at `0x1802556aa`
- `api-ms-win-storage-exports-external-l1-1-0!STORAGE_CEnumFiles_CreateInstance` at `0x1802556aa`

## string_xrefs

- `0x18025564f`: `StagingPath`
- `0x180255807`: `NextStagingPathIndex`
- `0x180255896`: `NextStagingPathIndex`

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
0x18025553c  mov     [rsp-8+arg_0], rbx
0x180255541  push    rbp
0x180255542  push    rsi
0x180255543  push    rdi
0x180255544  push    r12
0x180255546  push    r13
0x180255548  push    r14
0x18025554a  push    r15
0x18025554c  lea     rbp, [rsp-7F0h]
0x180255554  sub     rsp, 8F0h
0x18025555b  mov     rax, cs:__security_cookie
0x180255562  xor     rax, rsp
0x180255565  mov     [rbp+820h+var_40], rax
0x18025556c  mov     rdi, r8
0x18025556f  mov     r14, rdx
0x180255572  mov     esi, ecx
0x180255574  xor     r13d, r13d
0x180255577  mov     [r8], r13w
0x18025557b  mov     ebx, r13d
0x18025557e  mov     rcx, rdx; pszPath
0x180255581  call    cs:__imp_PathFindFileNameW
0x180255587  mov     r9, rax; pszMore
0x18025558a  lea     r8, aSoftwareMicros_179; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180255591  mov     r15d, 104h
0x180255597  mov     edx, r15d; cchPathOut
0x18025559a  lea     rcx, [rbp+820h+pszPathOut]; pszPathOut
0x1802555a1  call    cs:__imp_PathCchCombine
0x1802555a7  test    eax, eax
0x1802555a9  js      loc_1802558D1
0x1802555af  mov     [rbp+820h+pszPath], r13w
0x1802555b7  mov     dword ptr [rsp+920h+pvData], r15d
0x1802555bc  mov     r9, rdi
0x1802555bf  xor     r8d, r8d
0x1802555c2  mov     edx, 8000h
0x1802555c7  lea     rcx, FOLDERID_CDBurning
0x1802555ce  call    cs:__imp_SHGetFolderPathEx
0x1802555d4  test    eax, eax
0x1802555d6  js      short loc_180255607
0x1802555d8  mov     r8, rdi; unsigned __int16 *
0x1802555db  mov     edx, r15d; unsigned __int64
0x1802555de  lea     rcx, [rbp+820h+pszPath]; unsigned __int16 *
0x1802555e5  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1802555ea  mov     edx, r15d; cchPath
0x1802555ed  lea     rcx, [rbp+820h+pszPath]; pszPath
0x1802555f4  call    cs:__imp_PathCchRemoveFileSpec
0x1802555fa  mov     rdx, r14; unsigned __int16 *
0x1802555fd  mov     rcx, rdi; lpString2
0x180255600  call    ?_IsStagingPathOK@CCDBurn@@CAHPEBG0@Z; CCDBurn::_IsStagingPathOK(ushort const *,ushort const *)
0x180255605  mov     ebx, eax
0x180255607  mov     r12d, ebx
0x18025560a  test    ebx, ebx
0x18025560c  jnz     loc_1802558AF
0x180255612  mov     rdx, rdi; unsigned __int16 *
0x180255615  mov     ecx, esi; int
0x180255617  call    ?_GetDriveLetterBasedStagingPath@CCDBurn@@CAHHPEAGK@Z; CCDBurn::_GetDriveLetterBasedStagingPath(int,ushort *,ulong)
0x18025561c  test    eax, eax
0x18025561e  jz      short loc_180255635
0x180255620  mov     rdx, r14; unsigned __int16 *
0x180255623  mov     rcx, rdi; lpString2
0x180255626  call    ?_IsStagingPathOK@CCDBurn@@CAHPEBG0@Z; CCDBurn::_IsStagingPathOK(ushort const *,ushort const *)
0x18025562b  mov     ebx, eax
0x18025562d  test    eax, eax
0x18025562f  jnz     loc_1802558AF
0x180255635  mov     [rsp+920h+var_8F0], 208h
0x18025563d  lea     rax, [rsp+920h+var_8F0]
0x180255642  mov     [rsp+920h+pcbData], rax; pcbData
0x180255647  mov     [rsp+920h+pvData], rdi; pvData
0x18025564c  xor     r9d, r9d; pdwType
0x18025564f  lea     r8, aStagingpath; "StagingPath"
0x180255656  lea     rdx, [rbp+820h+pszPathOut]; pszSubKey
0x18025565d  mov     rcx, 0FFFFFFFF80000001h; hkey
0x180255664  call    cs:__imp_SHGetValueW
0x18025566a  test    eax, eax
0x18025566c  jnz     short loc_180255683
0x18025566e  mov     rdx, r14; unsigned __int16 *
0x180255671  mov     rcx, rdi; lpString2
0x180255674  call    ?_IsStagingPathOK@CCDBurn@@CAHPEBG0@Z; CCDBurn::_IsStagingPathOK(ushort const *,ushort const *)
0x180255679  mov     ebx, eax
0x18025567b  test    eax, eax
0x18025567d  jnz     loc_1802558AF
0x180255683  cmp     [rbp+820h+pszPath], r13w
0x18025568b  jz      loc_1802558D1
0x180255691  lea     rcx, [rsp+920h+var_8E8]; void *
0x180255696  call    ??0?$CComPtr@UIClassFactory@@@ATL@@QEAA@XZ; ATL::CComPtr<IClassFactory>::CComPtr<IClassFactory>(void)
0x18025569b  nop
0x18025569c  lea     r8, [rsp+920h+var_8E8]
0x1802556a1  lea     rdx, _GUID_4e31e71d_945b_471d_88a9_061b207facaa
0x1802556a8  xor     ecx, ecx
0x1802556aa  call    cs:__imp_STORAGE_CEnumFiles_CreateInstance
0x1802556b0  mov     esi, 1
0x1802556b5  test    eax, eax
0x1802556b7  js      loc_1802557C3
0x1802556bd  xor     edx, edx; Val
0x1802556bf  mov     r8d, 268h; Size
0x1802556c5  lea     rcx, [rsp+920h+var_8E0]; void *
0x1802556ca  call    memset_0
0x1802556cf  mov     rcx, qword ptr [rsp+920h+var_8E8]
0x1802556d4  mov     rax, [rcx]
0x1802556d7  lea     r8, [rsp+920h+var_8E0]
0x1802556dc  lea     rdx, [rbp+820h+pszPath]
0x1802556e3  mov     rax, [rax+20h]
0x1802556e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802556ec  mov     r15d, eax
0x1802556ef  test    eax, eax
0x1802556f1  jnz     loc_1802557C3
0x1802556f7  test    ebx, ebx
0x1802556f9  jnz     loc_1802557C3
0x1802556ff  test    [rsp+920h+var_8E0], 10h
0x180255704  jz      loc_1802557A1
0x18025570a  mov     dword ptr [rsp+920h+pvData], esi; bIgnoreCase
0x18025570e  or      r9d, 0FFFFFFFFh; cchCount2
0x180255712  lea     r8, asc_1805F0400; "."
0x180255719  or      edx, r9d; cchCount1
0x18025571c  lea     rcx, [rsp+920h+String1]; lpString1
0x180255721  call    cs:__imp_CompareStringOrdinal
0x180255727  cmp     eax, 2
0x18025572a  jz      short loc_1802557A1
0x18025572c  mov     dword ptr [rsp+920h+pvData], esi; bIgnoreCase
0x180255730  or      edx, 0FFFFFFFFh; cchCount1
0x180255733  mov     r9d, edx; cchCount2
0x180255736  lea     r8, asc_1805F0920; ".."
0x18025573d  lea     rcx, [rsp+920h+String1]; lpString1
0x180255742  call    cs:__imp_CompareStringOrdinal
0x180255748  cmp     eax, 2
0x18025574b  jz      short loc_1802557A1
0x18025574d  lea     r9, [rsp+920h+String1]; pszMore
0x180255752  lea     r8, [rbp+820h+pszPath]; pszPathIn
0x180255759  mov     edx, 104h; cchPathOut
0x18025575e  lea     rcx, [rbp+820h+String2]; pszPathOut
0x180255765  call    cs:__imp_PathCchCombine
0x18025576b  test    eax, eax
0x18025576d  js      short loc_1802557A1
0x18025576f  mov     rdx, r14; unsigned __int16 *
0x180255772  lea     rcx, [rbp+820h+String2]; lpString2
0x180255779  call    ?_IsStagingPathOK@CCDBurn@@CAHPEBG0@Z; CCDBurn::_IsStagingPathOK(ushort const *,ushort const *)
0x18025577e  test    eax, eax
0x180255780  jz      short loc_1802557A1
0x180255782  lea     r8, [rbp+820h+String2]; unsigned __int16 *
0x180255789  mov     edx, 104h; unsigned __int64
0x18025578e  mov     rcx, rdi; unsigned __int16 *
0x180255791  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180255796  test    eax, eax
0x180255798  js      short loc_18025579E
0x18025579a  mov     ebx, esi
0x18025579c  jmp     short loc_1802557BA
0x18025579e  mov     ebx, r13d
0x1802557a1  mov     rcx, qword ptr [rsp+920h+var_8E8]
0x1802557a6  mov     rax, [rcx]
0x1802557a9  lea     rdx, [rsp+920h+var_8E0]
0x1802557ae  mov     rax, [rax+38h]
0x1802557b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802557b7  mov     r15d, eax
0x1802557ba  test    r15d, r15d
0x1802557bd  jz      loc_1802556F7
0x1802557c3  lea     rcx, [rsp+920h+var_8E8]; void *
0x1802557c8  call    ??1?$CComPtr@UIUICommandWithBackgroundColor@@@ATL@@QEAA@XZ; ATL::CComPtr<IUICommandWithBackgroundColor>::~CComPtr<IUICommandWithBackgroundColor>(void)
0x1802557cd  test    ebx, ebx
0x1802557cf  jnz     loc_1802558AF
0x1802557d5  cmp     [rbp+820h+pszPath], r13w
0x1802557dd  jz      loc_1802558D1
0x1802557e3  mov     [rsp+920h+var_8F0], esi
0x1802557e7  lea     r15d, [rbx+4]
0x1802557eb  mov     [rsp+920h+var_8E8], r15d
0x1802557f0  lea     rax, [rsp+920h+var_8E8]
0x1802557f5  mov     [rsp+920h+pcbData], rax; pcbData
0x1802557fa  lea     rax, [rsp+920h+var_8F0]
0x1802557ff  mov     [rsp+920h+pvData], rax; pvData
0x180255804  xor     r9d, r9d; pdwType
0x180255807  lea     r8, aNextstagingpat; "NextStagingPathIndex"
0x18025580e  lea     rdx, aSoftwareMicros_179; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180255815  mov     r12, 0FFFFFFFF80000001h
0x18025581c  mov     rcx, r12; hkey
0x18025581f  call    cs:__imp_SHGetValueW
0x180255825  mov     r14d, r13d
0x180255828  mov     eax, [rsp+920h+var_8F0]
0x18025582c  mov     dword ptr [rsp+920h+pvData], eax
0x180255830  lea     r9, [rbp+820h+pszPath]
0x180255837  lea     r8, aSBurnD; "%s\\Burn%d"
0x18025583e  mov     edx, 104h; unsigned __int64
0x180255843  mov     rcx, rdi; unsigned __int16 *
0x180255846  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18025584b  test    eax, eax
0x18025584d  js      short loc_180255828
0x18025584f  mov     rcx, rdi; lpFileName
0x180255852  call    cs:__imp_GetFileAttributesW
0x180255858  cmp     eax, 0FFFFFFFFh
0x18025585b  jz      short loc_18025586C
0x18025585d  add     [rsp+920h+var_8F0], esi
0x180255861  inc     r14d
0x180255864  cmp     r14d, 32h ; '2'
0x180255868  jb      short loc_180255828
0x18025586a  jmp     short loc_1802558D1
0x18025586c  xor     r8d, r8d; psa
0x18025586f  mov     rdx, rdi; pszPath
0x180255872  xor     ecx, ecx; hwnd
0x180255874  call    cs:__imp_SHCreateDirectoryExW
0x18025587a  test    eax, eax
0x18025587c  jnz     short loc_1802558D1
0x18025587e  mov     ebx, esi
0x180255880  add     [rsp+920h+var_8F0], esi
0x180255884  mov     dword ptr [rsp+920h+pcbData], r15d; cbData
0x180255889  lea     rax, [rsp+920h+var_8F0]
0x18025588e  mov     [rsp+920h+pvData], rax; pvData
0x180255893  mov     r9d, r15d; dwType
0x180255896  lea     r8, aNextstagingpat; "NextStagingPathIndex"
0x18025589d  lea     rdx, aSoftwareMicros_179; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1802558a4  mov     rcx, r12; hkey
0x1802558a7  call    cs:__imp_SHSetValueW
0x1802558ad  jmp     short loc_1802558B7
0x1802558af  mov     esi, r13d
0x1802558b2  test    r12d, r12d
0x1802558b5  jz      short loc_1802558D1
0x1802558b7  mov     edx, 3; dwFileAttributes
0x1802558bc  mov     rcx, rdi; lpFileName
0x1802558bf  call    cs:__imp_SetFileAttributesW
0x1802558c5  test    esi, esi
0x1802558c7  jz      short loc_1802558D1
0x1802558c9  mov     rcx, rdi; unsigned __int16 *
0x1802558cc  call    ?_CreateLocalizationDesktopIni@CCDBurn@@CAJPEBG@Z; CCDBurn::_CreateLocalizationDesktopIni(ushort const *)
0x1802558d1  mov     eax, ebx
0x1802558d3  mov     rcx, [rbp+820h+var_40]
0x1802558da  xor     rcx, rsp; StackCookie
0x1802558dd  call    __security_check_cookie
0x1802558e2  mov     rbx, [rsp+920h+arg_0]
0x1802558ea  add     rsp, 8F0h
0x1802558f1  pop     r15
0x1802558f3  pop     r14
0x1802558f5  pop     r13
0x1802558f7  pop     r12
0x1802558f9  pop     rdi
0x1802558fa  pop     rsi
0x1802558fb  pop     rbp
0x1802558fc  retn
```
