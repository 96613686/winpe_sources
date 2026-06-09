# GetCurrentOutstandingServerThreads

- ea: `0x18000b10c`
- end: `0x18000b14d`
- name: `GetCurrentOutstandingServerThreads`
- size: `65`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `0`
- tags: `installer_update`

## callers

- `0x18000aba0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000b13f`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000b13f`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18000b12c`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18000b12c`

## pseudocode

```c
__int64 GetCurrentOutstandingServerThreads()
{
  unsigned int v0; // ebx

  WaitForMultipleObjectsEx(2u, &qword_1800239B0, 0, 0xFFFFFFFF, 0);
  v0 = ServerInstallThreadTotal;
  ReleaseMutex(qword_1800239B8);
  return v0;
}

```

## disassembly

```asm
0x18000b10c  push    rbx
0x18000b10e  sub     rsp, 30h
0x18000b112  xor     r8d, r8d; bWaitAll
0x18000b115  mov     [rsp+38h+bAlertable], 0; bAlertable
0x18000b11d  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x18000b121  lea     rdx, qword_1800239B0; lpHandles
0x18000b128  lea     ecx, [r8+2]; nCount
0x18000b12c  call    cs:__imp_WaitForMultipleObjectsEx
0x18000b132  mov     rcx, cs:qword_1800239B8; hMutex
0x18000b139  mov     ebx, cs:ServerInstallThreadTotal
0x18000b13f  call    cs:__imp_ReleaseMutex
0x18000b145  mov     eax, ebx
0x18000b147  add     rsp, 30h
0x18000b14b  pop     rbx
0x18000b14c  retn
```
