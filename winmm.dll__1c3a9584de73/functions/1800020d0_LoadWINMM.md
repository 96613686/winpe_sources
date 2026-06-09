# LoadWINMM

- ea: `0x1800020d0`
- end: `0x18000213a`
- name: `LoadWINMM`
- size: `106`
- prototype: `_BOOL8()`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180001eb0`
- `0x18000b5ec`

## callees

- `0x1800020d0`
- `0x18000c990`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameA` at `0x1800020fb`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameA` at `0x1800020fb`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x180002110`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x180002110`

## pseudocode

```c
_BOOL8 LoadWINMM()
{
  CHAR Filename[1008]; // [rsp+20h] [rbp-408h] BYREF

  return GetModuleFileNameA(ghInst, Filename, 0x3E8u) && LoadLibraryExA(Filename, 0, 2u) != 0;
}

```

## disassembly

```asm
0x1800020d0  sub     rsp, 428h
0x1800020d7  mov     rax, cs:__security_cookie
0x1800020de  xor     rax, rsp
0x1800020e1  mov     [rsp+428h+var_18], rax
0x1800020e9  mov     rcx, cs:ghInst; hModule
0x1800020f0  lea     rdx, [rsp+428h+Filename]; lpFilename
0x1800020f5  mov     r8d, 3E8h; nSize
0x1800020fb  call    cs:__imp_GetModuleFileNameA
0x180002101  test    eax, eax
0x180002103  jz      short loc_180002120
0x180002105  xor     edx, edx; hFile
0x180002107  lea     rcx, [rsp+428h+Filename]; lpLibFileName
0x18000210c  lea     r8d, [rdx+2]; dwFlags
0x180002110  call    cs:__imp_LoadLibraryExA
0x180002116  neg     rax
0x180002119  sbb     eax, eax
0x18000211b  and     eax, 1
0x18000211e  jmp     short loc_180002122
0x180002120  xor     eax, eax
0x180002122  mov     rcx, [rsp+428h+var_18]
0x18000212a  xor     rcx, rsp; StackCookie
0x18000212d  call    __security_check_cookie
0x180002132  add     rsp, 428h
0x180002139  retn
```
