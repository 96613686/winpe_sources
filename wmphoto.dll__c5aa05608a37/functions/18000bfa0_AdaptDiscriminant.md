# AdaptDiscriminant

- ea: `0x18000bfa0`
- end: `0x18000c28c`
- name: `AdaptDiscriminant`
- size: `748`
- prototype: ``
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x180005080`
- `0x1800093ac`
- `0x18000bee4`
- `0x18000bf18`
- `0x18000bf68`
- `0x18000c294`

## callees

- `0x18000bfa0`

## pseudocode

```c
unsigned __int64 __fastcall AdaptDiscriminant(int *a1)
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
  char *v11; // r9
  __int64 v12; // rax
  char *v13; // r11
  const wchar_t *v14; // rdx
  unsigned __int64 result; // rax

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
    v5 = *(_DWORD *)((char *)&unk_180049DE0 + v3);
    v4 = 0;
    a1[14] = v5;
    *((_QWORD *)a1 + 9) = 1;
    a1[20] = 0;
  }
  v6 = v4;
  v7 = a1[19];
  if ( !*(_DWORD *)((char *)&unk_180049DE0 + v3) )
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
  v8 = *(_DWORD *)((char *)&unk_180049E98 + v3);
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
    v13 = (char *)&unk_18004A090 + 52 * v5;
    *((_QWORD *)a1 + 6) = (char *)&unk_18004A160 + 24 * (v5 - (v5 + 1 == v8));
    v12 = 44LL * v5;
    v11 = (char *)&unk_18004A160 + 24 * (v5 - (v5 != 0));
    v14 = (const wchar_t *)&unk_1800464B0;
LABEL_21:
    result = (unsigned __int64)&v14[v12];
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
        v13 = (char *)&unk_180046B40;
        result = (unsigned __int64)&unk_180046AF0;
        goto LABEL_22;
      case 5:
        v11 = (char *)&unk_180046AD8;
        v12 = 42LL * v5;
        v13 = (char *)&unk_180049F70 + 4 * v5 * (2 * (int)v1 + 1);
        v14 = (const wchar_t *)&unk_180046A30;
        goto LABEL_21;
      case 7:
        v11 = (char *)&unk_1800466C8;
        v12 = 46LL * v5;
        v13 = (char *)&unk_180049E20 + 4 * v5 * (2 * (int)v1 + 1);
        v14 = a5;
        goto LABEL_21;
      case 8:
        v13 = (char *)&unk_180046C30;
        result = (unsigned __int64)&unk_180046B70;
        goto LABEL_22;
      case 9:
        v11 = (char *)&unk_180046D98;
        v12 = 50LL * v5;
        v13 = (char *)&unk_180049ED0 + 4 * v5 * (2 * (int)v1 + 1);
        v14 = (const wchar_t *)&unk_180046CD0;
        goto LABEL_21;
      case 12:
        v13 = (char *)&unk_18004A1B0 + 4 * v5 * (2 * (int)v1 + 1);
        *((_QWORD *)a1 + 6) = &_ImageBase[2 * (int)(v1 * (v5 - (v5 + 1 == v8))) + 151528];
        v14 = (const wchar_t *)&unk_1800466F0;
        v11 = (char *)&unk_180049FD0 + 4 * (int)(v1 * (v5 - (v5 != 0)));
        v12 = 56LL * v5;
        goto LABEL_21;
      default:
        result = (unsigned int)(v1 - 4);
        break;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000bfa0  push    rbx
