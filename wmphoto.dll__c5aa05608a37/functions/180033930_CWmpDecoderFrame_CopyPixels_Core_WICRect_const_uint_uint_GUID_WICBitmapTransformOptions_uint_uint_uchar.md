# CWmpDecoderFrame::CopyPixels_Core(WICRect const *,uint,uint,_GUID *,WICBitmapTransformOptions,uint,uint,uchar *)

- ea: `0x180033930`
- end: `0x180033d1c`
- name: `?CopyPixels_Core@CWmpDecoderFrame@@MEAAJPEBUWICRect@@IIPEAU_GUID@@W4WICBitmapTransformOptions@@IIPEAE@Z`
- size: `1004`
- prototype: `__int64 __fastcall(CWmpDecoderFrame *this, __m128i *, unsigned int, unsigned int, struct _GUID *, enum WICBitmapTransformOptions, unsigned int, UINT, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `13`
- tags: ``

## callers

- `0x1800314f0`

## callees

- `0x18000ee00`
- `0x18000fe30`
- `0x180028430`
- `0x180028870`
- `0x180028e94`
- `0x18002c560`
- `0x18002db00`
- `0x18002de74`
- `0x18002e56c`
- `0x180033930`
- `0x180035e50`
- `0x180036ba4`
- `0x1800392b0`

## pseudocode

```c
__int64 __fastcall CWmpDecoderFrame::CopyPixels_Core(
        CWmpDecoderFrame *this,
        __m128i *a2,
        unsigned int a3,
        unsigned int a4,
        struct _GUID *a5,
        enum WICBitmapTransformOptions a6,
        unsigned int a7,
        UINT a8,
        unsigned __int8 *a9)
{
  unsigned int v9; // r12d
  unsigned int v11; // r14d
  struct _GUID *v13; // rcx
  int ClosestSize; // ebx
  __m128i *v15; // rax
  __m128i v16; // xmm1
  int v17; // edx
  unsigned __int64 v18; // rax
  int v19; // r8d
  unsigned __int64 v20; // xmm1_8
  const struct _GUID *v21; // r10
  unsigned __int64 v22; // rax
  __int64 v23; // r9
  __int64 v24; // rcx
  __int64 v25; // rcx
  unsigned __int64 PixelSize; // rax
  __int64 v27; // r9
  int v29; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int v30; // [rsp+38h] [rbp-C8h] BYREF
  unsigned int v31; // [rsp+40h] [rbp-C0h] BYREF
  UINT puResult; // [rsp+48h] [rbp-B8h] BYREF
  unsigned int v33[2]; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v34; // [rsp+58h] [rbp-A8h] BYREF
  _QWORD v35[3]; // [rsp+60h] [rbp-A0h] BYREF
  __m128i v36; // [rsp+78h] [rbp-88h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v37; // [rsp+90h] [rbp-70h] BYREF
  __int8 *v38; // [rsp+A0h] [rbp-60h]
  __int64 v39; // [rsp+A8h] [rbp-58h]
  __m128i *v40; // [rsp+B0h] [rbp-50h]
  __int64 v41; // [rsp+B8h] [rbp-48h]
  __int8 *v42; // [rsp+C0h] [rbp-40h]
  __int64 v43; // [rsp+C8h] [rbp-38h]
  unsigned int *v44; // [rsp+D0h] [rbp-30h]
  __int64 v45; // [rsp+D8h] [rbp-28h]
  unsigned int *v46; // [rsp+E0h] [rbp-20h]
  __int64 v47; // [rsp+E8h] [rbp-18h]
  int *v48; // [rsp+F0h] [rbp-10h]
  __int64 v49; // [rsp+F8h] [rbp-8h]

  v9 = a3;
  v11 = a4;
  v31 = a3;
  v30 = a4;
  puResult = 0;
  v35[0] = a9;
  v35[1] = a4;
  v35[2] = a7;
  v36.m128i_i64[0] = 0;
  v36.m128i_i64[1] = __PAIR64__(a4, a3);
  v29 = 0;
  if ( g_petwPro )
  {
    ETWWrite((__int64)this, &WMPHOTO_Decoder_DecoderFrameCopyPixelsCore_Start, 0, 0);
    v9 = v31;
    v11 = v30;
  }
  ClosestSize = CWmpCodecBase::HrTestStateMinimum(this, 3);
  if ( ClosestSize >= 0 )
  {
    v15 = &v36;
    if ( a2 )
      v15 = a2;
    v16 = *v15;
    v17 = _mm_cvtsi128_si32(*v15);
    v36 = *v15;
    if ( v17 >= 0 && (unsigned int)v17 < *((_DWORD *)this + 25) )
    {
      v18 = HIDWORD(v16.m128i_i64[0]);
      if ( v16.m128i_i32[1] >= 0 && v16.m128i_i32[1] < *((_DWORD *)this + 26) )
      {
        v19 = _mm_cvtsi128_si32(_mm_srli_si128(v16, 8));
        if ( v19 > 0 && (unsigned int)v19 <= *((_DWORD *)this + 25) )
        {
          v20 = _mm_srli_si128(v16, 8).m128i_u64[0];
          v13 = (struct _GUID *)HIDWORD(v20);
          if ( SHIDWORD(v20) > 0 && HIDWORD(v20) <= *((_DWORD *)this + 26) )
          {
            if ( v19 + v17 < (unsigned int)v17 || (int)v18 + HIDWORD(v20) < (unsigned int)v18 )
              goto LABEL_26;
            if ( (unsigned int)(v19 + v17) <= *((_DWORD *)this + 25)
              && (unsigned int)(v18 + HIDWORD(v20)) <= *((_DWORD *)this + 26) )
            {
              v34 = v9;
              v33[0] = v11;
              ClosestSize = CWmpDecoderFrame::GetClosestSize((CWmpDecoderFrame *)((char *)this + 66328), &v34, v33);
              if ( ClosestSize < 0 )
                goto LABEL_40;
              if ( v34 == v31 && v33[0] == v30 )
              {
                v13 = a5;
                if ( *(_QWORD *)((char *)this + 66476) == *(_QWORD *)&a5->Data1
                  && *(_QWORD *)((char *)this + 66484) == *(_QWORD *)a5->Data4 )
                {
                  ClosestSize = TransformWICToWMPhoto(a6, (enum ORIENTATION *)&v29);
                  if ( ClosestSize < 0 )
                    goto LABEL_40;
                  *(_QWORD *)v33 = 0;
                  if ( v29 >= 4 )
                  {
                    PixelSize = CWmpDecoderFrame::GetPixelSize(this, v21);
                    if ( (unsigned int)Bit2ByteSafe(PixelSize, v27, v33) )
                      goto LABEL_26;
                    if ( *(_QWORD *)v33 > (unsigned __int64)a7 )
                      goto LABEL_39;
                    v24 = v36.m128i_u32[2];
                  }
                  else
                  {
                    v22 = CWmpDecoderFrame::GetPixelSize(this, v21);
                    if ( (unsigned int)Bit2ByteSafe(v22, v23, v33) )
                    {
LABEL_26:
                      ClosestSize = -2147024362;
                      goto LABEL_40;
                    }
                    if ( *(_QWORD *)v33 > (unsigned __int64)a7 )
                      goto LABEL_39;
                    v24 = v36.m128i_u32[3];
                  }
                  ClosestSize = -2147024362;
                  if ( ULongLongToUInt(a7 * v24, &puResult) == -2147024362 )
                    goto LABEL_40;
                  if ( puResult <= a8 )
                  {
                    ClosestSize = TransformConsolidate(*((unsigned int *)this + 16608), &v36, &v31, &v30, &v29);
                    if ( ClosestSize >= 0 )
                    {
                      if ( g_petwPro )
                      {
                        memset_0(&v37.Size, 0, 0x68u);
                        *(_QWORD *)&v37.Size = 4;
                        v37.Ptr = (ULONGLONG)&v36.m128i_u64[1];
                        v39 = 4;
                        v38 = &v36.m128i_i8[12];
                        v41 = 4;
                        v40 = &v36;
                        v43 = 4;
                        v42 = &v36.m128i_i8[4];
                        v44 = &v31;
                        v46 = &v30;
                        v48 = &v29;
                        v45 = 4;
                        v47 = 4;
                        v49 = 1;
                        ETWWrite(v25, &WMPHOTO_Decoder_FrameParamsTransform_Info, 7u, &v37);
                      }
                      ClosestSize = CWmpDecoderFrame::HrDecodeContentDirect(
                                      (__int64)this,
                                      v36.m128i_i32,
                                      v31,
                                      v30,
                                      v29,
                                      v35);
                      if ( ClosestSize >= 0 )
                        ClosestSize = CWmpDecoderFrame::HrDecodeAlphaDirect(
                                        (__int64)this,
                                        v36.m128i_i32,
                                        v31,
                                        v30,
                                        v29,
                                        v35);
                    }
                    goto LABEL_40;
                  }
                }
              }
            }
          }
        }
      }
    }
LABEL_39:
    ClosestSize = -2147024809;
  }
LABEL_40:
  if ( g_petwPro )
    ETWWrite((__int64)v13, &WMPHOTO_Decoder_DecoderFrameCopyPixelsCore_Stop, 0, 0);
  return (unsigned int)ClosestSize;
}

