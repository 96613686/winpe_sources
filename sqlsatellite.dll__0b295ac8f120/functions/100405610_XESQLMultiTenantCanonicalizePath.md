# XESQLMultiTenantCanonicalizePath

- ea: `0x100405610`
- end: `0x10040589d`
- name: `XESQLMultiTenantCanonicalizePath`
- size: `653`
- prototype: `__int64 __fastcall(PWSTR pszPathOut, PCWSTR pszMore)`
- caller_count: `0`
- callee_count: `3`
- tags: `reparse_path, registry_config, broker_com_uri`

## callees

- `0x100405450`
- `0x100405610`
- `0x100486af0`

## import_xrefs

- `sqldk!?s_pServerConf@@3PEAVIServerConfiguration@@EA` at `0x100405695`
- `sqldk!?s_pServerConf@@3PEAVIServerConfiguration@@EA` at `0x10040571a`
- `sqldk!?s_pServerConf@@3PEAVIServerConfiguration@@EA` at `0x100405739`
- `api-ms-win-crt-string-l1-1-0!_wcslwr_s` at `0x1004057ca`
- `api-ms-win-crt-string-l1-1-0!_wcslwr_s` at `0x1004057ca`
- `SHLWAPI!PathIsRelativeW` at `0x100405687`
- `SHLWAPI!PathIsRelativeW` at `0x100405687`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x1004056eb`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x10040570c`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x1004057e5`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x1004056eb`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x10040570c`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x1004057e5`
- `api-ms-win-core-path-l1-1-0!PathCchCanonicalize` at `0x1004057fa`
- `api-ms-win-core-path-l1-1-0!PathCchCanonicalize` at `0x1004057fa`

## pseudocode

```c
__int64 __fastcall XESQLMultiTenantCanonicalizePath(PWSTR pszPathOut, wchar_t *pszMore, int a3, int a4)
{
  unsigned int v4; // ebp
  WCHAR *v7; // rbx
  __int64 v9; // rsi
  __int64 v10; // rdi
  unsigned int v11; // edi
  HRESULT v12; // eax
  const WCHAR *v13; // r9
  __int64 v14; // rax
  __int64 v15; // r8
  __int64 v16; // rdx
  __int64 v17; // r8
  wchar_t *v18; // rcx
  wchar_t v19; // ax
  wchar_t *v20; // rax
  unsigned __int64 v21; // rax
  __int64 v22; // rdi
  unsigned __int64 v23; // rcx
  char *v24; // r14
  WCHAR v25; // ax
  WCHAR *v26; // rax
  int v27[4]; // [rsp+20h] [rbp-468h] BYREF
  WCHAR pszPathOuta[264]; // [rsp+30h] [rbp-458h] BYREF
  wchar_t String[264]; // [rsp+240h] [rbp-248h] BYREF

  v4 = 0;
  v7 = pszPathOut;
  if ( !a3 )
    return XESQLCanonicalizePath(pszPathOut, pszMore);
  if ( pszMore )
  {
    v9 = -1;
    v10 = -1;
    do
      ++v10;
    while ( pszMore[v10] );
    v11 = 2 * v10;
    if ( v11 )
    {
      _mm_lfence();
      if ( PathIsRelativeW(pszMore) )
      {
        v27[0] = 260;
        if ( (*(unsigned int (__fastcall **)(struct IServerConfiguration *, WCHAR *, int *))(*(_QWORD *)s_pServerConf
                                                                                           + 152LL))(
               s_pServerConf,
               pszPathOuta,
               v27) )
        {
          v12 = -2147467259;
        }
        else
        {
          v13 = L"Public";
          if ( a4 )
            v13 = L"Private";
          v12 = PathCchCombine(pszPathOuta, 0x104u, pszPathOuta, v13);
          if ( v12 >= 0 )
          {
            _mm_lfence();
            v12 = PathCchCombine(pszPathOuta, 0x104u, pszPathOuta, pszMore);
            if ( v12 >= 0 )
            {
              v14 = (*(__int64 (__fastcall **)(struct IServerConfiguration *))(*(_QWORD *)s_pServerConf + 224LL))(s_pServerConf);
              do
                ++v9;
              while ( *(_WORD *)(v14 + 2 * v9) );
              v15 = (*(__int64 (__fastcall **)(struct IServerConfiguration *))(*(_QWORD *)s_pServerConf + 224LL))(s_pServerConf);
              if ( (unsigned int)v9 <= 0x7FFFFFFEuLL )
              {
                v16 = 260;
                v17 = v15 - (_QWORD)String;
                v18 = String;
                do
                {
                  if ( !((unsigned int)v9 + v16 - 260) )
                    break;
                  v19 = *(wchar_t *)((char *)v18 + v17);
                  if ( !v19 )
                    break;
                  *v18++ = v19;
                  --v16;
                }
                while ( v16 );
                v20 = v18 - 1;
                if ( v16 )
                  v20 = v18;
                *v20 = 0;
                v12 = -2147024774;
                if ( v16 )
                {
                  _wcslwr_s(String, 0x104u);
                  v12 = PathCchCombine(pszPathOuta, 0x104u, pszPathOuta, String);
                  if ( v12 >= 0 )
                    v12 = PathCchCanonicalize(v7, 0x104u, pszPathOuta);
                }
              }
              else
              {
                v12 = -2147024809;
              }
            }
          }
        }
      }
      else
      {
        v21 = (unsigned __int64)v11 >> 1;
        if ( v21 <= 0x7FFFFFFE )
        {
          v22 = 260;
          v23 = v21 - 260;
          v24 = (char *)((char *)pszMore - (char *)v7);
          do
          {
            if ( !(v23 + v22) )
              break;
            v25 = *(WCHAR *)((char *)v7 + (_QWORD)v24);
            if ( !v25 )
              break;
            *v7++ = v25;
            --v22;
          }
          while ( v22 );
          v26 = v7 - 1;
          if ( v22 )
            v26 = v7;
          *v26 = 0;
          v12 = -2147024774;
          if ( v22 )
            v12 = 0;
        }
        else
        {
          v12 = -2147024809;
          *v7 = 0;
        }
      }
      return v12 >= 0;
    }
  }
  return v4;
}

```

