# CreateNestedDirectory(ushort const *,_SECURITY_ATTRIBUTES *)

- ea: `0x1800061d4`
- end: `0x180006301`
- name: `?CreateNestedDirectory@@YAJPEBGPEAU_SECURITY_ATTRIBUTES@@@Z`
- size: `301`
- prototype: `__int64 __fastcall(STRSAFE_PCNZWCH pszSrc, struct _SECURITY_ATTRIBUTES *)`
- caller_count: `2`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x18000a200`
- `0x18000c18c`

## callees

- `0x180004fc0`
- `0x1800061d4`
- `0x180006308`
- `0x180006378`
- `0x180006b24`
- `0x18000d9b0`
- `0x180011494`
- `0x1800114ec`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18000623b`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x1800062c6`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18000623b`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x1800062c6`

## pseudocode

```c
__int64 __fastcall CreateNestedDirectory(STRSAFE_PCNZWCH pszSrc, struct _SECURITY_ATTRIBUTES *a2)
{
  const unsigned __int16 *v3; // rcx
  __int64 result; // rax
  BOOL DirectoryW; // eax
  unsigned int v6; // eax
  size_t v7; // r8
  const wchar_t *v8; // rcx
  __int64 v9; // rax
  size_t v10; // rdx
  size_t *v11; // r8
  HRESULT v12; // eax
  __int16 v13; // ax
  __int16 *v14; // rbx
  BOOL v15; // eax
  size_t v16; // [rsp+20h] [rbp-238h]
  wchar_t pszDest[3]; // [rsp+30h] [rbp-228h] BYREF
  __int16 v18; // [rsp+36h] [rbp-222h] BYREF

  if ( !(unsigned int)IsLocalFullPath(pszSrc) && !(unsigned int)IsUNCPath(v3) )
    return 2147942561LL;
  DirectoryW = CreateDirectoryW(v3, 0);
  v6 = ResultFromWin32Bool(DirectoryW);
  v8 = (const wchar_t *)v6;
  if ( v6 == -2147024893 )
  {
    v9 = -1;
    do
      ++v9;
    while ( pszSrc[v9] );
    if ( pszSrc[v9 - 1] == 92 )
    {
      LODWORD(v8) = StringValidateDestW(v8, 0x104u, v7);
      if ( (int)v8 < 0 )
      {
        pszDest[0] = 0;
LABEL_14:
        if ( (int)v8 < 0 )
        {
          LODWORD(v8) = -2147024690;
        }
        else
        {
          v13 = v18;
          if ( v18 )
          {
            v14 = &v18;
            do
            {
              if ( v13 == 92 )
              {
                *v14 = 0;
                v15 = CreateDirectoryW(pszDest, 0);
                LODWORD(v8) = ResultFromWin32Bool(v15);
                *v14 = 92;
              }
              v13 = *++v14;
            }
            while ( *v14 );
          }
        }
        goto LABEL_5;
      }
      v12 = StringCopyWorkerW(pszDest, v10, v11, pszSrc, v16);
    }
    else
    {
      v12 = StringCchPrintfW(pszDest, 0x104u, L"%s\\", pszSrc);
    }
    LODWORD(v8) = v12;
    goto LABEL_14;
  }
LABEL_5:
  result = 0;
  if ( (_DWORD)v8 != -2147024713 )
    return (unsigned int)v8;
  return result;
}

