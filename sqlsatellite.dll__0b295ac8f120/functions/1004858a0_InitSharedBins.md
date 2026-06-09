# InitSharedBins

- ea: `0x1004858a0`
- end: `0x100485ff2`
- name: `InitSharedBins`
- size: `1874`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x100401570`

## callees

- `0x10045c290`
- `0x10045c7c0`
- `0x10045c840`
- `0x100485530`
- `0x1004855b0`
- `0x1004858a0`
- `0x100486af0`
- `0x100488260`

## import_xrefs

- `KERNEL32!lstrlenW` at `0x100485a4b`
- `KERNEL32!lstrlenW` at `0x100485c90`
- `KERNEL32!lstrlenW` at `0x100485cac`
- `KERNEL32!lstrlenW` at `0x100485a4b`
- `KERNEL32!lstrlenW` at `0x100485c90`
- `KERNEL32!lstrlenW` at `0x100485cac`
- `KERNEL32!HeapReAlloc` at `0x100485aa2`
- `KERNEL32!HeapReAlloc` at `0x100485d03`
- `KERNEL32!HeapReAlloc` at `0x100485aa2`
- `KERNEL32!HeapReAlloc` at `0x100485d03`
- `KERNEL32!CompareStringW` at `0x100485be2`
- `KERNEL32!CompareStringW` at `0x100485be2`
- `KERNEL32!SetEnvironmentVariableW` at `0x100485c5d`
- `KERNEL32!SetEnvironmentVariableW` at `0x100485f6c`
- `KERNEL32!SetEnvironmentVariableW` at `0x100485c5d`
- `KERNEL32!SetEnvironmentVariableW` at `0x100485f6c`
- `KERNEL32!GetProcAddress` at `0x1004859bf`
- `KERNEL32!GetProcAddress` at `0x1004859e4`
- `KERNEL32!GetProcAddress` at `0x1004859bf`
- `KERNEL32!GetProcAddress` at `0x1004859e4`
- `KERNEL32!GetEnvironmentVariableW` at `0x100485c35`
- `KERNEL32!GetEnvironmentVariableW` at `0x100485d98`
- `KERNEL32!GetEnvironmentVariableW` at `0x100485c35`
- `KERNEL32!GetEnvironmentVariableW` at `0x100485d98`
- `KERNEL32!GetModuleHandleW` at `0x1004859af`
- `KERNEL32!GetModuleHandleW` at `0x1004859d4`
- `KERNEL32!GetModuleHandleW` at `0x1004859af`
- `KERNEL32!GetModuleHandleW` at `0x1004859d4`
- `KERNEL32!HeapFree` at `0x100485acb`
- `KERNEL32!HeapFree` at `0x100485c05`
- `KERNEL32!HeapFree` at `0x100485d2c`
- `KERNEL32!HeapFree` at `0x100485f8e`
- `KERNEL32!HeapFree` at `0x100485fb5`
- `KERNEL32!HeapFree` at `0x10048e220`
- `KERNEL32!HeapFree` at `0x10048e246`
- `KERNEL32!HeapFree` at `0x100485acb`
- `KERNEL32!HeapFree` at `0x100485c05`
- `KERNEL32!HeapFree` at `0x100485d2c`
- `KERNEL32!HeapFree` at `0x100485f8e`
- `KERNEL32!HeapFree` at `0x100485fb5`
- `KERNEL32!HeapFree` at `0x10048e220`
- `KERNEL32!HeapFree` at `0x10048e246`
- `KERNEL32!GetProcessHeap` at `0x100485a84`
- `KERNEL32!GetProcessHeap` at `0x100485abb`
- `KERNEL32!GetProcessHeap` at `0x100485afa`
- `KERNEL32!GetProcessHeap` at `0x100485bf5`
- `KERNEL32!GetProcessHeap` at `0x100485ce5`
- `KERNEL32!GetProcessHeap` at `0x100485d1c`
- `KERNEL32!GetProcessHeap` at `0x100485d5b`
- `KERNEL32!GetProcessHeap` at `0x100485ee8`
- `KERNEL32!GetProcessHeap` at `0x100485f7e`
- `KERNEL32!GetProcessHeap` at `0x100485fa5`
- `KERNEL32!GetProcessHeap` at `0x10048e210`
- `KERNEL32!GetProcessHeap` at `0x10048e236`
- `KERNEL32!GetProcessHeap` at `0x100485a84`
- `KERNEL32!GetProcessHeap` at `0x100485abb`
- `KERNEL32!GetProcessHeap` at `0x100485afa`
- `KERNEL32!GetProcessHeap` at `0x100485bf5`
- `KERNEL32!GetProcessHeap` at `0x100485ce5`
- `KERNEL32!GetProcessHeap` at `0x100485d1c`
- `KERNEL32!GetProcessHeap` at `0x100485d5b`
- `KERNEL32!GetProcessHeap` at `0x100485ee8`
- `KERNEL32!GetProcessHeap` at `0x100485f7e`
- `KERNEL32!GetProcessHeap` at `0x100485fa5`
- `KERNEL32!GetProcessHeap` at `0x10048e210`
- `KERNEL32!GetProcessHeap` at `0x10048e236`
- `KERNEL32!HeapAlloc` at `0x100485b13`
- `KERNEL32!HeapAlloc` at `0x100485d74`
- `KERNEL32!HeapAlloc` at `0x100485f01`
- `KERNEL32!HeapAlloc` at `0x100485b13`
- `KERNEL32!HeapAlloc` at `0x100485d74`
- `KERNEL32!HeapAlloc` at `0x100485f01`

## string_xrefs

- `0x1004859a8`: `kernel32.dll`
- `0x1004859cd`: `kernel32.dll`
- `0x1004859da`: `GetDllDirectoryW`
- `0x1004859b5`: `SetDllDirectoryW`

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
0x1004858a0  sub     rsp, 318h
0x1004858a7  mov     rax, cs:__security_cookie
0x1004858ae  xor     rax, rsp
0x1004858b1  mov     [rsp+318h+var_18], rax
0x1004858b9  mov     [rsp+318h+var_2A8], 0
0x1004858c2  mov     [rsp+318h+nSize], 104h
0x1004858ca  mov     [rsp+318h+var_2D8], 0
0x1004858d2  mov     eax, [rsp+318h+nSize]
0x1004858d6  shl     rax, 1
0x1004858d9  mov     [rsp+318h+var_2A0], eax
0x1004858dd  mov     [rsp+318h+lpMem], 0
0x1004858e6  mov     [rsp+318h+pszDest], 0
0x1004858ef  mov     [rsp+318h+var_278], 0
0x1004858fb  mov     [rsp+318h+var_290], 0
0x100485907  mov     [rsp+318h+var_2D0], 0
0x10048590f  mov     [rsp+318h+var_2C0], 0
0x100485917  mov     [rsp+318h+Locale], 409h
0x100485922  lea     rax, [rsp+318h+var_2A8]
0x100485927  mov     [rsp+318h+lpString2], rax; PHKEY
0x10048592c  mov     r9d, 20019h; int
0x100485932  xor     r8d, r8d; int
0x100485935  lea     rdx, aSoftwareMicros; "Software\\Microsoft\\Microsoft SQL Serv"...
0x10048593c  mov     rcx, 0FFFFFFFF80000002h; int
0x100485943  call    IniRegOpenKeyExW
0x100485948  mov     [rsp+318h+var_2B4], eax
0x10048594c  cmp     [rsp+318h+var_2B4], 0
0x100485951  jz      short loc_100485958
0x100485953  jmp     loc_100485F76
0x100485958  lea     rax, [rsp+318h+var_2A0]
0x10048595d  mov     qword ptr [rsp+318h+cchCount2], rax; LPDWORD
0x100485962  lea     rax, [rsp+318h+String]
0x10048596a  mov     [rsp+318h+lpString2], rax; LPBYTE
0x10048596f  xor     r9d, r9d; int
0x100485972  xor     r8d, r8d; int
0x100485975  lea     rdx, ValueName; "SharedCode"
0x10048597c  mov     rcx, [rsp+318h+var_2A8]; int
0x100485981  call    IniRegQueryValueExW
0x100485986  mov     [rsp+318h+var_2B4], eax
0x10048598a  cmp     [rsp+318h+var_2B4], 0
0x10048598f  jz      short loc_100485996
0x100485991  jmp     loc_100485F76
0x100485996  mov     eax, [rsp+318h+var_2A0]
0x10048599a  xor     edx, edx
0x10048599c  mov     ecx, 2
0x1004859a1  div     rcx
0x1004859a4  mov     [rsp+318h+nSize], eax
0x1004859a8  lea     rcx, aKernel32Dll_1; "kernel32.dll"
0x1004859af  call    cs:__imp_GetModuleHandleW
0x1004859b5  lea     rdx, aSetdlldirector; "SetDllDirectoryW"
0x1004859bc  mov     rcx, rax; hModule
0x1004859bf  call    cs:__imp_GetProcAddress
0x1004859c5  mov     [rsp+318h+var_278], rax
0x1004859cd  lea     rcx, aKernel32Dll_1; "kernel32.dll"
0x1004859d4  call    cs:__imp_GetModuleHandleW
0x1004859da  lea     rdx, aGetdlldirector; "GetDllDirectoryW"
0x1004859e1  mov     rcx, rax; hModule
0x1004859e4  call    cs:__imp_GetProcAddress
0x1004859ea  mov     [rsp+318h+var_290], rax
0x1004859f2  cmp     [rsp+318h+var_278], 0
0x1004859fb  jz      short loc_100485A08
0x1004859fd  cmp     [rsp+318h+var_290], 0
0x100485a06  jnz     short loc_100485A15
0x100485a08  mov     [rsp+318h+var_2C0], 1
0x100485a10  jmp     loc_100485C1E
0x100485a15  mov     rax, [rsp+318h+var_290]
0x100485a1d  mov     [rsp+318h+var_268], rax
0x100485a25  xor     edx, edx
0x100485a27  xor     ecx, ecx
0x100485a29  mov     rax, [rsp+318h+var_268]
0x100485a31  call    cs:__guard_dispatch_icall_fptr
0x100485a37  mov     [rsp+318h+var_2D8], eax
0x100485a3b  mov     eax, [rsp+318h+var_2D8]
0x100485a3f  mov     [rsp+318h+nSize], eax
0x100485a43  lea     rcx, [rsp+318h+String]; lpString
0x100485a4b  call    cs:__imp_lstrlenW
0x100485a51  mov     ecx, [rsp+318h+nSize]
0x100485a55  lea     eax, [rcx+rax+2]
0x100485a59  mov     [rsp+318h+nSize], eax
0x100485a5d  cmp     [rsp+318h+lpMem], 0
0x100485a63  jz      loc_100485AEB
0x100485a69  mov     [rsp+318h+var_280], 0
0x100485a75  mov     eax, [rsp+318h+nSize]
0x100485a79  shl     rax, 1
0x100485a7c  mov     [rsp+318h+dwBytes], rax
0x100485a84  call    cs:__imp_GetProcessHeap
0x100485a8a  mov     rcx, [rsp+318h+dwBytes]
0x100485a92  mov     r9, rcx; dwBytes
0x100485a95  mov     r8, [rsp+318h+lpMem]; lpMem
0x100485a9a  mov     edx, 8; dwFlags
0x100485a9f  mov     rcx, rax; hHeap
0x100485aa2  call    cs:__imp_HeapReAlloc
0x100485aa8  mov     [rsp+318h+var_280], rax
0x100485ab0  cmp     [rsp+318h+var_280], 0
0x100485ab9  jnz     short loc_100485ADC
0x100485abb  call    cs:__imp_GetProcessHeap
0x100485ac1  mov     r8, [rsp+318h+lpMem]; lpMem
0x100485ac6  xor     edx, edx; dwFlags
0x100485ac8  mov     rcx, rax; hHeap
0x100485acb  call    cs:__imp_HeapFree
0x100485ad1  mov     [rsp+318h+lpMem], 0
0x100485ada  jmp     short loc_100485AE9
0x100485adc  mov     rax, [rsp+318h+var_280]
0x100485ae4  mov     [rsp+318h+lpMem], rax
0x100485ae9  jmp     short loc_100485B1E
0x100485aeb  mov     eax, [rsp+318h+nSize]
0x100485aef  shl     rax, 1
0x100485af2  mov     [rsp+318h+var_258], rax
0x100485afa  call    cs:__imp_GetProcessHeap
0x100485b00  mov     rcx, [rsp+318h+var_258]
0x100485b08  mov     r8, rcx; dwBytes
0x100485b0b  mov     edx, 8; dwFlags
0x100485b10  mov     rcx, rax; hHeap
0x100485b13  call    cs:__imp_HeapAlloc
0x100485b19  mov     [rsp+318h+lpMem], rax
0x100485b1e  cmp     [rsp+318h+lpMem], 0
0x100485b24  jz      short loc_100485B51
0x100485b26  mov     rax, [rsp+318h+var_290]
0x100485b2e  mov     [rsp+318h+var_250], rax
0x100485b36  mov     rdx, [rsp+318h+lpMem]
0x100485b3b  mov     ecx, [rsp+318h+nSize]
0x100485b3f  mov     rax, [rsp+318h+var_250]
0x100485b47  call    cs:__guard_dispatch_icall_fptr
0x100485b4d  mov     [rsp+318h+var_2D8], eax
0x100485b51  cmp     [rsp+318h+lpMem], 0
0x100485b57  jz      short loc_100485B67
0x100485b59  mov     eax, [rsp+318h+nSize]
0x100485b5d  cmp     [rsp+318h+var_2D8], eax
0x100485b61  jnb     loc_100485A15
0x100485b67  cmp     [rsp+318h+lpMem], 0
0x100485b6d  jz      short loc_100485B7B
0x100485b6f  mov     rax, [rsp+318h+lpMem]
0x100485b74  movzx   eax, word ptr [rax]
0x100485b77  test    eax, eax
0x100485b79  jnz     short loc_100485BB6
0x100485b7b  mov     rax, [rsp+318h+var_278]
0x100485b83  mov     [rsp+318h+var_248], rax
0x100485b8b  lea     rcx, [rsp+318h+String]
0x100485b93  mov     rax, [rsp+318h+var_248]
0x100485b9b  call    cs:__guard_dispatch_icall_fptr
0x100485ba1  mov     [rsp+318h+var_2D0], eax
0x100485ba5  cmp     [rsp+318h+var_2D0], 0
0x100485baa  jnz     short loc_100485BB4
0x100485bac  mov     [rsp+318h+var_2C0], 1
0x100485bb4  jmp     short loc_100485C1E
0x100485bb6  mov     [rsp+318h+cchCount2], 0FFFFFFFFh; cchCount2
0x100485bbe  lea     rax, [rsp+318h+String]
0x100485bc6  mov     [rsp+318h+lpString2], rax; lpString2
0x100485bcb  mov     r9d, 0FFFFFFFFh; cchCount1
0x100485bd1  mov     r8, [rsp+318h+lpMem]; lpString1
0x100485bd6  mov     edx, 1; dwCmpFlags
0x100485bdb  mov     ecx, [rsp+318h+Locale]; Locale
0x100485be2  call    cs:__imp_CompareStringW
0x100485be8  cmp     eax, 2
0x100485beb  jz      short loc_100485C16
0x100485bed  mov     [rsp+318h+var_2C0], 1
0x100485bf5  call    cs:__imp_GetProcessHeap
0x100485bfb  mov     r8, [rsp+318h+lpMem]; lpMem
0x100485c00  xor     edx, edx; dwFlags
0x100485c02  mov     rcx, rax; hHeap
0x100485c05  call    cs:__imp_HeapFree
0x100485c0b  mov     [rsp+318h+lpMem], 0
0x100485c14  jmp     short loc_100485C1E
0x100485c16  mov     [rsp+318h+var_2D0], 1
0x100485c1e  cmp     [rsp+318h+var_2C0], 0
0x100485c23  jz      loc_100485F76
0x100485c29  xor     r8d, r8d; nSize
0x100485c2c  xor     edx, edx; lpBuffer
0x100485c2e  lea     rcx, aPath; "Path"
0x100485c35  call    cs:__imp_GetEnvironmentVariableW
0x100485c3b  mov     [rsp+318h+var_2D8], eax
0x100485c3f  mov     eax, [rsp+318h+var_2D8]
0x100485c43  mov     [rsp+318h+nSize], eax
0x100485c47  cmp     [rsp+318h+nSize], 0
0x100485c4c  jnz     short loc_100485C6C
0x100485c4e  lea     rdx, [rsp+318h+String]; lpValue
0x100485c56  lea     rcx, aPath; "Path"
0x100485c5d  call    cs:__imp_SetEnvironmentVariableW
0x100485c63  mov     [rsp+318h+var_2D0], eax
0x100485c67  jmp     loc_100485F76
0x100485c6c  mov     [rsp+318h+var_2B8], 0
0x100485c74  mov     [rsp+318h+var_298], 0
0x100485c80  mov     [rsp+318h+var_2BC], 0
0x100485c88  lea     rcx, [rsp+318h+String]; lpString
0x100485c90  call    cs:__imp_lstrlenW
0x100485c96  inc     eax
0x100485c98  mov     [rsp+318h+var_2AC], eax
0x100485c9c  mov     eax, [rsp+318h+var_2D8]
0x100485ca0  mov     [rsp+318h+nSize], eax
0x100485ca4  lea     rcx, [rsp+318h+String]; lpString
0x100485cac  call    cs:__imp_lstrlenW
0x100485cb2  mov     ecx, [rsp+318h+nSize]
0x100485cb6  lea     eax, [rcx+rax+2]
0x100485cba  mov     [rsp+318h+nSize], eax
0x100485cbe  cmp     [rsp+318h+lpMem], 0
0x100485cc4  jz      loc_100485D4C
0x100485cca  mov     [rsp+318h+var_270], 0
0x100485cd6  mov     eax, [rsp+318h+nSize]
0x100485cda  shl     rax, 1
0x100485cdd  mov     [rsp+318h+var_240], rax
0x100485ce5  call    cs:__imp_GetProcessHeap
0x100485ceb  mov     rcx, [rsp+318h+var_240]
0x100485cf3  mov     r9, rcx; dwBytes
0x100485cf6  mov     r8, [rsp+318h+lpMem]; lpMem
0x100485cfb  mov     edx, 8; dwFlags
0x100485d00  mov     rcx, rax; hHeap
0x100485d03  call    cs:__imp_HeapReAlloc
0x100485d09  mov     [rsp+318h+var_270], rax
0x100485d11  cmp     [rsp+318h+var_270], 0
0x100485d1a  jnz     short loc_100485D3D
0x100485d1c  call    cs:__imp_GetProcessHeap
0x100485d22  mov     r8, [rsp+318h+lpMem]; lpMem
0x100485d27  xor     edx, edx; dwFlags
0x100485d29  mov     rcx, rax; hHeap
0x100485d2c  call    cs:__imp_HeapFree
0x100485d32  mov     [rsp+318h+lpMem], 0
0x100485d3b  jmp     short loc_100485D4A
0x100485d3d  mov     rax, [rsp+318h+var_270]
0x100485d45  mov     [rsp+318h+lpMem], rax
0x100485d4a  jmp     short loc_100485D7F
0x100485d4c  mov     eax, [rsp+318h+nSize]
0x100485d50  shl     rax, 1
0x100485d53  mov     [rsp+318h+var_238], rax
0x100485d5b  call    cs:__imp_GetProcessHeap
0x100485d61  mov     rcx, [rsp+318h+var_238]
0x100485d69  mov     r8, rcx; dwBytes
0x100485d6c  mov     edx, 8; dwFlags
0x100485d71  mov     rcx, rax; hHeap
0x100485d74  call    cs:__imp_HeapAlloc
0x100485d7a  mov     [rsp+318h+lpMem], rax
0x100485d7f  cmp     [rsp+318h+lpMem], 0
0x100485d85  jz      short loc_100485DA2
0x100485d87  mov     r8d, [rsp+318h+nSize]; nSize
0x100485d8c  mov     rdx, [rsp+318h+lpMem]; lpBuffer
0x100485d91  lea     rcx, aPath; "Path"
0x100485d98  call    cs:__imp_GetEnvironmentVariableW
0x100485d9e  mov     [rsp+318h+var_2D8], eax
0x100485da2  cmp     [rsp+318h+lpMem], 0
0x100485da8  jz      short loc_100485DB8
0x100485daa  mov     eax, [rsp+318h+nSize]
0x100485dae  cmp     [rsp+318h+var_2D8], eax
0x100485db2  jnb     loc_100485C9C
0x100485db8  mov     rax, [rsp+318h+lpMem]
0x100485dbd  mov     [rsp+318h+var_298], rax
0x100485dc5  mov     eax, [rsp+318h+var_2D8]
0x100485dc9  inc     eax
0x100485dcb  mov     [rsp+318h+var_2BC], eax
0x100485dcf  cmp     [rsp+318h+var_298], 0
0x100485dd8  jz      loc_100485EC5
0x100485dde  cmp     [rsp+318h+var_2B8], 0
0x100485de3  jnz     loc_100485EC5
0x100485de9  mov     eax, [rsp+318h+var_2AC]
0x100485ded  cmp     [rsp+318h+var_2BC], eax
0x100485df1  jb      loc_100485EC5
0x100485df7  mov     [rsp+318h+var_2CC], 0
0x100485dff  mov     [rsp+318h+var_2B0], 0
0x100485e07  xor     eax, eax
0x100485e09  mov     [rsp+318h+var_2D4], ax
0x100485e0e  mov     eax, [rsp+318h+var_2CC]
0x100485e12  mov     rcx, [rsp+318h+var_298]
0x100485e1a  movzx   eax, word ptr [rcx+rax*2]
0x100485e1e  mov     [rsp+318h+var_2D4], ax
0x100485e23  movzx   eax, [rsp+318h+var_2D4]
0x100485e28  mov     ecx, [rsp+318h+var_2CC]
0x100485e2c  movzx   ecx, [rsp+rcx*2+318h+String]
0x100485e34  cmp     eax, ecx
0x100485e36  jnz     short loc_100485E42
0x100485e38  mov     [rsp+318h+var_29C], 1
0x100485e40  jmp     short loc_100485E4A
0x100485e42  mov     [rsp+318h+var_29C], 0
0x100485e4a  mov     eax, [rsp+318h+var_29C]
0x100485e4e  mov     [rsp+318h+var_2B0], eax
0x100485e52  cmp     [rsp+318h+var_2B0], 0
0x100485e57  jz      short loc_100485E73
0x100485e59  mov     eax, [rsp+318h+var_2AC]
0x100485e5d  dec     eax
0x100485e5f  cmp     [rsp+318h+var_2CC], eax
0x100485e63  jnz     short loc_100485E67
0x100485e65  jmp     short loc_100485E73
0x100485e67  mov     eax, [rsp+318h+var_2CC]
0x100485e6b  inc     eax
0x100485e6d  mov     [rsp+318h+var_2CC], eax
0x100485e71  jmp     short loc_100485E0E
0x100485e73  cmp     [rsp+318h+var_2B0], 0
0x100485e78  jz      short loc_100485E84
0x100485e7a  mov     [rsp+318h+var_2B8], 1
0x100485e82  jmp     short loc_100485EA2
0x100485e84  mov     eax, [rsp+318h+var_2AC]
0x100485e88  dec     eax
0x100485e8a  cmp     [rsp+318h+var_2CC], eax
0x100485e8e  jnz     short loc_100485EA2
0x100485e90  movzx   eax, [rsp+318h+var_2D4]
0x100485e95  cmp     eax, 3Bh ; ';'
0x100485e98  jnz     short loc_100485EA2
0x100485e9a  mov     [rsp+318h+var_2B8], 1
0x100485ea2  mov     rax, [rsp+318h+var_298]
0x100485eaa  add     rax, 2
0x100485eae  mov     [rsp+318h+var_298], rax
0x100485eb6  mov     eax, [rsp+318h+var_2BC]
0x100485eba  dec     eax
0x100485ebc  mov     [rsp+318h+var_2BC], eax
  ... truncated ...
```
