# ChangeDeviceUserAssociation

- ea: `0x180030f40`
- end: `0x180031206`
- name: `ChangeDeviceUserAssociation`
- size: `710`
- prototype: `__int64 __fastcall(LPCWSTR lpAppName, LPCWSTR lpString, int, int, int)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x1800330a8`

## callees

- `0x180001600`
- `0x18001c740`
- `0x18001c854`
- `0x18002c8d4`
- `0x180030f40`
- `0x180032f08`
- `0x180033c28`
- `0x18003fb64`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18003107d`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180031096`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18003107d`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180031096`
- `KERNEL32!HeapAlloc` at `0x180030f8d`
- `KERNEL32!HeapAlloc` at `0x18003110f`
- `KERNEL32!HeapAlloc` at `0x180030f8d`
- `KERNEL32!HeapAlloc` at `0x18003110f`
- `KERNEL32!WritePrivateProfileStringW` at `0x1800310d1`
- `KERNEL32!WritePrivateProfileStringW` at `0x1800311f1`
- `KERNEL32!WritePrivateProfileStringW` at `0x1800310d1`
- `KERNEL32!WritePrivateProfileStringW` at `0x1800311f1`

## pseudocode

```c
__int64 __fastcall ChangeDeviceUserAssociation(LPCWSTR lpAppName, LPCWSTR lpString, int a3, int a4, int a5)
{
  wchar_t *v9; // r13
  const WCHAR *v10; // rdx
  wchar_t *v12; // rdi
  int v13; // r14d
  signed __int64 v14; // rsi
  wchar_t *v15; // rbx
  wchar_t *v16; // rax
  wchar_t *v17; // rax
  __int64 v18; // rax
  size_t v19; // rbx
  wchar_t *v20; // rax
  wchar_t *v21; // rsi
  wchar_t *i; // rcx
  wchar_t v23; // ax
  bool v24; // zf
  const WCHAR *v25; // r8
  const WCHAR *v26; // rdx
  __int64 v27; // [rsp+40h] [rbp-61h] BYREF
  wchar_t *String1; // [rsp+48h] [rbp-59h]
  STRSAFE_LPWSTR ppszDestEnd; // [rsp+50h] [rbp-51h] BYREF
  wchar_t pszDest[32]; // [rsp+60h] [rbp-41h] BYREF

  ppszDestEnd = 0;
  LODWORD(v27) = 128;
  String1 = (wchar_t *)HeapAlloc(ghTapisrvHeap, 8u, 0x80u);
  if ( !String1 )
    return 2147483716LL;
  v9 = gszLines;
  v10 = gszLines;
  if ( !a5 )
    v10 = gszPhones;
  if ( (unsigned int)MyGetPrivateProfileString(lpAppName, v10, (__int64)&v27) )
  {
    ServerFree(String1);
    return 2147483716LL;
  }
  StringCbPrintfExW(pszDest, 0x40u, &ppszDestEnd, 0, 0, L"%d,%d", a3, a4);
  v12 = String1;
  v13 = 0;
  v14 = ppszDestEnd - pszDest;
  v15 = String1;
  if ( *String1 )
  {
    while ( wcsncmp_0(v15, pszDest, (unsigned int)v14) || v15[(unsigned int)v14] != 44 && v15[(unsigned int)v14] )
    {
      v16 = wcschr(v15, 0x2Cu);
      v15 = v16;
      if ( v16 )
      {
        v17 = wcschr(v16 + 1, 0x2Cu);
        v15 = v17;
        if ( v17 )
        {
          v15 = v17 + 1;
          if ( v17[1] )
            continue;
        }
      }
      goto LABEL_14;
    }
    v13 = 1;
  }
LABEL_14:
  if ( lpString )
  {
    WritePrivateProfileStringW(lpAppName, gszFriendlyUserName, lpString, gszFileName);
    if ( !v13 )
    {
      v18 = -1;
      do
        ++v18;
      while ( v12[v18] );
      v19 = (unsigned int)(2 * (v14 + v18) + 4);
      if ( (unsigned int)v19 <= (unsigned int)v27 )
      {
        v19 = (unsigned int)v27;
      }
      else
      {
        v20 = (wchar_t *)HeapAlloc(ghTapisrvHeap, 8u, (unsigned int)v19);
        v21 = v20;
        if ( !v20 )
          return 2147483716LL;
        StringCbCopyW(v20, (unsigned int)v19, v12);
        ServerFree(v12);
        v12 = v21;
      }
      if ( *v12 )
      {
        StringCbCatW(v12, v19, L",");
        StringCbCatW(v12, v19, pszDest);
      }
      else
      {
        StringCbCopyW(v12, v19, pszDest);
      }
    }
  }
  else if ( v13 )
  {
    if ( v15[(unsigned int)v14] == 44 )
    {
      for ( i = &v15[(unsigned int)v14 + 1]; ; ++i )
      {
        v23 = *i;
        *v15 = *i;
        if ( !v23 )
          break;
        ++v15;
      }
    }
    else if ( !v15[(unsigned int)v14] )
    {
      if ( v15 == v12 )
        *v15 = 0;
      else
        *(v15 - 1) = 0;
    }
  }
  v24 = a5 == 0;
  if ( !a5 )
    goto LABEL_40;
  if ( *v12 )
  {
    v24 = a5 == 0;
LABEL_40:
    v25 = v12;
    if ( v24 )
      v9 = gszPhones;
    v26 = v9;
    goto LABEL_43;
  }
  v25 = 0;
  v26 = 0;
LABEL_43:
  WritePrivateProfileStringW(lpAppName, v26, v25, gszFileName);
  ServerFree(v12);
  return 0;
}

```

