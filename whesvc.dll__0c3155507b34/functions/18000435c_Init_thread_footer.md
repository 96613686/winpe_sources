# _Init_thread_footer

- ea: `0x18000435c`
- end: `0x1800043bc`
- name: `_Init_thread_footer`
- size: `96`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x18000ba38`
- `0x18000f410`
- `0x1800142e0`
- `0x18001c32c`

## callees

- `0x180004430`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000436c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000436c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800043ac`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800043ac`

## pseudocode

```c
__int64 __fastcall Init_thread_footer(_DWORD *a1)
{
  __int64 v2; // rdx

  EnterCriticalSection(&stru_180034808);
  v2 = (unsigned int)tls_index;
  *a1 = ++Init_global_epoch;
  *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + v2) + 4LL) = Init_global_epoch;
  LeaveCriticalSection(&stru_180034808);
  return Init_thread_notify();
}

```

## disassembly

```asm
0x18000435c  push    rbx
0x18000435e  sub     rsp, 20h
0x180004362  mov     rbx, rcx
0x180004365  lea     rcx, stru_180034808; lpCriticalSection
0x18000436c  call    cs:__imp_EnterCriticalSection
0x180004372  mov     eax, cs:_Init_global_epoch
0x180004378  lea     rcx, stru_180034808; lpCriticalSection
0x18000437f  mov     edx, cs:_tls_index
0x180004385  inc     eax
0x180004387  mov     cs:_Init_global_epoch, eax
0x18000438d  mov     [rbx], eax
0x18000438f  mov     rax, gs:58h
0x180004398  mov     r9d, 4
0x18000439e  mov     r8, [rax+rdx*8]
0x1800043a2  mov     eax, cs:_Init_global_epoch
0x1800043a8  mov     [r9+r8], eax
0x1800043ac  call    cs:__imp_LeaveCriticalSection
0x1800043b2  add     rsp, 20h
0x1800043b6  pop     rbx
0x1800043b7  jmp     _Init_thread_notify
```
