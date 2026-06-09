# [thunk]:TLoad64BitDllsMgr::`vector deleting destructor'`adjustor{16}' (uint)

- ea: `0x140006670`
- end: `0x140006679`
- name: `??_ETLoad64BitDllsMgr@@WBA@EAAPEAXI@Z`
- size: `9`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x140006680`

## pseudocode

```c
TLoad64BitDllsMgr *__fastcall TLoad64BitDllsMgr::`vector deleting destructor'(__int64 a1, char a2)
{
  return TLoad64BitDllsMgr::`vector deleting destructor'((TLoad64BitDllsMgr *)(a1 - 16), a2);
}

```

## disassembly

```asm
0x140006670  sub     rcx, 10h; this
0x140006674  jmp     ??_ETLoad64BitDllsMgr@@UEAAPEAXI@Z; TLoad64BitDllsMgr::`vector deleting destructor'(uint)
```
