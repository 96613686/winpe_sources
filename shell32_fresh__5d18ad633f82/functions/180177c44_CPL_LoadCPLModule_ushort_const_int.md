# CPL_LoadCPLModule(ushort const *,int)

- ea: `0x180177c44`
- end: `0x180177f5d`
- name: `?CPL_LoadCPLModule@@YAPEAUCPLMODULE@@PEBGH@Z`
- size: `793`
- prototype: `struct CPLMODULE *__fastcall(const unsigned __int16 *, int)`
- caller_count: `3`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, loader_planting`

## callers

- `0x180290050`
- `0x180391c04`
- `0x18039e8d0`

## callees

- `0x18003a3e0`
- `0x180177c44`
- `0x180177f64`
- `0x180178158`
- `0x1801efab8`
- `0x180249490`
- `0x1803916e4`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180177f22`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180177f22`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180177ca8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180177ca8`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180177ecd`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180177ecd`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180177ea7`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180177ea7`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x180177dd9`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x180177dd9`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180177cc2`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180177cc2`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x180177d03`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x180177d03`
- `api-ms-win-core-sidebyside-l1-1-0!ReleaseActCtx` at `0x180177e20`
- `api-ms-win-core-sidebyside-l1-1-0!ReleaseActCtx` at `0x180177e34`
- `api-ms-win-core-sidebyside-l1-1-0!ReleaseActCtx` at `0x180177efd`
- `api-ms-win-core-sidebyside-l1-1-0!ReleaseActCtx` at `0x180177f11`
- `api-ms-win-core-sidebyside-l1-1-0!ReleaseActCtx` at `0x180177e20`
- `api-ms-win-core-sidebyside-l1-1-0!ReleaseActCtx` at `0x180177e34`
- `api-ms-win-core-sidebyside-l1-1-0!ReleaseActCtx` at `0x180177efd`
- `api-ms-win-core-sidebyside-l1-1-0!ReleaseActCtx` at `0x180177f11`
- `api-ms-win-core-sidebyside-l1-1-0!DeactivateActCtx` at `0x180177e02`
- `api-ms-win-core-sidebyside-l1-1-0!DeactivateActCtx` at `0x180177ee4`
- `api-ms-win-core-sidebyside-l1-1-0!DeactivateActCtx` at `0x180177e02`
- `api-ms-win-core-sidebyside-l1-1-0!DeactivateActCtx` at `0x180177ee4`
- `api-ms-win-core-sidebyside-l1-1-0!CreateActCtxW` at `0x180177d3d`
- `api-ms-win-core-sidebyside-l1-1-0!CreateActCtxW` at `0x180177d60`
- `api-ms-win-core-sidebyside-l1-1-0!CreateActCtxW` at `0x180177d7f`
- `api-ms-win-core-sidebyside-l1-1-0!CreateActCtxW` at `0x180177d3d`
- `api-ms-win-core-sidebyside-l1-1-0!CreateActCtxW` at `0x180177d60`
- `api-ms-win-core-sidebyside-l1-1-0!CreateActCtxW` at `0x180177d7f`
- `api-ms-win-core-sidebyside-l1-1-0!ActivateActCtx` at `0x180177dad`
- `api-ms-win-core-sidebyside-l1-1-0!ActivateActCtx` at `0x180177ebc`
- `api-ms-win-core-sidebyside-l1-1-0!ActivateActCtx` at `0x180177dad`
- `api-ms-win-core-sidebyside-l1-1-0!ActivateActCtx` at `0x180177ebc`
- `apphelp!ApphelpCheckExe` at `0x180177dc6`
- `apphelp!ApphelpCheckExe` at `0x180177dc6`

## string_xrefs

