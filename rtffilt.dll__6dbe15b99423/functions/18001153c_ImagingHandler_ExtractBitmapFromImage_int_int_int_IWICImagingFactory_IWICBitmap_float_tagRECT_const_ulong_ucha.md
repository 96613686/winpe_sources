# ImagingHandler::ExtractBitmapFromImage(int,int,int,IWICImagingFactory *,IWICBitmap *,float,tagRECT const *,ulong,uchar *)

- ea: `0x18001153c`
- end: `0x18001198d`
- name: `?ExtractBitmapFromImage@ImagingHandler@@SAJHHHPEAUIWICImagingFactory@@PEAUIWICBitmap@@MPEBUtagRECT@@KPEAE@Z`
- size: `1105`
- prototype: `__int64 __fastcall(int, __int32, int, const wchar_t *, struct IWICBitmap *, float, const struct tagRECT *, unsigned int, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180013f00`

## callees

- `0x180001e40`
- `0x18000a844`
- `0x180011384`
- `0x18001153c`
- `0x180015148`
- `0x180015604`
- `0x180015644`
- `0x180018f38`
- `0x18001b010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_roundf` at `0x1800115e0`
- `api-ms-win-crt-private-l1-1-0!_o_roundf` at `0x1800115f6`
- `api-ms-win-crt-private-l1-1-0!_o_roundf` at `0x1800115e0`
- `api-ms-win-crt-private-l1-1-0!_o_roundf` at `0x1800115f6`

## string_xrefs

- `0x180011954`: `onecoreuap\base\appmodel\Search\filters\common\imageprocessing\imagingHandler.h`
- `0x18001171e`: `onecoreuap\base\appmodel\Search\filters\common\imageprocessing\imagingHandler.h`
- `0x180011784`: `onecoreuap\base\appmodel\Search\filters\common\imageprocessing\imagingHandler.h`
- `0x1800117c8`: `onecoreuap\base\appmodel\Search\filters\common\imageprocessing\imagingHandler.h`
- `0x180011884`: `onecoreuap\base\appmodel\Search\filters\common\imageprocessing\imagingHandler.h`
- `0x180011935`: `onecoreuap\base\appmodel\Search\filters\common\imageprocessing\imagingHandler.h`

## pseudocode

