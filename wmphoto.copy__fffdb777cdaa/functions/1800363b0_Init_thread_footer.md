# _Init_thread_footer

- ea: `0x1800363b0`
- end: `0x180036410`
- name: `_Init_thread_footer`
- size: `96`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18002af00`

## callees

- `0x180036484`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180036400`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180036400`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800363c0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800363c0`

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
0x1800363b0  push    rbx
0x1800363b2  sub     rsp, 20h
0x1800363b6  mov     rbx, rcx
0x1800363b9  lea     rcx, CriticalSection; lpCriticalSection
0x1800363c0  call    cs:__imp_EnterCriticalSection
0x1800363c6  mov     eax, cs:_Init_global_epoch
0x1800363cc  lea     rcx, CriticalSection; lpCriticalSection
0x1800363d3  mov     edx, cs:_tls_index
0x1800363d9  inc     eax
0x1800363db  mov     cs:_Init_global_epoch, eax
0x1800363e1  mov     [rbx], eax
0x1800363e3  mov     rax, gs:58h
0x1800363ec  mov     r9d, 4
0x1800363f2  mov     r8, [rax+rdx*8]
0x1800363f6  mov     eax, cs:_Init_global_epoch
0x1800363fc  mov     [r9+r8], eax
0x180036400  call    cs:__imp_LeaveCriticalSection
0x180036406  add     rsp, 20h
0x18003640a  pop     rbx
0x18003640b  jmp     _Init_thread_notify
```
