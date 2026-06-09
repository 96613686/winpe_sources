# ConfirmFontInstalledOnSystem

- ea: `0x180019a88`
- end: `0x180019da8`
- name: `ConfirmFontInstalledOnSystem`
- size: `800`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `installer_update`

## callers

- `0x1800190a4`

## callees

- `0x180019a88`
- `0x180019dc0`
- `0x18001b4b0`
- `0x18001ba0c`
- `0x18001c87c`
- `0x18001d304`
- `0x18001d4b4`
- `0x180023434`
- `0x18002a54e`
- `0x18002a566`
- `0x18002a590`

## import_xrefs

- `KERNEL32!lstrcmpiA` at `0x180019ca6`
- `KERNEL32!lstrcmpiA` at `0x180019ca6`
- `GDI32!SelectObject` at `0x180019bda`
- `GDI32!SelectObject` at `0x180019c21`
- `GDI32!SelectObject` at `0x180019d5b`
- `GDI32!SelectObject` at `0x180019bda`
- `GDI32!SelectObject` at `0x180019c21`
- `GDI32!SelectObject` at `0x180019d5b`
- `GDI32!DeleteObject` at `0x180019bf5`
- `GDI32!DeleteObject` at `0x180019d64`
- `GDI32!DeleteObject` at `0x180019bf5`
- `GDI32!DeleteObject` at `0x180019d64`
- `GDI32!CreateFontIndirectW` at `0x180019ba3`
- `GDI32!CreateFontIndirectW` at `0x180019ba3`
- `GDI32!GetFontData` at `0x180019cee`
- `GDI32!GetFontData` at `0x180019cee`
- `GDI32!GetTextMetricsA` at `0x180019c07`
- `GDI32!GetTextMetricsA` at `0x180019c07`

## pseudocode

```c
__int64 __fastcall ConfirmFontInstalledOnSystem(__int64 a1, int a2, BYTE a3, BOOL *a4, int a5, int a6, __int64 a7)
{
  HDC v10; // rbx
  size_t v12; // r8
  HFONT v13; // rax
  HFONT v14; // r14
  HDC v15; // rcx
  HGDIOBJ v16; // r12
  _QWORD *AllocOtm; // rdi
  CHAR *v18; // r13
  unsigned int v19; // edi
  const CHAR *v20; // rcx
  const char *v21; // r8
  BOOL v22; // eax
  _WORD v23[2]; // [rsp+30h] [rbp-B1h] BYREF
  int pvBuffer; // [rsp+34h] [rbp-ADh] BYREF
  LPCSTR lpString2; // [rsp+38h] [rbp-A9h] BYREF
  int v26; // [rsp+40h] [rbp-A1h]
  LOGFONTW lf; // [rsp+50h] [rbp-91h] BYREF
  tagTEXTMETRICA tm; // [rsp+B0h] [rbp-31h] BYREF

  v26 = a2;
  lpString2 = 0;
  LOWORD(pvBuffer) = 0;
  v23[0] = 0;
  memset(&tm, 0, sizeof(tm));
  memset_0(&lf, 0, sizeof(lf));
  v10 = (HDC)AllocDC(v23);
  if ( !v10 )
  {
    *(_DWORD *)(a7 + 944) = 520;
    return 0;
  }
  if ( !(unsigned int)AllocConvertToMultiByte(&lpString2, &pvBuffer, *(_QWORD *)(a1 + 88)) )
    return 0;
  memset_0(&lf, 0, sizeof(lf));
  lf.lfWeight = *(_DWORD *)(a1 + 28);
  lf.lfItalic = *(_BYTE *)(a1 + 27);
  *(_WORD *)&lf.lfOutPrecision = 8;
  lf.lfCharSet = a3;
  lf.lfPitchAndFamily = 0;
  if ( *(_WORD *)(a1 + 82) >= 0x40u )
    v12 = 64;
  else
    v12 = *(unsigned __int16 *)(a1 + 82);
  memcpy_0(lf.lfFaceName, *(const void **)(a1 + 88), v12);
  lf.lfFaceName[31] = 0;
  if ( !a5 || a6 )
    lf.lfClipPrecision |= 0x80u;
  v13 = CreateFontIndirectW(&lf);
  v14 = v13;
  v15 = v10;
  if ( !v13 )
  {
    *(_DWORD *)(a7 + 944) = 516;
LABEL_13:
    FreeDC(v15, v23[0]);
    T2free((LPVOID)lpString2);
    return 0;
  }
  v16 = SelectObject(v10, v13);
  if ( !v16 )
  {
    *(_DWORD *)(a7 + 944) = 516;
LABEL_16:
    DeleteObject(v14);
    v15 = v10;
    goto LABEL_13;
  }
  if ( !GetTextMetricsA(v10, &tm) )
  {
    *(_DWORD *)(a7 + 944) = 516;
    SelectObject(v10, v16);
    goto LABEL_16;
  }
  if ( !(unsigned int)IsSelectedFontOpenType(v10) )
  {
    v18 = (CHAR *)lpString2;
    *a4 = 0;
    goto LABEL_34;
  }
  AllocOtm = (_QWORD *)GetAllocOtm(v10);
  if ( AllocOtm )
  {
    if ( *(_DWORD *)(a1 + 28) == tm.tmWeight && (*(_BYTE *)(a1 + 27) != 0) == (tm.tmItalic != 0) )
    {
      v18 = (CHAR *)lpString2;
      v20 = (char *)AllocOtm + AllocOtm[25];
      pvBuffer = 0;
      if ( lstrcmpiA(v20, lpString2) )
        v21 = &Class;
      else
        v21 = (char *)AllocOtm + AllocOtm[26];
      StringCchCopyA((STRSAFE_LPSTR)(a7 + 780), 0x40u, v21);
      if ( (unsigned __int16)GetFontData(v10, 0x64616568u, 8u, &pvBuffer, 4u) != 4 )
      {
        *a4 = 0;
LABEL_32:
        T2free(AllocOtm);
LABEL_34:
        v19 = 1;
        goto LABEL_35;
      }
      v22 = v26 == (HIBYTE(pvBuffer)
                  | ((BYTE2(pvBuffer) | ((BYTE1(pvBuffer) | ((unsigned __int8)pvBuffer << 8)) << 8)) << 8));
    }
    else
    {
      v18 = (CHAR *)lpString2;
      v22 = 0;
    }
    *a4 = v22;
    goto LABEL_32;
  }
  v18 = (CHAR *)lpString2;
  v19 = 0;
  *(_DWORD *)(a7 + 944) = 516;
LABEL_35:
  SelectObject(v10, v16);
  DeleteObject(v14);
  FreeDC(v10, v23[0]);
  T2free(v18);
  return v19;
}

```

