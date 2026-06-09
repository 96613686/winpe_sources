# _guard_dispatch_icall

- ea: `0x140014d50`
- end: `0x140014d56`
- name: `_guard_dispatch_icall`
- size: `6`
- prototype: ``
- caller_count: `73`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x140001008`
- `0x140001118`
- `0x140001220`
- `0x1400044cc`
- `0x14000476c`
- `0x140004ed0`
- `0x14000554c`
- `0x140007020`
- `0x140007170`
- `0x140008040`
- `0x1400083c8`
- `0x1400088b4`
- `0x140008eac`
- `0x140009450`
- `0x1400099a8`
- `0x14000a448`
- `0x14000a6cc`
- `0x14000adbc`
- `0x14000b0ec`
- `0x14000b1f0`
- `0x14000b4bc`
- `0x14000b8cc`
- `0x14000ba3c`
- `0x14000c2bc`
- `0x14000c4d0`
- `0x14000c620`
- `0x14000c6b0`
- `0x14000c7e8`
- `0x14000cd78`
- `0x14000d240`
- `0x14000dc18`
- `0x14000dccc`
- `0x14000dfac`
- `0x14000e660`
- `0x14000e754`
- `0x14000e8a4`
- `0x14000edf4`
- `0x14000efe0`
- `0x14000f0c0`
- `0x14000f0ec`
- `0x14000fa04`
- `0x1400103a4`
- `0x140010b00`
- `0x1400115c8`
- `0x1400116a4`
- `0x1400119f0`
- `0x140011a78`
- `0x140011b58`
- `0x140011eb0`
- `0x140012218`

## callees

- `0x140014d80`

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
0x140014d50  jmp     cs:__guard_dispatch_icall_fptr
```
