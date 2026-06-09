# ClipBitmap(HBITMAP__ * *,tagRECT *)

- ea: `0x180042ffc`
- end: `0x18004314a`
- name: `?ClipBitmap@@YAHPEAPEAUHBITMAP__@@PEAUtagRECT@@@Z`
- size: `334`
- prototype: `__int64 __fastcall(HBITMAP *, struct tagRECT *)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180043150`
- `0x180057750`

## callees

- `0x18002203c`
- `0x180042ffc`

## import_xrefs

- `GDI32!DeleteObject` at `0x180043113`
- `GDI32!DeleteObject` at `0x180043113`
- `GDI32!BitBlt` at `0x1800430ee`
- `GDI32!BitBlt` at `0x1800430ee`
- `GDI32!SelectObject` at `0x180043097`
- `GDI32!SelectObject` at `0x1800430ae`
- `GDI32!SelectObject` at `0x1800430fd`
- `GDI32!SelectObject` at `0x180043109`
- `GDI32!SelectObject` at `0x180043097`
- `GDI32!SelectObject` at `0x1800430ae`
- `GDI32!SelectObject` at `0x1800430fd`
- `GDI32!SelectObject` at `0x180043109`
- `GDI32!CreateCompatibleDC` at `0x18004301b`
- `GDI32!CreateCompatibleDC` at `0x18004302f`
- `GDI32!CreateCompatibleDC` at `0x18004301b`
- `GDI32!CreateCompatibleDC` at `0x18004302f`
- `GDI32!DeleteDC` at `0x180043120`
- `GDI32!DeleteDC` at `0x180043129`
- `GDI32!DeleteDC` at `0x180043120`
- `GDI32!DeleteDC` at `0x180043129`

## pseudocode

```c
__int64 __fastcall ClipBitmap(HBITMAP *a1, struct tagRECT *a2)
{
  unsigned int v4; // r12d
  HDC hdcSrc; // r15
  HDC CompatibleDC; // rbp
  HGDIOBJ v7; // rax
  HBITMAP v8; // rsi
  void *v9; // rdi
  HGDIOBJ v10; // rbx
  void *v12; // [rsp+50h] [rbp-48h] BYREF
  tagSIZE cy; // [rsp+B0h] [rbp+18h] BYREF
  HGDIOBJ h; // [rsp+B8h] [rbp+20h] BYREF

  v4 = 0;
  hdcSrc = CreateCompatibleDC(0);
  if ( hdcSrc )
  {
    CompatibleDC = CreateCompatibleDC(0);
    if ( CompatibleDC )
    {
      cy.cx = a2->right - a2->left;
      cy.cy = a2->bottom - a2->top;
      h = 0;
      v12 = 0;
      if ( (int)Create32BitHBITMAP(CompatibleDC, &cy, &v12, (HBITMAP *)&h) >= 0 )
      {
        v7 = SelectObject(hdcSrc, *a1);
        v8 = (HBITMAP)h;
        v9 = v7;
        v10 = SelectObject(CompatibleDC, h);
        v4 = BitBlt(CompatibleDC, 0, 0, cy.cx, cy.cy, hdcSrc, a2->left, a2->top, 0xCC0020u);
        SelectObject(CompatibleDC, v10);
        SelectObject(hdcSrc, v9);
        DeleteObject(*a1);
        *a1 = v8;
      }
      DeleteDC(CompatibleDC);
    }
    DeleteDC(hdcSrc);
  }
  return v4;
}

```

## disassembly

