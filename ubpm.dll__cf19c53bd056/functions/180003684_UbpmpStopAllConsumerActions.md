# UbpmpStopAllConsumerActions

- ea: `0x180003684`
- end: `0x1800037f8`
- name: `UbpmpStopAllConsumerActions`
- size: `372`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x180003800`
- `0x1800179d0`

## callees

- `0x180003050`
- `0x180003684`
- `0x180007c50`
- `0x180007e30`
- `0x18000a6e0`
- `0x180027994`
- `0x180032dd8`

## import_xrefs

- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800036ee`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180003703`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180003792`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800037c2`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800037ed`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800036ee`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180003703`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180003792`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800037c2`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800037ed`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroupMembers` at `0x1800037b2`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroupMembers` at `0x1800037b2`

## pseudocode

```c
__int64 __fastcall UbpmpStopAllConsumerActions(__int64 a1, UUID *a2, __int64 a3)
{
  __int64 result; // rax
  unsigned int v7; // eax
  unsigned int v8; // r14d
  void *v9; // rax
  void *v10; // [rsp+68h] [rbp+20h] BYREF

  result = UbpmConsumerIncPendingActions(a1);
  if ( !(_DWORD)result )
  {
    UBPM_ACQUIRE_SRWLOCK_EXCLUSIVE((struct _UBPM_SRWLOCK *)(a1 + 312));
    UBPM_ACQUIRE_SRWLOCK_EXCLUSIVE((struct _UBPM_SRWLOCK *)(a1 + 208));
    v7 = UbpmTerminateActionsForConsumer(a1, a2, 0, 0, 0, a3);
    *(_DWORD *)(a1 + 216) = 0;
    v8 = v7;
    RtlReleaseSRWLockExclusive(a1 + 208);
    if ( !v8 && !a2 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF_S(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          155,
          WPP_dd0be36be19438d0c9cf63f3ad92ceae_Traceguids,
          *(_QWORD *)(*(_QWORD *)(a1 + 24) + 8LL));
      UBPM_ACQUIRE_SRWLOCK_EXCLUSIVE((struct _UBPM_SRWLOCK *)(a1 + 208));
      v9 = *(void **)(a1 + 288);
      *(_QWORD *)(a1 + 288) = 0;
      *(_BYTE *)(a1 + 296) = 1;
      v10 = v9;
      *(_DWORD *)(a1 + 216) = 0;
      RtlReleaseSRWLockExclusive(a1 + 208);
      UBPM_ACQUIRE_SRWLOCK_EXCLUSIVE((struct _UBPM_SRWLOCK *)(a1 + 192));
      CloseThreadpoolCleanupGroupMembers(*(PTP_CLEANUP_GROUP *)(a1 + 112), 1, 0);
      *(_DWORD *)(a1 + 200) = 0;
      RtlReleaseSRWLockExclusive(a1 + 192);
      UbpmUtilsFreeTimerContext(&v10, 0);
      UBPM_ACQUIRE_SRWLOCK_EXCLUSIVE((struct _UBPM_SRWLOCK *)(a1 + 208));
      *(_BYTE *)(a1 + 296) = 0;
      *(_DWORD *)(a1 + 216) = 0;
      RtlReleaseSRWLockExclusive(a1 + 208);
    }
    *(_DWORD *)(a1 + 320) = 0;
    RtlReleaseSRWLockExclusive(a1 + 312);
    UbpmConsumerDecPendingActions(a1);
    return v8;
  }
  return result;
}

