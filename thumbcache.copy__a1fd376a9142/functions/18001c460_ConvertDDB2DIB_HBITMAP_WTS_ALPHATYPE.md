# ConvertDDB2DIB(HBITMAP__ *,WTS_ALPHATYPE *)

- ea: `0x18001c460`
- end: `0x18001c6e8`
- name: `?ConvertDDB2DIB@@YAPEAUHBITMAP__@@PEAU1@PEAW4WTS_ALPHATYPE@@@Z`
- size: `648`
- prototype: `HBITMAP __fastcall(HBITMAP h, enum WTS_ALPHATYPE *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18001c134`

## callees

- `0x18001c460`
- `0x180035830`

## import_xrefs

- `ext-ms-win-gdi-draw-l1-1-0!BitBlt` at `0x18001c6ab`
- `ext-ms-win-gdi-draw-l1-1-0!BitBlt` at `0x18001c6ab`
- `ext-ms-win-gdi-draw-l1-1-0!CreateDIBSection` at `0x18001c574`
- `ext-ms-win-gdi-draw-l1-1-0!CreateDIBSection` at `0x18001c62f`
- `ext-ms-win-gdi-draw-l1-1-0!CreateDIBSection` at `0x18001c574`
- `ext-ms-win-gdi-draw-l1-1-0!CreateDIBSection` at `0x18001c62f`
- `ext-ms-win-gdi-draw-l1-1-0!GetBitmapBits` at `0x18001c59e`
- `ext-ms-win-gdi-draw-l1-1-0!GetBitmapBits` at `0x18001c59e`
- `GDI32!CreateCompatibleDC` at `0x18001c644`
- `GDI32!CreateCompatibleDC` at `0x18001c650`
- `GDI32!CreateCompatibleDC` at `0x18001c644`
- `GDI32!CreateCompatibleDC` at `0x18001c650`
- `GDI32!DeleteDC` at `0x18001c6cc`
- `GDI32!DeleteDC` at `0x18001c6da`
- `GDI32!DeleteDC` at `0x18001c6cc`
- `GDI32!DeleteDC` at `0x18001c6da`
- `GDI32!SelectObject` at `0x18001c669`
- `GDI32!SelectObject` at `0x18001c678`
- `GDI32!SelectObject` at `0x18001c6b7`
- `GDI32!SelectObject` at `0x18001c6c3`
- `GDI32!SelectObject` at `0x18001c669`
- `GDI32!SelectObject` at `0x18001c678`
- `GDI32!SelectObject` at `0x18001c6b7`
- `GDI32!SelectObject` at `0x18001c6c3`
- `GDI32!GetObjectW` at `0x18001c4c5`
- `GDI32!GetObjectW` at `0x18001c4c5`
- `USER32!ReleaseDC` at `0x18001c5b8`
- `USER32!ReleaseDC` at `0x18001c5b8`
- `USER32!GetDC` at `0x18001c4df`
- `USER32!GetDC` at `0x18001c4df`

## pseudocode

