# LoadAuthrootFromResource

- ea: `0x18002b260`
- end: `0x18002b42f`
- name: `LoadAuthrootFromResource`
- size: `463`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180041fe0`

## callees

- `0x180023128`
- `0x18002b260`
- `0x18002b5f4`
- `0x18002bba0`
- `0x18002c090`
- `0x18002c1b4`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18002b304`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18002b304`
- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x18002b38a`
- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x18002b38a`
- `api-ms-win-core-libraryloader-l1-2-0!LockResource` at `0x18002b39f`
- `api-ms-win-core-libraryloader-l1-2-0!LockResource` at `0x18002b39f`
- `api-ms-win-core-libraryloader-l1-2-0!SizeofResource` at `0x18002b371`
- `api-ms-win-core-libraryloader-l1-2-0!SizeofResource` at `0x18002b371`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002b2bc`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002b2bc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002b33c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002b3e8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002b33c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002b3e8`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18002b28a`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18002b2f5`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18002b28a`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18002b2f5`
- `api-ms-win-core-libraryloader-l1-2-1!FindResourceW` at `0x18002b356`
- `api-ms-win-core-libraryloader-l1-2-1!FindResourceW` at `0x18002b356`

## string_xrefs

- `0x18002b27e`: `%SystemRoot%\SystemResources\crypt32.dll.mun`
- `0x18002b2e8`: `%SystemRoot%\SystemResources\crypt32.dll.mun`
- `0x18002b29b`: `onecore\ds\security\cryptoapi\pkitrust\softpub\configciprov.cpp`
- `0x18002b32b`: `onecore\ds\security\cryptoapi\pkitrust\softpub\configciprov.cpp`
- `0x18002b3cc`: `onecore\ds\security\cryptoapi\pkitrust\softpub\configciprov.cpp`
- `0x18002b3f7`: `onecore\ds\security\cryptoapi\pkitrust\softpub\configciprov.cpp`

## pseudocode

```c
__int64 LoadAuthrootFromResource()
{
  DWORD v0; // eax
  const char *v1; // r9
  DWORD v2; // esi
  unsigned int LastError; // ebx
  SIZE_T v4; // rdi
  WCHAR *v5; // rax
  WCHAR *v6; // rbx
  WCHAR *i; // rcx
  WCHAR *v8; // rdi
  HMODULE Library; // rax
  const char *v10; // r9
  HMODULE v11; // rbx
  __int64 v12; // rdx
  HRSRC ResourceW; // rax
  HRSRC v14; // rsi
  DWORD v15; // ebp
  HGLOBAL Resource; // rax
  BYTE *v17; // rax
  int AuthrootCTL; // eax
  int v20; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  HMODULE hModule; // [rsp+48h] [rbp+10h] BYREF

  hModule = 0;
  v0 = ExpandEnvironmentStringsW(L"%SystemRoot%\\SystemResources\\crypt32.dll.mun", 0, 0);
  v2 = v0;
  if ( v0 )
  {
    v4 = v0;
    v5 = (WCHAR *)LocalAlloc(0, v4 * 2);
    v6 = v5;
    if ( !v5 )
    {
      LastError = -2147024882;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x3C9,
        (unsigned int)"onecore\\ds\\security\\cryptoapi\\pkitrust\\softpub\\configciprov.cpp",
        (const char *)0x8007000ELL,
        v20);
      goto LABEL_22;
    }
    for ( i = &v5[v4]; v5 != i; ++v5 )
      *v5 = 0;
    v8 = v6;
    ExpandEnvironmentStringsW(L"%SystemRoot%\\SystemResources\\crypt32.dll.mun", v6, v2);
    Library = LoadLibraryExW(v6, 0, 0x22u);
    wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::reset(
      &hModule,
      Library);
    v11 = hModule;
    if ( hModule )
    {
      ResourceW = FindResourceW(hModule, (LPCWSTR)0x3FC, L"AUTHROOTSTL");
      v14 = ResourceW;
      if ( ResourceW )
      {
        v15 = SizeofResource(v11, ResourceW);
        if ( v15 )
        {
          Resource = LoadResource(v11, v14);
          if ( Resource )
          {
            v17 = (BYTE *)LockResource(Resource);
            if ( v17 )
            {
              AuthrootCTL = LoadAuthrootCTL(v17, v15);
              LastError = AuthrootCTL;
              if ( AuthrootCTL >= 0 )
              {
                LocalFree(v8);
                LastError = 0;
                goto LABEL_22;
              }
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x3E3,
                (unsigned int)"onecore\\ds\\security\\cryptoapi\\pkitrust\\softpub\\configciprov.cpp",
                (const char *)(unsigned int)AuthrootCTL,
                v20);
              goto LABEL_9;
            }
            v12 = 991;
          }
          else
          {
            v12 = 988;
          }
        }
        else
        {
          v12 = 985;
        }
      }
      else
      {
        v12 = 982;
      }
    }
    else
    {
      v12 = 977;
    }
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)v12,
                  (unsigned int)"onecore\\ds\\security\\cryptoapi\\pkitrust\\softpub\\configciprov.cpp",
                  v10);
