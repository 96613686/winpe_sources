# wil::Wil_Staging_AreExternalFeatureDependenciesEnabled(uint)

- ea: `0x18000be64`
- end: `0x18000bf77`
- name: `?Wil_Staging_AreExternalFeatureDependenciesEnabled@wil@@YA_NI@Z`
- size: `275`
- prototype: `bool __fastcall(wil *__hidden this, unsigned int)`
- caller_count: `9`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000ffd4`
- `0x1800100f4`
- `0x18001fd64`
- `0x18001fe84`
- `0x1800635fc`
- `0x1800773a0`
- `0x1800af7e4`
- `0x1800c553c`
- `0x1800ca374`

## callees

- `0x18000be64`
- `0x1800e4630`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x18000be89`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x18000bed7`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x18000be89`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x18000bed7`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000bead`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000befb`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000bf10`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000bead`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000befb`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000bf10`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000bf3b`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000bf4a`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000bf5b`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000bf3b`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000bf4a`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000bf5b`

## string_xrefs

- `0x18000bed0`: `windowsudk.shellcommon.dll`
- `0x18000be82`: `kernelbase.dll`

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
0x18000be64  mov     [rsp+arg_8], rbx
0x18000be69  mov     [rsp+arg_10], rbp
0x18000be6e  push    rsi
0x18000be6f  push    rdi
0x18000be70  push    r14
0x18000be72  sub     rsp, 30h
0x18000be76  mov     esi, ecx
0x18000be78  mov     ebx, 800h
0x18000be7d  mov     r8d, ebx; dwFlags
0x18000be80  xor     edx, edx; hFile
0x18000be82  lea     rcx, LibFileName; "kernelbase.dll"
0x18000be89  call    cs:__imp_LoadLibraryExA
0x18000be8f  mov     rdi, rax
0x18000be92  mov     [rsp+48h+var_28], rax
0x18000be97  test    rax, rax
0x18000be9a  setnz   r14b
0x18000be9e  test    rax, rax
0x18000bea1  jz      short loc_18000BECB
0x18000bea3  lea     rdx, aAreexternalfea; "AreExternalFeatureDependenciesEnabled"
0x18000beaa  mov     rcx, rax; hModule
0x18000bead  call    cs:__imp_GetProcAddress
0x18000beb3  test    rax, rax
0x18000beb6  jz      short loc_18000BECB
0x18000beb8  mov     ecx, esi
0x18000beba  call    _guard_dispatch_icall
0x18000bebf  cmp     eax, 2
0x18000bec2  setz    sil
0x18000bec6  jmp     loc_18000BF53
0x18000becb  mov     r8d, ebx; dwFlags
0x18000bece  xor     edx, edx; hFile
0x18000bed0  lea     rcx, aWindowsudkShel; "windowsudk.shellcommon.dll"
0x18000bed7  call    cs:__imp_LoadLibraryExA
0x18000bedd  mov     rbx, rax
0x18000bee0  mov     [rsp+48h+var_20], rax
0x18000bee5  test    rax, rax
0x18000bee8  setnz   bpl
0x18000beec  test    rax, rax
0x18000beef  jz      short loc_18000BF43
0x18000bef1  lea     rdx, aAreexternalfea; "AreExternalFeatureDependenciesEnabled"
0x18000bef8  mov     rcx, rax; hModule
0x18000befb  call    cs:__imp_GetProcAddress
0x18000bf01  test    rax, rax
0x18000bf04  jnz     short loc_18000BF25
0x18000bf06  lea     rdx, aGetexternalfea; "GetExternalFeatureState"
0x18000bf0d  mov     rcx, rbx; hModule
0x18000bf10  call    cs:__imp_GetProcAddress
0x18000bf16  test    rax, rax
0x18000bf19  jnz     short loc_18000BF25
0x18000bf1b  test    bpl, bpl
0x18000bf1e  jz      short loc_18000BF50
0x18000bf20  mov     rcx, rbx
0x18000bf23  jmp     short loc_18000BF4A
0x18000bf25  mov     ecx, esi
0x18000bf27  call    _guard_dispatch_icall
0x18000bf2c  cmp     eax, 2
0x18000bf2f  setz    sil
0x18000bf33  test    bpl, bpl
0x18000bf36  jz      short loc_18000BF53
0x18000bf38  mov     rcx, rbx; hLibModule
0x18000bf3b  call    cs:__imp_FreeLibrary
0x18000bf41  jmp     short loc_18000BF53
0x18000bf43  test    bpl, bpl
0x18000bf46  jz      short loc_18000BF50
0x18000bf48  xor     ecx, ecx; hLibModule
0x18000bf4a  call    cs:__imp_FreeLibrary
0x18000bf50  xor     sil, sil
0x18000bf53  test    r14b, r14b
0x18000bf56  jz      short loc_18000BF61
0x18000bf58  mov     rcx, rdi; hLibModule
0x18000bf5b  call    cs:__imp_FreeLibrary
0x18000bf61  mov     al, sil
0x18000bf64  mov     rbx, [rsp+48h+arg_8]
0x18000bf69  mov     rbp, [rsp+48h+arg_10]
0x18000bf6e  add     rsp, 30h
0x18000bf72  pop     r14
0x18000bf74  pop     rdi
0x18000bf75  pop     rsi
0x18000bf76  retn
```
