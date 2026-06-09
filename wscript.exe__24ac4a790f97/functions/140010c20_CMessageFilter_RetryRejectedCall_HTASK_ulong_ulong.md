# CMessageFilter::RetryRejectedCall(HTASK__ *,ulong,ulong)

- ea: `0x140010c20`
- end: `0x140010c31`
- name: `?RetryRejectedCall@CMessageFilter@@UEAAKPEAUHTASK__@@KK@Z`
- size: `17`
- prototype: `unsigned int __fastcall(CMessageFilter *__hidden this, HTASK, unsigned int, unsigned int)`
- caller_count: `0`
- callee_count: `0`
- tags: `service_task`

## pseudocode

```c
__int64 __fastcall CMessageFilter::RetryRejectedCall(CMessageFilter *this, HTASK a2, unsigned int a3)
{
  return a3 < 0x2710 ? 500 : -1;
}

```

## disassembly

```asm
0x140010c20  cmp     r8d, 2710h
0x140010c27  sbb     eax, eax
0x140010c29  and     eax, 1F5h
0x140010c2e  dec     eax
0x140010c30  retn
```
