# RtlUShortAdd

- ea: `0x1400024d4`
- end: `0x1400024f3`
- name: `RtlUShortAdd`
- size: `31`
- prototype: `NTSTATUS __stdcall(USHORT usAugend, USHORT usAddend, USHORT *pusResult)`
- caller_count: `11`
- callee_count: `1`
- tags: ``

## callers

- `0x140014ad4`
- `0x140018e28`
- `0x14001a62c`
- `0x140020434`
- `0x140020e60`
- `0x140023ee8`
- `0x14002bf4c`
- `0x14002c8d4`
- `0x14002daa4`
- `0x14002f9e4`
- `0x140030da4`

## callees

- `0x1400024d4`

## pseudocode

```c
NTSTATUS __stdcall RtlUShortAdd(USHORT usAugend, USHORT usAddend, USHORT *pusResult)
{
  bool v3; // cf
  USHORT v4; // dx

  v3 = (unsigned __int16)(usAddend + usAugend) < usAugend;
  if ( (unsigned __int16)(usAddend + usAugend) < usAugend )
    v4 = -1;
  else
    v4 = usAddend + usAugend;
  *pusResult = v4;
  return v3 ? 0xC0000095 : 0;
}

```

## disassembly

```asm
0x1400024d4  lea     eax, [rdx+rcx]
0x1400024d7  cmp     ax, cx
0x1400024da  jb      short loc_1400024EC
0x1400024dc  movzx   edx, ax
0x1400024df  sbb     eax, eax
0x1400024e1  mov     [r8], dx
0x1400024e5  and     eax, 0C0000095h
0x1400024ea  retn
0x1400024ec  mov     edx, 0FFFFh
0x1400024f1  jmp     short loc_1400024DF
```
