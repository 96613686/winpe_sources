# THREAD_POOL::BindIoCompletionCallback(void *,void (*)(ulong,ulong,_OVERLAPPED *),ulong)

- ea: `0x180003790`
- end: `0x1800037ba`
- name: `?BindIoCompletionCallback@THREAD_POOL@@QEAAHPEAXP6AXKKPEAU_OVERLAPPED@@@ZK@Z`
- size: `42`
- prototype: `_BOOL8 __fastcall(THREAD_POOL *this, void *, void (*)(unsigned int, unsigned int, struct _OVERLAPPED *))`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180003d50`

## import_xrefs

- `api-ms-win-core-io-l1-1-0!CreateIoCompletionPort` at `0x1800037a5`
- `api-ms-win-core-io-l1-1-0!CreateIoCompletionPort` at `0x1800037a5`

## pseudocode

```c
_BOOL8 __fastcall THREAD_POOL::BindIoCompletionCallback(
        THREAD_POOL *this,
        void *a2,
        void (*a3)(unsigned int, unsigned int, struct _OVERLAPPED *))
{
  return CreateIoCompletionPort(
           a2,
           *(HANDLE *)(*(_QWORD *)this + 8LL),
           (ULONG_PTR)a3,
           *(_DWORD *)(*(_QWORD *)this + 72LL)) != 0;
}

```

## disassembly

```asm
0x180003790  sub     rsp, 28h
0x180003794  mov     rax, rdx
0x180003797  mov     rdx, [rcx]
0x18000379a  mov     rcx, rax; FileHandle
0x18000379d  mov     r9d, [rdx+48h]; NumberOfConcurrentThreads
0x1800037a1  mov     rdx, [rdx+8]; ExistingCompletionPort
0x1800037a5  call    cs:__imp_CreateIoCompletionPort
0x1800037ab  xor     ecx, ecx
0x1800037ad  test    rax, rax
0x1800037b0  setnz   cl
0x1800037b3  mov     eax, ecx
0x1800037b5  add     rsp, 28h
0x1800037b9  retn
```