```c
HBITMAP __fastcall ConvertDDB2DIB(HBITMAP h, enum WTS_ALPHATYPE *a2)
{
  HBITMAP v4; // rsi
  HDC DC; // r12
  HBITMAP v7; // rdi
  char *v8; // rdx
  LONG biHeight; // ecx
  int i; // ecx
  HBITMAP v11; // r15
  HDC CompatibleDC; // r14
  HDC v13; // rax
  HDC v14; // rsi
  HGDIOBJ v15; // rdi
  HGDIOBJ v16; // rbx
  void *ppvBits; // [rsp+50h] [rbp-39h] BYREF
  __int128 pv; // [rsp+58h] [rbp-31h] BYREF
  __int128 v19; // [rsp+68h] [rbp-21h]
  BITMAPINFO pbmi; // [rsp+78h] [rbp-11h] BYREF

  v4 = 0;
  if ( !h )
    return 0;
  pv = 0;
  v19 = 0;
  GetObjectW(h, 32, &pv);
  if ( *((_QWORD *)&v19 + 1) )
    return h;
  DC = GetDC(0);
  if ( !DC )
    return 0;
  memset(&pbmi.bmiHeader.biBitCount, 0, 30);
  pbmi.bmiHeader.biWidth = DWORD1(pv);
  pbmi.bmiHeader.biHeight = -DWORD2(pv);
  pbmi.bmiHeader.biSize = 40;
  pbmi.bmiHeader.biPlanes = 1;
  ppvBits = 0;
  if ( ((WORD1(v19) - 24) & 0xFFF7) != 0 )
  {
    pbmi.bmiHeader.biBitCount = 24;
    v11 = CreateDIBSection(DC, &pbmi, 0, &ppvBits, 0, 0);
    if ( v11 )
    {
      CompatibleDC = CreateCompatibleDC(DC);
      v13 = CreateCompatibleDC(DC);
      v14 = v13;
      if ( CompatibleDC )
      {
        if ( v13 )
        {
          v15 = SelectObject(CompatibleDC, v11);
          v16 = SelectObject(v14, h);
          BitBlt(CompatibleDC, 0, 0, SDWORD1(pv), SDWORD2(pv), v14, 0, 0, 0xCC0020u);
          SelectObject(CompatibleDC, v15);
          SelectObject(v14, v16);
        }
        DeleteDC(CompatibleDC);
      }
      if ( v14 )
        DeleteDC(v14);
      v4 = v11;
    }
  }
  else
  {
    pbmi.bmiHeader.biBitCount = WORD1(v19) * v19;
    v7 = CreateDIBSection(DC, &pbmi, 0, &ppvBits, 0, 0);
    if ( v7 )
    {
      GetBitmapBits(h, DWORD1(pv) * DWORD2(pv) * pbmi.bmiHeader.biBitCount / 8, ppvBits);
      v4 = v7;
      if ( WORD1(v19) == 32 && *a2 == WTSAT_UNKNOWN )
      {
        v8 = (char *)ppvBits;
        biHeight = -pbmi.bmiHeader.biHeight;
        if ( pbmi.bmiHeader.biHeight > 0 )
          biHeight = pbmi.bmiHeader.biHeight;
        for ( i = pbmi.bmiHeader.biWidth * biHeight; i > 0; v8 += 4 )
        {
          --i;
          v8[3] = -1;
        }
        *a2 = WTSAT_RGB;
      }
    }
  }
  ReleaseDC(0, DC);
  return v4;
}

```

## disassembly

