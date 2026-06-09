# px_ipps_cbMpy3_32fc

- ea: `0x18001fd08`
- end: `0x18001fe16`
- name: `px_ipps_cbMpy3_32fc`
- size: `270`
- prototype: ``
- caller_count: `9`
- callee_count: `1`
- tags: ``

## callers

- `0x180059468`
- `0x180059720`
- `0x180059898`
- `0x18005bb98`
- `0x18005be50`
- `0x18005bfc8`
- `0x18005e6fc`
- `0x18005e9b4`
- `0x18005eb2c`

## callees

- `0x18001fd08`

## pseudocode

```c
__int64 __fastcall px_ipps_cbMpy3_32fc(__int64 a1, __int64 a2, __int64 a3, int a4)
{
  __int64 result; // rax
  __int64 v5; // r11
  __int64 v6; // rbx
  float *v7; // rdi
  __int64 v8; // r10
  float v9; // xmm6_4
  float v10; // xmm2_4
  float v11; // xmm3_4
  float v12; // xmm1_4
  float v13; // xmm2_4
  float v14; // xmm4_4
  float v15; // xmm0_4
  float v16; // xmm1_4
  float v17; // xmm2_4
  float v18; // xmm3_4

  result = 0;
  if ( a4 - 1 > 0 )
  {
    v5 = a2 - a1;
    v6 = a3 - a1;
    v7 = (float *)(a1 + 12);
    v8 = ((unsigned int)(a4 - 2) >> 1) + 1;
    result = (unsigned int)(2 * v8);
    do
    {
      v9 = *(float *)((char *)v7 + v5 - 8);
      v10 = *(v7 - 1);
      v11 = v10 * *(float *)((char *)v7 + v5);
      v12 = *(float *)((char *)v7 + v5 - 4);
      v13 = v10 * v12;
      v14 = (float)(*(v7 - 3) * v9) + (float)(*(float *)((char *)v7 + v5 - 12) * *(v7 - 2));
      v15 = *(float *)((char *)v7 + v5) * *v7;
      v16 = v12 * *v7;
      *(float *)((char *)v7 + v6 - 12) = (float)(*(float *)((char *)v7 + v5 - 12) * *(v7 - 3)) - (float)(v9 * *(v7 - 2));
      *(float *)((char *)v7 + v6 - 8) = v14;
      *(float *)((char *)v7 + v6 - 4) = v13 - v15;
      *(float *)((char *)v7 + v6) = v11 + v16;
      v7 += 4;
      --v8;
    }
    while ( v8 );
  }
  if ( (a4 & 1) != 0 )
  {
    result = (int)result;
    v17 = *(float *)(a1 + 8LL * (int)result + 4);
    v18 = (float)(*(float *)(a2 + 8LL * (int)result) * *(float *)(a1 + 8LL * (int)result))
        - (float)(v17 * *(float *)(a2 + 8LL * (int)result + 4));
    *(float *)(a3 + 8LL * (int)result + 4) = (float)(*(float *)(a2 + 8LL * (int)result) * v17)
                                           + (float)(*(float *)(a2 + 8LL * (int)result + 4)
                                                   * *(float *)(a1 + 8LL * (int)result));
    *(float *)(a3 + 8LL * (int)result) = v18;
  }
  return result;
}

```

## disassembly

```asm
0x18001fd08  mov     [rsp+arg_0], rbx
0x18001fd0d  push    rdi
0x18001fd0e  sub     rsp, 10h
0x18001fd12  lea     r10d, [r9-1]
0x18001fd16  xor     eax, eax
0x18001fd18  movaps  [rsp+18h+var_18], xmm6
0x18001fd1c  test    r10d, r10d
0x18001fd1f  jle     loc_18001FDC2
0x18001fd25  lea     eax, [r10-1]
0x18001fd29  mov     r11, rdx
0x18001fd2c  mov     rbx, r8
0x18001fd2f  shr     eax, 1
0x18001fd31  sub     r11, rcx
0x18001fd34  sub     rbx, rcx
0x18001fd37  inc     eax
0x18001fd39  lea     rdi, [rcx+0Ch]
0x18001fd3d  mov     r10d, eax
0x18001fd40  add     eax, eax
0x18001fd42  movss   xmm5, dword ptr [r11+rdi-0Ch]
0x18001fd49  movss   xmm6, dword ptr [r11+rdi-8]
0x18001fd50  movss   xmm3, dword ptr [rdi-4]
0x18001fd55  movaps  xmm0, xmm5
0x18001fd58  mulss   xmm5, dword ptr [rdi-0Ch]
0x18001fd5d  movaps  xmm2, xmm3
0x18001fd60  mulss   xmm0, dword ptr [rdi-8]
0x18001fd65  mulss   xmm3, dword ptr [r11+rdi]
0x18001fd6b  movss   xmm1, dword ptr [r11+rdi-4]
0x18001fd72  movss   xmm4, dword ptr [rdi-0Ch]
0x18001fd77  mulss   xmm4, xmm6
0x18001fd7b  mulss   xmm6, dword ptr [rdi-8]
0x18001fd80  mulss   xmm2, xmm1
0x18001fd84  addss   xmm4, xmm0
0x18001fd88  movss   xmm0, dword ptr [r11+rdi]
0x18001fd8e  subss   xmm5, xmm6
0x18001fd92  mulss   xmm0, dword ptr [rdi]
0x18001fd96  mulss   xmm1, dword ptr [rdi]
0x18001fd9a  movss   dword ptr [rbx+rdi-0Ch], xmm5
0x18001fda0  movss   dword ptr [rbx+rdi-8], xmm4
0x18001fda6  subss   xmm2, xmm0
0x18001fdaa  addss   xmm3, xmm1
0x18001fdae  movss   dword ptr [rbx+rdi-4], xmm2
0x18001fdb4  movss   dword ptr [rbx+rdi], xmm3
0x18001fdb9  add     rdi, 10h
0x18001fdbd  dec     r10
0x18001fdc0  jnz     short loc_18001FD42
0x18001fdc2  test    r9b, 1
0x18001fdc6  jz      short loc_18001FE07
0x18001fdc8  cdqe
0x18001fdca  movss   xmm3, dword ptr [rdx+rax*8]
0x18001fdcf  movss   xmm2, dword ptr [rcx+rax*8+4]
0x18001fdd5  movss   xmm0, dword ptr [rdx+rax*8+4]
0x18001fddb  mulss   xmm0, dword ptr [rcx+rax*8]
0x18001fde0  movaps  xmm1, xmm3
0x18001fde3  mulss   xmm3, dword ptr [rcx+rax*8]
0x18001fde8  mulss   xmm1, xmm2
0x18001fdec  mulss   xmm2, dword ptr [rdx+rax*8+4]
0x18001fdf2  addss   xmm1, xmm0
0x18001fdf6  subss   xmm3, xmm2
0x18001fdfa  movss   dword ptr [r8+rax*8+4], xmm1
0x18001fe01  movss   dword ptr [r8+rax*8], xmm3
0x18001fe07  mov     rbx, [rsp+18h+arg_0]
0x18001fe0c  movaps  xmm6, [rsp+18h+var_18]
0x18001fe10  add     rsp, 10h
0x18001fe14  pop     rdi
0x18001fe15  retn
```
