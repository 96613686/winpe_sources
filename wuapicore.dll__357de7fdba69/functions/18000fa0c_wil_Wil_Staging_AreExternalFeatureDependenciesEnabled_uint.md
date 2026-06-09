# wil::Wil_Staging_AreExternalFeatureDependenciesEnabled(uint)

- ea: `0x18000fa0c`
- end: `0x18000fb1f`
- name: `?Wil_Staging_AreExternalFeatureDependenciesEnabled@wil@@YA_NI@Z`
- size: `275`
- prototype: `bool __fastcall(wil *__hidden this, unsigned int)`
- caller_count: `9`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000f500`
- `0x18000fb28`
- `0x18005f730`
- `0x18005fa18`
- `0x18005fd00`
- `0x18006cff0`
- `0x18006d2d8`
- `0x1800746c0`
- `0x180081de0`

## callees

- `0x18000fa0c`
- `0x1800a1960`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000fae3`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000faf2`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000fb03`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000fae3`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000faf2`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000fb03`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000fa55`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000faa3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000fab8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000fa55`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000faa3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000fab8`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x18000fa31`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x18000fa7f`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x18000fa31`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x18000fa7f`

## string_xrefs

- `0x18000fa2a`: `kernelbase.dll`
- `0x18000fa78`: `windowsudk.shellcommon.dll`

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
0x18000fa0c  mov     [rsp+arg_8], rbx
0x18000fa11  mov     [rsp+arg_10], rbp
0x18000fa16  push    rsi
0x18000fa17  push    rdi
0x18000fa18  push    r14
0x18000fa1a  sub     rsp, 30h
0x18000fa1e  mov     esi, ecx
0x18000fa20  mov     ebx, 800h
0x18000fa25  mov     r8d, ebx; dwFlags
0x18000fa28  xor     edx, edx; hFile
0x18000fa2a  lea     rcx, LibFileName; "kernelbase.dll"
0x18000fa31  call    cs:__imp_LoadLibraryExA
0x18000fa37  mov     rdi, rax
0x18000fa3a  mov     [rsp+48h+var_28], rax
0x18000fa3f  test    rax, rax
0x18000fa42  setnz   r14b
0x18000fa46  test    rax, rax
0x18000fa49  jz      short loc_18000FA73
0x18000fa4b  lea     rdx, ProcName; "AreExternalFeatureDependenciesEnabled"
0x18000fa52  mov     rcx, rax; hModule
0x18000fa55  call    cs:__imp_GetProcAddress
0x18000fa5b  test    rax, rax
0x18000fa5e  jz      short loc_18000FA73
0x18000fa60  mov     ecx, esi
0x18000fa62  call    _guard_dispatch_icall
0x18000fa67  cmp     eax, 2
0x18000fa6a  setz    sil
0x18000fa6e  jmp     loc_18000FAFB
0x18000fa73  mov     r8d, ebx; dwFlags
0x18000fa76  xor     edx, edx; hFile
0x18000fa78  lea     rcx, aWindowsudkShel; "windowsudk.shellcommon.dll"
0x18000fa7f  call    cs:__imp_LoadLibraryExA
0x18000fa85  mov     rbx, rax
0x18000fa88  mov     [rsp+48h+var_20], rax
0x18000fa8d  test    rax, rax
0x18000fa90  setnz   bpl
0x18000fa94  test    rax, rax
0x18000fa97  jz      short loc_18000FAEB
0x18000fa99  lea     rdx, ProcName; "AreExternalFeatureDependenciesEnabled"
0x18000faa0  mov     rcx, rax; hModule
0x18000faa3  call    cs:__imp_GetProcAddress
0x18000faa9  test    rax, rax
0x18000faac  jnz     short loc_18000FACD
0x18000faae  lea     rdx, aGetexternalfea; "GetExternalFeatureState"
0x18000fab5  mov     rcx, rbx; hModule
0x18000fab8  call    cs:__imp_GetProcAddress
0x18000fabe  test    rax, rax
0x18000fac1  jnz     short loc_18000FACD
0x18000fac3  test    bpl, bpl
0x18000fac6  jz      short loc_18000FAF8
0x18000fac8  mov     rcx, rbx
0x18000facb  jmp     short loc_18000FAF2
0x18000facd  mov     ecx, esi
0x18000facf  call    _guard_dispatch_icall
0x18000fad4  cmp     eax, 2
0x18000fad7  setz    sil
0x18000fadb  test    bpl, bpl
0x18000fade  jz      short loc_18000FAFB
0x18000fae0  mov     rcx, rbx; hLibModule
0x18000fae3  call    cs:__imp_FreeLibrary
0x18000fae9  jmp     short loc_18000FAFB
0x18000faeb  test    bpl, bpl
0x18000faee  jz      short loc_18000FAF8
0x18000faf0  xor     ecx, ecx; hLibModule
0x18000faf2  call    cs:__imp_FreeLibrary
0x18000faf8  xor     sil, sil
0x18000fafb  test    r14b, r14b
0x18000fafe  jz      short loc_18000FB09
0x18000fb00  mov     rcx, rdi; hLibModule
0x18000fb03  call    cs:__imp_FreeLibrary
0x18000fb09  mov     al, sil
0x18000fb0c  mov     rbx, [rsp+48h+arg_8]
0x18000fb11  mov     rbp, [rsp+48h+arg_10]
0x18000fb16  add     rsp, 30h
0x18000fb1a  pop     r14
0x18000fb1c  pop     rdi
0x18000fb1d  pop     rsi
0x18000fb1e  retn
```
