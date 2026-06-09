# GetDirectory

- ea: `0x180021ffc`
- end: `0x180022186`
- name: `GetDirectory`
- size: `394`
- prototype: `__int64 __fastcall(STRSAFE_LPSTR pszDest)`
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x18002231c`
- `0x18002252c`

## callees

- `0x18001ba0c`
- `0x18001f3e4`
- `0x18001f440`
- `0x180021ffc`
- `0x18002a566`
- `0x18002a590`

## import_xrefs

- `KERNEL32!GetWindowsDirectoryA` at `0x180022043`
- `KERNEL32!GetWindowsDirectoryA` at `0x18002211c`
- `KERNEL32!GetWindowsDirectoryA` at `0x180022043`
- `KERNEL32!GetWindowsDirectoryA` at `0x18002211c`
- `KERNEL32!OpenFile` at `0x1800220f4`
- `KERNEL32!OpenFile` at `0x1800220f4`
- `KERNEL32!DeleteFileA` at `0x18002210f`
- `KERNEL32!DeleteFileA` at `0x18002210f`
- `KERNEL32!_lclose` at `0x180022101`
- `KERNEL32!_lclose` at `0x180022101`

## pseudocode

```c
__int64 __fastcall GetDirectory(STRSAFE_LPSTR pszDest)
{
  HFILE v2; // eax
  size_t pcchLength[2]; // [rsp+20h] [rbp-1C8h] BYREF
  struct _OFSTRUCT ReOpenBuff; // [rsp+30h] [rbp-1B8h] BYREF
  char pszDesta[272]; // [rsp+C0h] [rbp-128h] BYREF

  memset_0(&ReOpenBuff, 0, sizeof(ReOpenBuff));
  pcchLength[0] = 0;
  if ( GetWindowsDirectoryA(pszDest, 0x104u)
    && StringCchLengthA(pszDest, 0x104u, pcchLength) >= 0
    && (pszDest[pcchLength[0] - 1] == 92 || StringCchCatA(pszDest, 0x104u, "\\") >= 0)
    && StringCchCatA(pszDest, 0x104u, "fonts\\") >= 0
    && StringCchCopyA(pszDesta, 0x104u, pszDest) >= 0
    && StringCchCatA(pszDesta, 0x104u, "NUL") >= 0 )
  {
    v2 = OpenFile(pszDesta, &ReOpenBuff, 0x1001u);
    if ( v2 != -1 )
    {
      _lclose(v2);
      DeleteFileA(pszDesta);
      return 1;
    }
    if ( GetWindowsDirectoryA(pszDest, 0x104u)
      && StringCchLengthA(pszDest, 0x104u, pcchLength) >= 0
      && (pszDest[pcchLength[0] - 1] == 92 || StringCchCatA(pszDest, 0x104u, "\\") >= 0) )
    {
      return 1;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180021ffc  mov     [rsp+arg_8], rbx
0x180022001  push    rdi
0x180022002  sub     rsp, 1E0h
0x180022009  mov     rax, cs:__security_cookie
0x180022010  xor     rax, rsp
0x180022013  mov     [rsp+1E8h+var_18], rax
0x18002201b  mov     rbx, rcx
0x18002201e  xor     edx, edx; Val
0x180022020  lea     rcx, [rsp+1E8h+ReOpenBuff]; void *
0x180022025  mov     r8d, 88h; Size
0x18002202b  call    memset_0
0x180022030  mov     edi, 104h
0x180022035  mov     [rsp+1E8h+pcchLength], 0
0x18002203e  mov     edx, edi; uSize
0x180022040  mov     rcx, rbx; lpBuffer
0x180022043  call    cs:__imp_GetWindowsDirectoryA
0x180022049  test    eax, eax
0x18002204b  jz      loc_180022163
0x180022051  lea     r8, [rsp+1E8h+pcchLength]; pcchLength
0x180022056  mov     edx, edi; cchMax
0x180022058  mov     rcx, rbx; psz
0x18002205b  call    StringCchLengthA
0x180022060  test    eax, eax
0x180022062  js      loc_180022163
0x180022068  mov     rax, [rsp+1E8h+pcchLength]
0x18002206d  cmp     byte ptr [rbx+rax-1], 5Ch ; '\'
0x180022072  jz      short loc_18002208D
0x180022074  lea     r8, asc_18002C930; "\\"
0x18002207b  mov     edx, edi; cchDest
0x18002207d  mov     rcx, rbx; pszDest
0x180022080  call    StringCchCatA
0x180022085  test    eax, eax
0x180022087  js      loc_180022163
0x18002208d  lea     r8, aFonts; "fonts\\"
0x180022094  mov     rdx, rdi; cchDest
0x180022097  mov     rcx, rbx; pszDest
0x18002209a  call    StringCchCatA
0x18002209f  test    eax, eax
0x1800220a1  js      loc_180022163
0x1800220a7  mov     r8, rbx; pszSrc
0x1800220aa  lea     rcx, [rsp+1E8h+pszDest]; pszDest
0x1800220b2  mov     rdx, rdi; cchDest
0x1800220b5  call    StringCchCopyA
0x1800220ba  test    eax, eax
0x1800220bc  js      loc_180022163
0x1800220c2  lea     r8, aNul; "NUL"
0x1800220c9  mov     rdx, rdi; cchDest
0x1800220cc  lea     rcx, [rsp+1E8h+pszDest]; pszDest
0x1800220d4  call    StringCchCatA
0x1800220d9  test    eax, eax
0x1800220db  js      loc_180022163
0x1800220e1  mov     r8d, 1001h; uStyle
0x1800220e7  lea     rdx, [rsp+1E8h+ReOpenBuff]; lpReOpenBuff
0x1800220ec  lea     rcx, [rsp+1E8h+pszDest]; lpFileName
0x1800220f4  call    cs:__imp_OpenFile
0x1800220fa  cmp     eax, 0FFFFFFFFh
0x1800220fd  jz      short loc_180022117
0x1800220ff  mov     ecx, eax; hFile
0x180022101  call    cs:__imp__lclose
0x180022107  lea     rcx, [rsp+1E8h+pszDest]; lpFileName
0x18002210f  call    cs:__imp_DeleteFileA
0x180022115  jmp     short loc_18002215C
0x180022117  mov     edx, edi; uSize
0x180022119  mov     rcx, rbx; lpBuffer
0x18002211c  call    cs:__imp_GetWindowsDirectoryA
0x180022122  test    eax, eax
0x180022124  jz      short loc_180022163
0x180022126  lea     r8, [rsp+1E8h+pcchLength]; pcchLength
0x18002212b  mov     rdx, rdi; cchMax
0x18002212e  mov     rcx, rbx; psz
0x180022131  call    StringCchLengthA
0x180022136  test    eax, eax
0x180022138  js      short loc_180022163
0x18002213a  mov     rax, [rsp+1E8h+pcchLength]
0x18002213f  cmp     byte ptr [rbx+rax-1], 5Ch ; '\'
0x180022144  jz      short loc_18002215C
0x180022146  lea     r8, asc_18002C930; "\\"
0x18002214d  mov     rdx, rdi; cchDest
0x180022150  mov     rcx, rbx; pszDest
0x180022153  call    StringCchCatA
0x180022158  test    eax, eax
0x18002215a  js      short loc_180022163
0x18002215c  mov     eax, 1
0x180022161  jmp     short loc_180022165
0x180022163  xor     eax, eax
0x180022165  mov     rcx, [rsp+1E8h+var_18]
0x18002216d  xor     rcx, rsp; StackCookie
0x180022170  call    __security_check_cookie
0x180022175  mov     rbx, [rsp+1E8h+arg_8]
0x18002217d  add     rsp, 1E0h
0x180022184  pop     rdi
0x180022185  retn
```
