# WdsGetFullPath

- ea: `0x18001bec0`
- end: `0x18001c274`
- name: `WdsGetFullPath`
- size: `948`
- prototype: `__int64 __fastcall(LPCWSTR pszPath)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x18001c730`

## callees

- `0x18000179c`
- `0x180014ce0`
- `0x180019a40`
- `0x18001a28c`
- `0x18001a980`
- `0x18001bec0`
- `0x18002e468`

## import_xrefs

- `KERNEL32!GetCurrentDirectoryW` at `0x18001bf36`
- `KERNEL32!GetCurrentDirectoryW` at `0x18001bfb3`
- `KERNEL32!GetCurrentDirectoryW` at `0x18001c0e9`
- `KERNEL32!GetCurrentDirectoryW` at `0x18001c166`
- `KERNEL32!GetCurrentDirectoryW` at `0x18001bf36`
- `KERNEL32!GetCurrentDirectoryW` at `0x18001bfb3`
- `KERNEL32!GetCurrentDirectoryW` at `0x18001c0e9`
- `KERNEL32!GetCurrentDirectoryW` at `0x18001c166`
- `KERNEL32!GetLastError` at `0x18001bf49`
- `KERNEL32!GetLastError` at `0x18001bfc3`
- `KERNEL32!GetLastError` at `0x18001c0fc`
- `KERNEL32!GetLastError` at `0x18001c176`
- `KERNEL32!GetLastError` at `0x18001bf49`
- `KERNEL32!GetLastError` at `0x18001bfc3`
- `KERNEL32!GetLastError` at `0x18001c0fc`
- `KERNEL32!GetLastError` at `0x18001c176`
- `SHLWAPI!PathGetDriveNumberW` at `0x18001bf00`
- `SHLWAPI!PathGetDriveNumberW` at `0x18001c03e`
- `SHLWAPI!PathGetDriveNumberW` at `0x18001bf00`
- `SHLWAPI!PathGetDriveNumberW` at `0x18001c03e`
- `SHLWAPI!PathIsRelativeW` at `0x18001bf1c`
- `SHLWAPI!PathIsRelativeW` at `0x18001bf1c`
- `SHLWAPI!PathIsUNCW` at `0x18001bee9`
- `SHLWAPI!PathIsUNCW` at `0x18001bee9`

## pseudocode

