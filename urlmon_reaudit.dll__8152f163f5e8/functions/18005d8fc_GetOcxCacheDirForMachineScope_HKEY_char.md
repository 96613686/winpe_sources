# GetOcxCacheDirForMachineScope(HKEY__ *,char *)

- ea: `0x18005d8fc`
- end: `0x18005db21`
- name: `?GetOcxCacheDirForMachineScope@@YAJPEAUHKEY__@@PEAD@Z`
- size: `549`
- prototype: `__int64 __fastcall(HKEY hKey, char *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18005d404`

## callees

- `0x18005d8fc`
- `0x18005e1c0`
- `0x1800bbee0`
- `0x180129010`

## import_xrefs

- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsA` at `0x18005d95c`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsA` at `0x18005d95c`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18005d9e7`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18005d9e7`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18005d99e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18005d9c0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18005d99e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18005d9c0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x18005dab4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x18005dab4`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x18005d947`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x18005da24`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x18005d947`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x18005da24`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x18005daf1`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x18005daf1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005db01`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005db01`
- `api-ms-win-core-sysinfo-l1-1-0!GetWindowsDirectoryA` at `0x18005da44`
- `api-ms-win-core-sysinfo-l1-1-0!GetWindowsDirectoryA` at `0x18005da44`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryA` at `0x18005d977`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryA` at `0x18005d977`

## string_xrefs