```asm
0x18001c460  push    rbp
0x18001c462  push    rbx
0x18001c463  push    rsi
0x18001c464  push    r13
0x18001c466  push    r14
0x18001c468  lea     rbp, [rsp-37h]
0x18001c46d  sub     rsp, 0C0h
0x18001c474  mov     rax, cs:__security_cookie
0x18001c47b  xor     rax, rsp
0x18001c47e  mov     [rbp+57h+var_38], rax
0x18001c482  xor     r13d, r13d
0x18001c485  mov     r14, rdx
0x18001c488  mov     rbx, rcx
0x18001c48b  mov     esi, r13d
0x18001c48e  test    rcx, rcx
0x18001c491  jnz     short loc_18001C4B1
0x18001c493  mov     eax, r13d
0x18001c496  mov     rcx, [rbp+57h+var_38]
0x18001c49a  xor     rcx, rsp; StackCookie
0x18001c49d  call    __security_check_cookie
0x18001c4a2  add     rsp, 0C0h
0x18001c4a9  pop     r14
0x18001c4ab  pop     r13
0x18001c4ad  pop     rsi
0x18001c4ae  pop     rbx
0x18001c4af  pop     rbp
0x18001c4b0  retn
0x18001c4b1  xorps   xmm0, xmm0
0x18001c4b4  lea     r8, [rbp+57h+pv]; pv
0x18001c4b8  mov     edx, 20h ; ' '; c
0x18001c4bd  movups  [rbp+57h+pv], xmm0
0x18001c4c1  movups  [rbp+57h+var_78], xmm0
0x18001c4c5  call    cs:__imp_GetObjectW
0x18001c4cb  cmp     qword ptr [rbp+57h+var_78+8], rsi
0x18001c4cf  jnz     loc_18001C5DE
0x18001c4d5  xor     ecx, ecx; hWnd
0x18001c4d7  mov     [rsp+0E0h+var_28], r12
0x18001c4df  call    cs:__imp_GetDC
0x18001c4e5  mov     r12, rax
0x18001c4e8  test    rax, rax
0x18001c4eb  jz      loc_18001C5E6
0x18001c4f1  movzx   ecx, word ptr [rbp+57h+var_78+2]
0x18001c4f5  lea     r9, [rbp+57h+ppvBits]; ppvBits
0x18001c4f9  xor     eax, eax
0x18001c4fb  mov     [rsp+0E0h+var_30], r15
0x18001c503  mov     qword ptr [rbp+57h+pbmi.bmiHeader.biClrImportant], rax
0x18001c507  xorps   xmm0, xmm0
0x18001c50a  mov     eax, dword ptr [rbp+57h+pv+4]
0x18001c50d  mov     edx, 0FFF7h
0x18001c512  movups  xmmword ptr [rbp+57h+pbmi.bmiHeader.biWidth], xmm0
0x18001c516  mov     [rbp+57h+pbmi.bmiHeader.biWidth], eax
0x18001c519  xor     r8d, r8d; usage
0x18001c51c  mov     eax, dword ptr [rbp+57h+pv+8]
0x18001c51f  mov     r15d, 1
0x18001c525  neg     eax
0x18001c527  mov     [rsp+0E0h+offset], r13d; offset
0x18001c52c  mov     [rbp+57h+pbmi.bmiHeader.biHeight], eax
0x18001c52f  lea     eax, [rcx-18h]
0x18001c532  test    dx, ax
0x18001c535  mov     [rsp+0E0h+arg_10], rdi
0x18001c53d  lea     rdx, [rbp+57h+pbmi]; pbmi
0x18001c541  mov     [rbp+57h+pbmi.bmiHeader.biSize], 28h ; '('
0x18001c548  movups  xmmword ptr [rbp+57h+pbmi.bmiHeader.biSizeImage], xmm0
0x18001c54c  mov     [rbp+57h+pbmi.bmiHeader.biPlanes], r15w
0x18001c551  mov     [rbp+57h+pbmi.bmiHeader.biCompression], r13d
0x18001c555  mov     [rbp+57h+ppvBits], r13
0x18001c559  mov     [rsp+0E0h+hSection], r13; hSection
0x18001c55e  jnz     loc_18001C623
0x18001c564  mov     eax, ecx
0x18001c566  movzx   ecx, word ptr [rbp+57h+var_78]
0x18001c56a  imul    ecx, eax
0x18001c56d  mov     [rbp+57h+pbmi.bmiHeader.biBitCount], cx
0x18001c571  mov     rcx, r12; hdc
0x18001c574  call    cs:__imp_CreateDIBSection
0x18001c57a  mov     rdi, rax
0x18001c57d  test    rax, rax
0x18001c580  jz      short loc_18001C5B3
0x18001c582  movzx   eax, [rbp+57h+pbmi.bmiHeader.biBitCount]
0x18001c586  mov     rcx, rbx; hbit
0x18001c589  imul    eax, dword ptr [rbp+57h+pv+8]
0x18001c58d  mov     r8, [rbp+57h+ppvBits]; lpvBits
0x18001c591  imul    eax, dword ptr [rbp+57h+pv+4]
0x18001c595  cdq
0x18001c596  and     edx, 7
0x18001c599  add     edx, eax
0x18001c59b  sar     edx, 3; cb
0x18001c59e  call    cs:__imp_GetBitmapBits
0x18001c5a4  cmp     word ptr [rbp+57h+var_78+2], 20h ; ' '
0x18001c5a9  mov     rsi, rdi
0x18001c5ac  jnz     short loc_18001C5B3
0x18001c5ae  cmp     [r14], r13d
0x18001c5b1  jz      short loc_18001C5F6
0x18001c5b3  mov     rdx, r12; hDC
0x18001c5b6  xor     ecx, ecx; hWnd
0x18001c5b8  call    cs:__imp_ReleaseDC
0x18001c5be  mov     r15, [rsp+0E0h+var_30]
0x18001c5c6  mov     rax, rsi
0x18001c5c9  mov     rdi, [rsp+0E0h+arg_10]
0x18001c5d1  mov     r12, [rsp+0E0h+var_28]
0x18001c5d9  jmp     loc_18001C496
0x18001c5de  mov     rax, rbx
0x18001c5e1  jmp     loc_18001C496
0x18001c5e6  mov     r12, [rsp+0E0h+var_28]
0x18001c5ee  mov     rax, r13
0x18001c5f1  jmp     loc_18001C496
0x18001c5f6  mov     ecx, [rbp+57h+pbmi.bmiHeader.biHeight]
0x18001c5f9  mov     rdx, [rbp+57h+ppvBits]
0x18001c5fd  neg     ecx
0x18001c5ff  cmovs   ecx, [rbp+57h+pbmi.bmiHeader.biHeight]
0x18001c603  imul    ecx, [rbp+57h+pbmi.bmiHeader.biWidth]
0x18001c607  test    ecx, ecx
0x18001c609  jle     short loc_18001C61E
0x18001c60b  nop     dword ptr [rax+rax+00h]
0x18001c610  dec     ecx
0x18001c612  mov     byte ptr [rdx+3], 0FFh
0x18001c616  lea     rdx, [rdx+4]
0x18001c61a  test    ecx, ecx
0x18001c61c  jg      short loc_18001C610
0x18001c61e  mov     [r14], r15d
0x18001c621  jmp     short loc_18001C5B3
0x18001c623  mov     eax, 18h
0x18001c628  mov     rcx, r12; hdc
0x18001c62b  mov     [rbp+57h+pbmi.bmiHeader.biBitCount], ax
0x18001c62f  call    cs:__imp_CreateDIBSection
0x18001c635  mov     r15, rax
0x18001c638  test    rax, rax
0x18001c63b  jz      loc_18001C5B3
0x18001c641  mov     rcx, r12; hdc
0x18001c644  call    cs:__imp_CreateCompatibleDC
0x18001c64a  mov     rcx, r12; hdc
0x18001c64d  mov     r14, rax
0x18001c650  call    cs:__imp_CreateCompatibleDC
0x18001c656  mov     rsi, rax
0x18001c659  test    r14, r14
0x18001c65c  jz      short loc_18001C6D2
0x18001c65e  test    rax, rax
0x18001c661  jz      short loc_18001C6C9
0x18001c663  mov     rdx, r15; h
0x18001c666  mov     rcx, r14; hdc
0x18001c669  call    cs:__imp_SelectObject
0x18001c66f  mov     rdx, rbx; h
0x18001c672  mov     rcx, rsi; hdc
0x18001c675  mov     rdi, rax
0x18001c678  call    cs:__imp_SelectObject
0x18001c67e  mov     r9d, dword ptr [rbp+57h+pv+4]; cx
0x18001c682  xor     r8d, r8d; y
0x18001c685  mov     [rsp+0E0h+rop], 0CC0020h; rop
0x18001c68d  mov     rbx, rax
0x18001c690  mov     eax, dword ptr [rbp+57h+pv+8]
0x18001c693  xor     edx, edx; x
0x18001c695  mov     [rsp+0E0h+y1], r13d; y1
0x18001c69a  mov     rcx, r14; hdc
0x18001c69d  mov     [rsp+0E0h+x1], r13d; x1
0x18001c6a2  mov     qword ptr [rsp+0E0h+offset], rsi; hdcSrc
0x18001c6a7  mov     dword ptr [rsp+0E0h+hSection], eax; cy
0x18001c6ab  call    cs:__imp_BitBlt
0x18001c6b1  mov     rdx, rdi; h
0x18001c6b4  mov     rcx, r14; hdc
0x18001c6b7  call    cs:__imp_SelectObject
0x18001c6bd  mov     rdx, rbx; h
0x18001c6c0  mov     rcx, rsi; hdc
0x18001c6c3  call    cs:__imp_SelectObject
0x18001c6c9  mov     rcx, r14; hdc
0x18001c6cc  call    cs:__imp_DeleteDC
0x18001c6d2  test    rsi, rsi
0x18001c6d5  jz      short loc_18001C6E0
0x18001c6d7  mov     rcx, rsi; hdc
0x18001c6da  call    cs:__imp_DeleteDC
0x18001c6e0  mov     rsi, r15
0x18001c6e3  jmp     loc_18001C5B3
```
