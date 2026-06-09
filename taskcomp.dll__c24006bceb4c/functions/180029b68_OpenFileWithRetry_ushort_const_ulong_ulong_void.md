# OpenFileWithRetry(ushort const *,ulong,ulong,void * *)

- ea: `0x180029b68`
- end: `0x180029c27`
- name: `?OpenFileWithRetry@@YAJPEBGKKPEAPEAX@Z`
- size: `191`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName, DWORD dwDesiredAccess, DWORD dwShareMode, void **)`
- caller_count: `3`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x18000ac28`
- `0x180015280`
- `0x1800242b4`

## callees

- `0x180029b68`

## import_xrefs

- `msvcrt!rand` at `0x180029bcf`
- `msvcrt!rand` at `0x180029bcf`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180029bf6`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180029bf6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029bc2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029bc2`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180029bb3`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180029bb3`

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
0x180029b68  push    rbx
0x180029b6a  push    rbp
0x180029b6b  push    rsi
0x180029b6c  push    rdi
0x180029b6d  push    r12
0x180029b6f  push    r14
0x180029b71  push    r15
0x180029b73  sub     rsp, 40h
0x180029b77  xor     ebx, ebx
0x180029b79  mov     r14, r9
0x180029b7c  mov     ebp, r8d
0x180029b7f  mov     r15d, edx
0x180029b82  mov     r12, rcx
0x180029b85  xor     edi, edi
0x180029b87  lea     esi, [rbx+3]
0x180029b8a  test    esi, esi
0x180029b8c  jz      short loc_180029C00
0x180029b8e  mov     [rsp+78h+hTemplateFile], 0; hTemplateFile
0x180029b97  xor     r9d, r9d; lpSecurityAttributes
0x180029b9a  mov     [rsp+78h+dwFlagsAndAttributes], 8000000h; dwFlagsAndAttributes
0x180029ba2  mov     r8d, ebp; dwShareMode
0x180029ba5  mov     edx, r15d; dwDesiredAccess
0x180029ba8  mov     [rsp+78h+dwCreationDisposition], 3; dwCreationDisposition
0x180029bb0  mov     rcx, r12; lpFileName
0x180029bb3  call    cs:__imp_CreateFileW
0x180029bb9  mov     rdi, rax
0x180029bbc  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180029bc0  jnz     short loc_180029C13
0x180029bc2  call    cs:__imp_GetLastError
0x180029bc8  mov     ebx, eax
0x180029bca  cmp     eax, 20h ; ' '
0x180029bcd  jnz     short loc_180029C00
0x180029bcf  call    cs:__imp_rand
0x180029bd5  mov     ecx, eax
0x180029bd7  mov     eax, 10624DD3h
0x180029bdc  imul    ecx
0x180029bde  sar     edx, 4
0x180029be1  mov     eax, edx
0x180029be3  shr     eax, 1Fh
0x180029be6  add     edx, eax
0x180029be8  imul    eax, edx, 0FAh
0x180029bee  sub     ecx, eax
0x180029bf0  add     ecx, 0FAh; dwMilliseconds
0x180029bf6  call    cs:__imp_Sleep
0x180029bfc  dec     esi
0x180029bfe  jmp     short loc_180029B8A
0x180029c00  test    ebx, ebx
0x180029c02  jz      short loc_180029C13
0x180029c04  jle     short loc_180029C0F
0x180029c06  movzx   ebx, bx
0x180029c09  or      ebx, 80070000h
0x180029c0f  mov     eax, ebx
0x180029c11  jmp     short loc_180029C18
0x180029c13  mov     [r14], rdi
0x180029c16  xor     eax, eax
0x180029c18  add     rsp, 40h
0x180029c1c  pop     r15
0x180029c1e  pop     r14
0x180029c20  pop     r12
0x180029c22  pop     rdi
0x180029c23  pop     rsi
0x180029c24  pop     rbp
0x180029c25  pop     rbx
0x180029c26  retn
```
