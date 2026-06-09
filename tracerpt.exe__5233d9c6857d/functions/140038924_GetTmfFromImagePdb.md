# GetTmfFromImagePdb

- ea: `0x140038924`
- end: `0x140038c11`
- name: `GetTmfFromImagePdb`
- size: `749`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, loader_planting`

## callers

- `0x140017398`

## callees

- `0x1400020e4`
- `0x140009c78`
- `0x140038408`
- `0x140038570`
- `0x140038850`
- `0x140038924`
- `0x14003b824`
- `0x140040130`

## import_xrefs

- `msvcrt!wcschr` at `0x140038a5c`
- `msvcrt!wcschr` at `0x140038a5c`
- `msvcrt!_wsplitpath_s` at `0x140038af2`
- `msvcrt!_wsplitpath_s` at `0x140038af2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140038ab5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140038ab5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1400389f1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1400389f1`
- `imagehlp!SymSetOptions` at `0x140038a10`
- `imagehlp!SymSetOptions` at `0x140038a10`
- `imagehlp!SymGetSymbolFileW` at `0x140038aa7`
- `imagehlp!SymGetSymbolFileW` at `0x140038b5f`
- `imagehlp!SymGetSymbolFileW` at `0x140038aa7`
- `imagehlp!SymGetSymbolFileW` at `0x140038b5f`
- `dbghelp!SymInitializeW` at `0x140038a05`
- `dbghelp!SymInitializeW` at `0x140038a05`

## string_xrefs

- `0x140038983`: `_NT_SYMBOL_PATH`

## pseudocode

```c
void __fastcall GetTmfFromImagePdb(_WORD *a1, const wchar_t *a2, const wchar_t *a3)
{
  __int64 v6; // r8
  const wchar_t *v7; // rdx
  WCHAR *v8; // rcx
  char *v9; // rcx
  unsigned int v10; // ebx
  HANDLE CurrentProcess; // r13
  __int64 v12; // rdx
  unsigned int i; // r8d
  unsigned int v14; // ecx
  unsigned int j; // esi
  char v16; // r12
  wchar_t *v17; // rax
  wchar_t *v18; // r14
  __int64 v19; // rax
  PCWSTR UserSearchPath; // [rsp+50h] [rbp-B0h] BYREF
  const WCHAR *v21; // [rsp+58h] [rbp-A8h]
  _WORD v22[8]; // [rsp+60h] [rbp-A0h] BYREF
  void *v23[2]; // [rsp+70h] [rbp-90h] BYREF
  char v24; // [rsp+80h] [rbp-80h] BYREF
  wchar_t Ext[256]; // [rsp+90h] [rbp-70h] BYREF
  WCHAR SymbolFile[264]; // [rsp+290h] [rbp+190h] BYREF
  WCHAR DbgFile[264]; // [rsp+4A0h] [rbp+3A0h] BYREF
  WCHAR SymPath[264]; // [rsp+6B0h] [rbp+5B0h] BYREF

  UserSearchPath = v22;
  v22[0] = 0;
  v21 = v22;
  if ( a3 )
  {
    v6 = -1;
    do
      ++v6;
    while ( a3[v6] );
    v7 = a3;
  }
  else
  {
    if ( (int)tlx::assign_environment_variable<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(
                &UserSearchPath,
                L"_NT_SYMBOL_PATH") >= 0 )
      goto LABEL_8;
    v6 = 4;
    v7 = L"srv*";
  }
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
    &UserSearchPath,
    v7,
    v6);
