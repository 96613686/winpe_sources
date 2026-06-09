# MakeSureDirectoryPathExistsW

- ea: `0x14003a6e4`
- end: `0x14003a868`
- name: `MakeSureDirectoryPathExistsW`
- size: `388`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x14003aab0`

## callees

- `0x1400020e4`
- `0x140002bf0`
- `0x140038850`
- `0x14003a6e4`

## import_xrefs

- `msvcrt!wcschr` at `0x14003a832`
- `msvcrt!wcschr` at `0x14003a832`
- `msvcrt!fprintf` at `0x14003a7e1`
- `msvcrt!fprintf` at `0x14003a823`
- `msvcrt!fprintf` at `0x14003a7e1`
- `msvcrt!fprintf` at `0x14003a823`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003a7b9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003a7b9`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x14003a7af`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x14003a7af`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x14003a79e`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x14003a79e`

## string_xrefs

- `0x14003a7d7`: `WPPFMT : error : Failed to create directory %ws\n`
- `0x14003a819`: `WPPFMT : error : File already exists and is not a directory: %ws\n`

## pseudocode

```c
char __fastcall MakeSureDirectoryPathExistsW(_QWORD *a1)
{
  unsigned __int64 v1; // rax
  _WORD *v2; // rdi
  _WORD *v3; // rbx
  _WORD *v4; // r8
  _WORD *v5; // rax
  const wchar_t *i; // rcx
  DWORD FileAttributesW; // eax
  LPCWSTR v8; // rbx
  FILE *v9; // rax
  LPCWSTR v11; // rbx
  FILE *v12; // rax
  wchar_t *v13; // rax
  wchar_t *v14; // rdi
  LPCWSTR lpFileName[2]; // [rsp+20h] [rbp-28h] BYREF
  _WORD v16[12]; // [rsp+30h] [rbp-18h] BYREF

  v1 = a1[1];
  v2 = (_WORD *)*a1;
  v3 = (_WORD *)*a1;
  if ( v1 >= 2 && v2[1] == 58 )
    v3 = v2 + 2;
  v4 = &v2[v1];
  while ( v4 != v3 )
  {
    v5 = v4--;
    if ( *v4 == 46 )
    {
      while ( v4 != v3 )
      {
        v5 = v4--;
        if ( *v4 == 47 || *v4 == 92 )
          goto LABEL_14;
      }
      break;
    }
    if ( *v4 == 47 || *v4 == 92 )
    {
LABEL_14:
      v4 = v5;
      break;
    }
  }
  lpFileName[0] = v16;
  lpFileName[1] = v16;
  v16[0] = 0;
  if ( (unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                          lpFileName,
                          v2,
                          v4 - v2) )
  {
    for ( i = &lpFileName[0][v3 - v2]; ; i = v14 + 1 )
    {
      v13 = wcschr(i, 0x5Cu);
      v14 = v13;
      if ( !v13 )
        break;
      *v13 = 0;
      FileAttributesW = GetFileAttributesW(lpFileName[0]);
      if ( FileAttributesW == -1 )
      {
        if ( !CreateDirectoryW(lpFileName[0], 0) && GetLastError() != 183 )
        {
          v8 = lpFileName[0];
          v9 = _acrt_iob_func(2u);
          fprintf(v9, "WPPFMT : error : Failed to create directory %ws\n", v8);
          goto LABEL_21;
        }
      }
      else if ( (FileAttributesW & 0x10) == 0 )
      {
        v11 = lpFileName[0];
        v12 = _acrt_iob_func(2u);
        fprintf(v12, "WPPFMT : error : File already exists and is not a directory: %ws\n", v11);
      }
      *v14 = 92;
    }
    if ( lpFileName[0] != v16 )
      operator delete((void *)lpFileName[0], (const struct std::nothrow_t *)&std::nothrow);
    return 1;
  }
  else
  {
LABEL_21:
    if ( lpFileName[0] != v16 )
      operator delete((void *)lpFileName[0], (const struct std::nothrow_t *)&std::nothrow);
    return 0;
  }
}

```

## disassembly