0x18000bfa2  push    rsi
0x18000bfa3  push    rdi
0x18000bfa4  push    r14
0x18000bfa6  cmp     dword ptr [rcx+48h], 0
0x18000bfaa  lea     r14, __ImageBase
0x18000bfb1  movsxd  r10, dword ptr [rcx]
0x18000bfb4  mov     esi, 1
0x18000bfb9  lea     rdx, ds:0[r10*4]
0x18000bfc1  jz      loc_18000C123
0x18000bfc7  mov     edi, [rcx+50h]
0x18000bfca  mov     r8d, [rcx+38h]
0x18000bfce  cmp     dword ptr [rdx+r14+49DE0h], 0
0x18000bfd7  mov     ebx, edi
0x18000bfd9  mov     eax, [rcx+4Ch]
0x18000bfdc  cmovz   ebx, eax
0x18000bfdf  cmp     eax, [rcx+58h]
0x18000bfe2  jl      short loc_18000C00B
0x18000bfe4  cmp     ebx, [rcx+54h]
0x18000bfe7  jg      short loc_18000C010
0x18000bfe9  cmp     eax, 0FFFFFFC0h
0x18000bfec  jge     loc_18000C1F8
0x18000bff2  mov     dword ptr [rcx+4Ch], 0FFFFFFC0h
0x18000bff9  cmp     edi, 0FFFFFFC0h
0x18000bffc  jge     loc_18000C141
0x18000c002  mov     dword ptr [rcx+50h], 0FFFFFFC0h
0x18000c009  jmp     short loc_18000C01F
0x18000c00b  mov     esi, 0FFFFFFFFh
0x18000c010  add     r8d, esi
0x18000c013  mov     [rcx+38h], r8d
0x18000c017  mov     qword ptr [rcx+4Ch], 0
0x18000c01f  mov     ebx, [rdx+r14+49E98h]
0x18000c027  test    r8d, r8d
0x18000c02a  mov     r9d, 0FFFFFFF8h
0x18000c030  mov     eax, 80000000h
0x18000c035  cmovnz  eax, r9d
0x18000c039  mov     edx, 40000000h
0x18000c03e  mov     [rcx+58h], eax
0x18000c041  mov     r9d, 8
0x18000c047  lea     eax, [rbx-1]
0x18000c04a  cmp     r8d, eax
0x18000c04d  cmovnz  edx, r9d
0x18000c051  mov     [rcx+54h], edx
0x18000c054  cmp     r10d, 6
0x18000c058  jz      short loc_18000C0AA
0x18000c05a  lea     eax, [r10-4]; switch 9 cases
0x18000c05e  cmp     eax, r9d
0x18000c061  ja      def_18000C077; jumptable 000000018000C077 default case, cases 6,10,11
0x18000c067  cdqe
0x18000c069  xor     r9d, r9d
0x18000c06c  mov     edx, ds:(jpt_18000C077 - 180000000h)[r14+rax*4]
0x18000c074  add     rdx, r14
0x18000c077  jmp     rdx; switch jump
0x18000c079  lea     eax, ds:1[r10*2]; jumptable 000000018000C077 case 7
0x18000c081  imul    eax, r8d
0x18000c085  lea     r11, rva unk_180049E20[r14]
0x18000c08c  lea     r9, unk_1800466C8
0x18000c093  movsxd  rdx, eax
0x18000c096  movsxd  rax, r8d
0x18000c099  imul    rax, 5Ch ; '\'
0x18000c09d  lea     r11, [r11+rdx*4]
0x18000c0a1  lea     rdx, a5; "-5$$\x1B\x1B\x1B\x1B"
0x18000c0a8  jmp     short loc_18000C10E
0x18000c0aa  imul    eax, r8d, 0Dh
0x18000c0ae  lea     r11, rva unk_18004A090[r14]
0x18000c0b5  lea     r9, rva unk_18004A160[r14]
0x18000c0bc  movsxd  rdx, eax
0x18000c0bf  lea     eax, [r8+1]
0x18000c0c3  lea     r11, [r11+rdx*4]
0x18000c0c7  xor     edx, edx
0x18000c0c9  cmp     eax, ebx
0x18000c0cb  mov     eax, r8d
0x18000c0ce  setz    dl
0x18000c0d1  sub     eax, edx
0x18000c0d3  lea     eax, [rax+rax*2]
0x18000c0d6  add     eax, eax
0x18000c0d8  movsxd  rdx, eax
0x18000c0db  lea     rax, rva unk_18004A160[r14]
0x18000c0e2  lea     rax, [rax+rdx*4]
0x18000c0e6  mov     [rcx+30h], rax
0x18000c0ea  mov     eax, r8d
0x18000c0ed  neg     eax
0x18000c0ef  sbb     edx, edx
0x18000c0f1  add     edx, r8d
0x18000c0f4  lea     eax, [rdx+rdx*2]
0x18000c0f7  add     eax, eax
0x18000c0f9  movsxd  rdx, eax
0x18000c0fc  movsxd  rax, r8d
0x18000c0ff  imul    rax, 58h ; 'X'
0x18000c103  lea     r9, [r9+rdx*4]
0x18000c107  lea     rdx, unk_1800464B0
0x18000c10e  add     rax, rdx
0x18000c111  mov     [rcx+40h], rax
0x18000c115  mov     [rcx+20h], r11
0x18000c119  mov     [rcx+28h], r9
0x18000c11d  pop     r14; jumptable 000000018000C077 default case, cases 6,10,11
0x18000c11f  pop     rdi
0x18000c120  pop     rsi
0x18000c121  pop     rbx
0x18000c122  retn
0x18000c123  mov     r8d, [rdx+r14+49DE0h]
0x18000c12b  xor     edi, edi
0x18000c12d  mov     [rcx+38h], r8d
0x18000c131  mov     [rcx+48h], rsi
0x18000c135  mov     dword ptr [rcx+50h], 0
0x18000c13c  jmp     loc_18000BFCE
0x18000c141  cmp     edi, 40h ; '@'
0x18000c144  jle     loc_18000C01F
0x18000c14a  mov     dword ptr [rcx+50h], 40h ; '@'
0x18000c151  jmp     loc_18000C01F
0x18000c156  lea     eax, ds:1[r10*2]; jumptable 000000018000C077 case 12
0x18000c15e  imul    eax, r8d
0x18000c162  lea     r11, rva unk_18004A1B0[r14]
0x18000c169  lea     r9, rva unk_180049FD0[r14]
0x18000c170  movsxd  rdx, eax
0x18000c173  lea     eax, [r8+1]
0x18000c177  lea     r11, [r11+rdx*4]
0x18000c17b  xor     edx, edx
0x18000c17d  cmp     eax, ebx
0x18000c17f  mov     eax, r8d
0x18000c182  setz    dl
0x18000c185  sub     eax, edx
0x18000c187  imul    eax, r10d
0x18000c18b  cdqe
0x18000c18d  lea     rax, ds:49FD0h[rax*4]
0x18000c195  add     rax, r14
0x18000c198  mov     [rcx+30h], rax
0x18000c19c  mov     eax, r8d
0x18000c19f  neg     eax
0x18000c1a1  sbb     edx, edx
0x18000c1a3  lea     eax, [r8+rdx]
0x18000c1a7  imul    eax, r10d
0x18000c1ab  lea     rdx, unk_1800466F0
0x18000c1b2  cdqe
0x18000c1b4  lea     r9, [r9+rax*4]
0x18000c1b8  movsxd  rax, r8d
0x18000c1bb  imul    rax, 70h ; 'p'
0x18000c1bf  jmp     loc_18000C10E
0x18000c1c4  lea     eax, ds:1[r10*2]; jumptable 000000018000C077 case 5
0x18000c1cc  imul    eax, r8d
0x18000c1d0  lea     r11, rva unk_180049F70[r14]
0x18000c1d7  lea     r9, unk_180046AD8
0x18000c1de  movsxd  rdx, eax
0x18000c1e1  movsxd  rax, r8d
0x18000c1e4  imul    rax, 54h ; 'T'
0x18000c1e8  lea     r11, [r11+rdx*4]
0x18000c1ec  lea     rdx, unk_180046A30
0x18000c1f3  jmp     loc_18000C10E
0x18000c1f8  cmp     eax, 40h ; '@'
0x18000c1fb  jle     loc_18000BFF9
0x18000c201  mov     dword ptr [rcx+4Ch], 40h ; '@'
0x18000c208  jmp     loc_18000BFF9
0x18000c20d  lea     r11, unk_180046B40; jumptable 000000018000C077 case 4
0x18000c214  lea     rax, unk_180046AF0
0x18000c21b  jmp     loc_18000C111
0x18000c220  lea     r11, unk_180046C30; jumptable 000000018000C077 case 8
0x18000c227  lea     rax, unk_180046B70
0x18000c22e  jmp     loc_18000C111
0x18000c233  lea     eax, ds:1[r10*2]; jumptable 000000018000C077 case 9
0x18000c23b  imul    eax, r8d
0x18000c23f  lea     r11, rva unk_180049ED0[r14]
0x18000c246  lea     r9, unk_180046D98
0x18000c24d  movsxd  rdx, eax
0x18000c250  movsxd  rax, r8d
0x18000c253  imul    rax, 64h ; 'd'
0x18000c257  lea     r11, [r11+rdx*4]
0x18000c25b  lea     rdx, unk_180046CD0
0x18000c262  jmp     loc_18000C10E
```