```

## disassembly

```asm
0x1800061d4  mov     [rsp+arg_8], rbx
0x1800061d9  mov     [rsp+arg_10], rsi
0x1800061de  push    rdi
0x1800061df  sub     rsp, 250h
0x1800061e6  mov     rax, cs:__security_cookie
0x1800061ed  xor     rax, rsp
0x1800061f0  mov     [rsp+258h+var_18], rax
0x1800061f8  mov     rbx, rcx
0x1800061fb  call    ?IsLocalFullPath@@YAHPEBG@Z; IsLocalFullPath(ushort const *)
0x180006200  xor     edi, edi
0x180006202  test    eax, eax
0x180006204  jnz     short loc_180006239
0x180006206  call    ?IsUNCPath@@YAHPEBG@Z; IsUNCPath(ushort const *)
0x18000620b  test    eax, eax
0x18000620d  jnz     short loc_180006239
0x18000620f  mov     eax, 800700A1h
0x180006214  mov     rcx, [rsp+258h+var_18]
0x18000621c  xor     rcx, rsp; StackCookie
0x18000621f  call    __security_check_cookie
0x180006224  lea     r11, [rsp+258h+var_8]
0x18000622c  mov     rbx, [r11+18h]
0x180006230  mov     rsi, [r11+20h]
0x180006234  mov     rsp, r11
0x180006237  pop     rdi
0x180006238  retn
0x180006239  xor     edx, edx; lpSecurityAttributes
0x18000623b  call    cs:__imp_CreateDirectoryW
0x180006241  mov     ecx, eax; int
0x180006243  call    ?ResultFromWin32Bool@@YAJH@Z; ResultFromWin32Bool(int)
0x180006248  mov     ecx, eax; pszDest
0x18000624a  cmp     eax, 80070003h
0x18000624f  jz      short loc_18000625E
0x180006251  cmp     ecx, 800700B7h
0x180006257  mov     eax, edi
0x180006259  cmovnz  eax, ecx
0x18000625c  jmp     short loc_180006214
0x18000625e  or      rax, 0FFFFFFFFFFFFFFFFh
0x180006262  inc     rax
0x180006265  cmp     [rbx+rax*2], di
0x180006269  jnz     short loc_180006262
0x18000626b  mov     esi, 5Ch ; '\'
0x180006270  mov     edx, 104h; unsigned __int64
0x180006275  cmp     [rbx+rax*2-2], si
0x18000627a  jnz     short loc_1800062DA
0x18000627c  call    StringValidateDestW
0x180006281  mov     ecx, eax
0x180006283  test    eax, eax
0x180006285  js      short loc_1800062FA
0x180006287  mov     r9, rbx; pszSrc
0x18000628a  lea     rcx, [rsp+258h+pszDest]; pszDest
0x18000628f  call    StringCopyWorkerW
0x180006294  mov     ecx, eax
0x180006296  test    ecx, ecx
0x180006298  js      short loc_1800062F0
0x18000629a  movzx   eax, [rsp+258h+var_222]
0x18000629f  test    ax, ax
0x1800062a2  jz      short loc_180006251
0x1800062a4  lea     rbx, [rsp+258h+var_222]
0x1800062a9  cmp     ax, si
0x1800062ac  jz      short loc_1800062BC
0x1800062ae  add     rbx, 2
0x1800062b2  movzx   eax, word ptr [rbx]
0x1800062b5  test    ax, ax
0x1800062b8  jnz     short loc_1800062A9
0x1800062ba  jmp     short loc_180006251
0x1800062bc  xor     edx, edx; lpSecurityAttributes
0x1800062be  mov     [rbx], di
0x1800062c1  lea     rcx, [rsp+258h+pszDest]; lpPathName
0x1800062c6  call    cs:__imp_CreateDirectoryW
0x1800062cc  mov     ecx, eax; int
0x1800062ce  call    ?ResultFromWin32Bool@@YAJH@Z; ResultFromWin32Bool(int)
0x1800062d3  mov     ecx, eax
0x1800062d5  mov     [rbx], si
0x1800062d8  jmp     short loc_1800062AE
0x1800062da  mov     r9, rbx
0x1800062dd  lea     r8, aS; "%s\\"
0x1800062e4  lea     rcx, [rsp+258h+pszDest]; unsigned __int16 *
0x1800062e9  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800062ee  jmp     short loc_180006294
0x1800062f0  mov     ecx, 800700CEh
0x1800062f5  jmp     loc_180006251
0x1800062fa  mov     [rsp+258h+pszDest], di
0x1800062ff  jmp     short loc_180006296
```
