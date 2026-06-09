# WdsGetParentFolderPathHelper

- ea: `0x18001c3b0`
- end: `0x18001c540`
- name: `WdsGetParentFolderPathHelper`
- size: `400`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x18001c550`
- `0x18001c5e0`

## callees

- `0x18000179c`
- `0x18001a28c`
- `0x18001a360`
- `0x18001c3b0`
- `0x18002e468`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18001c406`
- `KERNEL32!GetLastError` at `0x18001c493`
- `KERNEL32!GetLastError` at `0x18001c406`
- `KERNEL32!GetLastError` at `0x18001c493`
- `KERNEL32!GetFullPathNameW` at `0x18001c3f3`
- `KERNEL32!GetFullPathNameW` at `0x18001c483`
- `KERNEL32!GetFullPathNameW` at `0x18001c3f3`
- `KERNEL32!GetFullPathNameW` at `0x18001c483`

## pseudocode

```c
__int64 __fastcall WdsGetParentFolderPathHelper(LPCWSTR lpFileName, WCHAR **a2)
{
  DWORD FullPathNameW; // eax
  unsigned __int64 v5; // r14
  DWORD LastError; // eax
  __int64 v7; // rdx
  __int64 v8; // r8
  int v9; // eax
  signed int v10; // ebx
  unsigned __int64 v11; // rsi
  unsigned __int64 v12; // rax
  WCHAR *v13; // rax
  WCHAR *v14; // rdi
  WCHAR *v15; // rbp
  DWORD v16; // eax
  __int64 v17; // rdx
  __int64 v18; // r8
  int v19; // eax
  _WORD *FileNameFromPath; // rax

  if ( !lpFileName || !*lpFileName || !a2 )
    return (unsigned int)-2147024809;
  FullPathNameW = GetFullPathNameW(lpFileName, 0, 0, 0);
  v5 = FullPathNameW;
  if ( !FullPathNameW )
  {
    LastError = GetLastError();
    v9 = ElValidateWin32_8(LastError, v7, v8, 933);
    v10 = v9;
    if ( v9 > 0 )
      v10 = (unsigned __int16)v9 | 0x80070000;
    if ( v10 >= 0 )
      return (unsigned int)-2147467259;
    return (unsigned int)v10;
  }
  v11 = -1;
  v12 = 2LL * FullPathNameW;
  if ( !is_mul_ok(v5, 2u) )
    v12 = -1;
  v13 = (WCHAR *)operator new[](v12, (const struct std::nothrow_t *)&std::nothrow);
  v14 = v13;
  v15 = v13;
  if ( !v13 )
    return (unsigned int)-2147024882;
  if ( !GetFullPathNameW(lpFileName, v5, v13, 0) )
  {
    v16 = GetLastError();
    v19 = ElValidateWin32_8(v16, v17, v18, 953);
    v10 = v19;
    if ( v19 > 0 )
      v10 = (unsigned __int16)v19 | 0x80070000;
    if ( v10 >= 0 )
      v10 = -2147467259;
    goto LABEL_29;
  }
  do
    ++v11;
  while ( v14[v11] );
  if ( v11 < 3 )
  {
    v10 = -2147024735;
LABEL_29:
    operator delete(v14);
    return (unsigned int)v10;
  }
  FileNameFromPath = (_WORD *)GetFileNameFromPath(v14);
  if ( *FileNameFromPath )
  {
    if ( *(FileNameFromPath - 1) == 92 && *(FileNameFromPath - 2) == 58 )
      *FileNameFromPath = 0;
    else
      *(FileNameFromPath - 1) = 0;
    v14 = 0;
  }
  else
  {
    v15 = 0;
  }
  *a2 = v15;
  v10 = 0;
  if ( v14 )
    goto LABEL_29;
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18001c3b0  mov     [rsp+arg_8], rbx
0x18001c3b5  mov     [rsp+arg_10], rbp
0x18001c3ba  push    rsi
0x18001c3bb  push    rdi
0x18001c3bc  push    r12
0x18001c3be  push    r14
0x18001c3c0  push    r15
0x18001c3c2  sub     rsp, 20h
0x18001c3c6  xor     r12d, r12d
0x18001c3c9  mov     r15, rdx
0x18001c3cc  mov     rbx, rcx
0x18001c3cf  test    rcx, rcx
0x18001c3d2  jz      loc_18001C521
0x18001c3d8  cmp     [rcx], r12w
0x18001c3dc  jz      loc_18001C521
0x18001c3e2  test    rdx, rdx
0x18001c3e5  jz      loc_18001C521
0x18001c3eb  xor     r9d, r9d; lpFilePart
0x18001c3ee  xor     r8d, r8d; lpBuffer
0x18001c3f1  xor     edx, edx; nBufferLength
0x18001c3f3  call    cs:__imp_GetFullPathNameW
0x18001c3fa  nop     dword ptr [rax+rax+00h]
0x18001c3ff  mov     r14d, eax
0x18001c402  test    eax, eax
0x18001c404  jnz     short loc_18001C440
0x18001c406  call    cs:__imp_GetLastError
0x18001c40d  nop     dword ptr [rax+rax+00h]
0x18001c412  mov     ecx, eax
0x18001c414  mov     r9d, 3A5h
0x18001c41a  call    ElValidateWin32_8
0x18001c41f  mov     ebx, eax
0x18001c421  test    eax, eax
0x18001c423  jle     short loc_18001C42E
0x18001c425  movzx   ebx, ax
0x18001c428  or      ebx, 80070000h
0x18001c42e  test    ebx, ebx
0x18001c430  js      loc_18001C526
0x18001c436  mov     ebx, 80004005h
0x18001c43b  jmp     loc_18001C526
0x18001c440  mov     eax, 2
0x18001c445  mov     rsi, 0FFFFFFFFFFFFFFFFh
0x18001c44c  mul     r14
0x18001c44f  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001c456  cmovo   rax, rsi
0x18001c45a  mov     rcx, rax; unsigned __int64
0x18001c45d  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18001c462  mov     rdi, rax
0x18001c465  mov     rbp, rax
0x18001c468  test    rax, rax
0x18001c46b  jnz     short loc_18001C477
0x18001c46d  mov     ebx, 8007000Eh
0x18001c472  jmp     loc_18001C526
0x18001c477  xor     r9d, r9d; lpFilePart
0x18001c47a  mov     r8, rdi; lpBuffer
0x18001c47d  mov     edx, r14d; nBufferLength
0x18001c480  mov     rcx, rbx; lpFileName
0x18001c483  call    cs:__imp_GetFullPathNameW
0x18001c48a  nop     dword ptr [rax+rax+00h]
0x18001c48f  test    eax, eax
0x18001c491  jnz     short loc_18001C4C6
0x18001c493  call    cs:__imp_GetLastError
0x18001c49a  nop     dword ptr [rax+rax+00h]
0x18001c49f  mov     ecx, eax
0x18001c4a1  mov     r9d, 3B9h
0x18001c4a7  call    ElValidateWin32_8
0x18001c4ac  mov     ebx, eax
0x18001c4ae  test    eax, eax
0x18001c4b0  jle     short loc_18001C4BB
0x18001c4b2  movzx   ebx, ax
0x18001c4b5  or      ebx, 80070000h
0x18001c4bb  test    ebx, ebx
0x18001c4bd  js      short loc_18001C517
0x18001c4bf  mov     ebx, 80004005h
0x18001c4c4  jmp     short loc_18001C517
0x18001c4c6  inc     rsi
0x18001c4c9  cmp     [rdi+rsi*2], r12w
0x18001c4ce  jnz     short loc_18001C4C6
0x18001c4d0  cmp     rsi, 3
0x18001c4d4  jnb     short loc_18001C4DD
0x18001c4d6  mov     ebx, 800700A1h
0x18001c4db  jmp     short loc_18001C517
0x18001c4dd  mov     rcx, rdi
0x18001c4e0  call    GetFileNameFromPath
0x18001c4e5  cmp     [rax], r12w
0x18001c4e9  jnz     short loc_18001C4F0
0x18001c4eb  mov     rbp, r12
0x18001c4ee  jmp     short loc_18001C50C
0x18001c4f0  cmp     word ptr [rax-2], 5Ch ; '\'
0x18001c4f5  jnz     short loc_18001C504
0x18001c4f7  cmp     word ptr [rax-4], 3Ah ; ':'
0x18001c4fc  jnz     short loc_18001C504
0x18001c4fe  mov     [rax], r12w
0x18001c502  jmp     short loc_18001C509
0x18001c504  mov     [rax-2], r12w
0x18001c509  mov     rdi, r12
0x18001c50c  mov     [r15], rbp
0x18001c50f  mov     ebx, r12d
0x18001c512  test    rdi, rdi
0x18001c515  jz      short loc_18001C526
0x18001c517  mov     rcx, rdi; lpMem
0x18001c51a  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001c51f  jmp     short loc_18001C526
0x18001c521  mov     ebx, 80070057h
0x18001c526  mov     rbp, [rsp+48h+arg_10]
0x18001c52b  mov     eax, ebx
0x18001c52d  mov     rbx, [rsp+48h+arg_8]
0x18001c532  add     rsp, 20h
0x18001c536  pop     r15
0x18001c538  pop     r14
0x18001c53a  pop     r12
0x18001c53c  pop     rdi
0x18001c53d  pop     rsi
0x18001c53e  retn
```
