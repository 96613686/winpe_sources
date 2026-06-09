# CWmpDecoderFrame::CopyPixels_Core(WICRect const *,uint,uint,_GUID *,WICBitmapTransformOptions,uint,uint,uchar *)

- ea: `0x180033ee0`
- end: `0x1800342cd`
- name: `?CopyPixels_Core@CWmpDecoderFrame@@MEAAJPEBUWICRect@@IIPEAU_GUID@@W4WICBitmapTransformOptions@@IIPEAE@Z`
- size: `1005`
- prototype: `__int64 __fastcall(CWmpDecoderFrame *this, __m128i *, unsigned int, unsigned int, struct _GUID *, enum WICBitmapTransformOptions, unsigned int, UINT, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `13`
- tags: ``

## callers

- `0x180031850`

## callees

- `0x18000ef30`
- `0x18000ffc0`
- `0x180028f18`
- `0x18002b160`
- `0x18002c7f0`
- `0x18002ddfc`
- `0x18002df00`
- `0x18002e8bc`
- `0x180032bb0`
- `0x180033ee0`
- `0x180036420`
- `0x180037174`
- `0x1800399a0`

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
  __int8 *v37; // [rsp+90h] [rbp-70h] BYREF
  _QWORD v38[13]; // [rsp+98h] [rbp-68h] BYREF

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
    ETWWrite(this, WMPHOTO_Decoder_DecoderFrameCopyPixelsCore_Start, 0, 0);
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
                        memset_0(v38, 0, sizeof(v38));
                        v38[0] = 4;
                        v37 = &v36.m128i_i8[8];
                        v38[2] = 4;
                        v38[1] = (char *)&v36.m128i_i64[1] + 4;
                        v38[4] = 4;
                        v38[3] = &v36;
                        v38[6] = 4;
                        v38[5] = (char *)v36.m128i_i64 + 4;
                        v38[7] = &v31;
                        v38[9] = &v30;
                        v38[11] = &v29;
                        v38[8] = 4;
                        v38[10] = 4;
                        v38[12] = 1;
                        ETWWrite(v25, WMPHOTO_Decoder_FrameParamsTransform_Info, 7, &v37);
                      }
                      ClosestSize = CWmpDecoderFrame::HrDecodeContentDirect(this, &v36, v31, v30, v29, v35);
                      if ( ClosestSize >= 0 )
                        ClosestSize = CWmpDecoderFrame::HrDecodeAlphaDirect(this, &v36, v31, v30, v29, v35);
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
    ETWWrite(v13, WMPHOTO_Decoder_DecoderFrameCopyPixelsCore_Stop, 0, 0);
  return (unsigned int)ClosestSize;
}

```

## disassembly

