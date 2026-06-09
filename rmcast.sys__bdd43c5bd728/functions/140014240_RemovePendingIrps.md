# RemovePendingIrps

- ea: `0x140014240`
- end: `0x1400142df`
- name: `RemovePendingIrps`
- size: `159`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x140006998`
- `0x14000cf04`

## callees

- `0x140014240`

## pseudocode

```c
_QWORD **__fastcall RemovePendingIrps(__int64 a1, __int64 a2)
{
  __int64 v2; // rax
  _QWORD *v4; // r9
  _QWORD *v5; // rcx
  _QWORD **result; // rax
  _QWORD *v7; // rcx
  __int64 v8; // rax
  _QWORD *v9; // r8
  _QWORD *v10; // rax

  v2 = *(_QWORD *)(a1 + 48);
  v4 = *(_QWORD **)(v2 + 232);
  if ( v4 )
  {
    *(_QWORD *)(v2 + 232) = 0;
    v4[7] = *(unsigned int *)(*(_QWORD *)(a1 + 48) + 244LL);
    v5 = *(_QWORD **)(a2 + 8);
    if ( *v5 == a2 )
    {
      v4[21] = a2;
      v4[22] = v5;
      *v5 = v4 + 21;
      *(_QWORD *)(a2 + 8) = v4 + 21;
      goto LABEL_4;
    }
LABEL_9:
    __fastfail(3u);
  }
LABEL_4:
  while ( 1 )
  {
    result = (_QWORD **)(*(_QWORD *)(a1 + 48) + 200LL);
    v7 = *result;
    if ( *result == result )
      return result;
    v8 = *v7;
    if ( *(_QWORD **)(*v7 + 8LL) != v7 )
      goto LABEL_9;
    v9 = (_QWORD *)v7[1];
    if ( (_QWORD *)*v9 != v7 )
      goto LABEL_9;
    *v9 = v8;
    *(_QWORD *)(v8 + 8) = v9;
    v10 = *(_QWORD **)(a2 + 8);
    if ( *v10 != a2 )
      goto LABEL_9;
    *v7 = a2;
    v7[1] = v10;
    *v10 = v7;
    *(_QWORD *)(a2 + 8) = v7;
    *(v7 - 14) = 0;
  }
}

```

## disassembly

```asm
0x140014240  mov     rax, [rcx+30h]
0x140014244  mov     r10, rcx
0x140014247  mov     r9, [rax+0E8h]
0x14001424e  test    r9, r9
0x140014251  jz      short loc_14001428B
0x140014253  mov     qword ptr [rax+0E8h], 0
0x14001425e  mov     rax, [rcx+30h]
0x140014262  mov     r8d, [rax+0F4h]
0x140014269  mov     [r9+38h], r8
0x14001426d  mov     rcx, [rdx+8]
0x140014271  cmp     [rcx], rdx
0x140014274  jnz     short loc_1400142D7
0x140014276  lea     rax, [r9+0A8h]
0x14001427d  mov     [rax], rdx
0x140014280  mov     [rax+8], rcx
0x140014284  mov     [rcx], rax
0x140014287  mov     [rdx+8], rax
0x14001428b  mov     rax, [r10+30h]
0x14001428f  add     rax, 0C8h
0x140014295  mov     rcx, [rax]
0x140014298  cmp     rcx, rax
0x14001429b  jz      short locret_1400142DE
0x14001429d  mov     rax, [rcx]
0x1400142a0  cmp     [rax+8], rcx
0x1400142a4  jnz     short loc_1400142D7
0x1400142a6  mov     r8, [rcx+8]
0x1400142aa  cmp     [r8], rcx
0x1400142ad  jnz     short loc_1400142D7
0x1400142af  mov     [r8], rax
0x1400142b2  mov     [rax+8], r8
0x1400142b6  mov     rax, [rdx+8]
0x1400142ba  cmp     [rax], rdx
0x1400142bd  jnz     short loc_1400142D7
0x1400142bf  mov     [rcx], rdx
0x1400142c2  mov     [rcx+8], rax
0x1400142c6  mov     [rax], rcx
0x1400142c9  mov     [rdx+8], rcx
0x1400142cd  mov     qword ptr [rcx-70h], 0
0x1400142d5  jmp     short loc_14001428B
0x1400142d7  mov     ecx, 3
0x1400142dc  int     29h; Win8: RtlFailFast(ecx)
0x1400142de  retn
```
