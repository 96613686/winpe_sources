# GetUniqueFileName

- ea: `0x18002218c`
- end: `0x180022316`
- name: `GetUniqueFileName`
- size: `394`
- prototype: `__int64 __fastcall(STRSAFE_LPCSTR pszSrc, STRSAFE_LPCSTR, STRSAFE_LPCSTR, LPCSTR lpFileName)`
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x18002231c`
- `0x18002252c`

## callees

- `0x18001ba0c`
- `0x18001f3e4`
- `0x18001f440`
- `0x18002218c`
- `0x18002a566`
- `0x18002a590`

## import_xrefs

- `KERNEL32!OpenFile` at `0x18002229f`
- `KERNEL32!OpenFile` at `0x18002229f`

## pseudocode

```c
__int64 __fastcall GetUniqueFileName(STRSAFE_LPCSTR pszSrc, STRSAFE_LPCSTR a2, STRSAFE_LPCSTR a3, char *lpFileName)
{
  __int16 v8; // bx
  const CHAR *v9; // r14
  __int64 v10; // r15
  char *v11; // rsi
  const char *v12; // rbx
  int v13; // ebp
  CHAR v14; // al
  size_t pcchLength[2]; // [rsp+20h] [rbp-E8h] BYREF
  struct _OFSTRUCT ReOpenBuff; // [rsp+30h] [rbp-D8h] BYREF

  memset_0(&ReOpenBuff, 0, sizeof(ReOpenBuff));
  pcchLength[0] = 0;
  if ( StringCchCopyA(lpFileName, 0x104u, pszSrc) < 0 )
    return 513;
  if ( StringCchCatA(lpFileName, 0x104u, a2) < 0 )
    return 513;
  if ( StringCchLengthA(lpFileName, 0x104u, pcchLength) < 0 )
    return 513;
  v8 = pcchLength[0];
  if ( pcchLength[0] < 3 || StringCchCatA(lpFileName, 0x104u, ".") < 0 || StringCchCatA(lpFileName, 0x104u, a3) < 0 )
    return 513;
  v9 = "0123456789ABCDEFGHIJKLMNOPQRSTUVWXYZ";
  v10 = (unsigned __int16)(v8 - 3);
  v11 = "123456789ABCDEFGHIJKLMNOPQRSTUVWXYZ";
  v12 = "0123456789ABCDEFGHIJKLMNOPQRSTUVWXYZ";
  v13 = 0;
  *(_WORD *)&lpFileName[v10] = 12336;
  lpFileName[v10 + 2] = 48;
  while ( !v13 )
  {
    if ( OpenFile(lpFileName, &ReOpenBuff, 0x4040u) == -1 )
    {
      v13 = 1;
    }
    else
    {
      if ( !*v11 )
      {
        ++v12;
        v11 = "0123456789ABCDEFGHIJKLMNOPQRSTUVWXYZ";
        if ( !*v12 )
        {
          if ( !*++v9 )
            return 513;
          v12 = "0123456789ABCDEFGHIJKLMNOPQRSTUVWXYZ";
        }
      }
      lpFileName[v10] = *v9;
      lpFileName[v10 + 1] = *v12;
      v14 = *v11++;
      lpFileName[v10 + 2] = v14;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18002218c  push    rbx
0x18002218e  push    rbp
0x18002218f  push    rsi
0x180022190  push    rdi
0x180022191  push    r14
0x180022193  push    r15
0x180022195  sub     rsp, 0D8h
0x18002219c  mov     rax, cs:__security_cookie
0x1800221a3  xor     rax, rsp
0x1800221a6  mov     [rsp+108h+var_48], rax
0x1800221ae  mov     rbp, r8
0x1800221b1  mov     rsi, rdx
0x1800221b4  mov     rbx, rcx
0x1800221b7  xor     edx, edx; Val
0x1800221b9  mov     r8d, 88h; Size
0x1800221bf  lea     rcx, [rsp+108h+ReOpenBuff]; void *
0x1800221c4  mov     rdi, r9
0x1800221c7  call    memset_0
0x1800221cc  mov     r14d, 104h
0x1800221d2  mov     [rsp+108h+pcchLength], 0
0x1800221db  mov     edx, r14d; cchDest
0x1800221de  mov     r8, rbx; pszSrc
0x1800221e1  mov     rcx, rdi; pszDest
0x1800221e4  call    StringCchCopyA
0x1800221e9  test    eax, eax
0x1800221eb  js      loc_1800222F1
0x1800221f1  mov     r8, rsi; pszSrc
0x1800221f4  mov     edx, r14d; cchDest
0x1800221f7  mov     rcx, rdi; pszDest
0x1800221fa  call    StringCchCatA
0x1800221ff  test    eax, eax
0x180022201  js      loc_1800222F1
0x180022207  lea     r8, [rsp+108h+pcchLength]; pcchLength
0x18002220c  mov     edx, r14d; cchMax
0x18002220f  mov     rcx, rdi; psz
0x180022212  call    StringCchLengthA
0x180022217  test    eax, eax
0x180022219  js      loc_1800222F1
0x18002221f  mov     rbx, [rsp+108h+pcchLength]
0x180022224  mov     esi, 3
0x180022229  cmp     rbx, rsi
0x18002222c  jb      loc_1800222F1
0x180022232  lea     r8, asc_18002CA40; "."
0x180022239  mov     edx, r14d; cchDest
0x18002223c  mov     rcx, rdi; pszDest
0x18002223f  call    StringCchCatA
0x180022244  test    eax, eax
0x180022246  js      loc_1800222F1
0x18002224c  mov     r8, rbp; pszSrc
0x18002224f  mov     edx, r14d; cchDest
0x180022252  mov     rcx, rdi; pszDest
0x180022255  call    StringCchCatA
0x18002225a  test    eax, eax
0x18002225c  js      loc_1800222F1
0x180022262  sub     bx, si
0x180022265  lea     r14, a0123456789abcd; "0123456789ABCDEFGHIJKLMNOPQRSTUVWXYZ"
0x18002226c  movzx   r15d, bx
0x180022270  lea     rsi, a0123456789abcd+1; "123456789ABCDEFGHIJKLMNOPQRSTUVWXYZ"
0x180022277  lea     rbx, a0123456789abcd; "0123456789ABCDEFGHIJKLMNOPQRSTUVWXYZ"
0x18002227e  xor     ebp, ebp
0x180022280  mov     word ptr [r15+rdi], 3030h
0x180022287  mov     byte ptr [r15+rdi+2], 30h ; '0'
0x18002228d  test    ebp, ebp
0x18002228f  jnz     short loc_1800222ED
0x180022291  mov     r8d, 4040h; uStyle
0x180022297  lea     rdx, [rsp+108h+ReOpenBuff]; lpReOpenBuff
0x18002229c  mov     rcx, rdi; lpFileName
0x18002229f  call    cs:__imp_OpenFile
0x1800222a5  cmp     eax, 0FFFFFFFFh
0x1800222a8  jnz     short loc_1800222AF
0x1800222aa  lea     ebp, [rax+2]
0x1800222ad  jmp     short loc_18002228D
0x1800222af  cmp     byte ptr [rsi], 0
0x1800222b2  jnz     short loc_1800222D3
0x1800222b4  inc     rbx
0x1800222b7  lea     rsi, a0123456789abcd; "0123456789ABCDEFGHIJKLMNOPQRSTUVWXYZ"
0x1800222be  cmp     byte ptr [rbx], 0
0x1800222c1  jnz     short loc_1800222D3
0x1800222c3  inc     r14
0x1800222c6  cmp     byte ptr [r14], 0
0x1800222ca  jz      short loc_1800222F1
0x1800222cc  lea     rbx, a0123456789abcd; "0123456789ABCDEFGHIJKLMNOPQRSTUVWXYZ"
0x1800222d3  mov     al, [r14]
0x1800222d6  mov     [r15+rdi], al
0x1800222da  mov     al, [rbx]
0x1800222dc  mov     [r15+rdi+1], al
0x1800222e1  mov     al, [rsi]
0x1800222e3  inc     rsi
0x1800222e6  mov     [r15+rdi+2], al
0x1800222eb  jmp     short loc_18002228D
0x1800222ed  xor     eax, eax
0x1800222ef  jmp     short loc_1800222F6
0x1800222f1  mov     eax, 201h
0x1800222f6  mov     rcx, [rsp+108h+var_48]
0x1800222fe  xor     rcx, rsp; StackCookie
0x180022301  call    __security_check_cookie
0x180022306  add     rsp, 0D8h
0x18002230d  pop     r15
0x18002230f  pop     r14
0x180022311  pop     rdi
0x180022312  pop     rsi
0x180022313  pop     rbp
0x180022314  pop     rbx
0x180022315  retn
```
