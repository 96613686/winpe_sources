# _Windows::UI::Composition::EffectInstance::SetAnimatableProperty_::_4_::_lambda_1_::operator()

- ea: `0x180013ca0`
- end: `0x1800141fc`
- name: `_Windows::UI::Composition::EffectInstance::SetAnimatableProperty_::_4_::_lambda_1_::operator()`
- size: `1372`
- prototype: `unsigned int *__fastcall(__int64 *)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180013c7c`

## callees

- `0x180013a70`
- `0x180013ca0`
- `0x180014370`
- `0x18001a550`
- `0x18001c314`
- `0x1800217d0`
- `0x180021cd4`
- `0x180026134`
- `0x18002b8b0`
- `0x18002e010`

## import_xrefs

- `msvcp_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x180013d04`
- `msvcp_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x180013d04`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x1800141d1`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x1800141d1`

## pseudocode

```c
unsigned int *__fastcall Windows::UI::Composition::EffectInstance::SetAnimatableProperty_::_4_::_lambda_1_::operator()(
        __int64 *a1)
{
  unsigned __int64 v2; // rdx
  _QWORD *v3; // rcx
  __int64 v4; // rbp
  __int64 v5; // r15
  unsigned __int64 v6; // rdx
  __int64 **v7; // rbx
  __int64 *v8; // rsi
  int v9; // edx
  unsigned int v10; // eax
  __int64 v11; // r14
  __int64 v12; // r12
  __int64 v13; // rax
  unsigned __int64 v14; // kr10_8
  bool v15; // cf
  SIZE_T v16; // rax
  _QWORD *v17; // rax
  _QWORD *v18; // rbx
  __int64 v19; // rdx
  unsigned __int64 v20; // r13
  __int64 v21; // r12
  __int64 v22; // rax
  __int64 v23; // rbx
  __int64 v24; // r8
  __int64 v25; // r14
  int v26; // eax
  float *v27; // rdx
  __int64 v28; // rbx
  float *v29; // rsi
  void (__fastcall *v30)(float *); // rax
  unsigned __int64 v31; // rsi
  __int64 v32; // rdx
  __int64 v33; // rbx
  __int64 v34; // rax
  __int64 v35; // r8
  __int64 v36; // r10
  __int64 v37; // r12
  unsigned __int64 v38; // r14
  __int64 v39; // rcx
  __int64 v40; // r9
  __int64 v41; // rcx
  __int64 v42; // rax
  __int64 v43; // rcx
  __int64 v44; // rdx
  char v45; // cl
  unsigned int *result; // rax
  __int64 v47; // rcx
  const void **v48; // rbx
  SIZE_T v49; // r14
  void *v50; // rax
  void *v51; // rcx
  unsigned __int64 v52; // rdx
  __int64 v53; // r8
  __int128 *v54; // rax
  __int128 v55; // xmm0
  __int64 v56; // xmm1_8
  __int64 v57; // rax
  __int64 v58; // [rsp+30h] [rbp-138h]
  __int64 v59; // [rsp+38h] [rbp-130h]
  __int64 v60; // [rsp+40h] [rbp-128h]
  _BYTE pExceptionObject[288]; // [rsp+48h] [rbp-120h] BYREF
  void *retaddr; // [rsp+168h] [rbp+0h]
  int v63; // [rsp+170h] [rbp+8h] BYREF
  unsigned int v64; // [rsp+178h] [rbp+10h]
  __int64 v65; // [rsp+180h] [rbp+18h] BYREF
  __int64 v66; // [rsp+188h] [rbp+20h] BYREF

  v2 = *((unsigned int *)a1 + 2);
  v3 = *(_QWORD **)(*a1 + 16);
  v4 = v3[9];
  if ( 0xAAAAAAAAAAAAAAABuLL * ((v3[10] - v4) >> 3) <= v2 )
    goto LABEL_3;
  v5 = 3 * v2;
  v6 = *(unsigned int *)(v4 + 24 * v2 + 8);
  if ( (__int64)(v3[7] - v3[6]) >> 3 <= v6 )
    goto LABEL_3;
  _mm_lfence();
  v7 = *(__int64 ***)(v3[6] + 8 * v6);
  v8 = *v7;
  v64 = *((_DWORD *)v7 + 4);
  v63 = 0;
  if ( (*(unsigned __int8 (__fastcall **)(__int64 *, int *))(*v8 + 48))(v8, &v63)
    && *(_DWORD *)(v4 + 8 * v5 + 12) == v63 )
  {
    if ( *((_DWORD *)a1 + 3) != 104 || *(_DWORD *)(v4 + 8 * v5 + 20) != 1 )
    {
      wil::ResultException::ResultException((wil::ResultException *)pExceptionObject, v9);
      throw (wil::ResultException *)pExceptionObject;
    }
    v52 = *((unsigned int *)v7[1] + 1);
    v53 = *(_QWORD *)(*a1 + 64);
    if ( 0xAAAAAAAAAAAAAAABuLL * ((*(_QWORD *)(*a1 + 72) - v53) >> 3) > v52 )
    {
      v54 = (__int128 *)a1[2];
      v45 = 1;
      v55 = *v54;
      v56 = *((_QWORD *)v54 + 2);
      v57 = 3 * v52;
      *(_OWORD *)(v53 + 8 * v57) = v55;
      *(_QWORD *)(v53 + 8 * v57 + 16) = v56;
      goto LABEL_31;
    }
LABEL_3:
    std::_Xout_of_range("invalid vector subscript");
    __debugbreak();
  }
  if ( !*(_QWORD *)(*a1 + 32) )
  {
    v10 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(*(_QWORD *)(*a1 + 16) + 16LL) + 80LL))(*(_QWORD *)(*a1 + 16) + 16LL);
    v11 = *a1;
    v12 = v10;
    v14 = v10;
    v13 = 8LL * v10;
    if ( !is_mul_ok(v14, 8u) )
      v13 = -1;
    v15 = __CFADD__(v13, 8);
    v16 = v13 + 8;
    if ( v15 )
      v16 = -1;
    v17 = operator new[](v16);
    if ( v17 )
    {
      v18 = v17 + 1;
      *v17 = v12;
      `eh vector constructor iterator'(
        v17 + 1,
        8u,
        (unsigned int)v12,
        std::unique_ptr<unsigned char [0]>::unique_ptr<unsigned char [0]>,
        std::unique_ptr<unsigned char [0]>::~unique_ptr<unsigned char [0]>);
    }
    else
    {
      v18 = 0;
    }
    v19 = *(_QWORD *)(v11 + 32);
    *(_QWORD *)(v11 + 32) = v18;
    if ( v19 )
      std::default_delete<std::unique_ptr<unsigned char [0]> [0]>::operator()<std::unique_ptr<unsigned char [0]>,0>();
  }
  v20 = *(unsigned int *)(v4 + 8 * v5 + 8);
  v21 = *(_QWORD *)(*a1 + 32);
  v58 = v21;
  if ( !*(_QWORD *)(v21 + 8 * v20) )
  {
    v47 = *(_QWORD *)(*a1 + 16);
    if ( (__int64)(*(_QWORD *)(v47 + 56) - *(_QWORD *)(v47 + 48)) >> 3 <= v20 )
      goto LABEL_3;
    _mm_lfence();
    v48 = *(const void ***)(*(_QWORD *)(v47 + 48) + 8 * v20);
    v49 = (*(unsigned int (__fastcall **)(const void *))(*(_QWORD *)*v48 + 136LL))(*v48);
    v50 = operator new[](v49);
    v51 = *(void **)(v21 + 8 * v20);
    *(_QWORD *)(v21 + 8 * v20) = v50;
    if ( v51 )
      operator delete(v51);
    memcpy_0(*(void **)(v21 + 8 * v20), v48[3], v49);
  }
  v22 = *v8;
  v23 = *(unsigned int *)(v4 + 8 * v5 + 12);
  LODWORD(v65) = 0;
  v66 = 0;
  (*(void (__fastcall **)(__int64 *, __int64 *, __int64 *))(v22 + 144))(v8, &v65, &v66);
  v25 = v66;
  v26 = *(_DWORD *)(v4 + 8 * v5 + 20);
  v27 = (float *)a1[2];
  v28 = 32 * v23;
  v29 = (float *)(*(_QWORD *)(v21 + 8 * v20) + *(unsigned int *)(v28 + v66 + 8));
  if ( v26 == 1 )
  {
    memcpy_0(
      (void *)(*(_QWORD *)(v21 + 8 * v20) + *(unsigned int *)(v28 + v66 + 8)),
      v27,
      4LL * *(unsigned int *)(v28 + v66 + 20));
  }
  else
  {
    switch ( v26 )
    {
      case 2:
        *v29 = *v27;
        break;
      case 3:
        v29[1] = *v27;
        break;
      case 4:
        v29[2] = *v27;
        break;
      case 5:
        v29[3] = *v27;
        break;
      case 7:
        *v29 = *v27 * 57.295776;
        break;
      case 9:
        *v29 = *v27;
        v29[1] = v27[1];
        v29[2] = v27[2];
        break;
      case 10:
        *v29 = *v27;
        v29[1] = v27[1];
        v29[2] = v27[2];
        v29[3] = v27[3];
        break;
      default:
        ModuleFailFastForHRESULT(2147549183LL, retaddr, v24);
    }
  }
  v30 = *(void (__fastcall **)(float *))(v28 + v25 + 24);
  if ( v30 )
    v30(v29);
  v31 = v64;
  v32 = *(_QWORD *)(*a1 + 40);
  v59 = v32;
  if ( (*(_QWORD *)(*a1 + 48) - v32) >> 4 <= (unsigned __int64)v64 )
    goto LABEL_3;
  v33 = 16LL * v64;
  if ( *(_QWORD *)(v32 + v33) )
  {
    v34 = *(_QWORD *)(*a1 + 24);
    v35 = *(_QWORD *)(v34 + 16);
    if ( 0xF0F0F0F0F0F0F0F1uLL * ((*(_QWORD *)(v34 + 24) - v35) >> 3) <= v64 )
      goto LABEL_3;
    v36 = 136LL * v64;
    v37 = 0;
    v60 = v36;
    v38 = 0x8E38E38E38E38E39uLL * ((__int64)(*(_QWORD *)(v35 + v36 + 48) - *(_QWORD *)(v35 + v36 + 40)) >> 3);
    if ( (_DWORD)v38 )
    {
      do
      {
        v39 = *(_QWORD *)(*a1 + 24);
        v40 = *(_QWORD *)(v39 + 16);
        if ( 0xF0F0F0F0F0F0F0F1uLL * ((*(_QWORD *)(v39 + 24) - v40) >> 3) <= v31 )
          goto LABEL_3;
        v41 = *(_QWORD *)(v40 + v36 + 40);
        if ( 0x8E38E38E38E38E39uLL * ((*(_QWORD *)(v40 + v36 + 48) - v41) >> 3) <= (unsigned int)v37 )
          goto LABEL_3;
        if ( *(_DWORD *)(v41 + 72 * v37) == *(_DWORD *)(v4 + 8 * v5 + 8) )
        {
          v42 = *(_QWORD *)(v32 + 16LL * (unsigned int)v31) + *(unsigned int *)(v41 + 72 * v37 + 4);
          v43 = *(_QWORD *)(v41 + 72 * v37 + 64);
          v65 = v42;
          v66 = *(_QWORD *)(v58 + 8 * v20);
          if ( !v43 )
          {
            std::_Xbad_function_call();
            __debugbreak();
          }
          (*(void (__fastcall **)(__int64, __int64 *, __int64 *))(*(_QWORD *)v43 + 16LL))(v43, &v66, &v65);
          v32 = v59;
          v36 = v60;
        }
        v37 = (unsigned int)(v37 + 1);
      }
      while ( (unsigned int)v37 < (unsigned int)v38 );
    }
  }
  v44 = *(_QWORD *)(*a1 + 40);
  if ( (*(_QWORD *)(*a1 + 48) - v44) >> 4 <= v31 )
    goto LABEL_3;
  v45 = 0;
  ++*(_DWORD *)(v44 + v33 + 8);
