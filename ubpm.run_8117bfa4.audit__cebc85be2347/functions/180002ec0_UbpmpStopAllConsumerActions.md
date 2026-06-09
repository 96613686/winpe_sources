# UbpmpStopAllConsumerActions

- ea: `0x180002ec0`
- end: `0x180003059`
- name: `UbpmpStopAllConsumerActions`
- size: `409`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x180002e2c`
- `0x180028b20`

## callees

- `0x180002ec0`
- `0x180008720`
- `0x180008920`
- `0x18000a230`
- `0x18000eb68`
- `0x1800103c0`
- `0x180035184`

## import_xrefs

- `ntdll!RtlReleaseSRWLockExclusive` at `0x180002f2a`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180002f45`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180002fdb`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180003017`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180003048`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180002f2a`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180002f45`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180002fdb`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180003017`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180003048`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroupMembers` at `0x180003001`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroupMembers` at `0x180003001`

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
0x180002ec0  mov     [rsp+arg_0], rbx
0x180002ec5  mov     [rsp+arg_8], rbp
0x180002eca  push    rsi
0x180002ecb  push    rdi
0x180002ecc  push    r14
0x180002ece  sub     rsp, 30h
0x180002ed2  mov     r14, r8
0x180002ed5  mov     rbx, rdx
0x180002ed8  mov     rdi, rcx
0x180002edb  call    UbpmConsumerIncPendingActions
0x180002ee0  test    eax, eax
0x180002ee2  jnz     short loc_180002F5C
0x180002ee4  lea     rbp, [rdi+138h]
0x180002eeb  mov     rcx, rbp; struct _UBPM_SRWLOCK *
0x180002eee  call    ?UBPM_ACQUIRE_SRWLOCK_EXCLUSIVE@@YAXAEAU_UBPM_SRWLOCK@@@Z; UBPM_ACQUIRE_SRWLOCK_EXCLUSIVE(_UBPM_SRWLOCK &)
0x180002ef3  lea     rsi, [rdi+0D0h]
0x180002efa  mov     rcx, rsi; struct _UBPM_SRWLOCK *
0x180002efd  call    ?UBPM_ACQUIRE_SRWLOCK_EXCLUSIVE@@YAXAEAU_UBPM_SRWLOCK@@@Z; UBPM_ACQUIRE_SRWLOCK_EXCLUSIVE(_UBPM_SRWLOCK &)
0x180002f02  xor     r9d, r9d
0x180002f05  mov     [rsp+48h+var_20], r14
0x180002f0a  xor     r8d, r8d
0x180002f0d  mov     [rsp+48h+var_28], 0
0x180002f12  mov     rdx, rbx
0x180002f15  mov     rcx, rdi
0x180002f18  call    UbpmTerminateActionsForConsumer
0x180002f1d  mov     rcx, rsi
0x180002f20  mov     dword ptr [rsi+8], 0
0x180002f27  mov     r14d, eax
0x180002f2a  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180002f31  nop     dword ptr [rax+rax+00h]
0x180002f36  test    r14d, r14d
0x180002f39  jz      short loc_180002F70
0x180002f3b  mov     rcx, rbp
0x180002f3e  mov     dword ptr [rbp+8], 0
0x180002f45  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180002f4c  nop     dword ptr [rax+rax+00h]
0x180002f51  mov     rcx, rdi
0x180002f54  call    UbpmConsumerDecPendingActions
0x180002f59  mov     eax, r14d
0x180002f5c  mov     rbx, [rsp+48h+arg_0]
0x180002f61  mov     rbp, [rsp+48h+arg_8]
0x180002f66  add     rsp, 30h
0x180002f6a  pop     r14
0x180002f6c  pop     rdi
0x180002f6d  pop     rsi
0x180002f6e  retn
0x180002f70  test    rbx, rbx
0x180002f73  jnz     short loc_180002F3B
0x180002f75  mov     rcx, cs:WPP_GLOBAL_Control
0x180002f7c  lea     rax, WPP_GLOBAL_Control
0x180002f83  cmp     rcx, rax
0x180002f86  jz      short loc_180002FAB
0x180002f88  test    byte ptr [rcx+1Ch], 4
0x180002f8c  jz      short loc_180002FAB
0x180002f8e  mov     r9, [rdi+18h]
0x180002f92  lea     r8, WPP_dd0be36be19438d0c9cf63f3ad92ceae_Traceguids
0x180002f99  mov     rcx, [rcx+10h]
0x180002f9d  mov     edx, 9Bh
0x180002fa2  mov     r9, [r9+8]
0x180002fa6  call    WPP_SF_S
0x180002fab  mov     rcx, rsi; struct _UBPM_SRWLOCK *
0x180002fae  call    ?UBPM_ACQUIRE_SRWLOCK_EXCLUSIVE@@YAXAEAU_UBPM_SRWLOCK@@@Z; UBPM_ACQUIRE_SRWLOCK_EXCLUSIVE(_UBPM_SRWLOCK &)
0x180002fb3  mov     rax, [rdi+120h]
0x180002fba  mov     rcx, rsi
0x180002fbd  mov     qword ptr [rdi+120h], 0
0x180002fc8  mov     byte ptr [rdi+128h], 1
0x180002fcf  mov     [rsp+48h+arg_18], rax
0x180002fd4  mov     dword ptr [rsi+8], 0
0x180002fdb  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180002fe2  nop     dword ptr [rax+rax+00h]
0x180002fe7  lea     rbx, [rdi+0C0h]
0x180002fee  mov     rcx, rbx; struct _UBPM_SRWLOCK *
0x180002ff1  call    ?UBPM_ACQUIRE_SRWLOCK_EXCLUSIVE@@YAXAEAU_UBPM_SRWLOCK@@@Z; UBPM_ACQUIRE_SRWLOCK_EXCLUSIVE(_UBPM_SRWLOCK &)
0x180002ff6  mov     rcx, [rdi+70h]; ptpcg
0x180002ffa  xor     r8d, r8d; pvCleanupContext
0x180002ffd  lea     edx, [r8+1]; fCancelPendingCallbacks
0x180003001  call    cs:__imp_CloseThreadpoolCleanupGroupMembers
0x180003008  nop     dword ptr [rax+rax+00h]
0x18000300d  mov     rcx, rbx
0x180003010  mov     dword ptr [rbx+8], 0
0x180003017  call    cs:__imp_RtlReleaseSRWLockExclusive
0x18000301e  nop     dword ptr [rax+rax+00h]
0x180003023  xor     edx, edx; unsigned __int8
0x180003025  lea     rcx, [rsp+48h+arg_18]; void **
0x18000302a  call    ?UbpmUtilsFreeTimerContext@@YAXPEAPEAXE@Z; UbpmUtilsFreeTimerContext(void * *,uchar)
0x18000302f  mov     rcx, rsi; struct _UBPM_SRWLOCK *
0x180003032  call    ?UBPM_ACQUIRE_SRWLOCK_EXCLUSIVE@@YAXAEAU_UBPM_SRWLOCK@@@Z; UBPM_ACQUIRE_SRWLOCK_EXCLUSIVE(_UBPM_SRWLOCK &)
0x180003037  mov     byte ptr [rdi+128h], 0
0x18000303e  mov     rcx, rsi
0x180003041  mov     dword ptr [rsi+8], 0
0x180003048  call    cs:__imp_RtlReleaseSRWLockExclusive
0x18000304f  nop     dword ptr [rax+rax+00h]
0x180003054  jmp     loc_180002F3B
```
