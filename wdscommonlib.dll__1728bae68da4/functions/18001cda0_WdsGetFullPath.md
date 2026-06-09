# WdsGetFullPath

- ea: `0x18001cda0`
- end: `0x18001d177`
- name: `WdsGetFullPath`
- size: `983`
- prototype: `__int64 __fastcall(LPCWSTR pszPath)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x18001d640`

## callees

- `0x18000214c`
- `0x180015a00`
- `0x18001a880`
- `0x18001b0cc`
- `0x18001b800`
- `0x18001cda0`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18001cee3`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001cf4a`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001d0a4`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001d13f`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001d153`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001cee3`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001cf4a`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001d0a4`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001d13f`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001d153`
- `KERNEL32!GetCurrentDirectoryW` at `0x18001ce16`
- `KERNEL32!GetCurrentDirectoryW` at `0x18001ce93`
- `KERNEL32!GetCurrentDirectoryW` at `0x18001cfd7`
- `KERNEL32!GetCurrentDirectoryW` at `0x18001d054`
- `KERNEL32!GetCurrentDirectoryW` at `0x18001ce16`
- `KERNEL32!GetCurrentDirectoryW` at `0x18001ce93`
- `KERNEL32!GetCurrentDirectoryW` at `0x18001cfd7`
- `KERNEL32!GetCurrentDirectoryW` at `0x18001d054`
- `KERNEL32!GetLastError` at `0x18001ce29`
- `KERNEL32!GetLastError` at `0x18001cea3`
- `KERNEL32!GetLastError` at `0x18001cfea`
- `KERNEL32!GetLastError` at `0x18001d064`
- `KERNEL32!GetLastError` at `0x18001ce29`
- `KERNEL32!GetLastError` at `0x18001cea3`
- `KERNEL32!GetLastError` at `0x18001cfea`
- `KERNEL32!GetLastError` at `0x18001d064`
- `SHLWAPI!PathIsRelativeW` at `0x18001cdfc`
- `SHLWAPI!PathIsRelativeW` at `0x18001cdfc`
- `SHLWAPI!PathGetDriveNumberW` at `0x18001cde0`
- `SHLWAPI!PathGetDriveNumberW` at `0x18001cf25`
- `SHLWAPI!PathGetDriveNumberW` at `0x18001cde0`
- `SHLWAPI!PathGetDriveNumberW` at `0x18001cf25`
- `SHLWAPI!PathIsUNCW` at `0x18001cdc9`
- `SHLWAPI!PathIsUNCW` at `0x18001cdc9`

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
0x18001cda0  mov     [rsp-38h+arg_0], rbx
0x18001cda5  push    rbp
0x18001cda6  push    rsi
0x18001cda7  push    rdi
0x18001cda8  push    r12
0x18001cdaa  push    r13
0x18001cdac  push    r14
0x18001cdae  push    r15
0x18001cdb0  mov     rbp, rsp
0x18001cdb3  sub     rsp, 30h
0x18001cdb7  xor     edi, edi
0x18001cdb9  xor     esi, esi
0x18001cdbb  mov     [rbp+arg_18], rdi
0x18001cdbf  mov     r13, rdx
0x18001cdc2  mov     [rbp+pszPath], rsi
0x18001cdc6  mov     r12, rcx
0x18001cdc9  call    cs:__imp_PathIsUNCW
0x18001cdd0  nop     dword ptr [rax+rax+00h]
0x18001cdd5  test    eax, eax
0x18001cdd7  jnz     loc_18001D11D
0x18001cddd  mov     rcx, r12; pszPath
0x18001cde0  call    cs:__imp_PathGetDriveNumberW
0x18001cde7  nop     dword ptr [rax+rax+00h]
0x18001cdec  or      r15, 0FFFFFFFFFFFFFFFFh
0x18001cdf0  cmp     eax, r15d
0x18001cdf3  jnz     loc_18001D11D
0x18001cdf9  mov     rcx, r12; pszPath
0x18001cdfc  call    cs:__imp_PathIsRelativeW
0x18001ce03  nop     dword ptr [rax+rax+00h]
0x18001ce08  xor     edx, edx; lpBuffer
0x18001ce0a  xor     ecx, ecx; nBufferLength
0x18001ce0c  xor     ebx, ebx
0x18001ce0e  test    eax, eax
0x18001ce10  jnz     loc_18001CFD7
0x18001ce16  call    cs:__imp_GetCurrentDirectoryW
0x18001ce1d  nop     dword ptr [rax+rax+00h]
0x18001ce22  mov     r14d, eax
0x18001ce25  test    eax, eax
0x18001ce27  jnz     short loc_18001CE63
0x18001ce29  call    cs:__imp_GetLastError
0x18001ce30  nop     dword ptr [rax+rax+00h]
0x18001ce35  mov     ecx, eax
0x18001ce37  mov     r9d, 0AE0h
0x18001ce3d  call    ElValidateWin32_8
0x18001ce42  mov     ebx, eax
0x18001ce44  test    eax, eax
0x18001ce46  jle     short loc_18001CE51
0x18001ce48  movzx   ebx, ax
0x18001ce4b  or      ebx, 80070000h
0x18001ce51  test    ebx, ebx
0x18001ce53  js      loc_18001CEF3
0x18001ce59  mov     ebx, 80004005h
0x18001ce5e  jmp     loc_18001CEF3
0x18001ce63  mov     eax, 2
0x18001ce68  mul     r14
0x18001ce6b  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001ce72  cmovo   rax, r15
0x18001ce76  mov     rcx, rax; unsigned __int64
0x18001ce79  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18001ce7e  mov     r15, rax
0x18001ce81  test    rax, rax
0x18001ce84  jnz     short loc_18001CE8D
0x18001ce86  mov     ebx, 8007000Eh
0x18001ce8b  jmp     short loc_18001CF01
0x18001ce8d  mov     rdx, r15; lpBuffer
0x18001ce90  mov     ecx, r14d; nBufferLength
0x18001ce93  call    cs:__imp_GetCurrentDirectoryW
0x18001ce9a  nop     dword ptr [rax+rax+00h]
0x18001ce9f  test    eax, eax
0x18001cea1  jnz     short loc_18001CED6
0x18001cea3  call    cs:__imp_GetLastError
0x18001ceaa  nop     dword ptr [rax+rax+00h]
0x18001ceaf  mov     ecx, eax
0x18001ceb1  mov     r9d, 0AF2h
0x18001ceb7  call    ElValidateWin32_8
0x18001cebc  mov     ebx, eax
0x18001cebe  test    eax, eax
0x18001cec0  jle     short loc_18001CECB
0x18001cec2  movzx   ebx, ax
0x18001cec5  or      ebx, 80070000h
0x18001cecb  test    ebx, ebx
0x18001cecd  js      short loc_18001CEE0
0x18001cecf  mov     ebx, 80004005h
0x18001ced4  jmp     short loc_18001CEE0
0x18001ced6  cmp     eax, r14d
0x18001ced9  jbe     short loc_18001CF06
0x18001cedb  mov     ebx, 80070057h
0x18001cee0  mov     rcx, r15
0x18001cee3  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18001ceea  nop     dword ptr [rax+rax+00h]
0x18001ceef  test    ebx, ebx
0x18001cef1  jns     short loc_18001CF0D
0x18001cef3  mov     eax, ebx
0x18001cef5  and     eax, 1FFF0000h
0x18001cefa  cmp     eax, 70000h
0x18001ceff  jnz     short loc_18001CF0D
0x18001cf01  movzx   ebx, bx
0x18001cf04  jmp     short loc_18001CF0D
0x18001cf06  mov     rdi, r15
0x18001cf09  mov     [rbp+arg_18], r15
0x18001cf0d  mov     r9d, 0F31h
0x18001cf13  mov     ecx, ebx
0x18001cf15  call    ElValidateWin32_8
0x18001cf1a  test    eax, eax
0x18001cf1c  jnz     loc_18001D137
0x18001cf22  mov     rcx, rdi; pszPath
0x18001cf25  call    cs:__imp_PathGetDriveNumberW
0x18001cf2c  nop     dword ptr [rax+rax+00h]
0x18001cf31  mov     ebx, eax
0x18001cf33  cmp     eax, 0FFFFFFFFh
0x18001cf36  jnz     short loc_18001CF42
0x18001cf38  mov     ebx, 0A1h
0x18001cf3d  jmp     loc_18001D137
0x18001cf42  test    rdi, rdi
0x18001cf45  jz      short loc_18001CF5A
0x18001cf47  mov     rcx, rdi
0x18001cf4a  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18001cf51  nop     dword ptr [rax+rax+00h]
0x18001cf56  and     [rbp+arg_18], rsi
0x18001cf5a  lea     r9d, [rbx+41h]
0x18001cf5e  mov     edx, 4; unsigned __int64
0x18001cf63  lea     r8, aC; "%c:\\"
0x18001cf6a  lea     rcx, [rbp+arg_18]; unsigned __int16 **
0x18001cf6e  call    ?FormatString@@YAKPEAPEAG_KPEBGZZ; FormatString(ushort * *,unsigned __int64,ushort const *,...)
0x18001cf73  mov     r9d, 0F43h
0x18001cf79  mov     ecx, eax
0x18001cf7b  mov     ebx, eax
0x18001cf7d  call    ElValidateWin32_8
0x18001cf82  mov     rdi, [rbp+arg_18]
0x18001cf86  test    eax, eax
0x18001cf88  jnz     loc_18001D137
0x18001cf8e  lea     r8, [rbp+pszPath]
0x18001cf92  mov     rdx, r12
0x18001cf95  mov     rcx, rdi
0x18001cf98  call    ConcatenatePaths
0x18001cf9d  mov     r9d, 0F4Ch
0x18001cfa3  mov     ecx, eax
0x18001cfa5  mov     ebx, eax
0x18001cfa7  call    ElValidateWin32_8
0x18001cfac  test    eax, eax
0x18001cfae  jnz     loc_18001D117
0x18001cfb4  mov     rsi, [rbp+pszPath]
0x18001cfb8  mov     rdx, r13
0x18001cfbb  mov     rcx, rsi; pszPath
0x18001cfbe  call    WdsCanonicalizePath
0x18001cfc3  mov     r9d, 0F52h
0x18001cfc9  mov     ecx, eax
0x18001cfcb  mov     ebx, eax
0x18001cfcd  call    ElValidateWin32_8
0x18001cfd2  jmp     loc_18001D137
0x18001cfd7  call    cs:__imp_GetCurrentDirectoryW
0x18001cfde  nop     dword ptr [rax+rax+00h]
0x18001cfe3  mov     r14d, eax
0x18001cfe6  test    eax, eax
0x18001cfe8  jnz     short loc_18001D024
0x18001cfea  call    cs:__imp_GetLastError
0x18001cff1  nop     dword ptr [rax+rax+00h]
0x18001cff6  mov     ecx, eax
0x18001cff8  mov     r9d, 0AE0h
0x18001cffe  call    ElValidateWin32_8
0x18001d003  mov     ebx, eax
0x18001d005  test    eax, eax
0x18001d007  jle     short loc_18001D012
0x18001d009  movzx   ebx, ax
0x18001d00c  or      ebx, 80070000h
0x18001d012  test    ebx, ebx
0x18001d014  js      loc_18001D0B4
0x18001d01a  mov     ebx, 80004005h
0x18001d01f  jmp     loc_18001D0B4
0x18001d024  mov     eax, 2
0x18001d029  mul     r14
0x18001d02c  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001d033  cmovo   rax, r15
0x18001d037  mov     rcx, rax; unsigned __int64
0x18001d03a  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18001d03f  mov     r15, rax
0x18001d042  test    rax, rax
0x18001d045  jnz     short loc_18001D04E
0x18001d047  mov     ebx, 8007000Eh
0x18001d04c  jmp     short loc_18001D0C2
0x18001d04e  mov     rdx, r15; lpBuffer
0x18001d051  mov     ecx, r14d; nBufferLength
0x18001d054  call    cs:__imp_GetCurrentDirectoryW
0x18001d05b  nop     dword ptr [rax+rax+00h]
0x18001d060  test    eax, eax
0x18001d062  jnz     short loc_18001D097
0x18001d064  call    cs:__imp_GetLastError
0x18001d06b  nop     dword ptr [rax+rax+00h]
0x18001d070  mov     ecx, eax
0x18001d072  mov     r9d, 0AF2h
0x18001d078  call    ElValidateWin32_8
0x18001d07d  mov     ebx, eax
0x18001d07f  test    eax, eax
0x18001d081  jle     short loc_18001D08C
0x18001d083  movzx   ebx, ax
0x18001d086  or      ebx, 80070000h
0x18001d08c  test    ebx, ebx
0x18001d08e  js      short loc_18001D0A1
0x18001d090  mov     ebx, 80004005h
0x18001d095  jmp     short loc_18001D0A1
0x18001d097  cmp     eax, r14d
0x18001d09a  jbe     short loc_18001D0C7
0x18001d09c  mov     ebx, 80070057h
0x18001d0a1  mov     rcx, r15
0x18001d0a4  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18001d0ab  nop     dword ptr [rax+rax+00h]
0x18001d0b0  test    ebx, ebx
0x18001d0b2  jns     short loc_18001D0CA
0x18001d0b4  mov     eax, ebx
0x18001d0b6  and     eax, 1FFF0000h
0x18001d0bb  cmp     eax, 70000h
0x18001d0c0  jnz     short loc_18001D0CA
0x18001d0c2  movzx   ebx, bx
0x18001d0c5  jmp     short loc_18001D0CA
0x18001d0c7  mov     rdi, r15
0x18001d0ca  mov     r9d, 0F5Eh
0x18001d0d0  mov     ecx, ebx
0x18001d0d2  call    ElValidateWin32_8
0x18001d0d7  test    eax, eax
0x18001d0d9  jnz     short loc_18001D137
0x18001d0db  lea     r8, [rbp+pszPath]
0x18001d0df  mov     rdx, r12
0x18001d0e2  mov     rcx, rdi
0x18001d0e5  call    ConcatenatePaths
0x18001d0ea  mov     r9d, 0F66h
0x18001d0f0  mov     ecx, eax
0x18001d0f2  mov     ebx, eax
0x18001d0f4  call    ElValidateWin32_8
0x18001d0f9  test    eax, eax
0x18001d0fb  jnz     short loc_18001D117
0x18001d0fd  mov     rsi, [rbp+pszPath]
0x18001d101  mov     rdx, r13
0x18001d104  mov     rcx, rsi; pszPath
0x18001d107  call    WdsCanonicalizePath
0x18001d10c  mov     r9d, 0F6Ch
0x18001d112  jmp     loc_18001CFC9
0x18001d117  mov     rsi, [rbp+pszPath]
0x18001d11b  jmp     short loc_18001D137
0x18001d11d  mov     rdx, r13
0x18001d120  mov     rcx, r12; pszPath
0x18001d123  call    WdsCanonicalizePath
0x18001d128  mov     r9d, 0F25h
0x18001d12e  mov     ecx, eax
0x18001d130  mov     ebx, eax
0x18001d132  call    ElValidateWin32_8
0x18001d137  test    rdi, rdi
0x18001d13a  jz      short loc_18001D14B
0x18001d13c  mov     rcx, rdi
0x18001d13f  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18001d146  nop     dword ptr [rax+rax+00h]
0x18001d14b  test    rsi, rsi
0x18001d14e  jz      short loc_18001D15F
0x18001d150  mov     rcx, rsi
0x18001d153  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18001d15a  nop     dword ptr [rax+rax+00h]
0x18001d15f  mov     eax, ebx
0x18001d161  mov     rbx, [rsp+30h+arg_0]
0x18001d166  add     rsp, 30h
0x18001d16a  pop     r15
0x18001d16c  pop     r14
0x18001d16e  pop     r13
0x18001d170  pop     r12
0x18001d172  pop     rdi
0x18001d173  pop     rsi
0x18001d174  pop     rbp
0x18001d175  retn
```
