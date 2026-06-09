# _RINvNtNtNtNtCs9MWeMO1rkJG_4core5slice4sort6shared9smallsort25insertion_sort_shift_leftRNtNtCscTDbrdTM4KX_15onecore_windows6windef6__RECTLNCINvMB8_SB1m_20sort_unstable_by_keylNCNvMs_CsdcpJtfrLhSH_7rgncoreNtB2T_10RegionCore16subtract_complex0E0EB2T_

- ea: `0x140016510`
- end: `0x140016584`
- name: `_RINvNtNtNtNtCs9MWeMO1rkJG_4core5slice4sort6shared9smallsort25insertion_sort_shift_leftRNtNtCscTDbrdTM4KX_15onecore_windows6windef6__RECTLNCINvMB8_SB1m_20sort_unstable_by_keylNCNvMs_CsdcpJtfrLhSH_7rgncoreNtB2T_10RegionCore16subtract_complex0E0EB2T_`
- size: `116`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14000cc10`

## callees

- `0x140016510`

## pseudocode

```c
_QWORD *__fastcall RINvNtNtNtNtCs9MWeMO1rkJG_4core5slice4sort6shared9smallsort25insertion_sort_shift_leftRNtNtCscTDbrdTM4KX_15onecore_windows6windef6__RECTLNCINvMB8_SB1m_20sort_unstable_by_keylNCNvMs_CsdcpJtfrLhSH_7rgncoreNtB2T_10RegionCore16subtract_complex0E0EB2T_(
        _QWORD *a1,
        unsigned __int64 a2,
        __int64 a3)
{
  _QWORD *result; // rax
  _QWORD *v4; // rdx
  __int64 v5; // r8
  _QWORD *v6; // r10
  __int64 v7; // r11
  __int64 v8; // r9
  __int64 v9; // r10

  result = (_QWORD *)(a3 - 1);
  if ( a3 - 1 >= a2 )
    BUG();
  if ( a3 != a2 )
  {
    result = &a1[a2];
    v4 = &a1[a3];
    v5 = 8 * a3;
    do
    {
      v7 = *(v4 - 1);
      v8 = *v4;
      if ( *(_DWORD *)(*v4 + 4LL) < *(_DWORD *)(v7 + 4) )
      {
        v9 = v5;
        do
        {
          *(_QWORD *)((char *)a1 + v9) = v7;
          if ( v9 == 8 )
          {
            v6 = a1;
            goto LABEL_6;
          }
          v7 = *(_QWORD *)((char *)a1 + v9 - 16);
          v9 -= 8;
        }
        while ( *(_DWORD *)(v8 + 4) < *(_DWORD *)(v7 + 4) );
        v6 = (_QWORD *)((char *)a1 + v9);
LABEL_6:
        *v6 = v8;
      }
      ++v4;
      v5 += 8;
    }
    while ( v4 != result );
  }
  return result;
}

```

## disassembly

```asm
0x140016510  push    rsi
0x140016511  lea     rax, [r8-1]
0x140016515  cmp     rax, rdx
0x140016518  jnb     short loc_140016582
0x14001651a  cmp     r8, rdx
0x14001651d  jnz     short loc_140016521
0x14001651f  pop     rsi
0x140016520  retn
0x140016521  lea     rax, [rcx+rdx*8]
0x140016525  lea     rdx, [rcx+r8*8]
0x140016529  shl     r8, 3
0x14001652d  jmp     short loc_140016543
0x140016530  mov     r10, rcx
0x140016533  mov     [r10], r9
0x140016536  add     rdx, 8
0x14001653a  add     r8, 8
0x14001653e  cmp     rdx, rax
0x140016541  jz      short loc_14001651F
0x140016543  mov     r11, [rdx-8]
0x140016547  mov     r9, [rdx]
0x14001654a  mov     r10d, [r9+4]
0x14001654e  cmp     r10d, [r11+4]
0x140016552  jge     short loc_140016536
0x140016554  mov     r10, r8
0x140016557  nop     word ptr [rax+rax+00000000h]
0x140016560  mov     [rcx+r10], r11
0x140016564  cmp     r10, 8
0x140016568  jz      short loc_140016530
0x14001656a  mov     r11, [rcx+r10-10h]
0x14001656f  mov     esi, [r9+4]
0x140016573  add     r10, 0FFFFFFFFFFFFFFF8h
0x140016577  cmp     esi, [r11+4]
0x14001657b  jl      short loc_140016560
0x14001657d  add     r10, rcx
0x140016580  jmp     short loc_140016533
0x140016582  ud2
```
