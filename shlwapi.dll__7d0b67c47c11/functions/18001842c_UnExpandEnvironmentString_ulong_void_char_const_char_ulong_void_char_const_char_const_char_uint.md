# _UnExpandEnvironmentString(ulong (*)(void *,char const *,char *,ulong),void *,char const *,char const *,char *,uint)

- ea: `0x18001842c`
- end: `0x18001850c`
- name: `?_UnExpandEnvironmentString@@YAHP6AKPEAXPEBDPEADK@Z0112I@Z`
- size: `224`
- prototype: `int(unsigned int (*)(void *, const char *, char *, unsigned int), void *, const char *, const char *, char *, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1800182dc`

## callees

- `0x180012550`
- `0x180017344`
- `0x180018204`
- `0x18001842c`
- `0x18001cb60`

## import_xrefs

- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenA` at `0x1800184a0`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenA` at `0x1800184ad`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenA` at `0x1800184a0`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenA` at `0x1800184ad`
- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x180018492`
- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x180018492`

## pseudocode

```c
__int64 __fastcall _UnExpandEnvironmentString(
        unsigned int (*a1)(void *, const char *, char *, unsigned int),
        void *a2,
        const char *a3,
        const char *a4,
        char *pszDest,
        int cchDest)
{
  int v8; // eax
  int v9; // edi
  int v10; // ebx
  unsigned int v11; // r10d
  CHAR String1[272]; // [rsp+30h] [rbp-148h] BYREF

  v8 = SHExpandEnvironmentStringsForUserA(a2, a4, String1, 260);
  if ( !v8 )
    return 0;
  v9 = v8 - 1;
  if ( CompareStringA(0x800u, 0x10000001u, String1, v8 - 1, a3, v8 - 1) != 2 )
    return 0;
  v10 = lstrlenA(a3) - v9;
  if ( v10 + lstrlenA(a4) >= cchDest )
    return 0;
  StringCchCopyA(pszDest, (unsigned int)cchDest, a4);
  StringCchCatA(pszDest, v11, &a3[v9]);
  return 1;
}

```

## disassembly

```asm
0x18001842c  push    rbx
0x18001842e  push    rbp
0x18001842f  push    rsi
0x180018430  push    rdi
0x180018431  push    r14
0x180018433  sub     rsp, 150h
0x18001843a  mov     rax, cs:__security_cookie
0x180018441  xor     rax, rsp
0x180018444  mov     [rsp+178h+var_38], rax
0x18001844c  mov     r14, [rsp+178h+pszDest]
0x180018454  mov     rbp, r9
0x180018457  mov     rsi, r8
0x18001845a  mov     rcx, rdx
0x18001845d  mov     rdx, rbp
0x180018460  lea     r8, [rsp+178h+String1]
0x180018465  mov     r9d, 104h
0x18001846b  call    SHExpandEnvironmentStringsForUserA
0x180018470  test    eax, eax
0x180018472  jz      short loc_1800184EC
0x180018474  lea     edi, [rax-1]
0x180018477  mov     edx, 10000001h; dwCmpFlags
0x18001847c  mov     [rsp+178h+cchCount2], edi; cchCount2
0x180018480  lea     r8, [rsp+178h+String1]; lpString1
0x180018485  mov     r9d, edi; cchCount1
0x180018488  mov     [rsp+178h+lpString2], rsi; lpString2
0x18001848d  mov     ecx, 800h; Locale
0x180018492  call    cs:__imp_CompareStringA
0x180018498  cmp     eax, 2
0x18001849b  jnz     short loc_1800184EC
0x18001849d  mov     rcx, rsi; lpString
0x1800184a0  call    cs:__imp_lstrlenA
0x1800184a6  mov     ebx, eax
0x1800184a8  mov     rcx, rbp; lpString
0x1800184ab  sub     ebx, edi
0x1800184ad  call    cs:__imp_lstrlenA
0x1800184b3  add     eax, ebx
0x1800184b5  cmp     eax, dword ptr [rsp+178h+cchDest]
0x1800184bc  jge     short loc_1800184EC
0x1800184be  mov     r10d, dword ptr [rsp+178h+cchDest]
0x1800184c6  mov     r8, rbp; pszSrc
0x1800184c9  mov     edx, r10d; cchDest
0x1800184cc  mov     rcx, r14; pszDest
0x1800184cf  call    StringCchCopyA
0x1800184d4  mov     r8d, edi
0x1800184d7  mov     edx, r10d; unsigned __int64
0x1800184da  add     r8, rsi; char *
0x1800184dd  mov     rcx, r14; char *
0x1800184e0  call    ?StringCchCatA@@YAJPEAD_KPEBD@Z; StringCchCatA(char *,unsigned __int64,char const *)
0x1800184e5  mov     eax, 1
0x1800184ea  jmp     short loc_1800184EE
0x1800184ec  xor     eax, eax
0x1800184ee  mov     rcx, [rsp+178h+var_38]
0x1800184f6  xor     rcx, rsp; StackCookie
0x1800184f9  call    __security_check_cookie
0x1800184fe  add     rsp, 150h
0x180018505  pop     r14
0x180018507  pop     rdi
0x180018508  pop     rsi
0x180018509  pop     rbp
0x18001850a  pop     rbx
0x18001850b  retn
```
