# FixFontPath

- ea: `0x18001edf0`
- end: `0x18001ef07`
- name: `FixFontPath`
- size: `279`
- prototype: `__int64 __fastcall(STRSAFE_LPSTR pszDest)`
- caller_count: `1`
- callee_count: `5`
- tags: `reparse_path`

## callers

- `0x18001ef44`

## callees

- `0x18001ba0c`
- `0x18001edf0`
- `0x18001f3e4`
- `0x18001f440`
- `0x18002a590`

## import_xrefs

- `KERNEL32!GetWindowsDirectoryA` at `0x18001ee6b`
- `KERNEL32!GetWindowsDirectoryA` at `0x18001ee6b`

## pseudocode

```c
__int64 __fastcall FixFontPath(STRSAFE_LPSTR pszDest)
{
  char *v1; // rbx
  unsigned __int64 v2; // rax
  __int64 v3; // rdx
  size_t pcchLength[2]; // [rsp+20h] [rbp-138h] BYREF
  CHAR Buffer[272]; // [rsp+30h] [rbp-128h] BYREF

  v1 = pszDest;
  if ( pszDest )
  {
    v2 = -1;
    do
      ++v2;
    while ( pszDest[v2] );
    if ( v2 )
    {
      while ( *pszDest )
      {
        LOBYTE(v2) = *pszDest - 47;
        if ( (unsigned __int8)v2 <= 0x2Du )
        {
          v3 = 0x200000000801LL;
          if ( _bittest64(&v3, v2) )
            return 1;
        }
        ++pszDest;
      }
      pcchLength[0] = 0;
      if ( GetWindowsDirectoryA(Buffer, 0x104u) && StringCchLengthA(Buffer, 0x104u, pcchLength) >= 0 )
      {
        if ( Buffer[pcchLength[0]] != 92 )
          StringCchCatA(Buffer, 0x104u, "\\");
        StringCchCatA(Buffer, 0x104u, "fonts\\");
        StringCchCatA(Buffer, 0x104u, v1);
        StringCchCopyA(v1, 0x104u, Buffer);
        return 1;
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18001edf0  mov     [rsp+arg_8], rbx
0x18001edf5  push    rdi
0x18001edf6  sub     rsp, 150h
0x18001edfd  mov     rax, cs:__security_cookie
0x18001ee04  xor     rax, rsp
0x18001ee07  mov     [rsp+158h+var_18], rax
0x18001ee0f  mov     rbx, rcx
0x18001ee12  test    rcx, rcx
0x18001ee15  jz      loc_18001EEE4
0x18001ee1b  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001ee1f  inc     rax
0x18001ee22  cmp     byte ptr [rcx+rax], 0
0x18001ee26  jnz     short loc_18001EE1F
0x18001ee28  test    rax, rax
0x18001ee2b  jz      loc_18001EEE4
0x18001ee31  mov     al, [rcx]
0x18001ee33  test    al, al
0x18001ee35  jz      short loc_18001EE56
0x18001ee37  sub     al, 2Fh ; '/'
0x18001ee39  cmp     al, 2Dh ; '-'
0x18001ee3b  ja      short loc_18001EE51
0x18001ee3d  mov     rdx, 200000000801h
0x18001ee47  bt      rdx, rax
0x18001ee4b  jb      loc_18001EEDD
0x18001ee51  inc     rcx
0x18001ee54  jmp     short loc_18001EE31
0x18001ee56  mov     edi, 104h
0x18001ee5b  mov     [rsp+158h+pcchLength], 0
0x18001ee64  mov     edx, edi; uSize
0x18001ee66  lea     rcx, [rsp+158h+Buffer]; lpBuffer
0x18001ee6b  call    cs:__imp_GetWindowsDirectoryA
0x18001ee71  test    eax, eax
0x18001ee73  jz      short loc_18001EEE4
0x18001ee75  lea     r8, [rsp+158h+pcchLength]; pcchLength
0x18001ee7a  mov     edx, edi; cchMax
0x18001ee7c  lea     rcx, [rsp+158h+Buffer]; psz
0x18001ee81  call    StringCchLengthA
0x18001ee86  test    eax, eax
0x18001ee88  js      short loc_18001EEE4
0x18001ee8a  mov     rax, [rsp+158h+pcchLength]
0x18001ee8f  cmp     [rsp+rax+158h+Buffer], 5Ch ; '\'
0x18001ee94  jz      short loc_18001EEA9
0x18001ee96  lea     r8, asc_18002C930; "\\"
0x18001ee9d  mov     edx, edi; cchDest
0x18001ee9f  lea     rcx, [rsp+158h+Buffer]; pszDest
0x18001eea4  call    StringCchCatA
0x18001eea9  lea     r8, aFonts; "fonts\\"
0x18001eeb0  mov     rdx, rdi; cchDest
0x18001eeb3  lea     rcx, [rsp+158h+Buffer]; pszDest
0x18001eeb8  call    StringCchCatA
0x18001eebd  mov     r8, rbx; pszSrc
0x18001eec0  lea     rcx, [rsp+158h+Buffer]; pszDest
0x18001eec5  mov     rdx, rdi; cchDest
0x18001eec8  call    StringCchCatA
0x18001eecd  lea     r8, [rsp+158h+Buffer]; pszSrc
0x18001eed2  mov     rdx, rdi; cchDest
0x18001eed5  mov     rcx, rbx; pszDest
0x18001eed8  call    StringCchCopyA
0x18001eedd  mov     eax, 1
0x18001eee2  jmp     short loc_18001EEE6
0x18001eee4  xor     eax, eax
0x18001eee6  mov     rcx, [rsp+158h+var_18]
0x18001eeee  xor     rcx, rsp; StackCookie
0x18001eef1  call    __security_check_cookie
0x18001eef6  mov     rbx, [rsp+158h+arg_8]
0x18001eefe  add     rsp, 150h
0x18001ef05  pop     rdi
0x18001ef06  retn
```
