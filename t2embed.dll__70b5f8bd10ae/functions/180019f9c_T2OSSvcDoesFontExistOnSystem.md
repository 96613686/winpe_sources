# T2OSSvcDoesFontExistOnSystem

- ea: `0x180019f9c`
- end: `0x18001a19e`
- name: `T2OSSvcDoesFontExistOnSystem`
- size: `514`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x1800190a4`
- `0x18002173c`

## callees

- `0x180019dc0`
- `0x180019f9c`
- `0x18001c87c`
- `0x18001d304`
- `0x18001d4b4`
- `0x18002a566`
- `0x18002a590`

## import_xrefs

- `GDI32!CreateFontIndirectA` at `0x18001a099`
- `GDI32!CreateFontIndirectA` at `0x18001a099`
- `GDI32!SelectObject` at `0x18001a0c9`
- `GDI32!SelectObject` at `0x18001a14a`
- `GDI32!SelectObject` at `0x18001a0c9`
- `GDI32!SelectObject` at `0x18001a14a`
- `GDI32!EnumFontFamiliesA` at `0x18001a060`
- `GDI32!EnumFontFamiliesA` at `0x18001a060`
- `GDI32!DeleteObject` at `0x18001a153`
- `GDI32!DeleteObject` at `0x18001a153`
- `GDI32!GetFontData` at `0x18001a101`
- `GDI32!GetFontData` at `0x18001a101`

## pseudocode

```c
__int64 __fastcall T2OSSvcDoesFontExistOnSystem(
        __int64 a1,
        _DWORD *a2,
        _DWORD *a3,
        __int64 a4,
        int a5,
        int a6,
        __int64 a7)
{
  HDC v11; // rbx
  CHAR *v12; // rcx
  CHAR *v13; // r13
  unsigned int v14; // edi
  HFONT v15; // rax
  HFONT v16; // rsi
  __int64 v17; // rdx
  HGDIOBJ v18; // r12
  _WORD v19[2]; // [rsp+30h] [rbp-71h] BYREF
  int pvBuffer; // [rsp+34h] [rbp-6Dh] BYREF
  LPCSTR lpLogfont; // [rsp+38h] [rbp-69h] BYREF
  __int64 v22; // [rsp+40h] [rbp-61h]
  _DWORD lParam[3]; // [rsp+50h] [rbp-51h] BYREF
  LOGFONTA lf; // [rsp+5Ch] [rbp-45h] BYREF
  char v25; // [rsp+98h] [rbp-9h]

  v22 = a1;
  lpLogfont = 0;
  LOWORD(pvBuffer) = 0;
  v19[0] = 0;
  memset_0(lParam, 0, 0x4Cu);
  if ( !(unsigned int)AllocConvertToMultiByte(&lpLogfont, &pvBuffer, *(_QWORD *)(a1 + 88)) )
    return 0;
  v11 = (HDC)AllocDC(v19);
  if ( !v11 )
  {
    v12 = (CHAR *)lpLogfont;
    *(_DWORD *)(a7 + 944) = 520;
LABEL_5:
    T2free(v12);
    return 0;
  }
  v13 = (CHAR *)lpLogfont;
  v25 = *(_BYTE *)(a1 + 27);
  lParam[1] = *(_DWORD *)(a1 + 28);
  lParam[0] = 0;
  EnumFontFamiliesA(v11, lpLogfont, EnumFontFamProc, (LPARAM)lParam);
  v14 = 1;
  if ( !lParam[0] )
  {
    *a3 = 0;
    goto LABEL_21;
  }
  pvBuffer = 0;
  *a3 = 1;
  if ( !lParam[2] )
  {
LABEL_21:
    *a2 = 0;
    goto LABEL_22;
  }
  if ( !a5 || a6 )
    lf.lfClipPrecision |= 0x80u;
  v15 = CreateFontIndirectA(&lf);
  v16 = v15;
  if ( !v15 )
  {
    v17 = v19[0];
    *(_DWORD *)(a7 + 944) = 516;
    FreeDC(v11, v17);
    v12 = v13;
    goto LABEL_5;
  }
  v18 = SelectObject(v11, v15);
  if ( v18 )
  {
    *a2 = (unsigned __int16)GetFontData(v11, 0x64616568u, 8u, &pvBuffer, 4u) == 4
       && *(_DWORD *)(v22 + 60) == (HIBYTE(pvBuffer)
                                  | ((BYTE2(pvBuffer) | ((BYTE1(pvBuffer) | ((unsigned __int8)pvBuffer << 8)) << 8)) << 8));
    SelectObject(v11, v18);
  }
  else
  {
    *(_DWORD *)(a7 + 944) = 516;
    v14 = 0;
  }
  DeleteObject(v16);
LABEL_22:
  FreeDC(v11, v19[0]);
  T2free(v13);
  return v14;
}

