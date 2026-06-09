# _guard_dispatch_icall

- ea: `0x1400025c0`
- end: `0x1400025c6`
- name: `_guard_dispatch_icall`
- size: `6`
- prototype: ``
- caller_count: `39`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x1400010bc`
- `0x140001114`
- `0x14000117c`
- `0x1400011dc`
- `0x140001264`
- `0x1400012b8`
- `0x140001330`
- `0x140001374`
- `0x1400013d0`
- `0x140001618`
- `0x14000166c`
- `0x1400016d4`
- `0x140001740`
- `0x1400017c8`
- `0x140001a0c`
- `0x140001a3c`
- `0x140001a88`
- `0x140001aec`
- `0x140001d84`
- `0x140001e10`
- `0x140001e84`
- `0x140001f7c`
- `0x140001fec`
- `0x140002158`
- `0x1400021c0`
- `0x14000221c`
- `0x140002298`
- `0x1400022fc`
- `0x140003070`
- `0x14000f120`
- `0x14000f1b4`
- `0x14000f300`
- `0x140013ff0`
- `0x14001953c`
- `0x14001a000`
- `0x14001a870`
- `0x14001c010`
- `0x14001d510`
- `0x140020450`

## callees

- `0x140002560`

## pseudocode

```c
// attributes: thunk
__int64 __fastcall guard_dispatch_icall()
{
  __int64 (__fastcall *v0)(); // rax

  return v0();
}

```

## disassembly

```asm
0x1400025c0  jmp     cs:__guard_dispatch_icall_fptr
```
