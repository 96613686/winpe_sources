# CGpWmpEncoder::CreateNewFrameInternal(IWICBitmapFrameEncode * *,IPropertyBag2 * *,int)

- ea: `0x1800327b0`
- end: `0x1800329b8`
- name: `?CreateNewFrameInternal@CGpWmpEncoder@@UEAAJPEAPEAUIWICBitmapFrameEncode@@PEAPEAUIPropertyBag2@@H@Z`
- size: `520`
- prototype: `__int64 __fastcall(CGpWmpEncoder *__hidden this, struct IWICBitmapFrameEncode **, struct IPropertyBag2 **, int)`
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180035a80`
- `0x18003ab30`

## callees

- `0x18002b078`
- `0x1800327b0`
- `0x180035018`
- `0x180036444`
- `0x180043e34`
- `0x180045010`

## pseudocode

```c
__int64 __fastcall CGpWmpEncoder::CreateNewFrameInternal(
        CGpWmpEncoder *this,
        struct IWICBitmapFrameEncode **a2,
        struct IPropertyBag2 **a3,
        int a4)
{
  int v8; // edi
  CWmpEncoderFrame *v9; // rax
  CWmpEncoderFrame *v10; // rdi
  struct IWICComponentFactory *WICFactory; // rax
  struct IPropertyBag2 *v12; // rcx
  struct IWICBitmapFrameEncode *v13; // rcx
  int v15; // [rsp+30h] [rbp-38h] BYREF
  struct IWICBitmapFrameEncode *v16; // [rsp+38h] [rbp-30h] BYREF
  __int64 v17; // [rsp+40h] [rbp-28h] BYREF
  struct IPropertyBag2 *v18; // [rsp+48h] [rbp-20h] BYREF
  int v19; // [rsp+70h] [rbp+8h] BYREF

  v16 = 0;
  v18 = 0;
  if ( *((_DWORD *)this + 4) != 2 )
    return (unsigned int)-2003292412;
  v17 = 0;
  v8 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64, __int64 *))(**((_QWORD **)this + 12) + 40LL))(
         *((_QWORD *)this + 12),
         0,
         1,
         &v17);
  if ( v8 < 0 )
    goto LABEL_21;
  if ( HIDWORD(v17) )
  {
    v8 = -2003292273;
  }
  else
  {
    if ( (v17 & 1) != 0 )
    {
      LOBYTE(v19) = -68;
      v15 = 0;
      v8 = (*(__int64 (__fastcall **)(_QWORD, int *, __int64, int *))(**((_QWORD **)this + 12) + 32LL))(
             *((_QWORD *)this + 12),
             &v19,
             1,
             &v15);
      if ( v8 < 0 )
        goto LABEL_21;
    }
    try
    {
      v9 = (CWmpEncoderFrame *)operator new(0x10428u);
      v10 = CWmpEncoderFrame::CWmpEncoderFrame(v9, this, a4);
    }
    catch ( std::bad_alloc )
    {
      v19 = -2147024882;
      v8 = -2147024882;
      goto LABEL_21;
    }
    if ( v10 )
    {
      if ( !memcmp_0(&IID_IWICBitmapFrameEncode, &IID_IUnknown, 0x10u) )
      {
        v16 = (struct IWICBitmapFrameEncode *)v10;
        (*(void (__fastcall **)(CWmpEncoderFrame *))(*(_QWORD *)v10 + 8LL))(v10);
        v8 = 0;
      }
      else
      {
        v8 = (*(__int64 (__fastcall **)(CWmpEncoderFrame *, GUID *, struct IWICBitmapFrameEncode **))(*(_QWORD *)v10 + 56LL))(
               v10,
               &IID_IWICBitmapFrameEncode,
               &v16);
        if ( v8 < 0 )
          goto LABEL_21;
      }
      if ( a3 )
      {
        WICFactory = GetWICFactory();
        v8 = ((__int64 (__fastcall *)(struct IWICComponentFactory *, struct tagPROPBAG2 near **, _QWORD, struct IPropertyBag2 **))WICFactory->lpVtbl->CreateEncoderPropertyBag)(
               WICFactory,
               &g_pbg2EncoderOptions,
               (unsigned int)g_cEncoderOptions,
               &v18);
        if ( v8 < 0 )
          goto LABEL_21;
        v12 = v18;
        *a3 = v18;
        if ( v12 )
          ((void (__fastcall *)(struct IPropertyBag2 *))v12->lpVtbl->AddRef)(v12);
      }
      v13 = v16;
      *a2 = v16;
      if ( v13 )
      {
        ((void (__fastcall *)(struct IWICBitmapFrameEncode *))v13->lpVtbl->AddRef)(v13);
        v13 = v16;
      }
      *((_DWORD *)this + 4) = 3;
      goto LABEL_22;
    }
    v8 = -2147024882;
  }
