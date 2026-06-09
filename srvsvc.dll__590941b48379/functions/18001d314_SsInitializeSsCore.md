# SsInitializeSsCore

- ea: `0x18001d314`
- end: `0x18001d679`
- name: `SsInitializeSsCore`
- size: `869`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180015500`

## callees

- `0x18001d314`
- `0x180020de8`
- `0x180044010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d33e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d610`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d33e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d610`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18001d32a`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18001d32a`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18001d65f`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18001d65f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001d396`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001d3b1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001d3cc`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001d3e7`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001d402`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001d41d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001d438`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001d453`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001d46e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001d489`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001d4a4`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001d4bf`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001d4da`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001d4f5`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001d510`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001d396`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001d3b1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001d3cc`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001d3e7`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001d402`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001d41d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001d438`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001d453`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001d46e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001d489`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001d4a4`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001d4bf`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001d4da`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001d4f5`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001d510`

## string_xrefs

- `0x18001d321`: `SSCORE.DLL`
- `0x18001d3be`: `SsCoreShareAdd`
- `0x18001d3d9`: `SsCoreShareAddEx`
- `0x18001d4e7`: `SsCoreOpenInstance`

## pseudocode

```c
__int64 SsInitializeSsCore()
{
  HMODULE Library; // rax
  DWORD LastError; // ebx
  FARPROC ProcAddress; // rax

  Library = LoadLibraryExW(L"SSCORE.DLL", 0, 0);
  hLibModule = Library;
  if ( !Library )
  {
    LastError = GetLastError();
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 84, WPP_539c1b1611e137709d0d7dc2103426d1_Traceguids, LastError);
    }
    goto LABEL_30;
  }
  qword_18005E4D8 = (__int64)GetProcAddress(Library, "SsCoreInitializeEx");
  qword_18005E4E0 = (__int64)GetProcAddress(hLibModule, "SsCoreUninitialize");
  qword_18005E4E8 = (__int64)GetProcAddress(hLibModule, "SsCoreShareAdd");
  qword_18005E4F0 = (__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD))GetProcAddress(
                                                                                              hLibModule,
                                                                                              "SsCoreShareAddEx");
  qword_18005E4F8 = (__int64)GetProcAddress(hLibModule, "SsCoreShareSetInfo");
  qword_18005E500 = (__int64)GetProcAddress(hLibModule, "SsCoreShareDel");
  qword_18005E508 = (__int64)GetProcAddress(hLibModule, "SsCoreShareCleanup");
  qword_18005E510 = (__int64)GetProcAddress(hLibModule, "SsCoreAliasAddEx");
  qword_18005E518 = (__int64)GetProcAddress(hLibModule, "SsCoreAliasDelEx");
  qword_18005E520 = (__int64)GetProcAddress(hLibModule, "SsCoreSessionEnumForInstance");
  qword_18005E528 = (__int64)GetProcAddress(hLibModule, "SsCoreSessionDel");
  qword_18005E530 = (__int64)GetProcAddress(hLibModule, "SsCoreFileEnumForInstance");
  qword_18005E538 = (__int64)GetProcAddress(hLibModule, "SsCoreFileDel");
  qword_18005E540 = (__int64)GetProcAddress(hLibModule, "SsCoreOpenInstance");
  ProcAddress = GetProcAddress(hLibModule, "SsCoreCloseInstance");
  qword_18005E548 = (__int64)ProcAddress;
  if ( !qword_18005E4D8
    || !qword_18005E4E0
    || !qword_18005E4E8
    || !qword_18005E4F8
    || !qword_18005E500
    || !qword_18005E508
    || !qword_18005E510
    || !qword_18005E518
    || !qword_18005E4F0
    || !qword_18005E520
    || !qword_18005E528
    || !qword_18005E530
    || !qword_18005E538
    || !qword_18005E540
    || !ProcAddress )
  {
    LastError = GetLastError();
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 85, WPP_539c1b1611e137709d0d7dc2103426d1_Traceguids, LastError);
    }
LABEL_30:
    if ( !LastError )
      return LastError;
    goto LABEL_31;
  }
  LastError = ((__int64 (__fastcall *)(_QWORD))qword_18005E4D8)(0);
  if ( !LastError )
    return LastError;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 86, WPP_539c1b1611e137709d0d7dc2103426d1_Traceguids, LastError);
  }
LABEL_31:
  if ( hLibModule )
  {
    FreeLibrary(hLibModule);
    hLibModule = 0;
  }
  return LastError;
}

