# wil_details_FeatureDescriptors_SkipPadding

- ea: `0x14000f4cc`
- end: `0x14000f4ee`
- name: `wil_details_FeatureDescriptors_SkipPadding`
- size: `34`
- prototype: ``
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x1400258cc`
- `0x140025a04`
- `0x140025aa0`
- `0x140025b1c`
- `0x140025ba0`
- `0x140040990`
- `0x140040a50`

## callees

- `0x14000f4cc`

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
0x14000f4cc  xchg    ax, ax
0x14000f4ce  lea     rax, wil_details_featureDescriptors_z
0x14000f4d5  cmp     rcx, rax
0x14000f4d8  jnb     short loc_14000F4EB
0x14000f4da  cmp     qword ptr [rcx], 0
0x14000f4de  jnz     short loc_14000F4E6
0x14000f4e0  add     rcx, 8
0x14000f4e4  jmp     short loc_14000F4CE
0x14000f4e6  mov     rax, rcx
0x14000f4e9  retn
0x14000f4eb  xor     eax, eax
0x14000f4ed  retn
```
