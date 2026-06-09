# HDRConverter::CreateD2DBitmaps(IWICBitmapSource *,_GUID const &,_GUID const &)

- ea: `0x18003c640`
- end: `0x18003c991`
- name: `?CreateD2DBitmaps@HDRConverter@@AEAAJPEAUIWICBitmapSource@@AEBU_GUID@@1@Z`
- size: `849`
- prototype: `__int64 __fastcall(HDRConverter *__hidden this, struct IWICBitmapSource *, const struct _GUID *, const struct _GUID *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18003c0a0`

## callees

- `0x18003c640`
- `0x18003c9a0`
- `0x18003cc90`
- `0x180045010`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall HDRConverter::CreateD2DBitmaps(
        HDRConverter *this,
        struct IWICBitmapSource *a2,
        const struct _GUID *a3,
        const struct _GUID *a4)
{
  int As64bppWICBitmap; // ebx
  __int64 (__fastcall ***v8)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v9)(_QWORD, GUID *, char *); // r12
  __int64 v10; // rcx
  struct IWICBitmap *v11; // rcx
  __int64 v12; // rcx
  __int64 v13; // rbx
  __int64 (__fastcall *v14)(__int64, __int64, _QWORD, _QWORD, __int64 *); // rsi
  __int64 v15; // rcx
  __int64 v16; // rbx
  _QWORD *v17; // rsi
  __int64 v18; // rcx
  __int64 v19; // r14
  __int64 v20; // rcx
  struct IWICBitmap *v21; // rcx
  __int64 (__fastcall ***v22)(_QWORD, _QWORD, _QWORD); // rcx
  __int64 v23; // rcx
  __int64 (__fastcall ***v25)(_QWORD, GUID *, char *); // [rsp+40h] [rbp-39h] BYREF
  __int64 v26; // [rsp+48h] [rbp-31h] BYREF
  __int64 v27; // [rsp+50h] [rbp-29h] BYREF
  double v28; // [rsp+58h] [rbp-21h] BYREF
  double v29; // [rsp+60h] [rbp-19h] BYREF
  __int64 v30; // [rsp+68h] [rbp-11h] BYREF
  float v31; // [rsp+70h] [rbp-9h]
  float v32; // [rsp+74h] [rbp-5h]
  __int64 v33; // [rsp+78h] [rbp-1h]
  __int64 v34; // [rsp+80h] [rbp+7h]
  struct IWICBitmap *v35; // [rsp+F8h] [rbp+7Fh] BYREF

  v26 = 0;
  v25 = 0;
  v35 = 0;
  if ( *(_OWORD *)a3 == *(_OWORD *)&GUID_WICPixelFormat32bppBGR101010 )
  {
    v28 = 0.0;
    v29 = 0.0;
    As64bppWICBitmap = ((__int64 (__fastcall *)(struct IWICBitmapSource *, double *, double *, const struct _GUID *))a2->lpVtbl->GetResolution)(
                         a2,
                         &v28,
                         &v29,
                         a4);
    if ( As64bppWICBitmap >= 0 )
    {
      v27 = 0;
      As64bppWICBitmap = ((__int64 (__fastcall *)(struct IWICBitmapSource *, __int64 *, char *))a2->lpVtbl->GetSize)(
                           a2,
                           &v27,
                           (char *)&v27 + 4);
      if ( As64bppWICBitmap >= 0 )
      {
        As64bppWICBitmap = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD))(**((_QWORD **)this + 5) + 936LL))(
                             *((_QWORD *)this + 5),
                             12,
                             &v25);
        if ( As64bppWICBitmap >= 0 )
        {
          v8 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v25;
          v9 = **v25;
          v10 = *((_QWORD *)this + 1);
          if ( v10 )
          {
            *((_QWORD *)this + 1) = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
          }
          As64bppWICBitmap = v9(v8, &GUID_1c4820bb_5771_4518_a581_2fe4dd0ec657, (char *)this + 8);
          if ( As64bppWICBitmap >= 0 )
          {
            v11 = v35;
            if ( v35 )
            {
              v35 = 0;
              ((void (__fastcall *)(struct IWICBitmap *))v11->lpVtbl->Release)(v11);
            }
            As64bppWICBitmap = HDRConverter::GetAs64bppWICBitmap(this, a2, a3, &v35);
            if ( As64bppWICBitmap >= 0 )
            {
              v12 = *((_QWORD *)this + 7);
              if ( v12 )
              {
                *((_QWORD *)this + 7) = 0;
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
              }
              As64bppWICBitmap = HDRConverter::CreateD2DImageFromHDR10WICBitmap(
                                   this,
                                   v35,
                                   (struct ID2D1Image **)this + 7);
              if ( As64bppWICBitmap >= 0 )
              {
                v13 = *((_QWORD *)this + 5);
                v14 = *(__int64 (__fastcall **)(__int64, __int64, _QWORD, _QWORD, __int64 *))(*(_QWORD *)v13 + 472LL);
                v15 = v26;
                if ( v26 )
                {
                  v26 = 0;
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
                }
                As64bppWICBitmap = v14(v13, 2, 0, 0, &v26);
                if ( As64bppWICBitmap >= 0 )
                {
                  v30 = 0x30000000ALL;
                  v31 = v28;
                  v32 = v29;
                  v33 = 1;
                  v34 = v26;
                  v16 = *((_QWORD *)this + 5);
                  v17 = (_QWORD *)((char *)this + 64);
                  v18 = *((_QWORD *)this + 8);
                  if ( v18 )
                  {
                    *v17 = 0;
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
                  }
                  As64bppWICBitmap = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, _QWORD, __int64 *, char *))(*(_QWORD *)v16 + 456LL))(
                                       v16,
                                       v27,
                                       0,
                                       0,
                                       &v30,
                                       (char *)this + 64);
                  if ( As64bppWICBitmap >= 0 )
                  {
                    LODWORD(v33) = 6;
                    v19 = *((_QWORD *)this + 5);
                    v20 = *((_QWORD *)this + 9);
                    if ( v20 )
                    {
                      *((_QWORD *)this + 9) = 0;
                      (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
                    }
                    As64bppWICBitmap = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, _QWORD, __int64 *, char *))(*(_QWORD *)v19 + 456LL))(
                                         v19,
                                         v27,
                                         0,
                                         0,
                                         &v30,
                                         (char *)this + 72);
                    if ( As64bppWICBitmap >= 0 )
                      (*(void (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 5) + 592LL))(
                        *((_QWORD *)this + 5),
                        *v17);
                  }
                }
              }
            }
          }
        }
      }
    }
  }
  else
  {
    As64bppWICBitmap = -2147024809;
  }
  v21 = v35;
  if ( v35 )
  {
    v35 = 0;
    ((void (__fastcall *)(struct IWICBitmap *))v21->lpVtbl->Release)(v21);
  }
  v22 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v25;
  if ( v25 )
  {
    v25 = 0;
    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v22)[2])(v22);
  }
  v23 = v26;
  if ( v26 )
  {
    v26 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
  }
  return (unsigned int)As64bppWICBitmap;
}

