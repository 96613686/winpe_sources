# _CProfileTask_OnDelete::Execute_::_1_::dtor$2

- ea: `0x18000dcce`
- end: `0x18000dcda`
- name: `_CProfileTask_OnDelete::Execute_::_1_::dtor$2`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x180004ca0`

## pseudocode

```c
void __fastcall CProfileTask_OnDelete::Execute_::_1_::dtor_2(__int64 a1, __int64 a2)
{
  std::unique_ptr<wchar_t [0]>::~unique_ptr<wchar_t [0]>((void **)(a2 + 120));
}

```

## disassembly

```asm
0x18000dcce  lea     rcx, [rdx+78h]
0x18000dcd5  jmp     ??1?$unique_ptr@$$BY0A@_WU?$default_delete@$$BY0A@_W@std@@@std@@QEAA@XZ; std::unique_ptr<wchar_t [0]>::~unique_ptr<wchar_t [0]>(void)
```
