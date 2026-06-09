# ResumeTimersSupported(void)

- ea: `0x180016824`
- end: `0x1800168af`
- name: `?ResumeTimersSupported@@YAHXZ`
- size: `139`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800168b8`

## callees

- `0x180016824`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetWaitableTimer` at `0x180016875`
- `api-ms-win-core-synch-l1-1-0!SetWaitableTimer` at `0x180016875`
- `api-ms-win-core-synch-l1-1-0!CancelWaitableTimer` at `0x18001688e`
- `api-ms-win-core-synch-l1-1-0!CancelWaitableTimer` at `0x18001688e`
- `api-ms-win-core-synch-l1-1-0!CreateWaitableTimerExW` at `0x180016845`
- `api-ms-win-core-synch-l1-1-0!CreateWaitableTimerExW` at `0x180016845`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001687f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001687f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180016897`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180016897`

## pseudocode

```c
HANDLE ResumeTimersSupported(void)
{
  HANDLE result; // rax
  HANDLE v1; // rdi
  BOOL v2; // ebx
  LARGE_INTEGER DueTime; // [rsp+40h] [rbp+8h] BYREF

  result = CreateWaitableTimerExW(0, 0, 1u, 0x1F0003u);
  v1 = result;
  if ( result )
  {
    v2 = 0;
    DueTime.QuadPart = -1;
    if ( SetWaitableTimer(result, &DueTime, 0, 0, 0, 1) )
      v2 = GetLastError() != 50;
    CancelWaitableTimer(v1);
    CloseHandle(v1);
    return (HANDLE)v2;
  }
  return result;
}

```

## disassembly

```asm
0x180016824  mov     [rsp+arg_8], rbx
0x180016829  mov     [rsp+arg_10], rsi
0x18001682e  push    rdi
0x18001682f  sub     rsp, 30h
0x180016833  mov     esi, 1
0x180016838  mov     r9d, 1F0003h; dwDesiredAccess
0x18001683e  mov     r8d, esi; dwFlags
0x180016841  xor     edx, edx; lpTimerName
0x180016843  xor     ecx, ecx; lpTimerAttributes
0x180016845  call    cs:__imp_CreateWaitableTimerExW
0x18001684b  mov     rdi, rax
0x18001684e  test    rax, rax
0x180016851  jz      short loc_18001689F
0x180016853  xor     ebx, ebx
0x180016855  mov     [rsp+38h+fResume], esi; fResume
0x180016859  xor     r9d, r9d; pfnCompletionRoutine
0x18001685c  mov     [rsp+38h+lpArgToCompletionRoutine], rbx; lpArgToCompletionRoutine
0x180016861  xor     r8d, r8d; lPeriod
0x180016864  mov     qword ptr [rsp+38h+DueTime], 0FFFFFFFFFFFFFFFFh
0x18001686d  lea     rdx, [rsp+38h+DueTime]; lpDueTime
0x180016872  mov     rcx, rdi; hTimer
0x180016875  call    cs:__imp_SetWaitableTimer
0x18001687b  test    eax, eax
0x18001687d  jz      short loc_18001688B
0x18001687f  call    cs:__imp_GetLastError
0x180016885  cmp     eax, 32h ; '2'
0x180016888  cmovnz  ebx, esi
0x18001688b  mov     rcx, rdi; hTimer
0x18001688e  call    cs:__imp_CancelWaitableTimer
0x180016894  mov     rcx, rdi; hObject
0x180016897  call    cs:__imp_CloseHandle
0x18001689d  mov     eax, ebx
0x18001689f  mov     rbx, [rsp+38h+arg_8]
0x1800168a4  mov     rsi, [rsp+38h+arg_10]
0x1800168a9  add     rsp, 30h
0x1800168ad  pop     rdi
0x1800168ae  retn
```
