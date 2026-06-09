# WinHvCreateTdMigrationBundle

- ea: `0x1400243d0`
- end: `0x140024566`
- name: `WinHvCreateTdMigrationBundle`
- size: `406`
- prototype: `__int64 __fastcall(int, int)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x140001ef0`
- `0x140004408`
- `0x14000a040`
- `0x1400243d0`
- `0x140024670`

## pseudocode

```c
__int64 __fastcall WinHvCreateTdMigrationBundle(__int64 a1, unsigned int a2, int a3, _QWORD *a4)
{
  __int64 result; // rax
  __int64 v9; // rbx
  int v10; // r14d
  __int64 v11; // rdx
  _OWORD *v12; // rcx
  _OWORD *v13; // rax
  __int128 v14; // xmm1
  __int128 v15; // xmm0
  __int128 v16; // xmm1
  __int128 v17; // xmm0
  __int128 v18; // xmm1
  __int128 v19; // xmm0
  __int128 v20; // xmm1
  __int64 Src; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v22; // [rsp+48h] [rbp-B8h] BYREF
  _QWORD v23[3]; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE v24[272]; // [rsp+70h] [rbp-90h] BYREF
  __int64 v25; // [rsp+1A0h] [rbp+A0h] BYREF

  v25 = 0;
  memset(v24, 0, 0x108u);
  v23[2] = 0;
  Src = a1;
  v22 = 0;
  WinHvpSetProximityDomain(&v22, a2);
  DWORD2(v22) = a3;
  result = WinHvpAllocatingHypercall(a1, a2, 311, 0, &Src, 0x18u, &v25, 8u);
  if ( (int)result >= 0 )
  {
    v9 = v25;
    v23[0] = a1;
    v23[1] = v25;
    v10 = WinHvpAllocatingHypercall(a1, a2, 312, 0, v23, 0x18u, v24, 0x108u);
    if ( v10 < 0 )
    {
      WinHvDeleteTdMigrationBundle(a1, v9);
      *a4 = -1;
    }
    else
    {
      v11 = 2;
      *a4 = v9;
      v12 = a4 + 1;
      v13 = v24;
      do
      {
        v14 = v13[1];
        *v12 = *v13;
        v15 = v13[2];
        v12[1] = v14;
        v16 = v13[3];
        v12[2] = v15;
        v17 = v13[4];
        v12[3] = v16;
        v18 = v13[5];
        v12[4] = v17;
        v19 = v13[6];
        v12[5] = v18;
        v20 = v13[7];
        v13 += 8;
        v12[6] = v19;
        v12[7] = v20;
        v12 += 8;
        --v11;
      }
      while ( v11 );
      *(_QWORD *)v12 = *(_QWORD *)v13;
    }
    return (unsigned int)v10;
  }
  return result;
}

```

## disassembly

