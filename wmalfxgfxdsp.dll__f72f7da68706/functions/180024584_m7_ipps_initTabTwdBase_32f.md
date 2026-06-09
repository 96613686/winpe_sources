# m7_ipps_initTabTwdBase_32f

- ea: `0x180024584`
- end: `0x1800246c8`
- name: `m7_ipps_initTabTwdBase_32f`
- size: `324`
- prototype: ``
- caller_count: `6`
- callee_count: `3`
- tags: ``

## callers

- `0x1800191f8`
- `0x180019350`
- `0x18001a3f8`
- `0x18001a550`
- `0x18001b698`
- `0x18001b7f0`

## callees

- `0x180015e00`
- `0x180015e6c`
- `0x180024584`

## pseudocode

```c
char *__fastcall m7_ipps_initTabTwdBase_32f(int a1, float *a2)
{
  char v2; // r9
  __int64 v4; // rbx
  int v5; // r8d
  __int64 v6; // rdi
  char *v7; // r15
  __int64 *v8; // rcx
  float v9; // eax
  int v10; // r14d
  double v11; // xmm6_8
  float *v12; // rbp
  double v13; // xmm0_8
  float v14; // xmm1_4
  int v15; // r14d
  __int64 v16; // rbp
  __int64 v17; // rbx
  int v18; // edi
  double v19; // xmm0_8
  float v20; // xmm1_4

  v2 = a1;
  v4 = 0;
  v5 = 1 << a1;
  v6 = (1 << a1) / 4;
  v7 = (char *)&a2[(int)v6 + 1] + (-(4 * ((_DWORD)v6 + 1) + (_DWORD)a2) & 0x1F);
  if ( a1 > 10 )
  {
    v10 = v5 / 8;
    v11 = 6.283185307179586 / (double)v5;
    if ( v5 / 8 >= 0 )
    {
      v12 = a2;
      do
      {
        v13 = o_sin_0((double)(int)v4 * v11);
        LODWORD(v4) = v4 + 1;
        v14 = v13;
        *v12++ = v14;
      }
      while ( (int)v4 <= v10 );
    }
    v15 = v10 + 1;
    v16 = v6;
    v17 = v15;
    if ( v15 <= v6 )
    {
      v18 = v6 - v15;
      do
      {
        v19 = cos((double)v18-- * v11);
        v20 = v19;
        a2[v17++] = v20;
      }
      while ( v17 <= v16 );
    }
  }
  else
  {
    if ( (int)v6 > 0 )
    {
      v8 = fft_fix_twiddle_table_32f;
      do
      {
        v9 = *(float *)v8;
        v8 = (__int64 *)((char *)v8 + 4 * (1 << (10 - v2)));
        a2[v4++] = v9;
      }
      while ( v4 < v6 );
    }
    a2[v6] = 1.0;
  }
  return v7;
}

```

## disassembly

```asm
0x180024584  mov     rax, rsp
0x180024587  mov     [rax+8], rbx
0x18002458b  mov     [rax+10h], rbp
0x18002458f  mov     [rax+18h], rsi
0x180024593  push    rdi
0x180024594  push    r14
0x180024596  push    r15
0x180024598  sub     rsp, 30h
0x18002459c  movaps  xmmword ptr [rax-28h], xmm6
0x1800245a0  mov     r9d, ecx
0x1800245a3  mov     r15, rdx
0x1800245a6  mov     r8d, 1
0x1800245ac  mov     rsi, r15
0x1800245af  xor     ebx, ebx
0x1800245b1  shl     r8d, cl
0x1800245b4  mov     eax, r8d
0x1800245b7  cdq
0x1800245b8  and     edx, 3
0x1800245bb  add     eax, edx
0x1800245bd  sar     eax, 2
0x1800245c0  movsxd  rdi, eax
0x1800245c3  lea     eax, [rdi+1]
0x1800245c6  cdqe
0x1800245c8  shl     rax, 2
0x1800245cc  lea     rcx, [rax+r15]
0x1800245d0  neg     rcx
0x1800245d3  and     ecx, 1Fh
0x1800245d6  add     rcx, rax
0x1800245d9  add     r15, rcx
0x1800245dc  mov     ecx, 0Ah
0x1800245e1  cmp     r9d, ecx
0x1800245e4  jg      short loc_18002461C
0x1800245e6  test    edi, edi
0x1800245e8  jle     short loc_180024610
0x1800245ea  sub     ecx, r9d
0x1800245ed  lea     eax, [rbx+1]
0x1800245f0  shl     eax, cl
0x1800245f2  lea     rcx, fft_fix_twiddle_table_32f
0x1800245f9  movsxd  r8, eax
0x1800245fc  shl     r8, 2
0x180024600  mov     eax, [rcx]
0x180024602  add     rcx, r8
0x180024605  mov     [rsi+rbx*4], eax
0x180024608  inc     rbx
0x18002460b  cmp     rbx, rdi
0x18002460e  jl      short loc_180024600
0x180024610  mov     dword ptr [rsi+rdi*4], 3F800000h
0x180024617  jmp     loc_1800246A7
0x18002461c  movsd   xmm6, cs:__real@401921fb54442d18
0x180024624  movd    xmm0, r8d
0x180024629  mov     eax, r8d
0x18002462c  cdq
0x18002462d  and     edx, 7
0x180024630  add     eax, edx
0x180024632  sar     eax, 3
0x180024635  mov     r14d, eax
0x180024638  cvtdq2pd xmm0, xmm0
0x18002463c  divsd   xmm6, xmm0
0x180024640  test    eax, eax
0x180024642  js      short loc_18002466F
0x180024644  mov     rbp, rsi
0x180024647  movd    xmm0, ebx
0x18002464b  cvtdq2pd xmm0, xmm0
0x18002464f  mulsd   xmm0, xmm6; X
0x180024653  call    _o_sin_0
0x180024658  xorps   xmm1, xmm1
0x18002465b  inc     ebx
0x18002465d  cvtsd2ss xmm1, xmm0
0x180024661  movss   dword ptr [rbp+0], xmm1
0x180024666  lea     rbp, [rbp+4]
0x18002466a  cmp     ebx, r14d
0x18002466d  jle     short loc_180024647
0x18002466f  inc     r14d
0x180024672  mov     rbp, rdi
0x180024675  movsxd  rbx, r14d
0x180024678  cmp     rbx, rdi
0x18002467b  jg      short loc_1800246A7
0x18002467d  sub     edi, r14d
0x180024680  movd    xmm0, edi
0x180024684  cvtdq2pd xmm0, xmm0
0x180024688  mulsd   xmm0, xmm6; X
0x18002468c  call    cos
0x180024691  xorps   xmm1, xmm1
0x180024694  dec     edi
0x180024696  cvtsd2ss xmm1, xmm0
0x18002469a  movss   dword ptr [rsi+rbx*4], xmm1
0x18002469f  inc     rbx
0x1800246a2  cmp     rbx, rbp
0x1800246a5  jle     short loc_180024680
0x1800246a7  mov     rbx, [rsp+48h+arg_0]
0x1800246ac  mov     rbp, [rsp+48h+arg_8]
0x1800246b1  mov     rsi, [rsp+48h+arg_10]
0x1800246b6  movaps  xmm6, [rsp+48h+var_28]
0x1800246bb  mov     rax, r15
0x1800246be  add     rsp, 30h
0x1800246c2  pop     r15
0x1800246c4  pop     r14
0x1800246c6  pop     rdi
0x1800246c7  retn
```
