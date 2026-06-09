# cFFTfwd_norm_4

- ea: `0x1800174c0`
- end: `0x180017598`
- name: `cFFTfwd_norm_4`
- size: `216`
- prototype: ``
- caller_count: `6`
- callee_count: `0`
- tags: ``

## callers

- `0x180018990`
- `0x180019b10`
- `0x18001adb0`
- `0x18001d170`
- `0x18001dfd0`
- `0x18001ed60`

## pseudocode

```c
void __fastcall cFFTfwd_norm_4(float *a1, float *a2, float a3)
{
  float v3; // xmm1_4
  float v4; // xmm6_4
  float v5; // xmm3_4
  float v6; // xmm1_4
  float v7; // xmm7_4
  float v8; // xmm3_4
  float v9; // xmm4_4
  float v10; // xmm1_4
  float v11; // xmm2_4

  v3 = a1[2];
  v4 = (float)(v3 - a1[6]) * a3;
  v5 = (float)(*a1 + a1[4]) * a3;
  v6 = (float)(v3 + a1[6]) * a3;
  v7 = (float)(*a1 - a1[4]) * a3;
  *a2 = v6 + v5;
  a2[4] = v5 - v6;
  v8 = (float)(a1[1] + a1[5]) * a3;
  v9 = (float)(a1[1] - a1[5]) * a3;
  v10 = (float)(a1[3] + a1[7]) * a3;
  v11 = (float)(a1[3] - a1[7]) * a3;
  a2[1] = v10 + v8;
  a2[5] = v8 - v10;
  a2[6] = v7 - v11;
  a2[2] = v11 + v7;
  a2[3] = v9 - v4;
  a2[7] = v9 + v4;
}

```

## disassembly

```asm
0x1800174c0  sub     rsp, 28h
0x1800174c4  movaps  xmm5, xmm2
0x1800174c7  movaps  [rsp+28h+var_18], xmm6
0x1800174cc  movss   xmm6, dword ptr [rcx+8]
0x1800174d1  movaps  xmm1, xmm6
0x1800174d4  movaps  [rsp+28h+var_28], xmm7
0x1800174d8  movss   xmm7, dword ptr [rcx]
0x1800174dc  subss   xmm6, dword ptr [rcx+18h]
0x1800174e1  movaps  xmm3, xmm7
0x1800174e4  addss   xmm3, dword ptr [rcx+10h]
0x1800174e9  addss   xmm1, dword ptr [rcx+18h]
0x1800174ee  subss   xmm7, dword ptr [rcx+10h]
0x1800174f3  mulss   xmm6, xmm5
0x1800174f7  mulss   xmm3, xmm5
0x1800174fb  mulss   xmm1, xmm5
0x1800174ff  mulss   xmm7, xmm5
0x180017503  movaps  xmm0, xmm1
0x180017506  addss   xmm0, xmm3
0x18001750a  subss   xmm3, xmm1
0x18001750e  movss   dword ptr [rdx], xmm0
0x180017512  movss   dword ptr [rdx+10h], xmm3
0x180017517  movss   xmm4, dword ptr [rcx+4]
0x18001751c  movaps  xmm3, xmm4
0x18001751f  subss   xmm4, dword ptr [rcx+14h]
0x180017524  movss   xmm2, dword ptr [rcx+0Ch]
0x180017529  addss   xmm3, dword ptr [rcx+14h]
0x18001752e  movaps  xmm1, xmm2
0x180017531  mulss   xmm3, xmm5
0x180017535  mulss   xmm4, xmm5
0x180017539  addss   xmm1, dword ptr [rcx+1Ch]
0x18001753e  subss   xmm2, dword ptr [rcx+1Ch]
0x180017543  mulss   xmm1, xmm5
0x180017547  mulss   xmm2, xmm5
0x18001754b  movaps  xmm0, xmm1
0x18001754e  addss   xmm0, xmm3
0x180017552  subss   xmm3, xmm1
0x180017556  movss   dword ptr [rdx+4], xmm0
0x18001755b  movss   dword ptr [rdx+14h], xmm3
0x180017560  movaps  xmm0, xmm7
0x180017563  subss   xmm0, xmm2
0x180017567  addss   xmm2, xmm7
0x18001756b  movaps  xmm7, [rsp+28h+var_28]
0x18001756f  movss   dword ptr [rdx+18h], xmm0
0x180017574  movss   dword ptr [rdx+8], xmm2
0x180017579  movaps  xmm0, xmm4
0x18001757c  subss   xmm0, xmm6
0x180017580  addss   xmm4, xmm6
0x180017584  movaps  xmm6, [rsp+28h+var_18]
0x180017589  movss   dword ptr [rdx+0Ch], xmm0
0x18001758e  movss   dword ptr [rdx+1Ch], xmm4
0x180017593  add     rsp, 28h
0x180017597  retn
```
