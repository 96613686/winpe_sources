# wil_details_FeatureDescriptors_SkipPadding

- ea: `0x140010464`
- end: `0x140010486`
- name: `wil_details_FeatureDescriptors_SkipPadding`
- size: `34`
- prototype: ``
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x14001dc5c`
- `0x14001ddec`
- `0x14001de80`
- `0x14001defc`
- `0x14001df80`
- `0x1400202b8`
- `0x140020378`

## callees

- `0x140010464`

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
0x140010464  xchg    ax, ax
0x140010466  lea     rax, wil_details_featureDescriptors_a
0x14001046d  cmp     rcx, rax
0x140010470  jnb     short loc_140010483
0x140010472  cmp     qword ptr [rcx], 0
0x140010476  jnz     short loc_14001047E
0x140010478  add     rcx, 8
0x14001047c  jmp     short loc_140010466
0x14001047e  mov     rax, rcx
0x140010481  retn
0x140010483  xor     eax, eax
0x140010485  retn
```
