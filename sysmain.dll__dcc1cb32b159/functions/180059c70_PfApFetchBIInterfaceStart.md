# PfApFetchBIInterfaceStart

- ea: `0x180059c70`
- end: `0x180059cd7`
- name: `PfApFetchBIInterfaceStart`
- size: `103`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180059aac`

## callees

- `0x180059c70`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180059c97`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180059c97`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180059ca9`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180059cbd`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180059ca9`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180059cbd`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180059c89`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180059c89`

## string_xrefs

- `0x180059c9f`: `BiQueryBrokeredEvent`
- `0x180059c80`: `bi.dll`

## pseudocode

```c
DWORD __fastcall PfApFetchBIInterfaceStart(HMODULE *a1)
{
  HMODULE Library; // rax
  HMODULE v3; // rbx
  DWORD result; // eax

  Library = LoadLibraryExW(L"bi.dll", 0, 0);
  v3 = Library;
  if ( !Library )
    return GetLastError();
  a1[1] = (HMODULE)GetProcAddress(Library, "BiQueryBrokeredEvent");
  a1[2] = (HMODULE)GetProcAddress(v3, "BiFreeMemory");
  result = 0;
  *a1 = v3;
  return result;
}

```

## disassembly

```asm
0x180059c70  mov     [rsp+arg_0], rbx
0x180059c75  push    rdi
0x180059c76  sub     rsp, 20h
0x180059c7a  mov     rdi, rcx
0x180059c7d  xor     r8d, r8d; dwFlags
0x180059c80  lea     rcx, aBiDll; "bi.dll"
0x180059c87  xor     edx, edx; hFile
0x180059c89  call    cs:__imp_LoadLibraryExW
0x180059c8f  mov     rbx, rax
0x180059c92  test    rax, rax
0x180059c95  jnz     short loc_180059C9F
0x180059c97  call    cs:__imp_GetLastError
0x180059c9d  jmp     short loc_180059CCC
0x180059c9f  lea     rdx, aBiquerybrokere; "BiQueryBrokeredEvent"
0x180059ca6  mov     rcx, rbx; hModule
0x180059ca9  call    cs:__imp_GetProcAddress
0x180059caf  lea     rdx, aBifreememory; "BiFreeMemory"
0x180059cb6  mov     rcx, rbx; hModule
0x180059cb9  mov     [rdi+8], rax
0x180059cbd  call    cs:__imp_GetProcAddress
0x180059cc3  mov     [rdi+10h], rax
0x180059cc7  xor     eax, eax
0x180059cc9  mov     [rdi], rbx
0x180059ccc  mov     rbx, [rsp+28h+arg_0]
0x180059cd1  add     rsp, 20h
0x180059cd5  pop     rdi
0x180059cd6  retn
```
