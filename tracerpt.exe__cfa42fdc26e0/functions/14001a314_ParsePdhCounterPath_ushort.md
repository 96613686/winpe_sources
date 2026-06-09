# ParsePdhCounterPath(ushort *)

- ea: `0x14001a314`
- end: `0x14001a3a1`
- name: `?ParsePdhCounterPath@@YAPEAU_PDH_COUNTER_PATH_ELEMENTS_W@@PEAG@Z`
- size: `141`
- prototype: `struct _PDH_COUNTER_PATH_ELEMENTS_W *__fastcall(LPCWSTR szFullPathBuffer)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x14001a760`
- `0x14001ac30`

## callees

- `0x14001a314`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14001a38b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14001a38b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14001a342`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14001a37d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14001a342`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14001a37d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14001a353`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14001a353`
- `pdh!PdhParseCounterPathW` at `0x14001a331`
- `pdh!PdhParseCounterPathW` at `0x14001a373`
- `pdh!PdhParseCounterPathW` at `0x14001a331`
- `pdh!PdhParseCounterPathW` at `0x14001a373`

## pseudocode

```c
struct _PDH_COUNTER_PATH_ELEMENTS_W *__fastcall ParsePdhCounterPath(LPCWSTR szFullPathBuffer)
{
  struct _PDH_COUNTER_PATH_ELEMENTS_W *v1; // rbx
  DWORD v3; // ebx
  HANDLE ProcessHeap; // rax
  struct _PDH_COUNTER_PATH_ELEMENTS_W *v5; // rax
  HANDLE v7; // rax
  DWORD pdwBufferSize; // [rsp+38h] [rbp+10h] BYREF

  v1 = 0;
  pdwBufferSize = 0;
  if ( PdhParseCounterPathW(szFullPathBuffer, 0, &pdwBufferSize, 0) == -2147481646 )
  {
    v3 = pdwBufferSize;
    ProcessHeap = GetProcessHeap();
    v5 = (struct _PDH_COUNTER_PATH_ELEMENTS_W *)HeapAlloc(ProcessHeap, 8u, v3);
    v1 = v5;
    if ( !v5 )
      return 0;
    if ( PdhParseCounterPathW(szFullPathBuffer, v5, &pdwBufferSize, 0) )
    {
      v7 = GetProcessHeap();
      HeapFree(v7, 0, v1);
      return 0;
    }
  }
  return v1;
}

```

## disassembly

```asm
0x14001a314  mov     [rsp+arg_0], rbx
0x14001a319  push    rdi
0x14001a31a  sub     rsp, 20h
0x14001a31e  xor     ebx, ebx
0x14001a320  lea     r8, [rsp+28h+pdwBufferSize]; pdwBufferSize
0x14001a325  xor     r9d, r9d; dwFlags
0x14001a328  mov     [rsp+28h+pdwBufferSize], ebx
0x14001a32c  xor     edx, edx; pCounterPathElements
0x14001a32e  mov     rdi, rcx
0x14001a331  call    cs:__imp_PdhParseCounterPathW
0x14001a337  cmp     eax, 800007D2h
0x14001a33c  jnz     short loc_14001A393
0x14001a33e  mov     ebx, [rsp+28h+pdwBufferSize]
0x14001a342  call    cs:__imp_GetProcessHeap
0x14001a348  mov     r8d, ebx; dwBytes
0x14001a34b  mov     edx, 8; dwFlags
0x14001a350  mov     rcx, rax; hHeap
0x14001a353  call    cs:__imp_HeapAlloc
0x14001a359  mov     rbx, rax
0x14001a35c  test    rax, rax
0x14001a35f  jnz     short loc_14001A365
0x14001a361  xor     eax, eax
0x14001a363  jmp     short loc_14001A396
0x14001a365  xor     r9d, r9d; dwFlags
0x14001a368  lea     r8, [rsp+28h+pdwBufferSize]; pdwBufferSize
0x14001a36d  mov     rdx, rbx; pCounterPathElements
0x14001a370  mov     rcx, rdi; szFullPathBuffer
0x14001a373  call    cs:__imp_PdhParseCounterPathW
0x14001a379  test    eax, eax
0x14001a37b  jz      short loc_14001A393
0x14001a37d  call    cs:__imp_GetProcessHeap
0x14001a383  mov     r8, rbx; lpMem
0x14001a386  xor     edx, edx; dwFlags
0x14001a388  mov     rcx, rax; hHeap
0x14001a38b  call    cs:__imp_HeapFree
0x14001a391  jmp     short loc_14001A361
0x14001a393  mov     rax, rbx
0x14001a396  mov     rbx, [rsp+28h+arg_0]
0x14001a39b  add     rsp, 20h
0x14001a39f  pop     rdi
0x14001a3a0  retn
```
