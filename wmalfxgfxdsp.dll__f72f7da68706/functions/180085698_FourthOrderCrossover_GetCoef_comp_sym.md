# FourthOrderCrossover_GetCoef_comp_sym

- ea: `0x180085698`
- end: `0x180085838`
- name: `FourthOrderCrossover_GetCoef_comp_sym`
- size: `416`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `reparse_path, broker_com_uri`

## callers

- `0x180013990`

## callees

- `0x180085840`

## pseudocode

```c
_DWORD *__fastcall FourthOrderCrossover_GetCoef_comp_sym(
        double a1,
        int a2,
        __int64 a3,
        __int64 a4,
        _DWORD *a5,
        _DWORD *a6)
{
  double v6; // xmm5_8
  float v7; // xmm1_4
  float v8; // xmm0_4
  float v9; // xmm0_4
  float v10; // xmm0_4
  float v11; // xmm0_4
  float v12; // xmm0_4
  float v13; // xmm0_4
  double v14; // xmm1_8
  double v15; // xmm0_8
  double v16; // xmm5_8
  __int64 v17; // r8
  __int64 v18; // r9
  __int64 v19; // r9
  _DWORD *result; // rax

  *(_DWORD *)(a4 + 44) = 0;
  *(_DWORD *)(a4 + 32) = 0;
  v6 = 0.3183098861837907 / a1 * (double)a2;
  v7 = v6 * v6;
  v8 = v6 * -2.0 * v6;
  *(float *)a4 = v7;
  *(float *)(a4 + 4) = v8;
  *(float *)(a4 + 8) = v7;
  v9 = (v6 + 3.244827586206896) * v6 + 1.0;
  *(float *)(a4 + 12) = v9;
  v10 = 1.0 - v6 * v6 + 1.0 - v6 * v6;
  *(float *)(a4 + 16) = v10;
  v11 = v6 * v6 - v6 * 3.244827586206896 + 1.0;
  *(float *)(a4 + 20) = v11;
  v12 = v6 + 4.244827586206896;
  *(float *)(a4 + 24) = v12;
  v13 = 4.244827586206896 - v6;
  *(float *)(a4 + 28) = v13;
  v14 = 1.0 - v6;
  v15 = v6;
  v16 = v6 * 4.244827586206896;
  *(float *)&v15 = v15 + 1.0;
  *(_DWORD *)(a4 + 36) = LODWORD(v15);
  *(float *)&v15 = v14;
  *(_DWORD *)(a4 + 40) = LODWORD(v15);
  *(_DWORD *)a3 = 1065353216;
  *(_DWORD *)(a3 + 4) = 0x40000000;
  *(_DWORD *)(a3 + 8) = 1065353216;
  *(_DWORD *)(a3 + 12) = *(_DWORD *)(a4 + 12);
  *(_DWORD *)(a3 + 16) = *(_DWORD *)(a4 + 16);
  *(_DWORD *)(a3 + 20) = *(_DWORD *)(a4 + 20);
  *(_DWORD *)(a3 + 32) = 0;
  *(float *)&v15 = v16 + 1.0;
  *(_DWORD *)(a3 + 24) = LODWORD(v15);
  *(float *)(a3 + 28) = 1.0 - v16;
  *(_DWORD *)(a3 + 36) = *(_DWORD *)(a4 + 36);
  *(_DWORD *)(a3 + 40) = *(_DWORD *)(a4 + 40);
  *(_DWORD *)(a3 + 44) = *(_DWORD *)(a4 + 44);
  NormalizeY0(a3);
  NormalizeY0(v17 + 24);
  NormalizeY0(v18);
  NormalizeY0(v19 + 24);
  *a6 = 1067030938;
  result = a5;
  *a5 = 1067030938;
  return result;
}

```

## disassembly

