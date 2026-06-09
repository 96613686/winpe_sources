# SqospLimiterReplenishQuota

- ea: `0x140007094`
- end: `0x14000722f`
- name: `SqospLimiterReplenishQuota`
- size: `411`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x140006e98`
- `0x140007238`

## callees

- `0x140006e6c`
- `0x140007094`

## pseudocode

```c
void __fastcall SqospLimiterReplenishQuota(_QWORD *a1, unsigned __int64 a2)
{
  _QWORD *v3; // r11
  __int64 v4; // rcx
  __int64 v5; // r8
  __int64 v6; // rbx
  unsigned __int64 v7; // rcx
  unsigned __int64 v8; // r9
  __int64 v9; // rax
  _QWORD *v10; // r11
  unsigned __int64 v11; // rdi
  __int64 v12; // rax
  __int64 v13; // rax

  v3 = a1;
  if ( a2 < a1[62] )
    return;
  ++a1[68];
  a1[62] = a2 + qword_14000D328;
  v4 = a2 - a1[61];
  v5 = v3[57];
  v6 = v3[58];
  if ( v4 > qword_14000D330 )
    v4 = qword_14000D330;
  v7 = v4 << 16;
  v8 = v5 * (v7 / qword_14000D330);
  if ( !v5 )
    goto LABEL_8;
  if ( !v6 )
  {
    if ( v8 )
    {
      v9 = SqospInterlockedAdd64UpToMaximum(v3 + 63, v8, (v5 << 16) / 5uLL);
      v10[66] += v9;
      v10[67] = v10[66] >> 16;
LABEL_16:
      v10[61] = a2;
      return;
    }
LABEL_8:
    if ( !v6 )
      return;
  }
  v11 = v6 * (v7 / qword_14000D330);
  if ( !v5 )
  {
    if ( !v11 )
      return;
    goto LABEL_15;
  }
  if ( v8 && v11 )
  {
    v12 = SqospInterlockedAdd64UpToMaximum(v3 + 63, v8, (v5 << 16) / 5uLL);
    v3[66] += v12;
    v3[67] = v3[66] >> 16;
LABEL_15:
    v13 = SqospInterlockedAdd64UpToMaximum(v3 + 64, v11, (v6 << 16) / 5uLL);
    v10[69] += v13;
    v10[70] = v10[69] >> 16;
    goto LABEL_16;
  }
}

```

## disassembly

```asm
0x140007094  push    rbx
0x140007096  push    rbp
0x140007097  push    rsi
0x140007098  push    rdi
0x140007099  sub     rsp, 28h
0x14000709d  mov     rsi, rdx
0x1400070a0  mov     r11, rcx
0x1400070a3  cmp     rdx, [rcx+1F0h]
0x1400070aa  jb      loc_140007225
0x1400070b0  inc     qword ptr [rcx+220h]
0x1400070b7  mov     r8, cs:qword_14000D328
0x1400070be  add     r8, rdx
0x1400070c1  mov     [rcx+1F0h], r8
0x1400070c8  mov     rcx, rdx
0x1400070cb  sub     rcx, [r11+1E8h]
0x1400070d2  mov     r8, [r11+1C8h]
0x1400070d9  cmp     rcx, cs:qword_14000D330
0x1400070e0  mov     rbx, [r11+1D0h]
0x1400070e7  cmovg   rcx, cs:qword_14000D330
0x1400070ef  xor     edx, edx
0x1400070f1  shl     rcx, 10h
0x1400070f5  mov     rax, rcx
0x1400070f8  div     cs:qword_14000D330
0x1400070ff  mov     r9, rax
0x140007102  imul    r9, r8
0x140007106  test    r8, r8
0x140007109  jz      short loc_14000715A
0x14000710b  test    rbx, rbx
0x14000710e  jnz     short loc_140007163
0x140007110  test    r9, r9
0x140007113  jz      short loc_14000715A
0x140007115  shl     r8, 10h
0x140007119  lea     rcx, [r11+1F8h]
0x140007120  mov     rax, 0CCCCCCCCCCCCCCCDh
0x14000712a  mul     r8
0x14000712d  shr     rdx, 2
0x140007131  mov     r8, rdx
0x140007134  mov     rdx, r9
0x140007137  call    SqospInterlockedAdd64UpToMaximum
0x14000713c  add     [r11+210h], rax
0x140007143  mov     rax, [r11+210h]
0x14000714a  shr     rax, 10h
0x14000714e  mov     [r11+218h], rax
0x140007155  jmp     loc_14000721E
0x14000715a  test    rbx, rbx
0x14000715d  jz      loc_140007225
0x140007163  xor     edx, edx
0x140007165  mov     rax, rcx
0x140007168  div     cs:qword_14000D330
0x14000716f  mov     rdi, rax
0x140007172  imul    rdi, rbx
0x140007176  test    r8, r8
0x140007179  jnz     short loc_140007190
0x14000717b  test    rdi, rdi
0x14000717e  jz      loc_140007225
0x140007184  mov     rax, 0CCCCCCCCCCCCCCCDh
0x14000718e  jmp     short loc_1400071E8
0x140007190  test    r9, r9
0x140007193  jz      loc_140007225
0x140007199  test    rdi, rdi
0x14000719c  jz      loc_140007225
0x1400071a2  shl     r8, 10h
0x1400071a6  lea     rcx, [r11+1F8h]
0x1400071ad  mov     rbp, 0CCCCCCCCCCCCCCCDh
0x1400071b7  mov     rax, rbp
0x1400071ba  mul     r8
0x1400071bd  shr     rdx, 2
0x1400071c1  mov     r8, rdx
0x1400071c4  mov     rdx, r9
0x1400071c7  call    SqospInterlockedAdd64UpToMaximum
0x1400071cc  add     [r11+210h], rax
0x1400071d3  mov     rax, [r11+210h]
0x1400071da  shr     rax, 10h
0x1400071de  mov     [r11+218h], rax
0x1400071e5  mov     rax, rbp
0x1400071e8  shl     rbx, 10h
0x1400071ec  lea     rcx, [r11+200h]
0x1400071f3  mul     rbx
0x1400071f6  shr     rdx, 2
0x1400071fa  mov     r8, rdx
0x1400071fd  mov     rdx, rdi
0x140007200  call    SqospInterlockedAdd64UpToMaximum
0x140007205  add     [r11+228h], rax
0x14000720c  mov     rax, [r11+228h]
0x140007213  shr     rax, 10h
0x140007217  mov     [r11+230h], rax
0x14000721e  mov     [r11+1E8h], rsi
0x140007225  add     rsp, 28h
0x140007229  pop     rdi
0x14000722a  pop     rsi
0x14000722b  pop     rbp
0x14000722c  pop     rbx
0x14000722d  retn
```
