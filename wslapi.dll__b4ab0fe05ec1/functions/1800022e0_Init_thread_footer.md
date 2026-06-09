# _Init_thread_footer

- ea: `0x1800022e0`
- end: `0x180002340`
- name: `_Init_thread_footer`
- size: `96`
- prototype: `__int64 __fastcall(_DWORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800065f0`

## callees

- `0x1800023b4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002330`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002330`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800022f0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800022f0`

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
0x1800022e0  push    rbx
0x1800022e2  sub     rsp, 20h
0x1800022e6  mov     rbx, rcx
0x1800022e9  lea     rcx, CriticalSection; lpCriticalSection
0x1800022f0  call    cs:__imp_EnterCriticalSection
0x1800022f6  mov     eax, cs:_Init_global_epoch
0x1800022fc  lea     rcx, CriticalSection; lpCriticalSection
0x180002303  mov     edx, cs:_tls_index
0x180002309  inc     eax
0x18000230b  mov     cs:_Init_global_epoch, eax
0x180002311  mov     [rbx], eax
0x180002313  mov     rax, gs:58h
0x18000231c  mov     r9d, 4
0x180002322  mov     r8, [rax+rdx*8]
0x180002326  mov     eax, cs:_Init_global_epoch
0x18000232c  mov     [r9+r8], eax
0x180002330  call    cs:__imp_LeaveCriticalSection
0x180002336  add     rsp, 20h
0x18000233a  pop     rbx
0x18000233b  jmp     _Init_thread_notify
```
