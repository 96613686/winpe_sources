# LoadMonitorBitmap(int)

- ea: `0x180048db4`
- end: `0x180049071`
- name: `?LoadMonitorBitmap@@YAPEAUHBITMAP__@@H@Z`
- size: `701`
- prototype: `HBITMAP __fastcall(int)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18003b780`
- `0x180047550`

## callees

- `0x180048c74`
- `0x180048db4`

## import_xrefs

- `GDI32!DeleteObject` at `0x18004904d`
- `GDI32!DeleteObject` at `0x18004904d`
- `GDI32!SetStretchBltMode` at `0x180048e9c`
- `GDI32!SetStretchBltMode` at `0x180048fb3`
- `GDI32!SetStretchBltMode` at `0x180048e9c`
- `GDI32!SetStretchBltMode` at `0x180048fb3`
- `GDI32!GetPixel` at `0x180048e66`
- `GDI32!GetPixel` at `0x180048e66`
- `GDI32!ExtFloodFill` at `0x180048e80`
- `GDI32!ExtFloodFill` at `0x180048e80`
- `GDI32!StretchBlt` at `0x180048eed`
- `GDI32!StretchBlt` at `0x180048ff6`
- `GDI32!StretchBlt` at `0x180048eed`
- `GDI32!StretchBlt` at `0x180048ff6`
- `GDI32!CreateCompatibleBitmap` at `0x180048f8e`
- `GDI32!CreateCompatibleBitmap` at `0x180048f8e`
- `GDI32!GetObjectW` at `0x180048e4f`
- `GDI32!GetObjectW` at `0x180048e4f`
- `GDI32!GetDeviceCaps` at `0x180048f1e`
- `GDI32!GetDeviceCaps` at `0x180048f31`
- `GDI32!GetDeviceCaps` at `0x180048f1e`
- `GDI32!GetDeviceCaps` at `0x180048f31`
- `GDI32!SelectObject` at `0x180048e14`
- `GDI32!SelectObject` at `0x180048e35`
- `GDI32!SelectObject` at `0x180048fa2`
- `GDI32!SelectObject` at `0x180049002`
- `GDI32!SelectObject` at `0x18004902f`
- `GDI32!SelectObject` at `0x18004903b`
- `GDI32!SelectObject` at `0x180048e14`
- `GDI32!SelectObject` at `0x180048e35`
- `GDI32!SelectObject` at `0x180048fa2`
- `GDI32!SelectObject` at `0x180049002`
- `GDI32!SelectObject` at `0x18004902f`
- `GDI32!SelectObject` at `0x18004903b`
- `GDI32!CreateCompatibleDC` at `0x180048dfc`
- `GDI32!CreateCompatibleDC` at `0x180048f00`
- `GDI32!CreateCompatibleDC` at `0x180048dfc`
- `GDI32!CreateCompatibleDC` at `0x180048f00`
- `GDI32!DeleteDC` at `0x18004901e`
- `GDI32!DeleteDC` at `0x180049044`
- `GDI32!DeleteDC` at `0x18004901e`
- `GDI32!DeleteDC` at `0x180049044`
- `USER32!GetSysColorBrush` at `0x180048e29`
- `USER32!GetSysColorBrush` at `0x180048e29`
- `USER32!ReleaseDC` at `0x180048ef8`
- `USER32!ReleaseDC` at `0x18004900d`
- `USER32!ReleaseDC` at `0x180048ef8`
- `USER32!ReleaseDC` at `0x18004900d`
- `USER32!GetDC` at `0x180048e8c`
- `USER32!GetDC` at `0x180048f42`
- `USER32!GetDC` at `0x180048e8c`
- `USER32!GetDC` at `0x180048f42`
- `USER32!GetSystemMetrics` at `0x180048ea5`
- `USER32!GetSystemMetrics` at `0x180048eaf`
- `USER32!GetSystemMetrics` at `0x180048ea5`
- `USER32!GetSystemMetrics` at `0x180048eaf`

## pseudocode