```

## disassembly

```asm
0x180033930  push    rbp
0x180033932  push    rbx
0x180033933  push    rsi
0x180033934  push    rdi
0x180033935  push    r12
0x180033937  push    r13
0x180033939  push    r14
0x18003393b  push    r15
0x18003393d  lea     rbp, [rsp-18h]
0x180033942  sub     rsp, 118h
0x180033949  mov     rax, cs:__security_cookie
0x180033950  xor     rax, rsp
0x180033953  mov     [rbp+50h+var_50], rax
0x180033957  mov     rax, [rbp+50h+arg_40]
0x18003395e  xor     r13d, r13d
0x180033961  cmp     cs:g_petwPro, r13
0x180033968  mov     r12d, r8d
0x18003396b  mov     esi, [rbp+50h+arg_30]
0x180033971  mov     r15, rdx
0x180033974  mov     r14d, r9d
0x180033977  mov     rdi, rcx
0x18003397a  mov     [rsp+150h+var_110], r8d
0x18003397f  mov     [rsp+150h+var_118], r14d
0x180033984  mov     [rsp+150h+puResult], r13d
0x180033989  mov     [rsp+150h+var_F0], rax
0x18003398e  mov     [rsp+150h+var_E8], r14
0x180033993  mov     [rsp+150h+var_E0], rsi
0x180033998  mov     qword ptr [rsp+150h+var_D8], r13
0x18003399d  mov     dword ptr [rbp+50h+var_D8+8], r8d
0x1800339a1  mov     dword ptr [rbp+50h+var_D8+0Ch], r14d
0x1800339a5  mov     [rsp+150h+var_120], r13d
0x1800339aa  jz      short loc_1800339C8
0x1800339ac  xor     r9d, r9d
0x1800339af  lea     rdx, WMPHOTO_Decoder_DecoderFrameCopyPixelsCore_Start
0x1800339b6  xor     r8d, r8d
0x1800339b9  call    ETWWrite
0x1800339be  mov     r12d, [rsp+150h+var_110]
0x1800339c3  mov     r14d, [rsp+150h+var_118]
0x1800339c8  mov     edx, 3; int
0x1800339cd  mov     rcx, rdi; this
0x1800339d0  call    ?HrTestStateMinimum@CWmpCodecBase@@UEAAJH@Z; CWmpCodecBase::HrTestStateMinimum(int)
0x1800339d5  mov     ebx, eax
0x1800339d7  test    eax, eax
0x1800339d9  js      loc_180033CDF
0x1800339df  test    r15, r15
0x1800339e2  lea     rax, [rsp+150h+var_D8]
0x1800339e7  cmovnz  rax, r15
0x1800339eb  movups  xmm1, xmmword ptr [rax]
0x1800339ee  movd    edx, xmm1
0x1800339f2  movups  [rsp+150h+var_D8], xmm1
0x1800339f7  test    edx, edx
0x1800339f9  js      loc_180033CDA
0x1800339ff  cmp     edx, [rdi+64h]
0x180033a02  jnb     loc_180033CDA
0x180033a08  movq    rax, xmm1
0x180033a0d  shr     rax, 20h
0x180033a11  test    eax, eax
0x180033a13  js      loc_180033CDA
0x180033a19  cmp     eax, [rdi+68h]
0x180033a1c  jnb     loc_180033CDA
0x180033a22  movdqa  xmm0, xmm1
0x180033a26  psrldq  xmm0, 8
0x180033a2b  movd    r8d, xmm0
0x180033a30  test    r8d, r8d
0x180033a33  jle     loc_180033CDA
0x180033a39  cmp     r8d, [rdi+64h]
0x180033a3d  ja      loc_180033CDA
0x180033a43  psrldq  xmm1, 8
0x180033a48  movq    rcx, xmm1
0x180033a4d  shr     rcx, 20h
0x180033a51  test    ecx, ecx
0x180033a53  jle     loc_180033CDA
0x180033a59  cmp     ecx, [rdi+68h]
0x180033a5c  ja      loc_180033CDA
0x180033a62  lea     r9d, [r8+rdx]
0x180033a66  cmp     r9d, edx
0x180033a69  jb      loc_180033B4E
0x180033a6f  lea     edx, [rax+rcx]
0x180033a72  cmp     edx, eax
0x180033a74  jb      loc_180033B4E
0x180033a7a  cmp     r9d, [rdi+64h]
0x180033a7e  ja      loc_180033CDA
0x180033a84  cmp     edx, [rdi+68h]
0x180033a87  ja      loc_180033CDA
0x180033a8d  lea     rcx, [rdi+10318h]; this
0x180033a94  mov     [rsp+150h+var_F8], r12d
0x180033a99  lea     r8, [rsp+150h+var_100]; unsigned int *
0x180033a9e  mov     [rsp+150h+var_100], r14d
0x180033aa3  lea     rdx, [rsp+150h+var_F8]; unsigned int *
0x180033aa8  call    ?GetClosestSize@CWmpDecoderFrame@@UEAAJPEAI0@Z; CWmpDecoderFrame::GetClosestSize(uint *,uint *)
0x180033aad  mov     ebx, eax
0x180033aaf  test    eax, eax
0x180033ab1  js      loc_180033CDF
0x180033ab7  mov     eax, [rsp+150h+var_110]
0x180033abb  cmp     [rsp+150h+var_F8], eax
0x180033abf  jnz     loc_180033CDA
0x180033ac5  mov     eax, [rsp+150h+var_118]
0x180033ac9  cmp     [rsp+150h+var_100], eax
0x180033acd  jnz     loc_180033CDA
0x180033ad3  mov     rcx, [rbp+50h+arg_20]
0x180033ada  lea     r10, [rdi+103ACh]
0x180033ae1  mov     rax, [r10]
0x180033ae4  cmp     rax, [rcx]
0x180033ae7  jnz     loc_180033CDA
0x180033aed  mov     rax, [r10+8]
0x180033af1  cmp     rax, [rcx+8]
0x180033af5  jnz     loc_180033CDA
0x180033afb  mov     ecx, [rbp+50h+arg_28]; enum WICBitmapTransformOptions
0x180033b01  lea     rdx, [rsp+150h+var_120]; enum ORIENTATION *
0x180033b06  call    ?TransformWICToWMPhoto@@YAJW4WICBitmapTransformOptions@@PEAW4ORIENTATION@@@Z; TransformWICToWMPhoto(WICBitmapTransformOptions,ORIENTATION *)
0x180033b0b  mov     ebx, eax
0x180033b0d  test    eax, eax
0x180033b0f  js      loc_180033CDF
0x180033b15  mov     r14d, 4
0x180033b1b  mov     qword ptr [rsp+150h+var_100], r13
0x180033b20  mov     rdx, r10; struct _GUID *
0x180033b23  mov     rcx, rdi; this
0x180033b26  cmp     [rsp+150h+var_120], r14d
0x180033b2b  jge     loc_180033CAA
0x180033b31  movsxd  r9, dword ptr [rbp+50h+var_D8+8]
0x180033b35  call    ?GetPixelSize@CWmpDecoderFrame@@IEBA_KAEBU_GUID@@@Z; CWmpDecoderFrame::GetPixelSize(_GUID const &)
0x180033b3a  mov     rcx, rax
0x180033b3d  lea     r8, [rsp+150h+var_100]
0x180033b42  mov     rdx, r9
0x180033b45  call    Bit2ByteSafe
0x180033b4a  test    eax, eax
0x180033b4c  jz      short loc_180033B58
0x180033b4e  mov     ebx, 80070216h
0x180033b53  jmp     loc_180033CDF
0x180033b58  cmp     qword ptr [rsp+150h+var_100], rsi
0x180033b5d  ja      loc_180033CDA
0x180033b63  mov     ecx, dword ptr [rbp+50h+var_D8+0Ch]
0x180033b66  imul    rcx, rsi; ullOperand
0x180033b6a  lea     rdx, [rsp+150h+puResult]; puResult
0x180033b6f  call    ULongLongToUInt
0x180033b74  mov     ebx, 80070216h
0x180033b79  cmp     eax, ebx
0x180033b7b  jz      loc_180033CDF
0x180033b81  mov     eax, [rbp+50h+arg_38]
0x180033b87  cmp     [rsp+150h+puResult], eax
0x180033b8b  ja      loc_180033CDA
0x180033b91  mov     ecx, [rdi+10380h]
0x180033b97  lea     rax, [rsp+150h+var_120]
0x180033b9c  lea     r9, [rsp+150h+var_118]
0x180033ba1  mov     [rsp+150h+var_130], rax
0x180033ba6  lea     r8, [rsp+150h+var_110]
0x180033bab  lea     rdx, [rsp+150h+var_D8]
0x180033bb0  call    ?TransformConsolidate@@YAJW4ORIENTATION@@PEAUWICRect@@PEAI2PEAW41@@Z; TransformConsolidate(ORIENTATION,WICRect *,uint *,uint *,ORIENTATION *)
0x180033bb5  mov     ebx, eax
0x180033bb7  test    eax, eax
0x180033bb9  js      loc_180033CDF
0x180033bbf  cmp     cs:g_petwPro, r13
0x180033bc6  jz      loc_180033C4E
0x180033bcc  xor     edx, edx; Val
0x180033bce  lea     rcx, [rbp+50h+var_B8]; void *
0x180033bd2  lea     r8d, [rdx+68h]; Size
0x180033bd6  call    memset_0
0x180033bdb  lea     rax, [rbp+50h+var_D8+8]
0x180033bdf  mov     [rbp+50h+var_B8], r14
0x180033be3  mov     [rbp+50h+var_C0], rax
0x180033be7  lea     r9, [rbp+50h+var_C0]
0x180033beb  lea     rax, [rbp+50h+var_D8+0Ch]
0x180033bef  mov     [rbp+50h+var_A8], r14
0x180033bf3  mov     [rbp+50h+var_B0], rax
0x180033bf7  lea     rdx, WMPHOTO_Decoder_FrameParamsTransform_Info
0x180033bfe  lea     rax, [rsp+150h+var_D8]
0x180033c03  mov     [rbp+50h+var_98], r14
0x180033c07  mov     [rbp+50h+var_A0], rax
0x180033c0b  mov     r8d, 7
0x180033c11  lea     rax, [rsp+150h+var_D8+4]
0x180033c16  mov     [rbp+50h+var_88], r14
0x180033c1a  mov     [rbp+50h+var_90], rax
0x180033c1e  lea     rax, [rsp+150h+var_110]
0x180033c23  mov     [rbp+50h+var_80], rax
0x180033c27  lea     rax, [rsp+150h+var_118]
0x180033c2c  mov     [rbp+50h+var_70], rax
0x180033c30  lea     rax, [rsp+150h+var_120]
0x180033c35  mov     [rbp+50h+var_60], rax
0x180033c39  mov     [rbp+50h+var_78], r14
0x180033c3d  mov     [rbp+50h+var_68], r14
0x180033c41  mov     [rbp+50h+var_58], 1
0x180033c49  call    ETWWrite
0x180033c4e  mov     r9d, [rsp+150h+var_118]
0x180033c53  lea     rax, [rsp+150h+var_F0]
0x180033c58  mov     r8d, [rsp+150h+var_110]
0x180033c5d  lea     rdx, [rsp+150h+var_D8]
0x180033c62  mov     [rsp+150h+var_128], rax
0x180033c67  mov     rcx, rdi
0x180033c6a  mov     eax, [rsp+150h+var_120]
0x180033c6e  mov     dword ptr [rsp+150h+var_130], eax
0x180033c72  call    ?HrDecodeContentDirect@CWmpDecoderFrame@@MEAAJPEBUWICRect@@IIW4ORIENTATION@@PEBUtagCWMImageBufferInfo@@@Z; CWmpDecoderFrame::HrDecodeContentDirect(WICRect const *,uint,uint,ORIENTATION,tagCWMImageBufferInfo const *)
0x180033c77  mov     ebx, eax
0x180033c79  test    eax, eax
0x180033c7b  js      short loc_180033CDF
0x180033c7d  mov     r9d, [rsp+150h+var_118]
0x180033c82  lea     rax, [rsp+150h+var_F0]
0x180033c87  mov     r8d, [rsp+150h+var_110]
0x180033c8c  lea     rdx, [rsp+150h+var_D8]
0x180033c91  mov     [rsp+150h+var_128], rax
0x180033c96  mov     rcx, rdi
0x180033c99  mov     eax, [rsp+150h+var_120]
0x180033c9d  mov     dword ptr [rsp+150h+var_130], eax
0x180033ca1  call    ?HrDecodeAlphaDirect@CWmpDecoderFrame@@MEAAJPEBUWICRect@@IIW4ORIENTATION@@PEBUtagCWMImageBufferInfo@@@Z; CWmpDecoderFrame::HrDecodeAlphaDirect(WICRect const *,uint,uint,ORIENTATION,tagCWMImageBufferInfo const *)
0x180033ca6  mov     ebx, eax
0x180033ca8  jmp     short loc_180033CDF
0x180033caa  movsxd  r9, dword ptr [rbp+50h+var_D8+0Ch]
0x180033cae  call    ?GetPixelSize@CWmpDecoderFrame@@IEBA_KAEBU_GUID@@@Z; CWmpDecoderFrame::GetPixelSize(_GUID const &)
0x180033cb3  mov     rcx, rax
0x180033cb6  lea     r8, [rsp+150h+var_100]
0x180033cbb  mov     rdx, r9
0x180033cbe  call    Bit2ByteSafe
0x180033cc3  test    eax, eax
0x180033cc5  jnz     loc_180033B4E
0x180033ccb  cmp     qword ptr [rsp+150h+var_100], rsi
0x180033cd0  ja      short loc_180033CDA
0x180033cd2  mov     ecx, dword ptr [rbp+50h+var_D8+8]
0x180033cd5  jmp     loc_180033B66
0x180033cda  mov     ebx, 80070057h
0x180033cdf  cmp     cs:g_petwPro, r13
0x180033ce6  jz      short loc_180033CFA
0x180033ce8  xor     r9d, r9d
0x180033ceb  lea     rdx, WMPHOTO_Decoder_DecoderFrameCopyPixelsCore_Stop
0x180033cf2  xor     r8d, r8d
0x180033cf5  call    ETWWrite
0x180033cfa  mov     eax, ebx
0x180033cfc  mov     rcx, [rbp+50h+var_50]
0x180033d00  xor     rcx, rsp; StackCookie
0x180033d03  call    __security_check_cookie
0x180033d08  add     rsp, 118h
0x180033d0f  pop     r15
0x180033d11  pop     r14
0x180033d13  pop     r13
0x180033d15  pop     r12
0x180033d17  pop     rdi
0x180033d18  pop     rsi
0x180033d19  pop     rbx
0x180033d1a  pop     rbp
0x180033d1b  retn
```
