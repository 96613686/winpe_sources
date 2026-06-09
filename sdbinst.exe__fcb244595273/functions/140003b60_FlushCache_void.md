# FlushCache(void)

- ea: `0x140003b60`
- end: `0x140003c06`
- name: `?FlushCache@@YAXXZ`
- size: `166`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x140008500`

## callees

- `0x140003b60`
- `0x140006f60`
- `0x14002e420`
- `0x14002f010`

## import_xrefs

- `KERNEL32!GetSystemDirectoryW` at `0x140003b87`
- `KERNEL32!GetSystemDirectoryW` at `0x140003b87`
- `KERNEL32!LoadLibraryW` at `0x140003bb2`
- `KERNEL32!LoadLibraryW` at `0x140003bb2`
- `KERNEL32!GetProcAddress` at `0x140003bca`
- `KERNEL32!GetProcAddress` at `0x140003bca`
- `KERNEL32!FreeLibrary` at `0x140003be7`
- `KERNEL32!FreeLibrary` at `0x140003be7`

## string_xrefs

- `0x140003b96`: `\apphelp.dll`
- `0x140003bc0`: `ShimFlushCache`

## pseudocode

```c
void FlushCache(void)
{
  HMODULE LibraryW; // rax
  HMODULE v1; // rbx
  FARPROC ProcAddress; // rax
  WCHAR Buffer[264]; // [rsp+30h] [rbp-228h] BYREF

  if ( GetSystemDirectoryW(Buffer, 0x104u) - 1 <= 0x102 && (int)StringCchCatW(Buffer, 0x104u, L"\\apphelp.dll") >= 0 )
  {
    LibraryW = LoadLibraryW(Buffer);
    v1 = LibraryW;
    if ( LibraryW )
    {
      ProcAddress = GetProcAddress(LibraryW, "ShimFlushCache");
      if ( ProcAddress )
        ((void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD))ProcAddress)(0, 0, 0, 0);
      FreeLibrary(v1);
    }
  }
}

```

## disassembly

```asm
0x140003b60  push    rbx
0x140003b62  sub     rsp, 250h
0x140003b69  mov     rax, cs:__security_cookie
0x140003b70  xor     rax, rsp
0x140003b73  mov     [rsp+258h+var_18], rax
0x140003b7b  mov     ebx, 104h
0x140003b80  lea     rcx, [rsp+258h+Buffer]; lpBuffer
0x140003b85  mov     edx, ebx; uSize
0x140003b87  call    cs:__imp_GetSystemDirectoryW
0x140003b8d  dec     eax
0x140003b8f  cmp     eax, 102h
0x140003b94  ja      short loc_140003BED
0x140003b96  lea     r8, aApphelpDll; "\\apphelp.dll"
0x140003b9d  mov     edx, ebx; unsigned __int64
0x140003b9f  lea     rcx, [rsp+258h+Buffer]; unsigned __int16 *
0x140003ba4  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140003ba9  test    eax, eax
0x140003bab  js      short loc_140003BED
0x140003bad  lea     rcx, [rsp+258h+Buffer]; lpLibFileName
0x140003bb2  call    cs:__imp_LoadLibraryW
0x140003bb8  mov     rbx, rax
0x140003bbb  test    rax, rax
0x140003bbe  jz      short loc_140003BED
0x140003bc0  lea     rdx, aShimflushcache; "ShimFlushCache"
0x140003bc7  mov     rcx, rax; hModule
0x140003bca  call    cs:__imp_GetProcAddress
0x140003bd0  test    rax, rax
0x140003bd3  jz      short loc_140003BE4
0x140003bd5  xor     r9d, r9d
0x140003bd8  xor     r8d, r8d
0x140003bdb  xor     edx, edx
0x140003bdd  xor     ecx, ecx
0x140003bdf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003be4  mov     rcx, rbx; hLibModule
0x140003be7  call    cs:__imp_FreeLibrary
0x140003bed  mov     rcx, [rsp+258h+var_18]
0x140003bf5  xor     rcx, rsp; StackCookie
0x140003bf8  call    __security_check_cookie
0x140003bfd  add     rsp, 250h
0x140003c04  pop     rbx
0x140003c05  retn
```
