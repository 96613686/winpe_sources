# Windows::UI::Composition::ShaderIncludeResolver::Open(_D3D_INCLUDE_TYPE,char const *,void const *,void const * *,uint *)

- ea: `0x180019d60`
- end: `0x180019e32`
- name: `?Open@ShaderIncludeResolver@Composition@UI@Windows@@UEAAJW4_D3D_INCLUDE_TYPE@@PEBDPEBXPEAPEBXPEAI@Z`
- size: `210`
- prototype: `int(Windows::UI::Composition::ShaderIncludeResolver *__hidden this, enum _D3D_INCLUDE_TYPE, const char *, const void *, const void **, unsigned int *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180019d60`
- `0x18001f038`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x180019d9a`
- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x180019d9a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x180019df3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x180019df3`
- `api-ms-win-core-libraryloader-l1-2-0!LockResource` at `0x180019dac`
- `api-ms-win-core-libraryloader-l1-2-0!LockResource` at `0x180019dac`
- `api-ms-win-core-libraryloader-l1-2-0!SizeofResource` at `0x180019dc4`
- `api-ms-win-core-libraryloader-l1-2-0!SizeofResource` at `0x180019dc4`
- `api-ms-win-core-kernel32-legacy-l1-1-0!FindResourceA` at `0x180019d7e`
- `api-ms-win-core-kernel32-legacy-l1-1-0!FindResourceA` at `0x180019d7e`

## string_xrefs

- `0x180019e05`: `onecoreuap\windows\dwm\effects\compiler\shaderincluderesolver.cpp`

## pseudocode

```c
__int64 __fastcall Windows::UI::Composition::ShaderIncludeResolver::Open(
        Windows::UI::Composition::ShaderIncludeResolver *this,
        enum _D3D_INCLUDE_TYPE a2,
        const char *a3,
        const void *a4,
        const void **a5,
        unsigned int *a6)
{
  HMODULE v6; // rcx
  HRSRC ResourceA; // rax
  const char *v9; // r9
  HRSRC v10; // rbx
  HGLOBAL Resource; // rax
  __int64 v13; // rdx
  HMODULE phModule; // [rsp+20h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  v6 = hModule;
  if ( !hModule )
  {
    phModule = 0;
    if ( !GetModuleHandleExW(6u, (LPCWSTR)&hModule, &phModule) )
    {
      v13 = 49;
      return wil::details::in1diag3::Return_GetLastError(
               retaddr,
               (void *)v13,
               (unsigned int)"onecoreuap\\windows\\dwm\\effects\\compiler\\shaderincluderesolver.cpp",
               v9);
    }
    v6 = phModule;
    hModule = phModule;
  }
  ResourceA = FindResourceA(v6, a3, (LPCSTR)0xA);
  v10 = ResourceA;
  if ( ResourceA )
  {
    Resource = LoadResource(hModule, ResourceA);
    if ( Resource )
    {
      *a5 = LockResource(Resource);
      *a6 = SizeofResource(hModule, v10);
      return 0;
    }
    v13 = 60;
  }
  else
  {
    v13 = 57;
  }
  return wil::details::in1diag3::Return_GetLastError(
           retaddr,
           (void *)v13,
           (unsigned int)"onecoreuap\\windows\\dwm\\effects\\compiler\\shaderincluderesolver.cpp",
           v9);
}

```

## disassembly

```asm
0x180019d60  push    rbx
0x180019d62  sub     rsp, 30h
0x180019d66  mov     rcx, cs:hModule; hModule
0x180019d6d  mov     rbx, r8
0x180019d70  test    rcx, rcx
0x180019d73  jz      short loc_180019DD9
0x180019d75  mov     r8d, 0Ah; lpType
0x180019d7b  mov     rdx, rbx; lpName
0x180019d7e  call    cs:__imp_FindResourceA
0x180019d84  mov     rbx, rax
0x180019d87  test    rax, rax
0x180019d8a  jz      loc_180019E24
0x180019d90  mov     rcx, cs:hModule; hModule
0x180019d97  mov     rdx, rax; hResInfo
0x180019d9a  call    cs:__imp_LoadResource
0x180019da0  test    rax, rax
0x180019da3  jz      loc_180019E2B
0x180019da9  mov     rcx, rax; hResData
0x180019dac  call    cs:__imp_LockResource
0x180019db2  mov     rcx, [rsp+38h+arg_20]
0x180019db7  mov     rdx, rbx; hResInfo
0x180019dba  mov     [rcx], rax
0x180019dbd  mov     rcx, cs:hModule; hModule
0x180019dc4  call    cs:__imp_SizeofResource
0x180019dca  mov     rcx, [rsp+38h+arg_28]
0x180019dcf  mov     [rcx], eax
0x180019dd1  xor     eax, eax
0x180019dd3  add     rsp, 30h
0x180019dd7  pop     rbx
0x180019dd8  retn
0x180019dd9  lea     r8, [rsp+38h+phModule]; phModule
0x180019dde  mov     [rsp+38h+phModule], 0
0x180019de7  lea     rdx, hModule; lpModuleName
0x180019dee  mov     ecx, 6; dwFlags
0x180019df3  call    cs:__imp_GetModuleHandleExW
0x180019df9  test    eax, eax
0x180019dfb  jnz     short loc_180019E13
0x180019dfd  lea     edx, [rax+31h]; void *
0x180019e00  mov     rcx, [rsp+38h]; this
0x180019e05  lea     r8, aOnecoreuapWind_4; "onecoreuap\\windows\\dwm\\effects\\comp"...
0x180019e0c  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180019e11  jmp     short loc_180019DD3
0x180019e13  mov     rcx, [rsp+38h+phModule]
0x180019e18  mov     cs:hModule, rcx
0x180019e1f  jmp     loc_180019D75
0x180019e24  mov     edx, 39h ; '9'
0x180019e29  jmp     short loc_180019E00
0x180019e2b  mov     edx, 3Ch ; '<'
0x180019e30  jmp     short loc_180019E00
```
