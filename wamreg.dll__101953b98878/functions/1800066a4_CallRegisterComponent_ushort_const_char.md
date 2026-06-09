# CallRegisterComponent(ushort const *,char *)

- ea: `0x1800066a4`
- end: `0x180006773`
- name: `?CallRegisterComponent@@YAJPEBGPEAD@Z`
- size: `207`
- prototype: `__int64 __fastcall(const unsigned __int16 *, char *)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180001ca0`
- `0x180001cc0`

## callees

- `0x1800066a4`
- `0x180006850`
- `0x180007010`

## import_xrefs

- `msvcrt!wcscat_s` at `0x1800066f0`
- `msvcrt!wcscat_s` at `0x1800066f0`
- `KERNEL32!LoadLibraryExW` at `0x180006703`
- `KERNEL32!LoadLibraryExW` at `0x180006703`
- `KERNEL32!FreeLibrary` at `0x180006743`
- `KERNEL32!FreeLibrary` at `0x180006743`
- `KERNEL32!GetProcAddress` at `0x180006717`
- `KERNEL32!GetProcAddress` at `0x180006717`
- `KERNEL32!GetSystemDirectoryW` at `0x1800066d0`
- `KERNEL32!GetSystemDirectoryW` at `0x1800066d0`

## string_xrefs

- `0x180006732`: `wamreg.dll`
- `0x1800066df`: `\inetsrv\iisreg.dll`

## pseudocode

```c
__int64 __fastcall CallRegisterComponent(const unsigned __int16 *a1, char *a2)
{
  HMODULE Library; // rax
  HMODULE v4; // rdi
  FARPROC ProcAddress; // rax
  unsigned int v6; // ebx
  WCHAR Buffer[264]; // [rsp+20h] [rbp-228h] BYREF

  if ( GetSystemDirectoryW(Buffer, 0xF0u) - 1 > 0xEF )
    return 2147942403LL;
  wcscat_s(Buffer, 0x104u, L"\\inetsrv\\iisreg.dll");
  Library = LoadLibraryExW(Buffer, 0, 0x900u);
  v4 = Library;
  if ( !Library )
    return 2147942403LL;
  ProcAddress = GetProcAddress(Library, a2);
  v6 = ProcAddress == 0 ? 0x80004005 : 0;
  if ( ProcAddress )
    v6 = ((__int64 (__fastcall *)(const wchar_t *))ProcAddress)(L"wamreg.dll");
  FreeLibrary(v4);
  return v6;
}

```

## disassembly

```asm
0x1800066a4  mov     [rsp+arg_0], rbx
0x1800066a9  push    rdi
0x1800066aa  sub     rsp, 240h
0x1800066b1  mov     rax, cs:__security_cookie
0x1800066b8  xor     rax, rsp
0x1800066bb  mov     [rsp+248h+var_18], rax
0x1800066c3  mov     rbx, rdx
0x1800066c6  lea     rcx, [rsp+248h+Buffer]; lpBuffer
0x1800066cb  mov     edx, 0F0h; uSize
0x1800066d0  call    cs:__imp_GetSystemDirectoryW
0x1800066d6  dec     eax
0x1800066d8  cmp     eax, 0EFh
0x1800066dd  ja      short loc_18000674D
0x1800066df  lea     r8, aInetsrvIisregD; "\\inetsrv\\iisreg.dll"
0x1800066e6  mov     edx, 104h; SizeInWords
0x1800066eb  lea     rcx, [rsp+248h+Buffer]; Destination
0x1800066f0  call    cs:__imp_wcscat_s
0x1800066f6  xor     edx, edx; hFile
0x1800066f8  lea     rcx, [rsp+248h+Buffer]; lpLibFileName
0x1800066fd  mov     r8d, 900h; dwFlags
0x180006703  call    cs:__imp_LoadLibraryExW
0x180006709  mov     rdi, rax
0x18000670c  test    rax, rax
0x18000670f  jz      short loc_18000674D
0x180006711  mov     rdx, rbx; lpProcName
0x180006714  mov     rcx, rax; hModule
0x180006717  call    cs:__imp_GetProcAddress
0x18000671d  mov     rcx, rax
0x180006720  neg     rcx
0x180006723  sbb     ebx, ebx
0x180006725  not     ebx
0x180006727  and     ebx, 80004005h
0x18000672d  test    rax, rax
0x180006730  jz      short loc_180006740
0x180006732  lea     rcx, aWamregDll_0; "wamreg.dll"
0x180006739  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000673e  mov     ebx, eax
0x180006740  mov     rcx, rdi; hLibModule
0x180006743  call    cs:__imp_FreeLibrary
0x180006749  mov     eax, ebx
0x18000674b  jmp     short loc_180006752
0x18000674d  mov     eax, 80070003h
0x180006752  mov     rcx, [rsp+248h+var_18]
0x18000675a  xor     rcx, rsp; StackCookie
0x18000675d  call    __security_check_cookie
0x180006762  mov     rbx, [rsp+248h+arg_0]
0x18000676a  add     rsp, 240h
0x180006771  pop     rdi
0x180006772  retn
```
