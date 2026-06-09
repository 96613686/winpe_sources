# FourthOrderCrossover_GetCoef_comp_asym

- ea: `0x1800854e0`
- end: `0x180085690`
- name: `FourthOrderCrossover_GetCoef_comp_asym`
- size: `432`
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
_DWORD *__fastcall FourthOrderCrossover_GetCoef_comp_asym(
        double a1,
        int a2,
        __int64 a3,
        __int64 a4,
        _DWORD *a5,
        _DWORD *a6)
{
  double v6; // xmm5_8
  float v7; // xmm0_4
  float v8; // xmm0_4
  double v9; // xmm4_8
  double v10; // xmm1_8
  float v11; // xmm0_4
  float v12; // xmm0_4
  float v13; // xmm0_4
  double v14; // xmm0_8
  double v15; // xmm1_8
  double v16; // xmm5_8
  __int64 v17; // r8
  __int64 v18; // r9
  __int64 v19; // r9
  _DWORD *result; // rax

  *(_DWORD *)(a4 + 44) = 0;
  *(_DWORD *)a4 = 1065353216;
  *(_DWORD *)(a4 + 4) = -1073741824;
  *(_DWORD *)(a4 + 8) = 1065353216;
  *(_DWORD *)(a4 + 32) = 0;
  v6 = 0.3183098861837907 / a1 * (double)a2;
  v7 = (v6 + 1.006230589874905) * v6 + 0.8049844718999243;
  *(float *)(a4 + 12) = v7;
  v8 = 0.8049844718999243 - v6 * v6 + 0.8049844718999243 - v6 * v6;
  *(float *)(a4 + 16) = v8;
  v9 = v6 * v6 * 1.007230589874905;
  v10 = v6 * v6 * v6;
  v11 = v6 * v6 - v6 * 1.006230589874905 + 0.8049844718999243;
  *(float *)(a4 + 20) = v11;
  v12 = v10;
  *(float *)(a4 + 24) = v12;
  v13 = COERCE_DOUBLE(*(_QWORD *)&v10 ^ _xmm);
  *(float *)(a4 + 28) = v13;
  v14 = v6 + 0.001;
  v15 = 0.001 - v6;
  v16 = v6 * 0.8059844718999243;
  *(float *)&v14 = v14;
  *(_DWORD *)(a4 + 36) = LODWORD(v14);
  *(float *)&v14 = v15;
  *(_DWORD *)(a4 + 40) = LODWORD(v14);
  *(float *)&v14 = v9 + v16 + 0.0008049844718999243;
  *(_DWORD *)a3 = LODWORD(v14);
  *(float *)&v14 = 0.0008049844718999243 - v9 + 0.0008049844718999243 - v9;
  *(_DWORD *)(a3 + 4) = LODWORD(v14);
  *(float *)(a3 + 8) = v9 - v16 + 0.0008049844718999243;
  *(_DWORD *)(a3 + 12) = *(_DWORD *)(a4 + 12);
  *(_DWORD *)(a3 + 16) = *(_DWORD *)(a4 + 16);
  *(_DWORD *)(a3 + 20) = *(_DWORD *)(a4 + 20);
  *(_DWORD *)(a3 + 24) = 1065353216;
  *(_QWORD *)(a3 + 28) = 1065353216;
  *(_DWORD *)(a3 + 36) = *(_DWORD *)(a4 + 36);
  *(_DWORD *)(a3 + 40) = *(_DWORD *)(a4 + 40);
  *(_DWORD *)(a3 + 44) = *(_DWORD *)(a4 + 44);
  NormalizeY0(a3);
  NormalizeY0(v17 + 24);
  NormalizeY0(v18);
  NormalizeY0(v19 + 24);
  *a6 = 1068708659;
  result = a5;
  *a5 = 1068708659;
  return result;
}

