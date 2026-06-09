# api_guard::~api_guard(void)

- ea: `0x18000aba0`
- end: `0x18000abbf`
- name: `??1api_guard@@QEAA@XZ`
- size: `31`
- prototype: `void __fastcall(api_guard *__hidden this)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x18000a98c`
- `0x18000abc8`
- `0x18000bc90`
- `0x18000d2c7`

## callees

- `0x18000bc08`

## pseudocode

```c
void __fastcall api_guard::~api_guard(api_guard *this, __int64 a2)
{
  __int64 v3; // rdx

  std::_Func_class<void,>::_Tidy((__int64)this + 64, a2);
  std::_Func_class<void,>::_Tidy((__int64)this, v3);
}

```

## disassembly

```asm
0x18000aba0  push    rbx
0x18000aba2  sub     rsp, 20h
0x18000aba6  mov     rbx, rcx
0x18000aba9  add     rcx, 40h ; '@'
0x18000abad  call    ?_Tidy@?$_Func_class@X$$V@std@@IEAAXXZ; std::_Func_class<void,>::_Tidy(void)
0x18000abb2  mov     rcx, rbx
0x18000abb5  add     rsp, 20h
0x18000abb9  pop     rbx
0x18000abba  jmp     ?_Tidy@?$_Func_class@X$$V@std@@IEAAXXZ; std::_Func_class<void,>::_Tidy(void)
```
