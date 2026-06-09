# _guard_dispatch_icall

- ea: `0x140011ed0`
- end: `0x140011ed6`
- name: `_guard_dispatch_icall`
- size: `6`
- prototype: ``
- caller_count: `68`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x140001370`
- `0x140001780`
- `0x140001ce0`
- `0x140002190`
- `0x1400022c0`
- `0x140002410`
- `0x140004790`
- `0x140004860`
- `0x140004c40`
- `0x140005c40`
- `0x140006478`
- `0x1400068c0`
- `0x140007914`
- `0x140007b94`
- `0x140007d58`
- `0x14000840c`
- `0x14000862c`
- `0x140008d20`
- `0x140009028`
- `0x1400096f0`
- `0x14000a8c8`
- `0x14000a940`
- `0x14000a9bc`
- `0x14000ab90`
- `0x14000af84`
- `0x14000afe8`
- `0x14000b3d8`
- `0x14000bb70`
- `0x14000c87c`
- `0x14000cf30`
- `0x14000d310`
- `0x14000d9b0`
- `0x14000e148`
- `0x14000e414`
- `0x14000e4e0`
- `0x14000ed00`
- `0x14000f310`
- `0x14000f5c4`
- `0x14000f620`
- `0x14000f688`
- `0x14000f700`
- `0x14000f780`
- `0x14000f7ec`
- `0x14000f880`
- `0x14000f8f4`
- `0x14000f96c`
- `0x14000f9dc`
- `0x14000fa38`
- `0x14000fb10`
- `0x14000fb50`

## callees

- `0x140011f00`

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
0x140011ed0  jmp     cs:__guard_dispatch_icall_fptr
```
