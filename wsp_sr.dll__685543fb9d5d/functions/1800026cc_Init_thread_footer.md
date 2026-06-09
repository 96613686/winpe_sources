# _Init_thread_footer

- ea: `0x1800026cc`
- end: `0x18000272c`
- name: `_Init_thread_footer`
- size: `96`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18001881c`

## callees

- `0x1800027a0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800026dc`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800026dc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000271c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000271c`

## pseudocode

```c
int __fastcall Init_thread_footer(_DWORD *a1)
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
0x1800026cc  push    rbx
0x1800026ce  sub     rsp, 20h
0x1800026d2  mov     rbx, rcx
0x1800026d5  lea     rcx, CriticalSection; lpCriticalSection
0x1800026dc  call    cs:__imp_EnterCriticalSection
0x1800026e2  mov     eax, cs:_Init_global_epoch
0x1800026e8  lea     rcx, CriticalSection; lpCriticalSection
0x1800026ef  mov     edx, cs:_tls_index
0x1800026f5  inc     eax
0x1800026f7  mov     cs:_Init_global_epoch, eax
0x1800026fd  mov     [rbx], eax
0x1800026ff  mov     rax, gs:58h
0x180002708  mov     r9d, 4
0x18000270e  mov     r8, [rax+rdx*8]
0x180002712  mov     eax, cs:_Init_global_epoch
0x180002718  mov     [r9+r8], eax
0x18000271c  call    cs:__imp_LeaveCriticalSection
0x180002722  add     rsp, 20h
0x180002726  pop     rbx
0x180002727  jmp     _Init_thread_notify
```