LABEL_21:
  v13 = v16;
LABEL_22:
  if ( v13 )
  {
    ((void (__fastcall *)(struct IWICBitmapFrameEncode *))v13->lpVtbl->Release)(v13);
    v16 = 0;
  }
  if ( v18 )
    ((void (__fastcall *)(struct IPropertyBag2 *))v18->lpVtbl->Release)(v18);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1800327b0  mov     rax, rsp
0x1800327b3  mov     [rax+10h], rsi
0x1800327b7  mov     [rax+18h], rdi
0x1800327bb  push    r12
0x1800327bd  push    r14
0x1800327bf  push    r15
0x1800327c1  sub     rsp, 50h
0x1800327c5  mov     r15d, r9d
0x1800327c8  mov     r14, r8
0x1800327cb  mov     r12, rdx
0x1800327ce  mov     rsi, rcx
0x1800327d1  mov     qword ptr [rax-30h], 0
0x1800327d9  mov     qword ptr [rax-20h], 0
0x1800327e1  cmp     dword ptr [rcx+10h], 2
0x1800327e5  jz      short loc_1800327F1
0x1800327e7  mov     edi, 88982F04h
0x1800327ec  jmp     loc_18003299E
0x1800327f1  mov     [rsp+68h+var_28], 0
0x1800327fa  mov     rcx, [rcx+60h]
0x1800327fe  mov     rax, [rcx]
0x180032801  lea     r9, [rsp+68h+var_28]
0x180032806  xor     edx, edx
0x180032808  lea     r8d, [rdx+1]
0x18003280c  mov     rax, [rax+28h]
0x180032810  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032815  mov     edi, eax
0x180032817  test    eax, eax
0x180032819  js      loc_180032969
0x18003281f  cmp     dword ptr [rsp+68h+var_28+4], 0
0x180032824  jz      short loc_180032830
0x180032826  mov     edi, 88982F8Fh
0x18003282b  jmp     loc_180032969
0x180032830  mov     eax, dword ptr [rsp+68h+var_28]
0x180032834  test    al, 1
0x180032836  jz      short loc_18003286F
0x180032838  mov     byte ptr [rsp+68h+arg_0], 0BCh
0x18003283d  mov     [rsp+68h+var_38], 0
0x180032845  mov     rcx, [rsi+60h]
0x180032849  mov     rax, [rcx]
0x18003284c  lea     r9, [rsp+68h+var_38]
0x180032851  mov     r8d, 1
0x180032857  lea     rdx, [rsp+68h+arg_0]
0x18003285c  mov     rax, [rax+20h]
0x180032860  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032865  mov     edi, eax
0x180032867  test    eax, eax
0x180032869  js      loc_180032969
0x18003286f  mov     ecx, 10428h; Size
0x180032874  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180032879  mov     r8d, r15d; int
0x18003287c  mov     rdx, rsi; struct CGpWmpEncoder *
0x18003287f  mov     rcx, rax; this
0x180032882  call    ??0CWmpEncoderFrame@@QEAA@PEAVCGpWmpEncoder@@H@Z; CWmpEncoderFrame::CWmpEncoderFrame(CGpWmpEncoder *,int)
0x180032887  mov     rdi, rax
0x18003288a  test    rdi, rdi
0x18003288d  jnz     short loc_180032899
0x18003288f  mov     edi, 8007000Eh
0x180032894  jmp     loc_180032969
0x180032899  mov     r8d, 10h; Size
0x18003289f  lea     rdx, IID_IUnknown; Buf2
0x1800328a6  lea     rcx, IID_IWICBitmapFrameEncode; Buf1
0x1800328ad  call    memcmp_0
0x1800328b2  mov     rcx, rdi
0x1800328b5  test    eax, eax
0x1800328b7  jnz     short loc_1800328CE
0x1800328b9  mov     [rsp+68h+var_30], rdi
0x1800328be  mov     rax, [rdi]
0x1800328c1  mov     rax, [rax+8]
0x1800328c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800328ca  xor     edi, edi
0x1800328cc  jmp     short loc_1800328EC
0x1800328ce  mov     rax, [rdi]
0x1800328d1  lea     r8, [rsp+68h+var_30]
0x1800328d6  lea     rdx, IID_IWICBitmapFrameEncode
0x1800328dd  mov     rax, [rax+38h]
0x1800328e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800328e6  mov     edi, eax
0x1800328e8  test    eax, eax
0x1800328ea  js      short loc_180032969
0x1800328ec  test    r14, r14
0x1800328ef  jz      short loc_18003293D
0x1800328f1  call    ?GetWICFactory@@YAPEAUIWICComponentFactory@@XZ; GetWICFactory(void)
0x1800328f6  mov     r10, rax
0x1800328f9  mov     rcx, [rax]
0x1800328fc  mov     r8d, dword ptr cs:?g_cEncoderOptions@@3_KA; unsigned __int64 g_cEncoderOptions
0x180032903  mov     rax, [rcx+110h]
0x18003290a  lea     r9, [rsp+68h+var_20]
0x18003290f  lea     rdx, ?g_pbg2EncoderOptions@@3PAUtagPROPBAG2@@A; tagPROPBAG2 near * g_pbg2EncoderOptions
0x180032916  mov     rcx, r10
0x180032919  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003291e  mov     edi, eax
0x180032920  test    eax, eax
0x180032922  js      short loc_180032969
0x180032924  mov     rcx, [rsp+68h+var_20]
0x180032929  mov     [r14], rcx
0x18003292c  test    rcx, rcx
0x18003292f  jz      short loc_18003293D
0x180032931  mov     rax, [rcx]
0x180032934  mov     rax, [rax+8]
0x180032938  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003293d  mov     rcx, [rsp+68h+var_30]
0x180032942  mov     [r12], rcx
0x180032946  test    rcx, rcx
0x180032949  jz      short loc_18003295C
0x18003294b  mov     rax, [rcx]
0x18003294e  mov     rax, [rax+8]
0x180032952  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032957  mov     rcx, [rsp+68h+var_30]
0x18003295c  mov     dword ptr [rsi+10h], 3
0x180032963  jmp     short loc_18003296E
0x180032965  mov     edi, [rsp+68h+arg_0]
0x180032969  mov     rcx, [rsp+68h+var_30]
0x18003296e  test    rcx, rcx
0x180032971  jz      short loc_180032988
0x180032973  mov     rax, [rcx]
0x180032976  mov     rax, [rax+10h]
0x18003297a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003297f  mov     [rsp+68h+var_30], 0
0x180032988  mov     rcx, [rsp+68h+var_20]
0x18003298d  test    rcx, rcx
0x180032990  jz      short loc_18003299E
0x180032992  mov     rax, [rcx]
0x180032995  mov     rax, [rax+10h]
0x180032999  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003299e  mov     eax, edi
0x1800329a0  lea     r11, [rsp+68h+var_18]
0x1800329a5  mov     rsi, [r11+28h]
0x1800329a9  mov     rdi, [r11+30h]
0x1800329ad  mov     rsp, r11
0x1800329b0  pop     r15
0x1800329b2  pop     r14
0x1800329b4  pop     r12
0x1800329b6  retn
```