```asm
0x180033ee0  push    rbp
0x180033ee2  push    rbx
0x180033ee3  push    rsi
0x180033ee4  push    rdi
0x180033ee5  push    r12
0x180033ee7  push    r13
0x180033ee9  push    r14
0x180033eeb  push    r15
0x180033eed  lea     rbp, [rsp-18h]
0x180033ef2  sub     rsp, 118h
0x180033ef9  mov     rax, cs:__security_cookie
0x180033f00  xor     rax, rsp
0x180033f03  mov     [rbp+50h+var_50], rax
0x180033f07  mov     rax, [rbp+50h+arg_40]
0x180033f0e  xor     r13d, r13d
0x180033f11  cmp     cs:g_petwPro, r13
0x180033f18  mov     r12d, r8d
0x180033f1b  mov     esi, [rbp+50h+arg_30]
0x180033f21  mov     r15, rdx
0x180033f24  mov     r14d, r9d
0x180033f27  mov     rdi, rcx
0x180033f2a  mov     [rsp+150h+var_110], r8d
0x180033f2f  mov     [rsp+150h+var_118], r14d
0x180033f34  mov     [rsp+150h+puResult], r13d
0x180033f39  mov     [rsp+150h+var_F0], rax
0x180033f3e  mov     [rsp+150h+var_E8], r14
0x180033f43  mov     [rsp+150h+var_E0], rsi
0x180033f48  mov     qword ptr [rsp+150h+var_D8], r13
0x180033f4d  mov     dword ptr [rbp+50h+var_D8+8], r8d
0x180033f51  mov     dword ptr [rbp+50h+var_D8+0Ch], r14d
0x180033f55  mov     [rsp+150h+var_120], r13d
0x180033f5a  jz      short loc_180033F78
0x180033f5c  xor     r9d, r9d
0x180033f5f  lea     rdx, WMPHOTO_Decoder_DecoderFrameCopyPixelsCore_Start
0x180033f66  xor     r8d, r8d
0x180033f69  call    ETWWrite
0x180033f6e  mov     r12d, [rsp+150h+var_110]
0x180033f73  mov     r14d, [rsp+150h+var_118]
0x180033f78  mov     edx, 3; int
0x180033f7d  mov     rcx, rdi; this
0x180033f80  call    ?HrTestStateMinimum@CWmpCodecBase@@UEAAJH@Z; CWmpCodecBase::HrTestStateMinimum(int)
0x180033f85  mov     ebx, eax
0x180033f87  test    eax, eax
0x180033f89  js      loc_18003428F
0x180033f8f  test    r15, r15
0x180033f92  lea     rax, [rsp+150h+var_D8]
0x180033f97  cmovnz  rax, r15
0x180033f9b  movups  xmm1, xmmword ptr [rax]
0x180033f9e  movd    edx, xmm1
0x180033fa2  movups  [rsp+150h+var_D8], xmm1
0x180033fa7  test    edx, edx
0x180033fa9  js      loc_18003428A
0x180033faf  cmp     edx, [rdi+64h]
0x180033fb2  jnb     loc_18003428A
0x180033fb8  movq    rax, xmm1
0x180033fbd  shr     rax, 20h
0x180033fc1  test    eax, eax
0x180033fc3  js      loc_18003428A
0x180033fc9  cmp     eax, [rdi+68h]
0x180033fcc  jnb     loc_18003428A
0x180033fd2  movdqa  xmm0, xmm1
0x180033fd6  psrldq  xmm0, 8
0x180033fdb  movd    r8d, xmm0
0x180033fe0  test    r8d, r8d
0x180033fe3  jle     loc_18003428A
0x180033fe9  cmp     r8d, [rdi+64h]
0x180033fed  ja      loc_18003428A
0x180033ff3  psrldq  xmm1, 8
0x180033ff8  movq    rcx, xmm1
0x180033ffd  shr     rcx, 20h
0x180034001  test    ecx, ecx
0x180034003  jle     loc_18003428A
0x180034009  cmp     ecx, [rdi+68h]
0x18003400c  ja      loc_18003428A
0x180034012  lea     r9d, [r8+rdx]
0x180034016  cmp     r9d, edx
0x180034019  jb      loc_1800340FE
0x18003401f  lea     edx, [rax+rcx]
0x180034022  cmp     edx, eax
0x180034024  jb      loc_1800340FE
0x18003402a  cmp     r9d, [rdi+64h]
0x18003402e  ja      loc_18003428A
0x180034034  cmp     edx, [rdi+68h]
0x180034037  ja      loc_18003428A
0x18003403d  lea     rcx, [rdi+10318h]; this
0x180034044  mov     [rsp+150h+var_F8], r12d
0x180034049  lea     r8, [rsp+150h+var_100]; unsigned int *
0x18003404e  mov     [rsp+150h+var_100], r14d
0x180034053  lea     rdx, [rsp+150h+var_F8]; unsigned int *
0x180034058  call    ?GetClosestSize@CWmpDecoderFrame@@UEAAJPEAI0@Z; CWmpDecoderFrame::GetClosestSize(uint *,uint *)
0x18003405d  mov     ebx, eax
0x18003405f  test    eax, eax
0x180034061  js      loc_18003428F
0x180034067  mov     eax, [rsp+150h+var_110]
0x18003406b  cmp     [rsp+150h+var_F8], eax
0x18003406f  jnz     loc_18003428A
0x180034075  mov     eax, [rsp+150h+var_118]
0x180034079  cmp     [rsp+150h+var_100], eax
0x18003407d  jnz     loc_18003428A
0x180034083  mov     rcx, [rbp+50h+arg_20]
0x18003408a  lea     r10, [rdi+103ACh]
0x180034091  mov     rax, [r10]
0x180034094  cmp     rax, [rcx]
0x180034097  jnz     loc_18003428A
0x18003409d  mov     rax, [r10+8]
0x1800340a1  cmp     rax, [rcx+8]
0x1800340a5  jnz     loc_18003428A
0x1800340ab  mov     ecx, [rbp+50h+arg_28]; enum WICBitmapTransformOptions
0x1800340b1  lea     rdx, [rsp+150h+var_120]; enum ORIENTATION *
0x1800340b6  call    ?TransformWICToWMPhoto@@YAJW4WICBitmapTransformOptions@@PEAW4ORIENTATION@@@Z; TransformWICToWMPhoto(WICBitmapTransformOptions,ORIENTATION *)
0x1800340bb  mov     ebx, eax
0x1800340bd  test    eax, eax
0x1800340bf  js      loc_18003428F
0x1800340c5  mov     r14d, 4
0x1800340cb  mov     qword ptr [rsp+150h+var_100], r13
0x1800340d0  mov     rdx, r10; struct _GUID *
0x1800340d3  mov     rcx, rdi; this
0x1800340d6  cmp     [rsp+150h+var_120], r14d
0x1800340db  jge     loc_18003425A
0x1800340e1  movsxd  r9, dword ptr [rbp+50h+var_D8+8]
0x1800340e5  call    ?GetPixelSize@CWmpDecoderFrame@@IEBA_KAEBU_GUID@@@Z; CWmpDecoderFrame::GetPixelSize(_GUID const &)
0x1800340ea  mov     rcx, rax
0x1800340ed  lea     r8, [rsp+150h+var_100]
0x1800340f2  mov     rdx, r9
0x1800340f5  call    Bit2ByteSafe
0x1800340fa  test    eax, eax
0x1800340fc  jz      short loc_180034108
0x1800340fe  mov     ebx, 80070216h
0x180034103  jmp     loc_18003428F
0x180034108  cmp     qword ptr [rsp+150h+var_100], rsi
0x18003410d  ja      loc_18003428A
0x180034113  mov     ecx, dword ptr [rbp+50h+var_D8+0Ch]
0x180034116  imul    rcx, rsi; ullOperand
0x18003411a  lea     rdx, [rsp+150h+puResult]; puResult
0x18003411f  call    ULongLongToUInt
0x180034124  mov     ebx, 80070216h
0x180034129  cmp     eax, ebx
0x18003412b  jz      loc_18003428F
0x180034131  mov     eax, [rbp+50h+arg_38]
0x180034137  cmp     [rsp+150h+puResult], eax
0x18003413b  ja      loc_18003428A
0x180034141  mov     ecx, [rdi+10380h]
0x180034147  lea     rax, [rsp+150h+var_120]
0x18003414c  lea     r9, [rsp+150h+var_118]
0x180034151  mov     [rsp+150h+var_130], rax
0x180034156  lea     r8, [rsp+150h+var_110]
0x18003415b  lea     rdx, [rsp+150h+var_D8]
0x180034160  call    ?TransformConsolidate@@YAJW4ORIENTATION@@PEAUWICRect@@PEAI2PEAW41@@Z; TransformConsolidate(ORIENTATION,WICRect *,uint *,uint *,ORIENTATION *)
0x180034165  mov     ebx, eax
0x180034167  test    eax, eax
0x180034169  js      loc_18003428F
0x18003416f  cmp     cs:g_petwPro, r13
0x180034176  jz      loc_1800341FE
0x18003417c  xor     edx, edx; Val
0x18003417e  lea     rcx, [rbp+50h+var_B8]; void *
0x180034182  lea     r8d, [rdx+68h]; Size
0x180034186  call    memset_0
0x18003418b  lea     rax, [rbp+50h+var_D8+8]
0x18003418f  mov     [rbp+50h+var_B8], r14
0x180034193  mov     [rbp+50h+var_C0], rax
0x180034197  lea     r9, [rbp+50h+var_C0]
0x18003419b  lea     rax, [rbp+50h+var_D8+0Ch]
0x18003419f  mov     [rbp+50h+var_A8], r14
0x1800341a3  mov     [rbp+50h+var_B0], rax
0x1800341a7  lea     rdx, WMPHOTO_Decoder_FrameParamsTransform_Info
0x1800341ae  lea     rax, [rsp+150h+var_D8]
0x1800341b3  mov     [rbp+50h+var_98], r14
0x1800341b7  mov     [rbp+50h+var_A0], rax
0x1800341bb  mov     r8d, 7
0x1800341c1  lea     rax, [rsp+150h+var_D8+4]
0x1800341c6  mov     [rbp+50h+var_88], r14
0x1800341ca  mov     [rbp+50h+var_90], rax
0x1800341ce  lea     rax, [rsp+150h+var_110]
0x1800341d3  mov     [rbp+50h+var_80], rax
0x1800341d7  lea     rax, [rsp+150h+var_118]
0x1800341dc  mov     [rbp+50h+var_70], rax
0x1800341e0  lea     rax, [rsp+150h+var_120]
0x1800341e5  mov     [rbp+50h+var_60], rax
0x1800341e9  mov     [rbp+50h+var_78], r14
0x1800341ed  mov     [rbp+50h+var_68], r14
0x1800341f1  mov     [rbp+50h+var_58], 1
0x1800341f9  call    ETWWrite
0x1800341fe  mov     r9d, [rsp+150h+var_118]
0x180034203  lea     rax, [rsp+150h+var_F0]
0x180034208  mov     r8d, [rsp+150h+var_110]
0x18003420d  lea     rdx, [rsp+150h+var_D8]
0x180034212  mov     [rsp+150h+var_128], rax
0x180034217  mov     rcx, rdi
0x18003421a  mov     eax, [rsp+150h+var_120]
0x18003421e  mov     dword ptr [rsp+150h+var_130], eax
0x180034222  call    ?HrDecodeContentDirect@CWmpDecoderFrame@@MEAAJPEBUWICRect@@IIW4ORIENTATION@@PEBUtagCWMImageBufferInfo@@@Z; CWmpDecoderFrame::HrDecodeContentDirect(WICRect const *,uint,uint,ORIENTATION,tagCWMImageBufferInfo const *)
0x180034227  mov     ebx, eax
0x180034229  test    eax, eax
0x18003422b  js      short loc_18003428F
0x18003422d  mov     r9d, [rsp+150h+var_118]
0x180034232  lea     rax, [rsp+150h+var_F0]
0x180034237  mov     r8d, [rsp+150h+var_110]
0x18003423c  lea     rdx, [rsp+150h+var_D8]
0x180034241  mov     [rsp+150h+var_128], rax
0x180034246  mov     rcx, rdi
0x180034249  mov     eax, [rsp+150h+var_120]
0x18003424d  mov     dword ptr [rsp+150h+var_130], eax
0x180034251  call    ?HrDecodeAlphaDirect@CWmpDecoderFrame@@MEAAJPEBUWICRect@@IIW4ORIENTATION@@PEBUtagCWMImageBufferInfo@@@Z; CWmpDecoderFrame::HrDecodeAlphaDirect(WICRect const *,uint,uint,ORIENTATION,tagCWMImageBufferInfo const *)
0x180034256  mov     ebx, eax
0x180034258  jmp     short loc_18003428F
0x18003425a  movsxd  r9, dword ptr [rbp+50h+var_D8+0Ch]
0x18003425e  call    ?GetPixelSize@CWmpDecoderFrame@@IEBA_KAEBU_GUID@@@Z; CWmpDecoderFrame::GetPixelSize(_GUID const &)
0x180034263  mov     rcx, rax
0x180034266  lea     r8, [rsp+150h+var_100]
0x18003426b  mov     rdx, r9
0x18003426e  call    Bit2ByteSafe
0x180034273  test    eax, eax
0x180034275  jnz     loc_1800340FE
0x18003427b  cmp     qword ptr [rsp+150h+var_100], rsi
0x180034280  ja      short loc_18003428A
0x180034282  mov     ecx, dword ptr [rbp+50h+var_D8+8]
0x180034285  jmp     loc_180034116
0x18003428a  mov     ebx, 80070057h
0x18003428f  cmp     cs:g_petwPro, r13
0x180034296  jz      short loc_1800342AA
0x180034298  xor     r9d, r9d
0x18003429b  lea     rdx, WMPHOTO_Decoder_DecoderFrameCopyPixelsCore_Stop
0x1800342a2  xor     r8d, r8d
0x1800342a5  call    ETWWrite
0x1800342aa  mov     eax, ebx
0x1800342ac  mov     rcx, [rbp+50h+var_50]
0x1800342b0  xor     rcx, rsp; StackCookie
0x1800342b3  call    __security_check_cookie
0x1800342b8  add     rsp, 118h
0x1800342bf  pop     r15
0x1800342c1  pop     r14
0x1800342c3  pop     r13
0x1800342c5  pop     r12
0x1800342c7  pop     rdi
0x1800342c8  pop     rsi
0x1800342c9  pop     rbx
0x1800342ca  pop     rbp
0x1800342cb  retn
```
