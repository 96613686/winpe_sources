# CStackComposer::GetFinalBitmap(HBITMAP__ * *)

- ea: `0x180510e30`
- end: `0x1805111c6`
- name: `?GetFinalBitmap@CStackComposer@@UEAAJPEAPEAUHBITMAP__@@@Z`
- size: `918`
- prototype: `__int64 __fastcall(CStackComposer *__hidden this, HBITMAP *)`
- caller_count: `0`
- callee_count: `12`
- tags: `broker_com_uri`

## callees

- `0x180028818`
- `0x1800a01d4`
- `0x1800dbe2c`
- `0x180131f28`
- `0x180178a4c`
- `0x180249490`
- `0x18040dd38`
- `0x180510cd8`
- `0x180510e30`
- `0x180511320`
- `0x1805114e0`
- `0x180511b18`

## import_xrefs

- `GDI32!DeleteObject` at `0x1805110da`
- `GDI32!DeleteObject` at `0x180511154`
- `GDI32!DeleteObject` at `0x1805110da`
- `GDI32!DeleteObject` at `0x180511154`
- `GDI32!CreateCompatibleDC` at `0x180510e90`
- `GDI32!CreateCompatibleDC` at `0x180511033`
- `GDI32!CreateCompatibleDC` at `0x180510e90`
- `GDI32!CreateCompatibleDC` at `0x180511033`
- `GDI32!SelectObject` at `0x180510eee`
- `GDI32!SelectObject` at `0x18051113c`
- `GDI32!SelectObject` at `0x180510eee`
- `GDI32!SelectObject` at `0x18051113c`
- `GDI32!DeleteDC` at `0x1805110bf`
- `GDI32!DeleteDC` at `0x18051116c`
- `GDI32!DeleteDC` at `0x1805110bf`
- `GDI32!DeleteDC` at `0x18051116c`
- `api-ms-win-shlwapi-ie-l1-1-0!__imp_SHFillRectClr` at `0x180510f19`
- `api-ms-win-shlwapi-ie-l1-1-0!__imp_SHFillRectClr` at `0x180510f19`
- `gdiplus!GdipDeleteGraphics` at `0x180511109`
- `gdiplus!GdipDeleteGraphics` at `0x180511109`
- `gdiplus!GdipSetSmoothingMode` at `0x180510fa2`
- `gdiplus!GdipSetSmoothingMode` at `0x180510fa2`
- `gdiplus!GdipDeletePen` at `0x1805110ea`
- `gdiplus!GdipDeletePen` at `0x1805110fa`
- `gdiplus!GdipDeletePen` at `0x1805110ea`
- `gdiplus!GdipDeletePen` at `0x1805110fa`

## pseudocode

