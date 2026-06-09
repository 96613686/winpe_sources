# HBITMAPFromHICON(HICON__ *,HBITMAP__ * *)

- ea: `0x180004da4`
- end: `0x180004f6f`
- name: `?HBITMAPFromHICON@@YAJPEAUHICON__@@PEAPEAUHBITMAP__@@@Z`
- size: `459`
- prototype: `__int64 __fastcall(HICON, HBITMAP *)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x18000449c`
- `0x180005bbc`
- `0x180010bec`

## callees

- `0x180004da4`
- `0x18001e010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180004f45`
- `KERNEL32!GetLastError` at `0x180004f45`
- `GDI32!DeleteObject` at `0x180004df3`
- `GDI32!DeleteObject` at `0x180004e31`
- `GDI32!DeleteObject` at `0x180004df3`
- `GDI32!DeleteObject` at `0x180004e31`
- `GDI32!GetObjectW` at `0x180004e13`
- `GDI32!GetObjectW` at `0x180004e13`
- `gdiplus!GdiplusStartup` at `0x180004e61`
- `gdiplus!GdiplusStartup` at `0x180004e61`
- `gdiplus!GdipAlloc` at `0x180004e72`
- `gdiplus!GdipAlloc` at `0x180004e72`
- `gdiplus!GdipCreateBitmapFromHICON` at `0x180004e9d`
- `gdiplus!GdipCreateBitmapFromHICON` at `0x180004e9d`
- `gdiplus!GdiplusShutdown` at `0x180004f36`
- `gdiplus!GdiplusShutdown` at `0x180004f36`
- `gdiplus!GdipCreateHBITMAPFromBitmap` at `0x180004efb`
- `gdiplus!GdipCreateHBITMAPFromBitmap` at `0x180004efb`
- `gdiplus!GdipGetImageHeight` at `0x180004ede`
- `gdiplus!GdipGetImageHeight` at `0x180004ede`
- `gdiplus!GdipGetImageWidth` at `0x180004ebc`
- `gdiplus!GdipGetImageWidth` at `0x180004ebc`
- `USER32!GetIconInfo` at `0x180004de1`
- `USER32!GetIconInfo` at `0x180004de1`

## pseudocode

```c
__int64 __fastcall HBITMAPFromHICON(HICON a1, HBITMAP *a2)
{
  unsigned int v4; // ebx
  __int64 v5; // rdi
  __int64 v6; // rcx
  int ImageWidth; // eax
  __int64 v8; // rcx
  int ImageHeight; // eax
  int HBITMAPFromBitmap; // eax
  signed int LastError; // eax
  int v13; // [rsp+20h] [rbp-60h] BYREF
  __int64 v14; // [rsp+28h] [rbp-58h]
  __int64 v15; // [rsp+30h] [rbp-50h]
  ICONINFO piconinfo; // [rsp+38h] [rbp-48h] BYREF
  __int128 pv; // [rsp+58h] [rbp-28h] BYREF
  __int128 v18; // [rsp+68h] [rbp-18h]
  __int64 v19; // [rsp+A8h] [rbp+28h] BYREF
  __int64 v20; // [rsp+B0h] [rbp+30h] BYREF

  if ( !a2 )
    return (unsigned int)-2147467261;
  *a2 = 0;
  memset(&piconinfo, 0, sizeof(piconinfo));
  if ( GetIconInfo(a1, &piconinfo) )
  {
    DeleteObject(piconinfo.hbmMask);
    pv = 0;
    v18 = 0;
    GetObjectW(piconinfo.hbmColor, 32, &pv);
    if ( WORD1(v18) == 32 )
    {
      v4 = 0;
      *a2 = piconinfo.hbmColor;
      return v4;
    }
    DeleteObject(piconinfo.hbmColor);
    v20 = 0;
    v13 = 1;
    v14 = 0;
    v15 = 0;
    if ( (unsigned int)GdiplusStartup(&v20, &v13, 0) )
      return (unsigned int)-2147467259;
    v5 = GdipAlloc(24);
    if ( v5 )
    {
      v19 = 0;
      *(_QWORD *)v5 = &Gdiplus::Image::`vftable';
      *(_DWORD *)(v5 + 16) = GdipCreateBitmapFromHICON(a1, &v19);
      v6 = v19;
      *(_QWORD *)(v5 + 8) = v19;
      LODWORD(v19) = 0;
      ImageWidth = GdipGetImageWidth(v6, &v19);
      if ( ImageWidth )
        *(_DWORD *)(v5 + 16) = ImageWidth;
      if ( (_DWORD)v19 )
      {
        v8 = *(_QWORD *)(v5 + 8);
        LODWORD(v19) = 0;
        ImageHeight = GdipGetImageHeight(v8, &v19);
        if ( ImageHeight )
          *(_DWORD *)(v5 + 16) = ImageHeight;
        if ( (_DWORD)v19 )
        {
          HBITMAPFromBitmap = GdipCreateHBITMAPFromBitmap(*(_QWORD *)(v5 + 8), a2, 0);
          if ( HBITMAPFromBitmap )
          {
            *(_DWORD *)(v5 + 16) = HBITMAPFromBitmap;
            v4 = -2147467259;
          }
          else
          {
            v4 = 0;
          }
          goto LABEL_19;
        }
      }
    }
    else
    {
      v5 = 0;
    }
    v4 = -2147467259;
    if ( !v5 )
    {
LABEL_20:
      GdiplusShutdown(v20);
      return v4;
    }
