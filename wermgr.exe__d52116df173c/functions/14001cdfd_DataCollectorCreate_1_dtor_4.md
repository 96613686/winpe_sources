# _DataCollectorCreate_::_1_::dtor$4

- ea: `0x14001cdfd`
- end: `0x14001ce09`
- name: `_DataCollectorCreate_::_1_::dtor$4`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x140004a50`

## pseudocode

```c
__int64 __fastcall DataCollectorCreate_::_1_::dtor_4(__int64 a1, __int64 a2)
{
  return utl::unique_ptr<IHxHelpPane,tlx::release_delete>::~unique_ptr<IHxHelpPane,tlx::release_delete>((__int64 *)(a2 + 280));
}

```

## disassembly

```asm
0x14001cdfd  lea     rcx, [rdx+118h]
0x14001ce04  jmp     ??1?$unique_ptr@UIHxHelpPane@@Urelease_delete@tlx@@@utl@@QEAA@XZ; utl::unique_ptr<IHxHelpPane,tlx::release_delete>::~unique_ptr<IHxHelpPane,tlx::release_delete>(void)
```
