# AdaptDiscriminant

- ea: `0x18000c0c0`
- end: `0x18000c3b0`
- name: `AdaptDiscriminant`
- size: `752`
- prototype: ``
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x180005120`
- `0x1800094bc`
- `0x18000bff4`
- `0x18000c028`
- `0x18000c078`
- `0x18000c3b8`

## callees

- `0x18000c0c0`

## pseudocode

```c
__int64 *__fastcall AdaptDiscriminant(int *a1)
{
  __int64 v1; // r10
  int v2; // esi
  __int64 v3; // rdx
  int v4; // edi
  int v5; // r8d
  int v6; // ebx
  int v7; // eax
  int v8; // ebx
  unsigned int v9; // eax
  int v10; // edx
  __int64 *v11; // r9
  __int64 v12; // rax
  __int64 *v13; // r11
  __int64 *v14; // rdx
  __int64 *result; // rax

  v1 = *a1;
  v2 = 1;
  v3 = 4 * v1;
  if ( a1[18] )
  {
    v4 = a1[20];
    v5 = a1[14];
  }
  else
  {
    v5 = *(_DWORD *)((char *)&qword_18004AD10[24] + v3);
    v4 = 0;
    a1[14] = v5;
    *((_QWORD *)a1 + 9) = 1;
    a1[20] = 0;
  }
  v6 = v4;
  v7 = a1[19];
  if ( !*(_DWORD *)((char *)&qword_18004AD10[24] + v3) )
    v6 = a1[19];
  if ( v7 < a1[22] )
  {
    v2 = -1;
    goto LABEL_12;
  }
  if ( v6 > a1[21] )
  {
LABEL_12:
    v5 += v2;
    a1[14] = v5;
    *(_QWORD *)(a1 + 19) = 0;
    goto LABEL_13;
  }
  if ( v7 >= -64 )
  {
    if ( v7 > 64 )
      a1[19] = 64;
  }
  else
  {
    a1[19] = -64;
  }
  if ( v4 >= -64 )
  {
    if ( v4 > 64 )
      a1[20] = 64;
  }
  else
  {
    a1[20] = -64;
  }
LABEL_13:
  v8 = *(_DWORD *)((char *)&qword_18004AE10[15] + v3);
  v9 = 0x80000000;
  if ( v5 )
    v9 = -8;
  v10 = 0x40000000;
  a1[22] = v9;
  if ( v5 != v8 - 1 )
    v10 = 8;
  a1[21] = v10;
  if ( (_DWORD)v1 == 6 )
  {
    v13 = (__int64 *)((char *)qword_18004B080 + 52 * v5);
    *((_QWORD *)a1 + 6) = &qword_18004B150[3 * (v5 - (v5 + 1 == v8))];
    v12 = 88LL * v5;
    v11 = &qword_18004B150[3 * (v5 - (v5 != 0))];
    v14 = qword_1800474B0;
LABEL_21:
    result = (__int64 *)((char *)v14 + v12);
LABEL_22:
    *((_QWORD *)a1 + 8) = result;
    *((_QWORD *)a1 + 4) = v13;
    *((_QWORD *)a1 + 5) = v11;
  }
  else
  {
    v11 = 0;
    switch ( (int)v1 )
    {
      case 4:
        v13 = qword_180047B40;
        result = qword_180047AF0;
        goto LABEL_22;
      case 5:
        v11 = qword_180047AD8;
        v12 = 84LL * v5;
        v13 = (__int64 *)((char *)qword_18004AF60 + 4 * v5 * (2 * (int)v1 + 1));
        v14 = qword_180047A30;
        goto LABEL_21;
      case 7:
        v11 = qword_1800476C8;
        v12 = 92LL * v5;
        v13 = (__int64 *)((char *)qword_18004AE10 + 4 * v5 * (2 * (int)v1 + 1));
        v14 = (__int64 *)a5;
        goto LABEL_21;
      case 8:
        v13 = qword_180047C30;
        result = qword_180047B70;
        goto LABEL_22;
      case 9:
        v11 = qword_180047D98;
        v12 = 100LL * v5;
        v13 = (__int64 *)((char *)qword_18004AEC0 + 4 * v5 * (2 * (int)v1 + 1));
        v14 = qword_180047CD0;
        goto LABEL_21;
      case 12:
        v13 = (__int64 *)((char *)qword_18004B1A0 + 4 * v5 * (2 * (int)v1 + 1));
        *((_QWORD *)a1 + 6) = &_ImageBase[2 * (int)(v1 * (v5 - (v5 + 1 == v8))) + 153568];
        v14 = qword_1800476F0;
        v11 = (__int64 *)((char *)qword_18004AFC0 + 4 * (int)(v1 * (v5 - (v5 != 0))));
        v12 = 112LL * v5;
        goto LABEL_21;
      default:
        result = (__int64 *)(unsigned int)(v1 - 4);
        break;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000c0c0  push    rbx
0x18000c0c2  push    rsi
0x18000c0c3  push    rdi
0x18000c0c4  push    r14
0x18000c0c6  cmp     dword ptr [rcx+48h], 0
0x18000c0ca  lea     r14, __ImageBase
0x18000c0d1  movsxd  r10, dword ptr [rcx]
0x18000c0d4  mov     esi, 1
0x18000c0d9  lea     rdx, ds:0[r10*4]
0x18000c0e1  jz      loc_18000C248
0x18000c0e7  mov     edi, [rcx+50h]
0x18000c0ea  mov     r8d, [rcx+38h]
0x18000c0ee  cmp     dword ptr [rdx+r14+4ADD0h], 0
0x18000c0f7  mov     ebx, edi
0x18000c0f9  mov     eax, [rcx+4Ch]
0x18000c0fc  cmovz   ebx, eax
0x18000c0ff  cmp     eax, [rcx+58h]
0x18000c102  jl      short loc_18000C12B
0x18000c104  cmp     ebx, [rcx+54h]
0x18000c107  jg      short loc_18000C130
0x18000c109  cmp     eax, 0FFFFFFC0h
0x18000c10c  jge     loc_18000C31D
0x18000c112  mov     dword ptr [rcx+4Ch], 0FFFFFFC0h
0x18000c119  cmp     edi, 0FFFFFFC0h
0x18000c11c  jge     loc_18000C266
0x18000c122  mov     dword ptr [rcx+50h], 0FFFFFFC0h
0x18000c129  jmp     short loc_18000C13F
0x18000c12b  mov     esi, 0FFFFFFFFh
0x18000c130  add     r8d, esi
0x18000c133  mov     [rcx+38h], r8d
0x18000c137  mov     qword ptr [rcx+4Ch], 0
0x18000c13f  mov     ebx, [rdx+r14+4AE88h]
0x18000c147  test    r8d, r8d
0x18000c14a  mov     r9d, 0FFFFFFF8h
0x18000c150  mov     eax, 80000000h
0x18000c155  cmovnz  eax, r9d
0x18000c159  mov     edx, 40000000h
0x18000c15e  mov     [rcx+58h], eax
0x18000c161  mov     r9d, 8
0x18000c167  lea     eax, [rbx-1]
0x18000c16a  cmp     r8d, eax
0x18000c16d  cmovnz  edx, r9d
0x18000c171  mov     [rcx+54h], edx
0x18000c174  cmp     r10d, 6
0x18000c178  jz      short loc_18000C1CE
0x18000c17a  lea     eax, [r10-4]; switch 9 cases
0x18000c17e  cmp     eax, r9d
0x18000c181  ja      def_18000C197; jumptable 000000018000C197 default case, cases 6,10,11
0x18000c187  cdqe
0x18000c189  xor     r9d, r9d
0x18000c18c  mov     edx, ds:(jpt_18000C197 - 180000000h)[r14+rax*4]
0x18000c194  add     rdx, r14
0x18000c197  jmp     rdx; switch jump
0x18000c19d  lea     eax, ds:1[r10*2]; jumptable 000000018000C197 case 7
0x18000c1a5  imul    eax, r8d
0x18000c1a9  lea     r11, rva qword_18004AE10[r14]
0x18000c1b0  lea     r9, qword_1800476C8
0x18000c1b7  movsxd  rdx, eax
0x18000c1ba  movsxd  rax, r8d
0x18000c1bd  imul    rax, 5Ch ; '\'
0x18000c1c1  lea     r11, [r11+rdx*4]
0x18000c1c5  lea     rdx, a5; "-5$$\x1B\x1B\x1B\x1B"
0x18000c1cc  jmp     short loc_18000C232
0x18000c1ce  imul    eax, r8d, 0Dh
0x18000c1d2  lea     r11, rva qword_18004B080[r14]
0x18000c1d9  lea     r9, rva qword_18004B150[r14]
0x18000c1e0  movsxd  rdx, eax
0x18000c1e3  lea     eax, [r8+1]
0x18000c1e7  lea     r11, [r11+rdx*4]
0x18000c1eb  xor     edx, edx
0x18000c1ed  cmp     eax, ebx
0x18000c1ef  mov     eax, r8d
0x18000c1f2  setz    dl
0x18000c1f5  sub     eax, edx
0x18000c1f7  lea     eax, [rax+rax*2]
0x18000c1fa  add     eax, eax
0x18000c1fc  movsxd  rdx, eax
0x18000c1ff  lea     rax, rva qword_18004B150[r14]
0x18000c206  lea     rax, [rax+rdx*4]
0x18000c20a  mov     [rcx+30h], rax
0x18000c20e  mov     eax, r8d
0x18000c211  neg     eax
0x18000c213  sbb     edx, edx
0x18000c215  add     edx, r8d
0x18000c218  lea     eax, [rdx+rdx*2]
0x18000c21b  add     eax, eax
0x18000c21d  movsxd  rdx, eax
0x18000c220  movsxd  rax, r8d
0x18000c223  imul    rax, 58h ; 'X'
0x18000c227  lea     r9, [r9+rdx*4]
0x18000c22b  lea     rdx, qword_1800474B0
0x18000c232  add     rax, rdx
0x18000c235  mov     [rcx+40h], rax
0x18000c239  mov     [rcx+20h], r11
0x18000c23d  mov     [rcx+28h], r9
0x18000c241  pop     r14; jumptable 000000018000C197 default case, cases 6,10,11
0x18000c243  pop     rdi
0x18000c244  pop     rsi
0x18000c245  pop     rbx
0x18000c246  retn
0x18000c248  mov     r8d, [rdx+r14+4ADD0h]
0x18000c250  xor     edi, edi
0x18000c252  mov     [rcx+38h], r8d
0x18000c256  mov     [rcx+48h], rsi
0x18000c25a  mov     dword ptr [rcx+50h], 0
0x18000c261  jmp     loc_18000C0EE
0x18000c266  cmp     edi, 40h ; '@'
0x18000c269  jle     loc_18000C13F
0x18000c26f  mov     dword ptr [rcx+50h], 40h ; '@'
0x18000c276  jmp     loc_18000C13F
0x18000c27b  lea     eax, ds:1[r10*2]; jumptable 000000018000C197 case 12
0x18000c283  imul    eax, r8d
0x18000c287  lea     r11, rva qword_18004B1A0[r14]
0x18000c28e  lea     r9, rva qword_18004AFC0[r14]
0x18000c295  movsxd  rdx, eax
0x18000c298  lea     eax, [r8+1]
0x18000c29c  lea     r11, [r11+rdx*4]
0x18000c2a0  xor     edx, edx
0x18000c2a2  cmp     eax, ebx
0x18000c2a4  mov     eax, r8d
0x18000c2a7  setz    dl
0x18000c2aa  sub     eax, edx
0x18000c2ac  imul    eax, r10d
0x18000c2b0  cdqe
0x18000c2b2  lea     rax, ds:4AFC0h[rax*4]
0x18000c2ba  add     rax, r14
0x18000c2bd  mov     [rcx+30h], rax
0x18000c2c1  mov     eax, r8d
0x18000c2c4  neg     eax
0x18000c2c6  sbb     edx, edx
0x18000c2c8  lea     eax, [r8+rdx]
0x18000c2cc  imul    eax, r10d
0x18000c2d0  lea     rdx, qword_1800476F0
0x18000c2d7  cdqe
0x18000c2d9  lea     r9, [r9+rax*4]
0x18000c2dd  movsxd  rax, r8d
0x18000c2e0  imul    rax, 70h ; 'p'
0x18000c2e4  jmp     loc_18000C232
0x18000c2e9  lea     eax, ds:1[r10*2]; jumptable 000000018000C197 case 5
0x18000c2f1  imul    eax, r8d
0x18000c2f5  lea     r11, rva qword_18004AF60[r14]
0x18000c2fc  lea     r9, qword_180047AD8
0x18000c303  movsxd  rdx, eax
0x18000c306  movsxd  rax, r8d
0x18000c309  imul    rax, 54h ; 'T'
0x18000c30d  lea     r11, [r11+rdx*4]
0x18000c311  lea     rdx, qword_180047A30
0x18000c318  jmp     loc_18000C232
0x18000c31d  cmp     eax, 40h ; '@'
0x18000c320  jle     loc_18000C119
0x18000c326  mov     dword ptr [rcx+4Ch], 40h ; '@'
0x18000c32d  jmp     loc_18000C119
0x18000c332  lea     r11, qword_180047B40; jumptable 000000018000C197 case 4
0x18000c339  lea     rax, qword_180047AF0
0x18000c340  jmp     loc_18000C235
0x18000c345  lea     r11, qword_180047C30; jumptable 000000018000C197 case 8
0x18000c34c  lea     rax, qword_180047B70
0x18000c353  jmp     loc_18000C235
0x18000c358  lea     eax, ds:1[r10*2]; jumptable 000000018000C197 case 9
0x18000c360  imul    eax, r8d
0x18000c364  lea     r11, rva qword_18004AEC0[r14]
0x18000c36b  lea     r9, qword_180047D98
0x18000c372  movsxd  rdx, eax
0x18000c375  movsxd  rax, r8d
0x18000c378  imul    rax, 64h ; 'd'
0x18000c37c  lea     r11, [r11+rdx*4]
0x18000c380  lea     rdx, qword_180047CD0
0x18000c387  jmp     loc_18000C232
```