LABEL_9:
    LocalFree(v8);
    goto LABEL_22;
  }
  LastError = wil::details::in1diag3::Return_GetLastError(
                retaddr,
                (void *)0x3C6,
                (unsigned int)"onecore\\ds\\security\\cryptoapi\\pkitrust\\softpub\\configciprov.cpp",
                v1);
LABEL_22:
  wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(&hModule);
  return LastError;
}

```

## disassembly

```asm
0x18002b260  mov     [rsp+arg_0], rbx
0x18002b265  mov     [rsp+arg_10], rbp
0x18002b26a  push    rsi
0x18002b26b  push    rdi
0x18002b26c  push    r14; int
0x18002b26e  sub     rsp, 20h
0x18002b272  mov     r14, rcx
0x18002b275  mov     [rsp+38h+hModule], 0
0x18002b27e  lea     rcx, aSystemrootSyst_0; "%SystemRoot%\\SystemResources\\crypt32."...
0x18002b285  xor     r8d, r8d; nSize
0x18002b288  xor     edx, edx; lpDst
0x18002b28a  call    cs:__imp_ExpandEnvironmentStringsW
0x18002b290  mov     esi, eax
0x18002b292  test    eax, eax
0x18002b294  jnz     short loc_18002B2B3
0x18002b296  mov     rcx, [rsp+38h]; this
0x18002b29b  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\cryptoapi\\pkitr"...
0x18002b2a2  mov     edx, 3C6h; void *
0x18002b2a7  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18002b2ac  mov     ebx, eax
0x18002b2ae  jmp     loc_18002B410
0x18002b2b3  lea     rdi, [rsi+rsi]
0x18002b2b7  xor     ecx, ecx; uFlags
0x18002b2b9  mov     rdx, rdi; uBytes
0x18002b2bc  call    cs:__imp_LocalAlloc
0x18002b2c2  mov     rbx, rax
0x18002b2c5  test    rax, rax
0x18002b2c8  jz      loc_18002B3F2
0x18002b2ce  lea     rcx, [rdi+rax]
0x18002b2d2  cmp     rax, rcx
0x18002b2d5  jz      short loc_18002B2E5
0x18002b2d7  xor     edx, edx
0x18002b2d9  mov     [rax], dx
0x18002b2dc  add     rax, 2
0x18002b2e0  cmp     rax, rcx
0x18002b2e3  jnz     short loc_18002B2D7
0x18002b2e5  mov     r8d, esi; nSize
0x18002b2e8  lea     rcx, aSystemrootSyst_0; "%SystemRoot%\\SystemResources\\crypt32."...
0x18002b2ef  mov     rdx, rbx; lpDst
0x18002b2f2  mov     rdi, rbx
0x18002b2f5  call    cs:__imp_ExpandEnvironmentStringsW
0x18002b2fb  xor     edx, edx; hFile
0x18002b2fd  mov     rcx, rbx; lpLibFileName
0x18002b300  lea     r8d, [rdx+22h]; dwFlags
0x18002b304  call    cs:__imp_LoadLibraryExW
0x18002b30a  mov     rdx, rax
0x18002b30d  lea     rcx, [rsp+38h+hModule]
0x18002b312  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHINSTANCE__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::reset(HINSTANCE__ *)
0x18002b317  mov     rbx, [rsp+38h+hModule]
0x18002b31c  test    rbx, rbx
0x18002b31f  jnz     short loc_18002B347
0x18002b321  mov     edx, 3D1h; void *
0x18002b326  mov     rcx, [rsp+38h]; this
0x18002b32b  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\cryptoapi\\pkitr"...
0x18002b332  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18002b337  mov     ebx, eax
0x18002b339  mov     rcx, rdi; hMem
0x18002b33c  call    cs:__imp_LocalFree
0x18002b342  jmp     loc_18002B410
0x18002b347  lea     r8, Type; "AUTHROOTSTL"
0x18002b34e  mov     edx, 3FCh; lpName
0x18002b353  mov     rcx, rbx; hModule
0x18002b356  call    cs:__imp_FindResourceW
0x18002b35c  mov     rsi, rax
0x18002b35f  test    rax, rax
0x18002b362  jnz     short loc_18002B36B
0x18002b364  mov     edx, 3D6h
0x18002b369  jmp     short loc_18002B326
0x18002b36b  mov     rdx, rsi; hResInfo
0x18002b36e  mov     rcx, rbx; hModule
0x18002b371  call    cs:__imp_SizeofResource
0x18002b377  mov     ebp, eax
0x18002b379  test    eax, eax
0x18002b37b  jnz     short loc_18002B384
0x18002b37d  mov     edx, 3D9h
0x18002b382  jmp     short loc_18002B326
0x18002b384  mov     rdx, rsi; hResInfo
0x18002b387  mov     rcx, rbx; hModule
0x18002b38a  call    cs:__imp_LoadResource
0x18002b390  test    rax, rax
0x18002b393  jnz     short loc_18002B39C
0x18002b395  mov     edx, 3DCh
0x18002b39a  jmp     short loc_18002B326
0x18002b39c  mov     rcx, rax; hResData
0x18002b39f  call    cs:__imp_LockResource
0x18002b3a5  test    rax, rax
0x18002b3a8  jnz     short loc_18002B3B4
0x18002b3aa  mov     edx, 3DFh
0x18002b3af  jmp     loc_18002B326
0x18002b3b4  mov     r8, r14
0x18002b3b7  mov     edx, ebp; cbCtlEncoded
0x18002b3b9  mov     rcx, rax; pbCtlEncoded
0x18002b3bc  call    LoadAuthrootCTL
0x18002b3c1  mov     ebx, eax
0x18002b3c3  test    eax, eax
0x18002b3c5  jns     short loc_18002B3E5
0x18002b3c7  mov     rcx, [rsp+38h]; this
0x18002b3cc  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\cryptoapi\\pkitr"...
0x18002b3d3  mov     r9d, eax; char *
0x18002b3d6  mov     edx, 3E3h; void *
0x18002b3db  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002b3e0  jmp     loc_18002B339
0x18002b3e5  mov     rcx, rdi; hMem
0x18002b3e8  call    cs:__imp_LocalFree
0x18002b3ee  xor     ebx, ebx
0x18002b3f0  jmp     short loc_18002B410
0x18002b3f2  mov     rcx, [rsp+38h]; this
0x18002b3f7  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\cryptoapi\\pkitr"...
0x18002b3fe  mov     ebx, 8007000Eh
0x18002b403  mov     edx, 3C9h; void *
0x18002b408  mov     r9d, ebx; char *
0x18002b40b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002b410  lea     rcx, [rsp+38h+hModule]
0x18002b415  call    ??1?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(void)
0x18002b41a  mov     rbp, [rsp+38h+arg_10]
0x18002b41f  mov     eax, ebx
0x18002b421  mov     rbx, [rsp+38h+arg_0]
0x18002b426  add     rsp, 20h
0x18002b42a  pop     r14
0x18002b42c  pop     rdi
0x18002b42d  pop     rsi
0x18002b42e  retn
```
