# CPL_LoadCPLModule(ushort const *,int)

- ea: `0x18016674c`
- end: `0x1801669ee`
- name: `?CPL_LoadCPLModule@@YAPEAUCPLMODULE@@PEBGH@Z`
- size: `674`
- prototype: `struct CPLMODULE *__fastcall(const unsigned __int16 *, int)`
- caller_count: `3`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, loader_planting`

## callers

- `0x180276700`
- `0x18036cb34`
- `0x18037943c`

## callees

- `0x18003eab0`
- `0x18016674c`
- `0x1801669f4`
- `0x180166bb8`
- `0x1801d89d4`
- `0x180233280`
- `0x18036cc80`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801669ba`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801669ba`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1801667b0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1801667b0`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18016697d`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18016697d`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180166963`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180166963`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x1801668b1`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x1801668b1`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1801667c4`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1801667c4`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x1801667ff`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x1801667ff`
- `api-ms-win-core-sidebyside-l1-1-0!DeactivateActCtx` at `0x1801668d4`
- `api-ms-win-core-sidebyside-l1-1-0!DeactivateActCtx` at `0x18016698e`
- `api-ms-win-core-sidebyside-l1-1-0!DeactivateActCtx` at `0x1801668d4`
- `api-ms-win-core-sidebyside-l1-1-0!DeactivateActCtx` at `0x18016698e`
- `api-ms-win-core-sidebyside-l1-1-0!ActivateActCtx` at `0x180166891`
- `api-ms-win-core-sidebyside-l1-1-0!ActivateActCtx` at `0x180166972`
- `api-ms-win-core-sidebyside-l1-1-0!ActivateActCtx` at `0x180166891`
- `api-ms-win-core-sidebyside-l1-1-0!ActivateActCtx` at `0x180166972`
- `api-ms-win-core-sidebyside-l1-1-0!ReleaseActCtx` at `0x1801668ec`
- `api-ms-win-core-sidebyside-l1-1-0!ReleaseActCtx` at `0x1801668fa`
- `api-ms-win-core-sidebyside-l1-1-0!ReleaseActCtx` at `0x1801669a1`
- `api-ms-win-core-sidebyside-l1-1-0!ReleaseActCtx` at `0x1801669af`
- `api-ms-win-core-sidebyside-l1-1-0!ReleaseActCtx` at `0x1801668ec`
- `api-ms-win-core-sidebyside-l1-1-0!ReleaseActCtx` at `0x1801668fa`
- `api-ms-win-core-sidebyside-l1-1-0!ReleaseActCtx` at `0x1801669a1`
- `api-ms-win-core-sidebyside-l1-1-0!ReleaseActCtx` at `0x1801669af`
- `api-ms-win-core-sidebyside-l1-1-0!CreateActCtxW` at `0x180166833`
- `api-ms-win-core-sidebyside-l1-1-0!CreateActCtxW` at `0x180166850`
- `api-ms-win-core-sidebyside-l1-1-0!CreateActCtxW` at `0x180166869`
- `api-ms-win-core-sidebyside-l1-1-0!CreateActCtxW` at `0x180166833`
- `api-ms-win-core-sidebyside-l1-1-0!CreateActCtxW` at `0x180166850`
- `api-ms-win-core-sidebyside-l1-1-0!CreateActCtxW` at `0x180166869`
- `apphelp!ApphelpCheckExe` at `0x1801668a4`
- `apphelp!ApphelpCheckExe` at `0x1801668a4`

## string_xrefs

- `0x180166781`: `%s.manifest`

## pseudocode

