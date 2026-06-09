# _Init_thread_abort

- ea: `0x180002690`
- end: `0x1800026c3`
- name: `_Init_thread_abort`
- size: `51`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18002bbb4`

## callees

- `0x1800027a0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800026a0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800026a0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800026b3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800026b3`

## pseudocode

```c
int __fastcall Init_thread_abort(_DWORD *a1)
{
  EnterCriticalSection(&CriticalSection);
  *a1 = 0;
  LeaveCriticalSection(&CriticalSection);
  return Init_thread_notify();
}

```

## disassembly

```asm
0x180002690  push    rbx
0x180002692  sub     rsp, 20h
0x180002696  mov     rbx, rcx
0x180002699  lea     rcx, CriticalSection; lpCriticalSection
0x1800026a0  call    cs:__imp_EnterCriticalSection
0x1800026a6  lea     rcx, CriticalSection; lpCriticalSection
0x1800026ad  mov     dword ptr [rbx], 0
0x1800026b3  call    cs:__imp_LeaveCriticalSection
0x1800026b9  add     rsp, 20h
0x1800026bd  pop     rbx
0x1800026be  jmp     _Init_thread_notify
```
