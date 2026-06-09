# CallbackManager::Enter(void)

- ea: `0x180038710`
- end: `0x1800387f7`
- name: `?Enter@CallbackManager@@QEAA?AV?$optional@VCallbackReference@@@std@@XZ`
- size: `231`
- prototype: `__int64 __fastcall(PSRWLOCK SRWLock)`
- caller_count: `8`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180019a0c`
- `0x18003816c`
- `0x180038ae8`
- `0x18003c694`
- `0x18003d4cc`
- `0x18003dea0`
- `0x18003eb10`
- `0x180040480`

## callees

- `0x180008c34`
- `0x180038710`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180038725`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180038725`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800387a9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800387a9`
- `api-ms-win-core-synch-l1-2-0!SleepConditionVariableSRW` at `0x180038760`
- `api-ms-win-core-synch-l1-2-0!SleepConditionVariableSRW` at `0x180038760`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180038731`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180038731`

## string_xrefs

- `0x1800387ce`: `onecore\vm\compute\dll\lib\core\CallbackSynchronization.h`
- `0x1800387e5`: `onecore\vm\compute\dll\lib\core\CallbackSynchronization.h`

## pseudocode

```c
__int64 __fastcall CallbackManager::Enter(PSRWLOCK SRWLock, __int64 a2)
{
  DWORD CurrentThreadId; // esi
  const char *v5; // r9
  int Ptr; // eax
  int v7; // ecx
  int Ptr_high; // edx
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  AcquireSRWLockExclusive(SRWLock);
  CurrentThreadId = GetCurrentThreadId();
  Ptr = (int)SRWLock[2].Ptr;
  if ( Ptr )
  {
    do
    {
      v7 = Ptr;
      if ( Ptr == CurrentThreadId )
        break;
      if ( LOBYTE(SRWLock[3].Ptr) )
        goto LABEL_14;
      SleepConditionVariableSRW((PCONDITION_VARIABLE)&SRWLock[1], SRWLock, 0xFFFFFFFF, 0);
      Ptr = (int)SRWLock[2].Ptr;
      v7 = Ptr;
    }
    while ( Ptr );
  }
  else
  {
    v7 = 0;
  }
  if ( LOBYTE(SRWLock[3].Ptr) )
  {
LABEL_14:
    *(_BYTE *)(a2 + 8) = 0;
  }
  else
  {
    Ptr_high = HIDWORD(SRWLock[2].Ptr);
    if ( v7 )
    {
      if ( Ptr_high < 1 )
        wil::details::in1diag3::_FailFast_Unexpected(
          retaddr,
          (void *)0x55,
          (unsigned int)"onecore\\vm\\compute\\dll\\lib\\core\\CallbackSynchronization.h",
          v5);
    }
    else
    {
      if ( Ptr_high )
        wil::details::in1diag3::_FailFast_Unexpected(
          retaddr,
          (void *)0x4F,
          (unsigned int)"onecore\\vm\\compute\\dll\\lib\\core\\CallbackSynchronization.h",
          v5);
      LODWORD(SRWLock[2].Ptr) = CurrentThreadId;
    }
    HIDWORD(SRWLock[2].Ptr) = Ptr_high + 1;
    *(_QWORD *)a2 = SRWLock;
    *(_BYTE *)(a2 + 8) = 1;
  }
  ReleaseSRWLockExclusive(SRWLock);
  return a2;
}

```

## disassembly

```asm
0x180038710  mov     [rsp+arg_10], rbx
0x180038715  mov     [rsp+arg_18], rsi
0x18003871a  push    rdi
0x18003871b  sub     rsp, 20h
0x18003871f  mov     rdi, rdx
0x180038722  mov     rbx, rcx
0x180038725  call    cs:__imp_AcquireSRWLockExclusive
0x18003872c  nop     dword ptr [rax+rax+00h]
0x180038731  call    cs:__imp_GetCurrentThreadId
0x180038738  nop     dword ptr [rax+rax+00h]
0x18003873d  mov     esi, eax
0x18003873f  mov     eax, [rbx+10h]
0x180038742  test    eax, eax
0x180038744  jz      short loc_180038777
0x180038746  mov     ecx, eax
0x180038748  cmp     eax, esi
0x18003874a  jz      short loc_180038779
0x18003874c  cmp     byte ptr [rbx+18h], 0
0x180038750  jnz     short loc_1800387A2
0x180038752  lea     rcx, [rbx+8]; ConditionVariable
0x180038756  xor     r9d, r9d; Flags
0x180038759  or      r8d, 0FFFFFFFFh; dwMilliseconds
0x18003875d  mov     rdx, rbx; SRWLock
0x180038760  call    cs:__imp_SleepConditionVariableSRW
0x180038767  nop     dword ptr [rax+rax+00h]
0x18003876c  mov     eax, [rbx+10h]
0x18003876f  mov     ecx, eax
0x180038771  test    eax, eax
0x180038773  jnz     short loc_180038746
0x180038775  jmp     short loc_180038779
0x180038777  xor     ecx, ecx
0x180038779  cmp     byte ptr [rbx+18h], 0
0x18003877d  jnz     short loc_1800387A2
0x18003877f  mov     edx, [rbx+14h]
0x180038782  test    ecx, ecx
0x180038784  jnz     short loc_18003879B
0x180038786  test    edx, edx
0x180038788  jnz     short loc_1800387C9
0x18003878a  mov     [rbx+10h], esi
0x18003878d  inc     edx
0x18003878f  mov     [rbx+14h], edx
0x180038792  mov     [rdi], rbx
0x180038795  mov     byte ptr [rdi+8], 1
0x180038799  jmp     short loc_1800387A6
0x18003879b  cmp     edx, 1
0x18003879e  jl      short loc_1800387E0
0x1800387a0  jmp     short loc_18003878D
0x1800387a2  mov     byte ptr [rdi+8], 0
0x1800387a6  mov     rcx, rbx; SRWLock
0x1800387a9  call    cs:__imp_ReleaseSRWLockExclusive
0x1800387b0  nop     dword ptr [rax+rax+00h]
0x1800387b5  mov     rbx, [rsp+28h+arg_10]
0x1800387ba  mov     rax, rdi
0x1800387bd  mov     rsi, [rsp+28h+arg_18]
0x1800387c2  add     rsp, 20h
0x1800387c6  pop     rdi
0x1800387c7  retn
0x1800387c9  mov     rcx, [rsp+28h]; this
0x1800387ce  lea     r8, aOnecoreVmCompu_0; "onecore\\vm\\compute\\dll\\lib\\core\\C"...
0x1800387d5  mov     edx, 4Fh ; 'O'; void *
0x1800387da  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x1800387e0  mov     rcx, [rsp+28h]; this
0x1800387e5  lea     r8, aOnecoreVmCompu_0; "onecore\\vm\\compute\\dll\\lib\\core\\C"...
0x1800387ec  mov     edx, 55h ; 'U'; void *
0x1800387f1  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
