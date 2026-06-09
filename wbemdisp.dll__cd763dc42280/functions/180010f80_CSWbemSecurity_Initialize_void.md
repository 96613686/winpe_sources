# CSWbemSecurity::Initialize(void)

- ea: `0x180010f80`
- end: `0x1800112a4`
- name: `?Initialize@CSWbemSecurity@@SAXXZ`
- size: `804`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180010ee8`

## callees

- `0x180010f80`
- `0x18003405f`
- `0x180034090`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800110b1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800110b1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180010fb2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180010fb2`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180011151`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180011299`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180011151`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180011299`
- `api-ms-win-core-sysinfo-l1-1-0!GetVersionExW` at `0x180010fe4`
- `api-ms-win-core-sysinfo-l1-1-0!GetVersionExW` at `0x180010fe4`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180011121`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180011253`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180011121`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180011253`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001113a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001113a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001102e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001102e`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800111e8`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800111e8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180011204`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180011204`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180011091`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18001127e`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180011091`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18001127e`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180011214`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180011261`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180011214`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180011261`

## string_xrefs

- `0x180011045`: `\advapi32.dll`
- `0x180011115`: `Default Impersonation Level`
- `0x1800111fa`: `DuplicateTokenEx`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void CSWbemSecurity::Initialize(void)
{
  __int64 v0; // rbx
  unsigned int v1; // edi
  WCHAR *v2; // rax
  WCHAR *v3; // r14
  UINT SystemDirectoryW; // esi
  __int64 v5; // r9
  __int64 v6; // rcx
  WCHAR *v7; // rax
  __int64 v8; // r10
  WCHAR *v9; // rdx
  __int64 v10; // r8
  WCHAR *i; // rax
  WCHAR v12; // cx
  WCHAR *v13; // rcx
  HMODULE Library; // rax
  WCHAR *v15; // rax
  DWORD cbData; // [rsp+30h] [rbp-D0h] BYREF
  BYTE Data[4]; // [rsp+34h] [rbp-CCh] BYREF
  HKEY hKey; // [rsp+38h] [rbp-C8h] BYREF
  BYTE v19[8]; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v20[28]; // [rsp+48h] [rbp-B8h] BYREF
  _OSVERSIONINFOW VersionInformation; // [rsp+70h] [rbp-90h] BYREF

  EnterCriticalSection(&g_csSecurity);
  if ( !CSWbemSecurity::s_bInitialized )
  {
    memset_0(&VersionInformation.dwMajorVersion, 0, 0x110u);
    VersionInformation.dwOSVersionInfoSize = 276;
    GetVersionExW(&VersionInformation);
    CSWbemSecurity::s_dwNTMajorVersion = VersionInformation.dwMajorVersion;
    if ( VersionInformation.dwPlatformId == 2 )
    {
      CSWbemSecurity::s_bIsNT = 1;
      hKey = 0;
      if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\Wbem\\Scripting", 0, 1u, &hKey) )
      {
        if ( CSWbemSecurity::s_dwNTMajorVersion <= 4 )
        {
          *(_DWORD *)v19 = 0;
          cbData = 4;
          RegQueryValueExW(hKey, L"Enable for ASP", 0, 0, v19, &cbData);
        }
        *(_DWORD *)Data = 0;
        cbData = 4;
        if ( !RegQueryValueExW(hKey, L"Default Impersonation Level", 0, 0, Data, &cbData) )
          CSWbemSecurity::s_dwDefaultImpersonationLevel = *(_DWORD *)Data;
        RegCloseKey(hKey);
      }
      if ( CSWbemSecurity::s_hAdvapi )
        goto LABEL_8;
      *(_OWORD *)v20 = *(_OWORD *)L"\\advapi32.dll";
      *(_OWORD *)&v20[12] = *(_OWORD *)L"i32.dll";
      v0 = -1;
      do
        ++v0;
      while ( *(_WORD *)&v20[2 * v0] );
      v1 = v0 + 261;
      v2 = (WCHAR *)CWin32DefaultArena::WbemMemAlloc(saturated_mul((unsigned int)(v0 + 261), 2u));
      v3 = v2;
      if ( !v2 )
        goto LABEL_8;
      *v2 = 0;
      SystemDirectoryW = GetSystemDirectoryW(v2, 0x104u);
      if ( SystemDirectoryW <= 0x104 )
      {
LABEL_17:
        v5 = 2147483646;
        if ( v1 - 1 <= 0x7FFFFFFE )
        {
          v6 = v1;
          v7 = v3;
          while ( *v7 )
          {
            ++v7;
            if ( !--v6 )
            {
              v8 = 0;
              goto LABEL_23;
            }
          }
          v8 = v1 - v6;
LABEL_23:
          if ( v6 )
          {
            v9 = (WCHAR *)v20;
            v10 = v1 - v8;
            for ( i = &v3[v8]; v10; --v10 )
            {
              if ( !v5 )
                break;
              v12 = *v9;
              if ( !*v9 )
                break;
              ++v9;
              *i++ = v12;
              --v5;
            }
            v13 = i - 1;
            if ( v10 )
              v13 = i;
            *v13 = 0;
          }
        }
        Library = LoadLibraryExW(v3, 0, 0);
        CSWbemSecurity::s_hAdvapi = Library;
        if ( Library )
          s_pfnDuplicateTokenEx = (int (*)(void *, unsigned int, struct _SECURITY_ATTRIBUTES *, enum _SECURITY_IMPERSONATION_LEVEL, enum _TOKEN_TYPE, void **))GetProcAddress(Library, "DuplicateTokenEx");
        CWin32DefaultArena::WbemMemFree(v3);
        goto LABEL_8;
      }
      CWin32DefaultArena::WbemMemFree(v3);
      v1 = v0 + SystemDirectoryW + 1;
      v15 = (WCHAR *)CWin32DefaultArena::WbemMemAlloc(saturated_mul(v1, 2u));
      v3 = v15;
      if ( v15 )
      {
        *v15 = 0;
        GetSystemDirectoryW(v15, SystemDirectoryW);
        goto LABEL_17;
      }
    }
    else
    {
      CSWbemSecurity::s_bIsNT = 0;
    }
LABEL_8:
    CSWbemSecurity::s_bInitialized = 1;
  }
  LeaveCriticalSection(&g_csSecurity);
}

