# RealDrawFrameControl

- ea: `0x180039940`
- end: `0x180039c2a`
- name: `RealDrawFrameControl`
- size: `746`
- prototype: `__int64 __fastcall(HDC)`
- caller_count: `0`
- callee_count: `10`
- tags: ``

## callees

- `0x180038870`
- `0x180039808`
- `0x180039940`
- `0x180039dfc`
- `0x18003ad3c`
- `0x18003f39c`
- `0x18005be0c`
- `0x180096130`
- `0x180096dc5`
- `0x180096e00`

## import_xrefs

- `GDI32!SetBkMode` at `0x180039a04`
- `GDI32!SetBkMode` at `0x180039b28`
- `GDI32!SetBkMode` at `0x180039a04`
- `GDI32!SetBkMode` at `0x180039b28`
- `GDI32!SelectObject` at `0x180039a71`
- `GDI32!SelectObject` at `0x180039b35`
- `GDI32!SelectObject` at `0x180039a71`
- `GDI32!SelectObject` at `0x180039b35`
- `GDI32!SetTextAlign` at `0x180039ac5`
- `GDI32!SetTextAlign` at `0x180039bd5`
- `GDI32!SetTextAlign` at `0x180039c1f`
- `GDI32!SetTextAlign` at `0x180039ac5`
- `GDI32!SetTextAlign` at `0x180039bd5`
- `GDI32!SetTextAlign` at `0x180039c1f`
- `GDI32!GetTextAlign` at `0x180039bb6`
- `GDI32!GetTextAlign` at `0x180039bb6`
- `GDI32!GetLayout` at `0x1800399a5`
- `GDI32!GetLayout` at `0x1800399a5`
- `GDI32!SetGraphicsMode` at `0x180039ab9`
- `GDI32!SetGraphicsMode` at `0x180039ba2`
- `GDI32!SetGraphicsMode` at `0x180039c13`
- `GDI32!SetGraphicsMode` at `0x180039ab9`
- `GDI32!SetGraphicsMode` at `0x180039ba2`
- `GDI32!SetGraphicsMode` at `0x180039c13`
- `GDI32!PolyPatBlt` at `0x18009ca9e`
- `GDI32!PolyPatBlt` at `0x18009ca9e`
- `GDI32!CreateFontIndirectW` at `0x180039a62`
- `GDI32!CreateFontIndirectW` at `0x180039a62`
- `GDI32!DeleteObject` at `0x180039b3e`
- `GDI32!DeleteObject` at `0x180039b3e`

## pseudocode

