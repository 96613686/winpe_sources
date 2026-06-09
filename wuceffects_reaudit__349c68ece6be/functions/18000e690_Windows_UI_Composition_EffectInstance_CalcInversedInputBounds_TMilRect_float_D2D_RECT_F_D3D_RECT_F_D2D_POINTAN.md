# Windows::UI::Composition::EffectInstance::CalcInversedInputBounds(TMilRect_<float,D2D_RECT_F,D3D_RECT_F,D2D_POINTANDSIZE_F,RectUniqueness::NotNeeded> const &,uint,uint,TMilRect_<float,D2D_RECT_F,D3D_RECT_F,D2D_POINTANDSIZE_F,RectUniqueness::NotNeeded> const *,TMilRect_<float,D2D_RECT_F,D3D_RECT_F,D2D_POINTANDSIZE_F,RectUniqueness::NotNeeded> *,TMilRect_<float,D2D_RECT_F,D3D_RECT_F,D2D_POINTANDSIZE_F,RectUniqueness::NotNeeded> *,TMilRect_<float,D2D_RECT_F,D3D_RECT_F,D2D_POINTANDSIZE_F,RectUniqueness::NotNeeded> *)

- ea: `0x18000e690`
- end: `0x18000ebd7`
- name: `?CalcInversedInputBounds@EffectInstance@Composition@UI@Windows@@AEBAJAEBV?$TMilRect_@MUD2D_RECT_F@@UD3D_RECT_F@@UD2D_POINTANDSIZE_F@@UNotNeeded@RectUniqueness@@@@IIPEBV5@PEAV5@22@Z`
- size: `1351`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18000efc0`

## callees

- `0x18000e690`
- `0x18000fb90`
- `0x18001f204`
- `0x180021060`
- `0x18002b8b0`
- `0x18002e010`

## import_xrefs

- `msvcp_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x18000e801`
- `msvcp_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x18000e801`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000e716`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000e716`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000e708`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000e80b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000e708`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000e80b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000e819`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000e819`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Windows::UI::Composition::EffectInstance::CalcInversedInputBounds(
        __int64 a1,
        _OWORD *a2,
        unsigned int a3,
        unsigned int a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        __int64 a8)
{
  __int64 v11; // rdi
  SIZE_T v12; // rbx
  HANDLE ProcessHeap; // rax
  _OWORD *v14; // rax
  _OWORD *v15; // r14
  char *v16; // rbx
  __int64 v17; // rdi
  unsigned int i; // ecx
  unsigned int j; // ecx
  __int64 v20; // r15
  __int64 v21; // rcx
  unsigned int v22; // ebx
  HANDLE v23; // rax
  __int64 *v25; // rsi
  __int64 v26; // r11
  __int64 v27; // r10
  __int64 v28; // r10
  __int64 v29; // rbx
  unsigned int v30; // r11d
  __int64 v31; // rdx
  float v32; // xmm5_4
  float v33; // xmm2_4
  float v34; // xmm6_4
  float v35; // xmm1_4
  __int64 v36; // r9
  int v37; // ecx
  float v38; // xmm4_4
  BOOL v39; // ecx
  BOOL v40; // eax
  float v41; // xmm5_4
  BOOL v42; // ecx
  float v43; // xmm2_4
  float v44; // xmm3_4
  float v45; // xmm1_4
  BOOL v46; // eax
  int v47; // ecx
  unsigned __int64 v48; // r10
  __int64 v49; // rcx
  __int64 v50; // rax
  __int128 pExceptionObject; // [rsp+68h] [rbp-41h] BYREF
  __int64 v52; // [rsp+78h] [rbp-31h]
  __int128 v53; // [rsp+80h] [rbp-29h] BYREF

  *(_QWORD *)&v53 = a1;
  v11 = a3;
  *(_QWORD *)&pExceptionObject = a3;
  v12 = 16LL * a3;
  if ( !is_mul_ok(a3, 0x10u) )
    v12 = -1;
  ProcessHeap = GetProcessHeap();
  v14 = HeapAlloc(ProcessHeap, 0, v12);
  v15 = v14;
  if ( !v14 )
  {
    v52 = 0;
    *((_QWORD *)&pExceptionObject + 1) = "bad allocation";
    *(_QWORD *)&pExceptionObject = &std::bad_alloc::`vftable';
    throw (std::bad_alloc *)&pExceptionObject;
  }
  v16 = (char *)v14;
  if ( a3 )
  {
    do
    {
      TMilRect_<float,D2D_RECT_F,D3D_RECT_F,D2D_POINTANDSIZE_F,RectUniqueness::NotNeeded>::TMilRect_<float,D2D_RECT_F,D3D_RECT_F,D2D_POINTANDSIZE_F,RectUniqueness::NotNeeded>(v16);
      v16 += 16;
      --v11;
    }
    while ( v11 );
  }
  v17 = a3 - 1;
  v15[v17] = *a2;
  for ( i = 0; i < a3; ++i )
    *(_OWORD *)(a6 + 16LL * i) = TMilRect<float,D2D_RECT_F,D3D_RECT_F,RectUniqueness::NotNeeded>::sc_rcEmpty;
  for ( j = 0; j < a4; ++j )
    *(_OWORD *)(a7 + 16LL * j) = TMilRect<float,D2D_RECT_F,D3D_RECT_F,RectUniqueness::NotNeeded>::sc_rcEmpty;
  *(_OWORD *)a8 = TMilRect<float,D2D_RECT_F,D3D_RECT_F,RectUniqueness::NotNeeded>::sc_rcEmpty;
  v20 = v53;
  while ( (int)v17 >= 0 )
  {
    v21 = *(_QWORD *)(v20 + 16);
    if ( (__int64)(*(_QWORD *)(v21 + 56) - *(_QWORD *)(v21 + 48)) >> 3 <= (unsigned __int64)(unsigned int)v17
      || (_mm_lfence(),
          v25 = *(__int64 **)(*(_QWORD *)(v21 + 48) + 8 * v17),
          v26 = *v25,
          pExceptionObject = 0,
          v53 = 0,
          (__int64)(*(_QWORD *)(v21 + 56) - *(_QWORD *)(v21 + 48)) >> 3 <= (unsigned __int64)(unsigned int)v17) )
    {
LABEL_14:
      std::_Xout_of_range("invalid vector subscript");
      __debugbreak();
    }
    _mm_lfence();
    v27 = *(_QWORD *)(v20 + 32);
    if ( !v27 || (v28 = *(_QWORD *)(v27 + 8 * v17)) == 0 )
      v28 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v21 + 48) + 8 * v17) + 24LL);
    v29 = 16LL * (int)v17;
    (*(void (__fastcall **)(__int64, __int64, _OWORD *, __int64, __int128 *, __int128 *))(*(_QWORD *)v26 + 128LL))(
      v26,
      v28,
      &v15[(unsigned __int64)v29 / 0x10],
      v29 + a5,
      &pExceptionObject,
      &v53);
    *(_OWORD *)(v29 + a6) = v53;
    v30 = *((_DWORD *)v25 + 5);
    if ( v30 )
    {
      v31 = 0;
      v32 = *((float *)&pExceptionObject + 3);
      v33 = *((float *)&pExceptionObject + 2);
      v34 = *((float *)&pExceptionObject + 1);
      v35 = *(float *)&pExceptionObject;
      while ( 1 )
      {
        while ( 1 )
        {
          while ( 1 )
          {
            if ( (unsigned int)v31 >= v30 )
              goto LABEL_39;
            v36 = v25[1];
            v37 = *(_DWORD *)(v36 + 8 * v31);
            if ( v37 == 2 )
              break;
            v47 = v37 - 1;
            if ( v47 )
            {
              if ( v47 != 2 )
              {
                v22 = -2147024809;
                DoStackCaptureDirect(-2147024809, 0x305u);
                goto LABEL_16;
              }
              v48 = *(unsigned int *)(v36 + 8 * v31 + 4);
              v49 = *(_QWORD *)(v20 + 16);
              if ( (__int64)(*(_QWORD *)(v49 + 32) - *(_QWORD *)(v49 + 24)) >> 3 <= v48 )
                goto LABEL_14;
              _mm_lfence();
              v15[*(unsigned int *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v49 + 24) + 8 * v48) + 8LL) - 4LL)] = pExceptionObject;
            }
            else
            {
              v50 = *(unsigned int *)(v36 + 8 * v31 + 4);
              *(float *)&v15[v50] = v35;
              *((float *)&v15[v50] + 1) = v34;
              *((float *)&v15[v50] + 2) = v33;
              *((float *)&v15[v50] + 3) = v32;
            }
            v32 = *((float *)&pExceptionObject + 3);
            v33 = *((float *)&pExceptionObject + 2);
            v34 = *((float *)&pExceptionObject + 1);
            v35 = *(float *)&pExceptionObject;
            v31 = (unsigned int)(v31 + 1);
          }
          *(_OWORD *)(a7 + 16LL * *(unsigned int *)(v36 + 8 * v31 + 4)) = pExceptionObject;
          v38 = *(float *)(a8 + 8);
          v39 = v38 <= *(float *)a8 || *(float *)(a8 + 12) <= *(float *)(a8 + 4);
          v40 = v33 <= v35 || v32 <= v34;
          if ( v39 )
            break;
          if ( !v40 )
          {
            if ( *(float *)a8 > v35 )
              *(float *)a8 = v35;
            if ( *(float *)(a8 + 4) > v34 )
              *(float *)(a8 + 4) = v34;
            if ( v33 > v38 )
              *(float *)(a8 + 8) = v33;
            if ( v32 > *(float *)(a8 + 12) )
              *(float *)(a8 + 12) = v32;
          }
