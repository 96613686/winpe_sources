# CPicturePasswordEnrollmentHandler::GetEnrollmentGestures(uchar *,ulong,uchar * *,ulong *)

- ea: `0x180006f80`
- end: `0x1800071b3`
- name: `?GetEnrollmentGestures@CPicturePasswordEnrollmentHandler@@UEAAJPEAEKPEAPEAEPEAK@Z`
- size: `563`
- prototype: `__int64 __fastcall(CPicturePasswordEnrollmentHandler *this, unsigned __int8 *, unsigned int, LPVOID *, unsigned int *)`
- caller_count: `0`
- callee_count: `11`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callees

- `0x180002610`
- `0x180005a10`
- `0x180006d54`
- `0x180006f80`
- `0x18000a67c`
- `0x18000b000`
- `0x18000b094`
- `0x18000c438`
- `0x18000c6d4`
- `0x180018f10`
- `0x18001c444`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180007132`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180007132`

## pseudocode

```c
__int64 __fastcall CPicturePasswordEnrollmentHandler::GetEnrollmentGestures(
        CPicturePasswordEnrollmentHandler *this,
        unsigned __int8 *a2,
        unsigned int a3,
        LPVOID *a4,
        unsigned int *a5)
{
  int CallerSID; // ebx
  __int64 v9; // r14
  BYTE *v10; // rsi
  unsigned __int64 v11; // r8
  int v12; // eax
  unsigned __int64 v13; // r8
  struct GESTURE_SIGNATURE *v14; // rdi
  __int64 v15; // r15
  unsigned __int64 v16; // rax
  __m128 v17; // xmm3
  __m128 v18; // xmm2
  __m128 v19; // xmm0
  __m128 v20; // xmm3
  void *v21; // rcx
  BYTE *pbData; // [rsp+30h] [rbp-61h] BYREF
  unsigned __int64 v24; // [rsp+38h] [rbp-59h] BYREF
  LPVOID pv; // [rsp+40h] [rbp-51h] BYREF
  struct GESTURE_SIGNATURE *v26; // [rsp+48h] [rbp-49h] BYREF
  BYTE *v27; // [rsp+50h] [rbp-41h] BYREF
  PSID pSid; // [rsp+58h] [rbp-39h] BYREF
  BYTE v29[32]; // [rsp+60h] [rbp-31h] BYREF
  BYTE v30[32]; // [rsp+80h] [rbp-11h] BYREF

  *a4 = 0;
  CallerSID = -2147024809;
  *a5 = 0;
  if ( a3 && (a3 & 0xF) == 0 )
  {
    pSid = 0;
    CallerSID = CImpersonateCaller::GetCallerSID(&pSid);
    if ( CallerSID >= 0 )
    {
      v27 = 0;
      v9 = a3;
      CallerSID = UnprotectMemory(1, a2, a3, &v27);
      if ( CallerSID >= 0 )
      {
        v10 = v27;
        CallerSID = _ConfirmPasswordBufferPadding((const unsigned __int16 *)v27, (unsigned __int64)a3 >> 1);
        if ( CallerSID >= 0 )
        {
          pbData = 0;
          v26 = 0;
          v24 = 0;
          CallerSID = CPicturePasswordVault::GetEnrollment(pSid, (unsigned __int16 **)&pbData, &v26, &v24);
          if ( CallerSID >= 0 )
          {
            v12 = _HashPassword(pbData, v30, v11);
            v14 = v26;
            CallerSID = v12;
            v15 = 60;
            if ( v12 >= 0 )
            {
              CallerSID = _HashPassword(v10, v29, v13);
              if ( CallerSID >= 0 )
              {
                CallerSID = -2147024891;
                v16 = 0;
                v17 = 0;
                do
                {
                  v18 = (__m128)_mm_cvtsi32_si128(*(_DWORD *)&v29[v16]);
                  v19 = (__m128)_mm_cvtsi32_si128(*(_DWORD *)&v30[v16]);
                  v16 += 4LL;
                  v17 = _mm_or_ps(
                          v17,
                          (__m128)_mm_unpacklo_epi16(
                                    _mm_unpacklo_epi8((__m128i)_mm_xor_ps(v18, v19), (__m128i)0LL),
                                    (__m128i)0LL));
                }
                while ( v16 < 0x20 );
                v20 = _mm_or_ps(v17, (__m128)_mm_srli_si128((__m128i)v17, 8));
                if ( !_mm_cvtsi128_si32((__m128i)_mm_or_ps(v20, (__m128)_mm_srli_si128((__m128i)v20, 4))) )
                {
                  pv = 0;
                  v24 = 0;
                  CallerSID = ProtectMemory(1, (const unsigned __int8 *)v14, 0x3Cu, (unsigned __int8 **)&pv, &v24);
                  if ( CallerSID >= 0 )
                  {
                    CallerSID = ULongLongToULong(v24, a5);
                    if ( CallerSID < 0 )
                    {
                      v21 = pv;
                    }
                    else
                    {
                      v21 = 0;
                      *a4 = pv;
                    }
                    CoTaskMemFree(v21);
                  }
                }
              }
            }
            if ( v14 )
            {
              do
              {
                *(_BYTE *)v14 = 0;
                v14 = (struct GESTURE_SIGNATURE *)((char *)v14 + 1);
                --v15;
              }
              while ( v15 );
            }
            SecureZeroString((unsigned __int16 *)pbData);
          }
          CCoTaskMemPtr<unsigned char>::~CCoTaskMemPtr<unsigned char>(&v26);
          CCoTaskMemPtr<unsigned char>::~CCoTaskMemPtr<unsigned char>(&pbData);
        }
        for ( ; v9; --v9 )
          *v10++ = 0;
      }
      CCoTaskMemPtr<unsigned char>::~CCoTaskMemPtr<unsigned char>(&v27);
    }
    CCoTaskMemPtr<unsigned char>::~CCoTaskMemPtr<unsigned char>(&pSid);
  }
  return (unsigned int)CallerSID;
}

```

