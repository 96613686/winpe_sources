# CAutoComplete::_DrawGrip(HDC__ *,tagRECT const *,int)

- ea: `0x180420c5c`
- end: `0x180420f69`
- name: `?_DrawGrip@CAutoComplete@@IEBAHPEAUHDC__@@PEBUtagRECT@@H@Z`
- size: `781`
- prototype: `int(CAutoComplete *__hidden this, HDC, const struct tagRECT *, int)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18008b6c0`

## callees

- `0x180420c5c`

## import_xrefs

- `USER32!GetSysColorBrush` at `0x180420ca9`
- `USER32!GetSysColorBrush` at `0x180420ca9`
- `USER32!GetSysColor` at `0x180420cbc`
- `USER32!GetSysColor` at `0x180420cd3`
- `USER32!GetSysColor` at `0x180420d44`
- `USER32!GetSysColor` at `0x180420cbc`
- `USER32!GetSysColor` at `0x180420cd3`
- `USER32!GetSysColor` at `0x180420d44`
- `GDI32!DeleteObject` at `0x180420dde`
- `GDI32!DeleteObject` at `0x180420e76`
- `GDI32!DeleteObject` at `0x180420f40`
- `GDI32!DeleteObject` at `0x180420dde`
- `GDI32!DeleteObject` at `0x180420e76`
- `GDI32!DeleteObject` at `0x180420f40`
- `GDI32!SelectObject` at `0x180420ced`
- `GDI32!SelectObject` at `0x180420d30`
- `GDI32!SelectObject` at `0x180420d78`
- `GDI32!SelectObject` at `0x180420dcf`
- `GDI32!SelectObject` at `0x180420e17`
- `GDI32!SelectObject` at `0x180420e67`
- `GDI32!SelectObject` at `0x180420eb0`
- `GDI32!SelectObject` at `0x180420f31`
- `GDI32!SelectObject` at `0x180420ced`
- `GDI32!SelectObject` at `0x180420d30`
- `GDI32!SelectObject` at `0x180420d78`
- `GDI32!SelectObject` at `0x180420dcf`
- `GDI32!SelectObject` at `0x180420e17`
- `GDI32!SelectObject` at `0x180420e67`
- `GDI32!SelectObject` at `0x180420eb0`
- `GDI32!SelectObject` at `0x180420f31`
- `GDI32!CreatePen` at `0x180420d5a`
- `GDI32!CreatePen` at `0x180420df9`
- `GDI32!CreatePen` at `0x180420e92`
- `GDI32!CreatePen` at `0x180420d5a`
- `GDI32!CreatePen` at `0x180420df9`
- `GDI32!CreatePen` at `0x180420e92`
- `GDI32!PatBlt` at `0x180420d1e`
- `GDI32!PatBlt` at `0x180420d1e`
- `GDI32!MoveToEx` at `0x180420d9e`
- `GDI32!MoveToEx` at `0x180420e36`
- `GDI32!MoveToEx` at `0x180420ed4`
- `GDI32!MoveToEx` at `0x180420f00`
- `GDI32!MoveToEx` at `0x180420d9e`
- `GDI32!MoveToEx` at `0x180420e36`
- `GDI32!MoveToEx` at `0x180420ed4`
- `GDI32!MoveToEx` at `0x180420f00`
- `GDI32!LineTo` at `0x180420db2`
- `GDI32!LineTo` at `0x180420e4a`
- `GDI32!LineTo` at `0x180420ee8`
- `GDI32!LineTo` at `0x180420f15`
- `GDI32!LineTo` at `0x180420db2`
- `GDI32!LineTo` at `0x180420e4a`
- `GDI32!LineTo` at `0x180420ee8`
- `GDI32!LineTo` at `0x180420f15`

## pseudocode