```c
struct CPLMODULE *__fastcall CPL_LoadCPLModule(const unsigned __int16 *a1, unsigned int a2)
{
  struct CPLMODULE *v4; // rsi
  HANDLE v5; // rax
  HANDLE v6; // rdi
  void *v7; // rbx
  void *v8; // rdi
  HMODULE LibraryW; // r14
  HANDLE v10; // rcx
  struct CPLMODULE *v11; // rax
  void *CplInitEvent; // rax
  int v14; // [rsp+30h] [rbp-D0h] BYREF
  HMODULE hLibModule; // [rsp+38h] [rbp-C8h] BYREF
  __int64 CurrentProcessId; // [rsp+40h] [rbp-C0h]
  HANDLE hObject; // [rsp+48h] [rbp-B8h]
  ACTCTXW pActCtx; // [rsp+50h] [rbp-B0h] BYREF
  ULONG_PTR Cookie; // [rsp+88h] [rbp-78h] BYREF
  WCHAR pszPath[264]; // [rsp+90h] [rbp-70h] BYREF

  v4 = 0;
  if ( (int)StringCchPrintfW(pszPath, 0x104u, L"%s.manifest", a1) < 0 )
    return v4;
  hLibModule = 0;
  CurrentProcessId = GetCurrentProcessId();
  hObject = OpenProcess(0x100000u, 0, CurrentProcessId);
  if ( !hObject )
    return v4;
  memset(&pActCtx, 0, sizeof(pActCtx));
  pActCtx.cbSize = 56;
  if ( PathFileExistsW(pszPath) )
  {
    pActCtx.dwFlags = 0;
    pActCtx.lpSource = pszPath;
  }
  else
  {
    pActCtx.dwFlags = 8;
    pActCtx.lpSource = a1;
    pActCtx.lpResourceName = (LPCWSTR)123;
    v5 = CreateActCtxW(&pActCtx);
    v6 = v5;
    if ( v5 != (HANDLE)-1LL )
      goto LABEL_9;
    pActCtx.lpResourceName = (LPCWSTR)124;
    v5 = CreateActCtxW(&pActCtx);
    if ( v5 != (HANDLE)-1LL )
      goto LABEL_9;
    pActCtx.lpResourceName = (LPCWSTR)2;
  }
  v5 = CreateActCtxW(&pActCtx);
  v6 = v5;
LABEL_9:
  v7 = 0;
  Cookie = 0;
  if ( v6 != (HANDLE)-1LL )
    v7 = v6;
  v8 = 0;
  if ( v5 != (HANDLE)-1LL )
    v8 = v5;
  ActivateActCtx(v7, &Cookie);
  if ( (unsigned int)ApphelpCheckExe(a1, a2, 1) )
  {
    LibraryW = LoadLibraryW(a1);
    hLibModule = LibraryW;
  }
  else
  {
    LibraryW = 0;
    hLibModule = 0;
  }
  if ( Cookie )
    DeactivateActCtx(0, Cookie);
  if ( !LibraryW )
  {
    if ( v8 && v8 != v7 )
      ReleaseActCtx(v8);
    if ( v7 )
      ReleaseActCtx(v7);
    v10 = hObject;
LABEL_39:
    CloseHandle(v10);
    return v4;
  }
  v14 = 0;
  v11 = _FindOrAddCPLModuleInList((const struct MINST *)&hLibModule, a1, 1, v7, v8, &v14);
  v4 = v11;
  if ( !v11 || !v14 )
  {
    ActivateActCtx(v7, &Cookie);
    FreeLibrary(hLibModule);
    if ( Cookie )
      DeactivateActCtx(0, Cookie);
    if ( v8 && v8 != v7 )
      ReleaseActCtx(v8);
    if ( v7 )
      ReleaseActCtx(v7);
    v10 = hObject;
    goto LABEL_39;
  }
  if ( !(unsigned int)_InitializeCPLModule(v11) )
  {
    CPL_ReleaseModuleReference(v4);
    v4 = 0;
  }
  CplInitEvent = _GetCplInitEvent();
  if ( CplInitEvent )
    SetEvent(CplInitEvent);
  return v4;
}

```

## disassembly

