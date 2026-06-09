# _GetRegistryCompatFlags(ushort const *,int *,uint)

- ea: `0x18002c850`
- end: `0x18002cb02`
- name: `?_GetRegistryCompatFlags@@YAXPEBGPEAHI@Z`
- size: `690`
- prototype: `void __fastcall(const unsigned __int16 *, int *, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, reparse_path, registry_config, broker_com_uri`

## callers

- `0x18002c6f0`

## callees

- `0x180005da0`
- `0x180006ac0`
- `0x18002c850`
- `0x18002cb08`
- `0x180066910`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18002c9c2`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18002c9c2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002c9d1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002ca49`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002c9d1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002ca49`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002c8ce`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002c989`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002c8ce`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002c989`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18002ca39`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18002ca39`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathCombineW` at `0x18002ca2b`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathCombineW` at `0x18002ca2b`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x18002c885`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x18002c885`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathRemoveFileSpecW` at `0x18002c951`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathRemoveFileSpecW` at `0x18002c951`

## string_xrefs

- `0x18002c88e`: `SOFTWARE\Microsoft\Windows\CurrentVersion\ShellCompatibility\Applications\%s`

## pseudocode

```c
void __fastcall _GetRegistryCompatFlags(const unsigned __int16 *a1, int *a2)
{
  LPWSTR FileNameW; // rax
  __int64 v4; // rcx
  WCHAR *v5; // rax
  const unsigned __int16 *v6; // r8
  __int64 v7; // rdx
  WCHAR *v8; // rcx
  DWORD v9; // esi
  DWORD v10; // edx
  const WCHAR *v11; // rax
  LSTATUS ValueW; // eax
  WCHAR *v13; // rdx
  __int64 i; // rbx
  __int64 v15; // rax
  DWORD pcbData; // [rsp+40h] [rbp-C0h] BYREF
  DWORD cchName; // [rsp+44h] [rbp-BCh] BYREF
  HKEY hkey; // [rsp+48h] [rbp-B8h] BYREF
  HKEY hKey; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR SubKey[264]; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR pszPath[264]; // [rsp+270h] [rbp+170h] BYREF

  FileNameW = PathFindFileNameW(a1);
  cchName = 0;
  hKey = 0;
  StringCchPrintfW(
    SubKey,
    0x104u,
    L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\ShellCompatibility\\Applications\\%s",
    FileNameW);
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 9u, &hKey) )
  {
    v4 = 2147483646;
    v5 = pszPath;
    v6 = a1;
    v7 = 260;
    do
    {
      if ( !v4 )
        break;
      if ( !*v6 )
        break;
      *v5++ = *v6++;
      --v4;
      --v7;
    }
    while ( v7 );
    v8 = v5 - 1;
    if ( v7 )
      v8 = v5;
    *v8 = 0;
    PathRemoveFileSpecW(pszPath);
    SubKey[0] = 0;
    v9 = 0;
    do
    {
      hkey = 0;
      if ( !RegOpenKeyExW(hKey, SubKey, 0, 1u, &hkey) )
      {
        pcbData = 520;
        if ( SHRegGetValueW(hkey, 0, L"RequiredFile", 0xFFFF, 0, SubKey, &pcbData)
          || (v11 = PathCombineW(SubKey, pszPath, SubKey)) == 0
          || GetFileAttributesW(v11) != -1 )
        {
          pcbData = 520;
          ValueW = SHRegGetValueW(hkey, 0, L"Version", 0xFFFF, 0, SubKey, &pcbData);
          v13 = SubKey;
          if ( ValueW )
            v13 = 0;
          if ( (unsigned int)_IsAppCompatVersion(a1, v13) )
          {
            for ( i = 0; i != 25; ++i )
            {
              if ( !SHRegGetValueW(hkey, 0, (&off_1800A4D48)[2 * i], 0xFFFF, 0, 0, 0) )
              {
                v15 = (unsigned int)dword_1800A4D40[4 * i];
                if ( (unsigned int)v15 < 0x1B )
                  dword_1800E1C90[v15] = 1;
              }
            }
          }
        }
        RegCloseKey(hkey);
      }
      v10 = v9++;
      cchName = 260;
    }
    while ( !RegEnumKeyExW(hKey, v10, SubKey, &cchName, 0, 0, 0, 0) );
    RegCloseKey(hKey);
  }
}

