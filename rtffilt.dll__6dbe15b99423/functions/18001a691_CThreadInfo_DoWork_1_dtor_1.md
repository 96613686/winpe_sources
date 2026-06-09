# _CThreadInfo::DoWork_::_1_::dtor$1

- ea: `0x18001a691`
- end: `0x18001a69d`
- name: `_CThreadInfo::DoWork_::_1_::dtor$1`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x18000fbf0`

## pseudocode

```c
__int64 __fastcall CThreadInfo::DoWork_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  return XInterface<ITextServices>::~XInterface<ITextServices>((__int64 *)(a2 + 200));
}

```

## disassembly

```asm
0x18001a691  lea     rcx, [rdx+0C8h]
0x18001a698  jmp     ??1?$XInterface@VITextServices@@@@QEAA@XZ; XInterface<ITextServices>::~XInterface<ITextServices>(void)
```
