# GetTimeZoneInformationKey

- ea: `0x1800266d4`
- end: `0x18002684b`
- name: `GetTimeZoneInformationKey`
- size: `375`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x180025d14`

## callees

- `0x1800266d4`
- `0x180028f60`
- `0x18002a010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800267d1`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800267d1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180026796`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180026796`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18002677c`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18002677c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180026807`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180026807`

## string_xrefs

- `0x18002671c`: `kernelbase.dll`
- `0x18002678a`: `GetPersistedRegistryLocationW`

## pseudocode

```c
__int64 __fastcall GetTimeZoneInformationKey(HKEY *a1)
{
  HKEY v1; // rax
  int v3; // r14d
  HMODULE Library; // rax
  HMODULE v5; // rdi
  int v6; // ebx
  FARPROC ProcAddress; // rax
  WCHAR *v8; // rdx
  _DWORD v10[4]; // [rsp+30h] [rbp-D0h] BYREF
  _OWORD v11[5]; // [rsp+40h] [rbp-C0h] BYREF
  _OWORD v12[2]; // [rsp+90h] [rbp-70h]
  WCHAR SubKey[264]; // [rsp+B0h] [rbp-50h] BYREF

  v1 = phkResult;
  if ( !phkResult )
  {
    v11[0] = *(_OWORD *)L"SYSTEM\\CurrentControlSet\\Control\\TimeZoneInformation";
    v3 = 0;
    v11[2] = *(_OWORD *)L"ntrolSet\\Control\\TimeZoneInformation";
    v11[1] = *(_OWORD *)L"urrentControlSet\\Control\\TimeZoneInformation";
    v11[4] = *(_OWORD *)L"\\TimeZoneInformation";
    v10[0] = 0;
    v11[3] = *(_OWORD *)L"\\Control\\TimeZoneInformation";
    v12[0] = *(_OWORD *)L"eInformation";
    *(_OWORD *)((char *)v12 + 10) = *(_OWORD *)L"rmation";
    Library = LoadLibraryExW(L"kernelbase.dll", 0, 0x800u);
    v5 = Library;
    if ( Library )
    {
      v6 = 0;
      ProcAddress = GetProcAddress(Library, "GetPersistedRegistryLocationW");
      if ( ProcAddress )
      {
        v6 = ((__int64 (__fastcall *)(const wchar_t *, _OWORD *, WCHAR *, __int64, _DWORD *))ProcAddress)(
               L"TimeZoneInformationSettings",
               v11,
               SubKey,
               520,
               v10);
        v3 = 1;
      }
      FreeLibrary(v5);
      if ( v6 )
        return 2147746307LL;
    }
    v8 = (WCHAR *)v11;
    if ( v3 )
      v8 = SubKey;
    if ( RegOpenKeyExW(HKEY_LOCAL_MACHINE, v8, 0, 0x20019u, &phkResult) )
      return 2147746307LL;
    v1 = phkResult;
  }
  *a1 = v1;
  return 0;
}

```

## disassembly

