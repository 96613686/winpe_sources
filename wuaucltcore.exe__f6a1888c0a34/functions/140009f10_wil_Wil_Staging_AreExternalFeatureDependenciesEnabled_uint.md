# wil::Wil_Staging_AreExternalFeatureDependenciesEnabled(uint)

- ea: `0x140009f10`
- end: `0x14000a023`
- name: `?Wil_Staging_AreExternalFeatureDependenciesEnabled@wil@@YA_NI@Z`
- size: `275`
- prototype: `bool __fastcall(wil *__hidden this, unsigned int)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14000a02c`
- `0x140013f74`
- `0x140014554`

## callees

- `0x140009f10`
- `0x1400206e0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x140009fe7`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x140009ff6`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x14000a007`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x140009fe7`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x140009ff6`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x14000a007`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140009f59`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140009fa7`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140009fbc`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140009f59`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140009fa7`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140009fbc`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x140009f35`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x140009f83`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x140009f35`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x140009f83`

## string_xrefs

- `0x140009f2e`: `kernelbase.dll`
- `0x140009f7c`: `windowsudk.shellcommon.dll`

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
0x140009f10  mov     [rsp+arg_8], rbx
0x140009f15  mov     [rsp+arg_10], rbp
0x140009f1a  push    rsi
0x140009f1b  push    rdi
0x140009f1c  push    r14
0x140009f1e  sub     rsp, 30h
0x140009f22  mov     esi, ecx
0x140009f24  mov     ebx, 800h
0x140009f29  mov     r8d, ebx; dwFlags
0x140009f2c  xor     edx, edx; hFile
0x140009f2e  lea     rcx, LibFileName; "kernelbase.dll"
0x140009f35  call    cs:__imp_LoadLibraryExA
0x140009f3b  mov     rdi, rax
0x140009f3e  mov     [rsp+48h+var_28], rax
0x140009f43  test    rax, rax
0x140009f46  setnz   r14b
0x140009f4a  test    rax, rax
0x140009f4d  jz      short loc_140009F77
0x140009f4f  lea     rdx, aAreexternalfea; "AreExternalFeatureDependenciesEnabled"
0x140009f56  mov     rcx, rax; hModule
0x140009f59  call    cs:__imp_GetProcAddress
0x140009f5f  test    rax, rax
0x140009f62  jz      short loc_140009F77
0x140009f64  mov     ecx, esi
0x140009f66  call    _guard_dispatch_icall
0x140009f6b  cmp     eax, 2
0x140009f6e  setz    sil
0x140009f72  jmp     loc_140009FFF
0x140009f77  mov     r8d, ebx; dwFlags
0x140009f7a  xor     edx, edx; hFile
0x140009f7c  lea     rcx, aWindowsudkShel; "windowsudk.shellcommon.dll"
0x140009f83  call    cs:__imp_LoadLibraryExA
0x140009f89  mov     rbx, rax
0x140009f8c  mov     [rsp+48h+var_20], rax
0x140009f91  test    rax, rax
0x140009f94  setnz   bpl
0x140009f98  test    rax, rax
0x140009f9b  jz      short loc_140009FEF
0x140009f9d  lea     rdx, aAreexternalfea; "AreExternalFeatureDependenciesEnabled"
0x140009fa4  mov     rcx, rax; hModule
0x140009fa7  call    cs:__imp_GetProcAddress
0x140009fad  test    rax, rax
0x140009fb0  jnz     short loc_140009FD1
0x140009fb2  lea     rdx, aGetexternalfea; "GetExternalFeatureState"
0x140009fb9  mov     rcx, rbx; hModule
0x140009fbc  call    cs:__imp_GetProcAddress
0x140009fc2  test    rax, rax
0x140009fc5  jnz     short loc_140009FD1
0x140009fc7  test    bpl, bpl
0x140009fca  jz      short loc_140009FFC
0x140009fcc  mov     rcx, rbx
0x140009fcf  jmp     short loc_140009FF6
0x140009fd1  mov     ecx, esi
0x140009fd3  call    _guard_dispatch_icall
0x140009fd8  cmp     eax, 2
0x140009fdb  setz    sil
0x140009fdf  test    bpl, bpl
0x140009fe2  jz      short loc_140009FFF
0x140009fe4  mov     rcx, rbx; hLibModule
0x140009fe7  call    cs:__imp_FreeLibrary
0x140009fed  jmp     short loc_140009FFF
0x140009fef  test    bpl, bpl
0x140009ff2  jz      short loc_140009FFC
0x140009ff4  xor     ecx, ecx; hLibModule
0x140009ff6  call    cs:__imp_FreeLibrary
0x140009ffc  xor     sil, sil
0x140009fff  test    r14b, r14b
0x14000a002  jz      short loc_14000A00D
0x14000a004  mov     rcx, rdi; hLibModule
0x14000a007  call    cs:__imp_FreeLibrary
0x14000a00d  mov     al, sil
0x14000a010  mov     rbx, [rsp+48h+arg_8]
0x14000a015  mov     rbp, [rsp+48h+arg_10]
0x14000a01a  add     rsp, 30h
0x14000a01e  pop     r14
0x14000a020  pop     rdi
0x14000a021  pop     rsi
0x14000a022  retn
```