```c
HBITMAP __fastcall LoadMonitorBitmap(int a1)
{
  HBITMAP result; // rax
  HBITMAP v3; // rbp
  HBITMAP v4; // r14
  HDC CompatibleDC; // rax
  HDC v6; // rsi
  void *v7; // r13
  HBRUSH SysColorBrush; // rax
  int v9; // ebx
  COLORREF Pixel; // eax
  HDC hdcSrc; // rdi
  int hSrc; // ebx
  int wSrc; // eax
  HDC v14; // rax
  HDC v15; // rdi
  int DeviceCaps; // eax
  int v17; // ebx
  int v18; // eax
  int v19; // r12d
  HDC DC; // r15
  int v21; // r13d
  int v22; // r12d
  HBITMAP CompatibleBitmap; // rax
  HGDIOBJ v24; // rbx
  _OWORD pv[5]; // [rsp+60h] [rbp-58h] BYREF
  HGDIOBJ v26; // [rsp+C8h] [rbp+10h]
  HGDIOBJ h; // [rsp+D0h] [rbp+18h]

  memset(pv, 0, 32);
  result = LoadImageFromResourceID(g_hinst, (const unsigned __int16 *)0x258);
  v3 = result;
  if ( result )
  {
    v4 = 0;
    CompatibleDC = CreateCompatibleDC(0);
    v6 = CompatibleDC;
    if ( CompatibleDC )
    {
      v26 = SelectObject(CompatibleDC, v3);
      v7 = v26;
      SysColorBrush = GetSysColorBrush(15);
      h = SelectObject(v6, SysColorBrush);
      GetObjectW(v3, 32, pv);
      v9 = DWORD2(pv[0]) - 1;
      Pixel = GetPixel(v6, 0, DWORD2(pv[0]) - 1);
      ExtFloodFill(v6, 0, v9, Pixel, 1u);
      if ( a1 )
      {
        hdcSrc = GetDC(0);
        SetStretchBltMode(v6, 4);
        hSrc = GetSystemMetrics(1);
        wSrc = GetSystemMetrics(0);
        StretchBlt(v6, 16, 17, 152, 112, hdcSrc, 0, 0, wSrc, hSrc, 0xCC0020u);
        ReleaseDC(0, hdcSrc);
      }
      v14 = CreateCompatibleDC(0);
      v15 = v14;
      if ( v14 )
      {
        DeviceCaps = GetDeviceCaps(v14, 88);
        v17 = DWORD1(pv[0]) * DeviceCaps;
        v18 = GetDeviceCaps(v15, 88);
        v19 = DWORD2(pv[0]) * v18;
        DC = GetDC(0);
        if ( DC )
        {
          v21 = v17 / 96;
          v22 = v19 / 96;
          CompatibleBitmap = CreateCompatibleBitmap(DC, v17 / 96, v22);
          v4 = CompatibleBitmap;
          if ( CompatibleBitmap )
          {
            v24 = SelectObject(v15, CompatibleBitmap);
            SetStretchBltMode(v15, 4);
            StretchBlt(v15, 0, 0, v21, v22, v6, 0, 0, SDWORD1(pv[0]), SDWORD2(pv[0]), 0xCC0020u);
            SelectObject(v15, v24);
          }
          ReleaseDC(0, DC);
          v7 = v26;
        }
        DeleteDC(v15);
      }
      SelectObject(v6, h);
      SelectObject(v6, v7);
      DeleteDC(v6);
    }
    DeleteObject(v3);
    return v4;
  }
  return result;
}

```

## disassembly

