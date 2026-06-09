# InitSharedBins

- ea: `0x10044a2c0`
- end: `0x10044aa12`
- name: `InitSharedBins`
- size: `1874`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x100419a20`
- `0x100419c70`

## callees

- `0x100401580`
- `0x100401800`
- `0x100402080`
- `0x1004021d0`
- `0x100402f10`
- `0x100449f50`
- `0x100449fd0`
- `0x10044a2c0`

## import_xrefs

- `KERNEL32!HeapFree` at `0x10044a4eb`
- `KERNEL32!HeapFree` at `0x10044a625`
- `KERNEL32!HeapFree` at `0x10044a74c`
- `KERNEL32!HeapFree` at `0x10044a9ae`
- `KERNEL32!HeapFree` at `0x10044a9d5`
- `KERNEL32!HeapFree` at `0x100456b43`
- `KERNEL32!HeapFree` at `0x100456b67`
- `KERNEL32!HeapFree` at `0x10044a4eb`
- `KERNEL32!HeapFree` at `0x10044a625`
- `KERNEL32!HeapFree` at `0x10044a74c`
- `KERNEL32!HeapFree` at `0x10044a9ae`
- `KERNEL32!HeapFree` at `0x10044a9d5`
- `KERNEL32!HeapFree` at `0x100456b43`
- `KERNEL32!HeapFree` at `0x100456b67`
- `KERNEL32!GetProcessHeap` at `0x10044a4a4`
- `KERNEL32!GetProcessHeap` at `0x10044a4db`
- `KERNEL32!GetProcessHeap` at `0x10044a51a`
- `KERNEL32!GetProcessHeap` at `0x10044a615`
- `KERNEL32!GetProcessHeap` at `0x10044a705`
- `KERNEL32!GetProcessHeap` at `0x10044a73c`
- `KERNEL32!GetProcessHeap` at `0x10044a77b`
- `KERNEL32!GetProcessHeap` at `0x10044a908`
- `KERNEL32!GetProcessHeap` at `0x10044a99e`
- `KERNEL32!GetProcessHeap` at `0x10044a9c5`
- `KERNEL32!GetProcessHeap` at `0x100456b34`
- `KERNEL32!GetProcessHeap` at `0x100456b58`
- `KERNEL32!GetProcessHeap` at `0x10044a4a4`
- `KERNEL32!GetProcessHeap` at `0x10044a4db`
- `KERNEL32!GetProcessHeap` at `0x10044a51a`
- `KERNEL32!GetProcessHeap` at `0x10044a615`
- `KERNEL32!GetProcessHeap` at `0x10044a705`
- `KERNEL32!GetProcessHeap` at `0x10044a73c`
- `KERNEL32!GetProcessHeap` at `0x10044a77b`
- `KERNEL32!GetProcessHeap` at `0x10044a908`
- `KERNEL32!GetProcessHeap` at `0x10044a99e`
- `KERNEL32!GetProcessHeap` at `0x10044a9c5`
- `KERNEL32!GetProcessHeap` at `0x100456b34`
- `KERNEL32!GetProcessHeap` at `0x100456b58`
- `KERNEL32!GetProcAddress` at `0x10044a3df`
- `KERNEL32!GetProcAddress` at `0x10044a404`
- `KERNEL32!GetProcAddress` at `0x10044a3df`
- `KERNEL32!GetProcAddress` at `0x10044a404`
- `KERNEL32!SetEnvironmentVariableW` at `0x10044a67d`
- `KERNEL32!SetEnvironmentVariableW` at `0x10044a98c`
- `KERNEL32!SetEnvironmentVariableW` at `0x10044a67d`
- `KERNEL32!SetEnvironmentVariableW` at `0x10044a98c`
- `KERNEL32!GetModuleHandleW` at `0x10044a3cf`
- `KERNEL32!GetModuleHandleW` at `0x10044a3f4`
- `KERNEL32!GetModuleHandleW` at `0x10044a3cf`
- `KERNEL32!GetModuleHandleW` at `0x10044a3f4`
- `KERNEL32!HeapAlloc` at `0x10044a533`
- `KERNEL32!HeapAlloc` at `0x10044a794`
- `KERNEL32!HeapAlloc` at `0x10044a921`
- `KERNEL32!HeapAlloc` at `0x10044a533`
- `KERNEL32!HeapAlloc` at `0x10044a794`
- `KERNEL32!HeapAlloc` at `0x10044a921`
- `KERNEL32!GetEnvironmentVariableW` at `0x10044a655`
- `KERNEL32!GetEnvironmentVariableW` at `0x10044a7b8`
- `KERNEL32!GetEnvironmentVariableW` at `0x10044a655`
- `KERNEL32!GetEnvironmentVariableW` at `0x10044a7b8`
- `KERNEL32!HeapReAlloc` at `0x10044a4c2`
- `KERNEL32!HeapReAlloc` at `0x10044a723`
- `KERNEL32!HeapReAlloc` at `0x10044a4c2`
- `KERNEL32!HeapReAlloc` at `0x10044a723`
- `KERNEL32!lstrlenW` at `0x10044a46b`
- `KERNEL32!lstrlenW` at `0x10044a6b0`
- `KERNEL32!lstrlenW` at `0x10044a6cc`
- `KERNEL32!lstrlenW` at `0x10044a46b`
- `KERNEL32!lstrlenW` at `0x10044a6b0`
- `KERNEL32!lstrlenW` at `0x10044a6cc`
- `KERNEL32!CompareStringW` at `0x10044a602`
- `KERNEL32!CompareStringW` at `0x10044a602`

## string_xrefs

- `0x10044a3c8`: `kernel32.dll`
- `0x10044a3ed`: `kernel32.dll`
- `0x10044a3fa`: `GetDllDirectoryW`
- `0x10044a3d5`: `SetDllDirectoryW`

## pseudocode

```c
__int64 InitSharedBins()
{
  HMODULE ModuleHandleW; // rax
  HMODULE v1; // rax
  HANDLE ProcessHeap; // rax
  HANDLE v3; // rax
  HANDLE v4; // rax
  HANDLE v5; // rax
  HANDLE v6; // rax
  HANDLE v7; // rax
  HANDLE v8; // rax
  HANDLE v9; // rax
  HANDLE v10; // rax
  HANDLE v11; // rax
  DWORD nSize; // [rsp+30h] [rbp-2E8h]
  unsigned int nSizea; // [rsp+30h] [rbp-2E8h]
  _WORD *lpMem; // [rsp+38h] [rbp-2E0h]
  int v16; // [rsp+40h] [rbp-2D8h]
  DWORD EnvironmentVariableW; // [rsp+40h] [rbp-2D8h]
  unsigned __int16 v18; // [rsp+44h] [rbp-2D4h]
  unsigned int v19; // [rsp+48h] [rbp-2D0h]
  int i; // [rsp+4Ch] [rbp-2CCh]
  wchar_t *pszDest; // [rsp+50h] [rbp-2C8h]
  int v22; // [rsp+58h] [rbp-2C0h]
  unsigned int v23; // [rsp+5Ch] [rbp-2BCh]
  int v24; // [rsp+60h] [rbp-2B8h]
  unsigned int v25; // [rsp+6Ch] [rbp-2ACh]
  HKEY v26; // [rsp+70h] [rbp-2A8h] BYREF
  DWORD v27; // [rsp+78h] [rbp-2A0h] BYREF
  BOOL v28; // [rsp+7Ch] [rbp-29Ch]
  _WORD *v29; // [rsp+80h] [rbp-298h]
  FARPROC v30; // [rsp+88h] [rbp-290h]
  LCID Locale; // [rsp+90h] [rbp-288h]
  _WORD *v32; // [rsp+98h] [rbp-280h]
  FARPROC ProcAddress; // [rsp+A0h] [rbp-278h]
  _WORD *v34; // [rsp+A8h] [rbp-270h]
  FARPROC v35; // [rsp+B0h] [rbp-268h]
  SIZE_T dwBytes; // [rsp+B8h] [rbp-260h]
  SIZE_T v37; // [rsp+C0h] [rbp-258h]
  FARPROC v38; // [rsp+C8h] [rbp-250h]
  FARPROC v39; // [rsp+D0h] [rbp-248h]
  SIZE_T v40; // [rsp+D8h] [rbp-240h]
  SIZE_T v41; // [rsp+E0h] [rbp-238h]
  SIZE_T v42; // [rsp+E8h] [rbp-230h]
  wchar_t String[264]; // [rsp+F0h] [rbp-228h] BYREF

  v26 = 0;
  v27 = 520;
  lpMem = 0;
  pszDest = 0;
  ProcAddress = 0;
  v30 = 0;
  v19 = 0;
  v22 = 0;
  Locale = 1033;
  if ( !(unsigned int)IniRegOpenKeyExW(
                        -2147483646,
                        (int)L"Software\\Microsoft\\Microsoft SQL Server\\160",
                        0,
                        131097,
                        &v26)
    && !(unsigned int)IniRegQueryValueExW((int)v26, (int)L"SharedCode", 0, 0, (LPBYTE)String, &v27) )
  {
    ModuleHandleW = GetModuleHandleW(L"kernel32.dll");
    ProcAddress = GetProcAddress(ModuleHandleW, "SetDllDirectoryW");
    v1 = GetModuleHandleW(L"kernel32.dll");
    v30 = GetProcAddress(v1, "GetDllDirectoryW");
    if ( ProcAddress && v30 )
    {
      do
      {
        v35 = v30;
        v16 = ((__int64 (__fastcall *)(_QWORD, _QWORD))v30)(0, 0);
        nSize = v16 + lstrlenW(String) + 2;
        if ( lpMem )
        {
          v32 = 0;
          dwBytes = 2LL * nSize;
          ProcessHeap = GetProcessHeap();
          v32 = HeapReAlloc(ProcessHeap, 8u, lpMem, dwBytes);
          if ( v32 )
          {
            lpMem = v32;
          }
          else
          {
            v3 = GetProcessHeap();
            HeapFree(v3, 0, lpMem);
            lpMem = 0;
          }
        }
        else
        {
          v37 = 2LL * nSize;
          v4 = GetProcessHeap();
          lpMem = HeapAlloc(v4, 8u, v37);
        }
        if ( !lpMem )
          break;
        v38 = v30;
      }
      while ( ((unsigned int (__fastcall *)(_QWORD, _WORD *))v30)(nSize, lpMem) >= nSize );
      if ( lpMem && *lpMem )
      {
        if ( CompareStringW(Locale, 1u, lpMem, -1, String, -1) == 2 )
        {
          v19 = 1;
        }
        else
        {
          v22 = 1;
          v5 = GetProcessHeap();
          HeapFree(v5, 0, lpMem);
          lpMem = 0;
        }
      }
      else
      {
        v39 = ProcAddress;
        v19 = ((__int64 (__fastcall *)(wchar_t *))ProcAddress)(String);
        if ( !v19 )
          v22 = 1;
      }
    }
    else
    {
      v22 = 1;
    }
    if ( v22 )
    {
      EnvironmentVariableW = GetEnvironmentVariableW(L"Path", 0, 0);
      if ( EnvironmentVariableW )
      {
        v24 = 0;
        v29 = 0;
        v25 = lstrlenW(String) + 1;
        do
        {
          nSizea = EnvironmentVariableW + lstrlenW(String) + 2;
          if ( lpMem )
          {
            v34 = 0;
            v40 = 2LL * nSizea;
            v6 = GetProcessHeap();
            v34 = HeapReAlloc(v6, 8u, lpMem, v40);
            if ( v34 )
            {
              lpMem = v34;
            }
            else
            {
              v7 = GetProcessHeap();
              HeapFree(v7, 0, lpMem);
              lpMem = 0;
            }
          }
          else
          {
            v41 = 2LL * nSizea;
            v8 = GetProcessHeap();
            lpMem = HeapAlloc(v8, 8u, v41);
          }
          if ( !lpMem )
            break;
          EnvironmentVariableW = GetEnvironmentVariableW(L"Path", lpMem, nSizea);
        }
        while ( EnvironmentVariableW >= nSizea );
        v29 = lpMem;
        v23 = EnvironmentVariableW + 1;
        if ( lpMem )
        {
          while ( !v24 && v23 >= v25 )
          {
            for ( i = 0; ; ++i )
            {
              v18 = v29[i];
              v28 = v18 == String[i];
              if ( !v28 || i == v25 - 1 )
                break;
            }
            if ( v28 )
            {
              v24 = 1;
            }
            else if ( i == v25 - 1 && v18 == 59 )
            {
              v24 = 1;
            }
            ++v29;
            --v23;
          }
        }
        if ( v24 )
        {
          v19 = 1;
        }
        else
        {
          v42 = 2LL * nSizea;
          v9 = GetProcessHeap();
          pszDest = (wchar_t *)HeapAlloc(v9, 8u, v42);
          if ( lpMem && pszDest )
          {
            StringCchCopyW(pszDest, nSizea, String);
            StringCchCatW(pszDest, nSizea, L";");
            StringCchCatW(pszDest, nSizea, lpMem);
            v19 = SetEnvironmentVariableW(L"Path", pszDest);
          }
        }
      }
      else
      {
        v19 = SetEnvironmentVariableW(L"Path", String);
      }
    }
  }
  if ( lpMem )
  {
    v10 = GetProcessHeap();
    HeapFree(v10, 0, lpMem);
  }
  if ( pszDest )
  {
    v11 = GetProcessHeap();
    HeapFree(v11, 0, pszDest);
  }
  if ( v26 )
    IniRegCloseKey(v26);
  return v19;
}

