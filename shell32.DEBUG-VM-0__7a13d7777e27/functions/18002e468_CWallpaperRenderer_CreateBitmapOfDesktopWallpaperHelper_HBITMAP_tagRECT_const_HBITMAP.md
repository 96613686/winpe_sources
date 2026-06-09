# CWallpaperRenderer::_CreateBitmapOfDesktopWallpaperHelper(HBITMAP__ *,tagRECT const &,HBITMAP__ * *)

- ea: `0x18002e468`
- end: `0x18002e903`
- name: `?_CreateBitmapOfDesktopWallpaperHelper@CWallpaperRenderer@@AEBA_NPEAUHBITMAP__@@AEBUtagRECT@@PEAPEAU2@@Z`
- size: `1179`
- prototype: `bool(CWallpaperRenderer *__hidden this, HBITMAP, const struct tagRECT *, HBITMAP *)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18002d9a4`
- `0x180499840`

## callees

- `0x18002e468`
- `0x180233280`

## import_xrefs

- `USER32!CopyRect` at `0x18002e7ba`
- `USER32!CopyRect` at `0x18002e7ba`
- `USER32!FillRect` at `0x18002e5c4`
- `USER32!FillRect` at `0x18002e5c4`
- `USER32!GetSystemMetrics` at `0x18002e5f2`
- `USER32!GetSystemMetrics` at `0x18002e602`
- `USER32!GetSystemMetrics` at `0x18002e7d5`
- `USER32!GetSystemMetrics` at `0x18002e7e2`
- `USER32!GetSystemMetrics` at `0x18002e85d`
- `USER32!GetSystemMetrics` at `0x18002e86b`
- `USER32!GetSystemMetrics` at `0x18002e5f2`
- `USER32!GetSystemMetrics` at `0x18002e602`
- `USER32!GetSystemMetrics` at `0x18002e7d5`
- `USER32!GetSystemMetrics` at `0x18002e7e2`
- `USER32!GetSystemMetrics` at `0x18002e85d`
- `USER32!GetSystemMetrics` at `0x18002e86b`
- `GDI32!DeleteObject` at `0x18002e702`
- `GDI32!DeleteObject` at `0x18002e702`
- `GDI32!CreateCompatibleDC` at `0x18002e4cb`
- `GDI32!CreateCompatibleDC` at `0x18002e555`
- `GDI32!CreateCompatibleDC` at `0x18002e4cb`
- `GDI32!CreateCompatibleDC` at `0x18002e555`
- `GDI32!SelectObject` at `0x18002e4e3`
- `GDI32!SelectObject` at `0x18002e594`
- `GDI32!SelectObject` at `0x18002e6f9`
- `GDI32!SelectObject` at `0x18002e70f`
- `GDI32!SelectObject` at `0x18002e4e3`
- `GDI32!SelectObject` at `0x18002e594`
- `GDI32!SelectObject` at `0x18002e6f9`
- `GDI32!SelectObject` at `0x18002e70f`
- `GDI32!DeleteDC` at `0x18002e718`
- `GDI32!DeleteDC` at `0x18002e718`
- `GDI32!BitBlt` at `0x18002e667`
- `GDI32!BitBlt` at `0x18002e6d9`
- `GDI32!BitBlt` at `0x18002e8d2`
- `GDI32!BitBlt` at `0x18002e667`
- `GDI32!BitBlt` at `0x18002e6d9`
- `GDI32!BitBlt` at `0x18002e8d2`
- `GDI32!GetObjectW` at `0x18002e50d`
- `GDI32!GetObjectW` at `0x18002e50d`
- `GDI32!CreateCompatibleBitmap` at `0x18002e578`
- `GDI32!CreateCompatibleBitmap` at `0x18002e578`

## pseudocode

