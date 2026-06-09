# TiLock

- ea: `0x14000b78c`
- end: `0x14000b7a9`
- name: `TiLock`
- size: `29`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x140002a7c`
- `0x140002c9c`

## import_xrefs

- `ntoskrnl!KeAcquireGuardedMutex` at `0x14000b797`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x14000b797`

## pseudocode

```c
void TiLock()
{
  KeAcquireGuardedMutex((PKGUARDED_MUTEX)&WPP_MAIN_CB.DeviceQueue.DeviceListHead.Blink);
}

```

## disassembly

```asm
0x14000b78c  sub     rsp, 28h
0x14000b790  lea     rcx, WPP_MAIN_CB.DeviceQueue.DeviceListHead.Blink; Mutex
0x14000b797  call    cs:__imp_KeAcquireGuardedMutex
0x14000b79e  nop     dword ptr [rax+rax+00h]
0x14000b7a3  add     rsp, 28h
0x14000b7a7  retn
```