```

## disassembly

```asm
0x18002c850  mov     [rsp-8+arg_8], rbx
0x18002c855  mov     [rsp-8+arg_10], rsi
0x18002c85a  push    rbp
0x18002c85b  push    rdi
0x18002c85c  push    r13
0x18002c85e  push    r14
0x18002c860  push    r15
0x18002c862  lea     rbp, [rsp-390h]
0x18002c86a  sub     rsp, 490h
0x18002c871  mov     rax, cs:__security_cookie
0x18002c878  xor     rax, rsp
0x18002c87b  mov     [rbp+3B0h+var_30], rax
0x18002c882  mov     r14, rcx
0x18002c885  call    cs:__imp_PathFindFileNameW
0x18002c88b  xor     r15d, r15d
0x18002c88e  lea     r8, aSoftwareMicros_4; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18002c895  mov     r9, rax
0x18002c898  mov     [rsp+4B0h+cchName], r15d
0x18002c89d  mov     edx, 104h; unsigned __int64
0x18002c8a2  mov     [rsp+4B0h+hKey], r15
0x18002c8a7  lea     rcx, [rsp+4B0h+SubKey]; unsigned __int16 *
0x18002c8ac  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002c8b1  lea     rax, [rsp+4B0h+hKey]
0x18002c8b6  xor     r8d, r8d; ulOptions
0x18002c8b9  lea     r9d, [r15+9]; samDesired
0x18002c8bd  mov     [rsp+4B0h+phkResult], rax; phkResult
0x18002c8c2  lea     rdx, [rsp+4B0h+SubKey]; lpSubKey
0x18002c8c7  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002c8ce  call    cs:__imp_RegOpenKeyExW
0x18002c8d4  test    eax, eax
0x18002c8d6  jz      short loc_18002C903
0x18002c8d8  mov     rcx, [rbp+3B0h+var_30]
0x18002c8df  xor     rcx, rsp; StackCookie
0x18002c8e2  call    __security_check_cookie
0x18002c8e7  lea     r11, [rsp+4B0h+var_20]
0x18002c8ef  mov     rbx, [r11+38h]
0x18002c8f3  mov     rsi, [r11+40h]
0x18002c8f7  mov     rsp, r11
0x18002c8fa  pop     r15
0x18002c8fc  pop     r14
0x18002c8fe  pop     r13
0x18002c900  pop     rdi
0x18002c901  pop     rbp
0x18002c902  retn
0x18002c903  mov     ecx, 7FFFFFFEh
0x18002c908  lea     rax, [rbp+3B0h+pszPath]
0x18002c90f  mov     r8, r14
0x18002c912  mov     edx, 104h
0x18002c917  test    rcx, rcx
0x18002c91a  jz      short loc_18002C93B
0x18002c91c  movzx   r9d, word ptr [r8]
0x18002c920  test    r9w, r9w
0x18002c924  jz      short loc_18002C93B
0x18002c926  mov     [rax], r9w
0x18002c92a  add     r8, 2
0x18002c92e  add     rax, 2
0x18002c932  dec     rcx
0x18002c935  sub     rdx, 1
0x18002c939  jnz     short loc_18002C917
0x18002c93b  test    rdx, rdx
0x18002c93e  lea     rcx, [rax-2]
0x18002c942  cmovnz  rcx, rax
0x18002c946  mov     [rcx], r15w
0x18002c94a  lea     rcx, [rbp+3B0h+pszPath]; pszPath
0x18002c951  call    cs:__imp_PathRemoveFileSpecW
0x18002c957  mov     [rsp+4B0h+SubKey], r15w
0x18002c95d  lea     r13, __ImageBase
0x18002c964  mov     esi, r15d
0x18002c967  mov     rcx, [rsp+4B0h+hKey]; hKey
0x18002c96c  lea     rax, [rsp+4B0h+hkey]
0x18002c971  mov     r9d, 1; samDesired
0x18002c977  mov     [rsp+4B0h+phkResult], rax; phkResult
0x18002c97c  xor     r8d, r8d; ulOptions
0x18002c97f  mov     [rsp+4B0h+hkey], r15
0x18002c984  lea     rdx, [rsp+4B0h+SubKey]; lpSubKey
0x18002c989  call    cs:__imp_RegOpenKeyExW
0x18002c98f  test    eax, eax
0x18002c991  jz      short loc_18002C9DC
0x18002c993  mov     rcx, [rsp+4B0h+hKey]; hKey
0x18002c998  lea     r9, [rsp+4B0h+cchName]; lpcchName
0x18002c99d  mov     [rsp+4B0h+lpftLastWriteTime], r15; lpftLastWriteTime
0x18002c9a2  lea     r8, [rsp+4B0h+SubKey]; lpName
0x18002c9a7  mov     [rsp+4B0h+lpcchClass], r15; lpcchClass
0x18002c9ac  mov     edx, esi; dwIndex
0x18002c9ae  mov     [rsp+4B0h+lpClass], r15; lpClass
0x18002c9b3  inc     esi
0x18002c9b5  mov     [rsp+4B0h+phkResult], r15; lpReserved
0x18002c9ba  mov     [rsp+4B0h+cchName], 104h
0x18002c9c2  call    cs:__imp_RegEnumKeyExW
0x18002c9c8  test    eax, eax
0x18002c9ca  jz      short loc_18002C967
0x18002c9cc  mov     rcx, [rsp+4B0h+hKey]; hKey
0x18002c9d1  call    cs:__imp_RegCloseKey
0x18002c9d7  jmp     loc_18002C8D8
0x18002c9dc  mov     rcx, [rsp+4B0h+hkey]; hkey
0x18002c9e1  lea     rax, [rsp+4B0h+pcbData]
0x18002c9e6  mov     [rsp+4B0h+lpcchClass], rax; pcbData
0x18002c9eb  lea     r8, pszValue; "RequiredFile"
0x18002c9f2  lea     rax, [rsp+4B0h+SubKey]
0x18002c9f7  mov     [rsp+4B0h+pcbData], 208h
0x18002c9ff  mov     [rsp+4B0h+lpClass], rax; pvData
0x18002ca04  mov     r9d, 0FFFFh; srrfFlags
0x18002ca0a  xor     edx, edx; pszSubKey
0x18002ca0c  mov     [rsp+4B0h+phkResult], r15; pdwType
0x18002ca11  call    SHRegGetValueW
0x18002ca16  test    eax, eax
0x18002ca18  jnz     short loc_18002CA54
0x18002ca1a  lea     r8, [rsp+4B0h+SubKey]; pszFile
0x18002ca1f  lea     rdx, [rbp+3B0h+pszPath]; pszDir
0x18002ca26  lea     rcx, [rsp+4B0h+SubKey]; pszDest
0x18002ca2b  call    cs:__imp_PathCombineW
0x18002ca31  test    rax, rax
0x18002ca34  jz      short loc_18002CA54
0x18002ca36  mov     rcx, rax; lpFileName
0x18002ca39  call    cs:__imp_GetFileAttributesW
0x18002ca3f  cmp     eax, 0FFFFFFFFh
0x18002ca42  jnz     short loc_18002CA54
0x18002ca44  mov     rcx, [rsp+4B0h+hkey]; hKey
0x18002ca49  call    cs:__imp_RegCloseKey
0x18002ca4f  jmp     loc_18002C993
0x18002ca54  mov     rcx, [rsp+4B0h+hkey]; hkey
0x18002ca59  lea     rax, [rsp+4B0h+pcbData]
0x18002ca5e  mov     [rsp+4B0h+lpcchClass], rax; pcbData
0x18002ca63  lea     r8, aVersion; "Version"
0x18002ca6a  lea     rax, [rsp+4B0h+SubKey]
0x18002ca6f  mov     [rsp+4B0h+pcbData], 208h
0x18002ca77  mov     [rsp+4B0h+lpClass], rax; pvData
0x18002ca7c  mov     r9d, 0FFFFh; srrfFlags
0x18002ca82  xor     edx, edx; pszSubKey
0x18002ca84  mov     [rsp+4B0h+phkResult], r15; pdwType
0x18002ca89  call    SHRegGetValueW
0x18002ca8e  test    eax, eax
0x18002ca90  lea     rdx, [rsp+4B0h+SubKey]
0x18002ca95  mov     rcx, r14; unsigned __int16 *
0x18002ca98  cmovnz  rdx, r15; unsigned __int16 *
0x18002ca9c  call    ?_IsAppCompatVersion@@YAHPEBG0@Z; _IsAppCompatVersion(ushort const *,ushort const *)
0x18002caa1  test    eax, eax
0x18002caa3  jz      short loc_18002CA44
0x18002caa5  mov     rbx, r15
0x18002caa8  mov     rcx, [rsp+4B0h+hkey]; hkey
0x18002caad  mov     rdi, rbx
0x18002cab0  mov     [rsp+4B0h+lpcchClass], r15; pcbData
0x18002cab5  add     rdi, rdi
0x18002cab8  mov     [rsp+4B0h+lpClass], r15; pvData
0x18002cabd  mov     r9d, 0FFFFh; srrfFlags
0x18002cac3  xor     edx, edx; pszSubKey
0x18002cac5  mov     [rsp+4B0h+phkResult], r15; pdwType
0x18002caca  mov     r8, ds:rva off_1800A4D48[r13+rdi*8]; pszValue
0x18002cad2  call    SHRegGetValueW
0x18002cad7  test    eax, eax
0x18002cad9  jnz     short loc_18002CAF4
0x18002cadb  mov     eax, ds:rva dword_1800A4D40[r13+rdi*8]
0x18002cae3  cmp     eax, 1Bh
0x18002cae6  jnb     short loc_18002CAF4
0x18002cae8  mov     rva dword_1800E1C90[r13+rax*4], 1
0x18002caf4  inc     rbx
0x18002caf7  cmp     rbx, 19h
0x18002cafb  jnz     short loc_18002CAA8
0x18002cafd  jmp     loc_18002CA44
```