```c
bool __fastcall CWallpaperRenderer::_CreateBitmapOfDesktopWallpaperHelper(
        CWallpaperRenderer *this,
        HBITMAP a2,
        const struct tagRECT *a3,
        HBITMAP *a4)
{
  LONG right; // r15d
  LONG bottom; // r12d
  int v9; // r14d
  HDC CompatibleDC; // rax
  HDC hdcSrc; // r13
  int v12; // r8d
  int v13; // ebx
  int v14; // edi
  HDC v15; // r14
  int v16; // r15d
  int v17; // r12d
  HBITMAP CompatibleBitmap; // rax
  int y1; // r10d
  LONG v20; // ebx
  int v21; // eax
  LONG v22; // edi
  int v23; // ebx
  int v24; // eax
  int v25; // r9d
  int cy; // ecx
  int v27; // r15d
  int i; // edi
  int j; // ebx
  BOOL v30; // eax
  int v31; // edx
  int v32; // eax
  int v33; // r15d
  int v34; // r8d
  int v35; // edx
  int x1; // r9d
  int v38; // eax
  int v39; // edx
  int v40; // eax
  int v41; // r12d
  int v42; // eax
  const RECT *v43; // rdx
  int SystemMetrics; // ebx
  int v45; // r8d
  int v46; // ebx
  int v47; // eax
  int v48; // r14d
  int v49; // eax
  int v50; // eax
  bool v51; // [rsp+50h] [rbp-49h]
  int v52; // [rsp+54h] [rbp-45h]
  LONG left; // [rsp+58h] [rbp-41h]
  LONG top; // [rsp+5Ch] [rbp-3Dh]
  HGDIOBJ ha; // [rsp+60h] [rbp-39h]
  HGDIOBJ v57; // [rsp+68h] [rbp-31h]
  RECT rc; // [rsp+70h] [rbp-29h] BYREF
  _OWORD pv[2]; // [rsp+80h] [rbp-19h] BYREF

  right = a3->right;
  bottom = a3->bottom;
  v9 = 5;
  left = a3->left;
  top = a3->top;
  v51 = 0;
  if ( !*((_BYTE *)this + 48) )
    v9 = *((_DWORD *)this + 6);
  v52 = v9;
  CompatibleDC = CreateCompatibleDC(0);
  hdcSrc = CompatibleDC;
  if ( CompatibleDC )
  {
    v57 = SelectObject(CompatibleDC, a2);
    if ( !v57 )
    {
LABEL_35:
      DeleteDC(hdcSrc);
      return v51;
    }
    memset(pv, 0, sizeof(pv));
    if ( GetObjectW(a2, 32, pv) != 32 )
      goto LABEL_34;
    rc = 0;
    if ( v9 == 5 )
    {
      if ( *((_DWORD *)this + 6) == 3 && (v43 = (const RECT *)*((_QWORD *)this + 2)) != 0 )
      {
        CopyRect(&rc, v43 + 1);
        SystemMetrics = rc.right - rc.left;
        v45 = rc.bottom - rc.top;
      }
      else
      {
        SystemMetrics = GetSystemMetrics(78);
        v45 = GetSystemMetrics(79);
      }
      v46 = (SystemMetrics - DWORD1(pv[0])) / 2;
      v47 = (v45 - DWORD2(pv[0])) / ((*((_DWORD *)this + 6) != 3) + 2);
      v48 = v47;
      if ( *((_DWORD *)this + 6) == 3 && *((_QWORD *)this + 2) )
      {
        v14 = v46 + rc.left;
        v13 = v47 + rc.top;
      }
      else
      {
        v14 = v46 + GetSystemMetrics(76);
        v13 = v48 + GetSystemMetrics(77);
      }
    }
    else
    {
      v12 = a3->bottom - a3->top;
      if ( v9 == 1 || v9 == 2 )
      {
        v13 = 0;
        v14 = 0;
      }
      else
      {
        v14 = (a3->right - a3->left - DWORD1(pv[0])) / 2;
        v13 = v9 == 4 ? (v12 - DWORD2(pv[0])) / 3 : (v12 - DWORD2(pv[0])) / 2;
      }
    }
    v15 = CreateCompatibleDC(0);
    if ( !v15 )
    {
LABEL_34:
      SelectObject(hdcSrc, v57);
      goto LABEL_35;
    }
    v16 = right - left;
    v17 = bottom - top;
    CompatibleBitmap = CreateCompatibleBitmap(hdcSrc, v16, v17);
    *a4 = CompatibleBitmap;
    if ( !CompatibleBitmap || (ha = SelectObject(v15, CompatibleBitmap)) == 0 )
    {
LABEL_33:
      DeleteObject(v15);
      goto LABEL_34;
    }
    *(_QWORD *)&rc.left = 0;
    rc.right = v16;
    rc.bottom = v17;
    FillRect(v15, &rc, (HBRUSH)2);
    if ( v52 == 1 )
    {
      v20 = a3->left;
      v21 = GetSystemMetrics(76);
      v22 = a3->top;
      v23 = v20 - v21;
      v24 = GetSystemMetrics(77);
      v25 = DWORD1(pv[0]);
      cy = DWORD2(pv[0]);
      v27 = a3->left - v23 % SDWORD1(pv[0]);
      for ( i = v22 - (v22 - v24) % SDWORD2(pv[0]); i < a3->bottom; i += cy )
      {
        for ( j = v27; j < a3->right; j += DWORD1(pv[0]) )
        {
          v30 = BitBlt(v15, j - a3->left, i - a3->top, v25, cy, hdcSrc, 0, 0, 0xCC0020u);
          v25 = DWORD1(pv[0]);
          cy = DWORD2(pv[0]);
          v51 = v30;
        }
      }
      goto LABEL_32;
    }
    if ( v52 == 5 )
    {
      v51 = BitBlt(v15, v14 - a3->left, v13 - a3->top, SDWORD1(pv[0]), SDWORD2(pv[0]), hdcSrc, 0, 0, 0xCC0020u);
LABEL_32:
      SelectObject(v15, ha);
      goto LABEL_33;
    }
    if ( v13 < 0 )
      y1 = -v13;
    else
      y1 = 0;
    if ( v14 >= 0 )
      x1 = 0;
    else
      x1 = -v14;
    if ( v13 > 0 )
    {
      v38 = v13;
    }
    else
    {
      v38 = 0;
      if ( v13 < 0 )
      {
        v39 = v13;
        goto LABEL_45;
      }
    }
    v39 = 0;
LABEL_45:
    if ( v17 - v38 >= v39 + DWORD2(pv[0]) )
    {
      v49 = 0;
      if ( v13 < 0 )
        v49 = v13;
      v41 = v49 + DWORD2(pv[0]);
    }
    else
    {
      v40 = 0;
      if ( v13 > 0 )
        v40 = v13;
      v41 = v17 - v40;
    }
    if ( v14 > 0 )
    {
      v42 = v14;
    }
    else
    {
      v42 = 0;
      if ( v14 < 0 )
      {
        v31 = v14;
        goto LABEL_23;
      }
    }
    v31 = 0;
LABEL_23:
    if ( v16 - v42 >= v31 + DWORD1(pv[0]) )
    {
      v50 = 0;
      if ( v14 < 0 )
        v50 = v14;
      v33 = v50 + DWORD1(pv[0]);
    }
    else
    {
      v32 = 0;
      if ( v14 > 0 )
        v32 = v14;
      v33 = v16 - v32;
    }
    v34 = 0;
    if ( v13 > 0 )
      v34 = v13;
    v35 = 0;
    if ( v14 > 0 )
      v35 = v14;
    v51 = BitBlt(v15, v35, v34, v33, v41, hdcSrc, x1, y1, 0xCC0020u);
    goto LABEL_32;
  }
  return v51;
}

```

