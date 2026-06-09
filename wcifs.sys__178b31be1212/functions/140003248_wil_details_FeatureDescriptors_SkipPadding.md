# wil_details_FeatureDescriptors_SkipPadding

- ea: `0x140003248`
- end: `0x14000326a`
- name: `wil_details_FeatureDescriptors_SkipPadding`
- size: `34`
- prototype: `PDEVICE_OBJECT *__fastcall(PDEVICE_OBJECT *)`
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x14002254c`
- `0x1400226dc`
- `0x140022770`
- `0x1400227ec`
- `0x140022870`
- `0x1400360a4`
- `0x140036164`

## callees

- `0x140003248`

## pseudocode

```c
PDEVICE_OBJECT *__fastcall wil_details_FeatureDescriptors_SkipPadding(PDEVICE_OBJECT *a1)
{
  while ( a1 < &wil_details_featureDescriptors_a )
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
0x140003248  xchg    ax, ax
0x14000324a  lea     rax, wil_details_featureDescriptors_a
0x140003251  cmp     rcx, rax
0x140003254  jnb     short loc_140003267
0x140003256  cmp     qword ptr [rcx], 0
0x14000325a  jnz     short loc_140003262
0x14000325c  add     rcx, 8
0x140003260  jmp     short loc_14000324A
0x140003262  mov     rax, rcx
0x140003265  retn
0x140003267  xor     eax, eax
0x140003269  retn
```
