# _CProfileTask::DeletePerUserSearchRootsAndScopeRules_::_1_::dtor$6

- ea: `0x18000dc98`
- end: `0x18000dca4`
- name: `_CProfileTask::DeletePerUserSearchRootsAndScopeRules_::_1_::dtor$6`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x180004ca0`

## pseudocode

```c
void __fastcall CProfileTask::DeletePerUserSearchRootsAndScopeRules_::_1_::dtor_6(__int64 a1, __int64 a2)
{
  std::unique_ptr<wchar_t [0]>::~unique_ptr<wchar_t [0]>((void **)(a2 + 112));
}

```

## disassembly

```asm
0x18000dc98  lea     rcx, [rdx+70h]
0x18000dc9f  jmp     ??1?$unique_ptr@$$BY0A@_WU?$default_delete@$$BY0A@_W@std@@@std@@QEAA@XZ; std::unique_ptr<wchar_t [0]>::~unique_ptr<wchar_t [0]>(void)
```