```c
__int64 __fastcall ImagingHandler::ExtractBitmapFromImage(
        int a1,
        __int32 a2,
        int a3,
        const wchar_t *a4,
        struct IWICBitmap *a5,
        float a6,
        const struct tagRECT *a7,
        unsigned int a8,
        unsigned __int8 *a9)
{
  __int32 v10; // r13d
  __int32 v11; // r12d
  struct IWICBitmap *v12; // r15
  LONG left; // r8d
  LONG top; // r9d
  float v15; // xmm6_4
  float v16; // xmm0_4
  unsigned int v17; // ebx
  int v18; // r14d
  int v19; // esi
  float v20; // xmm6_4
  char Variant; // al
  int v22; // eax
  int v23; // edi
  bool v24; // zf
  int v26; // eax
  const wchar_t *v27; // r12
  __int64 v28; // rdx
  int v29; // eax
  __int64 v30; // r8
  int v31; // [rsp+28h] [rbp-81h]
  __int64 v32; // [rsp+38h] [rbp-71h] BYREF
  __int64 v33; // [rsp+40h] [rbp-69h] BYREF
  struct IWICBitmap *v34; // [rsp+48h] [rbp-61h] BYREF
  int v35; // [rsp+50h] [rbp-59h]
  const wchar_t *v36; // [rsp+58h] [rbp-51h]
  unsigned __int8 *v37; // [rsp+60h] [rbp-49h]
  __m128i v38; // [rsp+68h] [rbp-41h] BYREF
  __m128i v39; // [rsp+78h] [rbp-31h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+F0h] [rbp+47h]

  v36 = a4;
  v35 = a3;
  v10 = a2;
  v11 = a1;
  v12 = a5;
  v37 = a9;
  if ( !a8 || !a9 )
  {
    SearchIndexerTrace::Error(
      (wchar_t *)L"onecoreuap\\base\\appmodel\\Search\\filters\\common\\imageprocessing\\imagingHandler.h",
      (const wchar_t *)0x96,
      (unsigned int)L"ImagingHandler::GetPixelsForImage : Empty pixelBufferSize or pixelBuffer",
      a4);
    return 2147942487LL;
  }
  if ( a7 )
  {
    left = a7->left;
    top = a7->top;
    a1 = a7->right - a7->left;
    a2 = a7->bottom - top;
  }
  else
  {
    left = 0;
    top = 0;
  }
  v38.m128i_i64[0] = __PAIR64__(top, left);
  v38.m128i_i64[1] = __PAIR64__(a2, a1);
  LODWORD(v15) = COERCE_UNSIGNED_INT64(((double (*)(void))_o_roundf)());
  v16 = (float)v38.m128i_i32[3] * a6;
  _o_roundf();
  if ( v38.m128i_i32[0] < 0
    || v38.m128i_i32[1] < 0
    || v38.m128i_i32[2] <= 0
    || v38.m128i_i32[3] <= 0
    || v38.m128i_i32[2] > v11
    || v38.m128i_i32[3] > v10
    || (v17 = (int)v15, v38.m128i_i32[2] < (int)v15)
    || (v18 = (int)v16, v38.m128i_i32[3] < (int)v16)
    || (int)v17 <= 0
    || v18 <= 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x9C,
      (unsigned int)"onecoreuap\\base\\appmodel\\Search\\filters\\common\\imageprocessing\\imagingHandler.h",
      (const char *)0x80070057LL,
      v31);
    return 2147942487LL;
  }
  v19 = 3;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_57519991>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_57519991>::GetImpl'::`2'::impl) )
  {
    v20 = FLOAT_0_89999998;
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_58212721>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_58212721>::GetImpl'::`2'::impl) )
    {
      Variant = wil::details::FeatureImpl<__WilFeatureTraits_Feature_58212721>::__private_GetVariant(`wil::Feature<__WilFeatureTraits_Feature_58212721>::GetImpl'::`2'::impl);
      if ( Variant == 1 )
      {
        v20 = FLOAT_0_5;
      }
      else if ( Variant == 2 )
      {
        v20 = FLOAT_0_69999999;
      }
    }
    v19 = (v20 <= a6) + 2;
  }
  v39 = v38;
  if ( _mm_cvtsi128_si32(_mm_srli_si128(v38, 8)) == v17 && _mm_cvtsi128_si32(_mm_srli_si128(v38, 12)) == v18 )
    goto LABEL_50;
  v32 = 0;
  v22 = (*(__int64 (__fastcall **)(const wchar_t *, __int64 *))(*(_QWORD *)a4 + 88LL))(a4, &v32);
  v23 = v22;
  if ( v22 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xC3,
      (unsigned int)"onecoreuap\\base\\appmodel\\Search\\filters\\common\\imageprocessing\\imagingHandler.h",
      (const char *)(unsigned int)v22,
      v31);
    v24 = v32 == 0;
