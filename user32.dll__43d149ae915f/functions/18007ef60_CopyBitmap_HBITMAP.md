# CopyBitmap(HBITMAP__ *)

- ea: `0x18007ef60`
- end: `0x18007f08d`
- name: `?CopyBitmap@@YAPEAUHBITMAP__@@PEAU1@@Z`
- size: `301`
- prototype: `HBITMAP __fastcall(HBITMAP h)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18007f094`

## callees

- `0x18007ef60`

## import_xrefs

- `win32u!NtUserReleaseDC` at `0x18007f073`
- `win32u!NtUserReleaseDC` at `0x18007f073`
- `win32u!NtUserGetDC` at `0x18007ef97`
- `win32u!NtUserGetDC` at `0x18007ef97`
- `GDI32!SelectObject` at `0x18007efdc`
- `GDI32!SelectObject` at `0x18007f005`
- `GDI32!SelectObject` at `0x18007f04c`
- `GDI32!SelectObject` at `0x18007f058`
- `GDI32!SelectObject` at `0x18007efdc`
- `GDI32!SelectObject` at `0x18007f005`
- `GDI32!SelectObject` at `0x18007f04c`
- `GDI32!SelectObject` at `0x18007f058`
- `GDI32!GetObjectW` at `0x18007ef87`
- `GDI32!GetObjectW` at `0x18007ef87`
- `GDI32!CreateCompatibleBitmap` at `0x18007eff1`
- `GDI32!CreateCompatibleBitmap` at `0x18007eff1`
- `GDI32!DeleteDC` at `0x18007f061`
- `GDI32!DeleteDC` at `0x18007f06a`
- `GDI32!DeleteDC` at `0x18007f061`
- `GDI32!DeleteDC` at `0x18007f06a`
- `GDI32!BitBlt` at `0x18007f040`
- `GDI32!BitBlt` at `0x18007f040`
- `GDI32!CreateCompatibleDC` at `0x18007efaf`
- `GDI32!CreateCompatibleDC` at `0x18007efc4`
- `GDI32!CreateCompatibleDC` at `0x18007efaf`
- `GDI32!CreateCompatibleDC` at `0x18007efc4`

## pseudocode

```c
HBITMAP __fastcall CopyBitmap(HBITMAP h)
{
  HDC DC; // rax
  HDC v3; // rdi
  HBITMAP v4; // r14
  HDC hdcSrc; // rsi
  HDC CompatibleDC; // rbp
  HGDIOBJ v7; // r15
  HBITMAP CompatibleBitmap; // rax
  HGDIOBJ v9; // rbx
  _OWORD pv[5]; // [rsp+50h] [rbp-58h] BYREF

  memset(pv, 0, 32);
  if ( !GetObjectW(h, 32, pv) )
    return 0;
  DC = (HDC)NtUserGetDC(0);
  v3 = DC;
  if ( !DC )
    return 0;
  v4 = 0;
  hdcSrc = CreateCompatibleDC(DC);
  if ( hdcSrc )
  {
    CompatibleDC = CreateCompatibleDC(v3);
    if ( CompatibleDC )
    {
      v7 = SelectObject(hdcSrc, h);
      CompatibleBitmap = CreateCompatibleBitmap(hdcSrc, SDWORD1(pv[0]), SDWORD2(pv[0]));
      v4 = CompatibleBitmap;
      if ( CompatibleBitmap )
      {
        v9 = SelectObject(CompatibleDC, CompatibleBitmap);
        BitBlt(CompatibleDC, 0, 0, SDWORD1(pv[0]), SDWORD2(pv[0]), hdcSrc, 0, 0, 0xCC0020u);
        SelectObject(hdcSrc, v7);
        SelectObject(CompatibleDC, v9);
      }
      DeleteDC(CompatibleDC);
    }
    DeleteDC(hdcSrc);
  }
  NtUserReleaseDC(v3);
  return v4;
}

```

## disassembly

