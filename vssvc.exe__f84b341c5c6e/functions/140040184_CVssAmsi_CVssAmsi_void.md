# CVssAmsi::CVssAmsi(void)

- ea: `0x140040184`
- end: `0x140040293`
- name: `??0CVssAmsi@@QEAA@XZ`
- size: `271`
- prototype: `CVssAmsi *__fastcall(CVssAmsi *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, installer_update`

## callers

- `0x140028d60`

## callees

- `0x140040184`
- `0x1400f4010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1400401e4`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1400401f8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14004020c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140040220`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140040234`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1400401e4`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1400401f8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14004020c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140040220`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140040234`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x140040284`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x140040284`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1400401c8`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1400401c8`

## string_xrefs

- `0x140040201`: `AmsiScanBuffer`
- `0x140040215`: `AmsiOpenSession`
- `0x1400401c1`: `amsi.dll`
- `0x1400401ed`: `AmsiUninitialize`
- `0x140040229`: `AmsiCloseSession`
- `0x140040267`: `VSSAMSI`
- `0x1400401da`: `AmsiInitialize`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
0x140040184  push    rbx
0x140040186  sub     rsp, 20h
0x14004018a  mov     rbx, rcx
0x14004018d  mov     byte ptr [rcx+10h], 0
0x140040191  mov     qword ptr [rcx+18h], 0
0x140040199  xor     edx, edx; hFile
0x14004019b  mov     qword ptr [rcx+20h], 0
0x1400401a3  mov     r8d, 800h; dwFlags
0x1400401a9  mov     qword ptr [rcx+28h], 0
0x1400401b1  mov     qword ptr [rcx+30h], 0
0x1400401b9  mov     qword ptr [rcx+38h], 0
0x1400401c1  lea     rcx, aAmsiDll; "amsi.dll"
0x1400401c8  call    cs:__imp_LoadLibraryExW
0x1400401ce  mov     [rbx], rax
0x1400401d1  test    rax, rax
0x1400401d4  jz      loc_14004028A
0x1400401da  lea     rdx, aAmsiinitialize; "AmsiInitialize"
0x1400401e1  mov     rcx, rax; hModule
0x1400401e4  call    cs:__imp_GetProcAddress
0x1400401ea  mov     rcx, [rbx]; hModule
0x1400401ed  lea     rdx, aAmsiuninitiali; "AmsiUninitialize"
0x1400401f4  mov     [rbx+18h], rax
0x1400401f8  call    cs:__imp_GetProcAddress
0x1400401fe  mov     rcx, [rbx]; hModule
0x140040201  lea     rdx, aAmsiscanbuffer; "AmsiScanBuffer"
0x140040208  mov     [rbx+28h], rax
0x14004020c  call    cs:__imp_GetProcAddress
0x140040212  mov     rcx, [rbx]; hModule
0x140040215  lea     rdx, aAmsiopensessio; "AmsiOpenSession"
0x14004021c  mov     [rbx+20h], rax
0x140040220  call    cs:__imp_GetProcAddress
0x140040226  mov     rcx, [rbx]; hModule
0x140040229  lea     rdx, aAmsiclosesessi; "AmsiCloseSession"
0x140040230  mov     [rbx+30h], rax
0x140040234  call    cs:__imp_GetProcAddress
0x14004023a  cmp     qword ptr [rbx+18h], 0
0x14004023f  mov     [rbx+38h], rax
0x140040243  jz      short loc_14004027B
0x140040245  cmp     qword ptr [rbx+20h], 0
0x14004024a  jz      short loc_14004027B
0x14004024c  cmp     qword ptr [rbx+28h], 0
0x140040251  jz      short loc_14004027B
0x140040253  cmp     qword ptr [rbx+30h], 0
0x140040258  jz      short loc_14004027B
0x14004025a  test    rax, rax
0x14004025d  jz      short loc_14004027B
0x14004025f  mov     rax, [rbx+18h]
0x140040263  lea     rdx, [rbx+8]
0x140040267  lea     rcx, aVssamsi; "VSSAMSI"
0x14004026e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140040273  test    eax, eax
0x140040275  js      short loc_14004027B
0x140040277  mov     byte ptr [rbx+10h], 1
0x14004027b  cmp     byte ptr [rbx+10h], 0
0x14004027f  jnz     short loc_14004028A
0x140040281  mov     rcx, [rbx]; hLibModule
0x140040284  call    cs:__imp_FreeLibrary
0x14004028a  mov     rax, rbx
0x14004028d  add     rsp, 20h
0x140040291  pop     rbx
0x140040292  retn
```
