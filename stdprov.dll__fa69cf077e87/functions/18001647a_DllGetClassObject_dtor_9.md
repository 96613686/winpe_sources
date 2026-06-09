# DllGetClassObject$dtor$9

- ea: `0x18001647a`
- end: `0x180016486`
- name: `DllGetClassObject$dtor$9`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000bbf8`

## pseudocode

```c
void __fastcall DllGetClassObject_dtor_9(__int64 a1, __int64 a2)
{
  CCFDyn::~CCFDyn(*(CCFDyn **)(a2 + 64));
}

```

## disassembly

```asm
0x18001647a  mov     rcx, [rdx+40h]; this
0x180016481  jmp     ??1CCFDyn@@UEAA@XZ; CCFDyn::~CCFDyn(void)
```