LABEL_19:
    (**(void (__fastcall ***)(__int64, __int64))v5)(v5, 1);
    goto LABEL_20;
  }
  LastError = GetLastError();
  v4 = LastError;
  if ( LastError > 0 )
    return (unsigned __int16)LastError | 0x80070000;
  return v4;
}

```

## disassembly

```asm
0x180004da4  mov     [rsp-18h+arg_0], rbx
0x180004da9  push    rbp
0x180004daa  push    rsi
0x180004dab  push    rdi
0x180004dac  mov     rbp, rsp
0x180004daf  sub     rsp, 80h
0x180004db6  mov     rsi, rdx
0x180004db9  mov     rbx, rcx
0x180004dbc  test    rdx, rdx
0x180004dbf  jnz     short loc_180004DCB
0x180004dc1  mov     ebx, 80004003h
0x180004dc6  jmp     loc_180004F5A
0x180004dcb  xorps   xmm0, xmm0
0x180004dce  mov     qword ptr [rdx], 0
0x180004dd5  lea     rdx, [rbp+piconinfo]; piconinfo
0x180004dd9  movups  xmmword ptr [rbp+piconinfo.fIcon], xmm0
0x180004ddd  movups  xmmword ptr [rbp+piconinfo.hbmMask], xmm0
0x180004de1  call    cs:__imp_GetIconInfo
0x180004de7  test    eax, eax
0x180004de9  jz      loc_180004F45
0x180004def  mov     rcx, [rbp+piconinfo.hbmMask]; ho
0x180004df3  call    cs:__imp_DeleteObject
0x180004df9  mov     rcx, [rbp+piconinfo.hbmColor]; h
0x180004dfd  lea     r8, [rbp+pv]; pv
0x180004e01  xorps   xmm0, xmm0
0x180004e04  mov     edi, 20h ; ' '
0x180004e09  mov     edx, edi; c
0x180004e0b  movups  [rbp+pv], xmm0
0x180004e0f  movups  [rbp+var_18], xmm0
0x180004e13  call    cs:__imp_GetObjectW
0x180004e19  cmp     word ptr [rbp+var_18+2], di
0x180004e1d  jnz     short loc_180004E2D
0x180004e1f  mov     rax, [rbp+piconinfo.hbmColor]
0x180004e23  xor     ebx, ebx
0x180004e25  mov     [rsi], rax
0x180004e28  jmp     loc_180004F5A
0x180004e2d  mov     rcx, [rbp+piconinfo.hbmColor]; ho
0x180004e31  call    cs:__imp_DeleteObject
0x180004e37  xor     r8d, r8d
0x180004e3a  mov     [rbp+arg_10], 0
0x180004e42  lea     rdx, [rbp+var_60]
0x180004e46  mov     [rbp+var_60], 1
0x180004e4d  lea     rcx, [rbp+arg_10]
0x180004e51  mov     [rbp+var_58], 0
0x180004e59  mov     [rbp+var_50], 0
0x180004e61  call    cs:__imp_GdiplusStartup
0x180004e67  test    eax, eax
0x180004e69  jnz     loc_180004F3E
0x180004e6f  lea     ecx, [rax+18h]
0x180004e72  call    cs:__imp_GdipAlloc
0x180004e78  mov     rdi, rax
0x180004e7b  test    rax, rax
0x180004e7e  jz      loc_180004F13
0x180004e84  lea     rax, ??_7Image@Gdiplus@@6B@; const Gdiplus::Image::`vftable'
0x180004e8b  mov     [rbp+arg_8], 0
0x180004e93  lea     rdx, [rbp+arg_8]
0x180004e97  mov     [rdi], rax
0x180004e9a  mov     rcx, rbx
0x180004e9d  call    cs:__imp_GdipCreateBitmapFromHICON
0x180004ea3  mov     [rdi+10h], eax
0x180004ea6  lea     rdx, [rbp+arg_8]
0x180004eaa  mov     rax, [rbp+arg_8]
0x180004eae  mov     rcx, rax
0x180004eb1  mov     [rdi+8], rax
0x180004eb5  mov     dword ptr [rbp+arg_8], 0
0x180004ebc  call    cs:__imp_GdipGetImageWidth
0x180004ec2  test    eax, eax
0x180004ec4  jz      short loc_180004EC9
0x180004ec6  mov     [rdi+10h], eax
0x180004ec9  cmp     dword ptr [rbp+arg_8], 0
0x180004ecd  jbe     short loc_180004F15
0x180004ecf  mov     rcx, [rdi+8]
0x180004ed3  lea     rdx, [rbp+arg_8]
0x180004ed7  mov     dword ptr [rbp+arg_8], 0
0x180004ede  call    cs:__imp_GdipGetImageHeight
0x180004ee4  test    eax, eax
0x180004ee6  jz      short loc_180004EEB
0x180004ee8  mov     [rdi+10h], eax
0x180004eeb  cmp     dword ptr [rbp+arg_8], 0
0x180004eef  jbe     short loc_180004F15
0x180004ef1  mov     rcx, [rdi+8]
0x180004ef5  xor     r8d, r8d
0x180004ef8  mov     rdx, rsi
0x180004efb  call    cs:__imp_GdipCreateHBITMAPFromBitmap
0x180004f01  test    eax, eax
0x180004f03  jz      short loc_180004F0F
0x180004f05  mov     [rdi+10h], eax
0x180004f08  mov     ebx, 80004005h
0x180004f0d  jmp     short loc_180004F1F
0x180004f0f  xor     ebx, ebx
0x180004f11  jmp     short loc_180004F1F
0x180004f13  xor     edi, edi
0x180004f15  mov     ebx, 80004005h
0x180004f1a  test    rdi, rdi
0x180004f1d  jz      short loc_180004F32
0x180004f1f  mov     rax, [rdi]
0x180004f22  mov     edx, 1
0x180004f27  mov     rcx, rdi
0x180004f2a  mov     rax, [rax]
0x180004f2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004f32  mov     rcx, [rbp+arg_10]
0x180004f36  call    cs:__imp_GdiplusShutdown
0x180004f3c  jmp     short loc_180004F5A
0x180004f3e  mov     ebx, 80004005h
0x180004f43  jmp     short loc_180004F5A
0x180004f45  call    cs:__imp_GetLastError
0x180004f4b  mov     ebx, eax
0x180004f4d  test    eax, eax
0x180004f4f  jle     short loc_180004F5A
0x180004f51  movzx   ebx, ax
0x180004f54  or      ebx, 80070000h
0x180004f5a  mov     eax, ebx
0x180004f5c  mov     rbx, [rsp+80h+arg_0]
0x180004f64  add     rsp, 80h
0x180004f6b  pop     rdi
0x180004f6c  pop     rsi
0x180004f6d  pop     rbp
0x180004f6e  retn
```
