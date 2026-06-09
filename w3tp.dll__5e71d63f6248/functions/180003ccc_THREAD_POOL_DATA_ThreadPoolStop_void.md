# THREAD_POOL_DATA::ThreadPoolStop(void *)

- ea: `0x180003ccc`
- end: `0x180003cf7`
- name: `?ThreadPoolStop@THREAD_POOL_DATA@@SAXPEAX@Z`
- size: `43`
- prototype: `void __fastcall(void *)`
- caller_count: `2`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180002c34`
- `0x180003310`

## import_xrefs

- `api-ms-win-core-io-l1-1-0!PostQueuedCompletionStatus` at `0x180003cec`
- `api-ms-win-core-io-l1-1-0!PostQueuedCompletionStatus` at `0x180003cec`

## pseudocode

```c
void __fastcall THREAD_POOL_DATA::ThreadPoolStop(_QWORD *a1)
{
  void *v1; // rcx
  struct _OVERLAPPED Overlapped; // [rsp+20h] [rbp-28h] BYREF

  v1 = (void *)a1[1];
  memset(&Overlapped, 0, sizeof(Overlapped));
  PostQueuedCompletionStatus(v1, 0, 0xFFFFFFFFFFFFFFFFuLL, &Overlapped);
}

```

## disassembly

```asm
0x180003ccc  sub     rsp, 48h
0x180003cd0  mov     rcx, [rcx+8]; CompletionPort
0x180003cd4  lea     r9, [rsp+48h+Overlapped]; lpOverlapped
0x180003cd9  xorps   xmm0, xmm0
0x180003cdc  or      r8, 0FFFFFFFFFFFFFFFFh; dwCompletionKey
0x180003ce0  xor     edx, edx; dwNumberOfBytesTransferred
0x180003ce2  movups  xmmword ptr [rsp+48h+Overlapped.Internal], xmm0
0x180003ce7  movups  xmmword ptr [rsp+48h+Overlapped.10h], xmm0
0x180003cec  call    cs:__imp_PostQueuedCompletionStatus
0x180003cf2  add     rsp, 48h
0x180003cf6  retn
```