```asm
0x180085698  sub     rsp, 28h
0x18008569c  movsd   xmm5, cs:__real@3fd45f306dc9c883
0x1800856a4  xor     r10d, r10d
0x1800856a7  movsd   xmm4, cs:__real@3ff0000000000000
0x1800856af  mov     rcx, r8
0x1800856b2  movsd   xmm2, cs:__real@4010fab4152fab41
0x1800856ba  divsd   xmm5, xmm0
0x1800856be  mov     [r9+2Ch], r10d
0x1800856c2  mov     [r9+20h], r10d
0x1800856c6  mov     eax, edx
0x1800856c8  xorps   xmm0, xmm0
0x1800856cb  cvtsi2sd xmm0, rax
0x1800856d0  mov     eax, 3F800000h
0x1800856d5  mulsd   xmm5, xmm0
0x1800856d9  movaps  xmm0, xmm5
0x1800856dc  movaps  xmm3, xmm5
0x1800856df  mulsd   xmm0, cs:__real@c000000000000000
0x1800856e7  mulsd   xmm3, xmm5
0x1800856eb  mulsd   xmm0, xmm5
0x1800856ef  cvtpd2ps xmm1, xmm3
0x1800856f3  cvtpd2ps xmm0, xmm0
0x1800856f7  movss   dword ptr [r9], xmm1
0x1800856fc  movss   dword ptr [r9+4], xmm0
0x180085702  movaps  xmm0, xmm5
0x180085705  addsd   xmm0, cs:__real@4009f5682a5f5682
0x18008570d  movss   dword ptr [r9+8], xmm1
0x180085713  movaps  xmm1, xmm4
0x180085716  subsd   xmm1, xmm3
0x18008571a  mulsd   xmm0, xmm5
0x18008571e  addsd   xmm1, xmm1
0x180085722  addsd   xmm0, xmm4
0x180085726  cvtpd2ps xmm0, xmm0
0x18008572a  movss   dword ptr [r9+0Ch], xmm0
0x180085730  cvtpd2ps xmm0, xmm1
0x180085734  movaps  xmm1, xmm5
0x180085737  mulsd   xmm1, cs:__real@4009f5682a5f5682
0x18008573f  movss   dword ptr [r9+10h], xmm0
0x180085745  subsd   xmm3, xmm1
0x180085749  movaps  xmm1, xmm5
0x18008574c  addsd   xmm1, xmm2
0x180085750  addsd   xmm3, xmm4
0x180085754  cvtpd2ps xmm0, xmm3
0x180085758  movss   dword ptr [r9+14h], xmm0
0x18008575e  cvtpd2ps xmm0, xmm1
0x180085762  movaps  xmm1, xmm2
0x180085765  movss   dword ptr [r9+18h], xmm0
0x18008576b  subsd   xmm1, xmm5
0x18008576f  cvtpd2ps xmm0, xmm1
0x180085773  movaps  xmm1, xmm4
0x180085776  movss   dword ptr [r9+1Ch], xmm0
0x18008577c  subsd   xmm1, xmm5
0x180085780  movaps  xmm0, xmm5
0x180085783  mulsd   xmm5, xmm2
0x180085787  addsd   xmm0, xmm4
0x18008578b  cvtpd2ps xmm0, xmm0
0x18008578f  movss   dword ptr [r9+24h], xmm0
0x180085795  cvtpd2ps xmm0, xmm1
0x180085799  movss   dword ptr [r9+28h], xmm0
0x18008579f  movaps  xmm0, xmm5
0x1800857a2  mov     [r8], eax
0x1800857a5  addsd   xmm0, xmm4
0x1800857a9  mov     dword ptr [r8+4], 40000000h
0x1800857b1  subsd   xmm4, xmm5
0x1800857b5  mov     [r8+8], eax
0x1800857b9  mov     eax, [r9+0Ch]
0x1800857bd  mov     [r8+0Ch], eax
0x1800857c1  mov     eax, [r9+10h]
0x1800857c5  mov     [r8+10h], eax
0x1800857c9  mov     eax, [r9+14h]
0x1800857cd  mov     [r8+14h], eax
0x1800857d1  mov     [r8+20h], r10d
0x1800857d5  cvtpd2ps xmm0, xmm0
0x1800857d9  movss   dword ptr [r8+18h], xmm0
0x1800857df  cvtpd2ps xmm0, xmm4
0x1800857e3  movss   dword ptr [r8+1Ch], xmm0
0x1800857e9  mov     eax, [r9+24h]
0x1800857ed  mov     [r8+24h], eax
0x1800857f1  mov     eax, [r9+28h]
0x1800857f5  mov     [r8+28h], eax
0x1800857f9  mov     eax, [r9+2Ch]
0x1800857fd  mov     [r8+2Ch], eax
0x180085801  call    NormalizeY0
0x180085806  lea     rcx, [r8+18h]
0x18008580a  call    NormalizeY0
0x18008580f  mov     rcx, r9
0x180085812  call    NormalizeY0
0x180085817  lea     rcx, [r9+18h]
0x18008581b  call    NormalizeY0
0x180085820  mov     rax, [rsp+28h+arg_28]
0x180085825  mov     ecx, 3F99999Ah
0x18008582a  mov     [rax], ecx
0x18008582c  mov     rax, [rsp+28h+arg_20]
0x180085831  mov     [rax], ecx
0x180085833  add     rsp, 28h
0x180085837  retn
```
