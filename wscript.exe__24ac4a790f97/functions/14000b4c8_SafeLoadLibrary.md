# SafeLoadLibrary

- ea: `0x14000b4c8`
- end: `0x14000b5ca`
- name: `SafeLoadLibrary`
- size: `258`
- prototype: `__int64 __fastcall(char *Source)`
- caller_count: `3`
- callee_count: `3`
- tags: `file_ops, loader_planting`

## callers

- `0x14000b5d0`
- `0x14000b8c8`
- `0x14000bb38`

## callees

- `0x140001008`
- `0x140001048`
- `0x14000b4c8`

## import_xrefs

- `msvcrt!strcpy_s` at `0x14000b57c`
- `msvcrt!strcpy_s` at `0x14000b58c`
- `msvcrt!strcpy_s` at `0x14000b57c`
- `msvcrt!strcpy_s` at `0x14000b58c`
- `KERNEL32!GetLastError` at `0x14000b4fa`
- `KERNEL32!GetLastError` at `0x14000b550`
- `KERNEL32!GetLastError` at `0x14000b4fa`
- `KERNEL32!GetLastError` at `0x14000b550`
- `KERNEL32!GetSystemDirectoryA` at `0x14000b4ee`
- `KERNEL32!GetSystemDirectoryA` at `0x14000b546`
- `KERNEL32!GetSystemDirectoryA` at `0x14000b4ee`
- `KERNEL32!GetSystemDirectoryA` at `0x14000b546`
- `KERNEL32!LoadLibraryExA` at `0x14000b59d`
- `KERNEL32!LoadLibraryExA` at `0x14000b59d`

## pseudocode

```c
__int64 __fastcall SafeLoadLibrary(char *Source, HMODULE *a2)
{
  UINT SystemDirectoryA; // ebx
  signed int v5; // eax
  unsigned int v6; // ebx
  __int64 v7; // rax
  unsigned int v8; // edi
  CHAR *v9; // rax
  CHAR *v10; // rsi
  UINT v11; // eax
  signed int LastError; // eax
  UINT v13; // ebx
  char *v14; // rdi
  HMODULE Library; // rax
  CHAR Buffer; // [rsp+48h] [rbp+10h] BYREF

  *a2 = 0;
  SystemDirectoryA = GetSystemDirectoryA(&Buffer, 0);
  if ( SystemDirectoryA )
  {
    v7 = -1;
    do
      ++v7;
    while ( Source[v7] );
    v8 = v7 + SystemDirectoryA + 2;
    v9 = (CHAR *)operator new(v8);
    v10 = v9;
    if ( v9 )
    {
      v11 = GetSystemDirectoryA(v9, SystemDirectoryA + 1);
      if ( v11
        && (v13 = v8 - v11,
            v14 = &v10[v11],
            strcpy_s(v14, v13, "\\"),
            strcpy_s(v14 + 1, v13 - 1, Source),
            (Library = LoadLibraryExA(v10, 0, 0x800u)) != 0) )
      {
        *a2 = Library;
        v6 = 0;
      }
      else
      {
        LastError = GetLastError();
        v6 = LastError;
        if ( LastError > 0 )
          v6 = (unsigned __int16)LastError | 0x80070000;
      }
      operator delete(v10);
    }
    else
    {
      return (unsigned int)-2147024882;
    }
  }
  else
  {
    v5 = GetLastError();
    v6 = v5;
    if ( v5 > 0 )
      return (unsigned __int16)v5 | 0x80070000;
  }
  return v6;
}

```

## disassembly

```asm
0x14000b4c8  mov     [rsp+arg_0], rbx
0x14000b4cd  mov     [rsp+arg_10], rbp
0x14000b4d2  push    rsi
0x14000b4d3  push    rdi
0x14000b4d4  push    r14
0x14000b4d6  sub     rsp, 20h
0x14000b4da  mov     r14, rdx
0x14000b4dd  mov     qword ptr [rdx], 0
0x14000b4e4  mov     rbp, rcx
0x14000b4e7  xor     edx, edx; uSize
0x14000b4e9  lea     rcx, [rsp+38h+Buffer]; lpBuffer
0x14000b4ee  call    cs:__imp_GetSystemDirectoryA
0x14000b4f4  mov     ebx, eax
0x14000b4f6  test    eax, eax
0x14000b4f8  jnz     short loc_14000B518
0x14000b4fa  call    cs:__imp_GetLastError
0x14000b500  mov     ebx, eax
0x14000b502  test    eax, eax
0x14000b504  jle     loc_14000B5B5
0x14000b50a  movzx   ebx, ax
0x14000b50d  or      ebx, 80070000h
0x14000b513  jmp     loc_14000B5B5
0x14000b518  or      rax, 0FFFFFFFFFFFFFFFFh
0x14000b51c  inc     rax
0x14000b51f  cmp     byte ptr [rax+rbp], 0
0x14000b523  jnz     short loc_14000B51C
0x14000b525  lea     edi, [rbx+2]
0x14000b528  add     edi, eax
0x14000b52a  mov     ecx, edi; Size
0x14000b52c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14000b531  mov     rsi, rax
0x14000b534  test    rax, rax
0x14000b537  jnz     short loc_14000B540
0x14000b539  mov     ebx, 8007000Eh
0x14000b53e  jmp     short loc_14000B5B5
0x14000b540  lea     edx, [rbx+1]; uSize
0x14000b543  mov     rcx, rsi; lpBuffer
0x14000b546  call    cs:__imp_GetSystemDirectoryA
0x14000b54c  test    eax, eax
0x14000b54e  jnz     short loc_14000B567
0x14000b550  call    cs:__imp_GetLastError
0x14000b556  mov     ebx, eax
0x14000b558  test    eax, eax
0x14000b55a  jle     short loc_14000B5AD
0x14000b55c  movzx   ebx, ax
0x14000b55f  or      ebx, 80070000h
0x14000b565  jmp     short loc_14000B5AD
0x14000b567  sub     edi, eax
0x14000b569  lea     r8, asc_14001BBBC; "\\"
0x14000b570  mov     ebx, edi
0x14000b572  mov     edi, eax
0x14000b574  mov     edx, ebx; SizeInBytes
0x14000b576  add     rdi, rsi
0x14000b579  mov     rcx, rdi; Destination
0x14000b57c  call    cs:__imp_strcpy_s
0x14000b582  lea     edx, [rbx-1]; SizeInBytes
0x14000b585  mov     r8, rbp; Source
0x14000b588  lea     rcx, [rdi+1]; Destination
0x14000b58c  call    cs:__imp_strcpy_s
0x14000b592  xor     edx, edx; hFile
0x14000b594  mov     r8d, 800h; dwFlags
0x14000b59a  mov     rcx, rsi; lpLibFileName
0x14000b59d  call    cs:__imp_LoadLibraryExA
0x14000b5a3  test    rax, rax
0x14000b5a6  jz      short loc_14000B550
0x14000b5a8  mov     [r14], rax
0x14000b5ab  xor     ebx, ebx
0x14000b5ad  mov     rcx, rsi; Block
0x14000b5b0  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14000b5b5  mov     rbp, [rsp+38h+arg_10]
0x14000b5ba  mov     eax, ebx
0x14000b5bc  mov     rbx, [rsp+38h+arg_0]
0x14000b5c1  add     rsp, 20h
0x14000b5c5  pop     r14
0x14000b5c7  pop     rdi
0x14000b5c8  pop     rsi
0x14000b5c9  retn
```
