# BalanceSetLowerThreshold

- ea: `0x140005684`
- end: `0x1400056d6`
- name: `BalanceSetLowerThreshold`
- size: `82`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x1400027e0`
- `0x140005158`
- `0x140005614`

## callees

- `0x140005684`

## pseudocode

```c
unsigned __int64 __fastcall BalanceSetLowerThreshold(_QWORD *a1)
{
  unsigned __int64 v1; // rdx
  unsigned __int64 result; // rax
  unsigned __int64 v3; // rdx

  v1 = 100LL * a1[117];
  a1[121] = 0;
  result = a1[120];
  v3 = v1 / 0x78;
  a1[124] = v3;
  if ( v3 <= result )
  {
    if ( !v3 )
      a1[124] = 1;
  }
  else
  {
    a1[124] = result;
  }
  return result;
}

```

## disassembly

```asm
0x140005684  imul    rdx, [rcx+3A8h], 64h ; 'd'
0x14000568c  mov     rax, 8888888888888889h
0x140005696  mov     qword ptr [rcx+3C8h], 0
0x1400056a1  mul     rdx
0x1400056a4  mov     rax, [rcx+3C0h]
0x1400056ab  shr     rdx, 6
0x1400056af  mov     [rcx+3E0h], rdx
0x1400056b6  cmp     rdx, rax
0x1400056b9  jbe     short loc_1400056C4
0x1400056bb  mov     [rcx+3E0h], rax
0x1400056c2  retn
0x1400056c4  cmp     rdx, 1
0x1400056c8  jnb     short locret_1400056D5
0x1400056ca  mov     qword ptr [rcx+3E0h], 1
0x1400056d5  retn
```
