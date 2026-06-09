# [thunk]:NThreadingLibrary::TWorkItem::`vector deleting destructor'`adjustor{16}' (uint)

- ea: `0x140013320`
- end: `0x140013329`
- name: `??_ETWorkItem@NThreadingLibrary@@WBA@EAAPEAXI@Z`
- size: `9`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x1400133c0`

## pseudocode

```c
NThreadingLibrary::TWorkItem *__fastcall NThreadingLibrary::TWorkItem::`vector deleting destructor'(
        __int64 a1,
        char a2)
{
  return NThreadingLibrary::TWorkItem::`vector deleting destructor'((NThreadingLibrary::TWorkItem *)(a1 - 16), a2);
}

```

## disassembly

```asm
0x140013320  sub     rcx, 10h; this
0x140013324  jmp     ??_ETWorkItem@NThreadingLibrary@@UEAAPEAXI@Z; NThreadingLibrary::TWorkItem::`vector deleting destructor'(uint)
```
