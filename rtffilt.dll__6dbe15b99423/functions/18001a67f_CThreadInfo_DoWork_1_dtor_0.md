# _CThreadInfo::DoWork_::_1_::dtor$0

- ea: `0x18001a67f`
- end: `0x18001a68b`
- name: `_CThreadInfo::DoWork_::_1_::dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x18000fbf0`

## pseudocode

```c
__int64 __fastcall CThreadInfo::DoWork_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  return XInterface<ITextServices>::~XInterface<ITextServices>((__int64 *)(a2 + 208));
}

```

## disassembly

```asm
0x18001a67f  lea     rcx, [rdx+0D0h]
0x18001a686  jmp     ??1?$XInterface@VITextServices@@@@QEAA@XZ; XInterface<ITextServices>::~XInterface<ITextServices>(void)
```
