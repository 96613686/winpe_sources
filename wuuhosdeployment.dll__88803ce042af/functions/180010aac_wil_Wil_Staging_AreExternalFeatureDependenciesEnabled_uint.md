# wil::Wil_Staging_AreExternalFeatureDependenciesEnabled(uint)

- ea: `0x180010aac`
- end: `0x180010bbf`
- name: `?Wil_Staging_AreExternalFeatureDependenciesEnabled@wil@@YA_NI@Z`
- size: `275`
- prototype: `bool __fastcall(wil *__hidden this, unsigned int)`
- caller_count: `8`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180014420`
- `0x18001ae88`
- `0x18001b170`
- `0x18001cfc8`
- `0x180024408`
- `0x180030a10`
- `0x180030b30`
- `0x180030ea4`

## callees

- `0x180010aac`
- `0x180049260`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180010b83`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180010b92`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180010ba3`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180010b83`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180010b92`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180010ba3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180010af5`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180010b43`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180010b58`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180010af5`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180010b43`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180010b58`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x180010ad1`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x180010b1f`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x180010ad1`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x180010b1f`

## string_xrefs

- `0x180010b18`: `windowsudk.shellcommon.dll`
- `0x180010aca`: `kernelbase.dll`

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
0x180010aac  mov     [rsp+arg_8], rbx
0x180010ab1  mov     [rsp+arg_10], rbp
0x180010ab6  push    rsi
0x180010ab7  push    rdi
0x180010ab8  push    r14
0x180010aba  sub     rsp, 30h
0x180010abe  mov     esi, ecx
0x180010ac0  mov     ebx, 800h
0x180010ac5  mov     r8d, ebx; dwFlags
0x180010ac8  xor     edx, edx; hFile
0x180010aca  lea     rcx, LibFileName; "kernelbase.dll"
0x180010ad1  call    cs:__imp_LoadLibraryExA
0x180010ad7  mov     rdi, rax
0x180010ada  mov     [rsp+48h+var_28], rax
0x180010adf  test    rax, rax
0x180010ae2  setnz   r14b
0x180010ae6  test    rax, rax
0x180010ae9  jz      short loc_180010B13
0x180010aeb  lea     rdx, aAreexternalfea; "AreExternalFeatureDependenciesEnabled"
0x180010af2  mov     rcx, rax; hModule
0x180010af5  call    cs:__imp_GetProcAddress
0x180010afb  test    rax, rax
0x180010afe  jz      short loc_180010B13
0x180010b00  mov     ecx, esi
0x180010b02  call    _guard_dispatch_icall
0x180010b07  cmp     eax, 2
0x180010b0a  setz    sil
0x180010b0e  jmp     loc_180010B9B
0x180010b13  mov     r8d, ebx; dwFlags
0x180010b16  xor     edx, edx; hFile
0x180010b18  lea     rcx, aWindowsudkShel; "windowsudk.shellcommon.dll"
0x180010b1f  call    cs:__imp_LoadLibraryExA
0x180010b25  mov     rbx, rax
0x180010b28  mov     [rsp+48h+var_20], rax
0x180010b2d  test    rax, rax
0x180010b30  setnz   bpl
0x180010b34  test    rax, rax
0x180010b37  jz      short loc_180010B8B
0x180010b39  lea     rdx, aAreexternalfea; "AreExternalFeatureDependenciesEnabled"
0x180010b40  mov     rcx, rax; hModule
0x180010b43  call    cs:__imp_GetProcAddress
0x180010b49  test    rax, rax
0x180010b4c  jnz     short loc_180010B6D
0x180010b4e  lea     rdx, aGetexternalfea; "GetExternalFeatureState"
0x180010b55  mov     rcx, rbx; hModule
0x180010b58  call    cs:__imp_GetProcAddress
0x180010b5e  test    rax, rax
0x180010b61  jnz     short loc_180010B6D
0x180010b63  test    bpl, bpl
0x180010b66  jz      short loc_180010B98
0x180010b68  mov     rcx, rbx
0x180010b6b  jmp     short loc_180010B92
0x180010b6d  mov     ecx, esi
0x180010b6f  call    _guard_dispatch_icall
0x180010b74  cmp     eax, 2
0x180010b77  setz    sil
0x180010b7b  test    bpl, bpl
0x180010b7e  jz      short loc_180010B9B
0x180010b80  mov     rcx, rbx; hLibModule
0x180010b83  call    cs:__imp_FreeLibrary
0x180010b89  jmp     short loc_180010B9B
0x180010b8b  test    bpl, bpl
0x180010b8e  jz      short loc_180010B98
0x180010b90  xor     ecx, ecx; hLibModule
0x180010b92  call    cs:__imp_FreeLibrary
0x180010b98  xor     sil, sil
0x180010b9b  test    r14b, r14b
0x180010b9e  jz      short loc_180010BA9
0x180010ba0  mov     rcx, rdi; hLibModule
0x180010ba3  call    cs:__imp_FreeLibrary
0x180010ba9  mov     al, sil
0x180010bac  mov     rbx, [rsp+48h+arg_8]
0x180010bb1  mov     rbp, [rsp+48h+arg_10]
0x180010bb6  add     rsp, 30h
0x180010bba  pop     r14
0x180010bbc  pop     rdi
0x180010bbd  pop     rsi
0x180010bbe  retn
```
