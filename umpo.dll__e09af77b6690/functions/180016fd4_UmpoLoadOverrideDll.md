# UmpoLoadOverrideDll

- ea: `0x180016fd4`
- end: `0x1800170f5`
- name: `UmpoLoadOverrideDll`
- size: `289`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `2`
- tags: `reparse_path, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18000a574`

## callees

- `0x18000f3dc`
- `0x180016fd4`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x180016ff3`
- `ntdll!RtlAllocateHeap` at `0x180016ff3`
- `ntdll!RtlFreeHeap` at `0x1800170e0`
- `ntdll!RtlFreeHeap` at `0x1800170e0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017063`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017063`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180017055`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180017089`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001709c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180017055`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180017089`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001709c`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18001703d`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18001703d`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180017077`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180017077`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180017015`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180017015`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x18001702b`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x18001702b`

## string_xrefs

- `0x18001708f`: `UmpoDisablePowerSettingOverrideUpdates`
- `0x18001707f`: `UmpoEnablePowerSettingOverrideUpdates`
- `0x18001701f`: `umpo-overrides.dll`

## pseudocode

```c
__int64 UmpoLoadOverrideDll()
{
  WCHAR *Heap; // rax
  WCHAR *v1; // rsi
  DWORD LastError; // ebx
  HMODULE v3; // rdi
  HMODULE Library; // rax
  FARPROC v5; // r14
  FARPROC ProcAddress; // rbp
  FARPROC v7; // r15

  Heap = (WCHAR *)RtlAllocateHeap(UmpoHeapHandle, 8u, 0x208u);
  v1 = Heap;
  if ( Heap )
  {
    v3 = 0;
    if ( GetSystemDirectoryW(Heap, 0x104u)
      && PathCchAppend(v1, 0x104u, L"umpo-overrides.dll") >= 0
      && (Library = LoadLibraryExW(v1, 0, 0), (v3 = Library) != 0)
      && (v5 = GetProcAddress(Library, "UmpoGetPowerSettingOverrides")) != 0 )
    {
      ProcAddress = GetProcAddress(v3, "UmpoEnablePowerSettingOverrideUpdates");
      v7 = GetProcAddress(v3, "UmpoDisablePowerSettingOverrideUpdates");
      if ( !v7 )
      {
        if ( ProcAddress )
          MicrosoftTelemetryAssertTriggeredNoArgs();
        ProcAddress = 0;
      }
      LastError = 0;
      UmpoOverrideDllHandle = v3;
      UmpoOverrideFn = (__int64)v5;
      UmpoOverrideUpdateEnableFn = (__int64)ProcAddress;
      UmpoOverrideUpdateDisableFn = (__int64)v7;
    }
    else
    {
      LastError = GetLastError();
      if ( LastError && v3 )
        FreeLibrary(v3);
    }
    RtlFreeHeap(UmpoHeapHandle, 0, v1);
  }
  else
  {
    return 14;
  }
  return LastError;
}

```

## disassembly

```asm
0x180016fd4  push    rbx
0x180016fd6  push    rbp
0x180016fd7  push    rsi
0x180016fd8  push    rdi
0x180016fd9  push    r14
0x180016fdb  push    r15
0x180016fdd  sub     rsp, 28h
0x180016fe1  mov     rcx, cs:UmpoHeapHandle; HeapHandle
0x180016fe8  mov     edx, 8; Flags
0x180016fed  mov     r8d, 208h; Size
0x180016ff3  call    cs:__imp_RtlAllocateHeap
0x180016ff9  mov     rsi, rax
0x180016ffc  test    rax, rax
0x180016fff  jnz     short loc_180017009
0x180017001  lea     ebx, [rax+0Eh]
0x180017004  jmp     loc_1800170E6
0x180017009  mov     ebx, 104h
0x18001700e  mov     rcx, rsi; lpBuffer
0x180017011  mov     edx, ebx; uSize
0x180017013  xor     edi, edi
0x180017015  call    cs:__imp_GetSystemDirectoryW
0x18001701b  test    eax, eax
0x18001701d  jz      short loc_180017063
0x18001701f  lea     r8, pszMore; "umpo-overrides.dll"
0x180017026  mov     edx, ebx; cchPath
0x180017028  mov     rcx, rsi; pszPath
0x18001702b  call    cs:__imp_PathCchAppend
0x180017031  test    eax, eax
0x180017033  js      short loc_180017063
0x180017035  xor     r8d, r8d; dwFlags
0x180017038  xor     edx, edx; hFile
0x18001703a  mov     rcx, rsi; lpLibFileName
0x18001703d  call    cs:__imp_LoadLibraryExW
0x180017043  mov     rdi, rax
0x180017046  test    rax, rax
0x180017049  jz      short loc_180017063
0x18001704b  lea     rdx, aUmpogetpowerse; "UmpoGetPowerSettingOverrides"
0x180017052  mov     rcx, rax; hModule
0x180017055  call    cs:__imp_GetProcAddress
0x18001705b  mov     r14, rax
0x18001705e  test    rax, rax
0x180017061  jnz     short loc_18001707F
0x180017063  call    cs:__imp_GetLastError
0x180017069  mov     ebx, eax
0x18001706b  test    eax, eax
0x18001706d  jz      short loc_1800170D4
0x18001706f  test    rdi, rdi
0x180017072  jz      short loc_1800170D4
0x180017074  mov     rcx, rdi; hLibModule
0x180017077  call    cs:__imp_FreeLibrary
0x18001707d  jmp     short loc_1800170D4
0x18001707f  lea     rdx, aUmpoenablepowe; "UmpoEnablePowerSettingOverrideUpdates"
0x180017086  mov     rcx, rdi; hModule
0x180017089  call    cs:__imp_GetProcAddress
0x18001708f  lea     rdx, aUmpodisablepow; "UmpoDisablePowerSettingOverrideUpdates"
0x180017096  mov     rcx, rdi; hModule
0x180017099  mov     rbp, rax
0x18001709c  call    cs:__imp_GetProcAddress
0x1800170a2  mov     r15, rax
0x1800170a5  test    rax, rax
0x1800170a8  jnz     short loc_1800170B6
0x1800170aa  test    rbp, rbp
0x1800170ad  jz      short loc_1800170B4
0x1800170af  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800170b4  xor     ebp, ebp
0x1800170b6  xor     ebx, ebx
0x1800170b8  mov     cs:UmpoOverrideDllHandle, rdi
0x1800170bf  mov     cs:UmpoOverrideFn, r14
0x1800170c6  mov     cs:UmpoOverrideUpdateEnableFn, rbp
0x1800170cd  mov     cs:UmpoOverrideUpdateDisableFn, r15
0x1800170d4  mov     rcx, cs:UmpoHeapHandle; HeapHandle
0x1800170db  mov     r8, rsi; P
0x1800170de  xor     edx, edx; Flags
0x1800170e0  call    cs:__imp_RtlFreeHeap
0x1800170e6  mov     eax, ebx
0x1800170e8  add     rsp, 28h
0x1800170ec  pop     r15
0x1800170ee  pop     r14
0x1800170f0  pop     rdi
0x1800170f1  pop     rsi
0x1800170f2  pop     rbp
0x1800170f3  pop     rbx
0x1800170f4  retn
```