```asm
0x180048db4  mov     [rsp+arg_0], rbx
0x180048db9  push    rbp
0x180048dba  push    rsi
0x180048dbb  push    rdi
0x180048dbc  push    r12
0x180048dbe  push    r13
0x180048dc0  push    r14
0x180048dc2  push    r15
0x180048dc4  sub     rsp, 80h
0x180048dcb  xorps   xmm0, xmm0
0x180048dce  mov     edi, ecx
0x180048dd0  mov     rcx, cs:g_hinst; HINSTANCE
0x180048dd7  mov     edx, 258h; unsigned __int16 *
0x180048ddc  movups  [rsp+0B8h+pv], xmm0
0x180048de1  movups  [rsp+0B8h+var_48], xmm0
0x180048de6  call    ?LoadImageFromResourceID@@YAPEAUHBITMAP__@@PEAUHINSTANCE__@@PEBG@Z; LoadImageFromResourceID(HINSTANCE__ *,ushort const *)
0x180048deb  mov     rbp, rax
0x180048dee  test    rax, rax
0x180048df1  jz      loc_180049056
0x180048df7  xor     ecx, ecx; hdc
0x180048df9  xor     r14d, r14d
0x180048dfc  call    cs:__imp_CreateCompatibleDC
0x180048e02  mov     rsi, rax
0x180048e05  test    rax, rax
0x180048e08  jz      loc_18004904A
0x180048e0e  mov     rdx, rbp; h
0x180048e11  mov     rcx, rax; hdc
0x180048e14  call    cs:__imp_SelectObject
0x180048e1a  lea     ecx, [r14+0Fh]; nIndex
0x180048e1e  mov     [rsp+0B8h+arg_8], rax
0x180048e26  mov     r13, rax
0x180048e29  call    cs:__imp_GetSysColorBrush
0x180048e2f  mov     rdx, rax; h
0x180048e32  mov     rcx, rsi; hdc
0x180048e35  call    cs:__imp_SelectObject
0x180048e3b  lea     r8, [rsp+0B8h+pv]; pv
0x180048e40  mov     rcx, rbp; h
0x180048e43  lea     edx, [r14+20h]; c
0x180048e47  mov     [rsp+0B8h+h], rax
0x180048e4f  call    cs:__imp_GetObjectW
0x180048e55  mov     r8d, dword ptr [rsp+0B8h+pv+8]
0x180048e5a  xor     edx, edx; x
0x180048e5c  mov     rcx, rsi; hdc
0x180048e5f  lea     ebx, [r8-1]
0x180048e63  dec     r8d; y
0x180048e66  call    cs:__imp_GetPixel
0x180048e6c  lea     r15d, [r14+1]
0x180048e70  mov     r8d, ebx; y
0x180048e73  mov     r9d, eax; color
0x180048e76  mov     [rsp+0B8h+type], r15d; type
0x180048e7b  xor     edx, edx; x
0x180048e7d  mov     rcx, rsi; hdc
0x180048e80  call    cs:__imp_ExtFloodFill
0x180048e86  test    edi, edi
0x180048e88  jz      short loc_180048EFE
0x180048e8a  xor     ecx, ecx; hWnd
0x180048e8c  call    cs:__imp_GetDC
0x180048e92  lea     edx, [r14+4]; mode
0x180048e96  mov     rcx, rsi; hdc
0x180048e99  mov     rdi, rax
0x180048e9c  call    cs:__imp_SetStretchBltMode
0x180048ea2  mov     ecx, r15d; nIndex
0x180048ea5  call    cs:__imp_GetSystemMetrics
0x180048eab  xor     ecx, ecx; nIndex
0x180048ead  mov     ebx, eax
0x180048eaf  call    cs:__imp_GetSystemMetrics
0x180048eb5  mov     [rsp+0B8h+rop], 0CC0020h; rop
0x180048ebd  lea     edx, [r14+10h]; xDest
0x180048ec1  mov     [rsp+0B8h+hSrc], ebx; hSrc
0x180048ec5  lea     r8d, [r14+11h]; yDest
0x180048ec9  mov     [rsp+0B8h+wSrc], eax; wSrc
0x180048ecd  mov     r9d, 98h; wDest
0x180048ed3  mov     [rsp+0B8h+ySrc], r14d; ySrc
0x180048ed8  mov     rcx, rsi; hdcDest
0x180048edb  mov     [rsp+0B8h+xSrc], r14d; xSrc
0x180048ee0  mov     [rsp+0B8h+hdcSrc], rdi; hdcSrc
0x180048ee5  mov     [rsp+0B8h+type], 70h ; 'p'; hDest
0x180048eed  call    cs:__imp_StretchBlt
0x180048ef3  mov     rdx, rdi; hDC
0x180048ef6  xor     ecx, ecx; hWnd
0x180048ef8  call    cs:__imp_ReleaseDC
0x180048efe  xor     ecx, ecx; hdc
0x180048f00  call    cs:__imp_CreateCompatibleDC
0x180048f06  mov     rdi, rax
0x180048f09  test    rax, rax
0x180048f0c  jz      loc_180049024
0x180048f12  mov     r15d, 58h ; 'X'
0x180048f18  mov     rcx, rax; hdc
0x180048f1b  mov     edx, r15d; index
0x180048f1e  call    cs:__imp_GetDeviceCaps
0x180048f24  mov     edx, r15d; index
0x180048f27  mov     rcx, rdi; hdc
0x180048f2a  mov     ebx, eax
0x180048f2c  imul    ebx, dword ptr [rsp+0B8h+pv+4]
0x180048f31  call    cs:__imp_GetDeviceCaps
0x180048f37  mov     r12d, eax
0x180048f3a  xor     ecx, ecx; hWnd
0x180048f3c  imul    r12d, dword ptr [rsp+0B8h+pv+8]
0x180048f42  call    cs:__imp_GetDC
0x180048f48  mov     r15, rax
0x180048f4b  test    rax, rax
0x180048f4e  jz      loc_18004901B
0x180048f54  mov     r8d, 2AAAAAABh
0x180048f5a  mov     eax, r8d
0x180048f5d  imul    ebx
0x180048f5f  mov     eax, r8d
0x180048f62  mov     r13d, edx
0x180048f65  imul    r12d
0x180048f68  sar     r13d, 4
0x180048f6c  mov     r12d, edx
0x180048f6f  mov     ecx, r13d
0x180048f72  shr     ecx, 1Fh
0x180048f75  add     r13d, ecx
0x180048f78  sar     r12d, 4
0x180048f7c  mov     eax, r12d
0x180048f7f  mov     edx, r13d; cx
0x180048f82  shr     eax, 1Fh
0x180048f85  mov     rcx, r15; hdc
0x180048f88  add     r12d, eax
0x180048f8b  mov     r8d, r12d; cy
0x180048f8e  call    cs:__imp_CreateCompatibleBitmap
0x180048f94  mov     r14, rax
0x180048f97  test    rax, rax
0x180048f9a  jz      short loc_180049008
0x180048f9c  mov     rdx, rax; h
0x180048f9f  mov     rcx, rdi; hdc
0x180048fa2  call    cs:__imp_SelectObject
0x180048fa8  mov     edx, 4; mode
0x180048fad  mov     rcx, rdi; hdc
0x180048fb0  mov     rbx, rax
0x180048fb3  call    cs:__imp_SetStretchBltMode
0x180048fb9  mov     ecx, dword ptr [rsp+0B8h+pv+8]
0x180048fbd  mov     r9d, r13d; wDest
0x180048fc0  mov     [rsp+0B8h+rop], 0CC0020h; rop
0x180048fc8  xor     r8d, r8d; yDest
0x180048fcb  mov     [rsp+0B8h+hSrc], ecx; hSrc
0x180048fcf  xor     edx, edx; xDest
0x180048fd1  mov     ecx, dword ptr [rsp+0B8h+pv+4]
0x180048fd5  mov     [rsp+0B8h+wSrc], ecx; wSrc
0x180048fd9  mov     rcx, rdi; hdcDest
0x180048fdc  mov     [rsp+0B8h+ySrc], 0; ySrc
0x180048fe4  mov     [rsp+0B8h+xSrc], 0; xSrc
0x180048fec  mov     [rsp+0B8h+hdcSrc], rsi; hdcSrc
0x180048ff1  mov     [rsp+0B8h+type], r12d; hDest
0x180048ff6  call    cs:__imp_StretchBlt
0x180048ffc  mov     rdx, rbx; h
0x180048fff  mov     rcx, rdi; hdc
0x180049002  call    cs:__imp_SelectObject
0x180049008  mov     rdx, r15; hDC
0x18004900b  xor     ecx, ecx; hWnd
0x18004900d  call    cs:__imp_ReleaseDC
0x180049013  mov     r13, [rsp+0B8h+arg_8]
0x18004901b  mov     rcx, rdi; hdc
0x18004901e  call    cs:__imp_DeleteDC
0x180049024  mov     rdx, [rsp+0B8h+h]; h
0x18004902c  mov     rcx, rsi; hdc
0x18004902f  call    cs:__imp_SelectObject
0x180049035  mov     rdx, r13; h
0x180049038  mov     rcx, rsi; hdc
0x18004903b  call    cs:__imp_SelectObject
0x180049041  mov     rcx, rsi; hdc
0x180049044  call    cs:__imp_DeleteDC
0x18004904a  mov     rcx, rbp; ho
0x18004904d  call    cs:__imp_DeleteObject
0x180049053  mov     rax, r14
0x180049056  mov     rbx, [rsp+0B8h+arg_0]
0x18004905e  add     rsp, 80h
0x180049065  pop     r15
0x180049067  pop     r14
0x180049069  pop     r13
0x18004906b  pop     r12
0x18004906d  pop     rdi
0x18004906e  pop     rsi
0x18004906f  pop     rbp
0x180049070  retn
```
