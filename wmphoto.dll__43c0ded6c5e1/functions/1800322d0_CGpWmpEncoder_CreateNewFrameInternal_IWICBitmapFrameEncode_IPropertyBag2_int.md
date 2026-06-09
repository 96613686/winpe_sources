# CGpWmpEncoder::CreateNewFrameInternal(IWICBitmapFrameEncode * *,IPropertyBag2 * *,int)

- ea: `0x1800322d0`
- end: `0x1800324d7`
- name: `?CreateNewFrameInternal@CGpWmpEncoder@@UEAAJPEAPEAUIWICBitmapFrameEncode@@PEAPEAUIPropertyBag2@@H@Z`
- size: `519`
- prototype: `__int64 __fastcall(CGpWmpEncoder *__hidden this, struct IWICBitmapFrameEncode **, struct IPropertyBag2 **, int)`
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1800354b0`
- `0x18003a3e0`

## callees

- `0x18002aec8`
- `0x1800322d0`
- `0x180034a40`
- `0x180035e74`
- `0x180043624`
- `0x180044010`

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
0x1800322d0  mov     rax, rsp
0x1800322d3  mov     [rax+10h], rsi
0x1800322d7  mov     [rax+18h], rdi
0x1800322db  push    r12
0x1800322dd  push    r14
0x1800322df  push    r15
0x1800322e1  sub     rsp, 50h
0x1800322e5  mov     r15d, r9d
0x1800322e8  mov     r14, r8
0x1800322eb  mov     r12, rdx
0x1800322ee  mov     rsi, rcx
0x1800322f1  mov     qword ptr [rax-30h], 0
0x1800322f9  mov     qword ptr [rax-20h], 0
0x180032301  cmp     dword ptr [rcx+10h], 2
0x180032305  jz      short loc_180032311
0x180032307  mov     edi, 88982F04h
0x18003230c  jmp     loc_1800324BE
0x180032311  mov     [rsp+68h+var_28], 0
0x18003231a  mov     rcx, [rcx+60h]
0x18003231e  mov     rax, [rcx]
0x180032321  lea     r9, [rsp+68h+var_28]
0x180032326  xor     edx, edx
0x180032328  lea     r8d, [rdx+1]
0x18003232c  mov     rax, [rax+28h]
0x180032330  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032335  mov     edi, eax
0x180032337  test    eax, eax
0x180032339  js      loc_180032489
0x18003233f  cmp     dword ptr [rsp+68h+var_28+4], 0
0x180032344  jz      short loc_180032350
0x180032346  mov     edi, 88982F8Fh
0x18003234b  jmp     loc_180032489
0x180032350  mov     eax, dword ptr [rsp+68h+var_28]
0x180032354  test    al, 1
0x180032356  jz      short loc_18003238F
0x180032358  mov     byte ptr [rsp+68h+arg_0], 0BCh
0x18003235d  mov     [rsp+68h+var_38], 0
0x180032365  mov     rcx, [rsi+60h]
0x180032369  mov     rax, [rcx]
0x18003236c  lea     r9, [rsp+68h+var_38]
0x180032371  mov     r8d, 1
0x180032377  lea     rdx, [rsp+68h+arg_0]
0x18003237c  mov     rax, [rax+20h]
0x180032380  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032385  mov     edi, eax
0x180032387  test    eax, eax
0x180032389  js      loc_180032489
0x18003238f  mov     ecx, 10428h; Size
0x180032394  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180032399  mov     r8d, r15d; int
0x18003239c  mov     rdx, rsi; struct CGpWmpEncoder *
0x18003239f  mov     rcx, rax; this
0x1800323a2  call    ??0CWmpEncoderFrame@@QEAA@PEAVCGpWmpEncoder@@H@Z; CWmpEncoderFrame::CWmpEncoderFrame(CGpWmpEncoder *,int)
0x1800323a7  mov     rdi, rax
0x1800323aa  test    rdi, rdi
0x1800323ad  jnz     short loc_1800323B9
0x1800323af  mov     edi, 8007000Eh
0x1800323b4  jmp     loc_180032489
0x1800323b9  mov     r8d, 10h; Size
0x1800323bf  lea     rdx, IID_IUnknown; Buf2
0x1800323c6  lea     rcx, IID_IWICBitmapFrameEncode; Buf1
0x1800323cd  call    memcmp_0
0x1800323d2  mov     rcx, rdi
0x1800323d5  test    eax, eax
0x1800323d7  jnz     short loc_1800323EE
0x1800323d9  mov     [rsp+68h+var_30], rdi
0x1800323de  mov     rax, [rdi]
0x1800323e1  mov     rax, [rax+8]
0x1800323e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800323ea  xor     edi, edi
0x1800323ec  jmp     short loc_18003240C
0x1800323ee  mov     rax, [rdi]
0x1800323f1  lea     r8, [rsp+68h+var_30]
0x1800323f6  lea     rdx, IID_IWICBitmapFrameEncode
0x1800323fd  mov     rax, [rax+38h]
0x180032401  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032406  mov     edi, eax
0x180032408  test    eax, eax
0x18003240a  js      short loc_180032489
0x18003240c  test    r14, r14
0x18003240f  jz      short loc_18003245D
0x180032411  call    ?GetWICFactory@@YAPEAUIWICComponentFactory@@XZ; GetWICFactory(void)
0x180032416  mov     r10, rax
0x180032419  mov     rcx, [rax]
0x18003241c  mov     r8d, dword ptr cs:?g_cEncoderOptions@@3_KA; unsigned __int64 g_cEncoderOptions
0x180032423  mov     rax, [rcx+110h]
0x18003242a  lea     r9, [rsp+68h+var_20]
0x18003242f  lea     rdx, ?g_pbg2EncoderOptions@@3PAUtagPROPBAG2@@A; tagPROPBAG2 near * g_pbg2EncoderOptions
0x180032436  mov     rcx, r10
0x180032439  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003243e  mov     edi, eax
0x180032440  test    eax, eax
0x180032442  js      short loc_180032489
0x180032444  mov     rcx, [rsp+68h+var_20]
0x180032449  mov     [r14], rcx
0x18003244c  test    rcx, rcx
0x18003244f  jz      short loc_18003245D
0x180032451  mov     rax, [rcx]
0x180032454  mov     rax, [rax+8]
0x180032458  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003245d  mov     rcx, [rsp+68h+var_30]
0x180032462  mov     [r12], rcx
0x180032466  test    rcx, rcx
0x180032469  jz      short loc_18003247C
0x18003246b  mov     rax, [rcx]
0x18003246e  mov     rax, [rax+8]
0x180032472  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032477  mov     rcx, [rsp+68h+var_30]
0x18003247c  mov     dword ptr [rsi+10h], 3
0x180032483  jmp     short loc_18003248E
0x180032485  mov     edi, [rsp+68h+arg_0]
0x180032489  mov     rcx, [rsp+68h+var_30]
0x18003248e  test    rcx, rcx
0x180032491  jz      short loc_1800324A8
0x180032493  mov     rax, [rcx]
0x180032496  mov     rax, [rax+10h]
0x18003249a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003249f  mov     [rsp+68h+var_30], 0
0x1800324a8  mov     rcx, [rsp+68h+var_20]
0x1800324ad  test    rcx, rcx
0x1800324b0  jz      short loc_1800324BE
0x1800324b2  mov     rax, [rcx]
0x1800324b5  mov     rax, [rax+10h]
0x1800324b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800324be  mov     eax, edi
0x1800324c0  lea     r11, [rsp+68h+var_18]
0x1800324c5  mov     rsi, [r11+28h]
0x1800324c9  mov     rdi, [r11+30h]
0x1800324cd  mov     rsp, r11
0x1800324d0  pop     r15
0x1800324d2  pop     r14
0x1800324d4  pop     r12
0x1800324d6  retn
```
