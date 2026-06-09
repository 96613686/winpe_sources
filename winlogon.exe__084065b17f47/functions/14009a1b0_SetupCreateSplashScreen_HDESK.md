# SetupCreateSplashScreen(HDESK__ *)

- ea: `0x14009a1b0`
- end: `0x14009a245`
- name: `?SetupCreateSplashScreen@@YAXPEAUHDESK__@@@Z`
- size: `149`
- prototype: `void __fastcall(HDESK)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, installer_update`

## callers

- `0x1400877f0`

## callees

- `0x14009a1b0`
- `0x1400a1010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x14009a1c5`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x14009a1c5`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14009a1e1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14009a201`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14009a1e1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14009a201`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x14009a22e`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x14009a22e`

## string_xrefs

- `0x14009a1bc`: `oobe\WinLGDep.dll`
- `0x14009a1d7`: `CreateSplashWindows`

## pseudocode

```c
void __fastcall SetupCreateSplashScreen(HDESK a1)
{
  HMODULE Library; // rax

  Library = LoadLibraryExW(L"oobe\\WinLGDep.dll", 0, 0);
  hLibModule = Library;
  if ( Library )
  {
    qword_1400D33B8 = (__int64)GetProcAddress(Library, "CreateSplashWindows");
    if ( qword_1400D33B8 && (qword_1400D33B0 = (__int64)GetProcAddress(hLibModule, "DestroySplashWindows")) != 0 )
    {
      ((void (__fastcall *)(HDESK))qword_1400D33B8)(a1);
    }
    else
    {
      FreeLibrary(hLibModule);
      hLibModule = 0;
    }
  }
}

```

## disassembly

```asm
0x14009a1b0  push    rbx
0x14009a1b2  sub     rsp, 20h
0x14009a1b6  mov     rbx, rcx
0x14009a1b9  xor     r8d, r8d; dwFlags
0x14009a1bc  lea     rcx, aOobeWinlgdepDl; "oobe\\WinLGDep.dll"
0x14009a1c3  xor     edx, edx; hFile
0x14009a1c5  call    cs:__imp_LoadLibraryExW
0x14009a1cb  mov     cs:hLibModule, rax
0x14009a1d2  test    rax, rax
0x14009a1d5  jz      short loc_14009A23F
0x14009a1d7  lea     rdx, aCreatesplashwi; "CreateSplashWindows"
0x14009a1de  mov     rcx, rax; hModule
0x14009a1e1  call    cs:__imp_GetProcAddress
0x14009a1e7  mov     cs:qword_1400D33B8, rax
0x14009a1ee  test    rax, rax
0x14009a1f1  jz      short loc_14009A227
0x14009a1f3  mov     rcx, cs:hLibModule; hModule
0x14009a1fa  lea     rdx, aDestroysplashw; "DestroySplashWindows"
0x14009a201  call    cs:__imp_GetProcAddress
0x14009a207  mov     cs:qword_1400D33B0, rax
0x14009a20e  test    rax, rax
0x14009a211  jz      short loc_14009A227
0x14009a213  mov     rax, cs:qword_1400D33B8
0x14009a21a  mov     rcx, rbx
0x14009a21d  add     rsp, 20h
0x14009a221  pop     rbx
0x14009a222  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x14009a227  mov     rcx, cs:hLibModule; hLibModule
0x14009a22e  call    cs:__imp_FreeLibrary
0x14009a234  mov     cs:hLibModule, 0
0x14009a23f  add     rsp, 20h
0x14009a243  pop     rbx
0x14009a244  retn
```