LABEL_31:
          v31 = (unsigned int)(v31 + 1);
        }
        if ( !v40 )
        {
          *(_OWORD *)a8 = pExceptionObject;
          goto LABEL_31;
        }
        *(_QWORD *)(a8 + 8) = 0;
        *(_QWORD *)a8 = 0;
        v31 = (unsigned int)(v31 + 1);
      }
    }
    v41 = *(float *)(a8 + 8);
    v42 = v41 <= *(float *)a8 || *(float *)(a8 + 12) <= *(float *)(a8 + 4);
    v43 = *((float *)&pExceptionObject + 3);
    v44 = *((float *)&pExceptionObject + 1);
    v45 = *((float *)&pExceptionObject + 2);
    v46 = *((float *)&pExceptionObject + 2) <= *(float *)&pExceptionObject
       || *((float *)&pExceptionObject + 3) <= *((float *)&pExceptionObject + 1);
    if ( v42 )
    {
      if ( !v46 )
      {
        *(_OWORD *)a8 = pExceptionObject;
        goto LABEL_39;
      }
      *(_QWORD *)(a8 + 8) = 0;
      *(_QWORD *)a8 = 0;
      v17 = (unsigned int)(v17 - 1);
    }
    else
    {
      if ( !v46 )
      {
        if ( *(float *)a8 > *(float *)&pExceptionObject )
          *(_DWORD *)a8 = pExceptionObject;
        if ( *(float *)(a8 + 4) > v44 )
          *(float *)(a8 + 4) = v44;
        if ( v45 > v41 )
          *(float *)(a8 + 8) = v45;
        if ( v43 > *(float *)(a8 + 12) )
          *(float *)(a8 + 12) = v43;
      }
LABEL_39:
      v17 = (unsigned int)(v17 - 1);
    }
  }
  v22 = 0;
