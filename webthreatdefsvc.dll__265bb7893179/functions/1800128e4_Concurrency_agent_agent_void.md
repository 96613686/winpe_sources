# Concurrency::agent::~agent(void)

- ea: `0x1800128e4`
- end: `0x1800128f7`
- name: `??1agent@Concurrency@@UEAA@XZ`
- size: `19`
- prototype: `void __fastcall(Concurrency::agent *__hidden this)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x180003552`

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
0x1800128e4  lea     rax, ??_7exception@std@@6B@
0x1800128eb  mov     [rcx], rax
0x1800128ee  add     rcx, 8
0x1800128f2  jmp     _o___std_exception_destroy
```
