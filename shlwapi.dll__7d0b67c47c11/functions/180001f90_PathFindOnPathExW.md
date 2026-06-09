# PathFindOnPathExW

- ea: `0x180001f90`
- end: `0x1800022b0`
- name: `PathFindOnPathExW`
- size: `800`
- prototype: `__int64 __fastcall(unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `reparse_path, broker_com_uri`

## callers

- `0x180020b10`

## callees

- `0x180001f90`
- `0x1800022c0`
- `0x180002490`
- `0x180003400`
- `0x180012550`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000218e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000218e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000226b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000227e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000226b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000227e`
- `api-ms-win-core-sysinfo-l1-1-0!GetWindowsDirectoryW` at `0x1800020c5`
- `api-ms-win-core-sysinfo-l1-1-0!GetWindowsDirectoryW` at `0x1800020c5`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180002056`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180002056`
- `api-ms-win-core-processenvironment-l1-1-0!GetEnvironmentVariableW` at `0x180002175`
- `api-ms-win-core-processenvironment-l1-1-0!GetEnvironmentVariableW` at `0x1800021ad`
- `api-ms-win-core-processenvironment-l1-1-0!GetEnvironmentVariableW` at `0x180002175`
- `api-ms-win-core-processenvironment-l1-1-0!GetEnvironmentVariableW` at `0x1800021ad`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathCombineW` at `0x180002013`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathCombineW` at `0x180002013`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsUNCServerShareW` at `0x18000202d`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsUNCServerShareW` at `0x180002086`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsUNCServerShareW` at `0x180002102`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsUNCServerShareW` at `0x18000222d`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsUNCServerShareW` at `0x18000202d`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsUNCServerShareW` at `0x180002086`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsUNCServerShareW` at `0x180002102`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsUNCServerShareW` at `0x18000222d`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsUNCServerW` at `0x18000201e`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsUNCServerW` at `0x180002077`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsUNCServerW` at `0x1800020f3`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsUNCServerW` at `0x18000221e`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsUNCServerW` at `0x18000201e`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsUNCServerW` at `0x180002077`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsUNCServerW` at `0x1800020f3`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsUNCServerW` at `0x18000221e`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsFileSpecW` at `0x180001fd5`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsFileSpecW` at `0x180001fd5`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathAppendW` at `0x180002064`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathAppendW` at `0x1800020e0`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathAppendW` at `0x180002213`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathAppendW` at `0x180002064`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathAppendW` at `0x1800020e0`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathAppendW` at `0x180002213`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathUnquoteSpacesW` at `0x180001fe6`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathUnquoteSpacesW` at `0x180001fe6`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1800021fb`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1800021fb`

## pseudocode