```

## disassembly

```asm
0x10044a2c0  sub     rsp, 318h
0x10044a2c7  mov     rax, cs:__security_cookie
0x10044a2ce  xor     rax, rsp
0x10044a2d1  mov     [rsp+318h+var_18], rax
0x10044a2d9  mov     [rsp+318h+var_2A8], 0
0x10044a2e2  mov     [rsp+318h+nSize], 104h
0x10044a2ea  mov     [rsp+318h+var_2D8], 0
0x10044a2f2  mov     eax, [rsp+318h+nSize]
0x10044a2f6  shl     rax, 1
0x10044a2f9  mov     [rsp+318h+var_2A0], eax
0x10044a2fd  mov     [rsp+318h+lpMem], 0
0x10044a306  mov     [rsp+318h+pszDest], 0
0x10044a30f  mov     [rsp+318h+var_278], 0
0x10044a31b  mov     [rsp+318h+var_290], 0
0x10044a327  mov     [rsp+318h+var_2D0], 0
0x10044a32f  mov     [rsp+318h+var_2C0], 0
0x10044a337  mov     [rsp+318h+Locale], 409h
0x10044a342  lea     rax, [rsp+318h+var_2A8]
0x10044a347  mov     [rsp+318h+lpString2], rax; PHKEY
0x10044a34c  mov     r9d, 20019h; int
0x10044a352  xor     r8d, r8d; int
0x10044a355  lea     rdx, aSoftwareMicros_3; "Software\\Microsoft\\Microsoft SQL Serv"...
0x10044a35c  mov     rcx, 0FFFFFFFF80000002h; int
0x10044a363  call    IniRegOpenKeyExW
0x10044a368  mov     [rsp+318h+var_2B4], eax
0x10044a36c  cmp     [rsp+318h+var_2B4], 0
0x10044a371  jz      short loc_10044A378
0x10044a373  jmp     loc_10044A996
0x10044a378  lea     rax, [rsp+318h+var_2A0]
0x10044a37d  mov     qword ptr [rsp+318h+cchCount2], rax; LPDWORD
0x10044a382  lea     rax, [rsp+318h+String]
0x10044a38a  mov     [rsp+318h+lpString2], rax; LPBYTE
0x10044a38f  xor     r9d, r9d; int
0x10044a392  xor     r8d, r8d; int
0x10044a395  lea     rdx, aSharedcode; "SharedCode"
0x10044a39c  mov     rcx, [rsp+318h+var_2A8]; int
0x10044a3a1  call    IniRegQueryValueExW
0x10044a3a6  mov     [rsp+318h+var_2B4], eax
0x10044a3aa  cmp     [rsp+318h+var_2B4], 0
0x10044a3af  jz      short loc_10044A3B6
0x10044a3b1  jmp     loc_10044A996
0x10044a3b6  mov     eax, [rsp+318h+var_2A0]
0x10044a3ba  xor     edx, edx
0x10044a3bc  mov     ecx, 2
0x10044a3c1  div     rcx
0x10044a3c4  mov     [rsp+318h+nSize], eax
0x10044a3c8  lea     rcx, aKernel32Dll_0; "kernel32.dll"
0x10044a3cf  call    cs:__imp_GetModuleHandleW
0x10044a3d5  lea     rdx, aSetdlldirector; "SetDllDirectoryW"
0x10044a3dc  mov     rcx, rax; hModule
0x10044a3df  call    cs:__imp_GetProcAddress
0x10044a3e5  mov     [rsp+318h+var_278], rax
0x10044a3ed  lea     rcx, aKernel32Dll_0; "kernel32.dll"
0x10044a3f4  call    cs:__imp_GetModuleHandleW
0x10044a3fa  lea     rdx, aGetdlldirector; "GetDllDirectoryW"
0x10044a401  mov     rcx, rax; hModule
0x10044a404  call    cs:__imp_GetProcAddress
0x10044a40a  mov     [rsp+318h+var_290], rax
0x10044a412  cmp     [rsp+318h+var_278], 0
0x10044a41b  jz      short loc_10044A428
0x10044a41d  cmp     [rsp+318h+var_290], 0
0x10044a426  jnz     short loc_10044A435
0x10044a428  mov     [rsp+318h+var_2C0], 1
0x10044a430  jmp     loc_10044A63E
0x10044a435  mov     rax, [rsp+318h+var_290]
0x10044a43d  mov     [rsp+318h+var_268], rax
0x10044a445  xor     edx, edx
0x10044a447  xor     ecx, ecx
0x10044a449  mov     rax, [rsp+318h+var_268]
0x10044a451  call    cs:__guard_dispatch_icall_fptr
0x10044a457  mov     [rsp+318h+var_2D8], eax
0x10044a45b  mov     eax, [rsp+318h+var_2D8]
0x10044a45f  mov     [rsp+318h+nSize], eax
0x10044a463  lea     rcx, [rsp+318h+String]; lpString
0x10044a46b  call    cs:__imp_lstrlenW
0x10044a471  mov     ecx, [rsp+318h+nSize]
0x10044a475  lea     eax, [rcx+rax+2]
0x10044a479  mov     [rsp+318h+nSize], eax
0x10044a47d  cmp     [rsp+318h+lpMem], 0
0x10044a483  jz      loc_10044A50B
0x10044a489  mov     [rsp+318h+var_280], 0
0x10044a495  mov     eax, [rsp+318h+nSize]
0x10044a499  shl     rax, 1
0x10044a49c  mov     [rsp+318h+dwBytes], rax
0x10044a4a4  call    cs:__imp_GetProcessHeap
0x10044a4aa  mov     rcx, [rsp+318h+dwBytes]
0x10044a4b2  mov     r9, rcx; dwBytes
0x10044a4b5  mov     r8, [rsp+318h+lpMem]; lpMem
0x10044a4ba  mov     edx, 8; dwFlags
0x10044a4bf  mov     rcx, rax; hHeap
0x10044a4c2  call    cs:__imp_HeapReAlloc
0x10044a4c8  mov     [rsp+318h+var_280], rax
0x10044a4d0  cmp     [rsp+318h+var_280], 0
0x10044a4d9  jnz     short loc_10044A4FC
0x10044a4db  call    cs:__imp_GetProcessHeap
0x10044a4e1  mov     r8, [rsp+318h+lpMem]; lpMem
0x10044a4e6  xor     edx, edx; dwFlags
0x10044a4e8  mov     rcx, rax; hHeap
0x10044a4eb  call    cs:__imp_HeapFree
0x10044a4f1  mov     [rsp+318h+lpMem], 0
0x10044a4fa  jmp     short loc_10044A509
0x10044a4fc  mov     rax, [rsp+318h+var_280]
0x10044a504  mov     [rsp+318h+lpMem], rax
0x10044a509  jmp     short loc_10044A53E
0x10044a50b  mov     eax, [rsp+318h+nSize]
0x10044a50f  shl     rax, 1
0x10044a512  mov     [rsp+318h+var_258], rax
0x10044a51a  call    cs:__imp_GetProcessHeap
0x10044a520  mov     rcx, [rsp+318h+var_258]
0x10044a528  mov     r8, rcx; dwBytes
0x10044a52b  mov     edx, 8; dwFlags
0x10044a530  mov     rcx, rax; hHeap
0x10044a533  call    cs:__imp_HeapAlloc
0x10044a539  mov     [rsp+318h+lpMem], rax
0x10044a53e  cmp     [rsp+318h+lpMem], 0
0x10044a544  jz      short loc_10044A571
0x10044a546  mov     rax, [rsp+318h+var_290]
0x10044a54e  mov     [rsp+318h+var_250], rax
0x10044a556  mov     rdx, [rsp+318h+lpMem]
0x10044a55b  mov     ecx, [rsp+318h+nSize]
0x10044a55f  mov     rax, [rsp+318h+var_250]
0x10044a567  call    cs:__guard_dispatch_icall_fptr
0x10044a56d  mov     [rsp+318h+var_2D8], eax
0x10044a571  cmp     [rsp+318h+lpMem], 0
0x10044a577  jz      short loc_10044A587
0x10044a579  mov     eax, [rsp+318h+nSize]
0x10044a57d  cmp     [rsp+318h+var_2D8], eax
0x10044a581  jnb     loc_10044A435
0x10044a587  cmp     [rsp+318h+lpMem], 0
0x10044a58d  jz      short loc_10044A59B
0x10044a58f  mov     rax, [rsp+318h+lpMem]
0x10044a594  movzx   eax, word ptr [rax]
0x10044a597  test    eax, eax
0x10044a599  jnz     short loc_10044A5D6
0x10044a59b  mov     rax, [rsp+318h+var_278]
0x10044a5a3  mov     [rsp+318h+var_248], rax
0x10044a5ab  lea     rcx, [rsp+318h+String]
0x10044a5b3  mov     rax, [rsp+318h+var_248]
0x10044a5bb  call    cs:__guard_dispatch_icall_fptr
0x10044a5c1  mov     [rsp+318h+var_2D0], eax
0x10044a5c5  cmp     [rsp+318h+var_2D0], 0
0x10044a5ca  jnz     short loc_10044A5D4
0x10044a5cc  mov     [rsp+318h+var_2C0], 1
0x10044a5d4  jmp     short loc_10044A63E
0x10044a5d6  mov     [rsp+318h+cchCount2], 0FFFFFFFFh; cchCount2
0x10044a5de  lea     rax, [rsp+318h+String]
0x10044a5e6  mov     [rsp+318h+lpString2], rax; lpString2
0x10044a5eb  mov     r9d, 0FFFFFFFFh; cchCount1
0x10044a5f1  mov     r8, [rsp+318h+lpMem]; lpString1
0x10044a5f6  mov     edx, 1; dwCmpFlags
0x10044a5fb  mov     ecx, [rsp+318h+Locale]; Locale
0x10044a602  call    cs:__imp_CompareStringW
0x10044a608  cmp     eax, 2
0x10044a60b  jz      short loc_10044A636
0x10044a60d  mov     [rsp+318h+var_2C0], 1
0x10044a615  call    cs:__imp_GetProcessHeap
0x10044a61b  mov     r8, [rsp+318h+lpMem]; lpMem
0x10044a620  xor     edx, edx; dwFlags
0x10044a622  mov     rcx, rax; hHeap
0x10044a625  call    cs:__imp_HeapFree
0x10044a62b  mov     [rsp+318h+lpMem], 0
0x10044a634  jmp     short loc_10044A63E
0x10044a636  mov     [rsp+318h+var_2D0], 1
0x10044a63e  cmp     [rsp+318h+var_2C0], 0
0x10044a643  jz      loc_10044A996
0x10044a649  xor     r8d, r8d; nSize
0x10044a64c  xor     edx, edx; lpBuffer
0x10044a64e  lea     rcx, aPath; "Path"
0x10044a655  call    cs:__imp_GetEnvironmentVariableW
0x10044a65b  mov     [rsp+318h+var_2D8], eax
0x10044a65f  mov     eax, [rsp+318h+var_2D8]
0x10044a663  mov     [rsp+318h+nSize], eax
0x10044a667  cmp     [rsp+318h+nSize], 0
0x10044a66c  jnz     short loc_10044A68C
0x10044a66e  lea     rdx, [rsp+318h+String]; lpValue
0x10044a676  lea     rcx, aPath; "Path"
0x10044a67d  call    cs:__imp_SetEnvironmentVariableW
0x10044a683  mov     [rsp+318h+var_2D0], eax
0x10044a687  jmp     loc_10044A996
0x10044a68c  mov     [rsp+318h+var_2B8], 0
0x10044a694  mov     [rsp+318h+var_298], 0
0x10044a6a0  mov     [rsp+318h+var_2BC], 0
0x10044a6a8  lea     rcx, [rsp+318h+String]; lpString
0x10044a6b0  call    cs:__imp_lstrlenW
0x10044a6b6  inc     eax
0x10044a6b8  mov     [rsp+318h+var_2AC], eax
0x10044a6bc  mov     eax, [rsp+318h+var_2D8]
0x10044a6c0  mov     [rsp+318h+nSize], eax
0x10044a6c4  lea     rcx, [rsp+318h+String]; lpString
0x10044a6cc  call    cs:__imp_lstrlenW
0x10044a6d2  mov     ecx, [rsp+318h+nSize]
0x10044a6d6  lea     eax, [rcx+rax+2]
0x10044a6da  mov     [rsp+318h+nSize], eax
0x10044a6de  cmp     [rsp+318h+lpMem], 0
0x10044a6e4  jz      loc_10044A76C
0x10044a6ea  mov     [rsp+318h+var_270], 0
0x10044a6f6  mov     eax, [rsp+318h+nSize]
0x10044a6fa  shl     rax, 1
0x10044a6fd  mov     [rsp+318h+var_240], rax
0x10044a705  call    cs:__imp_GetProcessHeap
0x10044a70b  mov     rcx, [rsp+318h+var_240]
0x10044a713  mov     r9, rcx; dwBytes
0x10044a716  mov     r8, [rsp+318h+lpMem]; lpMem
0x10044a71b  mov     edx, 8; dwFlags
0x10044a720  mov     rcx, rax; hHeap
0x10044a723  call    cs:__imp_HeapReAlloc
0x10044a729  mov     [rsp+318h+var_270], rax
0x10044a731  cmp     [rsp+318h+var_270], 0
0x10044a73a  jnz     short loc_10044A75D
0x10044a73c  call    cs:__imp_GetProcessHeap
0x10044a742  mov     r8, [rsp+318h+lpMem]; lpMem
0x10044a747  xor     edx, edx; dwFlags
0x10044a749  mov     rcx, rax; hHeap
0x10044a74c  call    cs:__imp_HeapFree
0x10044a752  mov     [rsp+318h+lpMem], 0
0x10044a75b  jmp     short loc_10044A76A
0x10044a75d  mov     rax, [rsp+318h+var_270]
0x10044a765  mov     [rsp+318h+lpMem], rax
0x10044a76a  jmp     short loc_10044A79F
0x10044a76c  mov     eax, [rsp+318h+nSize]
0x10044a770  shl     rax, 1
0x10044a773  mov     [rsp+318h+var_238], rax
0x10044a77b  call    cs:__imp_GetProcessHeap
0x10044a781  mov     rcx, [rsp+318h+var_238]
0x10044a789  mov     r8, rcx; dwBytes
0x10044a78c  mov     edx, 8; dwFlags
0x10044a791  mov     rcx, rax; hHeap
0x10044a794  call    cs:__imp_HeapAlloc
0x10044a79a  mov     [rsp+318h+lpMem], rax
0x10044a79f  cmp     [rsp+318h+lpMem], 0
0x10044a7a5  jz      short loc_10044A7C2
0x10044a7a7  mov     r8d, [rsp+318h+nSize]; nSize
0x10044a7ac  mov     rdx, [rsp+318h+lpMem]; lpBuffer
0x10044a7b1  lea     rcx, aPath; "Path"
0x10044a7b8  call    cs:__imp_GetEnvironmentVariableW
0x10044a7be  mov     [rsp+318h+var_2D8], eax
0x10044a7c2  cmp     [rsp+318h+lpMem], 0
0x10044a7c8  jz      short loc_10044A7D8
0x10044a7ca  mov     eax, [rsp+318h+nSize]
0x10044a7ce  cmp     [rsp+318h+var_2D8], eax
0x10044a7d2  jnb     loc_10044A6BC
0x10044a7d8  mov     rax, [rsp+318h+lpMem]
0x10044a7dd  mov     [rsp+318h+var_298], rax
0x10044a7e5  mov     eax, [rsp+318h+var_2D8]
0x10044a7e9  inc     eax
0x10044a7eb  mov     [rsp+318h+var_2BC], eax
0x10044a7ef  cmp     [rsp+318h+var_298], 0
0x10044a7f8  jz      loc_10044A8E5
0x10044a7fe  cmp     [rsp+318h+var_2B8], 0
0x10044a803  jnz     loc_10044A8E5
0x10044a809  mov     eax, [rsp+318h+var_2AC]
0x10044a80d  cmp     [rsp+318h+var_2BC], eax
0x10044a811  jb      loc_10044A8E5
0x10044a817  mov     [rsp+318h+var_2CC], 0
0x10044a81f  mov     [rsp+318h+var_2B0], 0
0x10044a827  xor     eax, eax
0x10044a829  mov     [rsp+318h+var_2D4], ax
0x10044a82e  mov     eax, [rsp+318h+var_2CC]
0x10044a832  mov     rcx, [rsp+318h+var_298]
0x10044a83a  movzx   eax, word ptr [rcx+rax*2]
0x10044a83e  mov     [rsp+318h+var_2D4], ax
0x10044a843  movzx   eax, [rsp+318h+var_2D4]
0x10044a848  mov     ecx, [rsp+318h+var_2CC]
0x10044a84c  movzx   ecx, [rsp+rcx*2+318h+String]
0x10044a854  cmp     eax, ecx
0x10044a856  jnz     short loc_10044A862
0x10044a858  mov     [rsp+318h+var_29C], 1
0x10044a860  jmp     short loc_10044A86A
0x10044a862  mov     [rsp+318h+var_29C], 0
0x10044a86a  mov     eax, [rsp+318h+var_29C]
0x10044a86e  mov     [rsp+318h+var_2B0], eax
0x10044a872  cmp     [rsp+318h+var_2B0], 0
0x10044a877  jz      short loc_10044A893
0x10044a879  mov     eax, [rsp+318h+var_2AC]
0x10044a87d  dec     eax
0x10044a87f  cmp     [rsp+318h+var_2CC], eax
0x10044a883  jnz     short loc_10044A887
0x10044a885  jmp     short loc_10044A893
0x10044a887  mov     eax, [rsp+318h+var_2CC]
0x10044a88b  inc     eax
0x10044a88d  mov     [rsp+318h+var_2CC], eax
0x10044a891  jmp     short loc_10044A82E
0x10044a893  cmp     [rsp+318h+var_2B0], 0
0x10044a898  jz      short loc_10044A8A4
0x10044a89a  mov     [rsp+318h+var_2B8], 1
0x10044a8a2  jmp     short loc_10044A8C2
0x10044a8a4  mov     eax, [rsp+318h+var_2AC]
0x10044a8a8  dec     eax
0x10044a8aa  cmp     [rsp+318h+var_2CC], eax
0x10044a8ae  jnz     short loc_10044A8C2
0x10044a8b0  movzx   eax, [rsp+318h+var_2D4]
0x10044a8b5  cmp     eax, 3Bh ; ';'
0x10044a8b8  jnz     short loc_10044A8C2
0x10044a8ba  mov     [rsp+318h+var_2B8], 1
0x10044a8c2  mov     rax, [rsp+318h+var_298]
0x10044a8ca  add     rax, 2
0x10044a8ce  mov     [rsp+318h+var_298], rax
0x10044a8d6  mov     eax, [rsp+318h+var_2BC]
0x10044a8da  dec     eax
0x10044a8dc  mov     [rsp+318h+var_2BC], eax
  ... truncated ...
```