```

## disassembly

```asm
0x18003c640  mov     [rsp-8+arg_18], r9
0x18003c645  push    rbp
0x18003c646  push    rbx
0x18003c647  push    rsi
0x18003c648  push    rdi
0x18003c649  push    r12
0x18003c64b  push    r13
0x18003c64d  push    r14
0x18003c64f  push    r15
0x18003c651  lea     rbp, [rsp-1Fh]
0x18003c656  sub     rsp, 98h
0x18003c65d  mov     r15, r8
0x18003c660  mov     rsi, rdx
0x18003c663  mov     rdi, rcx
0x18003c666  xor     r13d, r13d
0x18003c669  mov     [rbp+57h+var_88], r13
0x18003c66d  mov     [rbp+57h+var_90], r13
0x18003c671  mov     [rbp+57h+arg_18], r13
0x18003c675  mov     rax, [r8]
0x18003c678  cmp     rax, qword ptr cs:GUID_WICPixelFormat32bppBGR101010.Data1
0x18003c67f  jnz     loc_18003C927
0x18003c685  mov     rax, [r8+8]
0x18003c689  cmp     rax, qword ptr cs:GUID_WICPixelFormat32bppBGR101010.Data4
0x18003c690  jnz     loc_18003C927
0x18003c696  xorps   xmm0, xmm0
0x18003c699  movsd   [rbp+57h+var_78], xmm0
0x18003c69e  movsd   [rbp+57h+var_70], xmm0
0x18003c6a3  mov     rax, [rdx]
0x18003c6a6  lea     r8, [rbp+57h+var_70]
0x18003c6aa  lea     rdx, [rbp+57h+var_78]
0x18003c6ae  mov     rcx, rsi
0x18003c6b1  mov     rax, [rax+28h]
0x18003c6b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c6ba  mov     ebx, eax
0x18003c6bc  test    eax, eax
0x18003c6be  js      loc_18003C92C
0x18003c6c4  mov     [rbp+57h+var_80], r13
0x18003c6c8  mov     rax, [rsi]
0x18003c6cb  lea     r8, [rbp+57h+var_80+4]
0x18003c6cf  lea     rdx, [rbp+57h+var_80]
0x18003c6d3  mov     rcx, rsi
0x18003c6d6  mov     rax, [rax+18h]
0x18003c6da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c6df  mov     ebx, eax
0x18003c6e1  test    eax, eax
0x18003c6e3  js      loc_18003C92C
0x18003c6e9  mov     rbx, [rdi+28h]
0x18003c6ed  mov     rax, [rbx]
0x18003c6f0  mov     r14, [rax+3A8h]
0x18003c6f7  mov     rcx, [rbp+57h+var_90]
0x18003c6fb  test    rcx, rcx
0x18003c6fe  jz      short loc_18003C711
0x18003c700  mov     [rbp+57h+var_90], r13
0x18003c704  mov     rdx, [rcx]
0x18003c707  mov     rax, [rdx+10h]
0x18003c70b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c710  nop
0x18003c711  lea     r8, [rbp+57h+var_90]
0x18003c715  mov     edx, 0Ch
0x18003c71a  mov     rcx, rbx
0x18003c71d  mov     rax, r14
0x18003c720  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c725  mov     ebx, eax
0x18003c727  test    eax, eax
0x18003c729  js      loc_18003C92C
0x18003c72f  mov     rbx, [rbp+57h+var_90]
0x18003c733  mov     rax, [rbx]
0x18003c736  mov     r12, [rax]
0x18003c739  mov     rcx, [rdi+8]
0x18003c73d  test    rcx, rcx
0x18003c740  jz      short loc_18003C753
0x18003c742  mov     [rdi+8], r13
0x18003c746  mov     rdx, [rcx]
0x18003c749  mov     rax, [rdx+10h]
0x18003c74d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c752  nop
0x18003c753  lea     r8, [rdi+8]
0x18003c757  lea     rdx, _GUID_1c4820bb_5771_4518_a581_2fe4dd0ec657
0x18003c75e  mov     rcx, rbx
0x18003c761  mov     rax, r12
0x18003c764  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c769  mov     ebx, eax
0x18003c76b  test    eax, eax
0x18003c76d  js      loc_18003C92C
0x18003c773  mov     rcx, [rbp+57h+arg_18]
0x18003c777  test    rcx, rcx
0x18003c77a  jz      short loc_18003C78D
0x18003c77c  mov     [rbp+57h+arg_18], r13
0x18003c780  mov     rax, [rcx]
0x18003c783  mov     rax, [rax+10h]
0x18003c787  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c78c  nop
0x18003c78d  lea     r9, [rbp+57h+arg_18]; struct IWICBitmap **
0x18003c791  mov     r8, r15; struct _GUID *
0x18003c794  mov     rdx, rsi; struct IWICBitmapSource *
0x18003c797  mov     rcx, rdi; this
0x18003c79a  call    ?GetAs64bppWICBitmap@HDRConverter@@AEAAJPEAUIWICBitmapSource@@AEBU_GUID@@PEAPEAUIWICBitmap@@@Z; HDRConverter::GetAs64bppWICBitmap(IWICBitmapSource *,_GUID const &,IWICBitmap * *)
0x18003c79f  mov     ebx, eax
0x18003c7a1  test    eax, eax
0x18003c7a3  js      loc_18003C92C
0x18003c7a9  mov     rcx, [rdi+38h]
0x18003c7ad  test    rcx, rcx
0x18003c7b0  jz      short loc_18003C7C3
0x18003c7b2  mov     [rdi+38h], r13
0x18003c7b6  mov     rax, [rcx]
0x18003c7b9  mov     rax, [rax+10h]
0x18003c7bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c7c2  nop
0x18003c7c3  lea     r8, [rdi+38h]; struct ID2D1Image **
0x18003c7c7  mov     rdx, [rbp+57h+arg_18]; struct IWICBitmap *
0x18003c7cb  mov     rcx, rdi; this
0x18003c7ce  call    ?CreateD2DImageFromHDR10WICBitmap@HDRConverter@@AEAAJPEAUIWICBitmap@@PEAPEAUID2D1Image@@@Z; HDRConverter::CreateD2DImageFromHDR10WICBitmap(IWICBitmap *,ID2D1Image * *)
0x18003c7d3  mov     ebx, eax
0x18003c7d5  test    eax, eax
0x18003c7d7  js      loc_18003C92C
0x18003c7dd  mov     rbx, [rdi+28h]
0x18003c7e1  mov     rax, [rbx]
0x18003c7e4  mov     rsi, [rax+1D8h]
0x18003c7eb  mov     rcx, [rbp+57h+var_88]
0x18003c7ef  test    rcx, rcx
0x18003c7f2  jz      short loc_18003C805
0x18003c7f4  mov     [rbp+57h+var_88], r13
0x18003c7f8  mov     rax, [rcx]
0x18003c7fb  mov     rax, [rax+10h]
0x18003c7ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c804  nop
0x18003c805  lea     rax, [rbp+57h+var_88]
0x18003c809  mov     [rsp+0D0h+var_B0], rax
0x18003c80e  xor     r9d, r9d
0x18003c811  xor     r8d, r8d
0x18003c814  mov     edx, 2
0x18003c819  mov     rcx, rbx
0x18003c81c  mov     rax, rsi
0x18003c81f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c824  mov     ebx, eax
0x18003c826  test    eax, eax
0x18003c828  js      loc_18003C92C
0x18003c82e  mov     rax, 30000000Ah
0x18003c838  mov     [rbp+57h+var_68], rax
0x18003c83c  movsd   xmm0, [rbp+57h+var_78]
0x18003c841  cvtpd2ps xmm0, xmm0
0x18003c845  movss   [rbp+57h+var_60], xmm0
0x18003c84a  movsd   xmm1, [rbp+57h+var_70]
0x18003c84f  cvtpd2ps xmm1, xmm1
0x18003c853  movss   [rbp+57h+var_5C], xmm1
0x18003c858  mov     [rbp+57h+var_58], 1
0x18003c860  mov     rax, [rbp+57h+var_88]
0x18003c864  mov     [rbp+57h+var_50], rax
0x18003c868  mov     rbx, [rdi+28h]
0x18003c86c  lea     rsi, [rdi+40h]
0x18003c870  mov     rcx, [rsi]
0x18003c873  test    rcx, rcx
0x18003c876  jz      short loc_18003C888
0x18003c878  mov     [rsi], r13
0x18003c87b  mov     rax, [rcx]
0x18003c87e  mov     rax, [rax+10h]
0x18003c882  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c887  nop
0x18003c888  mov     rax, [rbx]
0x18003c88b  mov     [rsp+0D0h+var_A8], rsi
0x18003c890  lea     rcx, [rbp+57h+var_68]
0x18003c894  mov     [rsp+0D0h+var_B0], rcx
0x18003c899  xor     r9d, r9d
0x18003c89c  xor     r8d, r8d
0x18003c89f  mov     rdx, [rbp+57h+var_80]
0x18003c8a3  mov     rcx, rbx
0x18003c8a6  mov     rax, [rax+1C8h]
0x18003c8ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c8b2  mov     ebx, eax
0x18003c8b4  test    eax, eax
0x18003c8b6  js      short loc_18003C92C
0x18003c8b8  mov     dword ptr [rbp+57h+var_58], 6
0x18003c8bf  mov     r14, [rdi+28h]
0x18003c8c3  lea     rbx, [rdi+48h]
0x18003c8c7  mov     rcx, [rbx]
0x18003c8ca  test    rcx, rcx
0x18003c8cd  jz      short loc_18003C8DF
0x18003c8cf  mov     [rbx], r13
0x18003c8d2  mov     rax, [rcx]
0x18003c8d5  mov     rax, [rax+10h]
0x18003c8d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c8de  nop
0x18003c8df  mov     rax, [r14]
0x18003c8e2  mov     [rsp+0D0h+var_A8], rbx
0x18003c8e7  lea     rcx, [rbp+57h+var_68]
0x18003c8eb  mov     [rsp+0D0h+var_B0], rcx
0x18003c8f0  xor     r9d, r9d
0x18003c8f3  xor     r8d, r8d
0x18003c8f6  mov     rdx, [rbp+57h+var_80]
0x18003c8fa  mov     rcx, r14
0x18003c8fd  mov     rax, [rax+1C8h]
0x18003c904  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c909  mov     ebx, eax
0x18003c90b  test    eax, eax
0x18003c90d  js      short loc_18003C92C
0x18003c90f  mov     rcx, [rdi+28h]
0x18003c913  mov     rax, [rcx]
0x18003c916  mov     rdx, [rsi]
0x18003c919  mov     rax, [rax+250h]
0x18003c920  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c925  jmp     short loc_18003C92C
0x18003c927  mov     ebx, 80070057h
0x18003c92c  mov     rcx, [rbp+57h+arg_18]
0x18003c930  test    rcx, rcx
0x18003c933  jz      short loc_18003C946
0x18003c935  mov     [rbp+57h+arg_18], r13
0x18003c939  mov     rax, [rcx]
0x18003c93c  mov     rax, [rax+10h]
0x18003c940  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c945  nop
0x18003c946  mov     rcx, [rbp+57h+var_90]
0x18003c94a  test    rcx, rcx
0x18003c94d  jz      short loc_18003C960
0x18003c94f  mov     [rbp+57h+var_90], r13
0x18003c953  mov     rax, [rcx]
0x18003c956  mov     rax, [rax+10h]
0x18003c95a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c95f  nop
0x18003c960  mov     rcx, [rbp+57h+var_88]
0x18003c964  test    rcx, rcx
0x18003c967  jz      short loc_18003C97A
0x18003c969  mov     [rbp+57h+var_88], r13
0x18003c96d  mov     rax, [rcx]
0x18003c970  mov     rax, [rax+10h]
0x18003c974  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c979  nop
0x18003c97a  mov     eax, ebx
0x18003c97c  add     rsp, 98h
0x18003c983  pop     r15
0x18003c985  pop     r14
0x18003c987  pop     r13
0x18003c989  pop     r12
0x18003c98b  pop     rdi
0x18003c98c  pop     rsi
0x18003c98d  pop     rbx
0x18003c98e  pop     rbp
0x18003c98f  retn
```
