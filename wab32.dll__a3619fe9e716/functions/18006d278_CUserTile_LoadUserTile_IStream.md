# CUserTile::_LoadUserTile(IStream *)

- ea: `0x18006d278`
- end: `0x18006d3bd`
- name: `?_LoadUserTile@CUserTile@@AEAAJPEAUIStream@@@Z`
- size: `325`
- prototype: `int(CUserTile *__hidden this, struct IStream *)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x18006c19c`
- `0x18006c288`
- `0x18006c5f8`

## callees

- `0x18006bbd0`
- `0x18006d278`
- `0x18006d3c4`
- `0x180093010`

## import_xrefs

- `GDI32!DeleteObject` at `0x18006d2af`
- `GDI32!DeleteObject` at `0x18006d30d`
- `GDI32!DeleteObject` at `0x18006d2af`
- `GDI32!DeleteObject` at `0x18006d30d`
- `gdiplus!GdipCreateBitmapFromResource` at `0x18006d363`
- `gdiplus!GdipCreateBitmapFromResource` at `0x18006d363`
- `gdiplus!GdipAlloc` at `0x18006d2c6`
- `gdiplus!GdipAlloc` at `0x18006d339`
- `gdiplus!GdipAlloc` at `0x18006d2c6`
- `gdiplus!GdipAlloc` at `0x18006d339`

## pseudocode