## disassembly

```asm
0x100405610  push    rbx
0x100405612  push    rbp
0x100405613  push    r14
0x100405615  push    r15
0x100405617  sub     rsp, 468h
0x10040561e  mov     rax, cs:__security_cookie
0x100405625  xor     rax, rsp
0x100405628  mov     [rsp+488h+var_38], rax
0x100405630  xor     ebp, ebp
0x100405632  mov     r15d, r9d
0x100405635  mov     r14, rdx
0x100405638  mov     rbx, rcx
0x10040563b  test    r8d, r8d
0x10040563e  jnz     short loc_10040564A
0x100405640  call    XESQLCanonicalizePath
0x100405645  jmp     loc_10040587F
0x10040564a  test    r14, r14
0x10040564d  jz      loc_10040587D
0x100405653  mov     [rsp+488h+arg_10], rsi
0x10040565b  mov     rsi, 0FFFFFFFFFFFFFFFFh
0x100405662  mov     [rsp+488h+var_28], rdi
0x10040566a  mov     rdi, rsi
0x10040566d  nop     dword ptr [rax]
0x100405670  inc     rdi
0x100405673  cmp     [rdx+rdi*2], bp
0x100405677  jnz     short loc_100405670
0x100405679  add     edi, edi
0x10040567b  jz      loc_10040586D
0x100405681  lfence
0x100405684  mov     rcx, r14; pszPath
0x100405687  call    cs:__imp_PathIsRelativeW
0x10040568d  test    eax, eax
0x10040568f  jz      loc_100405802
0x100405695  mov     rax, cs:__imp_?s_pServerConf@@3PEAVIServerConfiguration@@EA; IServerConfiguration * s_pServerConf
0x10040569c  lea     r8, [rsp+488h+var_468]
0x1004056a1  mov     edi, 104h
0x1004056a6  lea     rdx, [rsp+488h+pszPathOut]
0x1004056ab  mov     [rsp+488h+var_468], edi
0x1004056af  mov     rcx, [rax]
0x1004056b2  mov     rax, [rcx]
0x1004056b5  call    qword ptr [rax+98h]
0x1004056bb  test    eax, eax
0x1004056bd  jz      short loc_1004056C9
0x1004056bf  mov     eax, 80004005h
0x1004056c4  jmp     loc_100405866
0x1004056c9  lea     rax, pszMore; "Private"
0x1004056d0  test    r15d, r15d
0x1004056d3  lea     r9, aPublic; "Public"
0x1004056da  mov     rdx, rdi; cchPathOut
0x1004056dd  cmovnz  r9, rax; pszMore
0x1004056e1  lea     r8, [rsp+488h+pszPathOut]; pszPathIn
0x1004056e6  lea     rcx, [rsp+488h+pszPathOut]; pszPathOut
0x1004056eb  call    cs:__imp_PathCchCombine
0x1004056f1  test    eax, eax
0x1004056f3  js      loc_100405866
0x1004056f9  lfence
0x1004056fc  mov     r9, r14; pszMore
0x1004056ff  lea     r8, [rsp+488h+pszPathOut]; pszPathIn
0x100405704  mov     rdx, rdi; cchPathOut
0x100405707  lea     rcx, [rsp+488h+pszPathOut]; pszPathOut
0x10040570c  call    cs:__imp_PathCchCombine
0x100405712  test    eax, eax
0x100405714  js      loc_100405866
0x10040571a  mov     rax, cs:__imp_?s_pServerConf@@3PEAVIServerConfiguration@@EA; IServerConfiguration * s_pServerConf
0x100405721  mov     rcx, [rax]
0x100405724  mov     rax, [rcx]
0x100405727  call    qword ptr [rax+0E0h]
0x10040572d  nop     dword ptr [rax]
0x100405730  inc     rsi
0x100405733  cmp     [rax+rsi*2], bp
0x100405737  jnz     short loc_100405730
0x100405739  mov     rax, cs:__imp_?s_pServerConf@@3PEAVIServerConfiguration@@EA; IServerConfiguration * s_pServerConf
0x100405740  mov     rcx, [rax]
0x100405743  mov     rax, [rcx]
0x100405746  call    qword ptr [rax+0E0h]
0x10040574c  mov     r9d, esi
0x10040574f  mov     r8, rax
0x100405752  cmp     r9, 7FFFFFFEh
0x100405759  jbe     short loc_100405765
0x10040575b  mov     eax, 80070057h
0x100405760  jmp     loc_100405866
0x100405765  lea     rax, [rsp+488h+String]
0x10040576d  mov     rdx, rdi
0x100405770  sub     r8, rax
0x100405773  lea     rcx, [rsp+488h+String]
0x10040577b  nop     dword ptr [rax+rax+00h]
0x100405780  lea     rax, [rdx-104h]
0x100405787  add     rax, r9
0x10040578a  jz      short loc_1004057A3
0x10040578c  movzx   eax, word ptr [r8+rcx]
0x100405791  test    ax, ax
0x100405794  jz      short loc_1004057A3
0x100405796  mov     [rcx], ax
0x100405799  add     rcx, 2
0x10040579d  sub     rdx, 1
0x1004057a1  jnz     short loc_100405780
0x1004057a3  test    rdx, rdx
0x1004057a6  lea     rax, [rcx-2]
0x1004057aa  cmovnz  rax, rcx
0x1004057ae  mov     [rax], bp
0x1004057b1  mov     eax, 8007007Ah
0x1004057b6  cmovnz  eax, ebp
0x1004057b9  jz      loc_100405866
0x1004057bf  mov     rdx, rdi; SizeInWords
0x1004057c2  lea     rcx, [rsp+488h+String]; String
0x1004057ca  call    cs:__imp__wcslwr_s
0x1004057d0  lea     r9, [rsp+488h+String]; pszMore
0x1004057d8  mov     rdx, rdi; cchPathOut
0x1004057db  lea     r8, [rsp+488h+pszPathOut]; pszPathIn
0x1004057e0  lea     rcx, [rsp+488h+pszPathOut]; pszPathOut
0x1004057e5  call    cs:__imp_PathCchCombine
0x1004057eb  test    eax, eax
0x1004057ed  js      short loc_100405866
0x1004057ef  lea     r8, [rsp+488h+pszPathOut]; pszPathIn
0x1004057f4  mov     rdx, rdi; cchPathOut
0x1004057f7  mov     rcx, rbx; pszPathOut
0x1004057fa  call    cs:__imp_PathCchCanonicalize
0x100405800  jmp     short loc_100405866
0x100405802  mov     eax, edi
0x100405804  shr     rax, 1
0x100405807  cmp     rax, 7FFFFFFEh
0x10040580d  jbe     short loc_100405819
0x10040580f  mov     eax, 80070057h
0x100405814  mov     [rbx], bp
0x100405817  jmp     short loc_100405866
0x100405819  mov     edi, 104h
0x10040581e  lea     rcx, [rax-104h]
0x100405825  sub     r14, rbx
0x100405828  nop     dword ptr [rax+rax+00000000h]
0x100405830  lea     rax, [rcx+rdi]
0x100405834  test    rax, rax
0x100405837  jz      short loc_100405850
0x100405839  movzx   eax, word ptr [r14+rbx]
0x10040583e  test    ax, ax
0x100405841  jz      short loc_100405850
0x100405843  mov     [rbx], ax
0x100405846  add     rbx, 2
0x10040584a  sub     rdi, 1
0x10040584e  jnz     short loc_100405830
0x100405850  test    rdi, rdi
0x100405853  lea     rax, [rbx-2]
0x100405857  cmovnz  rax, rbx
0x10040585b  mov     [rax], bp
0x10040585e  mov     eax, 8007007Ah
0x100405863  cmovnz  eax, ebp
0x100405866  mov     ebp, eax
0x100405868  not     ebp
0x10040586a  shr     ebp, 1Fh
0x10040586d  mov     rsi, [rsp+488h+arg_10]
0x100405875  mov     rdi, [rsp+488h+var_28]
0x10040587d  mov     eax, ebp
0x10040587f  mov     rcx, [rsp+488h+var_38]
0x100405887  xor     rcx, rsp; StackCookie
0x10040588a  call    __security_check_cookie
0x10040588f  add     rsp, 468h
0x100405896  pop     r15
0x100405898  pop     r14
0x10040589a  pop     rbp
0x10040589b  pop     rbx
0x10040589c  retn
```
