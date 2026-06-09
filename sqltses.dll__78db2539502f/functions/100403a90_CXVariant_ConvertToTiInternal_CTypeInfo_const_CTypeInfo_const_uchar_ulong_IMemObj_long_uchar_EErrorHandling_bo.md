# CXVariant::ConvertToTiInternal(CTypeInfo const *,CTypeInfo const *,uchar *,ulong,IMemObj *,long,uchar,EErrorHandling,bool,bool,IBlobHandleFactory *,CDefaultCollation const *,short)

- ea: `0x100403a90`
- end: `0x100403e11`
- name: `?ConvertToTiInternal@CXVariant@@AEAAJPEBVCTypeInfo@@0PEAEKPEAVIMemObj@@JEW4EErrorHandling@@_N4PEAUIBlobHandleFactory@@PEBVCDefaultCollation@@F@Z`
- size: `897`
- prototype: `__int64 __fastcall(__m256i *, unsigned __int8 *, unsigned __int8 *, unsigned __int8 *, int, struct IMemObj *, int, char, char, bool, char, struct IBlobHandleFactory *, struct CDefaultCollation *, __int16)`
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x1004038f0`
- `0x1004504e0`

## callees

- `0x1004032e0`
- `0x100403640`
- `0x100403a90`
- `0x100403e20`
- `0x1004041f0`
- `0x10040d470`

## import_xrefs

- `sqldk!?ExceptionPostCatchActions@@YAXPEAVWorker@@@Z` at `0x100450d7b`
- `sqldk!?ExceptionPostCatchActions@@YAXPEAVWorker@@@Z` at `0x100450d7b`
- `sqldk!??_V@YAXPEAX@Z` at `0x100450d9d`
- `sqldk!??_V@YAXPEAX@Z` at `0x100450dfa`
- `sqldk!??_V@YAXPEAX@Z` at `0x100450e1a`
- `sqldk!??_V@YAXPEAX@Z` at `0x100450d9d`
- `sqldk!??_V@YAXPEAX@Z` at `0x100450dfa`
- `sqldk!??_V@YAXPEAX@Z` at `0x100450e1a`
- `sqldk!SystemThread_TlsIndex` at `0x100403d37`
- `sqldk!SystemThread_TlsIndex` at `0x100450afa`
- `sqldk!SystemThread_TlsOffset` at `0x100403d40`
- `sqldk!SystemThread_TlsOffset` at `0x100450b03`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100450b1f`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100450d68`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100450b1f`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100450d68`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CXVariant::ConvertToTiInternal(
        __m256i *a1,
        unsigned __int8 *a2,
        unsigned __int8 *a3,
        unsigned __int8 *a4,
        int a5,
        struct IMemObj *a6,
        int a7,
        char a8,
        char a9,
        bool a10,
        char a11,
        struct IBlobHandleFactory *a12,
        struct CDefaultCollation *a13,
        __int16 a14)
{
  unsigned __int8 *v14; // r12
  unsigned __int8 *v15; // rsi
  unsigned __int8 *v16; // r14
  __int64 v17; // rbx
  __int64 v18; // rcx
  BOOL v19; // eax
  __int16 v20; // r9
  __int64 v21; // xmm1_8
  unsigned __int8 *v22; // r9
  unsigned int v23; // ecx
  __int64 v24; // r15
  __int64 v25; // rcx
  unsigned int v26; // r15d
  __int16 v27; // ax
  __int64 v29; // rdx
  __int16 v30; // r8
  __int64 v31; // rcx
  __int64 v32; // rdx
  __int64 v33; // r10
  __int64 v34; // r11
  int v35; // ecx
  int v36; // ecx
  int v37; // r9d
  int v38; // r8d
  __int64 v39; // r15
  __int64 v40; // rax
  struct IMemObj *v41; // rcx
  int v42; // ecx
  char v43; // al
  unsigned __int8 *v44; // r9
  unsigned int v45; // ecx
  int v46; // eax
  __m128i v47; // xmm1
  __m128i v48; // xmm1
  const struct SQLError *CurrentException; // rax
  bool v50; // [rsp+70h] [rbp-D8h]
  bool v51; // [rsp+71h] [rbp-D7h] BYREF
  char v52; // [rsp+72h] [rbp-D6h]
  int v53; // [rsp+74h] [rbp-D4h] BYREF
  int v54; // [rsp+78h] [rbp-D0h]
  unsigned __int8 *v55; // [rsp+80h] [rbp-C8h] BYREF
  __m256i v56; // [rsp+88h] [rbp-C0h] BYREF
  int v57; // [rsp+A8h] [rbp-A0h] BYREF
  int v58; // [rsp+ACh] [rbp-9Ch] BYREF
  unsigned __int8 *v59; // [rsp+B0h] [rbp-98h] BYREF
  __int64 v60; // [rsp+B8h] [rbp-90h]
  _QWORD v61[2]; // [rsp+C0h] [rbp-88h] BYREF
  __int128 v62; // [rsp+D0h] [rbp-78h]
  _QWORD v63[3]; // [rsp+E0h] [rbp-68h] BYREF
  _BYTE v64[80]; // [rsp+F8h] [rbp-50h] BYREF
  unsigned __int8 *v67; // [rsp+160h] [rbp+18h]
  char v69; // [rsp+1A0h] [rbp+58h]

  v67 = a3;
  v63[2] = -2;
  v14 = a4;
  v15 = a3;
  v16 = a2;
  v17 = (__int64)a1;
  v54 = 100;
  v18 = *a2;
  v19 = 0;
  if ( *((_BYTE *)&CTypeInfo::sxm_rgfIsLegacyLargeObject + *((unsigned __int8 *)&xsm_rgOrdFromXvt + v18)) )
  {
    v29 = *a3;
    if ( *((_BYTE *)&CTypeInfo::sxm_rgfIsLegacyLargeObject + *((unsigned __int8 *)&xsm_rgOrdFromXvt + v29)) )
    {
      if ( (_BYTE)v29 != (_BYTE)v18 )
        v19 = 1;
    }
  }
  if ( !a11 && v19 )
    return 100;
  if ( (v16[1] & 0x10) != 0 && (_BYTE)v18 != 0xF0 || (a3[1] & 0x10) != 0 && *a3 != 0xF0 )
  {
    LOBYTE(a3) = 1;
    if ( !(unsigned int)CtCheckCast(v16, v15, a3) )
      return 100;
  }
  if ( *(_BYTE *)v17 == 3 )
  {
    if ( (v15[1] & 1) != 0 )
    {
      return 8;
    }
    else
    {
      if ( (*(_BYTE *)(v17 + 2) & 1) != 0 )
        CXVariant::ClearDeep<CTypeInfo>(v17, v16);
      *(_DWORD *)v17 = 3;
      *(_DWORD *)(v17 + 24) = 0;
      *(_QWORD *)(v17 + 8) = v14;
      *(_QWORD *)(v17 + 16) = 0;
      *(_BYTE *)(v17 + 1) = *v15;
      return 0;
    }
  }
  else
  {
    v20 = *((_WORD *)v16 + 8);
    if ( v20 != -1 && !*((_BYTE *)&CTypeInfo::sxm_rgfIsLargeObject + *((unsigned __int8 *)&xsm_rgOrdFromXvt + *v16)) )
      goto LABEL_9;
    v30 = *((_WORD *)v15 + 8);
    if ( v30 != -1 && !*((_BYTE *)&CTypeInfo::sxm_rgfIsLargeObject + *((unsigned __int8 *)&xsm_rgOrdFromXvt + *v15)) )
      goto LABEL_9;
    if ( v14 )
      goto LABEL_9;
    v31 = *v16;
    if ( (_BYTE)v31 == 0xF1 )
      goto LABEL_9;
    v32 = *v15;
    if ( (_BYTE)v32 == 0xF1 )
      goto LABEL_9;
    v33 = *((unsigned __int8 *)&xsm_rgOrdFromXvt + v32);
    if ( *((_BYTE *)&CTypeInfo::sxm_rgfIsBinary + v33) )
    {
      if ( v30 == -1 )
        goto LABEL_87;
    }
    if ( (_BYTE)v32 == 34 )
      goto LABEL_87;
    if ( (v34 = *((unsigned __int8 *)&xsm_rgOrdFromXvt + v31), *((_BYTE *)&CTypeInfo::sxm_rgfIsBinary + v34))
      && v20 == -1
      || (_BYTE)v31 == 34 )
    {
      if ( (!*((_BYTE *)&CTypeInfo::sxm_rgfIsWString + v33) || v30 != -1)
        && (_BYTE)v32 != 99
        && ((_BYTE)v32 != 0xF0 || v30 != -1) )
      {
        goto LABEL_87;
      }
    }
    if ( (*((_BYTE *)&CTypeInfo::sxm_rgfIsWString + v34) && v20 == -1 || (_BYTE)v31 == 99)
      && (*((_BYTE *)&CTypeInfo::sxm_rgfIsWString + v33) && v30 == -1 || (_BYTE)v32 == 99)
      || (_BYTE)v31 == 0xF0 && v20 == -1 && (_BYTE)v32 == 0xF0 && v30 == -1 )
    {
      goto LABEL_87;
    }
    if ( (!*((_BYTE *)&CTypeInfo::sxm_rgfIsString + v34) || v20 != -1) && (_BYTE)v31 != 35
      || (!*((_BYTE *)&CTypeInfo::sxm_rgfIsString + v33) || v30 != -1) && (_BYTE)v32 != 35 )
    {
      goto LABEL_9;
    }
    v35 = *((_DWORD *)v16 + 5);
    if ( (v35 & 0x80) != 0 )
    {
      v36 = 65001;
      v37 = 65001;
    }
    else
    {
      if ( HIBYTE(v35) )
        v37 = *((_DWORD *)&x_uiCodePage + (unsigned __int8)byte_10085C9DC[40 * HIBYTE(v35)]);
      else
        v37 = qword_100856AB0[4 * (v35 & 0x7F)];
      v36 = 65001;
    }
    v38 = *((_DWORD *)v15 + 5);
    if ( (v38 & 0x80) == 0 )
    {
      if ( HIBYTE(v38) )
        v36 = *((_DWORD *)&x_uiCodePage + (unsigned __int8)byte_10085C9DC[40 * HIBYTE(v38)]);
      else
        v36 = qword_100856AB0[4 * (v38 & 0x7F)];
    }
    if ( v37 == v36 )
    {
LABEL_87:
      *(_BYTE *)(v17 + 1) = v32;
      return 0;
    }
    else
    {
LABEL_9:
      v56.m256i_i32[0] = 3;
      memset(&v56.m256i_u64[1], 0, 20);
      v56 = *(__m256i *)v17;
      v21 = v56.m256i_i64[0];
      *(_WORD *)(v17 + 2) &= ~1u;
      v59 = 0;
      v55 = 0;
      v57 = 0;
      v53 = 0;
      v50 = 0;
      v56.m256i_i64[0] = v21;
      v69 = BYTE2(v21) & 1;
      v60 = 0;
      if ( __eh34_try(-1, 0) )
      {
        __eh34_scope_strut(0);
        v61[0] = 0;
        v61[1] = -1;
        v62 = 0u;
        if ( ConvertUtils::FTwoStepConvert(
               (const struct CTypeInfo *)v16,
               (const struct CTypeInfo *)v15,
               &v58,
               (struct CTypeInfo *)v61,
               &v51) )
        {
          if ( a6 )
          {
            v41 = a6;
          }
          else
          {
            v39 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                + SystemThread_TlsOffset;
            v40 = *(_QWORD *)(v39 + 256);
            if ( !v40 )
            {
              SystemThread::MakeMiniSOSThread(0);
              v40 = *(_QWORD *)(v39 + 256);
            }
            v41 = *(struct IMemObj **)(v40 + 1000);
          }
          AllocateConvertBuffer(v41, (const struct CTypeInfo *)v61, &v59, &v57);
          v50 = v59 != 0;
          v42 = 0;
          if ( (v58 & 1) != 0 )
            v42 = a7;
          v43 = a9;
          v52 = a9;
          if ( v51 )
          {
            if ( !a9 )
              v43 = 1;
            v52 = v43;
          }
          v54 = CXVariant::ConvertToTiOneStep(
                  v17,
                  (char *)v16,
                  (const struct CTypeInfo *)v61,
                  v59,
                  v57,
                  v42,
                  a13,
                  a14,
                  a8,
                  v43,
                  a10,
                  a12);
          if ( !v54 )
          {
            if ( ((_WORD)v62 == 0xFFFF
               || *((_BYTE *)&CTypeInfo::sxm_rgfIsLargeObject + *((unsigned __int8 *)&xsm_rgOrdFromXvt + LOBYTE(v61[0]))))
              && *(_BYTE *)v17 != 3 )
            {
              v60 = *(_QWORD *)(v17 + 8);
            }
            if ( v14 )
            {
              v44 = v14;
              v55 = v14;
              v45 = a5;
              v53 = a5;
            }
            else
            {
              AllocateConvertBuffer(a6, (const struct CTypeInfo *)v15, &v55, &v53);
              v44 = v55;
              v45 = v53;
            }
            v46 = 0;
            if ( (v58 & 2) != 0 )
              v46 = a7;
            v54 = CXVariant::ConvertToTiOneStep(
                    v17,
                    (char *)v61,
                    (const struct CTypeInfo *)v15,
                    v44,
                    v45,
                    v46,
                    a13,
                    a14,
                    a8,
                    a9,
                    a10,
                    a12);
          }
        }
        else
        {
          if ( v14 )
          {
            v22 = v14;
            v55 = v14;
            v23 = a5;
            v53 = a5;
          }
          else
          {
            AllocateConvertBuffer(a6, (const struct CTypeInfo *)v15, &v55, &v53);
            v22 = v55;
            v23 = v53;
          }
          v54 = CXVariant::ConvertToTiOneStep(
                  v17,
                  (char *)v16,
                  (const struct CTypeInfo *)v15,
                  v22,
                  v23,
                  a7,
                  a13,
                  a14,
                  a8,
                  a9,
                  a10,
                  a12);
        }
      }
      if ( __eh34_catch(0) )
      {
        if ( __eh34_catch_type(0, &SQLError `RTTI Type Descriptor', (SQLError *)v64) )
        {
          if ( __eh34_try(1, 2) )
          {
            __eh34_scope_strut(2);
            ExceptionBackout::ExceptionBackout((ExceptionBackout *)v63, (const struct SQLError *)v64);
            v48 = *(__m128i *)v56.m256i_i8;
            *a1 = v56;
            v56.m256i_i16[1] = _mm_extract_epi16(v48, 1) & 0xFFFE;
            if ( v60 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v60 + 16LL))(v60);
            if ( v59 )
              operator delete[](v59);
            if ( !a4 && v55 )
              operator delete[](v55);
            CurrentException = ExceptionBackout::GetCurrentException((ExceptionBackout *)v63);
            ExceptionRethrow(CurrentException);
            ExceptionBackout::~ExceptionBackout((ExceptionBackout *)v63);
          }
          if ( __eh34_catch(2) )
          {
            if ( __eh34_catch_type(2, &ShortStackException `RTTI Type Descriptor', 0) )
              __eh34_try_continuation(2, &ShortStackException `RTTI Type Descriptor', &loc_10083FDEE);
          }
          v17 = (__int64)a1;
          v14 = a4;
          v15 = v67;
          v16 = a2;
          __eh34_try_continuation(0, &SQLError `RTTI Type Descriptor', &loc_100450D3A);
        }
      }
      v24 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
      v25 = *(_QWORD *)(v24 + 256);
      if ( !v25 )
      {
        SystemThread::MakeMiniSOSThread(0);
        v25 = *(_QWORD *)(v24 + 256);
      }
      if ( *(_DWORD *)(v25 + 556) )
        ExceptionPostCatchActions((struct Worker *)v25);
      v26 = v54;
      if ( v54 )
      {
        v47 = *(__m128i *)v56.m256i_i8;
        *(__m256i *)v17 = v56;
        v56.m256i_i16[1] = _mm_extract_epi16(v47, 1) & 0xFFFE;
        if ( v60 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v60 + 16LL))(v60);
        if ( v59 )
          operator delete[](v59);
        if ( !v14 && v55 )
          operator delete[](v55);
      }
      else
      {
        if ( v69 )
          v56.m256i_i16[1] |= 1u;
        else
          v56.m256i_i16[1] &= ~1u;
        if ( (v56.m256i_i8[2] & 1) != 0 )
          CXVariant::ClearDeep<CTypeInfo>(&v56, v16);
        v56.m256i_i32[0] = 3;
        memset(&v56.m256i_u64[1], 0, 20);
        if ( v60 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v60 + 16LL))(v60);
        if ( v50 )
          operator delete[](v59);
        v27 = *(_WORD *)(v17 + 2);
        if ( v14 == v55 )
          *(_WORD *)(v17 + 2) = v27 & 0xFFFE;
        else
          *(_WORD *)(v17 + 2) = v27 | 1;
        *(_BYTE *)(v17 + 1) = *v15;
      }
      return v26;
    }
  }
}

```

## disassembly

```asm
0x100403a90  mov     rax, rsp
0x100403a93  mov     [rax+20h], r9
0x100403a97  mov     [rax+18h], r8
0x100403a9b  mov     [rax+10h], rdx
0x100403a9f  mov     [rax+8], rcx
0x100403aa3  push    rbx
0x100403aa4  push    rsi
0x100403aa5  push    rdi
0x100403aa6  push    r12
0x100403aa8  push    r13
0x100403aaa  push    r14
0x100403aac  push    r15
0x100403aae  sub     rsp, 110h
0x100403ab5  mov     qword ptr [rax-58h], 0FFFFFFFFFFFFFFFEh
0x100403abd  mov     r12, r9
0x100403ac0  mov     rsi, r8
0x100403ac3  mov     r14, rdx
0x100403ac6  mov     rbx, rcx
0x100403ac9  mov     [rsp+148h+var_D0], 64h ; 'd'
0x100403ad1  movzx   ecx, byte ptr [rdx]
0x100403ad4  lea     r15, ?tiBit@CTypeInfo@@2V1@B; CTypeInfo const CTypeInfo::tiBit
0x100403adb  movzx   eax, byte ptr [rcx+r15+45AE60h]
0x100403ae4  cmp     byte ptr [rax+r15+45BDA8h], 0
0x100403aed  jnz     loc_10045086E
0x100403af3  xor     edi, edi
0x100403af5  mov     eax, edi
0x100403af7  cmp     byte ptr [rsp+148h+arg_50], 0
0x100403aff  jz      loc_100406015
0x100403b05  test    byte ptr [r14+1], 10h
0x100403b0a  jnz     loc_10045089F
0x100403b10  test    byte ptr [r8+1], 10h
0x100403b15  jnz     loc_1004508AB
0x100403b1b  cmp     byte ptr [rbx], 3
0x100403b1e  jz      loc_100406E5D
0x100403b24  movzx   r9d, word ptr [r14+10h]
0x100403b29  mov     r13d, 0FFFFh
0x100403b2f  cmp     r9w, r13w
0x100403b33  jz      loc_1004508F3
0x100403b39  movzx   eax, byte ptr [r14]
0x100403b3d  movzx   ecx, byte ptr [rax+r15+45AE60h]
0x100403b46  cmp     byte ptr [rcx+r15+4F3B00h], 0
0x100403b4f  jnz     loc_1004508F3
0x100403b55  mov     dword ptr [rsp+148h+var_C0], 3
0x100403b60  xorps   xmm0, xmm0
0x100403b63  movdqu  [rsp+148h+var_C0+8], xmm0
0x100403b6c  mov     [rsp+148h+var_A8], edi
0x100403b73  movups  xmm1, xmmword ptr [rbx]
0x100403b76  movups  [rsp+148h+var_C0], xmm1
0x100403b7e  movups  xmm0, xmmword ptr [rbx+10h]
0x100403b82  movups  xmmword ptr [rsp+98h], xmm0
0x100403b8a  mov     r13d, 0FFFEh
0x100403b90  and     [rbx+2], r13w
0x100403b95  mov     [rsp+148h+var_98], rdi
0x100403b9d  mov     [rsp+148h+var_C8], rdi
0x100403ba5  mov     [rsp+148h+var_A0], edi
0x100403bac  mov     [rsp+148h+var_D4], edi
0x100403bb0  mov     [rsp+148h+var_D8], 0
0x100403bb5  movq    rax, xmm1
0x100403bba  mov     qword ptr [rsp+148h+var_C0], rax
0x100403bc2  shr     rax, 10h
0x100403bc6  and     al, 1
0x100403bc8  mov     byte ptr [rsp+148h+arg_50], al
0x100403bcf  mov     [rsp+148h+var_90], rdi
0x100403bd7  xorps   xmm0, xmm0
0x100403bda  movups  [rsp+148h+var_88], xmm0
0x100403be2  movups  [rsp+148h+var_78], xmm0
0x100403bea  mov     byte ptr [rsp+148h+var_88], 0
0x100403bf2  mov     dword ptr [rsp+148h+var_88+4], edi
0x100403bf9  mov     qword ptr [rsp+148h+var_88+8], 0FFFFFFFFFFFFFFFFh
0x100403c05  mov     word ptr [rsp+148h+var_78], di
0x100403c0d  mov     byte ptr [rsp+148h+var_78+2], 0
0x100403c15  mov     byte ptr [rsp+148h+var_78+3], 0
0x100403c1d  mov     byte ptr [rsp+148h+var_78+0Bh], 0
0x100403c25  mov     byte ptr [rsp+148h+var_78+0Ah], 0
0x100403c2d  mov     word ptr [rsp+148h+var_78+8], di
0x100403c35  mov     word ptr [rsp+148h+var_78+0Ch], di
0x100403c3d  mov     byte ptr [rsp+148h+var_78+0Eh], 0
0x100403c45  mov     byte ptr [rsp+148h+var_78+0Fh], 0
0x100403c4d  lea     rax, [rsp+148h+var_D7]
0x100403c52  mov     [rsp+148h+var_128], rax; bool *
0x100403c57  lea     r9, [rsp+148h+var_88]; struct CTypeInfo *
0x100403c5f  lea     r8, [rsp+148h+var_9C]; int *
0x100403c67  mov     rdx, rsi; struct CTypeInfo *
0x100403c6a  mov     rcx, r14; struct CTypeInfo *
0x100403c6d  call    ?FTwoStepConvert@ConvertUtils@@SA_NPEBVCTypeInfo@@0PEAJPEAV2@PEA_N@Z; ConvertUtils::FTwoStepConvert(CTypeInfo const *,CTypeInfo const *,long *,CTypeInfo *,bool *)
0x100403c72  test    al, al
0x100403c74  jnz     loc_100450AE0
0x100403c7a  test    r12, r12
0x100403c7d  jnz     loc_100403611
0x100403c83  lea     r9, [rsp+148h+var_D4]; int *
0x100403c88  lea     r8, [rsp+148h+var_C8]; unsigned __int8 **
0x100403c90  mov     rdx, rsi; struct CTypeInfo *
0x100403c93  mov     rcx, [rsp+148h+arg_28]; struct IMemObj *
0x100403c9b  call    ?AllocateConvertBuffer@@YAXPEAVIMemObj@@PEBVCTypeInfo@@PEAPEAEPEAH@Z; AllocateConvertBuffer(IMemObj *,CTypeInfo const *,uchar * *,int *)
0x100403ca0  mov     r9, [rsp+148h+var_C8]
0x100403ca8  mov     ecx, [rsp+148h+var_D4]
0x100403cac  jmp     short loc_100403CAF
0x100403caf  lea     rax, [rsp+148h+arg_50]
0x100403cb7  mov     [rsp+148h+var_E8], rax
0x100403cbc  mov     rax, [rsp+148h+arg_58]
0x100403cc4  mov     [rsp+148h+var_F0], rax
0x100403cc9  movzx   eax, [rsp+148h+arg_48]
0x100403cd1  mov     [rsp+148h+var_F8], al
0x100403cd5  movzx   eax, [rsp+148h+arg_40]
0x100403cdd  mov     [rsp+148h+var_100], al
0x100403ce1  movzx   eax, [rsp+148h+arg_38]
0x100403ce9  mov     [rsp+148h+var_108], al
0x100403ced  movzx   eax, [rsp+148h+arg_68]
0x100403cf5  mov     [rsp+148h+var_110], ax
0x100403cfa  mov     rax, [rsp+148h+arg_60]
0x100403d02  mov     [rsp+148h+var_118], rax
0x100403d07  mov     eax, [rsp+148h+arg_30]
0x100403d0e  mov     [rsp+148h+var_120], eax
0x100403d12  mov     dword ptr [rsp+148h+var_128], ecx
0x100403d16  mov     r8, rsi
0x100403d19  mov     rdx, r14
0x100403d1c  mov     rcx, rbx
0x100403d1f  call    ?ConvertToTiOneStep@CXVariant@@AEAAJPEBVCTypeInfo@@0PEAEKJPEBVCDefaultCollation@@FEW4EErrorHandling@@_NPEAUIBlobHandleFactory@@AEA_N@Z; CXVariant::ConvertToTiOneStep(CTypeInfo const *,CTypeInfo const *,uchar *,ulong,long,CDefaultCollation const *,short,uchar,EErrorHandling,bool,IBlobHandleFactory *,bool &)
0x100403d24  mov     [rsp+148h+var_D0], eax
0x100403d28  jmp     short loc_100403D2B
0x100403d2b  jmp     short loc_100403D2E
0x100403d2e  mov     rdx, gs:58h
0x100403d37  mov     rax, cs:__imp_SystemThread_TlsIndex
0x100403d3e  mov     ecx, [rax]
0x100403d40  mov     rax, cs:__imp_SystemThread_TlsOffset
0x100403d47  mov     r15d, [rax]
0x100403d4a  add     r15, [rdx+rcx*8]
0x100403d4e  mov     rcx, [r15+100h]
0x100403d55  test    rcx, rcx
0x100403d58  jz      loc_100450D68
0x100403d5e  cmp     dword ptr [rcx+22Ch], 0
0x100403d65  jnz     loc_100450D7B
0x100403d6b  mov     r15d, [rsp+148h+var_D0]
0x100403d70  test    r15d, r15d
0x100403d73  jnz     loc_100450DAA
0x100403d79  cmp     byte ptr [rsp+148h+arg_50], r15b
0x100403d81  jnz     loc_10041BCDB
0x100403d87  and     word ptr [rsp+148h+var_C0+2], r13w
0x100403d90  test    byte ptr [rsp+148h+var_C0+2], 1
0x100403d98  jnz     loc_10041BCEA
0x100403d9e  mov     dword ptr [rsp+148h+var_C0], 3
0x100403da9  xorps   xmm0, xmm0
0x100403dac  movdqu  [rsp+148h+var_C0+8], xmm0
0x100403db5  mov     [rsp+148h+var_A8], edi
0x100403dbc  mov     rcx, [rsp+148h+var_90]
0x100403dc4  test    rcx, rcx
0x100403dc7  jnz     loc_100450D88
0x100403dcd  cmp     [rsp+148h+var_D8], 0
0x100403dd2  jnz     loc_100450D95
0x100403dd8  movzx   eax, word ptr [rbx+2]
0x100403ddc  cmp     r12, [rsp+148h+var_C8]
0x100403de4  jnz     loc_10040E1CA
0x100403dea  and     ax, r13w
0x100403dee  mov     [rbx+2], ax
0x100403df2  movzx   eax, byte ptr [rsi]
0x100403df5  mov     [rbx+1], al
0x100403df8  jmp     short loc_100403DFB
0x100403dfb  mov     eax, r15d
0x100403dfe  add     rsp, 110h
0x100403e05  pop     r15
0x100403e07  pop     r14
0x100403e09  pop     r13
0x100403e0b  pop     r12
0x100403e0d  pop     rdi
0x100403e0e  pop     rsi
0x100403e0f  pop     rbx
0x100403e10  retn
0x100403611  mov     r9, r12
0x100403614  mov     [rsp+148h+var_C8], r12
0x10040361c  mov     ecx, [rsp+148h+arg_20]
0x100403623  mov     [rsp+148h+var_D4], ecx
0x100403627  jmp     loc_100403CAF
0x100406015  test    eax, eax
0x100406017  jz      loc_100403B05
0x10040601d  jmp     loc_1004508CB
0x100406e5d  movzx   eax, byte ptr [rsi+1]
0x100406e61  not     al
0x100406e63  test    al, 1
0x100406e65  jz      loc_1004508D6
0x100406e6b  test    byte ptr [rbx+2], 1
0x100406e6f  jnz     loc_1004508E1
0x100406e75  mov     dword ptr [rbx], 3
0x100406e7b  mov     [rbx+18h], edi
0x100406e7e  mov     [rbx+8], r12
0x100406e82  mov     [rbx+10h], rdi
0x100406e86  movzx   eax, byte ptr [rsi]
0x100406e89  mov     [rbx+1], al
0x100406e8c  xor     eax, eax
0x100406e8e  jmp     loc_100403DFE
0x10040e1ca  or      ax, 1
0x10040e1ce  mov     [rbx+2], ax
0x10040e1d2  movzx   eax, byte ptr [rsi]
0x10040e1d5  mov     [rbx+1], al
0x10040e1d8  jmp     loc_100403DFB
0x10041bcdb  or      word ptr [rsp+148h+var_C0+2], 1
0x10041bce4  jmp     loc_100403D90
0x10041bcea  mov     rdx, r14
0x10041bced  lea     rcx, [rsp+148h+var_C0]
0x10041bcf5  call    ??$ClearDeep@VCTypeInfo@@@CXVariant@@IEAAXPEBVCTypeInfo@@@Z; CXVariant::ClearDeep<CTypeInfo>(CTypeInfo const *)
0x10041bcfa  nop
0x10041bcfb  jmp     loc_100403D9E
0x10045086e  movzx   edx, byte ptr [r8]
0x100450872  movzx   eax, byte ptr [rdx+r15+45AE60h]
0x10045087b  cmp     byte ptr [rax+r15+45BDA8h], 0
0x100450884  jz      loc_100403AF3
0x10045088a  cmp     dl, cl
0x10045088c  jz      loc_100403AF3
0x100450892  mov     eax, 1
0x100450897  xor     edi, edi
0x100450899  jmp     loc_100403AF7
0x10045089f  cmp     cl, 0F0h
0x1004508a2  jz      loc_100403B10
0x1004508a8  jmp     short loc_1004508B5
0x1004508ab  cmp     byte ptr [r8], 0F0h
0x1004508af  jz      loc_100403B1B
0x1004508b5  mov     r8b, 1
0x1004508b8  mov     rdx, rsi
0x1004508bb  mov     rcx, r14
0x1004508be  call    ?CtCheckCast@@YA?AW4ECastType@@PEBVCTypeInfo@@0_N@Z; CtCheckCast(CTypeInfo const *,CTypeInfo const *,bool)
0x1004508c3  test    eax, eax
0x1004508c5  jnz     loc_100403B1B
0x1004508cb  mov     eax, 64h ; 'd'
0x1004508d0  jmp     loc_100403DFE
0x1004508d6  mov     eax, 8
0x1004508db  jmp     loc_100403DFE
0x1004508e1  mov     rdx, r14
0x1004508e4  mov     rcx, rbx
0x1004508e7  call    ??$ClearDeep@VCTypeInfo@@@CXVariant@@IEAAXPEBVCTypeInfo@@@Z; CXVariant::ClearDeep<CTypeInfo>(CTypeInfo const *)
0x1004508ec  nop
0x1004508ed  jmp     loc_100406E75
0x1004508f3  movzx   r8d, word ptr [rsi+10h]
0x1004508f8  cmp     r8w, r13w
0x1004508fc  jz      short loc_100450919
0x1004508fe  movzx   eax, byte ptr [rsi]
0x100450901  movzx   ecx, byte ptr [rax+r15+45AE60h]
0x10045090a  cmp     byte ptr [rcx+r15+4F3B00h], 0
0x100450913  jz      loc_100403B55
0x100450919  test    r12, r12
0x10045091c  jnz     loc_100403B55
0x100450922  movzx   ecx, byte ptr [r14]
0x100450926  cmp     cl, 0F1h
0x100450929  jz      loc_100403B55
0x10045092f  movzx   edx, byte ptr [rsi]
0x100450932  cmp     dl, 0F1h
0x100450935  jz      loc_100403B55
0x10045093b  movzx   r10d, byte ptr [rdx+r15+45AE60h]
0x100450944  cmp     [r10+r15+45BE40h], r12b
0x10045094c  jz      short loc_100450958
0x10045094e  cmp     r8w, r13w
0x100450952  jz      loc_100450A79
0x100450958  cmp     dl, 22h ; '"'
0x10045095b  jz      loc_100450A79
0x100450961  movzx   r11d, byte ptr [rcx+r15+45AE60h]
0x10045096a  cmp     byte ptr [r11+r15+45BE40h], 0
0x100450973  jz      short loc_10045097B
0x100450975  cmp     r9w, r13w
0x100450979  jz      short loc_100450980
0x10045097b  cmp     cl, 22h ; '"'
0x10045097e  jnz     short loc_1004509A9
0x100450980  cmp     byte ptr [r10+r15+4642E0h], 0
0x100450989  jz      short loc_100450991
0x10045098b  cmp     r8w, r13w
0x10045098f  jz      short loc_1004509A9
0x100450991  cmp     dl, 63h ; 'c'
0x100450994  jz      short loc_1004509A9
0x100450996  cmp     dl, 0F0h
0x100450999  jnz     loc_100450A79
0x10045099f  cmp     r8w, r13w
0x1004509a3  jnz     loc_100450A79
0x1004509a9  cmp     byte ptr [r11+r15+4642E0h], 0
0x1004509b2  jz      short loc_1004509BA
0x1004509b4  cmp     r9w, r13w
0x1004509b8  jz      short loc_1004509BF
0x1004509ba  cmp     cl, 63h ; 'c'
0x1004509bd  jnz     short loc_1004509DD
0x1004509bf  cmp     byte ptr [r10+r15+4642E0h], 0
0x1004509c8  jz      short loc_1004509D4
0x1004509ca  cmp     r8w, r13w
0x1004509ce  jz      loc_100450A79
0x1004509d4  cmp     dl, 63h ; 'c'
0x1004509d7  jz      loc_100450A79
0x1004509dd  cmp     cl, 0F0h
0x1004509e0  jnz     short loc_1004509F6
0x1004509e2  cmp     r9w, r13w
0x1004509e6  jnz     short loc_1004509F6
0x1004509e8  cmp     dl, cl
0x1004509ea  jnz     short loc_1004509F6
0x1004509ec  cmp     r8w, r13w
0x1004509f0  jz      loc_100450A79
0x1004509f6  cmp     byte ptr [r11+r15+4642A0h], 0
0x1004509ff  jz      short loc_100450A07
0x100450a01  cmp     r9w, r13w
0x100450a05  jz      short loc_100450A10
0x100450a07  cmp     cl, 23h ; '#'
0x100450a0a  jnz     loc_100403B55
0x100450a10  cmp     byte ptr [r10+r15+4642A0h], 0
0x100450a19  jz      short loc_100450A21
0x100450a1b  cmp     r8w, r13w
0x100450a1f  jz      short loc_100450A2A
0x100450a21  cmp     dl, 23h ; '#'
  ... truncated ...
```
