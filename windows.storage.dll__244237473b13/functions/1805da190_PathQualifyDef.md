# PathQualifyDef

- ea: `0x1805da190`
- end: `0x1805da49f`
- name: `PathQualifyDef`
- size: `783`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int64, unsigned __int16 *)`
- caller_count: `4`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x1802bbb40`
- `0x1805c7364`
- `0x1805c74f8`
- `0x1805da170`

## callees

- `0x180133f50`
- `0x1803b1f60`
- `0x1805da190`

## import_xrefs

- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1805da3b7`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1805da3b7`
- `api-ms-win-core-string-l2-1-0!CharPrevW` at `0x1805da45e`
- `api-ms-win-core-string-l2-1-0!CharPrevW` at `0x1805da45e`
- `api-ms-win-core-sysinfo-l1-1-0!GetWindowsDirectoryW` at `0x1805da2c0`
- `api-ms-win-core-sysinfo-l1-1-0!GetWindowsDirectoryW` at `0x1805da2c0`
- `api-ms-win-core-path-l1-1-0!PathIsUNCEx` at `0x1805da219`
- `api-ms-win-core-path-l1-1-0!PathIsUNCEx` at `0x1805da219`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathRemoveBackslashW` at `0x1805da435`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathRemoveBackslashW` at `0x1805da435`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathRemoveFileSpecW` at `0x1805da377`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathRemoveFileSpecW` at `0x1805da377`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathGetDriveNumberW` at `0x1805da253`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathGetDriveNumberW` at `0x1805da253`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathStripToRootW` at `0x1805da2e0`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathStripToRootW` at `0x1805da304`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathStripToRootW` at `0x1805da2e0`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathStripToRootW` at `0x1805da304`
- `api-ms-win-shcore-path-l1-1-0!__imp_PathBuildRootW` at `0x1805da26d`
- `api-ms-win-shcore-path-l1-1-0!__imp_PathBuildRootW` at `0x1805da26d`
- `api-ms-win-shlwapi-winrt-storage-l1-1-1!__imp_FixSlashesAndColonW` at `0x1805da1fe`
- `api-ms-win-shlwapi-winrt-storage-l1-1-1!__imp_FixSlashesAndColonW` at `0x1805da1fe`

## pseudocode

```c
void __fastcall PathQualifyDef(unsigned __int16 *a1, unsigned int a2, unsigned __int16 *a3, char a4)
{
  unsigned __int64 v5; // rdi
  char v7; // r12
  __int64 v8; // r14
  WCHAR *v9; // rbx
  int DriveNumberW; // eax
  unsigned __int16 *v11; // r15
  __int64 v12; // rax
  unsigned __int16 *v13; // rdi
  WCHAR v14; // ax
  __int64 v15; // rax
  WCHAR v16; // ax
  bool v17; // zf
  WCHAR v18; // ax
  LPWSTR v19; // rax
  PCWSTR ppszServer; // [rsp+28h] [rbp-D8h] BYREF
  WCHAR pszPath[2]; // [rsp+30h] [rbp-D0h] BYREF
  __int16 v23; // [rsp+34h] [rbp-CCh] BYREF
  char v24; // [rsp+36h] [rbp-CAh] BYREF
  WCHAR pszRoot[264]; // [rsp+240h] [rbp+140h] BYREF

  if ( a2 )
  {
    v5 = a2;
    v7 = a4;
    if ( (int)StringCchCopyW(pszPath, 0x104u, a1) >= 0 )
    {
      FixSlashesAndColonW(pszPath);
      ppszServer = 0;
      v8 = -1;
      if ( PathIsUNCEx(pszPath, &ppszServer) )
      {
        v9 = (WCHAR *)ppszServer;
        a1[ppszServer - pszPath] = 0;
      }
      else
      {
        DriveNumberW = PathGetDriveNumberW(pszPath);
        if ( DriveNumberW == -1 )
        {
          if ( !a3 || (int)StringCchCopyW(pszRoot, 0x104u, a3) < 0 )
          {
            pszRoot[0] = 0;
            if ( GetWindowsDirectoryW(pszRoot, 0x104u) - 1 > 0x102 )
              return;
            PathStripToRootW(pszRoot);
          }
          v9 = pszPath;
          if ( pszPath[0] == 92 )
            PathStripToRootW(pszRoot);
        }
        else
        {
          PathBuildRootW(pszRoot, DriveNumberW);
          v9 = (WCHAR *)&v24;
          if ( v23 != 92 )
            v9 = (WCHAR *)&v23;
        }
        StringCchCopyW(a1, v5, pszRoot);
      }
      v11 = &a1[v5];
      v12 = -1;
      do
        ++v12;
      while ( a1[v12] );
      v13 = &a1[v12];
      if ( *v9 )
      {
        do
        {
          if ( v13 >= v11 )
            goto LABEL_46;
          if ( *v9 == 46 )
          {
            v14 = v9[1];
            if ( v14 == 46 )
            {
              if ( !v9[2] || v9[2] == 92 )
              {
                *v13 = 0;
                PathRemoveFileSpecW(a1);
                v15 = -1;
                do
                  ++v15;
                while ( a1[v15] );
                v13 = &a1[v15];
LABEL_29:
                v16 = *v9;
                v17 = *v9 == 0;
                if ( !*v9 )
                  continue;
                do
                {
                  if ( v16 == 92 )
                    break;
                  v9 = CharNextW(v9);
                  v16 = *v9;
                }
                while ( *v9 );
                v7 = a4;
                v17 = *v9 == 0;
                if ( !*v9 )
                  continue;
                goto LABEL_43;
              }
            }
            else if ( !v14 || v14 == 92 )
            {
              goto LABEL_29;
            }
          }
          if ( v13 > a1 && *(v13 - 1) != 92 )
          {
            *v13 = 92;
            goto LABEL_40;
          }
          while ( 1 )
          {
            v18 = *v9;
            if ( !*v9 || v18 == 92 || v13 >= v11 )
              break;
            ++v9;
            *v13 = v18;
LABEL_40:
            ++v13;
          }
          if ( !*v9 )
            break;
LABEL_43:
          v17 = *++v9 == 0;
        }
        while ( !v17 );
      }
      if ( v13 >= v11 )
LABEL_46:
        v13 = v11 - 1;
      *v13 = 0;
      PathRemoveBackslashW(a1);
      if ( (v7 & 1) == 0 && *a1 )
      {
        do
          ++v8;
        while ( a1[v8] );
        v19 = CharPrevW(a1, &a1[v8]);
        if ( *v19 == 46 )
          *v19 = 0;
      }
    }
  }
}

```

