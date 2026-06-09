# WdsGetParentFolderPathHelper

- ea: `0x18001d2b0`
- end: `0x18001d447`
- name: `WdsGetParentFolderPathHelper`
- size: `407`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x18001d450`
- `0x18001d4e0`

## callees

- `0x18000214c`
- `0x18001b0cc`
- `0x18001b1a0`
- `0x18001d2b0`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18001d41a`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001d41a`
- `KERNEL32!GetFullPathNameW` at `0x18001d2f3`
- `KERNEL32!GetFullPathNameW` at `0x18001d383`
- `KERNEL32!GetFullPathNameW` at `0x18001d2f3`
- `KERNEL32!GetFullPathNameW` at `0x18001d383`
- `KERNEL32!GetLastError` at `0x18001d306`
- `KERNEL32!GetLastError` at `0x18001d393`
- `KERNEL32!GetLastError` at `0x18001d306`
- `KERNEL32!GetLastError` at `0x18001d393`

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
0x18001d2b0  mov     [rsp+arg_8], rbx
0x18001d2b5  mov     [rsp+arg_10], rbp
0x18001d2ba  push    rsi
0x18001d2bb  push    rdi
0x18001d2bc  push    r12
0x18001d2be  push    r14
0x18001d2c0  push    r15
0x18001d2c2  sub     rsp, 20h
0x18001d2c6  xor     r12d, r12d
0x18001d2c9  mov     r15, rdx
0x18001d2cc  mov     rbx, rcx
0x18001d2cf  test    rcx, rcx
0x18001d2d2  jz      loc_18001D428
0x18001d2d8  cmp     [rcx], r12w
0x18001d2dc  jz      loc_18001D428
0x18001d2e2  test    rdx, rdx
0x18001d2e5  jz      loc_18001D428
0x18001d2eb  xor     r9d, r9d; lpFilePart
0x18001d2ee  xor     r8d, r8d; lpBuffer
0x18001d2f1  xor     edx, edx; nBufferLength
0x18001d2f3  call    cs:__imp_GetFullPathNameW
0x18001d2fa  nop     dword ptr [rax+rax+00h]
0x18001d2ff  mov     r14d, eax
0x18001d302  test    eax, eax
0x18001d304  jnz     short loc_18001D340
0x18001d306  call    cs:__imp_GetLastError
0x18001d30d  nop     dword ptr [rax+rax+00h]
0x18001d312  mov     ecx, eax
0x18001d314  mov     r9d, 3A5h
0x18001d31a  call    ElValidateWin32_8
0x18001d31f  mov     ebx, eax
0x18001d321  test    eax, eax
0x18001d323  jle     short loc_18001D32E
0x18001d325  movzx   ebx, ax
0x18001d328  or      ebx, 80070000h
0x18001d32e  test    ebx, ebx
0x18001d330  js      loc_18001D42D
0x18001d336  mov     ebx, 80004005h
0x18001d33b  jmp     loc_18001D42D
0x18001d340  mov     eax, 2
0x18001d345  mov     rsi, 0FFFFFFFFFFFFFFFFh
0x18001d34c  mul     r14
0x18001d34f  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001d356  cmovo   rax, rsi
0x18001d35a  mov     rcx, rax; unsigned __int64
0x18001d35d  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18001d362  mov     rdi, rax
0x18001d365  mov     rbp, rax
0x18001d368  test    rax, rax
0x18001d36b  jnz     short loc_18001D377
0x18001d36d  mov     ebx, 8007000Eh
0x18001d372  jmp     loc_18001D42D
0x18001d377  xor     r9d, r9d; lpFilePart
0x18001d37a  mov     r8, rdi; lpBuffer
0x18001d37d  mov     edx, r14d; nBufferLength
0x18001d380  mov     rcx, rbx; lpFileName
0x18001d383  call    cs:__imp_GetFullPathNameW
0x18001d38a  nop     dword ptr [rax+rax+00h]
0x18001d38f  test    eax, eax
0x18001d391  jnz     short loc_18001D3C6
0x18001d393  call    cs:__imp_GetLastError
0x18001d39a  nop     dword ptr [rax+rax+00h]
0x18001d39f  mov     ecx, eax
0x18001d3a1  mov     r9d, 3B9h
0x18001d3a7  call    ElValidateWin32_8
0x18001d3ac  mov     ebx, eax
0x18001d3ae  test    eax, eax
0x18001d3b0  jle     short loc_18001D3BB
0x18001d3b2  movzx   ebx, ax
0x18001d3b5  or      ebx, 80070000h
0x18001d3bb  test    ebx, ebx
0x18001d3bd  js      short loc_18001D417
0x18001d3bf  mov     ebx, 80004005h
0x18001d3c4  jmp     short loc_18001D417
0x18001d3c6  inc     rsi
0x18001d3c9  cmp     [rdi+rsi*2], r12w
0x18001d3ce  jnz     short loc_18001D3C6
0x18001d3d0  cmp     rsi, 3
0x18001d3d4  jnb     short loc_18001D3DD
0x18001d3d6  mov     ebx, 800700A1h
0x18001d3db  jmp     short loc_18001D417
0x18001d3dd  mov     rcx, rdi
0x18001d3e0  call    GetFileNameFromPath
0x18001d3e5  cmp     [rax], r12w
0x18001d3e9  jnz     short loc_18001D3F0
0x18001d3eb  mov     rbp, r12
0x18001d3ee  jmp     short loc_18001D40C
0x18001d3f0  cmp     word ptr [rax-2], 5Ch ; '\'
0x18001d3f5  jnz     short loc_18001D404
0x18001d3f7  cmp     word ptr [rax-4], 3Ah ; ':'
0x18001d3fc  jnz     short loc_18001D404
0x18001d3fe  mov     [rax], r12w
0x18001d402  jmp     short loc_18001D409
0x18001d404  mov     [rax-2], r12w
0x18001d409  mov     rdi, r12
0x18001d40c  mov     [r15], rbp
0x18001d40f  mov     ebx, r12d
0x18001d412  test    rdi, rdi
0x18001d415  jz      short loc_18001D42D
0x18001d417  mov     rcx, rdi
0x18001d41a  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18001d421  nop     dword ptr [rax+rax+00h]
0x18001d426  jmp     short loc_18001D42D
0x18001d428  mov     ebx, 80070057h
0x18001d42d  mov     rbp, [rsp+48h+arg_10]
0x18001d432  mov     eax, ebx
0x18001d434  mov     rbx, [rsp+48h+arg_8]
0x18001d439  add     rsp, 20h
0x18001d43d  pop     r15
0x18001d43f  pop     r14
0x18001d441  pop     r12
0x18001d443  pop     rdi
0x18001d444  pop     rsi
0x18001d445  retn
```