```c
__int64 __fastcall CAutoComplete::_DrawGrip(CAutoComplete *this, HDC a2, const struct tagRECT *a3, int a4)
{
  LONG top; // r11d
  int v7; // eax
  int v9; // ebp
  int v10; // r12d
  HBRUSH SysColorBrush; // r14
  HGDIOBJ v12; // rbx
  COLORREF v13; // eax
  HPEN Pen; // rax
  HPEN v15; // r15
  HGDIOBJ v16; // r13
  int v17; // r14d
  int i; // ebx
  HPEN v19; // rax
  HPEN v20; // r14
  HGDIOBJ v21; // rax
  LONG v22; // r15d
  void *v23; // r13
  LONG j; // ebx
  HPEN v25; // rax
  HPEN v26; // r14
  HGDIOBJ v27; // r15
  int v28; // ebx
  int v29; // edi
  DWORD SysColor; // [rsp+70h] [rbp+8h]
  DWORD color; // [rsp+88h] [rbp+20h]

  top = a3->top;
  v7 = a3->right - a3->left;
  if ( v7 >= a3->bottom - top )
    v7 = a3->bottom - top;
  v9 = v7 + a3->left;
  v10 = v7 + top;
  SysColorBrush = GetSysColorBrush(15);
  color = GetSysColor(20);
  SysColor = GetSysColor(16);
  if ( a4 )
  {
    v12 = SelectObject(a2, SysColorBrush);
    PatBlt(a2, a3->left, a3->top, a3->right - a3->left, a3->bottom - a3->top, 0xF00021u);
    SelectObject(a2, v12);
  }
  else
  {
    v13 = GetSysColor(15);
    Pen = CreatePen(0, 1, v13);
    v15 = Pen;
    if ( !Pen )
      return 0;
    v16 = SelectObject(a2, Pen);
    v17 = a3->top + 3;
    for ( i = a3->left + 3; i < v9; i += 4 )
    {
      MoveToEx(a2, i, v10, 0);
      LineTo(a2, v9, v17);
      v17 += 4;
    }
    SelectObject(a2, v16);
    DeleteObject(v15);
  }
  v19 = CreatePen(0, 1, color);
  v20 = v19;
  if ( !v19 )
    return 0;
  v21 = SelectObject(a2, v19);
  v22 = a3->top;
  v23 = v21;
  for ( j = a3->left; j < v9; j += 4 )
  {
    MoveToEx(a2, j, v10, 0);
    LineTo(a2, v9, v22);
    v22 += 4;
  }
  SelectObject(a2, v23);
  DeleteObject(v20);
  v25 = CreatePen(0, 1, SysColor);
  v26 = v25;
  if ( !v25 )
    return 0;
  v27 = SelectObject(a2, v25);
  v28 = a3->left + 1;
  v29 = a3->top + 1;
  while ( v28 < v9 )
  {
    MoveToEx(a2, v28, v10, 0);
    LineTo(a2, v9, v29);
    MoveToEx(a2, v28 + 1, v10, 0);
    LineTo(a2, v9, v29 + 1);
    v28 += 4;
    v29 += 4;
  }
  SelectObject(a2, v27);
  DeleteObject(v26);
  return 1;
}

```

## disassembly

