# UserServerDllInitialization

- ea: `0x180001060`
- end: `0x180001113`
- name: `UserServerDllInitialization`
- size: `179`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting`

## callees

- `0x180001060`
- `0x1800013ac`
- `0x18000148c`
- `0x180001bc0`
- `0x180002010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800010c6`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800010c6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800010e1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800010e1`
- `api-ms-win-core-apiquery-l2-1-0!IsApiSetImplemented` at `0x1800010a7`
- `api-ms-win-core-apiquery-l2-1-0!IsApiSetImplemented` at `0x1800010a7`
- `ext-ms-win-core-winsrv-l1-1-0!UserServerDllInitializationExt` at `0x18000107a`
- `ext-ms-win-core-winsrv-min-l1-1-0!UserServerDllInitializationMin` at `0x180001092`
- `ext-ms-win-core-winsrv-min-l1-1-0!UserServerDllInitializationMin` at `0x180001092`

## string_xrefs

- `0x1800010b9`: `win32u.dll`

## pseudocode

```c
__int64 __fastcall UserServerDllInitialization(__int64 a1)
{
  HMODULE Library; // rax
  FARPROC ProcAddress; // rax

  if ( (unsigned __int8)IsUserServerDllInitializationExtPresent() )
    return UserServerDllInitializationExt(a1);
  if ( (unsigned __int8)IsUserServerDllInitializationMinPresent() )
    return UserServerDllInitializationMin(a1);
  if ( !IsApiSetImplemented("ext-ms-win-core-win32k-userinit-l1-1-0") )
    goto LABEL_9;
  Library = LoadLibraryExW(L"win32u.dll", 0, 0x800u);
  if ( !Library )
    goto LABEL_9;
  ProcAddress = GetProcAddress(Library, "NtUserInitialize");
  if ( ProcAddress )
  {
    ((void (__fastcall *)(_QWORD, _QWORD))ProcAddress)(0, 0);
LABEL_9:
    UserServerDllInitializationWin1(a1);
    return 0;
  }
  return 3221225659LL;
}

```

## disassembly

```asm
0x180001060  push    rbx
0x180001062  sub     rsp, 20h
0x180001066  mov     rbx, rcx
0x180001069  call    IsUserServerDllInitializationExtPresent
0x18000106e  test    al, al
0x180001070  jz      short loc_180001086
0x180001072  mov     rcx, rbx
0x180001075  add     rsp, 20h
0x180001079  pop     rbx
0x18000107a  jmp     cs:__imp_UserServerDllInitializationExt
0x180001086  call    IsUserServerDllInitializationMinPresent
0x18000108b  test    al, al
0x18000108d  jz      short loc_1800010A0
0x18000108f  mov     rcx, rbx
0x180001092  call    cs:__imp_UserServerDllInitializationMin
0x180001099  nop     dword ptr [rax+rax+00h]
0x18000109e  jmp     short loc_180001105
0x1800010a0  lea     rcx, Contract; "ext-ms-win-core-win32k-userinit-l1-1-0"
0x1800010a7  call    cs:__imp_IsApiSetImplemented
0x1800010ae  nop     dword ptr [rax+rax+00h]
0x1800010b3  test    eax, eax
0x1800010b5  jz      short loc_1800010FB
0x1800010b7  xor     edx, edx; hFile
0x1800010b9  lea     rcx, LibFileName; "win32u.dll"
0x1800010c0  mov     r8d, 800h; dwFlags
0x1800010c6  call    cs:__imp_LoadLibraryExW
0x1800010cd  nop     dword ptr [rax+rax+00h]
0x1800010d2  test    rax, rax
0x1800010d5  jz      short loc_1800010FB
0x1800010d7  lea     rdx, ProcName; "NtUserInitialize"
0x1800010de  mov     rcx, rax; hModule
0x1800010e1  call    cs:__imp_GetProcAddress
0x1800010e8  nop     dword ptr [rax+rax+00h]
0x1800010ed  test    rax, rax
0x1800010f0  jz      short loc_18000110C
0x1800010f2  xor     edx, edx
0x1800010f4  xor     ecx, ecx
0x1800010f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800010fb  mov     rcx, rbx
0x1800010fe  call    UserServerDllInitializationWin1
0x180001103  xor     eax, eax
0x180001105  add     rsp, 20h
0x180001109  pop     rbx
0x18000110a  retn
0x18000110c  mov     eax, 0C00000BBh
0x180001111  jmp     short loc_180001105
```
