# CUserTileControl::_PaintWorker(HDC__ *,tagRECT const &)

- ea: `0x18006de98`
- end: `0x18006dff7`
- name: `?_PaintWorker@CUserTileControl@@AEAAXPEAUHDC__@@AEBUtagRECT@@@Z`
- size: `351`
- prototype: `void(CUserTileControl *__hidden this, HDC, const struct tagRECT *)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18006dcf4`

## callees

- `0x18006bc28`
- `0x18006be54`
- `0x18006bf28`
- `0x18006d7f8`
- `0x18006de98`
- `0x180091ef0`

## import_xrefs

- `gdiplus!GdipDeleteGraphics` at `0x18006dfda`
- `gdiplus!GdipDeleteGraphics` at `0x18006dfda`
- `gdiplus!GdipCreateBitmapFromHBITMAP` at `0x18006df47`
- `gdiplus!GdipCreateBitmapFromHBITMAP` at `0x18006df47`
- `gdiplus!GdipDisposeImage` at `0x18006dfd0`
- `gdiplus!GdipDisposeImage` at `0x18006dfd0`

## pseudocode

```c
void __fastcall CUserTileControl::_PaintWorker(CUserTileControl *this, HDC a2, const struct tagRECT *a3)
{
  LONG v5; // ecx
  LONG v6; // eax
  int v7; // ecx
  LONG v8; // eax
  __int64 v9; // rcx
  int v10; // eax
  __int64 v11; // rbx
  struct tagRECT v12; // [rsp+30h] [rbp-19h] BYREF
  _QWORD v13[2]; // [rsp+40h] [rbp-9h] BYREF
  _QWORD v14[2]; // [rsp+50h] [rbp+7h] BYREF
  int v15; // [rsp+60h] [rbp+17h]
  struct tagRECT v16; // [rsp+68h] [rbp+1Fh] BYREF
  struct tagRECT v17; // [rsp+78h] [rbp+2Fh] BYREF

  Gdiplus::Graphics::Graphics((Gdiplus::Graphics *)v13, a2);
  v16.right = *((_DWORD *)this + 9);
  v16.bottom = *((_DWORD *)this + 10);
  *(_QWORD *)&v16.left = 0;
  CenterRect(&v16, a3);
  v5 = v16.left + *((_DWORD *)this + 5);
  v12.right = v16.right - *((_DWORD *)this + 6);
  v6 = v16.bottom - *((_DWORD *)this + 8);
  v12.left = v5;
  v7 = *((_DWORD *)this + 7);
  v12.bottom = v6;
  v17.right = *((_DWORD *)this + 13);
  v8 = *((_DWORD *)this + 14);
  v12.top = v16.top + v7;
  v17.bottom = v8;
  *(_QWORD *)&v17.left = 0;
  CenterRect(&v17, &v12);
  v9 = *((_QWORD *)this + 9);
  v14[0] = &Gdiplus::Image::`vftable';
  *(_QWORD *)&v12.left = 0;
  v10 = GdipCreateBitmapFromHBITMAP(v9, 0, &v12);
  v11 = *(_QWORD *)&v12.left;
  v15 = v10;
  v14[1] = *(_QWORD *)&v12.left;
  Gdiplus::Graphics::SetCompositingMode(v13);
  Gdiplus::Graphics::DrawImage(
    v13,
    v14,
    (unsigned int)v17.left,
    (unsigned int)v17.top,
    v17.right - v17.left,
    v17.bottom - v17.top,
    *(_QWORD *)&v12.left);
  if ( *(_QWORD *)(*((_QWORD *)this + 11) + 32LL) )
  {
    Gdiplus::Graphics::SetCompositingMode(v13);
    Gdiplus::Graphics::DrawImage(
      v13,
      *(_QWORD *)(*((_QWORD *)this + 11) + 32LL),
      (unsigned int)v16.left,
      (unsigned int)v16.top,
      v16.right - v16.left,
      v16.bottom - v16.top,
      *(_QWORD *)&v12.left);
  }
  GdipDisposeImage(v11);
  GdipDeleteGraphics(v13[0]);
}

