# SeqUnlockExecutionGroup

- ea: `0x180005760`
- end: `0x1800058e6`
- name: `SeqUnlockExecutionGroup`
- size: `390`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x18000deb0`

## callees

- `0x180002250`
- `0x180005760`
- `0x18000720c`
- `0x18000bca4`
- `0x18001dc70`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800057a7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005848`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800057a7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005848`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800058c4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800058c4`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000583a`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000583a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005797`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005797`

## string_xrefs

- `0x1800057b8`: `Attempt to use WdsUnlockExecutionGroup from another thread`
- `0x180005859`: `Trying to unlock queue which is already unlocked! (SEQ4)`

## pseudocode

```c
__int64 __fastcall SeqUnlockExecutionGroup(__int64 a1)
{
  int v3; // ebx
  DWORD LastError; // ebx
  int v5; // eax
  int v6; // eax
  void *v7; // rcx
  DWORD v8; // ebx
  int v9; // eax
  LPCWSTR lpModuleName; // [rsp+68h] [rbp+0h]

  if ( !(unsigned int)IsWorkQueueAccessible(L"WdsUnlockExecutionGroup") )
    return 0;
  pLock(a1);
  v3 = *(_DWORD *)(a1 + 176);
  if ( GetCurrentThreadId() != v3 )
  {
    LastError = GetLastError();
    v5 = (unsigned int)ConstructPartialMsgW(0x3000078u, "Attempt to use WdsUnlockExecutionGroup from another thread");
    WdsSetupLogMessageW(
      v5,
      589824,
      (int)L"D",
      0,
      1597,
      L"onecore\\base\\ntsetup\\panther\\engine\\seq.c",
      (__int64)L"SeqUnlockExecutionGroup",
      lpModuleName,
      LastError,
      0,
      0);
    return 0;
  }
  v6 = *(_DWORD *)(a1 + 160);
  if ( v6 )
  {
    v7 = *(void **)(a1 + 168);
    *(_DWORD *)(a1 + 160) = v6 - 1;
    SetEvent(v7);
  }
  else
  {
    v8 = GetLastError();
    v9 = (unsigned int)ConstructPartialMsgW(0x3000079u, "Trying to unlock queue which is already unlocked! (SEQ4)");
    WdsSetupLogMessageW(
      v9,
      589824,
      (int)L"D",
      0,
      1608,
      L"onecore\\base\\ntsetup\\panther\\engine\\seq.c",
      (__int64)L"SeqUnlockExecutionGroup",
      lpModuleName,
      v8,
      0,
      0);
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 184));
  return 1;
}

```

## disassembly

```asm
0x180005760  mov     [rsp+arg_0], rbx
0x180005765  mov     [rsp+arg_8], rsi
0x18000576a  push    rdi
0x18000576b  sub     rsp, 60h
0x18000576f  mov     rsi, rcx
0x180005772  lea     rcx, aWdsunlockexecu_0; "WdsUnlockExecutionGroup"
0x180005779  call    IsWorkQueueAccessible
0x18000577e  test    eax, eax
0x180005780  jnz     short loc_180005789
0x180005782  xor     eax, eax
0x180005784  jmp     loc_1800058D5
0x180005789  mov     rcx, rsi
0x18000578c  call    pLock
0x180005791  mov     ebx, [rsi+0B0h]
0x180005797  call    cs:__imp_GetCurrentThreadId
0x18000579e  nop     dword ptr [rax+rax+00h]
0x1800057a3  cmp     eax, ebx
0x1800057a5  jz      short loc_180005821
0x1800057a7  call    cs:__imp_GetLastError
0x1800057ae  nop     dword ptr [rax+rax+00h]
0x1800057b3  mov     rdi, [rsp+68h]
0x1800057b8  lea     rdx, aAttemptToUseWd; "Attempt to use WdsUnlockExecutionGroup "...
0x1800057bf  mov     ecx, 3000078h; unsigned int
0x1800057c4  mov     ebx, eax
0x1800057c6  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x1800057cb  mov     [rsp+68h+var_18], 0; int
0x1800057d3  lea     r8, aD_1; "D"
0x1800057da  mov     [rsp+68h+var_20], 0; __int64
0x1800057e3  mov     rcx, rax; int
0x1800057e6  mov     [rsp+68h+var_28], ebx; int
0x1800057ea  lea     rax, aSequnlockexecu; "SeqUnlockExecutionGroup"
0x1800057f1  mov     [rsp+68h+lpModuleName], rdi; lpModuleName
0x1800057f6  xor     r9d, r9d; int
0x1800057f9  mov     [rsp+68h+var_38], rax; __int64
0x1800057fe  mov     edx, 90000h; int
0x180005803  lea     rax, aOnecoreBaseNts_3; "onecore\\base\\ntsetup\\panther\\engine"...
0x18000580a  mov     [rsp+68h+var_40], rax; unsigned __int16 *
0x18000580f  mov     [rsp+68h+var_48], 63Dh; int
0x180005817  call    WdsSetupLogMessageW
0x18000581c  jmp     loc_180005782
0x180005821  mov     eax, [rsi+0A0h]
0x180005827  test    eax, eax
0x180005829  jz      short loc_180005848
0x18000582b  mov     rcx, [rsi+0A8h]; hEvent
0x180005832  dec     eax
0x180005834  mov     [rsi+0A0h], eax
0x18000583a  call    cs:__imp_SetEvent
0x180005841  nop     dword ptr [rax+rax+00h]
0x180005846  jmp     short loc_1800058BD
0x180005848  call    cs:__imp_GetLastError
0x18000584f  nop     dword ptr [rax+rax+00h]
0x180005854  mov     rdi, [rsp+68h]
0x180005859  lea     rdx, aTryingToUnlock; "Trying to unlock queue which is already"...
0x180005860  mov     ecx, 3000079h; unsigned int
0x180005865  mov     ebx, eax
0x180005867  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18000586c  mov     [rsp+68h+var_18], 0; int
0x180005874  lea     r8, aD_1; "D"
0x18000587b  mov     [rsp+68h+var_20], 0; __int64
0x180005884  mov     rcx, rax; int
0x180005887  mov     [rsp+68h+var_28], ebx; int
0x18000588b  lea     rax, aSequnlockexecu; "SeqUnlockExecutionGroup"
0x180005892  mov     [rsp+68h+lpModuleName], rdi; lpModuleName
0x180005897  xor     r9d, r9d; int
0x18000589a  mov     [rsp+68h+var_38], rax; __int64
0x18000589f  mov     edx, 90000h; int
0x1800058a4  lea     rax, aOnecoreBaseNts_3; "onecore\\base\\ntsetup\\panther\\engine"...
0x1800058ab  mov     [rsp+68h+var_40], rax; unsigned __int16 *
0x1800058b0  mov     [rsp+68h+var_48], 648h; int
0x1800058b8  call    WdsSetupLogMessageW
0x1800058bd  lea     rcx, [rsi+0B8h]; lpCriticalSection
0x1800058c4  call    cs:__imp_LeaveCriticalSection
0x1800058cb  nop     dword ptr [rax+rax+00h]
0x1800058d0  mov     eax, 1
0x1800058d5  mov     rbx, [rsp+68h+arg_0]
0x1800058da  mov     rsi, [rsp+68h+arg_8]
0x1800058df  add     rsp, 60h
0x1800058e3  pop     rdi
0x1800058e4  retn
```
