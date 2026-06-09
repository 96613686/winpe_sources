# ResolveCfgmgr32Imports

- ea: `0x18000a0a8`
- end: `0x18000a175`
- name: `ResolveCfgmgr32Imports`
- size: `205`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180009cb0`

## callees

- `0x18000a0a8`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000a101`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000a12b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000a155`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000a101`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000a12b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000a155`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18000a0c4`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18000a0c4`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000a0e3`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000a0e3`

## string_xrefs

- `0x18000a0bb`: `cfgmgr32.dll`

## pseudocode

```c
__int64 ResolveCfgmgr32Imports()
{
  HMODULE Library; // rax
  FARPROC ProcAddress; // rax
  FARPROC v2; // rax
  FARPROC v3; // rax

  if ( !hModule )
  {
    Library = LoadLibraryExW(L"cfgmgr32.dll", 0, 0);
    if ( !Library )
      return 0;
    if ( _InterlockedCompareExchange64((volatile signed __int64 *)&hModule, (signed __int64)Library, 0) )
      FreeLibrary(Library);
  }
  if ( !qword_18007C5E8 )
  {
    ProcAddress = GetProcAddress(hModule, "CM_Unregister_Notification");
    if ( !ProcAddress )
      return 0;
    _InterlockedExchange64(&qword_18007C5E8, (__int64)ProcAddress);
  }
  if ( qword_18007C5D8 )
    goto LABEL_11;
  v2 = GetProcAddress(hModule, "CMP_Register_Notification");
  if ( !v2 )
    return 0;
  _InterlockedExchange64(&qword_18007C5D8, (__int64)v2);
LABEL_11:
  if ( !qword_18007C5E0 )
  {
    v3 = GetProcAddress(hModule, "CM_MapCrToWin32Err");
    if ( !v3 )
      return 0;
    _InterlockedExchange64(&qword_18007C5E0, (__int64)v3);
  }
  return 1;
}

```

## disassembly

```asm
0x18000a0a8  sub     rsp, 28h
0x18000a0ac  mov     rax, cs:hModule
0x18000a0b3  test    rax, rax
0x18000a0b6  jnz     short loc_18000A0E9
0x18000a0b8  xor     r8d, r8d; dwFlags
0x18000a0bb  lea     rcx, LibFileName; "cfgmgr32.dll"
0x18000a0c2  xor     edx, edx; hFile
0x18000a0c4  call    cs:__imp_LoadLibraryExW
0x18000a0ca  mov     rcx, rax; hLibModule
0x18000a0cd  test    rax, rax
0x18000a0d0  jz      loc_18000A160
0x18000a0d6  xor     eax, eax
0x18000a0d8  lock cmpxchg cs:hModule, rcx
0x18000a0e1  jz      short loc_18000A0E9
0x18000a0e3  call    cs:__imp_FreeLibrary
0x18000a0e9  cmp     cs:qword_18007C5E8, 0
0x18000a0f1  jnz     short loc_18000A113
0x18000a0f3  mov     rcx, cs:hModule; hModule
0x18000a0fa  lea     rdx, ProcName; "CM_Unregister_Notification"
0x18000a101  call    cs:__imp_GetProcAddress
0x18000a107  test    rax, rax
0x18000a10a  jz      short loc_18000A160
0x18000a10c  xchg    rax, cs:qword_18007C5E8
0x18000a113  cmp     cs:qword_18007C5D8, 0
0x18000a11b  jnz     short loc_18000A13D
0x18000a11d  mov     rcx, cs:hModule; hModule
0x18000a124  lea     rdx, aCmpRegisterNot; "CMP_Register_Notification"
0x18000a12b  call    cs:__imp_GetProcAddress
0x18000a131  test    rax, rax
0x18000a134  jz      short loc_18000A160
0x18000a136  xchg    rax, cs:qword_18007C5D8
0x18000a13d  cmp     cs:qword_18007C5E0, 0
0x18000a145  jnz     short loc_18000A16B
0x18000a147  mov     rcx, cs:hModule; hModule
0x18000a14e  lea     rdx, aCmMapcrtowin32; "CM_MapCrToWin32Err"
0x18000a155  call    cs:__imp_GetProcAddress
0x18000a15b  test    rax, rax
0x18000a15e  jnz     short loc_18000A164
0x18000a160  xor     eax, eax
0x18000a162  jmp     short loc_18000A170
0x18000a164  xchg    rax, cs:qword_18007C5E0
0x18000a16b  mov     eax, 1
0x18000a170  add     rsp, 28h
0x18000a174  retn
```