```

## disassembly

```asm
0x180010f80  push    rbp
0x180010f82  push    rbx
0x180010f83  push    rsi
0x180010f84  push    rdi
0x180010f85  push    r12
0x180010f87  push    r14
0x180010f89  push    r15
0x180010f8b  lea     rbp, [rsp-0A0h]
0x180010f93  sub     rsp, 1A0h
0x180010f9a  mov     rax, cs:__security_cookie
0x180010fa1  xor     rax, rsp
0x180010fa4  mov     [rbp+0D0h+var_40], rax
0x180010fab  lea     rcx, ?g_csSecurity@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180010fb2  call    cs:__imp_EnterCriticalSection
0x180010fb8  cmp     cs:?s_bInitialized@CSWbemSecurity@@0_NA, 0; bool CSWbemSecurity::s_bInitialized
0x180010fbf  jnz     loc_1800110AA
0x180010fc5  xor     edx, edx; Val
0x180010fc7  mov     r8d, 110h; Size
0x180010fcd  lea     rcx, [rsp+1D0h+VersionInformation.dwMajorVersion]; void *
0x180010fd2  call    memset_0
0x180010fd7  mov     [rsp+1D0h+VersionInformation.dwOSVersionInfoSize], 114h
0x180010fdf  lea     rcx, [rsp+1D0h+VersionInformation]; lpVersionInformation
0x180010fe4  call    cs:__imp_GetVersionExW
0x180010fea  mov     eax, [rsp+1D0h+VersionInformation.dwMajorVersion]
0x180010fee  mov     cs:?s_dwNTMajorVersion@CSWbemSecurity@@0KA, eax; ulong CSWbemSecurity::s_dwNTMajorVersion
0x180010ff4  cmp     [rbp+0D0h+VersionInformation.dwPlatformId], 2
0x180010ff8  jnz     loc_1800110D8
0x180010ffe  mov     cs:?s_bIsNT@CSWbemSecurity@@0_NA, 1; bool CSWbemSecurity::s_bIsNT
0x180011005  xor     r12d, r12d
0x180011008  mov     [rsp+1D0h+hKey], r12
0x18001100d  lea     rax, [rsp+1D0h+hKey]
0x180011012  mov     [rsp+1D0h+phkResult], rax; phkResult
0x180011017  mov     r9d, 1; samDesired
0x18001101d  xor     r8d, r8d; ulOptions
0x180011020  lea     rdx, SubKey; "Software\\Microsoft\\Wbem\\Scripting"
0x180011027  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001102e  call    cs:__imp_RegOpenKeyExW
0x180011034  test    eax, eax
0x180011036  jz      loc_1800110E1
0x18001103c  cmp     cs:?s_hAdvapi@CSWbemSecurity@@0PEAUHINSTANCE__@@EA, r12; HINSTANCE__ * CSWbemSecurity::s_hAdvapi
0x180011043  jnz     short loc_1800110A3
0x180011045  movups  xmm0, xmmword ptr cs:aAdvapi32Dll; "\\advapi32.dll"
0x18001104c  movups  [rsp+1D0h+var_188], xmm0
0x180011051  movups  xmm1, xmmword ptr cs:aAdvapi32Dll+0Ch; "i32.dll"
0x180011058  movups  [rsp+1D0h+var_188+0Ch], xmm1
0x18001105d  lea     rax, [rsp+1D0h+var_188]
0x180011062  mov     r15, 0FFFFFFFFFFFFFFFFh
0x180011069  mov     rbx, r15
0x18001106c  nop     dword ptr [rax+00h]
0x180011070  inc     rbx
0x180011073  cmp     [rax+rbx*2], r12w
0x180011078  jnz     short loc_180011070
0x18001107a  lea     edi, [rbx+105h]
0x180011080  mov     ecx, edi
0x180011082  mov     eax, 2
0x180011087  mul     rcx
0x18001108a  cmovb   rax, r15
0x18001108e  mov     rcx, rax
0x180011091  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x180011097  mov     r14, rax
0x18001109a  test    rax, rax
0x18001109d  jnz     loc_180011145
0x1800110a3  mov     cs:?s_bInitialized@CSWbemSecurity@@0_NA, 1; bool CSWbemSecurity::s_bInitialized
0x1800110aa  lea     rcx, ?g_csSecurity@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800110b1  call    cs:__imp_LeaveCriticalSection
0x1800110b7  mov     rcx, [rbp+0D0h+var_40]
0x1800110be  xor     rcx, rsp; StackCookie
0x1800110c1  call    __security_check_cookie
0x1800110c6  add     rsp, 1A0h
0x1800110cd  pop     r15
0x1800110cf  pop     r14
0x1800110d1  pop     r12
0x1800110d3  pop     rdi
0x1800110d4  pop     rsi
0x1800110d5  pop     rbx
0x1800110d6  pop     rbp
0x1800110d7  retn
0x1800110d8  mov     cs:?s_bIsNT@CSWbemSecurity@@0_NA, 0; bool CSWbemSecurity::s_bIsNT
0x1800110df  jmp     short loc_1800110A3
0x1800110e1  cmp     cs:?s_dwNTMajorVersion@CSWbemSecurity@@0KA, 4; ulong CSWbemSecurity::s_dwNTMajorVersion
0x1800110e8  jbe     loc_180011220
0x1800110ee  mov     dword ptr [rsp+1D0h+Data], r12d
0x1800110f3  mov     [rsp+1D0h+cbData], 4
0x1800110fb  lea     rax, [rsp+1D0h+cbData]
0x180011100  mov     [rsp+1D0h+lpcbData], rax; lpcbData
0x180011105  lea     rax, [rsp+1D0h+Data]
0x18001110a  mov     [rsp+1D0h+phkResult], rax; lpData
0x18001110f  xor     r9d, r9d; lpType
0x180011112  xor     r8d, r8d; lpReserved
0x180011115  lea     rdx, ValueName; "Default Impersonation Level"
0x18001111c  mov     rcx, [rsp+1D0h+hKey]; hKey
0x180011121  call    cs:__imp_RegQueryValueExW
0x180011127  test    eax, eax
0x180011129  jnz     short loc_180011135
0x18001112b  mov     eax, dword ptr [rsp+1D0h+Data]
0x18001112f  mov     cs:?s_dwDefaultImpersonationLevel@CSWbemSecurity@@0W4WbemImpersonationLevelEnum@@A, eax; WbemImpersonationLevelEnum CSWbemSecurity::s_dwDefaultImpersonationLevel
0x180011135  mov     rcx, [rsp+1D0h+hKey]; hKey
0x18001113a  call    cs:__imp_RegCloseKey
0x180011140  jmp     loc_18001103C
0x180011145  mov     [rax], r12w
0x180011149  mov     edx, 104h; uSize
0x18001114e  mov     rcx, r14; lpBuffer
0x180011151  call    cs:__imp_GetSystemDirectoryW
0x180011157  mov     esi, eax
0x180011159  cmp     eax, 104h
0x18001115e  ja      loc_18001125E
0x180011164  lea     eax, [rdi-1]
0x180011167  mov     r9d, 7FFFFFFEh
0x18001116d  cmp     eax, r9d
0x180011170  ja      short loc_1800111E0
0x180011172  mov     r8d, edi
0x180011175  mov     ecx, edi
0x180011177  mov     rax, r14
0x18001117a  mov     r10d, edi
0x18001117d  nop     dword ptr [rax]
0x180011180  cmp     word ptr [rax], 0
0x180011184  jz      short loc_180011195
0x180011186  add     rax, 2
0x18001118a  sub     rcx, 1
0x18001118e  jnz     short loc_180011180
0x180011190  mov     r10, r12
0x180011193  jmp     short loc_180011198
0x180011195  sub     r10, rcx
0x180011198  test    rcx, rcx
0x18001119b  jz      short loc_1800111E0
0x18001119d  lea     rdx, [rsp+1D0h+var_188]
0x1800111a2  sub     r8, r10
0x1800111a5  lea     rax, [r14+r10*2]
0x1800111a9  jz      short loc_1800111D1
0x1800111ab  nop     dword ptr [rax+rax+00h]
0x1800111b0  test    r9, r9
0x1800111b3  jz      short loc_1800111D1
0x1800111b5  movzx   ecx, word ptr [rdx]
0x1800111b8  test    cx, cx
0x1800111bb  jz      short loc_1800111D1
0x1800111bd  add     rdx, 2
0x1800111c1  mov     [rax], cx
0x1800111c4  add     rax, 2
0x1800111c8  dec     r9
0x1800111cb  sub     r8, 1
0x1800111cf  jnz     short loc_1800111B0
0x1800111d1  lea     rcx, [rax-2]
0x1800111d5  test    r8, r8
0x1800111d8  cmovnz  rcx, rax
0x1800111dc  mov     [rcx], r12w
0x1800111e0  xor     r8d, r8d; dwFlags
0x1800111e3  xor     edx, edx; hFile
0x1800111e5  mov     rcx, r14; lpLibFileName
0x1800111e8  call    cs:__imp_LoadLibraryExW
0x1800111ee  mov     cs:?s_hAdvapi@CSWbemSecurity@@0PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * CSWbemSecurity::s_hAdvapi
0x1800111f5  test    rax, rax
0x1800111f8  jz      short loc_180011211
0x1800111fa  lea     rdx, ProcName; "DuplicateTokenEx"
0x180011201  mov     rcx, rax; hModule
0x180011204  call    cs:__imp_GetProcAddress
0x18001120a  mov     cs:?s_pfnDuplicateTokenEx@@3P6AHPEAXKPEAU_SECURITY_ATTRIBUTES@@W4_SECURITY_IMPERSONATION_LEVEL@@W4_TOKEN_TYPE@@PEAPEAX@ZEA, rax; int (*s_pfnDuplicateTokenEx)(void *,ulong,_SECURITY_ATTRIBUTES *,_SECURITY_IMPERSONATION_LEVEL,_TOKEN_TYPE,void * *)
0x180011211  mov     rcx, r14
0x180011214  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x18001121a  nop
0x18001121b  jmp     loc_1800110A3
0x180011220  mov     dword ptr [rsp+1D0h+var_190], r12d
0x180011225  mov     [rsp+1D0h+cbData], 4
0x18001122d  lea     rax, [rsp+1D0h+cbData]
0x180011232  mov     [rsp+1D0h+lpcbData], rax; lpcbData
0x180011237  lea     rax, [rsp+1D0h+var_190]
0x18001123c  mov     [rsp+1D0h+phkResult], rax; lpData
0x180011241  xor     r9d, r9d; lpType
0x180011244  xor     r8d, r8d; lpReserved
0x180011247  lea     rdx, aEnableForAsp; "Enable for ASP"
0x18001124e  mov     rcx, [rsp+1D0h+hKey]; hKey
0x180011253  call    cs:__imp_RegQueryValueExW
0x180011259  jmp     loc_1800110EE
0x18001125e  mov     rcx, r14
0x180011261  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x180011267  nop
0x180011268  lea     edi, [rsi+1]
0x18001126b  add     edi, ebx
0x18001126d  mov     ecx, edi
0x18001126f  mov     eax, 2
0x180011274  mul     rcx
0x180011277  cmovb   rax, r15
0x18001127b  mov     rcx, rax
0x18001127e  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x180011284  mov     r14, rax
0x180011287  test    rax, rax
0x18001128a  jz      loc_1800110A3
0x180011290  mov     [rax], r12w
0x180011294  mov     edx, esi; uSize
0x180011296  mov     rcx, rax; lpBuffer
0x180011299  call    cs:__imp_GetSystemDirectoryW
0x18001129f  jmp     loc_180011164
```
