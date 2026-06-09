# PfApFetchSEBInterfaceStart

- ea: `0x180059bec`
- end: `0x180059c67`
- name: `PfApFetchSEBInterfaceStart`
- size: `123`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180059aac`

## callees

- `0x180059bec`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180059c13`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180059c13`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180059c25`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180059c39`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180059c4d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180059c25`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180059c39`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180059c4d`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180059c05`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180059c05`

## string_xrefs

- `0x180059bfc`: `SystemEventsBrokerClient.dll`

## pseudocode

```c
DWORD __fastcall PfApFetchSEBInterfaceStart(HMODULE *a1)
{
  HMODULE Library; // rax
  HMODULE v3; // rbx
  DWORD result; // eax

  Library = LoadLibraryExW(L"SystemEventsBrokerClient.dll", 0, 0);
  v3 = Library;
  if ( !Library )
    return GetLastError();
  a1[1] = (HMODULE)GetProcAddress(Library, "SebEnumerateEventsByType");
  a1[2] = (HMODULE)GetProcAddress(v3, "SebSignalEvent");
  a1[3] = (HMODULE)GetProcAddress(v3, "SebQueryEventPackage");
  result = 0;
  *a1 = v3;
  return result;
}

```

## disassembly

```asm
0x180059bec  mov     [rsp+arg_0], rbx
0x180059bf1  push    rdi
0x180059bf2  sub     rsp, 20h
0x180059bf6  mov     rdi, rcx
0x180059bf9  xor     r8d, r8d; dwFlags
0x180059bfc  lea     rcx, LibFileName; "SystemEventsBrokerClient.dll"
0x180059c03  xor     edx, edx; hFile
0x180059c05  call    cs:__imp_LoadLibraryExW
0x180059c0b  mov     rbx, rax
0x180059c0e  test    rax, rax
0x180059c11  jnz     short loc_180059C1B
0x180059c13  call    cs:__imp_GetLastError
0x180059c19  jmp     short loc_180059C5C
0x180059c1b  lea     rdx, ProcName; "SebEnumerateEventsByType"
0x180059c22  mov     rcx, rbx; hModule
0x180059c25  call    cs:__imp_GetProcAddress
0x180059c2b  lea     rdx, aSebsignalevent; "SebSignalEvent"
0x180059c32  mov     rcx, rbx; hModule
0x180059c35  mov     [rdi+8], rax
0x180059c39  call    cs:__imp_GetProcAddress
0x180059c3f  lea     rdx, aSebqueryeventp; "SebQueryEventPackage"
0x180059c46  mov     rcx, rbx; hModule
0x180059c49  mov     [rdi+10h], rax
0x180059c4d  call    cs:__imp_GetProcAddress
0x180059c53  mov     [rdi+18h], rax
0x180059c57  xor     eax, eax
0x180059c59  mov     [rdi], rbx
0x180059c5c  mov     rbx, [rsp+28h+arg_0]
0x180059c61  add     rsp, 20h
0x180059c65  pop     rdi
0x180059c66  retn
```
