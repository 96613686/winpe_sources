# _Cnd_timedwait_for_impl

- ea: `0x1800026c4`
- end: `0x180002744`
- name: `_Cnd_timedwait_for_impl`
- size: `128`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000274c`

## callees

- `0x1800026c4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002729`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002729`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800026e6`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180002716`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800026e6`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180002716`
- `api-ms-win-core-synch-l1-2-0!SleepConditionVariableSRW` at `0x180002707`
- `api-ms-win-core-synch-l1-2-0!SleepConditionVariableSRW` at `0x180002707`

## pseudocode

```c
__int64 __fastcall Cnd_timedwait_for_impl(RTL_CONDITION_VARIABLE *a1, __int64 a2, unsigned int a3, char a4)
{
  unsigned int v4; // edi
  ULONGLONG v5; // r14
  ULONGLONG TickCount64; // rsi
  DWORD CurrentThreadId; // eax

  v4 = 0;
  v5 = a3;
  TickCount64 = 0;
  if ( a4 )
    TickCount64 = GetTickCount64();
  --*(_DWORD *)(a2 + 76);
  *(_DWORD *)(a2 + 72) = -1;
  if ( !SleepConditionVariableSRW(a1 + 1, (PSRWLOCK)(a2 + 16), v5, 0) && (!a4 || GetTickCount64() - TickCount64 >= v5) )
    v4 = 2;
  CurrentThreadId = GetCurrentThreadId();
  ++*(_DWORD *)(a2 + 76);
  *(_DWORD *)(a2 + 72) = CurrentThreadId;
  return v4;
}

```

## disassembly

```asm
0x1800026c4  push    rbx
0x1800026c6  push    rbp
0x1800026c7  push    rsi
0x1800026c8  push    rdi
0x1800026c9  push    r14
0x1800026cb  push    r15
0x1800026cd  sub     rsp, 28h
0x1800026d1  xor     edi, edi
0x1800026d3  mov     r14d, r8d
0x1800026d6  xor     esi, esi
0x1800026d8  mov     bpl, r9b
0x1800026db  mov     rbx, rdx
0x1800026de  mov     r15, rcx
0x1800026e1  test    r9b, r9b
0x1800026e4  jz      short loc_1800026EF
0x1800026e6  call    cs:__imp_GetTickCount64
0x1800026ec  mov     rsi, rax
0x1800026ef  dec     dword ptr [rbx+4Ch]
0x1800026f2  lea     rdx, [rbx+10h]; SRWLock
0x1800026f6  lea     rcx, [r15+8]; ConditionVariable
0x1800026fa  mov     dword ptr [rbx+48h], 0FFFFFFFFh
0x180002701  xor     r9d, r9d; Flags
0x180002704  mov     r8d, r14d; dwMilliseconds
0x180002707  call    cs:__imp_SleepConditionVariableSRW
0x18000270d  test    eax, eax
0x18000270f  jnz     short loc_180002729
0x180002711  test    bpl, bpl
0x180002714  jz      short loc_180002724
0x180002716  call    cs:__imp_GetTickCount64
0x18000271c  sub     rax, rsi
0x18000271f  cmp     rax, r14
0x180002722  jb      short loc_180002729
0x180002724  mov     edi, 2
0x180002729  call    cs:__imp_GetCurrentThreadId
0x18000272f  inc     dword ptr [rbx+4Ch]
0x180002732  mov     [rbx+48h], eax
0x180002735  mov     eax, edi
0x180002737  add     rsp, 28h
0x18000273b  pop     r15
0x18000273d  pop     r14
0x18000273f  pop     rdi
0x180002740  pop     rsi
0x180002741  pop     rbp
0x180002742  pop     rbx
0x180002743  retn
```
