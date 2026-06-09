# EnsureDirectory

- ea: `0x18002f294`
- end: `0x18002f57d`
- name: `EnsureDirectory`
- size: `745`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, reparse_path, broker_com_uri`

## callers

- `0x180064cec`

## callees

- `0x180020740`
- `0x180020cdc`
- `0x180021a58`
- `0x18002f294`
- `0x180036f50`
- `0x18006239c`
- `0x180062684`
- `0x180069740`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f3e6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f40a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f3e6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f40a`
- `api-ms-win-core-path-l1-1-0!PathCchSkipRoot` at `0x18002f2ff`
- `api-ms-win-core-path-l1-1-0!PathCchSkipRoot` at `0x18002f2ff`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18002f400`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18002f400`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18002f3db`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18002f3db`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall EnsureDirectory(__int64 a1, const WCHAR *a2, __int64 a3, _OWORD *a4, char a5)
{
  signed __int64 v7; // rcx
  bool v8; // sf
  PCWSTR v9; // rax
  char v10; // si
  __int64 v11; // r10
  WCHAR v12; // cx
  DWORD FileAttributesW; // eax
  signed int LastError; // edi
  signed int v15; // edi
  __int64 v16; // rax
  __int64 v17; // r8
  __int64 v18; // rdx
  __int64 v19; // rax
  __int64 v20; // r8
  const WCHAR *v22; // [rsp+20h] [rbp-41h] BYREF
  __int64 v23; // [rsp+28h] [rbp-39h]
  PCWSTR *p_pszPath; // [rsp+48h] [rbp-19h] BYREF
  __int64 *v25; // [rsp+50h] [rbp-11h]
  WCHAR *v26; // [rsp+58h] [rbp-9h]
  char v27; // [rsp+60h] [rbp-1h]
  PCWSTR pszPath; // [rsp+68h] [rbp+7h] BYREF
  __int64 v29; // [rsp+70h] [rbp+Fh] BYREF
  PCWSTR ppszRootEnd[2]; // [rsp+80h] [rbp+1Fh] BYREF
  WCHAR v31; // [rsp+90h] [rbp+2Fh] BYREF

  ppszRootEnd[0] = (PCWSTR)a1;
  pszPath = a2;
  *(_OWORD *)ppszRootEnd = *a4;
  v22 = a2;
  v23 = a3;
  common_path(&p_pszPath, &v22, ppszRootEnd);
  v7 = (signed __int64)v25;
  v29 = (__int64)v25;
  if ( v25 )
  {
    v9 = pszPath;
  }
  else
  {
    ppszRootEnd[0] = 0;
    v8 = PathCchSkipRoot(pszPath, ppszRootEnd) < 0;
    v9 = pszPath;
    if ( v8 )
    {
      v7 = v29;
    }
    else
    {
      v7 = ppszRootEnd[0] - pszPath;
      v29 = v7;
    }
  }
  if ( v9[v7] == 47 || v9[v7] == 92 )
    v29 = ++v7;
  ppszRootEnd[0] = &v9[v7];
  ppszRootEnd[1] = (PCWSTR)(a3 - v7);
  v10 = 0;
  while ( 1 )
  {
    do
    {
      if ( !ppszRootEnd[1] )
      {
        *(_OWORD *)a1 = 0;
        *(_OWORD *)(a1 + 16) = 0;
        *(_DWORD *)a1 = 0;
        *(_BYTE *)(a1 + 4) = 0;
        *(_OWORD *)(a1 + 8) = 0;
        *(_QWORD *)(a1 + 24) = 0;
        *(_QWORD *)(a1 + 32) = 7;
        *(_WORD *)(a1 + 8) = 0;
        return a1;
      }
      next_path_component(&v22, ppszRootEnd);
      v11 = v23;
    }
    while ( !v23 );
    v29 = ((__int64)v22 + 2 * v23 - (__int64)pszPath) >> 1;
    v12 = pszPath[v29];
    pszPath[v29] = 0;
    v31 = v12;
    p_pszPath = &pszPath;
    v25 = &v29;
    v26 = &v31;
    v27 = 1;
    if ( (unsigned __int8)std::_Traits_equal<std::char_traits<unsigned short>>(v22, v11, L"..", 2) )
    {
      v16 = std::wstring::wstring(&v22, pszPath, v29);
      LOBYTE(v17) = 7;
      v18 = 2147942561LL;
      goto LABEL_25;
    }
    if ( v10 )
      goto LABEL_17;
    FileAttributesW = GetFileAttributesW(pszPath);
    if ( FileAttributesW == -1 )
      break;
    if ( (FileAttributesW & 0x10) == 0 )
    {
      v16 = std::wstring::wstring(&v22, pszPath, v29);
      LOBYTE(v17) = 5;
      v18 = 2150039563LL;
      goto LABEL_25;
    }
    if ( (a5 & 2) == 0 && (FileAttributesW & 0x400) != 0 && is_symlink(pszPath) )
    {
      v16 = std::wstring::wstring(&v22, pszPath, v29);
      LOBYTE(v17) = 6;
      v18 = 2147943081LL;
LABEL_25:
      ExtractResult::ExtractResult(a1, v18, v17, v16);
      pszPath[v29] = v31;
      return a1;
    }
LABEL_19:
    pszPath[v29] = v31;
  }
  LastError = GetLastError();
  if ( LastError == 2 )
  {
    v10 = 1;
LABEL_17:
    if ( !CreateDirectoryW(pszPath, 0) )
    {
      v15 = GetLastError();
      if ( v15 != 183 )
      {
        v16 = std::wstring::wstring(&v22, pszPath, v29);
        if ( v15 > 0 )
          v15 = (unsigned __int16)v15 | 0x80070000;
        LOBYTE(v17) = 2;
        v18 = (unsigned int)v15;
        goto LABEL_25;
      }
    }
    goto LABEL_19;
  }
  v19 = std::wstring::wstring(&v22, pszPath, v29);
  if ( LastError > 0 )
    LastError = (unsigned __int16)LastError | 0x80070000;
  LOBYTE(v20) = 2;
  ExtractResult::ExtractResult(a1, (unsigned int)LastError, v20, v19);
  pszPath[v29] = v31;
  return a1;
}

