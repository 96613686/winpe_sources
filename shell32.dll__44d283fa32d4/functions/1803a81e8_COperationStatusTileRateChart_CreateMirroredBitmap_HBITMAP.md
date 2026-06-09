# COperationStatusTileRateChart::CreateMirroredBitmap(HBITMAP__ *)

- ea: `0x1803a81e8`
- end: `0x1803a83aa`
- name: `?CreateMirroredBitmap@COperationStatusTileRateChart@@AEAAPEAUHBITMAP__@@PEAU2@@Z`
- size: `450`
- prototype: `HBITMAP(COperationStatusTileRateChart *__hidden this, HBITMAP)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800ba8f4`
- `0x1800bb78c`

## callees

- `0x180249490`
- `0x1803a81e8`

## import_xrefs

- `USER32!ReleaseDC` at `0x1803a837d`
- `USER32!ReleaseDC` at `0x1803a837d`
- `USER32!GetDC` at `0x1803a820e`
- `USER32!GetDC` at `0x1803a820e`
- `GDI32!SetLayout` at `0x1803a82ec`
- `GDI32!SetLayout` at `0x1803a82ec`
- `GDI32!CreateCompatibleDC` at `0x1803a8255`
- `GDI32!CreateCompatibleDC` at `0x1803a8270`
- `GDI32!CreateCompatibleDC` at `0x1803a8255`
- `GDI32!CreateCompatibleDC` at `0x1803a8270`
- `GDI32!SelectObject` at `0x1803a82b2`
- `GDI32!SelectObject` at `0x1803a82d0`
- `GDI32!SelectObject` at `0x1803a833c`
- `GDI32!SelectObject` at `0x1803a834e`
- `GDI32!SelectObject` at `0x1803a82b2`
- `GDI32!SelectObject` at `0x1803a82d0`
- `GDI32!SelectObject` at `0x1803a833c`
- `GDI32!SelectObject` at `0x1803a834e`
- `GDI32!DeleteDC` at `0x1803a835d`
- `GDI32!DeleteDC` at `0x1803a836c`
- `GDI32!DeleteDC` at `0x1803a835d`
- `GDI32!DeleteDC` at `0x1803a836c`
- `GDI32!BitBlt` at `0x1803a832a`
- `GDI32!BitBlt` at `0x1803a832a`
- `GDI32!GetObjectW` at `0x1803a823e`
- `GDI32!GetObjectW` at `0x1803a823e`
- `GDI32!CreateCompatibleBitmap` at `0x1803a8294`
- `GDI32!CreateCompatibleBitmap` at `0x1803a8294`

## pseudocode

```c
HBITMAP __fastcall COperationStatusTileRateChart::CreateMirroredBitmap(COperationStatusTileRateChart *this, HBITMAP a2)
{
  HBITMAP CompatibleBitmap; // rbp
  HDC DC; // rbx
  HDC hdcSrc; // rdi
  HDC CompatibleDC; // rsi
  HGDIOBJ v7; // r14
  HGDIOBJ v8; // r15
  _OWORD pv[2]; // [rsp+50h] [rbp-68h] BYREF

  CompatibleBitmap = 0;
  DC = GetDC(0);
  if ( DC )
  {
    memset(pv, 0, sizeof(pv));
    if ( GetObjectW(a2, 32, pv) )
    {
      hdcSrc = CreateCompatibleDC(DC);
      if ( hdcSrc )
      {
        CompatibleDC = CreateCompatibleDC(DC);
        if ( CompatibleDC )
        {
          CompatibleBitmap = CreateCompatibleBitmap(DC, SDWORD1(pv[0]), SDWORD2(pv[0]));
          if ( CompatibleBitmap )
          {
            v7 = SelectObject(hdcSrc, a2);
            if ( v7 )
            {
              v8 = SelectObject(CompatibleDC, CompatibleBitmap);
              if ( v8 )
              {
                SetLayout(CompatibleDC, 1u);
                BitBlt(CompatibleDC, 0, 0, SDWORD1(pv[0]), SDWORD2(pv[0]), hdcSrc, 0, 0, 0xCC0020u);
                SelectObject(CompatibleDC, v8);
              }
              SelectObject(hdcSrc, v7);
            }
          }
          DeleteDC(CompatibleDC);
        }
        DeleteDC(hdcSrc);
      }
    }
    ReleaseDC(0, DC);
  }
  return CompatibleBitmap;
}

```

## disassembly

