# InitializeAssetLoader(void)

- ea: `0x18000f484`
- end: `0x18000f568`
- name: `?InitializeAssetLoader@@YAJXZ`
- size: `228`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x18000b380`

## callees

- `0x1800032e0`
- `0x180003da4`
- `0x180009024`
- `0x18000f410`
- `0x18000f484`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f511`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f511`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000f524`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000f524`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000f51c`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000f537`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000f51c`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000f537`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18000f4ce`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18000f4ce`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18000f4f6`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18000f4f6`

## string_xrefs

- `0x18000f4c7`: `%systemroot%\system32\whesvc_assets.dll`

## pseudocode

```c
__int64 InitializeAssetLoader(void)
{
  struct AssetLoaderSingleton *Instance; // rdi
  const char *v1; // r9
  __int64 v2; // rdx
  HMODULE LibraryW; // rsi
  HMODULE v5; // rbp
  DWORD LastError; // ebx
  char v7; // [rsp+20h] [rbp-258h] BYREF
  WCHAR Dst[264]; // [rsp+30h] [rbp-248h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+0h]

  Instance = AssetLoaderSingleton::GetInstance();
  memset_0(Dst, 0, 0x208u);
  if ( !ExpandEnvironmentStringsW(L"%systemroot%\\system32\\whesvc_assets.dll", Dst, 0x104u) )
  {
    v2 = 34;
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)v2,
             (unsigned int)"pcshell\\base\\whesvc\\lib\\assetloader.cpp",
             v1);
  }
  LibraryW = LoadLibraryW(Dst);
  if ( Instance == (struct AssetLoaderSingleton *)&v7 )
  {
    if ( LibraryW )
      FreeLibrary(LibraryW);
  }
  else
  {
    v5 = *(HMODULE *)Instance;
    if ( *(_QWORD *)Instance )
    {
      LastError = GetLastError();
      FreeLibrary(v5);
      SetLastError(LastError);
    }
    *(_QWORD *)Instance = LibraryW;
  }
  if ( !*(_QWORD *)Instance )
  {
    v2 = 38;
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)v2,
             (unsigned int)"pcshell\\base\\whesvc\\lib\\assetloader.cpp",
             v1);
  }
  return 0;
}

```

## disassembly

```asm
0x18000f484  push    rbx
0x18000f486  push    rbp
0x18000f487  push    rsi
0x18000f488  push    rdi
0x18000f489  sub     rsp, 258h
0x18000f490  mov     rax, cs:__security_cookie
0x18000f497  xor     rax, rsp
0x18000f49a  mov     [rsp+278h+var_38], rax
0x18000f4a2  call    ?GetInstance@AssetLoaderSingleton@@SAAEAV1@XZ; AssetLoaderSingleton::GetInstance(void)
0x18000f4a7  xor     edx, edx; Val
0x18000f4a9  lea     rcx, [rsp+278h+Dst]; void *
0x18000f4ae  mov     r8d, 208h; Size
0x18000f4b4  mov     rdi, rax
0x18000f4b7  call    memset_0
0x18000f4bc  mov     r8d, 104h; nSize
0x18000f4c2  lea     rdx, [rsp+278h+Dst]; lpDst
0x18000f4c7  lea     rcx, Src; "%systemroot%\\system32\\whesvc_assets.d"...
0x18000f4ce  call    cs:__imp_ExpandEnvironmentStringsW
0x18000f4d4  test    eax, eax
0x18000f4d6  jnz     short loc_18000F4F1
0x18000f4d8  lea     edx, [rax+22h]; void *
0x18000f4db  mov     rcx, [rsp+278h]; this
0x18000f4e3  lea     r8, aPcshellBaseWhe; "pcshell\\base\\whesvc\\lib\\assetloader"...
0x18000f4ea  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000f4ef  jmp     short loc_18000F54C
0x18000f4f1  lea     rcx, [rsp+278h+Dst]; lpLibFileName
0x18000f4f6  call    cs:__imp_LoadLibraryW
0x18000f4fc  mov     rsi, rax
0x18000f4ff  lea     rax, [rsp+278h+var_258]
0x18000f504  cmp     rdi, rax
0x18000f507  jz      short loc_18000F52F
0x18000f509  mov     rbp, [rdi]
0x18000f50c  test    rbp, rbp
0x18000f50f  jz      short loc_18000F52A
0x18000f511  call    cs:__imp_GetLastError
0x18000f517  mov     rcx, rbp; hLibModule
0x18000f51a  mov     ebx, eax
0x18000f51c  call    cs:__imp_FreeLibrary
0x18000f522  mov     ecx, ebx; dwErrCode
0x18000f524  call    cs:__imp_SetLastError
0x18000f52a  mov     [rdi], rsi
0x18000f52d  jmp     short loc_18000F53D
0x18000f52f  test    rsi, rsi
0x18000f532  jz      short loc_18000F53D
0x18000f534  mov     rcx, rsi; hLibModule
0x18000f537  call    cs:__imp_FreeLibrary
0x18000f53d  cmp     qword ptr [rdi], 0
0x18000f541  jnz     short loc_18000F54A
0x18000f543  mov     edx, 26h ; '&'
0x18000f548  jmp     short loc_18000F4DB
0x18000f54a  xor     eax, eax
0x18000f54c  mov     rcx, [rsp+278h+var_38]
0x18000f554  xor     rcx, rsp; StackCookie
0x18000f557  call    __security_check_cookie
0x18000f55c  add     rsp, 258h
0x18000f563  pop     rdi
0x18000f564  pop     rsi
0x18000f565  pop     rbp
0x18000f566  pop     rbx
0x18000f567  retn
```
