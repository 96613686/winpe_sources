# [thunk]:NThreadingLibrary::TWorkCrew::`vector deleting destructor'`adjustor{16}' (uint)

- ea: `0x140013310`
- end: `0x140013319`
- name: `??_ETWorkCrew@NThreadingLibrary@@WBA@EAAPEAXI@Z`
- size: `9`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x140013380`

## pseudocode

```c
struct _RTL_CRITICAL_SECTION *__fastcall NThreadingLibrary::TWorkCrew::`vector deleting destructor'(
        __int64 a1,
        void **a2)
{
  return NThreadingLibrary::TWorkCrew::`scalar deleting destructor'((struct _RTL_CRITICAL_SECTION *)(a1 - 16), a2);
}

```

## disassembly

```asm
0x140013310  sub     rcx, 10h; this
0x140013314  jmp     ??_GTWorkCrew@NThreadingLibrary@@UEAAPEAXI@Z; NThreadingLibrary::TWorkCrew::`scalar deleting destructor'(uint)
```