## disassembly

```asm
0x18002e468  push    rbp
0x18002e46a  push    rbx
0x18002e46b  push    rsi
0x18002e46c  push    rdi
0x18002e46d  push    r12
0x18002e46f  push    r13
0x18002e471  push    r14
0x18002e473  push    r15
0x18002e475  lea     rbp, [rsp-1Fh]
0x18002e47a  sub     rsp, 0B8h
0x18002e481  mov     rax, cs:__security_cookie
0x18002e488  xor     rax, rsp
0x18002e48b  mov     [rbp+57h+var_50], rax
0x18002e48f  cmp     byte ptr [rcx+30h], 0
0x18002e493  mov     rsi, r8
0x18002e496  mov     eax, [r8]
0x18002e499  mov     rbx, rdx
0x18002e49c  mov     r15d, [r8+8]
0x18002e4a0  mov     rdi, rcx
0x18002e4a3  mov     r12d, [r8+0Ch]
0x18002e4a7  mov     r14d, 5
0x18002e4ad  mov     [rbp+57h+var_98], eax
0x18002e4b0  mov     eax, [r8+4]
0x18002e4b4  mov     [rbp+57h+var_94], eax
0x18002e4b7  mov     [rbp+57h+h], r9
0x18002e4bb  mov     byte ptr [rbp+57h+var_A0], 0
0x18002e4bf  jnz     short loc_18002E4C5
0x18002e4c1  mov     r14d, [rcx+18h]
0x18002e4c5  xor     ecx, ecx; hdc
0x18002e4c7  mov     [rbp+57h+var_9C], r14d
0x18002e4cb  call    cs:__imp_CreateCompatibleDC
0x18002e4d1  mov     r13, rax
0x18002e4d4  test    rax, rax
0x18002e4d7  jz      loc_18002E71E
0x18002e4dd  mov     rdx, rbx; h
0x18002e4e0  mov     rcx, rax; hdc
0x18002e4e3  call    cs:__imp_SelectObject
0x18002e4e9  mov     [rbp+57h+var_88], rax
0x18002e4ed  test    rax, rax
0x18002e4f0  jz      loc_18002E715
0x18002e4f6  xorps   xmm0, xmm0
0x18002e4f9  lea     r8, [rbp+57h+pv]; pv
0x18002e4fd  mov     edx, 20h ; ' '; c
0x18002e502  mov     rcx, rbx; h
0x18002e505  movups  [rbp+57h+pv], xmm0
0x18002e509  movups  [rbp+57h+var_60], xmm0
0x18002e50d  call    cs:__imp_GetObjectW
0x18002e513  cmp     eax, 20h ; ' '
0x18002e516  jnz     loc_18002E708
0x18002e51c  lea     r9d, [rax-1Eh]
0x18002e520  xorps   xmm0, xmm0
0x18002e523  movups  xmmword ptr [rbp+57h+rc.left], xmm0
0x18002e527  cmp     r14d, 5
0x18002e52b  jz      loc_18002E7A3
0x18002e531  mov     ebx, [rsi+8]
0x18002e534  mov     ecx, r14d
0x18002e537  mov     r8d, [rsi+0Ch]
0x18002e53b  sub     ebx, [rsi]
0x18002e53d  sub     r8d, [rsi+4]
0x18002e541  sub     ecx, 1
0x18002e544  jz      short loc_18002E54F
0x18002e546  sub     ecx, 1
0x18002e549  jnz     loc_18002E831
0x18002e54f  xor     ebx, ebx
0x18002e551  xor     edi, edi
0x18002e553  xor     ecx, ecx; hdc
0x18002e555  call    cs:__imp_CreateCompatibleDC
0x18002e55b  mov     r14, rax
0x18002e55e  test    rax, rax
0x18002e561  jz      loc_18002E708
0x18002e567  sub     r15d, [rbp+57h+var_98]
0x18002e56b  mov     rcx, r13; hdc
0x18002e56e  sub     r12d, [rbp+57h+var_94]
0x18002e572  mov     edx, r15d; cx
0x18002e575  mov     r8d, r12d; cy
0x18002e578  call    cs:__imp_CreateCompatibleBitmap
0x18002e57e  mov     rcx, [rbp+57h+h]
0x18002e582  mov     [rcx], rax
0x18002e585  test    rax, rax
0x18002e588  jz      loc_18002E6FF
0x18002e58e  mov     rdx, rax; h
0x18002e591  mov     rcx, r14; hdc
0x18002e594  call    cs:__imp_SelectObject
0x18002e59a  mov     [rbp+57h+h], rax
0x18002e59e  test    rax, rax
0x18002e5a1  jz      loc_18002E6FF
0x18002e5a7  mov     r8d, 2; hbr
0x18002e5ad  mov     qword ptr [rbp+57h+rc.left], 0
0x18002e5b5  lea     rdx, [rbp+57h+rc]; lprc
0x18002e5b9  mov     [rbp+57h+rc.right], r15d
0x18002e5bd  mov     rcx, r14; hDC
0x18002e5c0  mov     [rbp+57h+rc.bottom], r12d
0x18002e5c4  call    cs:__imp_FillRect
0x18002e5ca  mov     edx, [rbp+57h+var_9C]
0x18002e5cd  cmp     edx, 1
0x18002e5d0  jz      short loc_18002E5EB
0x18002e5d2  cmp     edx, 5
0x18002e5d5  jz      loc_18002E89D
0x18002e5db  test    ebx, ebx
0x18002e5dd  js      loc_18002E741
0x18002e5e3  xor     r10d, r10d
0x18002e5e6  jmp     loc_18002E747
0x18002e5eb  mov     ebx, [rsi]
0x18002e5ed  mov     ecx, 4Ch ; 'L'; nIndex
0x18002e5f2  call    cs:__imp_GetSystemMetrics
0x18002e5f8  mov     edi, [rsi+4]
0x18002e5fb  mov     ecx, 4Dh ; 'M'; nIndex
0x18002e600  sub     ebx, eax
0x18002e602  call    cs:__imp_GetSystemMetrics
0x18002e608  mov     r9d, dword ptr [rbp+57h+pv+4]; cx
0x18002e60c  mov     ecx, edi
0x18002e60e  mov     r15d, [rsi]
0x18002e611  sub     ecx, eax
0x18002e613  mov     eax, ebx
0x18002e615  cdq
0x18002e616  idiv    r9d
0x18002e619  mov     eax, ecx
0x18002e61b  mov     ecx, dword ptr [rbp+57h+pv+8]
0x18002e61e  sub     r15d, edx
0x18002e621  cdq
0x18002e622  idiv    ecx
0x18002e624  sub     edi, edx
0x18002e626  cmp     edi, [rsi+0Ch]
0x18002e629  jge     loc_18002E6F2
0x18002e62f  mov     ebx, r15d
0x18002e632  cmp     r15d, [rsi+8]
0x18002e636  jge     short loc_18002E682
0x18002e638  mov     [rsp+0F0h+rop], 0CC0020h; rop
0x18002e640  mov     r8d, edi
0x18002e643  sub     r8d, [rsi+4]; y
0x18002e647  mov     edx, ebx
0x18002e649  sub     edx, [rsi]; x
0x18002e64b  mov     [rsp+0F0h+y1], 0; y1
0x18002e653  mov     [rsp+0F0h+x1], 0; x1
0x18002e65b  mov     [rsp+0F0h+hdcSrc], r13; hdcSrc
0x18002e660  mov     [rsp+0F0h+cy], ecx; cy
0x18002e664  mov     rcx, r14; hdc
0x18002e667  call    cs:__imp_BitBlt
0x18002e66d  mov     r9d, dword ptr [rbp+57h+pv+4]
0x18002e671  test    eax, eax
0x18002e673  mov     ecx, dword ptr [rbp+57h+pv+8]
0x18002e676  setnz   byte ptr [rbp+57h+var_A0]
0x18002e67a  add     ebx, r9d
0x18002e67d  cmp     ebx, [rsi+8]
0x18002e680  jl      short loc_18002E638
0x18002e682  add     edi, ecx
0x18002e684  jmp     short loc_18002E626
0x18002e686  xor     edx, edx
0x18002e688  mov     r8d, dword ptr [rbp+57h+pv+4]
0x18002e68c  mov     ecx, r15d
0x18002e68f  sub     ecx, eax
0x18002e691  lea     eax, [rdx+r8]
0x18002e695  cmp     ecx, eax
0x18002e697  jge     loc_18002E8F3
0x18002e69d  xor     eax, eax
0x18002e69f  test    edi, edi
0x18002e6a1  cmovg   eax, edi
0x18002e6a4  sub     r15d, eax
0x18002e6a7  xor     r8d, r8d
0x18002e6aa  mov     [rsp+0F0h+rop], 0CC0020h; rop
0x18002e6b2  mov     [rsp+0F0h+y1], r10d; y1
0x18002e6b7  test    ebx, ebx
0x18002e6b9  mov     [rsp+0F0h+x1], r9d; x1
0x18002e6be  mov     rcx, r14; hdc
0x18002e6c1  cmovg   r8d, ebx; y
0x18002e6c5  mov     [rsp+0F0h+hdcSrc], r13; hdcSrc
0x18002e6ca  xor     edx, edx
0x18002e6cc  mov     [rsp+0F0h+cy], r12d; cy
0x18002e6d1  test    edi, edi
0x18002e6d3  mov     r9d, r15d; cx
0x18002e6d6  cmovg   edx, edi; x
0x18002e6d9  call    cs:__imp_BitBlt
0x18002e6df  mov     ebx, [rbp+57h+var_A0]
0x18002e6e2  test    eax, eax
0x18002e6e4  mov     eax, 1
0x18002e6e9  movzx   ebx, bl
0x18002e6ec  cmovnz  ebx, eax
0x18002e6ef  mov     [rbp+57h+var_A0], ebx
0x18002e6f2  mov     rdx, [rbp+57h+h]; h
0x18002e6f6  mov     rcx, r14; hdc
0x18002e6f9  call    cs:__imp_SelectObject
0x18002e6ff  mov     rcx, r14; ho
0x18002e702  call    cs:__imp_DeleteObject
0x18002e708  mov     rdx, [rbp+57h+var_88]; h
0x18002e70c  mov     rcx, r13; hdc
0x18002e70f  call    cs:__imp_SelectObject
0x18002e715  mov     rcx, r13; hdc
0x18002e718  call    cs:__imp_DeleteDC
0x18002e71e  mov     al, byte ptr [rbp+57h+var_A0]
0x18002e721  mov     rcx, [rbp+57h+var_50]
0x18002e725  xor     rcx, rsp; StackCookie
0x18002e728  call    __security_check_cookie
0x18002e72d  add     rsp, 0B8h
0x18002e734  pop     r15
0x18002e736  pop     r14
0x18002e738  pop     r13
0x18002e73a  pop     r12
0x18002e73c  pop     rdi
0x18002e73d  pop     rsi
0x18002e73e  pop     rbx
0x18002e73f  pop     rbp
0x18002e740  retn
0x18002e741  mov     r10d, ebx
0x18002e744  neg     r10d
0x18002e747  test    edi, edi
0x18002e749  jns     short loc_18002E797
0x18002e74b  mov     r9d, edi
0x18002e74e  neg     r9d
0x18002e751  test    ebx, ebx
0x18002e753  jg      short loc_18002E75F
0x18002e755  xor     eax, eax
0x18002e757  test    ebx, ebx
0x18002e759  jns     short loc_18002E761
0x18002e75b  mov     edx, ebx
0x18002e75d  jmp     short loc_18002E763
0x18002e75f  mov     eax, ebx
0x18002e761  xor     edx, edx
0x18002e763  mov     r8d, dword ptr [rbp+57h+pv+8]
0x18002e767  mov     ecx, r12d
0x18002e76a  sub     ecx, eax
0x18002e76c  lea     eax, [rdx+r8]
0x18002e770  cmp     ecx, eax
0x18002e772  jge     loc_18002E8E3
0x18002e778  xor     eax, eax
0x18002e77a  test    ebx, ebx
0x18002e77c  cmovg   eax, ebx
0x18002e77f  sub     r12d, eax
0x18002e782  test    edi, edi
0x18002e784  jg      short loc_18002E79C
0x18002e786  xor     eax, eax
0x18002e788  test    edi, edi
0x18002e78a  jns     loc_18002E686
0x18002e790  mov     edx, edi
0x18002e792  jmp     loc_18002E688
0x18002e797  xor     r9d, r9d
0x18002e79a  jmp     short loc_18002E751
0x18002e79c  mov     eax, edi
0x18002e79e  jmp     loc_18002E686
0x18002e7a3  cmp     dword ptr [rdi+18h], 3
0x18002e7a7  jnz     short loc_18002E7D0
0x18002e7a9  mov     rdx, [rdi+10h]
0x18002e7ad  test    rdx, rdx
0x18002e7b0  jz      short loc_18002E7D0
0x18002e7b2  add     rdx, 10h; lprcSrc
0x18002e7b6  lea     rcx, [rbp+57h+rc]; lprcDst
0x18002e7ba  call    cs:__imp_CopyRect
0x18002e7c0  mov     ebx, [rbp+57h+rc.right]
0x18002e7c3  sub     ebx, [rbp+57h+rc.left]
0x18002e7c6  mov     r8d, [rbp+57h+rc.bottom]
0x18002e7ca  sub     r8d, [rbp+57h+rc.top]
0x18002e7ce  jmp     short loc_18002E7EB
0x18002e7d0  mov     ecx, 4Eh ; 'N'; nIndex
0x18002e7d5  call    cs:__imp_GetSystemMetrics
0x18002e7db  mov     ecx, 4Fh ; 'O'; nIndex
0x18002e7e0  mov     ebx, eax
0x18002e7e2  call    cs:__imp_GetSystemMetrics
0x18002e7e8  mov     r8d, eax
0x18002e7eb  mov     r9d, 2
0x18002e7f1  sub     ebx, dword ptr [rbp+57h+pv+4]
0x18002e7f4  xor     ecx, ecx
0x18002e7f6  sub     r8d, dword ptr [rbp+57h+pv+8]
0x18002e7fa  mov     eax, ebx
0x18002e7fc  cdq
0x18002e7fd  idiv    r9d
0x18002e800  cmp     dword ptr [rdi+18h], 3
0x18002e804  mov     ebx, eax
0x18002e806  mov     eax, r8d
0x18002e809  setnz   cl
0x18002e80c  cdq
0x18002e80d  add     ecx, r9d
0x18002e810  idiv    ecx
0x18002e812  cmp     dword ptr [rdi+18h], 3
0x18002e816  mov     r14d, eax
0x18002e819  jnz     short loc_18002E858
0x18002e81b  cmp     qword ptr [rdi+10h], 0
0x18002e820  jz      short loc_18002E858
0x18002e822  mov     edi, [rbp+57h+rc.left]
0x18002e825  add     edi, ebx
0x18002e827  mov     ebx, [rbp+57h+rc.top]
0x18002e82a  add     ebx, eax
0x18002e82c  jmp     loc_18002E553
0x18002e831  sub     ecx, r9d
0x18002e834  jz      short loc_18002E87A
0x18002e836  cmp     ecx, 1
0x18002e839  jz      short loc_18002E7F1
0x18002e83b  sub     ebx, dword ptr [rbp+57h+pv+4]
0x18002e83e  sub     r8d, dword ptr [rbp+57h+pv+8]
0x18002e842  mov     eax, ebx
0x18002e844  cdq
0x18002e845  idiv    r9d
0x18002e848  mov     edi, eax
0x18002e84a  mov     eax, r8d
0x18002e84d  cdq
0x18002e84e  idiv    r9d
0x18002e851  mov     ebx, eax
0x18002e853  jmp     loc_18002E553
0x18002e858  mov     ecx, 4Ch ; 'L'; nIndex
0x18002e85d  call    cs:__imp_GetSystemMetrics
0x18002e863  mov     ecx, 4Dh ; 'M'; nIndex
0x18002e868  lea     edi, [rbx+rax]
  ... truncated ...
```
