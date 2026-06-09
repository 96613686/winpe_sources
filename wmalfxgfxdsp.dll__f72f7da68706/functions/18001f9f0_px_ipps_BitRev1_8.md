# px_ipps_BitRev1_8

- ea: `0x18001f9f0`
- end: `0x18001fa96`
- name: `px_ipps_BitRev1_8`
- size: `166`
- prototype: ``
- caller_count: `9`
- callee_count: `1`
- tags: ``

## callers

- `0x180018990`
- `0x180018af0`
- `0x180018ccc`
- `0x1800194e0`
- `0x1800196c0`
- `0x18001981c`
- `0x180023ea0`
- `0x1800243d8`
- `0x18002447c`

## callees

- `0x18001f9f0`

## pseudocode

```c
void __fastcall px_ipps_BitRev1_8(__int64 a1, int a2, int *a3)
{
  int *v3; // r9
  __int64 v5; // r11
  int v6; // eax
  int i; // ecx
  __int64 v8; // r8
  __int64 v9; // rax
  __int64 v10; // rax
  __int64 v11; // rax
  __int64 v12; // rax
  int v13; // eax
  int v14; // ecx
  __int64 v15; // rdx
  __int64 v16; // rax

  v3 = a3;
  if ( a2 >= 4 )
  {
    v5 = a1 + 8 * ((__int64)a2 >> 1);
    v6 = *a3;
    for ( i = a3[1]; ; i = v3[1] )
    {
      v13 = v6 >> 1;
      v14 = i >> 1;
      if ( v13 <= 0 )
        break;
      v8 = v13;
      v3 += 2;
      v9 = *(_QWORD *)(a1 + 8LL * v13);
      *(_QWORD *)(a1 + 8 * v8) = *(_QWORD *)(a1 + 8LL * v14);
      *(_QWORD *)(a1 + 8LL * v14) = v9;
      v10 = *(_QWORD *)(a1 + 8 * v8 + 8);
      *(_QWORD *)(a1 + 8 * v8 + 8) = *(_QWORD *)(v5 + 8LL * v14);
      *(_QWORD *)(v5 + 8LL * v14) = v10;
      v11 = *(_QWORD *)(v5 + 8 * v8);
      *(_QWORD *)(v5 + 8 * v8) = *(_QWORD *)(a1 + 8LL * v14 + 8);
      *(_QWORD *)(a1 + 8LL * v14 + 8) = v11;
      v12 = *(_QWORD *)(v5 + 8 * v8 + 8);
      *(_QWORD *)(v5 + 8 * v8 + 8) = *(_QWORD *)(v5 + 8LL * v14 + 8);
      *(_QWORD *)(v5 + 8LL * v14 + 8) = v12;
      v6 = *v3;
    }
    do
    {
      v15 = v13;
      ++v3;
      v16 = *(_QWORD *)(a1 + 8LL * v13 + 8);
      *(_QWORD *)(a1 + 8 * v15 + 8) = *(_QWORD *)(v5 + 8 * v15);
      *(_QWORD *)(v5 + 8 * v15) = v16;
      v13 = *v3 >> 1;
    }
    while ( v13 > 0 );
  }
}

```

## disassembly

```asm
0x18001f9f0  mov     r9, r8
0x18001f9f3  mov     r10, rcx
0x18001f9f6  cmp     edx, 4
0x18001f9f9  jl      locret_18001FA95
0x18001f9ff  movsxd  rax, edx
0x18001fa02  sar     rax, 1
0x18001fa05  lea     r11, [rcx+rax*8]
0x18001fa09  mov     eax, [r8]
0x18001fa0c  mov     ecx, [r8+4]
0x18001fa10  jmp     short loc_18001FA6B
0x18001fa12  movsxd  rdx, ecx
0x18001fa15  movsxd  r8, eax
0x18001fa18  add     r9, 8
0x18001fa1c  mov     rcx, [r10+rdx*8]
0x18001fa20  mov     rax, [r10+r8*8]
0x18001fa24  mov     [r10+r8*8], rcx
0x18001fa28  mov     [r10+rdx*8], rax
0x18001fa2c  mov     rax, [r10+r8*8+8]
0x18001fa31  mov     rcx, [r11+rdx*8]
0x18001fa35  mov     [r10+r8*8+8], rcx
0x18001fa3a  mov     [r11+rdx*8], rax
0x18001fa3e  mov     rcx, [r10+rdx*8+8]
0x18001fa43  mov     rax, [r11+r8*8]
0x18001fa47  mov     [r11+r8*8], rcx
0x18001fa4b  mov     [r10+rdx*8+8], rax
0x18001fa50  mov     rcx, [r11+rdx*8+8]
0x18001fa55  mov     rax, [r11+r8*8+8]
0x18001fa5a  mov     [r11+r8*8+8], rcx
0x18001fa5f  mov     [r11+rdx*8+8], rax
0x18001fa64  mov     eax, [r9]
0x18001fa67  mov     ecx, [r9+4]
0x18001fa6b  sar     eax, 1
0x18001fa6d  sar     ecx, 1
0x18001fa6f  test    eax, eax
0x18001fa71  jg      short loc_18001FA12
0x18001fa73  movsxd  rdx, eax
0x18001fa76  lea     r9, [r9+4]
0x18001fa7a  mov     rax, [r10+rdx*8+8]
0x18001fa7f  mov     rcx, [r11+rdx*8]
0x18001fa83  mov     [r10+rdx*8+8], rcx
0x18001fa88  mov     [r11+rdx*8], rax
0x18001fa8c  mov     eax, [r9]
0x18001fa8f  sar     eax, 1
0x18001fa91  test    eax, eax
0x18001fa93  jg      short loc_18001FA73
0x18001fa95  retn
```