LABEL_8:
  v8 = (WCHAR *)UserSearchPath;
  if ( UserSearchPath != v21 )
  {
    GetTmfSearchPath((__int64)v23, a1);
    v9 = (char *)v23[0];
    if ( v23[0] != v23[1] )
    {
      v10 = 1;
      CurrentProcess = GetCurrentProcess();
      SymInitializeW(CurrentProcess, UserSearchPath, 0);
      SymSetOptions(0x680u);
      v12 = -1;
      do
        ++v12;
      while ( a2[v12] );
      for ( i = 0; i < (unsigned int)v12; v10 = v14 )
      {
        v14 = v10 + 1;
        if ( a2[i] != 59 )
          v14 = v10;
        ++i;
      }
      for ( j = 0; j < v10; ++j )
      {
        v16 = 0;
        v17 = wcschr(a2, 0x3Bu);
        v18 = v17;
        if ( v17 )
        {
          v16 = 1;
          *v17 = 0;
        }
        if ( SymGetSymbolFileW(CurrentProcess, 0, a2, 2u, SymbolFile, 0x104u, DbgFile, 0x104u)
          || GetLastError() == 2
          && (_wsplitpath_s(a2, 0, 0, 0, 0, 0, 0, Ext, 0x100u),
              Ext[0] = 92,
              StringCchPrintfW(SymPath, 0x104u, L"%s%s", a3, Ext),
              SymGetSymbolFileW(CurrentProcess, SymPath, a2, 2u, SymbolFile, 0x104u, DbgFile, 0x104u)) )
        {
          BinplaceWppFmtW(SymbolFile, v23[0]);
        }
        v19 = -1;
        do
          ++v19;
        while ( a2[v19] );
        a2 += v19 + 1;
        if ( v16 )
          *v18 = 59;
      }
      v9 = (char *)v23[0];
    }
    if ( v9 != &v24 )
      operator delete(v9, (const struct std::nothrow_t *)&std::nothrow);
    v8 = (WCHAR *)UserSearchPath;
  }
  if ( v8 != v22 )
    operator delete(v8, (const struct std::nothrow_t *)&std::nothrow);
}

