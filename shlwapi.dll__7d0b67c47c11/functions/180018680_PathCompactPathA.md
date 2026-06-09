# PathCompactPathA

- ea: `0x180018680`
- end: `0x1800189ce`
- name: `PathCompactPathA`
- size: `846`
- prototype: `BOOL __stdcall(HDC hDC, LPSTR pszPath, UINT dx)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800196c0`

## callees

- `0x180012550`
- `0x180017344`
- `0x180018680`

## import_xrefs

- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameA` at `0x18001878a`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameA` at `0x18001878a`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenA` at `0x1800186fe`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenA` at `0x1800187a1`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenA` at `0x180018829`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenA` at `0x1800186fe`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenA` at `0x1800187a1`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenA` at `0x180018829`
- `GDI32!GetTextExtentPointA` at `0x180018714`
- `GDI32!GetTextExtentPointA` at `0x180018746`
- `GDI32!GetTextExtentPointA` at `0x1800187b9`
- `GDI32!GetTextExtentPointA` at `0x1800187fc`
- `GDI32!GetTextExtentPointA` at `0x180018714`
- `GDI32!GetTextExtentPointA` at `0x180018746`
- `GDI32!GetTextExtentPointA` at `0x1800187b9`
- `GDI32!GetTextExtentPointA` at `0x1800187fc`
- `GDI32!GetGlyphIndicesA` at `0x180018778`
- `GDI32!GetGlyphIndicesA` at `0x180018778`
- `GDI32!GetTextExtentExPointI` at `0x18001888a`
- `GDI32!GetTextExtentExPointI` at `0x18001895a`
- `GDI32!GetTextExtentExPointI` at `0x18001888a`
- `GDI32!GetTextExtentExPointI` at `0x18001895a`
- `USER32!GetDC` at `0x1800186ef`
- `USER32!GetDC` at `0x1800186ef`
- `USER32!ReleaseDC` at `0x18001899b`
- `USER32!ReleaseDC` at `0x18001899b`

## pseudocode

```c
BOOL __stdcall PathCompactPathA(HDC hDC, LPSTR pszPath, UINT dx)
{
  BOOL v4; // r15d
  HDC v6; // rbx
  HDC DC; // r12
  int v8; // esi
  int v9; // ecx
  LONG v10; // r11d
  int v11; // r10d
  int v12; // eax
  int v13; // r8d
  char *v14; // r8
  int v15; // esi
  char *v16; // rcx
  int v17; // r8d
  LONG v19; // [rsp+40h] [rbp-C0h]
  LONG v20; // [rsp+44h] [rbp-BCh]
  LONG cx; // [rsp+48h] [rbp-B8h]
  const CHAR *pszSrc; // [rsp+50h] [rbp-B0h]
  int nFit; // [rsp+58h] [rbp-A8h] BYREF
  int v24; // [rsp+5Ch] [rbp-A4h] BYREF
  struct tagSIZE sz; // [rsp+60h] [rbp-A0h] BYREF
  char pszDest[256]; // [rsp+70h] [rbp-90h] BYREF
  WORD pgi[264]; // [rsp+170h] [rbp+70h] BYREF

  v4 = 1;
  v6 = hDC;
  if ( !pszPath )
    return v4;
  v4 = 0;
  v24 = 0;
  DC = 0;
  nFit = 0;
  sz = 0;
  if ( !hDC )
  {
    DC = GetDC(0);
    v6 = DC;
  }
  v8 = lstrlenA(pszPath);
  if ( GetTextExtentPointA(v6, pszPath, v8, &sz) )
  {
    if ( sz.cx <= dx )
    {
      v4 = 1;
      goto LABEL_28;
    }
    if ( !GetTextExtentPointA(v6, "...", 3, &sz) )
      goto LABEL_28;
    cx = sz.cx;
    if ( v8 > 259 )
      v8 = 259;
    if ( GetGlyphIndicesA(v6, pszPath, v8, pgi, 0) == -1 )
      goto LABEL_28;
    pszSrc = PathFindFileNameA(pszPath);
    nFit = (_DWORD)pszSrc - (_DWORD)pszPath;
    v24 = lstrlenA(pszSrc);
    if ( !GetTextExtentPointA(v6, pszSrc, v24, &sz) )
      goto LABEL_28;
    v9 = nFit;
    v10 = sz.cx;
    v11 = 0;
    v20 = sz.cx;
    if ( nFit )
    {
      if ( !GetTextExtentPointA(v6, "...\\", 4, &sz) )
        goto LABEL_28;
      v19 = sz.cx;
      StringCchCopyA(pszDest, 0x100u, pszSrc);
      v12 = lstrlenA(pszDest);
      v13 = nFit;
      v24 = v12;
      if ( nFit > 255 - v12 )
      {
        v13 = 255 - v12;
        nFit = 255 - v12;
      }
      if ( v13 > 0 && dx > v19 + v20 )
      {
        if ( !GetTextExtentExPointI(v6, pgi, v13, dx - v19 - v20, &nFit, 0, &sz) )
          goto LABEL_28;
        StringCchCopyA(&pszPath[nFit], 260 - nFit, "...\\");
        v14 = pszDest;
        v15 = 260 - (nFit + 4);
        v16 = &pszPath[nFit + 4];
        nFit += 4;
        goto LABEL_26;
      }
      StringCchCopyA(pszPath, 0x104u, "...\\");
      nFit = 4;
      StringCchCopyA(pszPath + 4, 0x100u, pszDest);
      v9 = 4;
    }
    if ( dx >= v11 + v10 )
    {
LABEL_27:
      v4 = 1;
      goto LABEL_28;
    }
    v17 = v24;
    if ( v24 > 256 - v9 )
    {
      v17 = 256 - v9;
      v24 = 256 - v9;
    }
    if ( !GetTextExtentExPointI(v6, &pgi[pszSrc - pszPath], v17, dx - cx - v11, &v24, 0, &sz) )
      goto LABEL_28;
    v14 = "...";
    v15 = 260 - nFit - v24;
    v16 = &pszPath[nFit + v24];
LABEL_26:
    StringCchCopyA(v16, v15, v14);
    goto LABEL_27;
  }
LABEL_28:
  if ( DC )
    ReleaseDC(0, DC);
  return v4;
}

```

