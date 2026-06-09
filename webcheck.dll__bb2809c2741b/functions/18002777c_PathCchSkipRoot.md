# PathCchSkipRoot

- ea: `0x18002777c`
- end: `0x1800278c3`
- name: `PathCchSkipRoot`
- size: `327`
- prototype: `HRESULT __stdcall(PCWSTR pszPath, PCWSTR *ppszRootEnd)`
- caller_count: `1`
- callee_count: `4`
- tags: `reparse_path`

## callers

- `0x1800278cc`

## callees

- `0x180025960`
- `0x180026684`
- `0x18002671c`
- `0x18002777c`

## import_xrefs

- `msvcrt!wcschr` at `0x1800277d9`
- `msvcrt!wcschr` at `0x1800277f0`
- `msvcrt!wcschr` at `0x1800277d9`
- `msvcrt!wcschr` at `0x1800277f0`
- `msvcrt!iswalpha` at `0x180027887`
- `msvcrt!iswalpha` at `0x180027887`

## pseudocode

```c
HRESULT __stdcall PathCchSkipRoot(PCWSTR pszPath, PCWSTR *ppszRootEnd)
{
  wchar_t *v4; // rsi
  wchar_t *v5; // rax
  wchar_t *v6; // rbx
  wchar_t *v7; // rsi
  wchar_t *v8; // rax
  const WCHAR *v9; // rbx
  __int64 v10; // rax
  __int64 v11; // rax
  WCHAR v12; // bp
  __int64 v13; // rax
  bool v14; // al
  PCWSTR v15; // rsi
  __int64 v16; // rbx
  wchar_t *Str; // [rsp+60h] [rbp+8h] BYREF

  Str = 0;
  if ( pszPath && *pszPath && ppszRootEnd )
  {
    *ppszRootEnd = 0;
    if ( (unsigned int)PathIsUnc2(
                         (unsigned __int16 *)pszPath,
                         &Str,
                         (unsigned __int8 (__fastcall *)(_QWORD))IsBackslash) )
    {
      v4 = Str;
      v5 = wcschr(Str, 0x5Cu);
      v6 = v5;
      if ( v5 )
      {
        v7 = v5 + 1;
        v8 = wcschr(v5 + 1, 0x5Cu);
        if ( v8 )
        {
          v9 = v8 + 1;
          if ( v8 == v7 )
            v9 = v8;
        }
        else
        {
          v10 = -1;
          do
            ++v10;
          while ( v6[v10] );
          v9 = &v6[v10];
        }
      }
      else
      {
        v11 = -1;
        do
          ++v11;
        while ( v4[v11] );
        v9 = &v4[v11];
      }
      goto LABEL_32;
    }
    v12 = *pszPath;
    if ( *pszPath == 92 && pszPath[1] != 92 )
    {
      v9 = pszPath + 1;
LABEL_32:
      *ppszRootEnd = v9;
      return 0;
    }
    if ( PathIsVolumeGUIDWorker(pszPath) )
    {
      v13 = 49;
      if ( pszPath[48] != 92 )
        v13 = 48;
      v9 = &pszPath[v13];
      goto LABEL_32;
    }
    v14 = IsExtendedLengthDosDevicePath(pszPath);
    if ( v14 )
      v12 = pszPath[4];
    v15 = pszPath + 4;
    if ( !v14 )
      v15 = pszPath;
    if ( iswalpha(v12) && v15[1] == 58 )
    {
      v16 = 3;
      if ( v15[2] != 92 )
        v16 = 2;
      v9 = &v15[v16];
      goto LABEL_32;
    }
  }
  return -2147024809;
}

```

## disassembly

