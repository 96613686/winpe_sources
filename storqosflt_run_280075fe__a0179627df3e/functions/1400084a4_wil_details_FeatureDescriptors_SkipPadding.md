# wil_details_FeatureDescriptors_SkipPadding

- ea: `0x1400084a4`
- end: `0x1400084c6`
- name: `wil_details_FeatureDescriptors_SkipPadding`
- size: `34`
- prototype: ``
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x14001396c`
- `0x140013aa4`
- `0x140013b40`
- `0x140013bbc`
- `0x140013c40`
- `0x140016920`
- `0x1400169e0`

## callees

- `0x1400084a4`

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
0x1400084a4  xchg    ax, ax
0x1400084a6  lea     rax, wil_details_featureDescriptors_a
0x1400084ad  cmp     rcx, rax
0x1400084b0  jnb     short loc_1400084C3
0x1400084b2  cmp     qword ptr [rcx], 0
0x1400084b6  jnz     short loc_1400084BE
0x1400084b8  add     rcx, 8
0x1400084bc  jmp     short loc_1400084A6
0x1400084be  mov     rax, rcx
0x1400084c1  retn
0x1400084c3  xor     eax, eax
0x1400084c5  retn
```
