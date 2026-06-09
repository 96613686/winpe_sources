# rFFTfwd_norm_4

- ea: `0x180018430`
- end: `0x180018486`
- name: `rFFTfwd_norm_4`
- size: `86`
- prototype: ``
- caller_count: `9`
- callee_count: `0`
- tags: ``

## callers

- `0x180018af0`
- `0x180018ccc`
- `0x180019cb0`
- `0x180019eb0`
- `0x18001af50`
- `0x18001b150`
- `0x18001ce80`
- `0x18001dce0`
- `0x18001ea70`

## pseudocode

```c
void __fastcall rFFTfwd_norm_4(float *a1, float *a2, float a3)
{
  float v4; // xmm2_4
  float v5; // xmm3_4
  float v6; // xmm1_4
  float v7; // xmm2_4

  v4 = a1[3];
  v5 = (float)(*a1 + a1[2]) * a3;
  v6 = (float)(a1[1] + v4) * a3;
  v7 = (float)(v4 - a1[1]) * a3;
  a2[2] = (float)(*a1 - a1[2]) * a3;
  *a2 = v6 + v5;
  a2[1] = v5 - v6;
  a2[3] = v7;
}

```

## disassembly

```asm
0x180018430  movss   xmm4, dword ptr [rcx]
0x180018434  movss   xmm1, dword ptr [rcx+4]
0x180018439  movaps  xmm0, xmm2
0x18001843c  movss   xmm2, dword ptr [rcx+0Ch]
0x180018441  movaps  xmm3, xmm4
0x180018444  addss   xmm3, dword ptr [rcx+8]
0x180018449  subss   xmm4, dword ptr [rcx+8]
0x18001844e  addss   xmm1, xmm2
0x180018452  subss   xmm2, dword ptr [rcx+4]
0x180018457  mulss   xmm3, xmm0
0x18001845b  mulss   xmm1, xmm0
0x18001845f  mulss   xmm4, xmm0
0x180018463  mulss   xmm2, xmm0
0x180018467  movaps  xmm0, xmm3
0x18001846a  subss   xmm0, xmm1
0x18001846e  addss   xmm1, xmm3
0x180018472  movss   dword ptr [rdx+8], xmm4
0x180018477  movss   dword ptr [rdx], xmm1
0x18001847b  movss   dword ptr [rdx+4], xmm0
0x180018480  movss   dword ptr [rdx+0Ch], xmm2
0x180018485  retn
```
