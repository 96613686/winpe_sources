# TiUnlock

- ea: `0x14000b7b0`
- end: `0x14000b7cd`
- name: `TiUnlock`
- size: `29`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x140002a7c`
- `0x140002c9c`

## import_xrefs

- `ntoskrnl!KeReleaseGuardedMutex` at `0x14000b7bb`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x14000b7bb`

## pseudocode

```c
void TiUnlock()
{
  KeReleaseGuardedMutex((PKGUARDED_MUTEX)&WPP_MAIN_CB.DeviceQueue.DeviceListHead.Blink);
}

```

## disassembly

```asm
0x14000b7b0  sub     rsp, 28h
0x14000b7b4  lea     rcx, WPP_MAIN_CB.DeviceQueue.DeviceListHead.Blink; Mutex
0x14000b7bb  call    cs:__imp_KeReleaseGuardedMutex
0x14000b7c2  nop     dword ptr [rax+rax+00h]
0x14000b7c7  add     rsp, 28h
0x14000b7cb  retn
```