```c
__int64 __fastcall RealDrawFrameControl(HDC a1, RECT *a2, unsigned int a3, int a4)
{
  int v8; // r15d
  UINT v9; // r12d
  unsigned int v10; // r14d
  int v11; // edx
  unsigned int v12; // edi
  LONG v13; // r13d
  HFONT v14; // r13
  unsigned __int16 CaptionChar; // ax
  UINT TextAlign; // eax
  unsigned int v18; // r8d
  LONG top; // edx
  int v20; // eax
  int v21; // eax
  int v22; // [rsp+30h] [rbp-99h]
  RECT rc; // [rsp+38h] [rbp-91h] BYREF
  int mode; // [rsp+48h] [rbp-81h]
  struct tagRECT *v25; // [rsp+50h] [rbp-79h]
  HGDIOBJ h; // [rsp+58h] [rbp-71h]
  _DWORD v27[4]; // [rsp+60h] [rbp-69h] BYREF
  __int64 v28; // [rsp+70h] [rbp-59h]
  LOGFONTW lf; // [rsp+80h] [rbp-49h] BYREF

  v25 = a2;
  v22 = 0;
  memset_0(&lf, 0, sizeof(lf));
  v8 = 0;
  v9 = 0;
  rc = *a2;
  v10 = 1;
  if ( (GetLayout(a1) & 1) != 0 )
  {
    v8 = SetGraphicsMode(a1, 2);
    if ( v8 )
    {
      TextAlign = GetTextAlign(a1);
      v9 = TextAlign;
      if ( (TextAlign & 6) != 6 )
        SetTextAlign(a1, TextAlign ^ 2);
    }
  }
  v11 = a4 | 0x8000;
  if ( *(_WORD *)(gpsi + 6996) != 1 )
    v11 = a4;
  v12 = v11 | 0x4000;
  if ( (v11 & 0x8000) == 0 )
    v12 = v11;
  if ( a3 != 2 && a3 != 5 && (a3 != 4 || (v12 & 0x10) != 0) && (a3 != 3 || (v12 & 0x18) == 0) )
  {
    DrawPushButton(a1);
    if ( (v12 & 0x2000) != 0 )
      *a2 = rc;
    v22 = 1;
  }
  mode = SetBkMode(a1, 1);
  if ( mode )
  {
    v13 = rc.right - rc.left;
    if ( rc.right - rc.left >= rc.bottom - rc.top )
      v13 = rc.bottom - rc.top;
    if ( v13 > 0 )
    {
      memset_0(&lf, 0, sizeof(lf));
      lf.lfHeight = v13;
      lf.lfWeight = 400;
      wcscpy(lf.lfFaceName, L"Marlett");
      lf.lfCharSet = 2;
      v14 = CreateFontIndirectW(&lf);
      h = SelectObject(a1, v14);
      if ( v22 )
      {
        if ( a3 == 1 )
        {
          CaptionChar = GetCaptionChar(v12);
          DrawIt(a1, &rc, v12, CaptionChar);
          goto LABEL_24;
        }
        if ( a3 != 3 )
        {
          if ( a3 != 4 )
            v10 = 0;
          goto LABEL_24;
        }
        v18 = v12;
      }
      else
      {
        if ( a3 != 2 && a3 != 5 )
        {
          if ( a3 == 4 )
            DrawBox(a1, &rc, v12);
          else
            DrawGrip(a1, v25, v12);
LABEL_24:
          if ( v8 )
          {
            SetGraphicsMode(a1, v8);
            SetTextAlign(a1, v9);
          }
          SetBkMode(a1, mode);
          SelectObject(a1, h);
          DeleteObject(v14);
          return v10;
        }
        if ( (v12 & 0x18) == 0 )
        {
          DrawMenuMark(a1, &rc, a3, v12);
          goto LABEL_24;
        }
        if ( (v12 & 0x800) == 0 )
        {
          top = v25->top;
          v20 = v25->right - v25->left;
          v27[0] = v25->left;
          v27[2] = v20;
          v21 = v25->bottom - top;
          v27[1] = top;
          v27[3] = v21;
          v28 = *(_QWORD *)(gpsi + 4728);
          PolyPatBlt(a1, 15728673, v27, 1, 0);
        }
        v18 = v12 & 0x1100 | (((v12 >> 3) & 1) == 0);
      }
      DrawScrollArrow(a1, &rc, v18);
      goto LABEL_24;
    }
  }
  if ( v8 )
  {
    SetGraphicsMode(a1, v8);
    SetTextAlign(a1, v9);
  }
  return 0;
}

```

## disassembly

