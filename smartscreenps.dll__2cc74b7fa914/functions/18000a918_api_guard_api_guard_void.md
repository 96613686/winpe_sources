# api_guard::~api_guard(void)

- ea: `0x18000a918`
- end: `0x18000a937`
- name: `??1api_guard@@QEAA@XZ`
- size: `31`
- prototype: `void __fastcall(api_guard *__hidden this)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x18000a710`
- `0x18000a940`
- `0x18000b9b0`
- `0x18000cfe3`

## callees

- `0x18000b938`

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
0x18000a918  push    rbx
0x18000a91a  sub     rsp, 20h
0x18000a91e  mov     rbx, rcx
0x18000a921  add     rcx, 40h ; '@'
0x18000a925  call    ?_Tidy@?$_Func_class@X$$V@std@@IEAAXXZ; std::_Func_class<void,>::_Tidy(void)
0x18000a92a  mov     rcx, rbx
0x18000a92d  add     rsp, 20h
0x18000a931  pop     rbx
0x18000a932  jmp     ?_Tidy@?$_Func_class@X$$V@std@@IEAAXXZ; std::_Func_class<void,>::_Tidy(void)
```
