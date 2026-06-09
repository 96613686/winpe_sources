# wil_details_FeatureDescriptors_SkipPadding

- ea: `0x14000e184`
- end: `0x14000e1a4`
- name: `wil_details_FeatureDescriptors_SkipPadding`
- size: `32`
- prototype: ``
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x14002ff70`
- `0x140030100`
- `0x1400301a0`
- `0x14003021c`
- `0x1400302a0`
- `0x1400363d4`
- `0x140036494`

## callees

- `0x14000e184`

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
0x14000e184  lea     rax, wil_details_featureDescriptors_z
0x14000e18b  jmp     short loc_14000E197
0x14000e18d  cmp     qword ptr [rcx], 0
0x14000e191  jnz     short loc_14000E1A0
0x14000e193  add     rcx, 8
0x14000e197  cmp     rcx, rax
0x14000e19a  jb      short loc_14000E18D
0x14000e19c  xor     eax, eax
0x14000e19e  retn
0x14000e1a0  mov     rax, rcx
0x14000e1a3  retn
```
