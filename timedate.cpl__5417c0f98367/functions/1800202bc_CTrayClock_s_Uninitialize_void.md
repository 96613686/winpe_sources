# CTrayClock::s_Uninitialize(void)

- ea: `0x1800202bc`
- end: `0x1800202dd`
- name: `?s_Uninitialize@CTrayClock@@CAXXZ`
- size: `33`
- prototype: `void(void)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x18001f3f4`
- `0x18001f928`
- `0x1800201d0`

## callees

- `0x1800043bc`

## import_xrefs

- `DUI70!UnInitThread` at `0x1800202c5`
- `DUI70!UnInitThread` at `0x1800202c5`
- `DUI70!UnInitProcessPriv` at `0x1800202d6`

## pseudocode

```c
void CTrayClock::s_Uninitialize(void)
{
  KillClockSync();
  UnInitThread();
  UnInitProcessPriv(&_ImageBase);
}

```

## disassembly

```asm
0x1800202bc  sub     rsp, 28h
0x1800202c0  call    ?KillClockSync@@YAXXZ; KillClockSync(void)
0x1800202c5  call    cs:__imp_UnInitThread
0x1800202cb  lea     rcx, __ImageBase
0x1800202d2  add     rsp, 28h
0x1800202d6  jmp     cs:__imp_UnInitProcessPriv
```
