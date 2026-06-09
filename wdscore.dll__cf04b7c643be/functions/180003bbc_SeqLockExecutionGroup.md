# SeqLockExecutionGroup

- ea: `0x180003bbc`
- end: `0x180003d10`
- name: `SeqLockExecutionGroup`
- size: `340`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x18000d8a0`

## callees

- `0x180002250`
- `0x180003bbc`
- `0x18000720c`
- `0x18000bca4`
- `0x18001dc70`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003bdf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003c75`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003bdf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003c75`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180003cf5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180003cf5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003c65`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003c65`

## string_xrefs

- `0x180003c89`: `Attempt to use SeqLockExecutionGroup from another thread`

## pseudocode

```c
__int64 __fastcall SeqLockExecutionGroup(__int64 a1)
{
  __int64 result; // rax
  DWORD LastError; // ebx
  int v4; // eax
  int v5; // ebx
  DWORD v6; // ebx
  int v7; // eax
  unsigned int v8; // ebx
  LPCWSTR lpModuleName; // [rsp+88h] [rbp+0h]

  result = IsWorkQueueAccessible(L"WdsLockExecutionGroup");
  if ( (_DWORD)result )
  {
    LastError = GetLastError();
    v4 = (unsigned int)ConstructPartialMsgW(0x4000000u, "SeqLockExecutionGroup: Initializing ExecQueue->csLock;");
    WdsSetupLogMessageW(
      v4,
      589824,
      (int)L"D",
      0,
      1548,
      L"onecore\\base\\ntsetup\\panther\\engine\\seq.c",
      (__int64)L"SeqLockExecutionGroup",
      lpModuleName,
      LastError,
      0,
      0);
    pLock(a1);
    v5 = *(_DWORD *)(a1 + 176);
    if ( GetCurrentThreadId() == v5 )
    {
      v8 = 1;
      ++*(_DWORD *)(a1 + 160);
    }
    else
    {
      v6 = GetLastError();
      v7 = (unsigned int)ConstructPartialMsgW(0x3000077u, "Attempt to use SeqLockExecutionGroup from another thread");
      WdsSetupLogMessageW(
        v7,
        589824,
        (int)L"D",
        0,
        1553,
        L"onecore\\base\\ntsetup\\panther\\engine\\seq.c",
        (__int64)L"SeqLockExecutionGroup",
        lpModuleName,
        v6,
        0,
        0);
      v8 = 0;
    }
    LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 184));
    return v8;
  }
  return result;
}

```

## disassembly

```asm
0x180003bbc  push    rbx
0x180003bbe  push    rsi
0x180003bbf  push    rdi
0x180003bc0  push    r12
0x180003bc2  push    r15
0x180003bc4  sub     rsp, 60h
0x180003bc8  mov     rsi, rcx
0x180003bcb  lea     rcx, aWdslockexecuti_0; "WdsLockExecutionGroup"
0x180003bd2  call    IsWorkQueueAccessible
0x180003bd7  test    eax, eax
0x180003bd9  jz      loc_180003D03
0x180003bdf  call    cs:__imp_GetLastError
0x180003be6  nop     dword ptr [rax+rax+00h]
0x180003beb  mov     rdi, [rsp+88h]
0x180003bf3  lea     rdx, aSeqlockexecuti_0; "SeqLockExecutionGroup: Initializing Exe"...
0x180003bfa  mov     ecx, 4000000h; unsigned int
0x180003bff  mov     ebx, eax
0x180003c01  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180003c06  mov     [rsp+88h+var_38], 0; int
0x180003c0e  lea     r15, aSeqlockexecuti; "SeqLockExecutionGroup"
0x180003c15  mov     [rsp+88h+var_40], 0; __int64
0x180003c1e  lea     r12, aOnecoreBaseNts_3; "onecore\\base\\ntsetup\\panther\\engine"...
0x180003c25  mov     [rsp+88h+var_48], ebx; int
0x180003c29  lea     r8, aD_1; "D"
0x180003c30  mov     [rsp+88h+lpModuleName], rdi; lpModuleName
0x180003c35  mov     rcx, rax; int
0x180003c38  mov     [rsp+88h+var_58], r15; __int64
0x180003c3d  xor     r9d, r9d; int
0x180003c40  mov     [rsp+88h+var_60], r12; unsigned __int16 *
0x180003c45  mov     edx, 90000h; int
0x180003c4a  mov     [rsp+88h+var_68], 60Ch; int
0x180003c52  call    WdsSetupLogMessageW
0x180003c57  mov     rcx, rsi
0x180003c5a  call    pLock
0x180003c5f  mov     ebx, [rsi+0B0h]
0x180003c65  call    cs:__imp_GetCurrentThreadId
0x180003c6c  nop     dword ptr [rax+rax+00h]
0x180003c71  cmp     eax, ebx
0x180003c73  jz      short loc_180003CE3
0x180003c75  call    cs:__imp_GetLastError
0x180003c7c  nop     dword ptr [rax+rax+00h]
0x180003c81  mov     rdi, [rsp+88h]
0x180003c89  lea     rdx, aAttemptToUseSe; "Attempt to use SeqLockExecutionGroup fr"...
0x180003c90  mov     ecx, 3000077h; unsigned int
0x180003c95  mov     ebx, eax
0x180003c97  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180003c9c  mov     [rsp+88h+var_38], 0; int
0x180003ca4  lea     r8, aD_1; "D"
0x180003cab  mov     [rsp+88h+var_40], 0; __int64
0x180003cb4  mov     rcx, rax; int
0x180003cb7  mov     [rsp+88h+var_48], ebx; int
0x180003cbb  xor     r9d, r9d; int
0x180003cbe  mov     [rsp+88h+lpModuleName], rdi; lpModuleName
0x180003cc3  mov     edx, 90000h; int
0x180003cc8  mov     [rsp+88h+var_58], r15; __int64
0x180003ccd  mov     [rsp+88h+var_60], r12; unsigned __int16 *
0x180003cd2  mov     [rsp+88h+var_68], 611h; int
0x180003cda  call    WdsSetupLogMessageW
0x180003cdf  xor     ebx, ebx
0x180003ce1  jmp     short loc_180003CEE
0x180003ce3  mov     ebx, 1
0x180003ce8  add     [rsi+0A0h], ebx
0x180003cee  lea     rcx, [rsi+0B8h]; lpCriticalSection
0x180003cf5  call    cs:__imp_LeaveCriticalSection
0x180003cfc  nop     dword ptr [rax+rax+00h]
0x180003d01  mov     eax, ebx
0x180003d03  add     rsp, 60h
0x180003d07  pop     r15
0x180003d09  pop     r12
0x180003d0b  pop     rdi
0x180003d0c  pop     rsi
0x180003d0d  pop     rbx
0x180003d0e  retn
```
