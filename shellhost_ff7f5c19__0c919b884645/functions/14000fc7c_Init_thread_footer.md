# _Init_thread_footer

- ea: `0x14000fc7c`
- end: `0x14000fcdc`
- name: `_Init_thread_footer`
- size: `96`
- prototype: ``
- caller_count: `8`
- callee_count: `1`
- tags: ``

## callers

- `0x1400080f8`
- `0x140020a80`
- `0x140027b80`
- `0x140031810`
- `0x140035bd0`
- `0x14003b360`
- `0x140044360`
- `0x1400584cc`

## callees

- `0x14000fd50`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14000fccc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14000fccc`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14000fc8c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14000fc8c`

## pseudocode

```c
__int64 __fastcall Init_thread_footer(_DWORD *a1)
{
  __int64 v2; // rdx

  EnterCriticalSection(&stru_140082FB0);
  v2 = (unsigned int)tls_index;
  *a1 = ++Init_global_epoch;
  *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + v2) + 4LL) = Init_global_epoch;
  LeaveCriticalSection(&stru_140082FB0);
  return Init_thread_notify();
}

```

## disassembly

```asm
0x14000fc7c  push    rbx
0x14000fc7e  sub     rsp, 20h
0x14000fc82  mov     rbx, rcx
0x14000fc85  lea     rcx, stru_140082FB0; lpCriticalSection
0x14000fc8c  call    cs:__imp_EnterCriticalSection
0x14000fc92  mov     eax, cs:_Init_global_epoch
0x14000fc98  lea     rcx, stru_140082FB0; lpCriticalSection
0x14000fc9f  mov     edx, cs:_tls_index
0x14000fca5  inc     eax
0x14000fca7  mov     cs:_Init_global_epoch, eax
0x14000fcad  mov     [rbx], eax
0x14000fcaf  mov     rax, gs:58h
0x14000fcb8  mov     r9d, 4
0x14000fcbe  mov     r8, [rax+rdx*8]
0x14000fcc2  mov     eax, cs:_Init_global_epoch
0x14000fcc8  mov     [r9+r8], eax
0x14000fccc  call    cs:__imp_LeaveCriticalSection
0x14000fcd2  add     rsp, 20h
0x14000fcd6  pop     rbx
0x14000fcd7  jmp     _Init_thread_notify
```