```c
__int64 __fastcall PathFindOnPathExW(unsigned __int16 *a1, LPCWSTR *a2)
{
  WCHAR *v3; // rbx
  int v4; // edi
  __int64 v5; // rsi
  const WCHAR *v6; // rdx
  __int64 v8; // rax
  WCHAR *v9; // rcx
  WCHAR *v10; // rcx
  signed int EnvironmentVariableW; // eax
  DWORD v12; // r14d
  WCHAR *v13; // rax
  WCHAR *v14; // rdi
  unsigned __int16 *PathW; // r15
  LPCWSTR *i; // r14
  WCHAR pszDest[264]; // [rsp+20h] [rbp-E0h] BYREF
  WCHAR Buffer[256]; // [rsp+230h] [rbp+130h] BYREF

  v3 = a1;
  if ( a1 && PathIsFileSpecW(a1) )
  {
    PathUnquoteSpacesW(v3);
    v4 = 0;
    v5 = 260;
    if ( a2 )
    {
      while ( 1 )
      {
        v6 = a2[v4];
        if ( !v6 || !*v6 )
          break;
        PathCombineW(pszDest, v6, v3);
        if ( !PathIsUNCServerW(pszDest)
          && !PathIsUNCServerShareW(pszDest)
          && (unsigned int)PathFileExistsDefExtAndAttributesW(pszDest) )
        {
          goto LABEL_14;
        }
        ++v4;
      }
    }
    GetSystemDirectoryW(pszDest, 0x104u);
    if ( PathAppendW(pszDest, v3) )
    {
      if ( !PathIsUNCServerW(pszDest)
        && !PathIsUNCServerShareW(pszDest)
        && (unsigned int)PathFileExistsDefExtAndAttributesW(pszDest) )
      {
LABEL_14:
        StringCchCopyW(v3, 0x104u, pszDest);
        return 1;
      }
      if ( GetWindowsDirectoryW(pszDest, 0x104u) - 1 <= 0x102 && PathAppendW(pszDest, v3) )
      {
        if ( !PathIsUNCServerW(pszDest)
          && !PathIsUNCServerShareW(pszDest)
          && (unsigned int)PathFileExistsDefExtAndAttributesW(pszDest) )
        {
          v8 = 2147483646;
          v9 = pszDest;
          do
          {
            if ( !v8 )
              break;
            if ( !*v9 )
              break;
            *v3++ = *v9++;
            --v8;
            --v5;
          }
          while ( v5 );
          v10 = v3 - 1;
          if ( v5 )
            v10 = v3;
          *v10 = 0;
          return 1;
        }
        EnvironmentVariableW = GetEnvironmentVariableW(L"PATH", Buffer, 0x100u);
        v12 = EnvironmentVariableW;
        if ( (unsigned __int64)EnvironmentVariableW < 0x100 )
        {
          if ( EnvironmentVariableW )
          {
            v14 = 0;
            PathW = Buffer;
LABEL_33:
            while ( 1 )
            {
              PathW = (unsigned __int16 *)NextPathW(PathW, pszDest);
              if ( !PathW )
                break;
              if ( a2 )
              {
                for ( i = a2; *i; ++i )
                {
                  if ( !lstrcmpiW(pszDest, *i) )
                    goto LABEL_33;
                }
              }
              PathAppendW(pszDest, v3);
              if ( !PathIsUNCServerW(pszDest)
                && !PathIsUNCServerShareW(pszDest)
                && (unsigned int)PathFileExistsDefExtAndAttributesW(pszDest) )
              {
                StringCchCopyW(v3, 0x104u, pszDest);
                if ( v14 )
                  LocalFree(v14);
                return 1;
              }
            }
            if ( v14 )
              LocalFree(v14);
          }
        }
        else
        {
          v13 = (WCHAR *)LocalAlloc(0x40u, 2LL * EnvironmentVariableW);
          v14 = v13;
          if ( v13 )
          {
            GetEnvironmentVariableW(L"PATH", v13, v12);
            PathW = v14;
            goto LABEL_33;
          }
        }
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180001f90  mov     [rsp-8+arg_18], rbx
0x180001f95  push    rbp
0x180001f96  push    rsi
0x180001f97  push    rdi
0x180001f98  push    r12
0x180001f9a  push    r13
0x180001f9c  push    r14
0x180001f9e  push    r15
0x180001fa0  lea     rbp, [rsp-340h]
0x180001fa8  sub     rsp, 440h
0x180001faf  mov     rax, cs:__security_cookie
0x180001fb6  xor     rax, rsp
0x180001fb9  mov     [rbp+370h+var_40], rax
0x180001fc0  xor     r15d, r15d
0x180001fc3  mov     r13d, r8d
0x180001fc6  mov     r12, rdx
0x180001fc9  mov     rbx, rcx
0x180001fcc  test    rcx, rcx
0x180001fcf  jz      loc_180002284
0x180001fd5  call    cs:__imp_PathIsFileSpecW
0x180001fdb  test    eax, eax
0x180001fdd  jz      loc_180002284
0x180001fe3  mov     rcx, rbx; lpsz
0x180001fe6  call    cs:__imp_PathUnquoteSpacesW
0x180001fec  mov     edi, r15d
0x180001fef  mov     esi, 104h
0x180001ff4  test    r12, r12
0x180001ff7  jz      short loc_18000204F
0x180001ff9  movsxd  rax, edi
0x180001ffc  mov     rdx, [r12+rax*8]; pszDir
0x180002000  test    rdx, rdx
0x180002003  jz      short loc_18000204F
0x180002005  cmp     [rdx], r15w
0x180002009  jz      short loc_18000204F
0x18000200b  mov     r8, rbx; pszFile
0x18000200e  lea     rcx, [rsp+470h+pszDest]; pszDest
0x180002013  call    cs:__imp_PathCombineW
0x180002019  lea     rcx, [rsp+470h+pszDest]; pszPath
0x18000201e  call    cs:__imp_PathIsUNCServerW
0x180002024  test    eax, eax
0x180002026  jnz     short loc_18000204B
0x180002028  lea     rcx, [rsp+470h+pszDest]; pszPath
0x18000202d  call    cs:__imp_PathIsUNCServerShareW
0x180002033  test    eax, eax
0x180002035  jnz     short loc_18000204B
0x180002037  xor     r8d, r8d
0x18000203a  lea     rcx, [rsp+470h+pszDest]; lpFileName
0x18000203f  mov     edx, r13d
0x180002042  call    PathFileExistsDefExtAndAttributesW
0x180002047  test    eax, eax
0x180002049  jnz     short loc_1800020A4
0x18000204b  inc     edi
0x18000204d  jmp     short loc_180001FF9
0x18000204f  mov     edx, esi; uSize
0x180002051  lea     rcx, [rsp+470h+pszDest]; lpBuffer
0x180002056  call    cs:__imp_GetSystemDirectoryW
0x18000205c  mov     rdx, rbx; pszMore
0x18000205f  lea     rcx, [rsp+470h+pszDest]; pszPath
0x180002064  call    cs:__imp_PathAppendW
0x18000206a  test    eax, eax
0x18000206c  jz      loc_180002284
0x180002072  lea     rcx, [rsp+470h+pszDest]; pszPath
0x180002077  call    cs:__imp_PathIsUNCServerW
0x18000207d  test    eax, eax
0x18000207f  jnz     short loc_1800020BE
0x180002081  lea     rcx, [rsp+470h+pszDest]; pszPath
0x180002086  call    cs:__imp_PathIsUNCServerShareW
0x18000208c  test    eax, eax
0x18000208e  jnz     short loc_1800020BE
0x180002090  xor     r8d, r8d
0x180002093  lea     rcx, [rsp+470h+pszDest]; lpFileName
0x180002098  mov     edx, r13d
0x18000209b  call    PathFileExistsDefExtAndAttributesW
0x1800020a0  test    eax, eax
0x1800020a2  jz      short loc_1800020BE
0x1800020a4  lea     r8, [rsp+470h+pszDest]; unsigned __int16 *
0x1800020a9  mov     rdx, rsi; unsigned __int64
0x1800020ac  mov     rcx, rbx; unsigned __int16 *
0x1800020af  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800020b4  mov     eax, 1
0x1800020b9  jmp     loc_180002286
0x1800020be  mov     edx, esi; uSize
0x1800020c0  lea     rcx, [rsp+470h+pszDest]; lpBuffer
0x1800020c5  call    cs:__imp_GetWindowsDirectoryW
0x1800020cb  dec     eax
0x1800020cd  cmp     eax, 102h
0x1800020d2  ja      loc_180002284
0x1800020d8  mov     rdx, rbx; pszMore
0x1800020db  lea     rcx, [rsp+470h+pszDest]; pszPath
0x1800020e0  call    cs:__imp_PathAppendW
0x1800020e6  test    eax, eax
0x1800020e8  jz      loc_180002284
0x1800020ee  lea     rcx, [rsp+470h+pszDest]; pszPath
0x1800020f3  call    cs:__imp_PathIsUNCServerW
0x1800020f9  test    eax, eax
0x1800020fb  jnz     short loc_18000215F
0x1800020fd  lea     rcx, [rsp+470h+pszDest]; pszPath
0x180002102  call    cs:__imp_PathIsUNCServerShareW
0x180002108  test    eax, eax
0x18000210a  jnz     short loc_18000215F
0x18000210c  xor     r8d, r8d
0x18000210f  lea     rcx, [rsp+470h+pszDest]; lpFileName
0x180002114  mov     edx, r13d
0x180002117  call    PathFileExistsDefExtAndAttributesW
0x18000211c  test    eax, eax
0x18000211e  jz      short loc_18000215F
0x180002120  mov     eax, 7FFFFFFEh
0x180002125  lea     rcx, [rsp+470h+pszDest]
0x18000212a  test    rax, rax
0x18000212d  jz      short loc_18000214B
0x18000212f  movzx   edx, word ptr [rcx]
0x180002132  test    dx, dx
0x180002135  jz      short loc_18000214B
0x180002137  mov     [rbx], dx
0x18000213a  add     rcx, 2
0x18000213e  add     rbx, 2
0x180002142  dec     rax
0x180002145  sub     rsi, 1
0x180002149  jnz     short loc_18000212A
0x18000214b  test    rsi, rsi
0x18000214e  lea     rcx, [rbx-2]
0x180002152  cmovnz  rcx, rbx
0x180002156  mov     [rcx], r15w
0x18000215a  jmp     loc_1800020B4
0x18000215f  mov     edi, 100h
0x180002164  lea     rdx, [rbp+370h+Buffer]; lpBuffer
0x18000216b  mov     r8d, edi; nSize
0x18000216e  lea     rcx, Name; "PATH"
0x180002175  call    cs:__imp_GetEnvironmentVariableW
0x18000217b  movsxd  r14, eax
0x18000217e  mov     rdx, r14
0x180002181  cmp     r14, rdi
0x180002184  jb      short loc_1800021B8
0x180002186  add     rdx, rdx; uBytes
0x180002189  mov     ecx, 40h ; '@'; uFlags
0x18000218e  call    cs:__imp_LocalAlloc
0x180002194  mov     rdi, rax
0x180002197  test    rax, rax
0x18000219a  jz      loc_180002284
0x1800021a0  mov     r8d, r14d; nSize
0x1800021a3  lea     rcx, Name; "PATH"
0x1800021aa  mov     rdx, rax; lpBuffer
0x1800021ad  call    cs:__imp_GetEnvironmentVariableW
0x1800021b3  mov     r15, rdi
0x1800021b6  jmp     short loc_1800021CA
0x1800021b8  test    eax, eax
0x1800021ba  jz      loc_180002284
0x1800021c0  mov     rdi, r15
0x1800021c3  lea     r15, [rbp+370h+Buffer]
0x1800021ca  mov     r8d, esi
0x1800021cd  lea     rdx, [rsp+470h+pszDest]; unsigned __int16 *
0x1800021d2  mov     rcx, r15; unsigned __int16 *
0x1800021d5  call    NextPathW
0x1800021da  mov     r15, rax
0x1800021dd  test    rax, rax
0x1800021e0  jz      loc_180002276
0x1800021e6  test    r12, r12
0x1800021e9  jz      short loc_18000220B
0x1800021eb  mov     r14, r12
0x1800021ee  mov     rdx, [r14]; lpString2
0x1800021f1  test    rdx, rdx
0x1800021f4  jz      short loc_18000220B
0x1800021f6  lea     rcx, [rsp+470h+pszDest]; lpString1
0x1800021fb  call    cs:__imp_lstrcmpiW
0x180002201  test    eax, eax
0x180002203  jz      short loc_1800021CA
0x180002205  add     r14, 8
0x180002209  jmp     short loc_1800021EE
0x18000220b  mov     rdx, rbx; pszMore
0x18000220e  lea     rcx, [rsp+470h+pszDest]; pszPath
0x180002213  call    cs:__imp_PathAppendW
0x180002219  lea     rcx, [rsp+470h+pszDest]; pszPath
0x18000221e  call    cs:__imp_PathIsUNCServerW
0x180002224  test    eax, eax
0x180002226  jnz     short loc_1800021CA
0x180002228  lea     rcx, [rsp+470h+pszDest]; pszPath
0x18000222d  call    cs:__imp_PathIsUNCServerShareW
0x180002233  test    eax, eax
0x180002235  jnz     short loc_1800021CA
0x180002237  xor     r8d, r8d
0x18000223a  lea     rcx, [rsp+470h+pszDest]; lpFileName
0x18000223f  mov     edx, r13d
0x180002242  call    PathFileExistsDefExtAndAttributesW
0x180002247  test    eax, eax
0x180002249  jz      loc_1800021CA
0x18000224f  lea     r8, [rsp+470h+pszDest]; unsigned __int16 *
0x180002254  mov     rdx, rsi; unsigned __int64
0x180002257  mov     rcx, rbx; unsigned __int16 *
0x18000225a  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000225f  test    rdi, rdi
0x180002262  jz      loc_1800020B4
0x180002268  mov     rcx, rdi; hMem
0x18000226b  call    cs:__imp_LocalFree
0x180002271  jmp     loc_1800020B4
0x180002276  test    rdi, rdi
0x180002279  jz      short loc_180002284
0x18000227b  mov     rcx, rdi; hMem
0x18000227e  call    cs:__imp_LocalFree
0x180002284  xor     eax, eax
0x180002286  mov     rcx, [rbp+370h+var_40]
0x18000228d  xor     rcx, rsp; StackCookie
0x180002290  call    __security_check_cookie
0x180002295  mov     rbx, [rsp+470h+arg_18]
0x18000229d  add     rsp, 440h
0x1800022a4  pop     r15
0x1800022a6  pop     r14
0x1800022a8  pop     r13
0x1800022aa  pop     r12
0x1800022ac  pop     rdi
0x1800022ad  pop     rsi
0x1800022ae  pop     rbp
0x1800022af  retn
```
