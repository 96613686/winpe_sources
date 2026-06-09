# CWpnIdleTaskHandler::AddRef(void)

- ea: `0x180006050`
- end: `0x18000605d`
- name: `?AddRef@CWpnIdleTaskHandler@@UEAAKXZ`
- size: `13`
- prototype: `unsigned int __fastcall(CWpnIdleTaskHandler *__hidden this)`
- caller_count: `0`
- callee_count: `0`
- tags: `loader_planting, service_task`

## pseudocode

```c
__int64 __fastcall CWpnIdleTaskHandler::AddRef(CWpnIdleTaskHandler *this)
{
  return (unsigned int)_InterlockedIncrement((volatile signed __int32 *)this + 2);
}

```

## disassembly

```asm
0x180006050  mov     eax, 1
0x180006055  lock xadd [rcx+8], eax
0x18000605a  inc     eax
0x18000605c  retn
```
