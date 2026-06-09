# [thunk]:CWSHExtension::`vector deleting destructor'`adjustor{40}' (uint)

- ea: `0x180005ef0`
- end: `0x180005ef9`
- name: `??_ECWSHExtension@@WCI@EAAPEAXI@Z`
- size: `9`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180005f00`

## pseudocode

```c
CWSHExtension *__fastcall CWSHExtension::`vector deleting destructor'(__int64 a1, char a2)
{
  return CWSHExtension::`vector deleting destructor'((CWSHExtension *)(a1 - 40), a2);
}

```

## disassembly

```asm
0x180005ef0  sub     rcx, 28h ; '('; this
0x180005ef4  jmp     ??_ECWSHExtension@@UEAAPEAXI@Z; CWSHExtension::`vector deleting destructor'(uint)
```