```asm
0x14003a6e4  push    rbp
0x14003a6e6  push    rbx
0x14003a6e7  push    rsi
0x14003a6e8  push    rdi
0x14003a6e9  mov     rbp, rsp
0x14003a6ec  sub     rsp, 48h
0x14003a6f0  mov     rax, [rcx+8]
0x14003a6f4  mov     rdi, [rcx]
0x14003a6f7  mov     rbx, rdi
0x14003a6fa  cmp     rax, 2
0x14003a6fe  jb      short loc_14003A70B
0x14003a700  cmp     word ptr [rdi+2], 3Ah ; ':'
0x14003a705  jnz     short loc_14003A70B
0x14003a707  lea     rbx, [rdi+4]
0x14003a70b  lea     r8, [rdi+rax*2]
0x14003a70f  mov     esi, 5Ch ; '\'
0x14003a714  jmp     short loc_14003A731
0x14003a716  mov     rax, r8
0x14003a719  sub     r8, 2
0x14003a71d  cmp     word ptr [r8], 2Eh ; '.'
0x14003a722  jz      short loc_14003A74C
0x14003a724  cmp     word ptr [r8], 2Fh ; '/'
0x14003a729  jz      short loc_14003A753
0x14003a72b  cmp     [r8], si
0x14003a72f  jz      short loc_14003A753
0x14003a731  cmp     r8, rbx
0x14003a734  jnz     short loc_14003A716
0x14003a736  jmp     short loc_14003A756
0x14003a738  mov     rax, r8
0x14003a73b  sub     r8, 2
0x14003a73f  cmp     word ptr [r8], 2Fh ; '/'
0x14003a744  jz      short loc_14003A753
0x14003a746  cmp     [r8], si
0x14003a74a  jz      short loc_14003A753
0x14003a74c  cmp     r8, rbx
0x14003a74f  jnz     short loc_14003A738
0x14003a751  jmp     short loc_14003A756
0x14003a753  mov     r8, rax
0x14003a756  lea     rax, [rbp+var_18]
0x14003a75a  sub     r8, rdi
0x14003a75d  mov     [rbp+lpFileName], rax
0x14003a761  lea     rcx, [rbp+lpFileName]
0x14003a765  lea     rax, [rbp+var_18]
0x14003a769  sar     r8, 1
0x14003a76c  mov     [rbp+var_20], rax
0x14003a770  mov     rdx, rdi
0x14003a773  xor     eax, eax
0x14003a775  mov     [rbp+var_18], ax
0x14003a779  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *,unsigned __int64)
0x14003a77e  test    al, al
0x14003a780  jz      short loc_14003A7E7
0x14003a782  mov     rax, [rbp+lpFileName]
0x14003a786  sub     rbx, rdi
0x14003a789  sar     rbx, 1
0x14003a78c  lea     rcx, [rax+rbx*2]
0x14003a790  jmp     loc_14003A830
0x14003a795  xor     ecx, ecx
0x14003a797  mov     [rdi], cx
0x14003a79a  mov     rcx, [rbp+lpFileName]; lpFileName
0x14003a79e  call    cs:__imp_GetFileAttributesW
0x14003a7a4  cmp     eax, 0FFFFFFFFh
0x14003a7a7  jnz     short loc_14003A804
0x14003a7a9  mov     rcx, [rbp+lpFileName]; lpPathName
0x14003a7ad  xor     edx, edx; lpSecurityAttributes
0x14003a7af  call    cs:__imp_CreateDirectoryW
0x14003a7b5  test    eax, eax
0x14003a7b7  jnz     short loc_14003A829
0x14003a7b9  call    cs:__imp_GetLastError
0x14003a7bf  cmp     eax, 0B7h
0x14003a7c4  jz      short loc_14003A829
0x14003a7c6  mov     rbx, [rbp+lpFileName]
0x14003a7ca  mov     ecx, 2; Ix
0x14003a7cf  call    __acrt_iob_func
0x14003a7d4  mov     r8, rbx
0x14003a7d7  lea     rdx, aWppfmtErrorFai_3; "WPPFMT : error : Failed to create direc"...
0x14003a7de  mov     rcx, rax; Stream
0x14003a7e1  call    cs:__imp_fprintf
0x14003a7e7  mov     rcx, [rbp+lpFileName]; void *
0x14003a7eb  lea     rax, [rbp+var_18]
0x14003a7ef  cmp     rcx, rax
0x14003a7f2  jz      short loc_14003A800
0x14003a7f4  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14003a7fb  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14003a800  xor     al, al
0x14003a802  jmp     short loc_14003A85F
0x14003a804  test    al, 10h
0x14003a806  jnz     short loc_14003A829
0x14003a808  mov     rbx, [rbp+lpFileName]
0x14003a80c  mov     ecx, 2; Ix
0x14003a811  call    __acrt_iob_func
0x14003a816  mov     r8, rbx
0x14003a819  lea     rdx, aWppfmtErrorFil; "WPPFMT : error : File already exists an"...
0x14003a820  mov     rcx, rax; Stream
0x14003a823  call    cs:__imp_fprintf
0x14003a829  mov     [rdi], si
0x14003a82c  lea     rcx, [rdi+2]; Str
0x14003a830  mov     edx, esi; Ch
0x14003a832  call    cs:__imp_wcschr
0x14003a838  mov     rdi, rax
0x14003a83b  test    rax, rax
0x14003a83e  jnz     loc_14003A795
0x14003a844  mov     rcx, [rbp+lpFileName]; void *
0x14003a848  lea     rax, [rbp+var_18]
0x14003a84c  cmp     rcx, rax
0x14003a84f  jz      short loc_14003A85D
0x14003a851  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14003a858  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14003a85d  mov     al, 1
0x14003a85f  add     rsp, 48h
0x14003a863  pop     rdi
0x14003a864  pop     rsi
0x14003a865  pop     rbx
0x14003a866  pop     rbp
0x14003a867  retn
```
