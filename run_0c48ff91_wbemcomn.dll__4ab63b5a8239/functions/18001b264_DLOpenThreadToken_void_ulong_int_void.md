# DLOpenThreadToken(void *,ulong,int,void * *)

- ea: `0x18001b264`
- end: `0x18001b2d8`
- name: `?DLOpenThreadToken@@YAHPEAXKHPEAPEAX@Z`
- size: `116`
- prototype: `__int64 __fastcall(void *, unsigned int, int, void **)`
- caller_count: `3`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18001b0e8`
- `0x18001d390`
- `0x180034850`

## callees

- `0x18001b264`
- `0x18001b340`
- `0x180047010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001b2ae`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001b2ae`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001b2c4`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001b2c4`

## string_xrefs

- `0x18001b2bd`: `OpenThreadToken`

## pseudocode

```c
__int64 __fastcall DLOpenThreadToken(void *a1, unsigned int a2, __int64 a3, void **a4)
{
  FARPROC ProcAddress; // rax
  unsigned int v8; // ebx
  DWORD ProcThreadsDll; // eax

  ProcAddress = (FARPROC)qword_1800703B0;
  if ( !qword_1800703B0 )
  {
    v8 = 0;
    ProcThreadsDll = DLpLoadProcThreadsDll();
    if ( ProcThreadsDll )
    {
      SetLastError(ProcThreadsDll);
      return v8;
    }
    ProcAddress = GetProcAddress(g_hInstProcThreadsDLL, "OpenThreadToken");
    qword_1800703B0 = (__int64)ProcAddress;
    if ( !ProcAddress )
      return v8;
  }
  return ((unsigned int (__fastcall *)(void *, _QWORD, __int64, void **))ProcAddress)(a1, a2, 1, a4);
}

```

## disassembly

```asm
0x18001b264  push    rbx
0x18001b266  push    rbp
0x18001b267  push    rsi
0x18001b268  push    rdi
0x18001b269  sub     rsp, 38h
0x18001b26d  mov     rax, cs:qword_1800703B0
0x18001b274  mov     rdi, r9
0x18001b277  mov     esi, edx
0x18001b279  mov     rbp, rcx
0x18001b27c  test    rax, rax
0x18001b27f  jz      short loc_18001B2A1
0x18001b281  mov     r9, rdi
0x18001b284  mov     r8d, 1
0x18001b28a  mov     edx, esi
0x18001b28c  mov     rcx, rbp
0x18001b28f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b294  mov     ebx, eax
0x18001b296  mov     eax, ebx
0x18001b298  add     rsp, 38h
0x18001b29c  pop     rdi
0x18001b29d  pop     rsi
0x18001b29e  pop     rbp
0x18001b29f  pop     rbx
0x18001b2a0  retn
0x18001b2a1  xor     ebx, ebx
0x18001b2a3  call    ?DLpLoadProcThreadsDll@@YAKXZ; DLpLoadProcThreadsDll(void)
0x18001b2a8  test    eax, eax
0x18001b2aa  jz      short loc_18001B2B6
0x18001b2ac  mov     ecx, eax; dwErrCode
0x18001b2ae  call    cs:__imp_SetLastError
0x18001b2b4  jmp     short loc_18001B296
0x18001b2b6  mov     rcx, cs:?g_hInstProcThreadsDLL@@3PEAUHINSTANCE__@@EA; hModule
0x18001b2bd  lea     rdx, aOpenthreadtoke; "OpenThreadToken"
0x18001b2c4  call    cs:__imp_GetProcAddress
0x18001b2ca  mov     cs:qword_1800703B0, rax
0x18001b2d1  test    rax, rax
0x18001b2d4  jnz     short loc_18001B281
0x18001b2d6  jmp     short loc_18001B296
```
