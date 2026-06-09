# Convert1BppToMonoBitmap(HDC__ *,HBITMAP__ *)

- ea: `0x180003a08`
- end: `0x180003b12`
- name: `?Convert1BppToMonoBitmap@@YAPEAUHBITMAP__@@PEAUHDC__@@PEAU1@@Z`
- size: `266`
- prototype: `HBITMAP(HDC, HBITMAP)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180005280`
- `0x18002f198`

## callees

- `0x180003a08`

## import_xrefs

- `GDI32!SelectObject` at `0x180003a85`
- `GDI32!SelectObject` at `0x180003a94`
- `GDI32!SelectObject` at `0x180003adb`
- `GDI32!SelectObject` at `0x180003ae7`
- `GDI32!SelectObject` at `0x180003a85`
- `GDI32!SelectObject` at `0x180003a94`
- `GDI32!SelectObject` at `0x180003adb`
- `GDI32!SelectObject` at `0x180003ae7`
- `GDI32!GetObjectW` at `0x180003a51`
- `GDI32!GetObjectW` at `0x180003a51`
- `GDI32!CreateBitmap` at `0x180003a71`
- `GDI32!CreateBitmap` at `0x180003a71`
- `GDI32!DeleteDC` at `0x180003afc`
- `GDI32!DeleteDC` at `0x180003afc`
- `GDI32!BitBlt` at `0x180003acf`
- `GDI32!BitBlt` at `0x180003acf`
- `GDI32!CreateCompatibleDC` at `0x180003a32`
- `GDI32!CreateCompatibleDC` at `0x180003a32`
- `GDI32!DeleteObject` at `0x180003af3`
- `GDI32!DeleteObject` at `0x180003af3`

## pseudocode

```c
HBITMAP __fastcall Convert1BppToMonoBitmap(HDC a1, HBITMAP a2)
{
  HDC hdcSrc; // r14
  HBITMAP v4; // rbx
  HDC CompatibleDC; // rsi
  HBITMAP Bitmap; // r15
  HGDIOBJ v7; // rdi
  HGDIOBJ v8; // rbx
  _OWORD pv[5]; // [rsp+50h] [rbp-58h] BYREF

  hdcSrc = ghdcBits2;
  v4 = a2;
  memset(pv, 0, 32);
  CompatibleDC = CreateCompatibleDC(ghdcBits2);
  if ( CompatibleDC )
  {
    GetObjectW(v4, 32, pv);
    Bitmap = CreateBitmap(SDWORD1(pv[0]), SDWORD2(pv[0]), 1u, 1u, 0);
    if ( Bitmap )
    {
      v7 = SelectObject(hdcSrc, v4);
      v8 = SelectObject(CompatibleDC, Bitmap);
      BitBlt(CompatibleDC, 0, 0, SDWORD1(pv[0]), SDWORD2(pv[0]), hdcSrc, 0, 0, 0xCC0020u);
      SelectObject(hdcSrc, v7);
      SelectObject(CompatibleDC, v8);
      v4 = Bitmap;
      DeleteObject(a2);
    }
    DeleteDC(CompatibleDC);
  }
  return v4;
}

```

## disassembly

```asm
0x180003a08  push    rbx
0x180003a0a  push    rbp
0x180003a0b  push    rsi
0x180003a0c  push    rdi
0x180003a0d  push    r14
0x180003a0f  push    r15
0x180003a11  sub     rsp, 78h
0x180003a15  mov     r14, cs:ghdcBits2
0x180003a1c  xorps   xmm0, xmm0
0x180003a1f  mov     rcx, r14; hdc
0x180003a22  mov     rbp, rdx
0x180003a25  mov     rbx, rdx
0x180003a28  movups  [rsp+0A8h+pv], xmm0
0x180003a2d  movups  [rsp+0A8h+var_48], xmm0
0x180003a32  call    cs:__imp_CreateCompatibleDC
0x180003a38  mov     rsi, rax
0x180003a3b  test    rax, rax
0x180003a3e  jz      loc_180003B02
0x180003a44  lea     r8, [rsp+0A8h+pv]; pv
0x180003a49  mov     edx, 20h ; ' '; c
0x180003a4e  mov     rcx, rbx; h
0x180003a51  call    cs:__imp_GetObjectW
0x180003a57  mov     edx, dword ptr [rsp+0A8h+pv+8]; nHeight
0x180003a5b  mov     r8d, 1; nPlanes
0x180003a61  mov     ecx, dword ptr [rsp+0A8h+pv+4]; nWidth
0x180003a65  mov     r9d, r8d; nBitCount
0x180003a68  mov     [rsp+0A8h+lpBits], 0; lpBits
0x180003a71  call    cs:__imp_CreateBitmap
0x180003a77  mov     r15, rax
0x180003a7a  test    rax, rax
0x180003a7d  jz      short loc_180003AF9
0x180003a7f  mov     rdx, rbx; h
0x180003a82  mov     rcx, r14; hdc
0x180003a85  call    cs:__imp_SelectObject
0x180003a8b  mov     rdx, r15; h
0x180003a8e  mov     rcx, rsi; hdc
0x180003a91  mov     rdi, rax
0x180003a94  call    cs:__imp_SelectObject
0x180003a9a  mov     r9d, dword ptr [rsp+0A8h+pv+4]; cx
0x180003a9f  xor     r8d, r8d; y
0x180003aa2  mov     [rsp+0A8h+rop], 0CC0020h; rop
0x180003aaa  mov     rbx, rax
0x180003aad  mov     eax, dword ptr [rsp+0A8h+pv+8]
0x180003ab1  xor     edx, edx; x
0x180003ab3  mov     [rsp+0A8h+y1], 0; y1
0x180003abb  mov     rcx, rsi; hdc
0x180003abe  mov     [rsp+0A8h+x1], 0; x1
0x180003ac6  mov     [rsp+0A8h+hdcSrc], r14; hdcSrc
0x180003acb  mov     dword ptr [rsp+0A8h+lpBits], eax; cy
0x180003acf  call    cs:__imp_BitBlt
0x180003ad5  mov     rdx, rdi; h
0x180003ad8  mov     rcx, r14; hdc
0x180003adb  call    cs:__imp_SelectObject
0x180003ae1  mov     rdx, rbx; h
0x180003ae4  mov     rcx, rsi; hdc
0x180003ae7  call    cs:__imp_SelectObject
0x180003aed  mov     rcx, rbp; ho
0x180003af0  mov     rbx, r15
0x180003af3  call    cs:__imp_DeleteObject
0x180003af9  mov     rcx, rsi; hdc
0x180003afc  call    cs:__imp_DeleteDC
0x180003b02  mov     rax, rbx
0x180003b05  add     rsp, 78h
0x180003b09  pop     r15
0x180003b0b  pop     r14
0x180003b0d  pop     rdi
0x180003b0e  pop     rsi
0x180003b0f  pop     rbp
0x180003b10  pop     rbx
0x180003b11  retn
```