```

## disassembly

```asm
0x18006de98  push    rbp
0x18006de9a  push    rbx
0x18006de9b  push    rdi
0x18006de9c  lea     rbp, [rsp-47h]
0x18006dea1  sub     rsp, 90h
0x18006dea8  mov     rax, cs:__security_cookie
0x18006deaf  xor     rax, rsp
0x18006deb2  mov     [rbp+57h+var_18], rax
0x18006deb6  mov     rdi, rcx
0x18006deb9  mov     rbx, r8
0x18006debc  lea     rcx, [rbp+57h+var_60]; this
0x18006dec0  call    ??0Graphics@Gdiplus@@QEAA@PEAUHDC__@@@Z; Gdiplus::Graphics::Graphics(HDC__ *)
0x18006dec5  mov     eax, [rdi+24h]
0x18006dec8  lea     rcx, [rbp+57h+var_38]; struct tagRECT *
0x18006decc  mov     [rbp+57h+var_38.right], eax
0x18006decf  mov     rdx, rbx; struct tagRECT *
0x18006ded2  mov     eax, [rdi+28h]
0x18006ded5  mov     [rbp+57h+var_38.bottom], eax
0x18006ded8  mov     qword ptr [rbp+57h+var_38.left], 0
0x18006dee0  call    ?CenterRect@@YAXPEAUtagRECT@@PEBU1@@Z; CenterRect(tagRECT *,tagRECT const *)
0x18006dee5  mov     ecx, [rdi+14h]
0x18006dee8  lea     rdx, [rbp+57h+var_70]; struct tagRECT *
0x18006deec  add     ecx, [rbp+57h+var_38.left]
0x18006deef  mov     eax, [rbp+57h+var_38.right]
0x18006def2  sub     eax, [rdi+18h]
0x18006def5  mov     [rbp+57h+var_70.right], eax
0x18006def8  mov     eax, [rbp+57h+var_38.bottom]
0x18006defb  sub     eax, [rdi+20h]
0x18006defe  mov     [rbp+57h+var_70.left], ecx
0x18006df01  mov     ecx, [rdi+1Ch]
0x18006df04  add     ecx, [rbp+57h+var_38.top]
0x18006df07  mov     [rbp+57h+var_70.bottom], eax
0x18006df0a  mov     eax, [rdi+34h]
0x18006df0d  mov     [rbp+57h+var_28.right], eax
0x18006df10  mov     eax, [rdi+38h]
0x18006df13  mov     [rbp+57h+var_70.top], ecx
0x18006df16  lea     rcx, [rbp+57h+var_28]; struct tagRECT *
0x18006df1a  mov     [rbp+57h+var_28.bottom], eax
0x18006df1d  mov     qword ptr [rbp+57h+var_28.left], 0
0x18006df25  call    ?CenterRect@@YAXPEAUtagRECT@@PEBU1@@Z; CenterRect(tagRECT *,tagRECT const *)
0x18006df2a  mov     rcx, [rdi+48h]
0x18006df2e  lea     rax, ??_7Image@Gdiplus@@6B@; const Gdiplus::Image::`vftable'
0x18006df35  lea     r8, [rbp+57h+var_70]
0x18006df39  mov     [rbp+57h+var_50], rax
0x18006df3d  xor     edx, edx
0x18006df3f  mov     qword ptr [rbp+57h+var_70.left], 0
0x18006df47  call    cs:__imp_GdipCreateBitmapFromHBITMAP
0x18006df4d  mov     rbx, qword ptr [rbp+57h+var_70.left]
0x18006df51  lea     rcx, [rbp+57h+var_60]
0x18006df55  mov     [rbp+57h+var_40], eax
0x18006df58  mov     [rbp+57h+var_48], rbx
0x18006df5c  call    ?SetCompositingMode@Graphics@Gdiplus@@QEAA?AW4Status@2@W4CompositingMode@2@@Z; Gdiplus::Graphics::SetCompositingMode(Gdiplus::CompositingMode)
0x18006df61  mov     ecx, [rbp+57h+var_28.bottom]
0x18006df64  lea     rdx, [rbp+57h+var_50]
0x18006df68  mov     r9d, [rbp+57h+var_28.top]
0x18006df6c  sub     ecx, r9d
0x18006df6f  mov     eax, [rbp+57h+var_28.right]
0x18006df72  mov     r8d, [rbp+57h+var_28.left]
0x18006df76  sub     eax, r8d
0x18006df79  mov     [rsp+0A0h+var_78], ecx
0x18006df7d  lea     rcx, [rbp+57h+var_60]
0x18006df81  mov     [rsp+0A0h+var_80], eax
0x18006df85  call    ?DrawImage@Graphics@Gdiplus@@QEAA?AW4Status@2@PEAVImage@2@HHHH@Z; Gdiplus::Graphics::DrawImage(Gdiplus::Image *,int,int,int,int)
0x18006df8a  mov     rax, [rdi+58h]
0x18006df8e  cmp     qword ptr [rax+20h], 0
0x18006df93  jz      short loc_18006DFCD
0x18006df95  lea     rcx, [rbp+57h+var_60]
0x18006df99  call    ?SetCompositingMode@Graphics@Gdiplus@@QEAA?AW4Status@2@W4CompositingMode@2@@Z; Gdiplus::Graphics::SetCompositingMode(Gdiplus::CompositingMode)
0x18006df9e  mov     rdx, [rdi+58h]
0x18006dfa2  lea     rcx, [rbp+57h+var_60]
0x18006dfa6  mov     r10d, [rbp+57h+var_38.bottom]
0x18006dfaa  mov     r9d, [rbp+57h+var_38.top]
0x18006dfae  sub     r10d, r9d
0x18006dfb1  mov     eax, [rbp+57h+var_38.right]
0x18006dfb4  mov     r8d, [rbp+57h+var_38.left]
0x18006dfb8  sub     eax, r8d
0x18006dfbb  mov     rdx, [rdx+20h]
0x18006dfbf  mov     [rsp+0A0h+var_78], r10d
0x18006dfc4  mov     [rsp+0A0h+var_80], eax
0x18006dfc8  call    ?DrawImage@Graphics@Gdiplus@@QEAA?AW4Status@2@PEAVImage@2@HHHH@Z; Gdiplus::Graphics::DrawImage(Gdiplus::Image *,int,int,int,int)
0x18006dfcd  mov     rcx, rbx
0x18006dfd0  call    cs:__imp_GdipDisposeImage
0x18006dfd6  mov     rcx, [rbp+57h+var_60]
0x18006dfda  call    cs:__imp_GdipDeleteGraphics
0x18006dfe0  mov     rcx, [rbp+57h+var_18]
0x18006dfe4  xor     rcx, rsp; StackCookie
0x18006dfe7  call    __security_check_cookie
0x18006dfec  add     rsp, 90h
0x18006dff3  pop     rdi
0x18006dff4  pop     rbx
0x18006dff5  pop     rbp
0x18006dff6  retn
```