## disassembly

```asm
0x180030f40  push    rbp
0x180030f42  push    rbx
0x180030f43  push    rsi
0x180030f44  push    rdi
0x180030f45  push    r12
0x180030f47  push    r13
0x180030f49  push    r14
0x180030f4b  push    r15
0x180030f4d  lea     rbp, [rsp-17h]
0x180030f52  sub     rsp, 0B8h
0x180030f59  mov     rax, cs:__security_cookie
0x180030f60  xor     rax, rsp
0x180030f63  mov     [rbp+4Fh+var_50], rax
0x180030f67  xor     esi, esi
0x180030f69  mov     ebx, r8d
0x180030f6c  mov     r15, rdx
0x180030f6f  mov     [rbp+4Fh+ppszDestEnd], rsi
0x180030f73  mov     r12, rcx
0x180030f76  mov     r8d, 80h; dwBytes
0x180030f7c  mov     rcx, cs:ghTapisrvHeap; hHeap
0x180030f83  mov     edi, r9d
0x180030f86  lea     edx, [rsi+8]; dwFlags
0x180030f89  mov     dword ptr [rbp+4Fh+var_B0], r8d
0x180030f8d  call    cs:__imp_HeapAlloc
0x180030f93  mov     [rbp+4Fh+String1], rax
0x180030f97  test    rax, rax
0x180030f9a  jz      short loc_180030FD6
0x180030f9c  cmp     [rbp+4Fh+arg_20], esi
0x180030f9f  lea     rax, gszPhones; "Phones"
0x180030fa6  lea     r13, gszLines; "Lines"
0x180030fad  mov     rcx, r12; lpAppName
0x180030fb0  mov     rdx, r13
0x180030fb3  lea     r9, [rbp+4Fh+String1]
0x180030fb7  cmovz   rdx, rax; lpKeyName
0x180030fbb  lea     rax, [rbp+4Fh+var_B0]
0x180030fbf  mov     qword ptr [rsp+0F0h+dwFlags], rax; __int64
0x180030fc4  call    MyGetPrivateProfileString
0x180030fc9  test    eax, eax
0x180030fcb  jz      short loc_180030FFB
0x180030fcd  mov     rcx, [rbp+4Fh+String1]; lpMem
0x180030fd1  call    ServerFree
0x180030fd6  mov     eax, 80000044h
0x180030fdb  mov     rcx, [rbp+4Fh+var_50]
0x180030fdf  xor     rcx, rsp; StackCookie
0x180030fe2  call    __security_check_cookie
0x180030fe7  add     rsp, 0B8h
0x180030fee  pop     r15
0x180030ff0  pop     r14
0x180030ff2  pop     r13
0x180030ff4  pop     r12
0x180030ff6  pop     rdi
0x180030ff7  pop     rsi
0x180030ff8  pop     rbx
0x180030ff9  pop     rbp
0x180030ffa  retn
0x180030ffb  mov     [rsp+0F0h+var_B8], edi
0x180030fff  lea     rax, aDD; "%d,%d"
0x180031006  xor     r9d, r9d; pcbRemaining
0x180031009  mov     [rsp+0F0h+var_C0], ebx
0x18003100d  mov     [rsp+0F0h+pszFormat], rax; pszFormat
0x180031012  lea     r8, [rbp+4Fh+ppszDestEnd]; ppszDestEnd
0x180031016  lea     rcx, [rbp+4Fh+pszDest]; pszDest
0x18003101a  mov     qword ptr [rsp+0F0h+dwFlags], rsi; dwFlags
0x18003101f  lea     edx, [r9+40h]; cbDest
0x180031023  call    StringCbPrintfExW
0x180031028  mov     rdi, [rbp+4Fh+String1]
0x18003102c  lea     rax, [rbp+4Fh+pszDest]
0x180031030  mov     rsi, [rbp+4Fh+ppszDestEnd]
0x180031034  xor     edx, edx
0x180031036  sub     rsi, rax
0x180031039  mov     r14d, edx
0x18003103c  sar     rsi, 1
0x18003103f  mov     rbx, rdi
0x180031042  lea     ecx, [rdx+2Ch]
0x180031045  cmp     [rdi], dx
0x180031048  jz      short loc_1800310B4
0x18003104a  mov     r8d, esi; MaxCount
0x18003104d  lea     rdx, [rbp+4Fh+pszDest]; String2
0x180031051  mov     rcx, rbx; String1
0x180031054  call    wcsncmp_0
0x180031059  xor     edx, edx
0x18003105b  lea     ecx, [rdx+2Ch]
0x18003105e  test    eax, eax
0x180031060  jnz     short loc_180031078
0x180031062  mov     eax, esi
0x180031064  cmp     [rbx+rax*2], cx
0x180031068  jz      loc_18003113E
0x18003106e  cmp     [rbx+rax*2], dx
0x180031072  jz      loc_18003113E
0x180031078  mov     edx, ecx; Ch
0x18003107a  mov     rcx, rbx; Str
0x18003107d  call    cs:__imp_wcschr
0x180031083  xor     edx, edx
0x180031085  mov     rbx, rax
0x180031088  test    rax, rax
0x18003108b  jz      short loc_1800310AF
0x18003108d  mov     edx, 2Ch ; ','; Ch
0x180031092  lea     rcx, [rax+2]; Str
0x180031096  call    cs:__imp_wcschr
0x18003109c  xor     edx, edx
0x18003109e  mov     rbx, rax
0x1800310a1  test    rax, rax
0x1800310a4  jz      short loc_1800310AF
0x1800310a6  add     rbx, 2
0x1800310aa  cmp     [rbx], dx
0x1800310ad  jnz     short loc_18003104A
0x1800310af  mov     ecx, 2Ch ; ','
0x1800310b4  test    r15, r15
0x1800310b7  jz      loc_180031181
0x1800310bd  lea     r9, gszFileName; "..\\TAPI\\tsec.ini"
0x1800310c4  mov     r8, r15; lpString
0x1800310c7  lea     rdx, gszFriendlyUserName; "FriendlyUserName"
0x1800310ce  mov     rcx, r12; lpAppName
0x1800310d1  call    cs:__imp_WritePrivateProfileStringW
0x1800310d7  xor     edx, edx
0x1800310d9  test    r14d, r14d
0x1800310dc  jnz     loc_1800311C1
0x1800310e2  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800310e6  inc     rax
0x1800310e9  cmp     [rdi+rax*2], dx
0x1800310ed  jnz     short loc_1800310E6
0x1800310ef  add     eax, esi
0x1800310f1  lea     ebx, ds:4[rax*2]
0x1800310f8  cmp     ebx, dword ptr [rbp+4Fh+var_B0]
0x1800310fb  jbe     short loc_180031149
0x1800310fd  mov     rcx, cs:ghTapisrvHeap; hHeap
0x180031104  mov     edx, 8; dwFlags
0x180031109  mov     r8d, ebx; dwBytes
0x18003110c  mov     r14d, ebx
0x18003110f  call    cs:__imp_HeapAlloc
0x180031115  mov     rsi, rax
0x180031118  test    rax, rax
0x18003111b  jz      loc_180030FD6
0x180031121  mov     r8, rdi; pszSrc
0x180031124  mov     edx, r14d; cbDest
0x180031127  mov     rcx, rax; pszDest
0x18003112a  call    StringCbCopyW
0x18003112f  mov     rcx, rdi; lpMem
0x180031132  call    ServerFree
0x180031137  xor     edx, edx
0x180031139  mov     rdi, rsi
0x18003113c  jmp     short loc_18003114C
0x18003113e  mov     r14d, 1
0x180031144  jmp     loc_1800310B4
0x180031149  mov     ebx, dword ptr [rbp+4Fh+var_B0]
0x18003114c  cmp     [rdi], dx
0x18003114f  mov     rcx, rdi; pszDest
0x180031152  mov     rdx, rbx; cbDest
0x180031155  jnz     short loc_180031162
0x180031157  lea     r8, [rbp+4Fh+pszDest]; pszSrc
0x18003115b  call    StringCbCopyW
0x180031160  jmp     short loc_18003117D
0x180031162  lea     r8, asc_18004A780; ","
0x180031169  call    StringCbCatW
0x18003116e  lea     r8, [rbp+4Fh+pszDest]; pszSrc
0x180031172  mov     rdx, rbx; cbDest
0x180031175  mov     rcx, rdi; pszDest
0x180031178  call    StringCbCatW
0x18003117d  xor     edx, edx
0x18003117f  jmp     short loc_1800311C1
0x180031181  test    r14d, r14d
0x180031184  jz      short loc_1800311C1
0x180031186  mov     eax, esi
0x180031188  cmp     [rbx+rax*2], cx
0x18003118c  jnz     short loc_1800311AD
0x18003118e  lea     rcx, [rax+1]
0x180031192  lea     rcx, [rbx+rcx*2]
0x180031196  jmp     short loc_1800311A0
0x180031198  lea     rbx, [rbx+2]
0x18003119c  lea     rcx, [rcx+2]
0x1800311a0  movzx   eax, word ptr [rcx]
0x1800311a3  mov     [rbx], ax
0x1800311a6  test    ax, ax
0x1800311a9  jnz     short loc_180031198
0x1800311ab  jmp     short loc_1800311C1
0x1800311ad  cmp     [rbx+rax*2], dx
0x1800311b1  jnz     short loc_1800311C1
0x1800311b3  cmp     rbx, rdi
0x1800311b6  jnz     short loc_1800311BD
0x1800311b8  mov     [rbx], dx
0x1800311bb  jmp     short loc_1800311C1
0x1800311bd  mov     [rbx-2], dx
0x1800311c1  mov     eax, [rbp+4Fh+arg_20]
0x1800311c4  test    eax, eax
0x1800311c6  jz      short loc_1800311D6
0x1800311c8  cmp     [rdi], dx
0x1800311cb  jnz     short loc_1800311D4
0x1800311cd  xor     r8d, r8d
0x1800311d0  xor     edx, edx
0x1800311d2  jmp     short loc_1800311E7
0x1800311d4  test    eax, eax
0x1800311d6  lea     rax, gszPhones; "Phones"
0x1800311dd  mov     r8, rdi; lpString
0x1800311e0  cmovz   r13, rax
0x1800311e4  mov     rdx, r13; lpKeyName
0x1800311e7  lea     r9, gszFileName; "..\\TAPI\\tsec.ini"
0x1800311ee  mov     rcx, r12; lpAppName
0x1800311f1  call    cs:__imp_WritePrivateProfileStringW
0x1800311f7  mov     rcx, rdi; lpMem
0x1800311fa  call    ServerFree
0x1800311ff  xor     eax, eax
0x180031201  jmp     loc_180030FDB
```
