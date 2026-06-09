# _guard_dispatch_icall

- ea: `0x140017190`
- end: `0x140017196`
- name: `_guard_dispatch_icall`
- size: `6`
- prototype: ``
- caller_count: `151`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x140001120`
- `0x1400018f0`
- `0x140001b70`
- `0x140002620`
- `0x140003600`
- `0x14000389c`
- `0x1400038cc`
- `0x140003b60`
- `0x140003bd0`
- `0x140003eb8`
- `0x1400041b4`
- `0x1400044b8`
- `0x140004684`
- `0x140004780`
- `0x1400047f0`
- `0x14000487c`
- `0x1400048dc`
- `0x140004918`
- `0x140004974`
- `0x140004b6c`
- `0x140004c50`
- `0x140004ce0`
- `0x140004f40`
- `0x1400053a0`
- `0x1400054fc`
- `0x140005564`
- `0x1400055cc`
- `0x140005610`
- `0x14000566c`
- `0x140005aa0`
- `0x140005bf0`
- `0x140005d50`
- `0x140005f28`
- `0x140005fc8`
- `0x1400060d8`
- `0x140006390`
- `0x1400063d0`
- `0x1400066b0`
- `0x1400069e4`
- `0x140006a70`
- `0x140006b50`
- `0x140006ca0`
- `0x140006ea0`
- `0x140007230`
- `0x140007330`
- `0x140007430`
- `0x140007530`
- `0x140009600`
- `0x140009690`
- `0x140009ab0`

## callees

- `0x1400171c0`

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
0x140017190  jmp     cs:__guard_dispatch_icall_fptr
```
