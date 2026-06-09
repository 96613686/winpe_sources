# WinHvCreatePort

- ea: `0x1400261c0`
- end: `0x14002625f`
- name: `WinHvCreatePort`
- size: `159`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x140001ef0`
- `0x140004408`

## pseudocode

```c
__int64 __fastcall WinHvCreatePort(__int64 a1, __int64 a2, int a3, unsigned __int64 a4, __int64 a5, char a6, char a7)
{
  __int64 v7; // xmm1_8
  unsigned int v8; // r10d
  __int64 v9; // r11
  __int64 Src; // [rsp+40h] [rbp-40h] BYREF
  int v12; // [rsp+48h] [rbp-38h]
  char v13; // [rsp+4Ch] [rbp-34h]
  char v14; // [rsp+4Dh] [rbp-33h]
  __int16 v15; // [rsp+4Eh] [rbp-32h]
  __m256i v16; // [rsp+50h] [rbp-30h]
  __int64 v17; // [rsp+70h] [rbp-10h] BYREF

  v15 = 0;
  v17 = 0;
  v13 = a6;
  *(_OWORD *)&v16.m256i_u64[2] = 0;
  v14 = a7;
  Src = a1;
  v12 = a3;
  *(_OWORD *)v16.m256i_i8 = a4;
  v7 = *(_QWORD *)(a5 + 16);
  *(_OWORD *)&v16.m256i_u64[1] = *(_OWORD *)a5;
  v16.m256i_i64[3] = v7;
  WinHvpSetProximityDomain(&v17, a2);
  return WinHvpAllocatingHypercall(v9, v8, 149, 0, &Src, 0x38u, 0, 0);
}

```

## disassembly

```asm
0x1400261c0  push    rbp
0x1400261c2  mov     rbp, rsp
0x1400261c5  sub     rsp, 80h
0x1400261cc  xor     eax, eax
0x1400261ce  xorps   xmm0, xmm0
0x1400261d1  movups  [rbp+var_40], xmm0
0x1400261d5  mov     [rbp+var_10], rax
0x1400261d9  mov     r11, rcx
0x1400261dc  mov     al, [rbp+arg_28]
0x1400261df  mov     r10d, edx
0x1400261e2  movups  [rbp+var_30], xmm0
0x1400261e6  mov     byte ptr [rbp+var_40+0Ch], al
0x1400261e9  mov     al, [rbp+arg_30]
0x1400261ec  movups  [rbp+var_20], xmm0
0x1400261f0  mov     byte ptr [rbp+var_40+0Dh], al
0x1400261f3  mov     rax, [rbp+arg_20]
0x1400261f7  mov     qword ptr [rbp+var_40], rcx
0x1400261fb  lea     rcx, [rbp+var_10]
0x1400261ff  mov     dword ptr [rbp+var_40+8], r8d
0x140026203  mov     qword ptr [rbp+var_30], r9
0x140026207  movups  xmm0, xmmword ptr [rax]
0x14002620a  movsd   xmm1, qword ptr [rax+10h]
0x14002620f  movups  [rbp+var_30+8], xmm0
0x140026213  movsd   qword ptr [rbp+var_20+8], xmm1
0x140026218  call    WinHvpSetProximityDomain
0x14002621d  mov     [rsp+80h+var_48], 0; size_t
0x140026226  lea     rax, [rbp+var_40]
0x14002622a  mov     [rsp+80h+var_50], 0; void *
0x140026233  xor     r9d, r9d; int
0x140026236  mov     [rsp+80h+Size], 38h ; '8'; Size
0x14002623f  mov     r8d, 95h; int
0x140026245  mov     edx, r10d; int
0x140026248  mov     [rsp+80h+Src], rax; Src
0x14002624d  mov     rcx, r11; int
0x140026250  call    WinHvpAllocatingHypercall
0x140026255  add     rsp, 80h
0x14002625c  pop     rbp
0x14002625d  retn
```