```

## disassembly

```asm
0x140038924  mov     [rsp-8+arg_18], rbx
0x140038929  push    rbp
0x14003892a  push    rsi
0x14003892b  push    rdi
0x14003892c  push    r12
0x14003892e  push    r13
0x140038930  push    r14
0x140038932  push    r15
0x140038934  lea     rbp, [rsp-7D0h]
0x14003893c  sub     rsp, 8D0h
0x140038943  mov     rax, cs:__security_cookie
0x14003894a  xor     rax, rsp
0x14003894d  mov     [rbp+800h+var_40], rax
0x140038954  lea     rax, [rsp+900h+var_8A0]
0x140038959  xor     r14d, r14d
0x14003895c  mov     [rsp+900h+UserSearchPath], rax
0x140038961  or      rsi, 0FFFFFFFFFFFFFFFFh
0x140038965  mov     [rsp+900h+var_8A0], r14w
0x14003896b  lea     rax, [rsp+900h+var_8A0]
0x140038970  mov     [rsp+900h+var_8A8], rax
0x140038975  mov     r15, r8
0x140038978  mov     rdi, rdx
0x14003897b  mov     rbx, rcx
0x14003897e  test    r8, r8
0x140038981  jnz     short loc_1400389A5
0x140038983  lea     rdx, aNtSymbolPath; "_NT_SYMBOL_PATH"
0x14003898a  lea     rcx, [rsp+900h+UserSearchPath]
0x14003898f  call    ??$assign_environment_variable@GU?$char_traits@G@utl@@V?$allocator@G@2@@tlx@@YAJAEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@PEBG@Z; tlx::assign_environment_variable<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &,ushort const *)
0x140038994  test    eax, eax
0x140038996  jns     short loc_1400389BF
0x140038998  lea     r8d, [r15+4]
0x14003899c  lea     rdx, aSrv; "srv*"
0x1400389a3  jmp     short loc_1400389B5
0x1400389a5  mov     r8, rsi
0x1400389a8  inc     r8
0x1400389ab  cmp     [r15+r8*2], r14w
0x1400389b0  jnz     short loc_1400389A8
0x1400389b2  mov     rdx, r15
0x1400389b5  lea     rcx, [rsp+900h+UserSearchPath]
0x1400389ba  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *,unsigned __int64)
0x1400389bf  mov     rcx, [rsp+900h+UserSearchPath]
0x1400389c4  cmp     rcx, [rsp+900h+var_8A8]
0x1400389c9  jz      loc_140038BD1
0x1400389cf  mov     rdx, rbx
0x1400389d2  lea     rcx, [rsp+900h+var_890]
0x1400389d7  call    GetTmfSearchPath
0x1400389dc  mov     rcx, [rsp+900h+var_890]
0x1400389e1  cmp     rcx, [rsp+900h+var_888]
0x1400389e6  jz      loc_140038BB7
0x1400389ec  mov     ebx, 1
0x1400389f1  call    cs:__imp_GetCurrentProcess
0x1400389f7  mov     rdx, [rsp+900h+UserSearchPath]; UserSearchPath
0x1400389fc  xor     r8d, r8d; fInvadeProcess
0x1400389ff  mov     rcx, rax; hProcess
0x140038a02  mov     r13, rax
0x140038a05  call    cs:__imp_SymInitializeW
0x140038a0b  mov     ecx, 680h; SymOptions
0x140038a10  call    cs:__imp_SymSetOptions
0x140038a16  mov     rdx, rsi
0x140038a19  inc     rdx
0x140038a1c  cmp     [rdi+rdx*2], r14w
0x140038a21  jnz     short loc_140038A19
0x140038a23  mov     r8d, r14d
0x140038a26  mov     r9d, 3Bh ; ';'
0x140038a2c  test    edx, edx
0x140038a2e  jz      short loc_140038A48
0x140038a30  mov     eax, r8d
0x140038a33  lea     ecx, [rbx+1]
0x140038a36  cmp     [rdi+rax*2], r9w
0x140038a3b  cmovnz  ecx, ebx
0x140038a3e  inc     r8d
0x140038a41  mov     ebx, ecx
0x140038a43  cmp     r8d, edx
0x140038a46  jb      short loc_140038A30
0x140038a48  mov     esi, r14d
0x140038a4b  test    ebx, ebx
0x140038a4d  jz      loc_140038BB2
0x140038a53  mov     edx, r9d; Ch
0x140038a56  mov     rcx, rdi; Str
0x140038a59  mov     r12b, r14b
0x140038a5c  call    cs:__imp_wcschr
0x140038a62  mov     r14, rax
0x140038a65  test    rax, rax
0x140038a68  jz      short loc_140038A72
0x140038a6a  xor     ecx, ecx
0x140038a6c  mov     r12b, 1
0x140038a6f  mov     [rax], cx
0x140038a72  mov     ecx, 104h
0x140038a77  lea     rax, [rbp+800h+var_460]
0x140038a7e  mov     [rsp+900h+cDbgFile], rcx; cDbgFile
0x140038a83  mov     r9d, 2; Type
0x140038a89  mov     [rsp+900h+DbgFile], rax; DbgFile
0x140038a8e  mov     r8, rdi; ImageFile
0x140038a91  mov     [rsp+900h+cSymbolFile], rcx; cSymbolFile
0x140038a96  lea     rax, [rbp+800h+var_670]
0x140038a9d  mov     rcx, r13; hProcess
0x140038aa0  mov     [rsp+900h+SymbolFile], rax; SymbolFile
0x140038aa5  xor     edx, edx; SymPath
0x140038aa7  call    cs:__imp_SymGetSymbolFileW
0x140038aad  test    eax, eax
0x140038aaf  jnz     loc_140038B6B
0x140038ab5  call    cs:__imp_GetLastError
0x140038abb  cmp     eax, 2
0x140038abe  jnz     loc_140038B7C
0x140038ac4  mov     [rsp+900h+ExtCount], 100h; ExtCount
0x140038acd  lea     rax, [rbp+800h+Ext]
0x140038ad1  mov     [rsp+900h+cDbgFile], rax; Ext
0x140038ad6  xor     r9d, r9d; Dir
0x140038ad9  xor     eax, eax
0x140038adb  xor     r8d, r8d; DriveCount
0x140038ade  mov     [rsp+900h+DbgFile], rax; FilenameCount
0x140038ae3  xor     edx, edx; Drive
0x140038ae5  mov     [rsp+900h+cSymbolFile], rax; Filename
0x140038aea  mov     rcx, rdi; FullPath
0x140038aed  mov     [rsp+900h+SymbolFile], rax; DirCount
0x140038af2  call    cs:__imp__wsplitpath_s
0x140038af8  mov     eax, 5Ch ; '\'
0x140038afd  lea     r8, aSS_0; "%s%s"
0x140038b04  mov     [rbp+800h+Ext], ax
0x140038b08  lea     rcx, [rbp+800h+SymPath]; unsigned __int16 *
0x140038b0f  lea     rax, [rbp+800h+Ext]
0x140038b13  mov     r9, r15
0x140038b16  mov     edx, 104h; unsigned __int64
0x140038b1b  mov     [rsp+900h+SymbolFile], rax
0x140038b20  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140038b25  mov     ecx, 104h
0x140038b2a  lea     rax, [rbp+800h+var_460]
0x140038b31  mov     [rsp+900h+cDbgFile], rcx; cDbgFile
0x140038b36  lea     rdx, [rbp+800h+SymPath]; SymPath
0x140038b3d  mov     [rsp+900h+DbgFile], rax; DbgFile
0x140038b42  mov     r9d, 2; Type
0x140038b48  mov     [rsp+900h+cSymbolFile], rcx; cSymbolFile
0x140038b4d  lea     rax, [rbp+800h+var_670]
0x140038b54  mov     rcx, r13; hProcess
0x140038b57  mov     [rsp+900h+SymbolFile], rax; SymbolFile
0x140038b5c  mov     r8, rdi; ImageFile
0x140038b5f  call    cs:__imp_SymGetSymbolFileW
0x140038b65  xor     ecx, ecx
0x140038b67  test    eax, eax
0x140038b69  jz      short loc_140038B7E
0x140038b6b  mov     rdx, [rsp+900h+var_890]
0x140038b70  lea     rcx, [rbp+800h+var_670]
0x140038b77  call    BinplaceWppFmtW
0x140038b7c  xor     ecx, ecx
0x140038b7e  or      rax, 0FFFFFFFFFFFFFFFFh
0x140038b82  inc     rax
0x140038b85  cmp     [rdi+rax*2], cx
0x140038b89  jnz     short loc_140038B82
0x140038b8b  lea     rdi, [rdi+rax*2]
0x140038b8f  mov     r9d, 3Bh ; ';'
0x140038b95  add     rdi, 2
0x140038b99  test    r12b, r12b
0x140038b9c  jz      short loc_140038BA2
0x140038b9e  mov     [r14], r9w
0x140038ba2  inc     esi
0x140038ba4  mov     r14d, 0
0x140038baa  cmp     esi, ebx
0x140038bac  jb      loc_140038A53
0x140038bb2  mov     rcx, [rsp+900h+var_890]; void *
0x140038bb7  lea     rax, [rbp+800h+var_880]
0x140038bbb  cmp     rcx, rax
0x140038bbe  jz      short loc_140038BCC
0x140038bc0  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x140038bc7  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140038bcc  mov     rcx, [rsp+900h+UserSearchPath]; void *
0x140038bd1  lea     rax, [rsp+900h+var_8A0]
0x140038bd6  cmp     rcx, rax
0x140038bd9  jz      short loc_140038BE7
0x140038bdb  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x140038be2  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140038be7  mov     rcx, [rbp+800h+var_40]
0x140038bee  xor     rcx, rsp; StackCookie
0x140038bf1  call    __security_check_cookie
0x140038bf6  mov     rbx, [rsp+900h+arg_18]
0x140038bfe  add     rsp, 8D0h
0x140038c05  pop     r15
0x140038c07  pop     r14
0x140038c09  pop     r13
0x140038c0b  pop     r12
0x140038c0d  pop     rdi
0x140038c0e  pop     rsi
0x140038c0f  pop     rbp
0x140038c10  retn
```