```asm
0x1400243d0  mov     [rsp-8+arg_8], rbx
0x1400243d5  mov     [rsp-8+arg_10], rsi
0x1400243da  push    rbp
0x1400243db  push    rdi
0x1400243dc  push    r14
0x1400243de  lea     rbp, [rsp-80h]
0x1400243e3  sub     rsp, 180h
0x1400243ea  mov     ebx, r8d
0x1400243ed  mov     [rbp+90h+arg_0], 0
0x1400243f8  mov     r14d, edx
0x1400243fb  mov     rsi, rcx
0x1400243fe  xor     edx, edx; Val
0x140024400  lea     rcx, [rsp+190h+var_120]; void *
0x140024405  mov     r8d, 108h; Size
0x14002440b  mov     rdi, r9
0x14002440e  call    memset
0x140024413  xorps   xmm0, xmm0
0x140024416  mov     [rsp+190h+var_128], 0
0x14002441f  mov     edx, r14d
0x140024422  mov     [rsp+190h+var_150], rsi
0x140024427  lea     rcx, [rsp+190h+var_148]
0x14002442c  movdqu  [rsp+190h+var_148], xmm0
0x140024432  call    WinHvpSetProximityDomain
0x140024437  mov     [rsp+190h+var_158], 8; size_t
0x140024440  lea     rax, [rbp+90h+arg_0]
0x140024447  mov     [rsp+190h+var_160], rax; void *
0x14002444c  xor     r9d, r9d; int
0x14002444f  lea     rax, [rsp+190h+var_150]
0x140024454  mov     [rsp+190h+Size], 18h; Size
0x14002445d  mov     r8d, 137h; int
0x140024463  mov     [rsp+190h+Src], rax; Src
0x140024468  mov     edx, r14d; int
0x14002446b  mov     dword ptr [rsp+190h+var_148+8], ebx
0x14002446f  mov     rcx, rsi; int
0x140024472  call    WinHvpAllocatingHypercall
0x140024477  test    eax, eax
0x140024479  js      loc_14002454D
0x14002447f  mov     rbx, [rbp+90h+arg_0]
0x140024486  lea     rax, [rsp+190h+var_120]
0x14002448b  mov     [rsp+190h+var_158], 108h; size_t
0x140024494  xor     r9d, r9d; int
0x140024497  mov     [rsp+190h+var_160], rax; void *
0x14002449c  mov     r8d, 138h; int
0x1400244a2  lea     rax, [rsp+190h+var_138]
0x1400244a7  mov     [rsp+190h+Size], 18h; Size
0x1400244b0  mov     edx, r14d; int
0x1400244b3  mov     [rsp+190h+Src], rax; Src
0x1400244b8  mov     rcx, rsi; int
0x1400244bb  mov     [rsp+190h+var_138], rsi
0x1400244c0  mov     [rsp+190h+var_130], rbx
0x1400244c5  call    WinHvpAllocatingHypercall
0x1400244ca  mov     r14d, eax
0x1400244cd  test    eax, eax
0x1400244cf  js      short loc_140024538
0x1400244d1  mov     edx, 2
0x1400244d6  mov     [rdi], rbx
0x1400244d9  lea     rcx, [rdi+8]
0x1400244dd  lea     rax, [rsp+190h+var_120]
0x1400244e2  lea     r8d, [rdx+7Eh]
0x1400244e6  movups  xmm0, xmmword ptr [rax]
0x1400244e9  movups  xmm1, xmmword ptr [rax+10h]
0x1400244ed  movups  xmmword ptr [rcx], xmm0
0x1400244f0  movups  xmm0, xmmword ptr [rax+20h]
0x1400244f4  movups  xmmword ptr [rcx+10h], xmm1
0x1400244f8  movups  xmm1, xmmword ptr [rax+30h]
0x1400244fc  movups  xmmword ptr [rcx+20h], xmm0
0x140024500  movups  xmm0, xmmword ptr [rax+40h]
0x140024504  movups  xmmword ptr [rcx+30h], xmm1
0x140024508  movups  xmm1, xmmword ptr [rax+50h]
0x14002450c  movups  xmmword ptr [rcx+40h], xmm0
0x140024510  movups  xmm0, xmmword ptr [rax+60h]
0x140024514  movups  xmmword ptr [rcx+50h], xmm1
0x140024518  movups  xmm1, xmmword ptr [rax+70h]
0x14002451c  add     rax, r8
0x14002451f  movups  xmmword ptr [rcx+60h], xmm0
0x140024523  movups  xmmword ptr [rcx+70h], xmm1
0x140024527  add     rcx, r8
0x14002452a  sub     rdx, 1
0x14002452e  jnz     short loc_1400244E6
0x140024530  mov     rax, [rax]
0x140024533  mov     [rcx], rax
0x140024536  jmp     short loc_14002454A
0x140024538  mov     rdx, rbx
0x14002453b  mov     rcx, rsi
0x14002453e  call    WinHvDeleteTdMigrationBundle
0x140024543  mov     qword ptr [rdi], 0FFFFFFFFFFFFFFFFh
0x14002454a  mov     eax, r14d
0x14002454d  lea     r11, [rsp+190h+var_10]
0x140024555  mov     rbx, [r11+28h]
0x140024559  mov     rsi, [r11+30h]
0x14002455d  mov     rsp, r11
0x140024560  pop     r14
0x140024562  pop     rdi
0x140024563  pop     rbp
0x140024564  retn
```
