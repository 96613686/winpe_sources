# _guard_dispatch_icall

- ea: `0x140018590`
- end: `0x140018596`
- name: `_guard_dispatch_icall`
- size: `6`
- prototype: ``
- caller_count: `71`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x140001550`
- `0x140002920`
- `0x140002ccc`
- `0x140003c9c`
- `0x1400043b0`
- `0x140004920`
- `0x140004df4`
- `0x140005688`
- `0x140005b00`
- `0x140006608`
- `0x140006db0`
- `0x1400075b0`
- `0x140007b90`
- `0x140009ad0`
- `0x14000a1b0`
- `0x14000aad0`
- `0x14000bab0`
- `0x14000cde0`
- `0x14000f4f0`
- `0x14000f650`
- `0x140010100`
- `0x140010608`
- `0x140011990`
- `0x140012400`
- `0x140012b5c`
- `0x140012b8c`
- `0x140012bd0`
- `0x140012c74`
- `0x140012cec`
- `0x140012d84`
- `0x140012e34`
- `0x140012e90`
- `0x140012ee4`
- `0x140012f64`
- `0x140012fd0`
- `0x14001303c`
- `0x1400130bc`
- `0x140013174`
- `0x140013460`
- `0x140013760`
- `0x1400139b0`
- `0x140013af4`
- `0x140013bf8`
- `0x140013c84`
- `0x140013d04`
- `0x140013dc0`
- `0x140013e60`
- `0x140013eec`
- `0x140013f88`
- `0x140013ffc`

## callees

- `0x140018530`

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
0x140018590  jmp     cs:__guard_dispatch_icall_fptr
```
