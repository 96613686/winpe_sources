# px_ipps_cCcsRecombine_32f

- ea: `0x180024780`
- end: `0x1800249aa`
- name: `px_ipps_cCcsRecombine_32f`
- size: `554`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800194e0`
- `0x18001981c`

## callees

- `0x180024780`

## pseudocode

```c
void __fastcall px_ipps_cCcsRecombine_32f(__int64 a1, __int64 a2, int a3, int a4, __int64 a5)
{
  int v5; // eax
  float *v6; // rdi
  __int64 v7; // r11
  float *v8; // rbx
  __int64 v9; // r9
  __int64 v10; // r10
  __int64 v11; // rax
  float v12; // xmm7_4
  float v13; // xmm0_4
  float v14; // xmm6_4
  float v15; // xmm4_4
  float v16; // xmm7_4
  float v17; // xmm2_4
  float v18; // xmm6_4
  float v19; // xmm5_4
  float v20; // xmm3_4
  float *v21; // rdi
  __int64 v22; // r11
  float *v23; // rbx
  __int64 v24; // r9
  __int64 v25; // r10
  __int64 v26; // rax
  float v27; // xmm7_4
  float v28; // xmm2_4
  float v29; // xmm6_4
  float v30; // xmm4_4
  float v31; // xmm7_4
  float v32; // xmm3_4
  float v33; // xmm5_4

  if ( a3 != 1 )
  {
    v5 = 2 * a3 - 2;
    if ( a4 <= 0 )
    {
      if ( a3 > 2 )
      {
        v21 = (float *)(a2 + 4 * (v5 + 1LL));
        v22 = a1 - a2;
        v23 = (float *)(a5 + 12);
        v24 = a1 - a5;
        v25 = a2 - a5;
        v26 = ((unsigned int)(a3 - 3) >> 1) + 1;
        do
        {
          v27 = *(float *)((char *)v21 + v22 - 4);
          v28 = *(float *)((char *)v23 + v24) + *(float *)((char *)v21 + v22);
          v29 = *(float *)((char *)v23 + v24) - *(float *)((char *)v21 + v22);
          v30 = *(float *)((char *)v23 + v24 - 4) - v27;
          v31 = v27 + *(float *)((char *)v23 + v24 - 4);
          v32 = (float)(*v23 * v30) - (float)(*(v23 - 1) * v28);
          v33 = (float)(*(v23 - 1) * v30) + (float)(*v23 * v28);
          *(float *)((char *)v23 + v25 - 4) = v32 + v31;
          *(float *)((char *)v23 + v25) = v33 + v29;
          v23 += 2;
          *(v21 - 1) = v31 - v32;
          *v21 = v33 - v29;
          v21 -= 2;
          --v26;
        }
        while ( v26 );
      }
      *(float *)(a2 + 4LL * a3) = *(float *)(a1 + 4LL * a3) * 2.0;
      *(float *)(a2 + 4LL * a3 + 4) = *(float *)(a1 + 4LL * a3 + 4) * -2.0;
    }
    else
    {
      if ( a3 > 2 )
      {
        v6 = (float *)(a2 + 4 * (v5 + 1LL));
        v7 = a1 - a2;
        v8 = (float *)(a5 + 12);
        v9 = a1 - a5;
        v10 = a2 - a5;
        v11 = ((unsigned int)(a3 - 3) >> 1) + 1;
        do
        {
          v12 = *(float *)((char *)v6 + v7 - 4);
          v13 = *(v8 - 1);
          v14 = *(float *)((char *)v8 + v9);
          v15 = *(float *)((char *)v8 + v9 - 4) - v12;
          v16 = v12 + *(float *)((char *)v8 + v9 - 4);
          v17 = *(float *)((char *)v6 + v7) + v14;
          v18 = v14 - *(float *)((char *)v6 + v7);
          v19 = (float)(v13 * v15) - (float)(*v8 * v17);
          v20 = (float)(*v8 * v15) + (float)(v13 * v17);
          *(float *)((char *)v8 + v10) = v19 + v18;
          v8 += 2;
          *(float *)((char *)v8 + v10 - 12) = v16 - v20;
          *(v6 - 1) = v20 + v16;
          *v6 = v19 - v18;
          v6 -= 2;
          --v11;
        }
        while ( v11 );
      }
      *(float *)(a2 + 4LL * a3) = *(float *)(a1 + 4LL * a3) * 2.0;
      *(float *)(a2 + 4LL * a3 + 4) = *(float *)(a1 + 4LL * a3 + 4) * 2.0;
    }
  }
}