```asm
0x180039940  mov     [rsp-8+arg_10], rbx
0x180039945  push    rbp
0x180039946  push    rsi
0x180039947  push    rdi
0x180039948  push    r12
0x18003994a  push    r13
0x18003994c  push    r14
0x18003994e  push    r15
0x180039950  lea     rbp, [rsp-27h]
0x180039955  sub     rsp, 0F0h
0x18003995c  mov     rax, cs:__security_cookie
0x180039963  xor     rax, rsp
0x180039966  mov     [rbp+57h+var_40], rax
0x18003996a  mov     r13, rdx
0x18003996d  mov     [rbp+57h+var_D0], rdx
0x180039971  xor     edx, edx; Val
0x180039973  mov     [rsp+120h+var_F0], 0
0x18003997b  mov     esi, r8d
0x18003997e  mov     rbx, rcx
0x180039981  lea     rcx, [rbp+57h+lf]; void *
0x180039985  mov     edi, r9d
0x180039988  lea     r8d, [rdx+5Ch]; Size
0x18003998c  call    memset_0
0x180039991  movups  xmm0, xmmword ptr [r13+0]
0x180039996  mov     rcx, rbx; hdc
0x180039999  xor     r15d, r15d
0x18003999c  xor     r12d, r12d
0x18003999f  movdqu  xmmword ptr [rsp+120h+rc.left], xmm0
0x1800399a5  call    cs:__imp_GetLayout
0x1800399ab  lea     r14d, [r15+1]
0x1800399af  test    r14b, al
0x1800399b2  jnz     loc_180039B9A
0x1800399b8  mov     rcx, cs:gpsi
0x1800399bf  mov     edx, edi
0x1800399c1  mov     r8d, 8000h
0x1800399c7  or      edx, r8d
0x1800399ca  cmp     [rcx+1B54h], r14w
0x1800399d2  cmovnz  edx, edi
0x1800399d5  mov     edi, edx
0x1800399d7  bts     edi, 0Eh
0x1800399db  test    r8d, edx
0x1800399de  cmovz   edi, edx
0x1800399e1  cmp     esi, 2
0x1800399e4  jz      short loc_1800399FE
0x1800399e6  cmp     esi, 5
0x1800399e9  jz      short loc_1800399FE
0x1800399eb  cmp     esi, 4
0x1800399ee  jnz     loc_180039B55
0x1800399f4  test    dil, 10h
0x1800399f8  jnz     loc_180039B55
0x1800399fe  mov     edx, r14d; mode
0x180039a01  mov     rcx, rbx; hdc
0x180039a04  call    cs:__imp_SetBkMode
0x180039a0a  mov     [rsp+120h+mode], eax
0x180039a0e  test    eax, eax
0x180039a10  jz      loc_180039AAE
0x180039a16  mov     eax, [rsp+120h+rc.bottom]
0x180039a1a  sub     eax, [rsp+120h+rc.top]
0x180039a1e  mov     r13d, [rsp+120h+rc.right]
0x180039a23  sub     r13d, [rsp+120h+rc.left]
0x180039a28  cmp     r13d, eax
0x180039a2b  cmovge  r13d, eax
0x180039a2f  test    r13d, r13d
0x180039a32  jle     short loc_180039AAE
0x180039a34  xor     edx, edx; Val
0x180039a36  lea     rcx, [rbp+57h+lf]; void *
0x180039a3a  lea     r8d, [rdx+5Ch]; Size
0x180039a3e  call    memset_0
0x180039a43  movups  xmm0, xmmword ptr cs:aMarlett; "Marlett"
0x180039a4a  lea     rcx, [rbp+57h+lf]; lplf
0x180039a4e  mov     [rbp+57h+lf.lfHeight], r13d
0x180039a52  mov     [rbp+57h+lf.lfWeight], 190h
0x180039a59  movdqu  xmmword ptr [rbp+57h+lf.lfFaceName], xmm0
0x180039a5e  mov     [rbp+57h+lf.lfCharSet], 2
0x180039a62  call    cs:__imp_CreateFontIndirectW
0x180039a68  mov     rdx, rax; h
0x180039a6b  mov     rcx, rbx; hdc
0x180039a6e  mov     r13, rax
0x180039a71  call    cs:__imp_SelectObject
0x180039a77  cmp     [rsp+120h+var_F0], 0
0x180039a7c  mov     [rbp+57h+h], rax
0x180039a80  jnz     short loc_180039AF4
0x180039a82  cmp     esi, 2
0x180039a85  jz      loc_18009CA42
0x180039a8b  cmp     esi, 5
0x180039a8e  jz      loc_18009CA42
0x180039a94  mov     r8d, edi; unsigned int
0x180039a97  mov     rcx, rbx; hdc
0x180039a9a  cmp     esi, 4
0x180039a9d  jz      loc_180039B49
0x180039aa3  mov     rdx, [rbp+57h+var_D0]; struct tagRECT *
0x180039aa7  call    ?DrawGrip@@YAHPEAUHDC__@@PEAUtagRECT@@I@Z; DrawGrip(HDC__ *,tagRECT *,uint)
0x180039aac  jmp     short loc_180039B18
0x180039aae  test    r15d, r15d
0x180039ab1  jz      short loc_180039ACB
0x180039ab3  mov     edx, r15d; iMode
0x180039ab6  mov     rcx, rbx; hdc
0x180039ab9  call    cs:__imp_SetGraphicsMode
0x180039abf  mov     edx, r12d; align
0x180039ac2  mov     rcx, rbx; hdc
0x180039ac5  call    cs:__imp_SetTextAlign
0x180039acb  xor     eax, eax
0x180039acd  mov     rcx, [rbp+57h+var_40]
0x180039ad1  xor     rcx, rsp; StackCookie
0x180039ad4  call    __security_check_cookie
0x180039ad9  mov     rbx, [rsp+120h+arg_10]
0x180039ae1  add     rsp, 0F0h
0x180039ae8  pop     r15
0x180039aea  pop     r14
0x180039aec  pop     r13
0x180039aee  pop     r12
0x180039af0  pop     rdi
0x180039af1  pop     rsi
0x180039af2  pop     rbp
0x180039af3  retn
0x180039af4  cmp     esi, r14d
0x180039af7  jnz     loc_180039BFC
0x180039afd  mov     ecx, edi; unsigned int
0x180039aff  call    ?GetCaptionChar@@YAGI@Z; GetCaptionChar(uint)
0x180039b04  movzx   r9d, ax; unsigned __int16
0x180039b08  lea     rdx, [rsp+120h+rc]; struct tagRECT *
0x180039b0d  mov     rcx, rbx; hdc
0x180039b10  mov     r8d, edi; unsigned int
0x180039b13  call    ?DrawIt@@YAHPEAUHDC__@@PEAUtagRECT@@IG@Z; DrawIt(HDC__ *,tagRECT *,uint,ushort)
0x180039b18  test    r15d, r15d
0x180039b1b  jnz     loc_180039C0D
0x180039b21  mov     edx, [rsp+120h+mode]; mode
0x180039b25  mov     rcx, rbx; hdc
0x180039b28  call    cs:__imp_SetBkMode
0x180039b2e  mov     rdx, [rbp+57h+h]; h
0x180039b32  mov     rcx, rbx; hdc
0x180039b35  call    cs:__imp_SelectObject
0x180039b3b  mov     rcx, r13; ho
0x180039b3e  call    cs:__imp_DeleteObject
0x180039b44  mov     eax, r14d
0x180039b47  jmp     short loc_180039ACD
0x180039b49  lea     rdx, [rsp+120h+rc]; struct tagRECT *
0x180039b4e  call    ?DrawBox@@YAHPEAUHDC__@@PEAUtagRECT@@I@Z; DrawBox(HDC__ *,tagRECT *,uint)
0x180039b53  jmp     short loc_180039B18
0x180039b55  cmp     esi, 3
0x180039b58  jz      loc_180039BE0
0x180039b5e  mov     eax, 2000h
0x180039b63  lea     rdx, [rsp+120h+rc]
0x180039b68  mov     r9d, 3000h
0x180039b6e  cmp     esi, 3
0x180039b71  mov     r8d, edi
0x180039b74  mov     rcx, rbx; hdc
0x180039b77  cmovz   r9d, eax
0x180039b7b  mov     eax, edi
0x180039b7d  and     eax, 0C000h
0x180039b82  or      r9d, eax
0x180039b85  call    DrawPushButton
0x180039b8a  bt      edi, 0Dh
0x180039b8e  jb      short loc_180039BEF
0x180039b90  mov     [rsp+120h+var_F0], r14d
0x180039b95  jmp     loc_1800399FE
0x180039b9a  mov     edx, 2; iMode
0x180039b9f  mov     rcx, rbx; hdc
0x180039ba2  call    cs:__imp_SetGraphicsMode
0x180039ba8  mov     r15d, eax
0x180039bab  test    eax, eax
0x180039bad  jz      loc_1800399B8
0x180039bb3  mov     rcx, rbx; hdc
0x180039bb6  call    cs:__imp_GetTextAlign
0x180039bbc  mov     ecx, eax
0x180039bbe  mov     r12d, eax
0x180039bc1  and     ecx, 6
0x180039bc4  cmp     cl, 6
0x180039bc7  jz      loc_1800399B8
0x180039bcd  mov     edx, eax
0x180039bcf  mov     rcx, rbx; hdc
0x180039bd2  xor     edx, 2; align
0x180039bd5  call    cs:__imp_SetTextAlign
0x180039bdb  jmp     loc_1800399B8
0x180039be0  test    dil, 18h
0x180039be4  jnz     loc_1800399FE
0x180039bea  jmp     loc_180039B5E
0x180039bef  movups  xmm0, xmmword ptr [rsp+120h+rc.left]
0x180039bf4  movdqu  xmmword ptr [r13+0], xmm0
0x180039bfa  jmp     short loc_180039B90
0x180039bfc  cmp     esi, 3
0x180039bff  jnz     loc_18009CAE6
0x180039c05  mov     r8d, edi
0x180039c08  jmp     loc_18009CABA
0x180039c0d  mov     edx, r15d; iMode
0x180039c10  mov     rcx, rbx; hdc
0x180039c13  call    cs:__imp_SetGraphicsMode
0x180039c19  mov     edx, r12d; align
0x180039c1c  mov     rcx, rbx; hdc
0x180039c1f  call    cs:__imp_SetTextAlign
0x180039c25  jmp     loc_180039B21
0x18009ca42  test    dil, 18h
0x18009ca46  jz      loc_18009CACD
0x18009ca4c  bt      edi, 0Bh
0x18009ca50  jb      short loc_18009CAA4
0x18009ca52  mov     r8, [rbp+57h+var_D0]
0x18009ca56  mov     r9d, r14d
0x18009ca59  mov     [rsp+120h+var_100], 0
0x18009ca61  mov     ecx, [r8]
0x18009ca64  mov     edx, [r8+4]
0x18009ca68  mov     eax, [r8+8]
0x18009ca6c  sub     eax, ecx
0x18009ca6e  mov     [rbp+57h+var_C0], ecx
0x18009ca71  mov     [rbp+57h+var_B8], eax
0x18009ca74  mov     eax, [r8+0Ch]
0x18009ca78  lea     r8, [rbp+57h+var_C0]
0x18009ca7c  sub     eax, edx
0x18009ca7e  mov     [rbp+57h+var_BC], edx
0x18009ca81  mov     [rbp+57h+var_B4], eax
0x18009ca84  mov     edx, 0F00021h
0x18009ca89  mov     rax, cs:gpsi
0x18009ca90  mov     rcx, [rax+1278h]
0x18009ca97  mov     [rbp+57h+var_B0], rcx
0x18009ca9b  mov     rcx, rbx
0x18009ca9e  call    cs:__imp_PolyPatBlt
0x18009caa4  mov     r8d, edi
0x18009caa7  and     edi, 1100h
0x18009caad  shr     r8d, 3
0x18009cab1  not     r8d
0x18009cab4  and     r8d, r14d
0x18009cab7  or      r8d, edi; unsigned int
0x18009caba  lea     rdx, [rsp+120h+rc]; struct tagRECT *
0x18009cabf  mov     rcx, rbx; HDC
0x18009cac2  call    ?DrawScrollArrow@@YAHPEAUHDC__@@PEAUtagRECT@@I@Z; DrawScrollArrow(HDC__ *,tagRECT *,uint)
0x18009cac7  nop
0x18009cac8  jmp     loc_180039B18
0x18009cacd  mov     r9d, edi; unsigned int
0x18009cad0  lea     rdx, [rsp+120h+rc]; lprc
0x18009cad5  mov     r8d, esi; unsigned int
0x18009cad8  mov     rcx, rbx; hdc
0x18009cadb  call    ?DrawMenuMark@@YAHPEAUHDC__@@PEAUtagRECT@@II@Z; DrawMenuMark(HDC__ *,tagRECT *,uint,uint)
0x18009cae0  nop
0x18009cae1  jmp     loc_180039B18
0x18009cae6  xor     eax, eax
0x18009cae8  cmp     esi, 4
0x18009caeb  cmovnz  r14d, eax
0x18009caef  jmp     loc_180039B18
```
