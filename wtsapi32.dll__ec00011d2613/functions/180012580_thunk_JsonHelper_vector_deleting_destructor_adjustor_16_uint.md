# [thunk]:JsonHelper::`vector deleting destructor'`adjustor{16}' (uint)

- ea: `0x180012580`
- end: `0x180012589`
- name: `??_EJsonHelper@@WBA@EAAPEAXI@Z`
- size: `9`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x1800125d0`

## pseudocode

```c
JsonHelper *__fastcall JsonHelper::`vector deleting destructor'(__int64 a1, char a2)
{
  return JsonHelper::`vector deleting destructor'((JsonHelper *)(a1 - 16), a2);
}

```

## disassembly

```asm
0x180012580  sub     rcx, 10h; this
0x180012584  jmp     ??_EJsonHelper@@UEAAPEAXI@Z; JsonHelper::`vector deleting destructor'(uint)
```