```asm
0x18016674c  mov     [rsp-8+arg_10], rbx
0x180166751  mov     [rsp-8+arg_18], rsi
0x180166756  push    rbp
0x180166757  push    rdi
0x180166758  push    r12
0x18016675a  push    r14
0x18016675c  push    r15
0x18016675e  lea     rbp, [rsp-1B0h]
0x180166766  sub     rsp, 2B0h
0x18016676d  mov     rax, cs:__security_cookie
0x180166774  xor     rax, rsp
0x180166777  mov     [rbp+1D0h+var_30], rax
0x18016677e  mov     r14d, edx
0x180166781  lea     r8, aSManifest; "%s.manifest"
0x180166788  mov     r15, rcx
0x18016678b  mov     r9, rcx
0x18016678e  mov     edx, 104h; unsigned __int64
0x180166793  lea     rcx, [rbp+1D0h+pszPath]; unsigned __int16 *
0x180166797  xor     esi, esi
0x180166799  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18016679e  test    eax, eax
0x1801667a0  js      loc_1801669C0
0x1801667a6  mov     [rsp+2D0h+hLibModule], rsi
0x1801667ab  mov     [rsp+2D0h+var_290], rsi
0x1801667b0  call    cs:__imp_GetCurrentProcessId
0x1801667b6  xor     edx, edx; bInheritHandle
0x1801667b8  mov     ecx, 100000h; dwDesiredAccess
0x1801667bd  mov     r8d, eax; dwProcessId
0x1801667c0  mov     dword ptr [rsp+2D0h+var_290], eax
0x1801667c4  call    cs:__imp_OpenProcess
0x1801667ca  mov     [rsp+2D0h+hObject], rax
0x1801667cf  mov     r12, rax
0x1801667d2  test    rax, rax
0x1801667d5  jz      loc_1801669C0
0x1801667db  xorps   xmm0, xmm0
0x1801667de  lea     rcx, [rbp+1D0h+pszPath]; pszPath
0x1801667e2  xor     eax, eax
0x1801667e4  movups  xmmword ptr [rsp+2D0h+pActCtx.cbSize], xmm0
0x1801667e9  mov     [rsp+2D0h+pActCtx.cbSize], 38h ; '8'
0x1801667f1  movups  xmmword ptr [rsp+2D0h+pActCtx.wProcessorArchitecture], xmm0
0x1801667f6  mov     [rbp+1D0h+pActCtx.hModule], rax
0x1801667fa  movups  xmmword ptr [rsp+2D0h+pActCtx.lpResourceName], xmm0
0x1801667ff  call    cs:__imp_PathFileExistsW
0x180166805  lea     rcx, [rsp+2D0h+pActCtx]; pActCtx
0x18016680a  test    eax, eax
0x18016680c  jz      short loc_18016681D
0x18016680e  lea     rax, [rbp+1D0h+pszPath]
0x180166812  mov     [rsp+2D0h+pActCtx.dwFlags], esi
0x180166816  mov     [rsp+2D0h+pActCtx.lpSource], rax
0x18016681b  jmp     short loc_180166869
0x18016681d  mov     [rsp+2D0h+pActCtx.dwFlags], 8
0x180166825  mov     [rsp+2D0h+pActCtx.lpSource], r15
0x18016682a  mov     [rsp+2D0h+pActCtx.lpResourceName], 7Bh ; '{'
0x180166833  call    cs:__imp_CreateActCtxW
0x180166839  mov     rdi, rax
0x18016683c  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180166840  jnz     short loc_180166872
0x180166842  lea     rcx, [rsp+2D0h+pActCtx]; pActCtx
0x180166847  mov     [rsp+2D0h+pActCtx.lpResourceName], 7Ch ; '|'
0x180166850  call    cs:__imp_CreateActCtxW
0x180166856  cmp     rax, rdi
0x180166859  jnz     short loc_180166872
0x18016685b  mov     [rsp+2D0h+pActCtx.lpResourceName], 2
0x180166864  lea     rcx, [rsp+2D0h+pActCtx]; pActCtx
0x180166869  call    cs:__imp_CreateActCtxW
0x18016686f  mov     rdi, rax
0x180166872  xor     ebx, ebx
0x180166874  mov     [rbp+1D0h+Cookie], rsi
0x180166878  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x18016687c  lea     rdx, [rbp+1D0h+Cookie]; lpCookie
0x180166880  cmovnz  rbx, rdi
0x180166884  xor     edi, edi
0x180166886  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18016688a  mov     rcx, rbx; hActCtx
0x18016688d  cmovnz  rdi, rax
0x180166891  call    cs:__imp_ActivateActCtx
0x180166897  xor     r9d, r9d
0x18016689a  mov     edx, r14d
0x18016689d  mov     rcx, r15
0x1801668a0  lea     r8d, [r9+1]
0x1801668a4  call    cs:__imp_ApphelpCheckExe
0x1801668aa  test    eax, eax
0x1801668ac  jz      short loc_1801668C1
0x1801668ae  mov     rcx, r15; lpLibFileName
0x1801668b1  call    cs:__imp_LoadLibraryW
0x1801668b7  mov     r14, rax
0x1801668ba  mov     [rsp+2D0h+hLibModule], rax
0x1801668bf  jmp     short loc_1801668C9
0x1801668c1  xor     r14d, r14d
0x1801668c4  mov     [rsp+2D0h+hLibModule], r14
0x1801668c9  mov     rdx, [rbp+1D0h+Cookie]; ulCookie
0x1801668cd  test    rdx, rdx
0x1801668d0  jz      short loc_1801668DA
0x1801668d2  xor     ecx, ecx; dwFlags
0x1801668d4  call    cs:__imp_DeactivateActCtx
0x1801668da  test    r14, r14
0x1801668dd  jnz     short loc_180166908
0x1801668df  test    rdi, rdi
0x1801668e2  jz      short loc_1801668F2
0x1801668e4  cmp     rdi, rbx
0x1801668e7  jz      short loc_1801668F2
0x1801668e9  mov     rcx, rdi; hActCtx
0x1801668ec  call    cs:__imp_ReleaseActCtx
0x1801668f2  test    rbx, rbx
0x1801668f5  jz      short loc_180166900
0x1801668f7  mov     rcx, rbx; hActCtx
0x1801668fa  call    cs:__imp_ReleaseActCtx
0x180166900  mov     rcx, r12
0x180166903  jmp     loc_1801669BA
0x180166908  lea     rax, [rsp+2D0h+var_2A0]
0x18016690d  mov     [rsp+2D0h+var_2A0], esi
0x180166911  mov     [rsp+2D0h+var_2A8], rax; int *
0x180166916  lea     rcx, [rsp+2D0h+hLibModule]; struct MINST *
0x18016691b  mov     r9, rbx; void *
0x18016691e  mov     [rsp+2D0h+var_2B0], rdi; void *
0x180166923  mov     r8d, 1; int
0x180166929  mov     rdx, r15; unsigned __int16 *
0x18016692c  call    ?_FindOrAddCPLModuleInList@@YAPEAUCPLMODULE@@PEBUMINST@@PEBGHPEAX2PEAH@Z; _FindOrAddCPLModuleInList(MINST const *,ushort const *,int,void *,void *,int *)
0x180166931  mov     rsi, rax
0x180166934  test    rax, rax
0x180166937  jz      short loc_18016696B
0x180166939  cmp     [rsp+2D0h+var_2A0], 0
0x18016693e  jz      short loc_18016696B
0x180166940  mov     rcx, rax; struct CPLMODULE *
0x180166943  call    ?_InitializeCPLModule@@YAHPEAUCPLMODULE@@@Z; _InitializeCPLModule(CPLMODULE *)
0x180166948  test    eax, eax
0x18016694a  jnz     short loc_180166956
0x18016694c  mov     rcx, rsi; struct CPLMODULE *
0x18016694f  call    ?CPL_ReleaseModuleReference@@YAXPEAUCPLMODULE@@@Z; CPL_ReleaseModuleReference(CPLMODULE *)
0x180166954  xor     esi, esi
0x180166956  call    ?_GetCplInitEvent@@YAPEAXXZ; _GetCplInitEvent(void)
0x18016695b  test    rax, rax
0x18016695e  jz      short loc_1801669C0
0x180166960  mov     rcx, rax; hEvent
0x180166963  call    cs:__imp_SetEvent
0x180166969  jmp     short loc_1801669C0
0x18016696b  lea     rdx, [rbp+1D0h+Cookie]; lpCookie
0x18016696f  mov     rcx, rbx; hActCtx
0x180166972  call    cs:__imp_ActivateActCtx
0x180166978  mov     rcx, [rsp+2D0h+hLibModule]; hLibModule
0x18016697d  call    cs:__imp_FreeLibrary
0x180166983  mov     rdx, [rbp+1D0h+Cookie]; ulCookie
0x180166987  test    rdx, rdx
0x18016698a  jz      short loc_180166994
0x18016698c  xor     ecx, ecx; dwFlags
0x18016698e  call    cs:__imp_DeactivateActCtx
0x180166994  test    rdi, rdi
0x180166997  jz      short loc_1801669A7
0x180166999  cmp     rdi, rbx
0x18016699c  jz      short loc_1801669A7
0x18016699e  mov     rcx, rdi; hActCtx
0x1801669a1  call    cs:__imp_ReleaseActCtx
0x1801669a7  test    rbx, rbx
0x1801669aa  jz      short loc_1801669B5
0x1801669ac  mov     rcx, rbx; hActCtx
0x1801669af  call    cs:__imp_ReleaseActCtx
0x1801669b5  mov     rcx, [rsp+2D0h+hObject]; hObject
0x1801669ba  call    cs:__imp_CloseHandle
0x1801669c0  mov     rax, rsi
0x1801669c3  mov     rcx, [rbp+1D0h+var_30]
0x1801669ca  xor     rcx, rsp; StackCookie
0x1801669cd  call    __security_check_cookie
0x1801669d2  lea     r11, [rsp+2D0h+var_20]
0x1801669da  mov     rbx, [r11+40h]
0x1801669de  mov     rsi, [r11+48h]
0x1801669e2  mov     rsp, r11
0x1801669e5  pop     r15
0x1801669e7  pop     r14
0x1801669e9  pop     r12
0x1801669eb  pop     rdi
0x1801669ec  pop     rbp
0x1801669ed  retn
```
