# DLOpenProcessToken(void *,ulong,void * *)

- ea: `0x18001d584`
- end: `0x18001d5f2`
- name: `?DLOpenProcessToken@@YAHPEAXKPEAPEAX@Z`
- size: `110`
- prototype: `__int64 __fastcall(void *, unsigned int, void **)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18001d390`
- `0x180034850`

## callees

- `0x18001b340`
- `0x18001d584`
- `0x180047010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001d5c8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001d5c8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001d5de`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001d5de`

## string_xrefs

- `0x18001d5d7`: `OpenProcessToken`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall DLOpenProcessToken(void *a1, unsigned int a2, void **a3)
{
  FARPROC ProcAddress; // rax
  unsigned int v7; // ebx
  DWORD ProcThreadsDll; // eax

  ProcAddress = (FARPROC)qword_1800703A8;
  if ( !qword_1800703A8 )
  {
    v7 = 0;
    ProcThreadsDll = DLpLoadProcThreadsDll();
    if ( ProcThreadsDll )
    {
      SetLastError(ProcThreadsDll);
      return v7;
    }
    ProcAddress = GetProcAddress(g_hInstProcThreadsDLL, "OpenProcessToken");
    qword_1800703A8 = (__int64)ProcAddress;
    if ( !ProcAddress )
      return v7;
  }
  return ((unsigned int (__fastcall *)(void *, _QWORD, void **))ProcAddress)(a1, a2, a3);
}

```

## disassembly

```asm
0x18001d584  push    rbx
0x18001d586  push    rbp
0x18001d587  push    rsi
0x18001d588  push    rdi
0x18001d589  sub     rsp, 28h
0x18001d58d  mov     rax, cs:qword_1800703A8
0x18001d594  mov     rdi, r8
0x18001d597  mov     esi, edx
0x18001d599  mov     rbp, rcx
0x18001d59c  test    rax, rax
0x18001d59f  jz      short loc_18001D5BB
0x18001d5a1  mov     r8, rdi
0x18001d5a4  mov     edx, esi
0x18001d5a6  mov     rcx, rbp
0x18001d5a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d5ae  mov     ebx, eax
0x18001d5b0  mov     eax, ebx
0x18001d5b2  add     rsp, 28h
0x18001d5b6  pop     rdi
0x18001d5b7  pop     rsi
0x18001d5b8  pop     rbp
0x18001d5b9  pop     rbx
0x18001d5ba  retn
0x18001d5bb  xor     ebx, ebx
0x18001d5bd  call    ?DLpLoadProcThreadsDll@@YAKXZ; DLpLoadProcThreadsDll(void)
0x18001d5c2  test    eax, eax
0x18001d5c4  jz      short loc_18001D5D0
0x18001d5c6  mov     ecx, eax; dwErrCode
0x18001d5c8  call    cs:__imp_SetLastError
0x18001d5ce  jmp     short loc_18001D5B0
0x18001d5d0  mov     rcx, cs:?g_hInstProcThreadsDLL@@3PEAUHINSTANCE__@@EA; hModule
0x18001d5d7  lea     rdx, aOpenprocesstok; "OpenProcessToken"
0x18001d5de  call    cs:__imp_GetProcAddress
0x18001d5e4  mov     cs:qword_1800703A8, rax
0x18001d5eb  test    rax, rax
0x18001d5ee  jz      short loc_18001D5B0
0x18001d5f0  jmp     short loc_18001D5A1
```