```

## disassembly

```asm
0x18001d314  mov     [rsp+arg_0], rbx
0x18001d319  push    rdi
0x18001d31a  sub     rsp, 20h
0x18001d31e  xor     r8d, r8d; dwFlags
0x18001d321  lea     rcx, aSscoreDll; "SSCORE.DLL"
0x18001d328  xor     edx, edx; hFile
0x18001d32a  call    cs:__imp_LoadLibraryExW
0x18001d330  xor     edi, edi
0x18001d332  mov     cs:hLibModule, rax
0x18001d339  test    rax, rax
0x18001d33c  jnz     short loc_18001D38C
0x18001d33e  call    cs:__imp_GetLastError
0x18001d344  mov     ebx, eax
0x18001d346  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d34d  lea     rax, WPP_GLOBAL_Control
0x18001d354  cmp     rcx, rax
0x18001d357  jz      loc_18001D64F
0x18001d35d  test    byte ptr [rcx+1Ch], 1
0x18001d361  jz      loc_18001D64F
0x18001d367  cmp     byte ptr [rcx+19h], 1
0x18001d36b  jb      loc_18001D64F
0x18001d371  mov     rcx, [rcx+10h]
0x18001d375  lea     edx, [rdi+54h]
0x18001d378  mov     r9d, ebx
0x18001d37b  lea     r8, WPP_539c1b1611e137709d0d7dc2103426d1_Traceguids
0x18001d382  call    WPP_SF_d
0x18001d387  jmp     loc_18001D64F
0x18001d38c  lea     rdx, aSscoreinitiali; "SsCoreInitializeEx"
0x18001d393  mov     rcx, rax; hModule
0x18001d396  call    cs:__imp_GetProcAddress
0x18001d39c  mov     rcx, cs:hLibModule; hModule
0x18001d3a3  lea     rdx, aSscoreuninitia; "SsCoreUninitialize"
0x18001d3aa  mov     cs:qword_18005E4D8, rax
0x18001d3b1  call    cs:__imp_GetProcAddress
0x18001d3b7  mov     rcx, cs:hLibModule; hModule
0x18001d3be  lea     rdx, aSscoreshareadd_0; "SsCoreShareAdd"
0x18001d3c5  mov     cs:qword_18005E4E0, rax
0x18001d3cc  call    cs:__imp_GetProcAddress
0x18001d3d2  mov     rcx, cs:hLibModule; hModule
0x18001d3d9  lea     rdx, aSscoreshareadd; "SsCoreShareAddEx"
0x18001d3e0  mov     cs:qword_18005E4E8, rax
0x18001d3e7  call    cs:__imp_GetProcAddress
0x18001d3ed  mov     rcx, cs:hLibModule; hModule
0x18001d3f4  lea     rdx, aSscoreshareset; "SsCoreShareSetInfo"
0x18001d3fb  mov     cs:qword_18005E4F0, rax
0x18001d402  call    cs:__imp_GetProcAddress
0x18001d408  mov     rcx, cs:hLibModule; hModule
0x18001d40f  lea     rdx, aSscoresharedel; "SsCoreShareDel"
0x18001d416  mov     cs:qword_18005E4F8, rax
0x18001d41d  call    cs:__imp_GetProcAddress
0x18001d423  mov     rcx, cs:hLibModule; hModule
0x18001d42a  lea     rdx, aSscoresharecle; "SsCoreShareCleanup"
0x18001d431  mov     cs:qword_18005E500, rax
0x18001d438  call    cs:__imp_GetProcAddress
0x18001d43e  mov     rcx, cs:hLibModule; hModule
0x18001d445  lea     rdx, aSscorealiasadd; "SsCoreAliasAddEx"
0x18001d44c  mov     cs:qword_18005E508, rax
0x18001d453  call    cs:__imp_GetProcAddress
0x18001d459  mov     rcx, cs:hLibModule; hModule
0x18001d460  lea     rdx, aSscorealiasdel; "SsCoreAliasDelEx"
0x18001d467  mov     cs:qword_18005E510, rax
0x18001d46e  call    cs:__imp_GetProcAddress
0x18001d474  mov     rcx, cs:hLibModule; hModule
0x18001d47b  lea     rdx, aSscoresessione; "SsCoreSessionEnumForInstance"
0x18001d482  mov     cs:qword_18005E518, rax
0x18001d489  call    cs:__imp_GetProcAddress
0x18001d48f  mov     rcx, cs:hLibModule; hModule
0x18001d496  lea     rdx, aSscoresessiond; "SsCoreSessionDel"
0x18001d49d  mov     cs:qword_18005E520, rax
0x18001d4a4  call    cs:__imp_GetProcAddress
0x18001d4aa  mov     rcx, cs:hLibModule; hModule
0x18001d4b1  lea     rdx, aSscorefileenum; "SsCoreFileEnumForInstance"
0x18001d4b8  mov     cs:qword_18005E528, rax
0x18001d4bf  call    cs:__imp_GetProcAddress
0x18001d4c5  mov     rcx, cs:hLibModule; hModule
0x18001d4cc  lea     rdx, aSscorefiledel; "SsCoreFileDel"
0x18001d4d3  mov     cs:qword_18005E530, rax
0x18001d4da  call    cs:__imp_GetProcAddress
0x18001d4e0  mov     rcx, cs:hLibModule; hModule
0x18001d4e7  lea     rdx, aSscoreopeninst; "SsCoreOpenInstance"
0x18001d4ee  mov     cs:qword_18005E538, rax
0x18001d4f5  call    cs:__imp_GetProcAddress
0x18001d4fb  mov     rcx, cs:hLibModule; hModule
0x18001d502  lea     rdx, aSscorecloseins; "SsCoreCloseInstance"
0x18001d509  mov     cs:qword_18005E540, rax
0x18001d510  call    cs:__imp_GetProcAddress
0x18001d516  mov     rdx, cs:qword_18005E4D8
0x18001d51d  mov     cs:qword_18005E548, rax
0x18001d524  test    rdx, rdx
0x18001d527  jz      loc_18001D610
0x18001d52d  cmp     cs:qword_18005E4E0, rdi
0x18001d534  jz      loc_18001D610
0x18001d53a  cmp     cs:qword_18005E4E8, rdi
0x18001d541  jz      loc_18001D610
0x18001d547  cmp     cs:qword_18005E4F8, rdi
0x18001d54e  jz      loc_18001D610
0x18001d554  cmp     cs:qword_18005E500, rdi
0x18001d55b  jz      loc_18001D610
0x18001d561  cmp     cs:qword_18005E508, rdi
0x18001d568  jz      loc_18001D610
0x18001d56e  cmp     cs:qword_18005E510, rdi
0x18001d575  jz      loc_18001D610
0x18001d57b  cmp     cs:qword_18005E518, rdi
0x18001d582  jz      loc_18001D610
0x18001d588  cmp     cs:qword_18005E4F0, rdi
0x18001d58f  jz      short loc_18001D610
0x18001d591  cmp     cs:qword_18005E520, rdi
0x18001d598  jz      short loc_18001D610
0x18001d59a  cmp     cs:qword_18005E528, rdi
0x18001d5a1  jz      short loc_18001D610
0x18001d5a3  cmp     cs:qword_18005E530, rdi
0x18001d5aa  jz      short loc_18001D610
0x18001d5ac  cmp     cs:qword_18005E538, rdi
0x18001d5b3  jz      short loc_18001D610
0x18001d5b5  cmp     cs:qword_18005E540, rdi
0x18001d5bc  jz      short loc_18001D610
0x18001d5be  test    rax, rax
0x18001d5c1  jz      short loc_18001D610
0x18001d5c3  xor     ecx, ecx
0x18001d5c5  mov     rax, rdx
0x18001d5c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d5cd  mov     ebx, eax
0x18001d5cf  test    eax, eax
0x18001d5d1  jz      loc_18001D66C
0x18001d5d7  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d5de  lea     rax, WPP_GLOBAL_Control
0x18001d5e5  cmp     rcx, rax
0x18001d5e8  jz      short loc_18001D653
0x18001d5ea  test    byte ptr [rcx+1Ch], 1
0x18001d5ee  jz      short loc_18001D653
0x18001d5f0  cmp     byte ptr [rcx+19h], 1
0x18001d5f4  jb      short loc_18001D653
0x18001d5f6  mov     rcx, [rcx+10h]
0x18001d5fa  lea     r8, WPP_539c1b1611e137709d0d7dc2103426d1_Traceguids
0x18001d601  mov     edx, 56h ; 'V'
0x18001d606  mov     r9d, ebx
0x18001d609  call    WPP_SF_d
0x18001d60e  jmp     short loc_18001D653
0x18001d610  call    cs:__imp_GetLastError
0x18001d616  mov     ebx, eax
0x18001d618  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d61f  lea     rax, WPP_GLOBAL_Control
0x18001d626  cmp     rcx, rax
0x18001d629  jz      short loc_18001D64F
0x18001d62b  test    byte ptr [rcx+1Ch], 1
0x18001d62f  jz      short loc_18001D64F
0x18001d631  cmp     byte ptr [rcx+19h], 1
0x18001d635  jb      short loc_18001D64F
0x18001d637  mov     rcx, [rcx+10h]
0x18001d63b  lea     r8, WPP_539c1b1611e137709d0d7dc2103426d1_Traceguids
0x18001d642  mov     edx, 55h ; 'U'
0x18001d647  mov     r9d, ebx
0x18001d64a  call    WPP_SF_d
0x18001d64f  test    ebx, ebx
0x18001d651  jz      short loc_18001D66C
0x18001d653  mov     rcx, cs:hLibModule; hLibModule
0x18001d65a  test    rcx, rcx
0x18001d65d  jz      short loc_18001D66C
0x18001d65f  call    cs:__imp_FreeLibrary
0x18001d665  mov     cs:hLibModule, rdi
0x18001d66c  mov     eax, ebx
0x18001d66e  mov     rbx, [rsp+28h+arg_0]
0x18001d673  add     rsp, 20h
0x18001d677  pop     rdi
0x18001d678  retn
```