```asm
0x1803a81e8  push    rbx
0x1803a81ea  push    rbp
0x1803a81eb  push    rsi
0x1803a81ec  push    rdi
0x1803a81ed  push    r14
0x1803a81ef  push    r15
0x1803a81f1  sub     rsp, 88h
0x1803a81f8  mov     rax, cs:__security_cookie
0x1803a81ff  xor     rax, rsp
0x1803a8202  mov     [rsp+0B8h+var_48], rax
0x1803a8207  xor     ecx, ecx; hWnd
0x1803a8209  mov     r14, rdx
0x1803a820c  xor     ebp, ebp
0x1803a820e  call    cs:__imp_GetDC
0x1803a8215  nop     dword ptr [rax+rax+00h]
0x1803a821a  mov     rbx, rax
0x1803a821d  test    rax, rax
0x1803a8220  jz      loc_1803A8389
0x1803a8226  xorps   xmm0, xmm0
0x1803a8229  lea     r8, [rsp+0B8h+pv]; pv
0x1803a822e  lea     edx, [rbp+20h]; c
0x1803a8231  mov     rcx, r14; h
0x1803a8234  movups  [rsp+0B8h+pv], xmm0
0x1803a8239  movups  [rsp+0B8h+var_58], xmm0
0x1803a823e  call    cs:__imp_GetObjectW
0x1803a8245  nop     dword ptr [rax+rax+00h]
0x1803a824a  test    eax, eax
0x1803a824c  jz      loc_1803A8378
0x1803a8252  mov     rcx, rbx; hdc
0x1803a8255  call    cs:__imp_CreateCompatibleDC
0x1803a825c  nop     dword ptr [rax+rax+00h]
0x1803a8261  mov     rdi, rax
0x1803a8264  test    rax, rax
0x1803a8267  jz      loc_1803A8378
0x1803a826d  mov     rcx, rbx; hdc
0x1803a8270  call    cs:__imp_CreateCompatibleDC
0x1803a8277  nop     dword ptr [rax+rax+00h]
0x1803a827c  mov     rsi, rax
0x1803a827f  test    rax, rax
0x1803a8282  jz      loc_1803A8369
0x1803a8288  mov     r8d, dword ptr [rsp+0B8h+pv+8]; cy
0x1803a828d  mov     rcx, rbx; hdc
0x1803a8290  mov     edx, dword ptr [rsp+0B8h+pv+4]; cx
0x1803a8294  call    cs:__imp_CreateCompatibleBitmap
0x1803a829b  nop     dword ptr [rax+rax+00h]
0x1803a82a0  mov     rbp, rax
0x1803a82a3  test    rax, rax
0x1803a82a6  jz      loc_1803A835A
0x1803a82ac  mov     rdx, r14; h
0x1803a82af  mov     rcx, rdi; hdc
0x1803a82b2  call    cs:__imp_SelectObject
0x1803a82b9  nop     dword ptr [rax+rax+00h]
0x1803a82be  mov     r14, rax
0x1803a82c1  test    rax, rax
0x1803a82c4  jz      loc_1803A835A
0x1803a82ca  mov     rdx, rbp; h
0x1803a82cd  mov     rcx, rsi; hdc
0x1803a82d0  call    cs:__imp_SelectObject
0x1803a82d7  nop     dword ptr [rax+rax+00h]
0x1803a82dc  mov     r15, rax
0x1803a82df  test    rax, rax
0x1803a82e2  jz      short loc_1803A8348
0x1803a82e4  mov     edx, 1; l
0x1803a82e9  mov     rcx, rsi; hdc
0x1803a82ec  call    cs:__imp_SetLayout
0x1803a82f3  nop     dword ptr [rax+rax+00h]
0x1803a82f8  mov     ecx, dword ptr [rsp+0B8h+pv+8]
0x1803a82fc  xor     r8d, r8d; y
0x1803a82ff  mov     r9d, dword ptr [rsp+0B8h+pv+4]; cx
0x1803a8304  xor     edx, edx; x
0x1803a8306  mov     [rsp+0B8h+rop], 0CC0020h; rop
0x1803a830e  mov     [rsp+0B8h+y1], 0; y1
0x1803a8316  mov     [rsp+0B8h+x1], 0; x1
0x1803a831e  mov     [rsp+0B8h+hdcSrc], rdi; hdcSrc
0x1803a8323  mov     [rsp+0B8h+cy], ecx; cy
0x1803a8327  mov     rcx, rsi; hdc
0x1803a832a  call    cs:__imp_BitBlt
0x1803a8331  nop     dword ptr [rax+rax+00h]
0x1803a8336  mov     rdx, r15; h
0x1803a8339  mov     rcx, rsi; hdc
0x1803a833c  call    cs:__imp_SelectObject
0x1803a8343  nop     dword ptr [rax+rax+00h]
0x1803a8348  mov     rdx, r14; h
0x1803a834b  mov     rcx, rdi; hdc
0x1803a834e  call    cs:__imp_SelectObject
0x1803a8355  nop     dword ptr [rax+rax+00h]
0x1803a835a  mov     rcx, rsi; hdc
0x1803a835d  call    cs:__imp_DeleteDC
0x1803a8364  nop     dword ptr [rax+rax+00h]
0x1803a8369  mov     rcx, rdi; hdc
0x1803a836c  call    cs:__imp_DeleteDC
0x1803a8373  nop     dword ptr [rax+rax+00h]
0x1803a8378  mov     rdx, rbx; hDC
0x1803a837b  xor     ecx, ecx; hWnd
0x1803a837d  call    cs:__imp_ReleaseDC
0x1803a8384  nop     dword ptr [rax+rax+00h]
0x1803a8389  mov     rax, rbp
0x1803a838c  mov     rcx, [rsp+0B8h+var_48]
0x1803a8391  xor     rcx, rsp; StackCookie
0x1803a8394  call    __security_check_cookie
0x1803a8399  add     rsp, 88h
0x1803a83a0  pop     r15
0x1803a83a2  pop     r14
0x1803a83a4  pop     rdi
0x1803a83a5  pop     rsi
0x1803a83a6  pop     rbp
0x1803a83a7  pop     rbx
0x1803a83a8  retn
```
