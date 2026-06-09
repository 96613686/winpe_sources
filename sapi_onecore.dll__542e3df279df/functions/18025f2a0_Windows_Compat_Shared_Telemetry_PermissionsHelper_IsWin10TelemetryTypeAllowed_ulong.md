# Windows::Compat::Shared::Telemetry::PermissionsHelper::IsWin10TelemetryTypeAllowed(ulong)

- ea: `0x18025f2a0`
- end: `0x18025f3a5`
- name: `?IsWin10TelemetryTypeAllowed@PermissionsHelper@Telemetry@Shared@Compat@Windows@@CA_NK@Z`
- size: `261`
- prototype: `bool __fastcall(unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18025f7b0`

## callees

- `0x18025f2a0`
- `0x18028b010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18025f2bf`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18025f30b`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18025f2bf`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18025f30b`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18025f377`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18025f385`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18025f393`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18025f377`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18025f385`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18025f393`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18025f2d7`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18025f323`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18025f34d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18025f2d7`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18025f323`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18025f34d`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18025f335`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18025f335`

## pseudocode

```c
bool __fastcall Windows::Compat::Shared::Telemetry::PermissionsHelper::IsWin10TelemetryTypeAllowed(int a1)
{
  HMODULE v1; // rbx
  HMODULE Library; // rax
  HMODULE v3; // rsi
  FARPROC ProcAddress; // rax
  int v5; // eax
  HMODULE v6; // rdi
  bool v7; // bp
  HMODULE v8; // rax
  FARPROC v9; // rax
  HMODULE LibraryW; // rax
  int v12; // [rsp+50h] [rbp+8h] BYREF

  v12 = a1;
  v1 = 0;
  Library = LoadLibraryExW(L"DiagnosticDataSettings", 0, 0x800u);
  v3 = Library;
  if ( Library )
  {
    ProcAddress = GetProcAddress(Library, "TelIsTelemetryTypeAllowed");
    if ( ProcAddress )
    {
      v5 = ((__int64 (__fastcall *)(__int64))ProcAddress)(1);
      if ( v5 >= 0 )
      {
        v6 = 0;
        v7 = v5 == 0;
LABEL_12:
        FreeLibrary(v3);
        goto LABEL_13;
      }
    }
  }
  v12 = 0;
  v7 = 0;
  v8 = LoadLibraryExW(L"Aepic", 0, 0x800u);
  v6 = v8;
  if ( v8 && (v9 = GetProcAddress(v8, "GetPrivacyLevel")) != 0
    || (LibraryW = LoadLibraryW(L"Devinv"), (v1 = LibraryW) != 0)
    && (v9 = GetProcAddress(LibraryW, "GetPrivacyLevel")) != 0 )
  {
    if ( ((int (__fastcall *)(int *))v9)(&v12) >= 0 )
      v7 = v12 != 0;
  }
  if ( v3 )
    goto LABEL_12;
LABEL_13:
  if ( v6 )
    FreeLibrary(v6);
  if ( v1 )
    FreeLibrary(v1);
  return v7;
}

```

## disassembly

```asm
0x18025f2a0  mov     [rsp+arg_0], ecx
0x18025f2a4  push    rbx
0x18025f2a5  push    rbp
0x18025f2a6  push    rsi
0x18025f2a7  push    rdi
0x18025f2a8  sub     rsp, 28h
0x18025f2ac  mov     edi, 800h
0x18025f2b1  lea     rcx, aDiagnosticdata; "DiagnosticDataSettings"
0x18025f2b8  mov     r8d, edi; dwFlags
0x18025f2bb  xor     edx, edx; hFile
0x18025f2bd  xor     ebx, ebx
0x18025f2bf  call    cs:__imp_LoadLibraryExW
0x18025f2c5  mov     rsi, rax
0x18025f2c8  test    rax, rax
0x18025f2cb  jz      short loc_18025F2F8
0x18025f2cd  lea     rdx, aTelistelemetry; "TelIsTelemetryTypeAllowed"
0x18025f2d4  mov     rcx, rax; hModule
0x18025f2d7  call    cs:__imp_GetProcAddress
0x18025f2dd  test    rax, rax
0x18025f2e0  jz      short loc_18025F2F8
0x18025f2e2  lea     ecx, [rbx+1]
0x18025f2e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18025f2ea  test    eax, eax
0x18025f2ec  js      short loc_18025F2F8
0x18025f2ee  xor     edi, edi
0x18025f2f0  test    eax, eax
0x18025f2f2  setz    bpl
0x18025f2f6  jmp     short loc_18025F374
0x18025f2f8  mov     r8d, edi; dwFlags
0x18025f2fb  mov     [rsp+48h+arg_0], ebx
0x18025f2ff  xor     edx, edx; hFile
0x18025f301  lea     rcx, aAepic; "Aepic"
0x18025f308  xor     bpl, bpl
0x18025f30b  call    cs:__imp_LoadLibraryExW
0x18025f311  mov     rdi, rax
0x18025f314  test    rax, rax
0x18025f317  jz      short loc_18025F32E
0x18025f319  lea     rdx, aGetprivacyleve; "GetPrivacyLevel"
0x18025f320  mov     rcx, rax; hModule
0x18025f323  call    cs:__imp_GetProcAddress
0x18025f329  test    rax, rax
0x18025f32c  jnz     short loc_18025F358
0x18025f32e  lea     rcx, aDevinv; "Devinv"
0x18025f335  call    cs:__imp_LoadLibraryW
0x18025f33b  mov     rbx, rax
0x18025f33e  test    rax, rax
0x18025f341  jz      short loc_18025F36F
0x18025f343  lea     rdx, aGetprivacyleve; "GetPrivacyLevel"
0x18025f34a  mov     rcx, rax; hModule
0x18025f34d  call    cs:__imp_GetProcAddress
0x18025f353  test    rax, rax
0x18025f356  jz      short loc_18025F36F
0x18025f358  lea     rcx, [rsp+48h+arg_0]
0x18025f35d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18025f362  test    eax, eax
0x18025f364  js      short loc_18025F36F
0x18025f366  cmp     [rsp+48h+arg_0], 1
0x18025f36b  setnb   bpl
0x18025f36f  test    rsi, rsi
0x18025f372  jz      short loc_18025F37D
0x18025f374  mov     rcx, rsi; hLibModule
0x18025f377  call    cs:__imp_FreeLibrary
0x18025f37d  test    rdi, rdi
0x18025f380  jz      short loc_18025F38B
0x18025f382  mov     rcx, rdi; hLibModule
0x18025f385  call    cs:__imp_FreeLibrary
0x18025f38b  test    rbx, rbx
0x18025f38e  jz      short loc_18025F399
0x18025f390  mov     rcx, rbx; hLibModule
0x18025f393  call    cs:__imp_FreeLibrary
0x18025f399  mov     al, bpl
0x18025f39c  add     rsp, 28h
0x18025f3a0  pop     rdi
0x18025f3a1  pop     rsi
0x18025f3a2  pop     rbp
0x18025f3a3  pop     rbx
0x18025f3a4  retn
```
