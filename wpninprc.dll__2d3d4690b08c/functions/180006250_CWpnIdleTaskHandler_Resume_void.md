# CWpnIdleTaskHandler::Resume(void)

- ea: `0x180006250`
- end: `0x180006256`
- name: `?Resume@CWpnIdleTaskHandler@@UEAAJXZ`
- size: `6`
- prototype: `__int64 __fastcall(CWpnIdleTaskHandler *__hidden this)`
- caller_count: `0`
- callee_count: `0`
- tags: `loader_planting, service_task`

## pseudocode

```c
__int64 __fastcall CWpnIdleTaskHandler::Resume(CWpnIdleTaskHandler *this)
{
  return 2147500033LL;
}

```

## disassembly

```asm
0x180006250  mov     eax, 80004001h
0x180006255  retn
```
