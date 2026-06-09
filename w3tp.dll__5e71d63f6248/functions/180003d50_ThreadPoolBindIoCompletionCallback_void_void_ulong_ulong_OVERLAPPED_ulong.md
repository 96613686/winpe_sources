# ThreadPoolBindIoCompletionCallback(void *,void (*)(ulong,ulong,_OVERLAPPED *),ulong)

- ea: `0x180003d50`
- end: `0x180003d77`
- name: `?ThreadPoolBindIoCompletionCallback@@YAHPEAXP6AXKKPEAU_OVERLAPPED@@@ZK@Z`
- size: `39`
- prototype: `__int64 __fastcall(void *, void (*)(unsigned int, unsigned int, struct _OVERLAPPED *), unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180003790`
- `0x180003d50`

## import_xrefs

- `api-ms-win-core-kernel32-legacy-l1-1-0!BindIoCompletionCallback` at `0x180003d70`

## pseudocode

```c
BOOL __fastcall ThreadPoolBindIoCompletionCallback(
        void *a1,
        void (*a2)(unsigned int, unsigned int, struct _OVERLAPPED *),
        ULONG a3)
{
  if ( g_pThreadPool )
    return THREAD_POOL::BindIoCompletionCallback(g_pThreadPool, a1, a2);
  else
    return BindIoCompletionCallback(a1, a2, a3);
}

```

## disassembly

```asm
0x180003d50  mov     rax, rcx
0x180003d53  mov     rcx, cs:?g_pThreadPool@@3PEAVTHREAD_POOL@@EA; this
0x180003d5a  test    rcx, rcx
0x180003d5d  jz      short loc_180003D6D
0x180003d5f  mov     r9d, r8d; unsigned int
0x180003d62  mov     r8, rdx; void (*)(unsigned int, unsigned int, struct _OVERLAPPED *)
0x180003d65  mov     rdx, rax; void *
0x180003d68  jmp     ?BindIoCompletionCallback@THREAD_POOL@@QEAAHPEAXP6AXKKPEAU_OVERLAPPED@@@ZK@Z; THREAD_POOL::BindIoCompletionCallback(void *,void (*)(ulong,ulong,_OVERLAPPED *),ulong)
0x180003d6d  mov     rcx, rax
0x180003d70  jmp     cs:__imp_BindIoCompletionCallback
```
