# px_ipps_createTabDftBase_32f

- ea: `0x180050900`
- end: `0x180050b5a`
- name: `px_ipps_createTabDftBase_32f`
- size: `602`
- prototype: ``
- caller_count: `9`
- callee_count: `4`
- tags: ``

## callers

- `0x18001c9d0`
- `0x18001cbe0`
- `0x18001d830`
- `0x18001da40`
- `0x18001e5c0`
- `0x18001e7d0`
- `0x180059558`
- `0x18005bc88`
- `0x18005e7ec`

## callees

- `0x180015e00`
- `0x180015e6c`
- `0x18001f910`
- `0x180050900`

## pseudocode

```c
__int64 __fastcall px_ipps_createTabDftBase_32f(int a1)
{
  __int64 v1; // rdi
  __int64 result; // rax
  int v3; // esi
  __int64 v4; // rbx
  double v5; // xmm7_8
  __int64 v6; // rbp
  float *v7; // r14
  double v8; // xmm6_8
  float v9; // xmm1_4
  float v10; // xmm0_4
  __int64 v11; // rbp
  float *v12; // r14
  double v13; // xmm6_8
  float v14; // xmm1_4
  float v15; // xmm0_4
  int v16; // ebp
  float *v17; // r14
  double v18; // xmm6_8
  float v19; // xmm1_4
  float v20; // xmm0_4
  __int64 v21; // rcx
  int *v22; // rdx
  int v23; // xmm1_4
  __int64 v24; // rcx
  int *v25; // rdx
  int v26; // xmm0_4
  __int64 v27; // rcx
  int *v28; // rdx
  int v29; // eax

  v1 = a1;
  result = px_ippsMalloc_8u((unsigned int)(8 * a1));
  v3 = 0;
  v4 = result;
  if ( result )
  {
    v5 = 6.283185307179586 / (double)(int)v1;
    if ( (v1 & 1) != 0 )
    {
      LODWORD(v6) = (int)v1 / 2;
      if ( (int)v1 / 2 >= 0 )
      {
        v7 = (float *)result;
        do
        {
          v8 = (double)v3 * v5;
          v9 = cos(v8);
          *v7 = v9;
          ++v3;
          v7 += 2;
          v10 = COERCE_DOUBLE(COERCE_UNSIGNED_INT64(o_sin_0(v8)) ^ _xmm);
          *(v7 - 1) = v10;
        }
        while ( v3 <= (int)v6 );
      }
    }
    else
    {
      if ( (v1 & 2) != 0 )
      {
        LODWORD(v11) = (int)v1 / 4;
        if ( (int)v1 / 4 >= 0 )
        {
          v12 = (float *)result;
          do
          {
            v13 = (double)v3 * v5;
            v14 = cos(v13);
            *v12 = v14;
            ++v3;
            v12 += 2;
            v15 = COERCE_DOUBLE(COERCE_UNSIGNED_INT64(o_sin_0(v13)) ^ _xmm);
            *(v12 - 1) = v15;
          }
          while ( v3 <= (int)v11 );
        }
      }
      else
      {
        v16 = (int)v1 / 8;
        if ( (int)v1 / 8 >= 0 )
        {
          v17 = (float *)result;
          do
          {
            v18 = (double)v3 * v5;
            v19 = cos(v18);
            *v17 = v19;
            ++v3;
            v17 += 2;
            v20 = COERCE_DOUBLE(COERCE_UNSIGNED_INT64(o_sin_0(v18)) ^ _xmm);
            *(v17 - 1) = v20;
          }
          while ( v3 <= v16 );
        }
        v21 = v16 + 1;
        v11 = (int)v1 / 4;
        if ( v21 <= v11 )
        {
          v22 = (int *)(v4 + 8 * (v11 - v21));
          do
          {
            *(_DWORD *)(v4 + 8 * v21) = v22[1] ^ _xmm;
            v23 = *v22;
            ++v21;
            v22 -= 2;
            *(_DWORD *)(v4 + 8 * v21 - 4) = v23 ^ _xmm;
          }
          while ( v21 <= v11 );
        }
      }
      v24 = (int)v11 + 1;
      v6 = (int)v1 / 2;
      if ( v24 <= v6 )
      {
        v25 = (int *)(v4 + 8 * (v6 - v24));
        do
        {
          v26 = *v25;
          v25 -= 2;
          *(_DWORD *)(v4 + 8 * v24++) = v26 ^ _xmm;
          *(_DWORD *)(v4 + 8 * v24 - 4) = v25[3];
        }
        while ( v24 <= v6 );
      }
    }
    v27 = (int)v6 + 1;
    if ( v27 < v1 )
    {
      v28 = (int *)(v4 + 8 * (v1 - v27));
      do
      {
        v29 = *v28;
        v28 -= 2;
        *(_DWORD *)(v4 + 8 * v27++) = v29;
        *(_DWORD *)(v4 + 8 * v27 - 4) = v28[3] ^ _xmm;
      }
      while ( v27 < v1 );
    }
    return v4;
  }
  return result;
}

```