- `0x18005d93d`: `ActiveXCache`
- `0x18005da13`: `ActiveXCache`
- `0x18005dad6`: `ActiveXCache`
- `0x18005d970`: `occache.dll`
- `0x18005d98f`: `DllRegisterServer`
- `0x18005d9b6`: `DllInstall`

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
  v3 = RegQueryValueExA(hKey, "ActiveXCache", 0, &Type, (LPBYTE)g_szOCXCacheDirMachineScope, &cbData);
  if ( v3 || !PathFileExistsA(g_szOCXCacheDirMachineScope) )
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
        v3 = RegQueryValueExA(hKey, "ActiveXCache", 0, &Type, (LPBYTE)g_szOCXCacheDirMachineScope, &cbData);
      }
    }
    if ( v3 )
    {
      WindowsDirectoryA = GetWindowsDirectoryA(g_szOCXCacheDirMachineScope, 0x104u);
      if ( WindowsDirectoryA )
      {
        if ( g_szOCXCacheDirMachineScope[WindowsDirectoryA - 1] != 92
          && (int)StringCchCatA(g_szOCXCacheDirMachineScope, 0x104u, "\\") < 0 )
        {
          return 0;
        }
      }
      else
      {
        g_szOCXCacheDirMachineScope[0] = 0;
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
          while ( g_szOCXCacheDirMachineScope[v14] );
          RegSetValueExA(phkResult, "ActiveXCache", 0, 1u, (const BYTE *)g_szOCXCacheDirMachineScope, v14 + 1);
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
0x18005d8fc  mov     r11, rsp
0x18005d8ff  mov     [r11+8], rbx
0x18005d903  mov     [r11+10h], rdx
0x18005d907  push    rbp
0x18005d908  push    rsi
0x18005d909  push    rdi
0x18005d90a  push    r12
0x18005d90c  push    r14
0x18005d90e  mov     rbp, rsp
0x18005d911  sub     rsp, 30h
0x18005d915  lea     rax, [rbp+cbData]
0x18005d919  mov     [rbp+cbData], 103h
0x18005d920  mov     [r11-30h], rax
0x18005d924  lea     r12, ?g_szOCXCacheDirMachineScope@@3PADA; char near * g_szOCXCacheDirMachineScope
0x18005d92b  lea     r9, [rbp+Type]; lpType
0x18005d92f  mov     [r11-38h], r12
0x18005d933  xor     r8d, r8d; lpReserved
0x18005d936  mov     [rbp+Type], 1
0x18005d93d  lea     rdx, aActivexcache; "ActiveXCache"
0x18005d944  mov     r14, rcx
0x18005d947  call    cs:__imp_RegQueryValueExA
0x18005d94e  nop     dword ptr [rax+rax+00h]
0x18005d953  mov     esi, eax
0x18005d955  test    eax, eax
0x18005d957  jnz     short loc_18005D970
0x18005d959  mov     rcx, r12; pszPath
0x18005d95c  call    cs:__imp_PathFileExistsA
0x18005d963  nop     dword ptr [rax+rax+00h]
0x18005d968  test    eax, eax
0x18005d96a  jnz     loc_18005DB0D
0x18005d970  lea     rcx, aOccacheDll_0; "occache.dll"
0x18005d977  call    cs:__imp_LoadLibraryA
0x18005d97e  nop     dword ptr [rax+rax+00h]
0x18005d983  mov     rbx, rax
0x18005d986  test    rax, rax
0x18005d989  jz      loc_18005DA32
0x18005d98f  lea     rdx, aDllregisterser_1; "DllRegisterServer"
0x18005d996  mov     rcx, rax; hModule
0x18005d999  mov     edi, 80004005h
0x18005d99e  call    cs:__imp_GetProcAddress
0x18005d9a5  nop     dword ptr [rax+rax+00h]
0x18005d9aa  test    rax, rax
0x18005d9ad  jz      short loc_18005D9B6
0x18005d9af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d9b4  mov     edi, eax
0x18005d9b6  lea     rdx, aDllinstall_0; "DllInstall"
0x18005d9bd  mov     rcx, rbx; hModule
0x18005d9c0  call    cs:__imp_GetProcAddress
0x18005d9c7  nop     dword ptr [rax+rax+00h]
0x18005d9cc  test    rax, rax
0x18005d9cf  jz      short loc_18005D9E4
0x18005d9d1  lea     rdx, pszFormat
0x18005d9d8  mov     ecx, 1
0x18005d9dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d9e2  mov     edi, eax
0x18005d9e4  mov     rcx, rbx; hLibModule
0x18005d9e7  call    cs:__imp_FreeLibrary
0x18005d9ee  nop     dword ptr [rax+rax+00h]
0x18005d9f3  test    edi, edi
0x18005d9f5  js      short loc_18005DA32
0x18005d9f7  lea     rax, [rbp+cbData]
0x18005d9fb  mov     [rbp+cbData], 103h
0x18005da02  mov     [rsp+30h+lpcbData], rax; lpcbData
0x18005da07  lea     r9, [rbp+Type]; lpType
0x18005da0b  xor     r8d, r8d; lpReserved
0x18005da0e  mov     [rsp+30h+lpData], r12; lpData
0x18005da13  lea     rdx, aActivexcache; "ActiveXCache"
0x18005da1a  mov     [rbp+Type], 1
0x18005da21  mov     rcx, r14; hKey
0x18005da24  call    cs:__imp_RegQueryValueExA
0x18005da2b  nop     dword ptr [rax+rax+00h]
0x18005da30  mov     esi, eax
0x18005da32  test    esi, esi
0x18005da34  jz      loc_18005DB0D
0x18005da3a  mov     ebx, 104h
0x18005da3f  mov     rcx, r12; lpBuffer
0x18005da42  mov     edx, ebx; uSize
0x18005da44  call    cs:__imp_GetWindowsDirectoryA
0x18005da4b  nop     dword ptr [rax+rax+00h]
0x18005da50  test    eax, eax
0x18005da52  jnz     short loc_18005DA5C
0x18005da54  mov     cs:?g_szOCXCacheDirMachineScope@@3PADA, al; char near * g_szOCXCacheDirMachineScope
0x18005da5a  jmp     short loc_18005DA7F
0x18005da5c  dec     eax
0x18005da5e  cmp     byte ptr [rax+r12], 5Ch ; '\'
0x18005da63  jz      short loc_18005DA7F
0x18005da65  lea     r8, asc_18013A808; "\\"
0x18005da6c  mov     rdx, rbx; unsigned __int64
0x18005da6f  mov     rcx, r12; char *
0x18005da72  call    ?StringCchCatA@@YAJPEAD_KPEBD@Z; StringCchCatA(char *,unsigned __int64,char const *)
0x18005da77  test    eax, eax
0x18005da79  js      loc_18005DB0D
0x18005da7f  call    ?StringCchCatNA@@YAJPEAD_KPEBD1@Z; StringCchCatNA(char *,unsigned __int64,char const *,unsigned __int64)
0x18005da84  test    eax, eax
0x18005da86  js      loc_18005DB0D
0x18005da8c  lea     rax, [rbp+phkResult]
0x18005da90  mov     [rbp+phkResult], 0
0x18005da98  mov     r9d, 0F003Fh; samDesired
0x18005da9e  mov     [rsp+30h+lpData], rax; phkResult
0x18005daa3  xor     r8d, r8d; ulOptions
0x18005daa6  lea     rdx, aSoftwareMicros_61; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18005daad  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18005dab4  call    cs:__imp_RegOpenKeyExA
0x18005dabb  nop     dword ptr [rax+rax+00h]
0x18005dac0  test    eax, eax
0x18005dac2  jnz     short loc_18005DB0D
0x18005dac4  or      rax, 0FFFFFFFFFFFFFFFFh
0x18005dac8  inc     rax
0x18005dacb  cmp     byte ptr [r12+rax], 0
0x18005dad0  jnz     short loc_18005DAC8
0x18005dad2  mov     rcx, [rbp+phkResult]; hKey
0x18005dad6  lea     rdx, aActivexcache; "ActiveXCache"
0x18005dadd  inc     eax
0x18005dadf  mov     r9d, 1; dwType
0x18005dae5  mov     dword ptr [rsp+30h+lpcbData], eax; cbData
0x18005dae9  xor     r8d, r8d; Reserved
0x18005daec  mov     [rsp+30h+lpData], r12; lpData
0x18005daf1  call    cs:__imp_RegSetValueExA
0x18005daf8  nop     dword ptr [rax+rax+00h]
0x18005dafd  mov     rcx, [rbp+phkResult]; hKey
0x18005db01  call    cs:__imp_RegCloseKey
0x18005db08  nop     dword ptr [rax+rax+00h]
0x18005db0d  mov     rbx, [rsp+30h+arg_0]
0x18005db12  xor     eax, eax
0x18005db14  add     rsp, 30h
0x18005db18  pop     r14
0x18005db1a  pop     r12
0x18005db1c  pop     rdi
0x18005db1d  pop     rsi
0x18005db1e  pop     rbp
0x18005db1f  retn
```
