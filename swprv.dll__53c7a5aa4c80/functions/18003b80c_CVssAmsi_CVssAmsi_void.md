# CVssAmsi::CVssAmsi(void)

- ea: `0x18003b80c`
- end: `0x18003b91b`
- name: `??0CVssAmsi@@QEAA@XZ`
- size: `271`
- prototype: `CVssAmsi *__fastcall(CVssAmsi *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, installer_update`

## callers

- `0x18000aa5c`

## callees

- `0x18003b80c`
- `0x18004b010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18003b850`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18003b850`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003b86c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003b880`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003b894`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003b8a8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003b8bc`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003b86c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003b880`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003b894`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003b8a8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003b8bc`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18003b90c`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18003b90c`

## string_xrefs

- `0x18003b849`: `amsi.dll`
- `0x18003b862`: `AmsiInitialize`
- `0x18003b875`: `AmsiUninitialize`
- `0x18003b889`: `AmsiScanBuffer`
- `0x18003b89d`: `AmsiOpenSession`
- `0x18003b8b1`: `AmsiCloseSession`
- `0x18003b8ef`: `VSSAMSI`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
CVssAmsi *__fastcall CVssAmsi::CVssAmsi(CVssAmsi *this)
{
  HMODULE Library; // rax
  FARPROC ProcAddress; // rax
  HMODULE v4; // rcx
  FARPROC v5; // rax
  HMODULE v6; // rcx
  FARPROC v7; // rax
  HMODULE v8; // rcx
  FARPROC v9; // rax
  HMODULE v10; // rcx
  FARPROC v11; // rax
  bool v12; // zf

  *((_BYTE *)this + 16) = 0;
  *((_QWORD *)this + 3) = 0;
  *((_QWORD *)this + 4) = 0;
  *((_QWORD *)this + 5) = 0;
  *((_QWORD *)this + 6) = 0;
  *((_QWORD *)this + 7) = 0;
  Library = LoadLibraryExW(L"amsi.dll", 0, 0x800u);
  *(_QWORD *)this = Library;
  if ( Library )
  {
    ProcAddress = GetProcAddress(Library, "AmsiInitialize");
    v4 = *(HMODULE *)this;
    *((_QWORD *)this + 3) = ProcAddress;
    v5 = GetProcAddress(v4, "AmsiUninitialize");
    v6 = *(HMODULE *)this;
    *((_QWORD *)this + 5) = v5;
    v7 = GetProcAddress(v6, "AmsiScanBuffer");
    v8 = *(HMODULE *)this;
    *((_QWORD *)this + 4) = v7;
    v9 = GetProcAddress(v8, "AmsiOpenSession");
    v10 = *(HMODULE *)this;
    *((_QWORD *)this + 6) = v9;
    v11 = GetProcAddress(v10, "AmsiCloseSession");
    v12 = *((_QWORD *)this + 3) == 0;
    *((_QWORD *)this + 7) = v11;
    if ( !v12
      && *((_QWORD *)this + 4)
      && *((_QWORD *)this + 5)
      && *((_QWORD *)this + 6)
      && v11
      && (*((int (__fastcall **)(const wchar_t *, char *))this + 3))(L"VSSAMSI", (char *)this + 8) >= 0 )
    {
      *((_BYTE *)this + 16) = 1;
    }
    if ( !*((_BYTE *)this + 16) )
      FreeLibrary(*(HMODULE *)this);
  }
  return this;
}

```

## disassembly

```asm
0x18003b80c  push    rbx
0x18003b80e  sub     rsp, 20h
0x18003b812  mov     rbx, rcx
0x18003b815  mov     byte ptr [rcx+10h], 0
0x18003b819  mov     qword ptr [rcx+18h], 0
0x18003b821  xor     edx, edx; hFile
0x18003b823  mov     qword ptr [rcx+20h], 0
0x18003b82b  mov     r8d, 800h; dwFlags
0x18003b831  mov     qword ptr [rcx+28h], 0
0x18003b839  mov     qword ptr [rcx+30h], 0
0x18003b841  mov     qword ptr [rcx+38h], 0
0x18003b849  lea     rcx, aAmsiDll; "amsi.dll"
0x18003b850  call    cs:__imp_LoadLibraryExW
0x18003b856  mov     [rbx], rax
0x18003b859  test    rax, rax
0x18003b85c  jz      loc_18003B912
0x18003b862  lea     rdx, aAmsiinitialize; "AmsiInitialize"
0x18003b869  mov     rcx, rax; hModule
0x18003b86c  call    cs:__imp_GetProcAddress
0x18003b872  mov     rcx, [rbx]; hModule
0x18003b875  lea     rdx, aAmsiuninitiali; "AmsiUninitialize"
0x18003b87c  mov     [rbx+18h], rax
0x18003b880  call    cs:__imp_GetProcAddress
0x18003b886  mov     rcx, [rbx]; hModule
0x18003b889  lea     rdx, aAmsiscanbuffer; "AmsiScanBuffer"
0x18003b890  mov     [rbx+28h], rax
0x18003b894  call    cs:__imp_GetProcAddress
0x18003b89a  mov     rcx, [rbx]; hModule
0x18003b89d  lea     rdx, aAmsiopensessio; "AmsiOpenSession"
0x18003b8a4  mov     [rbx+20h], rax
0x18003b8a8  call    cs:__imp_GetProcAddress
0x18003b8ae  mov     rcx, [rbx]; hModule
0x18003b8b1  lea     rdx, aAmsiclosesessi; "AmsiCloseSession"
0x18003b8b8  mov     [rbx+30h], rax
0x18003b8bc  call    cs:__imp_GetProcAddress
0x18003b8c2  cmp     qword ptr [rbx+18h], 0
0x18003b8c7  mov     [rbx+38h], rax
0x18003b8cb  jz      short loc_18003B903
0x18003b8cd  cmp     qword ptr [rbx+20h], 0
0x18003b8d2  jz      short loc_18003B903
0x18003b8d4  cmp     qword ptr [rbx+28h], 0
0x18003b8d9  jz      short loc_18003B903
0x18003b8db  cmp     qword ptr [rbx+30h], 0
0x18003b8e0  jz      short loc_18003B903
0x18003b8e2  test    rax, rax
0x18003b8e5  jz      short loc_18003B903
0x18003b8e7  mov     rax, [rbx+18h]
0x18003b8eb  lea     rdx, [rbx+8]
0x18003b8ef  lea     rcx, aVssamsi; "VSSAMSI"
0x18003b8f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b8fb  test    eax, eax
0x18003b8fd  js      short loc_18003B903
0x18003b8ff  mov     byte ptr [rbx+10h], 1
0x18003b903  cmp     byte ptr [rbx+10h], 0
0x18003b907  jnz     short loc_18003B912
0x18003b909  mov     rcx, [rbx]; hLibModule
0x18003b90c  call    cs:__imp_FreeLibrary
0x18003b912  mov     rax, rbx
0x18003b915  add     rsp, 20h
0x18003b919  pop     rbx
0x18003b91a  retn
```
