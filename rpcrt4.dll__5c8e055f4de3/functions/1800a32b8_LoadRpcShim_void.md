# LoadRpcShim(void)

- ea: `0x1800a32b8`
- end: `0x1800a3461`
- name: `?LoadRpcShim@@YAJXZ`
- size: `425`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x1800a2acc`

## callees

- `0x1800a32b8`
- `0x1800d2010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a33e1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a33e1`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800a33f5`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800a33f5`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800a32ce`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800a32ce`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800a32ea`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800a3311`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800a3338`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800a335f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800a3382`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800a33a5`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800a33c8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800a32ea`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800a3311`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800a3338`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800a335f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800a3382`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800a33a5`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800a33c8`

## string_xrefs

- `0x1800a32c5`: `RpcShim.dll`
- `0x1800a3378`: `RegisterThreadForPauseInjection`
- `0x1800a339b`: `UnRegisterThreadForPauseInjection`

## pseudocode

```c
__int64 LoadRpcShim(void)
{
  HMODULE Library; // rax
  HMODULE v1; // rdi
  FARPROC ProcAddress; // rax
  FARPROC v3; // rax
  FARPROC v4; // rax
  FARPROC v5; // rax
  FARPROC v6; // rax
  FARPROC v7; // rax
  FARPROC v8; // rax
  struct _tRpcVerifierSettings *v9; // rcx
  DWORD LastError; // ebx
  struct _tRpcVerifierSettings *v11; // rax

  Library = LoadLibraryExW(L"RpcShim.dll", 0, 0);
  v1 = Library;
  if ( !Library )
    goto LABEL_9;
  ProcAddress = GetProcAddress(Library, "InitializeRpcShim");
  *((_QWORD *)pRpcVerifierSettings + 21) = ProcAddress;
  if ( !ProcAddress )
    goto LABEL_9;
  v3 = GetProcAddress(v1, "CorruptionInject");
  *((_QWORD *)pRpcVerifierSettings + 22) = v3;
  if ( !v3 )
    goto LABEL_9;
  v4 = GetProcAddress(v1, "NDRSendCorruptionInject");
  *((_QWORD *)pRpcVerifierSettings + 23) = v4;
  if ( !v4 )
    goto LABEL_9;
  v5 = GetProcAddress(v1, "NDRReturnCorruptionInject");
  *((_QWORD *)pRpcVerifierSettings + 24) = v5;
  if ( !v5 )
    goto LABEL_9;
  v6 = GetProcAddress(v1, "RegisterThreadForPauseInjection");
  *((_QWORD *)pRpcVerifierSettings + 25) = v6;
  if ( v6
    && (v7 = GetProcAddress(v1, "UnRegisterThreadForPauseInjection"), (*((_QWORD *)pRpcVerifierSettings + 26) = v7) != 0)
    && (v8 = GetProcAddress(v1, "CloseAlpcPort"),
        v9 = pRpcVerifierSettings,
        (*((_QWORD *)pRpcVerifierSettings + 27) = v8) != 0) )
  {
    LastError = 0;
    (*((void (**)(void))v9 + 21))();
  }
  else
  {
LABEL_9:
    LastError = GetLastError();
    if ( LastError )
    {
      if ( v1 )
        FreeLibrary(v1);
      v11 = pRpcVerifierSettings;
      *((_QWORD *)pRpcVerifierSettings + 21) = 0;
      *((_QWORD *)v11 + 22) = 0;
      *((_QWORD *)v11 + 23) = 0;
      *((_QWORD *)v11 + 24) = 0;
      *((_QWORD *)v11 + 25) = 0;
      *((_QWORD *)v11 + 26) = 0;
    }
  }
  return LastError;
}

```

## disassembly