```

## disassembly

```asm
0x180003684  mov     [rsp+arg_0], rbx
0x180003689  mov     [rsp+arg_8], rbp
0x18000368e  push    rsi
0x18000368f  push    rdi
0x180003690  push    r14
0x180003692  sub     rsp, 30h
0x180003696  mov     r14, r8
0x180003699  mov     rbx, rdx
0x18000369c  mov     rdi, rcx
0x18000369f  call    UbpmConsumerIncPendingActions
0x1800036a4  test    eax, eax
0x1800036a6  jnz     short loc_180003714
0x1800036a8  lea     rbp, [rdi+138h]
0x1800036af  mov     rcx, rbp; struct _UBPM_SRWLOCK *
0x1800036b2  call    ?UBPM_ACQUIRE_SRWLOCK_EXCLUSIVE@@YAXAEAU_UBPM_SRWLOCK@@@Z; UBPM_ACQUIRE_SRWLOCK_EXCLUSIVE(_UBPM_SRWLOCK &)
0x1800036b7  lea     rsi, [rdi+0D0h]
0x1800036be  mov     rcx, rsi; struct _UBPM_SRWLOCK *
0x1800036c1  call    ?UBPM_ACQUIRE_SRWLOCK_EXCLUSIVE@@YAXAEAU_UBPM_SRWLOCK@@@Z; UBPM_ACQUIRE_SRWLOCK_EXCLUSIVE(_UBPM_SRWLOCK &)
0x1800036c6  xor     r9d, r9d
0x1800036c9  mov     [rsp+48h+var_20], r14
0x1800036ce  xor     r8d, r8d
0x1800036d1  mov     [rsp+48h+var_28], 0
0x1800036d6  mov     rdx, rbx
0x1800036d9  mov     rcx, rdi
0x1800036dc  call    UbpmTerminateActionsForConsumer
0x1800036e1  mov     rcx, rsi
0x1800036e4  mov     dword ptr [rsi+8], 0
0x1800036eb  mov     r14d, eax
0x1800036ee  call    cs:__imp_RtlReleaseSRWLockExclusive
0x1800036f4  test    r14d, r14d
0x1800036f7  jz      short loc_180003727
0x1800036f9  mov     rcx, rbp
0x1800036fc  mov     dword ptr [rbp+8], 0
0x180003703  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180003709  mov     rcx, rdi
0x18000370c  call    UbpmConsumerDecPendingActions
0x180003711  mov     eax, r14d
0x180003714  mov     rbx, [rsp+48h+arg_0]
0x180003719  mov     rbp, [rsp+48h+arg_8]
0x18000371e  add     rsp, 30h
0x180003722  pop     r14
0x180003724  pop     rdi
0x180003725  pop     rsi
0x180003726  retn
0x180003727  test    rbx, rbx
0x18000372a  jnz     short loc_1800036F9
0x18000372c  mov     rcx, cs:WPP_GLOBAL_Control
0x180003733  lea     rax, WPP_GLOBAL_Control
0x18000373a  cmp     rcx, rax
0x18000373d  jz      short loc_180003762
0x18000373f  test    byte ptr [rcx+1Ch], 4
0x180003743  jz      short loc_180003762
0x180003745  mov     r9, [rdi+18h]
0x180003749  lea     r8, WPP_dd0be36be19438d0c9cf63f3ad92ceae_Traceguids
0x180003750  mov     rcx, [rcx+10h]
0x180003754  mov     edx, 9Bh
0x180003759  mov     r9, [r9+8]
0x18000375d  call    WPP_SF_S
0x180003762  mov     rcx, rsi; struct _UBPM_SRWLOCK *
0x180003765  call    ?UBPM_ACQUIRE_SRWLOCK_EXCLUSIVE@@YAXAEAU_UBPM_SRWLOCK@@@Z; UBPM_ACQUIRE_SRWLOCK_EXCLUSIVE(_UBPM_SRWLOCK &)
0x18000376a  mov     rax, [rdi+120h]
0x180003771  mov     rcx, rsi
0x180003774  mov     qword ptr [rdi+120h], 0
0x18000377f  mov     byte ptr [rdi+128h], 1
0x180003786  mov     [rsp+48h+arg_18], rax
0x18000378b  mov     dword ptr [rsi+8], 0
0x180003792  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180003798  lea     rbx, [rdi+0C0h]
0x18000379f  mov     rcx, rbx; struct _UBPM_SRWLOCK *
0x1800037a2  call    ?UBPM_ACQUIRE_SRWLOCK_EXCLUSIVE@@YAXAEAU_UBPM_SRWLOCK@@@Z; UBPM_ACQUIRE_SRWLOCK_EXCLUSIVE(_UBPM_SRWLOCK &)
0x1800037a7  mov     rcx, [rdi+70h]; ptpcg
0x1800037ab  xor     r8d, r8d; pvCleanupContext
0x1800037ae  lea     edx, [r8+1]; fCancelPendingCallbacks
0x1800037b2  call    cs:__imp_CloseThreadpoolCleanupGroupMembers
0x1800037b8  mov     rcx, rbx
0x1800037bb  mov     dword ptr [rbx+8], 0
0x1800037c2  call    cs:__imp_RtlReleaseSRWLockExclusive
0x1800037c8  xor     edx, edx; unsigned __int8
0x1800037ca  lea     rcx, [rsp+48h+arg_18]; void **
0x1800037cf  call    ?UbpmUtilsFreeTimerContext@@YAXPEAPEAXE@Z; UbpmUtilsFreeTimerContext(void * *,uchar)
0x1800037d4  mov     rcx, rsi; struct _UBPM_SRWLOCK *
0x1800037d7  call    ?UBPM_ACQUIRE_SRWLOCK_EXCLUSIVE@@YAXAEAU_UBPM_SRWLOCK@@@Z; UBPM_ACQUIRE_SRWLOCK_EXCLUSIVE(_UBPM_SRWLOCK &)
0x1800037dc  mov     byte ptr [rdi+128h], 0
0x1800037e3  mov     rcx, rsi
0x1800037e6  mov     dword ptr [rsi+8], 0
0x1800037ed  call    cs:__imp_RtlReleaseSRWLockExclusive
0x1800037f3  jmp     loc_1800036F9
```