## disassembly

```asm
0x180006f80  mov     [rsp-8+arg_0], rbx
0x180006f85  push    rbp
0x180006f86  push    rsi
0x180006f87  push    rdi
0x180006f88  push    r12
0x180006f8a  push    r13
0x180006f8c  push    r14
0x180006f8e  push    r15
0x180006f90  lea     rbp, [rsp-1Fh]
0x180006f95  sub     rsp, 0B0h
0x180006f9c  mov     rax, cs:__security_cookie
0x180006fa3  xor     rax, rsp
0x180006fa6  mov     [rbp+4Fh+var_40], rax
0x180006faa  mov     r13, [rbp+4Fh+arg_20]
0x180006fae  xor     r15d, r15d
0x180006fb1  mov     [r9], r15
0x180006fb4  mov     r12, r9
0x180006fb7  mov     edi, r8d
0x180006fba  mov     rsi, rdx
0x180006fbd  mov     ebx, 80070057h
0x180006fc2  mov     [r13+0], r15d
0x180006fc6  test    r8d, r8d
0x180006fc9  jz      loc_18000718A
0x180006fcf  test    dil, 0Fh
0x180006fd3  jnz     loc_18000718A
0x180006fd9  lea     rcx, [rbp+4Fh+pSid]; void **
0x180006fdd  mov     [rbp+4Fh+pSid], r15
0x180006fe1  call    ?GetCallerSID@CImpersonateCaller@@SAJPEAPEAX@Z; CImpersonateCaller::GetCallerSID(void * *)
0x180006fe6  mov     ebx, eax
0x180006fe8  test    eax, eax
0x180006fea  js      loc_180007181
0x180006ff0  lea     r9, [rbp+4Fh+var_90]; unsigned __int8 **
0x180006ff4  mov     [rbp+4Fh+var_90], r15
0x180006ff8  mov     r8d, edi; unsigned __int64
0x180006ffb  mov     rdx, rsi; unsigned __int8 *
0x180006ffe  mov     cl, 1; bool
0x180007000  mov     r14d, edi
0x180007003  call    ?UnprotectMemory@@YAJ_NPEAE_KPEAPEAE@Z; UnprotectMemory(bool,uchar *,unsigned __int64,uchar * *)
0x180007008  mov     ebx, eax
0x18000700a  test    eax, eax
0x18000700c  js      loc_180007178
0x180007012  mov     rsi, [rbp+4Fh+var_90]
0x180007016  mov     edx, edi
0x180007018  shr     rdx, 1; unsigned __int64
0x18000701b  mov     rcx, rsi; unsigned __int16 *
0x18000701e  call    ?_ConfirmPasswordBufferPadding@@YAJPEBG_K@Z; _ConfirmPasswordBufferPadding(ushort const *,unsigned __int64)
0x180007023  mov     ebx, eax
0x180007025  test    eax, eax
0x180007027  js      loc_180007167
0x18000702d  mov     rcx, [rbp+4Fh+pSid]; pSid
0x180007031  lea     r9, [rbp+4Fh+var_A8]; unsigned __int64 *
0x180007035  lea     r8, [rbp+4Fh+var_98]; struct GESTURE_SIGNATURE **
0x180007039  mov     [rbp+4Fh+pbData], r15
0x18000703d  lea     rdx, [rbp+4Fh+pbData]; unsigned __int16 **
0x180007041  mov     [rbp+4Fh+var_98], r15
0x180007045  mov     [rbp+4Fh+var_A8], r15
0x180007049  call    ?GetEnrollment@CPicturePasswordVault@@SAJPEAXPEAPEAGPEAPEAUGESTURE_SIGNATURE@@PEA_K@Z; CPicturePasswordVault::GetEnrollment(void *,ushort * *,GESTURE_SIGNATURE * *,unsigned __int64 *)
0x18000704e  mov     ebx, eax
0x180007050  test    eax, eax
0x180007052  js      loc_180007155
0x180007058  mov     rcx, [rbp+4Fh+pbData]; pbData
0x18000705c  lea     rdx, [rbp+4Fh+var_60]; BYTE *
0x180007060  call    ?_HashPassword@@YAJPEBGPEAE_K@Z; _HashPassword(ushort const *,uchar *,unsigned __int64)
0x180007065  mov     rdi, [rbp+4Fh+var_98]
0x180007069  mov     ebx, eax
0x18000706b  mov     r15d, 3Ch ; '<'
0x180007071  test    eax, eax
0x180007073  js      loc_180007138
0x180007079  lea     rdx, [rbp+4Fh+var_80]; BYTE *
0x18000707d  mov     rcx, rsi; pbData
0x180007080  call    ?_HashPassword@@YAJPEBGPEAE_K@Z; _HashPassword(ushort const *,uchar *,unsigned __int64)
0x180007085  mov     ebx, eax
0x180007087  test    eax, eax
0x180007089  js      loc_180007138
0x18000708f  mov     ebx, 80070005h
0x180007094  xor     eax, eax
0x180007096  xorps   xmm3, xmm3
0x180007099  movd    xmm2, dword ptr [rbp+rax+4Fh+var_80]
0x18000709f  xorps   xmm1, xmm1
0x1800070a2  movd    xmm0, dword ptr [rbp+rax+4Fh+var_60]
0x1800070a8  add     rax, 4
0x1800070ac  xorps   xmm2, xmm0
0x1800070af  punpcklbw xmm2, xmm1
0x1800070b3  punpcklwd xmm2, xmm1
0x1800070b7  orps    xmm3, xmm2
0x1800070ba  cmp     rax, 20h ; ' '
0x1800070be  jb      short loc_180007099
0x1800070c0  movdqa  xmm0, xmm3
0x1800070c4  psrldq  xmm0, 8
0x1800070c9  orps    xmm3, xmm0
0x1800070cc  movdqa  xmm0, xmm3
0x1800070d0  psrldq  xmm0, 4
0x1800070d5  orps    xmm3, xmm0
0x1800070d8  movd    eax, xmm3
0x1800070dc  test    eax, eax
0x1800070de  jnz     short loc_180007138
0x1800070e0  lea     rax, [rbp+4Fh+var_A8]
0x1800070e4  mov     [rbp+4Fh+pv], 0
0x1800070ec  lea     r9, [rbp+4Fh+pv]; unsigned __int8 **
0x1800070f0  mov     [rsp+0E0h+var_C0], rax; unsigned __int64 *
0x1800070f5  mov     r8, r15; unsigned __int64
0x1800070f8  mov     [rbp+4Fh+var_A8], 0
0x180007100  mov     rdx, rdi; unsigned __int8 *
0x180007103  mov     cl, 1; bool
0x180007105  call    ?ProtectMemory@@YAJ_NPEBE_KPEAPEAEPEA_K@Z; ProtectMemory(bool,uchar const *,unsigned __int64,uchar * *,unsigned __int64 *)
0x18000710a  mov     ebx, eax
0x18000710c  test    eax, eax
0x18000710e  js      short loc_180007138
0x180007110  mov     rcx, [rbp+4Fh+var_A8]; unsigned __int64
0x180007114  mov     rdx, r13; unsigned int *
0x180007117  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x18000711c  mov     ebx, eax
0x18000711e  test    eax, eax
0x180007120  js      short loc_18000712E
0x180007122  mov     rax, [rbp+4Fh+pv]
0x180007126  xor     ecx, ecx
0x180007128  mov     [r12], rax
0x18000712c  jmp     short loc_180007132
0x18000712e  mov     rcx, [rbp+4Fh+pv]; pv
0x180007132  call    cs:__imp_CoTaskMemFree
0x180007138  test    rdi, rdi
0x18000713b  jz      short loc_180007149
0x18000713d  mov     byte ptr [rdi], 0
0x180007140  inc     rdi
0x180007143  sub     r15, 1
0x180007147  jnz     short loc_18000713D
0x180007149  mov     rcx, [rbp+4Fh+pbData]; unsigned __int16 *
0x18000714d  call    ?SecureZeroString@@YAXPEAG@Z; SecureZeroString(ushort *)
0x180007152  xor     r15d, r15d
0x180007155  lea     rcx, [rbp+4Fh+var_98]
0x180007159  call    ??1?$CCoTaskMemPtr@E@@QEAA@XZ; CCoTaskMemPtr<uchar>::~CCoTaskMemPtr<uchar>(void)
0x18000715e  lea     rcx, [rbp+4Fh+pbData]
0x180007162  call    ??1?$CCoTaskMemPtr@E@@QEAA@XZ; CCoTaskMemPtr<uchar>::~CCoTaskMemPtr<uchar>(void)
0x180007167  test    r14, r14
0x18000716a  jz      short loc_180007178
0x18000716c  mov     [rsi], r15b
0x18000716f  inc     rsi
0x180007172  sub     r14, 1
0x180007176  jnz     short loc_18000716C
0x180007178  lea     rcx, [rbp+4Fh+var_90]
0x18000717c  call    ??1?$CCoTaskMemPtr@E@@QEAA@XZ; CCoTaskMemPtr<uchar>::~CCoTaskMemPtr<uchar>(void)
0x180007181  lea     rcx, [rbp+4Fh+pSid]
0x180007185  call    ??1?$CCoTaskMemPtr@E@@QEAA@XZ; CCoTaskMemPtr<uchar>::~CCoTaskMemPtr<uchar>(void)
0x18000718a  mov     eax, ebx
0x18000718c  mov     rcx, [rbp+4Fh+var_40]
0x180007190  xor     rcx, rsp; StackCookie
0x180007193  call    __security_check_cookie
0x180007198  mov     rbx, [rsp+0E0h+arg_0]
0x1800071a0  add     rsp, 0B0h
0x1800071a7  pop     r15
0x1800071a9  pop     r14
0x1800071ab  pop     r13
0x1800071ad  pop     r12
0x1800071af  pop     rdi
0x1800071b0  pop     rsi
0x1800071b1  pop     rbp
0x1800071b2  retn
```
