# CThemeThumbnail::_AddRssToImage(HBITMAP__ *)

- ea: `0x1800579b0`
- end: `0x180057a9b`
- name: `?_AddRssToImage@CThemeThumbnail@@AEAAXPEAUHBITMAP__@@@Z`
- size: `235`
- prototype: `void(CThemeThumbnail *__hidden this, HBITMAP)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800581bc`

## callees

- `0x180031704`
- `0x1800578c0`
- `0x1800579b0`

## import_xrefs

- `GDI32!DeleteObject` at `0x180057a8a`
- `GDI32!DeleteObject` at `0x180057a8a`
- `GDI32!GetObjectW` at `0x180057a16`
- `GDI32!GetObjectW` at `0x180057a37`
- `GDI32!GetObjectW` at `0x180057a16`
- `GDI32!GetObjectW` at `0x180057a37`
- `GDI32!SelectObject` at `0x1800579f6`
- `GDI32!SelectObject` at `0x180057a78`
- `GDI32!SelectObject` at `0x1800579f6`
- `GDI32!SelectObject` at `0x180057a78`
- `GDI32!CreateCompatibleDC` at `0x1800579de`
- `GDI32!CreateCompatibleDC` at `0x1800579de`
- `GDI32!DeleteDC` at `0x180057a81`
- `GDI32!DeleteDC` at `0x180057a81`

## pseudocode

```c
void __fastcall CThemeThumbnail::_AddRssToImage(HDC *this, HBITMAP a2)
{
  HBITMAP BitmapWithWic; // rdi
  HDC CompatibleDC; // rax
  HDC v6; // rbx
  HGDIOBJ v7; // r14
  struct tagRECT v8; // [rsp+20h] [rbp-50h] BYREF
  _OWORD v9[2]; // [rsp+30h] [rbp-40h] BYREF
  _OWORD pv[2]; // [rsp+50h] [rbp-20h] BYREF

  BitmapWithWic = PremultiplyLoadBitmapWithWic((HINSTANCE)this, 0x262u);
  if ( BitmapWithWic )
  {
    CompatibleDC = CreateCompatibleDC(this[12]);
    v6 = CompatibleDC;
    if ( CompatibleDC )
    {
      memset(pv, 0, sizeof(pv));
      v7 = SelectObject(CompatibleDC, a2);
      if ( GetObjectW(a2, 32, pv) )
      {
        memset(v9, 0, sizeof(v9));
        if ( GetObjectW(BitmapWithWic, 32, v9) )
        {
          v8.top = 8;
          v8.left = DWORD1(pv[0]) - DWORD1(v9[0]) - 8;
          v8.right = DWORD1(pv[0]) - 8;
          v8.bottom = DWORD2(v9[0]) + 8;
          AlphaDrawImage(v6, BitmapWithWic, &v8);
        }
      }
      SelectObject(v6, v7);
      DeleteDC(v6);
    }
    DeleteObject(BitmapWithWic);
  }
}

```

## disassembly

```asm
0x1800579b0  push    rbp
0x1800579b2  push    rbx
0x1800579b3  push    rsi
0x1800579b4  push    rdi
0x1800579b5  push    r14
0x1800579b7  mov     rbp, rsp
0x1800579ba  sub     rsp, 70h
0x1800579be  mov     rsi, rdx
0x1800579c1  mov     rbx, rcx
0x1800579c4  mov     edx, 262h; unsigned int
0x1800579c9  call    ?PremultiplyLoadBitmapWithWic@@YAPEAUHBITMAP__@@PEAUHINSTANCE__@@I@Z; PremultiplyLoadBitmapWithWic(HINSTANCE__ *,uint)
0x1800579ce  mov     rdi, rax
0x1800579d1  test    rax, rax
0x1800579d4  jz      loc_180057A90
0x1800579da  mov     rcx, [rbx+60h]; hdc
0x1800579de  call    cs:__imp_CreateCompatibleDC
0x1800579e4  mov     rbx, rax
0x1800579e7  test    rax, rax
0x1800579ea  jz      loc_180057A87
0x1800579f0  mov     rdx, rsi; h
0x1800579f3  mov     rcx, rax; hdc
0x1800579f6  call    cs:__imp_SelectObject
0x1800579fc  xorps   xmm0, xmm0
0x1800579ff  lea     r8, [rbp+pv]; pv
0x180057a03  mov     edx, 20h ; ' '; c
0x180057a08  mov     rcx, rsi; h
0x180057a0b  movups  [rbp+pv], xmm0
0x180057a0f  mov     r14, rax
0x180057a12  movups  [rbp+var_10], xmm0
0x180057a16  call    cs:__imp_GetObjectW
0x180057a1c  test    eax, eax
0x180057a1e  jz      short loc_180057A72
0x180057a20  xorps   xmm0, xmm0
0x180057a23  lea     r8, [rbp+var_40]; pv
0x180057a27  mov     edx, 20h ; ' '; c
0x180057a2c  mov     rcx, rdi; h
0x180057a2f  movups  [rbp+var_40], xmm0
0x180057a33  movups  [rbp+var_30], xmm0
0x180057a37  call    cs:__imp_GetObjectW
0x180057a3d  test    eax, eax
0x180057a3f  jz      short loc_180057A72
0x180057a41  mov     eax, dword ptr [rbp+pv+4]
0x180057a44  lea     r8, [rbp+var_50]; struct tagRECT *
0x180057a48  sub     eax, dword ptr [rbp+var_40+4]
0x180057a4b  mov     rdx, rdi; h
0x180057a4e  add     eax, 0FFFFFFF8h
0x180057a51  mov     [rbp+var_50.top], 8
0x180057a58  mov     [rbp+var_50.left], eax
0x180057a5b  mov     rcx, rbx; hdcDest
0x180057a5e  add     eax, dword ptr [rbp+var_40+4]
0x180057a61  mov     [rbp+var_50.right], eax
0x180057a64  mov     eax, dword ptr [rbp+var_40+8]
0x180057a67  add     eax, 8
0x180057a6a  mov     [rbp+var_50.bottom], eax
0x180057a6d  call    ?AlphaDrawImage@@YAHPEAUHDC__@@PEAUHBITMAP__@@PEAUtagRECT@@@Z; AlphaDrawImage(HDC__ *,HBITMAP__ *,tagRECT *)
0x180057a72  mov     rdx, r14; h
0x180057a75  mov     rcx, rbx; hdc
0x180057a78  call    cs:__imp_SelectObject
0x180057a7e  mov     rcx, rbx; hdc
0x180057a81  call    cs:__imp_DeleteDC
0x180057a87  mov     rcx, rdi; ho
0x180057a8a  call    cs:__imp_DeleteObject
0x180057a90  add     rsp, 70h
0x180057a94  pop     r14
0x180057a96  pop     rdi
0x180057a97  pop     rsi
0x180057a98  pop     rbx
0x180057a99  pop     rbp
0x180057a9a  retn
```
