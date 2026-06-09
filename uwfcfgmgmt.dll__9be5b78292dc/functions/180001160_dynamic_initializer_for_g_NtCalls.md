# _dynamic_initializer_for__g_NtCalls__

- ea: `0x180001160`
- end: `0x180001265`
- name: `_dynamic_initializer_for__g_NtCalls__`
- size: `261`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, loader_planting, broker_com_uri`

## callees

- `0x180001160`
- `0x180002264`
- `0x180012084`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x18000124f`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18000124f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800011d1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800011ec`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180001207`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180001222`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000123d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800011d1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800011ec`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180001207`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180001222`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000123d`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800011aa`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800011aa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800011bc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800011bc`

## string_xrefs

- `0x18000118c`: `%windir%\system32\ntdll.dll`
- `0x1800011c7`: `NtCreateFile`
- `0x1800011de`: `NtOpenFile`

## pseudocode

```c
int dynamic_initializer_for__g_NtCalls__()
{
  HMODULE Library; // rax
  unsigned int v2; // [rsp+30h] [rbp+8h] BYREF
  LPCWSTR lpLibFileName; // [rsp+38h] [rbp+10h] BYREF

  lpLibFileName = 0;
  v2 = 0;
  if ( !CNtCalls::s_hNtDll
    && ExpandEnvironmentStringsHelper(L"%windir%\\system32\\ntdll.dll", (unsigned __int16 **)&lpLibFileName, &v2) >= 0 )
  {
    Library = LoadLibraryExW(lpLibFileName, 0, 0);
    CNtCalls::s_hNtDll = Library;
    if ( Library )
    {
      CNtCalls::s_pfnNtCreateFile = (int (*)(void **, unsigned int, struct _OBJECT_ATTRIBUTES *, struct _IO_STATUS_BLOCK *, union _LARGE_INTEGER *, unsigned int, unsigned int, unsigned int, unsigned int, void *, unsigned int))GetProcAddress(Library, "NtCreateFile");
      CNtCalls::s_pfnNtOpenFile = (int (*)(void **, unsigned int, struct _OBJECT_ATTRIBUTES *, struct _IO_STATUS_BLOCK *, unsigned int, unsigned int))GetProcAddress(CNtCalls::s_hNtDll, "NtOpenFile");
      CNtCalls::s_pfnNtClose = (int (*)(void *))GetProcAddress(CNtCalls::s_hNtDll, "NtClose");
      CNtCalls::s_pfnNtSetInformationFile = (int (*)(void *, struct _IO_STATUS_BLOCK *, void *, unsigned int, enum _FILE_INFORMATION_CLASS))GetProcAddress(CNtCalls::s_hNtDll, "NtSetInformationFile");
      CNtCalls::s_pfnRtlInitUnicodeString = (void (*)(struct _UNICODE_STRING *, const unsigned __int16 *))GetProcAddress(CNtCalls::s_hNtDll, "RtlInitUnicodeString");
    }
    else
    {
      GetLastError();
    }
  }
  operator delete[]((void *)lpLibFileName);
  return atexit((void (__cdecl *)())dynamic_atexit_destructor_for__g_NtCalls__);
}