## disassembly

```asm
0x180050900  mov     rax, rsp
0x180050903  mov     [rax+8], rbx
0x180050907  mov     [rax+10h], rbp
0x18005090b  mov     [rax+18h], rsi
0x18005090f  mov     [rax+20h], rdi
0x180050913  push    r14
0x180050915  sub     rsp, 40h
0x180050919  movsxd  rdi, ecx
0x18005091c  movaps  xmmword ptr [rax-18h], xmm6
0x180050920  movaps  xmmword ptr [rax-28h], xmm7
0x180050924  mov     ecx, edi
0x180050926  shl     ecx, 3
0x180050929  call    px_ippsMalloc_8u
0x18005092e  xor     esi, esi
0x180050930  mov     rbx, rax
0x180050933  test    rax, rax
0x180050936  jz      loc_180050B35
0x18005093c  movsd   xmm7, cs:__real@401921fb54442d18
0x180050944  movd    xmm0, edi
0x180050948  mov     eax, edi
0x18005094a  cdq
0x18005094b  cvtdq2pd xmm0, xmm0
0x18005094f  divsd   xmm7, xmm0
0x180050953  test    dil, 1
0x180050957  jz      short loc_1800509B0
0x180050959  sub     eax, edx
0x18005095b  sar     eax, 1
0x18005095d  mov     ebp, eax
0x18005095f  js      loc_180050AFA
0x180050965  mov     r14, rbx
0x180050968  movd    xmm6, esi
0x18005096c  cvtdq2pd xmm6, xmm6
0x180050970  mulsd   xmm6, xmm7
0x180050974  movaps  xmm0, xmm6; X
0x180050977  call    cos
0x18005097c  xorps   xmm1, xmm1
0x18005097f  cvtsd2ss xmm1, xmm0
0x180050983  movaps  xmm0, xmm6; X
0x180050986  movss   dword ptr [r14], xmm1
0x18005098b  call    _o_sin_0
0x180050990  inc     esi
0x180050992  lea     r14, [r14+8]
0x180050996  xorps   xmm0, cs:__xmm@80000000000000008000000000000000
0x18005099d  cvtsd2ss xmm0, xmm0
0x1800509a1  movss   dword ptr [r14-4], xmm0
0x1800509a7  cmp     esi, ebp
0x1800509a9  jle     short loc_180050968
0x1800509ab  jmp     loc_180050AFA
0x1800509b0  test    dil, 2
0x1800509b4  jz      short loc_180050A13
0x1800509b6  and     edx, 3
0x1800509b9  add     eax, edx
0x1800509bb  sar     eax, 2
0x1800509be  mov     ebp, eax
0x1800509c0  test    eax, eax
0x1800509c2  js      loc_180050AB8
0x1800509c8  mov     r14, rbx
0x1800509cb  movd    xmm6, esi
0x1800509cf  cvtdq2pd xmm6, xmm6
0x1800509d3  mulsd   xmm6, xmm7
0x1800509d7  movaps  xmm0, xmm6; X
0x1800509da  call    cos
0x1800509df  xorps   xmm1, xmm1
0x1800509e2  cvtsd2ss xmm1, xmm0
0x1800509e6  movaps  xmm0, xmm6; X
0x1800509e9  movss   dword ptr [r14], xmm1
0x1800509ee  call    _o_sin_0
0x1800509f3  inc     esi
0x1800509f5  lea     r14, [r14+8]
0x1800509f9  xorps   xmm0, cs:__xmm@80000000000000008000000000000000
0x180050a00  cvtsd2ss xmm0, xmm0
0x180050a04  movss   dword ptr [r14-4], xmm0
0x180050a0a  cmp     esi, ebp
0x180050a0c  jle     short loc_1800509CB
0x180050a0e  jmp     loc_180050AB8
0x180050a13  and     edx, 7
0x180050a16  add     eax, edx
0x180050a18  sar     eax, 3
0x180050a1b  mov     ebp, eax
0x180050a1d  test    eax, eax
0x180050a1f  js      short loc_180050A67
0x180050a21  mov     r14, rbx
0x180050a24  movd    xmm6, esi
0x180050a28  cvtdq2pd xmm6, xmm6
0x180050a2c  mulsd   xmm6, xmm7
0x180050a30  movaps  xmm0, xmm6; X
0x180050a33  call    cos
0x180050a38  xorps   xmm1, xmm1
0x180050a3b  cvtsd2ss xmm1, xmm0
0x180050a3f  movaps  xmm0, xmm6; X
0x180050a42  movss   dword ptr [r14], xmm1
0x180050a47  call    _o_sin_0
0x180050a4c  inc     esi
0x180050a4e  lea     r14, [r14+8]
0x180050a52  xorps   xmm0, cs:__xmm@80000000000000008000000000000000
0x180050a59  cvtsd2ss xmm0, xmm0
0x180050a5d  movss   dword ptr [r14-4], xmm0
0x180050a63  cmp     esi, ebp
0x180050a65  jle     short loc_180050A24
0x180050a67  lea     eax, [rbp+1]
0x180050a6a  movsxd  rcx, eax
0x180050a6d  mov     eax, edi
0x180050a6f  cdq
0x180050a70  and     edx, 3
0x180050a73  add     eax, edx
0x180050a75  sar     eax, 2
0x180050a78  movsxd  rbp, eax
0x180050a7b  cmp     rcx, rbp
0x180050a7e  jg      short loc_180050AB8
0x180050a80  mov     rax, rbp
0x180050a83  sub     rax, rcx
0x180050a86  lea     rdx, [rbx+rax*8]
0x180050a8a  movss   xmm0, dword ptr [rdx+4]
0x180050a8f  xorps   xmm0, cs:__xmm@80000000800000008000000080000000
0x180050a96  movss   dword ptr [rbx+rcx*8], xmm0
0x180050a9b  movss   xmm1, dword ptr [rdx]
0x180050a9f  inc     rcx
0x180050aa2  lea     rdx, [rdx-8]
0x180050aa6  xorps   xmm1, cs:__xmm@80000000800000008000000080000000
0x180050aad  movss   dword ptr [rbx+rcx*8-4], xmm1
0x180050ab3  cmp     rcx, rbp
0x180050ab6  jle     short loc_180050A8A
0x180050ab8  lea     eax, [rbp+1]
0x180050abb  movsxd  rcx, eax
0x180050abe  mov     eax, edi
0x180050ac0  cdq
0x180050ac1  sub     eax, edx
0x180050ac3  sar     eax, 1
0x180050ac5  movsxd  rbp, eax
0x180050ac8  cmp     rcx, rbp
0x180050acb  jg      short loc_180050AFA
0x180050acd  mov     rax, rbp
0x180050ad0  sub     rax, rcx
0x180050ad3  lea     rdx, [rbx+rax*8]
0x180050ad7  movss   xmm0, dword ptr [rdx]
0x180050adb  lea     rdx, [rdx-8]
0x180050adf  xorps   xmm0, cs:__xmm@80000000800000008000000080000000
0x180050ae6  movss   dword ptr [rbx+rcx*8], xmm0
0x180050aeb  mov     eax, [rdx+0Ch]
0x180050aee  inc     rcx
0x180050af1  mov     [rbx+rcx*8-4], eax
0x180050af5  cmp     rcx, rbp
0x180050af8  jle     short loc_180050AD7
0x180050afa  lea     eax, [rbp+1]
0x180050afd  movsxd  rcx, eax
0x180050b00  cmp     rcx, rdi
0x180050b03  jge     short loc_180050B32
0x180050b05  mov     rax, rdi
0x180050b08  sub     rax, rcx
0x180050b0b  lea     rdx, [rbx+rax*8]
0x180050b0f  mov     eax, [rdx]
0x180050b11  lea     rdx, [rdx-8]
0x180050b15  mov     [rbx+rcx*8], eax
0x180050b18  inc     rcx
0x180050b1b  movss   xmm0, dword ptr [rdx+0Ch]
0x180050b20  xorps   xmm0, cs:__xmm@80000000800000008000000080000000
0x180050b27  movss   dword ptr [rbx+rcx*8-4], xmm0
0x180050b2d  cmp     rcx, rdi
0x180050b30  jl      short loc_180050B0F
0x180050b32  mov     rax, rbx
0x180050b35  mov     rbx, [rsp+48h+arg_0]
0x180050b3a  mov     rbp, [rsp+48h+arg_8]
0x180050b3f  mov     rsi, [rsp+48h+arg_10]
0x180050b44  movaps  xmm6, [rsp+48h+var_18]
0x180050b49  movaps  xmm7, [rsp+48h+var_28]
0x180050b4e  mov     rdi, [rsp+48h+arg_18]
0x180050b53  add     rsp, 40h
0x180050b57  pop     r14
0x180050b59  retn
```
