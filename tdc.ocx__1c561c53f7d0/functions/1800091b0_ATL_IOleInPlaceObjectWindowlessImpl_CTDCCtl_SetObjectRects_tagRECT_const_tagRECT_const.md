# ATL::IOleInPlaceObjectWindowlessImpl<CTDCCtl>::SetObjectRects(tagRECT const *,tagRECT const *)

- ea: `0x1800091b0`
- end: `0x1800092c6`
- name: `?SetObjectRects@?$IOleInPlaceObjectWindowlessImpl@VCTDCCtl@@@ATL@@UEAAJPEBUtagRECT@@0@Z`
- size: `278`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x1800091b0`
- `0x180014270`

## import_xrefs

- `USER32!IntersectRect` at `0x180009223`
- `USER32!IntersectRect` at `0x180009223`
- `USER32!EqualRect` at `0x180009235`
- `USER32!EqualRect` at `0x180009235`
- `USER32!OffsetRect` at `0x18000924f`
- `USER32!OffsetRect` at `0x18000924f`
- `USER32!SetWindowRgn` at `0x180009272`
- `USER32!SetWindowRgn` at `0x180009272`
- `USER32!SetWindowPos` at `0x1800092a2`
- `USER32!SetWindowPos` at `0x1800092a2`
- `GDI32!CreateRectRgnIndirect` at `0x18000925a`
- `GDI32!CreateRectRgnIndirect` at `0x18000925a`

## pseudocode

```c
__int64 __fastcall ATL::IOleInPlaceObjectWindowlessImpl<CTDCCtl>::SetObjectRects(
        __int64 a1,
        const RECT *a2,
        const RECT *a3)
{
  __int64 v4; // rax
  __int64 v5; // rdi
  HRGN v6; // rsi
  struct tagRECT rcDst; // [rsp+40h] [rbp-38h] BYREF

  if ( !a2 || !a3 )
    return 2147500035LL;
  v4 = a1 - 152;
  v5 = a1 - 136;
  if ( !a1 )
    v4 = 72;
  *(RECT *)v4 = *a2;
  if ( !a1 )
    v5 = 88;
  if ( **(_QWORD **)v5 )
  {
    v6 = 0;
    rcDst = 0;
    if ( IntersectRect(&rcDst, a2, a3) )
    {
      if ( !EqualRect(&rcDst, a2) )
      {
        OffsetRect(&rcDst, -a2->left, -a2->top);
        v6 = CreateRectRgnIndirect(&rcDst);
      }
    }
    SetWindowRgn(**(HWND **)v5, v6, 1);
    SetWindowPos(**(HWND **)v5, 0, a2->left, a2->top, a2->right - a2->left, a2->bottom - a2->top, 0x14u);
  }
  return 0;
}

```

## disassembly

```asm
0x1800091b0  push    rbx
0x1800091b2  push    rsi
0x1800091b3  push    rdi
0x1800091b4  sub     rsp, 60h
0x1800091b8  mov     rax, cs:__security_cookie
0x1800091bf  xor     rax, rsp
0x1800091c2  mov     [rsp+78h+var_28], rax
0x1800091c7  mov     rbx, rdx
0x1800091ca  test    rdx, rdx
0x1800091cd  jz      loc_1800092AC
0x1800091d3  test    r8, r8
0x1800091d6  jz      loc_1800092AC
0x1800091dc  movups  xmm0, xmmword ptr [rbx]
0x1800091df  test    rcx, rcx
0x1800091e2  lea     rax, [rcx-98h]
0x1800091e9  mov     edx, 48h ; 'H'
0x1800091ee  lea     rdi, [rcx-88h]
0x1800091f5  cmovz   rax, rdx
0x1800091f9  movdqu  xmmword ptr [rax], xmm0
0x1800091fd  lea     eax, [rdx+10h]
0x180009200  cmovz   rdi, rax
0x180009204  mov     rax, [rdi]
0x180009207  cmp     qword ptr [rax], 0
0x18000920b  jz      loc_1800092A8
0x180009211  xorps   xmm0, xmm0
0x180009214  lea     rcx, [rsp+78h+rcDst]; lprcDst
0x180009219  mov     rdx, rbx; lprcSrc1
0x18000921c  xor     esi, esi
0x18000921e  movups  xmmword ptr [rsp+78h+rcDst.left], xmm0
0x180009223  call    cs:__imp_IntersectRect
0x180009229  test    eax, eax
0x18000922b  jz      short loc_180009263
0x18000922d  mov     rdx, rbx; lprc2
0x180009230  lea     rcx, [rsp+78h+rcDst]; lprc1
0x180009235  call    cs:__imp_EqualRect
0x18000923b  test    eax, eax
0x18000923d  jnz     short loc_180009263
0x18000923f  mov     r8d, [rbx+4]
0x180009243  lea     rcx, [rsp+78h+rcDst]; lprc
0x180009248  mov     edx, [rbx]
0x18000924a  neg     r8d; dy
0x18000924d  neg     edx; dx
0x18000924f  call    cs:__imp_OffsetRect
0x180009255  lea     rcx, [rsp+78h+rcDst]; lprect
0x18000925a  call    cs:__imp_CreateRectRgnIndirect
0x180009260  mov     rsi, rax
0x180009263  mov     rcx, [rdi]
0x180009266  mov     r8d, 1; bRedraw
0x18000926c  mov     rdx, rsi; hRgn
0x18000926f  mov     rcx, [rcx]; hWnd
0x180009272  call    cs:__imp_SetWindowRgn
0x180009278  mov     edx, [rbx+0Ch]
0x18000927b  mov     rcx, [rdi]
0x18000927e  mov     r9d, [rbx+4]; Y
0x180009282  sub     edx, r9d
0x180009285  mov     eax, [rbx+8]
0x180009288  sub     eax, [rbx]
0x18000928a  mov     rcx, [rcx]; hWnd
0x18000928d  mov     r8d, [rbx]; X
0x180009290  mov     [rsp+78h+uFlags], 14h; uFlags
0x180009298  mov     [rsp+78h+cy], edx; cy
0x18000929c  xor     edx, edx; hWndInsertAfter
0x18000929e  mov     [rsp+78h+var_58], eax; cx
0x1800092a2  call    cs:__imp_SetWindowPos
0x1800092a8  xor     eax, eax
0x1800092aa  jmp     short loc_1800092B1
0x1800092ac  mov     eax, 80004003h
0x1800092b1  mov     rcx, [rsp+78h+var_28]
0x1800092b6  xor     rcx, rsp; StackCookie
0x1800092b9  call    __security_check_cookie
0x1800092be  add     rsp, 60h
0x1800092c2  pop     rdi
0x1800092c3  pop     rsi
0x1800092c4  pop     rbx
0x1800092c5  retn
```
