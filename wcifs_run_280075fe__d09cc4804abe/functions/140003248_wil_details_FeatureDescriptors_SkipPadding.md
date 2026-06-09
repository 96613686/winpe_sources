# wil_details_FeatureDescriptors_SkipPadding

- ea: `0x140003248`
- end: `0x14000326a`
- name: `wil_details_FeatureDescriptors_SkipPadding`
- size: `34`
- prototype: ``
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x14002254c`
- `0x140022684`
- `0x140022720`
- `0x14002279c`
- `0x140022820`
- `0x1400360b0`
- `0x140036170`

## callees

- `0x140003248`

## pseudocode

```c
__int64 *__fastcall wil_details_FeatureDescriptors_SkipPadding(__int64 *a1)
{
  while ( a1 < wil_details_featureDescriptors_a )
  {
    if ( *a1 )
      return a1;
    ++a1;
  }
  return 0;
}

```

## disassembly

```asm
0x140003248  xchg    ax, ax
0x14000324a  lea     rax, wil_details_featureDescriptors_a
0x140003251  cmp     rcx, rax
0x140003254  jnb     short loc_140003267
0x140003256  cmp     qword ptr [rcx], 0
0x14000325a  jnz     short loc_140003262
0x14000325c  add     rcx, 8
0x140003260  jmp     short loc_14000324A
0x140003262  mov     rax, rcx
0x140003265  retn
0x140003267  xor     eax, eax
0x140003269  retn
```