```asm
0x1800a32b8  mov     [rsp+arg_0], rbx
0x1800a32bd  push    rdi
0x1800a32be  sub     rsp, 20h
0x1800a32c2  xor     r8d, r8d; dwFlags
0x1800a32c5  lea     rcx, aRpcshimDll; "RpcShim.dll"
0x1800a32cc  xor     edx, edx; hFile
0x1800a32ce  call    cs:__imp_LoadLibraryExW
0x1800a32d4  mov     rdi, rax
0x1800a32d7  test    rax, rax
0x1800a32da  jz      loc_1800A33E1
0x1800a32e0  lea     rdx, aInitializerpcs; "InitializeRpcShim"
0x1800a32e7  mov     rcx, rax; hModule
0x1800a32ea  call    cs:__imp_GetProcAddress
0x1800a32f0  mov     rcx, cs:?pRpcVerifierSettings@@3PEAU_tRpcVerifierSettings@@EA; _tRpcVerifierSettings * pRpcVerifierSettings
0x1800a32f7  mov     [rcx+0A8h], rax
0x1800a32fe  test    rax, rax
0x1800a3301  jz      loc_1800A33E1
0x1800a3307  lea     rdx, aCorruptioninje; "CorruptionInject"
0x1800a330e  mov     rcx, rdi; hModule
0x1800a3311  call    cs:__imp_GetProcAddress
0x1800a3317  mov     rcx, cs:?pRpcVerifierSettings@@3PEAU_tRpcVerifierSettings@@EA; _tRpcVerifierSettings * pRpcVerifierSettings
0x1800a331e  mov     [rcx+0B0h], rax
0x1800a3325  test    rax, rax
0x1800a3328  jz      loc_1800A33E1
0x1800a332e  lea     rdx, aNdrsendcorrupt; "NDRSendCorruptionInject"
0x1800a3335  mov     rcx, rdi; hModule
0x1800a3338  call    cs:__imp_GetProcAddress
0x1800a333e  mov     rcx, cs:?pRpcVerifierSettings@@3PEAU_tRpcVerifierSettings@@EA; _tRpcVerifierSettings * pRpcVerifierSettings
0x1800a3345  mov     [rcx+0B8h], rax
0x1800a334c  test    rax, rax
0x1800a334f  jz      loc_1800A33E1
0x1800a3355  lea     rdx, aNdrreturncorru; "NDRReturnCorruptionInject"
0x1800a335c  mov     rcx, rdi; hModule
0x1800a335f  call    cs:__imp_GetProcAddress
0x1800a3365  mov     rcx, cs:?pRpcVerifierSettings@@3PEAU_tRpcVerifierSettings@@EA; _tRpcVerifierSettings * pRpcVerifierSettings
0x1800a336c  mov     [rcx+0C0h], rax
0x1800a3373  test    rax, rax
0x1800a3376  jz      short loc_1800A33E1
0x1800a3378  lea     rdx, aRegisterthread; "RegisterThreadForPauseInjection"
0x1800a337f  mov     rcx, rdi; hModule
0x1800a3382  call    cs:__imp_GetProcAddress
0x1800a3388  mov     rcx, cs:?pRpcVerifierSettings@@3PEAU_tRpcVerifierSettings@@EA; _tRpcVerifierSettings * pRpcVerifierSettings
0x1800a338f  mov     [rcx+0C8h], rax
0x1800a3396  test    rax, rax
0x1800a3399  jz      short loc_1800A33E1
0x1800a339b  lea     rdx, aUnregisterthre; "UnRegisterThreadForPauseInjection"
0x1800a33a2  mov     rcx, rdi; hModule
0x1800a33a5  call    cs:__imp_GetProcAddress
0x1800a33ab  mov     rcx, cs:?pRpcVerifierSettings@@3PEAU_tRpcVerifierSettings@@EA; _tRpcVerifierSettings * pRpcVerifierSettings
0x1800a33b2  mov     [rcx+0D0h], rax
0x1800a33b9  test    rax, rax
0x1800a33bc  jz      short loc_1800A33E1
0x1800a33be  lea     rdx, aClosealpcport; "CloseAlpcPort"
0x1800a33c5  mov     rcx, rdi; hModule
0x1800a33c8  call    cs:__imp_GetProcAddress
0x1800a33ce  mov     rcx, cs:?pRpcVerifierSettings@@3PEAU_tRpcVerifierSettings@@EA; _tRpcVerifierSettings * pRpcVerifierSettings
0x1800a33d5  mov     [rcx+0D8h], rax
0x1800a33dc  test    rax, rax
0x1800a33df  jnz     short loc_1800A3446
0x1800a33e1  call    cs:__imp_GetLastError
0x1800a33e7  mov     ebx, eax
0x1800a33e9  test    eax, eax
0x1800a33eb  jz      short loc_1800A3454
0x1800a33ed  test    rdi, rdi
0x1800a33f0  jz      short loc_1800A33FB
0x1800a33f2  mov     rcx, rdi; hLibModule
0x1800a33f5  call    cs:__imp_FreeLibrary
0x1800a33fb  mov     rax, cs:?pRpcVerifierSettings@@3PEAU_tRpcVerifierSettings@@EA; _tRpcVerifierSettings * pRpcVerifierSettings
0x1800a3402  mov     qword ptr [rax+0A8h], 0
0x1800a340d  mov     qword ptr [rax+0B0h], 0
0x1800a3418  mov     qword ptr [rax+0B8h], 0
0x1800a3423  mov     qword ptr [rax+0C0h], 0
0x1800a342e  mov     qword ptr [rax+0C8h], 0
0x1800a3439  mov     qword ptr [rax+0D0h], 0
0x1800a3444  jmp     short loc_1800A3454
0x1800a3446  mov     rax, [rcx+0A8h]
0x1800a344d  xor     ebx, ebx
0x1800a344f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a3454  mov     eax, ebx
0x1800a3456  mov     rbx, [rsp+28h+arg_0]
0x1800a345b  add     rsp, 20h
0x1800a345f  pop     rdi
0x1800a3460  retn
```