```

## disassembly

```asm
0x1800854e0  sub     rsp, 28h
0x1800854e4  movsd   xmm5, cs:__real@3fd45f306dc9c883
0x1800854ec  mov     r11d, 3F800000h
0x1800854f2  movsd   xmm2, cs:__real@3fe9c26ecb9322dd
0x1800854fa  xor     r10d, r10d
0x1800854fd  divsd   xmm5, xmm0
0x180085501  mov     [r9+2Ch], r10d
0x180085505  mov     rcx, r8
0x180085508  mov     [r9], r11d
0x18008550b  mov     dword ptr [r9+4], 0C0000000h
0x180085513  mov     [r9+8], r11d
0x180085517  mov     [r9+20h], r10d
0x18008551b  mov     eax, edx
0x18008551d  xorps   xmm0, xmm0
0x180085520  cvtsi2sd xmm0, rax
0x180085525  mulsd   xmm5, xmm0
0x180085529  movaps  xmm4, xmm5
0x18008552c  movaps  xmm0, xmm5
0x18008552f  addsd   xmm0, cs:__real@3ff019853f3bf5ca
0x180085537  mulsd   xmm4, xmm5
0x18008553b  movaps  xmm1, xmm5
0x18008553e  mulsd   xmm1, cs:__real@3ff019853f3bf5ca
0x180085546  mulsd   xmm0, xmm5
0x18008554a  addsd   xmm0, xmm2
0x18008554e  cvtpd2ps xmm0, xmm0
0x180085552  movss   dword ptr [r9+0Ch], xmm0
0x180085558  movaps  xmm0, xmm2
0x18008555b  subsd   xmm0, xmm4
0x18008555f  addsd   xmm0, xmm0
0x180085563  cvtpd2ps xmm0, xmm0
0x180085567  movss   dword ptr [r9+10h], xmm0
0x18008556d  movaps  xmm0, xmm4
0x180085570  subsd   xmm0, xmm1
0x180085574  movaps  xmm1, xmm4
0x180085577  mulsd   xmm4, cs:__real@3ff01d9dd2b0b234
0x18008557f  mulsd   xmm1, xmm5
0x180085583  addsd   xmm0, xmm2
0x180085587  movsd   xmm2, cs:__real@3f4a60b2fd843c47
0x18008558f  cvtpd2ps xmm0, xmm0
0x180085593  movss   dword ptr [r9+14h], xmm0
0x180085599  cvtpd2ps xmm0, xmm1
0x18008559d  xorps   xmm1, cs:__xmm@80000000000000008000000000000000
0x1800855a4  movss   dword ptr [r9+18h], xmm0
0x1800855aa  xorps   xmm0, xmm0
0x1800855ad  cvtsd2ss xmm0, xmm1
0x1800855b1  movsd   xmm1, cs:__real@3f50624dd2f1a9fc
0x1800855b9  movss   dword ptr [r9+1Ch], xmm0
0x1800855bf  movaps  xmm0, xmm5
0x1800855c2  addsd   xmm0, xmm1
0x1800855c6  subsd   xmm1, xmm5
0x1800855ca  mulsd   xmm5, cs:__real@3fe9ca9ff27c9bb2
0x1800855d2  cvtpd2ps xmm0, xmm0
0x1800855d6  movss   dword ptr [r9+24h], xmm0
0x1800855dc  cvtpd2ps xmm0, xmm1
0x1800855e0  movaps  xmm1, xmm2
0x1800855e3  movss   dword ptr [r9+28h], xmm0
0x1800855e9  subsd   xmm1, xmm4
0x1800855ed  movaps  xmm0, xmm4
0x1800855f0  subsd   xmm4, xmm5
0x1800855f4  addsd   xmm0, xmm5
0x1800855f8  addsd   xmm1, xmm1
0x1800855fc  addsd   xmm4, xmm2
0x180085600  addsd   xmm0, xmm2
0x180085604  cvtpd2ps xmm0, xmm0
0x180085608  movss   dword ptr [r8], xmm0
0x18008560d  cvtpd2ps xmm0, xmm1
0x180085611  movss   dword ptr [r8+4], xmm0
0x180085617  cvtpd2ps xmm0, xmm4
0x18008561b  movss   dword ptr [r8+8], xmm0
0x180085621  mov     eax, [r9+0Ch]
0x180085625  mov     [r8+0Ch], eax
0x180085629  mov     eax, [r9+10h]
0x18008562d  mov     [r8+10h], eax
0x180085631  mov     eax, [r9+14h]
0x180085635  mov     [r8+14h], eax
0x180085639  mov     [r8+18h], r11d
0x18008563d  mov     [r8+1Ch], r11
0x180085641  mov     eax, [r9+24h]
0x180085645  mov     [r8+24h], eax
0x180085649  mov     eax, [r9+28h]
0x18008564d  mov     [r8+28h], eax
0x180085651  mov     eax, [r9+2Ch]
0x180085655  mov     [r8+2Ch], eax
0x180085659  call    NormalizeY0
0x18008565e  lea     rcx, [r8+18h]
0x180085662  call    NormalizeY0
0x180085667  mov     rcx, r9
0x18008566a  call    NormalizeY0
0x18008566f  lea     rcx, [r9+18h]
0x180085673  call    NormalizeY0
0x180085678  mov     rax, [rsp+28h+arg_28]
0x18008567d  mov     ecx, 3FB33333h
0x180085682  mov     [rax], ecx
0x180085684  mov     rax, [rsp+28h+arg_20]
0x180085689  mov     [rax], ecx
0x18008568b  add     rsp, 28h
0x18008568f  retn
```
