# GetTimeZoneInformationKey

- ea: `0x180018830`
- end: `0x1800189a7`
- name: `GetTimeZoneInformationKey`
- size: `375`
- prototype: `__int64 __fastcall(HKEY *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x180018020`

## callees

- `0x180018830`
- `0x18001b150`
- `0x18001d010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18001892d`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18001892d`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800188d8`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800188d8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800188f2`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800188f2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180018963`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180018963`

## string_xrefs

- `0x180018878`: `kernelbase.dll`
- `0x1800188e6`: `GetPersistedRegistryLocationW`

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
0x180018830  mov     [rsp-8+arg_8], rbx
0x180018835  mov     [rsp-8+arg_10], rsi
0x18001883a  push    rbp
0x18001883b  push    rdi
0x18001883c  push    r14
0x18001883e  lea     rbp, [rsp-1D0h]
0x180018846  sub     rsp, 2D0h
0x18001884d  mov     rax, cs:__security_cookie
0x180018854  xor     rax, rsp
0x180018857  mov     [rbp+1E0h+var_20], rax
0x18001885e  mov     rax, cs:phkResult
0x180018865  mov     rsi, rcx
0x180018868  test    rax, rax
0x18001886b  jnz     loc_18001897B
0x180018871  movaps  xmm0, xmmword ptr cs:aSystemCurrentc_0; "SYSTEM\\CurrentControlSet\\Control\\Tim"...
0x180018878  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18001887f  movaps  xmm1, xmmword ptr cs:aSystemCurrentc_0+10h; "urrentControlSet\\Control\\TimeZoneInfo"...
0x180018886  xor     edx, edx; hFile
0x180018888  movaps  [rsp+2E0h+var_2A0], xmm0
0x18001888d  mov     r8d, 800h; dwFlags
0x180018893  movaps  xmm0, xmmword ptr cs:aSystemCurrentc_0+20h; "ntrolSet\\Control\\TimeZoneInformation"
0x18001889a  xor     r14d, r14d
0x18001889d  movaps  [rsp+2E0h+var_280], xmm0
0x1800188a2  movaps  xmm0, xmmword ptr cs:aSystemCurrentc_0+40h; "\\TimeZoneInformation"
0x1800188a9  movaps  [rsp+2E0h+var_290], xmm1
0x1800188ae  movaps  xmm1, xmmword ptr cs:aSystemCurrentc_0+30h; "\\Control\\TimeZoneInformation"
0x1800188b5  movaps  [rbp+1E0h+var_260], xmm0
0x1800188b9  movups  xmm0, xmmword ptr cs:aSystemCurrentc_0+5Ah; "rmation"
0x1800188c0  mov     [rsp+2E0h+var_2B0], eax
0x1800188c4  movaps  [rsp+2E0h+var_270], xmm1
0x1800188c9  movaps  xmm1, xmmword ptr cs:aSystemCurrentc_0+50h; "eInformation"
0x1800188d0  movaps  xmmword ptr [rbp+1E0h+var_250], xmm1
0x1800188d4  movups  xmmword ptr [rbp+1E0h+var_250+0Ah], xmm0
0x1800188d8  call    cs:__imp_LoadLibraryExW
0x1800188de  mov     rdi, rax
0x1800188e1  test    rax, rax
0x1800188e4  jz      short loc_180018937
0x1800188e6  lea     rdx, aGetpersistedre; "GetPersistedRegistryLocationW"
0x1800188ed  mov     rcx, rax; hModule
0x1800188f0  xor     ebx, ebx
0x1800188f2  call    cs:__imp_GetProcAddress
0x1800188f8  test    rax, rax
0x1800188fb  jz      short loc_18001892A
0x1800188fd  lea     rcx, [rsp+2E0h+var_2B0]
0x180018902  mov     r9d, 208h
0x180018908  mov     [rsp+2E0h+phkResult], rcx
0x18001890d  lea     r8, [rbp+1E0h+SubKey]
0x180018911  lea     rcx, aTimezoneinform; "TimeZoneInformationSettings"
0x180018918  lea     rdx, [rsp+2E0h+var_2A0]
0x18001891d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018922  mov     ebx, eax
0x180018924  mov     r14d, 1
0x18001892a  mov     rcx, rdi; hLibModule
0x18001892d  call    cs:__imp_FreeLibrary
0x180018933  test    ebx, ebx
0x180018935  jnz     short loc_18001896D
0x180018937  lea     rax, [rbp+1E0h+SubKey]
0x18001893b  test    r14d, r14d
0x18001893e  lea     rdx, [rsp+2E0h+var_2A0]
0x180018943  mov     r9d, 20019h; samDesired
0x180018949  cmovnz  rdx, rax; lpSubKey
0x18001894d  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180018954  lea     rax, phkResult
0x18001895b  xor     r8d, r8d; ulOptions
0x18001895e  mov     [rsp+2E0h+phkResult], rax; phkResult
0x180018963  call    cs:__imp_RegOpenKeyExW
0x180018969  test    eax, eax
0x18001896b  jz      short loc_180018974
0x18001896d  mov     eax, 80040203h
0x180018972  jmp     short loc_180018980
0x180018974  mov     rax, cs:phkResult
0x18001897b  mov     [rsi], rax
0x18001897e  xor     eax, eax
0x180018980  mov     rcx, [rbp+1E0h+var_20]
0x180018987  xor     rcx, rsp; StackCookie
0x18001898a  call    __security_check_cookie
0x18001898f  lea     r11, [rsp+2E0h+var_10]
0x180018997  mov     rbx, [r11+28h]
0x18001899b  mov     rsi, [r11+30h]
0x18001899f  mov     rsp, r11
0x1800189a2  pop     r14
0x1800189a4  pop     rdi
0x1800189a5  pop     rbp
0x1800189a6  retn
```
