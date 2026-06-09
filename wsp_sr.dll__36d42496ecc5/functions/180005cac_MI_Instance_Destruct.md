# MI_Instance_Destruct

- ea: `0x180005cac`
- end: `0x180005cc8`
- name: `MI_Instance_Destruct`
- size: `28`
- prototype: `static MI_Result __stdcall(MI_Instance *self)`
- caller_count: `31`
- callee_count: `2`
- tags: ``

## callers

- `0x180006004`
- `0x1800061a0`
- `0x180009554`
- `0x18000b48c`
- `0x18000b98c`
- `0x18000c670`
- `0x18000ca34`
- `0x18000cb74`
- `0x18000cda0`
- `0x18000d2ac`
- `0x18000d4e4`
- `0x18000f440`
- `0x18000f6d4`
- `0x1800100d0`
- `0x18001039c`
- `0x18001056c`
- `0x1800107f8`
- `0x180010a68`
- `0x180010c38`
- `0x180010ec0`
- `0x1800124bc`
- `0x1800129e4`
- `0x180012b88`
- `0x180014050`
- `0x180016b28`
- `0x180016e04`
- `0x180019550`
- `0x18001a0c4`
- `0x18001c318`
- `0x18001c588`
- `0x18001c7f8`

## callees

- `0x180005cac`
- `0x18002d010`

## pseudocode

```c
MI_Result __stdcall MI_Instance_Destruct(MI_Instance *self)
{
  if ( self && self->ft )
    return ((unsigned int (__fastcall *)(MI_Instance *))self->ft->Destruct)(self);
  else
    return 4;
}

```

## disassembly

```asm
0x180005cac  test    rcx, rcx
0x180005caf  jz      short loc_180005CC2
0x180005cb1  mov     rax, [rcx]
0x180005cb4  test    rax, rax
0x180005cb7  jz      short loc_180005CC2
0x180005cb9  mov     rax, [rax+8]
0x180005cbd  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x180005cc2  mov     eax, 4
0x180005cc7  retn
```
