# _Init_thread_footer

- ea: `0x180036980`
- end: `0x1800369e0`
- name: `_Init_thread_footer`
- size: `96`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18002b180`

## callees

- `0x180036a54`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800369d0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800369d0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180036990`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180036990`

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
0x180036980  push    rbx
0x180036982  sub     rsp, 20h
0x180036986  mov     rbx, rcx
0x180036989  lea     rcx, CriticalSection; lpCriticalSection
0x180036990  call    cs:__imp_EnterCriticalSection
0x180036996  mov     eax, cs:_Init_global_epoch
0x18003699c  lea     rcx, CriticalSection; lpCriticalSection
0x1800369a3  mov     edx, cs:_tls_index
0x1800369a9  inc     eax
0x1800369ab  mov     cs:_Init_global_epoch, eax
0x1800369b1  mov     [rbx], eax
0x1800369b3  mov     rax, gs:58h
0x1800369bc  mov     r9d, 4
0x1800369c2  mov     r8, [rax+rdx*8]
0x1800369c6  mov     eax, cs:_Init_global_epoch
0x1800369cc  mov     [r9+r8], eax
0x1800369d0  call    cs:__imp_LeaveCriticalSection
0x1800369d6  add     rsp, 20h
0x1800369da  pop     rbx
0x1800369db  jmp     _Init_thread_notify
```
