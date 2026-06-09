# GetOcxCacheDirForMachineScope(HKEY__ *,char *)

- ea: `0x180057eec`
- end: `0x1800580c6`
- name: `?GetOcxCacheDirForMachineScope@@YAJPEAUHKEY__@@PEAD@Z`
- size: `474`
- prototype: `__int64 __fastcall(HKEY hKey, char *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180057a44`

## callees

- `0x180057eec`
- `0x180058738`
- `0x1800b4460`
- `0x18011c010`

## import_xrefs

- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsA` at `0x180057f46`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsA` at `0x180057f46`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180057fb9`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180057fb9`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180057f7c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180057f98`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180057f7c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180057f98`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x18005806c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x18005806c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x180057f37`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x180057ff0`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x180057f37`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x180057ff0`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x1800580a3`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x1800580a3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800580ad`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800580ad`
- `api-ms-win-core-sysinfo-l1-1-0!GetWindowsDirectoryA` at `0x18005800a`
- `api-ms-win-core-sysinfo-l1-1-0!GetWindowsDirectoryA` at `0x18005800a`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryA` at `0x180057f5b`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryA` at `0x180057f5b`

## string_xrefs

- `0x180057f2d`: `ActiveXCache`
- `0x180057fdf`: `ActiveXCache`
- `0x180058088`: `ActiveXCache`
- `0x180057f54`: `occache.dll`
- `0x180057f6d`: `DllRegisterServer`
- `0x180057f8e`: `DllInstall`

## pseudocode

```c
__int64 __fastcall GetOcxCacheDirForMachineScope(HKEY hKey, char *a2)
{
  LSTATUS v3; // esi
  HMODULE LibraryA; // rax
  HMODULE v5; // rbx
  int v6; // edi
  __int64 (*ProcAddress)(void); // rax
  FARPROC v8; // rax
  UINT WindowsDirectoryA; // eax
  unsigned __int64 v10; // rdx
  char *v11; // rcx
  const char *v12; // r8
  unsigned __int64 v13; // r9
  __int64 v14; // rax
  DWORD cbData; // [rsp+68h] [rbp+38h] BYREF
  int v17; // [rsp+6Ch] [rbp+3Ch]
  DWORD Type; // [rsp+70h] [rbp+40h] BYREF
  HKEY phkResult; // [rsp+78h] [rbp+48h] BYREF

  v17 = HIDWORD(a2);
  cbData = 259;
  Type = 1;
  v3 = RegQueryValueExA(hKey, "ActiveXCache", 0, &Type, (LPBYTE)&g_szOCXCacheDirMachineScope, &cbData);
  if ( v3 || !PathFileExistsA(&g_szOCXCacheDirMachineScope) )
  {
    LibraryA = LoadLibraryA("occache.dll");
    v5 = LibraryA;
    if ( LibraryA )
    {
      v6 = -2147467259;
      ProcAddress = GetProcAddress(LibraryA, "DllRegisterServer");
      if ( ProcAddress )
        v6 = ProcAddress();
      v8 = GetProcAddress(v5, "DllInstall");
      if ( v8 )
        v6 = ((__int64 (__fastcall *)(__int64, const OLECHAR *))v8)(1, &pszFormat);
      FreeLibrary(v5);
      if ( v6 >= 0 )
      {
        cbData = 259;
        Type = 1;
        v3 = RegQueryValueExA(hKey, "ActiveXCache", 0, &Type, (LPBYTE)&g_szOCXCacheDirMachineScope, &cbData);
      }
    }
    if ( v3 )
    {
      WindowsDirectoryA = GetWindowsDirectoryA(&g_szOCXCacheDirMachineScope, 0x104u);
      if ( WindowsDirectoryA )
      {
        if ( *(&g_szOCXCacheDirMachineScope + WindowsDirectoryA - 1) != 92
          && (int)StringCchCatA(&g_szOCXCacheDirMachineScope, 0x104u, "\\") < 0 )
        {
          return 0;
        }
      }
      else
      {
        g_szOCXCacheDirMachineScope = 0;
      }
      if ( (int)StringCchCatNA(v11, v10, v12, v13) >= 0 )
      {
        phkResult = 0;
        if ( !RegOpenKeyExA(
                HKEY_LOCAL_MACHINE,
                "Software\\Microsoft\\Windows\\CurrentVersion\\Internet Settings",
                0,
                0xF003Fu,
                &phkResult) )
        {
          v14 = -1;
          do
            ++v14;
          while ( *(&g_szOCXCacheDirMachineScope + v14) );
          RegSetValueExA(phkResult, "ActiveXCache", 0, 1u, (const BYTE *)&g_szOCXCacheDirMachineScope, v14 + 1);
          RegCloseKey(phkResult);
        }
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180057eec  mov     r11, rsp
0x180057eef  mov     [r11+8], rbx
0x180057ef3  mov     [r11+10h], rdx
0x180057ef7  push    rbp
0x180057ef8  push    rsi
0x180057ef9  push    rdi
0x180057efa  push    r12
0x180057efc  push    r14
0x180057efe  mov     rbp, rsp
0x180057f01  sub     rsp, 30h
0x180057f05  lea     rax, [rbp+cbData]
0x180057f09  mov     [rbp+cbData], 103h
0x180057f10  mov     [r11-30h], rax
0x180057f14  lea     r12, ?g_szOCXCacheDirMachineScope@@3PADA; char near * g_szOCXCacheDirMachineScope
0x180057f1b  lea     r9, [rbp+Type]; lpType
0x180057f1f  mov     [r11-38h], r12
0x180057f23  xor     r8d, r8d; lpReserved
0x180057f26  mov     [rbp+Type], 1
0x180057f2d  lea     rdx, aActivexcache; "ActiveXCache"
0x180057f34  mov     r14, rcx
0x180057f37  call    cs:__imp_RegQueryValueExA
0x180057f3d  mov     esi, eax
0x180057f3f  test    eax, eax
0x180057f41  jnz     short loc_180057F54
0x180057f43  mov     rcx, r12; pszPath
0x180057f46  call    cs:__imp_PathFileExistsA
0x180057f4c  test    eax, eax
0x180057f4e  jnz     loc_1800580B3
0x180057f54  lea     rcx, aOccacheDll_0; "occache.dll"
0x180057f5b  call    cs:__imp_LoadLibraryA
0x180057f61  mov     rbx, rax
0x180057f64  test    rax, rax
0x180057f67  jz      loc_180057FF8
0x180057f6d  lea     rdx, aDllregisterser_1; "DllRegisterServer"
0x180057f74  mov     rcx, rax; hModule
0x180057f77  mov     edi, 80004005h
0x180057f7c  call    cs:__imp_GetProcAddress
0x180057f82  test    rax, rax
0x180057f85  jz      short loc_180057F8E
0x180057f87  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180057f8c  mov     edi, eax
0x180057f8e  lea     rdx, aDllinstall_0; "DllInstall"
0x180057f95  mov     rcx, rbx; hModule
0x180057f98  call    cs:__imp_GetProcAddress
0x180057f9e  test    rax, rax
0x180057fa1  jz      short loc_180057FB6
0x180057fa3  lea     rdx, pszFormat
0x180057faa  mov     ecx, 1
0x180057faf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180057fb4  mov     edi, eax
0x180057fb6  mov     rcx, rbx; hLibModule
0x180057fb9  call    cs:__imp_FreeLibrary
0x180057fbf  test    edi, edi
0x180057fc1  js      short loc_180057FF8
0x180057fc3  lea     rax, [rbp+cbData]
0x180057fc7  mov     [rbp+cbData], 103h
0x180057fce  mov     [rsp+30h+lpcbData], rax; lpcbData
0x180057fd3  lea     r9, [rbp+Type]; lpType
0x180057fd7  xor     r8d, r8d; lpReserved
0x180057fda  mov     [rsp+30h+lpData], r12; lpData
0x180057fdf  lea     rdx, aActivexcache; "ActiveXCache"
0x180057fe6  mov     [rbp+Type], 1
0x180057fed  mov     rcx, r14; hKey
0x180057ff0  call    cs:__imp_RegQueryValueExA
0x180057ff6  mov     esi, eax
0x180057ff8  test    esi, esi
0x180057ffa  jz      loc_1800580B3
0x180058000  mov     ebx, 104h
0x180058005  mov     rcx, r12; lpBuffer
0x180058008  mov     edx, ebx; uSize
0x18005800a  call    cs:__imp_GetWindowsDirectoryA
0x180058010  test    eax, eax
0x180058012  jnz     short loc_18005801C
0x180058014  mov     cs:?g_szOCXCacheDirMachineScope@@3PADA, al; char near * g_szOCXCacheDirMachineScope
0x18005801a  jmp     short loc_18005803B
0x18005801c  dec     eax
0x18005801e  cmp     byte ptr [rax+r12], 5Ch ; '\'
0x180058023  jz      short loc_18005803B
0x180058025  lea     r8, asc_18012AFD0; "\\"
0x18005802c  mov     rdx, rbx; unsigned __int64
0x18005802f  mov     rcx, r12; char *
0x180058032  call    ?StringCchCatA@@YAJPEAD_KPEBD@Z; StringCchCatA(char *,unsigned __int64,char const *)
0x180058037  test    eax, eax
0x180058039  js      short loc_1800580B3
0x18005803b  call    ?StringCchCatNA@@YAJPEAD_KPEBD1@Z; StringCchCatNA(char *,unsigned __int64,char const *,unsigned __int64)
0x180058040  test    eax, eax
0x180058042  js      short loc_1800580B3
0x180058044  lea     rax, [rbp+phkResult]
0x180058048  mov     [rbp+phkResult], 0
0x180058050  mov     r9d, 0F003Fh; samDesired
0x180058056  mov     [rsp+30h+lpData], rax; phkResult
0x18005805b  xor     r8d, r8d; ulOptions
0x18005805e  lea     rdx, aSoftwareMicros_61; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180058065  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18005806c  call    cs:__imp_RegOpenKeyExA
0x180058072  test    eax, eax
0x180058074  jnz     short loc_1800580B3
0x180058076  or      rax, 0FFFFFFFFFFFFFFFFh
0x18005807a  inc     rax
0x18005807d  cmp     byte ptr [r12+rax], 0
0x180058082  jnz     short loc_18005807A
0x180058084  mov     rcx, [rbp+phkResult]; hKey
0x180058088  lea     rdx, aActivexcache; "ActiveXCache"
0x18005808f  inc     eax
0x180058091  mov     r9d, 1; dwType
0x180058097  mov     dword ptr [rsp+30h+lpcbData], eax; cbData
0x18005809b  xor     r8d, r8d; Reserved
0x18005809e  mov     [rsp+30h+lpData], r12; lpData
0x1800580a3  call    cs:__imp_RegSetValueExA
0x1800580a9  mov     rcx, [rbp+phkResult]; hKey
0x1800580ad  call    cs:__imp_RegCloseKey
0x1800580b3  mov     rbx, [rsp+30h+arg_0]
0x1800580b8  xor     eax, eax
0x1800580ba  add     rsp, 30h
0x1800580be  pop     r14
0x1800580c0  pop     r12
0x1800580c2  pop     rdi
0x1800580c3  pop     rsi
0x1800580c4  pop     rbp
0x1800580c5  retn
```
