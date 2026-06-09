# BalanceSetLatencyTarget

- ea: `0x140005614`
- end: `0x14000567d`
- name: `BalanceSetLatencyTarget`
- size: `105`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x1400027e0`
- `0x1400049b0`
- `0x140007344`

## callees

- `0x140005614`
- `0x140005684`

## pseudocode

```c
void __fastcall BalanceSetLatencyTarget(_QWORD *a1, unsigned __int64 a2)
{
  unsigned __int64 v2; // r8
  unsigned __int64 v3; // r8
  unsigned __int64 v4; // rax

  v2 = qword_14000D2D8;
  if ( a2 >= qword_14000D2D8 )
  {
    v2 = a2;
    if ( a2 > qword_14000D2D0 )
      v2 = qword_14000D2D0;
  }
  if ( v2 != a1[120] )
  {
    a1[120] = v2;
    v3 = v2 >> 1;
    if ( !v3 )
      v3 = 1;
    v4 = a1[117];
    if ( a1[121] )
      a1[121] = v3;
    if ( v4 >= v3 )
      BalanceSetLowerThreshold();
  }
}

```

## disassembly

```asm
0x140005614  sub     rsp, 28h
0x140005618  mov     r8, cs:qword_14000D2D8
0x14000561f  cmp     rdx, r8
0x140005622  jb      short loc_140005636
0x140005624  cmp     rdx, cs:qword_14000D2D0
0x14000562b  mov     r8, rdx
0x14000562e  cmova   r8, cs:qword_14000D2D0
0x140005636  cmp     r8, [rcx+3C0h]
0x14000563d  jz      short loc_140005677
0x14000563f  mov     eax, 1
0x140005644  mov     [rcx+3C0h], r8
0x14000564b  shr     r8, 1
0x14000564e  cmp     r8, rax
0x140005651  cmovb   r8, rax
0x140005655  cmp     qword ptr [rcx+3C8h], 0
0x14000565d  mov     rax, [rcx+3A8h]
0x140005664  jz      short loc_14000566D
0x140005666  mov     [rcx+3C8h], r8
0x14000566d  cmp     rax, r8
0x140005670  jb      short loc_140005677
0x140005672  call    BalanceSetLowerThreshold
0x140005677  add     rsp, 28h
0x14000567b  retn
```