```asm
0x18007ef60  push    rbx
0x18007ef62  push    rbp
0x18007ef63  push    rsi
0x18007ef64  push    rdi
0x18007ef65  push    r14
0x18007ef67  push    r15
0x18007ef69  sub     rsp, 78h
0x18007ef6d  xorps   xmm0, xmm0
0x18007ef70  lea     r8, [rsp+0A8h+pv]; pv
0x18007ef75  mov     edx, 20h ; ' '; c
0x18007ef7a  mov     rbx, rcx
0x18007ef7d  movups  [rsp+0A8h+pv], xmm0
0x18007ef82  movups  [rsp+0A8h+var_48], xmm0
0x18007ef87  call    cs:__imp_GetObjectW
0x18007ef8d  test    eax, eax
0x18007ef8f  jz      loc_18007F07E
0x18007ef95  xor     ecx, ecx
0x18007ef97  call    cs:__imp_NtUserGetDC
0x18007ef9d  mov     rdi, rax
0x18007efa0  test    rax, rax
0x18007efa3  jz      loc_18007F07E
0x18007efa9  mov     rcx, rax; hdc
0x18007efac  xor     r14d, r14d
0x18007efaf  call    cs:__imp_CreateCompatibleDC
0x18007efb5  mov     rsi, rax
0x18007efb8  test    rax, rax
0x18007efbb  jz      loc_18007F070
0x18007efc1  mov     rcx, rdi; hdc
0x18007efc4  call    cs:__imp_CreateCompatibleDC
0x18007efca  mov     rbp, rax
0x18007efcd  test    rax, rax
0x18007efd0  jz      loc_18007F067
0x18007efd6  mov     rdx, rbx; h
0x18007efd9  mov     rcx, rsi; hdc
0x18007efdc  call    cs:__imp_SelectObject
0x18007efe2  mov     r8d, dword ptr [rsp+0A8h+pv+8]; cy
0x18007efe7  mov     rcx, rsi; hdc
0x18007efea  mov     edx, dword ptr [rsp+0A8h+pv+4]; cx
0x18007efee  mov     r15, rax
0x18007eff1  call    cs:__imp_CreateCompatibleBitmap
0x18007eff7  mov     r14, rax
0x18007effa  test    rax, rax
0x18007effd  jz      short loc_18007F05E
0x18007efff  mov     rdx, rax; h
0x18007f002  mov     rcx, rbp; hdc
0x18007f005  call    cs:__imp_SelectObject
0x18007f00b  mov     ecx, dword ptr [rsp+0A8h+pv+8]
0x18007f00f  xor     r8d, r8d; y
0x18007f012  mov     r9d, dword ptr [rsp+0A8h+pv+4]; cx
0x18007f017  xor     edx, edx; x
0x18007f019  mov     [rsp+0A8h+rop], 0CC0020h; rop
0x18007f021  mov     rbx, rax
0x18007f024  mov     [rsp+0A8h+y1], 0; y1
0x18007f02c  mov     [rsp+0A8h+x1], 0; x1
0x18007f034  mov     [rsp+0A8h+hdcSrc], rsi; hdcSrc
0x18007f039  mov     [rsp+0A8h+cy], ecx; cy
0x18007f03d  mov     rcx, rbp; hdc
0x18007f040  call    cs:__imp_BitBlt
0x18007f046  mov     rdx, r15; h
0x18007f049  mov     rcx, rsi; hdc
0x18007f04c  call    cs:__imp_SelectObject
0x18007f052  mov     rdx, rbx; h
0x18007f055  mov     rcx, rbp; hdc
0x18007f058  call    cs:__imp_SelectObject
0x18007f05e  mov     rcx, rbp; hdc
0x18007f061  call    cs:__imp_DeleteDC
0x18007f067  mov     rcx, rsi; hdc
0x18007f06a  call    cs:__imp_DeleteDC
0x18007f070  mov     rcx, rdi
0x18007f073  call    cs:__imp_NtUserReleaseDC
0x18007f079  mov     rax, r14
0x18007f07c  jmp     short loc_18007F080
0x18007f07e  xor     eax, eax
0x18007f080  add     rsp, 78h
0x18007f084  pop     r15
0x18007f086  pop     r14
0x18007f088  pop     rdi
0x18007f089  pop     rsi
0x18007f08a  pop     rbp
0x18007f08b  pop     rbx
0x18007f08c  retn
```