```c
__int64 __fastcall CStackComposer::GetFinalBitmap(WCHAR *this, HBITMAP *a2, __int64 a3)
{
  HBITMAP *v3; // r15
  HDC CompatibleDC; // rsi
  __int64 v6; // r8
  __int64 v7; // rcx
  signed int v8; // ebx
  HBITMAP v9; // r13
  HGDIOBJ v10; // rax
  int v11; // eax
  int v12; // r14d
  __int64 v13; // r15
  __int64 v14; // r12
  int v15; // eax
  int v16; // ecx
  HDC v17; // r8
  HBITMAP v18; // r12
  HBITMAP v19; // rdx
  int v20; // eax
  struct tagSIZE v22; // [rsp+40h] [rbp-59h] BYREF
  struct tagSIZE v23; // [rsp+48h] [rbp-51h] BYREF
  HGDIOBJ h; // [rsp+50h] [rbp-49h] BYREF
  HBITMAP *v25; // [rsp+58h] [rbp-41h]
  __int64 v26; // [rsp+60h] [rbp-39h] BYREF
  int v27; // [rsp+68h] [rbp-31h]
  HGDIOBJ v28; // [rsp+70h] [rbp-29h]
  _BYTE v29[8]; // [rsp+78h] [rbp-21h] BYREF
  _QWORD v30[2]; // [rsp+80h] [rbp-19h] BYREF
  _QWORD v31[2]; // [rsp+90h] [rbp-9h] BYREF
  _QWORD v32[2]; // [rsp+A0h] [rbp+7h] BYREF

  v3 = a2;
  v25 = a2;
  if ( (Microsoft_Windows_Shell_CoreEnableBits & 1) != 0 )
    McGenEventWrite_EventWriteTransfer(this, &DataLayer_StackThumbnails_Rendering_Start, a3, 1, v32);
  *v3 = 0;
  CompatibleDC = CreateCompatibleDC(0);
  v7 = -(__int64)CompatibleDC;
  v8 = CompatibleDC == 0 ? 0x80004005 : 0;
  if ( CompatibleDC )
  {
    h = 0;
    v23.cx = 256;
    v23.cy = 256;
    v8 = Create32BitHBITMAP(CompatibleDC, &v23, 0, (HBITMAP *)&h);
    if ( v8 >= 0 )
    {
      v9 = (HBITMAP)h;
      v10 = SelectObject(CompatibleDC, h);
      v31[1] = v23;
      v28 = v10;
      v31[0] = 0;
      SHFillRectClr(CompatibleDC, v31, 0xFFFFFFFFLL);
      v8 = -2147024809;
      CGraphicsInit::CGraphicsInit((CGraphicsInit *)v29);
      v11 = CStackComposer::_Sort((CStackComposer *)this);
      v12 = v11;
      if ( v11 >= 0 )
      {
        v13 = v11;
        if ( !*((_DWORD *)this + 26) && *(_DWORD *)&this[12 * v11 + 8]
          || (v8 = RenderIcon((SHSTOCKICONID)*(_DWORD *)&this[2 * v11 + 42], this + 170, CompatibleDC, v23), v8 >= 0) )
        {
          Gdiplus::Graphics::Graphics((Gdiplus::Graphics *)&v26, CompatibleDC);
          Gdiplus::Graphics::SetInterpolationMode(&v26, 6);
          v14 = v26;
          v15 = GdipSetSmoothingMode(v26, 4);
          v16 = v27;
          h = 0;
          if ( v15 )
            v16 = v15;
          v27 = v16;
          v22.cx = 256;
          v22.cy = 256;
          v8 = Create32BitHBITMAP(CompatibleDC, &v22, 0, (HBITMAP *)&h);
          if ( v8 >= 0 )
          {
            v22.cx = *((_DWORD *)this + 24) | 0xFF000000;
            Gdiplus::Pen::Pen(
              (Gdiplus::Pen *)v32,
              (const struct Gdiplus::Color *)&v22,
              (float)(*((_DWORD *)this + 25) >> 1));
            v22.cx = *((_DWORD *)this + 24) | 0x80000000;
            Gdiplus::Pen::Pen((Gdiplus::Pen *)v30, (const struct Gdiplus::Color *)&v22, (float)*((int *)this + 25));
            v22 = (struct tagSIZE)CreateCompatibleDC(CompatibleDC);
            v17 = (HDC)v22;
            if ( v22 )
            {
              v18 = (HBITMAP)h;
              v8 = 0;
              do
              {
                if ( v12 < 0 )
                  break;
                if ( *(_DWORD *)&this[12 * v12 + 8] )
                {
                  v19 = (HBITMAP)*((_QWORD *)this + 14);
                  if ( v19 )
                    continue;
                }
                v19 = *(HBITMAP *)&this[12 * v12 + 4];
                v20 = RenderLayer(
                        (struct MATRIXDATA *)&this[36 * v13 + 62 + 12 * v12],
                        v19,
                        (struct Gdiplus::Graphics *)&v26,
                        (struct Gdiplus::Pen *)v32,
                        (struct Gdiplus::Pen *)v30,
                        v17,
                        v18);
                v17 = (HDC)v22;
                --v12;
                v8 = v20;
              }
              while ( v20 >= 0 );
              DeleteDC(v17);
              v14 = v26;
            }
            else
            {
              v8 = -2147467259;
            }
            DeleteObject(h);
            GdipDeletePen(v30[0]);
            GdipDeletePen(v32[0]);
          }
          GdipDeleteGraphics(v14);
          if ( v8 >= 0 )
            v8 = RenderIcon((SHSTOCKICONID)*((_DWORD *)this + 20), this + 430, CompatibleDC, v23);
        }
        v3 = v25;
      }
      SelectObject(CompatibleDC, v28);
      if ( v8 < 0 )
        DeleteObject(v9);
      else
        *v3 = v9;
      CGraphicsInit::~CGraphicsInit((CGraphicsInit *)v29);
    }
    DeleteDC(CompatibleDC);
  }
  if ( (Microsoft_Windows_Shell_CoreEnableBits & 1) != 0 )
    McGenEventWrite_EventWriteTransfer(v7, &DataLayer_StackThumbnails_Rendering_Stop, v6, 1, v32);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180510e30  mov     [rsp-8+arg_10], rbx
0x180510e35  push    rbp
0x180510e36  push    rsi
0x180510e37  push    rdi
0x180510e38  push    r12
0x180510e3a  push    r13
0x180510e3c  push    r14
0x180510e3e  push    r15
0x180510e40  lea     rbp, [rsp-27h]
0x180510e45  sub     rsp, 0C0h
0x180510e4c  mov     rax, cs:__security_cookie
0x180510e53  xor     rax, rsp
0x180510e56  mov     [rbp+57h+var_40], rax
0x180510e5a  test    byte ptr cs:Microsoft_Windows_Shell_CoreEnableBits, 1
0x180510e61  mov     r15, rdx
0x180510e64  mov     [rbp+57h+var_98], rdx
0x180510e68  mov     rdi, rcx
0x180510e6b  jz      short loc_180510E88
0x180510e6d  lea     rax, [rbp+57h+var_50]
0x180510e71  mov     r9d, 1
0x180510e77  lea     rdx, DataLayer_StackThumbnails_Rendering_Start
0x180510e7e  mov     [rsp+0F0h+var_D0], rax
0x180510e83  call    McGenEventWrite_EventWriteTransfer
0x180510e88  xor     r12d, r12d
0x180510e8b  xor     ecx, ecx; hdc
0x180510e8d  mov     [r15], r12
0x180510e90  call    cs:__imp_CreateCompatibleDC
0x180510e97  nop     dword ptr [rax+rax+00h]
0x180510e9c  mov     rcx, rax
0x180510e9f  mov     rsi, rax
0x180510ea2  neg     rcx
0x180510ea5  sbb     ebx, ebx
0x180510ea7  not     ebx
0x180510ea9  and     ebx, 80004005h
0x180510eaf  test    rax, rax
0x180510eb2  jz      loc_180511178
0x180510eb8  mov     eax, 100h
0x180510ebd  mov     [rbp+57h+h], r12
0x180510ec1  lea     r9, [rbp+57h+h]; HBITMAP *
0x180510ec5  mov     [rbp+57h+var_A8.cx], eax
0x180510ec8  xor     r8d, r8d; void **
0x180510ecb  mov     [rbp+57h+var_A8.cy], eax
0x180510ece  lea     rdx, [rbp+57h+var_A8]; struct tagSIZE *
0x180510ed2  mov     rcx, rsi; HDC
0x180510ed5  call    ?Create32BitHBITMAP@@YAJPEAUHDC__@@PEBUtagSIZE@@PEAPEAXPEAPEAUHBITMAP__@@@Z; Create32BitHBITMAP(HDC__ *,tagSIZE const *,void * *,HBITMAP__ * *)
0x180510eda  mov     ebx, eax
0x180510edc  test    eax, eax
0x180510ede  js      loc_180511169
0x180510ee4  mov     r13, [rbp+57h+h]
0x180510ee8  mov     rcx, rsi; hdc
0x180510eeb  mov     rdx, r13; h
0x180510eee  call    cs:__imp_SelectObject
0x180510ef5  nop     dword ptr [rax+rax+00h]
0x180510efa  mov     ecx, [rbp+57h+var_A8.cx]
0x180510efd  lea     rdx, [rbp+57h+var_60]
0x180510f01  mov     [rbp+57h+var_58], ecx
0x180510f04  or      r8d, 0FFFFFFFFh
0x180510f08  mov     ecx, [rbp+57h+var_A8.cy]
0x180510f0b  mov     [rbp+57h+var_54], ecx
0x180510f0e  mov     rcx, rsi
0x180510f11  mov     [rbp+57h+var_80], rax
0x180510f15  mov     [rbp+57h+var_60], r12
0x180510f19  call    cs:__imp_SHFillRectClr
0x180510f20  nop     dword ptr [rax+rax+00h]
0x180510f25  lea     rcx, [rbp+57h+var_78]; this
0x180510f29  mov     ebx, 80070057h
0x180510f2e  call    ??0CGraphicsInit@@QEAA@XZ; CGraphicsInit::CGraphicsInit(void)
0x180510f33  mov     rcx, rdi; this
0x180510f36  call    ?_Sort@CStackComposer@@AEAAHXZ; CStackComposer::_Sort(void)
0x180510f3b  movsxd  r14, eax
0x180510f3e  test    eax, eax
0x180510f40  js      loc_180511135
0x180510f46  mov     r15, r14
0x180510f49  cmp     [rdi+68h], r12d
0x180510f4d  jnz     short loc_180510F5A
0x180510f4f  lea     rcx, [r14+r14*2]
0x180510f53  cmp     [rdi+rcx*8+10h], r12d
0x180510f58  jnz     short loc_180510F7C
0x180510f5a  mov     r9, qword ptr [rbp+57h+var_A8.cx]; struct tagSIZE
0x180510f5e  lea     rdx, [rdi+154h]; pszPath
0x180510f65  mov     ecx, [rdi+r14*4+54h]; siid
0x180510f6a  mov     r8, rsi; HDC
0x180510f6d  call    ?RenderIcon@@YAJW4SHSTOCKICONID@@PEBGPEAUHDC__@@UtagSIZE@@@Z; RenderIcon(SHSTOCKICONID,ushort const *,HDC__ *,tagSIZE)
0x180510f72  mov     ebx, eax
0x180510f74  test    eax, eax
0x180510f76  js      loc_180511131
0x180510f7c  mov     rdx, rsi; HDC
0x180510f7f  lea     rcx, [rbp+57h+var_90]; this
0x180510f83  call    ??0Graphics@Gdiplus@@QEAA@PEAUHDC__@@@Z; Gdiplus::Graphics::Graphics(HDC__ *)
0x180510f88  mov     edx, 6
0x180510f8d  lea     rcx, [rbp+57h+var_90]
0x180510f91  call    ?SetInterpolationMode@Graphics@Gdiplus@@QEAA?AW4Status@2@W4InterpolationMode@2@@Z; Gdiplus::Graphics::SetInterpolationMode(Gdiplus::InterpolationMode)
0x180510f96  mov     r12, [rbp+57h+var_90]
0x180510f9a  mov     edx, 4
0x180510f9f  mov     rcx, r12
0x180510fa2  call    cs:__imp_GdipSetSmoothingMode
0x180510fa9  nop     dword ptr [rax+rax+00h]
0x180510fae  mov     ecx, [rbp+57h+var_88]
0x180510fb1  lea     r9, [rbp+57h+h]; HBITMAP *
0x180510fb5  test    eax, eax
0x180510fb7  mov     [rbp+57h+h], 0
0x180510fbf  lea     rdx, [rbp+57h+var_B0]; struct tagSIZE *
0x180510fc3  cmovnz  ecx, eax
0x180510fc6  mov     eax, 100h
0x180510fcb  mov     [rbp+57h+var_88], ecx
0x180510fce  xor     r8d, r8d; void **
0x180510fd1  mov     rcx, rsi; HDC
0x180510fd4  mov     [rbp+57h+var_B0.cx], eax
0x180510fd7  mov     [rbp+57h+var_B0.cy], eax
0x180510fda  call    ?Create32BitHBITMAP@@YAJPEAUHDC__@@PEBUtagSIZE@@PEAPEAXPEAPEAUHBITMAP__@@@Z; Create32BitHBITMAP(HDC__ *,tagSIZE const *,void * *,HBITMAP__ * *)
0x180510fdf  mov     ebx, eax
0x180510fe1  test    eax, eax
0x180510fe3  js      loc_180511106
0x180510fe9  mov     eax, [rdi+60h]
0x180510fec  lea     rdx, [rbp+57h+var_B0]; struct Gdiplus::Color *
0x180510ff0  or      eax, 0FF000000h
0x180510ff5  lea     rcx, [rbp+57h+var_50]; this
0x180510ff9  mov     [rbp+57h+var_B0.cx], eax
0x180510ffc  xorps   xmm2, xmm2
0x180510fff  mov     eax, [rdi+64h]
0x180511002  shr     eax, 1
0x180511004  cvtsi2ss xmm2, rax; float
0x180511009  call    ??0Pen@Gdiplus@@QEAA@AEBVColor@1@M@Z; Gdiplus::Pen::Pen(Gdiplus::Color const &,float)
0x18051100e  mov     eax, [rdi+60h]
0x180511011  lea     rdx, [rbp+57h+var_B0]; struct Gdiplus::Color *
0x180511015  bts     eax, 1Fh
0x180511019  lea     rcx, [rbp+57h+var_70]; this
0x18051101d  mov     [rbp+57h+var_B0.cx], eax
0x180511020  xorps   xmm2, xmm2
0x180511023  mov     eax, [rdi+64h]
0x180511026  cvtsi2ss xmm2, rax; float
0x18051102b  call    ??0Pen@Gdiplus@@QEAA@AEBVColor@1@M@Z; Gdiplus::Pen::Pen(Gdiplus::Color const &,float)
0x180511030  mov     rcx, rsi; hdc
0x180511033  call    cs:__imp_CreateCompatibleDC
0x18051103a  nop     dword ptr [rax+rax+00h]
0x18051103f  mov     qword ptr [rbp+57h+var_B0.cx], rax
0x180511043  mov     r8, rax
0x180511046  test    rax, rax
0x180511049  jz      loc_1805110D1
0x18051104f  mov     r12, [rbp+57h+h]
0x180511053  xor     ebx, ebx
0x180511055  test    r14d, r14d
0x180511058  js      short loc_1805110BC
0x18051105a  movsxd  rcx, r14d
0x18051105d  lea     rax, [rcx+rcx*2]
0x180511061  cmp     dword ptr [rdi+rax*8+10h], 0
0x180511066  jz      short loc_180511071
0x180511068  mov     rdx, [rdi+70h]
0x18051106c  test    rdx, rdx
0x18051106f  jnz     short loc_180511076
0x180511071  mov     rdx, [rdi+rax*8+8]; HBITMAP
0x180511076  lea     eax, [r14+r14*2]
0x18051107a  mov     [rsp+0F0h+var_C0], r12; HBITMAP
0x18051107f  movsxd  rcx, eax
0x180511082  lea     r9, [rbp+57h+var_50]; struct Gdiplus::Pen *
0x180511086  mov     [rsp+0F0h+var_C8], r8; HDC
0x18051108b  lea     rax, [r15+r15*8]
0x18051108f  add     rcx, rax
0x180511092  lea     r8, [rbp+57h+var_90]; struct Gdiplus::Graphics *
0x180511096  lea     rax, [rbp+57h+var_70]
0x18051109a  mov     [rsp+0F0h+var_D0], rax; struct Gdiplus::Pen *
0x18051109f  lea     rcx, ds:7Ch[rcx*8]
0x1805110a7  add     rcx, rdi; struct MATRIXDATA *
0x1805110aa  call    ?RenderLayer@@YAJPEAUMATRIXDATA@@PEAUHBITMAP__@@PEAVGraphics@Gdiplus@@PEAVPen@4@3PEAUHDC__@@1@Z; RenderLayer(MATRIXDATA *,HBITMAP__ *,Gdiplus::Graphics *,Gdiplus::Pen *,Gdiplus::Pen *,HDC__ *,HBITMAP__ *)
0x1805110af  mov     r8, qword ptr [rbp+57h+var_B0.cx]
0x1805110b3  dec     r14d
0x1805110b6  mov     ebx, eax
0x1805110b8  test    eax, eax
0x1805110ba  jns     short loc_180511055
0x1805110bc  mov     rcx, r8; hdc
0x1805110bf  call    cs:__imp_DeleteDC
0x1805110c6  nop     dword ptr [rax+rax+00h]
0x1805110cb  mov     r12, [rbp+57h+var_90]
0x1805110cf  jmp     short loc_1805110D6
0x1805110d1  mov     ebx, 80004005h
0x1805110d6  mov     rcx, [rbp+57h+h]; ho
0x1805110da  call    cs:__imp_DeleteObject
0x1805110e1  nop     dword ptr [rax+rax+00h]
0x1805110e6  mov     rcx, [rbp+57h+var_70]
0x1805110ea  call    cs:__imp_GdipDeletePen
0x1805110f1  nop     dword ptr [rax+rax+00h]
0x1805110f6  mov     rcx, [rbp+57h+var_50]
0x1805110fa  call    cs:__imp_GdipDeletePen
0x180511101  nop     dword ptr [rax+rax+00h]
0x180511106  mov     rcx, r12
0x180511109  call    cs:__imp_GdipDeleteGraphics
0x180511110  nop     dword ptr [rax+rax+00h]
0x180511115  test    ebx, ebx
0x180511117  js      short loc_180511131
0x180511119  mov     r9, qword ptr [rbp+57h+var_A8.cx]; struct tagSIZE
0x18051111d  lea     rdx, [rdi+35Ch]; pszPath
0x180511124  mov     ecx, [rdi+50h]; siid
0x180511127  mov     r8, rsi; HDC
0x18051112a  call    ?RenderIcon@@YAJW4SHSTOCKICONID@@PEBGPEAUHDC__@@UtagSIZE@@@Z; RenderIcon(SHSTOCKICONID,ushort const *,HDC__ *,tagSIZE)
0x18051112f  mov     ebx, eax
0x180511131  mov     r15, [rbp+57h+var_98]
0x180511135  mov     rdx, [rbp+57h+var_80]; h
0x180511139  mov     rcx, rsi; hdc
0x18051113c  call    cs:__imp_SelectObject
0x180511143  nop     dword ptr [rax+rax+00h]
0x180511148  test    ebx, ebx
0x18051114a  js      short loc_180511151
0x18051114c  mov     [r15], r13
0x18051114f  jmp     short loc_180511160
0x180511151  mov     rcx, r13; ho
0x180511154  call    cs:__imp_DeleteObject
0x18051115b  nop     dword ptr [rax+rax+00h]
0x180511160  lea     rcx, [rbp+57h+var_78]; this
0x180511164  call    ??1CGraphicsInit@@QEAA@XZ; CGraphicsInit::~CGraphicsInit(void)
0x180511169  mov     rcx, rsi; hdc
0x18051116c  call    cs:__imp_DeleteDC
0x180511173  nop     dword ptr [rax+rax+00h]
0x180511178  test    byte ptr cs:Microsoft_Windows_Shell_CoreEnableBits, 1
0x18051117f  jz      short loc_18051119C
0x180511181  lea     rax, [rbp+57h+var_50]
0x180511185  mov     r9d, 1
0x18051118b  lea     rdx, DataLayer_StackThumbnails_Rendering_Stop
0x180511192  mov     [rsp+0F0h+var_D0], rax
0x180511197  call    McGenEventWrite_EventWriteTransfer
0x18051119c  mov     eax, ebx
0x18051119e  mov     rcx, [rbp+57h+var_40]
0x1805111a2  xor     rcx, rsp; StackCookie
0x1805111a5  call    __security_check_cookie
0x1805111aa  mov     rbx, [rsp+0F0h+arg_10]
0x1805111b2  add     rsp, 0C0h
0x1805111b9  pop     r15
0x1805111bb  pop     r14
0x1805111bd  pop     r13
0x1805111bf  pop     r12
0x1805111c1  pop     rdi
0x1805111c2  pop     rsi
0x1805111c3  pop     rbp
0x1805111c4  retn
```
