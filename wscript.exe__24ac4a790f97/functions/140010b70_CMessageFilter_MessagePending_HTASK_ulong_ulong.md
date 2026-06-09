# CMessageFilter::MessagePending(HTASK__ *,ulong,ulong)

- ea: `0x140010b70`
- end: `0x140010b76`
- name: `?MessagePending@CMessageFilter@@UEAAKPEAUHTASK__@@KK@Z`
- size: `6`
- prototype: `unsigned int __fastcall(CMessageFilter *__hidden this, HTASK, unsigned int, unsigned int)`
- caller_count: `0`
- callee_count: `0`
- tags: `service_task`

## pseudocode

```c
__int64 __fastcall CMessageFilter::MessagePending(CMessageFilter *this, HTASK a2)
{
  return 1;
}

```

## disassembly

```asm
0x140010b70  mov     eax, 1
0x140010b75  retn
```
