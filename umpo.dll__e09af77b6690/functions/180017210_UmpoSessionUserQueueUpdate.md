# UmpoSessionUserQueueUpdate

- ea: `0x180017210`
- end: `0x180017283`
- name: `UmpoSessionUserQueueUpdate`
- size: `115`
- prototype: `BOOL __fastcall(int, size_t, const void *)`
- caller_count: `1`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x18000c4a0`

## callees

- `0x1800188c8`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180017260`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180017260`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180017231`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180017231`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001727c`

## pseudocode

```c
BOOL __fastcall UmpoSessionUserQueueUpdate(int a1, size_t a2, const void *a3)
{
  WaitForSingleObject(hHandle, 0xFFFFFFFF);
  dword_180024848 = a1;
  memcpy_0(qword_180024860, a3, a2);
  SetThreadpoolWait(UmpoSessionUserWork, qword_180024850, 0);
  return SetEvent(qword_180024850);
}

```

## disassembly

```asm
0x180017210  mov     [rsp+arg_0], rbx
0x180017215  mov     [rsp+arg_8], rsi
0x18001721a  push    rdi
0x18001721b  sub     rsp, 20h
0x18001721f  mov     rdi, rdx
0x180017222  mov     ebx, ecx
0x180017224  mov     rcx, cs:hHandle; hHandle
0x18001722b  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18001722e  mov     rsi, r8
0x180017231  call    cs:__imp_WaitForSingleObject
0x180017237  mov     r8, rdi; Size
0x18001723a  mov     cs:dword_180024848, ebx
0x180017240  mov     rdx, rsi; Src
0x180017243  lea     rcx, qword_180024860; void *
0x18001724a  call    memcpy_0
0x18001724f  mov     rdx, cs:qword_180024850; h
0x180017256  xor     r8d, r8d; pftTimeout
0x180017259  mov     rcx, cs:UmpoSessionUserWork; pwa
0x180017260  call    cs:__imp_SetThreadpoolWait
0x180017266  mov     rcx, cs:qword_180024850
0x18001726d  mov     rbx, [rsp+28h+arg_0]
0x180017272  mov     rsi, [rsp+28h+arg_8]
0x180017277  add     rsp, 20h
0x18001727b  pop     rdi
0x18001727c  jmp     cs:__imp_SetEvent
```