LABEL_27:
    if ( !v24 )
      winrt::com_ptr<IWICBitmapFrameDecode>::unconditional_release_ref(&v32);
    return (unsigned int)v23;
  }
  if ( v38.m128i_i64[1] != __PAIR64__(v10, v11) )
  {
    v33 = 0;
    v27 = v36;
    v23 = (*(__int64 (__fastcall **)(const wchar_t *, __int64 *))(*(_QWORD *)v36 + 96LL))(v36, &v33);
    if ( v23 >= 0 )
    {
      v23 = (*(__int64 (__fastcall **)(__int64, struct IWICBitmap *, __m128i *))(*(_QWORD *)v33 + 64LL))(v33, a5, &v38);
      if ( v23 >= 0 )
      {
        v31 = v19;
        v23 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, _QWORD))(*(_QWORD *)v32 + 64LL))(
                v32,
                v33,
                v17,
                (unsigned int)v18);
        if ( v23 >= 0 )
        {
          if ( v33 )
            winrt::com_ptr<IWICBitmapFrameDecode>::unconditional_release_ref(&v33);
          goto LABEL_45;
        }
        v28 = 201;
      }
      else
      {
        v28 = 200;
      }
    }
    else
    {
      v28 = 199;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v28,
      (unsigned int)"onecoreuap\\base\\appmodel\\Search\\filters\\common\\imageprocessing\\imagingHandler.h",
      (const char *)(unsigned int)v23,
      v31);
    if ( v33 )
      winrt::com_ptr<IWICBitmapFrameDecode>::unconditional_release_ref(&v33);
    goto LABEL_37;
  }
  v31 = v19;
  v26 = (*(__int64 (__fastcall **)(__int64, struct IWICBitmap *, _QWORD, _QWORD))(*(_QWORD *)v32 + 64LL))(
          v32,
          a5,
          v17,
          (unsigned int)v18);
  v23 = v26;
  if ( v26 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xCD,
      (unsigned int)"onecoreuap\\base\\appmodel\\Search\\filters\\common\\imageprocessing\\imagingHandler.h",
      (const char *)(unsigned int)v26,
      v19);
LABEL_37:
    v24 = v32 == 0;
    goto LABEL_27;
  }
  v27 = v36;
LABEL_45:
  v34 = 0;
  v29 = (*(__int64 (__fastcall **)(const wchar_t *, __int64, __int64, struct IWICBitmap **))(*(_QWORD *)v27 + 144LL))(
          v27,
          v32,
          2,
          &v34);
  v23 = v29;
  if ( v29 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD0,
      (unsigned int)"onecoreuap\\base\\appmodel\\Search\\filters\\common\\imageprocessing\\imagingHandler.h",
      (const char *)(unsigned int)v29,
      v31);
    if ( v34 )
      winrt::com_ptr<IWICBitmapFrameDecode>::unconditional_release_ref(&v34);
    goto LABEL_37;
  }
  v12 = v34;
  v34 = 0;
  v39.m128i_i64[0] = 0;
  v39.m128i_i32[2] = v17;
  v39.m128i_i32[3] = (int)v16;
  if ( v32 )
  {
    winrt::com_ptr<IWICBitmapFrameDecode>::unconditional_release_ref(&v32);
LABEL_50:
    v17 = v39.m128i_u32[2];
  }
  if ( v17 && v17 * (v35 & 0x1FFFFFFF) / v17 == (v35 & 0x1FFFFFFF) )
    v30 = (v17 * (v35 & 0x1FFFFFFF) + 3) & 0xFFFFFFFC;
  else
    v30 = 0;
  return ((__int64 (__fastcall *)(struct IWICBitmap *, __m128i *, __int64, _QWORD, unsigned __int8 *))v12->lpVtbl->CopyPixels)(
           v12,
           &v39,
           v30,
           a8,
           v37);
}