```asm
0x180420c5c  mov     [rsp+arg_8], rbx
0x180420c61  mov     qword ptr [rsp+arg_0], rcx
0x180420c66  push    rbp
0x180420c67  push    rsi
0x180420c68  push    rdi
0x180420c69  push    r12
0x180420c6b  push    r13
0x180420c6d  push    r14
0x180420c6f  push    r15
0x180420c71  sub     rsp, 30h
0x180420c75  mov     ecx, [r8]
0x180420c78  mov     r15d, 0Fh
0x180420c7e  mov     r11d, [r8+4]
0x180420c82  mov     ebx, r9d
0x180420c85  mov     r10d, [r8+0Ch]
0x180420c89  mov     rdi, r8
0x180420c8c  mov     eax, [r8+8]
0x180420c90  sub     r10d, r11d
0x180420c93  sub     eax, ecx
0x180420c95  mov     rsi, rdx
0x180420c98  cmp     eax, r10d
0x180420c9b  cmovge  eax, r10d
0x180420c9f  lea     ebp, [rax+rcx]
0x180420ca2  mov     ecx, r15d; nIndex
0x180420ca5  lea     r12d, [rax+r11]
0x180420ca9  call    cs:__imp_GetSysColorBrush
0x180420cb0  nop     dword ptr [rax+rax+00h]
0x180420cb5  lea     ecx, [r15+5]; nIndex
0x180420cb9  mov     r14, rax
0x180420cbc  call    cs:__imp_GetSysColor
0x180420cc3  nop     dword ptr [rax+rax+00h]
0x180420cc8  lea     ecx, [r15+1]; nIndex
0x180420ccc  mov     [rsp+68h+color], eax
0x180420cd3  call    cs:__imp_GetSysColor
0x180420cda  nop     dword ptr [rax+rax+00h]
0x180420cdf  mov     [rsp+68h+arg_0], eax
0x180420ce3  test    ebx, ebx
0x180420ce5  jz      short loc_180420D41
0x180420ce7  mov     rdx, r14; h
0x180420cea  mov     rcx, rsi; hdc
0x180420ced  call    cs:__imp_SelectObject
0x180420cf4  nop     dword ptr [rax+rax+00h]
0x180420cf9  mov     ecx, [rdi+0Ch]
0x180420cfc  mov     rbx, rax
0x180420cff  mov     r8d, [rdi+4]; y
0x180420d03  sub     ecx, r8d
0x180420d06  mov     r9d, [rdi+8]
0x180420d0a  sub     r9d, [rdi]; w
0x180420d0d  mov     edx, [rdi]; x
0x180420d0f  mov     [rsp+68h+rop], 0F00021h; rop
0x180420d17  mov     [rsp+68h+h], ecx; h
0x180420d1b  mov     rcx, rsi; hdc
0x180420d1e  call    cs:__imp_PatBlt
0x180420d25  nop     dword ptr [rax+rax+00h]
0x180420d2a  mov     rdx, rbx; h
0x180420d2d  mov     rcx, rsi; hdc
0x180420d30  call    cs:__imp_SelectObject
0x180420d37  nop     dword ptr [rax+rax+00h]
0x180420d3c  jmp     loc_180420DEA
0x180420d41  mov     ecx, r15d; nIndex
0x180420d44  call    cs:__imp_GetSysColor
0x180420d4b  nop     dword ptr [rax+rax+00h]
0x180420d50  mov     edx, 1; cWidth
0x180420d55  xor     ecx, ecx; iStyle
0x180420d57  mov     r8d, eax; color
0x180420d5a  call    cs:__imp_CreatePen
0x180420d61  nop     dword ptr [rax+rax+00h]
0x180420d66  mov     r15, rax
0x180420d69  test    rax, rax
0x180420d6c  jz      loc_180420F51
0x180420d72  mov     rdx, rax; h
0x180420d75  mov     rcx, rsi; hdc
0x180420d78  call    cs:__imp_SelectObject
0x180420d7f  nop     dword ptr [rax+rax+00h]
0x180420d84  mov     r14d, [rdi+4]
0x180420d88  mov     r13, rax
0x180420d8b  mov     ebx, [rdi]
0x180420d8d  add     r14d, 3
0x180420d91  add     ebx, 3
0x180420d94  jmp     short loc_180420DC5
0x180420d96  xor     r9d, r9d; lppt
0x180420d99  mov     r8d, r12d; y
0x180420d9c  mov     edx, ebx; x
0x180420d9e  call    cs:__imp_MoveToEx
0x180420da5  nop     dword ptr [rax+rax+00h]
0x180420daa  mov     r8d, r14d; y
0x180420dad  mov     edx, ebp; x
0x180420daf  mov     rcx, rsi; hdc
0x180420db2  call    cs:__imp_LineTo
0x180420db9  nop     dword ptr [rax+rax+00h]
0x180420dbe  add     ebx, 4
0x180420dc1  add     r14d, 4
0x180420dc5  mov     rcx, rsi; hdc
0x180420dc8  cmp     ebx, ebp
0x180420dca  jl      short loc_180420D96
0x180420dcc  mov     rdx, r13; h
0x180420dcf  call    cs:__imp_SelectObject
0x180420dd6  nop     dword ptr [rax+rax+00h]
0x180420ddb  mov     rcx, r15; ho
0x180420dde  call    cs:__imp_DeleteObject
0x180420de5  nop     dword ptr [rax+rax+00h]
0x180420dea  mov     r8d, [rsp+68h+color]; color
0x180420df2  mov     edx, 1; cWidth
0x180420df7  xor     ecx, ecx; iStyle
0x180420df9  call    cs:__imp_CreatePen
0x180420e00  nop     dword ptr [rax+rax+00h]
0x180420e05  mov     r14, rax
0x180420e08  test    rax, rax
0x180420e0b  jz      loc_180420F51
0x180420e11  mov     rdx, rax; h
0x180420e14  mov     rcx, rsi; hdc
0x180420e17  call    cs:__imp_SelectObject
0x180420e1e  nop     dword ptr [rax+rax+00h]
0x180420e23  mov     r15d, [rdi+4]
0x180420e27  mov     r13, rax
0x180420e2a  mov     ebx, [rdi]
0x180420e2c  jmp     short loc_180420E5D
0x180420e2e  xor     r9d, r9d; lppt
0x180420e31  mov     r8d, r12d; y
0x180420e34  mov     edx, ebx; x
0x180420e36  call    cs:__imp_MoveToEx
0x180420e3d  nop     dword ptr [rax+rax+00h]
0x180420e42  mov     r8d, r15d; y
0x180420e45  mov     edx, ebp; x
0x180420e47  mov     rcx, rsi; hdc
0x180420e4a  call    cs:__imp_LineTo
0x180420e51  nop     dword ptr [rax+rax+00h]
0x180420e56  add     ebx, 4
0x180420e59  add     r15d, 4
0x180420e5d  mov     rcx, rsi; hdc
0x180420e60  cmp     ebx, ebp
0x180420e62  jl      short loc_180420E2E
0x180420e64  mov     rdx, r13; h
0x180420e67  call    cs:__imp_SelectObject
0x180420e6e  nop     dword ptr [rax+rax+00h]
0x180420e73  mov     rcx, r14; ho
0x180420e76  call    cs:__imp_DeleteObject
0x180420e7d  nop     dword ptr [rax+rax+00h]
0x180420e82  mov     r8d, [rsp+68h+arg_0]; color
0x180420e87  mov     r13d, 1
0x180420e8d  mov     edx, r13d; cWidth
0x180420e90  xor     ecx, ecx; iStyle
0x180420e92  call    cs:__imp_CreatePen
0x180420e99  nop     dword ptr [rax+rax+00h]
0x180420e9e  mov     r14, rax
0x180420ea1  test    rax, rax
0x180420ea4  jz      loc_180420F51
0x180420eaa  mov     rdx, rax; h
0x180420ead  mov     rcx, rsi; hdc
0x180420eb0  call    cs:__imp_SelectObject
0x180420eb7  nop     dword ptr [rax+rax+00h]
0x180420ebc  mov     ebx, [rdi]
0x180420ebe  mov     r15, rax
0x180420ec1  mov     edi, [rdi+4]
0x180420ec4  add     ebx, r13d
0x180420ec7  add     edi, r13d
0x180420eca  jmp     short loc_180420F27
0x180420ecc  xor     r9d, r9d; lppt
0x180420ecf  mov     r8d, r12d; y
0x180420ed2  mov     edx, ebx; x
0x180420ed4  call    cs:__imp_MoveToEx
0x180420edb  nop     dword ptr [rax+rax+00h]
0x180420ee0  mov     r8d, edi; y
0x180420ee3  mov     edx, ebp; x
0x180420ee5  mov     rcx, rsi; hdc
0x180420ee8  call    cs:__imp_LineTo
0x180420eef  nop     dword ptr [rax+rax+00h]
0x180420ef4  xor     r9d, r9d; lppt
0x180420ef7  lea     edx, [rbx+1]; x
0x180420efa  mov     r8d, r12d; y
0x180420efd  mov     rcx, rsi; hdc
0x180420f00  call    cs:__imp_MoveToEx
0x180420f07  nop     dword ptr [rax+rax+00h]
0x180420f0c  lea     r8d, [rdi+1]; y
0x180420f10  mov     edx, ebp; x
0x180420f12  mov     rcx, rsi; hdc
0x180420f15  call    cs:__imp_LineTo
0x180420f1c  nop     dword ptr [rax+rax+00h]
0x180420f21  add     ebx, 4
0x180420f24  add     edi, 4
0x180420f27  mov     rcx, rsi; hdc
0x180420f2a  cmp     ebx, ebp
0x180420f2c  jl      short loc_180420ECC
0x180420f2e  mov     rdx, r15; h
0x180420f31  call    cs:__imp_SelectObject
0x180420f38  nop     dword ptr [rax+rax+00h]
0x180420f3d  mov     rcx, r14; ho
0x180420f40  call    cs:__imp_DeleteObject
0x180420f47  nop     dword ptr [rax+rax+00h]
0x180420f4c  mov     eax, r13d
0x180420f4f  jmp     short loc_180420F53
0x180420f51  xor     eax, eax
0x180420f53  mov     rbx, [rsp+68h+arg_8]
0x180420f58  add     rsp, 30h
0x180420f5c  pop     r15
0x180420f5e  pop     r14
0x180420f60  pop     r13
0x180420f62  pop     r12
0x180420f64  pop     rdi
0x180420f65  pop     rsi
0x180420f66  pop     rbp
0x180420f67  retn
```
