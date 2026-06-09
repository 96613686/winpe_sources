# _Init_thread_abort

- ea: `0x180002660`
- end: `0x180002693`
- name: `_Init_thread_abort`
- size: `51`
- prototype: `__int64 __fastcall(_DWORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18002b6ce`

## callees

- `0x180002770`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002670`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002670`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002683`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002683`

## pseudocode

```c
__int64 __fastcall Init_thread_abort(_DWORD *a1)
{
  EnterCriticalSection(&CriticalSection);
  *a1 = 0;
  LeaveCriticalSection(&CriticalSection);
  return Init_thread_notify();
}

```

## disassembly

```asm
0x180002660  push    rbx
0x180002662  sub     rsp, 20h
0x180002666  mov     rbx, rcx
0x180002669  lea     rcx, CriticalSection; lpCriticalSection
0x180002670  call    cs:__imp_EnterCriticalSection
0x180002676  lea     rcx, CriticalSection; lpCriticalSection
0x18000267d  mov     dword ptr [rbx], 0
0x180002683  call    cs:__imp_LeaveCriticalSection
0x180002689  add     rsp, 20h
0x18000268d  pop     rbx
0x18000268e  jmp     _Init_thread_notify
```
