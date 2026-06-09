# wil_details_FeatureDescriptors_SkipPadding

- ea: `0x140004f0c`
- end: `0x140004f2e`
- name: `wil_details_FeatureDescriptors_SkipPadding`
- size: `34`
- prototype: ``
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x14000b238`
- `0x14000b3c8`
- `0x14000b460`
- `0x14000b4dc`
- `0x14000b560`
- `0x14000d078`
- `0x14000d138`

## callees

- `0x140004f0c`

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
0x140004f0c  xchg    ax, ax
0x140004f0e  lea     rax, wil_details_featureDescriptors_a
0x140004f15  cmp     rcx, rax
0x140004f18  jnb     short loc_140004F2B
0x140004f1a  cmp     qword ptr [rcx], 0
0x140004f1e  jnz     short loc_140004F26
0x140004f20  add     rcx, 8
0x140004f24  jmp     short loc_140004F0E
0x140004f26  mov     rax, rcx
0x140004f29  retn
0x140004f2b  xor     eax, eax
0x140004f2d  retn
```
