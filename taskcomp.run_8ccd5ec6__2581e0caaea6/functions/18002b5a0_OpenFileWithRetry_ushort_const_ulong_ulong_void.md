# OpenFileWithRetry(ushort const *,ulong,ulong,void * *)

- ea: `0x18002b5a0`
- end: `0x18002b67f`
- name: `?OpenFileWithRetry@@YAJPEBGKKPEAPEAX@Z`
- size: `223`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName, DWORD dwDesiredAccess, DWORD dwShareMode, void **)`
- caller_count: `3`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x18000b218`
- `0x180016040`
- `0x180025974`

## callees

- `0x18002b5a0`

## import_xrefs

- `msvcrt!rand` at `0x18002b617`
- `msvcrt!rand` at `0x18002b617`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18002b644`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18002b644`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b604`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b604`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002b5ef`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002b5ef`

## pseudocode

```c
__int64 __fastcall OpenFileWithRetry(LPCWSTR lpFileName, DWORD dwDesiredAccess, DWORD dwShareMode, void **a4)
{
  signed int LastError; // ebx
  HANDLE FileW; // rdi
  int i; // esi
  int v11; // eax

  LastError = 0;
  FileW = 0;
  for ( i = 3; i; --i )
  {
    FileW = CreateFileW(lpFileName, dwDesiredAccess, dwShareMode, 0, 3u, 0x8000000u, 0);
    if ( FileW != (HANDLE)-1LL )
      goto LABEL_10;
    LastError = GetLastError();
    if ( LastError != 32 )
      break;
    v11 = rand();
    Sleep(v11 % 250 + 250);
  }
  if ( !LastError )
  {
LABEL_10:
    *a4 = FileW;
    return 0;
  }
  if ( LastError > 0 )
    return (unsigned __int16)LastError | 0x80070000;
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x18002b5a0  push    rbx
0x18002b5a2  push    rbp
0x18002b5a3  push    rsi
0x18002b5a4  push    rdi
0x18002b5a5  push    r12
0x18002b5a7  push    r14
0x18002b5a9  push    r15
0x18002b5ab  sub     rsp, 40h
0x18002b5af  xor     ebx, ebx
0x18002b5b1  mov     r14, r9
0x18002b5b4  mov     ebp, r8d
0x18002b5b7  mov     r15d, edx
0x18002b5ba  mov     r12, rcx
0x18002b5bd  xor     edi, edi
0x18002b5bf  lea     esi, [rbx+3]
0x18002b5c2  test    esi, esi
0x18002b5c4  jz      loc_18002B657
0x18002b5ca  mov     [rsp+78h+hTemplateFile], 0; hTemplateFile
0x18002b5d3  xor     r9d, r9d; lpSecurityAttributes
0x18002b5d6  mov     [rsp+78h+dwFlagsAndAttributes], 8000000h; dwFlagsAndAttributes
0x18002b5de  mov     r8d, ebp; dwShareMode
0x18002b5e1  mov     edx, r15d; dwDesiredAccess
0x18002b5e4  mov     [rsp+78h+dwCreationDisposition], 3; dwCreationDisposition
0x18002b5ec  mov     rcx, r12; lpFileName
0x18002b5ef  call    cs:__imp_CreateFileW
0x18002b5f6  nop     dword ptr [rax+rax+00h]
0x18002b5fb  mov     rdi, rax
0x18002b5fe  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18002b602  jnz     short loc_18002B66A
0x18002b604  call    cs:__imp_GetLastError
0x18002b60b  nop     dword ptr [rax+rax+00h]
0x18002b610  mov     ebx, eax
0x18002b612  cmp     eax, 20h ; ' '
0x18002b615  jnz     short loc_18002B657
0x18002b617  call    cs:__imp_rand
0x18002b61e  nop     dword ptr [rax+rax+00h]
0x18002b623  mov     ecx, eax
0x18002b625  mov     eax, 10624DD3h
0x18002b62a  imul    ecx
0x18002b62c  sar     edx, 4
0x18002b62f  mov     eax, edx
0x18002b631  shr     eax, 1Fh
0x18002b634  add     edx, eax
0x18002b636  imul    eax, edx, 0FAh
0x18002b63c  sub     ecx, eax
0x18002b63e  add     ecx, 0FAh; dwMilliseconds
0x18002b644  call    cs:__imp_Sleep
0x18002b64b  nop     dword ptr [rax+rax+00h]
0x18002b650  dec     esi
0x18002b652  jmp     loc_18002B5C2
0x18002b657  test    ebx, ebx
0x18002b659  jz      short loc_18002B66A
0x18002b65b  jle     short loc_18002B666
0x18002b65d  movzx   ebx, bx
0x18002b660  or      ebx, 80070000h
0x18002b666  mov     eax, ebx
0x18002b668  jmp     short loc_18002B66F
0x18002b66a  mov     [r14], rdi
0x18002b66d  xor     eax, eax
0x18002b66f  add     rsp, 40h
0x18002b673  pop     r15
0x18002b675  pop     r14
0x18002b677  pop     r12
0x18002b679  pop     rdi
0x18002b67a  pop     rsi
0x18002b67b  pop     rbp
0x18002b67c  pop     rbx
0x18002b67d  retn
```
