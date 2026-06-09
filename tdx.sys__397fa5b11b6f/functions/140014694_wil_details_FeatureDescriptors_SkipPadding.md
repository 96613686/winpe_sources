# wil_details_FeatureDescriptors_SkipPadding

- ea: `0x140014694`
- end: `0x1400146b6`
- name: `wil_details_FeatureDescriptors_SkipPadding`
- size: `34`
- prototype: ``
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x1400230c8`
- `0x140023258`
- `0x1400232f0`
- `0x14002336c`
- `0x1400233f0`
- `0x140024078`
- `0x140024138`

## callees

- `0x140014694`

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
0x140014694  xchg    ax, ax
0x140014696  lea     rax, wil_details_featureDescriptors_a
0x14001469d  cmp     rcx, rax
0x1400146a0  jnb     short loc_1400146B3
0x1400146a2  cmp     qword ptr [rcx], 0
0x1400146a6  jnz     short loc_1400146AE
0x1400146a8  add     rcx, 8
0x1400146ac  jmp     short loc_140014696
0x1400146ae  mov     rax, rcx
0x1400146b1  retn
0x1400146b3  xor     eax, eax
0x1400146b5  retn
```