```c
__int64 __fastcall CUserTile::_LoadUserTile(CUserTile *this, struct IStream *a2)
{
  void (__fastcall ***v3)(_QWORD, __int64); // rcx
  int v5; // edi
  void *v6; // rcx
  Gdiplus::Bitmap *v7; // rax
  __int64 v8; // rax
  __int64 v9; // rcx
  void *v10; // rcx
  HINSTANCE v11; // rsi
  __int64 v12; // rdi
  __int64 v13; // rcx
  void (__fastcall ***v14)(_QWORD, __int64); // rcx
  __int64 v16; // [rsp+50h] [rbp+8h] BYREF

  v3 = (void (__fastcall ***)(_QWORD, __int64))*((_QWORD *)this + 2);
  v5 = 0;
  if ( v3 )
  {
    (**v3)(v3, 1);
    *((_QWORD *)this + 2) = 0;
  }
  v6 = (void *)*((_QWORD *)this + 3);
  if ( v6 )
  {
    DeleteObject(v6);
    *((_QWORD *)this + 3) = 0;
  }
  *((_DWORD *)this + 2) = 0;
  if ( a2 )
  {
    v7 = (Gdiplus::Bitmap *)GdipAlloc(24);
    if ( !v7 )
    {
LABEL_17:
      *((_QWORD *)this + 2) = 0;
      return (unsigned int)-2147024882;
    }
    v8 = Gdiplus::Bitmap::Bitmap(v7, a2, 1);
    *((_QWORD *)this + 2) = v8;
    if ( !v8 )
      return (unsigned int)-2147024882;
    v9 = *(unsigned int *)(v8 + 16);
    *(_DWORD *)(v8 + 16) = 0;
    v5 = ResultFromGdiplusStatus(v9);
    if ( v5 >= 0 )
    {
      *((_DWORD *)this + 2) = 1;
    }
    else
    {
      v10 = (void *)*((_QWORD *)this + 2);
      if ( v10 )
      {
        DeleteObject(v10);
        *((_QWORD *)this + 2) = 0;
      }
    }
  }
  if ( *((_QWORD *)this + 2) )
    return (unsigned int)v5;
  v11 = hinstMapiX;
  *((_DWORD *)this + 2) = 0;
  v12 = GdipAlloc(24);
  if ( !v12 )
    goto LABEL_17;
  v16 = 0;
  *(_QWORD *)v12 = &Gdiplus::Image::`vftable';
  *(_DWORD *)(v12 + 16) = GdipCreateBitmapFromResource(v11, 4140, &v16);
  *(_QWORD *)(v12 + 8) = v16;
  *((_QWORD *)this + 2) = v12;
  v13 = *(unsigned int *)(v12 + 16);
  *(_DWORD *)(v12 + 16) = 0;
  v5 = ResultFromGdiplusStatus(v13);
  if ( v5 < 0 )
  {
    v14 = (void (__fastcall ***)(_QWORD, __int64))*((_QWORD *)this + 2);
    if ( v14 )
    {
      (**v14)(v14, 1);
      *((_QWORD *)this + 2) = 0;
    }
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18006d278  push    rbx
0x18006d27a  push    rbp
0x18006d27b  push    rsi
0x18006d27c  push    rdi
0x18006d27d  sub     rsp, 28h
0x18006d281  xor     ebp, ebp
0x18006d283  mov     rbx, rcx
0x18006d286  mov     rcx, [rcx+10h]
0x18006d28a  mov     rsi, rdx
0x18006d28d  mov     edi, ebp
0x18006d28f  test    rcx, rcx
0x18006d292  jz      short loc_18006D2A6
0x18006d294  mov     rax, [rcx]
0x18006d297  lea     edx, [rbp+1]
0x18006d29a  mov     rax, [rax]
0x18006d29d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006d2a2  mov     [rbx+10h], rbp
0x18006d2a6  mov     rcx, [rbx+18h]; ho
0x18006d2aa  test    rcx, rcx
0x18006d2ad  jz      short loc_18006D2B9
0x18006d2af  call    cs:__imp_DeleteObject
0x18006d2b5  mov     [rbx+18h], rbp
0x18006d2b9  mov     [rbx+8], ebp
0x18006d2bc  test    rsi, rsi
0x18006d2bf  jz      short loc_18006D320
0x18006d2c1  mov     ecx, 18h
0x18006d2c6  call    cs:__imp_GdipAlloc
0x18006d2cc  test    rax, rax
0x18006d2cf  jz      loc_18006D3A9
0x18006d2d5  mov     r8d, 1; int
0x18006d2db  mov     rdx, rsi; struct IStream *
0x18006d2de  mov     rcx, rax; this
0x18006d2e1  call    ??0Bitmap@Gdiplus@@QEAA@PEAUIStream@@H@Z; Gdiplus::Bitmap::Bitmap(IStream *,int)
0x18006d2e6  mov     [rbx+10h], rax
0x18006d2ea  test    rax, rax
0x18006d2ed  jz      loc_18006D3AD
0x18006d2f3  mov     ecx, [rax+10h]
0x18006d2f6  mov     [rax+10h], ebp
0x18006d2f9  call    _ResultFromGdiplusStatus
0x18006d2fe  mov     edi, eax
0x18006d300  test    eax, eax
0x18006d302  jns     short loc_18006D319
0x18006d304  mov     rcx, [rbx+10h]; ho
0x18006d308  test    rcx, rcx
0x18006d30b  jz      short loc_18006D320
0x18006d30d  call    cs:__imp_DeleteObject
0x18006d313  mov     [rbx+10h], rbp
0x18006d317  jmp     short loc_18006D320
0x18006d319  mov     dword ptr [rbx+8], 1
0x18006d320  cmp     [rbx+10h], rbp
0x18006d324  jnz     loc_18006D3B2
0x18006d32a  mov     rsi, cs:hinstMapiX
0x18006d331  mov     ecx, 18h
0x18006d336  mov     [rbx+8], ebp
0x18006d339  call    cs:__imp_GdipAlloc
0x18006d33f  mov     rdi, rax
0x18006d342  test    rax, rax
0x18006d345  jz      short loc_18006D3A9
0x18006d347  lea     rax, ??_7Image@Gdiplus@@6B@; const Gdiplus::Image::`vftable'
0x18006d34e  mov     [rsp+48h+arg_0], rbp
0x18006d353  lea     r8, [rsp+48h+arg_0]
0x18006d358  mov     [rdi], rax
0x18006d35b  mov     edx, 102Ch
0x18006d360  mov     rcx, rsi
0x18006d363  call    cs:__imp_GdipCreateBitmapFromResource
0x18006d369  mov     [rdi+10h], eax
0x18006d36c  mov     rax, [rsp+48h+arg_0]
0x18006d371  mov     [rdi+8], rax
0x18006d375  mov     [rbx+10h], rdi
0x18006d379  mov     ecx, [rdi+10h]
0x18006d37c  mov     [rdi+10h], ebp
0x18006d37f  call    _ResultFromGdiplusStatus
0x18006d384  mov     edi, eax
0x18006d386  test    eax, eax
0x18006d388  jns     short loc_18006D3B2
0x18006d38a  mov     rcx, [rbx+10h]
0x18006d38e  test    rcx, rcx
0x18006d391  jz      short loc_18006D3B2
0x18006d393  mov     rax, [rcx]
0x18006d396  mov     edx, 1
0x18006d39b  mov     rax, [rax]
0x18006d39e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006d3a3  mov     [rbx+10h], rbp
0x18006d3a7  jmp     short loc_18006D3B2
0x18006d3a9  mov     [rbx+10h], rbp
0x18006d3ad  mov     edi, 8007000Eh
0x18006d3b2  mov     eax, edi
0x18006d3b4  add     rsp, 28h
0x18006d3b8  pop     rdi
0x18006d3b9  pop     rsi
0x18006d3ba  pop     rbp
0x18006d3bb  pop     rbx
0x18006d3bc  retn
```