```asm
0x180042ffc  mov     [rsp+arg_0], rbx
0x180043001  push    rbp
0x180043002  push    rsi
0x180043003  push    rdi
0x180043004  push    r12
0x180043006  push    r13
0x180043008  push    r14
0x18004300a  push    r15
0x18004300c  sub     rsp, 60h
0x180043010  mov     r13, rcx
0x180043013  mov     r14, rdx
0x180043016  xor     ecx, ecx; hdc
0x180043018  xor     r12d, r12d
0x18004301b  call    cs:__imp_CreateCompatibleDC
0x180043021  mov     r15, rax
0x180043024  test    rax, rax
0x180043027  jz      loc_18004312F
0x18004302d  xor     ecx, ecx; hdc
0x18004302f  call    cs:__imp_CreateCompatibleDC
0x180043035  mov     rbp, rax
0x180043038  test    rax, rax
0x18004303b  jz      loc_180043126
0x180043041  mov     eax, [r14+8]
0x180043045  lea     r9, [rsp+98h+h]; HBITMAP *
0x18004304d  sub     eax, [r14]
0x180043050  lea     r8, [rsp+98h+var_48]; void **
0x180043055  mov     [rsp+98h+arg_10.cx], eax
0x18004305c  lea     rdx, [rsp+98h+arg_10]; struct tagSIZE *
0x180043064  mov     eax, [r14+0Ch]
0x180043068  mov     rcx, rbp; hDC
0x18004306b  sub     eax, [r14+4]
0x18004306f  mov     [rsp+98h+arg_10.cy], eax
0x180043076  mov     [rsp+98h+h], r12
0x18004307e  mov     [rsp+98h+var_48], r12
0x180043083  call    ?Create32BitHBITMAP@@YAJPEAUHDC__@@PEBUtagSIZE@@PEAPEAXPEAPEAUHBITMAP__@@@Z; Create32BitHBITMAP(HDC__ *,tagSIZE const *,void * *,HBITMAP__ * *)
0x180043088  test    eax, eax
0x18004308a  js      loc_18004311D
0x180043090  mov     rdx, [r13+0]; h
0x180043094  mov     rcx, r15; hdc
0x180043097  call    cs:__imp_SelectObject
0x18004309d  mov     rsi, [rsp+98h+h]
0x1800430a5  mov     rcx, rbp; hdc
0x1800430a8  mov     rdx, rsi; h
0x1800430ab  mov     rdi, rax
0x1800430ae  call    cs:__imp_SelectObject
0x1800430b4  mov     r9d, [rsp+98h+arg_10.cx]; cx
0x1800430bc  xor     r8d, r8d; y
0x1800430bf  mov     rbx, rax
0x1800430c2  mov     [rsp+98h+rop], 0CC0020h; rop
0x1800430ca  mov     eax, [r14+4]
0x1800430ce  xor     edx, edx; x
0x1800430d0  mov     [rsp+98h+y1], eax; y1
0x1800430d4  mov     rcx, rbp; hdc
0x1800430d7  mov     eax, [r14]
0x1800430da  mov     [rsp+98h+x1], eax; x1
0x1800430de  mov     eax, [rsp+98h+arg_10.cy]
0x1800430e5  mov     [rsp+98h+hdcSrc], r15; hdcSrc
0x1800430ea  mov     [rsp+98h+cy], eax; cy
0x1800430ee  call    cs:__imp_BitBlt
0x1800430f4  mov     rdx, rbx; h
0x1800430f7  mov     rcx, rbp; hdc
0x1800430fa  mov     r12d, eax
0x1800430fd  call    cs:__imp_SelectObject
0x180043103  mov     rdx, rdi; h
0x180043106  mov     rcx, r15; hdc
0x180043109  call    cs:__imp_SelectObject
0x18004310f  mov     rcx, [r13+0]; ho
0x180043113  call    cs:__imp_DeleteObject
0x180043119  mov     [r13+0], rsi
0x18004311d  mov     rcx, rbp; hdc
0x180043120  call    cs:__imp_DeleteDC
0x180043126  mov     rcx, r15; hdc
0x180043129  call    cs:__imp_DeleteDC
0x18004312f  mov     rbx, [rsp+98h+arg_0]
0x180043137  mov     eax, r12d
0x18004313a  add     rsp, 60h
0x18004313e  pop     r15
0x180043140  pop     r14
0x180043142  pop     r13
0x180043144  pop     r12
0x180043146  pop     rdi
0x180043147  pop     rsi
0x180043148  pop     rbp
0x180043149  retn
```
