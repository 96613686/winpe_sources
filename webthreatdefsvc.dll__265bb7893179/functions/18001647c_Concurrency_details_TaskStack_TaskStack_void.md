# Concurrency::details::TaskStack::~TaskStack(void)

- ea: `0x18001647c`
- end: `0x180016493`
- name: `??1TaskStack@details@Concurrency@@QEAA@XZ`
- size: `23`
- prototype: `void __fastcall(Concurrency::details::TaskStack *__hidden this)`
- caller_count: `3`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x180013db8`
- `0x180013e5c`
- `0x18001443c`

## callees

- `0x18001647c`
- `0x18001649c`

## pseudocode

```c
void __fastcall Concurrency::details::TaskStack::~TaskStack(Concurrency::details::TaskStack *this)
{
  if ( *((_QWORD *)this + 1) )
    sub_18001649C();
}

```

## disassembly

```asm
0x18001647c  sub     rsp, 28h
0x180016480  mov     rcx, [rcx+8]
0x180016484  test    rcx, rcx
0x180016487  jz      short loc_18001648E
0x180016489  call    sub_18001649C
0x18001648e  add     rsp, 28h
0x180016492  retn
```
