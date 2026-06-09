# EcTerminateService(void)

- ea: `0x1800025a4`
- end: `0x1800025b5`
- name: `?EcTerminateService@@YAXXZ`
- size: `17`
- prototype: `void __noreturn(void)`
- caller_count: `6`
- callee_count: `0`
- tags: `service_task`

## callers

- `0x1800202d5`
- `0x1800203e8`
- `0x1800204a3`
- `0x180021bbc`
- `0x180021e3f`
- `0x180022031`

## import_xrefs

- `msvcrt!abort` at `0x1800025ae`
- `msvcrt!abort` at `0x1800025ae`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800025a8`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800025a8`

## pseudocode

```c
void __noreturn EcTerminateService(void)
{
  DebugBreak();
  abort();
}

```

## disassembly

```asm
0x1800025a4  sub     rsp, 28h
0x1800025a8  call    cs:__imp_DebugBreak
0x1800025ae  call    cs:__imp_abort
```
