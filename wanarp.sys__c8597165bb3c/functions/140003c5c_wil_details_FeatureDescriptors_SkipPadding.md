# wil_details_FeatureDescriptors_SkipPadding

- ea: `0x140003c5c`
- end: `0x140003c7e`
- name: `wil_details_FeatureDescriptors_SkipPadding`
- size: `34`
- prototype: ``
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x140017bb0`
- `0x140017d40`
- `0x140017de0`
- `0x140017e5c`
- `0x140017ee0`
- `0x14001a85c`
- `0x14001a91c`

## callees

- `0x140003c5c`

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
0x140003c5c  xchg    ax, ax
0x140003c5e  lea     rax, wil_details_featureDescriptors_a
0x140003c65  cmp     rcx, rax
0x140003c68  jnb     short loc_140003C7B
0x140003c6a  cmp     qword ptr [rcx], 0
0x140003c6e  jnz     short loc_140003C76
0x140003c70  add     rcx, 8
0x140003c74  jmp     short loc_140003C5E
0x140003c76  mov     rax, rcx
0x140003c79  retn
0x140003c7b  xor     eax, eax
0x140003c7d  retn
```
