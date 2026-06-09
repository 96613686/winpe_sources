# DLSetThreadToken(void * *,void *)

- ea: `0x18001b1f4`
- end: `0x18001b25d`
- name: `?DLSetThreadToken@@YAHPEAPEAXPEAX@Z`
- size: `105`
- prototype: `__int64 __fastcall(void **, void *)`
- caller_count: `4`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18001a7bc`
- `0x18001ac90`
- `0x18001b150`
- `0x18001b1b0`

## callees

- `0x18001b1f4`
- `0x18001b340`
- `0x180047010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001b255`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001b255`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001b23f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001b23f`

## string_xrefs

- `0x18001b238`: `SetThreadToken`

## pseudocode

```c
__int64 __fastcall DLSetThreadToken(void **a1, void *a2)
{
  FARPROC ProcAddress; // rax
  unsigned int v4; // ebx
  DWORD ProcThreadsDll; // eax

  ProcAddress = (FARPROC)qword_1800703B8;
  if ( !qword_1800703B8 )
  {
    v4 = 0;
    ProcThreadsDll = DLpLoadProcThreadsDll();
    if ( ProcThreadsDll )
    {
      SetLastError(ProcThreadsDll);
      return v4;
    }
    ProcAddress = GetProcAddress(g_hInstProcThreadsDLL, "SetThreadToken");
    qword_1800703B8 = (__int64)ProcAddress;
    if ( !ProcAddress )
      return v4;
  }
  return ((unsigned int (__fastcall *)(_QWORD, void *))ProcAddress)(0, a2);
}

```

## disassembly

```asm
0x18001b1f4  mov     [rsp+arg_0], rbx
0x18001b1f9  push    rdi
0x18001b1fa  sub     rsp, 20h
0x18001b1fe  mov     rax, cs:qword_1800703B8
0x18001b205  mov     rdi, rdx
0x18001b208  test    rax, rax
0x18001b20b  jz      short loc_18001B226
0x18001b20d  mov     rdx, rdi
0x18001b210  xor     ecx, ecx
0x18001b212  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b217  mov     ebx, eax
0x18001b219  mov     eax, ebx
0x18001b21b  mov     rbx, [rsp+28h+arg_0]
0x18001b220  add     rsp, 20h
0x18001b224  pop     rdi
0x18001b225  retn
0x18001b226  xor     ebx, ebx
0x18001b228  call    ?DLpLoadProcThreadsDll@@YAKXZ; DLpLoadProcThreadsDll(void)
0x18001b22d  test    eax, eax
0x18001b22f  jnz     short loc_18001B253
0x18001b231  mov     rcx, cs:?g_hInstProcThreadsDLL@@3PEAUHINSTANCE__@@EA; hModule
0x18001b238  lea     rdx, aSetthreadtoken; "SetThreadToken"
0x18001b23f  call    cs:__imp_GetProcAddress
0x18001b245  mov     cs:qword_1800703B8, rax
0x18001b24c  test    rax, rax
0x18001b24f  jnz     short loc_18001B20D
0x18001b251  jmp     short loc_18001B219
0x18001b253  mov     ecx, eax; dwErrCode
0x18001b255  call    cs:__imp_SetLastError
0x18001b25b  jmp     short loc_18001B219
```
