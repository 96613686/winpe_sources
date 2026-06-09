# MI_Instance_Destruct

- ea: `0x180005cec`
- end: `0x180005d08`
- name: `MI_Instance_Destruct`
- size: `28`
- prototype: `static MI_Result __stdcall(MI_Instance *self)`
- caller_count: `31`
- callee_count: `2`
- tags: ``

## callers

- `0x180006044`
- `0x1800061e0`
- `0x180009714`
- `0x18000b5f8`
- `0x18000bab8`
- `0x18000c708`
- `0x18000ca5c`
- `0x18000cb64`
- `0x18000cd24`
- `0x18000d1d0`
- `0x18000d3d0`
- `0x18000f414`
- `0x18000f6a8`
- `0x1800100a8`
- `0x180010354`
- `0x1800104f0`
- `0x18001075c`
- `0x180010998`
- `0x180010b34`
- `0x180010d90`
- `0x180012384`
- `0x1800128b0`
- `0x180012a58`
- `0x180013f60`
- `0x1800169ec`
- `0x180016ccc`
- `0x180019584`
- `0x18001a0fc`
- `0x18001c410`
- `0x18001c684`
- `0x18001c8f8`

## callees

- `0x180005cec`
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
0x180005cec  test    rcx, rcx
0x180005cef  jz      short loc_180005D02
0x180005cf1  mov     rax, [rcx]
0x180005cf4  test    rax, rax
0x180005cf7  jz      short loc_180005D02
0x180005cf9  mov     rax, [rax+8]
0x180005cfd  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x180005d02  mov     eax, 4
0x180005d07  retn
```
