# NtSetupKey(void)

- ea: `0x18001001c`
- end: `0x180010166`
- name: `?NtSetupKey@@YAHXZ`
- size: `330`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x18000fff0`

## callees

- `0x18001001c`
- `0x18001016c`
- `0x1800101cc`
- `0x180047010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001011f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010154`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001011f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010154`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180010109`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001013e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180010109`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001013e`

## string_xrefs

- `0x180010137`: `RegOpenKeyExW`

## pseudocode

```c
_BOOL8 NtSetupKey(void)
{
  FARPROC ProcAddress; // rax
  DWORD LastError; // eax
  __int64 v2; // rdi
  FARPROC v3; // rax
  DWORD v4; // eax
  int RegistryDll; // ebx
  int v7; // [rsp+50h] [rbp+8h] BYREF
  int v8; // [rsp+58h] [rbp+10h] BYREF
  __int64 v9; // [rsp+60h] [rbp+18h] BYREF

  if ( CWbemInstallObject::m_bOffline )
    return 1;
  ProcAddress = (FARPROC)qword_1800703C0;
  v9 = 0;
  if ( qword_1800703C0 )
    goto LABEL_3;
  if ( (unsigned int)DLpLoadRegistryDll() )
    return 0;
  ProcAddress = GetProcAddress(g_hInstRegistryDLL, "RegOpenKeyExW");
  qword_1800703C0 = (__int64)ProcAddress;
  if ( ProcAddress )
LABEL_3:
    LastError = ((__int64 (__fastcall *)(__int64, const wchar_t *, _QWORD, __int64, __int64 *))ProcAddress)(
                  -2147483646,
                  L"system\\Setup",
                  0,
                  131097,
                  &v9);
  else
    LastError = GetLastError();
  if ( !LastError )
  {
    v2 = v9;
    v7 = 0;
    v3 = (FARPROC)qword_1800703F0;
    v8 = 4;
    if ( qword_1800703F0 )
      goto LABEL_6;
    RegistryDll = DLpLoadRegistryDll();
    if ( RegistryDll )
    {
LABEL_8:
      DLRegCloseKey(v9);
      if ( !RegistryDll )
        return v7 == 1;
      return 0;
    }
    v3 = GetProcAddress(g_hInstRegistryDLL, "RegQueryValueExW");
    qword_1800703F0 = (__int64)v3;
    if ( v3 )
LABEL_6:
      v4 = ((__int64 (__fastcall *)(__int64, const wchar_t *, _QWORD, _QWORD, int *, int *))v3)(
             v2,
             L"SystemSetupInProgress",
             0,
             0,
             &v7,
             &v8);
    else
      v4 = GetLastError();
    RegistryDll = v4;
    goto LABEL_8;
  }
  return 0;
}

```

## disassembly

```asm
0x18001001c  mov     [rsp+arg_18], rbx
0x180010021  push    rdi
0x180010022  sub     rsp, 40h
0x180010026  cmp     cs:?m_bOffline@CWbemInstallObject@@0_NA, 0; bool CWbemInstallObject::m_bOffline
0x18001002d  jnz     loc_1800100E9
0x180010033  mov     rax, cs:qword_1800703C0
0x18001003a  mov     [rsp+48h+arg_10], 0
0x180010043  test    rax, rax
0x180010046  jz      loc_180010127
0x18001004c  lea     rcx, [rsp+48h+arg_10]
0x180010051  mov     r9d, 20019h
0x180010057  mov     [rsp+48h+var_28], rcx
0x18001005c  lea     rdx, aSystemSetup; "system\\Setup"
0x180010063  mov     rcx, 0FFFFFFFF80000002h
0x18001006a  xor     r8d, r8d
0x18001006d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010072  test    eax, eax
0x180010074  jnz     loc_18001015F
0x18001007a  mov     rdi, [rsp+48h+arg_10]
0x18001007f  mov     [rsp+48h+arg_0], eax
0x180010083  mov     rax, cs:qword_1800703F0
0x18001008a  mov     [rsp+48h+arg_8], 4
0x180010092  test    rax, rax
0x180010095  jz      short loc_1800100F0
0x180010097  lea     rcx, [rsp+48h+arg_8]
0x18001009c  xor     r9d, r9d
0x18001009f  mov     [rsp+48h+var_20], rcx
0x1800100a4  lea     rdx, aSystemsetupinp; "SystemSetupInProgress"
0x1800100ab  lea     rcx, [rsp+48h+arg_0]
0x1800100b0  xor     r8d, r8d
0x1800100b3  mov     [rsp+48h+var_28], rcx
0x1800100b8  mov     rcx, rdi
0x1800100bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800100c0  mov     ebx, eax
0x1800100c2  mov     rcx, [rsp+48h+arg_10]
0x1800100c7  call    DLRegCloseKey
0x1800100cc  test    ebx, ebx
0x1800100ce  jnz     loc_18001015F
0x1800100d4  xor     eax, eax
0x1800100d6  cmp     [rsp+48h+arg_0], 1
0x1800100db  setz    al
0x1800100de  mov     rbx, [rsp+48h+arg_18]
0x1800100e3  add     rsp, 40h
0x1800100e7  pop     rdi
0x1800100e8  retn
0x1800100e9  mov     eax, 1
0x1800100ee  jmp     short loc_1800100DE
0x1800100f0  call    ?DLpLoadRegistryDll@@YAKXZ; DLpLoadRegistryDll(void)
0x1800100f5  mov     ebx, eax
0x1800100f7  test    eax, eax
0x1800100f9  jnz     short loc_1800100C2
0x1800100fb  mov     rcx, cs:?g_hInstRegistryDLL@@3PEAUHINSTANCE__@@EA; hModule
0x180010102  lea     rdx, aRegqueryvaluee; "RegQueryValueExW"
0x180010109  call    cs:__imp_GetProcAddress
0x18001010f  mov     cs:qword_1800703F0, rax
0x180010116  test    rax, rax
0x180010119  jnz     loc_180010097
0x18001011f  call    cs:__imp_GetLastError
0x180010125  jmp     short loc_1800100C0
0x180010127  call    ?DLpLoadRegistryDll@@YAKXZ; DLpLoadRegistryDll(void)
0x18001012c  test    eax, eax
0x18001012e  jnz     short loc_18001015F
0x180010130  mov     rcx, cs:?g_hInstRegistryDLL@@3PEAUHINSTANCE__@@EA; hModule
0x180010137  lea     rdx, aRegopenkeyexw; "RegOpenKeyExW"
0x18001013e  call    cs:__imp_GetProcAddress
0x180010144  mov     cs:qword_1800703C0, rax
0x18001014b  test    rax, rax
0x18001014e  jnz     loc_18001004C
0x180010154  call    cs:__imp_GetLastError
0x18001015a  jmp     loc_180010072
0x18001015f  xor     eax, eax
0x180010161  jmp     loc_1800100DE
```
