# TTDeleteEmbeddedFont

- ea: `0x18001f620`
- end: `0x18001f822`
- name: `TTDeleteEmbeddedFont`
- size: `514`
- prototype: `LONG __stdcall(HANDLE hFontReference, ULONG ulFlags, ULONG *pulStatus)`
- caller_count: `0`
- callee_count: `7`
- tags: `file_ops`

## callees

- `0x180019dc0`
- `0x18001ba0c`
- `0x18001f620`
- `0x180022770`
- `0x180023224`
- `0x18002a566`
- `0x18002a590`

## import_xrefs

- `KERNEL32!DeleteFileA` at `0x18001f7e2`
- `KERNEL32!DeleteFileA` at `0x18001f7e2`

## pseudocode

```c
LONG __stdcall TTDeleteEmbeddedFont(HANDLE hFontReference, ULONG ulFlags, ULONG *pulStatus)
{
  void *v7; // rcx
  void *v8; // rcx
  unsigned int v9; // r10d
  unsigned int v10; // r10d
  int v11; // r11d
  unsigned int v12; // r10d
  __int64 v13; // rcx
  int v14; // r11d
  char pszDest[260]; // [rsp+30h] [rbp-3E8h] BYREF
  char v16[260]; // [rsp+134h] [rbp-2E4h] BYREF
  CHAR FileName[260]; // [rsp+238h] [rbp-1E0h] BYREF
  char v18[64]; // [rsp+33Ch] [rbp-DCh] BYREF
  CHAR ValueName[64]; // [rsp+37Ch] [rbp-9Ch] BYREF
  int v20; // [rsp+3BCh] [rbp-5Ch]
  int v21; // [rsp+3C0h] [rbp-58h]
  __int64 v22; // [rsp+3C8h] [rbp-50h]
  int v23; // [rsp+3D0h] [rbp-48h]
  int v24; // [rsp+3E0h] [rbp-38h]

  memset_0(pszDest, 0, 0x3B8u);
  v24 = 0;
  if ( !hFontReference )
    return 8;
  if ( (ulFlags & 0xFFFFFFFE) != 0 )
    return 268;
  v7 = (void *)*((_QWORD *)hFontReference + 117);
  if ( v7 )
    T2free(v7);
  *((_QWORD *)hFontReference + 117) = 0;
  v8 = (void *)*((_QWORD *)hFontReference + 118);
  if ( v8 )
    T2free(v8);
  *((_QWORD *)hFontReference + 118) = 0;
  if ( (ulFlags & 1) == 0 || !*((_DWORD *)hFontReference + 233) )
  {
    StringCchCopyA(pszDest, 0x104u, (STRSAFE_LPCSTR)hFontReference);
    StringCchCopyA(v16, v9, (STRSAFE_LPCSTR)hFontReference + 260);
    StringCchCopyA(FileName, v10, (STRSAFE_LPCSTR)hFontReference + 520);
    StringCchCopyA(v18, (unsigned int)(v11 + 64), (STRSAFE_LPCSTR)hFontReference + 780);
    StringCchCopyA(ValueName, v12, (STRSAFE_LPCSTR)hFontReference + 844);
    v20 = *((_DWORD *)hFontReference + 227);
    v21 = *((_DWORD *)hFontReference + 228);
    v22 = *((_QWORD *)hFontReference + 115);
    v23 = *((_DWORD *)hFontReference + 232);
    if ( *((_DWORD *)hFontReference + 233) != v14 )
      LOBYTE(v14) = 1;
    if ( pulStatus )
      *pulStatus = 0;
    T2OSSvcRemoveFont(v13, v14 & 1, (__int64)pszDest);
    if ( v21 )
    {
      RemoveEUDCRegEntry(ValueName, v23);
      DeleteFileA(FileName);
    }
  }
  T2free(hFontReference);
  return 0;
}

```

## disassembly

