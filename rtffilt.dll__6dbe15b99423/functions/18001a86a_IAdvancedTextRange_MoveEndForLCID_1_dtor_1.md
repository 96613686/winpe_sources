# _IAdvancedTextRange::MoveEndForLCID_::_1_::dtor$1

- ea: `0x18001a86a`
- end: `0x18001a876`
- name: `_IAdvancedTextRange::MoveEndForLCID_::_1_::dtor$1`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x18000fbf0`

## pseudocode

```c
__int64 __fastcall IAdvancedTextRange::MoveEndForLCID_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  return XInterface<ITextServices>::~XInterface<ITextServices>((__int64 *)(a2 + 56));
}

```

## disassembly

```asm
0x18001a86a  lea     rcx, [rdx+38h]
0x18001a871  jmp     ??1?$XInterface@VITextServices@@@@QEAA@XZ; XInterface<ITextServices>::~XInterface<ITextServices>(void)
```