## disassembly

```asm
0x180018680  mov     [rsp-8+arg_18], rbx
0x180018685  push    rbp
0x180018686  push    rsi
0x180018687  push    rdi
0x180018688  push    r12
0x18001868a  push    r13
0x18001868c  push    r14
0x18001868e  push    r15
0x180018690  lea     rbp, [rsp-290h]
0x180018698  sub     rsp, 390h
0x18001869f  mov     rax, cs:__security_cookie
0x1800186a6  xor     rax, rsp
0x1800186a9  mov     [rbp+2C0h+var_40], rax
0x1800186b0  mov     r13d, 1
0x1800186b6  mov     r14d, r8d
0x1800186b9  mov     r15d, r13d
0x1800186bc  mov     rdi, rdx
0x1800186bf  mov     rbx, rcx
0x1800186c2  test    rdx, rdx
0x1800186c5  jz      loc_1800189A1
0x1800186cb  xor     r15d, r15d
0x1800186ce  mov     [rsp+3C0h+var_364], 0
0x1800186d6  xor     r12d, r12d
0x1800186d9  mov     [rsp+3C0h+nFit], 0
0x1800186e1  mov     qword ptr [rsp+3C0h+sz.cx], 0
0x1800186ea  test    rcx, rcx
0x1800186ed  jnz     short loc_1800186FB
0x1800186ef  call    cs:__imp_GetDC
0x1800186f5  mov     r12, rax
0x1800186f8  mov     rbx, rax
0x1800186fb  mov     rcx, rdi; lpString
0x1800186fe  call    cs:__imp_lstrlenA
0x180018704  lea     r9, [rsp+3C0h+sz]; lpsz
0x180018709  mov     rdx, rdi; lpString
0x18001870c  mov     r8d, eax; c
0x18001870f  mov     rcx, rbx; hdc
0x180018712  mov     esi, eax
0x180018714  call    cs:__imp_GetTextExtentPointA
0x18001871a  test    eax, eax
0x18001871c  jz      loc_180018991
0x180018722  cmp     [rsp+3C0h+sz.cx], r14d
0x180018727  ja      short loc_180018731
0x180018729  mov     r15d, r13d
0x18001872c  jmp     loc_180018991
0x180018731  lea     r9, [rsp+3C0h+sz]; lpsz
0x180018736  mov     r8d, 3; c
0x18001873c  lea     rdx, asc_18003DAFC; "..."
0x180018743  mov     rcx, rbx; hdc
0x180018746  call    cs:__imp_GetTextExtentPointA
0x18001874c  test    eax, eax
0x18001874e  jz      loc_180018991
0x180018754  mov     eax, [rsp+3C0h+sz.cx]
0x180018758  lea     r9, [rbp+2C0h+pgi]; pgi
0x18001875c  mov     [rsp+3C0h+var_378], eax
0x180018760  mov     rdx, rdi; lpstr
0x180018763  mov     eax, 103h
0x180018768  mov     [rsp+3C0h+fl], r15d; fl
0x18001876d  cmp     esi, eax
0x18001876f  mov     rcx, rbx; hdc
0x180018772  cmovg   esi, eax
0x180018775  mov     r8d, esi; c
0x180018778  call    cs:__imp_GetGlyphIndicesA
0x18001877e  cmp     eax, 0FFFFFFFFh
0x180018781  jz      loc_180018991
0x180018787  mov     rcx, rdi; pszPath
0x18001878a  call    cs:__imp_PathFindFileNameA
0x180018790  mov     rsi, rax
0x180018793  mov     [rsp+3C0h+pszSrc], rax
0x180018798  sub     eax, edi
0x18001879a  mov     rcx, rsi; lpString
0x18001879d  mov     [rsp+3C0h+nFit], eax
0x1800187a1  call    cs:__imp_lstrlenA
0x1800187a7  lea     r9, [rsp+3C0h+sz]; lpsz
0x1800187ac  mov     rdx, rsi; lpString
0x1800187af  mov     r8d, eax; c
0x1800187b2  mov     [rsp+3C0h+var_364], eax
0x1800187b6  mov     rcx, rbx; hdc
0x1800187b9  call    cs:__imp_GetTextExtentPointA
0x1800187bf  test    eax, eax
0x1800187c1  jz      loc_180018991
0x1800187c7  mov     ecx, [rsp+3C0h+nFit]
0x1800187cb  mov     esi, 104h
0x1800187d0  mov     r11d, [rsp+3C0h+sz.cx]
0x1800187d5  xor     r10d, r10d
0x1800187d8  mov     [rsp+3C0h+var_37C], r11d
0x1800187dd  lea     r13d, [rsi-4]
0x1800187e1  test    ecx, ecx
0x1800187e3  jz      loc_180018905
0x1800187e9  lea     r9, [rsp+3C0h+sz]; lpsz
0x1800187ee  mov     rcx, rbx; hdc
0x1800187f1  lea     r8d, [r10+4]; c
0x1800187f5  lea     rdx, asc_18003DAF4; "...\\"
0x1800187fc  call    cs:__imp_GetTextExtentPointA
0x180018802  test    eax, eax
0x180018804  jz      loc_180018991
0x18001880a  mov     eax, [rsp+3C0h+sz.cx]
0x18001880e  lea     rcx, [rsp+3C0h+pszDest]; pszDest
0x180018813  mov     r8, [rsp+3C0h+pszSrc]; pszSrc
0x180018818  mov     edx, r13d; cchDest
0x18001881b  mov     [rsp+3C0h+var_380], eax
0x18001881f  call    StringCchCopyA
0x180018824  lea     rcx, [rsp+3C0h+pszDest]; lpString
0x180018829  call    cs:__imp_lstrlenA
0x18001882f  mov     r8d, [rsp+3C0h+nFit]
0x180018834  lea     ecx, [rsi-5]
0x180018837  sub     ecx, eax
0x180018839  mov     [rsp+3C0h+var_364], eax
0x18001883d  cmp     r8d, ecx
0x180018840  jle     short loc_180018849
0x180018842  mov     r8d, ecx; cwchString
0x180018845  mov     [rsp+3C0h+nFit], ecx
0x180018849  mov     r10d, [rsp+3C0h+var_380]
0x18001884e  mov     r11d, [rsp+3C0h+var_37C]
0x180018853  test    r8d, r8d
0x180018856  jle     short loc_1800188D6
0x180018858  lea     eax, [r10+r11]
0x18001885c  cmp     r14d, eax
0x18001885f  jbe     short loc_1800188D6
0x180018861  sub     r14d, r10d
0x180018864  lea     rax, [rsp+3C0h+sz]
0x180018869  mov     [rsp+3C0h+lpSize], rax; lpSize
0x18001886e  lea     rdx, [rbp+2C0h+pgi]; lpwszString
0x180018872  sub     r14d, r11d
0x180018875  mov     [rsp+3C0h+lpnDx], r15; lpnDx
0x18001887a  lea     rax, [rsp+3C0h+nFit]
0x18001887f  mov     r9d, r14d; nMaxExtent
0x180018882  mov     rcx, rbx; hdc
0x180018885  mov     qword ptr [rsp+3C0h+fl], rax; lpnFit
0x18001888a  call    cs:__imp_GetTextExtentExPointI
0x180018890  test    eax, eax
0x180018892  jz      loc_180018991
0x180018898  movsxd  rcx, [rsp+3C0h+nFit]
0x18001889d  lea     r8, asc_18003DAF4; "...\\"
0x1800188a4  mov     eax, esi
0x1800188a6  add     rcx, rdi; pszDest
0x1800188a9  sub     eax, [rsp+3C0h+nFit]
0x1800188ad  movsxd  rdx, eax; cchDest
0x1800188b0  call    StringCchCopyA
0x1800188b5  mov     r10d, [rsp+3C0h+nFit]
0x1800188ba  lea     r8, [rsp+3C0h+pszDest]
0x1800188bf  add     r10d, 4
0x1800188c3  sub     esi, r10d
0x1800188c6  movsxd  rcx, r10d
0x1800188c9  add     rcx, rdi
0x1800188cc  mov     [rsp+3C0h+nFit], r10d
0x1800188d1  jmp     loc_180018983
0x1800188d6  lea     r8, asc_18003DAF4; "...\\"
0x1800188dd  mov     rdx, rsi; cchDest
0x1800188e0  mov     rcx, rdi; pszDest
0x1800188e3  call    StringCchCopyA
0x1800188e8  lea     rcx, [rdi+4]; pszDest
0x1800188ec  mov     [rsp+3C0h+nFit], 4
0x1800188f4  lea     r8, [rsp+3C0h+pszDest]; pszSrc
0x1800188f9  mov     rdx, r13; cchDest
0x1800188fc  call    StringCchCopyA
0x180018901  mov     ecx, [rsp+3C0h+nFit]
0x180018905  lea     eax, [r10+r11]
0x180018909  cmp     r14d, eax
0x18001890c  jnb     short loc_18001898B
0x18001890e  mov     r8d, [rsp+3C0h+var_364]
0x180018913  sub     r13d, ecx
0x180018916  cmp     r8d, r13d
0x180018919  jle     short loc_180018923
0x18001891b  mov     r8d, r13d; cwchString
0x18001891e  mov     [rsp+3C0h+var_364], r13d
0x180018923  mov     rax, [rsp+3C0h+pszSrc]
0x180018928  lea     rdx, [rbp+2C0h+pgi]
0x18001892c  sub     r14d, [rsp+3C0h+var_378]
0x180018931  sub     rax, rdi
0x180018934  sub     r14d, r10d
0x180018937  mov     rcx, rbx; hdc
0x18001893a  mov     r9d, r14d; nMaxExtent
0x18001893d  lea     rdx, [rdx+rax*2]; lpwszString
0x180018941  lea     rax, [rsp+3C0h+sz]
0x180018946  mov     [rsp+3C0h+lpSize], rax; lpSize
0x18001894b  lea     rax, [rsp+3C0h+var_364]
0x180018950  mov     [rsp+3C0h+lpnDx], r15; lpnDx
0x180018955  mov     qword ptr [rsp+3C0h+fl], rax; lpnFit
0x18001895a  call    cs:__imp_GetTextExtentExPointI
0x180018960  test    eax, eax
0x180018962  jz      short loc_180018991
0x180018964  sub     esi, [rsp+3C0h+nFit]
0x180018968  lea     r8, asc_18003DAFC; "..."
0x18001896f  movsxd  rax, [rsp+3C0h+nFit]
0x180018974  sub     esi, [rsp+3C0h+var_364]
0x180018978  add     rax, rdi
0x18001897b  movsxd  rcx, [rsp+3C0h+var_364]
0x180018980  add     rcx, rax; pszDest
0x180018983  movsxd  rdx, esi; cchDest
0x180018986  call    StringCchCopyA
0x18001898b  mov     r15d, 1
0x180018991  test    r12, r12
0x180018994  jz      short loc_1800189A1
0x180018996  mov     rdx, r12; hDC
0x180018999  xor     ecx, ecx; hWnd
0x18001899b  call    cs:__imp_ReleaseDC
0x1800189a1  mov     eax, r15d
0x1800189a4  mov     rcx, [rbp+2C0h+var_40]
0x1800189ab  xor     rcx, rsp; StackCookie
0x1800189ae  call    __security_check_cookie
0x1800189b3  mov     rbx, [rsp+3C0h+arg_18]
0x1800189bb  add     rsp, 390h
0x1800189c2  pop     r15
0x1800189c4  pop     r14
0x1800189c6  pop     r13
0x1800189c8  pop     r12
0x1800189ca  pop     rdi
0x1800189cb  pop     rsi
0x1800189cc  pop     rbp
0x1800189cd  retn
```
