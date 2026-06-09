# SmpConfigureNumberInitialSessions

- ea: `0x140013630`
- end: `0x140013678`
- name: `SmpConfigureNumberInitialSessions`
- size: `72`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x140013630`

## pseudocode

```c
__int64 __fastcall SmpConfigureNumberInitialSessions(__int64 a1, int a2, unsigned int *a3, int a4)
{
  unsigned int v4; // eax

  if ( SmpManufacturingMode == 1 || !SmpHostSmss || a4 != 4 || a2 != 4 )
    goto LABEL_8;
  v4 = *a3;
  SmpNumberInitialSessions = v4;
  if ( v4 <= 2 )
  {
    if ( v4 )
      return 0;
LABEL_8:
    SmpNumberInitialSessions = 1;
    return 0;
  }
  SmpNumberInitialSessions = 2;
  return 0;
}

```

## disassembly

```asm
0x140013630  mov     ecx, 1
0x140013635  cmp     cs:SmpManufacturingMode, cl
0x14001363b  jz      short loc_14001366F
0x14001363d  cmp     cs:SmpHostSmss, 0
0x140013644  jz      short loc_14001366F
0x140013646  cmp     r9d, 4
0x14001364a  jnz     short loc_14001366F
0x14001364c  cmp     edx, r9d
0x14001364f  jnz     short loc_14001366F
0x140013651  mov     eax, [r8]
0x140013654  mov     cs:SmpNumberInitialSessions, eax
0x14001365a  cmp     eax, 2
0x14001365d  jbe     short loc_14001366B
0x14001365f  mov     cs:SmpNumberInitialSessions, 2
0x140013669  jmp     short loc_140013675
0x14001366b  cmp     eax, ecx
0x14001366d  jnb     short loc_140013675
0x14001366f  mov     cs:SmpNumberInitialSessions, ecx
0x140013675  xor     eax, eax
0x140013677  retn
```