```

## disassembly

```asm
0x18002f294  mov     [rsp-8+arg_10], rbx
0x18002f299  push    rbp
0x18002f29a  push    rsi
0x18002f29b  push    rdi
0x18002f29c  lea     rbp, [rsp-3Fh]
0x18002f2a1  sub     rsp, 0A0h
0x18002f2a8  mov     rax, cs:__security_cookie
0x18002f2af  xor     rax, rsp
0x18002f2b2  mov     [rbp+4Fh+var_18], rax
0x18002f2b6  mov     rdi, r8
0x18002f2b9  mov     rbx, rcx
0x18002f2bc  mov     [rbp+4Fh+ppszRootEnd], rcx
0x18002f2c0  mov     [rbp+4Fh+pszPath], rdx
0x18002f2c4  movaps  xmm0, xmmword ptr [r9]
0x18002f2c8  movdqa  xmmword ptr [rbp+4Fh+ppszRootEnd], xmm0
0x18002f2cd  mov     [rbp+4Fh+var_90], rdx
0x18002f2d1  mov     [rbp+4Fh+var_88], r8
0x18002f2d5  lea     r8, [rbp+4Fh+ppszRootEnd]
0x18002f2d9  lea     rdx, [rbp+4Fh+var_90]
0x18002f2dd  lea     rcx, [rbp+4Fh+var_68]
0x18002f2e1  call    ?common_path@@YA?AV?$basic_string_view@GU?$char_traits@G@std@@@std@@V12@0@Z; common_path(std::basic_string_view<ushort>,std::basic_string_view<ushort>)
0x18002f2e6  mov     rcx, [rbp+4Fh+var_60]
0x18002f2ea  mov     [rbp+4Fh+var_40], rcx
0x18002f2ee  test    rcx, rcx
0x18002f2f1  jnz     short loc_18002F323
0x18002f2f3  mov     [rbp+4Fh+ppszRootEnd], rcx
0x18002f2f7  lea     rdx, [rbp+4Fh+ppszRootEnd]; ppszRootEnd
0x18002f2fb  mov     rcx, [rbp+4Fh+pszPath]; pszPath
0x18002f2ff  call    cs:__imp_PathCchSkipRoot
0x18002f305  test    eax, eax
0x18002f307  mov     rax, [rbp+4Fh+pszPath]
0x18002f30b  js      short loc_18002F31D
0x18002f30d  mov     rcx, [rbp+4Fh+ppszRootEnd]
0x18002f311  sub     rcx, rax
0x18002f314  sar     rcx, 1
0x18002f317  mov     [rbp+4Fh+var_40], rcx
0x18002f31b  jmp     short loc_18002F327
0x18002f31d  mov     rcx, [rbp+4Fh+var_40]
0x18002f321  jmp     short loc_18002F327
0x18002f323  mov     rax, [rbp+4Fh+pszPath]
0x18002f327  cmp     word ptr [rax+rcx*2], 2Fh ; '/'
0x18002f32c  jz      short loc_18002F335
0x18002f32e  cmp     word ptr [rax+rcx*2], 5Ch ; '\'
0x18002f333  jnz     short loc_18002F33C
0x18002f335  inc     rcx
0x18002f338  mov     [rbp+4Fh+var_40], rcx
0x18002f33c  lea     rax, [rax+rcx*2]
0x18002f340  mov     [rbp+4Fh+ppszRootEnd], rax
0x18002f344  sub     rdi, rcx
0x18002f347  mov     [rbp+4Fh+ppszRootEnd+8], rdi
0x18002f34b  xor     sil, sil
0x18002f34e  cmp     [rbp+4Fh+ppszRootEnd+8], 0
0x18002f353  jz      loc_18002F536
0x18002f359  lea     rdx, [rbp+4Fh+ppszRootEnd]
0x18002f35d  lea     rcx, [rbp+4Fh+var_90]
0x18002f361  call    ?next_path_component@@YA?AV?$basic_string_view@GU?$char_traits@G@std@@@std@@AEAV12@@Z; next_path_component(std::basic_string_view<ushort> &)
0x18002f366  mov     r10, [rbp+4Fh+var_88]
0x18002f36a  test    r10, r10
0x18002f36d  jz      short loc_18002F34E
0x18002f36f  lea     r8, [r10+r10]
0x18002f373  mov     rdx, [rbp+4Fh+pszPath]
0x18002f377  sub     r8, rdx
0x18002f37a  add     r8, [rbp+4Fh+var_90]
0x18002f37e  sar     r8, 1
0x18002f381  mov     [rbp+4Fh+var_40], r8
0x18002f385  movzx   ecx, word ptr [rdx+r8*2]
0x18002f38a  xor     eax, eax
0x18002f38c  mov     [rdx+r8*2], ax
0x18002f391  mov     [rbp+4Fh+var_20], cx
0x18002f395  lea     rax, [rbp+4Fh+pszPath]
0x18002f399  mov     [rbp+4Fh+var_68], rax
0x18002f39d  lea     rax, [rbp+4Fh+var_40]
0x18002f3a1  mov     [rbp+4Fh+var_60], rax
0x18002f3a5  lea     rax, [rbp+4Fh+var_20]
0x18002f3a9  mov     [rbp+4Fh+var_58], rax
0x18002f3ad  mov     [rbp+4Fh+var_50], 1
0x18002f3b1  mov     r9d, 2
0x18002f3b7  lea     r8, PathName; ".."
0x18002f3be  mov     rdx, r10
0x18002f3c1  mov     rcx, [rbp+4Fh+var_90]
0x18002f3c5  call    ??$_Traits_equal@U?$char_traits@G@std@@@std@@YA_NQEBG_K01@Z; std::_Traits_equal<std::char_traits<ushort>>(ushort const * const,unsigned __int64,ushort const * const,unsigned __int64)
0x18002f3ca  test    al, al
0x18002f3cc  jnz     loc_18002F518
0x18002f3d2  test    sil, sil
0x18002f3d5  jnz     short loc_18002F3FA
0x18002f3d7  mov     rcx, [rbp+4Fh+pszPath]; lpFileName
0x18002f3db  call    cs:__imp_GetFileAttributesW
0x18002f3e1  cmp     eax, 0FFFFFFFFh
0x18002f3e4  jnz     short loc_18002F432
0x18002f3e6  call    cs:__imp_GetLastError
0x18002f3ec  mov     edi, eax
0x18002f3ee  cmp     eax, 2
0x18002f3f1  jnz     loc_18002F48D
0x18002f3f7  mov     sil, 1
0x18002f3fa  xor     edx, edx; lpSecurityAttributes
0x18002f3fc  mov     rcx, [rbp+4Fh+pszPath]; lpPathName
0x18002f400  call    cs:__imp_CreateDirectoryW
0x18002f406  test    eax, eax
0x18002f408  jnz     short loc_18002F41D
0x18002f40a  call    cs:__imp_GetLastError
0x18002f410  mov     edi, eax
0x18002f412  cmp     eax, 0B7h
0x18002f417  jnz     loc_18002F4F0
0x18002f41d  mov     rdx, [rbp+4Fh+var_40]
0x18002f421  movzx   ecx, [rbp+4Fh+var_20]
0x18002f425  mov     rax, [rbp+4Fh+pszPath]
0x18002f429  mov     [rax+rdx*2], cx
0x18002f42d  jmp     loc_18002F34E
0x18002f432  test    al, 10h
0x18002f434  jz      loc_18002F4D2
0x18002f43a  test    [rbp+4Fh+arg_20], 2
0x18002f43e  jnz     short loc_18002F41D
0x18002f440  bt      eax, 0Ah
0x18002f444  jnb     short loc_18002F41D
0x18002f446  mov     rcx, [rbp+4Fh+pszPath]; lpFileName
0x18002f44a  call    ?is_symlink@@YA_NPEBG@Z; is_symlink(ushort const *)
0x18002f44f  test    al, al
0x18002f451  jz      short loc_18002F41D
0x18002f453  mov     r8, [rbp+4Fh+var_40]
0x18002f457  mov     rdx, [rbp+4Fh+pszPath]
0x18002f45b  lea     rcx, [rbp+4Fh+var_90]
0x18002f45f  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG_K@Z; std::wstring::wstring(ushort const * const,unsigned __int64)
0x18002f464  mov     r8b, 6
0x18002f467  mov     edx, 800702A9h
0x18002f46c  mov     r9, rax
0x18002f46f  mov     rcx, rbx
0x18002f472  call    ??0ExtractResult@@QEAA@JW4ExtractFailureReason@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; ExtractResult::ExtractResult(long,ExtractFailureReason,std::wstring)
0x18002f477  nop
0x18002f478  mov     rdx, [rbp+4Fh+var_40]
0x18002f47c  movzx   ecx, [rbp+4Fh+var_20]
0x18002f480  mov     rax, [rbp+4Fh+pszPath]
0x18002f484  mov     [rax+rdx*2], cx
0x18002f488  jmp     loc_18002F55B
0x18002f48d  mov     r8, [rbp+4Fh+var_40]
0x18002f491  mov     rdx, [rbp+4Fh+pszPath]
0x18002f495  lea     rcx, [rbp+4Fh+var_90]
0x18002f499  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG_K@Z; std::wstring::wstring(ushort const * const,unsigned __int64)
0x18002f49e  test    edi, edi
0x18002f4a0  jle     short loc_18002F4AB
0x18002f4a2  movzx   edi, di
0x18002f4a5  or      edi, 80070000h
0x18002f4ab  mov     r9, rax
0x18002f4ae  mov     r8b, 2
0x18002f4b1  mov     edx, edi
0x18002f4b3  mov     rcx, rbx
0x18002f4b6  call    ??0ExtractResult@@QEAA@JW4ExtractFailureReason@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; ExtractResult::ExtractResult(long,ExtractFailureReason,std::wstring)
0x18002f4bb  nop
0x18002f4bc  mov     r8, [rbp+4Fh+var_40]
0x18002f4c0  movzx   edx, [rbp+4Fh+var_20]
0x18002f4c4  mov     rcx, [rbp+4Fh+pszPath]
0x18002f4c8  mov     [rcx+r8*2], dx
0x18002f4cd  jmp     loc_18002F55B
0x18002f4d2  mov     r8, [rbp+4Fh+var_40]
0x18002f4d6  mov     rdx, [rbp+4Fh+pszPath]
0x18002f4da  lea     rcx, [rbp+4Fh+var_90]
0x18002f4de  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG_K@Z; std::wstring::wstring(ushort const * const,unsigned __int64)
0x18002f4e3  mov     r8b, 5
0x18002f4e6  mov     edx, 8027000Bh
0x18002f4eb  jmp     loc_18002F46C
0x18002f4f0  mov     r8, [rbp+4Fh+var_40]
0x18002f4f4  mov     rdx, [rbp+4Fh+pszPath]
0x18002f4f8  lea     rcx, [rbp+4Fh+var_90]
0x18002f4fc  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG_K@Z; std::wstring::wstring(ushort const * const,unsigned __int64)
0x18002f501  test    edi, edi
0x18002f503  jle     short loc_18002F50E
0x18002f505  movzx   edi, di
0x18002f508  or      edi, 80070000h
0x18002f50e  mov     r8b, 2
0x18002f511  mov     edx, edi
0x18002f513  jmp     loc_18002F46C
0x18002f518  mov     r8, [rbp+4Fh+var_40]
0x18002f51c  mov     rdx, [rbp+4Fh+pszPath]
0x18002f520  lea     rcx, [rbp+4Fh+var_90]
0x18002f524  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG_K@Z; std::wstring::wstring(ushort const * const,unsigned __int64)
0x18002f529  mov     r8b, 7
0x18002f52c  mov     edx, 800700A1h
0x18002f531  jmp     loc_18002F46C
0x18002f536  xorps   xmm0, xmm0
0x18002f539  xor     eax, eax
0x18002f53b  movups  xmmword ptr [rbx], xmm0
0x18002f53e  movups  xmmword ptr [rbx+10h], xmm0
0x18002f542  mov     [rbx], eax
0x18002f544  mov     [rbx+4], al
0x18002f547  movups  xmmword ptr [rbx+8], xmm0
0x18002f54b  mov     [rbx+18h], rax
0x18002f54f  mov     qword ptr [rbx+20h], 7
0x18002f557  mov     [rbx+8], ax
0x18002f55b  mov     rax, rbx
0x18002f55e  mov     rcx, [rbp+4Fh+var_18]
0x18002f562  xor     rcx, rsp; StackCookie
0x18002f565  call    __security_check_cookie
0x18002f56a  mov     rbx, [rsp+0B0h+arg_10]
0x18002f572  add     rsp, 0A0h
0x18002f579  pop     rdi
0x18002f57a  pop     rsi
0x18002f57b  pop     rbp
0x18002f57c  retn
```
