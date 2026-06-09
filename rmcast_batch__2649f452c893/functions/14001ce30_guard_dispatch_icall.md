# _guard_dispatch_icall

- ea: `0x14001ce30`
- end: `0x14001ce36`
- name: `_guard_dispatch_icall`
- size: `6`
- prototype: ``
- caller_count: `99`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x140005038`
- `0x140005068`
- `0x1400050ac`
- `0x140005100`
- `0x140005168`
- `0x1400051c8`
- `0x14000521c`
- `0x140005280`
- `0x1400052e4`
- `0x140005328`
- `0x14000537c`
- `0x1400053d8`
- `0x140005464`
- `0x1400054d0`
- `0x140005524`
- `0x140005584`
- `0x1400055f0`
- `0x1400056a4`
- `0x140005744`
- `0x140006dbc`
- `0x140006e34`
- `0x140006ee4`
- `0x140006f5c`
- `0x14000702c`
- `0x140007f9c`
- `0x140008004`
- `0x14000806c`
- `0x140009f50`
- `0x140009fbc`
- `0x14000a050`
- `0x14000a0e0`
- `0x14000a580`
- `0x14000b670`
- `0x14000bc98`
- `0x14000bcfc`
- `0x14000bd74`
- `0x14000be18`
- `0x14000bef8`
- `0x14000cf04`
- `0x14001013c`
- `0x140010ae4`
- `0x14001511c`
- `0x1400151b0`
- `0x140015214`
- `0x14001528c`
- `0x140015300`
- `0x14001538c`
- `0x1400153e8`
- `0x140015434`
- `0x14001548c`

## callees

- `0x14001ce60`

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
0x14001ce30  jmp     cs:__guard_dispatch_icall_fptr
```
