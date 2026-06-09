# _Init_thread_footer

- ea: `0x18000269c`
- end: `0x1800026fc`
- name: `_Init_thread_footer`
- size: `96`
- prototype: `__int64 __fastcall(_DWORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180018934`

## callees

- `0x180002770`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800026ac`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800026ac`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800026ec`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800026ec`

## pseudocode

```c
__int64 __fastcall Init_thread_footer(_DWORD *a1)
{
  __int64 v2; // rdx

  EnterCriticalSection(&CriticalSection);
  v2 = (unsigned int)tls_index;
  *a1 = ++Init_global_epoch;
  *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + v2) + 4LL) = Init_global_epoch;
  LeaveCriticalSection(&CriticalSection);
  return Init_thread_notify();
}

```

## disassembly

```asm
0x18000269c  push    rbx
0x18000269e  sub     rsp, 20h
0x1800026a2  mov     rbx, rcx
0x1800026a5  lea     rcx, CriticalSection; lpCriticalSection
0x1800026ac  call    cs:__imp_EnterCriticalSection
0x1800026b2  mov     eax, cs:_Init_global_epoch
0x1800026b8  lea     rcx, CriticalSection; lpCriticalSection
0x1800026bf  mov     edx, cs:_tls_index
0x1800026c5  inc     eax
0x1800026c7  mov     cs:_Init_global_epoch, eax
0x1800026cd  mov     [rbx], eax
0x1800026cf  mov     rax, gs:58h
0x1800026d8  mov     r9d, 4
0x1800026de  mov     r8, [rax+rdx*8]
0x1800026e2  mov     eax, cs:_Init_global_epoch
0x1800026e8  mov     [r9+r8], eax
0x1800026ec  call    cs:__imp_LeaveCriticalSection
0x1800026f2  add     rsp, 20h
0x1800026f6  pop     rbx
0x1800026f7  jmp     _Init_thread_notify
```