LABEL_31:
  *(_BYTE *)a1[3] = v45;
  result = (unsigned int *)a1[4];
  *result = v64;
  return result;
}

```

## disassembly

```asm
0x180013ca0  push    rbx
0x180013ca2  push    rbp
0x180013ca3  push    rsi
0x180013ca4  push    rdi
0x180013ca5  push    r12
0x180013ca7  push    r13
0x180013ca9  push    r14
0x180013cab  push    r15
0x180013cad  sub     rsp, 128h
0x180013cb4  mov     rax, [rcx]
0x180013cb7  mov     rdi, rcx
0x180013cba  mov     edx, [rcx+8]
0x180013cbd  mov     r12, 0AAAAAAAAAAAAAAABh
0x180013cc7  mov     rcx, [rax+10h]
0x180013ccb  mov     rbp, [rcx+48h]
0x180013ccf  mov     rax, [rcx+50h]
0x180013cd3  sub     rax, rbp
0x180013cd6  sar     rax, 3
0x180013cda  imul    rax, r12
0x180013cde  cmp     rax, rdx
0x180013ce1  jbe     short loc_180013CFD
0x180013ce3  mov     rax, [rcx+38h]
0x180013ce7  lea     r15, [rdx+rdx*2]
0x180013ceb  sub     rax, [rcx+30h]
0x180013cef  mov     edx, [rbp+r15*8+8]
0x180013cf4  sar     rax, 3
0x180013cf8  cmp     rax, rdx
0x180013cfb  ja      short loc_180013D0B
0x180013cfd  lea     rcx, aInvalidVectorS; "invalid vector subscript"
0x180013d04  call    cs:__imp_?_Xout_of_range@std@@YAXPEBD@Z; std::_Xout_of_range(char const *)
0x180013d0a  int     3; Trap to Debugger
0x180013d0b  lfence
0x180013d0e  mov     rax, [rcx+30h]
0x180013d12  xor     r14d, r14d
0x180013d15  mov     rbx, [rax+rdx*8]
0x180013d19  lea     rdx, [rsp+168h+arg_0]
0x180013d21  mov     rsi, [rbx]
0x180013d24  mov     eax, [rbx+10h]
0x180013d27  mov     rcx, rsi
0x180013d2a  mov     [rsp+168h+arg_8], eax
0x180013d31  mov     [rsp+168h+arg_0], r14d
0x180013d39  mov     rax, [rsi]
0x180013d3c  mov     rax, [rax+30h]
0x180013d40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013d45  test    al, al
0x180013d47  jnz     loc_1800140C9
0x180013d4d  mov     rax, [rdi]
0x180013d50  cmp     [rax+20h], r14
0x180013d54  jnz     loc_180013DDF
0x180013d5a  mov     rcx, [rax+10h]
0x180013d5e  mov     rax, [rcx+10h]
0x180013d62  add     rcx, 10h
0x180013d66  mov     rax, [rax+50h]
0x180013d6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013d6f  mov     r14, [rdi]
0x180013d72  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180013d79  mov     r12d, eax
0x180013d7c  mov     eax, 8
0x180013d81  mul     r12
0x180013d84  cmovb   rax, rcx
0x180013d88  add     rax, 8
0x180013d8c  cmovb   rax, rcx
0x180013d90  mov     rcx, rax; dwBytes
0x180013d93  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180013d98  test    rax, rax
0x180013d9b  jz      loc_18001414A
0x180013da1  lea     rbx, [rax+8]
0x180013da5  mov     [rax], r12
0x180013da8  lea     rax, ??1?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@std@@@std@@QEAA@XZ; std::unique_ptr<uchar [0]>::~unique_ptr<uchar [0]>(void)
0x180013daf  mov     rcx, rbx; void *
0x180013db2  lea     r9, ??$?0U?$default_delete@$$BY0A@E@std@@$0A@@?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@std@@@std@@QEAA@XZ; void (*)(void *)
0x180013db9  mov     [rsp+168h+var_148], rax; void (*)(void *)
0x180013dbe  mov     r8d, r12d; unsigned __int64
0x180013dc1  mov     edx, 8; unsigned __int64
0x180013dc6  call    ??_L@YAXPEAX_K1P6AX0@Z2@Z; `eh vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *),void (*)(void *))
0x180013dcb  mov     rdx, [r14+20h]
0x180013dcf  mov     [r14+20h], rbx
0x180013dd3  test    rdx, rdx
0x180013dd6  jnz     loc_180014182
0x180013ddc  xor     r14d, r14d
0x180013ddf  mov     rax, [rdi]
0x180013de2  mov     r13d, [rbp+r15*8+8]
0x180013de7  mov     r12, [rax+20h]
0x180013deb  mov     [rsp+168h+var_138], r12
0x180013df0  cmp     qword ptr [r12+r13*8], 0
0x180013df5  jz      loc_180014023
0x180013dfb  mov     rax, [rsi]
0x180013dfe  lea     r8, [rsp+168h+arg_18]
0x180013e06  mov     ebx, [rbp+r15*8+0Ch]
0x180013e0b  lea     rdx, [rsp+168h+arg_10]
0x180013e13  mov     rcx, rsi
0x180013e16  mov     dword ptr [rsp+168h+arg_10], r14d
0x180013e1e  mov     [rsp+168h+arg_18], r14
0x180013e26  mov     rax, [rax+90h]
0x180013e2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013e32  mov     r14, [rsp+168h+arg_18]
0x180013e3a  mov     eax, [rbp+r15*8+14h]
0x180013e3f  mov     rdx, [rdi+10h]; Src
0x180013e43  shl     rbx, 5
0x180013e47  mov     esi, [rbx+r14+8]
0x180013e4c  add     rsi, [r12+r13*8]
0x180013e50  cmp     eax, 1
0x180013e53  jnz     loc_18001408C
0x180013e59  mov     r8d, [rbx+r14+14h]
0x180013e5e  mov     rcx, rsi; void *
0x180013e61  shl     r8, 2; Size
0x180013e65  call    memcpy_0
0x180013e6a  mov     rax, [rbx+r14+18h]
0x180013e6f  test    rax, rax
0x180013e72  jz      short loc_180013E7C
0x180013e74  mov     rcx, rsi
0x180013e77  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013e7c  mov     rcx, [rdi]
0x180013e7f  mov     esi, [rsp+168h+arg_8]
0x180013e86  mov     rdx, [rcx+28h]
0x180013e8a  mov     rax, [rcx+30h]
0x180013e8e  sub     rax, rdx
0x180013e91  mov     [rsp+168h+var_130], rdx
0x180013e96  sar     rax, 4
0x180013e9a  cmp     rax, rsi
0x180013e9d  jbe     loc_180013CFD
0x180013ea3  mov     ebx, esi
0x180013ea5  shl     rbx, 4
0x180013ea9  cmp     qword ptr [rdx+rbx], 0
0x180013eae  jz      loc_180013FDB
0x180013eb4  mov     rax, [rcx+18h]
0x180013eb8  mov     r11, 0F0F0F0F0F0F0F0F1h
0x180013ec2  mov     r8, [rax+10h]
0x180013ec6  mov     rcx, [rax+18h]
0x180013eca  sub     rcx, r8
0x180013ecd  sar     rcx, 3
0x180013ed1  imul    rcx, r11
0x180013ed5  cmp     rcx, rsi
0x180013ed8  jbe     loc_180013CFD
0x180013ede  imul    r10, rsi, 88h
0x180013ee5  mov     rax, 8E38E38E38E38E39h
0x180013eef  xor     r12d, r12d
0x180013ef2  mov     [rsp+168h+var_128], r10
0x180013ef7  mov     r14, [r8+r10+30h]
0x180013efc  sub     r14, [r8+r10+28h]
0x180013f01  sar     r14, 3
0x180013f05  imul    r14, rax
0x180013f09  test    r14d, r14d
0x180013f0c  jz      loc_180013FDB
0x180013f12  mov     rax, [rdi]
0x180013f15  mov     rcx, [rax+18h]
0x180013f19  mov     r9, [rcx+10h]
0x180013f1d  mov     rax, [rcx+18h]
0x180013f21  sub     rax, r9
0x180013f24  sar     rax, 3
0x180013f28  imul    rax, r11
0x180013f2c  cmp     rax, rsi
0x180013f2f  jbe     loc_180013CFD
0x180013f35  mov     rcx, [r9+r10+28h]
0x180013f3a  mov     rax, [r9+r10+30h]
0x180013f3f  mov     r9, 8E38E38E38E38E39h
0x180013f49  sub     rax, rcx
0x180013f4c  mov     r8d, r12d
0x180013f4f  sar     rax, 3
0x180013f53  imul    rax, r9
0x180013f57  cmp     rax, r8
0x180013f5a  jbe     loc_180013CFD
0x180013f60  mov     eax, [rbp+r15*8+8]
0x180013f65  lea     r8, [r12+r12*8]
0x180013f69  cmp     [rcx+r8*8], eax
0x180013f6d  jnz     short loc_180013FCF
0x180013f6f  mov     eax, [rcx+r8*8+4]
0x180013f74  add     rax, [rdx+rbx]
0x180013f78  mov     rcx, [rcx+r8*8+40h]
0x180013f7d  mov     [rsp+168h+arg_10], rax
0x180013f85  mov     rax, [rsp+168h+var_138]
0x180013f8a  mov     rax, [rax+r13*8]
0x180013f8e  mov     [rsp+168h+arg_18], rax
0x180013f96  test    rcx, rcx
0x180013f99  jz      loc_1800141D1
0x180013f9f  mov     rax, [rcx]
0x180013fa2  lea     r8, [rsp+168h+arg_10]
0x180013faa  lea     rdx, [rsp+168h+arg_18]
0x180013fb2  mov     rax, [rax+10h]
0x180013fb6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013fbb  mov     rdx, [rsp+168h+var_130]
0x180013fc0  mov     r11, 0F0F0F0F0F0F0F0F1h
0x180013fca  mov     r10, [rsp+168h+var_128]
0x180013fcf  inc     r12d
0x180013fd2  cmp     r12d, r14d
0x180013fd5  jb      loc_180013F12
0x180013fdb  mov     rax, [rdi]
0x180013fde  mov     rdx, [rax+28h]
0x180013fe2  mov     rcx, [rax+30h]
0x180013fe6  sub     rcx, rdx
0x180013fe9  sar     rcx, 4
0x180013fed  cmp     rcx, rsi
0x180013ff0  jbe     loc_180013CFD
0x180013ff6  xor     cl, cl
0x180013ff8  inc     dword ptr [rdx+rbx+8]
0x180013ffc  mov     rax, [rdi+18h]
0x180014000  mov     [rax], cl
0x180014002  mov     rax, [rdi+20h]
0x180014006  mov     ecx, [rsp+168h+arg_8]
0x18001400d  mov     [rax], ecx
0x18001400f  add     rsp, 128h
0x180014016  pop     r15
0x180014018  pop     r14
0x18001401a  pop     r13
0x18001401c  pop     r12
0x18001401e  pop     rdi
0x18001401f  pop     rsi
0x180014020  pop     rbp
0x180014021  pop     rbx
0x180014022  retn
0x180014023  mov     rcx, [rax+10h]
0x180014027  mov     rax, [rcx+38h]
0x18001402b  sub     rax, [rcx+30h]
0x18001402f  sar     rax, 3
0x180014033  cmp     rax, r13
0x180014036  jbe     loc_180013CFD
0x18001403c  lfence
0x18001403f  mov     rax, [rcx+30h]
0x180014043  mov     rbx, [rax+r13*8]
0x180014047  mov     rcx, [rbx]
0x18001404a  mov     rax, [rcx]
0x18001404d  mov     rax, [rax+88h]
0x180014054  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014059  mov     ecx, eax; dwBytes
0x18001405b  mov     r14d, eax
0x18001405e  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180014063  mov     rcx, [r12+r13*8]; lpMem
0x180014067  mov     [r12+r13*8], rax
0x18001406b  test    rcx, rcx
0x18001406e  jnz     loc_18001418C
0x180014074  mov     rdx, [rbx+18h]; Src
0x180014078  mov     r8, r14; Size
0x18001407b  mov     rcx, [r12+r13*8]; void *
0x18001407f  call    memcpy_0
0x180014084  xor     r14d, r14d
0x180014087  jmp     loc_180013DFB
0x18001408c  add     eax, 0FFFFFFFEh; switch 9 cases
0x18001408f  cmp     eax, 8
0x180014092  ja      def_1800140AC; jumptable 00000001800140AC default case, cases 6,8
0x180014098  lea     r8, cs:180000000h
0x18001409f  cdqe
0x1800140a1  mov     ecx, ds:(jpt_1800140AC - 180000000h)[r8+rax*4]
0x1800140a9  add     rcx, r8
0x1800140ac  jmp     rcx; switch jump
0x1800140ae  mov     eax, [rdx]; jumptable 00000001800140AC case 10
0x1800140b0  mov     [rsi], eax
0x1800140b2  mov     eax, [rdx+4]
0x1800140b5  mov     [rsi+4], eax
0x1800140b8  mov     eax, [rdx+8]
0x1800140bb  mov     [rsi+8], eax
0x1800140be  mov     eax, [rdx+0Ch]
0x1800140c1  mov     [rsi+0Ch], eax
0x1800140c4  jmp     loc_180013E6A
0x1800140c9  mov     eax, [rsp+168h+arg_0]
0x1800140d0  cmp     [rbp+r15*8+0Ch], eax
0x1800140d5  jnz     loc_180013D4D
0x1800140db  cmp     dword ptr [rdi+0Ch], 68h ; 'h'
0x1800140df  jnz     loc_180014166
0x1800140e5  cmp     dword ptr [rbp+r15*8+14h], 1
0x1800140eb  jnz     short loc_180014166
0x1800140ed  mov     rax, [rbx+8]
0x1800140f1  mov     edx, [rax+4]
0x1800140f4  mov     rax, [rdi]
0x1800140f7  mov     r8, [rax+40h]
0x1800140fb  mov     rcx, [rax+48h]
0x1800140ff  sub     rcx, r8
0x180014102  sar     rcx, 3
0x180014106  imul    rcx, r12
0x18001410a  cmp     rcx, rdx
0x18001410d  jbe     loc_180013CFD
0x180014113  mov     rax, [rdi+10h]
0x180014117  mov     cl, 1
0x180014119  movups  xmm0, xmmword ptr [rax]
0x18001411c  movsd   xmm1, qword ptr [rax+10h]
0x180014121  lea     rax, [rdx+rdx*2]
0x180014125  movups  xmmword ptr [r8+rax*8], xmm0
0x18001412a  movsd   qword ptr [r8+rax*8+10h], xmm1
0x180014131  jmp     loc_180013FFC
0x180014136  mov     eax, [rdx]; jumptable 00000001800140AC case 4
0x180014138  mov     [rsi+8], eax
0x18001413b  jmp     loc_180013E6A
0x180014140  mov     eax, [rdx]; jumptable 00000001800140AC case 3
0x180014142  mov     [rsi+4], eax
0x180014145  jmp     loc_180013E6A
0x18001414a  xor     ebx, ebx
0x18001414c  jmp     loc_180013DCB
0x180014151  movss   xmm0, dword ptr [rdx]; jumptable 00000001800140AC case 7
0x180014155  mulss   xmm0, cs:__real@42652ee0
0x18001415d  movss   dword ptr [rsi], xmm0
0x180014161  jmp     loc_180013E6A
0x180014166  lea     rcx, [rsp+168h+pExceptionObject]; this
0x18001416b  call    ??0ResultException@wil@@QEAA@J@Z; wil::ResultException::ResultException(long)
0x180014170  lea     rdx, _TI2?AVResultException@wil@@; pThrowInfo
0x180014177  lea     rcx, [rsp+168h+pExceptionObject]; pExceptionObject
0x18001417c  call    _CxxThrowException_0
0x180014182  call    ??$?RV?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@std@@@std@@$0A@@?$default_delete@$$BY0A@V?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@std@@@std@@@std@@QEBAXPEAV?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@std@@@1@@Z; std::default_delete<std::unique_ptr<uchar [0]> [0]>::operator()<std::unique_ptr<uchar [0]>,0>(std::unique_ptr<uchar [0]> *)
0x180014187  jmp     loc_180013DDC
0x18001418c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180014191  jmp     loc_180014074
0x180014196  mov     eax, [rdx]; jumptable 00000001800140AC case 2
  ... truncated ...
```
