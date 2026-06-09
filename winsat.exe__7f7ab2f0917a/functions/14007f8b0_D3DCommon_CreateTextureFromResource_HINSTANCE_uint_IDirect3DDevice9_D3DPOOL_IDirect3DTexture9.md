# D3DCommon::CreateTextureFromResource(HINSTANCE__ *,uint,IDirect3DDevice9 *,_D3DPOOL,IDirect3DTexture9 * *)

- ea: `0x14007f8b0`
- end: `0x14007fa44`
- name: `?CreateTextureFromResource@D3DCommon@@YAJPEAUHINSTANCE__@@IPEAUIDirect3DDevice9@@W4_D3DPOOL@@PEAPEAUIDirect3DTexture9@@@Z`
- size: `404`
- prototype: `__int64 __usercall@<rax>(HINSTANCE this@<rcx>, HINSTANCE@<rdx>, unsigned int@<r8d>, struct IDirect3DDevice9 *@<r9>, enum _D3DPOOL, struct IDirect3DTexture9 **)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1400848f0`

## callees

- `0x14000398c`
- `0x14007f588`
- `0x14007f5ec`
- `0x14007f8b0`
- `0x14007fa4c`
- `0x14007fb50`
- `0x14011a010`

## import_xrefs

- `gdiplus!GdipDisposeImage` at `0x14007fa0b`
- `gdiplus!GdipDisposeImage` at `0x14007fa0b`
- `gdiplus!GdipCreateBitmapFromStream` at `0x14007f9a7`
- `gdiplus!GdipCreateBitmapFromStream` at `0x14007f9a7`
- `gdiplus!GdiplusShutdown` at `0x14007fa29`
- `gdiplus!GdiplusShutdown` at `0x14007fa29`
- `gdiplus!GdiplusStartup` at `0x14007f936`
- `gdiplus!GdiplusStartup` at `0x14007f936`

## string_xrefs

- `0x14007f9e0`: `D3DCommon::StreamWrapper::CreateStreamWrapper`
- `0x14007f8d7`: `D3DCommon::CreateTextureFromResource`

## pseudocode

```c
__int64 __fastcall D3DCommon::CreateTextureFromResource(
        HINSTANCE this,
        HINSTANCE a2,
        struct Gdiplus::GpBitmap *a3,
        struct IDirect3DDevice9 *a4,
        __int64 a5)
{
  D3DCommon::StreamWrapper *v8; // rbx
  struct IDirect3DTexture9 **v9; // rax
  D3DCommon::StreamWrapper *v10; // rax
  D3DCommon::StreamWrapper *v11; // rsi
  int TextureFromGDIBitmap; // edi
  unsigned __int16 v13; // dx
  struct IDirect3DDevice9 *v14; // r8
  struct IDirect3DTexture9 **v15[2]; // [rsp+20h] [rbp-30h] BYREF
  int v16; // [rsp+30h] [rbp-20h] BYREF
  __int64 v17; // [rsp+38h] [rbp-18h]
  __int64 v18; // [rsp+40h] [rbp-10h]
  D3DCommon *v19; // [rsp+80h] [rbp+30h] BYREF

  if ( !a3 )
  {
    D3DCommon::ERR((D3DCommon *)0x6A, (unsigned __int16)L"pDevice", L"D3DCommon::CreateTextureFromResource", a4);
    return 2147942487LL;
  }
  if ( !a5 )
  {
    D3DCommon::ERR((D3DCommon *)0x6A, (unsigned __int16)L"ppTex", L"D3DCommon::CreateTextureFromResource", a4);
    return 2147942487LL;
  }
  v16 = 1;
  v17 = 0;
  v18 = 0;
  v15[0] = 0;
  v8 = 0;
  v19 = 0;
  GdiplusStartup(v15, &v16, 0, a4);
  v9 = (struct IDirect3DTexture9 **)operator new(0x30u, (const struct std::nothrow_t *)std::nothrow);
  v15[1] = v9;
  if ( v9 && (v10 = D3DCommon::StreamWrapper::StreamWrapper((D3DCommon::StreamWrapper *)v9, this), (v11 = v10) != 0) )
  {
    TextureFromGDIBitmap = D3DCommon::StreamWrapper::Load(v10);
    if ( TextureFromGDIBitmap >= 0 )
    {
      (*(void (__fastcall **)(D3DCommon::StreamWrapper *))(*(_QWORD *)v11 + 8LL))(v11);
      TextureFromGDIBitmap = 0;
      v8 = v11;
    }
    (*(void (__fastcall **)(D3DCommon::StreamWrapper *))(*(_QWORD *)v11 + 16LL))(v11);
    if ( TextureFromGDIBitmap >= 0 )
    {
      if ( (unsigned int)GdipCreateBitmapFromStream(v8, &v19) || !v19 )
      {
        D3DCommon::ERR((D3DCommon *)0x8E, v13);
        TextureFromGDIBitmap = -2147467259;
      }
      else
      {
        TextureFromGDIBitmap = D3DCommon::CreateTextureFromGDIBitmap(v19, a3, v14, (enum _D3DPOOL)a5, v15[0]);
      }
      goto LABEL_17;
    }
  }
  else
  {
    D3DCommon::ERR((D3DCommon *)0x6D, (unsigned __int16)L"pStream", L"D3DCommon::StreamWrapper::CreateStreamWrapper");
    TextureFromGDIBitmap = -2147024882;
  }
  D3DCommon::ERR((D3DCommon *)0x9F, 0x2BDu);
LABEL_17:
  GdipDisposeImage(v19);
  if ( v8 )
    (*(void (__fastcall **)(D3DCommon::StreamWrapper *))(*(_QWORD *)v8 + 16LL))(v8);
  GdiplusShutdown(v15[0]);
  return (unsigned int)TextureFromGDIBitmap;
}

```

