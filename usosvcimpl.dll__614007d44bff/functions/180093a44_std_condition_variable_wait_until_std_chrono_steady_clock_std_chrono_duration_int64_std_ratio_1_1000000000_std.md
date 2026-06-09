# std::condition_variable::wait_until<std::chrono::steady_clock,std::chrono::duration<__int64,std::ratio<1,1000000000>>>(std::unique_lock<std::mutex> &,std::chrono::time_point<std::chrono::steady_clock,std::chrono::duration<__int64,std::ratio<1,1000000000>>> const &)

- ea: `0x180093a44`
- end: `0x180093b0d`
- name: `??$wait_until@Usteady_clock@chrono@std@@V?$duration@_JU?$ratio@$00$0DLJKMKAA@@std@@@23@@condition_variable@std@@QEAA?AW4cv_status@1@AEAV?$unique_lock@Vmutex@std@@@1@AEBV?$time_point@Usteady_clock@chrono@std@@V?$duration@_JU?$ratio@$00$0DLJKMKAA@@std@@@23@@chrono@1@@Z`
- size: `201`
- prototype: `__int64 __fastcall(RTL_CONDITION_VARIABLE *, __int64 *, _QWORD *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180093864`
- `0x18009abc0`

## callees

- `0x180093a44`
- `0x180093bf0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180093adf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180093adf`
- `api-ms-win-core-synch-l1-2-0!SleepConditionVariableSRW` at `0x180093ad7`
- `api-ms-win-core-synch-l1-2-0!SleepConditionVariableSRW` at `0x180093ad7`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall std::condition_variable::wait_until<std::chrono::steady_clock,std::chrono::duration<__int64,std::ratio<1,1000000000>>>(
        RTL_CONDITION_VARIABLE *a1,
        __int64 *a2,
        _QWORD *a3)
{
  __int64 v6; // r9
  __int64 v7; // r8
  __int64 v8; // rdi
  BOOL v9; // ebx
  DWORD CurrentThreadId; // eax
  __int64 v12; // [rsp+60h] [rbp+18h] BYREF

  while ( 1 )
  {
    std::chrono::steady_clock::now(&v12);
    if ( *a3 == v12 || *a3 < v12 )
      break;
    v6 = *a3 - v12;
    if ( v6 <= 86400000000000LL )
    {
      v7 = v6 / 1000000;
      if ( 1000000 * (v6 / 1000000) < v6 )
        LODWORD(v7) = v7 + 1;
    }
    else
    {
      LODWORD(v7) = 86400000;
    }
    v8 = *a2;
    --*(_DWORD *)(v8 + 76);
    *(_DWORD *)(v8 + 72) = -1;
    v9 = SleepConditionVariableSRW(a1 + 1, (PSRWLOCK)(v8 + 16), v7, 0);
    CurrentThreadId = GetCurrentThreadId();
    ++*(_DWORD *)(v8 + 76);
    *(_DWORD *)(v8 + 72) = CurrentThreadId;
    if ( v9 )
      return 0;
  }
  return 1;
}

```

## disassembly

```asm
0x180093a44  mov     [rsp+arg_0], rbx
0x180093a49  push    rbp
0x180093a4a  push    rsi
0x180093a4b  push    rdi
0x180093a4c  push    r14
0x180093a4e  push    r15
0x180093a50  sub     rsp, 20h
0x180093a54  mov     rsi, r8
0x180093a57  mov     r14, rdx
0x180093a5a  mov     rbp, rcx
0x180093a5d  mov     r15, 4E94914F0000h
0x180093a67  lea     rcx, [rsp+48h+arg_10]
0x180093a6c  call    ?now@steady_clock@chrono@std@@SA?AV?$time_point@Usteady_clock@chrono@std@@V?$duration@_JU?$ratio@$00$0DLJKMKAA@@std@@@23@@23@XZ; std::chrono::steady_clock::now(void)
0x180093a71  mov     r9, [rsi]
0x180093a74  mov     rax, [rsp+48h+arg_10]
0x180093a79  cmp     r9, rax
0x180093a7c  jz      short loc_180093AF7
0x180093a7e  jl      short loc_180093AF7
0x180093a80  sub     r9, rax
0x180093a83  cmp     r9, r15
0x180093a86  jz      short loc_180093A92
0x180093a88  jl      short loc_180093A92
0x180093a8a  mov     r8d, 5265C00h
0x180093a90  jmp     short loc_180093ABF
0x180093a92  mov     rax, 431BDE82D7B634DBh
0x180093a9c  imul    r9
0x180093a9f  mov     r8, rdx
0x180093aa2  sar     r8, 12h
0x180093aa6  mov     rax, r8
0x180093aa9  shr     rax, 3Fh
0x180093aad  add     r8, rax
0x180093ab0  imul    rax, r8, 0F4240h
0x180093ab7  cmp     rax, r9
0x180093aba  jge     short loc_180093ABF
0x180093abc  inc     r8; dwMilliseconds
0x180093abf  mov     rdi, [r14]
0x180093ac2  lea     rcx, [rbp+8]; ConditionVariable
0x180093ac6  xor     r9d, r9d; Flags
0x180093ac9  dec     dword ptr [rdi+4Ch]
0x180093acc  lea     rdx, [rdi+10h]; SRWLock
0x180093ad0  mov     dword ptr [rdi+48h], 0FFFFFFFFh
0x180093ad7  call    cs:__imp_SleepConditionVariableSRW
0x180093add  mov     ebx, eax
0x180093adf  call    cs:__imp_GetCurrentThreadId
0x180093ae5  inc     dword ptr [rdi+4Ch]
0x180093ae8  mov     [rdi+48h], eax
0x180093aeb  test    ebx, ebx
0x180093aed  jz      loc_180093A67
0x180093af3  xor     eax, eax
0x180093af5  jmp     short loc_180093AFC
0x180093af7  mov     eax, 1
0x180093afc  mov     rbx, [rsp+48h+arg_0]
0x180093b01  add     rsp, 20h
0x180093b05  pop     r15
0x180093b07  pop     r14
0x180093b09  pop     rdi
0x180093b0a  pop     rsi
0x180093b0b  pop     rbp
0x180093b0c  retn
```
