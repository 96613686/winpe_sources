# BalanceUpdateMovingAverage

- ea: `0x140002170`
- end: `0x1400021a2`
- name: `BalanceUpdateMovingAverage`
- size: `50`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `installer_update`

## callers

- `0x140001d10`

## pseudocode

```c
__int64 __fastcall BalanceUpdateMovingAverage(__int64 a1, _QWORD *a2)
{
  unsigned __int64 v2; // r9
  unsigned __int64 v3; // r8
  __int64 v4; // rcx
  __int64 result; // rax

  v2 = a2[2];
  v3 = a1 * v2;
  v4 = *a2 - a2[1];
  v3 >>= 5;
  a2[1] = *a2;
  result = v4 + v2 - v3;
  if ( v3 > v2 )
    result = v4;
  a2[2] = result;
  return result;
}

```

## disassembly

```asm
0x140002170  mov     r10, [rdx]
0x140002173  mov     r9, [rdx+10h]
0x140002177  mov     r8, r9
0x14000217a  mov     rax, r9
0x14000217d  imul    r8, rcx
0x140002181  mov     rcx, r10
0x140002184  sub     rcx, [rdx+8]
0x140002188  shr     r8, 5
0x14000218c  sub     rax, r8
0x14000218f  mov     [rdx+8], r10
0x140002193  add     rax, rcx
0x140002196  cmp     r8, r9
0x140002199  cmova   rax, rcx
0x14000219d  mov     [rdx+10h], rax
0x1400021a1  retn
```
