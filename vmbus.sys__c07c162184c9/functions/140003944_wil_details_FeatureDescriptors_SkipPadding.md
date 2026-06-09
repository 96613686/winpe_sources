# wil_details_FeatureDescriptors_SkipPadding

- ea: `0x140003944`
- end: `0x140003966`
- name: `wil_details_FeatureDescriptors_SkipPadding`
- size: `34`
- prototype: ``
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x14002794c`
- `0x140027adc`
- `0x140027b70`
- `0x140027bec`
- `0x140027c70`
- `0x140030260`
- `0x140030320`

## callees

- `0x140003944`

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
0x140003944  xchg    ax, ax
0x140003946  lea     rax, wil_details_featureDescriptors_a
0x14000394d  cmp     rcx, rax
0x140003950  jnb     short loc_140003963
0x140003952  cmp     qword ptr [rcx], 0
0x140003956  jnz     short loc_14000395E
0x140003958  add     rcx, 8
0x14000395c  jmp     short loc_140003946
0x14000395e  mov     rax, rcx
0x140003961  retn
0x140003963  xor     eax, eax
0x140003965  retn
```
