# _WslSession::s_Create_::_1_::dtor$4

- ea: `0x18000c186`
- end: `0x18000c196`
- name: `_WslSession::s_Create_::_1_::dtor$4`
- size: `16`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x1800068e0`

## pseudocode

```c
__int64 __fastcall WslSession::s_Create_::_1_::dtor_4(__int64 a1, __int64 a2)
{
  return wil::unique_call<void (*)(void),&void CoUninitialize(void),1>::~unique_call<void (*)(void),&void CoUninitialize(void),1>(*(_QWORD *)(a2 + 32) + 8LL);
}

```

## disassembly

```asm
0x18000c186  mov     rcx, [rdx+20h]
0x18000c18d  add     rcx, 8
0x18000c191  jmp     ??1?$unique_call@P6AXXZ$1?CoUninitialize@@YAXXZ$00@wil@@QEAA@XZ; wil::unique_call<void (*)(void),&CoUninitialize(void),1>::~unique_call<void (*)(void),&CoUninitialize(void),1>(void)
```
