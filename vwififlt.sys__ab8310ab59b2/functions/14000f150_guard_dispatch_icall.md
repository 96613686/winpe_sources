# _guard_dispatch_icall

- ea: `0x14000f150`
- end: `0x14000f156`
- name: `_guard_dispatch_icall`
- size: `6`
- prototype: ``
- caller_count: `30`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x1400080f0`
- `0x140008e70`
- `0x140009300`
- `0x140009bec`
- `0x14000a4e0`
- `0x14000a880`
- `0x14000ab50`
- `0x14000ada8`
- `0x14000aef0`
- `0x14000d8ec`
- `0x14000d91c`
- `0x14000d960`
- `0x14000d9d4`
- `0x14000da74`
- `0x14000db14`
- `0x14000db50`
- `0x14000dba8`
- `0x14000dc58`
- `0x14000dcc0`
- `0x14000dd28`
- `0x14000e0e8`
- `0x14000ed88`
- `0x14000ede4`
- `0x14000ee58`
- `0x14000eed4`
- `0x140010010`
- `0x140017008`
- `0x140017090`
- `0x14001732c`
- `0x140017474`

## callees

- `0x14000f180`

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
0x14000f150  jmp     cs:__guard_dispatch_icall_fptr
```
