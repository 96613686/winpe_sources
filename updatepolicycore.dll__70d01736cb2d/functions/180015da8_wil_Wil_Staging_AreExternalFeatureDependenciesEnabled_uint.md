# wil::Wil_Staging_AreExternalFeatureDependenciesEnabled(uint)

- ea: `0x180015da8`
- end: `0x180015ebb`
- name: `?Wil_Staging_AreExternalFeatureDependenciesEnabled@wil@@YA_NI@Z`
- size: `275`
- prototype: `bool __fastcall(wil *__hidden this, unsigned int)`
- caller_count: `4`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800156cc`
- `0x1800159b4`
- `0x180015ec4`
- `0x180019bd0`

## callees

- `0x180015da8`
- `0x180036a10`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x180015dcd`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x180015e1b`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x180015dcd`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x180015e1b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180015df1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180015e3f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180015e54`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180015df1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180015e3f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180015e54`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180015e7f`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180015e8e`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180015e9f`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180015e7f`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180015e8e`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180015e9f`

## string_xrefs

- `0x180015dc6`: `kernelbase.dll`
- `0x180015e14`: `windowsudk.shellcommon.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
bool __fastcall wil::Wil_Staging_AreExternalFeatureDependenciesEnabled(wil *this)
{
  unsigned int v1; // esi
  HMODULE Library; // rax
  HMODULE v3; // rdi
  bool v4; // r14
  FARPROC ProcAddress; // rax
  bool v6; // si
  HMODULE v7; // rax
  HMODULE v8; // rbx
  bool v9; // bp
  FARPROC v10; // rax

  v1 = (unsigned int)this;
  Library = LoadLibraryExA("kernelbase.dll", 0, 0x800u);
  v3 = Library;
  v4 = Library != 0;
  if ( Library )
  {
    ProcAddress = GetProcAddress(Library, "AreExternalFeatureDependenciesEnabled");
    if ( ProcAddress )
    {
      v6 = ((unsigned int (__fastcall *)(_QWORD))ProcAddress)(v1) == 2;
      goto LABEL_12;
    }
  }
  v7 = LoadLibraryExA("windowsudk.shellcommon.dll", 0, 0x800u);
  v8 = v7;
  v9 = v7 != 0;
  if ( !v7 )
    goto LABEL_11;
  v10 = GetProcAddress(v7, "AreExternalFeatureDependenciesEnabled");
  if ( !v10 )
  {
    v10 = GetProcAddress(v8, "GetExternalFeatureState");
    if ( !v10 )
    {
      if ( v9 )
        FreeLibrary(v8);
LABEL_11:
      v6 = 0;
      goto LABEL_12;
    }
  }
  v6 = ((unsigned int (__fastcall *)(_QWORD))v10)(v1) == 2;
  if ( v9 )
    FreeLibrary(v8);
LABEL_12:
  if ( v4 )
    FreeLibrary(v3);
  return v6;
}

```

## disassembly

```asm
0x180015da8  mov     [rsp+arg_8], rbx
0x180015dad  mov     [rsp+arg_10], rbp
0x180015db2  push    rsi
0x180015db3  push    rdi
0x180015db4  push    r14
0x180015db6  sub     rsp, 30h
0x180015dba  mov     esi, ecx
0x180015dbc  mov     ebx, 800h
0x180015dc1  mov     r8d, ebx; dwFlags
0x180015dc4  xor     edx, edx; hFile
0x180015dc6  lea     rcx, LibFileName; "kernelbase.dll"
0x180015dcd  call    cs:__imp_LoadLibraryExA
0x180015dd3  mov     rdi, rax
0x180015dd6  mov     [rsp+48h+var_28], rax
0x180015ddb  test    rax, rax
0x180015dde  setnz   r14b
0x180015de2  test    rax, rax
0x180015de5  jz      short loc_180015E0F
0x180015de7  lea     rdx, aAreexternalfea; "AreExternalFeatureDependenciesEnabled"
0x180015dee  mov     rcx, rax; hModule
0x180015df1  call    cs:__imp_GetProcAddress
0x180015df7  test    rax, rax
0x180015dfa  jz      short loc_180015E0F
0x180015dfc  mov     ecx, esi
0x180015dfe  call    _guard_dispatch_icall
0x180015e03  cmp     eax, 2
0x180015e06  setz    sil
0x180015e0a  jmp     loc_180015E97
0x180015e0f  mov     r8d, ebx; dwFlags
0x180015e12  xor     edx, edx; hFile
0x180015e14  lea     rcx, aWindowsudkShel; "windowsudk.shellcommon.dll"
0x180015e1b  call    cs:__imp_LoadLibraryExA
0x180015e21  mov     rbx, rax
0x180015e24  mov     [rsp+48h+var_20], rax
0x180015e29  test    rax, rax
0x180015e2c  setnz   bpl
0x180015e30  test    rax, rax
0x180015e33  jz      short loc_180015E87
0x180015e35  lea     rdx, aAreexternalfea; "AreExternalFeatureDependenciesEnabled"
0x180015e3c  mov     rcx, rax; hModule
0x180015e3f  call    cs:__imp_GetProcAddress
0x180015e45  test    rax, rax
0x180015e48  jnz     short loc_180015E69
0x180015e4a  lea     rdx, aGetexternalfea; "GetExternalFeatureState"
0x180015e51  mov     rcx, rbx; hModule
0x180015e54  call    cs:__imp_GetProcAddress
0x180015e5a  test    rax, rax
0x180015e5d  jnz     short loc_180015E69
0x180015e5f  test    bpl, bpl
0x180015e62  jz      short loc_180015E94
0x180015e64  mov     rcx, rbx
0x180015e67  jmp     short loc_180015E8E
0x180015e69  mov     ecx, esi
0x180015e6b  call    _guard_dispatch_icall
0x180015e70  cmp     eax, 2
0x180015e73  setz    sil
0x180015e77  test    bpl, bpl
0x180015e7a  jz      short loc_180015E97
0x180015e7c  mov     rcx, rbx; hLibModule
0x180015e7f  call    cs:__imp_FreeLibrary
0x180015e85  jmp     short loc_180015E97
0x180015e87  test    bpl, bpl
0x180015e8a  jz      short loc_180015E94
0x180015e8c  xor     ecx, ecx; hLibModule
0x180015e8e  call    cs:__imp_FreeLibrary
0x180015e94  xor     sil, sil
0x180015e97  test    r14b, r14b
0x180015e9a  jz      short loc_180015EA5
0x180015e9c  mov     rcx, rdi; hLibModule
0x180015e9f  call    cs:__imp_FreeLibrary
0x180015ea5  mov     al, sil
0x180015ea8  mov     rbx, [rsp+48h+arg_8]
0x180015ead  mov     rbp, [rsp+48h+arg_10]
0x180015eb2  add     rsp, 30h
0x180015eb6  pop     r14
0x180015eb8  pop     rdi
0x180015eb9  pop     rsi
0x180015eba  retn
```
