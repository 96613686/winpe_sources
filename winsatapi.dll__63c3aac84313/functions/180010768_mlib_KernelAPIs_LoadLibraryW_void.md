# mlib::KernelAPIs::LoadLibraryW(void)

- ea: `0x180010768`
- end: `0x180010812`
- name: `?LoadLibraryW@KernelAPIs@mlib@@QEAAKXZ`
- size: `170`
- prototype: `unsigned int __fastcall(mlib::KernelAPIs *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting, installer_update`

## callers

- `0x180010690`
- `0x1800248e0`

## callees

- `0x180010768`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001079c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800107b5`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800107ce`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800107e7`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180010800`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001079c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800107b5`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800107ce`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800107e7`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180010800`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001078b`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x180010778`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x180010778`

## string_xrefs

- `0x180010771`: `Kernel32.dll`
- `0x1800107ae`: `SetThreadPreferredUILanguages`
- `0x1800107f9`: `GetPhysicallyInstalledSystemMemory`

## pseudocode

```c
DWORD __fastcall mlib::KernelAPIs::LoadLibraryW(mlib::KernelAPIs *this)
{
  HMODULE LibraryW; // rax
  FARPROC ProcAddress; // rax
  FARPROC v5; // rax
  FARPROC v6; // rax
  FARPROC v7; // rax

  LibraryW = LoadLibraryW(L"Kernel32.dll");
  *(_QWORD *)this = LibraryW;
  if ( !LibraryW )
    return GetLastError();
  ProcAddress = GetProcAddress(LibraryW, "GetLogicalProcessorInformation");
  *((_QWORD *)this + 1) = ProcAddress;
  if ( !ProcAddress )
    return GetLastError();
  v5 = GetProcAddress(*(HMODULE *)this, "SetThreadPreferredUILanguages");
  *((_QWORD *)this + 2) = v5;
  if ( !v5 )
    return GetLastError();
  v6 = GetProcAddress(*(HMODULE *)this, "GetLocaleInfoEx");
  *((_QWORD *)this + 3) = v6;
  if ( !v6 )
    return GetLastError();
  v7 = GetProcAddress(*(HMODULE *)this, "GetNumberFormatEx");
  *((_QWORD *)this + 4) = v7;
  if ( !v7 )
    return GetLastError();
  *((_QWORD *)this + 5) = GetProcAddress(*(HMODULE *)this, "GetPhysicallyInstalledSystemMemory");
  return 0;
}

```

## disassembly

```asm
0x180010768  push    rbx
0x18001076a  sub     rsp, 20h
0x18001076e  mov     rbx, rcx
0x180010771  lea     rcx, aKernel32Dll_0; "Kernel32.dll"
0x180010778  call    cs:__imp_LoadLibraryW
0x18001077e  mov     [rbx], rax
0x180010781  test    rax, rax
0x180010784  jnz     short loc_180010792
0x180010786  add     rsp, 20h
0x18001078a  pop     rbx
0x18001078b  jmp     cs:__imp_GetLastError
0x180010792  lea     rdx, aGetlogicalproc; "GetLogicalProcessorInformation"
0x180010799  mov     rcx, rax; hModule
0x18001079c  call    cs:__imp_GetProcAddress
0x1800107a2  mov     [rbx+8], rax
0x1800107a6  test    rax, rax
0x1800107a9  jz      short loc_180010786
0x1800107ab  mov     rcx, [rbx]; hModule
0x1800107ae  lea     rdx, aSetthreadprefe; "SetThreadPreferredUILanguages"
0x1800107b5  call    cs:__imp_GetProcAddress
0x1800107bb  mov     [rbx+10h], rax
0x1800107bf  test    rax, rax
0x1800107c2  jz      short loc_180010786
0x1800107c4  mov     rcx, [rbx]; hModule
0x1800107c7  lea     rdx, aGetlocaleinfoe; "GetLocaleInfoEx"
0x1800107ce  call    cs:__imp_GetProcAddress
0x1800107d4  mov     [rbx+18h], rax
0x1800107d8  test    rax, rax
0x1800107db  jz      short loc_180010786
0x1800107dd  mov     rcx, [rbx]; hModule
0x1800107e0  lea     rdx, aGetnumberforma; "GetNumberFormatEx"
0x1800107e7  call    cs:__imp_GetProcAddress
0x1800107ed  mov     [rbx+20h], rax
0x1800107f1  test    rax, rax
0x1800107f4  jz      short loc_180010786
0x1800107f6  mov     rcx, [rbx]; hModule
0x1800107f9  lea     rdx, aGetphysicallyi; "GetPhysicallyInstalledSystemMemory"
0x180010800  call    cs:__imp_GetProcAddress
0x180010806  mov     [rbx+28h], rax
0x18001080a  xor     eax, eax
0x18001080c  add     rsp, 20h
0x180010810  pop     rbx
0x180010811  retn
```
