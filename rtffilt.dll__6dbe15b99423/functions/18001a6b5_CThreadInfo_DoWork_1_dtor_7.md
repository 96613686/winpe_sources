# _CThreadInfo::DoWork_::_1_::dtor$7

- ea: `0x18001a6b5`
- end: `0x18001a6c1`
- name: `_CThreadInfo::DoWork_::_1_::dtor$7`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x18000fbf0`

## pseudocode

```c
__int64 __fastcall CThreadInfo::DoWork_::_1_::dtor_7(__int64 a1, __int64 a2)
{
  return XInterface<ITextServices>::~XInterface<ITextServices>((__int64 *)(a2 + 192));
}

```

## disassembly

```asm
0x18001a6b5  lea     rcx, [rdx+0C0h]
0x18001a6bc  jmp     ??1?$XInterface@VITextServices@@@@QEAA@XZ; XInterface<ITextServices>::~XInterface<ITextServices>(void)
```