## disassembly

```asm
0x1805da190  test    edx, edx
0x1805da192  jz      locret_1805DA49D
0x1805da198  mov     [rsp-8+arg_18], rbx
0x1805da19d  push    rbp
0x1805da19e  push    rsi
0x1805da19f  push    rdi
0x1805da1a0  push    r12
0x1805da1a2  push    r13
0x1805da1a4  push    r14
0x1805da1a6  push    r15
0x1805da1a8  lea     rbp, [rsp-360h]
0x1805da1b0  sub     rsp, 460h
0x1805da1b7  mov     rax, cs:__security_cookie
0x1805da1be  xor     rax, rsp
0x1805da1c1  mov     [rbp+390h+var_40], rax
0x1805da1c8  mov     rbx, r8
0x1805da1cb  mov     edi, edx
0x1805da1cd  mov     r8, rcx; unsigned __int16 *
0x1805da1d0  mov     [rsp+490h+var_470], r9d
0x1805da1d5  mov     rsi, rcx
0x1805da1d8  mov     r15d, 104h
0x1805da1de  mov     edx, r15d; unsigned __int64
0x1805da1e1  lea     rcx, [rsp+490h+pszPath]; unsigned __int16 *
0x1805da1e6  mov     r12d, r9d
0x1805da1e9  xor     r13d, r13d
0x1805da1ec  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1805da1f1  test    eax, eax
0x1805da1f3  js      loc_1805DA474
0x1805da1f9  lea     rcx, [rsp+490h+pszPath]
0x1805da1fe  call    cs:__imp_FixSlashesAndColonW
0x1805da205  nop     dword ptr [rax+rax+00h]
0x1805da20a  lea     rdx, [rsp+490h+ppszServer]; ppszServer
0x1805da20f  mov     [rsp+490h+ppszServer], r13
0x1805da214  lea     rcx, [rsp+490h+pszPath]; pszPath
0x1805da219  call    cs:__imp_PathIsUNCEx
0x1805da220  nop     dword ptr [rax+rax+00h]
0x1805da225  or      r14, 0FFFFFFFFFFFFFFFFh
0x1805da229  lea     edx, [r13+5Ch]
0x1805da22d  test    eax, eax
0x1805da22f  jz      short loc_1805DA24E
0x1805da231  mov     rbx, [rsp+490h+ppszServer]
0x1805da236  lea     rax, [rsp+490h+pszPath]
0x1805da23b  mov     rcx, rbx
0x1805da23e  sub     rcx, rax
0x1805da241  sar     rcx, 1
0x1805da244  mov     [rsi+rcx*2], r13w
0x1805da249  jmp     loc_1805DA327
0x1805da24e  lea     rcx, [rsp+490h+pszPath]; pszPath
0x1805da253  call    cs:__imp_PathGetDriveNumberW
0x1805da25a  nop     dword ptr [rax+rax+00h]
0x1805da25f  cmp     eax, r14d
0x1805da262  jz      short loc_1805DA293
0x1805da264  mov     edx, eax; iDrive
0x1805da266  lea     rcx, [rbp+390h+pszRoot]; pszRoot
0x1805da26d  call    cs:__imp_PathBuildRootW
0x1805da274  nop     dword ptr [rax+rax+00h]
0x1805da279  mov     ecx, 5Ch ; '\'
0x1805da27e  lea     rbx, [rsp+490h+var_45A]
0x1805da283  cmp     [rsp+490h+var_45C], cx
0x1805da288  lea     rax, [rsp+490h+var_45C]
0x1805da28d  cmovnz  rbx, rax
0x1805da291  jmp     short loc_1805DA310
0x1805da293  test    rbx, rbx
0x1805da296  jz      short loc_1805DA2AE
0x1805da298  mov     r8, rbx; unsigned __int16 *
0x1805da29b  lea     rcx, [rbp+390h+pszRoot]; unsigned __int16 *
0x1805da2a2  mov     rdx, r15; unsigned __int64
0x1805da2a5  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1805da2aa  test    eax, eax
0x1805da2ac  jns     short loc_1805DA2EC
0x1805da2ae  mov     edx, r15d; uSize
0x1805da2b1  mov     [rbp+390h+pszRoot], r13w
0x1805da2b9  lea     rcx, [rbp+390h+pszRoot]; lpBuffer
0x1805da2c0  call    cs:__imp_GetWindowsDirectoryW
0x1805da2c7  nop     dword ptr [rax+rax+00h]
0x1805da2cc  dec     eax
0x1805da2ce  cmp     eax, 102h
0x1805da2d3  ja      loc_1805DA474
0x1805da2d9  lea     rcx, [rbp+390h+pszRoot]; pszPath
0x1805da2e0  call    cs:__imp_PathStripToRootW
0x1805da2e7  nop     dword ptr [rax+rax+00h]
0x1805da2ec  mov     eax, 5Ch ; '\'
0x1805da2f1  lea     rbx, [rsp+490h+pszPath]
0x1805da2f6  cmp     [rsp+490h+pszPath], ax
0x1805da2fb  jnz     short loc_1805DA310
0x1805da2fd  lea     rcx, [rbp+390h+pszRoot]; pszPath
0x1805da304  call    cs:__imp_PathStripToRootW
0x1805da30b  nop     dword ptr [rax+rax+00h]
0x1805da310  lea     r8, [rbp+390h+pszRoot]; unsigned __int16 *
0x1805da317  mov     rdx, rdi; unsigned __int64
0x1805da31a  mov     rcx, rsi; unsigned __int16 *
0x1805da31d  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1805da322  mov     edx, 5Ch ; '\'
0x1805da327  lea     r15, [rsi+rdi*2]
0x1805da32b  mov     rax, r14
0x1805da32e  inc     rax
0x1805da331  cmp     [rsi+rax*2], r13w
0x1805da336  jnz     short loc_1805DA32E
0x1805da338  lea     rdi, [rsi+rax*2]
0x1805da33c  cmp     [rbx], r13w
0x1805da340  jz      loc_1805DA425
0x1805da346  cmp     rdi, r15
0x1805da349  jnb     loc_1805DA42A
0x1805da34f  cmp     word ptr [rbx], 2Eh ; '.'
0x1805da353  jnz     loc_1805DA3DD
0x1805da359  movzx   eax, word ptr [rbx+2]
0x1805da35d  cmp     ax, 2Eh ; '.'
0x1805da361  jnz     short loc_1805DA396
0x1805da363  cmp     [rbx+4], r13w
0x1805da368  jz      short loc_1805DA370
0x1805da36a  cmp     [rbx+4], dx
0x1805da36e  jnz     short loc_1805DA3DD
0x1805da370  mov     rcx, rsi; pszPath
0x1805da373  mov     [rdi], r13w
0x1805da377  call    cs:__imp_PathRemoveFileSpecW
0x1805da37e  nop     dword ptr [rax+rax+00h]
0x1805da383  mov     rax, r14
0x1805da386  inc     rax
0x1805da389  cmp     [rsi+rax*2], r13w
0x1805da38e  jnz     short loc_1805DA386
0x1805da390  lea     rdi, [rsi+rax*2]
0x1805da394  jmp     short loc_1805DA3A0
0x1805da396  test    ax, ax
0x1805da399  jz      short loc_1805DA3A0
0x1805da39b  cmp     ax, dx
0x1805da39e  jnz     short loc_1805DA3DD
0x1805da3a0  movzx   eax, word ptr [rbx]
0x1805da3a3  test    ax, ax
0x1805da3a6  jz      short loc_1805DA41A
0x1805da3a8  mov     r12d, 5Ch ; '\'
0x1805da3ae  cmp     ax, r12w
0x1805da3b2  jz      short loc_1805DA3CE
0x1805da3b4  mov     rcx, rbx; lpsz
0x1805da3b7  call    cs:__imp_CharNextW
0x1805da3be  nop     dword ptr [rax+rax+00h]
0x1805da3c3  mov     rbx, rax
0x1805da3c6  movzx   eax, word ptr [rax]
0x1805da3c9  test    ax, ax
0x1805da3cc  jnz     short loc_1805DA3AE
0x1805da3ce  movzx   eax, word ptr [rbx]
0x1805da3d1  mov     r12d, [rsp+490h+var_470]
0x1805da3d6  test    ax, ax
0x1805da3d9  jz      short loc_1805DA41A
0x1805da3db  jmp     short loc_1805DA410
0x1805da3dd  cmp     rdi, rsi
0x1805da3e0  jbe     short loc_1805DA402
0x1805da3e2  cmp     dx, [rdi-2]
0x1805da3e6  jz      short loc_1805DA402
0x1805da3e8  mov     [rdi], dx
0x1805da3eb  jmp     short loc_1805DA3FE
0x1805da3ed  cmp     ax, dx
0x1805da3f0  jz      short loc_1805DA40A
0x1805da3f2  cmp     rdi, r15
0x1805da3f5  jnb     short loc_1805DA40A
0x1805da3f7  add     rbx, 2
0x1805da3fb  mov     [rdi], ax
0x1805da3fe  add     rdi, 2
0x1805da402  movzx   eax, word ptr [rbx]
0x1805da405  test    ax, ax
0x1805da408  jnz     short loc_1805DA3ED
0x1805da40a  cmp     [rbx], r13w
0x1805da40e  jz      short loc_1805DA425
0x1805da410  add     rbx, 2
0x1805da414  movzx   eax, word ptr [rbx]
0x1805da417  test    ax, ax
0x1805da41a  mov     edx, 5Ch ; '\'
0x1805da41f  jnz     loc_1805DA346
0x1805da425  cmp     rdi, r15
0x1805da428  jb      short loc_1805DA42E
0x1805da42a  lea     rdi, [r15-2]
0x1805da42e  mov     rcx, rsi; pszPath
0x1805da431  mov     [rdi], r13w
0x1805da435  call    cs:__imp_PathRemoveBackslashW
0x1805da43c  nop     dword ptr [rax+rax+00h]
0x1805da441  test    r12b, 1
0x1805da445  jnz     short loc_1805DA474
0x1805da447  cmp     [rsi], r13w
0x1805da44b  jz      short loc_1805DA474
0x1805da44d  inc     r14
0x1805da450  cmp     [rsi+r14*2], r13w
0x1805da455  jnz     short loc_1805DA44D
0x1805da457  lea     rdx, [rsi+r14*2]; lpszCurrent
0x1805da45b  mov     rcx, rsi; lpszStart
0x1805da45e  call    cs:__imp_CharPrevW
0x1805da465  nop     dword ptr [rax+rax+00h]
0x1805da46a  cmp     word ptr [rax], 2Eh ; '.'
0x1805da46e  jnz     short loc_1805DA474
0x1805da470  mov     [rax], r13w
0x1805da474  mov     rcx, [rbp+390h+var_40]
0x1805da47b  xor     rcx, rsp; StackCookie
0x1805da47e  call    __security_check_cookie
0x1805da483  mov     rbx, [rsp+490h+arg_18]
0x1805da48b  add     rsp, 460h
0x1805da492  pop     r15
0x1805da494  pop     r14
0x1805da496  pop     r13
0x1805da498  pop     r12
0x1805da49a  pop     rdi
0x1805da49b  pop     rsi
0x1805da49c  pop     rbp
0x1805da49d  retn
```
