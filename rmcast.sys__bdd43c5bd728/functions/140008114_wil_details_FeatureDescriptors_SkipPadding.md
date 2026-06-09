# wil_details_FeatureDescriptors_SkipPadding

- ea: `0x140008114`
- end: `0x140008134`
- name: `wil_details_FeatureDescriptors_SkipPadding`
- size: `32`
- prototype: ``
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x1400367bc`
- `0x14003694c`
- `0x1400369e0`
- `0x140036a5c`
- `0x140036ae0`
- `0x14003a23c`
- `0x14003a2fc`

## callees

- `0x140008114`

## pseudocode

```c
__int64 *__fastcall wil_details_FeatureDescriptors_SkipPadding(__int64 *a1)
{
  while ( 1 )
  {
    if ( a1 >= wil_details_featureDescriptors_a )
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
0x140008114  lea     rax, wil_details_featureDescriptors_a
0x14000811b  jmp     short loc_140008127
0x14000811d  cmp     qword ptr [rcx], 0
0x140008121  jnz     short loc_140008130
0x140008123  add     rcx, 8
0x140008127  cmp     rcx, rax
0x14000812a  jb      short loc_14000811D
0x14000812c  xor     eax, eax
0x14000812e  retn
0x140008130  mov     rax, rcx
0x140008133  retn
```
