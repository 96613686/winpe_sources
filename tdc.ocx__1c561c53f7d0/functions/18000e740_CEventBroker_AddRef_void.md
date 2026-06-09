# CEventBroker::AddRef(void)

- ea: `0x18000e740`
- end: `0x18000e747`
- name: `?AddRef@CEventBroker@@UEAAKXZ`
- size: `7`
- prototype: `unsigned int __fastcall(CEventBroker *__hidden this)`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## pseudocode

```c
__int64 __fastcall CEventBroker::AddRef(CEventBroker *this)
{
  return (unsigned int)++*((_DWORD *)this + 4);
}

```

## disassembly

```asm
0x18000e740  inc     dword ptr [rcx+10h]
0x18000e743  mov     eax, [rcx+10h]
0x18000e746  retn
```
