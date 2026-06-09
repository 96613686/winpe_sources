# Concurrency::details::TaskStack::~TaskStack(void)

- ea: `0x1800253b4`
- end: `0x1800253cb`
- name: `??1TaskStack@details@Concurrency@@QEAA@XZ`
- size: `23`
- prototype: `void __fastcall(Concurrency::details::TaskStack *__hidden this)`
- caller_count: `7`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x1800253a8`
- `0x180025510`
- `0x18002556c`
- `0x180027ac8`
- `0x180028a84`
- `0x18002c340`
- `0x18002c360`

## callees

- `0x1800253b4`
- `0x1800277ac`

## pseudocode

```c
void __fastcall Concurrency::details::TaskStack::~TaskStack(Concurrency::details::TaskStack *this)
{
  if ( *((_QWORD *)this + 1) )
    sub_1800277AC();
}

```

## disassembly

```asm
0x1800253b4  sub     rsp, 28h
0x1800253b8  mov     rcx, [rcx+8]
0x1800253bc  test    rcx, rcx
0x1800253bf  jz      short loc_1800253C6
0x1800253c1  call    sub_1800277AC
0x1800253c6  add     rsp, 28h
0x1800253ca  retn
```
