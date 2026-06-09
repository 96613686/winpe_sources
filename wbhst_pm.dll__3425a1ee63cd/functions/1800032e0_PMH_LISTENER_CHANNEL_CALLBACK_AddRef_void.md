# PMH_LISTENER_CHANNEL_CALLBACK::AddRef(void)

- ea: `0x1800032e0`
- end: `0x1800032ed`
- name: `?AddRef@PMH_LISTENER_CHANNEL_CALLBACK@@UEAAKXZ`
- size: `13`
- prototype: `unsigned int __fastcall(PMH_LISTENER_CHANNEL_CALLBACK *__hidden this)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x180001a90`

## pseudocode

```c
__int64 __fastcall PMH_LISTENER_CHANNEL_CALLBACK::AddRef(PMH_LISTENER_CHANNEL_CALLBACK *this)
{
  return (unsigned int)_InterlockedIncrement((volatile signed __int32 *)this + 5);
}

```

## disassembly

```asm
0x1800032e0  mov     eax, 1
0x1800032e5  lock xadd [rcx+14h], eax
0x1800032ea  inc     eax
0x1800032ec  retn
```
