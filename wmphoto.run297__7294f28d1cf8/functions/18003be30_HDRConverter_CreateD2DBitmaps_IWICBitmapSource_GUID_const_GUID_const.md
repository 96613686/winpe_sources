# HDRConverter::CreateD2DBitmaps(IWICBitmapSource *,_GUID const &,_GUID const &)

- ea: `0x18003be30`
- end: `0x18003c180`
- name: `?CreateD2DBitmaps@HDRConverter@@AEAAJPEAUIWICBitmapSource@@AEBU_GUID@@1@Z`
- size: `848`
- prototype: `__int64 __fastcall(HDRConverter *__hidden this, struct IWICBitmapSource *, const struct _GUID *, const struct _GUID *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18003b7b0`

## callees

- `0x18003be30`
- `0x18003c190`
- `0x18003c480`
- `0x180044010`

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
0x18003be30  mov     [rsp-8+arg_18], r9
0x18003be35  push    rbp
0x18003be36  push    rbx
0x18003be37  push    rsi
0x18003be38  push    rdi
0x18003be39  push    r12
0x18003be3b  push    r13
0x18003be3d  push    r14
0x18003be3f  push    r15
0x18003be41  lea     rbp, [rsp-1Fh]
0x18003be46  sub     rsp, 98h
0x18003be4d  mov     r15, r8
0x18003be50  mov     rsi, rdx
0x18003be53  mov     rdi, rcx
0x18003be56  xor     r13d, r13d
0x18003be59  mov     [rbp+57h+var_88], r13
0x18003be5d  mov     [rbp+57h+var_90], r13
0x18003be61  mov     [rbp+57h+arg_18], r13
0x18003be65  mov     rax, [r8]
0x18003be68  cmp     rax, qword ptr cs:GUID_WICPixelFormat32bppBGR101010.Data1
0x18003be6f  jnz     loc_18003C117
0x18003be75  mov     rax, [r8+8]
0x18003be79  cmp     rax, qword ptr cs:GUID_WICPixelFormat32bppBGR101010.Data4
0x18003be80  jnz     loc_18003C117
0x18003be86  xorps   xmm0, xmm0
0x18003be89  movsd   [rbp+57h+var_78], xmm0
0x18003be8e  movsd   [rbp+57h+var_70], xmm0
0x18003be93  mov     rax, [rdx]
0x18003be96  lea     r8, [rbp+57h+var_70]
0x18003be9a  lea     rdx, [rbp+57h+var_78]
0x18003be9e  mov     rcx, rsi
0x18003bea1  mov     rax, [rax+28h]
0x18003bea5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003beaa  mov     ebx, eax
0x18003beac  test    eax, eax
0x18003beae  js      loc_18003C11C
0x18003beb4  mov     [rbp+57h+var_80], r13
0x18003beb8  mov     rax, [rsi]
0x18003bebb  lea     r8, [rbp+57h+var_80+4]
0x18003bebf  lea     rdx, [rbp+57h+var_80]
0x18003bec3  mov     rcx, rsi
0x18003bec6  mov     rax, [rax+18h]
0x18003beca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003becf  mov     ebx, eax
0x18003bed1  test    eax, eax
0x18003bed3  js      loc_18003C11C
0x18003bed9  mov     rbx, [rdi+28h]
0x18003bedd  mov     rax, [rbx]
0x18003bee0  mov     r14, [rax+3A8h]
0x18003bee7  mov     rcx, [rbp+57h+var_90]
0x18003beeb  test    rcx, rcx
0x18003beee  jz      short loc_18003BF01
0x18003bef0  mov     [rbp+57h+var_90], r13
0x18003bef4  mov     rdx, [rcx]
0x18003bef7  mov     rax, [rdx+10h]
0x18003befb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003bf00  nop
0x18003bf01  lea     r8, [rbp+57h+var_90]
0x18003bf05  mov     edx, 0Ch
0x18003bf0a  mov     rcx, rbx
0x18003bf0d  mov     rax, r14
0x18003bf10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003bf15  mov     ebx, eax
0x18003bf17  test    eax, eax
0x18003bf19  js      loc_18003C11C
0x18003bf1f  mov     rbx, [rbp+57h+var_90]
0x18003bf23  mov     rax, [rbx]
0x18003bf26  mov     r12, [rax]
0x18003bf29  mov     rcx, [rdi+8]
0x18003bf2d  test    rcx, rcx
0x18003bf30  jz      short loc_18003BF43
0x18003bf32  mov     [rdi+8], r13
0x18003bf36  mov     rdx, [rcx]
0x18003bf39  mov     rax, [rdx+10h]
0x18003bf3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003bf42  nop
0x18003bf43  lea     r8, [rdi+8]
0x18003bf47  lea     rdx, _GUID_1c4820bb_5771_4518_a581_2fe4dd0ec657
0x18003bf4e  mov     rcx, rbx
0x18003bf51  mov     rax, r12
0x18003bf54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003bf59  mov     ebx, eax
0x18003bf5b  test    eax, eax
0x18003bf5d  js      loc_18003C11C
0x18003bf63  mov     rcx, [rbp+57h+arg_18]
0x18003bf67  test    rcx, rcx
0x18003bf6a  jz      short loc_18003BF7D
0x18003bf6c  mov     [rbp+57h+arg_18], r13
0x18003bf70  mov     rax, [rcx]
0x18003bf73  mov     rax, [rax+10h]
0x18003bf77  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003bf7c  nop
0x18003bf7d  lea     r9, [rbp+57h+arg_18]; struct IWICBitmap **
0x18003bf81  mov     r8, r15; struct _GUID *
0x18003bf84  mov     rdx, rsi; struct IWICBitmapSource *
0x18003bf87  mov     rcx, rdi; this
0x18003bf8a  call    ?GetAs64bppWICBitmap@HDRConverter@@AEAAJPEAUIWICBitmapSource@@AEBU_GUID@@PEAPEAUIWICBitmap@@@Z; HDRConverter::GetAs64bppWICBitmap(IWICBitmapSource *,_GUID const &,IWICBitmap * *)
0x18003bf8f  mov     ebx, eax
0x18003bf91  test    eax, eax
0x18003bf93  js      loc_18003C11C
0x18003bf99  mov     rcx, [rdi+38h]
0x18003bf9d  test    rcx, rcx
0x18003bfa0  jz      short loc_18003BFB3
0x18003bfa2  mov     [rdi+38h], r13
0x18003bfa6  mov     rax, [rcx]
0x18003bfa9  mov     rax, [rax+10h]
0x18003bfad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003bfb2  nop
0x18003bfb3  lea     r8, [rdi+38h]; struct ID2D1Image **
0x18003bfb7  mov     rdx, [rbp+57h+arg_18]; struct IWICBitmap *
0x18003bfbb  mov     rcx, rdi; this
0x18003bfbe  call    ?CreateD2DImageFromHDR10WICBitmap@HDRConverter@@AEAAJPEAUIWICBitmap@@PEAPEAUID2D1Image@@@Z; HDRConverter::CreateD2DImageFromHDR10WICBitmap(IWICBitmap *,ID2D1Image * *)
0x18003bfc3  mov     ebx, eax
0x18003bfc5  test    eax, eax
0x18003bfc7  js      loc_18003C11C
0x18003bfcd  mov     rbx, [rdi+28h]
0x18003bfd1  mov     rax, [rbx]
0x18003bfd4  mov     rsi, [rax+1D8h]
0x18003bfdb  mov     rcx, [rbp+57h+var_88]
0x18003bfdf  test    rcx, rcx
0x18003bfe2  jz      short loc_18003BFF5
0x18003bfe4  mov     [rbp+57h+var_88], r13
0x18003bfe8  mov     rax, [rcx]
0x18003bfeb  mov     rax, [rax+10h]
0x18003bfef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003bff4  nop
0x18003bff5  lea     rax, [rbp+57h+var_88]
0x18003bff9  mov     [rsp+0D0h+var_B0], rax
0x18003bffe  xor     r9d, r9d
0x18003c001  xor     r8d, r8d
0x18003c004  mov     edx, 2
0x18003c009  mov     rcx, rbx
0x18003c00c  mov     rax, rsi
0x18003c00f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c014  mov     ebx, eax
0x18003c016  test    eax, eax
0x18003c018  js      loc_18003C11C
0x18003c01e  mov     rax, 30000000Ah
0x18003c028  mov     [rbp+57h+var_68], rax
0x18003c02c  movsd   xmm0, [rbp+57h+var_78]
0x18003c031  cvtpd2ps xmm0, xmm0
0x18003c035  movss   [rbp+57h+var_60], xmm0
0x18003c03a  movsd   xmm1, [rbp+57h+var_70]
0x18003c03f  cvtpd2ps xmm1, xmm1
0x18003c043  movss   [rbp+57h+var_5C], xmm1
0x18003c048  mov     [rbp+57h+var_58], 1
0x18003c050  mov     rax, [rbp+57h+var_88]
0x18003c054  mov     [rbp+57h+var_50], rax
0x18003c058  mov     rbx, [rdi+28h]
0x18003c05c  lea     rsi, [rdi+40h]
0x18003c060  mov     rcx, [rsi]
0x18003c063  test    rcx, rcx
0x18003c066  jz      short loc_18003C078
0x18003c068  mov     [rsi], r13
0x18003c06b  mov     rax, [rcx]
0x18003c06e  mov     rax, [rax+10h]
0x18003c072  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c077  nop
0x18003c078  mov     rax, [rbx]
0x18003c07b  mov     [rsp+0D0h+var_A8], rsi
0x18003c080  lea     rcx, [rbp+57h+var_68]
0x18003c084  mov     [rsp+0D0h+var_B0], rcx
0x18003c089  xor     r9d, r9d
0x18003c08c  xor     r8d, r8d
0x18003c08f  mov     rdx, [rbp+57h+var_80]
0x18003c093  mov     rcx, rbx
0x18003c096  mov     rax, [rax+1C8h]
0x18003c09d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c0a2  mov     ebx, eax
0x18003c0a4  test    eax, eax
0x18003c0a6  js      short loc_18003C11C
0x18003c0a8  mov     dword ptr [rbp+57h+var_58], 6
0x18003c0af  mov     r14, [rdi+28h]
0x18003c0b3  lea     rbx, [rdi+48h]
0x18003c0b7  mov     rcx, [rbx]
0x18003c0ba  test    rcx, rcx
0x18003c0bd  jz      short loc_18003C0CF
0x18003c0bf  mov     [rbx], r13
0x18003c0c2  mov     rax, [rcx]
0x18003c0c5  mov     rax, [rax+10h]
0x18003c0c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c0ce  nop
0x18003c0cf  mov     rax, [r14]
0x18003c0d2  mov     [rsp+0D0h+var_A8], rbx
0x18003c0d7  lea     rcx, [rbp+57h+var_68]
0x18003c0db  mov     [rsp+0D0h+var_B0], rcx
0x18003c0e0  xor     r9d, r9d
0x18003c0e3  xor     r8d, r8d
0x18003c0e6  mov     rdx, [rbp+57h+var_80]
0x18003c0ea  mov     rcx, r14
0x18003c0ed  mov     rax, [rax+1C8h]
0x18003c0f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c0f9  mov     ebx, eax
0x18003c0fb  test    eax, eax
0x18003c0fd  js      short loc_18003C11C
0x18003c0ff  mov     rcx, [rdi+28h]
0x18003c103  mov     rax, [rcx]
0x18003c106  mov     rdx, [rsi]
0x18003c109  mov     rax, [rax+250h]
0x18003c110  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c115  jmp     short loc_18003C11C
0x18003c117  mov     ebx, 80070057h
0x18003c11c  mov     rcx, [rbp+57h+arg_18]
0x18003c120  test    rcx, rcx
0x18003c123  jz      short loc_18003C136
0x18003c125  mov     [rbp+57h+arg_18], r13
0x18003c129  mov     rax, [rcx]
0x18003c12c  mov     rax, [rax+10h]
0x18003c130  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c135  nop
0x18003c136  mov     rcx, [rbp+57h+var_90]
0x18003c13a  test    rcx, rcx
0x18003c13d  jz      short loc_18003C150
0x18003c13f  mov     [rbp+57h+var_90], r13
0x18003c143  mov     rax, [rcx]
0x18003c146  mov     rax, [rax+10h]
0x18003c14a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c14f  nop
0x18003c150  mov     rcx, [rbp+57h+var_88]
0x18003c154  test    rcx, rcx
0x18003c157  jz      short loc_18003C16A
0x18003c159  mov     [rbp+57h+var_88], r13
0x18003c15d  mov     rax, [rcx]
0x18003c160  mov     rax, [rax+10h]
0x18003c164  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c169  nop
0x18003c16a  mov     eax, ebx
0x18003c16c  add     rsp, 98h
0x18003c173  pop     r15
0x18003c175  pop     r14
0x18003c177  pop     r13
0x18003c179  pop     r12
0x18003c17b  pop     rdi
0x18003c17c  pop     rsi
0x18003c17d  pop     rbx
0x18003c17e  pop     rbp
0x18003c17f  retn
```
