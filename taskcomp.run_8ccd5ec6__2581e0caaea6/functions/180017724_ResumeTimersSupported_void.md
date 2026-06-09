# ResumeTimersSupported(void)

- ea: `0x180017724`
- end: `0x1800177ce`
- name: `?ResumeTimersSupported@@YAHXZ`
- size: `170`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800177d4`

## callees

- `0x180017724`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetWaitableTimer` at `0x18001777b`
- `api-ms-win-core-synch-l1-1-0!SetWaitableTimer` at `0x18001777b`
- `api-ms-win-core-synch-l1-1-0!CancelWaitableTimer` at `0x1800177a0`
- `api-ms-win-core-synch-l1-1-0!CancelWaitableTimer` at `0x1800177a0`
- `api-ms-win-core-synch-l1-1-0!CreateWaitableTimerExW` at `0x180017745`
- `api-ms-win-core-synch-l1-1-0!CreateWaitableTimerExW` at `0x180017745`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001778b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001778b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800177af`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800177af`

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
0x180017724  mov     [rsp+arg_8], rbx
0x180017729  mov     [rsp+arg_10], rsi
0x18001772e  push    rdi
0x18001772f  sub     rsp, 30h
0x180017733  mov     esi, 1
0x180017738  mov     r9d, 1F0003h; dwDesiredAccess
0x18001773e  mov     r8d, esi; dwFlags
0x180017741  xor     edx, edx; lpTimerName
0x180017743  xor     ecx, ecx; lpTimerAttributes
0x180017745  call    cs:__imp_CreateWaitableTimerExW
0x18001774c  nop     dword ptr [rax+rax+00h]
0x180017751  mov     rdi, rax
0x180017754  test    rax, rax
0x180017757  jz      short loc_1800177BD
0x180017759  xor     ebx, ebx
0x18001775b  mov     [rsp+38h+fResume], esi; fResume
0x18001775f  xor     r9d, r9d; pfnCompletionRoutine
0x180017762  mov     [rsp+38h+lpArgToCompletionRoutine], rbx; lpArgToCompletionRoutine
0x180017767  xor     r8d, r8d; lPeriod
0x18001776a  mov     qword ptr [rsp+38h+DueTime], 0FFFFFFFFFFFFFFFFh
0x180017773  lea     rdx, [rsp+38h+DueTime]; lpDueTime
0x180017778  mov     rcx, rdi; hTimer
0x18001777b  call    cs:__imp_SetWaitableTimer
0x180017782  nop     dword ptr [rax+rax+00h]
0x180017787  test    eax, eax
0x180017789  jz      short loc_18001779D
0x18001778b  call    cs:__imp_GetLastError
0x180017792  nop     dword ptr [rax+rax+00h]
0x180017797  cmp     eax, 32h ; '2'
0x18001779a  cmovnz  ebx, esi
0x18001779d  mov     rcx, rdi; hTimer
0x1800177a0  call    cs:__imp_CancelWaitableTimer
0x1800177a7  nop     dword ptr [rax+rax+00h]
0x1800177ac  mov     rcx, rdi; hObject
0x1800177af  call    cs:__imp_CloseHandle
0x1800177b6  nop     dword ptr [rax+rax+00h]
0x1800177bb  mov     eax, ebx
0x1800177bd  mov     rbx, [rsp+38h+arg_8]
0x1800177c2  mov     rsi, [rsp+38h+arg_10]
0x1800177c7  add     rsp, 30h
0x1800177cb  pop     rdi
0x1800177cc  retn
```
