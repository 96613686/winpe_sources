# PfPrAgentLoad

- ea: `0x18008c830`
- end: `0x18008c8a7`
- name: `PfPrAgentLoad`
- size: `119`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callers

- `0x18008c9c4`

## callees

- `0x18008c830`
- `0x1800b7010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008c856`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008c871`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008c856`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008c871`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18008c866`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18008c866`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18008c88f`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18008c88f`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryA` at `0x18008c848`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryA` at `0x18008c848`

## pseudocode

```c
__int64 __fastcall PfPrAgentLoad(__int64 a1, const CHAR *a2, const CHAR *a3)
{
  HMODULE LibraryA; // rax
  HMODULE v6; // rdi
  DWORD LastError; // ebx
  FARPROC ProcAddress; // rax

  LibraryA = LoadLibraryA(a2);
  v6 = LibraryA;
  if ( LibraryA )
  {
    ProcAddress = GetProcAddress(LibraryA, a3);
    if ( ProcAddress )
    {
      LastError = ((__int64 (__fastcall *)(HMODULE, __int64))ProcAddress)(v6, a1);
      if ( !LastError )
        return LastError;
    }
    else
    {
      LastError = GetLastError();
    }
    FreeLibrary(v6);
    return LastError;
  }
  return GetLastError();
}

```

## disassembly

```asm
0x18008c830  mov     [rsp+arg_0], rbx
0x18008c835  mov     [rsp+arg_8], rsi
0x18008c83a  push    rdi
0x18008c83b  sub     rsp, 20h
0x18008c83f  mov     rsi, rcx
0x18008c842  mov     rbx, r8
0x18008c845  mov     rcx, rdx; lpLibFileName
0x18008c848  call    cs:__imp_LoadLibraryA
0x18008c84e  mov     rdi, rax
0x18008c851  test    rax, rax
0x18008c854  jnz     short loc_18008C860
0x18008c856  call    cs:__imp_GetLastError
0x18008c85c  mov     ebx, eax
0x18008c85e  jmp     short loc_18008C895
0x18008c860  mov     rdx, rbx; lpProcName
0x18008c863  mov     rcx, rdi; hModule
0x18008c866  call    cs:__imp_GetProcAddress
0x18008c86c  test    rax, rax
0x18008c86f  jnz     short loc_18008C87B
0x18008c871  call    cs:__imp_GetLastError
0x18008c877  mov     ebx, eax
0x18008c879  jmp     short loc_18008C88C
0x18008c87b  mov     rdx, rsi
0x18008c87e  mov     rcx, rdi
0x18008c881  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008c886  mov     ebx, eax
0x18008c888  test    eax, eax
0x18008c88a  jz      short loc_18008C895
0x18008c88c  mov     rcx, rdi; hLibModule
0x18008c88f  call    cs:__imp_FreeLibrary
0x18008c895  mov     rsi, [rsp+28h+arg_8]
0x18008c89a  mov     eax, ebx
0x18008c89c  mov     rbx, [rsp+28h+arg_0]
0x18008c8a1  add     rsp, 20h
0x18008c8a5  pop     rdi
0x18008c8a6  retn
```
