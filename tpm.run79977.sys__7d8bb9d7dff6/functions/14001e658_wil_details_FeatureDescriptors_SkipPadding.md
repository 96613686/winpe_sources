# wil_details_FeatureDescriptors_SkipPadding

- ea: `0x14001e658`
- end: `0x14001e67a`
- name: `wil_details_FeatureDescriptors_SkipPadding`
- size: `34`
- prototype: ``
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x14004e770`
- `0x14004e980`
- `0x14004ea0c`
- `0x14004ea90`
- `0x140050170`
- `0x140050230`

## callees

- `0x14001e658`

## pseudocode

```c
__int64 *__fastcall wil_details_FeatureDescriptors_SkipPadding(__int64 *a1)
{
  while ( a1 < wil_details_featureDescriptors_z )
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
0x14001e658  xchg    ax, ax
0x14001e65a  lea     rax, wil_details_featureDescriptors_z
0x14001e661  cmp     rcx, rax
0x14001e664  jnb     short loc_14001E677
0x14001e666  cmp     qword ptr [rcx], 0
0x14001e66a  jnz     short loc_14001E672
0x14001e66c  add     rcx, 8
0x14001e670  jmp     short loc_14001E65A
0x14001e672  mov     rax, rcx
0x14001e675  retn
0x14001e677  xor     eax, eax
0x14001e679  retn
```
