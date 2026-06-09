# _guard_dispatch_icall

- ea: `0x140015680`
- end: `0x140015686`
- name: `_guard_dispatch_icall`
- size: `6`
- prototype: ``
- caller_count: `72`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x1400015ec`
- `0x140001f78`
- `0x1400020c0`
- `0x140002f50`
- `0x1400056d0`
- `0x140005794`
- `0x1400057c4`
- `0x140005830`
- `0x140005884`
- `0x1400058dc`
- `0x140005948`
- `0x1400059a4`
- `0x14000642c`
- `0x14000675c`
- `0x140006798`
- `0x1400067dc`
- `0x1400077ac`
- `0x140007d58`
- `0x140008110`
- `0x1400082a8`
- `0x1400083b8`
- `0x140008760`
- `0x14000880c`
- `0x140008878`
- `0x1400088f0`
- `0x14000cdf8`
- `0x14000ce98`
- `0x14000cf50`
- `0x14000d04c`
- `0x14000d0b8`
- `0x14000d228`
- `0x14000d300`
- `0x14000d740`
- `0x14000dc1c`
- `0x14000dcb8`
- `0x14000dd98`
- `0x14000de60`
- `0x14000dec0`
- `0x14000df80`
- `0x14000ebb8`
- `0x14000ec80`
- `0x14000eca0`
- `0x14000edb4`
- `0x14000ee3c`
- `0x14000eee0`
- `0x14000ef3c`
- `0x14000ef88`
- `0x14000efe4`
- `0x14000f04c`
- `0x14000f0c0`

## callees

- `0x1400156b0`

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
0x140015680  jmp     cs:__guard_dispatch_icall_fptr
```
