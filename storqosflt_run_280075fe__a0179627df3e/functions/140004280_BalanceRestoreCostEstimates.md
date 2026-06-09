# BalanceRestoreCostEstimates

- ea: `0x140004280`
- end: `0x140004333`
- name: `BalanceRestoreCostEstimates`
- size: `179`
- prototype: ``
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x1400049b0`
- `0x1400056e0`
- `0x140007344`

## pseudocode

```c
unsigned __int64 __fastcall BalanceRestoreCostEstimates(__int64 a1)
{
  __int64 v2; // rax
  __int64 v3; // rax
  unsigned __int64 v4; // rcx
  unsigned __int64 result; // rax

  *(_QWORD *)(a1 + 1120) = *(_QWORD *)(a1 + 1296) / 0x2000LL;
  *(_QWORD *)(a1 + 1128) = *(_QWORD *)(a1 + 1304) / 0x2000LL;
  *(_QWORD *)(a1 + 1136) = *(_QWORD *)(a1 + 1312) / 0x2000LL;
  v2 = *(_QWORD *)(a1 + 1320) / 0x2000LL;
  *(_QWORD *)(a1 + 1144) = v2;
  *(_QWORD *)(a1 + 1016) = v2;
  v3 = *(_QWORD *)(a1 + 1016);
  v4 = (unsigned int)dword_14000D2C8;
  *(_DWORD *)(a1 + 1100) = 0;
  result = 100 * v3 / v4;
  if ( !result )
    result = 1;
  *(_QWORD *)(a1 + 1000) = result;
  return result;
}

```

## disassembly

```asm
0x140004280  mov     rax, [rcx+510h]
0x140004287  mov     r8, rcx
0x14000428a  cqo
0x14000428c  and     edx, 1FFFh
0x140004292  add     rax, rdx
0x140004295  sar     rax, 0Dh
0x140004299  mov     [rcx+460h], rax
0x1400042a0  mov     rax, [rcx+518h]
0x1400042a7  cqo
0x1400042a9  and     edx, 1FFFh
0x1400042af  add     rax, rdx
0x1400042b2  sar     rax, 0Dh
0x1400042b6  mov     [rcx+468h], rax
0x1400042bd  mov     rax, [rcx+520h]
0x1400042c4  cqo
0x1400042c6  and     edx, 1FFFh
0x1400042cc  add     rax, rdx
0x1400042cf  sar     rax, 0Dh
0x1400042d3  mov     [rcx+470h], rax
0x1400042da  mov     rax, [rcx+528h]
0x1400042e1  cqo
0x1400042e3  and     edx, 1FFFh
0x1400042e9  add     rax, rdx
0x1400042ec  xor     edx, edx
0x1400042ee  sar     rax, 0Dh
0x1400042f2  mov     [rcx+478h], rax
0x1400042f9  mov     [rcx+3F8h], rax
0x140004300  mov     rax, [rcx+3F8h]
0x140004307  mov     ecx, cs:dword_14000D2C8
0x14000430d  imul    rax, 64h ; 'd'
0x140004311  mov     dword ptr [r8+44Ch], 0
0x14000431c  div     rcx
0x14000431f  mov     ecx, 1
0x140004324  test    rax, rax
0x140004327  cmovz   rax, rcx
0x14000432b  mov     [r8+3E8h], rax
0x140004332  retn
```