```

## disassembly

```asm
0x180024780  cmp     r8d, 1
0x180024784  jz      locret_1800249A9
0x18002478a  mov     [rsp+arg_0], rbx
0x18002478f  push    rdi
0x180024790  sub     rsp, 20h
0x180024794  movaps  [rsp+28h+var_18], xmm6
0x180024799  lea     eax, ds:0FFFFFFFFFFFFFFFEh[r8*2]
0x1800247a1  movaps  [rsp+28h+var_28], xmm7
0x1800247a5  test    r9d, r9d
0x1800247a8  jle     loc_1800248A5
0x1800247ae  cmp     r8d, 2
0x1800247b2  jle     loc_180024877
0x1800247b8  cdqe
0x1800247ba  mov     r9, rcx
0x1800247bd  mov     r10, rdx
0x1800247c0  inc     rax
0x1800247c3  mov     r11, rcx
0x1800247c6  lea     rdi, [rdx+rax*4]
0x1800247ca  mov     rax, [rsp+28h+arg_20]
0x1800247cf  sub     r11, rdx
0x1800247d2  lea     rbx, [rax+0Ch]
0x1800247d6  sub     r9, rax
0x1800247d9  sub     r10, rax
0x1800247dc  lea     eax, [r8-3]
0x1800247e0  shr     eax, 1
0x1800247e2  inc     eax
0x1800247e4  movss   xmm7, dword ptr [rdi+r11-4]
0x1800247eb  movss   xmm1, dword ptr [rbx]
0x1800247ef  movss   xmm5, dword ptr [rbx-4]
0x1800247f4  movaps  xmm0, xmm5
0x1800247f7  movaps  xmm3, xmm1
0x1800247fa  movss   xmm6, dword ptr [rbx+r9]
0x180024800  movss   xmm4, dword ptr [rbx+r9-4]
0x180024807  movss   xmm2, dword ptr [r11+rdi]
0x18002480d  subss   xmm4, xmm7
0x180024811  addss   xmm7, dword ptr [rbx+r9-4]
0x180024818  addss   xmm2, xmm6
0x18002481c  mulss   xmm5, xmm4
0x180024820  mulss   xmm1, xmm2
0x180024824  mulss   xmm0, xmm2
0x180024828  subss   xmm6, dword ptr [r11+rdi]
0x18002482e  subss   xmm5, xmm1
0x180024832  mulss   xmm3, xmm4
0x180024836  movaps  xmm1, xmm5
0x180024839  addss   xmm3, xmm0
0x18002483d  addss   xmm1, xmm6
0x180024841  subss   xmm5, xmm6
0x180024845  movaps  xmm0, xmm7
0x180024848  movss   dword ptr [rbx+r10], xmm1
0x18002484e  subss   xmm0, xmm3
0x180024852  addss   xmm3, xmm7
0x180024856  add     rbx, 8
0x18002485a  movss   dword ptr [rbx+r10-0Ch], xmm0
0x180024861  movss   dword ptr [rdi-4], xmm3
0x180024866  movss   dword ptr [rdi], xmm5
0x18002486a  sub     rdi, 8
0x18002486e  dec     rax
0x180024871  jnz     loc_1800247E4
0x180024877  movsxd  rax, r8d
0x18002487a  movss   xmm0, dword ptr [rcx+rax*4]
0x18002487f  mulss   xmm0, cs:__real@40000000
0x180024887  movss   dword ptr [rdx+rax*4], xmm0
0x18002488c  movss   xmm0, dword ptr [rcx+rax*4+4]
0x180024892  mulss   xmm0, cs:__real@40000000
0x18002489a  movss   dword ptr [rdx+rax*4+4], xmm0
0x1800248a0  jmp     loc_180024996
0x1800248a5  cmp     r8d, 2
0x1800248a9  jle     loc_18002496D
0x1800248af  cdqe
0x1800248b1  mov     r9, rcx
0x1800248b4  mov     r10, rdx
0x1800248b7  inc     rax
0x1800248ba  mov     r11, rcx
0x1800248bd  lea     rdi, [rdx+rax*4]
0x1800248c1  mov     rax, [rsp+28h+arg_20]
0x1800248c6  sub     r11, rdx
0x1800248c9  lea     rbx, [rax+0Ch]
0x1800248cd  sub     r9, rax
0x1800248d0  sub     r10, rax
0x1800248d3  lea     eax, [r8-3]
0x1800248d7  shr     eax, 1
0x1800248d9  inc     eax
0x1800248db  movss   xmm1, dword ptr [rbx]
0x1800248df  movss   xmm5, dword ptr [rbx-4]
0x1800248e4  movss   xmm6, dword ptr [rbx+r9]
0x1800248ea  movaps  xmm3, xmm1
0x1800248ed  movaps  xmm0, xmm5
0x1800248f0  movaps  xmm2, xmm6
0x1800248f3  movss   xmm7, dword ptr [rdi+r11-4]
0x1800248fa  addss   xmm2, dword ptr [r11+rdi]
0x180024900  subss   xmm6, dword ptr [r11+rdi]
0x180024906  mulss   xmm0, xmm2
0x18002490a  mulss   xmm1, xmm2
0x18002490e  movss   xmm4, dword ptr [rbx+r9-4]
0x180024915  subss   xmm4, xmm7
0x180024919  addss   xmm7, dword ptr [rbx+r9-4]
0x180024920  mulss   xmm5, xmm4
0x180024924  mulss   xmm3, xmm4
0x180024928  subss   xmm3, xmm0
0x18002492c  addss   xmm5, xmm1
0x180024930  movaps  xmm1, xmm5
0x180024933  movaps  xmm0, xmm3
0x180024936  addss   xmm0, xmm7
0x18002493a  addss   xmm1, xmm6
0x18002493e  subss   xmm7, xmm3
0x180024942  movss   dword ptr [rbx+r10-4], xmm0
0x180024949  movss   dword ptr [rbx+r10], xmm1
0x18002494f  subss   xmm5, xmm6
0x180024953  add     rbx, 8
0x180024957  movss   dword ptr [rdi-4], xmm7
0x18002495c  movss   dword ptr [rdi], xmm5
0x180024960  sub     rdi, 8
0x180024964  dec     rax
0x180024967  jnz     loc_1800248DB
0x18002496d  movsxd  rax, r8d
0x180024970  movss   xmm0, dword ptr [rcx+rax*4]
0x180024975  mulss   xmm0, cs:__real@40000000
0x18002497d  movss   dword ptr [rdx+rax*4], xmm0
0x180024982  movss   xmm1, dword ptr [rcx+rax*4+4]
0x180024988  mulss   xmm1, cs:__real@c0000000
0x180024990  movss   dword ptr [rdx+rax*4+4], xmm1
0x180024996  mov     rbx, [rsp+28h+arg_0]
0x18002499b  movaps  xmm6, [rsp+28h+var_18]
0x1800249a0  movaps  xmm7, [rsp+28h+var_28]
0x1800249a4  add     rsp, 20h
0x1800249a8  pop     rdi
0x1800249a9  retn
```
