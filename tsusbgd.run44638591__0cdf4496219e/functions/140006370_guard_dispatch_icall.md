# _guard_dispatch_icall

- ea: `0x140006370`
- end: `0x140006376`
- name: `_guard_dispatch_icall`
- size: `6`
- prototype: ``
- caller_count: `43`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x140001308`
- `0x140001464`
- `0x140001998`
- `0x140001ac0`
- `0x140001b04`
- `0x140001b50`
- `0x140001d10`
- `0x140001f8c`
- `0x140002228`
- `0x140002318`
- `0x1400025bc`
- `0x1400027e4`
- `0x140002978`
- `0x140002c60`
- `0x140003118`
- `0x140003368`
- `0x140003610`
- `0x1400037d0`
- `0x140003934`
- `0x140003964`
- `0x1400039b8`
- `0x140003a10`
- `0x140003a60`
- `0x140003b00`
- `0x140003c10`
- `0x140003e20`
- `0x140003f80`
- `0x140004040`
- `0x14000410c`
- `0x140004244`
- `0x1400043c0`
- `0x1400043f4`
- `0x140004580`
- `0x1400049ac`
- `0x140007010`
- `0x14000c010`
- `0x14000c2e0`
- `0x14000c330`
- `0x14000c390`
- `0x14000c430`
- `0x14000c4c4`
- `0x14000c610`
- `0x14000d03c`

## callees

- `0x1400063a0`

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
0x140006370  jmp     cs:__guard_dispatch_icall_fptr
```