## disassembly

```asm
0x14007f8b0  mov     [rsp-18h+arg_0], rbx
0x14007f8b5  mov     [rsp-18h+arg_8], rsi
0x14007f8ba  push    rbp
0x14007f8bb  push    rdi
0x14007f8bc  push    r15
0x14007f8be  mov     rbp, rsp
0x14007f8c1  sub     rsp, 50h
0x14007f8c5  mov     r15, r8
0x14007f8c8  mov     rdi, rcx
0x14007f8cb  test    r8, r8
0x14007f8ce  jnz     short loc_14007F8F2
0x14007f8d0  lea     rdx, aPdevice; "pDevice"
0x14007f8d7  lea     r8, aD3dcommonCreat_0; "D3DCommon::CreateTextureFromResource"
0x14007f8de  mov     ecx, 6Ah ; 'j'; this
0x14007f8e3  call    ?ERR@D3DCommon@@YAXGZZ; D3DCommon::ERR(ushort,...)
0x14007f8e8  mov     eax, 80070057h
0x14007f8ed  jmp     loc_14007FA31
0x14007f8f2  cmp     [rbp+arg_20], 0
0x14007f8f7  jnz     short loc_14007F902
0x14007f8f9  lea     rdx, aPptex; "ppTex"
0x14007f900  jmp     short loc_14007F8D7
0x14007f902  xor     r8d, r8d
0x14007f905  mov     [rbp+var_20], 1
0x14007f90c  lea     rdx, [rbp+var_20]
0x14007f910  mov     [rbp+var_18], 0
0x14007f918  lea     rcx, [rbp+var_30]
0x14007f91c  mov     [rbp+var_10], 0
0x14007f924  mov     [rbp+var_30], 0
0x14007f92c  xor     ebx, ebx
0x14007f92e  mov     [rbp+arg_10], 0
0x14007f936  call    cs:__imp_GdiplusStartup
0x14007f93c  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14007f943  lea     ecx, [rbx+30h]; unsigned __int64
0x14007f946  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x14007f94b  mov     [rbp+var_28], rax
0x14007f94f  test    rax, rax
0x14007f952  jz      loc_14007F9DB
0x14007f958  mov     rdx, rdi; HINSTANCE
0x14007f95b  mov     rcx, rax; this
0x14007f95e  call    ??0StreamWrapper@D3DCommon@@AEAA@PEAUHINSTANCE__@@I@Z; D3DCommon::StreamWrapper::StreamWrapper(HINSTANCE__ *,uint)
0x14007f963  mov     rsi, rax
0x14007f966  test    rax, rax
0x14007f969  jz      short loc_14007F9DB
0x14007f96b  mov     rcx, rax; this
0x14007f96e  call    ?Load@StreamWrapper@D3DCommon@@QEAAJXZ; D3DCommon::StreamWrapper::Load(void)
0x14007f973  mov     edi, eax
0x14007f975  test    eax, eax
0x14007f977  js      short loc_14007F98D
0x14007f979  mov     rcx, [rsi]
0x14007f97c  mov     rax, [rcx+8]
0x14007f980  mov     rcx, rsi
0x14007f983  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007f988  xor     edi, edi
0x14007f98a  mov     rbx, rsi
0x14007f98d  mov     rax, [rsi]
0x14007f990  mov     rcx, rsi
0x14007f993  mov     rax, [rax+10h]
0x14007f997  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007f99c  test    edi, edi
0x14007f99e  js      short loc_14007F9F8
0x14007f9a0  lea     rdx, [rbp+arg_10]
0x14007f9a4  mov     rcx, rbx
0x14007f9a7  call    cs:__imp_GdipCreateBitmapFromStream
0x14007f9ad  test    eax, eax
0x14007f9af  jnz     short loc_14007F9CA
0x14007f9b1  mov     rcx, [rbp+arg_10]; this
0x14007f9b5  test    rcx, rcx
0x14007f9b8  jz      short loc_14007F9CA
0x14007f9ba  mov     r9, [rbp+arg_20]; enum _D3DPOOL
0x14007f9be  mov     rdx, r15; struct Gdiplus::GpBitmap *
0x14007f9c1  call    ?CreateTextureFromGDIBitmap@D3DCommon@@YAJPEAVGpBitmap@Gdiplus@@PEAUIDirect3DDevice9@@W4_D3DPOOL@@PEAPEAUIDirect3DTexture9@@@Z; D3DCommon::CreateTextureFromGDIBitmap(Gdiplus::GpBitmap *,IDirect3DDevice9 *,_D3DPOOL,IDirect3DTexture9 * *)
0x14007f9c6  mov     edi, eax
0x14007f9c8  jmp     short loc_14007FA07
0x14007f9ca  mov     ecx, 8Eh; this
0x14007f9cf  call    ?ERR@D3DCommon@@YAXGZZ; D3DCommon::ERR(ushort,...)
0x14007f9d4  mov     edi, 80004005h
0x14007f9d9  jmp     short loc_14007FA07
0x14007f9db  mov     ecx, 6Dh ; 'm'; this
0x14007f9e0  lea     r8, aD3dcommonStrea_0; "D3DCommon::StreamWrapper::CreateStreamW"...
0x14007f9e7  lea     rdx, aPstream; "pStream"
0x14007f9ee  call    ?ERR@D3DCommon@@YAXGZZ; D3DCommon::ERR(ushort,...)
0x14007f9f3  mov     edi, 8007000Eh
0x14007f9f8  mov     ecx, 9Fh; this
0x14007f9fd  mov     edx, 2BDh; unsigned __int16
0x14007fa02  call    ?ERR@D3DCommon@@YAXGZZ; D3DCommon::ERR(ushort,...)
0x14007fa07  mov     rcx, [rbp+arg_10]
0x14007fa0b  call    cs:__imp_GdipDisposeImage
0x14007fa11  test    rbx, rbx
0x14007fa14  jz      short loc_14007FA25
0x14007fa16  mov     rax, [rbx]
0x14007fa19  mov     rcx, rbx
0x14007fa1c  mov     rax, [rax+10h]
0x14007fa20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007fa25  mov     rcx, [rbp+var_30]
0x14007fa29  call    cs:__imp_GdiplusShutdown
0x14007fa2f  mov     eax, edi
0x14007fa31  mov     rbx, [rsp+50h+arg_0]
0x14007fa36  mov     rsi, [rsp+50h+arg_8]
0x14007fa3b  add     rsp, 50h
0x14007fa3f  pop     r15
0x14007fa41  pop     rdi
0x14007fa42  pop     rbp
0x14007fa43  retn
```
