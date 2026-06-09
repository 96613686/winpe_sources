# SmpConfigureClearTempFiles

- ea: `0x140013320`
- end: `0x140013333`
- name: `SmpConfigureClearTempFiles`
- size: `19`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x140013320`

## pseudocode

```c
__int64 __fastcall SmpConfigureClearTempFiles(__int64 a1, __int64 a2, __int64 a3, int a4)
{
  if ( a4 == 4 )
    SmpClearTempFiles = 1;
  return 0;
}

```

## disassembly

```asm
0x140013320  cmp     r9d, 4
0x140013324  jnz     short loc_140013330
0x140013326  mov     cs:SmpClearTempFiles, 1
0x140013330  xor     eax, eax
0x140013332  retn
```