```asm
0x18001f620  mov     [rsp+arg_8], rbx
0x18001f625  mov     [rsp+arg_18], rsi
0x18001f62a  push    rdi
0x18001f62b  push    r12
0x18001f62d  push    r14
0x18001f62f  sub     rsp, 400h
0x18001f636  mov     rax, cs:__security_cookie
0x18001f63d  xor     rax, rsp
0x18001f640  mov     [rsp+418h+var_28], rax
0x18001f648  mov     r14, r8
0x18001f64b  mov     esi, edx
0x18001f64d  mov     rbx, rcx
0x18001f650  xor     edi, edi
0x18001f652  xor     edx, edx; Val
0x18001f654  mov     r8d, 3B8h; Size
0x18001f65a  lea     rcx, [rsp+418h+pszDest]; void *
0x18001f65f  call    memset_0
0x18001f664  mov     [rsp+418h+var_38], edi
0x18001f66b  test    rbx, rbx
0x18001f66e  jnz     short loc_18001F678
0x18001f670  lea     eax, [rdi+8]
0x18001f673  jmp     loc_18001F7F9
0x18001f678  test    esi, 0FFFFFFFEh
0x18001f67e  jz      short loc_18001F68A
0x18001f680  mov     eax, 10Ch
0x18001f685  jmp     loc_18001F7F9
0x18001f68a  mov     rcx, [rbx+3A8h]; lpMem
0x18001f691  test    rcx, rcx
0x18001f694  jz      short loc_18001F69B
0x18001f696  call    T2free
0x18001f69b  mov     qword ptr [rbx+3A8h], 0
0x18001f6a6  mov     rcx, [rbx+3B0h]; lpMem
0x18001f6ad  test    rcx, rcx
0x18001f6b0  jz      short loc_18001F6B7
0x18001f6b2  call    T2free
0x18001f6b7  mov     qword ptr [rbx+3B0h], 0
0x18001f6c2  mov     r12d, 1
0x18001f6c8  test    r12b, sil
0x18001f6cb  jz      short loc_18001F6DA
0x18001f6cd  cmp     dword ptr [rbx+3A4h], 0
0x18001f6d4  jnz     loc_18001F7E8
0x18001f6da  xor     r11d, r11d
0x18001f6dd  mov     [rsp+418h+var_3F8], r11d
0x18001f6e2  mov     r8, rbx; pszSrc
0x18001f6e5  mov     r10d, 104h
0x18001f6eb  mov     edx, r10d; cchDest
0x18001f6ee  lea     rcx, [rsp+418h+pszDest]; pszDest
0x18001f6f3  call    StringCchCopyA
0x18001f6f8  lea     r8, [rbx+104h]; pszSrc
0x18001f6ff  mov     edx, r10d; cchDest
0x18001f702  lea     rcx, [rsp+418h+var_2E4]; pszDest
0x18001f70a  call    StringCchCopyA
0x18001f70f  lea     r8, [rbx+208h]; pszSrc
0x18001f716  mov     edx, r10d; cchDest
0x18001f719  lea     rcx, [rsp+418h+FileName]; pszDest
0x18001f721  call    StringCchCopyA
0x18001f726  lea     r8, [rbx+30Ch]; pszSrc
0x18001f72d  lea     r10d, [r11+40h]
0x18001f731  mov     edx, r10d; cchDest
0x18001f734  lea     rcx, [rsp+418h+var_DC]; pszDest
0x18001f73c  call    StringCchCopyA
0x18001f741  lea     r8, [rbx+34Ch]; pszSrc
0x18001f748  mov     edx, r10d; cchDest
0x18001f74b  lea     rcx, [rsp+418h+ValueName]; pszDest
0x18001f753  call    StringCchCopyA
0x18001f758  mov     r10d, [rbx+38Ch]
0x18001f75f  mov     [rsp+418h+var_5C], r10d
0x18001f767  mov     eax, [rbx+390h]
0x18001f76d  mov     [rsp+418h+var_58], eax
0x18001f774  mov     rax, [rbx+398h]
0x18001f77b  mov     [rsp+418h+var_50], rax
0x18001f783  mov     eax, [rbx+3A0h]
0x18001f789  mov     [rsp+418h+var_48], eax
0x18001f790  cmp     [rbx+3A4h], r11d
0x18001f797  cmovnz  r11d, r12d
0x18001f79b  mov     [rsp+418h+var_3F8], r11d
0x18001f7a0  test    r14, r14
0x18001f7a3  jz      short loc_18001F7AC
0x18001f7a5  mov     dword ptr [r14], 0
0x18001f7ac  and     r11d, r12d
0x18001f7af  lea     r8, [rsp+418h+pszDest]
0x18001f7b4  mov     edx, r11d
0x18001f7b7  call    T2OSSvcRemoveFont
0x18001f7bc  cmp     [rsp+418h+var_58], 0
0x18001f7c4  jz      short loc_18001F7E8
0x18001f7c6  mov     edx, [rsp+418h+var_48]
0x18001f7cd  lea     rcx, [rsp+418h+ValueName]; lpValueName
0x18001f7d5  call    RemoveEUDCRegEntry
0x18001f7da  lea     rcx, [rsp+418h+FileName]; lpFileName
0x18001f7e2  call    cs:__imp_DeleteFileA
0x18001f7e8  mov     rcx, rbx; lpMem
0x18001f7eb  call    T2free
0x18001f7f0  jmp     short loc_18001F7F7
0x18001f7f2  mov     edi, 13h
0x18001f7f7  mov     eax, edi
0x18001f7f9  mov     rcx, [rsp+418h+var_28]
0x18001f801  xor     rcx, rsp; StackCookie
0x18001f804  call    __security_check_cookie
0x18001f809  lea     r11, [rsp+418h+var_18]
0x18001f811  mov     rbx, [r11+28h]
0x18001f815  mov     rsi, [r11+38h]
0x18001f819  mov     rsp, r11
0x18001f81c  pop     r14
0x18001f81e  pop     r12
0x18001f820  pop     rdi
0x18001f821  retn
```
