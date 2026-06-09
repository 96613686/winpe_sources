# CreateNestedDirectory(ushort const *,_SECURITY_ATTRIBUTES *)

- ea: `0x1800067b8`
- end: `0x1800068f2`
- name: `?CreateNestedDirectory@@YAJPEBGPEAU_SECURITY_ATTRIBUTES@@@Z`
- size: `314`
- prototype: `__int64 __fastcall(STRSAFE_PCNZWCH pszSrc, struct _SECURITY_ATTRIBUTES *)`
- caller_count: `2`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x18000ab88`
- `0x18000cce0`

## callees

- `0x180005690`
- `0x1800067b8`
- `0x1800068f8`
- `0x180006968`
- `0x180007008`
- `0x18000e640`
- `0x1800123d0`
- `0x180012428`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180006820`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x1800068b1`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180006820`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x1800068b1`

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
0x1800067b8  mov     [rsp+arg_8], rbx
0x1800067bd  mov     [rsp+arg_10], rsi
0x1800067c2  push    rdi
0x1800067c3  sub     rsp, 250h
0x1800067ca  mov     rax, cs:__security_cookie
0x1800067d1  xor     rax, rsp
0x1800067d4  mov     [rsp+258h+var_18], rax
0x1800067dc  mov     rbx, rcx
0x1800067df  call    ?IsLocalFullPath@@YAHPEBG@Z; IsLocalFullPath(ushort const *)
0x1800067e4  xor     edi, edi
0x1800067e6  test    eax, eax
0x1800067e8  jnz     short loc_18000681E
0x1800067ea  call    ?IsUNCPath@@YAHPEBG@Z; IsUNCPath(ushort const *)
0x1800067ef  test    eax, eax
0x1800067f1  jnz     short loc_18000681E
0x1800067f3  mov     eax, 800700A1h
0x1800067f8  mov     rcx, [rsp+258h+var_18]
0x180006800  xor     rcx, rsp; StackCookie
0x180006803  call    __security_check_cookie
0x180006808  lea     r11, [rsp+258h+var_8]
0x180006810  mov     rbx, [r11+18h]
0x180006814  mov     rsi, [r11+20h]
0x180006818  mov     rsp, r11
0x18000681b  pop     rdi
0x18000681c  retn
0x18000681e  xor     edx, edx; lpSecurityAttributes
0x180006820  call    cs:__imp_CreateDirectoryW
0x180006827  nop     dword ptr [rax+rax+00h]
0x18000682c  mov     ecx, eax; int
0x18000682e  call    ?ResultFromWin32Bool@@YAJH@Z; ResultFromWin32Bool(int)
0x180006833  mov     ecx, eax; pszDest
0x180006835  cmp     eax, 80070003h
0x18000683a  jz      short loc_180006849
0x18000683c  cmp     ecx, 800700B7h
0x180006842  mov     eax, edi
0x180006844  cmovnz  eax, ecx
0x180006847  jmp     short loc_1800067F8
0x180006849  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000684d  inc     rax
0x180006850  cmp     [rbx+rax*2], di
0x180006854  jnz     short loc_18000684D
0x180006856  mov     esi, 5Ch ; '\'
0x18000685b  mov     edx, 104h; unsigned __int64
0x180006860  cmp     [rbx+rax*2-2], si
0x180006865  jnz     short loc_1800068CB
0x180006867  call    StringValidateDestW
0x18000686c  mov     ecx, eax
0x18000686e  test    eax, eax
0x180006870  js      short loc_1800068EB
0x180006872  mov     r9, rbx; pszSrc
0x180006875  lea     rcx, [rsp+258h+pszDest]; pszDest
0x18000687a  call    StringCopyWorkerW
0x18000687f  mov     ecx, eax
0x180006881  test    ecx, ecx
0x180006883  js      short loc_1800068E1
0x180006885  movzx   eax, [rsp+258h+var_222]
0x18000688a  test    ax, ax
0x18000688d  jz      short loc_18000683C
0x18000688f  lea     rbx, [rsp+258h+var_222]
0x180006894  cmp     ax, si
0x180006897  jz      short loc_1800068A7
0x180006899  add     rbx, 2
0x18000689d  movzx   eax, word ptr [rbx]
0x1800068a0  test    ax, ax
0x1800068a3  jnz     short loc_180006894
0x1800068a5  jmp     short loc_18000683C
0x1800068a7  xor     edx, edx; lpSecurityAttributes
0x1800068a9  mov     [rbx], di
0x1800068ac  lea     rcx, [rsp+258h+pszDest]; lpPathName
0x1800068b1  call    cs:__imp_CreateDirectoryW
0x1800068b8  nop     dword ptr [rax+rax+00h]
0x1800068bd  mov     ecx, eax; int
0x1800068bf  call    ?ResultFromWin32Bool@@YAJH@Z; ResultFromWin32Bool(int)
0x1800068c4  mov     ecx, eax
0x1800068c6  mov     [rbx], si
0x1800068c9  jmp     short loc_180006899
0x1800068cb  mov     r9, rbx
0x1800068ce  lea     r8, aS; "%s\\"
0x1800068d5  lea     rcx, [rsp+258h+pszDest]; unsigned __int16 *
0x1800068da  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800068df  jmp     short loc_18000687F
0x1800068e1  mov     ecx, 800700CEh
0x1800068e6  jmp     loc_18000683C
0x1800068eb  mov     [rsp+258h+pszDest], di
0x1800068f0  jmp     short loc_180006881
```
