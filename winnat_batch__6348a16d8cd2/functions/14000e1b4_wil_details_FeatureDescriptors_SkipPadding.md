# wil_details_FeatureDescriptors_SkipPadding

- ea: `0x14000e1b4`
- end: `0x14000e1d4`
- name: `wil_details_FeatureDescriptors_SkipPadding`
- size: `32`
- prototype: ``
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x14002ef70`
- `0x14002f0a8`
- `0x14002f140`
- `0x14002f1bc`
- `0x14002f240`
- `0x1400353d4`
- `0x140035494`

## callees

- `0x14000e1b4`

## pseudocode

```c
__int64 *__fastcall wil_details_FeatureDescriptors_SkipPadding(__int64 *a1)
{
  while ( 1 )
  {
    if ( a1 >= wil_details_featureDescriptors_z )
      return 0;
    if ( *a1 )
      break;
    ++a1;
  }
  return a1;
}

```

## disassembly

```asm
0x14000e1b4  lea     rax, wil_details_featureDescriptors_z
0x14000e1bb  jmp     short loc_14000E1C7
0x14000e1bd  cmp     qword ptr [rcx], 0
0x14000e1c1  jnz     short loc_14000E1D0
0x14000e1c3  add     rcx, 8
0x14000e1c7  cmp     rcx, rax
0x14000e1ca  jb      short loc_14000E1BD
0x14000e1cc  xor     eax, eax
0x14000e1ce  retn
0x14000e1d0  mov     rax, rcx
0x14000e1d3  retn
```
