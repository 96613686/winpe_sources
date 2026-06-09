# wil_details_FeatureDescriptors_SkipPadding

- ea: `0x14000ef2c`
- end: `0x14000ef4e`
- name: `wil_details_FeatureDescriptors_SkipPadding`
- size: `34`
- prototype: ``
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x140022ce0`
- `0x140022d5c`
- `0x140022de0`
- `0x14002dd58`
- `0x14002dd98`
- `0x14002f268`
- `0x14002f328`

## callees

- `0x14000ef2c`

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
0x14000ef2c  xchg    ax, ax
0x14000ef2e  lea     rax, wil_details_featureDescriptors_z
0x14000ef35  cmp     rcx, rax
0x14000ef38  jb      short loc_14000EF3E
0x14000ef3a  xor     eax, eax
0x14000ef3c  retn
0x14000ef3e  cmp     qword ptr [rcx], 0
0x14000ef42  jnz     short loc_14000EF4A
0x14000ef44  add     rcx, 8
0x14000ef48  jmp     short loc_14000EF2E
0x14000ef4a  mov     rax, rcx
0x14000ef4d  retn
```