```

## disassembly

```asm
0x180019f9c  mov     [rsp-8+arg_18], rbx
0x180019fa1  push    rbp
0x180019fa2  push    rsi
0x180019fa3  push    rdi
0x180019fa4  push    r12
0x180019fa6  push    r13
0x180019fa8  push    r14
0x180019faa  push    r15
0x180019fac  lea     rbp, [rsp-0Fh]
0x180019fb1  sub     rsp, 0B0h
0x180019fb8  mov     rax, cs:__security_cookie
0x180019fbf  xor     rax, rsp
0x180019fc2  mov     [rbp+3Fh+var_40], rax
0x180019fc6  mov     r14, [rbp+3Fh+arg_30]
0x180019fca  xor     r12d, r12d
0x180019fcd  mov     rsi, r8
0x180019fd0  mov     [rbp+3Fh+var_A0], rcx
0x180019fd4  mov     r15, rdx
0x180019fd7  mov     [rbp+3Fh+lpLogfont], r12
0x180019fdb  mov     rdi, rcx
0x180019fde  mov     word ptr [rbp+3Fh+pvBuffer], r12w
0x180019fe3  lea     r8d, [r12+4Ch]; Size
0x180019fe8  mov     [rbp+3Fh+var_B0], r12w
0x180019fed  xor     edx, edx; Val
0x180019fef  lea     rcx, [rbp+3Fh+lParam]; void *
0x180019ff3  call    memset_0
0x180019ff8  mov     r8, [rdi+58h]
0x180019ffc  lea     rdx, [rbp+3Fh+pvBuffer]
0x18001a000  lea     rcx, [rbp+3Fh+lpLogfont]
0x18001a004  call    AllocConvertToMultiByte
0x18001a009  test    eax, eax
0x18001a00b  jnz     short loc_18001A014
0x18001a00d  xor     eax, eax
0x18001a00f  jmp     loc_18001A177
0x18001a014  lea     rcx, [rbp+3Fh+var_B0]
0x18001a018  call    AllocDC
0x18001a01d  mov     rbx, rax
0x18001a020  test    rax, rax
0x18001a023  jnz     short loc_18001A03B
0x18001a025  mov     rcx, [rbp+3Fh+lpLogfont]; lpMem
0x18001a029  mov     dword ptr [r14+3B0h], 208h
0x18001a034  call    T2free
0x18001a039  jmp     short loc_18001A00D
0x18001a03b  mov     al, [rdi+1Bh]
0x18001a03e  lea     r9, [rbp+3Fh+lParam]; lParam
0x18001a042  mov     r13, [rbp+3Fh+lpLogfont]
0x18001a046  lea     r8, EnumFontFamProc; lpProc
0x18001a04d  mov     [rbp+3Fh+var_48], al
0x18001a050  mov     rdx, r13; lpLogfont
0x18001a053  mov     eax, [rdi+1Ch]
0x18001a056  mov     rcx, rbx; hdc
0x18001a059  mov     dword ptr [rbp+3Fh+lParam+4], eax
0x18001a05c  mov     dword ptr [rbp+3Fh+lParam], r12d
0x18001a060  call    cs:__imp_EnumFontFamiliesA
0x18001a066  mov     edi, 1
0x18001a06b  cmp     dword ptr [rbp+3Fh+lParam], r12d
0x18001a06f  jz      loc_18001A15B
0x18001a075  mov     [rbp+3Fh+pvBuffer], r12d
0x18001a079  mov     [rsi], edi
0x18001a07b  cmp     [rbp+3Fh+var_88], r12d
0x18001a07f  jz      loc_18001A15E
0x18001a085  cmp     [rbp+3Fh+arg_20], r12d
0x18001a089  jz      short loc_18001A091
0x18001a08b  cmp     [rbp+3Fh+arg_28], r12d
0x18001a08f  jz      short loc_18001A095
0x18001a091  or      [rbp+3Fh+lf.lfClipPrecision], 80h
0x18001a095  lea     rcx, [rbp+3Fh+lf]; lplf
0x18001a099  call    cs:__imp_CreateFontIndirectA
0x18001a09f  mov     rsi, rax
0x18001a0a2  mov     rcx, rbx; hdc
0x18001a0a5  test    rax, rax
0x18001a0a8  jnz     short loc_18001A0C6
0x18001a0aa  movzx   edx, [rbp+3Fh+var_B0]
0x18001a0ae  mov     dword ptr [r14+3B0h], 204h
0x18001a0b9  call    FreeDC
0x18001a0be  mov     rcx, r13
0x18001a0c1  jmp     loc_18001A034
0x18001a0c6  mov     rdx, rsi; h
0x18001a0c9  call    cs:__imp_SelectObject
0x18001a0cf  mov     r12, rax
0x18001a0d2  test    rax, rax
0x18001a0d5  jnz     short loc_18001A0E6
0x18001a0d7  mov     dword ptr [r14+3B0h], 204h
0x18001a0e2  xor     edi, edi
0x18001a0e4  jmp     short loc_18001A150
0x18001a0e6  mov     r14d, 4
0x18001a0ec  lea     r9, [rbp+3Fh+pvBuffer]; pvBuffer
0x18001a0f0  mov     edx, 64616568h; dwTable
0x18001a0f5  mov     [rsp+0E0h+cjBuffer], r14d; cjBuffer
0x18001a0fa  mov     rcx, rbx; hdc
0x18001a0fd  lea     r8d, [r14+4]; dwOffset
0x18001a101  call    cs:__imp_GetFontData
0x18001a107  cmp     ax, r14w
0x18001a10b  jz      short loc_18001A116
0x18001a10d  mov     dword ptr [r15], 0
0x18001a114  jmp     short loc_18001A144
0x18001a116  movzx   eax, byte ptr [rbp+3Fh+pvBuffer+1]
0x18001a11a  movzx   ecx, byte ptr [rbp+3Fh+pvBuffer]
0x18001a11e  mov     rdx, [rbp+3Fh+var_A0]
0x18001a122  shl     ecx, 8
0x18001a125  or      ecx, eax
0x18001a127  movzx   eax, byte ptr [rbp+3Fh+pvBuffer+2]
0x18001a12b  shl     ecx, 8
0x18001a12e  or      ecx, eax
0x18001a130  movzx   eax, byte ptr [rbp+3Fh+pvBuffer+3]
0x18001a134  shl     ecx, 8
0x18001a137  or      ecx, eax
0x18001a139  xor     eax, eax
0x18001a13b  cmp     [rdx+3Ch], ecx
0x18001a13e  setz    al
0x18001a141  mov     [r15], eax
0x18001a144  mov     rdx, r12; h
0x18001a147  mov     rcx, rbx; hdc
0x18001a14a  call    cs:__imp_SelectObject
0x18001a150  mov     rcx, rsi; ho
0x18001a153  call    cs:__imp_DeleteObject
0x18001a159  jmp     short loc_18001A161
0x18001a15b  mov     [rsi], r12d
0x18001a15e  mov     [r15], r12d
0x18001a161  movzx   edx, [rbp+3Fh+var_B0]
0x18001a165  mov     rcx, rbx
0x18001a168  call    FreeDC
0x18001a16d  mov     rcx, r13; lpMem
0x18001a170  call    T2free
0x18001a175  mov     eax, edi
0x18001a177  mov     rcx, [rbp+3Fh+var_40]
0x18001a17b  xor     rcx, rsp; StackCookie
0x18001a17e  call    __security_check_cookie
0x18001a183  mov     rbx, [rsp+0E0h+arg_18]
0x18001a18b  add     rsp, 0B0h
0x18001a192  pop     r15
0x18001a194  pop     r14
0x18001a196  pop     r13
0x18001a198  pop     r12
0x18001a19a  pop     rdi
0x18001a19b  pop     rsi
0x18001a19c  pop     rbp
0x18001a19d  retn
```