- `0x180177c79`: `%s.manifest`

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
0x180177c44  mov     [rsp-8+arg_10], rbx
0x180177c49  mov     [rsp-8+arg_18], rsi
0x180177c4e  push    rbp
0x180177c4f  push    rdi
0x180177c50  push    r12
0x180177c52  push    r14
0x180177c54  push    r15
0x180177c56  lea     rbp, [rsp-1B0h]
0x180177c5e  sub     rsp, 2B0h
0x180177c65  mov     rax, cs:__security_cookie
0x180177c6c  xor     rax, rsp
0x180177c6f  mov     [rbp+1D0h+var_30], rax
0x180177c76  mov     r14d, edx
0x180177c79  lea     r8, aSManifest; "%s.manifest"
0x180177c80  mov     r15, rcx
0x180177c83  mov     r9, rcx
0x180177c86  mov     edx, 104h; unsigned __int64
0x180177c8b  lea     rcx, [rbp+1D0h+pszPath]; unsigned __int16 *
0x180177c8f  xor     esi, esi
0x180177c91  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180177c96  test    eax, eax
0x180177c98  js      loc_180177F2E
0x180177c9e  mov     [rsp+2D0h+hLibModule], rsi
0x180177ca3  mov     [rsp+2D0h+var_290], rsi
0x180177ca8  call    cs:__imp_GetCurrentProcessId
0x180177caf  nop     dword ptr [rax+rax+00h]
0x180177cb4  xor     edx, edx; bInheritHandle
0x180177cb6  mov     ecx, 100000h; dwDesiredAccess
0x180177cbb  mov     r8d, eax; dwProcessId
0x180177cbe  mov     dword ptr [rsp+2D0h+var_290], eax
0x180177cc2  call    cs:__imp_OpenProcess
0x180177cc9  nop     dword ptr [rax+rax+00h]
0x180177cce  mov     [rsp+2D0h+hObject], rax
0x180177cd3  mov     r12, rax
0x180177cd6  test    rax, rax
0x180177cd9  jz      loc_180177F2E
0x180177cdf  xorps   xmm0, xmm0
0x180177ce2  lea     rcx, [rbp+1D0h+pszPath]; pszPath
0x180177ce6  xor     eax, eax
0x180177ce8  movups  xmmword ptr [rsp+2D0h+pActCtx.cbSize], xmm0
0x180177ced  mov     [rsp+2D0h+pActCtx.cbSize], 38h ; '8'
0x180177cf5  movups  xmmword ptr [rsp+2D0h+pActCtx.wProcessorArchitecture], xmm0
0x180177cfa  mov     [rbp+1D0h+pActCtx.hModule], rax
0x180177cfe  movups  xmmword ptr [rsp+2D0h+pActCtx.lpResourceName], xmm0
0x180177d03  call    cs:__imp_PathFileExistsW
0x180177d0a  nop     dword ptr [rax+rax+00h]
0x180177d0f  lea     rcx, [rsp+2D0h+pActCtx]; pActCtx
0x180177d14  test    eax, eax
0x180177d16  jz      short loc_180177D27
0x180177d18  lea     rax, [rbp+1D0h+pszPath]
0x180177d1c  mov     [rsp+2D0h+pActCtx.dwFlags], esi
0x180177d20  mov     [rsp+2D0h+pActCtx.lpSource], rax
0x180177d25  jmp     short loc_180177D7F
0x180177d27  mov     [rsp+2D0h+pActCtx.dwFlags], 8
0x180177d2f  mov     [rsp+2D0h+pActCtx.lpSource], r15
0x180177d34  mov     [rsp+2D0h+pActCtx.lpResourceName], 7Bh ; '{'
0x180177d3d  call    cs:__imp_CreateActCtxW
0x180177d44  nop     dword ptr [rax+rax+00h]
0x180177d49  mov     rdi, rax
0x180177d4c  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180177d50  jnz     short loc_180177D8E
0x180177d52  lea     rcx, [rsp+2D0h+pActCtx]; pActCtx
0x180177d57  mov     [rsp+2D0h+pActCtx.lpResourceName], 7Ch ; '|'
0x180177d60  call    cs:__imp_CreateActCtxW
0x180177d67  nop     dword ptr [rax+rax+00h]
0x180177d6c  cmp     rax, rdi
0x180177d6f  jnz     short loc_180177D8E
0x180177d71  mov     [rsp+2D0h+pActCtx.lpResourceName], 2
0x180177d7a  lea     rcx, [rsp+2D0h+pActCtx]; pActCtx
0x180177d7f  call    cs:__imp_CreateActCtxW
0x180177d86  nop     dword ptr [rax+rax+00h]
0x180177d8b  mov     rdi, rax
0x180177d8e  xor     ebx, ebx
0x180177d90  mov     [rbp+1D0h+Cookie], rsi
0x180177d94  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x180177d98  lea     rdx, [rbp+1D0h+Cookie]; lpCookie
0x180177d9c  cmovnz  rbx, rdi
0x180177da0  xor     edi, edi
0x180177da2  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180177da6  mov     rcx, rbx; hActCtx
0x180177da9  cmovnz  rdi, rax
0x180177dad  call    cs:__imp_ActivateActCtx
0x180177db4  nop     dword ptr [rax+rax+00h]
0x180177db9  xor     r9d, r9d
0x180177dbc  mov     edx, r14d
0x180177dbf  mov     rcx, r15
0x180177dc2  lea     r8d, [r9+1]
0x180177dc6  call    cs:__imp_ApphelpCheckExe
0x180177dcd  nop     dword ptr [rax+rax+00h]
0x180177dd2  test    eax, eax
0x180177dd4  jz      short loc_180177DEF
0x180177dd6  mov     rcx, r15; lpLibFileName
0x180177dd9  call    cs:__imp_LoadLibraryW
0x180177de0  nop     dword ptr [rax+rax+00h]
0x180177de5  mov     r14, rax
0x180177de8  mov     [rsp+2D0h+hLibModule], rax
0x180177ded  jmp     short loc_180177DF7
0x180177def  xor     r14d, r14d
0x180177df2  mov     [rsp+2D0h+hLibModule], r14
0x180177df7  mov     rdx, [rbp+1D0h+Cookie]; ulCookie
0x180177dfb  test    rdx, rdx
0x180177dfe  jz      short loc_180177E0E
0x180177e00  xor     ecx, ecx; dwFlags
0x180177e02  call    cs:__imp_DeactivateActCtx
0x180177e09  nop     dword ptr [rax+rax+00h]
0x180177e0e  test    r14, r14
0x180177e11  jnz     short loc_180177E48
0x180177e13  test    rdi, rdi
0x180177e16  jz      short loc_180177E2C
0x180177e18  cmp     rdi, rbx
0x180177e1b  jz      short loc_180177E2C
0x180177e1d  mov     rcx, rdi; hActCtx
0x180177e20  call    cs:__imp_ReleaseActCtx
0x180177e27  nop     dword ptr [rax+rax+00h]
0x180177e2c  test    rbx, rbx
0x180177e2f  jz      short loc_180177E40
0x180177e31  mov     rcx, rbx; hActCtx
0x180177e34  call    cs:__imp_ReleaseActCtx
0x180177e3b  nop     dword ptr [rax+rax+00h]
0x180177e40  mov     rcx, r12
0x180177e43  jmp     loc_180177F22
0x180177e48  lea     rax, [rsp+2D0h+var_2A0]
0x180177e4d  mov     [rsp+2D0h+var_2A0], esi
0x180177e51  mov     [rsp+2D0h+var_2A8], rax; int *
0x180177e56  lea     rcx, [rsp+2D0h+hLibModule]; struct MINST *
0x180177e5b  mov     r9, rbx; void *
0x180177e5e  mov     [rsp+2D0h+var_2B0], rdi; void *
0x180177e63  mov     r8d, 1; int
0x180177e69  mov     rdx, r15; unsigned __int16 *
0x180177e6c  call    ?_FindOrAddCPLModuleInList@@YAPEAUCPLMODULE@@PEBUMINST@@PEBGHPEAX2PEAH@Z; _FindOrAddCPLModuleInList(MINST const *,ushort const *,int,void *,void *,int *)
0x180177e71  mov     rsi, rax
0x180177e74  test    rax, rax
0x180177e77  jz      short loc_180177EB5
0x180177e79  cmp     [rsp+2D0h+var_2A0], 0
0x180177e7e  jz      short loc_180177EB5
0x180177e80  mov     rcx, rax; struct CPLMODULE *
0x180177e83  call    ?_InitializeCPLModule@@YAHPEAUCPLMODULE@@@Z; _InitializeCPLModule(CPLMODULE *)
0x180177e88  test    eax, eax
0x180177e8a  jnz     short loc_180177E96
0x180177e8c  mov     rcx, rsi; struct CPLMODULE *
0x180177e8f  call    ?CPL_ReleaseModuleReference@@YAXPEAUCPLMODULE@@@Z; CPL_ReleaseModuleReference(CPLMODULE *)
0x180177e94  xor     esi, esi
0x180177e96  call    ?_GetCplInitEvent@@YAPEAXXZ; _GetCplInitEvent(void)
0x180177e9b  test    rax, rax
0x180177e9e  jz      loc_180177F2E
0x180177ea4  mov     rcx, rax; hEvent
0x180177ea7  call    cs:__imp_SetEvent
0x180177eae  nop     dword ptr [rax+rax+00h]
0x180177eb3  jmp     short loc_180177F2E
0x180177eb5  lea     rdx, [rbp+1D0h+Cookie]; lpCookie
0x180177eb9  mov     rcx, rbx; hActCtx
0x180177ebc  call    cs:__imp_ActivateActCtx
0x180177ec3  nop     dword ptr [rax+rax+00h]
0x180177ec8  mov     rcx, [rsp+2D0h+hLibModule]; hLibModule
0x180177ecd  call    cs:__imp_FreeLibrary
0x180177ed4  nop     dword ptr [rax+rax+00h]
0x180177ed9  mov     rdx, [rbp+1D0h+Cookie]; ulCookie
0x180177edd  test    rdx, rdx
0x180177ee0  jz      short loc_180177EF0
0x180177ee2  xor     ecx, ecx; dwFlags
0x180177ee4  call    cs:__imp_DeactivateActCtx
0x180177eeb  nop     dword ptr [rax+rax+00h]
0x180177ef0  test    rdi, rdi
0x180177ef3  jz      short loc_180177F09
0x180177ef5  cmp     rdi, rbx
0x180177ef8  jz      short loc_180177F09
0x180177efa  mov     rcx, rdi; hActCtx
0x180177efd  call    cs:__imp_ReleaseActCtx
0x180177f04  nop     dword ptr [rax+rax+00h]
0x180177f09  test    rbx, rbx
0x180177f0c  jz      short loc_180177F1D
0x180177f0e  mov     rcx, rbx; hActCtx
0x180177f11  call    cs:__imp_ReleaseActCtx
0x180177f18  nop     dword ptr [rax+rax+00h]
0x180177f1d  mov     rcx, [rsp+2D0h+hObject]; hObject
0x180177f22  call    cs:__imp_CloseHandle
0x180177f29  nop     dword ptr [rax+rax+00h]
0x180177f2e  mov     rax, rsi
0x180177f31  mov     rcx, [rbp+1D0h+var_30]
0x180177f38  xor     rcx, rsp; StackCookie
0x180177f3b  call    __security_check_cookie
0x180177f40  lea     r11, [rsp+2D0h+var_20]
0x180177f48  mov     rbx, [r11+40h]
0x180177f4c  mov     rsi, [r11+48h]
0x180177f50  mov     rsp, r11
0x180177f53  pop     r15
0x180177f55  pop     r14
0x180177f57  pop     r12
0x180177f59  pop     rdi
0x180177f5a  pop     rbp
0x180177f5b  retn
```
