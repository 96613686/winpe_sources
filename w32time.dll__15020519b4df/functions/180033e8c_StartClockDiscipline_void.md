# StartClockDiscipline(void)

- ea: `0x180033e8c`
- end: `0x180033f2f`
- name: `?StartClockDiscipline@@YAJXZ`
- size: `163`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180039100`

## callees

- `0x180033e8c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x180033f16`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x180033f16`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033ed3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033ed3`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180033eb8`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180033eb8`

## pseudocode

```c
signed int StartClockDiscipline(void)
{
  signed int result; // eax
  HANDLE Handles[3]; // [rsp+30h] [rbp-18h] BYREF
  DWORD ThreadId; // [rsp+50h] [rbp+8h] BYREF

  ThreadId = 0;
  hThread = CreateThread(0, 0, (LPTHREAD_START_ROUTINE)ClockDisciplineThread, 0, 0, &ThreadId);
  if ( hThread )
  {
    Handles[1] = hThread;
    Handles[0] = qword_1800A36D8;
    if ( WaitForMultipleObjectsEx(2u, Handles, 0, 0xFFFFFFFF, 0) != -1 )
      return 0;
  }
  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x180033e8c  sub     rsp, 48h
0x180033e90  lea     rax, [rsp+48h+ThreadId]
0x180033e95  mov     [rsp+48h+ThreadId], 0
0x180033e9d  mov     [rsp+48h+lpThreadId], rax; lpThreadId
0x180033ea2  lea     r8, ?ClockDisciplineThread@@YAKPEAX@Z; lpStartAddress
0x180033ea9  xor     r9d, r9d; lpParameter
0x180033eac  mov     [rsp+48h+dwCreationFlags], 0; dwCreationFlags
0x180033eb4  xor     edx, edx; dwStackSize
0x180033eb6  xor     ecx, ecx; lpThreadAttributes
0x180033eb8  call    cs:__imp_CreateThread
0x180033ebf  nop     dword ptr [rax+rax+00h]
0x180033ec4  mov     cs:hThread, rax
0x180033ecb  mov     rcx, rax
0x180033ece  test    rax, rax
0x180033ed1  jnz     short loc_180033EED
0x180033ed3  call    cs:__imp_GetLastError
0x180033eda  nop     dword ptr [rax+rax+00h]
0x180033edf  test    eax, eax
0x180033ee1  jle     short loc_180033F29
0x180033ee3  movzx   eax, ax
0x180033ee6  or      eax, 80070000h
0x180033eeb  jmp     short loc_180033F29
0x180033eed  mov     rax, cs:qword_1800A36D8
0x180033ef4  lea     rdx, [rsp+48h+Handles]; lpHandles
0x180033ef9  xor     r8d, r8d; bWaitAll
0x180033efc  mov     [rsp+48h+var_10], rcx
0x180033f01  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x180033f05  mov     [rsp+48h+Handles], rax
0x180033f0a  mov     [rsp+48h+dwCreationFlags], 0; bAlertable
0x180033f12  lea     ecx, [r8+2]; nCount
0x180033f16  call    cs:__imp_WaitForMultipleObjectsEx
0x180033f1d  nop     dword ptr [rax+rax+00h]
0x180033f22  cmp     eax, 0FFFFFFFFh
0x180033f25  jz      short loc_180033ED3
0x180033f27  xor     eax, eax
0x180033f29  add     rsp, 48h
0x180033f2d  retn
```