LABEL_16:
  v23 = GetProcessHeap();
  HeapFree(v23, 0, v15);
  return v22;
}

```

## disassembly

```asm
0x18000e690  mov     [rsp-8+arg_8], rbx
0x18000e695  push    rbp
0x18000e696  push    rsi
0x18000e697  push    rdi
0x18000e698  push    r12
0x18000e69a  push    r13
0x18000e69c  push    r14
0x18000e69e  push    r15
0x18000e6a0  lea     rbp, [rsp-7]
0x18000e6a5  sub     rsp, 0B0h
0x18000e6ac  movaps  [rsp+0E0h+var_40], xmm6
0x18000e6b4  mov     rax, cs:__security_cookie
0x18000e6bb  xor     rax, rsp
0x18000e6be  mov     [rbp+37h+var_50], rax
0x18000e6c2  mov     r15d, r9d
0x18000e6c5  mov     esi, r8d
0x18000e6c8  mov     r12, rdx
0x18000e6cb  mov     qword ptr [rbp+37h+var_60], rcx
0x18000e6cf  mov     rax, [rbp+37h+arg_20]
0x18000e6d3  mov     [rbp+37h+var_88], rax
0x18000e6d7  mov     rax, [rbp+37h+arg_28]
0x18000e6db  mov     [rbp+37h+var_98], rax
0x18000e6df  mov     rax, [rbp+37h+arg_30]
0x18000e6e3  mov     [rbp+37h+var_90], rax
0x18000e6e7  mov     r13, [rbp+37h+arg_38]
0x18000e6eb  mov     edi, r8d
0x18000e6ee  mov     qword ptr [rbp+37h+pExceptionObject], rsi
0x18000e6f2  mov     eax, 10h
0x18000e6f7  mul     rsi
0x18000e6fa  mov     rbx, rax
0x18000e6fd  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18000e704  cmovb   rbx, rax
0x18000e708  call    cs:__imp_GetProcessHeap
0x18000e70e  mov     rcx, rax; hHeap
0x18000e711  mov     r8, rbx; dwBytes
0x18000e714  xor     edx, edx; dwFlags
0x18000e716  call    cs:__imp_HeapAlloc
0x18000e71c  mov     r14, rax
0x18000e71f  test    rax, rax
0x18000e722  jnz     short loc_18000E752
0x18000e724  xorps   xmm0, xmm0
0x18000e727  movups  [rbp+37h+pExceptionObject+8], xmm0
0x18000e72b  lea     rax, aBadAllocation; "bad allocation"
0x18000e732  mov     qword ptr [rbp+37h+pExceptionObject+8], rax
0x18000e736  lea     rax, ??_7bad_alloc@std@@6B@; const std::bad_alloc::`vftable'
0x18000e73d  mov     qword ptr [rbp+37h+pExceptionObject], rax
0x18000e741  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x18000e748  lea     rcx, [rbp+37h+pExceptionObject]; pExceptionObject
0x18000e74c  call    _CxxThrowException_0
0x18000e752  mov     [rbp+37h+var_A0], 0
0x18000e759  mov     [rbp+37h+var_80], r14
0x18000e75d  mov     rbx, r14
0x18000e760  test    esi, esi
0x18000e762  jz      short loc_18000E776
0x18000e764  mov     rcx, rbx
0x18000e767  call    ??0?$TMilRect_@MUD2D_RECT_F@@UD3D_RECT_F@@UD2D_POINTANDSIZE_F@@UNotNeeded@RectUniqueness@@@@QEAA@XZ; TMilRect_<float,D2D_RECT_F,D3D_RECT_F,D2D_POINTANDSIZE_F,RectUniqueness::NotNeeded>::TMilRect_<float,D2D_RECT_F,D3D_RECT_F,D2D_POINTANDSIZE_F,RectUniqueness::NotNeeded>(void)
0x18000e76c  add     rbx, 10h
0x18000e770  sub     rdi, 1
0x18000e774  jnz     short loc_18000E764
0x18000e776  mov     [rbp+37h+var_80], r14
0x18000e77a  movups  xmm0, xmmword ptr [r12]
0x18000e77f  lea     edi, [rsi-1]
0x18000e782  mov     eax, edi
0x18000e784  add     rax, rax
0x18000e787  movups  xmmword ptr [r14+rax*8], xmm0
0x18000e78c  xor     ecx, ecx
0x18000e78e  mov     r12, [rbp+37h+var_98]
0x18000e792  test    esi, esi
0x18000e794  jz      short loc_18000E7AD
0x18000e796  movups  xmm0, cs:?sc_rcEmpty@?$TMilRect@MUD2D_RECT_F@@UD3D_RECT_F@@UNotNeeded@RectUniqueness@@@@2V1@B; TMilRect<float,D2D_RECT_F,D3D_RECT_F,RectUniqueness::NotNeeded> const TMilRect<float,D2D_RECT_F,D3D_RECT_F,RectUniqueness::NotNeeded>::sc_rcEmpty
0x18000e79d  mov     eax, ecx
0x18000e79f  add     rax, rax
0x18000e7a2  movups  xmmword ptr [r12+rax*8], xmm0
0x18000e7a7  inc     ecx
0x18000e7a9  cmp     ecx, esi
0x18000e7ab  jb      short loc_18000E796
0x18000e7ad  xor     ecx, ecx
0x18000e7af  test    r15d, r15d
0x18000e7b2  jz      short loc_18000E7CF
0x18000e7b4  mov     rdx, [rbp+37h+var_90]
0x18000e7b8  movups  xmm0, cs:?sc_rcEmpty@?$TMilRect@MUD2D_RECT_F@@UD3D_RECT_F@@UNotNeeded@RectUniqueness@@@@2V1@B; TMilRect<float,D2D_RECT_F,D3D_RECT_F,RectUniqueness::NotNeeded> const TMilRect<float,D2D_RECT_F,D3D_RECT_F,RectUniqueness::NotNeeded>::sc_rcEmpty
0x18000e7bf  mov     eax, ecx
0x18000e7c1  add     rax, rax
0x18000e7c4  movups  xmmword ptr [rdx+rax*8], xmm0
0x18000e7c8  inc     ecx
0x18000e7ca  cmp     ecx, r15d
0x18000e7cd  jb      short loc_18000E7B8
0x18000e7cf  movups  xmm0, cs:?sc_rcEmpty@?$TMilRect@MUD2D_RECT_F@@UD3D_RECT_F@@UNotNeeded@RectUniqueness@@@@2V1@B; TMilRect<float,D2D_RECT_F,D3D_RECT_F,RectUniqueness::NotNeeded> const TMilRect<float,D2D_RECT_F,D3D_RECT_F,RectUniqueness::NotNeeded>::sc_rcEmpty
0x18000e7d6  movups  xmmword ptr [r13+0], xmm0
0x18000e7db  mov     r15, qword ptr [rbp+37h+var_60]
0x18000e7df  test    edi, edi
0x18000e7e1  js      short loc_18000E808
0x18000e7e3  mov     rcx, [r15+10h]
0x18000e7e7  mov     edx, edi
0x18000e7e9  mov     rax, [rcx+38h]
0x18000e7ed  sub     rax, [rcx+30h]
0x18000e7f1  sar     rax, 3
0x18000e7f5  cmp     rax, rdx
0x18000e7f8  ja      short loc_18000E850
0x18000e7fa  lea     rcx, aInvalidVectorS; "invalid vector subscript"
0x18000e801  call    cs:__imp_?_Xout_of_range@std@@YAXPEBD@Z; std::_Xout_of_range(char const *)
0x18000e807  int     3; Trap to Debugger
0x18000e808  mov     ebx, [rbp+37h+var_A0]
0x18000e80b  call    cs:__imp_GetProcessHeap
0x18000e811  mov     rcx, rax; hHeap
0x18000e814  mov     r8, r14; lpMem
0x18000e817  xor     edx, edx; dwFlags
0x18000e819  call    cs:__imp_HeapFree
0x18000e81f  mov     eax, ebx
0x18000e821  mov     rcx, [rbp+37h+var_50]
0x18000e825  xor     rcx, rsp; StackCookie
0x18000e828  call    __security_check_cookie
0x18000e82d  mov     rbx, [rsp+0E0h+arg_8]
0x18000e835  movaps  xmm6, [rsp+0E0h+var_40]
0x18000e83d  add     rsp, 0B0h
0x18000e844  pop     r15
0x18000e846  pop     r14
0x18000e848  pop     r13
0x18000e84a  pop     r12
0x18000e84c  pop     rdi
0x18000e84d  pop     rsi
0x18000e84e  pop     rbp
0x18000e84f  retn
0x18000e850  lfence
0x18000e853  mov     rax, [rcx+30h]
0x18000e857  mov     rsi, [rax+rdi*8]
0x18000e85b  mov     r11, [rsi]
0x18000e85e  xorps   xmm0, xmm0
0x18000e861  movups  [rbp+37h+pExceptionObject], xmm0
0x18000e865  xorps   xmm1, xmm1
0x18000e868  movups  [rbp+37h+var_60], xmm1
0x18000e86c  mov     rax, [rcx+38h]
0x18000e870  sub     rax, [rcx+30h]
0x18000e874  sar     rax, 3
0x18000e878  cmp     rax, rdx
0x18000e87b  jbe     loc_18000E7FA
0x18000e881  lfence
0x18000e884  mov     r10, [r15+20h]
0x18000e888  test    r10, r10
0x18000e88b  jnz     loc_18000EA1C
0x18000e891  mov     rax, [rcx+30h]
0x18000e895  mov     rcx, [rax+rdi*8]
0x18000e899  mov     r10, [rcx+18h]
0x18000e89d  movsxd  rbx, edi
0x18000e8a0  shl     rbx, 4
0x18000e8a4  mov     rax, [r11]
0x18000e8a7  mov     r9, [rbp+37h+var_88]
0x18000e8ab  add     r9, rbx
0x18000e8ae  lea     r8, [rbx+r14]
0x18000e8b2  lea     rcx, [rbp+37h+var_60]
0x18000e8b6  mov     [rsp+0E0h+var_B8], rcx
0x18000e8bb  lea     rcx, [rbp+37h+pExceptionObject]
0x18000e8bf  mov     [rsp+0E0h+var_C0], rcx
0x18000e8c4  mov     rdx, r10
0x18000e8c7  mov     rcx, r11
0x18000e8ca  mov     rax, [rax+80h]
0x18000e8d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e8d6  movups  xmm0, [rbp+37h+var_60]
0x18000e8da  movups  xmmword ptr [rbx+r12], xmm0
0x18000e8df  mov     r11d, [rsi+14h]
0x18000e8e3  test    r11d, r11d
0x18000e8e6  jz      loc_18000E99C
0x18000e8ec  xor     edx, edx
0x18000e8ee  movss   xmm5, dword ptr [rbp+37h+pExceptionObject+0Ch]
0x18000e8f3  movss   xmm2, dword ptr [rbp+37h+pExceptionObject+8]
0x18000e8f8  movss   xmm6, dword ptr [rbp+37h+pExceptionObject+4]
0x18000e8fd  movss   xmm1, dword ptr [rbp+37h+pExceptionObject]
0x18000e902  cmp     edx, r11d
0x18000e905  jnb     loc_18000EA15
0x18000e90b  mov     r9, [rsi+8]
0x18000e90f  mov     ecx, [r9+rdx*8]
0x18000e913  cmp     ecx, 2
0x18000e916  jnz     loc_18000EA56
0x18000e91c  mov     eax, [r9+rdx*8+4]
0x18000e921  add     rax, rax
0x18000e924  movups  xmm0, [rbp+37h+pExceptionObject]
0x18000e928  mov     rcx, [rbp+37h+var_90]
0x18000e92c  movups  xmmword ptr [rcx+rax*8], xmm0
0x18000e930  movss   xmm3, dword ptr [r13+0]
0x18000e936  movss   xmm4, dword ptr [r13+8]
0x18000e93c  comiss  xmm4, xmm3
0x18000e93f  ja      loc_18000EA2E
0x18000e945  mov     ecx, 1
0x18000e94a  comiss  xmm2, xmm1
0x18000e94d  ja      loc_18000EA46
0x18000e953  mov     eax, 1
0x18000e958  test    ecx, ecx
0x18000e95a  jz      loc_18000EB1E
0x18000e960  test    eax, eax
0x18000e962  jnz     loc_18000EBA8
0x18000e968  ucomiss xmm1, xmm1
0x18000e96b  jp      loc_18000EBA8
0x18000e971  ucomiss xmm6, xmm6
0x18000e974  jp      loc_18000EBA8
0x18000e97a  ucomiss xmm2, xmm2
0x18000e97d  jp      loc_18000EBA8
0x18000e983  ucomiss xmm5, xmm5
0x18000e986  jp      loc_18000EBA8
0x18000e98c  movups  xmm0, [rbp+37h+pExceptionObject]
0x18000e990  movups  xmmword ptr [r13+0], xmm0
0x18000e995  inc     edx
0x18000e997  jmp     loc_18000E902
0x18000e99c  movss   xmm4, dword ptr [r13+0]
0x18000e9a2  movss   xmm5, dword ptr [r13+8]
0x18000e9a8  comiss  xmm5, xmm4
0x18000e9ab  ja      loc_18000EA7A
0x18000e9b1  mov     ecx, 1
0x18000e9b6  movss   xmm2, dword ptr [rbp+37h+pExceptionObject+0Ch]
0x18000e9bb  movss   xmm3, dword ptr [rbp+37h+pExceptionObject+4]
0x18000e9c0  movss   xmm1, dword ptr [rbp+37h+pExceptionObject+8]
0x18000e9c5  movss   xmm0, dword ptr [rbp+37h+pExceptionObject]
0x18000e9ca  comiss  xmm1, xmm0
0x18000e9cd  ja      loc_18000EA92
0x18000e9d3  mov     eax, 1
0x18000e9d8  test    ecx, ecx
0x18000e9da  jz      loc_18000EB63
0x18000e9e0  test    eax, eax
0x18000e9e2  jnz     loc_18000EBBF
0x18000e9e8  ucomiss xmm0, xmm0
0x18000e9eb  jp      loc_18000EBBF
0x18000e9f1  ucomiss xmm3, xmm3
0x18000e9f4  jp      loc_18000EBBF
0x18000e9fa  ucomiss xmm1, xmm1
0x18000e9fd  jp      loc_18000EBBF
0x18000ea03  ucomiss xmm2, xmm2
0x18000ea06  jp      loc_18000EBBF
0x18000ea0c  movups  xmm0, [rbp+37h+pExceptionObject]
0x18000ea10  movups  xmmword ptr [r13+0], xmm0
0x18000ea15  dec     edi
0x18000ea17  jmp     loc_18000E7DF
0x18000ea1c  mov     r10, [r10+rdi*8]
0x18000ea20  test    r10, r10
0x18000ea23  jnz     loc_18000E89D
0x18000ea29  jmp     loc_18000E891
0x18000ea2e  movss   xmm0, dword ptr [r13+0Ch]
0x18000ea34  comiss  xmm0, dword ptr [r13+4]
0x18000ea39  jbe     loc_18000E945
0x18000ea3f  xor     ecx, ecx
0x18000ea41  jmp     loc_18000E94A
0x18000ea46  comiss  xmm5, xmm6
0x18000ea49  jbe     loc_18000E953
0x18000ea4f  xor     eax, eax
0x18000ea51  jmp     loc_18000E958
0x18000ea56  sub     ecx, 1
0x18000ea59  jz      loc_18000EAE0
0x18000ea5f  cmp     ecx, 2
0x18000ea62  jz      short loc_18000EAA2
0x18000ea64  mov     ebx, 80070057h
0x18000ea69  mov     edx, 305h; unsigned int
0x18000ea6e  mov     ecx, ebx; int
0x18000ea70  call    ?DoStackCaptureDirect@@YAXJI@Z; DoStackCaptureDirect(long,uint)
0x18000ea75  jmp     loc_18000E80B
0x18000ea7a  movss   xmm0, dword ptr [r13+0Ch]
0x18000ea80  comiss  xmm0, dword ptr [r13+4]
0x18000ea85  jbe     loc_18000E9B1
0x18000ea8b  xor     ecx, ecx
0x18000ea8d  jmp     loc_18000E9B6
0x18000ea92  comiss  xmm2, xmm3
0x18000ea95  jbe     loc_18000E9D3
0x18000ea9b  xor     eax, eax
0x18000ea9d  jmp     loc_18000E9D8
0x18000eaa2  mov     r10d, [r9+rdx*8+4]
0x18000eaa7  mov     rcx, [r15+10h]
0x18000eaab  mov     rax, [rcx+20h]
0x18000eaaf  sub     rax, [rcx+18h]
0x18000eab3  sar     rax, 3
0x18000eab7  cmp     rax, r10
0x18000eaba  jbe     loc_18000E7FA
0x18000eac0  lfence
0x18000eac3  movups  xmm0, [rbp+37h+pExceptionObject]
0x18000eac7  mov     rax, [rcx+18h]
0x18000eacb  mov     rcx, [rax+r10*8]
0x18000eacf  mov     rax, [rcx+8]
0x18000ead3  mov     ecx, [rax-4]
0x18000ead6  add     rcx, rcx
0x18000ead9  movups  xmmword ptr [r14+rcx*8], xmm0
0x18000eade  jmp     short loc_18000EB03
0x18000eae0  mov     eax, [r9+rdx*8+4]
0x18000eae5  add     rax, rax
0x18000eae8  movss   dword ptr [r14+rax*8], xmm1
0x18000eaee  movss   dword ptr [r14+rax*8+4], xmm6
0x18000eaf5  movss   dword ptr [r14+rax*8+8], xmm2
0x18000eafc  movss   dword ptr [r14+rax*8+0Ch], xmm5
0x18000eb03  movss   xmm5, dword ptr [rbp+37h+pExceptionObject+0Ch]
0x18000eb08  movss   xmm2, dword ptr [rbp+37h+pExceptionObject+8]
0x18000eb0d  movss   xmm6, dword ptr [rbp+37h+pExceptionObject+4]
0x18000eb12  movss   xmm1, dword ptr [rbp+37h+pExceptionObject]
0x18000eb17  inc     edx
0x18000eb19  jmp     loc_18000E902
0x18000eb1e  test    eax, eax
0x18000eb20  jnz     loc_18000E995
0x18000eb26  comiss  xmm3, xmm1
0x18000eb29  jbe     short loc_18000EB31
0x18000eb2b  movss   dword ptr [r13+0], xmm1
0x18000eb31  movss   xmm0, dword ptr [r13+4]
0x18000eb37  comiss  xmm0, xmm6
0x18000eb3a  jbe     short loc_18000EB42
0x18000eb3c  movss   dword ptr [r13+4], xmm6
0x18000eb42  comiss  xmm2, xmm4
0x18000eb45  jbe     short loc_18000EB4D
  ... truncated ...
```
