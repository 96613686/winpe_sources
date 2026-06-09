# UnregisterTypeLibrary

- ea: `0x18002d1b4`
- end: `0x18002d2af`
- name: `UnregisterTypeLibrary`
- size: `251`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x18002d480`
- `0x18002dd48`

## callees

- `0x18002ce14`
- `0x18002d1b4`
- `0x180034090`
- `0x180036010`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18002d1e5`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18002d1e5`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18002d242`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18002d242`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18002d284`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18002d284`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002d25a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002d25a`

## string_xrefs

- `0x18002d22c`: `\oleaut32.dll`

## pseudocode

```c
int __fastcall UnregisterTypeLibrary(__int64 a1, unsigned __int16 a2)
{
  WCHAR *v3; // rax
  __int64 v4; // r8
  __int64 v5; // r9
  HMODULE Library; // rax
  HMODULE v7; // rbx
  FARPROC ProcAddress; // rax
  size_t v10; // [rsp+20h] [rbp-258h]
  WCHAR Buffer[280]; // [rsp+30h] [rbp-248h] BYREF

  GetSystemDirectoryW(Buffer, 0x104u);
  v3 = Buffer;
  v4 = 280;
  do
  {
    if ( !*v3 )
      break;
    ++v3;
    --v4;
  }
  while ( v4 );
  if ( v4 )
  {
    v5 = (280 - v4) & -(__int64)(v4 != 0);
    StringCopyWorkerW(&Buffer[v5], 280 - v5, (size_t *)v4, L"\\oleaut32.dll", v10);
  }
  Library = LoadLibraryExW(Buffer, 0, 0);
  v7 = Library;
  if ( Library )
  {
    ProcAddress = GetProcAddress(Library, "UnRegisterTypeLib");
    if ( ProcAddress )
      ((void (__fastcall *)(GUID *, __int64, _QWORD, _QWORD, int))ProcAddress)(&LIBID_WbemScripting, 1, a2, 0, 1);
    LODWORD(Library) = FreeLibrary(v7);
  }
  return (int)Library;
}

```

## disassembly

```asm
0x18002d1b4  mov     [rsp+arg_0], rbx
0x18002d1b9  mov     [rsp+arg_10], rsi
0x18002d1be  push    rdi
0x18002d1bf  sub     rsp, 270h
0x18002d1c6  mov     rax, cs:__security_cookie
0x18002d1cd  xor     rax, rsp
0x18002d1d0  mov     [rsp+278h+var_18], rax
0x18002d1d8  movzx   edi, dx
0x18002d1db  lea     rcx, [rsp+278h+Buffer]; lpBuffer
0x18002d1e0  mov     edx, 104h; uSize
0x18002d1e5  call    cs:__imp_GetSystemDirectoryW
0x18002d1eb  mov     edx, 118h
0x18002d1f0  lea     rax, [rsp+278h+Buffer]
0x18002d1f5  mov     r8d, edx
0x18002d1f8  xor     esi, esi
0x18002d1fa  cmp     [rax], si
0x18002d1fd  jz      short loc_18002D209
0x18002d1ff  add     rax, 2
0x18002d203  sub     r8, 1; pcchNewDestLength
0x18002d207  jnz     short loc_18002D1FA
0x18002d209  mov     rcx, rdx
0x18002d20c  mov     rax, r8
0x18002d20f  sub     rcx, r8
0x18002d212  neg     rax
0x18002d215  sbb     r9, r9
0x18002d218  and     r9, rcx
0x18002d21b  test    r8, r8
0x18002d21e  jz      short loc_18002D238
0x18002d220  sub     rdx, r9; cchDest
0x18002d223  lea     rcx, [rsp+278h+Buffer]
0x18002d228  lea     rcx, [rcx+r9*2]; pszDest
0x18002d22c  lea     r9, aOleaut32Dll_0; "\\oleaut32.dll"
0x18002d233  call    StringCopyWorkerW
0x18002d238  xor     r8d, r8d; dwFlags
0x18002d23b  lea     rcx, [rsp+278h+Buffer]; lpLibFileName
0x18002d240  xor     edx, edx; hFile
0x18002d242  call    cs:__imp_LoadLibraryExW
0x18002d248  mov     rbx, rax
0x18002d24b  test    rax, rax
0x18002d24e  jz      short loc_18002D28A
0x18002d250  lea     rdx, aUnregistertype; "UnRegisterTypeLib"
0x18002d257  mov     rcx, rax; hModule
0x18002d25a  call    cs:__imp_GetProcAddress
0x18002d260  test    rax, rax
0x18002d263  jz      short loc_18002D281
0x18002d265  mov     edx, 1
0x18002d26a  lea     rcx, LIBID_WbemScripting
0x18002d271  xor     r9d, r9d
0x18002d274  mov     dword ptr [rsp+278h+var_258], edx
0x18002d278  movzx   r8d, di
0x18002d27c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d281  mov     rcx, rbx; hLibModule
0x18002d284  call    cs:__imp_FreeLibrary
0x18002d28a  mov     rcx, [rsp+278h+var_18]
0x18002d292  xor     rcx, rsp; StackCookie
0x18002d295  call    __security_check_cookie
0x18002d29a  lea     r11, [rsp+278h+var_8]
0x18002d2a2  mov     rbx, [r11+10h]
0x18002d2a6  mov     rsi, [r11+20h]
0x18002d2aa  mov     rsp, r11
0x18002d2ad  pop     rdi
0x18002d2ae  retn
```
