# THREAD_POOL::PostCompletion(ulong,void (*)(ulong,ulong,_OVERLAPPED *),_OVERLAPPED *)

- ea: `0x180001420`
- end: `0x18000143f`
- name: `?PostCompletion@THREAD_POOL@@QEAAHKP6AXKKPEAU_OVERLAPPED@@@Z0@Z`
- size: `31`
- prototype: `_BOOL8 __fastcall(THREAD_POOL *this, DWORD, void (*)(unsigned int, unsigned int, struct _OVERLAPPED *), struct _OVERLAPPED *)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180002bc0`

## import_xrefs

- `api-ms-win-core-io-l1-1-0!PostQueuedCompletionStatus` at `0x18000142b`
- `api-ms-win-core-io-l1-1-0!PostQueuedCompletionStatus` at `0x18000142b`

## pseudocode

```c
_BOOL8 __fastcall THREAD_POOL::PostCompletion(
        THREAD_POOL *this,
        DWORD a2,
        void (*a3)(unsigned int, unsigned int, struct _OVERLAPPED *),
        struct _OVERLAPPED *a4)
{
  return PostQueuedCompletionStatus(*(HANDLE *)(*(_QWORD *)this + 8LL), a2, (ULONG_PTR)a3, a4);
}

```

## disassembly

```asm
0x180001420  sub     rsp, 28h
0x180001424  mov     rcx, [rcx]
0x180001427  mov     rcx, [rcx+8]; CompletionPort
0x18000142b  call    cs:__imp_PostQueuedCompletionStatus
0x180001431  xor     ecx, ecx
0x180001433  test    eax, eax
0x180001435  setnz   cl
0x180001438  mov     eax, ecx
0x18000143a  add     rsp, 28h
0x18000143e  retn
```
