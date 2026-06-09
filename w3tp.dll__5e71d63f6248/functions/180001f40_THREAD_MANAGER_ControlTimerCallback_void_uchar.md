# THREAD_MANAGER::ControlTimerCallback(void *,uchar)

- ea: `0x180001f40`
- end: `0x180001f45`
- name: `?ControlTimerCallback@THREAD_MANAGER@@CAXPEAXE@Z`
- size: `5`
- prototype: `void __stdcall(PVOID, BOOLEAN)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180001450`

## pseudocode

```c
// attributes: thunk
void __fastcall THREAD_MANAGER::ControlTimerCallback(THREAD_MANAGER *a1)
{
  THREAD_MANAGER::DetermineThreadAction(a1);
}

```

## disassembly

```asm
0x180001f40  jmp     ?DetermineThreadAction@THREAD_MANAGER@@AEAAXXZ; THREAD_MANAGER::DetermineThreadAction(void)
```