```

## disassembly

```asm
0x180001160  mov     rax, rsp
0x180001163  sub     rsp, 28h
0x180001167  cmp     cs:?s_hNtDll@CNtCalls@@0PEAUHINSTANCE__@@EA, 0; HINSTANCE__ * CNtCalls::s_hNtDll
0x18000116f  mov     qword ptr [rax+10h], 0
0x180001177  mov     dword ptr [rax+8], 0
0x18000117e  jnz     loc_18000124A
0x180001184  lea     r8, [rax+8]; unsigned int *
0x180001188  lea     rdx, [rax+10h]; unsigned __int16 **
0x18000118c  lea     rcx, aWindirSystem32_0; "%windir%\\system32\\ntdll.dll"
0x180001193  call    ?ExpandEnvironmentStringsHelper@@YAJPEBGPEAPEAGPEAK@Z; ExpandEnvironmentStringsHelper(ushort const *,ushort * *,ulong *)
0x180001198  test    eax, eax
0x18000119a  js      loc_18000124A
0x1800011a0  mov     rcx, [rsp+28h+lpLibFileName]; lpLibFileName
0x1800011a5  xor     r8d, r8d; dwFlags
0x1800011a8  xor     edx, edx; hFile
0x1800011aa  call    cs:__imp_LoadLibraryExW
0x1800011b0  mov     cs:?s_hNtDll@CNtCalls@@0PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * CNtCalls::s_hNtDll
0x1800011b7  test    rax, rax
0x1800011ba  jnz     short loc_1800011C7
0x1800011bc  call    cs:__imp_GetLastError
0x1800011c2  jmp     loc_18000124A
0x1800011c7  lea     rdx, ProcName; "NtCreateFile"
0x1800011ce  mov     rcx, rax; hModule
0x1800011d1  call    cs:__imp_GetProcAddress
0x1800011d7  mov     rcx, cs:?s_hNtDll@CNtCalls@@0PEAUHINSTANCE__@@EA; hModule
0x1800011de  lea     rdx, aNtopenfile; "NtOpenFile"
0x1800011e5  mov     cs:?s_pfnNtCreateFile@CNtCalls@@0P6AJPEAPEAXKPEAU_OBJECT_ATTRIBUTES@@PEAU_IO_STATUS_BLOCK@@PEAT_LARGE_INTEGER@@KKKKPEAXK@ZEA, rax; long (*CNtCalls::s_pfnNtCreateFile)(void * *,ulong,_OBJECT_ATTRIBUTES *,_IO_STATUS_BLOCK *,_LARGE_INTEGER *,ulong,ulong,ulong,ulong,void *,ulong)
0x1800011ec  call    cs:__imp_GetProcAddress
0x1800011f2  mov     rcx, cs:?s_hNtDll@CNtCalls@@0PEAUHINSTANCE__@@EA; hModule
0x1800011f9  lea     rdx, aNtclose; "NtClose"
0x180001200  mov     cs:?s_pfnNtOpenFile@CNtCalls@@0P6AJPEAPEAXKPEAU_OBJECT_ATTRIBUTES@@PEAU_IO_STATUS_BLOCK@@KK@ZEA, rax; long (*CNtCalls::s_pfnNtOpenFile)(void * *,ulong,_OBJECT_ATTRIBUTES *,_IO_STATUS_BLOCK *,ulong,ulong)
0x180001207  call    cs:__imp_GetProcAddress
0x18000120d  mov     rcx, cs:?s_hNtDll@CNtCalls@@0PEAUHINSTANCE__@@EA; hModule
0x180001214  lea     rdx, aNtsetinformati; "NtSetInformationFile"
0x18000121b  mov     cs:?s_pfnNtClose@CNtCalls@@0P6AJPEAX@ZEA, rax; long (*CNtCalls::s_pfnNtClose)(void *)
0x180001222  call    cs:__imp_GetProcAddress
0x180001228  mov     rcx, cs:?s_hNtDll@CNtCalls@@0PEAUHINSTANCE__@@EA; hModule
0x18000122f  lea     rdx, aRtlinitunicode; "RtlInitUnicodeString"
0x180001236  mov     cs:?s_pfnNtSetInformationFile@CNtCalls@@0P6AJPEAXPEAU_IO_STATUS_BLOCK@@0KW4_FILE_INFORMATION_CLASS@@@ZEA, rax; long (*CNtCalls::s_pfnNtSetInformationFile)(void *,_IO_STATUS_BLOCK *,void *,ulong,_FILE_INFORMATION_CLASS)
0x18000123d  call    cs:__imp_GetProcAddress
0x180001243  mov     cs:?s_pfnRtlInitUnicodeString@CNtCalls@@0P6AXPEAU_UNICODE_STRING@@PEBG@ZEA, rax; void (*CNtCalls::s_pfnRtlInitUnicodeString)(_UNICODE_STRING *,ushort const *)
0x18000124a  mov     rcx, [rsp+28h+lpLibFileName]
0x18000124f  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180001255  lea     rcx, _dynamic_atexit_destructor_for__g_NtCalls__
0x18000125c  add     rsp, 28h
0x180001260  jmp     atexit
```
