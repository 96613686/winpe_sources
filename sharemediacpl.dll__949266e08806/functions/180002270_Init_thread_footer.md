# _Init_thread_footer

- ea: `0x180002270`
- end: `0x1800022d0`
- name: `_Init_thread_footer`
- size: `96`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180012be0`

## callees

- `0x180002344`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x1800022c0`
- `KERNEL32!LeaveCriticalSection` at `0x1800022c0`
- `KERNEL32!EnterCriticalSection` at `0x180002280`
- `KERNEL32!EnterCriticalSection` at `0x180002280`

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
0x180002270  push    rbx
0x180002272  sub     rsp, 20h
0x180002276  mov     rbx, rcx
0x180002279  lea     rcx, CriticalSection; lpCriticalSection
0x180002280  call    cs:__imp_EnterCriticalSection
0x180002286  mov     eax, cs:_Init_global_epoch
0x18000228c  lea     rcx, CriticalSection; lpCriticalSection
0x180002293  mov     edx, cs:_tls_index
0x180002299  inc     eax
0x18000229b  mov     cs:_Init_global_epoch, eax
0x1800022a1  mov     [rbx], eax
0x1800022a3  mov     rax, gs:58h
0x1800022ac  mov     r9d, 4
0x1800022b2  mov     r8, [rax+rdx*8]
0x1800022b6  mov     eax, cs:_Init_global_epoch
0x1800022bc  mov     [r9+r8], eax
0x1800022c0  call    cs:__imp_LeaveCriticalSection
0x1800022c6  add     rsp, 20h
0x1800022ca  pop     rbx
0x1800022cb  jmp     _Init_thread_notify
```
