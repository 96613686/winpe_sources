# ThreadPoolPostCompletion(ulong,void (*)(ulong,ulong,_OVERLAPPED *),_OVERLAPPED *)

- ea: `0x180001360`
- end: `0x18000139e`
- name: `?ThreadPoolPostCompletion@@YAHKP6AXKKPEAU_OVERLAPPED@@@Z0@Z`
- size: `62`
- prototype: `__int64 __fastcall(DWORD dwNumberOfBytesTransferred, ULONG_PTR dwCompletionKey, LPOVERLAPPED lpOverlapped)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180001360`
- `0x180001aa0`

## import_xrefs

- `api-ms-win-core-io-l1-1-0!PostQueuedCompletionStatus` at `0x180001383`
- `api-ms-win-core-io-l1-1-0!PostQueuedCompletionStatus` at `0x180001383`

## pseudocode

```c
__int64 __fastcall ThreadPoolPostCompletion(
        DWORD dwNumberOfBytesTransferred,
        void (*dwCompletionKey)(unsigned int, unsigned int, struct _OVERLAPPED *),
        LPOVERLAPPED lpOverlapped)
{
  if ( g_pThreadPool )
    return PostQueuedCompletionStatus(
             *(HANDLE *)(*(_QWORD *)g_pThreadPool + 8LL),
             dwNumberOfBytesTransferred,
             (ULONG_PTR)dwCompletionKey,
             lpOverlapped);
  else
    return Win32ThreadPoolPostCompletion(dwNumberOfBytesTransferred, dwCompletionKey, lpOverlapped);
}

```

## disassembly

```asm
0x180001360  sub     rsp, 28h
0x180001364  mov     rax, cs:?g_pThreadPool@@3PEAVTHREAD_POOL@@EA; THREAD_POOL * g_pThreadPool
0x18000136b  mov     r10d, ecx
0x18000136e  test    rax, rax
0x180001371  jz      short loc_180001397
0x180001373  mov     rcx, [rax]
0x180001376  mov     r9, r8; lpOverlapped
0x180001379  mov     r8, rdx; dwCompletionKey
0x18000137c  mov     edx, r10d; dwNumberOfBytesTransferred
0x18000137f  mov     rcx, [rcx+8]; CompletionPort
0x180001383  call    cs:__imp_PostQueuedCompletionStatus
0x180001389  xor     ecx, ecx
0x18000138b  test    eax, eax
0x18000138d  setnz   cl; unsigned int
0x180001390  mov     eax, ecx
0x180001392  add     rsp, 28h
0x180001396  retn
0x180001397  call    ?Win32ThreadPoolPostCompletion@@YAHKP6AXKKPEAU_OVERLAPPED@@@Z0@Z; Win32ThreadPoolPostCompletion(ulong,void (*)(ulong,ulong,_OVERLAPPED *),_OVERLAPPED *)
0x18000139c  jmp     short loc_180001392
```