```asm
0x1800266d4  mov     [rsp-8+arg_8], rbx
0x1800266d9  mov     [rsp-8+arg_10], rsi
0x1800266de  push    rbp
0x1800266df  push    rdi
0x1800266e0  push    r14
0x1800266e2  lea     rbp, [rsp-1D0h]
0x1800266ea  sub     rsp, 2D0h
0x1800266f1  mov     rax, cs:__security_cookie
0x1800266f8  xor     rax, rsp
0x1800266fb  mov     [rbp+1E0h+var_20], rax
0x180026702  mov     rax, cs:phkResult
0x180026709  mov     rsi, rcx
0x18002670c  test    rax, rax
0x18002670f  jnz     loc_18002681F
0x180026715  movaps  xmm0, xmmword ptr cs:aSystemCurrentc_0; "SYSTEM\\CurrentControlSet\\Control\\Tim"...
0x18002671c  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x180026723  movaps  xmm1, xmmword ptr cs:aSystemCurrentc_0+10h; "urrentControlSet\\Control\\TimeZoneInfo"...
0x18002672a  xor     edx, edx; hFile
0x18002672c  movaps  [rsp+2E0h+var_2A0], xmm0
0x180026731  mov     r8d, 800h; dwFlags
0x180026737  movaps  xmm0, xmmword ptr cs:aSystemCurrentc_0+20h; "ntrolSet\\Control\\TimeZoneInformation"
0x18002673e  xor     r14d, r14d
0x180026741  movaps  [rsp+2E0h+var_280], xmm0
0x180026746  movaps  xmm0, xmmword ptr cs:aSystemCurrentc_0+40h; "\\TimeZoneInformation"
0x18002674d  movaps  [rsp+2E0h+var_290], xmm1
0x180026752  movaps  xmm1, xmmword ptr cs:aSystemCurrentc_0+30h; "\\Control\\TimeZoneInformation"
0x180026759  movaps  [rbp+1E0h+var_260], xmm0
0x18002675d  movups  xmm0, xmmword ptr cs:aSystemCurrentc_0+5Ah; "rmation"
0x180026764  mov     [rsp+2E0h+var_2B0], eax
0x180026768  movaps  [rsp+2E0h+var_270], xmm1
0x18002676d  movaps  xmm1, xmmword ptr cs:aSystemCurrentc_0+50h; "eInformation"
0x180026774  movaps  xmmword ptr [rbp+1E0h+var_250], xmm1
0x180026778  movups  xmmword ptr [rbp+1E0h+var_250+0Ah], xmm0
0x18002677c  call    cs:__imp_LoadLibraryExW
0x180026782  mov     rdi, rax
0x180026785  test    rax, rax
0x180026788  jz      short loc_1800267DB
0x18002678a  lea     rdx, aGetpersistedre; "GetPersistedRegistryLocationW"
0x180026791  mov     rcx, rax; hModule
0x180026794  xor     ebx, ebx
0x180026796  call    cs:__imp_GetProcAddress
0x18002679c  test    rax, rax
0x18002679f  jz      short loc_1800267CE
0x1800267a1  lea     rcx, [rsp+2E0h+var_2B0]
0x1800267a6  mov     r9d, 208h
0x1800267ac  mov     [rsp+2E0h+phkResult], rcx
0x1800267b1  lea     r8, [rbp+1E0h+SubKey]
0x1800267b5  lea     rcx, aTimezoneinform; "TimeZoneInformationSettings"
0x1800267bc  lea     rdx, [rsp+2E0h+var_2A0]
0x1800267c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800267c6  mov     ebx, eax
0x1800267c8  mov     r14d, 1
0x1800267ce  mov     rcx, rdi; hLibModule
0x1800267d1  call    cs:__imp_FreeLibrary
0x1800267d7  test    ebx, ebx
0x1800267d9  jnz     short loc_180026811
0x1800267db  lea     rax, [rbp+1E0h+SubKey]
0x1800267df  test    r14d, r14d
0x1800267e2  lea     rdx, [rsp+2E0h+var_2A0]
0x1800267e7  mov     r9d, 20019h; samDesired
0x1800267ed  cmovnz  rdx, rax; lpSubKey
0x1800267f1  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800267f8  lea     rax, phkResult
0x1800267ff  xor     r8d, r8d; ulOptions
0x180026802  mov     [rsp+2E0h+phkResult], rax; phkResult
0x180026807  call    cs:__imp_RegOpenKeyExW
0x18002680d  test    eax, eax
0x18002680f  jz      short loc_180026818
0x180026811  mov     eax, 80040203h
0x180026816  jmp     short loc_180026824
0x180026818  mov     rax, cs:phkResult
0x18002681f  mov     [rsi], rax
0x180026822  xor     eax, eax
0x180026824  mov     rcx, [rbp+1E0h+var_20]
0x18002682b  xor     rcx, rsp; StackCookie
0x18002682e  call    __security_check_cookie
0x180026833  lea     r11, [rsp+2E0h+var_10]
0x18002683b  mov     rbx, [r11+28h]
0x18002683f  mov     rsi, [r11+30h]
0x180026843  mov     rsp, r11
0x180026846  pop     r14
0x180026848  pop     rdi
0x180026849  pop     rbp
0x18002684a  retn
```