```

## disassembly

```asm
0x18001153c  mov     rax, rsp
0x18001153f  push    rbp
0x180011540  push    rbx
0x180011541  push    rsi
0x180011542  push    rdi
0x180011543  push    r12
0x180011545  push    r13
0x180011547  push    r14
0x180011549  push    r15
0x18001154b  lea     rbp, [rax-47h]
0x18001154f  sub     rsp, 0A8h
0x180011556  movaps  xmmword ptr [rax-58h], xmm6
0x18001155a  mov     rax, cs:__security_cookie
0x180011561  xor     rax, rsp
0x180011564  mov     [rbp+3Fh+var_60], rax
0x180011568  mov     rdi, r9
0x18001156b  mov     [rbp+3Fh+var_90], r9
0x18001156f  mov     [rbp+3Fh+var_98], r8d
0x180011573  mov     r13d, edx
0x180011576  mov     r12d, ecx
0x180011579  mov     rax, [rbp+3Fh+arg_30]
0x18001157d  mov     r15, [rbp+3Fh+arg_20]
0x180011581  mov     rcx, [rbp+3Fh+arg_40]
0x180011588  mov     [rbp+3Fh+var_88], rcx
0x18001158c  xor     esi, esi
0x18001158e  cmp     [rbp+3Fh+arg_38], esi
0x180011594  jz      loc_180011948
0x18001159a  test    rcx, rcx
0x18001159d  jz      loc_180011948
0x1800115a3  test    rax, rax
0x1800115a6  jz      short loc_1800115BD
0x1800115a8  mov     r8d, [rax]
0x1800115ab  mov     r9d, [rax+4]
0x1800115af  mov     ecx, [rax+8]
0x1800115b2  sub     ecx, r8d
0x1800115b5  mov     edx, [rax+0Ch]
0x1800115b8  sub     edx, r9d
0x1800115bb  jmp     short loc_1800115C6
0x1800115bd  mov     r8d, esi
0x1800115c0  mov     r9d, esi
0x1800115c3  mov     ecx, r12d
0x1800115c6  mov     dword ptr [rbp+3Fh+var_80], r8d
0x1800115ca  mov     dword ptr [rbp+3Fh+var_80+4], r9d
0x1800115ce  mov     dword ptr [rbp+3Fh+var_80+8], ecx
0x1800115d1  mov     dword ptr [rbp+3Fh+var_80+0Ch], edx
0x1800115d4  movd    xmm0, ecx
0x1800115d8  cvtdq2ps xmm0, xmm0
0x1800115db  mulss   xmm0, [rbp+3Fh+arg_28]
0x1800115e0  call    cs:__imp__o_roundf
0x1800115e6  movaps  xmm6, xmm0
0x1800115e9  movd    xmm0, dword ptr [rbp+3Fh+var_80+0Ch]
0x1800115ee  cvtdq2ps xmm0, xmm0
0x1800115f1  mulss   xmm0, [rbp+3Fh+arg_28]
0x1800115f6  call    cs:__imp__o_roundf
0x1800115fc  cmp     dword ptr [rbp+3Fh+var_80], esi
0x1800115ff  jl      loc_18001192B
0x180011605  cmp     dword ptr [rbp+3Fh+var_80+4], esi
0x180011608  jl      loc_18001192B
0x18001160e  mov     eax, dword ptr [rbp+3Fh+var_80+8]
0x180011611  test    eax, eax
0x180011613  jle     loc_18001192B
0x180011619  mov     ecx, dword ptr [rbp+3Fh+var_80+0Ch]
0x18001161c  test    ecx, ecx
0x18001161e  jle     loc_18001192B
0x180011624  cmp     eax, r12d
0x180011627  jg      loc_18001192B
0x18001162d  cmp     ecx, r13d
0x180011630  jg      loc_18001192B
0x180011636  cvttss2si ebx, xmm6
0x18001163a  cmp     eax, ebx
0x18001163c  jl      loc_18001192B
0x180011642  cvttss2si r14d, xmm0
0x180011647  cmp     ecx, r14d
0x18001164a  jl      loc_18001192B
0x180011650  test    ebx, ebx
0x180011652  jle     loc_18001192B
0x180011658  test    r14d, r14d
0x18001165b  jle     loc_18001192B
0x180011661  mov     esi, 3
0x180011666  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_57519991@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_57519991@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_57519991> `wil::Feature<__WilFeatureTraits_Feature_57519991>::GetImpl(void)'::`2'::impl
0x18001166d  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_57519991@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_57519991>::__private_IsEnabled(void)
0x180011672  test    al, al
0x180011674  jz      short loc_1800116C6
0x180011676  movss   xmm6, cs:__real@3f666666
0x18001167e  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_58212721@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_58212721@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_58212721> `wil::Feature<__WilFeatureTraits_Feature_58212721>::GetImpl(void)'::`2'::impl
0x180011685  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_58212721@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_58212721>::__private_IsEnabled(void)
0x18001168a  test    al, al
0x18001168c  jz      short loc_1800116B9
0x18001168e  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_58212721@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_58212721@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_58212721> `wil::Feature<__WilFeatureTraits_Feature_58212721>::GetImpl(void)'::`2'::impl
0x180011695  call    ?__private_GetVariant@?$FeatureImpl@U__WilFeatureTraits_Feature_58212721@@@details@wil@@QEAA?AW4Variant_58212721@@W4VariantReportingKind@3@_N@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_58212721>::__private_GetVariant(wil::VariantReportingKind,bool)
0x18001169a  movzx   ecx, al
0x18001169d  sub     ecx, 1
0x1800116a0  jz      short loc_1800116B1
0x1800116a2  sub     ecx, 1
0x1800116a5  jnz     short loc_1800116B9
0x1800116a7  movss   xmm6, cs:__real@3f333333
0x1800116af  jmp     short loc_1800116B9
0x1800116b1  movss   xmm6, cs:__real@3f000000
0x1800116b9  xor     esi, esi
0x1800116bb  comiss  xmm6, [rbp+3Fh+arg_28]
0x1800116bf  setbe   sil
0x1800116c3  add     esi, 2
0x1800116c6  movaps  xmm1, [rbp+3Fh+var_80]
0x1800116ca  movdqa  [rbp+3Fh+var_70], xmm1
0x1800116cf  movdqa  xmm0, xmm1
0x1800116d3  psrldq  xmm0, 8
0x1800116d8  movd    eax, xmm0
0x1800116dc  cmp     eax, ebx
0x1800116de  jnz     short loc_1800116F6
0x1800116e0  psrldq  xmm1, 0Ch
0x1800116e5  movd    eax, xmm1
0x1800116e9  cmp     eax, r14d
0x1800116ec  jnz     short loc_1800116F6
0x1800116ee  xor     r13d, r13d
0x1800116f1  jmp     loc_1800118D4
0x1800116f6  mov     [rbp+3Fh+var_B0], 0
0x1800116fe  mov     rax, [rdi]
0x180011701  lea     rdx, [rbp+3Fh+var_B0]
0x180011705  mov     rcx, rdi
0x180011708  mov     rax, [rax+58h]
0x18001170c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011711  mov     edi, eax
0x180011713  test    eax, eax
0x180011715  jns     short loc_180011747
0x180011717  mov     rcx, [rbp+47h]; this
0x18001171b  mov     r9d, eax; char *
0x18001171e  lea     r8, aOnecoreuapBase_1; "onecoreuap\\base\\appmodel\\Search\\fil"...
0x180011725  mov     edx, 0C3h; void *
0x18001172a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001172f  nop
0x180011730  cmp     [rbp+3Fh+var_B0], 0
0x180011735  jz      short loc_180011740
0x180011737  lea     rcx, [rbp+3Fh+var_B0]
0x18001173b  call    ?unconditional_release_ref@?$com_ptr@UIWICBitmapFrameDecode@@@winrt@@AEAAXXZ; winrt::com_ptr<IWICBitmapFrameDecode>::unconditional_release_ref(void)
0x180011740  mov     eax, edi
0x180011742  jmp     loc_180011965
0x180011747  cmp     dword ptr [rbp+3Fh+var_80+8], r12d
0x18001174b  jnz     short loc_180011797
0x18001174d  cmp     dword ptr [rbp+3Fh+var_80+0Ch], r13d
0x180011751  jnz     short loc_180011797
0x180011753  mov     rcx, [rbp+3Fh+var_B0]
0x180011757  mov     rax, [rcx]
0x18001175a  mov     [rsp+20h], esi; int
0x18001175e  mov     r9d, r14d
0x180011761  mov     r8d, ebx
0x180011764  mov     rdx, r15
0x180011767  mov     rax, [rax+40h]
0x18001176b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011770  mov     edi, eax
0x180011772  xor     r13d, r13d
0x180011775  test    eax, eax
0x180011777  jns     loc_18001184E
0x18001177d  mov     rcx, [rbp+47h]; this
0x180011781  mov     r9d, eax; char *
0x180011784  lea     r8, aOnecoreuapBase_1; "onecoreuap\\base\\appmodel\\Search\\fil"...
0x18001178b  mov     edx, 0CDh; void *
0x180011790  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180011795  jmp     short loc_1800117E5
0x180011797  xor     r13d, r13d
0x18001179a  mov     [rbp+3Fh+var_A8], r13
0x18001179e  mov     r12, [rbp+3Fh+var_90]
0x1800117a2  mov     rax, [r12]
0x1800117a6  lea     rdx, [rbp+3Fh+var_A8]
0x1800117aa  mov     rcx, r12
0x1800117ad  mov     rax, [rax+60h]
0x1800117b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800117b6  mov     edi, eax
0x1800117b8  test    eax, eax
0x1800117ba  jns     short loc_1800117EE
0x1800117bc  mov     edx, 0C7h; void *
0x1800117c1  mov     rcx, [rbp+47h]; this
0x1800117c5  mov     r9d, edi; char *
0x1800117c8  lea     r8, aOnecoreuapBase_1; "onecoreuap\\base\\appmodel\\Search\\fil"...
0x1800117cf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800117d4  nop
0x1800117d5  cmp     [rbp+3Fh+var_A8], r13
0x1800117d9  jz      short loc_1800117E5
0x1800117db  lea     rcx, [rbp+3Fh+var_A8]
0x1800117df  call    ?unconditional_release_ref@?$com_ptr@UIWICBitmapFrameDecode@@@winrt@@AEAAXXZ; winrt::com_ptr<IWICBitmapFrameDecode>::unconditional_release_ref(void)
0x1800117e4  nop
0x1800117e5  cmp     [rbp+3Fh+var_B0], r13
0x1800117e9  jmp     loc_180011735
0x1800117ee  mov     rcx, [rbp+3Fh+var_A8]
0x1800117f2  mov     rax, [rcx]
0x1800117f5  lea     r8, [rbp+3Fh+var_80]
0x1800117f9  mov     rdx, r15
0x1800117fc  mov     rax, [rax+40h]
0x180011800  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011805  mov     edi, eax
0x180011807  test    eax, eax
0x180011809  jns     short loc_180011812
0x18001180b  mov     edx, 0C8h
0x180011810  jmp     short loc_1800117C1
0x180011812  mov     rcx, [rbp+3Fh+var_B0]
0x180011816  mov     rax, [rcx]
0x180011819  mov     [rsp+20h], esi
0x18001181d  mov     r9d, r14d
0x180011820  mov     r8d, ebx
0x180011823  mov     rdx, [rbp+3Fh+var_A8]
0x180011827  mov     rax, [rax+40h]
0x18001182b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011830  mov     edi, eax
0x180011832  test    eax, eax
0x180011834  jns     short loc_18001183D
0x180011836  mov     edx, 0C9h
0x18001183b  jmp     short loc_1800117C1
0x18001183d  cmp     [rbp+3Fh+var_A8], r13
0x180011841  jz      short loc_180011852
0x180011843  lea     rcx, [rbp+3Fh+var_A8]
0x180011847  call    ?unconditional_release_ref@?$com_ptr@UIWICBitmapFrameDecode@@@winrt@@AEAAXXZ; winrt::com_ptr<IWICBitmapFrameDecode>::unconditional_release_ref(void)
0x18001184c  jmp     short loc_180011852
0x18001184e  mov     r12, [rbp+3Fh+var_90]
0x180011852  mov     [rbp+3Fh+var_A0], r13
0x180011856  mov     rax, [r12]
0x18001185a  lea     r9, [rbp+3Fh+var_A0]
0x18001185e  mov     r8d, 2
0x180011864  mov     rdx, [rbp+3Fh+var_B0]
0x180011868  mov     rcx, r12
0x18001186b  mov     rax, [rax+90h]
0x180011872  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011877  mov     edi, eax
0x180011879  test    eax, eax
0x18001187b  jns     short loc_1800118AE
0x18001187d  mov     rcx, [rbp+47h]; this
0x180011881  mov     r9d, eax; char *
0x180011884  lea     r8, aOnecoreuapBase_1; "onecoreuap\\base\\appmodel\\Search\\fil"...
0x18001188b  mov     edx, 0D0h; void *
0x180011890  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180011895  nop
0x180011896  cmp     [rbp+3Fh+var_A0], r13
0x18001189a  jz      loc_1800117E5
0x1800118a0  lea     rcx, [rbp+3Fh+var_A0]
0x1800118a4  call    ?unconditional_release_ref@?$com_ptr@UIWICBitmapFrameDecode@@@winrt@@AEAAXXZ; winrt::com_ptr<IWICBitmapFrameDecode>::unconditional_release_ref(void)
0x1800118a9  jmp     loc_1800117E5
0x1800118ae  mov     r15, [rbp+3Fh+var_A0]
0x1800118b2  mov     [rbp+3Fh+var_A0], r13
0x1800118b6  mov     qword ptr [rbp+3Fh+var_70], 0
0x1800118be  mov     dword ptr [rbp+3Fh+var_70+8], ebx
0x1800118c1  mov     dword ptr [rbp+3Fh+var_70+0Ch], r14d
0x1800118c5  cmp     [rbp+3Fh+var_B0], r13
0x1800118c9  jz      short loc_1800118D7
0x1800118cb  lea     rcx, [rbp+3Fh+var_B0]
0x1800118cf  call    ?unconditional_release_ref@?$com_ptr@UIWICBitmapFrameDecode@@@winrt@@AEAAXXZ; winrt::com_ptr<IWICBitmapFrameDecode>::unconditional_release_ref(void)
0x1800118d4  mov     ebx, dword ptr [rbp+3Fh+var_70+8]
0x1800118d7  mov     rax, [r15]
0x1800118da  mov     r10, [rax+38h]
0x1800118de  test    ebx, ebx
0x1800118e0  jnz     short loc_1800118E7
0x1800118e2  mov     r8d, r13d
0x1800118e5  jmp     short loc_18001190A
0x1800118e7  mov     ecx, [rbp+3Fh+var_98]
0x1800118ea  and     ecx, 1FFFFFFFh
0x1800118f0  mov     r8d, ecx
0x1800118f3  imul    r8d, ebx
0x1800118f7  xor     edx, edx
0x1800118f9  mov     eax, r8d
0x1800118fc  div     ebx
0x1800118fe  cmp     eax, ecx
0x180011900  jnz     short loc_1800118E2
0x180011902  add     r8d, 3
0x180011906  and     r8d, 0FFFFFFFCh
0x18001190a  mov     rax, [rbp+3Fh+var_88]
0x18001190e  mov     [rsp+20h], rax
0x180011913  mov     r9d, [rbp+3Fh+arg_38]
0x18001191a  lea     rdx, [rbp+3Fh+var_70]
0x18001191e  mov     rcx, r15
0x180011921  mov     rax, r10
0x180011924  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011929  jmp     short loc_180011965
0x18001192b  mov     rcx, [rbp+47h]; this
0x18001192f  mov     r9d, 80070057h; char *
0x180011935  lea     r8, aOnecoreuapBase_1; "onecoreuap\\base\\appmodel\\Search\\fil"...
0x18001193c  mov     edx, 9Ch; void *
0x180011941  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180011946  jmp     short loc_180011960
0x180011948  lea     r8, aImaginghandler; "ImagingHandler::GetPixelsForImage : Emp"...
0x18001194f  mov     edx, 96h; wchar_t *
0x180011954  lea     rcx, aOnecoreuapBase_0; "onecoreuap\\base\\appmodel\\Search\\fil"...
0x18001195b  call    ?Error@SearchIndexerTrace@@YAXPEB_WI0ZZ; SearchIndexerTrace::Error(wchar_t const *,uint,wchar_t const *,...)
0x180011960  mov     eax, 80070057h
0x180011965  mov     rcx, [rbp+3Fh+var_60]
0x180011969  xor     rcx, rsp; StackCookie
0x18001196c  call    __security_check_cookie
0x180011971  movaps  xmm6, [rsp+0E0h+var_58+8]
0x180011979  add     rsp, 0A8h
0x180011980  pop     r15
0x180011982  pop     r14
0x180011984  pop     r13
0x180011986  pop     r12
0x180011988  pop     rdi
0x180011989  pop     rsi
0x18001198a  pop     rbx
0x18001198b  pop     rbp
0x18001198c  retn
```
