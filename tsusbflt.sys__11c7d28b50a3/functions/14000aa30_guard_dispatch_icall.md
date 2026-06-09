# _guard_dispatch_icall

- ea: `0x14000aa30`
- end: `0x14000aa36`
- name: `_guard_dispatch_icall`
- size: `6`
- prototype: ``
- caller_count: `75`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x140001e28`
- `0x140001e80`
- `0x140002ae0`
- `0x140002bc4`
- `0x140003258`
- `0x140003a1c`
- `0x140003acc`
- `0x140003f90`
- `0x140004480`
- `0x140004724`
- `0x140004a18`
- `0x140004c74`
- `0x140004f18`
- `0x140004f48`
- `0x140004f8c`
- `0x140005000`
- `0x140005084`
- `0x1400050c8`
- `0x1400051b4`
- `0x140005520`
- `0x140005754`
- `0x140005a54`
- `0x140005d24`
- `0x140005e44`
- `0x1400060dc`
- `0x140006128`
- `0x14000617c`
- `0x140006278`
- `0x1400065e8`
- `0x1400068dc`
- `0x140006d2c`
- `0x140006efc`
- `0x14000711c`
- `0x140007c24`
- `0x14000818c`
- `0x1400085e4`
- `0x140008818`
- `0x140008940`
- `0x140008b54`
- `0x140008d84`
- `0x140008ec8`
- `0x1400090d4`
- `0x140009360`
- `0x1400093f0`
- `0x140009440`
- `0x1400094a0`
- `0x1400095c0`
- `0x140009650`
- `0x1400096a0`
- `0x140009930`

## callees

- `0x14000aa60`

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
0x14000aa30  jmp     cs:__guard_dispatch_icall_fptr
```
