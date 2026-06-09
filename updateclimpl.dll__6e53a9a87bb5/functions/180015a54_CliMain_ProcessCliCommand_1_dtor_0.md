# _CliMain::ProcessCliCommand_::_1_::dtor$0

- ea: `0x180015a54`
- end: `0x180015a60`
- name: `_CliMain::ProcessCliCommand_::_1_::dtor$0`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000bc60`

## pseudocode

```c
__int64 __fastcall CliMain::ProcessCliCommand_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  return wil::unique_call<void (*)(void),&void CoUninitialize(void),1>::~unique_call<void (*)(void),&void CoUninitialize(void),1>(a2 + 32);
}

```

## disassembly

```asm
0x180015a54  lea     rcx, [rdx+20h]
0x180015a5b  jmp     ??1?$unique_call@P6AXXZ$1?CoUninitialize@@YAXXZ$00@wil@@QEAA@XZ; wil::unique_call<void (*)(void),&CoUninitialize(void),1>::~unique_call<void (*)(void),&CoUninitialize(void),1>(void)
```
