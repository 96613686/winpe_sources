# Concurrency::agent::~agent(void)

- ea: `0x180022cdc`
- end: `0x180022cef`
- name: `??1agent@Concurrency@@UEAA@XZ`
- size: `19`
- prototype: `void __fastcall(Concurrency::agent *__hidden this)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x18000411e`

## pseudocode

```c
void __fastcall Concurrency::agent::~agent(Concurrency::agent *this)
{
  *(_QWORD *)this = &std::exception::`vftable';
  o___std_exception_destroy((char *)this + 8);
}

```

## disassembly

```asm
0x180022cdc  lea     rax, ??_7exception@std@@6B@
0x180022ce3  mov     [rcx], rax
0x180022ce6  add     rcx, 8
0x180022cea  jmp     _o___std_exception_destroy
```