## disassembly

```asm
0x180019a88  mov     [rsp-8+arg_8], rbx
0x180019a8d  push    rbp
0x180019a8e  push    rsi
0x180019a8f  push    rdi
0x180019a90  push    r12
0x180019a92  push    r13
0x180019a94  push    r14
0x180019a96  push    r15
0x180019a98  lea     rbp, [rsp-0Fh]
0x180019a9d  sub     rsp, 0F0h
0x180019aa4  mov     rax, cs:__security_cookie
0x180019aab  xor     rax, rsp
0x180019aae  mov     [rbp+3Fh+var_38], rax
0x180019ab2  mov     rsi, [rbp+3Fh+arg_30]
0x180019ab6  xor     r12d, r12d
0x180019ab9  xorps   xmm0, xmm0
0x180019abc  mov     [rsp+120h+var_E0], edx
0x180019ac0  mov     dil, r8b
0x180019ac3  mov     [rsp+120h+lpString2], r12
0x180019ac8  mov     r13, rcx
0x180019acb  mov     word ptr [rsp+120h+pvBuffer], r12w
0x180019ad1  xor     eax, eax
0x180019ad3  mov     [rsp+120h+var_F0], r12w
0x180019ad9  lea     r14d, [r12+5Ch]
0x180019ade  mov     qword ptr [rbp+3Fh+tm.tmItalic], rax
0x180019ae2  mov     r8d, r14d; Size
0x180019ae5  lea     rcx, [rsp+120h+lf]; void *
0x180019aea  xor     edx, edx; Val
0x180019aec  mov     r15, r9
0x180019aef  movups  xmmword ptr [rbp+3Fh+tm.tmHeight], xmm0
0x180019af3  movups  xmmword ptr [rbp+3Fh+tm.tmExternalLeading], xmm0
0x180019af7  movups  xmmword ptr [rbp+3Fh+tm.tmOverhang], xmm0
0x180019afb  call    memset_0
0x180019b00  lea     rcx, [rsp+120h+var_F0]
0x180019b05  call    AllocDC
0x180019b0a  mov     rbx, rax
0x180019b0d  test    rax, rax
0x180019b10  jnz     short loc_180019B23
0x180019b12  mov     dword ptr [rsi+3B0h], 208h
0x180019b1c  xor     eax, eax
0x180019b1e  jmp     loc_180019D81
0x180019b23  mov     r8, [r13+58h]
0x180019b27  lea     rdx, [rsp+120h+pvBuffer]
0x180019b2c  lea     rcx, [rsp+120h+lpString2]
0x180019b31  call    AllocConvertToMultiByte
0x180019b36  test    eax, eax
0x180019b38  jz      short loc_180019B1C
0x180019b3a  mov     r8, r14; Size
0x180019b3d  lea     rcx, [rsp+120h+lf]; void *
0x180019b42  xor     edx, edx; Val
0x180019b44  call    memset_0
0x180019b49  mov     eax, [r13+1Ch]
0x180019b4d  mov     [rsp+120h+lf.lfWeight], eax
0x180019b51  mov     al, [r13+1Bh]
0x180019b55  mov     [rbp+3Fh+lf.lfItalic], al
0x180019b58  mov     eax, 40h ; '@'
0x180019b5d  mov     word ptr [rbp+3Fh+lf.lfOutPrecision], 8
0x180019b63  mov     [rbp+3Fh+lf.lfCharSet], dil
0x180019b67  mov     [rbp+3Fh+lf.lfPitchAndFamily], r12b
0x180019b6b  cmp     [r13+52h], ax
0x180019b70  jnb     short loc_180019B79
0x180019b72  movzx   r8d, word ptr [r13+52h]
0x180019b77  jmp     short loc_180019B7C
0x180019b79  mov     r8, rax; Size
0x180019b7c  mov     rdx, [r13+58h]; Src
0x180019b80  lea     rcx, [rbp+3Fh+lf.lfFaceName]; void *
0x180019b84  call    memcpy_0
0x180019b89  mov     [rbp+3Fh+lf.lfFaceName+3Eh], r12w
0x180019b8e  cmp     [rbp+3Fh+arg_20], r12d
0x180019b92  jz      short loc_180019B9A
0x180019b94  cmp     [rbp+3Fh+arg_28], r12d
0x180019b98  jz      short loc_180019B9E
0x180019b9a  or      [rbp+3Fh+lf.lfClipPrecision], 80h
0x180019b9e  lea     rcx, [rsp+120h+lf]; lplf
0x180019ba3  call    cs:__imp_CreateFontIndirectW
0x180019ba9  mov     r14, rax
0x180019bac  mov     rcx, rbx; hdc
0x180019baf  test    rax, rax
0x180019bb2  jnz     short loc_180019BD7
0x180019bb4  mov     dword ptr [rsi+3B0h], 204h
0x180019bbe  movzx   edx, [rsp+120h+var_F0]
0x180019bc3  call    FreeDC
0x180019bc8  mov     rcx, [rsp+120h+lpString2]; lpMem
0x180019bcd  call    T2free
0x180019bd2  jmp     loc_180019B1C
0x180019bd7  mov     rdx, r14; h
0x180019bda  call    cs:__imp_SelectObject
0x180019be0  mov     r12, rax
0x180019be3  test    rax, rax
0x180019be6  jnz     short loc_180019C00
0x180019be8  mov     dword ptr [rsi+3B0h], 204h
0x180019bf2  mov     rcx, r14; ho
0x180019bf5  call    cs:__imp_DeleteObject
0x180019bfb  mov     rcx, rbx
0x180019bfe  jmp     short loc_180019BBE
0x180019c00  lea     rdx, [rbp+3Fh+tm]; lptm
0x180019c04  mov     rcx, rbx; hdc
0x180019c07  call    cs:__imp_GetTextMetricsA
0x180019c0d  mov     rcx, rbx; hdc
0x180019c10  test    eax, eax
0x180019c12  jnz     short loc_180019C29
0x180019c14  mov     rdx, r12; h
0x180019c17  mov     dword ptr [rsi+3B0h], 204h
0x180019c21  call    cs:__imp_SelectObject
0x180019c27  jmp     short loc_180019BF2
0x180019c29  xor     edx, edx
0x180019c2b  call    IsSelectedFontOpenType
0x180019c30  mov     rcx, [rsp+120h+lpString2]
0x180019c35  mov     [rsp+120h+lpString2], rcx
0x180019c3a  test    eax, eax
0x180019c3c  jz      loc_180019D44
0x180019c42  mov     rcx, rbx; hdc
0x180019c45  call    GetAllocOtm
0x180019c4a  xor     edx, edx
0x180019c4c  mov     rdi, rax
0x180019c4f  test    rax, rax
0x180019c52  jnz     short loc_180019C6A
0x180019c54  mov     r13, [rsp+120h+lpString2]
0x180019c59  mov     edi, edx
0x180019c5b  mov     dword ptr [rsi+3B0h], 204h
0x180019c65  jmp     loc_180019D55
0x180019c6a  mov     eax, [rbp+3Fh+tm.tmWeight]
0x180019c6d  cmp     [r13+1Ch], eax
0x180019c71  jnz     loc_180019D30
0x180019c77  cmp     [r13+1Bh], dl
0x180019c7b  mov     ecx, edx
0x180019c7d  mov     eax, edx
0x180019c7f  setnz   cl
0x180019c82  cmp     [rbp+3Fh+tm.tmItalic], dl
0x180019c85  setnz   al
0x180019c88  cmp     ecx, eax
0x180019c8a  jnz     loc_180019D30
0x180019c90  mov     rcx, [rdi+0C8h]
0x180019c97  mov     r13, [rsp+120h+lpString2]
0x180019c9c  add     rcx, rdi; lpString1
0x180019c9f  mov     [rsp+120h+pvBuffer], edx
0x180019ca3  mov     rdx, r13; lpString2
0x180019ca6  call    cs:__imp_lstrcmpiA
0x180019cac  mov     edx, 40h ; '@'; cchDest
0x180019cb1  lea     rcx, [rsi+30Ch]; pszDest
0x180019cb8  test    eax, eax
0x180019cba  jnz     short loc_180019CC8
0x180019cbc  mov     r8, [rdi+0D0h]
0x180019cc3  add     r8, rdi
0x180019cc6  jmp     short loc_180019CCF
0x180019cc8  lea     r8, Class; pszSrc
0x180019ccf  call    StringCchCopyA
0x180019cd4  mov     esi, 4
0x180019cd9  lea     r9, [rsp+120h+pvBuffer]; pvBuffer
0x180019cde  mov     edx, 64616568h; dwTable
0x180019ce3  mov     [rsp+120h+cjBuffer], esi; cjBuffer
0x180019ce7  mov     rcx, rbx; hdc
0x180019cea  lea     r8d, [rsi+4]; dwOffset
0x180019cee  call    cs:__imp_GetFontData
0x180019cf4  cmp     ax, si
0x180019cf7  jz      short loc_180019D02
0x180019cf9  mov     dword ptr [r15], 0
0x180019d00  jmp     short loc_180019D3A
0x180019d02  movzx   eax, byte ptr [rsp+120h+pvBuffer+1]
0x180019d07  movzx   ecx, byte ptr [rsp+120h+pvBuffer]
0x180019d0c  shl     ecx, 8
0x180019d0f  or      ecx, eax
0x180019d11  movzx   eax, byte ptr [rsp+120h+pvBuffer+2]
0x180019d16  shl     ecx, 8
0x180019d19  or      ecx, eax
0x180019d1b  movzx   eax, byte ptr [rsp+120h+pvBuffer+3]
0x180019d20  shl     ecx, 8
0x180019d23  or      ecx, eax
0x180019d25  xor     eax, eax
0x180019d27  cmp     [rsp+120h+var_E0], ecx
0x180019d2b  setz    al
0x180019d2e  jmp     short loc_180019D37
0x180019d30  mov     r13, [rsp+120h+lpString2]
0x180019d35  mov     eax, edx
0x180019d37  mov     [r15], eax
0x180019d3a  mov     rcx, rdi; lpMem
0x180019d3d  call    T2free
0x180019d42  jmp     short loc_180019D50
0x180019d44  mov     r13, [rsp+120h+lpString2]
0x180019d49  mov     dword ptr [r15], 0
0x180019d50  mov     edi, 1
0x180019d55  mov     rdx, r12; h
0x180019d58  mov     rcx, rbx; hdc
0x180019d5b  call    cs:__imp_SelectObject
0x180019d61  mov     rcx, r14; ho
0x180019d64  call    cs:__imp_DeleteObject
0x180019d6a  movzx   edx, [rsp+120h+var_F0]
0x180019d6f  mov     rcx, rbx
0x180019d72  call    FreeDC
0x180019d77  mov     rcx, r13; lpMem
0x180019d7a  call    T2free
0x180019d7f  mov     eax, edi
0x180019d81  mov     rcx, [rbp+3Fh+var_38]
0x180019d85  xor     rcx, rsp; StackCookie
0x180019d88  call    __security_check_cookie
0x180019d8d  mov     rbx, [rsp+120h+arg_8]
0x180019d95  add     rsp, 0F0h
0x180019d9c  pop     r15
0x180019d9e  pop     r14
0x180019da0  pop     r13
0x180019da2  pop     r12
0x180019da4  pop     rdi
0x180019da5  pop     rsi
0x180019da6  pop     rbp
0x180019da7  retn
```