```c
__int64 __fastcall WdsGetFullPath(LPCWSTR pszPath)
{
  unsigned __int16 *v1; // rdi
  WCHAR *v2; // rsi
  __int64 v4; // rbx
  DWORD v5; // eax
  unsigned __int64 v6; // r14
  DWORD v7; // eax
  __int64 v8; // rdx
  __int64 v9; // r8
  int v10; // eax
  __int64 v11; // rdx
  __int64 v12; // r8
  unsigned __int64 v13; // rax
  WCHAR *v14; // rax
  WCHAR *v15; // r15
  DWORD v16; // eax
  DWORD v17; // eax
  __int64 v18; // rdx
  __int64 v19; // r8
  int v20; // eax
  int DriveNumberW; // ebx
  __int64 v22; // rdx
  __int64 v23; // r8
  int v24; // eax
  __int64 v25; // rdx
  __int64 v26; // r8
  unsigned int v27; // eax
  __int64 v28; // rdx
  __int64 v29; // r8
  __int64 v30; // r9
  DWORD CurrentDirectoryW; // eax
  unsigned __int64 v32; // r14
  DWORD v33; // eax
  __int64 v34; // rdx
  __int64 v35; // r8
  int v36; // eax
  __int64 v37; // rdx
  __int64 v38; // r8
  unsigned __int64 v39; // rax
  WCHAR *v40; // rax
  unsigned __int16 *v41; // r15
  DWORD v42; // eax
  DWORD LastError; // eax
  __int64 v44; // rdx
  __int64 v45; // r8
  int v46; // eax
  __int64 v47; // rdx
  __int64 v48; // r8
  __int64 v49; // rdx
  __int64 v50; // r8
  LPCWSTR pszPatha[2]; // [rsp+20h] [rbp-10h] BYREF
  unsigned __int16 *v53; // [rsp+88h] [rbp+58h] BYREF

  v1 = 0;
  v2 = 0;
  v53 = 0;
  pszPatha[0] = 0;
  if ( PathIsUNCW(pszPath) || PathGetDriveNumberW(pszPath) != -1 )
  {
    v4 = (unsigned int)WdsCanonicalizePath(pszPath);
    ElValidateWin32_8(v4, v49, v50, 3877);
    goto LABEL_58;
  }
  LODWORD(v4) = 0;
  if ( PathIsRelativeW(pszPath) )
  {
    CurrentDirectoryW = GetCurrentDirectoryW(0, 0);
    v32 = CurrentDirectoryW;
    if ( CurrentDirectoryW )
    {
      v39 = 2LL * CurrentDirectoryW;
      if ( !is_mul_ok(v32, 2u) )
        v39 = -1;
      v40 = (WCHAR *)operator new[](v39, (const struct std::nothrow_t *)&std::nothrow);
      v41 = v40;
      if ( !v40 )
      {
        LOWORD(v4) = 14;
        goto LABEL_51;
      }
      v42 = GetCurrentDirectoryW(v32, v40);
      if ( v42 )
      {
        if ( v42 <= (unsigned int)v32 )
        {
          v1 = v41;
          goto LABEL_53;
        }
        LODWORD(v4) = -2147024809;
      }
      else
      {
        LastError = GetLastError();
        v46 = ElValidateWin32_8(LastError, v44, v45, 2802);
        LODWORD(v4) = v46;
        if ( v46 > 0 )
          LODWORD(v4) = (unsigned __int16)v46 | 0x80070000;
        if ( (int)v4 >= 0 )
          LODWORD(v4) = -2147467259;
      }
      operator delete(v41);
    }
    else
    {
      v33 = GetLastError();
      v36 = ElValidateWin32_8(v33, v34, v35, 2784);
      LODWORD(v4) = v36;
      if ( v36 > 0 )
        LODWORD(v4) = (unsigned __int16)v36 | 0x80070000;
      if ( (int)v4 >= 0 )
        LODWORD(v4) = -2147467259;
    }
    if ( (v4 & 0x1FFF0000) != 0x70000 )
    {
LABEL_53:
      if ( (unsigned int)ElValidateWin32_8((unsigned int)v4, v37, v38, 3934) )
        goto LABEL_58;
      v4 = (unsigned int)ConcatenatePaths(v1, pszPath, pszPatha);
      if ( !(unsigned int)ElValidateWin32_8(v4, v47, v48, 3942) )
      {
        v2 = (WCHAR *)pszPatha[0];
        v27 = WdsCanonicalizePath(pszPatha[0]);
        v30 = 3948;
        goto LABEL_32;
      }
      goto LABEL_56;
    }
LABEL_51:
    LODWORD(v4) = (unsigned __int16)v4;
    goto LABEL_53;
  }
  v5 = GetCurrentDirectoryW(0, 0);
  v6 = v5;
  if ( !v5 )
  {
    v7 = GetLastError();
    v10 = ElValidateWin32_8(v7, v8, v9, 2784);
    LODWORD(v4) = v10;
    if ( v10 > 0 )
      LODWORD(v4) = (unsigned __int16)v10 | 0x80070000;
    if ( (int)v4 >= 0 )
      LODWORD(v4) = -2147467259;
LABEL_21:
    if ( (v4 & 0x1FFF0000) != 0x70000 )
      goto LABEL_24;
    goto LABEL_22;
  }
  v13 = 2LL * v5;
  if ( !is_mul_ok(v6, 2u) )
    v13 = -1;
  v14 = (WCHAR *)operator new[](v13, (const struct std::nothrow_t *)&std::nothrow);
  v15 = v14;
  if ( !v14 )
  {
    LOWORD(v4) = 14;
LABEL_22:
    LODWORD(v4) = (unsigned __int16)v4;
    goto LABEL_24;
  }
  v16 = GetCurrentDirectoryW(v6, v14);
  if ( !v16 )
  {
    v17 = GetLastError();
    v20 = ElValidateWin32_8(v17, v18, v19, 2802);
    LODWORD(v4) = v20;
    if ( v20 > 0 )
      LODWORD(v4) = (unsigned __int16)v20 | 0x80070000;
    if ( (int)v4 >= 0 )
      LODWORD(v4) = -2147467259;
    goto LABEL_20;
  }
  if ( v16 > (unsigned int)v6 )
  {
    LODWORD(v4) = -2147024809;
LABEL_20:
    operator delete(v15);
    goto LABEL_21;
  }
  v1 = v15;
  v53 = v15;
LABEL_24:
  if ( (unsigned int)ElValidateWin32_8((unsigned int)v4, v11, v12, 3889) )
    goto LABEL_58;
  DriveNumberW = PathGetDriveNumberW(v1);
  if ( DriveNumberW == -1 )
  {
    LODWORD(v4) = 161;
    goto LABEL_58;
  }
  if ( v1 )
  {
    operator delete(v1);
    v53 = 0;
  }
  v4 = FormatString(&v53, 4u, L"%c:\\", (unsigned int)(DriveNumberW + 65), pszPatha[0]);
  v24 = ElValidateWin32_8(v4, v22, v23, 3907);
  v1 = v53;
  if ( !v24 )
  {
    v4 = (unsigned int)ConcatenatePaths(v53, pszPath, pszPatha);
    if ( !(unsigned int)ElValidateWin32_8(v4, v25, v26, 3916) )
    {
      v2 = (WCHAR *)pszPatha[0];
      v27 = WdsCanonicalizePath(pszPatha[0]);
      v30 = 3922;
LABEL_32:
      LODWORD(v4) = v27;
      ElValidateWin32_8(v27, v28, v29, v30);
      goto LABEL_58;
    }
LABEL_56:
    v2 = (WCHAR *)pszPatha[0];
  }
LABEL_58:
  if ( v1 )
    operator delete(v1);
  if ( v2 )
    operator delete(v2);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18001bec0  mov     [rsp-38h+arg_0], rbx
0x18001bec5  push    rbp
0x18001bec6  push    rsi
0x18001bec7  push    rdi
0x18001bec8  push    r12
0x18001beca  push    r13
0x18001becc  push    r14
0x18001bece  push    r15
0x18001bed0  mov     rbp, rsp
0x18001bed3  sub     rsp, 30h
0x18001bed7  xor     edi, edi
0x18001bed9  xor     esi, esi
0x18001bedb  mov     [rbp+arg_18], rdi
0x18001bedf  mov     r13, rdx
0x18001bee2  mov     [rbp+pszPath], rsi
0x18001bee6  mov     r12, rcx
0x18001bee9  call    cs:__imp_PathIsUNCW
0x18001bef0  nop     dword ptr [rax+rax+00h]
0x18001bef5  test    eax, eax
0x18001bef7  jnz     loc_18001C228
0x18001befd  mov     rcx, r12; pszPath
0x18001bf00  call    cs:__imp_PathGetDriveNumberW
0x18001bf07  nop     dword ptr [rax+rax+00h]
0x18001bf0c  or      r15, 0FFFFFFFFFFFFFFFFh
0x18001bf10  cmp     eax, r15d
0x18001bf13  jnz     loc_18001C228
0x18001bf19  mov     rcx, r12; pszPath
0x18001bf1c  call    cs:__imp_PathIsRelativeW
0x18001bf23  nop     dword ptr [rax+rax+00h]
0x18001bf28  xor     edx, edx; lpBuffer
0x18001bf2a  xor     ecx, ecx; nBufferLength
0x18001bf2c  xor     ebx, ebx
0x18001bf2e  test    eax, eax
0x18001bf30  jnz     loc_18001C0E9
0x18001bf36  call    cs:__imp_GetCurrentDirectoryW
0x18001bf3d  nop     dword ptr [rax+rax+00h]
0x18001bf42  mov     r14d, eax
0x18001bf45  test    eax, eax
0x18001bf47  jnz     short loc_18001BF83
0x18001bf49  call    cs:__imp_GetLastError
0x18001bf50  nop     dword ptr [rax+rax+00h]
0x18001bf55  mov     ecx, eax
0x18001bf57  mov     r9d, 0AE0h
0x18001bf5d  call    ElValidateWin32_8
0x18001bf62  mov     ebx, eax
0x18001bf64  test    eax, eax
0x18001bf66  jle     short loc_18001BF71
0x18001bf68  movzx   ebx, ax
0x18001bf6b  or      ebx, 80070000h
0x18001bf71  test    ebx, ebx
0x18001bf73  js      loc_18001C00C
0x18001bf79  mov     ebx, 80004005h
0x18001bf7e  jmp     loc_18001C00C
0x18001bf83  mov     eax, 2
0x18001bf88  mul     r14
0x18001bf8b  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001bf92  cmovo   rax, r15
0x18001bf96  mov     rcx, rax; unsigned __int64
0x18001bf99  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18001bf9e  mov     r15, rax
0x18001bfa1  test    rax, rax
0x18001bfa4  jnz     short loc_18001BFAD
0x18001bfa6  mov     ebx, 8007000Eh
0x18001bfab  jmp     short loc_18001C01A
0x18001bfad  mov     rdx, r15; lpBuffer
0x18001bfb0  mov     ecx, r14d; nBufferLength
0x18001bfb3  call    cs:__imp_GetCurrentDirectoryW
0x18001bfba  nop     dword ptr [rax+rax+00h]
0x18001bfbf  test    eax, eax
0x18001bfc1  jnz     short loc_18001BFF6
0x18001bfc3  call    cs:__imp_GetLastError
0x18001bfca  nop     dword ptr [rax+rax+00h]
0x18001bfcf  mov     ecx, eax
0x18001bfd1  mov     r9d, 0AF2h
0x18001bfd7  call    ElValidateWin32_8
0x18001bfdc  mov     ebx, eax
0x18001bfde  test    eax, eax
0x18001bfe0  jle     short loc_18001BFEB
0x18001bfe2  movzx   ebx, ax
0x18001bfe5  or      ebx, 80070000h
0x18001bfeb  test    ebx, ebx
0x18001bfed  js      short loc_18001C000
0x18001bfef  mov     ebx, 80004005h
0x18001bff4  jmp     short loc_18001C000
0x18001bff6  cmp     eax, r14d
0x18001bff9  jbe     short loc_18001C01F
0x18001bffb  mov     ebx, 80070057h
0x18001c000  mov     rcx, r15; lpMem
0x18001c003  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001c008  test    ebx, ebx
0x18001c00a  jns     short loc_18001C026
0x18001c00c  mov     eax, ebx
0x18001c00e  and     eax, 1FFF0000h
0x18001c013  cmp     eax, 70000h
0x18001c018  jnz     short loc_18001C026
0x18001c01a  movzx   ebx, bx
0x18001c01d  jmp     short loc_18001C026
0x18001c01f  mov     rdi, r15
0x18001c022  mov     [rbp+arg_18], r15
0x18001c026  mov     r9d, 0F31h
0x18001c02c  mov     ecx, ebx
0x18001c02e  call    ElValidateWin32_8
0x18001c033  test    eax, eax
0x18001c035  jnz     loc_18001C242
0x18001c03b  mov     rcx, rdi; pszPath
0x18001c03e  call    cs:__imp_PathGetDriveNumberW
0x18001c045  nop     dword ptr [rax+rax+00h]
0x18001c04a  mov     ebx, eax
0x18001c04c  cmp     eax, 0FFFFFFFFh
0x18001c04f  jnz     short loc_18001C05B
0x18001c051  mov     ebx, 0A1h
0x18001c056  jmp     loc_18001C242
0x18001c05b  test    rdi, rdi
0x18001c05e  jz      short loc_18001C06C
0x18001c060  mov     rcx, rdi; lpMem
0x18001c063  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001c068  and     [rbp+arg_18], rsi
0x18001c06c  lea     r9d, [rbx+41h]
0x18001c070  mov     edx, 4; unsigned __int64
0x18001c075  lea     r8, aC; "%c:\\"
0x18001c07c  lea     rcx, [rbp+arg_18]; unsigned __int16 **
0x18001c080  call    ?FormatString@@YAKPEAPEAG_KPEBGZZ; FormatString(ushort * *,unsigned __int64,ushort const *,...)
0x18001c085  mov     r9d, 0F43h
0x18001c08b  mov     ecx, eax
0x18001c08d  mov     ebx, eax
0x18001c08f  call    ElValidateWin32_8
0x18001c094  mov     rdi, [rbp+arg_18]
0x18001c098  test    eax, eax
0x18001c09a  jnz     loc_18001C242
0x18001c0a0  lea     r8, [rbp+pszPath]
0x18001c0a4  mov     rdx, r12
0x18001c0a7  mov     rcx, rdi
0x18001c0aa  call    ConcatenatePaths
0x18001c0af  mov     r9d, 0F4Ch
0x18001c0b5  mov     ecx, eax
0x18001c0b7  mov     ebx, eax
0x18001c0b9  call    ElValidateWin32_8
0x18001c0be  test    eax, eax
0x18001c0c0  jnz     loc_18001C222
0x18001c0c6  mov     rsi, [rbp+pszPath]
0x18001c0ca  mov     rdx, r13
0x18001c0cd  mov     rcx, rsi; pszPath
0x18001c0d0  call    WdsCanonicalizePath
0x18001c0d5  mov     r9d, 0F52h
0x18001c0db  mov     ecx, eax
0x18001c0dd  mov     ebx, eax
0x18001c0df  call    ElValidateWin32_8
0x18001c0e4  jmp     loc_18001C242
0x18001c0e9  call    cs:__imp_GetCurrentDirectoryW
0x18001c0f0  nop     dword ptr [rax+rax+00h]
0x18001c0f5  mov     r14d, eax
0x18001c0f8  test    eax, eax
0x18001c0fa  jnz     short loc_18001C136
0x18001c0fc  call    cs:__imp_GetLastError
0x18001c103  nop     dword ptr [rax+rax+00h]
0x18001c108  mov     ecx, eax
0x18001c10a  mov     r9d, 0AE0h
0x18001c110  call    ElValidateWin32_8
0x18001c115  mov     ebx, eax
0x18001c117  test    eax, eax
0x18001c119  jle     short loc_18001C124
0x18001c11b  movzx   ebx, ax
0x18001c11e  or      ebx, 80070000h
0x18001c124  test    ebx, ebx
0x18001c126  js      loc_18001C1BF
0x18001c12c  mov     ebx, 80004005h
0x18001c131  jmp     loc_18001C1BF
0x18001c136  mov     eax, 2
0x18001c13b  mul     r14
0x18001c13e  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001c145  cmovo   rax, r15
0x18001c149  mov     rcx, rax; unsigned __int64
0x18001c14c  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18001c151  mov     r15, rax
0x18001c154  test    rax, rax
0x18001c157  jnz     short loc_18001C160
0x18001c159  mov     ebx, 8007000Eh
0x18001c15e  jmp     short loc_18001C1CD
0x18001c160  mov     rdx, r15; lpBuffer
0x18001c163  mov     ecx, r14d; nBufferLength
0x18001c166  call    cs:__imp_GetCurrentDirectoryW
0x18001c16d  nop     dword ptr [rax+rax+00h]
0x18001c172  test    eax, eax
0x18001c174  jnz     short loc_18001C1A9
0x18001c176  call    cs:__imp_GetLastError
0x18001c17d  nop     dword ptr [rax+rax+00h]
0x18001c182  mov     ecx, eax
0x18001c184  mov     r9d, 0AF2h
0x18001c18a  call    ElValidateWin32_8
0x18001c18f  mov     ebx, eax
0x18001c191  test    eax, eax
0x18001c193  jle     short loc_18001C19E
0x18001c195  movzx   ebx, ax
0x18001c198  or      ebx, 80070000h
0x18001c19e  test    ebx, ebx
0x18001c1a0  js      short loc_18001C1B3
0x18001c1a2  mov     ebx, 80004005h
0x18001c1a7  jmp     short loc_18001C1B3
0x18001c1a9  cmp     eax, r14d
0x18001c1ac  jbe     short loc_18001C1D2
0x18001c1ae  mov     ebx, 80070057h
0x18001c1b3  mov     rcx, r15; lpMem
0x18001c1b6  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001c1bb  test    ebx, ebx
0x18001c1bd  jns     short loc_18001C1D5
0x18001c1bf  mov     eax, ebx
0x18001c1c1  and     eax, 1FFF0000h
0x18001c1c6  cmp     eax, 70000h
0x18001c1cb  jnz     short loc_18001C1D5
0x18001c1cd  movzx   ebx, bx
0x18001c1d0  jmp     short loc_18001C1D5
0x18001c1d2  mov     rdi, r15
0x18001c1d5  mov     r9d, 0F5Eh
0x18001c1db  mov     ecx, ebx
0x18001c1dd  call    ElValidateWin32_8
0x18001c1e2  test    eax, eax
0x18001c1e4  jnz     short loc_18001C242
0x18001c1e6  lea     r8, [rbp+pszPath]
0x18001c1ea  mov     rdx, r12
0x18001c1ed  mov     rcx, rdi
0x18001c1f0  call    ConcatenatePaths
0x18001c1f5  mov     r9d, 0F66h
0x18001c1fb  mov     ecx, eax
0x18001c1fd  mov     ebx, eax
0x18001c1ff  call    ElValidateWin32_8
0x18001c204  test    eax, eax
0x18001c206  jnz     short loc_18001C222
0x18001c208  mov     rsi, [rbp+pszPath]
0x18001c20c  mov     rdx, r13
0x18001c20f  mov     rcx, rsi; pszPath
0x18001c212  call    WdsCanonicalizePath
0x18001c217  mov     r9d, 0F6Ch
0x18001c21d  jmp     loc_18001C0DB
0x18001c222  mov     rsi, [rbp+pszPath]
0x18001c226  jmp     short loc_18001C242
0x18001c228  mov     rdx, r13
0x18001c22b  mov     rcx, r12; pszPath
0x18001c22e  call    WdsCanonicalizePath
0x18001c233  mov     r9d, 0F25h
0x18001c239  mov     ecx, eax
0x18001c23b  mov     ebx, eax
0x18001c23d  call    ElValidateWin32_8
0x18001c242  test    rdi, rdi
0x18001c245  jz      short loc_18001C24F
0x18001c247  mov     rcx, rdi; lpMem
0x18001c24a  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001c24f  test    rsi, rsi
0x18001c252  jz      short loc_18001C25C
0x18001c254  mov     rcx, rsi; lpMem
0x18001c257  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001c25c  mov     eax, ebx
0x18001c25e  mov     rbx, [rsp+30h+arg_0]
0x18001c263  add     rsp, 30h
0x18001c267  pop     r15
0x18001c269  pop     r14
0x18001c26b  pop     r13
0x18001c26d  pop     r12
0x18001c26f  pop     rdi
0x18001c270  pop     rsi
0x18001c271  pop     rbp
0x18001c272  retn
```
