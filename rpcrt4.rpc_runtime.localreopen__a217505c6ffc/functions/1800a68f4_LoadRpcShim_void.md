# LoadRpcShim(void)

- ea: `0x1800a68f4`
- end: `0x1800a6ada`
- name: `?LoadRpcShim@@YAJXZ`
- size: `486`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x1800a6048`

## callees

- `0x1800a68f4`
- `0x1800d7010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a6a4d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a6a4d`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800a6a67`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800a6a67`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800a690a`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800a690a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800a692c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800a6959`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800a6986`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800a69b3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800a69dc`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800a6a05`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800a6a2e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800a692c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800a6959`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800a6986`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800a69b3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800a69dc`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800a6a05`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800a6a2e`

## string_xrefs

- `0x1800a6901`: `RpcShim.dll`
- `0x1800a69d2`: `RegisterThreadForPauseInjection`
- `0x1800a69fb`: `UnRegisterThreadForPauseInjection`

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
0x1800a68f4  mov     [rsp+arg_0], rbx
0x1800a68f9  push    rdi
0x1800a68fa  sub     rsp, 20h
0x1800a68fe  xor     r8d, r8d; dwFlags
0x1800a6901  lea     rcx, aRpcshimDll; "RpcShim.dll"
0x1800a6908  xor     edx, edx; hFile
0x1800a690a  call    cs:__imp_LoadLibraryExW
0x1800a6911  nop     dword ptr [rax+rax+00h]
0x1800a6916  mov     rdi, rax
0x1800a6919  test    rax, rax
0x1800a691c  jz      loc_1800A6A4D
0x1800a6922  lea     rdx, aInitializerpcs; "InitializeRpcShim"
0x1800a6929  mov     rcx, rax; hModule
0x1800a692c  call    cs:__imp_GetProcAddress
0x1800a6933  nop     dword ptr [rax+rax+00h]
0x1800a6938  mov     rcx, cs:?pRpcVerifierSettings@@3PEAU_tRpcVerifierSettings@@EA; _tRpcVerifierSettings * pRpcVerifierSettings
0x1800a693f  mov     [rcx+0A8h], rax
0x1800a6946  test    rax, rax
0x1800a6949  jz      loc_1800A6A4D
0x1800a694f  lea     rdx, aCorruptioninje; "CorruptionInject"
0x1800a6956  mov     rcx, rdi; hModule
0x1800a6959  call    cs:__imp_GetProcAddress
0x1800a6960  nop     dword ptr [rax+rax+00h]
0x1800a6965  mov     rcx, cs:?pRpcVerifierSettings@@3PEAU_tRpcVerifierSettings@@EA; _tRpcVerifierSettings * pRpcVerifierSettings
0x1800a696c  mov     [rcx+0B0h], rax
0x1800a6973  test    rax, rax
0x1800a6976  jz      loc_1800A6A4D
0x1800a697c  lea     rdx, aNdrsendcorrupt; "NDRSendCorruptionInject"
0x1800a6983  mov     rcx, rdi; hModule
0x1800a6986  call    cs:__imp_GetProcAddress
0x1800a698d  nop     dword ptr [rax+rax+00h]
0x1800a6992  mov     rcx, cs:?pRpcVerifierSettings@@3PEAU_tRpcVerifierSettings@@EA; _tRpcVerifierSettings * pRpcVerifierSettings
0x1800a6999  mov     [rcx+0B8h], rax
0x1800a69a0  test    rax, rax
0x1800a69a3  jz      loc_1800A6A4D
0x1800a69a9  lea     rdx, aNdrreturncorru; "NDRReturnCorruptionInject"
0x1800a69b0  mov     rcx, rdi; hModule
0x1800a69b3  call    cs:__imp_GetProcAddress
0x1800a69ba  nop     dword ptr [rax+rax+00h]
0x1800a69bf  mov     rcx, cs:?pRpcVerifierSettings@@3PEAU_tRpcVerifierSettings@@EA; _tRpcVerifierSettings * pRpcVerifierSettings
0x1800a69c6  mov     [rcx+0C0h], rax
0x1800a69cd  test    rax, rax
0x1800a69d0  jz      short loc_1800A6A4D
0x1800a69d2  lea     rdx, aRegisterthread; "RegisterThreadForPauseInjection"
0x1800a69d9  mov     rcx, rdi; hModule
0x1800a69dc  call    cs:__imp_GetProcAddress
0x1800a69e3  nop     dword ptr [rax+rax+00h]
0x1800a69e8  mov     rcx, cs:?pRpcVerifierSettings@@3PEAU_tRpcVerifierSettings@@EA; _tRpcVerifierSettings * pRpcVerifierSettings
0x1800a69ef  mov     [rcx+0C8h], rax
0x1800a69f6  test    rax, rax
0x1800a69f9  jz      short loc_1800A6A4D
0x1800a69fb  lea     rdx, aUnregisterthre; "UnRegisterThreadForPauseInjection"
0x1800a6a02  mov     rcx, rdi; hModule
0x1800a6a05  call    cs:__imp_GetProcAddress
0x1800a6a0c  nop     dword ptr [rax+rax+00h]
0x1800a6a11  mov     rcx, cs:?pRpcVerifierSettings@@3PEAU_tRpcVerifierSettings@@EA; _tRpcVerifierSettings * pRpcVerifierSettings
0x1800a6a18  mov     [rcx+0D0h], rax
0x1800a6a1f  test    rax, rax
0x1800a6a22  jz      short loc_1800A6A4D
0x1800a6a24  lea     rdx, aClosealpcport; "CloseAlpcPort"
0x1800a6a2b  mov     rcx, rdi; hModule
0x1800a6a2e  call    cs:__imp_GetProcAddress
0x1800a6a35  nop     dword ptr [rax+rax+00h]
0x1800a6a3a  mov     rcx, cs:?pRpcVerifierSettings@@3PEAU_tRpcVerifierSettings@@EA; _tRpcVerifierSettings * pRpcVerifierSettings
0x1800a6a41  mov     [rcx+0D8h], rax
0x1800a6a48  test    rax, rax
0x1800a6a4b  jnz     short loc_1800A6ABE
0x1800a6a4d  call    cs:__imp_GetLastError
0x1800a6a54  nop     dword ptr [rax+rax+00h]
0x1800a6a59  mov     ebx, eax
0x1800a6a5b  test    eax, eax
0x1800a6a5d  jz      short loc_1800A6ACC
0x1800a6a5f  test    rdi, rdi
0x1800a6a62  jz      short loc_1800A6A73
0x1800a6a64  mov     rcx, rdi; hLibModule
0x1800a6a67  call    cs:__imp_FreeLibrary
0x1800a6a6e  nop     dword ptr [rax+rax+00h]
0x1800a6a73  mov     rax, cs:?pRpcVerifierSettings@@3PEAU_tRpcVerifierSettings@@EA; _tRpcVerifierSettings * pRpcVerifierSettings
0x1800a6a7a  mov     qword ptr [rax+0A8h], 0
0x1800a6a85  mov     qword ptr [rax+0B0h], 0
0x1800a6a90  mov     qword ptr [rax+0B8h], 0
0x1800a6a9b  mov     qword ptr [rax+0C0h], 0
0x1800a6aa6  mov     qword ptr [rax+0C8h], 0
0x1800a6ab1  mov     qword ptr [rax+0D0h], 0
0x1800a6abc  jmp     short loc_1800A6ACC
0x1800a6abe  mov     rax, [rcx+0A8h]
0x1800a6ac5  xor     ebx, ebx
0x1800a6ac7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a6acc  mov     eax, ebx
0x1800a6ace  mov     rbx, [rsp+28h+arg_0]
0x1800a6ad3  add     rsp, 20h
0x1800a6ad7  pop     rdi
0x1800a6ad8  retn
```