```asm
0x18002777c  push    rbx
0x18002777e  push    rbp
0x18002777f  push    rsi
0x180027780  push    rdi
0x180027781  push    r14
0x180027783  push    r15
0x180027785  sub     rsp, 28h
0x180027789  xor     r15d, r15d
0x18002778c  mov     r14, rdx
0x18002778f  mov     [rsp+58h+Str], r15
0x180027794  mov     rbx, rcx
0x180027797  test    rcx, rcx
0x18002779a  jz      loc_1800278B1
0x1800277a0  cmp     [rcx], r15w
0x1800277a4  jz      loc_1800278B1
0x1800277aa  test    rdx, rdx
0x1800277ad  jz      loc_1800278B1
0x1800277b3  mov     [rdx], r15
0x1800277b6  lea     r8, IsBackslash
0x1800277bd  lea     rdx, [rsp+58h+Str]
0x1800277c2  call    PathIsUnc2
0x1800277c7  lea     edi, [r15+5Ch]
0x1800277cb  test    eax, eax
0x1800277cd  jz      short loc_180027836
0x1800277cf  mov     rsi, [rsp+58h+Str]
0x1800277d4  mov     edx, edi; Ch
0x1800277d6  mov     rcx, rsi; Str
0x1800277d9  call    cs:__imp_wcschr
0x1800277df  mov     rbx, rax
0x1800277e2  test    rax, rax
0x1800277e5  jz      short loc_180027822
0x1800277e7  lea     rsi, [rax+2]
0x1800277eb  mov     edx, edi; Ch
0x1800277ed  mov     rcx, rsi; Str
0x1800277f0  call    cs:__imp_wcschr
0x1800277f6  test    rax, rax
0x1800277f9  jz      short loc_18002780B
0x1800277fb  cmp     rax, rsi
0x1800277fe  lea     rbx, [rax+2]
0x180027802  cmovz   rbx, rax
0x180027806  jmp     loc_1800278AA
0x18002780b  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002780f  inc     rax
0x180027812  cmp     [rbx+rax*2], r15w
0x180027817  jnz     short loc_18002780F
0x180027819  lea     rbx, [rbx+rax*2]
0x18002781d  jmp     loc_1800278AA
0x180027822  or      rax, 0FFFFFFFFFFFFFFFFh
0x180027826  inc     rax
0x180027829  cmp     [rsi+rax*2], r15w
0x18002782e  jnz     short loc_180027826
0x180027830  lea     rbx, [rsi+rax*2]
0x180027834  jmp     short loc_1800278AA
0x180027836  movzx   ebp, word ptr [rbx]
0x180027839  cmp     bp, di
0x18002783c  jnz     short loc_18002784A
0x18002783e  cmp     [rbx+2], di
0x180027842  jz      short loc_18002784A
0x180027844  add     rbx, 2
0x180027848  jmp     short loc_1800278AA
0x18002784a  mov     rcx, rbx; unsigned __int16 *
0x18002784d  call    ?PathIsVolumeGUIDWorker@@YA_NPEBG@Z; PathIsVolumeGUIDWorker(ushort const *)
0x180027852  test    al, al
0x180027854  jz      short loc_18002786A
0x180027856  cmp     [rbx+60h], di
0x18002785a  mov     eax, 62h ; 'b'
0x18002785f  lea     ecx, [rax-2]
0x180027862  cmovnz  eax, ecx
0x180027865  add     rbx, rax
0x180027868  jmp     short loc_1800278AA
0x18002786a  mov     rcx, rbx; unsigned __int16 *
0x18002786d  call    ?IsExtendedLengthDosDevicePath@@YA_NPEBG@Z; IsExtendedLengthDosDevicePath(ushort const *)
0x180027872  test    al, al
0x180027874  jz      short loc_18002787A
0x180027876  movzx   ebp, word ptr [rbx+8]
0x18002787a  test    al, al
0x18002787c  lea     rsi, [rbx+8]
0x180027880  movzx   ecx, bp; C
0x180027883  cmovz   rsi, rbx
0x180027887  call    cs:__imp_iswalpha
0x18002788d  test    eax, eax
0x18002788f  jz      short loc_1800278B1
0x180027891  cmp     word ptr [rsi+2], 3Ah ; ':'
0x180027896  jnz     short loc_1800278B1
0x180027898  cmp     [rsi+4], di
0x18002789c  mov     ebx, 6
0x1800278a1  lea     eax, [rbx-2]
0x1800278a4  cmovnz  ebx, eax
0x1800278a7  add     rbx, rsi
0x1800278aa  mov     [r14], rbx
0x1800278ad  xor     eax, eax
0x1800278af  jmp     short loc_1800278B6
0x1800278b1  mov     eax, 80070057h
0x1800278b6  add     rsp, 28h
0x1800278ba  pop     r15
0x1800278bc  pop     r14
0x1800278be  pop     rdi
0x1800278bf  pop     rsi
0x1800278c0  pop     rbp
0x1800278c1  pop     rbx
0x1800278c2  retn
```
